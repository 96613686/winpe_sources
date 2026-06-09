# Container::Manager::Core::Details::ConfigurationBuilder::CollectKryptonColdBootInjectableRegistryKeys(Container::Manager::Hcs::KryptonConfiguration &,_GUID const &,bool,utl::optional<Container::Manager::Common::HotPatches> const &,bool,Container::Manager::Core::Details::ContainerStorage const &)

- ea: `0x1800904ec`
- end: `0x180091298`
- name: `?CollectKryptonColdBootInjectableRegistryKeys@ConfigurationBuilder@Details@Core@Manager@Container@@AEBAJAEAUKryptonConfiguration@Hcs@45@AEBU_GUID@@_NAEBV?$optional@UHotPatches@Common@Manager@Container@@@utl@@2AEBVContainerStorage@2345@@Z`
- size: `3500`
- prototype: ``
- caller_count: `1`
- callee_count: `21`
- tags: `file_ops, registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x1800914d0`

## callees

- `0x180004bd0`
- `0x180004fc4`
- `0x180005704`
- `0x1800067cc`
- `0x18000da68`
- `0x18000da88`
- `0x180016774`
- `0x18002c5b4`
- `0x180075d50`
- `0x180082cc8`
- `0x18008bd08`
- `0x18008d428`
- `0x18008efac`
- `0x18008fd24`
- `0x1800904ec`
- `0x180095480`
- `0x1800975e0`
- `0x180097690`
- `0x18011f0f8`
- `0x18011f758`
- `0x1801231bc`

## import_xrefs

- `api-ms-win-core-sysinfo-l1-1-0!GetComputerNameExW` at `0x18009091d`
- `api-ms-win-core-sysinfo-l1-1-0!GetComputerNameExW` at `0x180090969`
- `api-ms-win-core-sysinfo-l1-1-0!GetComputerNameExW` at `0x180090b8d`
- `api-ms-win-core-sysinfo-l1-1-0!GetComputerNameExW` at `0x18009091d`
- `api-ms-win-core-sysinfo-l1-1-0!GetComputerNameExW` at `0x180090969`
- `api-ms-win-core-sysinfo-l1-1-0!GetComputerNameExW` at `0x180090b8d`
- `api-ms-win-core-sysinfo-l1-2-1!DnsHostnameToComputerNameExW` at `0x180090bcd`
- `api-ms-win-core-sysinfo-l1-2-1!DnsHostnameToComputerNameExW` at `0x180090bcd`

## string_xrefs

- `0x18009059d`: `onecore\base\gendrv\silos\clem\core\lib\configurationbuilder.cpp`
- `0x1800906a2`: `onecore\base\gendrv\silos\clem\core\lib\configurationbuilder.cpp`
- `0x180090752`: `onecore\base\gendrv\silos\clem\core\lib\configurationbuilder.cpp`
- `0x1800907e6`: `onecore\base\gendrv\silos\clem\core\lib\configurationbuilder.cpp`
- `0x180090982`: `onecore\base\gendrv\silos\clem\core\lib\configurationbuilder.cpp`
- `0x180090a04`: `onecore\base\gendrv\silos\clem\core\lib\configurationbuilder.cpp`
- `0x180090a7f`: `onecore\base\gendrv\silos\clem\core\lib\configurationbuilder.cpp`
- `0x180090ba2`: `onecore\base\gendrv\silos\clem\core\lib\configurationbuilder.cpp`
- `0x180090c1e`: `onecore\base\gendrv\silos\clem\core\lib\configurationbuilder.cpp`
- `0x180090d2d`: `onecore\base\gendrv\silos\clem\core\lib\configurationbuilder.cpp`
- `0x180090ed7`: `onecore\base\gendrv\silos\clem\core\lib\configurationbuilder.cpp`
- `0x180090f73`: `onecore\base\gendrv\silos\clem\core\lib\configurationbuilder.cpp`
- `0x180090ff8`: `onecore\base\gendrv\silos\clem\core\lib\configurationbuilder.cpp`
- `0x1800910b2`: `onecore\base\gendrv\silos\clem\core\lib\configurationbuilder.cpp`
- `0x1800911da`: `onecore\base\gendrv\silos\clem\core\lib\configurationbuilder.cpp`
- `0x1800907b0`: `ControlSet001\Services\Tcpip\Parameters`
- `0x180090c87`: `ControlSet001\Control\ComputerName\ComputerName`
- `0x180090cd0`: `ComputerName`
- `0x180091179`: `ForceImcUpdate`

## pseudocode

```c
__int64 __fastcall Container::Manager::Core::Details::ConfigurationBuilder::CollectKryptonColdBootInjectableRegistryKeys(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        char a4,
        __int64 a5,
        char a6,
        __int64 a7)
{
  int v11; // eax
  __int64 v12; // rdx
  unsigned int v13; // ebx
  __int64 v14; // rdx
  __int64 v15; // rdx
  void *v16; // rcx
  int v17; // eax
  __int64 v18; // rdx
  unsigned int LastError; // edi
  unsigned int v20; // esi
  __int64 v21; // rdx
  __int64 v22; // rcx
  DWORD v23; // r8d
  unsigned __int64 v24; // rsi
  _WORD *v25; // rax
  _WORD *v26; // rdi
  const char *v27; // r9
  const struct std::nothrow_t *v28; // rdx
  __int64 v29; // r8
  const struct std::nothrow_t *v30; // rdx
  const struct std::nothrow_t *v31; // rdx
  __int64 v32; // rdx
  _WORD *v33; // rcx
  _WORD *v34; // rax
  const char *v35; // r9
  __int64 v36; // rdx
  __int64 v37; // rdx
  __int64 v38; // rdx
  __int64 v39; // rdx
  __int64 v40; // rdx
  int StorageChain; // eax
  int v42; // eax
  __int64 v43; // rdx
  __int64 v44; // rdx
  DWORD *v46; // [rsp+20h] [rbp-E0h]
  const wchar_t *v47; // [rsp+40h] [rbp-C0h] BYREF
  __int64 v48; // [rsp+48h] [rbp-B8h]
  LPCWSTR Hostname; // [rsp+50h] [rbp-B0h] BYREF
  _WORD *v50; // [rsp+58h] [rbp-A8h]
  _WORD v51[8]; // [rsp+60h] [rbp-A0h] BYREF
  DWORD v52; // [rsp+70h] [rbp-90h] BYREF
  __int16 v53; // [rsp+74h] [rbp-8Ch]
  DWORD nSize[2]; // [rsp+80h] [rbp-80h] BYREF
  __int64 v55; // [rsp+88h] [rbp-78h]
  const wchar_t *v56; // [rsp+90h] [rbp-70h] BYREF
  __int64 v57; // [rsp+98h] [rbp-68h]
  void *v58; // [rsp+A0h] [rbp-60h] BYREF
  char *v59; // [rsp+A8h] [rbp-58h]
  _WORD v60[8]; // [rsp+B0h] [rbp-50h] BYREF
  int v61; // [rsp+C0h] [rbp-40h] BYREF
  void *v62; // [rsp+C8h] [rbp-38h]
  _WORD *v63; // [rsp+D0h] [rbp-30h]
  _WORD v64[8]; // [rsp+D8h] [rbp-28h] BYREF
  _QWORD v65[5]; // [rsp+E8h] [rbp-18h] BYREF
  int v66; // [rsp+110h] [rbp+10h] BYREF
  void *v67; // [rsp+118h] [rbp+18h]
  _WORD *v68; // [rsp+120h] [rbp+20h]
  _WORD v69[8]; // [rsp+128h] [rbp+28h] BYREF
  _QWORD v70[5]; // [rsp+138h] [rbp+38h] BYREF
  void *v71; // [rsp+160h] [rbp+60h] BYREF
  char *v72; // [rsp+168h] [rbp+68h]
  _WORD v73[8]; // [rsp+170h] [rbp+70h] BYREF
  void *v74[2]; // [rsp+180h] [rbp+80h] BYREF
  __int64 v75; // [rsp+190h] [rbp+90h]
  _QWORD v76[4]; // [rsp+198h] [rbp+98h] BYREF
  void *v77; // [rsp+1B8h] [rbp+B8h] BYREF
  char *v78; // [rsp+1C0h] [rbp+C0h]
  _WORD v79[12]; // [rsp+1C8h] [rbp+C8h] BYREF
  int v80; // [rsp+1E0h] [rbp+E0h] BYREF
  void *v81; // [rsp+1E8h] [rbp+E8h]
  _WORD *v82; // [rsp+1F0h] [rbp+F0h]
  _WORD v83[8]; // [rsp+1F8h] [rbp+F8h] BYREF
  _QWORD v84[5]; // [rsp+208h] [rbp+108h] BYREF
  int v85; // [rsp+230h] [rbp+130h] BYREF
  void *v86; // [rsp+238h] [rbp+138h]
  _WORD *v87; // [rsp+240h] [rbp+140h]
  _WORD v88[8]; // [rsp+248h] [rbp+148h] BYREF
  _QWORD v89[5]; // [rsp+258h] [rbp+158h] BYREF
  int v90; // [rsp+280h] [rbp+180h] BYREF
  void *v91; // [rsp+288h] [rbp+188h]
  _WORD *v92; // [rsp+290h] [rbp+190h]
  _WORD v93[8]; // [rsp+298h] [rbp+198h] BYREF
  _QWORD v94[5]; // [rsp+2A8h] [rbp+1A8h] BYREF
  WCHAR Buffer[16]; // [rsp+2D0h] [rbp+1D0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+338h] [rbp+238h]

  v76[0] = v76;
  v76[1] = v76;
  v76[2] = v76;
  v76[3] = 0;
  v11 = Container::Manager::Core::Details::ConfigurationBuilder::CollectInjectableAutoLoggers(a1, v76);
  v13 = v11;
  if ( v11 < 0 )
  {
    v14 = 2815;
LABEL_6:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v14,
      (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\core\\lib\\configurationbuilder.cpp",
      (const char *)(unsigned int)v11,
      (int)v46);
    goto LABEL_134;
  }
  if ( *(_BYTE *)(a5 + 48) )
  {
    v11 = Container::Manager::Core::Details::ConfigurationBuilder::CollectInjectableHotPatches(a5, v76);
    v13 = v11;
    if ( v11 < 0 )
    {
      v14 = 2819;
      goto LABEL_6;
    }
  }
  v80 = 0;
  v81 = v83;
  v82 = v83;
  v83[0] = 0;
  v84[0] = v84;
  v84[1] = v84;
  v84[2] = v84;
  v84[3] = 0;
  *(_QWORD *)nSize = L"ControlSet001\\Control\\CrashControl";
  v55 = 34;
  if ( !(unsigned __int8)Container::Manager::Hcs::InjectableRegistryKey::Initialize(&v80, v12, nSize) )
  {
    v15 = 2825;
    goto LABEL_13;
  }
  *(_QWORD *)nSize = L"CrashDumpEnabled";
  v55 = 16;
  if ( !(unsigned __int8)Container::Manager::Hcs::InjectableRegistryKey::AddDwordValue(&v80, nSize, 2) )
  {
    v15 = 2842;
    goto LABEL_13;
  }
  utl::_Tree<Container::Manager::Hcs::InjectableRegistryKey,Container::Manager::Hcs::InjectableRegistryKey,utl::less<Container::Manager::Hcs::InjectableRegistryKey>,utl::allocator<Container::Manager::Hcs::InjectableRegistryKey>,0>::emplace<Container::Manager::Hcs::InjectableRegistryKey,0>(
    v76,
    &v47,
    &v80);
  if ( !v47 )
  {
    v15 = 2845;
LABEL_13:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v15,
      (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\core\\lib\\configurationbuilder.cpp",
      (const char *)0x8007000ELL,
      (int)v46);
    utl::_Tree<Container::Manager::Hcs::InjectableRegistryValue,Container::Manager::Hcs::InjectableRegistryValue,utl::less<Container::Manager::Hcs::InjectableRegistryValue>,utl::allocator<Container::Manager::Hcs::InjectableRegistryValue>,0>::clear(v84);
    v16 = v81;
    if ( v81 == v83 )
    {
LABEL_15:
      v13 = -2147024882;
      goto LABEL_134;
    }
LABEL_14:
    operator delete(v16, (const struct std::nothrow_t *)&std::nothrow);
    goto LABEL_15;
  }
  utl::_Tree<Container::Manager::Hcs::InjectableRegistryValue,Container::Manager::Hcs::InjectableRegistryValue,utl::less<Container::Manager::Hcs::InjectableRegistryValue>,utl::allocator<Container::Manager::Hcs::InjectableRegistryValue>,0>::clear(v84);
  if ( v81 != v83 )
    operator delete(v81, (const struct std::nothrow_t *)&std::nothrow);
  Hostname = v51;
  v50 = v51;
  v51[0] = 0;
  v17 = Csl::GuidToString(a3, &Hostname);
  LastError = v17;
  v20 = 0;
  if ( v17 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xB22,
      (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\core\\lib\\configurationbuilder.cpp",
      (const char *)(unsigned int)v17,
      (int)v46);
LABEL_20:
    if ( Hostname != v51 )
      operator delete((void *)Hostname, (const struct std::nothrow_t *)&std::nothrow);
    v13 = LastError;
    goto LABEL_134;
  }
  v61 = 0;
  v62 = v64;
  v63 = v64;
  v64[0] = 0;
  v65[0] = v65;
  v65[1] = v65;
  v65[2] = v65;
  v65[3] = 0;
  *(_QWORD *)nSize = L"ControlSet001\\Services\\Tcpip\\Parameters";
  v55 = 39;
  if ( !(unsigned __int8)Container::Manager::Hcs::InjectableRegistryKey::Initialize(&v61, v18, nSize) )
  {
    v21 = 2855;
LABEL_25:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v21,
      (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\core\\lib\\configurationbuilder.cpp",
      (const char *)0x8007000ELL,
      (int)v46);
LABEL_55:
    utl::_Tree<Container::Manager::Hcs::InjectableRegistryValue,Container::Manager::Hcs::InjectableRegistryValue,utl::less<Container::Manager::Hcs::InjectableRegistryValue>,utl::allocator<Container::Manager::Hcs::InjectableRegistryValue>,0>::clear(v65);
    v33 = v62;
    v34 = v64;
    goto LABEL_56;
  }
  if ( a4 && (*(_DWORD *)(*(_QWORD *)(a1 + 8) + 96LL) & 0x10) != 0 )
  {
    *(_QWORD *)nSize = L"PortTrackerEnabledMode";
    v55 = 22;
    if ( !(unsigned __int8)Container::Manager::Hcs::InjectableRegistryKey::AddDwordValue(&v61, nSize, 1) )
    {
      v21 = 2862;
      goto LABEL_25;
    }
    v23 = *(_DWORD *)Feature_HnsWcosLoopback__descriptor;
    if ( (*(_DWORD *)Feature_HnsWcosLoopback__descriptor & 4) == 0 )
    {
      *(_QWORD *)nSize = *(_QWORD *)wil::details::FeatureImpl<__WilFeatureTraits_Feature_HnsWcosLoopback>::GetCachedFeatureEnabledState(
                                      v22,
                                      nSize);
      v23 = nSize[0];
    }
    v52 = 0;
    v53 = 3;
    v46 = &v52;
    wil::details::ReportUsageToService(&unk_18021F618, 23636350, (v23 >> 10) & 1, (v23 >> 11) & 1);
    *(_QWORD *)nSize = L"WcosLoopbackEnabled";
    v55 = 19;
    if ( !(unsigned __int8)Container::Manager::Hcs::InjectableRegistryKey::AddDwordValue(&v61, nSize, 1) )
    {
      v21 = 2866;
      goto LABEL_25;
    }
  }
  v58 = v60;
  v59 = (char *)v60;
  v60[0] = 0;
  if ( !a4 || (*(_DWORD *)(*(_QWORD *)(a1 + 8) + 96LL) & 0x10) == 0 )
  {
    if ( !(unsigned __int8)utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::assign(
                             &v58,
                             Hostname,
                             v50 - Hostname) )
    {
      v32 = 2893;
      goto LABEL_52;
    }
LABEL_49:
    v56 = (const wchar_t *)v58;
    v57 = (v59 - (_BYTE *)v58) >> 1;
    v47 = L"NV HostName";
    v48 = 11;
    if ( !(unsigned __int8)Container::Manager::Hcs::InjectableRegistryKey::AddStringValue(&v61, &v47, &v56) )
    {
      v32 = 2897;
LABEL_52:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v32,
        (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\core\\lib\\configurationbuilder.cpp",
        (const char *)0x8007000ELL,
        (int)v46);
LABEL_53:
      if ( v58 != v60 )
        operator delete(v58, (const struct std::nothrow_t *)&std::nothrow);
      goto LABEL_55;
    }
    utl::_Tree<Container::Manager::Hcs::InjectableRegistryKey,Container::Manager::Hcs::InjectableRegistryKey,utl::less<Container::Manager::Hcs::InjectableRegistryKey>,utl::allocator<Container::Manager::Hcs::InjectableRegistryKey>,0>::emplace<Container::Manager::Hcs::InjectableRegistryKey,0>(
      v76,
      &v47,
      &v61);
    if ( !v47 )
    {
      v32 = 2900;
      goto LABEL_52;
    }
    if ( v58 != v60 )
      operator delete(v58, (const struct std::nothrow_t *)&std::nothrow);
    utl::_Tree<Container::Manager::Hcs::InjectableRegistryValue,Container::Manager::Hcs::InjectableRegistryValue,utl::less<Container::Manager::Hcs::InjectableRegistryValue>,utl::allocator<Container::Manager::Hcs::InjectableRegistryValue>,0>::clear(v65);
    if ( v62 != v64 )
      operator delete(v62, (const struct std::nothrow_t *)&std::nothrow);
    v52 = 16;
    if ( a4 && (*(_DWORD *)(*(_QWORD *)(a1 + 8) + 96LL) & 0x10) != 0 )
    {
      if ( !GetComputerNameExW(ComputerNameNetBIOS, Buffer, &v52) )
      {
        v36 = 2915;
LABEL_72:
        LastError = wil::details::in1diag3::Return_GetLastError(
                      retaddr,
                      (void *)v36,
                      (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\core\\lib\\configurationbuilder.cpp",
                      v35);
        goto LABEL_20;
      }
    }
    else if ( !DnsHostnameToComputerNameExW(Hostname, Buffer, &v52) )
    {
      v36 = 2921;
      goto LABEL_72;
    }
    v71 = v73;
    v72 = (char *)v73;
    v73[0] = 0;
    if ( !(unsigned __int8)utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::assign(
                             &v71,
                             Buffer,
                             v52) )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xB6D,
        (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\core\\lib\\configurationbuilder.cpp",
        (const char *)0x8007000ELL,
        (int)v46);
LABEL_85:
      v34 = v73;
      v33 = v71;
      goto LABEL_56;
    }
    v85 = 0;
    v86 = v88;
    v87 = v88;
    v88[0] = 0;
    v89[0] = v89;
    v89[1] = v89;
    v89[2] = v89;
    v89[3] = 0;
    v47 = L"ControlSet001\\Control\\ComputerName\\ComputerName";
    v48 = 47;
    if ( !(unsigned __int8)Container::Manager::Hcs::InjectableRegistryKey::Initialize(&v85, v37, &v47) )
    {
      v38 = 2930;
      goto LABEL_83;
    }
    v47 = (const wchar_t *)v71;
    v48 = (v72 - (_BYTE *)v71) >> 1;
    v56 = L"ComputerName";
    v57 = 12;
    if ( !(unsigned __int8)Container::Manager::Hcs::InjectableRegistryKey::AddStringValue(&v85, &v56, &v47) )
    {
      v38 = 2933;
      goto LABEL_83;
    }
    utl::_Tree<Container::Manager::Hcs::InjectableRegistryKey,Container::Manager::Hcs::InjectableRegistryKey,utl::less<Container::Manager::Hcs::InjectableRegistryKey>,utl::allocator<Container::Manager::Hcs::InjectableRegistryKey>,0>::emplace<Container::Manager::Hcs::InjectableRegistryKey,0>(
      v76,
      &v47,
      &v85);
    if ( !v47 )
    {
      v38 = 2936;
LABEL_83:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v38,
        (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\core\\lib\\configurationbuilder.cpp",
        (const char *)0x8007000ELL,
        (int)v46);
      utl::_Tree<Container::Manager::Hcs::InjectableRegistryValue,Container::Manager::Hcs::InjectableRegistryValue,utl::less<Container::Manager::Hcs::InjectableRegistryValue>,utl::allocator<Container::Manager::Hcs::InjectableRegistryValue>,0>::clear(v89);
      if ( v86 != v88 )
        operator delete(v86, (const struct std::nothrow_t *)&std::nothrow);
      goto LABEL_85;
    }
    utl::_Tree<Container::Manager::Hcs::InjectableRegistryValue,Container::Manager::Hcs::InjectableRegistryValue,utl::less<Container::Manager::Hcs::InjectableRegistryValue>,utl::allocator<Container::Manager::Hcs::InjectableRegistryValue>,0>::clear(v89);
    if ( v86 != v88 )
      operator delete(v86, (const struct std::nothrow_t *)&std::nothrow);
    if ( v71 != v73 )
      operator delete(v71, (const struct std::nothrow_t *)&std::nothrow);
    v66 = 0;
    v67 = v69;
    v68 = v69;
    v69[0] = 0;
    v70[0] = v70;
    v70[1] = v70;
    v70[2] = v70;
    v70[3] = 0;
    v47 = L"ControlSet001\\Control";
    v48 = 21;
    if ( !(unsigned __int8)Container::Manager::Hcs::InjectableRegistryKey::Initialize(&v66, v39, &v47) )
    {
      v40 = 2944;
LABEL_118:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v40,
        (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\core\\lib\\configurationbuilder.cpp",
        (const char *)0x8007000ELL,
        (int)v46);
      utl::_Tree<Container::Manager::Hcs::InjectableRegistryValue,Container::Manager::Hcs::InjectableRegistryValue,utl::less<Container::Manager::Hcs::InjectableRegistryValue>,utl::allocator<Container::Manager::Hcs::InjectableRegistryValue>,0>::clear(v70);
      v34 = v69;
      v33 = v67;
      goto LABEL_56;
    }
    v47 = L"ContainerType";
    v48 = 13;
    if ( !(unsigned __int8)Container::Manager::Hcs::InjectableRegistryKey::AddDwordValue(&v66, &v47, 4) )
    {
      v40 = 2947;
      goto LABEL_118;
    }
    v47 = Hostname;
    v48 = v50 - Hostname;
    v56 = L"ContainerId";
    v57 = 11;
    if ( !(unsigned __int8)Container::Manager::Hcs::InjectableRegistryKey::AddStringValue(&v66, &v56, &v47) )
    {
      v40 = 2950;
      goto LABEL_118;
    }
    if ( a6 )
    {
      *(__m128i *)v74 = _mm_load_si128((const __m128i *)&_xmm_ffffffffffffffffffffffffffffffff);
      v75 = -1;
      StorageChain = Container::Manager::Core::Details::ContainerStorage::GetStorageChain(a7, v74);
      LastError = StorageChain;
      if ( StorageChain < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0xB99,
          (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\core\\lib\\configurationbuilder.cpp",
          (const char *)(unsigned int)StorageChain,
          (int)v46);
LABEL_99:
        if ( v74[0] != (void *)-1LL )
        {
          v74[1] = v74[0];
          operator delete(v74[0], (const struct std::nothrow_t *)&std::nothrow);
        }
        utl::_Tree<Container::Manager::Hcs::InjectableRegistryValue,Container::Manager::Hcs::InjectableRegistryValue,utl::less<Container::Manager::Hcs::InjectableRegistryValue>,utl::allocator<Container::Manager::Hcs::InjectableRegistryValue>,0>::clear(v70);
        if ( v67 != v69 )
          operator delete(v67, (const struct std::nothrow_t *)&std::nothrow);
        goto LABEL_20;
      }
      v77 = v79;
      v78 = (char *)v79;
      v79[0] = 0;
      v42 = Csl::GuidToString(*(_QWORD *)v74[0], &v77);
      LastError = v42;
      if ( v42 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0xB9C,
          (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\core\\lib\\configurationbuilder.cpp",
          (const char *)(unsigned int)v42,
          (int)v46);
        if ( v77 != v79 )
          operator delete(v77, (const struct std::nothrow_t *)&std::nothrow);
        goto LABEL_99;
      }
      v47 = (const wchar_t *)v77;
      v48 = (v78 - (_BYTE *)v77) >> 1;
      v56 = L"BootUnionGuid";
      v57 = 13;
      if ( !(unsigned __int8)Container::Manager::Hcs::InjectableRegistryKey::AddStringValue(&v66, &v56, &v47) )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0xBA0,
          (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\core\\lib\\configurationbuilder.cpp",
          (const char *)0x8007000ELL,
          (int)v46);
        if ( v77 != v79 )
          operator delete(v77, (const struct std::nothrow_t *)&std::nothrow);
        if ( v74[0] != (void *)-1LL )
        {
          v74[1] = v74[0];
          operator delete(v74[0], (const struct std::nothrow_t *)&std::nothrow);
        }
        utl::_Tree<Container::Manager::Hcs::InjectableRegistryValue,Container::Manager::Hcs::InjectableRegistryValue,utl::less<Container::Manager::Hcs::InjectableRegistryValue>,utl::allocator<Container::Manager::Hcs::InjectableRegistryValue>,0>::clear(v70);
        v33 = v67;
        v34 = v69;
        goto LABEL_56;
      }
      if ( v77 != v79 )
        operator delete(v77, (const struct std::nothrow_t *)&std::nothrow);
      if ( v74[0] != (void *)-1LL )
      {
        v74[1] = v74[0];
        operator delete(v74[0], (const struct std::nothrow_t *)&std::nothrow);
      }
    }
    utl::_Tree<Container::Manager::Hcs::InjectableRegistryKey,Container::Manager::Hcs::InjectableRegistryKey,utl::less<Container::Manager::Hcs::InjectableRegistryKey>,utl::allocator<Container::Manager::Hcs::InjectableRegistryKey>,0>::emplace<Container::Manager::Hcs::InjectableRegistryKey,0>(
      v76,
      &v47,
      &v66);
    if ( !v47 )
    {
      v40 = 2980;
      goto LABEL_118;
    }
    utl::_Tree<Container::Manager::Hcs::InjectableRegistryValue,Container::Manager::Hcs::InjectableRegistryValue,utl::less<Container::Manager::Hcs::InjectableRegistryValue>,utl::allocator<Container::Manager::Hcs::InjectableRegistryValue>,0>::clear(v70);
    if ( v67 != v69 )
      operator delete(v67, (const struct std::nothrow_t *)&std::nothrow);
    v90 = 0;
    v91 = v93;
    v92 = v93;
    v93[0] = 0;
    v94[0] = v94;
    v94[1] = v94;
    v94[2] = v94;
    v94[3] = 0;
    v47 = (const wchar_t *)&dword_1801D0670;
    v48 = 0;
    if ( (unsigned __int8)Container::Manager::Hcs::InjectableRegistryKey::Initialize(&v90, v43, &v47) )
    {
      v47 = L"ForceImcUpdate";
      v48 = 14;
      if ( (unsigned __int8)Container::Manager::Hcs::InjectableRegistryKey::AddDwordValue(&v90, &v47, 1) )
      {
        utl::_Tree<Container::Manager::Hcs::InjectableRegistryKey,Container::Manager::Hcs::InjectableRegistryKey,utl::less<Container::Manager::Hcs::InjectableRegistryKey>,utl::allocator<Container::Manager::Hcs::InjectableRegistryKey>,0>::emplace<Container::Manager::Hcs::InjectableRegistryKey,0>(
          v76,
          &v47,
          &v90);
        if ( v47 )
        {
          utl::_Tree<Container::Manager::Hcs::InjectableRegistryValue,Container::Manager::Hcs::InjectableRegistryValue,utl::less<Container::Manager::Hcs::InjectableRegistryValue>,utl::allocator<Container::Manager::Hcs::InjectableRegistryValue>,0>::clear(v94);
          if ( v91 != v93 )
            operator delete(v91, (const struct std::nothrow_t *)&std::nothrow);
          utl::set<Container::Manager::Hcs::InjectableRegistryKey,utl::less<Container::Manager::Hcs::InjectableRegistryKey>,utl::allocator<Container::Manager::Hcs::InjectableRegistryKey>>::operator=(
            a2 + 552,
            v76);
          goto LABEL_131;
        }
        v44 = 2995;
      }
      else
      {
        v44 = 2992;
      }
    }
    else
    {
      v44 = 2989;
    }
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v44,
      (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\core\\lib\\configurationbuilder.cpp",
      (const char *)0x8007000ELL,
      (int)v46);
    utl::_Tree<Container::Manager::Hcs::InjectableRegistryValue,Container::Manager::Hcs::InjectableRegistryValue,utl::less<Container::Manager::Hcs::InjectableRegistryValue>,utl::allocator<Container::Manager::Hcs::InjectableRegistryValue>,0>::clear(v94);
    v34 = v93;
    v33 = v91;
LABEL_56:
    if ( v33 != v34 )
      operator delete(v33, (const struct std::nothrow_t *)&std::nothrow);
    v16 = (void *)Hostname;
    if ( Hostname == v51 )
      goto LABEL_15;
    goto LABEL_14;
  }
  nSize[0] = 0;
  GetComputerNameExW(ComputerNamePhysicalDnsHostname, 0, nSize);
  v24 = 2LL * nSize[0];
  if ( !is_mul_ok(nSize[0], 2u) )
    v24 = -1;
  v25 = operator new[](v24, (const struct std::nothrow_t *)&std::nothrow);
  v26 = v25;
  if ( !v25 )
  {
    v32 = 2883;
    goto LABEL_52;
  }
  memset_0(v25, 0, v24);
  v20 = 0;
  if ( GetComputerNameExW(ComputerNamePhysicalDnsHostname, v26, nSize) )
  {
    v29 = -1;
    do
      ++v29;
    while ( v26[v29] );
    if ( !(unsigned __int8)utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::assign(
                             &v58,
                             v26,
                             v29) )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xB49,
        (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\core\\lib\\configurationbuilder.cpp",
        (const char *)0x8007000ELL,
        (int)v46);
      operator delete(v26, v31);
      goto LABEL_53;
    }
    operator delete(v26, v30);
    goto LABEL_49;
  }
  v20 = wil::details::in1diag3::Return_GetLastError(
          retaddr,
          (void *)0xB47,
          (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\core\\lib\\configurationbuilder.cpp",
          v27);
  operator delete(v26, v28);
  if ( v58 != v60 )
    operator delete(v58, (const struct std::nothrow_t *)&std::nothrow);
  utl::_Tree<Container::Manager::Hcs::InjectableRegistryValue,Container::Manager::Hcs::InjectableRegistryValue,utl::less<Container::Manager::Hcs::InjectableRegistryValue>,utl::allocator<Container::Manager::Hcs::InjectableRegistryValue>,0>::clear(v65);
  if ( v62 != v64 )
    operator delete(v62, (const struct std::nothrow_t *)&std::nothrow);
LABEL_131:
  if ( Hostname != v51 )
    operator delete((void *)Hostname, (const struct std::nothrow_t *)&std::nothrow);
  v13 = v20;
LABEL_134:
  utl::_Tree<Container::Manager::Hcs::InjectableRegistryKey,Container::Manager::Hcs::InjectableRegistryKey,utl::less<Container::Manager::Hcs::InjectableRegistryKey>,utl::allocator<Container::Manager::Hcs::InjectableRegistryKey>,0>::clear(v76);
  return v13;
}

```

## disassembly

```asm
0x1800904ec  mov     [rsp-8+arg_18], rbx
0x1800904f1  push    rbp
0x1800904f2  push    rsi
0x1800904f3  push    rdi
0x1800904f4  push    r12
0x1800904f6  push    r13
0x1800904f8  push    r14
0x1800904fa  push    r15
0x1800904fc  lea     rbp, [rsp-200h]
0x180090504  sub     rsp, 300h
0x18009050b  mov     rax, cs:__security_cookie
0x180090512  xor     rax, rsp
0x180090515  mov     [rbp+230h+var_40], rax
0x18009051c  mov     r15b, r9b
0x18009051f  mov     rsi, r8
0x180090522  mov     r13, rdx
0x180090525  mov     r14, rcx
0x180090528  mov     rdi, [rbp+230h+arg_20]
0x18009052f  mov     r12, [rbp+230h+arg_30]
0x180090536  lea     rax, [rbp+230h+var_198]
0x18009053d  mov     [rbp+230h+var_198], rax
0x180090544  lea     rax, [rbp+230h+var_198]
0x18009054b  mov     [rbp+230h+var_190], rax
0x180090552  mov     [rbp+230h+var_188], rax
0x180090559  mov     [rbp+230h+var_180], 0
0x180090564  lea     rdx, [rbp+230h+var_198]
0x18009056b  call    ?CollectInjectableAutoLoggers@ConfigurationBuilder@Details@Core@Manager@Container@@AEBAJAEAV?$set@VInjectableRegistryKey@Hcs@Manager@Container@@U?$less@VInjectableRegistryKey@Hcs@Manager@Container@@@utl@@V?$allocator@VInjectableRegistryKey@Hcs@Manager@Container@@@6@@utl@@@Z; Container::Manager::Core::Details::ConfigurationBuilder::CollectInjectableAutoLoggers(utl::set<Container::Manager::Hcs::InjectableRegistryKey,utl::less<Container::Manager::Hcs::InjectableRegistryKey>,utl::allocator<Container::Manager::Hcs::InjectableRegistryKey>> &)
0x180090570  mov     ebx, eax
0x180090572  test    eax, eax
0x180090574  jns     short loc_18009057D
0x180090576  mov     edx, 0AFFh
0x18009057b  jmp     short loc_18009059D
0x18009057d  cmp     byte ptr [rdi+30h], 0
0x180090581  jz      short loc_1800905B8
0x180090583  lea     rdx, [rbp+230h+var_198]
0x18009058a  mov     rcx, rdi
0x18009058d  call    ?CollectInjectableHotPatches@ConfigurationBuilder@Details@Core@Manager@Container@@CAJAEBUHotPatches@Common@45@AEAV?$set@VInjectableRegistryKey@Hcs@Manager@Container@@U?$less@VInjectableRegistryKey@Hcs@Manager@Container@@@utl@@V?$allocator@VInjectableRegistryKey@Hcs@Manager@Container@@@6@@utl@@@Z; Container::Manager::Core::Details::ConfigurationBuilder::CollectInjectableHotPatches(Container::Manager::Common::HotPatches const &,utl::set<Container::Manager::Hcs::InjectableRegistryKey,utl::less<Container::Manager::Hcs::InjectableRegistryKey>,utl::allocator<Container::Manager::Hcs::InjectableRegistryKey>> &)
0x180090592  mov     ebx, eax
0x180090594  test    eax, eax
0x180090596  jns     short loc_1800905B8
0x180090598  mov     edx, 0B03h; void *
0x18009059d  lea     r8, aOnecoreBaseGen_55; "onecore\\base\\gendrv\\silos\\clem\\cor"...
0x1800905a4  mov     r9d, eax; char *
0x1800905a7  mov     rcx, [rbp+238h]; this
0x1800905ae  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800905b3  jmp     loc_18009125F
0x1800905b8  mov     [rbp+230h+var_150], 0
0x1800905c2  lea     rax, [rbp+230h+var_138]
0x1800905c9  mov     [rbp+230h+var_148], rax
0x1800905d0  lea     rax, [rbp+230h+var_138]
0x1800905d7  mov     [rbp+230h+var_140], rax
0x1800905de  xor     eax, eax
0x1800905e0  mov     [rbp+230h+var_138], ax
0x1800905e7  lea     rax, [rbp+230h+var_128]
0x1800905ee  mov     [rbp+230h+var_128], rax
0x1800905f5  lea     rax, [rbp+230h+var_128]
0x1800905fc  mov     [rbp+230h+var_120], rax
0x180090603  mov     [rbp+230h+var_118], rax
0x18009060a  mov     [rbp+230h+var_110], 0
0x180090615  lea     rax, aControlset001C_5; "ControlSet001\\Control\\CrashControl"
0x18009061c  mov     qword ptr [rbp+230h+nSize], rax
0x180090620  mov     [rbp+230h+var_2A8], 22h ; '"'
0x180090628  lea     r8, [rbp+230h+nSize]
0x18009062c  lea     rcx, [rbp+230h+var_150]
0x180090633  call    ?Initialize@InjectableRegistryKey@Hcs@Manager@Container@@QEAA_NW4Hive@1234@V?$basic_string_view@GU?$char_traits@G@utl@@@utl@@@Z; Container::Manager::Hcs::InjectableRegistryKey::Initialize(Container::Manager::Hcs::InjectableRegistryKey::Hive,utl::basic_string_view<ushort,utl::char_traits<ushort>>)
0x180090638  test    al, al
0x18009063a  jnz     short loc_180090643
0x18009063c  mov     edx, 0B09h
0x180090641  jmp     short loc_18009069C
0x180090643  lea     rax, aCrashdumpenabl; "CrashDumpEnabled"
0x18009064a  mov     qword ptr [rbp+230h+nSize], rax
0x18009064e  mov     [rbp+230h+var_2A8], 10h
0x180090656  mov     r8d, 2
0x18009065c  lea     rdx, [rbp+230h+nSize]
0x180090660  lea     rcx, [rbp+230h+var_150]
0x180090667  call    ?AddDwordValue@InjectableRegistryKey@Hcs@Manager@Container@@QEAA_NV?$basic_string_view@GU?$char_traits@G@utl@@@utl@@K@Z; Container::Manager::Hcs::InjectableRegistryKey::AddDwordValue(utl::basic_string_view<ushort,utl::char_traits<ushort>>,ulong)
0x18009066c  test    al, al
0x18009066e  jnz     short loc_180090677
0x180090670  mov     edx, 0B1Ah
0x180090675  jmp     short loc_18009069C
0x180090677  lea     r8, [rbp+230h+var_150]
0x18009067e  lea     rdx, [rsp+330h+var_2F0]
0x180090683  lea     rcx, [rbp+230h+var_198]
0x18009068a  call    ??$emplace@VInjectableRegistryKey@Hcs@Manager@Container@@$0A@@?$_Tree@VInjectableRegistryKey@Hcs@Manager@Container@@V1234@U?$less@VInjectableRegistryKey@Hcs@Manager@Container@@@utl@@V?$allocator@VInjectableRegistryKey@Hcs@Manager@Container@@@6@$0A@@utl@@QEAA?AU?$pair@V?$_TreeConstIt@VInjectableRegistryKey@Hcs@Manager@Container@@@utl@@_N@1@$$QEAVInjectableRegistryKey@Hcs@Manager@Container@@@Z; utl::_Tree<Container::Manager::Hcs::InjectableRegistryKey,Container::Manager::Hcs::InjectableRegistryKey,utl::less<Container::Manager::Hcs::InjectableRegistryKey>,utl::allocator<Container::Manager::Hcs::InjectableRegistryKey>,0>::emplace<Container::Manager::Hcs::InjectableRegistryKey,0>(Container::Manager::Hcs::InjectableRegistryKey &&)
0x18009068f  cmp     [rsp+330h+var_2F0], 0
0x180090695  jnz     short loc_1800906EA
0x180090697  mov     edx, 0B1Dh; void *
0x18009069c  mov     r9d, 8007000Eh; char *
0x1800906a2  lea     r8, aOnecoreBaseGen_55; "onecore\\base\\gendrv\\silos\\clem\\cor"...
0x1800906a9  mov     rcx, [rbp+238h]; this
0x1800906b0  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800906b5  lea     rcx, [rbp+230h+var_128]
0x1800906bc  call    ?clear@?$_Tree@VInjectableRegistryValue@Hcs@Manager@Container@@V1234@U?$less@VInjectableRegistryValue@Hcs@Manager@Container@@@utl@@V?$allocator@VInjectableRegistryValue@Hcs@Manager@Container@@@6@$0A@@utl@@QEAAXXZ; utl::_Tree<Container::Manager::Hcs::InjectableRegistryValue,Container::Manager::Hcs::InjectableRegistryValue,utl::less<Container::Manager::Hcs::InjectableRegistryValue>,utl::allocator<Container::Manager::Hcs::InjectableRegistryValue>,0>::clear(void)
0x1800906c1  lea     rax, [rbp+230h+var_138]
0x1800906c8  mov     rcx, [rbp+230h+var_148]; void *
0x1800906cf  cmp     rcx, rax
0x1800906d2  jz      short loc_1800906E0
0x1800906d4  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x1800906db  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1800906e0  mov     ebx, 8007000Eh
0x1800906e5  jmp     loc_18009125F
0x1800906ea  lea     rcx, [rbp+230h+var_128]
0x1800906f1  call    ?clear@?$_Tree@VInjectableRegistryValue@Hcs@Manager@Container@@V1234@U?$less@VInjectableRegistryValue@Hcs@Manager@Container@@@utl@@V?$allocator@VInjectableRegistryValue@Hcs@Manager@Container@@@6@$0A@@utl@@QEAAXXZ; utl::_Tree<Container::Manager::Hcs::InjectableRegistryValue,Container::Manager::Hcs::InjectableRegistryValue,utl::less<Container::Manager::Hcs::InjectableRegistryValue>,utl::allocator<Container::Manager::Hcs::InjectableRegistryValue>,0>::clear(void)
0x1800906f6  mov     rcx, [rbp+230h+var_148]; void *
0x1800906fd  lea     rax, [rbp+230h+var_138]
0x180090704  lea     rbx, ?nothrow@std@@3Unothrow_t@1@B; std::nothrow_t const std::nothrow
0x18009070b  cmp     rcx, rax
0x18009070e  jz      short loc_180090718
0x180090710  mov     rdx, rbx; struct std::nothrow_t *
0x180090713  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180090718  lea     rax, [rsp+330h+var_2D0]
0x18009071d  mov     [rsp+330h+Hostname], rax
0x180090722  lea     rax, [rsp+330h+var_2D0]
0x180090727  mov     [rsp+330h+var_2D8], rax
0x18009072c  xor     eax, eax
0x18009072e  mov     [rsp+330h+var_2D0], ax
0x180090733  lea     rdx, [rsp+330h+Hostname]
0x180090738  mov     rcx, rsi
0x18009073b  call    ?GuidToString@Csl@@YAJAEBU_GUID@@AEAV?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@@Z; Csl::GuidToString(_GUID const &,utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>> &)
0x180090740  mov     edi, eax
0x180090742  xor     esi, esi
0x180090744  test    eax, eax
0x180090746  jns     short loc_180090781
0x180090748  mov     rcx, [rbp+238h]; this
0x18009074f  mov     r9d, eax; char *
0x180090752  lea     r8, aOnecoreBaseGen_55; "onecore\\base\\gendrv\\silos\\clem\\cor"...
0x180090759  mov     edx, 0B22h; void *
0x18009075e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180090763  lea     rax, [rsp+330h+var_2D0]
0x180090768  mov     rcx, [rsp+330h+Hostname]; void *
0x18009076d  cmp     rcx, rax
0x180090770  jz      short loc_18009077A
0x180090772  mov     rdx, rbx; struct std::nothrow_t *
0x180090775  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18009077a  mov     ebx, edi
0x18009077c  jmp     loc_18009125F
0x180090781  mov     [rbp+230h+var_270], esi
0x180090784  lea     rax, [rbp+230h+var_258]
0x180090788  mov     [rbp+230h+var_268], rax
0x18009078c  lea     rax, [rbp+230h+var_258]
0x180090790  mov     [rbp+230h+var_260], rax
0x180090794  mov     [rbp+230h+var_258], si
0x180090798  lea     rax, [rbp+230h+var_248]
0x18009079c  mov     [rbp+230h+var_248], rax
0x1800907a0  lea     rax, [rbp+230h+var_248]
0x1800907a4  mov     [rbp+230h+var_240], rax
0x1800907a8  mov     [rbp+230h+var_238], rax
0x1800907ac  mov     [rbp+230h+var_230], rsi
0x1800907b0  lea     rax, aControlset001S; "ControlSet001\\Services\\Tcpip\\Paramet"...
0x1800907b7  mov     qword ptr [rbp+230h+nSize], rax
0x1800907bb  mov     [rbp+230h+var_2A8], 27h ; '''
0x1800907c3  lea     r8, [rbp+230h+nSize]
0x1800907c7  lea     rcx, [rbp+230h+var_270]
0x1800907cb  call    ?Initialize@InjectableRegistryKey@Hcs@Manager@Container@@QEAA_NW4Hive@1234@V?$basic_string_view@GU?$char_traits@G@utl@@@utl@@@Z; Container::Manager::Hcs::InjectableRegistryKey::Initialize(Container::Manager::Hcs::InjectableRegistryKey::Hive,utl::basic_string_view<ushort,utl::char_traits<ushort>>)
0x1800907d0  test    al, al
0x1800907d2  jnz     short loc_1800907F7
0x1800907d4  mov     edx, 0B27h; void *
0x1800907d9  mov     rcx, [rbp+238h]; this
0x1800907e0  mov     r9d, 8007000Eh; char *
0x1800907e6  lea     r8, aOnecoreBaseGen_55; "onecore\\base\\gendrv\\silos\\clem\\cor"...
0x1800907ed  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800907f2  jmp     loc_180090AA7
0x1800907f7  mov     edi, 1
0x1800907fc  test    r15b, r15b
0x1800907ff  jz      loc_1800908DD
0x180090805  mov     rax, [r14+8]
0x180090809  mov     eax, [rax+60h]
0x18009080c  shr     eax, 4
0x18009080f  test    dil, al
0x180090812  jz      loc_1800908DD
0x180090818  lea     rax, aPorttrackerena; "PortTrackerEnabledMode"
0x18009081f  mov     qword ptr [rbp+230h+nSize], rax
0x180090823  mov     [rbp+230h+var_2A8], 16h
0x18009082b  mov     r8d, edi
0x18009082e  lea     rdx, [rbp+230h+nSize]
0x180090832  lea     rcx, [rbp+230h+var_270]
0x180090836  call    ?AddDwordValue@InjectableRegistryKey@Hcs@Manager@Container@@QEAA_NV?$basic_string_view@GU?$char_traits@G@utl@@@utl@@K@Z; Container::Manager::Hcs::InjectableRegistryKey::AddDwordValue(utl::basic_string_view<ushort,utl::char_traits<ushort>>,ulong)
0x18009083b  test    al, al
0x18009083d  jnz     short loc_180090846
0x18009083f  mov     edx, 0B2Eh
0x180090844  jmp     short loc_1800907D9
0x180090846  mov     rax, cs:Feature_HnsWcosLoopback__descriptor
0x18009084d  mov     r8d, [rax]
0x180090850  test    r8b, 4
0x180090854  jnz     short loc_180090869
0x180090856  lea     rdx, [rbp+230h+nSize]
0x18009085a  call    ?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_HnsWcosLoopback@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_HnsWcosLoopback>::GetCachedFeatureEnabledState(void)
0x18009085f  mov     rcx, [rax]
0x180090862  mov     qword ptr [rbp+230h+nSize], rcx
0x180090866  mov     r8d, ecx
0x180090869  mov     [rsp+330h+var_2C0], esi
0x18009086d  mov     [rsp+330h+var_2BC], 3
0x180090874  mov     r9d, r8d
0x180090877  shr     r9d, 0Bh
0x18009087b  and     r9d, edi
0x18009087e  shr     r8d, 0Ah
0x180090882  and     r8d, edi
0x180090885  mov     [rsp+330h+var_300], 3
0x18009088d  mov     [rsp+330h+var_308], edi
0x180090891  lea     rax, [rsp+330h+var_2C0]
0x180090896  mov     [rsp+330h+var_310], rax
0x18009089b  mov     edx, 168A97Eh
0x1800908a0  lea     rcx, unk_18021F618
0x1800908a7  call    ?ReportUsageToService@details@wil@@YAXPEAUwil_details_FeatureReportingCache@@IHHPEBUFEATURE_LOGGED_TRAITS@@HW4wil_ReportingKind@@_K@Z; wil::details::ReportUsageToService(wil_details_FeatureReportingCache *,uint,int,int,FEATURE_LOGGED_TRAITS const *,int,wil_ReportingKind,unsigned __int64)
0x1800908ac  lea     rax, aWcosloopbacken; "WcosLoopbackEnabled"
0x1800908b3  mov     qword ptr [rbp+230h+nSize], rax
0x1800908b7  mov     [rbp+230h+var_2A8], 13h
0x1800908bf  mov     r8d, edi
0x1800908c2  lea     rdx, [rbp+230h+nSize]
0x1800908c6  lea     rcx, [rbp+230h+var_270]
0x1800908ca  call    ?AddDwordValue@InjectableRegistryKey@Hcs@Manager@Container@@QEAA_NV?$basic_string_view@GU?$char_traits@G@utl@@@utl@@K@Z; Container::Manager::Hcs::InjectableRegistryKey::AddDwordValue(utl::basic_string_view<ushort,utl::char_traits<ushort>>,ulong)
0x1800908cf  test    al, al
0x1800908d1  jnz     short loc_1800908DD
0x1800908d3  mov     edx, 0B32h
0x1800908d8  jmp     loc_1800907D9
0x1800908dd  lea     rax, [rbp+230h+var_280]
0x1800908e1  mov     [rbp+230h+var_290], rax
0x1800908e5  lea     rax, [rbp+230h+var_280]
0x1800908e9  mov     [rbp+230h+var_288], rax
0x1800908ed  mov     [rbp+230h+var_280], si
0x1800908f1  or      rdi, 0FFFFFFFFFFFFFFFFh
0x1800908f5  test    r15b, r15b
0x1800908f8  jz      loc_180090AE0
0x1800908fe  mov     rcx, [r14+8]
0x180090902  mov     ecx, [rcx+60h]
0x180090905  shr     ecx, 4
0x180090908  test    cl, 1
0x18009090b  jz      loc_180090AE0
0x180090911  mov     [rbp+230h+nSize], esi
0x180090914  lea     r8, [rbp+230h+nSize]; nSize
0x180090918  xor     edx, edx; lpBuffer
0x18009091a  lea     ecx, [rdi+6]; NameType
0x18009091d  call    cs:__imp_GetComputerNameExW
0x180090924  nop     dword ptr [rax+rax+00h]
0x180090929  mov     ecx, [rbp+230h+nSize]
0x18009092c  lea     eax, [rdi+3]
0x18009092f  mul     rcx
0x180090932  mov     rsi, rax
0x180090935  cmovb   rsi, rdi
0x180090939  mov     rdx, rbx; struct std::nothrow_t *
0x18009093c  mov     rcx, rsi; unsigned __int64
0x18009093f  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x180090944  mov     rdi, rax
0x180090947  test    rax, rax
0x18009094a  jz      loc_180090A74
0x180090950  mov     r8, rsi; Size
0x180090953  xor     edx, edx; Val
0x180090955  mov     rcx, rax; void *
0x180090958  call    memset_0
0x18009095d  lea     r8, [rbp+230h+nSize]; nSize
0x180090961  mov     rdx, rdi; lpBuffer
0x180090964  mov     ecx, 5; NameType
0x180090969  call    cs:__imp_GetComputerNameExW
0x180090970  nop     dword ptr [rax+rax+00h]
0x180090975  xor     esi, esi
0x180090977  test    eax, eax
0x180090979  jnz     short loc_1800909D9
0x18009097b  mov     rcx, [rbp+238h]; this
0x180090982  lea     r8, aOnecoreBaseGen_55; "onecore\\base\\gendrv\\silos\\clem\\cor"...
0x180090989  mov     edx, 0B47h; void *
0x18009098e  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180090993  mov     esi, eax
0x180090995  mov     rcx, rdi; void *
0x180090998  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18009099d  lea     rax, [rbp+230h+var_280]
0x1800909a1  mov     rcx, [rbp+230h+var_290]; void *
0x1800909a5  cmp     rcx, rax
0x1800909a8  jz      short loc_1800909B2
0x1800909aa  mov     rdx, rbx; struct std::nothrow_t *
0x1800909ad  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1800909b2  lea     rcx, [rbp+230h+var_248]
0x1800909b6  call    ?clear@?$_Tree@VInjectableRegistryValue@Hcs@Manager@Container@@V1234@U?$less@VInjectableRegistryValue@Hcs@Manager@Container@@@utl@@V?$allocator@VInjectableRegistryValue@Hcs@Manager@Container@@@6@$0A@@utl@@QEAAXXZ; utl::_Tree<Container::Manager::Hcs::InjectableRegistryValue,Container::Manager::Hcs::InjectableRegistryValue,utl::less<Container::Manager::Hcs::InjectableRegistryValue>,utl::allocator<Container::Manager::Hcs::InjectableRegistryValue>,0>::clear(void)
0x1800909bb  mov     rcx, [rbp+230h+var_268]; void *
0x1800909bf  lea     rax, [rbp+230h+var_258]
0x1800909c3  cmp     rcx, rax
0x1800909c6  jz      loc_180091246
0x1800909cc  mov     rdx, rbx; struct std::nothrow_t *
0x1800909cf  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1800909d4  jmp     loc_180091246
0x1800909d9  or      r8, 0FFFFFFFFFFFFFFFFh
0x1800909dd  inc     r8
0x1800909e0  cmp     [rdi+r8*2], si
0x1800909e5  jnz     short loc_1800909DD
0x1800909e7  mov     rdx, rdi
0x1800909ea  lea     rcx, [rbp+230h+var_290]
0x1800909ee  call    ?assign@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA_NPEBG_K@Z; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::assign(ushort const *,unsigned __int64)
0x1800909f3  test    al, al
0x1800909f5  jnz     short loc_180090A1F
0x1800909f7  mov     rcx, [rbp+238h]; this
0x1800909fe  mov     r9d, 8007000Eh; char *
0x180090a04  lea     r8, aOnecoreBaseGen_55; "onecore\\base\\gendrv\\silos\\clem\\cor"...
0x180090a0b  mov     edx, 0B49h; void *
0x180090a10  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180090a15  mov     rcx, rdi; void *
0x180090a18  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180090a1d  jmp     short loc_180090A92
0x180090a1f  mov     rcx, rdi; void *
0x180090a22  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180090a27  mov     rax, [rbp+230h+var_290]
0x180090a2b  mov     [rbp+230h+var_2A0], rax
  ... truncated ...
```
