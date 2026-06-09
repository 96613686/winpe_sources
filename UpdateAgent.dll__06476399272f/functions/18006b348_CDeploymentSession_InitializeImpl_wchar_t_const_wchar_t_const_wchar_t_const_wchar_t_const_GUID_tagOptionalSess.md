# CDeploymentSession::InitializeImpl(wchar_t const *,wchar_t const *,wchar_t const *,wchar_t const *,_GUID,tagOptionalSessionInfo6 const &)

- ea: `0x18006b348`
- end: `0x18006cf02`
- name: `?InitializeImpl@CDeploymentSession@@AEAAJPEB_W000U_GUID@@AEBUtagOptionalSessionInfo6@@@Z`
- size: `7098`
- prototype: `__int64 __fastcall(CDeploymentSession *this, wchar_t *, wchar_t *, wchar_t *, wchar_t *, struct _GUID *, const struct tagOptionalSessionInfo6 *)`
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
  signed int v13; // edi
  struct IDlpManager *v14; // r15
  const char *v15; // r9
  __int64 result; // rax
  int StringCch; // eax
  __int64 v18; // rax
  __int64 v19; // rcx
  int v20; // eax
  char *v21; // r14
  int DefaultLogFolderPath; // eax
  __int64 v23; // rcx
  __int64 v24; // rcx
  const WCHAR *v25; // r15
  DWORD FileAttributesW; // edi
  int v27; // edi
  signed int LastError; // eax
  int v29; // eax
  __int64 v30; // rbx
  HANDLE ProcessHeap; // rax
  __int64 v32; // rcx
  CCBSSessionManager *v33; // rdi
  void *v34; // r14
  __int64 v35; // rcx
  int v36; // eax
  int v37; // eax
  __int64 v38; // rdx
  struct CWatsonHelper *Instance; // rdi
  __int64 v40; // rcx
  _BYTE *v41; // rax
  int v42; // edx
  int v43; // eax
  __int64 v44; // rcx
  _BYTE *v45; // rax
  int v46; // r14d
  int v47; // eax
  int v48; // eax
  int v49; // eax
  __int64 v50; // rdx
  const struct tagOptionalSessionInfo6 *v51; // rdi
  __int64 v52; // rdx
  __int64 v53; // r8
  int v54; // r9d
  __int64 v55; // rcx
  void *v56; // r14
  int Internal; // eax
  wchar_t *v58; // r14
  int v59; // eax
  void *v60; // r14
  int v61; // eax
  void *v62; // r14
  int v63; // eax
  int v64; // eax
  wchar_t *v65; // r12
  __int64 v66; // rcx
  int v67; // eax
  _QWORD *v68; // r15
  int v69; // eax
  LPCWSTR *v70; // r14
  int v71; // eax
  int v72; // eax
  int v73; // eax
  int v74; // eax
  int v75; // edi
  _QWORD *v76; // rax
  _QWORD *v77; // rcx
  int v78; // r8d
  int DlpManagerCore; // eax
  int v80; // r8d
  __int64 v81; // rcx
  int v82; // eax
  __int64 v83; // rcx
  __int64 v84; // rcx
  int v85; // eax
  __int64 v86; // rcx
  DWORD v87; // eax
  BOOL v88; // edi
  __int64 v89; // rcx
  signed int v90; // eax
  __int64 v91; // rax
  struct IDlpManager *v92; // rdi
  __int64 v93; // rcx
  __int64 v94; // rcx
  int v95; // eax
  __int64 v96; // rcx
  struct IDlpManager *v97; // rdi
  __int64 v98; // rcx
  __int64 v99; // rcx
  int v100; // eax
  int v101; // r14d
  const struct tagOptionalSessionInfo6 *v102; // rdi
  const WCHAR **v103; // r15
  bool v104; // zf
  __int64 v105; // rcx
  const WCHAR *v106; // rax
  void *v107; // r12
  int v108; // eax
  const WCHAR *v109; // rdi
  char IsEnabled; // al
  __int64 v111; // rdx
  _QWORD *v112; // rax
  void (__fastcall ***v113)(_QWORD); // r15
  int v114; // eax
  __int64 v115; // rcx
  int v116; // eax
  __int64 v117; // rcx
  int v118; // eax
  struct IDlpManager *v119; // rdi
  __int64 v120; // rcx
  RPC_STATUS v121; // eax
  int v122; // eax
  int v123; // eax
  int v124; // eax
  __int64 v125; // rcx
  __int64 v126; // rcx
  const WCHAR *v127; // r9
  __int64 v128; // rcx
  const WCHAR *v129; // r9
  __int64 v130; // rcx
  __int64 v131; // rcx
  __int64 i; // rdi
  __int64 v133; // rcx
  int IsHostOSMobile; // eax
  __int64 v135; // r9
  __int64 v136; // rdx
  int v137; // eax
  void (__fastcall ***v138)(_QWORD); // rcx
  const struct tagOptionalSessionInfo6 *v139; // rax
  int OneSettings; // eax
  __int64 v141; // rcx
  __int64 v142; // rax
  __int64 v143; // rdx
  int v144; // eax
  __int64 *v145; // [rsp+20h] [rbp-1D8h]
  const wchar_t **v146; // [rsp+28h] [rbp-1D0h]
  _QWORD v147[2]; // [rsp+30h] [rbp-1C8h] BYREF
  _QWORD v148[2]; // [rsp+40h] [rbp-1B8h] BYREF
  int v149; // [rsp+50h] [rbp-1A8h] BYREF
  struct IDlpManager *v150; // [rsp+58h] [rbp-1A0h] BYREF
  const wchar_t *v151; // [rsp+60h] [rbp-198h] BYREF
  const struct tagOptionalSessionInfo6 *v152; // [rsp+68h] [rbp-190h]
  void (__fastcall ***v153)(_QWORD); // [rsp+70h] [rbp-188h]
  int v154[2]; // [rsp+78h] [rbp-180h] BYREF
  LPCWSTR lpFileName; // [rsp+80h] [rbp-178h] BYREF
  _DWORD *v156; // [rsp+88h] [rbp-170h] BYREF
  void (__fastcall ***v157)(_QWORD); // [rsp+90h] [rbp-168h]
  CCBSSessionManager *v158; // [rsp+98h] [rbp-160h] BYREF
  char *v159; // [rsp+A0h] [rbp-158h]
  struct _GUID *v160; // [rsp+A8h] [rbp-150h]
  _QWORD v161[2]; // [rsp+B0h] [rbp-148h] BYREF
  const wchar_t **v162; // [rsp+C0h] [rbp-138h]
  const wchar_t **v163; // [rsp+C8h] [rbp-130h]
  const wchar_t **v164; // [rsp+D0h] [rbp-128h]
  const wchar_t **v165; // [rsp+D8h] [rbp-120h]
  __int64 v166; // [rsp+E0h] [rbp-118h]
  __int64 v167; // [rsp+E8h] [rbp-110h]
  _BYTE v168[32]; // [rsp+F0h] [rbp-108h] BYREF
  wchar_t *v169; // [rsp+110h] [rbp-E8h] BYREF
  void *Src; // [rsp+118h] [rbp-E0h] BYREF
  void *v171; // [rsp+120h] [rbp-D8h] BYREF
  int v172; // [rsp+130h] [rbp-C8h] BYREF
  __int64 v173; // [rsp+138h] [rbp-C0h]
  __int64 v174; // [rsp+140h] [rbp-B8h]
  __int64 v175; // [rsp+148h] [rbp-B0h]
  __int64 v176; // [rsp+150h] [rbp-A8h]
  __int64 v177; // [rsp+158h] [rbp-A0h]
  __int64 v178; // [rsp+160h] [rbp-98h]
  __int64 v179; // [rsp+168h] [rbp-90h]
  __int64 v180; // [rsp+170h] [rbp-88h]
  __int64 v181; // [rsp+178h] [rbp-80h]
  unsigned int v182; // [rsp+180h] [rbp-78h] BYREF
  __int64 v183; // [rsp+188h] [rbp-70h] BYREF
  __int64 v184; // [rsp+190h] [rbp-68h] BYREF
  __int64 v185; // [rsp+198h] [rbp-60h] BYREF
  UUID Uuid; // [rsp+1A0h] [rbp-58h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+1F8h] [rbp+0h]

  v166 = -2;
  Src = a2;
  v169 = a3;
  v171 = a4;
  v160 = a6;
  v9 = a7;
  v152 = a7;
  v10 = 0;
  v159 = 0;
  v148[0] = 0;
  v150 = 0;
  v167 = 0;
  v158 = 0;
  v149 = 0;
  v182 = 0;
  v185 = 0;
  Uuid = 0;
  lpFileName = 0;
  v184 = 0;
  v183 = 0;
  v153 = 0;
  v157 = 0;
  memset_0(&v172, 0, 0x50u);
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
          CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure((unsigned int)updated);
      }
      v13 = -2147024809;
      goto LABEL_7;
    }
    LODWORD(v147[0]) = 0;
    StringCch = CGlobalHelpersT<CEmptyType>::GetStringCchLength<unsigned long>(L"0xca00a004;0x800700ce", v147);
    v13 = StringCch;
    if ( StringCch < 0
      || (StringCch = CImmutableStringsT<wchar_t,CImmutableStringsPolicyDefault>::CreateInternal(L"0xca00a004;0x800700ce"),
          v13 = StringCch,
          StringCch < 0) )
    {
      CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure((unsigned int)StringCch);
    }
    CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent((unsigned int)v13);
    v18 = *((_QWORD *)this + 75);
    if ( v13 < 0 )
    {
      if ( !v18 )
      {
LABEL_21:
        v11 = 0;
LABEL_7:
        CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(v11);
LABEL_8:
        v14 = (struct IDlpManager *)v148[0];
LABEL_9:
        CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent((unsigned int)v13);
        if ( v153 )
          (**v153)(v153);
        SP_MEM<wchar_t>::~SP_MEM<wchar_t>(&v183);
        SP_MEM<wchar_t>::~SP_MEM<wchar_t>(&v184);
        DH_SSTRING::~DH_SSTRING((DH_SSTRING *)&lpFileName);
        DH_SSTRING::~DH_SSTRING((DH_SSTRING *)&v185);
        SP_CPP<CCBSSessionManager>::~SP_CPP<CCBSSessionManager>(&v158);
        if ( v14 )
          (*(void (__fastcall **)(struct IDlpManager *))(*(_QWORD *)v14 + 16LL))(v14);
        if ( v10 )
          (*(void (__fastcall **)(char *))(*(_QWORD *)v10 + 16LL))(v10);
        return (unsigned int)v13;
      }
      LODWORD(v146) = v13;
      LODWORD(v145) = 253;
      goto LABEL_23;
    }
    if ( !v18 )
    {
      v21 = (char *)operator new(0xF0u);
      memset_0(v21 + 8, 0, 0xE8u);
      *(_QWORD *)v21 = &winrt::impl::producers_base<CUpdateDiagnostics,std::tuple<IUpdateDiagnostics>>::`vftable';
      _InterlockedIncrement(&`winrt::get_module_lock'::`2'::s_lock);
      *((_QWORD *)v21 + 2) = 1;
      *(_QWORD *)v21 = &CUpdateDiagnostics::`vftable'{for `winrt::impl::producers_base<CUpdateDiagnostics,std::tuple<IUpdateDiagnostics>>'};
      *((_QWORD *)v21 + 1) = &CUpdateDiagnostics::`vftable'{for `winrt::impl::root_implements<CUpdateDiagnostics,IUpdateDiagnostics>'};
      *((_QWORD *)v21 + 3) = &CUpdateDiagnostics::`vftable'{for `IArbiterDiagnostics'};
      *((_QWORD *)v21 + 4) = &CUpdateDiagnostics::`vftable'{for `IMitiDiagnostics'};
      v14 = 0;
      *((_QWORD *)v21 + 5) = 0;
      *((_QWORD *)v21 + 6) = 0;
      *(_OWORD *)(v21 + 56) = 0;
      *((_QWORD *)v21 + 9) = 0;
      *((_QWORD *)v21 + 10) = 15;
      v21[56] = 0;
      *((_QWORD *)v21 + 11) = 0;
      *((_QWORD *)v21 + 12) = 0;
      *((_QWORD *)v21 + 13) = 0;
      *((_QWORD *)v21 + 14) = 0;
      *((_QWORD *)v21 + 15) = 0;
      *((_QWORD *)v21 + 16) = 0;
      *((_QWORD *)v21 + 17) = 0;
      *((_QWORD *)v21 + 18) = 0;
      *((_QWORD *)v21 + 19) = 0;
      *((_WORD *)v21 + 80) = 0;
      *((_DWORD *)v21 + 41) = 0;
      *(_OWORD *)(v21 + 168) = 0;
      *((_QWORD *)v21 + 23) = 0;
      v10 = v21;
      v159 = v21;
      DefaultLogFolderPath = CMoUpdateLogT<CEmptyType>::GetDefaultLogFolderPath(&lpFileName);
      v13 = DefaultLogFolderPath;
      if ( DefaultLogFolderPath < 0 )
      {
        v23 = *((_QWORD *)this + 75);
        if ( !v23 )
        {
LABEL_29:
          v24 = 0;
LABEL_33:
          CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(v24);
          goto LABEL_9;
        }
        v24 = (unsigned int)CMoUpdateLogT<CEmptyType>::MoUpdateLogFormat(
                              v23,
                              4,
                              L"%s(%d): Result = 0x%X",
                              L"CDeploymentSession::InitializeImpl",
                              261,
                              DefaultLogFolderPath);
LABEL_31:
        if ( (int)v24 < 0 )
          CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(v24);
        goto LABEL_33;
      }
      v25 = lpFileName;
      FileAttributesW = GetFileAttributesW(lpFileName);
      if ( FileAttributesW == -1 )
        v27 = 0;
      else
        v27 = (FileAttributesW >> 4) & 1;
      CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(0);
      CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(0);
      if ( !v27 && !CreateDirectoryW(v25, 0) )
      {
        LastError = GetLastError();
        v13 = LastError;
        if ( LastError )
        {
          if ( LastError > 0 )
            v13 = (unsigned __int16)LastError | 0x80070000;
        }
        else
        {
          v13 = -2147467259;
        }
        v18 = *((_QWORD *)this + 75);
        v11 = 0;
        if ( v13 >= 0 || !v18 )
          goto LABEL_7;
        LODWORD(v146) = v13;
        LODWORD(v145) = 265;
LABEL_23:
        v19 = v18;
        goto LABEL_24;
      }
      v145 = (__int64 *)*((_QWORD *)v152 + 5);
      v29 = (*(__int64 (__fastcall **)(char *, __int64, const WCHAR *, _QWORD))(*(_QWORD *)v21 + 56LL))(
              v21,
              1,
              v25,
              *((_QWORD *)v152 + 4));
      v13 = v29;
      if ( v29 < 0 )
      {
        v19 = *((_QWORD *)this + 75);
        if ( !v19 )
          goto LABEL_21;
        LODWORD(v146) = v29;
        LODWORD(v145) = 268;
LABEL_24:
        v20 = CMoUpdateLogT<CEmptyType>::MoUpdateLogFormat(
                v19,
                4,
                L"%s(%d): Result = 0x%X",
                L"CDeploymentSession::InitializeImpl",
                v145,
                v146);
        v11 = (unsigned int)v20;
        if ( v20 < 0 )
          CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure((unsigned int)v20);
        goto LABEL_7;
      }
      lpFileName = 0;
      v30 = *((_QWORD *)this + 65);
      if ( v30 )
      {
        ProcessHeap = GetProcessHeap();
        HeapFree(ProcessHeap, 0, (LPVOID)(v30 - 4));
        CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(0);
      }
      *((_QWORD *)this + 65) = v25;
      v10 = 0;
      v159 = 0;
      v32 = *((_QWORD *)this + 75);
      if ( v32 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v32 + 16LL))(v32);
      *((_QWORD *)this + 75) = v21;
      v9 = v152;
    }
    v33 = (CCBSSessionManager *)operator new(0x18u);
    *(_QWORD *)v33 = 0;
    *((_QWORD *)v33 + 1) = 0;
    *((_QWORD *)v33 + 2) = 0;
    v158 = v33;
    CCBSSessionManager::Initialize(v33, *((struct IUpdateDiagnostics **)this + 75), v169, a5);
    v158 = 0;
    v34 = (void *)*((_QWORD *)this + 83);
    if ( v34 )
    {
      CCBSSessionManager::~CCBSSessionManager(*((CCBSSessionManager **)this + 83));
      operator delete(v34, (const struct std::nothrow_t *)0x18);
    }
    *((_QWORD *)this + 83) = v33;
    v35 = *((_QWORD *)this + 75);
    v162 = (const wchar_t **)((char *)v9 + 16);
    v36 = (*(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v35 + 120LL))(v35, *((_QWORD *)v9 + 2));
    v13 = v36;
    v19 = *((_QWORD *)this + 75);
    if ( v36 < 0 )
    {
      if ( !v19 )
        goto LABEL_21;
      LODWORD(v146) = v36;
      LODWORD(v145) = 277;
      goto LABEL_24;
    }
    v163 = (const wchar_t **)((char *)v9 + 8);
    v37 = (*(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v19 + 128LL))(v19, *((_QWORD *)v9 + 1));
    v13 = v37;
    v19 = *((_QWORD *)this + 75);
    if ( v37 < 0 )
    {
      if ( !v19 )
        goto LABEL_21;
      LODWORD(v146) = v37;
      LODWORD(v145) = 278;
      goto LABEL_24;
    }
    (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v19 + 160LL))(v19, 1);
    Instance = CWatsonHelper::GetInstance();
    v151 = L"ON";
    LODWORD(v147[0]) = 1;
    if ( *(_QWORD *)&LogAdapter::g_Logger )
    {
      v146 = &v151;
      v145 = v147;
      LOBYTE(v38) = 1;
      LogAdapter::Logger::LogNumObjects<unsigned long,wchar_t const *>(
        *(_QWORD *)&LogAdapter::g_Logger,
        v38,
        1,
        "WatsonHelper: Bucket parameter [{}] mute: [{}]");
    }
    *(_BYTE *)(*((_QWORD *)Instance + 8) + 1LL) = 1;
    CDeploymentSession::InitializeWatsonIgnoredErrors(this);
    if ( *((_QWORD *)v9 + 4) )
    {
      v40 = 0x7FFFFFFF;
      v41 = (_BYTE *)*((_QWORD *)v9 + 4);
      while ( *v41 )
      {
        ++v41;
        if ( !--v40 )
        {
          v13 = -2147024809;
          v42 = 0;
          goto LABEL_70;
        }
      }
      v13 = 0;
      v42 = 0x7FFFFFFF - v40;
LABEL_70:
      if ( v13 < 0 )
      {
        v19 = *((_QWORD *)this + 75);
        if ( !v19 )
          goto LABEL_21;
        LODWORD(v146) = v13;
        LODWORD(v145) = 288;
        goto LABEL_24;
      }
      v43 = CStringConvertT<unsigned long>::A2W(*((LPCCH *)v9 + 4), v42);
      v13 = v43;
      if ( v43 < 0 )
      {
        v19 = *((_QWORD *)this + 75);
        if ( !v19 )
          goto LABEL_21;
        LODWORD(v146) = v43;
        LODWORD(v145) = 289;
        goto LABEL_24;
      }
    }
    if ( *((_QWORD *)v9 + 5) )
    {
      v44 = 0x7FFFFFFF;
      v45 = (_BYTE *)*((_QWORD *)v9 + 5);
      while ( *v45 )
      {
        ++v45;
        if ( !--v44 )
        {
          v13 = -2147024809;
          v46 = 0;
          goto LABEL_82;
        }
      }
      v13 = 0;
      v46 = 0x7FFFFFFF - v44;
LABEL_82:
      if ( v13 < 0 )
      {
        v19 = *((_QWORD *)this + 75);
        if ( !v19 )
          goto LABEL_21;
        LODWORD(v146) = v13;
        LODWORD(v145) = 294;
        goto LABEL_24;
      }
      v47 = CStringConvertT<unsigned long>::A2W(*((LPCCH *)v9 + 5), v46);
      v13 = v47;
      if ( v47 < 0 )
      {
        v19 = *((_QWORD *)this + 75);
        if ( !v19 )
          goto LABEL_21;
        LODWORD(v146) = v47;
        LODWORD(v145) = 295;
        goto LABEL_24;
      }
    }
    v48 = CDeploymentSession::CheckUpdateBlocks(this);
    v13 = v48;
    if ( v48 < 0 )
    {
      v19 = *((_QWORD *)this + 75);
      if ( !v19 )
        goto LABEL_21;
      LODWORD(v146) = v48;
      LODWORD(v145) = 300;
      goto LABEL_24;
    }
    LogAdapter::TraceInfo<wchar_t const *>("CDeploymentSession: Initializing SandboxPath = [{}]", &Src);
    LogAdapter::TraceInfo<wchar_t const *>("CDeploymentSession: Initializing OfflineWinDirPath = [{}]", &v169);
    LogAdapter::TraceInfo<wchar_t const *>("CDeploymentSession: Initializing DeviceInfoPath = [{}]", &v171);
    LogAdapter::TraceInfo<wchar_t const *>("CDeploymentSession: Initializing MergedSandboxPath = [{}]", (char *)v9 + 48);
    v49 = CDlpHelpersT<CEmptyType>::GuidToSString(v160, 0, &v185);
    v13 = v49;
    if ( v49 < 0 )
    {
      v19 = *((_QWORD *)this + 75);
      if ( !v19 )
        goto LABEL_21;
      LODWORD(v146) = v49;
      LODWORD(v145) = 308;
      goto LABEL_24;
    }
    if ( *(_QWORD *)&LogAdapter::g_Logger )
    {
      v145 = &v185;
      LOBYTE(v50) = 1;
      LogAdapter::Logger::LogNumObjects<Windows::AutoGenericHandle<wchar_t *,0,&void Windows::Detail::CloseWithCoTaskMemFree<wchar_t>(wchar_t *)>>(
        *(_QWORD *)&LogAdapter::g_Logger,
        v50,
        1,
        "CDeploymentSession: Initializing Callback Factory Guid = [{}]");
    }
    v51 = v152;
    LogAdapter::TraceInfo<wchar_t const *>("CDeploymentSession: Initializing SessionData = [{}]", v152);
    LogAdapter::TraceInfo<wchar_t const *>("CDeploymentSession: Initializing UpdateId = [{}]", (char *)v51 + 8);
    LogAdapter::TraceInfo<wchar_t const *>("CDeploymentSession: Initializing FlightId = [{}]", (char *)v51 + 16);
    v164 = (const wchar_t **)((char *)v51 + 24);
    LogAdapter::TraceInfo<wchar_t const *>("CDeploymentSession: Initializing FlightMetadata = [{}]", (char *)v51 + 24);
    v165 = (const wchar_t **)((char *)v51 + 56);
    LogAdapter::TraceInfo<wchar_t const *>("CDeploymentSession: Initializing Country Code = [{}]", (char *)v51 + 56);
    v161[0] = (char *)v51 + 64;
    LogAdapter::TraceInfo<unsigned long>("CDeploymentSession: Initializing optional flags = [{}]", (char *)v51 + 64);
    v55 = *(_QWORD *)&LogAdapter::g_Logger;
    if ( *(_QWORD *)&LogAdapter::g_Logger )
    {
      v145 = &v184;
      LogAdapter::Logger::LogNumObjects<SP_MEM<wchar_t>>(
        *(_QWORD *)&LogAdapter::g_Logger,
        v52,
        v53,
        "CDeploymentSession: Initializing CorrelationVector = [{}]");
      v55 = *(_QWORD *)&LogAdapter::g_Logger;
      if ( *(_QWORD *)&LogAdapter::g_Logger )
      {
        v145 = &v183;
        LogAdapter::Logger::LogNumObjects<SP_MEM<wchar_t>>(
          *(_QWORD *)&LogAdapter::g_Logger,
          v52,
          v53,
          "CDeploymentSession: Initializing RelatedCV = [{}]");
        v55 = *(_QWORD *)&LogAdapter::g_Logger;
      }
    }
    v151 = (const wchar_t *)((char *)v51 + 64);
    if ( v55 )
    {
      LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHex8Wrapper<unsigned long>>(
        v55,
        v52,
        v53,
        v54,
        (__int64)&v151);
      v55 = *(_QWORD *)&LogAdapter::g_Logger;
    }
    v156 = (_DWORD *)((char *)v51 + 104);
    *(_QWORD *)v154 = (char *)v51 + 104;
    if ( v55 )
      LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHex8Wrapper<enum tagSessionDownloadCapabilityFlags>>(
        v55,
        v52,
        v53,
        v54,
        (__int64)v154);
    v56 = Src;
    LODWORD(v147[0]) = 0;
    if ( Src
      && (Internal = CGlobalHelpersT<CEmptyType>::GetStringCchLength<unsigned long>(Src, v147),
          v13 = Internal,
          Internal < 0)
      || (Internal = CImmutableStringsT<wchar_t,CImmutableStringsPolicyDefault>::CreateInternal(v56),
          v13 = Internal,
          Internal < 0) )
    {
      CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure((unsigned int)Internal);
    }
    CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent((unsigned int)v13);
    if ( v13 < 0 )
    {
      v19 = *((_QWORD *)this + 75);
      if ( !v19 )
        goto LABEL_21;
      LODWORD(v146) = v13;
      LODWORD(v145) = 325;
      goto LABEL_24;
    }
    v58 = v169;
    LODWORD(v147[0]) = 0;
    if ( v169 && (v59 = CGlobalHelpersT<CEmptyType>::GetStringCchLength<unsigned long>(v169, v147), v13 = v59, v59 < 0)
      || (v59 = CImmutableStringsT<wchar_t,CImmutableStringsPolicyDefault>::CreateInternal(v58), v13 = v59, v59 < 0) )
    {
      CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure((unsigned int)v59);
    }
    CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent((unsigned int)v13);
    if ( v13 < 0 )
    {
      v19 = *((_QWORD *)this + 75);
      if ( !v19 )
        goto LABEL_21;
      LODWORD(v146) = v13;
      LODWORD(v145) = 326;
      goto LABEL_24;
    }
    v60 = v171;
    LODWORD(v147[0]) = 0;
    if ( v171 && (v61 = CGlobalHelpersT<CEmptyType>::GetStringCchLength<unsigned long>(v171, v147), v13 = v61, v61 < 0)
      || (v61 = CImmutableStringsT<wchar_t,CImmutableStringsPolicyDefault>::CreateInternal(v60), v13 = v61, v61 < 0) )
    {
      CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure((unsigned int)v61);
    }
    CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent((unsigned int)v13);
    if ( v13 < 0 )
    {
      v19 = *((_QWORD *)this + 75);
      if ( !v19 )
        goto LABEL_21;
      LODWORD(v146) = v13;
      LODWORD(v145) = 327;
      goto LABEL_24;
    }
    v62 = (void *)*((_QWORD *)v9 + 6);
    LODWORD(v147[0]) = 0;
    if ( v62 && (v63 = CGlobalHelpersT<CEmptyType>::GetStringCchLength<unsigned long>(v62, v147), v13 = v63, v63 < 0)
      || (v63 = CImmutableStringsT<wchar_t,CImmutableStringsPolicyDefault>::CreateInternal(v62), v13 = v63, v63 < 0) )
    {
      CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure((unsigned int)v63);
    }
    CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent((unsigned int)v13);
    if ( v13 < 0 )
    {
      v19 = *((_QWORD *)this + 75);
      if ( !v19 )
        goto LABEL_21;
      LODWORD(v146) = v13;
      LODWORD(v145) = 328;
      goto LABEL_24;
    }
    if ( a5 )
    {
      LODWORD(v147[0]) = 0;
      v64 = CGlobalHelpersT<CEmptyType>::GetStringCchLength<unsigned long>(a5, v147);
      v13 = v64;
      if ( v64 < 0
        || (v64 = CImmutableStringsT<wchar_t,CImmutableStringsPolicyDefault>::CreateInternal(a5), v13 = v64, v64 < 0) )
      {
        CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure((unsigned int)v64);
      }
      CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent((unsigned int)v13);
      if ( v13 < 0 )
      {
        v19 = *((_QWORD *)this + 75);
        if ( !v19 )
          goto LABEL_21;
        LODWORD(v146) = v13;
        LODWORD(v145) = 332;
        goto LABEL_24;
      }
    }
    v65 = (wchar_t *)Src;
    if ( *((_QWORD *)v9 + 6) )
      v65 = (wchar_t *)*((_QWORD *)v9 + 6);
    v151 = v65;
    *((_DWORD *)this + 146) = *((_QWORD *)v9 + 6) != 0;
    v66 = *((_QWORD *)this + 75);
    if ( v66 )
      CMoUpdateLogT<CEmptyType>::MoUpdateLogFormat(v66, 2, L"CDeploymentSession: Initializing WorkingDir = [%s]", v65);
    LODWORD(v147[0]) = 0;
    if ( v65 && (v67 = CGlobalHelpersT<CEmptyType>::GetStringCchLength<unsigned long>(v65, v147), v13 = v67, v67 < 0) )
    {
      CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure((unsigned int)v67);
      v68 = (_QWORD *)((char *)this + 488);
    }
    else
    {
      v68 = (_QWORD *)((char *)this + 488);
      *(_QWORD *)v154 = (char *)this + 488;
      v69 = CImmutableStringsT<wchar_t,CImmutableStringsPolicyDefault>::CreateInternal(v65);
      v13 = v69;
      if ( v69 < 0 )
      {
        CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure((unsigned int)v69);
LABEL_146:
        CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent((unsigned int)v13);
        if ( v13 < 0 )
        {
          v19 = *((_QWORD *)this + 75);
          if ( !v19 )
            goto LABEL_21;
          LODWORD(v146) = v13;
          LODWORD(v145) = 347;
          goto LABEL_24;
        }
        v70 = (LPCWSTR *)((char *)this + 504);
        v71 = CMiscHelpersT<CEmptyType>::CombinePath(*v68, L"ActionList.xml", 0, (char *)this + 504);
        v13 = v71;
        if ( v71 < 0 )
        {
          v19 = *((_QWORD *)this + 75);
          if ( !v19 )
            goto LABEL_21;
          LODWORD(v146) = v71;
          LODWORD(v145) = 348;
          goto LABEL_24;
        }
        v72 = CMiscHelpersT<CEmptyType>::CombinePath(*v68, L"DownloadList.xml", 0, (char *)this + 528);
        v13 = v72;
        if ( v72 < 0 )
        {
          v19 = *((_QWORD *)this + 75);
          if ( !v19 )
            goto LABEL_21;
          LODWORD(v146) = v72;
          LODWORD(v145) = 349;
          goto LABEL_24;
        }
        v73 = CMiscHelpersT<CEmptyType>::CombinePath(*v68, L"metadata", 0, (char *)this + 496);
        v13 = v73;
        if ( v73 < 0 )
        {
          v19 = *((_QWORD *)this + 75);
          if ( !v19 )
            goto LABEL_21;
          LODWORD(v146) = v73;
          LODWORD(v145) = 350;
          goto LABEL_24;
        }
        v74 = CExclusiveAcquireLock::Init((CDeploymentSession *)((char *)this + 152));
        v75 = v74;
        if ( v74 >= 0 )
          *((_DWORD *)this + 34) = 0;
        else
          CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure((unsigned int)v74);
        CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent((unsigned int)v75);
        if ( v75 < 0 )
          wil::details::in1diag3::Throw_Hr(
            retaddr,
            (void *)0x2BE6,
            (unsigned int)"onecore\\base\\ntsetup\\conx\\mosetup\\updateagent\\src\\DeploymentSessionImpl.h",
            (const char *)(unsigned int)v75,
            (int)v145);
        v76 = (_QWORD *)std::to_wstring(v168, 0);
        if ( v76[3] <= 7u )
          v77 = v76;
        else
          v77 = (_QWORD *)*v76;
        v148[0] = v77;
        v148[1] = v76[2];
        CWatsonHelper::SetParameter(2, v148);
        std::wstring::~wstring(v168);
        DlpManagerCore = CreateDlpManagerCore(
                           (_DWORD)v65,
                           2,
                           v78,
                           *((_QWORD *)this + 75),
                           (__int64)v145,
                           (__int64)&v150);
        v81 = *((_QWORD *)this + 75);
        if ( DlpManagerCore < 0 )
        {
          if ( v81 )
            CMoUpdateLogT<CEmptyType>::MoUpdateLogFormat(v81, 2, L"Existing session state not found.");
          v14 = v150;
          goto LABEL_249;
        }
        if ( v81 )
          CMoUpdateLogT<CEmptyType>::MoUpdateLogFormat(v81, 2, L"Found existing session state. Checking its state.");
        v14 = v150;
        v82 = (**((__int64 (__fastcall ***)(char *, const wchar_t *, unsigned int *))v150 + 1))(
                (char *)v150 + 8,
                L"State",
                &v182);
        v83 = *((_QWORD *)this + 75);
        if ( v82 < 0 )
        {
          if ( v83 )
            CMoUpdateLogT<CEmptyType>::MoUpdateLogFormat(
              v83,
              2,
              L"Session state is corrupt. Error: [0x%X]",
              (unsigned int)v82);
          goto LABEL_249;
        }
        if ( v83 )
          CMoUpdateLogT<CEmptyType>::MoUpdateLogFormat(v83, 2, L"Found State = [%lu].", v182);
        if ( v182 - 3 > 5 && v182 - 12 > 1 )
        {
          v84 = *((_QWORD *)this + 75);
          if ( v84 )
            CMoUpdateLogT<CEmptyType>::MoUpdateLogFormat(v84, 2, L"Preserving critical state data...");
          v85 = CDeploymentSession::PreserveExpressFileCount(this, v14);
          v13 = v85;
          v86 = *((_QWORD *)this + 75);
          if ( v85 < 0 )
          {
            if ( !v86 )
              goto LABEL_29;
            LODWORD(v146) = v85;
            LODWORD(v145) = 381;
            goto LABEL_180;
          }
          if ( v86 )
            CMoUpdateLogT<CEmptyType>::MoUpdateLogFormat(
              v86,
              2,
              L"Resume is NOT supported from this state. Ignoring session state file.");
          *((_DWORD *)this + 66) = 1;
          v87 = GetFileAttributesW(*v70);
          v88 = v87 != -1 && (v87 & 0x10) == 0;
          CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(0);
          CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(0);
          if ( v88 )
          {
            v89 = *((_QWORD *)this + 75);
            if ( v89 )
              CMoUpdateLogT<CEmptyType>::MoUpdateLogFormat(v89, 2, L"Deleting previous ActionList file.");
            if ( !DeleteFileW(*v70) )
            {
              v90 = GetLastError();
              v13 = v90;
              if ( v90 )
              {
                if ( v90 > 0 )
                  v13 = (unsigned __int16)v90 | 0x80070000;
              }
              else
              {
                v13 = -2147467259;
              }
              v91 = *((_QWORD *)this + 75);
              v24 = 0;
              if ( v13 >= 0 || !v91 )
                goto LABEL_33;
              LODWORD(v146) = v13;
              LODWORD(v145) = 393;
              goto LABEL_197;
            }
          }
          if ( v14 )
          {
            v92 = v14;
            v93 = *((_QWORD *)this + 75);
            if ( v93 )
              CMoUpdateLogT<CEmptyType>::MoUpdateLogFormat(v93, 2, L"Resetting existing session state.");
            v14 = 0;
            v148[0] = 0;
            v150 = 0;
            v94 = *((_QWORD *)this + 76);
            if ( v94 )
              (*(void (__fastcall **)(__int64))(*(_QWORD *)v94 + 16LL))(v94);
            *((_QWORD *)this + 76) = v92;
            v95 = CDeploymentSession::ResetState(this, 1, 0);
            v13 = v95;
            if ( v95 < 0 )
            {
              v86 = *((_QWORD *)this + 75);
              if ( !v86 )
                goto LABEL_29;
              LODWORD(v146) = v95;
              LODWORD(v145) = 458;
              goto LABEL_180;
            }
            goto LABEL_261;
          }
LABEL_249:
          v115 = *((_QWORD *)this + 75);
          if ( v115 )
            CMoUpdateLogT<CEmptyType>::MoUpdateLogFormat(v115, 2, L"Creating new session state.");
          if ( v14 )
          {
            (*(void (__fastcall **)(struct IDlpManager *))(*(_QWORD *)v14 + 16LL))(v14);
            v150 = 0;
          }
          v116 = CreateDlpManagerCore((_DWORD)v65, 1, v80, *((_QWORD *)this + 75), (__int64)v145, (__int64)&v150);
          v13 = v116;
          if ( v116 < 0 )
          {
            v117 = *((_QWORD *)this + 75);
            if ( v117 )
            {
              LODWORD(v146) = v116;
              LODWORD(v145) = 464;
              v118 = CMoUpdateLogT<CEmptyType>::MoUpdateLogFormat(
                       v117,
                       4,
                       L"%s(%d): Result = 0x%X",
                       L"CDeploymentSession::InitializeImpl",
                       v145,
                       v146,
                       v147[0]);
              v117 = (unsigned int)v118;
              if ( v118 < 0 )
                CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure((unsigned int)v118);
            }
            CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(v117);
            v14 = v150;
            goto LABEL_9;
          }
          v119 = v150;
          v14 = 0;
          v148[0] = 0;
          v150 = 0;
          v120 = *((_QWORD *)this + 76);
          if ( v120 )
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v120 + 16LL))(v120);
          *((_QWORD *)this + 76) = v119;
LABEL_261:
          v121 = UuidCreate(&Uuid);
          if ( v121 )
          {
            v144 = I_RpcMapWin32Status(v121);
            if ( v144 > 0 )
              v144 = (unsigned __int16)v144 | 0x80070000;
            if ( v144 >= 0 )
              v144 = -2147467259;
            v13 = v144;
            v91 = *((_QWORD *)this + 75);
            v24 = 0;
            if ( !v91 )
              goto LABEL_33;
            LODWORD(v146) = v13;
            LODWORD(v145) = 470;
LABEL_197:
            v86 = v91;
LABEL_180:
            v24 = (unsigned int)CMoUpdateLogT<CEmptyType>::MoUpdateLogFormat(
                                  v86,
                                  4,
                                  L"%s(%d): Result = 0x%X",
                                  L"CDeploymentSession::InitializeImpl",
                                  v145,
                                  v146,
                                  v147[0]);
            goto LABEL_31;
          }
          v122 = CDlpHelpersT<CEmptyType>::GuidToSString(&Uuid, 0, (char *)this + 48);
          v13 = v122;
          v86 = *((_QWORD *)this + 75);
          if ( v122 < 0 )
          {
            if ( !v86 )
              goto LABEL_29;
            LODWORD(v146) = v122;
            LODWORD(v145) = 471;
            goto LABEL_180;
          }
          if ( v86 )
            CMoUpdateLogT<CEmptyType>::MoUpdateLogFormat(v86, 2, L"Session ID [%s]", *((_QWORD *)this + 6));
          if ( *(_QWORD *)v152 )
          {
            v123 = STRAPI_Create(*(const wchar_t **)v152, (wchar_t **)this + 7);
            v13 = v123;
            if ( v123 < 0 )
            {
              v86 = *((_QWORD *)this + 75);
              if ( !v86 )
                goto LABEL_29;
              LODWORD(v146) = v123;
              LODWORD(v145) = 478;
              goto LABEL_180;
            }
          }
          v101 = 0;
          v124 = CDeploymentSession::StateSet(this, 2);
          v13 = v124;
          if ( v124 < 0 )
          {
            v86 = *((_QWORD *)this + 75);
            if ( !v86 )
              goto LABEL_29;
            LODWORD(v146) = v124;
            LODWORD(v145) = 481;
            goto LABEL_180;
          }
LABEL_237:
          v109 = &String2;
          if ( *((_QWORD *)this + 7) )
          {
            IsEnabled = wil::details::FeatureImpl<__WilFeatureTraits_Feature_UpdateAgentWUSARebaseMultiMSU>::__private_IsEnabled(&`wil::Feature<__WilFeatureTraits_Feature_UpdateAgentWUSARebaseMultiMSU>::GetImpl'::`2'::impl);
            v111 = *((_QWORD *)this + 7);
            if ( IsEnabled )
              v112 = CreateSessionData(&v151, v111, (unsigned __int64 *)v65);
            else
              v112 = CreateSessionData(&v151, v111, 0);
            v153 = (void (__fastcall ***)(_QWORD))*v112;
            v113 = v153;
            *v112 = 0;
            v157 = v113;
            if ( v151 )
              (**(void (__fastcall ***)(const wchar_t *))v151)(v151);
            v125 = *((_QWORD *)this + 75);
            if ( v125 )
              CMoUpdateLogT<CEmptyType>::MoUpdateLogFormat(
                v125,
                2,
                L"SessionData: ModuleID           [%d]",
                *((unsigned int *)v113 + 2));
            v126 = *((_QWORD *)this + 75);
            if ( v126 )
            {
              v127 = &String2;
              if ( v113[2] )
                v127 = (const WCHAR *)v113[2];
              CMoUpdateLogT<CEmptyType>::MoUpdateLogFormat(v126, 2, L"SessionData: PackageFileList    [%s]", v127);
            }
            v128 = *((_QWORD *)this + 75);
            if ( v128 )
            {
              v129 = &String2;
              if ( v113[5] )
                v129 = (const WCHAR *)v113[5];
              CMoUpdateLogT<CEmptyType>::MoUpdateLogFormat(v128, 2, L"SessionData: MediaVersion       [%s]", v129);
            }
            v130 = *((_QWORD *)this + 75);
            if ( v130 )
            {
              if ( v113[6] )
                v109 = (const WCHAR *)v113[6];
              CMoUpdateLogT<CEmptyType>::MoUpdateLogFormat(v130, 2, L"SessionData: MediaBranch        [%s]", v109);
            }
            v131 = *((_QWORD *)this + 75);
            if ( v131 )
              CMoUpdateLogT<CEmptyType>::MoUpdateLogFormat(
                v131,
                2,
                L"SessionData: Feature Count      [%lu]",
                *((unsigned int *)v113 + 8));
            for ( i = 0; (unsigned int)i < *((_DWORD *)v113 + 8); i = (unsigned int)(i + 1) )
            {
              v133 = *((_QWORD *)this + 75);
              if ( v133 )
                CMoUpdateLogT<CEmptyType>::MoUpdateLogFormat(
                  v133,
                  2,
                  L"SessionData: Feature [%lu], Name [%s], Language [%s]",
                  (unsigned int)i,
                  v113[3][3 * i],
                  v113[3][3 * i + 1]);
            }
          }
          else
          {
            v113 = v153;
          }
          if ( !v101 )
          {
            IsHostOSMobile = CMoUpdateHelpersT<CEmptyType>::IsHostOSMobile(&v149, *((_QWORD *)this + 70));
            v13 = IsHostOSMobile;
            if ( IsHostOSMobile < 0 )
            {
              v135 = 516;
              goto LABEL_302;
            }
            if ( v149 )
            {
              if ( !v113 )
              {
LABEL_310:
                v101 = 1;
                goto LABEL_350;
              }
              if ( *((_DWORD *)v113 + 2) == 18 )
              {
LABEL_307:
                v101 = 2;
                goto LABEL_350;
              }
              if ( *((_DWORD *)v113 + 2) == 19 )
              {
                *((_DWORD *)this + 81) = 1;
                goto LABEL_310;
              }
              v135 = 532;
LABEL_312:
              v13 = -2147418113;
              v136 = 2147549183LL;
              goto LABEL_303;
            }
            if ( v113 )
            {
              v137 = *((_DWORD *)v113 + 2);
              switch ( v137 )
              {
                case 3:
                  v101 = 6;
                  break;
                case 2:
                  v101 = 5;
                  break;
                case 18:
                  goto LABEL_307;
                case 4:
                  v101 = 8;
                  break;
                case 5:
                  v101 = 9;
                  break;
                case 6:
                  v101 = 10;
                  break;
                case 8:
                  v101 = 11;
                  break;
                case 7:
                  v101 = 12;
                  break;
                case 9:
                  v101 = 13;
                  break;
                case 10:
                  v101 = 14;
                  break;
                case 11:
                  v101 = 15;
                  break;
                case 12:
                  v101 = 16;
                  break;
                case 13:
                  v101 = 17;
                  break;
                case 14:
                  v101 = 18;
                  break;
                case 16:
                  v101 = 22;
                  break;
                default:
                  v101 = 20;
                  if ( v137 != 15 )
                  {
                    if ( v137 == 20 )
                    {
                      v101 = 24;
                    }
                    else
                    {
                      if ( v137 != 21 )
                      {
                        v135 = 618;
                        goto LABEL_312;
                      }
                      v101 = 3;
                    }
                  }
                  break;
              }
            }
            else
            {
              v101 = 0;
            }
          }
LABEL_350:
          *((_DWORD *)this + 114) = v101;
          v153 = 0;
          v157 = 0;
          v138 = (void (__fastcall ***)(_QWORD))*((_QWORD *)this + 59);
          if ( v138 )
            (**v138)(v138);
          *((_QWORD *)this + 59) = v113;
          SH_SSTRING::operator=((char *)this + 64);
          SH_SSTRING::operator=((char *)this + 72);
          SH_SSTRING::operator=((char *)this + 80);
          SH_SSTRING::operator=((char *)this + 88);
          *((struct _GUID *)this + 2) = *v160;
          *((_DWORD *)this + 186) = 0;
          if ( *((_DWORD *)this + 114) == 9
            && (IsHostOSMobile = STRAPI_Create(
                                   *(const wchar_t **)(*((_QWORD *)this + 59) + 16LL),
                                   (wchar_t **)this + 64),
                v13 = IsHostOSMobile,
                IsHostOSMobile < 0) )
          {
            v135 = 643;
          }
          else if ( (unsigned int)(*((_DWORD *)this + 114) - 13) <= 1
                 && *((_QWORD *)this + 76)
                 && (IsHostOSMobile = CDeploymentSession::ResetState(this, 0, 1),
                     v13 = IsHostOSMobile,
                     IsHostOSMobile < 0) )
          {
            v135 = 650;
          }
          else if ( *v162
                 && (IsHostOSMobile = STRAPI_Create(*v162, (wchar_t **)this + 8),
                     v13 = IsHostOSMobile,
                     IsHostOSMobile < 0) )
          {
            v135 = 656;
          }
          else if ( *v163
                 && (IsHostOSMobile = STRAPI_Create(*v163, (wchar_t **)this + 9),
                     v13 = IsHostOSMobile,
                     IsHostOSMobile < 0) )
          {
            v135 = 661;
          }
          else if ( *v164
                 && (IsHostOSMobile = STRAPI_Create(*v164, (wchar_t **)this + 10),
                     v13 = IsHostOSMobile,
                     IsHostOSMobile < 0) )
          {
            v135 = 666;
          }
          else
          {
            if ( !*v165
              || (IsHostOSMobile = STRAPI_Create(*v165, (wchar_t **)this + 11), v13 = IsHostOSMobile,
                                                                                IsHostOSMobile >= 0) )
            {
              *((_DWORD *)this + 93) = *(_DWORD *)v161[0];
              v139 = v152;
              *((_OWORD *)this + 44) = *(_OWORD *)((char *)v152 + 68);
              *((_OWORD *)this + 45) = *(_OWORD *)((char *)v139 + 84);
              *((_DWORD *)this + 184) = *((_DWORD *)v139 + 25);
              *((_DWORD *)this + 185) = *v156;
              if ( !*((_DWORD *)this + 65) )
              {
                IsHostOSMobile = CDeploymentSession::ExpandCompDBs(this);
                v13 = IsHostOSMobile;
                if ( IsHostOSMobile < 0 )
                {
                  v135 = 684;
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
              v13 = IsHostOSMobile;
              if ( IsHostOSMobile >= 0 )
              {
                OneSettings = CDeploymentSession::GetOneSettings(this);
                if ( OneSettings < 0 )
                {
                  v141 = *((_QWORD *)this + 75);
                  if ( v141 )
                    CMoUpdateLogT<CEmptyType>::MoUpdateLogFormat(
                      v141,
                      3,
                      L"Error getting OneSettings: [0x%X]",
                      (unsigned int)OneSettings);
                }
                if ( *((_DWORD *)this + 114)
                  && (IsHostOSMobile = CDeploymentSession::CreateScenarioCtrl(this),
                      v13 = IsHostOSMobile,
                      IsHostOSMobile < 0) )
                {
                  v135 = 704;
                }
                else
                {
                  v172 = *((_DWORD *)this + 114);
                  v175 = *((_QWORD *)this + 7);
                  v173 = **(_QWORD **)v154;
                  v174 = *((_QWORD *)this + 62);
                  v181 = *((_QWORD *)this + 75);
                  v177 = *((_QWORD *)this + 8);
                  v178 = *((_QWORD *)this + 10);
                  v176 = *((_QWORD *)this + 9);
                  v179 = v184;
                  v180 = v183;
                  v156 = operator new(0x60u);
                  v161[0] = xmmword_1803ACAA0;
                  v161[1] = (__int64)(*((_QWORD *)&xmmword_1803ACAA0 + 1) - xmmword_1803ACAA0) >> 6;
                  v142 = DeploymentPluginManager::DeploymentPluginManager(v156, &v172, v161);
                  v156 = 0;
                  v143 = *((_QWORD *)this + 81);
                  *((_QWORD *)this + 81) = v142;
                  if ( v143 )
                    std::default_delete<DeploymentPluginManager>::operator()();
                  std::unique_ptr<DeploymentPluginManager>::~unique_ptr<DeploymentPluginManager>(&v156);
                  IsHostOSMobile = CDeploymentSession::Serialize((CDeploymentSession *)((char *)this + 24));
                  v13 = IsHostOSMobile;
                  if ( IsHostOSMobile >= 0 )
                    goto LABEL_8;
                  v135 = 722;
                }
              }
              else
              {
                v135 = 689;
              }
              goto LABEL_302;
            }
            v135 = 671;
          }
LABEL_302:
          v136 = (unsigned int)IsHostOSMobile;
LABEL_303:
          CMoUpdateLogT<CEmptyType>::MoUpdateLogError(
            *((_QWORD *)this + 75),
            v136,
            L"CDeploymentSession::InitializeImpl",
            v135);
          goto LABEL_8;
        }
        v96 = *((_QWORD *)this + 75);
        if ( v96 )
          CMoUpdateLogT<CEmptyType>::MoUpdateLogFormat(v96, 2, L"Resume is supported from this state.");
        if ( !v14 )
          goto LABEL_249;
        v97 = v14;
        v98 = *((_QWORD *)this + 75);
        if ( v98 )
          CMoUpdateLogT<CEmptyType>::MoUpdateLogFormat(v98, 2, L"Loading existing session state.");
        v14 = 0;
        v148[0] = 0;
        v150 = 0;
        v99 = *((_QWORD *)this + 76);
        if ( v99 )
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v99 + 16LL))(v99);
        *((_QWORD *)this + 76) = v97;
        v100 = CDeploymentSession::Deserialize(this);
        v13 = v100;
        if ( v100 < 0 )
        {
          v86 = *((_QWORD *)this + 75);
          if ( !v86 )
            goto LABEL_29;
          LODWORD(v146) = v100;
          LODWORD(v145) = 414;
          goto LABEL_180;
        }
        v101 = *((_DWORD *)this + 114);
        v102 = v152;
        v103 = (const WCHAR **)((char *)this + 56);
        if ( *(_QWORD *)v152 )
        {
          if ( !*v103 )
          {
LABEL_221:
            v105 = *((_QWORD *)this + 75);
            if ( v105 )
            {
              v106 = &String2;
              if ( *v103 )
                v106 = *v103;
              HIDWORD(v145) = HIDWORD(v106);
              CMoUpdateLogT<CEmptyType>::MoUpdateLogFormat(
                v105,
                4,
                L"SessionData mismatch. New value = [%s]. Stored value = [%s]");
            }
            v11 = *((_QWORD *)this + 75);
            if ( (*((_BYTE *)v102 + 64) & 0x10) == 0 )
            {
              if ( v11 )
              {
                LODWORD(v146) = -2147418113;
                LODWORD(v145) = 447;
                v114 = CMoUpdateLogT<CEmptyType>::MoUpdateLogFormat(
                         v11,
                         4,
                         L"%s(%d): Result = 0x%X",
                         L"CDeploymentSession::InitializeImpl",
                         v145,
                         v146,
                         v147[0]);
                v11 = (unsigned int)v114;
                if ( v114 < 0 )
                  CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure((unsigned int)v114);
              }
              v13 = -2147418113;
              goto LABEL_7;
            }
            if ( v11 )
              CMoUpdateLogT<CEmptyType>::MoUpdateLogFormat(
                v11,
                2,
                L"Ignoring because flag is set to ignore session data.");
            v107 = *(void **)v102;
            if ( *(_QWORD *)v102 )
            {
              LODWORD(v147[0]) = 0;
              v108 = CGlobalHelpersT<CEmptyType>::GetStringCchLength<unsigned long>(v107, v147);
              v13 = v108;
              if ( v108 < 0
                || (v108 = CImmutableStringsT<wchar_t,CImmutableStringsPolicyDefault>::CreateInternal(v107),
                    v13 = v108,
                    v108 < 0) )
              {
                CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure((unsigned int)v108);
              }
              CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent((unsigned int)v13);
              if ( v13 < 0 )
              {
                v19 = *((_QWORD *)this + 75);
                if ( !v19 )
                  goto LABEL_21;
                LODWORD(v146) = v13;
                LODWORD(v145) = 441;
                goto LABEL_24;
              }
              *((_DWORD *)this + 68) = 0;
            }
            v65 = (wchar_t *)v151;
            goto LABEL_237;
          }
          v104 = (unsigned int)_o__wcsicmp(*(_QWORD *)v152, *v103) == 0;
        }
        else
        {
          v104 = *v103 == 0;
        }
        if ( v104 )
          goto LABEL_237;
        goto LABEL_221;
      }
    }
    *(_QWORD *)v154 = v68;
    goto LABEL_146;
  }
  catch ( ... )
  {
    return (unsigned int)wil::details::in1diag3::Return_CaughtException(
                           retaddr,
                           (void *)0x2D6,
                           (unsigned int)"onecore\\base\\ntsetup\\conx\\mosetup\\updateagent\\src\\DeploymentSessionImpl.h",
                           v15);
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
