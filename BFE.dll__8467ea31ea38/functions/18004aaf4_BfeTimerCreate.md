# BfeTimerCreate

- ea: `0x18004aaf4`
- end: `0x18004ac93`
- name: `BfeTimerCreate`
- size: `415`
- prototype: ``
- caller_count: `2`
- callee_count: `11`
- tags: `registry_config`

## callers

- `0x1800280e0`
- `0x18004cdbc`

## callees

- `0x18000e000`
- `0x18001236c`
- `0x180018b74`
- `0x1800238b4`
- `0x180041950`
- `0x1800439cc`
- `0x18004aaf4`
- `0x180054ecc`
- `0x180058b30`
- `0x18005a598`
- `0x18005a5fc`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x18004ab93`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x18004ab93`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18004ac5d`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18004ac5d`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18004abd4`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18004abd4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004abaf`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004abaf`

## string_xrefs

- `0x18004abb8`: `CreateThreadpoolTimer`
- `0x18004ac28`: `BfeTimerCreate`

## pseudocode

```c
__int64 __fastcall BfeTimerCreate(__int64 a1, __int64 a2, __int64 a3, unsigned int a4, PTP_TIMER **a5)
{
  __int64 v5; // r14
  int v7; // eax
  __int64 v8; // rcx
  __int64 v9; // r8
  const char *v10; // rdx
  struct _TP_TIMER **v11; // rbx
  struct _TP_TIMER *ThreadpoolTimer; // rax
  PTP_TIMER *v13; // rdi
  DWORD LastError; // eax
  __int64 v15; // rcx
  __int64 v16; // rax
  int v17; // ebx
  __int64 v18; // rbx
  RTL_SRWLOCK *p_pv; // [rsp+20h] [rbp-40h] BYREF
  PVOID v21; // [rsp+28h] [rbp-38h] BYREF
  _QWORD v22[2]; // [rsp+30h] [rbp-30h] BYREF
  PVOID pv; // [rsp+40h] [rbp-20h] BYREF
  struct _FILETIME pftDueTime; // [rsp+48h] [rbp-18h] BYREF

  v5 = a4;
  v21 = 0;
  pv = 0;
  *a5 = 0;
  p_pv = (RTL_SRWLOCK *)&pv;
  v7 = wil::ResultFromException__lambda_591e4da8b3c778e804448da3209d0030___(&p_pv);
  if ( v7 >= 0 )
  {
    *(_QWORD *)pv = BfeSaContextTimerCallback;
    *((_QWORD *)pv + 1) = a2;
    *((_DWORD *)pv + 4) = 0;
    v11 = (struct _TP_TIMER **)((char *)pv + 24);
    ThreadpoolTimer = CreateThreadpoolTimer(
                        (PTP_TIMER_CALLBACK)lambda_bbe3fba25f2dd4d7642083cd447b5ef3_::_lambda_invoker_cdecl_,
                        pv,
                        &gBfeTimerCallBackEnvironment);
    wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&public: static void wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::reset(
      v11,
      ThreadpoolTimer);
    v13 = (PTP_TIMER *)pv;
    if ( !*((_QWORD *)pv + 3) )
    {
      LastError = GetLastError();
      v16 = WfpReportSysErrorAsWinError(v15, "CreateThreadpoolTimer", LastError);
      goto LABEL_8;
    }
    v21 = pv;
    AcquireSRWLockExclusive(&gBfeTimerTracking);
    p_pv = &gBfeTimerTracking;
    v22[1] = &pv;
    v22[0] = &gBfeTimerTracking;
    v17 = wil::ResultFromException<_lambda_ea1b0df01b10eb15c77a50466ae49842_>(v22);
    wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(&p_pv);
    if ( v17 >= 0 )
    {
      v18 = 0;
      pftDueTime = (struct _FILETIME)(-10000 * v5);
      SetThreadpoolTimer(v13[3], &pftDueTime, 0, 0);
      *a5 = v13;
      goto LABEL_11;
    }
    v9 = (unsigned int)v17;
    v10 = "gBfeTimerTracking.TransferAndSetTimer";
  }
  else
  {
    v9 = (unsigned int)v7;
    v10 = "make_shared_BFE_TIMER";
  }
  v16 = WfpReportSysErrorAsHResult(v8, v10, v9, 1);
LABEL_8:
  v18 = v16;
  if ( v16 )
  {
    WfpMemFree(&v21);
    WfpReportError(v18, "BfeTimerCreate");
  }
LABEL_11:
  std::unique_ptr<BFE_TIMER_>::~unique_ptr<BFE_TIMER_>(&pv);
  return v18;
}

```

## disassembly

```asm
0x18004aaf4  mov     [rsp-18h+arg_0], rbx
0x18004aaf9  mov     [rsp-18h+arg_8], rsi
0x18004aafe  push    rbp
0x18004aaff  push    rdi
0x18004ab00  push    r14
0x18004ab02  mov     rbp, rsp
0x18004ab05  sub     rsp, 60h
0x18004ab09  mov     rax, cs:__security_cookie
0x18004ab10  xor     rax, rsp
0x18004ab13  mov     [rbp+var_10], rax
0x18004ab17  mov     rsi, [rbp+arg_20]
0x18004ab1b  lea     rax, [rbp+pv]
0x18004ab1f  lea     rcx, [rbp+var_40]
0x18004ab23  mov     r14d, r9d
0x18004ab26  mov     rbx, rdx
0x18004ab29  mov     [rbp+var_38], 0
0x18004ab31  mov     [rbp+pv], 0
0x18004ab39  mov     qword ptr [rsi], 0
0x18004ab40  mov     [rbp+var_40], rax
0x18004ab44  call    wil__ResultFromException__lambda_591e4da8b3c778e804448da3209d0030___
0x18004ab49  test    eax, eax
0x18004ab4b  jns     short loc_18004AB5C
0x18004ab4d  mov     r8d, eax
0x18004ab50  lea     rdx, aMakeSharedBfeT; "make_shared_BFE_TIMER"
0x18004ab57  jmp     loc_18004AC0C
0x18004ab5c  mov     rax, [rbp+pv]
0x18004ab60  lea     rcx, BfeSaContextTimerCallback
0x18004ab67  lea     r8, ?gBfeTimerCallBackEnvironment@@3U_TP_CALLBACK_ENVIRON_V3@@A; pcbe
0x18004ab6e  mov     [rax], rcx
0x18004ab71  lea     rcx, _lambda_bbe3fba25f2dd4d7642083cd447b5ef3____lambda_invoker_cdecl_; pfnti
0x18004ab78  mov     rax, [rbp+pv]
0x18004ab7c  mov     [rax+8], rbx
0x18004ab80  mov     rax, [rbp+pv]
0x18004ab84  mov     dword ptr [rax+10h], 0
0x18004ab8b  mov     rdx, [rbp+pv]; pv
0x18004ab8f  lea     rbx, [rdx+18h]
0x18004ab93  call    cs:__imp_CreateThreadpoolTimer
0x18004ab99  mov     rdx, rax
0x18004ab9c  mov     rcx, rbx
0x18004ab9f  call    ?reset@?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAU_TP_TIMER@@@Z; wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::reset(_TP_TIMER *)
0x18004aba4  mov     rdi, [rbp+pv]
0x18004aba8  cmp     qword ptr [rdi+18h], 0
0x18004abad  jnz     short loc_18004ABC6
0x18004abaf  call    cs:__imp_GetLastError
0x18004abb5  mov     r8d, eax
0x18004abb8  lea     rdx, aCreatethreadpo_0; "CreateThreadpoolTimer"
0x18004abbf  call    WfpReportSysErrorAsWinError
0x18004abc4  jmp     short loc_18004AC17
0x18004abc6  lea     rbx, ?gBfeTimerTracking@@3VBfeTimerTracking@@A; BfeTimerTracking gBfeTimerTracking
0x18004abcd  mov     [rbp+var_38], rdi
0x18004abd1  mov     rcx, rbx; SRWLock
0x18004abd4  call    cs:__imp_AcquireSRWLockExclusive
0x18004abda  lea     rax, [rbp+pv]
0x18004abde  mov     [rbp+var_40], rbx
0x18004abe2  lea     rcx, [rbp+var_30]
0x18004abe6  mov     [rbp+var_28], rax
0x18004abea  mov     [rbp+var_30], rbx
0x18004abee  call    ??$ResultFromException@V_lambda_ea1b0df01b10eb15c77a50466ae49842_@@@wil@@YAJ$$QEAV_lambda_ea1b0df01b10eb15c77a50466ae49842_@@@Z; wil::ResultFromException<_lambda_ea1b0df01b10eb15c77a50466ae49842_>(_lambda_ea1b0df01b10eb15c77a50466ae49842_ &&)
0x18004abf3  lea     rcx, [rbp+var_40]
0x18004abf7  mov     ebx, eax
0x18004abf9  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x18004abfe  test    ebx, ebx
0x18004ac00  jns     short loc_18004AC39
0x18004ac02  mov     r8d, ebx
0x18004ac05  lea     rdx, aGbfetimertrack; "gBfeTimerTracking.TransferAndSetTimer"
0x18004ac0c  mov     r9d, 1
0x18004ac12  call    WfpReportSysErrorAsHResult
0x18004ac17  mov     rbx, rax
0x18004ac1a  test    rax, rax
0x18004ac1d  jz      short loc_18004AC66
0x18004ac1f  lea     rcx, [rbp+var_38]
0x18004ac23  call    WfpMemFree
0x18004ac28  lea     rdx, aBfetimercreate; "BfeTimerCreate"
0x18004ac2f  mov     rcx, rbx
0x18004ac32  call    WfpReportError
0x18004ac37  jmp     short loc_18004AC66
0x18004ac39  imul    rax, r14, 0FFFFFFFFFFFFD8F0h
0x18004ac40  xor     ebx, ebx
0x18004ac42  lea     rdx, [rbp+pftDueTime]; pftDueTime
0x18004ac46  mov     rcx, rax
0x18004ac49  mov     [rbp+pftDueTime.dwLowDateTime], eax
0x18004ac4c  shr     rcx, 20h
0x18004ac50  xor     r9d, r9d; msWindowLength
0x18004ac53  mov     [rbp+pftDueTime.dwHighDateTime], ecx
0x18004ac56  xor     r8d, r8d; msPeriod
0x18004ac59  mov     rcx, [rdi+18h]; pti
0x18004ac5d  call    cs:__imp_SetThreadpoolTimer
0x18004ac63  mov     [rsi], rdi
0x18004ac66  lea     rcx, [rbp+pv]
0x18004ac6a  call    ??1?$unique_ptr@UBFE_TIMER_@@U?$default_delete@UBFE_TIMER_@@@std@@@std@@QEAA@XZ; std::unique_ptr<BFE_TIMER_>::~unique_ptr<BFE_TIMER_>(void)
0x18004ac6f  mov     rax, rbx
0x18004ac72  mov     rcx, [rbp+var_10]
0x18004ac76  xor     rcx, rsp; StackCookie
0x18004ac79  call    __security_check_cookie
0x18004ac7e  lea     r11, [rsp+60h+var_s0]
0x18004ac83  mov     rbx, [r11+20h]
0x18004ac87  mov     rsi, [r11+28h]
0x18004ac8b  mov     rsp, r11
0x18004ac8e  pop     r14
0x18004ac90  pop     rdi
0x18004ac91  pop     rbp
0x18004ac92  retn
```
