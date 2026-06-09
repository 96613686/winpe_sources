# UnionFs::UfsStreamCtx::FltGet(_FLT_INSTANCE const &,_FILE_OBJECT const &,bool,wistd::unique_ptr<UnionFs::UfsStreamCtx,wil::function_deleter<void (*)(void *),&FltReleaseContext(void *)>> &,UnionFs::StackEventTracer &)

- ea: `0x140027890`
- end: `0x1400279d6`
- name: `?FltGet@UfsStreamCtx@UnionFs@@SAJAEBU_FLT_INSTANCE@@AEBU_FILE_OBJECT@@_NAEAV?$unique_ptr@VUfsStreamCtx@UnionFs@@U?$function_deleter@P6AXPEAX@Z$1?FltReleaseContext@@YAX0@Z@wil@@@wistd@@AEAVStackEventTracer@2@@Z`
- size: `326`
- prototype: `__int64 __usercall@<rax>(PFLT_INSTANCE Instance@<rcx>, PFILE_OBJECT FileObject@<rdx>, int)`
- caller_count: `4`
- callee_count: `2`
- tags: ``

## callers

- `0x14000e2ac`
- `0x140027ef8`
- `0x140034900`
- `0x140079920`

## callees

- `0x140027890`
- `0x140056bd0`

## import_xrefs

- `FLTMGR!FltGetStreamContext` at `0x1400278f2`
- `FLTMGR!FltGetStreamContext` at `0x1400278f2`
- `FLTMGR!FltReleaseContext` at `0x1400278c0`
- `FLTMGR!FltReleaseContext` at `0x140027919`
- `FLTMGR!FltReleaseContext` at `0x14002798d`
- `FLTMGR!FltReleaseContext` at `0x1400279b4`
- `FLTMGR!FltReleaseContext` at `0x1400278c0`
- `FLTMGR!FltReleaseContext` at `0x140027919`
- `FLTMGR!FltReleaseContext` at `0x14002798d`
- `FLTMGR!FltReleaseContext` at `0x1400279b4`

## pseudocode

```c

```
