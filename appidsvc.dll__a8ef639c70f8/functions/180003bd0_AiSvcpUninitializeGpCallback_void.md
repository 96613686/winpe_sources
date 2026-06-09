# AiSvcpUninitializeGpCallback(void)

- ea: `0x180003bd0`
- end: `0x180003c76`
- name: `?AiSvcpUninitializeGpCallback@@YAXXZ`
- size: `166`
- prototype: `void(void)`
- caller_count: `2`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x180002d5c`
- `0x180003940`

## callees

- `0x180003bd0`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180003bfa`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180003bfa`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180003c07`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180003c07`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWait` at `0x180003c36`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWait` at `0x180003c36`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180003be8`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180003be8`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolWaitCallbacks` at `0x180003c29`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolWaitCallbacks` at `0x180003c29`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180003c60`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180003c60`
- `USERENV!UnregisterGPNotification` at `0x180003c53`
- `USERENV!UnregisterGPNotification` at `0x180003c53`

## pseudocode

```c
void AiSvcpUninitializeGpCallback(void)
{
  if ( AiSvcpGpNotifyTimer )
  {
    SetThreadpoolTimer(AiSvcpGpNotifyTimer, 0, 0, 0);
    WaitForThreadpoolTimerCallbacks(AiSvcpGpNotifyTimer, 1);
    CloseThreadpoolTimer(AiSvcpGpNotifyTimer);
    AiSvcpGpNotifyTimer = 0;
  }
  if ( AiSvcpGroupPolicyWaitObject )
  {
    WaitForThreadpoolWaitCallbacks(AiSvcpGroupPolicyWaitObject, 1);
    CloseThreadpoolWait(AiSvcpGroupPolicyWaitObject);
    AiSvcpGroupPolicyWaitObject = 0;
  }
  if ( AiSvcpGroupPolicyChangeEvent )
  {
    UnregisterGPNotification(AiSvcpGroupPolicyChangeEvent);
    CloseHandle(AiSvcpGroupPolicyChangeEvent);
    AiSvcpGroupPolicyChangeEvent = 0;
  }
}

```

## disassembly

```asm
0x180003bd0  sub     rsp, 28h
0x180003bd4  mov     rcx, cs:?AiSvcpGpNotifyTimer@@3PEAU_TP_TIMER@@EA; pti
0x180003bdb  test    rcx, rcx
0x180003bde  jz      short loc_180003C18
0x180003be0  xor     r9d, r9d; msWindowLength
0x180003be3  xor     r8d, r8d; msPeriod
0x180003be6  xor     edx, edx; pftDueTime
0x180003be8  call    cs:__imp_SetThreadpoolTimer
0x180003bee  mov     rcx, cs:?AiSvcpGpNotifyTimer@@3PEAU_TP_TIMER@@EA; pti
0x180003bf5  mov     edx, 1; fCancelPendingCallbacks
0x180003bfa  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x180003c00  mov     rcx, cs:?AiSvcpGpNotifyTimer@@3PEAU_TP_TIMER@@EA; pti
0x180003c07  call    cs:__imp_CloseThreadpoolTimer
0x180003c0d  mov     cs:?AiSvcpGpNotifyTimer@@3PEAU_TP_TIMER@@EA, 0; _TP_TIMER * AiSvcpGpNotifyTimer
0x180003c18  mov     rcx, cs:?AiSvcpGroupPolicyWaitObject@@3PEAU_TP_WAIT@@EA; pwa
0x180003c1f  test    rcx, rcx
0x180003c22  jz      short loc_180003C47
0x180003c24  mov     edx, 1; fCancelPendingCallbacks
0x180003c29  call    cs:__imp_WaitForThreadpoolWaitCallbacks
0x180003c2f  mov     rcx, cs:?AiSvcpGroupPolicyWaitObject@@3PEAU_TP_WAIT@@EA; pwa
0x180003c36  call    cs:__imp_CloseThreadpoolWait
0x180003c3c  mov     cs:?AiSvcpGroupPolicyWaitObject@@3PEAU_TP_WAIT@@EA, 0; _TP_WAIT * AiSvcpGroupPolicyWaitObject
0x180003c47  mov     rcx, cs:?AiSvcpGroupPolicyChangeEvent@@3PEAXEA; hEvent
0x180003c4e  test    rcx, rcx
0x180003c51  jz      short loc_180003C71
0x180003c53  call    cs:__imp_UnregisterGPNotification
0x180003c59  mov     rcx, cs:?AiSvcpGroupPolicyChangeEvent@@3PEAXEA; hObject
0x180003c60  call    cs:__imp_CloseHandle
0x180003c66  mov     cs:?AiSvcpGroupPolicyChangeEvent@@3PEAXEA, 0; void * AiSvcpGroupPolicyChangeEvent
0x180003c71  add     rsp, 28h
0x180003c75  retn
```
