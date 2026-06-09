# _CMDMPushConfiguration::CreatePushLaunchSchedule_::_1_::dtor$26

- ea: `0x140019a23`
- end: `0x140019a2f`
- name: `_CMDMPushConfiguration::CreatePushLaunchSchedule_::_1_::dtor$26`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callees

- `0x140004cd0`

## pseudocode

```c
HRESULT __fastcall CMDMPushConfiguration::CreatePushLaunchSchedule_::_1_::dtor_26(__int64 a1, VARIANTARG *a2)
{
  return ATL::CComVariant::~CComVariant(a2 + 8);
}

```

## disassembly

```asm
0x140019a23  lea     rcx, [rdx+0C0h]; pvarg
0x140019a2a  jmp     ??1CComVariant@ATL@@QEAA@XZ; ATL::CComVariant::~CComVariant(void)
```
