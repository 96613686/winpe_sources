# _Concurrency::details::_Task_impl_base::_ScheduleTask_::_1_::dtor$1

- ea: `0x1800184b1`
- end: `0x1800184bd`
- name: `_Concurrency::details::_Task_impl_base::_ScheduleTask_::_1_::dtor$1`
- size: `12`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `service_task`

## callees

- `0x18000fcc0`

## pseudocode

```c
__int64 __fastcall Concurrency::details::_Task_impl_base::_ScheduleTask_::_1_::dtor_1(__int64 a1, __int64 a2)
{
  return std::unique_ptr<Concurrency::details::_TaskProcHandle>::~unique_ptr<Concurrency::details::_TaskProcHandle>((__int64 (__fastcall ****)(_QWORD, __int64))(a2 + 88));
}

```

## disassembly

```asm
0x1800184b1  lea     rcx, [rdx+58h]
0x1800184b8  jmp     ??1?$unique_ptr@U_TaskProcHandle@details@Concurrency@@U?$default_delete@U_TaskProcHandle@details@Concurrency@@@std@@@std@@QEAA@XZ; std::unique_ptr<Concurrency::details::_TaskProcHandle>::~unique_ptr<Concurrency::details::_TaskProcHandle>(void)
```
