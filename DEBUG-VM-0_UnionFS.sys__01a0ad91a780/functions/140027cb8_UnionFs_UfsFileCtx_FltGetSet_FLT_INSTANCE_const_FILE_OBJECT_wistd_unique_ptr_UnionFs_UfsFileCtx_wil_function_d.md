# UnionFs::UfsFileCtx::FltGetSet(_FLT_INSTANCE const &,_FILE_OBJECT &,wistd::unique_ptr<UnionFs::UfsFileCtx,wil::function_deleter<void (*)(void *),&FltReleaseContext(void *)>> &,UnionFs::StackEventTracer &,ulong)

- ea: `0x140027cb8`
- end: `0x140027ef2`
- name: `?FltGetSet@UfsFileCtx@UnionFs@@SAJAEBU_FLT_INSTANCE@@AEAU_FILE_OBJECT@@AEAV?$unique_ptr@VUfsFileCtx@UnionFs@@U?$function_deleter@P6AXPEAX@Z$1?FltReleaseContext@@YAX0@Z@wil@@@wistd@@AEAVStackEventTracer@2@K@Z`
- size: `570`
- prototype: `__int64 __usercall@<rax>(PFLT_INSTANCE Instance@<rcx>, PFILE_OBJECT FileObject@<rdx>, int)`
- caller_count: `9`
- callee_count: `6`
- tags: ``

## callers

- `0x14000f6a0`
- `0x14002d6d0`
- `0x140031a5c`
- `0x1400353e0`
- `0x14003569c`
- `0x1400359c8`
- `0x140040110`
- `0x140078afc`
- `0x140078c58`

## callees

- `0x1400274cc`
- `0x140027cb8`
- `0x140028058`
- `0x140056bd0`
- `0x140056c7c`
- `0x14007bf40`

## import_xrefs

- `ntoskrnl!KeInitializeEvent` at `0x140027e6e`
- `ntoskrnl!KeInitializeEvent` at `0x140027e6e`
- `FLTMGR!FltAllocateContext` at `0x140027d8c`
- `FLTMGR!FltAllocateContext` at `0x140027d8c`
- `FLTMGR!FltReleaseContext` at `0x140027ceb`
- `FLTMGR!FltReleaseContext` at `0x140027d48`
- `FLTMGR!FltReleaseContext` at `0x140027eca`
- `FLTMGR!FltReleaseContext` at `0x140027ceb`
- `FLTMGR!FltReleaseContext` at `0x140027d48`
- `FLTMGR!FltReleaseContext` at `0x140027eca`

## pseudocode

```c

```
