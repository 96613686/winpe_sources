# _DisableMdmDiagnosticsCleanupTask_::_1_::dtor$2

- ea: `0x1400098b9`
- end: `0x1400098c5`
- name: `_DisableMdmDiagnosticsCleanupTask_::_1_::dtor$2`
- size: `12`
- prototype: `void __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `service_task`

## callees

- `0x140003568`

## pseudocode

```c
void __fastcall DisableMdmDiagnosticsCleanupTask_::_1_::dtor_2(__int64 a1, __int64 a2)
{
  _variant_t::~_variant_t((VARIANTARG *)(a2 + 136));
}

```

## disassembly

```asm
0x1400098b9  lea     rcx, [rdx+88h]; this
0x1400098c0  jmp     ??1_variant_t@@QEAA@XZ; _variant_t::~_variant_t(void)
```
