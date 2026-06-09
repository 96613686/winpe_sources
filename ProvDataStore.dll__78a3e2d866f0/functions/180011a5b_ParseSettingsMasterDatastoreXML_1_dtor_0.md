# _ParseSettingsMasterDatastoreXML_::_1_::dtor$0

- ea: `0x180011a5b`
- end: `0x180011a67`
- name: `_ParseSettingsMasterDatastoreXML_::_1_::dtor$0`
- size: `12`
- prototype: `_QWORD *__fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callees

- `0x180006d64`

## pseudocode

```c
_QWORD *__fastcall ParseSettingsMasterDatastoreXML_::_1_::dtor_0(__int64 a1, __int64 a2)
{
  return Microsoft::WRL::ComPtr<IClassFactory>::~ComPtr<IClassFactory>((_QWORD *)(a2 + 184));
}

```

## disassembly

```asm
0x180011a5b  lea     rcx, [rdx+0B8h]
0x180011a62  jmp     ??1?$ComPtr@UIClassFactory@@@WRL@Microsoft@@QEAA@XZ; Microsoft::WRL::ComPtr<IClassFactory>::~ComPtr<IClassFactory>(void)
```
