# A2dpSidebandAudioWdmEndpoint::GetAvdtpOffloadHandle(void)

- ea: `0x14007f81c`
- end: `0x14007f870`
- name: `?GetAvdtpOffloadHandle@A2dpSidebandAudioWdmEndpoint@@_A2PAGE@@EBAGXZ`
- size: `84`
- prototype: `__int64 __fastcall(A2dpSidebandAudioWdmEndpoint *this)`
- caller_count: `3`
- callee_count: `1`
- tags: `authz_impersonation`

## callers

- `0x140036b7c`
- `0x140036e14`
- `0x1400370ac`

## callees

- `0x1400202e8`

## import_xrefs

- `ntoskrnl!KeEnterCriticalRegion` at `0x14007f830`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14007f830`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x14007f83f`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x14007f83f`

## pseudocode

```c

```
