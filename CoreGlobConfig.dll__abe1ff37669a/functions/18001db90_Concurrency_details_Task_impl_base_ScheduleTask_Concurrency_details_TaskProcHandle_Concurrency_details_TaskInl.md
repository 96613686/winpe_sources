# Concurrency::details::_Task_impl_base::_ScheduleTask(Concurrency::details::_TaskProcHandle *,Concurrency::details::_TaskInliningMode)

- ea: `0x18001db90`
- end: `0x18001dbe2`
- name: `?_ScheduleTask@_Task_impl_base@details@Concurrency@@QEAAXPEAU_TaskProcHandle@23@W4_TaskInliningMode@23@@Z`
- size: `82`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `4`
- callee_count: `4`
- tags: `service_task`

## callers

- `0x180009770`
- `0x1800123a8`
- `0x18001d030`
- `0x18001da24`

## callees

- `0x18001d820`
- `0x18001db90`
- `0x18001ec74`
- `0x180025010`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall Concurrency::details::_Task_impl_base::_ScheduleTask(
        Concurrency::details::_Task_impl_base *a1,
        __int64 (__fastcall ***a2)(_QWORD, __int64),
        int a3)
{
  void (__fastcall ***v3)(_QWORD, void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, __int64)), __int64 (__fastcall ***)(_QWORD, __int64)); // rcx
  const struct std::exception_ptr *v4; // rax
  _QWORD v5[3]; // [rsp+20h] [rbp-18h] BYREF
  char v7; // [rsp+58h] [rbp+20h] BYREF

  try
  {
    if ( a3 == -1 )
    {
      Concurrency::details::_TaskProcHandle::_RunChoreBridge(a2);
    }
    else
    {
      v3 = (void (__fastcall ***)(_QWORD, void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, __int64)), __int64 (__fastcall ***)(_QWORD, __int64)))*((_QWORD *)a1 + 38);
      if ( v3 )
        (**v3)(v3, Concurrency::details::_TaskProcHandle::_RunChoreBridge, a2);
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
      v4 = (const struct std::exception_ptr *)std::current_exception(v5);
      Concurrency::details::_Task_impl_base::_CancelWithException(a1, v4);
      __ExceptionPtrDestroy(v5);
    }
  }
}

```

## disassembly

```asm
0x18001db90  mov     [rsp+arg_0], rcx
0x18001db95  sub     rsp, 38h
0x18001db99  cmp     r8d, 0FFFFFFFFh
0x18001db9d  jnz     short loc_18001DBA9
0x18001db9f  mov     rcx, rdx; void *
0x18001dba2  call    ?_RunChoreBridge@_TaskProcHandle@details@Concurrency@@SAXPEAX@Z; Concurrency::details::_TaskProcHandle::_RunChoreBridge(void *)
0x18001dba7  jmp     short loc_18001DBCA
0x18001dba9  mov     rcx, [rcx+130h]
0x18001dbb0  mov     r8, rdx; void *
0x18001dbb3  lea     rdx, ?_RunChoreBridge@_TaskProcHandle@details@Concurrency@@SAXPEAX@Z; void (*)(void *)
0x18001dbba  test    rcx, rcx
0x18001dbbd  jz      short loc_18001DBCC
0x18001dbbf  mov     rax, [rcx]
0x18001dbc2  mov     rax, [rax]
0x18001dbc5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001dbca  jmp     short loc_18001DBD7
0x18001dbcc  lea     rcx, [rsp+38h+arg_18]; this
0x18001dbd1  call    ?schedule@_DefaultPPLTaskScheduler@details@Concurrency@@UEAAXP6AXPEAX@Z0@Z; Concurrency::details::_DefaultPPLTaskScheduler::schedule(void (*)(void *),void *)
0x18001dbd6  nop
0x18001dbd7  jmp     short loc_18001DBDD
0x18001dbd9  jmp     short loc_18001DBDD
0x18001dbdb  jmp     short $+2
0x18001dbdd  add     rsp, 38h
0x18001dbe1  retn
```
