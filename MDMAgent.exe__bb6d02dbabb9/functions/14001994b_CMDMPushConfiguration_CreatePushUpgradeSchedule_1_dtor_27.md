# _CMDMPushConfiguration::CreatePushUpgradeSchedule_::_1_::dtor$27

- ea: `0x14001994b`
- end: `0x140019957`
- name: `_CMDMPushConfiguration::CreatePushUpgradeSchedule_::_1_::dtor$27`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config`

## callees

- `0x140004c54`

## pseudocode

```c
void __fastcall CMDMPushConfiguration::CreatePushUpgradeSchedule_::_1_::dtor_27(__int64 a1, __int64 a2)
{
  _bstr_t::~_bstr_t((_bstr_t *)(a2 + 144));
}

```

## disassembly

```asm
0x14001994b  lea     rcx, [rdx+90h]; this
0x140019952  jmp     ??1_bstr_t@@QEAA@XZ; _bstr_t::~_bstr_t(void)
```
