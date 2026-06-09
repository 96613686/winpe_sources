# FltpDoUnloadFilter

- ea: `0x18004eb7c`
- end: `0x18004ee4f`
- name: `FltpDoUnloadFilter`
- size: `723`
- prototype: `__int64 __fastcall(PVOID FltObject)`
- caller_count: `2`
- callee_count: `8`
- tags: `registry_config, service_task`

## callers

- `0x180053a90`
- `0x180053c90`

## callees

- `0x180009f20`
- `0x180010400`
- `0x180019160`
- `0x180024800`
- `0x1800248e0`
- `0x18004eb7c`
- `0x18004ee58`
- `0x18005dcc0`

## import_xrefs

- `ntoskrnl!ObfDereferenceObject` at `0x18004ee16`
- `ntoskrnl!ObfDereferenceObject` at `0x18004ee16`
- `ntoskrnl!ObfReferenceObject` at `0x18004ec0d`
- `ntoskrnl!ObfReferenceObject` at `0x18004ec0d`
- `ntoskrnl!RtlAppendUnicodeToString` at `0x18004ed65`
- `ntoskrnl!RtlAppendUnicodeToString` at `0x18004ed65`
- `ntoskrnl!RtlAppendUnicodeStringToString` at `0x18004ed82`
- `ntoskrnl!RtlAppendUnicodeStringToString` at `0x18004ed82`
- `ntoskrnl!IoGetStackLimits` at `0x18004ecdd`
- `ntoskrnl!IoGetStackLimits` at `0x18004ecdd`
- `ntoskrnl!KeEnterCriticalRegion` at `0x18004ec31`
- `ntoskrnl!KeEnterCriticalRegion` at `0x18004ec31`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x18004eca8`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x18004eca8`
- `ntoskrnl!ExReleaseFastResource` at `0x18004ec9c`
- `ntoskrnl!ExReleaseFastResource` at `0x18004ec9c`
- `ntoskrnl!ExAcquireFastResourceExclusive` at `0x18004ec49`
- `ntoskrnl!ExAcquireFastResourceExclusive` at `0x18004ec49`
- `ntoskrnl!ZwUnloadDriver` at `0x18004ed93`
- `ntoskrnl!ZwUnloadDriver` at `0x18004ed93`
- `HAL!KeQueryPerformanceCounter` at `0x18004ebc2`
- `HAL!KeQueryPerformanceCounter` at `0x18004ebc2`

## string_xrefs

- `0x18004ed54`: `\Registry\Machine\System\ControlSet001\Services\`

## pseudocode

```c

```
