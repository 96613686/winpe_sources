# UaLiteManager::CreateUUPProductSandboxWithMetadata(wil::basic_zstring_view<wchar_t>)

- ea: `0x180043ee8`
- end: `0x180044785`
- name: `?CreateUUPProductSandboxWithMetadata@UaLiteManager@@AEAA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$basic_zstring_view@_W@wil@@@Z`
- size: `2205`
- prototype: ``
- caller_count: `1`
- callee_count: `27`
- tags: `file_ops, registry_config, service_task, installer_update`

## callers

- `0x18006f0a0`

## callees

- `0x1800059d0`
- `0x180008ed8`
- `0x180009960`
- `0x18000a0e8`
- `0x18000c4c4`
- `0x18000d2fc`
- `0x180012430`
- `0x18001270c`
- `0x180023b20`
- `0x180027f3c`
- `0x180039f90`
- `0x180043ee8`
- `0x180060da4`
- `0x180067684`
- `0x180074744`
- `0x180077664`
- `0x180094d0c`
- `0x180096a40`
- `0x18009b6b0`
- `0x18009f0b0`
- `0x1801de458`
- `0x1801def30`
- `0x1801df488`
- `0x1801dfc4c`
- `0x1801e34c8`
- `0x180203760`
- `0x180203fa4`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x180043fe3`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x180044356`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x180043fe3`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x180044356`
- `api-ms-win-core-libraryloader-l1-1-0!FreeLibrary` at `0x18004460c`
- `api-ms-win-core-libraryloader-l1-1-0!FreeLibrary` at `0x18004460c`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800440c3`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18004462d`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800440c3`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18004462d`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800440d8`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180044642`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800440d8`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180044642`
- `api-ms-win-core-kernel32-legacy-l1-1-0!CopyFileW` at `0x1800445c9`
- `api-ms-win-core-kernel32-legacy-l1-1-0!CopyFileW` at `0x1800445c9`

## string_xrefs

- `0x18004468b`: `onecore\base\ntsetup\conx\mosetup\updateagent\src\UaLite\UaLiteManagerImpl.h`
- `0x18004469d`: `onecore\base\ntsetup\conx\mosetup\updateagent\src\UaLite\UaLiteManagerImpl.h`
- `0x1800446b2`: `onecore\base\ntsetup\conx\mosetup\updateagent\src\UaLite\UaLiteManagerImpl.h`
- `0x1800446f6`: `onecore\base\ntsetup\conx\mosetup\updateagent\src\UaLite\UaLiteManagerImpl.h`
- `0x180044708`: `onecore\base\ntsetup\conx\mosetup\updateagent\src\UaLite\UaLiteManagerImpl.h`
- `0x18004471d`: `onecore\base\ntsetup\conx\mosetup\updateagent\src\UaLite\UaLiteManagerImpl.h`
- `0x180044732`: `onecore\base\ntsetup\conx\mosetup\updateagent\src\UaLite\UaLiteManagerImpl.h`
- `0x180044773`: `onecore\base\ntsetup\conx\mosetup\updateagent\src\UaLite\UaLiteManagerImpl.h`
- `0x180043fc1`: `Product sandbox already exists. Return the sandbox location.`
- `0x180044470`: `.rum.json.cab`
- `0x180044082`: `UpdateAgentLiteCabPath`

## pseudocode

```c
// Hidden C++ exception states: #wind=17
HMODULE *__fastcall UaLiteManager::CreateUUPProductSandboxWithMetadata(_QWORD *a1, HMODULE *a2, _QWORD *a3)
{
  HMODULE v5; // rcx
  HMODULE v6; // rax
  __int64 v7; // rcx
  HMODULE v8; // rcx
  HMODULE v9; // rax
  const WCHAR *v10; // rcx
  const char *v11; // r9
  __int64 v12; // rdx
  HMODULE *v13; // r14
  HMODULE v14; // rbx
  int v15; // esi
  __int64 v16; // rcx
  int IsMoUpdateTestsEnabled; // eax
  __int64 v18; // rcx
  __int64 v19; // r8
  __int64 v20; // rcx
  int Value; // eax
  __int64 v22; // rdx
  HMODULE v23; // rax
  HANDLE ProcessHeap; // rax
  HMODULE p_Src; // rax
  _QWORD *v26; // rbx
  _QWORD *v27; // rax
  HMODULE v28; // rax
  __int64 v29; // rcx
  __int64 v30; // rax
  wchar_t **v31; // rax
  HMODULE v32; // rax
  __int64 v33; // rcx
  __int64 v34; // rax
  __int64 v35; // rax
  __int64 v36; // rax
  wchar_t **v37; // rax
  __int64 v38; // rcx
  HMODULE v39; // rcx
  HMODULE v40; // rax
  const WCHAR *v41; // rcx
  const char *v42; // r9
  int v43; // eax
  int v44; // esi
  __int64 v45; // rdx
  const wchar_t *v46; // rdx
  const wchar_t *v47; // rcx
  int CabFile; // eax
  int v49; // esi
  __int64 v50; // rdx
  _QWORD *v51; // rax
  _QWORD *v52; // rcx
  _QWORD *Path; // rax
  __int64 v54; // rcx
  _QWORD *v55; // rax
  LPCWSTR *v56; // rax
  _QWORD *v57; // rax
  __int64 v58; // rcx
  LPCWSTR *v59; // rax
  __int64 v60; // rcx
  const WCHAR *v61; // rdx
  const WCHAR *v62; // rcx
  const char *v63; // r9
  HMODULE v64; // rbx
  HANDLE v65; // rax
  unsigned int v67; // eax
  unsigned int v68; // eax
  int *v69; // [rsp+20h] [rbp-E0h]
  HMODULE hLibModule; // [rsp+30h] [rbp-D0h] BYREF
  __int64 v71; // [rsp+38h] [rbp-C8h]
  int v72[2]; // [rsp+40h] [rbp-C0h] BYREF
  __int64 v73; // [rsp+48h] [rbp-B8h]
  int v74; // [rsp+50h] [rbp-B0h]
  HMODULE v75; // [rsp+58h] [rbp-A8h] BYREF
  _OWORD v76[2]; // [rsp+60h] [rbp-A0h] BYREF
  _OWORD v77[2]; // [rsp+80h] [rbp-80h] BYREF
  __int64 v78; // [rsp+A0h] [rbp-60h]
  HMODULE *v79; // [rsp+A8h] [rbp-58h]
  int v80; // [rsp+B0h] [rbp-50h] BYREF
  __int128 Src; // [rsp+B8h] [rbp-48h] BYREF
  __int64 v82; // [rsp+C8h] [rbp-38h]
  unsigned __int64 v83; // [rsp+D0h] [rbp-30h]
  wchar_t *v84[2]; // [rsp+D8h] [rbp-28h] BYREF
  __m128i si128; // [rsp+E8h] [rbp-18h]
  LPCWSTR lpPathName[3]; // [rsp+F8h] [rbp-8h] BYREF
  unsigned __int64 v87; // [rsp+110h] [rbp+10h]
  LPCWSTR lpExistingFileName[3]; // [rsp+118h] [rbp+18h] BYREF
  unsigned __int64 v89; // [rsp+130h] [rbp+30h]
  _QWORD v90[2]; // [rsp+138h] [rbp+38h] BYREF
  __int64 v91; // [rsp+148h] [rbp+48h]
  unsigned __int64 v92; // [rsp+150h] [rbp+50h]
  LPCWSTR lpNewFileName[4]; // [rsp+158h] [rbp+58h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+1B8h] [rbp+B8h]

  v78 = -2;
  v79 = a2;
  v74 = 1;
  if ( a1[11] <= 7u )
    v5 = (HMODULE)(a1 + 8);
  else
    v5 = (HMODULE)a1[8];
  hLibModule = v5;
  v71 = a1[10];
  v6 = (HMODULE)CreatePath(&Src, (__int64)&hLibModule, a3);
  v7 = *((_QWORD *)v6 + 2);
  if ( *((_QWORD *)v6 + 3) > 7u )
    v6 = *(HMODULE *)v6;
  hLibModule = v6;
  v71 = v7;
  StripUNCPrefix(a2);
  v74 = 1;
  std::wstring::~wstring(&Src);
  v8 = a2[2];
  if ( (unsigned __int64)a2[3] <= 7 )
    v9 = (HMODULE)a2;
  else
    v9 = *a2;
  hLibModule = v9;
  v71 = (__int64)v8;
  if ( (unsigned __int8)DirectoryExists(&hLibModule) )
  {
    LogAdapter::TraceInfo<>("Product sandbox already exists. Return the sandbox location.");
    return a2;
  }
  if ( (unsigned __int64)a2[3] <= 7 )
    v10 = (const WCHAR *)a2;
  else
    v10 = (const WCHAR *)*a2;
  if ( !CreateDirectoryW(v10, 0) )
    wil::details::in1diag3::_Throw_GetLastError(
      retaddr,
      (void *)0xC6,
      (unsigned int)"onecore\\base\\ntsetup\\conx\\mosetup\\updateagent\\src\\UaLite\\UaLiteManagerImpl.h",
      v11);
  *(_OWORD *)v84 = 0;
  si128 = _mm_load_si128((const __m128i *)&_xmm);
  LOWORD(v84[0]) = 0;
  v75 = 0;
  v13 = (HMODULE *)_put___unique_any_t_V__unique_storage_U__resource_policy_PEA_WP6AJPEA_W__E_1_STRAPI_Release__YAJ0_ZU__integral_constant__K_0A__wistd__PEA_WPEA_W_0A___T_details_wil___details_wil___wil__QEAAPEAPEA_WXZ(&v75);
  v14 = 0;
  hLibModule = 0;
  v72[0] = 0;
  v80 = 0;
  if ( v13 )
  {
    IsMoUpdateTestsEnabled = CMoUpdateHelpersT<CEmptyType>::IsMoUpdateTestsEnabled(v72);
    v15 = IsMoUpdateTestsEnabled;
    if ( IsMoUpdateTestsEnabled < 0 )
    {
LABEL_19:
      v16 = (unsigned int)IsMoUpdateTestsEnabled;
      goto LABEL_17;
    }
    if ( v72[0] )
    {
      IsMoUpdateTestsEnabled = CRegUtilT<wchar_t *,CRegType,0,1>::ValueExists(v18, v12, v19, &v80);
      v15 = IsMoUpdateTestsEnabled;
      if ( IsMoUpdateTestsEnabled < 0 )
        goto LABEL_19;
      if ( v80 )
      {
        Value = CRegUtilT<wchar_t *,CRegType,0,1>::GetValue(
                  v20,
                  L"SYSTEM\\Setup\\MoSetup",
                  L"UpdateAgentLiteCabPath",
                  &hLibModule);
        v15 = Value;
        if ( Value < 0 )
        {
          CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure((unsigned int)Value, v22);
          v14 = hLibModule;
          goto LABEL_27;
        }
        v14 = hLibModule;
      }
    }
    v23 = v14;
    v14 = 0;
    *v13 = v23;
    goto LABEL_27;
  }
  v15 = -2147024809;
  v16 = 2147942487LL;
LABEL_17:
  CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(v16, v12);
LABEL_27:
  CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent((unsigned int)v15);
  if ( v14 )
  {
    ProcessHeap = GetProcessHeap();
    HeapFree(ProcessHeap, 0, v14 - 1);
    CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(0);
  }
  if ( v15 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0xCA,
      (unsigned int)"onecore\\base\\ntsetup\\conx\\mosetup\\updateagent\\src\\UaLite\\UaLiteManagerImpl.h",
      (const char *)(unsigned int)v15,
      (int)v69);
  if ( v75 )
  {
    hLibModule = v75;
    v35 = -1;
    do
      ++v35;
    while ( *((_WORD *)v75 + v35) );
    v71 = v35;
    v36 = StripUNCPrefix(v76);
    std::wstring::operator=(v84, v36);
    std::wstring::~wstring(v76);
  }
  else
  {
    hLibModule = (HMODULE)L".Deployment.cab";
    v71 = 15;
    operator+(&Src);
    p_Src = (HMODULE)&Src;
    if ( v83 > 7 )
      p_Src = (HMODULE)Src;
    hLibModule = p_Src;
    v71 = v82;
    v26 = a1 + 4;
    if ( a1[7] <= 7u )
      v27 = a1 + 4;
    else
      v27 = (_QWORD *)*v26;
    *(_QWORD *)v72 = v27;
    v73 = a1[6];
    v28 = (HMODULE)CreatePath(v76, (__int64)v72, &hLibModule);
    v29 = *((_QWORD *)v28 + 2);
    if ( *((_QWORD *)v28 + 3) > 7u )
      v28 = *(HMODULE *)v28;
    hLibModule = v28;
    v71 = v29;
    v30 = StripUNCPrefix(v77);
    std::wstring::operator=(v84, v30);
    std::wstring::~wstring(v77);
    std::wstring::~wstring(v76);
    v31 = v84;
    if ( si128.m128i_i64[1] > 7uLL )
      v31 = (wchar_t **)v84[0];
    hLibModule = (HMODULE)v31;
    v71 = si128.m128i_i64[0];
    if ( !(unsigned __int8)FileExists(&hLibModule) )
    {
      LogAdapter::TraceInfo<>("Product specific Deployment.cab not found. Checking for Default UaLite.");
      hLibModule = (HMODULE)L"Deployment.cab";
      v71 = 14;
      if ( a1[7] > 7u )
        v26 = (_QWORD *)*v26;
      *(_QWORD *)v72 = v26;
      v73 = a1[6];
      v32 = (HMODULE)CreatePath(v77, (__int64)v72, &hLibModule);
      v33 = *((_QWORD *)v32 + 2);
      if ( *((_QWORD *)v32 + 3) > 7u )
        v32 = *(HMODULE *)v32;
      hLibModule = v32;
      v71 = v33;
      v34 = StripUNCPrefix(v76);
      std::wstring::operator=(v84, v34);
      std::wstring::~wstring(v76);
      std::wstring::~wstring(v77);
    }
    std::wstring::~wstring(&Src);
  }
  v37 = v84;
  if ( si128.m128i_i64[1] > 7uLL )
    v37 = (wchar_t **)v84[0];
  hLibModule = (HMODULE)v37;
  v71 = si128.m128i_i64[0];
  if ( !(unsigned __int8)FileExists(&hLibModule) )
  {
    if ( *(_QWORD *)&LogAdapter::g_Logger )
      LogAdapter::Logger::Log<std::wstring>(v38, 3, "Could not find the expected file [{}]", v84);
    v67 = EnsureNTSTATUS<long>(2147549183LL);
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0xE0,
      (unsigned int)"onecore\\base\\ntsetup\\conx\\mosetup\\updateagent\\src\\UaLite\\UaLiteManagerImpl.h",
      (const char *)v67,
      (int)v69);
  }
  LogAdapter::TraceAtLevel<std::wstring>(1, "Deployment.cab found at [{}]", v84);
  v39 = a2[2];
  if ( (unsigned __int64)a2[3] <= 7 )
    v40 = (HMODULE)a2;
  else
    v40 = *a2;
  hLibModule = v40;
  v71 = (__int64)v39;
  UaLiteManager::GetMetadataDirectory(lpPathName, &hLibModule);
  v41 = (const WCHAR *)lpPathName;
  if ( v87 > 7 )
    v41 = lpPathName[0];
  if ( !CreateDirectoryW(v41, 0) )
    wil::details::in1diag3::_Throw_GetLastError(
      retaddr,
      (void *)0xE7,
      (unsigned int)"onecore\\base\\ntsetup\\conx\\mosetup\\updateagent\\src\\UaLite\\UaLiteManagerImpl.h",
      v42);
  hLibModule = 0;
  v43 = DpxLoad(&hLibModule);
  v44 = v43;
  if ( v43 < 0 )
  {
    v80 = v43;
    if ( *(_QWORD *)&LogAdapter::g_Logger )
    {
      LogAdapter::Logger::LogNumObjects<>(*(_QWORD *)&LogAdapter::g_Logger, 0, 3, "Failed to load DPX");
      *(_QWORD *)v72 = &v80;
      v69 = v72;
      LOBYTE(v45) = 1;
      LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
        *(_QWORD *)&LogAdapter::g_Logger,
        v45,
        3,
        ": {}");
    }
  }
  if ( v44 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0xEB,
      (unsigned int)"onecore\\base\\ntsetup\\conx\\mosetup\\updateagent\\src\\UaLite\\UaLiteManagerImpl.h",
      (const char *)(unsigned int)v44,
      (int)v69);
  v46 = (const wchar_t *)lpPathName;
  if ( v87 > 7 )
    v46 = lpPathName[0];
  v47 = (const wchar_t *)v84;
  if ( si128.m128i_i64[1] > 7uLL )
    v47 = v84[0];
  CabFile = ExtractCabFile(v47, v46, 0);
  v49 = CabFile;
  if ( CabFile < 0 )
  {
    v80 = CabFile;
    if ( *(_QWORD *)&LogAdapter::g_Logger )
    {
      LogAdapter::Logger::LogNumObjects<std::wstring>(
        *(_QWORD *)&LogAdapter::g_Logger,
        0,
        3,
        "Failed to extract all files from {}",
        v84);
      *(_QWORD *)v72 = &v80;
      v69 = v72;
      LOBYTE(v50) = 1;
      LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
        *(_QWORD *)&LogAdapter::g_Logger,
        v50,
        3,
        ": {}");
    }
  }
  if ( v49 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0xF2,
      (unsigned int)"onecore\\base\\ntsetup\\conx\\mosetup\\updateagent\\src\\UaLite\\UaLiteManagerImpl.h",
      (const char *)(unsigned int)v49,
      (int)v69);
  *(_QWORD *)v72 = L".rum.json.cab";
  v73 = 13;
  operator+(v90);
  v51 = v90;
  if ( v92 > 7 )
    v51 = (_QWORD *)v90[0];
  *(_QWORD *)v72 = v51;
  v73 = v91;
  if ( a1[7] <= 7u )
    v52 = a1 + 4;
  else
    v52 = (_QWORD *)a1[4];
  *(_QWORD *)&Src = v52;
  *((_QWORD *)&Src + 1) = a1[6];
  Path = CreatePath(v76, (__int64)&Src, v72);
  v54 = Path[2];
  if ( Path[3] > 7u )
    Path = (_QWORD *)*Path;
  *(_QWORD *)&Src = Path;
  *((_QWORD *)&Src + 1) = v54;
  StripUNCPrefix(lpExistingFileName);
  std::wstring::~wstring(v76);
  v55 = v90;
  if ( v92 > 7 )
    v55 = (_QWORD *)v90[0];
  *(_QWORD *)&Src = v55;
  *((_QWORD *)&Src + 1) = v91;
  v56 = lpPathName;
  if ( v87 > 7 )
    v56 = (LPCWSTR *)lpPathName[0];
  *(_QWORD *)v72 = v56;
  v73 = (__int64)lpPathName[2];
  v57 = CreatePath(v77, (__int64)v72, &Src);
  v58 = v57[2];
  if ( v57[3] > 7u )
    v57 = (_QWORD *)*v57;
  *(_QWORD *)&Src = v57;
  *((_QWORD *)&Src + 1) = v58;
  StripUNCPrefix(lpNewFileName);
  std::wstring::~wstring(v77);
  v59 = lpExistingFileName;
  if ( v89 > 7 )
    v59 = (LPCWSTR *)lpExistingFileName[0];
  *(_QWORD *)&Src = v59;
  *((LPCWSTR *)&Src + 1) = lpExistingFileName[2];
  if ( !(unsigned __int8)FileExists(&Src) )
  {
    if ( *(_QWORD *)&LogAdapter::g_Logger )
      LogAdapter::Logger::Log<std::wstring>(v60, 3, "Could not find the expected file [{}]", lpExistingFileName);
    v68 = EnsureNTSTATUS<long>(2147549183LL);
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0xFA,
      (unsigned int)"onecore\\base\\ntsetup\\conx\\mosetup\\updateagent\\src\\UaLite\\UaLiteManagerImpl.h",
      (const char *)v68,
      (int)v69);
  }
  v61 = (const WCHAR *)lpNewFileName;
  if ( lpNewFileName[3] > (LPCWSTR)7 )
    v61 = lpNewFileName[0];
  v62 = (const WCHAR *)lpExistingFileName;
  if ( v89 > 7 )
    v62 = lpExistingFileName[0];
  if ( !CopyFileW(v62, v61, 0) )
    wil::details::in1diag3::_Throw_GetLastError(
      retaddr,
      (void *)0xFC,
      (unsigned int)"onecore\\base\\ntsetup\\conx\\mosetup\\updateagent\\src\\UaLite\\UaLiteManagerImpl.h",
      v63);
  std::wstring::~wstring(lpNewFileName);
  std::wstring::~wstring(lpExistingFileName);
  std::wstring::~wstring(v90);
  if ( hLibModule )
    FreeLibrary(hLibModule);
  std::wstring::~wstring(lpPathName);
  v64 = v75;
  if ( v75 )
  {
    v65 = GetProcessHeap();
    HeapFree(v65, 0, v64 - 1);
    CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(0);
  }
  std::wstring::~wstring(v84);
  return a2;
}

```

## disassembly

```asm
0x180043ee8  mov     rax, rsp
0x180043eeb  push    rbp
0x180043eec  push    rsi
0x180043eed  push    rdi
0x180043eee  push    r12
0x180043ef0  push    r13
0x180043ef2  push    r14
0x180043ef4  push    r15
0x180043ef6  lea     rbp, [rsp-80h]
0x180043efb  sub     rsp, 180h
0x180043f02  mov     [rbp+0B0h+var_110], 0FFFFFFFFFFFFFFFEh
0x180043f0a  mov     [rax+8], rbx
0x180043f0e  mov     rax, cs:__security_cookie
0x180043f15  xor     rax, rsp
0x180043f18  mov     [rbp+0B0h+var_38], rax
0x180043f1c  mov     r12, r8
0x180043f1f  mov     rdi, rdx
0x180043f22  mov     r15, rcx
0x180043f25  mov     [rbp+0B0h+var_108], rdx
0x180043f29  mov     ebx, 1
0x180043f2e  mov     [rsp+1B0h+var_160], ebx
0x180043f32  cmp     qword ptr [rcx+58h], 7
0x180043f37  jbe     short loc_180043F3F
0x180043f39  mov     rcx, [rcx+40h]
0x180043f3d  jmp     short loc_180043F43
0x180043f3f  add     rcx, 40h ; '@'
0x180043f43  mov     [rsp+1B0h+hLibModule], rcx
0x180043f48  mov     rax, [r15+50h]
0x180043f4c  mov     [rsp+1B0h+var_178], rax
0x180043f51  lea     rdx, [rsp+1B0h+hLibModule]
0x180043f56  lea     rcx, [rbp+0B0h+Src]
0x180043f5a  call    ?CreatePath@@YA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEBV?$basic_string_view@_WU?$char_traits@_W@std@@@2@0@Z; CreatePath(std::wstring_view const &,std::wstring_view const &)
0x180043f5f  nop
0x180043f60  mov     rcx, [rax+10h]
0x180043f64  cmp     qword ptr [rax+18h], 7
0x180043f69  jbe     short loc_180043F6E
0x180043f6b  mov     rax, [rax]
0x180043f6e  mov     [rsp+1B0h+hLibModule], rax
0x180043f73  mov     [rsp+1B0h+var_178], rcx
0x180043f78  lea     rdx, [rsp+1B0h+hLibModule]
0x180043f7d  mov     rcx, rdi; Src
0x180043f80  call    ?StripUNCPrefix@@YA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEBV?$basic_zstring_view@_W@wil@@@Z; StripUNCPrefix(wil::basic_zstring_view<wchar_t> const &)
0x180043f85  nop
0x180043f86  mov     [rsp+1B0h+var_160], ebx
0x180043f8a  lea     rcx, [rbp+0B0h+Src]; void *
0x180043f8e  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180043f93  mov     rcx, [rdi+10h]
0x180043f97  cmp     qword ptr [rdi+18h], 7
0x180043f9c  jbe     short loc_180043FA3
0x180043f9e  mov     rax, [rdi]
0x180043fa1  jmp     short loc_180043FA6
0x180043fa3  mov     rax, rdi
0x180043fa6  mov     [rsp+1B0h+hLibModule], rax
0x180043fab  mov     [rsp+1B0h+var_178], rcx
0x180043fb0  lea     rcx, [rsp+1B0h+hLibModule]
0x180043fb5  call    ?DirectoryExists@@YA_NAEBV?$basic_zstring_view@_W@wil@@@Z; DirectoryExists(wil::basic_zstring_view<wchar_t> const &)
0x180043fba  xor     r13d, r13d
0x180043fbd  test    al, al
0x180043fbf  jz      short loc_180043FD2
0x180043fc1  lea     rcx, aProductSandbox; "Product sandbox already exists. Return "...
0x180043fc8  call    ??$TraceInfo@$$V@LogAdapter@@YAXQEBD@Z; LogAdapter::TraceInfo<>(char const * const)
0x180043fcd  jmp     loc_180044660
0x180043fd2  cmp     qword ptr [rdi+18h], 7
0x180043fd7  jbe     short loc_180043FDE
0x180043fd9  mov     rcx, [rdi]
0x180043fdc  jmp     short loc_180043FE1
0x180043fde  mov     rcx, rdi; lpPathName
0x180043fe1  xor     edx, edx; lpSecurityAttributes
0x180043fe3  call    cs:__imp_CreateDirectoryW
0x180043fea  nop     dword ptr [rax+rax+00h]
0x180043fef  mov     rcx, [rbp+0B8h]; this
0x180043ff6  test    eax, eax
0x180043ff8  jz      loc_18004469D
0x180043ffe  xorps   xmm0, xmm0
0x180044001  movups  xmmword ptr [rbp+0B0h+var_D8], xmm0
0x180044005  movdqa  xmm1, cs:__xmm@00000000000000070000000000000000
0x18004400d  movdqu  [rbp+0B0h+var_C8], xmm1
0x180044012  mov     word ptr [rbp+0B0h+var_D8], r13w
0x180044017  mov     [rsp+1B0h+var_158], r13
0x18004401c  lea     rcx, [rsp+1B0h+var_158]
0x180044021  call    ?put@?$unique_any_t@V?$unique_storage@U?$resource_policy@PEA_WP6AJPEA_W@_E$1?STRAPI_Release@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEA_WPEA_W$0A@$$T@details@wil@@@details@wil@@@wil@@QEAAPEAPEA_WXZ
0x180044026  mov     r14, rax
0x180044029  mov     rbx, r13
0x18004402c  mov     [rsp+1B0h+hLibModule], rbx
0x180044031  mov     [rsp+1B0h+var_170], r13d
0x180044036  mov     [rbp+0B0h+var_100], r13d
0x18004403a  test    rax, rax
0x18004403d  jnz     short loc_18004404D
0x18004403f  mov     esi, 80070057h
0x180044044  mov     ecx, esi
0x180044046  call    ?CheckToBreakOnFailure@?$CBreakOnFailureT@VCEmptyType@@@@SAXJ@Z; CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(long)
0x18004404b  jmp     short loc_1800440B7
0x18004404d  lea     rcx, [rsp+1B0h+var_170]
0x180044052  call    ?IsMoUpdateTestsEnabled@?$CMoUpdateHelpersT@VCEmptyType@@@@SAJPEAH@Z; CMoUpdateHelpersT<CEmptyType>::IsMoUpdateTestsEnabled(int *)
0x180044057  mov     esi, eax
0x180044059  test    eax, eax
0x18004405b  jns     short loc_180044061
0x18004405d  mov     ecx, eax
0x18004405f  jmp     short loc_180044046
0x180044061  cmp     [rsp+1B0h+var_170], r13d
0x180044066  jz      short loc_1800440AE
0x180044068  lea     r9, [rbp+0B0h+var_100]
0x18004406c  call    ?ValueExists@?$CRegUtilT@PEA_WUCRegType@@$0A@$00@@SAJPEAUHKEY__@@PEB_W1PEAH@Z; CRegUtilT<wchar_t *,CRegType,0,1>::ValueExists(HKEY__ *,wchar_t const *,wchar_t const *,int *)
0x180044071  mov     esi, eax
0x180044073  test    eax, eax
0x180044075  js      short loc_18004405D
0x180044077  cmp     [rbp+0B0h+var_100], r13d
0x18004407b  jz      short loc_1800440AE
0x18004407d  lea     r9, [rsp+1B0h+hLibModule]
0x180044082  lea     r8, aUpdateagentlit; "UpdateAgentLiteCabPath"
0x180044089  lea     rdx, aSystemSetupMos_0; "SYSTEM\\Setup\\MoSetup"
0x180044090  call    ?GetValue@?$CRegUtilT@PEA_WUCRegType@@$0A@$00@@SAJPEAUHKEY__@@PEB_W1PEAPEA_WPEAK@Z; CRegUtilT<wchar_t *,CRegType,0,1>::GetValue(HKEY__ *,wchar_t const *,wchar_t const *,wchar_t * *,ulong *)
0x180044095  mov     esi, eax
0x180044097  test    eax, eax
0x180044099  jns     short loc_1800440A9
0x18004409b  mov     ecx, eax
0x18004409d  call    ?CheckToBreakOnFailure@?$CBreakOnFailureT@VCEmptyType@@@@SAXJ@Z; CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(long)
0x1800440a2  mov     rbx, [rsp+1B0h+hLibModule]
0x1800440a7  jmp     short loc_1800440B7
0x1800440a9  mov     rbx, [rsp+1B0h+hLibModule]
0x1800440ae  mov     rax, rbx
0x1800440b1  mov     rbx, r13
0x1800440b4  mov     [r14], rax
0x1800440b7  mov     ecx, esi
0x1800440b9  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x1800440be  test    rbx, rbx
0x1800440c1  jz      short loc_1800440EB
0x1800440c3  call    cs:__imp_GetProcessHeap
0x1800440ca  nop     dword ptr [rax+rax+00h]
0x1800440cf  mov     rcx, rax; hHeap
0x1800440d2  lea     r8, [rbx-4]; lpMem
0x1800440d6  xor     edx, edx; dwFlags
0x1800440d8  call    cs:__imp_HeapFree
0x1800440df  nop     dword ptr [rax+rax+00h]
0x1800440e4  xor     ecx, ecx
0x1800440e6  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x1800440eb  mov     rcx, [rbp+0B8h]; this
0x1800440f2  test    esi, esi
0x1800440f4  js      loc_1800446AF
0x1800440fa  mov     rcx, [rsp+1B0h+var_158]
0x1800440ff  test    rcx, rcx
0x180044102  jnz     loc_180044297
0x180044108  lea     rax, aDeploymentCab_0; ".Deployment.cab"
0x18004410f  mov     [rsp+1B0h+hLibModule], rax
0x180044114  mov     [rsp+1B0h+var_178], 0Fh
0x18004411d  lea     r8, [rsp+1B0h+hLibModule]
0x180044122  mov     rdx, r12
0x180044125  lea     rcx, [rbp+0B0h+Src]; Src
0x180044129  call    ??H@YA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEBV?$basic_string_view@_WU?$char_traits@_W@std@@@1@0@Z; operator+(std::wstring_view const &,std::wstring_view const &)
0x18004412e  nop
0x18004412f  lea     rax, [rbp+0B0h+Src]
0x180044133  mov     r14d, 7
0x180044139  cmp     [rbp+0B0h+var_E0], r14
0x18004413d  cmova   rax, [rbp+0B0h+Src]
0x180044142  mov     [rsp+1B0h+hLibModule], rax
0x180044147  mov     rax, [rbp+0B0h+var_E8]
0x18004414b  mov     [rsp+1B0h+var_178], rax
0x180044150  lea     rbx, [r15+20h]
0x180044154  cmp     [rbx+18h], r14
0x180044158  jbe     short loc_18004415F
0x18004415a  mov     rax, [rbx]
0x18004415d  jmp     short loc_180044162
0x18004415f  mov     rax, rbx
0x180044162  lea     rsi, [rbx+10h]
0x180044166  mov     qword ptr [rsp+1B0h+var_170], rax
0x18004416b  mov     rax, [rsi]
0x18004416e  mov     [rsp+1B0h+var_168], rax
0x180044173  lea     r8, [rsp+1B0h+hLibModule]
0x180044178  lea     rdx, [rsp+1B0h+var_170]
0x18004417d  lea     rcx, [rsp+1B0h+var_150]
0x180044182  call    ?CreatePath@@YA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEBV?$basic_string_view@_WU?$char_traits@_W@std@@@2@0@Z; CreatePath(std::wstring_view const &,std::wstring_view const &)
0x180044187  nop
0x180044188  mov     rcx, [rax+10h]
0x18004418c  cmp     [rax+18h], r14
0x180044190  jbe     short loc_180044195
0x180044192  mov     rax, [rax]
0x180044195  mov     [rsp+1B0h+hLibModule], rax
0x18004419a  mov     [rsp+1B0h+var_178], rcx
0x18004419f  lea     rdx, [rsp+1B0h+hLibModule]
0x1800441a4  lea     rcx, [rbp+0B0h+var_130]; Src
0x1800441a8  call    ?StripUNCPrefix@@YA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEBV?$basic_zstring_view@_W@wil@@@Z; StripUNCPrefix(wil::basic_zstring_view<wchar_t> const &)
0x1800441ad  mov     rdx, rax
0x1800441b0  lea     rcx, [rbp+0B0h+var_D8]
0x1800441b4  call    ??4?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x1800441b9  lea     rcx, [rbp+0B0h+var_130]; void *
0x1800441bd  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800441c2  nop
0x1800441c3  lea     rcx, [rsp+1B0h+var_150]; void *
0x1800441c8  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800441cd  mov     rcx, qword ptr [rbp+0B0h+var_C8]
0x1800441d1  lea     rax, [rbp+0B0h+var_D8]
0x1800441d5  cmp     qword ptr [rbp+0B0h+var_C8+8], r14
0x1800441d9  cmova   rax, [rbp+0B0h+var_D8]
0x1800441de  mov     [rsp+1B0h+hLibModule], rax
0x1800441e3  mov     [rsp+1B0h+var_178], rcx
0x1800441e8  lea     rcx, [rsp+1B0h+hLibModule]
0x1800441ed  call    ?FileExists@@YA_NAEBV?$basic_zstring_view@_W@wil@@@Z; FileExists(wil::basic_zstring_view<wchar_t> const &)
0x1800441f2  test    al, al
0x1800441f4  jnz     loc_18004428C
0x1800441fa  lea     rcx, aProductSpecifi; "Product specific Deployment.cab not fou"...
0x180044201  call    ??$TraceInfo@$$V@LogAdapter@@YAXQEBD@Z; LogAdapter::TraceInfo<>(char const * const)
0x180044206  lea     rax, aDeploymentCab; "Deployment.cab"
0x18004420d  mov     [rsp+1B0h+hLibModule], rax
0x180044212  mov     [rsp+1B0h+var_178], 0Eh
0x18004421b  cmp     [rbx+18h], r14
0x18004421f  jbe     short loc_180044224
0x180044221  mov     rbx, [rbx]
0x180044224  mov     qword ptr [rsp+1B0h+var_170], rbx
0x180044229  mov     rax, [rsi]
0x18004422c  mov     [rsp+1B0h+var_168], rax
0x180044231  lea     r8, [rsp+1B0h+hLibModule]
0x180044236  lea     rdx, [rsp+1B0h+var_170]
0x18004423b  lea     rcx, [rbp+0B0h+var_130]
0x18004423f  call    ?CreatePath@@YA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEBV?$basic_string_view@_WU?$char_traits@_W@std@@@2@0@Z; CreatePath(std::wstring_view const &,std::wstring_view const &)
0x180044244  nop
0x180044245  mov     rcx, [rax+10h]
0x180044249  cmp     [rax+18h], r14
0x18004424d  jbe     short loc_180044252
0x18004424f  mov     rax, [rax]
0x180044252  mov     [rsp+1B0h+hLibModule], rax
0x180044257  mov     [rsp+1B0h+var_178], rcx
0x18004425c  lea     rdx, [rsp+1B0h+hLibModule]
0x180044261  lea     rcx, [rsp+1B0h+var_150]; Src
0x180044266  call    ?StripUNCPrefix@@YA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEBV?$basic_zstring_view@_W@wil@@@Z; StripUNCPrefix(wil::basic_zstring_view<wchar_t> const &)
0x18004426b  mov     rdx, rax
0x18004426e  lea     rcx, [rbp+0B0h+var_D8]
0x180044272  call    ??4?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x180044277  lea     rcx, [rsp+1B0h+var_150]; void *
0x18004427c  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180044281  nop
0x180044282  lea     rcx, [rbp+0B0h+var_130]; void *
0x180044286  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18004428b  nop
0x18004428c  lea     rcx, [rbp+0B0h+Src]; void *
0x180044290  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180044295  jmp     short loc_1800442DA
0x180044297  mov     [rsp+1B0h+hLibModule], rcx
0x18004429c  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800442a0  inc     rax
0x1800442a3  cmp     [rcx+rax*2], r13w
0x1800442a8  jnz     short loc_1800442A0
0x1800442aa  mov     [rsp+1B0h+var_178], rax
0x1800442af  lea     rdx, [rsp+1B0h+hLibModule]
0x1800442b4  lea     rcx, [rsp+1B0h+var_150]; Src
0x1800442b9  call    ?StripUNCPrefix@@YA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEBV?$basic_zstring_view@_W@wil@@@Z; StripUNCPrefix(wil::basic_zstring_view<wchar_t> const &)
0x1800442be  mov     rdx, rax
0x1800442c1  lea     rcx, [rbp+0B0h+var_D8]
0x1800442c5  call    ??4?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x1800442ca  lea     rcx, [rsp+1B0h+var_150]; void *
0x1800442cf  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800442d4  mov     r14d, 7
0x1800442da  mov     rcx, qword ptr [rbp+0B0h+var_C8]
0x1800442de  lea     rax, [rbp+0B0h+var_D8]
0x1800442e2  cmp     qword ptr [rbp+0B0h+var_C8+8], r14
0x1800442e6  cmova   rax, [rbp+0B0h+var_D8]
0x1800442eb  mov     [rsp+1B0h+hLibModule], rax
0x1800442f0  mov     [rsp+1B0h+var_178], rcx
0x1800442f5  lea     rcx, [rsp+1B0h+hLibModule]
0x1800442fa  call    ?FileExists@@YA_NAEBV?$basic_zstring_view@_W@wil@@@Z; FileExists(wil::basic_zstring_view<wchar_t> const &)
0x1800442ff  test    al, al
0x180044301  jz      loc_1800446C4
0x180044307  lea     r8, [rbp+0B0h+var_D8]
0x18004430b  lea     rdx, aDeploymentCabF; "Deployment.cab found at [{}]"
0x180044312  mov     ecx, 1
0x180044317  call    ??$TraceAtLevel@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@LogAdapter@@YAXW4LogLevel@0@QEBDAEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; LogAdapter::TraceAtLevel<std::wstring>(LogAdapter::LogLevel,char const * const,std::wstring const &)
0x18004431c  mov     rcx, [rdi+10h]
0x180044320  cmp     [rdi+18h], r14
0x180044324  jbe     short loc_18004432B
0x180044326  mov     rax, [rdi]
0x180044329  jmp     short loc_18004432E
0x18004432b  mov     rax, rdi
0x18004432e  mov     [rsp+1B0h+hLibModule], rax
0x180044333  mov     [rsp+1B0h+var_178], rcx
0x180044338  lea     rdx, [rsp+1B0h+hLibModule]
0x18004433d  lea     rcx, [rbp+0B0h+lpPathName]
0x180044341  call    ?GetMetadataDirectory@UaLiteManager@@CA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$basic_zstring_view@_W@wil@@@Z; UaLiteManager::GetMetadataDirectory(wil::basic_zstring_view<wchar_t>)
0x180044346  nop
0x180044347  lea     rcx, [rbp+0B0h+lpPathName]
0x18004434b  cmp     [rbp+0B0h+var_A0], r14
0x18004434f  cmova   rcx, [rbp+0B0h+lpPathName]; lpPathName
0x180044354  xor     edx, edx; lpSecurityAttributes
0x180044356  call    cs:__imp_CreateDirectoryW
0x18004435d  nop     dword ptr [rax+rax+00h]
0x180044362  mov     rcx, [rbp+0B8h]; this
0x180044369  test    eax, eax
0x18004436b  jz      loc_180044708
0x180044371  mov     [rsp+1B0h+hLibModule], r13
0x180044376  lea     rcx, [rsp+1B0h+hLibModule]; HINSTANCE *
0x18004437b  call    ?DpxLoad@@YAJPEAPEAUHINSTANCE__@@@Z; DpxLoad(HINSTANCE__ * *)
0x180044380  mov     esi, eax
0x180044382  mov     ebx, 3
0x180044387  test    eax, eax
0x180044389  jns     short loc_1800443D6
0x18004438b  mov     [rbp+0B0h+var_100], eax
0x18004438e  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x180044395  test    rcx, rcx
0x180044398  jz      short loc_1800443D6
0x18004439a  lea     r9, aFailedToLoadDp_0; "Failed to load DPX"
0x1800443a1  mov     r8d, ebx
0x1800443a4  xor     edx, edx
  ... truncated ...
```
