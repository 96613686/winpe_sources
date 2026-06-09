# LoadHashEntries(ConfigurationVersion,AutoOverlayConfigurationPtr &,void *)

- ea: `0x1800840f8`
- end: `0x1800843eb`
- name: `?LoadHashEntries@@YAJW4ConfigurationVersion@@AEAVAutoOverlayConfigurationPtr@@PEAX@Z`
- size: `755`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: `registry_config, installer_update`

## callers

- `0x1800829a0`

## callees

- `0x18001f5d4`
- `0x1800293a0`
- `0x18007ef80`
- `0x18007efac`
- `0x180081a50`
- `0x180081ba0`
- `0x1800821b8`
- `0x180082f64`
- `0x1800840f8`
- `0x180084c28`
- `0x180084f48`

## string_xrefs

- `0x180084177`: `onecore\base\servicing\overlayutil\read.cpp`
- `0x1800841d8`: `onecore\base\servicing\overlayutil\read.cpp`
- `0x18008424a`: `onecore\base\servicing\overlayutil\read.cpp`
- `0x18008430f`: `onecore\base\servicing\overlayutil\read.cpp`
- `0x18008434c`: `onecore\base\servicing\overlayutil\read.cpp`

## pseudocode

```c
__int64 __fastcall LoadHashEntries(int a1, __int64 *a2, void *a3)
{
  __m128i si128; // xmm6
  int v7; // ebx
  _QWORD *v8; // rbx
  unsigned __int64 v9; // rdi
  _QWORD *v10; // rdx
  __int64 v11; // r8
  int CimEntry; // esi
  unsigned __int64 v13; // rax
  const char *v15; // [rsp+40h] [rbp-C0h] BYREF
  unsigned __int64 v16; // [rsp+48h] [rbp-B8h]
  __int64 v17; // [rsp+50h] [rbp-B0h]
  const char *v18; // [rsp+58h] [rbp-A8h]
  _QWORD v19[4]; // [rsp+60h] [rbp-A0h] BYREF
  _QWORD v20[4]; // [rsp+80h] [rbp-80h] BYREF
  _QWORD v21[4]; // [rsp+A0h] [rbp-60h] BYREF
  _QWORD v22[4]; // [rsp+C0h] [rbp-40h] BYREF
  int v23; // [rsp+E0h] [rbp-20h] BYREF
  __m128i v24; // [rsp+E8h] [rbp-18h] BYREF
  __int64 v25; // [rsp+F8h] [rbp-8h]
  __m128i v26; // [rsp+100h] [rbp+0h] BYREF
  __int64 v27; // [rsp+110h] [rbp+10h]
  __m128i v28; // [rsp+118h] [rbp+18h] BYREF
  __int64 v29; // [rsp+128h] [rbp+28h]

  si128 = _mm_load_si128((const __m128i *)&_xmm_ffffffffffffffffffffffffffffffff);
  v23 = 0;
  v29 = -1;
  v28 = si128;
  v7 = OuEnumerateSubKeys((__int64)a3, v28.m128i_i64);
  if ( v7 >= 0 )
  {
    v8 = (_QWORD *)v28.m128i_i64[0];
    v9 = (v28.m128i_i64[1] - v28.m128i_i64[0]) >> 5;
    if ( v9 >= 0xFFFFFFFF )
    {
      v17 = 1045;
      v15 = "onecore\\base\\servicing\\overlayutil\\read.cpp";
      v16 = (unsigned __int64)"LoadHashEntries";
      v18 = "CimHashes.size() < 0xffffffffUL";
      v7 = Windows::ErrorHandling::Rtl::CBaseFrame<Windows::ErrorHandling::Rtl::CSimpleNtStatusCarryingFrame,long>::OriginateNtStatus(
             &v23,
             &v15,
             3221225659LL);
      goto LABEL_21;
    }
    v25 = -1;
    v24 = si128;
    if ( !utl::vector<AutoOverlayCimConfiguration,utl::allocator<AutoOverlayCimConfiguration>>::_Resize<,0>(
            &v24,
            (v28.m128i_i64[1] - v28.m128i_i64[0]) >> 5) )
    {
      v19[2] = 1048;
      v19[0] = "onecore\\base\\servicing\\overlayutil\\read.cpp";
      v19[1] = "LoadHashEntries";
      v19[3] = "CimEntries.resize(CimHashes.size())";
      v7 = Windows::ErrorHandling::Rtl::CBaseFrame<Windows::ErrorHandling::Rtl::CSimpleNtStatusCarryingFrame,long>::OriginateNtStatus(
             &v23,
             v19,
             3221225495LL);
LABEL_6:
      utl::vector<AutoOverlayCimConfiguration,utl::allocator<AutoOverlayCimConfiguration>>::_Uninit(v24.m128i_i64);
      goto LABEL_21;
    }
    v27 = -1;
    v26 = _mm_load_si128((const __m128i *)&_xmm_ffffffffffffffffffffffffffffffff);
    if ( (unsigned __int8)utl::vector<bool,utl::allocator<bool>>::_Resize<,0>(&v26, v9) )
    {
      while ( v8 != (_QWORD *)v28.m128i_i64[1] )
      {
        CimEntry = LoadCimEntry(a1, *(_DWORD *)(*a2 + 4), a3, v8, 0, v24.m128i_i64, v26.m128i_i64);
        if ( CimEntry < 0 )
        {
          utl::vector<_CIMFS_IMAGE_PATH,utl::allocator<_CIMFS_IMAGE_PATH>>::_Uninit((__int64)&v26);
          utl::vector<AutoOverlayCimConfiguration,utl::allocator<AutoOverlayCimConfiguration>>::_Uninit(v24.m128i_i64);
          v7 = CimEntry;
          goto LABEL_21;
        }
        v8 += 4;
      }
      v13 = 0xF0F0F0F0F0F0F0F1uLL * ((v24.m128i_i64[1] - v24.m128i_i64[0]) >> 3);
      if ( v13 )
      {
        if ( v9 == v13 )
        {
          v15 = (const char *)v24.m128i_i64[0];
          v16 = 0xF0F0F0F0F0F0F0F1uLL * ((v24.m128i_i64[1] - v24.m128i_i64[0]) >> 3);
          v7 = CopyOutConfig(a2, &v15);
          if ( v7 >= 0 )
          {
            utl::vector<_CIMFS_IMAGE_PATH,utl::allocator<_CIMFS_IMAGE_PATH>>::_Uninit((__int64)&v26);
            utl::vector<AutoOverlayCimConfiguration,utl::allocator<AutoOverlayCimConfiguration>>::_Uninit(v24.m128i_i64);
            v7 = 0;
            goto LABEL_21;
          }
          goto LABEL_10;
        }
        v22[2] = 1068;
        v22[0] = "onecore\\base\\servicing\\overlayutil\\read.cpp";
        v10 = v22;
        v11 = 3221225659LL;
        v22[1] = "LoadHashEntries";
        v22[3] = "CimHashes.size() == CimEntries.size()";
      }
      else
      {
        v21[2] = 1067;
        v21[0] = "onecore\\base\\servicing\\overlayutil\\read.cpp";
        v10 = v21;
        v11 = 3221225659LL;
        v21[1] = "LoadHashEntries";
        v21[3] = "CimEntries.size() > 0";
      }
    }
    else
    {
      v20[2] = 1051;
      v20[0] = "onecore\\base\\servicing\\overlayutil\\read.cpp";
      v10 = v20;
      v11 = 3221225495LL;
      v20[1] = "LoadHashEntries";
      v20[3] = "SeenCimIndexes.resize(CimHashes.size())";
    }
    v7 = Windows::ErrorHandling::Rtl::CBaseFrame<Windows::ErrorHandling::Rtl::CSimpleNtStatusCarryingFrame,long>::OriginateNtStatus(
           &v23,
           v10,
           v11);
LABEL_10:
    utl::vector<_CIMFS_IMAGE_PATH,utl::allocator<_CIMFS_IMAGE_PATH>>::_Uninit((__int64)&v26);
    goto LABEL_6;
  }
LABEL_21:
  utl::vector<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>,utl::allocator<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>>>::_Uninit(&v28);
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x1800840f8  mov     rax, rsp
0x1800840fb  push    rbp
0x1800840fc  push    rbx
0x1800840fd  push    rsi
0x1800840fe  push    rdi
0x1800840ff  push    r12
0x180084101  push    r14
0x180084103  push    r15
0x180084105  lea     rbp, [rsp-50h]
0x18008410a  sub     rsp, 150h
0x180084111  movaps  xmmword ptr [rax-48h], xmm6
0x180084115  mov     rax, cs:__security_cookie
0x18008411c  xor     rax, rsp
0x18008411f  mov     [rbp+80h+var_50], rax
0x180084123  movdqa  xmm6, cs:__xmm@ffffffffffffffffffffffffffffffff
0x18008412b  mov     r14, rdx
0x18008412e  mov     r12d, ecx
0x180084131  mov     [rbp+80h+var_A0], 0
0x180084138  or      rsi, 0FFFFFFFFFFFFFFFFh
0x18008413c  lea     rdx, [rbp+80h+var_68]
0x180084140  mov     rcx, r8
0x180084143  mov     [rbp+80h+var_58], rsi
0x180084147  movdqu  [rbp+80h+var_68], xmm6
0x18008414c  mov     r15, r8
0x18008414f  call    ?OuEnumerateSubKeys@@YAJPEAXAEAV?$vector@V?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@V?$allocator@V?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@@2@@utl@@@Z; OuEnumerateSubKeys(void *,utl::vector<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>,utl::allocator<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>>> &)
0x180084154  mov     ebx, eax
0x180084156  test    eax, eax
0x180084158  js      loc_1800843B9
0x18008415e  mov     rdi, qword ptr [rbp+80h+var_68+8]
0x180084162  mov     eax, 0FFFFFFFFh
0x180084167  mov     rbx, qword ptr [rbp+80h+var_68]
0x18008416b  sub     rdi, rbx
0x18008416e  sar     rdi, 5
0x180084172  cmp     rdi, rax
0x180084175  jb      short loc_1800841BF
0x180084177  lea     rax, aOnecoreBaseSer_3; "onecore\\base\\servicing\\overlayutil\\"...
0x18008417e  mov     [rsp+180h+var_130], 415h
0x180084187  mov     [rsp+180h+var_140], rax
0x18008418c  lea     rdx, [rsp+180h+var_140]
0x180084191  lea     rax, aLoadhashentrie; "LoadHashEntries"
0x180084198  mov     r8d, 0C00000BBh
0x18008419e  mov     [rsp+180h+var_138], rax
0x1800841a3  lea     rcx, [rbp+80h+var_A0]
0x1800841a7  lea     rax, aCimhashesSize0; "CimHashes.size() < 0xffffffffUL"
0x1800841ae  mov     [rsp+180h+var_128], rax
0x1800841b3  call    ?OriginateNtStatus@?$CBaseFrame@UCSimpleNtStatusCarryingFrame@Rtl@ErrorHandling@Windows@@J@Rtl@ErrorHandling@Windows@@QEAAJAEBU_RTL_CALL_SITE@34@J@Z; Windows::ErrorHandling::Rtl::CBaseFrame<Windows::ErrorHandling::Rtl::CSimpleNtStatusCarryingFrame,long>::OriginateNtStatus(Windows::ErrorHandling::_RTL_CALL_SITE const &,long)
0x1800841b8  mov     ebx, eax
0x1800841ba  jmp     loc_1800843B9
0x1800841bf  mov     rdx, rdi
0x1800841c2  mov     [rbp+80h+var_88], rsi
0x1800841c6  lea     rcx, [rbp+80h+var_98]
0x1800841ca  movdqu  [rbp+80h+var_98], xmm6
0x1800841cf  call    ??$_Resize@$$V$0A@@?$vector@UAutoOverlayCimConfiguration@@V?$allocator@UAutoOverlayCimConfiguration@@@utl@@@utl@@AEAA_N_K@Z; utl::vector<AutoOverlayCimConfiguration,utl::allocator<AutoOverlayCimConfiguration>>::_Resize<,0>(unsigned __int64)
0x1800841d4  test    al, al
0x1800841d6  jnz     short loc_180084229
0x1800841d8  lea     rax, aOnecoreBaseSer_3; "onecore\\base\\servicing\\overlayutil\\"...
0x1800841df  mov     [rsp+180h+var_110], 418h
0x1800841e8  mov     [rsp+180h+var_120], rax
0x1800841ed  lea     rdx, [rsp+180h+var_120]
0x1800841f2  lea     rax, aLoadhashentrie; "LoadHashEntries"
0x1800841f9  mov     r8d, 0C0000017h
0x1800841ff  mov     [rsp+180h+var_118], rax
0x180084204  lea     rcx, [rbp+80h+var_A0]
0x180084208  lea     rax, aCimentriesResi_0; "CimEntries.resize(CimHashes.size())"
0x18008420f  mov     [rsp+180h+var_108], rax
0x180084214  call    ?OriginateNtStatus@?$CBaseFrame@UCSimpleNtStatusCarryingFrame@Rtl@ErrorHandling@Windows@@J@Rtl@ErrorHandling@Windows@@QEAAJAEBU_RTL_CALL_SITE@34@J@Z; Windows::ErrorHandling::Rtl::CBaseFrame<Windows::ErrorHandling::Rtl::CSimpleNtStatusCarryingFrame,long>::OriginateNtStatus(Windows::ErrorHandling::_RTL_CALL_SITE const &,long)
0x180084219  mov     ebx, eax
0x18008421b  lea     rcx, [rbp+80h+var_98]
0x18008421f  call    ?_Uninit@?$vector@UAutoOverlayCimConfiguration@@V?$allocator@UAutoOverlayCimConfiguration@@@utl@@@utl@@AEAAXXZ; utl::vector<AutoOverlayCimConfiguration,utl::allocator<AutoOverlayCimConfiguration>>::_Uninit(void)
0x180084224  jmp     loc_1800843B9
0x180084229  movdqa  xmm0, cs:__xmm@ffffffffffffffffffffffffffffffff
0x180084231  lea     rcx, [rbp+80h+var_80]
0x180084235  mov     rdx, rdi
0x180084238  mov     [rbp+80h+var_70], rsi
0x18008423c  movdqu  [rbp+80h+var_80], xmm0
0x180084241  call    ??$_Resize@$$V$0A@@?$vector@_NV?$allocator@_N@utl@@@utl@@AEAA_N_K@Z; utl::vector<bool,utl::allocator<bool>>::_Resize<,0>(unsigned __int64)
0x180084246  test    al, al
0x180084248  jnz     short loc_180084293
0x18008424a  lea     rax, aOnecoreBaseSer_3; "onecore\\base\\servicing\\overlayutil\\"...
0x180084251  mov     [rbp+80h+var_F0], 41Bh
0x180084259  mov     [rbp+80h+var_100], rax
0x18008425d  lea     rdx, [rbp+80h+var_100]
0x180084261  lea     rax, aLoadhashentrie; "LoadHashEntries"
0x180084268  mov     r8d, 0C0000017h
0x18008426e  mov     [rbp+80h+var_F8], rax
0x180084272  lea     rax, aSeencimindexes_0; "SeenCimIndexes.resize(CimHashes.size())"
0x180084279  mov     [rbp+80h+var_E8], rax
0x18008427d  lea     rcx, [rbp+80h+var_A0]
0x180084281  call    ?OriginateNtStatus@?$CBaseFrame@UCSimpleNtStatusCarryingFrame@Rtl@ErrorHandling@Windows@@J@Rtl@ErrorHandling@Windows@@QEAAJAEBU_RTL_CALL_SITE@34@J@Z; Windows::ErrorHandling::Rtl::CBaseFrame<Windows::ErrorHandling::Rtl::CSimpleNtStatusCarryingFrame,long>::OriginateNtStatus(Windows::ErrorHandling::_RTL_CALL_SITE const &,long)
0x180084286  mov     ebx, eax
0x180084288  lea     rcx, [rbp+80h+var_80]
0x18008428c  call    ?_Uninit@?$vector@U_CIMFS_IMAGE_PATH@@V?$allocator@U_CIMFS_IMAGE_PATH@@@utl@@@utl@@AEAAXXZ; utl::vector<_CIMFS_IMAGE_PATH,utl::allocator<_CIMFS_IMAGE_PATH>>::_Uninit(void)
0x180084291  jmp     short loc_18008421B
0x180084293  cmp     rbx, qword ptr [rbp+80h+var_68+8]
0x180084297  jz      short loc_1800842ED
0x180084299  mov     rdx, [r14]
0x18008429c  lea     rax, [rbp+80h+var_80]
0x1800842a0  mov     [rsp+180h+var_150], rax
0x1800842a5  mov     r9, rbx
0x1800842a8  lea     rax, [rbp+80h+var_98]
0x1800842ac  mov     r8, r15
0x1800842af  mov     [rsp+180h+var_158], rax
0x1800842b4  mov     ecx, r12d
0x1800842b7  mov     edx, [rdx+4]
0x1800842ba  mov     [rsp+180h+var_160], 0
0x1800842c3  call    ?LoadCimEntry@@YAJW4ConfigurationVersion@@W4OverlayLoadType@@PEAXAEBV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@PEB_WAEAV?$vector@UAutoOverlayCimConfiguration@@V?$allocator@UAutoOverlayCimConfiguration@@@utl@@@4@AEAV?$vector@_NV?$allocator@_N@utl@@@4@@Z; LoadCimEntry(ConfigurationVersion,OverlayLoadType,void *,utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> const &,wchar_t const *,utl::vector<AutoOverlayCimConfiguration,utl::allocator<AutoOverlayCimConfiguration>> &,utl::vector<bool,utl::allocator<bool>> &)
0x1800842c8  mov     esi, eax
0x1800842ca  test    eax, eax
0x1800842cc  js      short loc_1800842D4
0x1800842ce  add     rbx, 20h ; ' '
0x1800842d2  jmp     short loc_180084293
0x1800842d4  lea     rcx, [rbp+80h+var_80]
0x1800842d8  call    ?_Uninit@?$vector@U_CIMFS_IMAGE_PATH@@V?$allocator@U_CIMFS_IMAGE_PATH@@@utl@@@utl@@AEAAXXZ; utl::vector<_CIMFS_IMAGE_PATH,utl::allocator<_CIMFS_IMAGE_PATH>>::_Uninit(void)
0x1800842dd  lea     rcx, [rbp+80h+var_98]
0x1800842e1  call    ?_Uninit@?$vector@UAutoOverlayCimConfiguration@@V?$allocator@UAutoOverlayCimConfiguration@@@utl@@@utl@@AEAAXXZ; utl::vector<AutoOverlayCimConfiguration,utl::allocator<AutoOverlayCimConfiguration>>::_Uninit(void)
0x1800842e6  mov     ebx, esi
0x1800842e8  jmp     loc_1800843B9
0x1800842ed  mov     rax, qword ptr [rbp+80h+var_98+8]
0x1800842f1  mov     rdx, 0F0F0F0F0F0F0F0F1h
0x1800842fb  mov     rcx, qword ptr [rbp+80h+var_98]
0x1800842ff  sub     rax, rcx
0x180084302  sar     rax, 3
0x180084306  imul    rax, rdx
0x18008430a  test    rax, rax
0x18008430d  jnz     short loc_180084347
0x18008430f  lea     rax, aOnecoreBaseSer_3; "onecore\\base\\servicing\\overlayutil\\"...
0x180084316  mov     [rbp+80h+var_D0], 42Bh
0x18008431e  mov     [rbp+80h+var_E0], rax
0x180084322  lea     rdx, [rbp+80h+var_E0]
0x180084326  lea     rax, aLoadhashentrie; "LoadHashEntries"
0x18008432d  mov     r8d, 0C00000BBh
0x180084333  mov     [rbp+80h+var_D8], rax
0x180084337  lea     rax, aCimentriesSize; "CimEntries.size() > 0"
0x18008433e  mov     [rbp+80h+var_C8], rax
0x180084342  jmp     loc_18008427D
0x180084347  cmp     rdi, rax
0x18008434a  jz      short loc_180084384
0x18008434c  lea     rax, aOnecoreBaseSer_3; "onecore\\base\\servicing\\overlayutil\\"...
0x180084353  mov     [rbp+80h+var_B0], 42Ch
0x18008435b  mov     [rbp+80h+var_C0], rax
0x18008435f  lea     rdx, [rbp+80h+var_C0]
0x180084363  lea     rax, aLoadhashentrie; "LoadHashEntries"
0x18008436a  mov     r8d, 0C00000BBh
0x180084370  mov     [rbp+80h+var_B8], rax
0x180084374  lea     rax, aCimhashesSizeC; "CimHashes.size() == CimEntries.size()"
0x18008437b  mov     [rbp+80h+var_A8], rax
0x18008437f  jmp     loc_18008427D
0x180084384  mov     [rsp+180h+var_140], rcx
0x180084389  lea     rdx, [rsp+180h+var_140]
0x18008438e  mov     rcx, r14
0x180084391  mov     [rsp+180h+var_138], rax
0x180084396  call    ?CopyOutConfig@@YAJAEAVAutoOverlayConfigurationPtr@@V?$span@UAutoOverlayCimConfiguration@@$0?0@utl@@@Z; CopyOutConfig(AutoOverlayConfigurationPtr &,utl::span<AutoOverlayCimConfiguration,-1>)
0x18008439b  lea     rcx, [rbp+80h+var_80]
0x18008439f  mov     ebx, eax
0x1800843a1  test    eax, eax
0x1800843a3  js      loc_18008428C
0x1800843a9  call    ?_Uninit@?$vector@U_CIMFS_IMAGE_PATH@@V?$allocator@U_CIMFS_IMAGE_PATH@@@utl@@@utl@@AEAAXXZ; utl::vector<_CIMFS_IMAGE_PATH,utl::allocator<_CIMFS_IMAGE_PATH>>::_Uninit(void)
0x1800843ae  lea     rcx, [rbp+80h+var_98]
0x1800843b2  call    ?_Uninit@?$vector@UAutoOverlayCimConfiguration@@V?$allocator@UAutoOverlayCimConfiguration@@@utl@@@utl@@AEAAXXZ; utl::vector<AutoOverlayCimConfiguration,utl::allocator<AutoOverlayCimConfiguration>>::_Uninit(void)
0x1800843b7  xor     ebx, ebx
0x1800843b9  lea     rcx, [rbp+80h+var_68]
0x1800843bd  call    ?_Uninit@?$vector@V?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@V?$allocator@V?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@@2@@utl@@AEAAXXZ; utl::vector<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>,utl::allocator<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>>>::_Uninit(void)
0x1800843c2  mov     eax, ebx
0x1800843c4  mov     rcx, [rbp+80h+var_50]
0x1800843c8  xor     rcx, rsp; StackCookie
0x1800843cb  call    __security_check_cookie
0x1800843d0  movaps  xmm6, [rsp+180h+var_40]
0x1800843d8  add     rsp, 150h
0x1800843df  pop     r15
0x1800843e1  pop     r14
0x1800843e3  pop     r12
0x1800843e5  pop     rdi
0x1800843e6  pop     rsi
0x1800843e7  pop     rbx
0x1800843e8  pop     rbp
0x1800843e9  retn
```
