# CFilterProcessBase::Init(_SECURITY_ATTRIBUTES *,wchar_t const *,wchar_t const *,ulong,CFilterPool *)

- ea: `0x18002538c`
- end: `0x18002677f`
- name: `?Init@CFilterProcessBase@@QEAAJPEAU_SECURITY_ATTRIBUTES@@PEB_W1KPEAVCFilterPool@@@Z`
- size: `5107`
- prototype: `__int64 __fastcall(CFilterProcessBase *this, struct _SECURITY_ATTRIBUTES *, const wchar_t *, wchar_t *, int Value, struct CFilterPool *)`
- caller_count: `1`
- callee_count: `48`
- tags: `file_ops, authz_impersonation, registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x18004a638`

## callees

- `0x18000e628`
- `0x18000ee18`
- `0x18000f880`
- `0x180012318`
- `0x18001d5b0`
- `0x180022688`
- `0x1800252e4`
- `0x18002538c`
- `0x1800269b0`
- `0x180026a18`
- `0x180026b58`
- `0x18002751c`
- `0x180029db0`
- `0x180049b00`
- `0x180054794`
- `0x180056610`
- `0x18005cbf4`
- `0x18006028c`
- `0x180067220`
- `0x18006a040`
- `0x18006a618`
- `0x18008a144`
- `0x1800904ec`
- `0x180098ebc`
- `0x18009d368`
- `0x1800a8b90`
- `0x1800a92b8`
- `0x1800ad384`
- `0x1800b6f54`
- `0x1800b9778`
- `0x1800baffc`
- `0x1800bc430`
- `0x1800bd2f0`
- `0x1800bd7f8`
- `0x1800be1c8`
- `0x1800bed60`
- `0x1800cae14`
- `0x1800e2374`
- `0x1800e95f0`
- `0x1800eaf44`
- `0x1800fb1e4`
- `0x1801244c0`
- `0x1801249b0`
- `0x18012540e`
- `0x18013dd98`
- `0x18019defc`
- `0x18019dfc4`
- `0x180241010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__itow` at `0x1800256c1`
- `api-ms-win-crt-private-l1-1-0!_o__itow` at `0x18002597e`
- `api-ms-win-crt-private-l1-1-0!_o__itow` at `0x1800256c1`
- `api-ms-win-crt-private-l1-1-0!_o__itow` at `0x18002597e`
- `api-ms-win-crt-private-l1-1-0!_o__i64tow_s` at `0x1800259d5`
- `api-ms-win-crt-private-l1-1-0!_o__i64tow_s` at `0x1800259d5`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180025477`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18002551b`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180025477`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18002551b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800254a6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002607e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800266d1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800254a6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002607e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800266d1`
- `api-ms-win-core-processthreads-l1-1-0!DeleteProcThreadAttributeList` at `0x180026685`
- `api-ms-win-core-processthreads-l1-1-0!DeleteProcThreadAttributeList` at `0x180026685`
- `api-ms-win-core-processthreads-l1-1-0!ResumeThread` at `0x18002633a`
- `api-ms-win-core-processthreads-l1-1-0!ResumeThread` at `0x18002633a`
- `api-ms-win-core-processthreads-l1-1-0!CreateProcessAsUserW` at `0x1800261cf`
- `api-ms-win-core-processthreads-l1-1-0!CreateProcessAsUserW` at `0x1800261cf`
- `api-ms-win-core-processthreads-l1-1-0!CreateProcessW` at `0x180026068`
- `api-ms-win-core-processthreads-l1-1-0!CreateProcessW` at `0x180026068`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x1800263a4`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x1800263ad`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18002640b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18002648e`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x1800264e4`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x1800263a4`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x1800263ad`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18002640b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18002648e`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x1800264e4`
- `api-ms-win-core-handle-l1-1-0!DuplicateHandle` at `0x1800263d6`
- `api-ms-win-core-handle-l1-1-0!DuplicateHandle` at `0x180026431`
- `api-ms-win-core-handle-l1-1-0!DuplicateHandle` at `0x1800264b7`
- `api-ms-win-core-handle-l1-1-0!DuplicateHandle` at `0x18002650d`
- `api-ms-win-core-handle-l1-1-0!DuplicateHandle` at `0x1800263d6`
- `api-ms-win-core-handle-l1-1-0!DuplicateHandle` at `0x180026431`
- `api-ms-win-core-handle-l1-1-0!DuplicateHandle` at `0x1800264b7`
- `api-ms-win-core-handle-l1-1-0!DuplicateHandle` at `0x18002650d`
- `api-ms-win-core-synch-l1-2-0!InitOnceExecuteOnce` at `0x180026159`
- `api-ms-win-core-synch-l1-2-0!InitOnceExecuteOnce` at `0x180026159`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x180025eb3`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x180025eb3`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x180025fe3`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x180025fe3`
- `api-ms-win-appmodel-runtime-l1-1-1!ParseApplicationUserModelId` at `0x180025f3a`
- `api-ms-win-appmodel-runtime-l1-1-1!ParseApplicationUserModelId` at `0x180025f3a`
- `USERENV!DestroyEnvironmentBlock` at `0x1800261e5`
- `USERENV!DestroyEnvironmentBlock` at `0x1800266cb`
- `USERENV!DestroyEnvironmentBlock` at `0x1800261e5`
- `USERENV!DestroyEnvironmentBlock` at `0x1800266cb`
- `USERENV!CreateEnvironmentBlock` at `0x18002612a`
- `USERENV!CreateEnvironmentBlock` at `0x18002612a`

## string_xrefs

- `0x180025b0b`: `DefaultUserAgent`
- `0x180025802`: `SearchProtocolHost.exe`
- `0x1800255a7`: `Container\AgentGathererPipe\`

## pseudocode

```c
__int64 __fastcall CFilterProcessBase::Init(
        CFilterProcessBase *this,
        struct _SECURITY_ATTRIBUTES *a2,
        const wchar_t *a3,
        wchar_t *a4,
        int Value,
        struct CFilterPool *a6)
{
  const wchar_t *v7; // r13
  unsigned int v10; // r15d
  struct IUnknownVtbl **v11; // rsi
  HANDLE EventW; // rax
  const char *v13; // r9
  HANDLE v14; // rax
  const char *v15; // r9
  int v16; // eax
  int v17; // ecx
  int v18; // eax
  int Instance; // eax
  wchar_t *v20; // rax
  struct IUnknown *v21; // rbx
  int v22; // eax
  unsigned int v23; // eax
  int v24; // eax
  wchar_t *v25; // r15
  int v26; // eax
  const wchar_t *v27; // rdx
  int ProcessParam; // eax
  unsigned int v29; // ebx
  __int64 v31; // rcx
  __int64 UserAgent; // rax
  int v33; // edi
  const wchar_t *v34; // rdx
  __int64 v35; // r13
  _QWORD *v36; // rdx
  void *v37; // rdi
  _QWORD *v38; // rax
  const char *v39; // r9
  const WCHAR *v40; // rcx
  unsigned int v41; // eax
  unsigned int v42; // r8d
  unsigned int v43; // r9d
  const unsigned __int16 *v44; // rax
  unsigned int v45; // eax
  const char *v46; // r9
  const char *v47; // r9
  BOOL EnvironmentBlock; // esi
  DWORD v49; // ebx
  SecUtil **v50; // rsi
  int v51; // ecx
  void *v52; // rdx
  int v53; // eax
  int JobManagerInstance; // eax
  wchar_t *v55; // rdi
  __int64 (__fastcall *v56)(wchar_t *, _QWORD); // rbx
  unsigned int MaxCPURateForFilterProcesses; // eax
  int v58; // eax
  const char *v59; // r9
  int v60; // eax
  SecUtil *v61; // rdi
  HANDLE CurrentProcess; // rbx
  HANDLE v63; // rax
  const char *v64; // r9
  SecUtil *v65; // rbx
  void *v66; // rdi
  HANDLE v67; // rax
  const char *v68; // r9
  HANDLE v69; // r8
  __int64 v70; // rcx
  void *v71; // rdi
  SecUtil *v72; // rbx
  HANDLE v73; // rax
  const char *v74; // r9
  SecUtil *v75; // rbx
  void *v76; // rdi
  HANDLE v77; // rax
  const char *v78; // r9
  int v79; // eax
  CFilterProcessBase *v80; // rbx
  CFilterPipeBase *v81; // rcx
  int v82; // eax
  const char *v83; // r9
  unsigned int packageRelativeApplicationId; // [rsp+20h] [rbp-EB8h]
  const unsigned __int16 *packageRelativeApplicationIda; // [rsp+20h] [rbp-EB8h]
  int packageRelativeApplicationIdc; // [rsp+20h] [rbp-EB8h]
  int packageRelativeApplicationIdb; // [rsp+20h] [rbp-EB8h]
  int packageRelativeApplicationIdd; // [rsp+20h] [rbp-EB8h]
  LPSTARTUPINFOW lpStartupInfo; // [rsp+40h] [rbp-E98h]
  unsigned int lpProcessInformation; // [rsp+48h] [rbp-E90h]
  LPPROCESS_INFORMATION v91; // [rsp+50h] [rbp-E88h]
  unsigned __int64 v92; // [rsp+58h] [rbp-E80h]
  unsigned __int64 *v93; // [rsp+60h] [rbp-E78h]
  struct _GUID *v94; // [rsp+68h] [rbp-E70h]
  unsigned __int64 v95; // [rsp+70h] [rbp-E68h]
  int v96; // [rsp+80h] [rbp-E58h] BYREF
  LPVOID Environment[2]; // [rsp+88h] [rbp-E50h] BYREF
  UINT32 packageFamilyNameLength[2]; // [rsp+98h] [rbp-E40h] BYREF
  __int16 v99; // [rsp+A0h] [rbp-E38h]
  UINT32 packageRelativeApplicationIdLength[2]; // [rsp+A8h] [rbp-E30h] BYREF
  HANDLE v101; // [rsp+B0h] [rbp-E28h] BYREF
  HANDLE TargetHandle; // [rsp+B8h] [rbp-E20h] BYREF
  wchar_t *v103[2]; // [rsp+C0h] [rbp-E18h]
  struct _PROCESS_INFORMATION ProcessInformation; // [rsp+D0h] [rbp-E08h] BYREF
  HANDLE v105; // [rsp+E8h] [rbp-DF0h] BYREF
  struct _SECURITY_ATTRIBUTES EventAttributes; // [rsp+F0h] [rbp-DE8h] BYREF
  struct _STARTUPINFOW StartupInfo; // [rsp+110h] [rbp-DC8h] BYREF
  LPPROC_THREAD_ATTRIBUTE_LIST lpAttributeList; // [rsp+178h] [rbp-D60h]
  _QWORD v109[2]; // [rsp+180h] [rbp-D58h] BYREF
  unsigned int v110; // [rsp+194h] [rbp-D44h]
  const int *v111; // [rsp+220h] [rbp-CB8h] BYREF
  LPWSTR lpCommandLine; // [rsp+228h] [rbp-CB0h]
  int v113; // [rsp+230h] [rbp-CA8h]
  unsigned int v114; // [rsp+234h] [rbp-CA4h]
  int v115; // [rsp+238h] [rbp-CA0h] BYREF
  void **v116; // [rsp+2C0h] [rbp-C18h] BYREF
  char *v117; // [rsp+2C8h] [rbp-C10h]
  int v118; // [rsp+2D0h] [rbp-C08h]
  int v119; // [rsp+2D4h] [rbp-C04h]
  char v120; // [rsp+2D8h] [rbp-C00h] BYREF
  void **v121; // [rsp+320h] [rbp-BB8h] BYREF
  wchar_t *v122; // [rsp+328h] [rbp-BB0h]
  int v123; // [rsp+330h] [rbp-BA8h]
  unsigned int v124; // [rsp+334h] [rbp-BA4h]
  char v125; // [rsp+338h] [rbp-BA0h] BYREF
  _QWORD v126[2]; // [rsp+3C0h] [rbp-B18h] BYREF
  unsigned int v127; // [rsp+3D4h] [rbp-B04h]
  _BYTE v128[8]; // [rsp+420h] [rbp-AB8h] BYREF
  wchar_t *v129; // [rsp+428h] [rbp-AB0h]
  unsigned int v130; // [rsp+434h] [rbp-AA4h]
  WCHAR packageFamilyName[80]; // [rsp+4C0h] [rbp-A18h] BYREF
  _QWORD v132[2]; // [rsp+560h] [rbp-978h] BYREF
  int v133; // [rsp+570h] [rbp-968h]
  unsigned int v134; // [rsp+574h] [rbp-964h]
  char v135; // [rsp+578h] [rbp-960h] BYREF
  WCHAR v136[4]; // [rsp+D80h] [rbp-158h] BYREF
  CFilterProcessBase *v137; // [rsp+D88h] [rbp-150h]
  CFilterProcessBase *v138; // [rsp+D90h] [rbp-148h]
  SecUtil *v139; // [rsp+DA8h] [rbp-130h]
  wchar_t Buffer[64]; // [rsp+E10h] [rbp-C8h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+ED8h] [rbp+0h]

  v103[0] = a4;
  v7 = a3;
  *(_QWORD *)packageRelativeApplicationIdLength = a3;
  *(_QWORD *)packageFamilyNameLength = a6;
  v10 = 0;
  v96 = 0;
  if ( (byte_1802DA181 & 8) != 0 )
    McTemplateU0qzh_EventWriteTransfer(
      (_DWORD)this,
      (unsigned int)MSSearchTraceId_ProtocolHostObjInit,
      0,
      *((_QWORD *)a6 + 90),
      *((_WORD *)this + 18));
  TComNoUnkPointer<CPlugin>::operator=(this, a6);
  TLMString<32,32,1024>::TLMString<32,32,1024>(v126, a4);
  (*(void (__fastcall **)(_QWORD *, const wchar_t *, _QWORD, __int64))(v126[0] + 32LL))(
    v126,
    L"SDE",
    v127,
    0xFFFFFFFFLL);
  v11 = (struct IUnknownVtbl **)((char *)this + 184);
  EventW = CreateEventW(a2, 1, 0, (LPCWSTR)v126[1]);
  wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::reset(
    (char *)this + 184,
    EventW);
  if ( !*((_QWORD *)this + 23) )
    wil::details::in1diag3::Throw_GetLastError(
      retaddr,
      (void *)0x222,
      (unsigned int)"onecoreuap\\base\\appmodel\\search\\mssrch\\gather\\gthrsvc\\fltrpool.cxx",
      v13);
  if ( GetLastError() == 183 )
  {
    wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::reset(
      (char *)this + 184,
      0);
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x227,
      (unsigned int)"onecoreuap\\base\\appmodel\\search\\mssrch\\gather\\gthrsvc\\fltrpool.cxx",
      (const char *)0x800700B7LL,
      packageRelativeApplicationId);
  }
  *(_OWORD *)&EventAttributes.nLength = *(_OWORD *)&a2->nLength;
  *(&EventAttributes.bInheritHandle + 1) = HIDWORD(*(_QWORD *)&a2->bInheritHandle);
  EventAttributes.bInheritHandle = 1;
  v14 = CreateEventW(&EventAttributes, 1, 1, 0);
  wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::reset(
    (char *)this + 192,
    v14);
  if ( !*((_QWORD *)this + 24) )
    wil::details::in1diag3::Throw_GetLastError(
      retaddr,
      (void *)0x235,
      (unsigned int)"onecoreuap\\base\\appmodel\\search\\mssrch\\gather\\gthrsvc\\fltrpool.cxx",
      v15);
  TLMString<64,64,32767>::TLMString<64,64,32767>(v128, v7);
  memset_0(&StartupInfo, 0, 0x70u);
  StartupInfo.cb = 112;
  v132[0] = &CLMString::`vftable';
  v132[1] = &v135;
  v133 = 1025;
  CLMString::AssignInConstructor((CLMString *)v132, L"Container\\AgentGathererPipe\\", 0xFFFFFFFF);
  v132[0] = &TLMString<1024,1024,1048576>::`vftable';
  LODWORD(Environment[0]) = 0;
  HIDWORD(Environment[0]) = v134;
  Environment[1] = v132;
  if ( v130 < v134 || (CLMString::Mid(v128, v136, 0), v16 = CLMSubStr::operator==(v136, Environment), v17 = 1, !v16) )
    v17 = 0;
  v18 = 0;
  if ( !v17 )
    v18 = Value;
  *((_DWORD *)this + 7) = v18;
  while ( 1 )
  {
    Environment[0] = 0;
    if ( v10 >= *((_DWORD *)this + 7) )
      break;
    Instance = ATL::CComObject<CFilterPipe>::CreateInstance(Environment);
    if ( Instance < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x241,
        (unsigned int)"onecoreuap\\base\\appmodel\\search\\mssrch\\gather\\gthrsvc\\fltrpool.cxx",
        (const char *)(unsigned int)Instance,
        packageRelativeApplicationId);
    TComNoUnkPointer<CUMap>::TComNoUnkPointer<CUMap>(v136, Environment[0]);
    CLMString::operator=(v128, v7);
    v20 = _itow(++v10, Buffer, 10);
    CLMString::Append((CLMString *)v128, v20, 0xFFFFFFFF);
    v21 = *(struct IUnknown **)v136;
    v22 = CFilterPipeBase::Init(
            (CFilterPipeBase *)(*(_QWORD *)v136 + 8LL),
            a2,
            v129,
            (struct CFilterProcess *)(((unsigned __int64)this - 24) & -(__int64)(this != 0)));
    if ( v22 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x246,
        (unsigned int)"onecoreuap\\base\\appmodel\\search\\mssrch\\gather\\gthrsvc\\fltrpool.cxx",
        (const char *)(unsigned int)v22,
        packageRelativeApplicationId);
    v21[3].lpVtbl = *v11;
    v23 = CUnkSList::Append((CFilterProcessBase *)((char *)this + 48), v21);
    if ( v23 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x24A,
        (unsigned int)"onecoreuap\\base\\appmodel\\search\\mssrch\\gather\\gthrsvc\\fltrpool.cxx",
        (const char *)v23,
        packageRelativeApplicationId);
    TComPointer<CGatherStore>::~TComPointer<CGatherStore>(v136);
    v7 = *(const wchar_t **)packageRelativeApplicationIdLength;
  }
  v24 = ATL::CComObject<CFilterPipe>::CreateInstance(Environment);
  if ( v24 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x24E,
      (unsigned int)"onecoreuap\\base\\appmodel\\search\\mssrch\\gather\\gthrsvc\\fltrpool.cxx",
      (const char *)(unsigned int)v24,
      packageRelativeApplicationId);
  TComNoUnkPointer<CPlugin>::operator=((char *)this + 80, Environment[0]);
  v25 = v103[0];
  v26 = CFilterPipeBase::Init(
          (CFilterPipeBase *)(*((_QWORD *)this + 10) + 8LL),
          a2,
          v103[0],
          (struct CFilterProcess *)(((unsigned __int64)this - 24) & -(__int64)(this != 0)));
  if ( v26 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x251,
      (unsigned int)"onecoreuap\\base\\appmodel\\search\\mssrch\\gather\\gthrsvc\\fltrpool.cxx",
      (const char *)(unsigned int)v26,
      packageRelativeApplicationId);
  *(_QWORD *)(*((_QWORD *)this + 10) + 24LL) = *v11;
  v27 = (const wchar_t *)*((_QWORD *)CSearchBinPathString::CSearchBinPathString(
                                       (CSearchBinPathString *)packageFamilyName,
                                       L"SearchProtocolHost.exe")
                         + 1);
  v121 = &CLMString::`vftable';
  v122 = (wchar_t *)&v125;
  v123 = 65;
  CLMString::AssignInConstructor((CLMString *)&v121, v27, 0xFFFFFFFF);
  v121 = (void **)&CCICommonPathString::`vftable';
  TLMString<64,64,32767>::~TLMString<64,64,32767>(packageFamilyName);
  v99 = *((_WORD *)this + 18);
  ProcessParam = CPhMultiArch::MarshalCreateProcessParam((CLMString *)&v121);
  v29 = ProcessParam;
  if ( ProcessParam < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x26D,
      (unsigned int)"onecoreuap\\base\\appmodel\\search\\mssrch\\gather\\gthrsvc\\fltrpool.cxx",
      (const char *)(unsigned int)ProcessParam,
      packageRelativeApplicationId);
    TLMString<64,64,32767>::~TLMString<64,64,32767>(&v121);
    TLMString<1024,1024,1048576>::~TLMString<1024,1024,1048576>(v132);
    CPhMultiArch::StartupInfoWrapper::~StartupInfoWrapper((CPhMultiArch::StartupInfoWrapper *)&StartupInfo);
    TLMString<64,64,32767>::~TLMString<64,64,32767>(v128);
    TLMString<32,32,1024>::~TLMString<32,32,1024>(v126);
    return v29;
  }
  TLMString<64,64,32767>::TLMString<64,64,32767>(v109, v7);
  CLMString::operator+=(v109, 32);
  (*(void (__fastcall **)(_QWORD *, wchar_t *, _QWORD, __int64))(v109[0] + 32LL))(v109, v25, v110, 0xFFFFFFFFLL);
  CLMString::operator+=(v109, 32);
  _itow(Value, Buffer, 10);
  (*(void (__fastcall **)(_QWORD *, wchar_t *, _QWORD, __int64))(v109[0] + 32LL))(v109, Buffer, v110, 0xFFFFFFFFLL);
  CLMString::operator+=(v109, 32);
  _o__i64tow_s(-2147483646, Buffer, 64, 10);
  (*(void (__fastcall **)(_QWORD *, wchar_t *, _QWORD, __int64))(v109[0] + 32LL))(v109, Buffer, v110, 0xFFFFFFFFLL);
  (*(void (__fastcall **)(_QWORD *, const wchar_t *, _QWORD, __int64))(v109[0] + 32LL))(
    v109,
    L" \"",
    v110,
    0xFFFFFFFFLL);
  TLMString<32,32,1024>::TLMString<32,32,1024>(v136, L"Software\\Microsoft\\Windows Search");
  v96 = 4;
  (*(void (__fastcall **)(_QWORD *, CFilterProcessBase *, _QWORD, _QWORD))(v109[0] + 32LL))(
    v109,
    v137,
    v110,
    HIDWORD(v138));
  TLMString<32,32,1024>::~TLMString<32,32,1024>(v136);
  (*(void (__fastcall **)(_QWORD *, const wchar_t *, _QWORD, __int64))(v109[0] + 32LL))(v109, L"\"", v110, 0xFFFFFFFFLL);
  (*(void (__fastcall **)(_QWORD *, const char *, _QWORD, __int64))(v109[0] + 24LL))(v109, " \"", v110, 0xFFFFFFFFLL);
  if ( g_pGatheringService )
  {
    UserAgent = CGatheringService::GetUserAgent(v31, packageFamilyName);
    v33 = 5;
  }
  else
  {
    UserAgent = TLMString<32,32,1024>::TLMString<32,32,1024>(v136, L"DefaultUserAgent");
    v33 = 6;
  }
  v96 = v33;
  v34 = *(const wchar_t **)(UserAgent + 8);
  v116 = &CLMString::`vftable';
  v117 = &v120;
  v118 = 33;
  CLMString::AssignInConstructor((CLMString *)&v116, v34, 0xFFFFFFFF);
  v116 = (void **)&TLMString<32,32,1024>::`vftable';
  if ( (v33 & 2) != 0 )
  {
    LOBYTE(v33) = v33 & 0xFD;
    TLMString<32,32,1024>::~TLMString<32,32,1024>(v136);
  }
  if ( (v33 & 1) != 0 )
    TLMString<32,32,1024>::~TLMString<32,32,1024>(packageFamilyName);
  if ( !v119 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x288,
      (unsigned int)"onecoreuap\\base\\appmodel\\search\\mssrch\\gather\\gthrsvc\\fltrpool.cxx",
      (const char *)0x80040D15LL,
      packageRelativeApplicationId);
  (*(void (__fastcall **)(_QWORD *, char *, _QWORD))(v109[0] + 32LL))(v109, v117, v110);
  (*(void (__fastcall **)(_QWORD *, const wchar_t *, _QWORD, __int64))(v109[0] + 32LL))(v109, L"\"", v110, 0xFFFFFFFFLL);
  (*(void (__fastcall **)(_QWORD *, const char *, _QWORD, __int64))(v109[0] + 24LL))(v109, " \"", v110, 0xFFFFFFFFLL);
  if ( g_pGatheringService )
  {
    (*(void (__fastcall **)(_QWORD *, _QWORD, _QWORD, _QWORD))(v109[0] + 32LL))(
      v109,
      *((_QWORD *)g_pGatheringService + 96),
      v110,
      *((unsigned int *)g_pGatheringService + 195));
    v35 = *(_QWORD *)packageFamilyNameLength;
  }
  else
  {
    v35 = *(_QWORD *)packageFamilyNameLength;
    v36 = (_QWORD *)(*(_QWORD *)packageFamilyNameLength + 1528LL);
    if ( *(_QWORD *)(*(_QWORD *)packageFamilyNameLength + 1552LL) > 7u )
      v36 = (_QWORD *)*v36;
    (*(void (__fastcall **)(_QWORD *, _QWORD *, _QWORD, __int64))(v109[0] + 32LL))(v109, v36, v110, 0xFFFFFFFFLL);
  }
  (*(void (__fastcall **)(_QWORD *, const wchar_t *, _QWORD, __int64))(v109[0] + 32LL))(v109, L"\"", v110, 0xFFFFFFFFLL);
  (*(void (__fastcall **)(_QWORD *, const wchar_t *, _QWORD, __int64))(v109[0] + 32LL))(
    v109,
    L" \"",
    v110,
    0xFFFFFFFFLL);
  (*(void (__fastcall **)(_QWORD *, const wchar_t *, _QWORD, __int64))(v109[0] + 32LL))(
    v109,
    L"DownLevelDaemon",
    v110,
    0xFFFFFFFFLL);
  (*(void (__fastcall **)(_QWORD *, const wchar_t *, _QWORD, __int64))(v109[0] + 32LL))(
    v109,
    L"\" ",
    v110,
    0xFFFFFFFFLL);
  memset(&ProcessInformation, 0, sizeof(ProcessInformation));
  v37 = *(void **)(*(_QWORD *)this + 704LL);
  lpCommandLine = (LPWSTR)&v115;
  v113 = 65;
  v115 = 34;
  v114 = 1;
  v111 = &CCICommonPathString::`vftable';
  CLMString::Assign((CLMString *)&v111, v122, 1u, v124);
  (*((void (__fastcall **)(const int **, const wchar_t *, _QWORD, __int64))v111 + 4))(&v111, L"\" ", v114, 0xFFFFFFFFLL);
  (*((void (__fastcall **)(const int **, _QWORD, _QWORD, _QWORD))v111 + 4))(&v111, v109[1], v114, v110);
  if ( !*(_QWORD *)(*(_QWORD *)this + 888LL) )
    goto LABEL_65;
  v38 = (_QWORD *)(*(_QWORD *)this + 872LL);
  if ( *(_QWORD *)(*(_QWORD *)this + 896LL) > 7u )
    v38 = (_QWORD *)*v38;
  if ( v38 )
  {
    if ( v37 )
    {
      (*(void (__fastcall **)(_QWORD *, const wchar_t *, _QWORD, __int64))(v109[0] + 32LL))(
        v109,
        L" \"2\"",
        v110,
        0xFFFFFFFFLL);
      if ( !ImpersonateLoggedOnUser(v37) )
        wil::details::in1diag3::Throw_GetLastError(
          retaddr,
          (void *)0x2ED,
          (unsigned int)"onecoreuap\\base\\appmodel\\search\\mssrch\\gather\\gthrsvc\\fltrpool.cxx",
          v39);
      BYTE1(v96) = 1;
      packageFamilyNameLength[0] = 65;
      packageRelativeApplicationIdLength[0] = 66;
      if ( *(_QWORD *)(*(_QWORD *)this + 888LL) )
      {
        v40 = (const WCHAR *)(*(_QWORD *)this + 872LL);
        if ( *(_QWORD *)(*(_QWORD *)this + 896LL) > 7u )
          v40 = *(const WCHAR **)v40;
      }
      else
      {
        v40 = 0;
      }
      v41 = ParseApplicationUserModelId(
              v40,
              packageFamilyNameLength,
              packageFamilyName,
              packageRelativeApplicationIdLength,
              v136);
      if ( v41 )
        wil::details::in1diag3::Throw_Win32(
          retaddr,
          (void *)0x2FD,
          (unsigned int)"onecoreuap\\base\\appmodel\\search\\mssrch\\gather\\gthrsvc\\fltrpool.cxx",
          (const char *)v41,
          (unsigned int)packageRelativeApplicationIda);
      if ( *(_QWORD *)(*(_QWORD *)this + 888LL) )
      {
        v44 = (const unsigned __int16 *)(*(_QWORD *)this + 872LL);
        if ( *(_QWORD *)(*(_QWORD *)this + 896LL) > 7u )
          v44 = *(const unsigned __int16 **)v44;
      }
      else
      {
        v44 = 0;
      }
      v45 = AicLaunchProcessWithIdentity(
              v122,
              lpCommandLine,
              v42,
              v43,
              packageRelativeApplicationIda,
              &StartupInfo,
              packageFamilyName,
              v44,
              (HWND)lpStartupInfo,
              lpProcessInformation,
              v91,
              v92,
              v93,
              v94,
              v95,
              &ProcessInformation);
      if ( v45 )
        wil::details::in1diag3::Throw_Win32(
          retaddr,
          (void *)0x310,
          (unsigned int)"onecoreuap\\base\\appmodel\\search\\mssrch\\gather\\gthrsvc\\fltrpool.cxx",
          (const char *)v45,
          packageRelativeApplicationId);
      if ( !RevertToSelf() )
        wil::details::in1diag3::Throw_GetLastError(
          retaddr,
          (void *)0x2F1,
          (unsigned int)"onecoreuap\\base\\appmodel\\search\\mssrch\\gather\\gthrsvc\\fltrpool.cxx",
          v46);
    }
    else
    {
      MicrosoftTelemetryAssertTriggeredNoArgs();
    }
  }
  else
  {
LABEL_65:
    if ( v37 )
    {
      CLMString::Append((CLMString *)&v111, L" \"1\"", 0xFFFFFFFF);
      Environment[0] = 0;
      EnvironmentBlock = CreateEnvironmentBlock(Environment, v37, 0);
      *(_DWORD *)v136 = EnvironmentBlock;
      v49 = 525324;
      v96 = 525324;
      InitOnceExecuteOnce(
        &g_initOnceOnPerUserCatalogCheck,
        _lambda_f0b3a3176349e3c23c9c4546c2833d77_::_lambda_invoker_cdecl_,
        0,
        0);
      if ( g_isPerUserCatalogEnabled || IsControlIndexingOnBatteryEnabled() )
      {
        v49 = 17302540;
        v96 = 17302540;
      }
      if ( !EnvironmentBlock
        || !CreateProcessAsUserW(
              v37,
              0,
              lpCommandLine,
              0,
              0,
              0,
              v49,
              Environment[0],
              0,
              &StartupInfo,
              &ProcessInformation) )
      {
        DestroyEnvironmentBlock(Environment[0]);
        packageFamilyNameLength[0] = GetLastError();
        packageRelativeApplicationIdLength[0] = 1;
        SearchIndexerDiagnosticTelemetry::ProtocolHostProcessLaunchFailure<TLMString<64,64,32767> &,int,unsigned long,unsigned long &,int &>(
          (unsigned int)&v121,
          (unsigned int)packageRelativeApplicationIdLength,
          (unsigned int)packageFamilyNameLength,
          (unsigned int)&v96,
          (__int64)v136);
        wil::details::in1diag3::_Log_GetLastError(
          retaddr,
          (void *)0x2E1,
          (unsigned int)"onecoreuap\\base\\appmodel\\search\\mssrch\\gather\\gthrsvc\\fltrpool.cxx",
          v83);
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x2E2,
          (unsigned int)"onecoreuap\\base\\appmodel\\search\\mssrch\\gather\\gthrsvc\\fltrpool.cxx",
          (const char *)0x80040D39LL,
          packageRelativeApplicationIdd);
      }
      DestroyEnvironmentBlock(Environment[0]);
    }
    else
    {
      packageFamilyNameLength[0] = 524300;
      if ( !CreateProcessW(0, lpCommandLine, 0, 0, 0, 0x8000Cu, 0, 0, &StartupInfo, &ProcessInformation) )
      {
        LOBYTE(v96) = 0;
        packageRelativeApplicationIdLength[0] = GetLastError();
        *(_DWORD *)v136 = 0;
        SearchIndexerDiagnosticTelemetry::ProtocolHostProcessLaunchFailure<TLMString<64,64,32767> &,int,unsigned long,unsigned long &,bool>(
          (unsigned int)&v121,
          (unsigned int)v136,
          (unsigned int)packageRelativeApplicationIdLength,
          (unsigned int)packageFamilyNameLength,
          (__int64)&v96);
        wil::details::in1diag3::_Log_GetLastError(
          retaddr,
          (void *)0x2BE,
          (unsigned int)"onecoreuap\\base\\appmodel\\search\\mssrch\\gather\\gthrsvc\\fltrpool.cxx",
          v47);
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x2BF,
          (unsigned int)"onecoreuap\\base\\appmodel\\search\\mssrch\\gather\\gthrsvc\\fltrpool.cxx",
          (const char *)0x80040D39LL,
          packageRelativeApplicationIdc);
      }
    }
  }
  v50 = (SecUtil **)((char *)this + 8);
  wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::reset(
    (char *)this + 8,
    ProcessInformation.hProcess);
  *((_DWORD *)this + 10) = ProcessInformation.dwProcessId;
  wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::reset(
    (char *)this + 16,
    ProcessInformation.hThread);
  if ( (byte_1802DA181 & 8) != 0 )
    McTemplateU0qzh_EventWriteTransfer(
      v51,
      (unsigned int)MSSearchTraceId_ProtocolHostStarted,
      *((_DWORD *)this + 10),
      *(_QWORD *)(v35 + 720),
      *((_WORD *)this + 18));
  v139 = *v50;
  StringCbPrintfW(v136, 0x26u, L"%p");
  SearchIndexerTrace::Information(
    (wchar_t *)L"\"onecoreuap\\\\base\\\\appmodel\\\\search\\\\mssrch\\\\gather\\\\gthrsvc\\\\fltrpool.cxx\"",
    (const wchar_t *)0x31E,
    (unsigned int)L"[SrchGatherSvc] New Filter Process %ws\n",
    v136);
  v53 = SecUtil::AddAdministratorsToProcessDacl(*v50, v52);
  if ( v53 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x31F,
      (unsigned int)"onecoreuap\\base\\appmodel\\search\\mssrch\\gather\\gthrsvc\\fltrpool.cxx",
      (const char *)(unsigned int)v53,
      packageRelativeApplicationId);
  *(_OWORD *)v103 = 0;
  JobManagerInstance = GetJobManagerInstance(ProcessInformation.hProcess);
  if ( JobManagerInstance < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x322,
      (unsigned int)"onecoreuap\\base\\appmodel\\search\\mssrch\\gather\\gthrsvc\\fltrpool.cxx",
      (const char *)(unsigned int)JobManagerInstance,
      packageRelativeApplicationId);
  v55 = v103[0];
  v56 = *(__int64 (__fastcall **)(wchar_t *, _QWORD))(*(_QWORD *)v103[0] + 32LL);
  MaxCPURateForFilterProcesses = GetMaxCPURateForFilterProcesses();
  v58 = v56(v55, MaxCPURateForFilterProcesses);
  if ( v58 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x324,
      (unsigned int)"onecoreuap\\base\\appmodel\\search\\mssrch\\gather\\gthrsvc\\fltrpool.cxx",
      (const char *)(unsigned int)v58,
      packageRelativeApplicationId);
  if ( ResumeThread(*((HANDLE *)this + 2)) == -1 )
    wil::details::in1diag3::Throw_GetLastError(
      retaddr,
      (void *)0x328,
      (unsigned int)"onecoreuap\\base\\appmodel\\search\\mssrch\\gather\\gthrsvc\\fltrpool.cxx",
      v59);
  *(_QWORD *)(*((_QWORD *)this + 10) + 32LL) = *v50;
  v60 = CFilterPipeBase::Connect((CFilterPipeBase *)(*((_QWORD *)this + 10) + 8LL));
  if ( v60 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x32C,
      (unsigned int)"onecoreuap\\base\\appmodel\\search\\mssrch\\gather\\gthrsvc\\fltrpool.cxx",
      (const char *)(unsigned int)v60,
      packageRelativeApplicationId);
  TargetHandle = 0;
  v61 = *v50;
  CurrentProcess = GetCurrentProcess();
  v63 = GetCurrentProcess();
  if ( !DuplicateHandle(v63, CurrentProcess, v61, &TargetHandle, 0x100000u, 0, 0) )
    wil::details::in1diag3::Throw_GetLastError(
      retaddr,
      (void *)0x336,
      (unsigned int)"onecoreuap\\base\\appmodel\\search\\mssrch\\gather\\gthrsvc\\fltrpool.cxx",
      v64);
  v105 = 0;
  v65 = *v50;
  v66 = (void *)*((_QWORD *)this + 24);
  v67 = GetCurrentProcess();
  if ( !DuplicateHandle(v67, v66, v65, &v105, 0, 0, 2u) )
    wil::details::in1diag3::Throw_GetLastError(
      retaddr,
      (void *)0x340,
      (unsigned int)"onecoreuap\\base\\appmodel\\search\\mssrch\\gather\\gthrsvc\\fltrpool.cxx",
      v68);
  v69 = 0;
  v101 = 0;
  if ( g_pGatheringService )
  {
    v70 = *((_QWORD *)g_pGatheringService + 500);
    if ( !v70 )
      goto LABEL_98;
    v71 = *(void **)(v70 + 768);
    if ( !v71 )
      goto LABEL_98;
    v72 = *v50;
    v73 = GetCurrentProcess();
    if ( !DuplicateHandle(v73, v71, v72, &v101, 0x100000u, 0, 2u) )
      wil::details::in1diag3::Throw_GetLastError(
        retaddr,
        (void *)0x34F,
        (unsigned int)"onecoreuap\\base\\appmodel\\search\\mssrch\\gather\\gthrsvc\\fltrpool.cxx",
        v74);
  }
  else
  {
    v75 = *v50;
    v76 = *(void **)(v35 + 1568);
    v77 = GetCurrentProcess();
    if ( !DuplicateHandle(v77, v76, v75, &v101, 0x100000u, 0, 2u) )
      wil::details::in1diag3::Throw_GetLastError(
        retaddr,
        (void *)0x35B,
        (unsigned int)"onecoreuap\\base\\appmodel\\search\\mssrch\\gather\\gthrsvc\\fltrpool.cxx",
        v78);
  }
  v69 = v101;
LABEL_98:
  v79 = CFilterProcessBase::SendControlHandles(this, TargetHandle, v69);
  if ( v79 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x35E,
      (unsigned int)"onecoreuap\\base\\appmodel\\search\\mssrch\\gather\\gthrsvc\\fltrpool.cxx",
      (const char *)(unsigned int)v79,
      packageRelativeApplicationIdb);
  *(_QWORD *)v136 = (char *)this + 48;
  v80 = (CFilterProcessBase *)((char *)this + 48);
  v138 = 0;
  while ( this != (CFilterProcessBase *)-48LL && v80 )
  {
    v138 = v80;
    v80 = *(CFilterProcessBase **)v80;
    if ( v80 == (CFilterProcessBase *)((char *)this + 56) )
      v80 = 0;
    v137 = v80;
    if ( !v80 )
      break;
    Environment[0] = 0;
    CNamedListIter<CGatherLog,IGatherLog>::GetCurrentValue(v136, Environment);
    v81 = (CFilterPipeBase *)((char *)Environment[0] + 8);
    *((_QWORD *)Environment[0] + 4) = *v50;
    v82 = CFilterPipeBase::Connect(v81);
    if ( v82 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x368,
        (unsigned int)"onecoreuap\\base\\appmodel\\search\\mssrch\\gather\\gthrsvc\\fltrpool.cxx",
        (const char *)(unsigned int)v82,
        packageRelativeApplicationIdb);
    TComPointer<CGatherStore>::~TComPointer<CGatherStore>(Environment);
  }
  if ( v103[1] )
    std::_Ref_count_base::_Decref((std::_Ref_count_base *)v103[1]);
  TLMString<64,64,32767>::~TLMString<64,64,32767>(&v111);
  TLMString<32,32,1024>::~TLMString<32,32,1024>(&v116);
  TLMString<64,64,32767>::~TLMString<64,64,32767>(v109);
  TLMString<64,64,32767>::~TLMString<64,64,32767>(&v121);
  TLMString<1024,1024,1048576>::~TLMString<1024,1024,1048576>(v132);
  if ( lpAttributeList )
  {
    DeleteProcThreadAttributeList(lpAttributeList);
    operator delete(lpAttributeList);
    lpAttributeList = 0;
  }
  TLMString<64,64,32767>::~TLMString<64,64,32767>(v128);
  TLMString<32,32,1024>::~TLMString<32,32,1024>(v126);
  return 0;
}

```

## disassembly

```asm
0x18002538c  push    rbx
0x18002538e  push    rsi
0x18002538f  push    rdi
0x180025390  push    r12
0x180025392  push    r13
0x180025394  push    r14
0x180025396  push    r15
0x180025398  sub     rsp, 0EA0h
0x18002539f  mov     rax, cs:__security_cookie
0x1800253a6  xor     rax, rsp
0x1800253a9  mov     [rsp+0ED8h+var_48], rax
0x1800253b1  mov     rbx, r9
0x1800253b4  mov     [rsp+0ED8h+var_E18], rbx
0x1800253bc  mov     r13, r8
0x1800253bf  mov     qword ptr [rsp+0ED8h+packageRelativeApplicationIdLength], r8
0x1800253c7  mov     r12, rdx
0x1800253ca  mov     r14, rcx
0x1800253cd  mov     rsi, [rsp+0ED8h+arg_28]
0x1800253d5  mov     qword ptr [rsp+0ED8h+packageFamilyNameLength], rsi
0x1800253dd  xor     r15d, r15d
0x1800253e0  mov     edi, r15d
0x1800253e3  mov     [rsp+0ED8h+var_E58], r15d
0x1800253eb  test    cs:byte_1802DA181, 8
0x1800253f2  jz      short loc_180025414
0x1800253f4  movzx   eax, word ptr [rcx+24h]
0x1800253f8  mov     word ptr [rsp+0ED8h+packageRelativeApplicationId], ax; int
0x1800253fd  mov     r9, [rsi+2D0h]
0x180025404  xor     r8d, r8d
0x180025407  lea     rdx, MSSearchTraceId_ProtocolHostObjInit
0x18002540e  call    McTemplateU0qzh_EventWriteTransfer
0x180025413  nop
0x180025414  mov     rdx, rsi
0x180025417  mov     rcx, r14
0x18002541a  call    ??4?$TComNoUnkPointer@VCPlugin@@@@QEAAPEAVCPlugin@@PEAV1@@Z; TComNoUnkPointer<CPlugin>::operator=(CPlugin *)
0x18002541f  mov     rdx, rbx
0x180025422  lea     rcx, [rsp+0ED8h+var_B18]
0x18002542a  call    ??0?$TLMString@$0CA@$0CA@$0EAA@@@QEAA@PEB_W@Z; TLMString<32,32,1024>::TLMString<32,32,1024>(wchar_t const *)
0x18002542f  nop
0x180025430  mov     rax, [rsp+0ED8h+var_B18]
0x180025438  or      r9d, 0FFFFFFFFh
0x18002543c  mov     r8d, [rsp+0ED8h+var_B04]
0x180025444  lea     rdx, aSde; "SDE"
0x18002544b  lea     rcx, [rsp+0ED8h+var_B18]
0x180025453  mov     rax, [rax+20h]
0x180025457  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002545c  lea     rsi, [r14+0B8h]
0x180025463  mov     r9, [rsp+0ED8h+lpName]; lpName
0x18002546b  xor     r8d, r8d; bInitialState
0x18002546e  lea     ebx, [r8+1]
0x180025472  mov     edx, ebx; bManualReset
0x180025474  mov     rcx, r12; lpEventAttributes
0x180025477  call    cs:__imp_CreateEventW
0x18002547d  mov     rdx, rax
0x180025480  mov     rcx, rsi
0x180025483  call    ?reset@?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::reset(void *)
0x180025488  mov     rcx, [rsp+0ED8h]; this
0x180025490  cmp     [rsi], r15
0x180025493  jnz     short loc_1800254A6
0x180025495  lea     r8, aOnecoreuapBase_245; "onecoreuap\\base\\appmodel\\search\\mss"...
0x18002549c  mov     edx, 222h; void *
0x1800254a1  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
0x1800254a6  call    cs:__imp_GetLastError
0x1800254ac  cmp     eax, 0B7h
0x1800254b1  jnz     short loc_1800254DC
0x1800254b3  xor     edx, edx
0x1800254b5  mov     rcx, rsi
0x1800254b8  call    ?reset@?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::reset(void *)
0x1800254bd  mov     rcx, [rsp+0ED8h]; this
0x1800254c5  mov     r9d, 800700B7h; char *
0x1800254cb  lea     r8, aOnecoreuapBase_245; "onecoreuap\\base\\appmodel\\search\\mss"...
0x1800254d2  mov     edx, 227h; void *
0x1800254d7  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800254dc  movups  xmm0, xmmword ptr [r12]
0x1800254e1  movups  xmmword ptr [rsp+0ED8h+EventAttributes.nLength], xmm0
0x1800254e9  movsd   xmm1, qword ptr [r12+10h]
0x1800254f0  movsd   qword ptr [rsp+0ED8h+EventAttributes.bInheritHandle], xmm1
0x1800254f9  mov     [rsp+0ED8h+EventAttributes.bInheritHandle], ebx
0x180025500  lea     rbx, [r14+0C0h]
0x180025507  xor     r9d, r9d; lpName
0x18002550a  lea     eax, [r9+1]
0x18002550e  mov     r8d, eax; bInitialState
0x180025511  mov     edx, eax; bManualReset
0x180025513  lea     rcx, [rsp+0ED8h+EventAttributes]; lpEventAttributes
0x18002551b  call    cs:__imp_CreateEventW
0x180025521  mov     rdx, rax
0x180025524  mov     rcx, rbx
0x180025527  call    ?reset@?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::reset(void *)
0x18002552c  mov     rcx, [rsp+0ED8h]; this
0x180025534  cmp     [rbx], r15
0x180025537  jnz     short loc_18002554A
0x180025539  lea     r8, aOnecoreuapBase_245; "onecoreuap\\base\\appmodel\\search\\mss"...
0x180025540  mov     edx, 235h; void *
0x180025545  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
0x18002554a  mov     rdx, r13
0x18002554d  lea     rcx, [rsp+0ED8h+var_AB8]
0x180025555  call    ??0?$TLMString@$0EA@$0EA@$0HPPP@@@QEAA@PEB_W@Z; TLMString<64,64,32767>::TLMString<64,64,32767>(wchar_t const *)
0x18002555a  nop
0x18002555b  mov     ebx, 70h ; 'p'
0x180025560  mov     r8d, ebx; Size
0x180025563  xor     edx, edx; Val
0x180025565  lea     rcx, [rsp+0ED8h+StartupInfo]; void *
0x18002556d  call    memset_0
0x180025572  mov     [rsp+0ED8h+StartupInfo.cb], ebx
0x180025579  lea     rax, ??_7CLMString@@6B@; const CLMString::`vftable'
0x180025580  mov     [rsp+0ED8h+var_978], rax
0x180025588  lea     rax, [rsp+0ED8h+var_960]
0x180025590  mov     [rsp+0ED8h+var_970], rax
0x180025598  mov     [rsp+0ED8h+var_968], 401h
0x1800255a3  or      r8d, 0FFFFFFFFh; unsigned int
0x1800255a7  lea     rdx, aContainerAgent; "Container\\AgentGathererPipe\\"
0x1800255ae  lea     rcx, [rsp+0ED8h+var_978]; this
0x1800255b6  call    ?AssignInConstructor@CLMString@@IEAAHPEB_WI@Z; CLMString::AssignInConstructor(wchar_t const *,uint)
0x1800255bb  lea     rax, ??_7?$TLMString@$0EAA@$0EAA@$0BAAAAA@@@6B@; const TLMString<1024,1024,1048576>::`vftable'
0x1800255c2  mov     [rsp+0ED8h+var_978], rax
0x1800255ca  mov     dword ptr [rsp+0ED8h+Environment], r15d
0x1800255d2  mov     r9d, [rsp+0ED8h+var_964]
0x1800255da  mov     dword ptr [rsp+0ED8h+Environment+4], r9d
0x1800255e2  lea     rax, [rsp+0ED8h+var_978]
0x1800255ea  mov     [rsp+0ED8h+var_E48], rax
0x1800255f2  cmp     [rsp+0ED8h+var_AA4], r9d
0x1800255fa  jb      short loc_180025630
0x1800255fc  xor     r8d, r8d
0x1800255ff  lea     rdx, [rsp+0ED8h+var_158]
0x180025607  lea     rcx, [rsp+0ED8h+var_AB8]
0x18002560f  call    ?Mid@CLMString@@QEBA?AVCLMSubStr@@II@Z; CLMString::Mid(uint,uint)
0x180025614  lea     rdx, [rsp+0ED8h+Environment]
0x18002561c  lea     rcx, [rsp+0ED8h+var_158]
0x180025624  call    ??8CLMSubStr@@QEBAHAEBV0@@Z; CLMSubStr::operator==(CLMSubStr const &)
0x180025629  test    eax, eax
0x18002562b  lea     ecx, [rbx-6Fh]
0x18002562e  jnz     short loc_180025633
0x180025630  mov     ecx, r15d
0x180025633  mov     eax, r15d
0x180025636  test    ecx, ecx
0x180025638  cmovz   eax, [rsp+0ED8h+Value]
0x180025640  mov     [r14+1Ch], eax
0x180025644  mov     [rsp+0ED8h+Environment], 0
0x180025650  lea     rcx, [rsp+0ED8h+Environment]
0x180025658  cmp     r15d, [r14+1Ch]
0x18002565c  jnb     loc_180025775
0x180025662  call    ?CreateInstance@?$CComObject@VCFilterPipe@@@ATL@@SAJPEAPEAV12@@Z; ATL::CComObject<CFilterPipe>::CreateInstance(ATL::CComObject<CFilterPipe> * *)
0x180025667  mov     rcx, [rsp+0ED8h]; this
0x18002566f  test    eax, eax
0x180025671  jns     short loc_180025687
0x180025673  mov     r9d, eax; char *
0x180025676  lea     r8, aOnecoreuapBase_245; "onecoreuap\\base\\appmodel\\search\\mss"...
0x18002567d  mov     edx, 241h; void *
0x180025682  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180025687  mov     rdx, [rsp+0ED8h+Environment]
0x18002568f  lea     rcx, [rsp+0ED8h+var_158]
0x180025697  call    ??0?$TComNoUnkPointer@VCUMap@@@@QEAA@PEAVCUMap@@@Z; TComNoUnkPointer<CUMap>::TComNoUnkPointer<CUMap>(CUMap *)
0x18002569c  nop
0x18002569d  mov     rdx, r13
0x1800256a0  lea     rcx, [rsp+0ED8h+var_AB8]
0x1800256a8  call    ??4CLMString@@QEAAXPEB_W@Z; CLMString::operator=(wchar_t const *)
0x1800256ad  inc     r15d
0x1800256b0  mov     r8d, 0Ah; Radix
0x1800256b6  lea     rdx, [rsp+0ED8h+Buffer]; Buffer
0x1800256be  mov     ecx, r15d; Value
0x1800256c1  call    cs:__imp__itow
0x1800256c7  or      r8d, 0FFFFFFFFh; unsigned int
0x1800256cb  mov     rdx, rax; wchar_t *
0x1800256ce  lea     rcx, [rsp+0ED8h+var_AB8]; this
0x1800256d6  call    ?Append@CLMString@@QEAAHPEB_WI@Z; CLMString::Append(wchar_t const *,uint)
0x1800256db  mov     rbx, qword ptr [rsp+0ED8h+var_158]
0x1800256e3  mov     rax, r14
0x1800256e6  lea     rcx, [r14-18h]
0x1800256ea  neg     rax
0x1800256ed  sbb     r9, r9
0x1800256f0  and     r9, rcx; struct CFilterProcess *
0x1800256f3  mov     r8, [rsp+0ED8h+var_AB0]; wchar_t *
0x1800256fb  mov     rdx, r12; struct _SECURITY_ATTRIBUTES *
0x1800256fe  lea     rcx, [rbx+8]; this
0x180025702  call    ?Init@CFilterPipeBase@@QEAAJPEAU_SECURITY_ATTRIBUTES@@PEB_WPEAVCFilterProcess@@@Z; CFilterPipeBase::Init(_SECURITY_ATTRIBUTES *,wchar_t const *,CFilterProcess *)
0x180025707  mov     rcx, [rsp+0ED8h]; this
0x18002570f  test    eax, eax
0x180025711  jns     short loc_180025727
0x180025713  mov     r9d, eax; char *
0x180025716  lea     r8, aOnecoreuapBase_245; "onecoreuap\\base\\appmodel\\search\\mss"...
0x18002571d  mov     edx, 246h; void *
0x180025722  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180025727  mov     rax, [rsi]
0x18002572a  mov     [rbx+18h], rax
0x18002572e  lea     rcx, [r14+30h]; this
0x180025732  mov     rdx, rbx; struct IUnknown *
0x180025735  call    ?Append@CUnkSList@@QEAAJPEAUIUnknown@@@Z; CUnkSList::Append(IUnknown *)
0x18002573a  mov     rcx, [rsp+0ED8h]; this
0x180025742  test    eax, eax
0x180025744  jz      short loc_18002575B
0x180025746  mov     r9d, eax; char *
0x180025749  lea     r8, aOnecoreuapBase_245; "onecoreuap\\base\\appmodel\\search\\mss"...
0x180025750  mov     edx, 24Ah; void *
0x180025755  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18002575b  lea     rcx, [rsp+0ED8h+var_158]
0x180025763  call    ??1?$TComPointer@VCGatherStore@@@@QEAA@XZ; TComPointer<CGatherStore>::~TComPointer<CGatherStore>(void)
0x180025768  mov     r13, qword ptr [rsp+0ED8h+packageRelativeApplicationIdLength]
0x180025770  jmp     loc_180025644
0x180025775  call    ?CreateInstance@?$CComObject@VCFilterPipe@@@ATL@@SAJPEAPEAV12@@Z; ATL::CComObject<CFilterPipe>::CreateInstance(ATL::CComObject<CFilterPipe> * *)
0x18002577a  mov     rcx, [rsp+0ED8h]; this
0x180025782  test    eax, eax
0x180025784  jns     short loc_18002579A
0x180025786  mov     r9d, eax; char *
0x180025789  lea     r8, aOnecoreuapBase_245; "onecoreuap\\base\\appmodel\\search\\mss"...
0x180025790  mov     edx, 24Eh; void *
0x180025795  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18002579a  lea     rbx, [r14+50h]
0x18002579e  mov     rdx, [rsp+0ED8h+Environment]
0x1800257a6  mov     rcx, rbx
0x1800257a9  call    ??4?$TComNoUnkPointer@VCPlugin@@@@QEAAPEAVCPlugin@@PEAV1@@Z; TComNoUnkPointer<CPlugin>::operator=(CPlugin *)
0x1800257ae  mov     rax, r14
0x1800257b1  neg     rax
0x1800257b4  sbb     r9, r9
0x1800257b7  lea     rax, [r14-18h]
0x1800257bb  and     r9, rax; struct CFilterProcess *
0x1800257be  mov     rcx, [rbx]
0x1800257c1  add     rcx, 8; this
0x1800257c5  mov     r15, [rsp+0ED8h+var_E18]
0x1800257cd  mov     r8, r15; wchar_t *
0x1800257d0  mov     rdx, r12; struct _SECURITY_ATTRIBUTES *
0x1800257d3  call    ?Init@CFilterPipeBase@@QEAAJPEAU_SECURITY_ATTRIBUTES@@PEB_WPEAVCFilterProcess@@@Z; CFilterPipeBase::Init(_SECURITY_ATTRIBUTES *,wchar_t const *,CFilterProcess *)
0x1800257d8  mov     rcx, [rsp+0ED8h]; this
0x1800257e0  test    eax, eax
0x1800257e2  jns     short loc_1800257F8
0x1800257e4  mov     r9d, eax; char *
0x1800257e7  lea     r8, aOnecoreuapBase_245; "onecoreuap\\base\\appmodel\\search\\mss"...
0x1800257ee  mov     edx, 251h; void *
0x1800257f3  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800257f8  mov     rcx, [rbx]
0x1800257fb  mov     rax, [rsi]
0x1800257fe  mov     [rcx+18h], rax
0x180025802  lea     rdx, aSearchprotocol_2; "SearchProtocolHost.exe"
0x180025809  lea     rcx, [rsp+0ED8h+packageFamilyName]; this
0x180025811  call    ??0CSearchBinPathString@@QEAA@PEB_W@Z; CSearchBinPathString::CSearchBinPathString(wchar_t const *)
0x180025816  nop
0x180025817  mov     rdx, [rax+8]; wchar_t *
0x18002581b  lea     rax, ??_7CLMString@@6B@; const CLMString::`vftable'
0x180025822  mov     [rsp+0ED8h+var_BB8], rax
0x18002582a  lea     rax, [rsp+0ED8h+var_BA0]
0x180025832  mov     [rsp+0ED8h+var_BB0], rax
0x18002583a  mov     [rsp+0ED8h+var_BA8], 41h ; 'A'
0x180025845  or      esi, 0FFFFFFFFh
0x180025848  mov     r8d, esi; unsigned int
0x18002584b  lea     rcx, [rsp+0ED8h+var_BB8]; this
0x180025853  call    ?AssignInConstructor@CLMString@@IEAAHPEB_WI@Z; CLMString::AssignInConstructor(wchar_t const *,uint)
0x180025858  lea     rax, ??_7CCICommonPathString@@6B@; const CCICommonPathString::`vftable'
0x18002585f  mov     [rsp+0ED8h+var_BB8], rax
0x180025867  lea     rcx, [rsp+0ED8h+packageFamilyName]
0x18002586f  call    ??1?$TLMString@$0EA@$0EA@$0HPPP@@@UEAA@XZ; TLMString<64,64,32767>::~TLMString<64,64,32767>(void)
0x180025874  movzx   eax, word ptr [r14+24h]
0x180025879  mov     [rsp+0ED8h+var_E38], ax
0x180025881  lea     r8, [rsp+0ED8h+var_E38]
0x180025889  lea     rdx, [rsp+0ED8h+StartupInfo]
0x180025891  lea     rcx, [rsp+0ED8h+var_BB8]; this
0x180025899  call    ?MarshalCreateProcessParam@CPhMultiArch@@SAJAEAV?$TLMString@$0EA@$0EA@$0HPPP@@@PEAVStartupInfoWrapper@1@PEAG@Z; CPhMultiArch::MarshalCreateProcessParam(TLMString<64,64,32767> &,CPhMultiArch::StartupInfoWrapper *,ushort *)
0x18002589e  mov     ebx, eax
0x1800258a0  test    eax, eax
0x1800258a2  jns     short loc_18002590D
0x1800258a4  mov     rcx, [rsp+0ED8h]; this
0x1800258ac  mov     r9d, eax; char *
0x1800258af  lea     r8, aOnecoreuapBase_245; "onecoreuap\\base\\appmodel\\search\\mss"...
0x1800258b6  mov     edx, 26Dh; void *
0x1800258bb  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800258c0  nop
0x1800258c1  lea     rcx, [rsp+0ED8h+var_BB8]
0x1800258c9  call    ??1?$TLMString@$0EA@$0EA@$0HPPP@@@UEAA@XZ; TLMString<64,64,32767>::~TLMString<64,64,32767>(void)
0x1800258ce  nop
0x1800258cf  lea     rcx, [rsp+0ED8h+var_978]
0x1800258d7  call    ??1?$TLMString@$0EAA@$0EAA@$0BAAAAA@@@UEAA@XZ; TLMString<1024,1024,1048576>::~TLMString<1024,1024,1048576>(void)
0x1800258dc  nop
0x1800258dd  lea     rcx, [rsp+0ED8h+StartupInfo]; this
0x1800258e5  call    ??1StartupInfoWrapper@CPhMultiArch@@QEAA@XZ; CPhMultiArch::StartupInfoWrapper::~StartupInfoWrapper(void)
0x1800258ea  nop
0x1800258eb  lea     rcx, [rsp+0ED8h+var_AB8]
0x1800258f3  call    ??1?$TLMString@$0EA@$0EA@$0HPPP@@@UEAA@XZ; TLMString<64,64,32767>::~TLMString<64,64,32767>(void)
0x1800258f8  nop
0x1800258f9  lea     rcx, [rsp+0ED8h+var_B18]
0x180025901  call    ??1?$TLMString@$0CA@$0CA@$0EAA@@@UEAA@XZ; TLMString<32,32,1024>::~TLMString<32,32,1024>(void)
0x180025906  mov     eax, ebx
0x180025908  jmp     loc_18002675B
0x18002590d  mov     rdx, r13
0x180025910  lea     rcx, [rsp+0ED8h+var_D58]
0x180025918  call    ??0?$TLMString@$0EA@$0EA@$0HPPP@@@QEAA@PEB_W@Z; TLMString<64,64,32767>::TLMString<64,64,32767>(wchar_t const *)
0x18002591d  nop
0x18002591e  mov     ebx, 20h ; ' '
0x180025923  mov     edx, ebx
0x180025925  lea     rcx, [rsp+0ED8h+var_D58]
0x18002592d  call    ??YCLMString@@QEAAX_W@Z; CLMString::operator+=(wchar_t)
0x180025932  mov     rax, [rsp+0ED8h+var_D58]
0x18002593a  mov     r9d, esi
0x18002593d  mov     r8d, [rsp+0ED8h+var_D44]
0x180025945  mov     rdx, r15
0x180025948  lea     rcx, [rsp+0ED8h+var_D58]
0x180025950  mov     rax, [rax+20h]
0x180025954  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180025959  mov     edx, ebx
0x18002595b  lea     rcx, [rsp+0ED8h+var_D58]
0x180025963  call    ??YCLMString@@QEAAX_W@Z; CLMString::operator+=(wchar_t)
0x180025968  lea     r15d, [rbx-16h]
0x18002596c  mov     r8d, r15d; Radix
0x18002596f  lea     rdx, [rsp+0ED8h+Buffer]; Buffer
  ... truncated ...
```
