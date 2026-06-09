# UnionFs::UfsStreamHandleCtx::FltSet(_FLT_INSTANCE const &,_FILE_OBJECT const &,wistd::unique_ptr<UnionFs::UfsStreamHandleCtx,wil::function_deleter<void (*)(void *),&FltReleaseContext(void *)>> &,UnionFs::StackEventTracer &)

- ea: `0x1400284f0`
- end: `0x140028622`
- name: `?FltSet@UfsStreamHandleCtx@UnionFs@@SAJAEBU_FLT_INSTANCE@@AEBU_FILE_OBJECT@@AEAV?$unique_ptr@VUfsStreamHandleCtx@UnionFs@@U?$function_deleter@P6AXPEAX@Z$1?FltReleaseContext@@YAX0@Z@wil@@@wistd@@AEAVStackEventTracer@2@@Z`
- size: `306`
- prototype: `__int64 __fastcall(PFLT_INSTANCE Instance, PFILE_OBJECT FileObject)`
- caller_count: `3`
- callee_count: `3`
- tags: ``

## callers

- `0x140011a60`
- `0x14005913c`
- `0x140062a64`

## callees

- `0x1400284f0`
- `0x140056bd0`
- `0x14007b2b0`

## import_xrefs

- `FLTMGR!FltSetStreamHandleContext` at `0x14002855a`
- `FLTMGR!FltSetStreamHandleContext` at `0x14002855a`
- `FLTMGR!FltReleaseContext` at `0x140028581`
- `FLTMGR!FltReleaseContext` at `0x1400285dd`
- `FLTMGR!FltReleaseContext` at `0x1400285fe`
- `FLTMGR!FltReleaseContext` at `0x140028581`
- `FLTMGR!FltReleaseContext` at `0x1400285dd`
- `FLTMGR!FltReleaseContext` at `0x1400285fe`

## pseudocode

```c

```
