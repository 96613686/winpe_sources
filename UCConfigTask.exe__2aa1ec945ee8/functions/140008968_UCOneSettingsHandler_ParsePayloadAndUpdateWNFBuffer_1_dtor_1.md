# _UCOneSettingsHandler::ParsePayloadAndUpdateWNFBuffer_::_1_::dtor$1

- ea: `0x140008968`
- end: `0x140008974`
- name: `_UCOneSettingsHandler::ParsePayloadAndUpdateWNFBuffer_::_1_::dtor$1`
- size: `12`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, loader_planting, installer_update, broker_com_uri`

## callees

- `0x140007e24`

## pseudocode

```c
__int64 __fastcall UCOneSettingsHandler::ParsePayloadAndUpdateWNFBuffer_::_1_::dtor_1(__int64 a1, __int64 a2)
{
  return Microsoft::WRL::ComPtr<Windows::Data::Json::IJsonObject>::~ComPtr<Windows::Data::Json::IJsonObject>(a2 + 56);
}

```

## disassembly

```asm
0x140008968  lea     rcx, [rdx+38h]
0x14000896f  jmp     ??1?$ComPtr@UIJsonObject@Json@Data@Windows@@@WRL@Microsoft@@QEAA@XZ; Microsoft::WRL::ComPtr<Windows::Data::Json::IJsonObject>::~ComPtr<Windows::Data::Json::IJsonObject>(void)
```
