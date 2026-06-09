# _std::_Task_async_state_void_::_Task_async_state_void__std::_Fake_no_copy_callable_adapter__lambda_28acef7f84ef4b64850563b8e90ad6f2______::_1_::dtor$0

- ea: `0x180017ebc`
- end: `0x180017ec8`
- name: `_std::_Task_async_state_void_::_Task_async_state_void__std::_Fake_no_copy_callable_adapter__lambda_28acef7f84ef4b64850563b8e90ad6f2______::_1_::dtor$0`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `service_task`

## callees

- `0x18000fa18`

## pseudocode

```c
void __fastcall std::_Task_async_state_void_::_Task_async_state_void__std::_Fake_no_copy_callable_adapter__lambda_28acef7f84ef4b64850563b8e90ad6f2______::_1_::dtor_0(
        __int64 a1,
        __int64 a2)
{
  std::_Packaged_state<void (void)>::~_Packaged_state<void (void)>(*(_QWORD *)(a2 + 192), a2);
}

```

## disassembly

```asm
0x180017ebc  mov     rcx, [rdx+0C0h]
0x180017ec3  jmp     ??1?$_Packaged_state@$$A6AXXZ@std@@UEAA@XZ; std::_Packaged_state<void (void)>::~_Packaged_state<void (void)>(void)
```
