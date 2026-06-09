# _ipx::mtf::CMtfSuggestionClient::UpdateDataSource_::_1_::dtor$0

- ea: `0x18002d809`
- end: `0x18002d815`
- name: `_ipx::mtf::CMtfSuggestionClient::UpdateDataSource_::_1_::dtor$0`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `installer_update`

## callees

- `0x18001481c`

## pseudocode

```c
void __fastcall ipx::mtf::CMtfSuggestionClient::UpdateDataSource_::_1_::dtor_0(__int64 a1, __int64 a2)
{
  MtfPlatformTelemetry::UpdateDataSource::~UpdateDataSource((MtfPlatformTelemetry::UpdateDataSource *)(a2 + 112));
}

```

## disassembly

```asm
0x18002d809  lea     rcx, [rdx+70h]; this
0x18002d810  jmp     ??1UpdateDataSource@MtfPlatformTelemetry@@QEAA@XZ; MtfPlatformTelemetry::UpdateDataSource::~UpdateDataSource(void)
```
