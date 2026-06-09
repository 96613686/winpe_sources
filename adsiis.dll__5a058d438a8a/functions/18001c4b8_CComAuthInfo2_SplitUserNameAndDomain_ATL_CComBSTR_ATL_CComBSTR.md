# CComAuthInfo2::SplitUserNameAndDomain(ATL::CComBSTR &,ATL::CComBSTR &)

- ea: `0x18001c4b8`
- end: `0x18001c552`
- name: `?SplitUserNameAndDomain@CComAuthInfo2@@SAHAEAVCComBSTR@ATL@@0@Z`
- size: `154`
- prototype: `__int64 __fastcall(struct ATL::CComBSTR *, struct ATL::CComBSTR *)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x18001c0d4`

## callees

- `0x180004284`
- `0x180012040`
- `0x18001c4b8`

## import_xrefs

- `msvcrt!wcschr` at `0x18001c4de`
- `msvcrt!wcschr` at `0x18001c4de`
- `OLEAUT32!__imp_SysAllocString` at `0x18001c520`
- `OLEAUT32!__imp_SysAllocString` at `0x18001c520`
- `OLEAUT32!__imp_SysAllocStringLen` at `0x18001c4f8`
- `OLEAUT32!__imp_SysAllocStringLen` at `0x18001c4f8`
- `OLEAUT32!__imp_SysFreeString` at `0x18001c516`
- `OLEAUT32!__imp_SysFreeString` at `0x18001c53e`
- `OLEAUT32!__imp_SysFreeString` at `0x18001c516`
- `OLEAUT32!__imp_SysFreeString` at `0x18001c53e`

## pseudocode

```c
__int64 __fastcall CComAuthInfo2::SplitUserNameAndDomain(const wchar_t **a1, struct ATL::CComBSTR *a2)
{
  __int64 result; // rax
  __int64 v5; // rsi
  OLECHAR *v6; // rbx
  OLECHAR *v7; // rbx
  OLECHAR *v8; // [rsp+50h] [rbp+8h] BYREF

  ATL::CComBSTR::operator=(a2, L".");
  result = (__int64)wcschr(*a1, 0x5Cu);
  v5 = result;
  if ( result )
  {
    v6 = SysAllocStringLen(*a1, (result - (__int64)*a1) >> 1);
    v8 = v6;
    ATL::CComBSTR::operator=(a2, &v8);
    SysFreeString(v6);
    v7 = SysAllocString((const OLECHAR *)(v5 + 2));
    v8 = v7;
    ATL::CComBSTR::operator=(a1, &v8);
    SysFreeString(v7);
    return 1;
  }
  return result;
}

```

## disassembly

```asm
0x18001c4b8  push    rbx
0x18001c4ba  push    rbp
0x18001c4bb  push    rsi
0x18001c4bc  push    rdi
0x18001c4bd  sub     rsp, 28h
0x18001c4c1  mov     rbp, rdx
0x18001c4c4  mov     rdi, rcx
0x18001c4c7  mov     rcx, rbp
0x18001c4ca  lea     rdx, asc_180037E90; "."
0x18001c4d1  call    ??4CComBSTR@ATL@@QEAAAEAV01@PEBG@Z; ATL::CComBSTR::operator=(ushort const *)
0x18001c4d6  mov     rcx, [rdi]; Str
0x18001c4d9  mov     edx, 5Ch ; '\'; Ch
0x18001c4de  call    cs:__imp_wcschr
0x18001c4e4  mov     rsi, rax
0x18001c4e7  test    rax, rax
0x18001c4ea  jz      short loc_18001C549
0x18001c4ec  mov     rcx, [rdi]; strIn
0x18001c4ef  mov     rdx, rax
0x18001c4f2  sub     rdx, [rdi]
0x18001c4f5  sar     rdx, 1; ui
0x18001c4f8  call    cs:__imp_SysAllocStringLen
0x18001c4fe  lea     rdx, [rsp+48h+arg_0]
0x18001c503  mov     rcx, rbp
0x18001c506  mov     rbx, rax
0x18001c509  mov     [rsp+48h+arg_0], rax
0x18001c50e  call    ??4CComBSTR@ATL@@QEAAAEAV01@AEBV01@@Z; ATL::CComBSTR::operator=(ATL::CComBSTR const &)
0x18001c513  mov     rcx, rbx; bstrString
0x18001c516  call    cs:__imp_SysFreeString
0x18001c51c  lea     rcx, [rsi+2]; psz
0x18001c520  call    cs:__imp_SysAllocString
0x18001c526  lea     rdx, [rsp+48h+arg_0]
0x18001c52b  mov     rcx, rdi
0x18001c52e  mov     rbx, rax
0x18001c531  mov     [rsp+48h+arg_0], rax
0x18001c536  call    ??4CComBSTR@ATL@@QEAAAEAV01@AEBV01@@Z; ATL::CComBSTR::operator=(ATL::CComBSTR const &)
0x18001c53b  mov     rcx, rbx; bstrString
0x18001c53e  call    cs:__imp_SysFreeString
0x18001c544  mov     eax, 1
0x18001c549  add     rsp, 28h
0x18001c54d  pop     rdi
0x18001c54e  pop     rsi
0x18001c54f  pop     rbp
0x18001c550  pop     rbx
0x18001c551  retn
```
