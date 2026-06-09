# TiWorkerCoreInstanceCreatedAndLoadComponentStore

- ea: `0x140008730`
- end: `0x140008794`
- name: `TiWorkerCoreInstanceCreatedAndLoadComponentStore`
- size: `100`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `installer_update, broker_com_uri`

## callees

- `0x140008700`
- `0x140008730`
- `0x14000e328`
- `0x14002b010`

## string_xrefs

- `0x140008772`: `Unable to load component store`

## pseudocode

```c
__int64 TiWorkerCoreInstanceCreatedAndLoadComponentStore()
{
  int v0; // eax
  int ComponentStore; // eax

  if ( vpfnCbsCoreStopIdleProcessing )
  {
    v0 = vpfnCbsCoreStopIdleProcessing();
    if ( v0 < 0 )
      CBSWdsLog(0x4000000u, v0, (size_t *)1, "Failed to stop idle processing");
  }
  ComponentStore = vpfnCbsCoreLoadComponentStore();
  if ( ComponentStore < 0 )
    CBSWdsLog(0x4000000u, ComponentStore, (size_t *)1, "Unable to load component store");
  return TiWorkerCoreInstanceCreated();
}

```

## disassembly

```asm
0x140008730  sub     rsp, 28h
0x140008734  mov     rax, cs:?vpfnCbsCoreStopIdleProcessing@@3P6AJXZEA; long (*vpfnCbsCoreStopIdleProcessing)(void)
0x14000873b  test    rax, rax
0x14000873e  jz      short loc_140008762
0x140008740  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140008745  test    eax, eax
0x140008747  jns     short loc_140008762
0x140008749  lea     r9, aFailedToStopId; "Failed to stop idle processing"
0x140008750  mov     r8d, 1
0x140008756  mov     edx, eax
0x140008758  mov     ecx, 4000000h
0x14000875d  call    ?CBSWdsLog@@YAXW4tagLOG_SETUPLOG_SEVERITY@@J_NPEBDZZ; CBSWdsLog(tagLOG_SETUPLOG_SEVERITY,long,bool,char const *,...)
0x140008762  mov     rax, cs:?vpfnCbsCoreLoadComponentStore@@3P6AJXZEA; long (*vpfnCbsCoreLoadComponentStore)(void)
0x140008769  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000876e  test    eax, eax
0x140008770  jns     short loc_14000878B
0x140008772  lea     r9, aUnableToLoadCo; "Unable to load component store"
0x140008779  mov     r8d, 1
0x14000877f  mov     edx, eax
0x140008781  mov     ecx, 4000000h
0x140008786  call    ?CBSWdsLog@@YAXW4tagLOG_SETUPLOG_SEVERITY@@J_NPEBDZZ; CBSWdsLog(tagLOG_SETUPLOG_SEVERITY,long,bool,char const *,...)
0x14000878b  add     rsp, 28h
0x14000878f  jmp     TiWorkerCoreInstanceCreated
```
