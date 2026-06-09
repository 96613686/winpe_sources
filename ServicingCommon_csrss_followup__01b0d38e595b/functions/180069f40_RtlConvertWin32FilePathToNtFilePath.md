# RtlConvertWin32FilePathToNtFilePath

- ea: `0x180069f40`
- end: `0x18006a24d`
- name: `RtlConvertWin32FilePathToNtFilePath`
- size: `781`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: ``

## callers

- `0x180074910`

## callees

- `0x180004a8c`
- `0x18001d7b0`
- `0x18001f1d8`
- `0x18001f840`
- `0x18002d2b0`
- `0x180069f40`

## string_xrefs

- `0x180069f84`: `onecore\base\lstring\path.cpp`
- `0x180069fc4`: `onecore\base\lstring\path.cpp`
- `0x180069ff8`: `onecore\base\lstring\path.cpp`
- `0x18006a05e`: `onecore\base\lstring\path.cpp`
- `0x18006a0e5`: `onecore\base\lstring\path.cpp`
- `0x180069fa2`: `Not-null check failed: PathIn`
- `0x180069fe2`: `Not-null check failed: PathOut`
- `0x180069f97`: `RtlConvertWin32FilePathToNtFilePath`
- `0x180069fd7`: `RtlConvertWin32FilePathToNtFilePath`
- `0x18006a00b`: `RtlConvertWin32FilePathToNtFilePath`
- `0x18006a075`: `RtlConvertWin32FilePathToNtFilePath`
- `0x18006a0f8`: `RtlConvertWin32FilePathToNtFilePath`
- `0x18006a016`: `PathIn->Length >= 2 * sizeof(WCHAR)`
- `0x18006a103`: `(PathIn->Length > 4 * sizeof(WCHAR)) && (PathIn->Buffer[3] == L'\\')`

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
0x180069f40  mov     [rsp-18h+arg_0], rbx
0x180069f45  mov     [rsp-18h+arg_10], rsi
0x180069f4a  push    rbp
0x180069f4b  push    rdi
0x180069f4c  push    r15
0x180069f4e  mov     rbp, rsp
0x180069f51  sub     rsp, 80h
0x180069f58  mov     rax, cs:__security_cookie
0x180069f5f  xor     rax, rsp
0x180069f62  mov     [rbp+var_8], rax
0x180069f66  mov     [rbp+var_10], 0
0x180069f6d  mov     rbx, rdx
0x180069f70  mov     r8, rcx
0x180069f73  test    rdx, rdx
0x180069f76  jz      short loc_180069F7F
0x180069f78  mov     qword ptr [rdx], 0
0x180069f7f  test    r8, r8
0x180069f82  jnz     short loc_180069FBF
0x180069f84  lea     rax, aOnecoreBaseLst; "onecore\\base\\lstring\\path.cpp"
0x180069f8b  mov     [rbp+var_50], 12Ch
0x180069f93  mov     qword ptr [rbp+var_60], rax
0x180069f97  lea     rax, aRtlconvertwin3_1; "RtlConvertWin32FilePathToNtFilePath"
0x180069f9e  mov     qword ptr [rbp+var_60+8], rax
0x180069fa2  lea     rax, aNotNullCheckFa_33; "Not-null check failed: PathIn"
0x180069fa9  lea     rdx, [rbp+var_60]
0x180069fad  mov     [rbp+var_48], rax
0x180069fb1  lea     rcx, [rbp+var_10]
0x180069fb5  call    ?OriginateInvalidParameter_NullPointer@?$CBaseFrame@UCSimpleNtStatusCarryingFrame@Rtl@ErrorHandling@Windows@@J@Rtl@ErrorHandling@Windows@@QEAAJAEBU_RTL_CALL_SITE@34@@Z; Windows::ErrorHandling::Rtl::CBaseFrame<Windows::ErrorHandling::Rtl::CSimpleNtStatusCarryingFrame,long>::OriginateInvalidParameter_NullPointer(Windows::ErrorHandling::_RTL_CALL_SITE const &)
0x180069fba  jmp     loc_18006A228
0x180069fbf  test    rbx, rbx
0x180069fc2  jnz     short loc_180069FEB
0x180069fc4  lea     rax, aOnecoreBaseLst; "onecore\\base\\lstring\\path.cpp"
0x180069fcb  mov     [rbp+var_50], 12Dh
0x180069fd3  mov     qword ptr [rbp+var_60], rax
0x180069fd7  lea     rax, aRtlconvertwin3_1; "RtlConvertWin32FilePathToNtFilePath"
0x180069fde  mov     qword ptr [rbp+var_60+8], rax
0x180069fe2  lea     rax, aNotNullCheckFa_9; "Not-null check failed: PathOut"
0x180069fe9  jmp     short loc_180069FA9
0x180069feb  mov     rdx, [rcx]
0x180069fee  mov     ecx, 4
0x180069ff3  cmp     rdx, rcx
0x180069ff6  jnb     short loc_18006A033
0x180069ff8  lea     rax, aOnecoreBaseLst; "onecore\\base\\lstring\\path.cpp"
0x180069fff  mov     [rbp+var_50], 12Eh
0x18006a007  mov     qword ptr [rbp+var_60], rax
0x18006a00b  lea     rax, aRtlconvertwin3_1; "RtlConvertWin32FilePathToNtFilePath"
0x18006a012  mov     qword ptr [rbp+var_60+8], rax
0x18006a016  lea     rax, aPathinLength2S; "PathIn->Length >= 2 * sizeof(WCHAR)"
0x18006a01d  lea     rdx, [rbp+var_60]
0x18006a021  mov     [rbp+var_48], rax
0x18006a025  lea     rcx, [rbp+var_10]
0x18006a029  call    ?OriginateInvalidParameter_NullPointer@?$CBaseFrame@UCSimpleNtStatusCarryingFrame@Rtl@ErrorHandling@Windows@@J@Rtl@ErrorHandling@Windows@@QEAAJAEBU_RTL_CALL_SITE@34@@Z; Windows::ErrorHandling::Rtl::CBaseFrame<Windows::ErrorHandling::Rtl::CSimpleNtStatusCarryingFrame,long>::OriginateInvalidParameter_NullPointer(Windows::ErrorHandling::_RTL_CALL_SITE const &)
0x18006a02e  jmp     loc_18006A228
0x18006a033  mov     r15d, 5Ch ; '\'
0x18006a039  cmp     rdx, 8
0x18006a03d  jb      short loc_18006A09C
0x18006a03f  mov     rax, [r8+10h]
0x18006a043  cmp     [rax], r15w
0x18006a047  jnz     short loc_18006A09C
0x18006a049  cmp     word ptr [rax+2], 3Fh ; '?'
0x18006a04e  jnz     short loc_18006A09C
0x18006a050  cmp     word ptr [rax+4], 3Fh ; '?'
0x18006a055  jnz     short loc_18006A09C
0x18006a057  cmp     [rax+6], r15w
0x18006a05c  jnz     short loc_18006A09C
0x18006a05e  lea     rax, aOnecoreBaseLst; "onecore\\base\\lstring\\path.cpp"
0x18006a065  mov     [rbp+var_50], 138h
0x18006a06d  mov     qword ptr [rbp+var_60], rax
0x18006a071  lea     rdx, [rbp+var_60]
0x18006a075  lea     rax, aRtlconvertwin3_1; "RtlConvertWin32FilePathToNtFilePath"
0x18006a07c  mov     [rbp+var_48], 0
0x18006a084  mov     r8d, 0C000000Dh
0x18006a08a  mov     qword ptr [rbp+var_60+8], rax
0x18006a08e  lea     rcx, [rbp+var_10]
0x18006a092  call    ?OriginateNtStatus@?$CBaseFrame@UCSimpleNtStatusCarryingFrame@Rtl@ErrorHandling@Windows@@J@Rtl@ErrorHandling@Windows@@QEAAJAEBU_RTL_CALL_SITE@34@J@Z; Windows::ErrorHandling::Rtl::CBaseFrame<Windows::ErrorHandling::Rtl::CSimpleNtStatusCarryingFrame,long>::OriginateNtStatus(Windows::ErrorHandling::_RTL_CALL_SITE const &,long)
0x18006a097  jmp     loc_18006A228
0x18006a09c  mov     rax, [r8+10h]
0x18006a0a0  mov     dil, 1
0x18006a0a3  cmp     [rax], r15w
0x18006a0a7  jnz     short loc_18006A125
0x18006a0a9  cmp     [rax+2], r15w
0x18006a0ae  jnz     short loc_18006A125
0x18006a0b0  cmp     rdx, 6
0x18006a0b4  jb      short loc_18006A10F
0x18006a0b6  cmp     word ptr [rax+4], 3Fh ; '?'
0x18006a0bb  jz      short loc_18006A0C4
0x18006a0bd  cmp     word ptr [rax+4], 2Eh ; '.'
0x18006a0c2  jnz     short loc_18006A10F
0x18006a0c4  cmp     rdx, 8
0x18006a0c8  jbe     short loc_18006A0E5
0x18006a0ca  cmp     [rax+6], r15w
0x18006a0cf  jnz     short loc_18006A0E5
0x18006a0d1  movups  xmm0, cs:g_LUNICODE_STRING__bslash__q__q__bslash_
0x18006a0d8  xor     dil, dil
0x18006a0db  movsd   xmm1, cs:off_1800A3928; "\\??\\"
0x18006a0e3  jmp     short loc_18006A136
0x18006a0e5  lea     rax, aOnecoreBaseLst; "onecore\\base\\lstring\\path.cpp"
0x18006a0ec  mov     [rbp+var_50], 14Eh
0x18006a0f4  mov     qword ptr [rbp+var_60], rax
0x18006a0f8  lea     rax, aRtlconvertwin3_1; "RtlConvertWin32FilePathToNtFilePath"
0x18006a0ff  mov     qword ptr [rbp+var_60+8], rax
0x18006a103  lea     rax, aPathinLength4S; "(PathIn->Length > 4 * sizeof(WCHAR)) &&"...
0x18006a10a  jmp     loc_18006A01D
0x18006a10f  movups  xmm0, cs:g_LUNICODE_STRING__bslash__q__q__bslash_UNC_bslash_
0x18006a116  mov     ecx, 2
0x18006a11b  movsd   xmm1, cs:off_1800A3988; "\\??\\UNC\\"
0x18006a123  jmp     short loc_18006A136
0x18006a125  movups  xmm0, cs:g_uc_LUNICODE_STRING__bslash__q__q__bslash_
0x18006a12c  xor     ecx, ecx
0x18006a12e  movsd   xmm1, cs:off_1800A3A78; "\\??\\"
0x18006a136  add     rcx, rcx
0x18006a139  movsd   [rbp+var_30], xmm1
0x18006a13e  add     rax, rcx
0x18006a141  sub     rdx, rcx
0x18006a144  mov     [rbp+var_18], rax
0x18006a148  mov     rax, [r8+8]
0x18006a14c  sub     rax, rcx
0x18006a14f  mov     [rbp+var_28], rdx
0x18006a153  mov     [rbp+var_20], rax
0x18006a157  lea     rcx, [rbp+var_60]
0x18006a15b  movups  [rbp+var_40], xmm0
0x18006a15f  xor     eax, eax
0x18006a161  xorps   xmm0, xmm0
0x18006a164  mov     [rbp+var_50], rax
0x18006a168  movups  [rbp+var_60], xmm0
0x18006a16c  call    ?Close@?$AutoString@U_LUTF8_STRING@@V?$Auto@U_LUTF8_STRING@@@Windows@@@Rtl@Windows@@QEAAXXZ; Windows::Rtl::AutoString<_LUTF8_STRING,Windows::Auto<_LUTF8_STRING>>::Close(void)
0x18006a171  movups  xmm0, xmmword ptr [rbx]
0x18006a174  lea     r9, [rbp+var_60]
0x18006a178  xor     eax, eax
0x18006a17a  movsd   xmm1, qword ptr [rbx+10h]
0x18006a17f  lea     r8, [rbp+var_40]
0x18006a183  movups  [rbp+var_60], xmm0
0x18006a187  xorps   xmm0, xmm0
0x18006a18a  movsd   [rbp+var_50], xmm1
0x18006a18f  movups  xmmword ptr [rbx], xmm0
0x18006a192  lea     edx, [rax+2]
0x18006a195  mov     [rbx+10h], rax
0x18006a199  lea     ecx, [rax+1]
0x18006a19c  call    RtlConcatenateLUnicodeStrings
0x18006a1a1  mov     esi, eax
0x18006a1a3  test    eax, eax
0x18006a1a5  js      short loc_18006A21D
0x18006a1a7  test    dil, dil
0x18006a1aa  jz      short loc_18006A1FD
0x18006a1ac  mov     rdx, [rbp+var_50]
0x18006a1b0  mov     r10, qword ptr [rbp+var_60]
0x18006a1b4  mov     rcx, rdx
0x18006a1b7  add     r10, rdx
0x18006a1ba  xor     r9d, r9d
0x18006a1bd  jmp     short loc_18006A1F8
0x18006a1bf  movzx   r8d, word ptr [rdx]
0x18006a1c3  mov     rax, rcx
0x18006a1c6  add     rdx, 2
0x18006a1ca  cmp     r8w, 20h ; ' '
0x18006a1cf  cmovz   rax, r9
0x18006a1d3  mov     r9, rax
0x18006a1d6  cmp     r8w, 2Fh ; '/'
0x18006a1db  jnz     short loc_18006A1E3
0x18006a1dd  movzx   r8d, r15w
0x18006a1e1  jmp     short loc_18006A1E9
0x18006a1e3  cmp     r8w, r15w
0x18006a1e7  jnz     short loc_18006A1F0
0x18006a1e9  test    rax, rax
0x18006a1ec  cmovnz  rcx, rax
0x18006a1f0  mov     [rcx], r8w
0x18006a1f4  add     rcx, 2
0x18006a1f8  cmp     rdx, r10
0x18006a1fb  jnz     short loc_18006A1BF
0x18006a1fd  movups  xmm1, [rbp+var_60]
0x18006a201  xor     eax, eax
0x18006a203  movsd   xmm2, [rbp+var_50]
0x18006a208  xorps   xmm0, xmm0
0x18006a20b  movups  xmmword ptr [rbx], xmm1
0x18006a20e  xor     esi, esi
0x18006a210  mov     [rbp+var_50], rax
0x18006a214  movsd   qword ptr [rbx+10h], xmm2
0x18006a219  movups  [rbp+var_60], xmm0
0x18006a21d  lea     rcx, [rbp+var_60]
0x18006a221  call    ?Close@?$AutoString@U_LUTF8_STRING@@V?$Auto@U_LUTF8_STRING@@@Windows@@@Rtl@Windows@@QEAAXXZ; Windows::Rtl::AutoString<_LUTF8_STRING,Windows::Auto<_LUTF8_STRING>>::Close(void)
0x18006a226  mov     eax, esi
0x18006a228  mov     rcx, [rbp+var_8]
0x18006a22c  xor     rcx, rsp; StackCookie
0x18006a22f  call    __security_check_cookie
0x18006a234  lea     r11, [rsp+80h+var_s0]
0x18006a23c  mov     rbx, [r11+20h]
0x18006a240  mov     rsi, [r11+30h]
0x18006a244  mov     rsp, r11
0x18006a247  pop     r15
0x18006a249  pop     rdi
0x18006a24a  pop     rbp
0x18006a24b  retn
```
