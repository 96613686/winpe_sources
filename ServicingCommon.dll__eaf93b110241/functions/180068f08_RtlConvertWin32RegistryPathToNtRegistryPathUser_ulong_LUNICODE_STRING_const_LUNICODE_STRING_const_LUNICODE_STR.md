# RtlConvertWin32RegistryPathToNtRegistryPathUser(ulong,_LUNICODE_STRING const *,_LUNICODE_STRING const *,_LUNICODE_STRING *)

- ea: `0x180068f08`
- end: `0x18006914e`
- name: `?RtlConvertWin32RegistryPathToNtRegistryPathUser@@YAJKPEBU_LUNICODE_STRING@@0PEAU1@@Z`
- size: `582`
- prototype: `__int64 __fastcall(unsigned int, const struct _LUNICODE_STRING *, const struct _LUNICODE_STRING *, struct _LUNICODE_STRING *)`
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config, loader_planting`

## callers

- `0x180069e44`

## callees

- `0x180002564`
- `0x180006010`
- `0x18001f4ac`
- `0x18001f5d4`
- `0x1800293a0`
- `0x180066520`
- `0x180068edc`
- `0x180068f08`
- `0x180069154`

## import_xrefs

- `ntdll!RtlFormatCurrentUserKeyPath` at `0x180069045`
- `ntdll!RtlFormatCurrentUserKeyPath` at `0x180069045`

## string_xrefs

- `0x180068f4e`: `onecore\base\lstring\path.cpp`
- `0x180068f8e`: `onecore\base\lstring\path.cpp`
- `0x180069058`: `onecore\base\lstring\path.cpp`
- `0x1800690ef`: `onecore\base\lstring\path.cpp`
- `0x180068f61`: `RtlConvertWin32RegistryPathToNtRegistryPathUser`
- `0x180068fa1`: `RtlConvertWin32RegistryPathToNtRegistryPathUser`
- `0x18006906f`: `RtlConvertWin32RegistryPathToNtRegistryPathUser`
- `0x180069106`: `RtlConvertWin32RegistryPathToNtRegistryPathUser`
- `0x180068f6c`: `Not-null check failed: PathIn`
- `0x180068fac`: `Not-null check failed: PathOut`
- `0x18006907e`: `RtlFormatCurrentUserKeyPath(UserProfilePath.GetMutablePointer())`
- `0x180069115`: `PathOut->Length != 0`

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
  NTSTATUS v9; // eax
  int v10; // eax
  unsigned int v11; // ebx
  int v12; // eax
  _BYTE v13[8]; // [rsp+30h] [rbp-39h] BYREF
  __int128 v14; // [rsp+38h] [rbp-31h] BYREF
  __int64 v15; // [rsp+48h] [rbp-21h]
  const char *v16; // [rsp+50h] [rbp-19h]
  __int64 v17; // [rsp+58h] [rbp-11h] BYREF
  __int64 v18; // [rsp+60h] [rbp-9h]
  __int64 v19; // [rsp+68h] [rbp-1h]
  const char *v20; // [rsp+70h] [rbp+7h]
  __int64 v21; // [rsp+78h] [rbp+Fh]
  const wchar_t *v22; // [rsp+80h] [rbp+17h]
  int v23; // [rsp+88h] [rbp+1Fh] BYREF
  struct _UNICODE_STRING KeyPath; // [rsp+90h] [rbp+27h] BYREF

  v23 = 0;
  if ( a4 )
    *(_QWORD *)a4 = 0;
  if ( !a3 )
  {
    v15 = 87;
    *(_QWORD *)&v14 = "onecore\\base\\lstring\\path.cpp";
    *((_QWORD *)&v14 + 1) = "RtlConvertWin32RegistryPathToNtRegistryPathUser";
    v6 = "Not-null check failed: PathIn";
LABEL_5:
    v16 = v6;
    return Windows::ErrorHandling::Rtl::CBaseFrame<Windows::ErrorHandling::Rtl::CSimpleNtStatusCarryingFrame,long>::OriginateInvalidParameter_NullPointer(
             &v23,
             &v14);
  }
  if ( !a4 )
  {
    v15 = 88;
    *(_QWORD *)&v14 = "onecore\\base\\lstring\\path.cpp";
    *((_QWORD *)&v14 + 1) = "RtlConvertWin32RegistryPathToNtRegistryPathUser";
    v6 = "Not-null check failed: PathOut";
    goto LABEL_5;
  }
  v17 = 34;
  v19 = (__int64)L"HKEY_CURRENT_USER";
  v8 = 0;
  v18 = 36;
  v22 = L"HKCU";
  v20 = (const char *)8;
  v21 = 10;
  v13[0] = 0;
  while ( 1 )
  {
    result = RtlEqualLUnicodeStringPrefix(a3, &v17 + 3 * v8, RtlUpcaseUCSCharacter, v13);
    if ( (int)result < 0 )
      return result;
    if ( v13[0] )
      break;
    if ( (unsigned int)++v8 >= 2 )
      goto LABEL_21;
  }
  v14 = 0;
  v15 = 0;
  KeyPath = 0;
  v9 = RtlFormatCurrentUserKeyPath(&KeyPath);
  if ( v9 < 0 )
  {
    v19 = 113;
    v17 = (__int64)"onecore\\base\\lstring\\path.cpp";
    v18 = (__int64)"RtlConvertWin32RegistryPathToNtRegistryPathUser";
    v20 = "RtlFormatCurrentUserKeyPath(UserProfilePath.GetMutablePointer())";
    v10 = Windows::ErrorHandling::Rtl::CBaseFrame<Windows::ErrorHandling::Rtl::CSimpleNtStatusCarryingFrame,long>::OriginateNtStatus(
            &v23,
            &v17,
            (unsigned int)v9);
LABEL_16:
    v11 = v10;
    Windows::Rtl::AutoString<_UNICODE_STRING,Windows::Auto<_UNICODE_STRING>>::Close(&KeyPath);
LABEL_19:
    Windows::Rtl::AutoString<_LUTF8_STRING,Windows::Auto<_LUTF8_STRING>>::Close(&v14);
    return v11;
  }
  v10 = RtlDuplicateUnicodeStringToLUnicodeString(&KeyPath, &v14, (unsigned int)v9);
  if ( v10 < 0 )
    goto LABEL_16;
  Windows::Rtl::AutoString<_UNICODE_STRING,Windows::Auto<_UNICODE_STRING>>::Close(&KeyPath);
  v12 = anonymous_namespace_::TryReplaceUpperCasePrefix(
          0,
          (_DWORD)a3,
          (unsigned int)(&v17 + 3 * v8),
          (unsigned int)&v14,
          (__int64)a4);
  if ( v12 < 0 )
  {
    v11 = v12;
    goto LABEL_19;
  }
  Windows::Rtl::AutoString<_LUTF8_STRING,Windows::Auto<_LUTF8_STRING>>::Close(&v14);
LABEL_21:
  if ( *(_QWORD *)a4 )
    return 0;
  v19 = 141;
  v17 = (__int64)"onecore\\base\\lstring\\path.cpp";
  v18 = (__int64)"RtlConvertWin32RegistryPathToNtRegistryPathUser";
  v20 = "PathOut->Length != 0";
  return Windows::ErrorHandling::Rtl::CBaseFrame<Windows::ErrorHandling::Rtl::CSimpleNtStatusCarryingFrame,long>::OriginateInvalidParameter_NullPointer(
           &v23,
           &v17);
}

```

## disassembly

```asm
0x180068f08  mov     [rsp-8+arg_0], rbx
0x180068f0d  mov     [rsp-8+arg_8], rsi
0x180068f12  push    rbp
0x180068f13  push    rdi
0x180068f14  push    r14
0x180068f16  lea     rbp, [rsp-47h]
0x180068f1b  sub     rsp, 0B0h
0x180068f22  mov     rax, cs:__security_cookie
0x180068f29  xor     rax, rsp
0x180068f2c  mov     [rbp+57h+var_20], rax
0x180068f30  mov     [rbp+57h+var_38], 0
0x180068f37  mov     rbx, r9
0x180068f3a  mov     rsi, r8
0x180068f3d  test    r9, r9
0x180068f40  jz      short loc_180068F49
0x180068f42  mov     qword ptr [r9], 0
0x180068f49  test    rsi, rsi
0x180068f4c  jnz     short loc_180068F89
0x180068f4e  lea     rax, aOnecoreBaseLst; "onecore\\base\\lstring\\path.cpp"
0x180068f55  mov     [rbp+57h+var_78], 57h ; 'W'
0x180068f5d  mov     qword ptr [rbp+57h+var_88], rax
0x180068f61  lea     rax, aRtlconvertwin3_2; "RtlConvertWin32RegistryPathToNtRegistry"...
0x180068f68  mov     qword ptr [rbp+57h+var_88+8], rax
0x180068f6c  lea     rax, aNotNullCheckFa_33; "Not-null check failed: PathIn"
0x180068f73  lea     rdx, [rbp+57h+var_88]
0x180068f77  mov     [rbp+57h+var_70], rax
0x180068f7b  lea     rcx, [rbp+57h+var_38]
0x180068f7f  call    ?OriginateInvalidParameter_NullPointer@?$CBaseFrame@UCSimpleNtStatusCarryingFrame@Rtl@ErrorHandling@Windows@@J@Rtl@ErrorHandling@Windows@@QEAAJAEBU_RTL_CALL_SITE@34@@Z; Windows::ErrorHandling::Rtl::CBaseFrame<Windows::ErrorHandling::Rtl::CSimpleNtStatusCarryingFrame,long>::OriginateInvalidParameter_NullPointer(Windows::ErrorHandling::_RTL_CALL_SITE const &)
0x180068f84  jmp     loc_180069129
0x180068f89  test    rbx, rbx
0x180068f8c  jnz     short loc_180068FB5
0x180068f8e  lea     rax, aOnecoreBaseLst; "onecore\\base\\lstring\\path.cpp"
0x180068f95  mov     [rbp+57h+var_78], 58h ; 'X'
0x180068f9d  mov     qword ptr [rbp+57h+var_88], rax
0x180068fa1  lea     rax, aRtlconvertwin3_2; "RtlConvertWin32RegistryPathToNtRegistry"...
0x180068fa8  mov     qword ptr [rbp+57h+var_88+8], rax
0x180068fac  lea     rax, aNotNullCheckFa_9; "Not-null check failed: PathOut"
0x180068fb3  jmp     short loc_180068F73
0x180068fb5  lea     rax, aHkeyCurrentUse; "HKEY_CURRENT_USER"
0x180068fbc  mov     [rbp+57h+var_68], 22h ; '"'
0x180068fc4  mov     [rbp+57h+var_58], rax
0x180068fc8  xor     edi, edi
0x180068fca  lea     rax, aHkcu; "HKCU"
0x180068fd1  mov     [rbp+57h+var_60], 24h ; '$'
0x180068fd9  mov     [rbp+57h+var_40], rax
0x180068fdd  mov     [rbp+57h+var_50], 8
0x180068fe5  mov     [rbp+57h+var_48], 0Ah
0x180068fed  mov     [rbp+57h+var_90], 0
0x180068ff1  movsxd  rax, edi
0x180068ff4  lea     r14, [rbp+57h+var_68]
0x180068ff8  lea     r9, [rbp+57h+var_90]
0x180068ffc  lea     r8, RtlUpcaseUCSCharacter
0x180069003  lea     rcx, [rax+rax*2]
0x180069007  lea     r14, [r14+rcx*8]
0x18006900b  mov     rcx, rsi
0x18006900e  mov     rdx, r14
0x180069011  call    RtlEqualLUnicodeStringPrefix
0x180069016  test    eax, eax
0x180069018  js      loc_180069129
0x18006901e  cmp     [rbp+57h+var_90], 0
0x180069022  jnz     short loc_180069030
0x180069024  inc     edi
0x180069026  cmp     edi, 2
0x180069029  jb      short loc_180068FF1
0x18006902b  jmp     loc_1800690E9
0x180069030  xorps   xmm0, xmm0
0x180069033  lea     rcx, [rbp+57h+KeyPath]; KeyPath
0x180069037  xor     eax, eax
0x180069039  movups  [rbp+57h+var_88], xmm0
0x18006903d  mov     [rbp+57h+var_78], rax
0x180069041  movups  xmmword ptr [rbp+57h+KeyPath.Length], xmm0
0x180069045  call    cs:__imp_RtlFormatCurrentUserKeyPath
0x18006904c  nop     dword ptr [rax+rax+00h]
0x180069051  mov     r8d, eax
0x180069054  test    eax, eax
0x180069056  jns     short loc_180069090
0x180069058  lea     rax, aOnecoreBaseLst; "onecore\\base\\lstring\\path.cpp"
0x18006905f  mov     [rbp+57h+var_58], 71h ; 'q'
0x180069067  mov     [rbp+57h+var_68], rax
0x18006906b  lea     rdx, [rbp+57h+var_68]
0x18006906f  lea     rax, aRtlconvertwin3_2; "RtlConvertWin32RegistryPathToNtRegistry"...
0x180069076  mov     [rbp+57h+var_60], rax
0x18006907a  lea     rcx, [rbp+57h+var_38]
0x18006907e  lea     rax, aRtlformatcurre; "RtlFormatCurrentUserKeyPath(UserProfile"...
0x180069085  mov     [rbp+57h+var_50], rax
0x180069089  call    ?OriginateNtStatus@?$CBaseFrame@UCSimpleNtStatusCarryingFrame@Rtl@ErrorHandling@Windows@@J@Rtl@ErrorHandling@Windows@@QEAAJAEBU_RTL_CALL_SITE@34@J@Z; Windows::ErrorHandling::Rtl::CBaseFrame<Windows::ErrorHandling::Rtl::CSimpleNtStatusCarryingFrame,long>::OriginateNtStatus(Windows::ErrorHandling::_RTL_CALL_SITE const &,long)
0x18006908e  jmp     short loc_1800690A1
0x180069090  lea     rdx, [rbp+57h+var_88]
0x180069094  lea     rcx, [rbp+57h+KeyPath]
0x180069098  call    RtlDuplicateUnicodeStringToLUnicodeString
0x18006909d  test    eax, eax
0x18006909f  jns     short loc_1800690AE
0x1800690a1  lea     rcx, [rbp+57h+KeyPath]
0x1800690a5  mov     ebx, eax
0x1800690a7  call    ?Close@?$AutoString@U_UNICODE_STRING@@V?$Auto@U_UNICODE_STRING@@@Windows@@@Rtl@Windows@@QEAAXXZ; Windows::Rtl::AutoString<_UNICODE_STRING,Windows::Auto<_UNICODE_STRING>>::Close(void)
0x1800690ac  jmp     short loc_1800690D3
0x1800690ae  lea     rcx, [rbp+57h+KeyPath]
0x1800690b2  call    ?Close@?$AutoString@U_UNICODE_STRING@@V?$Auto@U_UNICODE_STRING@@@Windows@@@Rtl@Windows@@QEAAXXZ; Windows::Rtl::AutoString<_UNICODE_STRING,Windows::Auto<_UNICODE_STRING>>::Close(void)
0x1800690b7  lea     r9, [rbp+57h+var_88]
0x1800690bb  mov     [rsp+0C0h+var_A0], rbx
0x1800690c0  mov     r8, r14
0x1800690c3  mov     rdx, rsi
0x1800690c6  xor     ecx, ecx
0x1800690c8  call    _anonymous_namespace___TryReplaceUpperCasePrefix
0x1800690cd  test    eax, eax
0x1800690cf  jns     short loc_1800690E0
0x1800690d1  mov     ebx, eax
0x1800690d3  lea     rcx, [rbp+57h+var_88]
0x1800690d7  call    ?Close@?$AutoString@U_LUTF8_STRING@@V?$Auto@U_LUTF8_STRING@@@Windows@@@Rtl@Windows@@QEAAXXZ; Windows::Rtl::AutoString<_LUTF8_STRING,Windows::Auto<_LUTF8_STRING>>::Close(void)
0x1800690dc  mov     eax, ebx
0x1800690de  jmp     short loc_180069129
0x1800690e0  lea     rcx, [rbp+57h+var_88]
0x1800690e4  call    ?Close@?$AutoString@U_LUTF8_STRING@@V?$Auto@U_LUTF8_STRING@@@Windows@@@Rtl@Windows@@QEAAXXZ; Windows::Rtl::AutoString<_LUTF8_STRING,Windows::Auto<_LUTF8_STRING>>::Close(void)
0x1800690e9  cmp     qword ptr [rbx], 0
0x1800690ed  jnz     short loc_180069127
0x1800690ef  lea     rax, aOnecoreBaseLst; "onecore\\base\\lstring\\path.cpp"
0x1800690f6  mov     [rbp+57h+var_58], 8Dh
0x1800690fe  mov     [rbp+57h+var_68], rax
0x180069102  lea     rdx, [rbp+57h+var_68]
0x180069106  lea     rax, aRtlconvertwin3_2; "RtlConvertWin32RegistryPathToNtRegistry"...
0x18006910d  mov     [rbp+57h+var_60], rax
0x180069111  lea     rcx, [rbp+57h+var_38]
0x180069115  lea     rax, aPathoutLength0; "PathOut->Length != 0"
0x18006911c  mov     [rbp+57h+var_50], rax
0x180069120  call    ?OriginateInvalidParameter_NullPointer@?$CBaseFrame@UCSimpleNtStatusCarryingFrame@Rtl@ErrorHandling@Windows@@J@Rtl@ErrorHandling@Windows@@QEAAJAEBU_RTL_CALL_SITE@34@@Z; Windows::ErrorHandling::Rtl::CBaseFrame<Windows::ErrorHandling::Rtl::CSimpleNtStatusCarryingFrame,long>::OriginateInvalidParameter_NullPointer(Windows::ErrorHandling::_RTL_CALL_SITE const &)
0x180069125  jmp     short loc_180069129
0x180069127  xor     eax, eax
0x180069129  mov     rcx, [rbp+57h+var_20]
0x18006912d  xor     rcx, rsp; StackCookie
0x180069130  call    __security_check_cookie
0x180069135  lea     r11, [rsp+0C0h+var_10]
0x18006913d  mov     rbx, [r11+20h]
0x180069141  mov     rsi, [r11+28h]
0x180069145  mov     rsp, r11
0x180069148  pop     r14
0x18006914a  pop     rdi
0x18006914b  pop     rbp
0x18006914c  retn
```
