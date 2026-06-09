# UnionFs::UfsFileCtx::FltGet(_FLT_INSTANCE const &,_FILE_OBJECT const &,bool,wistd::unique_ptr<UnionFs::UfsFileCtx,wil::function_deleter<void (*)(void *),&FltReleaseContext(void *)>> &,UnionFs::StackEventTracer &)

- ea: `0x1400274cc`
- end: `0x14002761b`
- name: `?FltGet@UfsFileCtx@UnionFs@@SAJAEBU_FLT_INSTANCE@@AEBU_FILE_OBJECT@@_NAEAV?$unique_ptr@VUfsFileCtx@UnionFs@@U?$function_deleter@P6AXPEAX@Z$1?FltReleaseContext@@YAX0@Z@wil@@@wistd@@AEAVStackEventTracer@2@@Z`
- size: `335`
- prototype: `__int64 __usercall@<rax>(PFLT_INSTANCE Instance@<rcx>, PFILE_OBJECT FileObject@<rdx>, int)`
- caller_count: `3`
- callee_count: `2`
- tags: ``

## callers

- `0x140027cb8`
- `0x140058008`
- `0x1400704d4`

## callees

- `0x1400274cc`
- `0x140056bd0`

## import_xrefs

- `FLTMGR!FltGetFileContext` at `0x14002752e`
- `FLTMGR!FltGetFileContext` at `0x14002752e`
- `FLTMGR!FltReleaseContext` at `0x1400274fc`
- `FLTMGR!FltReleaseContext` at `0x140027555`
- `FLTMGR!FltReleaseContext` at `0x1400275d2`
- `FLTMGR!FltReleaseContext` at `0x1400275f9`
- `FLTMGR!FltReleaseContext` at `0x1400274fc`
- `FLTMGR!FltReleaseContext` at `0x140027555`
- `FLTMGR!FltReleaseContext` at `0x1400275d2`
- `FLTMGR!FltReleaseContext` at `0x1400275f9`

## pseudocode

```c

```
