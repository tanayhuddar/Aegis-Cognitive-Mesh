

# 🚀 Aegis Cognitive Mesh (ACM)

Live demo : visit website :(https://aegis-cognitive-mesh.streamlit.app/)

**Azure-native, secure, AI decision fabric — “prove-then-execute.”**

ACM is a highly secure, **attested decision-making mesh** that ensures all actions are safe, auditable, and resilient. It blends **Confidential Compute, Azure Attestation, Digital Twins, and formal policy checks** into a single fabric for **deterministic, interview-ready demos**.

---

## ✨ Core Capabilities

* 🔒 **Confidential Compute** — protect sensitive operations.
* ✅ **Azure Attestation** — prove environment integrity before execution.
* 🔑 **Secure Key Release (SKR)** — secrets only released after verification.
* 🌐 **Azure Digital Twins (ADT)** — simulate warehouses, routes, and systems before acting.
* 📏 **Policy Verification with Z3** — enforce compliance and prevent unsafe decisions.

---

## 🎯 Goals

* Guarantee decisions are **safe + auditable**.
* Deliver a **resilient, production-suitable demo system**.
* Maintain **cost hygiene** (student credits, minimal Azure usage).
* Keep runs **deterministic and replayable** for interviews.

---

## 💰 Cost Hygiene

* Use **Azure for Students** credits sparingly.
* Run compute **only during tests/demos**.
* Set spend alerts; keep Digital Twins minimal.
* Avoid costly services (Managed HSM, Purview) unless needed.
* Prefer **local simulation** whenever possible.

---

## 🏗️ Architecture

📌 See `ops/architecture-v1.png` (or `architecture-template.txt`)

The mesh integrates:

* **Proof-then-execute pipeline**
* **Policy hashing + lock enforcement**
* **Immutable audit chain**
* **Local + cloud simulation modes**

---

## ⚙️ Development

### 🔗 Git Hooks

Enable policy-lock checks on commit:

```bash
bash scripts/setup_hooks.sh
```

### 📜 Policy Hashing & Locking

* Compute hash: `make policy-hash`
* Update lock: `make policy-lock`
* Commit lock:

  ```bash
  git add policies/policy.lock
  git commit -m "chore: update policy.lock after policy change"
  ```

### 🧪 CI Enforcement

CI verifies that the computed policy hash matches `policies/policy.lock`.
If mismatched → CI fails until updated.

---

## 🧩 Common Tasks

* Compute current policy hash → `make policy-hash`
* Update policy lock → `make policy-lock`
* Fix blocked commits → `make policy-lock && git add policies/policy.lock`






