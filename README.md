# US Holiday GitHub Action

GitHub Action that determines whether the current system clock date is a US Holiday

## Inputs

### `included_holidays`

**Required** A comma separated list of holiday names to include (from this list: https://github.com/bradymholt/us-holidays-helper/blob/12c6fa7f3e5f64565275a11e39f775177baf2407/src/index.ts#L13-L31)

**Default** `"newYearsDay,martinLutherKingJrDay,presidentsDay,memorialDay,juneteenth,indigenousPeoplesDay,independenceDay,laborDay,thanksgiving,christmas,newYearsEve"`

## Example usage

```yaml
steps:
  - uses: ynab/us-holiday-action@v1.1
    id: us-holiday-check
    with:
      included_holidays: "newYearsDay,martinLutherKingJrDay,presidentsDay,memorialDay,juneteenth,indigenousPeoplesDay,independenceDay,laborDay,thanksgiving,christmas,newYearsEve"  
  - run: echo "Today is a US Holiday"
    if: steps.us-holiday-check.outputs.is-holiday == 'true'
```
