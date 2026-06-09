# pplx::task_from_exception<int,std::exception_ptr>(std::exception_ptr,pplx::task_options const &)

- ea: `0x180081e9c`
- end: `0x180081f4c`
- name: `??$task_from_exception@HVexception_ptr@std@@@pplx@@YA?AV?$task@H@0@Vexception_ptr@std@@AEBVtask_options@0@@Z`
- size: `176`
- prototype: ``
- caller_count: `3`
- callee_count: `6`
- tags: `service_task, broker_com_uri`

## callers

- `0x18008131c`
- `0x1800858c0`
- `0x1800b964e`

## callees

- `0x18006f824`
- `0x18007b18c`
- `0x18008148c`
- `0x18008185c`
- `0x180083cc0`
- `0x180094c5c`

## import_xrefs

- `msvcp_win!?__ExceptionPtrDestroy@@YAXPEAX@Z` at `0x180081f29`
- `msvcp_win!?__ExceptionPtrDestroy@@YAXPEAX@Z` at `0x180081f29`
- `msvcp_win!?__ExceptionPtrCopy@@YAXPEAXPEBX@Z` at `0x180081ed7`
- `msvcp_win!?__ExceptionPtrCopy@@YAXPEAXPEBX@Z` at `0x180081ed7`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall pplx::task_from_exception<int,std::exception_ptr>(
        __int64 a1,
        void *a2,
        const struct pplx::task_options *a3)
{
  __int64 v6; // rbx
  __int128 v8; // [rsp+20h] [rbp-39h] BYREF
  _BYTE v9[16]; // [rsp+38h] [rbp-21h] BYREF
  _BYTE v10[104]; // [rsp+48h] [rbp-11h] BYREF

  std::make_shared<pplx::details::_Task_completion_event_impl<int>,>(v9);
  v8 = 0;
  __ExceptionPtrCopy(&v8, a2);
  pplx::task_completion_event<int>::set_exception(v9, &v8);
  v6 = pplx::task_options::task_options((pplx::task_options *)v10, a3);
  std::shared_ptr<pplx::details::_Task_impl<bool>>::shared_ptr<pplx::details::_Task_impl<bool>>(&v8, v9);
  pplx::create_task<pplx::task_completion_event<int>>(a1, &v8, v6);
  std::_Ptr_base<pplx::details::_Task_impl<int>>::_Decref(v9);
  __ExceptionPtrDestroy(a2);
  return a1;
}

```

## disassembly

```asm
0x180081e9c  mov     [rsp-8+arg_10], rbx
0x180081ea1  mov     [rsp-8+arg_8], rdx
0x180081ea6  push    rbp
0x180081ea7  push    rsi
0x180081ea8  push    rdi
0x180081ea9  lea     rbp, [rsp-47h]
0x180081eae  sub     rsp, 0A0h
0x180081eb5  mov     rbx, r8
0x180081eb8  mov     rdi, rdx
0x180081ebb  mov     rsi, rcx
0x180081ebe  lea     rcx, [rbp+57h+var_78]
0x180081ec2  call    ??$make_shared@U?$_Task_completion_event_impl@H@details@pplx@@$$V@std@@YA?AV?$shared_ptr@U?$_Task_completion_event_impl@H@details@pplx@@@0@XZ; std::make_shared<pplx::details::_Task_completion_event_impl<int>,>(void)
0x180081ec7  nop
0x180081ec8  xorps   xmm0, xmm0
0x180081ecb  movdqu  [rbp+57h+var_90], xmm0
0x180081ed0  mov     rdx, rdi
0x180081ed3  lea     rcx, [rbp+57h+var_90]
0x180081ed7  call    cs:__imp_?__ExceptionPtrCopy@@YAXPEAXPEBX@Z; __ExceptionPtrCopy(void *,void const *)
0x180081ede  nop     dword ptr [rax+rax+00h]
0x180081ee3  lea     rdx, [rbp+57h+var_90]
0x180081ee7  lea     rcx, [rbp+57h+var_78]
0x180081eeb  call    ?set_exception@?$task_completion_event@H@pplx@@QEBA_NVexception_ptr@std@@@Z; pplx::task_completion_event<int>::set_exception(std::exception_ptr)
0x180081ef0  mov     rdx, rbx; struct pplx::task_options *
0x180081ef3  lea     rcx, [rbp+57h+var_68]; this
0x180081ef7  call    ??0task_options@pplx@@QEAA@AEBV01@@Z; pplx::task_options::task_options(pplx::task_options const &)
0x180081efc  mov     rbx, rax
0x180081eff  lea     rdx, [rbp+57h+var_78]
0x180081f03  lea     rcx, [rbp+57h+var_90]
0x180081f07  call    ??0?$shared_ptr@U?$_Task_impl@_N@details@pplx@@@std@@QEAA@AEBV01@@Z; std::shared_ptr<pplx::details::_Task_impl<bool>>::shared_ptr<pplx::details::_Task_impl<bool>>(std::shared_ptr<pplx::details::_Task_impl<bool>> const &)
0x180081f0c  mov     r8, rbx
0x180081f0f  lea     rdx, [rbp+57h+var_90]
0x180081f13  mov     rcx, rsi
0x180081f16  call    ??$create_task@V?$task_completion_event@H@pplx@@@pplx@@YA?AV?$task@H@0@V?$task_completion_event@H@0@Vtask_options@0@@Z; pplx::create_task<pplx::task_completion_event<int>>(pplx::task_completion_event<int>,pplx::task_options)
0x180081f1b  nop
0x180081f1c  lea     rcx, [rbp+57h+var_78]
0x180081f20  call    ?_Decref@?$_Ptr_base@U?$_Task_impl@H@details@pplx@@@std@@IEAAXXZ; std::_Ptr_base<pplx::details::_Task_impl<int>>::_Decref(void)
0x180081f25  nop
0x180081f26  mov     rcx, rdi
0x180081f29  call    cs:__imp_?__ExceptionPtrDestroy@@YAXPEAX@Z; __ExceptionPtrDestroy(void *)
0x180081f30  nop     dword ptr [rax+rax+00h]
0x180081f35  mov     rax, rsi
0x180081f38  mov     rbx, [rsp+0B0h+arg_10]
0x180081f40  add     rsp, 0A0h
0x180081f47  pop     rdi
0x180081f48  pop     rsi
0x180081f49  pop     rbp
0x180081f4a  retn
```
