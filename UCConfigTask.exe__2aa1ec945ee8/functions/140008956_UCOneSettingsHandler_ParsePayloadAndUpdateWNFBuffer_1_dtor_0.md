# _UCOneSettingsHandler::ParsePayloadAndUpdateWNFBuffer_::_1_::dtor$0

- ea: `0x140008956`
- end: `0x140008962`
- name: `_UCOneSettingsHandler::ParsePayloadAndUpdateWNFBuffer_::_1_::dtor$0`
- size: `12`
- prototype: `_QWORD *__fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, loader_planting, installer_update, broker_com_uri`

## callees

- `0x140007e30`

## pseudocode

```c
_QWORD *__fastcall UCOneSettingsHandler::ParsePayloadAndUpdateWNFBuffer_::_1_::dtor_0(__int64 a1, __int64 a2)
{
  return Microsoft::WRL::ComPtr<Windows::Data::Json::IJsonArray>::~ComPtr<Windows::Data::Json::IJsonArray>(*(_QWORD **)(a2 + 80));
}

```

## disassembly

```asm
0x140008956  mov     rcx, [rdx+50h]
0x14000895d  jmp     ??1?$ComPtr@UIJsonArray@Json@Data@Windows@@@WRL@Microsoft@@QEAA@XZ; Microsoft::WRL::ComPtr<Windows::Data::Json::IJsonArray>::~ComPtr<Windows::Data::Json::IJsonArray>(void)
```
