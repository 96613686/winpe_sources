# AfdTdiBindHandler

- ea: `0x140067670`
- end: `0x140067747`
- name: `AfdTdiBindHandler`
- size: `215`
- prototype: `__int64 __fastcall(PCUNICODE_STRING SourceString)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting`

## callees

- `0x140067670`
- `0x140094414`

## import_xrefs

- `ntoskrnl!RtlCopyUnicodeString` at `0x1400676de`
- `ntoskrnl!RtlCopyUnicodeString` at `0x1400676de`
- `ntoskrnl!ExReleaseResourceAndLeaveCriticalRegion` at `0x14006772f`
- `ntoskrnl!ExReleaseResourceAndLeaveCriticalRegion` at `0x14006772f`
- `ntoskrnl!ExEnterCriticalRegionAndAcquireResourceExclusive` at `0x1400676f1`
- `ntoskrnl!ExEnterCriticalRegionAndAcquireResourceExclusive` at `0x1400676f1`
- `ntoskrnl!ExAllocatePool2` at `0x14006768f`
- `ntoskrnl!ExAllocatePool2` at `0x14006768f`

## pseudocode

```c

```
