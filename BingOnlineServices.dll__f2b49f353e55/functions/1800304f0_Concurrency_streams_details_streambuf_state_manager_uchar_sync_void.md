# Concurrency::streams::details::streambuf_state_manager<uchar>::sync(void)

- ea: `0x1800304f0`
- end: `0x1800305f1`
- name: `?sync@?$streambuf_state_manager@E@details@streams@Concurrency@@UEAA?AV?$task@X@pplx@@XZ`
- size: `257`
- prototype: ``
- caller_count: `0`
- callee_count: `9`
- tags: `service_task`

## callees

- `0x18001235c`
- `0x180012cc0`
- `0x1800148ac`
- `0x1800227ec`
- `0x1800231e8`
- `0x1800235fc`
- `0x1800304f0`
- `0x1800305f8`
- `0x18005f010`

## import_xrefs

- `msvcp_win!?__ExceptionPtrToBool@@YA_NPEBX@Z` at `0x180030521`
- `msvcp_win!?__ExceptionPtrToBool@@YA_NPEBX@Z` at `0x180030521`
- `msvcp_win!?__ExceptionPtrCopy@@YAXPEAXPEBX@Z` at `0x180030546`
- `msvcp_win!?__ExceptionPtrCopy@@YAXPEAXPEBX@Z` at `0x180030546`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
_QWORD *__fastcall Concurrency::streams::details::streambuf_state_manager<unsigned char>::sync(__int64 a1, _QWORD *a2)
{
  const void *v4; // rsi
  const struct pplx::task_options *v5; // rbx
  __int64 v6; // rax
  _QWORD *v7; // rax
  _QWORD *exception_checked; // rax
  __int128 v10; // [rsp+30h] [rbp-39h] BYREF
  _BYTE v11[8]; // [rsp+48h] [rbp-21h] BYREF
  std::_Ref_count_base *v12; // [rsp+50h] [rbp-19h]
  __int64 v13[13]; // [rsp+58h] [rbp-11h] BYREF

  if ( (*(unsigned __int8 (__fastcall **)(__int64))(*(_QWORD *)a1 + 16LL))(a1) )
  {
    v13[0] = (__int64)&std::_Func_impl_no_alloc<_lambda_df661cc4afe48d466781cfb5831923ba_,bool,bool>::`vftable';
    v13[7] = (__int64)v13;
    v7 = (_QWORD *)(*(__int64 (__fastcall **)(__int64, __int128 *))(*(_QWORD *)a1 + 352LL))(a1, &v10);
    exception_checked = (_QWORD *)Concurrency::streams::details::streambuf_state_manager<unsigned char>::create_exception_checked_task<bool>(
                                    a1,
                                    (__int64)v11,
                                    v7,
                                    v13);
    pplx::task<bool>::then<_lambda_08114761827faabe1bf84d934f9c06d0_>(exception_checked, (__int64)a2);
    if ( v12 )
      std::_Ref_count_base::_Decref(v12);
  }
  else
  {
    v4 = (const void *)(a1 + 24);
    if ( __ExceptionPtrToBool((const void *)(a1 + 24)) )
    {
      v5 = (const struct pplx::task_options *)pplx::task_options::task_options((pplx::task_options *)v13);
      v10 = 0;
      __ExceptionPtrCopy(&v10, v4);
      pplx::task_from_exception<void,std::exception_ptr>(a2, &v10, v5);
    }
    else
    {
      v6 = pplx::task_options::task_options((pplx::task_options *)v13);
      pplx::task_from_result(a2, v6);
    }
    pplx::task_options::~task_options((pplx::task_options *)v13);
  }
  return a2;
}

```

## disassembly

```asm
0x1800304f0  mov     [rsp-8+arg_8], rbx
0x1800304f5  push    rbp
0x1800304f6  push    rsi
0x1800304f7  push    rdi
0x1800304f8  lea     rbp, [rsp-47h]
0x1800304fd  sub     rsp, 0B0h
0x180030504  mov     rdi, rdx
0x180030507  mov     rbx, rcx
0x18003050a  mov     rax, [rcx]
0x18003050d  mov     rax, [rax+10h]
0x180030511  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180030516  test    al, al
0x180030518  jnz     short loc_18003057B
0x18003051a  lea     rsi, [rbx+18h]
0x18003051e  mov     rcx, rsi
0x180030521  call    cs:__imp_?__ExceptionPtrToBool@@YA_NPEBX@Z; __ExceptionPtrToBool(void const *)
0x180030527  lea     rcx, [rbp+57h+var_68]; this
0x18003052b  test    al, al
0x18003052d  jz      short loc_180030567
0x18003052f  call    ??0task_options@pplx@@QEAA@XZ; pplx::task_options::task_options(void)
0x180030534  mov     rbx, rax
0x180030537  xorps   xmm0, xmm0
0x18003053a  movdqu  [rbp+57h+var_90], xmm0
0x18003053f  mov     rdx, rsi
0x180030542  lea     rcx, [rbp+57h+var_90]
0x180030546  call    cs:__imp_?__ExceptionPtrCopy@@YAXPEAXPEBX@Z; __ExceptionPtrCopy(void *,void const *)
0x18003054c  mov     r8, rbx
0x18003054f  lea     rdx, [rbp+57h+var_90]
0x180030553  mov     rcx, rdi
0x180030556  call    ??$task_from_exception@XVexception_ptr@std@@@pplx@@YA?AV?$task@X@0@Vexception_ptr@std@@AEBVtask_options@0@@Z; pplx::task_from_exception<void,std::exception_ptr>(std::exception_ptr,pplx::task_options const &)
0x18003055b  nop
0x18003055c  lea     rcx, [rbp+57h+var_68]; this
0x180030560  call    ??1task_options@pplx@@QEAA@XZ; pplx::task_options::~task_options(void)
0x180030565  jmp     short loc_1800305DB
0x180030567  call    ??0task_options@pplx@@QEAA@XZ; pplx::task_options::task_options(void)
0x18003056c  nop
0x18003056d  mov     rdx, rax
0x180030570  mov     rcx, rdi
0x180030573  call    ?task_from_result@pplx@@YA?AV?$task@X@1@AEBVtask_options@1@@Z; pplx::task_from_result(pplx::task_options const &)
0x180030578  nop
0x180030579  jmp     short loc_18003055C
0x18003057b  lea     rax, [rbp+57h+var_68]
0x18003057f  mov     [rbp+57h+arg_0], rax
0x180030583  lea     rax, ??_7?$_Func_impl_no_alloc@V_lambda_df661cc4afe48d466781cfb5831923ba_@@_N_N@std@@6B@; const std::_Func_impl_no_alloc<_lambda_df661cc4afe48d466781cfb5831923ba_,bool,bool>::`vftable'
0x18003058a  mov     [rbp+57h+var_68], rax
0x18003058e  lea     rax, [rbp+57h+var_68]
0x180030592  mov     [rbp+57h+var_30], rax
0x180030596  mov     rax, [rbx]
0x180030599  lea     rdx, [rbp+57h+var_90]
0x18003059d  mov     rcx, rbx
0x1800305a0  mov     rax, [rax+160h]
0x1800305a7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800305ac  nop
0x1800305ad  lea     r9, [rbp+57h+var_68]
0x1800305b1  mov     r8, rax
0x1800305b4  lea     rdx, [rbp+57h+var_78]
0x1800305b8  mov     rcx, rbx
0x1800305bb  call    ??$create_exception_checked_task@_N@?$streambuf_state_manager@E@details@streams@Concurrency@@AEAA?AV?$task@_N@pplx@@V45@V?$function@$$A6A_N_N@Z@std@@H@Z; Concurrency::streams::details::streambuf_state_manager<uchar>::create_exception_checked_task<bool>(pplx::task<bool>,std::function<bool (bool)>,int)
0x1800305c0  nop
0x1800305c1  mov     rdx, rdi
0x1800305c4  mov     rcx, rax
0x1800305c7  call    ??$then@V_lambda_08114761827faabe1bf84d934f9c06d0_@@@?$task@_N@pplx@@QEBA?AV?$task@X@1@AEBV_lambda_08114761827faabe1bf84d934f9c06d0_@@@Z; pplx::task<bool>::then<_lambda_08114761827faabe1bf84d934f9c06d0_>(_lambda_08114761827faabe1bf84d934f9c06d0_ const &)
0x1800305cc  nop
0x1800305cd  mov     rcx, [rbp+57h+var_70]; this
0x1800305d1  test    rcx, rcx
0x1800305d4  jz      short loc_1800305DB
0x1800305d6  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x1800305db  mov     rax, rdi
0x1800305de  mov     rbx, [rsp+0C0h+arg_8]
0x1800305e6  add     rsp, 0B0h
0x1800305ed  pop     rdi
0x1800305ee  pop     rsi
0x1800305ef  pop     rbp
0x1800305f0  retn
```
