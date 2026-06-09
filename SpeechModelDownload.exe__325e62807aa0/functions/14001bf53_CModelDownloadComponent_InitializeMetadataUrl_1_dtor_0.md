# _CModelDownloadComponent::InitializeMetadataUrl_::_1_::dtor$0

- ea: `0x14001bf53`
- end: `0x14001bf5f`
- name: `_CModelDownloadComponent::InitializeMetadataUrl_::_1_::dtor$0`
- size: `12`
- prototype: `void __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x14000b2ec`

## pseudocode

```c
void __fastcall CModelDownloadComponent::InitializeMetadataUrl_::_1_::dtor_0(__int64 a1, __int64 a2)
{
  CSpDynamicString::~CSpDynamicString((CSpDynamicString *)(a2 + 56));
}

```

## disassembly

```asm
0x14001bf53  lea     rcx, [rdx+38h]; this
0x14001bf5a  jmp     ??1CSpDynamicString@@QEAA@XZ; CSpDynamicString::~CSpDynamicString(void)
```
