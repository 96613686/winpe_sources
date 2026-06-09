# _CTieringEngineLib::ManipulateOptimizationTask_::_1_::dtor$2

- ea: `0x14003ff6b`
- end: `0x14003ff77`
- name: `_CTieringEngineLib::ManipulateOptimizationTask_::_1_::dtor$2`
- size: `12`
- prototype: `void __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `service_task`

## callees

- `0x14000565c`

## pseudocode

```c
void __fastcall CTieringEngineLib::ManipulateOptimizationTask_::_1_::dtor_2(__int64 a1, __int64 a2)
{
  _variant_t::~_variant_t((_variant_t *)(a2 + 96));
}

```

## disassembly

```asm
0x14003ff6b  lea     rcx, [rdx+60h]; this
0x14003ff72  jmp     ??1_variant_t@@QEAA@XZ; _variant_t::~_variant_t(void)
```
