# RtlConvertWin32RegistryPathToNtRegistryPathWithSid

- ea: `0x18006a284`
- end: `0x18006a3e0`
- name: `RtlConvertWin32RegistryPathToNtRegistryPathWithSid`
- size: `348`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation, registry_config`

## callers

- `0x18006a260`

## callees

- `0x18001f1d8`
- `0x18002d2b0`
- `0x180069338`
- `0x180069588`
- `0x18006a284`

## string_xrefs

- `0x18006a2c5`: `onecore\base\lstring\path.cpp`
- `0x18006a305`: `onecore\base\lstring\path.cpp`
- `0x18006a384`: `onecore\base\lstring\path.cpp`
- `0x18006a2e3`: `Not-null check failed: PathIn`
- `0x18006a323`: `Not-null check failed: PathOut`
- `0x18006a3aa`: `PathOut->Length != 0`
- `0x18006a2d8`: `RtlConvertWin32RegistryPathToNtRegistryPathWithSid`
- `0x18006a318`: `RtlConvertWin32RegistryPathToNtRegistryPathWithSid`
- `0x18006a39b`: `RtlConvertWin32RegistryPathToNtRegistryPathWithSid`

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
  unsigned __int64 i; // rdi
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
  for ( i = 0; i < 9; ++i )
  {
    if ( off_1800A3280[3 * i + 2] == (__int64 (*)[2])-2147483647LL )
      result = RtlConvertWin32RegistryPathToNtRegistryPathUser(a1, a2, a3, a4);
    else
      result = anonymous_namespace_::TryReplaceUpperCasePrefix(
                 0,
                 (_DWORD)a3,
                 (unsigned int)off_1800A3280[3 * i],
                 (unsigned int)off_1800A3280[3 * i + 1],
                 (__int64)a4);
    if ( (int)result < 0 )
      return result;
    if ( *(_QWORD *)a4 )
      return 0;
  }
  if ( !*(_QWORD *)a4 )
  {
    v11 = 188;
    v9 = "onecore\\base\\lstring\\path.cpp";
    v10 = "RtlConvertWin32RegistryPathToNtRegistryPathWithSid";
    v12 = "PathOut->Length != 0";
    return Windows::ErrorHandling::Rtl::CBaseFrame<Windows::ErrorHandling::Rtl::CSimpleNtStatusCarryingFrame,long>::OriginateInvalidParameter_NullPointer(
             &v13,
             &v9);
  }
  return 0;
}

```

## disassembly

```asm
0x18006a284  mov     [rsp-18h+arg_0], rbx
0x18006a289  mov     [rsp-18h+arg_8], rsi
0x18006a28e  push    rbp
0x18006a28f  push    rdi
0x18006a290  push    r15
0x18006a292  mov     rbp, rsp
0x18006a295  sub     rsp, 60h
0x18006a299  mov     rax, cs:__security_cookie
0x18006a2a0  xor     rax, rsp
0x18006a2a3  mov     [rbp+var_8], rax
0x18006a2a7  mov     [rbp+var_10], 0
0x18006a2ae  mov     rbx, r9
0x18006a2b1  mov     rsi, r8
0x18006a2b4  test    r9, r9
0x18006a2b7  jz      short loc_18006A2C0
0x18006a2b9  mov     qword ptr [r9], 0
0x18006a2c0  test    rsi, rsi
0x18006a2c3  jnz     short loc_18006A300
0x18006a2c5  lea     rax, aOnecoreBaseLst; "onecore\\base\\lstring\\path.cpp"
0x18006a2cc  mov     [rbp+var_20], 0A8h
0x18006a2d4  mov     [rbp+var_30], rax
0x18006a2d8  lea     rax, aRtlconvertwin3_3; "RtlConvertWin32RegistryPathToNtRegistry"...
0x18006a2df  mov     [rbp+var_28], rax
0x18006a2e3  lea     rax, aNotNullCheckFa_33; "Not-null check failed: PathIn"
0x18006a2ea  lea     rdx, [rbp+var_30]
0x18006a2ee  mov     [rbp+var_18], rax
0x18006a2f2  lea     rcx, [rbp+var_10]
0x18006a2f6  call    ?OriginateInvalidParameter_NullPointer@?$CBaseFrame@UCSimpleNtStatusCarryingFrame@Rtl@ErrorHandling@Windows@@J@Rtl@ErrorHandling@Windows@@QEAAJAEBU_RTL_CALL_SITE@34@@Z; Windows::ErrorHandling::Rtl::CBaseFrame<Windows::ErrorHandling::Rtl::CSimpleNtStatusCarryingFrame,long>::OriginateInvalidParameter_NullPointer(Windows::ErrorHandling::_RTL_CALL_SITE const &)
0x18006a2fb  jmp     loc_18006A3BE
0x18006a300  test    rbx, rbx
0x18006a303  jnz     short loc_18006A32C
0x18006a305  lea     rax, aOnecoreBaseLst; "onecore\\base\\lstring\\path.cpp"
0x18006a30c  mov     [rbp+var_20], 0A9h
0x18006a314  mov     [rbp+var_30], rax
0x18006a318  lea     rax, aRtlconvertwin3_3; "RtlConvertWin32RegistryPathToNtRegistry"...
0x18006a31f  mov     [rbp+var_28], rax
0x18006a323  lea     rax, aNotNullCheckFa_9; "Not-null check failed: PathOut"
0x18006a32a  jmp     short loc_18006A2EA
0x18006a32c  xor     edi, edi
0x18006a32e  lea     r15, off_1800A3280
0x18006a335  cmp     rdi, 9
0x18006a339  jnb     short loc_18006A37E
0x18006a33b  lea     r8, [rdi+rdi*2]
0x18006a33f  cmp     qword ptr [r15+r8*8+10h], 0FFFFFFFF80000001h
0x18006a348  jnz     short loc_18006A357
0x18006a34a  mov     r9, rbx; struct _LUNICODE_STRING *
0x18006a34d  mov     r8, rsi; struct _LUNICODE_STRING *
0x18006a350  call    ?RtlConvertWin32RegistryPathToNtRegistryPathUser@@YAJKPEBU_LUNICODE_STRING@@0PEAU1@@Z; RtlConvertWin32RegistryPathToNtRegistryPathUser(ulong,_LUNICODE_STRING const *,_LUNICODE_STRING const *,_LUNICODE_STRING *)
0x18006a355  jmp     short loc_18006A36F
0x18006a357  mov     r9, [r15+r8*8+8]
0x18006a35c  mov     rdx, rsi
0x18006a35f  mov     r8, [r15+r8*8]
0x18006a363  xor     ecx, ecx
0x18006a365  mov     [rsp+60h+var_40], rbx
0x18006a36a  call    _anonymous_namespace___TryReplaceUpperCasePrefix
0x18006a36f  test    eax, eax
0x18006a371  js      short loc_18006A3BE
0x18006a373  cmp     qword ptr [rbx], 0
0x18006a377  jnz     short loc_18006A3BC
0x18006a379  inc     rdi
0x18006a37c  jmp     short loc_18006A335
0x18006a37e  cmp     qword ptr [rbx], 0
0x18006a382  jnz     short loc_18006A3BC
0x18006a384  lea     rax, aOnecoreBaseLst; "onecore\\base\\lstring\\path.cpp"
0x18006a38b  mov     [rbp+var_20], 0BCh
0x18006a393  mov     [rbp+var_30], rax
0x18006a397  lea     rdx, [rbp+var_30]
0x18006a39b  lea     rax, aRtlconvertwin3_3; "RtlConvertWin32RegistryPathToNtRegistry"...
0x18006a3a2  mov     [rbp+var_28], rax
0x18006a3a6  lea     rcx, [rbp+var_10]
0x18006a3aa  lea     rax, aPathoutLength0; "PathOut->Length != 0"
0x18006a3b1  mov     [rbp+var_18], rax
0x18006a3b5  call    ?OriginateInvalidParameter_NullPointer@?$CBaseFrame@UCSimpleNtStatusCarryingFrame@Rtl@ErrorHandling@Windows@@J@Rtl@ErrorHandling@Windows@@QEAAJAEBU_RTL_CALL_SITE@34@@Z; Windows::ErrorHandling::Rtl::CBaseFrame<Windows::ErrorHandling::Rtl::CSimpleNtStatusCarryingFrame,long>::OriginateInvalidParameter_NullPointer(Windows::ErrorHandling::_RTL_CALL_SITE const &)
0x18006a3ba  jmp     short loc_18006A3BE
0x18006a3bc  xor     eax, eax
0x18006a3be  mov     rcx, [rbp+var_8]
0x18006a3c2  xor     rcx, rsp; StackCookie
0x18006a3c5  call    __security_check_cookie
0x18006a3ca  lea     r11, [rsp+60h+var_s0]
0x18006a3cf  mov     rbx, [r11+20h]
0x18006a3d3  mov     rsi, [r11+28h]
0x18006a3d7  mov     rsp, r11
0x18006a3da  pop     r15
0x18006a3dc  pop     rdi
0x18006a3dd  pop     rbp
0x18006a3de  retn
```
