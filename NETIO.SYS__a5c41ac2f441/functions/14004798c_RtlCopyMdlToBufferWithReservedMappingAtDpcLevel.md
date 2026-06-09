# RtlCopyMdlToBufferWithReservedMappingAtDpcLevel

- ea: `0x14004798c`
- end: `0x140047a51`
- name: `RtlCopyMdlToBufferWithReservedMappingAtDpcLevel`
- size: `197`
- prototype: `__int64 __usercall@<rax>(PMDL SourceMdl@<rcx>, __int64)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x140055570`

## callees

- `0x1400553c8`
- `0x140077fa0`

## import_xrefs

- `ntoskrnl!KeAcquireSpinLockAtDpcLevel` at `0x1400479d9`
- `ntoskrnl!KeAcquireSpinLockAtDpcLevel` at `0x1400479d9`
- `ntoskrnl!KeReleaseSpinLockFromDpcLevel` at `0x140047a22`
- `ntoskrnl!KeReleaseSpinLockFromDpcLevel` at `0x140047a22`

## pseudocode

```c

```
