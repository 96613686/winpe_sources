# _OneSettings::ParseJsonBlob_::_1_::dtor$2

- ea: `0x14001c454`
- end: `0x14001c460`
- name: `_OneSettings::ParseJsonBlob_::_1_::dtor$2`
- size: `12`
- prototype: `_QWORD *__fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callees

- `0x1400049f0`

## pseudocode

```c
_QWORD *__fastcall OneSettings::ParseJsonBlob_::_1_::dtor_2(__int64 a1, __int64 a2)
{
  return Microsoft::WRL::ComPtr<Windows::Data::Json::IJsonObject>::~ComPtr<Windows::Data::Json::IJsonObject>((_QWORD *)(a2 + 48));
}

```

## disassembly

```asm
0x14001c454  lea     rcx, [rdx+30h]
0x14001c45b  jmp     ??1?$ComPtr@UIJsonObject@Json@Data@Windows@@@WRL@Microsoft@@QEAA@XZ; Microsoft::WRL::ComPtr<Windows::Data::Json::IJsonObject>::~ComPtr<Windows::Data::Json::IJsonObject>(void)
```
