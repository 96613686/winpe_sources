# Windows::Internal::CLanguage::Compare(Windows::Internal::CLanguage const &,double *)

- ea: `0x180008330`
- end: `0x180008631`
- name: `?Compare@CLanguage@Internal@Windows@@QEBAJAEBV123@PEAN@Z`
- size: `769`
- prototype: `__int64 __fastcall(Windows::Internal::CLanguage *__hidden this, const struct Windows::Internal::CLanguage *, double *)`
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1800061f0`
- `0x1800064d0`

## callees

- `0x180008330`
- `0x180008638`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18000859f`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180008618`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18000859f`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180008618`

## pseudocode

```c
__int64 __fastcall Windows::Internal::CLanguage::Compare(
        Windows::Internal::CLanguage *this,
        const struct Windows::Internal::CLanguage *a2,
        double *a3)
{
  int v6; // edi
  bool v7; // zf
  __int64 v8; // rdx
  unsigned int v9; // r14d
  __int64 v10; // r8
  unsigned __int64 v11; // rax
  unsigned __int64 v12; // rcx
  int v13; // eax
  unsigned __int64 v14; // rax
  unsigned __int64 v15; // rcx
  double v16; // xmm0_8
  double v17; // xmm0_8
  char v18; // al
  __int64 v19; // rax
  unsigned __int64 v21; // rdx
  unsigned __int64 v22; // r8
  const WCHAR *v23; // rax
  int v24; // eax
  const WCHAR *v25; // r8
  int v26; // [rsp+70h] [rbp+18h] BYREF

  if ( !a3 )
    return 2147500035LL;
  v6 = 0;
  *a3 = 0.0;
  v7 = (*((_BYTE *)this + 72) & 8) == 0;
  v26 = 0;
  if ( v7 || (*((_BYTE *)a2 + 72) & 8) == 0 )
    return 2147943569LL;
  v8 = *((_QWORD *)this + 8);
  v9 = -2147023727;
  v10 = *((_QWORD *)a2 + 8);
  if ( (v10 & 0x3FFF000000uLL) <= (v8 & 0x3FFF000000uLL) )
  {
    if ( (v10 & 0x3FFF000000uLL) >= (v8 & 0x3FFF000000uLL) )
      v6 = 50;
    v26 = v6;
  }
  v11 = v8 & 0xFF0000;
  v12 = v10 & 0xFF0000;
  if ( v12 <= v11 && v12 >= v11 )
  {
    v13 = 75;
    if ( !v6 )
      v13 = 40;
    v6 = v13;
    v26 = v13;
  }
  v14 = (unsigned __int16)v8 & 0xFF80;
  v15 = (unsigned __int16)v10 & 0xFF80;
  if ( v15 > v14 || v15 < v14 )
  {
    if ( v6 == 75 )
    {
      Windows::Internal::CLanguage::CheckLanguageRegionAffinity(this, a2, &v26);
      v6 = v26;
    }
  }
  else if ( v6 == 75 )
  {
    v6 = 90;
    v21 = v8 & 0x7F;
    v22 = v10 & 0x7F;
    if ( v22 <= v21 && v22 >= v21 )
    {
      if ( (*((_BYTE *)this + 32) & 0x10) != 0 )
        v6 = 97;
      v23 = (const WCHAR *)*((_QWORD *)this + 2);
      if ( v23 && (v25 = (const WCHAR *)*((_QWORD *)a2 + 2)) != 0 )
      {
        if ( CompareStringOrdinal(v23, -1, v25, -1, 1) == 2 )
          v6 = 100;
      }
      else if ( v23 == *((const WCHAR **)a2 + 2) )
      {
        v6 = 100;
      }
    }
  }
  else if ( !v6 )
  {
    v6 = 10;
  }
  if ( ((*((_BYTE *)this + 72) & 0x20) != 0) == ((*((_BYTE *)a2 + 72) & 0x20) != 0) )
  {
    if ( (*((_BYTE *)this + 72) & 0x20) == 0 )
      goto LABEL_18;
    v24 = CompareStringOrdinal(*((LPCWCH *)this + 2), -1, *((LPCWCH *)a2 + 2), -1, 1);
    if ( !v24 )
    {
      v6 = 10;
      goto LABEL_19;
    }
    if ( v24 == 2 )
    {
LABEL_18:
      if ( !v6 )
      {
LABEL_20:
        if ( (*((_QWORD *)this + 8) & 0x3FFF000000LL) == 0x1D6E000000LL
          || (*((_QWORD *)a2 + 8) & 0x3FFF000000LL) == 0x1D6E000000LL )
        {
          v17 = *a3;
          if ( *a3 == 0.4 )
          {
            v19 = 0x3FE4CCCCCCCCCCCDLL;
          }
          else
          {
            if ( BYTE2(*((_QWORD *)this + 8)) && BYTE2(*((_QWORD *)this + 8)) != 0xEC || v17 >= 0.6 )
            {
              v18 = *((_BYTE *)a2 + 66);
              if ( v18 )
              {
                if ( v18 != -20 )
                  return v9;
              }
              if ( v17 >= 0.6 )
                return v9;
            }
            v19 = 0x3FE3333333333333LL;
          }
          *(_QWORD *)a3 = v19;
          return 0;
        }
        return v9;
      }
      goto LABEL_19;
    }
    if ( v6 >= 75 )
      goto LABEL_50;
    if ( !v6 )
      goto LABEL_20;
LABEL_53:
    v6 = 10;
    goto LABEL_19;
  }
  if ( v6 < 75 )
  {
    if ( !v6 )
      goto LABEL_20;
    goto LABEL_53;
  }
LABEL_50:
  v6 = 40;
LABEL_19:
  v9 = 0;
  v16 = (double)v6 / 100.0;
  *a3 = v16;
  if ( v16 <= 0.65 )
    goto LABEL_20;
  return 0;
}

```

## disassembly

```asm
0x180008330  push    rbx
0x180008332  push    rbp
0x180008333  push    rsi
0x180008334  sub     rsp, 40h
0x180008338  mov     rbx, r8
0x18000833b  mov     rbp, rdx
0x18000833e  mov     rsi, rcx
0x180008341  test    r8, r8
0x180008344  jz      loc_1800084E9
0x18000834a  mov     [rsp+58h+arg_0], rdi
0x18000834f  xor     edi, edi
0x180008351  mov     qword ptr [r8], 0
0x180008358  test    byte ptr [rcx+48h], 8
0x18000835c  mov     [rsp+58h+var_20], r14
0x180008361  mov     [rsp+58h+arg_10], edi
0x180008365  jz      loc_1800084F6
0x18000836b  test    byte ptr [rdx+48h], 8
0x18000836f  jz      loc_1800084F6
0x180008375  mov     rdx, [rcx+40h]
0x180008379  mov     r14d, 80070491h
0x18000837f  mov     r8, [rbp+40h]
0x180008383  mov     rax, rdx
0x180008386  mov     [rsp+58h+arg_8], r12
0x18000838b  mov     rcx, r8
0x18000838e  mov     [rsp+58h+var_28], r15
0x180008393  mov     r15, 3FFF000000h
0x18000839d  and     rax, r15
0x1800083a0  and     rcx, r15
0x1800083a3  cmp     rcx, rax
0x1800083a6  ja      short loc_1800083B6
0x1800083a8  mov     r9d, 32h ; '2'
0x1800083ae  cmovnb  edi, r9d
0x1800083b2  mov     [rsp+58h+arg_10], edi
0x1800083b6  mov     rax, rdx
0x1800083b9  mov     rcx, r8
0x1800083bc  and     eax, 0FF0000h
0x1800083c1  and     ecx, 0FF0000h
0x1800083c7  mov     r12d, 28h ; '('
0x1800083cd  cmp     rcx, rax
0x1800083d0  ja      short loc_1800083E5
0x1800083d2  jb      short loc_1800083E5
0x1800083d4  test    edi, edi
0x1800083d6  mov     eax, 4Bh ; 'K'
0x1800083db  cmovz   eax, r12d
0x1800083df  mov     edi, eax
0x1800083e1  mov     [rsp+58h+arg_10], eax
0x1800083e5  mov     rax, rdx
0x1800083e8  mov     rcx, r8
0x1800083eb  and     eax, 0FF80h
0x1800083f0  and     ecx, 0FF80h
0x1800083f6  cmp     rcx, rax
0x1800083f9  jbe     loc_180008516
0x1800083ff  cmp     edi, 4Bh ; 'K'
0x180008402  jz      loc_1800084FD
0x180008408  movzx   ecx, byte ptr [rsi+48h]
0x18000840c  movzx   eax, byte ptr [rbp+48h]
0x180008410  shr     cl, 5
0x180008413  shr     al, 5
0x180008416  and     cl, 1
0x180008419  and     al, 1
0x18000841b  cmp     cl, al
0x18000841d  jnz     loc_1800085BF
0x180008423  test    cl, cl
0x180008425  jnz     loc_180008586
0x18000842b  test    edi, edi
0x18000842d  jz      short loc_180008454
0x18000842f  movd    xmm0, edi
0x180008433  xor     r14d, r14d
0x180008436  cvtdq2pd xmm0, xmm0
0x18000843a  divsd   xmm0, cs:__real@4059000000000000
0x180008442  comisd  xmm0, cs:__real@3fe4cccccccccccd
0x18000844a  movsd   qword ptr [rbx], xmm0
0x18000844e  ja      loc_18000852F
0x180008454  mov     rcx, [rsi+40h]
0x180008458  mov     rdx, 1D6E000000h
0x180008462  mov     rax, rcx
0x180008465  and     rax, r15
0x180008468  cmp     rax, rdx
0x18000846b  jz      short loc_180008479
0x18000846d  mov     rax, [rbp+40h]
0x180008471  and     rax, r15
0x180008474  cmp     rax, rdx
0x180008477  jnz     short loc_1800084CA
0x180008479  movsd   xmm0, qword ptr [rbx]
0x18000847d  ucomisd xmm0, cs:__real@3fd999999999999a
0x180008485  jp      short loc_18000848D
0x180008487  jz      loc_1800085E9
0x18000848d  movsd   xmm1, cs:__real@3fe3333333333333
0x180008495  shr     rcx, 10h
0x180008499  test    cl, cl
0x18000849b  jz      short loc_1800084A2
0x18000849d  cmp     cl, 0ECh
0x1800084a0  jnz     short loc_1800084A8
0x1800084a2  comisd  xmm1, xmm0
0x1800084a6  ja      short loc_1800084BA
0x1800084a8  movzx   eax, byte ptr [rbp+42h]
0x1800084ac  test    al, al
0x1800084ae  jz      short loc_1800084B4
0x1800084b0  cmp     al, 0ECh
0x1800084b2  jnz     short loc_1800084CA
0x1800084b4  comisd  xmm1, xmm0
0x1800084b8  jbe     short loc_1800084CA
0x1800084ba  mov     rax, 3FE3333333333333h
0x1800084c4  mov     [rbx], rax
0x1800084c7  xor     r14d, r14d
0x1800084ca  mov     eax, r14d
0x1800084cd  mov     r12, [rsp+58h+arg_8]
0x1800084d2  mov     r15, [rsp+58h+var_28]
0x1800084d7  mov     rdi, [rsp+58h+arg_0]
0x1800084dc  mov     r14, [rsp+58h+var_20]
0x1800084e1  add     rsp, 40h
0x1800084e5  pop     rsi
0x1800084e6  pop     rbp
0x1800084e7  pop     rbx
0x1800084e8  retn
0x1800084e9  mov     eax, 80004003h
0x1800084ee  add     rsp, 40h
0x1800084f2  pop     rsi
0x1800084f3  pop     rbp
0x1800084f4  pop     rbx
0x1800084f5  retn
0x1800084f6  mov     eax, 80070491h
0x1800084fb  jmp     short loc_1800084D7
0x1800084fd  lea     r8, [rsp+58h+arg_10]; int *
0x180008502  mov     rdx, rbp; struct Windows::Internal::CLanguage *
0x180008505  mov     rcx, rsi; this
0x180008508  call    ?CheckLanguageRegionAffinity@CLanguage@Internal@Windows@@QEBAJAEBV123@PEAH@Z; Windows::Internal::CLanguage::CheckLanguageRegionAffinity(Windows::Internal::CLanguage const &,int *)
0x18000850d  mov     edi, [rsp+58h+arg_10]
0x180008511  jmp     loc_180008408
0x180008516  jb      loc_1800083FF
0x18000851c  cmp     edi, 4Bh ; 'K'
0x18000851f  jz      short loc_180008533
0x180008521  test    edi, edi
0x180008523  jnz     short loc_18000857B
0x180008525  mov     edi, 0Ah
0x18000852a  jmp     loc_180008408
0x18000852f  xor     eax, eax
0x180008531  jmp     short loc_1800084CD
0x180008533  mov     edi, 5Ah ; 'Z'
0x180008538  and     edx, 7Fh
0x18000853b  and     r8d, 7Fh
0x18000853f  cmp     r8, rdx
0x180008542  ja      loc_180008408
0x180008548  jb      loc_180008408
0x18000854e  test    byte ptr [rsi+20h], 10h
0x180008552  mov     eax, 61h ; 'a'
0x180008557  cmovnz  edi, eax
0x18000855a  mov     rax, [rsi+10h]
0x18000855e  test    rax, rax
0x180008561  jnz     loc_1800085F8
0x180008567  cmp     rax, [rbp+10h]
0x18000856b  jnz     loc_180008408
0x180008571  mov     edi, 64h ; 'd'
0x180008576  jmp     loc_180008408
0x18000857b  cmp     edi, 5Ah ; 'Z'
0x18000857e  jnz     loc_180008408
0x180008584  jmp     short loc_180008538
0x180008586  mov     r8, [rbp+10h]; lpString2
0x18000858a  mov     r9d, 0FFFFFFFFh; cchCount2
0x180008590  mov     rcx, [rsi+10h]; lpString1
0x180008594  mov     edx, r9d; cchCount1
0x180008597  mov     [rsp+58h+bIgnoreCase], 1; bIgnoreCase
0x18000859f  call    cs:__imp_CompareStringOrdinal
0x1800085a5  test    eax, eax
0x1800085a7  jz      short loc_1800085D6
0x1800085a9  cmp     eax, 2
0x1800085ac  jz      loc_18000842B
0x1800085b2  cmp     edi, 4Bh ; 'K'
0x1800085b5  jl      short loc_1800085E0
0x1800085b7  mov     edi, r12d
0x1800085ba  jmp     loc_18000842F
0x1800085bf  cmp     edi, 4Bh ; 'K'
0x1800085c2  jge     short loc_1800085B7
0x1800085c4  test    edi, edi
0x1800085c6  jz      loc_180008454
0x1800085cc  mov     edi, 0Ah
0x1800085d1  jmp     loc_18000842F
0x1800085d6  mov     edi, 0Ah
0x1800085db  jmp     loc_18000842F
0x1800085e0  test    edi, edi
0x1800085e2  jnz     short loc_1800085CC
0x1800085e4  jmp     loc_180008454
0x1800085e9  mov     rax, 3FE4CCCCCCCCCCCDh
0x1800085f3  jmp     loc_1800084C4
0x1800085f8  mov     r8, [rbp+10h]; lpString2
0x1800085fc  test    r8, r8
0x1800085ff  jz      loc_180008567
0x180008605  mov     edx, 0FFFFFFFFh; cchCount1
0x18000860a  mov     [rsp+58h+bIgnoreCase], 1; bIgnoreCase
0x180008612  mov     r9d, edx; cchCount2
0x180008615  mov     rcx, rax; lpString1
0x180008618  call    cs:__imp_CompareStringOrdinal
0x18000861e  cmp     eax, 2
0x180008621  jnz     loc_180008408
0x180008627  mov     edi, 64h ; 'd'
0x18000862c  jmp     loc_180008408
```
