# _CMDMPushConfiguration::CreatePushLaunchSchedule_::_1_::dtor$32

- ea: `0x140018cd4`
- end: `0x140018ce0`
- name: `_CMDMPushConfiguration::CreatePushLaunchSchedule_::_1_::dtor$32`
- size: `12`
- prototype: `void __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config`

## callees

- `0x140004bc0`

## pseudocode

```c
void __fastcall CMDMPushConfiguration::CreatePushLaunchSchedule_::_1_::dtor_32(__int64 a1, __int64 a2)
{
  _bstr_t::~_bstr_t((_bstr_t *)(a2 + 128));
}

```

## disassembly

```asm
0x140018cd4  lea     rcx, [rdx+80h]; this
0x140018cdb  jmp     ??1_bstr_t@@QEAA@XZ; _bstr_t::~_bstr_t(void)
```
