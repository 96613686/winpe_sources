# WaaS2::ComTimeout::SetTimer(ulong)

- ea: `0x180061654`
- end: `0x1800616f7`
- name: `?SetTimer@ComTimeout@WaaS2@@QEAAJK@Z`
- size: `163`
- prototype: `__int64 __fastcall(PVOID pv, unsigned int)`
- caller_count: `1`
- callee_count: `3`
- tags: `installer_update, broker_com_uri`

## callers

- `0x18004e470`

## callees

- `0x18000bbb4`
- `0x18000bbd4`
- `0x180061654`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180061690`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180061690`
- `api-ms-win-core-com-l1-1-0!CoEnableCallCancellation` at `0x180061663`
- `api-ms-win-core-com-l1-1-0!CoEnableCallCancellation` at `0x180061663`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x1800616a6`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x1800616a6`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1800616e4`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1800616e4`

## pseudocode

```c
__int64 __fastcall WaaS2::ComTimeout::SetTimer(_BYTE *pv)
{
  HRESULT v2; // eax
  unsigned int v3; // ebx
  struct _TP_TIMER *ThreadpoolTimer; // rax
  const char *v6; // r9
  int v7; // [rsp+20h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]
  struct _FILETIME pftDueTime; // [rsp+40h] [rbp+18h] BYREF

  v2 = CoEnableCallCancellation(0);
  v3 = v2;
  if ( v2 >= 0 )
  {
    pv[12] = 1;
    *((_DWORD *)pv + 2) = GetCurrentThreadId();
    ThreadpoolTimer = CreateThreadpoolTimer(WaaS2::ComTimeout::s_TimerCallback, pv, 0);
    *(_QWORD *)pv = ThreadpoolTimer;
    if ( ThreadpoolTimer )
    {
      pftDueTime = (struct _FILETIME)-1200000000LL;
      SetThreadpoolTimer(ThreadpoolTimer, &pftDueTime, 0x3E8u, 0);
      return 0;
    }
    else
    {
      return wil::details::in1diag3::Return_GetLastError(
               retaddr,
               (void *)0x4C,
               (unsigned int)"onecore\\internal\\enduser\\inc\\WaaSDeviceFeatureEvaluator2.h",
               v6);
    }
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x47,
      (unsigned int)"onecore\\internal\\enduser\\inc\\WaaSDeviceFeatureEvaluator2.h",
      (const char *)(unsigned int)v2,
      v7);
    return v3;
  }
}

```

## disassembly

```asm
0x180061654  mov     [rsp+arg_0], rbx
0x180061659  push    rdi; int
0x18006165a  sub     rsp, 20h
0x18006165e  mov     rdi, rcx
0x180061661  xor     ecx, ecx; pReserved
0x180061663  call    cs:__imp_CoEnableCallCancellation
0x180061669  mov     ebx, eax
0x18006166b  test    eax, eax
0x18006166d  jns     short loc_18006168C
0x18006166f  mov     rcx, [rsp+28h]; this
0x180061674  lea     r8, aOnecoreInterna_3; "onecore\\internal\\enduser\\inc\\WaaSDe"...
0x18006167b  mov     r9d, eax; char *
0x18006167e  mov     edx, 47h ; 'G'; void *
0x180061683  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180061688  mov     eax, ebx
0x18006168a  jmp     short loc_1800616EC
0x18006168c  mov     byte ptr [rdi+0Ch], 1
0x180061690  call    cs:__imp_GetCurrentThreadId
0x180061696  xor     r8d, r8d; pcbe
0x180061699  lea     rcx, ?s_TimerCallback@ComTimeout@WaaS2@@SAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z; pfnti
0x1800616a0  mov     rdx, rdi; pv
0x1800616a3  mov     [rdi+8], eax
0x1800616a6  call    cs:__imp_CreateThreadpoolTimer
0x1800616ac  mov     [rdi], rax
0x1800616af  test    rax, rax
0x1800616b2  jnz     short loc_1800616CA
0x1800616b4  mov     rcx, [rsp+28h]; this
0x1800616b9  lea     r8, aOnecoreInterna_3; "onecore\\internal\\enduser\\inc\\WaaSDe"...
0x1800616c0  lea     edx, [rax+4Ch]; void *
0x1800616c3  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1800616c8  jmp     short loc_1800616EC
0x1800616ca  xor     r9d, r9d; msWindowLength
0x1800616cd  mov     qword ptr [rsp+28h+pftDueTime.dwLowDateTime], 0FFFFFFFFB8797400h
0x1800616d6  mov     r8d, 3E8h; msPeriod
0x1800616dc  lea     rdx, [rsp+28h+pftDueTime]; pftDueTime
0x1800616e1  mov     rcx, rax; pti
0x1800616e4  call    cs:__imp_SetThreadpoolTimer
0x1800616ea  xor     eax, eax
0x1800616ec  mov     rbx, [rsp+28h+arg_0]
0x1800616f1  add     rsp, 20h
0x1800616f5  pop     rdi
0x1800616f6  retn
```
