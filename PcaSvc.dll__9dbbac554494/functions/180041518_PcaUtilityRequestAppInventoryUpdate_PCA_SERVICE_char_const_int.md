# PcaUtilityRequestAppInventoryUpdate(_PCA_SERVICE *,char const *,int)

- ea: `0x180041518`
- end: `0x18004162d`
- name: `?PcaUtilityRequestAppInventoryUpdate@@YAKPEAU_PCA_SERVICE@@PEBDH@Z`
- size: `277`
- prototype: `unsigned int __fastcall(struct _PCA_SERVICE *, const char *, int)`
- caller_count: `3`
- callee_count: `3`
- tags: `file_ops, service_task, installer_update, broker_com_uri`

## callers

- `0x180021b90`
- `0x180027fc0`
- `0x180053470`

## callees

- `0x180012920`
- `0x18001b320`
- `0x180041518`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18004161a`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18004161a`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180041565`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180041565`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180041586`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800415e9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180041586`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800415e9`
- `api-ms-win-core-threadpool-legacy-l1-1-0!DeleteTimerQueueTimer` at `0x18004157c`
- `api-ms-win-core-threadpool-legacy-l1-1-0!DeleteTimerQueueTimer` at `0x18004157c`
- `api-ms-win-core-threadpool-legacy-l1-1-0!CreateTimerQueueTimer` at `0x1800415df`
- `api-ms-win-core-threadpool-legacy-l1-1-0!CreateTimerQueueTimer` at `0x1800415df`

## string_xrefs

- `0x180041535`: `RequestUpdate,Ignore due to shutdown`
- `0x1800415a4`: `PcaUtilityRequestAppInventoryUpdate`
- `0x1800415fc`: `PcaUtilityRequestAppInventoryUpdate`
- `0x180041593`: `Failed to delete inventory timer [%d]`
- `0x18004154d`: `RequestUpdate,%s`
- `0x1800415ef`: `Failed to create inventory timer [%d]`
- `0x180041546`: `Installer completed`

## pseudocode

```c
__int64 __fastcall PcaUtilityRequestAppInventoryUpdate(struct _PCA_SERVICE *a1, const char *a2)
{
  DWORD v2; // ebx
  DWORD LastError; // eax
  DWORD DueTime[2]; // [rsp+20h] [rbp-28h]
  DWORD DueTimea[2]; // [rsp+20h] [rbp-28h]

  v2 = 0;
  if ( *((_DWORD *)a1 + 1) )
  {
    PcaTracePrintf("Inventory", 0, 0, "RequestUpdate,Ignore due to shutdown");
  }
  else
  {
    PcaTracePrintf("Inventory", 0, 0, "RequestUpdate,%s", "Installer completed");
    EnterCriticalSection(&g_InventoryGlobal);
    if ( Timer )
    {
      if ( !DeleteTimerQueueTimer(0, Timer, 0) )
      {
        LastError = GetLastError();
        if ( LastError != 997 )
        {
          DueTime[0] = LastError;
          AslLogCallPrintf(
            1,
            (unsigned int)"PcaUtilityRequestAppInventoryUpdate",
            1693,
            (unsigned int)"Failed to delete inventory timer [%d]",
            *(_QWORD *)DueTime);
        }
      }
      Timer = 0;
    }
    if ( !CreateTimerQueueTimer(
            &Timer,
            0,
            (WAITORTIMERCALLBACK)PcaUtilityLaunchInventoryUpdateCallback,
            "Installer completed",
            0,
            0,
            8u) )
    {
      DueTimea[0] = GetLastError();
      v2 = DueTimea[0];
      AslLogCallPrintf(
        1,
        (unsigned int)"PcaUtilityRequestAppInventoryUpdate",
        1716,
        (unsigned int)"Failed to create inventory timer [%d]",
        *(_QWORD *)DueTimea);
    }
    LeaveCriticalSection(&g_InventoryGlobal);
  }
  return v2;
}

```

## disassembly

```asm
0x180041518  mov     [rsp+arg_0], rbx
0x18004151d  push    rsi
0x18004151e  sub     rsp, 40h
0x180041522  xor     ebx, ebx
0x180041524  xor     r8d, r8d; unsigned int
0x180041527  xor     edx, edx; unsigned int
0x180041529  cmp     [rcx+4], ebx
0x18004152c  lea     rcx, aInventory_0; "Inventory"
0x180041533  jz      short loc_180041546
0x180041535  lea     r9, aRequestupdateI; "RequestUpdate,Ignore due to shutdown"
0x18004153c  call    ?PcaTracePrintf@@YAXPEBDIK0ZZ; PcaTracePrintf(char const *,uint,ulong,char const *,...)
0x180041541  jmp     loc_180041620
0x180041546  lea     rsi, aInstallerCompl; "Installer completed"
0x18004154d  lea     r9, aRequestupdateS; "RequestUpdate,%s"
0x180041554  mov     qword ptr [rsp+48h+DueTime], rsi
0x180041559  call    ?PcaTracePrintf@@YAXPEBDIK0ZZ; PcaTracePrintf(char const *,uint,ulong,char const *,...)
0x18004155e  lea     rcx, g_InventoryGlobal; lpCriticalSection
0x180041565  call    cs:__imp_EnterCriticalSection
0x18004156b  mov     rdx, cs:Timer; Timer
0x180041572  test    rdx, rdx
0x180041575  jz      short loc_1800415BC
0x180041577  xor     r8d, r8d; CompletionEvent
0x18004157a  xor     ecx, ecx; TimerQueue
0x18004157c  call    cs:__imp_DeleteTimerQueueTimer
0x180041582  test    eax, eax
0x180041584  jnz     short loc_1800415B5
0x180041586  call    cs:__imp_GetLastError
0x18004158c  cmp     eax, 3E5h
0x180041591  jz      short loc_1800415B5
0x180041593  lea     r9, aFailedToDelete_11; "Failed to delete inventory timer [%d]"
0x18004159a  mov     [rsp+48h+DueTime], eax
0x18004159e  mov     r8d, 69Dh
0x1800415a4  lea     rdx, aPcautilityrequ; "PcaUtilityRequestAppInventoryUpdate"
0x1800415ab  mov     ecx, 1
0x1800415b0  call    AslLogCallPrintf
0x1800415b5  mov     cs:Timer, rbx
0x1800415bc  mov     [rsp+48h+Flags], 8; Flags
0x1800415c4  lea     r8, ?PcaUtilityLaunchInventoryUpdateCallback@@YAXPEAXE@Z; Callback
0x1800415cb  mov     [rsp+48h+Period], ebx; Period
0x1800415cf  lea     rcx, Timer; phNewTimer
0x1800415d6  mov     r9, rsi; Parameter
0x1800415d9  mov     [rsp+48h+DueTime], ebx; DueTime
0x1800415dd  xor     edx, edx; TimerQueue
0x1800415df  call    cs:__imp_CreateTimerQueueTimer
0x1800415e5  test    eax, eax
0x1800415e7  jnz     short loc_180041613
0x1800415e9  call    cs:__imp_GetLastError
0x1800415ef  lea     r9, aFailedToCreate_98; "Failed to create inventory timer [%d]"
0x1800415f6  mov     r8d, 6B4h
0x1800415fc  lea     rdx, aPcautilityrequ; "PcaUtilityRequestAppInventoryUpdate"
0x180041603  mov     [rsp+48h+DueTime], eax
0x180041607  mov     ecx, 1
0x18004160c  mov     ebx, eax
0x18004160e  call    AslLogCallPrintf
0x180041613  lea     rcx, g_InventoryGlobal; lpCriticalSection
0x18004161a  call    cs:__imp_LeaveCriticalSection
0x180041620  mov     eax, ebx
0x180041622  mov     rbx, [rsp+48h+arg_0]
0x180041627  add     rsp, 40h
0x18004162b  pop     rsi
0x18004162c  retn
```
