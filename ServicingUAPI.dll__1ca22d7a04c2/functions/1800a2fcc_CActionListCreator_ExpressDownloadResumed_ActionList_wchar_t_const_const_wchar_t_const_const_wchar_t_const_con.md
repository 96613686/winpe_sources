# CActionListCreator::ExpressDownloadResumed(ActionList * *,wchar_t const * const,wchar_t const * const,wchar_t const * const)

- ea: `0x1800a2fcc`
- end: `0x1800a500a`
- name: `?ExpressDownloadResumed@CActionListCreator@@QEAAJPEAPEAUActionList@@QEB_W11@Z`
- size: `8254`
- prototype: `__int64 __fastcall(CActionListCreator *__hidden this, struct ActionList **, const wchar_t *const, const wchar_t *const, const wchar_t *const)`
- caller_count: `1`
- callee_count: `54`
- tags: `file_ops, registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x180069378`

## callees

- `0x1800031d0`
- `0x180003c64`
- `0x180006198`
- `0x1800062b8`
- `0x180007f68`
- `0x180008b78`
- `0x180009660`
- `0x180009750`
- `0x18000ba40`
- `0x18000ca2c`
- `0x18000cc98`
- `0x18000ccb8`
- `0x18000f614`
- `0x18000f874`
- `0x18001085c`
- `0x18001a810`
- `0x18001b9e4`
- `0x18001ba14`
- `0x18001ba4c`
- `0x18001ba80`
- `0x18001c3c4`
- `0x18001c478`
- `0x18001c608`
- `0x1800296a4`
- `0x18002b66c`
- `0x18002bc54`
- `0x18002fc5c`
- `0x18002ff64`
- `0x18002ffa0`
- `0x180036990`
- `0x18003d278`
- `0x18003d670`
- `0x18003ddc8`
- `0x18003e9cc`
- `0x180042764`
- `0x180043160`
- `0x1800432e0`
- `0x180051984`
- `0x1800670fc`
- `0x180073000`
- `0x18007f820`
- `0x18009e188`
- `0x18009e588`
- `0x1800a0244`
- `0x1800a2fcc`
- `0x1800a87e0`
- `0x1800a8888`
- `0x1800aa4c8`
- `0x1800b7844`
- `0x1800b78c8`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!wcsrchr` at `0x1800a35d2`
- `api-ms-win-crt-private-l1-1-0!wcsrchr` at `0x1800a35d2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a34bc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a42f8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a4766`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a4ded`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a34bc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a42f8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a4766`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a4ded`
- `api-ms-win-core-libraryloader-l1-1-0!FreeLibrary` at `0x1800a34ac`
- `api-ms-win-core-libraryloader-l1-1-0!FreeLibrary` at `0x1800a4ddd`
- `api-ms-win-core-libraryloader-l1-1-0!FreeLibrary` at `0x1800a34ac`
- `api-ms-win-core-libraryloader-l1-1-0!FreeLibrary` at `0x1800a4ddd`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1800a3779`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1800a3779`
- `api-ms-win-core-file-l1-1-0!FindFirstFileW` at `0x1800a3d30`
- `api-ms-win-core-file-l1-1-0!FindFirstFileW` at `0x1800a3d30`
- `api-ms-win-core-kernel32-legacy-l1-1-0!CopyFileW` at `0x1800a3b55`
- `api-ms-win-core-kernel32-legacy-l1-1-0!CopyFileW` at `0x1800a3b55`

## string_xrefs

- `0x1800a3b03`: `ActionList.xml`
- `0x1800a4071`: `Failed to load dpx.dll`
- `0x1800a44a8`: `Failed creating directory {0}`
- `0x1800a3608`: `express.psf.cix.xml`
- `0x1800a369b`: `express.psf.cix.xml`
- `0x1800a397f`: `express.psf.cix.xml`
- `0x1800a3a18`: `Failed to extract cab file: {0} in directory {1}. Trying to extract WIM`
- `0x1800a450a`: `Unable to delete directory {0}`
- `0x1800a3bf7`: `%ws.cix.xml`
- `0x1800a42ac`: `ExpressPackageTargetDirectory already set`
- `0x1800a4312`: `Failed to copy ActionList to metadata folder.`
- `0x1800a3e37`: `Arbiter : Copying metadata contents from: {0} to {1}`
- `0x1800a4789`: `Failed to find a CiX file in directory: {0}`
- `0x1800a3d05`: `\*.cix.xml`

## pseudocode

```c
// Hidden C++ exception states: #wind=21
__int64 __fastcall CActionListCreator::ExpressDownloadResumed(
        CActionListCreator *this,
        struct ActionList **a2,
        const wchar_t *const a3,
        const WCHAR *a4,
        wchar_t *a5)
{
  CActionListCreator *v5; // r14
  const wchar_t *v6; // r13
  __int64 v7; // rbx
  __int64 v8; // rdi
  wchar_t *v9; // r15
  HINSTANCE v10; // rsi
  int v11; // eax
  int Directory; // r12d
  __int64 v13; // rdx
  __int64 v14; // rdx
  int v16; // eax
  __int64 v17; // rdx
  int v18; // eax
  __int64 v19; // rdx
  __int64 v20; // rcx
  __int64 v21; // rdx
  __int64 v22; // r8
  __int64 v23; // r13
  __int64 v24; // r12
  __int64 v25; // r14
  __int64 v26; // rdx
  wchar_t *v27; // rax
  wchar_t *v28; // rax
  wchar_t *v29; // rax
  __int64 v30; // rdx
  _QWORD *v31; // rcx
  unsigned int v32; // eax
  int v33; // edx
  __int64 v34; // rax
  __int64 v35; // rdx
  __int64 v36; // r12
  __int64 v37; // rax
  wchar_t *v38; // rax
  _QWORD *v39; // rax
  wchar_t *v40; // r13
  int v41; // r15d
  wchar_t *v42; // rax
  wchar_t **v43; // r12
  struct Windows::Rtl::IPoolAllocator *v44; // rcx
  wchar_t *v45; // r14
  wchar_t *v46; // rax
  WCHAR *v47; // rcx
  struct ActionList *v48; // rax
  __int64 v49; // r14
  __int64 v50; // r12
  __int64 v51; // r13
  _OWORD *v52; // r12
  void *v53; // r13
  __int64 v54; // r8
  LPCWSTR v55; // rax
  __int64 v56; // rax
  __int128 v57; // xmm6
  __int64 v58; // rcx
  __int64 v59; // rcx
  __int64 v60; // rdx
  int v61; // esi
  __int64 v62; // rdx
  __int64 v63; // r8
  __int64 v64; // r9
  struct Windows::Rtl::IPoolAllocator *v65; // rcx
  wchar_t *v66; // r14
  wchar_t *v67; // rax
  int CabFile; // eax
  __int64 v69; // rdx
  __int64 v70; // rcx
  __int64 v71; // rdx
  unsigned int v72; // r8d
  int v73; // eax
  __int64 v74; // rax
  unsigned int v75; // r8d
  __int64 v76; // rax
  int v77; // edx
  int v78; // r8d
  int v79; // r9d
  __int64 v80; // rax
  __int64 Path; // rax
  BOOL v82; // r14d
  __int64 v83; // r8
  int v84; // ebx
  __int64 v85; // rdx
  int v86; // edi
  wchar_t *v87; // rax
  int v88; // r12d
  wchar_t *v89; // rax
  _QWORD *v90; // r12
  _QWORD *v91; // r14
  int v92; // r13d
  __int128 *v93; // rax
  int v94; // r13d
  __int64 v95; // rcx
  _QWORD *v96; // rax
  void *v97; // rcx
  __int64 v98; // rdx
  __int64 v99; // rdx
  __int64 v100; // rdx
  __int64 v101; // rdx
  __int64 v102; // rdx
  __int64 v103; // rdx
  __int64 v104; // rdx
  signed int LastError; // esi
  __int64 v106; // rdx
  unsigned int v107; // eax
  __int64 v108; // rdx
  __int64 v109; // rdx
  __int64 v110; // rdx
  __int64 v111; // rdx
  __int64 v112; // rdx
  __int64 v113; // rdx
  __int64 v114; // rdx
  __int64 v115; // rdx
  signed int v116; // ebx
  __int64 v117; // rdx
  unsigned int v118; // eax
  __int64 v119; // rdx
  __int64 v120; // rdx
  __int64 v121; // rdx
  __int64 v122; // rdx
  __int64 v123; // rdx
  __int64 v124; // rdx
  __int64 v125; // rdx
  __int64 v126; // rdx
  int v127; // eax
  __int64 v128; // rdx
  struct ActionList *v129; // rax
  void *bIgnoreCase; // [rsp+28h] [rbp-E0h]
  unsigned int v131[2]; // [rsp+38h] [rbp-D0h] BYREF
  wchar_t *FirstFileW; // [rsp+40h] [rbp-C8h] BYREF
  __int64 v133; // [rsp+48h] [rbp-C0h]
  HINSTANCE v134; // [rsp+50h] [rbp-B8h] BYREF
  CActionListCreator *v135; // [rsp+58h] [rbp-B0h]
  __int64 v136; // [rsp+60h] [rbp-A8h] BYREF
  __int64 v137; // [rsp+68h] [rbp-A0h] BYREF
  __int64 v138; // [rsp+70h] [rbp-98h]
  wchar_t *Str; // [rsp+78h] [rbp-90h] BYREF
  __int64 v140; // [rsp+80h] [rbp-88h]
  wchar_t *v141; // [rsp+88h] [rbp-80h]
  const wchar_t *v142; // [rsp+90h] [rbp-78h]
  _BYTE v143[32]; // [rsp+98h] [rbp-70h] BYREF
  const WCHAR **v144; // [rsp+B8h] [rbp-50h]
  _OWORD *v145; // [rsp+C0h] [rbp-48h]
  struct ActionList **v146; // [rsp+C8h] [rbp-40h]
  _QWORD v147[2]; // [rsp+D0h] [rbp-38h] BYREF
  _QWORD v148[3]; // [rsp+E0h] [rbp-28h] BYREF
  _QWORD v149[2]; // [rsp+F8h] [rbp-10h] BYREF
  _QWORD v150[2]; // [rsp+108h] [rbp+0h] BYREF
  int v151[4]; // [rsp+118h] [rbp+10h] BYREF
  __int64 v152; // [rsp+128h] [rbp+20h]
  _BYTE v153[32]; // [rsp+130h] [rbp+28h] BYREF
  __int64 v154; // [rsp+150h] [rbp+48h]
  LPCWSTR lpExistingFileName; // [rsp+158h] [rbp+50h] BYREF
  int v156; // [rsp+160h] [rbp+58h] BYREF
  wchar_t *v157; // [rsp+168h] [rbp+60h] BYREF
  wchar_t *v158; // [rsp+170h] [rbp+68h] BYREF
  wchar_t *v159; // [rsp+178h] [rbp+70h] BYREF
  int v160; // [rsp+180h] [rbp+78h] BYREF
  const WCHAR *v161; // [rsp+188h] [rbp+80h] BYREF
  __int64 v162; // [rsp+190h] [rbp+88h]
  __int128 v163; // [rsp+198h] [rbp+90h] BYREF
  __int64 v164; // [rsp+1A8h] [rbp+A0h]
  unsigned __int64 v165; // [rsp+1B0h] [rbp+A8h]
  LPCWSTR lpFileName[2]; // [rsp+1B8h] [rbp+B0h] BYREF
  __int64 v167; // [rsp+1C8h] [rbp+C0h]
  __int128 v168; // [rsp+1D8h] [rbp+D0h] BYREF
  __int64 v169; // [rsp+1E8h] [rbp+E0h]
  struct _WIN32_FIND_DATAW FindFileData; // [rsp+1F8h] [rbp+F0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+4B0h] [rbp+3A8h]

  v154 = -2;
  v146 = a2;
  v5 = this;
  v135 = this;
  lpExistingFileName = a4;
  v6 = a5;
  v142 = a5;
  v160 = 0;
  v159 = 0;
  v157 = 0;
  v7 = 0;
  v137 = 0;
  v158 = 0;
  v8 = 0;
  v136 = 0;
  v9 = 0;
  Str = 0;
  v10 = 0;
  v134 = 0;
  v163 = 0;
  v164 = 0;
  v165 = 7;
  LOWORD(v163) = 0;
  if ( *(_QWORD *)this )
    __debugbreak();
  *(_QWORD *)this = *a2;
  *a2 = 0;
  LogAdapter::TraceInfo<>("arbiter: Express download resumed");
  v11 = SczAllocFromSz(&v159);
  Directory = v11;
  if ( v11 < 0 )
  {
    v160 = v11;
    if ( *(_QWORD *)&LogAdapter::g_Logger )
    {
      LogAdapter::Logger::LogNumObjects<>(*(_QWORD *)&LogAdapter::g_Logger, 0, 3, "Failed to allocate memory");
      FirstFileW = (wchar_t *)&v160;
      bIgnoreCase = &FirstFileW;
      LOBYTE(v13) = 1;
      LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
        *(_QWORD *)&LogAdapter::g_Logger,
        v13,
        3,
        ": {}");
    }
    v14 = 4382;
LABEL_7:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v14,
      (unsigned int)"onecore\\base\\servicing\\arbiter\\cactionlistcreator.cpp",
      (const char *)(unsigned int)Directory,
      (int)bIgnoreCase);
    std::wstring::~wstring(&v163);
    if ( v158 )
    {
      operator delete(v158 - 4);
      v158 = 0;
    }
    goto LABEL_9;
  }
  v16 = SczEnsureBackslashTerminated(&v159);
  Directory = v16;
  if ( v16 < 0 )
  {
    v160 = v16;
    if ( *(_QWORD *)&LogAdapter::g_Logger )
    {
      LogAdapter::Logger::LogNumObjects<>(*(_QWORD *)&LogAdapter::g_Logger, 0, 3, "Failed to allocate memory");
      FirstFileW = (wchar_t *)&v160;
      bIgnoreCase = &FirstFileW;
      LOBYTE(v17) = 1;
      LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
        *(_QWORD *)&LogAdapter::g_Logger,
        v17,
        3,
        ": {}");
    }
    v14 = 4384;
    goto LABEL_7;
  }
  v18 = SczAllocFromSz(&v157);
  Directory = v18;
  if ( v18 < 0 )
  {
    v160 = v18;
    if ( *(_QWORD *)&LogAdapter::g_Logger )
    {
      LogAdapter::Logger::LogNumObjects<>(*(_QWORD *)&LogAdapter::g_Logger, 0, 3, "Failed to allocate memory");
      FirstFileW = (wchar_t *)&v160;
      bIgnoreCase = &FirstFileW;
      LOBYTE(v19) = 1;
      LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
        *(_QWORD *)&LogAdapter::g_Logger,
        v19,
        3,
        ": {}");
    }
    v14 = 4386;
    goto LABEL_7;
  }
  v20 = -1;
  do
    ++v20;
  while ( v159[v20] );
  v138 = v20;
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_ArbiterMetadataContainer>::__private_IsEnabled(
                          `wil::Feature<__WilFeatureTraits_Feature_ArbiterMetadataContainer>::GetImpl'::`2'::impl,
                          0)
    && (unsigned __int8)IsMetadataContainerSupported(*(unsigned int *)(*(_QWORD *)v5 + 52LL), v21, v22, 0) )
  {
    v23 = *(_QWORD *)(*(_QWORD *)v5 + 392LL);
    v24 = v23 + 168LL * *(_QWORD *)(*(_QWORD *)v5 + 376LL);
    while ( v23 != v24 )
    {
      if ( *(_DWORD *)(v23 + 120) )
      {
        v25 = *(_QWORD *)(v23 + 112);
        v26 = 0;
        v27 = (wchar_t *)(v25 + 184LL * *(unsigned int *)(v23 + 120));
        FirstFileW = v27;
        if ( (wchar_t *)v25 == v27 )
        {
          v5 = v135;
        }
        else
        {
          do
          {
            if ( *(_DWORD *)(v25 + 8) == 2 && *(_QWORD *)(v25 + 24) )
            {
              v28 = DuplicateNullTerminatedString(
                      (struct Windows::Rtl::IPoolAllocator *)(*(_QWORD *)v135 + 264LL),
                      *(const wchar_t **)(v25 + 24));
              *(_QWORD *)(v25 + 104) = v28;
              if ( !v28 )
              {
                v30 = 4414;
                goto LABEL_45;
              }
              v26 = v25;
              v27 = FirstFileW;
            }
            v25 += 184;
          }
          while ( (wchar_t *)v25 != v27 );
          v5 = v135;
          if ( v26 )
          {
            v29 = DuplicateNullTerminatedString(
                    (struct Windows::Rtl::IPoolAllocator *)(*(_QWORD *)v135 + 264LL),
                    *(const wchar_t **)(v26 + 104));
            *(_QWORD *)(v23 + 80) = v29;
            if ( !v29 )
            {
              v30 = 4422;
LABEL_45:
              wil::details::in1diag3::Return_Hr(
                retaddr,
                (void *)v30,
                (unsigned int)"onecore\\base\\servicing\\arbiter\\cactionlistcreator.cpp",
                (const char *)0x8007000ELL,
                (int)bIgnoreCase);
              std::wstring::~wstring(&v163);
              if ( v158 )
              {
                operator delete(v158 - 4);
                v158 = 0;
              }
              if ( v157 )
              {
                operator delete(v157 - 4);
                v157 = 0;
              }
              goto LABEL_263;
            }
          }
        }
      }
      v23 += 168;
    }
    v6 = v142;
  }
  LOBYTE(v133) = 0;
  v31 = *(_QWORD **)v5;
  v32 = *(_DWORD *)(*(_QWORD *)v5 + 52LL);
  v33 = 4505604;
  if ( v32 <= 0x16 && _bittest(&v33, v32) )
  {
    v34 = v31[49];
    v35 = v34 + 168LL * v31[47];
    while ( v34 != v35 )
    {
      if ( *(_DWORD *)(v34 + 96) == 4 )
      {
        LOBYTE(v133) = 1;
        break;
      }
      v34 += 168;
    }
  }
  v36 = v31[41];
  v140 = v36;
  v37 = v36 + 168LL * v31[39];
  *(_QWORD *)v131 = v37;
  if ( v36 == v37 )
  {
LABEL_359:
    if ( !lpExistingFileName
      || (v127 = CActionListCreator::Save((__int64)v5, 1, lpExistingFileName), v84 = v127, v127 >= 0) )
    {
      v129 = *(struct ActionList **)v5;
      *(_QWORD *)v5 = 0;
      *v146 = v129;
      std::wstring::~wstring(&v163);
      CIUClient::~CIUClient((CIUClient *)&v134);
      AutoScz::~AutoScz((AutoScz *)&Str);
      AutoScz::~AutoScz((AutoScz *)&v136);
      AutoScz::~AutoScz((AutoScz *)&v158);
      AutoScz::~AutoScz((AutoScz *)&v137);
      AutoScz::~AutoScz((AutoScz *)&v157);
      AutoScz::~AutoScz((AutoScz *)&v159);
      return 0;
    }
    v156 = v127;
    if ( *(_QWORD *)&LogAdapter::g_Logger )
    {
      LogAdapter::Logger::LogNumObjects<wchar_t const *>(
        *(_QWORD *)&LogAdapter::g_Logger,
        0,
        3,
        "Failed to save to actionlist file: {0}",
        &lpExistingFileName);
      *(_QWORD *)v131 = &v156;
      bIgnoreCase = v131;
      LOBYTE(v128) = 1;
      LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
        *(_QWORD *)&LogAdapter::g_Logger,
        v128,
        3,
        ": {}");
    }
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1285,
      (unsigned int)"onecore\\base\\servicing\\arbiter\\cactionlistcreator.cpp",
      (const char *)(unsigned int)v84,
      (int)bIgnoreCase);
LABEL_364:
    std::wstring::~wstring(&v163);
    CIUClient::~CIUClient((CIUClient *)&v134);
    AutoScz::~AutoScz((AutoScz *)&Str);
    AutoScz::~AutoScz((AutoScz *)&v136);
    AutoScz::~AutoScz((AutoScz *)&v158);
    AutoScz::~AutoScz((AutoScz *)&v137);
    AutoScz::~AutoScz((AutoScz *)&v157);
    AutoScz::~AutoScz((AutoScz *)&v159);
    return (unsigned int)v84;
  }
  while ( 1 )
  {
    if ( *(_DWORD *)(v36 + 104) != 2 )
      goto LABEL_171;
    if ( *(_DWORD *)(*(_QWORD *)v5 + 52LL) == 8 )
    {
      v38 = DuplicateNullTerminatedString((struct Windows::Rtl::IPoolAllocator *)(*(_QWORD *)v5 + 264LL), v6);
      *(_QWORD *)(v36 + 128) = v38;
      if ( !v38 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x1168,
          (unsigned int)"onecore\\base\\servicing\\arbiter\\cactionlistcreator.cpp",
          (const char *)0x8007000ELL,
          (int)bIgnoreCase);
        std::wstring::~wstring(&v163);
        if ( v10 && !FreeLibrary(v10) )
        {
          GetLastError();
          __fastfail(7u);
        }
        if ( v9 )
          operator delete(v9 - 4);
        if ( v8 )
          operator delete((void *)(v8 - 8));
        if ( v158 )
        {
          operator delete(v158 - 4);
          v158 = 0;
        }
        if ( v7 )
          operator delete((void *)(v7 - 8));
        if ( v157 )
          goto LABEL_262;
        goto LABEL_263;
      }
    }
    v161 = 0;
    v162 = 0;
    v39 = operator new(0x40u);
    *v39 = v39;
    v39[1] = v39;
    v39[2] = v39;
    *((_WORD *)v39 + 12) = 257;
    v161 = (const WCHAR *)v39;
    v168 = 0;
    v169 = 0;
    v40 = *(wchar_t **)(v36 + 112);
    FirstFileW = v40;
    v141 = &v40[92 * *(unsigned int *)(v36 + 120)];
    if ( v40 != v141 )
      break;
LABEL_90:
    v48 = *(struct ActionList **)v5;
    v49 = *(_QWORD *)(*(_QWORD *)v5 + 712LL);
    v50 = v49 + 24LL * *((_QWORD *)v48 + 87);
    if ( v49 != v50 )
    {
      v51 = v140;
      while ( CompareStringOrdinal(*(LPCWCH *)(v51 + 24), -1, *(LPCWCH *)v49, -1, 1) != 2 )
      {
        v49 += 24;
        if ( v49 == v50 )
          goto LABEL_158;
      }
      *(_DWORD *)(v49 + 16) = 1;
    }
LABEL_158:
    if ( (_BYTE)v133 )
    {
      v90 = (_QWORD *)*((_QWORD *)&v168 + 1);
      v91 = (_QWORD *)v168;
      if ( (_QWORD)v168 != *((_QWORD *)&v168 + 1) && v164 && (_QWORD)v168 != *((_QWORD *)&v168 + 1) )
      {
        v92 = v160;
        do
        {
          LogAdapter::TraceInfo<std::wstring,std::wstring>(
            "Arbiter : Copying metadata contents from: {0} to {1}",
            v91,
            &v163);
          v93 = &v163;
          if ( v165 > 7 )
            v93 = (__int128 *)v163;
          v149[0] = v93;
          v149[1] = v164;
          to_wstring(v153, v149);
          v94 = v92 | 1;
          v95 = v91[2];
          if ( v91[3] <= 7u )
            v96 = v91;
          else
            v96 = (_QWORD *)*v91;
          v150[0] = v96;
          v150[1] = v95;
          to_wstring(v143, v150);
          v92 = v94 | 2;
          std::filesystem::copy(v143, v153);
          std::wstring::~wstring(v143);
          std::wstring::~wstring(v153);
          v91 += 4;
        }
        while ( v91 != v90 );
        v160 = v92;
      }
    }
    std::vector<std::wstring>::_Tidy(&v168);
    std::_Tree<std::_Tset_traits<std::wstring,WstringCaseInsensitiveCompare,std::allocator<std::wstring>,0>>::~_Tree<std::_Tset_traits<std::wstring,WstringCaseInsensitiveCompare,std::allocator<std::wstring>,0>>(&v161);
    v5 = v135;
    v36 = v140;
    v37 = *(_QWORD *)v131;
LABEL_171:
    v36 += 168;
    v140 = v36;
    if ( v36 == v37 )
      goto LABEL_359;
    v6 = v142;
  }
  while ( 1 )
  {
    v159[v138] = 0;
    v41 = SczAllocFromSz(&Str);
    if ( v41 < 0 )
    {
      v156 = v41;
      if ( *(_QWORD *)&LogAdapter::g_Logger )
      {
        LogAdapter::Logger::LogNumObjects<>(*(_QWORD *)&LogAdapter::g_Logger, 0, 3, "Failed to allocate memory");
        *(_QWORD *)v131 = &v156;
        bIgnoreCase = v131;
        LOBYTE(v126) = 1;
        LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
          *(_QWORD *)&LogAdapter::g_Logger,
          v126,
          3,
          ": {}");
      }
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x1172,
        (unsigned int)"onecore\\base\\servicing\\arbiter\\cactionlistcreator.cpp",
        (const char *)(unsigned int)v41,
        (int)bIgnoreCase);
      std::vector<std::wstring>::_Tidy(&v168);
      std::_Tree<std::_Tset_traits<std::wstring,WstringCaseInsensitiveCompare,std::allocator<std::wstring>,0>>::~_Tree<std::_Tset_traits<std::wstring,WstringCaseInsensitiveCompare,std::allocator<std::wstring>,0>>(&v161);
      std::wstring::~wstring(&v163);
      if ( v10 && !FreeLibrary(v10) )
      {
        GetLastError();
        __fastfail(7u);
      }
      if ( Str )
        operator delete(Str - 4);
      if ( v8 )
        operator delete((void *)(v8 - 8));
      if ( v158 )
      {
        operator delete(v158 - 4);
        v158 = 0;
      }
      if ( v7 )
        operator delete((void *)(v7 - 8));
      if ( v157 )
      {
        operator delete(v157 - 4);
        v157 = 0;
      }
      if ( v159 )
        operator delete(v159 - 4);
      return (unsigned int)v41;
    }
    v9 = Str;
    v42 = wcsrchr(Str, 0x2Eu);
    if ( v42 )
      *v42 = 0;
    Directory = SczAllocConcatSz(&v159, v9);
    if ( Directory < 0 )
      break;
    lpFileName[0] = 0;
    Directory = SczAllocFormatted(lpFileName, L"%ws\\%ws", v159, L"express.psf.cix.xml");
    if ( Directory < 0 )
    {
      v156 = Directory;
      if ( *(_QWORD *)&LogAdapter::g_Logger )
      {
        LogAdapter::Logger::LogNumObjects<>(*(_QWORD *)&LogAdapter::g_Logger, 0, 3, "Failed to allocate memory");
        *(_QWORD *)v131 = &v156;
        bIgnoreCase = v131;
        LOBYTE(v124) = 1;
        LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
          *(_QWORD *)&LogAdapter::g_Logger,
          v124,
          3,
          ": {}");
      }
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x118B,
        (unsigned int)"onecore\\base\\servicing\\arbiter\\cactionlistcreator.cpp",
        (const char *)(unsigned int)Directory,
        (int)bIgnoreCase);
      goto LABEL_185;
    }
    v43 = (wchar_t **)(v40 + 60);
    if ( *((_QWORD *)v40 + 15) )
    {
      LogAdapter::TraceInfo<wchar_t *,wchar_t *>(
        "Skipping previously processed express payload file: {0} for express cab: {1}",
        v40 + 60,
        v40 + 8);
      if ( lpFileName[0] )
        operator delete((void *)(lpFileName[0] - 4));
      goto LABEL_89;
    }
    if ( (unsigned int)DoesFileExist(lpFileName[0]) )
    {
      FirstFileW = 0;
      Directory = SczAllocFormatted(&FirstFileW, L"%ws\\%ws", &v159[v138], L"express.psf.cix.xml");
      if ( Directory < 0 )
      {
        v156 = Directory;
        if ( *(_QWORD *)&LogAdapter::g_Logger )
        {
          LogAdapter::Logger::LogNumObjects<>(*(_QWORD *)&LogAdapter::g_Logger, 0, 3, "Failed to allocate memory");
          *(_QWORD *)v131 = &v156;
          bIgnoreCase = v131;
          LOBYTE(v98) = 1;
          LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
            *(_QWORD *)&LogAdapter::g_Logger,
            v98,
            3,
            ": {}");
        }
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x119D,
          (unsigned int)"onecore\\base\\servicing\\arbiter\\cactionlistcreator.cpp",
          (const char *)(unsigned int)Directory,
          (int)bIgnoreCase);
        if ( FirstFileW )
          operator delete(FirstFileW - 4);
LABEL_185:
        if ( lpFileName[0] )
        {
          operator delete((void *)(lpFileName[0] - 4));
          lpFileName[0] = 0;
        }
        goto LABEL_331;
      }
      v44 = (struct Windows::Rtl::IPoolAllocator *)(*(_QWORD *)v5 + 264LL);
      v45 = FirstFileW;
      v46 = DuplicateNullTerminatedString(v44, FirstFileW);
      *((_QWORD *)v40 + 15) = v46;
      if ( !v46 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x119F,
          (unsigned int)"onecore\\base\\servicing\\arbiter\\cactionlistcreator.cpp",
          (const char *)0x8007000ELL,
          (int)bIgnoreCase);
        if ( v45 )
          operator delete(v45 - 4);
        if ( lpFileName[0] )
        {
          operator delete((void *)(lpFileName[0] - 4));
          lpFileName[0] = 0;
        }
        goto LABEL_177;
      }
      LogAdapter::TraceInfo<wchar_t const *,wchar_t const *>(
        "Skipping previously processed express payload file: {0} for express cab: {1}",
        lpFileName,
        v40 + 8);
      if ( v45 )
        operator delete(v45 - 4);
      if ( lpFileName[0] )
      {
        v47 = (WCHAR *)(lpFileName[0] - 4);
        goto LABEL_87;
      }
      goto LABEL_88;
    }
    if ( lpFileName[0] )
      operator delete((void *)(lpFileName[0] - 4));
    lpFileName[0] = v9;
    if ( !std::_Tree<std::_Tset_traits<std::wstring,WstringCaseInsensitiveCompare,std::allocator<std::wstring>,0>>::count<wchar_t *,WstringCaseInsensitiveCompare,0>(
            &v161,
            lpFileName) )
    {
      lpFileName[0] = v161;
      v144 = &v161;
      v145 = 0;
      v52 = operator new(0x40u);
      v145 = v52;
      v53 = v52 + 2;
      v52[2] = 0;
      *((_QWORD *)v52 + 6) = 0;
      *((_QWORD *)v52 + 7) = 0;
      v54 = -1;
      do
        ++v54;
      while ( v9[v54] );
      std::wstring::_Construct<1,wchar_t const *>(v53);
      v55 = lpFileName[0];
      *(LPCWSTR *)v52 = lpFileName[0];
      *((_QWORD *)v52 + 1) = v55;
      *((_QWORD *)v52 + 2) = v55;
      *((_WORD *)v52 + 12) = 0;
      v56 = std::_Tree<std::_Tset_traits<std::wstring,WstringCaseInsensitiveCompare,std::allocator<std::wstring>,0>>::_Find_lower_bound<std::wstring>(
              &v161,
              v151,
              v53);
      v57 = *(_OWORD *)v56;
      if ( (unsigned __int8)std::_Tree<std::_Tset_traits<std::wstring,WstringCaseInsensitiveCompare,std::allocator<std::wstring>,0>>::_Lower_bound_duplicate<std::wstring>(
                              v58,
                              *(_QWORD *)(v56 + 16),
                              v53) )
      {
        std::wstring::~wstring(v53);
        operator delete(v52);
      }
      else
      {
        if ( v162 == 0x3FFFFFFFFFFFFFFLL )
          std::_Throw_tree_length_error();
        v145 = 0;
        *(_OWORD *)lpFileName = v57;
        std::_Tree_val<std::_Tree_simple_types<std::pair<std::wstring const,ActionList::FeatureAction>>>::_Insert_node(
          &v161,
          lpFileName,
          v52);
      }
      Directory = RecursiveRemoveDirectory(v59, v159);
      if ( Directory < 0 )
      {
        v156 = Directory;
        if ( *(_QWORD *)&LogAdapter::g_Logger )
        {
          LogAdapter::Logger::LogNumObjects<AutoScz>(
            *(_QWORD *)&LogAdapter::g_Logger,
            0,
            3,
            "Unable to delete directory {0}",
            &v159);
          *(_QWORD *)v131 = &v156;
          bIgnoreCase = v131;
          LOBYTE(v111) = 1;
          LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
            *(_QWORD *)&LogAdapter::g_Logger,
            v111,
            3,
            ": {}");
        }
        v110 = 4531;
LABEL_244:
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)v110,
          (unsigned int)"onecore\\base\\servicing\\arbiter\\cactionlistcreator.cpp",
          (const char *)(unsigned int)Directory,
          (int)bIgnoreCase);
        std::vector<std::wstring>::_Tidy(&v168);
        std::_Tree<std::_Tset_traits<std::wstring,WstringCaseInsensitiveCompare,std::allocator<std::wstring>,0>>::~_Tree<std::_Tset_traits<std::wstring,WstringCaseInsensitiveCompare,std::allocator<std::wstring>,0>>(&v161);
        std::wstring::~wstring(&v163);
        CIUClient::~CIUClient((CIUClient *)&v134);
        if ( v9 )
          operator delete(v9 - 4);
        if ( v8 )
          operator delete((void *)(v8 - 8));
        if ( v158 )
        {
          operator delete(v158 - 4);
          v158 = 0;
        }
        if ( v7 )
          operator delete((void *)(v7 - 8));
LABEL_9:
        if ( v157 )
          goto LABEL_10;
        goto LABEL_11;
      }
      Directory = RecursivelyCreateDirectory(v159, 0);
      if ( Directory < 0 )
      {
        v156 = Directory;
        if ( *(_QWORD *)&LogAdapter::g_Logger )
        {
          LogAdapter::Logger::LogNumObjects<AutoScz>(
            *(_QWORD *)&LogAdapter::g_Logger,
            0,
            3,
            "Failed creating directory {0}",
            &v159);
          *(_QWORD *)v131 = &v156;
          bIgnoreCase = v131;
          LOBYTE(v109) = 1;
          LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
            *(_QWORD *)&LogAdapter::g_Logger,
            v109,
            3,
            ": {}");
        }
        v110 = 4537;
        goto LABEL_244;
      }
      v157[v138] = 0;
      v40 = FirstFileW;
      Directory = SczAllocConcatSz(&v157, *((_QWORD *)FirstFileW + 3));
      if ( Directory < 0 )
      {
        v156 = Directory;
        if ( *(_QWORD *)&LogAdapter::g_Logger )
        {
          LogAdapter::Logger::LogNumObjects<>(*(_QWORD *)&LogAdapter::g_Logger, 0, 3, "Failed to allocate memory");
          *(_QWORD *)v131 = &v156;
          bIgnoreCase = v131;
          LOBYTE(v108) = 1;
          LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
            *(_QWORD *)&LogAdapter::g_Logger,
            v108,
            3,
            ": {}");
        }
        v103 = 4544;
        goto LABEL_330;
      }
      if ( !v10 )
      {
        v61 = DpxLoad(&v134);
        if ( v61 < 0 )
        {
          v156 = v61;
          if ( *(_QWORD *)&LogAdapter::g_Logger )
          {
            LogAdapter::Logger::LogNumObjects<>(*(_QWORD *)&LogAdapter::g_Logger, 0, 3, "Failed to load dpx.dll");
            *(_QWORD *)v131 = &v156;
            bIgnoreCase = v131;
            LOBYTE(v99) = 1;
            LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
              *(_QWORD *)&LogAdapter::g_Logger,
              v99,
              3,
              ": {}");
          }
          v100 = 4548;
          goto LABEL_190;
        }
        v10 = v134;
      }
      if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_ArbiterMetadataContainer>::__private_IsEnabled(
                              `wil::Feature<__WilFeatureTraits_Feature_ArbiterMetadataContainer>::GetImpl'::`2'::impl,
                              v60)
        && (unsigned __int8)IsMetadataContainerSupported(*(unsigned int *)(*(_QWORD *)v5 + 52LL), v62, v63, v64)
        && *((_DWORD *)v40 + 32) != 1 )
      {
        FirstFileW = 0;
        Directory = SczAllocFormatted(&FirstFileW, L"%ws\\%ws", &v159[v138], L"express.psf.cix.xml");
        if ( Directory < 0 )
        {
          v156 = Directory;
          if ( *(_QWORD *)&LogAdapter::g_Logger )
          {
            LogAdapter::Logger::LogNumObjects<>(*(_QWORD *)&LogAdapter::g_Logger, 0, 3, "Failed to allocate memory");
            *(_QWORD *)v131 = &v156;
            bIgnoreCase = v131;
            LOBYTE(v101) = 1;
            LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
              *(_QWORD *)&LogAdapter::g_Logger,
              v101,
              3,
              ": {}");
          }
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x11D6,
            (unsigned int)"onecore\\base\\servicing\\arbiter\\cactionlistcreator.cpp",
            (const char *)(unsigned int)Directory,
            (int)bIgnoreCase);
          if ( FirstFileW )
            operator delete(FirstFileW - 4);
          goto LABEL_331;
        }
        v65 = (struct Windows::Rtl::IPoolAllocator *)(*(_QWORD *)v5 + 264LL);
        v66 = FirstFileW;
        v67 = DuplicateNullTerminatedString(v65, FirstFileW);
        *((_QWORD *)v40 + 15) = v67;
        if ( !v67 )
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x11D8,
            (unsigned int)"onecore\\base\\servicing\\arbiter\\cactionlistcreator.cpp",
            (const char *)0x8007000ELL,
            (int)bIgnoreCase);
          if ( v66 )
            operator delete(v66 - 4);
LABEL_177:
          std::vector<std::wstring>::_Tidy(&v168);
          std::_Tree<std::_Tset_traits<std::wstring,WstringCaseInsensitiveCompare,std::allocator<std::wstring>,0>>::~_Tree<std::_Tset_traits<std::wstring,WstringCaseInsensitiveCompare,std::allocator<std::wstring>,0>>(&v161);
          std::wstring::~wstring(&v163);
          CIUClient::~CIUClient((CIUClient *)&v134);
          if ( v9 )
            operator delete(v9 - 4);
          if ( v8 )
          {
            v97 = (void *)(v8 - 8);
            goto LABEL_256;
          }
          goto LABEL_257;
        }
        if ( v66 )
        {
          v47 = v66 - 4;
LABEL_87:
          operator delete(v47);
        }
LABEL_88:
        v5 = v135;
        goto LABEL_89;
      }
      LogAdapter::TraceInfo<wchar_t const *>("Expanding express cab: {0}", v40 + 8);
      CabFile = ExtractCabFile(v157, v159, 1);
      if ( CabFile < 0 )
      {
        v156 = CabFile;
        if ( *(_QWORD *)&LogAdapter::g_Logger )
        {
          LogAdapter::Logger::LogPartial<AutoScz,AutoScz>(
            v70,
            v69,
            "Failed to extract cab file: {0} in directory {1}. Trying to extract WIM",
            &v157,
            &v159);
          FirstFileW = (wchar_t *)&v156;
          bIgnoreCase = &FirstFileW;
          LOBYTE(v71) = 1;
          LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
            *(_QWORD *)&LogAdapter::g_Logger,
            v71,
            1,
            ": {0}");
        }
        Directory = CbsEsdExtractAllFiles(v157, v159);
        if ( Directory < 0 )
        {
          v156 = Directory;
          if ( *(_QWORD *)&LogAdapter::g_Logger )
          {
            LogAdapter::Logger::LogNumObjects<AutoScz>(
              *(_QWORD *)&LogAdapter::g_Logger,
              0,
              3,
              "Failed to extract files from wim {0}.",
              &v157);
            *(_QWORD *)v131 = &v156;
            bIgnoreCase = v131;
            LOBYTE(v102) = 1;
            LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
              *(_QWORD *)&LogAdapter::g_Logger,
              v102,
              3,
              ": {}");
          }
          v103 = 4591;
          goto LABEL_330;
        }
      }
      v72 = *(_DWORD *)(*(_QWORD *)v5 + 52LL);
      if ( v72 <= 0x16 )
      {
        v73 = 4505604;
        if ( _bittest(&v73, v72) )
        {
          if ( *(_DWORD *)(v140 + 88) == 6 )
          {
            v74 = ActionTypeToLUTF8String(v153, *(unsigned int *)(v140 + 96));
            *(_OWORD *)lpFileName = *(_OWORD *)v74;
            v167 = *(_QWORD *)(v74 + 16);
            v76 = OperationTypeToLUTF8String(v143, v75);
            *(_OWORD *)v151 = *(_OWORD *)v76;
            v152 = *(_QWORD *)(v76 + 16);
            if ( *(_QWORD *)&LogAdapter::g_Logger )
              LogAdapter::Logger::LogNumObjects<_LUTF8_STRING,_LUTF8_STRING>(
                LogAdapter::g_Logger,
                v77,
                v78,
                v79,
                (__int64)v151,
                (__int64)lpFileName);
            v147[0] = L"ActionList.xml";
            v147[1] = 14;
            v148[0] = v159;
            v80 = -1;
            do
              ++v80;
            while ( v159[v80] );
            v148[1] = v80;
            Path = CreatePath(v143, v148, v147);
            if ( *(_QWORD *)(Path + 24) > 7u )
              Path = *(_QWORD *)Path;
            v82 = CopyFileW(lpExistingFileName, (LPCWSTR)Path, 0);
            std::wstring::~wstring(v143);
            if ( !v82 )
            {
              LastError = GetLastError();
              if ( *(_QWORD *)&LogAdapter::g_Logger )
              {
                LogAdapter::Logger::LogNumObjects<>(
                  *(_QWORD *)&LogAdapter::g_Logger,
                  0,
                  3,
                  "Failed to copy ActionList to metadata folder.");
                if ( LastError > 0 )
                  v107 = (unsigned __int16)LastError | 0x80070000;
                else
                  v107 = LastError;
                v156 = v107;
                *(_QWORD *)v131 = &v156;
                bIgnoreCase = v131;
                LOBYTE(v106) = 1;
                LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
                  *(_QWORD *)&LogAdapter::g_Logger,
                  v106,
                  3,
                  ": {0}");
              }
              if ( LastError )
              {
                v61 = wil::details::in1diag3::Return_Win32(
                        retaddr,
                        (void *)0x1205,
                        (unsigned int)"onecore\\base\\servicing\\arbiter\\cactionlistcreator.cpp",
                        (const char *)(unsigned int)LastError,
                        (unsigned int)bIgnoreCase);
                goto LABEL_191;
              }
              std::vector<std::wstring>::_Tidy(&v168);
              std::_Tree<std::_Tset_traits<std::wstring,WstringCaseInsensitiveCompare,std::allocator<std::wstring>,0>>::~_Tree<std::_Tset_traits<std::wstring,WstringCaseInsensitiveCompare,std::allocator<std::wstring>,0>>(&v161);
              std::wstring::~wstring(&v163);
              CIUClient::~CIUClient((CIUClient *)&v134);
              if ( v9 )
                operator delete(v9 - 4);
              if ( v8 )
                operator delete((void *)(v8 - 8));
              if ( v158 )
              {
                operator delete(v158 - 4);
                v158 = 0;
              }
              if ( v7 )
                operator delete((void *)(v7 - 8));
              if ( v157 )
              {
                operator delete(v157 - 4);
                v157 = 0;
              }
              if ( v159 )
                operator delete(v159 - 4);
              return 0;
            }
            if ( *((_QWORD *)v40 + 22) )
            {
              FirstFileW = v9;
              if ( (unsigned __int8)Windows::StringUtil::AreStringsEqualByOrdinalCaseInvariantNonReflexive<wchar_t *,wchar_t *>(&FirstFileW) )
              {
                if ( v164 )
                {
                  v61 = -2147418113;
                  v156 = -2147418113;
                  if ( *(_QWORD *)&LogAdapter::g_Logger )
                  {
                    LogAdapter::Logger::LogNumObjects<>(
                      *(_QWORD *)&LogAdapter::g_Logger,
                      0,
                      3,
                      "ExpressPackageTargetDirectory already set");
                    *(_QWORD *)v131 = &v156;
                    bIgnoreCase = v131;
                    LOBYTE(v104) = 1;
                    LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
                      *(_QWORD *)&LogAdapter::g_Logger,
                      v104,
                      3,
                      ": {}");
                  }
                  v100 = 4624;
LABEL_190:
                  wil::details::in1diag3::Return_Hr(
                    retaddr,
                    (void *)v100,
                    (unsigned int)"onecore\\base\\servicing\\arbiter\\cactionlistcreator.cpp",
                    (const char *)(unsigned int)v61,
                    (int)bIgnoreCase);
LABEL_191:
                  std::vector<std::wstring>::_Tidy(&v168);
                  std::_Tree<std::_Tset_traits<std::wstring,WstringCaseInsensitiveCompare,std::allocator<std::wstring>,0>>::~_Tree<std::_Tset_traits<std::wstring,WstringCaseInsensitiveCompare,std::allocator<std::wstring>,0>>(&v161);
                  std::wstring::~wstring(&v163);
                  CIUClient::~CIUClient((CIUClient *)&v134);
                  if ( v9 )
                    operator delete(v9 - 4);
                  if ( v8 )
                    operator delete((void *)(v8 - 8));
                  if ( v158 )
                  {
                    operator delete(v158 - 4);
                    v158 = 0;
                  }
                  if ( v7 )
                    operator delete((void *)(v7 - 8));
                  if ( v157 )
                  {
                    operator delete(v157 - 4);
                    v157 = 0;
                  }
                  if ( v159 )
                    operator delete(v159 - 4);
                  return (unsigned int)v61;
                }
                v83 = -1;
                do
                  ++v83;
                while ( v159[v83] );
                std::wstring::_Assign<wchar_t>(&v163, v159, v83);
              }
              else
              {
                std::wstring::wstring(v143, v159);
                std::vector<std::wstring>::push_back(&v168, v143);
                std::wstring::~wstring(v143);
              }
            }
            v5 = v135;
          }
        }
      }
      v43 = (wchar_t **)(v40 + 60);
    }
    v84 = SczAllocFormatted(&v137, L"%ws.cix.xml", *((_QWORD *)v40 + 9));
    if ( v84 < 0 )
    {
      v156 = v84;
      if ( *(_QWORD *)&LogAdapter::g_Logger )
      {
        LogAdapter::Logger::LogNumObjects<>(*(_QWORD *)&LogAdapter::g_Logger, 0, 3, "Failed to allocate memory");
        *(_QWORD *)v131 = &v156;
        bIgnoreCase = v131;
        LOBYTE(v123) = 1;
        LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
          *(_QWORD *)&LogAdapter::g_Logger,
          v123,
          3,
          ": {}");
      }
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x1220,
        (unsigned int)"onecore\\base\\servicing\\arbiter\\cactionlistcreator.cpp",
        (const char *)(unsigned int)v84,
        (int)bIgnoreCase);
      std::vector<std::wstring>::_Tidy(&v168);
      std::_Tree<std::_Tset_traits<std::wstring,WstringCaseInsensitiveCompare,std::allocator<std::wstring>,0>>::~_Tree<std::_Tset_traits<std::wstring,WstringCaseInsensitiveCompare,std::allocator<std::wstring>,0>>(&v161);
      std::wstring::~wstring(&v163);
      CIUClient::~CIUClient((CIUClient *)&v134);
      if ( v9 )
        operator delete(v9 - 4);
      if ( v8 )
        operator delete((void *)(v8 - 8));
      if ( v158 )
      {
        operator delete(v158 - 4);
        v158 = 0;
      }
      if ( v137 )
        operator delete((void *)(v137 - 8));
      if ( v157 )
      {
        operator delete(v157 - 4);
        v157 = 0;
      }
      if ( v159 )
        operator delete(v159 - 4);
      return (unsigned int)v84;
    }
    v7 = v137;
    v86 = SczAllocFormatted(&v136, L"%ws\\%ws", v159, v137);
    if ( v86 < 0 )
    {
      v156 = v86;
      if ( *(_QWORD *)&LogAdapter::g_Logger )
      {
        LogAdapter::Logger::LogNumObjects<>(*(_QWORD *)&LogAdapter::g_Logger, 0, 3, "Failed to allocate memory");
        *(_QWORD *)v131 = &v156;
        bIgnoreCase = v131;
        LOBYTE(v122) = 1;
        LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
          *(_QWORD *)&LogAdapter::g_Logger,
          v122,
          3,
          ": {}");
      }
      v113 = 4646;
      goto LABEL_296;
    }
    if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_ArbiterMetadataContainer>::__private_IsEnabled(
                            `wil::Feature<__WilFeatureTraits_Feature_ArbiterMetadataContainer>::GetImpl'::`2'::impl,
                            v85)
      && *(_DWORD *)(*(_QWORD *)v5 + 52LL) == 1
      && *((_DWORD *)v40 + 32) != 1 )
    {
      v86 = SczAllocFormatted(&v158, L"%ws\\%ws", &v159[v138], v7);
      if ( v86 < 0 )
      {
        v156 = v86;
        if ( *(_QWORD *)&LogAdapter::g_Logger )
        {
          LogAdapter::Logger::LogNumObjects<>(*(_QWORD *)&LogAdapter::g_Logger, 0, 3, "Failed to allocate memory");
          *(_QWORD *)v131 = &v156;
          bIgnoreCase = v131;
          LOBYTE(v112) = 1;
          LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
            *(_QWORD *)&LogAdapter::g_Logger,
            v112,
            3,
            ": {}");
        }
        v113 = 4655;
LABEL_296:
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)v113,
          (unsigned int)"onecore\\base\\servicing\\arbiter\\cactionlistcreator.cpp",
          (const char *)(unsigned int)v86,
          (int)bIgnoreCase);
        std::vector<std::wstring>::_Tidy(&v168);
        std::_Tree<std::_Tset_traits<std::wstring,WstringCaseInsensitiveCompare,std::allocator<std::wstring>,0>>::~_Tree<std::_Tset_traits<std::wstring,WstringCaseInsensitiveCompare,std::allocator<std::wstring>,0>>(&v161);
        std::wstring::~wstring(&v163);
        CIUClient::~CIUClient((CIUClient *)&v134);
        if ( v9 )
          operator delete(v9 - 4);
        if ( v136 )
          operator delete((void *)(v136 - 8));
        if ( v158 )
        {
          operator delete(v158 - 4);
          v158 = 0;
        }
        if ( v7 )
          operator delete((void *)(v7 - 8));
        if ( v157 )
        {
          operator delete(v157 - 4);
          v157 = 0;
        }
        if ( v159 )
          operator delete(v159 - 4);
        return (unsigned int)v86;
      }
      v87 = DuplicateNullTerminatedString((struct Windows::Rtl::IPoolAllocator *)(*(_QWORD *)v5 + 264LL), v158);
      *v43 = v87;
      if ( !v87 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x1232,
          (unsigned int)"onecore\\base\\servicing\\arbiter\\cactionlistcreator.cpp",
          (const char *)0x8007000ELL,
          (int)bIgnoreCase);
        std::vector<std::wstring>::_Tidy(&v168);
        std::_Tree<std::_Tset_traits<std::wstring,WstringCaseInsensitiveCompare,std::allocator<std::wstring>,0>>::~_Tree<std::_Tset_traits<std::wstring,WstringCaseInsensitiveCompare,std::allocator<std::wstring>,0>>(&v161);
        std::wstring::~wstring(&v163);
        CIUClient::~CIUClient((CIUClient *)&v134);
        if ( v9 )
          operator delete(v9 - 4);
        if ( v136 )
        {
          v97 = (void *)(v136 - 8);
LABEL_256:
          operator delete(v97);
        }
LABEL_257:
        if ( v158 )
        {
          operator delete(v158 - 4);
          v158 = 0;
        }
        if ( v7 )
          operator delete((void *)(v7 - 8));
        if ( v157 )
        {
LABEL_262:
          operator delete(v157 - 4);
          v157 = 0;
        }
LABEL_263:
        if ( v159 )
          operator delete(v159 - 4);
        return 2147942414LL;
      }
      v8 = v136;
    }
    else
    {
      v8 = v136;
      if ( !(unsigned int)DoesFileExist(v136) )
      {
        lpFileName[0] = 0;
        FirstFileW = 0;
        memset_0(&FindFileData, 0, sizeof(FindFileData));
        v84 = SczAllocFromSz(lpFileName);
        if ( v84 < 0 )
        {
          v156 = v84;
          if ( *(_QWORD *)&LogAdapter::g_Logger )
          {
            LogAdapter::Logger::LogNumObjects<>(*(_QWORD *)&LogAdapter::g_Logger, 0, 3, "Failed to allocate memory");
            *(_QWORD *)v131 = &v156;
            bIgnoreCase = v131;
            LOBYTE(v120) = 1;
            LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
              *(_QWORD *)&LogAdapter::g_Logger,
              v120,
              3,
              ": {}");
          }
          v115 = 4678;
          goto LABEL_286;
        }
        v84 = SczAllocConcatSz(lpFileName, L"\\*.cix.xml");
        if ( v84 < 0 )
        {
          v156 = v84;
          if ( *(_QWORD *)&LogAdapter::g_Logger )
          {
            LogAdapter::Logger::LogNumObjects<>(*(_QWORD *)&LogAdapter::g_Logger, 0, 3, "Failed to allocate memory");
            *(_QWORD *)v131 = &v156;
            bIgnoreCase = v131;
            LOBYTE(v119) = 1;
            LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
              *(_QWORD *)&LogAdapter::g_Logger,
              v119,
              3,
              ": {}");
          }
          v115 = 4680;
LABEL_286:
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)v115,
            (unsigned int)"onecore\\base\\servicing\\arbiter\\cactionlistcreator.cpp",
            (const char *)(unsigned int)v84,
            (int)bIgnoreCase);
LABEL_287:
          Windows::AutoGenericHandle<void *,1,&void Windows::Detail::CloseWithFindClose(void *)>::~AutoGenericHandle<void *,1,&void Windows::Detail::CloseWithFindClose(void *)>(&FirstFileW);
          AutoScz::~AutoScz((AutoScz *)lpFileName);
LABEL_292:
          std::vector<std::wstring>::_Tidy(&v168);
          std::_Tree<std::_Tset_traits<std::wstring,WstringCaseInsensitiveCompare,std::allocator<std::wstring>,0>>::~_Tree<std::_Tset_traits<std::wstring,WstringCaseInsensitiveCompare,std::allocator<std::wstring>,0>>(&v161);
          goto LABEL_364;
        }
        FirstFileW = (wchar_t *)FindFirstFileW(lpFileName[0], &FindFileData);
        if ( (unsigned __int64)FirstFileW - 1 > 0xFFFFFFFFFFFFFFFDuLL )
        {
          v116 = GetLastError();
          if ( *(_QWORD *)&LogAdapter::g_Logger )
          {
            LogAdapter::Logger::LogNumObjects<AutoScz>(
              *(_QWORD *)&LogAdapter::g_Logger,
              0,
              3,
              "Failed to find a CiX file in directory: {0}",
              &v159);
            if ( v116 > 0 )
              v118 = (unsigned __int16)v116 | 0x80070000;
            else
              v118 = v116;
            v156 = v118;
            *(_QWORD *)v131 = &v156;
            bIgnoreCase = v131;
            LOBYTE(v117) = 1;
            LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
              *(_QWORD *)&LogAdapter::g_Logger,
              v117,
              3,
              ": {0}");
          }
          if ( v116 )
            v84 = wil::details::in1diag3::Return_Win32(
                    retaddr,
                    (void *)0x124B,
                    (unsigned int)"onecore\\base\\servicing\\arbiter\\cactionlistcreator.cpp",
                    (const char *)(unsigned int)v116,
                    (unsigned int)bIgnoreCase);
          else
            v84 = 0;
          goto LABEL_287;
        }
        v84 = SczAllocFromSz(&v137);
        if ( v84 < 0 )
        {
          v156 = v84;
          if ( *(_QWORD *)&LogAdapter::g_Logger )
          {
            LogAdapter::Logger::LogNumObjects<>(*(_QWORD *)&LogAdapter::g_Logger, 0, 3, "Failed to allocate memory");
            *(_QWORD *)v131 = &v156;
            bIgnoreCase = v131;
            LOBYTE(v114) = 1;
            LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
              *(_QWORD *)&LogAdapter::g_Logger,
              v114,
              3,
              ": {}");
          }
          v115 = 4685;
          goto LABEL_286;
        }
        Windows::AutoGenericHandle<void *,1,&void Windows::Detail::CloseWithFindClose(void *)>::~AutoGenericHandle<void *,1,&void Windows::Detail::CloseWithFindClose(void *)>(&FirstFileW);
        AutoScz::~AutoScz((AutoScz *)lpFileName);
        v7 = v137;
      }
      v88 = SczAllocFormatted(&v158, L"%ws\\%ws", &v159[v138], v7);
      if ( v88 < 0 )
      {
        v156 = v88;
        if ( *(_QWORD *)&LogAdapter::g_Logger )
        {
          LogAdapter::Logger::LogNumObjects<>(*(_QWORD *)&LogAdapter::g_Logger, 0, 3, "Failed to allocate memory");
          *(_QWORD *)v131 = &v156;
          bIgnoreCase = v131;
          LOBYTE(v121) = 1;
          LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
            *(_QWORD *)&LogAdapter::g_Logger,
            v121,
            3,
            ": {}");
        }
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x1251,
          (unsigned int)"onecore\\base\\servicing\\arbiter\\cactionlistcreator.cpp",
          (const char *)(unsigned int)v88,
          (int)bIgnoreCase);
        v84 = v88;
        goto LABEL_292;
      }
      v89 = DuplicateNullTerminatedString((struct Windows::Rtl::IPoolAllocator *)(*(_QWORD *)v5 + 264LL), v158);
      *((_QWORD *)v40 + 15) = v89;
      if ( !v89 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x1254,
          (unsigned int)"onecore\\base\\servicing\\arbiter\\cactionlistcreator.cpp",
          (const char *)0x8007000ELL,
          (int)bIgnoreCase);
        v84 = -2147024882;
        goto LABEL_292;
      }
      LogAdapter::TraceInfo<AutoScz>("  Cix file found: {0}", &v158);
    }
LABEL_89:
    v40 += 92;
    FirstFileW = v40;
    if ( v40 == v141 )
      goto LABEL_90;
  }
  v156 = Directory;
  if ( *(_QWORD *)&LogAdapter::g_Logger )
  {
    LogAdapter::Logger::LogNumObjects<>(*(_QWORD *)&LogAdapter::g_Logger, 0, 3, "Failed to allocate memory");
    *(_QWORD *)v131 = &v156;
    bIgnoreCase = v131;
    LOBYTE(v125) = 1;
    LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
      *(_QWORD *)&LogAdapter::g_Logger,
      v125,
      3,
      ": {}");
  }
  v103 = 4477;
LABEL_330:
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)v103,
    (unsigned int)"onecore\\base\\servicing\\arbiter\\cactionlistcreator.cpp",
    (const char *)(unsigned int)Directory,
    (int)bIgnoreCase);
LABEL_331:
  std::vector<std::wstring>::_Tidy(&v168);
  std::_Tree<std::_Tset_traits<std::wstring,WstringCaseInsensitiveCompare,std::allocator<std::wstring>,0>>::~_Tree<std::_Tset_traits<std::wstring,WstringCaseInsensitiveCompare,std::allocator<std::wstring>,0>>(&v161);
  std::wstring::~wstring(&v163);
  CIUClient::~CIUClient((CIUClient *)&v134);
  if ( v9 )
    operator delete(v9 - 4);
  if ( v8 )
    operator delete((void *)(v8 - 8));
  if ( v158 )
  {
    operator delete(v158 - 4);
    v158 = 0;
  }
  if ( v7 )
    operator delete((void *)(v7 - 8));
  if ( v157 )
  {
LABEL_10:
    operator delete(v157 - 4);
    v157 = 0;
  }
LABEL_11:
  if ( v159 )
    operator delete(v159 - 4);
  return (unsigned int)Directory;
}

```

## disassembly

```asm
0x1800a2fcc  mov     rax, rsp
0x1800a2fcf  push    rbp
0x1800a2fd0  push    rbx
0x1800a2fd1  push    rsi
0x1800a2fd2  push    rdi
0x1800a2fd3  push    r12
0x1800a2fd5  push    r13
0x1800a2fd7  push    r14
0x1800a2fd9  push    r15
0x1800a2fdb  lea     rbp, [rax-3A8h]
0x1800a2fe2  sub     rsp, 468h
0x1800a2fe9  mov     [rbp+3A0h+var_358], 0FFFFFFFFFFFFFFFEh
0x1800a2ff1  movaps  xmmword ptr [rax-58h], xmm6
0x1800a2ff5  mov     rax, cs:__security_cookie
0x1800a2ffc  xor     rax, rsp
0x1800a2fff  mov     [rbp+3A0h+var_60], rax
0x1800a3006  mov     r12, r8
0x1800a3009  mov     [rbp+3A0h+var_3E0], rdx
0x1800a300d  mov     r14, rcx
0x1800a3010  mov     [rsp+4A0h+var_450], rcx
0x1800a3015  mov     [rbp+3A0h+lpExistingFileName], r9
0x1800a3019  mov     r13, [rbp+3A0h+arg_20]
0x1800a3020  mov     [rbp+3A0h+var_418], r13
0x1800a3024  xor     ecx, ecx
0x1800a3026  mov     [rbp+3A0h+var_328], ecx
0x1800a3029  mov     [rbp+3A0h+var_330], rcx
0x1800a302d  mov     [rbp+3A0h+var_340], rcx
0x1800a3031  mov     ebx, ecx
0x1800a3033  mov     [rsp+4A0h+var_440], rcx
0x1800a3038  mov     [rbp+3A0h+var_338], rcx
0x1800a303c  mov     edi, ecx
0x1800a303e  mov     [rsp+4A0h+var_448], rcx
0x1800a3043  mov     r15d, ecx
0x1800a3046  mov     [rsp+4A0h+Str], rcx
0x1800a304b  mov     esi, ecx
0x1800a304d  mov     [rsp+4A0h+var_458], rcx
0x1800a3052  xorps   xmm0, xmm0
0x1800a3055  movups  [rbp+3A0h+var_310], xmm0
0x1800a305c  mov     [rbp+3A0h+var_300], rcx
0x1800a3063  mov     [rbp+3A0h+var_2F8], 7
0x1800a306e  mov     word ptr [rbp+3A0h+var_310], cx
0x1800a3075  mov     rax, [rdx]
0x1800a3078  cmp     [r14], rcx
0x1800a307b  jz      short loc_1800A307E
0x1800a307d  int     3; Trap to Debugger
0x1800a307e  mov     [r14], rax
0x1800a3081  mov     [rdx], rcx
0x1800a3084  lea     rcx, aArbiterExpress; "arbiter: Express download resumed"
0x1800a308b  call    ??$TraceInfo@$$V@LogAdapter@@YAXQEBD@Z; LogAdapter::TraceInfo<>(char const * const)
0x1800a3090  mov     rdx, r12
0x1800a3093  lea     rcx, [rbp+3A0h+var_330]
0x1800a3097  call    SczAllocFromSz
0x1800a309c  mov     r12d, eax
0x1800a309f  test    eax, eax
0x1800a30a1  jns     loc_1800A3168
0x1800a30a7  mov     [rbp+3A0h+var_328], eax
0x1800a30aa  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1800a30b1  xor     r13d, r13d
0x1800a30b4  test    rcx, rcx
0x1800a30b7  jz      short loc_1800A30F9
0x1800a30b9  lea     r9, aFailedToAlloca; "Failed to allocate memory"
0x1800a30c0  lea     r14d, [r13+3]
0x1800a30c4  mov     r8d, r14d
0x1800a30c7  xor     edx, edx
0x1800a30c9  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x1800a30ce  lea     rax, [rbp+3A0h+var_328]
0x1800a30d2  mov     [rsp+4A0h+var_468], rax
0x1800a30d7  lea     rax, [rsp+4A0h+var_468]
0x1800a30dc  mov     qword ptr [rsp+4A0h+bIgnoreCase], rax; int
0x1800a30e1  lea     r9, asc_1801CAFB4; ": {}"
0x1800a30e8  mov     r8d, r14d
0x1800a30eb  mov     dl, 1
0x1800a30ed  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1800a30f4  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x1800a30f9  mov     edx, 111Eh; void *
0x1800a30fe  mov     r9d, r12d; char *
0x1800a3101  lea     r8, aOnecoreBaseSer_9; "onecore\\base\\servicing\\arbiter\\cact"...
0x1800a3108  mov     rcx, [rbp+3A8h]; this
0x1800a310f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800a3114  nop
0x1800a3115  lea     rcx, [rbp+3A0h+var_310]; void *
0x1800a311c  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800a3121  nop
0x1800a3122  mov     rcx, [rbp+3A0h+var_338]
0x1800a3126  test    rcx, rcx
0x1800a3129  jz      short loc_1800A3138
0x1800a312b  add     rcx, 0FFFFFFFFFFFFFFF8h; Block
0x1800a312f  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1800a3134  mov     [rbp+3A0h+var_338], r13
0x1800a3138  mov     rcx, [rbp+3A0h+var_340]
0x1800a313c  test    rcx, rcx
0x1800a313f  jz      short loc_1800A314E
0x1800a3141  add     rcx, 0FFFFFFFFFFFFFFF8h; Block
0x1800a3145  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1800a314a  mov     [rbp+3A0h+var_340], r13
0x1800a314e  mov     rcx, [rbp+3A0h+var_330]
0x1800a3152  test    rcx, rcx
0x1800a3155  jz      short loc_1800A3160
0x1800a3157  add     rcx, 0FFFFFFFFFFFFFFF8h; Block
0x1800a315b  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1800a3160  mov     eax, r12d
0x1800a3163  jmp     loc_1800A4FD8
0x1800a3168  lea     rcx, [rbp+3A0h+var_330]
0x1800a316c  call    SczEnsureBackslashTerminated
0x1800a3171  mov     r12d, eax
0x1800a3174  test    eax, eax
0x1800a3176  jns     short loc_1800A31D4
0x1800a3178  mov     [rbp+3A0h+var_328], eax
0x1800a317b  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1800a3182  xor     r13d, r13d
0x1800a3185  test    rcx, rcx
0x1800a3188  jz      short loc_1800A31CA
0x1800a318a  lea     r9, aFailedToAlloca; "Failed to allocate memory"
0x1800a3191  lea     r14d, [r13+3]
0x1800a3195  mov     r8d, r14d
0x1800a3198  xor     edx, edx
0x1800a319a  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x1800a319f  lea     rax, [rbp+3A0h+var_328]
0x1800a31a3  mov     [rsp+4A0h+var_468], rax
0x1800a31a8  lea     rax, [rsp+4A0h+var_468]
0x1800a31ad  mov     qword ptr [rsp+4A0h+bIgnoreCase], rax
0x1800a31b2  lea     r9, asc_1801CAFB4; ": {}"
0x1800a31b9  mov     r8d, r14d
0x1800a31bc  mov     dl, 1
0x1800a31be  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1800a31c5  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x1800a31ca  mov     edx, 1120h
0x1800a31cf  jmp     loc_1800A30FE
0x1800a31d4  mov     rdx, [rbp+3A0h+var_330]
0x1800a31d8  lea     rcx, [rbp+3A0h+var_340]
0x1800a31dc  call    SczAllocFromSz
0x1800a31e1  mov     r12d, eax
0x1800a31e4  xor     edx, edx
0x1800a31e6  test    eax, eax
0x1800a31e8  jns     short loc_1800A3244
0x1800a31ea  mov     [rbp+3A0h+var_328], eax
0x1800a31ed  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1800a31f4  xor     r13d, r13d
0x1800a31f7  test    rcx, rcx
0x1800a31fa  jz      short loc_1800A323A
0x1800a31fc  lea     r9, aFailedToAlloca; "Failed to allocate memory"
0x1800a3203  lea     r14d, [rdx+3]
0x1800a3207  mov     r8d, r14d
0x1800a320a  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x1800a320f  lea     rax, [rbp+3A0h+var_328]
0x1800a3213  mov     [rsp+4A0h+var_468], rax
0x1800a3218  lea     rax, [rsp+4A0h+var_468]
0x1800a321d  mov     qword ptr [rsp+4A0h+bIgnoreCase], rax
0x1800a3222  lea     r9, asc_1801CAFB4; ": {}"
0x1800a3229  mov     r8d, r14d
0x1800a322c  mov     dl, 1
0x1800a322e  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1800a3235  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x1800a323a  mov     edx, 1122h
0x1800a323f  jmp     loc_1800A30FE
0x1800a3244  mov     rax, [rbp+3A0h+var_330]
0x1800a3248  or      rcx, 0FFFFFFFFFFFFFFFFh
0x1800a324c  inc     rcx
0x1800a324f  cmp     [rax+rcx*2], dx
0x1800a3253  jnz     short loc_1800A324C
0x1800a3255  mov     [rsp+4A0h+var_438], rcx
0x1800a325a  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_ArbiterMetadataContainer@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_ArbiterMetadataContainer@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ArbiterMetadataContainer> `wil::Feature<__WilFeatureTraits_Feature_ArbiterMetadataContainer>::GetImpl(void)'::`2'::impl
0x1800a3261  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_ArbiterMetadataContainer@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ArbiterMetadataContainer>::__private_IsEnabled(void)
0x1800a3266  xor     r9d, r9d
0x1800a3269  test    al, al
0x1800a326b  jz      loc_1800A335F
0x1800a3271  mov     rcx, [r14]
0x1800a3274  mov     ecx, [rcx+34h]
0x1800a3277  call    IsMetadataContainerSupported
0x1800a327c  xor     r9d, r9d
0x1800a327f  test    al, al
0x1800a3281  jz      loc_1800A335F
0x1800a3287  mov     rax, [r14]
0x1800a328a  mov     r13, [rax+188h]
0x1800a3291  imul    r12, [rax+178h], 0A8h
0x1800a329c  add     r12, r13
0x1800a329f  jmp     loc_1800A3352
0x1800a32a4  cmp     [r13+78h], r9d
0x1800a32a8  jbe     loc_1800A334B
0x1800a32ae  mov     r14, [r13+70h]
0x1800a32b2  mov     rdx, r9
0x1800a32b5  mov     eax, [r13+78h]
0x1800a32b9  imul    rax, 0B8h
0x1800a32c0  add     rax, r14
0x1800a32c3  mov     [rsp+4A0h+var_468], rax
0x1800a32c8  cmp     r14, rax
0x1800a32cb  jz      short loc_1800A3346
0x1800a32cd  cmp     dword ptr [r14+8], 2
0x1800a32d2  jnz     short loc_1800A330A
0x1800a32d4  cmp     [r14+18h], r9
0x1800a32d8  jz      short loc_1800A330A
0x1800a32da  mov     rax, [rsp+4A0h+var_450]
0x1800a32df  mov     rcx, [rax]
0x1800a32e2  add     rcx, 108h; struct Windows::Rtl::IPoolAllocator *
0x1800a32e9  mov     rdx, [r14+18h]; wchar_t *
0x1800a32ed  call    ?DuplicateNullTerminatedString@@YAPEA_WAEAVIPoolAllocator@Rtl@Windows@@PEB_W@Z; DuplicateNullTerminatedString(Windows::Rtl::IPoolAllocator &,wchar_t const *)
0x1800a32f2  mov     [r14+68h], rax
0x1800a32f6  xor     r9d, r9d
0x1800a32f9  test    rax, rax
0x1800a32fc  jz      loc_1800A3398
0x1800a3302  mov     rdx, r14
0x1800a3305  mov     rax, [rsp+4A0h+var_468]
0x1800a330a  add     r14, 0B8h
0x1800a3311  cmp     r14, rax
0x1800a3314  jnz     short loc_1800A32CD
0x1800a3316  mov     r14, [rsp+4A0h+var_450]
0x1800a331b  test    rdx, rdx
0x1800a331e  jz      short loc_1800A334B
0x1800a3320  mov     rcx, [r14]
0x1800a3323  add     rcx, 108h; struct Windows::Rtl::IPoolAllocator *
0x1800a332a  mov     rdx, [rdx+68h]; wchar_t *
0x1800a332e  call    ?DuplicateNullTerminatedString@@YAPEA_WAEAVIPoolAllocator@Rtl@Windows@@PEB_W@Z; DuplicateNullTerminatedString(Windows::Rtl::IPoolAllocator &,wchar_t const *)
0x1800a3333  mov     [r13+50h], rax
0x1800a3337  xor     r9d, r9d
0x1800a333a  test    rax, rax
0x1800a333d  jnz     short loc_1800A334B
0x1800a333f  mov     edx, 1146h
0x1800a3344  jmp     short loc_1800A339D
0x1800a3346  mov     r14, [rsp+4A0h+var_450]
0x1800a334b  add     r13, 0A8h
0x1800a3352  cmp     r13, r12
0x1800a3355  jnz     loc_1800A32A4
0x1800a335b  mov     r13, [rbp+3A0h+var_418]
0x1800a335f  mov     byte ptr [rsp+4A0h+var_460], r9b
0x1800a3364  mov     rcx, [r14]
0x1800a3367  mov     eax, [rcx+34h]
0x1800a336a  mov     edx, 44C004h
0x1800a336f  cmp     eax, 16h
0x1800a3372  ja      loc_1800A3414
0x1800a3378  bt      edx, eax
0x1800a337b  jnb     loc_1800A3414
0x1800a3381  mov     rax, [rcx+188h]
0x1800a3388  imul    rdx, [rcx+178h], 0A8h
0x1800a3393  add     rdx, rax
0x1800a3396  jmp     short loc_1800A3408
0x1800a3398  mov     edx, 113Eh; void *
0x1800a339d  mov     r9d, 8007000Eh; char *
0x1800a33a3  lea     r8, aOnecoreBaseSer_9; "onecore\\base\\servicing\\arbiter\\cact"...
0x1800a33aa  mov     rcx, [rbp+3A8h]; this
0x1800a33b1  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800a33b6  nop
0x1800a33b7  lea     rcx, [rbp+3A0h+var_310]; void *
0x1800a33be  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800a33c3  nop
0x1800a33c4  xor     r14d, r14d
0x1800a33c7  mov     rcx, [rbp+3A0h+var_338]
0x1800a33cb  test    rcx, rcx
0x1800a33ce  jz      short loc_1800A33DD
0x1800a33d0  add     rcx, 0FFFFFFFFFFFFFFF8h; Block
0x1800a33d4  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1800a33d9  mov     [rbp+3A0h+var_338], r14
0x1800a33dd  mov     rcx, [rbp+3A0h+var_340]
0x1800a33e1  test    rcx, rcx
0x1800a33e4  jz      loc_1800A4694
0x1800a33ea  add     rcx, 0FFFFFFFFFFFFFFF8h; Block
0x1800a33ee  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1800a33f3  mov     [rbp+3A0h+var_340], r14
0x1800a33f7  jmp     loc_1800A4694
0x1800a33fc  cmp     dword ptr [rax+60h], 4
0x1800a3400  jz      short loc_1800A340F
0x1800a3402  add     rax, 0A8h
0x1800a3408  cmp     rax, rdx
0x1800a340b  jnz     short loc_1800A33FC
0x1800a340d  jmp     short loc_1800A3414
0x1800a340f  mov     byte ptr [rsp+4A0h+var_460], 1
0x1800a3414  mov     r12, [rcx+148h]
0x1800a341b  mov     [rsp+4A0h+var_428], r12
0x1800a3420  imul    rax, [rcx+138h], 0A8h
0x1800a342b  add     rax, r12
0x1800a342e  mov     qword ptr [rsp+4A0h+var_470], rax
0x1800a3433  cmp     r12, rax
0x1800a3436  jz      loc_1800A4E7B
0x1800a343c  cmp     dword ptr [r12+68h], 2
0x1800a3442  jnz     loc_1800A3F00
0x1800a3448  mov     rcx, [r14]
0x1800a344b  cmp     dword ptr [rcx+34h], 8
0x1800a344f  jnz     loc_1800A3530
0x1800a3455  add     rcx, 108h; struct Windows::Rtl::IPoolAllocator *
0x1800a345c  mov     rdx, r13; wchar_t *
0x1800a345f  call    ?DuplicateNullTerminatedString@@YAPEA_WAEAVIPoolAllocator@Rtl@Windows@@PEB_W@Z; DuplicateNullTerminatedString(Windows::Rtl::IPoolAllocator &,wchar_t const *)
0x1800a3464  mov     [r12+80h], rax
0x1800a346c  xor     r13d, r13d
0x1800a346f  test    rax, rax
0x1800a3472  jnz     loc_1800A3533
0x1800a3478  mov     rcx, [rbp+3A8h]; this
0x1800a347f  mov     r9d, 8007000Eh; char *
0x1800a3485  lea     r8, aOnecoreBaseSer_9; "onecore\\base\\servicing\\arbiter\\cact"...
0x1800a348c  mov     edx, 1168h; void *
0x1800a3491  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800a3496  nop
0x1800a3497  lea     rcx, [rbp+3A0h+var_310]; void *
0x1800a349e  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800a34a3  nop
0x1800a34a4  test    rsi, rsi
0x1800a34a7  jz      short loc_1800A34CE
0x1800a34a9  mov     rcx, rsi; hLibModule
0x1800a34ac  call    cs:__imp_FreeLibrary
0x1800a34b3  nop     dword ptr [rax+rax+00h]
0x1800a34b8  test    eax, eax
0x1800a34ba  jnz     short loc_1800A34CE
  ... truncated ...
```
