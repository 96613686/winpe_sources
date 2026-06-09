# VsmmDmSlpWaitForTransientMbpOperationComplete

- ea: `0x140007b68`
- end: `0x140007d72`
- name: `VsmmDmSlpWaitForTransientMbpOperationComplete`
- size: `522`
- prototype: `__int64 __fastcall(int, int)`
- caller_count: `1`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x14003966c`

## callees

- `0x140007b68`
- `0x140009df8`
- `0x14001b440`
- `0x1400204e8`
- `0x140021c60`
- `0x140021e00`

## import_xrefs

- `ntoskrnl!KeReleaseGuardedMutex` at `0x140007d17`
- `ntoskrnl!KeReleaseGuardedMutex` at `0x140007d3c`
- `ntoskrnl!KeReleaseGuardedMutex` at `0x140007d17`
- `ntoskrnl!KeReleaseGuardedMutex` at `0x140007d3c`
- `ntoskrnl!KeAcquireGuardedMutex` at `0x140007bd0`
- `ntoskrnl!KeAcquireGuardedMutex` at `0x140007bd0`
- `ntoskrnl!RtlTestBitNoFenceEx` at `0x140007c13`
- `ntoskrnl!RtlTestBitNoFenceEx` at `0x140007c13`

## pseudocode

```c

```
