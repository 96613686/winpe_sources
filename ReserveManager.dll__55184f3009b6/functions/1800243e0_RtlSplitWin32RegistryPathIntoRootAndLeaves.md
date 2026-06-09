# RtlSplitWin32RegistryPathIntoRootAndLeaves

- ea: `0x1800243e0`
- end: `0x18002458f`
- name: `RtlSplitWin32RegistryPathIntoRootAndLeaves`
- size: `431`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x1800177f8`

## callees

- `0x18000f674`
- `0x18000fafc`
- `0x1800243e0`

## string_xrefs

- `0x180024428`: `onecore\base\lstring\path.cpp`
- `0x180024476`: `onecore\base\lstring\path.cpp`
- `0x1800244a2`: `onecore\base\lstring\path.cpp`
- `0x180024505`: `onecore\base\lstring\path.cpp`
- `0x18002443b`: `RtlSplitWin32RegistryPathIntoRootAndLeaves`
- `0x180024489`: `RtlSplitWin32RegistryPathIntoRootAndLeaves`
- `0x1800244b5`: `RtlSplitWin32RegistryPathIntoRootAndLeaves`
- `0x18002451f`: `RtlSplitWin32RegistryPathIntoRootAndLeaves`
- `0x180024446`: `Not-null check failed: Win32RegistryPath`
- `0x1800244c0`: `Not-null check failed: RootRelativePath`

## pseudocode

```c
__int64 __fastcall RtlSplitWin32RegistryPathIntoRootAndLeaves(__int64 a1, const __m128i *a2, __int64 **a3, __m128i *a4)
{
  const char *v7; // rax
  __int64 result; // rax
  __int64 v9; // rdi
  __int64 *v10; // r8
  __int64 v11; // rcx
  __int64 v12; // rdx
  _BYTE v13[8]; // [rsp+20h] [rbp-30h] BYREF
  const char *v14; // [rsp+28h] [rbp-28h] BYREF
  const char *v15; // [rsp+30h] [rbp-20h]
  __int64 v16; // [rsp+38h] [rbp-18h]
  const char *v17; // [rsp+40h] [rbp-10h]

  if ( a3 )
    *a3 = 0;
  if ( a4 )
  {
    a4->m128i_i64[0] = 0;
    a4->m128i_i64[1] = 0;
    a4[1].m128i_i64[0] = 0;
  }
  if ( !a2 )
  {
    v16 = 239;
    v14 = "onecore\\base\\lstring\\path.cpp";
    v15 = "RtlSplitWin32RegistryPathIntoRootAndLeaves";
    v7 = "Not-null check failed: Win32RegistryPath";
LABEL_7:
    v17 = v7;
    RtlReportErrorOrigination(&v14, &GUID_44edceb3_7a6e_47e9_b787_5aa9dadfa4ab, 3221225485LL);
    return 3221225485LL;
  }
  if ( !a3 )
  {
    v16 = 240;
    v14 = "onecore\\base\\lstring\\path.cpp";
    v15 = "RtlSplitWin32RegistryPathIntoRootAndLeaves";
    v7 = "Not-null check failed: KeyRoot";
    goto LABEL_7;
  }
  if ( !a4 )
  {
    v16 = 241;
    v14 = "onecore\\base\\lstring\\path.cpp";
    v15 = "RtlSplitWin32RegistryPathIntoRootAndLeaves";
    v7 = "Not-null check failed: RootRelativePath";
    goto LABEL_7;
  }
  v9 = 0;
  while ( 1 )
  {
    v13[0] = 0;
    result = RtlEqualLUnicodeStringPrefix(a2, (__int64 *)off_1800357F0[3 * v9], RtlUpcaseUCSCharacter, v13);
    if ( (int)result < 0 )
      return result;
    if ( v13[0] )
    {
      v10 = (__int64 *)off_1800357F0[3 * v9 + 2];
      if ( !v10 )
      {
LABEL_16:
        v16 = 279;
        v14 = "onecore\\base\\lstring\\path.cpp";
        v17 = 0;
        v15 = "RtlSplitWin32RegistryPathIntoRootAndLeaves";
        RtlReportErrorOrigination(&v14, &GUID_44edceb3_7a6e_47e9_b787_5aa9dadfa4ab, 3221225529LL);
        return 3221225529LL;
      }
      v11 = (*off_1800357F0[3 * v9])[0];
      v12 = v11 + a2[1].m128i_i64[0];
      result = 0;
      *a4 = _mm_sub_epi64(
              _mm_loadu_si128(a2),
              _mm_unpacklo_epi64((__m128i)(unsigned __int64)v11, (__m128i)(unsigned __int64)v11));
      a4[1].m128i_i64[0] = v12;
      *a3 = v10;
      return result;
    }
    if ( (unsigned __int64)++v9 >= 9 )
      goto LABEL_16;
  }
}

```

## disassembly

```asm
0x1800243e0  push    rbp
0x1800243e2  push    rbx
0x1800243e3  push    rsi
0x1800243e4  push    rdi
0x1800243e5  push    r13
0x1800243e7  push    r14
0x1800243e9  push    r15
0x1800243eb  mov     rbp, rsp
0x1800243ee  sub     rsp, 50h
0x1800243f2  mov     rbx, r9
0x1800243f5  mov     rsi, r8
0x1800243f8  mov     r14, rdx
0x1800243fb  test    r8, r8
0x1800243fe  jz      short loc_180024407
0x180024400  mov     qword ptr [r8], 0
0x180024407  test    rbx, rbx
0x18002440a  jz      short loc_180024423
0x18002440c  mov     qword ptr [r9], 0
0x180024413  mov     qword ptr [r9+8], 0
0x18002441b  mov     qword ptr [r9+10h], 0
0x180024423  test    r14, r14
0x180024426  jnz     short loc_180024471
0x180024428  lea     rax, aOnecoreBaseLst; "onecore\\base\\lstring\\path.cpp"
0x18002442f  mov     [rbp+var_18], 0EFh
0x180024437  mov     [rbp+var_28], rax
0x18002443b  lea     rax, aRtlsplitwin32r; "RtlSplitWin32RegistryPathIntoRootAndLea"...
0x180024442  mov     [rbp+var_20], rax
0x180024446  lea     rax, aNotNullCheckFa_7; "Not-null check failed: Win32RegistryPat"...
0x18002444d  mov     r8d, 0C000000Dh
0x180024453  mov     [rbp+var_10], rax
0x180024457  lea     rdx, _GUID_44edceb3_7a6e_47e9_b787_5aa9dadfa4ab
0x18002445e  lea     rcx, [rbp+var_28]
0x180024462  call    RtlReportErrorOrigination
0x180024467  mov     eax, 0C000000Dh
0x18002446c  jmp     loc_180024546
0x180024471  test    rsi, rsi
0x180024474  jnz     short loc_18002449D
0x180024476  lea     rax, aOnecoreBaseLst; "onecore\\base\\lstring\\path.cpp"
0x18002447d  mov     [rbp+var_18], 0F0h
0x180024485  mov     [rbp+var_28], rax
0x180024489  lea     rax, aRtlsplitwin32r; "RtlSplitWin32RegistryPathIntoRootAndLea"...
0x180024490  mov     [rbp+var_20], rax
0x180024494  lea     rax, aNotNullCheckFa_13; "Not-null check failed: KeyRoot"
0x18002449b  jmp     short loc_18002444D
0x18002449d  test    rbx, rbx
0x1800244a0  jnz     short loc_1800244C9
0x1800244a2  lea     rax, aOnecoreBaseLst; "onecore\\base\\lstring\\path.cpp"
0x1800244a9  mov     [rbp+var_18], 0F1h
0x1800244b1  mov     [rbp+var_28], rax
0x1800244b5  lea     rax, aRtlsplitwin32r; "RtlSplitWin32RegistryPathIntoRootAndLea"...
0x1800244bc  mov     [rbp+var_20], rax
0x1800244c0  lea     rax, aNotNullCheckFa_6; "Not-null check failed: RootRelativePath"
0x1800244c7  jmp     short loc_18002444D
0x1800244c9  xor     edi, edi
0x1800244cb  lea     r13, off_1800357F0
0x1800244d2  lea     r15, [rdi+rdi*2]
0x1800244d6  mov     [rbp+var_30], 0
0x1800244da  mov     rdx, [r13+r15*8+0]
0x1800244df  lea     r9, [rbp+var_30]
0x1800244e3  lea     r8, RtlUpcaseUCSCharacter
0x1800244ea  mov     rcx, r14
0x1800244ed  call    RtlEqualLUnicodeStringPrefix
0x1800244f2  test    eax, eax
0x1800244f4  js      short loc_180024546
0x1800244f6  cmp     [rbp+var_30], 0
0x1800244fa  jnz     short loc_180024555
0x1800244fc  inc     rdi
0x1800244ff  cmp     rdi, 9
0x180024503  jb      short loc_1800244D2
0x180024505  lea     rax, aOnecoreBaseLst; "onecore\\base\\lstring\\path.cpp"
0x18002450c  mov     [rbp+var_18], 117h
0x180024514  mov     [rbp+var_28], rax
0x180024518  lea     rdx, _GUID_44edceb3_7a6e_47e9_b787_5aa9dadfa4ab
0x18002451f  lea     rax, aRtlsplitwin32r; "RtlSplitWin32RegistryPathIntoRootAndLea"...
0x180024526  mov     [rbp+var_10], 0
0x18002452e  mov     r8d, 0C0000039h
0x180024534  mov     [rbp+var_20], rax
0x180024538  lea     rcx, [rbp+var_28]
0x18002453c  call    RtlReportErrorOrigination
0x180024541  mov     eax, 0C0000039h
0x180024546  add     rsp, 50h
0x18002454a  pop     r15
0x18002454c  pop     r14
0x18002454e  pop     r13
0x180024550  pop     rdi
0x180024551  pop     rsi
0x180024552  pop     rbx
0x180024553  pop     rbp
0x180024554  retn
0x180024555  mov     r8, [r13+r15*8+10h]
0x18002455a  test    r8, r8
0x18002455d  jz      short loc_180024505
0x18002455f  mov     rax, [r13+r15*8+0]
0x180024564  movdqu  xmm1, xmmword ptr [r14]
0x180024569  mov     rdx, [r14+10h]
0x18002456d  mov     rcx, [rax]
0x180024570  add     rdx, rcx
0x180024573  xor     eax, eax
0x180024575  movq    xmm0, rcx
0x18002457a  punpcklqdq xmm0, xmm0
0x18002457e  psubq   xmm1, xmm0
0x180024582  movdqu  xmmword ptr [rbx], xmm1
0x180024586  mov     [rbx+10h], rdx
0x18002458a  mov     [rsi], r8
0x18002458d  jmp     short loc_180024546
```
