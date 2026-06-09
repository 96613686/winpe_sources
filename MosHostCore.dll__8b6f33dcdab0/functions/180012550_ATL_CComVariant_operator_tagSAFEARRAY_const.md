# ATL::CComVariant::operator=(tagSAFEARRAY const *)

- ea: `0x180012550`
- end: `0x1800125f1`
- name: `??4CComVariant@ATL@@QEAAAEAV01@PEBUtagSAFEARRAY@@@Z`
- size: `161`
- prototype: `VARIANTARG *__fastcall(VARIANTARG *pvt, SAFEARRAY *psa)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x18001be24`

## callees

- `0x18000ec4c`
- `0x180012550`

## import_xrefs

- `OLEAUT32!__imp_VariantClear` at `0x180012560`
- `OLEAUT32!__imp_VariantClear` at `0x180012560`
- `OLEAUT32!__imp_SafeArrayCopy` at `0x18001257c`
- `OLEAUT32!__imp_SafeArrayCopy` at `0x18001257c`
- `OLEAUT32!__imp_SafeArrayGetVartype` at `0x180012594`
- `OLEAUT32!__imp_SafeArrayGetVartype` at `0x180012594`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
VARIANTARG *__fastcall ATL::CComVariant::operator=(VARIANTARG *pvt, SAFEARRAY *psa)
{
  HRESULT v4; // eax
  SAFEARRAY *ppsaOut; // [rsp+38h] [rbp+10h] BYREF

  VariantClear(pvt);
  ppsaOut = 0;
  if ( psa )
  {
    v4 = SafeArrayCopy(psa, &ppsaOut);
    if ( v4 < 0 || !ppsaOut )
    {
      pvt->vt = 10;
      pvt->lVal = v4;
      ATL::AtlThrowImpl(-2147024882);
    }
    if ( SafeArrayGetVartype(psa, &pvt->vt) >= 0 && pvt && pvt->vt == 13 && (psa->fFeatures & 0x440) == 0x440 )
      pvt->vt = 9;
    pvt->vt |= 0x2000u;
    pvt->llVal = (LONGLONG)ppsaOut;
  }
  return pvt;
}

```

## disassembly

```asm
0x180012550  mov     [rsp+arg_0], rbx
0x180012555  push    rdi
0x180012556  sub     rsp, 20h
0x18001255a  mov     rdi, rdx
0x18001255d  mov     rbx, rcx
0x180012560  call    cs:__imp_VariantClear
0x180012566  mov     [rsp+28h+ppsaOut], 0
0x18001256f  test    rdi, rdi
0x180012572  jz      short loc_1800125D0
0x180012574  lea     rdx, [rsp+28h+ppsaOut]; ppsaOut
0x180012579  mov     rcx, rdi; psa
0x18001257c  call    cs:__imp_SafeArrayCopy
0x180012582  test    eax, eax
0x180012584  js      short loc_1800125DE
0x180012586  cmp     [rsp+28h+ppsaOut], 0
0x18001258c  jz      short loc_1800125DE
0x18001258e  mov     rdx, rbx; pvt
0x180012591  mov     rcx, rdi; psa
0x180012594  call    cs:__imp_SafeArrayGetVartype
0x18001259a  test    eax, eax
0x18001259c  js      short loc_1800125BF
0x18001259e  test    rbx, rbx
0x1800125a1  jz      short loc_1800125BF
0x1800125a3  cmp     word ptr [rbx], 0Dh
0x1800125a7  jnz     short loc_1800125BF
0x1800125a9  movzx   eax, word ptr [rdi+2]
0x1800125ad  mov     ecx, 440h
0x1800125b2  and     ax, cx
0x1800125b5  cmp     ax, cx
0x1800125b8  jnz     short loc_1800125BF
0x1800125ba  mov     word ptr [rbx], 9
0x1800125bf  mov     eax, 2000h
0x1800125c4  or      [rbx], ax
0x1800125c7  mov     rax, [rsp+28h+ppsaOut]
0x1800125cc  mov     [rbx+8], rax
0x1800125d0  mov     rax, rbx
0x1800125d3  mov     rbx, [rsp+28h+arg_0]
0x1800125d8  add     rsp, 20h
0x1800125dc  pop     rdi
0x1800125dd  retn
0x1800125de  mov     ecx, 8007000Eh; int
0x1800125e3  mov     word ptr [rbx], 0Ah
0x1800125e8  mov     [rbx+8], eax
0x1800125eb  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
```
