# LegacySystemLanguagePackResourceProvider::_EnumerateLanguageFeatureCapabilities(ICbsSession9 *,std::vector<LanguageFeature,std::allocator<LanguageFeature>> const &,uint)

- ea: `0x180048ce8`
- end: `0x180049237`
- name: `?_EnumerateLanguageFeatureCapabilities@LegacySystemLanguagePackResourceProvider@@CA?AV?$vector@V?$ComPtr@UICbsCapability@@@WRL@Microsoft@@V?$allocator@V?$ComPtr@UICbsCapability@@@WRL@Microsoft@@@std@@@std@@PEAUICbsSession9@@AEBV?$vector@ULanguageFeature@@V?$allocator@ULanguageFeature@@@std@@@3@I@Z`
- size: `1359`
- prototype: ``
- caller_count: `4`
- callee_count: `16`
- tags: `service_task, broker_com_uri`

## callers

- `0x180045d10`
- `0x180046040`
- `0x180048b9c`
- `0x180049c04`

## callees

- `0x180003a00`
- `0x180012a98`
- `0x1800137bc`
- `0x180014720`
- `0x180014ed0`
- `0x18001a570`
- `0x18001d750`
- `0x18001df70`
- `0x18001f390`
- `0x18001f69c`
- `0x1800208b8`
- `0x1800215c8`
- `0x1800275f8`
- `0x180043f24`
- `0x180048ce8`
- `0x18006a010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsnicmp` at `0x180049145`
- `api-ms-win-crt-private-l1-1-0!_o__wcsnicmp` at `0x180049145`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180049057`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180049067`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004907b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180049057`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180049067`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004907b`

## string_xrefs

- `0x180049210`: `onecore\base\languageoverlay\services\languageoverlayservice\lib\systemlanguageresourcesprovider.cpp`
- `0x180049225`: `onecore\base\languageoverlay\services\languageoverlayservice\lib\systemlanguageresourcesprovider.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=17
__int64 __fastcall LegacySystemLanguagePackResourceProvider::_EnumerateLanguageFeatureCapabilities(
        __int64 a1,
        __int64 a2,
        __int64 **a3,
        unsigned int a4)
{
  int v8; // ebx
  int v9; // eax
  __int64 v10; // rdi
  unsigned int (__fastcall *v11)(__int64, __int64, __int64 *, _DWORD *); // r14
  __int64 v12; // rcx
  __int64 v13; // rax
  int v14; // eax
  const int *v15; // rdx
  unsigned __int64 v16; // r8
  int *v17; // rdx
  __int64 v18; // rax
  __int64 v19; // r8
  __int64 v20; // rax
  __int64 v21; // rcx
  char v22; // di
  char *v23; // rax
  int v24; // r15d
  __int64 *v25; // rdi
  __int64 *v26; // r14
  char **v27; // rdx
  char *v28; // r8
  __int64 *v29; // rcx
  char *v30; // rdx
  __int64 v31; // rcx
  __int64 v32; // rcx
  char *v34[4]; // [rsp+60h] [rbp-A0h] BYREF
  char *v35[4]; // [rsp+80h] [rbp-80h] BYREF
  __int64 *v36; // [rsp+A0h] [rbp-60h] BYREF
  __int64 v37; // [rsp+A8h] [rbp-58h]
  LPVOID v38; // [rsp+B0h] [rbp-50h] BYREF
  LPVOID v39; // [rsp+B8h] [rbp-48h] BYREF
  LPVOID pv; // [rsp+C0h] [rbp-40h] BYREF
  _DWORD v41[2]; // [rsp+C8h] [rbp-38h] BYREF
  int v42; // [rsp+D0h] [rbp-30h] BYREF
  char *v43[4]; // [rsp+D8h] [rbp-28h] BYREF
  _OWORD v44[2]; // [rsp+F8h] [rbp-8h] BYREF
  __int64 v45; // [rsp+120h] [rbp+20h] BYREF
  char v46; // [rsp+128h] [rbp+28h]
  _OWORD v47[2]; // [rsp+130h] [rbp+30h] BYREF
  __int64 v48; // [rsp+150h] [rbp+50h]
  char v49; // [rsp+158h] [rbp+58h]
  __int128 v50; // [rsp+160h] [rbp+60h]
  char v51; // [rsp+170h] [rbp+70h]
  __int64 v52; // [rsp+178h] [rbp+78h]
  __int64 v53; // [rsp+180h] [rbp+80h]
  char v54; // [rsp+188h] [rbp+88h] BYREF
  wchar_t S1[16]; // [rsp+190h] [rbp+90h] BYREF
  _BYTE v56[40]; // [rsp+1B0h] [rbp+B0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+228h] [rbp+128h]

  *(_QWORD *)a1 = 0;
  *(_QWORD *)(a1 + 8) = 0;
  *(_QWORD *)(a1 + 16) = 0;
  v8 = 1;
  if ( *a3 != a3[1] )
  {
    v37 = 0;
    v9 = (*(__int64 (__fastcall **)(__int64, _QWORD, const wchar_t *, _QWORD))(*(_QWORD *)a2 + 144LL))(
           a2,
           a4,
           L"Language",
           0);
    if ( v9 == -2146498298 && (a4 & 4) != 0 && a4 != 4 )
      v9 = (*(__int64 (__fastcall **)(__int64, _QWORD, const wchar_t *, _QWORD))(*(_QWORD *)a2 + 144LL))(
             a2,
             a4 & 0xFFFFFFFB,
             L"Language",
             0);
    if ( v9 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x3A3,
        (unsigned int)"onecore\\base\\languageoverlay\\services\\languageoverlayservice\\lib\\systemlanguageresourcesprovider.cpp",
        (const char *)(unsigned int)v9,
        0);
    v36 = 0;
    v41[0] = 0;
    while ( 1 )
    {
      v10 = v37;
      v11 = *(unsigned int (__fastcall **)(__int64, __int64, __int64 *, _DWORD *))(*(_QWORD *)v37 + 24LL);
      v12 = (__int64)v36;
      if ( v36 )
      {
        v36 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v12 + 16LL))(v12);
      }
      if ( v11(v10, 1, (__int64 *)&v36, v41) )
        break;
      v39 = 0;
      v38 = 0;
      pv = 0;
      v42 = 0;
      v41[1] = 0;
      v13 = *v36;
      pv = 0;
      v38 = 0;
      v39 = 0;
      v14 = (*(__int64 (__fastcall **)(__int64 *, LPVOID *, LPVOID *, LPVOID *))(v13 + 112))(v36, &v39, &v38, &pv);
      if ( v14 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x3B2,
          (unsigned int)"onecore\\base\\languageoverlay\\services\\languageoverlayservice\\lib\\systemlanguageresourcesprovider.cpp",
          (const char *)(unsigned int)v14,
          (int)&v42);
      v15 = &qword_180070100;
      if ( v39 )
        v15 = (const int *)v39;
      memset(v44, 0, sizeof(v44));
      v16 = -1;
      do
        ++v16;
      while ( *((_WORD *)v15 + v16) );
      std::wstring::_Construct<1,unsigned short const *>((char **)v44, v15, v16);
      v17 = (int *)&qword_180070100;
      if ( v38 )
        v17 = (int *)v38;
      std::basic_string<unsigned short,details::case_insensitive_wchar_traits,std::allocator<unsigned short>>::basic_string<unsigned short,details::case_insensitive_wchar_traits,std::allocator<unsigned short>>(
        v43,
        v17);
      std::basic_regex<unsigned short,std::regex_traits<unsigned short>>::basic_regex<unsigned short,std::regex_traits<unsigned short>>(v56);
      v45 = 0;
      v46 = 0;
      memset(v47, 0, sizeof(v47));
      v48 = 0;
      v49 = 0;
      v50 = 0;
      v51 = 0;
      v52 = 0;
      v53 = 0;
      v54 = 0;
      if ( !(unsigned __int8)std::regex_match<std::char_traits<unsigned short>,std::allocator<unsigned short>,std::allocator<std::sub_match<std::_String_const_iterator<std::_String_val<std::_Simple_types<unsigned short>>>>>,unsigned short,std::regex_traits<unsigned short>>(
                               v44,
                               &v45,
                               v56) )
        goto LABEL_28;
      v18 = std::match_results<std::_String_const_iterator<std::_String_val<std::_Simple_types<unsigned short>>>>::str(
              &v45,
              v34,
              1);
      v8 |= 2u;
      v19 = *(_QWORD *)(v18 + 16);
      if ( *(_QWORD *)(v18 + 24) > 7u )
        v18 = *(_QWORD *)v18;
      if ( v19 != 8 || wmemcmp((const wchar_t *)v18, L"Language", 8u) )
        goto LABEL_28;
      v20 = std::match_results<std::_String_const_iterator<std::_String_val<std::_Simple_types<unsigned short>>>>::str(
              &v45,
              v35,
              2);
      v8 |= 4u;
      v21 = *(_QWORD *)(v20 + 16);
      if ( *(_QWORD *)(v20 + 24) > 7u )
        v20 = *(_QWORD *)v20;
      if ( v21 != 2 || wmemcmp((const wchar_t *)v20, L"UI", 2u) )
        v22 = 0;
      else
LABEL_28:
        v22 = 1;
      if ( (v8 & 4) != 0 )
      {
        v8 &= ~4u;
        std::basic_string<unsigned short,details::case_insensitive_wchar_traits,std::allocator<unsigned short>>::~basic_string<unsigned short,details::case_insensitive_wchar_traits,std::allocator<unsigned short>>(v35);
      }
      if ( (v8 & 2) != 0 )
      {
        v8 &= ~2u;
        std::basic_string<unsigned short,details::case_insensitive_wchar_traits,std::allocator<unsigned short>>::~basic_string<unsigned short,details::case_insensitive_wchar_traits,std::allocator<unsigned short>>(v34);
      }
      if ( !v22 )
      {
        std::match_results<std::_String_const_iterator<std::_String_val<std::_Simple_types<unsigned short>>>>::str(
          &v45,
          S1,
          2);
        v23 = &v54;
        if ( 0xAAAAAAAAAAAAAAABuLL * ((__int64)(*((_QWORD *)&v47[0] + 1) - *(_QWORD *)&v47[0]) >> 3) > 4 )
          v23 = (char *)(*(_QWORD *)&v47[0] + 112LL);
        if ( *v23 )
        {
          std::match_results<std::_String_const_iterator<std::_String_val<std::_Simple_types<unsigned short>>>>::str(
            &v45,
            v34,
            3);
          std::wstring::operator+=(S1);
          std::basic_string<unsigned short,details::case_insensitive_wchar_traits,std::allocator<unsigned short>>::~basic_string<unsigned short,details::case_insensitive_wchar_traits,std::allocator<unsigned short>>(v34);
        }
        v24 = PayloadTypeFromName(S1);
        v25 = *a3;
        v26 = a3[1];
        while ( v25 != v26 )
        {
          v27 = v43;
          if ( v43[3] > (char *)7 )
            v27 = (char **)v43[0];
          v28 = (char *)v25[2];
          if ( (unsigned __int64)v25[3] <= 7 )
            v29 = v25;
          else
            v29 = (__int64 *)*v25;
          if ( v28 == v43[2] && (!v28 || !(unsigned int)_o__wcsnicmp(v29, v27)) && *((_DWORD *)v25 + 8) == v24 )
          {
            v30 = *(char **)(a1 + 8);
            if ( v30 == *(char **)(a1 + 16) )
            {
              std::vector<Microsoft::WRL::ComPtr<ICbsCapability>>::_Emplace_reallocate<Microsoft::WRL::ComPtr<ICbsCapability> const &>(
                (char **)a1,
                v30,
                (__int64 *)&v36);
            }
            else
            {
              *(_QWORD *)v30 = v36;
              if ( v36 )
                (*(void (__fastcall **)(__int64 *))(*v36 + 8))(v36);
              *(_QWORD *)(a1 + 8) += 8LL;
            }
            break;
          }
          v25 += 5;
        }
        std::basic_string<unsigned short,details::case_insensitive_wchar_traits,std::allocator<unsigned short>>::~basic_string<unsigned short,details::case_insensitive_wchar_traits,std::allocator<unsigned short>>((char **)S1);
      }
      std::vector<std::sub_match<std::_String_const_iterator<std::_String_val<std::_Simple_types<unsigned short>>>>>::~vector<std::sub_match<std::_String_const_iterator<std::_String_val<std::_Simple_types<unsigned short>>>>>(v47);
      std::basic_regex<unsigned short,std::regex_traits<unsigned short>>::~basic_regex<unsigned short,std::regex_traits<unsigned short>>(v56);
      std::basic_string<unsigned short,details::case_insensitive_wchar_traits,std::allocator<unsigned short>>::~basic_string<unsigned short,details::case_insensitive_wchar_traits,std::allocator<unsigned short>>(v43);
      std::basic_string<unsigned short,details::case_insensitive_wchar_traits,std::allocator<unsigned short>>::~basic_string<unsigned short,details::case_insensitive_wchar_traits,std::allocator<unsigned short>>((char **)v44);
      if ( pv )
        CoTaskMemFree(pv);
      if ( v38 )
        CoTaskMemFree(v38);
      if ( v39 )
        CoTaskMemFree(v39);
    }
    v31 = (__int64)v36;
    if ( v36 )
    {
      v36 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v31 + 16LL))(v31);
    }
    v32 = v37;
    if ( v37 )
    {
      v37 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v32 + 16LL))(v32);
    }
  }
  return a1;
}

```

## disassembly

```asm
0x180048ce8  push    rbp
0x180048cea  push    rbx
0x180048ceb  push    rsi
0x180048cec  push    rdi
0x180048ced  push    r12
0x180048cef  push    r13
0x180048cf1  push    r14
0x180048cf3  push    r15
0x180048cf5  lea     rbp, [rsp-0E8h]
0x180048cfd  sub     rsp, 1E8h
0x180048d04  mov     rax, cs:__security_cookie
0x180048d0b  xor     rax, rsp
0x180048d0e  mov     [rbp+120h+var_48], rax
0x180048d15  mov     edi, r9d
0x180048d18  mov     r12, r8
0x180048d1b  mov     r14, rdx
0x180048d1e  mov     rsi, rcx
0x180048d21  mov     [rsp+220h+var_1C8], rcx
0x180048d26  mov     [rsp+220h+var_1D0], 1
0x180048d2e  xor     r13d, r13d
0x180048d31  mov     [rcx], r13
0x180048d34  mov     [rcx+8], r13
0x180048d38  mov     [rcx+10h], r13
0x180048d3c  lea     ebx, [r13+1]
0x180048d40  mov     [rsp+220h+var_1D0], ebx
0x180048d44  mov     rcx, [r8+8]
0x180048d48  cmp     [r8], rcx
0x180048d4b  jz      loc_1800491E7
0x180048d51  mov     [rbp+120h+var_178], r13
0x180048d55  mov     rax, [rdx]
0x180048d58  lea     rcx, [rbp+120h+var_178]
0x180048d5c  mov     [rsp+220h+var_1E8], rcx
0x180048d61  mov     [rsp+220h+var_1F0], r13d
0x180048d66  mov     dword ptr [rsp+220h+var_1F8], r13d
0x180048d6b  mov     qword ptr [rsp+220h+var_200], r13
0x180048d70  xor     r9d, r9d
0x180048d73  lea     r8, aLanguage; "Language"
0x180048d7a  mov     edx, edi
0x180048d7c  mov     rcx, r14
0x180048d7f  mov     rax, [rax+90h]
0x180048d86  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180048d8b  cmp     eax, 800F0906h
0x180048d90  jnz     short loc_180048DF3
0x180048d92  test    dil, 4
0x180048d96  jz      short loc_180048DF3
0x180048d98  cmp     edi, 4
0x180048d9b  jz      short loc_180048DF3
0x180048d9d  and     edi, 0FFFFFFFBh
0x180048da0  mov     rax, [r14]
0x180048da3  mov     r15, [rax+90h]
0x180048daa  mov     rcx, [rbp+120h+var_178]
0x180048dae  test    rcx, rcx
0x180048db1  jz      short loc_180048DC4
0x180048db3  mov     [rbp+120h+var_178], r13
0x180048db7  mov     rax, [rcx]
0x180048dba  mov     rax, [rax+10h]
0x180048dbe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180048dc3  nop
0x180048dc4  lea     rax, [rbp+120h+var_178]
0x180048dc8  mov     [rsp+220h+var_1E8], rax
0x180048dcd  mov     [rsp+220h+var_1F0], r13d
0x180048dd2  mov     dword ptr [rsp+220h+var_1F8], r13d
0x180048dd7  mov     qword ptr [rsp+220h+var_200], r13; int
0x180048ddc  xor     r9d, r9d
0x180048ddf  lea     r8, aLanguage; "Language"
0x180048de6  mov     edx, edi
0x180048de8  mov     rcx, r14
0x180048deb  mov     rax, r15
0x180048dee  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180048df3  mov     rcx, [rbp+128h]; this
0x180048dfa  test    eax, eax
0x180048dfc  js      loc_180049222
0x180048e02  mov     [rbp+120h+var_180], r13
0x180048e06  mov     [rbp+120h+var_158], r13d
0x180048e0a  mov     rdi, [rbp+120h+var_178]
0x180048e0e  mov     rax, [rdi]
0x180048e11  mov     r14, [rax+18h]
0x180048e15  mov     rcx, [rbp+120h+var_180]
0x180048e19  test    rcx, rcx
0x180048e1c  jz      short loc_180048E2F
0x180048e1e  mov     [rbp+120h+var_180], r13
0x180048e22  mov     rax, [rcx]
0x180048e25  mov     rax, [rax+10h]
0x180048e29  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180048e2e  nop
0x180048e2f  lea     r9, [rbp+120h+var_158]
0x180048e33  lea     r8, [rbp+120h+var_180]
0x180048e37  mov     edx, 1
0x180048e3c  mov     rcx, rdi
0x180048e3f  mov     rax, r14
0x180048e42  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180048e47  test    eax, eax
0x180048e49  jnz     loc_1800491AC
0x180048e4f  mov     [rbp+120h+var_168], r13
0x180048e53  mov     [rbp+120h+var_170], r13
0x180048e57  mov     [rbp+120h+pv], r13
0x180048e5b  mov     [rbp+120h+var_150], r13d
0x180048e5f  mov     [rbp+120h+var_154], r13d
0x180048e63  mov     rcx, [rbp+120h+var_180]
0x180048e67  mov     rax, [rcx]
0x180048e6a  mov     [rbp+120h+pv], r13
0x180048e6e  mov     [rbp+120h+var_170], r13
0x180048e72  mov     [rbp+120h+var_168], r13
0x180048e76  lea     rdx, [rbp+120h+var_154]
0x180048e7a  mov     [rsp+220h+var_1F8], rdx
0x180048e7f  lea     rdx, [rbp+120h+var_150]
0x180048e83  mov     qword ptr [rsp+220h+var_200], rdx; int
0x180048e88  lea     r9, [rbp+120h+pv]
0x180048e8c  lea     r8, [rbp+120h+var_170]
0x180048e90  lea     rdx, [rbp+120h+var_168]
0x180048e94  mov     rax, [rax+70h]
0x180048e98  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180048e9d  mov     rcx, [rbp+128h]; this
0x180048ea4  test    eax, eax
0x180048ea6  js      loc_18004920D
0x180048eac  lea     rdx, qword_180070100
0x180048eb3  mov     rax, [rbp+120h+var_168]
0x180048eb7  test    rax, rax
0x180048eba  cmovnz  rdx, rax
0x180048ebe  xorps   xmm0, xmm0
0x180048ec1  movups  [rbp+120h+var_128], xmm0
0x180048ec5  xorps   xmm1, xmm1
0x180048ec8  movdqu  [rbp+120h+var_118], xmm1
0x180048ecd  or      r8, 0FFFFFFFFFFFFFFFFh
0x180048ed1  inc     r8
0x180048ed4  cmp     [rdx+r8*2], r13w
0x180048ed9  jnz     short loc_180048ED1
0x180048edb  lea     rcx, [rbp+120h+var_128]
0x180048edf  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x180048ee4  nop
0x180048ee5  lea     rdx, qword_180070100
0x180048eec  mov     rax, [rbp+120h+var_170]
0x180048ef0  test    rax, rax
0x180048ef3  cmovnz  rdx, rax
0x180048ef7  lea     rcx, [rbp+120h+var_148]
0x180048efb  call    ??0?$basic_string@GUcase_insensitive_wchar_traits@details@@V?$allocator@G@std@@@std@@QEAA@QEBG@Z; std::basic_string<ushort,details::case_insensitive_wchar_traits,std::allocator<ushort>>::basic_string<ushort,details::case_insensitive_wchar_traits,std::allocator<ushort>>(ushort const * const)
0x180048f00  nop
0x180048f01  lea     rcx, [rbp+120h+var_70]
0x180048f08  call    ??0?$basic_regex@GV?$regex_traits@G@std@@@std@@QEAA@PEBGW4syntax_option_type@regex_constants@1@@Z; std::basic_regex<ushort,std::regex_traits<ushort>>::basic_regex<ushort,std::regex_traits<ushort>>(ushort const *,std::regex_constants::syntax_option_type)
0x180048f0d  nop
0x180048f0e  mov     [rbp+120h+var_100], r13
0x180048f12  mov     [rbp+120h+var_F8], r13b
0x180048f16  xorps   xmm0, xmm0
0x180048f19  movdqa  [rbp+120h+var_F0], xmm0
0x180048f1e  xorps   xmm1, xmm1
0x180048f21  movdqa  [rbp+120h+var_E0], xmm1
0x180048f26  mov     [rbp+120h+var_D0], r13
0x180048f2a  mov     [rbp+120h+var_C8], r13b
0x180048f2e  movdqa  [rbp+120h+var_C0], xmm0
0x180048f33  mov     [rbp+120h+var_B0], r13b
0x180048f37  mov     [rbp+120h+var_A8], r13
0x180048f3b  mov     [rbp+120h+var_A0], r13
0x180048f42  mov     [rbp+120h+var_98], r13b
0x180048f49  lea     r8, [rbp+120h+var_70]
0x180048f50  lea     rdx, [rbp+120h+var_100]
0x180048f54  lea     rcx, [rbp+120h+var_128]
0x180048f58  call    ??$regex_match@U?$char_traits@G@std@@V?$allocator@G@2@V?$allocator@V?$sub_match@V?$_String_const_iterator@V?$_String_val@U?$_Simple_types@G@std@@@std@@@std@@@std@@@2@GV?$regex_traits@G@2@@std@@YA_NAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@AEAV?$match_results@V?$_String_const_iterator@V?$_String_val@U?$_Simple_types@G@std@@@std@@@std@@V?$allocator@V?$sub_match@V?$_String_const_iterator@V?$_String_val@U?$_Simple_types@G@std@@@std@@@std@@@std@@@2@@0@AEBV?$basic_regex@GV?$regex_traits@G@std@@@0@W4match_flag_type@regex_constants@0@@Z; std::regex_match<std::char_traits<ushort>,std::allocator<ushort>,std::allocator<std::sub_match<std::_String_const_iterator<std::_String_val<std::_Simple_types<ushort>>>>>,ushort,std::regex_traits<ushort>>(std::wstring const &,std::match_results<std::_String_const_iterator<std::_String_val<std::_Simple_types<ushort>>>> &,std::basic_regex<ushort,std::regex_traits<ushort>> const &,std::regex_constants::match_flag_type)
0x180048f5d  test    al, al
0x180048f5f  jz      loc_180048FEF
0x180048f65  mov     r8d, 1
0x180048f6b  lea     rdx, [rsp+220h+var_1C0]
0x180048f70  lea     rcx, [rbp+120h+var_100]
0x180048f74  call    ?str@?$match_results@V?$_String_const_iterator@V?$_String_val@U?$_Simple_types@G@std@@@std@@@std@@V?$allocator@V?$sub_match@V?$_String_const_iterator@V?$_String_val@U?$_Simple_types@G@std@@@std@@@std@@@std@@@2@@std@@QEBA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@2@_K@Z; std::match_results<std::_String_const_iterator<std::_String_val<std::_Simple_types<ushort>>>>::str(unsigned __int64)
0x180048f79  nop
0x180048f7a  or      ebx, 2
0x180048f7d  mov     [rsp+220h+var_1D0], ebx
0x180048f81  mov     r8, [rax+10h]; N
0x180048f85  cmp     qword ptr [rax+18h], 7
0x180048f8a  jbe     short loc_180048F8F
0x180048f8c  mov     rax, [rax]
0x180048f8f  cmp     r8, 8
0x180048f93  jnz     short loc_180048FEF
0x180048f95  lea     rdx, aLanguage; "Language"
0x180048f9c  mov     rcx, rax; S1
0x180048f9f  call    wmemcmp
0x180048fa4  test    eax, eax
0x180048fa6  jnz     short loc_180048FEF
0x180048fa8  lea     r8d, [rax+2]
0x180048fac  lea     rdx, [rbp+120h+var_1A0]
0x180048fb0  lea     rcx, [rbp+120h+var_100]
0x180048fb4  call    ?str@?$match_results@V?$_String_const_iterator@V?$_String_val@U?$_Simple_types@G@std@@@std@@@std@@V?$allocator@V?$sub_match@V?$_String_const_iterator@V?$_String_val@U?$_Simple_types@G@std@@@std@@@std@@@std@@@2@@std@@QEBA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@2@_K@Z; std::match_results<std::_String_const_iterator<std::_String_val<std::_Simple_types<ushort>>>>::str(unsigned __int64)
0x180048fb9  or      ebx, 4
0x180048fbc  mov     [rsp+220h+var_1D0], ebx
0x180048fc0  mov     rcx, [rax+10h]
0x180048fc4  cmp     qword ptr [rax+18h], 7
0x180048fc9  jbe     short loc_180048FCE
0x180048fcb  mov     rax, [rax]
0x180048fce  cmp     rcx, 2
0x180048fd2  jnz     short loc_180048FEA
0x180048fd4  mov     r8, rcx; N
0x180048fd7  lea     rdx, aUi; "UI"
0x180048fde  mov     rcx, rax; S1
0x180048fe1  call    wmemcmp
0x180048fe6  test    eax, eax
0x180048fe8  jz      short loc_180048FEF
0x180048fea  mov     dil, r13b
0x180048fed  jmp     short loc_180048FF2
0x180048fef  mov     dil, 1
0x180048ff2  test    bl, 4
0x180048ff5  jz      short loc_180049008
0x180048ff7  and     ebx, 0FFFFFFFBh
0x180048ffa  mov     [rsp+220h+var_1D0], ebx
0x180048ffe  lea     rcx, [rbp+120h+var_1A0]; void *
0x180049002  call    ??1?$basic_string@GUcase_insensitive_wchar_traits@details@@V?$allocator@G@std@@@std@@QEAA@XZ; std::basic_string<ushort,details::case_insensitive_wchar_traits,std::allocator<ushort>>::~basic_string<ushort,details::case_insensitive_wchar_traits,std::allocator<ushort>>(void)
0x180049007  nop
0x180049008  test    bl, 2
0x18004900b  jz      short loc_18004901E
0x18004900d  and     ebx, 0FFFFFFFDh
0x180049010  mov     [rsp+220h+var_1D0], ebx
0x180049014  lea     rcx, [rsp+220h+var_1C0]; void *
0x180049019  call    ??1?$basic_string@GUcase_insensitive_wchar_traits@details@@V?$allocator@G@std@@@std@@QEAA@XZ; std::basic_string<ushort,details::case_insensitive_wchar_traits,std::allocator<ushort>>::~basic_string<ushort,details::case_insensitive_wchar_traits,std::allocator<ushort>>(void)
0x18004901e  test    dil, dil
0x180049021  jz      short loc_180049086
0x180049023  lea     rcx, [rbp+120h+var_F0]
0x180049027  call    ??1?$vector@V?$sub_match@V?$_String_const_iterator@V?$_String_val@U?$_Simple_types@G@std@@@std@@@std@@@std@@V?$allocator@V?$sub_match@V?$_String_const_iterator@V?$_String_val@U?$_Simple_types@G@std@@@std@@@std@@@std@@@2@@std@@QEAA@XZ; std::vector<std::sub_match<std::_String_const_iterator<std::_String_val<std::_Simple_types<ushort>>>>>::~vector<std::sub_match<std::_String_const_iterator<std::_String_val<std::_Simple_types<ushort>>>>>(void)
0x18004902c  nop
0x18004902d  lea     rcx, [rbp+120h+var_70]
0x180049034  call    ??1?$basic_regex@GV?$regex_traits@G@std@@@std@@QEAA@XZ; std::basic_regex<ushort,std::regex_traits<ushort>>::~basic_regex<ushort,std::regex_traits<ushort>>(void)
0x180049039  nop
0x18004903a  lea     rcx, [rbp+120h+var_148]; void *
0x18004903e  call    ??1?$basic_string@GUcase_insensitive_wchar_traits@details@@V?$allocator@G@std@@@std@@QEAA@XZ; std::basic_string<ushort,details::case_insensitive_wchar_traits,std::allocator<ushort>>::~basic_string<ushort,details::case_insensitive_wchar_traits,std::allocator<ushort>>(void)
0x180049043  nop
0x180049044  lea     rcx, [rbp+120h+var_128]; void *
0x180049048  call    ??1?$basic_string@GUcase_insensitive_wchar_traits@details@@V?$allocator@G@std@@@std@@QEAA@XZ; std::basic_string<ushort,details::case_insensitive_wchar_traits,std::allocator<ushort>>::~basic_string<ushort,details::case_insensitive_wchar_traits,std::allocator<ushort>>(void)
0x18004904d  nop
0x18004904e  mov     rcx, [rbp+120h+pv]; pv
0x180049052  test    rcx, rcx
0x180049055  jz      short loc_18004905E
0x180049057  call    cs:__imp_CoTaskMemFree
0x18004905d  nop
0x18004905e  mov     rcx, [rbp+120h+var_170]; pv
0x180049062  test    rcx, rcx
0x180049065  jz      short loc_18004906E
0x180049067  call    cs:__imp_CoTaskMemFree
0x18004906d  nop
0x18004906e  mov     rcx, [rbp+120h+var_168]; pv
0x180049072  test    rcx, rcx
0x180049075  jz      loc_180048E0A
0x18004907b  call    cs:__imp_CoTaskMemFree
0x180049081  jmp     loc_180048E0A
0x180049086  mov     r8d, 2
0x18004908c  lea     rdx, [rbp+120h+S1]
0x180049093  lea     rcx, [rbp+120h+var_100]
0x180049097  call    ?str@?$match_results@V?$_String_const_iterator@V?$_String_val@U?$_Simple_types@G@std@@@std@@@std@@V?$allocator@V?$sub_match@V?$_String_const_iterator@V?$_String_val@U?$_Simple_types@G@std@@@std@@@std@@@std@@@2@@std@@QEBA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@2@_K@Z; std::match_results<std::_String_const_iterator<std::_String_val<std::_Simple_types<ushort>>>>::str(unsigned __int64)
0x18004909c  nop
0x18004909d  mov     rcx, qword ptr [rbp+120h+var_F0]
0x1800490a1  mov     rax, qword ptr [rbp+120h+var_F0+8]
0x1800490a5  sub     rax, rcx
0x1800490a8  sar     rax, 3
0x1800490ac  mov     rdx, 0AAAAAAAAAAAAAAABh
0x1800490b6  imul    rax, rdx
0x1800490ba  cmp     rax, 4
0x1800490be  lea     rax, [rbp+120h+var_98]
0x1800490c5  jbe     short loc_1800490CB
0x1800490c7  lea     rax, [rcx+70h]
0x1800490cb  cmp     [rax], r13b
0x1800490ce  jz      short loc_1800490FF
0x1800490d0  mov     r8d, 3
0x1800490d6  lea     rdx, [rsp+220h+var_1C0]
0x1800490db  lea     rcx, [rbp+120h+var_100]
0x1800490df  call    ?str@?$match_results@V?$_String_const_iterator@V?$_String_val@U?$_Simple_types@G@std@@@std@@@std@@V?$allocator@V?$sub_match@V?$_String_const_iterator@V?$_String_val@U?$_Simple_types@G@std@@@std@@@std@@@std@@@2@@std@@QEBA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@2@_K@Z; std::match_results<std::_String_const_iterator<std::_String_val<std::_Simple_types<ushort>>>>::str(unsigned __int64)
0x1800490e4  nop
0x1800490e5  mov     rdx, rax
0x1800490e8  lea     rcx, [rbp+120h+S1]; Src
0x1800490ef  call    ??Y?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@AEBV01@@Z; std::wstring::operator+=(std::wstring const &)
0x1800490f4  nop
0x1800490f5  lea     rcx, [rsp+220h+var_1C0]; void *
0x1800490fa  call    ??1?$basic_string@GUcase_insensitive_wchar_traits@details@@V?$allocator@G@std@@@std@@QEAA@XZ; std::basic_string<ushort,details::case_insensitive_wchar_traits,std::allocator<ushort>>::~basic_string<ushort,details::case_insensitive_wchar_traits,std::allocator<ushort>>(void)
0x1800490ff  lea     rcx, [rbp+120h+S1]; S1
0x180049106  call    ?PayloadTypeFromName@@YA?AW4PayloadType@@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; PayloadTypeFromName(std::wstring const &)
0x18004910b  mov     r15d, eax
0x18004910e  mov     rdi, [r12]
0x180049112  mov     r14, [r12+8]
0x180049117  jmp     short loc_180049159
0x180049119  lea     rdx, [rbp+120h+var_148]
0x18004911d  cmp     [rbp+120h+var_130], 7
0x180049122  cmova   rdx, [rbp+120h+var_148]
0x180049127  mov     r8, [rdi+10h]
0x18004912b  cmp     qword ptr [rdi+18h], 7
0x180049130  jbe     short loc_180049137
0x180049132  mov     rcx, [rdi]
0x180049135  jmp     short loc_18004913A
0x180049137  mov     rcx, rdi
0x18004913a  cmp     r8, [rbp+120h+var_138]
0x18004913e  jnz     short loc_180049155
0x180049140  test    r8, r8
0x180049143  jz      short loc_18004914F
0x180049145  call    cs:__imp__o__wcsnicmp
0x18004914b  test    eax, eax
0x18004914d  jnz     short loc_180049155
0x18004914f  cmp     [rdi+20h], r15d
0x180049153  jz      short loc_180049160
0x180049155  add     rdi, 28h ; '('
0x180049159  cmp     rdi, r14
0x18004915c  jnz     short loc_180049119
0x18004915e  jmp     short loc_18004919B
0x180049160  mov     rdx, [rsi+8]
0x180049164  cmp     rdx, [rsi+10h]
0x180049168  jz      short loc_18004918E
0x18004916a  mov     rax, [rbp+120h+var_180]
  ... truncated ...
```
