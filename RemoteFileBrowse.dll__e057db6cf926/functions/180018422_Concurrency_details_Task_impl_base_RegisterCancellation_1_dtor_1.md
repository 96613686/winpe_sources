# _Concurrency::details::_Task_impl_base::_RegisterCancellation_::_1_::dtor$1

- ea: `0x180018422`
- end: `0x18001842e`
- name: `_Concurrency::details::_Task_impl_base::_RegisterCancellation_::_1_::dtor$1`
- size: `12`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `service_task`

## callees

- `0x18000f90c`

## pseudocode

```c
__int64 __fastcall Concurrency::details::_Task_impl_base::_RegisterCancellation_::_1_::dtor_1(__int64 a1, __int64 a2)
{
  return std::weak_ptr<Concurrency::details::_Task_impl_base>::~weak_ptr<Concurrency::details::_Task_impl_base>(a2 + 32);
}

```

## disassembly

```asm
0x180018422  lea     rcx, [rdx+20h]
0x180018429  jmp     ??1?$weak_ptr@U_Task_impl_base@details@Concurrency@@@std@@QEAA@XZ; std::weak_ptr<Concurrency::details::_Task_impl_base>::~weak_ptr<Concurrency::details::_Task_impl_base>(void)
```
