# ATL::CComBSTR::~CComBSTR(void)

- ea: `0x180002a1c`
- end: `0x180002a26`
- name: `??1CComBSTR@ATL@@QEAA@XZ`
- size: `10`
- prototype: `void __fastcall(ATL::CComBSTR *__hidden this)`
- caller_count: `2`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x180028cdc`
- `0x180028cee`

## import_xrefs

- `OLEAUT32!__imp_SysFreeString` at `0x180002a1f`

## pseudocode

```c
void __fastcall ATL::CComBSTR::~CComBSTR(BSTR *this)
{
  SysFreeString(*this);
}

```

## disassembly

```asm
0x180002a1c  mov     rcx, [rcx]
0x180002a1f  jmp     cs:__imp_SysFreeString
```
