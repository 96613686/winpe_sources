# _Concurrency::details::_Task_impl_unsigned_char_::_CancelAndRunContinuations_::_1_::dtor$0

- ea: `0x1800182ea`
- end: `0x1800182f6`
- name: `_Concurrency::details::_Task_impl_unsigned_char_::_CancelAndRunContinuations_::_1_::dtor$0`
- size: `12`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `service_task`

## callees

- `0x18000fc90`

## pseudocode

```c
__int64 __fastcall Concurrency::details::_Task_impl_unsigned_char_::_CancelAndRunContinuations_::_1_::dtor_0(
        __int64 a1,
        __int64 a2)
{
  return std::lock_guard<std::mutex>::~lock_guard<std::mutex>(a2 + 32);
}

```

## disassembly

```asm
0x1800182ea  lea     rcx, [rdx+20h]
0x1800182f1  jmp     ??1?$lock_guard@Vmutex@std@@@std@@QEAA@XZ; std::lock_guard<std::mutex>::~lock_guard<std::mutex>(void)
```
