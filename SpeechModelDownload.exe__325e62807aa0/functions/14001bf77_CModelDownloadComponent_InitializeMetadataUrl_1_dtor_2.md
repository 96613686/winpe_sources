# _CModelDownloadComponent::InitializeMetadataUrl_::_1_::dtor$2

- ea: `0x14001bf77`
- end: `0x14001bf83`
- name: `_CModelDownloadComponent::InitializeMetadataUrl_::_1_::dtor$2`
- size: `12`
- prototype: `void __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callees

- `0x140013a98`

## pseudocode

```c
void __fastcall CModelDownloadComponent::InitializeMetadataUrl_::_1_::dtor_2(__int64 a1, __int64 a2)
{
  SPOneSettings::~SPOneSettings((SPOneSettings *)(a2 + 120));
}

```

## disassembly

```asm
0x14001bf77  lea     rcx, [rdx+78h]; this
0x14001bf7e  jmp     ??1SPOneSettings@@QEAA@XZ; SPOneSettings::~SPOneSettings(void)
```
