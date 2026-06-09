# UnionFs::UfsFileCtx::FltGet(_FLT_INSTANCE const &,_FILE_OBJECT const &,bool,wistd::unique_ptr<UnionFs::UfsFileCtx,wil::function_deleter<void (*)(void *),&FltReleaseContext(void *)>> &,UnionFs::StackEventTracer &)

- ea: `0x14002742c`
- end: `0x14002757b`
- name: `?FltGet@UfsFileCtx@UnionFs@@SAJAEBU_FLT_INSTANCE@@AEBU_FILE_OBJECT@@_NAEAV?$unique_ptr@VUfsFileCtx@UnionFs@@U?$function_deleter@P6AXPEAX@Z$1?FltReleaseContext@@YAX0@Z@wil@@@wistd@@AEAVStackEventTracer@2@@Z`
- size: `335`
- prototype: `__int64 __usercall@<rax>(PFLT_INSTANCE Instance@<rcx>, PFILE_OBJECT FileObject@<rdx>, int)`
- caller_count: `3`
- callee_count: `2`
- tags: ``

## callers

- `0x140027c18`
- `0x140057e88`
- `0x1400702e4`

## callees

- `0x14002742c`
- `0x140056a50`

## import_xrefs

- `FLTMGR!FltGetFileContext` at `0x14002748e`
- `FLTMGR!FltGetFileContext` at `0x14002748e`
- `FLTMGR!FltReleaseContext` at `0x14002745c`
- `FLTMGR!FltReleaseContext` at `0x1400274b5`
- `FLTMGR!FltReleaseContext` at `0x140027532`
- `FLTMGR!FltReleaseContext` at `0x140027559`
- `FLTMGR!FltReleaseContext` at `0x14002745c`
- `FLTMGR!FltReleaseContext` at `0x1400274b5`
- `FLTMGR!FltReleaseContext` at `0x140027532`
- `FLTMGR!FltReleaseContext` at `0x140027559`

## pseudocode

```c

```
