# pplx::task_from_exception<unsigned __int64,std::exception_ptr>(std::exception_ptr,pplx::task_options const &)

- ea: `0x18008200c`
- end: `0x1800820bc`
- name: `??$task_from_exception@_KVexception_ptr@std@@@pplx@@YA?AV?$task@_K@0@Vexception_ptr@std@@AEBVtask_options@0@@Z`
- size: `176`
- prototype: ``
- caller_count: `8`
- callee_count: `6`
- tags: `service_task, broker_com_uri`

## callers

- `0x180015970`
- `0x180018970`
- `0x1800813d4`
- `0x1800855e4`
- `0x1800b38c0`
- `0x1800b6a00`
- `0x1800b6c80`
- `0x1800b95a2`

## callees

- `0x18006f824`
- `0x18007b18c`
- `0x1800815ac`
- `0x18008189c`
- `0x180083cc0`
- `0x180094c5c`

## import_xrefs

- `msvcp_win!?__ExceptionPtrDestroy@@YAXPEAX@Z` at `0x180082099`
- `msvcp_win!?__ExceptionPtrDestroy@@YAXPEAX@Z` at `0x180082099`
- `msvcp_win!?__ExceptionPtrCopy@@YAXPEAXPEBX@Z` at `0x180082047`
- `msvcp_win!?__ExceptionPtrCopy@@YAXPEAXPEBX@Z` at `0x180082047`

## pseudocode

```c
__int64 __fastcall pplx::task_from_exception<unsigned __int64,std::exception_ptr>(
        __int64 a1,
        void *a2,
        const struct pplx::task_options *a3)
{
  __int64 v6; // rbx
  __int128 v8; // [rsp+20h] [rbp-39h] BYREF
  _BYTE v9[16]; // [rsp+38h] [rbp-21h] BYREF
  _BYTE v10[104]; // [rsp+48h] [rbp-11h] BYREF

  std::make_shared<pplx::details::_Task_completion_event_impl<unsigned __int64>,>(v9);
  v8 = 0;
  __ExceptionPtrCopy(&v8, a2);
  pplx::task_completion_event<int>::set_exception(v9, &v8);
  v6 = pplx::task_options::task_options((pplx::task_options *)v10, a3);
  std::shared_ptr<pplx::details::_Task_impl<bool>>::shared_ptr<pplx::details::_Task_impl<bool>>(&v8, v9);
  pplx::create_task<pplx::task_completion_event<unsigned __int64>>(a1, &v8, v6);
  std::_Ptr_base<pplx::details::_Task_impl<int>>::_Decref(v9);
  __ExceptionPtrDestroy(a2);
  return a1;
}

```

## disassembly

```asm
0x18008200c  mov     [rsp-8+arg_10], rbx
0x180082011  mov     [rsp-8+arg_8], rdx
0x180082016  push    rbp
0x180082017  push    rsi
0x180082018  push    rdi
0x180082019  lea     rbp, [rsp-47h]
0x18008201e  sub     rsp, 0A0h
0x180082025  mov     rbx, r8
0x180082028  mov     rdi, rdx
0x18008202b  mov     rsi, rcx
0x18008202e  lea     rcx, [rbp+57h+var_78]
0x180082032  call    ??$make_shared@U?$_Task_completion_event_impl@_K@details@pplx@@$$V@std@@YA?AV?$shared_ptr@U?$_Task_completion_event_impl@_K@details@pplx@@@0@XZ; std::make_shared<pplx::details::_Task_completion_event_impl<unsigned __int64>,>(void)
0x180082037  nop
0x180082038  xorps   xmm0, xmm0
0x18008203b  movdqu  [rbp+57h+var_90], xmm0
0x180082040  mov     rdx, rdi
0x180082043  lea     rcx, [rbp+57h+var_90]
0x180082047  call    cs:__imp_?__ExceptionPtrCopy@@YAXPEAXPEBX@Z; __ExceptionPtrCopy(void *,void const *)
0x18008204e  nop     dword ptr [rax+rax+00h]
0x180082053  lea     rdx, [rbp+57h+var_90]
0x180082057  lea     rcx, [rbp+57h+var_78]
0x18008205b  call    ?set_exception@?$task_completion_event@H@pplx@@QEBA_NVexception_ptr@std@@@Z; pplx::task_completion_event<int>::set_exception(std::exception_ptr)
0x180082060  mov     rdx, rbx; struct pplx::task_options *
0x180082063  lea     rcx, [rbp+57h+var_68]; this
0x180082067  call    ??0task_options@pplx@@QEAA@AEBV01@@Z; pplx::task_options::task_options(pplx::task_options const &)
0x18008206c  mov     rbx, rax
0x18008206f  lea     rdx, [rbp+57h+var_78]
0x180082073  lea     rcx, [rbp+57h+var_90]
0x180082077  call    ??0?$shared_ptr@U?$_Task_impl@_N@details@pplx@@@std@@QEAA@AEBV01@@Z; std::shared_ptr<pplx::details::_Task_impl<bool>>::shared_ptr<pplx::details::_Task_impl<bool>>(std::shared_ptr<pplx::details::_Task_impl<bool>> const &)
0x18008207c  mov     r8, rbx
0x18008207f  lea     rdx, [rbp+57h+var_90]
0x180082083  mov     rcx, rsi
0x180082086  call    ??$create_task@V?$task_completion_event@_K@pplx@@@pplx@@YA?AV?$task@_K@0@V?$task_completion_event@_K@0@Vtask_options@0@@Z; pplx::create_task<pplx::task_completion_event<unsigned __int64>>(pplx::task_completion_event<unsigned __int64>,pplx::task_options)
0x18008208b  nop
0x18008208c  lea     rcx, [rbp+57h+var_78]
0x180082090  call    ?_Decref@?$_Ptr_base@U?$_Task_impl@H@details@pplx@@@std@@IEAAXXZ; std::_Ptr_base<pplx::details::_Task_impl<int>>::_Decref(void)
0x180082095  nop
0x180082096  mov     rcx, rdi
0x180082099  call    cs:__imp_?__ExceptionPtrDestroy@@YAXPEAX@Z; __ExceptionPtrDestroy(void *)
0x1800820a0  nop     dword ptr [rax+rax+00h]
0x1800820a5  mov     rax, rsi
0x1800820a8  mov     rbx, [rsp+0B0h+arg_10]
0x1800820b0  add     rsp, 0A0h
0x1800820b7  pop     rdi
0x1800820b8  pop     rsi
0x1800820b9  pop     rbp
0x1800820ba  retn
```
