# _OnCreateProcessCallback_::_1_::dtor$11

- ea: `0x18000c81c`
- end: `0x18000c828`
- name: `_OnCreateProcessCallback_::_1_::dtor$11`
- size: `12`
- prototype: `_QWORD *__fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, loader_planting, broker_com_uri`

## callees

- `0x18000605c`

## pseudocode

```c
_QWORD *__fastcall OnCreateProcessCallback_::_1_::dtor_11(__int64 a1, __int64 a2)
{
  return Microsoft::WRL::ComPtr<Windows::Data::Json::IJsonObject>::~ComPtr<Windows::Data::Json::IJsonObject>((_QWORD *)(a2 + 80));
}

```

## disassembly

```asm
0x18000c81c  lea     rcx, [rdx+50h]
0x18000c823  jmp     ??1?$ComPtr@UIJsonObject@Json@Data@Windows@@@WRL@Microsoft@@QEAA@XZ; Microsoft::WRL::ComPtr<Windows::Data::Json::IJsonObject>::~ComPtr<Windows::Data::Json::IJsonObject>(void)
```
