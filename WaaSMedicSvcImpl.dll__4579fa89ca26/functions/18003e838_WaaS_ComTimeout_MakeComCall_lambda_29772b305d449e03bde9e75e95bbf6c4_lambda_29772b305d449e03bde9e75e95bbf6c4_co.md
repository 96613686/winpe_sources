# WaaS::ComTimeout::MakeComCall<_lambda_29772b305d449e03bde9e75e95bbf6c4_>(_lambda_29772b305d449e03bde9e75e95bbf6c4_ const &,ulong)

- ea: `0x18003e838`
- end: `0x18003e96a`
- name: `??$MakeComCall@V_lambda_29772b305d449e03bde9e75e95bbf6c4_@@@ComTimeout@WaaS@@SAJAEBV_lambda_29772b305d449e03bde9e75e95bbf6c4_@@K@Z`
- size: `306`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0x180050cac`

## callees

- `0x18000bbd4`
- `0x18003e838`
- `0x180061700`
- `0x18006f010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003e8df`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003e8df`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18003e8f2`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18003e8f2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003e8ea`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003e8ea`
- `api-ms-win-core-com-l1-1-0!CoDisableCallCancellation` at `0x18003e8b9`
- `api-ms-win-core-com-l1-1-0!CoDisableCallCancellation` at `0x18003e955`
- `api-ms-win-core-com-l1-1-0!CoDisableCallCancellation` at `0x18003e8b9`
- `api-ms-win-core-com-l1-1-0!CoDisableCallCancellation` at `0x18003e955`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18003e8ab`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18003e947`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18003e8ab`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18003e947`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18003e892`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18003e92e`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18003e892`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18003e92e`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18003e8a1`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18003e93d`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18003e8a1`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18003e93d`

## pseudocode

```c
__int64 __fastcall WaaS::ComTimeout::MakeComCall<_lambda_29772b305d449e03bde9e75e95bbf6c4_>(
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
  v7 = *(__int64 (__fastcall **)(__int64, void **))(*(_QWORD *)v6 + 40LL);
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
0x18003e838  push    rbp
0x18003e83a  push    rbx
0x18003e83b  push    rsi
0x18003e83c  push    rdi
0x18003e83d  push    r14
0x18003e83f  push    r15
0x18003e841  mov     rbp, rsp
0x18003e844  sub     rsp, 38h
0x18003e848  mov     rdi, rcx
0x18003e84b  mov     [rbp+pti], 0
0x18003e853  mov     [rbp+var_C], 0
0x18003e859  lea     rcx, [rbp+pti]; pv
0x18003e85d  call    ?SetTimer@ComTimeout@WaaS@@QEAAJK@Z; WaaS::ComTimeout::SetTimer(ulong)
0x18003e862  mov     ebx, eax
0x18003e864  test    eax, eax
0x18003e866  jns     short loc_18003E8C6
0x18003e868  mov     edx, 64h ; 'd'; void *
0x18003e86d  mov     r9d, ebx; char *
0x18003e870  lea     r8, aOnecoreInterna_0; "onecore\\internal\\enduser\\inc\\WaaSDe"...
0x18003e877  mov     rcx, [rbp+30h]; this
0x18003e87b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003e880  nop
0x18003e881  mov     rcx, [rbp+pti]; pti
0x18003e885  test    rcx, rcx
0x18003e888  jz      short loc_18003E8B1
0x18003e88a  xor     r9d, r9d; msWindowLength
0x18003e88d  xor     r8d, r8d; msPeriod
0x18003e890  xor     edx, edx; pftDueTime
0x18003e892  call    cs:__imp_SetThreadpoolTimer
0x18003e898  mov     edx, 1; fCancelPendingCallbacks
0x18003e89d  mov     rcx, [rbp+pti]; pti
0x18003e8a1  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x18003e8a7  mov     rcx, [rbp+pti]; pti
0x18003e8ab  call    cs:__imp_CloseThreadpoolTimer
0x18003e8b1  cmp     byte ptr [rbp+var_C], 0
0x18003e8b5  jz      short loc_18003E8BF
0x18003e8b7  xor     ecx, ecx; pReserved
0x18003e8b9  call    cs:__imp_CoDisableCallCancellation
0x18003e8bf  mov     eax, ebx
0x18003e8c1  jmp     loc_18003E95D
0x18003e8c6  mov     rax, [rdi]
0x18003e8c9  mov     r14, [rax]
0x18003e8cc  mov     rax, [r14]
0x18003e8cf  mov     r15, [rax+28h]
0x18003e8d3  mov     rdi, [rdi+8]
0x18003e8d7  mov     rsi, [rdi]
0x18003e8da  test    rsi, rsi
0x18003e8dd  jz      short loc_18003E8F8
0x18003e8df  call    cs:__imp_GetLastError
0x18003e8e5  mov     ebx, eax
0x18003e8e7  mov     rcx, rsi; pv
0x18003e8ea  call    cs:__imp_CoTaskMemFree
0x18003e8f0  mov     ecx, ebx; dwErrCode
0x18003e8f2  call    cs:__imp_SetLastError
0x18003e8f8  mov     qword ptr [rdi], 0
0x18003e8ff  mov     rdx, rdi
0x18003e902  mov     rcx, r14
0x18003e905  mov     rax, r15
0x18003e908  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003e90d  mov     ebx, eax
0x18003e90f  test    eax, eax
0x18003e911  jns     short loc_18003E91D
0x18003e913  mov     edx, 65h ; 'e'
0x18003e918  jmp     loc_18003E86D
0x18003e91d  mov     rcx, [rbp+pti]; pti
0x18003e921  test    rcx, rcx
0x18003e924  jz      short loc_18003E94D
0x18003e926  xor     r9d, r9d; msWindowLength
0x18003e929  xor     r8d, r8d; msPeriod
0x18003e92c  xor     edx, edx; pftDueTime
0x18003e92e  call    cs:__imp_SetThreadpoolTimer
0x18003e934  mov     edx, 1; fCancelPendingCallbacks
0x18003e939  mov     rcx, [rbp+pti]; pti
0x18003e93d  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x18003e943  mov     rcx, [rbp+pti]; pti
0x18003e947  call    cs:__imp_CloseThreadpoolTimer
0x18003e94d  cmp     byte ptr [rbp+var_C], 0
0x18003e951  jz      short loc_18003E95B
0x18003e953  xor     ecx, ecx; pReserved
0x18003e955  call    cs:__imp_CoDisableCallCancellation
0x18003e95b  xor     eax, eax
0x18003e95d  add     rsp, 38h
0x18003e961  pop     r15
0x18003e963  pop     r14
0x18003e965  pop     rdi
0x18003e966  pop     rsi
0x18003e967  pop     rbx
0x18003e968  pop     rbp
0x18003e969  retn
```
