# Concurrency::streams::details::streambuf_state_manager<char>::sync(void)

- ea: `0x180094fc0`
- end: `0x1800950d1`
- name: `?sync@?$streambuf_state_manager@D@details@streams@Concurrency@@UEAA?AV?$task@X@pplx@@XZ`
- size: `273`
- prototype: ``
- caller_count: `0`
- callee_count: `9`
- tags: `service_task`

## callees

- `0x18006f824`
- `0x180081238`
- `0x180081f54`
- `0x180082208`
- `0x1800827cc`
- `0x180083d18`
- `0x180085138`
- `0x180094fc0`
- `0x1800c0010`

## import_xrefs

- `msvcp_win!?__ExceptionPtrToBool@@YA_NPEBX@Z` at `0x180094ff1`
- `msvcp_win!?__ExceptionPtrToBool@@YA_NPEBX@Z` at `0x180094ff1`
- `msvcp_win!?__ExceptionPtrCopy@@YAXPEAXPEBX@Z` at `0x18009501c`
- `msvcp_win!?__ExceptionPtrCopy@@YAXPEAXPEBX@Z` at `0x18009501c`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall Concurrency::streams::details::streambuf_state_manager<char>::sync(__int64 a1, __int64 a2)
{
  const void *v4; // rsi
  __int64 v5; // rbx
  __int64 v6; // rax
  int v7; // eax
  __int64 exception_checked; // rax
  __int128 v10; // [rsp+30h] [rbp-39h] BYREF
  _BYTE v11[16]; // [rsp+48h] [rbp-21h] BYREF
  _QWORD v12[13]; // [rsp+58h] [rbp-11h] BYREF

  if ( (*(unsigned __int8 (__fastcall **)(__int64))(*(_QWORD *)a1 + 16LL))(a1) )
  {
    v12[0] = &std::_Func_impl_no_alloc<_lambda_a71a92aa9d0bb89e67b20293ccce2385_,bool,bool>::`vftable';
    v12[7] = v12;
    v7 = (*(__int64 (__fastcall **)(__int64, __int128 *))(*(_QWORD *)a1 + 352LL))(a1, &v10);
    exception_checked = Concurrency::streams::details::streambuf_state_manager<char>::create_exception_checked_task<bool>(
                          a1,
                          (unsigned int)v11,
                          v7,
                          (unsigned int)v12,
                          3);
    pplx::task<bool>::then<_lambda_ccc52d68d0ef3c0ed95db32f9cfb7615_>(exception_checked, a2);
    std::_Ptr_base<pplx::details::_Task_impl<int>>::_Decref(v11);
  }
  else
  {
    v4 = (const void *)(a1 + 24);
    if ( __ExceptionPtrToBool((const void *)(a1 + 24)) )
    {
      v5 = pplx::task_options::task_options((pplx::task_options *)v12);
      v10 = 0;
      __ExceptionPtrCopy(&v10, v4);
      pplx::task_from_exception<void,std::exception_ptr>(a2, &v10, v5);
    }
    else
    {
      v6 = pplx::task_options::task_options((pplx::task_options *)v12);
      pplx::task_from_result<void>(a2, v6);
    }
    pplx::task_options::~task_options((pplx::task_options *)v12);
  }
  return a2;
}

```

## disassembly

```asm
0x180094fc0  mov     [rsp-8+arg_8], rbx
0x180094fc5  push    rbp
0x180094fc6  push    rsi
0x180094fc7  push    rdi
0x180094fc8  lea     rbp, [rsp-47h]
0x180094fcd  sub     rsp, 0B0h
0x180094fd4  mov     rdi, rdx
0x180094fd7  mov     rbx, rcx
0x180094fda  mov     rax, [rcx]
0x180094fdd  mov     rax, [rax+10h]
0x180094fe1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180094fe6  test    al, al
0x180094fe8  jnz     short loc_180095057
0x180094fea  lea     rsi, [rbx+18h]
0x180094fee  mov     rcx, rsi
0x180094ff1  call    cs:__imp_?__ExceptionPtrToBool@@YA_NPEBX@Z; __ExceptionPtrToBool(void const *)
0x180094ff8  nop     dword ptr [rax+rax+00h]
0x180094ffd  lea     rcx, [rbp+57h+var_68]; this
0x180095001  test    al, al
0x180095003  jz      short loc_180095043
0x180095005  call    ??0task_options@pplx@@QEAA@XZ; pplx::task_options::task_options(void)
0x18009500a  mov     rbx, rax
0x18009500d  xorps   xmm0, xmm0
0x180095010  movdqu  [rbp+57h+var_90], xmm0
0x180095015  mov     rdx, rsi
0x180095018  lea     rcx, [rbp+57h+var_90]
0x18009501c  call    cs:__imp_?__ExceptionPtrCopy@@YAXPEAXPEBX@Z; __ExceptionPtrCopy(void *,void const *)
0x180095023  nop     dword ptr [rax+rax+00h]
0x180095028  mov     r8, rbx
0x18009502b  lea     rdx, [rbp+57h+var_90]
0x18009502f  mov     rcx, rdi
0x180095032  call    ??$task_from_exception@XVexception_ptr@std@@@pplx@@YA?AV?$task@X@0@Vexception_ptr@std@@AEBVtask_options@0@@Z; pplx::task_from_exception<void,std::exception_ptr>(std::exception_ptr,pplx::task_options const &)
0x180095037  nop
0x180095038  lea     rcx, [rbp+57h+var_68]; this
0x18009503c  call    ??1task_options@pplx@@QEAA@XZ; pplx::task_options::~task_options(void)
0x180095041  jmp     short loc_1800950BA
0x180095043  call    ??0task_options@pplx@@QEAA@XZ; pplx::task_options::task_options(void)
0x180095048  nop
0x180095049  mov     rdx, rax
0x18009504c  mov     rcx, rdi
0x18009504f  call    ??$task_from_result@X@pplx@@YA?AV?$task@X@0@AEBVtask_options@0@@Z; pplx::task_from_result<void>(pplx::task_options const &)
0x180095054  nop
0x180095055  jmp     short loc_180095038
0x180095057  lea     rax, [rbp+57h+var_68]
0x18009505b  mov     [rbp+57h+arg_0], rax
0x18009505f  lea     rax, ??_7?$_Func_impl_no_alloc@V_lambda_a71a92aa9d0bb89e67b20293ccce2385_@@_N_N@std@@6B@; const std::_Func_impl_no_alloc<_lambda_a71a92aa9d0bb89e67b20293ccce2385_,bool,bool>::`vftable'
0x180095066  mov     [rbp+57h+var_68], rax
0x18009506a  lea     rax, [rbp+57h+var_68]
0x18009506e  mov     [rbp+57h+var_30], rax
0x180095072  mov     rax, [rbx]
0x180095075  lea     rdx, [rbp+57h+var_90]
0x180095079  mov     rcx, rbx
0x18009507c  mov     rax, [rax+160h]
0x180095083  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180095088  nop
0x180095089  mov     [rsp+0C0h+var_A0], 3
0x180095091  lea     r9, [rbp+57h+var_68]
0x180095095  mov     r8, rax
0x180095098  lea     rdx, [rbp+57h+var_78]
0x18009509c  mov     rcx, rbx
0x18009509f  call    ??$create_exception_checked_task@_N@?$streambuf_state_manager@D@details@streams@Concurrency@@AEAA?AV?$task@_N@pplx@@V45@V?$function@$$A6A_N_N@Z@std@@H@Z; Concurrency::streams::details::streambuf_state_manager<char>::create_exception_checked_task<bool>(pplx::task<bool>,std::function<bool (bool)>,int)
0x1800950a4  nop
0x1800950a5  mov     rdx, rdi
0x1800950a8  mov     rcx, rax
0x1800950ab  call    ??$then@V_lambda_ccc52d68d0ef3c0ed95db32f9cfb7615_@@@?$task@_N@pplx@@QEBA?AV?$task@X@1@$$QEAV_lambda_ccc52d68d0ef3c0ed95db32f9cfb7615_@@@Z; pplx::task<bool>::then<_lambda_ccc52d68d0ef3c0ed95db32f9cfb7615_>(_lambda_ccc52d68d0ef3c0ed95db32f9cfb7615_ &&)
0x1800950b0  nop
0x1800950b1  lea     rcx, [rbp+57h+var_78]
0x1800950b5  call    ?_Decref@?$_Ptr_base@U?$_Task_impl@H@details@pplx@@@std@@IEAAXXZ; std::_Ptr_base<pplx::details::_Task_impl<int>>::_Decref(void)
0x1800950ba  mov     rax, rdi
0x1800950bd  mov     rbx, [rsp+0C0h+arg_8]
0x1800950c5  add     rsp, 0B0h
0x1800950cc  pop     rdi
0x1800950cd  pop     rsi
0x1800950ce  pop     rbp
0x1800950cf  retn
```
