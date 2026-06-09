# RtlConvertWin32RegistryPathToNtRegistryPathUser(ulong,_LUNICODE_STRING const *,_LUNICODE_STRING const *,_LUNICODE_STRING *)

- ea: `0x180069338`
- end: `0x180069580`
- name: `?RtlConvertWin32RegistryPathToNtRegistryPathUser@@YAJKPEBU_LUNICODE_STRING@@0PEAU1@@Z`
- size: `584`
- prototype: `__int64 __fastcall(unsigned int, const struct _LUNICODE_STRING *, const struct _LUNICODE_STRING *, struct _LUNICODE_STRING *)`
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config, loader_planting`

## callers

- `0x18006a284`

## callees

- `0x180004a8c`
- `0x180018e30`
- `0x18001f1d8`
- `0x18001f840`
- `0x18002d2b0`
- `0x180066bd0`
- `0x18006930c`
- `0x180069338`
- `0x180069588`

## import_xrefs

- `ntdll!RtlFormatCurrentUserKeyPath` at `0x180069477`
- `ntdll!RtlFormatCurrentUserKeyPath` at `0x180069477`

## string_xrefs

- `0x18006937e`: `onecore\base\lstring\path.cpp`
- `0x1800693be`: `onecore\base\lstring\path.cpp`
- `0x18006948a`: `onecore\base\lstring\path.cpp`
- `0x180069521`: `onecore\base\lstring\path.cpp`
- `0x180069391`: `RtlConvertWin32RegistryPathToNtRegistryPathUser`
- `0x1800693d1`: `RtlConvertWin32RegistryPathToNtRegistryPathUser`
- `0x1800694a1`: `RtlConvertWin32RegistryPathToNtRegistryPathUser`
- `0x180069538`: `RtlConvertWin32RegistryPathToNtRegistryPathUser`
- `0x18006939c`: `Not-null check failed: PathIn`
- `0x1800693dc`: `Not-null check failed: PathOut`
- `0x1800694b0`: `RtlFormatCurrentUserKeyPath(UserProfilePath.GetMutablePointer())`
- `0x180069547`: `PathOut->Length != 0`

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
  __int64 *v9; // r14
  NTSTATUS v10; // eax
  int v11; // eax
  unsigned int v12; // ebx
  int v13; // eax
  _BYTE v14[8]; // [rsp+30h] [rbp-39h] BYREF
  __int128 v15; // [rsp+38h] [rbp-31h] BYREF
  __int64 v16; // [rsp+48h] [rbp-21h]
  const char *v17; // [rsp+50h] [rbp-19h]
  __int64 v18; // [rsp+58h] [rbp-11h] BYREF
  __int64 v19; // [rsp+60h] [rbp-9h]
  __int64 v20; // [rsp+68h] [rbp-1h]
  const char *v21; // [rsp+70h] [rbp+7h]
  __int64 v22; // [rsp+78h] [rbp+Fh]
  const wchar_t *v23; // [rsp+80h] [rbp+17h]
  int v24; // [rsp+88h] [rbp+1Fh] BYREF
  struct _UNICODE_STRING KeyPath; // [rsp+90h] [rbp+27h] BYREF

  v24 = 0;
  if ( a4 )
    *(_QWORD *)a4 = 0;
  if ( !a3 )
  {
    v16 = 87;
    *(_QWORD *)&v15 = "onecore\\base\\lstring\\path.cpp";
    *((_QWORD *)&v15 + 1) = "RtlConvertWin32RegistryPathToNtRegistryPathUser";
    v6 = "Not-null check failed: PathIn";
LABEL_5:
    v17 = v6;
    return Windows::ErrorHandling::Rtl::CBaseFrame<Windows::ErrorHandling::Rtl::CSimpleNtStatusCarryingFrame,long>::OriginateInvalidParameter_NullPointer(
             &v24,
             &v15);
  }
  if ( !a4 )
  {
    v16 = 88;
    *(_QWORD *)&v15 = "onecore\\base\\lstring\\path.cpp";
    *((_QWORD *)&v15 + 1) = "RtlConvertWin32RegistryPathToNtRegistryPathUser";
    v6 = "Not-null check failed: PathOut";
    goto LABEL_5;
  }
  v18 = 34;
  v20 = (__int64)L"HKEY_CURRENT_USER";
  v8 = 0;
  v19 = 36;
  v23 = L"HKCU";
  v21 = (const char *)8;
  v22 = 10;
  v14[0] = 0;
  while ( 1 )
  {
    if ( (unsigned __int64)v8 >= 2 )
      goto LABEL_21;
    v9 = &v18 + 3 * v8;
    result = RtlEqualLUnicodeStringPrefix(a3, v9, RtlUpcaseUCSCharacter, v14);
    if ( (int)result < 0 )
      return result;
    if ( v14[0] )
      break;
    ++v8;
  }
  v15 = 0;
  v16 = 0;
  KeyPath = 0;
  v10 = RtlFormatCurrentUserKeyPath(&KeyPath);
  if ( v10 < 0 )
  {
    v20 = 113;
    v18 = (__int64)"onecore\\base\\lstring\\path.cpp";
    v19 = (__int64)"RtlConvertWin32RegistryPathToNtRegistryPathUser";
    v21 = "RtlFormatCurrentUserKeyPath(UserProfilePath.GetMutablePointer())";
    v11 = Windows::ErrorHandling::Rtl::CBaseFrame<Windows::ErrorHandling::Rtl::CSimpleNtStatusCarryingFrame,long>::OriginateNtStatus(
            &v24,
            &v18,
            (unsigned int)v10);
LABEL_16:
    v12 = v11;
    Windows::Rtl::AutoString<_UNICODE_STRING,Windows::Auto<_UNICODE_STRING>>::Close(&KeyPath);
LABEL_19:
    Windows::Rtl::AutoString<_LUTF8_STRING,Windows::Auto<_LUTF8_STRING>>::Close(&v15);
    return v12;
  }
  v11 = RtlDuplicateUnicodeStringToLUnicodeString(&KeyPath, &v15, (unsigned int)v10);
  if ( v11 < 0 )
    goto LABEL_16;
  Windows::Rtl::AutoString<_UNICODE_STRING,Windows::Auto<_UNICODE_STRING>>::Close(&KeyPath);
  v13 = anonymous_namespace_::TryReplaceUpperCasePrefix(0, (_DWORD)a3, (_DWORD)v9, (unsigned int)&v15, (__int64)a4);
  if ( v13 < 0 )
  {
    v12 = v13;
    goto LABEL_19;
  }
  Windows::Rtl::AutoString<_LUTF8_STRING,Windows::Auto<_LUTF8_STRING>>::Close(&v15);
LABEL_21:
  if ( *(_QWORD *)a4 )
    return 0;
  v20 = 141;
  v18 = (__int64)"onecore\\base\\lstring\\path.cpp";
  v19 = (__int64)"RtlConvertWin32RegistryPathToNtRegistryPathUser";
  v21 = "PathOut->Length != 0";
  return Windows::ErrorHandling::Rtl::CBaseFrame<Windows::ErrorHandling::Rtl::CSimpleNtStatusCarryingFrame,long>::OriginateInvalidParameter_NullPointer(
           &v24,
           &v18);
}

```

## disassembly

```asm
0x180069338  mov     [rsp-8+arg_0], rbx
0x18006933d  mov     [rsp-8+arg_8], rsi
0x180069342  push    rbp
0x180069343  push    rdi
0x180069344  push    r14
0x180069346  lea     rbp, [rsp-47h]
0x18006934b  sub     rsp, 0B0h
0x180069352  mov     rax, cs:__security_cookie
0x180069359  xor     rax, rsp
0x18006935c  mov     [rbp+57h+var_20], rax
0x180069360  mov     [rbp+57h+var_38], 0
0x180069367  mov     rbx, r9
0x18006936a  mov     rsi, r8
0x18006936d  test    r9, r9
0x180069370  jz      short loc_180069379
0x180069372  mov     qword ptr [r9], 0
0x180069379  test    rsi, rsi
0x18006937c  jnz     short loc_1800693B9
0x18006937e  lea     rax, aOnecoreBaseLst; "onecore\\base\\lstring\\path.cpp"
0x180069385  mov     [rbp+57h+var_78], 57h ; 'W'
0x18006938d  mov     qword ptr [rbp+57h+var_88], rax
0x180069391  lea     rax, aRtlconvertwin3_2; "RtlConvertWin32RegistryPathToNtRegistry"...
0x180069398  mov     qword ptr [rbp+57h+var_88+8], rax
0x18006939c  lea     rax, aNotNullCheckFa_33; "Not-null check failed: PathIn"
0x1800693a3  lea     rdx, [rbp+57h+var_88]
0x1800693a7  mov     [rbp+57h+var_70], rax
0x1800693ab  lea     rcx, [rbp+57h+var_38]
0x1800693af  call    ?OriginateInvalidParameter_NullPointer@?$CBaseFrame@UCSimpleNtStatusCarryingFrame@Rtl@ErrorHandling@Windows@@J@Rtl@ErrorHandling@Windows@@QEAAJAEBU_RTL_CALL_SITE@34@@Z; Windows::ErrorHandling::Rtl::CBaseFrame<Windows::ErrorHandling::Rtl::CSimpleNtStatusCarryingFrame,long>::OriginateInvalidParameter_NullPointer(Windows::ErrorHandling::_RTL_CALL_SITE const &)
0x1800693b4  jmp     loc_18006955B
0x1800693b9  test    rbx, rbx
0x1800693bc  jnz     short loc_1800693E5
0x1800693be  lea     rax, aOnecoreBaseLst; "onecore\\base\\lstring\\path.cpp"
0x1800693c5  mov     [rbp+57h+var_78], 58h ; 'X'
0x1800693cd  mov     qword ptr [rbp+57h+var_88], rax
0x1800693d1  lea     rax, aRtlconvertwin3_2; "RtlConvertWin32RegistryPathToNtRegistry"...
0x1800693d8  mov     qword ptr [rbp+57h+var_88+8], rax
0x1800693dc  lea     rax, aNotNullCheckFa_9; "Not-null check failed: PathOut"
0x1800693e3  jmp     short loc_1800693A3
0x1800693e5  lea     rax, aHkeyCurrentUse; "HKEY_CURRENT_USER"
0x1800693ec  mov     [rbp+57h+var_68], 22h ; '"'
0x1800693f4  mov     [rbp+57h+var_58], rax
0x1800693f8  xor     edi, edi
0x1800693fa  lea     rax, aHkcu; "HKCU"
0x180069401  mov     [rbp+57h+var_60], 24h ; '$'
0x180069409  mov     [rbp+57h+var_40], rax
0x18006940d  mov     [rbp+57h+var_50], 8
0x180069415  mov     [rbp+57h+var_48], 0Ah
0x18006941d  mov     [rbp+57h+var_90], 0
0x180069421  movsxd  rax, edi
0x180069424  cmp     rax, 2
0x180069428  jnb     loc_18006951B
0x18006942e  lea     rax, [rax+rax*2]
0x180069432  mov     rcx, rsi
0x180069435  lea     r14, [rbp+57h+var_68]
0x180069439  lea     r14, [r14+rax*8]
0x18006943d  mov     rdx, r14
0x180069440  lea     r9, [rbp+57h+var_90]
0x180069444  lea     r8, RtlUpcaseUCSCharacter
0x18006944b  call    RtlEqualLUnicodeStringPrefix
0x180069450  test    eax, eax
0x180069452  js      loc_18006955B
0x180069458  cmp     [rbp+57h+var_90], 0
0x18006945c  jnz     short loc_180069462
0x18006945e  inc     edi
0x180069460  jmp     short loc_180069421
0x180069462  xorps   xmm0, xmm0
0x180069465  lea     rcx, [rbp+57h+KeyPath]; KeyPath
0x180069469  xor     eax, eax
0x18006946b  movups  [rbp+57h+var_88], xmm0
0x18006946f  mov     [rbp+57h+var_78], rax
0x180069473  movups  xmmword ptr [rbp+57h+KeyPath.Length], xmm0
0x180069477  call    cs:__imp_RtlFormatCurrentUserKeyPath
0x18006947e  nop     dword ptr [rax+rax+00h]
0x180069483  mov     r8d, eax
0x180069486  test    eax, eax
0x180069488  jns     short loc_1800694C2
0x18006948a  lea     rax, aOnecoreBaseLst; "onecore\\base\\lstring\\path.cpp"
0x180069491  mov     [rbp+57h+var_58], 71h ; 'q'
0x180069499  mov     [rbp+57h+var_68], rax
0x18006949d  lea     rdx, [rbp+57h+var_68]
0x1800694a1  lea     rax, aRtlconvertwin3_2; "RtlConvertWin32RegistryPathToNtRegistry"...
0x1800694a8  mov     [rbp+57h+var_60], rax
0x1800694ac  lea     rcx, [rbp+57h+var_38]
0x1800694b0  lea     rax, aRtlformatcurre; "RtlFormatCurrentUserKeyPath(UserProfile"...
0x1800694b7  mov     [rbp+57h+var_50], rax
0x1800694bb  call    ?OriginateNtStatus@?$CBaseFrame@UCSimpleNtStatusCarryingFrame@Rtl@ErrorHandling@Windows@@J@Rtl@ErrorHandling@Windows@@QEAAJAEBU_RTL_CALL_SITE@34@J@Z; Windows::ErrorHandling::Rtl::CBaseFrame<Windows::ErrorHandling::Rtl::CSimpleNtStatusCarryingFrame,long>::OriginateNtStatus(Windows::ErrorHandling::_RTL_CALL_SITE const &,long)
0x1800694c0  jmp     short loc_1800694D3
0x1800694c2  lea     rdx, [rbp+57h+var_88]
0x1800694c6  lea     rcx, [rbp+57h+KeyPath]
0x1800694ca  call    RtlDuplicateUnicodeStringToLUnicodeString
0x1800694cf  test    eax, eax
0x1800694d1  jns     short loc_1800694E0
0x1800694d3  lea     rcx, [rbp+57h+KeyPath]
0x1800694d7  mov     ebx, eax
0x1800694d9  call    ?Close@?$AutoString@U_UNICODE_STRING@@V?$Auto@U_UNICODE_STRING@@@Windows@@@Rtl@Windows@@QEAAXXZ; Windows::Rtl::AutoString<_UNICODE_STRING,Windows::Auto<_UNICODE_STRING>>::Close(void)
0x1800694de  jmp     short loc_180069505
0x1800694e0  lea     rcx, [rbp+57h+KeyPath]
0x1800694e4  call    ?Close@?$AutoString@U_UNICODE_STRING@@V?$Auto@U_UNICODE_STRING@@@Windows@@@Rtl@Windows@@QEAAXXZ; Windows::Rtl::AutoString<_UNICODE_STRING,Windows::Auto<_UNICODE_STRING>>::Close(void)
0x1800694e9  lea     r9, [rbp+57h+var_88]
0x1800694ed  mov     [rsp+0C0h+var_A0], rbx
0x1800694f2  mov     r8, r14
0x1800694f5  mov     rdx, rsi
0x1800694f8  xor     ecx, ecx
0x1800694fa  call    _anonymous_namespace___TryReplaceUpperCasePrefix
0x1800694ff  test    eax, eax
0x180069501  jns     short loc_180069512
0x180069503  mov     ebx, eax
0x180069505  lea     rcx, [rbp+57h+var_88]
0x180069509  call    ?Close@?$AutoString@U_LUTF8_STRING@@V?$Auto@U_LUTF8_STRING@@@Windows@@@Rtl@Windows@@QEAAXXZ; Windows::Rtl::AutoString<_LUTF8_STRING,Windows::Auto<_LUTF8_STRING>>::Close(void)
0x18006950e  mov     eax, ebx
0x180069510  jmp     short loc_18006955B
0x180069512  lea     rcx, [rbp+57h+var_88]
0x180069516  call    ?Close@?$AutoString@U_LUTF8_STRING@@V?$Auto@U_LUTF8_STRING@@@Windows@@@Rtl@Windows@@QEAAXXZ; Windows::Rtl::AutoString<_LUTF8_STRING,Windows::Auto<_LUTF8_STRING>>::Close(void)
0x18006951b  cmp     qword ptr [rbx], 0
0x18006951f  jnz     short loc_180069559
0x180069521  lea     rax, aOnecoreBaseLst; "onecore\\base\\lstring\\path.cpp"
0x180069528  mov     [rbp+57h+var_58], 8Dh
0x180069530  mov     [rbp+57h+var_68], rax
0x180069534  lea     rdx, [rbp+57h+var_68]
0x180069538  lea     rax, aRtlconvertwin3_2; "RtlConvertWin32RegistryPathToNtRegistry"...
0x18006953f  mov     [rbp+57h+var_60], rax
0x180069543  lea     rcx, [rbp+57h+var_38]
0x180069547  lea     rax, aPathoutLength0; "PathOut->Length != 0"
0x18006954e  mov     [rbp+57h+var_50], rax
0x180069552  call    ?OriginateInvalidParameter_NullPointer@?$CBaseFrame@UCSimpleNtStatusCarryingFrame@Rtl@ErrorHandling@Windows@@J@Rtl@ErrorHandling@Windows@@QEAAJAEBU_RTL_CALL_SITE@34@@Z; Windows::ErrorHandling::Rtl::CBaseFrame<Windows::ErrorHandling::Rtl::CSimpleNtStatusCarryingFrame,long>::OriginateInvalidParameter_NullPointer(Windows::ErrorHandling::_RTL_CALL_SITE const &)
0x180069557  jmp     short loc_18006955B
0x180069559  xor     eax, eax
0x18006955b  mov     rcx, [rbp+57h+var_20]
0x18006955f  xor     rcx, rsp; StackCookie
0x180069562  call    __security_check_cookie
0x180069567  lea     r11, [rsp+0C0h+var_10]
0x18006956f  mov     rbx, [r11+20h]
0x180069573  mov     rsi, [r11+28h]
0x180069577  mov     rsp, r11
0x18006957a  pop     r14
0x18006957c  pop     rdi
0x18006957d  pop     rbp
0x18006957e  retn
```
