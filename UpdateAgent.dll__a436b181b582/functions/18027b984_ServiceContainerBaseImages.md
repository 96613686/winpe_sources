# ServiceContainerBaseImages

- ea: `0x18027b984`
- end: `0x18027d99a`
- name: `ServiceContainerBaseImages`
- size: `8214`
- prototype: `__int64 __usercall@<rax>(LPCWSTR lpFileName@<rcx>, __int64, wchar_t *, __int64, __int64)`
- caller_count: `1`
- callee_count: `39`
- tags: `file_ops, reparse_path, registry_config, loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x180071520`

## callees

- `0x1800059d0`
- `0x1800059f4`
- `0x18000a0e8`
- `0x18000b508`
- `0x18000c4c4`
- `0x18001ef84`
- `0x180022a08`
- `0x1800692fc`
- `0x18008b38c`
- `0x18008b3bc`
- `0x18009338c`
- `0x1800bd064`
- `0x1800c9954`
- `0x1800ce5fc`
- `0x1800ce6b0`
- `0x18011b0fc`
- `0x1801417cc`
- `0x18014c9a0`
- `0x180190844`
- `0x1801ee64c`
- `0x1801f01e4`
- `0x1801f250c`
- `0x18026fbc8`
- `0x180270900`
- `0x180270d34`
- `0x180270de0`
- `0x180270f8c`
- `0x1802744c4`
- `0x180275608`
- `0x180275838`
- `0x180276114`
- `0x18027694c`
- `0x180276990`
- `0x180277158`
- `0x180278b0c`
- `0x180278f00`
- `0x18027b984`
- `0x18027d9a0`
- `0x1802b1010`

## import_xrefs

- `ntdll!RtlFreeHeap` at `0x18027bc88`
- `ntdll!RtlFreeHeap` at `0x18027bd75`
- `ntdll!RtlFreeHeap` at `0x18027beb4`
- `ntdll!RtlFreeHeap` at `0x18027c0a6`
- `ntdll!RtlFreeHeap` at `0x18027c218`
- `ntdll!RtlFreeHeap` at `0x18027c330`
- `ntdll!RtlFreeHeap` at `0x18027c448`
- `ntdll!RtlFreeHeap` at `0x18027c560`
- `ntdll!RtlFreeHeap` at `0x18027c678`
- `ntdll!RtlFreeHeap` at `0x18027c790`
- `ntdll!RtlFreeHeap` at `0x18027ca07`
- `ntdll!RtlFreeHeap` at `0x18027cb6d`
- `ntdll!RtlFreeHeap` at `0x18027bc88`
- `ntdll!RtlFreeHeap` at `0x18027bd75`
- `ntdll!RtlFreeHeap` at `0x18027beb4`
- `ntdll!RtlFreeHeap` at `0x18027c0a6`
- `ntdll!RtlFreeHeap` at `0x18027c218`
- `ntdll!RtlFreeHeap` at `0x18027c330`
- `ntdll!RtlFreeHeap` at `0x18027c448`
- `ntdll!RtlFreeHeap` at `0x18027c560`
- `ntdll!RtlFreeHeap` at `0x18027c678`
- `ntdll!RtlFreeHeap` at `0x18027c790`
- `ntdll!RtlFreeHeap` at `0x18027ca07`
- `ntdll!RtlFreeHeap` at `0x18027cb6d`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x18027ba54`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x18027ba54`
- `api-ms-win-core-libraryloader-l1-1-0!FreeLibrary` at `0x18027c1e1`
- `api-ms-win-core-libraryloader-l1-1-0!FreeLibrary` at `0x18027c2f9`
- `api-ms-win-core-libraryloader-l1-1-0!FreeLibrary` at `0x18027c411`
- `api-ms-win-core-libraryloader-l1-1-0!FreeLibrary` at `0x18027c529`
- `api-ms-win-core-libraryloader-l1-1-0!FreeLibrary` at `0x18027c641`
- `api-ms-win-core-libraryloader-l1-1-0!FreeLibrary` at `0x18027c759`
- `api-ms-win-core-libraryloader-l1-1-0!FreeLibrary` at `0x18027c9d0`
- `api-ms-win-core-libraryloader-l1-1-0!FreeLibrary` at `0x18027cb36`
- `api-ms-win-core-libraryloader-l1-1-0!FreeLibrary` at `0x18027cc63`
- `api-ms-win-core-libraryloader-l1-1-0!FreeLibrary` at `0x18027cd2b`
- `api-ms-win-core-libraryloader-l1-1-0!FreeLibrary` at `0x18027cdf2`
- `api-ms-win-core-libraryloader-l1-1-0!FreeLibrary` at `0x18027cf0c`
- `api-ms-win-core-libraryloader-l1-1-0!FreeLibrary` at `0x18027cf3f`
- `api-ms-win-core-libraryloader-l1-1-0!FreeLibrary` at `0x18027d01c`
- `api-ms-win-core-libraryloader-l1-1-0!FreeLibrary` at `0x18027d04f`
- `api-ms-win-core-libraryloader-l1-1-0!FreeLibrary` at `0x18027d1b9`
- `api-ms-win-core-libraryloader-l1-1-0!FreeLibrary` at `0x18027d1ec`
- `api-ms-win-core-libraryloader-l1-1-0!FreeLibrary` at `0x18027d2ed`
- `api-ms-win-core-libraryloader-l1-1-0!FreeLibrary` at `0x18027d320`
- `api-ms-win-core-libraryloader-l1-1-0!FreeLibrary` at `0x18027d474`
- `api-ms-win-core-libraryloader-l1-1-0!FreeLibrary` at `0x18027d4a7`
- `api-ms-win-core-libraryloader-l1-1-0!FreeLibrary` at `0x18027d700`
- `api-ms-win-core-libraryloader-l1-1-0!FreeLibrary` at `0x18027d733`
- `api-ms-win-core-libraryloader-l1-1-0!FreeLibrary` at `0x18027d860`
- `api-ms-win-core-libraryloader-l1-1-0!FreeLibrary` at `0x18027d893`
- `api-ms-win-core-libraryloader-l1-1-0!FreeLibrary` at `0x18027c1e1`
- `api-ms-win-core-libraryloader-l1-1-0!FreeLibrary` at `0x18027c2f9`
- `api-ms-win-core-libraryloader-l1-1-0!FreeLibrary` at `0x18027c411`
- `api-ms-win-core-libraryloader-l1-1-0!FreeLibrary` at `0x18027c529`
- `api-ms-win-core-libraryloader-l1-1-0!FreeLibrary` at `0x18027c641`
- `api-ms-win-core-libraryloader-l1-1-0!FreeLibrary` at `0x18027c759`
- `api-ms-win-core-libraryloader-l1-1-0!FreeLibrary` at `0x18027c9d0`
- `api-ms-win-core-libraryloader-l1-1-0!FreeLibrary` at `0x18027cb36`
- `api-ms-win-core-libraryloader-l1-1-0!FreeLibrary` at `0x18027cc63`
- `api-ms-win-core-libraryloader-l1-1-0!FreeLibrary` at `0x18027cd2b`
- `api-ms-win-core-libraryloader-l1-1-0!FreeLibrary` at `0x18027cdf2`
- `api-ms-win-core-libraryloader-l1-1-0!FreeLibrary` at `0x18027cf0c`
- `api-ms-win-core-libraryloader-l1-1-0!FreeLibrary` at `0x18027cf3f`
- `api-ms-win-core-libraryloader-l1-1-0!FreeLibrary` at `0x18027d01c`
- `api-ms-win-core-libraryloader-l1-1-0!FreeLibrary` at `0x18027d04f`
- `api-ms-win-core-libraryloader-l1-1-0!FreeLibrary` at `0x18027d1b9`
- `api-ms-win-core-libraryloader-l1-1-0!FreeLibrary` at `0x18027d1ec`
- `api-ms-win-core-libraryloader-l1-1-0!FreeLibrary` at `0x18027d2ed`
- `api-ms-win-core-libraryloader-l1-1-0!FreeLibrary` at `0x18027d320`
- `api-ms-win-core-libraryloader-l1-1-0!FreeLibrary` at `0x18027d474`
- `api-ms-win-core-libraryloader-l1-1-0!FreeLibrary` at `0x18027d4a7`
- `api-ms-win-core-libraryloader-l1-1-0!FreeLibrary` at `0x18027d700`
- `api-ms-win-core-libraryloader-l1-1-0!FreeLibrary` at `0x18027d733`
- `api-ms-win-core-libraryloader-l1-1-0!FreeLibrary` at `0x18027d860`
- `api-ms-win-core-libraryloader-l1-1-0!FreeLibrary` at `0x18027d893`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18027bc0f`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18027d541`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18027d667`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18027d783`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18027bc0f`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18027d541`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18027d667`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18027d783`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18027d555`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18027d67b`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18027d797`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18027d555`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18027d67b`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18027d797`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18027bc23`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18027bc23`
- `api-ms-win-core-com-l1-1-0!CoCreateGuid` at `0x18027ca4c`
- `api-ms-win-core-com-l1-1-0!CoCreateGuid` at `0x18027ca4c`

## string_xrefs

- `0x18027c7ea`: `ServiceContainerBaseImages`
- `0x18027ce9b`: `Unable to load turbostack.dll`
- `0x18027c4b0`: `Failed to get address of function CmsOfflineCreateServicingTransaction.`
- `0x18027c482`: `CmsOfflineCreateServicingTransaction`
- `0x18027c5c8`: `Failed to get address of function CmsOfflineDeleteServicingTransaction.`
- `0x18027c59a`: `CmsOfflineDeleteServicingTransaction`
- `0x18027ca75`: `Failed to create transaction guid.`
- `0x18027cbd9`: `Failed to create servicing transaction.`
- `0x18027d129`: `Failed to create path for host Packages.`
- `0x18027bcea`: `Failed to copy ssu path.`
- `0x18027c00f`: `Failed to create path for cmservicing.`
- `0x18027be29`: `Failed to get SSU Path`
- `0x18027d387`: `Professional.xml`
- `0x18027d8e9`: `Invalid hostRootPath encountered`
- `0x18027baa1`: `Missing top level package or configDirs for layerIds`
- `0x18027bb63`: `Failed to create path for host windows dir.`

## pseudocode

```c
// Hidden C++ exception states: #wind=87
__int64 __fastcall ServiceContainerBaseImages(
        wchar_t *lpFileName,
        void *a2,
        wchar_t *a3,
        __int64 a4,
        wchar_t **a5,
        wchar_t *a6,
        struct _GUID *a7,
        __int64 a8)
{
  wchar_t *v9; // r14
  char FileAttributesW; // al
  __int64 v13; // rdx
  const char *v14; // r9
  __int64 result; // rax
  int v16; // eax
  unsigned int v17; // ebx
  __int64 v18; // rdx
  unsigned int v19; // ebx
  __int64 v20; // rax
  unsigned __int64 v21; // r14
  SIZE_T v22; // rbx
  HANDLE ProcessHeap; // rax
  void *v24; // rax
  int v25; // eax
  int v26; // eax
  unsigned int v27; // ebx
  int v28; // eax
  wchar_t *v29; // rbx
  int SsuPath; // eax
  unsigned int v31; // edi
  int v32; // eax
  PVOID v33; // rax
  __int64 v34; // rcx
  __int64 v35; // rcx
  __int64 v36; // rdx
  const wchar_t *v37; // rcx
  __int64 v38; // rax
  __int64 v39; // rax
  __int64 v40; // rdx
  __int64 v41; // rcx
  int v42; // edi
  __int128 v43; // kr10_16
  __int64 v44; // rdx
  unsigned int v45; // edi
  int v46; // eax
  wchar_t *v47; // r15
  int v48; // eax
  unsigned int v49; // edi
  int v50; // eax
  int FunctionPointer; // eax
  unsigned int v52; // edi
  int v53; // eax
  int v54; // eax
  unsigned int v55; // edi
  int v56; // eax
  int v57; // eax
  unsigned int v58; // edi
  int v59; // eax
  int v60; // eax
  unsigned int v61; // edi
  int v62; // eax
  int v63; // eax
  unsigned int v64; // edi
  int v65; // eax
  int v66; // eax
  __int64 v67; // rdx
  int v68; // eax
  unsigned int v69; // edi
  BOOL v70; // esi
  __int64 v71; // rdx
  const struct std::nothrow_t *v72; // rdx
  int v73; // eax
  HRESULT v74; // eax
  unsigned int v75; // edi
  __int64 v76; // rdx
  const struct std::nothrow_t *v77; // rdx
  int v78; // eax
  int v79; // eax
  unsigned int v80; // edi
  __int64 v81; // rdx
  int v82; // eax
  unsigned int v83; // edi
  int v84; // eax
  unsigned int v85; // edi
  int Turbostack; // eax
  unsigned int v87; // edi
  __int64 v88; // rdx
  __int64 v89; // rdx
  __int64 v90; // r8
  struct _GUID **v91; // r14
  int ConfigFilePaths; // eax
  unsigned int v93; // edi
  __int64 (*v94)(void); // rdi
  __int64 v95; // rax
  int v96; // eax
  unsigned int v97; // ebx
  __int64 v98; // rdx
  unsigned int v99; // ebx
  int DirectSystem; // eax
  unsigned int v101; // ebx
  __int64 v102; // rax
  const wchar_t *v103; // r8
  wchar_t **v104; // rbx
  int v105; // eax
  unsigned int v106; // edi
  struct _GUID **v107; // rbx
  __int64 v108; // rax
  void *v109; // rbx
  HANDLE v110; // rax
  void *v111; // r14
  const wchar_t *v112; // rdi
  const wchar_t *v113; // rsi
  __int64 v114; // rax
  __int64 v115; // r8
  struct _GUID *v116; // rdx
  const wchar_t *v117; // r9
  int v118; // eax
  unsigned int v119; // edi
  HANDLE v120; // rax
  HANDLE v121; // rax
  wchar_t **p_lpMem; // [rsp+20h] [rbp-D18h]
  int v123; // [rsp+20h] [rbp-D18h]
  char v124[8]; // [rsp+60h] [rbp-CD8h] BYREF
  HMODULE hLibModule; // [rsp+68h] [rbp-CD0h]
  wchar_t **v126; // [rsp+70h] [rbp-CC8h] BYREF
  struct _GUID **v127; // [rsp+78h] [rbp-CC0h] BYREF
  __int64 (*v128)(void); // [rsp+80h] [rbp-CB8h] BYREF
  __int64 (*v129)(void); // [rsp+88h] [rbp-CB0h] BYREF
  LPVOID lpMem; // [rsp+90h] [rbp-CA8h] BYREF
  __int128 v131; // [rsp+98h] [rbp-CA0h] BYREF
  wchar_t *v132; // [rsp+A8h] [rbp-C90h]
  wchar_t *v133; // [rsp+B0h] [rbp-C88h] BYREF
  int v134[2]; // [rsp+B8h] [rbp-C80h] BYREF
  __int128 v135; // [rsp+C0h] [rbp-C78h] BYREF
  wchar_t *v136; // [rsp+D0h] [rbp-C68h]
  wchar_t *v137; // [rsp+D8h] [rbp-C60h] BYREF
  __int128 v138; // [rsp+E0h] [rbp-C58h] BYREF
  __int64 v139; // [rsp+F0h] [rbp-C48h]
  char v140; // [rsp+F8h] [rbp-C40h]
  _QWORD v141[6]; // [rsp+100h] [rbp-C38h] BYREF
  int v142[4]; // [rsp+130h] [rbp-C08h] BYREF
  __int64 v143; // [rsp+140h] [rbp-BF8h]
  __int128 v144; // [rsp+148h] [rbp-BF0h] BYREF
  PVOID v145; // [rsp+158h] [rbp-BE0h]
  __int64 v146; // [rsp+160h] [rbp-BD8h]
  __int64 v147; // [rsp+168h] [rbp-BD0h]
  const wchar_t *v148; // [rsp+170h] [rbp-BC8h]
  struct _GUID *v149; // [rsp+178h] [rbp-BC0h]
  wchar_t *v150; // [rsp+180h] [rbp-BB8h]
  __int64 i; // [rsp+188h] [rbp-BB0h]
  __int64 v152; // [rsp+190h] [rbp-BA8h]
  struct _GUID v153; // [rsp+1A0h] [rbp-B98h] BYREF
  struct _GUID v154; // [rsp+1B0h] [rbp-B88h] BYREF
  struct _GUID v155; // [rsp+1C0h] [rbp-B78h] BYREF
  char v156[16]; // [rsp+1D0h] [rbp-B68h] BYREF
  wchar_t *v157; // [rsp+1E0h] [rbp-B58h] BYREF
  wchar_t *v158; // [rsp+1E8h] [rbp-B50h] BYREF
  void *v159; // [rsp+1F0h] [rbp-B48h] BYREF
  __int64 (*v160)(void); // [rsp+1F8h] [rbp-B40h] BYREF
  __int64 (*v161)(void); // [rsp+200h] [rbp-B38h] BYREF
  __int64 (*v162)(void); // [rsp+208h] [rbp-B30h] BYREF
  int v163; // [rsp+210h] [rbp-B28h] BYREF
  PVOID P; // [rsp+218h] [rbp-B20h] BYREF
  char v165; // [rsp+220h] [rbp-B18h] BYREF
  char v166[8]; // [rsp+228h] [rbp-B10h] BYREF
  HMODULE v167; // [rsp+230h] [rbp-B08h]
  GUID pguid; // [rsp+238h] [rbp-B00h] BYREF
  int v169[10]; // [rsp+250h] [rbp-AE8h] BYREF
  wchar_t *v170; // [rsp+278h] [rbp-AC0h]
  _BYTE v171[64]; // [rsp+290h] [rbp-AA8h] BYREF
  void *v172[259]; // [rsp+2D0h] [rbp-A68h] BYREF
  __int64 v173; // [rsp+AE8h] [rbp-250h]
  wchar_t v174[256]; // [rsp+AF0h] [rbp-248h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+D38h] [rbp+0h]

  v152 = -2;
  v127 = (struct _GUID **)a4;
  v9 = a3;
  v133 = a3;
  lpMem = a2;
  v150 = lpFileName;
  v157 = lpFileName;
  v158 = a3;
  v126 = a5;
  v149 = a7;
  *(_QWORD *)v134 = a8;
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
      v163 = -2147024809;
      if ( *(_QWORD *)&LogAdapter::g_Logger )
      {
        LogAdapter::Logger::LogNumObjects<>(*(_QWORD *)&LogAdapter::g_Logger, 0, 3, "Invalid hostRootPath encountered");
        *(_QWORD *)v134 = &v163;
        p_lpMem = (wchar_t **)v134;
        LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
          *(_QWORD *)&LogAdapter::g_Logger,
          1,
          3,
          ": {}");
      }
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x59A,
        (unsigned int)"onecore\\base\\cbs\\container\\servicingcontainerhelper.cpp",
        (const char *)0x80070057LL,
        (int)p_lpMem);
      return 2147942487LL;
    }
    if ( a2 && v9 )
    {
      result = *(_QWORD *)(a4 + 8);
    }
    else
    {
      result = *(_QWORD *)(a4 + 8);
      if ( a5[1] != (wchar_t *)result )
      {
        v163 = -2147024809;
        if ( *(_QWORD *)&LogAdapter::g_Logger )
        {
          LogAdapter::Logger::LogNumObjects<>(
            *(_QWORD *)&LogAdapter::g_Logger,
            0,
            3,
            "Missing top level package or configDirs for layerIds");
          v157 = (wchar_t *)&v163;
          p_lpMem = &v157;
          LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
            *(_QWORD *)&LogAdapter::g_Logger,
            1,
            3,
            ": {}");
        }
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x59C,
          (unsigned int)"onecore\\base\\cbs\\container\\servicingcontainerhelper.cpp",
          (const char *)0x80070057LL,
          (int)p_lpMem);
        return 2147942487LL;
      }
    }
    if ( !result )
      return result;
    v131 = 0;
    v132 = 0;
    v16 = Windows::StringUtil::Rtl::CombineAndNullTerminateWin32Paths<wchar_t const *,wchar_t [8]>(&v157, v13, &v131);
    v17 = v16;
    if ( v16 < 0 )
    {
      v163 = v16;
      if ( *(_QWORD *)&LogAdapter::g_Logger )
      {
        LogAdapter::Logger::LogNumObjects<>(
          *(_QWORD *)&LogAdapter::g_Logger,
          0,
          3,
          "Failed to create path for host windows dir.");
        v157 = (wchar_t *)&v163;
        p_lpMem = &v157;
        LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatNtStatusWrapper<long>>(
          *(_QWORD *)&LogAdapter::g_Logger,
          v18,
          3,
          ": {}");
      }
      v19 = wil::details::in1diag3::Return_NtStatus(
              retaddr,
              (void *)0x5A6,
              (unsigned int)"onecore\\base\\cbs\\container\\servicingcontainerhelper.cpp",
              (const char *)v17,
              (int)p_lpMem);
      if ( v132 )
        anonymous_namespace_::OurRtlFreeStringRoutine(v132);
      return v19;
    }
    P = 0;
    if ( a6 )
    {
      v20 = -1;
      do
        ++v20;
      while ( a6[v20] );
      v21 = v20 + 1;
      v22 = 2 * (v20 + 1);
      ProcessHeap = GetProcessHeap();
      v24 = HeapAlloc(ProcessHeap, 0, v22);
      if ( !P )
      {
        P = v24;
        if ( !v24 )
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x5AD,
            (unsigned int)"onecore\\base\\cbs\\container\\servicingcontainerhelper.cpp",
            (const char *)0x8007000ELL,
            (int)p_lpMem);
          if ( P )
          {
            LOBYTE(v25) = RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, P);
            if ( !v25 )
              __fastfail(7u);
            P = 0;
          }
          if ( v132 )
            anonymous_namespace_::OurRtlFreeStringRoutine(v132);
          return 2147942414LL;
        }
        v26 = StringCchCopyW((wchar_t *)v24, v21, a6);
        v27 = v26;
        if ( v26 < 0 )
        {
          v163 = v26;
          if ( *(_QWORD *)&LogAdapter::g_Logger )
          {
            LogAdapter::Logger::LogNumObjects<>(*(_QWORD *)&LogAdapter::g_Logger, 0, 3, "Failed to copy ssu path.");
            v157 = (wchar_t *)&v163;
            p_lpMem = &v157;
            LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
              *(_QWORD *)&LogAdapter::g_Logger,
              1,
              3,
              ": {}");
          }
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x5AF,
            (unsigned int)"onecore\\base\\cbs\\container\\servicingcontainerhelper.cpp",
            (const char *)v27,
            (int)p_lpMem);
          if ( P )
          {
            LOBYTE(v28) = RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, P);
            if ( !v28 )
              __fastfail(7u);
            P = 0;
          }
          if ( v132 )
            anonymous_namespace_::OurRtlFreeStringRoutine(v132);
          return v27;
        }
        v29 = v132;
        v9 = v133;
        goto LABEL_56;
      }
    }
    else
    {
      v29 = v132;
      if ( !v132 || *((_QWORD *)&v131 + 1) - (_QWORD)v131 >= 2u && !v132[(unsigned __int64)v131 >> 1] )
      {
        SsuPath = GetSsuPath(v132);
        v31 = SsuPath;
        if ( SsuPath < 0 )
        {
          v163 = SsuPath;
          if ( *(_QWORD *)&LogAdapter::g_Logger )
          {
            LogAdapter::Logger::LogNumObjects<>(*(_QWORD *)&LogAdapter::g_Logger, 0, 3, "Failed to get SSU Path");
            v157 = (wchar_t *)&v163;
            p_lpMem = &v157;
            LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
              *(_QWORD *)&LogAdapter::g_Logger,
              1,
              3,
              ": {}");
          }
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x5B3,
            (unsigned int)"onecore\\base\\cbs\\container\\servicingcontainerhelper.cpp",
            (const char *)v31,
            (int)p_lpMem);
          if ( P )
          {
            LOBYTE(v32) = RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, P);
            if ( !v32 )
              __fastfail(7u);
            P = 0;
          }
          if ( v29 )
            anonymous_namespace_::OurRtlFreeStringRoutine(v29);
          return v31;
        }
LABEL_56:
        v135 = 0;
        v136 = 0;
        v33 = P;
        if ( P )
        {
          v34 = -1;
          do
            ++v34;
          while ( *((_WORD *)P + v34) );
          v35 = 2 * v34;
          v36 = v35 + 2;
        }
        else
        {
          v33 = 0;
          v35 = 0;
          v36 = 0;
        }
        *(_QWORD *)&v144 = v35;
        *((_QWORD *)&v144 + 1) = v36;
        v145 = v33;
        v37 = L"cmsofflineservicing.dll";
        if ( L"cmsofflineservicing.dll" )
        {
          v38 = -1;
          do
            ++v38;
          while ( aCmsofflineserv[v38] );
          v39 = 2 * v38;
          v40 = v39 + 2;
        }
        else
        {
          v37 = 0;
          v39 = 0;
          v40 = 0;
        }
        v146 = v39;
        v147 = v40;
        v148 = v37;
        v42 = RtlCombineNtPathSegments(2, &v144, &v135);
        if ( v42 >= 0 )
        {
          v43 = v135;
          if ( *((_QWORD *)&v135 + 1) - (_QWORD)v135 >= 2u )
          {
LABEL_83:
            v47 = v136;
            *(wchar_t *)((char *)v136 + (v43 & 0xFFFFFFFFFFFFFFFEuLL)) = 0;
            v124[0] = 0;
            hLibModule = 0;
            v129 = 0;
            v162 = 0;
            v128 = 0;
            v160 = 0;
            v161 = 0;
            if ( !v47 || *((_QWORD *)&v43 + 1) - (_QWORD)v43 >= 2u && !v47[(unsigned __int64)v43 >> 1] )
            {
              v48 = LoadHelper::Initialize((LoadHelper *)v124, v47);
              v49 = v48;
              if ( v48 < 0 )
              {
                v163 = v48;
                if ( *(_QWORD *)&LogAdapter::g_Logger )
                {
                  LogAdapter::Logger::LogNumObjects<>(*(_QWORD *)&LogAdapter::g_Logger, 0, 3, "Failed to initialize {}");
                  v157 = (wchar_t *)&v163;
                  p_lpMem = &v157;
                  LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
                    *(_QWORD *)&LogAdapter::g_Logger,
                    1,
                    3,
                    ": {}");
                }
                wil::details::in1diag3::Return_Hr(
                  retaddr,
                  (void *)0x5C1,
                  (unsigned int)"onecore\\base\\cbs\\container\\servicingcontainerhelper.cpp",
                  (const char *)v49,
                  (int)p_lpMem);
                if ( hLibModule )
                  FreeLibrary(hLibModule);
                if ( v47 )
                  anonymous_namespace_::OurRtlFreeStringRoutine(v47);
                if ( P )
                {
                  LOBYTE(v50) = RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, P);
                  if ( !v50 )
                    __fastfail(7u);
                  P = 0;
                }
                if ( v29 )
                  anonymous_namespace_::OurRtlFreeStringRoutine(v29);
                return v49;
              }
              FunctionPointer = LoadHelper::GetFunctionPointer((LoadHelper *)v124, "CmsOfflineInitialize", &v129);
              v52 = FunctionPointer;
              if ( FunctionPointer < 0 )
              {
                v163 = FunctionPointer;
                if ( *(_QWORD *)&LogAdapter::g_Logger )
                {
                  LogAdapter::Logger::LogNumObjects<>(
                    *(_QWORD *)&LogAdapter::g_Logger,
                    0,
                    3,
                    "Failed to get address of function CmsOfflineInitialize.");
                  v157 = (wchar_t *)&v163;
                  p_lpMem = &v157;
                  LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
                    *(_QWORD *)&LogAdapter::g_Logger,
                    1,
                    3,
                    ": {}");
                }
                wil::details::in1diag3::Return_Hr(
                  retaddr,
                  (void *)0x5C4,
                  (unsigned int)"onecore\\base\\cbs\\container\\servicingcontainerhelper.cpp",
                  (const char *)v52,
                  (int)p_lpMem);
                if ( hLibModule )
                  FreeLibrary(hLibModule);
                if ( v47 )
                  anonymous_namespace_::OurRtlFreeStringRoutine(v47);
                if ( P )
                {
                  LOBYTE(v53) = RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, P);
                  if ( !v53 )
                    __fastfail(7u);
                  P = 0;
                }
                if ( v29 )
                  anonymous_namespace_::OurRtlFreeStringRoutine(v29);
                return v52;
              }
              v54 = LoadHelper::GetFunctionPointer((LoadHelper *)v124, "CmsOfflineCleanup", &v162);
              v55 = v54;
              if ( v54 < 0 )
              {
                v163 = v54;
                if ( *(_QWORD *)&LogAdapter::g_Logger )
                {
                  LogAdapter::Logger::LogNumObjects<>(
                    *(_QWORD *)&LogAdapter::g_Logger,
                    0,
                    3,
                    "Failed to get address of function CmsOfflineCleanup.");
                  v157 = (wchar_t *)&v163;
                  p_lpMem = &v157;
                  LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
                    *(_QWORD *)&LogAdapter::g_Logger,
                    1,
                    3,
                    ": {}");
                }
                wil::details::in1diag3::Return_Hr(
                  retaddr,
                  (void *)0x5C7,
                  (unsigned int)"onecore\\base\\cbs\\container\\servicingcontainerhelper.cpp",
                  (const char *)v55,
                  (int)p_lpMem);
                if ( hLibModule )
                  FreeLibrary(hLibModule);
                if ( v47 )
                  anonymous_namespace_::OurRtlFreeStringRoutine(v47);
                if ( P )
                {
                  LOBYTE(v56) = RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, P);
                  if ( !v56 )
                    __fastfail(7u);
                  P = 0;
                }
                if ( v29 )
                  anonymous_namespace_::OurRtlFreeStringRoutine(v29);
                return v55;
              }
              v57 = LoadHelper::GetFunctionPointer((LoadHelper *)v124, "CmsOfflineCreateServicingTransaction", &v128);
              v58 = v57;
              if ( v57 < 0 )
              {
                v163 = v57;
                if ( *(_QWORD *)&LogAdapter::g_Logger )
                {
                  LogAdapter::Logger::LogNumObjects<>(
                    *(_QWORD *)&LogAdapter::g_Logger,
                    0,
                    3,
                    "Failed to get address of function CmsOfflineCreateServicingTransaction.");
                  v157 = (wchar_t *)&v163;
                  p_lpMem = &v157;
                  LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
                    *(_QWORD *)&LogAdapter::g_Logger,
                    1,
                    3,
                    ": {}");
                }
                wil::details::in1diag3::Return_Hr(
                  retaddr,
                  (void *)0x5CA,
                  (unsigned int)"onecore\\base\\cbs\\container\\servicingcontainerhelper.cpp",
                  (const char *)v58,
                  (int)p_lpMem);
                if ( hLibModule )
                  FreeLibrary(hLibModule);
                if ( v47 )
                  anonymous_namespace_::OurRtlFreeStringRoutine(v47);
                if ( P )
                {
                  LOBYTE(v59) = RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, P);
                  if ( !v59 )
                    __fastfail(7u);
                  P = 0;
                }
                if ( v29 )
                  anonymous_namespace_::OurRtlFreeStringRoutine(v29);
                return v58;
              }
              v60 = LoadHelper::GetFunctionPointer((LoadHelper *)v124, "CmsOfflineDeleteServicingTransaction", &v160);
              v61 = v60;
              if ( v60 < 0 )
              {
                v163 = v60;
                if ( *(_QWORD *)&LogAdapter::g_Logger )
                {
                  LogAdapter::Logger::LogNumObjects<>(
                    *(_QWORD *)&LogAdapter::g_Logger,
                    0,
                    3,
                    "Failed to get address of function CmsOfflineDeleteServicingTransaction.");
                  v157 = (wchar_t *)&v163;
                  p_lpMem = &v157;
                  LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
                    *(_QWORD *)&LogAdapter::g_Logger,
                    1,
                    3,
                    ": {}");
                }
                wil::details::in1diag3::Return_Hr(
                  retaddr,
                  (void *)0x5CD,
                  (unsigned int)"onecore\\base\\cbs\\container\\servicingcontainerhelper.cpp",
                  (const char *)v61,
                  (int)p_lpMem);
                if ( hLibModule )
                  FreeLibrary(hLibModule);
                if ( v47 )
                  anonymous_namespace_::OurRtlFreeStringRoutine(v47);
                if ( P )
                {
                  LOBYTE(v62) = RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, P);
                  if ( !v62 )
                    __fastfail(7u);
                  P = 0;
                }
                if ( v29 )
                  anonymous_namespace_::OurRtlFreeStringRoutine(v29);
                return v61;
              }
              v63 = LoadHelper::GetFunctionPointer((LoadHelper *)v124, "CmsOfflineCloseServicingTransaction", &v161);
              v64 = v63;
              if ( v63 < 0 )
              {
                v163 = v63;
                if ( *(_QWORD *)&LogAdapter::g_Logger )
                {
                  LogAdapter::Logger::LogNumObjects<>(
                    *(_QWORD *)&LogAdapter::g_Logger,
                    0,
                    3,
                    "Failed to get address of function CmsOfflineCloseServicingTransaction.");
                  v157 = (wchar_t *)&v163;
                  p_lpMem = &v157;
                  LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
                    *(_QWORD *)&LogAdapter::g_Logger,
                    1,
                    3,
                    ": {}");
                }
                wil::details::in1diag3::Return_Hr(
                  retaddr,
                  (void *)0x5D0,
                  (unsigned int)"onecore\\base\\cbs\\container\\servicingcontainerhelper.cpp",
                  (const char *)v64,
                  (int)p_lpMem);
                if ( hLibModule )
                  FreeLibrary(hLibModule);
                if ( v47 )
                  anonymous_namespace_::OurRtlFreeStringRoutine(v47);
                if ( P )
                {
                  LOBYTE(v65) = RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, P);
                  if ( !v65 )
                    __fastfail(7u);
                  P = 0;
                }
                if ( v29 )
                  anonymous_namespace_::OurRtlFreeStringRoutine(v29);
                return v64;
              }
              v165 = 0;
              v159 = 0;
              v172[0] = 0;
              v172[1] = (void *)-1LL;
              v173 = 0;
              v66 = EtwLogger::Start((EtwLogger *)v172, L"ServiceContainerBaseImages");
              if ( v66 < 0 )
              {
                v163 = v66;
                if ( *(_QWORD *)&LogAdapter::g_Logger )
                {
                  LogAdapter::Logger::LogNumObjects<Windows::AutoGenericHandle<wchar_t *,0,&void Windows::Detail::CloseWithCoTaskMemFree<wchar_t>(wchar_t *)>>(
                    *(_QWORD *)&LogAdapter::g_Logger,
                    0,
                    3,
                    "Failed to start ETW tracing {}",
                    off_1802BDE70);
                  v157 = (wchar_t *)&v163;
                  p_lpMem = &v157;
                  LOBYTE(v67) = 1;
                  LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
                    *(_QWORD *)&LogAdapter::g_Logger,
                    v67,
                    3,
                    ": {}");
                }
              }
              v140 = 1;
              v141[0] = &v165;
              v141[1] = &v159;
              v141[2] = &v160;
              v141[3] = &v161;
              v141[4] = &v162;
              v141[5] = v172;
              v68 = v129();
              v69 = v68;
              LOBYTE(v70) = 0;
              if ( v68 < 0 )
              {
                v163 = v68;
                if ( *(_QWORD *)&LogAdapter::g_Logger )
                {
                  LogAdapter::Logger::LogNumObjects<>(
                    *(_QWORD *)&LogAdapter::g_Logger,
                    0,
                    3,
                    "Failed to initialize cmsservicing.");
                  v157 = (wchar_t *)&v163;
                  p_lpMem = &v157;
                  LOBYTE(v71) = 1;
                  LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
                    *(_QWORD *)&LogAdapter::g_Logger,
                    v71,
                    3,
                    ": {}");
                }
                wil::details::in1diag3::Return_Hr(
                  retaddr,
                  (void *)0x5E4,
                  (unsigned int)"onecore\\base\\cbs\\container\\servicingcontainerhelper.cpp",
                  (const char *)v69,
                  (int)p_lpMem);
                ServiceContainerBaseImages_::_3_::_lambda_1_::operator()(v141);
                EtwLogger::Stop((EtwLogger *)v172);
                if ( v173 )
                {
                  operator delete((void *)(v173 - 8), v72);
                  v173 = 0;
                }
                if ( v172[0] )
                {
                  operator delete(v172[0], v72);
                  v172[0] = 0;
                }
                if ( hLibModule )
                  FreeLibrary(hLibModule);
                if ( v47 )
                  anonymous_namespace_::OurRtlFreeStringRoutine(v47);
                if ( P )
                {
                  LOBYTE(v73) = RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, P);
                  if ( !v73 )
                    __fastfail(7u);
                  P = 0;
                }
                if ( v29 )
                  anonymous_namespace_::OurRtlFreeStringRoutine(v29);
                return v69;
              }
              pguid = 0;
              v74 = CoCreateGuid(&pguid);
              v75 = v74;
              if ( v74 < 0 )
              {
                v163 = v74;
                if ( *(_QWORD *)&LogAdapter::g_Logger )
                {
                  LogAdapter::Logger::LogNumObjects<>(
                    *(_QWORD *)&LogAdapter::g_Logger,
                    0,
                    3,
                    "Failed to create transaction guid.");
                  v157 = (wchar_t *)&v163;
                  p_lpMem = &v157;
                  LOBYTE(v76) = 1;
                  LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
                    *(_QWORD *)&LogAdapter::g_Logger,
                    v76,
                    3,
                    ": {}");
                }
                wil::details::in1diag3::Return_Hr(
                  retaddr,
                  (void *)0x5E8,
                  (unsigned int)"onecore\\base\\cbs\\container\\servicingcontainerhelper.cpp",
                  (const char *)v75,
                  (int)p_lpMem);
                ServiceContainerBaseImages_::_3_::_lambda_1_::operator()(v141);
                EtwLogger::Stop((EtwLogger *)v172);
                if ( v173 )
                {
                  operator delete((void *)(v173 - 8), v77);
                  v173 = 0;
                }
                if ( v172[0] )
                {
                  operator delete(v172[0], v77);
                  v172[0] = 0;
                }
                if ( hLibModule )
                  FreeLibrary(hLibModule);
                if ( v47 )
                  anonymous_namespace_::OurRtlFreeStringRoutine(v47);
                if ( P )
                {
                  LOBYTE(v78) = RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, P);
                  if ( !v78 )
                    __fastfail(7u);
                  P = 0;
                }
                if ( v29 )
                  anonymous_namespace_::OurRtlFreeStringRoutine(v29);
                return v75;
              }
              v79 = ((__int64 (__fastcall *)(GUID *, void **))v128)(&pguid, &v159);
              v80 = v79;
              if ( v79 < 0 )
              {
                v163 = v79;
                if ( *(_QWORD *)&LogAdapter::g_Logger )
                {
                  LogAdapter::Logger::LogNumObjects<>(
                    *(_QWORD *)&LogAdapter::g_Logger,
                    0,
                    3,
                    "Failed to create servicing transaction.");
                  v157 = (wchar_t *)&v163;
                  p_lpMem = &v157;
                  LOBYTE(v81) = 1;
                  LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
                    *(_QWORD *)&LogAdapter::g_Logger,
                    v81,
                    3,
                    ": {}");
                }
                wil::details::in1diag3::Return_Hr(
                  retaddr,
                  (void *)0x5EB,
                  (unsigned int)"onecore\\base\\cbs\\container\\servicingcontainerhelper.cpp",
                  (const char *)v80,
                  (int)p_lpMem);
                ServiceContainerBaseImages_::_3_::_lambda_1_::operator()(v141);
                EtwLogger::~EtwLogger((EtwLogger *)v172);
                if ( hLibModule )
                  FreeLibrary(hLibModule);
                if ( v47 )
                  anonymous_namespace_::OurRtlFreeStringRoutine(v47);
                Windows::AutoHeapPtr<wchar_t>::~AutoHeapPtr<wchar_t>(&P);
                if ( v29 )
                  anonymous_namespace_::OurRtlFreeStringRoutine(v29);
                return v80;
              }
              v163 = 0;
              v137 = 0;
              v157 = 0;
              v133 = 0;
              if ( v9 )
              {
                v82 = StringCchCopyW(v174, 0x100u, v9);
                v83 = v82;
                if ( v82 < 0 )
                {
                  wil::details::in1diag3::Return_Hr(
                    retaddr,
                    (void *)0x5F2,
                    (unsigned int)"onecore\\base\\cbs\\container\\servicingcontainerhelper.cpp",
                    (const char *)(unsigned int)v82,
                    (int)p_lpMem);
                  ServiceContainerBaseImages_::_3_::_lambda_1_::operator()(v141);
                  EtwLogger::~EtwLogger((EtwLogger *)v172);
                  if ( hLibModule )
                    FreeLibrary(hLibModule);
                  if ( v47 )
                    anonymous_namespace_::OurRtlFreeStringRoutine(v47);
                  Windows::AutoHeapPtr<wchar_t>::~AutoHeapPtr<wchar_t>(&P);
                  if ( v29 )
                    anonymous_namespace_::OurRtlFreeStringRoutine(v29);
                  return v83;
                }
                v84 = ShredStringIdIntoAttributes(
                        v174,
                        0x7Eu,
                        (const wchar_t **)&v157,
                        0,
                        (const wchar_t **)&v133,
                        0,
                        (const wchar_t **)&v137);
                v85 = v84;
                if ( v84 < 0 )
                {
                  wil::details::in1diag3::Return_Hr(
                    retaddr,
                    (void *)0x5F5,
                    (unsigned int)"onecore\\base\\cbs\\container\\servicingcontainerhelper.cpp",
                    (const char *)(unsigned int)v84,
                    (int)p_lpMem);
                  ServiceContainerBaseImages_::_3_::_lambda_1_::operator()(v141);
                  EtwLogger::~EtwLogger((EtwLogger *)v172);
                  if ( hLibModule )
                    FreeLibrary(hLibModule);
                  if ( v47 )
                    anonymous_namespace_::OurRtlFreeStringRoutine(v47);
                  Windows::AutoHeapPtr<wchar_t>::~AutoHeapPtr<wchar_t>(&P);
                  if ( v29 )
                    anonymous_namespace_::OurRtlFreeStringRoutine(v29);
                  return v85;
                }
                v70 = (unsigned __int8)Windows::StringUtil::IsStringPrefixEqualByOrdinalCaseInvariant<wchar_t const *,wchar_t const *>(
                                         &off_1802BDEA0,
                                         &v158) != 0;
                v163 = v70;
              }
              v166[0] = 0;
              v167 = 0;
              Turbostack = LoadTurbostack(P, v166);
              v87 = Turbostack;
              if ( Turbostack < 0 )
              {
                v163 = Turbostack;
                if ( *(_QWORD *)&LogAdapter::g_Logger )
                {
                  LogAdapter::Logger::LogNumObjects<>(
                    *(_QWORD *)&LogAdapter::g_Logger,
                    0,
                    3,
                    "Unable to load turbostack.dll");
                  v157 = (wchar_t *)&v163;
                  p_lpMem = &v157;
                  LOBYTE(v88) = 1;
                  LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
                    *(_QWORD *)&LogAdapter::g_Logger,
                    v88,
                    3,
                    ": {}");
                }
                wil::details::in1diag3::Return_Hr(
                  retaddr,
                  (void *)0x5FE,
                  (unsigned int)"onecore\\base\\cbs\\container\\servicingcontainerhelper.cpp",
                  (const char *)v87,
                  (int)p_lpMem);
                if ( v167 )
                  FreeLibrary(v167);
                ServiceContainerBaseImages_::_3_::_lambda_1_::operator()(v141);
                EtwLogger::~EtwLogger((EtwLogger *)v172);
                if ( hLibModule )
                  FreeLibrary(hLibModule);
                if ( v47 )
                  anonymous_namespace_::OurRtlFreeStringRoutine(v47);
                Windows::AutoHeapPtr<wchar_t>::~AutoHeapPtr<wchar_t>(&P);
                if ( v29 )
                  anonymous_namespace_::OurRtlFreeStringRoutine(v29);
                return v87;
              }
              CCbsStringArray::CCbsStringArray((CCbsStringArray *)v169);
              if ( v126[1] )
              {
                v158 = *v126;
                v91 = v127;
              }
              else
              {
                v90 = Windows::StringUtil::c_str<Windows::Auto<_LUNICODE_STRING>>(&v131);
                v91 = v127;
                ConfigFilePaths = GetConfigFilePaths(v127, (LoadHelper *)v166, v90, (__int64 (*)(void))lpMem, v70, v169);
                v93 = ConfigFilePaths;
                if ( ConfigFilePaths < 0 )
                {
                  wil::details::in1diag3::Return_Hr(
                    retaddr,
                    (void *)0x604,
                    (unsigned int)"onecore\\base\\cbs\\container\\servicingcontainerhelper.cpp",
                    (const char *)(unsigned int)ConfigFilePaths,
                    (int)p_lpMem);
                  CCbsArrayBase<wchar_t *,CCbsStringArray>::~CCbsArrayBase<wchar_t *,CCbsStringArray>(v169);
                  if ( v167 )
                    FreeLibrary(v167);
                  ServiceContainerBaseImages_::_3_::_lambda_1_::operator()(v141);
                  EtwLogger::~EtwLogger((EtwLogger *)v172);
                  if ( hLibModule )
                    FreeLibrary(hLibModule);
                  if ( v47 )
                    anonymous_namespace_::OurRtlFreeStringRoutine(v47);
                  Windows::AutoHeapPtr<wchar_t>::~AutoHeapPtr<wchar_t>(&P);
                  if ( v29 )
                    anonymous_namespace_::OurRtlFreeStringRoutine(v29);
                  return v93;
                }
                v158 = v170;
              }
              v128 = 0;
              v94 = (__int64 (*)(void))*v91;
              v95 = (__int64)&(*v91)[(_QWORD)v91[1]];
              for ( i = v95; ; v95 = i )
              {
                v129 = v94;
                if ( v94 == (__int64 (*)(void))v95 )
                  break;
                v138 = 0;
                v139 = 0;
                v96 = Windows::StringUtil::Rtl::CombineAndNullTerminateWin32Paths<Windows::Auto<_LUNICODE_STRING>,wchar_t const *>(
                        &v131,
                        v89,
                        &v138);
                v97 = v96;
                if ( v96 < 0 )
                {
                  v163 = v96;
                  if ( *(_QWORD *)&LogAdapter::g_Logger )
                  {
                    LogAdapter::Logger::LogNumObjects<>(
                      *(_QWORD *)&LogAdapter::g_Logger,
                      0,
                      3,
                      "Failed to create path for host Packages.");
                    lpMem = &v163;
                    p_lpMem = (wchar_t **)&lpMem;
                    LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatNtStatusWrapper<long>>(
                      *(_QWORD *)&LogAdapter::g_Logger,
                      v98,
                      3,
                      ": {}");
                  }
                  v99 = wil::details::in1diag3::Return_NtStatus(
                          retaddr,
                          (void *)0x613,
                          (unsigned int)"onecore\\base\\cbs\\container\\servicingcontainerhelper.cpp",
                          (const char *)v97,
                          (int)p_lpMem);
                  if ( v139 )
                    anonymous_namespace_::OurRtlFreeStringRoutine(v139);
                  CCbsArrayBase<wchar_t *,CCbsStringArray>::~CCbsArrayBase<wchar_t *,CCbsStringArray>(v169);
                  if ( v167 )
                    FreeLibrary(v167);
                  ServiceContainerBaseImages_::_3_::_lambda_1_::operator()(v141);
                  EtwLogger::~EtwLogger((EtwLogger *)v172);
                  if ( hLibModule )
                    FreeLibrary(hLibModule);
                  if ( v47 )
                    anonymous_namespace_::OurRtlFreeStringRoutine(v47);
                  Windows::AutoHeapPtr<wchar_t>::~AutoHeapPtr<wchar_t>(&P);
                  if ( v132 )
                    anonymous_namespace_::OurRtlFreeStringRoutine(v132);
                  return v99;
                }
                v144 = 0;
                v145 = 0;
                *(_OWORD *)v142 = 0;
                v143 = 0;
                CCbsStringArray::CCbsStringArray((CCbsStringArray *)v171);
                v126 = 0;
                DirectSystem = RtlGetDirectSystem(&v126);
                v101 = DirectSystem;
                if ( DirectSystem < 0 )
                {
                  wil::details::in1diag3::Return_Hr(
                    retaddr,
                    (void *)0x61B,
                    (unsigned int)"onecore\\base\\cbs\\container\\servicingcontainerhelper.cpp",
                    (const char *)(unsigned int)DirectSystem,
                    (int)p_lpMem);
                  if ( v126 )
                    (*(void (__fastcall **)(wchar_t **))*v126)(v126);
                  CCbsArrayBase<wchar_t *,CCbsStringArray>::~CCbsArrayBase<wchar_t *,CCbsStringArray>(v171);
                  if ( v139 )
                    anonymous_namespace_::OurRtlFreeStringRoutine(v139);
                  CCbsArrayBase<wchar_t *,CCbsStringArray>::~CCbsArrayBase<wchar_t *,CCbsStringArray>(v169);
                  if ( v167 )
                    FreeLibrary(v167);
                  ServiceContainerBaseImages_::_3_::_lambda_1_::operator()(v141);
                  EtwLogger::~EtwLogger((EtwLogger *)v172);
                  if ( hLibModule )
                    FreeLibrary(hLibModule);
                  if ( v47 )
                    anonymous_namespace_::OurRtlFreeStringRoutine(v47);
                  Windows::AutoHeapPtr<wchar_t>::~AutoHeapPtr<wchar_t>(&P);
                  if ( v132 )
                    anonymous_namespace_::OurRtlFreeStringRoutine(v132);
                  return v101;
                }
                v102 = *(_QWORD *)v94 - CMS_CLIENT_PROFESSIONAL_LAYER_ID;
                if ( *(_QWORD *)v94 == CMS_CLIENT_PROFESSIONAL_LAYER_ID )
                  v102 = *((_QWORD *)v94 + 1) + 0x43EC2C86689C996CLL;
                v103 = L"Professional.xml";
                if ( v102 )
                  v103 = &String2;
                v104 = v126;
                v105 = ProcessContainerConfigFile(
                         (_DWORD)v126,
                         *(_QWORD *)&v158[4 * (_QWORD)v128],
                         (_DWORD)v103,
                         (unsigned int)&v144,
                         (__int64)v142,
                         (__int64)v171);
                v106 = v105;
                if ( v105 < 0 )
                {
                  wil::details::in1diag3::Return_Hr(
                    retaddr,
                    (void *)0x61D,
                    (unsigned int)"onecore\\base\\cbs\\container\\servicingcontainerhelper.cpp",
                    (const char *)(unsigned int)v105,
                    v123);
                  if ( v104 )
                    (*(void (__fastcall **)(wchar_t **))*v104)(v104);
                  CCbsArrayBase<wchar_t *,CCbsStringArray>::~CCbsArrayBase<wchar_t *,CCbsStringArray>(v171);
                  if ( v143 )
                    anonymous_namespace_::OurRtlFreeStringRoutine(v143);
                  if ( v145 )
                    anonymous_namespace_::OurRtlFreeStringRoutine(v145);
                  if ( v139 )
                    anonymous_namespace_::OurRtlFreeStringRoutine(v139);
                  CCbsArrayBase<wchar_t *,CCbsStringArray>::~CCbsArrayBase<wchar_t *,CCbsStringArray>(v169);
                  if ( v167 )
                    FreeLibrary(v167);
                  ServiceContainerBaseImages_::_3_::_lambda_1_::operator()(v141);
                  EtwLogger::~EtwLogger((EtwLogger *)v172);
                  if ( hLibModule )
                    FreeLibrary(hLibModule);
                  if ( v47 )
                    anonymous_namespace_::OurRtlFreeStringRoutine(v47);
                  Windows::AutoHeapPtr<wchar_t>::~AutoHeapPtr<wchar_t>(&P);
                  if ( v132 )
                    anonymous_namespace_::OurRtlFreeStringRoutine(v132);
                  return v106;
                }
                v107 = 0;
                v127 = 0;
                if ( v70 )
                {
                  v108 = wil::str_printf<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<wchar_t *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>>>(
                           &lpMem,
                           L"%ws~31bf3856ad364e35~%ws~~%ws",
                           v157,
                           v133,
                           v137);
                  wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<wchar_t *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>>::operator=(
                    &v127,
                    v108);
                  v109 = lpMem;
                  if ( lpMem )
                  {
                    v110 = GetProcessHeap();
                    HeapFree(v110, 0, v109);
                  }
                  v107 = v127;
                }
                v111 = v159;
                v112 = (const wchar_t *)Windows::StringUtil::c_str<Windows::Auto<_LUNICODE_STRING>>(&v138);
                v113 = (const wchar_t *)Windows::StringUtil::c_str<Windows::Auto<_LUNICODE_STRING>>(v142);
                v114 = Windows::StringUtil::c_str<Windows::Auto<_LUNICODE_STRING>>(&v144);
                v153 = *v149;
                v154 = *(struct _GUID *)LayerIdToClientId(v156, v129, v115, v114);
                v155 = *v116;
                v118 = ServiceBaseImageInternal(
                         &v155,
                         v150,
                         (const wchar_t *const)P,
                         &v154,
                         &v153,
                         v117,
                         v113,
                         (struct CCbsStringArray *)v171,
                         v112,
                         v111,
                         0);
                v119 = v118;
                if ( v118 < 0 )
                {
                  wil::details::in1diag3::Return_Hr(
                    retaddr,
                    (void *)0x629,
                    (unsigned int)"onecore\\base\\cbs\\container\\servicingcontainerhelper.cpp",
                    (const char *)(unsigned int)v118,
                    (int)p_lpMem);
                  if ( v107 )
                  {
                    v120 = GetProcessHeap();
                    HeapFree(v120, 0, v107);
                  }
                  if ( v126 )
                    (*(void (__fastcall **)(wchar_t **))*v126)(v126);
                  CCbsArrayBase<wchar_t *,CCbsStringArray>::~CCbsArrayBase<wchar_t *,CCbsStringArray>(v171);
                  if ( v143 )
                    anonymous_namespace_::OurRtlFreeStringRoutine(v143);
                  if ( v145 )
                    anonymous_namespace_::OurRtlFreeStringRoutine(v145);
                  if ( v139 )
                    anonymous_namespace_::OurRtlFreeStringRoutine(v139);
                  CCbsArrayBase<wchar_t *,CCbsStringArray>::~CCbsArrayBase<wchar_t *,CCbsStringArray>(v169);
                  if ( v167 )
                    FreeLibrary(v167);
                  ServiceContainerBaseImages_::_3_::_lambda_1_::operator()(v141);
                  EtwLogger::~EtwLogger((EtwLogger *)v172);
                  if ( hLibModule )
                    FreeLibrary(hLibModule);
                  if ( v47 )
                    anonymous_namespace_::OurRtlFreeStringRoutine(v47);
                  Windows::AutoHeapPtr<wchar_t>::~AutoHeapPtr<wchar_t>(&P);
                  if ( v132 )
                    anonymous_namespace_::OurRtlFreeStringRoutine(v132);
                  return v119;
                }
                v128 = (__int64 (*)(void))((char *)v128 + 1);
                if ( v107 )
                {
                  v121 = GetProcessHeap();
                  HeapFree(v121, 0, v107);
                }
                if ( v126 )
                  (*(void (__fastcall **)(wchar_t **))*v126)(v126);
                CCbsArrayBase<wchar_t *,CCbsStringArray>::~CCbsArrayBase<wchar_t *,CCbsStringArray>(v171);
                if ( v143 )
                  anonymous_namespace_::OurRtlFreeStringRoutine(v143);
                if ( v145 )
                  anonymous_namespace_::OurRtlFreeStringRoutine(v145);
                if ( v139 )
                  anonymous_namespace_::OurRtlFreeStringRoutine(v139);
                v94 = (__int64 (*)(void))((char *)v129 + 16);
                v29 = v132;
                LOBYTE(v70) = v163;
              }
              **(_OWORD **)v134 = pguid;
              v165 = 1;
              CCbsArrayBase<wchar_t *,CCbsStringArray>::~CCbsArrayBase<wchar_t *,CCbsStringArray>(v169);
              if ( v167 )
                FreeLibrary(v167);
              ServiceContainerBaseImages_::_3_::_lambda_1_::operator()(v141);
              EtwLogger::~EtwLogger((EtwLogger *)v172);
              if ( hLibModule )
                FreeLibrary(hLibModule);
              if ( v47 )
                anonymous_namespace_::OurRtlFreeStringRoutine(v47);
              Windows::AutoHeapPtr<wchar_t>::~AutoHeapPtr<wchar_t>(&P);
              if ( v29 )
                anonymous_namespace_::OurRtlFreeStringRoutine(v29);
              return 0;
            }
LABEL_362:
            INTERNAL_ERROR_ACTION(-1073741595);
            JUMPOUT(0x18027D998LL);
          }
          if ( (__int64)v135 + 2 < (unsigned __int64)v135 )
          {
            v42 = -1073741675;
          }
          else
          {
            v42 = RtlReallocateLUnicodeString(v41, v135 + 2, &v135);
            if ( v42 >= 0 )
            {
              v43 = v135;
              goto LABEL_83;
            }
          }
        }
        v163 = v42;
        if ( *(_QWORD *)&LogAdapter::g_Logger )
        {
          LogAdapter::Logger::LogNumObjects<>(
            *(_QWORD *)&LogAdapter::g_Logger,
            0,
            3,
            "Failed to create path for cmservicing.");
          v157 = (wchar_t *)&v163;
          p_lpMem = &v157;
          LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatNtStatusWrapper<long>>(
            *(_QWORD *)&LogAdapter::g_Logger,
            v44,
            3,
            ": {}");
        }
        v45 = wil::details::in1diag3::Return_NtStatus(
                retaddr,
                (void *)0x5B8,
                (unsigned int)"onecore\\base\\cbs\\container\\servicingcontainerhelper.cpp",
                (const char *)(unsigned int)v42,
                (int)p_lpMem);
        if ( v136 )
          anonymous_namespace_::OurRtlFreeStringRoutine(v136);
        if ( P )
        {
          LOBYTE(v46) = RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, P);
          if ( !v46 )
            __fastfail(7u);
          P = 0;
        }
        if ( v29 )
          anonymous_namespace_::OurRtlFreeStringRoutine(v29);
        return v45;
      }
    }
    INTERNAL_ERROR_ACTION(-1073741595);
    goto LABEL_362;
  }
  catch ( ... )
  {
    return (unsigned int)wil::details::in1diag3::Return_CaughtException(
                           retaddr,
                           (void *)0x632,
                           (unsigned int)"onecore\\base\\cbs\\container\\servicingcontainerhelper.cpp",
                           v14);
  }
  return result;
}

```

## disassembly

```asm
0x18027b984  mov     r11, rsp
0x18027b987  push    rbx
0x18027b988  push    rsi
0x18027b989  push    rdi
0x18027b98a  push    r12
0x18027b98c  push    r13
0x18027b98e  push    r14
0x18027b990  push    r15
0x18027b992  sub     rsp, 0D00h
0x18027b999  mov     qword ptr [r11-0BA8h], 0FFFFFFFFFFFFFFFEh
0x18027b9a4  mov     rax, cs:__security_cookie
0x18027b9ab  xor     rax, rsp
0x18027b9ae  mov     [rsp+0D38h+var_48], rax
0x18027b9b6  mov     rbx, r9
0x18027b9b9  mov     [rsp+0D38h+var_CC0], rbx
0x18027b9be  mov     r14, r8
0x18027b9c1  mov     [r11-0C88h], r8
0x18027b9c8  mov     r15, rdx
0x18027b9cb  mov     [rsp+0D38h+lpMem], rdx
0x18027b9d3  mov     r12, rcx
0x18027b9d6  mov     [r11-0BB8h], rcx
0x18027b9dd  mov     [r11-0B58h], rcx
0x18027b9e4  mov     [r11-0B50h], r8
0x18027b9eb  mov     rsi, [rsp+0D38h+arg_20]
0x18027b9f3  mov     [rsp+0D38h+var_CC8], rsi
0x18027b9f8  mov     rdi, [rsp+0D38h+arg_28]
0x18027ba00  mov     rax, [rsp+0D38h+arg_30]
0x18027ba08  mov     [rsp+0D38h+var_BC0], rax
0x18027ba10  mov     rax, [rsp+0D38h+arg_38]
0x18027ba18  mov     qword ptr [rsp+0D38h+var_C80], rax
0x18027ba20  xor     r13d, r13d
0x18027ba23  cmp     cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA, r13; LogAdapter::Logger * LogAdapter::g_Logger
0x18027ba2a  jnz     short loc_18027BA51
0x18027ba2c  call    ?IsWdsLoggerSetup@@YA_NPEAPEAUHINSTANCE__@@@Z; IsWdsLoggerSetup(HINSTANCE__ * *)
0x18027ba31  test    al, al
0x18027ba33  jz      short loc_18027BA51
0x18027ba35  lea     rax, ?wdsLogger@@3VWdsLogger@LogAdapter@@A; LogAdapter::WdsLogger wdsLogger
0x18027ba3c  mov     cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA, rax; LogAdapter::Logger * LogAdapter::g_Logger
0x18027ba43  lea     rax, ?CbsCustomLogging@@YAXIPEBD@Z; CbsCustomLogging(uint,char const *)
0x18027ba4a  mov     cs:?vpfnCustomLogging@@3P6AXIPEBD@ZEA, rax; void (*vpfnCustomLogging)(uint,char const *)
0x18027ba51  mov     rcx, r12; lpFileName
0x18027ba54  call    cs:__imp_GetFileAttributesW
0x18027ba5b  nop     dword ptr [rax+rax+00h]
0x18027ba60  test    al, 10h
0x18027ba62  jz      loc_18027D8D1
0x18027ba68  test    r15, r15
0x18027ba6b  jz      short loc_18027BA7B
0x18027ba6d  test    r14, r14
0x18027ba70  jz      short loc_18027BA7B
0x18027ba72  mov     rax, [rbx+8]
0x18027ba76  jmp     loc_18027BB13
0x18027ba7b  mov     rax, [rbx+8]
0x18027ba7f  cmp     [rsi+8], rax
0x18027ba83  jz      loc_18027BB13
0x18027ba89  mov     ebx, 80070057h
0x18027ba8e  mov     [rsp+0D38h+var_B28], ebx
0x18027ba95  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x18027ba9c  test    rcx, rcx
0x18027ba9f  jz      short loc_18027BAF0
0x18027baa1  lea     r9, aMissingTopLeve; "Missing top level package or configDirs"...
0x18027baa8  mov     r12d, 3
0x18027baae  mov     r8d, r12d
0x18027bab1  xor     edx, edx
0x18027bab3  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x18027bab8  lea     rax, [rsp+0D38h+var_B28]
0x18027bac0  mov     [rsp+0D38h+var_B58], rax
0x18027bac8  lea     rax, [rsp+0D38h+var_B58]
0x18027bad0  mov     [rsp+0D38h+var_D18], rax; int
0x18027bad5  lea     r9, asc_1802C6678; ": {}"
0x18027badc  mov     r8d, r12d
0x18027badf  lea     edx, [r12-2]
0x18027bae4  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x18027baeb  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x18027baf0  mov     rcx, [rsp+0D38h]; this
0x18027baf8  mov     r9d, ebx; char *
0x18027bafb  lea     r8, aOnecoreBaseCbs_9; "onecore\\base\\cbs\\container\\servicin"...
0x18027bb02  mov     edx, 59Ch; void *
0x18027bb07  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18027bb0c  mov     eax, ebx
0x18027bb0e  jmp     loc_18027D95F
0x18027bb13  test    rax, rax
0x18027bb16  jz      loc_18027D95F
0x18027bb1c  xorps   xmm0, xmm0
0x18027bb1f  xor     eax, eax
0x18027bb21  movups  [rsp+0D38h+var_CA0], xmm0
0x18027bb29  mov     [rsp+0D38h+var_C90], rax
0x18027bb31  lea     r8, [rsp+0D38h+var_CA0]
0x18027bb39  lea     rcx, [rsp+0D38h+var_B58]
0x18027bb41  call    ??$CombineAndNullTerminateWin32Paths@PEB_W$$BY07_W@Rtl@StringUtil@Windows@@YAJAEBQEB_WAEAY07$$CB_WPEAV?$Auto@U_LUNICODE_STRING@@@2@@Z; Windows::StringUtil::Rtl::CombineAndNullTerminateWin32Paths<wchar_t const *,wchar_t [8]>(wchar_t const * const &,wchar_t const (&)[8],Windows::Auto<_LUNICODE_STRING> *)
0x18027bb46  mov     ebx, eax
0x18027bb48  test    eax, eax
0x18027bb4a  jns     loc_18027BBE5
0x18027bb50  mov     [rsp+0D38h+var_B28], eax
0x18027bb57  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x18027bb5e  test    rcx, rcx
0x18027bb61  jz      short loc_18027BBAD
0x18027bb63  lea     r9, aFailedToCreate_31; "Failed to create path for host windows "...
0x18027bb6a  mov     r12d, 3
0x18027bb70  mov     r8d, r12d
0x18027bb73  xor     edx, edx
0x18027bb75  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x18027bb7a  lea     rax, [rsp+0D38h+var_B28]
0x18027bb82  mov     [rsp+0D38h+var_B58], rax
0x18027bb8a  lea     rax, [rsp+0D38h+var_B58]
0x18027bb92  mov     [rsp+0D38h+var_D18], rax; int
0x18027bb97  lea     r9, asc_1802C6678; ": {}"
0x18027bb9e  mov     r8d, r12d
0x18027bba1  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x18027bba8  call    ??$LogNumObjects@U?$FormatNtStatusWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatNtStatusWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatNtStatusWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatNtStatusWrapper<long> const &)
0x18027bbad  mov     rcx, [rsp+0D38h]; this
0x18027bbb5  mov     r9d, ebx; char *
0x18027bbb8  lea     r8, aOnecoreBaseCbs_9; "onecore\\base\\cbs\\container\\servicin"...
0x18027bbbf  mov     edx, 5A6h; void *
0x18027bbc4  call    ?Return_NtStatus@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Return_NtStatus(void *,uint,char const *,long)
0x18027bbc9  mov     ebx, eax
0x18027bbcb  mov     rcx, [rsp+0D38h+var_C90]
0x18027bbd3  test    rcx, rcx
0x18027bbd6  jz      short loc_18027BBDE
0x18027bbd8  call    _anonymous_namespace___OurRtlFreeStringRoutine
0x18027bbdd  nop
0x18027bbde  mov     eax, ebx
0x18027bbe0  jmp     loc_18027D95F
0x18027bbe5  mov     [rsp+0D38h+P], r13
0x18027bbed  test    rdi, rdi
0x18027bbf0  jz      loc_18027BDC1
0x18027bbf6  or      rsi, 0FFFFFFFFFFFFFFFFh
0x18027bbfa  mov     rax, rsi
0x18027bbfd  inc     rax
0x18027bc00  cmp     [rdi+rax*2], r13w
0x18027bc05  jnz     short loc_18027BBFD
0x18027bc07  lea     r14, [rax+1]
0x18027bc0b  lea     rbx, [r14+r14]
0x18027bc0f  call    cs:__imp_GetProcessHeap
0x18027bc16  nop     dword ptr [rax+rax+00h]
0x18027bc1b  mov     rcx, rax; hHeap
0x18027bc1e  mov     r8, rbx; dwBytes
0x18027bc21  xor     edx, edx; dwFlags
0x18027bc23  call    cs:__imp_HeapAlloc
0x18027bc2a  nop     dword ptr [rax+rax+00h]
0x18027bc2f  cmp     [rsp+0D38h+P], r13
0x18027bc37  jnz     loc_18027D983
0x18027bc3d  mov     [rsp+0D38h+P], rax
0x18027bc45  test    rax, rax
0x18027bc48  jnz     short loc_18027BCBF
0x18027bc4a  mov     rcx, [rsp+0D38h]; this
0x18027bc52  mov     ebx, 8007000Eh
0x18027bc57  mov     r9d, ebx; char *
0x18027bc5a  lea     r8, aOnecoreBaseCbs_9; "onecore\\base\\cbs\\container\\servicin"...
0x18027bc61  mov     edx, 5ADh; void *
0x18027bc66  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18027bc6b  nop
0x18027bc6c  mov     r8, [rsp+0D38h+P]; P
0x18027bc74  test    r8, r8
0x18027bc77  jz      short loc_18027BCA5
0x18027bc79  mov     rcx, gs:60h
0x18027bc82  xor     edx, edx; Flags
0x18027bc84  mov     rcx, [rcx+30h]; HeapHandle
0x18027bc88  call    cs:__imp_RtlFreeHeap
0x18027bc8f  nop     dword ptr [rax+rax+00h]
0x18027bc94  test    eax, eax
0x18027bc96  jnz     short loc_18027BC9D
0x18027bc98  lea     ecx, [rax+7]
0x18027bc9b  int     29h; Win8: RtlFailFast(ecx)
0x18027bc9d  mov     [rsp+0D38h+P], r13
0x18027bca5  mov     rcx, [rsp+0D38h+var_C90]
0x18027bcad  test    rcx, rcx
0x18027bcb0  jz      short loc_18027BCB8
0x18027bcb2  call    _anonymous_namespace___OurRtlFreeStringRoutine
0x18027bcb7  nop
0x18027bcb8  mov     eax, ebx
0x18027bcba  jmp     loc_18027D95F
0x18027bcbf  mov     r8, rdi; wchar_t *
0x18027bcc2  mov     rdx, r14; unsigned __int64
0x18027bcc5  mov     rcx, rax; wchar_t *
0x18027bcc8  call    ?StringCchCopyW@@YAJPEA_W_KPEB_W@Z; StringCchCopyW(wchar_t *,unsigned __int64,wchar_t const *)
0x18027bccd  mov     ebx, eax
0x18027bccf  test    eax, eax
0x18027bcd1  jns     loc_18027BDAC
0x18027bcd7  mov     [rsp+0D38h+var_B28], eax
0x18027bcde  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x18027bce5  test    rcx, rcx
0x18027bce8  jz      short loc_18027BD3C
0x18027bcea  lea     r9, aFailedToCopySs; "Failed to copy ssu path."
0x18027bcf1  mov     r12d, 3
0x18027bcf7  mov     r8d, r12d
0x18027bcfa  xor     edx, edx
0x18027bcfc  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x18027bd01  lea     rax, [rsp+0D38h+var_B28]
0x18027bd09  mov     [rsp+0D38h+var_B58], rax
0x18027bd11  lea     rax, [rsp+0D38h+var_B58]
0x18027bd19  mov     [rsp+0D38h+var_D18], rax; int
0x18027bd1e  lea     r9, asc_1802C6678; ": {}"
0x18027bd25  mov     r8d, r12d
0x18027bd28  lea     edx, [r12-2]
0x18027bd2d  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x18027bd34  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x18027bd39  xor     r13d, r13d
0x18027bd3c  mov     rcx, [rsp+0D38h]; this
0x18027bd44  mov     r9d, ebx; char *
0x18027bd47  lea     r8, aOnecoreBaseCbs_9; "onecore\\base\\cbs\\container\\servicin"...
0x18027bd4e  mov     edx, 5AFh; void *
0x18027bd53  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18027bd58  nop
0x18027bd59  mov     r8, [rsp+0D38h+P]; P
0x18027bd61  test    r8, r8
0x18027bd64  jz      short loc_18027BD92
0x18027bd66  mov     rcx, gs:60h
0x18027bd6f  xor     edx, edx; Flags
0x18027bd71  mov     rcx, [rcx+30h]; HeapHandle
0x18027bd75  call    cs:__imp_RtlFreeHeap
0x18027bd7c  nop     dword ptr [rax+rax+00h]
0x18027bd81  test    eax, eax
0x18027bd83  jnz     short loc_18027BD8A
0x18027bd85  lea     ecx, [rax+7]
0x18027bd88  int     29h; Win8: RtlFailFast(ecx)
0x18027bd8a  mov     [rsp+0D38h+P], r13
0x18027bd92  mov     rcx, [rsp+0D38h+var_C90]
0x18027bd9a  test    rcx, rcx
0x18027bd9d  jz      short loc_18027BDA5
0x18027bd9f  call    _anonymous_namespace___OurRtlFreeStringRoutine
0x18027bda4  nop
0x18027bda5  mov     eax, ebx
0x18027bda7  jmp     loc_18027D95F
0x18027bdac  mov     rbx, [rsp+0D38h+var_C90]
0x18027bdb4  mov     r14, [rsp+0D38h+var_C88]
0x18027bdbc  jmp     loc_18027BEEA
0x18027bdc1  mov     rbx, [rsp+0D38h+var_C90]
0x18027bdc9  test    rbx, rbx
0x18027bdcc  jz      short loc_18027BDF9
0x18027bdce  mov     rax, qword ptr [rsp+0D38h+var_CA0+8]
0x18027bdd6  mov     rcx, qword ptr [rsp+0D38h+var_CA0]
0x18027bdde  sub     rax, rcx
0x18027bde1  cmp     rax, 2
0x18027bde5  jb      loc_18027D983
0x18027bdeb  shr     rcx, 1
0x18027bdee  cmp     [rbx+rcx*2], r13w
0x18027bdf3  jnz     loc_18027D983
0x18027bdf9  lea     r8, [rsp+0D38h+P]
0x18027be01  mov     rdx, r15
0x18027be04  mov     rcx, rbx; wchar_t *
0x18027be07  call    GetSsuPath
0x18027be0c  mov     edi, eax
0x18027be0e  test    eax, eax
0x18027be10  jns     loc_18027BEE6
0x18027be16  mov     [rsp+0D38h+var_B28], eax
0x18027be1d  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x18027be24  test    rcx, rcx
0x18027be27  jz      short loc_18027BE7B
0x18027be29  lea     r9, aFailedToGetSsu; "Failed to get SSU Path"
0x18027be30  mov     r12d, 3
0x18027be36  mov     r8d, r12d
0x18027be39  xor     edx, edx
0x18027be3b  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x18027be40  lea     rax, [rsp+0D38h+var_B28]
0x18027be48  mov     [rsp+0D38h+var_B58], rax
0x18027be50  lea     rax, [rsp+0D38h+var_B58]
0x18027be58  mov     [rsp+0D38h+var_D18], rax; int
0x18027be5d  lea     r9, asc_1802C6678; ": {}"
0x18027be64  mov     r8d, r12d
0x18027be67  lea     edx, [r12-2]
0x18027be6c  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x18027be73  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x18027be78  xor     r13d, r13d
0x18027be7b  mov     rcx, [rsp+0D38h]; this
0x18027be83  mov     r9d, edi; char *
0x18027be86  lea     r8, aOnecoreBaseCbs_9; "onecore\\base\\cbs\\container\\servicin"...
0x18027be8d  mov     edx, 5B3h; void *
0x18027be92  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18027be97  nop
0x18027be98  mov     r8, [rsp+0D38h+P]; P
0x18027bea0  test    r8, r8
0x18027bea3  jz      short loc_18027BED1
0x18027bea5  mov     rcx, gs:60h
0x18027beae  xor     edx, edx; Flags
0x18027beb0  mov     rcx, [rcx+30h]; HeapHandle
0x18027beb4  call    cs:__imp_RtlFreeHeap
0x18027bebb  nop     dword ptr [rax+rax+00h]
0x18027bec0  test    eax, eax
0x18027bec2  jnz     short loc_18027BEC9
0x18027bec4  lea     ecx, [rax+7]
0x18027bec7  int     29h; Win8: RtlFailFast(ecx)
0x18027bec9  mov     [rsp+0D38h+P], r13
0x18027bed1  test    rbx, rbx
0x18027bed4  jz      short loc_18027BEDF
0x18027bed6  mov     rcx, rbx
0x18027bed9  call    _anonymous_namespace___OurRtlFreeStringRoutine
0x18027bede  nop
0x18027bedf  mov     eax, edi
0x18027bee1  jmp     loc_18027D95F
0x18027bee6  or      rsi, 0FFFFFFFFFFFFFFFFh
0x18027beea  xorps   xmm0, xmm0
0x18027beed  xor     eax, eax
0x18027beef  movups  [rsp+0D38h+var_C78], xmm0
0x18027bef7  mov     [rsp+0D38h+var_C68], rax
0x18027beff  mov     rax, [rsp+0D38h+P]
0x18027bf07  test    rax, rax
0x18027bf0a  jz      short loc_18027BF22
0x18027bf0c  mov     rcx, rsi
0x18027bf0f  inc     rcx
0x18027bf12  cmp     [rax+rcx*2], r13w
  ... truncated ...
```
