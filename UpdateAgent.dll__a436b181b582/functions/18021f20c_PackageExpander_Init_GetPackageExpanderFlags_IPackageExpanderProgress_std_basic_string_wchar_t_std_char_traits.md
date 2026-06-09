# PackageExpander::Init(GetPackageExpanderFlags,IPackageExpanderProgress *,std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> const &,std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> const &,std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> const &,std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> const &,std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> const &,GetPackageExpanderDisposition *)

- ea: `0x18021f20c`
- end: `0x18021fcf2`
- name: `?Init@PackageExpander@@QEAAJW4GetPackageExpanderFlags@@PEAVIPackageExpanderProgress@@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@2222PEAW4GetPackageExpanderDisposition@@@Z`
- size: `2790`
- prototype: `__int64 __usercall@<rax>(PackageExpander *this@<rcx>, __int64, __int64, __int64, __int64, __int64)`
- caller_count: `1`
- callee_count: `14`
- tags: `reparse_path, loader_planting, installer_update, broker_com_uri`

## callers

- `0x180220c78`

## callees

- `0x1800059d0`
- `0x18000a7fc`
- `0x180012430`
- `0x18001270c`
- `0x180012b84`
- `0x180023b20`
- `0x1800692fc`
- `0x1801def30`
- `0x1801df624`
- `0x1801efdc0`
- `0x180217690`
- `0x18021ba2c`
- `0x18021f20c`
- `0x1802b1010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x18021f4be`
- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x18021f537`
- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x18021f5b1`
- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x18021f62a`
- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x18021f910`
- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x18021f4be`
- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x18021f537`
- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x18021f5b1`
- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x18021f62a`
- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x18021f910`
- `api-ms-win-core-libraryloader-l1-1-0!LoadLibraryExW` at `0x18021f3c5`
- `api-ms-win-core-libraryloader-l1-1-0!LoadLibraryExW` at `0x18021f412`
- `api-ms-win-core-libraryloader-l1-1-0!LoadLibraryExW` at `0x18021f8d0`
- `api-ms-win-core-libraryloader-l1-1-0!LoadLibraryExW` at `0x18021f3c5`
- `api-ms-win-core-libraryloader-l1-1-0!LoadLibraryExW` at `0x18021f412`
- `api-ms-win-core-libraryloader-l1-1-0!LoadLibraryExW` at `0x18021f8d0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18021f437`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18021f44e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18021f4d2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18021f4e9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18021f54c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18021f563`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18021f5c5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18021f5dc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18021f63f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18021f656`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18021f437`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18021f44e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18021f4d2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18021f4e9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18021f54c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18021f563`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18021f5c5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18021f5dc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18021f63f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18021f656`

## string_xrefs

- `0x18021f352`: `dpx.dll`
- `0x18021f3a0`: `Attempting to load DPX from {0}`
- `0x18021f3fe`: `Attempting to load DPX from system path`
- `0x18021f86e`: `turbostack.dll`
- `0x18021f8ab`: `Attempting to load TurboStack from {0}`
- `0x18021faf4`: `Failed to initialize the servicing hash provider with error {0}. DPX will compute the file hashes itself`
- `0x18021fb0b`: `Expander will ask DPX to compute file hashes itself`
- `0x18021fc19`: `m_DpxJob->SetOptionValue(L"hardlink_assets", L"1")`
- `0x18021fb6e`: `m_DpxJob->SetOptionValue(L"windir", m_OfflineWindowsPath.c_str())`
- `0x18021fb95`: `complete_self_copies`
- `0x18021fbc9`: `m_DpxJob->SetOptionValue(L"complete_self_copies", L"1")`
- `0x18021fbe5`: `hardlink_assets`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall PackageExpander::Init(
        PackageExpander *this,
        int a2,
        __int64 a3,
        _QWORD *a4,
        _QWORD *a5,
        INT_PTR (__stdcall *a6)(),
        _QWORD *a7,
        _QWORD *a8,
        _DWORD *a9)
{
  _QWORD *v9; // rdi
  INT_PTR (__stdcall *v12)(); // r12
  INT_PTR (__stdcall *v13)(); // rsi
  _QWORD *v14; // rdx
  _QWORD *v15; // rdx
  _QWORD *v16; // rdx
  int v17; // r13d
  __int64 v18; // rax
  int v19; // edx
  int v20; // r8d
  int v21; // r9d
  __int64 v22; // rcx
  const wchar_t *v23; // rax
  const WCHAR *p_lpLibFileName; // rcx
  HMODULE Library; // rax
  HMODULE v26; // rax
  signed int LastError; // ebx
  const char *v28; // rax
  __int64 result; // rax
  FARPROC ProcAddress; // r13
  FARPROC v31; // rsi
  FARPROC v32; // rax
  char v33; // al
  int v34; // r15d
  _QWORD *v35; // rcx
  int v36; // esi
  const char *v37; // rax
  _QWORD *v38; // rcx
  int v39; // esi
  _QWORD *v40; // r14
  int v41; // edi
  const char *v42; // rax
  __int64 v43; // rax
  const WCHAR *v44; // rcx
  HMODULE v45; // rax
  HMODULE v46; // rcx
  FARPROC v47; // rdi
  _QWORD *v48; // r8
  _QWORD *v49; // rdx
  __int64 v50; // rdx
  const char *v51; // rax
  char v52; // r13
  _QWORD *v53; // rdx
  bool v54; // [rsp+58h] [rbp-69h] BYREF
  int v55; // [rsp+5Ch] [rbp-65h]
  _DWORD *v56; // [rsp+60h] [rbp-61h]
  const wchar_t *v57; // [rsp+68h] [rbp-59h] BYREF
  __int64 v58; // [rsp+70h] [rbp-51h]
  _QWORD *v59; // [rsp+78h] [rbp-49h]
  __int64 v60; // [rsp+80h] [rbp-41h]
  __int128 lpLibFileName; // [rsp+88h] [rbp-39h] BYREF
  __int64 v62; // [rsp+98h] [rbp-29h]
  const char *v63; // [rsp+A0h] [rbp-21h]
  int v64; // [rsp+A8h] [rbp-19h] BYREF
  FARPROC v65; // [rsp+B0h] [rbp-11h] BYREF
  __int64 v66; // [rsp+B8h] [rbp-9h]

  v60 = -2;
  v9 = a4;
  v55 = a2;
  v59 = a5;
  v12 = a6;
  v56 = a9;
  if ( a9 )
    *a9 = 0;
  v13 = (INT_PTR (__stdcall *)())((char *)this + 40);
  if ( (_QWORD *)((char *)this + 40) != a4 )
  {
    if ( a4[3] <= 7u )
      v14 = a4;
    else
      v14 = (_QWORD *)*a4;
    std::wstring::_Assign<wchar_t>((char *)this + 40, v14, a4[2]);
  }
  *((_QWORD *)this + 27) = a3;
  if ( (_QWORD *)((char *)this + 72) != a7 )
  {
    if ( a7[3] <= 7u )
      v15 = a7;
    else
      v15 = (_QWORD *)*a7;
    std::wstring::_Assign<wchar_t>((char *)this + 72, v15, a7[2]);
  }
  if ( (_QWORD *)((char *)this + 104) != a8 )
  {
    if ( a8[3] <= 7u )
      v16 = a8;
    else
      v16 = (_QWORD *)*a8;
    std::wstring::_Assign<wchar_t>((char *)this + 104, v16, a8[2]);
  }
  v17 = v55;
  *((_BYTE *)this + 226) = v55 & 1;
  v18 = *((_QWORD *)v13 + 2);
  if ( *((_QWORD *)v13 + 3) > 7u )
    v13 = *(INT_PTR (__stdcall **)())v13;
  v65 = v13;
  v66 = v18;
  EnsureDirectoryExistsHr(&v65);
  v64 = v17;
  v65 = (FARPROC)&v64;
  if ( *(_QWORD *)&LogAdapter::g_Logger )
    LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHex8Wrapper<unsigned long>,std::wstring,std::wstring,std::wstring,std::wstring>(
      LogAdapter::g_Logger,
      v19,
      v20,
      v21,
      (__int64)&v65,
      (__int64)v9,
      (__int64)a6,
      (__int64)a7,
      (__int64)a8);
  v22 = *((_QWORD *)a6 + 2);
  if ( v22 )
  {
    v65 = (FARPROC)L"dpx.dll";
    v66 = 7;
    if ( *((_QWORD *)a6 + 3) <= 7u )
      v23 = (const wchar_t *)a6;
    else
      v23 = *(const wchar_t **)a6;
    v57 = v23;
    v58 = v22;
    CreatePath(&lpLibFileName, (__int64)&v57, &v65);
    LogAdapter::TraceAtLevel<std::wstring>(1, "Attempting to load DPX from {0}", &lpLibFileName);
    p_lpLibFileName = (const WCHAR *)&lpLibFileName;
    if ( (unsigned __int64)v63 > 7 )
      p_lpLibFileName = (const WCHAR *)lpLibFileName;
    Library = LoadLibraryExW(p_lpLibFileName, 0, 8u);
    if ( *((_QWORD *)this + 17) )
    {
LABEL_145:
      INTERNAL_ERROR_ACTION(-1073741595);
LABEL_146:
      INTERNAL_ERROR_ACTION(-1073741595);
      __debugbreak();
    }
    *((_QWORD *)this + 17) = Library;
    std::wstring::~wstring(&lpLibFileName);
  }
  v26 = (HMODULE)*((_QWORD *)this + 17);
  if ( !v26 )
  {
    LogAdapter::TraceInfo<>("Attempting to load DPX from system path");
    v26 = LoadLibraryExW(L"dpx.dll", 0, 0);
    if ( *((_QWORD *)this + 17) )
      goto LABEL_147;
    *((_QWORD *)this + 17) = v26;
    if ( !v26 )
    {
      if ( !GetLastError() )
      {
        LastError = 14077;
LABEL_36:
        *(_QWORD *)&lpLibFileName = "onecore\\base\\servicing\\expander\\lib\\expander.cpp";
        *((_QWORD *)&lpLibFileName + 1) = "PackageExpander::Init";
        v62 = 497;
        v28 = "m_DpxModule.IsValid()";
        goto LABEL_37;
      }
      LastError = GetLastError();
      if ( LastError )
        goto LABEL_36;
      goto LABEL_147;
    }
  }
  ProcAddress = GetProcAddress(v26, "DpxRestoreJob");
  if ( !ProcAddress )
  {
    if ( !GetLastError() )
    {
      LastError = 14077;
LABEL_44:
      *(_QWORD *)&lpLibFileName = "onecore\\base\\servicing\\expander\\lib\\expander.cpp";
      *((_QWORD *)&lpLibFileName + 1) = "PackageExpander::Init";
      v62 = 505;
      v28 = "pfnDpxRestoreJob";
      goto LABEL_37;
    }
    LastError = GetLastError();
    if ( LastError )
      goto LABEL_44;
LABEL_147:
    INTERNAL_ERROR_ACTION(-1073741595);
    goto LABEL_148;
  }
  v65 = GetProcAddress(*((HMODULE *)this + 17), "DpxNewJob");
  if ( !v65 )
  {
    if ( GetLastError() )
    {
      LastError = GetLastError();
      if ( !LastError )
        goto LABEL_147;
    }
    else
    {
      LastError = 14077;
    }
    *(_QWORD *)&lpLibFileName = "onecore\\base\\servicing\\expander\\lib\\expander.cpp";
    *((_QWORD *)&lpLibFileName + 1) = "PackageExpander::Init";
    v62 = 508;
    v28 = "pfnDpxNewJob";
LABEL_37:
    v63 = v28;
    if ( LastError > 0 )
      LastError = (unsigned __int16)LastError | 0x80070000;
    goto LABEL_39;
  }
  v31 = GetProcAddress(*((HMODULE *)this + 17), "DpxCheckJobExists");
  if ( !v31 )
  {
    if ( GetLastError() )
    {
      LastError = GetLastError();
      if ( !LastError )
        goto LABEL_147;
    }
    else
    {
      LastError = 14077;
    }
    *(_QWORD *)&lpLibFileName = "onecore\\base\\servicing\\expander\\lib\\expander.cpp";
    *((_QWORD *)&lpLibFileName + 1) = "PackageExpander::Init";
    v62 = 511;
    v28 = "pfnDpxCheckJobExists";
    goto LABEL_37;
  }
  v32 = GetProcAddress(*((HMODULE *)this + 17), "DpxFreeMemory");
  *((_QWORD *)this + 4) = v32;
  if ( !v32 )
  {
    if ( GetLastError() )
    {
      LastError = GetLastError();
      if ( !LastError )
        goto LABEL_147;
    }
    else
    {
      LastError = 14077;
    }
    *(_QWORD *)&lpLibFileName = "onecore\\base\\servicing\\expander\\lib\\expander.cpp";
    *((_QWORD *)&lpLibFileName + 1) = "PackageExpander::Init";
    v62 = 514;
    v28 = "m_pfnDpxFreeMemory";
    goto LABEL_37;
  }
  v33 = v55;
  v34 = v55 & 4;
  if ( (v55 & 4) != 0 )
  {
LABEL_76:
    if ( *((_BYTE *)this + 225) )
    {
      v39 = v33 & 2;
      v40 = (_QWORD *)((char *)this + 200);
    }
    else
    {
      v39 = v33 & 2;
      if ( (v33 & 2) != 0 )
      {
        if ( v56 )
          *v56 = 2;
        return 0;
      }
      v40 = (_QWORD *)((char *)this + 200);
      if ( *((_QWORD *)this + 25) )
        goto LABEL_147;
      if ( v9[3] > 7u )
        v9 = (_QWORD *)*v9;
      v41 = ((__int64 (__fastcall *)(_QWORD *, char *))v65)(v9, (char *)this + 200);
      if ( v41 < 0 )
      {
        *(_QWORD *)&lpLibFileName = "onecore\\base\\servicing\\expander\\lib\\expander.cpp";
        *((_QWORD *)&lpLibFileName + 1) = "PackageExpander::Init";
        v62 = 543;
        v42 = "pfnDpxNewJob(OutputFolder.c_str(), m_DpxJob.GetInitPointer())";
LABEL_85:
        v63 = v42;
        RtlReportErrorOrigination(&lpLibFileName, &GUID_e323b7c4_7a1a_4e06_bf6d_56ccd7377627, (unsigned int)v41);
        return (unsigned int)v41;
      }
    }
    if ( v34 || v39 )
      goto LABEL_125;
    v43 = *((_QWORD *)a6 + 2);
    if ( v43 )
    {
      v57 = L"turbostack.dll";
      v58 = 14;
      if ( *((_QWORD *)a6 + 3) > 7u )
        v12 = *(INT_PTR (__stdcall **)())a6;
      v65 = v12;
      v66 = v43;
      CreatePath(&lpLibFileName, (__int64)&v65, &v57);
      LogAdapter::TraceAtLevel<std::wstring>(1, "Attempting to load TurboStack from {0}", &lpLibFileName);
      v44 = (const WCHAR *)&lpLibFileName;
      if ( (unsigned __int64)v63 > 7 )
        v44 = (const WCHAR *)lpLibFileName;
      v45 = LoadLibraryExW(v44, 0, 8u);
      if ( *((_QWORD *)this + 18) )
      {
LABEL_148:
        INTERNAL_ERROR_ACTION(-1073741595);
        JUMPOUT(0x18021FCF1LL);
      }
      *((_QWORD *)this + 18) = v45;
      std::wstring::~wstring(&lpLibFileName);
    }
    v46 = (HMODULE)*((_QWORD *)this + 18);
    if ( !v46 )
    {
LABEL_125:
      if ( *((_QWORD *)this + 15)
        && (LastError = (*(__int64 (__fastcall **)(_QWORD, const wchar_t *))(**((_QWORD **)this + 25) + 120LL))(
                          *((_QWORD *)this + 25),
                          L"windir"),
            LastError < 0) )
      {
        *(_QWORD *)&lpLibFileName = "onecore\\base\\servicing\\expander\\lib\\expander.cpp";
        *((_QWORD *)&lpLibFileName + 1) = "PackageExpander::Init";
        v62 = 596;
        v51 = "m_DpxJob->SetOptionValue(L\"windir\", m_OfflineWindowsPath.c_str())";
      }
      else
      {
        v52 = v55;
        if ( (v55 & 8) != 0
          && (LastError = (*(__int64 (__fastcall **)(_QWORD, const wchar_t *, const wchar_t *))(*(_QWORD *)*v40 + 120LL))(
                            *v40,
                            L"complete_self_copies",
                            L"1"),
              LastError < 0) )
        {
          *(_QWORD *)&lpLibFileName = "onecore\\base\\servicing\\expander\\lib\\expander.cpp";
          *((_QWORD *)&lpLibFileName + 1) = "PackageExpander::Init";
          v62 = 601;
          v51 = "m_DpxJob->SetOptionValue(L\"complete_self_copies\", L\"1\")";
        }
        else if ( (v52 & 0x10) != 0
               && (LastError = (*(__int64 (__fastcall **)(_QWORD, const wchar_t *, const wchar_t *))(*(_QWORD *)*v40 + 120LL))(
                                 *v40,
                                 L"hardlink_assets",
                                 L"1"),
                   LastError < 0) )
        {
          *(_QWORD *)&lpLibFileName = "onecore\\base\\servicing\\expander\\lib\\expander.cpp";
          *((_QWORD *)&lpLibFileName + 1) = "PackageExpander::Init";
          v62 = 606;
          v51 = "m_DpxJob->SetOptionValue(L\"hardlink_assets\", L\"1\")";
        }
        else
        {
          v53 = v59;
          if ( !v59[2] )
            goto LABEL_140;
          if ( v59[3] > 7u )
            v53 = (_QWORD *)*v59;
          LastError = (*(__int64 (__fastcall **)(_QWORD, const wchar_t *, _QWORD *))(*(_QWORD *)*v40 + 120LL))(
                        *v40,
                        L"Telemetry_correlation_vector",
                        v53);
          if ( LastError >= 0 )
          {
LABEL_140:
            if ( v56 )
              *v56 = 1;
            return 0;
          }
          *(_QWORD *)&lpLibFileName = "onecore\\base\\servicing\\expander\\lib\\expander.cpp";
          *((_QWORD *)&lpLibFileName + 1) = "PackageExpander::Init";
          v62 = 611;
          v51 = "m_DpxJob->SetOptionValue(L\"Telemetry_correlation_vector\", CorrelationVector.c_str())";
        }
      }
      v63 = v51;
LABEL_39:
      RtlReportErrorOrigination(&lpLibFileName, &GUID_e323b7c4_7a1a_4e06_bf6d_56ccd7377627, (unsigned int)LastError);
      return (unsigned int)LastError;
    }
    v47 = GetProcAddress(v46, "GetIServicingFileHashProvider");
    if ( !v47 )
    {
      LogAdapter::TraceInfo<>("Expander will ask DPX to compute file hashes itself");
      goto LABEL_125;
    }
    LogAdapter::TraceInfo<>("Expander will ask DPX to use the WinSxS file hash provider");
    if ( !*((_QWORD *)this + 26) )
    {
      v41 = ((__int64 (__fastcall *)(char *))v47)((char *)this + 208);
      if ( v41 < 0 )
      {
        *(_QWORD *)&lpLibFileName = "onecore\\base\\servicing\\expander\\lib\\expander.cpp";
        *((_QWORD *)&lpLibFileName + 1) = "PackageExpander::Init";
        v62 = 573;
        v42 = "pfnGetIServicingFileHashProvider(m_HashProvider.GetInitPointer())";
        goto LABEL_85;
      }
      if ( *((_QWORD *)this + 15) )
      {
        v48 = (_QWORD *)((char *)this + 104);
        if ( *((_QWORD *)this + 16) > 7u )
          v48 = (_QWORD *)*v48;
      }
      else
      {
        v48 = 0;
      }
      if ( *((_QWORD *)this + 11) )
      {
        v49 = (_QWORD *)((char *)this + 72);
        if ( *((_QWORD *)this + 12) > 7u )
          v49 = (_QWORD *)*v49;
      }
      else
      {
        v49 = 0;
      }
      v64 = (*(__int64 (__fastcall **)(_QWORD, _QWORD *, _QWORD *))(**((_QWORD **)this + 26) + 32LL))(
              *((_QWORD *)this + 26),
              v49,
              v48);
      if ( v64 < 0 )
      {
        if ( *(_QWORD *)&LogAdapter::g_Logger )
        {
          LOBYTE(v50) = 1;
          LogAdapter::Logger::LogNumObjects<long>(
            *(_QWORD *)&LogAdapter::g_Logger,
            v50,
            1,
            "Failed to initialize the servicing hash provider with error {0}. DPX will compute the file hashes itself",
            &v64);
        }
      }
      else
      {
        v65 = 0;
        v41 = (***((__int64 (__fastcall ****)(_QWORD, GUID *, FARPROC *))this + 25))(
                *((_QWORD *)this + 25),
                &GUID_e1c292c8_919a_4f1b_b85a_9c542932fc8d,
                &v65);
        if ( v41 < 0 )
        {
          *(_QWORD *)&lpLibFileName = "onecore\\base\\servicing\\expander\\lib\\expander.cpp";
          *((_QWORD *)&lpLibFileName + 1) = "PackageExpander::Init";
          v62 = 578;
          v63 = "m_DpxJob->QueryInterface(DpxJob2.GetInitPointer())";
          RtlReportErrorOrigination(&lpLibFileName, &GUID_e323b7c4_7a1a_4e06_bf6d_56ccd7377627, (unsigned int)v41);
          if ( v65 )
            (*(void (__fastcall **)(FARPROC))(*(_QWORD *)v65 + 16LL))(v65);
          return (unsigned int)v41;
        }
        v41 = (*(__int64 (__fastcall **)(FARPROC, __int64, _QWORD))(*(_QWORD *)v65 + 144LL))(
                v65,
                67108865,
                *((_QWORD *)this + 26));
        if ( v41 < 0 )
        {
          *(_QWORD *)&lpLibFileName = "onecore\\base\\servicing\\expander\\lib\\expander.cpp";
          *((_QWORD *)&lpLibFileName + 1) = "PackageExpander::Init";
          v62 = 579;
          v63 = "DpxJob2->SetInventoryProvider(( 0x4000000 ) | ( 0x1 ), m_HashProvider)";
          RtlReportErrorOrigination(&lpLibFileName, &GUID_e323b7c4_7a1a_4e06_bf6d_56ccd7377627, (unsigned int)v41);
          if ( v65 )
            (*(void (__fastcall **)(FARPROC))(*(_QWORD *)v65 + 16LL))(v65);
          return (unsigned int)v41;
        }
        if ( v65 )
          (*(void (__fastcall **)(FARPROC))(*(_QWORD *)v65 + 16LL))(v65);
      }
      goto LABEL_125;
    }
    INTERNAL_ERROR_ACTION(-1073741595);
    goto LABEL_145;
  }
  v64 = 0;
  v35 = v9;
  if ( v9[3] > 7u )
    v35 = (_QWORD *)*v9;
  v36 = ((__int64 (__fastcall *)(_QWORD *, int *))v31)(v35, &v64);
  if ( v36 < 0 )
  {
    *(_QWORD *)&lpLibFileName = "onecore\\base\\servicing\\expander\\lib\\expander.cpp";
    *((_QWORD *)&lpLibFileName + 1) = "PackageExpander::Init";
    v62 = 519;
    v37 = "pfnDpxCheckJobExists(OutputFolder.c_str(), &fExists)";
LABEL_65:
    v63 = v37;
    RtlReportErrorOrigination(&lpLibFileName, &GUID_e323b7c4_7a1a_4e06_bf6d_56ccd7377627, (unsigned int)v36);
    return (unsigned int)v36;
  }
  if ( !v64 )
  {
LABEL_75:
    v33 = v55;
    goto LABEL_76;
  }
  if ( *((_QWORD *)this + 25) )
    goto LABEL_146;
  if ( v9[3] <= 7u )
    v38 = v9;
  else
    v38 = (_QWORD *)*v9;
  v36 = ((__int64 (__fastcall *)(_QWORD *, char *))ProcAddress)(v38, (char *)this + 200);
  if ( v36 < 0 )
  {
    *(_QWORD *)&lpLibFileName = "onecore\\base\\servicing\\expander\\lib\\expander.cpp";
    *((_QWORD *)&lpLibFileName + 1) = "PackageExpander::Init";
    v62 = 523;
    v37 = "pfnDpxRestoreJob(OutputFolder.c_str(), m_DpxJob.GetInitPointer())";
    goto LABEL_65;
  }
  *((_BYTE *)this + 225) = 1;
  v54 = 0;
  result = PackageExpander::CheckForceRecalculateRanges(this, *((struct IDpxJob **)this + 25), &v54);
  if ( (int)result >= 0 )
  {
    *((_BYTE *)this + 224) = !v54;
    goto LABEL_75;
  }
  return result;
}

```

## disassembly

```asm
0x18021f20c  mov     rax, rsp
0x18021f20f  push    rbp
0x18021f210  push    rsi
0x18021f211  push    rdi
0x18021f212  push    r12
0x18021f214  push    r13
0x18021f216  push    r14
0x18021f218  push    r15
0x18021f21a  lea     rbp, [rax-3Fh]
0x18021f21e  sub     rsp, 0C0h
0x18021f225  mov     [rbp+37h+var_78], 0FFFFFFFFFFFFFFFEh
0x18021f22d  mov     [rax+10h], rbx
0x18021f231  mov     rax, cs:__security_cookie
0x18021f238  xor     rax, rsp
0x18021f23b  mov     [rbp+37h+var_38], rax
0x18021f23f  mov     rdi, r9
0x18021f242  mov     r13, r8
0x18021f245  mov     [rbp+37h+var_9C], edx
0x18021f248  mov     rbx, rcx
0x18021f24b  mov     rax, [rbp+37h+arg_20]
0x18021f24f  mov     [rbp+37h+var_80], rax
0x18021f253  mov     r12, [rbp+37h+arg_28]
0x18021f257  mov     r14, [rbp+37h+arg_38]
0x18021f25b  mov     r15, [rbp+37h+arg_30]
0x18021f25f  mov     rax, [rbp+37h+arg_40]
0x18021f266  mov     [rbp+37h+var_98], rax
0x18021f26a  test    rax, rax
0x18021f26d  jz      short loc_18021F275
0x18021f26f  mov     dword ptr [rax], 0
0x18021f275  lea     rsi, [rcx+28h]
0x18021f279  cmp     rsi, rdi
0x18021f27c  jz      short loc_18021F299
0x18021f27e  cmp     qword ptr [r9+18h], 7
0x18021f283  jbe     short loc_18021F28A
0x18021f285  mov     rdx, [r9]
0x18021f288  jmp     short loc_18021F28D
0x18021f28a  mov     rdx, rdi
0x18021f28d  mov     r8, [r9+10h]
0x18021f291  mov     rcx, rsi
0x18021f294  call    ??$_Assign@_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAAEAV01@QEB_W_K@Z; std::wstring::_Assign<wchar_t>(wchar_t const * const,unsigned __int64)
0x18021f299  mov     [rbx+0D8h], r13
0x18021f2a0  lea     rcx, [rbx+48h]
0x18021f2a4  cmp     rcx, r15
0x18021f2a7  jz      short loc_18021F2C1
0x18021f2a9  cmp     qword ptr [r15+18h], 7
0x18021f2ae  jbe     short loc_18021F2B5
0x18021f2b0  mov     rdx, [r15]
0x18021f2b3  jmp     short loc_18021F2B8
0x18021f2b5  mov     rdx, r15
0x18021f2b8  mov     r8, [r15+10h]
0x18021f2bc  call    ??$_Assign@_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAAEAV01@QEB_W_K@Z; std::wstring::_Assign<wchar_t>(wchar_t const * const,unsigned __int64)
0x18021f2c1  lea     rax, [rbx+68h]
0x18021f2c5  cmp     rax, r14
0x18021f2c8  jz      short loc_18021F2E5
0x18021f2ca  cmp     qword ptr [r14+18h], 7
0x18021f2cf  jbe     short loc_18021F2D6
0x18021f2d1  mov     rdx, [r14]
0x18021f2d4  jmp     short loc_18021F2D9
0x18021f2d6  mov     rdx, r14
0x18021f2d9  mov     r8, [r14+10h]
0x18021f2dd  mov     rcx, rax
0x18021f2e0  call    ??$_Assign@_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAAEAV01@QEB_W_K@Z; std::wstring::_Assign<wchar_t>(wchar_t const * const,unsigned __int64)
0x18021f2e5  mov     r13d, [rbp+37h+var_9C]
0x18021f2e9  mov     al, r13b
0x18021f2ec  and     al, 1
0x18021f2ee  mov     [rbx+0E2h], al
0x18021f2f4  mov     rax, [rsi+10h]
0x18021f2f8  cmp     qword ptr [rsi+18h], 7
0x18021f2fd  jbe     short loc_18021F302
0x18021f2ff  mov     rsi, [rsi]
0x18021f302  mov     [rbp+37h+var_48], rsi
0x18021f306  mov     [rbp+37h+var_40], rax
0x18021f30a  lea     rcx, [rbp+37h+var_48]
0x18021f30e  call    ?EnsureDirectoryExistsHr@@YAJAEBV?$basic_zstring_view@_W@wil@@@Z; EnsureDirectoryExistsHr(wil::basic_zstring_view<wchar_t> const &)
0x18021f313  mov     [rbp+37h+var_50], r13d
0x18021f317  lea     rax, [rbp+37h+var_50]
0x18021f31b  mov     [rbp+37h+var_48], rax
0x18021f31f  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x18021f326  test    rcx, rcx
0x18021f329  jz      short loc_18021F34D
0x18021f32b  mov     [rsp+40h], r14
0x18021f330  mov     [rsp+0F0h+var_B8], r15
0x18021f335  mov     [rsp+0F0h+var_C0], r12
0x18021f33a  mov     [rsp+0F0h+var_C8], rdi
0x18021f33f  lea     rax, [rbp+37h+var_48]
0x18021f343  mov     [rsp+0F0h+var_D0], rax
0x18021f348  call    ??$LogNumObjects@U?$FormatHex8Wrapper@K@Rtl@WCP@Windows@@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V56@V56@V56@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHex8Wrapper@K@Rtl@WCP@Windows@@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@444@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHex8Wrapper<ulong>,std::wstring,std::wstring,std::wstring,std::wstring>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHex8Wrapper<ulong> const &,std::wstring const &,std::wstring const &,std::wstring const &,std::wstring const &)
0x18021f34d  mov     rcx, [r12+10h]
0x18021f352  lea     rsi, aDpxDll_0; "dpx.dll"
0x18021f359  xor     r14d, r14d
0x18021f35c  test    rcx, rcx
0x18021f35f  jz      loc_18021F3EE
0x18021f365  mov     [rbp+37h+var_48], rsi
0x18021f369  mov     [rbp+37h+var_40], 7
0x18021f371  cmp     qword ptr [r12+18h], 7
0x18021f377  jbe     short loc_18021F37F
0x18021f379  mov     rax, [r12]
0x18021f37d  jmp     short loc_18021F382
0x18021f37f  mov     rax, r12
0x18021f382  mov     [rbp+37h+var_90], rax
0x18021f386  mov     [rbp+37h+var_88], rcx
0x18021f38a  lea     r8, [rbp+37h+var_48]
0x18021f38e  lea     rdx, [rbp+37h+var_90]
0x18021f392  lea     rcx, [rbp+37h+lpLibFileName]
0x18021f396  call    ?CreatePath@@YA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEBV?$basic_string_view@_WU?$char_traits@_W@std@@@2@0@Z; CreatePath(std::wstring_view const &,std::wstring_view const &)
0x18021f39b  nop
0x18021f39c  lea     r8, [rbp+37h+lpLibFileName]
0x18021f3a0  lea     rdx, aAttemptingToLo; "Attempting to load DPX from {0}"
0x18021f3a7  mov     ecx, 1
0x18021f3ac  call    ??$TraceAtLevel@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@LogAdapter@@YAXW4LogLevel@0@QEBDAEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; LogAdapter::TraceAtLevel<std::wstring>(LogAdapter::LogLevel,char const * const,std::wstring const &)
0x18021f3b1  lea     rcx, [rbp+37h+lpLibFileName]
0x18021f3b5  cmp     [rbp+37h+var_58], 7
0x18021f3ba  cmova   rcx, [rbp+37h+lpLibFileName]; lpLibFileName
0x18021f3bf  xor     edx, edx; hFile
0x18021f3c1  lea     r8d, [rdx+8]; dwFlags
0x18021f3c5  call    cs:__imp_LoadLibraryExW
0x18021f3cc  nop     dword ptr [rax+rax+00h]
0x18021f3d1  cmp     [rbx+88h], r14
0x18021f3d8  jnz     loc_18021FCC6
0x18021f3de  mov     [rbx+88h], rax
0x18021f3e5  lea     rcx, [rbp+37h+lpLibFileName]; void *
0x18021f3e9  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18021f3ee  mov     rax, [rbx+88h]
0x18021f3f5  test    rax, rax
0x18021f3f8  jnz     loc_18021F4B4
0x18021f3fe  lea     rcx, aAttemptingToLo_1; "Attempting to load DPX from system path"
0x18021f405  call    ??$TraceInfo@$$V@LogAdapter@@YAXQEBD@Z; LogAdapter::TraceInfo<>(char const * const)
0x18021f40a  xor     r8d, r8d; dwFlags
0x18021f40d  xor     edx, edx; hFile
0x18021f40f  mov     rcx, rsi; lpLibFileName
0x18021f412  call    cs:__imp_LoadLibraryExW
0x18021f419  nop     dword ptr [rax+rax+00h]
0x18021f41e  cmp     [rbx+88h], r14
0x18021f425  jnz     loc_18021FCDC
0x18021f42b  mov     [rbx+88h], rax
0x18021f432  test    rax, rax
0x18021f435  jnz     short loc_18021F4B4
0x18021f437  call    cs:__imp_GetLastError
0x18021f43e  nop     dword ptr [rax+rax+00h]
0x18021f443  test    eax, eax
0x18021f445  jnz     short loc_18021F44E
0x18021f447  mov     ebx, 36FDh
0x18021f44c  jmp     short loc_18021F464
0x18021f44e  call    cs:__imp_GetLastError
0x18021f455  nop     dword ptr [rax+rax+00h]
0x18021f45a  mov     ebx, eax
0x18021f45c  test    eax, eax
0x18021f45e  jz      loc_18021FCDC
0x18021f464  lea     rax, aOnecoreBaseSer_12; "onecore\\base\\servicing\\expander\\lib"...
0x18021f46b  mov     [rbp+37h+lpLibFileName], rax
0x18021f46f  lea     rax, aPackageexpande_1; "PackageExpander::Init"
0x18021f476  mov     [rbp+37h+var_68], rax
0x18021f47a  mov     [rbp+37h+var_60], 1F1h
0x18021f482  lea     rax, aMDpxmoduleIsva; "m_DpxModule.IsValid()"
0x18021f489  test    ebx, ebx
0x18021f48b  mov     [rbp+37h+var_58], rax
0x18021f48f  jle     short loc_18021F49A
0x18021f491  movzx   ebx, bx
0x18021f494  or      ebx, 80070000h
0x18021f49a  mov     r8d, ebx
0x18021f49d  lea     rdx, _GUID_e323b7c4_7a1a_4e06_bf6d_56ccd7377627
0x18021f4a4  lea     rcx, [rbp+37h+lpLibFileName]
0x18021f4a8  call    RtlReportErrorOrigination
0x18021f4ad  mov     eax, ebx
0x18021f4af  jmp     loc_18021FC93
0x18021f4b4  lea     rdx, aDpxrestorejob; "DpxRestoreJob"
0x18021f4bb  mov     rcx, rax; hModule
0x18021f4be  call    cs:__imp_GetProcAddress
0x18021f4c5  nop     dword ptr [rax+rax+00h]
0x18021f4ca  mov     r13, rax
0x18021f4cd  test    rax, rax
0x18021f4d0  jnz     short loc_18021F529
0x18021f4d2  call    cs:__imp_GetLastError
0x18021f4d9  nop     dword ptr [rax+rax+00h]
0x18021f4de  test    eax, eax
0x18021f4e0  jnz     short loc_18021F4E9
0x18021f4e2  mov     ebx, 36FDh
0x18021f4e7  jmp     short loc_18021F4FF
0x18021f4e9  call    cs:__imp_GetLastError
0x18021f4f0  nop     dword ptr [rax+rax+00h]
0x18021f4f5  mov     ebx, eax
0x18021f4f7  test    eax, eax
0x18021f4f9  jz      loc_18021FCDC
0x18021f4ff  lea     rax, aOnecoreBaseSer_12; "onecore\\base\\servicing\\expander\\lib"...
0x18021f506  mov     [rbp+37h+lpLibFileName], rax
0x18021f50a  lea     rax, aPackageexpande_1; "PackageExpander::Init"
0x18021f511  mov     [rbp+37h+var_68], rax
0x18021f515  mov     [rbp+37h+var_60], 1F9h
0x18021f51d  lea     rax, aPfndpxrestorej; "pfnDpxRestoreJob"
0x18021f524  jmp     loc_18021F489
0x18021f529  lea     rdx, aDpxnewjob; "DpxNewJob"
0x18021f530  mov     rcx, [rbx+88h]; hModule
0x18021f537  call    cs:__imp_GetProcAddress
0x18021f53e  nop     dword ptr [rax+rax+00h]
0x18021f543  mov     [rbp+37h+var_48], rax
0x18021f547  test    rax, rax
0x18021f54a  jnz     short loc_18021F5A3
0x18021f54c  call    cs:__imp_GetLastError
0x18021f553  nop     dword ptr [rax+rax+00h]
0x18021f558  test    eax, eax
0x18021f55a  jnz     short loc_18021F563
0x18021f55c  mov     ebx, 36FDh
0x18021f561  jmp     short loc_18021F579
0x18021f563  call    cs:__imp_GetLastError
0x18021f56a  nop     dword ptr [rax+rax+00h]
0x18021f56f  mov     ebx, eax
0x18021f571  test    eax, eax
0x18021f573  jz      loc_18021FCDC
0x18021f579  lea     rax, aOnecoreBaseSer_12; "onecore\\base\\servicing\\expander\\lib"...
0x18021f580  mov     [rbp+37h+lpLibFileName], rax
0x18021f584  lea     rax, aPackageexpande_1; "PackageExpander::Init"
0x18021f58b  mov     [rbp+37h+var_68], rax
0x18021f58f  mov     [rbp+37h+var_60], 1FCh
0x18021f597  lea     rax, aPfndpxnewjob; "pfnDpxNewJob"
0x18021f59e  jmp     loc_18021F489
0x18021f5a3  lea     rdx, aDpxcheckjobexi; "DpxCheckJobExists"
0x18021f5aa  mov     rcx, [rbx+88h]; hModule
0x18021f5b1  call    cs:__imp_GetProcAddress
0x18021f5b8  nop     dword ptr [rax+rax+00h]
0x18021f5bd  mov     rsi, rax
0x18021f5c0  test    rax, rax
0x18021f5c3  jnz     short loc_18021F61C
0x18021f5c5  call    cs:__imp_GetLastError
0x18021f5cc  nop     dword ptr [rax+rax+00h]
0x18021f5d1  test    eax, eax
0x18021f5d3  jnz     short loc_18021F5DC
0x18021f5d5  mov     ebx, 36FDh
0x18021f5da  jmp     short loc_18021F5F2
0x18021f5dc  call    cs:__imp_GetLastError
0x18021f5e3  nop     dword ptr [rax+rax+00h]
0x18021f5e8  mov     ebx, eax
0x18021f5ea  test    eax, eax
0x18021f5ec  jz      loc_18021FCDC
0x18021f5f2  lea     rax, aOnecoreBaseSer_12; "onecore\\base\\servicing\\expander\\lib"...
0x18021f5f9  mov     [rbp+37h+lpLibFileName], rax
0x18021f5fd  lea     rax, aPackageexpande_1; "PackageExpander::Init"
0x18021f604  mov     [rbp+37h+var_68], rax
0x18021f608  mov     [rbp+37h+var_60], 1FFh
0x18021f610  lea     rax, aPfndpxcheckjob_0; "pfnDpxCheckJobExists"
0x18021f617  jmp     loc_18021F489
0x18021f61c  lea     rdx, aDpxfreememory; "DpxFreeMemory"
0x18021f623  mov     rcx, [rbx+88h]; hModule
0x18021f62a  call    cs:__imp_GetProcAddress
0x18021f631  nop     dword ptr [rax+rax+00h]
0x18021f636  mov     [rbx+20h], rax
0x18021f63a  test    rax, rax
0x18021f63d  jnz     short loc_18021F696
0x18021f63f  call    cs:__imp_GetLastError
0x18021f646  nop     dword ptr [rax+rax+00h]
0x18021f64b  test    eax, eax
0x18021f64d  jnz     short loc_18021F656
0x18021f64f  mov     ebx, 36FDh
0x18021f654  jmp     short loc_18021F66C
0x18021f656  call    cs:__imp_GetLastError
0x18021f65d  nop     dword ptr [rax+rax+00h]
0x18021f662  mov     ebx, eax
0x18021f664  test    eax, eax
0x18021f666  jz      loc_18021FCDC
0x18021f66c  lea     rax, aOnecoreBaseSer_12; "onecore\\base\\servicing\\expander\\lib"...
0x18021f673  mov     [rbp+37h+lpLibFileName], rax
0x18021f677  lea     rax, aPackageexpande_1; "PackageExpander::Init"
0x18021f67e  mov     [rbp+37h+var_68], rax
0x18021f682  mov     [rbp+37h+var_60], 202h
0x18021f68a  lea     rax, aMPfndpxfreemem; "m_pfnDpxFreeMemory"
0x18021f691  jmp     loc_18021F489
0x18021f696  mov     eax, [rbp+37h+var_9C]
0x18021f699  mov     r15d, eax
0x18021f69c  and     r15d, 4
0x18021f6a0  jnz     loc_18021F7A3
0x18021f6a6  mov     [rbp+37h+var_50], r14d
0x18021f6aa  mov     rcx, rdi
0x18021f6ad  cmp     qword ptr [rdi+18h], 7
0x18021f6b2  jbe     short loc_18021F6B7
0x18021f6b4  mov     rcx, [rdi]
0x18021f6b7  lea     rdx, [rbp+37h+var_50]
0x18021f6bb  mov     rax, rsi
0x18021f6be  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18021f6c3  mov     esi, eax
0x18021f6c5  test    eax, eax
0x18021f6c7  jns     short loc_18021F70C
0x18021f6c9  lea     rax, aOnecoreBaseSer_12; "onecore\\base\\servicing\\expander\\lib"...
0x18021f6d0  mov     [rbp+37h+lpLibFileName], rax
0x18021f6d4  lea     rax, aPackageexpande_1; "PackageExpander::Init"
0x18021f6db  mov     [rbp+37h+var_68], rax
0x18021f6df  mov     [rbp+37h+var_60], 207h
0x18021f6e7  lea     rax, aPfndpxcheckjob; "pfnDpxCheckJobExists(OutputFolder.c_str"...
0x18021f6ee  mov     [rbp+37h+var_58], rax
0x18021f6f2  mov     r8d, esi
0x18021f6f5  lea     rdx, _GUID_e323b7c4_7a1a_4e06_bf6d_56ccd7377627
0x18021f6fc  lea     rcx, [rbp+37h+lpLibFileName]
0x18021f700  call    RtlReportErrorOrigination
0x18021f705  mov     eax, esi
0x18021f707  jmp     loc_18021FC93
0x18021f70c  cmp     [rbp+37h+var_50], r14d
0x18021f710  jz      loc_18021F7A0
0x18021f716  lea     r14, [rbx+0C8h]
0x18021f71d  cmp     qword ptr [r14], 0
0x18021f721  jnz     loc_18021FCD1
0x18021f727  cmp     qword ptr [rdi+18h], 7
0x18021f72c  jbe     short loc_18021F733
  ... truncated ...
```
