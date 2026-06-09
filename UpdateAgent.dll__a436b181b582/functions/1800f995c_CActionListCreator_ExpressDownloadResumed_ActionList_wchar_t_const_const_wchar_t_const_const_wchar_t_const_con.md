# CActionListCreator::ExpressDownloadResumed(ActionList * *,wchar_t const * const,wchar_t const * const,wchar_t const * const)

- ea: `0x1800f995c`
- end: `0x1800fb7f8`
- name: `?ExpressDownloadResumed@CActionListCreator@@QEAAJPEAPEAUActionList@@QEB_W11@Z`
- size: `7836`
- prototype: `__int64 __fastcall(CActionListCreator *__hidden this, struct ActionList **, const wchar_t *const, const wchar_t *const, const wchar_t *const)`
- caller_count: `1`
- callee_count: `54`
- tags: `file_ops, registry_config, loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x1800c02fc`

## callees

- `0x1800059d0`
- `0x1800059f4`
- `0x180005cf0`
- `0x180006a18`
- `0x180007ccc`
- `0x18000a0e8`
- `0x18000b508`
- `0x18000c4c4`
- `0x18001270c`
- `0x180012770`
- `0x1800127a4`
- `0x1800127dc`
- `0x180012a30`
- `0x180012b84`
- `0x180012d94`
- `0x180016014`
- `0x1800192f8`
- `0x18001f05c`
- `0x180020324`
- `0x18002297c`
- `0x18002374c`
- `0x180023b20`
- `0x1800255c8`
- `0x18008b38c`
- `0x18008b3ec`
- `0x18009af9c`
- `0x18009b848`
- `0x18009b860`
- `0x18009d254`
- `0x18009f060`
- `0x1800a76dc`
- `0x1800bde88`
- `0x1800c96d8`
- `0x1800f5b10`
- `0x1800f5f10`
- `0x1800f6ae0`
- `0x1800f6cc4`
- `0x1800f995c`
- `0x1800fedf4`
- `0x1800fee9c`
- `0x18010039c`
- `0x18010dae8`
- `0x1801488f0`
- `0x180149180`
- `0x180149300`
- `0x18014a56c`
- `0x18014a96c`
- `0x18014b0c8`
- `0x18014bd44`
- `0x1801507cc`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!wcsrchr` at `0x1800f9f3d`
- `api-ms-win-crt-private-l1-1-0!wcsrchr` at `0x1800f9f3d`
- `api-ms-win-core-file-l1-1-0!FindFirstFileW` at `0x1800fa648`
- `api-ms-win-core-file-l1-1-0!FindFirstFileW` at `0x1800fa648`
- `api-ms-win-core-libraryloader-l1-1-0!FreeLibrary` at `0x1800f9e3d`
- `api-ms-win-core-libraryloader-l1-1-0!FreeLibrary` at `0x1800fb5ca`
- `api-ms-win-core-libraryloader-l1-1-0!FreeLibrary` at `0x1800f9e3d`
- `api-ms-win-core-libraryloader-l1-1-0!FreeLibrary` at `0x1800fb5ca`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1800fa0cb`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1800fa0cb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800f9e4d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800fab32`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800faf43`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800fb5da`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800f9e4d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800fab32`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800faf43`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800fb5da`
- `api-ms-win-core-kernel32-legacy-l1-1-0!CopyFileW` at `0x1800fa479`
- `api-ms-win-core-kernel32-legacy-l1-1-0!CopyFileW` at `0x1800fa479`

## string_xrefs

- `0x1800fa427`: `ActionList.xml`
- `0x1800fa8ae`: `Failed to load dpx.dll`
- `0x1800face1`: `Failed creating directory {0}`
- `0x1800f9f70`: `express.psf.cix.xml`
- `0x1800f9ff9`: `express.psf.cix.xml`
- `0x1800fa2ab`: `express.psf.cix.xml`
- `0x1800fad46`: `Unable to delete directory {0}`
- `0x1800fa344`: `Failed to extract cab file: {0} in directory {1}. Trying to extract WIM`
- `0x1800fab4c`: `Failed to copy ActionList to metadata folder.`
- `0x1800fa51b`: `%ws.cix.xml`
- `0x1800faae6`: `ExpressPackageTargetDirectory already set`
- `0x1800faf68`: `Failed to find a CiX file in directory: {0}`
- `0x1800fa622`: `\*.cix.xml`
- `0x1800fa735`: `Arbiter : Copying metadata contents from: {0} to {1}`

## pseudocode

```c
// Hidden C++ exception states: #wind=21
__int64 __fastcall CActionListCreator::ExpressDownloadResumed(
        CActionListCreator *this,
        struct ActionList **a2,
        const wchar_t *a3,
        const WCHAR *a4,
        wchar_t *a5)
{
  CActionListCreator *v6; // r14
  const wchar_t *v7; // r13
  __int64 v8; // rbx
  __int64 v9; // rdi
  wchar_t *v10; // r15
  HINSTANCE v11; // rsi
  int v12; // eax
  int Directory; // r12d
  __int64 v14; // rdx
  __int64 v15; // rdx
  const struct std::nothrow_t *v16; // rdx
  int v18; // eax
  __int64 v19; // rdx
  int v20; // eax
  __int64 v21; // rdx
  __int64 v22; // rcx
  __int64 v23; // rdx
  __int64 v24; // r8
  __int64 v25; // r13
  __int64 v26; // r12
  __int64 v27; // r14
  __int64 v28; // rdx
  __int64 v29; // rax
  wchar_t *v30; // rax
  wchar_t *v31; // rax
  __int64 v32; // rdx
  _QWORD *v33; // rcx
  unsigned int v34; // eax
  int v35; // edx
  __int64 v36; // rax
  __int64 v37; // rdx
  __int64 v38; // r12
  __int64 v39; // rax
  wchar_t *v40; // rax
  _QWORD *v41; // rax
  __int64 v42; // r13
  int v43; // r15d
  wchar_t *v44; // rax
  wchar_t **v45; // r12
  const struct std::nothrow_t *v46; // rdx
  struct Windows::Rtl::IPoolAllocator *v47; // rcx
  __int64 v48; // r14
  wchar_t *v49; // rax
  const struct std::nothrow_t *v50; // rdx
  WCHAR *v51; // rcx
  struct ActionList *v52; // rax
  __int64 v53; // r14
  __int64 v54; // r12
  __int64 v55; // r13
  __int64 v56; // rax
  _QWORD *v57; // r12
  __int64 v58; // r8
  __int64 v59; // rax
  __int64 v60; // rax
  __int128 v61; // xmm6
  __int64 v62; // rcx
  __int64 v63; // rcx
  __int64 v64; // rdx
  int v65; // esi
  __int64 v66; // rdx
  __int64 v67; // r8
  __int64 v68; // r9
  struct Windows::Rtl::IPoolAllocator *v69; // rcx
  __int64 v70; // r14
  wchar_t *v71; // rax
  int CabFile; // eax
  __int64 v73; // rdx
  __int64 v74; // rcx
  __int64 v75; // rdx
  unsigned int v76; // r8d
  int v77; // eax
  __int64 v78; // rax
  unsigned int v79; // r8d
  __int64 v80; // rax
  int v81; // edx
  int v82; // r8d
  int v83; // r9d
  __int64 v84; // rax
  _OWORD *Path; // rax
  BOOL v86; // r14d
  __int64 v87; // r8
  int v88; // ebx
  __int64 v89; // rdx
  int v90; // edi
  wchar_t *v91; // rax
  wchar_t *v92; // rax
  __int64 v93; // r12
  __int64 v94; // r14
  const struct std::nothrow_t *v95; // rdx
  void *v96; // rcx
  __int64 v97; // rdx
  __int64 v98; // rdx
  __int64 v99; // rdx
  const struct std::nothrow_t *v100; // rdx
  const struct std::nothrow_t *v101; // rdx
  void *v102; // rcx
  __int64 v103; // rdx
  __int64 v104; // rdx
  __int64 v105; // rdx
  __int64 v106; // rdx
  signed int LastError; // esi
  __int64 v108; // rdx
  unsigned int v109; // eax
  const struct std::nothrow_t *v110; // rdx
  __int64 v111; // rdx
  __int64 v112; // rdx
  __int64 v113; // rdx
  const struct std::nothrow_t *v114; // rdx
  __int64 v115; // rdx
  __int64 v116; // rdx
  __int64 v117; // rdx
  __int64 v118; // rdx
  signed int v119; // ebx
  __int64 v120; // rdx
  unsigned int v121; // eax
  __int64 v122; // rdx
  __int64 v123; // rdx
  __int64 v124; // rdx
  __int64 v125; // rdx
  __int64 v126; // rdx
  const struct std::nothrow_t *v127; // rdx
  __int64 v128; // rdx
  const struct std::nothrow_t *v129; // rdx
  __int64 v130; // rdx
  __int64 v131; // rdx
  __int64 v132; // rdx
  const struct std::nothrow_t *v133; // rdx
  int v134; // eax
  __int64 v135; // rdx
  struct ActionList *v136; // rax
  unsigned int *bIgnoreCase; // [rsp+28h] [rbp-E0h]
  unsigned int v138[2]; // [rsp+38h] [rbp-D0h] BYREF
  HINSTANCE v139; // [rsp+40h] [rbp-C8h] BYREF
  __int64 v140; // [rsp+48h] [rbp-C0h]
  __int64 v141; // [rsp+50h] [rbp-B8h] BYREF
  __int64 v142; // [rsp+58h] [rbp-B0h] BYREF
  CActionListCreator *v143; // [rsp+60h] [rbp-A8h]
  wchar_t *Str; // [rsp+68h] [rbp-A0h] BYREF
  _QWORD v145[5]; // [rsp+70h] [rbp-98h] BYREF
  __int64 v146; // [rsp+98h] [rbp-70h]
  __int64 v147; // [rsp+A0h] [rbp-68h]
  _OWORD v148[2]; // [rsp+A8h] [rbp-60h] BYREF
  __int64 v149; // [rsp+C8h] [rbp-40h]
  struct ActionList **v150; // [rsp+D0h] [rbp-38h]
  _QWORD *v151; // [rsp+D8h] [rbp-30h]
  __int64 v152; // [rsp+E0h] [rbp-28h]
  _QWORD v153[2]; // [rsp+E8h] [rbp-20h] BYREF
  _QWORD v154[2]; // [rsp+F8h] [rbp-10h] BYREF
  int v155[4]; // [rsp+108h] [rbp+0h] BYREF
  __int64 v156; // [rsp+118h] [rbp+10h]
  __int64 v157; // [rsp+120h] [rbp+18h]
  _BYTE v158[32]; // [rsp+128h] [rbp+20h] BYREF
  LPCWSTR lpExistingFileName; // [rsp+148h] [rbp+40h] BYREF
  int v160; // [rsp+150h] [rbp+48h] BYREF
  wchar_t *v161; // [rsp+158h] [rbp+50h] BYREF
  wchar_t *v162; // [rsp+160h] [rbp+58h] BYREF
  wchar_t *v163; // [rsp+168h] [rbp+60h] BYREF
  LPCWSTR lpFileName; // [rsp+170h] [rbp+68h] BYREF
  _QWORD *v165; // [rsp+178h] [rbp+70h] BYREF
  __int64 v166; // [rsp+180h] [rbp+78h]
  __int128 v167; // [rsp+188h] [rbp+80h] BYREF
  __int64 v168; // [rsp+198h] [rbp+90h]
  __int64 v169; // [rsp+1A0h] [rbp+98h]
  __int128 v170; // [rsp+1A8h] [rbp+A0h] BYREF
  __int64 v171; // [rsp+1B8h] [rbp+B0h]
  struct _WIN32_FIND_DATAW FindFileData; // [rsp+1C8h] [rbp+C0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+480h] [rbp+378h]

  v157 = -2;
  v150 = a2;
  v6 = this;
  v143 = this;
  lpExistingFileName = a4;
  v7 = a5;
  v145[0] = a5;
  v163 = 0;
  v161 = 0;
  v8 = 0;
  v142 = 0;
  v162 = 0;
  v9 = 0;
  v141 = 0;
  v10 = 0;
  Str = 0;
  v11 = 0;
  v139 = 0;
  v167 = 0;
  v168 = 0;
  v169 = 7;
  LOWORD(v167) = 0;
  if ( *(_QWORD *)this )
    __debugbreak();
  *(_QWORD *)this = *a2;
  *a2 = 0;
  LogAdapter::TraceInfo<>("arbiter: Express download resumed");
  v12 = SczAllocFromSz(&v163, a3);
  Directory = v12;
  if ( v12 < 0 )
  {
    v160 = v12;
    if ( *(_QWORD *)&LogAdapter::g_Logger )
    {
      LogAdapter::Logger::LogNumObjects<>(*(_QWORD *)&LogAdapter::g_Logger, 0, 3, "Failed to allocate memory");
      v145[0] = &v160;
      bIgnoreCase = (unsigned int *)v145;
      LOBYTE(v14) = 1;
      LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
        *(_QWORD *)&LogAdapter::g_Logger,
        v14,
        3,
        ": {}");
    }
    v15 = 4382;
LABEL_7:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v15,
      (unsigned int)"onecore\\base\\servicing\\arbiter\\cactionlistcreator.cpp",
      (const char *)(unsigned int)Directory,
      (int)bIgnoreCase);
    std::wstring::~wstring(&v167);
    if ( v162 )
    {
      operator delete(v162 - 4, v16);
      v162 = 0;
    }
LABEL_9:
    if ( v161 )
    {
      operator delete(v161 - 4, v16);
      v161 = 0;
    }
    goto LABEL_11;
  }
  v18 = SczEnsureBackslashTerminated(&v163);
  Directory = v18;
  if ( v18 < 0 )
  {
    v160 = v18;
    if ( *(_QWORD *)&LogAdapter::g_Logger )
    {
      LogAdapter::Logger::LogNumObjects<>(*(_QWORD *)&LogAdapter::g_Logger, 0, 3, "Failed to allocate memory");
      v145[0] = &v160;
      bIgnoreCase = (unsigned int *)v145;
      LOBYTE(v19) = 1;
      LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
        *(_QWORD *)&LogAdapter::g_Logger,
        v19,
        3,
        ": {}");
    }
    v15 = 4384;
    goto LABEL_7;
  }
  v20 = SczAllocFromSz(&v161, v163);
  Directory = v20;
  if ( v20 < 0 )
  {
    v160 = v20;
    if ( *(_QWORD *)&LogAdapter::g_Logger )
    {
      LogAdapter::Logger::LogNumObjects<>(*(_QWORD *)&LogAdapter::g_Logger, 0, 3, "Failed to allocate memory");
      v145[0] = &v160;
      bIgnoreCase = (unsigned int *)v145;
      LOBYTE(v21) = 1;
      LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
        *(_QWORD *)&LogAdapter::g_Logger,
        v21,
        3,
        ": {}");
    }
    v15 = 4386;
    goto LABEL_7;
  }
  v22 = -1;
  do
    ++v22;
  while ( v163[v22] );
  v146 = v22;
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_ArbiterMetadataContainer>::__private_IsEnabled(
                          &`wil::Feature<__WilFeatureTraits_Feature_ArbiterMetadataContainer>::GetImpl'::`2'::impl,
                          0)
    && (unsigned __int8)IsMetadataContainerSupported(*(unsigned int *)(*(_QWORD *)v6 + 52LL), v23, v24, 0) )
  {
    v25 = *(_QWORD *)(*(_QWORD *)v6 + 392LL);
    v26 = v25 + 168LL * *(_QWORD *)(*(_QWORD *)v6 + 376LL);
    while ( v25 != v26 )
    {
      if ( *(_DWORD *)(v25 + 120) )
      {
        v27 = *(_QWORD *)(v25 + 112);
        v28 = 0;
        v29 = v27 + 184LL * *(unsigned int *)(v25 + 120);
        v147 = v29;
        if ( v27 == v29 )
        {
          v6 = v143;
        }
        else
        {
          do
          {
            if ( *(_DWORD *)(v27 + 8) == 2 && *(_QWORD *)(v27 + 24) )
            {
              v30 = DuplicateNullTerminatedString(
                      (struct Windows::Rtl::IPoolAllocator *)(*(_QWORD *)v143 + 264LL),
                      *(const wchar_t **)(v27 + 24));
              *(_QWORD *)(v27 + 104) = v30;
              if ( !v30 )
              {
                v32 = 4414;
                goto LABEL_45;
              }
              v28 = v27;
              v29 = v147;
            }
            v27 += 184;
          }
          while ( v27 != v29 );
          v6 = v143;
          if ( v28 )
          {
            v31 = DuplicateNullTerminatedString(
                    (struct Windows::Rtl::IPoolAllocator *)(*(_QWORD *)v143 + 264LL),
                    *(const wchar_t **)(v28 + 104));
            *(_QWORD *)(v25 + 80) = v31;
            if ( !v31 )
            {
              v32 = 4422;
LABEL_45:
              Directory = -2147024882;
              wil::details::in1diag3::Return_Hr(
                retaddr,
                (void *)v32,
                (unsigned int)"onecore\\base\\servicing\\arbiter\\cactionlistcreator.cpp",
                (const char *)0x8007000ELL,
                (int)bIgnoreCase);
              std::wstring::~wstring(&v167);
              if ( v162 )
              {
                operator delete(v162 - 4, v16);
                v162 = 0;
              }
              if ( v161 )
              {
                operator delete(v161 - 4, v16);
                v161 = 0;
              }
              goto LABEL_11;
            }
          }
        }
      }
      v25 += 168;
    }
    v7 = (const wchar_t *)v145[0];
  }
  LOBYTE(v140) = 0;
  v33 = *(_QWORD **)v6;
  v34 = *(_DWORD *)(*(_QWORD *)v6 + 52LL);
  v35 = 4505604;
  if ( v34 <= 0x16 && _bittest(&v35, v34) )
  {
    v36 = v33[49];
    v37 = v36 + 168LL * v33[47];
    while ( v36 != v37 )
    {
      if ( *(_DWORD *)(v36 + 96) == 4 )
      {
        LOBYTE(v140) = 1;
        break;
      }
      v36 += 168;
    }
  }
  v38 = v33[41];
  v147 = v38;
  v39 = v38 + 168LL * v33[39];
  *(_QWORD *)v138 = v39;
  if ( v38 == v39 )
  {
LABEL_336:
    if ( lpExistingFileName )
    {
      v134 = CActionListCreator::Save((__int64)v6, 1, lpExistingFileName);
      Directory = v134;
      if ( v134 < 0 )
      {
        v160 = v134;
        if ( *(_QWORD *)&LogAdapter::g_Logger )
        {
          LogAdapter::Logger::LogNumObjects<Windows::AutoGenericHandle<wchar_t *,0,&void Windows::Detail::CloseWithCoTaskMemFree<wchar_t>(wchar_t *)>>(
            *(_QWORD *)&LogAdapter::g_Logger,
            0,
            3,
            "Failed to save to actionlist file: {0}",
            &lpExistingFileName);
          *(_QWORD *)v138 = &v160;
          bIgnoreCase = v138;
          LOBYTE(v135) = 1;
          LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
            *(_QWORD *)&LogAdapter::g_Logger,
            v135,
            3,
            ": {}");
        }
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x1285,
          (unsigned int)"onecore\\base\\servicing\\arbiter\\cactionlistcreator.cpp",
          (const char *)(unsigned int)Directory,
          (int)bIgnoreCase);
LABEL_341:
        std::wstring::~wstring(&v167);
        CIUClient::~CIUClient((CIUClient *)&v139);
        AutoScz::~AutoScz((AutoScz *)&Str);
        AutoScz::~AutoScz((AutoScz *)&v141);
        AutoScz::~AutoScz((AutoScz *)&v162);
        AutoScz::~AutoScz((AutoScz *)&v142);
        AutoScz::~AutoScz((AutoScz *)&v161);
        goto LABEL_342;
      }
    }
    v136 = *(struct ActionList **)v6;
    *(_QWORD *)v6 = 0;
    *v150 = v136;
    std::wstring::~wstring(&v167);
    CIUClient::~CIUClient((CIUClient *)&v139);
    AutoScz::~AutoScz((AutoScz *)&Str);
    AutoScz::~AutoScz((AutoScz *)&v141);
    AutoScz::~AutoScz((AutoScz *)&v162);
    AutoScz::~AutoScz((AutoScz *)&v142);
    AutoScz::~AutoScz((AutoScz *)&v161);
    AutoScz::~AutoScz((AutoScz *)&v163);
    return 0;
  }
  while ( 1 )
  {
    if ( *(_DWORD *)(v38 + 104) != 2 )
      goto LABEL_163;
    if ( *(_DWORD *)(*(_QWORD *)v6 + 52LL) == 8 )
    {
      v40 = DuplicateNullTerminatedString((struct Windows::Rtl::IPoolAllocator *)(*(_QWORD *)v6 + 264LL), v7);
      *(_QWORD *)(v38 + 128) = v40;
      if ( !v40 )
      {
        Directory = -2147024882;
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x1168,
          (unsigned int)"onecore\\base\\servicing\\arbiter\\cactionlistcreator.cpp",
          (const char *)0x8007000ELL,
          (int)bIgnoreCase);
        std::wstring::~wstring(&v167);
        if ( v11 && !FreeLibrary(v11) )
        {
          GetLastError();
          __fastfail(7u);
        }
        if ( v10 )
          operator delete(v10 - 4, v16);
        if ( v9 )
          operator delete((void *)(v9 - 8), v16);
        if ( v162 )
        {
          operator delete(v162 - 4, v16);
          v162 = 0;
        }
        if ( v8 )
          operator delete((void *)(v8 - 8), v16);
        goto LABEL_9;
      }
    }
    v165 = 0;
    v166 = 0;
    v41 = operator new(0x40u);
    *v41 = v41;
    v41[1] = v41;
    v41[2] = v41;
    *((_WORD *)v41 + 12) = 257;
    v165 = v41;
    v170 = 0;
    v171 = 0;
    v42 = *(_QWORD *)(v38 + 112);
    v149 = v42 + 184LL * *(unsigned int *)(v38 + 120);
    if ( v42 != v149 )
      break;
LABEL_88:
    v52 = *(struct ActionList **)v6;
    v53 = *(_QWORD *)(*(_QWORD *)v6 + 712LL);
    v54 = v53 + 24LL * *((_QWORD *)v52 + 87);
    if ( v53 != v54 )
    {
      v55 = v147;
      while ( CompareStringOrdinal(*(LPCWCH *)(v55 + 24), -1, *(LPCWCH *)v53, -1, 1) != 2 )
      {
        v53 += 24;
        if ( v53 == v54 )
          goto LABEL_156;
      }
      *(_DWORD *)(v53 + 16) = 1;
    }
LABEL_156:
    if ( (_BYTE)v140 )
    {
      v93 = *((_QWORD *)&v170 + 1);
      v94 = v170;
      if ( (_QWORD)v170 != *((_QWORD *)&v170 + 1) )
      {
        if ( v168 )
        {
          while ( v94 != v93 )
          {
            LogAdapter::TraceInfo<std::wstring,std::wstring>(
              "Arbiter : Copying metadata contents from: {0} to {1}",
              v94,
              &v167);
            std::filesystem::path::path(v158, &v167);
            std::filesystem::path::path(v148, v94);
            std::filesystem::copy(v148, v158);
            std::wstring::~wstring(v148);
            std::wstring::~wstring(v158);
            v94 += 32;
          }
        }
      }
    }
    std::vector<UUPInstallPlan::UUPProduct>::_Tidy(&v170);
    std::_Tree<std::_Tset_traits<std::wstring,WstringCaseInsensitiveCompare,std::allocator<std::wstring>,0>>::~_Tree<std::_Tset_traits<std::wstring,WstringCaseInsensitiveCompare,std::allocator<std::wstring>,0>>(&v165);
    v6 = v143;
    v38 = v147;
    v39 = *(_QWORD *)v138;
LABEL_163:
    v38 += 168;
    v147 = v38;
    if ( v38 == v39 )
      goto LABEL_336;
    v7 = (const wchar_t *)v145[0];
  }
  while ( 1 )
  {
    v163[v146] = 0;
    v43 = SczAllocFromSz(&Str, *(_QWORD *)(v42 + 24));
    if ( v43 < 0 )
    {
      v160 = v43;
      if ( *(_QWORD *)&LogAdapter::g_Logger )
      {
        LogAdapter::Logger::LogNumObjects<>(*(_QWORD *)&LogAdapter::g_Logger, 0, 3, "Failed to allocate memory");
        *(_QWORD *)v138 = &v160;
        bIgnoreCase = v138;
        LOBYTE(v132) = 1;
        LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
          *(_QWORD *)&LogAdapter::g_Logger,
          v132,
          3,
          ": {}");
      }
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x1172,
        (unsigned int)"onecore\\base\\servicing\\arbiter\\cactionlistcreator.cpp",
        (const char *)(unsigned int)v43,
        (int)bIgnoreCase);
      std::vector<UUPInstallPlan::UUPProduct>::_Tidy(&v170);
      std::_Tree<std::_Tset_traits<std::wstring,WstringCaseInsensitiveCompare,std::allocator<std::wstring>,0>>::~_Tree<std::_Tset_traits<std::wstring,WstringCaseInsensitiveCompare,std::allocator<std::wstring>,0>>(&v165);
      std::wstring::~wstring(&v167);
      if ( v11 && !FreeLibrary(v11) )
      {
        GetLastError();
        __fastfail(7u);
      }
      if ( Str )
        operator delete(Str - 4, v133);
      if ( v9 )
        operator delete((void *)(v9 - 8), v133);
      if ( v162 )
      {
        operator delete(v162 - 4, v133);
        v162 = 0;
      }
      if ( v8 )
        operator delete((void *)(v8 - 8), v133);
      if ( v161 )
      {
        operator delete(v161 - 4, v133);
        v161 = 0;
      }
      if ( v163 )
        operator delete(v163 - 4, v133);
      return (unsigned int)v43;
    }
    v10 = Str;
    v44 = wcsrchr(Str, 0x2Eu);
    if ( v44 )
      *v44 = 0;
    Directory = SczAllocConcatSz(&v163, v10);
    if ( Directory < 0 )
      break;
    lpFileName = 0;
    Directory = SczAllocFormatted(&lpFileName, L"%ws\\%ws", v163, L"express.psf.cix.xml");
    if ( Directory < 0 )
    {
      v160 = Directory;
      if ( *(_QWORD *)&LogAdapter::g_Logger )
      {
        LogAdapter::Logger::LogNumObjects<>(*(_QWORD *)&LogAdapter::g_Logger, 0, 3, "Failed to allocate memory");
        *(_QWORD *)v138 = &v160;
        bIgnoreCase = v138;
        LOBYTE(v130) = 1;
        LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
          *(_QWORD *)&LogAdapter::g_Logger,
          v130,
          3,
          ": {}");
      }
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x118B,
        (unsigned int)"onecore\\base\\servicing\\arbiter\\cactionlistcreator.cpp",
        (const char *)(unsigned int)Directory,
        (int)bIgnoreCase);
      goto LABEL_172;
    }
    v45 = (wchar_t **)(v42 + 120);
    if ( *(_QWORD *)(v42 + 120) )
    {
      LogAdapter::TraceInfo<wchar_t const *,wchar_t *>(
        "Skipping previously processed express payload file: {0} for express cab: {1}",
        v42 + 120,
        v42 + 16);
      if ( lpFileName )
        operator delete((void *)(lpFileName - 4), v46);
      goto LABEL_87;
    }
    if ( (unsigned int)DoesFileExist(lpFileName) )
    {
      v145[1] = 0;
      Directory = SczAllocFormatted(&v145[1], L"%ws\\%ws", &v163[v146], L"express.psf.cix.xml");
      if ( Directory < 0 )
      {
        v160 = Directory;
        if ( *(_QWORD *)&LogAdapter::g_Logger )
        {
          LogAdapter::Logger::LogNumObjects<>(*(_QWORD *)&LogAdapter::g_Logger, 0, 3, "Failed to allocate memory");
          *(_QWORD *)v138 = &v160;
          bIgnoreCase = v138;
          LOBYTE(v97) = 1;
          LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
            *(_QWORD *)&LogAdapter::g_Logger,
            v97,
            3,
            ": {}");
        }
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x119D,
          (unsigned int)"onecore\\base\\servicing\\arbiter\\cactionlistcreator.cpp",
          (const char *)(unsigned int)Directory,
          (int)bIgnoreCase);
        if ( v145[1] )
        {
          v96 = (void *)(v145[1] - 8LL);
LABEL_171:
          operator delete(v96, v95);
        }
LABEL_172:
        if ( lpFileName )
        {
          operator delete((void *)(lpFileName - 4), v95);
          lpFileName = 0;
        }
        goto LABEL_308;
      }
      v47 = (struct Windows::Rtl::IPoolAllocator *)(*(_QWORD *)v6 + 264LL);
      v48 = v145[1];
      v49 = DuplicateNullTerminatedString(v47, (const wchar_t *)v145[1]);
      *(_QWORD *)(v42 + 120) = v49;
      if ( !v49 )
      {
        Directory = -2147024882;
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x119F,
          (unsigned int)"onecore\\base\\servicing\\arbiter\\cactionlistcreator.cpp",
          (const char *)0x8007000ELL,
          (int)bIgnoreCase);
        if ( v48 )
        {
          v96 = (void *)(v48 - 8);
          goto LABEL_171;
        }
        goto LABEL_172;
      }
      LogAdapter::TraceInfo<wchar_t const *,wchar_t *>(
        "Skipping previously processed express payload file: {0} for express cab: {1}",
        &lpFileName,
        v42 + 16);
      if ( v48 )
        operator delete((void *)(v48 - 8), v50);
      if ( lpFileName )
      {
        v51 = (WCHAR *)(lpFileName - 4);
        goto LABEL_85;
      }
      goto LABEL_86;
    }
    if ( lpFileName )
      operator delete((void *)(lpFileName - 4), 0);
    v145[1] = v10;
    if ( !std::_Tree<std::_Tset_traits<std::wstring,WstringCaseInsensitiveCompare,std::allocator<std::wstring>,0>>::count<wchar_t *,WstringCaseInsensitiveCompare,0>(
            &v165,
            &v145[1]) )
    {
      v145[1] = v165;
      v151 = &v165;
      v152 = 0;
      v56 = std::_Allocate<16,std::_Default_allocate_traits>(64);
      v57 = (_QWORD *)v56;
      v152 = v56;
      *(_OWORD *)(v56 + 32) = 0;
      *(_QWORD *)(v56 + 48) = 0;
      *(_QWORD *)(v56 + 56) = 0;
      v58 = -1;
      do
        ++v58;
      while ( v10[v58] );
      std::wstring::_Construct<1,wchar_t const *>(v56 + 32, v10, v58);
      v59 = v145[1];
      *v57 = v145[1];
      v57[1] = v59;
      v57[2] = v59;
      *((_WORD *)v57 + 12) = 0;
      v60 = std::_Tree<std::_Tset_traits<std::wstring,WstringCaseInsensitiveCompare,std::allocator<std::wstring>,0>>::_Find_lower_bound<std::wstring>(
              &v165,
              v155,
              v57 + 4);
      v61 = *(_OWORD *)v60;
      if ( (unsigned __int8)std::_Tree<std::_Tset_traits<std::wstring,WstringCaseInsensitiveCompare,std::allocator<std::wstring>,0>>::_Lower_bound_duplicate<std::wstring>(
                              v62,
                              *(_QWORD *)(v60 + 16),
                              v57 + 4) )
      {
        std::wstring::~wstring(v57 + 4);
        operator delete(v57, (const struct std::nothrow_t *)0x40);
      }
      else
      {
        if ( v166 == 0x3FFFFFFFFFFFFFFLL )
          std::_Throw_tree_length_error();
        v152 = 0;
        *(_OWORD *)&v145[1] = v61;
        std::_Tree_val<std::_Tree_simple_types<std::wstring_view>>::_Insert_node(&v165, &v145[1], v57);
      }
      Directory = RecursiveRemoveDirectory(v63, v163);
      if ( Directory < 0 )
      {
        v160 = Directory;
        if ( *(_QWORD *)&LogAdapter::g_Logger )
        {
          LogAdapter::Logger::LogNumObjects<AutoScz>(
            *(_QWORD *)&LogAdapter::g_Logger,
            0,
            3,
            "Unable to delete directory {0}",
            &v163);
          *(_QWORD *)v138 = &v160;
          bIgnoreCase = v138;
          LOBYTE(v113) = 1;
          LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
            *(_QWORD *)&LogAdapter::g_Logger,
            v113,
            3,
            ": {}");
        }
        v105 = 4531;
        goto LABEL_307;
      }
      Directory = RecursivelyCreateDirectory(v163, 0);
      if ( Directory < 0 )
      {
        v160 = Directory;
        if ( *(_QWORD *)&LogAdapter::g_Logger )
        {
          LogAdapter::Logger::LogNumObjects<AutoScz>(
            *(_QWORD *)&LogAdapter::g_Logger,
            0,
            3,
            "Failed creating directory {0}",
            &v163);
          *(_QWORD *)v138 = &v160;
          bIgnoreCase = v138;
          LOBYTE(v112) = 1;
          LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
            *(_QWORD *)&LogAdapter::g_Logger,
            v112,
            3,
            ": {}");
        }
        v105 = 4537;
        goto LABEL_307;
      }
      v161[v146] = 0;
      Directory = SczAllocConcatSz(&v161, *(_QWORD *)(v42 + 24));
      if ( Directory < 0 )
      {
        v160 = Directory;
        if ( *(_QWORD *)&LogAdapter::g_Logger )
        {
          LogAdapter::Logger::LogNumObjects<>(*(_QWORD *)&LogAdapter::g_Logger, 0, 3, "Failed to allocate memory");
          *(_QWORD *)v138 = &v160;
          bIgnoreCase = v138;
          LOBYTE(v111) = 1;
          LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
            *(_QWORD *)&LogAdapter::g_Logger,
            v111,
            3,
            ": {}");
        }
        v105 = 4544;
        goto LABEL_307;
      }
      if ( !v11 )
      {
        v65 = DpxLoad(&v139);
        if ( v65 < 0 )
        {
          v160 = v65;
          if ( *(_QWORD *)&LogAdapter::g_Logger )
          {
            LogAdapter::Logger::LogNumObjects<>(*(_QWORD *)&LogAdapter::g_Logger, 0, 3, "Failed to load dpx.dll");
            *(_QWORD *)v138 = &v160;
            bIgnoreCase = v138;
            LOBYTE(v98) = 1;
            LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
              *(_QWORD *)&LogAdapter::g_Logger,
              v98,
              3,
              ": {}");
          }
          v99 = 4548;
          goto LABEL_177;
        }
        v11 = v139;
      }
      if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_ArbiterMetadataContainer>::__private_IsEnabled(
                              &`wil::Feature<__WilFeatureTraits_Feature_ArbiterMetadataContainer>::GetImpl'::`2'::impl,
                              v64)
        && (unsigned __int8)IsMetadataContainerSupported(*(unsigned int *)(*(_QWORD *)v6 + 52LL), v66, v67, v68)
        && *(_DWORD *)(v42 + 128) != 1 )
      {
        v145[1] = 0;
        Directory = SczAllocFormatted(&v145[1], L"%ws\\%ws", &v163[v146], L"express.psf.cix.xml");
        if ( Directory < 0 )
        {
          v160 = Directory;
          if ( *(_QWORD *)&LogAdapter::g_Logger )
          {
            LogAdapter::Logger::LogNumObjects<>(*(_QWORD *)&LogAdapter::g_Logger, 0, 3, "Failed to allocate memory");
            *(_QWORD *)v138 = &v160;
            bIgnoreCase = v138;
            LOBYTE(v103) = 1;
            LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
              *(_QWORD *)&LogAdapter::g_Logger,
              v103,
              3,
              ": {}");
          }
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x11D6,
            (unsigned int)"onecore\\base\\servicing\\arbiter\\cactionlistcreator.cpp",
            (const char *)(unsigned int)Directory,
            (int)bIgnoreCase);
          if ( !v145[1] )
            goto LABEL_308;
          v102 = (void *)(v145[1] - 8LL);
LABEL_193:
          operator delete(v102, v101);
          goto LABEL_308;
        }
        v69 = (struct Windows::Rtl::IPoolAllocator *)(*(_QWORD *)v6 + 264LL);
        v70 = v145[1];
        v71 = DuplicateNullTerminatedString(v69, (const wchar_t *)v145[1]);
        *(_QWORD *)(v42 + 120) = v71;
        if ( !v71 )
        {
          Directory = -2147024882;
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x11D8,
            (unsigned int)"onecore\\base\\servicing\\arbiter\\cactionlistcreator.cpp",
            (const char *)0x8007000ELL,
            (int)bIgnoreCase);
          if ( !v70 )
            goto LABEL_308;
          v102 = (void *)(v70 - 8);
          goto LABEL_193;
        }
        if ( v70 )
        {
          v51 = (WCHAR *)(v70 - 8);
LABEL_85:
          operator delete(v51, v50);
        }
LABEL_86:
        v6 = v143;
        goto LABEL_87;
      }
      LogAdapter::TraceInfo<wchar_t const *>("Expanding express cab: {0}", v42 + 16);
      CabFile = ExtractCabFile(v161, v163, 1);
      if ( CabFile < 0 )
      {
        v160 = CabFile;
        if ( *(_QWORD *)&LogAdapter::g_Logger )
        {
          LogAdapter::Logger::LogPartial<AutoScz,AutoScz>(
            v74,
            v73,
            "Failed to extract cab file: {0} in directory {1}. Trying to extract WIM",
            &v161,
            &v163);
          v145[1] = &v160;
          bIgnoreCase = (unsigned int *)&v145[1];
          LOBYTE(v75) = 1;
          LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
            *(_QWORD *)&LogAdapter::g_Logger,
            v75,
            1,
            ": {0}");
        }
        Directory = CbsEsdExtractAllFiles(v161, v163);
        if ( Directory < 0 )
        {
          v160 = Directory;
          if ( *(_QWORD *)&LogAdapter::g_Logger )
          {
            LogAdapter::Logger::LogNumObjects<AutoScz>(
              *(_QWORD *)&LogAdapter::g_Logger,
              0,
              3,
              "Failed to extract files from wim {0}.",
              &v161);
            *(_QWORD *)v138 = &v160;
            bIgnoreCase = v138;
            LOBYTE(v104) = 1;
            LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
              *(_QWORD *)&LogAdapter::g_Logger,
              v104,
              3,
              ": {}");
          }
          v105 = 4591;
          goto LABEL_307;
        }
      }
      v76 = *(_DWORD *)(*(_QWORD *)v6 + 52LL);
      if ( v76 <= 0x16 )
      {
        v77 = 4505604;
        if ( _bittest(&v77, v76) )
        {
          if ( *(_DWORD *)(v147 + 88) == 6 )
          {
            v78 = ActionTypeToLUTF8String(v158, *(unsigned int *)(v147 + 96));
            *(_OWORD *)&v145[1] = *(_OWORD *)v78;
            v145[3] = *(_QWORD *)(v78 + 16);
            v80 = OperationTypeToLUTF8String(v148, v79);
            *(_OWORD *)v155 = *(_OWORD *)v80;
            v156 = *(_QWORD *)(v80 + 16);
            if ( *(_QWORD *)&LogAdapter::g_Logger )
              LogAdapter::Logger::LogNumObjects<_LUTF8_STRING,_LUTF8_STRING>(
                LogAdapter::g_Logger,
                v81,
                v82,
                v83,
                (__int64)v155,
                (__int64)&v145[1]);
            v153[0] = L"ActionList.xml";
            v153[1] = 14;
            v154[0] = v163;
            v84 = -1;
            do
              ++v84;
            while ( v163[v84] );
            v154[1] = v84;
            Path = CreatePath(v148, (__int64)v154, v153);
            if ( *((_QWORD *)Path + 3) > 7u )
              Path = *(_OWORD **)Path;
            v86 = CopyFileW(lpExistingFileName, (LPCWSTR)Path, 0);
            std::wstring::~wstring(v148);
            if ( !v86 )
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
                  v109 = (unsigned __int16)LastError | 0x80070000;
                else
                  v109 = LastError;
                v160 = v109;
                *(_QWORD *)v138 = &v160;
                bIgnoreCase = v138;
                LOBYTE(v108) = 1;
                LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
                  *(_QWORD *)&LogAdapter::g_Logger,
                  v108,
                  3,
                  ": {0}");
              }
              if ( LastError )
              {
                v65 = wil::details::in1diag3::Return_Win32(
                        retaddr,
                        (void *)0x1205,
                        (unsigned int)"onecore\\base\\servicing\\arbiter\\cactionlistcreator.cpp",
                        (const char *)(unsigned int)LastError,
                        (unsigned int)bIgnoreCase);
                goto LABEL_178;
              }
              std::vector<UUPInstallPlan::UUPProduct>::_Tidy(&v170);
              std::_Tree<std::_Tset_traits<std::wstring,WstringCaseInsensitiveCompare,std::allocator<std::wstring>,0>>::~_Tree<std::_Tset_traits<std::wstring,WstringCaseInsensitiveCompare,std::allocator<std::wstring>,0>>(&v165);
              std::wstring::~wstring(&v167);
              CIUClient::~CIUClient((CIUClient *)&v139);
              if ( v10 )
                operator delete(v10 - 4, v110);
              if ( v9 )
                operator delete((void *)(v9 - 8), v110);
              if ( v162 )
              {
                operator delete(v162 - 4, v110);
                v162 = 0;
              }
              if ( v8 )
                operator delete((void *)(v8 - 8), v110);
              if ( v161 )
              {
                operator delete(v161 - 4, v110);
                v161 = 0;
              }
              if ( v163 )
                operator delete(v163 - 4, v110);
              return 0;
            }
            if ( *(_QWORD *)(v42 + 176) )
            {
              v145[1] = v10;
              if ( (unsigned __int8)Windows::StringUtil::AreStringsEqualByOrdinalCaseInvariantNonReflexive<wchar_t *,wchar_t *>(&v145[1]) )
              {
                if ( v168 )
                {
                  v65 = -2147418113;
                  v160 = -2147418113;
                  if ( *(_QWORD *)&LogAdapter::g_Logger )
                  {
                    LogAdapter::Logger::LogNumObjects<>(
                      *(_QWORD *)&LogAdapter::g_Logger,
                      0,
                      3,
                      "ExpressPackageTargetDirectory already set");
                    *(_QWORD *)v138 = &v160;
                    bIgnoreCase = v138;
                    LOBYTE(v106) = 1;
                    LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
                      *(_QWORD *)&LogAdapter::g_Logger,
                      v106,
                      3,
                      ": {}");
                  }
                  v99 = 4624;
LABEL_177:
                  wil::details::in1diag3::Return_Hr(
                    retaddr,
                    (void *)v99,
                    (unsigned int)"onecore\\base\\servicing\\arbiter\\cactionlistcreator.cpp",
                    (const char *)(unsigned int)v65,
                    (int)bIgnoreCase);
LABEL_178:
                  std::vector<UUPInstallPlan::UUPProduct>::_Tidy(&v170);
                  std::_Tree<std::_Tset_traits<std::wstring,WstringCaseInsensitiveCompare,std::allocator<std::wstring>,0>>::~_Tree<std::_Tset_traits<std::wstring,WstringCaseInsensitiveCompare,std::allocator<std::wstring>,0>>(&v165);
                  std::wstring::~wstring(&v167);
                  CIUClient::~CIUClient((CIUClient *)&v139);
                  if ( v10 )
                    operator delete(v10 - 4, v100);
                  if ( v9 )
                    operator delete((void *)(v9 - 8), v100);
                  if ( v162 )
                  {
                    operator delete(v162 - 4, v100);
                    v162 = 0;
                  }
                  if ( v8 )
                    operator delete((void *)(v8 - 8), v100);
                  if ( v161 )
                  {
                    operator delete(v161 - 4, v100);
                    v161 = 0;
                  }
                  if ( v163 )
                    operator delete(v163 - 4, v100);
                  return (unsigned int)v65;
                }
                v87 = -1;
                do
                  ++v87;
                while ( v163[v87] );
                std::wstring::_Assign<wchar_t>(&v167, v163, v87);
              }
              else
              {
                std::wstring::wstring(v148, v163);
                std::vector<std::wstring>::push_back(&v170, v148);
                std::wstring::~wstring(v148);
              }
            }
            v6 = v143;
          }
        }
      }
      v45 = (wchar_t **)(v42 + 120);
    }
    v88 = SczAllocFormatted(&v142, L"%ws.cix.xml", *(_QWORD *)(v42 + 72));
    if ( v88 < 0 )
    {
      v160 = v88;
      if ( *(_QWORD *)&LogAdapter::g_Logger )
      {
        LogAdapter::Logger::LogNumObjects<>(*(_QWORD *)&LogAdapter::g_Logger, 0, 3, "Failed to allocate memory");
        *(_QWORD *)v138 = &v160;
        bIgnoreCase = v138;
        LOBYTE(v128) = 1;
        LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
          *(_QWORD *)&LogAdapter::g_Logger,
          v128,
          3,
          ": {}");
      }
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x1220,
        (unsigned int)"onecore\\base\\servicing\\arbiter\\cactionlistcreator.cpp",
        (const char *)(unsigned int)v88,
        (int)bIgnoreCase);
      std::vector<UUPInstallPlan::UUPProduct>::_Tidy(&v170);
      std::_Tree<std::_Tset_traits<std::wstring,WstringCaseInsensitiveCompare,std::allocator<std::wstring>,0>>::~_Tree<std::_Tset_traits<std::wstring,WstringCaseInsensitiveCompare,std::allocator<std::wstring>,0>>(&v165);
      std::wstring::~wstring(&v167);
      CIUClient::~CIUClient((CIUClient *)&v139);
      if ( v10 )
        operator delete(v10 - 4, v129);
      if ( v9 )
        operator delete((void *)(v9 - 8), v129);
      if ( v162 )
      {
        operator delete(v162 - 4, v129);
        v162 = 0;
      }
      if ( v142 )
        operator delete((void *)(v142 - 8), v129);
      if ( v161 )
      {
        operator delete(v161 - 4, v129);
        v161 = 0;
      }
      if ( v163 )
        operator delete(v163 - 4, v129);
      return (unsigned int)v88;
    }
    v8 = v142;
    v90 = SczAllocFormatted(&v141, L"%ws\\%ws", v163, v142);
    if ( v90 < 0 )
    {
      v160 = v90;
      if ( *(_QWORD *)&LogAdapter::g_Logger )
      {
        LogAdapter::Logger::LogNumObjects<>(*(_QWORD *)&LogAdapter::g_Logger, 0, 3, "Failed to allocate memory");
        *(_QWORD *)v138 = &v160;
        bIgnoreCase = v138;
        LOBYTE(v126) = 1;
        LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
          *(_QWORD *)&LogAdapter::g_Logger,
          v126,
          3,
          ": {}");
      }
      v116 = 4646;
      goto LABEL_273;
    }
    if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_ArbiterMetadataContainer>::__private_IsEnabled(
                            &`wil::Feature<__WilFeatureTraits_Feature_ArbiterMetadataContainer>::GetImpl'::`2'::impl,
                            v89)
      && *(_DWORD *)(*(_QWORD *)v6 + 52LL) == 1
      && *(_DWORD *)(v42 + 128) != 1 )
    {
      v90 = SczAllocFormatted(&v162, L"%ws\\%ws", &v163[v146], v8);
      if ( v90 < 0 )
      {
        v160 = v90;
        if ( *(_QWORD *)&LogAdapter::g_Logger )
        {
          LogAdapter::Logger::LogNumObjects<>(*(_QWORD *)&LogAdapter::g_Logger, 0, 3, "Failed to allocate memory");
          *(_QWORD *)v138 = &v160;
          bIgnoreCase = v138;
          LOBYTE(v115) = 1;
          LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
            *(_QWORD *)&LogAdapter::g_Logger,
            v115,
            3,
            ": {}");
        }
        v116 = 4655;
LABEL_273:
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)v116,
          (unsigned int)"onecore\\base\\servicing\\arbiter\\cactionlistcreator.cpp",
          (const char *)(unsigned int)v90,
          (int)bIgnoreCase);
        std::vector<UUPInstallPlan::UUPProduct>::_Tidy(&v170);
        std::_Tree<std::_Tset_traits<std::wstring,WstringCaseInsensitiveCompare,std::allocator<std::wstring>,0>>::~_Tree<std::_Tset_traits<std::wstring,WstringCaseInsensitiveCompare,std::allocator<std::wstring>,0>>(&v165);
        std::wstring::~wstring(&v167);
        CIUClient::~CIUClient((CIUClient *)&v139);
        if ( v10 )
          operator delete(v10 - 4, v127);
        if ( v141 )
          operator delete((void *)(v141 - 8), v127);
        if ( v162 )
        {
          operator delete(v162 - 4, v127);
          v162 = 0;
        }
        if ( v8 )
          operator delete((void *)(v8 - 8), v127);
        if ( v161 )
        {
          operator delete(v161 - 4, v127);
          v161 = 0;
        }
        if ( v163 )
          operator delete(v163 - 4, v127);
        return (unsigned int)v90;
      }
      v91 = DuplicateNullTerminatedString((struct Windows::Rtl::IPoolAllocator *)(*(_QWORD *)v6 + 264LL), v162);
      *v45 = v91;
      if ( !v91 )
      {
        Directory = -2147024882;
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x1232,
          (unsigned int)"onecore\\base\\servicing\\arbiter\\cactionlistcreator.cpp",
          (const char *)0x8007000ELL,
          (int)bIgnoreCase);
        std::vector<UUPInstallPlan::UUPProduct>::_Tidy(&v170);
        std::_Tree<std::_Tset_traits<std::wstring,WstringCaseInsensitiveCompare,std::allocator<std::wstring>,0>>::~_Tree<std::_Tset_traits<std::wstring,WstringCaseInsensitiveCompare,std::allocator<std::wstring>,0>>(&v165);
        std::wstring::~wstring(&v167);
        CIUClient::~CIUClient((CIUClient *)&v139);
        if ( v10 )
          operator delete(v10 - 4, v114);
        if ( v141 )
          operator delete((void *)(v141 - 8), v114);
        if ( v162 )
        {
          operator delete(v162 - 4, v114);
          v162 = 0;
        }
        if ( v8 )
          operator delete((void *)(v8 - 8), v114);
        if ( v161 )
        {
          operator delete(v161 - 4, v114);
          v161 = 0;
        }
        goto LABEL_342;
      }
      v9 = v141;
    }
    else
    {
      v9 = v141;
      if ( !(unsigned int)DoesFileExist(v141) )
      {
        lpFileName = 0;
        v145[1] = 0;
        memset_0(&FindFileData, 0, sizeof(FindFileData));
        Directory = SczAllocFromSz(&lpFileName, v163);
        if ( Directory < 0 )
        {
          v160 = Directory;
          if ( *(_QWORD *)&LogAdapter::g_Logger )
          {
            LogAdapter::Logger::LogNumObjects<>(*(_QWORD *)&LogAdapter::g_Logger, 0, 3, "Failed to allocate memory");
            *(_QWORD *)v138 = &v160;
            bIgnoreCase = v138;
            LOBYTE(v123) = 1;
            LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
              *(_QWORD *)&LogAdapter::g_Logger,
              v123,
              3,
              ": {}");
          }
          v118 = 4678;
          goto LABEL_248;
        }
        Directory = SczAllocConcatSz(&lpFileName, L"\\*.cix.xml");
        if ( Directory < 0 )
        {
          v160 = Directory;
          if ( *(_QWORD *)&LogAdapter::g_Logger )
          {
            LogAdapter::Logger::LogNumObjects<>(*(_QWORD *)&LogAdapter::g_Logger, 0, 3, "Failed to allocate memory");
            *(_QWORD *)v138 = &v160;
            bIgnoreCase = v138;
            LOBYTE(v122) = 1;
            LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
              *(_QWORD *)&LogAdapter::g_Logger,
              v122,
              3,
              ": {}");
          }
          v118 = 4680;
LABEL_248:
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)v118,
            (unsigned int)"onecore\\base\\servicing\\arbiter\\cactionlistcreator.cpp",
            (const char *)(unsigned int)Directory,
            (int)bIgnoreCase);
LABEL_249:
          Windows::AutoGenericHandle<void *,1,&void Windows::Detail::CloseWithFindClose(void *)>::~AutoGenericHandle<void *,1,&void Windows::Detail::CloseWithFindClose(void *)>(&v145[1]);
          AutoScz::~AutoScz((AutoScz *)&lpFileName);
          goto LABEL_250;
        }
        v145[1] = FindFirstFileW(lpFileName, &FindFileData);
        if ( (unsigned __int64)(v145[1] - 1LL) > 0xFFFFFFFFFFFFFFFDuLL )
        {
          v119 = GetLastError();
          if ( *(_QWORD *)&LogAdapter::g_Logger )
          {
            LogAdapter::Logger::LogNumObjects<AutoScz>(
              *(_QWORD *)&LogAdapter::g_Logger,
              0,
              3,
              "Failed to find a CiX file in directory: {0}",
              &v163);
            if ( v119 > 0 )
              v121 = (unsigned __int16)v119 | 0x80070000;
            else
              v121 = v119;
            v160 = v121;
            *(_QWORD *)v138 = &v160;
            bIgnoreCase = v138;
            LOBYTE(v120) = 1;
            LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
              *(_QWORD *)&LogAdapter::g_Logger,
              v120,
              3,
              ": {0}");
          }
          if ( !v119 )
          {
            Windows::AutoGenericHandle<void *,1,&void Windows::Detail::CloseWithFindClose(void *)>::~AutoGenericHandle<void *,1,&void Windows::Detail::CloseWithFindClose(void *)>(&v145[1]);
            AutoScz::~AutoScz((AutoScz *)&lpFileName);
            std::vector<UUPInstallPlan::UUPProduct>::_Tidy(&v170);
            std::_Tree<std::_Tset_traits<std::wstring,WstringCaseInsensitiveCompare,std::allocator<std::wstring>,0>>::~_Tree<std::_Tset_traits<std::wstring,WstringCaseInsensitiveCompare,std::allocator<std::wstring>,0>>(&v165);
            std::wstring::~wstring(&v167);
            CIUClient::~CIUClient((CIUClient *)&v139);
            AutoScz::~AutoScz((AutoScz *)&Str);
            AutoScz::~AutoScz((AutoScz *)&v141);
            AutoScz::~AutoScz((AutoScz *)&v162);
            AutoScz::~AutoScz((AutoScz *)&v142);
            AutoScz::~AutoScz((AutoScz *)&v161);
            Directory = 0;
LABEL_342:
            AutoScz::~AutoScz((AutoScz *)&v163);
            return (unsigned int)Directory;
          }
          Directory = wil::details::in1diag3::Return_Win32(
                        retaddr,
                        (void *)0x124B,
                        (unsigned int)"onecore\\base\\servicing\\arbiter\\cactionlistcreator.cpp",
                        (const char *)(unsigned int)v119,
                        (unsigned int)bIgnoreCase);
          goto LABEL_249;
        }
        Directory = SczAllocFromSz(&v142, FindFileData.cFileName);
        if ( Directory < 0 )
        {
          v160 = Directory;
          if ( *(_QWORD *)&LogAdapter::g_Logger )
          {
            LogAdapter::Logger::LogNumObjects<>(*(_QWORD *)&LogAdapter::g_Logger, 0, 3, "Failed to allocate memory");
            *(_QWORD *)v138 = &v160;
            bIgnoreCase = v138;
            LOBYTE(v117) = 1;
            LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
              *(_QWORD *)&LogAdapter::g_Logger,
              v117,
              3,
              ": {}");
          }
          v118 = 4685;
          goto LABEL_248;
        }
        Windows::AutoGenericHandle<void *,1,&void Windows::Detail::CloseWithFindClose(void *)>::~AutoGenericHandle<void *,1,&void Windows::Detail::CloseWithFindClose(void *)>(&v145[1]);
        AutoScz::~AutoScz((AutoScz *)&lpFileName);
        v8 = v142;
      }
      Directory = SczAllocFormatted(&v162, L"%ws\\%ws", &v163[v146], v8);
      if ( Directory < 0 )
      {
        v160 = Directory;
        if ( *(_QWORD *)&LogAdapter::g_Logger )
        {
          LogAdapter::Logger::LogNumObjects<>(*(_QWORD *)&LogAdapter::g_Logger, 0, 3, "Failed to allocate memory");
          *(_QWORD *)v138 = &v160;
          bIgnoreCase = v138;
          LOBYTE(v125) = 1;
          LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
            *(_QWORD *)&LogAdapter::g_Logger,
            v125,
            3,
            ": {}");
        }
        v124 = 4689;
LABEL_266:
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)v124,
          (unsigned int)"onecore\\base\\servicing\\arbiter\\cactionlistcreator.cpp",
          (const char *)(unsigned int)Directory,
          (int)bIgnoreCase);
LABEL_250:
        std::vector<UUPInstallPlan::UUPProduct>::_Tidy(&v170);
        std::_Tree<std::_Tset_traits<std::wstring,WstringCaseInsensitiveCompare,std::allocator<std::wstring>,0>>::~_Tree<std::_Tset_traits<std::wstring,WstringCaseInsensitiveCompare,std::allocator<std::wstring>,0>>(&v165);
        goto LABEL_341;
      }
      v92 = DuplicateNullTerminatedString((struct Windows::Rtl::IPoolAllocator *)(*(_QWORD *)v6 + 264LL), v162);
      *(_QWORD *)(v42 + 120) = v92;
      if ( !v92 )
      {
        Directory = -2147024882;
        v124 = 4692;
        goto LABEL_266;
      }
      LogAdapter::TraceInfo<AutoScz>("  Cix file found: {0}", &v162);
    }
LABEL_87:
    v42 += 184;
    if ( v42 == v149 )
      goto LABEL_88;
  }
  v160 = Directory;
  if ( *(_QWORD *)&LogAdapter::g_Logger )
  {
    LogAdapter::Logger::LogNumObjects<>(*(_QWORD *)&LogAdapter::g_Logger, 0, 3, "Failed to allocate memory");
    *(_QWORD *)v138 = &v160;
    bIgnoreCase = v138;
    LOBYTE(v131) = 1;
    LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
      *(_QWORD *)&LogAdapter::g_Logger,
      v131,
      3,
      ": {}");
  }
  v105 = 4477;
LABEL_307:
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)v105,
    (unsigned int)"onecore\\base\\servicing\\arbiter\\cactionlistcreator.cpp",
    (const char *)(unsigned int)Directory,
    (int)bIgnoreCase);
LABEL_308:
  std::vector<UUPInstallPlan::UUPProduct>::_Tidy(&v170);
  std::_Tree<std::_Tset_traits<std::wstring,WstringCaseInsensitiveCompare,std::allocator<std::wstring>,0>>::~_Tree<std::_Tset_traits<std::wstring,WstringCaseInsensitiveCompare,std::allocator<std::wstring>,0>>(&v165);
  std::wstring::~wstring(&v167);
  CIUClient::~CIUClient((CIUClient *)&v139);
  if ( v10 )
    operator delete(v10 - 4, v16);
  if ( v9 )
    operator delete((void *)(v9 - 8), v16);
  if ( v162 )
  {
    operator delete(v162 - 4, v16);
    v162 = 0;
  }
  if ( v8 )
    operator delete((void *)(v8 - 8), v16);
  if ( v161 )
  {
    operator delete(v161 - 4, v16);
    v161 = 0;
  }
LABEL_11:
  if ( v163 )
    operator delete(v163 - 4, v16);
  return (unsigned int)Directory;
}

```

## disassembly

```asm
0x1800f995c  mov     rax, rsp
0x1800f995f  push    rbp
0x1800f9960  push    rbx
0x1800f9961  push    rsi
0x1800f9962  push    rdi
0x1800f9963  push    r12
0x1800f9965  push    r13
0x1800f9967  push    r14
0x1800f9969  push    r15
0x1800f996b  lea     rbp, [rax-378h]
0x1800f9972  sub     rsp, 438h
0x1800f9979  mov     [rbp+370h+var_358], 0FFFFFFFFFFFFFFFEh
0x1800f9981  movaps  xmmword ptr [rax-58h], xmm6
0x1800f9985  mov     rax, cs:__security_cookie
0x1800f998c  xor     rax, rsp
0x1800f998f  mov     [rbp+370h+var_60], rax
0x1800f9996  mov     r12, r8
0x1800f9999  mov     [rbp+370h+var_3A8], rdx
0x1800f999d  mov     r14, rcx
0x1800f99a0  mov     [rsp+470h+var_418], rcx
0x1800f99a5  mov     [rbp+370h+lpExistingFileName], r9
0x1800f99a9  mov     r13, [rbp+370h+arg_20]
0x1800f99b0  mov     qword ptr [rsp+470h+var_408], r13
0x1800f99b5  xor     ecx, ecx
0x1800f99b7  mov     [rbp+370h+var_310], rcx
0x1800f99bb  mov     [rbp+370h+var_320], rcx
0x1800f99bf  mov     ebx, ecx
0x1800f99c1  mov     [rsp+470h+var_420], rcx
0x1800f99c6  mov     [rbp+370h+var_318], rcx
0x1800f99ca  mov     edi, ecx
0x1800f99cc  mov     [rsp+470h+var_428], rcx
0x1800f99d1  mov     r15d, ecx
0x1800f99d4  mov     [rsp+470h+Str], rcx
0x1800f99d9  mov     esi, ecx
0x1800f99db  mov     [rsp+470h+var_438], rcx
0x1800f99e0  xorps   xmm0, xmm0
0x1800f99e3  movups  [rbp+370h+var_2F0], xmm0
0x1800f99ea  mov     [rbp+370h+var_2E0], rcx
0x1800f99f1  mov     [rbp+370h+var_2D8], 7
0x1800f99fc  mov     word ptr [rbp+370h+var_2F0], cx
0x1800f9a03  mov     rax, [rdx]
0x1800f9a06  cmp     [r14], rcx
0x1800f9a09  jz      short loc_1800F9A0C
0x1800f9a0b  int     3; Trap to Debugger
0x1800f9a0c  mov     [r14], rax
0x1800f9a0f  mov     [rdx], rcx
0x1800f9a12  lea     rcx, aArbiterExpress; "arbiter: Express download resumed"
0x1800f9a19  call    ??$TraceInfo@$$V@LogAdapter@@YAXQEBD@Z; LogAdapter::TraceInfo<>(char const * const)
0x1800f9a1e  mov     rdx, r12
0x1800f9a21  lea     rcx, [rbp+370h+var_310]
0x1800f9a25  call    SczAllocFromSz
0x1800f9a2a  mov     r12d, eax
0x1800f9a2d  test    eax, eax
0x1800f9a2f  jns     loc_1800F9AF6
0x1800f9a35  mov     [rbp+370h+var_328], eax
0x1800f9a38  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1800f9a3f  xor     r13d, r13d
0x1800f9a42  test    rcx, rcx
0x1800f9a45  jz      short loc_1800F9A87
0x1800f9a47  lea     r9, aFailedToAlloca; "Failed to allocate memory"
0x1800f9a4e  lea     r14d, [r13+3]
0x1800f9a52  mov     r8d, r14d
0x1800f9a55  xor     edx, edx
0x1800f9a57  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x1800f9a5c  lea     rax, [rbp+370h+var_328]
0x1800f9a60  mov     qword ptr [rsp+470h+var_408], rax
0x1800f9a65  lea     rax, [rsp+470h+var_408]
0x1800f9a6a  mov     qword ptr [rsp+470h+bIgnoreCase], rax; int
0x1800f9a6f  lea     r9, asc_1802C6678; ": {}"
0x1800f9a76  mov     r8d, r14d
0x1800f9a79  mov     dl, 1
0x1800f9a7b  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1800f9a82  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x1800f9a87  mov     edx, 111Eh; void *
0x1800f9a8c  mov     r9d, r12d; char *
0x1800f9a8f  lea     r8, aOnecoreBaseSer_8; "onecore\\base\\servicing\\arbiter\\cact"...
0x1800f9a96  mov     rcx, [rbp+378h]; this
0x1800f9a9d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800f9aa2  nop
0x1800f9aa3  lea     rcx, [rbp+370h+var_2F0]; void *
0x1800f9aaa  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800f9aaf  nop
0x1800f9ab0  mov     rcx, [rbp+370h+var_318]
0x1800f9ab4  test    rcx, rcx
0x1800f9ab7  jz      short loc_1800F9AC6
0x1800f9ab9  add     rcx, 0FFFFFFFFFFFFFFF8h; void *
0x1800f9abd  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1800f9ac2  mov     [rbp+370h+var_318], r13
0x1800f9ac6  mov     rcx, [rbp+370h+var_320]
0x1800f9aca  test    rcx, rcx
0x1800f9acd  jz      short loc_1800F9ADC
0x1800f9acf  add     rcx, 0FFFFFFFFFFFFFFF8h; void *
0x1800f9ad3  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1800f9ad8  mov     [rbp+370h+var_320], r13
0x1800f9adc  mov     rcx, [rbp+370h+var_310]
0x1800f9ae0  test    rcx, rcx
0x1800f9ae3  jz      short loc_1800F9AEE
0x1800f9ae5  add     rcx, 0FFFFFFFFFFFFFFF8h; void *
0x1800f9ae9  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1800f9aee  mov     eax, r12d
0x1800f9af1  jmp     loc_1800FB7C6
0x1800f9af6  lea     rcx, [rbp+370h+var_310]
0x1800f9afa  call    SczEnsureBackslashTerminated
0x1800f9aff  mov     r12d, eax
0x1800f9b02  test    eax, eax
0x1800f9b04  jns     short loc_1800F9B62
0x1800f9b06  mov     [rbp+370h+var_328], eax
0x1800f9b09  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1800f9b10  xor     r13d, r13d
0x1800f9b13  test    rcx, rcx
0x1800f9b16  jz      short loc_1800F9B58
0x1800f9b18  lea     r9, aFailedToAlloca; "Failed to allocate memory"
0x1800f9b1f  lea     r14d, [r13+3]
0x1800f9b23  mov     r8d, r14d
0x1800f9b26  xor     edx, edx
0x1800f9b28  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x1800f9b2d  lea     rax, [rbp+370h+var_328]
0x1800f9b31  mov     qword ptr [rsp+470h+var_408], rax
0x1800f9b36  lea     rax, [rsp+470h+var_408]
0x1800f9b3b  mov     qword ptr [rsp+470h+bIgnoreCase], rax
0x1800f9b40  lea     r9, asc_1802C6678; ": {}"
0x1800f9b47  mov     r8d, r14d
0x1800f9b4a  mov     dl, 1
0x1800f9b4c  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1800f9b53  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x1800f9b58  mov     edx, 1120h
0x1800f9b5d  jmp     loc_1800F9A8C
0x1800f9b62  mov     rdx, [rbp+370h+var_310]
0x1800f9b66  lea     rcx, [rbp+370h+var_320]
0x1800f9b6a  call    SczAllocFromSz
0x1800f9b6f  mov     r12d, eax
0x1800f9b72  xor     edx, edx
0x1800f9b74  test    eax, eax
0x1800f9b76  jns     short loc_1800F9BD2
0x1800f9b78  mov     [rbp+370h+var_328], eax
0x1800f9b7b  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1800f9b82  xor     r13d, r13d
0x1800f9b85  test    rcx, rcx
0x1800f9b88  jz      short loc_1800F9BC8
0x1800f9b8a  lea     r9, aFailedToAlloca; "Failed to allocate memory"
0x1800f9b91  lea     r14d, [rdx+3]
0x1800f9b95  mov     r8d, r14d
0x1800f9b98  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x1800f9b9d  lea     rax, [rbp+370h+var_328]
0x1800f9ba1  mov     qword ptr [rsp+470h+var_408], rax
0x1800f9ba6  lea     rax, [rsp+470h+var_408]
0x1800f9bab  mov     qword ptr [rsp+470h+bIgnoreCase], rax
0x1800f9bb0  lea     r9, asc_1802C6678; ": {}"
0x1800f9bb7  mov     r8d, r14d
0x1800f9bba  mov     dl, 1
0x1800f9bbc  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1800f9bc3  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x1800f9bc8  mov     edx, 1122h
0x1800f9bcd  jmp     loc_1800F9A8C
0x1800f9bd2  mov     rax, [rbp+370h+var_310]
0x1800f9bd6  or      rcx, 0FFFFFFFFFFFFFFFFh
0x1800f9bda  inc     rcx
0x1800f9bdd  cmp     [rax+rcx*2], dx
0x1800f9be1  jnz     short loc_1800F9BDA
0x1800f9be3  mov     [rbp+370h+var_3E0], rcx
0x1800f9be7  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_ArbiterMetadataContainer@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_ArbiterMetadataContainer@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ArbiterMetadataContainer> `wil::Feature<__WilFeatureTraits_Feature_ArbiterMetadataContainer>::GetImpl(void)'::`2'::impl
0x1800f9bee  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_ArbiterMetadataContainer@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ArbiterMetadataContainer>::__private_IsEnabled(void)
0x1800f9bf3  xor     r9d, r9d
0x1800f9bf6  test    al, al
0x1800f9bf8  jz      loc_1800F9CEB
0x1800f9bfe  mov     rcx, [r14]
0x1800f9c01  mov     ecx, [rcx+34h]
0x1800f9c04  call    IsMetadataContainerSupported
0x1800f9c09  xor     r9d, r9d
0x1800f9c0c  test    al, al
0x1800f9c0e  jz      loc_1800F9CEB
0x1800f9c14  mov     rax, [r14]
0x1800f9c17  mov     r13, [rax+188h]
0x1800f9c1e  imul    r12, [rax+178h], 0A8h
0x1800f9c29  add     r12, r13
0x1800f9c2c  jmp     loc_1800F9CDD
0x1800f9c31  cmp     [r13+78h], r9d
0x1800f9c35  jbe     loc_1800F9CD6
0x1800f9c3b  mov     r14, [r13+70h]
0x1800f9c3f  mov     rdx, r9
0x1800f9c42  mov     eax, [r13+78h]
0x1800f9c46  imul    rax, 0B8h
0x1800f9c4d  add     rax, r14
0x1800f9c50  mov     [rbp+370h+var_3D8], rax
0x1800f9c54  cmp     r14, rax
0x1800f9c57  jz      short loc_1800F9CD1
0x1800f9c59  cmp     dword ptr [r14+8], 2
0x1800f9c5e  jnz     short loc_1800F9C95
0x1800f9c60  cmp     [r14+18h], r9
0x1800f9c64  jz      short loc_1800F9C95
0x1800f9c66  mov     rax, [rsp+470h+var_418]
0x1800f9c6b  mov     rcx, [rax]
0x1800f9c6e  add     rcx, 108h; struct Windows::Rtl::IPoolAllocator *
0x1800f9c75  mov     rdx, [r14+18h]; wchar_t *
0x1800f9c79  call    ?DuplicateNullTerminatedString@@YAPEA_WAEAVIPoolAllocator@Rtl@Windows@@PEB_W@Z; DuplicateNullTerminatedString(Windows::Rtl::IPoolAllocator &,wchar_t const *)
0x1800f9c7e  mov     [r14+68h], rax
0x1800f9c82  xor     r9d, r9d
0x1800f9c85  test    rax, rax
0x1800f9c88  jz      loc_1800F9D24
0x1800f9c8e  mov     rdx, r14
0x1800f9c91  mov     rax, [rbp+370h+var_3D8]
0x1800f9c95  add     r14, 0B8h
0x1800f9c9c  cmp     r14, rax
0x1800f9c9f  jnz     short loc_1800F9C59
0x1800f9ca1  mov     r14, [rsp+470h+var_418]
0x1800f9ca6  test    rdx, rdx
0x1800f9ca9  jz      short loc_1800F9CD6
0x1800f9cab  mov     rcx, [r14]
0x1800f9cae  add     rcx, 108h; struct Windows::Rtl::IPoolAllocator *
0x1800f9cb5  mov     rdx, [rdx+68h]; wchar_t *
0x1800f9cb9  call    ?DuplicateNullTerminatedString@@YAPEA_WAEAVIPoolAllocator@Rtl@Windows@@PEB_W@Z; DuplicateNullTerminatedString(Windows::Rtl::IPoolAllocator &,wchar_t const *)
0x1800f9cbe  mov     [r13+50h], rax
0x1800f9cc2  xor     r9d, r9d
0x1800f9cc5  test    rax, rax
0x1800f9cc8  jnz     short loc_1800F9CD6
0x1800f9cca  mov     edx, 1146h
0x1800f9ccf  jmp     short loc_1800F9D29
0x1800f9cd1  mov     r14, [rsp+470h+var_418]
0x1800f9cd6  add     r13, 0A8h
0x1800f9cdd  cmp     r13, r12
0x1800f9ce0  jnz     loc_1800F9C31
0x1800f9ce6  mov     r13, qword ptr [rsp+470h+var_408]
0x1800f9ceb  mov     byte ptr [rsp+470h+var_430], r9b
0x1800f9cf0  mov     rcx, [r14]
0x1800f9cf3  mov     eax, [rcx+34h]
0x1800f9cf6  mov     edx, 44C004h
0x1800f9cfb  cmp     eax, 16h
0x1800f9cfe  ja      loc_1800F9DA3
0x1800f9d04  bt      edx, eax
0x1800f9d07  jnb     loc_1800F9DA3
0x1800f9d0d  mov     rax, [rcx+188h]
0x1800f9d14  imul    rdx, [rcx+178h], 0A8h
0x1800f9d1f  add     rdx, rax
0x1800f9d22  jmp     short loc_1800F9D97
0x1800f9d24  mov     edx, 113Eh; void *
0x1800f9d29  mov     r12d, 8007000Eh
0x1800f9d2f  mov     r9d, r12d; char *
0x1800f9d32  lea     r8, aOnecoreBaseSer_8; "onecore\\base\\servicing\\arbiter\\cact"...
0x1800f9d39  mov     rcx, [rbp+378h]; this
0x1800f9d40  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800f9d45  nop
0x1800f9d46  lea     rcx, [rbp+370h+var_2F0]; void *
0x1800f9d4d  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800f9d52  nop
0x1800f9d53  xor     r14d, r14d
0x1800f9d56  mov     rcx, [rbp+370h+var_318]
0x1800f9d5a  test    rcx, rcx
0x1800f9d5d  jz      short loc_1800F9D6C
0x1800f9d5f  add     rcx, 0FFFFFFFFFFFFFFF8h; void *
0x1800f9d63  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1800f9d68  mov     [rbp+370h+var_318], r14
0x1800f9d6c  mov     rcx, [rbp+370h+var_320]
0x1800f9d70  test    rcx, rcx
0x1800f9d73  jz      loc_1800F9ADC
0x1800f9d79  add     rcx, 0FFFFFFFFFFFFFFF8h; void *
0x1800f9d7d  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1800f9d82  mov     [rbp+370h+var_320], r14
0x1800f9d86  jmp     loc_1800F9ADC
0x1800f9d8b  cmp     dword ptr [rax+60h], 4
0x1800f9d8f  jz      short loc_1800F9D9E
0x1800f9d91  add     rax, 0A8h
0x1800f9d97  cmp     rax, rdx
0x1800f9d9a  jnz     short loc_1800F9D8B
0x1800f9d9c  jmp     short loc_1800F9DA3
0x1800f9d9e  mov     byte ptr [rsp+470h+var_430], 1
0x1800f9da3  mov     r12, [rcx+148h]
0x1800f9daa  mov     [rbp+370h+var_3D8], r12
0x1800f9dae  imul    rax, [rcx+138h], 0A8h
0x1800f9db9  add     rax, r12
0x1800f9dbc  mov     qword ptr [rsp+470h+var_440], rax
0x1800f9dc1  cmp     r12, rax
0x1800f9dc4  jz      loc_1800FB668
0x1800f9dca  cmp     dword ptr [r12+68h], 2
0x1800f9dd0  jnz     loc_1800FA7AD
0x1800f9dd6  mov     rcx, [r14]
0x1800f9dd9  cmp     dword ptr [rcx+34h], 8
0x1800f9ddd  jnz     loc_1800F9EAA
0x1800f9de3  add     rcx, 108h; struct Windows::Rtl::IPoolAllocator *
0x1800f9dea  mov     rdx, r13; wchar_t *
0x1800f9ded  call    ?DuplicateNullTerminatedString@@YAPEA_WAEAVIPoolAllocator@Rtl@Windows@@PEB_W@Z; DuplicateNullTerminatedString(Windows::Rtl::IPoolAllocator &,wchar_t const *)
0x1800f9df2  mov     [r12+80h], rax
0x1800f9dfa  xor     r13d, r13d
0x1800f9dfd  test    rax, rax
0x1800f9e00  jnz     loc_1800F9EAD
0x1800f9e06  mov     rcx, [rbp+378h]; this
0x1800f9e0d  mov     r12d, 8007000Eh
0x1800f9e13  mov     r9d, r12d; char *
0x1800f9e16  lea     r8, aOnecoreBaseSer_8; "onecore\\base\\servicing\\arbiter\\cact"...
0x1800f9e1d  mov     edx, 1168h; void *
0x1800f9e22  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800f9e27  nop
0x1800f9e28  lea     rcx, [rbp+370h+var_2F0]; void *
0x1800f9e2f  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800f9e34  nop
0x1800f9e35  test    rsi, rsi
0x1800f9e38  jz      short loc_1800F9E5F
0x1800f9e3a  mov     rcx, rsi; hLibModule
0x1800f9e3d  call    cs:__imp_FreeLibrary
0x1800f9e44  nop     dword ptr [rax+rax+00h]
0x1800f9e49  test    eax, eax
  ... truncated ...
```
