# EfspFileRequiresEncryption

- ea: `0x140212dfc`
- end: `0x1402134d1`
- name: `EfspFileRequiresEncryption`
- size: `1749`
- prototype: ``
- caller_count: `2`
- callee_count: `19`
- tags: `registry_config, loader_planting, service_task`

## callers

- `0x1401161d0`
- `0x140212b90`

## callees

- `0x140030b70`
- `0x1400313ec`
- `0x140031b38`
- `0x140036464`
- `0x140037f80`
- `0x14003c94c`
- `0x14005876c`
- `0x1400592c0`
- `0x140117b90`
- `0x140117e00`
- `0x140117ed8`
- `0x140117f24`
- `0x140118250`
- `0x140119bcc`
- `0x140119bf4`
- `0x140119ce4`
- `0x14011c91c`
- `0x1401476a8`
- `0x140212dfc`

## import_xrefs

- `ntoskrnl!KeGetCurrentIrql` at `0x140212ed5`
- `ntoskrnl!KeGetCurrentIrql` at `0x140212ed5`
- `ntoskrnl!RtlInitUnicodeString` at `0x140213041`
- `ntoskrnl!RtlInitUnicodeString` at `0x14021306a`
- `ntoskrnl!RtlInitUnicodeString` at `0x140213123`
- `ntoskrnl!RtlInitUnicodeString` at `0x140213041`
- `ntoskrnl!RtlInitUnicodeString` at `0x14021306a`
- `ntoskrnl!RtlInitUnicodeString` at `0x140213123`
- `ntoskrnl!ExFreePoolWithTag` at `0x14021344c`
- `ntoskrnl!ExFreePoolWithTag` at `0x140213477`
- `ntoskrnl!ExFreePoolWithTag` at `0x140213492`
- `ntoskrnl!ExFreePoolWithTag` at `0x14021344c`
- `ntoskrnl!ExFreePoolWithTag` at `0x140213477`
- `ntoskrnl!ExFreePoolWithTag` at `0x140213492`
- `ntoskrnl!ExAcquireFastMutex` at `0x1402130c2`
- `ntoskrnl!ExAcquireFastMutex` at `0x14021317b`
- `ntoskrnl!ExAcquireFastMutex` at `0x1402130c2`
- `ntoskrnl!ExAcquireFastMutex` at `0x14021317b`
- `ntoskrnl!ExReleaseFastMutex` at `0x1402130fa`
- `ntoskrnl!ExReleaseFastMutex` at `0x1402131b3`
- `ntoskrnl!ExReleaseFastMutex` at `0x1402130fa`
- `ntoskrnl!ExReleaseFastMutex` at `0x1402131b3`
- `ntoskrnl!PsGetCurrentThreadTeb` at `0x140212f6f`
- `ntoskrnl!PsGetCurrentThreadTeb` at `0x140212f6f`
- `ntoskrnl!wcsrchr` at `0x140213249`
- `ntoskrnl!wcsrchr` at `0x140213249`

## string_xrefs

- `0x140213032`: `\Registry\Machine\System\CurrentControlSet\Services\NTFS\EFS\Parameters`
- `0x14021305b`: `EdpExcludedExtensions`
- `0x140213114`: `EdpExcludedPaths`

## pseudocode

```c

```
