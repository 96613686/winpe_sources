# UtilWriteOSVersionInfo(CXMLWriter *)

- ea: `0x1400135c0`
- end: `0x140013fea`
- name: `?UtilWriteOSVersionInfo@@YAJPEAVCXMLWriter@@@Z`
- size: `2602`
- prototype: `__int64 __fastcall(struct CXMLWriter *)`
- caller_count: `1`
- callee_count: `15`
- tags: `file_ops, registry_config, loader_planting, broker_com_uri`

## callers

- `0x1400205c8`

## callees

- `0x140002470`
- `0x140002728`
- `0x1400030a8`
- `0x140005430`
- `0x14000c8a0`
- `0x14000eb7c`
- `0x14000ed48`
- `0x140010a7c`
- `0x14001211c`
- `0x140012210`
- `0x14001301c`
- `0x1400135c0`
- `0x14001444c`
- `0x140014474`
- `0x140015324`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14001382f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14001382f`
- `api-ms-win-core-localization-l1-2-0!GetThreadUILanguage` at `0x140013ced`
- `api-ms-win-core-localization-l1-2-0!GetThreadUILanguage` at `0x140013ced`
- `api-ms-win-core-localization-l1-2-0!GetUserGeoID` at `0x140013d5d`
- `api-ms-win-core-localization-l1-2-0!GetUserGeoID` at `0x140013d5d`
- `api-ms-win-core-sysinfo-l1-2-0!GetProductInfo` at `0x14001380c`
- `api-ms-win-core-sysinfo-l1-2-0!GetProductInfo` at `0x14001380c`
- `api-ms-win-core-sysinfo-l1-2-0!GetNativeSystemInfo` at `0x140013c1b`
- `api-ms-win-core-sysinfo-l1-2-0!GetNativeSystemInfo` at `0x140013c1b`
- `ntdll!RtlGetVersion` at `0x1400137d7`
- `ntdll!RtlGetVersion` at `0x1400137d7`

## pseudocode

```c
// Hidden C++ exception states: #wind=8
__int64 __fastcall UtilWriteOSVersionInfo(struct CXMLWriter *a1)
{
  _WORD *v2; // rcx
  _WORD *v3; // r8
  NTSTATUS Version; // edi
  DWORD LastError; // eax
  unsigned int DWORD; // eax
  int v8; // r9d
  int v9; // r9d
  int v10; // r9d
  int v11; // r9d
  int v12; // r9d
  int v13; // r9d
  int v14; // r9d
  __int64 v15; // r8
  const wchar_t *v16; // rdx
  int v17; // r9d
  LANGID ThreadUILanguage; // ax
  int v19; // r9d
  unsigned int UserGeoID; // eax
  int v21; // r9d
  int v22; // r9d
  int v23; // eax
  unsigned int v24; // edi
  bool v25; // [rsp+28h] [rbp-D8h]
  DWORD v26; // [rsp+30h] [rbp-D0h]
  DWORD v27; // [rsp+30h] [rbp-D0h]
  DWORD v28; // [rsp+30h] [rbp-D0h]
  __int128 v29; // [rsp+40h] [rbp-C0h] BYREF
  __int128 v30; // [rsp+50h] [rbp-B0h] BYREF
  __int128 v31; // [rsp+60h] [rbp-A0h] BYREF
  void *v32; // [rsp+70h] [rbp-90h] BYREF
  char *v33; // [rsp+78h] [rbp-88h]
  _WORD v34[8]; // [rsp+80h] [rbp-80h] BYREF
  DWORD pdwReturnedProductType; // [rsp+90h] [rbp-70h] BYREF
  void *v36; // [rsp+98h] [rbp-68h] BYREF
  char *v37; // [rsp+A0h] [rbp-60h]
  _WORD v38[8]; // [rsp+A8h] [rbp-58h] BYREF
  void *v39; // [rsp+B8h] [rbp-48h] BYREF
  char *v40; // [rsp+C0h] [rbp-40h]
  _WORD v41[8]; // [rsp+C8h] [rbp-38h] BYREF
  void *v42; // [rsp+D8h] [rbp-28h] BYREF
  char *v43; // [rsp+E0h] [rbp-20h]
  _WORD v44[8]; // [rsp+E8h] [rbp-18h] BYREF
  void *v45; // [rsp+F8h] [rbp-8h] BYREF
  char *v46; // [rsp+100h] [rbp+0h]
  _WORD v47[8]; // [rsp+108h] [rbp+8h] BYREF
  void *v48[2]; // [rsp+118h] [rbp+18h] BYREF
  _WORD v49[8]; // [rsp+128h] [rbp+28h] BYREF
  void *v50; // [rsp+138h] [rbp+38h]
  _WORD *v51; // [rsp+140h] [rbp+40h]
  _WORD v52[8]; // [rsp+148h] [rbp+48h] BYREF
  void *v53; // [rsp+158h] [rbp+58h]
  _WORD *v54; // [rsp+160h] [rbp+60h]
  _WORD v55[8]; // [rsp+168h] [rbp+68h] BYREF
  _SYSTEM_INFO SystemInfo; // [rsp+178h] [rbp+78h] BYREF
  struct _OSVERSIONINFOW VersionInformation; // [rsp+1B0h] [rbp+B0h] BYREF
  unsigned __int16 v58; // [rsp+2C4h] [rbp+1C4h]
  unsigned __int16 v59; // [rsp+2C6h] [rbp+1C6h]

  memset_0(&VersionInformation.dwMajorVersion, 0, 0x118u);
  v32 = v34;
  v33 = (char *)v34;
  v34[0] = 0;
  memset(&SystemInfo, 0, sizeof(SystemInfo));
  pdwReturnedProductType = 0;
  v48[0] = v49;
  v48[1] = v49;
  v49[0] = 0;
  v45 = v47;
  v46 = (char *)v47;
  v47[0] = 0;
  v42 = v44;
  v43 = (char *)v44;
  v44[0] = 0;
  v39 = v41;
  v40 = (char *)v41;
  v41[0] = 0;
  v53 = v55;
  v54 = v55;
  v55[0] = 0;
  v2 = v38;
  v36 = v38;
  v37 = (char *)v38;
  v38[0] = 0;
  v3 = v52;
  v50 = v52;
  v51 = v52;
  v52[0] = 0;
  if ( !a1 )
  {
    if ( WPP_GLOBAL_Control != (CUserModeHangReport *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 67, WPP_988ce82756cb3ec502560a762615dae0_Traceguids);
      v2 = v36;
      v3 = v50;
    }
    if ( v3 != v52 )
    {
      operator delete(v3, (const struct std::nothrow_t *)&std::nothrow);
      v2 = v36;
    }
    if ( v2 != v38 )
      operator delete(v2, (const struct std::nothrow_t *)&std::nothrow);
    if ( v53 != v55 )
      operator delete(v53, (const struct std::nothrow_t *)&std::nothrow);
    if ( v39 != v41 )
      operator delete(v39, (const struct std::nothrow_t *)&std::nothrow);
    if ( v42 != v44 )
      operator delete(v42, (const struct std::nothrow_t *)&std::nothrow);
    if ( v45 != v47 )
      operator delete(v45, (const struct std::nothrow_t *)&std::nothrow);
    if ( v48[0] != v49 )
      operator delete(v48[0], (const struct std::nothrow_t *)&std::nothrow);
    if ( v32 != v34 )
      operator delete(v32, (const struct std::nothrow_t *)&std::nothrow);
    return 2147942487LL;
  }
  VersionInformation.dwOSVersionInfoSize = 284;
  Version = RtlGetVersion(&VersionInformation);
  if ( Version < 0 )
  {
    v24 = Version | 0x10000000;
    if ( WPP_GLOBAL_Control != (CUserModeHangReport *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 69, WPP_988ce82756cb3ec502560a762615dae0_Traceguids, v24);
    }
    goto LABEL_56;
  }
  if ( !GetProductInfo(
          VersionInformation.dwMajorVersion,
          VersionInformation.dwMinorVersion,
          v58,
          v59,
          &pdwReturnedProductType) )
  {
    if ( WPP_GLOBAL_Control != (CUserModeHangReport *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      LastError = GetLastError();
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 68, WPP_988ce82756cb3ec502560a762615dae0_Traceguids, LastError);
    }
    pdwReturnedProductType = 0;
  }
  UtilRegGetString(
    HKEY_LOCAL_MACHINE,
    L"SOFTWARE\\Microsoft\\Windows NT\\CurrentVersion",
    L"ProductName",
    (__int64)v48,
    0,
    v26);
  UtilRegGetString(
    HKEY_LOCAL_MACHINE,
    L"SOFTWARE\\Microsoft\\Windows NT\\CurrentVersion",
    L"EditionID",
    (__int64)&v45,
    0,
    v27);
  DWORD = UtilRegGetDWORD(HKEY_LOCAL_MACHINE, L"SOFTWARE\\Microsoft\\Windows NT\\CurrentVersion", L"Ubr", 0, 0, v25);
  tlx::assign_sprintf<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(&v36, L"%u", DWORD);
  UtilGetPlatformVersion(&v39);
  UtilRegGetString(
    HKEY_LOCAL_MACHINE,
    L"SOFTWARE\\Microsoft\\Windows NT\\CurrentVersion",
    L"CurrentType",
    (__int64)&v42,
    0,
    v28);
  v29 = 0;
  v31 = 0;
  *(_QWORD *)&v30 = L"OSVersionInformation";
  *((_QWORD *)&v30 + 1) = 20;
  CXMLWriter::BeginElement((_DWORD)a1, (unsigned int)&v30, (unsigned int)&v31, 0, (__int64)&v29);
  tlx::assign_sprintf<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(
    &v32,
    L"%u.%u",
    VersionInformation.dwMajorVersion,
    VersionInformation.dwMinorVersion);
  v31 = 0;
  *(_QWORD *)&v30 = v32;
  *((_QWORD *)&v30 + 1) = (v33 - (_BYTE *)v32) >> 1;
  *(_QWORD *)&v29 = L"WindowsNTVersion";
  *((_QWORD *)&v29 + 1) = 16;
  LOBYTE(v8) = 1;
  CXMLWriter::BeginElement((_DWORD)a1, (unsigned int)&v29, (unsigned int)&v30, v8, (__int64)&v31);
  if ( VersionInformation.szCSDVersion[0] )
    tlx::assign_sprintf<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(
      &v32,
      L"%u %ls",
      VersionInformation.dwBuildNumber,
      VersionInformation.szCSDVersion);
  else
    tlx::assign_sprintf<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(
      &v32,
      L"%u",
      VersionInformation.dwBuildNumber);
  v31 = 0;
  *(_QWORD *)&v29 = v32;
  *((_QWORD *)&v29 + 1) = (v33 - (_BYTE *)v32) >> 1;
  *(_QWORD *)&v30 = L"Build";
  *((_QWORD *)&v30 + 1) = 5;
  LOBYTE(v9) = 1;
  CXMLWriter::BeginElement((_DWORD)a1, (unsigned int)&v30, (unsigned int)&v29, v9, (__int64)&v31);
  tlx::assign_sprintf<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(
    &v32,
    L"(0x%x): %ls",
    pdwReturnedProductType,
    v48[0]);
  v31 = 0;
  *(_QWORD *)&v29 = v32;
  *((_QWORD *)&v29 + 1) = (v33 - (_BYTE *)v32) >> 1;
  *(_QWORD *)&v30 = L"Product";
  *((_QWORD *)&v30 + 1) = 7;
  LOBYTE(v10) = 1;
  CXMLWriter::BeginElement((_DWORD)a1, (unsigned int)&v30, (unsigned int)&v29, v10, (__int64)&v31);
  v31 = 0;
  *(_QWORD *)&v29 = v45;
  *((_QWORD *)&v29 + 1) = (v46 - (_BYTE *)v45) >> 1;
  *(_QWORD *)&v30 = L"Edition";
  *((_QWORD *)&v30 + 1) = 7;
  LOBYTE(v11) = 1;
  CXMLWriter::BeginElement((_DWORD)a1, (unsigned int)&v30, (unsigned int)&v29, v11, (__int64)&v31);
  v31 = 0;
  *(_QWORD *)&v29 = v39;
  *((_QWORD *)&v29 + 1) = (v40 - (_BYTE *)v39) >> 1;
  *(_QWORD *)&v30 = L"BuildString";
  *((_QWORD *)&v30 + 1) = 11;
  LOBYTE(v12) = 1;
  CXMLWriter::BeginElement((_DWORD)a1, (unsigned int)&v30, (unsigned int)&v29, v12, (__int64)&v31);
  v31 = 0;
  *(_QWORD *)&v29 = v36;
  *((_QWORD *)&v29 + 1) = (v37 - (_BYTE *)v36) >> 1;
  *(_QWORD *)&v30 = L"Revision";
  *((_QWORD *)&v30 + 1) = 8;
  LOBYTE(v13) = 1;
  CXMLWriter::BeginElement((_DWORD)a1, (unsigned int)&v30, (unsigned int)&v29, v13, (__int64)&v31);
  v31 = 0;
  *(_QWORD *)&v29 = v42;
  *((_QWORD *)&v29 + 1) = (v43 - (_BYTE *)v42) >> 1;
  *(_QWORD *)&v30 = L"Flavor";
  *((_QWORD *)&v30 + 1) = 6;
  LOBYTE(v14) = 1;
  CXMLWriter::BeginElement((_DWORD)a1, (unsigned int)&v30, (unsigned int)&v29, v14, (__int64)&v31);
  GetNativeSystemInfo(&SystemInfo);
  if ( SystemInfo.wProcessorArchitecture == 6 )
  {
    v15 = 4;
    v16 = L"IA64";
    goto LABEL_42;
  }
  if ( SystemInfo.wProcessorArchitecture == 9 )
  {
    v16 = L"X64";
LABEL_39:
    v15 = 3;
    goto LABEL_42;
  }
  if ( !SystemInfo.wProcessorArchitecture )
  {
    v16 = L"X86";
    goto LABEL_39;
  }
  if ( SystemInfo.wProcessorArchitecture == 5 )
  {
    v16 = L"ARM";
    goto LABEL_39;
  }
  if ( SystemInfo.wProcessorArchitecture != 12 )
  {
    tlx::assign_sprintf<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(
      &v32,
      L"%u",
      SystemInfo.wProcessorArchitecture);
    goto LABEL_44;
  }
  v15 = 5;
  v16 = L"ARM64";
LABEL_42:
  utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::assign(&v32, v16, v15);
LABEL_44:
  v31 = 0;
  *(_QWORD *)&v29 = v32;
  *((_QWORD *)&v29 + 1) = (v33 - (_BYTE *)v32) >> 1;
  *(_QWORD *)&v30 = L"Architecture";
  *((_QWORD *)&v30 + 1) = 12;
  LOBYTE(v17) = 1;
  CXMLWriter::BeginElement((_DWORD)a1, (unsigned int)&v30, (unsigned int)&v29, v17, (__int64)&v31);
  ThreadUILanguage = GetThreadUILanguage();
  tlx::assign_sprintf<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(&v32, L"%u", ThreadUILanguage);
  v31 = 0;
  *(_QWORD *)&v29 = v32;
  *((_QWORD *)&v29 + 1) = (v33 - (_BYTE *)v32) >> 1;
  *(_QWORD *)&v30 = L"LCID";
  *((_QWORD *)&v30 + 1) = 4;
  LOBYTE(v19) = 1;
  CXMLWriter::BeginElement((_DWORD)a1, (unsigned int)&v30, (unsigned int)&v29, v19, (__int64)&v31);
  UserGeoID = GetUserGeoID(0);
  if ( UserGeoID != -1 )
  {
    tlx::assign_sprintf<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(&v32, L"%u", UserGeoID);
    v31 = 0;
    *(_QWORD *)&v29 = v32;
    *((_QWORD *)&v29 + 1) = (v33 - (_BYTE *)v32) >> 1;
    *(_QWORD *)&v30 = L"GeoId";
    *((_QWORD *)&v30 + 1) = 5;
    LOBYTE(v21) = 1;
    CXMLWriter::BeginElement((_DWORD)a1, (unsigned int)&v30, (unsigned int)&v29, v21, (__int64)&v31);
  }
  if ( UtilIsMemoryErrorEventSet() )
  {
    v31 = 0;
    *(_QWORD *)&v29 = L"1";
    *((_QWORD *)&v29 + 1) = 1;
    *(_QWORD *)&v30 = L"MemoryError";
    *((_QWORD *)&v30 + 1) = 11;
    LOBYTE(v22) = 1;
    CXMLWriter::BeginElement((_DWORD)a1, (unsigned int)&v30, (unsigned int)&v29, v22, (__int64)&v31);
  }
  v31 = 0;
  v30 = 0;
  *(_QWORD *)&v29 = L"BuildLayers";
  *((_QWORD *)&v29 + 1) = 11;
  CXMLWriter::BeginElement((_DWORD)a1, (unsigned int)&v29, (unsigned int)&v30, 0, (__int64)&v31);
  v23 = UtilWriteOSBuildLayerInfo(a1);
  if ( v23 < 0
    && WPP_GLOBAL_Control != (CUserModeHangReport *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
  {
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      70,
      WPP_988ce82756cb3ec502560a762615dae0_Traceguids,
      (unsigned int)v23);
  }
  *(_QWORD *)&v29 = L"BuildLayers";
  *((_QWORD *)&v29 + 1) = 11;
  CXMLWriter::EndElement(a1, &v29);
  *(_QWORD *)&v29 = L"OSVersionInformation";
  *((_QWORD *)&v29 + 1) = 20;
  CXMLWriter::EndElement(a1, &v29);
  v24 = 0;
LABEL_56:
  if ( v50 != v52 )
    operator delete(v50, (const struct std::nothrow_t *)&std::nothrow);
  if ( v36 != v38 )
    operator delete(v36, (const struct std::nothrow_t *)&std::nothrow);
  if ( v53 != v55 )
    operator delete(v53, (const struct std::nothrow_t *)&std::nothrow);
  if ( v39 != v41 )
    operator delete(v39, (const struct std::nothrow_t *)&std::nothrow);
  if ( v42 != v44 )
    operator delete(v42, (const struct std::nothrow_t *)&std::nothrow);
  if ( v45 != v47 )
    operator delete(v45, (const struct std::nothrow_t *)&std::nothrow);
  if ( v48[0] != v49 )
    operator delete(v48[0], (const struct std::nothrow_t *)&std::nothrow);
  if ( v32 != v34 )
    operator delete(v32, (const struct std::nothrow_t *)&std::nothrow);
  return v24;
}

```

## disassembly

```asm
0x1400135c0  push    rbp
0x1400135c2  push    rbx
0x1400135c3  push    rsi
0x1400135c4  push    rdi
0x1400135c5  push    r12
0x1400135c7  push    r13
0x1400135c9  push    r14
0x1400135cb  push    r15
0x1400135cd  lea     rbp, [rsp-1E8h]
0x1400135d5  sub     rsp, 2E8h
0x1400135dc  mov     rax, cs:__security_cookie
0x1400135e3  xor     rax, rsp
0x1400135e6  mov     [rbp+220h+var_50], rax
0x1400135ed  mov     rbx, rcx
0x1400135f0  xor     edx, edx; Val
0x1400135f2  mov     r8d, 118h; Size
0x1400135f8  lea     rcx, [rbp+220h+VersionInformation.dwMajorVersion]; void *
0x1400135ff  call    memset_0
0x140013604  lea     rax, [rbp+220h+var_2A0]
0x140013608  mov     [rsp+320h+var_2B0], rax
0x14001360d  lea     rax, [rbp+220h+var_2A0]
0x140013611  mov     [rsp+320h+var_2A8], rax
0x140013616  xor     r12d, r12d
0x140013619  mov     [rbp+220h+var_2A0], r12w
0x14001361e  xorps   xmm0, xmm0
0x140013621  movups  xmmword ptr [rbp+220h+SystemInfo], xmm0
0x140013625  movups  xmmword ptr [rbp+220h+SystemInfo.lpMaximumApplicationAddress], xmm0
0x14001362c  movups  xmmword ptr [rbp+220h+SystemInfo.dwNumberOfProcessors], xmm0
0x140013633  mov     [rbp+220h+var_290], r12d
0x140013637  lea     rax, [rbp+220h+var_1F8]
0x14001363b  mov     [rbp+220h+var_208], rax
0x14001363f  lea     rax, [rbp+220h+var_1F8]
0x140013643  mov     [rbp+220h+var_200], rax
0x140013647  mov     [rbp+220h+var_1F8], r12w
0x14001364c  lea     rax, [rbp+220h+var_218]
0x140013650  mov     [rbp+220h+var_228], rax
0x140013654  lea     rax, [rbp+220h+var_218]
0x140013658  mov     [rbp+220h+var_220], rax
0x14001365c  mov     [rbp+220h+var_218], r12w
0x140013661  lea     rax, [rbp+220h+var_238]
0x140013665  mov     [rbp+220h+var_248], rax
0x140013669  lea     rax, [rbp+220h+var_238]
0x14001366d  mov     [rbp+220h+var_240], rax
0x140013671  mov     [rbp+220h+var_238], r12w
0x140013676  lea     rax, [rbp+220h+var_258]
0x14001367a  mov     [rbp+220h+var_268], rax
0x14001367e  lea     rax, [rbp+220h+var_258]
0x140013682  mov     [rbp+220h+var_260], rax
0x140013686  mov     [rbp+220h+var_258], r12w
0x14001368b  lea     rax, [rbp+220h+var_1B8]
0x14001368f  mov     [rbp+220h+var_1C8], rax
0x140013693  lea     rax, [rbp+220h+var_1B8]
0x140013697  mov     [rbp+220h+var_1C0], rax
0x14001369b  mov     [rbp+220h+var_1B8], r12w
0x1400136a0  lea     rcx, [rbp+220h+var_278]
0x1400136a4  mov     [rbp+220h+var_288], rcx
0x1400136a8  lea     rax, [rbp+220h+var_278]
0x1400136ac  mov     [rbp+220h+var_280], rax
0x1400136b0  mov     [rbp+220h+var_278], r12w
0x1400136b5  lea     r8, [rbp+220h+var_1D8]
0x1400136b9  mov     [rbp+220h+var_1E8], r8
0x1400136bd  lea     rax, [rbp+220h+var_1D8]
0x1400136c1  mov     [rbp+220h+var_1E0], rax
0x1400136c5  mov     [rbp+220h+var_1D8], r12w
0x1400136ca  test    rbx, rbx
0x1400136cd  jnz     loc_1400137C6
0x1400136d3  lea     rsi, WPP_GLOBAL_Control
0x1400136da  mov     rax, cs:WPP_GLOBAL_Control
0x1400136e1  cmp     rax, rsi
0x1400136e4  jz      short loc_140013707
0x1400136e6  test    byte ptr [rax+1Ch], 1
0x1400136ea  jz      short loc_140013707
0x1400136ec  lea     edx, [rbx+43h]
0x1400136ef  lea     r8, WPP_988ce82756cb3ec502560a762615dae0_Traceguids
0x1400136f6  mov     rcx, [rax+10h]
0x1400136fa  call    WPP_SF_
0x1400136ff  mov     rcx, [rbp+220h+var_288]
0x140013703  mov     r8, [rbp+220h+var_1E8]
0x140013707  lea     rax, [rbp+220h+var_1D8]
0x14001370b  lea     rbx, ?nothrow@std@@3Unothrow_t@1@B; std::nothrow_t const std::nothrow
0x140013712  cmp     r8, rax
0x140013715  jz      short loc_140013726
0x140013717  mov     rdx, rbx; struct std::nothrow_t *
0x14001371a  mov     rcx, r8; void *
0x14001371d  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x140013722  mov     rcx, [rbp+220h+var_288]; void *
0x140013726  lea     rax, [rbp+220h+var_278]
0x14001372a  cmp     rcx, rax
0x14001372d  jz      short loc_140013738
0x14001372f  mov     rdx, rbx; struct std::nothrow_t *
0x140013732  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x140013737  nop
0x140013738  lea     rax, [rbp+220h+var_1B8]
0x14001373c  mov     rcx, [rbp+220h+var_1C8]; void *
0x140013740  cmp     rcx, rax
0x140013743  jz      short loc_14001374E
0x140013745  mov     rdx, rbx; struct std::nothrow_t *
0x140013748  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x14001374d  nop
0x14001374e  lea     rax, [rbp+220h+var_258]
0x140013752  mov     rcx, [rbp+220h+var_268]; void *
0x140013756  cmp     rcx, rax
0x140013759  jz      short loc_140013764
0x14001375b  mov     rdx, rbx; struct std::nothrow_t *
0x14001375e  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x140013763  nop
0x140013764  lea     rax, [rbp+220h+var_238]
0x140013768  mov     rcx, [rbp+220h+var_248]; void *
0x14001376c  cmp     rcx, rax
0x14001376f  jz      short loc_14001377A
0x140013771  mov     rdx, rbx; struct std::nothrow_t *
0x140013774  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x140013779  nop
0x14001377a  lea     rax, [rbp+220h+var_218]
0x14001377e  mov     rcx, [rbp+220h+var_228]; void *
0x140013782  cmp     rcx, rax
0x140013785  jz      short loc_140013790
0x140013787  mov     rdx, rbx; struct std::nothrow_t *
0x14001378a  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x14001378f  nop
0x140013790  lea     rax, [rbp+220h+var_1F8]
0x140013794  mov     rcx, [rbp+220h+var_208]; void *
0x140013798  cmp     rcx, rax
0x14001379b  jz      short loc_1400137A6
0x14001379d  mov     rdx, rbx; struct std::nothrow_t *
0x1400137a0  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1400137a5  nop
0x1400137a6  lea     rax, [rbp+220h+var_2A0]
0x1400137aa  mov     rcx, [rsp+320h+var_2B0]; void *
0x1400137af  cmp     rcx, rax
0x1400137b2  jz      short loc_1400137BC
0x1400137b4  mov     rdx, rbx; struct std::nothrow_t *
0x1400137b7  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1400137bc  mov     eax, 80070057h
0x1400137c1  jmp     loc_140013FC7
0x1400137c6  mov     [rbp+220h+VersionInformation.dwOSVersionInfoSize], 11Ch
0x1400137d0  lea     rcx, [rbp+220h+VersionInformation]; lpVersionInformation
0x1400137d7  call    cs:__imp_RtlGetVersion
0x1400137dd  mov     edi, eax
0x1400137df  test    eax, eax
0x1400137e1  js      loc_140013ED8
0x1400137e7  movzx   r9d, [rbp+220h+var_5A]; dwSpMinorVersion
0x1400137ef  movzx   r8d, [rbp+220h+var_5C]; dwSpMajorVersion
0x1400137f7  lea     rax, [rbp+220h+var_290]
0x1400137fb  mov     [rsp+320h+pdwReturnedProductType], rax; pdwReturnedProductType
0x140013800  mov     edx, [rbp+220h+VersionInformation.dwMinorVersion]; dwOSMinorVersion
0x140013806  mov     ecx, [rbp+220h+VersionInformation.dwMajorVersion]; dwOSMajorVersion
0x14001380c  call    cs:__imp_GetProductInfo
0x140013812  lea     rsi, WPP_GLOBAL_Control
0x140013819  test    eax, eax
0x14001381b  jnz     short loc_140013858
0x14001381d  mov     rax, cs:WPP_GLOBAL_Control
0x140013824  cmp     rax, rsi
0x140013827  jz      short loc_140013854
0x140013829  test    byte ptr [rax+1Ch], 1
0x14001382d  jz      short loc_140013854
0x14001382f  call    cs:__imp_GetLastError
0x140013835  mov     edx, 44h ; 'D'
0x14001383a  mov     r9d, eax
0x14001383d  lea     r8, WPP_988ce82756cb3ec502560a762615dae0_Traceguids
0x140013844  mov     rcx, cs:WPP_GLOBAL_Control
0x14001384b  mov     rcx, [rcx+10h]
0x14001384f  call    WPP_SF_d
0x140013854  mov     [rbp+220h+var_290], r12d
0x140013858  mov     [rsp+320h+var_2F8], r12b; char
0x14001385d  lea     rax, [rbp+220h+var_208]
0x140013861  mov     [rsp+320h+pdwReturnedProductType], rax; __int64
0x140013866  lea     r15, aUnknown_0; "Unknown"
0x14001386d  mov     r9, r15
0x140013870  lea     r8, aProductname; "ProductName"
0x140013877  lea     r14, aSoftwareMicros_16; "SOFTWARE\\Microsoft\\Windows NT\\Curren"...
0x14001387e  mov     rdx, r14; lpSubKey
0x140013881  mov     rdi, 0FFFFFFFF80000002h
0x140013888  mov     rcx, rdi; hKey
0x14001388b  call    ?UtilRegGetString@@YAJPEAUHKEY__@@PEB_W11PEAV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@_N3@Z; UtilRegGetString(HKEY__ *,wchar_t const *,wchar_t const *,wchar_t const *,utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> *,bool,bool)
0x140013890  mov     [rsp+320h+var_2F8], r12b; bool
0x140013895  lea     rax, [rbp+220h+var_228]
0x140013899  mov     [rsp+320h+pdwReturnedProductType], rax; __int64
0x14001389e  mov     r9, r15
0x1400138a1  lea     r8, aEditionid; "EditionID"
0x1400138a8  mov     rdx, r14; lpSubKey
0x1400138ab  mov     rcx, rdi; hKey
0x1400138ae  call    ?UtilRegGetString@@YAJPEAUHKEY__@@PEB_W11PEAV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@_N3@Z; UtilRegGetString(HKEY__ *,wchar_t const *,wchar_t const *,wchar_t const *,utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> *,bool,bool)
0x1400138b3  mov     [rsp+320h+pdwReturnedProductType], r12; bool *
0x1400138b8  xor     r9d, r9d; unsigned int
0x1400138bb  lea     r8, aUbr_0; "Ubr"
0x1400138c2  mov     rdx, r14; lpSubKey
0x1400138c5  mov     rcx, rdi; hKey
0x1400138c8  call    ?UtilRegGetDWORD@@YAKPEAUHKEY__@@PEB_W1KPEA_N_N@Z; UtilRegGetDWORD(HKEY__ *,wchar_t const *,wchar_t const *,ulong,bool *,bool)
0x1400138cd  mov     r8d, eax
0x1400138d0  lea     r13, aU; "%u"
0x1400138d7  mov     rdx, r13
0x1400138da  lea     rcx, [rbp+220h+var_288]
0x1400138de  call    ??$assign_sprintf@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@tlx@@YAJAEAV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@PEB_WZZ; tlx::assign_sprintf<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> &,wchar_t const *,...)
0x1400138e3  lea     rcx, [rbp+220h+var_268]
0x1400138e7  call    ?UtilGetPlatformVersion@@YAJPEAV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@@Z; UtilGetPlatformVersion(utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> *)
0x1400138ec  mov     [rsp+320h+var_2F8], r12b; char
0x1400138f1  lea     rax, [rbp+220h+var_248]
0x1400138f5  mov     [rsp+320h+pdwReturnedProductType], rax; __int64
0x1400138fa  mov     r9, r15
0x1400138fd  lea     r8, aCurrenttype; "CurrentType"
0x140013904  mov     rdx, r14; lpSubKey
0x140013907  mov     rcx, rdi; hKey
0x14001390a  call    ?UtilRegGetString@@YAJPEAUHKEY__@@PEB_W11PEAV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@_N3@Z; UtilRegGetString(HKEY__ *,wchar_t const *,wchar_t const *,wchar_t const *,utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> *,bool,bool)
0x14001390f  xorps   xmm0, xmm0
0x140013912  movdqa  [rsp+320h+var_2E0], xmm0
0x140013918  xorps   xmm1, xmm1
0x14001391b  movdqa  [rsp+320h+var_2C0], xmm1
0x140013921  lea     rax, aOsversioninfor; "OSVersionInformation"
0x140013928  mov     qword ptr [rsp+320h+var_2D0], rax
0x14001392d  mov     qword ptr [rsp+320h+var_2D0+8], 14h
0x140013936  lea     rax, [rsp+320h+var_2E0]
0x14001393b  mov     [rsp+320h+pdwReturnedProductType], rax
0x140013940  xor     r9d, r9d
0x140013943  lea     r8, [rsp+320h+var_2C0]
0x140013948  lea     rdx, [rsp+320h+var_2D0]
0x14001394d  mov     rcx, rbx
0x140013950  call    ?BeginElement@CXMLWriter@@QEAAJV?$basic_string_view@_WU?$char_traits@_W@utl@@@utl@@0_NV?$span@$$CBUCXMLAttribute@@$0?0@3@@Z; CXMLWriter::BeginElement(utl::basic_string_view<wchar_t,utl::char_traits<wchar_t>>,utl::basic_string_view<wchar_t,utl::char_traits<wchar_t>>,bool,utl::span<CXMLAttribute const,-1>)
0x140013955  mov     r9d, [rbp+220h+VersionInformation.dwMinorVersion]
0x14001395c  mov     r8d, [rbp+220h+VersionInformation.dwMajorVersion]
0x140013963  lea     rdx, aUU; "%u.%u"
0x14001396a  lea     rcx, [rsp+320h+var_2B0]
0x14001396f  call    ??$assign_sprintf@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@tlx@@YAJAEAV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@PEB_WZZ; tlx::assign_sprintf<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> &,wchar_t const *,...)
0x140013974  xorps   xmm0, xmm0
0x140013977  movdqa  [rsp+320h+var_2C0], xmm0
0x14001397d  mov     rax, [rsp+320h+var_2B0]
0x140013982  mov     qword ptr [rsp+320h+var_2D0], rax
0x140013987  mov     rcx, [rsp+320h+var_2A8]
0x14001398c  sub     rcx, rax
0x14001398f  sar     rcx, 1
0x140013992  mov     qword ptr [rsp+320h+var_2D0+8], rcx
0x140013997  lea     rax, aWindowsntversi; "WindowsNTVersion"
0x14001399e  mov     qword ptr [rsp+320h+var_2E0], rax
0x1400139a3  mov     qword ptr [rsp+320h+var_2E0+8], 10h
0x1400139ac  lea     rax, [rsp+320h+var_2C0]
0x1400139b1  mov     [rsp+320h+pdwReturnedProductType], rax
0x1400139b6  mov     r9b, 1
0x1400139b9  lea     r8, [rsp+320h+var_2D0]
0x1400139be  lea     rdx, [rsp+320h+var_2E0]
0x1400139c3  mov     rcx, rbx
0x1400139c6  call    ?BeginElement@CXMLWriter@@QEAAJV?$basic_string_view@_WU?$char_traits@_W@utl@@@utl@@0_NV?$span@$$CBUCXMLAttribute@@$0?0@3@@Z; CXMLWriter::BeginElement(utl::basic_string_view<wchar_t,utl::char_traits<wchar_t>>,utl::basic_string_view<wchar_t,utl::char_traits<wchar_t>>,bool,utl::span<CXMLAttribute const,-1>)
0x1400139cb  mov     r8d, [rbp+220h+VersionInformation.dwBuildNumber]
0x1400139d2  lea     rcx, [rsp+320h+var_2B0]
0x1400139d7  cmp     [rbp+220h+VersionInformation.szCSDVersion], r12w
0x1400139df  jz      short loc_1400139F6
0x1400139e1  lea     r9, [rbp+220h+VersionInformation.szCSDVersion]
0x1400139e8  lea     rdx, aULs; "%u %ls"
0x1400139ef  call    ??$assign_sprintf@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@tlx@@YAJAEAV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@PEB_WZZ; tlx::assign_sprintf<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> &,wchar_t const *,...)
0x1400139f4  jmp     short loc_1400139FE
0x1400139f6  mov     rdx, r13
0x1400139f9  call    ??$assign_sprintf@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@tlx@@YAJAEAV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@PEB_WZZ; tlx::assign_sprintf<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> &,wchar_t const *,...)
0x1400139fe  xorps   xmm0, xmm0
0x140013a01  movdqa  [rsp+320h+var_2C0], xmm0
0x140013a07  mov     rax, [rsp+320h+var_2B0]
0x140013a0c  mov     qword ptr [rsp+320h+var_2E0], rax
0x140013a11  mov     rcx, [rsp+320h+var_2A8]
0x140013a16  sub     rcx, rax
0x140013a19  sar     rcx, 1
0x140013a1c  mov     qword ptr [rsp+320h+var_2E0+8], rcx
0x140013a21  lea     rax, aBuild; "Build"
0x140013a28  mov     qword ptr [rsp+320h+var_2D0], rax
0x140013a2d  mov     r14d, 5
0x140013a33  mov     qword ptr [rsp+320h+var_2D0+8], r14
0x140013a38  lea     rax, [rsp+320h+var_2C0]
0x140013a3d  mov     [rsp+320h+pdwReturnedProductType], rax
0x140013a42  mov     r9b, 1
0x140013a45  lea     r8, [rsp+320h+var_2E0]
0x140013a4a  lea     rdx, [rsp+320h+var_2D0]
0x140013a4f  mov     rcx, rbx
0x140013a52  call    ?BeginElement@CXMLWriter@@QEAAJV?$basic_string_view@_WU?$char_traits@_W@utl@@@utl@@0_NV?$span@$$CBUCXMLAttribute@@$0?0@3@@Z; CXMLWriter::BeginElement(utl::basic_string_view<wchar_t,utl::char_traits<wchar_t>>,utl::basic_string_view<wchar_t,utl::char_traits<wchar_t>>,bool,utl::span<CXMLAttribute const,-1>)
0x140013a57  mov     r9, [rbp+220h+var_208]
0x140013a5b  mov     r8d, [rbp+220h+var_290]
0x140013a5f  lea     rdx, a0xXLs; "(0x%x): %ls"
0x140013a66  lea     rcx, [rsp+320h+var_2B0]
0x140013a6b  call    ??$assign_sprintf@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@tlx@@YAJAEAV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@PEB_WZZ; tlx::assign_sprintf<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> &,wchar_t const *,...)
0x140013a70  xorps   xmm0, xmm0
0x140013a73  movdqa  [rsp+320h+var_2C0], xmm0
0x140013a79  mov     rax, [rsp+320h+var_2B0]
0x140013a7e  mov     qword ptr [rsp+320h+var_2E0], rax
0x140013a83  mov     rcx, [rsp+320h+var_2A8]
0x140013a88  sub     rcx, rax
0x140013a8b  sar     rcx, 1
0x140013a8e  mov     qword ptr [rsp+320h+var_2E0+8], rcx
0x140013a93  lea     rax, aProduct; "Product"
0x140013a9a  mov     qword ptr [rsp+320h+var_2D0], rax
0x140013a9f  lea     edi, [r14+2]
0x140013aa3  mov     qword ptr [rsp+320h+var_2D0+8], rdi
0x140013aa8  lea     rax, [rsp+320h+var_2C0]
0x140013aad  mov     [rsp+320h+pdwReturnedProductType], rax
0x140013ab2  mov     r9b, 1
0x140013ab5  lea     r8, [rsp+320h+var_2E0]
0x140013aba  lea     rdx, [rsp+320h+var_2D0]
0x140013abf  mov     rcx, rbx
0x140013ac2  call    ?BeginElement@CXMLWriter@@QEAAJV?$basic_string_view@_WU?$char_traits@_W@utl@@@utl@@0_NV?$span@$$CBUCXMLAttribute@@$0?0@3@@Z; CXMLWriter::BeginElement(utl::basic_string_view<wchar_t,utl::char_traits<wchar_t>>,utl::basic_string_view<wchar_t,utl::char_traits<wchar_t>>,bool,utl::span<CXMLAttribute const,-1>)
0x140013ac7  xorps   xmm0, xmm0
0x140013aca  movdqa  [rsp+320h+var_2C0], xmm0
0x140013ad0  mov     rax, [rbp+220h+var_228]
0x140013ad4  mov     qword ptr [rsp+320h+var_2E0], rax
0x140013ad9  mov     rcx, [rbp+220h+var_220]
0x140013add  sub     rcx, rax
  ... truncated ...
```
