# SharedSocket::CreateCleanupTimer(ulong)

- ea: `0x1800142d4`
- end: `0x18001439a`
- name: `?CreateCleanupTimer@SharedSocket@@IEAAKK@Z`
- size: `198`
- prototype: `__int64 __fastcall(struct _RTL_CRITICAL_SECTION *pv)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180013f04`

## callees

- `0x18000a0a0`
- `0x1800142d4`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180014378`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180014378`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800142f1`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800142f1`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180014360`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180014360`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180014324`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180014324`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x18001430d`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x18001430d`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180014356`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180014356`

## string_xrefs

- `0x18001438c`: `SharedSocket: CreateThreadpoolTimer failed with`

## pseudocode

```c
__int64 __fastcall SharedSocket::CreateCleanupTimer(struct _RTL_CRITICAL_SECTION *pv)
{
  DWORD v2; // edi
  PTP_TIMER ThreadpoolTimer; // rax
  struct _TP_TIMER *DebugInfo; // rcx
  __int64 v5; // rax
  DWORD LastError; // eax
  __int64 v8; // rdx
  __int64 v9; // rcx
  struct _FILETIME SystemTimeAsFileTime; // [rsp+30h] [rbp+8h] BYREF

  v2 = 0;
  SystemTimeAsFileTime = 0;
  EnterCriticalSection(pv + 1);
  if ( pv[5].DebugInfo
    || (ThreadpoolTimer = CreateThreadpoolTimer((PTP_TIMER_CALLBACK)SharedSocket::CleanupTimerCallback, pv, 0),
        (pv[5].DebugInfo = (PRTL_CRITICAL_SECTION_DEBUG)ThreadpoolTimer) != 0) )
  {
    GetSystemTimeAsFileTime(&SystemTimeAsFileTime);
    DebugInfo = (struct _TP_TIMER *)pv[5].DebugInfo;
    v5 = *(_QWORD *)&SystemTimeAsFileTime + 600000000LL;
    SystemTimeAsFileTime.dwLowDateTime += 600000000;
    SystemTimeAsFileTime.dwHighDateTime = HIDWORD(v5);
    SetThreadpoolTimer(DebugInfo, &SystemTimeAsFileTime, 0, 0x960u);
  }
  else
  {
    LastError = GetLastError();
    v2 = LastError;
    if ( (Microsoft_Windows_Network_Connection_BrokerEnableBits & 1) != 0 )
      McTemplateU0zq_EventWriteTransfer(v9, v8, L"SharedSocket: CreateThreadpoolTimer failed with", LastError);
  }
  LeaveCriticalSection(pv + 1);
  return v2;
}

```

## disassembly

```asm
0x1800142d4  mov     [rsp+arg_8], rbx
0x1800142d9  mov     [rsp+arg_10], rsi
0x1800142de  push    rdi
0x1800142df  sub     rsp, 20h
0x1800142e3  mov     rbx, rcx
0x1800142e6  xor     edi, edi
0x1800142e8  add     rcx, 28h ; '('; lpCriticalSection
0x1800142ec  mov     qword ptr [rsp+28h+SystemTimeAsFileTime.dwLowDateTime], rdi
0x1800142f1  call    cs:__imp_EnterCriticalSection
0x1800142f7  cmp     [rbx+0C8h], rdi
0x1800142fe  jnz     short loc_18001431F
0x180014300  xor     r8d, r8d; pcbe
0x180014303  lea     rcx, ?CleanupTimerCallback@SharedSocket@@CAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z; pfnti
0x18001430a  mov     rdx, rbx; pv
0x18001430d  call    cs:__imp_CreateThreadpoolTimer
0x180014313  mov     [rbx+0C8h], rax
0x18001431a  test    rax, rax
0x18001431d  jz      short loc_180014378
0x18001431f  lea     rcx, [rsp+28h+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x180014324  call    cs:__imp_GetSystemTimeAsFileTime
0x18001432a  mov     rax, qword ptr [rsp+28h+SystemTimeAsFileTime.dwLowDateTime]
0x18001432f  lea     rdx, [rsp+28h+SystemTimeAsFileTime]; pftDueTime
0x180014334  mov     rcx, [rbx+0C8h]; pti
0x18001433b  add     rax, 23C34600h
0x180014341  mov     [rsp+28h+SystemTimeAsFileTime.dwLowDateTime], eax
0x180014345  mov     r9d, 960h; msWindowLength
0x18001434b  shr     rax, 20h
0x18001434f  xor     r8d, r8d; msPeriod
0x180014352  mov     [rsp+28h+SystemTimeAsFileTime.dwHighDateTime], eax
0x180014356  call    cs:__imp_SetThreadpoolTimer
0x18001435c  lea     rcx, [rbx+28h]; lpCriticalSection
0x180014360  call    cs:__imp_LeaveCriticalSection
0x180014366  mov     rbx, [rsp+28h+arg_8]
0x18001436b  mov     eax, edi
0x18001436d  mov     rsi, [rsp+28h+arg_10]
0x180014372  add     rsp, 20h
0x180014376  pop     rdi
0x180014377  retn
0x180014378  call    cs:__imp_GetLastError
0x18001437e  test    byte ptr cs:Microsoft_Windows_Network_Connection_BrokerEnableBits, 1
0x180014385  mov     edi, eax
0x180014387  jz      short loc_18001435C
0x180014389  mov     r9d, eax
0x18001438c  lea     r8, aSharedsocketCr_2; "SharedSocket: CreateThreadpoolTimer fai"...
0x180014393  call    McTemplateU0zq_EventWriteTransfer
0x180014398  jmp     short loc_18001435C
```
