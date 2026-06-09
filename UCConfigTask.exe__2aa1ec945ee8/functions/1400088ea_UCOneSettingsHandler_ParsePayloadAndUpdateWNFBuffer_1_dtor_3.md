# _UCOneSettingsHandler::ParsePayloadAndUpdateWNFBuffer_::_1_::dtor$3

- ea: `0x1400088ea`
- end: `0x1400088f6`
- name: `_UCOneSettingsHandler::ParsePayloadAndUpdateWNFBuffer_::_1_::dtor$3`
- size: `12`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, loader_planting, installer_update, broker_com_uri`

## callees

- `0x140007e24`

## pseudocode

```c
__int64 __fastcall UCOneSettingsHandler::ParsePayloadAndUpdateWNFBuffer_::_1_::dtor_3(__int64 a1, __int64 a2)
{
  return Microsoft::WRL::ComPtr<Windows::Data::Json::IJsonObject>::~ComPtr<Windows::Data::Json::IJsonObject>(a2 + 48);
}

```

## disassembly

```asm
0x1400088ea  lea     rcx, [rdx+30h]
0x1400088f1  jmp     ??1?$ComPtr@UIJsonObject@Json@Data@Windows@@@WRL@Microsoft@@QEAA@XZ; Microsoft::WRL::ComPtr<Windows::Data::Json::IJsonObject>::~ComPtr<Windows::Data::Json::IJsonObject>(void)
```
