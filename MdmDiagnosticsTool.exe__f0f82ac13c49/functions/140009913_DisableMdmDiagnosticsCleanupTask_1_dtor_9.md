# _DisableMdmDiagnosticsCleanupTask_::_1_::dtor$9

- ea: `0x140009913`
- end: `0x14000991f`
- name: `_DisableMdmDiagnosticsCleanupTask_::_1_::dtor$9`
- size: `12`
- prototype: `void __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `service_task`

## callees

- `0x1400034f8`

## pseudocode

```c
void __fastcall DisableMdmDiagnosticsCleanupTask_::_1_::dtor_9(__int64 a1, __int64 a2)
{
  _bstr_t::~_bstr_t((_bstr_t *)(a2 + 56));
}

```

## disassembly

```asm
0x140009913  lea     rcx, [rdx+38h]; this
0x14000991a  jmp     ??1_bstr_t@@QEAA@XZ; _bstr_t::~_bstr_t(void)
```
