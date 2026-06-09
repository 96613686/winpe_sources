# FwProduct::get_RuleCategories(tagVARIANT *)

- ea: `0x180038f60`
- end: `0x180038fb2`
- name: `?get_RuleCategories@FwProduct@@UEAAJPEAUtagVARIANT@@@Z`
- size: `82`
- prototype: `int(FwProduct *__hidden this, struct tagVARIANT *)`
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x180038f60`

## import_xrefs

- `OLEAUT32!__imp_VariantCopy` at `0x180038f7e`
- `OLEAUT32!__imp_VariantCopy` at `0x180038f7e`
- `fwbase!FwReportReturnError` at `0x180038f93`
- `fwbase!FwReportReturnError` at `0x180038fa2`
- `fwbase!FwReportReturnError` at `0x180038f93`
- `fwbase!FwReportReturnError` at `0x180038fa2`

## pseudocode

```c
__int64 __fastcall FwProduct::get_RuleCategories(FwProduct *this, struct tagVARIANT *a2)
{
  unsigned int v2; // ebx
  __int64 v3; // rdx
  HRESULT v4; // eax

  if ( !a2 )
  {
    v2 = -2147467261;
    v3 = 2147500035LL;
LABEL_5:
    FwReportReturnError("FwProduct::get_RuleCategories", v3);
    return (unsigned int)FwReportReturnError("FwProduct::get_RuleCategories", v2);
  }
  v4 = VariantCopy(a2, (const VARIANTARG *)((char *)this + 64));
  v2 = v4;
  if ( v4 < 0 )
  {
    v3 = (unsigned int)v4;
    goto LABEL_5;
  }
  return v2;
}

```

## disassembly

```asm
0x180038f60  push    rbx
0x180038f62  sub     rsp, 20h
0x180038f66  mov     rax, rdx
0x180038f69  test    rdx, rdx
0x180038f6c  jnz     short loc_180038F77
0x180038f6e  mov     ebx, 80004003h
0x180038f73  mov     edx, ebx
0x180038f75  jmp     short loc_180038F8C
0x180038f77  lea     rdx, [rcx+40h]; pvargSrc
0x180038f7b  mov     rcx, rax; pvargDest
0x180038f7e  call    cs:__imp_VariantCopy
0x180038f84  mov     ebx, eax
0x180038f86  test    eax, eax
0x180038f88  jns     short loc_180038FAA
0x180038f8a  mov     edx, eax
0x180038f8c  lea     rcx, aFwproductGetRu; "FwProduct::get_RuleCategories"
0x180038f93  call    cs:__imp_FwReportReturnError
0x180038f99  mov     edx, ebx
0x180038f9b  lea     rcx, aFwproductGetRu; "FwProduct::get_RuleCategories"
0x180038fa2  call    cs:__imp_FwReportReturnError
0x180038fa8  mov     ebx, eax
0x180038faa  mov     eax, ebx
0x180038fac  add     rsp, 20h
0x180038fb0  pop     rbx
0x180038fb1  retn
```
