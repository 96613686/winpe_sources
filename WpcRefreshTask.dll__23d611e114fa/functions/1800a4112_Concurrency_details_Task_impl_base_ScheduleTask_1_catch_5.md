# _Concurrency::details::_Task_impl_base::_ScheduleTask_::_1_::catch$5

- ea: `0x1800a4112`
- end: `0x1800a4172`
- name: `_Concurrency::details::_Task_impl_base::_ScheduleTask_::_1_::catch$5`
- size: `96`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `service_task`

## callees

- `0x18001a898`
- `0x1800a4112`

## import_xrefs

- `msvcp_win!?__ExceptionPtrCreate@@YAXPEAX@Z` at `0x1800a4137`
- `msvcp_win!?__ExceptionPtrCreate@@YAXPEAX@Z` at `0x1800a4137`
- `msvcp_win!?__ExceptionPtrCurrentException@@YAXPEAX@Z` at `0x1800a4141`
- `msvcp_win!?__ExceptionPtrCurrentException@@YAXPEAX@Z` at `0x1800a4141`
- `msvcp_win!?__ExceptionPtrDestroy@@YAXPEAX@Z` at `0x1800a4159`
- `msvcp_win!?__ExceptionPtrDestroy@@YAXPEAX@Z` at `0x1800a4159`

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
0x1800a4112  mov     [rsp+arg_8], rdx
0x1800a4117  push    rbx
0x1800a4118  push    rbp
0x1800a4119  sub     rsp, 28h
0x1800a411d  mov     rbp, rdx
0x1800a4120  mov     rbx, [rbp+40h]
0x1800a4124  cmp     qword ptr [rbx+10h], 0
0x1800a4129  jnz     short loc_1800A4160
0x1800a412b  xorps   xmm0, xmm0
0x1800a412e  movdqu  xmmword ptr [rbp+20h], xmm0
0x1800a4133  lea     rcx, [rbp+20h]
0x1800a4137  call    cs:__imp_?__ExceptionPtrCreate@@YAXPEAX@Z; __ExceptionPtrCreate(void *)
0x1800a413d  lea     rcx, [rbp+20h]
0x1800a4141  call    cs:__imp_?__ExceptionPtrCurrentException@@YAXPEAX@Z; __ExceptionPtrCurrentException(void *)
0x1800a4147  nop
0x1800a4148  lea     rdx, [rbp+20h]; struct std::exception_ptr *
0x1800a414c  mov     rcx, rbx; this
0x1800a414f  call    ?_CancelWithException@_Task_impl_base@details@Concurrency@@QEAA_NAEBVexception_ptr@std@@@Z; Concurrency::details::_Task_impl_base::_CancelWithException(std::exception_ptr const &)
0x1800a4154  nop
0x1800a4155  lea     rcx, [rbp+20h]
0x1800a4159  call    cs:__imp_?__ExceptionPtrDestroy@@YAXPEAX@Z; __ExceptionPtrDestroy(void *)
0x1800a415f  nop
0x1800a4160  mov     rax, 0
0x1800a416a  add     rsp, 28h
0x1800a416e  pop     rbp
0x1800a416f  pop     rbx
0x1800a4170  retn
```
