# BfeTimerCreate

- ea: `0x18004c92c`
- end: `0x18004caae`
- name: `BfeTimerCreate`
- size: `386`
- prototype: ``
- caller_count: `2`
- callee_count: `10`
- tags: `registry_config`

## callers

- `0x18001e17c`
- `0x18004e89c`

## callees

- `0x18000e7e0`
- `0x180012d8c`
- `0x1800197d0`
- `0x180025fe4`
- `0x180042c30`
- `0x18004c92c`
- `0x180056d6c`
- `0x18005aa60`
- `0x18005c488`
- `0x180060198`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x18004c9c8`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x18004c9c8`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18004ca73`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18004ca73`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004c9ea`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004c9ea`

## string_xrefs

- `0x18004c9f9`: `CreateThreadpoolTimer`
- `0x18004ca3e`: `BfeTimerCreate`

## pseudocode

```c
__int64 __fastcall BfeTimerCreate(__int64 a1, __int64 a2, __int64 a3, unsigned int a4, PTP_TIMER **a5)
{
  __int64 v5; // r14
  int v7; // eax
  __int64 v8; // rcx
  const char *v9; // rdx
  char *v10; // rbx
  PTP_TIMER ThreadpoolTimer; // rax
  __int64 v12; // rcx
  PTP_TIMER *v13; // rdi
  DWORD LastError; // eax
  __int64 v15; // rcx
  __int64 v16; // rax
  __int64 v17; // rbx
  PVOID v19; // [rsp+20h] [rbp-30h] BYREF
  PVOID *p_pv; // [rsp+28h] [rbp-28h] BYREF
  PVOID pv; // [rsp+30h] [rbp-20h] BYREF
  struct _FILETIME pftDueTime; // [rsp+38h] [rbp-18h] BYREF

  v5 = a4;
  v19 = 0;
  pv = 0;
  *a5 = 0;
  p_pv = &pv;
  v7 = wil::ResultFromException__lambda_591e4da8b3c778e804448da3209d0030___(&p_pv);
  if ( v7 >= 0 )
  {
    *(_QWORD *)pv = BfeSaContextTimerCallback;
    *((_QWORD *)pv + 1) = a2;
    *((_DWORD *)pv + 4) = 0;
    v10 = (char *)pv + 24;
    ThreadpoolTimer = CreateThreadpoolTimer(
                        lambda_bbe3fba25f2dd4d7642083cd447b5ef3_::_lambda_invoker_cdecl_,
                        pv,
                        &gBfeTimerCallBackEnvironment);
    wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&public: static void wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::reset(
      v10,
      ThreadpoolTimer);
    v13 = (PTP_TIMER *)pv;
    if ( !*((_QWORD *)pv + 3) )
    {
      LastError = GetLastError();
      v16 = WfpReportSysErrorAsWinError(v15, "CreateThreadpoolTimer", LastError);
      goto LABEL_8;
    }
    v19 = pv;
    v7 = BfeTimerTracking::TransferTimer(v12, &pv);
    if ( v7 >= 0 )
    {
      v17 = 0;
      pftDueTime = (struct _FILETIME)(-10000 * v5);
      SetThreadpoolTimer(v13[3], &pftDueTime, 0, 0);
      *a5 = v13;
      goto LABEL_11;
    }
    v9 = "gBfeTimerTracking.TransferAndSetTimer";
  }
  else
  {
    v9 = "make_shared_BFE_TIMER";
  }
  v16 = WfpReportSysErrorAsHResult(v8, v9, (unsigned int)v7, 1);
LABEL_8:
  v17 = v16;
  if ( v16 )
  {
    WfpMemFree(&v19);
    WfpReportError(v17, "BfeTimerCreate");
  }
LABEL_11:
  std::unique_ptr<BFE_TIMER_>::~unique_ptr<BFE_TIMER_>(&pv);
  return v17;
}

```

## disassembly

```asm
0x18004c92c  mov     [rsp-18h+arg_0], rbx
0x18004c931  mov     [rsp-18h+arg_8], rsi
0x18004c936  push    rbp
0x18004c937  push    rdi
0x18004c938  push    r14
0x18004c93a  mov     rbp, rsp
0x18004c93d  sub     rsp, 50h
0x18004c941  mov     rax, cs:__security_cookie
0x18004c948  xor     rax, rsp
0x18004c94b  mov     [rbp+var_10], rax
0x18004c94f  mov     rsi, [rbp+arg_20]
0x18004c953  lea     rax, [rbp+pv]
0x18004c957  lea     rcx, [rbp+var_28]
0x18004c95b  mov     r14d, r9d
0x18004c95e  mov     rbx, rdx
0x18004c961  mov     [rbp+var_30], 0
0x18004c969  mov     [rbp+pv], 0
0x18004c971  mov     qword ptr [rsi], 0
0x18004c978  mov     [rbp+var_28], rax
0x18004c97c  call    wil__ResultFromException__lambda_591e4da8b3c778e804448da3209d0030___
0x18004c981  test    eax, eax
0x18004c983  jns     short loc_18004C991
0x18004c985  lea     rdx, aMakeSharedBfeT; "make_shared_BFE_TIMER"
0x18004c98c  jmp     loc_18004CA1F
0x18004c991  mov     rax, [rbp+pv]
0x18004c995  lea     rcx, BfeSaContextTimerCallback
0x18004c99c  lea     r8, ?gBfeTimerCallBackEnvironment@@3U_TP_CALLBACK_ENVIRON_V3@@A; pcbe
0x18004c9a3  mov     [rax], rcx
0x18004c9a6  lea     rcx, _lambda_bbe3fba25f2dd4d7642083cd447b5ef3____lambda_invoker_cdecl_; pfnti
0x18004c9ad  mov     rax, [rbp+pv]
0x18004c9b1  mov     [rax+8], rbx
0x18004c9b5  mov     rax, [rbp+pv]
0x18004c9b9  mov     dword ptr [rax+10h], 0
0x18004c9c0  mov     rdx, [rbp+pv]; pv
0x18004c9c4  lea     rbx, [rdx+18h]
0x18004c9c8  call    cs:__imp_CreateThreadpoolTimer
0x18004c9cf  nop     dword ptr [rax+rax+00h]
0x18004c9d4  mov     rdx, rax
0x18004c9d7  mov     rcx, rbx
0x18004c9da  call    ?reset@?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAU_TP_TIMER@@@Z; wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::reset(_TP_TIMER *)
0x18004c9df  mov     rdi, [rbp+pv]
0x18004c9e3  cmp     qword ptr [rdi+18h], 0
0x18004c9e8  jnz     short loc_18004CA07
0x18004c9ea  call    cs:__imp_GetLastError
0x18004c9f1  nop     dword ptr [rax+rax+00h]
0x18004c9f6  mov     r8d, eax
0x18004c9f9  lea     rdx, aCreatethreadpo_0; "CreateThreadpoolTimer"
0x18004ca00  call    WfpReportSysErrorAsWinError
0x18004ca05  jmp     short loc_18004CA2D
0x18004ca07  lea     rdx, [rbp+pv]
0x18004ca0b  mov     [rbp+var_30], rdi
0x18004ca0f  call    ?TransferTimer@BfeTimerTracking@@QEAAJ$$QEAV?$unique_ptr@UBFE_TIMER_@@U?$default_delete@UBFE_TIMER_@@@std@@@std@@@Z; BfeTimerTracking::TransferTimer(std::unique_ptr<BFE_TIMER_> &&)
0x18004ca14  test    eax, eax
0x18004ca16  jns     short loc_18004CA4F
0x18004ca18  lea     rdx, aGbfetimertrack; "gBfeTimerTracking.TransferAndSetTimer"
0x18004ca1f  mov     r9d, 1
0x18004ca25  mov     r8d, eax
0x18004ca28  call    WfpReportSysErrorAsHResult
0x18004ca2d  mov     rbx, rax
0x18004ca30  test    rax, rax
0x18004ca33  jz      short loc_18004CA82
0x18004ca35  lea     rcx, [rbp+var_30]
0x18004ca39  call    WfpMemFree
0x18004ca3e  lea     rdx, aBfetimercreate; "BfeTimerCreate"
0x18004ca45  mov     rcx, rbx
0x18004ca48  call    WfpReportError
0x18004ca4d  jmp     short loc_18004CA82
0x18004ca4f  imul    rax, r14, 0FFFFFFFFFFFFD8F0h
0x18004ca56  xor     ebx, ebx
0x18004ca58  lea     rdx, [rbp+pftDueTime]; pftDueTime
0x18004ca5c  mov     rcx, rax
0x18004ca5f  mov     [rbp+pftDueTime.dwLowDateTime], eax
0x18004ca62  shr     rcx, 20h
0x18004ca66  xor     r9d, r9d; msWindowLength
0x18004ca69  mov     [rbp+pftDueTime.dwHighDateTime], ecx
0x18004ca6c  xor     r8d, r8d; msPeriod
0x18004ca6f  mov     rcx, [rdi+18h]; pti
0x18004ca73  call    cs:__imp_SetThreadpoolTimer
0x18004ca7a  nop     dword ptr [rax+rax+00h]
0x18004ca7f  mov     [rsi], rdi
0x18004ca82  lea     rcx, [rbp+pv]
0x18004ca86  call    ??1?$unique_ptr@UBFE_TIMER_@@U?$default_delete@UBFE_TIMER_@@@std@@@std@@QEAA@XZ; std::unique_ptr<BFE_TIMER_>::~unique_ptr<BFE_TIMER_>(void)
0x18004ca8b  mov     rax, rbx
0x18004ca8e  mov     rcx, [rbp+var_10]
0x18004ca92  xor     rcx, rsp; StackCookie
0x18004ca95  call    __security_check_cookie
0x18004ca9a  mov     rbx, [rsp+50h+arg_0]
0x18004ca9f  mov     rsi, [rsp+50h+arg_8]
0x18004caa4  add     rsp, 50h
0x18004caa8  pop     r14
0x18004caaa  pop     rdi
0x18004caab  pop     rbp
0x18004caac  retn
```
