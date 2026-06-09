# _DisableMdmDiagnosticsCleanupTask_::_1_::dtor$3

- ea: `0x140009f00`
- end: `0x140009f0c`
- name: `_DisableMdmDiagnosticsCleanupTask_::_1_::dtor$3`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `service_task`

## callees

- `0x1400035f0`

## pseudocode

```c
void __fastcall DisableMdmDiagnosticsCleanupTask_::_1_::dtor_3(__int64 a1, __int64 a2)
{
  _variant_t::~_variant_t((_variant_t *)(a2 + 112));
}

```

## disassembly

```asm
0x140009f00  lea     rcx, [rdx+70h]; this
0x140009f07  jmp     ??1_variant_t@@QEAA@XZ; _variant_t::~_variant_t(void)
```
