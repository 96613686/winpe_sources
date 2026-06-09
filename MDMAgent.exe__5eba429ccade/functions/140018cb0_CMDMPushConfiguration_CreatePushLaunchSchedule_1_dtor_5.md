# _CMDMPushConfiguration::CreatePushLaunchSchedule_::_1_::dtor$5

- ea: `0x140018cb0`
- end: `0x140018cbc`
- name: `_CMDMPushConfiguration::CreatePushLaunchSchedule_::_1_::dtor$5`
- size: `12`
- prototype: `HRESULT __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callees

- `0x140004c34`

## pseudocode

```c
HRESULT __fastcall CMDMPushConfiguration::CreatePushLaunchSchedule_::_1_::dtor_5(__int64 a1, __int64 a2)
{
  return ATL::CComVariant::~CComVariant((VARIANTARG *)(a2 + 416));
}

```

## disassembly

```asm
0x140018cb0  lea     rcx, [rdx+1A0h]; pvarg
0x140018cb7  jmp     ??1CComVariant@ATL@@QEAA@XZ; ATL::CComVariant::~CComVariant(void)
```
