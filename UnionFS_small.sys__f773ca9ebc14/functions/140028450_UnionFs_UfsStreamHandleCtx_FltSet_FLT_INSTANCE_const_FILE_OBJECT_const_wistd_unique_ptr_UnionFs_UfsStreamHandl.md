# UnionFs::UfsStreamHandleCtx::FltSet(_FLT_INSTANCE const &,_FILE_OBJECT const &,wistd::unique_ptr<UnionFs::UfsStreamHandleCtx,wil::function_deleter<void (*)(void *),&FltReleaseContext(void *)>> &,UnionFs::StackEventTracer &)

- ea: `0x140028450`
- end: `0x140028582`
- name: `?FltSet@UfsStreamHandleCtx@UnionFs@@SAJAEBU_FLT_INSTANCE@@AEBU_FILE_OBJECT@@AEAV?$unique_ptr@VUfsStreamHandleCtx@UnionFs@@U?$function_deleter@P6AXPEAX@Z$1?FltReleaseContext@@YAX0@Z@wil@@@wistd@@AEAVStackEventTracer@2@@Z`
- size: `306`
- prototype: `__int64 __fastcall(PFLT_INSTANCE Instance, PFILE_OBJECT FileObject)`
- caller_count: `3`
- callee_count: `3`
- tags: ``

## callers

- `0x140011a40`
- `0x140058fbc`
- `0x1400628e4`

## callees

- `0x140028450`
- `0x140056a50`
- `0x14007af90`

## import_xrefs

- `FLTMGR!FltSetStreamHandleContext` at `0x1400284ba`
- `FLTMGR!FltSetStreamHandleContext` at `0x1400284ba`
- `FLTMGR!FltReleaseContext` at `0x1400284e1`
- `FLTMGR!FltReleaseContext` at `0x14002853d`
- `FLTMGR!FltReleaseContext` at `0x14002855e`
- `FLTMGR!FltReleaseContext` at `0x1400284e1`
- `FLTMGR!FltReleaseContext` at `0x14002853d`
- `FLTMGR!FltReleaseContext` at `0x14002855e`

## pseudocode

```c

```
