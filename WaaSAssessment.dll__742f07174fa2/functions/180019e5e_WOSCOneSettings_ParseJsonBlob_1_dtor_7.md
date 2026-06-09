# _WOSCOneSettings::ParseJsonBlob_::_1_::dtor$7

- ea: `0x180019e5e`
- end: `0x180019e6a`
- name: `_WOSCOneSettings::ParseJsonBlob_::_1_::dtor$7`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callees

- `0x18000f910`

## pseudocode

```c
void __fastcall WOSCOneSettings::ParseJsonBlob_::_1_::dtor_7(__int64 a1, __int64 a2)
{
  Microsoft::WRL::Wrappers::HStringReference::~HStringReference((Microsoft::WRL::Wrappers::HStringReference *)(a2 + 104));
}

```

## disassembly

```asm
0x180019e5e  lea     rcx, [rdx+68h]; this
0x180019e65  jmp     ??1HStringReference@Wrappers@WRL@Microsoft@@QEAA@XZ; Microsoft::WRL::Wrappers::HStringReference::~HStringReference(void)
```
