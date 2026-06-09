# Concurrency::streams::details::streambuf_state_manager<char>::create_exception_checked_task<int>(pplx::task<int>,std::function<bool (int)>,int)

- ea: `0x180046b30`
- end: `0x180046ca8`
- name: `??$create_exception_checked_task@H@?$streambuf_state_manager@D@details@streams@Concurrency@@AEAA?AV?$task@H@pplx@@V45@V?$function@$$A6A_NH@Z@std@@H@Z`
- size: `376`
- prototype: `__int64 __fastcall(__int64, __int64, __int64 *, __int64 *)`
- caller_count: `5`
- callee_count: `12`
- tags: `service_task`

## callers

- `0x18004cfd0`
- `0x18004d5a0`
- `0x18004dd30`
- `0x18004de20`
- `0x18004e930`

## callees

- `0x180004fa0`
- `0x180005e9c`
- `0x18000fa74`
- `0x180011a14`
- `0x180012034`
- `0x1800148ac`
- `0x180024994`
- `0x1800303c0`
- `0x180046b30`
- `0x180047820`
- `0x180048b68`
- `0x18005f010`

## string_xrefs

- `0x180046ba2`: `is_done() cannot be called on a default constructed task.`

## pseudocode

```c
// Hidden C++ exception states: #wind=7
__int64 __fastcall Concurrency::streams::details::streambuf_state_manager<char>::create_exception_checked_task<int>(
        __int64 a1,
        __int64 a2,
        __int64 *a3,
        __int64 *a4)
{
  __int64 v7; // rcx
  __int64 v8; // rdx
  std::_Ref_count_base *v9; // rcx
  __int64 *v10; // rcx
  void (__fastcall *v11)(__int64 *, __int64); // rax
  std::_Ref_count_base *v12; // rcx
  _QWORD v14[2]; // [rsp+30h] [rbp-D0h] BYREF
  __int64 v15; // [rsp+40h] [rbp-C0h] BYREF
  std::_Ref_count_base *v16; // [rsp+48h] [rbp-B8h]
  __int64 *v17; // [rsp+50h] [rbp-B0h]
  _QWORD v18[2]; // [rsp+60h] [rbp-A0h] BYREF
  _BYTE v19[64]; // [rsp+70h] [rbp-90h] BYREF
  int v20; // [rsp+B0h] [rbp-50h]
  _BYTE pExceptionObject[56]; // [rsp+C0h] [rbp-40h] BYREF

  v17 = a4;
  std::enable_shared_from_this<Concurrency::streams::details::streambuf_state_manager<unsigned char>>::shared_from_this(
    a1 + 8,
    &v15);
  std::shared_ptr<pplx::details::_Task_impl_base>::shared_ptr<pplx::details::_Task_impl_base>(v18, &v15);
  std::function<void (pplx::task<long>)>::function<void (pplx::task<long>)>(v19);
  v20 = 3;
  v7 = *a3;
  if ( !*a3 )
  {
    pplx::invalid_operation::invalid_operation(
      (pplx::invalid_operation *)pExceptionObject,
      "is_done() cannot be called on a default constructed task.");
    throw (pplx::invalid_operation *)pExceptionObject;
  }
  if ( *(_DWORD *)(v7 + 8) == 3 || *(_DWORD *)(v7 + 8) == 4 )
  {
    std::shared_ptr<pplx::details::_Task_impl_base>::shared_ptr<pplx::details::_Task_impl_base>(v14, a3);
    _lambda_c6fdc32eb2a049594b0072a7c2a28a63_::operator()(v18, a2, v14);
    _lambda_13d4a3afe64463a7e188b8e74574abbc_::~_lambda_13d4a3afe64463a7e188b8e74574abbc_((_lambda_13d4a3afe64463a7e188b8e74574abbc_ *)v18);
    if ( v16 )
      std::_Ref_count_base::_Decref(v16);
    v12 = (std::_Ref_count_base *)a3[1];
    if ( v12 )
      std::_Ref_count_base::_Decref(v12);
    v10 = (__int64 *)a4[7];
    if ( v10 )
    {
      v8 = *v10;
      v11 = *(void (__fastcall **)(__int64 *, __int64))(*v10 + 32);
      goto LABEL_17;
    }
  }
  else
  {
    pplx::task<int>::then<_lambda_c6fdc32eb2a049594b0072a7c2a28a63_>(a3, a2, v18);
    _lambda_13d4a3afe64463a7e188b8e74574abbc_::~_lambda_13d4a3afe64463a7e188b8e74574abbc_((_lambda_13d4a3afe64463a7e188b8e74574abbc_ *)v18);
    if ( v16 )
      std::_Ref_count_base::_Decref(v16);
    v9 = (std::_Ref_count_base *)a3[1];
    if ( v9 )
      std::_Ref_count_base::_Decref(v9);
    v10 = (__int64 *)a4[7];
    if ( v10 )
    {
      v11 = *(void (__fastcall **)(__int64 *, __int64))(*v10 + 32);
LABEL_17:
      LOBYTE(v8) = v10 != a4;
      v11(v10, v8);
      a4[7] = 0;
    }
  }
  return a2;
}

```

## disassembly

```asm
0x180046b30  push    rbp
0x180046b32  push    rbx
0x180046b33  push    rsi
0x180046b34  push    rdi
0x180046b35  lea     rbp, [rsp-8]
0x180046b3a  sub     rsp, 108h
0x180046b41  mov     rax, cs:__security_cookie
0x180046b48  xor     rax, rsp
0x180046b4b  mov     [rbp+20h+var_28], rax
0x180046b4f  mov     rbx, r9
0x180046b52  mov     rdi, r8
0x180046b55  mov     rsi, rdx
0x180046b58  mov     [rsp+120h+var_F8], rdx
0x180046b5d  mov     [rsp+120h+var_F8], r8
0x180046b62  mov     [rsp+120h+var_D0], rbx
0x180046b67  add     rcx, 8
0x180046b6b  lea     rdx, [rsp+120h+var_E0]
0x180046b70  call    ?shared_from_this@?$enable_shared_from_this@V?$streambuf_state_manager@E@details@streams@Concurrency@@@std@@QEAA?AV?$shared_ptr@V?$streambuf_state_manager@E@details@streams@Concurrency@@@2@XZ; std::enable_shared_from_this<Concurrency::streams::details::streambuf_state_manager<uchar>>::shared_from_this(void)
0x180046b75  nop
0x180046b76  lea     rdx, [rsp+120h+var_E0]
0x180046b7b  lea     rcx, [rsp+120h+var_C0]
0x180046b80  call    ??$?0U?$_Task_impl@UOnlineServiceResponse@BingOnlineServices@@@details@pplx@@$0A@@?$shared_ptr@U_Task_impl_base@details@pplx@@@std@@QEAA@AEBV?$shared_ptr@U?$_Task_impl@UOnlineServiceResponse@BingOnlineServices@@@details@pplx@@@1@@Z; std::shared_ptr<pplx::details::_Task_impl_base>::shared_ptr<pplx::details::_Task_impl_base>(std::shared_ptr<pplx::details::_Task_impl<BingOnlineServices::OnlineServiceResponse>> const &)
0x180046b85  nop
0x180046b86  mov     rdx, rbx
0x180046b89  lea     rcx, [rsp+120h+var_B0]
0x180046b8e  call    ??0?$function@$$A6AXV?$task@J@pplx@@@Z@std@@QEAA@AEBV01@@Z; std::function<void (pplx::task<long>)>::function<void (pplx::task<long>)>(std::function<void (pplx::task<long>)> const &)
0x180046b93  mov     [rbp+20h+var_70], 3
0x180046b9a  mov     rcx, [rdi]
0x180046b9d  test    rcx, rcx
0x180046ba0  jnz     short loc_180046BC3
0x180046ba2  lea     rdx, aIsDoneCannotBe; "is_done() cannot be called on a default"...
0x180046ba9  lea     rcx, [rbp+20h+pExceptionObject]; this
0x180046bad  call    ??0invalid_operation@pplx@@QEAA@PEBD@Z; pplx::invalid_operation::invalid_operation(char const *)
0x180046bb2  lea     rdx, _TI2?AVinvalid_operation@pplx@@; pThrowInfo
0x180046bb9  lea     rcx, [rbp+20h+pExceptionObject]; pExceptionObject
0x180046bbd  call    _CxxThrowException_0
0x180046bc3  mov     eax, [rcx+8]
0x180046bc6  cmp     eax, 3
0x180046bc9  jz      short loc_180046C20
0x180046bcb  mov     eax, [rcx+8]
0x180046bce  cmp     eax, 4
0x180046bd1  jz      short loc_180046C20
0x180046bd3  lea     r8, [rsp+120h+var_C0]
0x180046bd8  mov     rdx, rsi
0x180046bdb  mov     rcx, rdi
0x180046bde  call    ??$then@V_lambda_c6fdc32eb2a049594b0072a7c2a28a63_@@@?$task@H@pplx@@QEBA?AV01@AEBV_lambda_c6fdc32eb2a049594b0072a7c2a28a63_@@@Z; pplx::task<int>::then<_lambda_c6fdc32eb2a049594b0072a7c2a28a63_>(_lambda_c6fdc32eb2a049594b0072a7c2a28a63_ const &)
0x180046be3  nop
0x180046be4  lea     rcx, [rsp+120h+var_C0]; this
0x180046be9  call    ??1_lambda_13d4a3afe64463a7e188b8e74574abbc_@@QEAA@XZ; _lambda_13d4a3afe64463a7e188b8e74574abbc_::~_lambda_13d4a3afe64463a7e188b8e74574abbc_(void)
0x180046bee  nop
0x180046bef  mov     rcx, [rsp+120h+var_D8]; this
0x180046bf4  test    rcx, rcx
0x180046bf7  jz      short loc_180046BFF
0x180046bf9  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x180046bfe  nop
0x180046bff  mov     rcx, [rdi+8]; this
0x180046c03  test    rcx, rcx
0x180046c06  jz      short loc_180046C0E
0x180046c08  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x180046c0d  nop
0x180046c0e  mov     rcx, [rbx+38h]
0x180046c12  test    rcx, rcx
0x180046c15  jz      short loc_180046C8D
0x180046c17  mov     rax, [rcx]
0x180046c1a  mov     rax, [rax+20h]
0x180046c1e  jmp     short loc_180046C7A
0x180046c20  mov     rdx, rdi
0x180046c23  lea     rcx, [rsp+120h+var_F0]
0x180046c28  call    ??$?0U?$_Task_impl@UOnlineServiceResponse@BingOnlineServices@@@details@pplx@@$0A@@?$shared_ptr@U_Task_impl_base@details@pplx@@@std@@QEAA@AEBV?$shared_ptr@U?$_Task_impl@UOnlineServiceResponse@BingOnlineServices@@@details@pplx@@@1@@Z; std::shared_ptr<pplx::details::_Task_impl_base>::shared_ptr<pplx::details::_Task_impl_base>(std::shared_ptr<pplx::details::_Task_impl<BingOnlineServices::OnlineServiceResponse>> const &)
0x180046c2d  lea     r8, [rsp+120h+var_F0]
0x180046c32  mov     rdx, rsi
0x180046c35  lea     rcx, [rsp+120h+var_C0]
0x180046c3a  call    ??R_lambda_c6fdc32eb2a049594b0072a7c2a28a63_@@QEBA?AV?$task@H@pplx@@V12@@Z; _lambda_c6fdc32eb2a049594b0072a7c2a28a63_::operator()(pplx::task<int>)
0x180046c3f  nop
0x180046c40  lea     rcx, [rsp+120h+var_C0]; this
0x180046c45  call    ??1_lambda_13d4a3afe64463a7e188b8e74574abbc_@@QEAA@XZ; _lambda_13d4a3afe64463a7e188b8e74574abbc_::~_lambda_13d4a3afe64463a7e188b8e74574abbc_(void)
0x180046c4a  nop
0x180046c4b  mov     rcx, [rsp+120h+var_D8]; this
0x180046c50  test    rcx, rcx
0x180046c53  jz      short loc_180046C5B
0x180046c55  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x180046c5a  nop
0x180046c5b  mov     rcx, [rdi+8]; this
0x180046c5f  test    rcx, rcx
0x180046c62  jz      short loc_180046C6A
0x180046c64  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x180046c69  nop
0x180046c6a  mov     rcx, [rbx+38h]
0x180046c6e  test    rcx, rcx
0x180046c71  jz      short loc_180046C8D
0x180046c73  mov     rdx, [rcx]
0x180046c76  mov     rax, [rdx+20h]
0x180046c7a  cmp     rcx, rbx
0x180046c7d  setnz   dl
0x180046c80  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180046c85  mov     qword ptr [rbx+38h], 0
0x180046c8d  mov     rax, rsi
0x180046c90  mov     rcx, [rbp+20h+var_28]
0x180046c94  xor     rcx, rsp; StackCookie
0x180046c97  call    __security_check_cookie
0x180046c9c  add     rsp, 108h
0x180046ca3  pop     rdi
0x180046ca4  pop     rsi
0x180046ca5  pop     rbx
0x180046ca6  pop     rbp
0x180046ca7  retn
```
