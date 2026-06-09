# DiagHubCommon::Logger::GetLogger(void)

- ea: `0x14000a42c`
- end: `0x14000b24e`
- name: `?GetLogger@Logger@DiagHubCommon@@SAAEAV12@XZ`
- size: `3618`
- prototype: `struct DiagHubCommon::Logger *(void)`
- caller_count: `5`
- callee_count: `30`
- tags: `file_ops, authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x140001100`
- `0x140001388`
- `0x140005760`
- `0x14000f510`
- `0x140010fc0`

## callees

- `0x140003010`
- `0x140003088`
- `0x140003220`
- `0x1400043a0`
- `0x14000993c`
- `0x140009ce4`
- `0x14000a298`
- `0x14000a42c`
- `0x14000b2cc`
- `0x14000b824`
- `0x14000b8fc`
- `0x14000b990`
- `0x14000ca88`
- `0x14000cf14`
- `0x14000d104`
- `0x14000d484`
- `0x14000d69c`
- `0x14000d7fc`
- `0x14000da28`
- `0x14000e54c`
- `0x14000e5d4`
- `0x1400108a8`
- `0x1400137e0`
- `0x14001382c`
- `0x140013834`
- `0x1400138ac`
- `0x140013918`
- `0x140013bbc`
- `0x14001473e`
- `0x140014c70`

## import_xrefs

- `VCRUNTIME140!wcsrchr` at `0x14000a981`
- `VCRUNTIME140!wcsrchr` at `0x14000aa53`
- `VCRUNTIME140!wcsrchr` at `0x14000a981`
- `VCRUNTIME140!wcsrchr` at `0x14000aa53`
- `KERNEL32!GetFileAttributesW` at `0x14000a92d`
- `KERNEL32!GetFileAttributesW` at `0x14000a92d`
- `KERNEL32!GetCurrentProcessId` at `0x14000aba3`
- `KERNEL32!GetCurrentProcessId` at `0x14000aba3`
- `MSVCP140!??1?$basic_ostream@GU?$char_traits@G@std@@@std@@UEAA@XZ` at `0x14000ad11`
- `MSVCP140!??1?$basic_ostream@GU?$char_traits@G@std@@@std@@UEAA@XZ` at `0x14000ad11`
- `MSVCP140!??1?$basic_ios@GU?$char_traits@G@std@@@std@@UEAA@XZ` at `0x14000ad1e`
- `MSVCP140!??1?$basic_ios@GU?$char_traits@G@std@@@std@@UEAA@XZ` at `0x14000ad1e`
- `MSVCP140!??0?$basic_streambuf@GU?$char_traits@G@std@@@std@@IEAA@XZ` at `0x14000ab7e`
- `MSVCP140!??0?$basic_streambuf@GU?$char_traits@G@std@@@std@@IEAA@XZ` at `0x14000ab7e`
- `MSVCP140!??0?$basic_ios@GU?$char_traits@G@std@@@std@@IEAA@XZ` at `0x14000ab18`
- `MSVCP140!??0?$basic_ios@GU?$char_traits@G@std@@@std@@IEAA@XZ` at `0x14000ab18`
- `MSVCP140!??0?$basic_ostream@GU?$char_traits@G@std@@@std@@QEAA@PEAV?$basic_streambuf@GU?$char_traits@G@std@@@1@_N@Z` at `0x14000ab3e`
- `MSVCP140!??0?$basic_ostream@GU?$char_traits@G@std@@@std@@QEAA@PEAV?$basic_streambuf@GU?$char_traits@G@std@@@1@_N@Z` at `0x14000ab3e`
- `MSVCP140!??6?$basic_ostream@GU?$char_traits@G@std@@@std@@QEAAAEAV01@K@Z` at `0x14000abb2`
- `MSVCP140!??6?$basic_ostream@GU?$char_traits@G@std@@@std@@QEAAAEAV01@K@Z` at `0x14000abb2`
- `ADVAPI32!EventWriteString` at `0x14000a794`
- `ADVAPI32!EventWriteString` at `0x14000a794`
- `ADVAPI32!EventRegister` at `0x14000a77e`
- `ADVAPI32!EventRegister` at `0x14000a77e`
- `ADVAPI32!RegQueryValueExW` at `0x14000a710`
- `ADVAPI32!RegQueryValueExW` at `0x14000a710`
- `ADVAPI32!RegCloseKey` at `0x14000b208`
- `ADVAPI32!RegCloseKey` at `0x14000b208`

## string_xrefs

- `0x14000a867`: `LogDirectory`

## pseudocode

```c
// Hidden C++ exception states: #wind=47
struct DiagHubCommon::Logger *DiagHubCommon::Logger::GetLogger(void)
{
  __int64 *ThreadLocalStoragePointer; // rax
  __int64 v1; // rbx
  DiagHubCommon::Logger::LogLevelMapFactory *v2; // rcx
  struct DiagHubCommon::Logger *result; // rax
  char v4; // si
  _DWORD *v5; // rax
  int v6; // r15d
  HKEY v7; // rdx
  volatile signed __int32 *v8; // rbx
  __int64 v9; // rdi
  __int64 *v10; // rbx
  __int64 v11; // rax
  _WORD *v12; // rdx
  __int64 v13; // rcx
  unsigned __int16 *v14; // r8
  char *v15; // rdi
  __int64 v16; // rdx
  volatile signed __int32 *v17; // rbx
  __int64 v18; // r8
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
  int v65; // [rsp+C0h] [rbp-48h]
  _QWORD v66[2]; // [rsp+C8h] [rbp-40h] BYREF
  __int64 v67; // [rsp+D8h] [rbp-30h]
  unsigned __int64 v68; // [rsp+E0h] [rbp-28h]
  void *v69; // [rsp+E8h] [rbp-20h]
  _BYTE *v70; // [rsp+F0h] [rbp-18h]
  _BYTE v71[24]; // [rsp+F8h] [rbp-10h] BYREF
  _BYTE v72[24]; // [rsp+110h] [rbp+8h] BYREF
  _BYTE v73[24]; // [rsp+128h] [rbp+20h] BYREF
  _BYTE v74[24]; // [rsp+140h] [rbp+38h] BYREF
  _BYTE v75[24]; // [rsp+158h] [rbp+50h] BYREF
  _BYTE v76[32]; // [rsp+170h] [rbp+68h] BYREF
  _BYTE v77[24]; // [rsp+190h] [rbp+88h] BYREF
  _BYTE v78[32]; // [rsp+1A8h] [rbp+A0h] BYREF
  _BYTE v79[24]; // [rsp+1C8h] [rbp+C0h] BYREF
  _BYTE v80[32]; // [rsp+1E0h] [rbp+D8h] BYREF
  _BYTE v81[24]; // [rsp+200h] [rbp+F8h] BYREF
  _BYTE v82[32]; // [rsp+218h] [rbp+110h] BYREF
  _BYTE v83[24]; // [rsp+238h] [rbp+130h] BYREF
  _BYTE v84[32]; // [rsp+250h] [rbp+148h] BYREF
  _BYTE v85[32]; // [rsp+270h] [rbp+168h] BYREF
  _BYTE v86[32]; // [rsp+290h] [rbp+188h] BYREF
  _BYTE v87[32]; // [rsp+2B0h] [rbp+1A8h] BYREF
  _BYTE v88[32]; // [rsp+2D0h] [rbp+1C8h] BYREF
  _BYTE v89[16]; // [rsp+2F0h] [rbp+1E8h] BYREF
  __int128 v90; // [rsp+300h] [rbp+1F8h] BYREF
  __int64 v91; // [rsp+310h] [rbp+208h]
  DWORD cbData; // [rsp+318h] [rbp+210h] BYREF
  DWORD Type; // [rsp+320h] [rbp+218h] BYREF
  LPCWSTR lpFileName[2]; // [rsp+328h] [rbp+220h] BYREF
  __int64 v95; // [rsp+338h] [rbp+230h]
  unsigned __int64 v96; // [rsp+340h] [rbp+238h]
  wchar_t *Str[2]; // [rsp+348h] [rbp+240h] BYREF
  __int128 v98; // [rsp+358h] [rbp+250h]
  wchar_t *v99; // [rsp+368h] [rbp+260h]
  BYTE Data[8]; // [rsp+370h] [rbp+268h] BYREF
  __int128 v101; // [rsp+378h] [rbp+270h] BYREF
  __int64 v102; // [rsp+388h] [rbp+280h]
  __int128 v103; // [rsp+390h] [rbp+288h] BYREF
  __int64 v104; // [rsp+3A0h] [rbp+298h]
  __int128 v105; // [rsp+3A8h] [rbp+2A0h] BYREF
  __int64 v106; // [rsp+3B8h] [rbp+2B0h]
  __int128 v107; // [rsp+3C0h] [rbp+2B8h] BYREF
  __int64 v108; // [rsp+3D0h] [rbp+2C8h]
  __int128 v109; // [rsp+3D8h] [rbp+2D0h] BYREF
  __int64 v110; // [rsp+3E8h] [rbp+2E0h]
  int v111; // [rsp+3F4h] [rbp+2ECh]
  __int64 *v112; // [rsp+3F8h] [rbp+2F0h] BYREF
  void **v113; // [rsp+400h] [rbp+2F8h] BYREF
  _BYTE v114[96]; // [rsp+408h] [rbp+300h] BYREF
  __int64 v115; // [rsp+468h] [rbp+360h]
  int v116; // [rsp+470h] [rbp+368h]
  _BYTE v117[104]; // [rsp+480h] [rbp+378h] BYREF
  unsigned __int16 v118[264]; // [rsp+4E8h] [rbp+3E0h] BYREF

  Type = 0;
  ThreadLocalStoragePointer = (__int64 *)NtCurrentTeb()->ThreadLocalStoragePointer;
  v1 = *ThreadLocalStoragePointer;
  if ( dword_140024B50 > *(_DWORD *)(*ThreadLocalStoragePointer + 4) )
  {
    Init_thread_header(&dword_140024B50);
    if ( dword_140024B50 == -1 )
    {
      atexit(DiagHubCommon::Logger::GetLogger_::_2_::_dynamic_atexit_destructor_for__loggerInstance__);
      Init_thread_footer(&dword_140024B50);
    }
  }
  if ( dword_140024B54 > *(_DWORD *)(v1 + 4) )
  {
    Init_thread_header(&dword_140024B54);
    if ( dword_140024B54 == -1 )
    {
      memset_0(&dword_140024B60, 0, 0x40u);
      DiagHubCommon::Logger::LogLevelMapFactory::LogLevelMapFactory(v2);
      atexit(DiagHubCommon::Logger::GetLogger_::_2_::_dynamic_atexit_destructor_for__logLevelMapFactory__);
      Init_thread_footer(&dword_140024B54);
    }
  }
  result = Block;
  if ( Block )
    return result;
  v4 = 0;
  v90 = 0;
  v91 = 0;
  v5 = operator new(0x18u);
  v57 = v5;
  *(_OWORD *)v5 = 0;
  v5[2] = 1;
  v5[3] = 1;
  *(_QWORD *)v5 = &std::_Ref_count_obj2<DiagHubCommon::DebugStringLogWriter>::`vftable';
  *((_QWORD *)v5 + 2) = &DiagHubCommon::DebugStringLogWriter::`vftable';
  v6 = 1;
  v55 = (char *)(v5 + 4);
  v56 = v5;
  v58 = 0;
  v7 = (HKEY)*((_QWORD *)&v90 + 1);
  if ( *((_QWORD *)&v90 + 1) == v91 )
  {
    std::vector<std::shared_ptr<DiagHubCommon::ILogWriter>>::_Emplace_reallocate<std::shared_ptr<DiagHubCommon::ILogWriter>>(
      &v90,
      *((_QWORD *)&v90 + 1),
      &v55);
    v8 = v56;
  }
  else
  {
    **((_QWORD **)&v90 + 1) = v5 + 4;
    *((_QWORD *)v7 + 1) = v5;
    v8 = 0;
    *((_QWORD *)&v90 + 1) += 16LL;
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
  if ( (unsigned int)ATL::CRegKey::Open(
                       (ATL::CRegKey *)hKey_8,
                       v7,
                       L"Software\\Microsoft\\VisualStudio\\DiagnosticsHub") )
    goto LABEL_79;
  cbData = 261;
  if ( (unsigned int)ATL::CRegKey::QueryStringValue((ATL::CRegKey *)hKey_8, L"LogLevel", v118, &cbData) )
    goto LABEL_28;
  v9 = qword_140024B68;
  v10 = *(__int64 **)qword_140024B68;
  if ( *(_QWORD *)qword_140024B68 == qword_140024B68 )
    goto LABEL_28;
  while ( 1 )
  {
    v65 = *((_DWORD *)v10 + 4);
    std::wstring::wstring(v66, v10 + 3);
    v11 = -1;
    do
      ++v11;
    while ( v118[v11] );
    v12 = v66;
    if ( v68 > 7 )
      v12 = (_WORD *)v66[0];
    v13 = v67;
    if ( v67 == v11 )
      break;
LABEL_33:
    std::wstring::~wstring(v66);
    v10 = (__int64 *)*v10;
    if ( v10 == (__int64 *)v9 )
      goto LABEL_28;
  }
  if ( v67 )
  {
    v14 = v118;
    while ( *v12 == *v14 )
    {
      ++v12;
      ++v14;
      if ( !--v13 )
        goto LABEL_27;
    }
    goto LABEL_33;
  }
LABEL_27:
  v4 = v65;
  std::wstring::~wstring(v66);
LABEL_28:
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
    v16 = *((_QWORD *)&v90 + 1);
    if ( *((_QWORD *)&v90 + 1) == v91 )
    {
      std::vector<std::shared_ptr<DiagHubCommon::ILogWriter>>::_Emplace_reallocate<std::shared_ptr<DiagHubCommon::ILogWriter>>(
        &v90,
        *((_QWORD *)&v90 + 1),
        &v55);
      v17 = v56;
    }
    else
    {
      **((_QWORD **)&v90 + 1) = v15 + 16;
      *(_QWORD *)(v16 + 8) = v15;
      v17 = 0;
      *((_QWORD *)&v90 + 1) += 16LL;
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
  if ( !(unsigned int)ATL::CRegKey::QueryStringValue((ATL::CRegKey *)hKey_8, L"LogDirectory", v118, &cbData)
    && cbData > 1 )
  {
    *(_OWORD *)lpFileName = 0;
    v95 = 0;
    v96 = 0;
    v18 = -1;
    do
      ++v18;
    while ( v118[v18] );
    std::wstring::_Construct<1,unsigned short const *>(lpFileName, v118, v18);
    v19 = lpFileName;
    v20 = lpFileName[0];
    v21 = v96;
    if ( v96 > 7 )
      v19 = (LPCWSTR *)lpFileName[0];
    if ( *((_WORD *)v19 + v95 - 1) != 92 )
    {
      std::wstring::append(lpFileName, L"\\");
      v21 = v96;
      v20 = lpFileName[0];
    }
    v22 = lpFileName;
    if ( v21 > 7 )
      v22 = (LPCWSTR *)v20;
    FileAttributesW = GetFileAttributesW((LPCWSTR)v22);
    if ( FileAttributesW != -1 && (FileAttributesW & 0x10) != 0 )
    {
      *(_OWORD *)Str = 0;
      v98 = 0;
      v99 = 0;
      ModulePath = DiagHubCommon::ModulePath::GetModulePath(0);
      v25 = ModulePath == 0;
      if ( ModulePath >= 0 )
      {
        v26 = wcsrchr(Str[0], 0x5Cu);
        if ( v26 )
        {
          *v26 = 0;
          *((wchar_t **)&v98 + 1) = Str[0];
          v99 = v26 + 1;
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
      std::wstring::append(lpFileName, L".");
      std::vector<unsigned short>::~vector<unsigned short>(Str);
      *(_OWORD *)Str = 0;
      v98 = 0;
      v99 = 0;
      v28 = DiagHubCommon::ModulePath::GetModulePath((HMODULE)0x140000000LL);
      v29 = v28 == 0;
      if ( v28 >= 0 )
      {
        v30 = wcsrchr(Str[0], 0x5Cu);
        if ( v30 )
        {
          *v30 = 0;
          *((wchar_t **)&v98 + 1) = Str[0];
          v99 = v30 + 1;
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
      std::wstring::append(lpFileName, L".");
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
      if ( v96 > 7 )
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
      v35 = *((_QWORD *)&v90 + 1);
      if ( *((_QWORD *)&v90 + 1) == v91 )
      {
        std::vector<std::shared_ptr<DiagHubCommon::ILogWriter>>::_Emplace_reallocate<std::shared_ptr<DiagHubCommon::ILogWriter>>(
          &v90,
          *((_QWORD *)&v90 + 1),
          &v55);
        v36 = v56;
      }
      else
      {
        **((_QWORD **)&v90 + 1) = v34 + 4;
        *(_QWORD *)(v35 + 8) = v34;
        v36 = 0;
        *((_QWORD *)&v90 + 1) += 16LL;
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
LABEL_79:
  v105 = 0;
  v106 = 0;
  v103 = 0;
  v104 = 0;
  v101 = 0;
  v102 = 0;
  v109 = 0;
  v110 = 0;
  v107 = 0;
  v108 = 0;
  if ( (v4 & 1) != 0 )
    std::vector<std::shared_ptr<DiagHubCommon::ILogWriter>>::_Assign_counted_range<std::shared_ptr<DiagHubCommon::ILogWriter> *>(
      &v105,
      v90,
      (__int64)(*((_QWORD *)&v90 + 1) - v90) >> 4);
  if ( (v4 & 2) != 0 )
    std::vector<std::shared_ptr<DiagHubCommon::ILogWriter>>::_Assign_counted_range<std::shared_ptr<DiagHubCommon::ILogWriter> *>(
      &v103,
      v90,
      (__int64)(*((_QWORD *)&v90 + 1) - v90) >> 4);
  if ( (v4 & 4) != 0 )
    std::vector<std::shared_ptr<DiagHubCommon::ILogWriter>>::_Assign_counted_range<std::shared_ptr<DiagHubCommon::ILogWriter> *>(
      &v101,
      v90,
      (__int64)(*((_QWORD *)&v90 + 1) - v90) >> 4);
  if ( (v4 & 8) != 0 )
    std::vector<std::shared_ptr<DiagHubCommon::ILogWriter>>::_Assign_counted_range<std::shared_ptr<DiagHubCommon::ILogWriter> *>(
      &v109,
      v90,
      (__int64)(*((_QWORD *)&v90 + 1) - v90) >> 4);
  if ( (v4 & 0x10) != 0 )
    std::vector<std::shared_ptr<DiagHubCommon::ILogWriter>>::_Assign_counted_range<std::shared_ptr<DiagHubCommon::ILogWriter> *>(
      &v107,
      v90,
      (__int64)(*((_QWORD *)&v90 + 1) - v90) >> 4);
  v37 = operator new(0x118u);
  v69 = v37;
  memset_0(v37, 0, 0x118u);
  v70 = v77;
  v38 = std::vector<std::shared_ptr<DiagHubCommon::ILogWriter>>::vector<std::shared_ptr<DiagHubCommon::ILogWriter>>(
          v71,
          &v107);
  v62 = (_BYTE *)v38;
  *(_DWORD *)Data = 16;
  v39 = (_QWORD *)std::_Hash<std::_Umap_traits<enum DiagHubCommon::LogLevel,std::wstring,std::_Uhash_compare<enum DiagHubCommon::LogLevel,std::hash<enum DiagHubCommon::LogLevel>,std::equal_to<enum DiagHubCommon::LogLevel>>,std::allocator<std::pair<enum DiagHubCommon::LogLevel const,std::wstring>>,0>>::_Try_emplace<enum DiagHubCommon::LogLevel,>(
                    &dword_140024B60,
                    &v55,
                    Data);
  v40 = std::wstring::wstring(v85, *v39 + 24LL);
  std::vector<std::shared_ptr<DiagHubCommon::ILogWriter>>::vector<std::shared_ptr<DiagHubCommon::ILogWriter>>(v77, v38);
  std::wstring::wstring(v78, v40);
  std::wstring::~wstring(v40);
  std::vector<std::shared_ptr<DiagHubCommon::ILogWriter>>::_Tidy(v38);
  v62 = v79;
  v41 = std::vector<std::shared_ptr<DiagHubCommon::ILogWriter>>::vector<std::shared_ptr<DiagHubCommon::ILogWriter>>(
          v74,
          &v109);
  v63 = (_BYTE *)v41;
  Type = 8;
  v42 = (_QWORD *)std::_Hash<std::_Umap_traits<enum DiagHubCommon::LogLevel,std::wstring,std::_Uhash_compare<enum DiagHubCommon::LogLevel,std::hash<enum DiagHubCommon::LogLevel>,std::equal_to<enum DiagHubCommon::LogLevel>>,std::allocator<std::pair<enum DiagHubCommon::LogLevel const,std::wstring>>,0>>::_Try_emplace<enum DiagHubCommon::LogLevel,>(
                    &dword_140024B60,
                    &v55,
                    &Type);
  v43 = std::wstring::wstring(v86, *v42 + 24LL);
  std::vector<std::shared_ptr<DiagHubCommon::ILogWriter>>::vector<std::shared_ptr<DiagHubCommon::ILogWriter>>(v79, v41);
  std::wstring::wstring(v80, v43);
  std::wstring::~wstring(v43);
  std::vector<std::shared_ptr<DiagHubCommon::ILogWriter>>::_Tidy(v41);
  v63 = v81;
  v44 = std::vector<std::shared_ptr<DiagHubCommon::ILogWriter>>::vector<std::shared_ptr<DiagHubCommon::ILogWriter>>(
          v73,
          &v101);
  v64 = (_BYTE *)v44;
  cbData = 4;
  v45 = (_QWORD *)std::_Hash<std::_Umap_traits<enum DiagHubCommon::LogLevel,std::wstring,std::_Uhash_compare<enum DiagHubCommon::LogLevel,std::hash<enum DiagHubCommon::LogLevel>,std::equal_to<enum DiagHubCommon::LogLevel>>,std::allocator<std::pair<enum DiagHubCommon::LogLevel const,std::wstring>>,0>>::_Try_emplace<enum DiagHubCommon::LogLevel,>(
                    &dword_140024B60,
                    &v55,
                    &cbData);
  v46 = std::wstring::wstring(v87, *v45 + 24LL);
  std::vector<std::shared_ptr<DiagHubCommon::ILogWriter>>::vector<std::shared_ptr<DiagHubCommon::ILogWriter>>(v81, v44);
  std::wstring::wstring(v82, v46);
  std::wstring::~wstring(v46);
  std::vector<std::shared_ptr<DiagHubCommon::ILogWriter>>::_Tidy(v44);
  v64 = v83;
  v47 = std::vector<std::shared_ptr<DiagHubCommon::ILogWriter>>::vector<std::shared_ptr<DiagHubCommon::ILogWriter>>(
          v72,
          &v103);
  *(_QWORD *)&v58 = v47;
  v60 = 2;
  v48 = (_QWORD *)std::_Hash<std::_Umap_traits<enum DiagHubCommon::LogLevel,std::wstring,std::_Uhash_compare<enum DiagHubCommon::LogLevel,std::hash<enum DiagHubCommon::LogLevel>,std::equal_to<enum DiagHubCommon::LogLevel>>,std::allocator<std::pair<enum DiagHubCommon::LogLevel const,std::wstring>>,0>>::_Try_emplace<enum DiagHubCommon::LogLevel,>(
                    &dword_140024B60,
                    &v55,
                    &v60);
  v49 = std::wstring::wstring(v88, *v48 + 24LL);
  std::vector<std::shared_ptr<DiagHubCommon::ILogWriter>>::vector<std::shared_ptr<DiagHubCommon::ILogWriter>>(v83, v47);
  std::wstring::wstring(v84, v49);
  std::wstring::~wstring(v49);
  std::vector<std::shared_ptr<DiagHubCommon::ILogWriter>>::_Tidy(v47);
  *(_QWORD *)&v58 = v75;
  v50 = std::vector<std::shared_ptr<DiagHubCommon::ILogWriter>>::vector<std::shared_ptr<DiagHubCommon::ILogWriter>>(
          v61,
          &v105);
  v55 = (char *)v50;
  LODWORD(v57) = 1;
  v51 = (_QWORD *)std::_Hash<std::_Umap_traits<enum DiagHubCommon::LogLevel,std::wstring,std::_Uhash_compare<enum DiagHubCommon::LogLevel,std::hash<enum DiagHubCommon::LogLevel>,std::equal_to<enum DiagHubCommon::LogLevel>>,std::allocator<std::pair<enum DiagHubCommon::LogLevel const,std::wstring>>,0>>::_Try_emplace<enum DiagHubCommon::LogLevel,>(
                    &dword_140024B60,
                    v89,
                    &v57);
  v54 = std::wstring::wstring(Str, *v51 + 24LL);
  std::vector<std::shared_ptr<DiagHubCommon::ILogWriter>>::vector<std::shared_ptr<DiagHubCommon::ILogWriter>>(v75, v50);
  std::wstring::wstring(v76, v54);
  std::wstring::~wstring(v54);
  std::vector<std::shared_ptr<DiagHubCommon::ILogWriter>>::_Tidy(v50);
  v52 = (DiagHubCommon::Logger *)DiagHubCommon::Logger::Logger(v37, v75, v83, v81, v79, v77);
  v53 = Block;
  Block = v52;
  if ( v53 )
  {
    DiagHubCommon::Logger::~Logger(v53);
    operator delete(v53);
    v52 = Block;
  }
  std::vector<std::shared_ptr<DiagHubCommon::ILogWriter>>::_Tidy(&v107);
  std::vector<std::shared_ptr<DiagHubCommon::ILogWriter>>::_Tidy(&v109);
  std::vector<std::shared_ptr<DiagHubCommon::ILogWriter>>::_Tidy(&v101);
  std::vector<std::shared_ptr<DiagHubCommon::ILogWriter>>::_Tidy(&v103);
  std::vector<std::shared_ptr<DiagHubCommon::ILogWriter>>::_Tidy(&v105);
  if ( hKey_8[0] )
    RegCloseKey(hKey_8[0]);
  std::vector<std::shared_ptr<DiagHubCommon::ILogWriter>>::_Tidy(&v90);
  return v52;
}

```

## disassembly

```asm
0x14000a42c  mov     rax, rsp
0x14000a42f  mov     [rax+8], rbx
0x14000a433  mov     [rax+10h], rsi
0x14000a437  mov     [rax+18h], rdi
0x14000a43b  push    rbp
0x14000a43c  push    r12
0x14000a43e  push    r13
0x14000a440  push    r14
0x14000a442  push    r15
0x14000a444  lea     rbp, [rax-628h]
0x14000a44b  sub     rsp, 700h
0x14000a452  mov     rax, cs:__security_cookie
0x14000a459  xor     rax, rsp
0x14000a45c  mov     [rbp+620h+var_30], rax
0x14000a463  xor     r12d, r12d
0x14000a466  mov     [rbp+620h+Type], r12d
0x14000a46d  mov     edi, 4
0x14000a472  mov     rax, gs:58h
0x14000a47b  mov     rbx, [rax]
0x14000a47e  or      r13, 0FFFFFFFFFFFFFFFFh
0x14000a482  mov     eax, [rdi+rbx]
0x14000a485  cmp     cs:dword_140024B50, eax
0x14000a48b  jle     short loc_14000A4BA
0x14000a48d  lea     rcx, dword_140024B50
0x14000a494  call    _Init_thread_header
0x14000a499  cmp     cs:dword_140024B50, r13d
0x14000a4a0  jnz     short loc_14000A4BA
0x14000a4a2  lea     rcx, _DiagHubCommon__Logger__GetLogger____2____dynamic_atexit_destructor_for__loggerInstance__; void (__cdecl *)()
0x14000a4a9  call    atexit
0x14000a4ae  lea     rcx, dword_140024B50
0x14000a4b5  call    _Init_thread_footer
0x14000a4ba  mov     eax, [rdi+rbx]
0x14000a4bd  cmp     cs:dword_140024B54, eax
0x14000a4c3  jle     short loc_14000A50A
0x14000a4c5  lea     rcx, dword_140024B54
0x14000a4cc  call    _Init_thread_header
0x14000a4d1  cmp     cs:dword_140024B54, r13d
0x14000a4d8  jnz     short loc_14000A50A
0x14000a4da  xor     edx, edx; Val
0x14000a4dc  lea     r8d, [rdx+40h]; Size
0x14000a4e0  lea     rcx, dword_140024B60; void *
0x14000a4e7  call    memset_0
0x14000a4ec  call    ??0LogLevelMapFactory@Logger@DiagHubCommon@@QEAA@XZ; DiagHubCommon::Logger::LogLevelMapFactory::LogLevelMapFactory(void)
0x14000a4f1  lea     rcx, _DiagHubCommon__Logger__GetLogger____2____dynamic_atexit_destructor_for__logLevelMapFactory__; void (__cdecl *)()
0x14000a4f8  call    atexit
0x14000a4fd  nop
0x14000a4fe  lea     rcx, dword_140024B54
0x14000a505  call    _Init_thread_footer
0x14000a50a  mov     rax, cs:Block
0x14000a511  test    rax, rax
0x14000a514  jnz     loc_14000B21E
0x14000a51a  mov     esi, r12d
0x14000a51d  xorps   xmm1, xmm1
0x14000a520  movdqu  [rbp+620h+var_428], xmm1
0x14000a528  mov     [rbp+620h+var_418], r12
0x14000a52f  lea     ecx, [rax+18h]; Size
0x14000a532  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x14000a537  mov     qword ptr [rsp+720h+var_6D8], rax
0x14000a53c  xorps   xmm0, xmm0
0x14000a53f  movups  xmmword ptr [rax], xmm0
0x14000a542  mov     r14d, 1
0x14000a548  mov     [rax+8], r14d
0x14000a54c  mov     [rax+0Ch], r14d
0x14000a550  lea     rcx, ??_7?$_Ref_count_obj2@VDebugStringLogWriter@DiagHubCommon@@@std@@6B@; const std::_Ref_count_obj2<DiagHubCommon::DebugStringLogWriter>::`vftable'
0x14000a557  mov     [rax], rcx
0x14000a55a  lea     rcx, [rax+10h]
0x14000a55e  lea     rdx, ??_7DebugStringLogWriter@DiagHubCommon@@6B@; const DiagHubCommon::DebugStringLogWriter::`vftable'
0x14000a565  mov     [rcx], rdx
0x14000a568  mov     r15d, r14d
0x14000a56b  mov     [rsp+720h+var_6E8], rcx
0x14000a570  mov     [rsp+720h+var_6E0], rax
0x14000a575  movdqu  [rsp+720h+var_6D8+8], xmm0
0x14000a57b  mov     rdx, qword ptr [rbp+620h+var_428+8]
0x14000a582  cmp     rdx, [rbp+620h+var_418]
0x14000a589  jz      short loc_14000A59F
0x14000a58b  mov     [rdx], rcx
0x14000a58e  mov     [rdx+8], rax
0x14000a592  mov     rbx, r12
0x14000a595  add     qword ptr [rbp+620h+var_428+8], 10h
0x14000a59d  jmp     short loc_14000A5B5
0x14000a59f  lea     r8, [rsp+720h+var_6E8]
0x14000a5a4  lea     rcx, [rbp+620h+var_428]
0x14000a5ab  call    ??$_Emplace_reallocate@V?$shared_ptr@VILogWriter@DiagHubCommon@@@std@@@?$vector@V?$shared_ptr@VILogWriter@DiagHubCommon@@@std@@V?$allocator@V?$shared_ptr@VILogWriter@DiagHubCommon@@@std@@@2@@std@@AEAAPEAV?$shared_ptr@VILogWriter@DiagHubCommon@@@1@QEAV21@$$QEAV21@@Z; std::vector<std::shared_ptr<DiagHubCommon::ILogWriter>>::_Emplace_reallocate<std::shared_ptr<DiagHubCommon::ILogWriter>>(std::shared_ptr<DiagHubCommon::ILogWriter> * const,std::shared_ptr<DiagHubCommon::ILogWriter> &&)
0x14000a5b0  mov     rbx, [rsp+720h+var_6E0]
0x14000a5b5  test    rbx, rbx
0x14000a5b8  jz      short loc_14000A5F4
0x14000a5ba  mov     eax, r13d
0x14000a5bd  lock xadd [rbx+8], eax
0x14000a5c2  add     eax, r13d
0x14000a5c5  jnz     short loc_14000A5F4
0x14000a5c7  mov     rax, [rbx]
0x14000a5ca  mov     rcx, rbx
0x14000a5cd  mov     rax, [rax]
0x14000a5d0  call    cs:__guard_dispatch_icall_fptr
0x14000a5d6  mov     eax, r13d
0x14000a5d9  lock xadd [rbx+0Ch], eax
0x14000a5de  add     eax, r13d
0x14000a5e1  jnz     short loc_14000A5F4
0x14000a5e3  mov     rax, [rbx]
0x14000a5e6  mov     rcx, rbx
0x14000a5e9  mov     rax, [rax+8]
0x14000a5ed  call    cs:__guard_dispatch_icall_fptr
0x14000a5f3  nop
0x14000a5f4  xorps   xmm0, xmm0
0x14000a5f7  movups  xmmword ptr [rsp+720h+hKey+8], xmm0
0x14000a5fc  mov     [rsp+720h+hKey+8], r12
0x14000a601  mov     dword ptr [rsp+720h+var_6B8], r12d
0x14000a606  mov     qword ptr [rsp+720h+var_6B0], r12
0x14000a60b  lea     r8, aSoftwareMicros_1; "Software\\Microsoft\\VisualStudio\\Diag"...
0x14000a612  lea     rcx, [rsp+720h+hKey+8]; this
0x14000a617  call    ?Open@CRegKey@ATL@@QEAAJPEAUHKEY__@@PEBGK@Z; ATL::CRegKey::Open(HKEY__ *,ushort const *,ulong)
0x14000a61c  test    eax, eax
0x14000a61e  jnz     loc_14000AD36
0x14000a624  mov     [rbp+620h+cbData], 105h
0x14000a62e  lea     r9, [rbp+620h+cbData]; unsigned int *
0x14000a635  lea     r8, [rbp+620h+var_240]; unsigned __int16 *
0x14000a63c  lea     rdx, aLoglevel; "LogLevel"
0x14000a643  lea     rcx, [rsp+720h+hKey+8]; this
0x14000a648  call    ?QueryStringValue@CRegKey@ATL@@QEAAJPEBGPEAGPEAK@Z; ATL::CRegKey::QueryStringValue(ushort const *,ushort *,ulong *)
0x14000a64d  test    eax, eax
0x14000a64f  jnz     loc_14000A6D8
0x14000a655  mov     rdi, cs:qword_140024B68
0x14000a65c  mov     rbx, [rdi]
0x14000a65f  cmp     rbx, rdi
0x14000a662  jz      short loc_14000A6D8
0x14000a664  mov     eax, [rbx+10h]
0x14000a667  mov     [rbp+620h+var_668], eax
0x14000a66a  lea     rdx, [rbx+18h]
0x14000a66e  lea     rcx, [rbp+620h+var_660]
0x14000a672  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x14000a677  lea     rcx, [rbp+620h+var_240]
0x14000a67e  mov     rax, r13
0x14000a681  inc     rax
0x14000a684  cmp     [rcx+rax*2], r12w
0x14000a689  jnz     short loc_14000A681
0x14000a68b  lea     rdx, [rbp+620h+var_660]
0x14000a68f  cmp     [rbp+620h+var_648], 7
0x14000a694  cmova   rdx, [rbp+620h+var_660]
0x14000a699  mov     rcx, [rbp+620h+var_650]
0x14000a69d  cmp     rcx, rax
0x14000a6a0  jnz     loc_14000A7D7
0x14000a6a6  test    rcx, rcx
0x14000a6a9  jz      short loc_14000A6CC
0x14000a6ab  lea     r8, [rbp+620h+var_240]
0x14000a6b2  movzx   eax, word ptr [r8]
0x14000a6b6  cmp     [rdx], ax
0x14000a6b9  jnz     loc_14000A7D7
0x14000a6bf  add     rdx, 2
0x14000a6c3  add     r8, 2
0x14000a6c7  sub     rcx, r14
0x14000a6ca  jnz     short loc_14000A6B2
0x14000a6cc  mov     esi, [rbp+620h+var_668]
0x14000a6cf  lea     rcx, [rbp+620h+var_660]
0x14000a6d3  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x14000a6d8  mov     [rbp+620h+cbData], 4
0x14000a6e2  lea     rax, [rbp+620h+cbData]
0x14000a6e9  mov     [rsp+720h+lpcbData], rax; lpcbData
0x14000a6ee  lea     rax, [rbp+620h+Data]
0x14000a6f5  mov     [rsp+720h+lpData], rax; lpData
0x14000a6fa  lea     r9, [rbp+620h+Type]; lpType
0x14000a701  xor     r8d, r8d; lpReserved
0x14000a704  lea     rdx, aEtwlogging; "EtwLogging"
0x14000a70b  mov     rcx, [rsp+720h+hKey+8]; hKey
0x14000a710  call    cs:__imp_RegQueryValueExW
0x14000a716  test    eax, eax
0x14000a718  jnz     loc_14000A84F
0x14000a71e  cmp     [rbp+620h+Type], 4
0x14000a725  jnz     loc_14000A84F
0x14000a72b  cmp     dword ptr [rbp+620h+Data], r14d
0x14000a732  jnz     loc_14000A84F
0x14000a738  lea     ecx, [rax+20h]; Size
0x14000a73b  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x14000a740  mov     rdi, rax
0x14000a743  mov     qword ptr [rsp+720h+var_6D8], rax
0x14000a748  xorps   xmm0, xmm0
0x14000a74b  movups  xmmword ptr [rax], xmm0
0x14000a74e  mov     [rax+8], r14d
0x14000a752  mov     [rax+0Ch], r14d
0x14000a756  lea     rax, ??_7?$_Ref_count_obj2@VEtlLogWriter@DiagHubCommon@@@std@@6B@; const std::_Ref_count_obj2<DiagHubCommon::EtlLogWriter>::`vftable'
0x14000a75d  mov     [rdi], rax
0x14000a760  lea     r14, [rdi+10h]
0x14000a764  lea     rax, ??_7EtlLogWriter@DiagHubCommon@@6B@; const DiagHubCommon::EtlLogWriter::`vftable'
0x14000a76b  mov     [r14], rax
0x14000a76e  lea     r9, [r14+8]; RegHandle
0x14000a772  xor     r8d, r8d; CallbackContext
0x14000a775  xor     edx, edx; EnableCallback
0x14000a777  lea     rcx, ?providerGuid@EtlLogWriter@DiagHubCommon@@0U_GUID@@B; ProviderId
0x14000a77e  call    cs:__imp_EventRegister
0x14000a784  lea     r9, String; "============= Diagnostics Hub Log ====="...
0x14000a78b  xor     r8d, r8d; Keyword
0x14000a78e  xor     edx, edx; Level
0x14000a790  mov     rcx, [r14+8]; RegHandle
0x14000a794  call    cs:__imp_EventWriteString
0x14000a79a  xorps   xmm0, xmm0
0x14000a79d  mov     r15d, 3
0x14000a7a3  mov     [rsp+720h+var_6E8], r14
0x14000a7a8  mov     [rsp+720h+var_6E0], rdi
0x14000a7ad  movdqu  [rsp+720h+var_6D8+8], xmm0
0x14000a7b3  mov     rdx, qword ptr [rbp+620h+var_428+8]
0x14000a7ba  cmp     rdx, [rbp+620h+var_418]
0x14000a7c1  jz      short loc_14000A7F4
0x14000a7c3  mov     [rdx], r14
0x14000a7c6  mov     [rdx+8], rdi
0x14000a7ca  mov     rbx, r12
0x14000a7cd  add     qword ptr [rbp+620h+var_428+8], 10h
0x14000a7d5  jmp     short loc_14000A80A
0x14000a7d7  lea     rcx, [rbp+620h+var_660]
0x14000a7db  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x14000a7e0  mov     rax, [rbx]
0x14000a7e3  mov     rbx, rax
0x14000a7e6  cmp     rax, rdi
0x14000a7e9  jnz     loc_14000A664
0x14000a7ef  jmp     loc_14000A6D8
0x14000a7f4  lea     r8, [rsp+720h+var_6E8]
0x14000a7f9  lea     rcx, [rbp+620h+var_428]
0x14000a800  call    ??$_Emplace_reallocate@V?$shared_ptr@VILogWriter@DiagHubCommon@@@std@@@?$vector@V?$shared_ptr@VILogWriter@DiagHubCommon@@@std@@V?$allocator@V?$shared_ptr@VILogWriter@DiagHubCommon@@@std@@@2@@std@@AEAAPEAV?$shared_ptr@VILogWriter@DiagHubCommon@@@1@QEAV21@$$QEAV21@@Z; std::vector<std::shared_ptr<DiagHubCommon::ILogWriter>>::_Emplace_reallocate<std::shared_ptr<DiagHubCommon::ILogWriter>>(std::shared_ptr<DiagHubCommon::ILogWriter> * const,std::shared_ptr<DiagHubCommon::ILogWriter> &&)
0x14000a805  mov     rbx, [rsp+720h+var_6E0]
0x14000a80a  test    rbx, rbx
0x14000a80d  jz      short loc_14000A849
0x14000a80f  mov     eax, r13d
0x14000a812  lock xadd [rbx+8], eax
0x14000a817  add     eax, r13d
0x14000a81a  jnz     short loc_14000A849
0x14000a81c  mov     rax, [rbx]
0x14000a81f  mov     rcx, rbx
0x14000a822  mov     rax, [rax]
0x14000a825  call    cs:__guard_dispatch_icall_fptr
0x14000a82b  mov     eax, r13d
0x14000a82e  lock xadd [rbx+0Ch], eax
0x14000a833  add     eax, r13d
0x14000a836  jnz     short loc_14000A849
0x14000a838  mov     rax, [rbx]
0x14000a83b  mov     rcx, rbx
0x14000a83e  mov     rax, [rax+8]
0x14000a842  call    cs:__guard_dispatch_icall_fptr
0x14000a848  nop
0x14000a849  mov     r14d, 1
0x14000a84f  mov     [rbp+620h+cbData], 105h
0x14000a859  lea     r9, [rbp+620h+cbData]; unsigned int *
0x14000a860  lea     r8, [rbp+620h+var_240]; unsigned __int16 *
0x14000a867  lea     rdx, aLogdirectory; "LogDirectory"
0x14000a86e  lea     rcx, [rsp+720h+hKey+8]; this
0x14000a873  call    ?QueryStringValue@CRegKey@ATL@@QEAAJPEBGPEAGPEAK@Z; ATL::CRegKey::QueryStringValue(ushort const *,ushort *,ulong *)
0x14000a878  test    eax, eax
0x14000a87a  jnz     loc_14000AD36
0x14000a880  cmp     [rbp+620h+cbData], r14d
0x14000a887  jbe     loc_14000AD36
0x14000a88d  xorps   xmm0, xmm0
0x14000a890  movups  xmmword ptr [rbp+620h+lpFileName], xmm0
0x14000a897  mov     [rbp+620h+var_3F0], r12
0x14000a89e  mov     [rbp+620h+var_3E8], r12
0x14000a8a5  lea     rax, [rbp+620h+var_240]
0x14000a8ac  mov     r8, r13
0x14000a8af  inc     r8
0x14000a8b2  cmp     [rax+r8*2], r12w
0x14000a8b7  jnz     short loc_14000A8AF
0x14000a8b9  lea     rdx, [rbp+620h+var_240]
0x14000a8c0  lea     rcx, [rbp+620h+lpFileName]
0x14000a8c7  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x14000a8cc  nop
0x14000a8cd  lea     rcx, [rbp+620h+lpFileName]
0x14000a8d4  mov     rdx, [rbp+620h+lpFileName]
0x14000a8db  mov     r8, [rbp+620h+var_3E8]
0x14000a8e2  cmp     r8, 7
0x14000a8e6  cmova   rcx, rdx
0x14000a8ea  mov     ebx, 5Ch ; '\'
0x14000a8ef  mov     rax, [rbp+620h+var_3F0]
0x14000a8f6  cmp     [rcx+rax*2-2], bx
0x14000a8fb  jz      short loc_14000A91E
0x14000a8fd  lea     rdx, asc_14001B1C8; "\\"
0x14000a904  lea     rcx, [rbp+620h+lpFileName]; Src
0x14000a90b  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@QEBG@Z; std::wstring::append(ushort const * const)
0x14000a910  mov     r8, [rbp+620h+var_3E8]
0x14000a917  mov     rdx, [rbp+620h+lpFileName]
0x14000a91e  lea     rcx, [rbp+620h+lpFileName]
0x14000a925  cmp     r8, 7
0x14000a929  cmova   rcx, rdx; lpFileName
0x14000a92d  call    cs:__imp_GetFileAttributesW
0x14000a933  cmp     eax, 0FFFFFFFFh
0x14000a936  jz      loc_14000AD2A
0x14000a93c  test    al, 10h
0x14000a93e  jz      loc_14000AD2A
0x14000a944  xorps   xmm0, xmm0
0x14000a947  movdqu  xmmword ptr [rbp+620h+Str], xmm0
0x14000a94f  xorps   xmm1, xmm1
0x14000a952  movdqu  [rbp+620h+var_3D0], xmm1
0x14000a95a  mov     [rbp+620h+var_3C0], r12
0x14000a961  lea     rdx, [rbp+620h+Str]
0x14000a968  xor     ecx, ecx; hModule
0x14000a96a  call    ?GetModulePath@ModulePath@DiagHubCommon@@SAJPEAUHINSTANCE__@@AEAV?$vector@GV?$allocator@G@std@@@std@@@Z; DiagHubCommon::ModulePath::GetModulePath(HINSTANCE__ *,std::vector<ushort> &)
0x14000a96f  mov     edi, 800700A1h
0x14000a974  test    eax, eax
0x14000a976  js      short loc_14000A9B5
0x14000a978  mov     edx, ebx; Ch
0x14000a97a  mov     rcx, [rbp+620h+Str]; Str
0x14000a981  call    cs:__imp_wcsrchr
0x14000a987  mov     rcx, rax
0x14000a98a  test    rax, rax
0x14000a98d  jnz     short loc_14000A993
0x14000a98f  mov     eax, edi
  ... truncated ...
```
