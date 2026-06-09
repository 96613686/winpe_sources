# pplx::task_web::json::value_::_ThenImpl_web::json::value__lambda_2928cf0dfdb8953a0e15861cab0d651e___

- ea: `0x180018ed8`
- end: `0x1800190dd`
- name: `pplx::task_web::json::value_::_ThenImpl_web::json::value__lambda_2928cf0dfdb8953a0e15861cab0d651e___`
- size: `517`
- prototype: ``
- caller_count: `1`
- callee_count: `13`
- tags: `registry_config, service_task`

## callers

- `0x18001a058`

## callees

- `0x180004fa0`
- `0x180005e9c`
- `0x18000fa74`
- `0x180011d84`
- `0x180011dcc`
- `0x180012034`
- `0x180014368`
- `0x1800148ac`
- `0x180014ddc`
- `0x1800157f4`
- `0x180015a8c`
- `0x180018ed8`
- `0x1800190e4`

## string_xrefs

- `0x180018f1d`: `then() cannot be called on a default constructed task.`

## pseudocode

```c
// Hidden C++ exception states: #wind=7
__int64 __fastcall pplx::task_web::json::value_::_ThenImpl_web::json::value__lambda_2928cf0dfdb8953a0e15861cab0d651e___(
        _QWORD *a1,
        __int64 a2,
        __int64 a3,
        __int64 a4)
{
  char v7; // bl
  __int64 v8; // rdi
  _QWORD *scheduler; // rax
  char v10; // r10
  char v11; // bl
  std::_Ref_count_base *v12; // r14
  __int64 v13; // r13
  const struct pplx::details::_TaskCreationCallstack *v14; // rax
  char v15; // bl
  __int64 v17; // [rsp+48h] [rbp-B8h] BYREF
  __int64 v18; // [rsp+50h] [rbp-B0h]
  __int64 v19; // [rsp+58h] [rbp-A8h] BYREF
  std::_Ref_count_base *v20; // [rsp+60h] [rbp-A0h]
  __int64 v21; // [rsp+68h] [rbp-98h]
  _QWORD v22[3]; // [rsp+70h] [rbp-90h] BYREF
  char v23[8]; // [rsp+88h] [rbp-78h] BYREF
  std::_Ref_count_base *v24; // [rsp+90h] [rbp-70h]
  char v25[8]; // [rsp+A8h] [rbp-58h] BYREF
  char v26[24]; // [rsp+B0h] [rbp-50h] BYREF
  char v27[8]; // [rsp+C8h] [rbp-38h] BYREF
  char v28[24]; // [rsp+D0h] [rbp-30h] BYREF
  char pExceptionObject[8]; // [rsp+E8h] [rbp-18h] BYREF
  char v30[48]; // [rsp+F0h] [rbp-10h] BYREF

  v18 = a3;
  v17 = a2;
  v7 = 0;
  if ( !*a1 )
  {
    pplx::invalid_operation::invalid_operation(
      (pplx::invalid_operation *)pExceptionObject,
      "then() cannot be called on a default constructed task.");
    throw (pplx::invalid_operation *)pExceptionObject;
  }
  if ( *(_BYTE *)(a4 + 80) )
  {
    v8 = *(_QWORD *)(a4 + 24);
    if ( v8 )
      _InterlockedIncrement((volatile signed __int32 *)(v8 + 8));
    v17 = v8;
    v7 = 1;
    if ( !v8 )
      v8 = 2;
  }
  else
  {
    v8 = 0;
  }
  if ( (v7 & 1) != 0 )
  {
    v7 &= ~1u;
    pplx::cancellation_token_registration::_Clear((pplx::cancellation_token_registration *)&v17);
  }
  if ( *(_BYTE *)(a4 + 81) )
  {
    scheduler = (_QWORD *)pplx::task_options::get_scheduler(a4, v23);
    v11 = v10 | v7;
  }
  else
  {
    scheduler = (_QWORD *)pplx::details::_Task_impl_base::_GetScheduler(*a1, &v19);
    v11 = v7 | 4;
  }
  v22[0] = *scheduler;
  v12 = (std::_Ref_count_base *)scheduler[1];
  v22[1] = v12;
  *scheduler = 0;
  scheduler[1] = 0;
  v13 = scheduler[2];
  v22[2] = v13;
  if ( (v11 & 4) != 0 )
  {
    v11 &= ~4u;
    if ( v20 )
      std::_Ref_count_base::_Decref(v20);
  }
  if ( (v11 & 2) != 0 )
  {
    v11 &= ~2u;
    if ( v24 )
      std::_Ref_count_base::_Decref(v24);
  }
  if ( *(_BYTE *)(a4 + 40) )
  {
    v14 = (const struct pplx::details::_TaskCreationCallstack *)pplx::details::_TaskCreationCallstack::_TaskCreationCallstack(
                                                                  (pplx::details::_TaskCreationCallstack *)pExceptionObject,
                                                                  (const struct pplx::details::_TaskCreationCallstack *)(a4 + 48));
    v15 = v11 | 8;
  }
  else
  {
    v14 = (const struct pplx::details::_TaskCreationCallstack *)pplx::details::_TaskCreationCallstack::_TaskCreationCallstack((pplx::details::_TaskCreationCallstack *)v27);
    v15 = v11 | 0x10;
  }
  pplx::details::_TaskCreationCallstack::_TaskCreationCallstack((pplx::details::_TaskCreationCallstack *)v25, v14);
  if ( (v15 & 0x10) != 0 )
  {
    v15 &= ~0x10u;
    std::vector<void *>::_Tidy(v28);
  }
  if ( (v15 & 8) != 0 )
    std::vector<void *>::_Tidy(v30);
  pplx::details::_TaskCreationCallstack::_TaskCreationCallstack(
    (pplx::details::_TaskCreationCallstack *)v23,
    (const struct pplx::details::_TaskCreationCallstack *)v25);
  std::shared_ptr<pplx::details::_Task_impl_base>::shared_ptr<pplx::details::_Task_impl_base>(&v19, v22);
  v21 = v13;
  pplx::task_web::json::value_::_ThenImpl_web::json::value__lambda_2928cf0dfdb8953a0e15861cab0d651e____0(
    a1,
    a2,
    v18,
    v8);
  std::vector<void *>::_Tidy(v26);
  if ( v12 )
    std::_Ref_count_base::_Decref(v12);
  return a2;
}

```

## disassembly

```asm
0x180018ed8  push    rbp
0x180018eda  push    rbx
0x180018edb  push    rsi
0x180018edc  push    rdi
0x180018edd  push    r12
0x180018edf  push    r13
0x180018ee1  push    r14
0x180018ee3  push    r15
0x180018ee5  lea     rbp, [rsp-38h]
0x180018eea  sub     rsp, 138h
0x180018ef1  mov     rax, cs:__security_cookie
0x180018ef8  xor     rax, rsp
0x180018efb  mov     [rbp+70h+var_50], rax
0x180018eff  mov     rsi, r9
0x180018f02  mov     [rsp+170h+var_120], r8
0x180018f07  mov     r15, rdx
0x180018f0a  mov     r12, rcx
0x180018f0d  mov     [rsp+170h+var_128], rdx
0x180018f12  xor     ebx, ebx
0x180018f14  mov     [rsp+170h+var_130], ebx
0x180018f18  cmp     [rcx], rbx
0x180018f1b  jnz     short loc_180018F3E
0x180018f1d  lea     rdx, aThenCannotBeCa; "then() cannot be called on a default co"...
0x180018f24  lea     rcx, [rbp+70h+pExceptionObject]; this
0x180018f28  call    ??0invalid_operation@pplx@@QEAA@PEBD@Z; pplx::invalid_operation::invalid_operation(char const *)
0x180018f2d  lea     rdx, _TI2?AVinvalid_operation@pplx@@; pThrowInfo
0x180018f34  lea     rcx, [rbp+70h+pExceptionObject]; pExceptionObject
0x180018f38  call    _CxxThrowException_0
0x180018f3e  mov     r10d, 2
0x180018f44  cmp     [r9+50h], bl
0x180018f48  jz      short loc_180018F6A
0x180018f4a  mov     rdi, [r9+18h]
0x180018f4e  test    rdi, rdi
0x180018f51  jz      short loc_180018F57
0x180018f53  lock inc dword ptr [rdi+8]
0x180018f57  mov     [rsp+170h+var_128], rdi
0x180018f5c  mov     ebx, 1
0x180018f61  test    rdi, rdi
0x180018f64  cmovz   rdi, r10
0x180018f68  jmp     short loc_180018F6C
0x180018f6a  xor     edi, edi
0x180018f6c  test    bl, 1
0x180018f6f  jz      short loc_180018F85
0x180018f71  and     ebx, 0FFFFFFFEh
0x180018f74  lea     rcx, [rsp+170h+var_128]; this
0x180018f79  call    ?_Clear@cancellation_token_registration@pplx@@AEAAXXZ; pplx::cancellation_token_registration::_Clear(void)
0x180018f7e  nop
0x180018f7f  mov     r10d, 2
0x180018f85  cmp     byte ptr [rsi+51h], 0
0x180018f89  jz      short loc_180018F9C
0x180018f8b  lea     rdx, [rbp+70h+var_E8]
0x180018f8f  mov     rcx, rsi
0x180018f92  call    ?get_scheduler@task_options@pplx@@QEBA?AUscheduler_ptr@2@XZ; pplx::task_options::get_scheduler(void)
0x180018f97  or      ebx, r10d
0x180018f9a  jmp     short loc_180018FAD
0x180018f9c  lea     rdx, [rsp+170h+var_118]
0x180018fa1  mov     rcx, [r12]
0x180018fa5  call    ?_GetScheduler@_Task_impl_base@details@pplx@@QEBA?AUscheduler_ptr@3@XZ; pplx::details::_Task_impl_base::_GetScheduler(void)
0x180018faa  or      ebx, 4
0x180018fad  mov     r9, rax
0x180018fb0  mov     rax, [rax]
0x180018fb3  mov     [rsp+170h+var_100], rax
0x180018fb8  mov     r14, [r9+8]
0x180018fbc  mov     [rsp+170h+var_F8], r14
0x180018fc1  mov     qword ptr [r9], 0
0x180018fc8  mov     qword ptr [r9+8], 0
0x180018fd0  mov     r13, [r9+10h]
0x180018fd4  mov     [rbp+70h+var_F0], r13
0x180018fd8  test    bl, 4
0x180018fdb  jz      short loc_180018FEF
0x180018fdd  and     ebx, 0FFFFFFFBh
0x180018fe0  mov     rcx, [rsp+170h+var_110]; this
0x180018fe5  test    rcx, rcx
0x180018fe8  jz      short loc_180018FEF
0x180018fea  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x180018fef  test    bl, 2
0x180018ff2  jz      short loc_180019005
0x180018ff4  and     ebx, 0FFFFFFFDh
0x180018ff7  mov     rcx, [rbp+70h+var_E0]; this
0x180018ffb  test    rcx, rcx
0x180018ffe  jz      short loc_180019005
0x180019000  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x180019005  cmp     byte ptr [rsi+28h], 0
0x180019009  jz      short loc_18001901E
0x18001900b  lea     rdx, [rsi+30h]; struct pplx::details::_TaskCreationCallstack *
0x18001900f  lea     rcx, [rbp+70h+pExceptionObject]; this
0x180019013  call    ??0_TaskCreationCallstack@details@pplx@@QEAA@AEBV012@@Z; pplx::details::_TaskCreationCallstack::_TaskCreationCallstack(pplx::details::_TaskCreationCallstack const &)
0x180019018  nop
0x180019019  or      ebx, 8
0x18001901c  jmp     short loc_18001902B
0x18001901e  lea     rcx, [rbp+70h+var_A8]; this
0x180019022  call    ??0_TaskCreationCallstack@details@pplx@@QEAA@XZ; pplx::details::_TaskCreationCallstack::_TaskCreationCallstack(void)
0x180019027  nop
0x180019028  or      ebx, 10h
0x18001902b  mov     [rsp+170h+var_130], ebx
0x18001902f  mov     rdx, rax; struct pplx::details::_TaskCreationCallstack *
0x180019032  lea     rcx, [rbp+70h+var_C8]; this
0x180019036  call    ??0_TaskCreationCallstack@details@pplx@@QEAA@AEBV012@@Z; pplx::details::_TaskCreationCallstack::_TaskCreationCallstack(pplx::details::_TaskCreationCallstack const &)
0x18001903b  nop
0x18001903c  test    bl, 10h
0x18001903f  jz      short loc_18001904E
0x180019041  and     ebx, 0FFFFFFEFh
0x180019044  lea     rcx, [rbp+70h+var_A0]
0x180019048  call    ?_Tidy@?$vector@PEAXV?$allocator@PEAX@std@@@std@@AEAAXXZ; std::vector<void *>::_Tidy(void)
0x18001904d  nop
0x18001904e  test    bl, 8
0x180019051  jz      short loc_18001905C
0x180019053  lea     rcx, [rbp+70h+var_80]
0x180019057  call    ?_Tidy@?$vector@PEAXV?$allocator@PEAX@std@@@std@@AEAAXXZ; std::vector<void *>::_Tidy(void)
0x18001905c  lea     rdx, [rbp+70h+var_C8]; struct pplx::details::_TaskCreationCallstack *
0x180019060  lea     rcx, [rbp+70h+var_E8]; this
0x180019064  call    ??0_TaskCreationCallstack@details@pplx@@QEAA@AEBV012@@Z; pplx::details::_TaskCreationCallstack::_TaskCreationCallstack(pplx::details::_TaskCreationCallstack const &)
0x180019069  mov     r10, rax
0x18001906c  lea     rdx, [rsp+170h+var_100]
0x180019071  lea     rcx, [rsp+170h+var_118]
0x180019076  call    ??$?0U?$_Task_impl@UOnlineServiceResponse@BingOnlineServices@@@details@pplx@@$0A@@?$shared_ptr@U_Task_impl_base@details@pplx@@@std@@QEAA@AEBV?$shared_ptr@U?$_Task_impl@UOnlineServiceResponse@BingOnlineServices@@@details@pplx@@@1@@Z; std::shared_ptr<pplx::details::_Task_impl_base>::shared_ptr<pplx::details::_Task_impl_base>(std::shared_ptr<pplx::details::_Task_impl<BingOnlineServices::OnlineServiceResponse>> const &)
0x18001907b  mov     [rsp+170h+var_108], r13
0x180019080  mov     [rsp+170h+var_140], r10
0x180019085  lea     rax, [rsp+170h+var_118]
0x18001908a  mov     [rsp+170h+var_148], rax
0x18001908f  mov     r9, rdi
0x180019092  mov     r8, [rsp+170h+var_120]
0x180019097  mov     rdx, r15
0x18001909a  mov     rcx, r12
0x18001909d  call    pplx__task_web__json__value____ThenImpl_web__json__value__lambda_2928cf0dfdb8953a0e15861cab0d651e____0
0x1800190a2  nop
0x1800190a3  lea     rcx, [rbp+70h+var_C0]
0x1800190a7  call    ?_Tidy@?$vector@PEAXV?$allocator@PEAX@std@@@std@@AEAAXXZ; std::vector<void *>::_Tidy(void)
0x1800190ac  nop
0x1800190ad  test    r14, r14
0x1800190b0  jz      short loc_1800190BA
0x1800190b2  mov     rcx, r14; this
0x1800190b5  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x1800190ba  mov     rax, r15
0x1800190bd  mov     rcx, [rbp+70h+var_50]
0x1800190c1  xor     rcx, rsp; StackCookie
0x1800190c4  call    __security_check_cookie
0x1800190c9  add     rsp, 138h
0x1800190d0  pop     r15
0x1800190d2  pop     r14
0x1800190d4  pop     r13
0x1800190d6  pop     r12
0x1800190d8  pop     rdi
0x1800190d9  pop     rsi
0x1800190da  pop     rbx
0x1800190db  pop     rbp
0x1800190dc  retn
```
