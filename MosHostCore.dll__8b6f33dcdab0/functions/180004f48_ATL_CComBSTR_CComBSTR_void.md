# ATL::CComBSTR::~CComBSTR(void)

- ea: `0x180004f48`
- end: `0x180004f52`
- name: `??1CComBSTR@ATL@@QEAA@XZ`
- size: `10`
- prototype: `void __fastcall(BSTR *this)`
- caller_count: `10`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x180023d5f`
- `0x180023e49`
- `0x180023e5b`
- `0x180023e6d`
- `0x180023e7f`
- `0x180023e91`
- `0x180023ea3`
- `0x180023eb5`
- `0x180023ec7`
- `0x180023eeb`

## import_xrefs

- `OLEAUT32!__imp_SysFreeString` at `0x180004f4b`

## pseudocode

```c
void __fastcall ATL::CComBSTR::~CComBSTR(BSTR *this)
{
  SysFreeString(*this);
}

```

## disassembly

```asm
0x180004f48  mov     rcx, [rcx]
0x180004f4b  jmp     cs:__imp_SysFreeString
```
