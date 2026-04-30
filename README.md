realmask — Verified Agent Identity

> A Web3 intelligence agent backed by a verified human identity on Billions Network.  
> Built for transparent market analysis, honest project reviews, and exposing bad actors in Web3.

**Agent DID**: `did:iden3:billions:main:2VmAkXrihYaM89bpmdhkr8fVFvvBpXW1n3Qnd6w5Zz`  
**Backed by**: [@realmisky](https://github.com/realmisky)  
**Network**: Billions Network (onchain verified)  
**Status**: ✅ Active — Human-linked and identity verified

---

## Overview

This repository contains the verified identity infrastructure for **realmask**, a Web3 intelligence agent operated by [@realmisky](https://github.com/realmisky).

The identity is built on the [Billions Network](https://billions.network/) using the `verified-agent-identity` skill — a decentralized identity toolkit powered by the iden3 protocol. Once installed and linked, the agent can:

- Prove its identity to other agents and users cryptographically
- Sign and verify challenges for authentication
- Protect sensitive data with verified credentials
- Build an onchain reputation that cannot be faked
- Participate in the **First AI Agent Rewards (FAIAR)** program

---

## Why Verified Identity Matters in Web3

In a space full of anonymous bots, fake accounts, and coordinated scams, a verifiable agent identity is a competitive advantage. **realmask** is human-backed, onchain-verified, and cryptographically provable — meaning:

- Every market analysis it produces is traceable to a real, verified human operator
- Its identity cannot be spoofed or impersonated by bad actors
- Community members can verify the agent's DID directly on Billions Network

---

## Installation

### Requirements

- Node.js >= v20
- npm

### Step 1 — Install the Skill

Using ClawHub:
```bash
npx clawhub@latest install verified-agent-identity
```

Or using skills.sh:
```bash
npx skills add BillionsNetwork/verified-agent-identity
```

### Step 2 — Install Dependencies

```bash
cd scripts && npm install && cd ..
```

### Step 3 — Create Identity

Generate a new identity:
```bash
node scripts/createNewEthereumIdentity.js
```

Or use an existing Ethereum private key:
```bash
node scripts/createNewEthereumIdentity.js --key <your-ethereum-private-key>
```

### Step 4 — Link Human Identity to Agent

```bash
node scripts/manualLinkHumanToAgent.js --challenge '{"name": "realmask", "description": "A verified agent dedicated to truth in Web3 — exposing bad actors, analyzing markets, and building trusted communities one signal at a time."}'
```

Open the generated URL in your browser and complete the verification via Google, Apple, or wallet + face scan.

---

## Usage

### Check Your Identity
```bash
node scripts/getIdentities.js
```

### Prove Identity to Another Agent or User
```bash
node scripts/linkHumanToAgent.js --challenge '{"name": "realmask", "description": "A verified agent dedicated to truth in Web3"}'
```

### Verify Someone Else's Identity

```bash
# Step 1 — Generate a challenge for their DID
node scripts/generateChallenge.js --did <their-did>

# Step 2 — Verify their signed token
node scripts/verifySignature.js --did <their-did> --token <their-token>
```

### Sign a Challenge
```bash
node scripts/signChallenge.js --challenge <challenge_value>
```

---

## Security

> ⚠️ **NEVER commit your private key or `.env` file to this repository.**

All sensitive identity data is stored outside the workspace at:
```
$HOME/.openclaw/billions/
```

Key files in that directory:

| File | Contents |
|------|----------|
| `kms.json` | Private keys (encrypt with `BILLIONS_NETWORK_MASTER_KMS_KEY`) |
| `defaultDid.json` | Active DID and public key |
| `identities.json` | Identity metadata |
| `challenges.json` | Authentication challenge history |
| `credentials.json` | Verifiable credentials |

To enable AES-256-GCM encryption for your private keys:
```bash
export BILLIONS_NETWORK_MASTER_KMS_KEY="your-strong-secret"
```

---

## Project Structure

```
verified-agent-identity/
├── skills/
│   └── verified-agent-identity/
│       ├── SKILL.md
│       ├── README.md
│       └── scripts/
│           ├── createNewEthereumIdentity.js
│           ├── getIdentities.js
│           ├── generateChallenge.js
│           ├── signChallenge.js
│           ├── linkHumanToAgent.js
│           ├── manualLinkHumanToAgent.js
│           └── verifySignature.js
└── .clawhub/
```

---

## Resources

- [Billions Network](https://billions.network/)
- [ClawHub — verified-agent-identity](https://clawhub.ai/OBrezhniev/verified-agent-identity)
- [BillionsNetwork GitHub](https://github.com/BillionsNetwork/verified-agent-identity)
- [Billions Discord Support](https://discord.com/invite/billions-ntwk/#support)
- [Billions Wallet](https://wallet.billions.network/)

---

## License

This project uses the `verified-agent-identity` skill from [BillionsNetwork](https://github.com/BillionsNetwork/verified-agent-identity).  
Operated by [@realmisky](https://github.com/realmisky).
