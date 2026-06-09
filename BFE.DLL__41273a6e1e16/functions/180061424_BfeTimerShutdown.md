# BfeTimerShutdown

- ea: `0x180061424`
- end: `0x180061481`
- name: `BfeTimerShutdown`
- size: `93`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180040330`

## callees

- `0x18005f20c`
- `0x180061424`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolCleanupGroupMembers` at `0x180061444`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolCleanupGroupMembers` at `0x180061444`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolCleanupGroup` at `0x180061457`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolCleanupGroup` at `0x180061457`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpool` at `0x18006146f`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpool` at `0x18006146f`

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
0x180061424  sub     rsp, 28h
0x180061428  call    ?Reset@BfeTimerTracking@@QEAA_NXZ; BfeTimerTracking::Reset(void)
0x18006142d  test    al, al
0x18006142f  jz      short loc_18006147B
0x180061431  mov     rcx, cs:?gBfeTimerCallBackEnvironment@@3U_TP_CALLBACK_ENVIRON_V3@@A.CleanupGroup; ptpcg
0x180061438  test    rcx, rcx
0x18006143b  jz      short loc_180061463
0x18006143d  xor     r8d, r8d; pvCleanupContext
0x180061440  lea     edx, [r8+1]; fCancelPendingCallbacks
0x180061444  call    cs:__imp_CloseThreadpoolCleanupGroupMembers
0x18006144b  nop     dword ptr [rax+rax+00h]
0x180061450  mov     rcx, cs:?gBfeTimerCallBackEnvironment@@3U_TP_CALLBACK_ENVIRON_V3@@A.CleanupGroup; ptpcg
0x180061457  call    cs:__imp_CloseThreadpoolCleanupGroup
0x18006145e  nop     dword ptr [rax+rax+00h]
0x180061463  mov     rcx, cs:?gBfeTimerCallBackEnvironment@@3U_TP_CALLBACK_ENVIRON_V3@@A.Pool; ptpp
0x18006146a  test    rcx, rcx
0x18006146d  jz      short loc_18006147B
0x18006146f  call    cs:__imp_CloseThreadpool
0x180061476  nop     dword ptr [rax+rax+00h]
0x18006147b  add     rsp, 28h
0x18006147f  retn
```
