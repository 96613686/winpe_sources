# pplx::details::_WhenAllImpl<void,pplx::task<void> *>::_Perform(pplx::task_options const &,pplx::task<void> *,pplx::task<void> *)

- ea: `0x180029abc`
- end: `0x180029df4`
- name: `?_Perform@?$_WhenAllImpl@XPEAV?$task@X@pplx@@@details@pplx@@SA?AV?$task@X@3@AEBVtask_options@3@PEAV43@1@Z`
- size: `824`
- prototype: ``
- caller_count: `1`
- callee_count: `24`
- tags: `service_task, broker_com_uri`

## callers

- `0x1800260e8`

## callees

- `0x180004fa0`
- `0x18000529c`
- `0x180005e9c`
- `0x18000fa74`
- `0x180011dcc`
- `0x180012034`
- `0x18001230c`
- `0x180012430`
- `0x180012cc0`
- `0x180014368`
- `0x1800148ac`
- `0x180014ddc`
- `0x18001a458`
- `0x18001ad20`
- `0x18001e0e0`
- `0x18001f5f0`
- `0x18001fc50`
- `0x180023ec8`
- `0x1800241d8`
- `0x180025790`
- `0x180026c4c`
- `0x1800295f4`
- `0x180029abc`
- `0x18002f8e8`

## string_xrefs

- `0x180029dd3`: `is_apartment_aware() cannot be called on a default constructed task.`

## pseudocode

```c
// Hidden C++ exception states: #wind=10
_QWORD *__fastcall pplx::details::_WhenAllImpl<void,pplx::task<void> *>::_Perform(
        _QWORD *a1,
        __int64 a2,
        pplx::details::_Task_impl_base **a3,
        pplx::details::_Task_impl_base **a4)
{
  int v8; // ebx
  __int64 v9; // rdi
  _QWORD *v10; // r14
  __int64 v11; // rax
  __int64 v12; // r8
  __int64 v13; // r8
  __int64 v14; // r9
  struct pplx::details::_CancellationTokenState *v15; // r8
  int v16; // ebx
  int v17; // ebx
  pplx::details::_Task_impl_base **i; // r15
  __int64 v19; // r8
  int v21; // [rsp+20h] [rbp-E0h]
  int v22; // [rsp+20h] [rbp-E0h]
  _QWORD *v23; // [rsp+48h] [rbp-B8h] BYREF
  _QWORD v24[2]; // [rsp+50h] [rbp-B0h] BYREF
  __int64 v25; // [rsp+60h] [rbp-A0h] BYREF
  std::_Ref_count_base *v26; // [rsp+68h] [rbp-98h]
  __int64 v27; // [rsp+70h] [rbp-90h]
  __int128 v28; // [rsp+78h] [rbp-88h] BYREF
  pplx::details::_Task_impl_base *v29; // [rsp+88h] [rbp-78h] BYREF
  std::_Ref_count_base *v30; // [rsp+90h] [rbp-70h]
  _QWORD v31[3]; // [rsp+98h] [rbp-68h] BYREF
  __int64 v32; // [rsp+B0h] [rbp-50h] BYREF
  std::_Ref_count_base *v33; // [rsp+B8h] [rbp-48h]
  __int64 v34; // [rsp+C0h] [rbp-40h]
  _QWORD *v35; // [rsp+D0h] [rbp-30h]
  _BYTE v36[24]; // [rsp+E0h] [rbp-20h] BYREF
  _BYTE v37[72]; // [rsp+F8h] [rbp-8h] BYREF
  _QWORD pExceptionObject[7]; // [rsp+140h] [rbp+40h] BYREF

  v35 = a1;
  v8 = 0;
  if ( *(_BYTE *)(a2 + 80) )
  {
    v9 = *(_QWORD *)(a2 + 24);
    if ( v9 )
      _InterlockedIncrement((volatile signed __int32 *)(v9 + 8));
    v24[0] = v9;
    v8 = 1;
    if ( !v9 )
      v9 = 2;
  }
  else
  {
    v9 = 0;
  }
  if ( (v8 & 1) != 0 )
  {
    v8 &= ~1u;
    pplx::cancellation_token_registration::_Clear((pplx::cancellation_token_registration *)v24);
  }
  v10 = operator new(0x20u);
  v24[0] = v10;
  pplx::task_completion_event<unsigned char>::task_completion_event<unsigned char>(v10);
  std::atomic<unsigned __int64>::atomic<unsigned __int64>(v10 + 2);
  v10[3] = 0;
  pplx::cancellation_token_source::cancellation_token_source((pplx::cancellation_token_source *)v24);
  pplx::task_options::task_options((pplx::task_options *)v36, (const struct pplx::task_options *)a2);
  v23 = (_QWORD *)v24[0];
  if ( v24[0] == 2 )
  {
    v23 = 0;
  }
  else if ( v24[0] )
  {
    _InterlockedIncrement((volatile signed __int32 *)(v24[0] + 8LL));
  }
  v24[1] = &v23;
  pplx::cancellation_token::operator=(v37, &v23);
  v37[56] = 1;
  pplx::cancellation_token_registration::_Clear((pplx::cancellation_token_registration *)&v23);
  v28 = 0;
  v11 = v10[1];
  if ( v11 )
    _InterlockedIncrement((volatile signed __int32 *)(v11 + 8));
  v28 = *(_OWORD *)v10;
  pplx::task<unsigned char>::task<unsigned char>(&v29, (__int64 *)&v28, (__int64)v36);
  pplx::details::_Task_impl_base::_GetScheduler(v29, &v25);
  pplx::details::_TaskCreationCallstack::_TaskCreationCallstack((pplx::details::_TaskCreationCallstack *)&v32);
  v32 = v12;
  std::shared_ptr<pplx::details::_Task_impl_base>::shared_ptr<pplx::details::_Task_impl_base>(v31, &v25);
  v31[2] = v27;
  pplx::task<unsigned char>::_ThenImpl<unsigned char,_lambda_0073bfcf7319a8539931a760272dfdc9_>(
    &v29,
    a1,
    v13,
    v14,
    v21,
    v31,
    (__int64)&v32);
  v16 = v8 | 4;
  if ( v26 )
    std::_Ref_count_base::_Decref(v26);
  v17 = v16 | 2;
  if ( v9 )
  {
    pplx::details::_JoinAllTokens_Add((pplx::details *)v24, (const struct pplx::cancellation_token_source *)v9, v15);
    v9 = ((char *)a4 - (char *)a3) >> 4;
  }
  else
  {
    for ( i = a3; i != a4; i += 2 )
    {
      ++v9;
      pplx::details::_JoinAllTokens_Add(
        (pplx::details *)v24,
        *((const struct pplx::cancellation_token_source **)*i + 12),
        v15);
    }
  }
  v10[3] = v9;
  if ( a3 == a4 )
  {
    pplx::task_completion_event<unsigned char>::set(v10);
    pplx::details::_RunAllParam<unsigned char>::`scalar deleting destructor'(v10);
  }
  else
  {
    do
    {
      if ( !*a3 )
      {
        pplx::invalid_operation::invalid_operation(
          (pplx::invalid_operation *)pExceptionObject,
          "is_apartment_aware() cannot be called on a default constructed task.");
        throw (pplx::invalid_operation *)pExceptionObject;
      }
      if ( *((_BYTE *)*a3 + 12) )
        *(_BYTE *)(*a1 + 12LL) = 1;
      v23 = v10;
      pplx::details::_Task_impl_base::_GetScheduler(*a3, &v32);
      pplx::details::_TaskCreationCallstack::_TaskCreationCallstack((pplx::details::_TaskCreationCallstack *)pExceptionObject);
      pExceptionObject[0] = v19;
      std::shared_ptr<pplx::details::_Task_impl_base>::shared_ptr<pplx::details::_Task_impl_base>(&v25, &v32);
      v27 = v34;
      pplx::task<unsigned char>::_ThenImpl<void,_lambda_08052126caf30f35e5385e23194a6196_>(
        a3,
        v31,
        &v23,
        2,
        v22,
        &v25,
        (__int64)pExceptionObject);
      v17 |= 8u;
      if ( v33 )
        std::_Ref_count_base::_Decref(v33);
      pplx::task<long>::~task<long>(v31);
      a3 += 2;
    }
    while ( a3 != a4 );
  }
  if ( v30 )
    std::_Ref_count_base::_Decref(v30);
  pplx::task_options::~task_options((pplx::task_options *)v36);
  pplx::cancellation_token_source::~cancellation_token_source((pplx::cancellation_token_source *)v24);
  return a1;
}

```

## disassembly

```asm
0x180029abc  mov     [rsp-8+arg_18], rbx
0x180029ac1  push    rbp
0x180029ac2  push    rsi
0x180029ac3  push    rdi
0x180029ac4  push    r12
0x180029ac6  push    r13
0x180029ac8  push    r14
0x180029aca  push    r15
0x180029acc  lea     rbp, [rsp-80h]
0x180029ad1  sub     rsp, 180h
0x180029ad8  mov     rax, cs:__security_cookie
0x180029adf  xor     rax, rsp
0x180029ae2  mov     [rbp+0B0h+var_38], rax
0x180029ae6  mov     r12, r9
0x180029ae9  mov     rsi, r8
0x180029aec  mov     r15, rdx
0x180029aef  mov     r13, rcx
0x180029af2  mov     [rbp+0B0h+var_E0], rcx
0x180029af6  xor     ebx, ebx
0x180029af8  mov     [rsp+1B0h+var_170], ebx
0x180029afc  lea     eax, [rbx+2]
0x180029aff  cmp     [rdx+50h], bl
0x180029b02  jz      short loc_180029B28
0x180029b04  mov     rdi, [rdx+18h]
0x180029b08  test    rdi, rdi
0x180029b0b  jz      short loc_180029B11
0x180029b0d  lock inc dword ptr [rdi+8]
0x180029b11  mov     [rsp+1B0h+var_160], rdi
0x180029b16  mov     ebx, 1
0x180029b1b  mov     [rsp+1B0h+var_170], ebx
0x180029b1f  test    rdi, rdi
0x180029b22  cmovz   rdi, rax
0x180029b26  jmp     short loc_180029B2A
0x180029b28  xor     edi, edi
0x180029b2a  test    bl, 1
0x180029b2d  jz      short loc_180029B41
0x180029b2f  and     ebx, 0FFFFFFFEh
0x180029b32  mov     [rsp+1B0h+var_170], ebx
0x180029b36  lea     rcx, [rsp+1B0h+var_160]; this
0x180029b3b  call    ?_Clear@cancellation_token_registration@pplx@@AEAAXXZ; pplx::cancellation_token_registration::_Clear(void)
0x180029b40  nop
0x180029b41  mov     ecx, 20h ; ' '; Size
0x180029b46  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180029b4b  mov     r14, rax
0x180029b4e  mov     [rsp+1B0h+var_160], rax
0x180029b53  mov     rcx, rax
0x180029b56  call    ??0?$task_completion_event@E@pplx@@QEAA@XZ; pplx::task_completion_event<uchar>::task_completion_event<uchar>(void)
0x180029b5b  lea     rcx, [r14+10h]
0x180029b5f  call    ??0?$atomic@_K@std@@QEAA@_K@Z; std::atomic<unsigned __int64>::atomic<unsigned __int64>(unsigned __int64)
0x180029b64  mov     qword ptr [r14+18h], 0
0x180029b6c  lea     rcx, [rsp+1B0h+var_160]; this
0x180029b71  call    ??0cancellation_token_source@pplx@@QEAA@XZ; pplx::cancellation_token_source::cancellation_token_source(void)
0x180029b76  nop
0x180029b77  mov     rdx, r15; struct pplx::task_options *
0x180029b7a  lea     rcx, [rbp+0B0h+var_D0]; this
0x180029b7e  call    ??0task_options@pplx@@QEAA@AEBV01@@Z; pplx::task_options::task_options(pplx::task_options const &)
0x180029b83  nop
0x180029b84  mov     rax, [rsp+1B0h+var_160]
0x180029b89  mov     [rsp+1B0h+var_168], rax
0x180029b8e  cmp     rax, 2
0x180029b92  jnz     short loc_180029B9F
0x180029b94  mov     [rsp+1B0h+var_168], 0
0x180029b9d  jmp     short loc_180029BA8
0x180029b9f  test    rax, rax
0x180029ba2  jz      short loc_180029BA8
0x180029ba4  lock inc dword ptr [rax+8]
0x180029ba8  lea     rax, [rsp+1B0h+var_168]
0x180029bad  mov     [rsp+1B0h+var_158], rax
0x180029bb2  lea     rdx, [rsp+1B0h+var_168]
0x180029bb7  lea     rcx, [rbp+0B0h+var_B8]
0x180029bbb  call    ??4cancellation_token@pplx@@QEAAAEAV01@AEBV01@@Z; pplx::cancellation_token::operator=(pplx::cancellation_token const &)
0x180029bc0  mov     [rbp+0B0h+var_80], 1
0x180029bc4  lea     rcx, [rsp+1B0h+var_168]; this
0x180029bc9  call    ?_Clear@cancellation_token_registration@pplx@@AEAAXXZ; pplx::cancellation_token_registration::_Clear(void)
0x180029bce  nop
0x180029bcf  xorps   xmm0, xmm0
0x180029bd2  movdqu  [rsp+1B0h+var_138], xmm0
0x180029bd8  mov     rax, [r14+8]
0x180029bdc  test    rax, rax
0x180029bdf  jz      short loc_180029BE5
0x180029be1  lock inc dword ptr [rax+8]
0x180029be5  mov     rax, [r14]
0x180029be8  mov     qword ptr [rsp+1B0h+var_138], rax
0x180029bed  mov     rax, [r14+8]
0x180029bf1  mov     qword ptr [rbp+0B0h+var_138+8], rax
0x180029bf5  lea     r8, [rbp+0B0h+var_D0]
0x180029bf9  lea     rdx, [rsp+1B0h+var_138]
0x180029bfe  lea     rcx, [rbp+0B0h+var_128]
0x180029c02  call    ??$?0V?$task_completion_event@E@pplx@@@?$task@E@pplx@@QEAA@V?$task_completion_event@E@1@AEBVtask_options@1@@Z; pplx::task<uchar>::task<uchar>(pplx::task_completion_event<uchar>,pplx::task_options const &)
0x180029c07  nop
0x180029c08  lea     rdx, [rsp+1B0h+var_150]
0x180029c0d  mov     rcx, [rbp+0B0h+var_128]
0x180029c11  call    ?_GetScheduler@_Task_impl_base@details@pplx@@QEBA?AUscheduler_ptr@3@XZ; pplx::details::_Task_impl_base::_GetScheduler(void)
0x180029c16  nop
0x180029c17  mov     r8, [rbp+0B8h]
0x180029c1e  lea     rcx, [rbp+0B0h+var_100]; this
0x180029c22  call    ??0_TaskCreationCallstack@details@pplx@@QEAA@XZ; pplx::details::_TaskCreationCallstack::_TaskCreationCallstack(void)
0x180029c27  mov     [rbp+0B0h+var_100], r8
0x180029c2b  lea     rdx, [rsp+1B0h+var_150]
0x180029c30  lea     rcx, [rbp+0B0h+var_118]
0x180029c34  call    ??$?0U?$_Task_impl@UOnlineServiceResponse@BingOnlineServices@@@details@pplx@@$0A@@?$shared_ptr@U_Task_impl_base@details@pplx@@@std@@QEAA@AEBV?$shared_ptr@U?$_Task_impl@UOnlineServiceResponse@BingOnlineServices@@@details@pplx@@@1@@Z; std::shared_ptr<pplx::details::_Task_impl_base>::shared_ptr<pplx::details::_Task_impl_base>(std::shared_ptr<pplx::details::_Task_impl<BingOnlineServices::OnlineServiceResponse>> const &)
0x180029c39  mov     rcx, [rsp+1B0h+var_140]
0x180029c3e  mov     [rbp+0B0h+var_108], rcx
0x180029c42  lea     rax, [rbp+0B0h+var_100]
0x180029c46  mov     [rsp+1B0h+var_180], rax
0x180029c4b  lea     rax, [rbp+0B0h+var_118]
0x180029c4f  mov     [rsp+1B0h+var_188], rax
0x180029c54  mov     rdx, r13
0x180029c57  lea     rcx, [rbp+0B0h+var_128]
0x180029c5b  call    ??$_ThenImpl@EV_lambda_0073bfcf7319a8539931a760272dfdc9_@@@?$task@E@pplx@@AEBA?AV?$task@X@1@AEBV_lambda_0073bfcf7319a8539931a760272dfdc9_@@PEAV_CancellationTokenState@details@1@AEBVtask_continuation_context@1@Uscheduler_ptr@1@V_TaskCreationCallstack@51@W4_TaskInliningMode@51@@Z; pplx::task<uchar>::_ThenImpl<uchar,_lambda_0073bfcf7319a8539931a760272dfdc9_>(_lambda_0073bfcf7319a8539931a760272dfdc9_ const &,pplx::details::_CancellationTokenState *,pplx::task_continuation_context const &,pplx::scheduler_ptr,pplx::details::_TaskCreationCallstack,pplx::details::_TaskInliningMode)
0x180029c60  or      ebx, 4
0x180029c63  mov     rcx, [rsp+1B0h+var_148]; this
0x180029c68  test    rcx, rcx
0x180029c6b  jz      short loc_180029C72
0x180029c6d  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x180029c72  or      ebx, 2
0x180029c75  mov     [rsp+1B0h+var_170], ebx
0x180029c79  test    rdi, rdi
0x180029c7c  jz      short loc_180029C97
0x180029c7e  mov     rdx, rdi; struct pplx::cancellation_token_source *
0x180029c81  lea     rcx, [rsp+1B0h+var_160]; this
0x180029c86  call    ?_JoinAllTokens_Add@details@pplx@@YAXAEBVcancellation_token_source@2@PEAV_CancellationTokenState@12@@Z; pplx::details::_JoinAllTokens_Add(pplx::cancellation_token_source const &,pplx::details::_CancellationTokenState *)
0x180029c8b  mov     rdi, r12
0x180029c8e  sub     rdi, rsi
0x180029c91  sar     rdi, 4
0x180029c95  jmp     short loc_180029CBC
0x180029c97  mov     r15, rsi
0x180029c9a  cmp     rsi, r12
0x180029c9d  jz      short loc_180029CBC
0x180029c9f  inc     rdi
0x180029ca2  mov     rdx, [r15]
0x180029ca5  mov     rdx, [rdx+60h]; struct pplx::cancellation_token_source *
0x180029ca9  lea     rcx, [rsp+1B0h+var_160]; this
0x180029cae  call    ?_JoinAllTokens_Add@details@pplx@@YAXAEBVcancellation_token_source@2@PEAV_CancellationTokenState@12@@Z; pplx::details::_JoinAllTokens_Add(pplx::cancellation_token_source const &,pplx::details::_CancellationTokenState *)
0x180029cb3  add     r15, 10h
0x180029cb7  cmp     r15, r12
0x180029cba  jnz     short loc_180029C9F
0x180029cbc  mov     [r14+18h], rdi
0x180029cc0  cmp     rsi, r12
0x180029cc3  jnz     short loc_180029CDA
0x180029cc5  mov     rcx, r14
0x180029cc8  call    ?set@?$task_completion_event@E@pplx@@QEBA_NE@Z; pplx::task_completion_event<uchar>::set(uchar)
0x180029ccd  mov     rcx, r14; Block
0x180029cd0  call    ??_G?$_RunAllParam@E@details@pplx@@QEAAPEAXI@Z; pplx::details::_RunAllParam<uchar>::`scalar deleting destructor'(uint)
0x180029cd5  jmp     loc_180029D86
0x180029cda  mov     rax, [rsi]
0x180029cdd  test    rax, rax
0x180029ce0  jz      loc_180029DD3
0x180029ce6  cmp     byte ptr [rax+0Ch], 0
0x180029cea  jz      short loc_180029CF4
0x180029cec  mov     rax, [r13+0]
0x180029cf0  mov     byte ptr [rax+0Ch], 1
0x180029cf4  mov     [rsp+1B0h+var_168], r14
0x180029cf9  lea     rdx, [rbp+0B0h+var_100]
0x180029cfd  mov     rcx, [rsi]
0x180029d00  call    ?_GetScheduler@_Task_impl_base@details@pplx@@QEBA?AUscheduler_ptr@3@XZ; pplx::details::_Task_impl_base::_GetScheduler(void)
0x180029d05  nop
0x180029d06  mov     r8, [rbp+0B8h]
0x180029d0d  lea     rcx, [rbp+0B0h+pExceptionObject]; this
0x180029d11  call    ??0_TaskCreationCallstack@details@pplx@@QEAA@XZ; pplx::details::_TaskCreationCallstack::_TaskCreationCallstack(void)
0x180029d16  mov     [rbp+0B0h+pExceptionObject], r8
0x180029d1a  lea     rdx, [rbp+0B0h+var_100]
0x180029d1e  lea     rcx, [rsp+1B0h+var_150]
0x180029d23  call    ??$?0U?$_Task_impl@UOnlineServiceResponse@BingOnlineServices@@@details@pplx@@$0A@@?$shared_ptr@U_Task_impl_base@details@pplx@@@std@@QEAA@AEBV?$shared_ptr@U?$_Task_impl@UOnlineServiceResponse@BingOnlineServices@@@details@pplx@@@1@@Z; std::shared_ptr<pplx::details::_Task_impl_base>::shared_ptr<pplx::details::_Task_impl_base>(std::shared_ptr<pplx::details::_Task_impl<BingOnlineServices::OnlineServiceResponse>> const &)
0x180029d28  mov     rcx, [rbp+0B0h+var_F0]
0x180029d2c  mov     [rsp+1B0h+var_140], rcx
0x180029d31  lea     rax, [rbp+0B0h+pExceptionObject]
0x180029d35  mov     [rsp+1B0h+var_180], rax
0x180029d3a  lea     rax, [rsp+1B0h+var_150]
0x180029d3f  mov     [rsp+1B0h+var_188], rax
0x180029d44  mov     r9d, 2
0x180029d4a  lea     r8, [rsp+1B0h+var_168]
0x180029d4f  lea     rdx, [rbp+0B0h+var_118]
0x180029d53  mov     rcx, rsi
0x180029d56  call    ??$_ThenImpl@XV_lambda_08052126caf30f35e5385e23194a6196_@@@?$task@E@pplx@@AEBA?AV?$task@X@1@AEBV_lambda_08052126caf30f35e5385e23194a6196_@@PEAV_CancellationTokenState@details@1@AEBVtask_continuation_context@1@Uscheduler_ptr@1@V_TaskCreationCallstack@51@W4_TaskInliningMode@51@@Z; pplx::task<uchar>::_ThenImpl<void,_lambda_08052126caf30f35e5385e23194a6196_>(_lambda_08052126caf30f35e5385e23194a6196_ const &,pplx::details::_CancellationTokenState *,pplx::task_continuation_context const &,pplx::scheduler_ptr,pplx::details::_TaskCreationCallstack,pplx::details::_TaskInliningMode)
0x180029d5b  or      ebx, 8
0x180029d5e  mov     [rsp+1B0h+var_170], ebx
0x180029d62  mov     rcx, [rbp+0B0h+var_F8]; this
0x180029d66  test    rcx, rcx
0x180029d69  jz      short loc_180029D70
0x180029d6b  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x180029d70  lea     rcx, [rbp+0B0h+var_118]; void *
0x180029d74  call    ??1?$task@J@pplx@@QEAA@XZ; pplx::task<long>::~task<long>(void)
0x180029d79  add     rsi, 10h
0x180029d7d  cmp     rsi, r12
0x180029d80  jnz     loc_180029CDA
0x180029d86  mov     rcx, [rbp+0B0h+var_120]; this
0x180029d8a  test    rcx, rcx
0x180029d8d  jz      short loc_180029D95
0x180029d8f  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x180029d94  nop
0x180029d95  lea     rcx, [rbp+0B0h+var_D0]; this
0x180029d99  call    ??1task_options@pplx@@QEAA@XZ; pplx::task_options::~task_options(void)
0x180029d9e  nop
0x180029d9f  lea     rcx, [rsp+1B0h+var_160]; this
0x180029da4  call    ??1cancellation_token_source@pplx@@QEAA@XZ; pplx::cancellation_token_source::~cancellation_token_source(void)
0x180029da9  mov     rax, r13
0x180029dac  mov     rcx, [rbp+0B0h+var_38]
0x180029db0  xor     rcx, rsp; StackCookie
0x180029db3  call    __security_check_cookie
0x180029db8  mov     rbx, [rsp+1B0h+arg_18]
0x180029dc0  add     rsp, 180h
0x180029dc7  pop     r15
0x180029dc9  pop     r14
0x180029dcb  pop     r13
0x180029dcd  pop     r12
0x180029dcf  pop     rdi
0x180029dd0  pop     rsi
0x180029dd1  pop     rbp
0x180029dd2  retn
0x180029dd3  lea     rdx, aIsApartmentAwa; "is_apartment_aware() cannot be called o"...
0x180029dda  lea     rcx, [rbp+0B0h+pExceptionObject]; this
0x180029dde  call    ??0invalid_operation@pplx@@QEAA@PEBD@Z; pplx::invalid_operation::invalid_operation(char const *)
0x180029de3  lea     rdx, _TI2?AVinvalid_operation@pplx@@; pThrowInfo
0x180029dea  lea     rcx, [rbp+0B0h+pExceptionObject]; pExceptionObject
0x180029dee  call    _CxxThrowException_0
```
