# _Concurrency::details::_TaskProcThunk::_Bridge_::_1_::dtor$0

- ea: `0x18001816f`
- end: `0x18001817b`
- name: `_Concurrency::details::_TaskProcThunk::_Bridge_::_1_::dtor$0`
- size: `12`
- prototype: `void __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `service_task`

## callees

- `0x18000fef4`

## pseudocode

```c
void __fastcall Concurrency::details::_TaskProcThunk::_Bridge_::_1_::dtor_0(__int64 a1, __int64 a2)
{
  Concurrency::details::_TaskProcThunk::_Holder::~_Holder(
    (Concurrency::details::_TaskProcThunk::_Holder *)(a2 + 48),
    a2);
}

```

## disassembly

```asm
0x18001816f  lea     rcx, [rdx+30h]; this
0x180018176  jmp     ??1_Holder@_TaskProcThunk@details@Concurrency@@QEAA@XZ; Concurrency::details::_TaskProcThunk::_Holder::~_Holder(void)
```
