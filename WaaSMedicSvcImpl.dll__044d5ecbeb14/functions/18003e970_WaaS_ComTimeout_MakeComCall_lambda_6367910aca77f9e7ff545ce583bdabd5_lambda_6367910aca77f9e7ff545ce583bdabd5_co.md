# WaaS::ComTimeout::MakeComCall<_lambda_6367910aca77f9e7ff545ce583bdabd5_>(_lambda_6367910aca77f9e7ff545ce583bdabd5_ const &,ulong)

- ea: `0x18003e970`
- end: `0x18003eaa2`
- name: `??$MakeComCall@V_lambda_6367910aca77f9e7ff545ce583bdabd5_@@@ComTimeout@WaaS@@SAJAEBV_lambda_6367910aca77f9e7ff545ce583bdabd5_@@K@Z`
- size: `306`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `1`
- callee_count: `4`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0x180050cac`

## callees

- `0x18000bbd4`
- `0x18003e970`
- `0x180061700`
- `0x18006f010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003ea17`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003ea17`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18003ea2a`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18003ea2a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003ea22`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003ea22`
- `api-ms-win-core-com-l1-1-0!CoDisableCallCancellation` at `0x18003e9f1`
- `api-ms-win-core-com-l1-1-0!CoDisableCallCancellation` at `0x18003ea8d`
- `api-ms-win-core-com-l1-1-0!CoDisableCallCancellation` at `0x18003e9f1`
- `api-ms-win-core-com-l1-1-0!CoDisableCallCancellation` at `0x18003ea8d`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18003e9e3`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18003ea7f`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18003e9e3`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18003ea7f`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18003e9ca`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18003ea66`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18003e9ca`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18003ea66`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18003e9d9`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18003ea75`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18003e9d9`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18003ea75`

## pseudocode

```c
__int64 __fastcall WaaS::ComTimeout::MakeComCall<_lambda_6367910aca77f9e7ff545ce583bdabd5_>(
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
  v7 = *(__int64 (__fastcall **)(__int64, void **))(*(_QWORD *)v6 + 24LL);
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
0x18003e970  push    rbp
0x18003e972  push    rbx
0x18003e973  push    rsi
0x18003e974  push    rdi
0x18003e975  push    r14
0x18003e977  push    r15
0x18003e979  mov     rbp, rsp
0x18003e97c  sub     rsp, 38h
0x18003e980  mov     rdi, rcx
0x18003e983  mov     [rbp+pti], 0
0x18003e98b  mov     [rbp+var_C], 0
0x18003e991  lea     rcx, [rbp+pti]; pv
0x18003e995  call    ?SetTimer@ComTimeout@WaaS@@QEAAJK@Z; WaaS::ComTimeout::SetTimer(ulong)
0x18003e99a  mov     ebx, eax
0x18003e99c  test    eax, eax
0x18003e99e  jns     short loc_18003E9FE
0x18003e9a0  mov     edx, 64h ; 'd'; void *
0x18003e9a5  mov     r9d, ebx; char *
0x18003e9a8  lea     r8, aOnecoreInterna_0; "onecore\\internal\\enduser\\inc\\WaaSDe"...
0x18003e9af  mov     rcx, [rbp+30h]; this
0x18003e9b3  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003e9b8  nop
0x18003e9b9  mov     rcx, [rbp+pti]; pti
0x18003e9bd  test    rcx, rcx
0x18003e9c0  jz      short loc_18003E9E9
0x18003e9c2  xor     r9d, r9d; msWindowLength
0x18003e9c5  xor     r8d, r8d; msPeriod
0x18003e9c8  xor     edx, edx; pftDueTime
0x18003e9ca  call    cs:__imp_SetThreadpoolTimer
0x18003e9d0  mov     edx, 1; fCancelPendingCallbacks
0x18003e9d5  mov     rcx, [rbp+pti]; pti
0x18003e9d9  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x18003e9df  mov     rcx, [rbp+pti]; pti
0x18003e9e3  call    cs:__imp_CloseThreadpoolTimer
0x18003e9e9  cmp     byte ptr [rbp+var_C], 0
0x18003e9ed  jz      short loc_18003E9F7
0x18003e9ef  xor     ecx, ecx; pReserved
0x18003e9f1  call    cs:__imp_CoDisableCallCancellation
0x18003e9f7  mov     eax, ebx
0x18003e9f9  jmp     loc_18003EA95
0x18003e9fe  mov     rax, [rdi]
0x18003ea01  mov     r14, [rax]
0x18003ea04  mov     rax, [r14]
0x18003ea07  mov     r15, [rax+18h]
0x18003ea0b  mov     rdi, [rdi+8]
0x18003ea0f  mov     rsi, [rdi]
0x18003ea12  test    rsi, rsi
0x18003ea15  jz      short loc_18003EA30
0x18003ea17  call    cs:__imp_GetLastError
0x18003ea1d  mov     ebx, eax
0x18003ea1f  mov     rcx, rsi; pv
0x18003ea22  call    cs:__imp_CoTaskMemFree
0x18003ea28  mov     ecx, ebx; dwErrCode
0x18003ea2a  call    cs:__imp_SetLastError
0x18003ea30  mov     qword ptr [rdi], 0
0x18003ea37  mov     rdx, rdi
0x18003ea3a  mov     rcx, r14
0x18003ea3d  mov     rax, r15
0x18003ea40  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003ea45  mov     ebx, eax
0x18003ea47  test    eax, eax
0x18003ea49  jns     short loc_18003EA55
0x18003ea4b  mov     edx, 65h ; 'e'
0x18003ea50  jmp     loc_18003E9A5
0x18003ea55  mov     rcx, [rbp+pti]; pti
0x18003ea59  test    rcx, rcx
0x18003ea5c  jz      short loc_18003EA85
0x18003ea5e  xor     r9d, r9d; msWindowLength
0x18003ea61  xor     r8d, r8d; msPeriod
0x18003ea64  xor     edx, edx; pftDueTime
0x18003ea66  call    cs:__imp_SetThreadpoolTimer
0x18003ea6c  mov     edx, 1; fCancelPendingCallbacks
0x18003ea71  mov     rcx, [rbp+pti]; pti
0x18003ea75  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x18003ea7b  mov     rcx, [rbp+pti]; pti
0x18003ea7f  call    cs:__imp_CloseThreadpoolTimer
0x18003ea85  cmp     byte ptr [rbp+var_C], 0
0x18003ea89  jz      short loc_18003EA93
0x18003ea8b  xor     ecx, ecx; pReserved
0x18003ea8d  call    cs:__imp_CoDisableCallCancellation
0x18003ea93  xor     eax, eax
0x18003ea95  add     rsp, 38h
0x18003ea99  pop     r15
0x18003ea9b  pop     r14
0x18003ea9d  pop     rdi
0x18003ea9e  pop     rsi
0x18003ea9f  pop     rbx
0x18003eaa0  pop     rbp
0x18003eaa1  retn
```
