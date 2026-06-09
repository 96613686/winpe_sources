# _std::_Task_async_state_void_::_Task_async_state_void__std::_Fake_no_copy_callable_adapter__lambda_28acef7f84ef4b64850563b8e90ad6f2______::_1_::dtor$8

- ea: `0x180017ee7`
- end: `0x180017ef7`
- name: `_std::_Task_async_state_void_::_Task_async_state_void__std::_Fake_no_copy_callable_adapter__lambda_28acef7f84ef4b64850563b8e90ad6f2______::_1_::dtor$8`
- size: `16`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `service_task`

## callees

- `0x1800100e8`

## pseudocode

```c
void __fastcall std::_Task_async_state_void_::_Task_async_state_void__std::_Fake_no_copy_callable_adapter__lambda_28acef7f84ef4b64850563b8e90ad6f2______::_1_::dtor_8(
        __int64 a1,
        __int64 a2)
{
  Concurrency::cancellation_token::~cancellation_token((volatile signed __int32 **)(*(_QWORD *)(a2 + 208) + 24LL));
}

```

## disassembly

```asm
0x180017ee7  mov     rcx, [rdx+0D0h]
0x180017eee  add     rcx, 18h; this
0x180017ef2  jmp     ??1cancellation_token@Concurrency@@QEAA@XZ; Concurrency::cancellation_token::~cancellation_token(void)
```
