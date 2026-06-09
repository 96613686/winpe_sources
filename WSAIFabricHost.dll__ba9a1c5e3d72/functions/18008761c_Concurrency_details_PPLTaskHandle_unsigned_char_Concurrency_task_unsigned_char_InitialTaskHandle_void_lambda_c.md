# _Concurrency::details::_PPLTaskHandle_unsigned_char_Concurrency::task_unsigned_char_::_InitialTaskHandle_void__lambda_cb907e11b937c718692f05152060950b__Concurrency::details::_TypeSelectorNoAsync__Concurrency::details::_TaskProcHandle_::invoke_::_1_::catch$5

- ea: `0x18008761c`
- end: `0x180087679`
- name: `_Concurrency::details::_PPLTaskHandle_unsigned_char_Concurrency::task_unsigned_char_::_InitialTaskHandle_void__lambda_cb907e11b937c718692f05152060950b__Concurrency::details::_TypeSelectorNoAsync__Concurrency::details::_TaskProcHandle_::invoke_::_1_::catch$5`
- size: `93`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `service_task`

## callees

- `0x1800717a4`

## import_xrefs

- `msvcp_win!?__ExceptionPtrCurrentException@@YAXPEAX@Z` at `0x180087648`
- `msvcp_win!?__ExceptionPtrCurrentException@@YAXPEAX@Z` at `0x180087648`
- `msvcp_win!?__ExceptionPtrDestroy@@YAXPEAX@Z` at `0x180087660`
- `msvcp_win!?__ExceptionPtrDestroy@@YAXPEAX@Z` at `0x180087660`
- `msvcp_win!?__ExceptionPtrCreate@@YAXPEAX@Z` at `0x18008763e`
- `msvcp_win!?__ExceptionPtrCreate@@YAXPEAX@Z` at `0x18008763e`

## pseudocode

```c
__int64 __fastcall Concurrency::details::_PPLTaskHandle_unsigned_char_Concurrency::task_unsigned_char_::_InitialTaskHandle_void__lambda_cb907e11b937c718692f05152060950b__Concurrency::details::_TypeSelectorNoAsync__Concurrency::details::_TaskProcHandle_::invoke_::_1_::catch_5(
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
0x18008761c  mov     [rsp+arg_8], rdx
0x180087621  push    rbx
0x180087622  push    rbp
0x180087623  sub     rsp, 38h
0x180087627  mov     rbp, rdx
0x18008762a  mov     rax, [rbp+60h]
0x18008762e  mov     rbx, [rax+8]
0x180087632  xorps   xmm0, xmm0
0x180087635  movdqu  xmmword ptr [rbp+30h], xmm0
0x18008763a  lea     rcx, [rbp+30h]
0x18008763e  call    cs:__imp_?__ExceptionPtrCreate@@YAXPEAX@Z; __ExceptionPtrCreate(void *)
0x180087644  lea     rcx, [rbp+30h]
0x180087648  call    cs:__imp_?__ExceptionPtrCurrentException@@YAXPEAX@Z; __ExceptionPtrCurrentException(void *)
0x18008764e  nop
0x18008764f  lea     rdx, [rbp+30h]; struct std::exception_ptr *
0x180087653  mov     rcx, rbx; this
0x180087656  call    ?_CancelWithException@_Task_impl_base@details@Concurrency@@QEAA_NAEBVexception_ptr@std@@@Z; Concurrency::details::_Task_impl_base::_CancelWithException(std::exception_ptr const &)
0x18008765b  nop
0x18008765c  lea     rcx, [rbp+30h]
0x180087660  call    cs:__imp_?__ExceptionPtrDestroy@@YAXPEAX@Z; __ExceptionPtrDestroy(void *)
0x180087666  nop
0x180087667  mov     rax, 0
0x180087671  add     rsp, 38h
0x180087675  pop     rbp
0x180087676  pop     rbx
0x180087677  retn
```
