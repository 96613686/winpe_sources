# _CMDMPushConfiguration::CreatePushLaunchSchedule_::_1_::dtor$30

- ea: `0x140018c9e`
- end: `0x140018caa`
- name: `_CMDMPushConfiguration::CreatePushLaunchSchedule_::_1_::dtor$30`
- size: `12`
- prototype: `HRESULT __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callees

- `0x140004c34`

## pseudocode

```c
HRESULT __fastcall CMDMPushConfiguration::CreatePushLaunchSchedule_::_1_::dtor_30(__int64 a1, __int64 a2)
{
  return ATL::CComVariant::~CComVariant((VARIANTARG *)(a2 + 272));
}

```

## disassembly

```asm
0x140018c9e  lea     rcx, [rdx+110h]; pvarg
0x140018ca5  jmp     ??1CComVariant@ATL@@QEAA@XZ; ATL::CComVariant::~CComVariant(void)
```
