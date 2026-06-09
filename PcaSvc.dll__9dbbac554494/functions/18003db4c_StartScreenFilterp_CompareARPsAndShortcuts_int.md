# StartScreenFilterp_CompareARPsAndShortcuts(int)

- ea: `0x18003db4c`
- end: `0x18003dc42`
- name: `?StartScreenFilterp_CompareARPsAndShortcuts@@YAKH@Z`
- size: `246`
- prototype: `unsigned int __fastcall(int)`
- caller_count: `3`
- callee_count: `2`
- tags: `file_ops, broker_com_uri`

## callers

- `0x180039500`
- `0x1800b2b00`
- `0x1800b2c60`

## callees

- `0x180012920`
- `0x18003db4c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18003dc34`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18003dc34`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18003db5b`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18003db5b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003db82`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003dbff`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003db82`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003dbff`
- `api-ms-win-core-threadpool-legacy-l1-1-0!DeleteTimerQueueTimer` at `0x18003db78`
- `api-ms-win-core-threadpool-legacy-l1-1-0!DeleteTimerQueueTimer` at `0x18003db78`
- `api-ms-win-core-threadpool-legacy-l1-1-0!CreateTimerQueueTimer` at `0x18003dbf5`
- `api-ms-win-core-threadpool-legacy-l1-1-0!CreateTimerQueueTimer` at `0x18003dbf5`

## string_xrefs

- `0x18003dc05`: `Failed to create start screen timer [%d]`
- `0x18003dba0`: `StartScreenFilterp_CompareARPsAndShortcuts`
- `0x18003dc12`: `StartScreenFilterp_CompareARPsAndShortcuts`
- `0x18003db8f`: `Failed to delete start screen timer [%d]`

## pseudocode

```c
__int64 __fastcall StartScreenFilterp_CompareARPsAndShortcuts(int a1)
{
  DWORD LastError; // eax
  unsigned int v3; // ebx
  DWORD DueTimea; // [rsp+20h] [rbp-28h]
  __int64 DueTime; // [rsp+20h] [rbp-28h]

  EnterCriticalSection(&g_StartScreenFilterState);
  dword_18015C6DC = a1;
  if ( phNewTimer )
  {
    if ( !DeleteTimerQueueTimer(0, phNewTimer, 0) )
    {
      LastError = GetLastError();
      if ( LastError != 997 )
      {
        DueTimea = LastError;
        AslLogCallPrintf(
          1,
          (unsigned int)"StartScreenFilterp_CompareARPsAndShortcuts",
          428,
          (unsigned int)"Failed to delete start screen timer [%d]",
          DueTimea);
      }
    }
    phNewTimer = 0;
  }
  if ( CreateTimerQueueTimer(
         &phNewTimer,
         0,
         (WAITORTIMERCALLBACK)StartScreenFilterp_ComparerCallback,
         &dword_18015C6DC,
         a1 != 0 ? 1 : 10000,
         0,
         8u) )
  {
    v3 = 0;
  }
  else
  {
    LODWORD(DueTime) = GetLastError();
    v3 = DueTime;
    AslLogCallPrintf(
      1,
      (unsigned int)"StartScreenFilterp_CompareARPsAndShortcuts",
      447,
      (unsigned int)"Failed to create start screen timer [%d]",
      DueTime);
  }
  LeaveCriticalSection(&g_StartScreenFilterState);
  return v3;
}

```

## disassembly

```asm
0x18003db4c  push    rbx
0x18003db4e  sub     rsp, 40h
0x18003db52  mov     ebx, ecx
0x18003db54  lea     rcx, ?g_StartScreenFilterState@@3U_PCA_STARTSCREEN_FILTER_GLOBAL@@A; lpCriticalSection
0x18003db5b  call    cs:__imp_EnterCriticalSection
0x18003db61  mov     rdx, cs:phNewTimer; Timer
0x18003db68  mov     cs:dword_18015C6DC, ebx
0x18003db6e  test    rdx, rdx
0x18003db71  jz      short loc_18003DBBC
0x18003db73  xor     r8d, r8d; CompletionEvent
0x18003db76  xor     ecx, ecx; TimerQueue
0x18003db78  call    cs:__imp_DeleteTimerQueueTimer
0x18003db7e  test    eax, eax
0x18003db80  jnz     short loc_18003DBB1
0x18003db82  call    cs:__imp_GetLastError
0x18003db88  cmp     eax, 3E5h
0x18003db8d  jz      short loc_18003DBB1
0x18003db8f  lea     r9, aFailedToDelete_2; "Failed to delete start screen timer [%d"...
0x18003db96  mov     dword ptr [rsp+48h+DueTime], eax
0x18003db9a  mov     r8d, 1ACh
0x18003dba0  lea     rdx, aStartscreenfil_7; "StartScreenFilterp_CompareARPsAndShortc"...
0x18003dba7  mov     ecx, 1
0x18003dbac  call    AslLogCallPrintf
0x18003dbb1  mov     cs:phNewTimer, 0
0x18003dbbc  mov     [rsp+48h+Flags], 8; Flags
0x18003dbc4  lea     r9, dword_18015C6DC; Parameter
0x18003dbcb  neg     ebx
0x18003dbcd  mov     [rsp+48h+Period], 0; Period
0x18003dbd5  lea     r8, ?StartScreenFilterp_ComparerCallback@@YAXPEAXE@Z; Callback
0x18003dbdc  sbb     eax, eax
0x18003dbde  lea     rcx, phNewTimer; phNewTimer
0x18003dbe5  and     eax, 0FFFFD8F1h
0x18003dbea  xor     edx, edx; TimerQueue
0x18003dbec  add     eax, 2710h
0x18003dbf1  mov     dword ptr [rsp+48h+DueTime], eax; DueTime
0x18003dbf5  call    cs:__imp_CreateTimerQueueTimer
0x18003dbfb  test    eax, eax
0x18003dbfd  jnz     short loc_18003DC2B
0x18003dbff  call    cs:__imp_GetLastError
0x18003dc05  lea     r9, aFailedToCreate_78; "Failed to create start screen timer [%d"...
0x18003dc0c  mov     r8d, 1BFh
0x18003dc12  lea     rdx, aStartscreenfil_7; "StartScreenFilterp_CompareARPsAndShortc"...
0x18003dc19  mov     dword ptr [rsp+48h+DueTime], eax
0x18003dc1d  mov     ecx, 1
0x18003dc22  mov     ebx, eax
0x18003dc24  call    AslLogCallPrintf
0x18003dc29  jmp     short loc_18003DC2D
0x18003dc2b  xor     ebx, ebx
0x18003dc2d  lea     rcx, ?g_StartScreenFilterState@@3U_PCA_STARTSCREEN_FILTER_GLOBAL@@A; lpCriticalSection
0x18003dc34  call    cs:__imp_LeaveCriticalSection
0x18003dc3a  mov     eax, ebx
0x18003dc3c  add     rsp, 40h
0x18003dc40  pop     rbx
0x18003dc41  retn
```
