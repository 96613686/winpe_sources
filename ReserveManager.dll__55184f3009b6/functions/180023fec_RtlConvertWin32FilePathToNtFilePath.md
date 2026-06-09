# RtlConvertWin32FilePathToNtFilePath

- ea: `0x180023fec`
- end: `0x18002429f`
- name: `RtlConvertWin32FilePathToNtFilePath`
- size: `691`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x18001a5b4`

## callees

- `0x18000f220`
- `0x18000fafc`
- `0x180010794`
- `0x180023fec`

## string_xrefs

- `0x180024018`: `onecore\base\lstring\path.cpp`
- `0x180024066`: `onecore\base\lstring\path.cpp`
- `0x18002409a`: `onecore\base\lstring\path.cpp`
- `0x1800240ef`: `onecore\base\lstring\path.cpp`
- `0x180024163`: `onecore\base\lstring\path.cpp`
- `0x180024036`: `Not-null check failed: PathIn`
- `0x180024084`: `Not-null check failed: PathOut`
- `0x18002402b`: `RtlConvertWin32FilePathToNtFilePath`
- `0x180024079`: `RtlConvertWin32FilePathToNtFilePath`
- `0x1800240ad`: `RtlConvertWin32FilePathToNtFilePath`
- `0x180024102`: `RtlConvertWin32FilePathToNtFilePath`
- `0x180024176`: `RtlConvertWin32FilePathToNtFilePath`
- `0x1800240b8`: `PathIn->Length >= 2 * sizeof(WCHAR)`
- `0x180024181`: `(PathIn->Length > 4 * sizeof(WCHAR)) && (PathIn->Buffer[3] == L'\\')`

## pseudocode

```c
__int64 __fastcall RtlConvertWin32FilePathToNtFilePath(unsigned __int64 *a1, _QWORD *a2)
{
  const char *v4; // rax
  __int64 result; // rax
  unsigned __int64 v6; // rdx
  __int64 v7; // rcx
  _WORD *v8; // rax
  _WORD *v9; // rax
  char v10; // di
  __int128 v11; // xmm0
  const wchar_t *v12; // xmm1_8
  __int64 v13; // rcx
  unsigned __int64 v14; // rax
  int v15; // esi
  __int16 *v16; // rdx
  __int16 *v17; // rcx
  __int16 *v18; // r10
  __int16 *v19; // r9
  __int16 v20; // r8
  __int16 *v21; // rax
  __int64 v22; // xmm1_8
  __int128 v23; // [rsp+20h] [rbp-50h] BYREF
  __int64 v24; // [rsp+30h] [rbp-40h]
  const char *v25; // [rsp+38h] [rbp-38h]
  __int128 v26; // [rsp+40h] [rbp-30h] BYREF
  const wchar_t *v27; // [rsp+50h] [rbp-20h]
  unsigned __int64 v28; // [rsp+58h] [rbp-18h]
  unsigned __int64 v29; // [rsp+60h] [rbp-10h]
  _WORD *v30; // [rsp+68h] [rbp-8h]

  if ( a2 )
    *a2 = 0;
  if ( !a1 )
  {
    v24 = 300;
    *(_QWORD *)&v23 = "onecore\\base\\lstring\\path.cpp";
    *((_QWORD *)&v23 + 1) = "RtlConvertWin32FilePathToNtFilePath";
    v4 = "Not-null check failed: PathIn";
LABEL_5:
    v25 = v4;
LABEL_6:
    RtlReportErrorOrigination(&v23, &GUID_44edceb3_7a6e_47e9_b787_5aa9dadfa4ab, 3221225485LL);
    return 3221225485LL;
  }
  if ( !a2 )
  {
    v24 = 301;
    *(_QWORD *)&v23 = "onecore\\base\\lstring\\path.cpp";
    *((_QWORD *)&v23 + 1) = "RtlConvertWin32FilePathToNtFilePath";
    v4 = "Not-null check failed: PathOut";
    goto LABEL_5;
  }
  v6 = *a1;
  v7 = 4;
  if ( v6 < 4 )
  {
    v24 = 302;
    *(_QWORD *)&v23 = "onecore\\base\\lstring\\path.cpp";
    *((_QWORD *)&v23 + 1) = "RtlConvertWin32FilePathToNtFilePath";
    v4 = "PathIn->Length >= 2 * sizeof(WCHAR)";
    goto LABEL_5;
  }
  if ( v6 >= 8 )
  {
    v8 = (_WORD *)a1[2];
    if ( *v8 == 92 && v8[1] == 63 && v8[2] == 63 && v8[3] == 92 )
    {
      v24 = 312;
      *(_QWORD *)&v23 = "onecore\\base\\lstring\\path.cpp";
      *((_QWORD *)&v23 + 1) = "RtlConvertWin32FilePathToNtFilePath";
      v25 = 0;
      goto LABEL_6;
    }
  }
  v9 = (_WORD *)a1[2];
  v10 = 1;
  if ( *v9 == 92 && v9[1] == 92 )
  {
    if ( v6 >= 6 && (v9[2] == 63 || v9[2] == 46) )
    {
      if ( v6 <= 8 || v9[3] != 92 )
      {
        v24 = 334;
        *(_QWORD *)&v23 = "onecore\\base\\lstring\\path.cpp";
        *((_QWORD *)&v23 + 1) = "RtlConvertWin32FilePathToNtFilePath";
        v4 = "(PathIn->Length > 4 * sizeof(WCHAR)) && (PathIn->Buffer[3] == L'\\\\')";
        goto LABEL_5;
      }
      v11 = g_LUNICODE_STRING__bslash__q__q__bslash_;
      v10 = 0;
      v12 = L"\\??\\";
    }
    else
    {
      v11 = g_LUNICODE_STRING__bslash__q__q__bslash_UNC_bslash_;
      v7 = 2;
      v12 = L"\\??\\UNC\\";
    }
  }
  else
  {
    v11 = g_LUNICODE_STRING__bslash__q__q__bslash_;
    v7 = 0;
    v12 = L"\\??\\";
  }
  v13 = 2 * v7;
  v27 = v12;
  v24 = a2[2];
  v30 = &v9[(unsigned __int64)v13 / 2];
  v14 = a1[1];
  v28 = v6 - v13;
  v26 = v11;
  v29 = v14 - v13;
  v23 = *(_OWORD *)a2;
  *(_OWORD *)a2 = 0;
  a2[2] = 0;
  v15 = RtlConcatenateLUnicodeStrings(1, 2, &v26, &v23);
  if ( v15 >= 0 )
  {
    if ( !v10 )
    {
LABEL_43:
      result = 0;
      v22 = v24;
      *(_OWORD *)a2 = v23;
      a2[2] = v22;
      return result;
    }
    v16 = (__int16 *)v24;
    v17 = (__int16 *)v24;
    v18 = (__int16 *)(v24 + v23);
    v19 = 0;
    while ( 1 )
    {
      if ( v16 == v18 )
        goto LABEL_43;
      v20 = *v16;
      v21 = v17;
      ++v16;
      if ( v20 == 32 )
        v21 = v19;
      v19 = v21;
      if ( v20 == 47 )
      {
        v20 = 92;
      }
      else if ( v20 != 92 )
      {
        goto LABEL_41;
      }
      if ( v21 )
        v17 = v21;
LABEL_41:
      *v17++ = v20;
    }
  }
  if ( v24 )
    anonymous_namespace_::OurRtlFreeStringRoutine(v24);
  return (unsigned int)v15;
}

```

## disassembly

```asm
0x180023fec  mov     [rsp-18h+arg_0], rbx
0x180023ff1  mov     [rsp-18h+arg_10], rsi
0x180023ff6  push    rbp
0x180023ff7  push    rdi
0x180023ff8  push    r14
0x180023ffa  mov     rbp, rsp
0x180023ffd  sub     rsp, 70h
0x180024001  mov     rbx, rdx
0x180024004  mov     r8, rcx
0x180024007  test    rdx, rdx
0x18002400a  jz      short loc_180024013
0x18002400c  mov     qword ptr [rdx], 0
0x180024013  test    r8, r8
0x180024016  jnz     short loc_180024061
0x180024018  lea     rax, aOnecoreBaseLst; "onecore\\base\\lstring\\path.cpp"
0x18002401f  mov     [rbp+var_40], 12Ch
0x180024027  mov     qword ptr [rbp+var_50], rax
0x18002402b  lea     rax, aRtlconvertwin3; "RtlConvertWin32FilePathToNtFilePath"
0x180024032  mov     qword ptr [rbp+var_50+8], rax
0x180024036  lea     rax, aNotNullCheckFa_3; "Not-null check failed: PathIn"
0x18002403d  mov     [rbp+var_38], rax
0x180024041  mov     r8d, 0C000000Dh
0x180024047  lea     rdx, _GUID_44edceb3_7a6e_47e9_b787_5aa9dadfa4ab
0x18002404e  lea     rcx, [rbp+var_50]
0x180024052  call    RtlReportErrorOrigination
0x180024057  mov     eax, 0C000000Dh
0x18002405c  jmp     loc_18002428A
0x180024061  test    rbx, rbx
0x180024064  jnz     short loc_18002408D
0x180024066  lea     rax, aOnecoreBaseLst; "onecore\\base\\lstring\\path.cpp"
0x18002406d  mov     [rbp+var_40], 12Dh
0x180024075  mov     qword ptr [rbp+var_50], rax
0x180024079  lea     rax, aRtlconvertwin3; "RtlConvertWin32FilePathToNtFilePath"
0x180024080  mov     qword ptr [rbp+var_50+8], rax
0x180024084  lea     rax, aNotNullCheckFa_0; "Not-null check failed: PathOut"
0x18002408b  jmp     short loc_18002403D
0x18002408d  mov     rdx, [rcx]
0x180024090  mov     ecx, 4
0x180024095  cmp     rdx, rcx
0x180024098  jnb     short loc_1800240C4
0x18002409a  lea     rax, aOnecoreBaseLst; "onecore\\base\\lstring\\path.cpp"
0x1800240a1  mov     [rbp+var_40], 12Eh
0x1800240a9  mov     qword ptr [rbp+var_50], rax
0x1800240ad  lea     rax, aRtlconvertwin3; "RtlConvertWin32FilePathToNtFilePath"
0x1800240b4  mov     qword ptr [rbp+var_50+8], rax
0x1800240b8  lea     rax, aPathinLength2S; "PathIn->Length >= 2 * sizeof(WCHAR)"
0x1800240bf  jmp     loc_18002403D
0x1800240c4  mov     r14d, 5Ch ; '\'
0x1800240ca  cmp     rdx, 8
0x1800240ce  jb      short loc_18002411A
0x1800240d0  mov     rax, [r8+10h]
0x1800240d4  cmp     [rax], r14w
0x1800240d8  jnz     short loc_18002411A
0x1800240da  cmp     word ptr [rax+2], 3Fh ; '?'
0x1800240df  jnz     short loc_18002411A
0x1800240e1  cmp     word ptr [rax+4], 3Fh ; '?'
0x1800240e6  jnz     short loc_18002411A
0x1800240e8  cmp     [rax+6], r14w
0x1800240ed  jnz     short loc_18002411A
0x1800240ef  lea     rax, aOnecoreBaseLst; "onecore\\base\\lstring\\path.cpp"
0x1800240f6  mov     [rbp+var_40], 138h
0x1800240fe  mov     qword ptr [rbp+var_50], rax
0x180024102  lea     rax, aRtlconvertwin3; "RtlConvertWin32FilePathToNtFilePath"
0x180024109  mov     qword ptr [rbp+var_50+8], rax
0x18002410d  mov     [rbp+var_38], 0
0x180024115  jmp     loc_180024041
0x18002411a  mov     rax, [r8+10h]
0x18002411e  mov     dil, 1
0x180024121  cmp     [rax], r14w
0x180024125  jnz     short loc_1800241A3
0x180024127  cmp     [rax+2], r14w
0x18002412c  jnz     short loc_1800241A3
0x18002412e  cmp     rdx, 6
0x180024132  jb      short loc_18002418D
0x180024134  cmp     word ptr [rax+4], 3Fh ; '?'
0x180024139  jz      short loc_180024142
0x18002413b  cmp     word ptr [rax+4], 2Eh ; '.'
0x180024140  jnz     short loc_18002418D
0x180024142  cmp     rdx, 8
0x180024146  jbe     short loc_180024163
0x180024148  cmp     [rax+6], r14w
0x18002414d  jnz     short loc_180024163
0x18002414f  movups  xmm0, cs:g_LUNICODE_STRING__bslash__q__q__bslash_
0x180024156  xor     dil, dil
0x180024159  movsd   xmm1, cs:off_180035968; "\\??\\"
0x180024161  jmp     short loc_1800241B4
0x180024163  lea     rax, aOnecoreBaseLst; "onecore\\base\\lstring\\path.cpp"
0x18002416a  mov     [rbp+var_40], 14Eh
0x180024172  mov     qword ptr [rbp+var_50], rax
0x180024176  lea     rax, aRtlconvertwin3; "RtlConvertWin32FilePathToNtFilePath"
0x18002417d  mov     qword ptr [rbp+var_50+8], rax
0x180024181  lea     rax, aPathinLength4S; "(PathIn->Length > 4 * sizeof(WCHAR)) &&"...
0x180024188  jmp     loc_18002403D
0x18002418d  movups  xmm0, cs:g_LUNICODE_STRING__bslash__q__q__bslash_UNC_bslash_
0x180024194  mov     ecx, 2
0x180024199  movsd   xmm1, cs:off_180035998; "\\??\\UNC\\"
0x1800241a1  jmp     short loc_1800241B4
0x1800241a3  movups  xmm0, cs:g_LUNICODE_STRING__bslash__q__q__bslash_
0x1800241aa  xor     ecx, ecx
0x1800241ac  movsd   xmm1, cs:off_180035968; "\\??\\"
0x1800241b4  add     rcx, rcx
0x1800241b7  movsd   [rbp+var_20], xmm1
0x1800241bc  movsd   xmm1, qword ptr [rbx+10h]
0x1800241c1  lea     r9, [rbp+var_50]
0x1800241c5  add     rax, rcx
0x1800241c8  movsd   [rbp+var_40], xmm1
0x1800241cd  mov     [rbp+var_8], rax
0x1800241d1  sub     rdx, rcx
0x1800241d4  mov     rax, [r8+8]
0x1800241d8  lea     r8, [rbp+var_30]
0x1800241dc  sub     rax, rcx
0x1800241df  mov     [rbp+var_18], rdx
0x1800241e3  movups  [rbp+var_30], xmm0
0x1800241e7  mov     [rbp+var_10], rax
0x1800241eb  xor     eax, eax
0x1800241ed  movups  xmm0, xmmword ptr [rbx]
0x1800241f0  movups  [rbp+var_50], xmm0
0x1800241f4  lea     edx, [rax+2]
0x1800241f7  xorps   xmm0, xmm0
0x1800241fa  lea     ecx, [rax+1]
0x1800241fd  movups  xmmword ptr [rbx], xmm0
0x180024200  mov     [rbx+10h], rax
0x180024204  call    RtlConcatenateLUnicodeStrings
0x180024209  mov     esi, eax
0x18002420b  test    eax, eax
0x18002420d  jns     short loc_180024221
0x18002420f  mov     rcx, [rbp+var_40]
0x180024213  test    rcx, rcx
0x180024216  jz      short loc_18002421D
0x180024218  call    _anonymous_namespace___OurRtlFreeStringRoutine
0x18002421d  mov     eax, esi
0x18002421f  jmp     short loc_18002428A
0x180024221  test    dil, dil
0x180024224  jz      short loc_180024277
0x180024226  mov     rdx, [rbp+var_40]
0x18002422a  mov     r10, qword ptr [rbp+var_50]
0x18002422e  mov     rcx, rdx
0x180024231  add     r10, rdx
0x180024234  xor     r9d, r9d
0x180024237  jmp     short loc_180024272
0x180024239  movzx   r8d, word ptr [rdx]
0x18002423d  mov     rax, rcx
0x180024240  add     rdx, 2
0x180024244  cmp     r8w, 20h ; ' '
0x180024249  cmovz   rax, r9
0x18002424d  mov     r9, rax
0x180024250  cmp     r8w, 2Fh ; '/'
0x180024255  jnz     short loc_18002425D
0x180024257  movzx   r8d, r14w
0x18002425b  jmp     short loc_180024263
0x18002425d  cmp     r8w, r14w
0x180024261  jnz     short loc_18002426A
0x180024263  test    rax, rax
0x180024266  cmovnz  rcx, rax
0x18002426a  mov     [rcx], r8w
0x18002426e  add     rcx, 2
0x180024272  cmp     rdx, r10
0x180024275  jnz     short loc_180024239
0x180024277  movups  xmm0, [rbp+var_50]
0x18002427b  xor     eax, eax
0x18002427d  movsd   xmm1, [rbp+var_40]
0x180024282  movups  xmmword ptr [rbx], xmm0
0x180024285  movsd   qword ptr [rbx+10h], xmm1
0x18002428a  lea     r11, [rsp+70h+var_s0]
0x18002428f  mov     rbx, [r11+20h]
0x180024293  mov     rsi, [r11+30h]
0x180024297  mov     rsp, r11
0x18002429a  pop     r14
0x18002429c  pop     rdi
0x18002429d  pop     rbp
0x18002429e  retn
```
