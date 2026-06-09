# A2dpSidebandAudioWdmEndpoint::SetAvdtpOffloadHandle(ushort)

- ea: `0x140081ba0`
- end: `0x140081bfe`
- name: `?SetAvdtpOffloadHandle@A2dpSidebandAudioWdmEndpoint@@_A2PAGE@@EAAXG@Z`
- size: `94`
- prototype: `void __fastcall(A2dpSidebandAudioWdmEndpoint *this, __int16)`
- caller_count: `3`
- callee_count: `1`
- tags: `authz_impersonation`

## callers

- `0x14007e530`
- `0x140080ec4`
- `0x1400810e4`

## callees

- `0x1400202e8`

## import_xrefs

- `ntoskrnl!KeEnterCriticalRegion` at `0x140081bbc`
- `ntoskrnl!KeEnterCriticalRegion` at `0x140081bbc`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x140081bcb`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x140081bcb`

## pseudocode

```c

```
