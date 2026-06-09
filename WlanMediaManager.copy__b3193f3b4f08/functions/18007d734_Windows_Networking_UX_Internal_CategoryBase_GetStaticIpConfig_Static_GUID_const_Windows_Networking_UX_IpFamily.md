# Windows::Networking::UX::Internal::CategoryBase::GetStaticIpConfig_Static(_GUID const &,Windows::Networking::UX::IpFamily,Windows::Networking::UX::IStaticIpConfig * *)

- ea: `0x18007d734`
- end: `0x18007dffd`
- name: `?GetStaticIpConfig_Static@CategoryBase@Internal@UX@Networking@Windows@@SAJAEBU_GUID@@W4IpFamily@345@PEAPEAUIStaticIpConfig@345@@Z`
- size: `2249`
- prototype: ``
- caller_count: `2`
- callee_count: `16`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x180026c40`
- `0x18007e920`

## callees

- `0x180003ed0`
- `0x180008e30`
- `0x1800097b4`
- `0x18001668c`
- `0x18001b230`
- `0x18005b728`
- `0x18005b774`
- `0x18007d61c`
- `0x18007d714`
- `0x18007d734`
- `0x18007e29c`
- `0x18007e54c`
- `0x180081e5c`
- `0x1800871f0`
- `0x18008941c`
- `0x18008e010`

## import_xrefs

- `ntdll!RtlIpv6AddressToStringExW` at `0x18007d91e`
- `ntdll!RtlIpv6AddressToStringExW` at `0x18007dc21`
- `ntdll!RtlIpv6AddressToStringExW` at `0x18007d91e`
- `ntdll!RtlIpv6AddressToStringExW` at `0x18007dc21`
- `ntdll!RtlIpv4AddressToStringExW` at `0x18007d8ed`
- `ntdll!RtlIpv4AddressToStringExW` at `0x18007db8b`
- `ntdll!RtlIpv4AddressToStringExW` at `0x18007d8ed`
- `ntdll!RtlIpv4AddressToStringExW` at `0x18007db8b`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18007d9be`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18007da44`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18007da89`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18007dbda`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18007dc86`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18007dd19`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18007dda0`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18007d9be`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18007da44`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18007da89`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18007dbda`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18007dc86`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18007dd19`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18007dda0`
- `IPHLPAPI!GetIpForwardTable2` at `0x18007dab9`
- `IPHLPAPI!GetIpForwardTable2` at `0x18007dab9`
- `IPHLPAPI!GetUnicastIpAddressTable` at `0x18007d84a`
- `IPHLPAPI!GetUnicastIpAddressTable` at `0x18007d84a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18007d954`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18007d99c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18007da22`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18007da6f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18007dcbc`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18007dcff`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18007dd86`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18007ddd3`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18007d954`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18007d99c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18007da22`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18007da6f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18007dcbc`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18007dcff`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18007dd86`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18007ddd3`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x18007d971`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x18007dcd5`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x18007d971`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x18007dcd5`

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
  const unsigned __int16 (*v7)[37]; // rdx
  _QWORD *v8; // rax
  int v9; // eax
  unsigned int v10; // ebx
  __int64 v11; // rdx
  __int64 v12; // r8
  int v14; // eax
  unsigned int v15; // ebx
  __int64 v16; // rdx
  __int64 v17; // r8
  char v18; // r14
  __int16 v19; // r12
  PMIB_UNICASTIPADDRESS_TABLE v20; // rbx
  unsigned __int64 v21; // rsi
  ULONG v22; // edx
  LONG v23; // eax
  int v24; // eax
  HRESULT v25; // eax
  unsigned int v26; // r14d
  PWSTR v27; // rcx
  __int64 v28; // rdx
  __int64 v29; // r8
  int v30; // eax
  unsigned int v31; // ebx
  PWSTR v32; // rcx
  __int64 v33; // rdx
  __int64 v34; // r8
  PWSTR v35; // rcx
  __int16 v36; // si
  unsigned int IpForwardTable2; // eax
  unsigned int v38; // ebx
  __int64 v39; // rdx
  __int64 v40; // r8
  ULONG v41; // r12d
  PMIB_IPFORWARD_TABLE2 v42; // rbx
  unsigned __int64 v43; // r14
  ULONG v44; // edx
  LONG v45; // eax
  int v46; // esi
  wil::details::in1diag3 *v47; // rcx
  __int64 v48; // rdx
  PWSTR v49; // r15
  LONG v50; // eax
  PWSTR v51; // r8
  int v52; // ecx
  PWSTR v53; // rcx
  HRESULT v54; // eax
  unsigned int v55; // esi
  PWSTR v56; // rcx
  __int64 v57; // rdx
  __int64 v58; // r8
  int v59; // eax
  unsigned int v60; // ebx
  PWSTR v61; // rcx
  __int64 v62; // rdx
  __int64 v63; // r8
  __int64 v64; // rdx
  __int64 v65; // r8
  int v66; // eax
  unsigned int v67; // ebx
  __int64 v68; // rdx
  __int64 v69; // r8
  __int64 v70; // rdx
  __int64 v71; // r8
  unsigned int i; // ebx
  int v73; // eax
  unsigned int v74; // esi
  __int64 v75; // rdx
  __int64 v76; // r8
  __int64 v77; // rdx
  __int64 v78; // r8
  int v79; // eax
  unsigned int v80; // esi
  __int64 v81; // rdx
  __int64 v82; // r8
  __int64 v83; // rdx
  __int64 v84; // r8
  __int64 v85; // rcx
  __int64 v86; // rdx
  __int64 v87; // r8
  unsigned int v88; // [rsp+20h] [rbp-C8h]
  PWSTR AddressString; // [rsp+30h] [rbp-B8h] BYREF
  __int64 v90; // [rsp+38h] [rbp-B0h] BYREF
  int v91; // [rsp+40h] [rbp-A8h]
  HSTRING string; // [rsp+48h] [rbp-A0h] BYREF
  ULONG AddressStringLength; // [rsp+50h] [rbp-98h] BYREF
  unsigned int v94; // [rsp+54h] [rbp-94h] BYREF
  PMIB_UNICASTIPADDRESS_TABLE Table; // [rsp+58h] [rbp-90h] BYREF
  __int64 v96; // [rsp+60h] [rbp-88h] BYREF
  _QWORD *v97; // [rsp+68h] [rbp-80h]
  PMIB_IPFORWARD_TABLE2 v98[2]; // [rsp+70h] [rbp-78h] BYREF
  __int64 v99; // [rsp+80h] [rbp-68h]
  struct _GUID v100; // [rsp+90h] [rbp-58h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+E8h] [rbp+0h]

  v3 = a3;
  v97 = a3;
  v5 = 0;
  *a3 = 0;
  v6 = 2;
  if ( a2 != 4 )
    LOWORD(v6) = 23;
  v91 = v6;
  v90 = 0;
  v100 = *Windows::Networking::UX::Internal::CategoryBase::_GetActualInterfaceGuid((struct _GUID *)v98, a1);
  v94 = Windows::Networking::UX::Internal::CategoryBase::_ConvertInterfaceGuidToIndex(&v100);
  v8 = (_QWORD *)Windows::Internal::StringReference::StringReference((HSTRING *)v98, v7);
  v9 = Windows::Foundation::ActivateInstance<Microsoft::WRL::ComPtr<Windows::Networking::UX::IStaticIpConfig>>(
         *v8,
         &v90);
  v10 = v9;
  if ( v9 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x128,
      (unsigned int)"onecoreuap\\net\\ux\\mediamanagerbase\\lib\\categorybase.cpp",
      (const char *)(unsigned int)v9,
      v88);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v90, v11, v12);
    return v10;
  }
  v14 = (*(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v90 + 56LL))(v90, a2);
  v15 = v14;
  if ( v14 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x129,
      (unsigned int)"onecoreuap\\net\\ux\\mediamanagerbase\\lib\\categorybase.cpp",
      (const char *)(unsigned int)v14,
      v88);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v90, v16, v17);
    return v15;
  }
  Table = 0;
  if ( GetUnicastIpAddressTable(0, &Table) )
    goto LABEL_80;
  v18 = 0;
  v19 = v91;
  while ( 1 )
  {
    v20 = Table;
    if ( v5 >= Table->NumEntries )
      break;
    v21 = v5;
    if ( Table->Table[v21].InterfaceIndex != v94
      || Table->Table[v21].Address.Ipv4.sin_family != v19
      || Table->Table[v21].PrefixOrigin != IpPrefixOriginManual
      || Table->Table[v21].SuffixOrigin != NlsoManual )
    {
      goto LABEL_34;
    }
    v22 = 22;
    if ( a2 != 4 )
      v22 = 65;
    AddressStringLength = v22;
    wil::make_unique_hlocal<unsigned short [0]>(&AddressString);
    if ( v20->Table[v21].Address.Ipv4.sin_family == 2 )
    {
      v23 = RtlIpv4AddressToStringExW(&v20->Table[v21].Address.Ipv4.sin_addr, 0, AddressString, &AddressStringLength);
LABEL_20:
      v24 = v23 | 0x10000000;
      goto LABEL_21;
    }
    v24 = 0;
    if ( v20->Table[v21].Address.Ipv4.sin_family == 23 )
    {
      v23 = RtlIpv6AddressToStringExW(
              &v20->Table[v21].Address.Ipv6.sin6_addr,
              v20->Table[v21].Address.Ipv6.sin6_scope_id,
              0,
              AddressString,
              &AddressStringLength);
      goto LABEL_20;
    }
LABEL_21:
    if ( v24 >= 0 )
    {
      string = 0;
      WindowsDeleteString(0);
      string = 0;
      v25 = WindowsCreateString(AddressString, AddressStringLength, &string);
      v26 = v25;
      if ( v25 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x14C,
          (unsigned int)"onecoreuap\\net\\ux\\mediamanagerbase\\lib\\categorybase.cpp",
          (const char *)(unsigned int)v25,
          v88);
        WindowsDeleteString(string);
        string = 0;
        v27 = AddressString;
        AddressString = 0;
        if ( v27 )
          LocalFree(v27);
        wil::details::unique_storage<wil::details::resource_policy<_MIB_IF_TABLE2 *,void (*)(void *),&void FreeMibTable(void *),wistd::integral_constant<unsigned __int64,0>,_MIB_IF_TABLE2 *,_MIB_IF_TABLE2 *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_MIB_IF_TABLE2 *,void (*)(void *),&void FreeMibTable(void *),wistd::integral_constant<unsigned __int64,0>,_MIB_IF_TABLE2 *,_MIB_IF_TABLE2 *,0,std::nullptr_t>>(&Table);
        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v90, v28, v29);
        return v26;
      }
      v30 = (*(__int64 (__fastcall **)(__int64, HSTRING, _QWORD))(*(_QWORD *)v90 + 104LL))(
              v90,
              string,
              v20->Table[v21].OnLinkPrefixLength);
      v31 = v30;
      if ( v30 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x14D,
          (unsigned int)"onecoreuap\\net\\ux\\mediamanagerbase\\lib\\categorybase.cpp",
          (const char *)(unsigned int)v30,
          v88);
        WindowsDeleteString(string);
        string = 0;
        v32 = AddressString;
        AddressString = 0;
        if ( v32 )
          LocalFree(v32);
        wil::details::unique_storage<wil::details::resource_policy<_MIB_IF_TABLE2 *,void (*)(void *),&void FreeMibTable(void *),wistd::integral_constant<unsigned __int64,0>,_MIB_IF_TABLE2 *,_MIB_IF_TABLE2 *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_MIB_IF_TABLE2 *,void (*)(void *),&void FreeMibTable(void *),wistd::integral_constant<unsigned __int64,0>,_MIB_IF_TABLE2 *,_MIB_IF_TABLE2 *,0,std::nullptr_t>>(&Table);
        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v90, v33, v34);
        return v31;
      }
      v18 = 1;
      WindowsDeleteString(string);
    }
    else
    {
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x149,
        (unsigned int)"onecoreuap\\net\\ux\\mediamanagerbase\\lib\\categorybase.cpp",
        (const char *)(unsigned int)v24,
        v88);
    }
    v35 = AddressString;
    AddressString = 0;
    if ( v35 )
      LocalFree(v35);
LABEL_34:
    ++v5;
  }
  if ( v18 )
  {
    v98[0] = 0;
    v36 = v91;
    IpForwardTable2 = GetIpForwardTable2(v91, v98);
    if ( IpForwardTable2 )
    {
      v38 = wil::details::in1diag3::Return_Win32(
              retaddr,
              (void *)0x157,
              (unsigned int)"onecoreuap\\net\\ux\\mediamanagerbase\\lib\\categorybase.cpp",
              (const char *)IpForwardTable2,
              v88);
      wil::details::unique_storage<wil::details::resource_policy<_MIB_IF_TABLE2 *,void (*)(void *),&void FreeMibTable(void *),wistd::integral_constant<unsigned __int64,0>,_MIB_IF_TABLE2 *,_MIB_IF_TABLE2 *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_MIB_IF_TABLE2 *,void (*)(void *),&void FreeMibTable(void *),wistd::integral_constant<unsigned __int64,0>,_MIB_IF_TABLE2 *,_MIB_IF_TABLE2 *,0,std::nullptr_t>>(v98);
      wil::details::unique_storage<wil::details::resource_policy<_MIB_IF_TABLE2 *,void (*)(void *),&void FreeMibTable(void *),wistd::integral_constant<unsigned __int64,0>,_MIB_IF_TABLE2 *,_MIB_IF_TABLE2 *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_MIB_IF_TABLE2 *,void (*)(void *),&void FreeMibTable(void *),wistd::integral_constant<unsigned __int64,0>,_MIB_IF_TABLE2 *,_MIB_IF_TABLE2 *,0,std::nullptr_t>>(&Table);
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v90, v39, v40);
      return v38;
    }
    v41 = 0;
    while ( 2 )
    {
      v42 = v98[0];
      if ( v41 >= v98[0]->NumEntries )
      {
        wil::details::unique_storage<wil::details::resource_policy<_MIB_IF_TABLE2 *,void (*)(void *),&void FreeMibTable(void *),wistd::integral_constant<unsigned __int64,0>,_MIB_IF_TABLE2 *,_MIB_IF_TABLE2 *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_MIB_IF_TABLE2 *,void (*)(void *),&void FreeMibTable(void *),wistd::integral_constant<unsigned __int64,0>,_MIB_IF_TABLE2 *,_MIB_IF_TABLE2 *,0,std::nullptr_t>>(v98);
        break;
      }
      v43 = v41;
      if ( v98[0]->Table[v43].InterfaceIndex == v94
        && v98[0]->Table[v43].NextHop.Ipv4.sin_family == v36
        && !v98[0]->Table[v43].DestinationPrefix.PrefixLength
        && v98[0]->Table[v43].Origin == NlroManual )
      {
        v44 = 22;
        if ( a2 != 4 )
          v44 = 65;
        AddressStringLength = v44;
        wil::make_unique_hlocal<unsigned short [0]>(&AddressString);
        if ( v42->Table[v43].NextHop.Ipv4.sin_family != 2 )
        {
          v46 = 0;
          if ( v42->Table[v43].NextHop.Ipv4.sin_family != 23 )
            goto LABEL_65;
          v50 = RtlIpv6AddressToStringExW(
                  &v42->Table[v43].NextHop.Ipv6.sin6_addr,
                  v42->Table[v43].NextHop.Ipv6.sin6_scope_id,
                  0,
                  AddressString,
                  &AddressStringLength);
          v46 = v50 | 0x10000000;
          v47 = retaddr;
          if ( v50 < 0 )
          {
            v48 = 374;
LABEL_57:
            wil::details::in1diag3::_Log_Hr(
              v47,
              (void *)v48,
              (unsigned int)"onecoreuap\\net\\ux\\mediamanagerbase\\lib\\categorybase.cpp",
              (const char *)(unsigned int)v46,
              v88);
            goto LABEL_65;
          }
          v51 = AddressString;
          v52 = *AddressString - 58;
          if ( *AddressString == 58 )
          {
            v52 = AddressString[1] - 58;
            if ( AddressString[1] == 58 )
              v52 = AddressString[2];
          }
          if ( v52 )
            goto LABEL_65;
          AddressString = 0;
          if ( !v51 )
            goto LABEL_52;
          v53 = v51;
LABEL_64:
          LocalFree(v53);
          goto LABEL_52;
        }
        v45 = RtlIpv4AddressToStringExW(&v42->Table[v43].NextHop.Ipv4.sin_addr, 0, AddressString, &AddressStringLength);
        v46 = v45 | 0x10000000;
        v47 = retaddr;
        if ( v45 < 0 )
        {
          v48 = 363;
          goto LABEL_57;
        }
        v49 = AddressString;
        if ( !wcscmp_0(AddressString, L"0.0.0.0") )
        {
          AddressString = 0;
          if ( v49 )
            LocalFree(v49);
          goto LABEL_52;
        }
LABEL_65:
        if ( v46 >= 0 )
        {
          string = 0;
          WindowsDeleteString(0);
          string = 0;
          v54 = WindowsCreateString(AddressString, AddressStringLength, &string);
          v55 = v54;
          if ( v54 < 0 )
          {
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)0x17F,
              (unsigned int)"onecoreuap\\net\\ux\\mediamanagerbase\\lib\\categorybase.cpp",
              (const char *)(unsigned int)v54,
              v88);
            WindowsDeleteString(string);
            string = 0;
            v56 = AddressString;
            AddressString = 0;
            if ( v56 )
              LocalFree(v56);
            wil::details::unique_storage<wil::details::resource_policy<_MIB_IF_TABLE2 *,void (*)(void *),&void FreeMibTable(void *),wistd::integral_constant<unsigned __int64,0>,_MIB_IF_TABLE2 *,_MIB_IF_TABLE2 *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_MIB_IF_TABLE2 *,void (*)(void *),&void FreeMibTable(void *),wistd::integral_constant<unsigned __int64,0>,_MIB_IF_TABLE2 *,_MIB_IF_TABLE2 *,0,std::nullptr_t>>(v98);
            wil::details::unique_storage<wil::details::resource_policy<_MIB_IF_TABLE2 *,void (*)(void *),&void FreeMibTable(void *),wistd::integral_constant<unsigned __int64,0>,_MIB_IF_TABLE2 *,_MIB_IF_TABLE2 *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_MIB_IF_TABLE2 *,void (*)(void *),&void FreeMibTable(void *),wistd::integral_constant<unsigned __int64,0>,_MIB_IF_TABLE2 *,_MIB_IF_TABLE2 *,0,std::nullptr_t>>(&Table);
            Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(
              &v90,
              v57,
              v58);
            return v55;
          }
          v59 = (*(__int64 (__fastcall **)(__int64, HSTRING, _QWORD))(*(_QWORD *)v90 + 120LL))(
                  v90,
                  string,
                  v42->Table[v43].Metric);
          v60 = v59;
          if ( v59 < 0 )
          {
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)0x180,
              (unsigned int)"onecoreuap\\net\\ux\\mediamanagerbase\\lib\\categorybase.cpp",
              (const char *)(unsigned int)v59,
              v88);
            WindowsDeleteString(string);
            string = 0;
            v61 = AddressString;
            AddressString = 0;
            if ( v61 )
              LocalFree(v61);
            wil::details::unique_storage<wil::details::resource_policy<_MIB_IF_TABLE2 *,void (*)(void *),&void FreeMibTable(void *),wistd::integral_constant<unsigned __int64,0>,_MIB_IF_TABLE2 *,_MIB_IF_TABLE2 *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_MIB_IF_TABLE2 *,void (*)(void *),&void FreeMibTable(void *),wistd::integral_constant<unsigned __int64,0>,_MIB_IF_TABLE2 *,_MIB_IF_TABLE2 *,0,std::nullptr_t>>(v98);
            wil::details::unique_storage<wil::details::resource_policy<_MIB_IF_TABLE2 *,void (*)(void *),&void FreeMibTable(void *),wistd::integral_constant<unsigned __int64,0>,_MIB_IF_TABLE2 *,_MIB_IF_TABLE2 *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_MIB_IF_TABLE2 *,void (*)(void *),&void FreeMibTable(void *),wistd::integral_constant<unsigned __int64,0>,_MIB_IF_TABLE2 *,_MIB_IF_TABLE2 *,0,std::nullptr_t>>(&Table);
            Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(
              &v90,
              v62,
              v63);
            return v60;
          }
          WindowsDeleteString(string);
        }
        else
        {
          wil::details::in1diag3::_Log_Hr(
            retaddr,
            (void *)0x17C,
            (unsigned int)"onecoreuap\\net\\ux\\mediamanagerbase\\lib\\categorybase.cpp",
            (const char *)(unsigned int)v46,
            v88);
        }
        v53 = AddressString;
        AddressString = 0;
        if ( v53 )
          goto LABEL_64;
LABEL_52:
        v36 = v91;
      }
      ++v41;
      continue;
    }
  }
  v3 = v97;
LABEL_80:
  TryGetInterfaceDnsServerView(&v96, &v100, a2);
  if ( v96 )
  {
    v94 = 0;
    v66 = (*(__int64 (__fastcall **)(__int64, unsigned int *))(*(_QWORD *)v96 + 56LL))(v96, &v94);
    v67 = v66;
    if ( v66 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x18E,
        (unsigned int)"onecoreuap\\net\\ux\\mediamanagerbase\\lib\\categorybase.cpp",
        (const char *)(unsigned int)v66,
        v88);
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v96, v68, v69);
      wil::details::unique_storage<wil::details::resource_policy<_MIB_IF_TABLE2 *,void (*)(void *),&void FreeMibTable(void *),wistd::integral_constant<unsigned __int64,0>,_MIB_IF_TABLE2 *,_MIB_IF_TABLE2 *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_MIB_IF_TABLE2 *,void (*)(void *),&void FreeMibTable(void *),wistd::integral_constant<unsigned __int64,0>,_MIB_IF_TABLE2 *,_MIB_IF_TABLE2 *,0,std::nullptr_t>>(&Table);
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v90, v70, v71);
      return v67;
    }
    for ( i = 0; i < v94; ++i )
    {
      *(_OWORD *)v98 = 0;
      v99 = 0;
      v73 = (*(__int64 (__fastcall **)(__int64, _QWORD, PMIB_IPFORWARD_TABLE2 *))(*(_QWORD *)v96 + 48LL))(v96, i, v98);
      v74 = v73;
      if ( v73 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x192,
          (unsigned int)"onecoreuap\\net\\ux\\mediamanagerbase\\lib\\categorybase.cpp",
          (const char *)(unsigned int)v73,
          v88);
        FreeDnsServer((struct Windows::Networking::UX::DnsServer *)v98);
        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v96, v75, v76);
        wil::details::unique_storage<wil::details::resource_policy<_MIB_IF_TABLE2 *,void (*)(void *),&void FreeMibTable(void *),wistd::integral_constant<unsigned __int64,0>,_MIB_IF_TABLE2 *,_MIB_IF_TABLE2 *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_MIB_IF_TABLE2 *,void (*)(void *),&void FreeMibTable(void *),wistd::integral_constant<unsigned __int64,0>,_MIB_IF_TABLE2 *,_MIB_IF_TABLE2 *,0,std::nullptr_t>>(&Table);
        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v90, v77, v78);
        return v74;
      }
      v79 = (*(__int64 (__fastcall **)(__int64, PMIB_IPFORWARD_TABLE2, __int64, _QWORD))(*(_QWORD *)v90 + 144LL))(
              v90,
              v98[1],
              v99,
              HIDWORD(v98[0]));
      v80 = v79;
      if ( v79 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x194,
          (unsigned int)"onecoreuap\\net\\ux\\mediamanagerbase\\lib\\categorybase.cpp",
          (const char *)(unsigned int)v79,
          v88);
        FreeDnsServer((struct Windows::Networking::UX::DnsServer *)v98);
        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v96, v81, v82);
        wil::details::unique_storage<wil::details::resource_policy<_MIB_IF_TABLE2 *,void (*)(void *),&void FreeMibTable(void *),wistd::integral_constant<unsigned __int64,0>,_MIB_IF_TABLE2 *,_MIB_IF_TABLE2 *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_MIB_IF_TABLE2 *,void (*)(void *),&void FreeMibTable(void *),wistd::integral_constant<unsigned __int64,0>,_MIB_IF_TABLE2 *,_MIB_IF_TABLE2 *,0,std::nullptr_t>>(&Table);
        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v90, v83, v84);
        return v80;
      }
      FreeDnsServer((struct Windows::Networking::UX::DnsServer *)v98);
    }
    v3 = v97;
  }
  v85 = v90;
  if ( v90 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v90 + 8LL))(v90);
    v85 = v90;
  }
  *v3 = v85;
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v96, v64, v65);
  wil::details::unique_storage<wil::details::resource_policy<_MIB_IF_TABLE2 *,void (*)(void *),&void FreeMibTable(void *),wistd::integral_constant<unsigned __int64,0>,_MIB_IF_TABLE2 *,_MIB_IF_TABLE2 *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_MIB_IF_TABLE2 *,void (*)(void *),&void FreeMibTable(void *),wistd::integral_constant<unsigned __int64,0>,_MIB_IF_TABLE2 *,_MIB_IF_TABLE2 *,0,std::nullptr_t>>(&Table);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v90, v86, v87);
  return 0;
}

```

## disassembly

```asm
0x18007d734  push    rbx
0x18007d736  push    rsi
0x18007d737  push    rdi
0x18007d738  push    r12
0x18007d73a  push    r13
0x18007d73c  push    r14
0x18007d73e  push    r15
0x18007d740  sub     rsp, 0B0h
0x18007d747  mov     rax, cs:__security_cookie
0x18007d74e  xor     rax, rsp
0x18007d751  mov     [rsp+0E8h+var_48], rax
0x18007d759  mov     r14, r8
0x18007d75c  mov     [rsp+0E8h+var_80], r8
0x18007d761  mov     r13d, edx
0x18007d764  xor     r15d, r15d
0x18007d767  mov     [r8], r15
0x18007d76a  lea     esi, [r15+2]
0x18007d76e  lea     eax, [rsi+15h]
0x18007d771  cmp     edx, 4
0x18007d774  cmovnz  si, ax
0x18007d778  mov     [rsp+0E8h+var_A8], esi
0x18007d77c  mov     [rsp+0E8h+var_B0], r15
0x18007d781  mov     rdx, rcx; struct _GUID *
0x18007d784  lea     rcx, [rsp+0E8h+var_78]; retstr
0x18007d789  call    ?_GetActualInterfaceGuid@CategoryBase@Internal@UX@Networking@Windows@@CA?AU_GUID@@AEBU6@@Z; Windows::Networking::UX::Internal::CategoryBase::_GetActualInterfaceGuid(_GUID const &)
0x18007d78e  movups  xmm0, xmmword ptr [rax]
0x18007d791  movdqu  xmmword ptr [rsp+0E8h+var_58.Data1], xmm0
0x18007d79a  lea     rcx, [rsp+0E8h+var_58]; struct _GUID *
0x18007d7a2  call    ?_ConvertInterfaceGuidToIndex@CategoryBase@Internal@UX@Networking@Windows@@CAKAEBU_GUID@@@Z; Windows::Networking::UX::Internal::CategoryBase::_ConvertInterfaceGuidToIndex(_GUID const &)
0x18007d7a7  mov     [rsp+0E8h+var_94], eax
0x18007d7ab  lea     rcx, [rsp+0E8h+var_78]; string
0x18007d7b0  call    ??$?0$0CF@@StringReference@Internal@Windows@@QEAA@AEAY0CF@$$CBG@Z; Windows::Internal::StringReference::StringReference(ushort const (&)[37])
0x18007d7b5  lea     rdx, [rsp+0E8h+var_B0]
0x18007d7ba  mov     rcx, [rax]
0x18007d7bd  call    ??$ActivateInstance@V?$ComPtr@UIStaticIpConfig@UX@Networking@Windows@@@WRL@Microsoft@@@Foundation@Windows@@YAJPEAUHSTRING__@@V?$ComPtrRef@V?$ComPtr@UIStaticIpConfig@UX@Networking@Windows@@@WRL@Microsoft@@@Details@WRL@Microsoft@@@Z; Windows::Foundation::ActivateInstance<Microsoft::WRL::ComPtr<Windows::Networking::UX::IStaticIpConfig>>(HSTRING__ *,Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::Networking::UX::IStaticIpConfig>>)
0x18007d7c2  mov     ebx, eax
0x18007d7c4  test    eax, eax
0x18007d7c6  jns     short loc_18007D7F6
0x18007d7c8  mov     rcx, [rsp+0E8h]; this
0x18007d7d0  mov     r9d, eax; char *
0x18007d7d3  lea     r8, aOnecoreuapNetU_21; "onecoreuap\\net\\ux\\mediamanagerbase\\"...
0x18007d7da  mov     edx, 128h; void *
0x18007d7df  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18007d7e4  nop
0x18007d7e5  lea     rcx, [rsp+0E8h+var_B0]
0x18007d7ea  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18007d7ef  mov     eax, ebx
0x18007d7f1  jmp     loc_18007DFD9
0x18007d7f6  mov     rcx, [rsp+0E8h+var_B0]
0x18007d7fb  mov     rax, [rcx]
0x18007d7fe  mov     edx, r13d
0x18007d801  mov     rax, [rax+38h]
0x18007d805  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007d80a  mov     ebx, eax
0x18007d80c  test    eax, eax
0x18007d80e  jns     short loc_18007D83E
0x18007d810  mov     rcx, [rsp+0E8h]; this
0x18007d818  mov     r9d, eax; char *
0x18007d81b  lea     r8, aOnecoreuapNetU_21; "onecoreuap\\net\\ux\\mediamanagerbase\\"...
0x18007d822  mov     edx, 129h; void *
0x18007d827  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18007d82c  nop
0x18007d82d  lea     rcx, [rsp+0E8h+var_B0]
0x18007d832  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18007d837  mov     eax, ebx
0x18007d839  jmp     loc_18007DFD9
0x18007d83e  mov     [rsp+0E8h+Table], r15
0x18007d843  xor     ecx, ecx; Family
0x18007d845  lea     rdx, [rsp+0E8h+Table]; Table
0x18007d84a  call    cs:__imp_GetUnicastIpAddressTable
0x18007d850  lea     rdi, aOnecoreuapNetU_21; "onecoreuap\\net\\ux\\mediamanagerbase\\"...
0x18007d857  test    eax, eax
0x18007d859  jnz     loc_18007DE01
0x18007d85f  mov     r14b, r15b
0x18007d862  lea     ecx, [rax+41h]
0x18007d865  mov     r12d, [rsp+0E8h+var_A8]
0x18007d86a  mov     rbx, [rsp+0E8h+Table]
0x18007d86f  cmp     r15d, [rbx]
0x18007d872  jnb     loc_18007DA9C
0x18007d878  mov     eax, r15d
0x18007d87b  lea     rsi, [rax+rax*4]
0x18007d87f  shl     rsi, 4
0x18007d883  mov     eax, [rsp+0E8h+var_94]
0x18007d887  cmp     [rsi+rbx+30h], eax
0x18007d88b  jnz     loc_18007DA94
0x18007d891  cmp     [rsi+rbx+8], r12w
0x18007d897  jnz     loc_18007DA94
0x18007d89d  cmp     dword ptr [rsi+rbx+34h], 1
0x18007d8a2  jnz     loc_18007DA94
0x18007d8a8  cmp     dword ptr [rsi+rbx+38h], 1
0x18007d8ad  jnz     loc_18007DA94
0x18007d8b3  mov     edx, 16h
0x18007d8b8  cmp     r13d, 4
0x18007d8bc  cmovnz  edx, ecx
0x18007d8bf  mov     [rsp+0E8h+AddressStringLength], edx
0x18007d8c3  lea     rcx, [rsp+0E8h+AddressString]
0x18007d8c8  call    ??$make_unique_hlocal@$$BY0A@G@wil@@YA?AV?$unique_ptr@$$BY0A@GU?$function_deleter@P6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@Z@wil@@@wistd@@_K@Z; wil::make_unique_hlocal<ushort [0]>(unsigned __int64)
0x18007d8cd  nop
0x18007d8ce  mov     eax, 2
0x18007d8d3  cmp     [rsi+rbx+8], ax
0x18007d8d8  jnz     short loc_18007D8F5
0x18007d8da  xor     edx, edx; Port
0x18007d8dc  lea     rcx, [rbx+0Ch]
0x18007d8e0  add     rcx, rsi; Address
0x18007d8e3  lea     r9, [rsp+0E8h+AddressStringLength]; AddressStringLength
0x18007d8e8  mov     r8, [rsp+0E8h+AddressString]; AddressString
0x18007d8ed  call    cs:__imp_RtlIpv4AddressToStringExW
0x18007d8f3  jmp     short loc_18007D924
0x18007d8f5  xor     eax, eax
0x18007d8f7  lea     ecx, [rax+17h]
0x18007d8fa  cmp     [rsi+rbx+8], cx
0x18007d8ff  jnz     short loc_18007D928
0x18007d901  xor     r8d, r8d; Port
0x18007d904  lea     rcx, [rbx+10h]
0x18007d908  add     rcx, rsi; Address
0x18007d90b  lea     rax, [rsp+0E8h+AddressStringLength]
0x18007d910  mov     qword ptr [rsp+0E8h+var_C8], rax; int
0x18007d915  mov     r9, [rsp+0E8h+AddressString]; AddressString
0x18007d91a  mov     edx, [rsi+rbx+20h]; ScopeId
0x18007d91e  call    cs:__imp_RtlIpv6AddressToStringExW
0x18007d924  bts     eax, 1Ch
0x18007d928  mov     rcx, [rsp+0E8h]; this
0x18007d930  test    eax, eax
0x18007d932  jns     short loc_18007D949
0x18007d934  mov     r9d, eax; char *
0x18007d937  mov     r8, rdi; unsigned int
0x18007d93a  mov     edx, 149h; void *
0x18007d93f  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18007d944  jmp     loc_18007DA76
0x18007d949  mov     [rsp+0E8h+string], 0
0x18007d952  xor     ecx, ecx; string
0x18007d954  call    cs:__imp_WindowsDeleteString
0x18007d95a  mov     [rsp+0E8h+string], 0
0x18007d963  lea     r8, [rsp+0E8h+string]; string
0x18007d968  mov     edx, [rsp+0E8h+AddressStringLength]; length
0x18007d96c  mov     rcx, [rsp+0E8h+AddressString]; sourceString
0x18007d971  call    cs:__imp_WindowsCreateString
0x18007d977  mov     r14d, eax
0x18007d97a  test    eax, eax
0x18007d97c  jns     short loc_18007D9E2
0x18007d97e  mov     rcx, [rsp+0E8h]; this
0x18007d986  mov     r9d, eax; char *
0x18007d989  mov     r8, rdi; unsigned int
0x18007d98c  mov     edx, 14Ch; void *
0x18007d991  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18007d996  nop
0x18007d997  mov     rcx, [rsp+0E8h+string]; string
0x18007d99c  call    cs:__imp_WindowsDeleteString
0x18007d9a2  mov     [rsp+0E8h+string], 0
0x18007d9ab  mov     rcx, [rsp+0E8h+AddressString]; hMem
0x18007d9b0  mov     [rsp+0E8h+AddressString], 0
0x18007d9b9  test    rcx, rcx
0x18007d9bc  jz      short loc_18007D9C5
0x18007d9be  call    cs:__imp_LocalFree
0x18007d9c4  nop
0x18007d9c5  lea     rcx, [rsp+0E8h+Table]
0x18007d9ca  call    ??1?$unique_storage@U?$resource_policy@PEAU_MIB_IF_TABLE2@@P6AXPEAX@Z$1?FreeMibTable@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_MIB_IF_TABLE2 *,void (*)(void *),&FreeMibTable(void *),wistd::integral_constant<unsigned __int64,0>,_MIB_IF_TABLE2 *,_MIB_IF_TABLE2 *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_MIB_IF_TABLE2 *,void (*)(void *),&FreeMibTable(void *),wistd::integral_constant<unsigned __int64,0>,_MIB_IF_TABLE2 *,_MIB_IF_TABLE2 *,0,std::nullptr_t>>(void)
0x18007d9cf  nop
0x18007d9d0  lea     rcx, [rsp+0E8h+var_B0]
0x18007d9d5  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18007d9da  mov     eax, r14d
0x18007d9dd  jmp     loc_18007DFD9
0x18007d9e2  mov     rcx, [rsp+0E8h+var_B0]
0x18007d9e7  mov     rax, [rcx]
0x18007d9ea  movzx   r8d, byte ptr [rsi+rbx+44h]
0x18007d9f0  mov     rdx, [rsp+0E8h+string]
0x18007d9f5  mov     rax, [rax+68h]
0x18007d9f9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007d9fe  mov     ebx, eax
0x18007da00  test    eax, eax
0x18007da02  jns     short loc_18007DA67
0x18007da04  mov     rcx, [rsp+0E8h]; this
0x18007da0c  mov     r9d, eax; char *
0x18007da0f  mov     r8, rdi; unsigned int
0x18007da12  mov     edx, 14Dh; void *
0x18007da17  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18007da1c  nop
0x18007da1d  mov     rcx, [rsp+0E8h+string]; string
0x18007da22  call    cs:__imp_WindowsDeleteString
0x18007da28  mov     [rsp+0E8h+string], 0
0x18007da31  mov     rcx, [rsp+0E8h+AddressString]; hMem
0x18007da36  mov     [rsp+0E8h+AddressString], 0
0x18007da3f  test    rcx, rcx
0x18007da42  jz      short loc_18007DA4B
0x18007da44  call    cs:__imp_LocalFree
0x18007da4a  nop
0x18007da4b  lea     rcx, [rsp+0E8h+Table]
0x18007da50  call    ??1?$unique_storage@U?$resource_policy@PEAU_MIB_IF_TABLE2@@P6AXPEAX@Z$1?FreeMibTable@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_MIB_IF_TABLE2 *,void (*)(void *),&FreeMibTable(void *),wistd::integral_constant<unsigned __int64,0>,_MIB_IF_TABLE2 *,_MIB_IF_TABLE2 *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_MIB_IF_TABLE2 *,void (*)(void *),&FreeMibTable(void *),wistd::integral_constant<unsigned __int64,0>,_MIB_IF_TABLE2 *,_MIB_IF_TABLE2 *,0,std::nullptr_t>>(void)
0x18007da55  nop
0x18007da56  lea     rcx, [rsp+0E8h+var_B0]
0x18007da5b  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18007da60  mov     eax, ebx
0x18007da62  jmp     loc_18007DFD9
0x18007da67  mov     r14b, 1
0x18007da6a  mov     rcx, [rsp+0E8h+string]; string
0x18007da6f  call    cs:__imp_WindowsDeleteString
0x18007da75  nop
0x18007da76  mov     rcx, [rsp+0E8h+AddressString]; hMem
0x18007da7b  mov     [rsp+0E8h+AddressString], 0
0x18007da84  test    rcx, rcx
0x18007da87  jz      short loc_18007DA8F
0x18007da89  call    cs:__imp_LocalFree
0x18007da8f  mov     ecx, 41h ; 'A'
0x18007da94  inc     r15d
0x18007da97  jmp     loc_18007D86A
0x18007da9c  xor     r15d, r15d
0x18007da9f  test    r14b, r14b
0x18007daa2  jz      loc_18007DDFC
0x18007daa8  mov     [rsp+0E8h+var_78], r15
0x18007daad  lea     rdx, [rsp+0E8h+var_78]; Table
0x18007dab2  mov     esi, [rsp+0E8h+var_A8]
0x18007dab6  movzx   ecx, si; Family
0x18007dab9  call    cs:__imp_GetIpForwardTable2
0x18007dabf  test    eax, eax
0x18007dac1  jz      short loc_18007DB04
0x18007dac3  mov     rcx, [rsp+0E8h]; this
0x18007dacb  mov     r9d, eax; char *
0x18007dace  mov     r8, rdi; unsigned int
0x18007dad1  mov     edx, 157h; void *
0x18007dad6  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x18007dadb  mov     ebx, eax
0x18007dadd  lea     rcx, [rsp+0E8h+var_78]
0x18007dae2  call    ??1?$unique_storage@U?$resource_policy@PEAU_MIB_IF_TABLE2@@P6AXPEAX@Z$1?FreeMibTable@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_MIB_IF_TABLE2 *,void (*)(void *),&FreeMibTable(void *),wistd::integral_constant<unsigned __int64,0>,_MIB_IF_TABLE2 *,_MIB_IF_TABLE2 *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_MIB_IF_TABLE2 *,void (*)(void *),&FreeMibTable(void *),wistd::integral_constant<unsigned __int64,0>,_MIB_IF_TABLE2 *,_MIB_IF_TABLE2 *,0,std::nullptr_t>>(void)
0x18007dae7  nop
0x18007dae8  lea     rcx, [rsp+0E8h+Table]
0x18007daed  call    ??1?$unique_storage@U?$resource_policy@PEAU_MIB_IF_TABLE2@@P6AXPEAX@Z$1?FreeMibTable@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_MIB_IF_TABLE2 *,void (*)(void *),&FreeMibTable(void *),wistd::integral_constant<unsigned __int64,0>,_MIB_IF_TABLE2 *,_MIB_IF_TABLE2 *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_MIB_IF_TABLE2 *,void (*)(void *),&FreeMibTable(void *),wistd::integral_constant<unsigned __int64,0>,_MIB_IF_TABLE2 *,_MIB_IF_TABLE2 *,0,std::nullptr_t>>(void)
0x18007daf2  nop
0x18007daf3  lea     rcx, [rsp+0E8h+var_B0]
0x18007daf8  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18007dafd  mov     eax, ebx
0x18007daff  jmp     loc_18007DFD9
0x18007db04  mov     r12d, r15d
0x18007db07  mov     rbx, [rsp+0E8h+var_78]
0x18007db0c  cmp     r12d, [rbx]
0x18007db0f  jnb     loc_18007DDF2
0x18007db15  mov     eax, r12d
0x18007db18  imul    r14, rax, 68h ; 'h'
0x18007db1c  mov     eax, [rsp+0E8h+var_94]
0x18007db20  cmp     [r14+rbx+10h], eax
0x18007db25  jnz     loc_18007DBE7
0x18007db2b  cmp     [r14+rbx+34h], si
0x18007db31  jnz     loc_18007DBE7
0x18007db37  cmp     [r14+rbx+30h], r15b
0x18007db3c  jnz     loc_18007DBE7
0x18007db42  cmp     [r14+rbx+6Ch], r15d
0x18007db47  jnz     loc_18007DBE7
0x18007db4d  mov     edx, 16h
0x18007db52  cmp     r13d, 4
0x18007db56  lea     ecx, [rdx+2Bh]
0x18007db59  cmovnz  edx, ecx
0x18007db5c  mov     [rsp+0E8h+AddressStringLength], edx
0x18007db60  lea     rcx, [rsp+0E8h+AddressString]
0x18007db65  call    ??$make_unique_hlocal@$$BY0A@G@wil@@YA?AV?$unique_ptr@$$BY0A@GU?$function_deleter@P6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@Z@wil@@@wistd@@_K@Z; wil::make_unique_hlocal<ushort [0]>(unsigned __int64)
0x18007db6a  nop
0x18007db6b  mov     eax, 2
0x18007db70  cmp     [r14+rbx+34h], ax
0x18007db76  jnz     short loc_18007DBEF
0x18007db78  xor     edx, edx; Port
0x18007db7a  lea     rcx, [rbx+38h]
0x18007db7e  add     rcx, r14; Address
0x18007db81  lea     r9, [rsp+0E8h+AddressStringLength]; AddressStringLength
0x18007db86  mov     r8, [rsp+0E8h+AddressString]; AddressString
0x18007db8b  call    cs:__imp_RtlIpv4AddressToStringExW
0x18007db91  mov     esi, eax
0x18007db93  or      esi, 10000000h
0x18007db99  mov     rcx, [rsp+0E8h]
0x18007dba1  jge     short loc_18007DBAD
0x18007dba3  mov     edx, 16Bh
0x18007dba8  jmp     loc_18007DC3E
0x18007dbad  lea     rdx, a0000; "0.0.0.0"
0x18007dbb4  mov     r15, [rsp+0E8h+AddressString]
0x18007dbb9  mov     rcx, r15; String1
0x18007dbbc  call    wcscmp_0
0x18007dbc1  test    eax, eax
0x18007dbc3  jnz     loc_18007DC91
0x18007dbc9  mov     [rsp+0E8h+AddressString], 0
0x18007dbd2  test    r15, r15
0x18007dbd5  jz      short loc_18007DBE0
0x18007dbd7  mov     rcx, r15; hMem
0x18007dbda  call    cs:__imp_LocalFree
0x18007dbe0  xor     r15d, r15d
0x18007dbe3  mov     esi, [rsp+0E8h+var_A8]
0x18007dbe7  inc     r12d
0x18007dbea  jmp     loc_18007DB07
0x18007dbef  mov     esi, r15d
0x18007dbf2  mov     eax, 17h
0x18007dbf7  cmp     [r14+rbx+34h], ax
0x18007dbfd  jnz     loc_18007DC94
0x18007dc03  xor     r8d, r8d; Port
0x18007dc06  lea     rcx, [rbx+3Ch]
0x18007dc0a  add     rcx, r14; Address
0x18007dc0d  lea     rax, [rsp+0E8h+AddressStringLength]
0x18007dc12  mov     qword ptr [rsp+0E8h+var_C8], rax; int
0x18007dc17  mov     r9, [rsp+0E8h+AddressString]; AddressString
0x18007dc1c  mov     edx, [r14+rbx+4Ch]; ScopeId
0x18007dc21  call    cs:__imp_RtlIpv6AddressToStringExW
0x18007dc27  mov     esi, eax
0x18007dc29  or      esi, 10000000h
0x18007dc2f  mov     rcx, [rsp+0E8h]; this
0x18007dc37  jge     short loc_18007DC4B
  ... truncated ...
```
