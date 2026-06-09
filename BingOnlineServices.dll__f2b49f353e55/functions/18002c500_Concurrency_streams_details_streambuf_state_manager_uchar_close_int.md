# Concurrency::streams::details::streambuf_state_manager<uchar>::close(int)

- ea: `0x18002c500`
- end: `0x18002c765`
- name: `?close@?$streambuf_state_manager@E@details@streams@Concurrency@@UEAA?AV?$task@X@pplx@@H@Z`
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
- `0x1800237d0`
- `0x180023a64`
- `0x1800260e8`
- `0x18002c500`
- `0x1800303c0`
- `0x1800305f8`
- `0x18005f010`

## string_xrefs

- `0x18002c610`: `is_done() cannot be called on a default constructed task.`

## pseudocode

```c
// Hidden C++ exception states: #wind=7
_QWORD *__fastcall Concurrency::streams::details::streambuf_state_manager<unsigned char>::close(
        __int64 a1,
        _QWORD *a2,
        char a3)
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
      v13 = pplx::task<void>::then<_lambda_68eafabd67f4932b8e9918fb0693cf42_>(v12, v23, &v16);
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
      v11 = pplx::task<void>::then<_lambda_d02101470ff44e04543297f88e5e8cbe_>(a2, v19, &v16);
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
0x18002c500  mov     [rsp-8+arg_10], rbx
0x18002c505  mov     [rsp-8+arg_18], rsi
0x18002c50a  push    rbp
0x18002c50b  push    rdi
0x18002c50c  push    r14
0x18002c50e  lea     rbp, [rsp-47h]
0x18002c513  sub     rsp, 0F0h
0x18002c51a  mov     rax, cs:__security_cookie
0x18002c521  xor     rax, rsp
0x18002c524  mov     [rbp+57h+var_18], rax
0x18002c528  mov     r14d, r8d
0x18002c52b  mov     rdi, rdx
0x18002c52e  mov     rbx, rcx
0x18002c531  mov     [rbp+57h+var_A8], rdx
0x18002c535  mov     [rsp+100h+var_E0], 0
0x18002c53d  lea     rcx, [rbp+57h+pExceptionObject]; this
0x18002c541  call    ??0task_options@pplx@@QEAA@XZ; pplx::task_options::task_options(void)
0x18002c546  nop
0x18002c547  mov     rdx, rax
0x18002c54a  mov     rcx, rdi
0x18002c54d  call    ?task_from_result@pplx@@YA?AV?$task@X@1@AEBVtask_options@1@@Z; pplx::task_from_result(pplx::task_options const &)
0x18002c552  mov     [rsp+100h+var_E0], 1
0x18002c55a  lea     rcx, [rbp+57h+pExceptionObject]; this
0x18002c55e  call    ??1task_options@pplx@@QEAA@XZ; pplx::task_options::~task_options(void)
0x18002c563  test    r14b, 1
0x18002c567  jz      short loc_18002C5AB
0x18002c569  mov     rax, [rbx]
0x18002c56c  mov     rcx, rbx
0x18002c56f  mov     rax, [rax+8]
0x18002c573  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002c578  test    al, al
0x18002c57a  jz      short loc_18002C5AB
0x18002c57c  mov     rax, [rbx]
0x18002c57f  lea     rdx, [rbp+57h+var_C8]
0x18002c583  mov     rcx, rbx
0x18002c586  mov     rax, [rax+178h]
0x18002c58d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002c592  cmp     rdi, rax
0x18002c595  jz      short loc_18002C5A2
0x18002c597  mov     rdx, rax
0x18002c59a  mov     rcx, rdi
0x18002c59d  call    ??4?$shared_ptr@U_ExceptionHolder@details@pplx@@@std@@QEAAAEAV01@$$QEAV01@@Z; std::shared_ptr<pplx::details::_ExceptionHolder>::operator=(std::shared_ptr<pplx::details::_ExceptionHolder> &&)
0x18002c5a2  lea     rcx, [rbp+57h+var_C8]; void *
0x18002c5a6  call    ??1?$task@J@pplx@@QEAA@XZ; pplx::task<long>::~task<long>(void)
0x18002c5ab  lea     rcx, [rbx+8]
0x18002c5af  lea     rdx, [rbp+57h+var_A0]
0x18002c5b3  call    ?shared_from_this@?$enable_shared_from_this@V?$streambuf_state_manager@E@details@streams@Concurrency@@@std@@QEAA?AV?$shared_ptr@V?$streambuf_state_manager@E@details@streams@Concurrency@@@2@XZ; std::enable_shared_from_this<Concurrency::streams::details::streambuf_state_manager<uchar>>::shared_from_this(void)
0x18002c5b8  mov     rcx, rax
0x18002c5bb  mov     rax, [rax]
0x18002c5be  mov     [rbp+57h+var_C8], rax
0x18002c5c2  mov     rsi, [rcx+8]
0x18002c5c6  mov     [rbp+57h+var_C0], rsi
0x18002c5ca  mov     qword ptr [rcx], 0
0x18002c5d1  mov     qword ptr [rcx+8], 0
0x18002c5d9  mov     rcx, [rbp+57h+var_98]; this
0x18002c5dd  test    rcx, rcx
0x18002c5e0  jz      short loc_18002C5E7
0x18002c5e2  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18002c5e7  test    r14b, 2
0x18002c5eb  jz      loc_18002C730
0x18002c5f1  mov     rax, [rbx]
0x18002c5f4  mov     rcx, rbx
0x18002c5f7  mov     rax, [rax+10h]
0x18002c5fb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002c600  test    al, al
0x18002c602  jz      loc_18002C730
0x18002c608  mov     rcx, [rdi]
0x18002c60b  test    rcx, rcx
0x18002c60e  jnz     short loc_18002C631
0x18002c610  lea     rdx, aIsDoneCannotBe; "is_done() cannot be called on a default"...
0x18002c617  lea     rcx, [rbp+57h+pExceptionObject]; this
0x18002c61b  call    ??0invalid_operation@pplx@@QEAA@PEBD@Z; pplx::invalid_operation::invalid_operation(char const *)
0x18002c620  lea     rdx, _TI2?AVinvalid_operation@pplx@@; pThrowInfo
0x18002c627  lea     rcx, [rbp+57h+pExceptionObject]; pExceptionObject
0x18002c62b  call    _CxxThrowException_0
0x18002c631  mov     eax, [rcx+8]
0x18002c634  cmp     eax, 3
0x18002c637  jz      short loc_18002C69E
0x18002c639  mov     eax, [rcx+8]
0x18002c63c  cmp     eax, 4
0x18002c63f  jz      short loc_18002C69E
0x18002c641  lea     rcx, [rbp+57h+pExceptionObject]; this
0x18002c645  call    ??0task_options@pplx@@QEAA@XZ; pplx::task_options::task_options(void)
0x18002c64a  mov     r9, rax
0x18002c64d  lea     rdx, [rbp+57h+var_C8]
0x18002c651  lea     rcx, [rsp+100h+var_D8]
0x18002c656  call    ??$?0U?$_Task_impl@UOnlineServiceResponse@BingOnlineServices@@@details@pplx@@$0A@@?$shared_ptr@U_Task_impl_base@details@pplx@@@std@@QEAA@AEBV?$shared_ptr@U?$_Task_impl@UOnlineServiceResponse@BingOnlineServices@@@details@pplx@@@1@@Z; std::shared_ptr<pplx::details::_Task_impl_base>::shared_ptr<pplx::details::_Task_impl_base>(std::shared_ptr<pplx::details::_Task_impl<BingOnlineServices::OnlineServiceResponse>> const &)
0x18002c65b  nop
0x18002c65c  lea     r8, [rsp+100h+var_D8]
0x18002c661  lea     rdx, [rbp+57h+var_B8]
0x18002c665  mov     rcx, rdi
0x18002c668  call    ??$then@V_lambda_d02101470ff44e04543297f88e5e8cbe_@@@?$task@X@pplx@@QEBA?AV01@AEBV_lambda_d02101470ff44e04543297f88e5e8cbe_@@Vtask_options@1@@Z; pplx::task<void>::then<_lambda_d02101470ff44e04543297f88e5e8cbe_>(_lambda_d02101470ff44e04543297f88e5e8cbe_ const &,pplx::task_options)
0x18002c66d  cmp     rdi, rax
0x18002c670  jz      short loc_18002C67D
0x18002c672  mov     rdx, rax
0x18002c675  mov     rcx, rdi
0x18002c678  call    ??4?$shared_ptr@U_ExceptionHolder@details@pplx@@@std@@QEAAAEAV01@$$QEAV01@@Z; std::shared_ptr<pplx::details::_ExceptionHolder>::operator=(std::shared_ptr<pplx::details::_ExceptionHolder> &&)
0x18002c67d  lea     rcx, [rbp+57h+var_B8]; void *
0x18002c681  call    ??1?$task@J@pplx@@QEAA@XZ; pplx::task<long>::~task<long>(void)
0x18002c686  nop
0x18002c687  mov     rcx, [rbp+57h+var_D0]; this
0x18002c68b  test    rcx, rcx
0x18002c68e  jz      loc_18002C730
0x18002c694  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18002c699  jmp     loc_18002C730
0x18002c69e  mov     rax, [rbx]
0x18002c6a1  lea     rdx, [rbp+57h+var_80]
0x18002c6a5  mov     rcx, rbx
0x18002c6a8  mov     rax, [rax+180h]
0x18002c6af  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002c6b4  mov     rbx, rax
0x18002c6b7  lea     rcx, [rbp+57h+pExceptionObject]; this
0x18002c6bb  call    ??0task_options@pplx@@QEAA@XZ; pplx::task_options::task_options(void)
0x18002c6c0  mov     r9, rax
0x18002c6c3  lea     rdx, [rbp+57h+var_C8]
0x18002c6c7  lea     rcx, [rsp+100h+var_D8]
0x18002c6cc  call    ??$?0U?$_Task_impl@UOnlineServiceResponse@BingOnlineServices@@@details@pplx@@$0A@@?$shared_ptr@U_Task_impl_base@details@pplx@@@std@@QEAA@AEBV?$shared_ptr@U?$_Task_impl@UOnlineServiceResponse@BingOnlineServices@@@details@pplx@@@1@@Z; std::shared_ptr<pplx::details::_Task_impl_base>::shared_ptr<pplx::details::_Task_impl_base>(std::shared_ptr<pplx::details::_Task_impl<BingOnlineServices::OnlineServiceResponse>> const &)
0x18002c6d1  nop
0x18002c6d2  lea     r8, [rsp+100h+var_D8]
0x18002c6d7  lea     rdx, [rbp+57h+var_90]
0x18002c6db  mov     rcx, rbx
0x18002c6de  call    ??$then@V_lambda_68eafabd67f4932b8e9918fb0693cf42_@@@?$task@X@pplx@@QEBA?AV01@AEBV_lambda_68eafabd67f4932b8e9918fb0693cf42_@@Vtask_options@1@@Z; pplx::task<void>::then<_lambda_68eafabd67f4932b8e9918fb0693cf42_>(_lambda_68eafabd67f4932b8e9918fb0693cf42_ const &,pplx::task_options)
0x18002c6e3  nop
0x18002c6e4  mov     r8, rax
0x18002c6e7  mov     rdx, rdi
0x18002c6ea  lea     rcx, [rbp+57h+var_B8]
0x18002c6ee  call    ??Vpplx@@YA?AV?$task@X@0@AEBV10@0@Z; pplx::operator&&(pplx::task<void> const &,pplx::task<void> const &)
0x18002c6f3  cmp     rdi, rax
0x18002c6f6  jz      short loc_18002C703
0x18002c6f8  mov     rdx, rax
0x18002c6fb  mov     rcx, rdi
0x18002c6fe  call    ??4?$shared_ptr@U_ExceptionHolder@details@pplx@@@std@@QEAAAEAV01@$$QEAV01@@Z; std::shared_ptr<pplx::details::_ExceptionHolder>::operator=(std::shared_ptr<pplx::details::_ExceptionHolder> &&)
0x18002c703  lea     rcx, [rbp+57h+var_B8]; void *
0x18002c707  call    ??1?$task@J@pplx@@QEAA@XZ; pplx::task<long>::~task<long>(void)
0x18002c70c  nop
0x18002c70d  lea     rcx, [rbp+57h+var_90]; void *
0x18002c711  call    ??1?$task@J@pplx@@QEAA@XZ; pplx::task<long>::~task<long>(void)
0x18002c716  nop
0x18002c717  mov     rcx, [rbp+57h+var_D0]; this
0x18002c71b  test    rcx, rcx
0x18002c71e  jz      short loc_18002C726
0x18002c720  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18002c725  nop
0x18002c726  lea     rcx, [rbp+57h+var_80]; void *
0x18002c72a  call    ??1?$task@J@pplx@@QEAA@XZ; pplx::task<long>::~task<long>(void)
0x18002c72f  nop
0x18002c730  test    rsi, rsi
0x18002c733  jz      short loc_18002C73D
0x18002c735  mov     rcx, rsi; this
0x18002c738  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18002c73d  mov     rax, rdi
0x18002c740  mov     rcx, [rbp+57h+var_18]
0x18002c744  xor     rcx, rsp; StackCookie
0x18002c747  call    __security_check_cookie
0x18002c74c  lea     r11, [rsp+100h+var_10]
0x18002c754  mov     rbx, [r11+30h]
0x18002c758  mov     rsi, [r11+38h]
0x18002c75c  mov     rsp, r11
0x18002c75f  pop     r14
0x18002c761  pop     rdi
0x18002c762  pop     rbp
0x18002c763  retn
```
