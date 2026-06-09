# _Concurrency::details::_Task_impl_base::_RegisterCancellation_::_1_::dtor$4

- ea: `0x180018434`
- end: `0x180018440`
- name: `_Concurrency::details::_Task_impl_base::_RegisterCancellation_::_1_::dtor$4`
- size: `12`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `service_task`

## callees

- `0x18000fc90`

## pseudocode

```c
__int64 __fastcall Concurrency::details::_Task_impl_base::_RegisterCancellation_::_1_::dtor_4(__int64 a1, __int64 a2)
{
  return std::lock_guard<std::mutex>::~lock_guard<std::mutex>(a2 + 112);
}

```

## disassembly

```asm
0x180018434  lea     rcx, [rdx+70h]
0x18001843b  jmp     ??1?$lock_guard@Vmutex@std@@@std@@QEAA@XZ; std::lock_guard<std::mutex>::~lock_guard<std::mutex>(void)
```
