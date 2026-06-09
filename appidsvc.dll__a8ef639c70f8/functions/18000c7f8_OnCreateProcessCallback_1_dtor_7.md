# _OnCreateProcessCallback_::_1_::dtor$7

- ea: `0x18000c7f8`
- end: `0x18000c804`
- name: `_OnCreateProcessCallback_::_1_::dtor$7`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, loader_planting, broker_com_uri`

## callees

- `0x18000605c`

## pseudocode

```c
_QWORD *__fastcall OnCreateProcessCallback_::_1_::dtor_7(__int64 a1, __int64 a2)
{
  return Microsoft::WRL::ComPtr<Windows::Data::Json::IJsonObject>::~ComPtr<Windows::Data::Json::IJsonObject>((_QWORD *)(a2 + 104));
}

```

## disassembly

```asm
0x18000c7f8  lea     rcx, [rdx+68h]
0x18000c7ff  jmp     ??1?$ComPtr@UIJsonObject@Json@Data@Windows@@@WRL@Microsoft@@QEAA@XZ; Microsoft::WRL::ComPtr<Windows::Data::Json::IJsonObject>::~ComPtr<Windows::Data::Json::IJsonObject>(void)
```
