# pplx::task<unsigned __int64>::_ThenImpl<unsigned __int64,_lambda_9ae1b6b611071959ad7ff25d21dd2ecc_>(_lambda_9ae1b6b611071959ad7ff25d21dd2ecc_ const &,pplx::details::_CancellationTokenState *,pplx::task_continuation_context const &,pplx::scheduler_ptr,pplx::details::_TaskCreationCallstack,pplx::details::_TaskInliningMode)

- ea: `0x180019474`
- end: `0x180019628`
- name: `??$_ThenImpl@_KV_lambda_9ae1b6b611071959ad7ff25d21dd2ecc_@@@?$task@_K@pplx@@AEBA?AV?$task@Vvalue@json@web@@@1@AEBV_lambda_9ae1b6b611071959ad7ff25d21dd2ecc_@@PEAV_CancellationTokenState@details@1@AEBVtask_continuation_context@1@Uscheduler_ptr@1@V_TaskCreationCallstack@51@W4_TaskInliningMode@51@@Z`
- size: `436`
- prototype: `_QWORD *__fastcall(pplx::details::_Task_impl_base **, _QWORD *, __int64, __int64, __int64, _QWORD *, __int64)`
- caller_count: `1`
- callee_count: `11`
- tags: `registry_config, service_task`

## callers

- `0x180019268`

## callees

- `0x180004fa0`
- `0x18000529c`
- `0x180005e9c`
- `0x18000fa74`
- `0x1800100d8`
- `0x180012034`
- `0x1800148ac`
- `0x180015508`
- `0x1800157f4`
- `0x180019474`
- `0x18001cea4`

## string_xrefs

- `0x1800194c5`: `then() cannot be called on a default constructed task.`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
_QWORD *__fastcall pplx::task<unsigned __int64>::_ThenImpl<unsigned __int64,_lambda_9ae1b6b611071959ad7ff25d21dd2ecc_>(
        pplx::details::_Task_impl_base **a1,
        _QWORD *a2,
        __int64 a3,
        __int64 a4,
        __int64 a5,
        _QWORD *a6,
        __int64 a7)
{
  __int64 v10; // r9
  __int64 v11; // rcx
  __int64 *v12; // rcx
  pplx::details::_Task_impl_base *v13; // rbx
  _QWORD *v14; // r9
  __int64 v15; // r9
  __int64 v16; // r9
  std::_Ref_count_base *v17; // rcx
  _QWORD *v19; // [rsp+28h] [rbp-71h]
  _QWORD v20[6]; // [rsp+30h] [rbp-69h] BYREF
  _BYTE pExceptionObject[56]; // [rsp+60h] [rbp-39h] BYREF

  v20[3] = a2;
  v20[4] = a6;
  v20[5] = a7;
  if ( !*a1 )
  {
    pplx::invalid_operation::invalid_operation(
      (pplx::invalid_operation *)pExceptionObject,
      "then() cannot be called on a default constructed task.");
    throw (pplx::invalid_operation *)pExceptionObject;
  }
  *a2 = 0;
  a2[1] = 0;
  std::shared_ptr<pplx::details::_Task_impl_base>::shared_ptr<pplx::details::_Task_impl_base>(v20, a6);
  v20[2] = a6[2];
  pplx::task<web::json::value>::_CreateImpl(a2, v10, v20);
  *(_BYTE *)(*a2 + 12LL) = *((_BYTE *)*a1 + 12) != 0;
  *(_BYTE *)(*a2 + 13LL) = 0;
  v11 = *a2;
  *(_QWORD *)(v11 + 152) = *(_QWORD *)a7;
  v12 = (__int64 *)(v11 + 160);
  if ( v12 != (__int64 *)(a7 + 8) )
    std::vector<void *>::_Assign_counted_range<void * *>(
      v12,
      *(char **)(a7 + 8),
      (__int64)(*(_QWORD *)(a7 + 16) - *(_QWORD *)(a7 + 8)) >> 3);
  v13 = *a1;
  v19 = operator new(0x50u);
  v19[1] = 0;
  *((_BYTE *)v19 + 17) = 0;
  *((_DWORD *)v19 + 5) = 0;
  *v19 = &pplx::details::_PPLTaskHandle<web::json::value,pplx::task<unsigned __int64>::_ContinuationTaskHandle<unsigned __int64,web::json::value,_lambda_9ae1b6b611071959ad7ff25d21dd2ecc_,std::integral_constant<bool,0>,pplx::details::_TypeSelectorNoAsync>,pplx::details::_ContinuationTaskHandleBase>::`vftable';
  std::shared_ptr<pplx::details::_Task_impl_base>::shared_ptr<pplx::details::_Task_impl_base>(v19 + 3, a2);
  *v14 = &pplx::task<unsigned __int64>::_ContinuationTaskHandle<unsigned __int64,web::json::value,_lambda_9ae1b6b611071959ad7ff25d21dd2ecc_,std::integral_constant<bool,0>,pplx::details::_TypeSelectorNoAsync>::`vftable';
  std::shared_ptr<pplx::details::_Task_impl_base>::shared_ptr<pplx::details::_Task_impl_base>(v14 + 5, a1);
  std::shared_ptr<pplx::details::_Task_impl_base>::shared_ptr<pplx::details::_Task_impl_base>(
    (_QWORD *)(v15 + 56),
    (_QWORD *)a3);
  *(_BYTE *)(v16 + 72) = *(_BYTE *)(a3 + 16);
  *(_BYTE *)(v16 + 17) = 0;
  *(_DWORD *)(v16 + 20) = 0;
  pplx::details::_Task_impl_base::_ScheduleContinuation(v13, (struct pplx::details::_ContinuationTaskHandleBase *)v16);
  v17 = (std::_Ref_count_base *)a6[1];
  if ( v17 )
    std::_Ref_count_base::_Decref(v17);
  std::vector<void *>::_Tidy(a7 + 8);
  return a2;
}

```

## disassembly

```asm
0x180019474  push    rbp
0x180019476  push    rbx
0x180019477  push    rsi
0x180019478  push    rdi
0x180019479  push    r13
0x18001947b  push    r14
0x18001947d  push    r15
0x18001947f  lea     rbp, [rsp-7]
0x180019484  sub     rsp, 0A0h
0x18001948b  mov     rax, cs:__security_cookie
0x180019492  xor     rax, rsp
0x180019495  mov     [rbp+37h+var_38], rax
0x180019499  mov     r13, r8
0x18001949c  mov     rdi, rdx
0x18001949f  mov     r15, rcx
0x1800194a2  mov     [rbp+37h+var_88], rdx
0x1800194a6  mov     r14, [rbp+37h+arg_28]
0x1800194aa  mov     [rbp+37h+var_80], r14
0x1800194ae  mov     rsi, [rbp+37h+arg_30]
0x1800194b2  mov     [rbp+37h+var_78], rsi
0x1800194b6  mov     [rbp+37h+var_B0], 0
0x1800194bd  mov     rax, [rcx]
0x1800194c0  test    rax, rax
0x1800194c3  jnz     short loc_1800194E6
0x1800194c5  lea     rdx, aThenCannotBeCa; "then() cannot be called on a default co"...
0x1800194cc  lea     rcx, [rbp+37h+pExceptionObject]; this
0x1800194d0  call    ??0invalid_operation@pplx@@QEAA@PEBD@Z; pplx::invalid_operation::invalid_operation(char const *)
0x1800194d5  lea     rdx, _TI2?AVinvalid_operation@pplx@@; pThrowInfo
0x1800194dc  lea     rcx, [rbp+37h+pExceptionObject]; pExceptionObject
0x1800194e0  call    _CxxThrowException_0
0x1800194e6  test    r9, r9
0x1800194e9  jnz     short loc_1800194EF
0x1800194eb  mov     r9, [rax+60h]
0x1800194ef  mov     qword ptr [rdx], 0
0x1800194f6  mov     qword ptr [rdx+8], 0
0x1800194fe  mov     [rbp+37h+var_B0], 1
0x180019505  mov     rdx, r14
0x180019508  lea     rcx, [rbp+37h+var_A0]
0x18001950c  call    ??$?0U?$_Task_impl@UOnlineServiceResponse@BingOnlineServices@@@details@pplx@@$0A@@?$shared_ptr@U_Task_impl_base@details@pplx@@@std@@QEAA@AEBV?$shared_ptr@U?$_Task_impl@UOnlineServiceResponse@BingOnlineServices@@@details@pplx@@@1@@Z; std::shared_ptr<pplx::details::_Task_impl_base>::shared_ptr<pplx::details::_Task_impl_base>(std::shared_ptr<pplx::details::_Task_impl<BingOnlineServices::OnlineServiceResponse>> const &)
0x180019511  mov     rcx, [r14+10h]
0x180019515  mov     [rbp+37h+var_90], rcx
0x180019519  lea     r8, [rbp+37h+var_A0]
0x18001951d  mov     rdx, r9
0x180019520  mov     rcx, rdi
0x180019523  call    ?_CreateImpl@?$task@Vvalue@json@web@@@pplx@@QEAAXPEAV_CancellationTokenState@details@2@Uscheduler_ptr@2@@Z; pplx::task<web::json::value>::_CreateImpl(pplx::details::_CancellationTokenState *,pplx::scheduler_ptr)
0x180019528  mov     rax, [r15]
0x18001952b  cmp     byte ptr [rax+0Ch], 0
0x18001952f  setnz   cl
0x180019532  mov     rax, [rdi]
0x180019535  mov     [rax+0Ch], cl
0x180019538  mov     rax, [rdi]
0x18001953b  mov     byte ptr [rax+0Dh], 0
0x18001953f  mov     rcx, [rdi]
0x180019542  mov     rax, [rsi]
0x180019545  mov     [rcx+98h], rax
0x18001954c  add     rsi, 8
0x180019550  add     rcx, 0A0h
0x180019557  cmp     rcx, rsi
0x18001955a  jz      short loc_18001956F
0x18001955c  mov     r8, [rsi+8]
0x180019560  sub     r8, [rsi]
0x180019563  sar     r8, 3
0x180019567  mov     rdx, [rsi]
0x18001956a  call    ??$_Assign_counted_range@PEAPEAX@?$vector@PEAXV?$allocator@PEAX@std@@@std@@AEAAXPEAPEAX_K@Z; std::vector<void *>::_Assign_counted_range<void * *>(void * *,unsigned __int64)
0x18001956f  mov     rbx, [r15]
0x180019572  mov     ecx, 50h ; 'P'; Size
0x180019577  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18001957c  mov     r9, rax
0x18001957f  mov     [rbp+37h+var_A8], rax
0x180019583  mov     qword ptr [rax+8], 0
0x18001958b  mov     byte ptr [rax+11h], 0
0x18001958f  mov     dword ptr [rax+14h], 0
0x180019596  lea     rax, ??_7?$_PPLTaskHandle@Vvalue@json@web@@U?$_ContinuationTaskHandle@_KVvalue@json@web@@V_lambda_9ae1b6b611071959ad7ff25d21dd2ecc_@@U?$integral_constant@_N$0A@@std@@U_TypeSelectorNoAsync@details@pplx@@@?$task@_K@pplx@@U_ContinuationTaskHandleBase@details@6@@details@pplx@@6B@; const pplx::details::_PPLTaskHandle<web::json::value,pplx::task<unsigned __int64>::_ContinuationTaskHandle<unsigned __int64,web::json::value,_lambda_9ae1b6b611071959ad7ff25d21dd2ecc_,std::integral_constant<bool,0>,pplx::details::_TypeSelectorNoAsync>,pplx::details::_ContinuationTaskHandleBase>::`vftable'
0x18001959d  mov     [r9], rax
0x1800195a0  lea     rcx, [r9+18h]
0x1800195a4  mov     rdx, rdi
0x1800195a7  call    ??$?0U?$_Task_impl@UOnlineServiceResponse@BingOnlineServices@@@details@pplx@@$0A@@?$shared_ptr@U_Task_impl_base@details@pplx@@@std@@QEAA@AEBV?$shared_ptr@U?$_Task_impl@UOnlineServiceResponse@BingOnlineServices@@@details@pplx@@@1@@Z; std::shared_ptr<pplx::details::_Task_impl_base>::shared_ptr<pplx::details::_Task_impl_base>(std::shared_ptr<pplx::details::_Task_impl<BingOnlineServices::OnlineServiceResponse>> const &)
0x1800195ac  lea     rcx, ??_7?$_ContinuationTaskHandle@_KVvalue@json@web@@V_lambda_9ae1b6b611071959ad7ff25d21dd2ecc_@@U?$integral_constant@_N$0A@@std@@U_TypeSelectorNoAsync@details@pplx@@@?$task@_K@pplx@@6B@; const pplx::task<unsigned __int64>::_ContinuationTaskHandle<unsigned __int64,web::json::value,_lambda_9ae1b6b611071959ad7ff25d21dd2ecc_,std::integral_constant<bool,0>,pplx::details::_TypeSelectorNoAsync>::`vftable'
0x1800195b3  mov     [r9], rcx
0x1800195b6  lea     rcx, [r9+28h]
0x1800195ba  mov     rdx, r15
0x1800195bd  call    ??$?0U?$_Task_impl@UOnlineServiceResponse@BingOnlineServices@@@details@pplx@@$0A@@?$shared_ptr@U_Task_impl_base@details@pplx@@@std@@QEAA@AEBV?$shared_ptr@U?$_Task_impl@UOnlineServiceResponse@BingOnlineServices@@@details@pplx@@@1@@Z; std::shared_ptr<pplx::details::_Task_impl_base>::shared_ptr<pplx::details::_Task_impl_base>(std::shared_ptr<pplx::details::_Task_impl<BingOnlineServices::OnlineServiceResponse>> const &)
0x1800195c2  mov     rdx, r13
0x1800195c5  lea     rcx, [r9+38h]
0x1800195c9  call    ??$?0U?$_Task_impl@UOnlineServiceResponse@BingOnlineServices@@@details@pplx@@$0A@@?$shared_ptr@U_Task_impl_base@details@pplx@@@std@@QEAA@AEBV?$shared_ptr@U?$_Task_impl@UOnlineServiceResponse@BingOnlineServices@@@details@pplx@@@1@@Z; std::shared_ptr<pplx::details::_Task_impl_base>::shared_ptr<pplx::details::_Task_impl_base>(std::shared_ptr<pplx::details::_Task_impl<BingOnlineServices::OnlineServiceResponse>> const &)
0x1800195ce  mov     cl, [r13+10h]
0x1800195d2  mov     [r9+48h], cl
0x1800195d6  mov     byte ptr [r9+11h], 0
0x1800195db  mov     dword ptr [r9+14h], 0
0x1800195e3  mov     rdx, r9; struct pplx::details::_ContinuationTaskHandleBase *
0x1800195e6  mov     rcx, rbx; this
0x1800195e9  call    ?_ScheduleContinuation@_Task_impl_base@details@pplx@@QEAAXPEAU_ContinuationTaskHandleBase@23@@Z; pplx::details::_Task_impl_base::_ScheduleContinuation(pplx::details::_ContinuationTaskHandleBase *)
0x1800195ee  nop
0x1800195ef  mov     rcx, [r14+8]; this
0x1800195f3  test    rcx, rcx
0x1800195f6  jz      short loc_1800195FE
0x1800195f8  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x1800195fd  nop
0x1800195fe  mov     rcx, rsi
0x180019601  call    ?_Tidy@?$vector@PEAXV?$allocator@PEAX@std@@@std@@AEAAXXZ; std::vector<void *>::_Tidy(void)
0x180019606  mov     rax, rdi
0x180019609  mov     rcx, [rbp+37h+var_38]
0x18001960d  xor     rcx, rsp; StackCookie
0x180019610  call    __security_check_cookie
0x180019615  add     rsp, 0A0h
0x18001961c  pop     r15
0x18001961e  pop     r14
0x180019620  pop     r13
0x180019622  pop     rdi
0x180019623  pop     rsi
0x180019624  pop     rbx
0x180019625  pop     rbp
0x180019626  retn
```
