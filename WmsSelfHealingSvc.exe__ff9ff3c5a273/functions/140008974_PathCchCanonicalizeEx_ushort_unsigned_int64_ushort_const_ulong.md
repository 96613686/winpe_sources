# PathCchCanonicalizeEx(ushort *,unsigned __int64,ushort const *,ulong)

- ea: `0x140008974`
- end: `0x140008e2e`
- name: `?PathCchCanonicalizeEx@@YAJPEAG_KPEBGK@Z`
- size: `1210`
- prototype: `__int64 __fastcall(unsigned __int16 *, __int64, wchar_t *)`
- caller_count: `1`
- callee_count: `5`
- tags: `reparse_path`

## callers

- `0x140008e34`

## callees

- `0x140005b48`
- `0x140008974`
- `0x140009000`
- `0x1400091bc`
- `0x1400097d4`

## import_xrefs

- `msvcrt!iswalpha` at `0x140008a5f`
- `msvcrt!iswalpha` at `0x140008a79`
- `msvcrt!iswalpha` at `0x140008a5f`
- `msvcrt!iswalpha` at `0x140008a79`
- `msvcrt!wcschr` at `0x140008aaf`
- `msvcrt!wcschr` at `0x140008aaf`

## pseudocode

```c
__int64 __fastcall PathCchCanonicalizeEx(unsigned __int16 *a1, __int64 a2, wchar_t *a3)
{
  __int64 result; // rax
  signed int v6; // r14d
  unsigned __int64 v7; // rbp
  signed int v8; // eax
  unsigned __int16 *v9; // rbx
  const wchar_t *v10; // r9
  int v11; // r11d
  wchar_t *v12; // r10
  int v13; // ecx
  int v14; // edx
  int v15; // ecx
  int v16; // r8d
  __int64 v17; // r13
  wchar_t *v18; // rax
  unsigned __int64 v19; // rdx
  unsigned __int64 v20; // rax
  wchar_t *v21; // rcx
  unsigned __int64 v22; // r8
  unsigned __int16 *v23; // r9
  __int64 v24; // r11
  __int64 v25; // r10
  unsigned __int16 *v26; // rcx
  unsigned __int16 v27; // ax
  unsigned int v28; // r11d
  unsigned __int16 *v29; // rbx
  unsigned __int16 *v30; // rcx
  unsigned __int16 *v31; // rax
  unsigned __int16 *v32; // rcx
  unsigned __int16 *v33; // r11
  int v34; // ebx
  unsigned __int16 *v35; // r10
  const wchar_t *v36; // r9
  int v37; // ecx
  int v38; // edx
  int v39; // ecx
  int v40; // r8d
  unsigned int v41; // [rsp+28h] [rbp-40h]
  unsigned __int16 *v42; // [rsp+30h] [rbp-38h] BYREF
  unsigned __int64 v43; // [rsp+38h] [rbp-30h] BYREF
  wchar_t *Str; // [rsp+78h] [rbp+10h] BYREF

  Str = 0;
  v42 = 0;
  result = StringCchCopyW(a1, 0x104u, &LocaleName);
  v6 = result;
  if ( (int)result < 0 )
    return result;
  v43 = 260;
  v7 = 260;
  if ( (unsigned int)PathIsUNCEx(a3, (const unsigned __int16 **)&Str) )
  {
    v8 = StringCchCopyExW(a1, 0x104u, L"\\\\", &v42, &v43, v41);
    a3 = Str;
    v6 = v8;
    v9 = v42;
    v7 = v43;
  }
  else
  {
    v9 = a1;
    v10 = L"\\\\?\\";
    v11 = 4;
    v12 = a3;
    do
    {
      v13 = *v12;
      v14 = v13 + 32;
      if ( (unsigned int)(v13 - 65) > 0x19 )
        v14 = *v12;
      v15 = *v10;
      v16 = v15 + 32;
      if ( (unsigned int)(v15 - 65) > 0x19 )
        v16 = *v10;
      if ( !--v11 )
        break;
      if ( !v14 )
        break;
      ++v12;
      ++v10;
    }
    while ( v14 == v16 );
    if ( v14 == v16 )
    {
      if ( iswalpha(a3[4]) && a3[5] == 58 )
        a3 += 4;
    }
    else
    {
      iswalpha(*a3);
    }
  }
  if ( !a3 )
    return 2147942487LL;
  if ( v6 < 0 )
  {
LABEL_79:
    StringCchCopyW(a1, 0x104u, &LocaleName);
    if ( v6 == -2147024774 )
      return v28;
    return (unsigned int)v6;
  }
  v17 = -1;
  while ( *a3 )
  {
    v18 = wcschr(a3, 0x5Cu);
    if ( v18 )
    {
      v19 = v18 - a3;
    }
    else
    {
      v19 = -1;
      do
        ++v19;
      while ( a3[v19] );
    }
    if ( v19 > 0x100 )
    {
      v6 = -2147024690;
      goto LABEL_79;
    }
    switch ( v19 )
    {
      case 1uLL:
        if ( *a3 == 46 )
        {
          if ( a3[1] )
          {
            a3 += 2;
          }
          else
          {
            ++a3;
            if ( v9 > a1 && !(unsigned int)PathCchIsRoot(a1) )
              v6 = StringCchCopyW(--v9, ++v7, &LocaleName);
          }
          goto LABEL_78;
        }
        break;
      case 2uLL:
        if ( *a3 == 46 && a3[1] == 46 )
        {
          if ( v9 <= a1 || (unsigned int)PathCchIsRoot(a1) )
          {
            if ( a3[2] == 92 )
              ++a3;
          }
          else
          {
            if ( a1 >= --v9 )
              goto LABEL_42;
            while ( *--v9 != 92 )
            {
              if ( a1 >= v9 )
                goto LABEL_42;
            }
            if ( v9 )
            {
              v7 = 260 - (v9 - a1);
            }
            else
            {
LABEL_42:
              v9 = a1;
              v7 = 260;
            }
            v6 = StringCchCopyW(v9, v7, &LocaleName);
          }
          a3 += 2;
          goto LABEL_78;
        }
        break;
      case 0uLL:
        v19 = *a3 == 92;
        break;
    }
    if ( !v7 )
    {
      v6 = -2147024809;
      goto LABEL_67;
    }
    if ( v7 <= 0x7FFFFFFF )
    {
      v20 = v19;
      v21 = a3;
      v22 = v7;
      v23 = v9;
      v24 = 0;
      do
      {
        if ( !v20 )
          break;
        if ( !*v21 )
          break;
        *v23++ = *v21++;
        --v20;
        ++v24;
        --v22;
      }
      while ( v22 );
      v25 = v24 - 1;
      v26 = v23 - 1;
      if ( v22 )
        v25 = v24;
      v6 = v22 == 0 ? 0x8007007A : 0;
      if ( v22 )
        v26 = v23;
      *v26 = 0;
      if ( (int)(v6 + 0x80000000) < 0 || v6 == -2147024774 )
      {
        v9 += v25;
        v7 -= v25;
      }
LABEL_67:
      if ( v6 == -2147024774 && v19 == 1 && *a3 == 92 )
      {
        v27 = a3[1];
        if ( !v27 || v27 == 46 && !a3[2] )
          break;
        if ( v7 == 1 && v27 == 46 && a3[2] == 46 )
        {
          *v9 = 0;
          v7 = 0;
          ++v9;
          v6 = 0;
        }
      }
      goto LABEL_77;
    }
    *v9 = 0;
    v6 = -2147024809;
LABEL_77:
    a3 += v19;
LABEL_78:
    if ( v6 < 0 )
      goto LABEL_79;
  }
  if ( v9 > a1 )
  {
    v29 = v9 - 1;
    if ( *v29 == 46 )
    {
      v30 = v29;
      v31 = v29;
      while ( v30 != a1 )
      {
        v30 = v31 - 1;
        if ( *(v31 - 1) != 42 )
        {
          *v29 = 0;
          --v31;
          v29 = v30;
          if ( *v30 == 46 )
            continue;
        }
        goto LABEL_92;
      }
      *v29 = 0;
    }
  }
  do
LABEL_92:
    ++v17;
  while ( a1[v17] );
  v32 = &a1[v17];
  if ( v32 >= a1 + 7 )
  {
    v33 = v32 - 7;
    v34 = 7;
    v35 = v32 - 7;
    v36 = L"::$DATA";
    do
    {
      v37 = *v35;
      v38 = v37 + 32;
      if ( (unsigned int)(v37 - 65) > 0x19 )
        v38 = *v35;
      v39 = *v36;
      v40 = v39 + 32;
      if ( (unsigned int)(v39 - 65) > 0x19 )
        v40 = *v36;
      if ( !--v34 )
        break;
      if ( !v38 )
        break;
      ++v35;
      ++v36;
    }
    while ( v38 == v40 );
    if ( v38 == v40 )
      *v33 = 0;
  }
  if ( !*a1 )
    *(_DWORD *)a1 = 92;
  if ( a1[1] == 58 && !a1[2] )
    *((_DWORD *)a1 + 1) = 92;
  return 0;
}

```

## disassembly

```asm
0x140008974  mov     rax, rsp
0x140008977  mov     [rax+8], rbx
0x14000897b  mov     [rax+18h], rbp
0x14000897f  mov     [rax+10h], rdx
0x140008983  push    rsi
0x140008984  push    rdi
0x140008985  push    r13
0x140008987  push    r14
0x140008989  push    r15
0x14000898b  sub     rsp, 40h
0x14000898f  mov     rdi, r8
0x140008992  xor     r15d, r15d
0x140008995  mov     ebx, 104h
0x14000899a  mov     [rax+10h], r15
0x14000899e  mov     edx, ebx; unsigned __int64
0x1400089a0  mov     [rax-38h], r15
0x1400089a4  lea     r8, LocaleName; unsigned __int16 *
0x1400089ab  mov     rsi, rcx
0x1400089ae  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x1400089b3  mov     r14d, eax
0x1400089b6  test    eax, eax
0x1400089b8  js      loc_140008D3D
0x1400089be  lea     rdx, [rsp+68h+Str]; unsigned __int16 **
0x1400089c3  mov     [rsp+68h+var_30], rbx
0x1400089c8  mov     rcx, rdi; unsigned __int16 *
0x1400089cb  mov     ebp, ebx
0x1400089cd  call    ?PathIsUNCEx@@YAHPEBGPEAPEBG@Z; PathIsUNCEx(ushort const *,ushort const * *)
0x1400089d2  test    eax, eax
0x1400089d4  jz      short loc_140008A0A
0x1400089d6  lea     rax, [rsp+68h+var_30]
0x1400089db  mov     edx, ebx; unsigned __int64
0x1400089dd  lea     r9, [rsp+68h+var_38]; unsigned __int16 **
0x1400089e2  mov     [rsp+68h+var_48], rax; unsigned __int64 *
0x1400089e7  lea     r8, asc_140010CE8; "\\\\"
0x1400089ee  mov     rcx, rsi; unsigned __int16 *
0x1400089f1  call    ?StringCchCopyExW@@YAJPEAG_KPEBGPEAPEAGPEA_KK@Z; StringCchCopyExW(ushort *,unsigned __int64,ushort const *,ushort * *,unsigned __int64 *,ulong)
0x1400089f6  mov     rdi, [rsp+68h+Str]
0x1400089fb  mov     r14d, eax
0x1400089fe  mov     rbx, [rsp+68h+var_38]
0x140008a03  mov     rbp, [rsp+68h+var_30]
0x140008a08  jmp     short loc_140008A7F
0x140008a0a  mov     rbx, rsi
0x140008a0d  lea     r9, asc_140010D00; "\\\\?\\"
0x140008a14  mov     r11d, 4
0x140008a1a  mov     r10, rdi
0x140008a1d  movzx   ecx, word ptr [r10]
0x140008a21  lea     eax, [rcx-41h]
0x140008a24  cmp     eax, 19h
0x140008a27  lea     edx, [rcx+20h]
0x140008a2a  cmova   edx, ecx
0x140008a2d  movzx   ecx, word ptr [r9]
0x140008a31  lea     eax, [rcx-41h]
0x140008a34  cmp     eax, 19h
0x140008a37  lea     r8d, [rcx+20h]
0x140008a3b  cmova   r8d, ecx
0x140008a3f  sub     r11d, 1
0x140008a43  jz      short loc_140008A56
0x140008a45  test    edx, edx
0x140008a47  jz      short loc_140008A56
0x140008a49  add     r10, 2
0x140008a4d  add     r9, 2
0x140008a51  cmp     edx, r8d
0x140008a54  jz      short loc_140008A1D
0x140008a56  cmp     edx, r8d
0x140008a59  jnz     short loc_140008A76
0x140008a5b  movzx   ecx, word ptr [rdi+8]; C
0x140008a5f  call    cs:__imp_iswalpha
0x140008a65  test    eax, eax
0x140008a67  jz      short loc_140008A7F
0x140008a69  cmp     word ptr [rdi+0Ah], 3Ah ; ':'
0x140008a6e  jnz     short loc_140008A7F
0x140008a70  add     rdi, 8
0x140008a74  jmp     short loc_140008A7F
0x140008a76  movzx   ecx, word ptr [rdi]; C
0x140008a79  call    cs:__imp_iswalpha
0x140008a7f  test    rdi, rdi
0x140008a82  jnz     short loc_140008A8E
0x140008a84  mov     eax, 80070057h
0x140008a89  jmp     loc_140008D3D
0x140008a8e  test    r14d, r14d
0x140008a91  js      loc_140008D15
0x140008a97  or      r13, 0FFFFFFFFFFFFFFFFh
0x140008a9b  mov     eax, 5Ch ; '\'
0x140008aa0  cmp     [rdi], r15w
0x140008aa4  jz      loc_140008D61
0x140008aaa  mov     edx, eax; Ch
0x140008aac  mov     rcx, rdi; Str
0x140008aaf  call    cs:__imp_wcschr
0x140008ab5  mov     rdx, rax
0x140008ab8  test    rax, rax
0x140008abb  jz      short loc_140008AC5
0x140008abd  sub     rdx, rdi
0x140008ac0  sar     rdx, 1
0x140008ac3  jmp     short loc_140008AD2
0x140008ac5  mov     rdx, r13
0x140008ac8  inc     rdx
0x140008acb  cmp     [rdi+rdx*2], r15w
0x140008ad0  jnz     short loc_140008AC8
0x140008ad2  cmp     rdx, 100h
0x140008ad9  ja      loc_140008D56
0x140008adf  mov     r10d, 1
0x140008ae5  cmp     rdx, r10
0x140008ae8  jnz     short loc_140008B42
0x140008aea  cmp     word ptr [rdi], 2Eh ; '.'
0x140008aee  jnz     loc_140008BF6
0x140008af4  cmp     [rdi+2], r15w
0x140008af9  jnz     short loc_140008B39
0x140008afb  add     rdi, 2
0x140008aff  cmp     rbx, rsi
0x140008b02  jbe     loc_140008D0C
0x140008b08  mov     rcx, rsi; unsigned __int16 *
0x140008b0b  call    ?PathCchIsRoot@@YAHPEBG@Z; PathCchIsRoot(ushort const *)
0x140008b10  test    eax, eax
0x140008b12  jnz     loc_140008D0C
0x140008b18  sub     rbx, 2
0x140008b1c  lea     r8, LocaleName; unsigned __int16 *
0x140008b23  inc     rbp
0x140008b26  mov     rcx, rbx; unsigned __int16 *
0x140008b29  mov     rdx, rbp; unsigned __int64
0x140008b2c  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x140008b31  mov     r14d, eax
0x140008b34  jmp     loc_140008D0C
0x140008b39  add     rdi, 4
0x140008b3d  jmp     loc_140008D0C
0x140008b42  cmp     rdx, 2
0x140008b46  jnz     loc_140008BE2
0x140008b4c  cmp     word ptr [rdi], 2Eh ; '.'
0x140008b50  jnz     loc_140008BF6
0x140008b56  lea     r15, [rdi+2]
0x140008b5a  cmp     word ptr [r15], 2Eh ; '.'
0x140008b5f  jnz     loc_140008BF3
0x140008b65  cmp     rbx, rsi
0x140008b68  jbe     short loc_140008BC9
0x140008b6a  mov     rcx, rsi; unsigned __int16 *
0x140008b6d  call    ?PathCchIsRoot@@YAHPEBG@Z; PathCchIsRoot(ushort const *)
0x140008b72  test    eax, eax
0x140008b74  jnz     short loc_140008BC9
0x140008b76  add     rbx, 0FFFFFFFFFFFFFFFEh
0x140008b7a  cmp     rsi, rbx
0x140008b7d  jnb     short loc_140008B92
0x140008b7f  mov     eax, 5Ch ; '\'
0x140008b84  sub     rbx, 2
0x140008b88  cmp     [rbx], ax
0x140008b8b  jz      short loc_140008BB1
0x140008b8d  cmp     rsi, rbx
0x140008b90  jb      short loc_140008B84
0x140008b92  mov     rbx, rsi
0x140008b95  mov     ebp, 104h
0x140008b9a  lea     r8, LocaleName; unsigned __int16 *
0x140008ba1  mov     rdx, rbp; unsigned __int64
0x140008ba4  mov     rcx, rbx; unsigned __int16 *
0x140008ba7  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x140008bac  mov     r14d, eax
0x140008baf  jmp     short loc_140008BD6
0x140008bb1  test    rbx, rbx
0x140008bb4  jz      short loc_140008B92
0x140008bb6  mov     rax, rbx
0x140008bb9  mov     ebp, 104h
0x140008bbe  sub     rax, rsi
0x140008bc1  sar     rax, 1
0x140008bc4  sub     rbp, rax
0x140008bc7  jmp     short loc_140008B9A
0x140008bc9  mov     eax, 5Ch ; '\'
0x140008bce  cmp     [rdi+4], ax
0x140008bd2  cmovz   rdi, r15
0x140008bd6  add     rdi, 4
0x140008bda  xor     r15d, r15d
0x140008bdd  jmp     loc_140008D0C
0x140008be2  test    rdx, rdx
0x140008be5  jnz     short loc_140008BF6
0x140008be7  lea     eax, [rdx+5Ch]
0x140008bea  cmp     [rdi], ax
0x140008bed  cmovz   rdx, r10
0x140008bf1  jmp     short loc_140008BF6
0x140008bf3  xor     r15d, r15d
0x140008bf6  test    rbp, rbp
0x140008bf9  jz      loc_140008CA8
0x140008bff  mov     eax, 7FFFFFFFh
0x140008c04  cmp     rbp, rax
0x140008c07  ja      short loc_140008C0E
0x140008c09  cmp     rdx, rax
0x140008c0c  jb      short loc_140008C1D
0x140008c0e  mov     [rbx], r15w
0x140008c12  mov     r14d, 80070057h
0x140008c18  jmp     loc_140008D08
0x140008c1d  mov     rax, rdx
0x140008c20  mov     rcx, rdi
0x140008c23  mov     r8, rbp
0x140008c26  mov     r9, rbx
0x140008c29  mov     r11, r15
0x140008c2c  test    rax, rax
0x140008c2f  jz      short loc_140008C58
0x140008c31  movzx   r10d, word ptr [rcx]
0x140008c35  test    r10w, r10w
0x140008c39  jz      short loc_140008C58
0x140008c3b  mov     [r9], r10w
0x140008c3f  add     rcx, 2
0x140008c43  mov     r10d, 1
0x140008c49  add     r9, 2
0x140008c4d  sub     rax, r10
0x140008c50  add     r11, r10
0x140008c53  sub     r8, r10
0x140008c56  jnz     short loc_140008C2C
0x140008c58  test    r8, r8
0x140008c5b  lea     r10, [r11-1]
0x140008c5f  mov     rax, r8
0x140008c62  lea     rcx, [r9-2]
0x140008c66  cmovnz  r10, r11
0x140008c6a  neg     rax
0x140008c6d  mov     r11d, 8007007Ah
0x140008c73  sbb     r14d, r14d
0x140008c76  not     r14d
0x140008c79  and     r14d, r11d
0x140008c7c  test    r8, r8
0x140008c7f  cmovnz  rcx, r9
0x140008c83  mov     [rcx], r15w
0x140008c87  mov     ecx, 80000000h
0x140008c8c  lea     eax, [r14+rcx]
0x140008c90  test    ecx, eax
0x140008c92  jnz     short loc_140008C99
0x140008c94  cmp     r14d, r11d
0x140008c97  jnz     short loc_140008CA0
0x140008c99  lea     rbx, [rbx+r10*2]
0x140008c9d  sub     rbp, r10
0x140008ca0  mov     r10d, 1
0x140008ca6  jmp     short loc_140008CBB
0x140008ca8  mov     r14d, 80070057h
0x140008cae  test    rbp, rbp
0x140008cb1  jnz     loc_140008C0E
0x140008cb7  lea     r11d, [r14+23h]
0x140008cbb  cmp     r14d, r11d
0x140008cbe  jnz     short loc_140008D08
0x140008cc0  cmp     rdx, r10
0x140008cc3  jnz     short loc_140008D08
0x140008cc5  mov     eax, 5Ch ; '\'
0x140008cca  cmp     [rdi], ax
0x140008ccd  jnz     short loc_140008D08
0x140008ccf  movzx   eax, word ptr [rdi+2]
0x140008cd3  test    ax, ax
0x140008cd6  jz      loc_140008D61
0x140008cdc  cmp     ax, 2Eh ; '.'
0x140008ce0  jnz     short loc_140008CE9
0x140008ce2  cmp     [rdi+4], r15w
0x140008ce7  jz      short loc_140008D61
0x140008ce9  cmp     rbp, r10
0x140008cec  jnz     short loc_140008D08
0x140008cee  cmp     ax, 2Eh ; '.'
0x140008cf2  jnz     short loc_140008D08
0x140008cf4  cmp     [rdi+4], ax
0x140008cf8  jnz     short loc_140008D08
0x140008cfa  mov     [rbx], r15w
0x140008cfe  mov     rbp, r15
0x140008d01  add     rbx, 2
0x140008d05  mov     r14d, r15d
0x140008d08  lea     rdi, [rdi+rdx*2]
0x140008d0c  test    r14d, r14d
0x140008d0f  jns     loc_140008A9B
0x140008d15  mov     r11d, 800700CEh
0x140008d1b  lea     r8, LocaleName; unsigned __int16 *
0x140008d22  mov     edx, 104h; unsigned __int64
0x140008d27  mov     rcx, rsi; unsigned __int16 *
0x140008d2a  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x140008d2f  cmp     r14d, 8007007Ah
0x140008d36  cmovz   r14d, r11d
0x140008d3a  mov     eax, r14d
0x140008d3d  lea     r11, [rsp+68h+var_28]
0x140008d42  mov     rbx, [r11+30h]
0x140008d46  mov     rbp, [r11+40h]
0x140008d4a  mov     rsp, r11
0x140008d4d  pop     r15
0x140008d4f  pop     r14
0x140008d51  pop     r13
0x140008d53  pop     rdi
0x140008d54  pop     rsi
0x140008d55  retn
0x140008d56  mov     r11d, 800700CEh
0x140008d5c  mov     r14d, r11d
0x140008d5f  jmp     short loc_140008D1B
0x140008d61  cmp     rbx, rsi
0x140008d64  jbe     short loc_140008D9B
0x140008d66  sub     rbx, 2
0x140008d6a  cmp     word ptr [rbx], 2Eh ; '.'
0x140008d6e  jnz     short loc_140008D9B
0x140008d70  mov     rcx, rbx
0x140008d73  mov     rax, rbx
0x140008d76  cmp     rcx, rsi
0x140008d79  jz      short loc_140008D97
0x140008d7b  lea     rcx, [rax-2]
0x140008d7f  cmp     word ptr [rcx], 2Ah ; '*'
0x140008d83  jz      short loc_140008D9B
0x140008d85  mov     [rbx], r15w
0x140008d89  mov     rax, rcx
0x140008d8c  cmp     word ptr [rcx], 2Eh ; '.'
0x140008d90  mov     rbx, rcx
0x140008d93  jz      short loc_140008D76
0x140008d95  jmp     short loc_140008D9B
0x140008d97  mov     [rbx], r15w
0x140008d9b  inc     r13
0x140008d9e  cmp     [rsi+r13*2], r15w
0x140008da3  jnz     short loc_140008D9B
  ... truncated ...
```
