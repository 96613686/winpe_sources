# ATL::CComBSTR::~CComBSTR(void)

- ea: `0x1400039d0`
- end: `0x1400039da`
- name: `??1CComBSTR@ATL@@QEAA@XZ`
- size: `10`
- prototype: `void __fastcall(BSTR *this)`
- caller_count: `7`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x140015e62`
- `0x140015f8d`
- `0x140015f9f`
- `0x140015fc3`
- `0x140015fe7`
- `0x140015ff9`
- `0x14001600b`

## import_xrefs

- `OLEAUT32!__imp_SysFreeString` at `0x1400039d3`

## pseudocode

```c
void __fastcall ATL::CComBSTR::~CComBSTR(BSTR *this)
{
  SysFreeString(*this);
}

```

## disassembly

```asm
0x1400039d0  mov     rcx, [rcx]
0x1400039d3  jmp     cs:__imp_SysFreeString
```
