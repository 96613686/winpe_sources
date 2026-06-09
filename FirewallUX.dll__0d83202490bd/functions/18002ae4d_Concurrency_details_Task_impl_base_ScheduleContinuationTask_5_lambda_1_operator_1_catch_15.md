# __Concurrency::details::_Task_impl_base::_ScheduleContinuationTask_::_5_::_lambda_1_::operator()_::_1_::catch$15

- ea: `0x18002ae4d`
- end: `0x18002aea6`
- name: `__Concurrency::details::_Task_impl_base::_ScheduleContinuationTask_::_5_::_lambda_1_::operator()_::_1_::catch$15`
- size: `89`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `service_task`

## callees

- `0x180018ac4`

## import_xrefs

- `msvcp_win!?__ExceptionPtrDestroy@@YAXPEAX@Z` at `0x18002ae8d`
- `msvcp_win!?__ExceptionPtrDestroy@@YAXPEAX@Z` at `0x18002ae8d`
- `msvcp_win!?__ExceptionPtrCreate@@YAXPEAX@Z` at `0x18002ae6b`
- `msvcp_win!?__ExceptionPtrCreate@@YAXPEAX@Z` at `0x18002ae6b`
- `msvcp_win!?__ExceptionPtrCurrentException@@YAXPEAX@Z` at `0x18002ae75`
- `msvcp_win!?__ExceptionPtrCurrentException@@YAXPEAX@Z` at `0x18002ae75`

## pseudocode

```c
__int64 __fastcall _Concurrency::details::_Task_impl_base::_ScheduleContinuationTask_::_5_::_lambda_1_::operator()_::_1_::catch_15(
        __int64 a1,
        __int64 a2)
{
  Concurrency::details::_Task_impl_base *v3; // rbx

  v3 = *(Concurrency::details::_Task_impl_base **)(a2 + 32);
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
0x18002ae4d  mov     [rsp+arg_8], rdx
0x18002ae52  push    rbx
0x18002ae53  push    rbp
0x18002ae54  sub     rsp, 28h
0x18002ae58  mov     rbp, rdx
0x18002ae5b  mov     rbx, [rbp+20h]
0x18002ae5f  xorps   xmm0, xmm0
0x18002ae62  movdqu  xmmword ptr [rbp+30h], xmm0
0x18002ae67  lea     rcx, [rbp+30h]
0x18002ae6b  call    cs:__imp_?__ExceptionPtrCreate@@YAXPEAX@Z; __ExceptionPtrCreate(void *)
0x18002ae71  lea     rcx, [rbp+30h]
0x18002ae75  call    cs:__imp_?__ExceptionPtrCurrentException@@YAXPEAX@Z; __ExceptionPtrCurrentException(void *)
0x18002ae7b  nop
0x18002ae7c  lea     rdx, [rbp+30h]; struct std::exception_ptr *
0x18002ae80  mov     rcx, rbx; this
0x18002ae83  call    ?_CancelWithException@_Task_impl_base@details@Concurrency@@QEAA_NAEBVexception_ptr@std@@@Z; Concurrency::details::_Task_impl_base::_CancelWithException(std::exception_ptr const &)
0x18002ae88  nop
0x18002ae89  lea     rcx, [rbp+30h]
0x18002ae8d  call    cs:__imp_?__ExceptionPtrDestroy@@YAXPEAX@Z; __ExceptionPtrDestroy(void *)
0x18002ae93  nop
0x18002ae94  mov     rax, 0
0x18002ae9e  add     rsp, 28h
0x18002aea2  pop     rbp
0x18002aea3  pop     rbx
0x18002aea4  retn
```
