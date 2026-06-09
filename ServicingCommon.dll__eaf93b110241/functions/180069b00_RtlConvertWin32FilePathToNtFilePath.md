# RtlConvertWin32FilePathToNtFilePath

- ea: `0x180069b00`
- end: `0x180069e0d`
- name: `RtlConvertWin32FilePathToNtFilePath`
- size: `781`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: ``

## callers

- `0x180074928`

## callees

- `0x180002564`
- `0x18001f4ac`
- `0x18001f5d4`
- `0x1800293a0`
- `0x1800655b0`
- `0x180069b00`

## string_xrefs

- `0x180069b44`: `onecore\base\lstring\path.cpp`
- `0x180069b84`: `onecore\base\lstring\path.cpp`
- `0x180069bb8`: `onecore\base\lstring\path.cpp`
- `0x180069c1e`: `onecore\base\lstring\path.cpp`
- `0x180069ca5`: `onecore\base\lstring\path.cpp`
- `0x180069b62`: `Not-null check failed: PathIn`
- `0x180069ba2`: `Not-null check failed: PathOut`
- `0x180069b57`: `RtlConvertWin32FilePathToNtFilePath`
- `0x180069b97`: `RtlConvertWin32FilePathToNtFilePath`
- `0x180069bcb`: `RtlConvertWin32FilePathToNtFilePath`
- `0x180069c35`: `RtlConvertWin32FilePathToNtFilePath`
- `0x180069cb8`: `RtlConvertWin32FilePathToNtFilePath`
- `0x180069bd6`: `PathIn->Length >= 2 * sizeof(WCHAR)`
- `0x180069cc3`: `(PathIn->Length > 4 * sizeof(WCHAR)) && (PathIn->Buffer[3] == L'\\')`

## pseudocode

```c
__int64 __fastcall RtlConvertWin32FilePathToNtFilePath(unsigned __int64 *a1, _QWORD *a2)
{
  const char *v4; // rax
  unsigned __int64 v6; // rdx
  __int64 v7; // rcx
  _WORD *v8; // rax
  _WORD *v9; // rax
  char v10; // di
  __int128 v11; // xmm0
  const wchar_t *v12; // xmm1_8
  __int64 v13; // rcx
  __int64 v14; // rax
  __int64 v15; // xmm1_8
  int v16; // esi
  __int16 *v17; // rdx
  __int16 *v18; // rcx
  __int16 *v19; // r10
  __int16 *v20; // r9
  __int16 v21; // r8
  __int16 *v22; // rax
  __int64 v23; // xmm2_8
  __int128 v24; // [rsp+20h] [rbp-60h] BYREF
  __int64 v25; // [rsp+30h] [rbp-50h]
  const char *v26; // [rsp+38h] [rbp-48h]
  __int128 v27; // [rsp+40h] [rbp-40h] BYREF
  const wchar_t *v28; // [rsp+50h] [rbp-30h]
  unsigned __int64 v29; // [rsp+58h] [rbp-28h]
  __int64 v30; // [rsp+60h] [rbp-20h]
  _WORD *v31; // [rsp+68h] [rbp-18h]
  int v32; // [rsp+70h] [rbp-10h] BYREF

  v32 = 0;
  if ( a2 )
    *a2 = 0;
  if ( !a1 )
  {
    v25 = 300;
    *(_QWORD *)&v24 = "onecore\\base\\lstring\\path.cpp";
    *((_QWORD *)&v24 + 1) = "RtlConvertWin32FilePathToNtFilePath";
    v4 = "Not-null check failed: PathIn";
LABEL_5:
    v26 = v4;
    return Windows::ErrorHandling::Rtl::CBaseFrame<Windows::ErrorHandling::Rtl::CSimpleNtStatusCarryingFrame,long>::OriginateInvalidParameter_NullPointer(
             &v32,
             &v24);
  }
  if ( !a2 )
  {
    v25 = 301;
    *(_QWORD *)&v24 = "onecore\\base\\lstring\\path.cpp";
    *((_QWORD *)&v24 + 1) = "RtlConvertWin32FilePathToNtFilePath";
    v4 = "Not-null check failed: PathOut";
    goto LABEL_5;
  }
  v6 = *a1;
  v7 = 4;
  if ( v6 < 4 )
  {
    v25 = 302;
    *(_QWORD *)&v24 = "onecore\\base\\lstring\\path.cpp";
    *((_QWORD *)&v24 + 1) = "RtlConvertWin32FilePathToNtFilePath";
    v4 = "PathIn->Length >= 2 * sizeof(WCHAR)";
    goto LABEL_5;
  }
  if ( v6 >= 8 )
  {
    v8 = (_WORD *)a1[2];
    if ( *v8 == 92 && v8[1] == 63 && v8[2] == 63 && v8[3] == 92 )
    {
      v25 = 312;
      *(_QWORD *)&v24 = "onecore\\base\\lstring\\path.cpp";
      v26 = 0;
      *((_QWORD *)&v24 + 1) = "RtlConvertWin32FilePathToNtFilePath";
      return Windows::ErrorHandling::Rtl::CBaseFrame<Windows::ErrorHandling::Rtl::CSimpleNtStatusCarryingFrame,long>::OriginateNtStatus(
               &v32,
               &v24,
               3221225485LL);
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
        v25 = 334;
        *(_QWORD *)&v24 = "onecore\\base\\lstring\\path.cpp";
        *((_QWORD *)&v24 + 1) = "RtlConvertWin32FilePathToNtFilePath";
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
    v11 = g_uc_LUNICODE_STRING__bslash__q__q__bslash_;
    v7 = 0;
    v12 = L"\\??\\";
  }
  v13 = 2 * v7;
  v28 = v12;
  v31 = &v9[(unsigned __int64)v13 / 2];
  v14 = a1[1] - v13;
  v29 = v6 - v13;
  v30 = v14;
  v27 = v11;
  v25 = 0;
  v24 = 0;
  Windows::Rtl::AutoString<_LUTF8_STRING,Windows::Auto<_LUTF8_STRING>>::Close(&v24);
  v15 = a2[2];
  v24 = *(_OWORD *)a2;
  v25 = v15;
  *(_OWORD *)a2 = 0;
  a2[2] = 0;
  v16 = RtlConcatenateLUnicodeStrings(1, 2, &v27, &v24);
  if ( v16 >= 0 )
  {
    if ( v10 )
    {
      v17 = (__int16 *)v25;
      v18 = (__int16 *)v25;
      v19 = (__int16 *)(v25 + v24);
      v20 = 0;
      while ( v17 != v19 )
      {
        v21 = *v17;
        v22 = v18;
        ++v17;
        if ( v21 == 32 )
          v22 = v20;
        v20 = v22;
        if ( v21 == 47 )
        {
          v21 = 92;
        }
        else if ( v21 != 92 )
        {
          goto LABEL_37;
        }
        if ( v22 )
          v18 = v22;
LABEL_37:
        *v18++ = v21;
      }
    }
    v23 = v25;
    *(_OWORD *)a2 = v24;
    v16 = 0;
    v25 = 0;
    a2[2] = v23;
    v24 = 0;
  }
  Windows::Rtl::AutoString<_LUTF8_STRING,Windows::Auto<_LUTF8_STRING>>::Close(&v24);
  return (unsigned int)v16;
}

```

## disassembly

```asm
0x180069b00  mov     [rsp-18h+arg_0], rbx
0x180069b05  mov     [rsp-18h+arg_10], rsi
0x180069b0a  push    rbp
0x180069b0b  push    rdi
0x180069b0c  push    r15
0x180069b0e  mov     rbp, rsp
0x180069b11  sub     rsp, 80h
0x180069b18  mov     rax, cs:__security_cookie
0x180069b1f  xor     rax, rsp
0x180069b22  mov     [rbp+var_8], rax
0x180069b26  mov     [rbp+var_10], 0
0x180069b2d  mov     rbx, rdx
0x180069b30  mov     r8, rcx
0x180069b33  test    rdx, rdx
0x180069b36  jz      short loc_180069B3F
0x180069b38  mov     qword ptr [rdx], 0
0x180069b3f  test    r8, r8
0x180069b42  jnz     short loc_180069B7F
0x180069b44  lea     rax, aOnecoreBaseLst; "onecore\\base\\lstring\\path.cpp"
0x180069b4b  mov     [rbp+var_50], 12Ch
0x180069b53  mov     qword ptr [rbp+var_60], rax
0x180069b57  lea     rax, aRtlconvertwin3_1; "RtlConvertWin32FilePathToNtFilePath"
0x180069b5e  mov     qword ptr [rbp+var_60+8], rax
0x180069b62  lea     rax, aNotNullCheckFa_33; "Not-null check failed: PathIn"
0x180069b69  lea     rdx, [rbp+var_60]
0x180069b6d  mov     [rbp+var_48], rax
0x180069b71  lea     rcx, [rbp+var_10]
0x180069b75  call    ?OriginateInvalidParameter_NullPointer@?$CBaseFrame@UCSimpleNtStatusCarryingFrame@Rtl@ErrorHandling@Windows@@J@Rtl@ErrorHandling@Windows@@QEAAJAEBU_RTL_CALL_SITE@34@@Z; Windows::ErrorHandling::Rtl::CBaseFrame<Windows::ErrorHandling::Rtl::CSimpleNtStatusCarryingFrame,long>::OriginateInvalidParameter_NullPointer(Windows::ErrorHandling::_RTL_CALL_SITE const &)
0x180069b7a  jmp     loc_180069DE8
0x180069b7f  test    rbx, rbx
0x180069b82  jnz     short loc_180069BAB
0x180069b84  lea     rax, aOnecoreBaseLst; "onecore\\base\\lstring\\path.cpp"
0x180069b8b  mov     [rbp+var_50], 12Dh
0x180069b93  mov     qword ptr [rbp+var_60], rax
0x180069b97  lea     rax, aRtlconvertwin3_1; "RtlConvertWin32FilePathToNtFilePath"
0x180069b9e  mov     qword ptr [rbp+var_60+8], rax
0x180069ba2  lea     rax, aNotNullCheckFa_9; "Not-null check failed: PathOut"
0x180069ba9  jmp     short loc_180069B69
0x180069bab  mov     rdx, [rcx]
0x180069bae  mov     ecx, 4
0x180069bb3  cmp     rdx, rcx
0x180069bb6  jnb     short loc_180069BF3
0x180069bb8  lea     rax, aOnecoreBaseLst; "onecore\\base\\lstring\\path.cpp"
0x180069bbf  mov     [rbp+var_50], 12Eh
0x180069bc7  mov     qword ptr [rbp+var_60], rax
0x180069bcb  lea     rax, aRtlconvertwin3_1; "RtlConvertWin32FilePathToNtFilePath"
0x180069bd2  mov     qword ptr [rbp+var_60+8], rax
0x180069bd6  lea     rax, aPathinLength2S; "PathIn->Length >= 2 * sizeof(WCHAR)"
0x180069bdd  lea     rdx, [rbp+var_60]
0x180069be1  mov     [rbp+var_48], rax
0x180069be5  lea     rcx, [rbp+var_10]
0x180069be9  call    ?OriginateInvalidParameter_NullPointer@?$CBaseFrame@UCSimpleNtStatusCarryingFrame@Rtl@ErrorHandling@Windows@@J@Rtl@ErrorHandling@Windows@@QEAAJAEBU_RTL_CALL_SITE@34@@Z; Windows::ErrorHandling::Rtl::CBaseFrame<Windows::ErrorHandling::Rtl::CSimpleNtStatusCarryingFrame,long>::OriginateInvalidParameter_NullPointer(Windows::ErrorHandling::_RTL_CALL_SITE const &)
0x180069bee  jmp     loc_180069DE8
0x180069bf3  mov     r15d, 5Ch ; '\'
0x180069bf9  cmp     rdx, 8
0x180069bfd  jb      short loc_180069C5C
0x180069bff  mov     rax, [r8+10h]
0x180069c03  cmp     [rax], r15w
0x180069c07  jnz     short loc_180069C5C
0x180069c09  cmp     word ptr [rax+2], 3Fh ; '?'
0x180069c0e  jnz     short loc_180069C5C
0x180069c10  cmp     word ptr [rax+4], 3Fh ; '?'
0x180069c15  jnz     short loc_180069C5C
0x180069c17  cmp     [rax+6], r15w
0x180069c1c  jnz     short loc_180069C5C
0x180069c1e  lea     rax, aOnecoreBaseLst; "onecore\\base\\lstring\\path.cpp"
0x180069c25  mov     [rbp+var_50], 138h
0x180069c2d  mov     qword ptr [rbp+var_60], rax
0x180069c31  lea     rdx, [rbp+var_60]
0x180069c35  lea     rax, aRtlconvertwin3_1; "RtlConvertWin32FilePathToNtFilePath"
0x180069c3c  mov     [rbp+var_48], 0
0x180069c44  mov     r8d, 0C000000Dh
0x180069c4a  mov     qword ptr [rbp+var_60+8], rax
0x180069c4e  lea     rcx, [rbp+var_10]
0x180069c52  call    ?OriginateNtStatus@?$CBaseFrame@UCSimpleNtStatusCarryingFrame@Rtl@ErrorHandling@Windows@@J@Rtl@ErrorHandling@Windows@@QEAAJAEBU_RTL_CALL_SITE@34@J@Z; Windows::ErrorHandling::Rtl::CBaseFrame<Windows::ErrorHandling::Rtl::CSimpleNtStatusCarryingFrame,long>::OriginateNtStatus(Windows::ErrorHandling::_RTL_CALL_SITE const &,long)
0x180069c57  jmp     loc_180069DE8
0x180069c5c  mov     rax, [r8+10h]
0x180069c60  mov     dil, 1
0x180069c63  cmp     [rax], r15w
0x180069c67  jnz     short loc_180069CE5
0x180069c69  cmp     [rax+2], r15w
0x180069c6e  jnz     short loc_180069CE5
0x180069c70  cmp     rdx, 6
0x180069c74  jb      short loc_180069CCF
0x180069c76  cmp     word ptr [rax+4], 3Fh ; '?'
0x180069c7b  jz      short loc_180069C84
0x180069c7d  cmp     word ptr [rax+4], 2Eh ; '.'
0x180069c82  jnz     short loc_180069CCF
0x180069c84  cmp     rdx, 8
0x180069c88  jbe     short loc_180069CA5
0x180069c8a  cmp     [rax+6], r15w
0x180069c8f  jnz     short loc_180069CA5
0x180069c91  movups  xmm0, cs:g_LUNICODE_STRING__bslash__q__q__bslash_
0x180069c98  xor     dil, dil
0x180069c9b  movsd   xmm1, cs:off_1800A57F8; "\\??\\"
0x180069ca3  jmp     short loc_180069CF6
0x180069ca5  lea     rax, aOnecoreBaseLst; "onecore\\base\\lstring\\path.cpp"
0x180069cac  mov     [rbp+var_50], 14Eh
0x180069cb4  mov     qword ptr [rbp+var_60], rax
0x180069cb8  lea     rax, aRtlconvertwin3_1; "RtlConvertWin32FilePathToNtFilePath"
0x180069cbf  mov     qword ptr [rbp+var_60+8], rax
0x180069cc3  lea     rax, aPathinLength4S; "(PathIn->Length > 4 * sizeof(WCHAR)) &&"...
0x180069cca  jmp     loc_180069BDD
0x180069ccf  movups  xmm0, cs:g_LUNICODE_STRING__bslash__q__q__bslash_UNC_bslash_
0x180069cd6  mov     ecx, 2
0x180069cdb  movsd   xmm1, cs:off_1800A5858; "\\??\\UNC\\"
0x180069ce3  jmp     short loc_180069CF6
0x180069ce5  movups  xmm0, cs:g_uc_LUNICODE_STRING__bslash__q__q__bslash_
0x180069cec  xor     ecx, ecx
0x180069cee  movsd   xmm1, cs:off_1800A5948; "\\??\\"
0x180069cf6  add     rcx, rcx
0x180069cf9  movsd   [rbp+var_30], xmm1
0x180069cfe  add     rax, rcx
0x180069d01  sub     rdx, rcx
0x180069d04  mov     [rbp+var_18], rax
0x180069d08  mov     rax, [r8+8]
0x180069d0c  sub     rax, rcx
0x180069d0f  mov     [rbp+var_28], rdx
0x180069d13  mov     [rbp+var_20], rax
0x180069d17  lea     rcx, [rbp+var_60]
0x180069d1b  movups  [rbp+var_40], xmm0
0x180069d1f  xor     eax, eax
0x180069d21  xorps   xmm0, xmm0
0x180069d24  mov     [rbp+var_50], rax
0x180069d28  movups  [rbp+var_60], xmm0
0x180069d2c  call    ?Close@?$AutoString@U_LUTF8_STRING@@V?$Auto@U_LUTF8_STRING@@@Windows@@@Rtl@Windows@@QEAAXXZ; Windows::Rtl::AutoString<_LUTF8_STRING,Windows::Auto<_LUTF8_STRING>>::Close(void)
0x180069d31  movups  xmm0, xmmword ptr [rbx]
0x180069d34  lea     r9, [rbp+var_60]
0x180069d38  xor     eax, eax
0x180069d3a  movsd   xmm1, qword ptr [rbx+10h]
0x180069d3f  lea     r8, [rbp+var_40]
0x180069d43  movups  [rbp+var_60], xmm0
0x180069d47  xorps   xmm0, xmm0
0x180069d4a  movsd   [rbp+var_50], xmm1
0x180069d4f  movups  xmmword ptr [rbx], xmm0
0x180069d52  lea     edx, [rax+2]
0x180069d55  mov     [rbx+10h], rax
0x180069d59  lea     ecx, [rax+1]
0x180069d5c  call    RtlConcatenateLUnicodeStrings
0x180069d61  mov     esi, eax
0x180069d63  test    eax, eax
0x180069d65  js      short loc_180069DDD
0x180069d67  test    dil, dil
0x180069d6a  jz      short loc_180069DBD
0x180069d6c  mov     rdx, [rbp+var_50]
0x180069d70  mov     r10, qword ptr [rbp+var_60]
0x180069d74  mov     rcx, rdx
0x180069d77  add     r10, rdx
0x180069d7a  xor     r9d, r9d
0x180069d7d  jmp     short loc_180069DB8
0x180069d7f  movzx   r8d, word ptr [rdx]
0x180069d83  mov     rax, rcx
0x180069d86  add     rdx, 2
0x180069d8a  cmp     r8w, 20h ; ' '
0x180069d8f  cmovz   rax, r9
0x180069d93  mov     r9, rax
0x180069d96  cmp     r8w, 2Fh ; '/'
0x180069d9b  jnz     short loc_180069DA3
0x180069d9d  movzx   r8d, r15w
0x180069da1  jmp     short loc_180069DA9
0x180069da3  cmp     r8w, r15w
0x180069da7  jnz     short loc_180069DB0
0x180069da9  test    rax, rax
0x180069dac  cmovnz  rcx, rax
0x180069db0  mov     [rcx], r8w
0x180069db4  add     rcx, 2
0x180069db8  cmp     rdx, r10
0x180069dbb  jnz     short loc_180069D7F
0x180069dbd  movups  xmm1, [rbp+var_60]
0x180069dc1  xor     eax, eax
0x180069dc3  movsd   xmm2, [rbp+var_50]
0x180069dc8  xorps   xmm0, xmm0
0x180069dcb  movups  xmmword ptr [rbx], xmm1
0x180069dce  xor     esi, esi
0x180069dd0  mov     [rbp+var_50], rax
0x180069dd4  movsd   qword ptr [rbx+10h], xmm2
0x180069dd9  movups  [rbp+var_60], xmm0
0x180069ddd  lea     rcx, [rbp+var_60]
0x180069de1  call    ?Close@?$AutoString@U_LUTF8_STRING@@V?$Auto@U_LUTF8_STRING@@@Windows@@@Rtl@Windows@@QEAAXXZ; Windows::Rtl::AutoString<_LUTF8_STRING,Windows::Auto<_LUTF8_STRING>>::Close(void)
0x180069de6  mov     eax, esi
0x180069de8  mov     rcx, [rbp+var_8]
0x180069dec  xor     rcx, rsp; StackCookie
0x180069def  call    __security_check_cookie
0x180069df4  lea     r11, [rsp+80h+var_s0]
0x180069dfc  mov     rbx, [r11+20h]
0x180069e00  mov     rsi, [r11+30h]
0x180069e04  mov     rsp, r11
0x180069e07  pop     r15
0x180069e09  pop     rdi
0x180069e0a  pop     rbp
0x180069e0b  retn
```
