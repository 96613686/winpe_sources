# ATL::CComBSTR::~CComBSTR(void)

- ea: `0x1800021d0`
- end: `0x1800021da`
- name: `??1CComBSTR@ATL@@QEAA@XZ`
- size: `10`
- prototype: `void __fastcall(ATL::CComBSTR *__hidden this)`
- caller_count: `2`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x18000bc65`
- `0x18000becc`

## import_xrefs

- `OLEAUT32!__imp_SysFreeString` at `0x1800021d3`

## pseudocode

```c
void __fastcall ATL::CComBSTR::~CComBSTR(BSTR *this)
{
  SysFreeString(*this);
}

```

## disassembly

```asm
0x1800021d0  mov     rcx, [rcx]
0x1800021d3  jmp     cs:__imp_SysFreeString
```
