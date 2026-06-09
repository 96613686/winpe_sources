# VidVppInitialize

- ea: `0x1400fc060`
- end: `0x1400fc188`
- name: `VidVppInitialize`
- size: `296`
- prototype: `__int64 __usercall@<rax>(PVOID DeferredContext@<rcx>, __int64, __int64)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x14009a058`

## callees

- `0x140021e00`
- `0x140075a68`

## import_xrefs

- `ntoskrnl!ExWaitForRundownProtectionRelease` at `0x1400fc162`
- `ntoskrnl!ExWaitForRundownProtectionRelease` at `0x1400fc162`
- `ntoskrnl!ExRundownCompleted` at `0x1400fc171`
- `ntoskrnl!ExRundownCompleted` at `0x1400fc171`
- `ntoskrnl!KeInitializeEvent` at `0x1400fc0d0`
- `ntoskrnl!KeInitializeEvent` at `0x1400fc0d0`
- `ntoskrnl!KeInitializeDpc` at `0x1400fc0fd`
- `ntoskrnl!KeInitializeDpc` at `0x1400fc0fd`

## pseudocode

```c

```
