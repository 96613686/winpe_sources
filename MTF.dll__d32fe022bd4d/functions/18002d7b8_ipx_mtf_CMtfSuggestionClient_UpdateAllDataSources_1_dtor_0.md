# _ipx::mtf::CMtfSuggestionClient::UpdateAllDataSources_::_1_::dtor$0

- ea: `0x18002d7b8`
- end: `0x18002d7c4`
- name: `_ipx::mtf::CMtfSuggestionClient::UpdateAllDataSources_::_1_::dtor$0`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `installer_update`

## callees

- `0x1800147f0`

## pseudocode

```c
void __fastcall ipx::mtf::CMtfSuggestionClient::UpdateAllDataSources_::_1_::dtor_0(__int64 a1, __int64 a2)
{
  MtfPlatformTelemetry::UpdateAllDataSource::~UpdateAllDataSource((MtfPlatformTelemetry::UpdateAllDataSource *)(a2 + 96));
}

```

## disassembly

```asm
0x18002d7b8  lea     rcx, [rdx+60h]; this
0x18002d7bf  jmp     ??1UpdateAllDataSource@MtfPlatformTelemetry@@QEAA@XZ; MtfPlatformTelemetry::UpdateAllDataSource::~UpdateAllDataSource(void)
```
