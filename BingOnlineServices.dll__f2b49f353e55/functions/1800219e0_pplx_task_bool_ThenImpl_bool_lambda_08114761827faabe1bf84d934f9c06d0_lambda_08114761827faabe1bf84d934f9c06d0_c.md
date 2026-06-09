# pplx::task<bool>::_ThenImpl<bool,_lambda_08114761827faabe1bf84d934f9c06d0_>(_lambda_08114761827faabe1bf84d934f9c06d0_ const &,pplx::task_options const &)

- ea: `0x1800219e0`
- end: `0x180021be6`
- name: `??$_ThenImpl@_NV_lambda_08114761827faabe1bf84d934f9c06d0_@@@?$task@_N@pplx@@AEBA?AV?$task@X@1@AEBV_lambda_08114761827faabe1bf84d934f9c06d0_@@AEBVtask_options@1@@Z`
- size: `518`
- prototype: `__int64 __fastcall(_QWORD *, __int64, __int64, __int64)`
- caller_count: `1`
- callee_count: `13`
- tags: `service_task`

## callers

- `0x1800235fc`

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
- `0x1800219e0`
- `0x180021bec`

## string_xrefs

- `0x180021a23`: `then() cannot be called on a default constructed task.`

## pseudocode

```c
// Hidden C++ exception states: #wind=7
__int64 __fastcall pplx::task<bool>::_ThenImpl<bool,_lambda_08114761827faabe1bf84d934f9c06d0_>(
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
  std::_Ref_count_base *v12; // r15
  __int64 v13; // r13
  const struct pplx::details::_TaskCreationCallstack *v14; // rax
  char v15; // bl
  int v16; // r8d
  __int64 v18; // [rsp+48h] [rbp-B8h] BYREF
  __int64 v19; // [rsp+50h] [rbp-B0h] BYREF
  std::_Ref_count_base *v20; // [rsp+58h] [rbp-A8h]
  __int64 v21; // [rsp+60h] [rbp-A0h]
  _QWORD v22[3]; // [rsp+68h] [rbp-98h] BYREF
  _BYTE v23[8]; // [rsp+80h] [rbp-80h] BYREF
  std::_Ref_count_base *v24; // [rsp+88h] [rbp-78h]
  _BYTE v25[8]; // [rsp+A0h] [rbp-60h] BYREF
  _BYTE v26[24]; // [rsp+A8h] [rbp-58h] BYREF
  _BYTE v27[8]; // [rsp+C0h] [rbp-40h] BYREF
  _BYTE v28[24]; // [rsp+C8h] [rbp-38h] BYREF
  _BYTE pExceptionObject[8]; // [rsp+E0h] [rbp-20h] BYREF
  _BYTE v30[48]; // [rsp+E8h] [rbp-18h] BYREF

  v18 = a2;
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
    v18 = v8;
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
    pplx::cancellation_token_registration::_Clear((pplx::cancellation_token_registration *)&v18);
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
  pplx::task<bool>::_ThenImpl<bool,_lambda_08114761827faabe1bf84d934f9c06d0_>((_DWORD)a1, a2, v16, v8);
  std::vector<void *>::_Tidy(v26);
  if ( v12 )
    std::_Ref_count_base::_Decref(v12);
  return a2;
}

```

## disassembly

```asm
0x1800219e0  mov     [rsp-8+arg_10], rbx
0x1800219e5  push    rbp
0x1800219e6  push    rsi
0x1800219e7  push    rdi
0x1800219e8  push    r12
0x1800219ea  push    r13
0x1800219ec  push    r14
0x1800219ee  push    r15
0x1800219f0  lea     rbp, [rsp-20h]
0x1800219f5  sub     rsp, 120h
0x1800219fc  mov     rax, cs:__security_cookie
0x180021a03  xor     rax, rsp
0x180021a06  mov     [rbp+50h+var_38], rax
0x180021a0a  mov     rsi, r9
0x180021a0d  mov     r14, rdx
0x180021a10  mov     r12, rcx
0x180021a13  mov     [rsp+150h+var_108], rdx
0x180021a18  xor     ebx, ebx
0x180021a1a  mov     [rsp+150h+var_110], ebx
0x180021a1e  cmp     [rcx], rbx
0x180021a21  jnz     short loc_180021A44
0x180021a23  lea     rdx, aThenCannotBeCa; "then() cannot be called on a default co"...
0x180021a2a  lea     rcx, [rbp+50h+pExceptionObject]; this
0x180021a2e  call    ??0invalid_operation@pplx@@QEAA@PEBD@Z; pplx::invalid_operation::invalid_operation(char const *)
0x180021a33  lea     rdx, _TI2?AVinvalid_operation@pplx@@; pThrowInfo
0x180021a3a  lea     rcx, [rbp+50h+pExceptionObject]; pExceptionObject
0x180021a3e  call    _CxxThrowException_0
0x180021a44  mov     r10d, 2
0x180021a4a  cmp     [r9+50h], bl
0x180021a4e  jz      short loc_180021A70
0x180021a50  mov     rdi, [r9+18h]
0x180021a54  test    rdi, rdi
0x180021a57  jz      short loc_180021A5D
0x180021a59  lock inc dword ptr [rdi+8]
0x180021a5d  mov     [rsp+150h+var_108], rdi
0x180021a62  mov     ebx, 1
0x180021a67  test    rdi, rdi
0x180021a6a  cmovz   rdi, r10
0x180021a6e  jmp     short loc_180021A72
0x180021a70  xor     edi, edi
0x180021a72  test    bl, 1
0x180021a75  jz      short loc_180021A8B
0x180021a77  and     ebx, 0FFFFFFFEh
0x180021a7a  lea     rcx, [rsp+150h+var_108]; this
0x180021a7f  call    ?_Clear@cancellation_token_registration@pplx@@AEAAXXZ; pplx::cancellation_token_registration::_Clear(void)
0x180021a84  nop
0x180021a85  mov     r10d, 2
0x180021a8b  cmp     byte ptr [rsi+51h], 0
0x180021a8f  jz      short loc_180021AA2
0x180021a91  lea     rdx, [rbp+50h+var_D0]
0x180021a95  mov     rcx, rsi
0x180021a98  call    ?get_scheduler@task_options@pplx@@QEBA?AUscheduler_ptr@2@XZ; pplx::task_options::get_scheduler(void)
0x180021a9d  or      ebx, r10d
0x180021aa0  jmp     short loc_180021AB3
0x180021aa2  lea     rdx, [rsp+150h+var_100]
0x180021aa7  mov     rcx, [r12]
0x180021aab  call    ?_GetScheduler@_Task_impl_base@details@pplx@@QEBA?AUscheduler_ptr@3@XZ; pplx::details::_Task_impl_base::_GetScheduler(void)
0x180021ab0  or      ebx, 4
0x180021ab3  mov     r9, rax
0x180021ab6  mov     rax, [rax]
0x180021ab9  mov     [rsp+150h+var_E8], rax
0x180021abe  mov     r15, [r9+8]
0x180021ac2  mov     [rsp+150h+var_E0], r15
0x180021ac7  mov     qword ptr [r9], 0
0x180021ace  mov     qword ptr [r9+8], 0
0x180021ad6  mov     r13, [r9+10h]
0x180021ada  mov     [rsp+150h+var_D8], r13
0x180021adf  test    bl, 4
0x180021ae2  jz      short loc_180021AF6
0x180021ae4  and     ebx, 0FFFFFFFBh
0x180021ae7  mov     rcx, [rsp+150h+var_F8]; this
0x180021aec  test    rcx, rcx
0x180021aef  jz      short loc_180021AF6
0x180021af1  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x180021af6  test    bl, 2
0x180021af9  jz      short loc_180021B0C
0x180021afb  and     ebx, 0FFFFFFFDh
0x180021afe  mov     rcx, [rbp+50h+var_C8]; this
0x180021b02  test    rcx, rcx
0x180021b05  jz      short loc_180021B0C
0x180021b07  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x180021b0c  cmp     byte ptr [rsi+28h], 0
0x180021b10  jz      short loc_180021B25
0x180021b12  lea     rdx, [rsi+30h]; struct pplx::details::_TaskCreationCallstack *
0x180021b16  lea     rcx, [rbp+50h+pExceptionObject]; this
0x180021b1a  call    ??0_TaskCreationCallstack@details@pplx@@QEAA@AEBV012@@Z; pplx::details::_TaskCreationCallstack::_TaskCreationCallstack(pplx::details::_TaskCreationCallstack const &)
0x180021b1f  nop
0x180021b20  or      ebx, 8
0x180021b23  jmp     short loc_180021B32
0x180021b25  lea     rcx, [rbp+50h+var_90]; this
0x180021b29  call    ??0_TaskCreationCallstack@details@pplx@@QEAA@XZ; pplx::details::_TaskCreationCallstack::_TaskCreationCallstack(void)
0x180021b2e  nop
0x180021b2f  or      ebx, 10h
0x180021b32  mov     [rsp+150h+var_110], ebx
0x180021b36  mov     rdx, rax; struct pplx::details::_TaskCreationCallstack *
0x180021b39  lea     rcx, [rbp+50h+var_B0]; this
0x180021b3d  call    ??0_TaskCreationCallstack@details@pplx@@QEAA@AEBV012@@Z; pplx::details::_TaskCreationCallstack::_TaskCreationCallstack(pplx::details::_TaskCreationCallstack const &)
0x180021b42  nop
0x180021b43  test    bl, 10h
0x180021b46  jz      short loc_180021B55
0x180021b48  and     ebx, 0FFFFFFEFh
0x180021b4b  lea     rcx, [rbp+50h+var_88]
0x180021b4f  call    ?_Tidy@?$vector@PEAXV?$allocator@PEAX@std@@@std@@AEAAXXZ; std::vector<void *>::_Tidy(void)
0x180021b54  nop
0x180021b55  test    bl, 8
0x180021b58  jz      short loc_180021B63
0x180021b5a  lea     rcx, [rbp+50h+var_68]
0x180021b5e  call    ?_Tidy@?$vector@PEAXV?$allocator@PEAX@std@@@std@@AEAAXXZ; std::vector<void *>::_Tidy(void)
0x180021b63  lea     rdx, [rbp+50h+var_B0]; struct pplx::details::_TaskCreationCallstack *
0x180021b67  lea     rcx, [rbp+50h+var_D0]; this
0x180021b6b  call    ??0_TaskCreationCallstack@details@pplx@@QEAA@AEBV012@@Z; pplx::details::_TaskCreationCallstack::_TaskCreationCallstack(pplx::details::_TaskCreationCallstack const &)
0x180021b70  mov     r8, rax
0x180021b73  lea     rdx, [rsp+150h+var_E8]
0x180021b78  lea     rcx, [rsp+150h+var_100]
0x180021b7d  call    ??$?0U?$_Task_impl@UOnlineServiceResponse@BingOnlineServices@@@details@pplx@@$0A@@?$shared_ptr@U_Task_impl_base@details@pplx@@@std@@QEAA@AEBV?$shared_ptr@U?$_Task_impl@UOnlineServiceResponse@BingOnlineServices@@@details@pplx@@@1@@Z; std::shared_ptr<pplx::details::_Task_impl_base>::shared_ptr<pplx::details::_Task_impl_base>(std::shared_ptr<pplx::details::_Task_impl<BingOnlineServices::OnlineServiceResponse>> const &)
0x180021b82  mov     [rsp+150h+var_F0], r13
0x180021b87  mov     [rsp+150h+var_120], r8
0x180021b8c  lea     rax, [rsp+150h+var_100]
0x180021b91  mov     [rsp+150h+var_128], rax
0x180021b96  mov     r9, rdi
0x180021b99  mov     rdx, r14
0x180021b9c  mov     rcx, r12
0x180021b9f  call    ??$_ThenImpl@_NV_lambda_08114761827faabe1bf84d934f9c06d0_@@@?$task@_N@pplx@@AEBA?AV?$task@X@1@AEBV_lambda_08114761827faabe1bf84d934f9c06d0_@@PEAV_CancellationTokenState@details@1@AEBVtask_continuation_context@1@Uscheduler_ptr@1@V_TaskCreationCallstack@51@W4_TaskInliningMode@51@@Z; pplx::task<bool>::_ThenImpl<bool,_lambda_08114761827faabe1bf84d934f9c06d0_>(_lambda_08114761827faabe1bf84d934f9c06d0_ const &,pplx::details::_CancellationTokenState *,pplx::task_continuation_context const &,pplx::scheduler_ptr,pplx::details::_TaskCreationCallstack,pplx::details::_TaskInliningMode)
0x180021ba4  nop
0x180021ba5  lea     rcx, [rbp+50h+var_A8]
0x180021ba9  call    ?_Tidy@?$vector@PEAXV?$allocator@PEAX@std@@@std@@AEAAXXZ; std::vector<void *>::_Tidy(void)
0x180021bae  nop
0x180021baf  test    r15, r15
0x180021bb2  jz      short loc_180021BBC
0x180021bb4  mov     rcx, r15; this
0x180021bb7  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x180021bbc  mov     rax, r14
0x180021bbf  mov     rcx, [rbp+50h+var_38]
0x180021bc3  xor     rcx, rsp; StackCookie
0x180021bc6  call    __security_check_cookie
0x180021bcb  mov     rbx, [rsp+150h+arg_10]
0x180021bd3  add     rsp, 120h
0x180021bda  pop     r15
0x180021bdc  pop     r14
0x180021bde  pop     r13
0x180021be0  pop     r12
0x180021be2  pop     rdi
0x180021be3  pop     rsi
0x180021be4  pop     rbp
0x180021be5  retn
```
