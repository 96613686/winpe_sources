# RtlConvertWin32RegistryPathToNtRegistryPathUser(ulong,_LUNICODE_STRING const *,_LUNICODE_STRING const *,_LUNICODE_STRING *)

- ea: `0x1800238e8`
- end: `0x180023b45`
- name: `?RtlConvertWin32RegistryPathToNtRegistryPathUser@@YAJKPEBU_LUNICODE_STRING@@0PEAU1@@Z`
- size: `605`
- prototype: `__int64 __fastcall(__int64, const struct _LUNICODE_STRING *, const struct _LUNICODE_STRING *, struct _LUNICODE_STRING *)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config, loader_planting`

## callers

- `0x1800242a8`

## callees

- `0x180003870`
- `0x180005658`
- `0x18000f58c`
- `0x18000f674`
- `0x18000fafc`
- `0x180010794`
- `0x1800238e8`
- `0x180023b4c`

## import_xrefs

- `ntdll!RtlFormatCurrentUserKeyPath` at `0x180023a34`
- `ntdll!RtlFormatCurrentUserKeyPath` at `0x180023a34`

## string_xrefs

- `0x18002392f`: `onecore\base\lstring\path.cpp`
- `0x18002397d`: `onecore\base\lstring\path.cpp`
- `0x180023a40`: `onecore\base\lstring\path.cpp`
- `0x180023af5`: `onecore\base\lstring\path.cpp`
- `0x18002393a`: `RtlConvertWin32RegistryPathToNtRegistryPathUser`
- `0x180023988`: `RtlConvertWin32RegistryPathToNtRegistryPathUser`
- `0x180023a4b`: `RtlConvertWin32RegistryPathToNtRegistryPathUser`
- `0x180023b00`: `RtlConvertWin32RegistryPathToNtRegistryPathUser`
- `0x18002394d`: `Not-null check failed: PathIn`
- `0x18002399b`: `Not-null check failed: PathOut`
- `0x180023a5e`: `RtlFormatCurrentUserKeyPath(UserProfilePath.GetMutablePointer())`
- `0x180023b13`: `PathOut->Length != 0`

## pseudocode

```c
__int64 __fastcall RtlConvertWin32RegistryPathToNtRegistryPathUser(
        __int64 a1,
        const struct _LUNICODE_STRING *a2,
        const struct _LUNICODE_STRING *a3,
        struct _LUNICODE_STRING *a4)
{
  const char *v6; // rax
  __int64 result; // rax
  int v8; // edi
  _QWORD *v9; // r14
  NTSTATUS v10; // edi
  __int64 v11; // rcx
  _BYTE v12[8]; // [rsp+38h] [rbp-39h] BYREF
  __int128 v13; // [rsp+40h] [rbp-31h] BYREF
  __int64 v14; // [rsp+50h] [rbp-21h]
  const char *v15; // [rsp+58h] [rbp-19h]
  _QWORD v16[7]; // [rsp+60h] [rbp-11h] BYREF
  struct _UNICODE_STRING KeyPath; // [rsp+98h] [rbp+27h] BYREF

  v16[6] = -2;
  if ( a4 )
    *(_QWORD *)a4 = 0;
  if ( !a3 )
  {
    *(_QWORD *)&v13 = "onecore\\base\\lstring\\path.cpp";
    *((_QWORD *)&v13 + 1) = "RtlConvertWin32RegistryPathToNtRegistryPathUser";
    v14 = 87;
    v6 = "Not-null check failed: PathIn";
LABEL_5:
    v15 = v6;
    RtlReportErrorOrigination(&v13, &GUID_44edceb3_7a6e_47e9_b787_5aa9dadfa4ab, 3221225485LL);
    return 3221225485LL;
  }
  if ( !a4 )
  {
    *(_QWORD *)&v13 = "onecore\\base\\lstring\\path.cpp";
    *((_QWORD *)&v13 + 1) = "RtlConvertWin32RegistryPathToNtRegistryPathUser";
    v14 = 88;
    v6 = "Not-null check failed: PathOut";
    goto LABEL_5;
  }
  v16[0] = 34;
  v16[1] = 36;
  v16[2] = L"HKEY_CURRENT_USER";
  v16[3] = 8;
  v16[4] = 10;
  v16[5] = L"HKCU";
  v12[0] = 0;
  v8 = 0;
  while ( 1 )
  {
    v9 = &v16[3 * v8];
    result = RtlEqualLUnicodeStringPrefix(a3, v9, RtlUpcaseUCSCharacter, v12);
    if ( (int)result < 0 )
      return result;
    if ( v12[0] )
      break;
    if ( (unsigned int)++v8 >= 2 )
      goto LABEL_23;
  }
  v13 = 0;
  v14 = 0;
  KeyPath = 0;
  v10 = RtlFormatCurrentUserKeyPath(&KeyPath);
  if ( v10 < 0 )
  {
    *(_QWORD *)&v13 = "onecore\\base\\lstring\\path.cpp";
    *((_QWORD *)&v13 + 1) = "RtlConvertWin32RegistryPathToNtRegistryPathUser";
    v14 = 113;
    v15 = "RtlFormatCurrentUserKeyPath(UserProfilePath.GetMutablePointer())";
    RtlReportErrorOrigination(&v13, &GUID_44edceb3_7a6e_47e9_b787_5aa9dadfa4ab, (unsigned int)v10);
    Windows::Rtl::AutoString<_UNICODE_STRING,Windows::Auto<_UNICODE_STRING>>::~AutoString<_UNICODE_STRING,Windows::Auto<_UNICODE_STRING>>(&KeyPath);
    return (unsigned int)v10;
  }
  v10 = RtlDuplicateUnicodeStringToLUnicodeString(&KeyPath, &v13);
  if ( v10 < 0 )
  {
    Windows::Rtl::AutoString<_UNICODE_STRING,Windows::Auto<_UNICODE_STRING>>::~AutoString<_UNICODE_STRING,Windows::Auto<_UNICODE_STRING>>(&KeyPath);
    v11 = v14;
    goto LABEL_18;
  }
  Windows::Rtl::AutoString<_UNICODE_STRING,Windows::Auto<_UNICODE_STRING>>::~AutoString<_UNICODE_STRING,Windows::Auto<_UNICODE_STRING>>(&KeyPath);
  v10 = anonymous_namespace_::TryReplaceUpperCasePrefix(0, (_DWORD)a3, (_DWORD)v9, (unsigned int)&v13, (__int64)a4);
  v11 = v14;
  if ( v10 < 0 )
  {
LABEL_18:
    if ( v11 )
      anonymous_namespace_::OurRtlFreeStringRoutine(v11);
    return (unsigned int)v10;
  }
  if ( v14 )
    anonymous_namespace_::OurRtlFreeStringRoutine(v14);
LABEL_23:
  if ( !*(_QWORD *)a4 )
  {
    *(_QWORD *)&v13 = "onecore\\base\\lstring\\path.cpp";
    *((_QWORD *)&v13 + 1) = "RtlConvertWin32RegistryPathToNtRegistryPathUser";
    v14 = 141;
    v6 = "PathOut->Length != 0";
    goto LABEL_5;
  }
  return 0;
}

```

## disassembly

```asm
0x1800238e8  mov     rax, rsp
0x1800238eb  push    rbp
0x1800238ec  push    rdi
0x1800238ed  push    r14
0x1800238ef  lea     rbp, [rax-5Fh]
0x1800238f3  sub     rsp, 0B0h
0x1800238fa  mov     [rbp+57h+var_38], 0FFFFFFFFFFFFFFFEh
0x180023902  mov     [rax+8], rbx
0x180023906  mov     [rax+10h], rsi
0x18002390a  mov     rax, cs:__security_cookie
0x180023911  xor     rax, rsp
0x180023914  mov     [rbp+57h+var_20], rax
0x180023918  mov     rbx, r9
0x18002391b  mov     rsi, r8
0x18002391e  test    r9, r9
0x180023921  jz      short loc_18002392A
0x180023923  mov     qword ptr [r9], 0
0x18002392a  test    rsi, rsi
0x18002392d  jnz     short loc_180023978
0x18002392f  lea     rax, aOnecoreBaseLst; "onecore\\base\\lstring\\path.cpp"
0x180023936  mov     qword ptr [rbp+57h+var_88], rax
0x18002393a  lea     rax, aRtlconvertwin3_0; "RtlConvertWin32RegistryPathToNtRegistry"...
0x180023941  mov     qword ptr [rbp+57h+var_88+8], rax
0x180023945  mov     [rbp+57h+var_78], 57h ; 'W'
0x18002394d  lea     rax, aNotNullCheckFa_3; "Not-null check failed: PathIn"
0x180023954  mov     [rbp+57h+var_70], rax
0x180023958  mov     r8d, 0C000000Dh
0x18002395e  lea     rdx, _GUID_44edceb3_7a6e_47e9_b787_5aa9dadfa4ab
0x180023965  lea     rcx, [rbp+57h+var_88]
0x180023969  call    RtlReportErrorOrigination
0x18002396e  mov     eax, 0C000000Dh
0x180023973  jmp     loc_180023B21
0x180023978  test    rbx, rbx
0x18002397b  jnz     short loc_1800239A4
0x18002397d  lea     rax, aOnecoreBaseLst; "onecore\\base\\lstring\\path.cpp"
0x180023984  mov     qword ptr [rbp+57h+var_88], rax
0x180023988  lea     rax, aRtlconvertwin3_0; "RtlConvertWin32RegistryPathToNtRegistry"...
0x18002398f  mov     qword ptr [rbp+57h+var_88+8], rax
0x180023993  mov     [rbp+57h+var_78], 58h ; 'X'
0x18002399b  lea     rax, aNotNullCheckFa_0; "Not-null check failed: PathOut"
0x1800239a2  jmp     short loc_180023954
0x1800239a4  mov     [rbp+57h+var_68], 22h ; '"'
0x1800239ac  mov     [rbp+57h+var_60], 24h ; '$'
0x1800239b4  lea     rax, aHkeyCurrentUse; "HKEY_CURRENT_USER"
0x1800239bb  mov     [rbp+57h+var_58], rax
0x1800239bf  mov     [rbp+57h+var_50], 8
0x1800239c7  mov     [rbp+57h+var_48], 0Ah
0x1800239cf  lea     rax, aHkcu; "HKCU"
0x1800239d6  mov     [rbp+57h+var_40], rax
0x1800239da  mov     [rbp+57h+var_90], 0
0x1800239de  xor     edi, edi
0x1800239e0  movsxd  rax, edi
0x1800239e3  lea     rcx, [rax+rax*2]
0x1800239e7  lea     r14, [rbp+57h+var_68]
0x1800239eb  lea     r14, [r14+rcx*8]
0x1800239ef  lea     r9, [rbp+57h+var_90]
0x1800239f3  lea     r8, RtlUpcaseUCSCharacter
0x1800239fa  mov     rdx, r14
0x1800239fd  mov     rcx, rsi
0x180023a00  call    RtlEqualLUnicodeStringPrefix
0x180023a05  test    eax, eax
0x180023a07  js      loc_180023B21
0x180023a0d  cmp     [rbp+57h+var_90], 0
0x180023a11  jnz     short loc_180023A1F
0x180023a13  inc     edi
0x180023a15  cmp     edi, 2
0x180023a18  jb      short loc_1800239E0
0x180023a1a  jmp     loc_180023AEF
0x180023a1f  xorps   xmm0, xmm0
0x180023a22  xor     eax, eax
0x180023a24  movups  [rbp+57h+var_88], xmm0
0x180023a28  mov     [rbp+57h+var_78], rax
0x180023a2c  movups  xmmword ptr [rbp+57h+KeyPath.Length], xmm0
0x180023a30  lea     rcx, [rbp+57h+KeyPath]; KeyPath
0x180023a34  call    cs:__imp_RtlFormatCurrentUserKeyPath
0x180023a3a  mov     edi, eax
0x180023a3c  test    eax, eax
0x180023a3e  jns     short loc_180023A8E
0x180023a40  lea     rax, aOnecoreBaseLst; "onecore\\base\\lstring\\path.cpp"
0x180023a47  mov     qword ptr [rbp+57h+var_88], rax
0x180023a4b  lea     rax, aRtlconvertwin3_0; "RtlConvertWin32RegistryPathToNtRegistry"...
0x180023a52  mov     qword ptr [rbp+57h+var_88+8], rax
0x180023a56  mov     [rbp+57h+var_78], 71h ; 'q'
0x180023a5e  lea     rax, aRtlformatcurre; "RtlFormatCurrentUserKeyPath(UserProfile"...
0x180023a65  mov     [rbp+57h+var_70], rax
0x180023a69  mov     r8d, edi
0x180023a6c  lea     rdx, _GUID_44edceb3_7a6e_47e9_b787_5aa9dadfa4ab
0x180023a73  lea     rcx, [rbp+57h+var_88]
0x180023a77  call    RtlReportErrorOrigination
0x180023a7c  nop
0x180023a7d  lea     rcx, [rbp+57h+KeyPath]
0x180023a81  call    ??1?$AutoString@U_UNICODE_STRING@@V?$Auto@U_UNICODE_STRING@@@Windows@@@Rtl@Windows@@QEAA@XZ; Windows::Rtl::AutoString<_UNICODE_STRING,Windows::Auto<_UNICODE_STRING>>::~AutoString<_UNICODE_STRING,Windows::Auto<_UNICODE_STRING>>(void)
0x180023a86  nop
0x180023a87  mov     eax, edi
0x180023a89  jmp     loc_180023B21
0x180023a8e  lea     rdx, [rbp+57h+var_88]
0x180023a92  lea     rcx, [rbp+57h+KeyPath]
0x180023a96  call    RtlDuplicateUnicodeStringToLUnicodeString
0x180023a9b  mov     edi, eax
0x180023a9d  test    eax, eax
0x180023a9f  jns     short loc_180023ABB
0x180023aa1  lea     rcx, [rbp+57h+KeyPath]
0x180023aa5  call    ??1?$AutoString@U_UNICODE_STRING@@V?$Auto@U_UNICODE_STRING@@@Windows@@@Rtl@Windows@@QEAA@XZ; Windows::Rtl::AutoString<_UNICODE_STRING,Windows::Auto<_UNICODE_STRING>>::~AutoString<_UNICODE_STRING,Windows::Auto<_UNICODE_STRING>>(void)
0x180023aaa  nop
0x180023aab  mov     rcx, [rbp+57h+var_78]
0x180023aaf  test    rcx, rcx
0x180023ab2  jz      short loc_180023A87
0x180023ab4  call    _anonymous_namespace___OurRtlFreeStringRoutine
0x180023ab9  jmp     short loc_180023A87
0x180023abb  lea     rcx, [rbp+57h+KeyPath]
0x180023abf  call    ??1?$AutoString@U_UNICODE_STRING@@V?$Auto@U_UNICODE_STRING@@@Windows@@@Rtl@Windows@@QEAA@XZ; Windows::Rtl::AutoString<_UNICODE_STRING,Windows::Auto<_UNICODE_STRING>>::~AutoString<_UNICODE_STRING,Windows::Auto<_UNICODE_STRING>>(void)
0x180023ac4  nop
0x180023ac5  mov     [rsp+0C0h+var_A0], rbx
0x180023aca  lea     r9, [rbp+57h+var_88]
0x180023ace  mov     r8, r14
0x180023ad1  mov     rdx, rsi
0x180023ad4  xor     ecx, ecx
0x180023ad6  call    _anonymous_namespace___TryReplaceUpperCasePrefix
0x180023adb  mov     edi, eax
0x180023add  mov     rcx, [rbp+57h+var_78]
0x180023ae1  test    eax, eax
0x180023ae3  js      short loc_180023AAF
0x180023ae5  test    rcx, rcx
0x180023ae8  jz      short loc_180023AEF
0x180023aea  call    _anonymous_namespace___OurRtlFreeStringRoutine
0x180023aef  cmp     qword ptr [rbx], 0
0x180023af3  jnz     short loc_180023B1F
0x180023af5  lea     rax, aOnecoreBaseLst; "onecore\\base\\lstring\\path.cpp"
0x180023afc  mov     qword ptr [rbp+57h+var_88], rax
0x180023b00  lea     rax, aRtlconvertwin3_0; "RtlConvertWin32RegistryPathToNtRegistry"...
0x180023b07  mov     qword ptr [rbp+57h+var_88+8], rax
0x180023b0b  mov     [rbp+57h+var_78], 8Dh
0x180023b13  lea     rax, aPathoutLength0; "PathOut->Length != 0"
0x180023b1a  jmp     loc_180023954
0x180023b1f  xor     eax, eax
0x180023b21  mov     rcx, [rbp+57h+var_20]
0x180023b25  xor     rcx, rsp; StackCookie
0x180023b28  call    __security_check_cookie
0x180023b2d  lea     r11, [rsp+0C0h+var_10]
0x180023b35  mov     rbx, [r11+20h]
0x180023b39  mov     rsi, [r11+28h]
0x180023b3d  mov     rsp, r11
0x180023b40  pop     r14
0x180023b42  pop     rdi
0x180023b43  pop     rbp
0x180023b44  retn
```
