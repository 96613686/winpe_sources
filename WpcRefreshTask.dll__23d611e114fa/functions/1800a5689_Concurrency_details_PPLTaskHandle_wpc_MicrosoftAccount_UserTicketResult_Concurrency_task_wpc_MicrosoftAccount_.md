# _Concurrency::details::_PPLTaskHandle_wpc::MicrosoftAccount::UserTicketResult_Concurrency::task_wpc::MicrosoftAccount::UserTicketResult_::_InitialTaskHandle_wpc::MicrosoftAccount::UserTicketResult__lambda_76df95f8bc94559cee4cf8aea0755487__Concurrency::details::_TypeSelectorNoAsync__Concurrency::details::_TaskProcHandle_::invoke_::_1_::catch$17

- ea: `0x1800a5689`
- end: `0x1800a56e9`
- name: `_Concurrency::details::_PPLTaskHandle_wpc::MicrosoftAccount::UserTicketResult_Concurrency::task_wpc::MicrosoftAccount::UserTicketResult_::_InitialTaskHandle_wpc::MicrosoftAccount::UserTicketResult__lambda_76df95f8bc94559cee4cf8aea0755487__Concurrency::details::_TypeSelectorNoAsync__Concurrency::details::_TaskProcHandle_::invoke_::_1_::catch$17`
- size: `96`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callees

- `0x18001a898`

## import_xrefs

- `msvcp_win!?__ExceptionPtrCreate@@YAXPEAX@Z` at `0x1800a56ae`
- `msvcp_win!?__ExceptionPtrCreate@@YAXPEAX@Z` at `0x1800a56ae`
- `msvcp_win!?__ExceptionPtrCurrentException@@YAXPEAX@Z` at `0x1800a56b8`
- `msvcp_win!?__ExceptionPtrCurrentException@@YAXPEAX@Z` at `0x1800a56b8`
- `msvcp_win!?__ExceptionPtrDestroy@@YAXPEAX@Z` at `0x1800a56d0`
- `msvcp_win!?__ExceptionPtrDestroy@@YAXPEAX@Z` at `0x1800a56d0`

## pseudocode

```c
__int64 __fastcall Concurrency::details::_PPLTaskHandle_wpc::MicrosoftAccount::UserTicketResult_Concurrency::task_wpc::MicrosoftAccount::UserTicketResult_::_InitialTaskHandle_wpc::MicrosoftAccount::UserTicketResult__lambda_76df95f8bc94559cee4cf8aea0755487__Concurrency::details::_TypeSelectorNoAsync__Concurrency::details::_TaskProcHandle_::invoke_::_1_::catch_17(
        __int64 a1,
        __int64 a2)
{
  Concurrency::details::_Task_impl_base *v3; // rbx

  v3 = *(Concurrency::details::_Task_impl_base **)(*(_QWORD *)(a2 + 304) + 8LL);
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
0x1800a5689  mov     [rsp+arg_8], rdx
0x1800a568e  push    rbx
0x1800a568f  push    rbp
0x1800a5690  sub     rsp, 38h
0x1800a5694  mov     rbp, rdx
0x1800a5697  mov     rax, [rbp+130h]
0x1800a569e  mov     rbx, [rax+8]
0x1800a56a2  xorps   xmm0, xmm0
0x1800a56a5  movdqu  xmmword ptr [rbp+30h], xmm0
0x1800a56aa  lea     rcx, [rbp+30h]
0x1800a56ae  call    cs:__imp_?__ExceptionPtrCreate@@YAXPEAX@Z; __ExceptionPtrCreate(void *)
0x1800a56b4  lea     rcx, [rbp+30h]
0x1800a56b8  call    cs:__imp_?__ExceptionPtrCurrentException@@YAXPEAX@Z; __ExceptionPtrCurrentException(void *)
0x1800a56be  nop
0x1800a56bf  lea     rdx, [rbp+30h]; struct std::exception_ptr *
0x1800a56c3  mov     rcx, rbx; this
0x1800a56c6  call    ?_CancelWithException@_Task_impl_base@details@Concurrency@@QEAA_NAEBVexception_ptr@std@@@Z; Concurrency::details::_Task_impl_base::_CancelWithException(std::exception_ptr const &)
0x1800a56cb  nop
0x1800a56cc  lea     rcx, [rbp+30h]
0x1800a56d0  call    cs:__imp_?__ExceptionPtrDestroy@@YAXPEAX@Z; __ExceptionPtrDestroy(void *)
0x1800a56d6  nop
0x1800a56d7  mov     rax, 0
0x1800a56e1  add     rsp, 38h
0x1800a56e5  pop     rbp
0x1800a56e6  pop     rbx
0x1800a56e7  retn
```
