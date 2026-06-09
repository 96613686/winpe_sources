# _DisableMdmDiagnosticsCleanupTask_::_1_::dtor$5

- ea: `0x1400098ef`
- end: `0x1400098fb`
- name: `_DisableMdmDiagnosticsCleanupTask_::_1_::dtor$5`
- size: `12`
- prototype: `void __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `service_task`

## callees

- `0x140003568`

## pseudocode

```c
void __fastcall DisableMdmDiagnosticsCleanupTask_::_1_::dtor_5(__int64 a1, __int64 a2)
{
  _variant_t::~_variant_t((VARIANTARG *)(a2 + 64));
}

```

## disassembly

```asm
0x1400098ef  lea     rcx, [rdx+40h]; this
0x1400098f6  jmp     ??1_variant_t@@QEAA@XZ; _variant_t::~_variant_t(void)
```
