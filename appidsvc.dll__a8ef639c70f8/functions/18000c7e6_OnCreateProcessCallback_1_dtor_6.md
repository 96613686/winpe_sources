# _OnCreateProcessCallback_::_1_::dtor$6

- ea: `0x18000c7e6`
- end: `0x18000c7f2`
- name: `_OnCreateProcessCallback_::_1_::dtor$6`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, loader_planting, broker_com_uri`

## callees

- `0x18000605c`

## pseudocode

```c
_QWORD *__fastcall OnCreateProcessCallback_::_1_::dtor_6(__int64 a1, __int64 a2)
{
  return Microsoft::WRL::ComPtr<Windows::Data::Json::IJsonObject>::~ComPtr<Windows::Data::Json::IJsonObject>((_QWORD *)(a2 + 96));
}

```

## disassembly

```asm
0x18000c7e6  lea     rcx, [rdx+60h]
0x18000c7ed  jmp     ??1?$ComPtr@UIJsonObject@Json@Data@Windows@@@WRL@Microsoft@@QEAA@XZ; Microsoft::WRL::ComPtr<Windows::Data::Json::IJsonObject>::~ComPtr<Windows::Data::Json::IJsonObject>(void)
```
