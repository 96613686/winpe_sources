# _Concurrency::details::_Task_impl_base::_ScheduleTask_::_1_::catch$5

- ea: `0x18002b3ff`
- end: `0x18002b45f`
- name: `_Concurrency::details::_Task_impl_base::_ScheduleTask_::_1_::catch$5`
- size: `96`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `service_task`

## callees

- `0x180018ac4`
- `0x18002b3ff`

## import_xrefs

- `msvcp_win!?__ExceptionPtrDestroy@@YAXPEAX@Z` at `0x18002b446`
- `msvcp_win!?__ExceptionPtrDestroy@@YAXPEAX@Z` at `0x18002b446`
- `msvcp_win!?__ExceptionPtrCreate@@YAXPEAX@Z` at `0x18002b424`
- `msvcp_win!?__ExceptionPtrCreate@@YAXPEAX@Z` at `0x18002b424`
- `msvcp_win!?__ExceptionPtrCurrentException@@YAXPEAX@Z` at `0x18002b42e`
- `msvcp_win!?__ExceptionPtrCurrentException@@YAXPEAX@Z` at `0x18002b42e`

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
0x18002b3ff  mov     [rsp+arg_8], rdx
0x18002b404  push    rbx
0x18002b405  push    rbp
0x18002b406  sub     rsp, 28h
0x18002b40a  mov     rbp, rdx
0x18002b40d  mov     rbx, [rbp+40h]
0x18002b411  cmp     qword ptr [rbx+10h], 0
0x18002b416  jnz     short loc_18002B44D
0x18002b418  xorps   xmm0, xmm0
0x18002b41b  movdqu  xmmword ptr [rbp+20h], xmm0
0x18002b420  lea     rcx, [rbp+20h]
0x18002b424  call    cs:__imp_?__ExceptionPtrCreate@@YAXPEAX@Z; __ExceptionPtrCreate(void *)
0x18002b42a  lea     rcx, [rbp+20h]
0x18002b42e  call    cs:__imp_?__ExceptionPtrCurrentException@@YAXPEAX@Z; __ExceptionPtrCurrentException(void *)
0x18002b434  nop
0x18002b435  lea     rdx, [rbp+20h]; struct std::exception_ptr *
0x18002b439  mov     rcx, rbx; this
0x18002b43c  call    ?_CancelWithException@_Task_impl_base@details@Concurrency@@QEAA_NAEBVexception_ptr@std@@@Z; Concurrency::details::_Task_impl_base::_CancelWithException(std::exception_ptr const &)
0x18002b441  nop
0x18002b442  lea     rcx, [rbp+20h]
0x18002b446  call    cs:__imp_?__ExceptionPtrDestroy@@YAXPEAX@Z; __ExceptionPtrDestroy(void *)
0x18002b44c  nop
0x18002b44d  mov     rax, 0
0x18002b457  add     rsp, 28h
0x18002b45b  pop     rbp
0x18002b45c  pop     rbx
0x18002b45d  retn
```
