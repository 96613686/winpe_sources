# _Concurrency::details::_Task_impl_base::_RunTaskContinuations_::_1_::dtor$0

- ea: `0x180018098`
- end: `0x1800180a4`
- name: `_Concurrency::details::_Task_impl_base::_RunTaskContinuations_::_1_::dtor$0`
- size: `12`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `service_task`

## callees

- `0x180005988`

## pseudocode

```c
__int64 __fastcall Concurrency::details::_Task_impl_base::_RunTaskContinuations_::_1_::dtor_0(__int64 a1, __int64 a2)
{
  return std::shared_ptr<Concurrency::details::_ExceptionHolder>::~shared_ptr<Concurrency::details::_ExceptionHolder>(a2 + 48);
}

```

## disassembly

```asm
0x180018098  lea     rcx, [rdx+30h]
0x18001809f  jmp     ??1?$shared_ptr@U_ExceptionHolder@details@Concurrency@@@std@@QEAA@XZ; std::shared_ptr<Concurrency::details::_ExceptionHolder>::~shared_ptr<Concurrency::details::_ExceptionHolder>(void)
```
