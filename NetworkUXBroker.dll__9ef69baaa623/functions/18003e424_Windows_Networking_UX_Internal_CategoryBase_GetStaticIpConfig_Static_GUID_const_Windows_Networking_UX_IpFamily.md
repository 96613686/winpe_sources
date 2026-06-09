# Windows::Networking::UX::Internal::CategoryBase::GetStaticIpConfig_Static(_GUID const &,Windows::Networking::UX::IpFamily,Windows::Networking::UX::IStaticIpConfig * *)

- ea: `0x18003e424`
- end: `0x18003ed19`
- name: `?GetStaticIpConfig_Static@CategoryBase@Internal@UX@Networking@Windows@@SAJAEBU_GUID@@W4IpFamily@345@PEAPEAUIStaticIpConfig@345@@Z`
- size: `2293`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `2`
- callee_count: `15`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x18003ccc0`
- `0x18003f65c`

## callees

- `0x180002520`
- `0x18000955c`
- `0x18000e768`
- `0x180013b8c`
- `0x18001a2d0`
- `0x180030678`
- `0x18003a438`
- `0x18003e1f0`
- `0x18003e30c`
- `0x18003e404`
- `0x18003e424`
- `0x18003efdc`
- `0x18003f27c`
- `0x180044a70`
- `0x180047010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18003e4c9`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18003e4c9`
- `ntdll!RtlIpv4AddressToStringExW` at `0x18003e609`
- `ntdll!RtlIpv4AddressToStringExW` at `0x18003e8a7`
- `ntdll!RtlIpv4AddressToStringExW` at `0x18003e609`
- `ntdll!RtlIpv4AddressToStringExW` at `0x18003e8a7`
- `ntdll!RtlIpv6AddressToStringExW` at `0x18003e63a`
- `ntdll!RtlIpv6AddressToStringExW` at `0x18003e93d`
- `ntdll!RtlIpv6AddressToStringExW` at `0x18003e63a`
- `ntdll!RtlIpv6AddressToStringExW` at `0x18003e93d`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18003e6da`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18003e760`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18003e7a5`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18003e8f6`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18003e9a2`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18003ea35`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18003eabc`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18003e6da`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18003e760`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18003e7a5`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18003e8f6`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18003e9a2`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18003ea35`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18003eabc`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x18003e68d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x18003e9f1`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x18003e68d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x18003e9f1`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003e670`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003e6b8`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003e73e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003e78b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003e9d8`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003ea1b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003eaa2`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003eaef`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003e670`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003e6b8`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003e73e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003e78b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003e9d8`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003ea1b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003eaa2`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003eaef`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18003e4b0`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18003e4b0`
- `IPHLPAPI!GetUnicastIpAddressTable` at `0x18003e566`
- `IPHLPAPI!GetUnicastIpAddressTable` at `0x18003e566`
- `IPHLPAPI!GetIpForwardTable2` at `0x18003e7d5`
- `IPHLPAPI!GetIpForwardTable2` at `0x18003e7d5`

## string_xrefs

- `0x18003e4a9`: `Windows.Networking.UX.StaticIpConfig`

## pseudocode

```c
// Hidden C++ exception states: #wind=10 #try_helpers=1
__int64 __fastcall Windows::Networking::UX::Internal::CategoryBase::GetStaticIpConfig_Static(
        const struct _GUID *a1,
        unsigned int a2,
        _QWORD *a3)
{
  _QWORD *v3; // r14
  ULONG v5; // r15d
  int v6; // esi
  int v7; // eax
  unsigned int v8; // ebx
  int v10; // eax
  unsigned int v11; // ebx
  char v12; // r14
  __int16 v13; // r12
  PMIB_UNICASTIPADDRESS_TABLE v14; // rbx
  unsigned __int64 v15; // rsi
  ULONG v16; // edx
  LONG v17; // eax
  int v18; // eax
  HRESULT v19; // eax
  unsigned int v20; // r14d
  PWSTR v21; // rcx
  int v22; // eax
  unsigned int v23; // ebx
  PWSTR v24; // rcx
  PWSTR v25; // rcx
  __int16 v26; // si
  unsigned int IpForwardTable2; // eax
  unsigned int v28; // ebx
  unsigned int v29; // r12d
  char *Reserved1; // rbx
  __int64 v31; // r14
  ULONG v32; // edx
  LONG v33; // eax
  int v34; // esi
  wil::details::in1diag3 *v35; // rcx
  __int64 v36; // rdx
  PWSTR v37; // r15
  LONG v38; // eax
  PWSTR v39; // r8
  int v40; // ecx
  PWSTR v41; // rcx
  HRESULT v42; // eax
  unsigned int v43; // esi
  PWSTR v44; // rcx
  int v45; // eax
  unsigned int v46; // ebx
  PWSTR v47; // rcx
  int v48; // eax
  unsigned int v49; // ebx
  unsigned int i; // ebx
  int v51; // eax
  unsigned int v52; // esi
  int v53; // eax
  unsigned int v54; // esi
  __int64 v55; // rcx
  unsigned int v56; // [rsp+20h] [rbp-C8h]
  PWSTR AddressString; // [rsp+30h] [rbp-B8h] BYREF
  __int64 v58; // [rsp+38h] [rbp-B0h] BYREF
  int v59; // [rsp+40h] [rbp-A8h]
  HSTRING string; // [rsp+48h] [rbp-A0h] BYREF
  ULONG AddressStringLength; // [rsp+50h] [rbp-98h] BYREF
  unsigned int v62; // [rsp+54h] [rbp-94h] BYREF
  PMIB_UNICASTIPADDRESS_TABLE Table; // [rsp+58h] [rbp-90h] BYREF
  __int64 v64; // [rsp+60h] [rbp-88h] BYREF
  _QWORD *v65; // [rsp+68h] [rbp-80h]
  HSTRING_HEADER hstringHeader; // [rsp+70h] [rbp-78h] BYREF
  struct _GUID v67; // [rsp+90h] [rbp-58h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+E8h] [rbp+0h]

  v3 = a3;
  v65 = a3;
  v5 = 0;
  *a3 = 0;
  v6 = 2;
  if ( a2 != 4 )
    LOWORD(v6) = 23;
  v59 = v6;
  v58 = 0;
  v67 = *Windows::Networking::UX::Internal::CategoryBase::_GetActualInterfaceGuid((struct _GUID *)&hstringHeader, a1);
  v62 = Windows::Networking::UX::Internal::CategoryBase::_ConvertInterfaceGuidToIndex(&v67);
  if ( WindowsCreateStringReference(
         L"Windows.Networking.UX.StaticIpConfig",
         0x24u,
         (HSTRING_HEADER *)&hstringHeader.Reserved.Reserved2[8],
         (HSTRING *)&hstringHeader) < 0 )
    RaiseException(0xC000000D, 1u, 0, 0);
  v7 = Windows::Foundation::ActivateInstance<Microsoft::WRL::ComPtr<Windows::Networking::UX::IStaticIpConfig>>(
         (__int64)hstringHeader.Reserved.Reserved1,
         &v58);
  v8 = v7;
  if ( v7 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x128,
      (unsigned int)"onecoreuap\\net\\ux\\mediamanagerbase\\lib\\categorybase.cpp",
      (const char *)(unsigned int)v7,
      v56);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v58);
    return v8;
  }
  v10 = (*(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v58 + 56LL))(v58, a2);
  v11 = v10;
  if ( v10 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x129,
      (unsigned int)"onecoreuap\\net\\ux\\mediamanagerbase\\lib\\categorybase.cpp",
      (const char *)(unsigned int)v10,
      v56);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v58);
    return v11;
  }
  Table = 0;
  if ( GetUnicastIpAddressTable(0, &Table) )
    goto LABEL_82;
  v12 = 0;
  v13 = v59;
  while ( 1 )
  {
    v14 = Table;
    if ( v5 >= Table->NumEntries )
      break;
    v15 = v5;
    if ( Table->Table[v15].InterfaceIndex != v62
      || Table->Table[v15].Address.Ipv4.sin_family != v13
      || Table->Table[v15].PrefixOrigin != IpPrefixOriginManual
      || Table->Table[v15].SuffixOrigin != NlsoManual )
    {
      goto LABEL_36;
    }
    v16 = 22;
    if ( a2 != 4 )
      v16 = 65;
    AddressStringLength = v16;
    wil::make_unique_hlocal<unsigned short [0]>(&AddressString);
    if ( v14->Table[v15].Address.Ipv4.sin_family == 2 )
    {
      v17 = RtlIpv4AddressToStringExW(&v14->Table[v15].Address.Ipv4.sin_addr, 0, AddressString, &AddressStringLength);
LABEL_22:
      v18 = v17 | 0x10000000;
      goto LABEL_23;
    }
    v18 = 0;
    if ( v14->Table[v15].Address.Ipv4.sin_family == 23 )
    {
      v17 = RtlIpv6AddressToStringExW(
              &v14->Table[v15].Address.Ipv6.sin6_addr,
              v14->Table[v15].Address.Ipv6.sin6_scope_id,
              0,
              AddressString,
              &AddressStringLength);
      goto LABEL_22;
    }
LABEL_23:
    if ( v18 >= 0 )
    {
      string = 0;
      WindowsDeleteString(0);
      string = 0;
      v19 = WindowsCreateString(AddressString, AddressStringLength, &string);
      v20 = v19;
      if ( v19 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x14C,
          (unsigned int)"onecoreuap\\net\\ux\\mediamanagerbase\\lib\\categorybase.cpp",
          (const char *)(unsigned int)v19,
          v56);
        WindowsDeleteString(string);
        string = 0;
        v21 = AddressString;
        AddressString = 0;
        if ( v21 )
          LocalFree(v21);
        wil::details::unique_storage<wil::details::resource_policy<_MIB_IF_TABLE2 *,void (*)(void *),&void FreeMibTable(void *),wistd::integral_constant<unsigned __int64,0>,_MIB_IF_TABLE2 *,_MIB_IF_TABLE2 *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_MIB_IF_TABLE2 *,void (*)(void *),&void FreeMibTable(void *),wistd::integral_constant<unsigned __int64,0>,_MIB_IF_TABLE2 *,_MIB_IF_TABLE2 *,0,std::nullptr_t>>(&Table);
        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v58);
        return v20;
      }
      v22 = (*(__int64 (__fastcall **)(__int64, HSTRING, _QWORD))(*(_QWORD *)v58 + 104LL))(
              v58,
              string,
              v14->Table[v15].OnLinkPrefixLength);
      v23 = v22;
      if ( v22 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x14D,
          (unsigned int)"onecoreuap\\net\\ux\\mediamanagerbase\\lib\\categorybase.cpp",
          (const char *)(unsigned int)v22,
          v56);
        WindowsDeleteString(string);
        string = 0;
        v24 = AddressString;
        AddressString = 0;
        if ( v24 )
          LocalFree(v24);
        wil::details::unique_storage<wil::details::resource_policy<_MIB_IF_TABLE2 *,void (*)(void *),&void FreeMibTable(void *),wistd::integral_constant<unsigned __int64,0>,_MIB_IF_TABLE2 *,_MIB_IF_TABLE2 *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_MIB_IF_TABLE2 *,void (*)(void *),&void FreeMibTable(void *),wistd::integral_constant<unsigned __int64,0>,_MIB_IF_TABLE2 *,_MIB_IF_TABLE2 *,0,std::nullptr_t>>(&Table);
        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v58);
        return v23;
      }
      v12 = 1;
      WindowsDeleteString(string);
    }
    else
    {
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x149,
        (unsigned int)"onecoreuap\\net\\ux\\mediamanagerbase\\lib\\categorybase.cpp",
        (const char *)(unsigned int)v18,
        v56);
    }
    v25 = AddressString;
    AddressString = 0;
    if ( v25 )
      LocalFree(v25);
LABEL_36:
    ++v5;
  }
  if ( v12 )
  {
    hstringHeader.Reserved.Reserved1 = 0;
    v26 = v59;
    IpForwardTable2 = GetIpForwardTable2(v59, (PMIB_IPFORWARD_TABLE2 *)&hstringHeader);
    if ( IpForwardTable2 )
    {
      v28 = wil::details::in1diag3::Return_Win32(
              retaddr,
              (void *)0x157,
              (unsigned int)"onecoreuap\\net\\ux\\mediamanagerbase\\lib\\categorybase.cpp",
              (const char *)IpForwardTable2,
              v56);
      wil::details::unique_storage<wil::details::resource_policy<_MIB_IF_TABLE2 *,void (*)(void *),&void FreeMibTable(void *),wistd::integral_constant<unsigned __int64,0>,_MIB_IF_TABLE2 *,_MIB_IF_TABLE2 *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_MIB_IF_TABLE2 *,void (*)(void *),&void FreeMibTable(void *),wistd::integral_constant<unsigned __int64,0>,_MIB_IF_TABLE2 *,_MIB_IF_TABLE2 *,0,std::nullptr_t>>(&hstringHeader);
      wil::details::unique_storage<wil::details::resource_policy<_MIB_IF_TABLE2 *,void (*)(void *),&void FreeMibTable(void *),wistd::integral_constant<unsigned __int64,0>,_MIB_IF_TABLE2 *,_MIB_IF_TABLE2 *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_MIB_IF_TABLE2 *,void (*)(void *),&void FreeMibTable(void *),wistd::integral_constant<unsigned __int64,0>,_MIB_IF_TABLE2 *,_MIB_IF_TABLE2 *,0,std::nullptr_t>>(&Table);
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v58);
      return v28;
    }
    v29 = 0;
    while ( 2 )
    {
      Reserved1 = (char *)hstringHeader.Reserved.Reserved1;
      if ( v29 >= *(_DWORD *)hstringHeader.Reserved.Reserved1 )
      {
        wil::details::unique_storage<wil::details::resource_policy<_MIB_IF_TABLE2 *,void (*)(void *),&void FreeMibTable(void *),wistd::integral_constant<unsigned __int64,0>,_MIB_IF_TABLE2 *,_MIB_IF_TABLE2 *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_MIB_IF_TABLE2 *,void (*)(void *),&void FreeMibTable(void *),wistd::integral_constant<unsigned __int64,0>,_MIB_IF_TABLE2 *,_MIB_IF_TABLE2 *,0,std::nullptr_t>>(&hstringHeader);
        break;
      }
      v31 = 104LL * v29;
      if ( *(_DWORD *)((char *)hstringHeader.Reserved.Reserved1 + v31 + 16) == v62
        && *(_WORD *)((char *)hstringHeader.Reserved.Reserved1 + v31 + 52) == v26
        && !*((_BYTE *)hstringHeader.Reserved.Reserved1 + v31 + 48)
        && !*(_DWORD *)((char *)hstringHeader.Reserved.Reserved1 + v31 + 108) )
      {
        v32 = 22;
        if ( a2 != 4 )
          v32 = 65;
        AddressStringLength = v32;
        wil::make_unique_hlocal<unsigned short [0]>(&AddressString);
        if ( *(_WORD *)&Reserved1[v31 + 52] != 2 )
        {
          v34 = 0;
          if ( *(_WORD *)&Reserved1[v31 + 52] != 23 )
            goto LABEL_67;
          v38 = RtlIpv6AddressToStringExW(
                  (const struct in6_addr *)&Reserved1[v31 + 60],
                  *(_DWORD *)&Reserved1[v31 + 76],
                  0,
                  AddressString,
                  &AddressStringLength);
          v34 = v38 | 0x10000000;
          v35 = retaddr;
          if ( v38 < 0 )
          {
            v36 = 374;
LABEL_59:
            wil::details::in1diag3::_Log_Hr(
              v35,
              (void *)v36,
              (unsigned int)"onecoreuap\\net\\ux\\mediamanagerbase\\lib\\categorybase.cpp",
              (const char *)(unsigned int)v34,
              v56);
            goto LABEL_67;
          }
          v39 = AddressString;
          v40 = *AddressString - 58;
          if ( *AddressString == 58 )
          {
            v40 = AddressString[1] - 58;
            if ( AddressString[1] == 58 )
              v40 = AddressString[2];
          }
          if ( v40 )
            goto LABEL_67;
          AddressString = 0;
          if ( !v39 )
            goto LABEL_54;
          v41 = v39;
LABEL_66:
          LocalFree(v41);
          goto LABEL_54;
        }
        v33 = RtlIpv4AddressToStringExW(
                (const struct in_addr *)&Reserved1[v31 + 56],
                0,
                AddressString,
                &AddressStringLength);
        v34 = v33 | 0x10000000;
        v35 = retaddr;
        if ( v33 < 0 )
        {
          v36 = 363;
          goto LABEL_59;
        }
        v37 = AddressString;
        if ( !wcscmp_0(AddressString, L"0.0.0.0") )
        {
          AddressString = 0;
          if ( v37 )
            LocalFree(v37);
          goto LABEL_54;
        }
LABEL_67:
        if ( v34 >= 0 )
        {
          string = 0;
          WindowsDeleteString(0);
          string = 0;
          v42 = WindowsCreateString(AddressString, AddressStringLength, &string);
          v43 = v42;
          if ( v42 < 0 )
          {
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)0x17F,
              (unsigned int)"onecoreuap\\net\\ux\\mediamanagerbase\\lib\\categorybase.cpp",
              (const char *)(unsigned int)v42,
              v56);
            WindowsDeleteString(string);
            string = 0;
            v44 = AddressString;
            AddressString = 0;
            if ( v44 )
              LocalFree(v44);
            wil::details::unique_storage<wil::details::resource_policy<_MIB_IF_TABLE2 *,void (*)(void *),&void FreeMibTable(void *),wistd::integral_constant<unsigned __int64,0>,_MIB_IF_TABLE2 *,_MIB_IF_TABLE2 *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_MIB_IF_TABLE2 *,void (*)(void *),&void FreeMibTable(void *),wistd::integral_constant<unsigned __int64,0>,_MIB_IF_TABLE2 *,_MIB_IF_TABLE2 *,0,std::nullptr_t>>(&hstringHeader);
            wil::details::unique_storage<wil::details::resource_policy<_MIB_IF_TABLE2 *,void (*)(void *),&void FreeMibTable(void *),wistd::integral_constant<unsigned __int64,0>,_MIB_IF_TABLE2 *,_MIB_IF_TABLE2 *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_MIB_IF_TABLE2 *,void (*)(void *),&void FreeMibTable(void *),wistd::integral_constant<unsigned __int64,0>,_MIB_IF_TABLE2 *,_MIB_IF_TABLE2 *,0,std::nullptr_t>>(&Table);
            Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v58);
            return v43;
          }
          v45 = (*(__int64 (__fastcall **)(__int64, HSTRING, _QWORD))(*(_QWORD *)v58 + 120LL))(
                  v58,
                  string,
                  *(unsigned int *)&Reserved1[v31 + 92]);
          v46 = v45;
          if ( v45 < 0 )
          {
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)0x180,
              (unsigned int)"onecoreuap\\net\\ux\\mediamanagerbase\\lib\\categorybase.cpp",
              (const char *)(unsigned int)v45,
              v56);
            WindowsDeleteString(string);
            string = 0;
            v47 = AddressString;
            AddressString = 0;
            if ( v47 )
              LocalFree(v47);
            wil::details::unique_storage<wil::details::resource_policy<_MIB_IF_TABLE2 *,void (*)(void *),&void FreeMibTable(void *),wistd::integral_constant<unsigned __int64,0>,_MIB_IF_TABLE2 *,_MIB_IF_TABLE2 *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_MIB_IF_TABLE2 *,void (*)(void *),&void FreeMibTable(void *),wistd::integral_constant<unsigned __int64,0>,_MIB_IF_TABLE2 *,_MIB_IF_TABLE2 *,0,std::nullptr_t>>(&hstringHeader);
            wil::details::unique_storage<wil::details::resource_policy<_MIB_IF_TABLE2 *,void (*)(void *),&void FreeMibTable(void *),wistd::integral_constant<unsigned __int64,0>,_MIB_IF_TABLE2 *,_MIB_IF_TABLE2 *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_MIB_IF_TABLE2 *,void (*)(void *),&void FreeMibTable(void *),wistd::integral_constant<unsigned __int64,0>,_MIB_IF_TABLE2 *,_MIB_IF_TABLE2 *,0,std::nullptr_t>>(&Table);
            Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v58);
            return v46;
          }
          WindowsDeleteString(string);
        }
        else
        {
          wil::details::in1diag3::_Log_Hr(
            retaddr,
            (void *)0x17C,
            (unsigned int)"onecoreuap\\net\\ux\\mediamanagerbase\\lib\\categorybase.cpp",
            (const char *)(unsigned int)v34,
            v56);
        }
        v41 = AddressString;
        AddressString = 0;
        if ( v41 )
          goto LABEL_66;
LABEL_54:
        v26 = v59;
      }
      ++v29;
      continue;
    }
  }
  v3 = v65;
LABEL_82:
  TryGetInterfaceDnsServerView(&v64, &v67, a2);
  if ( v64 )
  {
    v62 = 0;
    v48 = (*(__int64 (__fastcall **)(__int64, unsigned int *))(*(_QWORD *)v64 + 56LL))(v64, &v62);
    v49 = v48;
    if ( v48 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x18E,
        (unsigned int)"onecoreuap\\net\\ux\\mediamanagerbase\\lib\\categorybase.cpp",
        (const char *)(unsigned int)v48,
        v56);
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v64);
      wil::details::unique_storage<wil::details::resource_policy<_MIB_IF_TABLE2 *,void (*)(void *),&void FreeMibTable(void *),wistd::integral_constant<unsigned __int64,0>,_MIB_IF_TABLE2 *,_MIB_IF_TABLE2 *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_MIB_IF_TABLE2 *,void (*)(void *),&void FreeMibTable(void *),wistd::integral_constant<unsigned __int64,0>,_MIB_IF_TABLE2 *,_MIB_IF_TABLE2 *,0,std::nullptr_t>>(&Table);
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v58);
      return v49;
    }
    for ( i = 0; i < v62; ++i )
    {
      memset(&hstringHeader, 0, sizeof(hstringHeader));
      v51 = (*(__int64 (__fastcall **)(__int64, _QWORD, HSTRING_HEADER *))(*(_QWORD *)v64 + 48LL))(
              v64,
              i,
              &hstringHeader);
      v52 = v51;
      if ( v51 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x192,
          (unsigned int)"onecoreuap\\net\\ux\\mediamanagerbase\\lib\\categorybase.cpp",
          (const char *)(unsigned int)v51,
          v56);
        FreeDnsServer((struct Windows::Networking::UX::DnsServer *)&hstringHeader);
        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v64);
        wil::details::unique_storage<wil::details::resource_policy<_MIB_IF_TABLE2 *,void (*)(void *),&void FreeMibTable(void *),wistd::integral_constant<unsigned __int64,0>,_MIB_IF_TABLE2 *,_MIB_IF_TABLE2 *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_MIB_IF_TABLE2 *,void (*)(void *),&void FreeMibTable(void *),wistd::integral_constant<unsigned __int64,0>,_MIB_IF_TABLE2 *,_MIB_IF_TABLE2 *,0,std::nullptr_t>>(&Table);
        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v58);
        return v52;
      }
      v53 = (*(__int64 (__fastcall **)(__int64, _QWORD, _QWORD, _QWORD))(*(_QWORD *)v58 + 144LL))(
              v58,
              *(_QWORD *)&hstringHeader.Reserved.Reserved2[8],
              *(_QWORD *)&hstringHeader.Reserved.Reserved2[16],
              *(unsigned int *)&hstringHeader.Reserved.Reserved2[4]);
      v54 = v53;
      if ( v53 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x194,
          (unsigned int)"onecoreuap\\net\\ux\\mediamanagerbase\\lib\\categorybase.cpp",
          (const char *)(unsigned int)v53,
          v56);
        FreeDnsServer((struct Windows::Networking::UX::DnsServer *)&hstringHeader);
        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v64);
        wil::details::unique_storage<wil::details::resource_policy<_MIB_IF_TABLE2 *,void (*)(void *),&void FreeMibTable(void *),wistd::integral_constant<unsigned __int64,0>,_MIB_IF_TABLE2 *,_MIB_IF_TABLE2 *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_MIB_IF_TABLE2 *,void (*)(void *),&void FreeMibTable(void *),wistd::integral_constant<unsigned __int64,0>,_MIB_IF_TABLE2 *,_MIB_IF_TABLE2 *,0,std::nullptr_t>>(&Table);
        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v58);
        return v54;
      }
      FreeDnsServer((struct Windows::Networking::UX::DnsServer *)&hstringHeader);
    }
    v3 = v65;
  }
  v55 = v58;
  if ( v58 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v58 + 8LL))(v58);
    v55 = v58;
  }
  *v3 = v55;
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v64);
  wil::details::unique_storage<wil::details::resource_policy<_MIB_IF_TABLE2 *,void (*)(void *),&void FreeMibTable(void *),wistd::integral_constant<unsigned __int64,0>,_MIB_IF_TABLE2 *,_MIB_IF_TABLE2 *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_MIB_IF_TABLE2 *,void (*)(void *),&void FreeMibTable(void *),wistd::integral_constant<unsigned __int64,0>,_MIB_IF_TABLE2 *,_MIB_IF_TABLE2 *,0,std::nullptr_t>>(&Table);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v58);
  return 0;
}

```

## disassembly

```asm
0x18003e424  push    rbx
0x18003e426  push    rsi
0x18003e427  push    rdi
0x18003e428  push    r12
0x18003e42a  push    r13
0x18003e42c  push    r14
0x18003e42e  push    r15
0x18003e430  sub     rsp, 0B0h
0x18003e437  mov     rax, cs:__security_cookie
0x18003e43e  xor     rax, rsp
0x18003e441  mov     [rsp+0E8h+var_48], rax
0x18003e449  mov     r14, r8
0x18003e44c  mov     [rsp+0E8h+var_80], r8
0x18003e451  mov     r13d, edx
0x18003e454  xor     r15d, r15d
0x18003e457  mov     [r8], r15
0x18003e45a  lea     esi, [r15+2]
0x18003e45e  lea     eax, [rsi+15h]
0x18003e461  cmp     edx, 4
0x18003e464  cmovnz  si, ax
0x18003e468  mov     [rsp+0E8h+var_A8], esi
0x18003e46c  mov     [rsp+0E8h+var_B0], r15
0x18003e471  mov     rdx, rcx; struct _GUID *
0x18003e474  lea     rcx, [rsp+0E8h+hstringHeader]; retstr
0x18003e479  call    ?_GetActualInterfaceGuid@CategoryBase@Internal@UX@Networking@Windows@@CA?AU_GUID@@AEBU6@@Z; Windows::Networking::UX::Internal::CategoryBase::_GetActualInterfaceGuid(_GUID const &)
0x18003e47e  movups  xmm0, xmmword ptr [rax]
0x18003e481  movdqu  xmmword ptr [rsp+0E8h+var_58.Data1], xmm0
0x18003e48a  lea     rcx, [rsp+0E8h+var_58]; struct _GUID *
0x18003e492  call    ?_ConvertInterfaceGuidToIndex@CategoryBase@Internal@UX@Networking@Windows@@CAKAEBU_GUID@@@Z; Windows::Networking::UX::Internal::CategoryBase::_ConvertInterfaceGuidToIndex(_GUID const &)
0x18003e497  mov     [rsp+0E8h+var_94], eax
0x18003e49b  lea     r9, [rsp+0E8h+hstringHeader]; string
0x18003e4a0  lea     r8, [rsp+0E8h+hstringHeader.Reserved+8]; hstringHeader
0x18003e4a5  lea     edx, [r15+24h]; length
0x18003e4a9  lea     rcx, ?RuntimeClass_Windows_Networking_UX_StaticIpConfig@@3QBGB; "Windows.Networking.UX.StaticIpConfig"
0x18003e4b0  call    cs:__imp_WindowsCreateStringReference
0x18003e4b6  test    eax, eax
0x18003e4b8  jns     short loc_18003E4CF
0x18003e4ba  xor     r9d, r9d; lpArguments
0x18003e4bd  xor     r8d, r8d; nNumberOfArguments
0x18003e4c0  lea     edx, [r15+1]; dwExceptionFlags
0x18003e4c4  mov     ecx, 0C000000Dh; dwExceptionCode
0x18003e4c9  call    cs:__imp_RaiseException
0x18003e4cf  lea     rdx, [rsp+0E8h+var_B0]
0x18003e4d4  mov     rcx, qword ptr [rsp+0E8h+hstringHeader.Reserved]
0x18003e4d9  call    ??$ActivateInstance@V?$ComPtr@UIStaticIpConfig@UX@Networking@Windows@@@WRL@Microsoft@@@Foundation@Windows@@YAJPEAUHSTRING__@@V?$ComPtrRef@V?$ComPtr@UIStaticIpConfig@UX@Networking@Windows@@@WRL@Microsoft@@@Details@WRL@Microsoft@@@Z; Windows::Foundation::ActivateInstance<Microsoft::WRL::ComPtr<Windows::Networking::UX::IStaticIpConfig>>(HSTRING__ *,Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::Networking::UX::IStaticIpConfig>>)
0x18003e4de  mov     ebx, eax
0x18003e4e0  test    eax, eax
0x18003e4e2  jns     short loc_18003E512
0x18003e4e4  mov     rcx, [rsp+0E8h]; this
0x18003e4ec  mov     r9d, eax; char *
0x18003e4ef  lea     r8, aOnecoreuapNetU_9; "onecoreuap\\net\\ux\\mediamanagerbase\\"...
0x18003e4f6  mov     edx, 128h; void *
0x18003e4fb  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003e500  nop
0x18003e501  lea     rcx, [rsp+0E8h+var_B0]
0x18003e506  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18003e50b  mov     eax, ebx
0x18003e50d  jmp     loc_18003ECF5
0x18003e512  mov     rcx, [rsp+0E8h+var_B0]
0x18003e517  mov     rax, [rcx]
0x18003e51a  mov     edx, r13d
0x18003e51d  mov     rax, [rax+38h]
0x18003e521  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003e526  mov     ebx, eax
0x18003e528  test    eax, eax
0x18003e52a  jns     short loc_18003E55A
0x18003e52c  mov     rcx, [rsp+0E8h]; this
0x18003e534  mov     r9d, eax; char *
0x18003e537  lea     r8, aOnecoreuapNetU_9; "onecoreuap\\net\\ux\\mediamanagerbase\\"...
0x18003e53e  mov     edx, 129h; void *
0x18003e543  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003e548  nop
0x18003e549  lea     rcx, [rsp+0E8h+var_B0]
0x18003e54e  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18003e553  mov     eax, ebx
0x18003e555  jmp     loc_18003ECF5
0x18003e55a  mov     [rsp+0E8h+Table], r15
0x18003e55f  xor     ecx, ecx; Family
0x18003e561  lea     rdx, [rsp+0E8h+Table]; Table
0x18003e566  call    cs:__imp_GetUnicastIpAddressTable
0x18003e56c  lea     rdi, aOnecoreuapNetU_9; "onecoreuap\\net\\ux\\mediamanagerbase\\"...
0x18003e573  test    eax, eax
0x18003e575  jnz     loc_18003EB1D
0x18003e57b  mov     r14b, r15b
0x18003e57e  lea     ecx, [rax+41h]
0x18003e581  mov     r12d, [rsp+0E8h+var_A8]
0x18003e586  mov     rbx, [rsp+0E8h+Table]
0x18003e58b  cmp     r15d, [rbx]
0x18003e58e  jnb     loc_18003E7B8
0x18003e594  mov     eax, r15d
0x18003e597  lea     rsi, [rax+rax*4]
0x18003e59b  shl     rsi, 4
0x18003e59f  mov     eax, [rsp+0E8h+var_94]
0x18003e5a3  cmp     [rsi+rbx+30h], eax
0x18003e5a7  jnz     loc_18003E7B0
0x18003e5ad  cmp     [rsi+rbx+8], r12w
0x18003e5b3  jnz     loc_18003E7B0
0x18003e5b9  cmp     dword ptr [rsi+rbx+34h], 1
0x18003e5be  jnz     loc_18003E7B0
0x18003e5c4  cmp     dword ptr [rsi+rbx+38h], 1
0x18003e5c9  jnz     loc_18003E7B0
0x18003e5cf  mov     edx, 16h
0x18003e5d4  cmp     r13d, 4
0x18003e5d8  cmovnz  edx, ecx
0x18003e5db  mov     [rsp+0E8h+AddressStringLength], edx
0x18003e5df  lea     rcx, [rsp+0E8h+AddressString]
0x18003e5e4  call    ??$make_unique_hlocal@$$BY0A@G@wil@@YA?AV?$unique_ptr@$$BY0A@GU?$function_deleter@P6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@Z@wil@@@wistd@@_K@Z; wil::make_unique_hlocal<ushort [0]>(unsigned __int64)
0x18003e5e9  nop
0x18003e5ea  mov     eax, 2
0x18003e5ef  cmp     [rsi+rbx+8], ax
0x18003e5f4  jnz     short loc_18003E611
0x18003e5f6  xor     edx, edx; Port
0x18003e5f8  lea     rcx, [rbx+0Ch]
0x18003e5fc  add     rcx, rsi; Address
0x18003e5ff  lea     r9, [rsp+0E8h+AddressStringLength]; AddressStringLength
0x18003e604  mov     r8, [rsp+0E8h+AddressString]; AddressString
0x18003e609  call    cs:__imp_RtlIpv4AddressToStringExW
0x18003e60f  jmp     short loc_18003E640
0x18003e611  xor     eax, eax
0x18003e613  lea     ecx, [rax+17h]
0x18003e616  cmp     [rsi+rbx+8], cx
0x18003e61b  jnz     short loc_18003E644
0x18003e61d  xor     r8d, r8d; Port
0x18003e620  lea     rcx, [rbx+10h]
0x18003e624  add     rcx, rsi; Address
0x18003e627  lea     rax, [rsp+0E8h+AddressStringLength]
0x18003e62c  mov     qword ptr [rsp+0E8h+var_C8], rax; int
0x18003e631  mov     r9, [rsp+0E8h+AddressString]; AddressString
0x18003e636  mov     edx, [rsi+rbx+20h]; ScopeId
0x18003e63a  call    cs:__imp_RtlIpv6AddressToStringExW
0x18003e640  bts     eax, 1Ch
0x18003e644  mov     rcx, [rsp+0E8h]; this
0x18003e64c  test    eax, eax
0x18003e64e  jns     short loc_18003E665
0x18003e650  mov     r9d, eax; char *
0x18003e653  mov     r8, rdi; unsigned int
0x18003e656  mov     edx, 149h; void *
0x18003e65b  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18003e660  jmp     loc_18003E792
0x18003e665  mov     [rsp+0E8h+string], 0
0x18003e66e  xor     ecx, ecx; string
0x18003e670  call    cs:__imp_WindowsDeleteString
0x18003e676  mov     [rsp+0E8h+string], 0
0x18003e67f  lea     r8, [rsp+0E8h+string]; string
0x18003e684  mov     edx, [rsp+0E8h+AddressStringLength]; length
0x18003e688  mov     rcx, [rsp+0E8h+AddressString]; sourceString
0x18003e68d  call    cs:__imp_WindowsCreateString
0x18003e693  mov     r14d, eax
0x18003e696  test    eax, eax
0x18003e698  jns     short loc_18003E6FE
0x18003e69a  mov     rcx, [rsp+0E8h]; this
0x18003e6a2  mov     r9d, eax; char *
0x18003e6a5  mov     r8, rdi; unsigned int
0x18003e6a8  mov     edx, 14Ch; void *
0x18003e6ad  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003e6b2  nop
0x18003e6b3  mov     rcx, [rsp+0E8h+string]; string
0x18003e6b8  call    cs:__imp_WindowsDeleteString
0x18003e6be  mov     [rsp+0E8h+string], 0
0x18003e6c7  mov     rcx, [rsp+0E8h+AddressString]; hMem
0x18003e6cc  mov     [rsp+0E8h+AddressString], 0
0x18003e6d5  test    rcx, rcx
0x18003e6d8  jz      short loc_18003E6E1
0x18003e6da  call    cs:__imp_LocalFree
0x18003e6e0  nop
0x18003e6e1  lea     rcx, [rsp+0E8h+Table]
0x18003e6e6  call    ??1?$unique_storage@U?$resource_policy@PEAU_MIB_IF_TABLE2@@P6AXPEAX@Z$1?FreeMibTable@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_MIB_IF_TABLE2 *,void (*)(void *),&FreeMibTable(void *),wistd::integral_constant<unsigned __int64,0>,_MIB_IF_TABLE2 *,_MIB_IF_TABLE2 *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_MIB_IF_TABLE2 *,void (*)(void *),&FreeMibTable(void *),wistd::integral_constant<unsigned __int64,0>,_MIB_IF_TABLE2 *,_MIB_IF_TABLE2 *,0,std::nullptr_t>>(void)
0x18003e6eb  nop
0x18003e6ec  lea     rcx, [rsp+0E8h+var_B0]
0x18003e6f1  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18003e6f6  mov     eax, r14d
0x18003e6f9  jmp     loc_18003ECF5
0x18003e6fe  mov     rcx, [rsp+0E8h+var_B0]
0x18003e703  mov     rax, [rcx]
0x18003e706  movzx   r8d, byte ptr [rsi+rbx+44h]
0x18003e70c  mov     rdx, [rsp+0E8h+string]
0x18003e711  mov     rax, [rax+68h]
0x18003e715  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003e71a  mov     ebx, eax
0x18003e71c  test    eax, eax
0x18003e71e  jns     short loc_18003E783
0x18003e720  mov     rcx, [rsp+0E8h]; this
0x18003e728  mov     r9d, eax; char *
0x18003e72b  mov     r8, rdi; unsigned int
0x18003e72e  mov     edx, 14Dh; void *
0x18003e733  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003e738  nop
0x18003e739  mov     rcx, [rsp+0E8h+string]; string
0x18003e73e  call    cs:__imp_WindowsDeleteString
0x18003e744  mov     [rsp+0E8h+string], 0
0x18003e74d  mov     rcx, [rsp+0E8h+AddressString]; hMem
0x18003e752  mov     [rsp+0E8h+AddressString], 0
0x18003e75b  test    rcx, rcx
0x18003e75e  jz      short loc_18003E767
0x18003e760  call    cs:__imp_LocalFree
0x18003e766  nop
0x18003e767  lea     rcx, [rsp+0E8h+Table]
0x18003e76c  call    ??1?$unique_storage@U?$resource_policy@PEAU_MIB_IF_TABLE2@@P6AXPEAX@Z$1?FreeMibTable@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_MIB_IF_TABLE2 *,void (*)(void *),&FreeMibTable(void *),wistd::integral_constant<unsigned __int64,0>,_MIB_IF_TABLE2 *,_MIB_IF_TABLE2 *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_MIB_IF_TABLE2 *,void (*)(void *),&FreeMibTable(void *),wistd::integral_constant<unsigned __int64,0>,_MIB_IF_TABLE2 *,_MIB_IF_TABLE2 *,0,std::nullptr_t>>(void)
0x18003e771  nop
0x18003e772  lea     rcx, [rsp+0E8h+var_B0]
0x18003e777  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18003e77c  mov     eax, ebx
0x18003e77e  jmp     loc_18003ECF5
0x18003e783  mov     r14b, 1
0x18003e786  mov     rcx, [rsp+0E8h+string]; string
0x18003e78b  call    cs:__imp_WindowsDeleteString
0x18003e791  nop
0x18003e792  mov     rcx, [rsp+0E8h+AddressString]; hMem
0x18003e797  mov     [rsp+0E8h+AddressString], 0
0x18003e7a0  test    rcx, rcx
0x18003e7a3  jz      short loc_18003E7AB
0x18003e7a5  call    cs:__imp_LocalFree
0x18003e7ab  mov     ecx, 41h ; 'A'
0x18003e7b0  inc     r15d
0x18003e7b3  jmp     loc_18003E586
0x18003e7b8  xor     r15d, r15d
0x18003e7bb  test    r14b, r14b
0x18003e7be  jz      loc_18003EB18
0x18003e7c4  mov     qword ptr [rsp+0E8h+hstringHeader.Reserved], r15
0x18003e7c9  lea     rdx, [rsp+0E8h+hstringHeader]; Table
0x18003e7ce  mov     esi, [rsp+0E8h+var_A8]
0x18003e7d2  movzx   ecx, si; Family
0x18003e7d5  call    cs:__imp_GetIpForwardTable2
0x18003e7db  test    eax, eax
0x18003e7dd  jz      short loc_18003E820
0x18003e7df  mov     rcx, [rsp+0E8h]; this
0x18003e7e7  mov     r9d, eax; char *
0x18003e7ea  mov     r8, rdi; unsigned int
0x18003e7ed  mov     edx, 157h; void *
0x18003e7f2  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x18003e7f7  mov     ebx, eax
0x18003e7f9  lea     rcx, [rsp+0E8h+hstringHeader]
0x18003e7fe  call    ??1?$unique_storage@U?$resource_policy@PEAU_MIB_IF_TABLE2@@P6AXPEAX@Z$1?FreeMibTable@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_MIB_IF_TABLE2 *,void (*)(void *),&FreeMibTable(void *),wistd::integral_constant<unsigned __int64,0>,_MIB_IF_TABLE2 *,_MIB_IF_TABLE2 *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_MIB_IF_TABLE2 *,void (*)(void *),&FreeMibTable(void *),wistd::integral_constant<unsigned __int64,0>,_MIB_IF_TABLE2 *,_MIB_IF_TABLE2 *,0,std::nullptr_t>>(void)
0x18003e803  nop
0x18003e804  lea     rcx, [rsp+0E8h+Table]
0x18003e809  call    ??1?$unique_storage@U?$resource_policy@PEAU_MIB_IF_TABLE2@@P6AXPEAX@Z$1?FreeMibTable@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_MIB_IF_TABLE2 *,void (*)(void *),&FreeMibTable(void *),wistd::integral_constant<unsigned __int64,0>,_MIB_IF_TABLE2 *,_MIB_IF_TABLE2 *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_MIB_IF_TABLE2 *,void (*)(void *),&FreeMibTable(void *),wistd::integral_constant<unsigned __int64,0>,_MIB_IF_TABLE2 *,_MIB_IF_TABLE2 *,0,std::nullptr_t>>(void)
0x18003e80e  nop
0x18003e80f  lea     rcx, [rsp+0E8h+var_B0]
0x18003e814  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18003e819  mov     eax, ebx
0x18003e81b  jmp     loc_18003ECF5
0x18003e820  mov     r12d, r15d
0x18003e823  mov     rbx, qword ptr [rsp+0E8h+hstringHeader.Reserved]
0x18003e828  cmp     r12d, [rbx]
0x18003e82b  jnb     loc_18003EB0E
0x18003e831  mov     eax, r12d
0x18003e834  imul    r14, rax, 68h ; 'h'
0x18003e838  mov     eax, [rsp+0E8h+var_94]
0x18003e83c  cmp     [r14+rbx+10h], eax
0x18003e841  jnz     loc_18003E903
0x18003e847  cmp     [r14+rbx+34h], si
0x18003e84d  jnz     loc_18003E903
0x18003e853  cmp     [r14+rbx+30h], r15b
0x18003e858  jnz     loc_18003E903
0x18003e85e  cmp     [r14+rbx+6Ch], r15d
0x18003e863  jnz     loc_18003E903
0x18003e869  mov     edx, 16h
0x18003e86e  cmp     r13d, 4
0x18003e872  lea     ecx, [rdx+2Bh]
0x18003e875  cmovnz  edx, ecx
0x18003e878  mov     [rsp+0E8h+AddressStringLength], edx
0x18003e87c  lea     rcx, [rsp+0E8h+AddressString]
0x18003e881  call    ??$make_unique_hlocal@$$BY0A@G@wil@@YA?AV?$unique_ptr@$$BY0A@GU?$function_deleter@P6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@Z@wil@@@wistd@@_K@Z; wil::make_unique_hlocal<ushort [0]>(unsigned __int64)
0x18003e886  nop
0x18003e887  mov     eax, 2
0x18003e88c  cmp     [r14+rbx+34h], ax
0x18003e892  jnz     short loc_18003E90B
0x18003e894  xor     edx, edx; Port
0x18003e896  lea     rcx, [rbx+38h]
0x18003e89a  add     rcx, r14; Address
0x18003e89d  lea     r9, [rsp+0E8h+AddressStringLength]; AddressStringLength
0x18003e8a2  mov     r8, [rsp+0E8h+AddressString]; AddressString
0x18003e8a7  call    cs:__imp_RtlIpv4AddressToStringExW
0x18003e8ad  mov     esi, eax
0x18003e8af  or      esi, 10000000h
0x18003e8b5  mov     rcx, [rsp+0E8h]
0x18003e8bd  jge     short loc_18003E8C9
0x18003e8bf  mov     edx, 16Bh
0x18003e8c4  jmp     loc_18003E95A
0x18003e8c9  lea     rdx, a0000; "0.0.0.0"
0x18003e8d0  mov     r15, [rsp+0E8h+AddressString]
0x18003e8d5  mov     rcx, r15; String1
0x18003e8d8  call    wcscmp_0
0x18003e8dd  test    eax, eax
0x18003e8df  jnz     loc_18003E9AD
0x18003e8e5  mov     [rsp+0E8h+AddressString], 0
0x18003e8ee  test    r15, r15
0x18003e8f1  jz      short loc_18003E8FC
0x18003e8f3  mov     rcx, r15; hMem
0x18003e8f6  call    cs:__imp_LocalFree
0x18003e8fc  xor     r15d, r15d
0x18003e8ff  mov     esi, [rsp+0E8h+var_A8]
0x18003e903  inc     r12d
0x18003e906  jmp     loc_18003E823
0x18003e90b  mov     esi, r15d
0x18003e90e  mov     eax, 17h
0x18003e913  cmp     [r14+rbx+34h], ax
0x18003e919  jnz     loc_18003E9B0
0x18003e91f  xor     r8d, r8d; Port
0x18003e922  lea     rcx, [rbx+3Ch]
  ... truncated ...
```
