# _CModelDownloadComponent::ProcessXMLModelFilesChildren_::_1_::dtor$3

- ea: `0x14001bf2f`
- end: `0x14001bf3b`
- name: `_CModelDownloadComponent::ProcessXMLModelFilesChildren_::_1_::dtor$3`
- size: `12`
- prototype: `void __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callees

- `0x14000b254`

## pseudocode

```c
void __fastcall CModelDownloadComponent::ProcessXMLModelFilesChildren_::_1_::dtor_3(__int64 a1, __int64 a2)
{
  ATL::CComBSTR::~CComBSTR((BSTR *)(a2 + 48));
}

```

## disassembly

```asm
0x14001bf2f  lea     rcx, [rdx+30h]; this
0x14001bf36  jmp     ??1CComBSTR@ATL@@QEAA@XZ; ATL::CComBSTR::~CComBSTR(void)
```
