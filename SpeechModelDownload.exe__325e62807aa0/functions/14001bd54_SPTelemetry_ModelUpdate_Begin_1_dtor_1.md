# _SPTelemetry::ModelUpdate::Begin_::_1_::dtor$1

- ea: `0x14001bd54`
- end: `0x14001bd60`
- name: `_SPTelemetry::ModelUpdate::Begin_::_1_::dtor$1`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, installer_update, broker_com_uri`

## callees

- `0x1400049f0`

## pseudocode

```c
_QWORD *__fastcall SPTelemetry::ModelUpdate::Begin_::_1_::dtor_1(__int64 a1, __int64 a2)
{
  return Microsoft::WRL::ComPtr<Windows::Data::Json::IJsonObject>::~ComPtr<Windows::Data::Json::IJsonObject>((_QWORD *)(a2 + 112));
}

```

## disassembly

```asm
0x14001bd54  lea     rcx, [rdx+70h]
0x14001bd5b  jmp     ??1?$ComPtr@UIJsonObject@Json@Data@Windows@@@WRL@Microsoft@@QEAA@XZ; Microsoft::WRL::ComPtr<Windows::Data::Json::IJsonObject>::~ComPtr<Windows::Data::Json::IJsonObject>(void)
```
