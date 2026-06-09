# _Concurrency::details::_Task_impl_base::_ScheduleTask_::_1_::catch$5

- ea: `0x180087517`
- end: `0x180087577`
- name: `_Concurrency::details::_Task_impl_base::_ScheduleTask_::_1_::catch$5`
- size: `96`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `service_task`

## callees

- `0x1800717a4`
- `0x180087517`

## import_xrefs

- `msvcp_win!?__ExceptionPtrCurrentException@@YAXPEAX@Z` at `0x180087546`
- `msvcp_win!?__ExceptionPtrCurrentException@@YAXPEAX@Z` at `0x180087546`
- `msvcp_win!?__ExceptionPtrDestroy@@YAXPEAX@Z` at `0x18008755e`
- `msvcp_win!?__ExceptionPtrDestroy@@YAXPEAX@Z` at `0x18008755e`
- `msvcp_win!?__ExceptionPtrCreate@@YAXPEAX@Z` at `0x18008753c`
- `msvcp_win!?__ExceptionPtrCreate@@YAXPEAX@Z` at `0x18008753c`

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
0x180087517  mov     [rsp+arg_8], rdx
0x18008751c  push    rbx
0x18008751d  push    rbp
0x18008751e  sub     rsp, 28h
0x180087522  mov     rbp, rdx
0x180087525  mov     rbx, [rbp+40h]
0x180087529  cmp     qword ptr [rbx+10h], 0
0x18008752e  jnz     short loc_180087565
0x180087530  xorps   xmm0, xmm0
0x180087533  movdqu  xmmword ptr [rbp+20h], xmm0
0x180087538  lea     rcx, [rbp+20h]
0x18008753c  call    cs:__imp_?__ExceptionPtrCreate@@YAXPEAX@Z; __ExceptionPtrCreate(void *)
0x180087542  lea     rcx, [rbp+20h]
0x180087546  call    cs:__imp_?__ExceptionPtrCurrentException@@YAXPEAX@Z; __ExceptionPtrCurrentException(void *)
0x18008754c  nop
0x18008754d  lea     rdx, [rbp+20h]; struct std::exception_ptr *
0x180087551  mov     rcx, rbx; this
0x180087554  call    ?_CancelWithException@_Task_impl_base@details@Concurrency@@QEAA_NAEBVexception_ptr@std@@@Z; Concurrency::details::_Task_impl_base::_CancelWithException(std::exception_ptr const &)
0x180087559  nop
0x18008755a  lea     rcx, [rbp+20h]
0x18008755e  call    cs:__imp_?__ExceptionPtrDestroy@@YAXPEAX@Z; __ExceptionPtrDestroy(void *)
0x180087564  nop
0x180087565  mov     rax, 0
0x18008756f  add     rsp, 28h
0x180087573  pop     rbp
0x180087574  pop     rbx
0x180087575  retn
```
