# _CMDMPushConfiguration::CreatePushUpgradeSchedule_::_1_::dtor$26

- ea: `0x140019b82`
- end: `0x140019b8e`
- name: `_CMDMPushConfiguration::CreatePushUpgradeSchedule_::_1_::dtor$26`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callees

- `0x140004cd0`

## pseudocode

```c
HRESULT __fastcall CMDMPushConfiguration::CreatePushUpgradeSchedule_::_1_::dtor_26(__int64 a1, __int64 a2)
{
  return ATL::CComVariant::~CComVariant((VARIANTARG *)(a2 + 280));
}

```

## disassembly

```asm
0x140019b82  lea     rcx, [rdx+118h]; pvarg
0x140019b89  jmp     ??1CComVariant@ATL@@QEAA@XZ; ATL::CComVariant::~CComVariant(void)
```
