# _CMDMPushConfiguration::CreatePushLaunchSchedule_::_1_::dtor$31

- ea: `0x140018c8c`
- end: `0x140018c98`
- name: `_CMDMPushConfiguration::CreatePushLaunchSchedule_::_1_::dtor$31`
- size: `12`
- prototype: `HRESULT __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callees

- `0x140004c34`

## pseudocode

```c
HRESULT __fastcall CMDMPushConfiguration::CreatePushLaunchSchedule_::_1_::dtor_31(__int64 a1, __int64 a2)
{
  return ATL::CComVariant::~CComVariant((VARIANTARG *)(a2 + 296));
}

```

## disassembly

```asm
0x140018c8c  lea     rcx, [rdx+128h]; pvarg
0x140018c93  jmp     ??1CComVariant@ATL@@QEAA@XZ; ATL::CComVariant::~CComVariant(void)
```
