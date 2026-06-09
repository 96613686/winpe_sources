# MpDlpUpdatePolicyWorker

- ea: `0x14006d3b0`
- end: `0x14006d763`
- name: `MpDlpUpdatePolicyWorker`
- size: `947`
- prototype: `void __stdcall(PFLT_GENERIC_WORKITEM FltWorkItem, PVOID FltObject, PVOID Context)`
- caller_count: `0`
- callee_count: `5`
- tags: `registry_config, installer_update`

## callees

- `0x140003460`
- `0x1400118d0`
- `0x140030060`
- `0x14006d3b0`
- `0x14006d764`

## import_xrefs

- `ntoskrnl!RtlEqualUnicodeString` at `0x14006d618`
- `ntoskrnl!RtlEqualUnicodeString` at `0x14006d618`
- `ntoskrnl!ExFreePoolWithTag` at `0x14006d577`
- `ntoskrnl!ExFreePoolWithTag` at `0x14006d593`
- `ntoskrnl!ExFreePoolWithTag` at `0x14006d693`
- `ntoskrnl!ExFreePoolWithTag` at `0x14006d6af`
- `ntoskrnl!ExFreePoolWithTag` at `0x14006d6d3`
- `ntoskrnl!ExFreePoolWithTag` at `0x14006d577`
- `ntoskrnl!ExFreePoolWithTag` at `0x14006d593`
- `ntoskrnl!ExFreePoolWithTag` at `0x14006d693`
- `ntoskrnl!ExFreePoolWithTag` at `0x14006d6af`
- `ntoskrnl!ExFreePoolWithTag` at `0x14006d6d3`
- `FLTMGR!FltReleaseContext` at `0x14006d713`
- `FLTMGR!FltReleaseContext` at `0x14006d713`
- `FLTMGR!FltReleasePushLock` at `0x14006d4ca`
- `FLTMGR!FltReleasePushLock` at `0x14006d65a`
- `FLTMGR!FltReleasePushLock` at `0x14006d4ca`
- `FLTMGR!FltReleasePushLock` at `0x14006d65a`
- `FLTMGR!FltFreeGenericWorkItem` at `0x14006d72b`
- `FLTMGR!FltFreeGenericWorkItem` at `0x14006d72b`
- `FLTMGR!FltAcquirePushLockExclusive` at `0x14006d410`
- `FLTMGR!FltAcquirePushLockExclusive` at `0x14006d5f9`
- `FLTMGR!FltAcquirePushLockExclusive` at `0x14006d410`
- `FLTMGR!FltAcquirePushLockExclusive` at `0x14006d5f9`

## pseudocode

```c

```
