# _DisableMdmDiagnosticsCleanupTask_::_1_::dtor$2

- ea: `0x140009eee`
- end: `0x140009efa`
- name: `_DisableMdmDiagnosticsCleanupTask_::_1_::dtor$2`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `service_task`

## callees

- `0x1400035f0`

## pseudocode

```c
void __fastcall DisableMdmDiagnosticsCleanupTask_::_1_::dtor_2(__int64 a1, __int64 a2)
{
  _variant_t::~_variant_t((_variant_t *)(a2 + 136));
}

```

## disassembly

```asm
0x140009eee  lea     rcx, [rdx+88h]; this
0x140009ef5  jmp     ??1_variant_t@@QEAA@XZ; _variant_t::~_variant_t(void)
```
