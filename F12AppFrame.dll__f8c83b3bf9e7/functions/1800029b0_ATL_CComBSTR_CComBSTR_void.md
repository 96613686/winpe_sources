# ATL::CComBSTR::~CComBSTR(void)

- ea: `0x1800029b0`
- end: `0x1800029ba`
- name: `??1CComBSTR@ATL@@QEAA@XZ`
- size: `10`
- prototype: `void __fastcall(BSTR *this)`
- caller_count: `17`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x180033009`
- `0x18003301b`
- `0x18003302d`
- `0x18003303f`
- `0x180033051`
- `0x1800330cf`
- `0x180033129`
- `0x1800331dd`
- `0x180033322`
- `0x18003336a`
- `0x180033ac3`
- `0x180033bd0`
- `0x180033cef`
- `0x180033d13`
- `0x180033f1c`
- `0x18003404d`
- `0x18003415b`

## import_xrefs

- `OLEAUT32!__imp_SysFreeString` at `0x1800029b3`

## pseudocode

```c
void __fastcall ATL::CComBSTR::~CComBSTR(BSTR *this)
{
  SysFreeString(*this);
}

```

## disassembly

```asm
0x1800029b0  mov     rcx, [rcx]
0x1800029b3  jmp     cs:__imp_SysFreeString
```
