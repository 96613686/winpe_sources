# CCbsPackage::PrepareInitializeEx(CCbsPackage::PrepareInitializeFlags,CCbsSession *,void *,wchar_t const *,IDpxJob *,wchar_t const *,wchar_t const *,_CbsPackageType,ulong,PerSessionPackageState *,ParsingSession * *,CCbsPackage::PrepareInitializeDisposition *)

- ea: `0x18009d188`
- end: `0x18009f706`
- name: `?PrepareInitializeEx@CCbsPackage@@QEAAJW4PrepareInitializeFlags@1@PEAVCCbsSession@@PEAXPEB_WPEAUIDpxJob@@33W4_CbsPackageType@@KPEAUPerSessionPackageState@@PEAPEAUParsingSession@@PEAW4PrepareInitializeDisposition@1@@Z`
- size: `9598`
- prototype: `int __high(enum CCbsPackage::PrepareInitializeFlags, struct CCbsSession *, void *, const wchar_t *, struct IDpxJob *, const wchar_t *, const wchar_t *, enum _CbsPackageType, unsigned int, struct PerSessionPackageState *, struct ParsingSession **, enum CCbsPackage::PrepareInitializeDisposition *)`
- caller_count: `2`
- callee_count: `54`
- tags: `file_ops, authz_impersonation, registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x18002fa74`
- `0x18009c068`

## callees

- `0x18000b46c`
- `0x18000c248`
- `0x18000c58c`
- `0x18000c5b4`
- `0x180010cc0`
- `0x1800115a8`
- `0x180012fe4`
- `0x180013250`
- `0x180015420`
- `0x180016250`
- `0x180016d40`
- `0x18001837c`
- `0x1800261e0`
- `0x180028e24`
- `0x18002a2bc`
- `0x18002e280`
- `0x18002ec34`
- `0x180033f58`
- `0x18003404c`
- `0x180042448`
- `0x1800439a0`
- `0x1800532d4`
- `0x180056e00`
- `0x1800576cc`
- `0x180057c28`
- `0x18005aa38`
- `0x18005eef0`
- `0x180073b74`
- `0x180073d94`
- `0x180093a70`
- `0x18009564c`
- `0x180098538`
- `0x180099390`
- `0x180099548`
- `0x18009cf78`
- `0x18009d188`
- `0x1800a8678`
- `0x1800c003c`
- `0x1800c1958`
- `0x1800c1984`
- `0x1800eb920`
- `0x1800ed210`
- `0x1800f1d54`
- `0x180126f30`
- `0x18012c6d8`
- `0x18012cfcc`
- `0x180143f5c`
- `0x18019e7c8`
- `0x18019eb64`
- `0x18019eba4`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18009d5a0`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18009d5a0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18009d2e5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18009d2e5`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x18009d837`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x18009dfbd`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x18009e2bd`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x18009e8e1`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x18009d837`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x18009dfbd`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x18009e2bd`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x18009e8e1`
- `api-ms-win-security-base-l1-1-0!DuplicateToken` at `0x18009d2d3`
- `api-ms-win-security-base-l1-1-0!DuplicateToken` at `0x18009d2d3`

## string_xrefs

- `0x18009d599`: `update`
- `0x18009f0fa`: `Failed to create private session store.`
- `0x18009dec9`: `Failed to cache package identity in the package property.`
- `0x18009ed95`: `Failed to cache package identity in the package property.`
- `0x18009dae0`: `Failed to impersonate user to extract from cabinet: {}, package manifest: {}, sandbox: {}`
- `0x18009e310`: `Failed to impersonate user to extract from cabinet: {}, package manifest: {}, sandbox: {}`
- `0x18009dba9`: `Failed to create package extract job for location: {}`
- `0x18009e011`: `Failed to create package extract job for location: {}`
- `0x18009ddee`: `Failed to allocate CbsIdentity for onepackage.`
- `0x18009ecda`: `Failed to allocate CbsIdentity for onepackage.`
- `0x18009de5d`: `Failed to get CbsIdentity for this onepackage.`
- `0x18009ed39`: `Failed to get CbsIdentity for this onepackage.`
- `0x18009d5e1`: `Failed to get target servicing directory.`
- `0x18009d2a2`: `Unable to get non-TI token.`
- `0x18009d300`: `Unable to duplicate non-TI token.`
- `0x18009d365`: `A User token is required on non-existing packages.`
- `0x18009f059`: `Failed to parse package manifest: {}`
- `0x18009f209`: `Failed to copy manifest: {} to private store and verify the content.`
- `0x18009f30a`: `Failed cache package identity in the package property.`
- `0x18009e4ed`: `Failed to parse the package manifest {}`
- `0x18009e602`: `Failed to get CbsIdentity for this package.`
- `0x18009f280`: `Failed to get CbsIdentity for this package.`
- `0x18009e11e`: `Failed to extract package manifest from cabinet`
- `0x18009e774`: `Failed to extract package manifest from cabinet`
- `0x18009e19f`: `Opened cabinet package, package directory: {}, sandbox location: {}, cabinet location: {}, manifest location: {}`
- `0x18009ee6b`: `Failed to parse package manifest from given buffer`

## pseudocode

```c
__int64 __fastcall CCbsPackage::PrepareInitializeEx(
        __int64 a1,
        unsigned int a2,
        CCbsSession *a3,
        __int64 a4,
        const WCHAR *a5,
        __int64 a6,
        const WCHAR *lpFileName,
        __int64 a8,
        int a9,
        int a10,
        __int64 a11,
        ParsingSession **a12,
        unsigned int *a13)
{
  CCbsSession *v14; // rbx
  __int64 v15; // rsi
  int v16; // eax
  ParsingSession **v17; // rcx
  char v18; // di
  void **InitPointer; // rax
  int NonTiToken; // ebx
  void **v21; // rax
  signed int LastError; // eax
  signed int v23; // ebx
  unsigned int v24; // ebx
  __int64 v25; // rdx
  unsigned int v26; // edx
  ParsingSession *v27; // rcx
  int ServicingDirectory; // eax
  __int64 v29; // rcx
  struct Windows::Rtl::StopWatch *v30; // r9
  unsigned int v31; // edx
  ParsingSession *v32; // rcx
  ParsingSession *v33; // rsi
  __int64 v34; // rdx
  DWORD FileAttributesW; // eax
  LPCWCH *v36; // rbx
  int v37; // edi
  __int64 v38; // rdx
  unsigned int v39; // edx
  wchar_t *v41; // rdi
  int v42; // r12d
  __int64 v43; // rdx
  unsigned int v44; // edx
  int v45; // eax
  struct IDpxJob **v46; // r12
  __int64 v47; // rcx
  struct IDpxJob **v48; // rax
  int v49; // eax
  int v50; // eax
  int v51; // eax
  unsigned int v52; // edx
  _QWORD *v53; // rdi
  int v54; // eax
  int v55; // eax
  int v56; // eax
  unsigned int v57; // edx
  struct IDpxJob **v58; // rax
  int v59; // eax
  int v60; // eax
  int SingleFileFromCabinet; // eax
  int v62; // edx
  int v63; // r8d
  int v64; // eax
  __int64 v65; // rdx
  wchar_t *v66; // rbx
  int v67; // eax
  int v68; // eax
  int v69; // edx
  unsigned int v70; // r12d
  __int64 v71; // rcx
  CCbsSession *v72; // rdi
  int v73; // eax
  __int64 v74; // rcx
  __int64 v75; // r9
  struct Windows::Rtl::StopWatch *v76; // r9
  struct ParsingSession *v77; // rbx
  int v78; // eax
  int v79; // edi
  __int64 v80; // rcx
  struct CCbsIdentity **v81; // rax
  int v82; // eax
  __int64 v83; // rcx
  __int64 v84; // rcx
  __int64 v85; // rdx
  unsigned __int64 v86; // r9
  int v87; // eax
  int v88; // eax
  wchar_t *v89; // rdi
  int v90; // eax
  wchar_t *v91; // rbx
  int v92; // eax
  int v93; // eax
  __int64 v94; // rcx
  __int64 v95; // rcx
  int v96; // eax
  __int64 v97; // rcx
  _QWORD *v98; // rbx
  __int64 v99; // rcx
  __int64 v100; // rax
  __int64 v101; // rdx
  int v102; // edi
  wchar_t *v103; // r12
  int v104; // eax
  unsigned int v105; // edx
  _QWORD *v106; // rdi
  int CbsIdentity; // eax
  __int64 v108; // rcx
  __int64 v109; // rcx
  int v110; // eax
  __int64 v111; // rcx
  __int64 v112; // rcx
  int v113; // eax
  __int64 v114; // rcx
  __int64 v115; // rcx
  __int64 v116; // rcx
  __int64 v117; // rcx
  __int64 v118; // rcx
  char v119; // di
  __int64 v120; // rcx
  __int64 v121; // rcx
  __int64 v122; // rax
  int SessionSandbox; // eax
  __int64 v124; // rcx
  __int64 v125; // rcx
  CCbsSession *v126; // rdi
  int v127; // eax
  __int64 v128; // rdx
  CCbsSession *v129; // r12
  __int64 v130; // rcx
  __int64 v131; // rcx
  int CbsIdentityFromAssemblyIdentity; // eax
  __int64 v133; // rcx
  __int64 v134; // rcx
  __int64 v135; // rdx
  const wchar_t **v136; // rdi
  int v137; // eax
  __int64 v138; // rcx
  __int64 v139; // rcx
  __int64 v140; // rax
  unsigned __int64 v141; // rcx
  const wchar_t *v142; // rax
  unsigned __int64 v143; // rdx
  unsigned __int64 v144; // rcx
  bool v145; // zf
  __int64 v146; // rcx
  CCbsSession *v147; // rcx
  int OfflineServicingStackVersion; // eax
  __int64 v149; // rcx
  __int64 v150; // rcx
  unsigned __int64 v151; // rcx
  unsigned __int64 v152; // rdx
  const wchar_t *v153; // rax
  unsigned __int64 v154; // rcx
  unsigned __int64 v155; // rdx
  __int64 v156; // rcx
  const wchar_t *v157; // rax
  wchar_t *v158; // [rsp+20h] [rbp-E0h]
  int v159; // [rsp+20h] [rbp-E0h]
  wchar_t *v160; // [rsp+60h] [rbp-A0h] BYREF
  __int64 v161; // [rsp+68h] [rbp-98h] BYREF
  HANDLE ExistingTokenHandle; // [rsp+70h] [rbp-90h] BYREF
  wchar_t *v163; // [rsp+78h] [rbp-88h] BYREF
  wchar_t *v164; // [rsp+80h] [rbp-80h] BYREF
  wchar_t *v165; // [rsp+88h] [rbp-78h] BYREF
  wchar_t *v166; // [rsp+90h] [rbp-70h] BYREF
  wchar_t *v167; // [rsp+98h] [rbp-68h] BYREF
  __int64 v168; // [rsp+A0h] [rbp-60h] BYREF
  __int64 v169; // [rsp+A8h] [rbp-58h] BYREF
  struct ParsingSession *v170; // [rsp+B0h] [rbp-50h] BYREF
  ParsingSession *v171; // [rsp+B8h] [rbp-48h] BYREF
  LPCWCH lpWideCharStr; // [rsp+C0h] [rbp-40h] BYREF
  int v173[2]; // [rsp+C8h] [rbp-38h] BYREF
  __int64 v174; // [rsp+D0h] [rbp-30h] BYREF
  char v175; // [rsp+D8h] [rbp-28h]
  int v176[2]; // [rsp+E0h] [rbp-20h] BYREF
  ParsingSession **v177; // [rsp+E8h] [rbp-18h] BYREF
  __int64 v178; // [rsp+F0h] [rbp-10h] BYREF
  ParsingSession **v179; // [rsp+F8h] [rbp-8h] BYREF
  __int64 v180; // [rsp+100h] [rbp+0h] BYREF
  unsigned __int64 v181; // [rsp+108h] [rbp+8h] BYREF
  __int64 v182; // [rsp+110h] [rbp+10h] BYREF
  _QWORD v183[2]; // [rsp+118h] [rbp+18h] BYREF
  char v184; // [rsp+128h] [rbp+28h]
  int v185; // [rsp+130h] [rbp+30h] BYREF
  unsigned int v186; // [rsp+134h] [rbp+34h] BYREF
  __int64 v187; // [rsp+138h] [rbp+38h] BYREF
  __int64 v188; // [rsp+140h] [rbp+40h] BYREF
  unsigned int v189; // [rsp+148h] [rbp+48h] BYREF
  CCbsSession *v190; // [rsp+150h] [rbp+50h] BYREF
  int v191; // [rsp+158h] [rbp+58h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+1A8h] [rbp+A8h]

  v14 = a3;
  v15 = a4;
  lpWideCharStr = a5;
  v183[0] = &a13;
  v183[1] = &v186;
  v189 = a2;
  v181 = vServicingStackVersion;
  v16 = a9;
  v180 = a6;
  v17 = a12;
  v182 = a4;
  v190 = a3;
  v178 = a8;
  v179 = a12;
  v186 = 0;
  v184 = 1;
  v171 = 0;
  v167 = 0;
  v160 = 0;
  v166 = 0;
  v169 = 0;
  v168 = 0;
  v161 = 0;
  v165 = 0;
  v170 = 0;
  v164 = 0;
  v163 = 0;
  v187 = 0;
  if ( a9 == 1 || a9 <= -2 || (v18 = 1, a9 >= 4) )
    v18 = 0;
  ExistingTokenHandle = 0;
  v188 = 0;
  if ( !v18 && !a4 )
  {
    InitPointer = (void **)Windows::AutoGenericHandleBase<void *,1,Windows::AutoGenericHandle<void *,1,&void Windows::Detail::CloseWithNtCloseHandle(void *)>>::GetInitPointer(&ExistingTokenHandle);
    NonTiToken = GetNonTiToken(InitPointer);
    LogAdapter::TraceAtLevelIfFailed<long,>(1, (unsigned int)NonTiToken, "Unable to get non-TI token.");
    if ( NonTiToken >= 0 )
    {
      v21 = (void **)Windows::AutoGenericHandleBase<void *,1,Windows::AutoGenericHandle<void *,1,&void Windows::Detail::CloseWithNtCloseHandle(void *)>>::GetInitPointer(&v188);
      if ( DuplicateToken(ExistingTokenHandle, SecurityImpersonation, v21) )
        goto LABEL_12;
      LastError = GetLastError();
      v23 = LastError;
      if ( LastError > 0 )
        v23 = (unsigned __int16)LastError | 0x80070000;
      LogAdapter::TraceAtLevelIfFailed<long,>(1, (unsigned int)v23, "Unable to duplicate non-TI token.");
      if ( v23 >= 0 )
      {
LABEL_12:
        v15 = v188;
        v182 = v188;
      }
    }
    v14 = v190;
    v16 = a9;
    v17 = v179;
  }
  v174 = v15;
  v175 = 0;
  if ( !v18 && !v15 )
  {
    v24 = -2146498560;
    v185 = -2146498560;
    if ( LogAdapter::g_Logger )
    {
      LogAdapter::Logger::LogNumObjects<>(
        (__int64)LogAdapter::g_Logger,
        0,
        3,
        (struct Windows::Rtl::IRtlFormattedOutputStream *)"A User token is required on non-existing packages.");
      lpWideCharStr = (LPCWCH)&v185;
      LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
        (__int64)LogAdapter::g_Logger,
        1,
        3,
        (__int64)": {}",
        (__int64)&lpWideCharStr);
    }
    v25 = 367;
LABEL_19:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v25,
      (unsigned int)"onecore\\base\\cbs\\core\\cbspackagepersistence.cpp",
      (const char *)v24,
      (int)v158);
    ImpersonatorBase::Unimpersonate((ImpersonatorBase *)&v174);
    Windows::AutoGenericHandleBase<void *,1,Windows::AutoGenericHandle<void *,1,&void Windows::Detail::CloseWithNtCloseHandle(void *)>>::Close(&v188);
    Windows::AutoGenericHandleBase<void *,1,Windows::AutoGenericHandle<void *,1,&void Windows::Detail::CloseWithNtCloseHandle(void *)>>::Close(&ExistingTokenHandle);
    Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&v187);
    Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&v163);
    Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&v164);
    Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&v165);
    Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&v161);
    Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&v168);
    Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&v169);
    Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&v166);
    Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&v160);
    Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&v167);
    if ( a13 )
      *a13 = v186;
    return v24;
  }
  if ( !v17 )
  {
    v24 = -2147467261;
    v185 = -2147467261;
    if ( LogAdapter::g_Logger )
    {
      LogAdapter::Logger::LogNumObjects<>(
        (__int64)LogAdapter::g_Logger,
        0,
        3,
        (struct Windows::Rtl::IRtlFormattedOutputStream *)"No parsing session result specified");
      lpWideCharStr = (LPCWCH)&v185;
      LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
        (__int64)LogAdapter::g_Logger,
        1,
        3,
        (__int64)": {}",
        (__int64)&lpWideCharStr);
    }
    v25 = 369;
    goto LABEL_19;
  }
  *(_DWORD *)(a1 + 864) = v16;
  *(_DWORD *)(a1 + 104) = a10;
  *(_BYTE *)(a1 + 1058) = 0;
  if ( !Windows::AutoNewPtr<ParsingSession>::Allocate<>(&v171) )
  {
    v24 = -2147024882;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x177,
      (unsigned int)"onecore\\base\\cbs\\core\\cbspackagepersistence.cpp",
      (const char *)0x8007000ELL,
      (int)v158);
    ImpersonatorBase::Unimpersonate((ImpersonatorBase *)&v174);
    Windows::AutoGenericHandleBase<void *,1,Windows::AutoGenericHandle<void *,1,&void Windows::Detail::CloseWithNtCloseHandle(void *)>>::Close(&v188);
    Windows::AutoGenericHandleBase<void *,1,Windows::AutoGenericHandle<void *,1,&void Windows::Detail::CloseWithNtCloseHandle(void *)>>::Close(&ExistingTokenHandle);
    Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&v187);
    Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&v163);
    Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&v164);
    Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&v165);
    Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&v161);
    Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&v168);
    Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&v169);
    Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&v166);
    Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&v160);
    Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&v167);
    v27 = v171;
    if ( !v171 )
      goto LABEL_28;
    goto LABEL_27;
  }
  v185 = _o__wcsicmp(L"update", a8);
  ServicingDirectory = CCbsSession::GetServicingDirectory(v14, L"Packages", &v165);
  v24 = ServicingDirectory;
  if ( ServicingDirectory < 0 )
  {
    v185 = ServicingDirectory;
    if ( LogAdapter::g_Logger )
    {
      LogAdapter::Logger::LogNumObjects<>(
        (__int64)LogAdapter::g_Logger,
        0,
        3,
        (struct Windows::Rtl::IRtlFormattedOutputStream *)"Failed to get target servicing directory.");
      lpWideCharStr = (LPCWCH)&v185;
      LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
        (__int64)LogAdapter::g_Logger,
        1,
        3,
        (__int64)": {}",
        (__int64)&lpWideCharStr);
    }
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x186,
      (unsigned int)"onecore\\base\\cbs\\core\\cbspackagepersistence.cpp",
      (const char *)v24,
      (int)v158);
    ImpersonatorBase::Unimpersonate((ImpersonatorBase *)&v174);
    Windows::AutoGenericHandleBase<void *,1,Windows::AutoGenericHandle<void *,1,&void Windows::Detail::CloseWithNtCloseHandle(void *)>>::Close(&v188);
    Windows::AutoGenericHandleBase<void *,1,Windows::AutoGenericHandle<void *,1,&void Windows::Detail::CloseWithNtCloseHandle(void *)>>::Close(&ExistingTokenHandle);
    Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&v187);
    Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&v163);
    Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&v164);
    Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&v165);
    Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&v161);
    Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&v168);
    Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&v169);
    Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&v166);
    Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&v160);
    Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&v167);
    v32 = v171;
    if ( !v171 )
      goto LABEL_35;
    goto LABEL_34;
  }
  v33 = v171;
  v191 = v189 & 1;
  if ( a9 )
  {
    v102 = v189 & 2;
    v189 = v102;
    if ( a9 == 2 )
    {
      if ( !a11 )
      {
        v24 = -2147024809;
        v189 = -2147024809;
        if ( LogAdapter::g_Logger )
        {
          LogAdapter::Logger::LogPartial<>(v29, 3, "No per-session package state specified for package");
          *(_QWORD *)v173 = &v189;
          LogAdapter::Logger::Log<Windows::WCP::Rtl::FormatHResultWrapper<long>>(v118, 3, ": {}", v173);
        }
        v75 = 2147942487LL;
        v65 = 629;
        goto LABEL_215;
      }
    }
    else
    {
      if ( a9 == 3 )
      {
        v24 = ParseCbsPackageFromBuffer(lpWideCharStr, v171);
        if ( (v24 & 0x80000000) != 0 )
        {
          if ( v102 )
            v186 |= 4u;
          else
            CCbsSession::MarkPackageStoreCorrupt(v190);
          v185 = v24;
          if ( LogAdapter::g_Logger )
          {
            LogAdapter::Logger::LogPartial<>(v116, 3, "Failed to parse package manifest from given buffer");
            *(_QWORD *)v173 = &v185;
            LogAdapter::Logger::Log<Windows::WCP::Rtl::FormatHResultWrapper<long>>(v117, 3, ": {}", v173);
          }
          v75 = v24;
          v65 = 625;
          goto LABEL_215;
        }
        goto LABEL_289;
      }
      if ( !a11 )
      {
        v24 = -2147024809;
        v189 = -2147024809;
        if ( LogAdapter::g_Logger )
        {
          LogAdapter::Logger::LogNumObjects<>(
            (__int64)LogAdapter::g_Logger,
            0,
            3,
            (struct Windows::Rtl::IRtlFormattedOutputStream *)"No state specified for package");
          *(_QWORD *)v173 = &v189;
          LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
            (__int64)LogAdapter::g_Logger,
            1,
            3,
            (__int64)": {}",
            (__int64)v173);
        }
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x240,
          (unsigned int)"onecore\\base\\cbs\\core\\cbspackagepersistence.cpp",
          (const char *)0x80070057LL,
          (int)v158);
        ImpersonatorBase::Unimpersonate((ImpersonatorBase *)&v174);
        Windows::AutoGenericHandleBase<void *,1,Windows::AutoGenericHandle<void *,1,&void Windows::Detail::CloseWithNtCloseHandle(void *)>>::Close(&v188);
        Windows::AutoGenericHandleBase<void *,1,Windows::AutoGenericHandle<void *,1,&void Windows::Detail::CloseWithNtCloseHandle(void *)>>::Close(&ExistingTokenHandle);
        Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&v187);
        Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&v163);
        Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&v164);
        Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&v165);
        Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&v161);
        Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&v168);
        Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&v169);
        Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&v166);
        Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&v160);
        Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&v167);
        if ( !v33 )
          goto LABEL_28;
        v27 = v33;
LABEL_27:
        ParsingSession::`scalar deleting destructor'(v27, v26);
LABEL_28:
        if ( a13 )
          *a13 = v186;
        return v24;
      }
      v103 = (wchar_t *)lpWideCharStr;
      v24 = DirectoryFromPath((wchar_t *)lpWideCharStr);
      if ( (v24 & 0x80000000) != 0 )
      {
        v34 = 578;
        goto LABEL_44;
      }
      v24 = PathPrefix(a11 + 16);
      if ( (v24 & 0x80000000) != 0 )
      {
        v34 = 579;
        goto LABEL_44;
      }
      v24 = SczAllocFromSz(a11 + 32, v103);
      if ( (v24 & 0x80000000) != 0 )
      {
        v34 = 580;
        goto LABEL_44;
      }
      v104 = PathPrefix(a11 + 32);
      v24 = v104;
      if ( v104 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x245,
          (unsigned int)"onecore\\base\\cbs\\core\\cbspackagepersistence.cpp",
          (const char *)(unsigned int)v104,
          (int)v158);
        ImpersonatorBase::Unimpersonate((ImpersonatorBase *)&v174);
        Windows::AutoGenericHandleBase<void *,1,Windows::AutoGenericHandle<void *,1,&void Windows::Detail::CloseWithNtCloseHandle(void *)>>::Close(&v188);
        Windows::AutoGenericHandleBase<void *,1,Windows::AutoGenericHandle<void *,1,&void Windows::Detail::CloseWithNtCloseHandle(void *)>>::Close(&ExistingTokenHandle);
        Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&v187);
        Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&v163);
        Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&v164);
        Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&v165);
        Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&v161);
        Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&v168);
        Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&v169);
        Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&v166);
        Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&v160);
        Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&v167);
        if ( v33 )
          ParsingSession::`scalar deleting destructor'(v33, v105);
        goto LABEL_330;
      }
      v64 = DirectoryFromPath(v103);
      v24 = v64;
      if ( v64 < 0 )
      {
        v65 = 582;
        goto LABEL_214;
      }
      v64 = PathPrefix(a11 + 24);
      v24 = v64;
      if ( v64 < 0 )
      {
        v65 = 583;
        goto LABEL_214;
      }
      v64 = SczAllocConcat2Sz(&v161, *(_QWORD *)(a11 + 24), L"desktopdeployment.cab");
      v24 = v64;
      if ( v64 < 0 )
      {
        v65 = 584;
        goto LABEL_214;
      }
      if ( !v185 && (unsigned int)DoesFileExist(v161, 0) )
      {
        v106 = (_QWORD *)(a1 + 112);
        *(_BYTE *)(a1 + 1058) = 1;
        *(_DWORD *)(a1 + 92) = 1;
        CbsIdentity = CreateCbsIdentity((struct CCbsIdentity **)(a1 + 112));
        v24 = CbsIdentity;
        if ( CbsIdentity < 0 )
        {
          v185 = CbsIdentity;
          if ( LogAdapter::g_Logger )
          {
            LogAdapter::Logger::LogPartial<>(v108, 3, "Failed to allocate CbsIdentity for onepackage.");
            *(_QWORD *)v173 = &v185;
            LogAdapter::Logger::Log<Windows::WCP::Rtl::FormatHResultWrapper<long>>(v109, 3, ": {}", v173);
          }
          v75 = v24;
          v65 = 594;
          goto LABEL_215;
        }
        v110 = (*(__int64 (__fastcall **)(_QWORD, const wchar_t *))(*(_QWORD *)*v106 + 56LL))(
                 *v106,
                 L"OnePackage~~~~0.0.0.0");
        v24 = v110;
        if ( v110 < 0 )
        {
          v185 = v110;
          if ( LogAdapter::g_Logger )
          {
            LogAdapter::Logger::LogPartial<>(v111, 3, "Failed to get CbsIdentity for this onepackage.");
            *(_QWORD *)v173 = &v185;
            LogAdapter::Logger::Log<Windows::WCP::Rtl::FormatHResultWrapper<long>>(v112, 3, ": {}", v173);
          }
          v75 = v24;
          v65 = 597;
          goto LABEL_215;
        }
        v113 = (*(__int64 (__fastcall **)(_QWORD, __int64))(*(_QWORD *)*v106 + 72LL))(*v106, a1 + 120);
        v24 = v113;
        if ( v113 < 0 )
        {
          v185 = v113;
          if ( LogAdapter::g_Logger )
          {
            LogAdapter::Logger::LogPartial<>(v114, 3, "Failed to cache package identity in the package property.");
            *(_QWORD *)v173 = &v185;
            LogAdapter::Logger::Log<Windows::WCP::Rtl::FormatHResultWrapper<long>>(v115, 3, ": {}", v173);
          }
          v75 = v24;
          v65 = 600;
          goto LABEL_215;
        }
        CCbsPackage::SetCurrentState(a1, 0, 1);
      }
      if ( a9 == -1 || a9 == 4 )
      {
        v64 = FileReplaceExtension(*(wchar_t **)(a11 + 32));
        v24 = v64;
        if ( v64 < 0 )
        {
          v65 = 637;
          goto LABEL_214;
        }
        v64 = SczAllocFromSz(a11 + 48, v160);
        v24 = v64;
        if ( v64 < 0 )
        {
          v65 = 638;
          goto LABEL_214;
        }
        goto LABEL_259;
      }
    }
    if ( !*(_BYTE *)(a1 + 1058) )
    {
      v64 = SczAllocFormatted(&v160, L"%ws.cat", v178);
      v24 = v64;
      if ( v64 < 0 )
      {
        v65 = 744;
        goto LABEL_214;
      }
      v64 = SczAllocConcat2Sz(a11 + 48, *(_QWORD *)(a11 + 24), v160);
      v24 = v64;
      if ( v64 < 0 )
      {
        v65 = 745;
        goto LABEL_214;
      }
      goto LABEL_190;
    }
LABEL_259:
    v119 = v191;
    if ( a9 == -1 )
    {
      v24 = ParseCbsPackage(0, *(const wchar_t *const *)(a11 + 32), v33, v30);
      if ( (v24 & 0x80000000) != 0 )
      {
        if ( v189 )
        {
          v120 = v186 | 4;
          v186 |= 4u;
        }
        else
        {
          CCbsSession::MarkPackageStoreCorrupt(v190);
          v120 = v186;
        }
        if ( v24 != -2147024894 || !v119 )
        {
          v185 = v24;
          if ( LogAdapter::g_Logger )
          {
            *(_QWORD *)v173 = *(_QWORD *)(a11 + 32);
            LogAdapter::Logger::LogPartial<wchar_t *>(v120, 3, "Failed to parse package manifest: {}", v173);
            *(_QWORD *)v176 = &v185;
            LogAdapter::Logger::Log<Windows::WCP::Rtl::FormatHResultWrapper<long>>(v121, 3, ": {}", v176);
          }
          v75 = v24;
          v65 = 770;
          goto LABEL_215;
        }
        v186 = v120 | 2;
LABEL_267:
        ImpersonatorBase::Unimpersonate((ImpersonatorBase *)&v174);
        Windows::AutoGenericHandleBase<void *,1,Windows::AutoGenericHandle<void *,1,&void Windows::Detail::CloseWithNtCloseHandle(void *)>>::Close(&v188);
        Windows::AutoGenericHandleBase<void *,1,Windows::AutoGenericHandle<void *,1,&void Windows::Detail::CloseWithNtCloseHandle(void *)>>::Close(&ExistingTokenHandle);
        Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&v187);
        Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&v163);
        Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&v164);
        Windows::AutoNewPtr<ParsingSession>::~AutoNewPtr<ParsingSession>(&v170);
        Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&v165);
        Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&v161);
        Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&v168);
        Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&v169);
        Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&v166);
        Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&v160);
        Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&v167);
        Windows::AutoNewPtr<ParsingSession>::~AutoNewPtr<ParsingSession>(&v171);
        v24 = 1;
        goto LABEL_330;
      }
      goto LABEL_289;
    }
    goto LABEL_190;
  }
  if ( !a11 )
  {
    v24 = -2147024809;
    v189 = -2147024809;
    if ( LogAdapter::g_Logger )
    {
      LogAdapter::Logger::LogNumObjects<>(
        (__int64)LogAdapter::g_Logger,
        0,
        3,
        (struct Windows::Rtl::IRtlFormattedOutputStream *)"No state specified for cabinet package");
      lpWideCharStr = (LPCWCH)&v189;
      LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
        (__int64)LogAdapter::g_Logger,
        1,
        3,
        (__int64)": {}",
        (__int64)&lpWideCharStr);
    }
    v34 = 404;
    goto LABEL_44;
  }
  v24 = DirectoryFromPath((wchar_t *)lpWideCharStr);
  if ( (v24 & 0x80000000) != 0 )
  {
    v34 = 405;
LABEL_44:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v34,
      (unsigned int)"onecore\\base\\cbs\\core\\cbspackagepersistence.cpp",
      (const char *)v24,
      (int)v158);
    ImpersonatorBase::Unimpersonate((ImpersonatorBase *)&v174);
    Windows::AutoGenericHandleBase<void *,1,Windows::AutoGenericHandle<void *,1,&void Windows::Detail::CloseWithNtCloseHandle(void *)>>::Close(&v188);
    Windows::AutoGenericHandleBase<void *,1,Windows::AutoGenericHandle<void *,1,&void Windows::Detail::CloseWithNtCloseHandle(void *)>>::Close(&ExistingTokenHandle);
    Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&v187);
    Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&v163);
    Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&v164);
    Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&v165);
    Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&v161);
    Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&v168);
    Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&v169);
    Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&v166);
    Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&v160);
    Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&v167);
    if ( !v33 )
    {
LABEL_35:
      if ( a13 )
        *a13 = v186;
      return v24;
    }
    v32 = v33;
LABEL_34:
    ParsingSession::`scalar deleting destructor'(v32, v31);
    goto LABEL_35;
  }
  v24 = PathPrefix(a11 + 16);
  if ( (v24 & 0x80000000) != 0 )
  {
    v34 = 406;
    goto LABEL_44;
  }
  if ( lpFileName
    && ((FileAttributesW = GetFileAttributesW(lpFileName), FileAttributesW != -1) && (FileAttributesW & 0x10) != 0
     || (int)RecursivelyCreateDirectory(lpFileName, 0) >= 0) )
  {
    v36 = (LPCWCH *)(a11 + 24);
    v37 = SczAllocFromSz(a11 + 24, lpFileName);
    if ( v37 < 0 )
    {
      v38 = 430;
LABEL_54:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v38,
        (unsigned int)"onecore\\base\\cbs\\core\\cbspackagepersistence.cpp",
        (const char *)(unsigned int)v37,
        (int)v158);
      ImpersonatorBase::Unimpersonate((ImpersonatorBase *)&v174);
      Windows::AutoGenericHandleBase<void *,1,Windows::AutoGenericHandle<void *,1,&void Windows::Detail::CloseWithNtCloseHandle(void *)>>::Close(&v188);
      Windows::AutoGenericHandleBase<void *,1,Windows::AutoGenericHandle<void *,1,&void Windows::Detail::CloseWithNtCloseHandle(void *)>>::Close(&ExistingTokenHandle);
      Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&v187);
      Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&v163);
      Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&v164);
      Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&v165);
      Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&v161);
      Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&v168);
      Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&v169);
      Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&v166);
      Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&v160);
      Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&v167);
      if ( v33 )
        ParsingSession::`scalar deleting destructor'(v33, v39);
      if ( a13 )
        *a13 = v186;
      return (unsigned int)v37;
    }
  }
  else
  {
    v36 = (LPCWCH *)(a11 + 24);
    v37 = SczAllocFromSz(a11 + 24, *(_QWORD *)(a11 + 16));
    if ( v37 < 0 )
    {
      v38 = 440;
      goto LABEL_54;
    }
  }
  v37 = PathPrefix(v36);
  if ( v37 < 0 )
  {
    v38 = 443;
    goto LABEL_54;
  }
  v37 = SczEnsureBackslashTerminated(v36);
  if ( v37 < 0 )
  {
    v38 = 445;
    goto LABEL_54;
  }
  v37 = SczAllocFormatted(&v167, L"%s.mum", v178);
  if ( v37 < 0 )
  {
    v38 = 447;
    goto LABEL_54;
  }
  v41 = v167;
  v42 = SczAllocConcat2Sz(a11 + 32, *v36, v167);
  if ( v42 < 0 )
  {
    v43 = 449;
LABEL_69:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v43,
      (unsigned int)"onecore\\base\\cbs\\core\\cbspackagepersistence.cpp",
      (const char *)(unsigned int)v42,
      (int)v158);
    ImpersonatorBase::Unimpersonate((ImpersonatorBase *)&v174);
    Windows::AutoGenericHandleBase<void *,1,Windows::AutoGenericHandle<void *,1,&void Windows::Detail::CloseWithNtCloseHandle(void *)>>::Close(&v188);
    Windows::AutoGenericHandleBase<void *,1,Windows::AutoGenericHandle<void *,1,&void Windows::Detail::CloseWithNtCloseHandle(void *)>>::Close(&ExistingTokenHandle);
    Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&v187);
    Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&v163);
    Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&v164);
    Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&v165);
    Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&v161);
    Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&v168);
    Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&v169);
    Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&v166);
    Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&v160);
    Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&v167);
    if ( v33 )
      ParsingSession::`scalar deleting destructor'(v33, v44);
    if ( a13 )
      *a13 = v186;
    return (unsigned int)v42;
  }
  v177 = (ParsingSession **)(a11 + 40);
  v42 = SczAllocFromSz(a11 + 40, lpWideCharStr);
  if ( v42 < 0 )
  {
    v43 = 451;
    goto LABEL_69;
  }
  v42 = PathPrefix(a11 + 40);
  if ( v42 < 0 )
  {
    v43 = 453;
    goto LABEL_69;
  }
  v45 = NestableImpersonator::Impersonate((NestableImpersonator *)&v174);
  v42 = v45;
  if ( v45 < 0 )
  {
    v185 = v45;
    if ( LogAdapter::g_Logger )
    {
      lpWideCharStr = *v36;
      v170 = (struct ParsingSession *)v41;
      v171 = *v177;
      LogAdapter::Logger::LogNumObjects<wchar_t const *,AutoScz,wchar_t *>(
        (_DWORD)LogAdapter::g_Logger,
        0,
        3,
        (unsigned int)"Failed to impersonate user to extract from cabinet: {}, package manifest: {}, sandbox: {}",
        (__int64)&v171,
        (__int64)&v170,
        (__int64)&lpWideCharStr);
      v190 = (CCbsSession *)&v185;
      LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
        (__int64)LogAdapter::g_Logger,
        1,
        3,
        (__int64)": {}",
        (__int64)&v190);
    }
    v43 = 460;
    goto LABEL_69;
  }
  v46 = (struct IDpxJob **)(a11 + 192);
  if ( !*(_QWORD *)(a11 + 192) )
  {
    v47 = a11 + 192;
    if ( v180 )
    {
      Windows::AutoComPtr<CCbsPublicSession>::TakeReference(v47, v180);
    }
    else
    {
      v48 = (struct IDpxJob **)Windows::AutoGenericHandleBase<void *,0,Windows::AutoGenericHandle<void *,0,&void CloseBcdStore(void *)>>::GetInitPointer(v47);
      v49 = Dpx_DpxNewJob(*v36, v48);
      v42 = v49;
      if ( v49 < 0 )
      {
        v185 = v49;
        if ( LogAdapter::g_Logger )
        {
          lpWideCharStr = *v36;
          LogAdapter::Logger::LogNumObjects<wchar_t const *>(
            (__int64)LogAdapter::g_Logger,
            0,
            3,
            (__int64)"Failed to create package extract job for location: {}",
            (__int64)&lpWideCharStr);
          v170 = (struct ParsingSession *)&v185;
          LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
            (__int64)LogAdapter::g_Logger,
            1,
            3,
            (__int64)": {}",
            (__int64)&v170);
        }
        v43 = 475;
        goto LABEL_69;
      }
      v50 = (*(__int64 (__fastcall **)(_QWORD, const wchar_t *, const wchar_t *))(**(_QWORD **)(a11 + 192) + 120LL))(
              *(_QWORD *)(a11 + 192),
              L"ignore_filenotfound_warnings",
              L"1");
      v42 = v50;
      if ( v50 < 0 )
      {
        v185 = v50;
        if ( LogAdapter::g_Logger )
        {
          LogAdapter::Logger::LogNumObjects<>(
            (__int64)LogAdapter::g_Logger,
            0,
            3,
            (struct Windows::Rtl::IRtlFormattedOutputStream *)"Failed to set DPX_OPTION_IGNORE_FNF_WARNINGS");
          lpWideCharStr = (LPCWCH)&v185;
          LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
            (__int64)LogAdapter::g_Logger,
            1,
            3,
            (__int64)": {}",
            (__int64)&lpWideCharStr);
        }
        v43 = 479;
        goto LABEL_69;
      }
      v46 = (struct IDpxJob **)(a11 + 192);
    }
  }
  v51 = SczAllocConcat2Sz(&v161, *v36, L"desktopdeployment.cab");
  v189 = v51;
  if ( v51 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1E3,
      (unsigned int)"onecore\\base\\cbs\\core\\cbspackagepersistence.cpp",
      (const char *)(unsigned int)v51,
      (int)v158);
    ImpersonatorBase::Unimpersonate((ImpersonatorBase *)&v174);
    Windows::AutoGenericHandleBase<void *,1,Windows::AutoGenericHandle<void *,1,&void Windows::Detail::CloseWithNtCloseHandle(void *)>>::Close(&v188);
    Windows::AutoGenericHandleBase<void *,1,Windows::AutoGenericHandle<void *,1,&void Windows::Detail::CloseWithNtCloseHandle(void *)>>::Close(&ExistingTokenHandle);
    Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&v187);
    Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&v163);
    Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&v164);
    Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&v165);
    Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&v161);
    Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&v168);
    Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&v169);
    Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&v166);
    Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&v160);
    Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&v167);
    if ( v33 )
      ParsingSession::`scalar deleting destructor'(v33, v52);
    if ( a13 )
      *a13 = v186;
    return v189;
  }
  if ( !v185 )
  {
    if ( (unsigned int)DoesFileExist(v161, 0)
      || DpxExtractSingleFileFromCabinet(
           *v46,
           (struct CCbsPackage *)a1,
           *((_DWORD *)v190 + 368) != 0,
           *v36,
           *(const wchar_t **)(a11 + 40),
           L"desktopdeployment.cab") >= 0 )
    {
      *(_BYTE *)(a1 + 1058) = 1;
      *(_DWORD *)(a1 + 92) = 1;
    }
    else
    {
      Windows::AutoComPtr<IEnumCSI_PENDING_TRANSACTION>::Close(v46);
    }
  }
  if ( !*(_BYTE *)(a1 + 1058) )
  {
    if ( GetFileAttributesW(*(LPCWSTR *)(a11 + 32)) == -1 )
    {
      if ( !*v46 )
      {
        v58 = (struct IDpxJob **)Windows::AutoGenericHandleBase<void *,0,Windows::AutoGenericHandle<void *,0,&void CloseBcdStore(void *)>>::GetInitPointer(v46);
        v59 = Dpx_DpxNewJob(*v36, v58);
        v42 = v59;
        if ( v59 < 0 )
        {
          v185 = v59;
          if ( LogAdapter::g_Logger )
          {
            lpWideCharStr = *v36;
            LogAdapter::Logger::LogNumObjects<wchar_t const *>(
              (__int64)LogAdapter::g_Logger,
              0,
              3,
              (__int64)"Failed to create package extract job for location: {}",
              (__int64)&lpWideCharStr);
            v170 = (struct ParsingSession *)&v185;
            LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
              (__int64)LogAdapter::g_Logger,
              1,
              3,
              (__int64)": {}",
              (__int64)&v170);
          }
          v43 = 540;
          goto LABEL_69;
        }
        v60 = (*(__int64 (__fastcall **)(_QWORD, const wchar_t *, const wchar_t *))(**(_QWORD **)(a11 + 192) + 120LL))(
                *(_QWORD *)(a11 + 192),
                L"ignore_filenotfound_warnings",
                L"1");
        v42 = v60;
        if ( v60 < 0 )
        {
          v185 = v60;
          if ( LogAdapter::g_Logger )
          {
            LogAdapter::Logger::LogNumObjects<>(
              (__int64)LogAdapter::g_Logger,
              0,
              3,
              (struct Windows::Rtl::IRtlFormattedOutputStream *)"Failed to set DPX_OPTION_IGNORE_FNF_WARNINGS");
            lpWideCharStr = (LPCWCH)&v185;
            LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
              (__int64)LogAdapter::g_Logger,
              1,
              3,
              (__int64)": {}",
              (__int64)&lpWideCharStr);
          }
          v43 = 544;
          goto LABEL_69;
        }
        v46 = (struct IDpxJob **)(a11 + 192);
      }
      SingleFileFromCabinet = DpxExtractSingleFileFromCabinet(
                                *v46,
                                (struct CCbsPackage *)a1,
                                *((_DWORD *)v190 + 368) != 0,
                                *v36,
                                *(const wchar_t **)(a11 + 40),
                                v41);
      v42 = SingleFileFromCabinet;
      if ( SingleFileFromCabinet < 0 )
      {
        v185 = SingleFileFromCabinet;
        if ( LogAdapter::g_Logger )
        {
          LogAdapter::Logger::LogNumObjects<>(
            (__int64)LogAdapter::g_Logger,
            0,
            3,
            (struct Windows::Rtl::IRtlFormattedOutputStream *)"Failed to extract package manifest from cabinet");
          lpWideCharStr = (LPCWCH)&v185;
          LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
            (__int64)LogAdapter::g_Logger,
            1,
            3,
            (__int64)": {}",
            (__int64)&lpWideCharStr);
        }
        v43 = 558;
        goto LABEL_69;
      }
    }
    ImpersonatorBase::Unimpersonate((ImpersonatorBase *)&v174);
    v177 = *(ParsingSession ***)(a11 + 32);
    v180 = *(_QWORD *)(a11 + 40);
    *(_QWORD *)v176 = *v36;
    *(_QWORD *)v173 = *(_QWORD *)(a11 + 16);
    if ( LogAdapter::g_Logger )
      LogAdapter::Logger::LogNumObjects<wchar_t *,wchar_t *,wchar_t const *,wchar_t const *>(
        (_DWORD)LogAdapter::g_Logger,
        v62,
        v63,
        (unsigned int)"Opened cabinet package, package directory: {}, sandbox location: {}, cabinet location: {}, manifest location: {}",
        (__int64)v173,
        (__int64)v176,
        (__int64)&v180,
        (__int64)&v177);
    v64 = SczAllocFormatted(&v160, L"%ws.cat", v178);
    v24 = v64;
    if ( v64 < 0 )
    {
      v65 = 644;
LABEL_214:
      v75 = (unsigned int)v64;
      goto LABEL_215;
    }
    v66 = v160;
    v67 = SczAllocConcat2Sz(a11 + 48, *(_QWORD *)(a11 + 24), v160);
    v185 = v67;
    if ( v67 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x285,
        (unsigned int)"onecore\\base\\cbs\\core\\cbspackagepersistence.cpp",
        (const char *)(unsigned int)v67,
        (int)v158);
LABEL_144:
      ImpersonatorBase::Unimpersonate((ImpersonatorBase *)&v174);
      Windows::AutoGenericHandleBase<void *,1,Windows::AutoGenericHandle<void *,1,&void Windows::Detail::CloseWithNtCloseHandle(void *)>>::Close(&v188);
      Windows::AutoGenericHandleBase<void *,1,Windows::AutoGenericHandle<void *,1,&void Windows::Detail::CloseWithNtCloseHandle(void *)>>::Close(&ExistingTokenHandle);
      Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&v187);
      Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&v163);
      Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&v164);
      Windows::AutoNewPtr<ParsingSession>::~AutoNewPtr<ParsingSession>(&v170);
      Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&v165);
      Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&v161);
      Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&v168);
      Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&v169);
      Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&v166);
      Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&v160);
      Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&v167);
      Windows::AutoNewPtr<ParsingSession>::~AutoNewPtr<ParsingSession>(&v171);
      v24 = v185;
LABEL_330:
      wil::details::lambda_call__CCbsPackage::PrepareInitializeEx_::_2_::_lambda_1___::_lambda_call__CCbsPackage::PrepareInitializeEx_::_2_::_lambda_1___(v183);
      return v24;
    }
    if ( GetFileAttributesW(*(LPCWSTR *)(a11 + 48)) != -1 )
    {
LABEL_190:
      if ( !*(_BYTE *)(a1 + 1058) )
      {
        v98 = (_QWORD *)(a11 + 32);
        if ( GetFileAttributesW(*(LPCWSTR *)(a11 + 32)) == -1 )
        {
          *(_QWORD *)v173 = *v98;
          *(_QWORD *)v176 = v165;
          if ( (unsigned __int8)Windows::StringUtil::IsStringPrefixEqualByOrdinalCaseInvariant<wchar_t const *,wchar_t const *>(
                                  v176,
                                  v173) )
          {
            v99 = *v98;
            v177 = 0;
            v100 = FileFromPath(v99);
            v79 = SczAllocFromSz(&v177, v100);
            if ( v79 < 0 )
            {
              v101 = 792;
LABEL_195:
              wil::details::in1diag3::Return_Hr(
                retaddr,
                (void *)v101,
                (unsigned int)"onecore\\base\\cbs\\core\\cbspackagepersistence.cpp",
                (const char *)(unsigned int)v79,
                (int)v158);
              Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&v177);
LABEL_161:
              ImpersonatorBase::Unimpersonate((ImpersonatorBase *)&v174);
              Windows::AutoGenericHandleBase<void *,1,Windows::AutoGenericHandle<void *,1,&void Windows::Detail::CloseWithNtCloseHandle(void *)>>::Close(&v188);
              Windows::AutoGenericHandleBase<void *,1,Windows::AutoGenericHandle<void *,1,&void Windows::Detail::CloseWithNtCloseHandle(void *)>>::Close(&ExistingTokenHandle);
              Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&v187);
              Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&v163);
              Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&v164);
              Windows::AutoNewPtr<ParsingSession>::~AutoNewPtr<ParsingSession>(&v170);
              Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&v165);
              Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&v161);
              Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&v168);
              Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&v169);
              Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&v166);
              Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&v160);
              Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&v167);
              Windows::AutoNewPtr<ParsingSession>::~AutoNewPtr<ParsingSession>(&v171);
              v24 = v79;
              goto LABEL_330;
            }
            v122 = FileFromPath(*(_QWORD *)(a11 + 48));
            v79 = SczAllocFromSz(&v160, v122);
            if ( v79 < 0 )
            {
              v101 = 795;
              goto LABEL_195;
            }
            Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(a11 + 32);
            Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(a11 + 48);
            SessionSandbox = CCbsSession::CreateSessionSandbox(v190, *((void **)v190 + 141), 0, 0);
            v79 = SessionSandbox;
            if ( SessionSandbox < 0 )
            {
              v185 = SessionSandbox;
              if ( LogAdapter::g_Logger )
              {
                LogAdapter::Logger::LogPartial<>(v124, 3, "Failed to create private session store.");
                *(_QWORD *)v173 = &v185;
                LogAdapter::Logger::Log<Windows::WCP::Rtl::FormatHResultWrapper<long>>(v125, 3, ": {}", v173);
              }
              v101 = 801;
              goto LABEL_195;
            }
            v126 = v190;
            v127 = SczAllocConcat2Sz(a11 + 32, *((_QWORD *)v190 + 138), v177);
            v24 = v127;
            if ( v127 < 0 )
            {
              v128 = 804;
LABEL_279:
              wil::details::in1diag3::Return_Hr(
                retaddr,
                (void *)v128,
                (unsigned int)"onecore\\base\\cbs\\core\\cbspackagepersistence.cpp",
                (const char *)(unsigned int)v127,
                (int)v158);
              Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&v177);
              goto LABEL_216;
            }
            v127 = SczAllocConcat2Sz(a11 + 48, *((_QWORD *)v126 + 138), v160);
            v24 = v127;
            if ( v127 < 0 )
            {
              v128 = 807;
              goto LABEL_279;
            }
            Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&v177);
          }
        }
        v185 = 0;
        v129 = v190;
        v158 = *(wchar_t **)(a11 + 32);
        v24 = CopyManifestFilesAndVerifyContent(4 * (unsigned int)(unsigned __int8)v191, v190, a1, v178);
        if ( (v185 & 1) != 0 )
        {
          v186 |= 2u;
          goto LABEL_267;
        }
        if ( (v24 & 0x80000000) != 0 )
        {
          v185 = v24;
          if ( LogAdapter::g_Logger )
          {
            *(_QWORD *)v173 = *(_QWORD *)(a11 + 32);
            LogAdapter::Logger::LogPartial<wchar_t *>(
              v130,
              3,
              "Failed to copy manifest: {} to private store and verify the content.",
              v173);
            *(_QWORD *)v176 = &v185;
            LogAdapter::Logger::Log<Windows::WCP::Rtl::FormatHResultWrapper<long>>(v131, 3, ": {}", v176);
          }
          v75 = v24;
          v65 = 828;
          goto LABEL_215;
        }
LABEL_290:
        if ( !*(_BYTE *)(a1 + 1058) )
        {
          CbsIdentityFromAssemblyIdentity = GetCbsIdentityFromAssemblyIdentity(
                                              (const struct IDENTITY_TYPE *)(*((_QWORD *)v33 + 7) + 304LL),
                                              (struct CCbsIdentity **)(a1 + 112),
                                              0);
          v24 = CbsIdentityFromAssemblyIdentity;
          if ( CbsIdentityFromAssemblyIdentity < 0 )
          {
            v185 = CbsIdentityFromAssemblyIdentity;
            if ( LogAdapter::g_Logger )
            {
              LogAdapter::Logger::LogPartial<>(v133, 3, "Failed to get CbsIdentity for this package.");
              *(_QWORD *)v173 = &v185;
              LogAdapter::Logger::Log<Windows::WCP::Rtl::FormatHResultWrapper<long>>(v134, 3, ": {}", v173);
            }
            v75 = v24;
            v65 = 840;
            goto LABEL_215;
          }
          v135 = *(_QWORD *)(*((_QWORD *)v33 + 7) + 80LL);
          if ( v135 )
          {
            v64 = SczAllocFromSz(a1 + 1032, v135);
            v24 = v64;
            if ( v64 < 0 )
            {
              v65 = 844;
              goto LABEL_214;
            }
          }
          v136 = (const wchar_t **)(a1 + 120);
          v137 = (*(__int64 (__fastcall **)(_QWORD, __int64))(**(_QWORD **)(a1 + 112) + 72LL))(
                   *(_QWORD *)(a1 + 112),
                   a1 + 120);
          v24 = v137;
          if ( v137 < 0 )
          {
            v185 = v137;
            if ( LogAdapter::g_Logger )
            {
              LogAdapter::Logger::LogPartial<>(v138, 3, "Failed cache package identity in the package property.");
              *(_QWORD *)v173 = &v185;
              LogAdapter::Logger::Log<Windows::WCP::Rtl::FormatHResultWrapper<long>>(v139, 3, ": {}", v173);
            }
            v75 = v24;
            v65 = 848;
            goto LABEL_215;
          }
          *(_DWORD *)(a1 + 632) = *(_DWORD *)(*((_QWORD *)v33 + 7) + 24LL);
          v140 = *(_QWORD *)(*((_QWORD *)v33 + 7) + 272LL);
          if ( v140 )
            *(_QWORD *)(a1 + 600) = *(_QWORD *)(v140 + 8);
          if ( *(_BYTE *)(a1 + 1060) )
          {
            v157 = &qword_1802EB518;
            if ( *v136 )
              v157 = *v136;
            *(_QWORD *)v173 = v157;
            LogAdapter::TraceInfo<wchar_t const *>(
              "Skipping minimum servicing stack required check for Package: {}",
              v173);
          }
          else
          {
            v141 = *(_QWORD *)(a1 + 600);
            if ( v141 > v181 )
            {
              v24 = -2146498525;
              LODWORD(v190) = -2146498525;
              if ( LogAdapter::g_Logger )
              {
                v189 = (unsigned __int16)v181;
                v191 = WORD1(v181);
                LODWORD(v180) = WORD2(v181);
                LODWORD(v182) = (unsigned __int16)v141;
                LODWORD(v179) = WORD1(v141);
                LODWORD(v178) = WORD2(v141);
                v142 = &qword_1802EB518;
                v143 = HIWORD(v181);
                v144 = HIWORD(v141);
                v145 = *v136 == 0;
                LODWORD(v181) = HIWORD(v181);
                if ( !v145 )
                  v142 = *v136;
                *(_QWORD *)v176 = v142;
                LODWORD(v177) = v144;
                LogAdapter::Logger::LogPartial<wchar_t const *,int,int,int,int,int,int,int,int>(
                  v144,
                  v143,
                  (unsigned int)"Package \"{}\" requires Servicing Stack v{}.{}.{}.{} but current Servicing Stack is v{}.{}.{}.{}.",
                  (unsigned int)v176,
                  (__int64)&v177,
                  (__int64)&v178,
                  (__int64)&v179,
                  (__int64)&v182,
                  (__int64)&v181,
                  (__int64)&v180,
                  (__int64)&v191,
                  (__int64)&v189);
                *(_QWORD *)v173 = &v190;
                LogAdapter::Logger::Log<Windows::WCP::Rtl::FormatHResultWrapper<long>>(v146, 3, ": {}", v173);
              }
              v75 = 2148468771LL;
              v65 = 881;
              goto LABEL_215;
            }
            if ( (unsigned int)CCbsSession::IsOffline(v129) )
            {
              v190 = 0;
              OfflineServicingStackVersion = CCbsSession::GetOfflineServicingStackVersion(
                                               v147,
                                               (unsigned __int64 *)&v190);
              v24 = OfflineServicingStackVersion;
              if ( OfflineServicingStackVersion < 0 )
              {
                LODWORD(v190) = OfflineServicingStackVersion;
                if ( LogAdapter::g_Logger )
                {
                  LogAdapter::Logger::LogPartial<>(v149, 3, "Failed to get offline servicing stack version.");
                  *(_QWORD *)v173 = &v190;
                  LogAdapter::Logger::Log<Windows::WCP::Rtl::FormatHResultWrapper<long>>(v150, 3, ": {}", v173);
                }
                v75 = v24;
                v65 = 887;
                goto LABEL_215;
              }
              v151 = (unsigned __int64)v190;
              v152 = *(_QWORD *)(a1 + 600);
              if ( !v190 )
                v151 = v181;
              if ( v152 > v151 )
              {
                v24 = -2146498525;
                v191 = -2146498525;
                if ( LogAdapter::g_Logger )
                {
                  LODWORD(v177) = (unsigned __int16)v151;
                  LODWORD(v178) = WORD1(v151);
                  LODWORD(v179) = WORD2(v151);
                  LODWORD(v181) = (unsigned __int16)v152;
                  LODWORD(v180) = WORD1(v152);
                  v185 = WORD2(v152);
                  v153 = &qword_1802EB518;
                  v154 = HIWORD(v151);
                  v155 = HIWORD(v152);
                  v145 = *v136 == 0;
                  LODWORD(v182) = v154;
                  if ( !v145 )
                    v153 = *v136;
                  *(_QWORD *)v176 = v153;
                  v189 = v155;
                  LogAdapter::Logger::LogPartial<wchar_t const *,int,int,int,int,int,int,int,int>(
                    v154,
                    v155,
                    (unsigned int)"Package \"{}\" requires Servicing Stack v{}.{}.{}.{} but offline Servicing Stack is v{}.{}.{}.{}.",
                    (unsigned int)v176,
                    (__int64)&v189,
                    (__int64)&v185,
                    (__int64)&v180,
                    (__int64)&v181,
                    (__int64)&v182,
                    (__int64)&v179,
                    (__int64)&v178,
                    (__int64)&v177);
                  *(_QWORD *)v173 = &v191;
                  LogAdapter::Logger::Log<Windows::WCP::Rtl::FormatHResultWrapper<long>>(v156, 3, ": {}", v173);
                }
                v75 = 2148468771LL;
                v65 = 906;
                goto LABEL_215;
              }
            }
          }
        }
        if ( a11 )
          *(_DWORD *)(a11 + 8) = a9;
        v186 |= 1u;
        v171 = 0;
        *v179 = v33;
        ImpersonatorBase::Unimpersonate((ImpersonatorBase *)&v174);
        Windows::AutoGenericHandleBase<void *,1,Windows::AutoGenericHandle<void *,1,&void Windows::Detail::CloseWithNtCloseHandle(void *)>>::Close(&v188);
        Windows::AutoGenericHandleBase<void *,1,Windows::AutoGenericHandle<void *,1,&void Windows::Detail::CloseWithNtCloseHandle(void *)>>::Close(&ExistingTokenHandle);
        Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&v187);
        Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&v163);
        Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&v164);
        Windows::AutoNewPtr<ParsingSession>::~AutoNewPtr<ParsingSession>(&v170);
        Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&v165);
        Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&v161);
        Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&v168);
        Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&v169);
        Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&v166);
        Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&v160);
        Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&v167);
        Windows::AutoNewPtr<ParsingSession>::~AutoNewPtr<ParsingSession>(&v171);
        v24 = 0;
        goto LABEL_330;
      }
LABEL_289:
      v129 = v190;
      goto LABEL_290;
    }
    v68 = NestableImpersonator::Impersonate((NestableImpersonator *)&v174);
    v70 = v68;
    if ( v68 < 0 )
    {
      v185 = v68;
      if ( LogAdapter::g_Logger )
      {
        *(_QWORD *)v173 = *(_QWORD *)(a11 + 24);
        lpWideCharStr = *(LPCWCH *)(a11 + 40);
        *(_QWORD *)v176 = v41;
        LogAdapter::Logger::LogPartial<wchar_t *,wchar_t *,wchar_t *>(
          (_DWORD)lpWideCharStr,
          v69,
          (unsigned int)"Failed to impersonate user to extract from cabinet: {}, package manifest: {}, sandbox: {}",
          (unsigned int)&lpWideCharStr,
          (__int64)v176,
          (__int64)v173);
        v190 = (CCbsSession *)&v185;
        LogAdapter::Logger::Log<Windows::WCP::Rtl::FormatHResultWrapper<long>>(v71, 3, ": {}", &v190);
      }
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x28B,
        (unsigned int)"onecore\\base\\cbs\\core\\cbspackagepersistence.cpp",
        (const char *)v70,
        (int)v158);
      ImpersonatorBase::Unimpersonate((ImpersonatorBase *)&v174);
      Windows::AutoGenericHandleBase<void *,1,Windows::AutoGenericHandle<void *,1,&void Windows::Detail::CloseWithNtCloseHandle(void *)>>::Close(&v188);
      Windows::AutoGenericHandleBase<void *,1,Windows::AutoGenericHandle<void *,1,&void Windows::Detail::CloseWithNtCloseHandle(void *)>>::Close(&ExistingTokenHandle);
      Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&v187);
      Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&v163);
      Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&v164);
      Windows::AutoNewPtr<ParsingSession>::~AutoNewPtr<ParsingSession>(&v170);
      Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&v165);
      Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&v161);
      Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&v168);
      Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&v169);
      Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&v166);
      Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&v160);
      Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&v167);
      Windows::AutoNewPtr<ParsingSession>::~AutoNewPtr<ParsingSession>(&v171);
      v24 = v70;
      goto LABEL_330;
    }
    v72 = v190;
    v73 = DpxExtractSingleFileFromCabinet(
            *(struct IDpxJob **)(a11 + 192),
            (struct CCbsPackage *)a1,
            *((_DWORD *)v190 + 368) != 0,
            *(const wchar_t **)(a11 + 24),
            *(const wchar_t **)(a11 + 40),
            v66);
    v24 = v73;
    if ( (unsigned int)(v73 + 2147024894) > 1 )
    {
      if ( v73 < 0 )
      {
        v185 = v73;
        if ( LogAdapter::g_Logger )
        {
          *(_QWORD *)v173 = *(_QWORD *)(a11 + 40);
          *(_QWORD *)v176 = *(_QWORD *)(a11 + 48);
          LogAdapter::Logger::LogPartial<wchar_t *,wchar_t *>(
            v176[0],
            3,
            (unsigned int)"Failed to extract package catalog {} from cabinet {}",
            (unsigned int)v176,
            (__int64)v173);
          lpWideCharStr = (LPCWCH)&v185;
          LogAdapter::Logger::Log<Windows::WCP::Rtl::FormatHResultWrapper<long>>(v74, 3, ": {}", &lpWideCharStr);
        }
        v75 = v24;
        v65 = 719;
        goto LABEL_215;
      }
      goto LABEL_185;
    }
    if ( !Windows::AutoNewPtr<ParsingSession>::Allocate<>(&v170) )
    {
      v24 = -2147024882;
      v65 = 670;
      v75 = 2147942414LL;
LABEL_215:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v65,
        (unsigned int)"onecore\\base\\cbs\\core\\cbspackagepersistence.cpp",
        (const char *)v75,
        (int)v158);
      goto LABEL_216;
    }
    v77 = v170;
    v78 = ParseCbsPackage(0, *(const wchar_t *const *)(a11 + 32), v170, v76);
    v79 = v78;
    if ( v78 < 0 )
    {
      v185 = v78;
      if ( LogAdapter::g_Logger )
      {
        *(_QWORD *)v173 = *(_QWORD *)(a11 + 32);
        LogAdapter::Logger::LogPartial<wchar_t *>(*(_QWORD *)v173, 3, "Failed to parse the package manifest {}", v173);
        *(_QWORD *)v176 = &v185;
        LogAdapter::Logger::Log<Windows::WCP::Rtl::FormatHResultWrapper<long>>(v80, 3, ": {}", v176);
      }
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x2A1,
        (unsigned int)"onecore\\base\\cbs\\core\\cbspackagepersistence.cpp",
        (const char *)(unsigned int)v79,
        (int)v158);
      goto LABEL_161;
    }
    lpWideCharStr = 0;
    v81 = (struct CCbsIdentity **)Windows::AutoGenericHandleBase<void *,0,Windows::AutoGenericHandle<void *,0,&void CloseBcdStore(void *)>>::GetInitPointer(&lpWideCharStr);
    v82 = GetCbsIdentityFromAssemblyIdentity((const struct IDENTITY_TYPE *)(*((_QWORD *)v77 + 7) + 304LL), v81, 0);
    v24 = v82;
    if ( v82 >= 0 )
    {
      (*(void (__fastcall **)(LPCWCH, __int64 *))(*(_QWORD *)lpWideCharStr + 72LL))(lpWideCharStr, &v187);
      v87 = SczAllocFormatted(&v164, L"%ws.mum", v187);
      v24 = v87;
      if ( v87 < 0 )
      {
        v86 = (unsigned int)v87;
        v85 = 682;
        goto LABEL_167;
      }
      v88 = SczAllocFormatted(&v163, L"%ws.cat", v187);
      v24 = v88;
      if ( v88 < 0 )
      {
        v86 = (unsigned int)v88;
        v85 = 683;
        goto LABEL_167;
      }
      Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(a11 + 32);
      Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(a11 + 48);
      v89 = v164;
      v90 = SczAllocConcat2Sz(a11 + 32, *(_QWORD *)(a11 + 24), v164);
      v24 = v90;
      if ( v90 < 0 )
      {
        v86 = (unsigned int)v90;
        v85 = 689;
        goto LABEL_167;
      }
      v91 = v163;
      v92 = SczAllocConcat2Sz(a11 + 48, *(_QWORD *)(a11 + 24), v163);
      v185 = v92;
      if ( v92 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x2B4,
          (unsigned int)"onecore\\base\\cbs\\core\\cbspackagepersistence.cpp",
          (const char *)(unsigned int)v92,
          (int)v158);
        Windows::AutoComPtr<IEnumCSI_PENDING_TRANSACTION>::Close(&lpWideCharStr);
        goto LABEL_144;
      }
      v93 = DpxExtractSingleFileFromCabinet(
              *(struct IDpxJob **)(a11 + 192),
              (struct CCbsPackage *)a1,
              *((_DWORD *)v190 + 368) != 0,
              *(const wchar_t **)(a11 + 24),
              *(const wchar_t **)(a11 + 40),
              v89);
      v79 = v93;
      if ( v93 < 0 )
      {
        v185 = v93;
        if ( LogAdapter::g_Logger )
        {
          LogAdapter::Logger::LogPartial<>(v94, 3, "Failed to extract package manifest from cabinet");
          *(_QWORD *)v173 = &v185;
          LogAdapter::Logger::Log<Windows::WCP::Rtl::FormatHResultWrapper<long>>(v95, 3, ": {}", v173);
        }
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x2BE,
          (unsigned int)"onecore\\base\\cbs\\core\\cbspackagepersistence.cpp",
          (const char *)(unsigned int)v79,
          v159);
        Windows::AutoComPtr<IEnumCSI_PENDING_TRANSACTION>::Close(&lpWideCharStr);
        goto LABEL_161;
      }
      v72 = v190;
      v96 = DpxExtractSingleFileFromCabinet(
              *(struct IDpxJob **)(a11 + 192),
              (struct CCbsPackage *)a1,
              *((_DWORD *)v190 + 368) != 0,
              *(const wchar_t **)(a11 + 24),
              *(const wchar_t **)(a11 + 40),
              v91);
      v24 = v96;
      if ( v96 >= 0 )
      {
        Windows::AutoComPtr<IEnumCSI_PENDING_TRANSACTION>::Close(&lpWideCharStr);
LABEL_185:
        if ( (a10 & 8) == 0 )
        {
          v64 = SczAllocFormatted(&v166, L"%ws.ses", v178);
          v24 = v64;
          if ( v64 < 0 )
          {
            v65 = 728;
            goto LABEL_214;
          }
          DpxExtractSingleFileFromCabinet(
            *(struct IDpxJob **)(a11 + 192),
            (struct CCbsPackage *)a1,
            *((_DWORD *)v72 + 368) != 0,
            *(const wchar_t **)(a11 + 24),
            *(const wchar_t **)(a11 + 40),
            v166);
        }
        ImpersonatorBase::Unimpersonate((ImpersonatorBase *)&v174);
        goto LABEL_190;
      }
      v185 = v96;
      if ( LogAdapter::g_Logger )
      {
        *(_QWORD *)v173 = *(_QWORD *)(a11 + 40);
        *(_QWORD *)v176 = *(_QWORD *)(a11 + 48);
        LogAdapter::Logger::LogPartial<wchar_t *,wchar_t *>(
          v176[0],
          3,
          (unsigned int)"Failed to extract package catalog {} from cabinet {}",
          (unsigned int)v176,
          (__int64)v173);
        v190 = (CCbsSession *)&v185;
        LogAdapter::Logger::Log<Windows::WCP::Rtl::FormatHResultWrapper<long>>(v97, 3, ": {}", &v190);
      }
      v85 = 714;
    }
    else
    {
      v185 = v82;
      if ( LogAdapter::g_Logger )
      {
        LogAdapter::Logger::LogPartial<>(v83, 3, "Failed to get CbsIdentity for this package.");
        *(_QWORD *)v173 = &v185;
        LogAdapter::Logger::Log<Windows::WCP::Rtl::FormatHResultWrapper<long>>(v84, 3, ": {}", v173);
      }
      v85 = 678;
    }
    v86 = v24;
LABEL_167:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v85,
      (unsigned int)"onecore\\base\\cbs\\core\\cbspackagepersistence.cpp",
      (const char *)v86,
      (int)v158);
    Windows::AutoComPtr<IEnumCSI_PENDING_TRANSACTION>::Close(&lpWideCharStr);
LABEL_216:
    ImpersonatorBase::Unimpersonate((ImpersonatorBase *)&v174);
    Windows::AutoGenericHandleBase<void *,1,Windows::AutoGenericHandle<void *,1,&void Windows::Detail::CloseWithNtCloseHandle(void *)>>::Close(&v188);
    Windows::AutoGenericHandleBase<void *,1,Windows::AutoGenericHandle<void *,1,&void Windows::Detail::CloseWithNtCloseHandle(void *)>>::Close(&ExistingTokenHandle);
    Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&v187);
    Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&v163);
    Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&v164);
    Windows::AutoNewPtr<ParsingSession>::~AutoNewPtr<ParsingSession>(&v170);
    Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&v165);
    Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&v161);
    Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&v168);
    Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&v169);
    Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&v166);
    Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&v160);
    Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&v167);
    Windows::AutoNewPtr<ParsingSession>::~AutoNewPtr<ParsingSession>(&v171);
    goto LABEL_330;
  }
  v53 = (_QWORD *)(a1 + 112);
  v54 = CreateCbsIdentity((struct CCbsIdentity **)(a1 + 112));
  v24 = v54;
  if ( v54 < 0 )
  {
    v185 = v54;
    if ( LogAdapter::g_Logger )
    {
      LogAdapter::Logger::LogNumObjects<>(
        (__int64)LogAdapter::g_Logger,
        0,
        3,
        (struct Windows::Rtl::IRtlFormattedOutputStream *)"Failed to allocate CbsIdentity for onepackage.");
      lpWideCharStr = (LPCWCH)&v185;
      LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
        (__int64)LogAdapter::g_Logger,
        1,
        3,
        (__int64)": {}",
        (__int64)&lpWideCharStr);
    }
    v34 = 522;
    goto LABEL_44;
  }
  v55 = (*(__int64 (__fastcall **)(_QWORD, const wchar_t *))(*(_QWORD *)*v53 + 56LL))(*v53, L"OnePackage~~~~0.0.0.0");
  v24 = v55;
  if ( v55 < 0 )
  {
    v185 = v55;
    if ( LogAdapter::g_Logger )
    {
      LogAdapter::Logger::LogNumObjects<>(
        (__int64)LogAdapter::g_Logger,
        0,
        3,
        (struct Windows::Rtl::IRtlFormattedOutputStream *)"Failed to get CbsIdentity for this onepackage.");
      lpWideCharStr = (LPCWCH)&v185;
      LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
        (__int64)LogAdapter::g_Logger,
        1,
        3,
        (__int64)": {}",
        (__int64)&lpWideCharStr);
    }
    v34 = 525;
    goto LABEL_44;
  }
  v56 = (*(__int64 (__fastcall **)(_QWORD, __int64))(*(_QWORD *)*v53 + 72LL))(*v53, a1 + 120);
  v24 = v56;
  if ( v56 < 0 )
  {
    v185 = v56;
    if ( LogAdapter::g_Logger )
    {
      LogAdapter::Logger::LogNumObjects<>(
        (__int64)LogAdapter::g_Logger,
        0,
        3,
        (struct Windows::Rtl::IRtlFormattedOutputStream *)"Failed to cache package identity in the package property.");
      lpWideCharStr = (LPCWCH)&v185;
      LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
        (__int64)LogAdapter::g_Logger,
        1,
        3,
        (__int64)": {}",
        (__int64)&lpWideCharStr);
    }
    v34 = 528;
    goto LABEL_44;
  }
  CCbsPackage::SetCurrentState(a1, 0, 1);
  ImpersonatorBase::Unimpersonate((ImpersonatorBase *)&v174);
  Windows::AutoGenericHandleBase<void *,1,Windows::AutoGenericHandle<void *,1,&void Windows::Detail::CloseWithNtCloseHandle(void *)>>::Close(&v188);
  Windows::AutoGenericHandleBase<void *,1,Windows::AutoGenericHandle<void *,1,&void Windows::Detail::CloseWithNtCloseHandle(void *)>>::Close(&ExistingTokenHandle);
  Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&v187);
  Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&v163);
  Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&v164);
  Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&v165);
  Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&v161);
  Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&v168);
  Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&v169);
  Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&v166);
  Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&v160);
  Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&v167);
  if ( v33 )
    ParsingSession::`scalar deleting destructor'(v33, v57);
  if ( a13 )
    *a13 = v186;
  return 0;
}

```

## disassembly

```asm
0x18009d188  mov     [rsp-8+arg_8], rbx
0x18009d18d  push    rbp
0x18009d18e  push    rsi
0x18009d18f  push    rdi
0x18009d190  push    r12
0x18009d192  push    r13
0x18009d194  push    r14
0x18009d196  push    r15
0x18009d198  lea     rbp, [rsp-70h]
0x18009d19d  sub     rsp, 170h
0x18009d1a4  mov     rax, cs:__security_cookie
0x18009d1ab  xor     rax, rsp
0x18009d1ae  mov     [rbp+0A0h+var_40], rax
0x18009d1b2  mov     rax, [rbp+0A0h+arg_20]
0x18009d1b9  mov     r13, rcx
0x18009d1bc  mov     rcx, [rbp+0A0h+arg_28]
0x18009d1c3  mov     rbx, r8
0x18009d1c6  mov     r14, [rbp+0A0h+arg_38]
0x18009d1cd  mov     rsi, r9
0x18009d1d0  mov     r12, [rbp+0A0h+lpFileName]
0x18009d1d7  mov     r15, [rbp+0A0h+arg_50]
0x18009d1de  mov     [rbp+0A0h+lpWideCharStr], rax
0x18009d1e2  lea     rax, [rbp+0A0h+arg_60]
0x18009d1e9  mov     [rbp+0A0h+var_88], rax
0x18009d1ed  lea     rax, [rbp+0A0h+var_6C]
0x18009d1f1  mov     [rbp+0A0h+var_80], rax
0x18009d1f5  mov     rax, cs:?vServicingStackVersion@@3_KA; unsigned __int64 vServicingStackVersion
0x18009d1fc  mov     [rbp+0A0h+var_58], edx
0x18009d1ff  xor     edx, edx
0x18009d201  mov     [rbp+0A0h+var_98], rax
0x18009d205  mov     eax, [rbp+0A0h+arg_40]
0x18009d20b  mov     [rbp+0A0h+var_A0], rcx
0x18009d20f  mov     rcx, [rbp+0A0h+arg_58]
0x18009d216  mov     [rbp+0A0h+var_90], r9
0x18009d21a  mov     [rbp+0A0h+var_50], rbx
0x18009d21e  mov     [rbp+0A0h+var_B0], r14
0x18009d222  mov     [rbp+0A0h+var_A8], rcx
0x18009d226  mov     [rbp+0A0h+var_6C], edx
0x18009d229  mov     [rbp+0A0h+var_78], 1
0x18009d22d  mov     [rbp+0A0h+var_E8], rdx
0x18009d231  mov     [rbp+0A0h+var_108], rdx
0x18009d235  mov     [rsp+1A0h+var_140], rdx
0x18009d23a  mov     [rbp+0A0h+var_110], rdx
0x18009d23e  mov     [rbp+0A0h+var_F8], rdx
0x18009d242  mov     [rbp+0A0h+var_100], rdx
0x18009d246  mov     [rsp+1A0h+var_138], rdx
0x18009d24b  mov     [rbp+0A0h+var_118], rdx
0x18009d24f  mov     [rbp+0A0h+var_F0], rdx
0x18009d253  mov     [rbp+0A0h+var_120], rdx
0x18009d257  mov     [rsp+1A0h+var_128], rdx
0x18009d25c  mov     [rbp+0A0h+var_68], rdx
0x18009d260  cmp     eax, 1
0x18009d263  jz      short loc_18009D272
0x18009d265  cmp     eax, 0FFFFFFFEh
0x18009d268  jle     short loc_18009D272
0x18009d26a  mov     dil, 1
0x18009d26d  cmp     eax, 4
0x18009d270  jl      short loc_18009D275
0x18009d272  mov     dil, dl
0x18009d275  mov     [rsp+1A0h+ExistingTokenHandle], rdx
0x18009d27a  mov     [rbp+0A0h+var_60], rdx
0x18009d27e  test    dil, dil
0x18009d281  jnz     loc_18009D32F
0x18009d287  test    r9, r9
0x18009d28a  jnz     loc_18009D32F
0x18009d290  lea     rcx, [rsp+1A0h+ExistingTokenHandle]
0x18009d295  call    ?GetInitPointer@?$AutoGenericHandleBase@PEAX$00V?$AutoGenericHandle@PEAX$00$1?CloseWithNtCloseHandle@Detail@Windows@@YAXPEAX@Z@Windows@@@Windows@@QEAAPEAPEAXXZ; Windows::AutoGenericHandleBase<void *,1,Windows::AutoGenericHandle<void *,1,&Windows::Detail::CloseWithNtCloseHandle(void *)>>::GetInitPointer(void)
0x18009d29a  mov     rcx, rax; void **
0x18009d29d  call    ?GetNonTiToken@@YAJPEAPEAX@Z; GetNonTiToken(void * *)
0x18009d2a2  lea     r8, aUnableToGetNon; "Unable to get non-TI token."
0x18009d2a9  mov     edx, eax
0x18009d2ab  mov     ecx, 1
0x18009d2b0  mov     ebx, eax
0x18009d2b2  call    ??$TraceAtLevelIfFailed@J$$V@LogAdapter@@YAXW4LogLevel@0@JQEBD@Z; LogAdapter::TraceAtLevelIfFailed<long,>(LogAdapter::LogLevel,long,char const * const)
0x18009d2b7  xor     edx, edx
0x18009d2b9  test    ebx, ebx
0x18009d2bb  js      short loc_18009D321
0x18009d2bd  lea     rcx, [rbp+0A0h+var_60]
0x18009d2c1  call    ?GetInitPointer@?$AutoGenericHandleBase@PEAX$00V?$AutoGenericHandle@PEAX$00$1?CloseWithNtCloseHandle@Detail@Windows@@YAXPEAX@Z@Windows@@@Windows@@QEAAPEAPEAXXZ; Windows::AutoGenericHandleBase<void *,1,Windows::AutoGenericHandle<void *,1,&Windows::Detail::CloseWithNtCloseHandle(void *)>>::GetInitPointer(void)
0x18009d2c6  mov     rcx, [rsp+1A0h+ExistingTokenHandle]; ExistingTokenHandle
0x18009d2cb  mov     r8, rax; DuplicateTokenHandle
0x18009d2ce  mov     edx, 2; ImpersonationLevel
0x18009d2d3  call    cs:__imp_DuplicateToken
0x18009d2da  nop     dword ptr [rax+rax+00h]
0x18009d2df  xor     edx, edx
0x18009d2e1  test    eax, eax
0x18009d2e3  jnz     short loc_18009D319
0x18009d2e5  call    cs:__imp_GetLastError
0x18009d2ec  nop     dword ptr [rax+rax+00h]
0x18009d2f1  mov     ebx, eax
0x18009d2f3  test    eax, eax
0x18009d2f5  jle     short loc_18009D300
0x18009d2f7  movzx   ebx, ax
0x18009d2fa  or      ebx, 80070000h
0x18009d300  lea     r8, aUnableToDuplic_1; "Unable to duplicate non-TI token."
0x18009d307  mov     edx, ebx
0x18009d309  mov     ecx, 1
0x18009d30e  call    ??$TraceAtLevelIfFailed@J$$V@LogAdapter@@YAXW4LogLevel@0@JQEBD@Z; LogAdapter::TraceAtLevelIfFailed<long,>(LogAdapter::LogLevel,long,char const * const)
0x18009d313  xor     edx, edx
0x18009d315  test    ebx, ebx
0x18009d317  js      short loc_18009D321
0x18009d319  mov     rsi, [rbp+0A0h+var_60]
0x18009d31d  mov     [rbp+0A0h+var_90], rsi
0x18009d321  mov     rbx, [rbp+0A0h+var_50]
0x18009d325  mov     eax, [rbp+0A0h+arg_40]
0x18009d32b  mov     rcx, [rbp+0A0h+var_A8]
0x18009d32f  mov     [rbp+0A0h+var_D0], rsi
0x18009d333  mov     [rbp+0A0h+var_C8], dl
0x18009d336  test    dil, dil
0x18009d339  jnz     loc_18009D448
0x18009d33f  test    rsi, rsi
0x18009d342  jnz     loc_18009D448
0x18009d348  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x18009d34f  mov     ebx, 800F0800h
0x18009d354  mov     [rbp+0A0h+var_70], ebx
0x18009d357  test    rcx, rcx
0x18009d35a  jz      short loc_18009D39A
0x18009d35c  lea     r14d, [rsi+3]
0x18009d360  xor     edx, edx
0x18009d362  mov     r8d, r14d
0x18009d365  lea     r9, aAUserTokenIsRe; "A User token is required on non-existin"...
0x18009d36c  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x18009d371  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x18009d378  lea     rax, [rbp+0A0h+var_70]
0x18009d37c  mov     [rbp+0A0h+lpWideCharStr], rax
0x18009d380  lea     r9, asc_1802EE7AC; ": {}"
0x18009d387  lea     rax, [rbp+0A0h+lpWideCharStr]
0x18009d38b  mov     r8d, r14d
0x18009d38e  mov     dl, 1
0x18009d390  mov     [rsp+1A0h+var_180], rax; int
0x18009d395  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x18009d39a  mov     edx, 16Fh; void *
0x18009d39f  mov     rcx, [rbp+0A8h]; this
0x18009d3a6  lea     r8, aOnecoreBaseCbs_138; "onecore\\base\\cbs\\core\\cbspackageper"...
0x18009d3ad  mov     r9d, ebx; char *
0x18009d3b0  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18009d3b5  lea     rcx, [rbp+0A0h+var_D0]; this
0x18009d3b9  call    ?Unimpersonate@ImpersonatorBase@@QEAAXXZ; ImpersonatorBase::Unimpersonate(void)
0x18009d3be  lea     rcx, [rbp+0A0h+var_60]
0x18009d3c2  call    ?Close@?$AutoGenericHandleBase@PEAX$00V?$AutoGenericHandle@PEAX$00$1?CloseWithNtCloseHandle@Detail@Windows@@YAXPEAX@Z@Windows@@@Windows@@QEAAXXZ; Windows::AutoGenericHandleBase<void *,1,Windows::AutoGenericHandle<void *,1,&Windows::Detail::CloseWithNtCloseHandle(void *)>>::Close(void)
0x18009d3c7  lea     rcx, [rsp+1A0h+ExistingTokenHandle]
0x18009d3cc  call    ?Close@?$AutoGenericHandleBase@PEAX$00V?$AutoGenericHandle@PEAX$00$1?CloseWithNtCloseHandle@Detail@Windows@@YAXPEAX@Z@Windows@@@Windows@@QEAAXXZ; Windows::AutoGenericHandleBase<void *,1,Windows::AutoGenericHandle<void *,1,&Windows::Detail::CloseWithNtCloseHandle(void *)>>::Close(void)
0x18009d3d1  lea     rcx, [rbp+0A0h+var_68]
0x18009d3d5  call    ?Close@?$AutoGenericHandleBase@PEA_W$0A@VAutoScz@@@Windows@@QEAAXXZ; Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(void)
0x18009d3da  lea     rcx, [rsp+1A0h+var_128]
0x18009d3df  call    ?Close@?$AutoGenericHandleBase@PEA_W$0A@VAutoScz@@@Windows@@QEAAXXZ; Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(void)
0x18009d3e4  lea     rcx, [rbp+0A0h+var_120]
0x18009d3e8  call    ?Close@?$AutoGenericHandleBase@PEA_W$0A@VAutoScz@@@Windows@@QEAAXXZ; Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(void)
0x18009d3ed  lea     rcx, [rbp+0A0h+var_118]
0x18009d3f1  call    ?Close@?$AutoGenericHandleBase@PEA_W$0A@VAutoScz@@@Windows@@QEAAXXZ; Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(void)
0x18009d3f6  lea     rcx, [rsp+1A0h+var_138]
0x18009d3fb  call    ?Close@?$AutoGenericHandleBase@PEA_W$0A@VAutoScz@@@Windows@@QEAAXXZ; Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(void)
0x18009d400  lea     rcx, [rbp+0A0h+var_100]
0x18009d404  call    ?Close@?$AutoGenericHandleBase@PEA_W$0A@VAutoScz@@@Windows@@QEAAXXZ; Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(void)
0x18009d409  lea     rcx, [rbp+0A0h+var_F8]
0x18009d40d  call    ?Close@?$AutoGenericHandleBase@PEA_W$0A@VAutoScz@@@Windows@@QEAAXXZ; Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(void)
0x18009d412  lea     rcx, [rbp+0A0h+var_110]
0x18009d416  call    ?Close@?$AutoGenericHandleBase@PEA_W$0A@VAutoScz@@@Windows@@QEAAXXZ; Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(void)
0x18009d41b  lea     rcx, [rsp+1A0h+var_140]
0x18009d420  call    ?Close@?$AutoGenericHandleBase@PEA_W$0A@VAutoScz@@@Windows@@QEAAXXZ; Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(void)
0x18009d425  lea     rcx, [rbp+0A0h+var_108]
0x18009d429  call    ?Close@?$AutoGenericHandleBase@PEA_W$0A@VAutoScz@@@Windows@@QEAAXXZ; Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(void)
0x18009d42e  mov     rdx, [rbp+0A0h+arg_60]
0x18009d435  test    rdx, rdx
0x18009d438  jz      loc_18009F6DC
0x18009d43e  mov     ecx, [rbp+0A0h+var_6C]
0x18009d441  mov     [rdx], ecx
0x18009d443  jmp     loc_18009F6DC
0x18009d448  test    rcx, rcx
0x18009d44b  jnz     short loc_18009D4AB
0x18009d44d  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x18009d454  mov     ebx, 80004003h
0x18009d459  mov     [rbp+0A0h+var_70], ebx
0x18009d45c  test    rcx, rcx
0x18009d45f  jz      short loc_18009D4A1
0x18009d461  mov     r14d, 3
0x18009d467  lea     r9, aNoParsingSessi; "No parsing session result specified"
0x18009d46e  mov     r8d, r14d
0x18009d471  xor     edx, edx
0x18009d473  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x18009d478  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x18009d47f  lea     rax, [rbp+0A0h+var_70]
0x18009d483  mov     [rbp+0A0h+lpWideCharStr], rax
0x18009d487  lea     r9, asc_1802EE7AC; ": {}"
0x18009d48e  lea     rax, [rbp+0A0h+lpWideCharStr]
0x18009d492  mov     r8d, r14d
0x18009d495  mov     dl, 1
0x18009d497  mov     [rsp+1A0h+var_180], rax
0x18009d49c  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x18009d4a1  mov     edx, 171h
0x18009d4a6  jmp     loc_18009D39F
0x18009d4ab  mov     [r13+360h], eax
0x18009d4b2  lea     rcx, [rbp+0A0h+var_E8]
0x18009d4b6  mov     eax, [rbp+0A0h+arg_48]
0x18009d4bc  mov     [r13+68h], eax
0x18009d4c0  mov     [r13+422h], dl
0x18009d4c7  call    ??$Allocate@$$V@?$AutoNewPtr@UParsingSession@@@Windows@@QEAAPEAUParsingSession@@XZ; Windows::AutoNewPtr<ParsingSession>::Allocate<>(void)
0x18009d4cc  test    rax, rax
0x18009d4cf  jnz     loc_18009D596
0x18009d4d5  mov     rcx, [rbp+0A8h]; this
0x18009d4dc  lea     r8, aOnecoreBaseCbs_138; "onecore\\base\\cbs\\core\\cbspackageper"...
0x18009d4e3  mov     ebx, 8007000Eh
0x18009d4e8  mov     edx, 177h; void *
0x18009d4ed  mov     r9d, ebx; char *
0x18009d4f0  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18009d4f5  lea     rcx, [rbp+0A0h+var_D0]; this
0x18009d4f9  call    ?Unimpersonate@ImpersonatorBase@@QEAAXXZ; ImpersonatorBase::Unimpersonate(void)
0x18009d4fe  lea     rcx, [rbp+0A0h+var_60]
0x18009d502  call    ?Close@?$AutoGenericHandleBase@PEAX$00V?$AutoGenericHandle@PEAX$00$1?CloseWithNtCloseHandle@Detail@Windows@@YAXPEAX@Z@Windows@@@Windows@@QEAAXXZ; Windows::AutoGenericHandleBase<void *,1,Windows::AutoGenericHandle<void *,1,&Windows::Detail::CloseWithNtCloseHandle(void *)>>::Close(void)
0x18009d507  lea     rcx, [rsp+1A0h+ExistingTokenHandle]
0x18009d50c  call    ?Close@?$AutoGenericHandleBase@PEAX$00V?$AutoGenericHandle@PEAX$00$1?CloseWithNtCloseHandle@Detail@Windows@@YAXPEAX@Z@Windows@@@Windows@@QEAAXXZ; Windows::AutoGenericHandleBase<void *,1,Windows::AutoGenericHandle<void *,1,&Windows::Detail::CloseWithNtCloseHandle(void *)>>::Close(void)
0x18009d511  lea     rcx, [rbp+0A0h+var_68]
0x18009d515  call    ?Close@?$AutoGenericHandleBase@PEA_W$0A@VAutoScz@@@Windows@@QEAAXXZ; Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(void)
0x18009d51a  lea     rcx, [rsp+1A0h+var_128]
0x18009d51f  call    ?Close@?$AutoGenericHandleBase@PEA_W$0A@VAutoScz@@@Windows@@QEAAXXZ; Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(void)
0x18009d524  lea     rcx, [rbp+0A0h+var_120]
0x18009d528  call    ?Close@?$AutoGenericHandleBase@PEA_W$0A@VAutoScz@@@Windows@@QEAAXXZ; Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(void)
0x18009d52d  lea     rcx, [rbp+0A0h+var_118]
0x18009d531  call    ?Close@?$AutoGenericHandleBase@PEA_W$0A@VAutoScz@@@Windows@@QEAAXXZ; Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(void)
0x18009d536  lea     rcx, [rsp+1A0h+var_138]
0x18009d53b  call    ?Close@?$AutoGenericHandleBase@PEA_W$0A@VAutoScz@@@Windows@@QEAAXXZ; Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(void)
0x18009d540  lea     rcx, [rbp+0A0h+var_100]
0x18009d544  call    ?Close@?$AutoGenericHandleBase@PEA_W$0A@VAutoScz@@@Windows@@QEAAXXZ; Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(void)
0x18009d549  lea     rcx, [rbp+0A0h+var_F8]
0x18009d54d  call    ?Close@?$AutoGenericHandleBase@PEA_W$0A@VAutoScz@@@Windows@@QEAAXXZ; Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(void)
0x18009d552  lea     rcx, [rbp+0A0h+var_110]
0x18009d556  call    ?Close@?$AutoGenericHandleBase@PEA_W$0A@VAutoScz@@@Windows@@QEAAXXZ; Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(void)
0x18009d55b  lea     rcx, [rsp+1A0h+var_140]
0x18009d560  call    ?Close@?$AutoGenericHandleBase@PEA_W$0A@VAutoScz@@@Windows@@QEAAXXZ; Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(void)
0x18009d565  lea     rcx, [rbp+0A0h+var_108]
0x18009d569  call    ?Close@?$AutoGenericHandleBase@PEA_W$0A@VAutoScz@@@Windows@@QEAAXXZ; Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(void)
0x18009d56e  mov     rcx, [rbp+0A0h+var_E8]; this
0x18009d572  test    rcx, rcx
0x18009d575  jz      short loc_18009D57C
0x18009d577  call    ??_GParsingSession@@QEAAPEAXI@Z; ParsingSession::`scalar deleting destructor'(uint)
0x18009d57c  mov     rax, [rbp+0A0h+arg_60]
0x18009d583  test    rax, rax
0x18009d586  jz      loc_18009F6DC
0x18009d58c  mov     ecx, [rbp+0A0h+var_6C]
0x18009d58f  mov     [rax], ecx
0x18009d591  jmp     loc_18009F6DC
0x18009d596  mov     rdx, r14
0x18009d599  lea     rcx, aUpdate_2; "update"
0x18009d5a0  call    cs:__imp__o__wcsicmp
0x18009d5a7  nop     dword ptr [rax+rax+00h]
0x18009d5ac  lea     r8, [rbp+0A0h+var_118]; wchar_t **
0x18009d5b0  mov     rcx, rbx; this
0x18009d5b3  lea     rdx, aPackages; "Packages"
0x18009d5ba  mov     [rbp+0A0h+var_70], eax
0x18009d5bd  call    ?GetServicingDirectory@CCbsSession@@QEAAJPEB_WPEAPEA_W@Z; CCbsSession::GetServicingDirectory(wchar_t const *,wchar_t * *)
0x18009d5c2  mov     ebx, eax
0x18009d5c4  test    eax, eax
0x18009d5c6  jns     loc_18009D6D7
0x18009d5cc  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x18009d5d3  mov     [rbp+0A0h+var_70], eax
0x18009d5d6  test    rcx, rcx
0x18009d5d9  jz      short loc_18009D61B
0x18009d5db  mov     r14d, 3
0x18009d5e1  lea     r9, aFailedToGetTar_0; "Failed to get target servicing director"...
0x18009d5e8  mov     r8d, r14d
0x18009d5eb  xor     edx, edx
0x18009d5ed  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x18009d5f2  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x18009d5f9  lea     rax, [rbp+0A0h+var_70]
0x18009d5fd  mov     [rbp+0A0h+lpWideCharStr], rax
0x18009d601  lea     r9, asc_1802EE7AC; ": {}"
0x18009d608  lea     rax, [rbp+0A0h+lpWideCharStr]
0x18009d60c  mov     r8d, r14d
0x18009d60f  mov     dl, 1
0x18009d611  mov     [rsp+1A0h+var_180], rax; int
0x18009d616  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x18009d61b  mov     rcx, [rbp+0A8h]; this
0x18009d622  lea     r8, aOnecoreBaseCbs_138; "onecore\\base\\cbs\\core\\cbspackageper"...
0x18009d629  mov     r9d, ebx; char *
0x18009d62c  mov     edx, 186h; void *
0x18009d631  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18009d636  lea     rcx, [rbp+0A0h+var_D0]; this
0x18009d63a  call    ?Unimpersonate@ImpersonatorBase@@QEAAXXZ; ImpersonatorBase::Unimpersonate(void)
0x18009d63f  lea     rcx, [rbp+0A0h+var_60]
0x18009d643  call    ?Close@?$AutoGenericHandleBase@PEAX$00V?$AutoGenericHandle@PEAX$00$1?CloseWithNtCloseHandle@Detail@Windows@@YAXPEAX@Z@Windows@@@Windows@@QEAAXXZ; Windows::AutoGenericHandleBase<void *,1,Windows::AutoGenericHandle<void *,1,&Windows::Detail::CloseWithNtCloseHandle(void *)>>::Close(void)
0x18009d648  lea     rcx, [rsp+1A0h+ExistingTokenHandle]
0x18009d64d  call    ?Close@?$AutoGenericHandleBase@PEAX$00V?$AutoGenericHandle@PEAX$00$1?CloseWithNtCloseHandle@Detail@Windows@@YAXPEAX@Z@Windows@@@Windows@@QEAAXXZ; Windows::AutoGenericHandleBase<void *,1,Windows::AutoGenericHandle<void *,1,&Windows::Detail::CloseWithNtCloseHandle(void *)>>::Close(void)
0x18009d652  lea     rcx, [rbp+0A0h+var_68]
0x18009d656  call    ?Close@?$AutoGenericHandleBase@PEA_W$0A@VAutoScz@@@Windows@@QEAAXXZ; Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(void)
0x18009d65b  lea     rcx, [rsp+1A0h+var_128]
0x18009d660  call    ?Close@?$AutoGenericHandleBase@PEA_W$0A@VAutoScz@@@Windows@@QEAAXXZ; Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(void)
0x18009d665  lea     rcx, [rbp+0A0h+var_120]
0x18009d669  call    ?Close@?$AutoGenericHandleBase@PEA_W$0A@VAutoScz@@@Windows@@QEAAXXZ; Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(void)
0x18009d66e  lea     rcx, [rbp+0A0h+var_118]
0x18009d672  call    ?Close@?$AutoGenericHandleBase@PEA_W$0A@VAutoScz@@@Windows@@QEAAXXZ; Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(void)
0x18009d677  lea     rcx, [rsp+1A0h+var_138]
0x18009d67c  call    ?Close@?$AutoGenericHandleBase@PEA_W$0A@VAutoScz@@@Windows@@QEAAXXZ; Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(void)
0x18009d681  lea     rcx, [rbp+0A0h+var_100]
0x18009d685  call    ?Close@?$AutoGenericHandleBase@PEA_W$0A@VAutoScz@@@Windows@@QEAAXXZ; Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(void)
0x18009d68a  lea     rcx, [rbp+0A0h+var_F8]
0x18009d68e  call    ?Close@?$AutoGenericHandleBase@PEA_W$0A@VAutoScz@@@Windows@@QEAAXXZ; Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(void)
0x18009d693  lea     rcx, [rbp+0A0h+var_110]
0x18009d697  call    ?Close@?$AutoGenericHandleBase@PEA_W$0A@VAutoScz@@@Windows@@QEAAXXZ; Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(void)
0x18009d69c  lea     rcx, [rsp+1A0h+var_140]
0x18009d6a1  call    ?Close@?$AutoGenericHandleBase@PEA_W$0A@VAutoScz@@@Windows@@QEAAXXZ; Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(void)
  ... truncated ...
```
