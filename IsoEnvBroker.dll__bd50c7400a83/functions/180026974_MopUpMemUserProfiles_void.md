# MopUpMemUserProfiles(void)

- ea: `0x180026974`
- end: `0x180027356`
- name: `?MopUpMemUserProfiles@@YA_NXZ`
- size: `2530`
- prototype: `bool(void)`
- caller_count: `2`
- callee_count: `28`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x180023170`
- `0x180056060`

## callees

- `0x180002520`
- `0x180002ee8`
- `0x1800030d0`
- `0x1800050cd`
- `0x1800075e4`
- `0x18000e4ec`
- `0x180010148`
- `0x18001045c`
- `0x180011e18`
- `0x180014c04`
- `0x1800158dc`
- `0x18001ac4c`
- `0x18001e648`
- `0x18001e820`
- `0x18001e8a8`
- `0x18001f7c0`
- `0x18001fa68`
- `0x18002030c`
- `0x1800206a0`
- `0x1800207d0`
- `0x180020de4`
- `0x1800214c4`
- `0x18002193c`
- `0x180026780`
- `0x180026974`
- `0x18002ab4c`
- `0x180030214`
- `0x180031a30`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180027252`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180027252`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180026e77`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180026e77`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800269dd`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800269dd`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180026a12`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180027171`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800272f6`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180026a12`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180027171`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800272f6`
- `USERENV!DeleteProfileW` at `0x180027248`
- `USERENV!DeleteProfileW` at `0x180027248`

## string_xrefs

- `0x1800269f6`: `Unexpected: failed to open profile list: %#x`
- `0x180026e6b`: `ProfileImagePath`
- `0x180026ea9`: `Unexpected: failed to read ProfileImagePath for key %s: %#x`
- `0x18002729d`: `DeleteProfile failed for %s: %#x`
- `0x180027331`: `onecore\internal\sdk\inc\wil\opensource\wil\registry_helpers.h`
- `0x180027343`: `onecore\internal\sdk\inc\wil\opensource\wil\registry_helpers.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=15
bool MopUpMemUserProfiles(void)
{
  int v0; // r14d
  bool result; // al
  const char *v2; // r9
  int v3; // eax
  bool v4; // sf
  __int64 *v5; // rax
  int v6; // eax
  unsigned int v7; // esi
  const char *v8; // r9
  int v9; // r15d
  char *v10; // r12
  __m128i si128; // xmm6
  __int128 v12; // xmm0
  __int64 v13; // rdx
  unsigned __int64 v14; // rcx
  const wchar_t *v15; // rax
  char v16; // bl
  __int128 *v17; // rax
  char *v18; // rcx
  __int128 v19; // xmm0
  const WCHAR *v20; // rdx
  int ValueW; // eax
  bool v22; // sf
  LPCWSTR *v23; // r8
  LPCWSTR *v24; // rdx
  __int64 v25; // r9
  unsigned __int64 i; // rcx
  __int64 v27; // rcx
  __int64 v28; // r8
  unsigned __int64 v29; // rdx
  char *v30; // rdi
  __int64 v31; // rbx
  const WCHAR *v32; // rdx
  unsigned __int64 v33; // r8
  __int64 v34; // rcx
  bool v35; // r15
  __int64 *v36; // rdi
  __int64 *j; // rbx
  _QWORD *v38; // r9
  LPCWSTR *v39; // r8
  const WCHAR *v40; // rcx
  DWORD LastError; // eax
  LPCWSTR *v42; // r8
  int phkResult; // [rsp+20h] [rbp-558h]
  HKEY hKey; // [rsp+40h] [rbp-538h] BYREF
  __int128 v45; // [rsp+50h] [rbp-528h]
  DWORD pcbData[4]; // [rsp+60h] [rbp-518h] BYREF
  __int64 v47; // [rsp+70h] [rbp-508h] BYREF
  __int64 *v48; // [rsp+78h] [rbp-500h] BYREF
  __int64 v49; // [rsp+80h] [rbp-4F8h]
  char *v50; // [rsp+88h] [rbp-4F0h] BYREF
  __int128 v51; // [rsp+90h] [rbp-4E8h]
  __int64 v52; // [rsp+A0h] [rbp-4D8h]
  __int64 v53; // [rsp+A8h] [rbp-4D0h]
  __int64 v54; // [rsp+B0h] [rbp-4C8h] BYREF
  char v55; // [rsp+B8h] [rbp-4C0h]
  _OWORD v56[2]; // [rsp+C0h] [rbp-4B8h] BYREF
  __int64 v57; // [rsp+E0h] [rbp-498h]
  char v58; // [rsp+E8h] [rbp-490h]
  __int128 v59; // [rsp+F0h] [rbp-488h]
  char v60; // [rsp+100h] [rbp-478h]
  _QWORD v61[2]; // [rsp+108h] [rbp-470h] BYREF
  char v62; // [rsp+118h] [rbp-460h] BYREF
  _BYTE v63[40]; // [rsp+120h] [rbp-458h] BYREF
  __int64 v64; // [rsp+148h] [rbp-430h] BYREF
  _BYTE v65[16]; // [rsp+158h] [rbp-420h] BYREF
  _BYTE v66[16]; // [rsp+168h] [rbp-410h] BYREF
  _BYTE v67[16]; // [rsp+178h] [rbp-400h] BYREF
  _BYTE v68[16]; // [rsp+188h] [rbp-3F0h] BYREF
  LPCWSTR lpSidString[2]; // [rsp+198h] [rbp-3E0h] BYREF
  __m128i v70; // [rsp+1A8h] [rbp-3D0h]
  wchar_t *S1[2]; // [rsp+1B8h] [rbp-3C0h] BYREF
  __int64 v72; // [rsp+1C8h] [rbp-3B0h]
  __int64 v73; // [rsp+1D0h] [rbp-3A8h]
  __int64 v74; // [rsp+1D8h] [rbp-3A0h]
  int v75; // [rsp+1E0h] [rbp-398h]
  int v76; // [rsp+1E4h] [rbp-394h]
  __int64 v77; // [rsp+1E8h] [rbp-390h]
  _BYTE v78[24]; // [rsp+1F0h] [rbp-388h] BYREF
  __int128 v79; // [rsp+208h] [rbp-370h]
  int v80; // [rsp+218h] [rbp-360h]
  __int64 v81; // [rsp+220h] [rbp-358h]
  LPCWSTR lpSubKey[3]; // [rsp+228h] [rbp-350h] BYREF
  unsigned __int64 v83; // [rsp+240h] [rbp-338h]
  char *v84; // [rsp+248h] [rbp-330h]
  int v85; // [rsp+250h] [rbp-328h]
  char *v86[5]; // [rsp+260h] [rbp-318h] BYREF
  __int64 v87; // [rsp+288h] [rbp-2F0h]
  char *v88[7]; // [rsp+2A0h] [rbp-2D8h] BYREF
  char *v89[7]; // [rsp+2D8h] [rbp-2A0h] BYREF
  _WORD Src[264]; // [rsp+310h] [rbp-268h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+578h] [rbp+0h]

  v0 = 0;
  pcbData[0] = 0;
  try
  {
    result = IsMemAuthorityPresent();
    if ( result )
    {
      hKey = 0;
      v3 = RegOpenKeyExW(
             HKEY_LOCAL_MACHINE,
             L"SOFTWARE\\Microsoft\\Windows NT\\CurrentVersion\\ProfileList",
             0,
             0xF003Fu,
             &hKey);
      v4 = v3 < 0;
      if ( v3 > 0 )
      {
        v3 = (unsigned __int16)v3 | 0x80070000;
        v4 = v3 < 0;
      }
      if ( v4 )
      {
        Log(3u, L"Unexpected: failed to open profile list: %#x", (unsigned int)v3);
        if ( hKey )
          RegCloseKey(hKey);
        result = 0;
      }
      else
      {
        LODWORD(v47) = 0;
        v48 = 0;
        v49 = 0;
        v5 = (__int64 *)operator new(0x58u);
        *v5 = (__int64)v5;
        v5[1] = (__int64)v5;
        v48 = v5;
        v50 = 0;
        v51 = 0;
        v52 = 7;
        v53 = 8;
        LODWORD(v47) = 1065353216;
        std::_Hash_vec<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<void * const,std::shared_ptr<ProcessConnection::ProcessExitCallbackContext>>>>>>>::_Assign_grow(
          &v50,
          16,
          v5);
        memset_0(Src, 0, 0x208u);
        std::basic_regex<wchar_t,std::regex_traits<wchar_t>>::basic_regex<wchar_t,std::regex_traits<wchar_t>>(v63);
        *(_QWORD *)pcbData = S1;
        v76 = 0;
        *(_OWORD *)S1 = 0;
        v72 = 0;
        v73 = 7;
        LOWORD(S1[0]) = 0;
        v74 = 0;
        v75 = -1;
        v77 = 0;
        *(_QWORD *)&v45 = v78;
        memset(v78, 0, sizeof(v78));
        *(_QWORD *)&v79 = 7;
        *(_WORD *)v78 = 0;
        *((_QWORD *)&v79 + 1) = hKey;
        v80 = -1;
        v81 = 0;
        if ( hKey )
        {
          v80 = 0;
          v6 = wil::reg::key_iterator_data<std::wstring>::enumerate_current_index(v78);
          if ( v6 < 0 )
            wil::details::in1diag3::_Throw_Hr(
              retaddr,
              (void *)0x6EE,
              (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\registry_helpers.h",
              (const char *)(unsigned int)v6,
              phkResult);
        }
        v7 = 0;
        wil::make_range<wil::reg::iterator_t<wil::reg::key_iterator_data<std::wstring>>>(v88, v78, S1);
        wil::reg::iterator_t<wil::reg::key_iterator_data<std::wstring>>::iterator_t<wil::reg::key_iterator_data<std::wstring>>(
          lpSubKey,
          v88);
        wil::reg::iterator_t<wil::reg::key_iterator_data<std::wstring>>::iterator_t<wil::reg::key_iterator_data<std::wstring>>(
          v86,
          v89);
        v9 = v87;
        v10 = v86[4];
        si128 = _mm_load_si128((const __m128i *)&_xmm);
        while ( v85 != -1 && v9 != -1 && v84 != v10 || v85 != v9 )
        {
          if ( v85 == -1 )
            wil::details::in1diag3::_FailFast_Unexpected(
              retaddr,
              (void *)0x6FF,
              (int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\registry_helpers.h",
              v8);
          v54 = 0;
          v55 = 0;
          memset(v56, 0, sizeof(v56));
          v57 = 0;
          v58 = 0;
          v59 = 0;
          v60 = 0;
          v61[0] = 0;
          v61[1] = 0;
          v62 = 0;
          if ( (unsigned __int8)std::regex_match<std::char_traits<wchar_t>,std::allocator<wchar_t>,std::allocator<std::sub_match<std::_String_const_iterator<std::_String_val<std::_Simple_types<wchar_t>>>>>,wchar_t,std::regex_traits<wchar_t>>(
                                  lpSubKey,
                                  &v54,
                                  v63)
            && *((_QWORD *)&v56[0] + 1) - *(_QWORD *)&v56[0] == 72 )
          {
            if ( *(_BYTE *)(*(_QWORD *)&v56[0] + 40LL) )
              v12 = *(_OWORD *)(*(_QWORD *)&v56[0] + 24LL);
            else
              v12 = 0;
            v45 = v12;
            *(_OWORD *)S1 = 0;
            v72 = 0;
            v73 = 0;
            if ( (_QWORD)v12 == *((_QWORD *)&v12 + 1) )
            {
              v13 = 0;
              v72 = 0;
              v14 = 7;
              v73 = 7;
              LOWORD(S1[0]) = 0;
            }
            else
            {
              std::wstring::_Construct<1,wchar_t const *>(
                (char **)S1,
                (const void *)v12,
                (__int64)(*((_QWORD *)&v45 + 1) - v45) >> 1);
              v14 = v73;
              v13 = v72;
            }
            v15 = (const wchar_t *)S1;
            if ( v14 > 7 )
              v15 = S1[0];
            if ( v13 == 3 && !wmemcmp(v15, L"110", 3u) )
            {
              v16 = 1;
              ++v7;
            }
            else
            {
              v16 = 0;
            }
            if ( 0xAAAAAAAAAAAAAAABuLL * ((__int64)(*((_QWORD *)&v56[0] + 1) - *(_QWORD *)&v56[0]) >> 3) > 2 )
            {
              v17 = (__int128 *)(*(_QWORD *)&v56[0] + 48LL);
              v18 = (char *)(*(_QWORD *)&v56[0] + 64LL);
            }
            else
            {
              v17 = (__int128 *)v61;
              v18 = &v62;
            }
            if ( *v18 )
              v19 = *v17;
            else
              v19 = 0;
            v45 = v19;
            *(_OWORD *)lpSidString = 0;
            v70 = 0;
            if ( (_QWORD)v19 == *((_QWORD *)&v19 + 1) )
            {
              v70 = si128;
              LOWORD(lpSidString[0]) = 0;
            }
            else
            {
              std::wstring::_Construct<1,wchar_t const *>(
                (char **)lpSidString,
                (const void *)v45,
                (__int64)(*((_QWORD *)&v45 + 1) - v45) >> 1);
            }
            Src[0] = 0;
            v20 = (const WCHAR *)lpSubKey;
            if ( v83 > 7 )
              v20 = lpSubKey[0];
            pcbData[0] = 520;
            ValueW = RegGetValueW(hKey, v20, L"ProfileImagePath", 0x10000006u, 0, Src, pcbData);
            v22 = ValueW < 0;
            if ( ValueW > 0 )
            {
              ValueW = (unsigned __int16)ValueW | 0x80070000;
              v22 = ValueW < 0;
            }
            if ( v22 )
            {
              v23 = lpSubKey;
              if ( v83 > 7 )
                v23 = (LPCWSTR *)lpSubKey[0];
              Log(3u, L"Unexpected: failed to read ProfileImagePath for key %s: %#x", v23, (unsigned int)ValueW);
            }
            v24 = lpSidString;
            if ( v70.m128i_i64[1] > 7uLL )
              v24 = (LPCWSTR *)lpSidString[0];
            v25 = 0xCBF29CE484222325uLL;
            for ( i = 0; i < 2 * v70.m128i_i64[0]; ++i )
              v25 = 0x100000001B3LL * (*((unsigned __int8 *)v24 + i) ^ (unsigned __int64)v25);
            if ( ____Find_last_V__basic_string__WU__char_traits__W_std__V__allocator__W_2__std______Hash_V___Umap_traits_V__basic_string__WU__char_traits__W_std__V__allocator__W_2__std__UProfileData__2__MopUpMemUserProfiles__YA_NXZ_V___Uhash_compare_V__basic_string__WU__char_traits__W_std__V__allocator__W_2__std__U__hash_V__basic_string__WU__char_traits__W_std__V__allocator__W_2__std___2_U__equal_to_V__basic_string__WU__char_traits__W_std__V__allocator__W_2__std___2__2_V__allocator_U__pair___CBV__basic_string__WU__char_traits__W_std__V__allocator__W_2__std__UProfileData__2__MopUpMemUserProfiles__YA_NXZ__std___2__0A__std___std__IEBA_AU___Hash_find_last_result_PEAU___List_node_U__pair___CBV__basic_string__WU__char_traits__W_std__V__allocator__W_2__std__UProfileData__2__MopUpMemUserProfiles__YA_NXZ__std__PEAX_std___1_AEBV__basic_string__WU__char_traits__W_std__V__allocator__W_2__1__K_Z(
                   &v47,
                   &v64,
                   (__int64)lpSidString,
                   v25)[1] )
            {
              if ( v16 )
              {
                *(_BYTE *)(*(_QWORD *)____Try_emplace_AEBV__basic_string__WU__char_traits__W_std__V__allocator__W_2__std____V____Hash_V___Umap_traits_V__basic_string__WU__char_traits__W_std__V__allocator__W_2__std__UProfileData__2__MopUpMemUserProfiles__YA_NXZ_V___Uhash_compare_V__basic_string__WU__char_traits__W_std__V__allocator__W_2__std__U__hash_V__basic_string__WU__char_traits__W_std__V__allocator__W_2__std___2_U__equal_to_V__basic_string__WU__char_traits__W_std__V__allocator__W_2__std___2__2_V__allocator_U__pair___CBV__basic_string__WU__char_traits__W_std__V__allocator__W_2__std__UProfileData__2__MopUpMemUserProfiles__YA_NXZ__std___2__0A__std___std__IEAA_AU__pair_PEAU___List_node_U__pair___CBV__basic_string__WU__char_traits__W_std__V__allocator__W_2__std__UProfileData__2__MopUpMemUserProfiles__YA_NXZ__std__PEAX_std___N_1_AEBV__basic_string__WU__char_traits__W_std__V__allocator__W_2__1__Z(
                                        (float *)&v47,
                                        (__int64)v65,
                                        lpSidString)
                         + 48LL) = 1;
                v27 = *(_QWORD *)____Try_emplace_AEBV__basic_string__WU__char_traits__W_std__V__allocator__W_2__std____V____Hash_V___Umap_traits_V__basic_string__WU__char_traits__W_std__V__allocator__W_2__std__UProfileData__2__MopUpMemUserProfiles__YA_NXZ_V___Uhash_compare_V__basic_string__WU__char_traits__W_std__V__allocator__W_2__std__U__hash_V__basic_string__WU__char_traits__W_std__V__allocator__W_2__std___2_U__equal_to_V__basic_string__WU__char_traits__W_std__V__allocator__W_2__std___2__2_V__allocator_U__pair___CBV__basic_string__WU__char_traits__W_std__V__allocator__W_2__std__UProfileData__2__MopUpMemUserProfiles__YA_NXZ__std___2__0A__std___std__IEAA_AU__pair_PEAU___List_node_U__pair___CBV__basic_string__WU__char_traits__W_std__V__allocator__W_2__std__UProfileData__2__MopUpMemUserProfiles__YA_NXZ__std__PEAX_std___N_1_AEBV__basic_string__WU__char_traits__W_std__V__allocator__W_2__1__Z(
                                   (float *)&v47,
                                   (__int64)v66,
                                   lpSidString)
                    + 56LL;
                v29 = -1;
                do
                  ++v29;
                while ( Src[v29] );
                if ( v29 > *(_QWORD *)(v27 + 24) )
                {
                  ____Reallocate_for_V_lambda_1___1_____Assign__W___basic_string__WU__char_traits__W_std__V__allocator__W_2__std__AEAAAEAV23_QEB_W_K_Z_PEB_W___basic_string__WU__char_traits__W_std__V__allocator__W_2__std__AEAAAEAV01__KV_lambda_1___1_____Assign__W_01_AEAAAEAV01_QEB_W0_Z_PEB_W_Z(
                    (char **)v27,
                    v29,
                    v28,
                    Src);
                }
                else
                {
                  if ( *(_QWORD *)(v27 + 24) <= 7u )
                    v30 = (char *)v27;
                  else
                    v30 = *(char **)v27;
                  *(_QWORD *)(v27 + 16) = v29;
                  v31 = 2 * v29;
                  memmove_0(v30, Src, 2 * v29);
                  *(_WORD *)&v30[v31] = 0;
                }
              }
              else
              {
                *(_BYTE *)(*(_QWORD *)____Try_emplace_AEBV__basic_string__WU__char_traits__W_std__V__allocator__W_2__std____V____Hash_V___Umap_traits_V__basic_string__WU__char_traits__W_std__V__allocator__W_2__std__UProfileData__2__MopUpMemUserProfiles__YA_NXZ_V___Uhash_compare_V__basic_string__WU__char_traits__W_std__V__allocator__W_2__std__U__hash_V__basic_string__WU__char_traits__W_std__V__allocator__W_2__std___2_U__equal_to_V__basic_string__WU__char_traits__W_std__V__allocator__W_2__std___2__2_V__allocator_U__pair___CBV__basic_string__WU__char_traits__W_std__V__allocator__W_2__std__UProfileData__2__MopUpMemUserProfiles__YA_NXZ__std___2__0A__std___std__IEAA_AU__pair_PEAU___List_node_U__pair___CBV__basic_string__WU__char_traits__W_std__V__allocator__W_2__std__UProfileData__2__MopUpMemUserProfiles__YA_NXZ__std__PEAX_std___N_1_AEBV__basic_string__WU__char_traits__W_std__V__allocator__W_2__1__Z(
                                        (float *)&v47,
                                        (__int64)v67,
                                        lpSidString)
                         + 49LL) = 1;
              }
            }
            else
            {
              v78[0] = v16;
              v78[1] = v16 == 0;
              *(_DWORD *)&v78[2] = 0;
              *(_WORD *)&v78[6] = 0;
              v32 = Src;
              if ( !v16 )
                v32 = &word_180096C4C;
              *(_OWORD *)&v78[8] = 0;
              v79 = 0;
              v33 = -1;
              do
                ++v33;
              while ( v32[v33] );
              std::wstring::_Construct<1,wchar_t const *>((char **)&v78[8], v32, v33);
              v34 = *(_QWORD *)____Try_emplace_AEBV__basic_string__WU__char_traits__W_std__V__allocator__W_2__std____V____Hash_V___Umap_traits_V__basic_string__WU__char_traits__W_std__V__allocator__W_2__std__UProfileData__2__MopUpMemUserProfiles__YA_NXZ_V___Uhash_compare_V__basic_string__WU__char_traits__W_std__V__allocator__W_2__std__U__hash_V__basic_string__WU__char_traits__W_std__V__allocator__W_2__std___2_U__equal_to_V__basic_string__WU__char_traits__W_std__V__allocator__W_2__std___2__2_V__allocator_U__pair___CBV__basic_string__WU__char_traits__W_std__V__allocator__W_2__std__UProfileData__2__MopUpMemUserProfiles__YA_NXZ__std___2__0A__std___std__IEAA_AU__pair_PEAU___List_node_U__pair___CBV__basic_string__WU__char_traits__W_std__V__allocator__W_2__std__UProfileData__2__MopUpMemUserProfiles__YA_NXZ__std__PEAX_std___N_1_AEBV__basic_string__WU__char_traits__W_std__V__allocator__W_2__1__Z(
                                 (float *)&v47,
                                 (__int64)v68,
                                 lpSidString);
              *(_WORD *)(v34 + 48) = *(_WORD *)v78;
              std::wstring::operator=(v34 + 56, &v78[8]);
              std::wstring::~wstring((char **)&v78[8]);
            }
            v0 |= 3u;
            std::wstring::~wstring((char **)lpSidString);
            std::wstring::~wstring((char **)S1);
          }
          std::vector<std::sub_match<std::_String_const_iterator<std::_String_val<std::_Simple_types<wchar_t>>>>>::~vector<std::sub_match<std::_String_const_iterator<std::_String_val<std::_Simple_types<wchar_t>>>>>(v56);
          wil::reg::iterator_t<wil::reg::key_iterator_data<std::wstring>>::operator++(lpSubKey);
        }
        std::wstring::~wstring(v86);
        std::wstring::~wstring((char **)lpSubKey);
        std::wstring::~wstring(v89);
        std::wstring::~wstring(v88);
        if ( v7 )
        {
          Log(4u, L"Found %u MEM profiles (out of %zu)", v7, v49);
          v35 = 0;
          v36 = v48;
          for ( j = (__int64 *)*v48; j != v36; j = (__int64 *)*j )
          {
            if ( *((_BYTE *)j + 48) && !*((_BYTE *)j + 49) )
            {
              *(_QWORD *)&v45 = L"S-1-5-110-{}";
              *((_QWORD *)&v45 + 1) = 12;
              std::format<std::wstring &>(lpSidString);
              v38 = j + 7;
              if ( (unsigned __int64)j[10] > 7 )
                v38 = (_QWORD *)*v38;
              v39 = lpSidString;
              if ( v70.m128i_i64[1] > 7uLL )
                v39 = (LPCWSTR *)lpSidString[0];
              Log(4u, L"Cleaning up MEM profile for %s at %s", v39, v38);
              v40 = (const WCHAR *)lpSidString;
              if ( v70.m128i_i64[1] > 7uLL )
                v40 = lpSidString[0];
              if ( !DeleteProfileW(v40, 0, 0) )
              {
                LastError = GetLastError();
                v42 = lpSidString;
                if ( LastError == 2 )
                {
                  if ( v70.m128i_i64[1] > 7uLL )
                    v42 = (LPCWSTR *)lpSidString[0];
                  Log(4u, L"No profile found for %s?", v42);
                }
                else
                {
                  if ( v70.m128i_i64[1] > 7uLL )
                    v42 = (LPCWSTR *)lpSidString[0];
                  Log(3u, L"DeleteProfile failed for %s: %#x", v42, LastError);
                  v35 = 1;
                }
              }
              std::wstring::~wstring((char **)lpSidString);
            }
          }
          std::basic_regex<wchar_t,std::regex_traits<wchar_t>>::~basic_regex<wchar_t,std::regex_traits<wchar_t>>(v63);
          std::_Hash_vec<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<void * const,std::shared_ptr<ProcessConnection::ProcessExitCallbackContext>>>>>>>::~_Hash_vec<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<void * const,std::shared_ptr<ProcessConnection::ProcessExitCallbackContext>>>>>>>(&v50);
          __1__list_U__pair___CBV__basic_string__WU__char_traits__W_std__V__allocator__W_2__std__UProfileData__2__MopUpMemUserProfiles__YA_NXZ__std__V__allocator_U__pair___CBV__basic_string__WU__char_traits__W_std__V__allocator__W_2__std__UProfileData__2__MopUpMemUserProfiles__YA_NXZ__std___2__std__QEAA_XZ(&v48);
          if ( hKey )
            RegCloseKey(hKey);
          result = v35;
        }
        else
        {
          Log(4u, L"(no MEM profiles found)");
          std::basic_regex<wchar_t,std::regex_traits<wchar_t>>::~basic_regex<wchar_t,std::regex_traits<wchar_t>>(v63);
          std::_Hash_vec<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<void * const,std::shared_ptr<ProcessConnection::ProcessExitCallbackContext>>>>>>>::~_Hash_vec<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<void * const,std::shared_ptr<ProcessConnection::ProcessExitCallbackContext>>>>>>>(&v50);
          __1__list_U__pair___CBV__basic_string__WU__char_traits__W_std__V__allocator__W_2__std__UProfileData__2__MopUpMemUserProfiles__YA_NXZ__std__V__allocator_U__pair___CBV__basic_string__WU__char_traits__W_std__V__allocator__W_2__std__UProfileData__2__MopUpMemUserProfiles__YA_NXZ__std___2__std__QEAA_XZ(&v48);
          if ( hKey )
            RegCloseKey(hKey);
          result = 0;
        }
      }
    }
  }
  catch ( ... )
  {
    wil::details::in1diag3::Log_CaughtException(
      retaddr,
      (void *)0x226,
      (unsigned int)"onecoreuap\\windows\\core\\isoenvbroker\\lib\\common\\UserAccountHelpers.h",
      v2);
    return 0;
  }
  return result;
}

```

## disassembly

```asm
0x180026974  mov     rax, rsp
0x180026977  push    rbx
0x180026978  push    rsi
0x180026979  push    rdi
0x18002697a  push    r12
0x18002697c  push    r13
0x18002697e  push    r14
0x180026980  push    r15
0x180026982  sub     rsp, 540h
0x180026989  movaps  xmmword ptr [rax-48h], xmm6
0x18002698d  mov     rax, cs:__security_cookie
0x180026994  xor     rax, rsp
0x180026997  mov     [rsp+578h+var_58], rax
0x18002699f  xor     r13d, r13d
0x1800269a2  mov     r14d, r13d
0x1800269a5  mov     [rsp+578h+var_518], r13d
0x1800269aa  call    ?IsMemAuthorityPresent@@YA_NXZ; IsMemAuthorityPresent(void)
0x1800269af  test    al, al
0x1800269b1  jz      loc_180027303
0x1800269b7  mov     [rsp+578h+hKey], r13
0x1800269bc  lea     rax, [rsp+578h+hKey]
0x1800269c1  mov     [rsp+578h+phkResult], rax; int
0x1800269c6  mov     r9d, 0F003Fh; samDesired
0x1800269cc  xor     r8d, r8d; ulOptions
0x1800269cf  lea     rdx, SubKey; "SOFTWARE\\Microsoft\\Windows NT\\Curren"...
0x1800269d6  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1800269dd  call    cs:__imp_RegOpenKeyExW
0x1800269e3  test    eax, eax
0x1800269e5  jle     short loc_1800269F1
0x1800269e7  movzx   eax, ax
0x1800269ea  or      eax, 80070000h
0x1800269ef  test    eax, eax
0x1800269f1  jns     short loc_180026A1F
0x1800269f3  mov     r8d, eax
0x1800269f6  lea     rdx, aUnexpectedFail_0; "Unexpected: failed to open profile list"...
0x1800269fd  mov     ecx, 3; unsigned __int8
0x180026a02  call    ?Log@@YAXEPEB_WZZ; Log(uchar,wchar_t const *,...)
0x180026a07  nop
0x180026a08  mov     rcx, [rsp+578h+hKey]; hKey
0x180026a0d  test    rcx, rcx
0x180026a10  jz      short loc_180026A18
0x180026a12  call    cs:__imp_RegCloseKey
0x180026a18  xor     al, al
0x180026a1a  jmp     loc_180027303
0x180026a1f  mov     dword ptr [rsp+578h+var_508], 0
0x180026a27  mov     [rsp+578h+var_500], r13
0x180026a2c  mov     [rsp+578h+var_4F8], r13
0x180026a34  mov     ecx, 58h ; 'X'; Size
0x180026a39  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180026a3e  mov     [rax], rax
0x180026a41  mov     [rax+8], rax
0x180026a45  mov     [rsp+578h+var_500], rax
0x180026a4a  mov     [rsp+578h+var_4F0], r13
0x180026a52  xorps   xmm0, xmm0
0x180026a55  movdqa  [rsp+578h+var_4E8], xmm0
0x180026a5e  mov     edi, 7
0x180026a63  mov     [rsp+578h+var_4D8], rdi
0x180026a6b  mov     [rsp+578h+var_4D0], 8
0x180026a77  mov     dword ptr [rsp+578h+var_508], 3F800000h
0x180026a7f  mov     r8, rax
0x180026a82  lea     edx, [rdi+9]
0x180026a85  lea     rcx, [rsp+578h+var_4F0]
0x180026a8d  call    ?_Assign_grow@?$_Hash_vec@V?$allocator@V?$_List_unchecked_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@QEAXV?$shared_ptr@UProcessExitCallbackContext@ProcessConnection@@@std@@@std@@@std@@@std@@@std@@@std@@@std@@QEAAX_KV?$_List_unchecked_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@QEAXV?$shared_ptr@UProcessExitCallbackContext@ProcessConnection@@@std@@@std@@@std@@@std@@@2@@Z; std::_Hash_vec<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<void * const,std::shared_ptr<ProcessConnection::ProcessExitCallbackContext>>>>>>>::_Assign_grow(unsigned __int64,std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<void * const,std::shared_ptr<ProcessConnection::ProcessExitCallbackContext>>>>>)
0x180026a92  nop
0x180026a93  xor     edx, edx; Val
0x180026a95  mov     r8d, 208h; Size
0x180026a9b  lea     rcx, [rsp+578h+Src]; void *
0x180026aa3  call    memset_0
0x180026aa8  lea     rcx, [rsp+578h+var_458]
0x180026ab0  call    ??0?$basic_regex@_WV?$regex_traits@_W@std@@@std@@QEAA@PEB_WW4syntax_option_type@regex_constants@1@@Z; std::basic_regex<wchar_t,std::regex_traits<wchar_t>>::basic_regex<wchar_t,std::regex_traits<wchar_t>>(wchar_t const *,std::regex_constants::syntax_option_type)
0x180026ab5  nop
0x180026ab6  lea     rax, [rsp+578h+S1]
0x180026abe  mov     qword ptr [rsp+578h+var_518], rax
0x180026ac3  mov     [rsp+578h+var_394], r13d
0x180026acb  xorps   xmm0, xmm0
0x180026ace  movups  xmmword ptr [rsp+578h+S1], xmm0
0x180026ad6  mov     [rsp+578h+var_3B0], r13
0x180026ade  mov     [rsp+578h+var_3A8], rdi
0x180026ae6  mov     word ptr [rsp+578h+S1], r13w
0x180026aef  mov     [rsp+578h+var_3A0], r13
0x180026af7  or      ebx, 0FFFFFFFFh
0x180026afa  mov     [rsp+578h+var_398], ebx
0x180026b01  mov     [rsp+578h+var_390], r13
0x180026b09  lea     rax, [rsp+578h+var_388]
0x180026b11  mov     qword ptr [rsp+578h+var_528], rax
0x180026b16  mov     rcx, [rsp+578h+hKey]
0x180026b1b  movups  [rsp+578h+var_388], xmm0
0x180026b23  mov     [rsp+578h+var_378], r13
0x180026b2b  mov     qword ptr [rsp+578h+var_370], rdi
0x180026b33  mov     word ptr [rsp+578h+var_388], r13w
0x180026b3c  mov     qword ptr [rsp+578h+var_370+8], rcx
0x180026b44  mov     [rsp+578h+var_360], ebx
0x180026b4b  mov     [rsp+578h+var_358], r13
0x180026b53  test    rcx, rcx
0x180026b56  jz      short loc_180026B7D
0x180026b58  mov     [rsp+578h+var_360], r13d
0x180026b60  lea     rcx, [rsp+578h+var_388]; Src
0x180026b68  call    ?enumerate_current_index@?$key_iterator_data@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@reg@wil@@AEAAJXZ; wil::reg::key_iterator_data<std::wstring>::enumerate_current_index(void)
0x180026b6d  mov     rcx, [rsp+578h]; this
0x180026b75  test    eax, eax
0x180026b77  js      loc_18002732E
0x180026b7d  mov     esi, r13d
0x180026b80  lea     r8, [rsp+578h+S1]
0x180026b88  lea     rdx, [rsp+578h+var_388]
0x180026b90  lea     rcx, [rsp+578h+var_2D8]
0x180026b98  call    ??$make_range@V?$iterator_t@V?$key_iterator_data@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@reg@wil@@@reg@wil@@@wil@@YA?AV?$pointer_range@V?$iterator_t@V?$key_iterator_data@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@reg@wil@@@reg@wil@@@details@0@V?$iterator_t@V?$key_iterator_data@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@reg@wil@@@reg@0@0@Z; wil::make_range<wil::reg::iterator_t<wil::reg::key_iterator_data<std::wstring>>>(wil::reg::iterator_t<wil::reg::key_iterator_data<std::wstring>>,wil::reg::iterator_t<wil::reg::key_iterator_data<std::wstring>>)
0x180026b9d  nop
0x180026b9e  lea     rdx, [rsp+578h+var_2D8]
0x180026ba6  lea     rcx, [rsp+578h+lpSubKey]
0x180026bae  call    ??0?$iterator_t@V?$key_iterator_data@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@reg@wil@@@reg@wil@@QEAA@AEBV012@@Z; wil::reg::iterator_t<wil::reg::key_iterator_data<std::wstring>>::iterator_t<wil::reg::key_iterator_data<std::wstring>>(wil::reg::iterator_t<wil::reg::key_iterator_data<std::wstring>> const &)
0x180026bb3  nop
0x180026bb4  lea     rdx, [rsp+578h+var_2A0]
0x180026bbc  lea     rcx, [rsp+578h+var_318]
0x180026bc4  call    ??0?$iterator_t@V?$key_iterator_data@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@reg@wil@@@reg@wil@@QEAA@AEBV012@@Z; wil::reg::iterator_t<wil::reg::key_iterator_data<std::wstring>>::iterator_t<wil::reg::key_iterator_data<std::wstring>>(wil::reg::iterator_t<wil::reg::key_iterator_data<std::wstring>> const &)
0x180026bc9  nop
0x180026bca  mov     r15, [rsp+578h+var_2F0]
0x180026bd2  mov     r12, [rsp+578h+var_2F8]
0x180026bda  movdqa  xmm6, cs:__xmm@00000000000000070000000000000000
0x180026be2  mov     eax, [rsp+578h+var_328]
0x180026be9  cmp     eax, ebx
0x180026beb  jz      short loc_180026BFC
0x180026bed  cmp     r15d, ebx
0x180026bf0  jz      short loc_180026BFC
0x180026bf2  cmp     [rsp+578h+var_330], r12
0x180026bfa  jnz     short loc_180026C05
0x180026bfc  cmp     eax, r15d
0x180026bff  jz      loc_1800270F7
0x180026c05  cmp     eax, ebx
0x180026c07  setz    al
0x180026c0a  mov     rcx, [rsp+578h]; this
0x180026c12  test    al, al
0x180026c14  jnz     loc_180027343
0x180026c1a  mov     [rsp+578h+var_4C8], r13
0x180026c22  mov     [rsp+578h+var_4C0], r13b
0x180026c2a  xorps   xmm0, xmm0
0x180026c2d  movdqa  [rsp+578h+var_4B8], xmm0
0x180026c36  xorps   xmm1, xmm1
0x180026c39  movdqa  [rsp+578h+var_4A8], xmm1
0x180026c42  mov     [rsp+578h+var_498], r13
0x180026c4a  mov     [rsp+578h+var_490], r13b
0x180026c52  movdqa  [rsp+578h+var_488], xmm0
0x180026c5b  mov     [rsp+578h+var_478], r13b
0x180026c63  mov     [rsp+578h+var_470], r13
0x180026c6b  mov     [rsp+578h+var_468], r13
0x180026c73  mov     [rsp+578h+var_460], r13b
0x180026c7b  lea     r8, [rsp+578h+var_458]
0x180026c83  lea     rdx, [rsp+578h+var_4C8]
0x180026c8b  lea     rcx, [rsp+578h+lpSubKey]
0x180026c93  call    ??$regex_match@U?$char_traits@_W@std@@V?$allocator@_W@2@V?$allocator@V?$sub_match@V?$_String_const_iterator@V?$_String_val@U?$_Simple_types@_W@std@@@std@@@std@@@std@@@2@_WV?$regex_traits@_W@2@@std@@YA_NAEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@0@AEAV?$match_results@V?$_String_const_iterator@V?$_String_val@U?$_Simple_types@_W@std@@@std@@@std@@V?$allocator@V?$sub_match@V?$_String_const_iterator@V?$_String_val@U?$_Simple_types@_W@std@@@std@@@std@@@std@@@2@@0@AEBV?$basic_regex@_WV?$regex_traits@_W@std@@@0@W4match_flag_type@regex_constants@0@@Z; std::regex_match<std::char_traits<wchar_t>,std::allocator<wchar_t>,std::allocator<std::sub_match<std::_String_const_iterator<std::_String_val<std::_Simple_types<wchar_t>>>>>,wchar_t,std::regex_traits<wchar_t>>(std::wstring const &,std::match_results<std::_String_const_iterator<std::_String_val<std::_Simple_types<wchar_t>>>> &,std::basic_regex<wchar_t,std::regex_traits<wchar_t>> const &,std::regex_constants::match_flag_type)
0x180026c98  test    al, al
0x180026c9a  jz      loc_1800270D8
0x180026ca0  mov     rcx, qword ptr [rsp+578h+var_4B8]
0x180026ca8  mov     rax, qword ptr [rsp+578h+var_4B8+8]
0x180026cb0  sub     rax, rcx
0x180026cb3  cmp     rax, 48h ; 'H'
0x180026cb7  jnz     loc_1800270D8
0x180026cbd  cmp     [rcx+28h], r13b
0x180026cc1  jz      short loc_180026CC9
0x180026cc3  movups  xmm0, xmmword ptr [rcx+18h]
0x180026cc7  jmp     short loc_180026CCC
0x180026cc9  xorps   xmm0, xmm0
0x180026ccc  movdqu  [rsp+578h+var_528], xmm0
0x180026cd2  xorps   xmm0, xmm0
0x180026cd5  movups  xmmword ptr [rsp+578h+S1], xmm0
0x180026cdd  mov     [rsp+578h+var_3B0], r13
0x180026ce5  mov     [rsp+578h+var_3A8], r13
0x180026ced  mov     rdx, qword ptr [rsp+578h+var_528]
0x180026cf2  mov     r8, qword ptr [rsp+578h+var_528+8]
0x180026cf7  cmp     rdx, r8
0x180026cfa  jnz     short loc_180026D1D
0x180026cfc  mov     rdx, r13
0x180026cff  mov     [rsp+578h+var_3B0], rdx
0x180026d07  mov     rcx, rdi
0x180026d0a  mov     [rsp+578h+var_3A8], rcx
0x180026d12  mov     word ptr [rsp+578h+S1], r13w
0x180026d1b  jmp     short loc_180026D40
0x180026d1d  sub     r8, rdx
0x180026d20  sar     r8, 1
0x180026d23  lea     rcx, [rsp+578h+S1]
0x180026d2b  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x180026d30  mov     rcx, [rsp+578h+var_3A8]
0x180026d38  mov     rdx, [rsp+578h+var_3B0]
0x180026d40  lea     rax, [rsp+578h+S1]
0x180026d48  cmp     rcx, rdi
0x180026d4b  cmova   rax, [rsp+578h+S1]
0x180026d54  cmp     rdx, 3
0x180026d58  jnz     short loc_180026D76
0x180026d5a  mov     r8, rdx; N
0x180026d5d  lea     rdx, a110; "110"
0x180026d64  mov     rcx, rax; S1
0x180026d67  call    wmemcmp
0x180026d6c  test    eax, eax
0x180026d6e  jnz     short loc_180026D76
0x180026d70  mov     bl, 1
0x180026d72  inc     esi
0x180026d74  jmp     short loc_180026D79
0x180026d76  mov     bl, r13b
0x180026d79  mov     rcx, qword ptr [rsp+578h+var_4B8]
0x180026d81  mov     rax, qword ptr [rsp+578h+var_4B8+8]
0x180026d89  sub     rax, rcx
0x180026d8c  sar     rax, 3
0x180026d90  mov     rdx, 0AAAAAAAAAAAAAAABh
0x180026d9a  imul    rax, rdx
0x180026d9e  cmp     rax, 2
0x180026da2  ja      short loc_180026DB6
0x180026da4  lea     rax, [rsp+578h+var_470]
0x180026dac  lea     rcx, [rsp+578h+var_460]
0x180026db4  jmp     short loc_180026DBE
0x180026db6  lea     rax, [rcx+30h]
0x180026dba  add     rcx, 40h ; '@'
0x180026dbe  cmp     [rcx], r13b
0x180026dc1  jz      short loc_180026DC8
0x180026dc3  movups  xmm0, xmmword ptr [rax]
0x180026dc6  jmp     short loc_180026DCB
0x180026dc8  xorps   xmm0, xmm0
0x180026dcb  movdqu  [rsp+578h+var_528], xmm0
0x180026dd1  xorps   xmm0, xmm0
0x180026dd4  movups  xmmword ptr [rsp+578h+lpSidString], xmm0
0x180026ddc  xorps   xmm1, xmm1
0x180026ddf  movdqu  [rsp+578h+var_3D0], xmm1
0x180026de8  mov     rdx, qword ptr [rsp+578h+var_528]
0x180026ded  mov     r8, qword ptr [rsp+578h+var_528+8]
0x180026df2  cmp     rdx, r8
0x180026df5  jnz     short loc_180026E0B
0x180026df7  movdqu  [rsp+578h+var_3D0], xmm6
0x180026e00  mov     word ptr [rsp+578h+lpSidString], r13w
0x180026e09  jmp     short loc_180026E1F
0x180026e0b  sub     r8, rdx
0x180026e0e  sar     r8, 1
0x180026e11  lea     rcx, [rsp+578h+lpSidString]
0x180026e19  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x180026e1e  nop
0x180026e1f  mov     [rsp+578h+Src], r13w
0x180026e28  lea     rdx, [rsp+578h+lpSubKey]
0x180026e30  cmp     [rsp+578h+var_338], rdi
0x180026e38  cmova   rdx, [rsp+578h+lpSubKey]; lpSubKey
0x180026e41  mov     [rsp+578h+var_518], 208h
0x180026e49  lea     rax, [rsp+578h+var_518]
0x180026e4e  mov     [rsp+578h+pcbData], rax; pcbData
0x180026e53  lea     rax, [rsp+578h+Src]
0x180026e5b  mov     [rsp+578h+pvData], rax; pvData
0x180026e60  mov     [rsp+578h+phkResult], r13; pdwType
0x180026e65  mov     r9d, 10000006h; dwFlags
0x180026e6b  lea     r8, Value; "ProfileImagePath"
0x180026e72  mov     rcx, [rsp+578h+hKey]; hkey
0x180026e77  call    cs:__imp_RegGetValueW
0x180026e7d  test    eax, eax
0x180026e7f  jle     short loc_180026E8B
0x180026e81  movzx   eax, ax
0x180026e84  or      eax, 80070000h
0x180026e89  test    eax, eax
0x180026e8b  jns     short loc_180026EBA
0x180026e8d  lea     r8, [rsp+578h+lpSubKey]
0x180026e95  cmp     [rsp+578h+var_338], rdi
0x180026e9d  cmova   r8, [rsp+578h+lpSubKey]
0x180026ea6  mov     r9d, eax
0x180026ea9  lea     rdx, aUnexpectedFail; "Unexpected: failed to read ProfileImage"...
0x180026eb0  mov     ecx, 3; unsigned __int8
0x180026eb5  call    ?Log@@YAXEPEB_WZZ; Log(uchar,wchar_t const *,...)
0x180026eba  mov     rax, qword ptr [rsp+578h+var_3D0]
0x180026ec2  lea     rdx, [rsp+578h+lpSidString]
0x180026eca  cmp     qword ptr [rsp+578h+var_3D0+8], rdi
0x180026ed2  cmova   rdx, [rsp+578h+lpSidString]
0x180026edb  mov     r9, 0CBF29CE484222325h
0x180026ee5  lea     r8, [rax+rax]
0x180026ee9  mov     rcx, r13
0x180026eec  test    r8, r8
0x180026eef  jz      short loc_180026F0E
0x180026ef1  movzx   eax, byte ptr [rcx+rdx]
0x180026ef5  xor     r9, rax
0x180026ef8  mov     r10, 100000001B3h
0x180026f02  imul    r9, r10
0x180026f06  inc     rcx
0x180026f09  cmp     rcx, r8
0x180026f0c  jb      short loc_180026EF1
0x180026f0e  lea     r8, [rsp+578h+lpSidString]
0x180026f16  lea     rdx, [rsp+578h+var_430]
0x180026f1e  lea     rcx, [rsp+578h+var_508]
0x180026f23  call    ??$_Find_last@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@?$_Hash@V?$_Umap_traits@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@UProfileData@?2??MopUpMemUserProfiles@@YA_NXZ@V?$_Uhash_compare@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@U?$hash@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@U?$equal_to@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@@2@V?$allocator@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@UProfileData@?2??MopUpMemUserProfiles@@YA_NXZ@@std@@@2@$0A@@std@@@std@@IEBA?AU?$_Hash_find_last_result@PEAU?$_List_node@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@UProfileData@?2??MopUpMemUserProfiles@@YA_NXZ@@std@@PEAX@std@@@1@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@1@_K@Z; std::_Hash<std::_Umap_traits<std::wstring,`MopUpMemUserProfiles(void)'::`3'::ProfileData,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::pair<std::wstring const,`MopUpMemUserProfiles(void)'::`3'::ProfileData>>,0>>::_Find_last<std::wstring>(std::wstring const &,unsigned __int64)
0x180026f28  cmp     [rax+8], r13
0x180026f2c  jz      loc_180026FFB
0x180026f32  lea     r8, [rsp+578h+lpSidString]
0x180026f3a  lea     rcx, [rsp+578h+var_508]
0x180026f3f  test    bl, bl
0x180026f41  jz      loc_180026FE2
0x180026f47  lea     rdx, [rsp+578h+var_420]
0x180026f4f  call    ??$_Try_emplace@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@$$V@?$_Hash@V?$_Umap_traits@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@UProfileData@?2??MopUpMemUserProfiles@@YA_NXZ@V?$_Uhash_compare@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@U?$hash@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@U?$equal_to@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@@2@V?$allocator@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@UProfileData@?2??MopUpMemUserProfiles@@YA_NXZ@@std@@@2@$0A@@std@@@std@@IEAA?AU?$pair@PEAU?$_List_node@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@UProfileData@?2??MopUpMemUserProfiles@@YA_NXZ@@std@@PEAX@std@@_N@1@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@1@@Z; std::_Hash<std::_Umap_traits<std::wstring,`MopUpMemUserProfiles(void)'::`3'::ProfileData,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::pair<std::wstring const,`MopUpMemUserProfiles(void)'::`3'::ProfileData>>,0>>::_Try_emplace<std::wstring const &,>(std::wstring const &)
0x180026f54  mov     rax, [rax]
0x180026f57  mov     byte ptr [rax+30h], 1
0x180026f5b  lea     r8, [rsp+578h+lpSidString]
0x180026f63  lea     rdx, [rsp+578h+var_410]
0x180026f6b  lea     rcx, [rsp+578h+var_508]
0x180026f70  call    ??$_Try_emplace@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@$$V@?$_Hash@V?$_Umap_traits@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@UProfileData@?2??MopUpMemUserProfiles@@YA_NXZ@V?$_Uhash_compare@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@U?$hash@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@U?$equal_to@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@@2@V?$allocator@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@UProfileData@?2??MopUpMemUserProfiles@@YA_NXZ@@std@@@2@$0A@@std@@@std@@IEAA?AU?$pair@PEAU?$_List_node@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@UProfileData@?2??MopUpMemUserProfiles@@YA_NXZ@@std@@PEAX@std@@_N@1@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@1@@Z; std::_Hash<std::_Umap_traits<std::wstring,`MopUpMemUserProfiles(void)'::`3'::ProfileData,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::pair<std::wstring const,`MopUpMemUserProfiles(void)'::`3'::ProfileData>>,0>>::_Try_emplace<std::wstring const &,>(std::wstring const &)
0x180026f75  mov     rcx, [rax]
0x180026f78  add     rcx, 38h ; '8'
0x180026f7c  lea     rax, [rsp+578h+Src]
0x180026f84  or      rdx, 0FFFFFFFFFFFFFFFFh
0x180026f88  inc     rdx
0x180026f8b  cmp     [rax+rdx*2], r13w
0x180026f90  jnz     short loc_180026F88
  ... truncated ...
```
