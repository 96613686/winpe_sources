# _Concurrency::details::_PPLTaskHandle_unsigned_char_Concurrency::task_unsigned_char_::_InitialTaskHandle_void__std::_Task_async_state_void_::_Task_async_state_void__std::_Fake_no_copy_callable_adapter__winrt::Windows::Internal::NetworkUX::Firewall::implementation::FirewallDialogBase::CreateDialogAsync_::_2_::_lambda_1______::_2_::_lambda_1__Concurrency::details::_TypeSelectorNoAsync__Concurrency::details::_TaskProcHandle_::invoke_::_1_::catch$5

- ea: `0x18002b5c6`
- end: `0x18002b623`
- name: `_Concurrency::details::_PPLTaskHandle_unsigned_char_Concurrency::task_unsigned_char_::_InitialTaskHandle_void__std::_Task_async_state_void_::_Task_async_state_void__std::_Fake_no_copy_callable_adapter__winrt::Windows::Internal::NetworkUX::Firewall::implementation::FirewallDialogBase::CreateDialogAsync_::_2_::_lambda_1______::_2_::_lambda_1__Concurrency::details::_TypeSelectorNoAsync__Concurrency::details::_TaskProcHandle_::invoke_::_1_::catch$5`
- size: `93`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `service_task`

## callees

- `0x180018ac4`

## import_xrefs

- `msvcp_win!?__ExceptionPtrDestroy@@YAXPEAX@Z` at `0x18002b60a`
- `msvcp_win!?__ExceptionPtrDestroy@@YAXPEAX@Z` at `0x18002b60a`
- `msvcp_win!?__ExceptionPtrCreate@@YAXPEAX@Z` at `0x18002b5e8`
- `msvcp_win!?__ExceptionPtrCreate@@YAXPEAX@Z` at `0x18002b5e8`
- `msvcp_win!?__ExceptionPtrCurrentException@@YAXPEAX@Z` at `0x18002b5f2`
- `msvcp_win!?__ExceptionPtrCurrentException@@YAXPEAX@Z` at `0x18002b5f2`

## pseudocode

```c
__int64 __fastcall Concurrency::details::_PPLTaskHandle_unsigned_char_Concurrency::task_unsigned_char_::_InitialTaskHandle_void__std::_Task_async_state_void_::_Task_async_state_void__std::_Fake_no_copy_callable_adapter__winrt::Windows::Internal::NetworkUX::Firewall::implementation::FirewallDialogBase::CreateDialogAsync_::_2_::_lambda_1______::_2_::_lambda_1__Concurrency::details::_TypeSelectorNoAsync__Concurrency::details::_TaskProcHandle_::invoke_::_1_::catch_5(
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
0x18002b5c6  mov     [rsp+arg_8], rdx
0x18002b5cb  push    rbx
0x18002b5cc  push    rbp
0x18002b5cd  sub     rsp, 38h
0x18002b5d1  mov     rbp, rdx
0x18002b5d4  mov     rax, [rbp+60h]
0x18002b5d8  mov     rbx, [rax+8]
0x18002b5dc  xorps   xmm0, xmm0
0x18002b5df  movdqu  xmmword ptr [rbp+30h], xmm0
0x18002b5e4  lea     rcx, [rbp+30h]
0x18002b5e8  call    cs:__imp_?__ExceptionPtrCreate@@YAXPEAX@Z; __ExceptionPtrCreate(void *)
0x18002b5ee  lea     rcx, [rbp+30h]
0x18002b5f2  call    cs:__imp_?__ExceptionPtrCurrentException@@YAXPEAX@Z; __ExceptionPtrCurrentException(void *)
0x18002b5f8  nop
0x18002b5f9  lea     rdx, [rbp+30h]; struct std::exception_ptr *
0x18002b5fd  mov     rcx, rbx; this
0x18002b600  call    ?_CancelWithException@_Task_impl_base@details@Concurrency@@QEAA_NAEBVexception_ptr@std@@@Z; Concurrency::details::_Task_impl_base::_CancelWithException(std::exception_ptr const &)
0x18002b605  nop
0x18002b606  lea     rcx, [rbp+30h]
0x18002b60a  call    cs:__imp_?__ExceptionPtrDestroy@@YAXPEAX@Z; __ExceptionPtrDestroy(void *)
0x18002b610  nop
0x18002b611  mov     rax, 0
0x18002b61b  add     rsp, 38h
0x18002b61f  pop     rbp
0x18002b620  pop     rbx
0x18002b621  retn
```
