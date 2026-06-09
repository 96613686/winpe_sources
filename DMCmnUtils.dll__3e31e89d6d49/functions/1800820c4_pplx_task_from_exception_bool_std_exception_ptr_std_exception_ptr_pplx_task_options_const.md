# pplx::task_from_exception<bool,std::exception_ptr>(std::exception_ptr,pplx::task_options const &)

- ea: `0x1800820c4`
- end: `0x180082174`
- name: `??$task_from_exception@_NVexception_ptr@std@@@pplx@@YA?AV?$task@_N@0@Vexception_ptr@std@@AEBVtask_options@0@@Z`
- size: `176`
- prototype: ``
- caller_count: `6`
- callee_count: `6`
- tags: `service_task, broker_com_uri`

## callers

- `0x180018b80`
- `0x180085ad8`
- `0x1800b39b0`
- `0x1800b6940`
- `0x1800b6d00`
- `0x1800b96fa`

## callees

- `0x18006f824`
- `0x18007b18c`
- `0x18008163c`
- `0x1800818dc`
- `0x180083cc0`
- `0x180094c5c`

## import_xrefs

- `msvcp_win!?__ExceptionPtrDestroy@@YAXPEAX@Z` at `0x180082151`
- `msvcp_win!?__ExceptionPtrDestroy@@YAXPEAX@Z` at `0x180082151`
- `msvcp_win!?__ExceptionPtrCopy@@YAXPEAXPEBX@Z` at `0x1800820ff`
- `msvcp_win!?__ExceptionPtrCopy@@YAXPEAXPEBX@Z` at `0x1800820ff`

## pseudocode

```c
__int64 __fastcall pplx::task_from_exception<bool,std::exception_ptr>(
        __int64 a1,
        void *a2,
        const struct pplx::task_options *a3)
{
  __int64 v6; // rbx
  __int128 v8; // [rsp+20h] [rbp-39h] BYREF
  _BYTE v9[16]; // [rsp+38h] [rbp-21h] BYREF
  _BYTE v10[104]; // [rsp+48h] [rbp-11h] BYREF

  std::make_shared<pplx::details::_Task_completion_event_impl<bool>,>(v9);
  v8 = 0;
  __ExceptionPtrCopy(&v8, a2);
  pplx::task_completion_event<int>::set_exception(v9, &v8);
  v6 = pplx::task_options::task_options((pplx::task_options *)v10, a3);
  std::shared_ptr<pplx::details::_Task_impl<bool>>::shared_ptr<pplx::details::_Task_impl<bool>>(&v8, v9);
  pplx::create_task<pplx::task_completion_event<bool>>(a1, &v8, v6);
  std::_Ptr_base<pplx::details::_Task_impl<int>>::_Decref(v9);
  __ExceptionPtrDestroy(a2);
  return a1;
}

```

## disassembly

```asm
0x1800820c4  mov     [rsp-8+arg_10], rbx
0x1800820c9  mov     [rsp-8+arg_8], rdx
0x1800820ce  push    rbp
0x1800820cf  push    rsi
0x1800820d0  push    rdi
0x1800820d1  lea     rbp, [rsp-47h]
0x1800820d6  sub     rsp, 0A0h
0x1800820dd  mov     rbx, r8
0x1800820e0  mov     rdi, rdx
0x1800820e3  mov     rsi, rcx
0x1800820e6  lea     rcx, [rbp+57h+var_78]
0x1800820ea  call    ??$make_shared@U?$_Task_completion_event_impl@_N@details@pplx@@$$V@std@@YA?AV?$shared_ptr@U?$_Task_completion_event_impl@_N@details@pplx@@@0@XZ; std::make_shared<pplx::details::_Task_completion_event_impl<bool>,>(void)
0x1800820ef  nop
0x1800820f0  xorps   xmm0, xmm0
0x1800820f3  movdqu  [rbp+57h+var_90], xmm0
0x1800820f8  mov     rdx, rdi
0x1800820fb  lea     rcx, [rbp+57h+var_90]
0x1800820ff  call    cs:__imp_?__ExceptionPtrCopy@@YAXPEAXPEBX@Z; __ExceptionPtrCopy(void *,void const *)
0x180082106  nop     dword ptr [rax+rax+00h]
0x18008210b  lea     rdx, [rbp+57h+var_90]
0x18008210f  lea     rcx, [rbp+57h+var_78]
0x180082113  call    ?set_exception@?$task_completion_event@H@pplx@@QEBA_NVexception_ptr@std@@@Z; pplx::task_completion_event<int>::set_exception(std::exception_ptr)
0x180082118  mov     rdx, rbx; struct pplx::task_options *
0x18008211b  lea     rcx, [rbp+57h+var_68]; this
0x18008211f  call    ??0task_options@pplx@@QEAA@AEBV01@@Z; pplx::task_options::task_options(pplx::task_options const &)
0x180082124  mov     rbx, rax
0x180082127  lea     rdx, [rbp+57h+var_78]
0x18008212b  lea     rcx, [rbp+57h+var_90]
0x18008212f  call    ??0?$shared_ptr@U?$_Task_impl@_N@details@pplx@@@std@@QEAA@AEBV01@@Z; std::shared_ptr<pplx::details::_Task_impl<bool>>::shared_ptr<pplx::details::_Task_impl<bool>>(std::shared_ptr<pplx::details::_Task_impl<bool>> const &)
0x180082134  mov     r8, rbx
0x180082137  lea     rdx, [rbp+57h+var_90]
0x18008213b  mov     rcx, rsi
0x18008213e  call    ??$create_task@V?$task_completion_event@_N@pplx@@@pplx@@YA?AV?$task@_N@0@V?$task_completion_event@_N@0@Vtask_options@0@@Z; pplx::create_task<pplx::task_completion_event<bool>>(pplx::task_completion_event<bool>,pplx::task_options)
0x180082143  nop
0x180082144  lea     rcx, [rbp+57h+var_78]
0x180082148  call    ?_Decref@?$_Ptr_base@U?$_Task_impl@H@details@pplx@@@std@@IEAAXXZ; std::_Ptr_base<pplx::details::_Task_impl<int>>::_Decref(void)
0x18008214d  nop
0x18008214e  mov     rcx, rdi
0x180082151  call    cs:__imp_?__ExceptionPtrDestroy@@YAXPEAX@Z; __ExceptionPtrDestroy(void *)
0x180082158  nop     dword ptr [rax+rax+00h]
0x18008215d  mov     rax, rsi
0x180082160  mov     rbx, [rsp+0B0h+arg_10]
0x180082168  add     rsp, 0A0h
0x18008216f  pop     rdi
0x180082170  pop     rsi
0x180082171  pop     rbp
0x180082172  retn
```
