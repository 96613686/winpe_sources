# _DisableMdmDiagnosticsCleanupTask_::_1_::dtor$4

- ea: `0x1400098dd`
- end: `0x1400098e9`
- name: `_DisableMdmDiagnosticsCleanupTask_::_1_::dtor$4`
- size: `12`
- prototype: `void __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `service_task`

## callees

- `0x140003568`

## pseudocode

```c
void __fastcall DisableMdmDiagnosticsCleanupTask_::_1_::dtor_4(__int64 a1, __int64 a2)
{
  _variant_t::~_variant_t((VARIANTARG *)(a2 + 88));
}

```

## disassembly

```asm
0x1400098dd  lea     rcx, [rdx+58h]; this
0x1400098e4  jmp     ??1_variant_t@@QEAA@XZ; _variant_t::~_variant_t(void)
```
