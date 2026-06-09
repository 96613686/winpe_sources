# Windows::Networking::UX::Internal::CategoryBase::_SetStaticIpConfigInternal(Windows::Networking::UX::IStaticIpConfig *,_GUID const &,ulong)

- ea: `0x180028aa8`
- end: `0x18002a061`
- name: `?_SetStaticIpConfigInternal@CategoryBase@Internal@UX@Networking@Windows@@CAJPEAUIStaticIpConfig@345@AEBU_GUID@@K@Z`
- size: `5561`
- prototype: `static int(struct Windows::Networking::UX::IStaticIpConfig *, const struct _GUID *, unsigned int)`
- caller_count: `1`
- callee_count: `18`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x180028840`

## callees

- `0x180002150`
- `0x180005be0`
- `0x180005c80`
- `0x18001b1d4`
- `0x18001bdb8`
- `0x18001cb10`
- `0x18002711c`
- `0x180028aa8`
- `0x18002a068`
- `0x18002cd20`
- `0x18002d8c8`
- `0x1800331a4`
- `0x180036714`
- `0x180051e58`
- `0x180051f70`
- `0x1800524fc`
- `0x180052ac8`
- `0x180059010`

## import_xrefs

- `ntdll!RtlIpv6StringToAddressExW` at `0x180029658`
- `ntdll!RtlIpv6StringToAddressExW` at `0x180029cf9`
- `ntdll!RtlIpv6StringToAddressExW` at `0x180029dab`
- `ntdll!RtlIpv6StringToAddressExW` at `0x180029658`
- `ntdll!RtlIpv6StringToAddressExW` at `0x180029cf9`
- `ntdll!RtlIpv6StringToAddressExW` at `0x180029dab`
- `ntdll!RtlIpv4StringToAddressExW` at `0x180029556`
- `ntdll!RtlIpv4StringToAddressExW` at `0x180029b14`
- `ntdll!RtlIpv4StringToAddressExW` at `0x180029bc0`
- `ntdll!RtlIpv4StringToAddressExW` at `0x180029556`
- `ntdll!RtlIpv4StringToAddressExW` at `0x180029b14`
- `ntdll!RtlIpv4StringToAddressExW` at `0x180029bc0`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002933c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180029385`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002941f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180029583`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180029685`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180029783`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800297df`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800298f7`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002993f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800299d5`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180029b41`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180029bed`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180029d26`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180029dd8`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180029eff`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180029f5b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002933c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180029385`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002941f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180029583`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180029685`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180029783`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800297df`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800298f7`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002993f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800299d5`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180029b41`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180029bed`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180029d26`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180029dd8`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180029eff`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180029f5b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18002949d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18002953e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18002963a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180029a4f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180029ba8`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180029d8d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18002949d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18002953e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18002963a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180029a4f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180029ba8`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180029d8d`
- `IPHLPAPI!InternalDeleteUnicastIpAddressEntry` at `0x1800292bb`
- `IPHLPAPI!InternalDeleteUnicastIpAddressEntry` at `0x1800292bb`
- `IPHLPAPI!GetIpForwardTable2` at `0x180029804`
- `IPHLPAPI!GetIpForwardTable2` at `0x180029804`
- `IPHLPAPI!InitializeUnicastIpAddressEntry` at `0x1800294da`
- `IPHLPAPI!InitializeUnicastIpAddressEntry` at `0x1800294da`
- `IPHLPAPI!GetUnicastIpAddressTable` at `0x18002924c`
- `IPHLPAPI!GetUnicastIpAddressTable` at `0x18002924c`
- `IPHLPAPI!InternalCreateIpForwardEntry2` at `0x180029e9a`
- `IPHLPAPI!InternalCreateIpForwardEntry2` at `0x180029e9a`
- `IPHLPAPI!InitializeIpForwardEntry` at `0x180029a93`
- `IPHLPAPI!InitializeIpForwardEntry` at `0x180029a93`
- `IPHLPAPI!InternalDeleteIpForwardEntry2` at `0x180029878`
- `IPHLPAPI!InternalDeleteIpForwardEntry2` at `0x180029878`
- `IPHLPAPI!InternalCreateUnicastIpAddressEntry` at `0x180029717`
- `IPHLPAPI!InternalCreateUnicastIpAddressEntry` at `0x180029717`
- `IPHLPAPI!ConvertInterfaceGuidToLuid` at `0x1800291a2`
- `IPHLPAPI!ConvertInterfaceGuidToLuid` at `0x1800291a2`

## pseudocode

```c
// Hidden C++ exception states: #wind=8 #try_helpers=1
__int64 __fastcall Windows::Networking::UX::Internal::CategoryBase::_SetStaticIpConfigInternal(
        struct Windows::Networking::UX::IStaticIpConfig *a1,
        const struct _GUID *a2,
        int a3)
{
  const GUID *v3; // rsi
  int v5; // eax
  unsigned int v6; // ebx
  int v8; // eax
  unsigned int v9; // ebx
  __int64 (__fastcall *v10)(struct Windows::Networking::UX::IStaticIpConfig *, __int64 *); // rbx
  int v11; // eax
  unsigned int v12; // ebx
  char v13; // bl
  char DhcpEnabled; // al
  int v15; // eax
  unsigned int v16; // ebx
  __int64 (__fastcall *v17)(struct Windows::Networking::UX::IStaticIpConfig *, __int64 *); // rbx
  int v18; // eax
  unsigned int v19; // ebx
  __int64 (__fastcall *v20)(struct Windows::Networking::UX::IStaticIpConfig *, __int64 *); // rbx
  int v21; // eax
  unsigned int v22; // ebx
  int v23; // eax
  unsigned int v24; // ebx
  __int64 (__fastcall *v25)(struct Windows::Networking::UX::IStaticIpConfig *, __int64 *); // rbx
  int v26; // eax
  unsigned int v27; // ebx
  __int64 (__fastcall *v28)(struct Windows::Networking::UX::IStaticIpConfig *, __int64 *); // rbx
  int v29; // eax
  unsigned int v30; // ebx
  int v31; // eax
  unsigned int v32; // ebx
  char v33; // di
  int StaticIpConfig_Static; // eax
  ADDRESS_FAMILY v35; // r15
  int v36; // eax
  __int64 v37; // r8
  unsigned int v38; // ebx
  int v39; // eax
  unsigned int v40; // eax
  unsigned int v41; // ebx
  __int64 v42; // rbx
  PMIB_UNICASTIPADDRESS_TABLE v43; // r8
  int i; // edi
  __int64 v45; // rdx
  unsigned int v46; // eax
  unsigned int j; // esi
  __int64 v48; // rdi
  __int64 (__fastcall *v49)(__int64, _QWORD, HSTRING *); // rbx
  int v50; // eax
  unsigned int v51; // ebx
  int v52; // eax
  unsigned int v53; // ebx
  char v54; // bl
  unsigned int StringRawBuffer; // eax
  int v56; // r8d
  const WCHAR *v57; // rax
  LONG v58; // eax
  unsigned int v59; // ebx
  const WCHAR *v60; // rax
  LONG v61; // eax
  unsigned int v62; // ebx
  unsigned int v63; // eax
  unsigned int v64; // ebx
  PMIB_IPFORWARD_TABLE2 k; // r8
  ULONG v66; // ebx
  __int64 v67; // rdx
  unsigned int v68; // eax
  unsigned int m; // esi
  __int64 v70; // rdi
  __int64 (__fastcall *v71)(__int64, _QWORD, HSTRING *); // rbx
  int v72; // eax
  unsigned int v73; // ebx
  int v74; // eax
  unsigned int v75; // ebx
  char v76; // bl
  unsigned int v77; // eax
  int v78; // r8d
  LONG v79; // eax
  unsigned int v80; // ebx
  const WCHAR *v81; // rax
  LONG v82; // eax
  unsigned int v83; // ebx
  LONG v84; // eax
  unsigned int v85; // ebx
  const WCHAR *v86; // rax
  LONG v87; // eax
  unsigned int v88; // ebx
  unsigned int v89; // eax
  unsigned int v90; // ebx
  unsigned int v91; // [rsp+20h] [rbp-188h]
  __int64 v92; // [rsp+30h] [rbp-178h] BYREF
  unsigned int v93; // [rsp+38h] [rbp-170h] BYREF
  HSTRING v94; // [rsp+40h] [rbp-168h] BYREF
  __int64 v95; // [rsp+48h] [rbp-160h] BYREF
  __int64 v96; // [rsp+50h] [rbp-158h] BYREF
  USHORT Port[4]; // [rsp+58h] [rbp-150h] BYREF
  __int64 v98; // [rsp+60h] [rbp-148h] BYREF
  __int64 v99; // [rsp+68h] [rbp-140h] BYREF
  __int64 v100; // [rsp+70h] [rbp-138h] BYREF
  HSTRING string; // [rsp+78h] [rbp-130h] BYREF
  unsigned int v102; // [rsp+80h] [rbp-128h] BYREF
  int v103; // [rsp+84h] [rbp-124h] BYREF
  int v104; // [rsp+88h] [rbp-120h]
  int v105; // [rsp+8Ch] [rbp-11Ch] BYREF
  unsigned int v106; // [rsp+90h] [rbp-118h] BYREF
  unsigned int v107; // [rsp+94h] [rbp-114h] BYREF
  PMIB_UNICASTIPADDRESS_TABLE Table; // [rsp+98h] [rbp-110h] BYREF
  PMIB_IPFORWARD_TABLE2 v109; // [rsp+A0h] [rbp-108h] BYREF
  NET_LUID InterfaceLuid; // [rsp+A8h] [rbp-100h] BYREF
  const struct _GUID *v111; // [rsp+B0h] [rbp-F8h]
  ADDRESS_FAMILY v112; // [rsp+B8h] [rbp-F0h]
  struct in_addr Address[7]; // [rsp+BAh] [rbp-EEh] BYREF
  ADDRESS_FAMILY v114; // [rsp+D8h] [rbp-D0h]
  struct in_addr v115[9]; // [rsp+DAh] [rbp-CEh] BYREF
  struct _MIB_IPFORWARD_ROW2 Row; // [rsp+100h] [rbp-A8h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+1A8h] [rbp+0h]

  LODWORD(v94) = a3;
  v3 = a2;
  v111 = a2;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 45, &WPP_426275660baf32778194b91bb4cd93ce_Traceguids);
  v103 = 0;
  v5 = (*(__int64 (__fastcall **)(struct Windows::Networking::UX::IStaticIpConfig *, int *))(*(_QWORD *)a1 + 176LL))(
         a1,
         &v103);
  v6 = v5;
  if ( v5 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1E9,
      (unsigned int)"onecoreuap\\net\\ux\\mediamanagerbase\\lib\\categorybase.cpp",
      (const char *)(unsigned int)v5,
      v91);
    return v6;
  }
  v93 = 4;
  v92 = 0;
  v8 = (*(__int64 (__fastcall **)(struct Windows::Networking::UX::IStaticIpConfig *, unsigned int *))(*(_QWORD *)a1 + 48LL))(
         a1,
         &v93);
  v9 = v8;
  if ( v8 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1ED,
      (unsigned int)"onecoreuap\\net\\ux\\mediamanagerbase\\lib\\categorybase.cpp",
      (const char *)(unsigned int)v8,
      v91);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v92);
    return v9;
  }
  v10 = *(__int64 (__fastcall **)(struct Windows::Networking::UX::IStaticIpConfig *, __int64 *))(*(_QWORD *)a1 + 64LL);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v92);
  v11 = v10(a1, &v92);
  v12 = v11;
  if ( v11 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1EE,
      (unsigned int)"onecoreuap\\net\\ux\\mediamanagerbase\\lib\\categorybase.cpp",
      (const char *)(unsigned int)v11,
      v91);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v92);
    return v12;
  }
  if ( v103 == 1 || (v13 = 0, v103 == 4) )
    v13 = 1;
  DhcpEnabled = Windows::Networking::UX::Internal::CategoryBase::_GetDhcpEnabled(v3, v93);
  if ( v13 != DhcpEnabled )
  {
    if ( DhcpEnabled )
    {
      if ( !v13 )
      {
        v104 = 2;
        goto LABEL_20;
      }
    }
    else if ( v13 )
    {
      v104 = 1;
      goto LABEL_20;
    }
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x1E0,
      (unsigned int)"onecoreuap\\net\\ux\\mediamanagerbase\\lib\\categorybase.cpp",
      (const char *)0x80070057LL,
      v91);
  }
  v104 = 0;
LABEL_20:
  v106 = 0;
  if ( v92 )
  {
    v15 = (*(__int64 (__fastcall **)(__int64, unsigned int *))(*(_QWORD *)v92 + 56LL))(v92, &v106);
    v16 = v15;
    if ( v15 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x1F5,
        (unsigned int)"onecoreuap\\net\\ux\\mediamanagerbase\\lib\\categorybase.cpp",
        (const char *)(unsigned int)v15,
        v91);
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v92);
      return v16;
    }
  }
  v96 = 0;
  v17 = *(__int64 (__fastcall **)(struct Windows::Networking::UX::IStaticIpConfig *, __int64 *))(*(_QWORD *)a1 + 72LL);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v96);
  v18 = v17(a1, &v96);
  v19 = v18;
  if ( v18 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1FA,
      (unsigned int)"onecoreuap\\net\\ux\\mediamanagerbase\\lib\\categorybase.cpp",
      (const char *)(unsigned int)v18,
      v91);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v96);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v92);
    return v19;
  }
  v95 = 0;
  v20 = *(__int64 (__fastcall **)(struct Windows::Networking::UX::IStaticIpConfig *, __int64 *))(*(_QWORD *)a1 + 80LL);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v95);
  v21 = v20(a1, &v95);
  v22 = v21;
  if ( v21 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1FD,
      (unsigned int)"onecoreuap\\net\\ux\\mediamanagerbase\\lib\\categorybase.cpp",
      (const char *)(unsigned int)v21,
      v91);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v95);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v96);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v92);
    return v22;
  }
  v107 = 0;
  if ( v95 )
  {
    v23 = (*(__int64 (__fastcall **)(__int64, unsigned int *))(*(_QWORD *)v95 + 56LL))(v95, &v107);
    v24 = v23;
    if ( v23 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x202,
        (unsigned int)"onecoreuap\\net\\ux\\mediamanagerbase\\lib\\categorybase.cpp",
        (const char *)(unsigned int)v23,
        v91);
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v95);
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v96);
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v92);
      return v24;
    }
  }
  v99 = 0;
  v98 = 0;
  v25 = *(__int64 (__fastcall **)(struct Windows::Networking::UX::IStaticIpConfig *, __int64 *))(*(_QWORD *)a1 + 88LL);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v99);
  v26 = v25(a1, &v99);
  v27 = v26;
  if ( v26 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x208,
      (unsigned int)"onecoreuap\\net\\ux\\mediamanagerbase\\lib\\categorybase.cpp",
      (const char *)(unsigned int)v26,
      v91);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v98);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v99);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v95);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v96);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v92);
    return v27;
  }
  v28 = *(__int64 (__fastcall **)(struct Windows::Networking::UX::IStaticIpConfig *, __int64 *))(*(_QWORD *)a1 + 96LL);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v98);
  v29 = v28(a1, &v98);
  v30 = v29;
  if ( v29 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x209,
      (unsigned int)"onecoreuap\\net\\ux\\mediamanagerbase\\lib\\categorybase.cpp",
      (const char *)(unsigned int)v29,
      v91);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v98);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v99);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v95);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v96);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v92);
    return v30;
  }
  v105 = 0;
  if ( v98 )
  {
    v31 = (*(__int64 (__fastcall **)(__int64, int *))(*(_QWORD *)v98 + 56LL))(v98, &v105);
    v32 = v31;
    if ( v31 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x20E,
        (unsigned int)"onecoreuap\\net\\ux\\mediamanagerbase\\lib\\categorybase.cpp",
        (const char *)(unsigned int)v31,
        v91);
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v98);
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v99);
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v95);
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v96);
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v92);
      return v32;
    }
  }
  v33 = 1;
  v100 = 0;
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v100);
  StaticIpConfig_Static = Windows::Networking::UX::Internal::CategoryBase::GetStaticIpConfig_Static(v3, v93, &v100);
  if ( StaticIpConfig_Static < 0 )
  {
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x217,
      (unsigned int)"onecoreuap\\net\\ux\\mediamanagerbase\\lib\\categorybase.cpp",
      (const char *)(unsigned int)StaticIpConfig_Static,
      v91);
    goto LABEL_39;
  }
  *(_DWORD *)Port = 0;
  v36 = (*(__int64 (__fastcall **)(__int64, USHORT *))(*(_QWORD *)v100 + 176LL))(v100, Port);
  v38 = v36;
  if ( v36 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x21A,
      (unsigned int)"onecoreuap\\net\\ux\\mediamanagerbase\\lib\\categorybase.cpp",
      (const char *)(unsigned int)v36,
      v91);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v100);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v98);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v99);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v95);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v96);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v92);
    return v38;
  }
  if ( v103 == 1 )
  {
    v39 = *(_DWORD *)Port;
    if ( *(_DWORD *)Port == 1 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 46, &WPP_426275660baf32778194b91bb4cd93ce_Traceguids);
LABEL_48:
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v100);
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v98);
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v99);
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v95);
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v96);
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v92);
      return 0;
    }
    goto LABEL_51;
  }
  if ( v103 != 4 )
    goto LABEL_39;
  v39 = *(_DWORD *)Port;
  if ( *(_DWORD *)Port != 1 )
  {
LABEL_51:
    if ( v39 != 4 )
      goto LABEL_39;
  }
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 47, &WPP_426275660baf32778194b91bb4cd93ce_Traceguids);
  v33 = 0;
  LOBYTE(v37) = 1;
  Windows::Networking::UX::Internal::CategoryBase::_EnsureDhcpEnabled(v3, v93, v37);
LABEL_39:
  if ( v93 == 4 )
    v35 = 2;
  else
    v35 = 23;
  InterfaceLuid.Value = 0;
  v40 = ConvertInterfaceGuidToLuid(v3, &InterfaceLuid);
  if ( !v40 )
  {
    if ( v33 )
    {
      if ( v104 == 2 )
        Windows::Networking::UX::Internal::CategoryBase::_EnsureDhcpEnabled(v3, v93, 0);
      Table = 0;
      if ( GetUnicastIpAddressTable(v35, &Table) )
      {
        i = (int)v94;
      }
      else
      {
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
          WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 48, &WPP_426275660baf32778194b91bb4cd93ce_Traceguids);
        v42 = 0;
        v43 = Table;
        for ( i = (int)v94; (unsigned int)v42 < v43->NumEntries; v42 = (unsigned int)(v42 + 1) )
        {
          v45 = (__int64)&v43->Table[v42];
          if ( *(_DWORD *)(v45 + 40) == i
            && *(_WORD *)v45 == v35
            && *(_DWORD *)(v45 + 44) == 1
            && *(_DWORD *)(v45 + 48) == 1 )
          {
            v46 = InternalDeleteUnicastIpAddressEntry(2);
            if ( v46 )
              wil::details::in1diag3::_Log_Win32(
                retaddr,
                (void *)0x249,
                (unsigned int)"onecoreuap\\net\\ux\\mediamanagerbase\\lib\\categorybase.cpp",
                (const char *)v46,
                v91);
            v43 = Table;
          }
        }
      }
      for ( j = 0; j < v106; ++j )
      {
        v112 = 0;
        memset(Address, 0, 26);
        string = 0;
        v102 = 0;
        v48 = v92;
        v49 = *(__int64 (__fastcall **)(__int64, _QWORD, HSTRING *))(*(_QWORD *)v92 + 48LL);
        WindowsDeleteString(0);
        string = 0;
        v50 = v49(v48, j, &string);
        v51 = v50;
        if ( v50 < 0 )
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x255,
            (unsigned int)"onecoreuap\\net\\ux\\mediamanagerbase\\lib\\categorybase.cpp",
            (const char *)(unsigned int)v50,
            v91);
          WindowsDeleteString(string);
          string = 0;
          Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v100);
          Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v98);
          Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v99);
          Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v95);
          Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v96);
          Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v92);
          return v51;
        }
        v52 = (*(__int64 (__fastcall **)(__int64, _QWORD, unsigned int *))(*(_QWORD *)v96 + 48LL))(v96, j, &v102);
        v53 = v52;
        if ( v52 < 0 )
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x256,
            (unsigned int)"onecoreuap\\net\\ux\\mediamanagerbase\\lib\\categorybase.cpp",
            (const char *)(unsigned int)v52,
            v91);
          WindowsDeleteString(string);
          string = 0;
          Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v100);
          Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v98);
          Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v99);
          Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v95);
          Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v96);
          Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v92);
          return v53;
        }
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
        {
          v54 = v102;
          StringRawBuffer = (unsigned int)WindowsGetStringRawBuffer(string, 0);
          WPP_SF_Sd(*((_QWORD *)WPP_GLOBAL_Control + 2), 49, v56, StringRawBuffer, v54);
        }
        memset_0(&Row, 0, 0x50u);
        InitializeUnicastIpAddressEntry((PMIB_UNICASTIPADDRESS_ROW)&Row);
        *(NET_LUID *)(&Row.DestinationPrefix.Prefix.si_family + 10) = InterfaceLuid;
        i = (int)v94;
        *(_DWORD *)&Row.DestinationPrefix.PrefixLength = (_DWORD)v94;
        Row.NextHop.Ipv6.sin6_addr.u.Byte[8] = v102;
        *(_QWORD *)&Row.NextHop.Ipv4.sin_family = 0x100000001LL;
        Port[0] = 0;
        if ( v93 == 4 )
        {
          v112 = 2;
          v57 = WindowsGetStringRawBuffer(string, 0);
          v58 = RtlIpv4StringToAddressExW(v57, 1u, (struct in_addr *)&Address[0].S_un.S_un_w.s_w2, Port);
          if ( v58 < 0 )
          {
            v59 = wil::details::in1diag3::Return_NtStatus(
                    retaddr,
                    (void *)0x268,
                    (unsigned int)"onecoreuap\\net\\ux\\mediamanagerbase\\lib\\categorybase.cpp",
                    (const char *)(unsigned int)v58,
                    v91);
            WindowsDeleteString(string);
            string = 0;
            Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v100);
            Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v98);
            Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v99);
            Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v95);
            Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v96);
            Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v92);
            return v59;
          }
          LOWORD(Row.InterfaceLuid.Value) = v112;
          *(struct _NET_LUID_LH::$0227A65EDE726BD8ABDBF310B0E65A75 *)((char *)&Row.InterfaceLuid.Info + 2) = *(struct _NET_LUID_LH::$0227A65EDE726BD8ABDBF310B0E65A75 *)&Address[0].S_un.S_un_b.s_b1;
          *(struct in_addr *)((char *)&Row.InterfaceIndex + 2) = Address[2];
          Row.DestinationPrefix.Prefix.Ipv4.sin_port = Address[3].S_un.S_un_w.s_w1;
        }
        else if ( v93 == 6 )
        {
          v112 = 23;
          v60 = WindowsGetStringRawBuffer(string, 0);
          v61 = RtlIpv6StringToAddressExW(
                  v60,
                  (struct in6_addr *)&Address[1].S_un.S_un_w.s_w2,
                  (PULONG)&Address[5].S_un.S_un_w.s_w2,
                  Port);
          if ( v61 < 0 )
          {
            v62 = wil::details::in1diag3::Return_NtStatus(
                    retaddr,
                    (void *)0x26F,
                    (unsigned int)"onecoreuap\\net\\ux\\mediamanagerbase\\lib\\categorybase.cpp",
                    (const char *)(unsigned int)v61,
                    v91);
            WindowsDeleteString(string);
            string = 0;
            Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v100);
            Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v98);
            Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v99);
            Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v95);
            Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v96);
            Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v92);
            return v62;
          }
          LOWORD(Row.InterfaceLuid.Value) = v112;
          *(_OWORD *)((char *)&Row.InterfaceLuid.Info + 2) = *(_OWORD *)&Address[0].S_un.S_un_b.s_b1;
          Row.DestinationPrefix.Prefix.Ipv4 = *(SOCKADDR_IN *)&Address[2].S_un.S_un_w.s_w2;
        }
        v63 = InternalCreateUnicastIpAddressEntry(2, &Row);
        if ( v63 == 5010 )
        {
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
            WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 50, &WPP_426275660baf32778194b91bb4cd93ce_Traceguids);
        }
        else if ( v63 )
        {
          v64 = wil::details::in1diag3::Return_Win32(
                  retaddr,
                  (void *)0x27A,
                  (unsigned int)"onecoreuap\\net\\ux\\mediamanagerbase\\lib\\categorybase.cpp",
                  (const char *)v63,
                  v91);
          WindowsDeleteString(string);
          string = 0;
          Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v100);
          Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v98);
          Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v99);
          Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v95);
          Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v96);
          Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v92);
          return v64;
        }
        WindowsDeleteString(string);
      }
      v109 = 0;
      if ( !GetIpForwardTable2(v35, &v109) )
      {
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
          WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 51, &WPP_426275660baf32778194b91bb4cd93ce_Traceguids);
        v66 = 0;
        for ( k = v109; v66 < k->NumEntries; ++v66 )
        {
          v67 = (__int64)&k->Table[v66];
          if ( *(_DWORD *)(v67 + 8) == i
            && *(_WORD *)(v67 + 44) == v35
            && !*(_BYTE *)(v67 + 40)
            && !*(_DWORD *)(v67 + 100) )
          {
            v68 = InternalDeleteIpForwardEntry2(2);
            if ( v68 )
              wil::details::in1diag3::_Log_Win32(
                retaddr,
                (void *)0x28C,
                (unsigned int)"onecoreuap\\net\\ux\\mediamanagerbase\\lib\\categorybase.cpp",
                (const char *)v68,
                v91);
            k = v109;
          }
        }
      }
      for ( m = 0; m < v107; ++m )
      {
        v94 = 0;
        v114 = 0;
        memset(v115, 0, 26);
        v102 = 0;
        v70 = v95;
        v71 = *(__int64 (__fastcall **)(__int64, _QWORD, HSTRING *))(*(_QWORD *)v95 + 48LL);
        WindowsDeleteString(0);
        v94 = 0;
        v72 = v71(v70, m, &v94);
        v73 = v72;
        if ( v72 < 0 )
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x297,
            (unsigned int)"onecoreuap\\net\\ux\\mediamanagerbase\\lib\\categorybase.cpp",
            (const char *)(unsigned int)v72,
            v91);
          WindowsDeleteString(v94);
          v94 = 0;
          Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v100);
          Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v98);
          Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v99);
          Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v95);
          Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v96);
          Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v92);
          return v73;
        }
        v74 = (*(__int64 (__fastcall **)(__int64, _QWORD, unsigned int *))(*(_QWORD *)v99 + 48LL))(v99, m, &v102);
        v75 = v74;
        if ( v74 < 0 )
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x298,
            (unsigned int)"onecoreuap\\net\\ux\\mediamanagerbase\\lib\\categorybase.cpp",
            (const char *)(unsigned int)v74,
            v91);
          WindowsDeleteString(v94);
          v94 = 0;
          Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v100);
          Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v98);
          Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v99);
          Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v95);
          Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v96);
          Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v92);
          return v75;
        }
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
        {
          v76 = v102;
          v77 = (unsigned int)WindowsGetStringRawBuffer(v94, 0);
          WPP_SF_Sd(*((_QWORD *)WPP_GLOBAL_Control + 2), 52, v78, v77, v76);
        }
        memset_0(&Row, 0, sizeof(Row));
        InitializeIpForwardEntry(&Row);
        Row.InterfaceLuid = InterfaceLuid;
        Row.Metric = (unsigned __int8)v102;
        Row.DestinationPrefix.PrefixLength = 0;
        Row.Origin = NlroManual;
        v112 = 0;
        memset(Address, 0, 26);
        Port[0] = 0;
        if ( v93 == 4 )
        {
          v112 = 2;
          v79 = RtlIpv4StringToAddressExW(L"0.0.0.0", 1u, (struct in_addr *)&Address[0].S_un.S_un_w.s_w2, Port);
          if ( v79 < 0 )
          {
            v80 = wil::details::in1diag3::Return_NtStatus(
                    retaddr,
                    (void *)0x2AA,
                    (unsigned int)"onecoreuap\\net\\ux\\mediamanagerbase\\lib\\categorybase.cpp",
                    (const char *)(unsigned int)v79,
                    v91);
            WindowsDeleteString(v94);
            v94 = 0;
            Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v100);
            Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v98);
            Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v99);
            Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v95);
            Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v96);
            Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v92);
            return v80;
          }
          v114 = 2;
          v81 = WindowsGetStringRawBuffer(v94, 0);
          v82 = RtlIpv4StringToAddressExW(v81, 1u, (struct in_addr *)&v115[0].S_un.S_un_w.s_w2, Port);
          if ( v82 < 0 )
          {
            v83 = wil::details::in1diag3::Return_NtStatus(
                    retaddr,
                    (void *)0x2AE,
                    (unsigned int)"onecoreuap\\net\\ux\\mediamanagerbase\\lib\\categorybase.cpp",
                    (const char *)(unsigned int)v82,
                    v91);
            WindowsDeleteString(v94);
            v94 = 0;
            Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v100);
            Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v98);
            Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v99);
            Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v95);
            Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v96);
            Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v92);
            return v83;
          }
          Row.DestinationPrefix.Prefix.Ipv4.sin_family = v112;
          *(_QWORD *)&Row.DestinationPrefix.Prefix.Ipv6.sin6_port = *(_QWORD *)&Address[0].S_un.S_un_b.s_b1;
          *(struct in_addr *)(&Row.DestinationPrefix.Prefix.si_family + 5) = Address[2];
          Row.DestinationPrefix.Prefix.Ipv6.sin6_addr.u.Word[3] = Address[3].S_un.S_un_w.s_w1;
          Row.NextHop.Ipv4.sin_family = v114;
          *(_QWORD *)&Row.NextHop.Ipv6.sin6_port = *(_QWORD *)&v115[0].S_un.S_un_b.s_b1;
          *(struct in_addr *)(&Row.NextHop.si_family + 5) = v115[2];
          Row.NextHop.Ipv6.sin6_addr.u.Word[3] = v115[3].S_un.S_un_w.s_w1;
        }
        else if ( v93 == 6 )
        {
          v112 = 23;
          v84 = RtlIpv6StringToAddressExW(
                  L"::",
                  (struct in6_addr *)&Address[1].S_un.S_un_w.s_w2,
                  (PULONG)&Address[5].S_un.S_un_w.s_w2,
                  Port);
          if ( v84 < 0 )
          {
            v85 = wil::details::in1diag3::Return_NtStatus(
                    retaddr,
                    (void *)0x2B7,
                    (unsigned int)"onecoreuap\\net\\ux\\mediamanagerbase\\lib\\categorybase.cpp",
                    (const char *)(unsigned int)v84,
                    v91);
            WindowsDeleteString(v94);
            v94 = 0;
            Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v100);
            Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v98);
            Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v99);
            Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v95);
            Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v96);
            Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v92);
            return v85;
          }
          v114 = 23;
          v86 = WindowsGetStringRawBuffer(v94, 0);
          v87 = RtlIpv6StringToAddressExW(
                  v86,
                  (struct in6_addr *)&v115[1].S_un.S_un_w.s_w2,
                  (PULONG)&v115[5].S_un.S_un_w.s_w2,
                  Port);
          if ( v87 < 0 )
          {
            v88 = wil::details::in1diag3::Return_NtStatus(
                    retaddr,
                    (void *)0x2BB,
                    (unsigned int)"onecoreuap\\net\\ux\\mediamanagerbase\\lib\\categorybase.cpp",
                    (const char *)(unsigned int)v87,
                    v91);
            WindowsDeleteString(v94);
            v94 = 0;
            Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v100);
            Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v98);
            Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v99);
            Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v95);
            Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v96);
            Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v92);
            return v88;
          }
          Row.DestinationPrefix.Prefix.Ipv4.sin_family = v112;
          *(_OWORD *)&Row.DestinationPrefix.Prefix.Ipv6.sin6_port = *(_OWORD *)&Address[0].S_un.S_un_b.s_b1;
          *(_OWORD *)(&Row.DestinationPrefix.Prefix.si_family + 6) = *(_OWORD *)&Address[2].S_un.S_un_w.s_w2;
          Row.NextHop.Ipv4.sin_family = v114;
          *(_OWORD *)&Row.NextHop.Ipv6.sin6_port = *(_OWORD *)&v115[0].S_un.S_un_b.s_b1;
          *(_OWORD *)(&Row.NextHop.si_family + 6) = *(_OWORD *)&v115[2].S_un.S_un_w.s_w2;
        }
        v89 = InternalCreateIpForwardEntry2(2, &Row);
        if ( v89 == 5010 )
        {
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
            WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 53, &WPP_426275660baf32778194b91bb4cd93ce_Traceguids);
        }
        else if ( v89 )
        {
          v90 = wil::details::in1diag3::Return_Win32(
                  retaddr,
                  (void *)0x2C8,
                  (unsigned int)"onecoreuap\\net\\ux\\mediamanagerbase\\lib\\categorybase.cpp",
                  (const char *)v89,
                  v91);
          WindowsDeleteString(v94);
          v94 = 0;
          Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v100);
          Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v98);
          Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v99);
          Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v95);
          Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v96);
          Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v92);
          return v90;
        }
        WindowsDeleteString(v94);
      }
      v3 = v111;
      if ( v104 == 1 )
      {
        LOBYTE(k) = 1;
        Windows::Networking::UX::Internal::CategoryBase::_EnsureDhcpEnabled(v111, v93, k);
      }
    }
    SetInterfaceDns(v93, v3, v98);
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0 )
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 54, &WPP_426275660baf32778194b91bb4cd93ce_Traceguids, 0);
    goto LABEL_48;
  }
  v41 = wil::details::in1diag3::Return_Win32(
          retaddr,
          (void *)0x22B,
          (unsigned int)"onecoreuap\\net\\ux\\mediamanagerbase\\lib\\categorybase.cpp",
          (const char *)v40,
          v91);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v100);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v98);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v99);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v95);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v96);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v92);
  return v41;
}

```

## disassembly

```asm
0x180028aa8  mov     [rsp+arg_18], rbx
0x180028aad  push    rsi
0x180028aae  push    rdi
0x180028aaf  push    r13
0x180028ab1  push    r14
0x180028ab3  push    r15
0x180028ab5  sub     rsp, 180h
0x180028abc  mov     rax, cs:__security_cookie
0x180028ac3  xor     rax, rsp
0x180028ac6  mov     [rsp+1A8h+var_38], rax
0x180028ace  mov     dword ptr [rsp+1A8h+var_168], r8d
0x180028ad3  mov     rsi, rdx
0x180028ad6  mov     [rsp+1A8h+var_F8], rdx
0x180028ade  mov     rdi, rcx
0x180028ae1  lea     rax, WPP_GLOBAL_Control
0x180028ae8  mov     rcx, cs:WPP_GLOBAL_Control
0x180028aef  cmp     rcx, rax
0x180028af2  jz      short loc_180028B0F
0x180028af4  test    byte ptr [rcx+1Ch], 40h
0x180028af8  jz      short loc_180028B0F
0x180028afa  mov     edx, 2Dh ; '-'
0x180028aff  lea     r8, WPP_426275660baf32778194b91bb4cd93ce_Traceguids
0x180028b06  mov     rcx, [rcx+10h]
0x180028b0a  call    WPP_SF_
0x180028b0f  xor     r15d, r15d
0x180028b12  mov     [rsp+1A8h+var_124], r15d
0x180028b1a  mov     rax, [rdi]
0x180028b1d  lea     rdx, [rsp+1A8h+var_124]
0x180028b25  mov     rcx, rdi
0x180028b28  mov     rax, [rax+0B0h]
0x180028b2f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180028b34  mov     ebx, eax
0x180028b36  test    eax, eax
0x180028b38  jns     short loc_180028B5D
0x180028b3a  mov     rcx, [rsp+1A8h]; this
0x180028b42  mov     r9d, eax; char *
0x180028b45  lea     r8, aOnecoreuapNetU_14; "onecoreuap\\net\\ux\\mediamanagerbase\\"...
0x180028b4c  mov     edx, 1E9h; void *
0x180028b51  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180028b56  mov     eax, ebx
0x180028b58  jmp     loc_18002A038
0x180028b5d  mov     [rsp+1A8h+var_170], 4
0x180028b65  mov     [rsp+1A8h+var_178], r15
0x180028b6a  mov     rax, [rdi]
0x180028b6d  lea     rdx, [rsp+1A8h+var_170]
0x180028b72  mov     rcx, rdi
0x180028b75  mov     rax, [rax+30h]
0x180028b79  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180028b7e  mov     ebx, eax
0x180028b80  test    eax, eax
0x180028b82  jns     short loc_180028BB2
0x180028b84  mov     rcx, [rsp+1A8h]; this
0x180028b8c  mov     r9d, eax; char *
0x180028b8f  lea     r8, aOnecoreuapNetU_14; "onecoreuap\\net\\ux\\mediamanagerbase\\"...
0x180028b96  mov     edx, 1EDh; void *
0x180028b9b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180028ba0  nop
0x180028ba1  lea     rcx, [rsp+1A8h+var_178]
0x180028ba6  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180028bab  mov     eax, ebx
0x180028bad  jmp     loc_18002A038
0x180028bb2  mov     rax, [rdi]
0x180028bb5  mov     rbx, [rax+40h]
0x180028bb9  lea     rcx, [rsp+1A8h+var_178]
0x180028bbe  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180028bc3  lea     rdx, [rsp+1A8h+var_178]
0x180028bc8  mov     rcx, rdi
0x180028bcb  mov     rax, rbx
0x180028bce  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180028bd3  mov     ebx, eax
0x180028bd5  test    eax, eax
0x180028bd7  jns     short loc_180028C07
0x180028bd9  mov     rcx, [rsp+1A8h]; this
0x180028be1  mov     r9d, eax; char *
0x180028be4  lea     r8, aOnecoreuapNetU_14; "onecoreuap\\net\\ux\\mediamanagerbase\\"...
0x180028beb  mov     edx, 1EEh; void *
0x180028bf0  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180028bf5  nop
0x180028bf6  lea     rcx, [rsp+1A8h+var_178]
0x180028bfb  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180028c00  mov     eax, ebx
0x180028c02  jmp     loc_18002A038
0x180028c07  mov     r13d, 1
0x180028c0d  cmp     [rsp+1A8h+var_124], r13d
0x180028c15  jz      short loc_180028C24
0x180028c17  cmp     [rsp+1A8h+var_124], 4
0x180028c1f  mov     bl, r15b
0x180028c22  jnz     short loc_180028C27
0x180028c24  mov     bl, r13b
0x180028c27  mov     edx, [rsp+1A8h+var_170]
0x180028c2b  mov     rcx, rsi
0x180028c2e  call    ?_GetDhcpEnabled@CategoryBase@Internal@UX@Networking@Windows@@CA_NAEBU_GUID@@W4IpFamily@345@@Z; Windows::Networking::UX::Internal::CategoryBase::_GetDhcpEnabled(_GUID const &,Windows::Networking::UX::IpFamily)
0x180028c33  cmp     bl, al
0x180028c35  jnz     short loc_180028C41
0x180028c37  mov     [rsp+1A8h+var_120], r15d
0x180028c3f  jmp     short loc_180028C6D
0x180028c41  test    al, al
0x180028c43  jz      short loc_180028C5D
0x180028c45  test    bl, bl
0x180028c47  jnz     loc_18002A011
0x180028c4d  mov     r14d, 2
0x180028c53  mov     [rsp+1A8h+var_120], r14d
0x180028c5b  jmp     short loc_180028C73
0x180028c5d  test    bl, bl
0x180028c5f  jz      loc_18002A011
0x180028c65  mov     [rsp+1A8h+var_120], r13d
0x180028c6d  mov     r14d, 2
0x180028c73  mov     [rsp+1A8h+var_118], r15d
0x180028c7b  mov     rcx, [rsp+1A8h+var_178]
0x180028c80  test    rcx, rcx
0x180028c83  jz      short loc_180028CCD
0x180028c85  mov     rax, [rcx]
0x180028c88  lea     rdx, [rsp+1A8h+var_118]
0x180028c90  mov     rax, [rax+38h]
0x180028c94  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180028c99  mov     ebx, eax
0x180028c9b  test    eax, eax
0x180028c9d  jns     short loc_180028CCD
0x180028c9f  mov     rcx, [rsp+1A8h]; this
0x180028ca7  mov     r9d, eax; char *
0x180028caa  lea     r8, aOnecoreuapNetU_14; "onecoreuap\\net\\ux\\mediamanagerbase\\"...
0x180028cb1  mov     edx, 1F5h; void *
0x180028cb6  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180028cbb  nop
0x180028cbc  lea     rcx, [rsp+1A8h+var_178]
0x180028cc1  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180028cc6  mov     eax, ebx
0x180028cc8  jmp     loc_18002A038
0x180028ccd  mov     [rsp+1A8h+var_158], r15
0x180028cd2  mov     rax, [rdi]
0x180028cd5  mov     rbx, [rax+48h]
0x180028cd9  lea     rcx, [rsp+1A8h+var_158]
0x180028cde  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180028ce3  lea     rdx, [rsp+1A8h+var_158]
0x180028ce8  mov     rcx, rdi
0x180028ceb  mov     rax, rbx
0x180028cee  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180028cf3  mov     ebx, eax
0x180028cf5  test    eax, eax
0x180028cf7  jns     short loc_180028D32
0x180028cf9  mov     rcx, [rsp+1A8h]; this
0x180028d01  mov     r9d, eax; char *
0x180028d04  lea     r8, aOnecoreuapNetU_14; "onecoreuap\\net\\ux\\mediamanagerbase\\"...
0x180028d0b  mov     edx, 1FAh; void *
0x180028d10  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180028d15  nop
0x180028d16  lea     rcx, [rsp+1A8h+var_158]
0x180028d1b  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180028d20  nop
0x180028d21  lea     rcx, [rsp+1A8h+var_178]
0x180028d26  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180028d2b  mov     eax, ebx
0x180028d2d  jmp     loc_18002A038
0x180028d32  mov     [rsp+1A8h+var_160], r15
0x180028d37  mov     rax, [rdi]
0x180028d3a  mov     rbx, [rax+50h]
0x180028d3e  lea     rcx, [rsp+1A8h+var_160]
0x180028d43  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180028d48  lea     rdx, [rsp+1A8h+var_160]
0x180028d4d  mov     rcx, rdi
0x180028d50  mov     rax, rbx
0x180028d53  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180028d58  mov     ebx, eax
0x180028d5a  test    eax, eax
0x180028d5c  jns     short loc_180028DA2
0x180028d5e  mov     rcx, [rsp+1A8h]; this
0x180028d66  mov     r9d, eax; char *
0x180028d69  lea     r8, aOnecoreuapNetU_14; "onecoreuap\\net\\ux\\mediamanagerbase\\"...
0x180028d70  mov     edx, 1FDh; void *
0x180028d75  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180028d7a  nop
0x180028d7b  lea     rcx, [rsp+1A8h+var_160]
0x180028d80  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180028d85  nop
0x180028d86  lea     rcx, [rsp+1A8h+var_158]
0x180028d8b  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180028d90  nop
0x180028d91  lea     rcx, [rsp+1A8h+var_178]
0x180028d96  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180028d9b  mov     eax, ebx
0x180028d9d  jmp     loc_18002A038
0x180028da2  mov     [rsp+1A8h+var_114], r15d
0x180028daa  mov     rcx, [rsp+1A8h+var_160]
0x180028daf  test    rcx, rcx
0x180028db2  jz      short loc_180028E12
0x180028db4  mov     rax, [rcx]
0x180028db7  lea     rdx, [rsp+1A8h+var_114]
0x180028dbf  mov     rax, [rax+38h]
0x180028dc3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180028dc8  mov     ebx, eax
0x180028dca  test    eax, eax
0x180028dcc  jns     short loc_180028E12
0x180028dce  mov     rcx, [rsp+1A8h]; this
0x180028dd6  mov     r9d, eax; char *
0x180028dd9  lea     r8, aOnecoreuapNetU_14; "onecoreuap\\net\\ux\\mediamanagerbase\\"...
0x180028de0  mov     edx, 202h; void *
0x180028de5  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180028dea  nop
0x180028deb  lea     rcx, [rsp+1A8h+var_160]
0x180028df0  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180028df5  nop
0x180028df6  lea     rcx, [rsp+1A8h+var_158]
0x180028dfb  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180028e00  nop
0x180028e01  lea     rcx, [rsp+1A8h+var_178]
0x180028e06  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180028e0b  mov     eax, ebx
0x180028e0d  jmp     loc_18002A038
0x180028e12  mov     [rsp+1A8h+var_140], r15
0x180028e17  mov     [rsp+1A8h+var_148], r15
0x180028e1c  mov     rax, [rdi]
0x180028e1f  mov     rbx, [rax+58h]
0x180028e23  lea     rcx, [rsp+1A8h+var_140]
0x180028e28  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180028e2d  lea     rdx, [rsp+1A8h+var_140]
0x180028e32  mov     rcx, rdi
0x180028e35  mov     rax, rbx
0x180028e38  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180028e3d  mov     ebx, eax
0x180028e3f  test    eax, eax
0x180028e41  jns     short loc_180028E9D
0x180028e43  mov     rcx, [rsp+1A8h]; this
0x180028e4b  mov     r9d, eax; char *
0x180028e4e  lea     r8, aOnecoreuapNetU_14; "onecoreuap\\net\\ux\\mediamanagerbase\\"...
0x180028e55  mov     edx, 208h; void *
0x180028e5a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180028e5f  nop
0x180028e60  lea     rcx, [rsp+1A8h+var_148]
0x180028e65  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180028e6a  nop
0x180028e6b  lea     rcx, [rsp+1A8h+var_140]
0x180028e70  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180028e75  nop
0x180028e76  lea     rcx, [rsp+1A8h+var_160]
0x180028e7b  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180028e80  nop
0x180028e81  lea     rcx, [rsp+1A8h+var_158]
0x180028e86  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180028e8b  nop
0x180028e8c  lea     rcx, [rsp+1A8h+var_178]
0x180028e91  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180028e96  mov     eax, ebx
0x180028e98  jmp     loc_18002A038
0x180028e9d  mov     rax, [rdi]
0x180028ea0  mov     rbx, [rax+60h]
0x180028ea4  lea     rcx, [rsp+1A8h+var_148]
0x180028ea9  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180028eae  lea     rdx, [rsp+1A8h+var_148]
0x180028eb3  mov     rcx, rdi
0x180028eb6  mov     rax, rbx
0x180028eb9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180028ebe  mov     ebx, eax
0x180028ec0  test    eax, eax
0x180028ec2  jns     short loc_180028F1E
0x180028ec4  mov     rcx, [rsp+1A8h]; this
0x180028ecc  mov     r9d, eax; char *
0x180028ecf  lea     r8, aOnecoreuapNetU_14; "onecoreuap\\net\\ux\\mediamanagerbase\\"...
0x180028ed6  mov     edx, 209h; void *
0x180028edb  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180028ee0  nop
0x180028ee1  lea     rcx, [rsp+1A8h+var_148]
0x180028ee6  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180028eeb  nop
0x180028eec  lea     rcx, [rsp+1A8h+var_140]
0x180028ef1  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180028ef6  nop
0x180028ef7  lea     rcx, [rsp+1A8h+var_160]
0x180028efc  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180028f01  nop
0x180028f02  lea     rcx, [rsp+1A8h+var_158]
0x180028f07  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180028f0c  nop
0x180028f0d  lea     rcx, [rsp+1A8h+var_178]
0x180028f12  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180028f17  mov     eax, ebx
0x180028f19  jmp     loc_18002A038
0x180028f1e  mov     [rsp+1A8h+var_11C], r15d
0x180028f26  mov     rcx, [rsp+1A8h+var_148]
0x180028f2b  test    rcx, rcx
0x180028f2e  jz      short loc_180028FA4
0x180028f30  mov     rax, [rcx]
0x180028f33  lea     rdx, [rsp+1A8h+var_11C]
0x180028f3b  mov     rax, [rax+38h]
0x180028f3f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180028f44  mov     ebx, eax
0x180028f46  test    eax, eax
0x180028f48  jns     short loc_180028FA4
0x180028f4a  mov     rcx, [rsp+1A8h]; this
0x180028f52  mov     r9d, eax; char *
0x180028f55  lea     r8, aOnecoreuapNetU_14; "onecoreuap\\net\\ux\\mediamanagerbase\\"...
0x180028f5c  mov     edx, 20Eh; void *
0x180028f61  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180028f66  nop
0x180028f67  lea     rcx, [rsp+1A8h+var_148]
0x180028f6c  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180028f71  nop
0x180028f72  lea     rcx, [rsp+1A8h+var_140]
0x180028f77  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180028f7c  nop
0x180028f7d  lea     rcx, [rsp+1A8h+var_160]
  ... truncated ...
```
