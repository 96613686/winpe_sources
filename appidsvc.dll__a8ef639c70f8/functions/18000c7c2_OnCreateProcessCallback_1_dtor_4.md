# _OnCreateProcessCallback_::_1_::dtor$4

- ea: `0x18000c7c2`
- end: `0x18000c7ce`
- name: `_OnCreateProcessCallback_::_1_::dtor$4`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, loader_planting, broker_com_uri`

## callees

- `0x18000605c`

## pseudocode

```c
_QWORD *__fastcall OnCreateProcessCallback_::_1_::dtor_4(__int64 a1, __int64 a2)
{
  return Microsoft::WRL::ComPtr<Windows::Data::Json::IJsonObject>::~ComPtr<Windows::Data::Json::IJsonObject>((_QWORD *)(a2 + 88));
}

```

## disassembly

```asm
0x18000c7c2  lea     rcx, [rdx+58h]
0x18000c7c9  jmp     ??1?$ComPtr@UIJsonObject@Json@Data@Windows@@@WRL@Microsoft@@QEAA@XZ; Microsoft::WRL::ComPtr<Windows::Data::Json::IJsonObject>::~ComPtr<Windows::Data::Json::IJsonObject>(void)
```
