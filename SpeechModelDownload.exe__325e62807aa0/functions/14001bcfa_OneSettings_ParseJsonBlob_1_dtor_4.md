# _OneSettings::ParseJsonBlob_::_1_::dtor$4

- ea: `0x14001bcfa`
- end: `0x14001bd06`
- name: `_OneSettings::ParseJsonBlob_::_1_::dtor$4`
- size: `12`
- prototype: `_QWORD *__fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callees

- `0x1400049f0`

## pseudocode

```c
_QWORD *__fastcall OneSettings::ParseJsonBlob_::_1_::dtor_4(__int64 a1, __int64 a2)
{
  return Microsoft::WRL::ComPtr<Windows::Data::Json::IJsonObject>::~ComPtr<Windows::Data::Json::IJsonObject>((_QWORD *)(a2 + 40));
}

```

## disassembly

```asm
0x14001bcfa  lea     rcx, [rdx+28h]
0x14001bd01  jmp     ??1?$ComPtr@UIJsonObject@Json@Data@Windows@@@WRL@Microsoft@@QEAA@XZ; Microsoft::WRL::ComPtr<Windows::Data::Json::IJsonObject>::~ComPtr<Windows::Data::Json::IJsonObject>(void)
```
