# UnionFs::UfsStreamHandleCtx::IsDirectoryEmpty(_FLT_CALLBACK_DATA const &,bool *,UnionFs::StackEventTracer &,bool)

- ea: `0x140029560`
- end: `0x14002978a`
- name: `?IsDirectoryEmpty@UfsStreamHandleCtx@UnionFs@@QEBAJAEBU_FLT_CALLBACK_DATA@@PEA_NAEAVStackEventTracer@2@_N@Z`
- size: `554`
- prototype: `__int64 __usercall@<rax>(UnionFs::UfsStreamHandleCtx *__hidden this@<rcx>, const struct _FLT_CALLBACK_DATA *@<rdx>, bool *@<r8>, struct UnionFs::StackEventTracer *@<r9>, bool)`
- caller_count: `3`
- callee_count: `7`
- tags: ``

## callers

- `0x14002e3c8`
- `0x1400628e4`
- `0x1400703f0`

## callees

- `0x140025b28`
- `0x140025d48`
- `0x140029560`
- `0x140056ac4`
- `0x140056afc`
- `0x14007af90`
- `0x14007bc00`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x1400296db`
- `ntoskrnl!ExFreePoolWithTag` at `0x140029739`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400296db`
- `ntoskrnl!ExFreePoolWithTag` at `0x140029739`
- `ntoskrnl!ExAllocatePool2` at `0x14002959b`
- `ntoskrnl!ExAllocatePool2` at `0x14002959b`
- `ntoskrnl!RtlEqualUnicodeString` at `0x14002967f`
- `ntoskrnl!RtlEqualUnicodeString` at `0x14002969d`
- `ntoskrnl!RtlEqualUnicodeString` at `0x14002967f`
- `ntoskrnl!RtlEqualUnicodeString` at `0x14002969d`

## string_xrefs

- `0x140029716`: `UnionFs::UfsStreamHandleCtx::IsDirectoryEmpty`
- `0x14002975a`: `UnionFs::UfsStreamHandleCtx::IsDirectoryEmpty`
- `0x140029705`: `PUSH: Enumerating and Merging Directory`

## pseudocode

```c

```
