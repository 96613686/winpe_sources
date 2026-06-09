# _ParseSettingsMasterDatastoreXML_::_1_::dtor$1

- ea: `0x180011a6d`
- end: `0x180011a79`
- name: `_ParseSettingsMasterDatastoreXML_::_1_::dtor$1`
- size: `12`
- prototype: `void __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config`

## callees

- `0x18000b1ec`

## pseudocode

```c
void __fastcall ParseSettingsMasterDatastoreXML_::_1_::dtor_1(__int64 a1, __int64 a2)
{
  MasterDatastoreContext::~MasterDatastoreContext((MasterDatastoreContext *)(a2 + 72));
}

```

## disassembly

```asm
0x180011a6d  lea     rcx, [rdx+48h]; this
0x180011a74  jmp     ??1MasterDatastoreContext@@QEAA@XZ; MasterDatastoreContext::~MasterDatastoreContext(void)
```
