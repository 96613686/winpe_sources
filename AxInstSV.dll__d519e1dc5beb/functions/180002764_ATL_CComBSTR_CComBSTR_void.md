# ATL::CComBSTR::~CComBSTR(void)

- ea: `0x180002764`
- end: `0x18000276e`
- name: `??1CComBSTR@ATL@@QEAA@XZ`
- size: `10`
- prototype: `void __fastcall(ATL::CComBSTR *__hidden this)`
- caller_count: `8`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x180014479`
- `0x18001448b`
- `0x1800144c2`
- `0x180014546`
- `0x180014653`
- `0x1800147fe`
- `0x180014af2`
- `0x180014b04`

## import_xrefs

- `OLEAUT32!__imp_SysFreeString` at `0x180002767`

## pseudocode

```c
void __fastcall ATL::CComBSTR::~CComBSTR(BSTR *this)
{
  SysFreeString(*this);
}

```

## disassembly

```asm
0x180002764  mov     rcx, [rcx]
0x180002767  jmp     cs:__imp_SysFreeString
```
