# Concurrency::streams::details::streambuf_state_manager<char>::sync(void)

- ea: `0x18004e450`
- end: `0x18004e551`
- name: `?sync@?$streambuf_state_manager@D@details@streams@Concurrency@@UEAA?AV?$task@X@pplx@@XZ`
- size: `257`
- prototype: ``
- caller_count: `0`
- callee_count: `9`
- tags: `service_task`

## callees

- `0x18001235c`
- `0x180012cc0`
- `0x1800148ac`
- `0x1800231e8`
- `0x1800305f8`
- `0x180046df4`
- `0x1800478d0`
- `0x18004e450`
- `0x18005f010`

## import_xrefs

- `msvcp_win!?__ExceptionPtrToBool@@YA_NPEBX@Z` at `0x18004e481`
- `msvcp_win!?__ExceptionPtrToBool@@YA_NPEBX@Z` at `0x18004e481`
- `msvcp_win!?__ExceptionPtrCopy@@YAXPEAXPEBX@Z` at `0x18004e4a6`
- `msvcp_win!?__ExceptionPtrCopy@@YAXPEAXPEBX@Z` at `0x18004e4a6`

## pseudocode

```c
_QWORD *__fastcall Concurrency::streams::details::streambuf_state_manager<char>::sync(__int64 a1, _QWORD *a2)
{
  const void *v4; // rsi
  const struct pplx::task_options *v5; // rbx
  __int64 v6; // rax
  _QWORD *v7; // rax
  __int64 exception_checked; // rax
  __int128 v10; // [rsp+30h] [rbp-39h] BYREF
  _BYTE v11[8]; // [rsp+48h] [rbp-21h] BYREF
  std::_Ref_count_base *v12; // [rsp+50h] [rbp-19h]
  __int64 v13[13]; // [rsp+58h] [rbp-11h] BYREF

  if ( (*(unsigned __int8 (__fastcall **)(__int64))(*(_QWORD *)a1 + 16LL))(a1) )
  {
    v13[0] = (__int64)&std::_Func_impl_no_alloc<_lambda_a71a92aa9d0bb89e67b20293ccce2385_,bool,bool>::`vftable';
    v13[7] = (__int64)v13;
    v7 = (_QWORD *)(*(__int64 (__fastcall **)(__int64, __int128 *))(*(_QWORD *)a1 + 352LL))(a1, &v10);
    exception_checked = Concurrency::streams::details::streambuf_state_manager<char>::create_exception_checked_task<bool>(
                          a1,
                          (__int64)v11,
                          v7,
                          v13);
    pplx::task<bool>::then<_lambda_ccc52d68d0ef3c0ed95db32f9cfb7615_>(exception_checked, a2);
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
0x18004e450  mov     [rsp-8+arg_8], rbx
0x18004e455  push    rbp
0x18004e456  push    rsi
0x18004e457  push    rdi
0x18004e458  lea     rbp, [rsp-47h]
0x18004e45d  sub     rsp, 0B0h
0x18004e464  mov     rdi, rdx
0x18004e467  mov     rbx, rcx
0x18004e46a  mov     rax, [rcx]
0x18004e46d  mov     rax, [rax+10h]
0x18004e471  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004e476  test    al, al
0x18004e478  jnz     short loc_18004E4DB
0x18004e47a  lea     rsi, [rbx+18h]
0x18004e47e  mov     rcx, rsi
0x18004e481  call    cs:__imp_?__ExceptionPtrToBool@@YA_NPEBX@Z; __ExceptionPtrToBool(void const *)
0x18004e487  lea     rcx, [rbp+57h+var_68]; this
0x18004e48b  test    al, al
0x18004e48d  jz      short loc_18004E4C7
0x18004e48f  call    ??0task_options@pplx@@QEAA@XZ; pplx::task_options::task_options(void)
0x18004e494  mov     rbx, rax
0x18004e497  xorps   xmm0, xmm0
0x18004e49a  movdqu  [rbp+57h+var_90], xmm0
0x18004e49f  mov     rdx, rsi
0x18004e4a2  lea     rcx, [rbp+57h+var_90]
0x18004e4a6  call    cs:__imp_?__ExceptionPtrCopy@@YAXPEAXPEBX@Z; __ExceptionPtrCopy(void *,void const *)
0x18004e4ac  mov     r8, rbx
0x18004e4af  lea     rdx, [rbp+57h+var_90]
0x18004e4b3  mov     rcx, rdi
0x18004e4b6  call    ??$task_from_exception@XVexception_ptr@std@@@pplx@@YA?AV?$task@X@0@Vexception_ptr@std@@AEBVtask_options@0@@Z; pplx::task_from_exception<void,std::exception_ptr>(std::exception_ptr,pplx::task_options const &)
0x18004e4bb  nop
0x18004e4bc  lea     rcx, [rbp+57h+var_68]; this
0x18004e4c0  call    ??1task_options@pplx@@QEAA@XZ; pplx::task_options::~task_options(void)
0x18004e4c5  jmp     short loc_18004E53B
0x18004e4c7  call    ??0task_options@pplx@@QEAA@XZ; pplx::task_options::task_options(void)
0x18004e4cc  nop
0x18004e4cd  mov     rdx, rax
0x18004e4d0  mov     rcx, rdi
0x18004e4d3  call    ?task_from_result@pplx@@YA?AV?$task@X@1@AEBVtask_options@1@@Z; pplx::task_from_result(pplx::task_options const &)
0x18004e4d8  nop
0x18004e4d9  jmp     short loc_18004E4BC
0x18004e4db  lea     rax, [rbp+57h+var_68]
0x18004e4df  mov     [rbp+57h+arg_0], rax
0x18004e4e3  lea     rax, ??_7?$_Func_impl_no_alloc@V_lambda_a71a92aa9d0bb89e67b20293ccce2385_@@_N_N@std@@6B@; const std::_Func_impl_no_alloc<_lambda_a71a92aa9d0bb89e67b20293ccce2385_,bool,bool>::`vftable'
0x18004e4ea  mov     [rbp+57h+var_68], rax
0x18004e4ee  lea     rax, [rbp+57h+var_68]
0x18004e4f2  mov     [rbp+57h+var_30], rax
0x18004e4f6  mov     rax, [rbx]
0x18004e4f9  lea     rdx, [rbp+57h+var_90]
0x18004e4fd  mov     rcx, rbx
0x18004e500  mov     rax, [rax+160h]
0x18004e507  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004e50c  nop
0x18004e50d  lea     r9, [rbp+57h+var_68]
0x18004e511  mov     r8, rax
0x18004e514  lea     rdx, [rbp+57h+var_78]
0x18004e518  mov     rcx, rbx
0x18004e51b  call    ??$create_exception_checked_task@_N@?$streambuf_state_manager@D@details@streams@Concurrency@@AEAA?AV?$task@_N@pplx@@V45@V?$function@$$A6A_N_N@Z@std@@H@Z; Concurrency::streams::details::streambuf_state_manager<char>::create_exception_checked_task<bool>(pplx::task<bool>,std::function<bool (bool)>,int)
0x18004e520  nop
0x18004e521  mov     rdx, rdi
0x18004e524  mov     rcx, rax
0x18004e527  call    ??$then@V_lambda_ccc52d68d0ef3c0ed95db32f9cfb7615_@@@?$task@_N@pplx@@QEBA?AV?$task@X@1@AEBV_lambda_ccc52d68d0ef3c0ed95db32f9cfb7615_@@@Z; pplx::task<bool>::then<_lambda_ccc52d68d0ef3c0ed95db32f9cfb7615_>(_lambda_ccc52d68d0ef3c0ed95db32f9cfb7615_ const &)
0x18004e52c  nop
0x18004e52d  mov     rcx, [rbp+57h+var_70]; this
0x18004e531  test    rcx, rcx
0x18004e534  jz      short loc_18004E53B
0x18004e536  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18004e53b  mov     rax, rdi
0x18004e53e  mov     rbx, [rsp+0C0h+arg_8]
0x18004e546  add     rsp, 0B0h
0x18004e54d  pop     rdi
0x18004e54e  pop     rsi
0x18004e54f  pop     rbp
0x18004e550  retn
```
