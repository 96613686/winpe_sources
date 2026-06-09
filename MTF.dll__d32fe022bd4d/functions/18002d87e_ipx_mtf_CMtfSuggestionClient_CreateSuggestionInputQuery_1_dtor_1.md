# _ipx::mtf::CMtfSuggestionClient::_CreateSuggestionInputQuery_::_1_::dtor$1

- ea: `0x18002d87e`
- end: `0x18002d88a`
- name: `_ipx::mtf::CMtfSuggestionClient::_CreateSuggestionInputQuery_::_1_::dtor$1`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x1800114f4`

## pseudocode

```c
void __fastcall ipx::mtf::CMtfSuggestionClient::_CreateSuggestionInputQuery_::_1_::dtor_1(__int64 a1, __int64 a2)
{
  ATL::CComBSTR::~CComBSTR((BSTR *)(a2 + 48));
}

```

## disassembly

```asm
0x18002d87e  lea     rcx, [rdx+30h]; this
0x18002d885  jmp     ??1CComBSTR@ATL@@QEAA@XZ; ATL::CComBSTR::~CComBSTR(void)
```
