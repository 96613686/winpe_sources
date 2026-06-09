# ATL::CComBSTR::~CComBSTR(void)

- ea: `0x180001640`
- end: `0x18000164a`
- name: `??1CComBSTR@ATL@@QEAA@XZ`
- size: `10`
- prototype: `void __fastcall(ATL::CComBSTR *__hidden this)`
- caller_count: `2`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x180029572`
- `0x18002957e`

## import_xrefs

- `OLEAUT32!__imp_SysFreeString` at `0x180001643`

## pseudocode

```c
void __fastcall ATL::CComBSTR::~CComBSTR(BSTR *this)
{
  SysFreeString(*this);
}

```

## disassembly

```asm
0x180001640  mov     rcx, [rcx]
0x180001643  jmp     cs:__imp_SysFreeString
```
