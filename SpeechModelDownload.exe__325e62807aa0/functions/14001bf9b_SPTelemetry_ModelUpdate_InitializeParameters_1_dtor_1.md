# _SPTelemetry::ModelUpdate::InitializeParameters_::_1_::dtor$1

- ea: `0x14001bf9b`
- end: `0x14001bfa7`
- name: `_SPTelemetry::ModelUpdate::InitializeParameters_::_1_::dtor$1`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, installer_update, broker_com_uri`

## callees

- `0x1400049f0`

## pseudocode

```c
_QWORD *__fastcall SPTelemetry::ModelUpdate::InitializeParameters_::_1_::dtor_1(__int64 a1, __int64 a2)
{
  return Microsoft::WRL::ComPtr<Windows::Data::Json::IJsonObject>::~ComPtr<Windows::Data::Json::IJsonObject>((_QWORD *)(a2 + 200));
}

```

## disassembly

```asm
0x14001bf9b  lea     rcx, [rdx+0C8h]
0x14001bfa2  jmp     ??1?$ComPtr@UIJsonObject@Json@Data@Windows@@@WRL@Microsoft@@QEAA@XZ; Microsoft::WRL::ComPtr<Windows::Data::Json::IJsonObject>::~ComPtr<Windows::Data::Json::IJsonObject>(void)
```
