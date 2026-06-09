# _CTieringEngineLib::ManipulateOptimizationTask_::_1_::dtor$5

- ea: `0x14003ff8f`
- end: `0x14003ff9b`
- name: `_CTieringEngineLib::ManipulateOptimizationTask_::_1_::dtor$5`
- size: `12`
- prototype: `void __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `service_task`

## callees

- `0x1400055ec`

## pseudocode

```c
void __fastcall CTieringEngineLib::ManipulateOptimizationTask_::_1_::dtor_5(__int64 a1, __int64 a2)
{
  _bstr_t::~_bstr_t((_bstr_t *)(a2 + 472));
}

```

## disassembly

```asm
0x14003ff8f  lea     rcx, [rdx+1D8h]; this
0x14003ff96  jmp     ??1_bstr_t@@QEAA@XZ; _bstr_t::~_bstr_t(void)
```
