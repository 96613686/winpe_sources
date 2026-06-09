# RtlSplitWin32RegistryPathIntoRootAndLeaves

- ea: `0x18006a3f0`
- end: `0x18006a61a`
- name: `RtlSplitWin32RegistryPathIntoRootAndLeaves`
- size: `554`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `registry_config`

## callees

- `0x180018e30`
- `0x18001f1d8`
- `0x18001f840`
- `0x18002d2b0`
- `0x18006a3f0`

## string_xrefs

- `0x18006a449`: `onecore\base\lstring\path.cpp`
- `0x18006a489`: `onecore\base\lstring\path.cpp`
- `0x18006a4c9`: `onecore\base\lstring\path.cpp`
- `0x18006a4f5`: `onecore\base\lstring\path.cpp`
- `0x18006a5e3`: `onecore\base\lstring\path.cpp`
- `0x18006a460`: `RtlSplitWin32RegistryPathIntoRootAndLeaves`
- `0x18006a49c`: `RtlSplitWin32RegistryPathIntoRootAndLeaves`
- `0x18006a4dc`: `RtlSplitWin32RegistryPathIntoRootAndLeaves`
- `0x18006a508`: `RtlSplitWin32RegistryPathIntoRootAndLeaves`
- `0x18006a5f6`: `RtlSplitWin32RegistryPathIntoRootAndLeaves`
- `0x18006a4a7`: `Not-null check failed: Win32RegistryPath`
- `0x18006a513`: `Not-null check failed: RootRelativePath`

## pseudocode

```c
__int64 __fastcall RtlSplitWin32RegistryPathIntoRootAndLeaves(int a1, const __m128i *a2, __int64 **a3, __m128i *a4)
{
  char v4; // r15
  __int64 result; // rax
  const char *v9; // rax
  unsigned __int64 i; // rsi
  __int64 *v11; // rdx
  __int64 *v12; // r8
  __int64 v13; // rdx
  __int64 v14; // rcx
  _BYTE v15[8]; // [rsp+20h] [rbp-40h] BYREF
  const char *v16; // [rsp+28h] [rbp-38h] BYREF
  const char *v17; // [rsp+30h] [rbp-30h]
  __int64 v18; // [rsp+38h] [rbp-28h]
  const char *v19; // [rsp+40h] [rbp-20h]
  __int64 v20; // [rsp+48h] [rbp-18h]
  int v21; // [rsp+50h] [rbp-10h] BYREF

  v4 = a1;
  v21 = 0;
  if ( a3 )
    *a3 = 0;
  if ( a4 )
  {
    a4->m128i_i64[0] = 0;
    a4->m128i_i64[1] = 0;
    a4[1].m128i_i64[0] = 0;
  }
  if ( (a1 & 0xFFFFFFFC) != 0 )
  {
    v18 = 238;
    v16 = "onecore\\base\\lstring\\path.cpp";
    v17 = "RtlSplitWin32RegistryPathIntoRootAndLeaves";
    v19 = "Valid flags check failed: Flags";
    return Windows::ErrorHandling::Rtl::CBaseFrame<Windows::ErrorHandling::Rtl::CSimpleNtStatusCarryingFrame,long>::OriginateInvalidParameter_NullPointer(
             &v21,
             &v16);
  }
  if ( !a2 )
  {
    v18 = 239;
    v16 = "onecore\\base\\lstring\\path.cpp";
    v17 = "RtlSplitWin32RegistryPathIntoRootAndLeaves";
    v9 = "Not-null check failed: Win32RegistryPath";
LABEL_9:
    v19 = v9;
    return Windows::ErrorHandling::Rtl::CBaseFrame<Windows::ErrorHandling::Rtl::CSimpleNtStatusCarryingFrame,long>::OriginateInvalidParameter_NullPointer(
             &v21,
             &v16);
  }
  if ( !a3 )
  {
    v18 = 240;
    v16 = "onecore\\base\\lstring\\path.cpp";
    v17 = "RtlSplitWin32RegistryPathIntoRootAndLeaves";
    v9 = "Not-null check failed: KeyRoot";
    goto LABEL_9;
  }
  if ( !a4 )
  {
    v18 = 241;
    v16 = "onecore\\base\\lstring\\path.cpp";
    v17 = "RtlSplitWin32RegistryPathIntoRootAndLeaves";
    v9 = "Not-null check failed: RootRelativePath";
    goto LABEL_9;
  }
  for ( i = 0; ; ++i )
  {
    if ( i >= 9 )
      goto LABEL_23;
    v15[0] = 0;
    v11 = (__int64 *)off_1800A3280[3 * i];
    v20 = 3 * i;
    result = RtlEqualLUnicodeStringPrefix(
               a2,
               v11,
               (unsigned __int64)RtlUpcaseUCSCharacter & -(__int64)((v4 & 2) != 0),
               v15);
    if ( (int)result < 0 )
      return result;
    if ( v15[0] )
      break;
  }
  _mm_lfence();
  v12 = (__int64 *)off_1800A3280[v20 + 2];
  if ( v12 )
  {
    v13 = a2[1].m128i_i64[0];
    v14 = (*off_1800A3280[v20])[0];
    *a4 = _mm_sub_epi64(
            _mm_loadu_si128(a2),
            _mm_unpacklo_epi64((__m128i)(unsigned __int64)v14, (__m128i)(unsigned __int64)v14));
    a4[1].m128i_i64[0] = v14 + v13;
    *a3 = v12;
    return 0;
  }
LABEL_23:
  if ( (v4 & 1) != 0 )
    return 0;
  v19 = 0;
  v16 = "onecore\\base\\lstring\\path.cpp";
  v18 = 279;
  v17 = "RtlSplitWin32RegistryPathIntoRootAndLeaves";
  return Windows::ErrorHandling::Rtl::CBaseFrame<Windows::ErrorHandling::Rtl::CSimpleNtStatusCarryingFrame,long>::OriginateNtStatus(
           &v21,
           &v16,
           3221225529LL);
}

```

## disassembly

```asm
0x18006a3f0  mov     [rsp-38h+arg_0], rbx
0x18006a3f5  push    rbp
0x18006a3f6  push    rsi
0x18006a3f7  push    rdi
0x18006a3f8  push    r12
0x18006a3fa  push    r13
0x18006a3fc  push    r14
0x18006a3fe  push    r15
0x18006a400  mov     rbp, rsp
0x18006a403  sub     rsp, 60h
0x18006a407  mov     rax, cs:__security_cookie
0x18006a40e  xor     rax, rsp
0x18006a411  mov     [rbp+var_8], rax
0x18006a415  mov     r15d, ecx
0x18006a418  mov     rdi, r9
0x18006a41b  xor     ecx, ecx
0x18006a41d  mov     r14, r8
0x18006a420  mov     [rbp+var_10], ecx
0x18006a423  mov     r13, rdx
0x18006a426  mov     ebx, ecx
0x18006a428  test    r8, r8
0x18006a42b  jz      short loc_18006A430
0x18006a42d  mov     [r8], rcx
0x18006a430  test    rdi, rdi
0x18006a433  jz      short loc_18006A440
0x18006a435  mov     [r9], rcx
0x18006a438  mov     [r9+8], rcx
0x18006a43c  mov     [r9+10h], rcx
0x18006a440  test    r15d, 0FFFFFFFCh
0x18006a447  jz      short loc_18006A484
0x18006a449  lea     rax, aOnecoreBaseLst; "onecore\\base\\lstring\\path.cpp"
0x18006a450  mov     [rbp+var_28], 0EEh
0x18006a458  mov     [rbp+var_38], rax
0x18006a45c  lea     rdx, [rbp+var_38]
0x18006a460  lea     rax, aRtlsplitwin32r_0; "RtlSplitWin32RegistryPathIntoRootAndLea"...
0x18006a467  mov     [rbp+var_30], rax
0x18006a46b  lea     rcx, [rbp+var_10]
0x18006a46f  lea     rax, aValidFlagsChec; "Valid flags check failed: Flags"
0x18006a476  mov     [rbp+var_20], rax
0x18006a47a  call    ?OriginateInvalidParameter_NullPointer@?$CBaseFrame@UCSimpleNtStatusCarryingFrame@Rtl@ErrorHandling@Windows@@J@Rtl@ErrorHandling@Windows@@QEAAJAEBU_RTL_CALL_SITE@34@@Z; Windows::ErrorHandling::Rtl::CBaseFrame<Windows::ErrorHandling::Rtl::CSimpleNtStatusCarryingFrame,long>::OriginateInvalidParameter_NullPointer(Windows::ErrorHandling::_RTL_CALL_SITE const &)
0x18006a47f  jmp     loc_18006A5B8
0x18006a484  test    r13, r13
0x18006a487  jnz     short loc_18006A4C4
0x18006a489  lea     rax, aOnecoreBaseLst; "onecore\\base\\lstring\\path.cpp"
0x18006a490  mov     [rbp+var_28], 0EFh
0x18006a498  mov     [rbp+var_38], rax
0x18006a49c  lea     rax, aRtlsplitwin32r_0; "RtlSplitWin32RegistryPathIntoRootAndLea"...
0x18006a4a3  mov     [rbp+var_30], rax
0x18006a4a7  lea     rax, aNotNullCheckFa_68; "Not-null check failed: Win32RegistryPat"...
0x18006a4ae  lea     rdx, [rbp+var_38]
0x18006a4b2  mov     [rbp+var_20], rax
0x18006a4b6  lea     rcx, [rbp+var_10]
0x18006a4ba  call    ?OriginateInvalidParameter_NullPointer@?$CBaseFrame@UCSimpleNtStatusCarryingFrame@Rtl@ErrorHandling@Windows@@J@Rtl@ErrorHandling@Windows@@QEAAJAEBU_RTL_CALL_SITE@34@@Z; Windows::ErrorHandling::Rtl::CBaseFrame<Windows::ErrorHandling::Rtl::CSimpleNtStatusCarryingFrame,long>::OriginateInvalidParameter_NullPointer(Windows::ErrorHandling::_RTL_CALL_SITE const &)
0x18006a4bf  jmp     loc_18006A5B8
0x18006a4c4  test    r14, r14
0x18006a4c7  jnz     short loc_18006A4F0
0x18006a4c9  lea     rax, aOnecoreBaseLst; "onecore\\base\\lstring\\path.cpp"
0x18006a4d0  mov     [rbp+var_28], 0F0h
0x18006a4d8  mov     [rbp+var_38], rax
0x18006a4dc  lea     rax, aRtlsplitwin32r_0; "RtlSplitWin32RegistryPathIntoRootAndLea"...
0x18006a4e3  mov     [rbp+var_30], rax
0x18006a4e7  lea     rax, aNotNullCheckFa_124; "Not-null check failed: KeyRoot"
0x18006a4ee  jmp     short loc_18006A4AE
0x18006a4f0  test    rdi, rdi
0x18006a4f3  jnz     short loc_18006A51C
0x18006a4f5  lea     rax, aOnecoreBaseLst; "onecore\\base\\lstring\\path.cpp"
0x18006a4fc  mov     [rbp+var_28], 0F1h
0x18006a504  mov     [rbp+var_38], rax
0x18006a508  lea     rax, aRtlsplitwin32r_0; "RtlSplitWin32RegistryPathIntoRootAndLea"...
0x18006a50f  mov     [rbp+var_30], rax
0x18006a513  lea     rax, aNotNullCheckFa_47; "Not-null check failed: RootRelativePath"
0x18006a51a  jmp     short loc_18006A4AE
0x18006a51c  mov     eax, r15d
0x18006a51f  lea     rdx, off_1800A3280
0x18006a526  and     al, 2
0x18006a528  mov     rsi, rcx
0x18006a52b  neg     al
0x18006a52d  lea     rax, RtlUpcaseUCSCharacter
0x18006a534  sbb     r12, r12
0x18006a537  and     r12, rax
0x18006a53a  cmp     rsi, 9
0x18006a53e  jnb     loc_18006A5DD
0x18006a544  lea     rax, [rsi+rsi*2]
0x18006a548  mov     [rbp+var_40], cl
0x18006a54b  mov     rdx, [rdx+rax*8]
0x18006a54f  lea     r9, [rbp+var_40]
0x18006a553  mov     r8, r12
0x18006a556  mov     [rbp+var_18], rax
0x18006a55a  mov     rcx, r13
0x18006a55d  call    RtlEqualLUnicodeStringPrefix
0x18006a562  xor     ecx, ecx
0x18006a564  test    eax, eax
0x18006a566  js      short loc_18006A5B8
0x18006a568  lea     rdx, off_1800A3280
0x18006a56f  cmp     [rbp+var_40], cl
0x18006a572  jnz     short loc_18006A579
0x18006a574  inc     rsi
0x18006a577  jmp     short loc_18006A53A
0x18006a579  lfence
0x18006a57c  mov     rax, [rbp+var_18]
0x18006a580  mov     r8, [rdx+rax*8+10h]
0x18006a585  test    r8, r8
0x18006a588  jz      short loc_18006A5DD
0x18006a58a  mov     rax, [rdx+rax*8]
0x18006a58e  movdqu  xmm1, xmmword ptr [r13+0]
0x18006a594  mov     rdx, [r13+10h]
0x18006a598  mov     rcx, [rax]
0x18006a59b  add     rdx, rcx
0x18006a59e  movq    xmm0, rcx
0x18006a5a3  punpcklqdq xmm0, xmm0
0x18006a5a7  psubq   xmm1, xmm0
0x18006a5ab  movdqu  xmmword ptr [rdi], xmm1
0x18006a5af  mov     [rdi+10h], rdx
0x18006a5b3  mov     [r14], r8
0x18006a5b6  mov     eax, ebx
0x18006a5b8  mov     rcx, [rbp+var_8]
0x18006a5bc  xor     rcx, rsp; StackCookie
0x18006a5bf  call    __security_check_cookie
0x18006a5c4  mov     rbx, [rsp+60h+arg_0]
0x18006a5cc  add     rsp, 60h
0x18006a5d0  pop     r15
0x18006a5d2  pop     r14
0x18006a5d4  pop     r13
0x18006a5d6  pop     r12
0x18006a5d8  pop     rdi
0x18006a5d9  pop     rsi
0x18006a5da  pop     rbp
0x18006a5db  retn
0x18006a5dd  test    r15b, 1
0x18006a5e1  jnz     short loc_18006A5B6
0x18006a5e3  lea     rax, aOnecoreBaseLst; "onecore\\base\\lstring\\path.cpp"
0x18006a5ea  mov     [rbp+var_20], rcx
0x18006a5ee  mov     [rbp+var_38], rax
0x18006a5f2  lea     rdx, [rbp+var_38]
0x18006a5f6  lea     rax, aRtlsplitwin32r_0; "RtlSplitWin32RegistryPathIntoRootAndLea"...
0x18006a5fd  mov     [rbp+var_28], 117h
0x18006a605  mov     r8d, 0C0000039h
0x18006a60b  mov     [rbp+var_30], rax
0x18006a60f  lea     rcx, [rbp+var_10]
0x18006a613  call    ?OriginateNtStatus@?$CBaseFrame@UCSimpleNtStatusCarryingFrame@Rtl@ErrorHandling@Windows@@J@Rtl@ErrorHandling@Windows@@QEAAJAEBU_RTL_CALL_SITE@34@J@Z; Windows::ErrorHandling::Rtl::CBaseFrame<Windows::ErrorHandling::Rtl::CSimpleNtStatusCarryingFrame,long>::OriginateNtStatus(Windows::ErrorHandling::_RTL_CALL_SITE const &,long)
0x18006a618  jmp     short loc_18006A5B8
```
