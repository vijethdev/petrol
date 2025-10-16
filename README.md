# Petrol Bunk Tracker

Petrol Bunk Tracker is a role-based management system designed to streamline daily operations for multi-fuel petrol bunks. The platform emphasises accurate stock tracking, shift accountability, and transparent reconciliation across all fuel and oil products.

## Objective

Build a petrol bunk management system that:

- Supports role-based access for owners, managers, and operators.
- Tracks fuel types (MS, XP, Diesel) and oil inventory (20/40/60 grades).
- Deducts fuel and oil inventory in real time as sales are recorded.
- Manages shifts, daily readings, expenses, and receipts.
- Provides auto-reconciliation to maintain consistent stock balances.

## Roles and Access

### Owner (Admin)
- Full access to all system data.
- Visibility into negative balances.
- Manage shifts and override closures.

### Manager
- Access to current and limited historical data.
- Record daily tank readings and manage receipts.
- Approve and lock day-end reconciliations.
- Update operator shifts or reassign operators as required.

### Operator
- Access limited to current-day operations.
- Enter quick transactions for cash, UPI, card, oil, tests, expenses, and credits.

## Fuel and Inventory Types

- **Petrol**: MS (Regular), XP (Premium)
- **Diesel**: Standard
- **Oil**: Grades 20, 40, 60 tracked as inventory with unit counts and value.

## Pumps, Nozzles, and Alias System

- Each pump supports up to four nozzles.
- Every nozzle has a unique alias (e.g., `P1-MS1`, `P1-XP2`) that maps directly to its tank.
- Alias mapping ensures accurate carry-forward logic and precise reconciliation of dispensed fuel.

## Manager Responsibilities

- Record tank readings three times a day: Opening (morning), Midday, and Closing (night).
- Log receipts for new fuel or oil deliveries.
- Approve and lock daily data after reconciliation.
- Adjust operator shifts or perform reallocations when necessary.

## Operator Quick Entry Functions

Operators can quickly record:

- Sales: Cash, UPI, Card, Credit.
- Oil Sales: 20/40/60 grades.
- Tests: Morning or customer.
- Expenses and credits.

All entries immediately deduct quantities from the relevant fuel tanks or oil inventory.

## KPI Dashboards

- **Owner Dashboard**: Aggregated KPIs for cash, UPI, card, expenses, and credits, including per-attendant performance.
- **Manager Dashboard**: Daily stock cards for MS, XP, Diesel, and Oil with variance analysis and approval controls.
- **Operator Dashboard**: Current-day statistics only, without historical access.

## Daily Closure and Shift Logic

- Automatic closure at 11:59 PM ends all open shifts.
- Owner and manager can manually override or modify shifts.
- Operators can sign in from any device without logging others out.
- Opening balances for new shifts auto-populate from the previous closing balance.

## Variance and Adjustment Logic

- Opening variance tolerance: ±2.0 L.
- Variance beyond tolerance requires manager or owner approval and an adjustment entry.
- If the day is unlocked, the previous closing balance updates to match the approved opening.
- If the day is locked, an adjustment record is created and applied to tank stock.

## Carry-Forward Mismatch Resolution

To prevent discrepancies between closing and opening balances:

- Unique nozzle aliases ensure accurate pump tracking.
- Opening balances auto-fill from the previous closing figures.
- Variance beyond tolerance triggers approval workflows with reason logging.
- Adjustment records preserve stock continuity and resolve mismatches.
- Audit reports list adjustments by pump, nozzle, and date for transparency.

## Data Security and Visibility

- Operators only see current-day data.
- Negative balances are visible only to the owner.
- Managers have access to limited historical records.
- All data is stored locally with export capabilities (CSV/Excel).

