# _CMDMPushConfiguration::CreatePushUpgradeSchedule_::_1_::dtor$24

- ea: `0x140019bdc`
- end: `0x140019be8`
- name: `_CMDMPushConfiguration::CreatePushUpgradeSchedule_::_1_::dtor$24`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callees

- `0x140004cd0`

## pseudocode

```c
HRESULT __fastcall CMDMPushConfiguration::CreatePushUpgradeSchedule_::_1_::dtor_24(__int64 a1, __int64 a2)
{
  return ATL::CComVariant::~CComVariant((VARIANTARG *)(a2 + 368));
}

```

## disassembly

```asm
0x140019bdc  lea     rcx, [rdx+170h]; pvarg
0x140019be3  jmp     ??1CComVariant@ATL@@QEAA@XZ; ATL::CComVariant::~CComVariant(void)
```
