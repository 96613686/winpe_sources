# _PowerGrid::ForecastOutput::ConvertToJson_::_1_::dtor$4

- ea: `0x180036105`
- end: `0x180036111`
- name: `_PowerGrid::ForecastOutput::ConvertToJson_::_1_::dtor$4`
- size: `12`
- prototype: `_QWORD *__fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callees

- `0x180028588`

## pseudocode

```c
_QWORD *__fastcall PowerGrid::ForecastOutput::ConvertToJson_::_1_::dtor_4(__int64 a1, __int64 a2)
{
  return Microsoft::WRL::ComPtr<Windows::Data::Json::IJsonObject>::~ComPtr<Windows::Data::Json::IJsonObject>((_QWORD *)(a2 + 48));
}

```

## disassembly

```asm
0x180036105  lea     rcx, [rdx+30h]
0x18003610c  jmp     ??1?$ComPtr@UIJsonObject@Json@Data@Windows@@@WRL@Microsoft@@QEAA@XZ; Microsoft::WRL::ComPtr<Windows::Data::Json::IJsonObject>::~ComPtr<Windows::Data::Json::IJsonObject>(void)
```
