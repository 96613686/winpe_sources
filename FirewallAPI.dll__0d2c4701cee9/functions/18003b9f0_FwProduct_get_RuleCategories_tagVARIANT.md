# FwProduct::get_RuleCategories(tagVARIANT *)

- ea: `0x18003b9f0`
- end: `0x18003ba55`
- name: `?get_RuleCategories@FwProduct@@UEAAJPEAUtagVARIANT@@@Z`
- size: `101`
- prototype: `int(FwProduct *__hidden this, struct tagVARIANT *)`
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x18003b9f0`

## import_xrefs

- `OLEAUT32!__imp_VariantCopy` at `0x18003ba0e`
- `OLEAUT32!__imp_VariantCopy` at `0x18003ba0e`
- `fwbase!FwReportReturnError` at `0x18003ba29`
- `fwbase!FwReportReturnError` at `0x18003ba3e`
- `fwbase!FwReportReturnError` at `0x18003ba29`
- `fwbase!FwReportReturnError` at `0x18003ba3e`

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
0x18003b9f0  push    rbx
0x18003b9f2  sub     rsp, 20h
0x18003b9f6  mov     rax, rdx
0x18003b9f9  test    rdx, rdx
0x18003b9fc  jnz     short loc_18003BA07
0x18003b9fe  mov     ebx, 80004003h
0x18003ba03  mov     edx, ebx
0x18003ba05  jmp     short loc_18003BA22
0x18003ba07  lea     rdx, [rcx+40h]; pvargSrc
0x18003ba0b  mov     rcx, rax; pvargDest
0x18003ba0e  call    cs:__imp_VariantCopy
0x18003ba15  nop     dword ptr [rax+rax+00h]
0x18003ba1a  mov     ebx, eax
0x18003ba1c  test    eax, eax
0x18003ba1e  jns     short loc_18003BA4C
0x18003ba20  mov     edx, eax
0x18003ba22  lea     rcx, aFwproductGetRu; "FwProduct::get_RuleCategories"
0x18003ba29  call    cs:__imp_FwReportReturnError
0x18003ba30  nop     dword ptr [rax+rax+00h]
0x18003ba35  mov     edx, ebx
0x18003ba37  lea     rcx, aFwproductGetRu; "FwProduct::get_RuleCategories"
0x18003ba3e  call    cs:__imp_FwReportReturnError
0x18003ba45  nop     dword ptr [rax+rax+00h]
0x18003ba4a  mov     ebx, eax
0x18003ba4c  mov     eax, ebx
0x18003ba4e  add     rsp, 20h
0x18003ba52  pop     rbx
0x18003ba53  retn
```
