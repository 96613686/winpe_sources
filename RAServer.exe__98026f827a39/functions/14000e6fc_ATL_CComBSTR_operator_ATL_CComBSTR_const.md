# ATL::CComBSTR::operator==(ATL::CComBSTR const &)

- ea: `0x14000e6fc`
- end: `0x14000e720`
- name: `??8CComBSTR@ATL@@QEBA_NAEBV01@@Z`
- size: `36`
- prototype: `bool __fastcall(BSTR *, BSTR *)`
- caller_count: `3`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x14000efc0`
- `0x140011fc0`
- `0x140013250`

## import_xrefs

- `OLEAUT32!__imp_VarBstrCmp` at `0x14000e70f`
- `OLEAUT32!__imp_VarBstrCmp` at `0x14000e70f`

## pseudocode

```c
bool __fastcall ATL::CComBSTR::operator==(BSTR *a1, BSTR *a2)
{
  return VarBstrCmp(*a1, *a2, 0x400u, 0) == 1;
}

```

## disassembly

```asm
0x14000e6fc  sub     rsp, 28h
0x14000e700  mov     rdx, [rdx]; bstrRight
0x14000e703  xor     r9d, r9d; dwFlags
0x14000e706  mov     rcx, [rcx]; bstrLeft
0x14000e709  mov     r8d, 400h; lcid
0x14000e70f  call    cs:__imp_VarBstrCmp
0x14000e715  cmp     eax, 1
0x14000e718  setz    al
0x14000e71b  add     rsp, 28h
0x14000e71f  retn
```
