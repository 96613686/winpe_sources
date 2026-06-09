# DiagHubCommon::Logger::GetLogger(void)

- ea: `0x18003da40`
- end: `0x18003e871`
- name: `?GetLogger@Logger@DiagHubCommon@@SAAEAV12@XZ`
- size: `3633`
- prototype: `struct DiagHubCommon::Logger *(void)`
- caller_count: `3`
- callee_count: `30`
- tags: `file_ops, authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x1800013d0`
- `0x180042e38`
- `0x180043040`

## callees

- `0x180001b50`
- `0x180008914`
- `0x180009d1c`
- `0x180009fa4`
- `0x18000a078`
- `0x18000a17c`
- `0x1800154c0`
- `0x18001662c`
- `0x180025eac`
- `0x1800267fc`
- `0x18003d05c`
- `0x18003d414`
- `0x18003d884`
- `0x18003da40`
- `0x18003e8f0`
- `0x18003ebfc`
- `0x18003fa10`
- `0x18003fc08`
- `0x18004019c`
- `0x18004021c`
- `0x180040bac`
- `0x180040d8c`
- `0x180049b50`
- `0x180049bac`
- `0x180049c18`
- `0x18004a024`
- `0x18004a03c`
- `0x18004a078`
- `0x18004ad26`
- `0x18004b640`

## import_xrefs

- `VCRUNTIME140!wcsrchr` at `0x18003dfb0`
- `VCRUNTIME140!wcsrchr` at `0x18003e082`
- `VCRUNTIME140!wcsrchr` at `0x18003dfb0`
- `VCRUNTIME140!wcsrchr` at `0x18003e082`
- `KERNEL32!GetCurrentProcessId` at `0x18003e1d2`
- `KERNEL32!GetCurrentProcessId` at `0x18003e1d2`
- `KERNEL32!GetFileAttributesW` at `0x18003df5c`
- `KERNEL32!GetFileAttributesW` at `0x18003df5c`
- `MSVCP140!??6?$basic_ostream@GU?$char_traits@G@std@@@std@@QEAAAEAV01@K@Z` at `0x18003e1e1`
- `MSVCP140!??6?$basic_ostream@GU?$char_traits@G@std@@@std@@QEAAAEAV01@K@Z` at `0x18003e1e1`
- `MSVCP140!??0?$basic_ostream@GU?$char_traits@G@std@@@std@@QEAA@PEAV?$basic_streambuf@GU?$char_traits@G@std@@@1@_N@Z` at `0x18003e16d`
- `MSVCP140!??0?$basic_ostream@GU?$char_traits@G@std@@@std@@QEAA@PEAV?$basic_streambuf@GU?$char_traits@G@std@@@1@_N@Z` at `0x18003e16d`
- `MSVCP140!??1?$basic_ios@GU?$char_traits@G@std@@@std@@UEAA@XZ` at `0x18003e34d`
- `MSVCP140!??1?$basic_ios@GU?$char_traits@G@std@@@std@@UEAA@XZ` at `0x18003e34d`
- `MSVCP140!??0?$basic_ios@GU?$char_traits@G@std@@@std@@IEAA@XZ` at `0x18003e147`
- `MSVCP140!??0?$basic_ios@GU?$char_traits@G@std@@@std@@IEAA@XZ` at `0x18003e147`
- `MSVCP140!??0?$basic_streambuf@GU?$char_traits@G@std@@@std@@IEAA@XZ` at `0x18003e1ad`
- `MSVCP140!??0?$basic_streambuf@GU?$char_traits@G@std@@@std@@IEAA@XZ` at `0x18003e1ad`
- `MSVCP140!??1?$basic_ostream@GU?$char_traits@G@std@@@std@@UEAA@XZ` at `0x18003e340`
- `MSVCP140!??1?$basic_ostream@GU?$char_traits@G@std@@@std@@UEAA@XZ` at `0x18003e340`
- `ADVAPI32!RegCloseKey` at `0x18003e82b`
- `ADVAPI32!RegCloseKey` at `0x18003e82b`
- `ADVAPI32!EventWriteString` at `0x18003ddc4`
- `ADVAPI32!EventWriteString` at `0x18003ddc4`
- `ADVAPI32!EventRegister` at `0x18003ddae`
- `ADVAPI32!EventRegister` at `0x18003ddae`
- `ADVAPI32!RegQueryValueExW` at `0x18003dd40`
- `ADVAPI32!RegQueryValueExW` at `0x18003dd40`
- `api-ms-win-crt-string-l1-1-0!wcslen` at `0x18003dca3`
- `api-ms-win-crt-string-l1-1-0!wcslen` at `0x18003dedf`
- `api-ms-win-crt-string-l1-1-0!wcslen` at `0x18003dca3`
- `api-ms-win-crt-string-l1-1-0!wcslen` at `0x18003dedf`

## string_xrefs

- `0x18003de9a`: `LogDirectory`

## pseudocode

```c
// Hidden C++ exception states: #wind=47
struct DiagHubCommon::Logger *DiagHubCommon::Logger::GetLogger(void)
{
  __int64 v0; // rbx
  DiagHubCommon::Logger::LogLevelMapFactory *v1; // rcx
  struct DiagHubCommon::Logger *result; // rax
  char v3; // si
  _DWORD *v4; // rax
  unsigned int v5; // r9d
  int v6; // r15d
  HKEY v7; // rdx
  volatile signed __int32 *v8; // rbx
  __int64 v9; // rdi
  __int64 *v10; // rbx
  size_t v11; // rax
  _WORD *v12; // rdx
  __int64 v13; // rcx
  wchar_t *v14; // r8
  char *v15; // rdi
  __int64 v16; // rdx
  volatile signed __int32 *v17; // rbx
  size_t v18; // rax
  LPCWSTR *v19; // rcx
  LPCWSTR v20; // rdx
  unsigned __int64 v21; // r8
  LPCWSTR *v22; // rcx
  DWORD FileAttributesW; // eax
  int ModulePath; // eax
  bool v25; // zf
  wchar_t *v26; // rax
  int v27; // eax
  int v28; // eax
  bool v29; // zf
  wchar_t *v30; // rax
  int v31; // eax
  DWORD CurrentProcessId; // eax
  const unsigned __int16 *v33; // rbx
  _DWORD *v34; // rdi
  __int64 v35; // rdx
  volatile signed __int32 *v36; // rbx
  void *v37; // rsi
  __int64 v38; // rdi
  _QWORD *v39; // rax
  __int64 v40; // rbx
  __int64 v41; // rdi
  _QWORD *v42; // rax
  __int64 v43; // rbx
  __int64 v44; // rdi
  _QWORD *v45; // rax
  __int64 v46; // rbx
  __int64 v47; // rdi
  _QWORD *v48; // rax
  __int64 v49; // rbx
  __int64 v50; // rdi
  _QWORD *v51; // rax
  DiagHubCommon::Logger *v52; // rbx
  DiagHubCommon::Logger *v53; // rdi
  __int64 v54; // [rsp+38h] [rbp-D0h]
  char *v55; // [rsp+40h] [rbp-C8h] BYREF
  volatile signed __int32 *v56; // [rsp+48h] [rbp-C0h]
  _DWORD *v57; // [rsp+50h] [rbp-B8h] BYREF
  __int128 v58; // [rsp+58h] [rbp-B0h]
  HKEY hKey_8[3]; // [rsp+68h] [rbp-A0h] BYREF
  int v60; // [rsp+80h] [rbp-88h] BYREF
  _BYTE v61[32]; // [rsp+88h] [rbp-80h] BYREF
  _BYTE *v62; // [rsp+A8h] [rbp-60h]
  _BYTE *v63; // [rsp+B0h] [rbp-58h]
  _BYTE *v64; // [rsp+B8h] [rbp-50h]
  void *v65; // [rsp+C0h] [rbp-48h]
  _BYTE *v66; // [rsp+C8h] [rbp-40h]
  _BYTE v67[24]; // [rsp+D0h] [rbp-38h] BYREF
  _BYTE v68[24]; // [rsp+E8h] [rbp-20h] BYREF
  _BYTE v69[24]; // [rsp+100h] [rbp-8h] BYREF
  _BYTE v70[24]; // [rsp+118h] [rbp+10h] BYREF
  _BYTE v71[24]; // [rsp+130h] [rbp+28h] BYREF
  _BYTE v72[32]; // [rsp+148h] [rbp+40h] BYREF
  _BYTE v73[24]; // [rsp+168h] [rbp+60h] BYREF
  _BYTE v74[32]; // [rsp+180h] [rbp+78h] BYREF
  _BYTE v75[24]; // [rsp+1A0h] [rbp+98h] BYREF
  _BYTE v76[32]; // [rsp+1B8h] [rbp+B0h] BYREF
  _BYTE v77[24]; // [rsp+1D8h] [rbp+D0h] BYREF
  _BYTE v78[32]; // [rsp+1F0h] [rbp+E8h] BYREF
  _BYTE v79[24]; // [rsp+210h] [rbp+108h] BYREF
  _BYTE v80[32]; // [rsp+228h] [rbp+120h] BYREF
  _BYTE v81[16]; // [rsp+248h] [rbp+140h] BYREF
  _BYTE v82[32]; // [rsp+258h] [rbp+150h] BYREF
  _BYTE v83[32]; // [rsp+278h] [rbp+170h] BYREF
  _BYTE v84[32]; // [rsp+298h] [rbp+190h] BYREF
  _BYTE v85[32]; // [rsp+2B8h] [rbp+1B0h] BYREF
  DWORD cbData; // [rsp+2D8h] [rbp+1D0h] BYREF
  __int128 v87; // [rsp+2E0h] [rbp+1D8h] BYREF
  __int64 v88; // [rsp+2F0h] [rbp+1E8h]
  DWORD Type; // [rsp+2F8h] [rbp+1F0h] BYREF
  LPCWSTR lpFileName[2]; // [rsp+300h] [rbp+1F8h] BYREF
  __int64 v91; // [rsp+310h] [rbp+208h]
  unsigned __int64 v92; // [rsp+318h] [rbp+210h]
  wchar_t *Str[2]; // [rsp+320h] [rbp+218h] BYREF
  __int128 v94; // [rsp+330h] [rbp+228h]
  wchar_t *v95; // [rsp+340h] [rbp+238h]
  BYTE Data[8]; // [rsp+348h] [rbp+240h] BYREF
  __int128 v97; // [rsp+350h] [rbp+248h] BYREF
  __int64 v98; // [rsp+360h] [rbp+258h]
  __int128 v99; // [rsp+368h] [rbp+260h] BYREF
  __int64 v100; // [rsp+378h] [rbp+270h]
  __int128 v101; // [rsp+380h] [rbp+278h] BYREF
  __int64 v102; // [rsp+390h] [rbp+288h]
  __int128 v103; // [rsp+398h] [rbp+290h] BYREF
  __int64 v104; // [rsp+3A8h] [rbp+2A0h]
  __int128 v105; // [rsp+3B0h] [rbp+2A8h] BYREF
  __int64 v106; // [rsp+3C0h] [rbp+2B8h]
  int v107; // [rsp+3C8h] [rbp+2C0h]
  _QWORD v108[2]; // [rsp+3D0h] [rbp+2C8h] BYREF
  __int64 v109; // [rsp+3E0h] [rbp+2D8h]
  unsigned __int64 v110; // [rsp+3E8h] [rbp+2E0h]
  int v111; // [rsp+3F4h] [rbp+2ECh]
  __int64 *v112; // [rsp+3F8h] [rbp+2F0h] BYREF
  void **v113; // [rsp+400h] [rbp+2F8h] BYREF
  _BYTE v114[96]; // [rsp+408h] [rbp+300h] BYREF
  __int64 v115; // [rsp+468h] [rbp+360h]
  int v116; // [rsp+470h] [rbp+368h]
  _BYTE v117[104]; // [rsp+480h] [rbp+378h] BYREF
  wchar_t String[264]; // [rsp+4E8h] [rbp+3E0h] BYREF

  Type = 0;
  v0 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + (unsigned int)tls_index);
  if ( dword_180077A40 > *(_DWORD *)(v0 + 4) )
  {
    Init_thread_header(&dword_180077A40);
    if ( dword_180077A40 == -1 )
    {
      atexit(DiagHubCommon::Logger::GetLogger_::_2_::_dynamic_atexit_destructor_for__loggerInstance__);
      Init_thread_footer(&dword_180077A40);
    }
  }
  if ( dword_180077A44 > *(_DWORD *)(v0 + 4) )
  {
    Init_thread_header(&dword_180077A44);
    if ( dword_180077A44 == -1 )
    {
      memset_0(&dword_180077A50, 0, 0x40u);
      DiagHubCommon::Logger::LogLevelMapFactory::LogLevelMapFactory(v1);
      atexit(DiagHubCommon::Logger::GetLogger_::_2_::_dynamic_atexit_destructor_for__logLevelMapFactory__);
      Init_thread_footer(&dword_180077A44);
    }
  }
  result = Block;
  if ( Block )
    return result;
  v3 = 0;
  v87 = 0;
  v88 = 0;
  v4 = operator new(0x18u);
  v57 = v4;
  *(_OWORD *)v4 = 0;
  v4[2] = 1;
  v4[3] = 1;
  *(_QWORD *)v4 = &std::_Ref_count_obj2<DiagHubCommon::DebugStringLogWriter>::`vftable';
  *((_QWORD *)v4 + 2) = &DiagHubCommon::DebugStringLogWriter::`vftable';
  v6 = 1;
  v55 = (char *)(v4 + 4);
  v56 = v4;
  v58 = 0;
  v7 = (HKEY)*((_QWORD *)&v87 + 1);
  if ( *((_QWORD *)&v87 + 1) == v88 )
  {
    std::vector<std::shared_ptr<DiagHubCommon::ILogWriter>>::_Emplace_reallocate<std::shared_ptr<DiagHubCommon::ILogWriter>>(
      &v87,
      *((_QWORD *)&v87 + 1),
      &v55);
    v8 = v56;
  }
  else
  {
    **((_QWORD **)&v87 + 1) = v4 + 4;
    *((_QWORD *)v7 + 1) = v4;
    v8 = 0;
    *((_QWORD *)&v87 + 1) += 16LL;
  }
  if ( v8 )
  {
    if ( _InterlockedExchangeAdd(v8 + 2, 0xFFFFFFFF) == 1 )
    {
      (**(void (__fastcall ***)(volatile signed __int32 *))v8)(v8);
      if ( _InterlockedExchangeAdd(v8 + 3, 0xFFFFFFFF) == 1 )
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v8 + 8LL))(v8);
    }
  }
  memset(hKey_8, 0, sizeof(hKey_8));
  if ( ATL::CRegKey::Open((ATL::CRegKey *)hKey_8, v7, L"Software\\Microsoft\\VisualStudio\\DiagnosticsHub", v5) )
    goto LABEL_75;
  cbData = 261;
  if ( (unsigned int)ATL::CRegKey::QueryStringValue((ATL::CRegKey *)hKey_8, L"LogLevel", String, &cbData) )
    goto LABEL_26;
  v9 = qword_180077A58;
  v10 = *(__int64 **)qword_180077A58;
  if ( *(_QWORD *)qword_180077A58 == qword_180077A58 )
    goto LABEL_26;
  while ( 1 )
  {
    v107 = *((_DWORD *)v10 + 4);
    std::wstring::wstring(v108, v10 + 3);
    v11 = wcslen(String);
    v12 = v108;
    if ( v110 > 7 )
      v12 = (_WORD *)v108[0];
    v13 = v109;
    if ( v109 == v11 )
      break;
LABEL_31:
    std::wstring::~wstring(v108);
    v10 = (__int64 *)*v10;
    if ( v10 == (__int64 *)v9 )
      goto LABEL_26;
  }
  if ( v109 )
  {
    v14 = String;
    while ( *v12 == *v14 )
    {
      ++v12;
      ++v14;
      if ( !--v13 )
        goto LABEL_25;
    }
    goto LABEL_31;
  }
LABEL_25:
  v3 = v107;
  std::wstring::~wstring(v108);
LABEL_26:
  cbData = 4;
  if ( !RegQueryValueExW(hKey_8[0], L"EtwLogging", 0, &Type, Data, &cbData) && Type == 4 && *(_DWORD *)Data == 1 )
  {
    v15 = (char *)operator new(0x20u);
    v57 = v15;
    *(_OWORD *)v15 = 0;
    *((_DWORD *)v15 + 2) = 1;
    *((_DWORD *)v15 + 3) = 1;
    *(_QWORD *)v15 = &std::_Ref_count_obj2<DiagHubCommon::EtlLogWriter>::`vftable';
    *((_QWORD *)v15 + 2) = &DiagHubCommon::EtlLogWriter::`vftable';
    EventRegister(&DiagHubCommon::EtlLogWriter::providerGuid, 0, 0, (PREGHANDLE)v15 + 3);
    EventWriteString(*((_QWORD *)v15 + 3), 0, 0, L"============= Diagnostics Hub Log =============");
    v6 = 3;
    v55 = v15 + 16;
    v56 = (volatile signed __int32 *)v15;
    v58 = 0;
    v16 = *((_QWORD *)&v87 + 1);
    if ( *((_QWORD *)&v87 + 1) == v88 )
    {
      std::vector<std::shared_ptr<DiagHubCommon::ILogWriter>>::_Emplace_reallocate<std::shared_ptr<DiagHubCommon::ILogWriter>>(
        &v87,
        *((_QWORD *)&v87 + 1),
        &v55);
      v17 = v56;
    }
    else
    {
      **((_QWORD **)&v87 + 1) = v15 + 16;
      *(_QWORD *)(v16 + 8) = v15;
      v17 = 0;
      *((_QWORD *)&v87 + 1) += 16LL;
    }
    if ( v17 )
    {
      if ( _InterlockedExchangeAdd(v17 + 2, 0xFFFFFFFF) == 1 )
      {
        (**(void (__fastcall ***)(volatile signed __int32 *))v17)(v17);
        if ( _InterlockedExchangeAdd(v17 + 3, 0xFFFFFFFF) == 1 )
          (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v17 + 8LL))(v17);
      }
    }
  }
  cbData = 261;
  if ( !(unsigned int)ATL::CRegKey::QueryStringValue((ATL::CRegKey *)hKey_8, L"LogDirectory", String, &cbData)
    && cbData > 1 )
  {
    *(_OWORD *)lpFileName = 0;
    v91 = 0;
    v92 = 0;
    v18 = wcslen(String);
    std::wstring::_Construct<1,unsigned short const *>(lpFileName, String, v18);
    v19 = lpFileName;
    v20 = lpFileName[0];
    v21 = v92;
    if ( v92 > 7 )
      v19 = (LPCWSTR *)lpFileName[0];
    if ( *((_WORD *)v19 + v91 - 1) != 92 )
    {
      std::wstring::append(lpFileName, L"\\");
      v21 = v92;
      v20 = lpFileName[0];
    }
    v22 = lpFileName;
    if ( v21 > 7 )
      v22 = (LPCWSTR *)v20;
    FileAttributesW = GetFileAttributesW((LPCWSTR)v22);
    if ( FileAttributesW != -1 && (FileAttributesW & 0x10) != 0 )
    {
      *(_OWORD *)Str = 0;
      v94 = 0;
      v95 = 0;
      ModulePath = DiagHubCommon::ModulePath::GetModulePath(0);
      v25 = ModulePath == 0;
      if ( ModulePath >= 0 )
      {
        v26 = wcsrchr(Str[0], 0x5Cu);
        if ( v26 )
        {
          *v26 = 0;
          *((wchar_t **)&v94 + 1) = Str[0];
          v95 = v26 + 1;
          v27 = 0;
        }
        else
        {
          v27 = -2147024735;
        }
        v25 = v27 == 0;
      }
      if ( v25 )
      {
        DiagHubCommon::ModulePath::GetNameNoExtension(Str, v61);
        std::wstring::append(lpFileName);
        std::wstring::~wstring(v61);
      }
      else
      {
        std::wstring::append(lpFileName, L"UnknownProcess");
      }
      std::wstring::append(lpFileName, (void *)L".");
      std::vector<unsigned short>::~vector<unsigned short>(Str);
      *(_OWORD *)Str = 0;
      v94 = 0;
      v95 = 0;
      v28 = DiagHubCommon::ModulePath::GetModulePath((HMODULE)0x180000000LL);
      v29 = v28 == 0;
      if ( v28 >= 0 )
      {
        v30 = wcsrchr(Str[0], 0x5Cu);
        if ( v30 )
        {
          *v30 = 0;
          *((wchar_t **)&v94 + 1) = Str[0];
          v95 = v30 + 1;
          v31 = 0;
        }
        else
        {
          v31 = -2147024735;
        }
        v29 = v31 == 0;
      }
      if ( v29 )
      {
        DiagHubCommon::ModulePath::GetNameNoExtension(Str, v61);
        std::wstring::append(lpFileName);
        std::wstring::~wstring(v61);
      }
      else
      {
        std::wstring::append(lpFileName, L"UnknownModule");
      }
      std::wstring::append(lpFileName, (void *)L".");
      std::vector<unsigned short>::~vector<unsigned short>(Str);
      memset_0(&v112, 0, 0xE8u);
      v112 = &std::basic_stringstream<unsigned short,std::char_traits<unsigned short>,std::allocator<unsigned short>>::`vbtable'{for `std::basic_ostream<unsigned short>'};
      std::basic_ios<unsigned short>::basic_ios<unsigned short>(v117);
      Type = v6 | 0x10;
      std::basic_ostream<unsigned short>::basic_ostream<unsigned short>(&v112, &v113, 0, 0);
      *(__int64 **)((char *)&v112 + *((int *)v112 + 1)) = (__int64 *)&std::basic_ostringstream<unsigned short>::`vftable';
      *(int *)((char *)&v111 + *((int *)v112 + 1)) = *((_DWORD *)v112 + 1) - 136;
      std::basic_streambuf<unsigned short>::basic_streambuf<unsigned short>(&v113);
      v113 = &std::basic_stringbuf<unsigned short>::`vftable';
      v115 = 0;
      v116 = 4;
      CurrentProcessId = GetCurrentProcessId();
      std::basic_ostream<unsigned short>::operator<<(&v112, CurrentProcessId);
      std::basic_stringbuf<unsigned short>::str(&v113, v61);
      std::wstring::append(lpFileName);
      std::wstring::~wstring(v61);
      std::wstring::append(lpFileName, L".log");
      v33 = (const unsigned __int16 *)lpFileName;
      if ( v92 > 7 )
        v33 = lpFileName[0];
      v34 = operator new(0x148u);
      v57 = v34;
      *(_OWORD *)v34 = 0;
      v34[2] = 1;
      v34[3] = 1;
      *(_QWORD *)v34 = &std::_Ref_count_obj2<DiagHubCommon::FileLogWriter>::`vftable';
      DiagHubCommon::FileLogWriter::FileLogWriter((DiagHubCommon::FileLogWriter *)(v34 + 4), v33);
      v55 = (char *)(v34 + 4);
      v56 = v34;
      v58 = 0;
      v35 = *((_QWORD *)&v87 + 1);
      if ( *((_QWORD *)&v87 + 1) == v88 )
      {
        std::vector<std::shared_ptr<DiagHubCommon::ILogWriter>>::_Emplace_reallocate<std::shared_ptr<DiagHubCommon::ILogWriter>>(
          &v87,
          *((_QWORD *)&v87 + 1),
          &v55);
        v36 = v56;
      }
      else
      {
        **((_QWORD **)&v87 + 1) = v34 + 4;
        *(_QWORD *)(v35 + 8) = v34;
        v36 = 0;
        *((_QWORD *)&v87 + 1) += 16LL;
      }
      if ( v36 )
      {
        if ( _InterlockedExchangeAdd(v36 + 2, 0xFFFFFFFF) == 1 )
        {
          (**(void (__fastcall ***)(volatile signed __int32 *))v36)(v36);
          if ( _InterlockedExchangeAdd(v36 + 3, 0xFFFFFFFF) == 1 )
            (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v36 + 8LL))(v36);
        }
      }
      *(__int64 **)((char *)&v112 + *((int *)v112 + 1)) = (__int64 *)&std::basic_ostringstream<unsigned short>::`vftable';
      *(int *)((char *)&v111 + *((int *)v112 + 1)) = *((_DWORD *)v112 + 1) - 136;
      std::basic_stringbuf<unsigned short>::~basic_stringbuf<unsigned short>(&v113);
      std::basic_ostream<unsigned short>::~basic_ostream<unsigned short,std::char_traits<unsigned short>>(v114);
      std::basic_ios<unsigned short>::~basic_ios<unsigned short,std::char_traits<unsigned short>>(v117);
    }
    std::wstring::~wstring(lpFileName);
  }
LABEL_75:
  v103 = 0;
  v104 = 0;
  v101 = 0;
  v102 = 0;
  v99 = 0;
  v100 = 0;
  v97 = 0;
  v98 = 0;
  v105 = 0;
  v106 = 0;
  if ( (v3 & 1) != 0 )
    std::vector<std::shared_ptr<DiagHubCommon::ILogWriter>>::_Assign_counted_range<std::shared_ptr<DiagHubCommon::ILogWriter> *>(
      &v103,
      v87,
      (__int64)(*((_QWORD *)&v87 + 1) - v87) >> 4);
  if ( (v3 & 2) != 0 )
    std::vector<std::shared_ptr<DiagHubCommon::ILogWriter>>::_Assign_counted_range<std::shared_ptr<DiagHubCommon::ILogWriter> *>(
      &v101,
      v87,
      (__int64)(*((_QWORD *)&v87 + 1) - v87) >> 4);
  if ( (v3 & 4) != 0 )
    std::vector<std::shared_ptr<DiagHubCommon::ILogWriter>>::_Assign_counted_range<std::shared_ptr<DiagHubCommon::ILogWriter> *>(
      &v99,
      v87,
      (__int64)(*((_QWORD *)&v87 + 1) - v87) >> 4);
  if ( (v3 & 8) != 0 )
    std::vector<std::shared_ptr<DiagHubCommon::ILogWriter>>::_Assign_counted_range<std::shared_ptr<DiagHubCommon::ILogWriter> *>(
      &v97,
      v87,
      (__int64)(*((_QWORD *)&v87 + 1) - v87) >> 4);
  if ( (v3 & 0x10) != 0 )
    std::vector<std::shared_ptr<DiagHubCommon::ILogWriter>>::_Assign_counted_range<std::shared_ptr<DiagHubCommon::ILogWriter> *>(
      &v105,
      v87,
      (__int64)(*((_QWORD *)&v87 + 1) - v87) >> 4);
  v37 = operator new(0x118u);
  v65 = v37;
  memset_0(v37, 0, 0x118u);
  v66 = v71;
  v38 = std::vector<std::shared_ptr<DiagHubCommon::ILogWriter>>::vector<std::shared_ptr<DiagHubCommon::ILogWriter>>(
          v67,
          &v105);
  v62 = (_BYTE *)v38;
  *(_DWORD *)Data = 16;
  v39 = (_QWORD *)std::_Hash<std::_Umap_traits<enum DiagHubCommon::LogLevel,std::wstring,std::_Uhash_compare<enum DiagHubCommon::LogLevel,std::hash<enum DiagHubCommon::LogLevel>,std::equal_to<enum DiagHubCommon::LogLevel>>,std::allocator<std::pair<enum DiagHubCommon::LogLevel const,std::wstring>>,0>>::_Try_emplace<enum DiagHubCommon::LogLevel,>(
                    &dword_180077A50,
                    &v55,
                    Data);
  v40 = std::wstring::wstring(v82, *v39 + 24LL);
  std::vector<std::shared_ptr<DiagHubCommon::ILogWriter>>::vector<std::shared_ptr<DiagHubCommon::ILogWriter>>(v71, v38);
  std::wstring::wstring(v72, v40);
  std::wstring::~wstring(v40);
  std::vector<std::shared_ptr<Microsoft::Json::Object>>::~vector<std::shared_ptr<Microsoft::Json::Object>>(v38);
  v62 = v73;
  v41 = std::vector<std::shared_ptr<DiagHubCommon::ILogWriter>>::vector<std::shared_ptr<DiagHubCommon::ILogWriter>>(
          v68,
          &v97);
  v63 = (_BYTE *)v41;
  Type = 8;
  v42 = (_QWORD *)std::_Hash<std::_Umap_traits<enum DiagHubCommon::LogLevel,std::wstring,std::_Uhash_compare<enum DiagHubCommon::LogLevel,std::hash<enum DiagHubCommon::LogLevel>,std::equal_to<enum DiagHubCommon::LogLevel>>,std::allocator<std::pair<enum DiagHubCommon::LogLevel const,std::wstring>>,0>>::_Try_emplace<enum DiagHubCommon::LogLevel,>(
                    &dword_180077A50,
                    &v55,
                    &Type);
  v43 = std::wstring::wstring(v83, *v42 + 24LL);
  std::vector<std::shared_ptr<DiagHubCommon::ILogWriter>>::vector<std::shared_ptr<DiagHubCommon::ILogWriter>>(v73, v41);
  std::wstring::wstring(v74, v43);
  std::wstring::~wstring(v43);
  std::vector<std::shared_ptr<Microsoft::Json::Object>>::~vector<std::shared_ptr<Microsoft::Json::Object>>(v41);
  v63 = v75;
  v44 = std::vector<std::shared_ptr<DiagHubCommon::ILogWriter>>::vector<std::shared_ptr<DiagHubCommon::ILogWriter>>(
          v69,
          &v99);
  v64 = (_BYTE *)v44;
  cbData = 4;
  v45 = (_QWORD *)std::_Hash<std::_Umap_traits<enum DiagHubCommon::LogLevel,std::wstring,std::_Uhash_compare<enum DiagHubCommon::LogLevel,std::hash<enum DiagHubCommon::LogLevel>,std::equal_to<enum DiagHubCommon::LogLevel>>,std::allocator<std::pair<enum DiagHubCommon::LogLevel const,std::wstring>>,0>>::_Try_emplace<enum DiagHubCommon::LogLevel,>(
                    &dword_180077A50,
                    &v55,
                    &cbData);
  v46 = std::wstring::wstring(v84, *v45 + 24LL);
  std::vector<std::shared_ptr<DiagHubCommon::ILogWriter>>::vector<std::shared_ptr<DiagHubCommon::ILogWriter>>(v75, v44);
  std::wstring::wstring(v76, v46);
  std::wstring::~wstring(v46);
  std::vector<std::shared_ptr<Microsoft::Json::Object>>::~vector<std::shared_ptr<Microsoft::Json::Object>>(v44);
  v64 = v77;
  v47 = std::vector<std::shared_ptr<DiagHubCommon::ILogWriter>>::vector<std::shared_ptr<DiagHubCommon::ILogWriter>>(
          v70,
          &v101);
  *(_QWORD *)&v58 = v47;
  v60 = 2;
  v48 = (_QWORD *)std::_Hash<std::_Umap_traits<enum DiagHubCommon::LogLevel,std::wstring,std::_Uhash_compare<enum DiagHubCommon::LogLevel,std::hash<enum DiagHubCommon::LogLevel>,std::equal_to<enum DiagHubCommon::LogLevel>>,std::allocator<std::pair<enum DiagHubCommon::LogLevel const,std::wstring>>,0>>::_Try_emplace<enum DiagHubCommon::LogLevel,>(
                    &dword_180077A50,
                    &v55,
                    &v60);
  v49 = std::wstring::wstring(v85, *v48 + 24LL);
  std::vector<std::shared_ptr<DiagHubCommon::ILogWriter>>::vector<std::shared_ptr<DiagHubCommon::ILogWriter>>(v77, v47);
  std::wstring::wstring(v78, v49);
  std::wstring::~wstring(v49);
  std::vector<std::shared_ptr<Microsoft::Json::Object>>::~vector<std::shared_ptr<Microsoft::Json::Object>>(v47);
  *(_QWORD *)&v58 = v79;
  v50 = std::vector<std::shared_ptr<DiagHubCommon::ILogWriter>>::vector<std::shared_ptr<DiagHubCommon::ILogWriter>>(
          v61,
          &v103);
  v55 = (char *)v50;
  LODWORD(v57) = 1;
  v51 = (_QWORD *)std::_Hash<std::_Umap_traits<enum DiagHubCommon::LogLevel,std::wstring,std::_Uhash_compare<enum DiagHubCommon::LogLevel,std::hash<enum DiagHubCommon::LogLevel>,std::equal_to<enum DiagHubCommon::LogLevel>>,std::allocator<std::pair<enum DiagHubCommon::LogLevel const,std::wstring>>,0>>::_Try_emplace<enum DiagHubCommon::LogLevel,>(
                    &dword_180077A50,
                    v81,
                    &v57);
  v54 = std::wstring::wstring(Str, *v51 + 24LL);
  std::vector<std::shared_ptr<DiagHubCommon::ILogWriter>>::vector<std::shared_ptr<DiagHubCommon::ILogWriter>>(v79, v50);
  std::wstring::wstring(v80, v54);
  std::wstring::~wstring(v54);
  std::vector<std::shared_ptr<Microsoft::Json::Object>>::~vector<std::shared_ptr<Microsoft::Json::Object>>(v50);
  v52 = (DiagHubCommon::Logger *)DiagHubCommon::Logger::Logger(v37, v79, v77, v75, v73, v71);
  v53 = Block;
  Block = v52;
  if ( v53 )
  {
    DiagHubCommon::Logger::~Logger(v53);
    operator delete(v53);
    v52 = Block;
  }
  std::vector<std::shared_ptr<Microsoft::Json::Object>>::~vector<std::shared_ptr<Microsoft::Json::Object>>(&v105);
  std::vector<std::shared_ptr<Microsoft::Json::Object>>::~vector<std::shared_ptr<Microsoft::Json::Object>>(&v97);
  std::vector<std::shared_ptr<Microsoft::Json::Object>>::~vector<std::shared_ptr<Microsoft::Json::Object>>(&v99);
  std::vector<std::shared_ptr<Microsoft::Json::Object>>::~vector<std::shared_ptr<Microsoft::Json::Object>>(&v101);
  std::vector<std::shared_ptr<Microsoft::Json::Object>>::~vector<std::shared_ptr<Microsoft::Json::Object>>(&v103);
  if ( hKey_8[0] )
    RegCloseKey(hKey_8[0]);
  std::vector<std::shared_ptr<Microsoft::Json::Object>>::~vector<std::shared_ptr<Microsoft::Json::Object>>(&v87);
  return v52;
}

```

## disassembly

```asm
0x18003da40  mov     rax, rsp
0x18003da43  mov     [rax+8], rbx
0x18003da47  mov     [rax+10h], rsi
0x18003da4b  mov     [rax+18h], rdi
0x18003da4f  push    rbp
0x18003da50  push    r12
0x18003da52  push    r13
0x18003da54  push    r14
0x18003da56  push    r15
0x18003da58  lea     rbp, [rax-628h]
0x18003da5f  sub     rsp, 700h
0x18003da66  mov     rax, cs:__security_cookie
0x18003da6d  xor     rax, rsp
0x18003da70  mov     [rbp+620h+var_30], rax
0x18003da77  xor     r12d, r12d
0x18003da7a  mov     [rbp+620h+Type], r12d
0x18003da81  mov     ecx, cs:_tls_index
0x18003da87  mov     rax, gs:58h
0x18003da90  mov     edi, 4
0x18003da95  mov     rbx, [rax+rcx*8]
0x18003da99  or      r13d, 0FFFFFFFFh
0x18003da9d  mov     eax, [rbx+rdi]
0x18003daa0  cmp     cs:dword_180077A40, eax
0x18003daa6  jle     short loc_18003DAD5
0x18003daa8  lea     rcx, dword_180077A40
0x18003daaf  call    _Init_thread_header
0x18003dab4  cmp     cs:dword_180077A40, r13d
0x18003dabb  jnz     short loc_18003DAD5
0x18003dabd  lea     rcx, _DiagHubCommon__Logger__GetLogger____2____dynamic_atexit_destructor_for__loggerInstance__; void (__cdecl *)()
0x18003dac4  call    atexit
0x18003dac9  lea     rcx, dword_180077A40
0x18003dad0  call    _Init_thread_footer
0x18003dad5  mov     eax, [rbx+rdi]
0x18003dad8  cmp     cs:dword_180077A44, eax
0x18003dade  jle     short loc_18003DB25
0x18003dae0  lea     rcx, dword_180077A44
0x18003dae7  call    _Init_thread_header
0x18003daec  cmp     cs:dword_180077A44, r13d
0x18003daf3  jnz     short loc_18003DB25
0x18003daf5  xor     edx, edx; Val
0x18003daf7  lea     r8d, [rdx+40h]; Size
0x18003dafb  lea     rcx, dword_180077A50; void *
0x18003db02  call    memset_0
0x18003db07  call    ??0LogLevelMapFactory@Logger@DiagHubCommon@@QEAA@XZ; DiagHubCommon::Logger::LogLevelMapFactory::LogLevelMapFactory(void)
0x18003db0c  lea     rcx, _DiagHubCommon__Logger__GetLogger____2____dynamic_atexit_destructor_for__logLevelMapFactory__; void (__cdecl *)()
0x18003db13  call    atexit
0x18003db18  nop
0x18003db19  lea     rcx, dword_180077A44
0x18003db20  call    _Init_thread_footer
0x18003db25  mov     rax, cs:Block
0x18003db2c  test    rax, rax
0x18003db2f  jnz     loc_18003E841
0x18003db35  mov     esi, r12d
0x18003db38  xorps   xmm1, xmm1
0x18003db3b  movdqu  [rbp+620h+var_448], xmm1
0x18003db43  mov     [rbp+620h+var_438], r12
0x18003db4a  lea     ecx, [rax+18h]; Size
0x18003db4d  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18003db52  mov     qword ptr [rsp+720h+var_6D8], rax
0x18003db57  xorps   xmm0, xmm0
0x18003db5a  movups  xmmword ptr [rax], xmm0
0x18003db5d  mov     r14d, 1
0x18003db63  mov     [rax+8], r14d
0x18003db67  mov     [rax+0Ch], r14d
0x18003db6b  lea     rcx, ??_7?$_Ref_count_obj2@VDebugStringLogWriter@DiagHubCommon@@@std@@6B@; const std::_Ref_count_obj2<DiagHubCommon::DebugStringLogWriter>::`vftable'
0x18003db72  mov     [rax], rcx
0x18003db75  lea     rcx, [rax+10h]
0x18003db79  lea     rdx, ??_7DebugStringLogWriter@DiagHubCommon@@6B@; const DiagHubCommon::DebugStringLogWriter::`vftable'
0x18003db80  mov     [rcx], rdx
0x18003db83  mov     r15d, r14d
0x18003db86  mov     [rsp+720h+var_6E8], rcx
0x18003db8b  mov     [rsp+720h+var_6E0], rax
0x18003db90  movdqu  [rsp+720h+var_6D8+8], xmm0
0x18003db96  mov     rdx, qword ptr [rbp+620h+var_448+8]
0x18003db9d  cmp     rdx, [rbp+620h+var_438]
0x18003dba4  jz      short loc_18003DBBA
0x18003dba6  mov     [rdx], rcx
0x18003dba9  mov     [rdx+8], rax
0x18003dbad  mov     rbx, r12
0x18003dbb0  add     qword ptr [rbp+620h+var_448+8], 10h
0x18003dbb8  jmp     short loc_18003DBD0
0x18003dbba  lea     r8, [rsp+720h+var_6E8]
0x18003dbbf  lea     rcx, [rbp+620h+var_448]
0x18003dbc6  call    ??$_Emplace_reallocate@V?$shared_ptr@VILogWriter@DiagHubCommon@@@std@@@?$vector@V?$shared_ptr@VILogWriter@DiagHubCommon@@@std@@V?$allocator@V?$shared_ptr@VILogWriter@DiagHubCommon@@@std@@@2@@std@@AEAAPEAV?$shared_ptr@VILogWriter@DiagHubCommon@@@1@QEAV21@$$QEAV21@@Z; std::vector<std::shared_ptr<DiagHubCommon::ILogWriter>>::_Emplace_reallocate<std::shared_ptr<DiagHubCommon::ILogWriter>>(std::shared_ptr<DiagHubCommon::ILogWriter> * const,std::shared_ptr<DiagHubCommon::ILogWriter> &&)
0x18003dbcb  mov     rbx, [rsp+720h+var_6E0]
0x18003dbd0  test    rbx, rbx
0x18003dbd3  jz      short loc_18003DC0F
0x18003dbd5  mov     eax, r13d
0x18003dbd8  lock xadd [rbx+8], eax
0x18003dbdd  add     eax, r13d
0x18003dbe0  jnz     short loc_18003DC0F
0x18003dbe2  mov     rax, [rbx]
0x18003dbe5  mov     rcx, rbx
0x18003dbe8  mov     rax, [rax]
0x18003dbeb  call    cs:__guard_dispatch_icall_fptr
0x18003dbf1  mov     eax, r13d
0x18003dbf4  lock xadd [rbx+0Ch], eax
0x18003dbf9  add     eax, r13d
0x18003dbfc  jnz     short loc_18003DC0F
0x18003dbfe  mov     rax, [rbx]
0x18003dc01  mov     rcx, rbx
0x18003dc04  mov     rax, [rax+8]
0x18003dc08  call    cs:__guard_dispatch_icall_fptr
0x18003dc0e  nop
0x18003dc0f  xorps   xmm0, xmm0
0x18003dc12  movups  xmmword ptr [rsp+720h+hKey+8], xmm0
0x18003dc17  mov     [rsp+720h+hKey+8], r12
0x18003dc1c  mov     dword ptr [rsp+720h+var_6B8], r12d
0x18003dc21  mov     qword ptr [rsp+720h+var_6B0], r12
0x18003dc26  lea     r8, aSoftwareMicros_1; "Software\\Microsoft\\VisualStudio\\Diag"...
0x18003dc2d  lea     rcx, [rsp+720h+hKey+8]; this
0x18003dc32  call    ?Open@CRegKey@ATL@@QEAAJPEAUHKEY__@@PEBGK@Z; ATL::CRegKey::Open(HKEY__ *,ushort const *,ulong)
0x18003dc37  test    eax, eax
0x18003dc39  jnz     loc_18003E365
0x18003dc3f  mov     [rbp+620h+cbData], 105h
0x18003dc49  lea     r9, [rbp+620h+cbData]; unsigned int *
0x18003dc50  lea     r8, [rbp+620h+String]; unsigned __int16 *
0x18003dc57  lea     rdx, aLoglevel; "LogLevel"
0x18003dc5e  lea     rcx, [rsp+720h+hKey+8]; this
0x18003dc63  call    ?QueryStringValue@CRegKey@ATL@@QEAAJPEBGPEAGPEAK@Z; ATL::CRegKey::QueryStringValue(ushort const *,ushort *,ulong *)
0x18003dc68  test    eax, eax
0x18003dc6a  jnz     loc_18003DD08
0x18003dc70  mov     rdi, cs:qword_180077A58
0x18003dc77  mov     rbx, [rdi]
0x18003dc7a  cmp     rbx, rdi
0x18003dc7d  jz      loc_18003DD08
0x18003dc83  mov     eax, [rbx+10h]
0x18003dc86  mov     [rbp+620h+var_360], eax
0x18003dc8c  lea     rdx, [rbx+18h]
0x18003dc90  lea     rcx, [rbp+620h+var_358]
0x18003dc97  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x18003dc9c  lea     rcx, [rbp+620h+String]; String
0x18003dca3  call    cs:__imp_wcslen
0x18003dca9  lea     rdx, [rbp+620h+var_358]
0x18003dcb0  cmp     [rbp+620h+var_340], 7
0x18003dcb8  cmova   rdx, [rbp+620h+var_358]
0x18003dcc0  mov     rcx, [rbp+620h+var_348]
0x18003dcc7  cmp     rcx, rax
0x18003dcca  jnz     loc_18003DE07
0x18003dcd0  test    rcx, rcx
0x18003dcd3  jz      short loc_18003DCF6
0x18003dcd5  lea     r8, [rbp+620h+String]
0x18003dcdc  movzx   eax, word ptr [r8]
0x18003dce0  cmp     [rdx], ax
0x18003dce3  jnz     loc_18003DE07
0x18003dce9  add     rdx, 2
0x18003dced  add     r8, 2
0x18003dcf1  sub     rcx, r14
0x18003dcf4  jnz     short loc_18003DCDC
0x18003dcf6  mov     esi, [rbp+620h+var_360]
0x18003dcfc  lea     rcx, [rbp+620h+var_358]
0x18003dd03  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18003dd08  mov     [rbp+620h+cbData], 4
0x18003dd12  lea     rax, [rbp+620h+cbData]
0x18003dd19  mov     [rsp+720h+lpcbData], rax; lpcbData
0x18003dd1e  lea     rax, [rbp+620h+Data]
0x18003dd25  mov     [rsp+720h+lpData], rax; lpData
0x18003dd2a  lea     r9, [rbp+620h+Type]; lpType
0x18003dd31  xor     r8d, r8d; lpReserved
0x18003dd34  lea     rdx, aEtwlogging; "EtwLogging"
0x18003dd3b  mov     rcx, [rsp+720h+hKey+8]; hKey
0x18003dd40  call    cs:__imp_RegQueryValueExW
0x18003dd46  test    eax, eax
0x18003dd48  jnz     loc_18003DE82
0x18003dd4e  cmp     [rbp+620h+Type], 4
0x18003dd55  jnz     loc_18003DE82
0x18003dd5b  cmp     dword ptr [rbp+620h+Data], r14d
0x18003dd62  jnz     loc_18003DE82
0x18003dd68  lea     ecx, [rax+20h]; Size
0x18003dd6b  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18003dd70  mov     rdi, rax
0x18003dd73  mov     qword ptr [rsp+720h+var_6D8], rax
0x18003dd78  xorps   xmm0, xmm0
0x18003dd7b  movups  xmmword ptr [rax], xmm0
0x18003dd7e  mov     [rax+8], r14d
0x18003dd82  mov     [rax+0Ch], r14d
0x18003dd86  lea     rax, ??_7?$_Ref_count_obj2@VEtlLogWriter@DiagHubCommon@@@std@@6B@; const std::_Ref_count_obj2<DiagHubCommon::EtlLogWriter>::`vftable'
0x18003dd8d  mov     [rdi], rax
0x18003dd90  lea     r14, [rdi+10h]
0x18003dd94  lea     rax, ??_7EtlLogWriter@DiagHubCommon@@6B@; const DiagHubCommon::EtlLogWriter::`vftable'
0x18003dd9b  mov     [r14], rax
0x18003dd9e  lea     r9, [r14+8]; RegHandle
0x18003dda2  xor     r8d, r8d; CallbackContext
0x18003dda5  xor     edx, edx; EnableCallback
0x18003dda7  lea     rcx, ?providerGuid@EtlLogWriter@DiagHubCommon@@0U_GUID@@B; ProviderId
0x18003ddae  call    cs:__imp_EventRegister
0x18003ddb4  lea     r9, aDiagnosticsHub; "============= Diagnostics Hub Log ====="...
0x18003ddbb  xor     r8d, r8d; Keyword
0x18003ddbe  xor     edx, edx; Level
0x18003ddc0  mov     rcx, [r14+8]; RegHandle
0x18003ddc4  call    cs:__imp_EventWriteString
0x18003ddca  xorps   xmm0, xmm0
0x18003ddcd  mov     r15d, 3
0x18003ddd3  mov     [rsp+720h+var_6E8], r14
0x18003ddd8  mov     [rsp+720h+var_6E0], rdi
0x18003dddd  movdqu  [rsp+720h+var_6D8+8], xmm0
0x18003dde3  mov     rdx, qword ptr [rbp+620h+var_448+8]
0x18003ddea  cmp     rdx, [rbp+620h+var_438]
0x18003ddf1  jz      short loc_18003DE27
0x18003ddf3  mov     [rdx], r14
0x18003ddf6  mov     [rdx+8], rdi
0x18003ddfa  mov     rbx, r12
0x18003ddfd  add     qword ptr [rbp+620h+var_448+8], 10h
0x18003de05  jmp     short loc_18003DE3D
0x18003de07  lea     rcx, [rbp+620h+var_358]
0x18003de0e  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18003de13  mov     rax, [rbx]
0x18003de16  mov     rbx, rax
0x18003de19  cmp     rax, rdi
0x18003de1c  jnz     loc_18003DC83
0x18003de22  jmp     loc_18003DD08
0x18003de27  lea     r8, [rsp+720h+var_6E8]
0x18003de2c  lea     rcx, [rbp+620h+var_448]
0x18003de33  call    ??$_Emplace_reallocate@V?$shared_ptr@VILogWriter@DiagHubCommon@@@std@@@?$vector@V?$shared_ptr@VILogWriter@DiagHubCommon@@@std@@V?$allocator@V?$shared_ptr@VILogWriter@DiagHubCommon@@@std@@@2@@std@@AEAAPEAV?$shared_ptr@VILogWriter@DiagHubCommon@@@1@QEAV21@$$QEAV21@@Z; std::vector<std::shared_ptr<DiagHubCommon::ILogWriter>>::_Emplace_reallocate<std::shared_ptr<DiagHubCommon::ILogWriter>>(std::shared_ptr<DiagHubCommon::ILogWriter> * const,std::shared_ptr<DiagHubCommon::ILogWriter> &&)
0x18003de38  mov     rbx, [rsp+720h+var_6E0]
0x18003de3d  test    rbx, rbx
0x18003de40  jz      short loc_18003DE7C
0x18003de42  mov     eax, r13d
0x18003de45  lock xadd [rbx+8], eax
0x18003de4a  add     eax, r13d
0x18003de4d  jnz     short loc_18003DE7C
0x18003de4f  mov     rax, [rbx]
0x18003de52  mov     rcx, rbx
0x18003de55  mov     rax, [rax]
0x18003de58  call    cs:__guard_dispatch_icall_fptr
0x18003de5e  mov     eax, r13d
0x18003de61  lock xadd [rbx+0Ch], eax
0x18003de66  add     eax, r13d
0x18003de69  jnz     short loc_18003DE7C
0x18003de6b  mov     rax, [rbx]
0x18003de6e  mov     rcx, rbx
0x18003de71  mov     rax, [rax+8]
0x18003de75  call    cs:__guard_dispatch_icall_fptr
0x18003de7b  nop
0x18003de7c  mov     r14d, 1
0x18003de82  mov     [rbp+620h+cbData], 105h
0x18003de8c  lea     r9, [rbp+620h+cbData]; unsigned int *
0x18003de93  lea     r8, [rbp+620h+String]; unsigned __int16 *
0x18003de9a  lea     rdx, aLogdirectory; "LogDirectory"
0x18003dea1  lea     rcx, [rsp+720h+hKey+8]; this
0x18003dea6  call    ?QueryStringValue@CRegKey@ATL@@QEAAJPEBGPEAGPEAK@Z; ATL::CRegKey::QueryStringValue(ushort const *,ushort *,ulong *)
0x18003deab  test    eax, eax
0x18003dead  jnz     loc_18003E365
0x18003deb3  cmp     [rbp+620h+cbData], r14d
0x18003deba  jbe     loc_18003E365
0x18003dec0  xorps   xmm0, xmm0
0x18003dec3  movups  xmmword ptr [rbp+620h+lpFileName], xmm0
0x18003deca  mov     [rbp+620h+var_418], r12
0x18003ded1  mov     [rbp+620h+var_410], r12
0x18003ded8  lea     rcx, [rbp+620h+String]; String
0x18003dedf  call    cs:__imp_wcslen
0x18003dee5  mov     r8, rax
0x18003dee8  lea     rdx, [rbp+620h+String]
0x18003deef  lea     rcx, [rbp+620h+lpFileName]
0x18003def6  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x18003defb  nop
0x18003defc  lea     rcx, [rbp+620h+lpFileName]
0x18003df03  mov     rdx, [rbp+620h+lpFileName]
0x18003df0a  mov     r8, [rbp+620h+var_410]
0x18003df11  cmp     r8, 7
0x18003df15  cmova   rcx, rdx
0x18003df19  mov     ebx, 5Ch ; '\'
0x18003df1e  mov     rax, [rbp+620h+var_418]
0x18003df25  cmp     [rcx+rax*2-2], bx
0x18003df2a  jz      short loc_18003DF4D
0x18003df2c  lea     rdx, asc_180055D1C; "\\"
0x18003df33  lea     rcx, [rbp+620h+lpFileName]; Src
0x18003df3a  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@QEBG@Z; std::wstring::append(ushort const * const)
0x18003df3f  mov     r8, [rbp+620h+var_410]
0x18003df46  mov     rdx, [rbp+620h+lpFileName]
0x18003df4d  lea     rcx, [rbp+620h+lpFileName]
0x18003df54  cmp     r8, 7
0x18003df58  cmova   rcx, rdx; lpFileName
0x18003df5c  call    cs:__imp_GetFileAttributesW
0x18003df62  cmp     eax, 0FFFFFFFFh
0x18003df65  jz      loc_18003E359
0x18003df6b  test    al, 10h
0x18003df6d  jz      loc_18003E359
0x18003df73  xorps   xmm0, xmm0
0x18003df76  movdqu  xmmword ptr [rbp+620h+Str], xmm0
0x18003df7e  xorps   xmm1, xmm1
0x18003df81  movdqu  [rbp+620h+var_3F8], xmm1
0x18003df89  mov     [rbp+620h+var_3E8], r12
0x18003df90  lea     rdx, [rbp+620h+Str]
0x18003df97  xor     ecx, ecx; hModule
0x18003df99  call    ?GetModulePath@ModulePath@DiagHubCommon@@SAJPEAUHINSTANCE__@@AEAV?$vector@GV?$allocator@G@std@@@std@@@Z; DiagHubCommon::ModulePath::GetModulePath(HINSTANCE__ *,std::vector<ushort> &)
0x18003df9e  mov     edi, 800700A1h
0x18003dfa3  test    eax, eax
0x18003dfa5  js      short loc_18003DFE4
0x18003dfa7  mov     edx, ebx; Ch
0x18003dfa9  mov     rcx, [rbp+620h+Str]; Str
0x18003dfb0  call    cs:__imp_wcsrchr
0x18003dfb6  mov     rcx, rax
0x18003dfb9  test    rax, rax
0x18003dfbc  jnz     short loc_18003DFC2
0x18003dfbe  mov     eax, edi
0x18003dfc0  jmp     short loc_18003DFE2
0x18003dfc2  mov     [rax], r12w
0x18003dfc6  mov     rax, [rbp+620h+Str]
0x18003dfcd  mov     qword ptr [rbp+620h+var_3F8+8], rax
  ... truncated ...
```
