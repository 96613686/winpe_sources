# pplx::task_from_exception<void,std::exception_ptr>(std::exception_ptr,pplx::task_options const &)

- ea: `0x180081f54`
- end: `0x180082004`
- name: `??$task_from_exception@XVexception_ptr@std@@@pplx@@YA?AV?$task@X@0@Vexception_ptr@std@@AEBVtask_options@0@@Z`
- size: `176`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `service_task, broker_com_uri`

## callers

- `0x180094fc0`

## callees

- `0x18006f824`
- `0x18007b18c`
- `0x18008151c`
- `0x1800831fc`
- `0x180083cc0`
- `0x180094cec`

## import_xrefs

- `msvcp_win!?__ExceptionPtrDestroy@@YAXPEAX@Z` at `0x180081fe1`
- `msvcp_win!?__ExceptionPtrDestroy@@YAXPEAX@Z` at `0x180081fe1`
- `msvcp_win!?__ExceptionPtrCopy@@YAXPEAXPEBX@Z` at `0x180081f8f`
- `msvcp_win!?__ExceptionPtrCopy@@YAXPEAXPEBX@Z` at `0x180081f8f`

## pseudocode

```c
__int64 __fastcall pplx::task_from_exception<void,std::exception_ptr>(
        __int64 a1,
        void *a2,
        const struct pplx::task_options *a3)
{
  __int64 v6; // rbx
  __int128 v8; // [rsp+20h] [rbp-39h] BYREF
  _BYTE v9[16]; // [rsp+38h] [rbp-21h] BYREF
  _BYTE v10[104]; // [rsp+48h] [rbp-11h] BYREF

  pplx::task_completion_event<unsigned char>::task_completion_event<unsigned char>(v9);
  v8 = 0;
  __ExceptionPtrCopy(&v8, a2);
  pplx::task_completion_event<void>::set_exception(v9, &v8);
  v6 = pplx::task_options::task_options((pplx::task_options *)v10, a3);
  std::shared_ptr<pplx::details::_Task_impl<bool>>::shared_ptr<pplx::details::_Task_impl<bool>>(&v8, v9);
  pplx::create_task<pplx::task_completion_event<void>>(a1, &v8, v6);
  std::_Ptr_base<pplx::details::_Task_impl<int>>::_Decref(v9);
  __ExceptionPtrDestroy(a2);
  return a1;
}

```

## disassembly

```asm
0x180081f54  mov     [rsp-8+arg_10], rbx
0x180081f59  mov     [rsp-8+arg_8], rdx
0x180081f5e  push    rbp
0x180081f5f  push    rsi
0x180081f60  push    rdi
0x180081f61  lea     rbp, [rsp-47h]
0x180081f66  sub     rsp, 0A0h
0x180081f6d  mov     rbx, r8
0x180081f70  mov     rdi, rdx
0x180081f73  mov     rsi, rcx
0x180081f76  lea     rcx, [rbp+57h+var_78]
0x180081f7a  call    ??0?$task_completion_event@E@pplx@@QEAA@XZ; pplx::task_completion_event<uchar>::task_completion_event<uchar>(void)
0x180081f7f  nop
0x180081f80  xorps   xmm0, xmm0
0x180081f83  movdqu  [rbp+57h+var_90], xmm0
0x180081f88  mov     rdx, rdi
0x180081f8b  lea     rcx, [rbp+57h+var_90]
0x180081f8f  call    cs:__imp_?__ExceptionPtrCopy@@YAXPEAXPEBX@Z; __ExceptionPtrCopy(void *,void const *)
0x180081f96  nop     dword ptr [rax+rax+00h]
0x180081f9b  lea     rdx, [rbp+57h+var_90]
0x180081f9f  lea     rcx, [rbp+57h+var_78]
0x180081fa3  call    ?set_exception@?$task_completion_event@X@pplx@@QEBA_NVexception_ptr@std@@@Z; pplx::task_completion_event<void>::set_exception(std::exception_ptr)
0x180081fa8  mov     rdx, rbx; struct pplx::task_options *
0x180081fab  lea     rcx, [rbp+57h+var_68]; this
0x180081faf  call    ??0task_options@pplx@@QEAA@AEBV01@@Z; pplx::task_options::task_options(pplx::task_options const &)
0x180081fb4  mov     rbx, rax
0x180081fb7  lea     rdx, [rbp+57h+var_78]
0x180081fbb  lea     rcx, [rbp+57h+var_90]
0x180081fbf  call    ??0?$shared_ptr@U?$_Task_impl@_N@details@pplx@@@std@@QEAA@AEBV01@@Z; std::shared_ptr<pplx::details::_Task_impl<bool>>::shared_ptr<pplx::details::_Task_impl<bool>>(std::shared_ptr<pplx::details::_Task_impl<bool>> const &)
0x180081fc4  mov     r8, rbx
0x180081fc7  lea     rdx, [rbp+57h+var_90]
0x180081fcb  mov     rcx, rsi
0x180081fce  call    ??$create_task@V?$task_completion_event@X@pplx@@@pplx@@YA?AV?$task@X@0@V?$task_completion_event@X@0@Vtask_options@0@@Z; pplx::create_task<pplx::task_completion_event<void>>(pplx::task_completion_event<void>,pplx::task_options)
0x180081fd3  nop
0x180081fd4  lea     rcx, [rbp+57h+var_78]
0x180081fd8  call    ?_Decref@?$_Ptr_base@U?$_Task_impl@H@details@pplx@@@std@@IEAAXXZ; std::_Ptr_base<pplx::details::_Task_impl<int>>::_Decref(void)
0x180081fdd  nop
0x180081fde  mov     rcx, rdi
0x180081fe1  call    cs:__imp_?__ExceptionPtrDestroy@@YAXPEAX@Z; __ExceptionPtrDestroy(void *)
0x180081fe8  nop     dword ptr [rax+rax+00h]
0x180081fed  mov     rax, rsi
0x180081ff0  mov     rbx, [rsp+0B0h+arg_10]
0x180081ff8  add     rsp, 0A0h
0x180081fff  pop     rdi
0x180082000  pop     rsi
0x180082001  pop     rbp
0x180082002  retn
```
