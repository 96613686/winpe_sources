# UtilWriteOSVersionInfo(CXMLWriter *)

- ea: `0x140013f04`
- end: `0x140014953`
- name: `?UtilWriteOSVersionInfo@@YAJPEAVCXMLWriter@@@Z`
- size: `2639`
- prototype: `__int64 __fastcall(struct CXMLWriter *)`
- caller_count: `1`
- callee_count: `15`
- tags: `file_ops, registry_config, loader_planting, broker_com_uri`

## callers

- `0x140021b9c`

## callees

- `0x140002490`
- `0x140002748`
- `0x1400030f8`
- `0x1400054e4`
- `0x14000ca20`
- `0x14000ee84`
- `0x14000f008`
- `0x140011158`
- `0x140012994`
- `0x140012a9c`
- `0x140013940`
- `0x140013f04`
- `0x140014ee4`
- `0x140014f14`
- `0x140015e5c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14001417f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14001417f`
- `api-ms-win-core-localization-l1-2-0!GetThreadUILanguage` at `0x140014649`
- `api-ms-win-core-localization-l1-2-0!GetThreadUILanguage` at `0x140014649`
- `api-ms-win-core-localization-l1-2-0!GetUserGeoID` at `0x1400146bf`
- `api-ms-win-core-localization-l1-2-0!GetUserGeoID` at `0x1400146bf`
- `api-ms-win-core-sysinfo-l1-2-0!GetProductInfo` at `0x140014156`
- `api-ms-win-core-sysinfo-l1-2-0!GetProductInfo` at `0x140014156`
- `api-ms-win-core-sysinfo-l1-2-0!GetNativeSystemInfo` at `0x140014571`
- `api-ms-win-core-sysinfo-l1-2-0!GetNativeSystemInfo` at `0x140014571`
- `ntdll!RtlGetVersion` at `0x14001411b`
- `ntdll!RtlGetVersion` at `0x14001411b`

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
  const wchar_t *v15; // rdx
  int v16; // r9d
  LANGID ThreadUILanguage; // ax
  int v18; // r9d
  unsigned int UserGeoID; // eax
  int v20; // r9d
  int v21; // r9d
  int v22; // eax
  unsigned int v23; // edi
  bool v24; // [rsp+28h] [rbp-D8h]
  DWORD v25; // [rsp+30h] [rbp-D0h]
  DWORD v26; // [rsp+30h] [rbp-D0h]
  DWORD v27; // [rsp+30h] [rbp-D0h]
  __int128 v28; // [rsp+40h] [rbp-C0h] BYREF
  __int128 v29; // [rsp+50h] [rbp-B0h] BYREF
  __int128 v30; // [rsp+60h] [rbp-A0h] BYREF
  void *v31; // [rsp+70h] [rbp-90h] BYREF
  char *v32; // [rsp+78h] [rbp-88h]
  _WORD v33[8]; // [rsp+80h] [rbp-80h] BYREF
  DWORD pdwReturnedProductType; // [rsp+90h] [rbp-70h] BYREF
  void *v35; // [rsp+98h] [rbp-68h] BYREF
  char *v36; // [rsp+A0h] [rbp-60h]
  _WORD v37[8]; // [rsp+A8h] [rbp-58h] BYREF
  void *v38; // [rsp+B8h] [rbp-48h] BYREF
  char *v39; // [rsp+C0h] [rbp-40h]
  _WORD v40[8]; // [rsp+C8h] [rbp-38h] BYREF
  void *v41; // [rsp+D8h] [rbp-28h] BYREF
  char *v42; // [rsp+E0h] [rbp-20h]
  _WORD v43[8]; // [rsp+E8h] [rbp-18h] BYREF
  void *v44; // [rsp+F8h] [rbp-8h] BYREF
  char *v45; // [rsp+100h] [rbp+0h]
  _WORD v46[8]; // [rsp+108h] [rbp+8h] BYREF
  void *v47[2]; // [rsp+118h] [rbp+18h] BYREF
  _WORD v48[8]; // [rsp+128h] [rbp+28h] BYREF
  void *v49; // [rsp+138h] [rbp+38h]
  _WORD *v50; // [rsp+140h] [rbp+40h]
  _WORD v51[8]; // [rsp+148h] [rbp+48h] BYREF
  void *v52; // [rsp+158h] [rbp+58h]
  _WORD *v53; // [rsp+160h] [rbp+60h]
  _WORD v54[8]; // [rsp+168h] [rbp+68h] BYREF
  _SYSTEM_INFO SystemInfo; // [rsp+178h] [rbp+78h] BYREF
  struct _OSVERSIONINFOW VersionInformation; // [rsp+1B0h] [rbp+B0h] BYREF
  unsigned __int16 v57; // [rsp+2C4h] [rbp+1C4h]
  unsigned __int16 v58; // [rsp+2C6h] [rbp+1C6h]

  memset_0(&VersionInformation.dwMajorVersion, 0, 0x118u);
  v31 = v33;
  v32 = (char *)v33;
  v33[0] = 0;
  memset(&SystemInfo, 0, sizeof(SystemInfo));
  pdwReturnedProductType = 0;
  v47[0] = v48;
  v47[1] = v48;
  v48[0] = 0;
  v44 = v46;
  v45 = (char *)v46;
  v46[0] = 0;
  v41 = v43;
  v42 = (char *)v43;
  v43[0] = 0;
  v38 = v40;
  v39 = (char *)v40;
  v40[0] = 0;
  v52 = v54;
  v53 = v54;
  v54[0] = 0;
  v2 = v37;
  v35 = v37;
  v36 = (char *)v37;
  v37[0] = 0;
  v3 = v51;
  v49 = v51;
  v50 = v51;
  v51[0] = 0;
  if ( !a1 )
  {
    if ( WPP_GLOBAL_Control != (CUserModeHangReport *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 67, WPP_a64051d924863e2da6af6f261aa69bc0_Traceguids);
      v2 = v35;
      v3 = v49;
    }
    if ( v3 != v51 )
    {
      operator delete(v3, (const struct std::nothrow_t *)&std::nothrow);
      v2 = v35;
    }
    if ( v2 != v37 )
      operator delete(v2, (const struct std::nothrow_t *)&std::nothrow);
    if ( v52 != v54 )
      operator delete(v52, (const struct std::nothrow_t *)&std::nothrow);
    if ( v38 != v40 )
      operator delete(v38, (const struct std::nothrow_t *)&std::nothrow);
    if ( v41 != v43 )
      operator delete(v41, (const struct std::nothrow_t *)&std::nothrow);
    if ( v44 != v46 )
      operator delete(v44, (const struct std::nothrow_t *)&std::nothrow);
    if ( v47[0] != v48 )
      operator delete(v47[0], (const struct std::nothrow_t *)&std::nothrow);
    if ( v31 != v33 )
      operator delete(v31, (const struct std::nothrow_t *)&std::nothrow);
    return 2147942487LL;
  }
  VersionInformation.dwOSVersionInfoSize = 284;
  Version = RtlGetVersion(&VersionInformation);
  if ( Version < 0 )
  {
    v23 = Version | 0x10000000;
    if ( WPP_GLOBAL_Control != (CUserModeHangReport *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 69, WPP_a64051d924863e2da6af6f261aa69bc0_Traceguids, v23);
    }
    goto LABEL_55;
  }
  if ( !GetProductInfo(
          VersionInformation.dwMajorVersion,
          VersionInformation.dwMinorVersion,
          v57,
          v58,
          &pdwReturnedProductType) )
  {
    if ( WPP_GLOBAL_Control != (CUserModeHangReport *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      LastError = GetLastError();
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 68, WPP_a64051d924863e2da6af6f261aa69bc0_Traceguids, LastError);
    }
    pdwReturnedProductType = 0;
  }
  UtilRegGetString(
    HKEY_LOCAL_MACHINE,
    L"SOFTWARE\\Microsoft\\Windows NT\\CurrentVersion",
    L"ProductName",
    (__int64)v47,
    0,
    v25);
  UtilRegGetString(
    HKEY_LOCAL_MACHINE,
    L"SOFTWARE\\Microsoft\\Windows NT\\CurrentVersion",
    L"EditionID",
    (__int64)&v44,
    0,
    v26);
  DWORD = UtilRegGetDWORD(HKEY_LOCAL_MACHINE, L"SOFTWARE\\Microsoft\\Windows NT\\CurrentVersion", L"Ubr", 0, 0, v24);
  tlx::assign_sprintf<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(&v35, L"%u", DWORD);
  UtilGetPlatformVersion(&v38);
  UtilRegGetString(
    HKEY_LOCAL_MACHINE,
    L"SOFTWARE\\Microsoft\\Windows NT\\CurrentVersion",
    L"CurrentType",
    (__int64)&v41,
    0,
    v27);
  v28 = 0;
  v30 = 0;
  *(_QWORD *)&v29 = L"OSVersionInformation";
  *((_QWORD *)&v29 + 1) = 20;
  CXMLWriter::BeginElement((_DWORD)a1, (unsigned int)&v29, (unsigned int)&v30, 0, (__int64)&v28);
  tlx::assign_sprintf<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(
    &v31,
    L"%u.%u",
    VersionInformation.dwMajorVersion,
    VersionInformation.dwMinorVersion);
  v30 = 0;
  *(_QWORD *)&v29 = v31;
  *((_QWORD *)&v29 + 1) = (v32 - (_BYTE *)v31) >> 1;
  *(_QWORD *)&v28 = L"WindowsNTVersion";
  *((_QWORD *)&v28 + 1) = 16;
  LOBYTE(v8) = 1;
  CXMLWriter::BeginElement((_DWORD)a1, (unsigned int)&v28, (unsigned int)&v29, v8, (__int64)&v30);
  if ( VersionInformation.szCSDVersion[0] )
    tlx::assign_sprintf<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(
      &v31,
      L"%u %ls",
      VersionInformation.dwBuildNumber,
      VersionInformation.szCSDVersion);
  else
    tlx::assign_sprintf<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(
      &v31,
      L"%u",
      VersionInformation.dwBuildNumber);
  v30 = 0;
  *(_QWORD *)&v28 = v31;
  *((_QWORD *)&v28 + 1) = (v32 - (_BYTE *)v31) >> 1;
  *(_QWORD *)&v29 = L"Build";
  *((_QWORD *)&v29 + 1) = 5;
  LOBYTE(v9) = 1;
  CXMLWriter::BeginElement((_DWORD)a1, (unsigned int)&v29, (unsigned int)&v28, v9, (__int64)&v30);
  tlx::assign_sprintf<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(
    &v31,
    L"(0x%x): %ls",
    pdwReturnedProductType,
    v47[0]);
  v30 = 0;
  *(_QWORD *)&v28 = v31;
  *((_QWORD *)&v28 + 1) = (v32 - (_BYTE *)v31) >> 1;
  *(_QWORD *)&v29 = L"Product";
  *((_QWORD *)&v29 + 1) = 7;
  LOBYTE(v10) = 1;
  CXMLWriter::BeginElement((_DWORD)a1, (unsigned int)&v29, (unsigned int)&v28, v10, (__int64)&v30);
  v30 = 0;
  *(_QWORD *)&v28 = v44;
  *((_QWORD *)&v28 + 1) = (v45 - (_BYTE *)v44) >> 1;
  *(_QWORD *)&v29 = L"Edition";
  *((_QWORD *)&v29 + 1) = 7;
  LOBYTE(v11) = 1;
  CXMLWriter::BeginElement((_DWORD)a1, (unsigned int)&v29, (unsigned int)&v28, v11, (__int64)&v30);
  v30 = 0;
  *(_QWORD *)&v28 = v38;
  *((_QWORD *)&v28 + 1) = (v39 - (_BYTE *)v38) >> 1;
  *(_QWORD *)&v29 = L"BuildString";
  *((_QWORD *)&v29 + 1) = 11;
  LOBYTE(v12) = 1;
  CXMLWriter::BeginElement((_DWORD)a1, (unsigned int)&v29, (unsigned int)&v28, v12, (__int64)&v30);
  v30 = 0;
  *(_QWORD *)&v28 = v35;
  *((_QWORD *)&v28 + 1) = (v36 - (_BYTE *)v35) >> 1;
  *(_QWORD *)&v29 = L"Revision";
  *((_QWORD *)&v29 + 1) = 8;
  LOBYTE(v13) = 1;
  CXMLWriter::BeginElement((_DWORD)a1, (unsigned int)&v29, (unsigned int)&v28, v13, (__int64)&v30);
  v30 = 0;
  *(_QWORD *)&v28 = v41;
  *((_QWORD *)&v28 + 1) = (v42 - (_BYTE *)v41) >> 1;
  *(_QWORD *)&v29 = L"Flavor";
  *((_QWORD *)&v29 + 1) = 6;
  LOBYTE(v14) = 1;
  CXMLWriter::BeginElement((_DWORD)a1, (unsigned int)&v29, (unsigned int)&v28, v14, (__int64)&v30);
  GetNativeSystemInfo(&SystemInfo);
  if ( SystemInfo.wProcessorArchitecture == 6 )
  {
    v15 = L"IA64";
  }
  else if ( SystemInfo.wProcessorArchitecture == 9 )
  {
    v15 = L"X64";
  }
  else if ( SystemInfo.wProcessorArchitecture )
  {
    if ( SystemInfo.wProcessorArchitecture == 5 )
    {
      v15 = L"ARM";
    }
    else
    {
      if ( SystemInfo.wProcessorArchitecture != 12 )
      {
        tlx::assign_sprintf<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(
          &v31,
          L"%u",
          SystemInfo.wProcessorArchitecture);
        goto LABEL_43;
      }
      v15 = L"ARM64";
    }
  }
  else
  {
    v15 = L"X86";
  }
  utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::assign(&v31, v15);
LABEL_43:
  v30 = 0;
  *(_QWORD *)&v28 = v31;
  *((_QWORD *)&v28 + 1) = (v32 - (_BYTE *)v31) >> 1;
  *(_QWORD *)&v29 = L"Architecture";
  *((_QWORD *)&v29 + 1) = 12;
  LOBYTE(v16) = 1;
  CXMLWriter::BeginElement((_DWORD)a1, (unsigned int)&v29, (unsigned int)&v28, v16, (__int64)&v30);
  ThreadUILanguage = GetThreadUILanguage();
  tlx::assign_sprintf<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(&v31, L"%u", ThreadUILanguage);
  v30 = 0;
  *(_QWORD *)&v28 = v31;
  *((_QWORD *)&v28 + 1) = (v32 - (_BYTE *)v31) >> 1;
  *(_QWORD *)&v29 = L"LCID";
  *((_QWORD *)&v29 + 1) = 4;
  LOBYTE(v18) = 1;
  CXMLWriter::BeginElement((_DWORD)a1, (unsigned int)&v29, (unsigned int)&v28, v18, (__int64)&v30);
  UserGeoID = GetUserGeoID(0);
  if ( UserGeoID != -1 )
  {
    tlx::assign_sprintf<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(&v31, L"%u", UserGeoID);
    v30 = 0;
    *(_QWORD *)&v28 = v31;
    *((_QWORD *)&v28 + 1) = (v32 - (_BYTE *)v31) >> 1;
    *(_QWORD *)&v29 = L"GeoId";
    *((_QWORD *)&v29 + 1) = 5;
    LOBYTE(v20) = 1;
    CXMLWriter::BeginElement((_DWORD)a1, (unsigned int)&v29, (unsigned int)&v28, v20, (__int64)&v30);
  }
  if ( UtilIsMemoryErrorEventSet() )
  {
    v30 = 0;
    *(_QWORD *)&v28 = L"1";
    *((_QWORD *)&v28 + 1) = 1;
    *(_QWORD *)&v29 = L"MemoryError";
    *((_QWORD *)&v29 + 1) = 11;
    LOBYTE(v21) = 1;
    CXMLWriter::BeginElement((_DWORD)a1, (unsigned int)&v29, (unsigned int)&v28, v21, (__int64)&v30);
  }
  v30 = 0;
  v29 = 0;
  *(_QWORD *)&v28 = L"BuildLayers";
  *((_QWORD *)&v28 + 1) = 11;
  CXMLWriter::BeginElement((_DWORD)a1, (unsigned int)&v28, (unsigned int)&v29, 0, (__int64)&v30);
  v22 = UtilWriteOSBuildLayerInfo(a1);
  if ( v22 < 0
    && WPP_GLOBAL_Control != (CUserModeHangReport *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
  {
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      70,
      WPP_a64051d924863e2da6af6f261aa69bc0_Traceguids,
      (unsigned int)v22);
  }
  *(_QWORD *)&v28 = L"BuildLayers";
  *((_QWORD *)&v28 + 1) = 11;
  CXMLWriter::EndElement(a1, &v28);
  *(_QWORD *)&v28 = L"OSVersionInformation";
  *((_QWORD *)&v28 + 1) = 20;
  CXMLWriter::EndElement(a1, &v28);
  v23 = 0;
LABEL_55:
  if ( v49 != v51 )
    operator delete(v49, (const struct std::nothrow_t *)&std::nothrow);
  if ( v35 != v37 )
    operator delete(v35, (const struct std::nothrow_t *)&std::nothrow);
  if ( v52 != v54 )
    operator delete(v52, (const struct std::nothrow_t *)&std::nothrow);
  if ( v38 != v40 )
    operator delete(v38, (const struct std::nothrow_t *)&std::nothrow);
  if ( v41 != v43 )
    operator delete(v41, (const struct std::nothrow_t *)&std::nothrow);
  if ( v44 != v46 )
    operator delete(v44, (const struct std::nothrow_t *)&std::nothrow);
  if ( v47[0] != v48 )
    operator delete(v47[0], (const struct std::nothrow_t *)&std::nothrow);
  if ( v31 != v33 )
    operator delete(v31, (const struct std::nothrow_t *)&std::nothrow);
  return v23;
}

```

## disassembly

```asm
0x140013f04  push    rbp
0x140013f06  push    rbx
0x140013f07  push    rsi
0x140013f08  push    rdi
0x140013f09  push    r12
0x140013f0b  push    r13
0x140013f0d  push    r14
0x140013f0f  push    r15
0x140013f11  lea     rbp, [rsp-1E8h]
0x140013f19  sub     rsp, 2E8h
0x140013f20  mov     rax, cs:__security_cookie
0x140013f27  xor     rax, rsp
0x140013f2a  mov     [rbp+220h+var_50], rax
0x140013f31  mov     rbx, rcx
0x140013f34  xor     edx, edx; Val
0x140013f36  mov     r8d, 118h; Size
0x140013f3c  lea     rcx, [rbp+220h+VersionInformation.dwMajorVersion]; void *
0x140013f43  call    memset_0
0x140013f48  lea     rax, [rbp+220h+var_2A0]
0x140013f4c  mov     [rsp+320h+var_2B0], rax
0x140013f51  lea     rax, [rbp+220h+var_2A0]
0x140013f55  mov     [rsp+320h+var_2A8], rax
0x140013f5a  xor     r12d, r12d
0x140013f5d  mov     [rbp+220h+var_2A0], r12w
0x140013f62  xorps   xmm0, xmm0
0x140013f65  movups  xmmword ptr [rbp+220h+SystemInfo], xmm0
0x140013f69  movups  xmmword ptr [rbp+220h+SystemInfo.lpMaximumApplicationAddress], xmm0
0x140013f70  movups  xmmword ptr [rbp+220h+SystemInfo.dwNumberOfProcessors], xmm0
0x140013f77  mov     [rbp+220h+var_290], r12d
0x140013f7b  lea     rax, [rbp+220h+var_1F8]
0x140013f7f  mov     [rbp+220h+var_208], rax
0x140013f83  lea     rax, [rbp+220h+var_1F8]
0x140013f87  mov     [rbp+220h+var_200], rax
0x140013f8b  mov     [rbp+220h+var_1F8], r12w
0x140013f90  lea     rax, [rbp+220h+var_218]
0x140013f94  mov     [rbp+220h+var_228], rax
0x140013f98  lea     rax, [rbp+220h+var_218]
0x140013f9c  mov     [rbp+220h+var_220], rax
0x140013fa0  mov     [rbp+220h+var_218], r12w
0x140013fa5  lea     rax, [rbp+220h+var_238]
0x140013fa9  mov     [rbp+220h+var_248], rax
0x140013fad  lea     rax, [rbp+220h+var_238]
0x140013fb1  mov     [rbp+220h+var_240], rax
0x140013fb5  mov     [rbp+220h+var_238], r12w
0x140013fba  lea     rax, [rbp+220h+var_258]
0x140013fbe  mov     [rbp+220h+var_268], rax
0x140013fc2  lea     rax, [rbp+220h+var_258]
0x140013fc6  mov     [rbp+220h+var_260], rax
0x140013fca  mov     [rbp+220h+var_258], r12w
0x140013fcf  lea     rax, [rbp+220h+var_1B8]
0x140013fd3  mov     [rbp+220h+var_1C8], rax
0x140013fd7  lea     rax, [rbp+220h+var_1B8]
0x140013fdb  mov     [rbp+220h+var_1C0], rax
0x140013fdf  mov     [rbp+220h+var_1B8], r12w
0x140013fe4  lea     rcx, [rbp+220h+var_278]
0x140013fe8  mov     [rbp+220h+var_288], rcx
0x140013fec  lea     rax, [rbp+220h+var_278]
0x140013ff0  mov     [rbp+220h+var_280], rax
0x140013ff4  mov     [rbp+220h+var_278], r12w
0x140013ff9  lea     r8, [rbp+220h+var_1D8]
0x140013ffd  mov     [rbp+220h+var_1E8], r8
0x140014001  lea     rax, [rbp+220h+var_1D8]
0x140014005  mov     [rbp+220h+var_1E0], rax
0x140014009  mov     [rbp+220h+var_1D8], r12w
0x14001400e  test    rbx, rbx
0x140014011  jnz     loc_14001410A
0x140014017  lea     rsi, WPP_GLOBAL_Control
0x14001401e  mov     rax, cs:WPP_GLOBAL_Control
0x140014025  cmp     rax, rsi
0x140014028  jz      short loc_14001404B
0x14001402a  test    byte ptr [rax+1Ch], 1
0x14001402e  jz      short loc_14001404B
0x140014030  lea     edx, [rbx+43h]
0x140014033  lea     r8, WPP_a64051d924863e2da6af6f261aa69bc0_Traceguids
0x14001403a  mov     rcx, [rax+10h]
0x14001403e  call    WPP_SF_
0x140014043  mov     rcx, [rbp+220h+var_288]
0x140014047  mov     r8, [rbp+220h+var_1E8]
0x14001404b  lea     rax, [rbp+220h+var_1D8]
0x14001404f  lea     rbx, ?nothrow@std@@3Unothrow_t@1@B; std::nothrow_t const std::nothrow
0x140014056  cmp     r8, rax
0x140014059  jz      short loc_14001406A
0x14001405b  mov     rdx, rbx; struct std::nothrow_t *
0x14001405e  mov     rcx, r8; void *
0x140014061  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x140014066  mov     rcx, [rbp+220h+var_288]; void *
0x14001406a  lea     rax, [rbp+220h+var_278]
0x14001406e  cmp     rcx, rax
0x140014071  jz      short loc_14001407C
0x140014073  mov     rdx, rbx; struct std::nothrow_t *
0x140014076  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x14001407b  nop
0x14001407c  lea     rax, [rbp+220h+var_1B8]
0x140014080  mov     rcx, [rbp+220h+var_1C8]; void *
0x140014084  cmp     rcx, rax
0x140014087  jz      short loc_140014092
0x140014089  mov     rdx, rbx; struct std::nothrow_t *
0x14001408c  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x140014091  nop
0x140014092  lea     rax, [rbp+220h+var_258]
0x140014096  mov     rcx, [rbp+220h+var_268]; void *
0x14001409a  cmp     rcx, rax
0x14001409d  jz      short loc_1400140A8
0x14001409f  mov     rdx, rbx; struct std::nothrow_t *
0x1400140a2  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1400140a7  nop
0x1400140a8  lea     rax, [rbp+220h+var_238]
0x1400140ac  mov     rcx, [rbp+220h+var_248]; void *
0x1400140b0  cmp     rcx, rax
0x1400140b3  jz      short loc_1400140BE
0x1400140b5  mov     rdx, rbx; struct std::nothrow_t *
0x1400140b8  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1400140bd  nop
0x1400140be  lea     rax, [rbp+220h+var_218]
0x1400140c2  mov     rcx, [rbp+220h+var_228]; void *
0x1400140c6  cmp     rcx, rax
0x1400140c9  jz      short loc_1400140D4
0x1400140cb  mov     rdx, rbx; struct std::nothrow_t *
0x1400140ce  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1400140d3  nop
0x1400140d4  lea     rax, [rbp+220h+var_1F8]
0x1400140d8  mov     rcx, [rbp+220h+var_208]; void *
0x1400140dc  cmp     rcx, rax
0x1400140df  jz      short loc_1400140EA
0x1400140e1  mov     rdx, rbx; struct std::nothrow_t *
0x1400140e4  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1400140e9  nop
0x1400140ea  lea     rax, [rbp+220h+var_2A0]
0x1400140ee  mov     rcx, [rsp+320h+var_2B0]; void *
0x1400140f3  cmp     rcx, rax
0x1400140f6  jz      short loc_140014100
0x1400140f8  mov     rdx, rbx; struct std::nothrow_t *
0x1400140fb  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x140014100  mov     eax, 80070057h
0x140014105  jmp     loc_14001492F
0x14001410a  mov     [rbp+220h+VersionInformation.dwOSVersionInfoSize], 11Ch
0x140014114  lea     rcx, [rbp+220h+VersionInformation]; lpVersionInformation
0x14001411b  call    cs:__imp_RtlGetVersion
0x140014122  nop     dword ptr [rax+rax+00h]
0x140014127  mov     edi, eax
0x140014129  test    eax, eax
0x14001412b  js      loc_140014840
0x140014131  movzx   r9d, [rbp+220h+var_5A]; dwSpMinorVersion
0x140014139  movzx   r8d, [rbp+220h+var_5C]; dwSpMajorVersion
0x140014141  lea     rax, [rbp+220h+var_290]
0x140014145  mov     [rsp+320h+pdwReturnedProductType], rax; pdwReturnedProductType
0x14001414a  mov     edx, [rbp+220h+VersionInformation.dwMinorVersion]; dwOSMinorVersion
0x140014150  mov     ecx, [rbp+220h+VersionInformation.dwMajorVersion]; dwOSMajorVersion
0x140014156  call    cs:__imp_GetProductInfo
0x14001415d  nop     dword ptr [rax+rax+00h]
0x140014162  lea     rsi, WPP_GLOBAL_Control
0x140014169  test    eax, eax
0x14001416b  jnz     short loc_1400141AE
0x14001416d  mov     rax, cs:WPP_GLOBAL_Control
0x140014174  cmp     rax, rsi
0x140014177  jz      short loc_1400141AA
0x140014179  test    byte ptr [rax+1Ch], 1
0x14001417d  jz      short loc_1400141AA
0x14001417f  call    cs:__imp_GetLastError
0x140014186  nop     dword ptr [rax+rax+00h]
0x14001418b  mov     edx, 44h ; 'D'
0x140014190  mov     r9d, eax
0x140014193  lea     r8, WPP_a64051d924863e2da6af6f261aa69bc0_Traceguids
0x14001419a  mov     rcx, cs:WPP_GLOBAL_Control
0x1400141a1  mov     rcx, [rcx+10h]
0x1400141a5  call    WPP_SF_d
0x1400141aa  mov     [rbp+220h+var_290], r12d
0x1400141ae  mov     [rsp+320h+var_2F8], r12b; char
0x1400141b3  lea     rax, [rbp+220h+var_208]
0x1400141b7  mov     [rsp+320h+pdwReturnedProductType], rax; __int64
0x1400141bc  lea     r15, aUnknown_0; "Unknown"
0x1400141c3  mov     r9, r15
0x1400141c6  lea     r8, aProductname; "ProductName"
0x1400141cd  lea     r14, aSoftwareMicros_16; "SOFTWARE\\Microsoft\\Windows NT\\Curren"...
0x1400141d4  mov     rdx, r14; lpSubKey
0x1400141d7  mov     rdi, 0FFFFFFFF80000002h
0x1400141de  mov     rcx, rdi; hKey
0x1400141e1  call    ?UtilRegGetString@@YAJPEAUHKEY__@@PEB_W11PEAV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@_N3@Z; UtilRegGetString(HKEY__ *,wchar_t const *,wchar_t const *,wchar_t const *,utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> *,bool,bool)
0x1400141e6  mov     [rsp+320h+var_2F8], r12b; bool
0x1400141eb  lea     rax, [rbp+220h+var_228]
0x1400141ef  mov     [rsp+320h+pdwReturnedProductType], rax; __int64
0x1400141f4  mov     r9, r15
0x1400141f7  lea     r8, aEditionid; "EditionID"
0x1400141fe  mov     rdx, r14; lpSubKey
0x140014201  mov     rcx, rdi; hKey
0x140014204  call    ?UtilRegGetString@@YAJPEAUHKEY__@@PEB_W11PEAV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@_N3@Z; UtilRegGetString(HKEY__ *,wchar_t const *,wchar_t const *,wchar_t const *,utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> *,bool,bool)
0x140014209  mov     [rsp+320h+pdwReturnedProductType], r12; bool *
0x14001420e  xor     r9d, r9d; unsigned int
0x140014211  lea     r8, aUbr_0; "Ubr"
0x140014218  mov     rdx, r14; lpSubKey
0x14001421b  mov     rcx, rdi; hKey
0x14001421e  call    ?UtilRegGetDWORD@@YAKPEAUHKEY__@@PEB_W1KPEA_N_N@Z; UtilRegGetDWORD(HKEY__ *,wchar_t const *,wchar_t const *,ulong,bool *,bool)
0x140014223  mov     r8d, eax
0x140014226  lea     r13, aU; "%u"
0x14001422d  mov     rdx, r13
0x140014230  lea     rcx, [rbp+220h+var_288]
0x140014234  call    ??$assign_sprintf@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@tlx@@YAJAEAV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@PEB_WZZ; tlx::assign_sprintf<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> &,wchar_t const *,...)
0x140014239  lea     rcx, [rbp+220h+var_268]
0x14001423d  call    ?UtilGetPlatformVersion@@YAJPEAV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@@Z; UtilGetPlatformVersion(utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> *)
0x140014242  mov     [rsp+320h+var_2F8], r12b; char
0x140014247  lea     rax, [rbp+220h+var_248]
0x14001424b  mov     [rsp+320h+pdwReturnedProductType], rax; __int64
0x140014250  mov     r9, r15
0x140014253  lea     r8, aCurrenttype; "CurrentType"
0x14001425a  mov     rdx, r14; lpSubKey
0x14001425d  mov     rcx, rdi; hKey
0x140014260  call    ?UtilRegGetString@@YAJPEAUHKEY__@@PEB_W11PEAV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@_N3@Z; UtilRegGetString(HKEY__ *,wchar_t const *,wchar_t const *,wchar_t const *,utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> *,bool,bool)
0x140014265  xorps   xmm0, xmm0
0x140014268  movdqa  [rsp+320h+var_2E0], xmm0
0x14001426e  xorps   xmm1, xmm1
0x140014271  movdqa  [rsp+320h+var_2C0], xmm1
0x140014277  lea     rax, aOsversioninfor; "OSVersionInformation"
0x14001427e  mov     qword ptr [rsp+320h+var_2D0], rax
0x140014283  mov     qword ptr [rsp+320h+var_2D0+8], 14h
0x14001428c  lea     rax, [rsp+320h+var_2E0]
0x140014291  mov     [rsp+320h+pdwReturnedProductType], rax
0x140014296  xor     r9d, r9d
0x140014299  lea     r8, [rsp+320h+var_2C0]
0x14001429e  lea     rdx, [rsp+320h+var_2D0]
0x1400142a3  mov     rcx, rbx
0x1400142a6  call    ?BeginElement@CXMLWriter@@QEAAJV?$basic_string_view@_WU?$char_traits@_W@utl@@@utl@@0_NV?$span@$$CBUCXMLAttribute@@$0?0@3@@Z; CXMLWriter::BeginElement(utl::basic_string_view<wchar_t,utl::char_traits<wchar_t>>,utl::basic_string_view<wchar_t,utl::char_traits<wchar_t>>,bool,utl::span<CXMLAttribute const,-1>)
0x1400142ab  mov     r9d, [rbp+220h+VersionInformation.dwMinorVersion]
0x1400142b2  mov     r8d, [rbp+220h+VersionInformation.dwMajorVersion]
0x1400142b9  lea     rdx, aUU; "%u.%u"
0x1400142c0  lea     rcx, [rsp+320h+var_2B0]
0x1400142c5  call    ??$assign_sprintf@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@tlx@@YAJAEAV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@PEB_WZZ; tlx::assign_sprintf<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> &,wchar_t const *,...)
0x1400142ca  xorps   xmm0, xmm0
0x1400142cd  movdqa  [rsp+320h+var_2C0], xmm0
0x1400142d3  mov     rax, [rsp+320h+var_2B0]
0x1400142d8  mov     qword ptr [rsp+320h+var_2D0], rax
0x1400142dd  mov     rcx, [rsp+320h+var_2A8]
0x1400142e2  sub     rcx, rax
0x1400142e5  sar     rcx, 1
0x1400142e8  mov     qword ptr [rsp+320h+var_2D0+8], rcx
0x1400142ed  lea     rax, aWindowsntversi; "WindowsNTVersion"
0x1400142f4  mov     qword ptr [rsp+320h+var_2E0], rax
0x1400142f9  mov     qword ptr [rsp+320h+var_2E0+8], 10h
0x140014302  lea     rax, [rsp+320h+var_2C0]
0x140014307  mov     [rsp+320h+pdwReturnedProductType], rax
0x14001430c  mov     r9b, 1
0x14001430f  lea     r8, [rsp+320h+var_2D0]
0x140014314  lea     rdx, [rsp+320h+var_2E0]
0x140014319  mov     rcx, rbx
0x14001431c  call    ?BeginElement@CXMLWriter@@QEAAJV?$basic_string_view@_WU?$char_traits@_W@utl@@@utl@@0_NV?$span@$$CBUCXMLAttribute@@$0?0@3@@Z; CXMLWriter::BeginElement(utl::basic_string_view<wchar_t,utl::char_traits<wchar_t>>,utl::basic_string_view<wchar_t,utl::char_traits<wchar_t>>,bool,utl::span<CXMLAttribute const,-1>)
0x140014321  mov     r8d, [rbp+220h+VersionInformation.dwBuildNumber]
0x140014328  lea     rcx, [rsp+320h+var_2B0]
0x14001432d  cmp     [rbp+220h+VersionInformation.szCSDVersion], r12w
0x140014335  jz      short loc_14001434C
0x140014337  lea     r9, [rbp+220h+VersionInformation.szCSDVersion]
0x14001433e  lea     rdx, aULs; "%u %ls"
0x140014345  call    ??$assign_sprintf@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@tlx@@YAJAEAV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@PEB_WZZ; tlx::assign_sprintf<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> &,wchar_t const *,...)
0x14001434a  jmp     short loc_140014354
0x14001434c  mov     rdx, r13
0x14001434f  call    ??$assign_sprintf@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@tlx@@YAJAEAV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@PEB_WZZ; tlx::assign_sprintf<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> &,wchar_t const *,...)
0x140014354  xorps   xmm0, xmm0
0x140014357  movdqa  [rsp+320h+var_2C0], xmm0
0x14001435d  mov     rax, [rsp+320h+var_2B0]
0x140014362  mov     qword ptr [rsp+320h+var_2E0], rax
0x140014367  mov     rcx, [rsp+320h+var_2A8]
0x14001436c  sub     rcx, rax
0x14001436f  sar     rcx, 1
0x140014372  mov     qword ptr [rsp+320h+var_2E0+8], rcx
0x140014377  lea     rax, aBuild; "Build"
0x14001437e  mov     qword ptr [rsp+320h+var_2D0], rax
0x140014383  mov     r14d, 5
0x140014389  mov     qword ptr [rsp+320h+var_2D0+8], r14
0x14001438e  lea     rax, [rsp+320h+var_2C0]
0x140014393  mov     [rsp+320h+pdwReturnedProductType], rax
0x140014398  mov     r9b, 1
0x14001439b  lea     r8, [rsp+320h+var_2E0]
0x1400143a0  lea     rdx, [rsp+320h+var_2D0]
0x1400143a5  mov     rcx, rbx
0x1400143a8  call    ?BeginElement@CXMLWriter@@QEAAJV?$basic_string_view@_WU?$char_traits@_W@utl@@@utl@@0_NV?$span@$$CBUCXMLAttribute@@$0?0@3@@Z; CXMLWriter::BeginElement(utl::basic_string_view<wchar_t,utl::char_traits<wchar_t>>,utl::basic_string_view<wchar_t,utl::char_traits<wchar_t>>,bool,utl::span<CXMLAttribute const,-1>)
0x1400143ad  mov     r9, [rbp+220h+var_208]
0x1400143b1  mov     r8d, [rbp+220h+var_290]
0x1400143b5  lea     rdx, a0xXLs; "(0x%x): %ls"
0x1400143bc  lea     rcx, [rsp+320h+var_2B0]
0x1400143c1  call    ??$assign_sprintf@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@tlx@@YAJAEAV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@PEB_WZZ; tlx::assign_sprintf<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> &,wchar_t const *,...)
0x1400143c6  xorps   xmm0, xmm0
0x1400143c9  movdqa  [rsp+320h+var_2C0], xmm0
0x1400143cf  mov     rax, [rsp+320h+var_2B0]
0x1400143d4  mov     qword ptr [rsp+320h+var_2E0], rax
0x1400143d9  mov     rcx, [rsp+320h+var_2A8]
0x1400143de  sub     rcx, rax
0x1400143e1  sar     rcx, 1
0x1400143e4  mov     qword ptr [rsp+320h+var_2E0+8], rcx
0x1400143e9  lea     rax, aProduct; "Product"
0x1400143f0  mov     qword ptr [rsp+320h+var_2D0], rax
0x1400143f5  lea     edi, [r14+2]
0x1400143f9  mov     qword ptr [rsp+320h+var_2D0+8], rdi
0x1400143fe  lea     rax, [rsp+320h+var_2C0]
0x140014403  mov     [rsp+320h+pdwReturnedProductType], rax
0x140014408  mov     r9b, 1
0x14001440b  lea     r8, [rsp+320h+var_2E0]
0x140014410  lea     rdx, [rsp+320h+var_2D0]
0x140014415  mov     rcx, rbx
0x140014418  call    ?BeginElement@CXMLWriter@@QEAAJV?$basic_string_view@_WU?$char_traits@_W@utl@@@utl@@0_NV?$span@$$CBUCXMLAttribute@@$0?0@3@@Z; CXMLWriter::BeginElement(utl::basic_string_view<wchar_t,utl::char_traits<wchar_t>>,utl::basic_string_view<wchar_t,utl::char_traits<wchar_t>>,bool,utl::span<CXMLAttribute const,-1>)
0x14001441d  xorps   xmm0, xmm0
0x140014420  movdqa  [rsp+320h+var_2C0], xmm0
0x140014426  mov     rax, [rbp+220h+var_228]
  ... truncated ...
```
