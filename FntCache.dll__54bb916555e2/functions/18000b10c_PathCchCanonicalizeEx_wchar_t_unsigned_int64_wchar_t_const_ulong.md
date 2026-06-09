# PathCchCanonicalizeEx(wchar_t *,unsigned __int64,wchar_t const *,ulong)

- ea: `0x18000b10c`
- end: `0x18000b992`
- name: `?PathCchCanonicalizeEx@@YAJPEA_W_KPEB_WK@Z`
- size: `2182`
- prototype: `__int64 __fastcall(wchar_t *, unsigned __int64, const wchar_t *, unsigned int)`
- caller_count: `1`
- callee_count: `8`
- tags: `reparse_path`

## callers

- `0x18000adf8`

## callees

- `0x18000b10c`
- `0x18008d1c0`
- `0x18008e034`
- `0x180093504`
- `0x1800aee18`
- `0x1800aeec4`
- `0x1800b93e8`
- `0x1800b9778`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_iswalpha` at `0x18000b22f`
- `api-ms-win-crt-private-l1-1-0!_o_iswalpha` at `0x18000b788`
- `api-ms-win-crt-private-l1-1-0!_o_iswalpha` at `0x18000b22f`
- `api-ms-win-crt-private-l1-1-0!_o_iswalpha` at `0x18000b788`
- `api-ms-win-crt-private-l1-1-0!wcschr` at `0x18000b35d`
- `api-ms-win-crt-private-l1-1-0!wcschr` at `0x18000b35d`

## pseudocode

```c
__int64 __fastcall PathCchCanonicalizeEx(wchar_t *a1, size_t a2, const wchar_t *a3)
{
  unsigned __int64 v4; // rdi
  size_t v6; // rdx
  wchar_t *v7; // rcx
  size_t *v8; // r8
  wchar_t v9; // r11
  HRESULT v10; // r14d
  const wchar_t *v11; // r11
  int v13; // esi
  unsigned __int64 v14; // r12
  int v15; // r10d
  const wchar_t *v16; // r9
  const wchar_t *v17; // r15
  wchar_t *v18; // rsi
  const wchar_t *v19; // r8
  int v20; // ecx
  __int64 v21; // rdx
  int v22; // eax
  int v23; // eax
  size_t v24; // r8
  __int64 v25; // r11
  int v26; // eax
  const wchar_t *v27; // rcx
  const wchar_t *v28; // r10
  __int64 v29; // r9
  __int64 v30; // rcx
  size_t v31; // r8
  wchar_t *v32; // rax
  __int64 v33; // rdx
  wchar_t *v34; // rcx
  size_t v35; // rdx
  size_t *v36; // r8
  HRESULT v37; // eax
  wchar_t *v38; // rax
  wchar_t *v39; // r13
  unsigned __int64 v40; // rdx
  unsigned __int64 v41; // rax
  const wchar_t *v42; // rcx
  unsigned __int64 v43; // r8
  wchar_t *v44; // r9
  __int64 v45; // r10
  wchar_t *v46; // rcx
  int v47; // eax
  unsigned __int64 v48; // rdx
  __int64 v49; // rax
  wchar_t *v50; // rcx
  wchar_t *v51; // rsi
  wchar_t *v52; // rcx
  wchar_t *v53; // rax
  wchar_t *v54; // r10
  int v55; // r11d
  wchar_t *v56; // r8
  const wchar_t *v57; // r9
  int v58; // ecx
  int v59; // edx
  bool v60; // zf
  int IsVolumeGUIDWorker; // eax
  __int64 v62; // rdx
  BOOL v63; // ecx
  HRESULT v64; // eax
  int v65; // eax
  int IsRoot; // eax
  wchar_t v67; // ax
  const wchar_t *v68; // r8
  unsigned __int64 v69; // rdx
  wchar_t *v70; // rcx
  unsigned __int64 *v71; // [rsp+20h] [rbp-40h]
  unsigned __int64 *v72; // [rsp+20h] [rbp-40h]
  unsigned int v73; // [rsp+28h] [rbp-38h]
  int v74; // [rsp+30h] [rbp-30h]
  int v75; // [rsp+34h] [rbp-2Ch]
  wchar_t *v76; // [rsp+38h] [rbp-28h] BYREF
  int v77; // [rsp+40h] [rbp-20h]
  STRSAFE_PCNZWCH pszDest; // [rsp+48h] [rbp-18h]
  unsigned __int64 v79[2]; // [rsp+50h] [rbp-10h] BYREF
  int v81; // [rsp+B8h] [rbp+58h]

  v76 = 0;
  v4 = a2;
  v10 = StringValidateDestW(a1, a2, (const size_t)a3);
  if ( v10 < 0 )
  {
    if ( v4 )
      *v7 = v9;
    return (unsigned int)v10;
  }
  v10 = StringCopyWorkerW(v7, v6, v8, &pszSrc, (size_t)v71);
  if ( v10 < 0 )
    return (unsigned int)v10;
  if ( v4 > 0x8000 )
    return 2147942487LL;
  pszDest = v11;
  if ( v4 > 0x104 )
  {
    v81 = 1;
    v13 = 1;
    v74 = 1;
  }
  else
  {
    v13 = (int)v11;
    v81 = (int)v11;
    v74 = (int)v11;
  }
  v77 = v13;
  v14 = v4;
  v79[0] = v4;
  v75 = (int)v11;
  if ( *a3 == 92 && a3[1] == 92 )
  {
    if ( a3[2] == 63 )
    {
      if ( (unsigned int)StrIsEqualWorker(a3 + 3, L"\\UNC\\", 5) )
      {
        v62 = 8;
        v63 = 1;
        goto LABEL_117;
      }
    }
    else
    {
      IsVolumeGUIDWorker = PathIsVolumeGUIDWorker(a3);
      LODWORD(v11) = 0;
      v62 = IsVolumeGUIDWorker == 0 ? 2 : 0;
      v63 = IsVolumeGUIDWorker == 0;
      v75 = v63;
      if ( !IsVolumeGUIDWorker )
      {
LABEL_117:
        v75 = v63;
        v17 = &a3[v62];
        if ( v13 )
        {
          pszDest = (STRSAFE_PCNZWCH)6;
          v64 = StringCchCopyExW(a1, v4, L"\\\\?\\UNC\\", &v76, v79, v73);
        }
        else
        {
          v64 = StringCchCopyExW(a1, v4, L"\\\\", &v76, v79, v73);
        }
        v27 = pszDest;
        LODWORD(v25) = 0;
        v14 = v79[0];
        v60 = v13 == 0;
        v18 = v76;
        v10 = v64;
        if ( v60 || !pszDest )
          goto LABEL_36;
        goto LABEL_30;
      }
    }
  }
  v15 = 4;
  v16 = L"\\\\?\\";
  v17 = a3;
  v18 = a1;
  v19 = a3;
  do
  {
    v20 = *v19;
    if ( (unsigned int)(v20 - 65) <= 0x19 )
      v20 += 32;
    v21 = *v16;
    if ( (unsigned int)(v21 - 65) <= 0x19 )
      v21 = (unsigned int)(v21 + 32);
    if ( !--v15 )
      break;
    if ( !v20 )
      break;
    ++v19;
    ++v16;
  }
  while ( v20 == (_DWORD)v21 );
  v22 = (int)v11;
  LOBYTE(v22) = v20 == (_DWORD)v21;
  LODWORD(v76) = v22;
  if ( v20 != (_DWORD)v21 )
  {
    v23 = _o_iswalpha(*a3, v21, v19, v16);
    LODWORD(v25) = 0;
    if ( v23 )
    {
      v26 = (int)v76;
      if ( a3[1] == 58 )
        v26 = 1;
      goto LABEL_20;
    }
    goto LABEL_123;
  }
  v65 = _o_iswalpha(a3[4], v21, v19, v16);
  LODWORD(v25) = 0;
  if ( v65 && a3[5] == 58 )
  {
    v17 = a3 + 4;
LABEL_123:
    v26 = (int)v76;
    goto LABEL_20;
  }
  v26 = 0;
LABEL_20:
  v4 = a2;
  if ( !v77 || !v26 )
    goto LABEL_36;
  v27 = (const wchar_t *)4;
  pszDest = (STRSAFE_PCNZWCH)4;
  if ( a2 )
  {
    v28 = L"\\\\?\\";
    v29 = 0;
    v30 = 2147483646;
    v31 = a2;
    LODWORD(v25) = 0;
    v32 = a1;
    do
    {
      if ( !v30 )
        break;
      if ( !*v28 )
        break;
      *v32++ = *v28++;
      --v30;
      ++v29;
      --v31;
    }
    while ( v31 );
    v33 = v29 - 1;
    v34 = v32 - 1;
    if ( v31 )
    {
      v34 = v32;
      v33 = v29;
    }
    v24 = -(__int64)v31;
    *v34 = 0;
    v27 = pszDest;
    v18 = &a1[v33];
    v10 = v24 == 0 ? 0x8007007A : 0;
    v14 = a2 - v33;
  }
  else
  {
    v10 = -2147024809;
  }
LABEL_30:
  if ( v4 <= (unsigned __int64)(v27 + 130) )
  {
    pszDest = 0;
    v17 = a3;
    v18 = a1;
    if ( v4 > 0x104 )
      v4 = 260;
    v14 = v4;
    v10 = StringValidateDestW(v27, v4, v24);
    if ( v10 >= 0 )
    {
      v37 = StringCopyWorkerW(a1, v35, v36, &pszSrc, (size_t)v72);
      goto LABEL_35;
    }
    if ( v4 )
      *a1 = v25;
  }
LABEL_36:
  while ( v10 >= 0 )
  {
    if ( *v17 == (_WORD)v25 )
      goto LABEL_79;
    v38 = wcschr(v17, 0x5Cu);
    v25 = 0;
    v39 = v38;
    if ( v38 )
    {
      v40 = v38 - v17;
    }
    else
    {
      v40 = -1;
      do
        ++v40;
      while ( v17[v40] );
    }
    if ( v40 > 0x100 && !v81 || v40 >= 0x8000 )
    {
      v10 = -2147024690;
      break;
    }
    if ( v40 == 1 )
    {
      if ( *v17 != 46 )
        goto LABEL_47;
      if ( v38 )
      {
        v17 = v38 + 1;
      }
      else
      {
        ++v17;
        if ( v18 > a1 )
        {
          IsRoot = PathCchIsRoot(a1);
          LODWORD(v25) = 0;
          if ( !IsRoot )
          {
            v37 = StringCchCopyW(--v18, ++v14, &pszSrc);
LABEL_35:
            v10 = v37;
          }
        }
      }
    }
    else if ( v40 == 2 )
    {
      if ( *v17 != 46 || v17[1] != 46 )
        goto LABEL_47;
      if ( v18 <= a1 || (v47 = PathCchIsRoot(a1), LODWORD(v25) = 0, v47) )
      {
        if ( !v39 )
          goto LABEL_135;
        v17 = v39 + 1;
      }
      else
      {
        --v18;
        while ( a1 < v18 )
        {
          if ( *--v18 == 92 )
          {
            if ( v18 )
            {
              v14 = v4 - (v18 - a1);
              goto LABEL_134;
            }
            break;
          }
        }
        v18 = a1;
        v14 = v4;
LABEL_134:
        v10 = StringCchCopyW(v18, v14, &pszSrc);
LABEL_135:
        v17 += 2;
      }
    }
    else
    {
      if ( !v40 )
        v40 = *v17 == 92;
LABEL_47:
      if ( v14 )
      {
        if ( v14 > 0x7FFFFFFF )
        {
          *v18 = 0;
          v10 = -2147024809;
          goto LABEL_60;
        }
        v41 = v40;
        v42 = v17;
        v43 = v14;
        v44 = v18;
        do
        {
          if ( !v41 )
            break;
          if ( !*v42 )
            break;
          *v44++ = *v42++;
          --v41;
          ++v25;
          --v43;
        }
        while ( v43 );
        v45 = v25 - 1;
        v46 = v44 - 1;
        if ( v43 )
          v45 = v25;
        LODWORD(v25) = 0;
        v10 = v43 == 0 ? 0x8007007A : 0;
        if ( v43 )
          v46 = v44;
        *v46 = 0;
        if ( (int)(v10 + 0x80000000) < 0 || v10 == -2147024774 )
        {
          v18 += v45;
          v14 -= v45;
        }
      }
      else
      {
        v10 = -2147024809;
      }
      if ( v10 == -2147024774 && v40 == 1 && *v17 == 92 )
      {
        v67 = v17[1];
        if ( !v67 || v67 == 46 && !v17[2] )
        {
LABEL_79:
          if ( v18 > a1 )
          {
            v51 = v18 - 1;
            v52 = v51;
            v53 = v51;
            while ( *v51 == 46 )
            {
              if ( v52 == a1 )
              {
                *v51 = v25;
                break;
              }
              v52 = v53 - 1;
              if ( *(v53 - 1) == 42 )
                break;
              *v51 = v25;
              --v53;
              v51 = v52;
            }
          }
          v48 = -1;
          v49 = -1;
          do
            ++v49;
          while ( a1[v49] != (_WORD)v25 );
          v50 = &a1[v49];
          if ( v50 >= a1 + 7 )
          {
            v54 = v50 - 7;
            v55 = 7;
            v56 = v50 - 7;
            v57 = L"::$DATA";
            do
            {
              v58 = *v56;
              if ( (unsigned int)(v58 - 65) <= 0x19 )
                v58 += 32;
              v59 = *v57;
              if ( (unsigned int)(v59 - 65) <= 0x19 )
                v59 += 32;
              if ( !--v55 )
                break;
              if ( !v58 )
                break;
              ++v56;
              ++v57;
            }
            while ( v58 == v59 );
            if ( v58 == v59 )
            {
              LODWORD(v25) = 0;
              *v54 = 0;
              v48 = -1;
            }
            else
            {
              v48 = -1;
              LODWORD(v25) = 0;
            }
          }
          if ( pszDest )
          {
            do
              ++v48;
            while ( a1[(_QWORD)pszDest + v48] != (_WORD)v25 );
            if ( v48 < 0x104 )
            {
              if ( v75 == (_DWORD)v25 )
              {
                v68 = a1 + 4;
                v69 = v4;
                v70 = a1;
              }
              else
              {
                v68 = a1 + 8;
                v69 = v4 - 2;
                v70 = a1 + 2;
              }
              StringCchCopyW(v70, v69, v68);
            }
          }
          if ( v4 > 1 && *a1 == (_WORD)v25 )
            *(_DWORD *)a1 = 92;
          if ( v4 > 3 && a1[1] == 58 && a1[2] == (_WORD)v25 )
            *((_DWORD *)a1 + 1) = 92;
          return 0;
        }
        if ( v14 == 1 && v67 == 46 && v17[2] == 46 )
        {
          *v18 = 0;
          v14 = 0;
          ++v18;
          v10 = 0;
        }
      }
LABEL_60:
      v17 += v40;
    }
  }
  StringCchCopyW(a1, v4, &pszSrc);
  if ( v10 != -2147024774 )
    return (unsigned int)v10;
  if ( v74 )
  {
    if ( v4 != 0x8000 )
      return (unsigned int)v10;
  }
  else if ( v4 != 260 )
  {
    return (unsigned int)v10;
  }
  return (unsigned int)-2147024690;
}

```

## disassembly

```asm
0x18000b10c  mov     [rsp-38h+arg_0], rbx
0x18000b111  mov     [rsp-38h+arg_18], r9d
0x18000b116  mov     [rsp-38h+arg_8], rdx
0x18000b11b  push    rbp
0x18000b11c  push    rsi
0x18000b11d  push    rdi
0x18000b11e  push    r12
0x18000b120  push    r13
0x18000b122  push    r14
0x18000b124  push    r15
0x18000b126  mov     rbp, rsp
0x18000b129  sub     rsp, 60h
0x18000b12d  xor     r11d, r11d
0x18000b130  mov     r13, r8
0x18000b133  mov     [rbp+var_28], r11
0x18000b137  mov     rdi, rdx
0x18000b13a  mov     rbx, rcx
0x18000b13d  call    StringValidateDestW
0x18000b142  mov     r14d, eax
0x18000b145  test    eax, eax
0x18000b147  js      loc_18000B980
0x18000b14d  lea     r9, pszSrc; pszSrc
0x18000b154  call    StringCopyWorkerW
0x18000b159  mov     r14d, eax
0x18000b15c  test    eax, eax
0x18000b15e  js      loc_18000B4F1
0x18000b164  cmp     rdi, 8000h
0x18000b16b  jbe     short loc_18000B18A
0x18000b16d  mov     eax, 80070057h
0x18000b172  mov     rbx, [rsp+60h+arg_0]
0x18000b17a  add     rsp, 60h
0x18000b17e  pop     r15
0x18000b180  pop     r14
0x18000b182  pop     r13
0x18000b184  pop     r12
0x18000b186  pop     rdi
0x18000b187  pop     rsi
0x18000b188  pop     rbp
0x18000b189  retn
0x18000b18a  mov     [rbp+pszDest], r11
0x18000b18e  mov     r15d, 1
0x18000b194  cmp     rdi, 104h
0x18000b19b  ja      loc_18000B563
0x18000b1a1  mov     esi, r11d
0x18000b1a4  mov     [rbp+arg_18], r11d
0x18000b1a8  mov     [rbp+var_30], r11d
0x18000b1ac  mov     eax, 5Ch ; '\'
0x18000b1b1  mov     [rbp+var_20], esi
0x18000b1b4  mov     r12, rdi
0x18000b1b7  mov     [rbp+var_10], rdi
0x18000b1bb  mov     [rbp+var_2C], r11d
0x18000b1bf  cmp     [r13+0], ax
0x18000b1c4  jz      loc_18000B6CA
0x18000b1ca  mov     r10d, 4
0x18000b1d0  lea     r9, asc_1800EAEB8; "\\\\?\\"
0x18000b1d7  mov     r15, r13
0x18000b1da  mov     rsi, rbx
0x18000b1dd  mov     r8, r13
0x18000b1e0  lea     edi, [r10-3]
0x18000b1e4  movzx   ecx, word ptr [r8]
0x18000b1e8  lea     eax, [rcx-41h]
0x18000b1eb  cmp     eax, 19h
0x18000b1ee  jbe     loc_18000B573
0x18000b1f4  movzx   edx, word ptr [r9]
0x18000b1f8  lea     eax, [rdx-41h]
0x18000b1fb  cmp     eax, 19h
0x18000b1fe  jbe     loc_18000B77B
0x18000b204  sub     r10d, edi
0x18000b207  jz      short loc_18000B219
0x18000b209  test    ecx, ecx
0x18000b20b  jz      short loc_18000B219
0x18000b20d  add     r8, 2
0x18000b211  add     r9, 2
0x18000b215  cmp     ecx, edx
0x18000b217  jz      short loc_18000B1E4
0x18000b219  mov     eax, r11d
0x18000b21c  cmp     ecx, edx
0x18000b21e  setz    al
0x18000b221  mov     dword ptr [rbp+var_28], eax
0x18000b224  jz      loc_18000B783
0x18000b22a  movzx   ecx, word ptr [r13+0]
0x18000b22f  call    cs:__imp__o_iswalpha
0x18000b235  xor     r11d, r11d
0x18000b238  test    eax, eax
0x18000b23a  jz      loc_18000B7A1
0x18000b240  cmp     word ptr [r13+2], 3Ah ; ':'
0x18000b246  mov     eax, dword ptr [rbp+var_28]
0x18000b249  cmovz   eax, edi
0x18000b24c  mov     rdi, [rbp+arg_8]
0x18000b250  cmp     [rbp+var_20], r11d
0x18000b254  jz      loc_18000B342
0x18000b25a  test    eax, eax
0x18000b25c  jz      loc_18000B342
0x18000b262  mov     ecx, 4
0x18000b267  mov     [rbp+pszDest], rcx
0x18000b26b  test    rdi, rdi
0x18000b26e  jz      loc_18000B7B1
0x18000b274  mov     edx, [rbp+var_30]
0x18000b277  lea     r10, asc_1800EAEB8; "\\\\?\\"
0x18000b27e  mov     r9, r11
0x18000b281  mov     [rbp+var_30], edx
0x18000b284  mov     r11d, [rbp+arg_18]
0x18000b288  mov     ecx, 7FFFFFFEh
0x18000b28d  mov     [rbp+arg_18], r11d
0x18000b291  mov     r8, rdi
0x18000b294  xor     r11d, r11d
0x18000b297  mov     rax, rbx
0x18000b29a  test    rcx, rcx
0x18000b29d  jz      short loc_18000B2C3
0x18000b29f  movzx   edx, word ptr [r10]
0x18000b2a3  test    dx, dx
0x18000b2a6  jz      short loc_18000B2C3
0x18000b2a8  mov     [rax], dx
0x18000b2ab  add     r10, 2
0x18000b2af  mov     edx, 1
0x18000b2b4  add     rax, 2
0x18000b2b8  sub     rcx, rdx
0x18000b2bb  add     r9, rdx
0x18000b2be  sub     r8, rdx
0x18000b2c1  jnz     short loc_18000B29A
0x18000b2c3  test    r8, r8
0x18000b2c6  lea     rdx, [r9-1]
0x18000b2ca  lea     rcx, [rax-2]
0x18000b2ce  mov     r12, rdi
0x18000b2d1  cmovnz  rcx, rax
0x18000b2d5  cmovnz  rdx, r9
0x18000b2d9  neg     r8; cchMax
0x18000b2dc  sbb     r14d, r14d
0x18000b2df  not     r14d
0x18000b2e2  mov     [rcx], r11w
0x18000b2e6  mov     rcx, [rbp+pszDest]; pszDest
0x18000b2ea  lea     rsi, [rbx+rdx*2]
0x18000b2ee  and     r14d, 8007007Ah
0x18000b2f5  sub     r12, rdx
0x18000b2f8  lea     rax, [rcx+104h]
0x18000b2ff  cmp     rdi, rax
0x18000b302  ja      short loc_18000B342
0x18000b304  mov     eax, 104h
0x18000b309  mov     [rbp+pszDest], r11
0x18000b30d  cmp     rdi, rax
0x18000b310  mov     r15, r13
0x18000b313  mov     rsi, rbx
0x18000b316  cmova   rdi, rax
0x18000b31a  mov     rdx, rdi; cchDest
0x18000b31d  mov     r12, rdi
0x18000b320  call    StringValidateDestW
0x18000b325  mov     r14d, eax
0x18000b328  test    eax, eax
0x18000b32a  js      loc_18000B7C8
0x18000b330  lea     r9, pszSrc; pszSrc
0x18000b337  mov     rcx, rbx; pszDest
0x18000b33a  call    StringCopyWorkerW
0x18000b33f  mov     r14d, eax
0x18000b342  test    r14d, r14d
0x18000b345  js      loc_18000B4D2
0x18000b34b  cmp     [r15], r11w
0x18000b34f  jz      loc_18000B57B
0x18000b355  mov     edx, 5Ch ; '\'; Ch
0x18000b35a  mov     rcx, r15; Str
0x18000b35d  call    cs:__imp_wcschr
0x18000b363  xor     r11d, r11d
0x18000b366  mov     r13, rax
0x18000b369  test    rax, rax
0x18000b36c  jnz     loc_18000B486
0x18000b372  or      rdx, 0FFFFFFFFFFFFFFFFh
0x18000b376  inc     rdx
0x18000b379  cmp     [r15+rdx*2], r11w
0x18000b37e  jnz     short loc_18000B376
0x18000b380  cmp     rdx, 100h
0x18000b387  ja      loc_18000B7DA
0x18000b38d  cmp     rdx, 8000h
0x18000b394  jnb     loc_18000B4CC
0x18000b39a  mov     ecx, 1
0x18000b39f  cmp     rdx, rcx
0x18000b3a2  jz      loc_18000B4AF
0x18000b3a8  cmp     rdx, 2
0x18000b3ac  jz      loc_18000B4F9
0x18000b3b2  test    rdx, rdx
0x18000b3b5  jz      loc_18000B49D
0x18000b3bb  mov     r10d, [rbp+var_30]
0x18000b3bf  mov     r13d, [rbp+arg_18]
0x18000b3c3  mov     [rbp+var_30], r10d
0x18000b3c7  mov     [rbp+arg_18], r13d
0x18000b3cb  test    r12, r12
0x18000b3ce  jz      loc_18000B870
0x18000b3d4  mov     eax, 7FFFFFFFh
0x18000b3d9  cmp     r12, rax
0x18000b3dc  ja      loc_18000B859
0x18000b3e2  cmp     rdx, rax
0x18000b3e5  jnb     loc_18000B861
0x18000b3eb  mov     rax, rdx
0x18000b3ee  mov     [rbp+arg_18], r13d
0x18000b3f2  mov     rcx, r15
0x18000b3f5  mov     [rbp+var_30], r10d
0x18000b3f9  mov     r8, r12
0x18000b3fc  mov     r9, rsi
0x18000b3ff  test    rax, rax
0x18000b402  jz      short loc_18000B42B
0x18000b404  movzx   r10d, word ptr [rcx]
0x18000b408  test    r10w, r10w
0x18000b40c  jz      short loc_18000B42B
0x18000b40e  mov     [r9], r10w
0x18000b412  add     rcx, 2
0x18000b416  mov     r10d, 1
0x18000b41c  add     r9, 2
0x18000b420  sub     rax, r10
0x18000b423  add     r11, r10
0x18000b426  sub     r8, r10
0x18000b429  jnz     short loc_18000B3FF
0x18000b42b  test    r8, r8
0x18000b42e  lea     r10, [r11-1]
0x18000b432  mov     rax, r8
0x18000b435  lea     rcx, [r9-2]
0x18000b439  cmovnz  r10, r11
0x18000b43d  mov     r13d, 8007007Ah
0x18000b443  neg     rax
0x18000b446  sbb     r14d, r14d
0x18000b449  xor     r11d, r11d
0x18000b44c  not     r14d
0x18000b44f  and     r14d, r13d
0x18000b452  test    r8, r8
0x18000b455  cmovnz  rcx, r9
0x18000b459  mov     [rcx], r11w
0x18000b45d  mov     ecx, 80000000h
0x18000b462  lea     eax, [r14+rcx]
0x18000b466  test    ecx, eax
0x18000b468  jnz     short loc_18000B494
0x18000b46a  cmp     r14d, r13d
0x18000b46d  jz      short loc_18000B494
0x18000b46f  mov     ecx, 1
0x18000b474  cmp     r14d, r13d
0x18000b477  jz      loc_18000B887
0x18000b47d  lea     r15, [r15+rdx*2]
0x18000b481  jmp     loc_18000B342
0x18000b486  mov     rdx, r13
0x18000b489  sub     rdx, r15
0x18000b48c  sar     rdx, 1
0x18000b48f  jmp     loc_18000B380
0x18000b494  lea     rsi, [rsi+r10*2]
0x18000b498  sub     r12, r10
0x18000b49b  jmp     short loc_18000B46F
0x18000b49d  mov     eax, 5Ch ; '\'
0x18000b4a2  cmp     [r15], ax
0x18000b4a6  cmovz   rdx, rcx
0x18000b4aa  jmp     loc_18000B3BB
0x18000b4af  cmp     word ptr [r15], 2Eh ; '.'
0x18000b4b4  jnz     loc_18000B3BB
0x18000b4ba  test    r13, r13
0x18000b4bd  jz      loc_18000B7E9
0x18000b4c3  lea     r15, [rax+2]
0x18000b4c7  jmp     loc_18000B342
0x18000b4cc  mov     r14d, 800700CEh
0x18000b4d2  lea     r8, pszSrc; wchar_t *
0x18000b4d9  mov     rdx, rdi; unsigned __int64
0x18000b4dc  mov     rcx, rbx; wchar_t *
0x18000b4df  call    ?StringCchCopyW@@YAJPEA_W_KPEB_W@Z; StringCchCopyW(wchar_t *,unsigned __int64,wchar_t const *)
0x18000b4e4  cmp     r14d, 8007007Ah
0x18000b4eb  jz      loc_18000B954
0x18000b4f1  mov     eax, r14d
0x18000b4f4  jmp     loc_18000B172
0x18000b4f9  cmp     word ptr [r15], 2Eh ; '.'
0x18000b4fe  jnz     loc_18000B3BB
0x18000b504  cmp     word ptr [r15+2], 2Eh ; '.'
0x18000b50a  jnz     loc_18000B3BB
0x18000b510  cmp     rsi, rbx
0x18000b513  jbe     loc_18000B84B
0x18000b519  mov     rcx, rbx; wchar_t *
0x18000b51c  call    ?PathCchIsRoot@@YAHPEB_W@Z; PathCchIsRoot(wchar_t const *)
0x18000b521  xor     r11d, r11d
0x18000b524  test    eax, eax
0x18000b526  jnz     loc_18000B84B
0x18000b52c  add     rsi, 0FFFFFFFFFFFFFFFEh
0x18000b530  lea     eax, [r11+5Ch]
0x18000b534  cmp     rbx, rsi
0x18000b537  jnb     loc_18000B827
0x18000b53d  sub     rsi, 2
0x18000b541  cmp     [rsi], ax
0x18000b544  jnz     short loc_18000B534
0x18000b546  test    rsi, rsi
0x18000b549  jz      loc_18000B827
0x18000b54f  mov     rax, rsi
0x18000b552  mov     r12, rdi
0x18000b555  sub     rax, rbx
0x18000b558  sar     rax, 1
0x18000b55b  sub     r12, rax
0x18000b55e  jmp     loc_18000B82D
0x18000b563  mov     [rbp+arg_18], r15d
0x18000b567  mov     esi, r15d
0x18000b56a  mov     [rbp+var_30], r15d
0x18000b56e  jmp     loc_18000B1AC
0x18000b573  add     ecx, 20h ; ' '
0x18000b576  jmp     loc_18000B1F4
0x18000b57b  cmp     rsi, rbx
0x18000b57e  ja      short loc_18000B5C6
0x18000b580  or      rdx, 0FFFFFFFFFFFFFFFFh
0x18000b584  mov     rax, rdx
0x18000b587  inc     rax
0x18000b58a  cmp     [rbx+rax*2], r11w
0x18000b58f  jnz     short loc_18000B587
0x18000b591  lea     rcx, [rbx+rax*2]
  ... truncated ...
```
