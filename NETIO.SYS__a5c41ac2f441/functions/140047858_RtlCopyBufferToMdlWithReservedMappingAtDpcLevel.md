# RtlCopyBufferToMdlWithReservedMappingAtDpcLevel

- ea: `0x140047858`
- end: `0x14004791d`
- name: `RtlCopyBufferToMdlWithReservedMappingAtDpcLevel`
- size: `197`
- prototype: `__int64 __usercall@<rax>(void *Src@<rcx>, PMDL SourceMdl@<rdx>, __int64)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x140054f60`

## callees

- `0x140055250`
- `0x140077fa0`

## import_xrefs

- `ntoskrnl!KeAcquireSpinLockAtDpcLevel` at `0x1400478a5`
- `ntoskrnl!KeAcquireSpinLockAtDpcLevel` at `0x1400478a5`
- `ntoskrnl!KeReleaseSpinLockFromDpcLevel` at `0x1400478ee`
- `ntoskrnl!KeReleaseSpinLockFromDpcLevel` at `0x1400478ee`

## pseudocode

```c

```
