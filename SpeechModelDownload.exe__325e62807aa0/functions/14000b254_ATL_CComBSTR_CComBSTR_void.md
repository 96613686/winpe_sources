# ATL::CComBSTR::~CComBSTR(void)

- ea: `0x14000b254`
- end: `0x14000b25e`
- name: `??1CComBSTR@ATL@@QEAA@XZ`
- size: `10`
- prototype: `void __fastcall(BSTR *this)`
- caller_count: `4`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x14001bef9`
- `0x14001bf2f`
- `0x14001bfd1`
- `0x14001bfe3`

## import_xrefs

- `OLEAUT32!__imp_SysFreeString` at `0x14000b257`

## pseudocode

```c
void __fastcall ATL::CComBSTR::~CComBSTR(BSTR *this)
{
  SysFreeString(*this);
}

```

## disassembly

```asm
0x14000b254  mov     rcx, [rcx]
0x14000b257  jmp     cs:__imp_SysFreeString
```
