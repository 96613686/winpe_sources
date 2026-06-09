# _DisableMdmDiagnosticsCleanupTask_::_1_::dtor$5

- ea: `0x140009f24`
- end: `0x140009f30`
- name: `_DisableMdmDiagnosticsCleanupTask_::_1_::dtor$5`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `service_task`

## callees

- `0x1400035f0`

## pseudocode

```c
void __fastcall DisableMdmDiagnosticsCleanupTask_::_1_::dtor_5(__int64 a1, __int64 a2)
{
  _variant_t::~_variant_t((_variant_t *)(a2 + 64));
}

```

## disassembly

```asm
0x140009f24  lea     rcx, [rdx+40h]; this
0x140009f2b  jmp     ??1_variant_t@@QEAA@XZ; _variant_t::~_variant_t(void)
```
