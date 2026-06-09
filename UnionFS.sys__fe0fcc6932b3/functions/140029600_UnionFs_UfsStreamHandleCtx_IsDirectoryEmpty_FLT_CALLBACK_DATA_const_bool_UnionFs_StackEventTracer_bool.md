# UnionFs::UfsStreamHandleCtx::IsDirectoryEmpty(_FLT_CALLBACK_DATA const &,bool *,UnionFs::StackEventTracer &,bool)

- ea: `0x140029600`
- end: `0x14002982a`
- name: `?IsDirectoryEmpty@UfsStreamHandleCtx@UnionFs@@QEBAJAEBU_FLT_CALLBACK_DATA@@PEA_NAEAVStackEventTracer@2@_N@Z`
- size: `554`
- prototype: `__int64 __usercall@<rax>(UnionFs::UfsStreamHandleCtx *__hidden this@<rcx>, const struct _FLT_CALLBACK_DATA *@<rdx>, bool *@<r8>, struct UnionFs::StackEventTracer *@<r9>, bool)`
- caller_count: `3`
- callee_count: `7`
- tags: ``

## callers

- `0x14002e468`
- `0x140062a64`
- `0x1400705e0`

## callees

- `0x140025bc8`
- `0x140025de8`
- `0x140029600`
- `0x140056c44`
- `0x140056c7c`
- `0x14007b2b0`
- `0x14007bf40`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x14002977b`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400297d9`
- `ntoskrnl!ExFreePoolWithTag` at `0x14002977b`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400297d9`
- `ntoskrnl!ExAllocatePool2` at `0x14002963b`
- `ntoskrnl!ExAllocatePool2` at `0x14002963b`
- `ntoskrnl!RtlEqualUnicodeString` at `0x14002971f`
- `ntoskrnl!RtlEqualUnicodeString` at `0x14002973d`
- `ntoskrnl!RtlEqualUnicodeString` at `0x14002971f`
- `ntoskrnl!RtlEqualUnicodeString` at `0x14002973d`

## string_xrefs

- `0x1400297b6`: `UnionFs::UfsStreamHandleCtx::IsDirectoryEmpty`
- `0x1400297fa`: `UnionFs::UfsStreamHandleCtx::IsDirectoryEmpty`
- `0x1400297a5`: `PUSH: Enumerating and Merging Directory`

## pseudocode

```c

```
