# RtlConvertNtFilePathToWin32FilePath

- ea: `0x180069a30`
- end: `0x180069e51`
- name: `RtlConvertNtFilePathToWin32FilePath`
- size: `1057`
- prototype: ``
- caller_count: `0`
- callee_count: `7`
- tags: ``

## callees

- `0x180007bb0`
- `0x180018e30`
- `0x18001d7b0`
- `0x18001f1d8`
- `0x18001f840`
- `0x18002d2b0`
- `0x180069a30`

## string_xrefs

- `0x180069a7d`: `onecore\base\lstring\path.cpp`
- `0x180069ac5`: `onecore\base\lstring\path.cpp`
- `0x180069d4f`: `onecore\base\lstring\path.cpp`
- `0x180069a9e`: `Not-null check failed: PathIn`
- `0x180069ae6`: `Not-null check failed: PathOut`
- `0x180069a92`: `RtlConvertNtFilePathToWin32FilePath`
- `0x180069ada`: `RtlConvertNtFilePathToWin32FilePath`
- `0x180069d69`: `RtlConvertNtFilePathToWin32FilePath`

## pseudocode

```c
__int64 __fastcall RtlConvertNtFilePathToWin32FilePath(const __m128i *a1, _QWORD *a2)
{
  const char *v4; // rax
  __int64 result; // rax
  __int64 v6; // rcx
  unsigned __int64 v7; // rsi
  unsigned __int64 v8; // rdx
  __m128i v9; // xmm2
  __int64 v10; // xmm1_8
  _BYTE v11[8]; // [rsp+20h] [rbp-E0h] BYREF
  __int128 v12; // [rsp+28h] [rbp-D8h] BYREF
  __int64 v13; // [rsp+38h] [rbp-C8h]
  const char *v14; // [rsp+40h] [rbp-C0h]
  _QWORD v15[3]; // [rsp+50h] [rbp-B0h] BYREF
  _QWORD v16[2]; // [rsp+68h] [rbp-98h]
  _QWORD v17[49]; // [rsp+78h] [rbp-88h]
  __int128 v18; // [rsp+200h] [rbp+100h] BYREF
  __int64 v19; // [rsp+210h] [rbp+110h]
  __m128i v20; // [rsp+218h] [rbp+118h]
  unsigned __int64 v21; // [rsp+228h] [rbp+128h]
  __int64 v22; // [rsp+230h] [rbp+130h]
  __int64 v23; // [rsp+238h] [rbp+138h]
  int *v24; // [rsp+240h] [rbp+140h]
  int v25; // [rsp+250h] [rbp+150h] BYREF

  v25 = 0;
  if ( a2 )
    *a2 = 0;
  if ( !a1 )
  {
    v13 = 456;
    *(_QWORD *)&v12 = "onecore\\base\\lstring\\path.cpp";
    *((_QWORD *)&v12 + 1) = "RtlConvertNtFilePathToWin32FilePath";
    v4 = "Not-null check failed: PathIn";
LABEL_5:
    v14 = v4;
    return Windows::ErrorHandling::Rtl::CBaseFrame<Windows::ErrorHandling::Rtl::CSimpleNtStatusCarryingFrame,long>::OriginateInvalidParameter_NullPointer(
             &v25,
             &v12);
  }
  if ( !a2 )
  {
    v13 = 457;
    *(_QWORD *)&v12 = "onecore\\base\\lstring\\path.cpp";
    *((_QWORD *)&v12 + 1) = "RtlConvertNtFilePathToWin32FilePath";
    v4 = "Not-null check failed: PathOut";
    goto LABEL_5;
  }
  v12 = 0;
  v13 = 0;
  result = RtlInitLUnicodeStringFromNullTerminatedString(2147352624, &v12);
  if ( (int)result >= 0 )
  {
    v6 = v12;
    if ( *(_WORD *)(v13 + 2 * ((unsigned __int64)v12 >> 1) - 2) == 92 )
      v6 = v12 - 2;
    v15[0] = 16;
    v15[1] = 18;
    v15[2] = L"\\??\\UNC\\";
    v16[0] = 4;
    v17[3] = L"\\??\\HardDisk";
    v17[7] = 20;
    v17[10] = 20;
    v17[8] = 22;
    v17[6] = L"\\\\?\\HardDisk";
    v17[11] = 22;
    v17[9] = L"\\??\\Volume";
    v17[31] = 22;
    v17[12] = L"\\\\?\\Volume";
    v17[43] = 22;
    v17[15] = L"\\??\\";
    v7 = 0;
    v16[1] = 6;
    v17[18] = &dword_1800AF424;
    v17[21] = L"\\DosDevices\\UNC\\";
    v17[27] = L"\\DosDevices\\";
    v17[30] = &dword_1800AF424;
    v17[33] = L"\\SystemRoot";
    v17[35] = *((_QWORD *)&v12 + 1);
    v17[39] = L"\\Device\\HarddiskVolume";
    v17[42] = L"\\\\?\\HarddiskVolume";
    v17[45] = L"\\Device\\Mup";
    v17[48] = L"\\\\?\\UNC";
    v17[0] = L"\\\\";
    v17[1] = 24;
    v17[2] = 26;
    v17[4] = 24;
    v17[5] = 26;
    v17[13] = 8;
    v17[14] = 10;
    v17[16] = 0;
    v17[17] = 2;
    v17[19] = 32;
    v17[20] = 34;
    v17[22] = 4;
    v17[23] = 6;
    v17[24] = L"\\\\";
    v17[25] = 24;
    v17[26] = 26;
    v17[28] = 0;
    v17[29] = 2;
    v17[32] = 24;
    v17[34] = v6;
    v17[36] = v13;
    v17[37] = 44;
    v17[38] = 46;
    v17[40] = 36;
    v17[41] = 38;
    v17[44] = 24;
    v17[46] = 14;
    v17[47] = 16;
    while ( v7 < 9 )
    {
      v11[0] = 0;
      result = RtlEqualLUnicodeStringPrefix(a1, &v15[6 * v7], RtlUpcaseUCSCharacter, v11);
      if ( (int)result < 0 )
        return result;
      if ( v11[0] )
        goto LABEL_18;
      ++v7;
    }
    if ( v7 == 9 )
    {
      v13 = 507;
      *(_QWORD *)&v12 = "onecore\\base\\lstring\\path.cpp";
      v14 = 0;
      *((_QWORD *)&v12 + 1) = "RtlConvertNtFilePathToWin32FilePath";
      return Windows::ErrorHandling::Rtl::CBaseFrame<Windows::ErrorHandling::Rtl::CSimpleNtStatusCarryingFrame,long>::OriginateNtStatus(
               &v25,
               &v12,
               3221225529LL);
    }
LABEL_18:
    v8 = v15[6 * v7];
    v9 = _mm_loadu_si128(a1);
    v10 = v17[6 * v7];
    v18 = *(_OWORD *)&v16[6 * v7];
    v21 = a1[1].m128i_i64[0] + v8;
    v19 = v10;
    v20 = _mm_sub_epi64(v9, _mm_unpacklo_epi64((__m128i)v8, (__m128i)v8));
    v22 = 2;
    v23 = 2;
    v24 = &dword_1800AF424;
    result = RtlConcatenateLUnicodeStrings(1, 3, &v18, a2);
    if ( (int)result >= 0 )
    {
      if ( *a2 > 2u )
        *a2 -= 2LL;
      return 0;
    }
  }
  return result;
}

```

## disassembly

```asm
0x180069a30  mov     [rsp-8+arg_10], rbx
0x180069a35  push    rbp
0x180069a36  push    rsi
0x180069a37  push    rdi
0x180069a38  push    r14
0x180069a3a  push    r15
0x180069a3c  lea     rbp, [rsp-160h]
0x180069a44  sub     rsp, 260h
0x180069a4b  mov     rax, cs:__security_cookie
0x180069a52  xor     rax, rsp
0x180069a55  mov     [rbp+180h+var_28], rax
0x180069a5c  mov     [rbp+180h+var_30], 0
0x180069a66  mov     rbx, rdx
0x180069a69  mov     r14, rcx
0x180069a6c  test    rdx, rdx
0x180069a6f  jz      short loc_180069A78
0x180069a71  mov     qword ptr [rdx], 0
0x180069a78  test    r14, r14
0x180069a7b  jnz     short loc_180069AC0
0x180069a7d  lea     rax, aOnecoreBaseLst; "onecore\\base\\lstring\\path.cpp"
0x180069a84  mov     [rsp+280h+var_248], 1C8h
0x180069a8d  mov     qword ptr [rsp+280h+var_258], rax
0x180069a92  lea     rax, aRtlconvertntfi_0; "RtlConvertNtFilePathToWin32FilePath"
0x180069a99  mov     qword ptr [rsp+280h+var_258+8], rax
0x180069a9e  lea     rax, aNotNullCheckFa_33; "Not-null check failed: PathIn"
0x180069aa5  lea     rdx, [rsp+280h+var_258]
0x180069aaa  mov     [rsp+280h+var_240], rax
0x180069aaf  lea     rcx, [rbp+180h+var_30]
0x180069ab6  call    ?OriginateInvalidParameter_NullPointer@?$CBaseFrame@UCSimpleNtStatusCarryingFrame@Rtl@ErrorHandling@Windows@@J@Rtl@ErrorHandling@Windows@@QEAAJAEBU_RTL_CALL_SITE@34@@Z; Windows::ErrorHandling::Rtl::CBaseFrame<Windows::ErrorHandling::Rtl::CSimpleNtStatusCarryingFrame,long>::OriginateInvalidParameter_NullPointer(Windows::ErrorHandling::_RTL_CALL_SITE const &)
0x180069abb  jmp     loc_180069E2A
0x180069ac0  test    rbx, rbx
0x180069ac3  jnz     short loc_180069AEF
0x180069ac5  lea     rax, aOnecoreBaseLst; "onecore\\base\\lstring\\path.cpp"
0x180069acc  mov     [rsp+280h+var_248], 1C9h
0x180069ad5  mov     qword ptr [rsp+280h+var_258], rax
0x180069ada  lea     rax, aRtlconvertntfi_0; "RtlConvertNtFilePathToWin32FilePath"
0x180069ae1  mov     qword ptr [rsp+280h+var_258+8], rax
0x180069ae6  lea     rax, aNotNullCheckFa_9; "Not-null check failed: PathOut"
0x180069aed  jmp     short loc_180069AA5
0x180069aef  xorps   xmm0, xmm0
0x180069af2  lea     rdx, [rsp+280h+var_258]
0x180069af7  xor     eax, eax
0x180069af9  mov     ecx, 7FFE0030h
0x180069afe  movups  [rsp+280h+var_258], xmm0
0x180069b03  mov     [rsp+280h+var_248], rax
0x180069b08  call    RtlInitLUnicodeStringFromNullTerminatedString
0x180069b0d  test    eax, eax
0x180069b0f  js      loc_180069E2A
0x180069b15  mov     rcx, qword ptr [rsp+280h+var_258]
0x180069b1a  mov     rdx, [rsp+280h+var_248]
0x180069b1f  mov     rax, rcx
0x180069b22  shr     rax, 1
0x180069b25  cmp     word ptr [rdx+rax*2-2], 5Ch ; '\'
0x180069b2b  jnz     short loc_180069B31
0x180069b2d  sub     rcx, 2
0x180069b31  mov     edi, 4
0x180069b36  mov     [rsp+280h+var_230], 10h
0x180069b3f  lea     rax, aUnc; "\\??\\UNC\\"
0x180069b46  mov     [rsp+280h+var_228], 12h
0x180069b4f  mov     [rsp+280h+var_220], rax
0x180069b54  lea     r10, asc_1800B1234; "\\\\"
0x180069b5b  lea     rax, aHarddisk; "\\??\\HardDisk"
0x180069b62  mov     qword ptr [rsp+280h+var_218], rdi
0x180069b67  mov     [rbp+180h+var_1F0], rax
0x180069b6b  lea     r8d, [rdi+10h]
0x180069b6f  lea     esi, [rdi+12h]
0x180069b72  mov     [rbp+180h+var_1D0], r8
0x180069b76  lea     r15d, [rdi+14h]
0x180069b7a  mov     [rbp+180h+var_1B8], r8
0x180069b7e  lea     rax, aHarddisk_0; "\\\\?\\HardDisk"
0x180069b85  mov     [rbp+180h+var_1C8], rsi
0x180069b89  mov     [rbp+180h+var_1D8], rax
0x180069b8d  lea     r9d, [rdi+16h]
0x180069b91  lea     rax, aVolume; "\\??\\Volume"
0x180069b98  mov     [rbp+180h+var_1B0], rsi
0x180069b9c  mov     [rbp+180h+var_1C0], rax
0x180069ba0  lea     r11d, [rdi+2]
0x180069ba4  lea     rax, aVolume_0; "\\\\?\\Volume"
0x180069bab  mov     [rbp+180h+var_110], rsi
0x180069baf  mov     [rbp+180h+var_1A8], rax
0x180069bb3  lea     r8d, [rdi-2]
0x180069bb7  lea     rax, asc_1800B76A0; "\\??\\"
0x180069bbe  mov     [rbp+180h+var_B0], rsi
0x180069bc5  mov     [rbp+180h+var_190], rax
0x180069bc9  xor     esi, esi
0x180069bcb  lea     rax, dword_1800AF424
0x180069bd2  mov     qword ptr [rsp+280h+var_218+8], r11
0x180069bd7  mov     [rbp+180h+var_178], rax
0x180069bdb  lea     rax, aDosdevicesUnc; "\\DosDevices\\UNC\\"
0x180069be2  mov     [rbp+180h+var_160], rax
0x180069be6  lea     rax, aDosdevices; "\\DosDevices\\"
0x180069bed  mov     [rbp+180h+var_130], rax
0x180069bf1  lea     rax, dword_1800AF424
0x180069bf8  mov     [rbp+180h+var_118], rax
0x180069bfc  lea     rax, aSystemroot; "\\SystemRoot"
0x180069c03  mov     [rbp+180h+var_100], rax
0x180069c0a  mov     rax, qword ptr [rsp+280h+var_258+8]
0x180069c0f  mov     [rbp+180h+var_F0], rax
0x180069c16  lea     rax, aDeviceHarddisk; "\\Device\\HarddiskVolume"
0x180069c1d  mov     [rbp+180h+var_D0], rax
0x180069c24  lea     rax, aHarddiskvolume; "\\\\?\\HarddiskVolume"
0x180069c2b  mov     [rbp+180h+var_B8], rax
0x180069c32  lea     rax, aDeviceMup; "\\Device\\Mup"
0x180069c39  mov     [rbp+180h+var_A0], rax
0x180069c40  lea     rax, aUnc_0; "\\\\?\\UNC"
0x180069c47  mov     [rbp+180h+var_88], rax
0x180069c4e  mov     [rsp+280h+var_208], r10
0x180069c53  mov     [rbp+180h+var_200], r15
0x180069c57  mov     [rbp+180h+var_1F8], r9
0x180069c5b  mov     [rbp+180h+var_1E8], r15
0x180069c5f  mov     [rbp+180h+var_1E0], r9
0x180069c63  mov     [rbp+180h+var_1A0], 8
0x180069c6b  mov     [rbp+180h+var_198], 0Ah
0x180069c73  mov     [rbp+180h+var_188], 0
0x180069c7b  mov     [rbp+180h+var_180], r8
0x180069c7f  mov     [rbp+180h+var_170], 20h ; ' '
0x180069c87  mov     [rbp+180h+var_168], 22h ; '"'
0x180069c8f  mov     [rbp+180h+var_158], rdi
0x180069c93  mov     [rbp+180h+var_150], r11
0x180069c97  mov     [rbp+180h+var_148], r10
0x180069c9b  mov     [rbp+180h+var_140], r15
0x180069c9f  mov     [rbp+180h+var_138], r9
0x180069ca3  mov     [rbp+180h+var_128], 0
0x180069cab  mov     [rbp+180h+var_120], r8
0x180069caf  mov     [rbp+180h+var_108], r15
0x180069cb3  mov     [rbp+180h+var_F8], rcx
0x180069cba  mov     [rbp+180h+var_E8], rdx
0x180069cc1  mov     [rbp+180h+var_E0], 2Ch ; ','
0x180069ccc  mov     [rbp+180h+var_D8], 2Eh ; '.'
0x180069cd7  mov     [rbp+180h+var_C8], 24h ; '$'
0x180069ce2  mov     [rbp+180h+var_C0], 26h ; '&'
0x180069ced  mov     [rbp+180h+var_A8], r15
0x180069cf4  mov     [rbp+180h+var_98], 0Eh
0x180069cff  mov     [rbp+180h+var_90], 10h
0x180069d0a  lea     rdi, [rsi+rsi*2]
0x180069d0e  shl     rdi, 4
0x180069d12  cmp     rsi, 9
0x180069d16  jnb     short loc_180069D4D
0x180069d18  lea     rdx, [rsp+280h+var_230]
0x180069d1d  mov     [rsp+280h+var_260], 0
0x180069d22  add     rdx, rdi
0x180069d25  lea     r9, [rsp+280h+var_260]
0x180069d2a  lea     r8, RtlUpcaseUCSCharacter
0x180069d31  mov     rcx, r14
0x180069d34  call    RtlEqualLUnicodeStringPrefix
0x180069d39  test    eax, eax
0x180069d3b  js      loc_180069E2A
0x180069d41  cmp     [rsp+280h+var_260], 0
0x180069d46  jnz     short loc_180069D95
0x180069d48  inc     rsi
0x180069d4b  jmp     short loc_180069D0A
0x180069d4d  jnz     short loc_180069D95
0x180069d4f  lea     rax, aOnecoreBaseLst; "onecore\\base\\lstring\\path.cpp"
0x180069d56  mov     [rsp+280h+var_248], 1FBh
0x180069d5f  mov     qword ptr [rsp+280h+var_258], rax
0x180069d64  lea     rdx, [rsp+280h+var_258]
0x180069d69  lea     rax, aRtlconvertntfi_0; "RtlConvertNtFilePathToWin32FilePath"
0x180069d70  mov     [rsp+280h+var_240], 0
0x180069d79  mov     r8d, 0C0000039h
0x180069d7f  mov     qword ptr [rsp+280h+var_258+8], rax
0x180069d84  lea     rcx, [rbp+180h+var_30]
0x180069d8b  call    ?OriginateNtStatus@?$CBaseFrame@UCSimpleNtStatusCarryingFrame@Rtl@ErrorHandling@Windows@@J@Rtl@ErrorHandling@Windows@@QEAAJAEBU_RTL_CALL_SITE@34@J@Z; Windows::ErrorHandling::Rtl::CBaseFrame<Windows::ErrorHandling::Rtl::CSimpleNtStatusCarryingFrame,long>::OriginateNtStatus(Windows::ErrorHandling::_RTL_CALL_SITE const &,long)
0x180069d90  jmp     loc_180069E2A
0x180069d95  movups  xmm0, [rsp+rdi+280h+var_218]
0x180069d9a  mov     rdx, [rsp+rdi+280h+var_230]
0x180069d9f  lea     rax, dword_1800AF424
0x180069da6  movdqu  xmm2, xmmword ptr [r14]
0x180069dab  lea     r8, [rbp+180h+var_80]
0x180069db2  mov     r9, rbx
0x180069db5  movsd   xmm1, [rsp+rdi+280h+var_208]
0x180069dbb  movaps  [rbp+180h+var_80], xmm0
0x180069dc2  movq    xmm0, rdx
0x180069dc7  add     rdx, [r14+10h]
0x180069dcb  mov     [rbp+180h+var_58], rdx
0x180069dd2  mov     edx, 3
0x180069dd7  punpcklqdq xmm0, xmm0
0x180069ddb  psubq   xmm2, xmm0
0x180069ddf  movsd   [rbp+180h+var_70], xmm1
0x180069de7  movdqu  [rbp+180h+var_68], xmm2
0x180069def  lea     ecx, [rdx-2]
0x180069df2  mov     [rbp+180h+var_50], 2
0x180069dfd  mov     [rbp+180h+var_48], 2
0x180069e08  mov     [rbp+180h+var_40], rax
0x180069e0f  call    RtlConcatenateLUnicodeStrings
0x180069e14  test    eax, eax
0x180069e16  js      short loc_180069E2A
0x180069e18  mov     rax, [rbx]
0x180069e1b  cmp     rax, 2
0x180069e1f  jbe     short loc_180069E28
0x180069e21  add     rax, 0FFFFFFFFFFFFFFFEh
0x180069e25  mov     [rbx], rax
0x180069e28  xor     eax, eax
0x180069e2a  mov     rcx, [rbp+180h+var_28]
0x180069e31  xor     rcx, rsp; StackCookie
0x180069e34  call    __security_check_cookie
0x180069e39  mov     rbx, [rsp+280h+arg_10]
0x180069e41  add     rsp, 260h
0x180069e48  pop     r15
0x180069e4a  pop     r14
0x180069e4c  pop     rdi
0x180069e4d  pop     rsi
0x180069e4e  pop     rbp
0x180069e4f  retn
```
