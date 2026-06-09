# _CMDMPushConfiguration::CreatePushLaunchSchedule_::_1_::dtor$29

- ea: `0x140019b1f`
- end: `0x140019b2b`
- name: `_CMDMPushConfiguration::CreatePushLaunchSchedule_::_1_::dtor$29`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callees

- `0x140004cd0`

## pseudocode

```c
HRESULT __fastcall CMDMPushConfiguration::CreatePushLaunchSchedule_::_1_::dtor_29(__int64 a1, VARIANTARG *a2)
{
  return ATL::CComVariant::~CComVariant(a2 + 16);
}

```

## disassembly

```asm
0x140019b1f  lea     rcx, [rdx+180h]; pvarg
0x140019b26  jmp     ??1CComVariant@ATL@@QEAA@XZ; ATL::CComVariant::~CComVariant(void)
```
