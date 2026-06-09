# _CModelDownloadComponent::ProcessXMLModelFilesChildren_::_1_::dtor$4

- ea: `0x14001bfe3`
- end: `0x14001bfef`
- name: `_CModelDownloadComponent::ProcessXMLModelFilesChildren_::_1_::dtor$4`
- size: `12`
- prototype: `void __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callees

- `0x14000b254`

## pseudocode

```c
void __fastcall CModelDownloadComponent::ProcessXMLModelFilesChildren_::_1_::dtor_4(__int64 a1, __int64 a2)
{
  ATL::CComBSTR::~CComBSTR((BSTR *)(a2 + 152));
}

```

## disassembly

```asm
0x14001bfe3  lea     rcx, [rdx+98h]; this
0x14001bfea  jmp     ??1CComBSTR@ATL@@QEAA@XZ; ATL::CComBSTR::~CComBSTR(void)
```
