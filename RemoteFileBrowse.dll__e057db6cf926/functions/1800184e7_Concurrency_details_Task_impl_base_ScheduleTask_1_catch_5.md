# _Concurrency::details::_Task_impl_base::_ScheduleTask_::_1_::catch$5

- ea: `0x1800184e7`
- end: `0x180018547`
- name: `_Concurrency::details::_Task_impl_base::_ScheduleTask_::_1_::catch$5`
- size: `96`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `2`
- tags: `service_task`

## callees

- `0x180011744`
- `0x1800184e7`

## import_xrefs

- `msvcp_win!?__ExceptionPtrCreate@@YAXPEAX@Z` at `0x18001850c`
- `msvcp_win!?__ExceptionPtrCreate@@YAXPEAX@Z` at `0x18001850c`
- `msvcp_win!?__ExceptionPtrCurrentException@@YAXPEAX@Z` at `0x180018516`
- `msvcp_win!?__ExceptionPtrCurrentException@@YAXPEAX@Z` at `0x180018516`
- `msvcp_win!?__ExceptionPtrDestroy@@YAXPEAX@Z` at `0x18001852e`
- `msvcp_win!?__ExceptionPtrDestroy@@YAXPEAX@Z` at `0x18001852e`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
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
0x1800184e7  mov     [rsp+arg_8], rdx
0x1800184ec  push    rbx
0x1800184ed  push    rbp
0x1800184ee  sub     rsp, 28h
0x1800184f2  mov     rbp, rdx
0x1800184f5  mov     rbx, [rbp+40h]
0x1800184f9  cmp     qword ptr [rbx+10h], 0
0x1800184fe  jnz     short loc_180018535
0x180018500  xorps   xmm0, xmm0
0x180018503  movdqu  xmmword ptr [rbp+20h], xmm0
0x180018508  lea     rcx, [rbp+20h]
0x18001850c  call    cs:__imp_?__ExceptionPtrCreate@@YAXPEAX@Z; __ExceptionPtrCreate(void *)
0x180018512  lea     rcx, [rbp+20h]
0x180018516  call    cs:__imp_?__ExceptionPtrCurrentException@@YAXPEAX@Z; __ExceptionPtrCurrentException(void *)
0x18001851c  nop
0x18001851d  lea     rdx, [rbp+20h]; struct std::exception_ptr *
0x180018521  mov     rcx, rbx; this
0x180018524  call    ?_CancelWithException@_Task_impl_base@details@Concurrency@@QEAA_NAEBVexception_ptr@std@@@Z; Concurrency::details::_Task_impl_base::_CancelWithException(std::exception_ptr const &)
0x180018529  nop
0x18001852a  lea     rcx, [rbp+20h]
0x18001852e  call    cs:__imp_?__ExceptionPtrDestroy@@YAXPEAX@Z; __ExceptionPtrDestroy(void *)
0x180018534  nop
0x180018535  mov     rax, 0
0x18001853f  add     rsp, 28h
0x180018543  pop     rbp
0x180018544  pop     rbx
0x180018545  retn
```
