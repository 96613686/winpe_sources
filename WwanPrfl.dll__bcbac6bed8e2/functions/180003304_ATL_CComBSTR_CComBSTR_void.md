# ATL::CComBSTR::~CComBSTR(void)

- ea: `0x180003304`
- end: `0x18000330e`
- name: `??1CComBSTR@ATL@@QEAA@XZ`
- size: `10`
- prototype: `void __fastcall(BSTR *this)`
- caller_count: `1`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x180013965`

## import_xrefs

- `OLEAUT32!__imp_SysFreeString` at `0x180003307`

## pseudocode

```c
void __fastcall ATL::CComBSTR::~CComBSTR(BSTR *this)
{
  SysFreeString(*this);
}

```

## disassembly

```asm
0x180003304  mov     rcx, [rcx]
0x180003307  jmp     cs:__imp_SysFreeString
```
