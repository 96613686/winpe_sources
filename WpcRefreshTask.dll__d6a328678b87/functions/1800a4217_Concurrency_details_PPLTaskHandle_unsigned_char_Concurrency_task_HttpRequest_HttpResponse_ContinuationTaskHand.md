# _Concurrency::details::_PPLTaskHandle_unsigned_char_Concurrency::task_HttpRequest::HttpResponse_::_ContinuationTaskHandle_HttpRequest::HttpResponse_void_std::function_void___cdecl(Concurrency::task_HttpRequest::HttpResponse_)__std::integral_constant_bool_1__Concurrency::details::_TypeSelectorNoAsync__Concurrency::details::_ContinuationTaskHandleBase_::invoke_::_1_::catch$4

- ea: `0x1800a4217`
- end: `0x1800a4274`
- name: `_Concurrency::details::_PPLTaskHandle_unsigned_char_Concurrency::task_HttpRequest::HttpResponse_::_ContinuationTaskHandle_HttpRequest::HttpResponse_void_std::function_void___cdecl(Concurrency::task_HttpRequest::HttpResponse_)__std::integral_constant_bool_1__Concurrency::details::_TypeSelectorNoAsync__Concurrency::details::_ContinuationTaskHandleBase_::invoke_::_1_::catch$4`
- size: `93`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `service_task`

## callees

- `0x18001a898`

## import_xrefs

- `msvcp_win!?__ExceptionPtrCreate@@YAXPEAX@Z` at `0x1800a4239`
- `msvcp_win!?__ExceptionPtrCreate@@YAXPEAX@Z` at `0x1800a4239`
- `msvcp_win!?__ExceptionPtrCurrentException@@YAXPEAX@Z` at `0x1800a4243`
- `msvcp_win!?__ExceptionPtrCurrentException@@YAXPEAX@Z` at `0x1800a4243`
- `msvcp_win!?__ExceptionPtrDestroy@@YAXPEAX@Z` at `0x1800a425b`
- `msvcp_win!?__ExceptionPtrDestroy@@YAXPEAX@Z` at `0x1800a425b`

## pseudocode

```c
__int64 __fastcall Concurrency::details::_PPLTaskHandle_unsigned_char_Concurrency::task_HttpRequest::HttpResponse_::_ContinuationTaskHandle_HttpRequest::HttpResponse_void_std::function_void___cdecl_Concurrency::task_HttpRequest::HttpResponse____std::integral_constant_bool_1__Concurrency::details::_TypeSelectorNoAsync__Concurrency::details::_ContinuationTaskHandleBase_::invoke_::_1_::catch_4(
        __int64 a1,
        __int64 a2)
{
  Concurrency::details::_Task_impl_base *v3; // rbx

  v3 = *(Concurrency::details::_Task_impl_base **)(*(_QWORD *)(a2 + 80) + 40LL);
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
0x1800a4217  mov     [rsp+arg_8], rdx
0x1800a421c  push    rbx
0x1800a421d  push    rbp
0x1800a421e  sub     rsp, 38h
0x1800a4222  mov     rbp, rdx
0x1800a4225  mov     rax, [rbp+50h]
0x1800a4229  mov     rbx, [rax+28h]
0x1800a422d  xorps   xmm0, xmm0
0x1800a4230  movdqu  xmmword ptr [rbp+30h], xmm0
0x1800a4235  lea     rcx, [rbp+30h]
0x1800a4239  call    cs:__imp_?__ExceptionPtrCreate@@YAXPEAX@Z; __ExceptionPtrCreate(void *)
0x1800a423f  lea     rcx, [rbp+30h]
0x1800a4243  call    cs:__imp_?__ExceptionPtrCurrentException@@YAXPEAX@Z; __ExceptionPtrCurrentException(void *)
0x1800a4249  nop
0x1800a424a  lea     rdx, [rbp+30h]; struct std::exception_ptr *
0x1800a424e  mov     rcx, rbx; this
0x1800a4251  call    ?_CancelWithException@_Task_impl_base@details@Concurrency@@QEAA_NAEBVexception_ptr@std@@@Z; Concurrency::details::_Task_impl_base::_CancelWithException(std::exception_ptr const &)
0x1800a4256  nop
0x1800a4257  lea     rcx, [rbp+30h]
0x1800a425b  call    cs:__imp_?__ExceptionPtrDestroy@@YAXPEAX@Z; __ExceptionPtrDestroy(void *)
0x1800a4261  nop
0x1800a4262  mov     rax, 0
0x1800a426c  add     rsp, 38h
0x1800a4270  pop     rbp
0x1800a4271  pop     rbx
0x1800a4272  retn
```
