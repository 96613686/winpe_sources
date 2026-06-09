# _Concurrency::details::_PPLTaskHandle_HttpRequest::HttpResponse_Concurrency::task_HttpRequest::HttpResponse_::_InitialTaskHandle_HttpRequest::HttpResponse__lambda_8130d6685246581cf174266372fcb501__Concurrency::details::_TypeSelectorNoAsync__Concurrency::details::_TaskProcHandle_::invoke_::_1_::catch$5

- ea: `0x1800a830b`
- end: `0x1800a8368`
- name: `_Concurrency::details::_PPLTaskHandle_HttpRequest::HttpResponse_Concurrency::task_HttpRequest::HttpResponse_::_InitialTaskHandle_HttpRequest::HttpResponse__lambda_8130d6685246581cf174266372fcb501__Concurrency::details::_TypeSelectorNoAsync__Concurrency::details::_TaskProcHandle_::invoke_::_1_::catch$5`
- size: `93`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `service_task`

## callees

- `0x18001a898`

## import_xrefs

- `msvcp_win!?__ExceptionPtrCreate@@YAXPEAX@Z` at `0x1800a832d`
- `msvcp_win!?__ExceptionPtrCreate@@YAXPEAX@Z` at `0x1800a832d`
- `msvcp_win!?__ExceptionPtrCurrentException@@YAXPEAX@Z` at `0x1800a8337`
- `msvcp_win!?__ExceptionPtrCurrentException@@YAXPEAX@Z` at `0x1800a8337`
- `msvcp_win!?__ExceptionPtrDestroy@@YAXPEAX@Z` at `0x1800a834f`
- `msvcp_win!?__ExceptionPtrDestroy@@YAXPEAX@Z` at `0x1800a834f`

## pseudocode

```c
__int64 __fastcall Concurrency::details::_PPLTaskHandle_HttpRequest::HttpResponse_Concurrency::task_HttpRequest::HttpResponse_::_InitialTaskHandle_HttpRequest::HttpResponse__lambda_8130d6685246581cf174266372fcb501__Concurrency::details::_TypeSelectorNoAsync__Concurrency::details::_TaskProcHandle_::invoke_::_1_::catch_5(
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
0x1800a830b  mov     [rsp+arg_8], rdx
0x1800a8310  push    rbx
0x1800a8311  push    rbp
0x1800a8312  sub     rsp, 38h
0x1800a8316  mov     rbp, rdx
0x1800a8319  mov     rax, [rbp+60h]
0x1800a831d  mov     rbx, [rax+8]
0x1800a8321  xorps   xmm0, xmm0
0x1800a8324  movdqu  xmmword ptr [rbp+30h], xmm0
0x1800a8329  lea     rcx, [rbp+30h]
0x1800a832d  call    cs:__imp_?__ExceptionPtrCreate@@YAXPEAX@Z; __ExceptionPtrCreate(void *)
0x1800a8333  lea     rcx, [rbp+30h]
0x1800a8337  call    cs:__imp_?__ExceptionPtrCurrentException@@YAXPEAX@Z; __ExceptionPtrCurrentException(void *)
0x1800a833d  nop
0x1800a833e  lea     rdx, [rbp+30h]; struct std::exception_ptr *
0x1800a8342  mov     rcx, rbx; this
0x1800a8345  call    ?_CancelWithException@_Task_impl_base@details@Concurrency@@QEAA_NAEBVexception_ptr@std@@@Z; Concurrency::details::_Task_impl_base::_CancelWithException(std::exception_ptr const &)
0x1800a834a  nop
0x1800a834b  lea     rcx, [rbp+30h]
0x1800a834f  call    cs:__imp_?__ExceptionPtrDestroy@@YAXPEAX@Z; __ExceptionPtrDestroy(void *)
0x1800a8355  nop
0x1800a8356  mov     rax, 0
0x1800a8360  add     rsp, 38h
0x1800a8364  pop     rbp
0x1800a8365  pop     rbx
0x1800a8366  retn
```
