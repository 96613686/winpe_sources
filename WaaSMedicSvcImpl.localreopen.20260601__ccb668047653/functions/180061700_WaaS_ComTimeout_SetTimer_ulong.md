# WaaS::ComTimeout::SetTimer(ulong)

- ea: `0x180061700`
- end: `0x18006177b`
- name: `?SetTimer@ComTimeout@WaaS@@QEAAJK@Z`
- size: `123`
- prototype: `__int64 __fastcall(PVOID pv, unsigned int)`
- caller_count: `3`
- callee_count: `2`
- tags: `installer_update, broker_com_uri`

## callers

- `0x18003e700`
- `0x18003e838`
- `0x18003e970`

## callees

- `0x18000bbb4`
- `0x180061700`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180061719`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180061719`
- `api-ms-win-core-com-l1-1-0!CoEnableCallCancellation` at `0x18006170b`
- `api-ms-win-core-com-l1-1-0!CoEnableCallCancellation` at `0x18006170b`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x18006172f`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x18006172f`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18006176d`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18006176d`

## pseudocode

```c
__int64 __fastcall WaaS::ComTimeout::SetTimer(_BYTE *pv)
{
  struct _TP_TIMER *ThreadpoolTimer; // rax
  const char *v3; // r9
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]
  struct _FILETIME pftDueTime; // [rsp+40h] [rbp+18h] BYREF

  if ( CoEnableCallCancellation(0) >= 0 )
  {
    pv[12] = 1;
    *((_DWORD *)pv + 2) = GetCurrentThreadId();
    ThreadpoolTimer = CreateThreadpoolTimer(WaaS::ComTimeout::s_TimerCallback, pv, 0);
    *(_QWORD *)pv = ThreadpoolTimer;
    if ( !ThreadpoolTimer )
      return wil::details::in1diag3::Return_GetLastError(
               retaddr,
               (void *)0x3B,
               (unsigned int)"onecore\\internal\\enduser\\inc\\WaaSDeviceFeatureEvaluator.h",
               v3);
    pftDueTime = (struct _FILETIME)-1200000000LL;
    SetThreadpoolTimer(ThreadpoolTimer, &pftDueTime, 0x3E8u, 0);
  }
  return 0;
}

```

## disassembly

```asm
0x180061700  push    rbx
0x180061702  sub     rsp, 20h
0x180061706  mov     rbx, rcx
0x180061709  xor     ecx, ecx; pReserved
0x18006170b  call    cs:__imp_CoEnableCallCancellation
0x180061711  test    eax, eax
0x180061713  js      short loc_180061773
0x180061715  mov     byte ptr [rbx+0Ch], 1
0x180061719  call    cs:__imp_GetCurrentThreadId
0x18006171f  xor     r8d, r8d; pcbe
0x180061722  lea     rcx, ?s_TimerCallback@ComTimeout@WaaS@@SAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z; pfnti
0x180061729  mov     rdx, rbx; pv
0x18006172c  mov     [rbx+8], eax
0x18006172f  call    cs:__imp_CreateThreadpoolTimer
0x180061735  mov     [rbx], rax
0x180061738  test    rax, rax
0x18006173b  jnz     short loc_180061753
0x18006173d  mov     rcx, [rsp+28h]; this
0x180061742  lea     r8, aOnecoreInterna_0; "onecore\\internal\\enduser\\inc\\WaaSDe"...
0x180061749  lea     edx, [rax+3Bh]; void *
0x18006174c  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180061751  jmp     short loc_180061775
0x180061753  xor     r9d, r9d; msWindowLength
0x180061756  mov     qword ptr [rsp+28h+pftDueTime.dwLowDateTime], 0FFFFFFFFB8797400h
0x18006175f  mov     r8d, 3E8h; msPeriod
0x180061765  lea     rdx, [rsp+28h+pftDueTime]; pftDueTime
0x18006176a  mov     rcx, rax; pti
0x18006176d  call    cs:__imp_SetThreadpoolTimer
0x180061773  xor     eax, eax
0x180061775  add     rsp, 20h
0x180061779  pop     rbx
0x18006177a  retn
```
