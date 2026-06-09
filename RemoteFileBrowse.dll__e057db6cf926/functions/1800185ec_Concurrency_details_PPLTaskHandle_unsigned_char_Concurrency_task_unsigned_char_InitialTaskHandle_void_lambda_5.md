# _Concurrency::details::_PPLTaskHandle_unsigned_char_Concurrency::task_unsigned_char_::_InitialTaskHandle_void__lambda_5a3b4c8fbc070cd6d2fcfe17e4a62358__Concurrency::details::_TypeSelectorNoAsync__Concurrency::details::_TaskProcHandle_::invoke_::_1_::catch$5

- ea: `0x1800185ec`
- end: `0x180018649`
- name: `_Concurrency::details::_PPLTaskHandle_unsigned_char_Concurrency::task_unsigned_char_::_InitialTaskHandle_void__lambda_5a3b4c8fbc070cd6d2fcfe17e4a62358__Concurrency::details::_TypeSelectorNoAsync__Concurrency::details::_TaskProcHandle_::invoke_::_1_::catch$5`
- size: `93`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `service_task`

## callees

- `0x180011744`

## import_xrefs

- `msvcp_win!?__ExceptionPtrCreate@@YAXPEAX@Z` at `0x18001860e`
- `msvcp_win!?__ExceptionPtrCreate@@YAXPEAX@Z` at `0x18001860e`
- `msvcp_win!?__ExceptionPtrCurrentException@@YAXPEAX@Z` at `0x180018618`
- `msvcp_win!?__ExceptionPtrCurrentException@@YAXPEAX@Z` at `0x180018618`
- `msvcp_win!?__ExceptionPtrDestroy@@YAXPEAX@Z` at `0x180018630`
- `msvcp_win!?__ExceptionPtrDestroy@@YAXPEAX@Z` at `0x180018630`

## pseudocode

```c
__int64 __fastcall Concurrency::details::_PPLTaskHandle_unsigned_char_Concurrency::task_unsigned_char_::_InitialTaskHandle_void__lambda_5a3b4c8fbc070cd6d2fcfe17e4a62358__Concurrency::details::_TypeSelectorNoAsync__Concurrency::details::_TaskProcHandle_::invoke_::_1_::catch_5(
        __int64 a1,
        __int64 a2)
{
  Concurrency::details::_Task_impl_base *v3; // rbx

  v3 = *(Concurrency::details::_Task_impl_base **)(*(_QWORD *)(a2 + 96) + 8LL);
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
0x1800185ec  mov     [rsp+arg_8], rdx
0x1800185f1  push    rbx
0x1800185f2  push    rbp
0x1800185f3  sub     rsp, 38h
0x1800185f7  mov     rbp, rdx
0x1800185fa  mov     rax, [rbp+60h]
0x1800185fe  mov     rbx, [rax+8]
0x180018602  xorps   xmm0, xmm0
0x180018605  movdqu  xmmword ptr [rbp+30h], xmm0
0x18001860a  lea     rcx, [rbp+30h]
0x18001860e  call    cs:__imp_?__ExceptionPtrCreate@@YAXPEAX@Z; __ExceptionPtrCreate(void *)
0x180018614  lea     rcx, [rbp+30h]
0x180018618  call    cs:__imp_?__ExceptionPtrCurrentException@@YAXPEAX@Z; __ExceptionPtrCurrentException(void *)
0x18001861e  nop
0x18001861f  lea     rdx, [rbp+30h]; struct std::exception_ptr *
0x180018623  mov     rcx, rbx; this
0x180018626  call    ?_CancelWithException@_Task_impl_base@details@Concurrency@@QEAA_NAEBVexception_ptr@std@@@Z; Concurrency::details::_Task_impl_base::_CancelWithException(std::exception_ptr const &)
0x18001862b  nop
0x18001862c  lea     rcx, [rbp+30h]
0x180018630  call    cs:__imp_?__ExceptionPtrDestroy@@YAXPEAX@Z; __ExceptionPtrDestroy(void *)
0x180018636  nop
0x180018637  mov     rax, 0
0x180018641  add     rsp, 38h
0x180018645  pop     rbp
0x180018646  pop     rbx
0x180018647  retn
```
