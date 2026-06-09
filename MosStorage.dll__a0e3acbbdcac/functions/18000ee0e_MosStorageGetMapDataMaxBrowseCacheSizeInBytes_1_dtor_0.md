# _MosStorageGetMapDataMaxBrowseCacheSizeInBytes_::_1_::dtor$0

- ea: `0x18000ee0e`
- end: `0x18000ee1a`
- name: `_MosStorageGetMapDataMaxBrowseCacheSizeInBytes_::_1_::dtor$0`
- size: `12`
- prototype: `_QWORD *__fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callees

- `0x180006c14`

## pseudocode

```c
_QWORD *__fastcall MosStorageGetMapDataMaxBrowseCacheSizeInBytes_::_1_::dtor_0(__int64 a1, __int64 a2)
{
  return Microsoft::WRL::ComPtr<ILocaleMapConfiguration>::~ComPtr<ILocaleMapConfiguration>((_QWORD *)(a2 + 56));
}

```

## disassembly

```asm
0x18000ee0e  lea     rcx, [rdx+38h]
0x18000ee15  jmp     ??1?$ComPtr@UILocaleMapConfiguration@@@WRL@Microsoft@@QEAA@XZ; Microsoft::WRL::ComPtr<ILocaleMapConfiguration>::~ComPtr<ILocaleMapConfiguration>(void)
```
