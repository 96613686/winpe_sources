# WaaS::ComTimeout::MakeComCall<_lambda_17081ffd41afdefee409225a436c3101_>(_lambda_17081ffd41afdefee409225a436c3101_ const &,ulong)

- ea: `0x18003e700`
- end: `0x18003e832`
- name: `??$MakeComCall@V_lambda_17081ffd41afdefee409225a436c3101_@@@ComTimeout@WaaS@@SAJAEBV_lambda_17081ffd41afdefee409225a436c3101_@@K@Z`
- size: `306`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `1`
- callee_count: `4`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0x180050cac`

## callees

- `0x18000bbd4`
- `0x18003e700`
- `0x180061700`
- `0x18006f010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003e7a7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003e7a7`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18003e7ba`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18003e7ba`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003e7b2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003e7b2`
- `api-ms-win-core-com-l1-1-0!CoDisableCallCancellation` at `0x18003e781`
- `api-ms-win-core-com-l1-1-0!CoDisableCallCancellation` at `0x18003e81d`
- `api-ms-win-core-com-l1-1-0!CoDisableCallCancellation` at `0x18003e781`
- `api-ms-win-core-com-l1-1-0!CoDisableCallCancellation` at `0x18003e81d`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18003e773`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18003e80f`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18003e773`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18003e80f`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18003e75a`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18003e7f6`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18003e75a`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18003e7f6`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18003e769`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18003e805`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18003e769`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18003e805`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall WaaS::ComTimeout::MakeComCall<_lambda_17081ffd41afdefee409225a436c3101_>(
        __int64 **a1,
        unsigned int a2)
{
  int v3; // ebx
  __int64 v4; // rdx
  __int64 v6; // r14
  __int64 (__fastcall *v7)(__int64, void **); // r15
  void **v8; // rdi
  void *v9; // rsi
  DWORD LastError; // ebx
  PTP_TIMER pti; // [rsp+20h] [rbp-18h] BYREF
  __int16 v12; // [rsp+2Ch] [rbp-Ch]
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+30h]

  pti = 0;
  v12 = 0;
  v3 = WaaS::ComTimeout::SetTimer(&pti, a2);
  if ( v3 < 0 )
  {
    v4 = 100;
LABEL_3:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v4,
      (unsigned int)"onecore\\internal\\enduser\\inc\\WaaSDeviceFeatureEvaluator.h",
      (const char *)(unsigned int)v3,
      (int)pti);
    if ( pti )
    {
      SetThreadpoolTimer(pti, 0, 0, 0);
      WaitForThreadpoolTimerCallbacks(pti, 1);
      CloseThreadpoolTimer(pti);
    }
    if ( (_BYTE)v12 )
      CoDisableCallCancellation(0);
    return (unsigned int)v3;
  }
  v6 = **a1;
  v7 = *(__int64 (__fastcall **)(__int64, void **))(*(_QWORD *)v6 + 32LL);
  v8 = (void **)a1[1];
  v9 = *v8;
  if ( *v8 )
  {
    LastError = GetLastError();
    CoTaskMemFree(v9);
    SetLastError(LastError);
  }
  *v8 = 0;
  v3 = v7(v6, v8);
  if ( v3 < 0 )
  {
    v4 = 101;
    goto LABEL_3;
  }
  if ( pti )
  {
    SetThreadpoolTimer(pti, 0, 0, 0);
    WaitForThreadpoolTimerCallbacks(pti, 1);
    CloseThreadpoolTimer(pti);
  }
  if ( (_BYTE)v12 )
    CoDisableCallCancellation(0);
  return 0;
}

```

## disassembly

```asm
0x18003e700  push    rbp
0x18003e702  push    rbx
0x18003e703  push    rsi
0x18003e704  push    rdi
0x18003e705  push    r14
0x18003e707  push    r15
0x18003e709  mov     rbp, rsp
0x18003e70c  sub     rsp, 38h
0x18003e710  mov     rdi, rcx
0x18003e713  mov     [rbp+pti], 0
0x18003e71b  mov     [rbp+var_C], 0
0x18003e721  lea     rcx, [rbp+pti]; pv
0x18003e725  call    ?SetTimer@ComTimeout@WaaS@@QEAAJK@Z; WaaS::ComTimeout::SetTimer(ulong)
0x18003e72a  mov     ebx, eax
0x18003e72c  test    eax, eax
0x18003e72e  jns     short loc_18003E78E
0x18003e730  mov     edx, 64h ; 'd'; void *
0x18003e735  mov     r9d, ebx; char *
0x18003e738  lea     r8, aOnecoreInterna_0; "onecore\\internal\\enduser\\inc\\WaaSDe"...
0x18003e73f  mov     rcx, [rbp+30h]; this
0x18003e743  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003e748  nop
0x18003e749  mov     rcx, [rbp+pti]; pti
0x18003e74d  test    rcx, rcx
0x18003e750  jz      short loc_18003E779
0x18003e752  xor     r9d, r9d; msWindowLength
0x18003e755  xor     r8d, r8d; msPeriod
0x18003e758  xor     edx, edx; pftDueTime
0x18003e75a  call    cs:__imp_SetThreadpoolTimer
0x18003e760  mov     edx, 1; fCancelPendingCallbacks
0x18003e765  mov     rcx, [rbp+pti]; pti
0x18003e769  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x18003e76f  mov     rcx, [rbp+pti]; pti
0x18003e773  call    cs:__imp_CloseThreadpoolTimer
0x18003e779  cmp     byte ptr [rbp+var_C], 0
0x18003e77d  jz      short loc_18003E787
0x18003e77f  xor     ecx, ecx; pReserved
0x18003e781  call    cs:__imp_CoDisableCallCancellation
0x18003e787  mov     eax, ebx
0x18003e789  jmp     loc_18003E825
0x18003e78e  mov     rax, [rdi]
0x18003e791  mov     r14, [rax]
0x18003e794  mov     rax, [r14]
0x18003e797  mov     r15, [rax+20h]
0x18003e79b  mov     rdi, [rdi+8]
0x18003e79f  mov     rsi, [rdi]
0x18003e7a2  test    rsi, rsi
0x18003e7a5  jz      short loc_18003E7C0
0x18003e7a7  call    cs:__imp_GetLastError
0x18003e7ad  mov     ebx, eax
0x18003e7af  mov     rcx, rsi; pv
0x18003e7b2  call    cs:__imp_CoTaskMemFree
0x18003e7b8  mov     ecx, ebx; dwErrCode
0x18003e7ba  call    cs:__imp_SetLastError
0x18003e7c0  mov     qword ptr [rdi], 0
0x18003e7c7  mov     rdx, rdi
0x18003e7ca  mov     rcx, r14
0x18003e7cd  mov     rax, r15
0x18003e7d0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003e7d5  mov     ebx, eax
0x18003e7d7  test    eax, eax
0x18003e7d9  jns     short loc_18003E7E5
0x18003e7db  mov     edx, 65h ; 'e'
0x18003e7e0  jmp     loc_18003E735
0x18003e7e5  mov     rcx, [rbp+pti]; pti
0x18003e7e9  test    rcx, rcx
0x18003e7ec  jz      short loc_18003E815
0x18003e7ee  xor     r9d, r9d; msWindowLength
0x18003e7f1  xor     r8d, r8d; msPeriod
0x18003e7f4  xor     edx, edx; pftDueTime
0x18003e7f6  call    cs:__imp_SetThreadpoolTimer
0x18003e7fc  mov     edx, 1; fCancelPendingCallbacks
0x18003e801  mov     rcx, [rbp+pti]; pti
0x18003e805  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x18003e80b  mov     rcx, [rbp+pti]; pti
0x18003e80f  call    cs:__imp_CloseThreadpoolTimer
0x18003e815  cmp     byte ptr [rbp+var_C], 0
0x18003e819  jz      short loc_18003E823
0x18003e81b  xor     ecx, ecx; pReserved
0x18003e81d  call    cs:__imp_CoDisableCallCancellation
0x18003e823  xor     eax, eax
0x18003e825  add     rsp, 38h
0x18003e829  pop     r15
0x18003e82b  pop     r14
0x18003e82d  pop     rdi
0x18003e82e  pop     rsi
0x18003e82f  pop     rbx
0x18003e830  pop     rbp
0x18003e831  retn
```
