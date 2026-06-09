# _CMDMPushConfiguration::CreatePushUpgradeSchedule_::_1_::dtor$25

- ea: `0x140019b94`
- end: `0x140019ba0`
- name: `_CMDMPushConfiguration::CreatePushUpgradeSchedule_::_1_::dtor$25`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callees

- `0x140004cd0`

## pseudocode

```c
HRESULT __fastcall CMDMPushConfiguration::CreatePushUpgradeSchedule_::_1_::dtor_25(__int64 a1, __int64 a2)
{
  return ATL::CComVariant::~CComVariant((VARIANTARG *)(a2 + 256));
}

```

## disassembly

```asm
0x140019b94  lea     rcx, [rdx+100h]; pvarg
0x140019b9b  jmp     ??1CComVariant@ATL@@QEAA@XZ; ATL::CComVariant::~CComVariant(void)
```
