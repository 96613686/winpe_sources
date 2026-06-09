# ReadVariableLengthPolicy

- ea: `0x140163a94`
- end: `0x140163bda`
- name: `ReadVariableLengthPolicy`
- size: `326`
- prototype: `__int64 __usercall@<rax>(HANDLE KeyHandle@<rcx>, PUNICODE_STRING ValueName@<rdx>, __int64, __int64)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x1401646f4`

## callees

- `0x140163a94`
- `0x140209448`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x140163b49`
- `ntoskrnl!ExFreePoolWithTag` at `0x140163bad`
- `ntoskrnl!ExFreePoolWithTag` at `0x140163b49`
- `ntoskrnl!ExFreePoolWithTag` at `0x140163bad`
- `ntoskrnl!ExAllocatePool2` at `0x140163b6e`
- `ntoskrnl!ExAllocatePool2` at `0x140163b6e`

## pseudocode

```c

```
