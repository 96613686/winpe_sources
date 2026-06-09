# ATL::CComBSTR::~CComBSTR(void)

- ea: `0x140002290`
- end: `0x1400022a3`
- name: `??1CComBSTR@ATL@@QEAA@XZ`
- size: `19`
- prototype: `void __fastcall(BSTR *this)`
- caller_count: `9`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x140013d9d`
- `0x140013daf`
- `0x140013dc1`
- `0x140013f3a`
- `0x140013fa9`
- `0x1400150dd`
- `0x14001515b`
- `0x1400152c7`
- `0x1400152fd`

## import_xrefs

- `OLEAUT32!__imp_SysFreeString` at `0x140002297`
- `OLEAUT32!__imp_SysFreeString` at `0x140002297`

## pseudocode

```c
void __fastcall ATL::CComBSTR::~CComBSTR(BSTR *this)
{
  SysFreeString(*this);
}

```

## disassembly

```asm
0x140002290  sub     rsp, 28h
0x140002294  mov     rcx, [rcx]; bstrString
0x140002297  call    cs:__imp_SysFreeString
0x14000229d  nop
0x14000229e  add     rsp, 28h
0x1400022a2  retn
```
