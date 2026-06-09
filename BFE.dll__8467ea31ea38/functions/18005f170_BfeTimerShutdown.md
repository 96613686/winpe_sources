# BfeTimerShutdown

- ea: `0x18005f170`
- end: `0x18005f1ba`
- name: `BfeTimerShutdown`
- size: `74`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x18003f0a0`

## callees

- `0x18005d184`
- `0x18005f170`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolCleanupGroupMembers` at `0x18005f190`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolCleanupGroupMembers` at `0x18005f190`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolCleanupGroup` at `0x18005f19d`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolCleanupGroup` at `0x18005f19d`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpool` at `0x18005f1af`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpool` at `0x18005f1af`

## pseudocode

```c
void __fastcall BfeTimerShutdown(BfeTimerTracking *a1)
{
  if ( BfeTimerTracking::Reset(a1) )
  {
    if ( gBfeTimerCallBackEnvironment.CleanupGroup )
    {
      CloseThreadpoolCleanupGroupMembers(gBfeTimerCallBackEnvironment.CleanupGroup, 1, 0);
      CloseThreadpoolCleanupGroup(gBfeTimerCallBackEnvironment.CleanupGroup);
    }
    if ( gBfeTimerCallBackEnvironment.Pool )
      CloseThreadpool(gBfeTimerCallBackEnvironment.Pool);
  }
}

```

## disassembly

```asm
0x18005f170  sub     rsp, 28h
0x18005f174  call    ?Reset@BfeTimerTracking@@QEAA_NXZ; BfeTimerTracking::Reset(void)
0x18005f179  test    al, al
0x18005f17b  jz      short loc_18005F1B5
0x18005f17d  mov     rcx, cs:?gBfeTimerCallBackEnvironment@@3U_TP_CALLBACK_ENVIRON_V3@@A.CleanupGroup; ptpcg
0x18005f184  test    rcx, rcx
0x18005f187  jz      short loc_18005F1A3
0x18005f189  xor     r8d, r8d; pvCleanupContext
0x18005f18c  lea     edx, [r8+1]; fCancelPendingCallbacks
0x18005f190  call    cs:__imp_CloseThreadpoolCleanupGroupMembers
0x18005f196  mov     rcx, cs:?gBfeTimerCallBackEnvironment@@3U_TP_CALLBACK_ENVIRON_V3@@A.CleanupGroup; ptpcg
0x18005f19d  call    cs:__imp_CloseThreadpoolCleanupGroup
0x18005f1a3  mov     rcx, cs:?gBfeTimerCallBackEnvironment@@3U_TP_CALLBACK_ENVIRON_V3@@A.Pool; ptpp
0x18005f1aa  test    rcx, rcx
0x18005f1ad  jz      short loc_18005F1B5
0x18005f1af  call    cs:__imp_CloseThreadpool
0x18005f1b5  add     rsp, 28h
0x18005f1b9  retn
```
