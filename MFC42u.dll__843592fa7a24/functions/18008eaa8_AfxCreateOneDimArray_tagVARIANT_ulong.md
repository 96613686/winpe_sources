# _AfxCreateOneDimArray(tagVARIANT &,ulong)

- ea: `0x18008eaa8`
- end: `0x18008eb75`
- name: `?_AfxCreateOneDimArray@@YAXAEAUtagVARIANT@@K@Z`
- size: `205`
- prototype: `void __fastcall(VARIANTARG *pvarg, unsigned int)`
- caller_count: `2`
- callee_count: `3`
- tags: ``

## callers

- `0x18008bdb0`
- `0x18008be10`

## callees

- `0x180024fc0`
- `0x18002d800`
- `0x18008eaa8`

## import_xrefs

- `OLEAUT32!__imp_VariantClear` at `0x18008eb45`
- `OLEAUT32!__imp_VariantClear` at `0x18008eb45`
- `OLEAUT32!__imp_SafeArrayCreate` at `0x18008eb61`
- `OLEAUT32!__imp_SafeArrayCreate` at `0x18008eb61`
- `OLEAUT32!__imp_SafeArrayGetDim` at `0x18008eace`
- `OLEAUT32!__imp_SafeArrayGetDim` at `0x18008eace`
- `OLEAUT32!__imp_SafeArrayGetUBound` at `0x18008eb01`
- `OLEAUT32!__imp_SafeArrayGetUBound` at `0x18008eb01`
- `OLEAUT32!__imp_SafeArrayGetLBound` at `0x18008eaea`
- `OLEAUT32!__imp_SafeArrayGetLBound` at `0x18008eaea`
- `OLEAUT32!__imp_SafeArrayRedim` at `0x18008eb2a`
- `OLEAUT32!__imp_SafeArrayRedim` at `0x18008eb2a`

## pseudocode

```c
void __fastcall _AfxCreateOneDimArray(VARIANTARG *pvarg, ULONG a2)
{
  union tagVARIANT::$::$65D68C826D16CA47CF95571D7BFCD657::$E09503A454170B491AC1C4312CE36FE6 *p_llVal; // rbx
  SAFEARRAY *llVal; // rcx
  ULONG v6; // edi
  HRESULT LBound; // eax
  HRESULT UBound; // eax
  SAFEARRAY *v9; // rcx
  HRESULT v10; // eax
  SAFEARRAY *v11; // rax
  SAFEARRAYBOUND plUbound; // [rsp+50h] [rbp+30h] BYREF
  LONG plLbound; // [rsp+60h] [rbp+40h] BYREF
  SAFEARRAYBOUND psaboundNew; // [rsp+68h] [rbp+48h] BYREF

  p_llVal = (union tagVARIANT::$::$65D68C826D16CA47CF95571D7BFCD657::$E09503A454170B491AC1C4312CE36FE6 *)&pvarg->llVal;
  if ( pvarg->vt == 8209 && SafeArrayGetDim(p_llVal->parray) == 1 )
  {
    llVal = (SAFEARRAY *)p_llVal->llVal;
    v6 = 0;
    plLbound = 0;
    plUbound.cElements = 0;
    LBound = SafeArrayGetLBound(llVal, 1u, &plLbound);
    AfxCheckError(LBound);
    UBound = SafeArrayGetUBound(p_llVal->parray, 1u, (LONG *)&plUbound);
    AfxCheckError(UBound);
    if ( (signed int)(plUbound.cElements - plLbound) >= 0 )
      v6 = plUbound.cElements - plLbound;
    if ( v6 != a2 )
    {
      psaboundNew.lLbound = plLbound;
      v9 = (SAFEARRAY *)p_llVal->llVal;
      psaboundNew.cElements = a2;
      v10 = SafeArrayRedim(v9, &psaboundNew);
      AfxCheckError(v10);
    }
  }
  else
  {
    VariantClear(pvarg);
    pvarg->vt = 8209;
    plUbound.cElements = a2;
    plUbound.lLbound = 0;
    v11 = SafeArrayCreate(0x11u, 1u, &plUbound);
    p_llVal->llVal = (LONGLONG)v11;
    if ( !v11 )
      AfxThrowMemoryException();
  }
}

```

## disassembly

```asm
0x18008eaa8  push    rbp
0x18008eaaa  push    rbx
0x18008eaab  push    rsi
0x18008eaac  push    rdi
0x18008eaad  push    r15
0x18008eaaf  mov     rbp, rsp
0x18008eab2  sub     rsp, 20h
0x18008eab6  mov     r15d, 2011h
0x18008eabc  lea     rbx, [rcx+8]
0x18008eac0  mov     esi, edx
0x18008eac2  mov     rdi, rcx
0x18008eac5  cmp     [rcx], r15w
0x18008eac9  jnz     short loc_18008EB42
0x18008eacb  mov     rcx, [rbx]; psa
0x18008eace  call    cs:__imp_SafeArrayGetDim
0x18008ead4  cmp     eax, 1
0x18008ead7  jnz     short loc_18008EB42
0x18008ead9  mov     rcx, [rbx]; psa
0x18008eadc  lea     r8, [rbp+plLbound]; plLbound
0x18008eae0  xor     edi, edi
0x18008eae2  mov     edx, eax; nDim
0x18008eae4  mov     [rbp+plLbound], edi
0x18008eae7  mov     [rbp+plUbound], edi
0x18008eaea  call    cs:__imp_SafeArrayGetLBound
0x18008eaf0  mov     ecx, eax; int
0x18008eaf2  call    ?AfxCheckError@@YAXJ@Z; AfxCheckError(long)
0x18008eaf7  mov     rcx, [rbx]; psa
0x18008eafa  lea     r8, [rbp+plUbound]; plUbound
0x18008eafe  lea     edx, [rdi+1]; nDim
0x18008eb01  call    cs:__imp_SafeArrayGetUBound
0x18008eb07  mov     ecx, eax; int
0x18008eb09  call    ?AfxCheckError@@YAXJ@Z; AfxCheckError(long)
0x18008eb0e  mov     eax, [rbp+plUbound]
0x18008eb11  mov     ecx, [rbp+plLbound]
0x18008eb14  sub     eax, ecx
0x18008eb16  cmovns  edi, eax
0x18008eb19  cmp     edi, esi
0x18008eb1b  jz      short loc_18008EB37
0x18008eb1d  mov     [rbp+psaboundNew.lLbound], ecx
0x18008eb20  lea     rdx, [rbp+psaboundNew]; psaboundNew
0x18008eb24  mov     rcx, [rbx]; psa
0x18008eb27  mov     [rbp+psaboundNew.cElements], esi
0x18008eb2a  call    cs:__imp_SafeArrayRedim
0x18008eb30  mov     ecx, eax; int
0x18008eb32  call    ?AfxCheckError@@YAXJ@Z; AfxCheckError(long)
0x18008eb37  add     rsp, 20h
0x18008eb3b  pop     r15
0x18008eb3d  pop     rdi
0x18008eb3e  pop     rsi
0x18008eb3f  pop     rbx
0x18008eb40  pop     rbp
0x18008eb41  retn
0x18008eb42  mov     rcx, rdi; pvarg
0x18008eb45  call    cs:__imp_VariantClear
0x18008eb4b  mov     [rdi], r15w
0x18008eb4f  lea     r8, [rbp+plUbound]; rgsabound
0x18008eb53  xor     edi, edi
0x18008eb55  mov     [rbp+plUbound], esi
0x18008eb58  mov     [rbp+arg_4], edi
0x18008eb5b  lea     ecx, [rdi+11h]; vt
0x18008eb5e  lea     edx, [rdi+1]; cDims
0x18008eb61  call    cs:__imp_SafeArrayCreate
0x18008eb67  mov     [rbx], rax
0x18008eb6a  test    rax, rax
0x18008eb6d  jnz     short loc_18008EB37
0x18008eb6f  call    ?AfxThrowMemoryException@@YAXXZ; AfxThrowMemoryException(void)
```
