# Threat Hunt: Internal Port Scanning on yc-vm-mde

This repository documents a threat hunt focused on detecting unauthorized internal network scanning using Microsoft Defender for Endpoint (MDE) telemetry.

## Scenario
The server team observed degraded performance on older systems within the `10.0.0.0/16` network. After ruling out external DDoS activity, internal misuse was suspected. This hunt uncovered PowerShell-based port scanning activity originating from `yc-vm-mde`.

## Key Artifacts
- **Script Used**: `portscan.ps1`
- **Execution Method**: `powershell.exe -ExecutionPolicy Bypass -File C:\programdata\portscan.ps1`
- **Detected On**: June 1 & June 7, 2025
- **MITRE ATT&CK**: T1046 (Network Service Scanning), T1059.001 (PowerShell)

## Files Included
- `threat-hunt-portscan.md`: Full investigation report
- `portscan_timeline_header_updated.png`: Execution timeline visualization

## Outcome
The hunt successfully identified internal misuse of PowerShell to perform lateral reconnaissance. Recommendations include tightening script execution policies and enhanced internal traffic monitoring.

## Report

See [`threat-hunt-portscan-report.md`](./threat-hunt-portscan-report.md) for the full analysis, IOCs, timeline, and recommendations.
