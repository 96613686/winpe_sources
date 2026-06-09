# _CMDMPushConfiguration::CreatePushLaunchSchedule_::_1_::dtor$31

- ea: `0x1400199ed`
- end: `0x1400199f9`
- name: `_CMDMPushConfiguration::CreatePushLaunchSchedule_::_1_::dtor$31`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callees

- `0x140004cd0`

## pseudocode

```c
HRESULT __fastcall CMDMPushConfiguration::CreatePushLaunchSchedule_::_1_::dtor_31(__int64 a1, __int64 a2)
{
  return ATL::CComVariant::~CComVariant((VARIANTARG *)(a2 + 296));
}

```

## disassembly

```asm
0x1400199ed  lea     rcx, [rdx+128h]; pvarg
0x1400199f4  jmp     ??1CComVariant@ATL@@QEAA@XZ; ATL::CComVariant::~CComVariant(void)
```
