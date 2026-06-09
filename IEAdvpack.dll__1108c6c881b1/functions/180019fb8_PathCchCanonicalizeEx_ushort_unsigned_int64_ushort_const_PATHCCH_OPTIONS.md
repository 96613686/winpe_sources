# PathCchCanonicalizeEx(ushort *,unsigned __int64,ushort const *,PATHCCH_OPTIONS)

- ea: `0x180019fb8`
- end: `0x18001a680`
- name: `?PathCchCanonicalizeEx@@YAJPEAG_KPEBGW4PATHCCH_OPTIONS@@@Z`
- size: `1736`
- prototype: `int __fastcall(STRSAFE_LPWSTR pszDest, unsigned __int64, unsigned __int16 *, enum PATHCCH_OPTIONS)`
- caller_count: `1`
- callee_count: `11`
- tags: `reparse_path`

## callers

- `0x18001b294`

## callees

- `0x1800022bc`
- `0x180003218`
- `0x1800033a8`
- `0x180018bcc`
- `0x1800198d0`
- `0x180019e84`
- `0x180019fb8`
- `0x18001a688`
- `0x18001ac8c`
- `0x18001b524`
- `0x18001c010`

## import_xrefs

- `msvcrt!wcspbrk` at `0x18001a254`
- `msvcrt!wcspbrk` at `0x18001a254`
- `msvcrt!iswalpha` at `0x18001a132`
- `msvcrt!iswalpha` at `0x18001a1cb`
- `msvcrt!iswalpha` at `0x18001a132`
- `msvcrt!iswalpha` at `0x18001a1cb`

## pseudocode

```c
int __fastcall PathCchCanonicalizeEx(
        STRSAFE_LPWSTR pszDest,
        unsigned __int64 a2,
        unsigned __int16 *a3,
        enum PATHCCH_OPTIONS a4)
{
  int result; // eax
  int v8; // r12d
  PATHCCH_OPTIONS v9; // ecx
  unsigned __int64 v10; // rsi
  unsigned __int64 v11; // r13
  char v12; // cl
  __int64 (__fastcall *v13)(); // rax
  wchar_t *v14; // rdx
  const unsigned __int16 *v15; // r14
  bool v16; // bl
  const unsigned __int16 *v17; // r8
  int v18; // eax
  bool v19; // cf
  STRSAFE_LPWSTR v20; // rbx
  __int64 v21; // r11
  wint_t v22; // cx
  bool v23; // al
  __int16 v24; // r11
  wint_t v25; // cx
  int v26; // eax
  unsigned __int64 i; // r15
  wchar_t *v28; // rax
  BOOL IsRoot; // eax
  BOOL v30; // eax
  int v31; // eax
  __int64 (__fastcall *v32)(); // r13
  const unsigned __int16 *j; // rbx
  char v34; // al
  char v35; // al
  unsigned __int16 v36; // ax
  unsigned __int16 *v37; // rbx
  char v38; // r14
  int v39; // eax
  STRSAFE_LPWSTR v40; // rbx
  wchar_t *v41; // rcx
  STRSAFE_LPWSTR v42; // rax
  __int64 v43; // rax
  wchar_t *v44; // rbx
  const unsigned __int16 *v45; // r8
  unsigned __int64 v46; // rdx
  unsigned __int16 *v47; // rcx
  unsigned __int16 *v48; // [rsp+40h] [rbp-49h] BYREF
  bool v49; // [rsp+48h] [rbp-41h]
  unsigned __int64 v50; // [rsp+50h] [rbp-39h] BYREF
  PATHCCH_OPTIONS v51; // [rsp+58h] [rbp-31h]
  __int64 v52; // [rsp+60h] [rbp-29h]
  enum PATHCCH_OPTIONS v53; // [rsp+68h] [rbp-21h] BYREF
  __int64 (__fastcall *v54)(); // [rsp+70h] [rbp-19h]
  const unsigned __int16 *v55; // [rsp+78h] [rbp-11h]
  int v56; // [rsp+80h] [rbp-9h]
  __int32 v57; // [rsp+84h] [rbp-5h]
  int IsUnc2; // [rsp+88h] [rbp-1h]
  wchar_t *Control; // [rsp+90h] [rbp+7h]
  wchar_t *v60; // [rsp+98h] [rbp+Fh]
  char v61; // [rsp+108h] [rbp+7Fh]

  v53 = PATHCCH_NONE;
  result = StringCchCopyW(pszDest, a2, &word_18001DE6C);
  v8 = result;
  if ( result < 0 )
    return result;
  if ( a2 > 0x8000 || !AreOptionsValidAndOptInLongPathAwareProcess(&v53) )
    return -2147024809;
  v9 = v53;
  if ( a2 <= 0x104 )
    v9 = v53 & 0xFFFFFFF8;
  v51 = v9;
  v48 = 0;
  v56 = v9 & 0x11;
  v10 = v56 != 0 ? 0x8000LL : 260LL;
  if ( a2 < v10 )
    v10 = a2;
  v50 = v10;
  v11 = v10;
  if ( (v9 & 0x40) != 0 )
  {
    v12 = 1;
    v13 = IsBackOrForwardSlash;
  }
  else
  {
    v12 = 0;
    v13 = IsBackslash;
  }
  v61 = v12;
  v54 = v13;
  v14 = L"\\/";
  v55 = 0;
  if ( !v12 )
    v14 = (wchar_t *)L"\\";
  Control = v14;
  IsUnc2 = PathIsUnc2(a3);
  if ( IsUnc2 )
  {
    v15 = v55;
    v16 = MayNeedExtendedLengthPrefix(v51);
    v17 = L"\\\\?\\UNC\\";
    if ( !v16 )
      v17 = L"\\\\";
    v18 = StringCchCopyExW(pszDest, v10, v17, &v48, &v50, 0);
    v11 = v50;
    v19 = v16;
    v20 = v48;
    v8 = v18;
    v21 = v19 ? 6 : 0;
    v52 = (unsigned int)v21;
    goto LABEL_24;
  }
  v20 = pszDest;
  v52 = 0;
  v48 = pszDest;
  v15 = a3;
  v49 = IsExtendedLengthDosDevicePath(a3);
  if ( v49 )
  {
    v22 = a3[4];
    v55 = a3 + 4;
    if ( iswalpha(v22) && a3[5] == 58 )
    {
      v23 = v49;
      v15 = a3 + 4;
    }
    else
    {
      v23 = 0;
    }
    if ( !v23 )
      goto LABEL_23;
  }
  else
  {
    v25 = *a3;
    v55 = a3;
    if ( !iswalpha(v25) || a3[1] != 58 )
      goto LABEL_23;
  }
  if ( MayNeedExtendedLengthPrefix(v51) )
  {
    v52 = 4;
    v26 = StringCchCopyExW(pszDest, v10, L"\\\\?\\", &v48, &v50, 0);
    v11 = v50;
    v8 = v26;
    v20 = v48;
    v21 = 4;
    goto LABEL_24;
  }
LABEL_23:
  v21 = v52;
LABEL_24:
  v57 = v51 & 5;
  if ( v57 == 5 && v21 && v10 <= v21 + 260 )
  {
    v20 = pszDest;
    v48 = pszDest;
    if ( v10 > 0x104 )
      v10 = 260;
    v15 = a3;
    v50 = v10;
    v52 = 0;
    v11 = v10;
    v8 = StringCchCopyW(pszDest, v10, &word_18001DE6C);
  }
  else
  {
    v24 = 0;
  }
  while ( 2 )
  {
    while ( 1 )
    {
      for ( i = -1; ; i = -1 )
      {
        if ( v8 < 0 || *v15 == v24 )
          goto LABEL_90;
        v28 = wcspbrk(v15, Control);
        v24 = 0;
        v60 = v28;
        if ( v28 )
        {
          i = v28 - v15;
        }
        else
        {
          do
            ++i;
          while ( v15[i] );
        }
        if ( i > 0x100 && !v56 || i >= 0x8000 )
        {
          v8 = -2147024690;
          goto LABEL_89;
        }
        if ( i != 1 )
          break;
        if ( *v15 != 46 )
          goto LABEL_72;
        if ( v28 )
          goto LABEL_65;
        ++v15;
        if ( v20 > pszDest )
        {
          IsRoot = PathCchIsRoot(pszDest);
          v24 = 0;
          if ( !IsRoot )
          {
            --v20;
            ++v11;
            v48 = v20;
            v50 = v11;
            v8 = StringCchCopyW(v20, v11, &word_18001DE6C);
          }
        }
      }
      if ( i != 2 )
        break;
      if ( *v15 != 46 || v15[1] != 46 )
        goto LABEL_72;
      if ( v20 > pszDest )
      {
        v30 = PathCchIsRoot(pszDest);
        v24 = 0;
        if ( !v30 )
        {
          --v20;
          while ( pszDest < v20 )
          {
            if ( *--v20 == 92 )
            {
              v48 = v20;
              if ( v20 )
              {
                v11 = v10 - (v20 - pszDest);
                goto LABEL_61;
              }
              break;
            }
          }
          v20 = pszDest;
          v11 = v10;
          v48 = pszDest;
LABEL_61:
          v50 = v11;
          v8 = StringCchCopyW(v20, v11, &word_18001DE6C);
          goto LABEL_62;
        }
        v28 = v60;
      }
      if ( !v28 )
      {
LABEL_62:
        v15 += 2;
        continue;
      }
LABEL_65:
      v15 = v28 + 1;
    }
    if ( i )
    {
LABEL_72:
      v8 = StringCchCopyNExW(v20, v11, v15, i, &v48, &v50, 0);
      v24 = 0;
    }
    else
    {
      v31 = StringCchCopyNExW(v20, v11, L"\\", 1u, &v48, &v50, 0);
      v24 = 0;
      ++v15;
      v8 = v31;
      if ( v15 > v55 )
      {
        v32 = v54;
        if ( v61 )
        {
          for ( j = v15 + 1; ; ++j )
          {
            v34 = ((__int64 (__fastcall *)(_QWORD))v32)(*v15);
            v24 = 0;
            if ( !v34 )
              break;
            v15 = j;
          }
        }
        goto LABEL_74;
      }
    }
    v32 = v54;
LABEL_74:
    if ( v8 != -2147024774 || i != 1 || (v35 = ((__int64 (__fastcall *)(_QWORD))v32)(*v15), v24 = 0, !v35) )
    {
      v11 = v50;
      goto LABEL_85;
    }
    v36 = v15[1];
    if ( v36 && (v36 != 46 || v15[2]) )
    {
      v11 = v50;
      if ( v50 == 1 && v36 == 46 && v15[2] == 46 )
      {
        v37 = v48;
        v11 = 0;
        v50 = 0;
        v8 = 0;
        *v48 = 0;
        v20 = v37 + 1;
        v48 = v20;
LABEL_86:
        v15 += i;
        continue;
      }
LABEL_85:
      v20 = v48;
      goto LABEL_86;
    }
    break;
  }
  v11 = v50;
  v8 = 0;
  v20 = v48;
LABEL_89:
  i = -1;
LABEL_90:
  v38 = v51;
  if ( (v51 & 0x20) != 0 && v20 > pszDest && !((unsigned __int8 (__fastcall *)(_QWORD))v54)(*(v20 - 1)) )
  {
    v39 = StringCchCopyNExW(v20, v11, L"\\", 1u, &v48, &v50, 0);
    v20 = v48;
    v8 = v39;
  }
  if ( v8 < 0 )
  {
    StringCchCopyW(pszDest, v10, &word_18001DE6C);
    if ( v8 == -2147024774 )
    {
      if ( (v38 & 1) == 0 )
      {
        if ( v10 != 260 )
          return v8;
        return -2147024690;
      }
      if ( v10 == 0x8000 )
        return -2147024690;
    }
    return v8;
  }
  if ( (v38 & 0x18) == 0 )
  {
    if ( v20 > pszDest )
    {
      v40 = v20 - 1;
      v41 = v40;
      v42 = v40;
      while ( *v40 == 46 )
      {
        if ( v41 == pszDest )
        {
          *v40 = 0;
          break;
        }
        v41 = v42 - 1;
        if ( *(v42 - 1) == 42 )
          break;
        *v40 = 0;
        --v42;
        v40 = v41;
      }
    }
    v43 = -1;
    do
      ++v43;
    while ( pszDest[v43] );
    v44 = &pszDest[v43];
    if ( v44 >= pszDest + 7 && StrIsEqualCaseInsensitive(v44 - 7, L"::$DATA", 7) )
      *(v44 - 7) = 0;
  }
  if ( v52 && v57 == 5 )
  {
    do
      ++i;
    while ( pszDest[v52 + i] );
    if ( i < 0x104 )
    {
      if ( IsUnc2 )
      {
        v45 = pszDest + 8;
        v46 = v10 - 2;
        v47 = pszDest + 2;
      }
      else
      {
        v45 = pszDest + 4;
        v46 = v10;
        v47 = pszDest;
      }
      StringCchCopyW(v47, v46, v45);
    }
  }
  if ( v10 > 1 && !*pszDest )
    *(_DWORD *)pszDest = 92;
  if ( v10 > 3 && pszDest[1] == 58 && !pszDest[2] )
    *((_DWORD *)pszDest + 1) = 92;
  return 0;
}

```

## disassembly

```asm
0x180019fb8  mov     [rsp-8+arg_18], r9d
0x180019fbd  push    rbp
0x180019fbe  push    rbx
0x180019fbf  push    rsi
0x180019fc0  push    rdi
0x180019fc1  push    r12
0x180019fc3  push    r13
0x180019fc5  push    r14
0x180019fc7  push    r15
0x180019fc9  lea     rbp, [rsp-1Fh]
0x180019fce  sub     rsp, 0A8h
0x180019fd5  mov     r15, r8
0x180019fd8  xor     r14d, r14d
0x180019fdb  lea     r8, word_18001DE6C; unsigned __int16 *
0x180019fe2  mov     [rbp+57h+var_78], r14d
0x180019fe6  mov     rbx, rdx
0x180019fe9  mov     rdi, rcx
0x180019fec  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180019ff1  mov     r12d, eax
0x180019ff4  test    eax, eax
0x180019ff6  js      loc_18001A66C
0x180019ffc  cmp     rbx, 8000h
0x18001a003  ja      loc_18001A667
0x18001a009  lea     rcx, [rbp+57h+var_78]; enum PATHCCH_OPTIONS *
0x18001a00d  call    ?AreOptionsValidAndOptInLongPathAwareProcess@@YA_NAEAW4PATHCCH_OPTIONS@@@Z; AreOptionsValidAndOptInLongPathAwareProcess(PATHCCH_OPTIONS &)
0x18001a012  test    al, al
0x18001a014  jz      loc_18001A667
0x18001a01a  mov     ecx, [rbp+57h+var_78]
0x18001a01d  mov     edx, 104h
0x18001a022  cmp     rbx, rdx
0x18001a025  ja      short loc_18001A02A
0x18001a027  and     ecx, 0FFFFFFF8h
0x18001a02a  mov     eax, ecx
0x18001a02c  mov     [rbp+57h+var_88], ecx
0x18001a02f  and     eax, 11h
0x18001a032  mov     [rbp+57h+var_A0], r14
0x18001a036  mov     [rbp+57h+var_60], eax
0x18001a039  neg     eax
0x18001a03b  sbb     rsi, rsi
0x18001a03e  and     esi, 7EFCh
0x18001a044  add     rsi, rdx
0x18001a047  cmp     rbx, rsi
0x18001a04a  cmovb   rsi, rbx
0x18001a04e  mov     [rbp+57h+var_90], rsi
0x18001a052  mov     r13, rsi
0x18001a055  test    cl, 40h
0x18001a058  jz      short loc_18001A065
0x18001a05a  mov     cl, 1
0x18001a05c  lea     rax, IsBackOrForwardSlash
0x18001a063  jmp     short loc_18001A06F
0x18001a065  mov     cl, r14b
0x18001a068  lea     rax, IsBackslash
0x18001a06f  test    cl, cl
0x18001a071  mov     byte ptr [rbp+57h+arg_18], cl
0x18001a074  lea     r8, SubBlock; "\\"
0x18001a07b  mov     [rbp+57h+var_70], rax
0x18001a07f  lea     rdx, asc_180020EA8; "\\/"
0x18001a086  mov     [rbp+57h+var_68], r14
0x18001a08a  cmovz   rdx, r8
0x18001a08e  mov     rcx, r15; unsigned __int16 *
0x18001a091  mov     [rbp+57h+Control], rdx
0x18001a095  mov     r8, rax
0x18001a098  lea     rdx, [rbp+57h+var_68]
0x18001a09c  call    PathIsUnc2
0x18001a0a1  mov     [rbp+57h+var_58], eax
0x18001a0a4  test    eax, eax
0x18001a0a6  jz      short loc_18001A106
0x18001a0a8  mov     r14, [rbp+57h+var_68]
0x18001a0ac  mov     ecx, [rbp+57h+var_88]; enum PATHCCH_OPTIONS
0x18001a0af  mov     [rbp+57h+var_68], r14
0x18001a0b3  call    ?MayNeedExtendedLengthPrefix@@YA_NW4PATHCCH_OPTIONS@@@Z; MayNeedExtendedLengthPrefix(PATHCCH_OPTIONS)
0x18001a0b8  mov     bl, al
0x18001a0ba  lea     r8, aUnc; "\\\\?\\UNC\\"
0x18001a0c1  xor     ecx, ecx
0x18001a0c3  lea     rax, asc_18002116C; "\\\\"
0x18001a0ca  mov     dword ptr [rsp+0E0h+var_B8], ecx; unsigned int
0x18001a0ce  lea     r9, [rbp+57h+var_A0]; unsigned __int16 **
0x18001a0d2  test    bl, bl
0x18001a0d4  mov     rdx, rsi; unsigned __int64
0x18001a0d7  mov     rcx, rdi; pszDest
0x18001a0da  cmovz   r8, rax; unsigned __int16 *
0x18001a0de  lea     rax, [rbp+57h+var_90]
0x18001a0e2  mov     [rsp+0E0h+var_C0], rax; unsigned __int64 *
0x18001a0e7  call    ?StringCchCopyExW@@YAJPEAG_KPEBGPEAPEAGPEA_KK@Z; StringCchCopyExW(ushort *,unsigned __int64,ushort const *,ushort * *,unsigned __int64 *,ulong)
0x18001a0ec  mov     r13, [rbp+57h+var_90]
0x18001a0f0  neg     bl
0x18001a0f2  mov     rbx, [rbp+57h+var_A0]
0x18001a0f6  mov     r12d, eax
0x18001a0f9  sbb     r11, r11
0x18001a0fc  and     r11d, 6
0x18001a100  mov     [rbp+57h+var_80], r11
0x18001a104  jmp     short loc_18001A15D
0x18001a106  mov     rbx, rdi
0x18001a109  mov     [rbp+57h+var_80], r14
0x18001a10d  mov     rcx, r15; unsigned __int16 *
0x18001a110  mov     [rbp+57h+var_A0], rbx
0x18001a114  mov     r14, r15
0x18001a117  call    ?IsExtendedLengthDosDevicePath@@YA_NPEBG@Z; IsExtendedLengthDosDevicePath(ushort const *)
0x18001a11c  mov     [rbp+57h+var_98], al
0x18001a11f  test    al, al
0x18001a121  jz      loc_18001A1C3
0x18001a127  lea     rax, [r15+8]
0x18001a12b  movzx   ecx, word ptr [rax]; C
0x18001a12e  mov     [rbp+57h+var_68], rax
0x18001a132  call    cs:__imp_iswalpha
0x18001a138  xor     ecx, ecx
0x18001a13a  test    eax, eax
0x18001a13c  jz      short loc_18001A14F
0x18001a13e  cmp     word ptr [r15+0Ah], 3Ah ; ':'
0x18001a144  jnz     short loc_18001A14F
0x18001a146  mov     al, [rbp+57h+var_98]
0x18001a149  lea     r14, [r15+8]
0x18001a14d  jmp     short loc_18001A151
0x18001a14f  mov     al, cl
0x18001a151  test    al, al
0x18001a153  jnz     loc_18001A1E1
0x18001a159  mov     r11, [rbp+57h+var_80]
0x18001a15d  mov     eax, [rbp+57h+var_88]
0x18001a160  and     eax, 5
0x18001a163  mov     [rbp+57h+var_5C], eax
0x18001a166  cmp     eax, 5
0x18001a169  jnz     loc_18001A233
0x18001a16f  test    r11, r11
0x18001a172  jz      loc_18001A233
0x18001a178  lea     rax, [r11+104h]
0x18001a17f  cmp     rsi, rax
0x18001a182  ja      loc_18001A233
0x18001a188  mov     eax, 104h
0x18001a18d  lea     r8, word_18001DE6C; unsigned __int16 *
0x18001a194  cmp     rsi, rax
0x18001a197  mov     rbx, rdi
0x18001a19a  mov     rcx, rdi; unsigned __int16 *
0x18001a19d  mov     [rbp+57h+var_A0], rbx
0x18001a1a1  cmova   rsi, rax
0x18001a1a5  mov     r14, r15
0x18001a1a8  xor     r11d, r11d
0x18001a1ab  mov     [rbp+57h+var_90], rsi
0x18001a1af  mov     rdx, rsi; unsigned __int64
0x18001a1b2  mov     [rbp+57h+var_80], r11
0x18001a1b6  mov     r13, rsi
0x18001a1b9  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18001a1be  mov     r12d, eax
0x18001a1c1  jmp     short loc_18001A236
0x18001a1c3  movzx   ecx, word ptr [r15]; C
0x18001a1c7  mov     [rbp+57h+var_68], r15
0x18001a1cb  call    cs:__imp_iswalpha
0x18001a1d1  test    eax, eax
0x18001a1d3  jz      short loc_18001A159
0x18001a1d5  cmp     word ptr [r15+2], 3Ah ; ':'
0x18001a1db  jnz     loc_18001A159
0x18001a1e1  mov     ecx, [rbp+57h+var_88]; enum PATHCCH_OPTIONS
0x18001a1e4  call    ?MayNeedExtendedLengthPrefix@@YA_NW4PATHCCH_OPTIONS@@@Z; MayNeedExtendedLengthPrefix(PATHCCH_OPTIONS)
0x18001a1e9  xor     ecx, ecx
0x18001a1eb  test    al, al
0x18001a1ed  jz      loc_18001A159
0x18001a1f3  lea     eax, [rcx+4]
0x18001a1f6  mov     dword ptr [rsp+0E0h+var_B8], ecx; unsigned int
0x18001a1fa  mov     [rbp+57h+var_80], rax
0x18001a1fe  lea     r9, [rbp+57h+var_A0]; unsigned __int16 **
0x18001a202  lea     rax, [rbp+57h+var_90]
0x18001a206  mov     rdx, rsi; unsigned __int64
0x18001a209  lea     r8, asc_180021228; "\\\\?\\"
0x18001a210  mov     [rsp+0E0h+var_C0], rax; unsigned __int64 *
0x18001a215  mov     rcx, rdi; pszDest
0x18001a218  call    ?StringCchCopyExW@@YAJPEAG_KPEBGPEAPEAGPEA_KK@Z; StringCchCopyExW(ushort *,unsigned __int64,ushort const *,ushort * *,unsigned __int64 *,ulong)
0x18001a21d  mov     r13, [rbp+57h+var_90]
0x18001a221  mov     r12d, eax
0x18001a224  mov     rbx, [rbp+57h+var_A0]
0x18001a228  mov     r11d, 4
0x18001a22e  jmp     loc_18001A15D
0x18001a233  xor     r11d, r11d
0x18001a236  or      r15, 0FFFFFFFFFFFFFFFFh
0x18001a23a  test    r12d, r12d
0x18001a23d  js      loc_18001A4DA
0x18001a243  cmp     [r14], r11w
0x18001a247  jz      loc_18001A4DA
0x18001a24d  mov     rdx, [rbp+57h+Control]; Control
0x18001a251  mov     rcx, r14; String
0x18001a254  call    cs:__imp_wcspbrk
0x18001a25a  xor     r11d, r11d
0x18001a25d  mov     [rbp+57h+var_48], rax
0x18001a261  test    rax, rax
0x18001a264  jz      short loc_18001A271
0x18001a266  mov     r15, rax
0x18001a269  sub     r15, r14
0x18001a26c  sar     r15, 1
0x18001a26f  jmp     short loc_18001A27B
0x18001a271  inc     r15
0x18001a274  cmp     [r14+r15*2], r11w
0x18001a279  jnz     short loc_18001A271
0x18001a27b  cmp     r15, 100h
0x18001a282  jbe     short loc_18001A28E
0x18001a284  cmp     [rbp+57h+var_60], r11d
0x18001a288  jz      loc_18001A4D0
0x18001a28e  cmp     r15, 8000h
0x18001a295  jnb     loc_18001A4D0
0x18001a29b  cmp     r15, 1
0x18001a29f  jnz     short loc_18001A305
0x18001a2a1  cmp     word ptr [r14], 2Eh ; '.'
0x18001a2a6  jnz     loc_18001A414
0x18001a2ac  test    rax, rax
0x18001a2af  jnz     loc_18001A39F
0x18001a2b5  add     r14, 2
0x18001a2b9  lea     r15, [rax-1]
0x18001a2bd  cmp     rbx, rdi
0x18001a2c0  jbe     loc_18001A23A
0x18001a2c6  mov     rcx, rdi; pszPath
0x18001a2c9  call    PathCchIsRoot
0x18001a2ce  xor     r11d, r11d
0x18001a2d1  test    eax, eax
0x18001a2d3  jnz     loc_18001A23A
0x18001a2d9  sub     rbx, 2
0x18001a2dd  lea     r8, word_18001DE6C; unsigned __int16 *
0x18001a2e4  inc     r13
0x18001a2e7  mov     [rbp+57h+var_A0], rbx
0x18001a2eb  mov     rdx, r13; unsigned __int64
0x18001a2ee  mov     [rbp+57h+var_90], r13
0x18001a2f2  mov     rcx, rbx; unsigned __int16 *
0x18001a2f5  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18001a2fa  mov     r12d, eax
0x18001a2fd  or      r15, r15
0x18001a300  jmp     loc_18001A23A
0x18001a305  cmp     r15, 2
0x18001a309  jnz     loc_18001A3A8
0x18001a30f  cmp     word ptr [r14], 2Eh ; '.'
0x18001a314  jnz     loc_18001A414
0x18001a31a  cmp     word ptr [r14+2], 2Eh ; '.'
0x18001a320  jnz     loc_18001A414
0x18001a326  cmp     rbx, rdi
0x18001a329  jbe     short loc_18001A39A
0x18001a32b  mov     rcx, rdi; pszPath
0x18001a32e  call    PathCchIsRoot
0x18001a333  xor     r11d, r11d
0x18001a336  test    eax, eax
0x18001a338  jnz     short loc_18001A396
0x18001a33a  add     rbx, 0FFFFFFFFFFFFFFFEh
0x18001a33e  lea     eax, [r15+5Ah]
0x18001a342  cmp     rdi, rbx
0x18001a345  jnb     short loc_18001A36A
0x18001a347  sub     rbx, 2
0x18001a34b  cmp     [rbx], ax
0x18001a34e  jnz     short loc_18001A342
0x18001a350  mov     [rbp+57h+var_A0], rbx
0x18001a354  test    rbx, rbx
0x18001a357  jz      short loc_18001A36A
0x18001a359  mov     rax, rbx
0x18001a35c  mov     r13, rsi
0x18001a35f  sub     rax, rdi
0x18001a362  sar     rax, 1
0x18001a365  sub     r13, rax
0x18001a368  jmp     short loc_18001A374
0x18001a36a  mov     rbx, rdi
0x18001a36d  mov     r13, rsi
0x18001a370  mov     [rbp+57h+var_A0], rbx
0x18001a374  lea     r8, word_18001DE6C; unsigned __int16 *
0x18001a37b  mov     [rbp+57h+var_90], r13
0x18001a37f  mov     rdx, r13; unsigned __int64
0x18001a382  mov     rcx, rbx; unsigned __int16 *
0x18001a385  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18001a38a  mov     r12d, eax
0x18001a38d  add     r14, 4
0x18001a391  jmp     loc_18001A236
0x18001a396  mov     rax, [rbp+57h+var_48]
0x18001a39a  test    rax, rax
0x18001a39d  jz      short loc_18001A38D
0x18001a39f  lea     r14, [rax+2]
0x18001a3a3  jmp     loc_18001A236
0x18001a3a8  test    r15, r15
0x18001a3ab  jnz     short loc_18001A414
0x18001a3ad  mov     [rsp+0E0h+var_B0], r11d; unsigned int
0x18001a3b2  lea     rax, [rbp+57h+var_90]
0x18001a3b6  mov     [rsp+0E0h+var_B8], rax; unsigned __int64 *
0x18001a3bb  lea     r9d, [r15+1]; unsigned __int64
0x18001a3bf  lea     rax, [rbp+57h+var_A0]
0x18001a3c3  mov     rdx, r13; cchDest
0x18001a3c6  lea     r8, SubBlock; "\\"
0x18001a3cd  mov     [rsp+0E0h+var_C0], rax; unsigned __int16 **
0x18001a3d2  mov     rcx, rbx; pszDest
0x18001a3d5  call    ?StringCchCopyNExW@@YAJPEAG_KPEBG1PEAPEAGPEA_KK@Z; StringCchCopyNExW(ushort *,unsigned __int64,ushort const *,unsigned __int64,ushort * *,unsigned __int64 *,ulong)
0x18001a3da  xor     r11d, r11d
0x18001a3dd  add     r14, 2
0x18001a3e1  mov     r12d, eax
0x18001a3e4  cmp     r14, [rbp+57h+var_68]
0x18001a3e8  jbe     short loc_18001A442
0x18001a3ea  mov     r13, [rbp+57h+var_70]
0x18001a3ee  cmp     byte ptr [rbp+57h+arg_18], r11b
0x18001a3f2  jz      short loc_18001A446
0x18001a3f4  lea     rbx, [r14+2]
0x18001a3f8  movzx   ecx, word ptr [r14]
0x18001a3fc  mov     rax, r13
0x18001a3ff  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001a404  xor     r11d, r11d
0x18001a407  test    al, al
0x18001a409  jz      short loc_18001A446
0x18001a40b  mov     r14, rbx
0x18001a40e  add     rbx, 2
0x18001a412  jmp     short loc_18001A3F8
0x18001a414  mov     [rsp+0E0h+var_B0], r11d; unsigned int
0x18001a419  lea     rax, [rbp+57h+var_90]
0x18001a41d  mov     [rsp+0E0h+var_B8], rax; unsigned __int64 *
  ... truncated ...
```
