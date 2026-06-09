# ATL::CComBSTR::~CComBSTR(void)

- ea: `0x140002434`
- end: `0x14000243e`
- name: `??1CComBSTR@ATL@@QEAA@XZ`
- size: `10`
- prototype: `void __fastcall(BSTR *this)`
- caller_count: `8`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x140014cde`
- `0x140014f9a`
- `0x140014fb2`
- `0x140014fbe`
- `0x14001574a`
- `0x1400158b0`
- `0x1400158c8`
- `0x1400158ec`

## import_xrefs

- `OLEAUT32!__imp_SysFreeString` at `0x140002437`

## pseudocode

```c
// Hidden C++ exception states: #wind=11
void __fastcall ATL::CComBSTR::~CComBSTR(BSTR *this)
{
  SysFreeString(*this);
}

```

## disassembly

```asm
0x140002434  mov     rcx, [rcx]
0x140002437  jmp     cs:__imp_SysFreeString
```
