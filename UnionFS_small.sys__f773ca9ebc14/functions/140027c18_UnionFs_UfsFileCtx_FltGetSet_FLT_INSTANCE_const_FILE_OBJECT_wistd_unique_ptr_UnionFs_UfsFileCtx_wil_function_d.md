# UnionFs::UfsFileCtx::FltGetSet(_FLT_INSTANCE const &,_FILE_OBJECT &,wistd::unique_ptr<UnionFs::UfsFileCtx,wil::function_deleter<void (*)(void *),&FltReleaseContext(void *)>> &,UnionFs::StackEventTracer &,ulong)

- ea: `0x140027c18`
- end: `0x140027e52`
- name: `?FltGetSet@UfsFileCtx@UnionFs@@SAJAEBU_FLT_INSTANCE@@AEAU_FILE_OBJECT@@AEAV?$unique_ptr@VUfsFileCtx@UnionFs@@U?$function_deleter@P6AXPEAX@Z$1?FltReleaseContext@@YAX0@Z@wil@@@wistd@@AEAVStackEventTracer@2@K@Z`
- size: `570`
- prototype: `__int64 __usercall@<rax>(PFLT_INSTANCE Instance@<rcx>, PFILE_OBJECT FileObject@<rdx>, int)`
- caller_count: `9`
- callee_count: `6`
- tags: ``

## callers

- `0x14000f680`
- `0x14002d630`
- `0x1400319bc`
- `0x1400352a8`
- `0x140035564`
- `0x140035890`
- `0x14003ff88`
- `0x1400787d4`
- `0x140078930`

## callees

- `0x14002742c`
- `0x140027c18`
- `0x140027fb8`
- `0x140056a50`
- `0x140056afc`
- `0x14007bc00`

## import_xrefs

- `ntoskrnl!KeInitializeEvent` at `0x140027dce`
- `ntoskrnl!KeInitializeEvent` at `0x140027dce`
- `FLTMGR!FltAllocateContext` at `0x140027cec`
- `FLTMGR!FltAllocateContext` at `0x140027cec`
- `FLTMGR!FltReleaseContext` at `0x140027c4b`
- `FLTMGR!FltReleaseContext` at `0x140027ca8`
- `FLTMGR!FltReleaseContext` at `0x140027e2a`
- `FLTMGR!FltReleaseContext` at `0x140027c4b`
- `FLTMGR!FltReleaseContext` at `0x140027ca8`
- `FLTMGR!FltReleaseContext` at `0x140027e2a`

## pseudocode

```c

```
