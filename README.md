# Contract Verification failure
This is a minimal example of a contract that fails to verify on Tenderly.

Project created with:
1. `forge init verify-test`
2. Added hardhat integration https://book.getfoundry.sh/config/hardhat
3. Added tenderly integration https://docs.tenderly.co/monitoring/smart-contract-verification/verifying-contracts-using-the-tenderly-hardhat-plugin

Steps for reproduction:
1. npm install 
2. `cp .env-template .env`
3. Fill relevant fields within .env
4. `npx hardhat run script/deploy.ts --network goerli`

Results:
```bash
➜  verify-test git:(main) ✗ npx hardhat run script/deploy.ts --network goerli
You have both ethereum-waffle and @nomicfoundation/hardhat-chai-matchers installed. They don't work correctly together, so please make sure you only use one.

We recommend you migrate to @nomicfoundation/hardhat-chai-matchers. Learn how to do it here: https://hardhat.org/migrate-from-waffle
(node:46336) ExperimentalWarning: stream/web is an experimental feature. This feature could change at any time
(Use `node --trace-warnings ...` to show where the warning was created)
Warning: SPDX license identifier not provided in source file. Before publishing, consider adding a comment containing "SPDX-License-Identifier: <SPDX-License>" to each source file. Use "SPDX-License-Identifier: UNLICENSED" for non-open-source code. Please see https://spdx.org for more information.
--> src/Greeter.sol


Compiled 3 Solidity files successfully
You have both ethereum-waffle and @nomicfoundation/hardhat-chai-matchers installed. They don't work correctly together, so please make sure you only use one.

We recommend you migrate to @nomicfoundation/hardhat-chai-matchers. Learn how to do it here: https://hardhat.org/migrate-from-waffle
(node:46345) ExperimentalWarning: stream/web is an experimental feature. This feature could change at any time
(Use `node --trace-warnings ...` to show where the warning was created)
Unexpected error occurred. 
  Error reason 404 Not Found. 
  Error context: 404 page not found

Error in hardhat-tenderly: Verification failed. There was an error during the API request, please contact support with the above error.
{Greeter} deployed to 0x2E8719ffE56874730994a1f882acBF2ce77b122E
```