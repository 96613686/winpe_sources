# _CMDMPushConfiguration::CreatePushLaunchSchedule_::_1_::dtor$30

- ea: `0x1400199ff`
- end: `0x140019a0b`
- name: `_CMDMPushConfiguration::CreatePushLaunchSchedule_::_1_::dtor$30`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callees

- `0x140004cd0`

## pseudocode

```c
HRESULT __fastcall CMDMPushConfiguration::CreatePushLaunchSchedule_::_1_::dtor_30(__int64 a1, __int64 a2)
{
  return ATL::CComVariant::~CComVariant((VARIANTARG *)(a2 + 272));
}

```

## disassembly

```asm
0x1400199ff  lea     rcx, [rdx+110h]; pvarg
0x140019a06  jmp     ??1CComVariant@ATL@@QEAA@XZ; ATL::CComVariant::~CComVariant(void)
```
