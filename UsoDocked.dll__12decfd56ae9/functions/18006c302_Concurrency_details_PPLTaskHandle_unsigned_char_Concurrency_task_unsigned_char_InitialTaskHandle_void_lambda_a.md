# _Concurrency::details::_PPLTaskHandle_unsigned_char_Concurrency::task_unsigned_char_::_InitialTaskHandle_void__lambda_afc3e0c581ebf1dec6a4111471076a98__Concurrency::details::_TypeSelectorNoAsync__Concurrency::details::_TaskProcHandle_::invoke_::_1_::catch$10

- ea: `0x18006c302`
- end: `0x18006c362`
- name: `_Concurrency::details::_PPLTaskHandle_unsigned_char_Concurrency::task_unsigned_char_::_InitialTaskHandle_void__lambda_afc3e0c581ebf1dec6a4111471076a98__Concurrency::details::_TypeSelectorNoAsync__Concurrency::details::_TaskProcHandle_::invoke_::_1_::catch$10`
- size: `96`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `service_task`

## callees

- `0x180038408`

## import_xrefs

- `msvcp_win!?__ExceptionPtrCreate@@YAXPEAX@Z` at `0x18006c327`
- `msvcp_win!?__ExceptionPtrCreate@@YAXPEAX@Z` at `0x18006c327`
- `msvcp_win!?__ExceptionPtrCurrentException@@YAXPEAX@Z` at `0x18006c331`
- `msvcp_win!?__ExceptionPtrCurrentException@@YAXPEAX@Z` at `0x18006c331`
- `msvcp_win!?__ExceptionPtrDestroy@@YAXPEAX@Z` at `0x18006c349`
- `msvcp_win!?__ExceptionPtrDestroy@@YAXPEAX@Z` at `0x18006c349`

## pseudocode

```c
__int64 __fastcall Concurrency::details::_PPLTaskHandle_unsigned_char_Concurrency::task_unsigned_char_::_InitialTaskHandle_void__lambda_afc3e0c581ebf1dec6a4111471076a98__Concurrency::details::_TypeSelectorNoAsync__Concurrency::details::_TaskProcHandle_::invoke_::_1_::catch_10(
        __int64 a1,
        __int64 a2)
{
  Concurrency::details::_Task_impl_base *v3; // rbx

  v3 = *(Concurrency::details::_Task_impl_base **)(*(_QWORD *)(a2 + 240) + 8LL);
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
0x18006c302  mov     [rsp+arg_8], rdx
0x18006c307  push    rbx
0x18006c308  push    rbp
0x18006c309  sub     rsp, 38h
0x18006c30d  mov     rbp, rdx
0x18006c310  mov     rax, [rbp+0F0h]
0x18006c317  mov     rbx, [rax+8]
0x18006c31b  xorps   xmm0, xmm0
0x18006c31e  movdqu  xmmword ptr [rbp+30h], xmm0
0x18006c323  lea     rcx, [rbp+30h]
0x18006c327  call    cs:__imp_?__ExceptionPtrCreate@@YAXPEAX@Z; __ExceptionPtrCreate(void *)
0x18006c32d  lea     rcx, [rbp+30h]
0x18006c331  call    cs:__imp_?__ExceptionPtrCurrentException@@YAXPEAX@Z; __ExceptionPtrCurrentException(void *)
0x18006c337  nop
0x18006c338  lea     rdx, [rbp+30h]; struct std::exception_ptr *
0x18006c33c  mov     rcx, rbx; this
0x18006c33f  call    ?_CancelWithException@_Task_impl_base@details@Concurrency@@QEAA_NAEBVexception_ptr@std@@@Z; Concurrency::details::_Task_impl_base::_CancelWithException(std::exception_ptr const &)
0x18006c344  nop
0x18006c345  lea     rcx, [rbp+30h]
0x18006c349  call    cs:__imp_?__ExceptionPtrDestroy@@YAXPEAX@Z; __ExceptionPtrDestroy(void *)
0x18006c34f  nop
0x18006c350  mov     rax, 0
0x18006c35a  add     rsp, 38h
0x18006c35e  pop     rbp
0x18006c35f  pop     rbx
0x18006c360  retn
```
