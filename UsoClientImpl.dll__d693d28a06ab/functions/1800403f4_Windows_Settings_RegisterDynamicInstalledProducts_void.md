# Windows::Settings::RegisterDynamicInstalledProducts(void)

- ea: `0x1800403f4`
- end: `0x1800409c2`
- name: `?RegisterDynamicInstalledProducts@Settings@Windows@@AEAAXXZ`
- size: `1486`
- prototype: `void __fastcall(Windows::Settings *__hidden this)`
- caller_count: `1`
- callee_count: `16`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x18003ef00`

## callees

- `0x180005f70`
- `0x180009380`
- `0x1800338a4`
- `0x180033b00`
- `0x180033f14`
- `0x180034304`
- `0x180036b10`
- `0x18003a388`
- `0x1800403f4`
- `0x1800409c8`
- `0x180040cd0`
- `0x180044804`
- `0x18004bde4`
- `0x18004fc3c`
- `0x180056500`
- `0x18005c5e0`

## string_xrefs

- `0x180040995`: `C:\__w\1\s\packages\Microsoft.Windows.Wil.Internal.0.3.30\inc\wil\opensource\wil\stl.h`
- `0x1800409af`: `C:\__w\1\s\packages\Microsoft.Windows.Wil.Internal.0.3.30\inc\wil\opensource\wil\stl.h`
- `0x1800407d1`: `DynamicInstalledProductsArray`
- `0x1800407e7`: `DynamicInstalledProductsArray`

## pseudocode

```c
// Hidden C++ exception states: #wind=9
void __fastcall Windows::Settings::RegisterDynamicInstalledProducts(Windows::Settings *this)
{
  int v2; // r15d
  __int64 v3; // rax
  const char *v4; // r9
  _QWORD *v5; // rax
  const struct web::json::array *v6; // rax
  __int64 i; // rbx
  __int64 v8; // rdi
  _QWORD *v9; // rax
  _QWORD *Src; // rax
  __int64 v11; // rdx
  __int64 v12; // rsi
  void (__fastcall *v13)(__int64, __int128 *, __int128 *, __int128 *, _BYTE *); // r14
  _QWORD *v14; // rax
  __int64 v15; // rax
  __int16 *traits_2_unsigned_short; // rax
  const char *v17; // r9
  __int64 v18; // r11
  __int64 v19; // rax
  _QWORD *v20; // rax
  __int64 v21; // rax
  __int64 v22; // rsi
  void (__fastcall *v23)(__int64, __int128 *, __int128 *, __int128 *, _BYTE *); // r14
  _QWORD *v24; // rax
  __int64 v25; // rax
  wchar_t *v26; // rax
  const char *v27; // r9
  __int64 v28; // r11
  __int64 v29; // rax
  _QWORD *v30; // rax
  __int64 v31; // rax
  __int128 v32; // [rsp+40h] [rbp-1A8h] BYREF
  __int128 v33; // [rsp+50h] [rbp-198h] BYREF
  __int64 v34; // [rsp+60h] [rbp-188h]
  __int64 v35; // [rsp+68h] [rbp-180h]
  __int128 v36; // [rsp+70h] [rbp-178h] BYREF
  __int128 v37; // [rsp+80h] [rbp-168h] BYREF
  __int128 v38; // [rsp+90h] [rbp-158h] BYREF
  __int128 v39; // [rsp+A0h] [rbp-148h] BYREF
  _BYTE v40[32]; // [rsp+B0h] [rbp-138h] BYREF
  char v41; // [rsp+D0h] [rbp-118h]
  __int128 v42; // [rsp+D8h] [rbp-110h]
  __int128 v43; // [rsp+E8h] [rbp-100h]
  __int128 v44; // [rsp+100h] [rbp-E8h]
  __int128 v45; // [rsp+110h] [rbp-D8h]
  __int128 v46; // [rsp+120h] [rbp-C8h]
  __int128 v47; // [rsp+130h] [rbp-B8h] BYREF
  __int64 v48; // [rsp+140h] [rbp-A8h]
  __int64 v49; // [rsp+148h] [rbp-A0h]
  _QWORD v50[2]; // [rsp+150h] [rbp-98h] BYREF
  __int64 v51; // [rsp+160h] [rbp-88h]
  unsigned __int64 v52; // [rsp+168h] [rbp-80h]
  __int128 v53; // [rsp+170h] [rbp-78h] BYREF
  __int64 v54; // [rsp+180h] [rbp-68h]
  _BYTE v55[32]; // [rsp+188h] [rbp-60h] BYREF
  char v56; // [rsp+1A8h] [rbp-40h]
  char v57; // [rsp+1B0h] [rbp-38h]
  wil::details::in1diag3 *retaddr; // [rsp+1E8h] [rbp+0h]

  v2 = 0;
  *(_QWORD *)&v32 = Windows::Settings::c_dynamicInstalledProductsArray;
  v3 = -1;
  do
    ++v3;
  while ( Windows::Settings::c_dynamicInstalledProductsArray[v3] );
  *((_QWORD *)&v32 + 1) = v3;
  v36 = v32;
  try
  {
    Windows::Settings::TryGetSetting(this, v55, &v36);
    if ( v57 )
    {
      v53 = 0;
      v54 = 0;
      if ( v56 != 2 )
        std::_Throw_bad_variant_access();
      v5 = (_QWORD *)web::json::value::parse(&v32, v55);
      v6 = (const struct web::json::array *)(*(__int64 (__fastcall **)(_QWORD))(*(_QWORD *)*v5 + 152LL))(*v5);
      web::json::array::array((web::json::array *)&v53, v6);
      if ( (_QWORD)v32 )
        (*(void (__fastcall **)(_QWORD, __int64))(*(_QWORD *)v32 + 192LL))(v32, 1);
      v8 = *((_QWORD *)&v53 + 1);
      for ( i = v53; i != v8; i += 8 )
      {
        v47 = 0;
        v48 = 0;
        v49 = 0;
        std::wstring::_Construct<1,wchar_t const *>(&v47);
        v9 = (_QWORD *)web::json::value::at(i, &v47);
        Src = (_QWORD *)(*(__int64 (__fastcall **)(_QWORD))(*(_QWORD *)*v9 + 176LL))(*v9);
        v11 = Src[2];
        if ( v11 == 0x7FFFFFFFFFFFFFFELL )
          std::_Xlen_string();
        if ( Src[3] > 7u )
          Src = (_QWORD *)*Src;
        std::wstring::wstring(v50, 1, Src, v11);
        v2 |= 1u;
        std::wstring::~wstring(&v47);
        v12 = *((_QWORD *)this + 11);
        v13 = *(void (__fastcall **)(__int64, __int128 *, __int128 *, __int128 *, _BYTE *))(*(_QWORD *)v12 + 64LL);
        v33 = 0;
        v34 = 0;
        v35 = 0;
        std::wstring::_Construct<1,wchar_t const *>(&v33);
        v14 = (_QWORD *)web::json::value::at(i, &v33);
        v15 = (*(__int64 (__fastcall **)(_QWORD))(*(_QWORD *)*v14 + 176LL))(*v14);
        std::wstring::wstring(v40, v15);
        v41 = 2;
        traits_2_unsigned_short = (__int16 *)anonymous_namespace_::__std_find_trivial_impl__anonymous_namespace_::_Find_traits_2_unsigned_short_(
                                               L"source",
                                               &word_18008CB6E,
                                               0);
        if ( traits_2_unsigned_short == &word_18008CB6E
          || (v19 = ((__int64)traits_2_unsigned_short - v18) >> 1, v19 == -1) )
        {
          wil::details::in1diag3::_FailFast_Unexpected(
            retaddr,
            (void *)0xC9,
            (unsigned int)"C:\\__w\\1\\s\\packages\\Microsoft.Windows.Wil.Internal.0.3.30\\inc\\wil\\opensource\\wil\\stl.h",
            v17);
        }
        *(_QWORD *)&v42 = v18;
        *((_QWORD *)&v42 + 1) = v19;
        v20 = v50;
        if ( v52 > 7 )
          v20 = (_QWORD *)v50[0];
        *(_QWORD *)&v43 = v20;
        *((_QWORD *)&v43 + 1) = v51;
        *(_QWORD *)&v44 = SystemInterface::Registry::UUP_DYN_INSTALLED_PROD_REDIRECTION_ID;
        v21 = -1;
        do
          ++v21;
        while ( SystemInterface::Registry::UUP_DYN_INSTALLED_PROD_REDIRECTION_ID[v21] );
        *((_QWORD *)&v44 + 1) = v21;
        v37 = v42;
        v38 = v43;
        v39 = v44;
        v13(v12, &v39, &v38, &v37, v40);
        if ( v41 != -1 && v41 && v41 != 1 )
          std::wstring::~wstring(v40);
        std::wstring::~wstring(&v33);
        v22 = *((_QWORD *)this + 11);
        v23 = *(void (__fastcall **)(__int64, __int128 *, __int128 *, __int128 *, _BYTE *))(*(_QWORD *)v22 + 64LL);
        v33 = 0;
        v34 = 0;
        v35 = 0;
        std::wstring::_Construct<1,wchar_t const *>(&v33);
        v24 = (_QWORD *)web::json::value::at(i, &v33);
        v25 = (*(__int64 (__fastcall **)(_QWORD))(*(_QWORD *)*v24 + 176LL))(*v24);
        std::wstring::wstring(v40, v25);
        v41 = 2;
        v26 = (wchar_t *)anonymous_namespace_::__std_find_trivial_impl__anonymous_namespace_::_Find_traits_2_unsigned_short_(
                           L"version",
                           L"DynamicInstalledProductsArray",
                           0);
        if ( v26 == L"DynamicInstalledProductsArray" || (v29 = ((__int64)v26 - v28) >> 1, v29 == -1) )
          wil::details::in1diag3::_FailFast_Unexpected(
            retaddr,
            (void *)0xC9,
            (unsigned int)"C:\\__w\\1\\s\\packages\\Microsoft.Windows.Wil.Internal.0.3.30\\inc\\wil\\opensource\\wil\\stl.h",
            v27);
        *(_QWORD *)&v45 = v28;
        *((_QWORD *)&v45 + 1) = v29;
        v30 = v50;
        if ( v52 > 7 )
          v30 = (_QWORD *)v50[0];
        *(_QWORD *)&v46 = v30;
        *((_QWORD *)&v46 + 1) = v51;
        *(_QWORD *)&v36 = SystemInterface::Registry::UUP_DYN_INSTALLED_PROD_REDIRECTION_ID;
        v31 = -1;
        do
          ++v31;
        while ( SystemInterface::Registry::UUP_DYN_INSTALLED_PROD_REDIRECTION_ID[v31] );
        *((_QWORD *)&v36 + 1) = v31;
        v39 = v45;
        v38 = v46;
        v37 = v36;
        v23(v22, &v37, &v38, &v39, v40);
        if ( v41 != -1 && v41 && v41 != 1 )
          std::wstring::~wstring(v40);
        std::wstring::~wstring(&v33);
        std::wstring::~wstring(v50);
      }
      std::vector<web::json::value>::_Tidy(&v53);
      if ( v57 && v56 != -1 && v56 && v56 != 1 )
        std::wstring::~wstring(v55);
    }
  }
  catch ( ... )
  {
    wil::details::in1diag3::Log_CaughtException(
      retaddr,
      (void *)0xD2,
      (unsigned int)"C:\\__w\\1\\s\\src\\orchestrator\\system\\windows\\servicesystem\\Settings.cpp",
      v4);
  }
}

```

## disassembly

```asm
0x1800403f4  mov     [rsp+arg_8], rbx
0x1800403f9  mov     [rsp+arg_10], rsi
0x1800403fe  push    rdi
0x1800403ff  push    r12
0x180040401  push    r13
0x180040403  push    r14
0x180040405  push    r15
0x180040407  sub     rsp, 1C0h
0x18004040e  mov     rax, cs:__security_cookie
0x180040415  xor     rax, rsp
0x180040418  mov     [rsp+1E8h+var_30], rax
0x180040420  mov     r13, rcx
0x180040423  xor     r12d, r12d
0x180040426  mov     r15d, r12d
0x180040429  mov     dword ptr [rsp+1E8h+var_1A8], r12d
0x18004042e  mov     rdx, cs:?c_dynamicInstalledProductsArray@Settings@Windows@@0QEB_WEB; wchar_t const * const Windows::Settings::c_dynamicInstalledProductsArray
0x180040435  mov     qword ptr [rsp+1E8h+var_1A8], rdx
0x18004043a  or      rax, 0FFFFFFFFFFFFFFFFh
0x18004043e  inc     rax
0x180040441  cmp     [rdx+rax*2], r12w
0x180040446  jnz     short loc_18004043E
0x180040448  mov     qword ptr [rsp+1E8h+var_1A8+8], rax
0x18004044d  movaps  xmm0, [rsp+1E8h+var_1A8]
0x180040452  movdqa  [rsp+1E8h+var_178], xmm0
0x180040458  lea     r8, [rsp+1E8h+var_178]
0x18004045d  lea     rdx, [rsp+1E8h+var_60]
0x180040465  call    ?TryGetSetting@Settings@Windows@@UEAA?AV?$optional@V?$variant@I_KV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@std@@@std@@V?$basic_zstring_view@_W@wil@@@Z; Windows::Settings::TryGetSetting(wil::basic_zstring_view<wchar_t>)
0x18004046a  nop
0x18004046b  cmp     [rsp+1E8h+var_38], r12b
0x180040473  jnz     short loc_18004047A
0x180040475  jmp     loc_180040954
0x18004047a  xorps   xmm0, xmm0
0x18004047d  xor     eax, eax
0x18004047f  movups  [rsp+1E8h+var_78], xmm0
0x180040487  mov     [rsp+1E8h+var_68], rax
0x18004048f  cmp     [rsp+1E8h+var_40], 2
0x180040497  jnz     loc_180040981
0x18004049d  lea     rdx, [rsp+1E8h+var_60]
0x1800404a5  lea     rcx, [rsp+1E8h+var_1A8]
0x1800404aa  call    ?parse@value@json@web@@SA?AV123@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; web::json::value::parse(std::wstring const &)
0x1800404af  nop
0x1800404b0  mov     rcx, [rax]
0x1800404b3  mov     rax, [rcx]
0x1800404b6  mov     rax, [rax+98h]
0x1800404bd  call    _guard_dispatch_icall
0x1800404c2  mov     rdx, rax; struct web::json::array *
0x1800404c5  lea     rcx, [rsp+1E8h+var_78]; this
0x1800404cd  call    ??0array@json@web@@QEAA@AEBV012@@Z; web::json::array::array(web::json::array const &)
0x1800404d2  nop
0x1800404d3  mov     rcx, qword ptr [rsp+1E8h+var_1A8]
0x1800404d8  test    rcx, rcx
0x1800404db  jz      short loc_1800404F1
0x1800404dd  mov     rax, [rcx]
0x1800404e0  mov     edx, 1
0x1800404e5  mov     rax, [rax+0C0h]
0x1800404ec  call    _guard_dispatch_icall
0x1800404f1  mov     rbx, qword ptr [rsp+1E8h+var_78]
0x1800404f9  mov     rdi, qword ptr [rsp+1E8h+var_78+8]
0x180040501  cmp     rbx, rdi
0x180040504  jz      loc_180040913
0x18004050a  xorps   xmm0, xmm0
0x18004050d  movups  [rsp+1E8h+var_B8], xmm0
0x180040515  mov     [rsp+1E8h+var_A8], r12
0x18004051d  mov     [rsp+1E8h+var_A0], r12
0x180040525  mov     r8d, 9
0x18004052b  lea     rdx, aProductid; "productid"
0x180040532  lea     rcx, [rsp+1E8h+var_B8]
0x18004053a  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x18004053f  nop
0x180040540  lea     rdx, [rsp+1E8h+var_B8]
0x180040548  mov     rcx, rbx
0x18004054b  call    ?at@value@json@web@@QEBAAEBV123@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; web::json::value::at(std::wstring const &)
0x180040550  mov     rcx, [rax]
0x180040553  mov     rax, [rcx]
0x180040556  mov     rax, [rax+0B0h]
0x18004055d  call    _guard_dispatch_icall
0x180040562  mov     rdx, [rax+10h]
0x180040566  mov     rcx, 7FFFFFFFFFFFFFFEh
0x180040570  sub     rcx, rdx
0x180040573  cmp     rcx, 1
0x180040577  jb      loc_180040987
0x18004057d  cmp     qword ptr [rax+18h], 7
0x180040582  jbe     short loc_180040587
0x180040584  mov     rax, [rax]
0x180040587  mov     [rsp+1E8h+var_1B8], rdx; __int64
0x18004058c  mov     [rsp+1E8h+Src], rax; Src
0x180040591  mov     [rsp+1E8h+var_1C8], 1; __int64
0x18004059a  lea     r9, asc_18008CFE8; "\\"
0x1800405a1  lea     rcx, [rsp+1E8h+var_98]; void *
0x1800405a9  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@U_String_constructor_concat_tag@1@AEBV01@QEB_W_K23@Z; std::wstring::wstring(std::_String_constructor_concat_tag,std::wstring const &,wchar_t const * const,unsigned __int64,wchar_t const * const,unsigned __int64)
0x1800405ae  or      r15d, 1
0x1800405b2  lea     rcx, [rsp+1E8h+var_B8]; void *
0x1800405ba  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800405bf  mov     rsi, [r13+58h]
0x1800405c3  mov     rax, [rsi]
0x1800405c6  mov     r14, [rax+40h]
0x1800405ca  xorps   xmm0, xmm0
0x1800405cd  movups  [rsp+1E8h+var_198], xmm0
0x1800405d2  mov     [rsp+1E8h+var_188], r12
0x1800405d7  mov     [rsp+1E8h+var_180], r12
0x1800405dc  mov     r8d, 6
0x1800405e2  lea     rdx, aSource; "source"
0x1800405e9  lea     rcx, [rsp+1E8h+var_198]
0x1800405ee  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x1800405f3  nop
0x1800405f4  lea     rdx, [rsp+1E8h+var_198]
0x1800405f9  mov     rcx, rbx
0x1800405fc  call    ?at@value@json@web@@QEBAAEBV123@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; web::json::value::at(std::wstring const &)
0x180040601  mov     rcx, [rax]
0x180040604  mov     rax, [rcx]
0x180040607  mov     rax, [rax+0B0h]
0x18004060e  call    _guard_dispatch_icall
0x180040613  mov     rdx, rax
0x180040616  lea     rcx, [rsp+1E8h+var_138]
0x18004061e  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x180040623  mov     [rsp+1E8h+var_118], 2
0x18004062b  xor     r8d, r8d
0x18004062e  lea     rdx, word_18008CB6E
0x180040635  lea     r11, aSource; "source"
0x18004063c  mov     rcx, r11
0x18004063f  call    _anonymous_namespace_____std_find_trivial_impl__anonymous_namespace____Find_traits_2_unsigned_short_
0x180040644  lea     rcx, word_18008CB6E
0x18004064b  cmp     rax, rcx
0x18004064e  jz      loc_1800409A7
0x180040654  sub     rax, r11
0x180040657  sar     rax, 1
0x18004065a  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18004065e  jz      loc_1800409A7
0x180040664  mov     qword ptr [rsp+1E8h+var_110], r11
0x18004066c  mov     qword ptr [rsp+1E8h+var_110+8], rax
0x180040674  lea     rax, [rsp+1E8h+var_98]
0x18004067c  cmp     [rsp+1E8h+var_80], 7
0x180040685  cmova   rax, [rsp+1E8h+var_98]
0x18004068e  mov     qword ptr [rsp+1E8h+var_100], rax
0x180040696  mov     rax, [rsp+1E8h+var_88]
0x18004069e  mov     qword ptr [rsp+1E8h+var_100+8], rax
0x1800406a6  mov     rcx, cs:?UUP_DYN_INSTALLED_PROD_REDIRECTION_ID@Registry@SystemInterface@@2QEB_WEB; wchar_t const * const SystemInterface::Registry::UUP_DYN_INSTALLED_PROD_REDIRECTION_ID
0x1800406ad  mov     qword ptr [rsp+1E8h+var_E8], rcx
0x1800406b5  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800406b9  inc     rax
0x1800406bc  cmp     [rcx+rax*2], r12w
0x1800406c1  jnz     short loc_1800406B9
0x1800406c3  mov     qword ptr [rsp+1E8h+var_E8+8], rax
0x1800406cb  movups  xmm0, [rsp+1E8h+var_110]
0x1800406d3  movdqu  [rsp+1E8h+var_168], xmm0
0x1800406dc  movups  xmm1, [rsp+1E8h+var_100]
0x1800406e4  movdqu  [rsp+1E8h+var_158], xmm1
0x1800406ed  movaps  xmm0, [rsp+1E8h+var_E8]
0x1800406f5  movdqa  [rsp+1E8h+var_148], xmm0
0x1800406fe  lea     rax, [rsp+1E8h+var_138]
0x180040706  mov     [rsp+1E8h+var_1C8], rax
0x18004070b  lea     r9, [rsp+1E8h+var_168]
0x180040713  lea     r8, [rsp+1E8h+var_158]
0x18004071b  lea     rdx, [rsp+1E8h+var_148]
0x180040723  mov     rcx, rsi
0x180040726  mov     rax, r14
0x180040729  call    _guard_dispatch_icall
0x18004072e  nop
0x18004072f  movsx   rax, [rsp+1E8h+var_118]
0x180040738  add     rax, 1
0x18004073c  jz      short loc_180040758
0x18004073e  sub     rax, 1
0x180040742  jz      short loc_180040758
0x180040744  cmp     rax, 1
0x180040748  jz      short loc_180040758
0x18004074a  lea     rcx, [rsp+1E8h+var_138]; void *
0x180040752  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180040757  nop
0x180040758  lea     rcx, [rsp+1E8h+var_198]; void *
0x18004075d  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180040762  mov     rsi, [r13+58h]
0x180040766  mov     rax, [rsi]
0x180040769  mov     r14, [rax+40h]
0x18004076d  xorps   xmm0, xmm0
0x180040770  movups  [rsp+1E8h+var_198], xmm0
0x180040775  mov     [rsp+1E8h+var_188], r12
0x18004077a  mov     [rsp+1E8h+var_180], r12
0x18004077f  mov     r8d, 7
0x180040785  lea     rdx, aVersion; "version"
0x18004078c  lea     rcx, [rsp+1E8h+var_198]
0x180040791  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x180040796  nop
0x180040797  lea     rdx, [rsp+1E8h+var_198]
0x18004079c  mov     rcx, rbx
0x18004079f  call    ?at@value@json@web@@QEBAAEBV123@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; web::json::value::at(std::wstring const &)
0x1800407a4  mov     rcx, [rax]
0x1800407a7  mov     rax, [rcx]
0x1800407aa  mov     rax, [rax+0B0h]
0x1800407b1  call    _guard_dispatch_icall
0x1800407b6  mov     rdx, rax
0x1800407b9  lea     rcx, [rsp+1E8h+var_138]
0x1800407c1  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x1800407c6  mov     [rsp+1E8h+var_118], 2
0x1800407ce  xor     r8d, r8d
0x1800407d1  lea     rdx, aDynamicinstall_0; "DynamicInstalledProductsArray"
0x1800407d8  lea     r11, aVersion; "version"
0x1800407df  mov     rcx, r11
0x1800407e2  call    _anonymous_namespace_____std_find_trivial_impl__anonymous_namespace____Find_traits_2_unsigned_short_
0x1800407e7  lea     rcx, aDynamicinstall_0; "DynamicInstalledProductsArray"
0x1800407ee  cmp     rax, rcx
0x1800407f1  jz      loc_18004098D
0x1800407f7  sub     rax, r11
0x1800407fa  sar     rax, 1
0x1800407fd  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180040801  jz      loc_18004098D
0x180040807  mov     qword ptr [rsp+1E8h+var_D8], r11
0x18004080f  mov     qword ptr [rsp+1E8h+var_D8+8], rax
0x180040817  lea     rax, [rsp+1E8h+var_98]
0x18004081f  cmp     [rsp+1E8h+var_80], 7
0x180040828  cmova   rax, [rsp+1E8h+var_98]
0x180040831  mov     qword ptr [rsp+1E8h+var_C8], rax
0x180040839  mov     rax, [rsp+1E8h+var_88]
0x180040841  mov     qword ptr [rsp+1E8h+var_C8+8], rax
0x180040849  mov     rcx, cs:?UUP_DYN_INSTALLED_PROD_REDIRECTION_ID@Registry@SystemInterface@@2QEB_WEB; wchar_t const * const SystemInterface::Registry::UUP_DYN_INSTALLED_PROD_REDIRECTION_ID
0x180040850  mov     qword ptr [rsp+1E8h+var_178], rcx
0x180040855  or      rax, 0FFFFFFFFFFFFFFFFh
0x180040859  inc     rax
0x18004085c  cmp     [rcx+rax*2], r12w
0x180040861  jnz     short loc_180040859
0x180040863  mov     qword ptr [rsp+1E8h+var_178+8], rax
0x180040868  movups  xmm0, [rsp+1E8h+var_D8]
0x180040870  movdqu  [rsp+1E8h+var_148], xmm0
0x180040879  movups  xmm1, [rsp+1E8h+var_C8]
0x180040881  movdqu  [rsp+1E8h+var_158], xmm1
0x18004088a  movaps  xmm0, [rsp+1E8h+var_178]
0x18004088f  movdqa  [rsp+1E8h+var_168], xmm0
0x180040898  lea     rax, [rsp+1E8h+var_138]
0x1800408a0  mov     [rsp+1E8h+var_1C8], rax
0x1800408a5  lea     r9, [rsp+1E8h+var_148]
0x1800408ad  lea     r8, [rsp+1E8h+var_158]
0x1800408b5  lea     rdx, [rsp+1E8h+var_168]
0x1800408bd  mov     rcx, rsi
0x1800408c0  mov     rax, r14
0x1800408c3  call    _guard_dispatch_icall
0x1800408c8  nop
0x1800408c9  movsx   rax, [rsp+1E8h+var_118]
0x1800408d2  add     rax, 1
0x1800408d6  jz      short loc_1800408F2
0x1800408d8  sub     rax, 1
0x1800408dc  jz      short loc_1800408F2
0x1800408de  cmp     rax, 1
0x1800408e2  jz      short loc_1800408F2
0x1800408e4  lea     rcx, [rsp+1E8h+var_138]; void *
0x1800408ec  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800408f1  nop
0x1800408f2  lea     rcx, [rsp+1E8h+var_198]; void *
0x1800408f7  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800408fc  nop
0x1800408fd  lea     rcx, [rsp+1E8h+var_98]; void *
0x180040905  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18004090a  add     rbx, 8
0x18004090e  jmp     loc_180040501
0x180040913  lea     rcx, [rsp+1E8h+var_78]
0x18004091b  call    ?_Tidy@?$vector@Vvalue@json@web@@V?$allocator@Vvalue@json@web@@@std@@@std@@AEAAXXZ; std::vector<web::json::value>::_Tidy(void)
0x180040920  nop
0x180040921  cmp     [rsp+1E8h+var_38], r12b
0x180040929  jz      short loc_180040954
0x18004092b  movsx   rax, [rsp+1E8h+var_40]
0x180040934  add     rax, 1
0x180040938  jz      short loc_180040954
0x18004093a  sub     rax, 1
0x18004093e  jz      short loc_180040954
0x180040940  cmp     rax, 1
0x180040944  jz      short loc_180040954
0x180040946  lea     rcx, [rsp+1E8h+var_60]; void *
0x18004094e  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180040953  nop
0x180040954  mov     rcx, [rsp+1E8h+var_30]
0x18004095c  xor     rcx, rsp; StackCookie
0x18004095f  call    __security_check_cookie
0x180040964  lea     r11, [rsp+1E8h+var_28]
0x18004096c  mov     rbx, [r11+38h]
0x180040970  mov     rsi, [r11+40h]
0x180040974  mov     rsp, r11
0x180040977  pop     r15
0x180040979  pop     r14
0x18004097b  pop     r13
0x18004097d  pop     r12
0x18004097f  pop     rdi
0x180040980  retn
0x180040981  call    ?_Throw_bad_variant_access@std@@YAXXZ; std::_Throw_bad_variant_access(void)
0x180040987  call    ?_Xlen_string@std@@YAXXZ; std::_Xlen_string(void)
0x18004098d  mov     rcx, [rsp+1E8h]; this
0x180040995  lea     r8, aCW1SPackagesMi_0; "C:\\__w\\1\\s\\packages\\Microsoft.Wind"...
0x18004099c  mov     edx, 0C9h; void *
0x1800409a1  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
0x1800409a7  mov     rcx, [rsp+1E8h]; this
0x1800409af  lea     r8, aCW1SPackagesMi_0; "C:\\__w\\1\\s\\packages\\Microsoft.Wind"...
0x1800409b6  mov     edx, 0C9h; void *
0x1800409bb  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
```
