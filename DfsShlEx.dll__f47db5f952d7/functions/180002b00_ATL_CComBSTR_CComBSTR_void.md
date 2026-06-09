# ATL::CComBSTR::~CComBSTR(void)

- ea: `0x180002b00`
- end: `0x180002b0a`
- name: `??1CComBSTR@ATL@@QEAA@XZ`
- size: `10`
- prototype: `void __fastcall(ATL::CComBSTR *__hidden this)`
- caller_count: `4`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x18000b00c`
- `0x18000b01e`
- `0x18000b0f8`
- `0x18000b10a`

## import_xrefs

- `OLEAUT32!__imp_SysFreeString` at `0x180002b03`

## pseudocode

```c
void __fastcall ATL::CComBSTR::~CComBSTR(BSTR *this)
{
  SysFreeString(*this);
}

```

## disassembly

```asm
0x180002b00  mov     rcx, [rcx]
0x180002b03  jmp     cs:__imp_SysFreeString
```
