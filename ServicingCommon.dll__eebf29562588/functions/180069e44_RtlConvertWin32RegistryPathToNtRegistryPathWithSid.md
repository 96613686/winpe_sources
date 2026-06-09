# RtlConvertWin32RegistryPathToNtRegistryPathWithSid

- ea: `0x180069e44`
- end: `0x180069f98`
- name: `RtlConvertWin32RegistryPathToNtRegistryPathWithSid`
- size: `340`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation, registry_config`

## callers

- `0x180069e20`

## callees

- `0x18001f4ac`
- `0x1800293a0`
- `0x180068f08`
- `0x180069154`
- `0x180069e44`

## string_xrefs

- `0x180069e85`: `onecore\base\lstring\path.cpp`
- `0x180069ec5`: `onecore\base\lstring\path.cpp`
- `0x180069f3c`: `onecore\base\lstring\path.cpp`
- `0x180069ea3`: `Not-null check failed: PathIn`
- `0x180069ee3`: `Not-null check failed: PathOut`
- `0x180069f62`: `PathOut->Length != 0`
- `0x180069e98`: `RtlConvertWin32RegistryPathToNtRegistryPathWithSid`
- `0x180069ed8`: `RtlConvertWin32RegistryPathToNtRegistryPathWithSid`
- `0x180069f53`: `RtlConvertWin32RegistryPathToNtRegistryPathWithSid`

## pseudocode

```c
__int64 __fastcall RtlConvertWin32RegistryPathToNtRegistryPathWithSid(
        __int64 a1,
        const struct _LUNICODE_STRING *a2,
        const struct _LUNICODE_STRING *a3,
        struct _LUNICODE_STRING *a4)
{
  const char *v6; // rax
  __int64 result; // rax
  __int64 v8; // rdi
  const char *v9; // [rsp+30h] [rbp-30h] BYREF
  const char *v10; // [rsp+38h] [rbp-28h]
  __int64 v11; // [rsp+40h] [rbp-20h]
  const char *v12; // [rsp+48h] [rbp-18h]
  int v13; // [rsp+50h] [rbp-10h] BYREF

  v13 = 0;
  if ( a4 )
    *(_QWORD *)a4 = 0;
  if ( !a3 )
  {
    v11 = 168;
    v9 = "onecore\\base\\lstring\\path.cpp";
    v10 = "RtlConvertWin32RegistryPathToNtRegistryPathWithSid";
    v6 = "Not-null check failed: PathIn";
LABEL_5:
    v12 = v6;
    return Windows::ErrorHandling::Rtl::CBaseFrame<Windows::ErrorHandling::Rtl::CSimpleNtStatusCarryingFrame,long>::OriginateInvalidParameter_NullPointer(
             &v13,
             &v9);
  }
  if ( !a4 )
  {
    v11 = 169;
    v9 = "onecore\\base\\lstring\\path.cpp";
    v10 = "RtlConvertWin32RegistryPathToNtRegistryPathWithSid";
    v6 = "Not-null check failed: PathOut";
    goto LABEL_5;
  }
  v8 = 0;
  while ( 1 )
  {
    result = off_1800A5130[3 * v8 + 2] == (__int64 (*)[2])-2147483647LL
           ? RtlConvertWin32RegistryPathToNtRegistryPathUser(a1, a2, a3, a4)
           : anonymous_namespace_::TryReplaceUpperCasePrefix(
               0,
               (_DWORD)a3,
               (unsigned int)off_1800A5130[3 * v8],
               (unsigned int)off_1800A5130[3 * v8 + 1],
               (__int64)a4);
    if ( (int)result < 0 )
      break;
    if ( *(_QWORD *)a4 )
      return 0;
    if ( (unsigned __int64)++v8 >= 9 )
    {
      v11 = 188;
      v9 = "onecore\\base\\lstring\\path.cpp";
      v10 = "RtlConvertWin32RegistryPathToNtRegistryPathWithSid";
      v12 = "PathOut->Length != 0";
      return Windows::ErrorHandling::Rtl::CBaseFrame<Windows::ErrorHandling::Rtl::CSimpleNtStatusCarryingFrame,long>::OriginateInvalidParameter_NullPointer(
               &v13,
               &v9);
    }
  }
  return result;
}

```

## disassembly

```asm
0x180069e44  mov     [rsp-18h+arg_0], rbx
0x180069e49  mov     [rsp-18h+arg_8], rsi
0x180069e4e  push    rbp
0x180069e4f  push    rdi
0x180069e50  push    r15
0x180069e52  mov     rbp, rsp
0x180069e55  sub     rsp, 60h
0x180069e59  mov     rax, cs:__security_cookie
0x180069e60  xor     rax, rsp
0x180069e63  mov     [rbp+var_8], rax
0x180069e67  mov     [rbp+var_10], 0
0x180069e6e  mov     rbx, r9
0x180069e71  mov     rsi, r8
0x180069e74  test    r9, r9
0x180069e77  jz      short loc_180069E80
0x180069e79  mov     qword ptr [r9], 0
0x180069e80  test    rsi, rsi
0x180069e83  jnz     short loc_180069EC0
0x180069e85  lea     rax, aOnecoreBaseLst; "onecore\\base\\lstring\\path.cpp"
0x180069e8c  mov     [rbp+var_20], 0A8h
0x180069e94  mov     [rbp+var_30], rax
0x180069e98  lea     rax, aRtlconvertwin3_3; "RtlConvertWin32RegistryPathToNtRegistry"...
0x180069e9f  mov     [rbp+var_28], rax
0x180069ea3  lea     rax, aNotNullCheckFa_33; "Not-null check failed: PathIn"
0x180069eaa  lea     rdx, [rbp+var_30]
0x180069eae  mov     [rbp+var_18], rax
0x180069eb2  lea     rcx, [rbp+var_10]
0x180069eb6  call    ?OriginateInvalidParameter_NullPointer@?$CBaseFrame@UCSimpleNtStatusCarryingFrame@Rtl@ErrorHandling@Windows@@J@Rtl@ErrorHandling@Windows@@QEAAJAEBU_RTL_CALL_SITE@34@@Z; Windows::ErrorHandling::Rtl::CBaseFrame<Windows::ErrorHandling::Rtl::CSimpleNtStatusCarryingFrame,long>::OriginateInvalidParameter_NullPointer(Windows::ErrorHandling::_RTL_CALL_SITE const &)
0x180069ebb  jmp     loc_180069F76
0x180069ec0  test    rbx, rbx
0x180069ec3  jnz     short loc_180069EEC
0x180069ec5  lea     rax, aOnecoreBaseLst; "onecore\\base\\lstring\\path.cpp"
0x180069ecc  mov     [rbp+var_20], 0A9h
0x180069ed4  mov     [rbp+var_30], rax
0x180069ed8  lea     rax, aRtlconvertwin3_3; "RtlConvertWin32RegistryPathToNtRegistry"...
0x180069edf  mov     [rbp+var_28], rax
0x180069ee3  lea     rax, aNotNullCheckFa_9; "Not-null check failed: PathOut"
0x180069eea  jmp     short loc_180069EAA
0x180069eec  xor     edi, edi
0x180069eee  lea     r15, off_1800A5130
0x180069ef5  lea     r8, [rdi+rdi*2]
0x180069ef9  cmp     qword ptr [r15+r8*8+10h], 0FFFFFFFF80000001h
0x180069f02  jnz     short loc_180069F11
0x180069f04  mov     r9, rbx; struct _LUNICODE_STRING *
0x180069f07  mov     r8, rsi; struct _LUNICODE_STRING *
0x180069f0a  call    ?RtlConvertWin32RegistryPathToNtRegistryPathUser@@YAJKPEBU_LUNICODE_STRING@@0PEAU1@@Z; RtlConvertWin32RegistryPathToNtRegistryPathUser(ulong,_LUNICODE_STRING const *,_LUNICODE_STRING const *,_LUNICODE_STRING *)
0x180069f0f  jmp     short loc_180069F29
0x180069f11  mov     r9, [r15+r8*8+8]
0x180069f16  mov     rdx, rsi
0x180069f19  mov     r8, [r15+r8*8]
0x180069f1d  xor     ecx, ecx
0x180069f1f  mov     [rsp+60h+var_40], rbx
0x180069f24  call    _anonymous_namespace___TryReplaceUpperCasePrefix
0x180069f29  test    eax, eax
0x180069f2b  js      short loc_180069F76
0x180069f2d  cmp     qword ptr [rbx], 0
0x180069f31  jnz     short loc_180069F74
0x180069f33  inc     rdi
0x180069f36  cmp     rdi, 9
0x180069f3a  jb      short loc_180069EF5
0x180069f3c  lea     rax, aOnecoreBaseLst; "onecore\\base\\lstring\\path.cpp"
0x180069f43  mov     [rbp+var_20], 0BCh
0x180069f4b  mov     [rbp+var_30], rax
0x180069f4f  lea     rdx, [rbp+var_30]
0x180069f53  lea     rax, aRtlconvertwin3_3; "RtlConvertWin32RegistryPathToNtRegistry"...
0x180069f5a  mov     [rbp+var_28], rax
0x180069f5e  lea     rcx, [rbp+var_10]
0x180069f62  lea     rax, aPathoutLength0; "PathOut->Length != 0"
0x180069f69  mov     [rbp+var_18], rax
0x180069f6d  call    ?OriginateInvalidParameter_NullPointer@?$CBaseFrame@UCSimpleNtStatusCarryingFrame@Rtl@ErrorHandling@Windows@@J@Rtl@ErrorHandling@Windows@@QEAAJAEBU_RTL_CALL_SITE@34@@Z; Windows::ErrorHandling::Rtl::CBaseFrame<Windows::ErrorHandling::Rtl::CSimpleNtStatusCarryingFrame,long>::OriginateInvalidParameter_NullPointer(Windows::ErrorHandling::_RTL_CALL_SITE const &)
0x180069f72  jmp     short loc_180069F76
0x180069f74  xor     eax, eax
0x180069f76  mov     rcx, [rbp+var_8]
0x180069f7a  xor     rcx, rsp; StackCookie
0x180069f7d  call    __security_check_cookie
0x180069f82  lea     r11, [rsp+60h+var_s0]
0x180069f87  mov     rbx, [r11+20h]
0x180069f8b  mov     rsi, [r11+28h]
0x180069f8f  mov     rsp, r11
0x180069f92  pop     r15
0x180069f94  pop     rdi
0x180069f95  pop     rbp
0x180069f96  retn
```
