# ATL::CComBSTR::~CComBSTR(void)

- ea: `0x140007964`
- end: `0x140007977`
- name: `??1CComBSTR@ATL@@QEAA@XZ`
- size: `19`
- prototype: `void __fastcall(BSTR *this)`
- caller_count: `7`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x140015466`
- `0x140015b91`
- `0x140015ba3`
- `0x140015d6f`
- `0x140015de2`
- `0x140015e55`
- `0x140015e67`

## import_xrefs

- `OLEAUT32!__imp_SysFreeString` at `0x14000796b`
- `OLEAUT32!__imp_SysFreeString` at `0x14000796b`

## pseudocode

```c
void __fastcall ATL::CComBSTR::~CComBSTR(BSTR *this)
{
  SysFreeString(*this);
}

```

## disassembly

```asm
0x140007964  sub     rsp, 28h
0x140007968  mov     rcx, [rcx]; bstrString
0x14000796b  call    cs:__imp_SysFreeString
0x140007971  nop
0x140007972  add     rsp, 28h
0x140007976  retn
```
