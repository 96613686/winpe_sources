# ARI::Identity::Convert<ushort,ushort *,ushort const *,PACKAGE_ID>::PackageIdBasicFromFullName(ushort const *,uint,uint *,uchar *)

- ea: `0x18000a600`
- end: `0x18000ae0d`
- name: `?PackageIdBasicFromFullName@?$Convert@GPEAGPEBGUPACKAGE_ID@@@Identity@ARI@@SAJPEBGIPEAIPEAE@Z`
- size: `2061`
- prototype: `__int64 __fastcall(LPCWCH lpString1)`
- caller_count: `10`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x180007ebc`
- `0x180008130`
- `0x180009438`
- `0x1800095d0`
- `0x180009d80`
- `0x18000a170`
- `0x18000af10`
- `0x18001e3dc`
- `0x18002f2c0`
- `0x180048f40`

## callees

- `0x18000a600`

## import_xrefs

- `msvcrt!_wcsnicmp` at `0x18000ac22`
- `msvcrt!_wcsnicmp` at `0x18000ad16`
- `msvcrt!_wcsnicmp` at `0x18000ad30`
- `msvcrt!_wcsnicmp` at `0x18000ad4e`
- `msvcrt!_wcsnicmp` at `0x18000ad93`
- `msvcrt!_wcsnicmp` at `0x18000adcb`
- `msvcrt!_wcsnicmp` at `0x18000adf4`
- `msvcrt!_wcsnicmp` at `0x18000ac22`
- `msvcrt!_wcsnicmp` at `0x18000ad16`
- `msvcrt!_wcsnicmp` at `0x18000ad30`
- `msvcrt!_wcsnicmp` at `0x18000ad4e`
- `msvcrt!_wcsnicmp` at `0x18000ad93`
- `msvcrt!_wcsnicmp` at `0x18000adcb`
- `msvcrt!_wcsnicmp` at `0x18000adf4`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18000a6ee`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18000a736`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18000a790`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18000a8b5`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18000a901`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18000a962`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18000a6ee`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18000a736`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18000a790`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18000a8b5`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18000a901`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18000a962`

## pseudocode

```c
__int64 __fastcall ARI::Identity::Convert<unsigned short,unsigned short *,unsigned short const *,PACKAGE_ID>::PackageIdBasicFromFullName(
        LPCWCH lpString1,
        __int64 a2,
        unsigned int *a3,
        __int64 a4)
{
  const WCHAR *v4; // rsi
  LPCWCH v5; // rdx
  __int64 i; // rbp
  WCHAR v7; // cx
  __int64 result; // rax
  unsigned __int64 j; // rbx
  __int64 v10; // r9
  unsigned __int64 k; // rbx
  unsigned __int64 v12; // rdx
  int v13; // r12d
  unsigned __int64 m; // rbx
  unsigned int v15; // r13d
  _WORD *v16; // rdx
  WCHAR v17; // ax
  __int16 v18; // ax
  _WORD *v19; // rdx
  unsigned __int64 v20; // r11
  unsigned __int16 v21; // cx
  const WCHAR *v22; // rdx
  const WCHAR *v23; // r14
  unsigned int v24; // r15d
  unsigned __int64 n; // rbx
  __int64 v26; // r9
  unsigned __int64 ii; // rbx
  unsigned __int64 v28; // rdx
  unsigned __int64 jj; // rbx
  unsigned int v30; // ebp
  WCHAR *v31; // rdi
  WCHAR kk; // ax
  const WCHAR *v33; // rsi
  unsigned int v34; // ecx
  char *mm; // rdx
  int v36; // r8d
  unsigned int v37; // ecx
  char *v38; // r9
  char *nn; // rdx
  int v40; // r8d
  unsigned int v41; // ecx
  char *v42; // r10
  char *i1; // rdx
  int v44; // r8d
  unsigned int v45; // ecx
  char *v46; // r9
  char *i2; // rdx
  int v48; // r8d
  WCHAR *v49; // rdi
  const WCHAR *v50; // r9
  WCHAR i3; // ax
  unsigned int v52; // r10d
  _WORD *v53; // rdi
  unsigned __int16 *v54; // r9
  int v55; // r8d
  const char *i4; // rdx
  LPCWCH v57; // [rsp+80h] [rbp+8h]
  unsigned __int64 v58; // [rsp+80h] [rbp+8h]
  char v59; // [rsp+88h] [rbp+10h]

  v4 = lpString1;
  if ( !lpString1 || !a3 || *a3 && !a4 )
    return 87;
  v5 = lpString1;
  for ( i = 0; ; i = (unsigned int)(i + 1) )
  {
    v7 = *v5;
    v57 = v5;
    if ( *v5 == 95 )
      break;
    if ( !v7 || (unsigned int)i >= 0x32 )
      return 87;
    if ( v7 >= 0x61u )
    {
      if ( v7 > 0x7Au )
        return 87;
    }
    else if ( v7 >= 0x41u )
    {
      if ( v7 > 0x5Au )
        return 87;
    }
    else if ( (unsigned __int16)(v7 - 45) > 1u && (unsigned __int16)(v7 - 48) > 9u )
    {
      return 87;
    }
    ++v5;
  }
  if ( (unsigned int)(i - 3) > 0x2F )
    return 87;
  for ( j = 0; j < 0x18; ++j )
  {
    v10 = (unsigned int)dword_18004E190[4 * j];
    if ( (unsigned int)i == v10 && CompareStringOrdinal(v4, i, (&off_18004E198)[2 * j], v10, 1) == 2 )
      return 87;
  }
  for ( k = 0; k < 0x17; ++k )
  {
    v12 = (unsigned int)dword_18004E020[4 * k];
    if ( (unsigned int)i >= v12 && CompareStringOrdinal(v4, v12, (&off_18004E028)[2 * k], v12, 1) == 2 )
      return 87;
  }
  if ( (_DWORD)i && v4[i - 1] == 46 )
    return 87;
  v13 = 5;
  if ( (unsigned int)i >= 5uLL )
  {
    for ( m = 0; m <= (unsigned __int64)(unsigned int)i - 5; ++m )
    {
      if ( CompareStringOrdinal(&v4[m], 5, L".xn--", 5, 1) == 2 )
        return 87;
    }
  }
  v15 = 0;
  v16 = v57 + 1;
  v17 = v57[1];
  if ( v17 != 95 )
  {
    while ( v17 && v15 < 0x17 )
    {
      v17 = v16[1];
      ++v16;
      ++v15;
      if ( v17 == 95 )
        goto LABEL_41;
    }
    if ( *v16 != 95 )
      return 87;
LABEL_41:
    if ( v15 > 0x17 )
      return 87;
  }
  v18 = v16[1];
  v19 = v16 + 1;
  v20 = 0;
  v58 = 0;
  if ( v18 != 95 )
  {
    while ( v18 && v20 < 7 )
    {
      v18 = v19[1];
      ++v19;
      v58 = ++v20;
      if ( v18 == 95 )
        goto LABEL_46;
    }
    if ( *v19 != 95 )
      return 87;
LABEL_46:
    if ( v20 > 7 )
      return 87;
  }
  v21 = v19[1];
  v22 = v19 + 1;
  v23 = v22;
  if ( v21 == 126 )
  {
    if ( v22[1] != 95 )
      return 87;
    v59 = 1;
    v24 = 1;
  }
  else
  {
    v59 = 0;
    v24 = 0;
    while ( v21 != 95 )
    {
      if ( !v21 || v24 >= 0x1E )
        return 87;
      if ( (unsigned __int16)(v21 - 97) > 0x19u )
      {
        if ( v21 >= 0x41u )
        {
          if ( v21 > 0x5Au )
            return 87;
        }
        else if ( (unsigned __int16)(v21 - 45) > 1u && (unsigned __int16)(v21 - 48) > 9u )
        {
          return 87;
        }
      }
      v21 = v22[1];
      ++v22;
      ++v24;
    }
  }
  if ( v24 > 0x1E )
    return 87;
  if ( v24 )
  {
    for ( n = 0; n < 0x18; ++n )
    {
      v26 = (unsigned int)dword_18004E190[4 * n];
      if ( v24 == v26 && CompareStringOrdinal(v23, v24, (&off_18004E198)[2 * n], v26, 1) == 2 )
        return 87;
    }
    for ( ii = 0; ii < 0x17; ++ii )
    {
      v28 = (unsigned int)dword_18004E020[4 * ii];
      if ( v24 >= v28 && CompareStringOrdinal(v23, v28, (&off_18004E028)[2 * ii], v28, 1) == 2 )
        return 87;
    }
    if ( v23[v24 - 1] == 46 )
      return 87;
    if ( v24 >= 5uLL )
    {
      for ( jj = 0; jj <= (unsigned __int64)v24 - 5; ++jj )
      {
        if ( CompareStringOrdinal(&v23[jj], 5, L".xn--", 5, 1) == 2 )
          return 87;
      }
    }
    v20 = v58;
  }
  v30 = 2 * (v24 + i) + 80;
  if ( *a3 < v30 )
  {
    *a3 = v30;
    return 122;
  }
  v31 = (WCHAR *)(a4 + 48);
  *(_DWORD *)a4 = 0;
  *(_QWORD *)(a4 + 16) = a4 + 48;
  for ( kk = *v4; *v4 != 95; kk = *v4 )
  {
    ++v4;
    *v31++ = kk;
  }
  v33 = v4 + 1;
  *v31 = 0;
  v34 = 0;
  for ( mm = (char *)v33; ; mm += 2 )
  {
    v36 = *(unsigned __int16 *)mm;
    if ( v36 == 46 )
      break;
    if ( (__int64)((mm - (char *)v33) & 0xFFFFFFFFFFFFFFFEuLL) >= 10 || (unsigned __int16)(v36 - 48) > 9u )
      return 87;
    v34 = v36 + 2 * (5 * v34 - 24);
  }
  if ( v34 > 0xFFFF )
    return 87;
  *(_WORD *)(a4 + 14) = v34;
  v37 = 0;
  v38 = (char *)&v33[(unsigned int)((mm - (char *)v33) >> 1) + 1];
  for ( nn = v38; ; nn += 2 )
  {
    v40 = *(unsigned __int16 *)nn;
    if ( v40 == 46 )
      break;
    if ( (__int64)((nn - v38) & 0xFFFFFFFFFFFFFFFEuLL) >= 10 || (unsigned __int16)(v40 - 48) > 9u )
      return 87;
    v37 = v40 + 2 * (5 * v37 - 24);
  }
  if ( v37 > 0xFFFF )
    return 87;
  *(_WORD *)(a4 + 12) = v37;
  v41 = 0;
  v42 = &v38[2 * (unsigned int)((nn - v38) >> 1) + 2];
  for ( i1 = v42; ; i1 += 2 )
  {
    v44 = *(unsigned __int16 *)i1;
    if ( v44 == 46 )
      break;
    if ( (__int64)((i1 - v42) & 0xFFFFFFFFFFFFFFFEuLL) >= 10 || (unsigned __int16)(v44 - 48) > 9u )
      return 87;
    v41 = v44 + 2 * (5 * v41 - 24);
  }
  if ( v41 > 0xFFFF )
    return 87;
  *(_WORD *)(a4 + 10) = v41;
  v45 = 0;
  v46 = &v42[2 * (unsigned int)((i1 - v42) >> 1) + 2];
  for ( i2 = v46; ; i2 += 2 )
  {
    v48 = *(unsigned __int16 *)i2;
    if ( v48 == 95 )
      break;
    if ( (__int64)((i2 - v46) & 0xFFFFFFFFFFFFFFFEuLL) >= 10 || (unsigned __int16)(v48 - 48) > 9u )
      goto LABEL_139;
    v45 = v48 + 2 * (5 * v45 - 24);
  }
  if ( v45 <= 0xFFFF )
  {
    *(_WORD *)(a4 + 8) = v45;
    result = 0;
    goto LABEL_112;
  }
LABEL_139:
  result = 87;
LABEL_112:
  if ( !(_DWORD)result )
  {
    switch ( v20 )
    {
      case 3uLL:
        if ( !_wcsnicmp(&v33[v15 + 1], L"x86", 3u) )
        {
          v13 = 0;
          goto LABEL_119;
        }
        if ( !_wcsnicmp(&v33[v15 + 1], L"arm", 3u) )
        {
LABEL_119:
          if ( !v59 || v13 == 11 )
          {
            v49 = v31 + 1;
            *(_DWORD *)(a4 + 4) = v13;
            v50 = &v33[v15 + 2 + v58];
            *(_QWORD *)(a4 + 32) = v49;
            for ( i3 = *v50; *v50 != 95; i3 = *v50 )
            {
              ++v50;
              *v49++ = i3;
            }
            v52 = 0;
            *v49 = 0;
            v53 = v49 + 1;
            *(_QWORD *)(a4 + 40) = v53;
            v54 = (unsigned __int16 *)(v50 + 1);
            *(_QWORD *)(a4 + 24) = 0;
LABEL_123:
            v55 = *v54;
            if ( (_WORD)v55 )
            {
              if ( v52 < 0xD )
              {
                for ( i4 = "1234567890abcdefghjkmnpqrstvwxyzABCDEFGHJKMNPQRSTVWXYZ"; *i4; ++i4 )
                {
                  if ( v55 == *i4 )
                  {
                    *v53 = v55;
                    ++v54;
                    ++v53;
                    ++v52;
                    goto LABEL_123;
                  }
                }
              }
            }
            else if ( v52 == 13 )
            {
              *v53 = 0;
              *a3 = v30;
              return 0;
            }
          }
          return 87;
        }
        if ( !_wcsnicmp(&v33[v15 + 1], L"x64", 3u) )
        {
          v13 = 9;
          goto LABEL_119;
        }
        break;
      case 5uLL:
        if ( !_wcsnicmp(&v33[v15 + 1], L"arm64", 5u) )
        {
          v13 = 12;
          goto LABEL_119;
        }
        break;
      case 6uLL:
        if ( !_wcsnicmp(&v33[v15 + 1], L"x86a64", 6u) )
        {
          v13 = 14;
          goto LABEL_119;
        }
        break;
      case 7uLL:
        if ( !_wcsnicmp(&v33[v15 + 1], L"neutral", 7u) )
        {
          v13 = 11;
          goto LABEL_119;
        }
        if ( !_wcsnicmp(&v33[v15 + 1], L"unknown", 7u) )
        {
          v13 = 0xFFFF;
          goto LABEL_119;
        }
        break;
    }
    return 87;
  }
  return result;
}

```

## disassembly

```asm
0x18000a600  mov     [rsp+arg_18], r9
0x18000a605  mov     [rsp+arg_10], r8
0x18000a60a  mov     [rsp+arg_8], edx
0x18000a60e  push    rbx
0x18000a60f  push    rbp
0x18000a610  push    rsi
0x18000a611  push    rdi
0x18000a612  push    r12
0x18000a614  push    r13
0x18000a616  push    r14
0x18000a618  push    r15
0x18000a61a  sub     rsp, 38h
0x18000a61e  mov     rsi, rcx
0x18000a621  test    rcx, rcx
0x18000a624  jz      short loc_18000A684
0x18000a626  test    r8, r8
0x18000a629  jz      short loc_18000A684
0x18000a62b  cmp     dword ptr [r8], 0
0x18000a62f  ja      short loc_18000A69A
0x18000a631  mov     rdx, rsi
0x18000a634  xor     ebp, ebp
0x18000a636  mov     r8d, 61h ; 'a'
0x18000a63c  mov     r9d, 41h ; 'A'
0x18000a642  movzx   ecx, word ptr [rdx]
0x18000a645  mov     [rsp+78h+arg_0], rdx
0x18000a64d  cmp     cx, 5Fh ; '_'
0x18000a651  jz      short loc_18000A6AD
0x18000a653  test    cx, cx
0x18000a656  jz      short loc_18000A684
0x18000a658  cmp     ebp, 32h ; '2'
0x18000a65b  jnb     short loc_18000A684
0x18000a65d  cmp     r8w, cx
0x18000a661  jbe     loc_18000ADAC
0x18000a667  cmp     r9w, cx
0x18000a66b  jbe     short loc_18000A67E
0x18000a66d  lea     eax, [rcx-2Dh]
0x18000a670  cmp     ax, 1
0x18000a674  ja      short loc_18000A6A1
0x18000a676  add     rdx, 2
0x18000a67a  inc     ebp
0x18000a67c  jmp     short loc_18000A642
0x18000a67e  cmp     cx, 5Ah ; 'Z'
0x18000a682  jbe     short loc_18000A676
0x18000a684  mov     eax, 57h ; 'W'
0x18000a689  add     rsp, 38h
0x18000a68d  pop     r15
0x18000a68f  pop     r14
0x18000a691  pop     r13
0x18000a693  pop     r12
0x18000a695  pop     rdi
0x18000a696  pop     rsi
0x18000a697  pop     rbp
0x18000a698  pop     rbx
0x18000a699  retn
0x18000a69a  test    r9, r9
0x18000a69d  jnz     short loc_18000A631
0x18000a69f  jmp     short loc_18000A684
0x18000a6a1  sub     cx, 30h ; '0'
0x18000a6a5  cmp     cx, 9
0x18000a6a9  jbe     short loc_18000A676
0x18000a6ab  jmp     short loc_18000A684
0x18000a6ad  lea     eax, [rbp-3]
0x18000a6b0  cmp     eax, 2Fh ; '/'
0x18000a6b3  ja      short loc_18000A684
0x18000a6b5  mov     edi, ebp
0x18000a6b7  lea     r10, __ImageBase
0x18000a6be  xor     ebx, ebx
0x18000a6c0  cmp     rbx, 18h
0x18000a6c4  jnb     short loc_18000A705
0x18000a6c6  mov     r8, rbx
0x18000a6c9  add     r8, r8
0x18000a6cc  mov     r9d, ds:rva dword_18004E190[r10+r8*8]; cchCount2
0x18000a6d4  cmp     rdi, r9
0x18000a6d7  jnz     short loc_18000A700
0x18000a6d9  mov     r8, ds:rva off_18004E198[r10+r8*8]; lpString2
0x18000a6e1  mov     edx, ebp; cchCount1
0x18000a6e3  mov     rcx, rsi; lpString1
0x18000a6e6  mov     [rsp+78h+bIgnoreCase], 1; bIgnoreCase
0x18000a6ee  call    cs:__imp_CompareStringOrdinal
0x18000a6f4  cmp     eax, 2
0x18000a6f7  jz      short loc_18000A684
0x18000a6f9  lea     r10, __ImageBase
0x18000a700  inc     rbx
0x18000a703  jmp     short loc_18000A6C0
0x18000a705  xor     ebx, ebx
0x18000a707  cmp     rbx, 17h
0x18000a70b  jnb     short loc_18000A751
0x18000a70d  mov     r8, rbx
0x18000a710  add     r8, r8
0x18000a713  mov     edx, ds:rva dword_18004E020[r10+r8*8]; cchCount1
0x18000a71b  cmp     rdi, rdx
0x18000a71e  jb      short loc_18000A74C
0x18000a720  mov     r8, ds:rva off_18004E028[r10+r8*8]; lpString2
0x18000a728  mov     r9d, edx; cchCount2
0x18000a72b  mov     rcx, rsi; lpString1
0x18000a72e  mov     [rsp+78h+bIgnoreCase], 1; bIgnoreCase
0x18000a736  call    cs:__imp_CompareStringOrdinal
0x18000a73c  cmp     eax, 2
0x18000a73f  jz      loc_18000A684
0x18000a745  lea     r10, __ImageBase
0x18000a74c  inc     rbx
0x18000a74f  jmp     short loc_18000A707
0x18000a751  test    ebp, ebp
0x18000a753  jz      short loc_18000A761
0x18000a755  cmp     word ptr [rsi+rbp*2-2], 2Eh ; '.'
0x18000a75b  jz      loc_18000A684
0x18000a761  mov     r12d, 5
0x18000a767  cmp     rdi, r12
0x18000a76a  jb      short loc_18000A7AB
0x18000a76c  xor     ebx, ebx
0x18000a76e  add     rdi, 0FFFFFFFFFFFFFFFBh
0x18000a772  cmp     rbx, rdi
0x18000a775  ja      short loc_18000A7A4
0x18000a777  lea     rcx, [rsi+rbx*2]; lpString1
0x18000a77b  mov     [rsp+78h+bIgnoreCase], 1; bIgnoreCase
0x18000a783  mov     r9d, r12d; cchCount2
0x18000a786  lea     r8, String2; ".xn--"
0x18000a78d  mov     edx, r12d; cchCount1
0x18000a790  call    cs:__imp_CompareStringOrdinal
0x18000a796  cmp     eax, 2
0x18000a799  jz      loc_18000A684
0x18000a79f  inc     rbx
0x18000a7a2  jmp     short loc_18000A772
0x18000a7a4  lea     r10, __ImageBase
0x18000a7ab  mov     rdx, [rsp+78h+arg_0]
0x18000a7b3  xor     r13d, r13d
0x18000a7b6  add     rdx, 2
0x18000a7ba  movzx   eax, word ptr [rdx]
0x18000a7bd  cmp     ax, 5Fh ; '_'
0x18000a7c1  jz      short loc_18000A7F1
0x18000a7c3  test    ax, ax
0x18000a7c6  jz      loc_18000A985
0x18000a7cc  cmp     r13d, 17h
0x18000a7d0  jnb     loc_18000A985
0x18000a7d6  movzx   eax, word ptr [rdx+2]
0x18000a7da  add     rdx, 2
0x18000a7de  inc     r13d
0x18000a7e1  cmp     ax, 5Fh ; '_'
0x18000a7e5  jnz     short loc_18000A7C3
0x18000a7e7  cmp     r13d, 17h
0x18000a7eb  ja      loc_18000A684
0x18000a7f1  movzx   eax, word ptr [rdx+2]
0x18000a7f5  add     rdx, 2
0x18000a7f9  xor     r11d, r11d
0x18000a7fc  mov     [rsp+78h+arg_0], r11
0x18000a804  cmp     ax, 5Fh ; '_'
0x18000a808  jz      short loc_18000A840
0x18000a80a  test    ax, ax
0x18000a80d  jz      loc_18000A976
0x18000a813  cmp     r11, 7
0x18000a817  jnb     loc_18000A976
0x18000a81d  movzx   eax, word ptr [rdx+2]
0x18000a821  add     rdx, 2
0x18000a825  inc     r11
0x18000a828  mov     [rsp+78h+arg_0], r11
0x18000a830  cmp     ax, 5Fh ; '_'
0x18000a834  jnz     short loc_18000A80A
0x18000a836  cmp     r11, 7
0x18000a83a  ja      loc_18000A684
0x18000a840  movzx   ecx, word ptr [rdx+2]
0x18000a844  add     rdx, 2
0x18000a848  mov     r14, rdx
0x18000a84b  cmp     cx, 7Eh ; '~'
0x18000a84f  jnz     loc_18000A994
0x18000a855  cmp     word ptr [rdx+2], 5Fh ; '_'
0x18000a85a  jnz     loc_18000A684
0x18000a860  mov     byte ptr [rsp+78h+arg_8], 1
0x18000a868  mov     r15d, 1
0x18000a86e  cmp     r15d, 1Eh
0x18000a872  ja      loc_18000A684
0x18000a878  test    r15d, r15d
0x18000a87b  jz      loc_18000AA08
0x18000a881  mov     edi, r15d
0x18000a884  xor     ebx, ebx
0x18000a886  cmp     rbx, 18h
0x18000a88a  jnb     short loc_18000A8D0
0x18000a88c  mov     r8, rbx
0x18000a88f  add     r8, r8
0x18000a892  mov     r9d, ds:rva dword_18004E190[r10+r8*8]; cchCount2
0x18000a89a  cmp     rdi, r9
0x18000a89d  jnz     short loc_18000A8CB
0x18000a89f  mov     r8, ds:rva off_18004E198[r10+r8*8]; lpString2
0x18000a8a7  mov     edx, r15d; cchCount1
0x18000a8aa  mov     rcx, r14; lpString1
0x18000a8ad  mov     [rsp+78h+bIgnoreCase], 1; bIgnoreCase
0x18000a8b5  call    cs:__imp_CompareStringOrdinal
0x18000a8bb  cmp     eax, 2
0x18000a8be  jz      loc_18000A684
0x18000a8c4  lea     r10, __ImageBase
0x18000a8cb  inc     rbx
0x18000a8ce  jmp     short loc_18000A886
0x18000a8d0  xor     ebx, ebx
0x18000a8d2  cmp     rbx, 17h
0x18000a8d6  jnb     short loc_18000A91C
0x18000a8d8  mov     r8, rbx
0x18000a8db  add     r8, r8
0x18000a8de  mov     edx, ds:rva dword_18004E020[r10+r8*8]; cchCount1
0x18000a8e6  cmp     rdi, rdx
0x18000a8e9  jb      short loc_18000A917
0x18000a8eb  mov     r8, ds:rva off_18004E028[r10+r8*8]; lpString2
0x18000a8f3  mov     r9d, edx; cchCount2
0x18000a8f6  mov     rcx, r14; lpString1
0x18000a8f9  mov     [rsp+78h+bIgnoreCase], 1; bIgnoreCase
0x18000a901  call    cs:__imp_CompareStringOrdinal
0x18000a907  cmp     eax, 2
0x18000a90a  jz      loc_18000A684
0x18000a910  lea     r10, __ImageBase
0x18000a917  inc     rbx
0x18000a91a  jmp     short loc_18000A8D2
0x18000a91c  test    r15d, r15d
0x18000a91f  jz      short loc_18000A92E
0x18000a921  cmp     word ptr [r14+rdi*2-2], 2Eh ; '.'
0x18000a928  jz      loc_18000A684
0x18000a92e  cmp     rdi, 5
0x18000a932  jb      loc_18000AA00
0x18000a938  xor     ebx, ebx
0x18000a93a  add     rdi, 0FFFFFFFFFFFFFFFBh
0x18000a93e  xchg    ax, ax
0x18000a940  cmp     rbx, rdi
0x18000a943  ja      loc_18000AA00
0x18000a949  lea     rcx, [r14+rbx*2]; lpString1
0x18000a94d  mov     [rsp+78h+bIgnoreCase], 1; bIgnoreCase
0x18000a955  mov     r9d, r12d; cchCount2
0x18000a958  lea     r8, String2; ".xn--"
0x18000a95f  mov     edx, r12d; cchCount1
0x18000a962  call    cs:__imp_CompareStringOrdinal
0x18000a968  cmp     eax, 2
0x18000a96b  jz      loc_18000A684
0x18000a971  inc     rbx
0x18000a974  jmp     short loc_18000A940
0x18000a976  cmp     word ptr [rdx], 5Fh ; '_'
0x18000a97a  jz      loc_18000A836
0x18000a980  jmp     loc_18000A684
0x18000a985  cmp     word ptr [rdx], 5Fh ; '_'
0x18000a989  jz      loc_18000A7E7
0x18000a98f  jmp     loc_18000A684
0x18000a994  mov     byte ptr [rsp+78h+arg_8], 0
0x18000a99c  xor     r15d, r15d
0x18000a99f  mov     r9d, 41h ; 'A'
0x18000a9a5  cmp     cx, 5Fh ; '_'
0x18000a9a9  jz      loc_18000A86E
0x18000a9af  test    cx, cx
0x18000a9b2  jz      loc_18000A684
0x18000a9b8  cmp     r15d, 1Eh
0x18000a9bc  jnb     loc_18000A684
0x18000a9c2  lea     eax, [rcx-61h]
0x18000a9c5  cmp     ax, 19h
0x18000a9c9  jbe     short loc_18000A9F3
0x18000a9cb  cmp     r9w, cx
0x18000a9cf  jbe     short loc_18000A9E9
0x18000a9d1  lea     eax, [rcx-2Dh]
0x18000a9d4  cmp     ax, 1
0x18000a9d8  jbe     short loc_18000A9F3
0x18000a9da  sub     cx, 30h ; '0'
0x18000a9de  cmp     cx, 9
0x18000a9e2  jbe     short loc_18000A9F3
0x18000a9e4  jmp     loc_18000A684
0x18000a9e9  cmp     cx, 5Ah ; 'Z'
0x18000a9ed  ja      loc_18000A684
0x18000a9f3  movzx   ecx, word ptr [rdx+2]
0x18000a9f7  add     rdx, 2
0x18000a9fb  inc     r15d
0x18000a9fe  jmp     short loc_18000A9A5
0x18000aa00  mov     r11, [rsp+78h+arg_0]
0x18000aa08  mov     r8, [rsp+78h+arg_10]
0x18000aa10  lea     eax, [r15+rbp]
0x18000aa14  lea     ebp, ds:50h[rax*2]
0x18000aa1b  cmp     [r8], ebp
0x18000aa1e  jb      loc_18000AD79
0x18000aa24  mov     r14, [rsp+78h+arg_18]
0x18000aa2c  lea     rdi, [r14+30h]
0x18000aa30  mov     dword ptr [r14], 0
0x18000aa37  mov     [r14+10h], rdi
0x18000aa3b  movzx   eax, word ptr [rsi]
0x18000aa3e  cmp     ax, 5Fh ; '_'
0x18000aa42  jz      short loc_18000AA64
0x18000aa44  nop     dword ptr [rax+00h]
0x18000aa48  nop     dword ptr [rax+rax+00000000h]
0x18000aa50  add     rsi, 2
0x18000aa54  mov     [rdi], ax
0x18000aa57  add     rdi, 2
0x18000aa5b  movzx   eax, word ptr [rsi]
0x18000aa5e  cmp     ax, 5Fh ; '_'
0x18000aa62  jnz     short loc_18000AA50
0x18000aa64  xor     eax, eax
0x18000aa66  add     rsi, 2
0x18000aa6a  mov     [rdi], ax
0x18000aa6d  xor     ecx, ecx
0x18000aa6f  mov     rdx, rsi
0x18000aa72  movzx   r8d, word ptr [rdx]
0x18000aa76  cmp     r8d, 2Eh ; '.'
0x18000aa7a  jz      short loc_18000AAAE
0x18000aa7c  mov     rax, rdx
0x18000aa7f  sub     rax, rsi
0x18000aa82  and     rax, 0FFFFFFFFFFFFFFFEh
0x18000aa86  cmp     rax, 0Ah
0x18000aa8a  jge     loc_18000A684
0x18000aa90  lea     eax, [r8-30h]
0x18000aa94  cmp     ax, 9
0x18000aa98  ja      loc_18000A684
  ... truncated ...
```
