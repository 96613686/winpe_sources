# OperationWatchdog::Start(uint,char const *,ulong,ulong)

- ea: `0x180031f6c`
- end: `0x180032106`
- name: `?Start@OperationWatchdog@@QEAAXIPEBDKK@Z`
- size: `410`
- prototype: `void __fastcall(PVOID pv, unsigned int, const char *, unsigned int, unsigned int)`
- caller_count: `8`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x18001de50`
- `0x180024c00`
- `0x18003723c`
- `0x18006278c`
- `0x180062c5c`
- `0x180062ee0`
- `0x180063320`
- `0x180064b20`

## callees

- `0x18002c574`
- `0x180031f6c`
- `0x18007f9ec`
- `0x18008d9b0`

## import_xrefs

- `msvcrt!memcpy_s` at `0x180031fd3`
- `msvcrt!memcpy_s` at `0x180031fd3`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180032006`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800320bb`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180032006`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800320bb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180031ff3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180032089`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180031ff3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180032089`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180032023`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180032023`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x1800320e1`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x1800320e1`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180031ffe`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180032019`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180031ffe`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180032019`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180031fb8`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180031fb8`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18003209c`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1800320db`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18003209c`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1800320db`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x1800320b3`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x1800320b3`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x1800320aa`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x1800320aa`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x180032077`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x180032077`

## pseudocode

```c
void __fastcall OperationWatchdog::Start(_DWORD *pv, int a2, const char *a3, int a4)
{
  const unsigned __int16 *v4; // rbp
  rsize_t v7; // rdi
  _BYTE *v9; // rax
  _BYTE *v10; // rbx
  void **v11; // r14
  void *v12; // rbp
  DWORD LastError; // edi
  PTP_TIMER ThreadpoolTimer; // rax
  struct _TP_TIMER *v15; // rbp
  struct _TP_TIMER *v16; // rdi
  DWORD v17; // ebx
  char v18; // [rsp+20h] [rbp-58h] BYREF
  struct _FILETIME pftDueTime; // [rsp+28h] [rbp-50h] BYREF

  pv[6] = a4;
  v4 = &byte_18009A505;
  if ( a3 )
    v4 = (const unsigned __int16 *)a3;
  v7 = -1;
  do
    ++v7;
  while ( *((_BYTE *)v4 + v7) );
  v9 = LocalAlloc(0, v7 + 1);
  v10 = v9;
  if ( v9 )
  {
    memcpy_s(v9, v7 + 1, v4, v7);
    v10[v7] = 0;
  }
  v11 = (void **)(pv + 8);
  if ( pv + 8 == (_DWORD *)&v18 )
  {
    if ( v10 )
      LocalFree(v10);
  }
  else
  {
    v12 = *v11;
    if ( *v11 )
    {
      LastError = GetLastError();
      LocalFree(v12);
      SetLastError(LastError);
    }
    *v11 = v10;
  }
  pv[2] = a2;
  pv[10] = GetCurrentThreadId();
  pftDueTime = (struct _FILETIME)-(__int64)(unsigned int)(10000 * a4);
  if ( *((_QWORD *)pv + 2) )
  {
    Log_AssertionEvent_3(
      (unsigned __int64)-(__int64)(unsigned int)(10000 * a4) >> 32,
      "onecoreuap\\internal\\net\\inc\\phone\\OperationWatchdog.h",
      75);
    if ( *((_QWORD *)pv + 2) )
      MicrosoftTelemetryAssertTriggeredNoArgs();
  }
  ThreadpoolTimer = CreateThreadpoolTimer(OperationWatchdog::_WatchdogCallback, pv, 0);
  v15 = (struct _TP_TIMER *)*((_QWORD *)pv + 2);
  v16 = ThreadpoolTimer;
  if ( v15 )
  {
    v17 = GetLastError();
    SetThreadpoolTimer(v15, 0, 0, 0);
    WaitForThreadpoolTimerCallbacks(v15, 1);
    CloseThreadpoolTimer(v15);
    SetLastError(v17);
  }
  *((_QWORD *)pv + 2) = v16;
  if ( v16 )
    SetThreadpoolTimer(v16, &pftDueTime, 0x1388u, 0);
  pv[3] = GetTickCount();
}

```

## disassembly

```asm
0x180031f6c  push    rbx
0x180031f6e  push    rbp
0x180031f6f  push    rsi
0x180031f70  push    rdi
0x180031f71  push    r12
0x180031f73  push    r14
0x180031f75  push    r15
0x180031f77  sub     rsp, 40h
0x180031f7b  mov     rax, cs:__security_cookie
0x180031f82  xor     rax, rsp
0x180031f85  mov     [rsp+78h+var_48], rax
0x180031f8a  test    r8, r8
0x180031f8d  mov     [rcx+18h], r9d
0x180031f91  lea     rbp, byte_18009A505
0x180031f98  mov     r15d, r9d
0x180031f9b  cmovnz  rbp, r8
0x180031f9f  mov     r12d, edx
0x180031fa2  or      rdi, 0FFFFFFFFFFFFFFFFh
0x180031fa6  mov     rsi, rcx
0x180031fa9  inc     rdi
0x180031fac  cmp     byte ptr [rdi+rbp], 0
0x180031fb0  jnz     short loc_180031FA9
0x180031fb2  lea     rdx, [rdi+1]; uBytes
0x180031fb6  xor     ecx, ecx; uFlags
0x180031fb8  call    cs:__imp_LocalAlloc
0x180031fbe  mov     rbx, rax
0x180031fc1  test    rax, rax
0x180031fc4  jz      short loc_180031FDD
0x180031fc6  mov     r9, rdi; SourceSize
0x180031fc9  lea     rdx, [rdi+1]; DestinationSize
0x180031fcd  mov     r8, rbp; Source
0x180031fd0  mov     rcx, rax; Destination
0x180031fd3  call    cs:__imp_memcpy_s
0x180031fd9  mov     byte ptr [rdi+rbx], 0
0x180031fdd  lea     r14, [rsi+20h]
0x180031fe1  lea     rax, [rsp+78h+var_58]
0x180031fe6  cmp     r14, rax
0x180031fe9  jz      short loc_180032011
0x180031feb  mov     rbp, [r14]
0x180031fee  test    rbp, rbp
0x180031ff1  jz      short loc_18003200C
0x180031ff3  call    cs:__imp_GetLastError
0x180031ff9  mov     rcx, rbp; hMem
0x180031ffc  mov     edi, eax
0x180031ffe  call    cs:__imp_LocalFree
0x180032004  mov     ecx, edi; dwErrCode
0x180032006  call    cs:__imp_SetLastError
0x18003200c  mov     [r14], rbx
0x18003200f  jmp     short loc_18003201F
0x180032011  test    rbx, rbx
0x180032014  jz      short loc_18003201F
0x180032016  mov     rcx, rbx; hMem
0x180032019  call    cs:__imp_LocalFree
0x18003201f  mov     [rsi+8], r12d
0x180032023  call    cs:__imp_GetCurrentThreadId
0x180032029  mov     [rsi+28h], eax
0x18003202c  imul    eax, r15d, 2710h
0x180032033  neg     rax
0x180032036  mov     rcx, rax
0x180032039  mov     [rsp+78h+pftDueTime.dwLowDateTime], eax
0x18003203d  shr     rcx, 20h
0x180032041  cmp     qword ptr [rsi+10h], 0
0x180032046  mov     [rsp+78h+pftDueTime.dwHighDateTime], ecx
0x18003204a  jz      short loc_18003206A
0x18003204c  mov     r8d, 4Bh ; 'K'
0x180032052  lea     rdx, aOnecoreuapInte_2; "onecoreuap\\internal\\net\\inc\\phone\\"...
0x180032059  call    Log_AssertionEvent_3
0x18003205e  cmp     qword ptr [rsi+10h], 0
0x180032063  jz      short loc_18003206A
0x180032065  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x18003206a  xor     r8d, r8d; pcbe
0x18003206d  lea     rcx, ?_WatchdogCallback@OperationWatchdog@@CAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z; pfnti
0x180032074  mov     rdx, rsi; pv
0x180032077  call    cs:__imp_CreateThreadpoolTimer
0x18003207d  mov     rbp, [rsi+10h]
0x180032081  mov     rdi, rax
0x180032084  test    rbp, rbp
0x180032087  jz      short loc_1800320C1
0x180032089  call    cs:__imp_GetLastError
0x18003208f  xor     r9d, r9d; msWindowLength
0x180032092  xor     r8d, r8d; msPeriod
0x180032095  xor     edx, edx; pftDueTime
0x180032097  mov     rcx, rbp; pti
0x18003209a  mov     ebx, eax
0x18003209c  call    cs:__imp_SetThreadpoolTimer
0x1800320a2  mov     edx, 1; fCancelPendingCallbacks
0x1800320a7  mov     rcx, rbp; pti
0x1800320aa  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x1800320b0  mov     rcx, rbp; pti
0x1800320b3  call    cs:__imp_CloseThreadpoolTimer
0x1800320b9  mov     ecx, ebx; dwErrCode
0x1800320bb  call    cs:__imp_SetLastError
0x1800320c1  mov     [rsi+10h], rdi
0x1800320c5  test    rdi, rdi
0x1800320c8  jz      short loc_1800320E1
0x1800320ca  xor     r9d, r9d; msWindowLength
0x1800320cd  lea     rdx, [rsp+78h+pftDueTime]; pftDueTime
0x1800320d2  mov     r8d, 1388h; msPeriod
0x1800320d8  mov     rcx, rdi; pti
0x1800320db  call    cs:__imp_SetThreadpoolTimer
0x1800320e1  call    cs:__imp_GetTickCount
0x1800320e7  mov     [rsi+0Ch], eax
0x1800320ea  mov     rcx, [rsp+78h+var_48]
0x1800320ef  xor     rcx, rsp; StackCookie
0x1800320f2  call    __security_check_cookie
0x1800320f7  add     rsp, 40h
0x1800320fb  pop     r15
0x1800320fd  pop     r14
0x1800320ff  pop     r12
0x180032101  pop     rdi
0x180032102  pop     rsi
0x180032103  pop     rbp
0x180032104  pop     rbx
0x180032105  retn
```
