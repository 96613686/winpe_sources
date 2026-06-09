# _CMDMPushConfiguration::CreatePushUpgradeSchedule_::_1_::dtor$25

- ea: `0x140018e33`
- end: `0x140018e3f`
- name: `_CMDMPushConfiguration::CreatePushUpgradeSchedule_::_1_::dtor$25`
- size: `12`
- prototype: `HRESULT __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callees

- `0x140004c34`

## pseudocode

```c
HRESULT __fastcall CMDMPushConfiguration::CreatePushUpgradeSchedule_::_1_::dtor_25(__int64 a1, __int64 a2)
{
  return ATL::CComVariant::~CComVariant((VARIANTARG *)(a2 + 256));
}

```

## disassembly

```asm
0x140018e33  lea     rcx, [rdx+100h]; pvarg
0x140018e3a  jmp     ??1CComVariant@ATL@@QEAA@XZ; ATL::CComVariant::~CComVariant(void)
```
