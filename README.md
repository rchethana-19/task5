# Task 5: Wireshark Traffic Analysis

## Objective
Capture live packets using Wireshark and analyze at least three different network protocols.

---

## Tools Used
- **Wireshark** 
- Firefox Browser

---

## Steps Followed

1. **Installed Wireshark** from [https://www.wireshark.org](https://www.wireshark.org).
2. Launched the app and selected `eth0` interface for packet capture.
3. Started live capture (blue shark fin icon).
4. In browser:
   - Visited `http://example.com` → for unencrypted HTTP traffic.
   - Visited `https://google.com` → for encrypted HTTPS (TLS) traffic.
5. In Terminal:
   - Ran `ping google.com` to generate ICMP traffic.
6. Stopped capture after ~1 minute.
7. Applied filters:
   - `http` — to view HTTP request/response packets.
   - `tls` — to observe TLS encrypted traffic.
   - `dns` — to analyze DNS lookups.

---

## Protocols Identified

| Protocol | Filter Used | Description |
|----------|-------------|-------------|
| HTTP     | `http`      | Unencrypted web traffic showing URLs, headers, content. |
| TLS      | `tls`       | Encrypted traffic for HTTPS; packet content hidden. |
| DNS      | `dns`       | Domain Name System queries/responses for site resolution. |

---

## Deliverables 
- `README.md` — This documentation
- `/screenshots/` — Captures of filtered traffic

---

## Key Learnings

- **HTTP** packets can expose all details — making them insecure.
- **TLS/HTTPS** encrypts content but still shows destination IP and handshake metadata.
- **DNS** requests can leak visited domains unless DNS over HTTPS is used.
- Filtering in Wireshark helps narrow down and isolate specific traffic types.

---

## Bonus Observations
- TCP 3-way handshake observed: filtered with `tcp.flags.syn == 1`
- ICMP packets captured from `ping google.com`

---

