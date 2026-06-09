# CompareSafeArray(tagSAFEARRAY *,tagSAFEARRAY *)

- ea: `0x1805ed930`
- end: `0x1805edacb`
- name: `?CompareSafeArray@@YA_NPEAUtagSAFEARRAY@@0@Z`
- size: `411`
- prototype: `bool __fastcall(SAFEARRAY *psa, SAFEARRAY *)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x1808abfac`

## callees

- `0x180040ad3`
- `0x1805ed930`

## import_xrefs

- `OLEAUT32!__imp_SafeArrayGetDim` at `0x1805ed97a`
- `OLEAUT32!__imp_SafeArrayGetDim` at `0x1805ed985`
- `OLEAUT32!__imp_SafeArrayGetDim` at `0x1805ed995`
- `OLEAUT32!__imp_SafeArrayGetDim` at `0x1805ed97a`
- `OLEAUT32!__imp_SafeArrayGetDim` at `0x1805ed985`
- `OLEAUT32!__imp_SafeArrayGetDim` at `0x1805ed995`
- `OLEAUT32!__imp_SafeArrayGetUBound` at `0x1805ed9ea`
- `OLEAUT32!__imp_SafeArrayGetUBound` at `0x1805eda18`
- `OLEAUT32!__imp_SafeArrayGetUBound` at `0x1805ed9ea`
- `OLEAUT32!__imp_SafeArrayGetUBound` at `0x1805eda18`
- `OLEAUT32!__imp_SafeArrayGetLBound` at `0x1805ed9d3`
- `OLEAUT32!__imp_SafeArrayGetLBound` at `0x1805eda01`
- `OLEAUT32!__imp_SafeArrayGetLBound` at `0x1805ed9d3`
- `OLEAUT32!__imp_SafeArrayGetLBound` at `0x1805eda01`
- `OLEAUT32!__imp_SafeArrayAccessData` at `0x1805eda73`
- `OLEAUT32!__imp_SafeArrayAccessData` at `0x1805eda82`
- `OLEAUT32!__imp_SafeArrayAccessData` at `0x1805eda73`
- `OLEAUT32!__imp_SafeArrayAccessData` at `0x1805eda82`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x1805edab4`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x1805edac2`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x1805edab4`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x1805edac2`

## pseudocode

```c
bool __fastcall CompareSafeArray(SAFEARRAY *psa, SAFEARRAY *a2)
{
  bool v4; // r12
  UINT Dim; // ebx
  int v7; // r14d
  UINT v8; // eax
  signed int v9; // ebx
  signed int v10; // r15d
  HRESULT v11; // ebx
  HRESULT v12; // eax
  int v13; // r15d
  LONG v14; // [rsp+20h] [rbp-20h] BYREF
  void *Buf2; // [rsp+28h] [rbp-18h] BYREF
  void *ppvData; // [rsp+30h] [rbp-10h] BYREF
  LONG plLbound; // [rsp+80h] [rbp+40h] BYREF
  LONG v18; // [rsp+90h] [rbp+50h] BYREF
  LONG plUbound; // [rsp+98h] [rbp+58h] BYREF

  v4 = 1;
  if ( psa )
  {
    if ( !a2 )
      return 0;
    if ( psa->cbElements != a2->cbElements )
      return 0;
    Dim = SafeArrayGetDim(psa);
    if ( Dim != SafeArrayGetDim(a2) )
      return 0;
    v7 = 1;
    v8 = SafeArrayGetDim(psa);
    plLbound = 0;
    v9 = 1;
    v10 = v8;
    v18 = 0;
    plUbound = -1;
    v14 = -1;
    while ( v9 <= v10 )
    {
      if ( !v7 )
        return v4;
      if ( SafeArrayGetLBound(psa, v9, &plLbound) < 0
        || SafeArrayGetUBound(psa, v9, &plUbound) < 0
        || SafeArrayGetLBound(a2, v9, &v18) < 0
        || SafeArrayGetUBound(a2, v9, &v14) < 0
        || plLbound != v18
        || plUbound != v14 )
      {
        return 0;
      }
      v7 *= plUbound - plLbound + 1;
      ++v9;
    }
    if ( v7 )
    {
      ppvData = 0;
      Buf2 = 0;
      v11 = SafeArrayAccessData(psa, &ppvData);
      v12 = SafeArrayAccessData(a2, &Buf2);
      v4 = 0;
      v13 = v12;
      if ( v11 >= 0 )
      {
        if ( v12 >= 0 )
          v4 = memcmp_0(ppvData, Buf2, psa->cbElements * v7) == 0;
        SafeArrayUnaccessData(psa);
      }
      if ( v13 >= 0 )
        SafeArrayUnaccessData(a2);
    }
  }
  else if ( a2 )
  {
    return 0;
  }
  return v4;
}

```

## disassembly

```asm
0x1805ed930  push    rbp
0x1805ed932  push    rbx
0x1805ed933  push    rsi
0x1805ed934  push    rdi
0x1805ed935  push    r12
0x1805ed937  push    r14
0x1805ed939  push    r15
0x1805ed93b  mov     rbp, rsp
0x1805ed93e  sub     rsp, 40h
0x1805ed942  mov     rdi, rdx
0x1805ed945  mov     rsi, rcx
0x1805ed948  mov     r12d, 1
0x1805ed94e  test    rcx, rcx
0x1805ed951  jnz     short loc_1805ED96D
0x1805ed953  test    rdx, rdx
0x1805ed956  jz      loc_1805EDA54
0x1805ed95c  xor     al, al
0x1805ed95e  add     rsp, 40h
0x1805ed962  pop     r15
0x1805ed964  pop     r14
0x1805ed966  pop     r12
0x1805ed968  pop     rdi
0x1805ed969  pop     rsi
0x1805ed96a  pop     rbx
0x1805ed96b  pop     rbp
0x1805ed96c  retn
0x1805ed96d  test    rdi, rdi
0x1805ed970  jz      short loc_1805ED95C
0x1805ed972  mov     eax, [rdx+4]
0x1805ed975  cmp     [rcx+4], eax
0x1805ed978  jnz     short loc_1805ED95C
0x1805ed97a  call    cs:__imp_SafeArrayGetDim
0x1805ed980  mov     rcx, rdi; psa
0x1805ed983  mov     ebx, eax
0x1805ed985  call    cs:__imp_SafeArrayGetDim
0x1805ed98b  cmp     ebx, eax
0x1805ed98d  jnz     short loc_1805ED95C
0x1805ed98f  mov     rcx, rsi; psa
0x1805ed992  mov     r14d, r12d
0x1805ed995  call    cs:__imp_SafeArrayGetDim
0x1805ed99b  mov     [rbp+plLbound], 0
0x1805ed9a2  mov     ebx, r12d
0x1805ed9a5  mov     r15d, eax
0x1805ed9a8  mov     [rbp+arg_10], 0
0x1805ed9af  or      eax, 0FFFFFFFFh
0x1805ed9b2  mov     [rbp+plUbound], eax
0x1805ed9b5  mov     [rbp+var_20], eax
0x1805ed9b8  cmp     ebx, r15d
0x1805ed9bb  jg      loc_1805EDA4F
0x1805ed9c1  test    r14d, r14d
0x1805ed9c4  jz      loc_1805EDA54
0x1805ed9ca  lea     r8, [rbp+plLbound]; plLbound
0x1805ed9ce  mov     edx, ebx; nDim
0x1805ed9d0  mov     rcx, rsi; psa
0x1805ed9d3  call    cs:__imp_SafeArrayGetLBound
0x1805ed9d9  test    eax, eax
0x1805ed9db  js      loc_1805ED95C
0x1805ed9e1  lea     r8, [rbp+plUbound]; plUbound
0x1805ed9e5  mov     edx, ebx; nDim
0x1805ed9e7  mov     rcx, rsi; psa
0x1805ed9ea  call    cs:__imp_SafeArrayGetUBound
0x1805ed9f0  test    eax, eax
0x1805ed9f2  js      loc_1805ED95C
0x1805ed9f8  lea     r8, [rbp+arg_10]; plLbound
0x1805ed9fc  mov     edx, ebx; nDim
0x1805ed9fe  mov     rcx, rdi; psa
0x1805eda01  call    cs:__imp_SafeArrayGetLBound
0x1805eda07  test    eax, eax
0x1805eda09  js      loc_1805ED95C
0x1805eda0f  lea     r8, [rbp+var_20]; plUbound
0x1805eda13  mov     edx, ebx; nDim
0x1805eda15  mov     rcx, rdi; psa
0x1805eda18  call    cs:__imp_SafeArrayGetUBound
0x1805eda1e  test    eax, eax
0x1805eda20  js      loc_1805ED95C
0x1805eda26  mov     ecx, [rbp+plLbound]
0x1805eda29  cmp     ecx, [rbp+arg_10]
0x1805eda2c  jnz     loc_1805ED95C
0x1805eda32  mov     eax, [rbp+plUbound]
0x1805eda35  cmp     eax, [rbp+var_20]
0x1805eda38  jnz     loc_1805ED95C
0x1805eda3e  sub     eax, ecx
0x1805eda40  add     eax, r12d
0x1805eda43  imul    r14d, eax
0x1805eda47  add     ebx, r12d
0x1805eda4a  jmp     loc_1805ED9B8
0x1805eda4f  test    r14d, r14d
0x1805eda52  jnz     short loc_1805EDA5C
0x1805eda54  mov     al, r12b
0x1805eda57  jmp     loc_1805ED95E
0x1805eda5c  lea     rdx, [rbp+ppvData]; ppvData
0x1805eda60  mov     [rbp+ppvData], 0
0x1805eda68  mov     rcx, rsi; psa
0x1805eda6b  mov     [rbp+Buf2], 0
0x1805eda73  call    cs:__imp_SafeArrayAccessData
0x1805eda79  lea     rdx, [rbp+Buf2]; ppvData
0x1805eda7d  mov     rcx, rdi; psa
0x1805eda80  mov     ebx, eax
0x1805eda82  call    cs:__imp_SafeArrayAccessData
0x1805eda88  xor     r12b, r12b
0x1805eda8b  mov     r15d, eax
0x1805eda8e  test    ebx, ebx
0x1805eda90  js      short loc_1805EDABA
0x1805eda92  test    eax, eax
0x1805eda94  js      short loc_1805EDAB1
0x1805eda96  imul    r14d, [rsi+4]
0x1805eda9b  mov     rdx, [rbp+Buf2]; Buf2
0x1805eda9f  mov     rcx, [rbp+ppvData]; Buf1
0x1805edaa3  mov     r8d, r14d; Size
0x1805edaa6  call    memcmp_0
0x1805edaab  test    eax, eax
0x1805edaad  setz    r12b
0x1805edab1  mov     rcx, rsi; psa
0x1805edab4  call    cs:__imp_SafeArrayUnaccessData
0x1805edaba  test    r15d, r15d
0x1805edabd  js      short loc_1805EDA54
0x1805edabf  mov     rcx, rdi; psa
0x1805edac2  call    cs:__imp_SafeArrayUnaccessData
0x1805edac8  jmp     short loc_1805EDA54
```
