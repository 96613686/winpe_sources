# _Concurrency::details::_PPLTaskHandle_unsigned_char_Concurrency::task_unsigned_char_::_InitialTaskHandle_void_std::function_void___cdecl(void)__Concurrency::details::_TypeSelectorNoAsync__Concurrency::details::_TaskProcHandle_::invoke_::_1_::catch$4

- ea: `0x1800a42c4`
- end: `0x1800a4321`
- name: `_Concurrency::details::_PPLTaskHandle_unsigned_char_Concurrency::task_unsigned_char_::_InitialTaskHandle_void_std::function_void___cdecl(void)__Concurrency::details::_TypeSelectorNoAsync__Concurrency::details::_TaskProcHandle_::invoke_::_1_::catch$4`
- size: `93`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `service_task`

## callees

- `0x18001a898`

## import_xrefs

- `msvcp_win!?__ExceptionPtrCreate@@YAXPEAX@Z` at `0x1800a42e6`
- `msvcp_win!?__ExceptionPtrCreate@@YAXPEAX@Z` at `0x1800a42e6`
- `msvcp_win!?__ExceptionPtrCurrentException@@YAXPEAX@Z` at `0x1800a42f0`
- `msvcp_win!?__ExceptionPtrCurrentException@@YAXPEAX@Z` at `0x1800a42f0`
- `msvcp_win!?__ExceptionPtrDestroy@@YAXPEAX@Z` at `0x1800a4308`
- `msvcp_win!?__ExceptionPtrDestroy@@YAXPEAX@Z` at `0x1800a4308`

## pseudocode

```c
__int64 __fastcall Concurrency::details::_PPLTaskHandle_unsigned_char_Concurrency::task_unsigned_char_::_InitialTaskHandle_void_std::function_void___cdecl_void___Concurrency::details::_TypeSelectorNoAsync__Concurrency::details::_TaskProcHandle_::invoke_::_1_::catch_4(
        __int64 a1,
        __int64 a2)
{
  Concurrency::details::_Task_impl_base *v3; // rbx

  v3 = *(Concurrency::details::_Task_impl_base **)(*(_QWORD *)(a2 + 80) + 8LL);
  *(_OWORD *)(a2 + 48) = 0;
  __ExceptionPtrCreate((void *)(a2 + 48));
  __ExceptionPtrCurrentException((void *)(a2 + 48));
  Concurrency::details::_Task_impl_base::_CancelWithException(v3, (const struct std::exception_ptr *)(a2 + 48));
  __ExceptionPtrDestroy((void *)(a2 + 48));
  return 0;
}

```

## disassembly

```asm
0x1800a42c4  mov     [rsp+arg_8], rdx
0x1800a42c9  push    rbx
0x1800a42ca  push    rbp
0x1800a42cb  sub     rsp, 38h
0x1800a42cf  mov     rbp, rdx
0x1800a42d2  mov     rax, [rbp+50h]
0x1800a42d6  mov     rbx, [rax+8]
0x1800a42da  xorps   xmm0, xmm0
0x1800a42dd  movdqu  xmmword ptr [rbp+30h], xmm0
0x1800a42e2  lea     rcx, [rbp+30h]
0x1800a42e6  call    cs:__imp_?__ExceptionPtrCreate@@YAXPEAX@Z; __ExceptionPtrCreate(void *)
0x1800a42ec  lea     rcx, [rbp+30h]
0x1800a42f0  call    cs:__imp_?__ExceptionPtrCurrentException@@YAXPEAX@Z; __ExceptionPtrCurrentException(void *)
0x1800a42f6  nop
0x1800a42f7  lea     rdx, [rbp+30h]; struct std::exception_ptr *
0x1800a42fb  mov     rcx, rbx; this
0x1800a42fe  call    ?_CancelWithException@_Task_impl_base@details@Concurrency@@QEAA_NAEBVexception_ptr@std@@@Z; Concurrency::details::_Task_impl_base::_CancelWithException(std::exception_ptr const &)
0x1800a4303  nop
0x1800a4304  lea     rcx, [rbp+30h]
0x1800a4308  call    cs:__imp_?__ExceptionPtrDestroy@@YAXPEAX@Z; __ExceptionPtrDestroy(void *)
0x1800a430e  nop
0x1800a430f  mov     rax, 0
0x1800a4319  add     rsp, 38h
0x1800a431d  pop     rbp
0x1800a431e  pop     rbx
0x1800a431f  retn
```
