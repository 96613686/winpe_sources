# AfdTdiBindHandler

- ea: `0x1400674d0`
- end: `0x1400675a7`
- name: `AfdTdiBindHandler`
- size: `215`
- prototype: `void __fastcall(PCUNICODE_STRING SourceString)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting`

## callees

- `0x1400674d0`
- `0x140094414`

## import_xrefs

- `ntoskrnl!RtlCopyUnicodeString` at `0x14006753e`
- `ntoskrnl!RtlCopyUnicodeString` at `0x14006753e`
- `ntoskrnl!ExReleaseResourceAndLeaveCriticalRegion` at `0x14006758f`
- `ntoskrnl!ExReleaseResourceAndLeaveCriticalRegion` at `0x14006758f`
- `ntoskrnl!ExEnterCriticalRegionAndAcquireResourceExclusive` at `0x140067551`
- `ntoskrnl!ExEnterCriticalRegionAndAcquireResourceExclusive` at `0x140067551`
- `ntoskrnl!ExAllocatePool2` at `0x1400674ef`
- `ntoskrnl!ExAllocatePool2` at `0x1400674ef`

## pseudocode

```c

```
