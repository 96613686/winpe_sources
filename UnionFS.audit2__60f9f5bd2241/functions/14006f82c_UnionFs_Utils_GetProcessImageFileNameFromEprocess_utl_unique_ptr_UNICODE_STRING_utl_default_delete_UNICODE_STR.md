# UnionFs::Utils::GetProcessImageFileNameFromEprocess(utl::unique_ptr<_UNICODE_STRING,utl::default_delete<_UNICODE_STRING>> &,UnionFs::StackEventTracer &,_KPROCESS *)

- ea: `0x14006f82c`
- end: `0x14006f9e6`
- name: `?GetProcessImageFileNameFromEprocess@Utils@UnionFs@@YAJAEAV?$unique_ptr@U_UNICODE_STRING@@U?$default_delete@U_UNICODE_STRING@@@utl@@@utl@@AEAVStackEventTracer@2@PEAU_KPROCESS@@@Z`
- size: `442`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x14006f70c`

## callees

- `0x140056bd0`
- `0x140056c44`
- `0x14006f82c`

## import_xrefs

- `ntoskrnl!IoGetCurrentProcess` at `0x14006f85c`
- `ntoskrnl!IoGetCurrentProcess` at `0x14006f85c`
- `ntoskrnl!PsGetProcessImageFileName` at `0x14006f86b`
- `ntoskrnl!PsGetProcessImageFileName` at `0x14006f86b`
- `ntoskrnl!ExFreePoolWithTag` at `0x14006f850`
- `ntoskrnl!ExFreePoolWithTag` at `0x14006f982`
- `ntoskrnl!ExFreePoolWithTag` at `0x14006f850`
- `ntoskrnl!ExFreePoolWithTag` at `0x14006f982`
- `ntoskrnl!ExAllocatePool2` at `0x14006f92a`
- `ntoskrnl!ExAllocatePool2` at `0x14006f92a`

## pseudocode

```c

```
