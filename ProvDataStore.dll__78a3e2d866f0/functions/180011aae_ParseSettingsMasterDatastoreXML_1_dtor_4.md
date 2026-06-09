# _ParseSettingsMasterDatastoreXML_::_1_::dtor$4

- ea: `0x180011aae`
- end: `0x180011aba`
- name: `_ParseSettingsMasterDatastoreXML_::_1_::dtor$4`
- size: `12`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config`

## callees

- `0x180008ebc`

## pseudocode

```c
__int64 __fastcall ParseSettingsMasterDatastoreXML_::_1_::dtor_4(__int64 a1, __int64 a2)
{
  return std::shared_ptr<CConfigSet>::~shared_ptr<CConfigSet>(a2 + 40);
}

```

## disassembly

```asm
0x180011aae  lea     rcx, [rdx+28h]
0x180011ab5  jmp     ??1?$shared_ptr@VCConfigSet@@@std@@QEAA@XZ; std::shared_ptr<CConfigSet>::~shared_ptr<CConfigSet>(void)
```
