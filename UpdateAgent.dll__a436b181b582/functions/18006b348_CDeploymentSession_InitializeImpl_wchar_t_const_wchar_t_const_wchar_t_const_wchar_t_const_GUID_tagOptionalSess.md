# CDeploymentSession::InitializeImpl(wchar_t const *,wchar_t const *,wchar_t const *,wchar_t const *,_GUID,tagOptionalSessionInfo6 const &)

- ea: `0x18006b348`
- end: `0x18006cf02`
- name: `?InitializeImpl@CDeploymentSession@@AEAAJPEB_W000U_GUID@@AEBUtagOptionalSessionInfo6@@@Z`
- size: `7098`
- prototype: `__int64 __usercall@<rax>(CDeploymentSession *__hidden this@<rcx>, const wchar_t *@<rdx>, const wchar_t *@<r8>, const wchar_t *@<r9>, const wchar_t *, struct _GUID *__struct_ptr, const struct tagOptionalSessionInfo6 *)`
- caller_count: `1`
- callee_count: `53`
- tags: `file_ops, registry_config, loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x180069894`

## callees

- `0x1800059d0`
- `0x1800059f4`
- `0x180005cf0`
- `0x180006a18`
- `0x180008fbc`
- `0x18000afc8`
- `0x18000b508`
- `0x18000c760`
- `0x18000c994`
- `0x18000d0b0`
- `0x18001273c`
- `0x180012770`
- `0x180021578`
- `0x180022e2c`
- `0x180023010`
- `0x180023b20`
- `0x180024c4c`
- `0x180025724`
- `0x180026af8`
- `0x1800281d4`
- `0x1800315e8`
- `0x180032b8c`
- `0x180039f90`
- `0x180039fb0`
- `0x18003c418`
- `0x1800408d0`
- `0x180041688`
- `0x180042b08`
- `0x180045dc0`
- `0x18004ab74`
- `0x18005d484`
- `0x18005f7f8`
- `0x1800621cc`
- `0x180068c88`
- `0x18006968c`
- `0x180069704`
- `0x18006b348`
- `0x18006f89c`
- `0x180073dac`
- `0x180077664`
- `0x180078b4c`
- `0x180078b9c`
- `0x18007c558`
- `0x18008a46c`
- `0x18008c3e0`
- `0x18008cba0`
- `0x180090650`
- `0x180092f88`
- `0x180094d0c`
- `0x18009d43c`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18006c48e`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18006c48e`
- `RPCRT4!UuidCreate` at `0x18006c72a`
- `RPCRT4!UuidCreate` at `0x18006c72a`
- `RPCRT4!I_RpcMapWin32Status` at `0x18006ce9d`
- `RPCRT4!I_RpcMapWin32Status` at `0x18006ce9d`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x18006b751`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x18006b751`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x18006c2e0`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x18006c2e0`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x18006b71d`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x18006c28d`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x18006b71d`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x18006c28d`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18006b816`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18006b816`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18006b82b`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18006b82b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006b761`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006c2f0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006b761`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006c2f0`

## string_xrefs

- `0x18006c01f`: `ActionList.xml`
- `0x18006ceef`: `onecore\base\ntsetup\conx\mosetup\updateagent\src\DeploymentSessionImpl.h`
- `0x18006bb49`: `CDeploymentSession: Initializing SandboxPath = [{}]`
- `0x18006bb5d`: `CDeploymentSession: Initializing OfflineWinDirPath = [{}]`
- `0x18006bb71`: `CDeploymentSession: Initializing DeviceInfoPath = [{}]`
- `0x18006bb81`: `CDeploymentSession: Initializing MergedSandboxPath = [{}]`
- `0x18006bc0e`: `CDeploymentSession: Initializing UpdateId = [{}]`
- `0x18006c05f`: `DownloadList.xml`

## pseudocode

```c
// Hidden C++ exception states: #wind=25
__int64 __fastcall CDeploymentSession::InitializeImpl(
        CDeploymentSession *this,
        wchar_t *a2,
        wchar_t *a3,
        wchar_t *a4,
        wchar_t *a5,
        struct _GUID *a6,
        const struct tagOptionalSessionInfo6 *a7)
{
  const struct tagOptionalSessionInfo6 *v9; // r15
  char *v10; // rbx
  __int64 v11; // rcx
  int updated; // eax
  __int64 v13; // rdx
  signed int v14; // edi
  struct IDlpManager *v15; // r15
  const char *v16; // r9
  __int64 result; // rax
  int StringCch; // eax
  __int64 v19; // rdx
  __int64 v20; // rax
  __int64 v21; // rcx
  int v22; // eax
  __int64 v23; // rdx
  char *v24; // r14
  int DefaultLogFolderPath; // eax
  __int64 v26; // rcx
  __int64 v27; // rcx
  __int64 v28; // rdx
  const WCHAR *v29; // r15
  DWORD FileAttributesW; // edi
  int v31; // edi
  signed int LastError; // eax
  int v33; // eax
  __int64 v34; // rbx
  HANDLE ProcessHeap; // rax
  __int64 v36; // rcx
  CCBSSessionManager *v37; // rdi
  void *v38; // r14
  __int64 v39; // rcx
  int v40; // eax
  int v41; // eax
  __int64 v42; // rdx
  struct CWatsonHelper *Instance; // rdi
  __int64 v44; // rcx
  _BYTE *v45; // rax
  int v46; // edx
  int v47; // eax
  __int64 v48; // rcx
  _BYTE *v49; // rax
  int v50; // r14d
  int v51; // eax
  int v52; // eax
  int v53; // eax
  __int64 v54; // rdx
  const struct tagOptionalSessionInfo6 *v55; // rdi
  __int64 v56; // rdx
  __int64 v57; // r8
  int v58; // r9d
  __int64 v59; // rcx
  void *v60; // r14
  int Internal; // eax
  __int64 v62; // rdx
  wchar_t *v63; // r14
  int v64; // eax
  __int64 v65; // rdx
  void *v66; // r14
  int v67; // eax
  __int64 v68; // rdx
  void *v69; // r14
  int v70; // eax
  __int64 v71; // rdx
  int v72; // eax
  __int64 v73; // rdx
  wchar_t *v74; // r12
  __int64 v75; // rcx
  int v76; // eax
  __int64 v77; // rdx
  _QWORD *v78; // r15
  int v79; // eax
  __int64 v80; // rdx
  LPCWSTR *v81; // r14
  int v82; // eax
  int v83; // eax
  int v84; // eax
  int v85; // eax
  __int64 v86; // rdx
  int v87; // edi
  _QWORD *v88; // rax
  _QWORD *v89; // rcx
  int v90; // r8d
  int DlpManagerCore; // eax
  int v92; // r8d
  __int64 v93; // rcx
  int v94; // eax
  __int64 v95; // rcx
  __int64 v96; // rcx
  int v97; // eax
  __int64 v98; // rcx
  DWORD v99; // eax
  BOOL v100; // edi
  __int64 v101; // rcx
  signed int v102; // eax
  __int64 v103; // rax
  struct IDlpManager *v104; // rdi
  __int64 v105; // rcx
  __int64 v106; // rcx
  int v107; // eax
  __int64 v108; // rcx
  struct IDlpManager *v109; // rdi
  __int64 v110; // rcx
  __int64 v111; // rcx
  int v112; // eax
  int v113; // r14d
  const struct tagOptionalSessionInfo6 *v114; // rdi
  const WCHAR **v115; // r15
  bool v116; // zf
  __int64 v117; // rcx
  const WCHAR *v118; // rax
  void *v119; // r12
  int v120; // eax
  __int64 v121; // rdx
  const WCHAR *v122; // rdi
  char IsEnabled; // al
  __int64 v124; // rdx
  _QWORD *v125; // rax
  void (__fastcall ***v126)(_QWORD); // r15
  int v127; // eax
  __int64 v128; // rdx
  __int64 v129; // rcx
  int v130; // eax
  __int64 v131; // rcx
  int v132; // eax
  __int64 v133; // rdx
  struct IDlpManager *v134; // rdi
  __int64 v135; // rcx
  RPC_STATUS v136; // eax
  int v137; // eax
  int v138; // eax
  int v139; // eax
  __int64 v140; // rcx
  __int64 v141; // rcx
  const WCHAR *v142; // r9
  __int64 v143; // rcx
  const WCHAR *v144; // r9
  __int64 v145; // rcx
  __int64 v146; // rcx
  __int64 i; // rdi
  __int64 v148; // rcx
  int IsHostOSMobile; // eax
  __int64 v150; // r9
  __int64 v151; // rdx
  int v152; // eax
  void (__fastcall ***v153)(_QWORD); // rcx
  const struct tagOptionalSessionInfo6 *v154; // rax
  int OneSettings; // eax
  __int64 v156; // rcx
  __int64 v157; // rax
  __int64 v158; // rdx
  int v159; // eax
  __int64 *v160; // [rsp+20h] [rbp-1D8h]
  const wchar_t **v161; // [rsp+28h] [rbp-1D0h]
  _QWORD v162[2]; // [rsp+30h] [rbp-1C8h] BYREF
  _QWORD v163[2]; // [rsp+40h] [rbp-1B8h] BYREF
  int v164; // [rsp+50h] [rbp-1A8h] BYREF
  struct IDlpManager *v165; // [rsp+58h] [rbp-1A0h] BYREF
  const wchar_t *v166; // [rsp+60h] [rbp-198h] BYREF
  const struct tagOptionalSessionInfo6 *v167; // [rsp+68h] [rbp-190h]
  void (__fastcall ***v168)(_QWORD); // [rsp+70h] [rbp-188h]
  int v169[2]; // [rsp+78h] [rbp-180h] BYREF
  LPCWSTR lpFileName; // [rsp+80h] [rbp-178h] BYREF
  _DWORD *v171; // [rsp+88h] [rbp-170h] BYREF
  void (__fastcall ***v172)(_QWORD); // [rsp+90h] [rbp-168h]
  CCBSSessionManager *v173; // [rsp+98h] [rbp-160h] BYREF
  char *v174; // [rsp+A0h] [rbp-158h]
  struct _GUID *v175; // [rsp+A8h] [rbp-150h]
  _QWORD v176[2]; // [rsp+B0h] [rbp-148h] BYREF
  const wchar_t **v177; // [rsp+C0h] [rbp-138h]
  const wchar_t **v178; // [rsp+C8h] [rbp-130h]
  const wchar_t **v179; // [rsp+D0h] [rbp-128h]
  const wchar_t **v180; // [rsp+D8h] [rbp-120h]
  __int64 v181; // [rsp+E0h] [rbp-118h]
  __int64 v182; // [rsp+E8h] [rbp-110h]
  _BYTE v183[32]; // [rsp+F0h] [rbp-108h] BYREF
  wchar_t *v184; // [rsp+110h] [rbp-E8h] BYREF
  void *Src; // [rsp+118h] [rbp-E0h] BYREF
  void *v186; // [rsp+120h] [rbp-D8h] BYREF
  int v187; // [rsp+130h] [rbp-C8h] BYREF
  __int64 v188; // [rsp+138h] [rbp-C0h]
  __int64 v189; // [rsp+140h] [rbp-B8h]
  __int64 v190; // [rsp+148h] [rbp-B0h]
  __int64 v191; // [rsp+150h] [rbp-A8h]
  __int64 v192; // [rsp+158h] [rbp-A0h]
  __int64 v193; // [rsp+160h] [rbp-98h]
  __int64 v194; // [rsp+168h] [rbp-90h]
  __int64 v195; // [rsp+170h] [rbp-88h]
  __int64 v196; // [rsp+178h] [rbp-80h]
  unsigned int v197; // [rsp+180h] [rbp-78h] BYREF
  __int64 v198; // [rsp+188h] [rbp-70h] BYREF
  __int64 v199; // [rsp+190h] [rbp-68h] BYREF
  __int64 v200; // [rsp+198h] [rbp-60h] BYREF
  UUID Uuid; // [rsp+1A0h] [rbp-58h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+1F8h] [rbp+0h]

  v181 = -2;
  Src = a2;
  v184 = a3;
  v186 = a4;
  v175 = a6;
  v9 = a7;
  v167 = a7;
  v10 = 0;
  v174 = 0;
  v163[0] = 0;
  v165 = 0;
  v182 = 0;
  v173 = 0;
  v164 = 0;
  v197 = 0;
  v200 = 0;
  Uuid = 0;
  lpFileName = 0;
  v199 = 0;
  v198 = 0;
  v168 = 0;
  v172 = 0;
  memset_0(&v187, 0, 0x50u);
  try
  {
    if ( !a2 )
    {
      v11 = *((_QWORD *)this + 75);
      if ( v11 )
      {
        updated = CMoUpdateLogT<CEmptyType>::MoUpdateLogFormat(
                    v11,
                    4,
                    L"%s(%d): Result = 0x%X",
                    L"CDeploymentSession::InitializeImpl",
                    251,
                    -2147024809);
        v11 = (unsigned int)updated;
        if ( updated < 0 )
          CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure((unsigned int)updated, v13);
      }
      v14 = -2147024809;
      goto LABEL_7;
    }
    LODWORD(v162[0]) = 0;
    StringCch = CGlobalHelpersT<CEmptyType>::GetStringCchLength<unsigned long>(L"0xca00a004;0x800700ce", v162);
    v14 = StringCch;
    if ( StringCch < 0
      || (StringCch = CImmutableStringsT<wchar_t,CImmutableStringsPolicyDefault>::CreateInternal(L"0xca00a004;0x800700ce"),
          v14 = StringCch,
          StringCch < 0) )
    {
      CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure((unsigned int)StringCch, v19);
    }
    CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent((unsigned int)v14);
    v20 = *((_QWORD *)this + 75);
    if ( v14 < 0 )
    {
      if ( !v20 )
      {
LABEL_21:
        v11 = 0;
LABEL_7:
        CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(v11);
LABEL_8:
        v15 = (struct IDlpManager *)v163[0];
LABEL_9:
        CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent((unsigned int)v14);
        if ( v168 )
          (**v168)(v168);
        SP_MEM<wchar_t>::~SP_MEM<wchar_t>(&v198);
        SP_MEM<wchar_t>::~SP_MEM<wchar_t>(&v199);
        DH_SSTRING::~DH_SSTRING((DH_SSTRING *)&lpFileName);
        DH_SSTRING::~DH_SSTRING((DH_SSTRING *)&v200);
        SP_CPP<CCBSSessionManager>::~SP_CPP<CCBSSessionManager>(&v173);
        if ( v15 )
          (*(void (__fastcall **)(struct IDlpManager *))(*(_QWORD *)v15 + 16LL))(v15);
        if ( v10 )
          (*(void (__fastcall **)(char *))(*(_QWORD *)v10 + 16LL))(v10);
        return (unsigned int)v14;
      }
      LODWORD(v161) = v14;
      LODWORD(v160) = 253;
      goto LABEL_23;
    }
    if ( !v20 )
    {
      v24 = (char *)operator new(0xF0u);
      memset_0(v24 + 8, 0, 0xE8u);
      *(_QWORD *)v24 = &winrt::impl::producers_base<CUpdateDiagnostics,std::tuple<IUpdateDiagnostics>>::`vftable';
      _InterlockedIncrement(&`winrt::get_module_lock'::`2'::s_lock);
      *((_QWORD *)v24 + 2) = 1;
      *(_QWORD *)v24 = &CUpdateDiagnostics::`vftable'{for `winrt::impl::producers_base<CUpdateDiagnostics,std::tuple<IUpdateDiagnostics>>'};
      *((_QWORD *)v24 + 1) = &CUpdateDiagnostics::`vftable'{for `winrt::impl::root_implements<CUpdateDiagnostics,IUpdateDiagnostics>'};
      *((_QWORD *)v24 + 3) = &CUpdateDiagnostics::`vftable'{for `IArbiterDiagnostics'};
      *((_QWORD *)v24 + 4) = &CUpdateDiagnostics::`vftable'{for `IMitiDiagnostics'};
      v15 = 0;
      *((_QWORD *)v24 + 5) = 0;
      *((_QWORD *)v24 + 6) = 0;
      *(_OWORD *)(v24 + 56) = 0;
      *((_QWORD *)v24 + 9) = 0;
      *((_QWORD *)v24 + 10) = 15;
      v24[56] = 0;
      *((_QWORD *)v24 + 11) = 0;
      *((_QWORD *)v24 + 12) = 0;
      *((_QWORD *)v24 + 13) = 0;
      *((_QWORD *)v24 + 14) = 0;
      *((_QWORD *)v24 + 15) = 0;
      *((_QWORD *)v24 + 16) = 0;
      *((_QWORD *)v24 + 17) = 0;
      *((_QWORD *)v24 + 18) = 0;
      *((_QWORD *)v24 + 19) = 0;
      *((_WORD *)v24 + 80) = 0;
      *((_DWORD *)v24 + 41) = 0;
      *(_OWORD *)(v24 + 168) = 0;
      *((_QWORD *)v24 + 23) = 0;
      v10 = v24;
      v174 = v24;
      DefaultLogFolderPath = CMoUpdateLogT<CEmptyType>::GetDefaultLogFolderPath(&lpFileName);
      v14 = DefaultLogFolderPath;
      if ( DefaultLogFolderPath < 0 )
      {
        v26 = *((_QWORD *)this + 75);
        if ( !v26 )
        {
LABEL_29:
          v27 = 0;
LABEL_33:
          CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(v27);
          goto LABEL_9;
        }
        v27 = (unsigned int)CMoUpdateLogT<CEmptyType>::MoUpdateLogFormat(
                              v26,
                              4,
                              L"%s(%d): Result = 0x%X",
                              L"CDeploymentSession::InitializeImpl",
                              261,
                              DefaultLogFolderPath);
LABEL_31:
        if ( (int)v27 < 0 )
          CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(v27, v28);
        goto LABEL_33;
      }
      v29 = lpFileName;
      FileAttributesW = GetFileAttributesW(lpFileName);
      if ( FileAttributesW == -1 )
        v31 = 0;
      else
        v31 = (FileAttributesW >> 4) & 1;
      CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(0);
      CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(0);
      if ( !v31 && !CreateDirectoryW(v29, 0) )
      {
        LastError = GetLastError();
        v14 = LastError;
        if ( LastError )
        {
          if ( LastError > 0 )
            v14 = (unsigned __int16)LastError | 0x80070000;
        }
        else
        {
          v14 = -2147467259;
        }
        v20 = *((_QWORD *)this + 75);
        v11 = 0;
        if ( v14 >= 0 || !v20 )
          goto LABEL_7;
        LODWORD(v161) = v14;
        LODWORD(v160) = 265;
LABEL_23:
        v21 = v20;
        goto LABEL_24;
      }
      v160 = (__int64 *)*((_QWORD *)v167 + 5);
      v33 = (*(__int64 (__fastcall **)(char *, __int64, const WCHAR *, _QWORD))(*(_QWORD *)v24 + 56LL))(
              v24,
              1,
              v29,
              *((_QWORD *)v167 + 4));
      v14 = v33;
      if ( v33 < 0 )
      {
        v21 = *((_QWORD *)this + 75);
        if ( !v21 )
          goto LABEL_21;
        LODWORD(v161) = v33;
        LODWORD(v160) = 268;
LABEL_24:
        v22 = CMoUpdateLogT<CEmptyType>::MoUpdateLogFormat(
                v21,
                4,
                L"%s(%d): Result = 0x%X",
                L"CDeploymentSession::InitializeImpl",
                v160,
                v161);
        v11 = (unsigned int)v22;
        if ( v22 < 0 )
          CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure((unsigned int)v22, v23);
        goto LABEL_7;
      }
      lpFileName = 0;
      v34 = *((_QWORD *)this + 65);
      if ( v34 )
      {
        ProcessHeap = GetProcessHeap();
        HeapFree(ProcessHeap, 0, (LPVOID)(v34 - 4));
        CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(0);
      }
      *((_QWORD *)this + 65) = v29;
      v10 = 0;
      v174 = 0;
      v36 = *((_QWORD *)this + 75);
      if ( v36 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v36 + 16LL))(v36);
      *((_QWORD *)this + 75) = v24;
      v9 = v167;
    }
    v37 = (CCBSSessionManager *)operator new(0x18u);
    *(_QWORD *)v37 = 0;
    *((_QWORD *)v37 + 1) = 0;
    *((_QWORD *)v37 + 2) = 0;
    v173 = v37;
    CCBSSessionManager::Initialize(v37, *((struct IUpdateDiagnostics **)this + 75), v184, a5);
    v173 = 0;
    v38 = (void *)*((_QWORD *)this + 83);
    if ( v38 )
    {
      CCBSSessionManager::~CCBSSessionManager(*((CCBSSessionManager **)this + 83));
      operator delete(v38, (const struct std::nothrow_t *)0x18);
    }
    *((_QWORD *)this + 83) = v37;
    v39 = *((_QWORD *)this + 75);
    v177 = (const wchar_t **)((char *)v9 + 16);
    v40 = (*(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v39 + 120LL))(v39, *((_QWORD *)v9 + 2));
    v14 = v40;
    v21 = *((_QWORD *)this + 75);
    if ( v40 < 0 )
    {
      if ( !v21 )
        goto LABEL_21;
      LODWORD(v161) = v40;
      LODWORD(v160) = 277;
      goto LABEL_24;
    }
    v178 = (const wchar_t **)((char *)v9 + 8);
    v41 = (*(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v21 + 128LL))(v21, *((_QWORD *)v9 + 1));
    v14 = v41;
    v21 = *((_QWORD *)this + 75);
    if ( v41 < 0 )
    {
      if ( !v21 )
        goto LABEL_21;
      LODWORD(v161) = v41;
      LODWORD(v160) = 278;
      goto LABEL_24;
    }
    (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v21 + 160LL))(v21, 1);
    Instance = CWatsonHelper::GetInstance();
    v166 = L"ON";
    LODWORD(v162[0]) = 1;
    if ( *(_QWORD *)&LogAdapter::g_Logger )
    {
      v161 = &v166;
      v160 = v162;
      LOBYTE(v42) = 1;
      LogAdapter::Logger::LogNumObjects<unsigned long,wchar_t const *>(
        *(_QWORD *)&LogAdapter::g_Logger,
        v42,
        1,
        "WatsonHelper: Bucket parameter [{}] mute: [{}]");
    }
    *(_BYTE *)(*((_QWORD *)Instance + 8) + 1LL) = 1;
    CDeploymentSession::InitializeWatsonIgnoredErrors(this);
    if ( *((_QWORD *)v9 + 4) )
    {
      v44 = 0x7FFFFFFF;
      v45 = (_BYTE *)*((_QWORD *)v9 + 4);
      while ( *v45 )
      {
        ++v45;
        if ( !--v44 )
        {
          v14 = -2147024809;
          v46 = 0;
          goto LABEL_70;
        }
      }
      v14 = 0;
      v46 = 0x7FFFFFFF - v44;
LABEL_70:
      if ( v14 < 0 )
      {
        v21 = *((_QWORD *)this + 75);
        if ( !v21 )
          goto LABEL_21;
        LODWORD(v161) = v14;
        LODWORD(v160) = 288;
        goto LABEL_24;
      }
      v47 = CStringConvertT<unsigned long>::A2W(*((LPCCH *)v9 + 4), v46);
      v14 = v47;
      if ( v47 < 0 )
      {
        v21 = *((_QWORD *)this + 75);
        if ( !v21 )
          goto LABEL_21;
        LODWORD(v161) = v47;
        LODWORD(v160) = 289;
        goto LABEL_24;
      }
    }
    if ( *((_QWORD *)v9 + 5) )
    {
      v48 = 0x7FFFFFFF;
      v49 = (_BYTE *)*((_QWORD *)v9 + 5);
      while ( *v49 )
      {
        ++v49;
        if ( !--v48 )
        {
          v14 = -2147024809;
          v50 = 0;
          goto LABEL_82;
        }
      }
      v14 = 0;
      v50 = 0x7FFFFFFF - v48;
LABEL_82:
      if ( v14 < 0 )
      {
        v21 = *((_QWORD *)this + 75);
        if ( !v21 )
          goto LABEL_21;
        LODWORD(v161) = v14;
        LODWORD(v160) = 294;
        goto LABEL_24;
      }
      v51 = CStringConvertT<unsigned long>::A2W(*((LPCCH *)v9 + 5), v50);
      v14 = v51;
      if ( v51 < 0 )
      {
        v21 = *((_QWORD *)this + 75);
        if ( !v21 )
          goto LABEL_21;
        LODWORD(v161) = v51;
        LODWORD(v160) = 295;
        goto LABEL_24;
      }
    }
    v52 = CDeploymentSession::CheckUpdateBlocks(this);
    v14 = v52;
    if ( v52 < 0 )
    {
      v21 = *((_QWORD *)this + 75);
      if ( !v21 )
        goto LABEL_21;
      LODWORD(v161) = v52;
      LODWORD(v160) = 300;
      goto LABEL_24;
    }
    LogAdapter::TraceInfo<wchar_t const *>("CDeploymentSession: Initializing SandboxPath = [{}]", &Src);
    LogAdapter::TraceInfo<wchar_t const *>("CDeploymentSession: Initializing OfflineWinDirPath = [{}]", &v184);
    LogAdapter::TraceInfo<wchar_t const *>("CDeploymentSession: Initializing DeviceInfoPath = [{}]", &v186);
    LogAdapter::TraceInfo<wchar_t const *>("CDeploymentSession: Initializing MergedSandboxPath = [{}]", (char *)v9 + 48);
    v53 = CDlpHelpersT<CEmptyType>::GuidToSString(v175, 0, &v200);
    v14 = v53;
    if ( v53 < 0 )
    {
      v21 = *((_QWORD *)this + 75);
      if ( !v21 )
        goto LABEL_21;
      LODWORD(v161) = v53;
      LODWORD(v160) = 308;
      goto LABEL_24;
    }
    if ( *(_QWORD *)&LogAdapter::g_Logger )
    {
      LOBYTE(v54) = 1;
      LogAdapter::Logger::LogNumObjects<Windows::AutoGenericHandle<wchar_t *,0,&void Windows::Detail::CloseWithCoTaskMemFree<wchar_t>(wchar_t *)>>(
        *(_QWORD *)&LogAdapter::g_Logger,
        v54,
        1,
        "CDeploymentSession: Initializing Callback Factory Guid = [{}]",
        &v200);
    }
    v55 = v167;
    LogAdapter::TraceInfo<wchar_t const *>("CDeploymentSession: Initializing SessionData = [{}]", v167);
    LogAdapter::TraceInfo<wchar_t const *>("CDeploymentSession: Initializing UpdateId = [{}]", (char *)v55 + 8);
    LogAdapter::TraceInfo<wchar_t const *>("CDeploymentSession: Initializing FlightId = [{}]", (char *)v55 + 16);
    v179 = (const wchar_t **)((char *)v55 + 24);
    LogAdapter::TraceInfo<wchar_t const *>("CDeploymentSession: Initializing FlightMetadata = [{}]", (char *)v55 + 24);
    v180 = (const wchar_t **)((char *)v55 + 56);
    LogAdapter::TraceInfo<wchar_t const *>("CDeploymentSession: Initializing Country Code = [{}]", (char *)v55 + 56);
    v176[0] = (char *)v55 + 64;
    LogAdapter::TraceInfo<unsigned long>("CDeploymentSession: Initializing optional flags = [{}]", (char *)v55 + 64);
    v59 = *(_QWORD *)&LogAdapter::g_Logger;
    if ( *(_QWORD *)&LogAdapter::g_Logger )
    {
      v160 = &v199;
      LogAdapter::Logger::LogNumObjects<SP_MEM<wchar_t>>(
        *(_QWORD *)&LogAdapter::g_Logger,
        v56,
        v57,
        "CDeploymentSession: Initializing CorrelationVector = [{}]");
      v59 = *(_QWORD *)&LogAdapter::g_Logger;
      if ( *(_QWORD *)&LogAdapter::g_Logger )
      {
        v160 = &v198;
        LogAdapter::Logger::LogNumObjects<SP_MEM<wchar_t>>(
          *(_QWORD *)&LogAdapter::g_Logger,
          v56,
          v57,
          "CDeploymentSession: Initializing RelatedCV = [{}]");
        v59 = *(_QWORD *)&LogAdapter::g_Logger;
      }
    }
    v166 = (const wchar_t *)((char *)v55 + 64);
    if ( v59 )
    {
      LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHex8Wrapper<unsigned long>>(
        v59,
        v56,
        v57,
        v58,
        (__int64)&v166);
      v59 = *(_QWORD *)&LogAdapter::g_Logger;
    }
    v171 = (_DWORD *)((char *)v55 + 104);
    *(_QWORD *)v169 = (char *)v55 + 104;
    if ( v59 )
      LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHex8Wrapper<enum tagSessionDownloadCapabilityFlags>>(
        v59,
        v56,
        v57,
        v58,
        (__int64)v169);
    v60 = Src;
    LODWORD(v162[0]) = 0;
    if ( Src
      && (Internal = CGlobalHelpersT<CEmptyType>::GetStringCchLength<unsigned long>(Src, v162),
          v14 = Internal,
          Internal < 0)
      || (Internal = CImmutableStringsT<wchar_t,CImmutableStringsPolicyDefault>::CreateInternal(v60),
          v14 = Internal,
          Internal < 0) )
    {
      CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure((unsigned int)Internal, v62);
    }
    CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent((unsigned int)v14);
    if ( v14 < 0 )
    {
      v21 = *((_QWORD *)this + 75);
      if ( !v21 )
        goto LABEL_21;
      LODWORD(v161) = v14;
      LODWORD(v160) = 325;
      goto LABEL_24;
    }
    v63 = v184;
    LODWORD(v162[0]) = 0;
    if ( v184 && (v64 = CGlobalHelpersT<CEmptyType>::GetStringCchLength<unsigned long>(v184, v162), v14 = v64, v64 < 0)
      || (v64 = CImmutableStringsT<wchar_t,CImmutableStringsPolicyDefault>::CreateInternal(v63), v14 = v64, v64 < 0) )
    {
      CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure((unsigned int)v64, v65);
    }
    CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent((unsigned int)v14);
    if ( v14 < 0 )
    {
      v21 = *((_QWORD *)this + 75);
      if ( !v21 )
        goto LABEL_21;
      LODWORD(v161) = v14;
      LODWORD(v160) = 326;
      goto LABEL_24;
    }
    v66 = v186;
    LODWORD(v162[0]) = 0;
    if ( v186 && (v67 = CGlobalHelpersT<CEmptyType>::GetStringCchLength<unsigned long>(v186, v162), v14 = v67, v67 < 0)
      || (v67 = CImmutableStringsT<wchar_t,CImmutableStringsPolicyDefault>::CreateInternal(v66), v14 = v67, v67 < 0) )
    {
      CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure((unsigned int)v67, v68);
    }
    CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent((unsigned int)v14);
    if ( v14 < 0 )
    {
      v21 = *((_QWORD *)this + 75);
      if ( !v21 )
        goto LABEL_21;
      LODWORD(v161) = v14;
      LODWORD(v160) = 327;
      goto LABEL_24;
    }
    v69 = (void *)*((_QWORD *)v9 + 6);
    LODWORD(v162[0]) = 0;
    if ( v69 && (v70 = CGlobalHelpersT<CEmptyType>::GetStringCchLength<unsigned long>(v69, v162), v14 = v70, v70 < 0)
      || (v70 = CImmutableStringsT<wchar_t,CImmutableStringsPolicyDefault>::CreateInternal(v69), v14 = v70, v70 < 0) )
    {
      CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure((unsigned int)v70, v71);
    }
    CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent((unsigned int)v14);
    if ( v14 < 0 )
    {
      v21 = *((_QWORD *)this + 75);
      if ( !v21 )
        goto LABEL_21;
      LODWORD(v161) = v14;
      LODWORD(v160) = 328;
      goto LABEL_24;
    }
    if ( a5 )
    {
      LODWORD(v162[0]) = 0;
      v72 = CGlobalHelpersT<CEmptyType>::GetStringCchLength<unsigned long>(a5, v162);
      v14 = v72;
      if ( v72 < 0
        || (v72 = CImmutableStringsT<wchar_t,CImmutableStringsPolicyDefault>::CreateInternal(a5), v14 = v72, v72 < 0) )
      {
        CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure((unsigned int)v72, v73);
      }
      CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent((unsigned int)v14);
      if ( v14 < 0 )
      {
        v21 = *((_QWORD *)this + 75);
        if ( !v21 )
          goto LABEL_21;
        LODWORD(v161) = v14;
        LODWORD(v160) = 332;
        goto LABEL_24;
      }
    }
    v74 = (wchar_t *)Src;
    if ( *((_QWORD *)v9 + 6) )
      v74 = (wchar_t *)*((_QWORD *)v9 + 6);
    v166 = v74;
    *((_DWORD *)this + 146) = *((_QWORD *)v9 + 6) != 0;
    v75 = *((_QWORD *)this + 75);
    if ( v75 )
      CMoUpdateLogT<CEmptyType>::MoUpdateLogFormat(v75, 2, L"CDeploymentSession: Initializing WorkingDir = [%s]", v74);
    LODWORD(v162[0]) = 0;
    if ( v74 && (v76 = CGlobalHelpersT<CEmptyType>::GetStringCchLength<unsigned long>(v74, v162), v14 = v76, v76 < 0) )
    {
      CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure((unsigned int)v76, v77);
      v78 = (_QWORD *)((char *)this + 488);
    }
    else
    {
      v78 = (_QWORD *)((char *)this + 488);
      *(_QWORD *)v169 = (char *)this + 488;
      v79 = CImmutableStringsT<wchar_t,CImmutableStringsPolicyDefault>::CreateInternal(v74);
      v14 = v79;
      if ( v79 < 0 )
      {
        CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure((unsigned int)v79, v80);
LABEL_146:
        CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent((unsigned int)v14);
        if ( v14 < 0 )
        {
          v21 = *((_QWORD *)this + 75);
          if ( !v21 )
            goto LABEL_21;
          LODWORD(v161) = v14;
          LODWORD(v160) = 347;
          goto LABEL_24;
        }
        v81 = (LPCWSTR *)((char *)this + 504);
        v82 = CMiscHelpersT<CEmptyType>::CombinePath(*v78, L"ActionList.xml", 0, (char *)this + 504);
        v14 = v82;
        if ( v82 < 0 )
        {
          v21 = *((_QWORD *)this + 75);
          if ( !v21 )
            goto LABEL_21;
          LODWORD(v161) = v82;
          LODWORD(v160) = 348;
          goto LABEL_24;
        }
        v83 = CMiscHelpersT<CEmptyType>::CombinePath(*v78, L"DownloadList.xml", 0, (char *)this + 528);
        v14 = v83;
        if ( v83 < 0 )
        {
          v21 = *((_QWORD *)this + 75);
          if ( !v21 )
            goto LABEL_21;
          LODWORD(v161) = v83;
          LODWORD(v160) = 349;
          goto LABEL_24;
        }
        v84 = CMiscHelpersT<CEmptyType>::CombinePath(*v78, L"metadata", 0, (char *)this + 496);
        v14 = v84;
        if ( v84 < 0 )
        {
          v21 = *((_QWORD *)this + 75);
          if ( !v21 )
            goto LABEL_21;
          LODWORD(v161) = v84;
          LODWORD(v160) = 350;
          goto LABEL_24;
        }
        v85 = CExclusiveAcquireLock::Init((CDeploymentSession *)((char *)this + 152));
        v87 = v85;
        if ( v85 >= 0 )
          *((_DWORD *)this + 34) = 0;
        else
          CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure((unsigned int)v85, v86);
        CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent((unsigned int)v87);
        if ( v87 < 0 )
          wil::details::in1diag3::Throw_Hr(
            retaddr,
            (void *)0x2BE6,
            (unsigned int)"onecore\\base\\ntsetup\\conx\\mosetup\\updateagent\\src\\DeploymentSessionImpl.h",
            (const char *)(unsigned int)v87,
            (int)v160);
        v88 = (_QWORD *)std::to_wstring(v183, 0);
        if ( v88[3] <= 7u )
          v89 = v88;
        else
          v89 = (_QWORD *)*v88;
        v163[0] = v89;
        v163[1] = v88[2];
        CWatsonHelper::SetParameter(2, v163);
        std::wstring::~wstring(v183);
        DlpManagerCore = CreateDlpManagerCore(
                           (_DWORD)v74,
                           2,
                           v90,
                           *((_QWORD *)this + 75),
                           (__int64)v160,
                           (__int64)&v165);
        v93 = *((_QWORD *)this + 75);
        if ( DlpManagerCore < 0 )
        {
          if ( v93 )
            CMoUpdateLogT<CEmptyType>::MoUpdateLogFormat(v93, 2, L"Existing session state not found.");
          v15 = v165;
          goto LABEL_249;
        }
        if ( v93 )
          CMoUpdateLogT<CEmptyType>::MoUpdateLogFormat(v93, 2, L"Found existing session state. Checking its state.");
        v15 = v165;
        v94 = (**((__int64 (__fastcall ***)(char *, const wchar_t *, unsigned int *))v165 + 1))(
                (char *)v165 + 8,
                L"State",
                &v197);
        v95 = *((_QWORD *)this + 75);
        if ( v94 < 0 )
        {
          if ( v95 )
            CMoUpdateLogT<CEmptyType>::MoUpdateLogFormat(
              v95,
              2,
              L"Session state is corrupt. Error: [0x%X]",
              (unsigned int)v94);
          goto LABEL_249;
        }
        if ( v95 )
          CMoUpdateLogT<CEmptyType>::MoUpdateLogFormat(v95, 2, L"Found State = [%lu].", v197);
        if ( v197 - 3 > 5 && v197 - 12 > 1 )
        {
          v96 = *((_QWORD *)this + 75);
          if ( v96 )
            CMoUpdateLogT<CEmptyType>::MoUpdateLogFormat(v96, 2, L"Preserving critical state data...");
          v97 = CDeploymentSession::PreserveExpressFileCount(this, v15);
          v14 = v97;
          v98 = *((_QWORD *)this + 75);
          if ( v97 < 0 )
          {
            if ( !v98 )
              goto LABEL_29;
            LODWORD(v161) = v97;
            LODWORD(v160) = 381;
            goto LABEL_180;
          }
          if ( v98 )
            CMoUpdateLogT<CEmptyType>::MoUpdateLogFormat(
              v98,
              2,
              L"Resume is NOT supported from this state. Ignoring session state file.");
          *((_DWORD *)this + 66) = 1;
          v99 = GetFileAttributesW(*v81);
          v100 = v99 != -1 && (v99 & 0x10) == 0;
          CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(0);
          CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(0);
          if ( v100 )
          {
            v101 = *((_QWORD *)this + 75);
            if ( v101 )
              CMoUpdateLogT<CEmptyType>::MoUpdateLogFormat(v101, 2, L"Deleting previous ActionList file.");
            if ( !DeleteFileW(*v81) )
            {
              v102 = GetLastError();
              v14 = v102;
              if ( v102 )
              {
                if ( v102 > 0 )
                  v14 = (unsigned __int16)v102 | 0x80070000;
              }
              else
              {
                v14 = -2147467259;
              }
              v103 = *((_QWORD *)this + 75);
              v27 = 0;
              if ( v14 >= 0 || !v103 )
                goto LABEL_33;
              LODWORD(v161) = v14;
              LODWORD(v160) = 393;
              goto LABEL_197;
            }
          }
          if ( v15 )
          {
            v104 = v15;
            v105 = *((_QWORD *)this + 75);
            if ( v105 )
              CMoUpdateLogT<CEmptyType>::MoUpdateLogFormat(v105, 2, L"Resetting existing session state.");
            v15 = 0;
            v163[0] = 0;
            v165 = 0;
            v106 = *((_QWORD *)this + 76);
            if ( v106 )
              (*(void (__fastcall **)(__int64))(*(_QWORD *)v106 + 16LL))(v106);
            *((_QWORD *)this + 76) = v104;
            v107 = CDeploymentSession::ResetState(this, 1, 0);
            v14 = v107;
            if ( v107 < 0 )
            {
              v98 = *((_QWORD *)this + 75);
              if ( !v98 )
                goto LABEL_29;
              LODWORD(v161) = v107;
              LODWORD(v160) = 458;
              goto LABEL_180;
            }
            goto LABEL_261;
          }
LABEL_249:
          v129 = *((_QWORD *)this + 75);
          if ( v129 )
            CMoUpdateLogT<CEmptyType>::MoUpdateLogFormat(v129, 2, L"Creating new session state.");
          if ( v15 )
          {
            (*(void (__fastcall **)(struct IDlpManager *))(*(_QWORD *)v15 + 16LL))(v15);
            v165 = 0;
          }
          v130 = CreateDlpManagerCore((_DWORD)v74, 1, v92, *((_QWORD *)this + 75), (__int64)v160, (__int64)&v165);
          v14 = v130;
          if ( v130 < 0 )
          {
            v131 = *((_QWORD *)this + 75);
            if ( v131 )
            {
              LODWORD(v161) = v130;
              LODWORD(v160) = 464;
              v132 = CMoUpdateLogT<CEmptyType>::MoUpdateLogFormat(
                       v131,
                       4,
                       L"%s(%d): Result = 0x%X",
                       L"CDeploymentSession::InitializeImpl",
                       v160,
                       v161,
                       v162[0]);
              v131 = (unsigned int)v132;
              if ( v132 < 0 )
                CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure((unsigned int)v132, v133);
            }
            CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(v131);
            v15 = v165;
            goto LABEL_9;
          }
          v134 = v165;
          v15 = 0;
          v163[0] = 0;
          v165 = 0;
          v135 = *((_QWORD *)this + 76);
          if ( v135 )
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v135 + 16LL))(v135);
          *((_QWORD *)this + 76) = v134;
LABEL_261:
          v136 = UuidCreate(&Uuid);
          if ( v136 )
          {
            v159 = I_RpcMapWin32Status(v136);
            if ( v159 > 0 )
              v159 = (unsigned __int16)v159 | 0x80070000;
            if ( v159 >= 0 )
              v159 = -2147467259;
            v14 = v159;
            v103 = *((_QWORD *)this + 75);
            v27 = 0;
            if ( !v103 )
              goto LABEL_33;
            LODWORD(v161) = v14;
            LODWORD(v160) = 470;
LABEL_197:
            v98 = v103;
LABEL_180:
            v27 = (unsigned int)CMoUpdateLogT<CEmptyType>::MoUpdateLogFormat(
                                  v98,
                                  4,
                                  L"%s(%d): Result = 0x%X",
                                  L"CDeploymentSession::InitializeImpl",
                                  v160,
                                  v161,
                                  v162[0]);
            goto LABEL_31;
          }
          v137 = CDlpHelpersT<CEmptyType>::GuidToSString(&Uuid, 0, (char *)this + 48);
          v14 = v137;
          v98 = *((_QWORD *)this + 75);
          if ( v137 < 0 )
          {
            if ( !v98 )
              goto LABEL_29;
            LODWORD(v161) = v137;
            LODWORD(v160) = 471;
            goto LABEL_180;
          }
          if ( v98 )
            CMoUpdateLogT<CEmptyType>::MoUpdateLogFormat(v98, 2, L"Session ID [%s]", *((_QWORD *)this + 6));
          if ( *(_QWORD *)v167 )
          {
            v138 = STRAPI_Create(*(const wchar_t **)v167, (wchar_t **)this + 7);
            v14 = v138;
            if ( v138 < 0 )
            {
              v98 = *((_QWORD *)this + 75);
              if ( !v98 )
                goto LABEL_29;
              LODWORD(v161) = v138;
              LODWORD(v160) = 478;
              goto LABEL_180;
            }
          }
          v113 = 0;
          v139 = CDeploymentSession::StateSet(this, 2);
          v14 = v139;
          if ( v139 < 0 )
          {
            v98 = *((_QWORD *)this + 75);
            if ( !v98 )
              goto LABEL_29;
            LODWORD(v161) = v139;
            LODWORD(v160) = 481;
            goto LABEL_180;
          }
LABEL_237:
          v122 = &String2;
          if ( *((_QWORD *)this + 7) )
          {
            IsEnabled = wil::details::FeatureImpl<__WilFeatureTraits_Feature_UpdateAgentWUSARebaseMultiMSU>::__private_IsEnabled(&`wil::Feature<__WilFeatureTraits_Feature_UpdateAgentWUSARebaseMultiMSU>::GetImpl'::`2'::impl);
            v124 = *((_QWORD *)this + 7);
            if ( IsEnabled )
              v125 = CreateSessionData(&v166, v124, (unsigned __int64 *)v74);
            else
              v125 = CreateSessionData(&v166, v124, 0);
            v168 = (void (__fastcall ***)(_QWORD))*v125;
            v126 = v168;
            *v125 = 0;
            v172 = v126;
            if ( v166 )
              (**(void (__fastcall ***)(const wchar_t *))v166)(v166);
            v140 = *((_QWORD *)this + 75);
            if ( v140 )
              CMoUpdateLogT<CEmptyType>::MoUpdateLogFormat(
                v140,
                2,
                L"SessionData: ModuleID           [%d]",
                *((unsigned int *)v126 + 2));
            v141 = *((_QWORD *)this + 75);
            if ( v141 )
            {
              v142 = &String2;
              if ( v126[2] )
                v142 = (const WCHAR *)v126[2];
              CMoUpdateLogT<CEmptyType>::MoUpdateLogFormat(v141, 2, L"SessionData: PackageFileList    [%s]", v142);
            }
            v143 = *((_QWORD *)this + 75);
            if ( v143 )
            {
              v144 = &String2;
              if ( v126[5] )
                v144 = (const WCHAR *)v126[5];
              CMoUpdateLogT<CEmptyType>::MoUpdateLogFormat(v143, 2, L"SessionData: MediaVersion       [%s]", v144);
            }
            v145 = *((_QWORD *)this + 75);
            if ( v145 )
            {
              if ( v126[6] )
                v122 = (const WCHAR *)v126[6];
              CMoUpdateLogT<CEmptyType>::MoUpdateLogFormat(v145, 2, L"SessionData: MediaBranch        [%s]", v122);
            }
            v146 = *((_QWORD *)this + 75);
            if ( v146 )
              CMoUpdateLogT<CEmptyType>::MoUpdateLogFormat(
                v146,
                2,
                L"SessionData: Feature Count      [%lu]",
                *((unsigned int *)v126 + 8));
            for ( i = 0; (unsigned int)i < *((_DWORD *)v126 + 8); i = (unsigned int)(i + 1) )
            {
              v148 = *((_QWORD *)this + 75);
              if ( v148 )
                CMoUpdateLogT<CEmptyType>::MoUpdateLogFormat(
                  v148,
                  2,
                  L"SessionData: Feature [%lu], Name [%s], Language [%s]",
                  (unsigned int)i,
                  v126[3][3 * i],
                  v126[3][3 * i + 1]);
            }
          }
          else
          {
            v126 = v168;
          }
          if ( !v113 )
          {
            IsHostOSMobile = CMoUpdateHelpersT<CEmptyType>::IsHostOSMobile(&v164, *((_QWORD *)this + 70));
            v14 = IsHostOSMobile;
            if ( IsHostOSMobile < 0 )
            {
              v150 = 516;
              goto LABEL_302;
            }
            if ( v164 )
            {
              if ( !v126 )
              {
LABEL_310:
                v113 = 1;
                goto LABEL_350;
              }
              if ( *((_DWORD *)v126 + 2) == 18 )
              {
LABEL_307:
                v113 = 2;
                goto LABEL_350;
              }
              if ( *((_DWORD *)v126 + 2) == 19 )
              {
                *((_DWORD *)this + 81) = 1;
                goto LABEL_310;
              }
              v150 = 532;
LABEL_312:
              v14 = -2147418113;
              v151 = 2147549183LL;
              goto LABEL_303;
            }
            if ( v126 )
            {
              v152 = *((_DWORD *)v126 + 2);
              switch ( v152 )
              {
                case 3:
                  v113 = 6;
                  break;
                case 2:
                  v113 = 5;
                  break;
                case 18:
                  goto LABEL_307;
                case 4:
                  v113 = 8;
                  break;
                case 5:
                  v113 = 9;
                  break;
                case 6:
                  v113 = 10;
                  break;
                case 8:
                  v113 = 11;
                  break;
                case 7:
                  v113 = 12;
                  break;
                case 9:
                  v113 = 13;
                  break;
                case 10:
                  v113 = 14;
                  break;
                case 11:
                  v113 = 15;
                  break;
                case 12:
                  v113 = 16;
                  break;
                case 13:
                  v113 = 17;
                  break;
                case 14:
                  v113 = 18;
                  break;
                case 16:
                  v113 = 22;
                  break;
                default:
                  v113 = 20;
                  if ( v152 != 15 )
                  {
                    if ( v152 == 20 )
                    {
                      v113 = 24;
                    }
                    else
                    {
                      if ( v152 != 21 )
                      {
                        v150 = 618;
                        goto LABEL_312;
                      }
                      v113 = 3;
                    }
                  }
                  break;
              }
            }
            else
            {
              v113 = 0;
            }
          }
LABEL_350:
          *((_DWORD *)this + 114) = v113;
          v168 = 0;
          v172 = 0;
          v153 = (void (__fastcall ***)(_QWORD))*((_QWORD *)this + 59);
          if ( v153 )
            (**v153)(v153);
          *((_QWORD *)this + 59) = v126;
          SH_SSTRING::operator=((char *)this + 64);
          SH_SSTRING::operator=((char *)this + 72);
          SH_SSTRING::operator=((char *)this + 80);
          SH_SSTRING::operator=((char *)this + 88);
          *((struct _GUID *)this + 2) = *v175;
          *((_DWORD *)this + 186) = 0;
          if ( *((_DWORD *)this + 114) == 9
            && (IsHostOSMobile = STRAPI_Create(
                                   *(const wchar_t **)(*((_QWORD *)this + 59) + 16LL),
                                   (wchar_t **)this + 64),
                v14 = IsHostOSMobile,
                IsHostOSMobile < 0) )
          {
            v150 = 643;
          }
          else if ( (unsigned int)(*((_DWORD *)this + 114) - 13) <= 1
                 && *((_QWORD *)this + 76)
                 && (IsHostOSMobile = CDeploymentSession::ResetState(this, 0, 1),
                     v14 = IsHostOSMobile,
                     IsHostOSMobile < 0) )
          {
            v150 = 650;
          }
          else if ( *v177
                 && (IsHostOSMobile = STRAPI_Create(*v177, (wchar_t **)this + 8),
                     v14 = IsHostOSMobile,
                     IsHostOSMobile < 0) )
          {
            v150 = 656;
          }
          else if ( *v178
                 && (IsHostOSMobile = STRAPI_Create(*v178, (wchar_t **)this + 9),
                     v14 = IsHostOSMobile,
                     IsHostOSMobile < 0) )
          {
            v150 = 661;
          }
          else if ( *v179
                 && (IsHostOSMobile = STRAPI_Create(*v179, (wchar_t **)this + 10),
                     v14 = IsHostOSMobile,
                     IsHostOSMobile < 0) )
          {
            v150 = 666;
          }
          else
          {
            if ( !*v180
              || (IsHostOSMobile = STRAPI_Create(*v180, (wchar_t **)this + 11), v14 = IsHostOSMobile,
                                                                                IsHostOSMobile >= 0) )
            {
              *((_DWORD *)this + 93) = *(_DWORD *)v176[0];
              v154 = v167;
              *((_OWORD *)this + 44) = *(_OWORD *)((char *)v167 + 68);
              *((_OWORD *)this + 45) = *(_OWORD *)((char *)v154 + 84);
              *((_DWORD *)this + 184) = *((_DWORD *)v154 + 25);
              *((_DWORD *)this + 185) = *v171;
              if ( !*((_DWORD *)this + 65) )
              {
                IsHostOSMobile = CDeploymentSession::ExpandCompDBs(this);
                v14 = IsHostOSMobile;
                if ( IsHostOSMobile < 0 )
                {
                  v150 = 684;
                  goto LABEL_302;
                }
                *((_DWORD *)this + 65) = 1;
              }
              (*(void (__fastcall **)(_QWORD, _QWORD))(**((_QWORD **)this + 75) + 144LL))(
                *((_QWORD *)this + 75),
                *((unsigned int *)this + 114));
              IsHostOSMobile = (*(__int64 (__fastcall **)(_QWORD, _QWORD))(**((_QWORD **)this + 75) + 104LL))(
                                 *((_QWORD *)this + 75),
                                 *((_QWORD *)this + 6));
              v14 = IsHostOSMobile;
              if ( IsHostOSMobile >= 0 )
              {
                OneSettings = CDeploymentSession::GetOneSettings(this);
                if ( OneSettings < 0 )
                {
                  v156 = *((_QWORD *)this + 75);
                  if ( v156 )
                    CMoUpdateLogT<CEmptyType>::MoUpdateLogFormat(
                      v156,
                      3,
                      L"Error getting OneSettings: [0x%X]",
                      (unsigned int)OneSettings);
                }
                if ( *((_DWORD *)this + 114)
                  && (IsHostOSMobile = CDeploymentSession::CreateScenarioCtrl(this),
                      v14 = IsHostOSMobile,
                      IsHostOSMobile < 0) )
                {
                  v150 = 704;
                }
                else
                {
                  v187 = *((_DWORD *)this + 114);
                  v190 = *((_QWORD *)this + 7);
                  v188 = **(_QWORD **)v169;
                  v189 = *((_QWORD *)this + 62);
                  v196 = *((_QWORD *)this + 75);
                  v192 = *((_QWORD *)this + 8);
                  v193 = *((_QWORD *)this + 10);
                  v191 = *((_QWORD *)this + 9);
                  v194 = v199;
                  v195 = v198;
                  v171 = operator new(0x60u);
                  v176[0] = xmmword_1803ACAA0;
                  v176[1] = (__int64)(*((_QWORD *)&xmmword_1803ACAA0 + 1) - xmmword_1803ACAA0) >> 6;
                  v157 = DeploymentPluginManager::DeploymentPluginManager(v171, &v187, v176);
                  v171 = 0;
                  v158 = *((_QWORD *)this + 81);
                  *((_QWORD *)this + 81) = v157;
                  if ( v158 )
                    std::default_delete<DeploymentPluginManager>::operator()();
                  std::unique_ptr<DeploymentPluginManager>::~unique_ptr<DeploymentPluginManager>(&v171);
                  IsHostOSMobile = CDeploymentSession::Serialize((CDeploymentSession *)((char *)this + 24));
                  v14 = IsHostOSMobile;
                  if ( IsHostOSMobile >= 0 )
                    goto LABEL_8;
                  v150 = 722;
                }
              }
              else
              {
                v150 = 689;
              }
              goto LABEL_302;
            }
            v150 = 671;
          }
LABEL_302:
          v151 = (unsigned int)IsHostOSMobile;
LABEL_303:
          CMoUpdateLogT<CEmptyType>::MoUpdateLogError(
            *((_QWORD *)this + 75),
            v151,
            L"CDeploymentSession::InitializeImpl",
            v150);
          goto LABEL_8;
        }
        v108 = *((_QWORD *)this + 75);
        if ( v108 )
          CMoUpdateLogT<CEmptyType>::MoUpdateLogFormat(v108, 2, L"Resume is supported from this state.");
        if ( !v15 )
          goto LABEL_249;
        v109 = v15;
        v110 = *((_QWORD *)this + 75);
        if ( v110 )
          CMoUpdateLogT<CEmptyType>::MoUpdateLogFormat(v110, 2, L"Loading existing session state.");
        v15 = 0;
        v163[0] = 0;
        v165 = 0;
        v111 = *((_QWORD *)this + 76);
        if ( v111 )
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v111 + 16LL))(v111);
        *((_QWORD *)this + 76) = v109;
        v112 = CDeploymentSession::Deserialize(this);
        v14 = v112;
        if ( v112 < 0 )
        {
          v98 = *((_QWORD *)this + 75);
          if ( !v98 )
            goto LABEL_29;
          LODWORD(v161) = v112;
          LODWORD(v160) = 414;
          goto LABEL_180;
        }
        v113 = *((_DWORD *)this + 114);
        v114 = v167;
        v115 = (const WCHAR **)((char *)this + 56);
        if ( *(_QWORD *)v167 )
        {
          if ( !*v115 )
          {
LABEL_221:
            v117 = *((_QWORD *)this + 75);
            if ( v117 )
            {
              v118 = &String2;
              if ( *v115 )
                v118 = *v115;
              HIDWORD(v160) = HIDWORD(v118);
              CMoUpdateLogT<CEmptyType>::MoUpdateLogFormat(
                v117,
                4,
                L"SessionData mismatch. New value = [%s]. Stored value = [%s]");
            }
            v11 = *((_QWORD *)this + 75);
            if ( (*((_BYTE *)v114 + 64) & 0x10) == 0 )
            {
              if ( v11 )
              {
                LODWORD(v161) = -2147418113;
                LODWORD(v160) = 447;
                v127 = CMoUpdateLogT<CEmptyType>::MoUpdateLogFormat(
                         v11,
                         4,
                         L"%s(%d): Result = 0x%X",
                         L"CDeploymentSession::InitializeImpl",
                         v160,
                         v161,
                         v162[0]);
                v11 = (unsigned int)v127;
                if ( v127 < 0 )
                  CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure((unsigned int)v127, v128);
              }
              v14 = -2147418113;
              goto LABEL_7;
            }
            if ( v11 )
              CMoUpdateLogT<CEmptyType>::MoUpdateLogFormat(
                v11,
                2,
                L"Ignoring because flag is set to ignore session data.");
            v119 = *(void **)v114;
            if ( *(_QWORD *)v114 )
            {
              LODWORD(v162[0]) = 0;
              v120 = CGlobalHelpersT<CEmptyType>::GetStringCchLength<unsigned long>(v119, v162);
              v14 = v120;
              if ( v120 < 0
                || (v120 = CImmutableStringsT<wchar_t,CImmutableStringsPolicyDefault>::CreateInternal(v119),
                    v14 = v120,
                    v120 < 0) )
              {
                CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure((unsigned int)v120, v121);
              }
              CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent((unsigned int)v14);
              if ( v14 < 0 )
              {
                v21 = *((_QWORD *)this + 75);
                if ( !v21 )
                  goto LABEL_21;
                LODWORD(v161) = v14;
                LODWORD(v160) = 441;
                goto LABEL_24;
              }
              *((_DWORD *)this + 68) = 0;
            }
            v74 = (wchar_t *)v166;
            goto LABEL_237;
          }
          v116 = (unsigned int)_o__wcsicmp(*(_QWORD *)v167, *v115) == 0;
        }
        else
        {
          v116 = *v115 == 0;
        }
        if ( v116 )
          goto LABEL_237;
        goto LABEL_221;
      }
    }
    *(_QWORD *)v169 = v78;
    goto LABEL_146;
  }
  catch ( ... )
  {
    return (unsigned int)wil::details::in1diag3::Return_CaughtException(
                           retaddr,
                           (void *)0x2D6,
                           (unsigned int)"onecore\\base\\ntsetup\\conx\\mosetup\\updateagent\\src\\DeploymentSessionImpl.h",
                           v16);
  }
  return result;
}

```

## disassembly

```asm
0x18006b348  mov     r11, rsp
0x18006b34b  push    rbx
0x18006b34c  push    rsi
0x18006b34d  push    rdi
0x18006b34e  push    r12
0x18006b350  push    r13
0x18006b352  push    r14
0x18006b354  push    r15
0x18006b356  sub     rsp, 1C0h
0x18006b35d  mov     qword ptr [r11-118h], 0FFFFFFFFFFFFFFFEh
0x18006b368  mov     rax, cs:__security_cookie
0x18006b36f  xor     rax, rsp
0x18006b372  mov     [rsp+1F8h+var_48], rax
0x18006b37a  mov     rdi, rdx
0x18006b37d  mov     rsi, rcx
0x18006b380  mov     [r11-0E0h], rdx
0x18006b387  mov     [r11-0E8h], r8
0x18006b38e  mov     [r11-0D8h], r9
0x18006b395  mov     r12, [rsp+1F8h+arg_20]
0x18006b39d  mov     rax, [rsp+1F8h+arg_28]
0x18006b3a5  mov     [rsp+1F8h+var_150], rax
0x18006b3ad  mov     r15, [rsp+1F8h+arg_30]
0x18006b3b5  mov     [rsp+1F8h+var_190], r15
0x18006b3ba  xor     ebx, ebx
0x18006b3bc  mov     [rsp+1F8h+var_158], rbx
0x18006b3c4  xor     eax, eax
0x18006b3c6  mov     [rsp+1F8h+var_1B8], rax
0x18006b3cb  mov     [rsp+1F8h+var_1A0], rax
0x18006b3d0  mov     [r11-110h], rax
0x18006b3d7  mov     [r11-160h], rax
0x18006b3de  mov     [rsp+1F8h+var_1A8], eax
0x18006b3e2  mov     [r11-78h], eax
0x18006b3e6  mov     [r11-60h], rax
0x18006b3ea  xorps   xmm0, xmm0
0x18006b3ed  movups  xmmword ptr [r11-58h], xmm0
0x18006b3f2  mov     [r11-178h], rax
0x18006b3f9  mov     [r11-68h], rax
0x18006b3fd  mov     [r11-70h], rax
0x18006b401  mov     [rsp+1F8h+var_188], rax
0x18006b406  mov     [rsp+1F8h+var_168], rax
0x18006b40e  xor     edx, edx; Val
0x18006b410  lea     r8d, [rbx+50h]; Size
0x18006b414  lea     rcx, [r11-0C8h]; void *
0x18006b41b  call    memset_0
0x18006b420  test    rdi, rdi
0x18006b423  jnz     loc_18006B531
0x18006b429  mov     rcx, [rsi+258h]
0x18006b430  test    rcx, rcx
0x18006b433  jz      short loc_18006B468
0x18006b435  mov     dword ptr [rsp+1F8h+var_1D0], 80070057h
0x18006b43d  mov     [rsp+1F8h+var_1D8], 0FBh
0x18006b445  lea     r9, aCdeploymentses_26; "CDeploymentSession::InitializeImpl"
0x18006b44c  lea     r8, aSDResult0xX; "%s(%d): Result = 0x%X"
0x18006b453  mov     edx, 4
0x18006b458  call    ?MoUpdateLogFormat@?$CMoUpdateLogT@VCEmptyType@@@@SAJPEAVIUpdateDiagnostics@@W4MOUPDATE_LOGLEVEL@@PEB_WZZ; CMoUpdateLogT<CEmptyType>::MoUpdateLogFormat(IUpdateDiagnostics *,MOUPDATE_LOGLEVEL,wchar_t const *,...)
0x18006b45d  mov     ecx, eax
0x18006b45f  test    eax, eax
0x18006b461  jns     short loc_18006B468
0x18006b463  call    ?CheckToBreakOnFailure@?$CBreakOnFailureT@VCEmptyType@@@@SAXJ@Z; CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(long)
0x18006b468  mov     edi, 80070057h
0x18006b46d  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x18006b472  mov     r15, [rsp+1F8h+var_1B8]
0x18006b477  mov     ecx, edi
0x18006b479  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x18006b47e  nop
0x18006b47f  mov     rcx, [rsp+1F8h+var_188]
0x18006b484  test    rcx, rcx
0x18006b487  jz      short loc_18006B495
0x18006b489  mov     rax, [rcx]
0x18006b48c  mov     rax, [rax]
0x18006b48f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006b494  nop
0x18006b495  lea     rcx, [rsp+1F8h+var_70]
0x18006b49d  call    ??1?$SP_MEM@_W@@QEAA@XZ; SP_MEM<wchar_t>::~SP_MEM<wchar_t>(void)
0x18006b4a2  nop
0x18006b4a3  lea     rcx, [rsp+1F8h+var_68]
0x18006b4ab  call    ??1?$SP_MEM@_W@@QEAA@XZ; SP_MEM<wchar_t>::~SP_MEM<wchar_t>(void)
0x18006b4b0  nop
0x18006b4b1  lea     rcx, [rsp+1F8h+lpFileName]; this
0x18006b4b9  call    ??1DH_SSTRING@@QEAA@XZ; DH_SSTRING::~DH_SSTRING(void)
0x18006b4be  nop
0x18006b4bf  lea     rcx, [rsp+1F8h+var_60]; this
0x18006b4c7  call    ??1DH_SSTRING@@QEAA@XZ; DH_SSTRING::~DH_SSTRING(void)
0x18006b4cc  nop
0x18006b4cd  lea     rcx, [rsp+1F8h+var_160]
0x18006b4d5  call    ??1?$SP_CPP@VCCBSSessionManager@@@@QEAA@XZ; SP_CPP<CCBSSessionManager>::~SP_CPP<CCBSSessionManager>(void)
0x18006b4da  nop
0x18006b4db  test    r15, r15
0x18006b4de  jz      short loc_18006B4F0
0x18006b4e0  mov     rax, [r15]
0x18006b4e3  mov     rcx, r15
0x18006b4e6  mov     rax, [rax+10h]
0x18006b4ea  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006b4ef  nop
0x18006b4f0  test    rbx, rbx
0x18006b4f3  jz      short loc_18006B505
0x18006b4f5  mov     rax, [rbx]
0x18006b4f8  mov     rcx, rbx
0x18006b4fb  mov     rax, [rax+10h]
0x18006b4ff  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006b504  nop
0x18006b505  mov     eax, edi
0x18006b507  jmp     short loc_18006B50D
0x18006b509  mov     eax, [rsp+1F8h+var_1A8]
0x18006b50d  mov     rcx, [rsp+1F8h+var_48]
0x18006b515  xor     rcx, rsp; StackCookie
0x18006b518  call    __security_check_cookie
0x18006b51d  add     rsp, 1C0h
0x18006b524  pop     r15
0x18006b526  pop     r14
0x18006b528  pop     r13
0x18006b52a  pop     r12
0x18006b52c  pop     rdi
0x18006b52d  pop     rsi
0x18006b52e  pop     rbx
0x18006b52f  retn
0x18006b531  mov     [rsp+1F8h+var_1C8], 0
0x18006b539  lea     rdx, [rsp+1F8h+var_1C8]
0x18006b53e  lea     rcx, a0xca00a0040x80; "0xca00a004;0x800700ce"
0x18006b545  call    ??$GetStringCchLength@K@?$CGlobalHelpersT@VCEmptyType@@@@SAJPEB_WPEAKK@Z; CGlobalHelpersT<CEmptyType>::GetStringCchLength<ulong>(wchar_t const *,ulong *,ulong)
0x18006b54a  mov     edi, eax
0x18006b54c  test    eax, eax
0x18006b54e  js      short loc_18006B56D
0x18006b550  lea     r8, [rsi+2B8h]
0x18006b557  mov     edx, [rsp+1F8h+var_1C8]
0x18006b55b  lea     rcx, a0xca00a0040x80; "0xca00a004;0x800700ce"
0x18006b562  call    ?CreateInternal@?$CImmutableStringsT@_WVCImmutableStringsPolicyDefault@@@@KAJPEB_WKPEAPEA_W@Z; CImmutableStringsT<wchar_t,CImmutableStringsPolicyDefault>::CreateInternal(wchar_t const *,ulong,wchar_t * *)
0x18006b567  mov     edi, eax
0x18006b569  test    eax, eax
0x18006b56b  jns     short loc_18006B574
0x18006b56d  mov     ecx, eax
0x18006b56f  call    ?CheckToBreakOnFailure@?$CBreakOnFailureT@VCEmptyType@@@@SAXJ@Z; CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(long)
0x18006b574  mov     ecx, edi
0x18006b576  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x18006b57b  mov     rax, [rsi+258h]
0x18006b582  test    edi, edi
0x18006b584  jns     short loc_18006B5CD
0x18006b586  test    rax, rax
0x18006b589  jnz     short loc_18006B592
0x18006b58b  xor     ecx, ecx
0x18006b58d  jmp     loc_18006B46D
0x18006b592  mov     dword ptr [rsp+1F8h+var_1D0], edi
0x18006b596  mov     [rsp+1F8h+var_1D8], 0FDh
0x18006b59e  mov     rcx, rax
0x18006b5a1  mov     edx, 4
0x18006b5a6  lea     r8, aSDResult0xX; "%s(%d): Result = 0x%X"
0x18006b5ad  lea     r9, aCdeploymentses_26; "CDeploymentSession::InitializeImpl"
0x18006b5b4  call    ?MoUpdateLogFormat@?$CMoUpdateLogT@VCEmptyType@@@@SAJPEAVIUpdateDiagnostics@@W4MOUPDATE_LOGLEVEL@@PEB_WZZ; CMoUpdateLogT<CEmptyType>::MoUpdateLogFormat(IUpdateDiagnostics *,MOUPDATE_LOGLEVEL,wchar_t const *,...)
0x18006b5b9  mov     ecx, eax
0x18006b5bb  test    eax, eax
0x18006b5bd  jns     loc_18006B46D
0x18006b5c3  call    ?CheckToBreakOnFailure@?$CBreakOnFailureT@VCEmptyType@@@@SAXJ@Z; CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(long)
0x18006b5c8  jmp     loc_18006B46D
0x18006b5cd  test    rax, rax
0x18006b5d0  jnz     loc_18006B876
0x18006b5d6  mov     ecx, 0F0h; Size
0x18006b5db  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18006b5e0  mov     r14, rax
0x18006b5e3  lea     rcx, [rax+8]; void *
0x18006b5e7  xor     edx, edx; Val
0x18006b5e9  mov     r8d, 0E8h; Size
0x18006b5ef  call    memset_0
0x18006b5f4  lea     rax, ??_7?$producers_base@VCUpdateDiagnostics@@V?$tuple@VIUpdateDiagnostics@@@std@@@impl@winrt@@6B@; const winrt::impl::producers_base<CUpdateDiagnostics,std::tuple<IUpdateDiagnostics>>::`vftable'
0x18006b5fb  mov     [r14], rax
0x18006b5fe  lock inc cs:?s_lock@?1??get_module_lock@winrt@@YAAEAUatomic_ref_count@impl@2@XZ@4U342@A; winrt::impl::atomic_ref_count `winrt::get_module_lock(void)'::`2'::s_lock
0x18006b605  mov     r13d, 1
0x18006b60b  mov     [r14+10h], r13
0x18006b60f  lea     rax, ??_7CUpdateDiagnostics@@6B?$producers_base@VCUpdateDiagnostics@@V?$tuple@VIUpdateDiagnostics@@@std@@@impl@winrt@@@; const CUpdateDiagnostics::`vftable'{for `winrt::impl::producers_base<CUpdateDiagnostics,std::tuple<IUpdateDiagnostics>>'}
0x18006b616  mov     [r14], rax
0x18006b619  lea     rax, ??_7CUpdateDiagnostics@@6B?$root_implements@VCUpdateDiagnostics@@VIUpdateDiagnostics@@@impl@winrt@@@; const CUpdateDiagnostics::`vftable'{for `winrt::impl::root_implements<CUpdateDiagnostics,IUpdateDiagnostics>'}
0x18006b620  mov     [r14+8], rax
0x18006b624  lea     rax, ??_7CUpdateDiagnostics@@6BIArbiterDiagnostics@@@; const CUpdateDiagnostics::`vftable'{for `IArbiterDiagnostics'}
0x18006b62b  mov     [r14+18h], rax
0x18006b62f  lea     rax, ??_7CUpdateDiagnostics@@6BIMitiDiagnostics@@@; const CUpdateDiagnostics::`vftable'{for `IMitiDiagnostics'}
0x18006b636  mov     [r14+20h], rax
0x18006b63a  xor     r15d, r15d
0x18006b63d  mov     [r14+28h], r15
0x18006b641  mov     [r14+30h], r15
0x18006b645  xorps   xmm0, xmm0
0x18006b648  movups  xmmword ptr [r14+38h], xmm0
0x18006b64d  mov     [r14+48h], r15
0x18006b651  mov     qword ptr [r14+50h], 0Fh
0x18006b659  mov     [r14+38h], r15b
0x18006b65d  mov     [r14+58h], r15
0x18006b661  mov     [r14+60h], r15
0x18006b665  mov     [r14+68h], r15
0x18006b669  mov     [r14+70h], r15
0x18006b66d  mov     [r14+78h], r15
0x18006b671  mov     [r14+80h], r15
0x18006b678  mov     [r14+88h], r15
0x18006b67f  mov     [r14+90h], r15
0x18006b686  mov     [r14+98h], r15
0x18006b68d  mov     [r14+0A0h], r15w
0x18006b695  mov     [r14+0A4h], r15d
0x18006b69c  movups  xmmword ptr [r14+0A8h], xmm0
0x18006b6a4  mov     [r14+0B8h], r15
0x18006b6ab  mov     rbx, r14
0x18006b6ae  mov     [rsp+1F8h+var_158], rbx
0x18006b6b6  lea     rcx, [rsp+1F8h+lpFileName]
0x18006b6be  call    ?GetDefaultLogFolderPath@?$CMoUpdateLogT@VCEmptyType@@@@SAJPEAPEA_W@Z; CMoUpdateLogT<CEmptyType>::GetDefaultLogFolderPath(wchar_t * *)
0x18006b6c3  mov     edi, eax
0x18006b6c5  test    eax, eax
0x18006b6c7  jns     short loc_18006B712
0x18006b6c9  mov     rcx, [rsi+258h]
0x18006b6d0  test    rcx, rcx
0x18006b6d3  jnz     short loc_18006B6D9
0x18006b6d5  xor     ecx, ecx
0x18006b6d7  jmp     short loc_18006B708
0x18006b6d9  mov     dword ptr [rsp+1F8h+var_1D0], eax
0x18006b6dd  mov     [rsp+1F8h+var_1D8], 105h
0x18006b6e5  lea     r9, aCdeploymentses_26; "CDeploymentSession::InitializeImpl"
0x18006b6ec  lea     r8, aSDResult0xX; "%s(%d): Result = 0x%X"
0x18006b6f3  mov     edx, 4
0x18006b6f8  call    ?MoUpdateLogFormat@?$CMoUpdateLogT@VCEmptyType@@@@SAJPEAVIUpdateDiagnostics@@W4MOUPDATE_LOGLEVEL@@PEB_WZZ; CMoUpdateLogT<CEmptyType>::MoUpdateLogFormat(IUpdateDiagnostics *,MOUPDATE_LOGLEVEL,wchar_t const *,...)
0x18006b6fd  mov     ecx, eax
0x18006b6ff  test    ecx, ecx
0x18006b701  jns     short loc_18006B708
0x18006b703  call    ?CheckToBreakOnFailure@?$CBreakOnFailureT@VCEmptyType@@@@SAXJ@Z; CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(long)
0x18006b708  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x18006b70d  jmp     loc_18006B477
0x18006b712  mov     r15, [rsp+1F8h+lpFileName]
0x18006b71a  mov     rcx, r15; lpFileName
0x18006b71d  call    cs:__imp_GetFileAttributesW
0x18006b724  nop     dword ptr [rax+rax+00h]
0x18006b729  mov     edi, eax
0x18006b72b  cmp     eax, 0FFFFFFFFh
0x18006b72e  jz      short loc_18006B738
0x18006b730  shr     edi, 4
0x18006b733  and     edi, r13d
0x18006b736  jmp     short loc_18006B73A
0x18006b738  xor     edi, edi
0x18006b73a  xor     ecx, ecx
0x18006b73c  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x18006b741  xor     ecx, ecx
0x18006b743  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x18006b748  test    edi, edi
0x18006b74a  jnz     short loc_18006B7B0
0x18006b74c  xor     edx, edx; lpSecurityAttributes
0x18006b74e  mov     rcx, r15; lpPathName
0x18006b751  call    cs:__imp_CreateDirectoryW
0x18006b758  nop     dword ptr [rax+rax+00h]
0x18006b75d  test    eax, eax
0x18006b75f  jnz     short loc_18006B7B0
0x18006b761  call    cs:__imp_GetLastError
0x18006b768  nop     dword ptr [rax+rax+00h]
0x18006b76d  mov     edi, eax
0x18006b76f  test    eax, eax
0x18006b771  jnz     short loc_18006B77A
0x18006b773  mov     edi, 80004005h
0x18006b778  jmp     short loc_18006B785
0x18006b77a  jle     short loc_18006B785
0x18006b77c  movzx   edi, ax
0x18006b77f  or      edi, 80070000h
0x18006b785  mov     rax, [rsi+258h]
0x18006b78c  xor     ecx, ecx
0x18006b78e  test    edi, edi
0x18006b790  jns     loc_18006B46D
0x18006b796  test    rax, rax
0x18006b799  jz      loc_18006B46D
0x18006b79f  mov     dword ptr [rsp+1F8h+var_1D0], edi
0x18006b7a3  mov     [rsp+1F8h+var_1D8], 109h
0x18006b7ab  jmp     loc_18006B59E
0x18006b7b0  mov     rax, [r14]
0x18006b7b3  mov     rdx, [rsp+1F8h+var_190]
0x18006b7b8  mov     rcx, [rdx+28h]
0x18006b7bc  mov     qword ptr [rsp+1F8h+var_1D8], rcx
0x18006b7c1  mov     r9, [rdx+20h]
0x18006b7c5  mov     r8, r15
0x18006b7c8  mov     edx, r13d
0x18006b7cb  mov     rcx, r14
0x18006b7ce  mov     rax, [rax+38h]
0x18006b7d2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006b7d7  mov     edi, eax
0x18006b7d9  test    eax, eax
0x18006b7db  jns     short loc_18006B7FE
0x18006b7dd  mov     rcx, [rsi+258h]
0x18006b7e4  test    rcx, rcx
0x18006b7e7  jz      loc_18006B58B
0x18006b7ed  mov     dword ptr [rsp+1F8h+var_1D0], eax
0x18006b7f1  mov     [rsp+1F8h+var_1D8], 10Ch
0x18006b7f9  jmp     loc_18006B5A1
0x18006b7fe  mov     [rsp+1F8h+lpFileName], 0
0x18006b80a  mov     rbx, [rsi+208h]
0x18006b811  test    rbx, rbx
0x18006b814  jz      short loc_18006B83E
0x18006b816  call    cs:__imp_GetProcessHeap
0x18006b81d  nop     dword ptr [rax+rax+00h]
0x18006b822  mov     rcx, rax; hHeap
0x18006b825  lea     r8, [rbx-4]; lpMem
0x18006b829  xor     edx, edx; dwFlags
0x18006b82b  call    cs:__imp_HeapFree
0x18006b832  nop     dword ptr [rax+rax+00h]
0x18006b837  xor     ecx, ecx
0x18006b839  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x18006b83e  mov     [rsi+208h], r15
0x18006b845  xor     ebx, ebx
0x18006b847  mov     [rsp+1F8h+var_158], rbx
0x18006b84f  mov     rcx, [rsi+258h]
0x18006b856  test    rcx, rcx
0x18006b859  jz      short loc_18006B868
  ... truncated ...
```
