# UnionFs::Utils::GetProcessImageFileNameFromEprocess(utl::unique_ptr<_UNICODE_STRING,utl::default_delete<_UNICODE_STRING>> &,UnionFs::StackEventTracer &,_KPROCESS *)

- ea: `0x14006f63c`
- end: `0x14006f7f6`
- name: `?GetProcessImageFileNameFromEprocess@Utils@UnionFs@@YAJAEAV?$unique_ptr@U_UNICODE_STRING@@U?$default_delete@U_UNICODE_STRING@@@utl@@@utl@@AEAVStackEventTracer@2@PEAU_KPROCESS@@@Z`
- size: `442`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x14006f51c`

## callees

- `0x140056a50`
- `0x140056ac4`
- `0x14006f63c`

## import_xrefs

- `ntoskrnl!IoGetCurrentProcess` at `0x14006f66c`
- `ntoskrnl!IoGetCurrentProcess` at `0x14006f66c`
- `ntoskrnl!PsGetProcessImageFileName` at `0x14006f67b`
- `ntoskrnl!PsGetProcessImageFileName` at `0x14006f67b`
- `ntoskrnl!ExFreePoolWithTag` at `0x14006f660`
- `ntoskrnl!ExFreePoolWithTag` at `0x14006f792`
- `ntoskrnl!ExFreePoolWithTag` at `0x14006f660`
- `ntoskrnl!ExFreePoolWithTag` at `0x14006f792`
- `ntoskrnl!ExAllocatePool2` at `0x14006f73a`
- `ntoskrnl!ExAllocatePool2` at `0x14006f73a`

## pseudocode

```c

```
