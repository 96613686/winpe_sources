# _std::_Task_async_state_void_::_Task_async_state_void__std::_Fake_no_copy_callable_adapter__lambda_28acef7f84ef4b64850563b8e90ad6f2______::_1_::dtor$1

- ea: `0x180017ece`
- end: `0x180017ee1`
- name: `_std::_Task_async_state_void_::_Task_async_state_void__std::_Fake_no_copy_callable_adapter__lambda_28acef7f84ef4b64850563b8e90ad6f2______::_1_::dtor$1`
- size: `19`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `service_task`

## callees

- `0x180005988`

## pseudocode

```c
__int64 __fastcall std::_Task_async_state_void_::_Task_async_state_void__std::_Fake_no_copy_callable_adapter__lambda_28acef7f84ef4b64850563b8e90ad6f2______::_1_::dtor_1(
        __int64 a1,
        __int64 a2)
{
  return std::shared_ptr<Concurrency::details::_ExceptionHolder>::~shared_ptr<Concurrency::details::_ExceptionHolder>(*(_QWORD *)(a2 + 192) + 272LL);
}

```

## disassembly

```asm
0x180017ece  mov     rcx, [rdx+0C0h]
0x180017ed5  add     rcx, 110h
0x180017edc  jmp     ??1?$shared_ptr@U_ExceptionHolder@details@Concurrency@@@std@@QEAA@XZ; std::shared_ptr<Concurrency::details::_ExceptionHolder>::~shared_ptr<Concurrency::details::_ExceptionHolder>(void)
```
