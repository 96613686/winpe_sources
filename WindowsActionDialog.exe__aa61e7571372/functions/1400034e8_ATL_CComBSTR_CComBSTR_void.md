# ATL::CComBSTR::~CComBSTR(void)

- ea: `0x1400034e8`
- end: `0x1400034f2`
- name: `??1CComBSTR@ATL@@QEAA@XZ`
- size: `10`
- prototype: `void __fastcall(ATL::CComBSTR *__hidden this)`
- caller_count: `2`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x140009415`
- `0x140009427`

## import_xrefs

- `OLEAUT32!__imp_SysFreeString` at `0x1400034eb`

## pseudocode

```c
void __fastcall ATL::CComBSTR::~CComBSTR(BSTR *this)
{
  SysFreeString(*this);
}

```

## disassembly

```asm
0x1400034e8  mov     rcx, [rcx]
0x1400034eb  jmp     cs:__imp_SysFreeString
```
