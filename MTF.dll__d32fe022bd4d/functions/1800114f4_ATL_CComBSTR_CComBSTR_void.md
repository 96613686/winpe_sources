# ATL::CComBSTR::~CComBSTR(void)

- ea: `0x1800114f4`
- end: `0x1800114fe`
- name: `??1CComBSTR@ATL@@QEAA@XZ`
- size: `10`
- prototype: `void __fastcall(ATL::CComBSTR *__hidden this)`
- caller_count: `1`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x18002d87e`

## import_xrefs

- `OLEAUT32!__imp_SysFreeString` at `0x1800114f7`

## pseudocode

```c
void __fastcall ATL::CComBSTR::~CComBSTR(BSTR *this)
{
  SysFreeString(*this);
}

```

## disassembly

```asm
0x1800114f4  mov     rcx, [rcx]
0x1800114f7  jmp     cs:__imp_SysFreeString
```
