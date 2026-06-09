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
  const struct std::nothrow_t *v15; // rdx
  int v17; // eax
  int v18; // eax
  __int64 v19; // rcx
  __int64 v20; // rdx
  __int64 v21; // r8
  __int64 v22; // r13
  __int64 v23; // r12
  __int64 v24; // r14
  __int64 v25; // rdx
  __int64 v26; // rax
  wchar_t *v27; // rax
  wchar_t *v28; // rax
  __int64 v29; // rdx
  _QWORD *v30; // rcx
  unsigned int v31; // eax
  int v32; // edx
  __int64 v33; // rax
  __int64 v34; // rdx
  __int64 v35; // r12
  __int64 v36; // rax
  wchar_t *v37; // rax
  _QWORD *v38; // rax
  __int64 v39; // r13
  int v40; // r15d
  wchar_t *v41; // rax
  __int64 v42; // rdx
  wchar_t **v43; // r12
  const struct std::nothrow_t *v44; // rdx
  struct Windows::Rtl::IPoolAllocator *v45; // rcx
  __int64 v46; // r14
  wchar_t *v47; // rax
  const struct std::nothrow_t *v48; // rdx
  WCHAR *v49; // rcx
  struct ActionList *v50; // rax
  __int64 v51; // r14
  __int64 v52; // r12
  __int64 v53; // r13
  __int64 v54; // rax
  _QWORD *v55; // r12
  unsigned __int64 v56; // r8
  __int64 v57; // rax
  _QWORD *v58; // rax
  __int128 v59; // xmm6
  __int64 v60; // rcx
  __int64 v61; // rcx
  int v62; // esi
  __int64 v63; // rdx
  __int64 v64; // r8
  __int64 v65; // r9
  struct Windows::Rtl::IPoolAllocator *v66; // rcx
  __int64 v67; // r14
  wchar_t *v68; // rax
  int CabFile; // eax
  __int64 v70; // rdx
  __int64 v71; // rcx
  unsigned int v72; // r8d
  int v73; // eax
  __int64 v74; // rax
  unsigned int v75; // r8d
  __int64 v76; // rax
  __int64 v77; // rdx
  __int64 v78; // r8
  __int64 v79; // r9
  __int64 v80; // rax
  _OWORD *Path; // rax
  BOOL v82; // r14d
  __int64 v83; // r8
  int v84; // ebx
  int v85; // edi
  __int64 v86; // rdx
  wchar_t *v87; // rax
  wchar_t *v88; // rax
  _QWORD *v89; // r12
  _QWORD *v90; // r14
  const struct std::nothrow_t *v91; // rdx
  void *v92; // rcx
  __int64 v93; // rdx
  const struct std::nothrow_t *v94; // rdx
  const struct std::nothrow_t *v95; // rdx
  void *v96; // rcx
  __int64 v97; // rdx
  signed int LastError; // esi
  unsigned int v99; // eax
  const struct std::nothrow_t *v100; // rdx
  const struct std::nothrow_t *v101; // rdx
  __int64 v102; // rdx
  __int64 v103; // rdx
  signed int v104; // ebx
  unsigned int v105; // eax
  __int64 v106; // rdx
  const struct std::nothrow_t *v107; // rdx
  const struct std::nothrow_t *v108; // rdx
  const struct std::nothrow_t *v109; // rdx
  int v110; // eax
  struct ActionList *v111; // rax
  unsigned int bIgnoreCase; // [rsp+28h] [rbp-E0h]
  unsigned int v113[2]; // [rsp+38h] [rbp-D0h] BYREF
  HINSTANCE v114; // [rsp+40h] [rbp-C8h] BYREF
  __int64 v115; // [rsp+48h] [rbp-C0h]
  __int64 v116; // [rsp+50h] [rbp-B8h] BYREF
  __int64 v117; // [rsp+58h] [rbp-B0h] BYREF
  CActionListCreator *v118; // [rsp+60h] [rbp-A8h]
  wchar_t *Str; // [rsp+68h] [rbp-A0h] BYREF
  _QWORD v120[5]; // [rsp+70h] [rbp-98h] BYREF
  __int64 v121; // [rsp+98h] [rbp-70h]
  __int64 v122; // [rsp+A0h] [rbp-68h]
  _OWORD v123[2]; // [rsp+A8h] [rbp-60h] BYREF
  __int64 v124; // [rsp+C8h] [rbp-40h]
  struct ActionList **v125; // [rsp+D0h] [rbp-38h]
  __int64 *v126; // [rsp+D8h] [rbp-30h]
  __int64 v127; // [rsp+E0h] [rbp-28h]
  _QWORD v128[2]; // [rsp+E8h] [rbp-20h] BYREF
  _QWORD v129[2]; // [rsp+F8h] [rbp-10h] BYREF
  int v130[4]; // [rsp+108h] [rbp+0h] BYREF
  __int64 v131; // [rsp+118h] [rbp+10h]
  __int64 v132; // [rsp+120h] [rbp+18h]
  _BYTE v133[32]; // [rsp+128h] [rbp+20h] BYREF
  LPCWSTR lpExistingFileName; // [rsp+148h] [rbp+40h] BYREF
  int v135; // [rsp+150h] [rbp+48h] BYREF
  wchar_t *v136; // [rsp+158h] [rbp+50h] BYREF
  wchar_t *v137; // [rsp+160h] [rbp+58h] BYREF
  wchar_t *v138; // [rsp+168h] [rbp+60h] BYREF
  LPCWSTR lpFileName; // [rsp+170h] [rbp+68h] BYREF
  _QWORD *v140; // [rsp+178h] [rbp+70h] BYREF
  __int64 v141; // [rsp+180h] [rbp+78h]
  __int128 v142; // [rsp+188h] [rbp+80h] BYREF
  __int64 v143; // [rsp+198h] [rbp+90h]
  __int64 v144; // [rsp+1A0h] [rbp+98h]
  __int128 v145; // [rsp+1A8h] [rbp+A0h] BYREF
  __int64 v146; // [rsp+1B8h] [rbp+B0h]
  struct _WIN32_FIND_DATAW FindFileData; // [rsp+1C8h] [rbp+C0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+480h] [rbp+378h]

  v132 = -2;
  v125 = a2;
  v6 = this;
  v118 = this;
  lpExistingFileName = a4;
  v7 = a5;
  v120[0] = a5;
  v138 = 0;
  v136 = 0;
  v8 = 0;
  v117 = 0;
  v137 = 0;
  v9 = 0;
  v116 = 0;
  v10 = 0;
  Str = 0;
  v11 = 0;
  v114 = 0;
  v142 = 0;
  v143 = 0;
  v144 = 7;
  LOWORD(v142) = 0;
  if ( *(_QWORD *)this )
    __debugbreak();
  *(_QWORD *)this = *a2;
  *a2 = 0;
  LogAdapter::TraceInfo<>("arbiter: Express download resumed");
  v12 = SczAllocFromSz(&v138, a3);
  Directory = v12;
  if ( v12 < 0 )
  {
    v135 = v12;
    if ( *(_QWORD *)&LogAdapter::g_Logger )
    {
      LogAdapter::Logger::LogNumObjects<>(
        *(__int64 *)&LogAdapter::g_Logger,
        0,
        3,
        (struct Windows::Rtl::IRtlFormattedOutputStream *)"Failed to allocate memory");
      v120[0] = &v135;
      LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
        *(__int64 *)&LogAdapter::g_Logger,
        1,
        3,
        (struct Windows::Rtl::IRtlFormattedOutputStream *)": {}",
        (__int64)v120);
    }
    v14 = 4382;
LABEL_7:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v14,
      (unsigned int)"onecore\\base\\servicing\\arbiter\\cactionlistcreator.cpp",
      (const char *)(unsigned int)Directory,
      bIgnoreCase);
    std::wstring::~wstring(&v142);
    if ( v137 )
    {
      operator delete(v137 - 4, v15);
      v137 = 0;
    }
LABEL_9:
    if ( v136 )
    {
      operator delete(v136 - 4, v15);
      v136 = 0;
    }
    goto LABEL_11;
  }
  v17 = SczEnsureBackslashTerminated(&v138);
  Directory = v17;
  if ( v17 < 0 )
  {
    v135 = v17;
    if ( *(_QWORD *)&LogAdapter::g_Logger )
    {
      LogAdapter::Logger::LogNumObjects<>(
        *(__int64 *)&LogAdapter::g_Logger,
        0,
        3,
        (struct Windows::Rtl::IRtlFormattedOutputStream *)"Failed to allocate memory");
      v120[0] = &v135;
      LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
        *(__int64 *)&LogAdapter::g_Logger,
        1,
        3,
        (struct Windows::Rtl::IRtlFormattedOutputStream *)": {}",
        (__int64)v120);
    }
    v14 = 4384;
    goto LABEL_7;
  }
  v18 = SczAllocFromSz(&v136, v138);
  Directory = v18;
  if ( v18 < 0 )
  {
    v135 = v18;
    if ( *(_QWORD *)&LogAdapter::g_Logger )
    {
      LogAdapter::Logger::LogNumObjects<>(
        *(__int64 *)&LogAdapter::g_Logger,
        0,
        3,
        (struct Windows::Rtl::IRtlFormattedOutputStream *)"Failed to allocate memory");
      v120[0] = &v135;
      LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
        *(__int64 *)&LogAdapter::g_Logger,
        1,
        3,
        (struct Windows::Rtl::IRtlFormattedOutputStream *)": {}",
        (__int64)v120);
    }
    v14 = 4386;
    goto LABEL_7;
  }
  v19 = -1;
  do
    ++v19;
  while ( v138[v19] );
  v121 = v19;
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_ArbiterMetadataContainer>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_ArbiterMetadataContainer>::GetImpl'::`2'::impl)
    && (unsigned __int8)IsMetadataContainerSupported(*(unsigned int *)(*(_QWORD *)v6 + 52LL), v20, v21, 0) )
  {
    v22 = *(_QWORD *)(*(_QWORD *)v6 + 392LL);
    v23 = v22 + 168LL * *(_QWORD *)(*(_QWORD *)v6 + 376LL);
    while ( v22 != v23 )
    {
      if ( *(_DWORD *)(v22 + 120) )
      {
        v24 = *(_QWORD *)(v22 + 112);
        v25 = 0;
        v26 = v24 + 184LL * *(unsigned int *)(v22 + 120);
        v122 = v26;
        if ( v24 == v26 )
        {
          v6 = v118;
        }
        else
        {
          do
          {
            if ( *(_DWORD *)(v24 + 8) == 2 && *(_QWORD *)(v24 + 24) )
            {
              v27 = DuplicateNullTerminatedString(
                      (struct Windows::Rtl::IPoolAllocator *)(*(_QWORD *)v118 + 264LL),
                      *(const wchar_t **)(v24 + 24));
              *(_QWORD *)(v24 + 104) = v27;
              if ( !v27 )
              {
                v29 = 4414;
                goto LABEL_45;
              }
              v25 = v24;
              v26 = v122;
            }
            v24 += 184;
          }
          while ( v24 != v26 );
          v6 = v118;
          if ( v25 )
          {
            v28 = DuplicateNullTerminatedString(
                    (struct Windows::Rtl::IPoolAllocator *)(*(_QWORD *)v118 + 264LL),
                    *(const wchar_t **)(v25 + 104));
            *(_QWORD *)(v22 + 80) = v28;
            if ( !v28 )
            {
              v29 = 4422;
LABEL_45:
              Directory = -2147024882;
              wil::details::in1diag3::Return_Hr(
                retaddr,
                (void *)v29,
                (unsigned int)"onecore\\base\\servicing\\arbiter\\cactionlistcreator.cpp",
                (const char *)0x8007000ELL,
                bIgnoreCase);
              std::wstring::~wstring(&v142);
              if ( v137 )
              {
                operator delete(v137 - 4, v15);
                v137 = 0;
              }
              if ( v136 )
              {
                operator delete(v136 - 4, v15);
                v136 = 0;
              }
              goto LABEL_11;
            }
          }
        }
      }
      v22 += 168;
    }
    v7 = (const wchar_t *)v120[0];
  }
  LOBYTE(v115) = 0;
  v30 = *(_QWORD **)v6;
  v31 = *(_DWORD *)(*(_QWORD *)v6 + 52LL);
  v32 = 4505604;
  if ( v31 <= 0x16 && _bittest(&v32, v31) )
  {
    v33 = v30[49];
    v34 = v33 + 168LL * v30[47];
    while ( v33 != v34 )
    {
      if ( *(_DWORD *)(v33 + 96) == 4 )
      {
        LOBYTE(v115) = 1;
        break;
      }
      v33 += 168;
    }
  }
  v35 = v30[41];
  v122 = v35;
  v36 = v35 + 168LL * v30[39];
  *(_QWORD *)v113 = v36;
  if ( v35 == v36 )
  {
LABEL_336:
    if ( lpExistingFileName )
    {
      v110 = CActionListCreator::Save((__int64)v6, 1, lpExistingFileName);
      Directory = v110;
      if ( v110 < 0 )
      {
        v135 = v110;
        if ( *(_QWORD *)&LogAdapter::g_Logger )
        {
          LogAdapter::Logger::LogNumObjects<Windows::AutoGenericHandle<wchar_t *,0,&void Windows::Detail::CloseWithCoTaskMemFree<wchar_t>(wchar_t *)>>(
            *(__int64 *)&LogAdapter::g_Logger,
            0,
            3,
            (struct Windows::Rtl::IRtlFormattedOutputStream *)"Failed to save to actionlist file: {0}",
            (__int64)&lpExistingFileName);
          *(_QWORD *)v113 = &v135;
          LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
            *(__int64 *)&LogAdapter::g_Logger,
            1,
            3,
            (struct Windows::Rtl::IRtlFormattedOutputStream *)": {}",
            (__int64)v113);
        }
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x1285,
          (unsigned int)"onecore\\base\\servicing\\arbiter\\cactionlistcreator.cpp",
          (const char *)(unsigned int)Directory,
          bIgnoreCase);
LABEL_341:
        std::wstring::~wstring(&v142);
        CIUClient::~CIUClient((CIUClient *)&v114);
        AutoScz::~AutoScz((AutoScz *)&Str);
        AutoScz::~AutoScz((AutoScz *)&v116);
        AutoScz::~AutoScz((AutoScz *)&v137);
        AutoScz::~AutoScz((AutoScz *)&v117);
        AutoScz::~AutoScz((AutoScz *)&v136);
        goto LABEL_342;
      }
    }
    v111 = *(struct ActionList **)v6;
    *(_QWORD *)v6 = 0;
    *v125 = v111;
    std::wstring::~wstring(&v142);
    CIUClient::~CIUClient((CIUClient *)&v114);
    AutoScz::~AutoScz((AutoScz *)&Str);
    AutoScz::~AutoScz((AutoScz *)&v116);
    AutoScz::~AutoScz((AutoScz *)&v137);
    AutoScz::~AutoScz((AutoScz *)&v117);
    AutoScz::~AutoScz((AutoScz *)&v136);
    AutoScz::~AutoScz((AutoScz *)&v138);
    return 0;
  }
  while ( 1 )
  {
    if ( *(_DWORD *)(v35 + 104) != 2 )
      goto LABEL_163;
    if ( *(_DWORD *)(*(_QWORD *)v6 + 52LL) == 8 )
    {
      v37 = DuplicateNullTerminatedString((struct Windows::Rtl::IPoolAllocator *)(*(_QWORD *)v6 + 264LL), v7);
      *(_QWORD *)(v35 + 128) = v37;
      if ( !v37 )
      {
        Directory = -2147024882;
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x1168,
          (unsigned int)"onecore\\base\\servicing\\arbiter\\cactionlistcreator.cpp",
          (const char *)0x8007000ELL,
          bIgnoreCase);
        std::wstring::~wstring(&v142);
        if ( v11 && !FreeLibrary(v11) )
        {
          GetLastError();
          __fastfail(7u);
        }
        if ( v10 )
          operator delete(v10 - 4, v15);
        if ( v9 )
          operator delete((void *)(v9 - 8), v15);
        if ( v137 )
        {
          operator delete(v137 - 4, v15);
          v137 = 0;
        }
        if ( v8 )
          operator delete((void *)(v8 - 8), v15);
        goto LABEL_9;
      }
    }
    v140 = 0;
    v141 = 0;
    v38 = operator new(0x40u);
    *v38 = v38;
    v38[1] = v38;
    v38[2] = v38;
    *((_WORD *)v38 + 12) = 257;
    v140 = v38;
    v145 = 0;
    v146 = 0;
    v39 = *(_QWORD *)(v35 + 112);
    v124 = v39 + 184LL * *(unsigned int *)(v35 + 120);
    if ( v39 != v124 )
      break;
LABEL_88:
    v50 = *(struct ActionList **)v6;
    v51 = *(_QWORD *)(*(_QWORD *)v6 + 712LL);
    v52 = v51 + 24LL * *((_QWORD *)v50 + 87);
    if ( v51 != v52 )
    {
      v53 = v122;
      while ( CompareStringOrdinal(*(LPCWCH *)(v53 + 24), -1, *(LPCWCH *)v51, -1, 1) != 2 )
      {
        v51 += 24;
        if ( v51 == v52 )
          goto LABEL_156;
      }
      *(_DWORD *)(v51 + 16) = 1;
    }
LABEL_156:
    if ( (_BYTE)v115 )
    {
      v89 = (_QWORD *)*((_QWORD *)&v145 + 1);
      v90 = (_QWORD *)v145;
      if ( (_QWORD)v145 != *((_QWORD *)&v145 + 1) )
      {
        if ( v143 )
        {
          while ( v90 != v89 )
          {
            LogAdapter::TraceInfo<std::wstring,std::wstring>(
              "Arbiter : Copying metadata contents from: {0} to {1}",
              v90,
              &v142);
            std::filesystem::path::path((__int64)v133, &v142);
            std::filesystem::path::path((__int64)v123, v90);
            std::filesystem::copy(v123, v133);
            std::wstring::~wstring(v123);
            std::wstring::~wstring(v133);
            v90 += 4;
          }
        }
      }
    }
    std::vector<UUPInstallPlan::UUPProduct>::_Tidy(&v145);
    std::_Tree<std::_Tset_traits<std::wstring,WstringCaseInsensitiveCompare,std::allocator<std::wstring>,0>>::~_Tree<std::_Tset_traits<std::wstring,WstringCaseInsensitiveCompare,std::allocator<std::wstring>,0>>(&v140);
    v6 = v118;
    v35 = v122;
    v36 = *(_QWORD *)v113;
LABEL_163:
    v35 += 168;
    v122 = v35;
    if ( v35 == v36 )
      goto LABEL_336;
    v7 = (const wchar_t *)v120[0];
  }
  while ( 1 )
  {
    v138[v121] = 0;
    v40 = SczAllocFromSz(&Str, *(_QWORD *)(v39 + 24));
    if ( v40 < 0 )
    {
      v135 = v40;
      if ( *(_QWORD *)&LogAdapter::g_Logger )
      {
        LogAdapter::Logger::LogNumObjects<>(
          *(__int64 *)&LogAdapter::g_Logger,
          0,
          3,
          (struct Windows::Rtl::IRtlFormattedOutputStream *)"Failed to allocate memory");
        *(_QWORD *)v113 = &v135;
        LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
          *(__int64 *)&LogAdapter::g_Logger,
          1,
          3,
          (struct Windows::Rtl::IRtlFormattedOutputStream *)": {}",
          (__int64)v113);
      }
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x1172,
        (unsigned int)"onecore\\base\\servicing\\arbiter\\cactionlistcreator.cpp",
        (const char *)(unsigned int)v40,
        bIgnoreCase);
      std::vector<UUPInstallPlan::UUPProduct>::_Tidy(&v145);
      std::_Tree<std::_Tset_traits<std::wstring,WstringCaseInsensitiveCompare,std::allocator<std::wstring>,0>>::~_Tree<std::_Tset_traits<std::wstring,WstringCaseInsensitiveCompare,std::allocator<std::wstring>,0>>(&v140);
      std::wstring::~wstring(&v142);
      if ( v11 && !FreeLibrary(v11) )
      {
        GetLastError();
        __fastfail(7u);
      }
      if ( Str )
        operator delete(Str - 4, v109);
      if ( v9 )
        operator delete((void *)(v9 - 8), v109);
      if ( v137 )
      {
        operator delete(v137 - 4, v109);
        v137 = 0;
      }
      if ( v8 )
        operator delete((void *)(v8 - 8), v109);
      if ( v136 )
      {
        operator delete(v136 - 4, v109);
        v136 = 0;
      }
      if ( v138 )
        operator delete(v138 - 4, v109);
      return (unsigned int)v40;
    }
    v10 = Str;
    v41 = wcsrchr(Str, 0x2Eu);
    if ( v41 )
      *v41 = 0;
    Directory = SczAllocConcatSz(&v138, v10);
    if ( Directory < 0 )
      break;
    lpFileName = 0;
    Directory = SczAllocFormatted(&lpFileName, L"%ws\\%ws", v138, L"express.psf.cix.xml");
    if ( Directory < 0 )
    {
      v135 = Directory;
      if ( *(_QWORD *)&LogAdapter::g_Logger )
      {
        LogAdapter::Logger::LogNumObjects<>(
          *(__int64 *)&LogAdapter::g_Logger,
          0,
          3,
          (struct Windows::Rtl::IRtlFormattedOutputStream *)"Failed to allocate memory");
        *(_QWORD *)v113 = &v135;
        LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
          *(__int64 *)&LogAdapter::g_Logger,
          1,
          3,
          (struct Windows::Rtl::IRtlFormattedOutputStream *)": {}",
          (__int64)v113);
      }
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x118B,
        (unsigned int)"onecore\\base\\servicing\\arbiter\\cactionlistcreator.cpp",
        (const char *)(unsigned int)Directory,
        bIgnoreCase);
      goto LABEL_172;
    }
    v43 = (wchar_t **)(v39 + 120);
    if ( *(_QWORD *)(v39 + 120) )
    {
      LogAdapter::TraceInfo<wchar_t const *,wchar_t *>(
        "Skipping previously processed express payload file: {0} for express cab: {1}",
        v39 + 120,
        v39 + 16);
      if ( lpFileName )
        operator delete((void *)(lpFileName - 4), v44);
      goto LABEL_87;
    }
    if ( (unsigned int)DoesFileExist(lpFileName, v42) )
    {
      v120[1] = 0;
      Directory = SczAllocFormatted(&v120[1], L"%ws\\%ws", &v138[v121], L"express.psf.cix.xml");
      if ( Directory < 0 )
      {
        v135 = Directory;
        if ( *(_QWORD *)&LogAdapter::g_Logger )
        {
          LogAdapter::Logger::LogNumObjects<>(
            *(__int64 *)&LogAdapter::g_Logger,
            0,
            3,
            (struct Windows::Rtl::IRtlFormattedOutputStream *)"Failed to allocate memory");
          *(_QWORD *)v113 = &v135;
          LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
            *(__int64 *)&LogAdapter::g_Logger,
            1,
            3,
            (struct Windows::Rtl::IRtlFormattedOutputStream *)": {}",
            (__int64)v113);
        }
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x119D,
          (unsigned int)"onecore\\base\\servicing\\arbiter\\cactionlistcreator.cpp",
          (const char *)(unsigned int)Directory,
          bIgnoreCase);
        if ( v120[1] )
        {
          v92 = (void *)(v120[1] - 8LL);
LABEL_171:
          operator delete(v92, v91);
        }
LABEL_172:
        if ( lpFileName )
        {
          operator delete((void *)(lpFileName - 4), v91);
          lpFileName = 0;
        }
        goto LABEL_308;
      }
      v45 = (struct Windows::Rtl::IPoolAllocator *)(*(_QWORD *)v6 + 264LL);
      v46 = v120[1];
      v47 = DuplicateNullTerminatedString(v45, (const wchar_t *)v120[1]);
      *(_QWORD *)(v39 + 120) = v47;
      if ( !v47 )
      {
        Directory = -2147024882;
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x119F,
          (unsigned int)"onecore\\base\\servicing\\arbiter\\cactionlistcreator.cpp",
          (const char *)0x8007000ELL,
          bIgnoreCase);
        if ( v46 )
        {
          v92 = (void *)(v46 - 8);
          goto LABEL_171;
        }
        goto LABEL_172;
      }
      LogAdapter::TraceInfo<wchar_t const *,wchar_t *>(
        "Skipping previously processed express payload file: {0} for express cab: {1}",
        &lpFileName,
        v39 + 16);
      if ( v46 )
        operator delete((void *)(v46 - 8), v48);
      if ( lpFileName )
      {
        v49 = (WCHAR *)(lpFileName - 4);
        goto LABEL_85;
      }
      goto LABEL_86;
    }
    if ( lpFileName )
      operator delete((void *)(lpFileName - 4), 0);
    v120[1] = v10;
    if ( !std::_Tree<std::_Tset_traits<std::wstring,WstringCaseInsensitiveCompare,std::allocator<std::wstring>,0>>::count<wchar_t *,WstringCaseInsensitiveCompare,0>(
            (__int64 *)&v140,
            &v120[1]) )
    {
      v120[1] = v140;
      v126 = (__int64 *)&v140;
      v127 = 0;
      v54 = std::_Allocate<16,std::_Default_allocate_traits>(64);
      v55 = (_QWORD *)v54;
      v127 = v54;
      *(_OWORD *)(v54 + 32) = 0;
      *(_QWORD *)(v54 + 48) = 0;
      *(_QWORD *)(v54 + 56) = 0;
      v56 = -1;
      do
        ++v56;
      while ( v10[v56] );
      std::wstring::_Construct<1,wchar_t const *>(v54 + 32, v10, v56);
      v57 = v120[1];
      *v55 = v120[1];
      v55[1] = v57;
      v55[2] = v57;
      *((_WORD *)v55 + 12) = 0;
      v58 = std::_Tree<std::_Tset_traits<std::wstring,WstringCaseInsensitiveCompare,std::allocator<std::wstring>,0>>::_Find_lower_bound<std::wstring>(
              (__int64)&v140,
              v130,
              v55 + 4);
      v59 = *(_OWORD *)v58;
      if ( std::_Tree<std::_Tset_traits<std::wstring,WstringCaseInsensitiveCompare,std::allocator<std::wstring>,0>>::_Lower_bound_duplicate<std::wstring>(
             v60,
             v58[2],
             v55 + 4) )
      {
        std::wstring::~wstring(v55 + 4);
        operator delete(v55, (const struct std::nothrow_t *)0x40);
      }
      else
      {
        if ( v141 == 0x3FFFFFFFFFFFFFFLL )
          std::_Throw_tree_length_error();
        v127 = 0;
        *(_OWORD *)&v120[1] = v59;
        std::_Tree_val<std::_Tree_simple_types<std::wstring_view>>::_Insert_node(&v140, &v120[1], v55);
      }
      Directory = RecursiveRemoveDirectory(v61, v138);
      if ( Directory < 0 )
      {
        v135 = Directory;
        if ( *(_QWORD *)&LogAdapter::g_Logger )
        {
          LogAdapter::Logger::LogNumObjects<AutoScz>(
            *(_QWORD *)&LogAdapter::g_Logger,
            0,
            3,
            "Unable to delete directory {0}",
            &v138);
          *(_QWORD *)v113 = &v135;
          LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
            *(__int64 *)&LogAdapter::g_Logger,
            1,
            3,
            (struct Windows::Rtl::IRtlFormattedOutputStream *)": {}",
            (__int64)v113);
        }
        v97 = 4531;
        goto LABEL_307;
      }
      Directory = RecursivelyCreateDirectory(v138, 0);
      if ( Directory < 0 )
      {
        v135 = Directory;
        if ( *(_QWORD *)&LogAdapter::g_Logger )
        {
          LogAdapter::Logger::LogNumObjects<AutoScz>(
            *(_QWORD *)&LogAdapter::g_Logger,
            0,
            3,
            "Failed creating directory {0}",
            &v138);
          *(_QWORD *)v113 = &v135;
          LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
            *(__int64 *)&LogAdapter::g_Logger,
            1,
            3,
            (struct Windows::Rtl::IRtlFormattedOutputStream *)": {}",
            (__int64)v113);
        }
        v97 = 4537;
        goto LABEL_307;
      }
      v136[v121] = 0;
      Directory = SczAllocConcatSz(&v136, *(_QWORD *)(v39 + 24));
      if ( Directory < 0 )
      {
        v135 = Directory;
        if ( *(_QWORD *)&LogAdapter::g_Logger )
        {
          LogAdapter::Logger::LogNumObjects<>(
            *(__int64 *)&LogAdapter::g_Logger,
            0,
            3,
            (struct Windows::Rtl::IRtlFormattedOutputStream *)"Failed to allocate memory");
          *(_QWORD *)v113 = &v135;
          LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
            *(__int64 *)&LogAdapter::g_Logger,
            1,
            3,
            (struct Windows::Rtl::IRtlFormattedOutputStream *)": {}",
            (__int64)v113);
        }
        v97 = 4544;
        goto LABEL_307;
      }
      if ( !v11 )
      {
        v62 = DpxLoad(&v114);
        if ( v62 < 0 )
        {
          v135 = v62;
          if ( *(_QWORD *)&LogAdapter::g_Logger )
          {
            LogAdapter::Logger::LogNumObjects<>(
              *(__int64 *)&LogAdapter::g_Logger,
              0,
              3,
              (struct Windows::Rtl::IRtlFormattedOutputStream *)"Failed to load dpx.dll");
            *(_QWORD *)v113 = &v135;
            LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
              *(__int64 *)&LogAdapter::g_Logger,
              1,
              3,
              (struct Windows::Rtl::IRtlFormattedOutputStream *)": {}",
              (__int64)v113);
          }
          v93 = 4548;
          goto LABEL_177;
        }
        v11 = v114;
      }
      if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_ArbiterMetadataContainer>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_ArbiterMetadataContainer>::GetImpl'::`2'::impl)
        && (unsigned __int8)IsMetadataContainerSupported(*(unsigned int *)(*(_QWORD *)v6 + 52LL), v63, v64, v65)
        && *(_DWORD *)(v39 + 128) != 1 )
      {
        v120[1] = 0;
        Directory = SczAllocFormatted(&v120[1], L"%ws\\%ws", &v138[v121], L"express.psf.cix.xml");
        if ( Directory < 0 )
        {
          v135 = Directory;
          if ( *(_QWORD *)&LogAdapter::g_Logger )
          {
            LogAdapter::Logger::LogNumObjects<>(
              *(__int64 *)&LogAdapter::g_Logger,
              0,
              3,
              (struct Windows::Rtl::IRtlFormattedOutputStream *)"Failed to allocate memory");
            *(_QWORD *)v113 = &v135;
            LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
              *(__int64 *)&LogAdapter::g_Logger,
              1,
              3,
              (struct Windows::Rtl::IRtlFormattedOutputStream *)": {}",
              (__int64)v113);
          }
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x11D6,
            (unsigned int)"onecore\\base\\servicing\\arbiter\\cactionlistcreator.cpp",
            (const char *)(unsigned int)Directory,
            bIgnoreCase);
          if ( !v120[1] )
            goto LABEL_308;
          v96 = (void *)(v120[1] - 8LL);
LABEL_193:
          operator delete(v96, v95);
          goto LABEL_308;
        }
        v66 = (struct Windows::Rtl::IPoolAllocator *)(*(_QWORD *)v6 + 264LL);
        v67 = v120[1];
        v68 = DuplicateNullTerminatedString(v66, (const wchar_t *)v120[1]);
        *(_QWORD *)(v39 + 120) = v68;
        if ( !v68 )
        {
          Directory = -2147024882;
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x11D8,
            (unsigned int)"onecore\\base\\servicing\\arbiter\\cactionlistcreator.cpp",
            (const char *)0x8007000ELL,
            bIgnoreCase);
          if ( !v67 )
            goto LABEL_308;
          v96 = (void *)(v67 - 8);
          goto LABEL_193;
        }
        if ( v67 )
        {
          v49 = (WCHAR *)(v67 - 8);
LABEL_85:
          operator delete(v49, v48);
        }
LABEL_86:
        v6 = v118;
        goto LABEL_87;
      }
      LogAdapter::TraceInfo<wchar_t const *>("Expanding express cab: {0}", v39 + 16);
      CabFile = ExtractCabFile(v136, v138, 1);
      if ( CabFile < 0 )
      {
        v135 = CabFile;
        if ( *(_QWORD *)&LogAdapter::g_Logger )
        {
          LogAdapter::Logger::LogPartial<AutoScz,AutoScz>(
            v71,
            v70,
            "Failed to extract cab file: {0} in directory {1}. Trying to extract WIM",
            &v136,
            &v138);
          v120[1] = &v135;
          LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
            *(__int64 *)&LogAdapter::g_Logger,
            1,
            1,
            (struct Windows::Rtl::IRtlFormattedOutputStream *)": {0}",
            (__int64)&v120[1]);
        }
        Directory = CbsEsdExtractAllFiles(v136, v138);
        if ( Directory < 0 )
        {
          v135 = Directory;
          if ( *(_QWORD *)&LogAdapter::g_Logger )
          {
            LogAdapter::Logger::LogNumObjects<AutoScz>(
              *(_QWORD *)&LogAdapter::g_Logger,
              0,
              3,
              "Failed to extract files from wim {0}.",
              &v136);
            *(_QWORD *)v113 = &v135;
            LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
              *(__int64 *)&LogAdapter::g_Logger,
              1,
              3,
              (struct Windows::Rtl::IRtlFormattedOutputStream *)": {}",
              (__int64)v113);
          }
          v97 = 4591;
          goto LABEL_307;
        }
      }
      v72 = *(_DWORD *)(*(_QWORD *)v6 + 52LL);
      if ( v72 <= 0x16 )
      {
        v73 = 4505604;
        if ( _bittest(&v73, v72) )
        {
          if ( *(_DWORD *)(v122 + 88) == 6 )
          {
            v74 = ActionTypeToLUTF8String(v133, *(unsigned int *)(v122 + 96));
            *(_OWORD *)&v120[1] = *(_OWORD *)v74;
            v120[3] = *(_QWORD *)(v74 + 16);
            v76 = OperationTypeToLUTF8String(v123, v75);
            *(_OWORD *)v130 = *(_OWORD *)v76;
            v131 = *(_QWORD *)(v76 + 16);
            if ( *(_QWORD *)&LogAdapter::g_Logger )
              LogAdapter::Logger::LogNumObjects<_LUTF8_STRING,_LUTF8_STRING>(
                *(__int64 *)&LogAdapter::g_Logger,
                v77,
                v78,
                v79,
                (__int64)v130,
                (__int64)&v120[1]);
            v128[0] = L"ActionList.xml";
            v128[1] = 14;
            v129[0] = v138;
            v80 = -1;
            do
              ++v80;
            while ( v138[v80] );
            v129[1] = v80;
            Path = CreatePath(v123, (__int64)v129, v128);
            if ( *((_QWORD *)Path + 3) > 7u )
              Path = *(_OWORD **)Path;
            v82 = CopyFileW(lpExistingFileName, (LPCWSTR)Path, 0);
            std::wstring::~wstring(v123);
            if ( !v82 )
            {
              LastError = GetLastError();
              if ( *(_QWORD *)&LogAdapter::g_Logger )
              {
                LogAdapter::Logger::LogNumObjects<>(
                  *(__int64 *)&LogAdapter::g_Logger,
                  0,
                  3,
                  (struct Windows::Rtl::IRtlFormattedOutputStream *)"Failed to copy ActionList to metadata folder.");
                if ( LastError > 0 )
                  v99 = (unsigned __int16)LastError | 0x80070000;
                else
                  v99 = LastError;
                v135 = v99;
                *(_QWORD *)v113 = &v135;
                LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
                  *(__int64 *)&LogAdapter::g_Logger,
                  1,
                  3,
                  (struct Windows::Rtl::IRtlFormattedOutputStream *)": {0}",
                  (__int64)v113);
              }
              if ( LastError )
              {
                v62 = wil::details::in1diag3::Return_Win32(
                        retaddr,
                        (void *)0x1205,
                        (unsigned int)"onecore\\base\\servicing\\arbiter\\cactionlistcreator.cpp",
                        (const char *)(unsigned int)LastError,
                        bIgnoreCase);
                goto LABEL_178;
              }
              std::vector<UUPInstallPlan::UUPProduct>::_Tidy(&v145);
              std::_Tree<std::_Tset_traits<std::wstring,WstringCaseInsensitiveCompare,std::allocator<std::wstring>,0>>::~_Tree<std::_Tset_traits<std::wstring,WstringCaseInsensitiveCompare,std::allocator<std::wstring>,0>>(&v140);
              std::wstring::~wstring(&v142);
              CIUClient::~CIUClient((CIUClient *)&v114);
              if ( v10 )
                operator delete(v10 - 4, v100);
              if ( v9 )
                operator delete((void *)(v9 - 8), v100);
              if ( v137 )
              {
                operator delete(v137 - 4, v100);
                v137 = 0;
              }
              if ( v8 )
                operator delete((void *)(v8 - 8), v100);
              if ( v136 )
              {
                operator delete(v136 - 4, v100);
                v136 = 0;
              }
              if ( v138 )
                operator delete(v138 - 4, v100);
              return 0;
            }
            if ( *(_QWORD *)(v39 + 176) )
            {
              v120[1] = v10;
              if ( (unsigned __int8)Windows::StringUtil::AreStringsEqualByOrdinalCaseInvariantNonReflexive<wchar_t *,wchar_t *>(&v120[1]) )
              {
                if ( v143 )
                {
                  v62 = -2147418113;
                  v135 = -2147418113;
                  if ( *(_QWORD *)&LogAdapter::g_Logger )
                  {
                    LogAdapter::Logger::LogNumObjects<>(
                      *(__int64 *)&LogAdapter::g_Logger,
                      0,
                      3,
                      (struct Windows::Rtl::IRtlFormattedOutputStream *)"ExpressPackageTargetDirectory already set");
                    *(_QWORD *)v113 = &v135;
                    LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
                      *(__int64 *)&LogAdapter::g_Logger,
                      1,
                      3,
                      (struct Windows::Rtl::IRtlFormattedOutputStream *)": {}",
                      (__int64)v113);
                  }
                  v93 = 4624;
LABEL_177:
                  wil::details::in1diag3::Return_Hr(
                    retaddr,
                    (void *)v93,
                    (unsigned int)"onecore\\base\\servicing\\arbiter\\cactionlistcreator.cpp",
                    (const char *)(unsigned int)v62,
                    bIgnoreCase);
LABEL_178:
                  std::vector<UUPInstallPlan::UUPProduct>::_Tidy(&v145);
                  std::_Tree<std::_Tset_traits<std::wstring,WstringCaseInsensitiveCompare,std::allocator<std::wstring>,0>>::~_Tree<std::_Tset_traits<std::wstring,WstringCaseInsensitiveCompare,std::allocator<std::wstring>,0>>(&v140);
                  std::wstring::~wstring(&v142);
                  CIUClient::~CIUClient((CIUClient *)&v114);
                  if ( v10 )
                    operator delete(v10 - 4, v94);
                  if ( v9 )
                    operator delete((void *)(v9 - 8), v94);
                  if ( v137 )
                  {
                    operator delete(v137 - 4, v94);
                    v137 = 0;
                  }
                  if ( v8 )
                    operator delete((void *)(v8 - 8), v94);
                  if ( v136 )
                  {
                    operator delete(v136 - 4, v94);
                    v136 = 0;
                  }
                  if ( v138 )
                    operator delete(v138 - 4, v94);
                  return (unsigned int)v62;
                }
                v83 = -1;
                do
                  ++v83;
                while ( v138[v83] );
                std::wstring::_Assign<wchar_t>(&v142);
              }
              else
              {
                std::wstring::wstring(v123, v138);
                std::vector<std::wstring>::push_back(&v145, v123);
                std::wstring::~wstring(v123);
              }
            }
            v6 = v118;
          }
        }
      }
      v43 = (wchar_t **)(v39 + 120);
    }
    v84 = SczAllocFormatted(&v117, L"%ws.cix.xml", *(_QWORD *)(v39 + 72));
    if ( v84 < 0 )
    {
      v135 = v84;
      if ( *(_QWORD *)&LogAdapter::g_Logger )
      {
        LogAdapter::Logger::LogNumObjects<>(
          *(__int64 *)&LogAdapter::g_Logger,
          0,
          3,
          (struct Windows::Rtl::IRtlFormattedOutputStream *)"Failed to allocate memory");
        *(_QWORD *)v113 = &v135;
        LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
          *(__int64 *)&LogAdapter::g_Logger,
          1,
          3,
          (struct Windows::Rtl::IRtlFormattedOutputStream *)": {}",
          (__int64)v113);
      }
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x1220,
        (unsigned int)"onecore\\base\\servicing\\arbiter\\cactionlistcreator.cpp",
        (const char *)(unsigned int)v84,
        bIgnoreCase);
      std::vector<UUPInstallPlan::UUPProduct>::_Tidy(&v145);
      std::_Tree<std::_Tset_traits<std::wstring,WstringCaseInsensitiveCompare,std::allocator<std::wstring>,0>>::~_Tree<std::_Tset_traits<std::wstring,WstringCaseInsensitiveCompare,std::allocator<std::wstring>,0>>(&v140);
      std::wstring::~wstring(&v142);
      CIUClient::~CIUClient((CIUClient *)&v114);
      if ( v10 )
        operator delete(v10 - 4, v108);
      if ( v9 )
        operator delete((void *)(v9 - 8), v108);
      if ( v137 )
      {
        operator delete(v137 - 4, v108);
        v137 = 0;
      }
      if ( v117 )
        operator delete((void *)(v117 - 8), v108);
      if ( v136 )
      {
        operator delete(v136 - 4, v108);
        v136 = 0;
      }
      if ( v138 )
        operator delete(v138 - 4, v108);
      return (unsigned int)v84;
    }
    v8 = v117;
    v85 = SczAllocFormatted(&v116, L"%ws\\%ws", v138, v117);
    if ( v85 < 0 )
    {
      v135 = v85;
      if ( *(_QWORD *)&LogAdapter::g_Logger )
      {
        LogAdapter::Logger::LogNumObjects<>(
          *(__int64 *)&LogAdapter::g_Logger,
          0,
          3,
          (struct Windows::Rtl::IRtlFormattedOutputStream *)"Failed to allocate memory");
        *(_QWORD *)v113 = &v135;
        LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
          *(__int64 *)&LogAdapter::g_Logger,
          1,
          3,
          (struct Windows::Rtl::IRtlFormattedOutputStream *)": {}",
          (__int64)v113);
      }
      v102 = 4646;
      goto LABEL_273;
    }
    if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_ArbiterMetadataContainer>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_ArbiterMetadataContainer>::GetImpl'::`2'::impl)
      && *(_DWORD *)(*(_QWORD *)v6 + 52LL) == 1
      && *(_DWORD *)(v39 + 128) != 1 )
    {
      v85 = SczAllocFormatted(&v137, L"%ws\\%ws", &v138[v121], v8);
      if ( v85 < 0 )
      {
        v135 = v85;
        if ( *(_QWORD *)&LogAdapter::g_Logger )
        {
          LogAdapter::Logger::LogNumObjects<>(
            *(__int64 *)&LogAdapter::g_Logger,
            0,
            3,
            (struct Windows::Rtl::IRtlFormattedOutputStream *)"Failed to allocate memory");
          *(_QWORD *)v113 = &v135;
          LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
            *(__int64 *)&LogAdapter::g_Logger,
            1,
            3,
            (struct Windows::Rtl::IRtlFormattedOutputStream *)": {}",
            (__int64)v113);
        }
        v102 = 4655;
LABEL_273:
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)v102,
          (unsigned int)"onecore\\base\\servicing\\arbiter\\cactionlistcreator.cpp",
          (const char *)(unsigned int)v85,
          bIgnoreCase);
        std::vector<UUPInstallPlan::UUPProduct>::_Tidy(&v145);
        std::_Tree<std::_Tset_traits<std::wstring,WstringCaseInsensitiveCompare,std::allocator<std::wstring>,0>>::~_Tree<std::_Tset_traits<std::wstring,WstringCaseInsensitiveCompare,std::allocator<std::wstring>,0>>(&v140);
        std::wstring::~wstring(&v142);
        CIUClient::~CIUClient((CIUClient *)&v114);
        if ( v10 )
          operator delete(v10 - 4, v107);
        if ( v116 )
          operator delete((void *)(v116 - 8), v107);
        if ( v137 )
        {
          operator delete(v137 - 4, v107);
          v137 = 0;
        }
        if ( v8 )
          operator delete((void *)(v8 - 8), v107);
        if ( v136 )
        {
          operator delete(v136 - 4, v107);
          v136 = 0;
        }
        if ( v138 )
          operator delete(v138 - 4, v107);
        return (unsigned int)v85;
      }
      v87 = DuplicateNullTerminatedString((struct Windows::Rtl::IPoolAllocator *)(*(_QWORD *)v6 + 264LL), v137);
      *v43 = v87;
      if ( !v87 )
      {
        Directory = -2147024882;
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x1232,
          (unsigned int)"onecore\\base\\servicing\\arbiter\\cactionlistcreator.cpp",
          (const char *)0x8007000ELL,
          bIgnoreCase);
        std::vector<UUPInstallPlan::UUPProduct>::_Tidy(&v145);
        std::_Tree<std::_Tset_traits<std::wstring,WstringCaseInsensitiveCompare,std::allocator<std::wstring>,0>>::~_Tree<std::_Tset_traits<std::wstring,WstringCaseInsensitiveCompare,std::allocator<std::wstring>,0>>(&v140);
        std::wstring::~wstring(&v142);
        CIUClient::~CIUClient((CIUClient *)&v114);
        if ( v10 )
          operator delete(v10 - 4, v101);
        if ( v116 )
          operator delete((void *)(v116 - 8), v101);
        if ( v137 )
        {
          operator delete(v137 - 4, v101);
          v137 = 0;
        }
        if ( v8 )
          operator delete((void *)(v8 - 8), v101);
        if ( v136 )
        {
          operator delete(v136 - 4, v101);
          v136 = 0;
        }
        goto LABEL_342;
      }
      v9 = v116;
    }
    else
    {
      v9 = v116;
      if ( !(unsigned int)DoesFileExist(v116, v86) )
      {
        lpFileName = 0;
        v120[1] = 0;
        memset_0(&FindFileData, 0, sizeof(FindFileData));
        Directory = SczAllocFromSz(&lpFileName, v138);
        if ( Directory < 0 )
        {
          v135 = Directory;
          if ( *(_QWORD *)&LogAdapter::g_Logger )
          {
            LogAdapter::Logger::LogNumObjects<>(
              *(__int64 *)&LogAdapter::g_Logger,
              0,
              3,
              (struct Windows::Rtl::IRtlFormattedOutputStream *)"Failed to allocate memory");
            *(_QWORD *)v113 = &v135;
            LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
              *(__int64 *)&LogAdapter::g_Logger,
              1,
              3,
              (struct Windows::Rtl::IRtlFormattedOutputStream *)": {}",
              (__int64)v113);
          }
          v103 = 4678;
          goto LABEL_248;
        }
        Directory = SczAllocConcatSz(&lpFileName, L"\\*.cix.xml");
        if ( Directory < 0 )
        {
          v135 = Directory;
          if ( *(_QWORD *)&LogAdapter::g_Logger )
          {
            LogAdapter::Logger::LogNumObjects<>(
              *(__int64 *)&LogAdapter::g_Logger,
              0,
              3,
              (struct Windows::Rtl::IRtlFormattedOutputStream *)"Failed to allocate memory");
            *(_QWORD *)v113 = &v135;
            LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
              *(__int64 *)&LogAdapter::g_Logger,
              1,
              3,
              (struct Windows::Rtl::IRtlFormattedOutputStream *)": {}",
              (__int64)v113);
          }
          v103 = 4680;
LABEL_248:
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)v103,
            (unsigned int)"onecore\\base\\servicing\\arbiter\\cactionlistcreator.cpp",
            (const char *)(unsigned int)Directory,
            bIgnoreCase);
LABEL_249:
          Windows::AutoGenericHandle<void *,1,&void Windows::Detail::CloseWithFindClose(void *)>::~AutoGenericHandle<void *,1,&void Windows::Detail::CloseWithFindClose(void *)>(&v120[1]);
          AutoScz::~AutoScz((AutoScz *)&lpFileName);
          goto LABEL_250;
        }
        v120[1] = FindFirstFileW(lpFileName, &FindFileData);
        if ( (unsigned __int64)(v120[1] - 1LL) > 0xFFFFFFFFFFFFFFFDuLL )
        {
          v104 = GetLastError();
          if ( *(_QWORD *)&LogAdapter::g_Logger )
          {
            LogAdapter::Logger::LogNumObjects<AutoScz>(
              *(_QWORD *)&LogAdapter::g_Logger,
              0,
              3,
              "Failed to find a CiX file in directory: {0}",
              &v138);
            if ( v104 > 0 )
              v105 = (unsigned __int16)v104 | 0x80070000;
            else
              v105 = v104;
            v135 = v105;
            *(_QWORD *)v113 = &v135;
            LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
              *(__int64 *)&LogAdapter::g_Logger,
              1,
              3,
              (struct Windows::Rtl::IRtlFormattedOutputStream *)": {0}",
              (__int64)v113);
          }
          if ( !v104 )
          {
            Windows::AutoGenericHandle<void *,1,&void Windows::Detail::CloseWithFindClose(void *)>::~AutoGenericHandle<void *,1,&void Windows::Detail::CloseWithFindClose(void *)>(&v120[1]);
            AutoScz::~AutoScz((AutoScz *)&lpFileName);
            std::vector<UUPInstallPlan::UUPProduct>::_Tidy(&v145);
            std::_Tree<std::_Tset_traits<std::wstring,WstringCaseInsensitiveCompare,std::allocator<std::wstring>,0>>::~_Tree<std::_Tset_traits<std::wstring,WstringCaseInsensitiveCompare,std::allocator<std::wstring>,0>>(&v140);
            std::wstring::~wstring(&v142);
            CIUClient::~CIUClient((CIUClient *)&v114);
            AutoScz::~AutoScz((AutoScz *)&Str);
            AutoScz::~AutoScz((AutoScz *)&v116);
            AutoScz::~AutoScz((AutoScz *)&v137);
            AutoScz::~AutoScz((AutoScz *)&v117);
            AutoScz::~AutoScz((AutoScz *)&v136);
            Directory = 0;
LABEL_342:
            AutoScz::~AutoScz((AutoScz *)&v138);
            return (unsigned int)Directory;
          }
          Directory = wil::details::in1diag3::Return_Win32(
                        retaddr,
                        (void *)0x124B,
                        (unsigned int)"onecore\\base\\servicing\\arbiter\\cactionlistcreator.cpp",
                        (const char *)(unsigned int)v104,
                        bIgnoreCase);
          goto LABEL_249;
        }
        Directory = SczAllocFromSz(&v117, FindFileData.cFileName);
        if ( Directory < 0 )
        {
          v135 = Directory;
          if ( *(_QWORD *)&LogAdapter::g_Logger )
          {
            LogAdapter::Logger::LogNumObjects<>(
              *(__int64 *)&LogAdapter::g_Logger,
              0,
              3,
              (struct Windows::Rtl::IRtlFormattedOutputStream *)"Failed to allocate memory");
            *(_QWORD *)v113 = &v135;
            LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
              *(__int64 *)&LogAdapter::g_Logger,
              1,
              3,
              (struct Windows::Rtl::IRtlFormattedOutputStream *)": {}",
              (__int64)v113);
          }
          v103 = 4685;
          goto LABEL_248;
        }
        Windows::AutoGenericHandle<void *,1,&void Windows::Detail::CloseWithFindClose(void *)>::~AutoGenericHandle<void *,1,&void Windows::Detail::CloseWithFindClose(void *)>(&v120[1]);
        AutoScz::~AutoScz((AutoScz *)&lpFileName);
        v8 = v117;
      }
      Directory = SczAllocFormatted(&v137, L"%ws\\%ws", &v138[v121], v8);
      if ( Directory < 0 )
      {
        v135 = Directory;
        if ( *(_QWORD *)&LogAdapter::g_Logger )
        {
          LogAdapter::Logger::LogNumObjects<>(
            *(__int64 *)&LogAdapter::g_Logger,
            0,
            3,
            (struct Windows::Rtl::IRtlFormattedOutputStream *)"Failed to allocate memory");
          *(_QWORD *)v113 = &v135;
          LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
            *(__int64 *)&LogAdapter::g_Logger,
            1,
            3,
            (struct Windows::Rtl::IRtlFormattedOutputStream *)": {}",
            (__int64)v113);
        }
        v106 = 4689;
LABEL_266:
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)v106,
          (unsigned int)"onecore\\base\\servicing\\arbiter\\cactionlistcreator.cpp",
          (const char *)(unsigned int)Directory,
          bIgnoreCase);
LABEL_250:
        std::vector<UUPInstallPlan::UUPProduct>::_Tidy(&v145);
        std::_Tree<std::_Tset_traits<std::wstring,WstringCaseInsensitiveCompare,std::allocator<std::wstring>,0>>::~_Tree<std::_Tset_traits<std::wstring,WstringCaseInsensitiveCompare,std::allocator<std::wstring>,0>>(&v140);
        goto LABEL_341;
      }
      v88 = DuplicateNullTerminatedString((struct Windows::Rtl::IPoolAllocator *)(*(_QWORD *)v6 + 264LL), v137);
      *(_QWORD *)(v39 + 120) = v88;
      if ( !v88 )
      {
        Directory = -2147024882;
        v106 = 4692;
        goto LABEL_266;
      }
      LogAdapter::TraceInfo<AutoScz>("  Cix file found: {0}", &v137);
    }
LABEL_87:
    v39 += 184;
    if ( v39 == v124 )
      goto LABEL_88;
  }
  v135 = Directory;
  if ( *(_QWORD *)&LogAdapter::g_Logger )
  {
    LogAdapter::Logger::LogNumObjects<>(
      *(__int64 *)&LogAdapter::g_Logger,
      0,
      3,
      (struct Windows::Rtl::IRtlFormattedOutputStream *)"Failed to allocate memory");
    *(_QWORD *)v113 = &v135;
    LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
      *(__int64 *)&LogAdapter::g_Logger,
      1,
      3,
      (struct Windows::Rtl::IRtlFormattedOutputStream *)": {}",
      (__int64)v113);
  }
  v97 = 4477;
LABEL_307:
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)v97,
    (unsigned int)"onecore\\base\\servicing\\arbiter\\cactionlistcreator.cpp",
    (const char *)(unsigned int)Directory,
    bIgnoreCase);
LABEL_308:
  std::vector<UUPInstallPlan::UUPProduct>::_Tidy(&v145);
  std::_Tree<std::_Tset_traits<std::wstring,WstringCaseInsensitiveCompare,std::allocator<std::wstring>,0>>::~_Tree<std::_Tset_traits<std::wstring,WstringCaseInsensitiveCompare,std::allocator<std::wstring>,0>>(&v140);
  std::wstring::~wstring(&v142);
  CIUClient::~CIUClient((CIUClient *)&v114);
  if ( v10 )
    operator delete(v10 - 4, v15);
  if ( v9 )
    operator delete((void *)(v9 - 8), v15);
  if ( v137 )
  {
    operator delete(v137 - 4, v15);
    v137 = 0;
  }
  if ( v8 )
    operator delete((void *)(v8 - 8), v15);
  if ( v136 )
  {
    operator delete(v136 - 4, v15);
    v136 = 0;
  }
LABEL_11:
  if ( v138 )
    operator delete(v138 - 4, v15);
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
