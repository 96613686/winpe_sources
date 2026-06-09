# _WOSCOneSettings::ParseJsonBlob_::_1_::dtor$2

- ea: `0x180019d86`
- end: `0x180019d92`
- name: `_WOSCOneSettings::ParseJsonBlob_::_1_::dtor$2`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callees

- `0x180006dc8`

## pseudocode

```c
_QWORD *__fastcall WOSCOneSettings::ParseJsonBlob_::_1_::dtor_2(__int64 a1, __int64 a2)
{
  return Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IIterable<Windows::Foundation::Collections::IKeyValuePair<HSTRING__ *,Windows::Data::Json::IJsonValue *> *>>::~ComPtr<Windows::Foundation::Collections::IIterable<Windows::Foundation::Collections::IKeyValuePair<HSTRING__ *,Windows::Data::Json::IJsonValue *> *>>((_QWORD *)(a2 + 48));
}

```

## disassembly

```asm
0x180019d86  lea     rcx, [rdx+30h]
0x180019d8d  jmp     ??1?$ComPtr@U?$IIterable@PEAU?$IKeyValuePair@PEAUHSTRING__@@PEAUIJsonValue@Json@Data@Windows@@@Collections@Foundation@Windows@@@Collections@Foundation@Windows@@@WRL@Microsoft@@QEAA@XZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IIterable<Windows::Foundation::Collections::IKeyValuePair<HSTRING__ *,Windows::Data::Json::IJsonValue *> *>>::~ComPtr<Windows::Foundation::Collections::IIterable<Windows::Foundation::Collections::IKeyValuePair<HSTRING__ *,Windows::Data::Json::IJsonValue *> *>>(void)
```
