# _DisableMdmDiagnosticsCleanupTask_::_1_::dtor$4

- ea: `0x140009f12`
- end: `0x140009f1e`
- name: `_DisableMdmDiagnosticsCleanupTask_::_1_::dtor$4`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `service_task`

## callees

- `0x1400035f0`

## pseudocode

```c
void __fastcall DisableMdmDiagnosticsCleanupTask_::_1_::dtor_4(__int64 a1, __int64 a2)
{
  _variant_t::~_variant_t((_variant_t *)(a2 + 88));
}

```

## disassembly

```asm
0x140009f12  lea     rcx, [rdx+58h]; this
0x140009f19  jmp     ??1_variant_t@@QEAA@XZ; _variant_t::~_variant_t(void)
```
