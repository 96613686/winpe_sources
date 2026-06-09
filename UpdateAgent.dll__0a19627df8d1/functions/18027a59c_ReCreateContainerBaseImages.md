# ReCreateContainerBaseImages

- ea: `0x18027a59c`
- end: `0x18027b97c`
- name: `ReCreateContainerBaseImages`
- size: `5088`
- prototype: `__int64 __usercall@<rax>(LPCWSTR lpFileName@<rcx>, __int64, wchar_t *, __int64, __int64, __int64)`
- caller_count: `1`
- callee_count: `31`
- tags: `file_ops, registry_config, loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x180071520`

## callees

- `0x1800059d0`
- `0x1800059f4`
- `0x18000a0e8`
- `0x18000b508`
- `0x18000c4c4`
- `0x18000ce14`
- `0x1800692fc`
- `0x18008b38c`
- `0x18008b3bc`
- `0x18009338c`
- `0x1800bd064`
- `0x1800c9954`
- `0x1800ce5fc`
- `0x1800ce6b0`
- `0x18011b0fc`
- `0x18014c9a0`
- `0x180190844`
- `0x1801f250c`
- `0x18026fbc8`
- `0x1802702f8`
- `0x180270ba0`
- `0x180271160`
- `0x1802744c4`
- `0x180275838`
- `0x180276990`
- `0x180278b0c`
- `0x180278f00`
- `0x18027a59c`
- `0x18027d9a0`
- `0x18029ea98`
- `0x1802b1010`

## import_xrefs

- `ntdll!RtlFreeHeap` at `0x18027aa63`
- `ntdll!RtlFreeHeap` at `0x18027ab46`
- `ntdll!RtlFreeHeap` at `0x18027ac70`
- `ntdll!RtlFreeHeap` at `0x18027ae84`
- `ntdll!RtlFreeHeap` at `0x18027b004`
- `ntdll!RtlFreeHeap` at `0x18027b194`
- `ntdll!RtlFreeHeap` at `0x18027b342`
- `ntdll!RtlFreeHeap` at `0x18027b523`
- `ntdll!RtlFreeHeap` at `0x18027b7b7`
- `ntdll!RtlFreeHeap` at `0x18027b901`
- `ntdll!RtlFreeHeap` at `0x18027aa63`
- `ntdll!RtlFreeHeap` at `0x18027ab46`
- `ntdll!RtlFreeHeap` at `0x18027ac70`
- `ntdll!RtlFreeHeap` at `0x18027ae84`
- `ntdll!RtlFreeHeap` at `0x18027b004`
- `ntdll!RtlFreeHeap` at `0x18027b194`
- `ntdll!RtlFreeHeap` at `0x18027b342`
- `ntdll!RtlFreeHeap` at `0x18027b523`
- `ntdll!RtlFreeHeap` at `0x18027b7b7`
- `ntdll!RtlFreeHeap` at `0x18027b901`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x18027a66e`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x18027a66e`
- `api-ms-win-core-libraryloader-l1-1-0!FreeLibrary` at `0x18027ae0b`
- `api-ms-win-core-libraryloader-l1-1-0!FreeLibrary` at `0x18027af8b`
- `api-ms-win-core-libraryloader-l1-1-0!FreeLibrary` at `0x18027b11b`
- `api-ms-win-core-libraryloader-l1-1-0!FreeLibrary` at `0x18027b2c9`
- `api-ms-win-core-libraryloader-l1-1-0!FreeLibrary` at `0x18027b4aa`
- `api-ms-win-core-libraryloader-l1-1-0!FreeLibrary` at `0x18027b73e`
- `api-ms-win-core-libraryloader-l1-1-0!FreeLibrary` at `0x18027b888`
- `api-ms-win-core-libraryloader-l1-1-0!FreeLibrary` at `0x18027ae0b`
- `api-ms-win-core-libraryloader-l1-1-0!FreeLibrary` at `0x18027af8b`
- `api-ms-win-core-libraryloader-l1-1-0!FreeLibrary` at `0x18027b11b`
- `api-ms-win-core-libraryloader-l1-1-0!FreeLibrary` at `0x18027b2c9`
- `api-ms-win-core-libraryloader-l1-1-0!FreeLibrary` at `0x18027b4aa`
- `api-ms-win-core-libraryloader-l1-1-0!FreeLibrary` at `0x18027b73e`
- `api-ms-win-core-libraryloader-l1-1-0!FreeLibrary` at `0x18027b888`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18027a9ea`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18027b256`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18027b413`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18027b6a7`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18027b7f1`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18027a9ea`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18027b256`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18027b413`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18027b6a7`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18027b7f1`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18027b26a`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18027b427`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18027b6bb`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18027b805`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18027b26a`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18027b427`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18027b6bb`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18027b805`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18027a9fe`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18027a9fe`

## string_xrefs

- `0x18027acc2`: `RecreateContainerBaseImages`
- `0x18027ad9b`: `Unable to load turbostack.dll`
- `0x18027b08b`: `Failed to create path for host Packages.`
- `0x18027aac2`: `Failed to copy ssu path.`
- `0x18027abec`: `Failed to get SSU Path`
- `0x18027b39c`: `Professional.xml`
- `0x18027a69a`: `Invalid hostRootPath encountered`
- `0x18027a742`: `Missing top level package or configDirs for layerIds`
- `0x18027a93f`: `Failed to create path for host windows dir.`
- `0x18027b63f`: `Failed to recreate container base layer: {}`

## pseudocode

```c
// Hidden C++ exception states: #wind=47
__int64 __fastcall ReCreateContainerBaseImages(
        WCHAR *lpFileName,
        __int64 a2,
        void (__fastcall ***a3)(_QWORD),
        struct _GUID **a4,
        __int64 a5,
        wchar_t *a6,
        __int64 a7,
        struct _GUID *a8,
        struct _GUID *a9)
{
  char FileAttributesW; // al
  const char *v14; // r9
  __int64 result; // rax
  __int64 v16; // rdx
  int v17; // eax
  unsigned int v18; // ebx
  __int64 v19; // rdx
  unsigned int v20; // ebx
  __int64 v21; // rax
  unsigned __int64 v22; // rsi
  SIZE_T v23; // rbx
  HANDLE ProcessHeap; // rax
  void *v25; // rax
  int v26; // eax
  int v27; // eax
  unsigned int v28; // ebx
  int v29; // eax
  wchar_t *v30; // rbx
  unsigned __int64 v31; // rsi
  int SsuPath; // eax
  unsigned int v33; // r14d
  int v34; // eax
  int v35; // eax
  int Turbostack; // eax
  unsigned int v37; // r14d
  const struct std::nothrow_t *v38; // rdx
  int v39; // eax
  __int64 v40; // rdx
  char IsStringPrefixEqualByOrdinalCase; // al
  char v42; // cl
  int ConfigFilePaths; // eax
  unsigned int v44; // esi
  const struct std::nothrow_t *v45; // rdx
  int v46; // eax
  char **v47; // rsi
  int v48; // eax
  unsigned int v49; // ebx
  __int64 v50; // rdx
  unsigned int v51; // ebx
  const struct std::nothrow_t *v52; // rdx
  int v53; // eax
  const char *v54; // r9
  int DirectSystem; // eax
  unsigned int v56; // esi
  void *v57; // rbx
  HANDLE v58; // rax
  const struct std::nothrow_t *v59; // rdx
  int v60; // eax
  int v61; // eax
  const wchar_t *v62; // r15
  const wchar_t *v63; // r8
  wchar_t *v64; // rbx
  void (__fastcall ***v65)(_QWORD); // rsi
  int v66; // eax
  unsigned int v67; // r14d
  HANDLE v68; // rax
  const struct std::nothrow_t *v69; // rdx
  int v70; // eax
  const wchar_t *v71; // r14
  GUID v72; // xmm6
  int v73; // eax
  int v74; // eax
  unsigned int v75; // r14d
  HANDLE v76; // rax
  const struct std::nothrow_t *v77; // rdx
  int v78; // eax
  HANDLE v79; // rax
  const struct std::nothrow_t *v80; // rdx
  int v81; // eax
  int v82; // [rsp+20h] [rbp-A28h]
  int v83; // [rsp+20h] [rbp-A28h]
  int v84; // [rsp+20h] [rbp-A28h]
  __int128 v85; // [rsp+50h] [rbp-9F8h] BYREF
  wchar_t *v86; // [rsp+60h] [rbp-9E8h]
  void (__fastcall ***v87)(_QWORD); // [rsp+68h] [rbp-9E0h] BYREF
  char v88[8]; // [rsp+70h] [rbp-9D8h] BYREF
  void **v89; // [rsp+78h] [rbp-9D0h]
  struct _GUID *v90; // [rsp+80h] [rbp-9C8h] BYREF
  struct _GUID v91; // [rsp+90h] [rbp-9B8h] BYREF
  __int128 v92; // [rsp+A0h] [rbp-9A8h] BYREF
  __int64 v93; // [rsp+B0h] [rbp-998h]
  struct _GUID v94; // [rsp+C0h] [rbp-988h] BYREF
  struct _GUID *v95; // [rsp+D0h] [rbp-978h]
  int v96[4]; // [rsp+D8h] [rbp-970h] BYREF
  __int64 v97; // [rsp+E8h] [rbp-960h]
  __int128 v98; // [rsp+F0h] [rbp-958h] BYREF
  __int64 v99; // [rsp+100h] [rbp-948h]
  __int64 v100; // [rsp+108h] [rbp-940h]
  LPVOID lpMem; // [rsp+110h] [rbp-938h] BYREF
  void (__fastcall ***v102)(_QWORD); // [rsp+118h] [rbp-930h] BYREF
  int v103; // [rsp+120h] [rbp-928h] BYREF
  PVOID P; // [rsp+128h] [rbp-920h] BYREF
  char v105[8]; // [rsp+130h] [rbp-918h] BYREF
  HMODULE hLibModule; // [rsp+138h] [rbp-910h]
  struct _GUID Buf1; // [rsp+140h] [rbp-908h] BYREF
  int v108[10]; // [rsp+150h] [rbp-8F8h] BYREF
  char **v109; // [rsp+178h] [rbp-8D0h]
  _BYTE v110[64]; // [rsp+190h] [rbp-8B8h] BYREF
  void *v111[259]; // [rsp+1D0h] [rbp-878h] BYREF
  __int64 v112; // [rsp+9E8h] [rbp-60h]
  wil::details::in1diag3 *retaddr; // [rsp+A48h] [rbp+0h]

  v100 = -2;
  v87 = a3;
  *(_QWORD *)&v91.Data1 = a2;
  lpMem = lpFileName;
  v102 = a3;
  *(_QWORD *)&v94.Data1 = a7;
  v95 = a8;
  v90 = a9;
  if ( !*(_QWORD *)&LogAdapter::g_Logger && IsWdsLoggerSetup((HINSTANCE *)lpFileName) )
  {
    *(_QWORD *)&LogAdapter::g_Logger = &wdsLogger;
    vpfnCustomLogging = (void (*)(unsigned int, const char *))CbsCustomLogging;
  }
  FileAttributesW = GetFileAttributesW(lpFileName);
  try
  {
    if ( (FileAttributesW & 0x10) == 0 )
    {
      v103 = -2147024809;
      if ( *(_QWORD *)&LogAdapter::g_Logger )
      {
        LogAdapter::Logger::LogNumObjects<>(
          *(__int64 *)&LogAdapter::g_Logger,
          0,
          3,
          (struct Windows::Rtl::IRtlFormattedOutputStream *)"Invalid hostRootPath encountered");
        lpMem = &v103;
        LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
          *(__int64 *)&LogAdapter::g_Logger,
          1,
          3,
          (struct Windows::Rtl::IRtlFormattedOutputStream *)": {}",
          (__int64)&lpMem);
      }
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x8B5,
        (unsigned int)"onecore\\base\\cbs\\container\\servicingcontainerhelper.cpp",
        (const char *)0x80070057LL,
        v82);
      return 2147942487LL;
    }
    if ( a2 && a3 )
    {
      result = (__int64)a4[1];
    }
    else
    {
      result = (__int64)a4[1];
      if ( *(_QWORD *)(a5 + 8) != result )
      {
        v103 = -2147024809;
        if ( *(_QWORD *)&LogAdapter::g_Logger )
        {
          LogAdapter::Logger::LogNumObjects<>(
            *(__int64 *)&LogAdapter::g_Logger,
            0,
            3,
            (struct Windows::Rtl::IRtlFormattedOutputStream *)"Missing top level package or configDirs for layerIds");
          lpMem = &v103;
          LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
            *(__int64 *)&LogAdapter::g_Logger,
            1,
            3,
            (struct Windows::Rtl::IRtlFormattedOutputStream *)": {}",
            (__int64)&lpMem);
        }
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x8B7,
          (unsigned int)"onecore\\base\\cbs\\container\\servicingcontainerhelper.cpp",
          (const char *)0x80070057LL,
          v82);
        return 2147942487LL;
      }
    }
    if ( !result )
      return result;
    if ( result != 1 )
    {
      v103 = -2147418113;
      if ( *(_QWORD *)&LogAdapter::g_Logger )
      {
        LogAdapter::Logger::LogNumObjects<>(
          *(__int64 *)&LogAdapter::g_Logger,
          0,
          3,
          (struct Windows::Rtl::IRtlFormattedOutputStream *)"Only one layer is supported");
        lpMem = &v103;
        LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
          *(__int64 *)&LogAdapter::g_Logger,
          1,
          3,
          (struct Windows::Rtl::IRtlFormattedOutputStream *)": {}",
          (__int64)&lpMem);
      }
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x8C8,
        (unsigned int)"onecore\\base\\cbs\\container\\servicingcontainerhelper.cpp",
        (const char *)0x8000FFFFLL,
        v82);
      return 2147549183LL;
    }
    Buf1 = **a4;
    if ( memcmp_0(&Buf1, &CMS_CLIENT_PROFESSIONAL_LAYER_ID, 0x10u) )
    {
      v103 = -2147418113;
      if ( *(_QWORD *)&LogAdapter::g_Logger )
      {
        LogAdapter::Logger::LogNumObjects<>(
          *(__int64 *)&LogAdapter::g_Logger,
          0,
          3,
          (struct Windows::Rtl::IRtlFormattedOutputStream *)"Only professional is supported");
        lpMem = &v103;
        LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
          *(__int64 *)&LogAdapter::g_Logger,
          1,
          3,
          (struct Windows::Rtl::IRtlFormattedOutputStream *)": {}",
          (__int64)&lpMem);
      }
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x8CC,
        (unsigned int)"onecore\\base\\cbs\\container\\servicingcontainerhelper.cpp",
        (const char *)0x8000FFFFLL,
        v82);
      return 2147549183LL;
    }
    v85 = 0;
    v86 = 0;
    v17 = Windows::StringUtil::Rtl::CombineAndNullTerminateWin32Paths<wchar_t const *,wchar_t [8]>(
            (__int64 *)&lpMem,
            v16,
            (unsigned __int64 *)&v85);
    v18 = v17;
    if ( v17 < 0 )
    {
      v103 = v17;
      if ( *(_QWORD *)&LogAdapter::g_Logger )
      {
        LogAdapter::Logger::LogNumObjects<>(
          *(__int64 *)&LogAdapter::g_Logger,
          0,
          3,
          (struct Windows::Rtl::IRtlFormattedOutputStream *)"Failed to create path for host windows dir.");
        lpMem = &v103;
        LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatNtStatusWrapper<long>>(
          *(__int64 *)&LogAdapter::g_Logger,
          v19,
          3,
          (struct Windows::Rtl::IRtlFormattedOutputStream *)": {}",
          (__int64)&lpMem);
      }
      v20 = wil::details::in1diag3::Return_NtStatus(
              retaddr,
              (void *)0x8D0,
              (unsigned int)"onecore\\base\\cbs\\container\\servicingcontainerhelper.cpp",
              (const char *)v18,
              v82);
      if ( v86 )
        anonymous_namespace_::OurRtlFreeStringRoutine(v86);
      return v20;
    }
    P = 0;
    if ( a6 )
    {
      v21 = -1;
      do
        ++v21;
      while ( a6[v21] );
      v22 = v21 + 1;
      v23 = 2 * (v21 + 1);
      ProcessHeap = GetProcessHeap();
      v25 = HeapAlloc(ProcessHeap, 0, v23);
      if ( !P )
      {
        P = v25;
        if ( !v25 )
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x8D7,
            (unsigned int)"onecore\\base\\cbs\\container\\servicingcontainerhelper.cpp",
            (const char *)0x8007000ELL,
            v82);
          if ( P )
          {
            LOBYTE(v26) = RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, P);
            if ( !v26 )
              __fastfail(7u);
            P = 0;
          }
          if ( v86 )
            anonymous_namespace_::OurRtlFreeStringRoutine(v86);
          return 2147942414LL;
        }
        v27 = StringCchCopyW((wchar_t *)v25, v22, a6);
        v28 = v27;
        if ( v27 < 0 )
        {
          v103 = v27;
          if ( *(_QWORD *)&LogAdapter::g_Logger )
          {
            LogAdapter::Logger::LogNumObjects<>(
              *(__int64 *)&LogAdapter::g_Logger,
              0,
              3,
              (struct Windows::Rtl::IRtlFormattedOutputStream *)"Failed to copy ssu path.");
            lpMem = &v103;
            LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
              *(__int64 *)&LogAdapter::g_Logger,
              1,
              3,
              (struct Windows::Rtl::IRtlFormattedOutputStream *)": {}",
              (__int64)&lpMem);
          }
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x8D9,
            (unsigned int)"onecore\\base\\cbs\\container\\servicingcontainerhelper.cpp",
            (const char *)v28,
            v82);
          if ( P )
          {
            LOBYTE(v29) = RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, P);
            if ( !v29 )
              __fastfail(7u);
            P = 0;
          }
          if ( v86 )
            anonymous_namespace_::OurRtlFreeStringRoutine(v86);
          return v28;
        }
        v30 = v86;
        v31 = v85;
        goto LABEL_67;
      }
LABEL_227:
      INTERNAL_ERROR_ACTION(-1073741595);
      goto LABEL_228;
    }
    v30 = v86;
    v31 = v85;
    if ( v86 && (*((_QWORD *)&v85 + 1) - (_QWORD)v85 < 2u || v86[(unsigned __int64)v85 >> 1]) )
      goto LABEL_227;
    SsuPath = GetSsuPath(v86, a2, &P);
    v33 = SsuPath;
    if ( SsuPath >= 0 )
    {
LABEL_67:
      v111[0] = 0;
      v111[1] = (void *)-1LL;
      v112 = 0;
      v35 = EtwLogger::Start((EtwLogger *)v111, L"RecreateContainerBaseImages");
      if ( v35 < 0 )
      {
        v103 = v35;
        if ( *(_QWORD *)&LogAdapter::g_Logger )
        {
          LogAdapter::Logger::LogNumObjects<Windows::AutoGenericHandle<wchar_t *,0,&void Windows::Detail::CloseWithCoTaskMemFree<wchar_t>(wchar_t *)>>(
            *(__int64 *)&LogAdapter::g_Logger,
            0,
            3,
            (struct Windows::Rtl::IRtlFormattedOutputStream *)"Failed to start ETW tracing {}",
            (__int64)off_1802BDE78);
          lpMem = &v103;
          LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
            *(__int64 *)&LogAdapter::g_Logger,
            1,
            3,
            (struct Windows::Rtl::IRtlFormattedOutputStream *)": {}",
            (__int64)&lpMem);
        }
      }
      v88[0] = 1;
      v89 = v111;
      v105[0] = 0;
      hLibModule = 0;
      Turbostack = LoadTurbostack(P, v105);
      v37 = Turbostack;
      if ( Turbostack < 0 )
      {
        v103 = Turbostack;
        if ( *(_QWORD *)&LogAdapter::g_Logger )
        {
          LogAdapter::Logger::LogNumObjects<>(
            *(__int64 *)&LogAdapter::g_Logger,
            0,
            3,
            (struct Windows::Rtl::IRtlFormattedOutputStream *)"Unable to load turbostack.dll");
          lpMem = &v103;
          LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
            *(__int64 *)&LogAdapter::g_Logger,
            1,
            3,
            (struct Windows::Rtl::IRtlFormattedOutputStream *)": {}",
            (__int64)&lpMem);
        }
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x8E9,
          (unsigned int)"onecore\\base\\cbs\\container\\servicingcontainerhelper.cpp",
          (const char *)v37,
          v82);
        if ( hLibModule )
          FreeLibrary(hLibModule);
        Windows::Detail::OnBlockExitImpl__ReCreateContainerBaseImages_::_3_::_lambda_1___::_OnBlockExitImpl__ReCreateContainerBaseImages_::_3_::_lambda_1___(v88);
        EtwLogger::Stop((EtwLogger *)v111);
        if ( v112 )
        {
          operator delete((void *)(v112 - 8), v38);
          v112 = 0;
        }
        if ( v111[0] )
        {
          operator delete(v111[0], v38);
          v111[0] = 0;
        }
        if ( P )
        {
          LOBYTE(v39) = RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, P);
          if ( !v39 )
            __fastfail(7u);
          P = 0;
        }
        if ( v30 )
          anonymous_namespace_::OurRtlFreeStringRoutine(v30);
        return v37;
      }
      CCbsStringArray::CCbsStringArray((CCbsStringArray *)v108);
      if ( *(_QWORD *)(a5 + 8) )
      {
        v47 = *(char ***)a5;
LABEL_109:
        v92 = 0;
        v93 = 0;
        v48 = Windows::StringUtil::Rtl::CombineAndNullTerminateWin32Paths<Windows::Auto<_LUNICODE_STRING>,wchar_t const *>(
                &v85,
                v40,
                (unsigned __int64 *)&v92);
        v49 = v48;
        if ( v48 >= 0 )
        {
          v98 = 0;
          v99 = 0;
          *(_OWORD *)v96 = 0;
          v97 = 0;
          CCbsStringArray::CCbsStringArray((CCbsStringArray *)v110);
          v87 = 0;
          wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<wchar_t *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>>>(
            &lpMem,
            *v47,
            0xFFFFFFFFFFFFFFFFuLL,
            v54);
          DirectSystem = RtlGetDirectSystem(&v87);
          v56 = DirectSystem;
          if ( DirectSystem >= 0 )
          {
            v61 = memcmp_0(&Buf1, &CMS_CLIENT_PROFESSIONAL_LAYER_ID, 0x10u);
            v62 = L"Professional.xml";
            v63 = L"Professional.xml";
            if ( v61 )
              v63 = &String2;
            v64 = (wchar_t *)lpMem;
            v65 = v87;
            v66 = ProcessContainerConfigFile(
                    (_DWORD)v87,
                    (_DWORD)lpMem,
                    (_DWORD)v63,
                    (unsigned int)&v98,
                    (__int64)v96,
                    (__int64)v110);
            v67 = v66;
            if ( v66 >= 0 )
            {
              v71 = (const wchar_t *)P;
              if ( !memcmp_0(&Buf1, &CMS_CLIENT_PROFESSIONAL_LAYER_ID, 0x10u) )
                v72 = (GUID)xmmword_18034FE38;
              else
                v72 = GUID_NULL;
              v73 = memcmp_0(&Buf1, &CMS_CLIENT_PROFESSIONAL_LAYER_ID, 0x10u);
              v94 = *(struct _GUID *)*(_QWORD *)&v94.Data1;
              v91 = v72;
              if ( v73 )
                v62 = &String2;
              v74 = CreateContainerBaseImageInternal(v64, v62, &v91, &v94, 1, 1, v71, v90, v95);
              v75 = v74;
              if ( v74 >= 0 )
              {
                if ( v64 )
                {
                  v79 = GetProcessHeap();
                  HeapFree(v79, 0, v64);
                }
                if ( v65 )
                  (**v65)(v65);
                CCbsArrayBase<wchar_t *,CCbsStringArray>::~CCbsArrayBase<wchar_t *,CCbsStringArray>(v110);
                if ( v97 )
                  anonymous_namespace_::OurRtlFreeStringRoutine(v97);
                if ( v99 )
                  anonymous_namespace_::OurRtlFreeStringRoutine(v99);
                if ( v93 )
                  anonymous_namespace_::OurRtlFreeStringRoutine(v93);
                CCbsArrayBase<wchar_t *,CCbsStringArray>::~CCbsArrayBase<wchar_t *,CCbsStringArray>(v108);
                if ( hLibModule )
                  FreeLibrary(hLibModule);
                Windows::Detail::OnBlockExitImpl__ReCreateContainerBaseImages_::_3_::_lambda_1___::_OnBlockExitImpl__ReCreateContainerBaseImages_::_3_::_lambda_1___(v88);
                EtwLogger::Stop((EtwLogger *)v111);
                if ( v112 )
                {
                  operator delete((void *)(v112 - 8), v80);
                  v112 = 0;
                }
                if ( v111[0] )
                {
                  operator delete(v111[0], v80);
                  v111[0] = 0;
                }
                if ( P )
                {
                  LOBYTE(v81) = RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, P);
                  if ( !v81 )
                    __fastfail(7u);
                  P = 0;
                }
                if ( v86 )
                  anonymous_namespace_::OurRtlFreeStringRoutine(v86);
                return 0;
              }
              else
              {
                v103 = v74;
                if ( *(_QWORD *)&LogAdapter::g_Logger )
                {
                  LogAdapter::Logger::LogNumObjects<_GUID>(
                    *(_QWORD *)&LogAdapter::g_Logger,
                    0,
                    3,
                    "Failed to recreate container base layer: {}");
                  v90 = (struct _GUID *)&v103;
                  LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
                    *(__int64 *)&LogAdapter::g_Logger,
                    1,
                    3,
                    (struct Windows::Rtl::IRtlFormattedOutputStream *)": {}",
                    (__int64)&v90);
                }
                wil::details::in1diag3::Return_Hr(
                  retaddr,
                  (void *)0x918,
                  (unsigned int)"onecore\\base\\cbs\\container\\servicingcontainerhelper.cpp",
                  (const char *)v75,
                  v84);
                if ( v64 )
                {
                  v76 = GetProcessHeap();
                  HeapFree(v76, 0, v64);
                }
                if ( v65 )
                  (**v65)(v65);
                CCbsArrayBase<wchar_t *,CCbsStringArray>::~CCbsArrayBase<wchar_t *,CCbsStringArray>(v110);
                if ( v97 )
                  anonymous_namespace_::OurRtlFreeStringRoutine(v97);
                if ( v99 )
                  anonymous_namespace_::OurRtlFreeStringRoutine(v99);
                if ( v93 )
                  anonymous_namespace_::OurRtlFreeStringRoutine(v93);
                CCbsArrayBase<wchar_t *,CCbsStringArray>::~CCbsArrayBase<wchar_t *,CCbsStringArray>(v108);
                if ( hLibModule )
                  FreeLibrary(hLibModule);
                Windows::Detail::OnBlockExitImpl__ReCreateContainerBaseImages_::_3_::_lambda_1___::_OnBlockExitImpl__ReCreateContainerBaseImages_::_3_::_lambda_1___(v88);
                EtwLogger::Stop((EtwLogger *)v111);
                if ( v112 )
                {
                  operator delete((void *)(v112 - 8), v77);
                  v112 = 0;
                }
                if ( v111[0] )
                {
                  operator delete(v111[0], v77);
                  v111[0] = 0;
                }
                if ( P )
                {
                  LOBYTE(v78) = RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, P);
                  if ( !v78 )
                    __fastfail(7u);
                  P = 0;
                }
                if ( v86 )
                  anonymous_namespace_::OurRtlFreeStringRoutine(v86);
                return v75;
              }
            }
            else
            {
              wil::details::in1diag3::Return_Hr(
                retaddr,
                (void *)0x909,
                (unsigned int)"onecore\\base\\cbs\\container\\servicingcontainerhelper.cpp",
                (const char *)(unsigned int)v66,
                v83);
              if ( v64 )
              {
                v68 = GetProcessHeap();
                HeapFree(v68, 0, v64);
              }
              if ( v65 )
                (**v65)(v65);
              CCbsArrayBase<wchar_t *,CCbsStringArray>::~CCbsArrayBase<wchar_t *,CCbsStringArray>(v110);
              if ( v97 )
                anonymous_namespace_::OurRtlFreeStringRoutine(v97);
              if ( v99 )
                anonymous_namespace_::OurRtlFreeStringRoutine(v99);
              if ( v93 )
                anonymous_namespace_::OurRtlFreeStringRoutine(v93);
              CCbsArrayBase<wchar_t *,CCbsStringArray>::~CCbsArrayBase<wchar_t *,CCbsStringArray>(v108);
              if ( hLibModule )
                FreeLibrary(hLibModule);
              Windows::Detail::OnBlockExitImpl__ReCreateContainerBaseImages_::_3_::_lambda_1___::_OnBlockExitImpl__ReCreateContainerBaseImages_::_3_::_lambda_1___(v88);
              EtwLogger::Stop((EtwLogger *)v111);
              if ( v112 )
              {
                operator delete((void *)(v112 - 8), v69);
                v112 = 0;
              }
              if ( v111[0] )
              {
                operator delete(v111[0], v69);
                v111[0] = 0;
              }
              if ( P )
              {
                LOBYTE(v70) = RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, P);
                if ( !v70 )
                  __fastfail(7u);
                P = 0;
              }
              if ( v86 )
                anonymous_namespace_::OurRtlFreeStringRoutine(v86);
              return v67;
            }
          }
          else
          {
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)0x907,
              (unsigned int)"onecore\\base\\cbs\\container\\servicingcontainerhelper.cpp",
              (const char *)(unsigned int)DirectSystem,
              v82);
            v57 = lpMem;
            if ( lpMem )
            {
              v58 = GetProcessHeap();
              HeapFree(v58, 0, v57);
            }
            if ( v87 )
              (**v87)(v87);
            CCbsArrayBase<wchar_t *,CCbsStringArray>::~CCbsArrayBase<wchar_t *,CCbsStringArray>(v110);
            if ( v93 )
              anonymous_namespace_::OurRtlFreeStringRoutine(v93);
            CCbsArrayBase<wchar_t *,CCbsStringArray>::~CCbsArrayBase<wchar_t *,CCbsStringArray>(v108);
            if ( hLibModule )
              FreeLibrary(hLibModule);
            Windows::Detail::OnBlockExitImpl__ReCreateContainerBaseImages_::_3_::_lambda_1___::_OnBlockExitImpl__ReCreateContainerBaseImages_::_3_::_lambda_1___(v88);
            EtwLogger::Stop((EtwLogger *)v111);
            if ( v112 )
            {
              operator delete((void *)(v112 - 8), v59);
              v112 = 0;
            }
            if ( v111[0] )
            {
              operator delete(v111[0], v59);
              v111[0] = 0;
            }
            if ( P )
            {
              LOBYTE(v60) = RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, P);
              if ( !v60 )
                __fastfail(7u);
              P = 0;
            }
            if ( v86 )
              anonymous_namespace_::OurRtlFreeStringRoutine(v86);
            return v56;
          }
        }
        else
        {
          v103 = v48;
          if ( *(_QWORD *)&LogAdapter::g_Logger )
          {
            LogAdapter::Logger::LogNumObjects<>(
              *(__int64 *)&LogAdapter::g_Logger,
              0,
              3,
              (struct Windows::Rtl::IRtlFormattedOutputStream *)"Failed to create path for host Packages.");
            *(_QWORD *)&v91.Data1 = &v103;
            LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatNtStatusWrapper<long>>(
              *(__int64 *)&LogAdapter::g_Logger,
              v50,
              3,
              (struct Windows::Rtl::IRtlFormattedOutputStream *)": {}",
              (__int64)&v91);
          }
          v51 = wil::details::in1diag3::Return_NtStatus(
                  retaddr,
                  (void *)0x8FC,
                  (unsigned int)"onecore\\base\\cbs\\container\\servicingcontainerhelper.cpp",
                  (const char *)v49,
                  v82);
          if ( v93 )
            anonymous_namespace_::OurRtlFreeStringRoutine(v93);
          CCbsArrayBase<wchar_t *,CCbsStringArray>::~CCbsArrayBase<wchar_t *,CCbsStringArray>(v108);
          if ( hLibModule )
            FreeLibrary(hLibModule);
          Windows::Detail::OnBlockExitImpl__ReCreateContainerBaseImages_::_3_::_lambda_1___::_OnBlockExitImpl__ReCreateContainerBaseImages_::_3_::_lambda_1___(v88);
          EtwLogger::Stop((EtwLogger *)v111);
          if ( v112 )
          {
            operator delete((void *)(v112 - 8), v52);
            v112 = 0;
          }
          if ( v111[0] )
          {
            operator delete(v111[0], v52);
            v111[0] = 0;
          }
          if ( P )
          {
            LOBYTE(v53) = RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, P);
            if ( !v53 )
              __fastfail(7u);
            P = 0;
          }
          if ( v86 )
            anonymous_namespace_::OurRtlFreeStringRoutine(v86);
          return v51;
        }
      }
      if ( !v87
        || (IsStringPrefixEqualByOrdinalCase = Windows::StringUtil::IsStringPrefixEqualByOrdinalCaseInvariant<wchar_t const *,wchar_t const *>(
                                                 &off_1802BDEA0,
                                                 &v102),
            v42 = 1,
            !IsStringPrefixEqualByOrdinalCase) )
      {
        v42 = 0;
      }
      if ( !v30 || *((_QWORD *)&v85 + 1) - v31 >= 2 && !v30[v31 >> 1] )
      {
        ConfigFilePaths = GetConfigFilePaths(
                            a4,
                            (LoadHelper *)v105,
                            (__int64)v30,
                            *(__int64 (**)(void))&v91.Data1,
                            v42,
                            v108);
        v44 = ConfigFilePaths;
        if ( ConfigFilePaths < 0 )
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x8F1,
            (unsigned int)"onecore\\base\\cbs\\container\\servicingcontainerhelper.cpp",
            (const char *)(unsigned int)ConfigFilePaths,
            v82);
          CCbsArrayBase<wchar_t *,CCbsStringArray>::~CCbsArrayBase<wchar_t *,CCbsStringArray>(v108);
          if ( hLibModule )
            FreeLibrary(hLibModule);
          Windows::Detail::OnBlockExitImpl__ReCreateContainerBaseImages_::_3_::_lambda_1___::_OnBlockExitImpl__ReCreateContainerBaseImages_::_3_::_lambda_1___(v88);
          EtwLogger::Stop((EtwLogger *)v111);
          if ( v112 )
          {
            operator delete((void *)(v112 - 8), v45);
            v112 = 0;
          }
          if ( v111[0] )
          {
            operator delete(v111[0], v45);
            v111[0] = 0;
          }
          if ( P )
          {
            LOBYTE(v46) = RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, P);
            if ( !v46 )
              __fastfail(7u);
            P = 0;
          }
          if ( v30 )
            anonymous_namespace_::OurRtlFreeStringRoutine(v30);
          return v44;
        }
        v47 = v109;
        goto LABEL_109;
      }
LABEL_228:
      INTERNAL_ERROR_ACTION(-1073741595);
      JUMPOUT(0x18027B97ALL);
    }
    v103 = SsuPath;
    if ( *(_QWORD *)&LogAdapter::g_Logger )
    {
      LogAdapter::Logger::LogNumObjects<>(
        *(__int64 *)&LogAdapter::g_Logger,
        0,
        3,
        (struct Windows::Rtl::IRtlFormattedOutputStream *)"Failed to get SSU Path");
      lpMem = &v103;
      LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
        *(__int64 *)&LogAdapter::g_Logger,
        1,
        3,
        (struct Windows::Rtl::IRtlFormattedOutputStream *)": {}",
        (__int64)&lpMem);
    }
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x8DD,
      (unsigned int)"onecore\\base\\cbs\\container\\servicingcontainerhelper.cpp",
      (const char *)v33,
      v82);
    if ( P )
    {
      LOBYTE(v34) = RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, P);
      if ( !v34 )
        __fastfail(7u);
      P = 0;
    }
    if ( v30 )
      anonymous_namespace_::OurRtlFreeStringRoutine(v30);
    result = v33;
  }
  catch ( ... )
  {
    return (unsigned int)wil::details::in1diag3::Return_CaughtException(
                           retaddr,
                           (void *)0x91C,
                           (unsigned int)"onecore\\base\\cbs\\container\\servicingcontainerhelper.cpp",
                           v14);
  }
  return result;
}

```

## disassembly

```asm
0x18027a59c  mov     r11, rsp
0x18027a59f  push    rbx
0x18027a5a0  push    rsi
0x18027a5a1  push    rdi
0x18027a5a2  push    r12
0x18027a5a4  push    r13
0x18027a5a6  push    r14
0x18027a5a8  push    r15
0x18027a5aa  sub     rsp, 0A10h
0x18027a5b1  mov     qword ptr [r11-940h], 0FFFFFFFFFFFFFFFEh
0x18027a5bc  movaps  xmmword ptr [r11-48h], xmm6
0x18027a5c1  mov     rax, cs:__security_cookie
0x18027a5c8  xor     rax, rsp
0x18027a5cb  mov     [rsp+0A48h+var_58], rax
0x18027a5d3  mov     r13, r9
0x18027a5d6  mov     rsi, r8
0x18027a5d9  mov     [rsp+0A48h+var_9E0], r8
0x18027a5de  mov     r14, rdx
0x18027a5e1  mov     qword ptr [rsp+0A48h+var_9B8.Data1], rdx
0x18027a5e9  mov     rbx, rcx
0x18027a5ec  mov     [r11-938h], rcx
0x18027a5f3  mov     [r11-930h], r8
0x18027a5fa  mov     r12, [rsp+0A48h+arg_20]
0x18027a602  mov     rdi, [rsp+0A48h+arg_28]
0x18027a60a  mov     rax, [rsp+0A48h+arg_30]
0x18027a612  mov     qword ptr [rsp+0A48h+var_988.Data1], rax
0x18027a61a  mov     rax, [rsp+0A48h+arg_38]
0x18027a622  mov     [rsp+0A48h+var_978], rax
0x18027a62a  mov     rax, [rsp+0A48h+arg_40]
0x18027a632  mov     [rsp+0A48h+var_9C8], rax
0x18027a63a  xor     r15d, r15d
0x18027a63d  cmp     cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA, r15; LogAdapter::Logger * LogAdapter::g_Logger
0x18027a644  jnz     short loc_18027A66B
0x18027a646  call    ?IsWdsLoggerSetup@@YA_NPEAPEAUHINSTANCE__@@@Z; IsWdsLoggerSetup(HINSTANCE__ * *)
0x18027a64b  test    al, al
0x18027a64d  jz      short loc_18027A66B
0x18027a64f  lea     rax, ?wdsLogger@@3VWdsLogger@LogAdapter@@A; LogAdapter::WdsLogger wdsLogger
0x18027a656  mov     cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA, rax; LogAdapter::Logger * LogAdapter::g_Logger
0x18027a65d  lea     rax, ?CbsCustomLogging@@YAXIPEBD@Z; CbsCustomLogging(uint,char const *)
0x18027a664  mov     cs:?vpfnCustomLogging@@3P6AXIPEBD@ZEA, rax; void (*vpfnCustomLogging)(uint,char const *)
0x18027a66b  mov     rcx, rbx; lpFileName
0x18027a66e  call    cs:__imp_GetFileAttributesW
0x18027a675  nop     dword ptr [rax+rax+00h]
0x18027a67a  test    al, 10h
0x18027a67c  jnz     loc_18027A708
0x18027a682  mov     ebx, 80070057h
0x18027a687  mov     [rsp+0A48h+var_928], ebx
0x18027a68e  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x18027a695  test    rcx, rcx
0x18027a698  jz      short loc_18027A6E5
0x18027a69a  lea     r9, aInvalidHostroo; "Invalid hostRootPath encountered"
0x18027a6a1  mov     edi, 3
0x18027a6a6  mov     r8d, edi
0x18027a6a9  xor     edx, edx
0x18027a6ab  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x18027a6b0  lea     rax, [rsp+0A48h+var_928]
0x18027a6b8  mov     [rsp+0A48h+lpMem], rax
0x18027a6c0  lea     rax, [rsp+0A48h+lpMem]
0x18027a6c8  mov     qword ptr [rsp+0A48h+var_A28], rax; int
0x18027a6cd  lea     r9, asc_1802C6678; ": {}"
0x18027a6d4  mov     r8d, edi
0x18027a6d7  mov     dl, 1
0x18027a6d9  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x18027a6e0  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x18027a6e5  mov     rcx, [rsp+0A48h]; this
0x18027a6ed  mov     r9d, ebx; char *
0x18027a6f0  lea     r8, aOnecoreBaseCbs_9; "onecore\\base\\cbs\\container\\servicin"...
0x18027a6f7  mov     edx, 8B5h; void *
0x18027a6fc  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18027a701  mov     eax, ebx
0x18027a703  jmp     loc_18027B939
0x18027a708  test    r14, r14
0x18027a70b  jz      short loc_18027A71B
0x18027a70d  test    rsi, rsi
0x18027a710  jz      short loc_18027A71B
0x18027a712  mov     rax, [r13+8]
0x18027a716  jmp     loc_18027A7B0
0x18027a71b  mov     rax, [r13+8]
0x18027a71f  cmp     [r12+8], rax
0x18027a724  jz      loc_18027A7B0
0x18027a72a  mov     ebx, 80070057h
0x18027a72f  mov     [rsp+0A48h+var_928], ebx
0x18027a736  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x18027a73d  test    rcx, rcx
0x18027a740  jz      short loc_18027A78D
0x18027a742  lea     r9, aMissingTopLeve; "Missing top level package or configDirs"...
0x18027a749  mov     edi, 3
0x18027a74e  mov     r8d, edi
0x18027a751  xor     edx, edx
0x18027a753  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x18027a758  lea     rax, [rsp+0A48h+var_928]
0x18027a760  mov     [rsp+0A48h+lpMem], rax
0x18027a768  lea     rax, [rsp+0A48h+lpMem]
0x18027a770  mov     qword ptr [rsp+0A48h+var_A28], rax; int
0x18027a775  lea     r9, asc_1802C6678; ": {}"
0x18027a77c  mov     r8d, edi
0x18027a77f  mov     dl, 1
0x18027a781  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x18027a788  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x18027a78d  mov     rcx, [rsp+0A48h]; this
0x18027a795  mov     r9d, ebx; char *
0x18027a798  lea     r8, aOnecoreBaseCbs_9; "onecore\\base\\cbs\\container\\servicin"...
0x18027a79f  mov     edx, 8B7h; void *
0x18027a7a4  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18027a7a9  mov     eax, ebx
0x18027a7ab  jmp     loc_18027B939
0x18027a7b0  test    rax, rax
0x18027a7b3  jz      loc_18027B939
0x18027a7b9  cmp     rax, 1
0x18027a7bd  jz      loc_18027A849
0x18027a7c3  mov     ebx, 8000FFFFh
0x18027a7c8  mov     [rsp+0A48h+var_928], ebx
0x18027a7cf  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x18027a7d6  test    rcx, rcx
0x18027a7d9  jz      short loc_18027A826
0x18027a7db  lea     r9, aOnlyOneLayerIs; "Only one layer is supported"
0x18027a7e2  mov     edi, 3
0x18027a7e7  mov     r8d, edi
0x18027a7ea  xor     edx, edx
0x18027a7ec  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x18027a7f1  lea     rax, [rsp+0A48h+var_928]
0x18027a7f9  mov     [rsp+0A48h+lpMem], rax
0x18027a801  lea     rax, [rsp+0A48h+lpMem]
0x18027a809  mov     qword ptr [rsp+0A48h+var_A28], rax; int
0x18027a80e  lea     r9, asc_1802C6678; ": {}"
0x18027a815  mov     r8d, edi
0x18027a818  mov     dl, 1
0x18027a81a  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x18027a821  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x18027a826  mov     rcx, [rsp+0A48h]; this
0x18027a82e  mov     r9d, ebx; char *
0x18027a831  lea     r8, aOnecoreBaseCbs_9; "onecore\\base\\cbs\\container\\servicin"...
0x18027a838  mov     edx, 8C8h; void *
0x18027a83d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18027a842  mov     eax, ebx
0x18027a844  jmp     loc_18027B939
0x18027a849  mov     rax, [r13+0]
0x18027a84d  movups  xmm0, xmmword ptr [rax]
0x18027a850  movdqu  [rsp+0A48h+Buf1], xmm0
0x18027a859  mov     r8d, 10h; Size
0x18027a85f  lea     rdx, CMS_CLIENT_PROFESSIONAL_LAYER_ID; Buf2
0x18027a866  lea     rcx, [rsp+0A48h+Buf1]; Buf1
0x18027a86e  call    memcmp_0
0x18027a873  test    eax, eax
0x18027a875  jz      loc_18027A901
0x18027a87b  mov     ebx, 8000FFFFh
0x18027a880  mov     [rsp+0A48h+var_928], ebx
0x18027a887  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x18027a88e  test    rcx, rcx
0x18027a891  jz      short loc_18027A8DE
0x18027a893  lea     r9, aOnlyProfession; "Only professional is supported"
0x18027a89a  mov     edi, 3
0x18027a89f  mov     r8d, edi
0x18027a8a2  xor     edx, edx
0x18027a8a4  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x18027a8a9  lea     rax, [rsp+0A48h+var_928]
0x18027a8b1  mov     [rsp+0A48h+lpMem], rax
0x18027a8b9  lea     rax, [rsp+0A48h+lpMem]
0x18027a8c1  mov     qword ptr [rsp+0A48h+var_A28], rax; int
0x18027a8c6  lea     r9, asc_1802C6678; ": {}"
0x18027a8cd  mov     r8d, edi
0x18027a8d0  mov     dl, 1
0x18027a8d2  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x18027a8d9  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x18027a8de  mov     rcx, [rsp+0A48h]; this
0x18027a8e6  mov     r9d, ebx; char *
0x18027a8e9  lea     r8, aOnecoreBaseCbs_9; "onecore\\base\\cbs\\container\\servicin"...
0x18027a8f0  mov     edx, 8CCh; void *
0x18027a8f5  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18027a8fa  mov     eax, ebx
0x18027a8fc  jmp     loc_18027B939
0x18027a901  xorps   xmm0, xmm0
0x18027a904  xor     eax, eax
0x18027a906  movups  [rsp+0A48h+var_9F8], xmm0
0x18027a90b  mov     [rsp+0A48h+var_9E8], rax
0x18027a910  lea     r8, [rsp+0A48h+var_9F8]
0x18027a915  lea     rcx, [rsp+0A48h+lpMem]
0x18027a91d  call    ??$CombineAndNullTerminateWin32Paths@PEB_W$$BY07_W@Rtl@StringUtil@Windows@@YAJAEBQEB_WAEAY07$$CB_WPEAV?$Auto@U_LUNICODE_STRING@@@2@@Z; Windows::StringUtil::Rtl::CombineAndNullTerminateWin32Paths<wchar_t const *,wchar_t [8]>(wchar_t const * const &,wchar_t const (&)[8],Windows::Auto<_LUNICODE_STRING> *)
0x18027a922  mov     ebx, eax
0x18027a924  test    eax, eax
0x18027a926  jns     loc_18027A9BD
0x18027a92c  mov     [rsp+0A48h+var_928], eax
0x18027a933  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x18027a93a  test    rcx, rcx
0x18027a93d  jz      short loc_18027A988
0x18027a93f  lea     r9, aFailedToCreate_31; "Failed to create path for host windows "...
0x18027a946  mov     edi, 3
0x18027a94b  mov     r8d, edi
0x18027a94e  xor     edx, edx
0x18027a950  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x18027a955  lea     rax, [rsp+0A48h+var_928]
0x18027a95d  mov     [rsp+0A48h+lpMem], rax
0x18027a965  lea     rax, [rsp+0A48h+lpMem]
0x18027a96d  mov     qword ptr [rsp+0A48h+var_A28], rax; int
0x18027a972  lea     r9, asc_1802C6678; ": {}"
0x18027a979  mov     r8d, edi
0x18027a97c  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x18027a983  call    ??$LogNumObjects@U?$FormatNtStatusWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatNtStatusWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatNtStatusWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatNtStatusWrapper<long> const &)
0x18027a988  mov     rcx, [rsp+0A48h]; this
0x18027a990  mov     r9d, ebx; char *
0x18027a993  lea     r8, aOnecoreBaseCbs_9; "onecore\\base\\cbs\\container\\servicin"...
0x18027a99a  mov     edx, 8D0h; void *
0x18027a99f  call    ?Return_NtStatus@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Return_NtStatus(void *,uint,char const *,long)
0x18027a9a4  mov     ebx, eax
0x18027a9a6  mov     rcx, [rsp+0A48h+var_9E8]
0x18027a9ab  test    rcx, rcx
0x18027a9ae  jz      short loc_18027A9B6
0x18027a9b0  call    _anonymous_namespace___OurRtlFreeStringRoutine
0x18027a9b5  nop
0x18027a9b6  mov     eax, ebx
0x18027a9b8  jmp     loc_18027B939
0x18027a9bd  mov     [rsp+0A48h+P], r15
0x18027a9c5  test    rdi, rdi
0x18027a9c8  jz      loc_18027AB89
0x18027a9ce  or      r15, 0FFFFFFFFFFFFFFFFh
0x18027a9d2  mov     rax, r15
0x18027a9d5  xor     r14d, r14d
0x18027a9d8  inc     rax
0x18027a9db  cmp     [rdi+rax*2], r14w
0x18027a9e0  jnz     short loc_18027A9D8
0x18027a9e2  lea     rsi, [rax+1]
0x18027a9e6  lea     rbx, [rsi+rsi]
0x18027a9ea  call    cs:__imp_GetProcessHeap
0x18027a9f1  nop     dword ptr [rax+rax+00h]
0x18027a9f6  mov     rcx, rax; hHeap
0x18027a9f9  mov     r8, rbx; dwBytes
0x18027a9fc  xor     edx, edx; dwFlags
0x18027a9fe  call    cs:__imp_HeapAlloc
0x18027aa05  nop     dword ptr [rax+rax+00h]
0x18027aa0a  cmp     [rsp+0A48h+P], r14
0x18027aa12  jnz     loc_18027B965
0x18027aa18  mov     [rsp+0A48h+P], rax
0x18027aa20  test    rax, rax
0x18027aa23  jnz     short loc_18027AA97
0x18027aa25  mov     rcx, [rsp+0A48h]; this
0x18027aa2d  mov     ebx, 8007000Eh
0x18027aa32  mov     r9d, ebx; char *
0x18027aa35  lea     r8, aOnecoreBaseCbs_9; "onecore\\base\\cbs\\container\\servicin"...
0x18027aa3c  mov     edx, 8D7h; void *
0x18027aa41  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18027aa46  nop
0x18027aa47  mov     r8, [rsp+0A48h+P]; P
0x18027aa4f  test    r8, r8
0x18027aa52  jz      short loc_18027AA80
0x18027aa54  mov     rcx, gs:60h
0x18027aa5d  xor     edx, edx; Flags
0x18027aa5f  mov     rcx, [rcx+30h]; HeapHandle
0x18027aa63  call    cs:__imp_RtlFreeHeap
0x18027aa6a  nop     dword ptr [rax+rax+00h]
0x18027aa6f  test    eax, eax
0x18027aa71  jnz     short loc_18027AA78
0x18027aa73  lea     ecx, [rax+7]
0x18027aa76  int     29h; Win8: RtlFailFast(ecx)
0x18027aa78  mov     [rsp+0A48h+P], r14
0x18027aa80  mov     rcx, [rsp+0A48h+var_9E8]
0x18027aa85  test    rcx, rcx
0x18027aa88  jz      short loc_18027AA90
0x18027aa8a  call    _anonymous_namespace___OurRtlFreeStringRoutine
0x18027aa8f  nop
0x18027aa90  mov     eax, ebx
0x18027aa92  jmp     loc_18027B939
0x18027aa97  mov     r8, rdi; wchar_t *
0x18027aa9a  mov     rdx, rsi; unsigned __int64
0x18027aa9d  mov     rcx, rax; wchar_t *
0x18027aaa0  call    ?StringCchCopyW@@YAJPEA_W_KPEB_W@Z; StringCchCopyW(wchar_t *,unsigned __int64,wchar_t const *)
0x18027aaa5  mov     ebx, eax
0x18027aaa7  test    eax, eax
0x18027aaa9  jns     loc_18027AB7A
0x18027aaaf  mov     [rsp+0A48h+var_928], eax
0x18027aab6  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x18027aabd  test    rcx, rcx
0x18027aac0  jz      short loc_18027AB0D
0x18027aac2  lea     r9, aFailedToCopySs; "Failed to copy ssu path."
0x18027aac9  mov     edi, 3
0x18027aace  mov     r8d, edi
0x18027aad1  xor     edx, edx
0x18027aad3  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x18027aad8  lea     rax, [rsp+0A48h+var_928]
0x18027aae0  mov     [rsp+0A48h+lpMem], rax
0x18027aae8  lea     rax, [rsp+0A48h+lpMem]
0x18027aaf0  mov     qword ptr [rsp+0A48h+var_A28], rax; int
0x18027aaf5  lea     r9, asc_1802C6678; ": {}"
0x18027aafc  mov     r8d, edi
0x18027aaff  mov     dl, 1
0x18027ab01  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x18027ab08  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x18027ab0d  mov     rcx, [rsp+0A48h]; this
0x18027ab15  mov     r9d, ebx; char *
0x18027ab18  lea     r8, aOnecoreBaseCbs_9; "onecore\\base\\cbs\\container\\servicin"...
0x18027ab1f  mov     edx, 8D9h; void *
0x18027ab24  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18027ab29  nop
0x18027ab2a  mov     r8, [rsp+0A48h+P]; P
0x18027ab32  test    r8, r8
0x18027ab35  jz      short loc_18027AB63
0x18027ab37  mov     rcx, gs:60h
0x18027ab40  xor     edx, edx; Flags
0x18027ab42  mov     rcx, [rcx+30h]; HeapHandle
0x18027ab46  call    cs:__imp_RtlFreeHeap
0x18027ab4d  nop     dword ptr [rax+rax+00h]
  ... truncated ...
```
