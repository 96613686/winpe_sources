# pplx::task<unsigned __int64>::_ThenImpl<unsigned __int64,_lambda_9ae1b6b611071959ad7ff25d21dd2ecc_>(_lambda_9ae1b6b611071959ad7ff25d21dd2ecc_ const &,pplx::task_options const &)

- ea: `0x180019268`
- end: `0x18001946d`
- name: `??$_ThenImpl@_KV_lambda_9ae1b6b611071959ad7ff25d21dd2ecc_@@@?$task@_K@pplx@@AEBA?AV?$task@Vvalue@json@web@@@1@AEBV_lambda_9ae1b6b611071959ad7ff25d21dd2ecc_@@AEBVtask_options@1@@Z`
- size: `517`
- prototype: `__int64 __fastcall(_QWORD *, __int64, __int64, __int64)`
- caller_count: `1`
- callee_count: `13`
- tags: `service_task`

## callers

- `0x18001a108`

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
- `0x180019268`
- `0x180019474`

## string_xrefs

- `0x1800192ad`: `then() cannot be called on a default constructed task.`

## pseudocode

```c
// Hidden C++ exception states: #wind=7
__int64 __fastcall pplx::task<unsigned __int64>::_ThenImpl<unsigned __int64,_lambda_9ae1b6b611071959ad7ff25d21dd2ecc_>(
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
  _BYTE v23[8]; // [rsp+88h] [rbp-78h] BYREF
  std::_Ref_count_base *v24; // [rsp+90h] [rbp-70h]
  _BYTE v25[8]; // [rsp+A8h] [rbp-58h] BYREF
  _BYTE v26[24]; // [rsp+B0h] [rbp-50h] BYREF
  _BYTE v27[8]; // [rsp+C8h] [rbp-38h] BYREF
  _BYTE v28[24]; // [rsp+D0h] [rbp-30h] BYREF
  _BYTE pExceptionObject[8]; // [rsp+E8h] [rbp-18h] BYREF
  _BYTE v30[48]; // [rsp+F0h] [rbp-10h] BYREF

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
      LODWORD(v8) = 2;
  }
  else
  {
    LODWORD(v8) = 0;
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
  pplx::task<unsigned __int64>::_ThenImpl<unsigned __int64,_lambda_9ae1b6b611071959ad7ff25d21dd2ecc_>(
    (_DWORD)a1,
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
0x180019268  push    rbp
0x18001926a  push    rbx
0x18001926b  push    rsi
0x18001926c  push    rdi
0x18001926d  push    r12
0x18001926f  push    r13
0x180019271  push    r14
0x180019273  push    r15
0x180019275  lea     rbp, [rsp-38h]
0x18001927a  sub     rsp, 138h
0x180019281  mov     rax, cs:__security_cookie
0x180019288  xor     rax, rsp
0x18001928b  mov     [rbp+70h+var_50], rax
0x18001928f  mov     rsi, r9
0x180019292  mov     [rsp+170h+var_120], r8
0x180019297  mov     r15, rdx
0x18001929a  mov     r12, rcx
0x18001929d  mov     [rsp+170h+var_128], rdx
0x1800192a2  xor     ebx, ebx
0x1800192a4  mov     [rsp+170h+var_130], ebx
0x1800192a8  cmp     [rcx], rbx
0x1800192ab  jnz     short loc_1800192CE
0x1800192ad  lea     rdx, aThenCannotBeCa; "then() cannot be called on a default co"...
0x1800192b4  lea     rcx, [rbp+70h+pExceptionObject]; this
0x1800192b8  call    ??0invalid_operation@pplx@@QEAA@PEBD@Z; pplx::invalid_operation::invalid_operation(char const *)
0x1800192bd  lea     rdx, _TI2?AVinvalid_operation@pplx@@; pThrowInfo
0x1800192c4  lea     rcx, [rbp+70h+pExceptionObject]; pExceptionObject
0x1800192c8  call    _CxxThrowException_0
0x1800192ce  mov     r10d, 2
0x1800192d4  cmp     [r9+50h], bl
0x1800192d8  jz      short loc_1800192FA
0x1800192da  mov     rdi, [r9+18h]
0x1800192de  test    rdi, rdi
0x1800192e1  jz      short loc_1800192E7
0x1800192e3  lock inc dword ptr [rdi+8]
0x1800192e7  mov     [rsp+170h+var_128], rdi
0x1800192ec  mov     ebx, 1
0x1800192f1  test    rdi, rdi
0x1800192f4  cmovz   rdi, r10
0x1800192f8  jmp     short loc_1800192FC
0x1800192fa  xor     edi, edi
0x1800192fc  test    bl, 1
0x1800192ff  jz      short loc_180019315
0x180019301  and     ebx, 0FFFFFFFEh
0x180019304  lea     rcx, [rsp+170h+var_128]; this
0x180019309  call    ?_Clear@cancellation_token_registration@pplx@@AEAAXXZ; pplx::cancellation_token_registration::_Clear(void)
0x18001930e  nop
0x18001930f  mov     r10d, 2
0x180019315  cmp     byte ptr [rsi+51h], 0
0x180019319  jz      short loc_18001932C
0x18001931b  lea     rdx, [rbp+70h+var_E8]
0x18001931f  mov     rcx, rsi
0x180019322  call    ?get_scheduler@task_options@pplx@@QEBA?AUscheduler_ptr@2@XZ; pplx::task_options::get_scheduler(void)
0x180019327  or      ebx, r10d
0x18001932a  jmp     short loc_18001933D
0x18001932c  lea     rdx, [rsp+170h+var_118]
0x180019331  mov     rcx, [r12]
0x180019335  call    ?_GetScheduler@_Task_impl_base@details@pplx@@QEBA?AUscheduler_ptr@3@XZ; pplx::details::_Task_impl_base::_GetScheduler(void)
0x18001933a  or      ebx, 4
0x18001933d  mov     r9, rax
0x180019340  mov     rax, [rax]
0x180019343  mov     [rsp+170h+var_100], rax
0x180019348  mov     r14, [r9+8]
0x18001934c  mov     [rsp+170h+var_F8], r14
0x180019351  mov     qword ptr [r9], 0
0x180019358  mov     qword ptr [r9+8], 0
0x180019360  mov     r13, [r9+10h]
0x180019364  mov     [rbp+70h+var_F0], r13
0x180019368  test    bl, 4
0x18001936b  jz      short loc_18001937F
0x18001936d  and     ebx, 0FFFFFFFBh
0x180019370  mov     rcx, [rsp+170h+var_110]; this
0x180019375  test    rcx, rcx
0x180019378  jz      short loc_18001937F
0x18001937a  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18001937f  test    bl, 2
0x180019382  jz      short loc_180019395
0x180019384  and     ebx, 0FFFFFFFDh
0x180019387  mov     rcx, [rbp+70h+var_E0]; this
0x18001938b  test    rcx, rcx
0x18001938e  jz      short loc_180019395
0x180019390  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x180019395  cmp     byte ptr [rsi+28h], 0
0x180019399  jz      short loc_1800193AE
0x18001939b  lea     rdx, [rsi+30h]; struct pplx::details::_TaskCreationCallstack *
0x18001939f  lea     rcx, [rbp+70h+pExceptionObject]; this
0x1800193a3  call    ??0_TaskCreationCallstack@details@pplx@@QEAA@AEBV012@@Z; pplx::details::_TaskCreationCallstack::_TaskCreationCallstack(pplx::details::_TaskCreationCallstack const &)
0x1800193a8  nop
0x1800193a9  or      ebx, 8
0x1800193ac  jmp     short loc_1800193BB
0x1800193ae  lea     rcx, [rbp+70h+var_A8]; this
0x1800193b2  call    ??0_TaskCreationCallstack@details@pplx@@QEAA@XZ; pplx::details::_TaskCreationCallstack::_TaskCreationCallstack(void)
0x1800193b7  nop
0x1800193b8  or      ebx, 10h
0x1800193bb  mov     [rsp+170h+var_130], ebx
0x1800193bf  mov     rdx, rax; struct pplx::details::_TaskCreationCallstack *
0x1800193c2  lea     rcx, [rbp+70h+var_C8]; this
0x1800193c6  call    ??0_TaskCreationCallstack@details@pplx@@QEAA@AEBV012@@Z; pplx::details::_TaskCreationCallstack::_TaskCreationCallstack(pplx::details::_TaskCreationCallstack const &)
0x1800193cb  nop
0x1800193cc  test    bl, 10h
0x1800193cf  jz      short loc_1800193DE
0x1800193d1  and     ebx, 0FFFFFFEFh
0x1800193d4  lea     rcx, [rbp+70h+var_A0]
0x1800193d8  call    ?_Tidy@?$vector@PEAXV?$allocator@PEAX@std@@@std@@AEAAXXZ; std::vector<void *>::_Tidy(void)
0x1800193dd  nop
0x1800193de  test    bl, 8
0x1800193e1  jz      short loc_1800193EC
0x1800193e3  lea     rcx, [rbp+70h+var_80]
0x1800193e7  call    ?_Tidy@?$vector@PEAXV?$allocator@PEAX@std@@@std@@AEAAXXZ; std::vector<void *>::_Tidy(void)
0x1800193ec  lea     rdx, [rbp+70h+var_C8]; struct pplx::details::_TaskCreationCallstack *
0x1800193f0  lea     rcx, [rbp+70h+var_E8]; this
0x1800193f4  call    ??0_TaskCreationCallstack@details@pplx@@QEAA@AEBV012@@Z; pplx::details::_TaskCreationCallstack::_TaskCreationCallstack(pplx::details::_TaskCreationCallstack const &)
0x1800193f9  mov     r10, rax
0x1800193fc  lea     rdx, [rsp+170h+var_100]
0x180019401  lea     rcx, [rsp+170h+var_118]
0x180019406  call    ??$?0U?$_Task_impl@UOnlineServiceResponse@BingOnlineServices@@@details@pplx@@$0A@@?$shared_ptr@U_Task_impl_base@details@pplx@@@std@@QEAA@AEBV?$shared_ptr@U?$_Task_impl@UOnlineServiceResponse@BingOnlineServices@@@details@pplx@@@1@@Z; std::shared_ptr<pplx::details::_Task_impl_base>::shared_ptr<pplx::details::_Task_impl_base>(std::shared_ptr<pplx::details::_Task_impl<BingOnlineServices::OnlineServiceResponse>> const &)
0x18001940b  mov     [rsp+170h+var_108], r13
0x180019410  mov     [rsp+170h+var_140], r10
0x180019415  lea     rax, [rsp+170h+var_118]
0x18001941a  mov     [rsp+170h+var_148], rax
0x18001941f  mov     r9, rdi
0x180019422  mov     r8, [rsp+170h+var_120]
0x180019427  mov     rdx, r15
0x18001942a  mov     rcx, r12
0x18001942d  call    ??$_ThenImpl@_KV_lambda_9ae1b6b611071959ad7ff25d21dd2ecc_@@@?$task@_K@pplx@@AEBA?AV?$task@Vvalue@json@web@@@1@AEBV_lambda_9ae1b6b611071959ad7ff25d21dd2ecc_@@PEAV_CancellationTokenState@details@1@AEBVtask_continuation_context@1@Uscheduler_ptr@1@V_TaskCreationCallstack@51@W4_TaskInliningMode@51@@Z; pplx::task<unsigned __int64>::_ThenImpl<unsigned __int64,_lambda_9ae1b6b611071959ad7ff25d21dd2ecc_>(_lambda_9ae1b6b611071959ad7ff25d21dd2ecc_ const &,pplx::details::_CancellationTokenState *,pplx::task_continuation_context const &,pplx::scheduler_ptr,pplx::details::_TaskCreationCallstack,pplx::details::_TaskInliningMode)
0x180019432  nop
0x180019433  lea     rcx, [rbp+70h+var_C0]
0x180019437  call    ?_Tidy@?$vector@PEAXV?$allocator@PEAX@std@@@std@@AEAAXXZ; std::vector<void *>::_Tidy(void)
0x18001943c  nop
0x18001943d  test    r14, r14
0x180019440  jz      short loc_18001944A
0x180019442  mov     rcx, r14; this
0x180019445  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18001944a  mov     rax, r15
0x18001944d  mov     rcx, [rbp+70h+var_50]
0x180019451  xor     rcx, rsp; StackCookie
0x180019454  call    __security_check_cookie
0x180019459  add     rsp, 138h
0x180019460  pop     r15
0x180019462  pop     r14
0x180019464  pop     r13
0x180019466  pop     r12
0x180019468  pop     rdi
0x180019469  pop     rsi
0x18001946a  pop     rbx
0x18001946b  pop     rbp
0x18001946c  retn
```
