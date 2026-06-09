# _CMDMPushConfiguration::CreatePushLaunchSchedule_::_1_::dtor$32

- ea: `0x140019a35`
- end: `0x140019a41`
- name: `_CMDMPushConfiguration::CreatePushLaunchSchedule_::_1_::dtor$32`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config`

## callees

- `0x140004c54`

## pseudocode

```c
void __fastcall CMDMPushConfiguration::CreatePushLaunchSchedule_::_1_::dtor_32(__int64 a1, __int64 a2)
{
  _bstr_t::~_bstr_t((_bstr_t *)(a2 + 128));
}

```

## disassembly

```asm
0x140019a35  lea     rcx, [rdx+80h]; this
0x140019a3c  jmp     ??1_bstr_t@@QEAA@XZ; _bstr_t::~_bstr_t(void)
```
