# CDeviceInfo::PopulateEditionInformation(DeviceContext *)

- ea: `0x18008c588`
- end: `0x18008d4b4`
- name: `?PopulateEditionInformation@CDeviceInfo@@QEAAJPEAVDeviceContext@@@Z`
- size: `3884`
- prototype: `__int64 __fastcall(CDeviceInfo *__hidden this, struct DeviceContext *)`
- caller_count: `1`
- callee_count: `28`
- tags: `file_ops, installer_update, broker_com_uri`

## callers

- `0x18008bb10`

## callees

- `0x1800031d0`
- `0x180003c28`
- `0x180003c64`
- `0x1800062b8`
- `0x180007f68`
- `0x180008b78`
- `0x180009750`
- `0x18000ba40`
- `0x18000f614`
- `0x18000f874`
- `0x18001b9e4`
- `0x1800296a4`
- `0x180036228`
- `0x18003cd78`
- `0x18003d278`
- `0x18003d670`
- `0x18003ddc8`
- `0x180051984`
- `0x1800670fc`
- `0x1800745d0`
- `0x1800751c0`
- `0x180076104`
- `0x180085620`
- `0x18008716c`
- `0x180088a24`
- `0x18008c588`
- `0x180112454`
- `0x1801126e4`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!wcsrchr` at `0x18008d234`
- `api-ms-win-crt-private-l1-1-0!wcsrchr` at `0x18008d234`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18008cdc2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18008cdc2`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18008ca0f`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18008cad2`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18008cbf9`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18008ca0f`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18008cad2`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18008cbf9`
- `api-ms-win-core-localization-l1-2-2!LCIDToLocaleName` at `0x18008cdae`
- `api-ms-win-core-localization-l1-2-2!LCIDToLocaleName` at `0x18008cdae`

## string_xrefs

- `0x18008c81a`: `Failed reading edition id`
- `0x18008c8e7`: `InstallationType`
- `0x18008c930`: `Failed reading InstallationType`
- `0x18008cb3b`: `Installation Type set to WinPE`
- `0x18008cae7`: `Failed getting installed Edition info. Reusing OS version instead`
- `0x18008cc4f`: `Failed reading system language`
- `0x18008cc1d`: `InstallLanguage`
- `0x18008d131`: `Failed reading BaseBuildRevisionNumber`

## pseudocode

```c
// Hidden C++ exception states: #wind=20
__int64 __fastcall CDeviceInfo::PopulateEditionInformation(CDeviceInfo *this, struct DeviceContext *a2)
{
  wchar_t *v4; // rdi
  wchar_t *v5; // rax
  HMODULE v6; // r9
  int v7; // eax
  unsigned int v8; // ebx
  __int64 v9; // rdx
  int RegValue; // eax
  __int64 v11; // rdx
  int EditionInfo; // r12d
  const WCHAR *v13; // rbx
  __int64 v14; // rdx
  __int64 v15; // rdx
  int v16; // eax
  __int64 v17; // rdx
  __int64 v18; // rdx
  int v19; // eax
  unsigned int v20; // edi
  __int64 v21; // rdx
  __int64 v22; // rdx
  LCID v23; // r12d
  signed int LastError; // r15d
  __int64 v25; // rdx
  unsigned int v26; // eax
  int v27; // esi
  int v28; // eax
  __int64 v29; // rdx
  __int64 v30; // rdx
  int v31; // eax
  __int64 v32; // rcx
  __int64 *v33; // rax
  __int64 v34; // rdx
  __int64 v35; // rdx
  int v36; // eax
  __int64 v37; // rdx
  int v38; // eax
  int v39; // eax
  wchar_t *v40; // rax
  const wchar_t *v41; // rsi
  int v42; // eax
  int v43; // r14d
  wchar_t *v44; // r14
  wchar_t *v45; // rsi
  wchar_t *v46; // rsi
  const wchar_t **bIgnoreCase; // [rsp+28h] [rbp-E0h]
  LPCWCH *bIgnoreCasea; // [rsp+28h] [rbp-E0h]
  wchar_t **bIgnoreCaseb; // [rsp+28h] [rbp-E0h]
  int v51; // [rsp+30h] [rbp-D8h]
  const wchar_t *v52; // [rsp+38h] [rbp-D0h] BYREF
  wchar_t *v53[2]; // [rsp+40h] [rbp-C8h] BYREF
  __int128 v54; // [rsp+50h] [rbp-B8h]
  wchar_t *Str; // [rsp+60h] [rbp-A8h] BYREF
  wchar_t *String; // [rsp+68h] [rbp-A0h] BYREF
  LPCWCH lpString1[3]; // [rsp+70h] [rbp-98h] BYREF
  wchar_t *v58; // [rsp+88h] [rbp-80h] BYREF
  __int64 v59; // [rsp+90h] [rbp-78h] BYREF
  __int64 v60; // [rsp+98h] [rbp-70h] BYREF
  wchar_t *v61; // [rsp+A0h] [rbp-68h] BYREF
  unsigned int v62; // [rsp+A8h] [rbp-60h] BYREF
  int v63[2]; // [rsp+B0h] [rbp-58h] BYREF
  int v64; // [rsp+B8h] [rbp-50h] BYREF
  __int128 v65; // [rsp+C0h] [rbp-48h]
  __int128 v66; // [rsp+D0h] [rbp-38h]
  __int16 v67; // [rsp+E0h] [rbp-28h]
  WCHAR Name[88]; // [rsp+E8h] [rbp-20h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+1E0h] [rbp+D8h]

  lpString1[1] = (LPCWCH)-2LL;
  v64 = 0;
  v65 = 0;
  v66 = 0;
  v67 = 0;
  v61 = 0;
  v59 = 0;
  v60 = 0;
  lpString1[0] = 0;
  lpString1[2] = 0;
  v4 = 0;
  String = 0;
  memset_0(Name, 0, 0xAAu);
  Str = 0;
  v58 = 0;
  v63[0] = 0;
  *(_OWORD *)v53 = 0;
  v54 = 0;
  std::wstring::_Construct<1,wchar_t const *>(v53);
  CDeviceInfo::AddValuePair(this, v53, 0);
  std::wstring::~wstring(v53);
  *(_OWORD *)v53 = 0;
  v54 = 0;
  std::wstring::_Construct<1,wchar_t const *>(v53);
  CDeviceInfo::AddValuePair(this, v53, 0);
  std::wstring::~wstring(v53);
  *(_OWORD *)v53 = 0;
  v54 = 0;
  std::wstring::_Construct<1,wchar_t const *>(v53);
  CDeviceInfo::AddValuePair(this, v53, 0);
  std::wstring::~wstring(v53);
  *(_OWORD *)v53 = 0;
  v54 = 0;
  std::wstring::_Construct<1,wchar_t const *>(v53);
  CDeviceInfo::AddValuePair(this, v53, 0);
  std::wstring::~wstring(v53);
  LogAdapter::TraceInfo<>("arbiter: Determining media feature name");
  if ( !*(_BYTE *)a2 )
  {
    v5 = 0;
    goto LABEL_6;
  }
  v5 = (wchar_t *)*((_QWORD *)a2 + 5);
  if ( !*((_QWORD *)a2 + 3) )
  {
LABEL_6:
    v6 = 0;
    goto LABEL_7;
  }
  v6 = (HMODULE)((char *)a2 + 8);
  if ( *((_QWORD *)a2 + 4) > 7u )
    v6 = *(HMODULE *)v6;
LABEL_7:
  v7 = CArbiterCbsClient::Initialize((__int64)&v64, 0, *((_DWORD *)a2 + 1), v6, 0, v5);
  v8 = v7;
  if ( v7 < 0 )
  {
    v63[0] = v7;
    if ( *(_QWORD *)&LogAdapter::g_Logger )
    {
      LogAdapter::Logger::LogNumObjects<>(*(_QWORD *)&LogAdapter::g_Logger, 0, 3, "Failed initializing cbs client");
      v52 = (const wchar_t *)v63;
      bIgnoreCase = &v52;
      LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
        *(_QWORD *)&LogAdapter::g_Logger,
        1,
        3,
        ": {}");
    }
    v9 = 3798;
LABEL_15:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v9,
      (unsigned int)"onecore\\base\\servicing\\arbiter\\cdeviceinfo.cpp",
      (const char *)v8,
      (int)bIgnoreCase);
    if ( v58 )
    {
      operator delete(v58 - 4);
      v58 = 0;
    }
    if ( v60 )
    {
      operator delete((void *)(v60 - 8));
      v60 = 0;
    }
    if ( v59 )
    {
      operator delete((void *)(v59 - 8));
      v59 = 0;
    }
    if ( v61 )
    {
      operator delete(v61 - 4);
      v61 = 0;
    }
    goto LABEL_164;
  }
  bIgnoreCase = (const wchar_t **)&v59;
  RegValue = DeviceContext::GetRegValue(a2, 0, L"Microsoft\\Windows NT\\CurrentVersion", L"EditionID");
  v8 = RegValue;
  if ( RegValue < 0 )
  {
    v63[0] = RegValue;
    if ( *(_QWORD *)&LogAdapter::g_Logger )
    {
      LogAdapter::Logger::LogNumObjects<>(*(_QWORD *)&LogAdapter::g_Logger, 0, 3, "Failed reading edition id");
      v52 = (const wchar_t *)v63;
      bIgnoreCase = &v52;
      LOBYTE(v11) = 1;
      LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
        *(_QWORD *)&LogAdapter::g_Logger,
        v11,
        3,
        ": {}");
    }
    v9 = 3809;
    goto LABEL_15;
  }
  bIgnoreCasea = lpString1;
  EditionInfo = DeviceContext::GetRegValue(a2, 0, L"Microsoft\\Windows NT\\CurrentVersion", L"InstallationType");
  v13 = lpString1[0];
  if ( EditionInfo != -805306316 )
  {
    if ( EditionInfo < 0 )
    {
      v63[0] = EditionInfo;
      if ( *(_QWORD *)&LogAdapter::g_Logger )
      {
        LogAdapter::Logger::LogNumObjects<>(*(_QWORD *)&LogAdapter::g_Logger, 0, 3, "Failed reading InstallationType");
        v52 = (const wchar_t *)v63;
        bIgnoreCasea = &v52;
        LOBYTE(v14) = 1;
        LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
          *(_QWORD *)&LogAdapter::g_Logger,
          v14,
          3,
          ": {}");
      }
      v15 = 3829;
      goto LABEL_28;
    }
    if ( CompareStringOrdinal(lpString1[0], -1, L"Server Core", -1, 1) == 2 )
    {
      v16 = SczAllocConcatSz(&v59, L"Core");
      EditionInfo = v16;
      if ( v16 < 0 )
      {
        v63[0] = v16;
        if ( *(_QWORD *)&LogAdapter::g_Logger )
        {
          LogAdapter::Logger::LogNumObjects<>(
            *(_QWORD *)&LogAdapter::g_Logger,
            0,
            3,
            "Failed forming edition core feature name");
          v52 = (const wchar_t *)v63;
          bIgnoreCasea = &v52;
          LOBYTE(v17) = 1;
          LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
            *(_QWORD *)&LogAdapter::g_Logger,
            v17,
            3,
            ": {}");
        }
        v15 = 3833;
        goto LABEL_28;
      }
    }
  }
  EditionInfo = CArbiterCbsClient::GetEditionInfo((CArbiterCbsClient *)&v64, a2, *((_BYTE *)this + 328), &v61, &v58);
  if ( EditionInfo < 0 )
  {
    if ( CompareStringOrdinal(v13, -1, L"WindowsPE", -1, 1) != 2 )
    {
      v63[0] = EditionInfo;
      if ( *(_QWORD *)&LogAdapter::g_Logger )
      {
        LogAdapter::Logger::LogNumObjects<>(*(_QWORD *)&LogAdapter::g_Logger, 0, 3, "Failed getting Edition info");
        v52 = (const wchar_t *)v63;
        bIgnoreCasea = &v52;
        LOBYTE(v22) = 1;
        LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
          *(_QWORD *)&LogAdapter::g_Logger,
          v22,
          3,
          ": {}");
      }
      v15 = 3864;
      goto LABEL_28;
    }
    LogAdapter::TraceInfo<>("Failed getting installed Edition info. Reusing OS version instead");
    *(_OWORD *)v53 = 0;
    v54 = 0;
    std::wstring::_Construct<1,wchar_t const *>(v53);
    CDeviceInfo::AddValuePair(this, v53, L"1");
    std::wstring::~wstring(v53);
    LogAdapter::TraceInfo<>("Installation Type set to WinPE");
    v52 = 0;
    EditionInfo = CDeviceInfo::GetNameValuePairValue(this, L"OSVersion", &v52, 1);
    if ( EditionInfo < 0 )
    {
      v15 = 3854;
      goto LABEL_28;
    }
    EditionInfo = SczAllocFromSz(&v58);
    if ( EditionInfo < 0 )
    {
      v15 = 3855;
LABEL_28:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v15,
        (unsigned int)"onecore\\base\\servicing\\arbiter\\cdeviceinfo.cpp",
        (const char *)(unsigned int)EditionInfo,
        (int)bIgnoreCasea);
      if ( v58 )
      {
        operator delete(v58 - 4);
        v58 = 0;
      }
LABEL_30:
      if ( v13 )
        operator delete((void *)(v13 - 4));
      if ( v60 )
      {
        operator delete((void *)(v60 - 8));
        v60 = 0;
      }
      if ( v59 )
      {
        operator delete((void *)(v59 - 8));
        v59 = 0;
      }
      if ( v61 )
      {
        operator delete(v61 - 4);
        v61 = 0;
      }
      v8 = EditionInfo;
      goto LABEL_164;
    }
    *(_OWORD *)v53 = 0;
    v54 = 0;
    std::wstring::_Construct<1,wchar_t const *>(v53);
    CDeviceInfo::AddValuePair(this, v53, L"1");
    std::wstring::~wstring(v53);
    *((_BYTE *)this + 236) = 1;
  }
  if ( CompareStringOrdinal(v13, -1, L"WindowsPE", -1, 1) != 2 )
  {
    LOBYTE(v51) = 1;
    bIgnoreCaseb = &String;
    v19 = DeviceContext::GetRegValue(a2, 1, L"CurrentControlSet\\Control\\nls\\language", L"InstallLanguage");
    v20 = v19;
    if ( v19 < 0 )
    {
      v63[0] = v19;
      if ( *(_QWORD *)&LogAdapter::g_Logger )
      {
        LogAdapter::Logger::LogNumObjects<>(*(_QWORD *)&LogAdapter::g_Logger, 0, 3, "Failed reading system language");
        v52 = (const wchar_t *)v63;
        bIgnoreCaseb = (wchar_t **)&v52;
        LOBYTE(v21) = 1;
        LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
          *(_QWORD *)&LogAdapter::g_Logger,
          v21,
          3,
          ": {}");
      }
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xF28,
        (unsigned int)"onecore\\base\\servicing\\arbiter\\cdeviceinfo.cpp",
        (const char *)v20,
        (int)bIgnoreCaseb);
      if ( v58 )
      {
        operator delete(v58 - 4);
        v58 = 0;
      }
      if ( String )
        operator delete(String - 4);
      if ( v13 )
        operator delete((void *)(v13 - 4));
      if ( v60 )
      {
        operator delete((void *)(v60 - 8));
        v60 = 0;
      }
      if ( v59 )
      {
        operator delete((void *)(v59 - 8));
        v59 = 0;
      }
      if ( v61 )
      {
        operator delete(v61 - 4);
        v61 = 0;
      }
      v8 = v20;
      goto LABEL_164;
    }
    v4 = String;
    v23 = o_wcstoul_0(String, 0, 16);
    if ( !LCIDToLocaleName(v23, Name, 85, 0) )
    {
      LastError = GetLastError();
      if ( *(_QWORD *)&LogAdapter::g_Logger )
      {
        v63[0] = v23;
        LogAdapter::Logger::LogNumObjects<unsigned long>(
          *(_QWORD *)&LogAdapter::g_Logger,
          0,
          3,
          "Failed converting language ID to locale name: {0}",
          v63,
          v51);
        if ( LastError > 0 )
          v26 = (unsigned __int16)LastError | 0x80070000;
        else
          v26 = LastError;
        v62 = v26;
        v52 = (const wchar_t *)&v62;
        bIgnoreCaseb = (wchar_t **)&v52;
        LOBYTE(v25) = 1;
        LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
          *(_QWORD *)&LogAdapter::g_Logger,
          v25,
          3,
          ": {0}");
      }
      if ( LastError )
      {
        v27 = wil::details::in1diag3::Return_Win32(
                retaddr,
                (void *)0xF2E,
                (unsigned int)"onecore\\base\\servicing\\arbiter\\cdeviceinfo.cpp",
                (const char *)(unsigned int)LastError,
                (unsigned int)bIgnoreCaseb);
LABEL_79:
        if ( v58 )
        {
          operator delete(v58 - 4);
          v58 = 0;
        }
        if ( v4 )
          operator delete(v4 - 4);
        if ( v13 )
          operator delete((void *)(v13 - 4));
        if ( v60 )
        {
          operator delete((void *)(v60 - 8));
          v60 = 0;
        }
        if ( v59 )
        {
          operator delete((void *)(v59 - 8));
          v59 = 0;
        }
        if ( v61 )
        {
          operator delete(v61 - 4);
          v61 = 0;
        }
        v8 = v27;
        goto LABEL_164;
      }
      goto LABEL_151;
    }
    v28 = SczAllocConcat2Sz(&v59, L"_", Name);
    EditionInfo = v28;
    if ( v28 < 0 )
    {
      v62 = v28;
      if ( *(_QWORD *)&LogAdapter::g_Logger )
      {
        LogAdapter::Logger::LogNumObjects<>(
          *(_QWORD *)&LogAdapter::g_Logger,
          0,
          3,
          "Failed forming edition feature name");
        v52 = (const wchar_t *)&v62;
        bIgnoreCaseb = (wchar_t **)&v52;
        LOBYTE(v29) = 1;
        LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
          *(_QWORD *)&LogAdapter::g_Logger,
          v29,
          3,
          ": {}");
      }
      v30 = 3888;
      goto LABEL_96;
    }
    EditionInfo = SczAllocFromSz(&v60);
    if ( EditionInfo < 0 )
    {
      v30 = 3890;
LABEL_96:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v30,
        (unsigned int)"onecore\\base\\servicing\\arbiter\\cdeviceinfo.cpp",
        (const char *)(unsigned int)EditionInfo,
        (int)bIgnoreCaseb);
LABEL_97:
      if ( v58 )
      {
        operator delete(v58 - 4);
        v58 = 0;
      }
      if ( v4 )
        operator delete(v4 - 4);
      goto LABEL_30;
    }
    EditionInfo = SczAllocConcat2Sz(&v60, L"_", Name);
    if ( EditionInfo < 0 )
    {
      v30 = 3891;
      goto LABEL_96;
    }
  }
  LOBYTE(v18) = 2;
  v31 = CDeviceInfo::AddInstalledFeature(this, v18, v59, 0);
  EditionInfo = v31;
  if ( v31 < 0 )
  {
    v62 = v31;
    v32 = *(_QWORD *)&LogAdapter::g_Logger;
    if ( !*(_QWORD *)&LogAdapter::g_Logger )
      goto LABEL_97;
    v33 = &v59;
LABEL_108:
    LogAdapter::Logger::LogNumObjects<AutoScz>(v32, 0, 3, "Failed adding feature: {0}", v33);
    v52 = (const wchar_t *)&v62;
    LOBYTE(v34) = 1;
    LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
      *(_QWORD *)&LogAdapter::g_Logger,
      v34,
      3,
      ": {}");
    goto LABEL_97;
  }
  LogAdapter::TraceInfo<AutoScz>("Device: Edition version: {0}", &v58);
  if ( v60 )
  {
    LOBYTE(v35) = 27;
    v36 = CDeviceInfo::AddInstalledFeature(this, v35, v60, 0);
    EditionInfo = v36;
    if ( v36 < 0 )
    {
      v62 = v36;
      v32 = *(_QWORD *)&LogAdapter::g_Logger;
      if ( !*(_QWORD *)&LogAdapter::g_Logger )
        goto LABEL_97;
      v33 = &v60;
      goto LABEL_108;
    }
  }
  EditionInfo = DeviceContext::GetRegValue(a2, 0, L"Microsoft\\Windows NT\\CurrentVersion", L"BaseBuildRevisionNumber");
  if ( EditionInfo == -805306316 )
  {
    LogAdapter::TraceInfo<>("No BaseBuildRevisionNumber found, will continue without it");
LABEL_150:
    v45 = v58;
    std::wstring::wstring(v53, L"EditionVersion");
    CDeviceInfo::AddValuePair(this, v53, v45);
    std::wstring::~wstring(v53);
    v46 = v61;
    std::wstring::wstring(v53, L"CBSEdition");
    CDeviceInfo::AddValuePair(this, v53, v46);
    std::wstring::~wstring(v53);
    std::wstring::wstring(v53, L"SystemLanguage");
    CDeviceInfo::AddValuePair(this, v53, Name);
    std::wstring::~wstring(v53);
LABEL_151:
    if ( v58 )
    {
      operator delete(v58 - 4);
      v58 = 0;
    }
    if ( v4 )
      operator delete(v4 - 4);
    if ( v13 )
      operator delete((void *)(v13 - 4));
    if ( v60 )
    {
      operator delete((void *)(v60 - 8));
      v60 = 0;
    }
    if ( v59 )
    {
      operator delete((void *)(v59 - 8));
      v59 = 0;
    }
    if ( v61 )
    {
      operator delete(v61 - 4);
      v61 = 0;
    }
    v8 = 0;
    goto LABEL_164;
  }
  v52 = 0;
  Str = 0;
  if ( EditionInfo < 0 )
  {
    v62 = EditionInfo;
    if ( *(_QWORD *)&LogAdapter::g_Logger )
    {
      LogAdapter::Logger::LogNumObjects<>(
        *(_QWORD *)&LogAdapter::g_Logger,
        0,
        3,
        "Failed reading BaseBuildRevisionNumber");
      *(_QWORD *)v63 = &v62;
      LOBYTE(v37) = 1;
      LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
        *(_QWORD *)&LogAdapter::g_Logger,
        v37,
        3,
        ": {}");
    }
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xF61,
      (unsigned int)"onecore\\base\\servicing\\arbiter\\cdeviceinfo.cpp",
      (const char *)(unsigned int)EditionInfo,
      (int)v63);
    goto LABEL_97;
  }
  v38 = SczAllocFormatted(&v52, L"%lu", (unsigned int)v63[0]);
  v27 = v38;
  if ( v38 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xF63,
      (unsigned int)"onecore\\base\\servicing\\arbiter\\cdeviceinfo.cpp",
      (const char *)(unsigned int)v38,
      (int)v63);
LABEL_121:
    if ( v52 )
      operator delete((void *)(v52 - 4));
    goto LABEL_79;
  }
  v39 = SczAllocFromSz(&Str);
  v27 = v39;
  if ( v39 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xF64,
      (unsigned int)"onecore\\base\\servicing\\arbiter\\cdeviceinfo.cpp",
      (const char *)(unsigned int)v39,
      (int)v63);
    if ( Str )
      operator delete(Str - 4);
    goto LABEL_121;
  }
  v40 = wcsrchr(Str, 0x2Eu);
  if ( v40 )
    v40[1] = 0;
  v41 = v52;
  v42 = SczAllocConcatSz(&Str, v52);
  v43 = v42;
  if ( v42 >= 0 )
  {
    v44 = Str;
    std::wstring::wstring(v53, L"OSBaseVersion");
    CDeviceInfo::AddValuePair(this, v53, v44);
    std::wstring::~wstring(v53);
    if ( v44 )
      operator delete(v44 - 4);
    if ( v41 )
      operator delete((void *)(v41 - 4));
    goto LABEL_150;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0xF6E,
    (unsigned int)"onecore\\base\\servicing\\arbiter\\cdeviceinfo.cpp",
    (const char *)(unsigned int)v42,
    (int)v63);
  if ( Str )
    operator delete(Str - 4);
  if ( v41 )
    operator delete((void *)(v41 - 4));
  if ( v58 )
  {
    operator delete(v58 - 4);
    v58 = 0;
  }
  if ( v4 )
    operator delete(v4 - 4);
  if ( v13 )
    operator delete((void *)(v13 - 4));
  if ( v60 )
  {
    operator delete((void *)(v60 - 8));
    v60 = 0;
  }
  if ( v59 )
  {
    operator delete((void *)(v59 - 8));
    v59 = 0;
  }
  if ( v61 )
  {
    operator delete(v61 - 4);
    v61 = 0;
  }
  v8 = v43;
LABEL_164:
  CArbiterCbsClient::~CArbiterCbsClient((CArbiterCbsClient *)&v64);
  return v8;
}

```

## disassembly

```asm
0x18008c588  mov     rax, rsp
0x18008c58b  push    rbp
0x18008c58c  push    rsi
0x18008c58d  push    rdi
0x18008c58e  push    r12
0x18008c590  push    r13
0x18008c592  push    r14
0x18008c594  push    r15
0x18008c596  lea     rbp, [rax-0D8h]
0x18008c59d  sub     rsp, 1A0h
0x18008c5a4  mov     [rsp+1D0h+var_160], 0FFFFFFFFFFFFFFFEh
0x18008c5ad  mov     [rax+18h], rbx
0x18008c5b1  mov     rax, cs:__security_cookie
0x18008c5b8  xor     rax, rsp
0x18008c5bb  mov     [rbp+0D0h+var_40], rax
0x18008c5c2  mov     rsi, rdx
0x18008c5c5  mov     r15, rcx
0x18008c5c8  xor     r13d, r13d
0x18008c5cb  mov     [rbp+0D0h+var_120], r13d
0x18008c5cf  xorps   xmm0, xmm0
0x18008c5d2  movdqu  [rbp+0D0h+var_118], xmm0
0x18008c5d7  xorps   xmm1, xmm1
0x18008c5da  movdqu  [rbp+0D0h+var_108], xmm1
0x18008c5df  mov     [rbp+0D0h+var_F8], r13w
0x18008c5e4  mov     [rbp+0D0h+var_138], r13
0x18008c5e8  mov     [rbp+0D0h+var_148], r13
0x18008c5ec  mov     [rbp+0D0h+var_140], r13
0x18008c5f0  mov     [rsp+1D0h+lpString1], r13
0x18008c5f5  mov     [rsp+78h], r13
0x18008c5fa  mov     edi, r13d
0x18008c5fd  mov     [rsp+1D0h+String], r13
0x18008c602  xor     edx, edx; Val
0x18008c604  mov     r8d, 0AAh; Size
0x18008c60a  lea     rcx, [rbp+0D0h+Name]; void *
0x18008c60e  call    memset_0
0x18008c613  mov     [rsp+1D0h+Str], r13
0x18008c618  mov     [rbp+0D0h+var_150], r13
0x18008c61c  mov     [rbp+0D0h+var_128], r13d
0x18008c620  xorps   xmm0, xmm0
0x18008c623  movups  xmmword ptr [rsp+1D0h+var_1A0+8], xmm0
0x18008c628  xorps   xmm1, xmm1
0x18008c62b  movdqu  [rsp+1D0h+var_190+8], xmm1
0x18008c631  lea     r8d, [r13+0Dh]
0x18008c635  lea     rdx, aOsbaseversion; "OSBaseVersion"
0x18008c63c  lea     rcx, [rsp+1D0h+var_1A0+8]
0x18008c641  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x18008c646  nop
0x18008c647  xor     r8d, r8d
0x18008c64a  lea     rdx, [rsp+1D0h+var_1A0+8]
0x18008c64f  mov     rcx, r15
0x18008c652  call    ?AddValuePair@CDeviceInfo@@QEAAX$$QEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEB_W@Z; CDeviceInfo::AddValuePair(std::wstring &&,wchar_t const * const)
0x18008c657  nop
0x18008c658  lea     rcx, [rsp+1D0h+var_1A0+8]; void *
0x18008c65d  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18008c662  xorps   xmm0, xmm0
0x18008c665  movups  xmmword ptr [rsp+1D0h+var_1A0+8], xmm0
0x18008c66a  xorps   xmm1, xmm1
0x18008c66d  movdqu  [rsp+1D0h+var_190+8], xmm1
0x18008c673  lea     ebx, [r13+0Eh]
0x18008c677  mov     r8d, ebx
0x18008c67a  lea     rdx, aEditionversion; "EditionVersion"
0x18008c681  lea     rcx, [rsp+1D0h+var_1A0+8]
0x18008c686  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x18008c68b  nop
0x18008c68c  xor     r8d, r8d
0x18008c68f  lea     rdx, [rsp+1D0h+var_1A0+8]
0x18008c694  mov     rcx, r15
0x18008c697  call    ?AddValuePair@CDeviceInfo@@QEAAX$$QEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEB_W@Z; CDeviceInfo::AddValuePair(std::wstring &&,wchar_t const * const)
0x18008c69c  nop
0x18008c69d  lea     rcx, [rsp+1D0h+var_1A0+8]; void *
0x18008c6a2  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18008c6a7  xorps   xmm0, xmm0
0x18008c6aa  movups  xmmword ptr [rsp+1D0h+var_1A0+8], xmm0
0x18008c6af  xorps   xmm1, xmm1
0x18008c6b2  movdqu  [rsp+1D0h+var_190+8], xmm1
0x18008c6b8  lea     r8d, [r13+0Ah]
0x18008c6bc  lea     rdx, aCbsedition; "CBSEdition"
0x18008c6c3  lea     rcx, [rsp+1D0h+var_1A0+8]
0x18008c6c8  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x18008c6cd  nop
0x18008c6ce  xor     r8d, r8d
0x18008c6d1  lea     rdx, [rsp+1D0h+var_1A0+8]
0x18008c6d6  mov     rcx, r15
0x18008c6d9  call    ?AddValuePair@CDeviceInfo@@QEAAX$$QEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEB_W@Z; CDeviceInfo::AddValuePair(std::wstring &&,wchar_t const * const)
0x18008c6de  nop
0x18008c6df  lea     rcx, [rsp+1D0h+var_1A0+8]; void *
0x18008c6e4  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18008c6e9  xorps   xmm0, xmm0
0x18008c6ec  movups  xmmword ptr [rsp+1D0h+var_1A0+8], xmm0
0x18008c6f1  xorps   xmm1, xmm1
0x18008c6f4  movdqu  [rsp+1D0h+var_190+8], xmm1
0x18008c6fa  mov     r8d, ebx
0x18008c6fd  lea     rdx, aSystemlanguage; "SystemLanguage"
0x18008c704  lea     rcx, [rsp+1D0h+var_1A0+8]
0x18008c709  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x18008c70e  nop
0x18008c70f  xor     r8d, r8d
0x18008c712  lea     rdx, [rsp+1D0h+var_1A0+8]
0x18008c717  mov     rcx, r15
0x18008c71a  call    ?AddValuePair@CDeviceInfo@@QEAAX$$QEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEB_W@Z; CDeviceInfo::AddValuePair(std::wstring &&,wchar_t const * const)
0x18008c71f  nop
0x18008c720  lea     rcx, [rsp+1D0h+var_1A0+8]; void *
0x18008c725  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18008c72a  lea     rcx, aArbiterDetermi_0; "arbiter: Determining media feature name"
0x18008c731  call    ??$TraceInfo@$$V@LogAdapter@@YAXQEBD@Z; LogAdapter::TraceInfo<>(char const * const)
0x18008c736  cmp     [rsi], r13b
0x18008c739  jz      short loc_18008C755
0x18008c73b  mov     rax, [rsi+28h]
0x18008c73f  cmp     [rsi+18h], r13
0x18008c743  jz      short loc_18008C758
0x18008c745  lea     r9, [rsi+8]
0x18008c749  cmp     qword ptr [r9+18h], 7
0x18008c74e  jbe     short loc_18008C75B
0x18008c750  mov     r9, [r9]
0x18008c753  jmp     short loc_18008C75B
0x18008c755  mov     rax, r13
0x18008c758  mov     r9, r13
0x18008c75b  mov     [rsp+1D0h+var_1A8], rax
0x18008c760  mov     qword ptr [rsp+1D0h+bIgnoreCase], r13
0x18008c765  mov     r8d, [rsi+4]
0x18008c769  xor     edx, edx
0x18008c76b  lea     rcx, [rbp+0D0h+var_120]
0x18008c76f  call    ?Initialize@CArbiterCbsClient@@QEAAJW4InitializeFlags@1@W4DeviceType@@QEB_W22@Z; CArbiterCbsClient::Initialize(CArbiterCbsClient::InitializeFlags,DeviceType,wchar_t const * const,wchar_t const * const,wchar_t const * const)
0x18008c774  mov     ebx, eax
0x18008c776  test    eax, eax
0x18008c778  jns     short loc_18008C7D5
0x18008c77a  mov     [rbp+0D0h+var_128], eax
0x18008c77d  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x18008c784  test    rcx, rcx
0x18008c787  jz      short loc_18008C7CB
0x18008c789  lea     r9, aFailedInitiali_2; "Failed initializing cbs client"
0x18008c790  mov     esi, 3
0x18008c795  mov     r8d, esi
0x18008c798  xor     edx, edx
0x18008c79a  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x18008c79f  lea     rax, [rbp+0D0h+var_128]
0x18008c7a3  mov     [rsp+1D0h+var_1A0], rax
0x18008c7a8  lea     rax, [rsp+1D0h+var_1A0]
0x18008c7ad  mov     qword ptr [rsp+1D0h+bIgnoreCase], rax
0x18008c7b2  lea     r9, asc_1801CAFB4; ": {}"
0x18008c7b9  mov     r8d, esi
0x18008c7bc  lea     edx, [rsi-2]
0x18008c7bf  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x18008c7c6  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x18008c7cb  mov     edx, 0ED6h
0x18008c7d0  jmp     loc_18008C860
0x18008c7d5  mov     r14d, 1
0x18008c7db  mov     byte ptr [rsp+1D0h+var_1A8], r14b
0x18008c7e0  lea     rax, [rbp+0D0h+var_148]
0x18008c7e4  mov     qword ptr [rsp+1D0h+bIgnoreCase], rax
0x18008c7e9  lea     r9, aEditionid; "EditionID"
0x18008c7f0  lea     r8, aMicrosoftWindo_8; "Microsoft\\Windows NT\\CurrentVersion"
0x18008c7f7  xor     edx, edx
0x18008c7f9  mov     rcx, rsi
0x18008c7fc  call    ?GetRegValue@DeviceContext@@QEBAJW4RegistryHive@1@PEB_W1PEAVAutoScz@@_N@Z; DeviceContext::GetRegValue(DeviceContext::RegistryHive,wchar_t const *,wchar_t const *,AutoScz *,bool)
0x18008c801  mov     ebx, eax
0x18008c803  test    eax, eax
0x18008c805  jns     loc_18008C8D8
0x18008c80b  mov     [rbp+0D0h+var_128], eax
0x18008c80e  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x18008c815  test    rcx, rcx
0x18008c818  jz      short loc_18008C85B
0x18008c81a  lea     r9, aFailedReadingE_0; "Failed reading edition id"
0x18008c821  lea     esi, [r14+2]
0x18008c825  mov     r8d, esi
0x18008c828  xor     edx, edx
0x18008c82a  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x18008c82f  lea     rax, [rbp+0D0h+var_128]
0x18008c833  mov     [rsp+1D0h+var_1A0], rax
0x18008c838  lea     rax, [rsp+1D0h+var_1A0]
0x18008c83d  mov     qword ptr [rsp+1D0h+bIgnoreCase], rax; int
0x18008c842  lea     r9, asc_1801CAFB4; ": {}"
0x18008c849  mov     r8d, esi
0x18008c84c  mov     dl, r14b
0x18008c84f  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x18008c856  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x18008c85b  mov     edx, 0EE1h; void *
0x18008c860  mov     r9d, ebx; char *
0x18008c863  lea     r8, aOnecoreBaseSer_8; "onecore\\base\\servicing\\arbiter\\cdev"...
0x18008c86a  mov     rcx, [rbp+0D8h]; this
0x18008c871  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18008c876  nop
0x18008c877  mov     rcx, [rbp+0D0h+var_150]
0x18008c87b  test    rcx, rcx
0x18008c87e  jz      short loc_18008C88D
0x18008c880  add     rcx, 0FFFFFFFFFFFFFFF8h; Block
0x18008c884  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18008c889  mov     [rbp+0D0h+var_150], r13
0x18008c88d  mov     rcx, [rbp+0D0h+var_140]
0x18008c891  test    rcx, rcx
0x18008c894  jz      short loc_18008C8A3
0x18008c896  add     rcx, 0FFFFFFFFFFFFFFF8h; Block
0x18008c89a  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18008c89f  mov     [rbp+0D0h+var_140], r13
0x18008c8a3  mov     rcx, [rbp+0D0h+var_148]
0x18008c8a7  test    rcx, rcx
0x18008c8aa  jz      short loc_18008C8B9
0x18008c8ac  add     rcx, 0FFFFFFFFFFFFFFF8h; Block
0x18008c8b0  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18008c8b5  mov     [rbp+0D0h+var_148], r13
0x18008c8b9  mov     rcx, [rbp+0D0h+var_138]
0x18008c8bd  test    rcx, rcx
0x18008c8c0  jz      loc_18008D47E
0x18008c8c6  add     rcx, 0FFFFFFFFFFFFFFF8h; Block
0x18008c8ca  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18008c8cf  mov     [rbp+0D0h+var_138], r13
0x18008c8d3  jmp     loc_18008D47E
0x18008c8d8  mov     byte ptr [rsp+1D0h+var_1A8], r13b
0x18008c8dd  lea     rax, [rsp+1D0h+lpString1]
0x18008c8e2  mov     qword ptr [rsp+1D0h+bIgnoreCase], rax
0x18008c8e7  lea     r9, aInstallationty; "InstallationType"
0x18008c8ee  lea     r8, aMicrosoftWindo_8; "Microsoft\\Windows NT\\CurrentVersion"
0x18008c8f5  xor     edx, edx
0x18008c8f7  mov     rcx, rsi
0x18008c8fa  call    ?GetRegValue@DeviceContext@@QEBAJW4RegistryHive@1@PEB_W1PEAVAutoScz@@_N@Z; DeviceContext::GetRegValue(DeviceContext::RegistryHive,wchar_t const *,wchar_t const *,AutoScz *,bool)
0x18008c8ff  mov     r12d, eax
0x18008c902  or      eax, 0FFFFFFFFh
0x18008c905  mov     rbx, [rsp+1D0h+lpString1]
0x18008c90a  cmp     r12d, 0D0000034h
0x18008c911  jz      loc_18008CA92
0x18008c917  test    r12d, r12d
0x18008c91a  jns     loc_18008C9FB
0x18008c920  mov     [rbp+0D0h+var_128], r12d
0x18008c924  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x18008c92b  test    rcx, rcx
0x18008c92e  jz      short loc_18008C970
0x18008c930  lea     r9, aFailedReadingI; "Failed reading InstallationType"
0x18008c937  lea     esi, [rax+4]
0x18008c93a  mov     r8d, esi
0x18008c93d  xor     edx, edx
0x18008c93f  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x18008c944  lea     rax, [rbp+0D0h+var_128]
0x18008c948  mov     [rsp+1D0h+var_1A0], rax
0x18008c94d  lea     rax, [rsp+1D0h+var_1A0]
0x18008c952  mov     qword ptr [rsp+1D0h+bIgnoreCase], rax; int
0x18008c957  lea     r9, asc_1801CAFB4; ": {}"
0x18008c95e  mov     r8d, esi
0x18008c961  mov     dl, r14b
0x18008c964  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x18008c96b  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x18008c970  mov     edx, 0EF5h; void *
0x18008c975  mov     r9d, r12d; char *
0x18008c978  lea     r8, aOnecoreBaseSer_8; "onecore\\base\\servicing\\arbiter\\cdev"...
0x18008c97f  mov     rcx, [rbp+0D8h]; this
0x18008c986  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18008c98b  nop
0x18008c98c  mov     rcx, [rbp+0D0h+var_150]
0x18008c990  test    rcx, rcx
0x18008c993  jz      short loc_18008C9A2
0x18008c995  add     rcx, 0FFFFFFFFFFFFFFF8h; Block
0x18008c999  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18008c99e  mov     [rbp+0D0h+var_150], r13
0x18008c9a2  test    rbx, rbx
0x18008c9a5  jz      short loc_18008C9B1
0x18008c9a7  lea     rcx, [rbx-8]; Block
0x18008c9ab  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18008c9b0  nop
0x18008c9b1  mov     rcx, [rbp+0D0h+var_140]
0x18008c9b5  test    rcx, rcx
0x18008c9b8  jz      short loc_18008C9C7
0x18008c9ba  add     rcx, 0FFFFFFFFFFFFFFF8h; Block
0x18008c9be  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18008c9c3  mov     [rbp+0D0h+var_140], r13
0x18008c9c7  mov     rcx, [rbp+0D0h+var_148]
0x18008c9cb  test    rcx, rcx
0x18008c9ce  jz      short loc_18008C9DD
0x18008c9d0  add     rcx, 0FFFFFFFFFFFFFFF8h; Block
0x18008c9d4  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18008c9d9  mov     [rbp+0D0h+var_148], r13
0x18008c9dd  mov     rcx, [rbp+0D0h+var_138]
0x18008c9e1  test    rcx, rcx
0x18008c9e4  jz      short loc_18008C9F3
0x18008c9e6  add     rcx, 0FFFFFFFFFFFFFFF8h; Block
0x18008c9ea  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18008c9ef  mov     [rbp+0D0h+var_138], r13
0x18008c9f3  mov     ebx, r12d
0x18008c9f6  jmp     loc_18008D47E
0x18008c9fb  mov     [rsp+1D0h+bIgnoreCase], r14d; bIgnoreCase
0x18008ca00  mov     r9d, eax; cchCount2
0x18008ca03  lea     r8, aServerCore; "Server Core"
0x18008ca0a  mov     edx, eax; cchCount1
0x18008ca0c  mov     rcx, rbx; lpString1
0x18008ca0f  call    cs:__imp_CompareStringOrdinal
0x18008ca16  nop     dword ptr [rax+rax+00h]
0x18008ca1b  cmp     eax, 2
0x18008ca1e  jnz     short loc_18008CA92
0x18008ca20  lea     rdx, aCore; "Core"
0x18008ca27  lea     rcx, [rbp+0D0h+var_148]
0x18008ca2b  call    SczAllocConcatSz
0x18008ca30  mov     r12d, eax
0x18008ca33  test    eax, eax
0x18008ca35  jns     short loc_18008CA92
0x18008ca37  mov     [rbp+0D0h+var_128], eax
0x18008ca3a  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x18008ca41  test    rcx, rcx
0x18008ca44  jz      short loc_18008CA88
0x18008ca46  lea     r9, aFailedFormingE; "Failed forming edition core feature nam"...
0x18008ca4d  mov     esi, 3
0x18008ca52  mov     r8d, esi
0x18008ca55  xor     edx, edx
  ... truncated ...
```
