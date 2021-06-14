# Pool Lifecycle

Any user can create a new pool by calling `newBPool()` on the `BFactory` contract. The caller is set as the `controller` or pool owner.

Pools can exist in one of two states: `controlled` or `finalized`. Pools start in a controlled state and the controller may choose to make the pool finalized by calling `finalize()`. Finalize is a one-way transition. While in a controlled state, outside actors cannot add liquidity. A controlled state allows the controller to set the pool's tokens and weights.

### WPTs

All pools in WazirX are also ERC20 tokens known as WPTs \(WazirX Pool Tokens\), which represent proportional ownership in the pool's liquidity. When users add liquidity through `joinPool` or `joinswap*` they receive BPTs proportional to the amount of assets they are adding to the pool.

## Notes

WPTs are an opinionated ERC20 token implementation, and have a few subtle differences. `transferFrom` from itself does not require a previous allowance.

