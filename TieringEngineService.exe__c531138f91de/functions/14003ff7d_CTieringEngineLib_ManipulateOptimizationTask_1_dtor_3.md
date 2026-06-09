# _CTieringEngineLib::ManipulateOptimizationTask_::_1_::dtor$3

- ea: `0x14003ff7d`
- end: `0x14003ff89`
- name: `_CTieringEngineLib::ManipulateOptimizationTask_::_1_::dtor$3`
- size: `12`
- prototype: `void __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `service_task`

## callees

- `0x14000565c`

## pseudocode

```c
void __fastcall CTieringEngineLib::ManipulateOptimizationTask_::_1_::dtor_3(__int64 a1, __int64 a2)
{
  _variant_t::~_variant_t((_variant_t *)(a2 + 72));
}

```

## disassembly

```asm
0x14003ff7d  lea     rcx, [rdx+48h]; this
0x14003ff84  jmp     ??1_variant_t@@QEAA@XZ; _variant_t::~_variant_t(void)
```
