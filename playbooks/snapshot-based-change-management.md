# Snapshot-Based Change Management on Production VPS

## Context

Live VPS systems rarely fail because of hardware.
They fail during **changes**:
- DNS updates
- SSL renewals
- Docker reconfigurations
- Firewall rule edits

This playbook documents how to make those changes **safe and reversible**.

---

## Principle: Snapshot First

Before touching:
- Docker
- DNS
- SSL
- Firewall rules

Take a full VPS snapshot.

This turns:
> “I hope this works”

into:
> “I can undo this in minutes.”

---

## Why Snapshots Matter

Snapshots provide:
- Instant rollback
- Confidence during debugging
- Freedom to iterate safely

They remove pressure during outages.

---

## Example Scenario

### Change Required
- DNS provider updated URLs
- Docker services required updates
- SSL certificates needed correction
- TOR IP ranges blocked at firewall level

### Risk
- Service downtime
- Lockout
- Cert misconfiguration

### Mitigation
- Snapshot taken before each major phase
- Changes applied incrementally
- Rollback available at every step

---

## Snapshot Naming Strategy

Use names that describe the **intent**, not the outcome.

Good:
- `dns-change-pre-docker`
- `ssl-cert-fix`
- `tor-ips-blocked`

Bad:
- `backup1`
- `test`
- `final-final-really-final`

---

## Operational Benefits

- Faster incident resolution
- Reduced stress during outages
- Easier root-cause analysis
- Professional-grade change hygiene

---

## Takeaway

If a change can break production,
it deserves a snapshot.

Snapshots are not paranoia.
They are operational maturity.
