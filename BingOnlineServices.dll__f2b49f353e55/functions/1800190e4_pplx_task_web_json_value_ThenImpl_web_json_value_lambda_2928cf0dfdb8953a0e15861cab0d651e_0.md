# pplx::task_web::json::value_::_ThenImpl_web::json::value__lambda_2928cf0dfdb8953a0e15861cab0d651e____0

- ea: `0x1800190e4`
- end: `0x180019260`
- name: `pplx::task_web::json::value_::_ThenImpl_web::json::value__lambda_2928cf0dfdb8953a0e15861cab0d651e____0`
- size: `380`
- prototype: ``
- caller_count: `1`
- callee_count: `12`
- tags: `registry_config, service_task`

## callers

- `0x180018ed8`

## callees

- `0x180004fa0`
- `0x18000529c`
- `0x180005e9c`
- `0x18000fa74`
- `0x180011c10`
- `0x180012034`
- `0x1800148ac`
- `0x180015508`
- `0x1800156d4`
- `0x1800157f4`
- `0x1800190e4`
- `0x18001cdac`

## string_xrefs

- `0x180019136`: `then() cannot be called on a default constructed task.`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
_QWORD *__fastcall pplx::task_web::json::value_::_ThenImpl_web::json::value__lambda_2928cf0dfdb8953a0e15861cab0d651e____0(
        pplx::details::_Task_impl_base **a1,
        _QWORD *a2,
        const struct BingOnlineServices::OnlineServiceResponse *a3,
        __int64 a4,
        __int64 a5,
        _QWORD *a6,
        __int64 a7)
{
  __int64 v10; // r9
  pplx::details::_Task_impl_base *v11; // rdi
  std::_Ref_count_base *v12; // rcx
  _QWORD *v14; // [rsp+28h] [rbp-79h]
  _QWORD v15[6]; // [rsp+30h] [rbp-71h] BYREF
  _BYTE pExceptionObject[56]; // [rsp+60h] [rbp-41h] BYREF

  v15[3] = a2;
  v15[4] = a6;
  v15[5] = a7;
  if ( !*a1 )
  {
    pplx::invalid_operation::invalid_operation(
      (pplx::invalid_operation *)pExceptionObject,
      "then() cannot be called on a default constructed task.");
    throw (pplx::invalid_operation *)pExceptionObject;
  }
  *a2 = 0;
  a2[1] = 0;
  std::shared_ptr<pplx::details::_Task_impl_base>::shared_ptr<pplx::details::_Task_impl_base>(v15, a6);
  v15[2] = a6[2];
  pplx::task<BingOnlineServices::OnlineServiceResponse>::_CreateImpl(a2, v10, v15);
  *(_BYTE *)(*a2 + 12LL) = *((_BYTE *)*a1 + 12) != 0;
  *(_BYTE *)(*a2 + 13LL) = 1;
  pplx::task<BingOnlineServices::OnlineServiceResponse>::_SetTaskCreationCallstack(a2, a7);
  v11 = *a1;
  v14 = operator new(0xC0u);
  v14[1] = 0;
  *((_BYTE *)v14 + 17) = 0;
  *((_DWORD *)v14 + 5) = 0;
  *v14 = &pplx::details::_PPLTaskHandle<BingOnlineServices::OnlineServiceResponse,pplx::task<web::json::value>::_ContinuationTaskHandle<web::json::value,BingOnlineServices::OnlineServiceResponse,_lambda_2928cf0dfdb8953a0e15861cab0d651e_,std::integral_constant<bool,0>,pplx::details::_TypeSelectorAsyncTask>,pplx::details::_ContinuationTaskHandleBase>::`vftable';
  std::shared_ptr<pplx::details::_Task_impl_base>::shared_ptr<pplx::details::_Task_impl_base>(v14 + 3, a2);
  *v14 = &pplx::task<web::json::value>::_ContinuationTaskHandle<web::json::value,BingOnlineServices::OnlineServiceResponse,_lambda_2928cf0dfdb8953a0e15861cab0d651e_,std::integral_constant<bool,0>,pplx::details::_TypeSelectorAsyncTask>::`vftable';
  std::shared_ptr<pplx::details::_Task_impl_base>::shared_ptr<pplx::details::_Task_impl_base>(v14 + 5, a1);
  BingOnlineServices::OnlineServiceResponse::OnlineServiceResponse(
    (BingOnlineServices::OnlineServiceResponse *)(v14 + 7),
    a3);
  *((_BYTE *)v14 + 17) = 0;
  *((_DWORD *)v14 + 5) = 0;
  pplx::details::_Task_impl_base::_ScheduleContinuation(v11, (struct pplx::details::_ContinuationTaskHandleBase *)v14);
  v12 = (std::_Ref_count_base *)a6[1];
  if ( v12 )
    std::_Ref_count_base::_Decref(v12);
  std::vector<void *>::_Tidy(a7 + 8);
  return a2;
}

```

## disassembly

```asm
0x1800190e4  push    rbp
0x1800190e6  push    rbx
0x1800190e7  push    rsi
0x1800190e8  push    rdi
0x1800190e9  push    r12
0x1800190eb  push    r13
0x1800190ed  push    r14
0x1800190ef  push    r15
0x1800190f1  lea     rbp, [rsp-7]
0x1800190f6  sub     rsp, 0A8h
0x1800190fd  mov     rax, cs:__security_cookie
0x180019104  xor     rax, rsp
0x180019107  mov     [rbp+3Fh+var_48], rax
0x18001910b  mov     r12, r8
0x18001910e  mov     rsi, rdx
0x180019111  mov     r15, rcx
0x180019114  mov     [rbp+3Fh+var_98], rdx
0x180019118  mov     r13, [rbp+3Fh+arg_28]
0x18001911c  mov     [rbp+3Fh+var_90], r13
0x180019120  mov     r14, [rbp+3Fh+arg_30]
0x180019124  mov     [rbp+3Fh+var_88], r14
0x180019128  xor     ebx, ebx
0x18001912a  mov     [rsp+0E0h+var_C0], ebx
0x18001912e  mov     rax, [rcx]
0x180019131  test    rax, rax
0x180019134  jnz     short loc_180019157
0x180019136  lea     rdx, aThenCannotBeCa; "then() cannot be called on a default co"...
0x18001913d  lea     rcx, [rbp+3Fh+pExceptionObject]; this
0x180019141  call    ??0invalid_operation@pplx@@QEAA@PEBD@Z; pplx::invalid_operation::invalid_operation(char const *)
0x180019146  lea     rdx, _TI2?AVinvalid_operation@pplx@@; pThrowInfo
0x18001914d  lea     rcx, [rbp+3Fh+pExceptionObject]; pExceptionObject
0x180019151  call    _CxxThrowException_0
0x180019157  test    r9, r9
0x18001915a  jnz     short loc_180019160
0x18001915c  mov     r9, [rax+60h]
0x180019160  mov     [rdx], rbx
0x180019163  mov     [rdx+8], rbx
0x180019167  mov     [rsp+0E0h+var_C0], 1
0x18001916f  mov     rdx, r13
0x180019172  lea     rcx, [rbp+3Fh+var_B0]
0x180019176  call    ??$?0U?$_Task_impl@UOnlineServiceResponse@BingOnlineServices@@@details@pplx@@$0A@@?$shared_ptr@U_Task_impl_base@details@pplx@@@std@@QEAA@AEBV?$shared_ptr@U?$_Task_impl@UOnlineServiceResponse@BingOnlineServices@@@details@pplx@@@1@@Z; std::shared_ptr<pplx::details::_Task_impl_base>::shared_ptr<pplx::details::_Task_impl_base>(std::shared_ptr<pplx::details::_Task_impl<BingOnlineServices::OnlineServiceResponse>> const &)
0x18001917b  mov     rcx, [r13+10h]
0x18001917f  mov     [rbp+3Fh+var_A0], rcx
0x180019183  lea     r8, [rbp+3Fh+var_B0]
0x180019187  mov     rdx, r9
0x18001918a  mov     rcx, rsi
0x18001918d  call    ?_CreateImpl@?$task@UOnlineServiceResponse@BingOnlineServices@@@pplx@@QEAAXPEAV_CancellationTokenState@details@2@Uscheduler_ptr@2@@Z; pplx::task<BingOnlineServices::OnlineServiceResponse>::_CreateImpl(pplx::details::_CancellationTokenState *,pplx::scheduler_ptr)
0x180019192  mov     rax, [r15]
0x180019195  cmp     [rax+0Ch], bl
0x180019198  setnz   cl
0x18001919b  mov     rax, [rsi]
0x18001919e  mov     [rax+0Ch], cl
0x1800191a1  mov     rax, [rsi]
0x1800191a4  mov     byte ptr [rax+0Dh], 1
0x1800191a8  mov     rdx, r14
0x1800191ab  mov     rcx, rsi
0x1800191ae  call    ?_SetTaskCreationCallstack@?$task@UOnlineServiceResponse@BingOnlineServices@@@pplx@@QEAAXAEBV_TaskCreationCallstack@details@2@@Z; pplx::task<BingOnlineServices::OnlineServiceResponse>::_SetTaskCreationCallstack(pplx::details::_TaskCreationCallstack const &)
0x1800191b3  mov     rdi, [r15]
0x1800191b6  mov     ecx, 0C0h; Size
0x1800191bb  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800191c0  mov     rbx, rax
0x1800191c3  mov     [rbp+3Fh+var_B8], rax
0x1800191c7  xor     eax, eax
0x1800191c9  mov     [rbx+8], rax
0x1800191cd  mov     [rbx+11h], al
0x1800191d0  mov     [rbx+14h], eax
0x1800191d3  lea     rax, ??_7?$_PPLTaskHandle@UOnlineServiceResponse@BingOnlineServices@@U?$_ContinuationTaskHandle@Vvalue@json@web@@UOnlineServiceResponse@BingOnlineServices@@V_lambda_2928cf0dfdb8953a0e15861cab0d651e_@@U?$integral_constant@_N$0A@@std@@U_TypeSelectorAsyncTask@details@pplx@@@?$task@Vvalue@json@web@@@pplx@@U_ContinuationTaskHandleBase@details@5@@details@pplx@@6B@; const pplx::details::_PPLTaskHandle<BingOnlineServices::OnlineServiceResponse,pplx::task<web::json::value>::_ContinuationTaskHandle<web::json::value,BingOnlineServices::OnlineServiceResponse,_lambda_2928cf0dfdb8953a0e15861cab0d651e_,std::integral_constant<bool,0>,pplx::details::_TypeSelectorAsyncTask>,pplx::details::_ContinuationTaskHandleBase>::`vftable'
0x1800191da  mov     [rbx], rax
0x1800191dd  lea     rcx, [rbx+18h]
0x1800191e1  mov     rdx, rsi
0x1800191e4  call    ??$?0U?$_Task_impl@UOnlineServiceResponse@BingOnlineServices@@@details@pplx@@$0A@@?$shared_ptr@U_Task_impl_base@details@pplx@@@std@@QEAA@AEBV?$shared_ptr@U?$_Task_impl@UOnlineServiceResponse@BingOnlineServices@@@details@pplx@@@1@@Z; std::shared_ptr<pplx::details::_Task_impl_base>::shared_ptr<pplx::details::_Task_impl_base>(std::shared_ptr<pplx::details::_Task_impl<BingOnlineServices::OnlineServiceResponse>> const &)
0x1800191e9  nop
0x1800191ea  lea     rax, ??_7?$_ContinuationTaskHandle@Vvalue@json@web@@UOnlineServiceResponse@BingOnlineServices@@V_lambda_2928cf0dfdb8953a0e15861cab0d651e_@@U?$integral_constant@_N$0A@@std@@U_TypeSelectorAsyncTask@details@pplx@@@?$task@Vvalue@json@web@@@pplx@@6B@; const pplx::task<web::json::value>::_ContinuationTaskHandle<web::json::value,BingOnlineServices::OnlineServiceResponse,_lambda_2928cf0dfdb8953a0e15861cab0d651e_,std::integral_constant<bool,0>,pplx::details::_TypeSelectorAsyncTask>::`vftable'
0x1800191f1  mov     [rbx], rax
0x1800191f4  lea     rcx, [rbx+28h]
0x1800191f8  mov     rdx, r15
0x1800191fb  call    ??$?0U?$_Task_impl@UOnlineServiceResponse@BingOnlineServices@@@details@pplx@@$0A@@?$shared_ptr@U_Task_impl_base@details@pplx@@@std@@QEAA@AEBV?$shared_ptr@U?$_Task_impl@UOnlineServiceResponse@BingOnlineServices@@@details@pplx@@@1@@Z; std::shared_ptr<pplx::details::_Task_impl_base>::shared_ptr<pplx::details::_Task_impl_base>(std::shared_ptr<pplx::details::_Task_impl<BingOnlineServices::OnlineServiceResponse>> const &)
0x180019200  nop
0x180019201  lea     rcx, [rbx+38h]; this
0x180019205  mov     rdx, r12; struct BingOnlineServices::OnlineServiceResponse *
0x180019208  call    ??0OnlineServiceResponse@BingOnlineServices@@QEAA@AEBU01@@Z; BingOnlineServices::OnlineServiceResponse::OnlineServiceResponse(BingOnlineServices::OnlineServiceResponse const &)
0x18001920d  mov     byte ptr [rbx+11h], 0
0x180019211  mov     dword ptr [rbx+14h], 0
0x180019218  mov     rdx, rbx; struct pplx::details::_ContinuationTaskHandleBase *
0x18001921b  mov     rcx, rdi; this
0x18001921e  call    ?_ScheduleContinuation@_Task_impl_base@details@pplx@@QEAAXPEAU_ContinuationTaskHandleBase@23@@Z; pplx::details::_Task_impl_base::_ScheduleContinuation(pplx::details::_ContinuationTaskHandleBase *)
0x180019223  nop
0x180019224  mov     rcx, [r13+8]; this
0x180019228  test    rcx, rcx
0x18001922b  jz      short loc_180019233
0x18001922d  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x180019232  nop
0x180019233  lea     rcx, [r14+8]
0x180019237  call    ?_Tidy@?$vector@PEAXV?$allocator@PEAX@std@@@std@@AEAAXXZ; std::vector<void *>::_Tidy(void)
0x18001923c  mov     rax, rsi
0x18001923f  mov     rcx, [rbp+3Fh+var_48]
0x180019243  xor     rcx, rsp; StackCookie
0x180019246  call    __security_check_cookie
0x18001924b  add     rsp, 0A8h
0x180019252  pop     r15
0x180019254  pop     r14
0x180019256  pop     r13
0x180019258  pop     r12
0x18001925a  pop     rdi
0x18001925b  pop     rsi
0x18001925c  pop     rbx
0x18001925d  pop     rbp
0x18001925e  retn
```
