# RtlSplitWin32RegistryPathIntoRootAndLeaves

- ea: `0x180069fa0`
- end: `0x18006a1c5`
- name: `RtlSplitWin32RegistryPathIntoRootAndLeaves`
- size: `549`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `registry_config`

## callees

- `0x180006010`
- `0x18001f4ac`
- `0x18001f5d4`
- `0x1800293a0`
- `0x180069fa0`

## string_xrefs

- `0x180069ff9`: `onecore\base\lstring\path.cpp`
- `0x18006a039`: `onecore\base\lstring\path.cpp`
- `0x18006a079`: `onecore\base\lstring\path.cpp`
- `0x18006a0a5`: `onecore\base\lstring\path.cpp`
- `0x18006a12d`: `onecore\base\lstring\path.cpp`
- `0x18006a010`: `RtlSplitWin32RegistryPathIntoRootAndLeaves`
- `0x18006a04c`: `RtlSplitWin32RegistryPathIntoRootAndLeaves`
- `0x18006a08c`: `RtlSplitWin32RegistryPathIntoRootAndLeaves`
- `0x18006a0b8`: `RtlSplitWin32RegistryPathIntoRootAndLeaves`
- `0x18006a140`: `RtlSplitWin32RegistryPathIntoRootAndLeaves`
- `0x18006a057`: `Not-null check failed: Win32RegistryPath`
- `0x18006a0c3`: `Not-null check failed: RootRelativePath`

## pseudocode

```c
__int64 __fastcall RtlSplitWin32RegistryPathIntoRootAndLeaves(int a1, const __m128i *a2, _QWORD *a3, __m128i *a4)
{
  char v4; // r15
  __int64 result; // rax
  const char *v9; // rax
  __int64 v10; // rsi
  __int64 v11; // rdx
  __int64 v12; // r8
  __int64 v13; // rdx
  unsigned __int64 v14; // rcx
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
  v10 = 0;
  while ( 1 )
  {
    v15[0] = 0;
    v11 = (__int64)*(&off_1800A5130 + 3 * v10);
    v20 = 3 * v10;
    result = RtlEqualLUnicodeStringPrefix(
               a2,
               v11,
               (unsigned __int64)RtlUpcaseUCSCharacter & -(__int64)((v4 & 2) != 0),
               v15);
    if ( (int)result < 0 )
      return result;
    if ( v15[0] )
    {
      v12 = (__int64)*(&off_1800A5130 + v20 + 2);
      if ( v12 )
      {
        v13 = a2[1].m128i_i64[0];
        v14 = *(_QWORD *)*(&off_1800A5130 + v20);
        *a4 = _mm_sub_epi64(_mm_loadu_si128(a2), _mm_unpacklo_epi64((__m128i)v14, (__m128i)v14));
        a4[1].m128i_i64[0] = v14 + v13;
        *a3 = v12;
      }
      else
      {
LABEL_18:
        if ( (v4 & 1) == 0 )
        {
          v19 = 0;
          v16 = "onecore\\base\\lstring\\path.cpp";
          v18 = 279;
          v17 = "RtlSplitWin32RegistryPathIntoRootAndLeaves";
          return Windows::ErrorHandling::Rtl::CBaseFrame<Windows::ErrorHandling::Rtl::CSimpleNtStatusCarryingFrame,long>::OriginateNtStatus(
                   &v21,
                   &v16,
                   3221225529LL);
        }
      }
      return 0;
    }
    if ( (unsigned __int64)++v10 >= 9 )
      goto LABEL_18;
  }
}

```

## disassembly

```asm
0x180069fa0  mov     [rsp-38h+arg_0], rbx
0x180069fa5  push    rbp
0x180069fa6  push    rsi
0x180069fa7  push    rdi
0x180069fa8  push    r12
0x180069faa  push    r13
0x180069fac  push    r14
0x180069fae  push    r15
0x180069fb0  mov     rbp, rsp
0x180069fb3  sub     rsp, 60h
0x180069fb7  mov     rax, cs:__security_cookie
0x180069fbe  xor     rax, rsp
0x180069fc1  mov     [rbp+var_8], rax
0x180069fc5  mov     r15d, ecx
0x180069fc8  mov     rdi, r9
0x180069fcb  xor     ecx, ecx
0x180069fcd  mov     r14, r8
0x180069fd0  mov     [rbp+var_10], ecx
0x180069fd3  mov     r13, rdx
0x180069fd6  mov     ebx, ecx
0x180069fd8  test    r8, r8
0x180069fdb  jz      short loc_180069FE0
0x180069fdd  mov     [r8], rcx
0x180069fe0  test    rdi, rdi
0x180069fe3  jz      short loc_180069FF0
0x180069fe5  mov     [r9], rcx
0x180069fe8  mov     [r9+8], rcx
0x180069fec  mov     [r9+10h], rcx
0x180069ff0  test    r15d, 0FFFFFFFCh
0x180069ff7  jz      short loc_18006A034
0x180069ff9  lea     rax, aOnecoreBaseLst; "onecore\\base\\lstring\\path.cpp"
0x18006a000  mov     [rbp+var_28], 0EEh
0x18006a008  mov     [rbp+var_38], rax
0x18006a00c  lea     rdx, [rbp+var_38]
0x18006a010  lea     rax, aRtlsplitwin32r_0; "RtlSplitWin32RegistryPathIntoRootAndLea"...
0x18006a017  mov     [rbp+var_30], rax
0x18006a01b  lea     rcx, [rbp+var_10]
0x18006a01f  lea     rax, aValidFlagsChec; "Valid flags check failed: Flags"
0x18006a026  mov     [rbp+var_20], rax
0x18006a02a  call    ?OriginateInvalidParameter_NullPointer@?$CBaseFrame@UCSimpleNtStatusCarryingFrame@Rtl@ErrorHandling@Windows@@J@Rtl@ErrorHandling@Windows@@QEAAJAEBU_RTL_CALL_SITE@34@@Z; Windows::ErrorHandling::Rtl::CBaseFrame<Windows::ErrorHandling::Rtl::CSimpleNtStatusCarryingFrame,long>::OriginateInvalidParameter_NullPointer(Windows::ErrorHandling::_RTL_CALL_SITE const &)
0x18006a02f  jmp     loc_18006A1A0
0x18006a034  test    r13, r13
0x18006a037  jnz     short loc_18006A074
0x18006a039  lea     rax, aOnecoreBaseLst; "onecore\\base\\lstring\\path.cpp"
0x18006a040  mov     [rbp+var_28], 0EFh
0x18006a048  mov     [rbp+var_38], rax
0x18006a04c  lea     rax, aRtlsplitwin32r_0; "RtlSplitWin32RegistryPathIntoRootAndLea"...
0x18006a053  mov     [rbp+var_30], rax
0x18006a057  lea     rax, aNotNullCheckFa_68; "Not-null check failed: Win32RegistryPat"...
0x18006a05e  lea     rdx, [rbp+var_38]
0x18006a062  mov     [rbp+var_20], rax
0x18006a066  lea     rcx, [rbp+var_10]
0x18006a06a  call    ?OriginateInvalidParameter_NullPointer@?$CBaseFrame@UCSimpleNtStatusCarryingFrame@Rtl@ErrorHandling@Windows@@J@Rtl@ErrorHandling@Windows@@QEAAJAEBU_RTL_CALL_SITE@34@@Z; Windows::ErrorHandling::Rtl::CBaseFrame<Windows::ErrorHandling::Rtl::CSimpleNtStatusCarryingFrame,long>::OriginateInvalidParameter_NullPointer(Windows::ErrorHandling::_RTL_CALL_SITE const &)
0x18006a06f  jmp     loc_18006A1A0
0x18006a074  test    r14, r14
0x18006a077  jnz     short loc_18006A0A0
0x18006a079  lea     rax, aOnecoreBaseLst; "onecore\\base\\lstring\\path.cpp"
0x18006a080  mov     [rbp+var_28], 0F0h
0x18006a088  mov     [rbp+var_38], rax
0x18006a08c  lea     rax, aRtlsplitwin32r_0; "RtlSplitWin32RegistryPathIntoRootAndLea"...
0x18006a093  mov     [rbp+var_30], rax
0x18006a097  lea     rax, aNotNullCheckFa_124; "Not-null check failed: KeyRoot"
0x18006a09e  jmp     short loc_18006A05E
0x18006a0a0  test    rdi, rdi
0x18006a0a3  jnz     short loc_18006A0CC
0x18006a0a5  lea     rax, aOnecoreBaseLst; "onecore\\base\\lstring\\path.cpp"
0x18006a0ac  mov     [rbp+var_28], 0F1h
0x18006a0b4  mov     [rbp+var_38], rax
0x18006a0b8  lea     rax, aRtlsplitwin32r_0; "RtlSplitWin32RegistryPathIntoRootAndLea"...
0x18006a0bf  mov     [rbp+var_30], rax
0x18006a0c3  lea     rax, aNotNullCheckFa_47; "Not-null check failed: RootRelativePath"
0x18006a0ca  jmp     short loc_18006A05E
0x18006a0cc  mov     eax, r15d
0x18006a0cf  lea     rdx, off_1800A5130
0x18006a0d6  and     al, 2
0x18006a0d8  mov     rsi, rcx
0x18006a0db  neg     al
0x18006a0dd  lea     rax, RtlUpcaseUCSCharacter
0x18006a0e4  sbb     r12, r12
0x18006a0e7  and     r12, rax
0x18006a0ea  lea     rax, [rsi+rsi*2]
0x18006a0ee  mov     [rbp+var_40], cl
0x18006a0f1  mov     rdx, [rdx+rax*8]
0x18006a0f5  lea     r9, [rbp+var_40]
0x18006a0f9  mov     r8, r12
0x18006a0fc  mov     [rbp+var_18], rax
0x18006a100  mov     rcx, r13
0x18006a103  call    RtlEqualLUnicodeStringPrefix
0x18006a108  xor     ecx, ecx
0x18006a10a  test    eax, eax
0x18006a10c  js      loc_18006A1A0
0x18006a112  lea     rdx, off_1800A5130
0x18006a119  cmp     [rbp+var_40], cl
0x18006a11c  jnz     short loc_18006A164
0x18006a11e  inc     rsi
0x18006a121  cmp     rsi, 9
0x18006a125  jb      short loc_18006A0EA
0x18006a127  test    r15b, 1
0x18006a12b  jnz     short loc_18006A19E
0x18006a12d  lea     rax, aOnecoreBaseLst; "onecore\\base\\lstring\\path.cpp"
0x18006a134  mov     [rbp+var_20], rcx
0x18006a138  mov     [rbp+var_38], rax
0x18006a13c  lea     rdx, [rbp+var_38]
0x18006a140  lea     rax, aRtlsplitwin32r_0; "RtlSplitWin32RegistryPathIntoRootAndLea"...
0x18006a147  mov     [rbp+var_28], 117h
0x18006a14f  mov     r8d, 0C0000039h
0x18006a155  mov     [rbp+var_30], rax
0x18006a159  lea     rcx, [rbp+var_10]
0x18006a15d  call    ?OriginateNtStatus@?$CBaseFrame@UCSimpleNtStatusCarryingFrame@Rtl@ErrorHandling@Windows@@J@Rtl@ErrorHandling@Windows@@QEAAJAEBU_RTL_CALL_SITE@34@J@Z; Windows::ErrorHandling::Rtl::CBaseFrame<Windows::ErrorHandling::Rtl::CSimpleNtStatusCarryingFrame,long>::OriginateNtStatus(Windows::ErrorHandling::_RTL_CALL_SITE const &,long)
0x18006a162  jmp     short loc_18006A1A0
0x18006a164  mov     rax, [rbp+var_18]
0x18006a168  mov     r8, [rdx+rax*8+10h]
0x18006a16d  test    r8, r8
0x18006a170  jz      short loc_18006A127
0x18006a172  mov     rax, [rdx+rax*8]
0x18006a176  movdqu  xmm1, xmmword ptr [r13+0]
0x18006a17c  mov     rdx, [r13+10h]
0x18006a180  mov     rcx, [rax]
0x18006a183  add     rdx, rcx
0x18006a186  movq    xmm0, rcx
0x18006a18b  punpcklqdq xmm0, xmm0
0x18006a18f  psubq   xmm1, xmm0
0x18006a193  movdqu  xmmword ptr [rdi], xmm1
0x18006a197  mov     [rdi+10h], rdx
0x18006a19b  mov     [r14], r8
0x18006a19e  mov     eax, ebx
0x18006a1a0  mov     rcx, [rbp+var_8]
0x18006a1a4  xor     rcx, rsp; StackCookie
0x18006a1a7  call    __security_check_cookie
0x18006a1ac  mov     rbx, [rsp+60h+arg_0]
0x18006a1b4  add     rsp, 60h
0x18006a1b8  pop     r15
0x18006a1ba  pop     r14
0x18006a1bc  pop     r13
0x18006a1be  pop     r12
0x18006a1c0  pop     rdi
0x18006a1c1  pop     rsi
0x18006a1c2  pop     rbp
0x18006a1c3  retn
```
