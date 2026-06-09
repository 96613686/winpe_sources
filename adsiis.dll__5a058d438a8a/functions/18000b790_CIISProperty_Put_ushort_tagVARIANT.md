# CIISProperty::Put(ushort *,tagVARIANT)

- ea: `0x18000b790`
- end: `0x18000bb35`
- name: `?Put@CIISProperty@@UEAAJPEAGUtagVARIANT@@@Z`
- size: `933`
- prototype: `int(CIISProperty *__hidden this, unsigned __int16 *, struct tagVARIANT *__struct_ptr)`
- caller_count: `0`
- callee_count: `6`
- tags: ``

## callees

- `0x18000b790`
- `0x18000c294`
- `0x18000c308`
- `0x180012fc8`
- `0x18001bef0`
- `0x18001e010`

## import_xrefs

- `OLEAUT32!__imp_VariantInit` at `0x18000b7e1`
- `OLEAUT32!__imp_VariantInit` at `0x18000b7eb`
- `OLEAUT32!__imp_VariantInit` at `0x18000b7e1`
- `OLEAUT32!__imp_VariantInit` at `0x18000b7eb`
- `OLEAUT32!__imp_VariantClear` at `0x18000ba25`
- `OLEAUT32!__imp_VariantClear` at `0x18000ba25`
- `OLEAUT32!__imp_VariantCopy` at `0x18000b7f8`
- `OLEAUT32!__imp_VariantCopy` at `0x18000b7f8`
- `OLEAUT32!__imp_VariantCopyInd` at `0x18000ba11`
- `OLEAUT32!__imp_VariantCopyInd` at `0x18000ba11`

## pseudocode

```c
__int64 __fastcall CIISProperty::Put(VARIANTARG *this, unsigned __int16 *a2, struct tagVARIANT *a3)
{
  HRESULT v7; // edi
  CIISProperty *v8; // rcx
  int v9; // ecx
  unsigned int v10; // ecx
  const OLECHAR *bstrVal; // rdx
  unsigned int v12; // eax
  int v13; // ecx
  IRecordInfo *pRecInfo; // xmm1_8
  int v15; // ecx
  int v16; // ecx
  int v17; // ecx
  int v18; // ecx
  int v19; // ecx
  VARIANTARG pvargDest; // [rsp+20h] [rbp-30h] BYREF
  VARIANTARG pvarg; // [rsp+38h] [rbp-18h] BYREF
  unsigned int v22; // [rsp+78h] [rbp+28h] BYREF
  unsigned int v23; // [rsp+88h] [rbp+38h] BYREF

  if ( !a2 )
    return 2147500035LL;
  v22 = 0;
  v23 = 0;
  memset(&pvarg, 0, sizeof(pvarg));
  memset(&pvargDest, 0, sizeof(pvargDest));
  VariantInit(&pvarg);
  VariantInit(&pvargDest);
  v7 = VariantCopy(&pvargDest, a3);
  if ( v7 < 0 )
    return (unsigned int)v7;
  v7 = ValidatePropertyObjProps(a2, &v22, &v23);
  if ( v7 < 0 )
    return (unsigned int)v7;
  if ( v23 > 0x1A )
  {
    switch ( v23 )
    {
      case 0x1Bu:
        v7 = CheckVariantDataType(&pvargDest, 0xBu);
        if ( v7 >= 0 )
        {
          v19 = *((_DWORD *)&this[2].decVal + 5);
          if ( pvargDest.iVal == -1 )
            v10 = v19 | 4;
          else
            v10 = v19 & 0xFFFFFFFB;
          goto LABEL_66;
        }
        return (unsigned int)v7;
      case 0x1Cu:
        v7 = CheckVariantDataType(&pvargDest, 0xBu);
        if ( v7 >= 0 )
        {
          v18 = *((_DWORD *)&this[2].decVal + 5);
          if ( pvargDest.iVal == -1 )
            v10 = v18 | 8;
          else
            v10 = v18 & 0xFFFFFFF7;
          goto LABEL_66;
        }
        return (unsigned int)v7;
      case 0x1Du:
        v7 = CheckVariantDataType(&pvargDest, 0xBu);
        if ( v7 >= 0 )
        {
          v17 = *((_DWORD *)&this[2].decVal + 5);
          if ( pvargDest.iVal == -1 )
            v10 = v17 | 0x10;
          else
            v10 = v17 & 0xFFFFFFEF;
          goto LABEL_66;
        }
        return (unsigned int)v7;
      case 0x1Eu:
        v7 = CheckVariantDataType(&pvargDest, 0xBu);
        if ( v7 >= 0 )
        {
          v16 = *((_DWORD *)&this[2].decVal + 5);
          if ( pvargDest.iVal == -1 )
            v10 = v16 | 0x20;
          else
            v10 = v16 & 0xFFFFFFDF;
          goto LABEL_66;
        }
        return (unsigned int)v7;
      case 0x1Fu:
        v7 = CheckVariantDataType(&pvargDest, 0xBu);
        if ( v7 >= 0 )
        {
          v15 = *((_DWORD *)&this[2].decVal + 5);
          if ( pvargDest.iVal == -1 )
            v10 = v15 | 0x40;
          else
            v10 = v15 & 0xFFFFFFBF;
          goto LABEL_66;
        }
        return (unsigned int)v7;
      case 0x20u:
        v7 = VariantCopyInd(&pvarg, &pvargDest);
        if ( v7 >= 0 )
        {
          VariantClear(this + 3);
          pRecInfo = pvarg.pRecInfo;
          *(_OWORD *)&this[3].vt = *(_OWORD *)&pvarg.vt;
          this[3].pRecInfo = pRecInfo;
        }
        return (unsigned int)v7;
    }
    return (unsigned int)-2147463162;
  }
  if ( v23 != 26 )
  {
    switch ( v23 )
    {
      case 0x11u:
        if ( *(_DWORD *)&this[7].vt )
        {
          return (unsigned int)-2147463153;
        }
        else
        {
          v7 = CIISProperty::ValidateSyntaxName(v8, pvargDest.bstrVal, &v22);
          if ( v7 >= 0 )
          {
            bstrVal = &psz;
            if ( pvargDest.llVal )
              bstrVal = pvargDest.bstrVal;
            v7 = ADsReAllocString(&this[1].decVal + 1, bstrVal);
            if ( v7 >= 0 )
            {
              v12 = v22;
              *(_DWORD *)&this[4].vt = v22;
              if ( ((v12 - 4) & 0xFFFFFFFB) == 0 )
                this[2].iVal = -1;
            }
          }
        }
        return (unsigned int)v7;
      case 0x12u:
        v7 = CheckVariantDataType(&pvargDest, 3u);
        if ( v7 >= 0 )
          *(_DWORD *)&this[2].vt = pvargDest.lVal;
        return (unsigned int)v7;
      case 0x13u:
        v7 = CheckVariantDataType(&pvargDest, 3u);
        if ( v7 >= 0 )
          this[2].decVal.Hi32 = pvargDest.cyVal.Lo;
        return (unsigned int)v7;
      case 0x16u:
        v7 = CheckVariantDataType(&pvargDest, 3u);
        if ( v7 >= 0 )
          return (unsigned int)(*(__int64 (__fastcall **)(CHAR *, _QWORD))(this->llVal + 72))(
                                 &this->cVal,
                                 pvargDest.cyVal.Lo);
        return (unsigned int)v7;
      case 0x17u:
        v7 = CheckVariantDataType(&pvargDest, 3u);
        if ( v7 >= 0 )
          *((_DWORD *)&this[2].decVal + 4) = pvargDest.lVal;
        return (unsigned int)v7;
      case 0x19u:
        v7 = CheckVariantDataType(&pvargDest, 0xBu);
        if ( v7 >= 0 )
        {
          v9 = *((_DWORD *)&this[2].decVal + 5);
          if ( pvargDest.iVal == -1 )
            v10 = v9 | 1;
          else
            v10 = v9 & 0xFFFFFFFE;
LABEL_66:
          *((_DWORD *)&this[2].decVal + 5) = v10;
          return (unsigned int)v7;
        }
        return (unsigned int)v7;
    }
    return (unsigned int)-2147463162;
  }
  v7 = CheckVariantDataType(&pvargDest, 0xBu);
  if ( v7 >= 0 )
  {
    v13 = *((_DWORD *)&this[2].decVal + 5);
    if ( pvargDest.iVal == -1 )
      v10 = v13 | 2;
    else
      v10 = v13 & 0xFFFFFFFD;
    goto LABEL_66;
  }
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x18000b790  mov     [rsp-18h+arg_0], rbx
0x18000b795  push    rbp
0x18000b796  push    rsi
0x18000b797  push    rdi
0x18000b798  mov     rbp, rsp
0x18000b79b  sub     rsp, 50h
0x18000b79f  mov     rdi, r8
0x18000b7a2  mov     rsi, rdx
0x18000b7a5  mov     rbx, rcx
0x18000b7a8  test    rdx, rdx
0x18000b7ab  jnz     short loc_18000B7B7
0x18000b7ad  mov     eax, 80004003h
0x18000b7b2  jmp     loc_18000BB28
0x18000b7b7  xor     eax, eax
0x18000b7b9  mov     [rbp+arg_8], 0
0x18000b7c0  xorps   xmm0, xmm0
0x18000b7c3  mov     qword ptr [rbp+pvarg+10h], rax
0x18000b7c7  xorps   xmm1, xmm1
0x18000b7ca  mov     qword ptr [rbp+pvargDest+10h], rax
0x18000b7ce  lea     rcx, [rbp+pvarg]; pvarg
0x18000b7d2  mov     [rbp+arg_18], 0
0x18000b7d9  movups  xmmword ptr [rbp+pvarg], xmm0
0x18000b7dd  movups  xmmword ptr [rbp+pvargDest], xmm1
0x18000b7e1  call    cs:__imp_VariantInit
0x18000b7e7  lea     rcx, [rbp+pvargDest]; pvarg
0x18000b7eb  call    cs:__imp_VariantInit
0x18000b7f1  mov     rdx, rdi; pvargSrc
0x18000b7f4  lea     rcx, [rbp+pvargDest]; pvargDest
0x18000b7f8  call    cs:__imp_VariantCopy
0x18000b7fe  mov     edi, eax
0x18000b800  test    eax, eax
0x18000b802  js      loc_18000BB26
0x18000b808  lea     r8, [rbp+arg_18]; unsigned int *
0x18000b80c  mov     rcx, rsi; String2
0x18000b80f  lea     rdx, [rbp+arg_8]; unsigned int *
0x18000b813  call    ?ValidatePropertyObjProps@@YAJPEAGPEAK1@Z; ValidatePropertyObjProps(ushort *,ulong *,ulong *)
0x18000b818  mov     edi, eax
0x18000b81a  test    eax, eax
0x18000b81c  js      loc_18000BB26
0x18000b822  mov     eax, [rbp+arg_18]
0x18000b825  cmp     eax, 1Ah
0x18000b828  ja      loc_18000B9D1
0x18000b82e  jz      loc_18000B99D
0x18000b834  sub     eax, 11h
0x18000b837  jz      loc_18000B92F
0x18000b83d  sub     eax, 1
0x18000b840  jz      loc_18000B90C
0x18000b846  sub     eax, 1
0x18000b849  jz      loc_18000B8E9
0x18000b84f  sub     eax, 3
0x18000b852  jz      short loc_18000B8B7
0x18000b854  sub     eax, 1
0x18000b857  jz      short loc_18000B894
0x18000b859  cmp     eax, 2
0x18000b85c  jnz     loc_18000B9FF
0x18000b862  lea     edx, [rax+9]; unsigned __int16
0x18000b865  lea     rcx, [rbp+pvargDest]; pvarSrc
0x18000b869  call    ?CheckVariantDataType@@YAJPEAUtagVARIANT@@G@Z; CheckVariantDataType(tagVARIANT *,ushort)
0x18000b86e  mov     edi, eax
0x18000b870  test    eax, eax
0x18000b872  js      loc_18000BB26
0x18000b878  mov     ecx, [rbx+44h]
0x18000b87b  or      eax, 0FFFFFFFFh
0x18000b87e  cmp     word ptr [rbp+pvargDest+8], ax
0x18000b882  jnz     short loc_18000B88C
0x18000b884  or      ecx, 1
0x18000b887  jmp     loc_18000BB23
0x18000b88c  and     ecx, 0FFFFFFFEh
0x18000b88f  jmp     loc_18000BB23
0x18000b894  mov     edx, 3; unsigned __int16
0x18000b899  lea     rcx, [rbp+pvargDest]; pvarSrc
0x18000b89d  call    ?CheckVariantDataType@@YAJPEAUtagVARIANT@@G@Z; CheckVariantDataType(tagVARIANT *,ushort)
0x18000b8a2  mov     edi, eax
0x18000b8a4  test    eax, eax
0x18000b8a6  js      loc_18000BB26
0x18000b8ac  mov     eax, dword ptr [rbp+pvargDest+8]
0x18000b8af  mov     [rbx+40h], eax
0x18000b8b2  jmp     loc_18000BB26
0x18000b8b7  mov     edx, 3; unsigned __int16
0x18000b8bc  lea     rcx, [rbp+pvargDest]; pvarSrc
0x18000b8c0  call    ?CheckVariantDataType@@YAJPEAUtagVARIANT@@G@Z; CheckVariantDataType(tagVARIANT *,ushort)
0x18000b8c5  mov     edi, eax
0x18000b8c7  test    eax, eax
0x18000b8c9  js      loc_18000BB26
0x18000b8cf  mov     edx, dword ptr [rbp+pvargDest+8]
0x18000b8d2  lea     rcx, [rbx+8]
0x18000b8d6  mov     rax, [rcx]
0x18000b8d9  mov     rax, [rax+48h]
0x18000b8dd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b8e2  mov     edi, eax
0x18000b8e4  jmp     loc_18000BB26
0x18000b8e9  mov     edx, 3; unsigned __int16
0x18000b8ee  lea     rcx, [rbp+pvargDest]; pvarSrc
0x18000b8f2  call    ?CheckVariantDataType@@YAJPEAUtagVARIANT@@G@Z; CheckVariantDataType(tagVARIANT *,ushort)
0x18000b8f7  mov     edi, eax
0x18000b8f9  test    eax, eax
0x18000b8fb  js      loc_18000BB26
0x18000b901  mov     eax, dword ptr [rbp+pvargDest+8]
0x18000b904  mov     [rbx+34h], eax
0x18000b907  jmp     loc_18000BB26
0x18000b90c  mov     edx, 3; unsigned __int16
0x18000b911  lea     rcx, [rbp+pvargDest]; pvarSrc
0x18000b915  call    ?CheckVariantDataType@@YAJPEAUtagVARIANT@@G@Z; CheckVariantDataType(tagVARIANT *,ushort)
0x18000b91a  mov     edi, eax
0x18000b91c  test    eax, eax
0x18000b91e  js      loc_18000BB26
0x18000b924  mov     eax, dword ptr [rbp+pvargDest+8]
0x18000b927  mov     [rbx+30h], eax
0x18000b92a  jmp     loc_18000BB26
0x18000b92f  cmp     dword ptr [rbx+0A8h], 0
0x18000b936  jz      short loc_18000B942
0x18000b938  mov     edi, 8000500Fh
0x18000b93d  jmp     loc_18000BB26
0x18000b942  mov     rdx, qword ptr [rbp+pvargDest+8]; unsigned __int16 *
0x18000b946  lea     r8, [rbp+arg_8]; unsigned int *
0x18000b94a  call    ?ValidateSyntaxName@CIISProperty@@QEAAJPEBGPEAK@Z; CIISProperty::ValidateSyntaxName(ushort const *,ulong *)
0x18000b94f  mov     edi, eax
0x18000b951  test    eax, eax
0x18000b953  js      loc_18000BB26
0x18000b959  mov     rax, qword ptr [rbp+pvargDest+8]
0x18000b95d  lea     rdx, psz
0x18000b964  test    rax, rax
0x18000b967  lea     rcx, [rbx+28h]
0x18000b96b  cmovnz  rdx, rax
0x18000b96f  call    ADsReAllocString
0x18000b974  mov     edi, eax
0x18000b976  test    eax, eax
0x18000b978  js      loc_18000BB26
0x18000b97e  mov     eax, [rbp+arg_8]
0x18000b981  mov     [rbx+60h], eax
0x18000b984  add     eax, 0FFFFFFFCh
0x18000b987  test    eax, 0FFFFFFFBh
0x18000b98c  jnz     loc_18000BB26
0x18000b992  mov     word ptr [rbx+38h], 0FFFFh
0x18000b998  jmp     loc_18000BB26
0x18000b99d  mov     edx, 0Bh; unsigned __int16
0x18000b9a2  lea     rcx, [rbp+pvargDest]; pvarSrc
0x18000b9a6  call    ?CheckVariantDataType@@YAJPEAUtagVARIANT@@G@Z; CheckVariantDataType(tagVARIANT *,ushort)
0x18000b9ab  mov     edi, eax
0x18000b9ad  test    eax, eax
0x18000b9af  js      loc_18000BB26
0x18000b9b5  mov     ecx, [rbx+44h]
0x18000b9b8  or      eax, 0FFFFFFFFh
0x18000b9bb  cmp     word ptr [rbp+pvargDest+8], ax
0x18000b9bf  jnz     short loc_18000B9C9
0x18000b9c1  or      ecx, 2
0x18000b9c4  jmp     loc_18000BB23
0x18000b9c9  and     ecx, 0FFFFFFFDh
0x18000b9cc  jmp     loc_18000BB23
0x18000b9d1  sub     eax, 1Bh
0x18000b9d4  jz      loc_18000BAFB
0x18000b9da  sub     eax, 1
0x18000b9dd  jz      loc_18000BAD1
0x18000b9e3  sub     eax, 1
0x18000b9e6  jz      loc_18000BAA7
0x18000b9ec  sub     eax, 1
0x18000b9ef  jz      loc_18000BA76
0x18000b9f5  sub     eax, 1
0x18000b9f8  jz      short loc_18000BA42
0x18000b9fa  cmp     eax, 1
0x18000b9fd  jz      short loc_18000BA09
0x18000b9ff  mov     edi, 80005006h
0x18000ba04  jmp     loc_18000BB26
0x18000ba09  lea     rdx, [rbp+pvargDest]; pvargSrc
0x18000ba0d  lea     rcx, [rbp+pvarg]; pvarDest
0x18000ba11  call    cs:__imp_VariantCopyInd
0x18000ba17  mov     edi, eax
0x18000ba19  test    eax, eax
0x18000ba1b  js      loc_18000BB26
0x18000ba21  lea     rcx, [rbx+48h]; pvarg
0x18000ba25  call    cs:__imp_VariantClear
0x18000ba2b  movups  xmm0, xmmword ptr [rbp+pvarg]
0x18000ba2f  movsd   xmm1, qword ptr [rbp+pvarg+10h]
0x18000ba34  movups  xmmword ptr [rbx+48h], xmm0
0x18000ba38  movsd   qword ptr [rbx+58h], xmm1
0x18000ba3d  jmp     loc_18000BB26
0x18000ba42  mov     edx, 0Bh; unsigned __int16
0x18000ba47  lea     rcx, [rbp+pvargDest]; pvarSrc
0x18000ba4b  call    ?CheckVariantDataType@@YAJPEAUtagVARIANT@@G@Z; CheckVariantDataType(tagVARIANT *,ushort)
0x18000ba50  mov     edi, eax
0x18000ba52  test    eax, eax
0x18000ba54  js      loc_18000BB26
0x18000ba5a  mov     ecx, [rbx+44h]
0x18000ba5d  or      eax, 0FFFFFFFFh
0x18000ba60  cmp     word ptr [rbp+pvargDest+8], ax
0x18000ba64  jnz     short loc_18000BA6E
0x18000ba66  or      ecx, 40h
0x18000ba69  jmp     loc_18000BB23
0x18000ba6e  and     ecx, 0FFFFFFBFh
0x18000ba71  jmp     loc_18000BB23
0x18000ba76  mov     edx, 0Bh; unsigned __int16
0x18000ba7b  lea     rcx, [rbp+pvargDest]; pvarSrc
0x18000ba7f  call    ?CheckVariantDataType@@YAJPEAUtagVARIANT@@G@Z; CheckVariantDataType(tagVARIANT *,ushort)
0x18000ba84  mov     edi, eax
0x18000ba86  test    eax, eax
0x18000ba88  js      loc_18000BB26
0x18000ba8e  mov     ecx, [rbx+44h]
0x18000ba91  or      eax, 0FFFFFFFFh
0x18000ba94  cmp     word ptr [rbp+pvargDest+8], ax
0x18000ba98  jnz     short loc_18000BAA2
0x18000ba9a  or      ecx, 20h
0x18000ba9d  jmp     loc_18000BB23
0x18000baa2  and     ecx, 0FFFFFFDFh
0x18000baa5  jmp     short loc_18000BB23
0x18000baa7  mov     edx, 0Bh; unsigned __int16
0x18000baac  lea     rcx, [rbp+pvargDest]; pvarSrc
0x18000bab0  call    ?CheckVariantDataType@@YAJPEAUtagVARIANT@@G@Z; CheckVariantDataType(tagVARIANT *,ushort)
0x18000bab5  mov     edi, eax
0x18000bab7  test    eax, eax
0x18000bab9  js      short loc_18000BB26
0x18000babb  mov     ecx, [rbx+44h]
0x18000babe  or      eax, 0FFFFFFFFh
0x18000bac1  cmp     word ptr [rbp+pvargDest+8], ax
0x18000bac5  jnz     short loc_18000BACC
0x18000bac7  or      ecx, 10h
0x18000baca  jmp     short loc_18000BB23
0x18000bacc  and     ecx, 0FFFFFFEFh
0x18000bacf  jmp     short loc_18000BB23
0x18000bad1  mov     edx, 0Bh; unsigned __int16
0x18000bad6  lea     rcx, [rbp+pvargDest]; pvarSrc
0x18000bada  call    ?CheckVariantDataType@@YAJPEAUtagVARIANT@@G@Z; CheckVariantDataType(tagVARIANT *,ushort)
0x18000badf  mov     edi, eax
0x18000bae1  test    eax, eax
0x18000bae3  js      short loc_18000BB26
0x18000bae5  mov     ecx, [rbx+44h]
0x18000bae8  or      eax, 0FFFFFFFFh
0x18000baeb  cmp     word ptr [rbp+pvargDest+8], ax
0x18000baef  jnz     short loc_18000BAF6
0x18000baf1  or      ecx, 8
0x18000baf4  jmp     short loc_18000BB23
0x18000baf6  and     ecx, 0FFFFFFF7h
0x18000baf9  jmp     short loc_18000BB23
0x18000bafb  mov     edx, 0Bh; unsigned __int16
0x18000bb00  lea     rcx, [rbp+pvargDest]; pvarSrc
0x18000bb04  call    ?CheckVariantDataType@@YAJPEAUtagVARIANT@@G@Z; CheckVariantDataType(tagVARIANT *,ushort)
0x18000bb09  mov     edi, eax
0x18000bb0b  test    eax, eax
0x18000bb0d  js      short loc_18000BB26
0x18000bb0f  mov     ecx, [rbx+44h]
0x18000bb12  or      eax, 0FFFFFFFFh
0x18000bb15  cmp     word ptr [rbp+pvargDest+8], ax
0x18000bb19  jnz     short loc_18000BB20
0x18000bb1b  or      ecx, 4
0x18000bb1e  jmp     short loc_18000BB23
0x18000bb20  and     ecx, 0FFFFFFFBh
0x18000bb23  mov     [rbx+44h], ecx
0x18000bb26  mov     eax, edi
0x18000bb28  mov     rbx, [rsp+50h+arg_0]
0x18000bb2d  add     rsp, 50h
0x18000bb31  pop     rdi
0x18000bb32  pop     rsi
0x18000bb33  pop     rbp
0x18000bb34  retn
```
