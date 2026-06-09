# _CMDMPushConfiguration::CreatePushLaunchSchedule_::_1_::dtor$26

- ea: `0x140018cc2`
- end: `0x140018cce`
- name: `_CMDMPushConfiguration::CreatePushLaunchSchedule_::_1_::dtor$26`
- size: `12`
- prototype: `HRESULT __fastcall(__int64, VARIANTARG *)`
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callees

- `0x140004c34`

## pseudocode

```c
HRESULT __fastcall CMDMPushConfiguration::CreatePushLaunchSchedule_::_1_::dtor_26(__int64 a1, VARIANTARG *a2)
{
  return ATL::CComVariant::~CComVariant(a2 + 8);
}

```

## disassembly

```asm
0x140018cc2  lea     rcx, [rdx+0C0h]; pvarg
0x140018cc9  jmp     ??1CComVariant@ATL@@QEAA@XZ; ATL::CComVariant::~CComVariant(void)
```
