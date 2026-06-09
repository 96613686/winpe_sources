# Concurrency::streams::details::streambuf_state_manager<char>::close(int)

- ea: `0x18004d080`
- end: `0x18004d2e5`
- name: `?close@?$streambuf_state_manager@D@details@streams@Concurrency@@UEAA?AV?$task@X@pplx@@H@Z`
- size: `613`
- prototype: ``
- caller_count: `0`
- callee_count: `16`
- tags: `service_task`

## callees

- `0x180004fa0`
- `0x180005e9c`
- `0x18000fa74`
- `0x180012034`
- `0x18001235c`
- `0x180012430`
- `0x180012cc0`
- `0x180012d44`
- `0x1800148ac`
- `0x1800260e8`
- `0x1800303c0`
- `0x1800305f8`
- `0x18004778c`
- `0x180047ad0`
- `0x18004d080`
- `0x18005f010`

## string_xrefs

- `0x18004d190`: `is_done() cannot be called on a default constructed task.`

## pseudocode

```c
_QWORD *__fastcall Concurrency::streams::details::streambuf_state_manager<char>::close(__int64 a1, _QWORD *a2, char a3)
{
  __int64 v6; // rax
  __int64 v7; // rax
  _QWORD *v8; // rax
  std::_Ref_count_base *v9; // rsi
  __int64 v10; // rcx
  __int64 v11; // rax
  __int64 v12; // rbx
  __int64 v13; // rax
  __int64 v14; // rax
  __int64 v16; // [rsp+28h] [rbp-81h] BYREF
  std::_Ref_count_base *v17; // [rsp+30h] [rbp-79h]
  _QWORD v18[2]; // [rsp+38h] [rbp-71h] BYREF
  _BYTE v19[16]; // [rsp+48h] [rbp-61h] BYREF
  _QWORD *v20; // [rsp+58h] [rbp-51h]
  _BYTE v21[8]; // [rsp+60h] [rbp-49h] BYREF
  std::_Ref_count_base *v22; // [rsp+68h] [rbp-41h]
  _BYTE v23[16]; // [rsp+70h] [rbp-39h] BYREF
  _BYTE v24[16]; // [rsp+80h] [rbp-29h] BYREF
  _BYTE pExceptionObject[88]; // [rsp+90h] [rbp-19h] BYREF

  v20 = a2;
  v6 = pplx::task_options::task_options((pplx::task_options *)pExceptionObject);
  pplx::task_from_result(a2, v6);
  pplx::task_options::~task_options((pplx::task_options *)pExceptionObject);
  if ( (a3 & 1) != 0 && (*(unsigned __int8 (__fastcall **)(__int64))(*(_QWORD *)a1 + 8LL))(a1) )
  {
    v7 = (*(__int64 (__fastcall **)(__int64, _QWORD *))(*(_QWORD *)a1 + 376LL))(a1, v18);
    if ( a2 != (_QWORD *)v7 )
      std::shared_ptr<pplx::details::_ExceptionHolder>::operator=(a2, v7);
    pplx::task<long>::~task<long>(v18);
  }
  v8 = (_QWORD *)std::enable_shared_from_this<Concurrency::streams::details::streambuf_state_manager<unsigned char>>::shared_from_this(
                   a1 + 8,
                   v21);
  v18[0] = *v8;
  v9 = (std::_Ref_count_base *)v8[1];
  v18[1] = v9;
  *v8 = 0;
  v8[1] = 0;
  if ( v22 )
    std::_Ref_count_base::_Decref(v22);
  if ( (a3 & 2) != 0 && (*(unsigned __int8 (__fastcall **)(__int64))(*(_QWORD *)a1 + 16LL))(a1) )
  {
    v10 = *a2;
    if ( !*a2 )
    {
      pplx::invalid_operation::invalid_operation(
        (pplx::invalid_operation *)pExceptionObject,
        "is_done() cannot be called on a default constructed task.");
      throw (pplx::invalid_operation *)pExceptionObject;
    }
    if ( *(_DWORD *)(v10 + 8) == 3 || *(_DWORD *)(v10 + 8) == 4 )
    {
      v12 = (*(__int64 (__fastcall **)(__int64, _BYTE *))(*(_QWORD *)a1 + 384LL))(a1, v24);
      pplx::task_options::task_options((pplx::task_options *)pExceptionObject);
      std::shared_ptr<pplx::details::_Task_impl_base>::shared_ptr<pplx::details::_Task_impl_base>(&v16, v18);
      v13 = pplx::task<void>::then<_lambda_89ef8f9e192d0c9d8a44552b2fb585d9_>(v12, v23, &v16);
      v14 = pplx::operator&&(v19, a2, v13);
      if ( a2 != (_QWORD *)v14 )
        std::shared_ptr<pplx::details::_ExceptionHolder>::operator=(a2, v14);
      pplx::task<long>::~task<long>(v19);
      pplx::task<long>::~task<long>(v23);
      if ( v17 )
        std::_Ref_count_base::_Decref(v17);
      pplx::task<long>::~task<long>(v24);
    }
    else
    {
      pplx::task_options::task_options((pplx::task_options *)pExceptionObject);
      std::shared_ptr<pplx::details::_Task_impl_base>::shared_ptr<pplx::details::_Task_impl_base>(&v16, v18);
      v11 = pplx::task<void>::then<_lambda_f0d76877e2124af93dd5e09c8d041edf_>(a2, v19, &v16);
      if ( a2 != (_QWORD *)v11 )
        std::shared_ptr<pplx::details::_ExceptionHolder>::operator=(a2, v11);
      pplx::task<long>::~task<long>(v19);
      if ( v17 )
        std::_Ref_count_base::_Decref(v17);
    }
  }
  if ( v9 )
    std::_Ref_count_base::_Decref(v9);
  return a2;
}

```

## disassembly

```asm
0x18004d080  mov     [rsp-8+arg_10], rbx
0x18004d085  mov     [rsp-8+arg_18], rsi
0x18004d08a  push    rbp
0x18004d08b  push    rdi
0x18004d08c  push    r14
0x18004d08e  lea     rbp, [rsp-47h]
0x18004d093  sub     rsp, 0F0h
0x18004d09a  mov     rax, cs:__security_cookie
0x18004d0a1  xor     rax, rsp
0x18004d0a4  mov     [rbp+57h+var_18], rax
0x18004d0a8  mov     r14d, r8d
0x18004d0ab  mov     rdi, rdx
0x18004d0ae  mov     rbx, rcx
0x18004d0b1  mov     [rbp+57h+var_A8], rdx
0x18004d0b5  mov     [rsp+100h+var_E0], 0
0x18004d0bd  lea     rcx, [rbp+57h+pExceptionObject]; this
0x18004d0c1  call    ??0task_options@pplx@@QEAA@XZ; pplx::task_options::task_options(void)
0x18004d0c6  nop
0x18004d0c7  mov     rdx, rax
0x18004d0ca  mov     rcx, rdi
0x18004d0cd  call    ?task_from_result@pplx@@YA?AV?$task@X@1@AEBVtask_options@1@@Z; pplx::task_from_result(pplx::task_options const &)
0x18004d0d2  mov     [rsp+100h+var_E0], 1
0x18004d0da  lea     rcx, [rbp+57h+pExceptionObject]; this
0x18004d0de  call    ??1task_options@pplx@@QEAA@XZ; pplx::task_options::~task_options(void)
0x18004d0e3  test    r14b, 1
0x18004d0e7  jz      short loc_18004D12B
0x18004d0e9  mov     rax, [rbx]
0x18004d0ec  mov     rcx, rbx
0x18004d0ef  mov     rax, [rax+8]
0x18004d0f3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004d0f8  test    al, al
0x18004d0fa  jz      short loc_18004D12B
0x18004d0fc  mov     rax, [rbx]
0x18004d0ff  lea     rdx, [rbp+57h+var_C8]
0x18004d103  mov     rcx, rbx
0x18004d106  mov     rax, [rax+178h]
0x18004d10d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004d112  cmp     rdi, rax
0x18004d115  jz      short loc_18004D122
0x18004d117  mov     rdx, rax
0x18004d11a  mov     rcx, rdi
0x18004d11d  call    ??4?$shared_ptr@U_ExceptionHolder@details@pplx@@@std@@QEAAAEAV01@$$QEAV01@@Z; std::shared_ptr<pplx::details::_ExceptionHolder>::operator=(std::shared_ptr<pplx::details::_ExceptionHolder> &&)
0x18004d122  lea     rcx, [rbp+57h+var_C8]; void *
0x18004d126  call    ??1?$task@J@pplx@@QEAA@XZ; pplx::task<long>::~task<long>(void)
0x18004d12b  lea     rcx, [rbx+8]
0x18004d12f  lea     rdx, [rbp+57h+var_A0]
0x18004d133  call    ?shared_from_this@?$enable_shared_from_this@V?$streambuf_state_manager@E@details@streams@Concurrency@@@std@@QEAA?AV?$shared_ptr@V?$streambuf_state_manager@E@details@streams@Concurrency@@@2@XZ; std::enable_shared_from_this<Concurrency::streams::details::streambuf_state_manager<uchar>>::shared_from_this(void)
0x18004d138  mov     rcx, rax
0x18004d13b  mov     rax, [rax]
0x18004d13e  mov     [rbp+57h+var_C8], rax
0x18004d142  mov     rsi, [rcx+8]
0x18004d146  mov     [rbp+57h+var_C0], rsi
0x18004d14a  mov     qword ptr [rcx], 0
0x18004d151  mov     qword ptr [rcx+8], 0
0x18004d159  mov     rcx, [rbp+57h+var_98]; this
0x18004d15d  test    rcx, rcx
0x18004d160  jz      short loc_18004D167
0x18004d162  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18004d167  test    r14b, 2
0x18004d16b  jz      loc_18004D2B0
0x18004d171  mov     rax, [rbx]
0x18004d174  mov     rcx, rbx
0x18004d177  mov     rax, [rax+10h]
0x18004d17b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004d180  test    al, al
0x18004d182  jz      loc_18004D2B0
0x18004d188  mov     rcx, [rdi]
0x18004d18b  test    rcx, rcx
0x18004d18e  jnz     short loc_18004D1B1
0x18004d190  lea     rdx, aIsDoneCannotBe; "is_done() cannot be called on a default"...
0x18004d197  lea     rcx, [rbp+57h+pExceptionObject]; this
0x18004d19b  call    ??0invalid_operation@pplx@@QEAA@PEBD@Z; pplx::invalid_operation::invalid_operation(char const *)
0x18004d1a0  lea     rdx, _TI2?AVinvalid_operation@pplx@@; pThrowInfo
0x18004d1a7  lea     rcx, [rbp+57h+pExceptionObject]; pExceptionObject
0x18004d1ab  call    _CxxThrowException_0
0x18004d1b1  mov     eax, [rcx+8]
0x18004d1b4  cmp     eax, 3
0x18004d1b7  jz      short loc_18004D21E
0x18004d1b9  mov     eax, [rcx+8]
0x18004d1bc  cmp     eax, 4
0x18004d1bf  jz      short loc_18004D21E
0x18004d1c1  lea     rcx, [rbp+57h+pExceptionObject]; this
0x18004d1c5  call    ??0task_options@pplx@@QEAA@XZ; pplx::task_options::task_options(void)
0x18004d1ca  mov     r9, rax
0x18004d1cd  lea     rdx, [rbp+57h+var_C8]
0x18004d1d1  lea     rcx, [rsp+100h+var_D8]
0x18004d1d6  call    ??$?0U?$_Task_impl@UOnlineServiceResponse@BingOnlineServices@@@details@pplx@@$0A@@?$shared_ptr@U_Task_impl_base@details@pplx@@@std@@QEAA@AEBV?$shared_ptr@U?$_Task_impl@UOnlineServiceResponse@BingOnlineServices@@@details@pplx@@@1@@Z; std::shared_ptr<pplx::details::_Task_impl_base>::shared_ptr<pplx::details::_Task_impl_base>(std::shared_ptr<pplx::details::_Task_impl<BingOnlineServices::OnlineServiceResponse>> const &)
0x18004d1db  nop
0x18004d1dc  lea     r8, [rsp+100h+var_D8]
0x18004d1e1  lea     rdx, [rbp+57h+var_B8]
0x18004d1e5  mov     rcx, rdi
0x18004d1e8  call    ??$then@V_lambda_f0d76877e2124af93dd5e09c8d041edf_@@@?$task@X@pplx@@QEBA?AV01@AEBV_lambda_f0d76877e2124af93dd5e09c8d041edf_@@Vtask_options@1@@Z; pplx::task<void>::then<_lambda_f0d76877e2124af93dd5e09c8d041edf_>(_lambda_f0d76877e2124af93dd5e09c8d041edf_ const &,pplx::task_options)
0x18004d1ed  cmp     rdi, rax
0x18004d1f0  jz      short loc_18004D1FD
0x18004d1f2  mov     rdx, rax
0x18004d1f5  mov     rcx, rdi
0x18004d1f8  call    ??4?$shared_ptr@U_ExceptionHolder@details@pplx@@@std@@QEAAAEAV01@$$QEAV01@@Z; std::shared_ptr<pplx::details::_ExceptionHolder>::operator=(std::shared_ptr<pplx::details::_ExceptionHolder> &&)
0x18004d1fd  lea     rcx, [rbp+57h+var_B8]; void *
0x18004d201  call    ??1?$task@J@pplx@@QEAA@XZ; pplx::task<long>::~task<long>(void)
0x18004d206  nop
0x18004d207  mov     rcx, [rbp+57h+var_D0]; this
0x18004d20b  test    rcx, rcx
0x18004d20e  jz      loc_18004D2B0
0x18004d214  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18004d219  jmp     loc_18004D2B0
0x18004d21e  mov     rax, [rbx]
0x18004d221  lea     rdx, [rbp+57h+var_80]
0x18004d225  mov     rcx, rbx
0x18004d228  mov     rax, [rax+180h]
0x18004d22f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004d234  mov     rbx, rax
0x18004d237  lea     rcx, [rbp+57h+pExceptionObject]; this
0x18004d23b  call    ??0task_options@pplx@@QEAA@XZ; pplx::task_options::task_options(void)
0x18004d240  mov     r9, rax
0x18004d243  lea     rdx, [rbp+57h+var_C8]
0x18004d247  lea     rcx, [rsp+100h+var_D8]
0x18004d24c  call    ??$?0U?$_Task_impl@UOnlineServiceResponse@BingOnlineServices@@@details@pplx@@$0A@@?$shared_ptr@U_Task_impl_base@details@pplx@@@std@@QEAA@AEBV?$shared_ptr@U?$_Task_impl@UOnlineServiceResponse@BingOnlineServices@@@details@pplx@@@1@@Z; std::shared_ptr<pplx::details::_Task_impl_base>::shared_ptr<pplx::details::_Task_impl_base>(std::shared_ptr<pplx::details::_Task_impl<BingOnlineServices::OnlineServiceResponse>> const &)
0x18004d251  nop
0x18004d252  lea     r8, [rsp+100h+var_D8]
0x18004d257  lea     rdx, [rbp+57h+var_90]
0x18004d25b  mov     rcx, rbx
0x18004d25e  call    ??$then@V_lambda_89ef8f9e192d0c9d8a44552b2fb585d9_@@@?$task@X@pplx@@QEBA?AV01@AEBV_lambda_89ef8f9e192d0c9d8a44552b2fb585d9_@@Vtask_options@1@@Z; pplx::task<void>::then<_lambda_89ef8f9e192d0c9d8a44552b2fb585d9_>(_lambda_89ef8f9e192d0c9d8a44552b2fb585d9_ const &,pplx::task_options)
0x18004d263  nop
0x18004d264  mov     r8, rax
0x18004d267  mov     rdx, rdi
0x18004d26a  lea     rcx, [rbp+57h+var_B8]
0x18004d26e  call    ??Vpplx@@YA?AV?$task@X@0@AEBV10@0@Z; pplx::operator&&(pplx::task<void> const &,pplx::task<void> const &)
0x18004d273  cmp     rdi, rax
0x18004d276  jz      short loc_18004D283
0x18004d278  mov     rdx, rax
0x18004d27b  mov     rcx, rdi
0x18004d27e  call    ??4?$shared_ptr@U_ExceptionHolder@details@pplx@@@std@@QEAAAEAV01@$$QEAV01@@Z; std::shared_ptr<pplx::details::_ExceptionHolder>::operator=(std::shared_ptr<pplx::details::_ExceptionHolder> &&)
0x18004d283  lea     rcx, [rbp+57h+var_B8]; void *
0x18004d287  call    ??1?$task@J@pplx@@QEAA@XZ; pplx::task<long>::~task<long>(void)
0x18004d28c  nop
0x18004d28d  lea     rcx, [rbp+57h+var_90]; void *
0x18004d291  call    ??1?$task@J@pplx@@QEAA@XZ; pplx::task<long>::~task<long>(void)
0x18004d296  nop
0x18004d297  mov     rcx, [rbp+57h+var_D0]; this
0x18004d29b  test    rcx, rcx
0x18004d29e  jz      short loc_18004D2A6
0x18004d2a0  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18004d2a5  nop
0x18004d2a6  lea     rcx, [rbp+57h+var_80]; void *
0x18004d2aa  call    ??1?$task@J@pplx@@QEAA@XZ; pplx::task<long>::~task<long>(void)
0x18004d2af  nop
0x18004d2b0  test    rsi, rsi
0x18004d2b3  jz      short loc_18004D2BD
0x18004d2b5  mov     rcx, rsi; this
0x18004d2b8  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18004d2bd  mov     rax, rdi
0x18004d2c0  mov     rcx, [rbp+57h+var_18]
0x18004d2c4  xor     rcx, rsp; StackCookie
0x18004d2c7  call    __security_check_cookie
0x18004d2cc  lea     r11, [rsp+100h+var_10]
0x18004d2d4  mov     rbx, [r11+30h]
0x18004d2d8  mov     rsi, [r11+38h]
0x18004d2dc  mov     rsp, r11
0x18004d2df  pop     r14
0x18004d2e1  pop     rdi
0x18004d2e2  pop     rbp
0x18004d2e3  retn
```
