# Windows::Internal::AI::Agents::Mcp::Implementation::McpConsentStore::GetConsentsForClient(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &)

- ea: `0x1800b71cc`
- end: `0x1800b77b8`
- name: `?GetConsentsForClient@McpConsentStore@Implementation@Mcp@Agents@AI@Internal@Windows@@SA?AV?$vector@UInternalMcpConsentKeyValue@Implementation@Mcp@Agents@AI@Internal@Windows@@V?$allocator@UInternalMcpConsentKeyValue@Implementation@Mcp@Agents@AI@Internal@Windows@@@std@@@std@@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@9@0@Z`
- size: `1516`
- prototype: ``
- caller_count: `1`
- callee_count: `23`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x180098eb0`

## callees

- `0x1800094c0`
- `0x180016450`
- `0x18001c3b4`
- `0x18002392c`
- `0x1800257a4`
- `0x180029408`
- `0x18002a564`
- `0x18002f280`
- `0x18003afa0`
- `0x18003b54c`
- `0x18003ce34`
- `0x18005829c`
- `0x180058ac4`
- `0x180058dfc`
- `0x18009862c`
- `0x1800986d0`
- `0x18009f524`
- `0x1800b6670`
- `0x1800b6898`
- `0x1800b6b18`
- `0x1800b6b5c`
- `0x1800b71cc`
- `0x1800b7d6c`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800b742d`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800b74d9`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800b742d`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800b74d9`

## pseudocode

```c
// Hidden C++ exception states: #wind=21
_QWORD *__fastcall Windows::Internal::AI::Agents::Mcp::Implementation::McpConsentStore::GetConsentsForClient(
        _QWORD *a1,
        __int64 a2,
        __int64 a3)
{
  int SettingsForClient; // eax
  HKEY v7; // rbx
  HKEY v8; // rsi
  HKEY v9; // r14
  HKEY v10; // r15
  HKEY v11; // r12
  __int64 v12; // rdx
  __m128i si128; // xmm6
  const WCHAR *v14; // rax
  __int64 v15; // rbx
  __int64 v16; // r14
  __int64 v17; // rax
  __int64 v18; // r8
  const WCHAR *v19; // rax
  unsigned int Uint32Value; // esi
  __int64 v21; // rsi
  __int64 v22; // r12
  __int64 v23; // rax
  HKEY v24; // r13
  HKEY v25; // r14
  __int64 v26; // rax
  __int64 v27; // r8
  HKEY v28; // rax
  int phkResult; // [rsp+28h] [rbp-E0h]
  bool *phkResulta; // [rsp+28h] [rbp-E0h]
  bool *phkResultb; // [rsp+28h] [rbp-E0h]
  unsigned __int16 v33[4]; // [rsp+38h] [rbp-D0h] BYREF
  HKEY v34; // [rsp+40h] [rbp-C8h] BYREF
  __int64 v35; // [rsp+48h] [rbp-C0h]
  HKEY v36; // [rsp+50h] [rbp-B8h] BYREF
  HKEY hKey; // [rsp+58h] [rbp-B0h] BYREF
  HKEY hKey_8[2]; // [rsp+60h] [rbp-A8h] BYREF
  __int64 v39; // [rsp+70h] [rbp-98h]
  __int64 v40; // [rsp+78h] [rbp-90h]
  __int64 v41; // [rsp+80h] [rbp-88h]
  __int64 v42; // [rsp+88h] [rbp-80h]
  __int64 v43; // [rsp+90h] [rbp-78h] BYREF
  __int64 v44; // [rsp+98h] [rbp-70h]
  __int64 v45; // [rsp+A8h] [rbp-60h] BYREF
  __int64 v46; // [rsp+B0h] [rbp-58h]
  _QWORD *v47; // [rsp+C0h] [rbp-48h]
  _OWORD v48[2]; // [rsp+C8h] [rbp-40h] BYREF
  _OWORD v49[2]; // [rsp+E8h] [rbp-20h] BYREF
  _OWORD v50[2]; // [rsp+108h] [rbp+0h] BYREF
  __int128 v51; // [rsp+128h] [rbp+20h] BYREF
  __m128i v52; // [rsp+138h] [rbp+30h]
  __int128 v53; // [rsp+148h] [rbp+40h] BYREF
  __m128i v54; // [rsp+158h] [rbp+50h]
  int v55; // [rsp+168h] [rbp+60h]
  int v56; // [rsp+16Ch] [rbp+64h]
  _BYTE v57[32]; // [rsp+178h] [rbp+70h] BYREF
  _BYTE v58[128]; // [rsp+198h] [rbp+90h] BYREF
  unsigned int v59; // [rsp+218h] [rbp+110h]
  int v60; // [rsp+21Ch] [rbp+114h]
  wil::details::in1diag3 *retaddr; // [rsp+280h] [rbp+178h]

  v47 = a1;
  LODWORD(v35) = 1;
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_ID59213523>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_ID59213523>::GetImpl'::`2'::impl) )
  {
    *(_OWORD *)hKey_8 = 0;
    v39 = 0;
    *a1 = 0;
    a1[1] = 0;
    a1[2] = 0;
    LODWORD(v35) = 1;
    SettingsForClient = Windows::Internal::CapabilityAccess::Extensions::Storage::APIWrappers::MCP::GetSettingsForClient(
                          a2,
                          a3,
                          hKey_8);
    if ( SettingsForClient < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x1A8,
        (unsigned int)"onecore\\base\\devices\\cam\\core\\mcpconsentstore.cpp",
        (const char *)(unsigned int)SettingsForClient,
        phkResult);
    v8 = hKey_8[1];
    v7 = hKey_8[0];
    if ( hKey_8[0] != hKey_8[1] )
    {
      v9 = hKey_8[0] + 8;
      v10 = hKey_8[0] + 16;
      v11 = hKey_8[0] + 24;
      do
      {
        v49[0] = *(_OWORD *)v7;
        v49[1] = *((_OWORD *)v7 + 1);
        *((_QWORD *)v7 + 2) = 0;
        *((_QWORD *)v7 + 3) = 7;
        *(_WORD *)v7 = 0;
        v50[0] = *(_OWORD *)v9;
        v50[1] = *((_OWORD *)v9 + 1);
        *((_QWORD *)v9 + 2) = 0;
        *((_QWORD *)v9 + 3) = 7;
        *(_WORD *)v9 = 0;
        v51 = *(_OWORD *)v10;
        v52 = *((__m128i *)v10 + 1);
        *((_QWORD *)v10 + 2) = 0;
        *((_QWORD *)v10 + 3) = 7;
        *(_WORD *)v10 = 0;
        v53 = *(_OWORD *)v11;
        v54 = *((__m128i *)v11 + 1);
        *((_QWORD *)v11 + 2) = 0;
        *((_QWORD *)v11 + 3) = 7;
        *(_WORD *)v11 = 0;
        v55 = *((_DWORD *)v7 + 32);
        v56 = 0;
        v12 = a1[1];
        if ( v12 == a1[2] )
          std::vector<Windows::Internal::AI::Agents::Mcp::Implementation::InternalMcpConsentKeyValue>::_Emplace_reallocate<Windows::Internal::AI::Agents::Mcp::Implementation::InternalMcpConsentKeyValue>(
            a1,
            v12,
            v49);
        else
          std::vector<Windows::Internal::AI::Agents::Mcp::Implementation::InternalMcpConsentKeyValue>::_Emplace_back_with_unused_capacity<Windows::Internal::AI::Agents::Mcp::Implementation::InternalMcpConsentKeyValue>(
            a1,
            v49);
        Windows::Internal::AI::Agents::Mcp::Implementation::InternalMcpConsentKey::~InternalMcpConsentKey((Windows::Internal::AI::Agents::Mcp::Implementation::InternalMcpConsentKey *)v49);
        v7 += 34;
        v9 += 34;
        v10 += 34;
        v11 += 34;
      }
      while ( v7 != v8 );
      v7 = hKey_8[0];
    }
    if ( v7 )
    {
      std::_Destroy_range<std::allocator<Windows::Internal::CapabilityAccess::Extensions::Storage::APIWrappers::MCP::McpConsent>>((Windows::Internal::AI::Agents::Mcp::Implementation::InternalMcpConsentKey *)v7);
      std::_Deallocate<16>(hKey_8[0], 8 * ((signed __int64)(v39 - (unsigned __int64)hKey_8[0]) >> 3));
    }
  }
  else
  {
    hKey = 0;
    *a1 = 0;
    a1[1] = 0;
    a1[2] = 0;
    LODWORD(v35) = 3;
    v48[0] = 0;
    si128 = _mm_load_si128((const __m128i *)&_xmm);
    v48[1] = si128;
    LOWORD(v48[0]) = 0;
    Windows::Internal::AI::Agents::Mcp::Implementation::McpConsentStore::OpenTemporaryRegistryStoreWithOffset(&hKey);
    std::wstring::_Tidy_deallocate(v48);
    v36 = 0;
    wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(
      &v36,
      0);
    v14 = (const WCHAR *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(a2);
    if ( RegOpenKeyExW(hKey, v14, 0, 0xF013Fu, &v36) != 2 )
    {
      Windows::Internal::CapabilityAccess::Private::RegGetKeyArray(&v45, v36, 0);
      v15 = v45;
      v16 = v46;
      v42 = v46;
      while ( v15 != v16 )
      {
        v34 = 0;
        std::wstring::wstring(v48, a2);
        std::wstring::_Append<unsigned short>(v48, L"\\");
        v17 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v15);
        v18 = -1;
        do
          ++v18;
        while ( *(_WORD *)(v17 + 2 * v18) );
        std::wstring::_Append<unsigned short>(v48, v17);
        wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(
          &v34,
          0);
        v19 = (const WCHAR *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v48);
        if ( RegOpenKeyExW(hKey, v19, 0, 0xF013Fu, &v34) != 2 )
        {
          LOBYTE(v33[0]) = 0;
          Uint32Value = Windows::Internal::CapabilityAccess::Private::RegGetUint32Value(
                          (Windows::Internal::CapabilityAccess::Private *)v34,
                          0,
                          L"Value",
                          v33,
                          phkResulta);
          if ( LOBYTE(v33[0]) )
          {
            std::wstring::wstring(v49, a2);
            std::wstring::wstring(v50, v15);
            v51 = 0;
            v52 = si128;
            LOWORD(v51) = 0;
            v53 = 0;
            v54 = si128;
            LOWORD(v53) = 0;
            Windows::Internal::AI::Agents::Mcp::Implementation::InternalMcpConsentKey::InternalMcpConsentKey(
              (Windows::Internal::AI::Agents::Mcp::Implementation::InternalMcpConsentKey *)v58,
              (const struct Windows::Internal::AI::Agents::Mcp::Implementation::InternalMcpConsentKey *)v49);
            v59 = Uint32Value;
            v60 = 0;
            std::vector<Windows::Internal::AI::Agents::Mcp::Implementation::InternalMcpConsentKeyValue>::emplace_back<Windows::Internal::AI::Agents::Mcp::Implementation::InternalMcpConsentKeyValue &>(
              a1,
              v58);
            Windows::Internal::AI::Agents::Mcp::Implementation::InternalMcpConsentKey::~InternalMcpConsentKey((Windows::Internal::AI::Agents::Mcp::Implementation::InternalMcpConsentKey *)v58);
            Windows::Internal::AI::Agents::Mcp::Implementation::InternalMcpConsentKey::~InternalMcpConsentKey((Windows::Internal::AI::Agents::Mcp::Implementation::InternalMcpConsentKey *)v49);
          }
          if ( (unsigned int)std::wstring::compare(v15, L"*") )
          {
            Windows::Internal::CapabilityAccess::Private::RegGetKeyArray(&v43, v34, 0);
            v21 = v43;
            v22 = v44;
            v41 = v44;
            if ( v43 != v44 )
            {
              do
              {
                v23 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v21);
                Windows::Internal::CapabilityAccess::Private::RegGetKeyArray(hKey_8, v34, v23);
                v24 = hKey_8[1];
                v25 = hKey_8[0];
                if ( hKey_8[0] != hKey_8[1] )
                {
                  do
                  {
                    std::wstring::wstring(v57, v21);
                    std::wstring::_Append<unsigned short>(v57, L"\\");
                    v26 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v25);
                    v27 = -1;
                    do
                      ++v27;
                    while ( *(_WORD *)(v26 + 2 * v27) );
                    std::wstring::_Append<unsigned short>(v57, v26);
                    LOBYTE(v33[0]) = 0;
                    v28 = (HKEY)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v57);
                    LODWORD(v40) = Windows::Internal::CapabilityAccess::Private::RegGetUint32Value(
                                     (Windows::Internal::CapabilityAccess::Private *)v34,
                                     v28,
                                     L"Value",
                                     v33,
                                     phkResultb);
                    if ( LOBYTE(v33[0]) )
                    {
                      std::wstring::wstring(v49, a2);
                      std::wstring::wstring(v50, v15);
                      std::wstring::wstring(&v51, v21);
                      std::wstring::wstring(&v53, v25);
                      Windows::Internal::AI::Agents::Mcp::Implementation::InternalMcpConsentKey::InternalMcpConsentKey(
                        (Windows::Internal::AI::Agents::Mcp::Implementation::InternalMcpConsentKey *)v58,
                        (const struct Windows::Internal::AI::Agents::Mcp::Implementation::InternalMcpConsentKey *)v49);
                      v59 = v40;
                      v60 = 0;
                      std::vector<Windows::Internal::AI::Agents::Mcp::Implementation::InternalMcpConsentKeyValue>::emplace_back<Windows::Internal::AI::Agents::Mcp::Implementation::InternalMcpConsentKeyValue &>(
                        a1,
                        v58);
                      Windows::Internal::AI::Agents::Mcp::Implementation::InternalMcpConsentKey::~InternalMcpConsentKey((Windows::Internal::AI::Agents::Mcp::Implementation::InternalMcpConsentKey *)v58);
                      Windows::Internal::AI::Agents::Mcp::Implementation::InternalMcpConsentKey::~InternalMcpConsentKey((Windows::Internal::AI::Agents::Mcp::Implementation::InternalMcpConsentKey *)v49);
                    }
                    std::wstring::_Tidy_deallocate(v57);
                    v25 += 8;
                  }
                  while ( v25 != v24 );
                  v22 = v41;
                }
                std::vector<std::wstring>::_Tidy(hKey_8);
                v21 += 32;
              }
              while ( v21 != v22 );
              v16 = v42;
            }
            std::vector<std::wstring>::_Tidy(&v43);
          }
        }
        std::wstring::_Tidy_deallocate(v48);
        wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&v34);
        v15 += 32;
      }
      std::vector<std::wstring>::_Tidy(&v45);
    }
    wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&v36);
    wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
  }
  return a1;
}

```

## disassembly

```asm
0x1800b71cc  mov     rax, rsp
0x1800b71cf  mov     [rax+20h], rbx
0x1800b71d3  push    rbp
0x1800b71d4  push    rsi
0x1800b71d5  push    rdi
0x1800b71d6  push    r12
0x1800b71d8  push    r13
0x1800b71da  push    r14
0x1800b71dc  push    r15
0x1800b71de  lea     rbp, [rax-178h]
0x1800b71e5  sub     rsp, 240h
0x1800b71ec  movaps  xmmword ptr [rax-48h], xmm6
0x1800b71f0  mov     rax, cs:__security_cookie
0x1800b71f7  xor     rax, rsp
0x1800b71fa  mov     [rbp+170h+var_50], rax
0x1800b7201  mov     rbx, r8
0x1800b7204  mov     r15, rdx
0x1800b7207  mov     rdi, rcx
0x1800b720a  mov     [rbp+170h+var_1B8], rcx
0x1800b720e  mov     dword ptr [rsp+270h+var_230], 1
0x1800b7216  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_ID59213523@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_ID59213523@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ID59213523> `wil::Feature<__WilFeatureTraits_Feature_ID59213523>::GetImpl(void)'::`2'::impl
0x1800b721d  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_ID59213523@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ID59213523>::__private_IsEnabled(void)
0x1800b7222  xor     r13d, r13d
0x1800b7225  test    al, al
0x1800b7227  jz      loc_1800B73AD
0x1800b722d  xorps   xmm0, xmm0
0x1800b7230  movdqu  xmmword ptr [rsp+270h+hKey+8], xmm0
0x1800b7236  mov     [rsp+270h+var_208], r13
0x1800b723b  mov     [rdi], r13
0x1800b723e  mov     [rdi+8], r13
0x1800b7242  mov     [rdi+10h], r13
0x1800b7246  mov     dword ptr [rsp+270h+var_230], 1
0x1800b724e  lea     r8, [rsp+270h+hKey+8]
0x1800b7253  mov     rdx, rbx
0x1800b7256  mov     rcx, r15
0x1800b7259  call    ?GetSettingsForClient@MCP@APIWrappers@Storage@Extensions@CapabilityAccess@Internal@Windows@@YAJAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@0AEAV?$vector@UMcpConsent@MCP@APIWrappers@Storage@Extensions@CapabilityAccess@Internal@Windows@@V?$allocator@UMcpConsent@MCP@APIWrappers@Storage@Extensions@CapabilityAccess@Internal@Windows@@@std@@@9@@Z; Windows::Internal::CapabilityAccess::Extensions::Storage::APIWrappers::MCP::GetSettingsForClient(std::wstring const &,std::wstring const &,std::vector<Windows::Internal::CapabilityAccess::Extensions::Storage::APIWrappers::MCP::McpConsent> &)
0x1800b725e  mov     rcx, [rbp+178h]; this
0x1800b7265  test    eax, eax
0x1800b7267  js      loc_1800B77A3
0x1800b726d  mov     rbx, [rsp+270h+hKey+8]
0x1800b7272  mov     rsi, [rsp+270h+var_210]
0x1800b7277  cmp     rbx, rsi
0x1800b727a  jz      loc_1800B7369
0x1800b7280  lea     r14, [rbx+20h]
0x1800b7284  lea     r15, [rbx+40h]
0x1800b7288  lea     r12, [rbx+60h]
0x1800b728c  lea     ecx, [r13+7]
0x1800b7290  movups  xmm1, xmmword ptr [rbx]
0x1800b7293  movaps  [rbp+170h+var_190], xmm1
0x1800b7297  movups  xmm0, xmmword ptr [rbx+10h]
0x1800b729b  movaps  [rbp+170h+var_180], xmm0
0x1800b729f  mov     [rbx+10h], r13
0x1800b72a3  mov     [rbx+18h], rcx
0x1800b72a7  mov     [rbx], r13w
0x1800b72ab  movups  xmm1, xmmword ptr [r14]
0x1800b72af  movaps  [rbp+170h+var_170], xmm1
0x1800b72b3  movups  xmm0, xmmword ptr [r14+10h]
0x1800b72b8  movaps  [rbp+170h+var_160], xmm0
0x1800b72bc  mov     [r14+10h], r13
0x1800b72c0  mov     [r14+18h], rcx
0x1800b72c4  mov     [r14], r13w
0x1800b72c8  movups  xmm1, xmmword ptr [r15]
0x1800b72cc  movaps  [rbp+170h+var_150], xmm1
0x1800b72d0  movups  xmm0, xmmword ptr [r15+10h]
0x1800b72d5  movaps  [rbp+170h+var_140], xmm0
0x1800b72d9  mov     [r15+10h], r13
0x1800b72dd  mov     [r15+18h], rcx
0x1800b72e1  mov     [r15], r13w
0x1800b72e5  movups  xmm1, xmmword ptr [r12]
0x1800b72ea  movaps  [rbp+170h+var_130], xmm1
0x1800b72ee  movups  xmm0, xmmword ptr [r12+10h]
0x1800b72f4  movaps  [rbp+170h+var_120], xmm0
0x1800b72f8  mov     [r12+10h], r13
0x1800b72fd  mov     [r12+18h], rcx
0x1800b7302  mov     [r12], r13w
0x1800b7307  mov     eax, [rbx+80h]
0x1800b730d  mov     [rbp+170h+var_110], eax
0x1800b7310  xor     eax, eax
0x1800b7312  mov     [rbp+170h+var_10C], eax
0x1800b7315  mov     rdx, [rdi+8]
0x1800b7319  mov     rcx, rdi
0x1800b731c  cmp     rdx, [rdi+10h]
0x1800b7320  jz      short loc_1800B732D
0x1800b7322  lea     rdx, [rbp+170h+var_190]
0x1800b7326  call    ??$_Emplace_back_with_unused_capacity@UInternalMcpConsentKeyValue@Implementation@Mcp@Agents@AI@Internal@Windows@@@?$vector@UInternalMcpConsentKeyValue@Implementation@Mcp@Agents@AI@Internal@Windows@@V?$allocator@UInternalMcpConsentKeyValue@Implementation@Mcp@Agents@AI@Internal@Windows@@@std@@@std@@AEAAAEAUInternalMcpConsentKeyValue@Implementation@Mcp@Agents@AI@Internal@Windows@@$$QEAU2345678@@Z; std::vector<Windows::Internal::AI::Agents::Mcp::Implementation::InternalMcpConsentKeyValue>::_Emplace_back_with_unused_capacity<Windows::Internal::AI::Agents::Mcp::Implementation::InternalMcpConsentKeyValue>(Windows::Internal::AI::Agents::Mcp::Implementation::InternalMcpConsentKeyValue &&)
0x1800b732b  jmp     short loc_1800B7337
0x1800b732d  lea     r8, [rbp+170h+var_190]
0x1800b7331  call    ??$_Emplace_reallocate@UInternalMcpConsentKeyValue@Implementation@Mcp@Agents@AI@Internal@Windows@@@?$vector@UInternalMcpConsentKeyValue@Implementation@Mcp@Agents@AI@Internal@Windows@@V?$allocator@UInternalMcpConsentKeyValue@Implementation@Mcp@Agents@AI@Internal@Windows@@@std@@@std@@AEAAPEAUInternalMcpConsentKeyValue@Implementation@Mcp@Agents@AI@Internal@Windows@@QEAU2345678@$$QEAU2345678@@Z; std::vector<Windows::Internal::AI::Agents::Mcp::Implementation::InternalMcpConsentKeyValue>::_Emplace_reallocate<Windows::Internal::AI::Agents::Mcp::Implementation::InternalMcpConsentKeyValue>(Windows::Internal::AI::Agents::Mcp::Implementation::InternalMcpConsentKeyValue * const,Windows::Internal::AI::Agents::Mcp::Implementation::InternalMcpConsentKeyValue &&)
0x1800b7336  nop
0x1800b7337  lea     rcx, [rbp+170h+var_190]; this
0x1800b733b  call    ??1InternalMcpConsentKey@Implementation@Mcp@Agents@AI@Internal@Windows@@QEAA@XZ; Windows::Internal::AI::Agents::Mcp::Implementation::InternalMcpConsentKey::~InternalMcpConsentKey(void)
0x1800b7340  mov     ecx, 88h
0x1800b7345  add     rbx, rcx
0x1800b7348  add     r14, rcx
0x1800b734b  add     r15, rcx
0x1800b734e  add     r12, rcx
0x1800b7351  cmp     rbx, rsi
0x1800b7354  mov     ecx, 7
0x1800b7359  jnz     loc_1800B7290
0x1800b735f  mov     rsi, [rsp+270h+var_210]
0x1800b7364  mov     rbx, [rsp+270h+hKey+8]
0x1800b7369  test    rbx, rbx
0x1800b736c  jz      loc_1800B7771
0x1800b7372  mov     rdx, rsi
0x1800b7375  mov     rcx, rbx; this
0x1800b7378  call    ??$_Destroy_range@V?$allocator@UMcpConsent@MCP@APIWrappers@Storage@Extensions@CapabilityAccess@Internal@Windows@@@std@@@std@@YAXPEAUMcpConsent@MCP@APIWrappers@Storage@Extensions@CapabilityAccess@Internal@Windows@@QEAU12345678@AEAV?$allocator@UMcpConsent@MCP@APIWrappers@Storage@Extensions@CapabilityAccess@Internal@Windows@@@0@@Z; std::_Destroy_range<std::allocator<Windows::Internal::CapabilityAccess::Extensions::Storage::APIWrappers::MCP::McpConsent>>(Windows::Internal::CapabilityAccess::Extensions::Storage::APIWrappers::MCP::McpConsent *,Windows::Internal::CapabilityAccess::Extensions::Storage::APIWrappers::MCP::McpConsent * const,std::allocator<Windows::Internal::CapabilityAccess::Extensions::Storage::APIWrappers::MCP::McpConsent> &)
0x1800b737d  mov     rcx, [rsp+270h+hKey+8]
0x1800b7382  mov     rdx, [rsp+270h+var_208]
0x1800b7387  sub     rdx, rcx
0x1800b738a  sar     rdx, 3
0x1800b738e  mov     rax, 0F0F0F0F0F0F0F0F1h
0x1800b7398  imul    rdx, rax
0x1800b739c  imul    rdx, 88h
0x1800b73a3  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x1800b73a8  jmp     loc_1800B7771
0x1800b73ad  mov     [rsp+270h+hKey], r13
0x1800b73b2  mov     [rdi], r13
0x1800b73b5  mov     [rdi+8], r13
0x1800b73b9  mov     [rdi+10h], r13
0x1800b73bd  mov     dword ptr [rsp+270h+var_230], 3
0x1800b73c5  xorps   xmm0, xmm0
0x1800b73c8  movups  [rbp+170h+var_1B0], xmm0
0x1800b73cc  movdqa  xmm6, cs:__xmm@00000000000000070000000000000000
0x1800b73d4  movdqu  [rbp+170h+var_1A0], xmm6
0x1800b73d9  mov     word ptr [rbp+170h+var_1B0], r13w
0x1800b73de  mov     r9, rbx
0x1800b73e1  lea     r8, [rbp+170h+var_1B0]
0x1800b73e5  lea     rcx, [rsp+270h+hKey]; phkResult
0x1800b73ea  call    ?OpenTemporaryRegistryStoreWithOffset@McpConsentStore@Implementation@Mcp@Agents@AI@Internal@Windows@@CAXAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@KAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@1@Z; Windows::Internal::AI::Agents::Mcp::Implementation::McpConsentStore::OpenTemporaryRegistryStoreWithOffset(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>> &,ulong,std::wstring const &,std::wstring const &)
0x1800b73ef  nop
0x1800b73f0  lea     rcx, [rbp+170h+var_1B0]
0x1800b73f4  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800b73f9  mov     [rsp+270h+var_228], r13
0x1800b73fe  xor     edx, edx
0x1800b7400  lea     rcx, [rsp+270h+var_228]
0x1800b7405  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHKEY__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(HKEY__ *)
0x1800b740a  mov     rcx, r15
0x1800b740d  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x1800b7412  lea     rcx, [rsp+270h+var_228]
0x1800b7417  mov     [rsp+270h+phkResult], rcx; phkResult
0x1800b741c  mov     r9d, 0F013Fh; samDesired
0x1800b7422  xor     r8d, r8d; ulOptions
0x1800b7425  mov     rdx, rax; lpSubKey
0x1800b7428  mov     rcx, [rsp+270h+hKey]; hKey
0x1800b742d  call    cs:__imp_RegOpenKeyExW
0x1800b7433  cmp     eax, 2
0x1800b7436  jz      loc_1800B775C
0x1800b743c  xor     r8d, r8d
0x1800b743f  mov     rdx, [rsp+270h+var_228]
0x1800b7444  lea     rcx, [rbp+170h+var_1D0]
0x1800b7448  call    ?RegGetKeyArray@Private@CapabilityAccess@Internal@Windows@@YA?AV?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@PEAUHKEY__@@PEBG@Z; Windows::Internal::CapabilityAccess::Private::RegGetKeyArray(HKEY__ *,ushort const *)
0x1800b744d  nop
0x1800b744e  mov     rbx, [rbp+170h+var_1D0]
0x1800b7452  mov     r14, [rbp+170h+var_1C8]
0x1800b7456  mov     [rbp+170h+var_1F0], r14
0x1800b745a  jmp     loc_1800B7749
0x1800b745f  mov     [rsp+270h+var_238], r13
0x1800b7464  mov     rdx, r15
0x1800b7467  lea     rcx, [rbp+170h+var_1B0]
0x1800b746b  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x1800b7470  nop
0x1800b7471  mov     r8d, 1
0x1800b7477  lea     rdx, asc_1800D35BC; "\\"
0x1800b747e  lea     rcx, [rbp+170h+var_1B0]
0x1800b7482  call    ??$_Append@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Append<ushort>(ushort const * const,unsigned __int64)
0x1800b7487  mov     rcx, rbx
0x1800b748a  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x1800b748f  or      r8, 0FFFFFFFFFFFFFFFFh
0x1800b7493  inc     r8
0x1800b7496  cmp     [rax+r8*2], r13w
0x1800b749b  jnz     short loc_1800B7493
0x1800b749d  mov     rdx, rax
0x1800b74a0  lea     rcx, [rbp+170h+var_1B0]
0x1800b74a4  call    ??$_Append@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Append<ushort>(ushort const * const,unsigned __int64)
0x1800b74a9  xor     edx, edx
0x1800b74ab  lea     rcx, [rsp+270h+var_238]
0x1800b74b0  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHKEY__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(HKEY__ *)
0x1800b74b5  lea     rcx, [rbp+170h+var_1B0]
0x1800b74b9  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x1800b74be  mov     rdx, rax; lpSubKey
0x1800b74c1  lea     rax, [rsp+270h+var_238]
0x1800b74c6  mov     [rsp+270h+phkResult], rax; bool *
0x1800b74cb  mov     r9d, 0F013Fh; samDesired
0x1800b74d1  xor     r8d, r8d; ulOptions
0x1800b74d4  mov     rcx, [rsp+270h+hKey]; hKey
0x1800b74d9  call    cs:__imp_RegOpenKeyExW
0x1800b74df  cmp     eax, 2
0x1800b74e2  jz      loc_1800B7731
0x1800b74e8  mov     byte ptr [rsp+270h+var_240], r13b
0x1800b74ed  lea     r9, [rsp+270h+var_240]; unsigned __int16 *
0x1800b74f2  lea     r8, ValueName; "Value"
0x1800b74f9  xor     edx, edx; HKEY
0x1800b74fb  mov     rcx, [rsp+270h+var_238]; this
0x1800b7500  call    ?RegGetUint32Value@Private@CapabilityAccess@Internal@Windows@@YAIPEAUHKEY__@@PEBG1PEA_N@Z; Windows::Internal::CapabilityAccess::Private::RegGetUint32Value(HKEY__ *,ushort const *,ushort const *,bool *)
0x1800b7505  mov     esi, eax
0x1800b7507  cmp     byte ptr [rsp+270h+var_240], r13b
0x1800b750c  jz      short loc_1800B758A
0x1800b750e  mov     rdx, r15
0x1800b7511  lea     rcx, [rbp+170h+var_190]
0x1800b7515  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x1800b751a  nop
0x1800b751b  mov     rdx, rbx
0x1800b751e  lea     rcx, [rbp+170h+var_170]
0x1800b7522  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x1800b7527  xorps   xmm0, xmm0
0x1800b752a  movups  [rbp+170h+var_150], xmm0
0x1800b752e  movdqa  [rbp+170h+var_140], xmm6
0x1800b7533  mov     word ptr [rbp+170h+var_150], r13w
0x1800b7538  movups  [rbp+170h+var_130], xmm0
0x1800b753c  movdqa  [rbp+170h+var_120], xmm6
0x1800b7541  mov     word ptr [rbp+170h+var_130], r13w
0x1800b7546  lea     rdx, [rbp+170h+var_190]; struct Windows::Internal::AI::Agents::Mcp::Implementation::InternalMcpConsentKey *
0x1800b754a  lea     rcx, [rbp+170h+var_E0]; this
0x1800b7551  call    ??0InternalMcpConsentKey@Implementation@Mcp@Agents@AI@Internal@Windows@@QEAA@AEBU0123456@@Z; Windows::Internal::AI::Agents::Mcp::Implementation::InternalMcpConsentKey::InternalMcpConsentKey(Windows::Internal::AI::Agents::Mcp::Implementation::InternalMcpConsentKey const &)
0x1800b7556  mov     [rbp+170h+var_60], esi
0x1800b755c  xor     eax, eax
0x1800b755e  mov     [rbp+170h+var_5C], eax
0x1800b7564  lea     rdx, [rbp+170h+var_E0]
0x1800b756b  mov     rcx, rdi
0x1800b756e  call    ??$emplace_back@AEAUInternalMcpConsentKeyValue@Implementation@Mcp@Agents@AI@Internal@Windows@@@?$vector@UInternalMcpConsentKeyValue@Implementation@Mcp@Agents@AI@Internal@Windows@@V?$allocator@UInternalMcpConsentKeyValue@Implementation@Mcp@Agents@AI@Internal@Windows@@@std@@@std@@QEAAAEAUInternalMcpConsentKeyValue@Implementation@Mcp@Agents@AI@Internal@Windows@@AEAU2345678@@Z; std::vector<Windows::Internal::AI::Agents::Mcp::Implementation::InternalMcpConsentKeyValue>::emplace_back<Windows::Internal::AI::Agents::Mcp::Implementation::InternalMcpConsentKeyValue &>(Windows::Internal::AI::Agents::Mcp::Implementation::InternalMcpConsentKeyValue &)
0x1800b7573  nop
0x1800b7574  lea     rcx, [rbp+170h+var_E0]; this
0x1800b757b  call    ??1InternalMcpConsentKey@Implementation@Mcp@Agents@AI@Internal@Windows@@QEAA@XZ; Windows::Internal::AI::Agents::Mcp::Implementation::InternalMcpConsentKey::~InternalMcpConsentKey(void)
0x1800b7580  nop
0x1800b7581  lea     rcx, [rbp+170h+var_190]; this
0x1800b7585  call    ??1InternalMcpConsentKey@Implementation@Mcp@Agents@AI@Internal@Windows@@QEAA@XZ; Windows::Internal::AI::Agents::Mcp::Implementation::InternalMcpConsentKey::~InternalMcpConsentKey(void)
0x1800b758a  lea     rdx, String2; "*"
0x1800b7591  mov     rcx, rbx
0x1800b7594  call    ?compare@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEBAHQEBG@Z; std::wstring::compare(ushort const * const)
0x1800b7599  test    eax, eax
0x1800b759b  jz      loc_1800B7731
0x1800b75a1  xor     r8d, r8d
0x1800b75a4  mov     rdx, [rsp+270h+var_238]
0x1800b75a9  lea     rcx, [rbp+170h+var_1E8]
0x1800b75ad  call    ?RegGetKeyArray@Private@CapabilityAccess@Internal@Windows@@YA?AV?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@PEAUHKEY__@@PEBG@Z; Windows::Internal::CapabilityAccess::Private::RegGetKeyArray(HKEY__ *,ushort const *)
0x1800b75b2  nop
0x1800b75b3  mov     rsi, [rbp+170h+var_1E8]
0x1800b75b7  mov     r12, [rbp+170h+var_1E0]
0x1800b75bb  mov     [rsp+270h+var_1F8], r12
0x1800b75c0  cmp     rsi, r12
0x1800b75c3  jz      loc_1800B7727
0x1800b75c9  mov     rcx, rsi
0x1800b75cc  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x1800b75d1  mov     r8, rax
0x1800b75d4  mov     rdx, [rsp+270h+var_238]
0x1800b75d9  lea     rcx, [rsp+270h+hKey+8]
0x1800b75de  call    ?RegGetKeyArray@Private@CapabilityAccess@Internal@Windows@@YA?AV?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@PEAUHKEY__@@PEBG@Z; Windows::Internal::CapabilityAccess::Private::RegGetKeyArray(HKEY__ *,ushort const *)
0x1800b75e3  nop
0x1800b75e4  mov     r14, [rsp+270h+hKey+8]
0x1800b75e9  mov     r13, [rsp+270h+var_210]
0x1800b75ee  cmp     r14, r13
0x1800b75f1  jz      loc_1800B7709
0x1800b75f7  xor     r12d, r12d
0x1800b75fa  mov     rdx, rsi
0x1800b75fd  lea     rcx, [rbp+170h+var_100]
0x1800b7601  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x1800b7606  nop
0x1800b7607  mov     r8d, 1
0x1800b760d  lea     rdx, asc_1800D35BC; "\\"
0x1800b7614  lea     rcx, [rbp+170h+var_100]
0x1800b7618  call    ??$_Append@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Append<ushort>(ushort const * const,unsigned __int64)
0x1800b761d  mov     rcx, r14
0x1800b7620  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x1800b7625  or      r8, 0FFFFFFFFFFFFFFFFh
0x1800b7629  inc     r8
0x1800b762c  cmp     [rax+r8*2], r12w
0x1800b7631  jnz     short loc_1800B7629
0x1800b7633  mov     rdx, rax
0x1800b7636  lea     rcx, [rbp+170h+var_100]
0x1800b763a  call    ??$_Append@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Append<ushort>(ushort const * const,unsigned __int64)
0x1800b763f  mov     byte ptr [rsp+270h+var_240], r12b
0x1800b7644  lea     rcx, [rbp+170h+var_100]
0x1800b7648  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x1800b764d  mov     rdx, rax; HKEY
0x1800b7650  lea     r9, [rsp+270h+var_240]; unsigned __int16 *
0x1800b7655  lea     r8, ValueName; "Value"
0x1800b765c  mov     rcx, [rsp+270h+var_238]; this
0x1800b7661  call    ?RegGetUint32Value@Private@CapabilityAccess@Internal@Windows@@YAIPEAUHKEY__@@PEBG1PEA_N@Z; Windows::Internal::CapabilityAccess::Private::RegGetUint32Value(HKEY__ *,ushort const *,ushort const *,bool *)
0x1800b7666  mov     dword ptr [rsp+270h+var_200], eax
0x1800b766a  cmp     byte ptr [rsp+270h+var_240], r12b
0x1800b766f  jz      short loc_1800B76EE
0x1800b7671  mov     rdx, r15
0x1800b7674  lea     rcx, [rbp+170h+var_190]
0x1800b7678  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x1800b767d  nop
0x1800b767e  mov     rdx, rbx
0x1800b7681  lea     rcx, [rbp+170h+var_170]
0x1800b7685  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x1800b768a  nop
0x1800b768b  mov     rdx, rsi
0x1800b768e  lea     rcx, [rbp+170h+var_150]
0x1800b7692  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x1800b7697  nop
0x1800b7698  mov     rdx, r14
0x1800b769b  lea     rcx, [rbp+170h+var_130]
0x1800b769f  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x1800b76a4  nop
0x1800b76a5  lea     rdx, [rbp+170h+var_190]; struct Windows::Internal::AI::Agents::Mcp::Implementation::InternalMcpConsentKey *
0x1800b76a9  lea     rcx, [rbp+170h+var_E0]; this
0x1800b76b0  call    ??0InternalMcpConsentKey@Implementation@Mcp@Agents@AI@Internal@Windows@@QEAA@AEBU0123456@@Z; Windows::Internal::AI::Agents::Mcp::Implementation::InternalMcpConsentKey::InternalMcpConsentKey(Windows::Internal::AI::Agents::Mcp::Implementation::InternalMcpConsentKey const &)
  ... truncated ...
```
