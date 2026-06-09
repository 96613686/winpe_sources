# ATL::CComBSTR::~CComBSTR(void)

- ea: `0x180002bf4`
- end: `0x180002bfe`
- name: `??1CComBSTR@ATL@@QEAA@XZ`
- size: `10`
- prototype: `void __fastcall(ATL::CComBSTR *__hidden this)`
- caller_count: `3`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x18000e66e`
- `0x18000e686`
- `0x18000e6fe`

## import_xrefs

- `OLEAUT32!__imp_SysFreeString` at `0x180002bf7`

## pseudocode

```c
void __fastcall ATL::CComBSTR::~CComBSTR(BSTR *this)
{
  SysFreeString(*this);
}

```

## disassembly

```asm
0x180002bf4  mov     rcx, [rcx]
0x180002bf7  jmp     cs:__imp_SysFreeString
```
