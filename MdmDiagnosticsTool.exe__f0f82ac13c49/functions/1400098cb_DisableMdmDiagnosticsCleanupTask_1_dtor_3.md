# _DisableMdmDiagnosticsCleanupTask_::_1_::dtor$3

- ea: `0x1400098cb`
- end: `0x1400098d7`
- name: `_DisableMdmDiagnosticsCleanupTask_::_1_::dtor$3`
- size: `12`
- prototype: `void __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `service_task`

## callees

- `0x140003568`

## pseudocode

```c
void __fastcall DisableMdmDiagnosticsCleanupTask_::_1_::dtor_3(__int64 a1, __int64 a2)
{
  _variant_t::~_variant_t((VARIANTARG *)(a2 + 112));
}

```

## disassembly

```asm
0x1400098cb  lea     rcx, [rdx+70h]; this
0x1400098d2  jmp     ??1_variant_t@@QEAA@XZ; _variant_t::~_variant_t(void)
```
