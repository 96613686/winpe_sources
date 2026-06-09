# _CacheMsiComponents(std::unordered_map<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,std::vector<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,std::allocator<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>>,std::hash<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>,std::equal_to<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>,std::allocator<std::pair<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const,std::vector<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,std::allocator<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>>>>> &)

- ea: `0x18004937c`
- end: `0x180049950`
- name: `?_CacheMsiComponents@@YAXAEAV?$unordered_map@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@2@U?$hash@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@U?$equal_to@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@2@@std@@@2@@std@@@Z`
- size: `1492`
- prototype: ``
- caller_count: `1`
- callee_count: `23`
- tags: `installer_update, broker_com_uri`

## callers

- `0x180048628`

## callees

- `0x180001cf0`
- `0x1800020a0`
- `0x180002d1c`
- `0x180002d84`
- `0x18000b5fc`
- `0x18000b720`
- `0x18000bbbc`
- `0x18000dfd8`
- `0x18000e064`
- `0x18000e428`
- `0x18001067c`
- `0x1800118f4`
- `0x180021dd4`
- `0x1800237b8`
- `0x18002649c`
- `0x1800465cc`
- `0x180046c94`
- `0x180047190`
- `0x180047410`
- `0x180048170`
- `0x1800487a8`
- `0x18004937c`
- `0x18004a6f8`

## string_xrefs

- `0x1800493dc`: `SOFTWARE\Microsoft\Windows\CurrentVersion\Installer\UserData`
- `0x18004948c`: `\Components`
- `0x180049476`: `SOFTWARE\Microsoft\Windows\CurrentVersion\Installer\UserData\`
- `0x18004953e`: `SOFTWARE\Microsoft\Windows\CurrentVersion\Installer\UserData\`
- `0x180049552`: `\Components\`

## pseudocode

```c
// Hidden C++ exception states: #wind=21
__int64 __fastcall _CacheMsiComponents(__int64 a1)
{
  int v2; // ebx
  __int64 v3; // rdx
  __int64 v4; // r8
  _QWORD *v5; // rdi
  __int64 v6; // r14
  __m128i si128; // xmm6
  __int64 v8; // rax
  __int64 v9; // rdx
  __int64 v10; // r8
  __int64 i; // r12
  _QWORD *v12; // rax
  __int64 v13; // rax
  __int64 v14; // rax
  __int64 v15; // rcx
  __int64 *v16; // rcx
  __int64 v17; // rsi
  __int64 v18; // rax
  __int64 v19; // r15
  _QWORD *ThreadLocalStoragePointer; // rdi
  _QWORD *v21; // rdx
  __int64 v22; // r9
  unsigned __int64 j; // rcx
  __int64 v24; // rcx
  __int64 v25; // r14
  __int64 v26; // rax
  __int64 v27; // rdx
  __int64 v29; // [rsp+28h] [rbp-E0h]
  _QWORD *v30; // [rsp+30h] [rbp-D8h]
  __int64 v31; // [rsp+38h] [rbp-D0h]
  _QWORD *v32; // [rsp+48h] [rbp-C0h]
  __int128 v33; // [rsp+50h] [rbp-B8h] BYREF
  __int64 v34; // [rsp+60h] [rbp-A8h]
  __int128 v35; // [rsp+68h] [rbp-A0h] BYREF
  __int64 v36; // [rsp+78h] [rbp-90h]
  _QWORD v37[3]; // [rsp+80h] [rbp-88h] BYREF
  _QWORD *v38; // [rsp+98h] [rbp-70h] BYREF
  _QWORD *v39; // [rsp+A0h] [rbp-68h]
  _QWORD v40[4]; // [rsp+B0h] [rbp-58h] BYREF
  char v41[8]; // [rsp+D0h] [rbp-38h] BYREF
  __int128 v42; // [rsp+D8h] [rbp-30h]
  char v43[16]; // [rsp+E8h] [rbp-20h] BYREF
  _QWORD v44[2]; // [rsp+F8h] [rbp-10h] BYREF
  __int64 v45; // [rsp+108h] [rbp+0h]
  unsigned __int64 v46; // [rsp+110h] [rbp+8h]
  _BYTE v47[16]; // [rsp+118h] [rbp+10h] BYREF
  __int64 v48; // [rsp+128h] [rbp+20h]
  _QWORD v49[2]; // [rsp+138h] [rbp+30h] BYREF
  __m128i v50; // [rsp+148h] [rbp+40h]
  __int128 v51; // [rsp+158h] [rbp+50h] BYREF
  __int128 v52; // [rsp+168h] [rbp+60h]
  __int128 v53; // [rsp+178h] [rbp+70h] BYREF
  __int128 v54; // [rsp+188h] [rbp+80h]
  __int128 Src; // [rsp+198h] [rbp+90h] BYREF
  __int128 v56; // [rsp+1A8h] [rbp+A0h]
  _OWORD v57[2]; // [rsp+1B8h] [rbp+B0h] BYREF
  _BYTE v58[32]; // [rsp+1D8h] [rbp+D0h] BYREF
  _BYTE v59[32]; // [rsp+1F8h] [rbp+F0h] BYREF

  v40[3] = -2;
  v2 = 0;
  memset(v57, 0, sizeof(v57));
  std::wstring::_Construct<1,unsigned short const *>(
    v57,
    L"SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\Installer\\UserData",
    60);
  AppCompatUtility::RegOperations::GetSubkeyNamesOrDefault(&v38, -2147483646, v57);
  std::wstring::~wstring(v57);
  v5 = v38;
  v32 = v38;
  if ( v38 != v39 )
  {
    v6 = (unsigned int)tls_index;
    si128 = _mm_load_si128((const __m128i *)&_xmm);
    do
    {
      if ( (unsigned __int64)(0x7FFFFFFFFFFFFFFELL - v5[2]) < 0x3D )
        std::_Xlen_string();
      std::wstring::wstring(v58, v3, v4, L"SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\Installer\\UserData\\");
      v8 = std::wstring::append(v58, L"\\Components");
      v51 = 0;
      v52 = 0;
      v51 = *(_OWORD *)v8;
      v52 = *(_OWORD *)(v8 + 16);
      *(_QWORD *)(v8 + 16) = 0;
      *(_QWORD *)(v8 + 24) = 7;
      *(_WORD *)v8 = 0;
      v2 |= 3u;
      AppCompatUtility::RegOperations::GetSubkeyNamesOrDefault(v37, -2147483646, &v51);
      std::wstring::~wstring(&v51);
      std::wstring::~wstring(v58);
      for ( i = v37[0]; i != v37[1]; i += 32 )
      {
        if ( (unsigned __int64)(0x7FFFFFFFFFFFFFFELL - v5[2]) < 0x3D )
          std::_Xlen_string();
        if ( v5[3] <= 7u )
          v12 = v5;
        else
          v12 = (_QWORD *)*v5;
        v31 = v5[2];
        v30 = v12;
        v29 = 61;
        std::wstring::wstring(v59, v9, v10, L"SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\Installer\\UserData\\");
        v13 = std::wstring::append(v59, L"\\Components\\");
        Src = 0;
        v56 = 0;
        Src = *(_OWORD *)v13;
        v56 = *(_OWORD *)(v13 + 16);
        *(_QWORD *)(v13 + 16) = 0;
        *(_QWORD *)(v13 + 24) = 7;
        *(_WORD *)v13 = 0;
        v14 = std::wstring::append(&Src);
        v53 = 0;
        v54 = 0;
        v53 = *(_OWORD *)v14;
        v54 = *(_OWORD *)(v14 + 16);
        *(_QWORD *)(v14 + 16) = 0;
        *(_QWORD *)(v14 + 24) = 7;
        *(_WORD *)v14 = 0;
        v35 = 0;
        v36 = 0;
        if ( (unsigned int)AppCompatUtility::RegOperations::GetStringValues(v15, &v53, &v35) )
        {
          v42 = 0;
          v16 = (__int64 *)v41;
          v2 |= 0xDCu;
          v17 = 0;
        }
        else
        {
          v16 = (__int64 *)std::vector<std::pair<std::wstring,std::wstring>>::vector<std::pair<std::wstring,std::wstring>>(
                             v44,
                             &v35);
          v2 |= 0xBCu;
          v17 = *v16;
        }
        v18 = v16[2];
        v16[2] = 0;
        v19 = v16[1];
        v16[1] = 0;
        *v16 = 0;
        v40[0] = v17;
        v40[1] = v19;
        v40[2] = v18;
        if ( (v2 & 0x40) != 0 )
        {
          v2 &= ~0x40u;
          std::vector<std::pair<std::wstring,std::wstring>>::_Tidy(v41);
        }
        if ( (v2 & 0x20) != 0 )
        {
          v2 &= ~0x20u;
          std::vector<std::pair<std::wstring,std::wstring>>::_Tidy(v44);
        }
        std::vector<std::pair<std::wstring,std::wstring>>::_Tidy(&v35);
        std::wstring::~wstring(&v53);
        std::wstring::~wstring(&Src);
        std::wstring::~wstring(v59);
        if ( v17 != v19 )
        {
          ThreadLocalStoragePointer = NtCurrentTeb()->ThreadLocalStoragePointer;
          do
          {
            std::wstring::wstring(v47, v17);
            std::wstring::wstring(v49, v17 + 32);
            if ( v48 == 32 )
            {
              if ( __TSS0__1___IsValidMsiProductId__YA_NAEBV__basic_string_GU__char_traits_G_std__V__allocator_G_2__std___Z_4HA > *(_DWORD *)(ThreadLocalStoragePointer[v6] + 4LL) )
              {
                Init_thread_header(&__TSS0__1___IsValidMsiProductId__YA_NAEBV__basic_string_GU__char_traits_G_std__V__allocator_G_2__std___Z_4HA);
                if ( __TSS0__1___IsValidMsiProductId__YA_NAEBV__basic_string_GU__char_traits_G_std__V__allocator_G_2__std___Z_4HA == -1 )
                {
                  std::basic_regex<unsigned short,std::regex_traits<unsigned short>>::basic_regex<unsigned short,std::regex_traits<unsigned short>>(
                    &`_IsValidMsiProductId'::`2'::Pattern,
                    L"[?a-zA-Z0-9]{32}",
                    256);
                  atexit(`_IsValidMsiProductId'::`2'::`dynamic atexit destructor for 'Pattern'');
                  Init_thread_footer(&__TSS0__1___IsValidMsiProductId__YA_NAEBV__basic_string_GU__char_traits_G_std__V__allocator_G_2__std___Z_4HA);
                }
              }
              if ( (unsigned __int8)std::regex_match<std::char_traits<unsigned short>,std::allocator<unsigned short>,unsigned short,std::regex_traits<unsigned short>>(v47)
                && (unsigned __int64)(v50.m128i_i64[0] - 1) <= 0x103 )
              {
                _ToProductCode(v44);
                v21 = v44;
                if ( v46 > 7 )
                  v21 = (_QWORD *)v44[0];
                v22 = 0xCBF29CE484222325uLL;
                for ( j = 0; j < 2 * v45; ++j )
                  v22 = 0x100000001B3LL * (*((unsigned __int8 *)v21 + j) ^ (unsigned __int64)v22);
                v24 = *(_QWORD *)(std::_Hash<std::_Uset_traits<std::wstring,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::wstring>,0>>::_Find_last<std::wstring>(
                                    a1,
                                    v43,
                                    v44,
                                    v22,
                                    v29,
                                    v30,
                                    v31)
                                + 8);
                if ( !v24 || v24 == *(_QWORD *)(a1 + 8) )
                {
                  v33 = 0;
                  v34 = 0;
                  v25 = std::unordered_map<std::wstring,std::vector<std::wstring>>::operator[](a1, v44);
                  if ( (__int128 *)v25 != &v33 )
                  {
                    std::vector<std::wstring>::_Tidy(v25);
                    *(_QWORD *)v25 = 0;
                    *(_QWORD *)(v25 + 8) = 0;
                    *(_QWORD *)(v25 + 16) = 0;
                    v33 = 0;
                    v34 = 0;
                  }
                  std::vector<std::wstring>::_Tidy(&v33);
                  v6 = (unsigned int)tls_index;
                }
                v26 = std::unordered_map<std::wstring,std::vector<std::wstring>>::operator[](a1, v44);
                v27 = *(_QWORD *)(v26 + 8);
                if ( v27 == *(_QWORD *)(v26 + 16) )
                {
                  std::vector<std::wstring>::_Emplace_reallocate<std::wstring>(v26, v27, v49);
                }
                else
                {
                  *(_OWORD *)v27 = 0;
                  *(_QWORD *)(v27 + 16) = 0;
                  *(_QWORD *)(v27 + 24) = 0;
                  *(_QWORD *)v27 = v49[0];
                  *(_QWORD *)(v27 + 8) = v49[1];
                  *(__m128i *)(v27 + 16) = v50;
                  v50 = si128;
                  LOWORD(v49[0]) = 0;
                  *(_QWORD *)(v26 + 8) += 32LL;
                }
                std::wstring::~wstring(v44);
              }
            }
            std::wstring::~wstring(v49);
            std::wstring::~wstring(v47);
            v17 += 64;
          }
          while ( v17 != v19 );
          v5 = v32;
        }
        std::vector<std::pair<std::wstring,std::wstring>>::_Tidy(v40);
      }
      std::vector<std::wstring>::_Tidy(v37);
      v5 += 4;
      v32 = v5;
    }
    while ( v5 != v39 );
  }
  return std::vector<std::wstring>::_Tidy(&v38);
}

```

## disassembly

```asm
0x18004937c  mov     rax, rsp
0x18004937f  push    rbp
0x180049380  push    rbx
0x180049381  push    rsi
0x180049382  push    rdi
0x180049383  push    r12
0x180049385  push    r13
0x180049387  push    r14
0x180049389  push    r15
0x18004938b  lea     rbp, [rax-178h]
0x180049392  sub     rsp, 238h
0x180049399  mov     [rbp+170h+var_1B0], 0FFFFFFFFFFFFFFFEh
0x1800493a1  movaps  xmmword ptr [rax-58h], xmm6
0x1800493a5  mov     rax, cs:__security_cookie
0x1800493ac  xor     rax, rsp
0x1800493af  mov     [rbp+170h+var_60], rax
0x1800493b6  mov     r13, rcx
0x1800493b9  xor     r15d, r15d
0x1800493bc  mov     ebx, r15d
0x1800493bf  mov     dword ptr [rsp+270h+var_230], ebx
0x1800493c3  xorps   xmm0, xmm0
0x1800493c6  movups  [rbp+170h+var_C0], xmm0
0x1800493cd  xorps   xmm1, xmm1
0x1800493d0  movdqu  [rbp+170h+var_B0], xmm1
0x1800493d8  lea     r8d, [r15+3Ch]
0x1800493dc  lea     rdx, aSoftwareMicros_8; "SOFTWARE\\Microsoft\\Windows\\CurrentVe"...
0x1800493e3  lea     rcx, [rbp+170h+var_C0]
0x1800493ea  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x1800493ef  nop
0x1800493f0  lea     r8, [rbp+170h+var_C0]
0x1800493f7  mov     rdx, 0FFFFFFFF80000002h
0x1800493fe  lea     rcx, [rbp+170h+var_1E0]
0x180049402  call    ?GetSubkeyNamesOrDefault@RegOperations@AppCompatUtility@@YA?AV?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@PEAUHKEY__@@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@4@@Z; AppCompatUtility::RegOperations::GetSubkeyNamesOrDefault(HKEY__ *,std::wstring const &)
0x180049407  nop
0x180049408  lea     rcx, [rbp+170h+var_C0]; void *
0x18004940f  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180049414  mov     rdi, [rbp+170h+var_1E0]
0x180049418  mov     qword ptr [rsp+270h+var_230], rdi
0x18004941d  cmp     rdi, [rbp+170h+var_1D8]
0x180049421  jz      loc_1800498BF
0x180049427  mov     r14d, cs:_tls_index
0x18004942e  lea     esi, [r15+7]
0x180049432  movdqa  xmm6, cs:__xmm@00000000000000070000000000000000
0x18004943a  mov     rax, 7FFFFFFFFFFFFFFEh
0x180049444  mov     rcx, [rdi+10h]
0x180049448  sub     rax, rcx
0x18004944b  cmp     rax, 3Dh ; '='
0x18004944f  jb      loc_1800498F9
0x180049455  cmp     [rdi+18h], rsi
0x180049459  jbe     short loc_180049460
0x18004945b  mov     rax, [rdi]
0x18004945e  jmp     short loc_180049463
0x180049460  mov     rax, rdi
0x180049463  mov     [rsp+30h], rcx
0x180049468  mov     [rsp+270h+var_248], rax
0x18004946d  mov     [rsp+270h+var_250], 3Dh ; '='
0x180049476  lea     r9, aSoftwareMicros_11; "SOFTWARE\\Microsoft\\Windows\\CurrentVe"...
0x18004947d  lea     rcx, [rbp+170h+var_A0]
0x180049484  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@U_String_constructor_concat_tag@1@AEBV01@QEBG_K23@Z; std::wstring::wstring(std::_String_constructor_concat_tag,std::wstring const &,ushort const * const,unsigned __int64,ushort const * const,unsigned __int64)
0x180049489  or      ebx, 1
0x18004948c  lea     rdx, aComponents_0; "\\Components"
0x180049493  lea     rcx, [rbp+170h+var_A0]; Src
0x18004949a  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@QEBG@Z; std::wstring::append(ushort const * const)
0x18004949f  xorps   xmm0, xmm0
0x1800494a2  movups  [rbp+170h+var_120], xmm0
0x1800494a6  xorps   xmm1, xmm1
0x1800494a9  movdqu  [rbp+170h+var_110], xmm1
0x1800494ae  movups  xmm0, xmmword ptr [rax]
0x1800494b1  movups  [rbp+170h+var_120], xmm0
0x1800494b5  movups  xmm1, xmmword ptr [rax+10h]
0x1800494b9  movups  [rbp+170h+var_110], xmm1
0x1800494bd  mov     [rax+10h], r15
0x1800494c1  mov     [rax+18h], rsi
0x1800494c5  mov     [rax], r15w
0x1800494c9  or      ebx, 2
0x1800494cc  lea     r8, [rbp+170h+var_120]
0x1800494d0  mov     rdx, 0FFFFFFFF80000002h
0x1800494d7  lea     rcx, [rsp+78h]
0x1800494dc  call    ?GetSubkeyNamesOrDefault@RegOperations@AppCompatUtility@@YA?AV?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@PEAUHKEY__@@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@4@@Z; AppCompatUtility::RegOperations::GetSubkeyNamesOrDefault(HKEY__ *,std::wstring const &)
0x1800494e1  nop
0x1800494e2  lea     rcx, [rbp+170h+var_120]; void *
0x1800494e6  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800494eb  nop
0x1800494ec  lea     rcx, [rbp+170h+var_A0]; void *
0x1800494f3  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800494f8  mov     r12, [rsp+78h]
0x1800494fd  jmp     loc_180049898
0x180049502  mov     rcx, [rdi+10h]
0x180049506  mov     rax, 7FFFFFFFFFFFFFFEh
0x180049510  sub     rax, rcx
0x180049513  cmp     rax, 3Dh ; '='
0x180049517  jb      loc_1800498F3
0x18004951d  cmp     [rdi+18h], rsi
0x180049521  jbe     short loc_180049528
0x180049523  mov     rax, [rdi]
0x180049526  jmp     short loc_18004952B
0x180049528  mov     rax, rdi
0x18004952b  mov     [rsp+30h], rcx
0x180049530  mov     [rsp+270h+var_248], rax
0x180049535  mov     [rsp+270h+var_250], 3Dh ; '='
0x18004953e  lea     r9, aSoftwareMicros_11; "SOFTWARE\\Microsoft\\Windows\\CurrentVe"...
0x180049545  lea     rcx, [rbp+170h+var_80]
0x18004954c  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@U_String_constructor_concat_tag@1@AEBV01@QEBG_K23@Z; std::wstring::wstring(std::_String_constructor_concat_tag,std::wstring const &,ushort const * const,unsigned __int64,ushort const * const,unsigned __int64)
0x180049551  nop
0x180049552  lea     rdx, aComponents; "\\Components\\"
0x180049559  lea     rcx, [rbp+170h+var_80]; Src
0x180049560  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@QEBG@Z; std::wstring::append(ushort const * const)
0x180049565  xorps   xmm0, xmm0
0x180049568  movups  [rbp+170h+Src], xmm0
0x18004956f  xorps   xmm1, xmm1
0x180049572  movdqu  [rbp+170h+var_D0], xmm1
0x18004957a  movups  xmm0, xmmword ptr [rax]
0x18004957d  movups  [rbp+170h+Src], xmm0
0x180049584  movups  xmm1, xmmword ptr [rax+10h]
0x180049588  movups  [rbp+170h+var_D0], xmm1
0x18004958f  mov     [rax+10h], r15
0x180049593  mov     [rax+18h], rsi
0x180049597  mov     [rax], r15w
0x18004959b  mov     rdx, r12
0x18004959e  lea     rcx, [rbp+170h+Src]; Src
0x1800495a5  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@AEBV12@@Z; std::wstring::append(std::wstring const &)
0x1800495aa  xorps   xmm0, xmm0
0x1800495ad  movups  [rbp+170h+var_100], xmm0
0x1800495b1  xorps   xmm1, xmm1
0x1800495b4  movdqu  [rbp+170h+var_F0], xmm1
0x1800495bc  movups  xmm0, xmmword ptr [rax]
0x1800495bf  movups  [rbp+170h+var_100], xmm0
0x1800495c3  movups  xmm1, xmmword ptr [rax+10h]
0x1800495c7  movups  [rbp+170h+var_F0], xmm1
0x1800495ce  mov     [rax+10h], r15
0x1800495d2  mov     [rax+18h], rsi
0x1800495d6  mov     [rax], r15w
0x1800495da  xorps   xmm0, xmm0
0x1800495dd  movdqu  [rsp+270h+var_218+8], xmm0
0x1800495e3  mov     [rsp+270h+var_200], r15
0x1800495e8  lea     r8, [rsp+270h+var_218+8]
0x1800495ed  lea     rdx, [rbp+170h+var_100]
0x1800495f1  call    ?GetStringValues@RegOperations@AppCompatUtility@@YAJPEAUHKEY__@@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAV?$vector@U?$pair@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@V?$allocator@U?$pair@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@@2@@5@@Z; AppCompatUtility::RegOperations::GetStringValues(HKEY__ *,std::wstring const &,std::vector<std::pair<std::wstring,std::wstring>> &)
0x1800495f6  test    eax, eax
0x1800495f8  jnz     short loc_180049616
0x1800495fa  lea     rdx, [rsp+270h+var_218+8]
0x1800495ff  lea     rcx, [rbp+170h+var_180]
0x180049603  call    ??0?$vector@U?$pair@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@V?$allocator@U?$pair@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@@2@@std@@QEAA@AEBV01@@Z; std::vector<std::pair<std::wstring,std::wstring>>::vector<std::pair<std::wstring,std::wstring>>(std::vector<std::pair<std::wstring,std::wstring>> const &)
0x180049608  mov     rcx, rax
0x18004960b  or      ebx, 0BCh
0x180049611  mov     rsi, [rax]
0x180049614  jmp     short loc_18004962B
0x180049616  xorps   xmm0, xmm0
0x180049619  movdqu  [rbp+170h+var_1A0], xmm0
0x18004961e  lea     rcx, [rbp+170h+var_1A8]
0x180049622  or      ebx, 0DCh
0x180049628  mov     rsi, r15
0x18004962b  mov     rax, [rcx+10h]
0x18004962f  mov     [rcx+10h], r15
0x180049633  mov     r15, [rcx+8]
0x180049637  mov     qword ptr [rcx+8], 0
0x18004963f  mov     qword ptr [rcx], 0
0x180049646  mov     [rbp+170h+var_1C8], rsi
0x18004964a  mov     [rbp+170h+var_1C0], r15
0x18004964e  mov     [rbp+170h+var_1B8], rax
0x180049652  test    bl, 40h
0x180049655  jz      short loc_180049663
0x180049657  and     ebx, 0FFFFFFBFh
0x18004965a  lea     rcx, [rbp+170h+var_1A8]
0x18004965e  call    ?_Tidy@?$vector@U?$pair@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@V?$allocator@U?$pair@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@@2@@std@@AEAAXXZ; std::vector<std::pair<std::wstring,std::wstring>>::_Tidy(void)
0x180049663  test    bl, 20h
0x180049666  jz      short loc_180049675
0x180049668  and     ebx, 0FFFFFFDFh
0x18004966b  lea     rcx, [rbp+170h+var_180]
0x18004966f  call    ?_Tidy@?$vector@U?$pair@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@V?$allocator@U?$pair@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@@2@@std@@AEAAXXZ; std::vector<std::pair<std::wstring,std::wstring>>::_Tidy(void)
0x180049674  nop
0x180049675  lea     rcx, [rsp+270h+var_218+8]
0x18004967a  call    ?_Tidy@?$vector@U?$pair@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@V?$allocator@U?$pair@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@@2@@std@@AEAAXXZ; std::vector<std::pair<std::wstring,std::wstring>>::_Tidy(void)
0x18004967f  nop
0x180049680  lea     rcx, [rbp+170h+var_100]; void *
0x180049684  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180049689  nop
0x18004968a  lea     rcx, [rbp+170h+Src]; void *
0x180049691  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180049696  nop
0x180049697  lea     rcx, [rbp+170h+var_80]; void *
0x18004969e  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800496a3  cmp     rsi, r15
0x1800496a6  jz      loc_180049882
0x1800496ac  mov     rdi, gs:58h
0x1800496b5  mov     rdx, rsi
0x1800496b8  lea     rcx, [rbp+170h+var_160]
0x1800496bc  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x1800496c1  nop
0x1800496c2  lea     rdx, [rsi+20h]
0x1800496c6  lea     rcx, [rbp+170h+var_140]
0x1800496ca  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x1800496cf  nop
0x1800496d0  cmp     [rbp+170h+var_150], 20h ; ' '
0x1800496d5  jnz     loc_18004985E
0x1800496db  mov     ecx, 4
0x1800496e0  mov     rax, [rdi+r14*8]
0x1800496e4  mov     ecx, [rcx+rax]
0x1800496e7  cmp     cs:?$TSS0@?1??_IsValidMsiProductId@@YA_NAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z@4HA, ecx
0x1800496ed  jg      loc_1800498FF
0x1800496f3  lea     rcx, [rbp+170h+var_160]
0x1800496f7  call    ??$regex_match@U?$char_traits@G@std@@V?$allocator@G@2@GV?$regex_traits@G@2@@std@@YA_NAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@AEBV?$basic_regex@GV?$regex_traits@G@std@@@0@W4match_flag_type@regex_constants@0@@Z; std::regex_match<std::char_traits<ushort>,std::allocator<ushort>,ushort,std::regex_traits<ushort>>(std::wstring const &,std::basic_regex<ushort,std::regex_traits<ushort>> const &,std::regex_constants::match_flag_type)
0x1800496fc  test    al, al
0x1800496fe  jz      loc_18004985E
0x180049704  mov     rax, qword ptr [rbp+170h+var_130]
0x180049708  dec     rax
0x18004970b  cmp     rax, 103h
0x180049711  ja      loc_18004985E
0x180049717  lea     rdx, [rbp+170h+var_160]
0x18004971b  lea     rcx, [rbp+170h+var_180]; Src
0x18004971f  call    ?_ToProductCode@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEBV12@@Z; _ToProductCode(std::wstring const &)
0x180049724  nop
0x180049725  mov     rax, [rbp+170h+var_170]
0x180049729  lea     rdx, [rbp+170h+var_180]
0x18004972d  cmp     [rbp+170h+var_168], 7
0x180049732  cmova   rdx, [rbp+170h+var_180]
0x180049737  mov     r9, 0CBF29CE484222325h
0x180049741  lea     r8, [rax+rax]
0x180049745  xor     ecx, ecx
0x180049747  test    r8, r8
0x18004974a  jz      short loc_180049769
0x18004974c  movzx   eax, byte ptr [rcx+rdx]
0x180049750  xor     r9, rax
0x180049753  mov     r10, 100000001B3h
0x18004975d  imul    r9, r10
0x180049761  inc     rcx
0x180049764  cmp     rcx, r8
0x180049767  jb      short loc_18004974C
0x180049769  lea     r8, [rbp+170h+var_180]
0x18004976d  lea     rdx, [rbp+170h+var_190]
0x180049771  mov     rcx, r13
0x180049774  call    ??$_Find_last@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@?$_Hash@V?$_Uset_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$_Uhash_compare@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$hash@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@U?$equal_to@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@2@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@$0A@@std@@@std@@IEBA?AU?$_Hash_find_last_result@PEAU?$_List_node@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAX@std@@@1@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@_K@Z; std::_Hash<std::_Uset_traits<std::wstring,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::wstring>,0>>::_Find_last<std::wstring>(std::wstring const &,unsigned __int64)
0x180049779  mov     rcx, [rax+8]
0x18004977d  test    rcx, rcx
0x180049780  jz      short loc_180049788
0x180049782  cmp     rcx, [r13+8]
0x180049786  jnz     short loc_1800497E7
0x180049788  xorps   xmm0, xmm0
0x18004978b  movdqu  [rsp+270h+var_230+8], xmm0
0x180049791  mov     qword ptr [rsp+270h+var_218], 0
0x18004979a  lea     rdx, [rbp+170h+var_180]
0x18004979e  mov     rcx, r13
0x1800497a1  call    ??A?$unordered_map@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@2@U?$hash@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@U?$equal_to@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@2@@std@@@2@@std@@QEAAAEAV?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@1@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@@Z; std::unordered_map<std::wstring,std::vector<std::wstring>>::operator[](std::wstring const &)
0x1800497a6  mov     r14, rax
0x1800497a9  lea     rax, [rsp+270h+var_230+8]
0x1800497ae  cmp     r14, rax
0x1800497b1  jz      short loc_1800497D6
0x1800497b3  mov     rcx, r14
0x1800497b6  call    ?_Tidy@?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@AEAAXXZ; std::vector<std::wstring>::_Tidy(void)
0x1800497bb  xor     eax, eax
0x1800497bd  mov     [r14], rax
0x1800497c0  mov     [r14+8], rax
0x1800497c4  mov     [r14+10h], rax
0x1800497c8  xorps   xmm0, xmm0
0x1800497cb  movdqu  [rsp+270h+var_230+8], xmm0
0x1800497d1  mov     qword ptr [rsp+270h+var_218], rax
0x1800497d6  lea     rcx, [rsp+270h+var_230+8]
0x1800497db  call    ?_Tidy@?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@AEAAXXZ; std::vector<std::wstring>::_Tidy(void)
0x1800497e0  mov     r14d, cs:_tls_index
0x1800497e7  lea     rdx, [rbp+170h+var_180]
0x1800497eb  mov     rcx, r13
0x1800497ee  call    ??A?$unordered_map@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@2@U?$hash@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@U?$equal_to@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@2@@std@@@2@@std@@QEAAAEAV?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@1@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@@Z; std::unordered_map<std::wstring,std::vector<std::wstring>>::operator[](std::wstring const &)
0x1800497f3  mov     r9, rax
0x1800497f6  mov     rdx, [rax+8]
0x1800497fa  cmp     rdx, [rax+10h]
0x1800497fe  jz      short loc_180049847
0x180049800  xorps   xmm0, xmm0
0x180049803  movups  xmmword ptr [rdx], xmm0
0x180049806  mov     qword ptr [rdx+10h], 0
0x18004980e  mov     qword ptr [rdx+18h], 0
0x180049816  mov     rcx, [rbp+170h+var_140]
0x18004981a  mov     [rdx], rcx
0x18004981d  mov     rax, [rbp+170h+var_138]
0x180049821  mov     [rdx+8], rax
0x180049825  mov     rax, qword ptr [rbp+170h+var_130]
0x180049829  mov     [rdx+10h], rax
0x18004982d  mov     rax, qword ptr [rbp+170h+var_130+8]
0x180049831  mov     [rdx+18h], rax
0x180049835  movdqa  [rbp+170h+var_130], xmm6
0x18004983a  xor     eax, eax
0x18004983c  mov     word ptr [rbp+170h+var_140], ax
0x180049840  add     qword ptr [r9+8], 20h ; ' '
0x180049845  jmp     short loc_180049854
0x180049847  lea     r8, [rbp+170h+var_140]
0x18004984b  mov     rcx, r9
0x18004984e  call    ??$_Emplace_reallocate@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@AEAAPEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@QEAV21@$$QEAV21@@Z; std::vector<std::wstring>::_Emplace_reallocate<std::wstring>(std::wstring * const,std::wstring &&)
0x180049853  nop
0x180049854  lea     rcx, [rbp+170h+var_180]; void *
0x180049858  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18004985d  nop
0x18004985e  lea     rcx, [rbp+170h+var_140]; void *
0x180049862  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180049867  lea     rcx, [rbp+170h+var_160]; void *
0x18004986b  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180049870  add     rsi, 40h ; '@'
0x180049874  cmp     rsi, r15
0x180049877  jnz     loc_1800496B5
0x18004987d  mov     rdi, qword ptr [rsp+270h+var_230]
0x180049882  lea     rcx, [rbp+170h+var_1C8]
0x180049886  call    ?_Tidy@?$vector@U?$pair@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@V?$allocator@U?$pair@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@@2@@std@@AEAAXXZ; std::vector<std::pair<std::wstring,std::wstring>>::_Tidy(void)
  ... truncated ...
```
