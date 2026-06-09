# Concurrency::streams::details::streambuf_state_manager<uchar>::create_exception_checked_task<long>(pplx::task<long>,std::function<bool (long)>,int)

- ea: `0x180022528`
- end: `0x1800226a0`
- name: `??$create_exception_checked_task@J@?$streambuf_state_manager@E@details@streams@Concurrency@@AEAA?AV?$task@J@pplx@@V45@V?$function@$$A6A_NJ@Z@std@@H@Z`
- size: `376`
- prototype: `__int64 __fastcall(__int64, __int64, __int64 *, __int64 *)`
- caller_count: `5`
- callee_count: `12`
- tags: `service_task`

## callers

- `0x18002be80`
- `0x18002df40`
- `0x18002ed50`
- `0x18002f0a0`
- `0x180030710`

## callees

- `0x180004fa0`
- `0x180005e9c`
- `0x18000fa74`
- `0x180011a14`
- `0x180012034`
- `0x1800148ac`
- `0x180022528`
- `0x1800239b4`
- `0x180024994`
- `0x180025a50`
- `0x1800303c0`
- `0x18005f010`

## string_xrefs

- `0x18002259a`: `is_done() cannot be called on a default constructed task.`

## pseudocode

```c
// Hidden C++ exception states: #wind=7
__int64 __fastcall Concurrency::streams::details::streambuf_state_manager<unsigned char>::create_exception_checked_task<long>(
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
    _lambda_c00d281dd57b62ac6d8c9c32b58cbda5_::operator()(v18, a2, v14);
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
    pplx::task<long>::then<_lambda_c00d281dd57b62ac6d8c9c32b58cbda5_>(a3, a2, v18);
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
0x180022528  push    rbp
0x18002252a  push    rbx
0x18002252b  push    rsi
0x18002252c  push    rdi
0x18002252d  lea     rbp, [rsp-8]
0x180022532  sub     rsp, 108h
0x180022539  mov     rax, cs:__security_cookie
0x180022540  xor     rax, rsp
0x180022543  mov     [rbp+20h+var_28], rax
0x180022547  mov     rbx, r9
0x18002254a  mov     rdi, r8
0x18002254d  mov     rsi, rdx
0x180022550  mov     [rsp+120h+var_F8], rdx
0x180022555  mov     [rsp+120h+var_F8], r8
0x18002255a  mov     [rsp+120h+var_D0], rbx
0x18002255f  add     rcx, 8
0x180022563  lea     rdx, [rsp+120h+var_E0]
0x180022568  call    ?shared_from_this@?$enable_shared_from_this@V?$streambuf_state_manager@E@details@streams@Concurrency@@@std@@QEAA?AV?$shared_ptr@V?$streambuf_state_manager@E@details@streams@Concurrency@@@2@XZ; std::enable_shared_from_this<Concurrency::streams::details::streambuf_state_manager<uchar>>::shared_from_this(void)
0x18002256d  nop
0x18002256e  lea     rdx, [rsp+120h+var_E0]
0x180022573  lea     rcx, [rsp+120h+var_C0]
0x180022578  call    ??$?0U?$_Task_impl@UOnlineServiceResponse@BingOnlineServices@@@details@pplx@@$0A@@?$shared_ptr@U_Task_impl_base@details@pplx@@@std@@QEAA@AEBV?$shared_ptr@U?$_Task_impl@UOnlineServiceResponse@BingOnlineServices@@@details@pplx@@@1@@Z; std::shared_ptr<pplx::details::_Task_impl_base>::shared_ptr<pplx::details::_Task_impl_base>(std::shared_ptr<pplx::details::_Task_impl<BingOnlineServices::OnlineServiceResponse>> const &)
0x18002257d  nop
0x18002257e  mov     rdx, rbx
0x180022581  lea     rcx, [rsp+120h+var_B0]
0x180022586  call    ??0?$function@$$A6AXV?$task@J@pplx@@@Z@std@@QEAA@AEBV01@@Z; std::function<void (pplx::task<long>)>::function<void (pplx::task<long>)>(std::function<void (pplx::task<long>)> const &)
0x18002258b  mov     [rbp+20h+var_70], 3
0x180022592  mov     rcx, [rdi]
0x180022595  test    rcx, rcx
0x180022598  jnz     short loc_1800225BB
0x18002259a  lea     rdx, aIsDoneCannotBe; "is_done() cannot be called on a default"...
0x1800225a1  lea     rcx, [rbp+20h+pExceptionObject]; this
0x1800225a5  call    ??0invalid_operation@pplx@@QEAA@PEBD@Z; pplx::invalid_operation::invalid_operation(char const *)
0x1800225aa  lea     rdx, _TI2?AVinvalid_operation@pplx@@; pThrowInfo
0x1800225b1  lea     rcx, [rbp+20h+pExceptionObject]; pExceptionObject
0x1800225b5  call    _CxxThrowException_0
0x1800225bb  mov     eax, [rcx+8]
0x1800225be  cmp     eax, 3
0x1800225c1  jz      short loc_180022618
0x1800225c3  mov     eax, [rcx+8]
0x1800225c6  cmp     eax, 4
0x1800225c9  jz      short loc_180022618
0x1800225cb  lea     r8, [rsp+120h+var_C0]
0x1800225d0  mov     rdx, rsi
0x1800225d3  mov     rcx, rdi
0x1800225d6  call    ??$then@V_lambda_c00d281dd57b62ac6d8c9c32b58cbda5_@@@?$task@J@pplx@@QEBA?AV01@AEBV_lambda_c00d281dd57b62ac6d8c9c32b58cbda5_@@@Z; pplx::task<long>::then<_lambda_c00d281dd57b62ac6d8c9c32b58cbda5_>(_lambda_c00d281dd57b62ac6d8c9c32b58cbda5_ const &)
0x1800225db  nop
0x1800225dc  lea     rcx, [rsp+120h+var_C0]; this
0x1800225e1  call    ??1_lambda_13d4a3afe64463a7e188b8e74574abbc_@@QEAA@XZ; _lambda_13d4a3afe64463a7e188b8e74574abbc_::~_lambda_13d4a3afe64463a7e188b8e74574abbc_(void)
0x1800225e6  nop
0x1800225e7  mov     rcx, [rsp+120h+var_D8]; this
0x1800225ec  test    rcx, rcx
0x1800225ef  jz      short loc_1800225F7
0x1800225f1  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x1800225f6  nop
0x1800225f7  mov     rcx, [rdi+8]; this
0x1800225fb  test    rcx, rcx
0x1800225fe  jz      short loc_180022606
0x180022600  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x180022605  nop
0x180022606  mov     rcx, [rbx+38h]
0x18002260a  test    rcx, rcx
0x18002260d  jz      short loc_180022685
0x18002260f  mov     rax, [rcx]
0x180022612  mov     rax, [rax+20h]
0x180022616  jmp     short loc_180022672
0x180022618  mov     rdx, rdi
0x18002261b  lea     rcx, [rsp+120h+var_F0]
0x180022620  call    ??$?0U?$_Task_impl@UOnlineServiceResponse@BingOnlineServices@@@details@pplx@@$0A@@?$shared_ptr@U_Task_impl_base@details@pplx@@@std@@QEAA@AEBV?$shared_ptr@U?$_Task_impl@UOnlineServiceResponse@BingOnlineServices@@@details@pplx@@@1@@Z; std::shared_ptr<pplx::details::_Task_impl_base>::shared_ptr<pplx::details::_Task_impl_base>(std::shared_ptr<pplx::details::_Task_impl<BingOnlineServices::OnlineServiceResponse>> const &)
0x180022625  lea     r8, [rsp+120h+var_F0]
0x18002262a  mov     rdx, rsi
0x18002262d  lea     rcx, [rsp+120h+var_C0]
0x180022632  call    ??R_lambda_c00d281dd57b62ac6d8c9c32b58cbda5_@@QEBA?AV?$task@J@pplx@@V12@@Z; _lambda_c00d281dd57b62ac6d8c9c32b58cbda5_::operator()(pplx::task<long>)
0x180022637  nop
0x180022638  lea     rcx, [rsp+120h+var_C0]; this
0x18002263d  call    ??1_lambda_13d4a3afe64463a7e188b8e74574abbc_@@QEAA@XZ; _lambda_13d4a3afe64463a7e188b8e74574abbc_::~_lambda_13d4a3afe64463a7e188b8e74574abbc_(void)
0x180022642  nop
0x180022643  mov     rcx, [rsp+120h+var_D8]; this
0x180022648  test    rcx, rcx
0x18002264b  jz      short loc_180022653
0x18002264d  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x180022652  nop
0x180022653  mov     rcx, [rdi+8]; this
0x180022657  test    rcx, rcx
0x18002265a  jz      short loc_180022662
0x18002265c  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x180022661  nop
0x180022662  mov     rcx, [rbx+38h]
0x180022666  test    rcx, rcx
0x180022669  jz      short loc_180022685
0x18002266b  mov     rdx, [rcx]
0x18002266e  mov     rax, [rdx+20h]
0x180022672  cmp     rcx, rbx
0x180022675  setnz   dl
0x180022678  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002267d  mov     qword ptr [rbx+38h], 0
0x180022685  mov     rax, rsi
0x180022688  mov     rcx, [rbp+20h+var_28]
0x18002268c  xor     rcx, rsp; StackCookie
0x18002268f  call    __security_check_cookie
0x180022694  add     rsp, 108h
0x18002269b  pop     rdi
0x18002269c  pop     rsi
0x18002269d  pop     rbx
0x18002269e  pop     rbp
0x18002269f  retn
```
