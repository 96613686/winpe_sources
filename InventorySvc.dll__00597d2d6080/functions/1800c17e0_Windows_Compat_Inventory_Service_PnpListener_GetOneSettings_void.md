# Windows::Compat::Inventory::Service::PnpListener::GetOneSettings(void)

- ea: `0x1800c17e0`
- end: `0x1800c1f31`
- name: `?GetOneSettings@PnpListener@Service@Inventory@Compat@Windows@@CAXXZ`
- size: `1873`
- prototype: `void(void)`
- caller_count: `2`
- callee_count: `17`
- tags: `file_ops, registry_config, service_task, broker_com_uri`

## callers

- `0x1800c1f5c`
- `0x1800c22f8`

## callees

- `0x180002bf0`
- `0x180003100`
- `0x1800038b8`
- `0x180005000`
- `0x180005130`
- `0x180005460`
- `0x180006a04`
- `0x180006e60`
- `0x1800074f0`
- `0x180010c14`
- `0x1800152d0`
- `0x18002e1ac`
- `0x1800c0944`
- `0x1800c0b98`
- `0x1800c17e0`
- `0x1800c3094`
- `0x1800c30ac`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800c1a69`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800c1ec0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800c1a69`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800c1ec0`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1800c185f`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1800c1901`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1800c1998`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1800c1a5f`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1800c1cf0`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1800c1d61`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1800c185f`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1800c1901`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1800c1998`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1800c1a5f`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1800c1cf0`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1800c1d61`

## string_xrefs

- `0x1800c181f`: `SOFTWARE\Microsoft\Windows NT\CurrentVersion\AppCompatFlags\OneSettings\InvSvc`
- `0x1800c1865`: `Windows::Compat::Inventory::Service::PnpListener::GetOneSettings`
- `0x1800c18c4`: `Windows::Compat::Inventory::Service::PnpListener::GetOneSettings`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
void Windows::Compat::Inventory::Service::PnpListener::GetOneSettings(void)
{
  char IsEnabled; // al
  char *v1; // rbx
  __int64 v2; // r15
  unsigned __int64 v3; // rbx
  _WORD *v4; // r15
  DWORD LastError; // eax
  __int64 v6; // rdx
  unsigned __int64 v7; // r13
  unsigned __int64 v8; // rsi
  wchar_t *v9; // r12
  __int64 trivial_2; // rax
  unsigned __int64 v11; // r14
  unsigned __int64 first_not_of_trivial_pos_2; // rbx
  unsigned __int64 v13; // rsi
  const wchar_t *v14; // rcx
  wchar_t *v15; // rbx
  __int64 last_not_of; // rax
  __int64 v17; // rcx
  unsigned __int64 v18; // rax
  unsigned __int64 v19; // r8
  __int64 v20; // rax
  unsigned __int64 v21; // rbx
  __int64 v22; // rcx
  char *v23; // rsi
  char *v24; // rbx
  _WORD *v25; // r14
  _WORD *v26; // rsi
  _WORD *v27; // r12
  __int64 v28; // rax
  DWORD v29; // eax
  const char *v30; // rax
  DWORD pcbData; // [rsp+40h] [rbp-1A8h] BYREF
  unsigned __int64 pvData; // [rsp+48h] [rbp-1A0h] BYREF
  unsigned __int64 v33; // [rsp+50h] [rbp-198h]
  const wchar_t *v34; // [rsp+58h] [rbp-190h]
  _WORD *v35; // [rsp+60h] [rbp-188h] BYREF
  unsigned __int64 v36; // [rsp+68h] [rbp-180h]
  const std::exception *v37; // [rsp+70h] [rbp-178h] BYREF
  _BYTE v38[256]; // [rsp+80h] [rbp-168h] BYREF
  __int128 v39; // [rsp+180h] [rbp-68h] BYREF
  __int64 v40; // [rsp+190h] [rbp-58h]
  __int64 v41; // [rsp+198h] [rbp-50h]

  pvData = 0;
  pcbData = 8;
  if ( !(unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_InventorySvc_Logon_CPU_Fix>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_InventorySvc_Logon_CPU_Fix>::GetImpl'::`2'::impl) )
  {
    if ( RegGetValueW(
           HKEY_LOCAL_MACHINE,
           L"SOFTWARE\\Microsoft\\Windows NT\\CurrentVersion\\AppCompatFlags\\OneSettings\\InvSvc",
           L"InvSvcPnPBootPauseMs",
           0x10u,
           0,
           &pvData,
           &pcbData) )
    {
      AslLogCallPrintf(
        3,
        "Windows::Compat::Inventory::Service::PnpListener::GetOneSettings",
        151,
        "Failed to find InvSvcPnPBootPauseMs in OneSettings. Using default value %llu",
        Windows::Compat::Inventory::Service::PnpListener::s_ignoreEventsAfterBootMs);
    }
    else
    {
      AslLogCallPrintf(
        3,
        "Windows::Compat::Inventory::Service::PnpListener::GetOneSettings",
        146,
        "Found InvSvcPnPBootPauseMs in OneSettings with value %llu",
        pvData);
      Windows::Compat::Inventory::Service::PnpListener::s_ignoreEventsAfterBootMs = pvData;
    }
  }
  pcbData = 8;
  if ( RegGetValueW(
         HKEY_LOCAL_MACHINE,
         L"SOFTWARE\\Microsoft\\Windows NT\\CurrentVersion\\AppCompatFlags\\OneSettings\\InvSvc",
         L"InvSvcPnPIgnoreDupesMs",
         0x10u,
         0,
         &pvData,
         &pcbData) )
  {
    AslLogCallPrintf(
      3,
      "Windows::Compat::Inventory::Service::PnpListener::GetOneSettings",
      171,
      "Failed to find InvSvcPnPIgnoreDupesMs in OneSettings. Using default value %llu",
      Windows::Compat::Inventory::Service::PnpListener::s_timeBetweenDuplicateAddsMs);
  }
  else
  {
    AslLogCallPrintf(
      3,
      "Windows::Compat::Inventory::Service::PnpListener::GetOneSettings",
      166,
      "Found InvSvcPnPIgnoreDupesMs in OneSettings with value %llu",
      pvData);
    Windows::Compat::Inventory::Service::PnpListener::s_timeBetweenDuplicateAddsMs = pvData;
  }
  IsEnabled = wil::details::FeatureImpl<__WilFeatureTraits_Feature_InventorySvc_Logon_CPU_Fix>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_InventorySvc_Logon_CPU_Fix>::GetImpl'::`2'::impl);
  pcbData = 0;
  if ( IsEnabled )
  {
    if ( RegGetValueW(
           HKEY_LOCAL_MACHINE,
           L"SOFTWARE\\Microsoft\\Windows NT\\CurrentVersion\\AppCompatFlags\\OneSettings\\InvSvc",
           L"InvSvcPnPDeviceThrottledList",
           2u,
           0,
           0,
           &pcbData) )
    {
      AslLogCallPrintf(
        3,
        "Windows::Compat::Inventory::Service::PnpListener::GetOneSettings",
        188,
        "Failed to find InvSvcPnPDeviceThrottledList in OneSettings. Using default value");
      return;
    }
    v1 = (char *)Windows::Compat::Inventory::Service::PnpListener::s_throttledDeviceFilters;
    v2 = qword_1800FF8E8;
    if ( Windows::Compat::Inventory::Service::PnpListener::s_throttledDeviceFilters != (void *)qword_1800FF8E8 )
    {
      do
      {
        std::wstring::~wstring(v1);
        v1 += 32;
      }
      while ( v1 != (char *)v2 );
      qword_1800FF8E8 = (__int64)Windows::Compat::Inventory::Service::PnpListener::s_throttledDeviceFilters;
    }
    if ( !pcbData )
    {
      AslLogCallPrintf(
        3,
        "Windows::Compat::Inventory::Service::PnpListener::GetOneSettings",
        197,
        "InvSvcPnPDeviceThrottledList is explicitly set to empty - cleared throttled device list");
      return;
    }
    v3 = saturated_mul((unsigned __int64)pcbData >> 1, 2u);
    v4 = operator new[](v3);
    memset_0(v4, 0, v3);
    v33 = (unsigned __int64)v4;
    if ( RegGetValueW(
           HKEY_LOCAL_MACHINE,
           L"SOFTWARE\\Microsoft\\Windows NT\\CurrentVersion\\AppCompatFlags\\OneSettings\\InvSvc",
           L"InvSvcPnPDeviceThrottledList",
           2u,
           0,
           v4,
           &pcbData) )
    {
      LastError = GetLastError();
      AslLogCallPrintf(
        1,
        "Windows::Compat::Inventory::Service::PnpListener::GetOneSettings",
        214,
        "RegGetValueW failed [%d]",
        LastError);
      goto LABEL_80;
    }
    v34 = v4;
    AslLogCallPrintf(
      3,
      "Windows::Compat::Inventory::Service::PnpListener::GetOneSettings",
      220,
      "Found InvSvcPnPDeviceThrottledList in OneSettings with value %ls",
      v4);
    if ( !*v4 )
    {
      AslLogCallPrintf(
        3,
        "Windows::Compat::Inventory::Service::PnpListener::GetOneSettings",
        224,
        "InvSvcPnPDeviceThrottledList is explicitly set to empty - cleared throttled device list");
      goto LABEL_80;
    }
    v7 = -1;
    do
      ++v7;
    while ( v4[v7] );
    v8 = 0;
    while ( 1 )
    {
      if ( v8 >= v7 )
      {
LABEL_58:
        if ( v4 )
          goto LABEL_80;
        return;
      }
      v9 = &v4[v8];
      trivial_2 = _std_find_trivial_2(v9, &v4[v7], 44);
      try
      {
        if ( (_WORD *)trivial_2 == &v4[v7] || (v11 = (trivial_2 - (__int64)v4) >> 1, v11 == -1) )
        {
          v11 = v7;
LABEL_29:
          v6 = v7 - v8;
          if ( v7 - v8 >= v11 - v8 )
            v6 = v11 - v8;
          v35 = &v4[v8];
          v36 = v6;
          if ( v6 )
          {
            if ( (unsigned __int64)(v6 + 4) < 0x10 )
            {
              v13 = (unsigned __int64)&v9[v6];
              memset_0(v38, 0, sizeof(v38));
              v14 = L" \t\r\n";
              v6 = 256;
              while ( *v14 < 0x100u )
              {
                v38[*(unsigned __int8 *)v14++] = 1;
                if ( v14 == L"" )
                {
                  v15 = v9;
                  if ( (unsigned __int64)v9 >= v13 )
                    goto LABEL_55;
                  while ( *v15 < 0x100u && v38[*v15] )
                  {
                    if ( (unsigned __int64)++v15 >= v13 )
                      goto LABEL_55;
                  }
                  goto LABEL_46;
                }
              }
              v15 = v9;
              if ( (unsigned __int64)v9 >= v13 )
                goto LABEL_55;
              while ( wmemchr(L" \t\r\n", *v15, 4u) )
              {
                if ( (unsigned __int64)++v15 >= v13 )
                  goto LABEL_55;
              }
LABEL_46:
              first_not_of_trivial_pos_2 = v15 - v9;
            }
            else
            {
              first_not_of_trivial_pos_2 = _std_find_first_not_of_trivial_pos_2(&v4[v8], v6, L" \t\r\n", 4);
            }
            if ( first_not_of_trivial_pos_2 != -1 )
            {
              last_not_of = std::basic_string_view<unsigned short>::find_last_not_of(&v35);
              if ( v36 < first_not_of_trivial_pos_2 )
                std::basic_string_view<unsigned short>::_Xran();
              v18 = last_not_of - first_not_of_trivial_pos_2 + 1;
              v19 = v36 - first_not_of_trivial_pos_2;
              if ( v36 - first_not_of_trivial_pos_2 >= v18 )
                v19 = v18;
              v6 = (__int64)&v35[first_not_of_trivial_pos_2];
              *(_QWORD *)&v39 = v6;
              *((_QWORD *)&v39 + 1) = v19;
              if ( v19 )
              {
                v20 = qword_1800FF8E8;
                if ( qword_1800FF8E8 == qword_1800FF8F0 )
                {
                  std::vector<std::wstring>::_Emplace_reallocate<std::basic_string_view<unsigned short> &>(
                    v17,
                    qword_1800FF8E8,
                    &v39);
                }
                else
                {
                  *(_OWORD *)qword_1800FF8E8 = 0;
                  *(_QWORD *)(v20 + 16) = 0;
                  *(_QWORD *)(v20 + 24) = 0;
                  std::wstring::_Construct<1,unsigned short const *>(v20);
                  qword_1800FF8E8 += 32;
                }
              }
            }
          }
        }
        else if ( v8 < v11 )
        {
          goto LABEL_29;
        }
LABEL_55:
        v8 = v11;
        if ( v11 != v7 )
          v8 = v11 + 1;
      }
      catch ( const std::exception *v37 )
      {
        v30 = (const char *)(*(__int64 (__fastcall **)(const std::exception *))(*(_QWORD *)v37 + 8LL))(v37);
        AslLogCallPrintf(
          1,
          "Windows::Compat::Inventory::Service::PnpListener::GetOneSettings",
          260,
          "Exception while parsing throttled device list: [%hs]. Input: [%ls]",
          v30,
          v34);
        v4 = (_WORD *)v33;
        goto LABEL_58;
      }
    }
  }
  if ( RegGetValueW(
         HKEY_LOCAL_MACHINE,
         L"SOFTWARE\\Microsoft\\Windows NT\\CurrentVersion\\AppCompatFlags\\OneSettings\\InvSvc",
         L"InvSvcPnPDeviceBlacklist",
         2u,
         0,
         0,
         &pcbData) )
  {
    AslLogCallPrintf(
      3,
      "Windows::Compat::Inventory::Service::PnpListener::GetOneSettings",
      322,
      "Failed to find InvSvcPnPDeviceBlacklist in OneSettings. Using default value");
  }
  else
  {
    v33 = (unsigned __int64)pcbData >> 1;
    v21 = saturated_mul(v33, 2u);
    v4 = operator new[](v21);
    memset_0(v4, 0, v21);
    v34 = v4;
    if ( RegGetValueW(
           HKEY_LOCAL_MACHINE,
           L"SOFTWARE\\Microsoft\\Windows NT\\CurrentVersion\\AppCompatFlags\\OneSettings\\InvSvc",
           L"InvSvcPnPDeviceBlacklist",
           2u,
           0,
           v4,
           &pcbData) )
    {
      v29 = GetLastError();
      AslLogCallPrintf(
        1,
        "Windows::Compat::Inventory::Service::PnpListener::GetOneSettings",
        317,
        "RegGetValueW failed [%d]",
        v29);
    }
    else
    {
      AslLogCallPrintf(
        3,
        "Windows::Compat::Inventory::Service::PnpListener::GetOneSettings",
        291,
        "Found InvSvcPnPDeviceBlacklist in OneSettings with value %ls",
        v4);
      v23 = (char *)Windows::Compat::Inventory::Service::PnpListener::s_deviceFilters;
      v24 = (char *)qword_1800FF8D0;
      if ( Windows::Compat::Inventory::Service::PnpListener::s_deviceFilters != (void *)qword_1800FF8D0 )
      {
        do
        {
          std::wstring::~wstring(v23);
          v23 += 32;
        }
        while ( v23 != v24 );
        v24 = (char *)Windows::Compat::Inventory::Service::PnpListener::s_deviceFilters;
        qword_1800FF8D0 = (__int64)Windows::Compat::Inventory::Service::PnpListener::s_deviceFilters;
      }
      v25 = v4;
      v26 = v4;
      v27 = &v4[v33];
      if ( v4 < v27 )
      {
        do
        {
          if ( !*v26 )
            break;
          if ( *v26 == 44 )
          {
            v39 = 0;
            v40 = 0;
            v41 = 0;
            if ( v25 == v26 )
            {
              v28 = 0;
              v40 = 0;
              v41 = 7;
              LOWORD(v39) = 0;
            }
            else
            {
              std::wstring::_Construct<1,unsigned short const *>(&v39);
              v28 = v40;
              v24 = (char *)qword_1800FF8D0;
            }
            if ( v28 )
            {
              if ( v24 == (char *)qword_1800FF8D8 )
              {
                std::vector<std::wstring>::_Emplace_reallocate<std::wstring const &>(v22, v24, &v39);
              }
              else
              {
                std::wstring::wstring(v24, &v39);
                qword_1800FF8D0 += 32;
              }
            }
            v25 = ++v26;
            std::wstring::~wstring(&v39);
            v24 = (char *)qword_1800FF8D0;
          }
          ++v26;
        }
        while ( v26 < v27 );
      }
    }
LABEL_80:
    operator delete(v4, (const struct std::nothrow_t *)v6);
  }
}

```

## disassembly

```asm
0x1800c17e0  push    rbx
0x1800c17e2  push    rsi
0x1800c17e3  push    rdi
0x1800c17e4  push    r12
0x1800c17e6  push    r13
0x1800c17e8  push    r14
0x1800c17ea  push    r15
0x1800c17ec  sub     rsp, 1B0h
0x1800c17f3  mov     rax, cs:__security_cookie
0x1800c17fa  xor     rax, rsp
0x1800c17fd  mov     [rsp+1E8h+var_48], rax
0x1800c1805  xor     edi, edi
0x1800c1807  mov     [rsp+1E8h+var_1A0], rdi
0x1800c180c  lea     ebx, [rdi+8]
0x1800c180f  mov     [rsp+1E8h+var_1A8], ebx
0x1800c1813  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_InventorySvc_Logon_CPU_Fix@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_InventorySvc_Logon_CPU_Fix@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_InventorySvc_Logon_CPU_Fix> `wil::Feature<__WilFeatureTraits_Feature_InventorySvc_Logon_CPU_Fix>::GetImpl(void)'::`2'::impl
0x1800c181a  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_InventorySvc_Logon_CPU_Fix@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_InventorySvc_Logon_CPU_Fix>::__private_IsEnabled(void)
0x1800c181f  lea     r12, aSoftwareMicros_9; "SOFTWARE\\Microsoft\\Windows NT\\Curren"...
0x1800c1826  mov     r13, 0FFFFFFFF80000002h
0x1800c182d  test    al, al
0x1800c182f  jnz     loc_1800C18C4
0x1800c1835  lea     rax, [rsp+1E8h+var_1A8]
0x1800c183a  mov     [rsp+1E8h+pcbData], rax; pcbData
0x1800c183f  lea     rax, [rsp+1E8h+var_1A0]
0x1800c1844  mov     [rsp+1E8h+pvData], rax; pvData
0x1800c1849  mov     [rsp+1E8h+pdwType], rdi; pdwType
0x1800c184e  lea     r9d, [rdi+10h]; dwFlags
0x1800c1852  lea     r8, aInvsvcpnpbootp; "InvSvcPnPBootPauseMs"
0x1800c1859  mov     rdx, r12; lpSubKey
0x1800c185c  mov     rcx, r13; hkey
0x1800c185f  call    cs:__imp_RegGetValueW
0x1800c1865  lea     rsi, aWindowsCompatI_55; "Windows::Compat::Inventory::Service::Pn"...
0x1800c186c  lea     r14d, [rdi+3]
0x1800c1870  mov     rdx, rsi
0x1800c1873  mov     ecx, r14d
0x1800c1876  test    eax, eax
0x1800c1878  jnz     short loc_1800C18A4
0x1800c187a  mov     rax, [rsp+1E8h+var_1A0]
0x1800c187f  mov     [rsp+1E8h+pdwType], rax
0x1800c1884  lea     r9, aFoundInvsvcpnp_2; "Found InvSvcPnPBootPauseMs in OneSettin"...
0x1800c188b  mov     r8d, 92h
0x1800c1891  call    AslLogCallPrintf
0x1800c1896  mov     rax, [rsp+1E8h+var_1A0]
0x1800c189b  mov     cs:?s_ignoreEventsAfterBootMs@PnpListener@Service@Inventory@Compat@Windows@@0_KA, rax; unsigned __int64 Windows::Compat::Inventory::Service::PnpListener::s_ignoreEventsAfterBootMs
0x1800c18a2  jmp     short loc_1800C18D1
0x1800c18a4  mov     rax, cs:?s_ignoreEventsAfterBootMs@PnpListener@Service@Inventory@Compat@Windows@@0_KA; unsigned __int64 Windows::Compat::Inventory::Service::PnpListener::s_ignoreEventsAfterBootMs
0x1800c18ab  mov     [rsp+1E8h+pdwType], rax
0x1800c18b0  lea     r9, aFailedToFindIn_1; "Failed to find InvSvcPnPBootPauseMs in "...
0x1800c18b7  mov     r8d, 97h
0x1800c18bd  call    AslLogCallPrintf
0x1800c18c2  jmp     short loc_1800C18D1
0x1800c18c4  lea     rsi, aWindowsCompatI_55; "Windows::Compat::Inventory::Service::Pn"...
0x1800c18cb  mov     r14d, 3
0x1800c18d1  mov     [rsp+1E8h+var_1A8], ebx
0x1800c18d5  lea     rax, [rsp+1E8h+var_1A8]
0x1800c18da  mov     [rsp+1E8h+pcbData], rax; pcbData
0x1800c18df  lea     rax, [rsp+1E8h+var_1A0]
0x1800c18e4  mov     [rsp+1E8h+pvData], rax; pvData
0x1800c18e9  mov     [rsp+1E8h+pdwType], rdi; pdwType
0x1800c18ee  mov     r9d, 10h; dwFlags
0x1800c18f4  lea     r8, aInvsvcpnpignor; "InvSvcPnPIgnoreDupesMs"
0x1800c18fb  mov     rdx, r12; lpSubKey
0x1800c18fe  mov     rcx, r13; hkey
0x1800c1901  call    cs:__imp_RegGetValueW
0x1800c1907  mov     rdx, rsi
0x1800c190a  mov     ecx, r14d
0x1800c190d  test    eax, eax
0x1800c190f  jnz     short loc_1800C193B
0x1800c1911  mov     rax, [rsp+1E8h+var_1A0]
0x1800c1916  mov     [rsp+1E8h+pdwType], rax
0x1800c191b  lea     r9, aFoundInvsvcpnp_0; "Found InvSvcPnPIgnoreDupesMs in OneSett"...
0x1800c1922  mov     r8d, 0A6h
0x1800c1928  call    AslLogCallPrintf
0x1800c192d  mov     rax, [rsp+1E8h+var_1A0]
0x1800c1932  mov     cs:?s_timeBetweenDuplicateAddsMs@PnpListener@Service@Inventory@Compat@Windows@@0_KA, rax; unsigned __int64 Windows::Compat::Inventory::Service::PnpListener::s_timeBetweenDuplicateAddsMs
0x1800c1939  jmp     short loc_1800C1959
0x1800c193b  mov     rax, cs:?s_timeBetweenDuplicateAddsMs@PnpListener@Service@Inventory@Compat@Windows@@0_KA; unsigned __int64 Windows::Compat::Inventory::Service::PnpListener::s_timeBetweenDuplicateAddsMs
0x1800c1942  mov     [rsp+1E8h+pdwType], rax
0x1800c1947  lea     r9, aFailedToFindIn_0; "Failed to find InvSvcPnPIgnoreDupesMs i"...
0x1800c194e  mov     r8d, 0ABh
0x1800c1954  call    AslLogCallPrintf
0x1800c1959  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_InventorySvc_Logon_CPU_Fix@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_InventorySvc_Logon_CPU_Fix@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_InventorySvc_Logon_CPU_Fix> `wil::Feature<__WilFeatureTraits_Feature_InventorySvc_Logon_CPU_Fix>::GetImpl(void)'::`2'::impl
0x1800c1960  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_InventorySvc_Logon_CPU_Fix@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_InventorySvc_Logon_CPU_Fix>::__private_IsEnabled(void)
0x1800c1965  mov     [rsp+1E8h+var_1A8], edi
0x1800c1969  mov     rdx, r12; lpSubKey
0x1800c196c  mov     rcx, r13; hkey
0x1800c196f  test    al, al
0x1800c1971  lea     rax, [rsp+1E8h+var_1A8]
0x1800c1976  mov     [rsp+1E8h+pcbData], rax; pcbData
0x1800c197b  mov     [rsp+1E8h+pvData], rdi; pvData
0x1800c1980  mov     [rsp+1E8h+pdwType], rdi; pdwType
0x1800c1985  jz      loc_1800C1CE1
0x1800c198b  mov     r9d, 2; dwFlags
0x1800c1991  lea     r8, aInvsvcpnpdevic_0; "InvSvcPnPDeviceThrottledList"
0x1800c1998  call    cs:__imp_RegGetValueW
0x1800c199e  test    eax, eax
0x1800c19a0  jz      short loc_1800C19B4
0x1800c19a2  lea     r9, aFailedToFindIn_2; "Failed to find InvSvcPnPDeviceThrottled"...
0x1800c19a9  mov     r8d, 0BCh
0x1800c19af  jmp     loc_1800C1EFC
0x1800c19b4  mov     rbx, cs:?s_throttledDeviceFilters@PnpListener@Service@Inventory@Compat@Windows@@0V?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@A; std::vector<std::wstring> Windows::Compat::Inventory::Service::PnpListener::s_throttledDeviceFilters
0x1800c19bb  mov     r15, cs:qword_1800FF8E8
0x1800c19c2  cmp     rbx, r15
0x1800c19c5  jz      short loc_1800C19E6
0x1800c19c7  mov     rcx, rbx; void *
0x1800c19ca  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800c19cf  add     rbx, 20h ; ' '
0x1800c19d3  cmp     rbx, r15
0x1800c19d6  jnz     short loc_1800C19C7
0x1800c19d8  mov     rbx, cs:?s_throttledDeviceFilters@PnpListener@Service@Inventory@Compat@Windows@@0V?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@A; std::vector<std::wstring> Windows::Compat::Inventory::Service::PnpListener::s_throttledDeviceFilters
0x1800c19df  mov     cs:qword_1800FF8E8, rbx
0x1800c19e6  cmp     [rsp+1E8h+var_1A8], edi
0x1800c19ea  ja      short loc_1800C19FE
0x1800c19ec  lea     r9, aInvsvcpnpdevic_1; "InvSvcPnPDeviceThrottledList is explici"...
0x1800c19f3  mov     r8d, 0C5h
0x1800c19f9  jmp     loc_1800C1EFC
0x1800c19fe  mov     ecx, [rsp+1E8h+var_1A8]
0x1800c1a02  shr     rcx, 1
0x1800c1a05  mov     eax, 2
0x1800c1a0a  mul     rcx
0x1800c1a0d  mov     rbx, rax
0x1800c1a10  mov     rax, 0FFFFFFFFFFFFFFFFh
0x1800c1a17  cmovb   rbx, rax
0x1800c1a1b  mov     rcx, rbx; unsigned __int64
0x1800c1a1e  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x1800c1a23  mov     r15, rax
0x1800c1a26  mov     r8, rbx; Size
0x1800c1a29  xor     edx, edx; Val
0x1800c1a2b  mov     rcx, rax; void *
0x1800c1a2e  call    memset_0
0x1800c1a33  mov     [rsp+1E8h+var_198], r15
0x1800c1a38  lea     rax, [rsp+1E8h+var_1A8]
0x1800c1a3d  mov     [rsp+1E8h+pcbData], rax; pcbData
0x1800c1a42  mov     [rsp+1E8h+pvData], r15; pvData
0x1800c1a47  mov     [rsp+1E8h+pdwType], rdi; pdwType
0x1800c1a4c  mov     r9d, 2; dwFlags
0x1800c1a52  lea     r8, aInvsvcpnpdevic_0; "InvSvcPnPDeviceThrottledList"
0x1800c1a59  mov     rdx, r12; lpSubKey
0x1800c1a5c  mov     rcx, r13; hkey
0x1800c1a5f  call    cs:__imp_RegGetValueW
0x1800c1a65  test    eax, eax
0x1800c1a67  jz      short loc_1800C1A93
0x1800c1a69  call    cs:__imp_GetLastError
0x1800c1a6f  mov     dword ptr [rsp+1E8h+pdwType], eax
0x1800c1a73  lea     r9, aReggetvaluewFa; "RegGetValueW failed [%d]"
0x1800c1a7a  mov     r8d, 0D6h
0x1800c1a80  mov     rdx, rsi
0x1800c1a83  mov     ecx, 1
0x1800c1a88  call    AslLogCallPrintf
0x1800c1a8d  nop
0x1800c1a8e  jmp     loc_1800C1EE5
0x1800c1a93  mov     [rsp+1E8h+var_190], r15
0x1800c1a98  mov     [rsp+1E8h+pdwType], r15
0x1800c1a9d  lea     r9, aFoundInvsvcpnp_1; "Found InvSvcPnPDeviceThrottledList in O"...
0x1800c1aa4  mov     r8d, 0DCh
0x1800c1aaa  mov     rdx, rsi
0x1800c1aad  mov     ecx, r14d
0x1800c1ab0  call    AslLogCallPrintf
0x1800c1ab5  cmp     [r15], di
0x1800c1ab9  jz      loc_1800C1CC4
0x1800c1abf  or      r13, 0FFFFFFFFFFFFFFFFh
0x1800c1ac3  inc     r13
0x1800c1ac6  cmp     [r15+r13*2], di
0x1800c1acb  jnz     short loc_1800C1AC3
0x1800c1acd  mov     rsi, rdi
0x1800c1ad0  cmp     rsi, r13
0x1800c1ad3  jnb     loc_1800C1CAF
0x1800c1ad9  lea     rbx, [r15+r13*2]
0x1800c1add  lea     r12, [r15+rsi*2]
0x1800c1ae1  mov     r8d, 2Ch ; ','
0x1800c1ae7  mov     rdx, rbx
0x1800c1aea  mov     rcx, r12
0x1800c1aed  call    __std_find_trivial_2
0x1800c1af2  mov     r14, rax
0x1800c1af5  cmp     rax, rbx
0x1800c1af8  jz      short loc_1800C1B11
0x1800c1afa  sub     r14, r15
0x1800c1afd  sar     r14, 1
0x1800c1b00  cmp     r14, 0FFFFFFFFFFFFFFFFh
0x1800c1b04  jz      short loc_1800C1B11
0x1800c1b06  cmp     rsi, r14
0x1800c1b09  jnb     loc_1800C1C9C
0x1800c1b0f  jmp     short loc_1800C1B14
0x1800c1b11  mov     r14, r13
0x1800c1b14  mov     rax, r14
0x1800c1b17  sub     rax, rsi
0x1800c1b1a  mov     rdx, r13
0x1800c1b1d  sub     rdx, rsi
0x1800c1b20  cmp     rdx, rax
0x1800c1b23  cmovnb  rdx, rax
0x1800c1b27  mov     [rsp+1E8h+var_188], r12
0x1800c1b2c  mov     [rsp+1E8h+var_180], rdx
0x1800c1b31  test    rdx, rdx
0x1800c1b34  jz      loc_1800C1C9C
0x1800c1b3a  lea     rax, [rdx+4]
0x1800c1b3e  cmp     rax, 10h
0x1800c1b42  jb      short loc_1800C1B61
0x1800c1b44  mov     r9d, 4
0x1800c1b4a  lea     r8, S; " \t\r\n"
0x1800c1b51  mov     rcx, r12
0x1800c1b54  call    __std_find_first_not_of_trivial_pos_2
0x1800c1b59  mov     rbx, rax
0x1800c1b5c  jmp     loc_1800C1C0C
0x1800c1b61  lea     rsi, [r12+rdx*2]
0x1800c1b65  xor     edx, edx; Val
0x1800c1b67  mov     r8d, 100h; Size
0x1800c1b6d  lea     rcx, [rsp+1E8h+var_168]; void *
0x1800c1b75  call    memset_0
0x1800c1b7a  lea     rcx, S; " \t\r\n"
0x1800c1b81  mov     edx, 100h
0x1800c1b86  cmp     [rcx], dx
0x1800c1b89  jnb     short loc_1800C1BD2
0x1800c1b8b  movzx   eax, byte ptr [rcx]
0x1800c1b8e  mov     [rsp+rax+1E8h+var_168], 1
0x1800c1b96  add     rcx, 2
0x1800c1b9a  lea     rax, S+8; ""
0x1800c1ba1  cmp     rcx, rax
0x1800c1ba4  jnz     short loc_1800C1B86
0x1800c1ba6  mov     rbx, r12
0x1800c1ba9  cmp     r12, rsi
0x1800c1bac  jnb     loc_1800C1C9C
0x1800c1bb2  cmp     [rbx], dx
0x1800c1bb5  jnb     short loc_1800C1C06
0x1800c1bb7  movzx   eax, word ptr [rbx]
0x1800c1bba  cmp     [rsp+rax+1E8h+var_168], dil
0x1800c1bc2  jz      short loc_1800C1C06
0x1800c1bc4  add     rbx, 2
0x1800c1bc8  cmp     rbx, rsi
0x1800c1bcb  jb      short loc_1800C1BB2
0x1800c1bcd  jmp     loc_1800C1C9C
0x1800c1bd2  mov     rbx, r12
0x1800c1bd5  cmp     r12, rsi
0x1800c1bd8  jnb     loc_1800C1C9C
0x1800c1bde  mov     r8d, 4; N
0x1800c1be4  movzx   edx, word ptr [rbx]; C
0x1800c1be7  lea     rcx, S; " \t\r\n"
0x1800c1bee  call    wmemchr
0x1800c1bf3  test    rax, rax
0x1800c1bf6  jz      short loc_1800C1C06
0x1800c1bf8  add     rbx, 2
0x1800c1bfc  cmp     rbx, rsi
0x1800c1bff  jb      short loc_1800C1BDE
0x1800c1c01  jmp     loc_1800C1C9C
0x1800c1c06  sub     rbx, r12
0x1800c1c09  sar     rbx, 1
0x1800c1c0c  cmp     rbx, 0FFFFFFFFFFFFFFFFh
0x1800c1c10  jz      loc_1800C1C9C
0x1800c1c16  lea     rcx, [rsp+1E8h+var_188]
0x1800c1c1b  call    ?find_last_not_of@?$basic_string_view@GU?$char_traits@G@std@@@std@@QEBA_KQEBG_K@Z; std::basic_string_view<ushort>::find_last_not_of(ushort const * const,unsigned __int64)
0x1800c1c20  mov     r8, [rsp+1E8h+var_180]
0x1800c1c25  cmp     r8, rbx
0x1800c1c28  jb      loc_1800C1F2A
0x1800c1c2e  sub     rax, rbx
0x1800c1c31  inc     rax
0x1800c1c34  sub     r8, rbx
0x1800c1c37  cmp     r8, rax
0x1800c1c3a  cmovnb  r8, rax
0x1800c1c3e  mov     rax, [rsp+1E8h+var_188]
0x1800c1c43  lea     rdx, [rax+rbx*2]
0x1800c1c47  mov     qword ptr [rsp+1E8h+var_68], rdx
0x1800c1c4f  mov     qword ptr [rsp+1E8h+var_68+8], r8
0x1800c1c57  test    r8, r8
0x1800c1c5a  jz      short loc_1800C1C9C
0x1800c1c5c  mov     rax, cs:qword_1800FF8E8
0x1800c1c63  cmp     rax, cs:qword_1800FF8F0
0x1800c1c6a  jz      short loc_1800C1C8C
0x1800c1c6c  xorps   xmm0, xmm0
0x1800c1c6f  movups  xmmword ptr [rax], xmm0
0x1800c1c72  mov     [rax+10h], rdi
0x1800c1c76  mov     [rax+18h], rdi
0x1800c1c7a  mov     rcx, rax
0x1800c1c7d  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x1800c1c82  add     cs:qword_1800FF8E8, 20h ; ' '
0x1800c1c8a  jmp     short loc_1800C1C9C
0x1800c1c8c  lea     r8, [rsp+1E8h+var_68]
0x1800c1c94  mov     rdx, rax
0x1800c1c97  call    ??$_Emplace_reallocate@AEAV?$basic_string_view@GU?$char_traits@G@std@@@std@@@?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@AEAAPEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@QEAV21@AEAV?$basic_string_view@GU?$char_traits@G@std@@@1@@Z; std::vector<std::wstring>::_Emplace_reallocate<std::basic_string_view<ushort> &>(std::wstring * const,std::basic_string_view<ushort> &)
0x1800c1c9c  lea     rax, [r14+1]
0x1800c1ca0  mov     rsi, r14
0x1800c1ca3  cmp     r14, r13
0x1800c1ca6  cmovnz  rsi, rax
0x1800c1caa  jmp     loc_1800C1AD0
0x1800c1caf  jmp     short loc_1800C1CB6
0x1800c1cb1  mov     r15, [rsp+1E8h+var_198]
0x1800c1cb6  test    r15, r15
0x1800c1cb9  jz      loc_1800C1F07
0x1800c1cbf  jmp     loc_1800C1EE5
0x1800c1cc4  lea     r9, aInvsvcpnpdevic_1; "InvSvcPnPDeviceThrottledList is explici"...
0x1800c1ccb  mov     r8d, 0E0h
0x1800c1cd1  mov     rdx, rsi
0x1800c1cd4  mov     ecx, r14d
0x1800c1cd7  call    AslLogCallPrintf
0x1800c1cdc  jmp     loc_1800C1A8E
0x1800c1ce1  mov     ebx, 2
0x1800c1ce6  mov     r9d, ebx; dwFlags
0x1800c1ce9  lea     r8, aInvsvcpnpdevic; "InvSvcPnPDeviceBlacklist"
0x1800c1cf0  call    cs:__imp_RegGetValueW
0x1800c1cf6  test    eax, eax
0x1800c1cf8  jnz     loc_1800C1EEF
0x1800c1cfe  mov     ecx, [rsp+1E8h+var_1A8]
  ... truncated ...
```
