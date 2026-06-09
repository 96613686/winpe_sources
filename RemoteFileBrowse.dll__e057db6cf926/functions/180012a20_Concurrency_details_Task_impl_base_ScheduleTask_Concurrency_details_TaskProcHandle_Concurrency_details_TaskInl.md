# Concurrency::details::_Task_impl_base::_ScheduleTask(Concurrency::details::_TaskProcHandle *,Concurrency::details::_TaskInliningMode)

- ea: `0x180012a20`
- end: `0x180012a95`
- name: `?_ScheduleTask@_Task_impl_base@details@Concurrency@@QEAAXPEAU_TaskProcHandle@23@W4_TaskInliningMode@23@@Z`
- size: `117`
- prototype: `void __fastcall(Concurrency::details::_Task_impl_base *, void *, int)`
- caller_count: `4`
- callee_count: `3`
- tags: `service_task`

## callers

- `0x18000e664`
- `0x180010298`
- `0x180011e40`
- `0x18001277c`

## callees

- `0x180012a20`
- `0x1800130b8`
- `0x180019010`

## pseudocode

```c
void __fastcall Concurrency::details::_Task_impl_base::_ScheduleTask(
        Concurrency::details::_Task_impl_base *a1,
        void *a2,
        int a3)
{
  void (__fastcall ***v4)(_QWORD, void (__fastcall *)(void *), void *); // rcx
  __int128 v5; // [rsp+20h] [rbp-18h] BYREF
  void *v7; // [rsp+58h] [rbp+20h] BYREF

  try
  {
    if ( a3 == -1 )
    {
      v7 = a2;
      (*(void (__fastcall **)(void *))(*(_QWORD *)a2 + 8LL))(a2);
      (**(void (__fastcall ***)(void *, __int64))a2)(a2, 1);
    }
    else
    {
      v4 = (void (__fastcall ***)(_QWORD, void (__fastcall *)(void *), void *))*((_QWORD *)a1 + 38);
      if ( v4 )
        (**v4)(v4, Concurrency::details::_TaskProcHandle::_RunChoreBridge, a2);
      else
        Concurrency::details::_DefaultPPLTaskScheduler::schedule(
          (Concurrency::details::_DefaultPPLTaskScheduler *)&v7,
          (void (*)(void *))Concurrency::details::_TaskProcHandle::_RunChoreBridge,
          a2);
    }
  }
  catch ( Concurrency::task_canceled )
  {
    return;
  }
  catch ( Concurrency::details::_Interruption_exception )
  {
    return;
  }
  catch ( ... )
  {
    if ( !*((_QWORD *)a1 + 2) )
    {
      v5 = 0;
      __ExceptionPtrCreate(&v5);
      __ExceptionPtrCurrentException(&v5);
      Concurrency::details::_Task_impl_base::_CancelWithException(a1, (const struct std::exception_ptr *)&v5);
      __ExceptionPtrDestroy(&v5);
    }
  }
}

```

## disassembly

```asm
0x180012a20  mov     [rsp+arg_0], rcx
0x180012a25  push    rbx
0x180012a26  sub     rsp, 30h
0x180012a2a  mov     rbx, rdx
0x180012a2d  cmp     r8d, 0FFFFFFFFh
0x180012a31  jnz     short loc_180012A5D
0x180012a33  mov     [rsp+38h+arg_18], rdx
0x180012a38  mov     rax, [rdx]
0x180012a3b  mov     rcx, rdx
0x180012a3e  mov     rax, [rax+8]
0x180012a42  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012a47  nop
0x180012a48  mov     rax, [rbx]
0x180012a4b  mov     edx, 1
0x180012a50  mov     rcx, rbx
0x180012a53  mov     rax, [rax]
0x180012a56  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012a5b  jmp     short loc_180012A8B
0x180012a5d  mov     rcx, [rcx+130h]
0x180012a64  mov     r8, rbx; void *
0x180012a67  lea     rdx, ?_RunChoreBridge@_TaskProcHandle@details@Concurrency@@SAXPEAX@Z; void (*)(void *)
0x180012a6e  test    rcx, rcx
0x180012a71  jz      short loc_180012A80
0x180012a73  mov     rax, [rcx]
0x180012a76  mov     rax, [rax]
0x180012a79  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012a7e  jmp     short loc_180012A8B
0x180012a80  lea     rcx, [rsp+38h+arg_18]; this
0x180012a85  call    ?schedule@_DefaultPPLTaskScheduler@details@Concurrency@@UEAAXP6AXPEAX@Z0@Z; Concurrency::details::_DefaultPPLTaskScheduler::schedule(void (*)(void *),void *)
0x180012a8a  nop
0x180012a8b  add     rsp, 30h
0x180012a8f  pop     rbx
0x180012a90  retn
0x180012a91  jmp     short loc_180012A8B
0x180012a93  jmp     short loc_180012A8B
```
