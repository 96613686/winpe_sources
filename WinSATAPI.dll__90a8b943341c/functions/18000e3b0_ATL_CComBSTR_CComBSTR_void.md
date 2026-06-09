# ATL::CComBSTR::~CComBSTR(void)

- ea: `0x18000e3b0`
- end: `0x18000e3ba`
- name: `??1CComBSTR@ATL@@QEAA@XZ`
- size: `10`
- prototype: `void __fastcall(ATL::CComBSTR *__hidden this)`
- caller_count: `15`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x180030310`
- `0x180030330`
- `0x180030370`
- `0x180030390`
- `0x1800303b0`
- `0x180030524`
- `0x180030540`
- `0x180030560`
- `0x180030610`
- `0x180030630`
- `0x180030650`
- `0x180030740`
- `0x180030780`
- `0x180031fab`
- `0x180032302`

## import_xrefs

- `OLEAUT32!__imp_SysFreeString` at `0x18000e3b3`

## pseudocode

```c
void __fastcall ATL::CComBSTR::~CComBSTR(BSTR *this)
{
  SysFreeString(*this);
}

```

## disassembly

```asm
0x18000e3b0  mov     rcx, [rcx]
0x18000e3b3  jmp     cs:__imp_SysFreeString
```
