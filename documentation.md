# Sample Substrate EVM Chain

## Token Specifications
- Token Symbol: SMPL
- Token Name: Sample
- Decimals: 18
- Initial Supply: 4000 tokens per account

## Build Instructions

### Prerequisites
- Rust (latest stable version)
- LLVM
- OpenSSL
- Git

### Installation Steps
1. Clone the repository:
```bash
git clone https://github.com/raizblockchain/Sample-substrate-evm.git
cd Sample-substrate-evm
```

2. Build the project:
```bash
cargo build --release
```

3. Run the development node:
```bash
./target/release/frontier-template-node --dev
```

## Configuration Files

### Token Configuration
To modify token details, edit the following files:

1. `template/node/src/chain_spec.rs`:
   - Token properties (name, symbol, decimals)
   - Initial token distribution
   - Modify the `properties()` function to change token metadata
   - Modify the `testnet_genesis()` function to change initial token distribution

2. `template/runtime/src/lib.rs`:
   - Token implementation details
   - Runtime configuration

### Consensus Configuration
To modify consensus settings, edit:

1. `template/node/src/chain_spec.rs`:
   - Authority configuration
   - Validator setup
   - Modify `authority_keys_from_seed()` and related functions

2. `template/runtime/src/lib.rs`:
   - Consensus engine configuration
   - Block time settings
   - Modify `MILLISECS_PER_BLOCK` and related constants

### EVM Configuration
To modify EVM settings, edit:

1. `template/runtime/src/lib.rs`:
   - Gas configuration
   - EVM chain ID
   - Modify `GasLimitPovSizeRatio`, `GasLimitStorageGrowthRatio`, and related parameters

## Development

### Adding New Pallets
1. Add the pallet to `Cargo.toml` in the runtime directory
2. Configure the pallet in `template/runtime/src/lib.rs`
3. Update the runtime configuration

### Customizing Genesis Configuration
1. Edit `template/node/src/chain_spec.rs`
2. Modify the `testnet_genesis()` function
3. Update the `development_config()` and `local_testnet_config()` functions

## Testing
Run the test suite:
```bash
cargo test
```

## Contributing
1. Fork the repository
2. Create your feature branch
3. Commit your changes
4. Push to the branch
5. Create a Pull Request

## License
This project is licensed under the Apache License 2.0 - see the LICENSE file for details. 