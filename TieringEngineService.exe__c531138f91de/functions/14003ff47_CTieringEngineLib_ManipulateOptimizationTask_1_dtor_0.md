# _CTieringEngineLib::ManipulateOptimizationTask_::_1_::dtor$0

- ea: `0x14003ff47`
- end: `0x14003ff53`
- name: `_CTieringEngineLib::ManipulateOptimizationTask_::_1_::dtor$0`
- size: `12`
- prototype: `void __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `service_task`

## callees

- `0x14000565c`

## pseudocode

```c
void __fastcall CTieringEngineLib::ManipulateOptimizationTask_::_1_::dtor_0(__int64 a1, __int64 a2)
{
  _variant_t::~_variant_t((_variant_t *)(a2 + 144));
}

```

## disassembly

```asm
0x14003ff47  lea     rcx, [rdx+90h]; this
0x14003ff4e  jmp     ??1_variant_t@@QEAA@XZ; _variant_t::~_variant_t(void)
```
