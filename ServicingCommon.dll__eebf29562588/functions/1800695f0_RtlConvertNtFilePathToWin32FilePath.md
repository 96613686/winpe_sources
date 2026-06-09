# RtlConvertNtFilePathToWin32FilePath

- ea: `0x1800695f0`
- end: `0x180069a10`
- name: `RtlConvertNtFilePathToWin32FilePath`
- size: `1056`
- prototype: ``
- caller_count: `0`
- callee_count: `7`
- tags: ``

## callees

- `0x180004450`
- `0x180006010`
- `0x18001f4ac`
- `0x18001f5d4`
- `0x1800293a0`
- `0x1800655b0`
- `0x1800695f0`

## string_xrefs

- `0x18006963d`: `onecore\base\lstring\path.cpp`
- `0x180069685`: `onecore\base\lstring\path.cpp`
- `0x18006990e`: `onecore\base\lstring\path.cpp`
- `0x18006965e`: `Not-null check failed: PathIn`
- `0x1800696a6`: `Not-null check failed: PathOut`
- `0x180069652`: `RtlConvertNtFilePathToWin32FilePath`
- `0x18006969a`: `RtlConvertNtFilePathToWin32FilePath`
- `0x180069928`: `RtlConvertNtFilePathToWin32FilePath`

## pseudocode

```c
__int64 __fastcall RtlConvertNtFilePathToWin32FilePath(const __m128i *a1, _QWORD *a2)
{
  const char *v4; // rax
  __int64 result; // rax
  __int64 v6; // rcx
  __int64 v7; // rbx
  __m128i v8; // xmm2
  unsigned __int64 v9; // rdx
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
    v16[0] = 4;
    v15[2] = L"\\??\\UNC\\";
    v17[22] = 4;
    v17[3] = L"\\??\\HardDisk";
    v17[7] = 20;
    v17[10] = 20;
    v15[1] = 18;
    v17[0] = L"\\\\";
    v17[6] = L"\\\\?\\HardDisk";
    v16[1] = 6;
    v17[9] = L"\\??\\Volume";
    v17[1] = 24;
    v17[12] = L"\\\\?\\Volume";
    v7 = 0;
    v17[2] = 26;
    v17[15] = L"\\??\\";
    v17[18] = &dword_1800AFA74;
    v17[21] = L"\\DosDevices\\UNC\\";
    v17[27] = L"\\DosDevices\\";
    v17[30] = &dword_1800AFA74;
    v17[33] = L"\\SystemRoot";
    v17[35] = *((_QWORD *)&v12 + 1);
    v17[39] = L"\\Device\\HarddiskVolume";
    v17[42] = L"\\\\?\\HarddiskVolume";
    v17[45] = L"\\Device\\Mup";
    v17[48] = L"\\\\?\\UNC";
    v17[4] = 24;
    v17[5] = 26;
    v17[8] = 22;
    v17[11] = 22;
    v17[13] = 8;
    v17[14] = 10;
    v17[16] = 0;
    v17[17] = 2;
    v17[19] = 32;
    v17[20] = 34;
    v17[23] = 6;
    v17[24] = L"\\\\";
    v17[25] = 24;
    v17[26] = 26;
    v17[28] = 0;
    v17[29] = 2;
    v17[31] = 22;
    v17[32] = 24;
    v17[34] = v6;
    v17[36] = v13;
    v17[37] = 44;
    v17[38] = 46;
    v17[40] = 36;
    v17[41] = 38;
    v17[43] = 22;
    v17[44] = 24;
    v17[46] = 14;
    v17[47] = 16;
    while ( 1 )
    {
      v11[0] = 0;
      result = RtlEqualLUnicodeStringPrefix(a1, &v15[6 * v7], RtlUpcaseUCSCharacter, v11);
      if ( (int)result < 0 )
        break;
      if ( v11[0] )
        goto LABEL_17;
      if ( (unsigned __int64)++v7 >= 9 )
      {
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
LABEL_17:
        v8 = _mm_loadu_si128(a1);
        v22 = 2;
        v23 = 2;
        v9 = v15[6 * v7];
        v10 = v17[6 * v7];
        v18 = *(_OWORD *)&v16[6 * v7];
        v21 = a1[1].m128i_i64[0] + v9;
        v19 = v10;
        v20 = _mm_sub_epi64(v8, _mm_unpacklo_epi64((__m128i)v9, (__m128i)v9));
        v24 = &dword_1800AFA74;
        result = RtlConcatenateLUnicodeStrings(1, 3, &v18, a2);
        if ( (int)result >= 0 )
        {
          if ( *a2 > 2u )
            *a2 -= 2LL;
          return 0;
        }
        return result;
      }
    }
  }
  return result;
}

```

## disassembly

```asm
0x1800695f0  mov     [rsp-8+arg_10], rbx
0x1800695f5  push    rbp
0x1800695f6  push    rsi
0x1800695f7  push    rdi
0x1800695f8  push    r14
0x1800695fa  push    r15
0x1800695fc  lea     rbp, [rsp-160h]
0x180069604  sub     rsp, 260h
0x18006960b  mov     rax, cs:__security_cookie
0x180069612  xor     rax, rsp
0x180069615  mov     [rbp+180h+var_28], rax
0x18006961c  mov     [rbp+180h+var_30], 0
0x180069626  mov     rdi, rdx
0x180069629  mov     rsi, rcx
0x18006962c  test    rdx, rdx
0x18006962f  jz      short loc_180069638
0x180069631  mov     qword ptr [rdx], 0
0x180069638  test    rsi, rsi
0x18006963b  jnz     short loc_180069680
0x18006963d  lea     rax, aOnecoreBaseLst; "onecore\\base\\lstring\\path.cpp"
0x180069644  mov     [rsp+280h+var_248], 1C8h
0x18006964d  mov     qword ptr [rsp+280h+var_258], rax
0x180069652  lea     rax, aRtlconvertntfi_0; "RtlConvertNtFilePathToWin32FilePath"
0x180069659  mov     qword ptr [rsp+280h+var_258+8], rax
0x18006965e  lea     rax, aNotNullCheckFa_33; "Not-null check failed: PathIn"
0x180069665  lea     rdx, [rsp+280h+var_258]
0x18006966a  mov     [rsp+280h+var_240], rax
0x18006966f  lea     rcx, [rbp+180h+var_30]
0x180069676  call    ?OriginateInvalidParameter_NullPointer@?$CBaseFrame@UCSimpleNtStatusCarryingFrame@Rtl@ErrorHandling@Windows@@J@Rtl@ErrorHandling@Windows@@QEAAJAEBU_RTL_CALL_SITE@34@@Z; Windows::ErrorHandling::Rtl::CBaseFrame<Windows::ErrorHandling::Rtl::CSimpleNtStatusCarryingFrame,long>::OriginateInvalidParameter_NullPointer(Windows::ErrorHandling::_RTL_CALL_SITE const &)
0x18006967b  jmp     loc_1800699E9
0x180069680  test    rdi, rdi
0x180069683  jnz     short loc_1800696AF
0x180069685  lea     rax, aOnecoreBaseLst; "onecore\\base\\lstring\\path.cpp"
0x18006968c  mov     [rsp+280h+var_248], 1C9h
0x180069695  mov     qword ptr [rsp+280h+var_258], rax
0x18006969a  lea     rax, aRtlconvertntfi_0; "RtlConvertNtFilePathToWin32FilePath"
0x1800696a1  mov     qword ptr [rsp+280h+var_258+8], rax
0x1800696a6  lea     rax, aNotNullCheckFa_9; "Not-null check failed: PathOut"
0x1800696ad  jmp     short loc_180069665
0x1800696af  xorps   xmm0, xmm0
0x1800696b2  lea     rdx, [rsp+280h+var_258]
0x1800696b7  xor     eax, eax
0x1800696b9  mov     ecx, 7FFE0030h
0x1800696be  movups  [rsp+280h+var_258], xmm0
0x1800696c3  mov     [rsp+280h+var_248], rax
0x1800696c8  call    RtlInitLUnicodeStringFromNullTerminatedString
0x1800696cd  test    eax, eax
0x1800696cf  js      loc_1800699E9
0x1800696d5  mov     rcx, qword ptr [rsp+280h+var_258]
0x1800696da  mov     rdx, [rsp+280h+var_248]
0x1800696df  mov     rax, rcx
0x1800696e2  shr     rax, 1
0x1800696e5  cmp     word ptr [rdx+rax*2-2], 5Ch ; '\'
0x1800696eb  jnz     short loc_1800696F1
0x1800696ed  sub     rcx, 2
0x1800696f1  mov     ebx, 4
0x1800696f6  mov     [rsp+280h+var_230], 10h
0x1800696ff  lea     rax, aUnc; "\\??\\UNC\\"
0x180069706  mov     qword ptr [rsp+280h+var_218], rbx
0x18006970b  mov     [rsp+280h+var_220], rax
0x180069710  lea     r10, asc_1800B17EC; "\\\\"
0x180069717  lea     rax, aHarddisk; "\\??\\HardDisk"
0x18006971e  mov     [rbp+180h+var_158], rbx
0x180069722  mov     [rbp+180h+var_1F0], rax
0x180069726  lea     r8d, [rbx+10h]
0x18006972a  lea     r15d, [rbx+14h]
0x18006972e  mov     [rbp+180h+var_1D0], r8
0x180069732  lea     r14d, [rbx+12h]
0x180069736  mov     [rbp+180h+var_1B8], r8
0x18006973a  lea     r9d, [rbx+16h]
0x18006973e  mov     [rsp+280h+var_228], 12h
0x180069747  lea     rax, aHarddisk_0; "\\\\?\\HardDisk"
0x18006974e  mov     [rsp+280h+var_208], r10
0x180069753  mov     [rbp+180h+var_1D8], rax
0x180069757  lea     r11d, [rbx+2]
0x18006975b  lea     rax, aVolume; "\\??\\Volume"
0x180069762  mov     qword ptr [rsp+280h+var_218+8], r11
0x180069767  mov     [rbp+180h+var_1C0], rax
0x18006976b  lea     r8d, [rbx-2]
0x18006976f  lea     rax, aVolume_0; "\\\\?\\Volume"
0x180069776  mov     [rbp+180h+var_200], r15
0x18006977a  mov     [rbp+180h+var_1A8], rax
0x18006977e  xor     ebx, ebx
0x180069780  lea     rax, asc_1800B9170; "\\??\\"
0x180069787  mov     [rbp+180h+var_1F8], r9
0x18006978b  mov     [rbp+180h+var_190], rax
0x18006978f  lea     rax, dword_1800AFA74
0x180069796  mov     [rbp+180h+var_178], rax
0x18006979a  lea     rax, aDosdevicesUnc; "\\DosDevices\\UNC\\"
0x1800697a1  mov     [rbp+180h+var_160], rax
0x1800697a5  lea     rax, aDosdevices; "\\DosDevices\\"
0x1800697ac  mov     [rbp+180h+var_130], rax
0x1800697b0  lea     rax, dword_1800AFA74
0x1800697b7  mov     [rbp+180h+var_118], rax
0x1800697bb  lea     rax, aSystemroot; "\\SystemRoot"
0x1800697c2  mov     [rbp+180h+var_100], rax
0x1800697c9  mov     rax, qword ptr [rsp+280h+var_258+8]
0x1800697ce  mov     [rbp+180h+var_F0], rax
0x1800697d5  lea     rax, aDeviceHarddisk; "\\Device\\HarddiskVolume"
0x1800697dc  mov     [rbp+180h+var_D0], rax
0x1800697e3  lea     rax, aHarddiskvolume; "\\\\?\\HarddiskVolume"
0x1800697ea  mov     [rbp+180h+var_B8], rax
0x1800697f1  lea     rax, aDeviceMup; "\\Device\\Mup"
0x1800697f8  mov     [rbp+180h+var_A0], rax
0x1800697ff  lea     rax, aUnc_0; "\\\\?\\UNC"
0x180069806  mov     [rbp+180h+var_88], rax
0x18006980d  mov     [rbp+180h+var_1E8], r15
0x180069811  mov     [rbp+180h+var_1E0], r9
0x180069815  mov     [rbp+180h+var_1C8], r14
0x180069819  mov     [rbp+180h+var_1B0], r14
0x18006981d  mov     [rbp+180h+var_1A0], 8
0x180069825  mov     [rbp+180h+var_198], 0Ah
0x18006982d  mov     [rbp+180h+var_188], 0
0x180069835  mov     [rbp+180h+var_180], r8
0x180069839  mov     [rbp+180h+var_170], 20h ; ' '
0x180069841  mov     [rbp+180h+var_168], 22h ; '"'
0x180069849  mov     [rbp+180h+var_150], r11
0x18006984d  mov     [rbp+180h+var_148], r10
0x180069851  mov     [rbp+180h+var_140], r15
0x180069855  mov     [rbp+180h+var_138], r9
0x180069859  mov     [rbp+180h+var_128], 0
0x180069861  mov     [rbp+180h+var_120], r8
0x180069865  mov     [rbp+180h+var_110], r14
0x180069869  mov     [rbp+180h+var_108], r15
0x18006986d  mov     [rbp+180h+var_F8], rcx
0x180069874  mov     [rbp+180h+var_E8], rdx
0x18006987b  mov     [rbp+180h+var_E0], 2Ch ; ','
0x180069886  mov     [rbp+180h+var_D8], 2Eh ; '.'
0x180069891  mov     [rbp+180h+var_C8], 24h ; '$'
0x18006989c  mov     [rbp+180h+var_C0], 26h ; '&'
0x1800698a7  mov     [rbp+180h+var_B0], r14
0x1800698ae  mov     [rbp+180h+var_A8], r15
0x1800698b5  mov     [rbp+180h+var_98], 0Eh
0x1800698c0  mov     [rbp+180h+var_90], 10h
0x1800698cb  lea     rax, [rbx+rbx*2]
0x1800698cf  mov     [rsp+280h+var_260], 0
0x1800698d4  shl     rax, 4
0x1800698d8  lea     rdx, [rsp+280h+var_230]
0x1800698dd  add     rdx, rax
0x1800698e0  lea     r9, [rsp+280h+var_260]
0x1800698e5  lea     r8, RtlUpcaseUCSCharacter
0x1800698ec  mov     rcx, rsi
0x1800698ef  call    RtlEqualLUnicodeStringPrefix
0x1800698f4  test    eax, eax
0x1800698f6  js      loc_1800699E9
0x1800698fc  cmp     [rsp+280h+var_260], 0
0x180069901  jnz     short loc_180069954
0x180069903  inc     rbx
0x180069906  cmp     rbx, 9
0x18006990a  jb      short loc_1800698CB
0x18006990c  jnz     short loc_180069954
0x18006990e  lea     rax, aOnecoreBaseLst; "onecore\\base\\lstring\\path.cpp"
0x180069915  mov     [rsp+280h+var_248], 1FBh
0x18006991e  mov     qword ptr [rsp+280h+var_258], rax
0x180069923  lea     rdx, [rsp+280h+var_258]
0x180069928  lea     rax, aRtlconvertntfi_0; "RtlConvertNtFilePathToWin32FilePath"
0x18006992f  mov     [rsp+280h+var_240], 0
0x180069938  mov     r8d, 0C0000039h
0x18006993e  mov     qword ptr [rsp+280h+var_258+8], rax
0x180069943  lea     rcx, [rbp+180h+var_30]
0x18006994a  call    ?OriginateNtStatus@?$CBaseFrame@UCSimpleNtStatusCarryingFrame@Rtl@ErrorHandling@Windows@@J@Rtl@ErrorHandling@Windows@@QEAAJAEBU_RTL_CALL_SITE@34@J@Z; Windows::ErrorHandling::Rtl::CBaseFrame<Windows::ErrorHandling::Rtl::CSimpleNtStatusCarryingFrame,long>::OriginateNtStatus(Windows::ErrorHandling::_RTL_CALL_SITE const &,long)
0x18006994f  jmp     loc_1800699E9
0x180069954  movdqu  xmm2, xmmword ptr [rsi]
0x180069958  lea     rax, [rbx+rbx*2]
0x18006995c  mov     r9, rdi
0x18006995f  add     rax, rax
0x180069962  lea     r8, [rbp+180h+var_80]
0x180069969  mov     ebx, 2
0x18006996e  mov     [rbp+180h+var_50], rbx
0x180069975  mov     [rbp+180h+var_48], rbx
0x18006997c  mov     rdx, [rsp+rax*8+280h+var_230]
0x180069981  movups  xmm0, [rsp+rax*8+280h+var_218]
0x180069986  lea     ecx, [rbx-1]
0x180069989  movsd   xmm1, [rsp+rax*8+280h+var_208]
0x18006998f  lea     rax, dword_1800AFA74
0x180069996  movaps  [rbp+180h+var_80], xmm0
0x18006999d  movq    xmm0, rdx
0x1800699a2  add     rdx, [rsi+10h]
0x1800699a6  punpcklqdq xmm0, xmm0
0x1800699aa  psubq   xmm2, xmm0
0x1800699ae  mov     [rbp+180h+var_58], rdx
0x1800699b5  lea     edx, [rbx+1]
0x1800699b8  movsd   [rbp+180h+var_70], xmm1
0x1800699c0  movdqu  [rbp+180h+var_68], xmm2
0x1800699c8  mov     [rbp+180h+var_40], rax
0x1800699cf  call    RtlConcatenateLUnicodeStrings
0x1800699d4  test    eax, eax
0x1800699d6  js      short loc_1800699E9
0x1800699d8  mov     rax, [rdi]
0x1800699db  cmp     rax, rbx
0x1800699de  jbe     short loc_1800699E7
0x1800699e0  add     rax, 0FFFFFFFFFFFFFFFEh
0x1800699e4  mov     [rdi], rax
0x1800699e7  xor     eax, eax
0x1800699e9  mov     rcx, [rbp+180h+var_28]
0x1800699f0  xor     rcx, rsp; StackCookie
0x1800699f3  call    __security_check_cookie
0x1800699f8  mov     rbx, [rsp+280h+arg_10]
0x180069a00  add     rsp, 260h
0x180069a07  pop     r15
0x180069a09  pop     r14
0x180069a0b  pop     rdi
0x180069a0c  pop     rsi
0x180069a0d  pop     rbp
0x180069a0e  retn
```
