# _CTieringEngineLib::ManipulateOptimizationTask_::_1_::dtor$11

- ea: `0x14003ffa1`
- end: `0x14003ffad`
- name: `_CTieringEngineLib::ManipulateOptimizationTask_::_1_::dtor$11`
- size: `12`
- prototype: `void __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `file_ops, service_task`

## callees

- `0x140001a00`

## pseudocode

```c
void __fastcall CTieringEngineLib::ManipulateOptimizationTask_::_1_::dtor_11(__int64 a1, __int64 a2)
{
  operator delete(*(void **)(a2 + 472));
}

```

## disassembly

```asm
0x14003ffa1  mov     rcx, [rdx+1D8h]; Block
0x14003ffa8  jmp     ??3@YAXPEAX@Z; operator delete(void *)
```
