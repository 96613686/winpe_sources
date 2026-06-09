# _Concurrency::details::_Task_impl_base::_ScheduleTask_::_1_::catch$5

- ea: `0x18006c162`
- end: `0x18006c1c2`
- name: `_Concurrency::details::_Task_impl_base::_ScheduleTask_::_1_::catch$5`
- size: `96`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `service_task`

## callees

- `0x180038408`
- `0x18006c162`

## import_xrefs

- `msvcp_win!?__ExceptionPtrCreate@@YAXPEAX@Z` at `0x18006c187`
- `msvcp_win!?__ExceptionPtrCreate@@YAXPEAX@Z` at `0x18006c187`
- `msvcp_win!?__ExceptionPtrCurrentException@@YAXPEAX@Z` at `0x18006c191`
- `msvcp_win!?__ExceptionPtrCurrentException@@YAXPEAX@Z` at `0x18006c191`
- `msvcp_win!?__ExceptionPtrDestroy@@YAXPEAX@Z` at `0x18006c1a9`
- `msvcp_win!?__ExceptionPtrDestroy@@YAXPEAX@Z` at `0x18006c1a9`

## pseudocode

```c
__int64 __fastcall Concurrency::details::_Task_impl_base::_ScheduleTask_::_1_::catch_5(__int64 a1, __int64 a2)
{
  Concurrency::details::_Task_impl_base *v3; // rbx

  v3 = *(Concurrency::details::_Task_impl_base **)(a2 + 64);
  if ( !*((_QWORD *)v3 + 2) )
  {
    *(_OWORD *)(a2 + 32) = 0;
    __ExceptionPtrCreate((void *)(a2 + 32));
    __ExceptionPtrCurrentException((void *)(a2 + 32));
    Concurrency::details::_Task_impl_base::_CancelWithException(v3, (const struct std::exception_ptr *)(a2 + 32));
    __ExceptionPtrDestroy((void *)(a2 + 32));
  }
  return 0;
}

```

## disassembly

```asm
0x18006c162  mov     [rsp+arg_8], rdx
0x18006c167  push    rbx
0x18006c168  push    rbp
0x18006c169  sub     rsp, 28h
0x18006c16d  mov     rbp, rdx
0x18006c170  mov     rbx, [rbp+40h]
0x18006c174  cmp     qword ptr [rbx+10h], 0
0x18006c179  jnz     short loc_18006C1B0
0x18006c17b  xorps   xmm0, xmm0
0x18006c17e  movdqu  xmmword ptr [rbp+20h], xmm0
0x18006c183  lea     rcx, [rbp+20h]
0x18006c187  call    cs:__imp_?__ExceptionPtrCreate@@YAXPEAX@Z; __ExceptionPtrCreate(void *)
0x18006c18d  lea     rcx, [rbp+20h]
0x18006c191  call    cs:__imp_?__ExceptionPtrCurrentException@@YAXPEAX@Z; __ExceptionPtrCurrentException(void *)
0x18006c197  nop
0x18006c198  lea     rdx, [rbp+20h]; struct std::exception_ptr *
0x18006c19c  mov     rcx, rbx; this
0x18006c19f  call    ?_CancelWithException@_Task_impl_base@details@Concurrency@@QEAA_NAEBVexception_ptr@std@@@Z; Concurrency::details::_Task_impl_base::_CancelWithException(std::exception_ptr const &)
0x18006c1a4  nop
0x18006c1a5  lea     rcx, [rbp+20h]
0x18006c1a9  call    cs:__imp_?__ExceptionPtrDestroy@@YAXPEAX@Z; __ExceptionPtrDestroy(void *)
0x18006c1af  nop
0x18006c1b0  mov     rax, 0
0x18006c1ba  add     rsp, 28h
0x18006c1be  pop     rbp
0x18006c1bf  pop     rbx
0x18006c1c0  retn
```
