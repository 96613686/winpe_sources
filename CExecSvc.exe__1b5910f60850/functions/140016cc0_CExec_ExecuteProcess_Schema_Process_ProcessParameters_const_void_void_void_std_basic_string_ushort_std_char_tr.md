# CExec::ExecuteProcess(Schema::Process::ProcessParameters const &,void *,void *,void *,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &,void *)

- ea: `0x140016cc0`
- end: `0x140017d11`
- name: `?ExecuteProcess@CExec@@YA?AV?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@AEBUProcessParameters@Process@Schema@@PEAX11AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@1@Z`
- size: `4177`
- prototype: `LPHANDLE __fastcall(HANDLE *, __int64, void *, void *, HANDLE hSourceHandle, ConsoleToPipeRedirector *)`
- caller_count: `1`
- callee_count: `35`
- tags: `authz_impersonation, loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x140008670`

## callees

- `0x140002310`
- `0x140002334`
- `0x140002ecc`
- `0x1400068ac`
- `0x140008060`
- `0x140008160`
- `0x14000d5cc`
- `0x14000e3a4`
- `0x14000e828`
- `0x1400126b0`
- `0x140015180`
- `0x1400155e4`
- `0x140015798`
- `0x140015cdc`
- `0x140015d7c`
- `0x1400162fc`
- `0x140016480`
- `0x1400166ec`
- `0x1400168e0`
- `0x140016b50`
- `0x140016cc0`
- `0x140017de8`
- `0x1400187e0`
- `0x1400196a0`
- `0x1400197f4`
- `0x140019948`
- `0x140019a9c`
- `0x14001a43c`
- `0x14001a640`
- `0x14001b5ec`
- `0x14001b9d8`
- `0x14001cca8`
- `0x14001ce88`
- `0x14001f5bc`
- `0x140024010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140016f78`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400173a2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400173cd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140016f78`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400173a2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400173cd`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x140016f8b`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1400173b5`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1400173e0`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x140016f8b`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1400173b5`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1400173e0`
- `api-ms-win-core-processthreads-l1-1-0!CreateProcessAsUserW` at `0x140017910`
- `api-ms-win-core-processthreads-l1-1-0!CreateProcessAsUserW` at `0x140017910`
- `api-ms-win-core-processthreads-l1-1-0!UpdateProcThreadAttribute` at `0x14001756b`
- `api-ms-win-core-processthreads-l1-1-0!UpdateProcThreadAttribute` at `0x1400175bb`
- `api-ms-win-core-processthreads-l1-1-0!UpdateProcThreadAttribute` at `0x1400175f1`
- `api-ms-win-core-processthreads-l1-1-0!UpdateProcThreadAttribute` at `0x14001772b`
- `api-ms-win-core-processthreads-l1-1-0!UpdateProcThreadAttribute` at `0x14001756b`
- `api-ms-win-core-processthreads-l1-1-0!UpdateProcThreadAttribute` at `0x1400175bb`
- `api-ms-win-core-processthreads-l1-1-0!UpdateProcThreadAttribute` at `0x1400175f1`
- `api-ms-win-core-processthreads-l1-1-0!UpdateProcThreadAttribute` at `0x14001772b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x14001798b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x140017994`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x14001798b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x140017994`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x140017b6f`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x140017b6f`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x140017155`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x140017155`
- `api-ms-win-core-handle-l1-1-0!DuplicateHandle` at `0x1400179b9`
- `api-ms-win-core-handle-l1-1-0!DuplicateHandle` at `0x1400179b9`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140016f83`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14001714c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1400173ad`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1400173d8`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140017440`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140017457`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140017abf`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140017add`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140017b27`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140017b3b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140017b83`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140017b98`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140017bb0`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140017bc8`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140017be0`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140016f83`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14001714c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1400173ad`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1400173d8`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140017440`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140017457`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140017abf`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140017add`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140017b27`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140017b3b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140017b83`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140017b98`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140017bb0`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140017bc8`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140017be0`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x140017aff`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x140017aff`
- `api-ms-win-eventing-provider-l1-1-0!EventWrite` at `0x140016eb5`
- `api-ms-win-eventing-provider-l1-1-0!EventWrite` at `0x140016eb5`
- `api-ms-win-core-console-l1-2-1!ClosePseudoConsole` at `0x140017b12`
- `api-ms-win-core-console-l1-2-1!ClosePseudoConsole` at `0x140017b12`
- `api-ms-win-core-console-internal-l1-1-0!CreatePseudoConsoleAsUser` at `0x140017383`
- `api-ms-win-core-console-internal-l1-1-0!CreatePseudoConsoleAsUser` at `0x140017383`
- `profapi!__imp_CreateEnvBlock` at `0x140017182`
- `profapi!__imp_CreateEnvBlock` at `0x140017182`
- `profapi!__imp_DestroyEnvBlock` at `0x140017b68`
- `profapi!__imp_DestroyEnvBlock` at `0x140017b68`
- `profapi!__imp_LoadProfileBasic` at `0x1400170dc`
- `profapi!__imp_LoadProfileBasic` at `0x1400170dc`

## string_xrefs

- `0x14001763f`: `CreateProcessAsUserW`
- `0x140017c3f`: `onecore\vm\compute\service\cexec\lib\cexecprocess.cpp`
- `0x140017c54`: `onecore\vm\compute\service\cexec\lib\cexecprocess.cpp`
- `0x140017c66`: `onecore\vm\compute\service\cexec\lib\cexecprocess.cpp`
- `0x140017c7b`: `onecore\vm\compute\service\cexec\lib\cexecprocess.cpp`
- `0x140017c90`: `onecore\vm\compute\service\cexec\lib\cexecprocess.cpp`
- `0x140017ca9`: `onecore\vm\compute\service\cexec\lib\cexecprocess.cpp`
- `0x140017cbb`: `onecore\vm\compute\service\cexec\lib\cexecprocess.cpp`
- `0x140017cd0`: `onecore\vm\compute\service\cexec\lib\cexecprocess.cpp`
- `0x140017ce2`: `onecore\vm\compute\service\cexec\lib\cexecprocess.cpp`
- `0x140017cf4`: `onecore\vm\compute\service\cexec\lib\cexecprocess.cpp`

## pseudocode

```c
LPHANDLE __fastcall CExec::ExecuteProcess(
        HANDLE *a1,
        __int64 a2,
        void *a3,
        void *a4,
        HANDLE hSourceHandle,
        ConsoleToPipeRedirector *a6)
{
  const unsigned __int16 *v9; // rdi
  const unsigned __int16 *v10; // r8
  const unsigned __int16 *v11; // r14
  const unsigned __int16 *v12; // rbx
  ConsoleToPipeRedirector *v13; // r14
  char v14; // bl
  __int64 v15; // r15
  __int64 v16; // r13
  HANDLE v17; // rdi
  DWORD LastError; // ebx
  __int16 v19; // r12
  int ProfileBasic; // eax
  HANDLE v21; // rdi
  const char *v22; // r9
  int v23; // eax
  __int64 v24; // rdx
  ConsoleToPipeRedirector *v25; // r8
  _QWORD *v26; // rax
  __int64 v27; // rax
  __int64 **v28; // rdx
  __int64 *i; // rcx
  __int64 j; // rcx
  __int64 v31; // rax
  bool v32; // di
  int PseudoConsoleAsUser; // eax
  DWORD v34; // ebx
  DWORD v35; // ebx
  __int64 v36; // r13
  HANDLE *Console; // rcx
  HANDLE *v38; // rcx
  void *v39; // rbx
  struct _PROC_THREAD_ATTRIBUTE_LIST *v40; // rcx
  const char *v41; // r9
  char *v42; // r12
  const char *v43; // r9
  const char *v44; // r9
  const unsigned __int16 *v45; // rdx
  const WCHAR *lpCurrentDirectory; // rdi
  const WCHAR *v47; // rcx
  const char *v48; // r9
  const WCHAR *p_UserData; // rdx
  WCHAR *Ptr; // rcx
  _QWORD *ApplicationName; // rbx
  __int128 *lpEnvironment; // rax
  HANDLE v53; // rsi
  const char *v54; // r9
  HANDLE hProcess; // rbx
  HANDLE CurrentProcess; // rdi
  HANDLE v57; // rax
  const char *v58; // r9
  _DWORD *v59; // rax
  DWORD dwProcessId; // ecx
  volatile signed __int32 *v61; // rbx
  unsigned int v62; // r8d
  const char *v63; // r9
  unsigned int v64; // r8d
  const char *v65; // r9
  LPPROC_THREAD_ATTRIBUTE_LIST v66; // rcx
  int cbSize; // [rsp+20h] [rbp-E0h]
  char v69; // [rsp+60h] [rbp-A0h]
  ConsoleToPipeRedirector *v70; // [rsp+68h] [rbp-98h] BYREF
  __int64 v71; // [rsp+70h] [rbp-90h]
  __int16 v72[4]; // [rsp+78h] [rbp-88h]
  LPPROC_THREAD_ATTRIBUTE_LIST lpAttributeList; // [rsp+80h] [rbp-80h] BYREF
  HANDLE v74; // [rsp+88h] [rbp-78h]
  HANDLE v75; // [rsp+90h] [rbp-70h]
  __int64 v76; // [rsp+98h] [rbp-68h]
  char v77; // [rsp+A1h] [rbp-5Fh]
  WCHAR *v78; // [rsp+A8h] [rbp-58h] BYREF
  volatile signed __int32 *v79; // [rsp+B0h] [rbp-50h]
  HANDLE v80; // [rsp+B8h] [rbp-48h]
  LPHANDLE lpTargetHandle; // [rsp+C0h] [rbp-40h]
  HANDLE v82[2]; // [rsp+C8h] [rbp-38h] BYREF
  unsigned int v83[2]; // [rsp+D8h] [rbp-28h] BYREF
  unsigned int v84; // [rsp+E0h] [rbp-20h] BYREF
  unsigned int v85; // [rsp+E4h] [rbp-1Ch] BYREF
  HANDLE *v86; // [rsp+E8h] [rbp-18h]
  __int64 v87; // [rsp+F0h] [rbp-10h]
  __int64 v88; // [rsp+F8h] [rbp-8h]
  _QWORD Src[4]; // [rsp+100h] [rbp+0h] BYREF
  char v90[32]; // [rsp+120h] [rbp+20h] BYREF
  HANDLE v91; // [rsp+140h] [rbp+40h] BYREF
  __int64 v92; // [rsp+148h] [rbp+48h] BYREF
  struct _PROCESS_INFORMATION ProcessInformation; // [rsp+150h] [rbp+50h] BYREF
  struct _STARTUPINFOW StartupInfo; // [rsp+170h] [rbp+70h] BYREF
  LPPROC_THREAD_ATTRIBUTE_LIST v95; // [rsp+1D8h] [rbp+D8h]
  PVOID lpValue; // [rsp+1E0h] [rbp+E0h]
  HANDLE hObject; // [rsp+1E8h] [rbp+E8h] BYREF
  HANDLE v98; // [rsp+1F0h] [rbp+F0h] BYREF
  HANDLE TargetHandle; // [rsp+1F8h] [rbp+F8h] BYREF
  HANDLE hToken[2]; // [rsp+200h] [rbp+100h] BYREF
  __int64 v101; // [rsp+210h] [rbp+110h]
  __int64 v102; // [rsp+218h] [rbp+118h]
  LPVOID v103; // [rsp+220h] [rbp+120h] BYREF
  __int128 v104; // [rsp+228h] [rbp+128h] BYREF
  __int128 v105; // [rsp+238h] [rbp+138h] BYREF
  __int64 v106; // [rsp+248h] [rbp+148h]
  unsigned __int64 v107; // [rsp+250h] [rbp+150h]
  void **v108; // [rsp+260h] [rbp+160h] BYREF
  int v109; // [rsp+268h] [rbp+168h] BYREF
  char v110; // [rsp+26Ch] [rbp+16Ch]
  int v111; // [rsp+290h] [rbp+190h] BYREF
  const char *v112; // [rsp+298h] [rbp+198h]
  __int64 v113; // [rsp+2A0h] [rbp+1A0h]
  char v114; // [rsp+2A8h] [rbp+1A8h]
  int v115; // [rsp+2B0h] [rbp+1B0h]
  _BYTE v116[152]; // [rsp+2B8h] [rbp+1B8h] BYREF
  __int64 v117; // [rsp+350h] [rbp+250h]
  __int64 v118; // [rsp+358h] [rbp+258h]
  int v119; // [rsp+360h] [rbp+260h]
  __int64 v120; // [rsp+368h] [rbp+268h]
  int *v121; // [rsp+370h] [rbp+270h]
  __int64 v122; // [rsp+378h] [rbp+278h]
  __int64 v123; // [rsp+380h] [rbp+280h]
  void ***v124; // [rsp+388h] [rbp+288h]
  __int64 v125; // [rsp+390h] [rbp+290h]
  int v126; // [rsp+398h] [rbp+298h]
  int *v127; // [rsp+3A0h] [rbp+2A0h]
  char v128; // [rsp+3A8h] [rbp+2A8h]
  void **v129; // [rsp+3B0h] [rbp+2B0h] BYREF
  int v130; // [rsp+3B8h] [rbp+2B8h] BYREF
  char v131; // [rsp+3BCh] [rbp+2BCh]
  int v132; // [rsp+3E0h] [rbp+2E0h] BYREF
  const char *v133; // [rsp+3E8h] [rbp+2E8h]
  __int64 v134; // [rsp+3F0h] [rbp+2F0h]
  char v135; // [rsp+3F8h] [rbp+2F8h]
  int v136; // [rsp+400h] [rbp+300h]
  char v137[152]; // [rsp+408h] [rbp+308h] BYREF
  __int64 v138; // [rsp+4A0h] [rbp+3A0h]
  __int64 v139; // [rsp+4A8h] [rbp+3A8h]
  int v140; // [rsp+4B0h] [rbp+3B0h]
  __int64 v141; // [rsp+4B8h] [rbp+3B8h]
  int *v142; // [rsp+4C0h] [rbp+3C0h]
  __int64 v143; // [rsp+4C8h] [rbp+3C8h]
  __int64 v144; // [rsp+4D0h] [rbp+3D0h]
  void ***v145; // [rsp+4D8h] [rbp+3D8h]
  __int64 v146; // [rsp+4E0h] [rbp+3E0h]
  int v147; // [rsp+4E8h] [rbp+3E8h]
  int *v148; // [rsp+4F0h] [rbp+3F0h]
  char v149; // [rsp+4F8h] [rbp+3F8h]
  struct _EVENT_DATA_DESCRIPTOR UserData; // [rsp+500h] [rbp+400h] BYREF
  struct _EVENT_DATA_DESCRIPTOR v151; // [rsp+510h] [rbp+410h] BYREF
  struct _EVENT_DATA_DESCRIPTOR v152; // [rsp+520h] [rbp+420h] BYREF
  struct _EVENT_DATA_DESCRIPTOR v153; // [rsp+530h] [rbp+430h] BYREF
  _QWORD Value[3]; // [rsp+540h] [rbp+440h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+5A8h] [rbp+4A8h]

  lpTargetHandle = a1;
  v86 = a1;
  v70 = a6;
  v92 = -1;
  memset_0(&v129, 0, 0x150u);
  v130 = 0;
  v131 = 0;
  v135 = 0;
  v132 = 0;
  v133 = "ExecuteProcess";
  v134 = 0;
  v136 = 0;
  v138 = 0;
  v139 = 0;
  memset_0(v137, 0, sizeof(v137));
  v140 = 1;
  v141 = 0;
  v142 = &v130;
  v143 = 0;
  v144 = 0;
  v145 = &v129;
  v146 = 0;
  v147 = 0;
  v148 = &v132;
  v149 = 0;
  v129 = &CExec::Diagnostics::TraceProvider::ExecuteProcess::`vftable';
  CExec::Diagnostics::TraceProvider::ExecuteProcess::StartActivity((CExec::Diagnostics::TraceProvider::ExecuteProcess *)&v129);
  v9 = L"pipe";
  v10 = L"pipe";
  if ( !hSourceHandle )
    v10 = L"<n/a>";
  v11 = L"pipe";
  if ( !a4 )
    v11 = L"<n/a>";
  if ( !a3 )
    v9 = L"<n/a>";
  v12 = (const unsigned __int16 *)(a2 + 32);
  v78 = (WCHAR *)(a2 + 32);
  if ( *(_QWORD *)(a2 + 56) > 7u )
    v12 = *(const unsigned __int16 **)v12;
  if ( g_VmlEtwTrace )
  {
    VmCreateDataDescriptor(&v153, &v85, v10);
    VmCreateDataDescriptor(&v152, &v84, v11);
    VmCreateDataDescriptor(&v151, &v83[1], v9);
    VmCreateDataDescriptor(&UserData, v83, v12);
    v13 = 0;
    if ( g_VmlEtwTrace )
      EventWrite(*((_QWORD *)g_VmlEtwTrace + 2), &MSCEXEC_CREATE_PROCESS, 4u, &UserData);
  }
  else
  {
    v13 = 0;
  }
  v14 = *(_BYTE *)(a2 + 169);
  v69 = v14;
  TargetHandle = 0;
  CExec::ConnectStdDevicePipe(&TargetHandle, a3);
  v98 = 0;
  CExec::ConnectStdDevicePipe(&v98, a4);
  hObject = 0;
  CExec::ConnectStdDevicePipe(&hObject, hSourceHandle);
  v87 = -1;
  v88 = -1;
  *(_QWORD *)v83 = -1;
  v15 = -1;
  v74 = (HANDLE)-1LL;
  v16 = -1;
  v76 = -1;
  if ( v14 )
  {
    v15 = (__int64)TargetHandle;
    v74 = TargetHandle;
    TargetHandle = (HANDLE)-1LL;
    v16 = (__int64)v98;
    v76 = (__int64)v98;
    v98 = (HANDLE)-1LL;
    v17 = hObject;
    if ( (char *)hObject - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
    {
      LastError = GetLastError();
      CloseHandle(v17);
      SetLastError(LastError);
      v14 = v69;
    }
    hObject = (HANDLE)-1LL;
  }
  if ( *(_WORD *)(a2 + 174) )
    v72[0] = *(_WORD *)(a2 + 174);
  else
    *(_DWORD *)v72 = 25;
  if ( *(_WORD *)(a2 + 176) )
    v19 = *(_WORD *)(a2 + 176);
  else
    v19 = 80;
  v80 = 0;
  hToken[0] = 0;
  CExec::GetProcessToken(hToken, a2);
  memset_0(&v108, 0, 0x150u);
  v109 = 0;
  v110 = 0;
  v114 = 0;
  v111 = 0;
  v112 = "ExecuteProcess_LoadProfile";
  v113 = 0;
  v115 = 0;
  v117 = 0;
  v118 = 0;
  memset_0(v116, 0, sizeof(v116));
  v119 = 1;
  v120 = 0;
  v121 = &v109;
  v122 = 0;
  v123 = 0;
  v124 = &v108;
  v125 = 0;
  v126 = 0;
  v127 = &v111;
  v128 = 0;
  v108 = &CExec::Diagnostics::TraceProvider::ExecuteProcess_LoadProfile::`vftable';
  CExec::Diagnostics::TraceProvider::ExecuteProcess_LoadProfile::StartActivity((CExec::Diagnostics::TraceProvider::ExecuteProcess_LoadProfile *)&v108);
  ProfileBasic = LoadProfileBasic(hToken[0], 0);
  if ( ProfileBasic < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x35D,
      (unsigned int)"onecore\\vm\\compute\\service\\cexec\\lib\\cexecprocess.cpp",
      (const char *)(unsigned int)ProfileBasic,
      cbSize);
  v21 = hToken[0];
  v75 = hToken[0];
  hToken[0] = 0;
  v80 = v75;
  wil::ActivityBase<CExec::Diagnostics::TraceProvider,0,2,4,0,_TlgReflectorTag_Param0IsProviderType>::Stop(&v108);
  v108 = &CExec::Diagnostics::TraceProvider::ExecuteProcess_LoadProfile::`vftable';
  wil::ActivityBase<CExec::Diagnostics::TraceProvider,0,2,4,0,_TlgReflectorTag_Param0IsProviderType>::Destroy(&v108);
  wil::ActivityBase<CExec::Diagnostics::TraceProvider,0,2,4,0,_TlgReflectorTag_Param0IsProviderType>::~ActivityBase<CExec::Diagnostics::TraceProvider,0,2,4,0,_TlgReflectorTag_Param0IsProviderType>(&v108);
  if ( (unsigned __int64)hToken[0] - 1 <= 0xFFFFFFFFFFFFFFFDuLL )
    CloseHandle(hToken[0]);
  if ( !ImpersonateLoggedOnUser(v21) )
    wil::details::in1diag3::Throw_GetLastError(
      retaddr,
      (void *)0x362,
      (unsigned int)"onecore\\vm\\compute\\service\\cexec\\lib\\cexecprocess.cpp",
      v22);
  v77 = 1;
  v103 = 0;
  v23 = CreateEnvBlock(&v103, v21, 0);
  if ( v23 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x366,
      (unsigned int)"onecore\\vm\\compute\\service\\cexec\\lib\\cexecprocess.cpp",
      (const char *)(unsigned int)v23,
      cbSize);
  v105 = 0;
  v106 = 0;
  v107 = 7;
  LOWORD(v105) = 0;
  v104 = 0;
  CExec::EnvironmentBlockToMap(&v104, v103);
  v25 = v70;
  if ( *(_QWORD *)(a2 + 160) || *((_QWORD *)v70 + 2) )
  {
    CExec::UpdateEnvironmentMap(&v104, a2 + 152, v70);
    v70 = 0;
    v71 = 0;
    hToken[0] = &v70;
    hToken[1] = &v70;
    v26 = operator new(0x60u);
    *v26 = v26;
    v26[1] = v26;
    v26[2] = v26;
    *((_WORD *)v26 + 12) = 257;
    v70 = (ConsoleToPipeRedirector *)v26;
    v27 = std::_Tree<std::_Tmap_traits<std::wstring,std::wstring,Vml::CaseInsensitiveLess,std::allocator<std::pair<std::wstring const,std::wstring>>,0>>::_Copy_nodes<0>(
            &v70,
            *(_QWORD *)(v104 + 8),
            v26);
    *((_QWORD *)v70 + 1) = v27;
    v71 = *((_QWORD *)&v104 + 1);
    v28 = (__int64 **)*((_QWORD *)v70 + 1);
    if ( *((_BYTE *)v28 + 25) )
    {
      *(_QWORD *)v70 = v70;
      *((_QWORD *)v70 + 2) = v70;
    }
    else
    {
      for ( i = *v28; !*((_BYTE *)i + 25); i = (__int64 *)*i )
        v28 = (__int64 **)i;
      *(_QWORD *)v70 = v28;
      for ( j = *((_QWORD *)v70 + 1); !*(_BYTE *)(*(_QWORD *)(j + 16) + 25LL); j = *(_QWORD *)(j + 16) )
        ;
      *((_QWORD *)v70 + 2) = j;
    }
    hToken[1] = 0;
    std::_Tree_head_scoped_ptr<std::allocator<std::_Tree_node<std::pair<std::wstring const,std::wstring>,void *>>,std::_Tree_val<std::_Tree_simple_types<std::pair<std::wstring const,std::wstring>>>>::~_Tree_head_scoped_ptr<std::allocator<std::_Tree_node<std::pair<std::wstring const,std::wstring>,void *>>,std::_Tree_val<std::_Tree_simple_types<std::pair<std::wstring const,std::wstring>>>>(hToken);
    v31 = CExec::EnvironmentMapToBlock(&UserData);
    std::wstring::operator=(&v105, v31);
    std::wstring::~wstring(&UserData);
  }
  v32 = v14 && (!*(_BYTE *)(a2 + 181) || !*(_BYTE *)(a2 + 180));
  *(__m128i *)v82 = _mm_load_si128((const __m128i *)&_xmm_ffffffffffffffffffffffffffffffff);
  v70 = 0;
  lpValue = 0;
  if ( v32 )
  {
    LOWORD(hToken[0]) = v19;
    WORD1(hToken[0]) = v72[0];
    lpValue = 0;
    PseudoConsoleAsUser = CreatePseudoConsoleAsUser(v75, LODWORD(hToken[0]), v15, v16);
    if ( PseudoConsoleAsUser < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x384,
        (unsigned int)"onecore\\vm\\compute\\service\\cexec\\lib\\cexecprocess.cpp",
        (const char *)(unsigned int)PseudoConsoleAsUser,
        0);
    if ( (unsigned __int64)(v15 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
    {
      v34 = GetLastError();
      CloseHandle((HANDLE)v15);
      SetLastError(v34);
    }
    v74 = (HANDLE)-1LL;
    if ( (unsigned __int64)(v16 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
    {
      v35 = GetLastError();
      CloseHandle((HANDLE)v16);
      SetLastError(v35);
    }
    v36 = -1;
    v76 = -1;
  }
  else
  {
    Console = (HANDLE *)CreateConsole(hToken, v24, v25);
    if ( v82 != Console )
    {
      v82[0] = *Console;
      *Console = (HANDLE)-1LL;
    }
    v38 = Console + 1;
    if ( &v82[1] != v38 )
    {
      v82[1] = *v38;
      *v38 = (HANDLE)-1LL;
    }
    if ( (unsigned __int64)hToken[1] - 1 <= 0xFFFFFFFFFFFFFFFDuLL )
      CloseHandle(hToken[1]);
    if ( (unsigned __int64)hToken[0] - 1 <= 0xFFFFFFFFFFFFFFFDuLL )
      CloseHandle(hToken[0]);
    v39 = operator new(0x180u);
    hToken[0] = v39;
    memset_0(v39, 0, 0x180u);
    v13 = (ConsoleToPipeRedirector *)ConsoleToPipeRedirector::ConsoleToPipeRedirector(v39, v72[0], v19, v72[0], v19);
    v70 = v13;
    v36 = v76;
  }
  *(_QWORD *)&StartupInfo.cb = 112;
  memset_0(&StartupInfo.lpReserved, 0, 0x60u);
  v95 = 0;
  CExec::MakeAttributeList(&lpAttributeList);
  v40 = lpAttributeList;
  v95 = lpAttributeList;
  Value[0] = TargetHandle;
  Value[1] = v98;
  Value[2] = hObject;
  StartupInfo.dwFlags |= 0x100u;
  if ( !v69 )
  {
    StartupInfo.hStdInput = TargetHandle;
    StartupInfo.hStdOutput = v98;
    StartupInfo.hStdError = hObject;
    if ( !UpdateProcThreadAttribute(lpAttributeList, 0, 0x20002u, Value, 0x18u, 0, 0) )
      wil::details::in1diag3::Throw_GetLastError(
        retaddr,
        (void *)0x3AE,
        (unsigned int)"onecore\\vm\\compute\\service\\cexec\\lib\\cexecprocess.cpp",
        v41);
    v40 = lpAttributeList;
  }
  v42 = (char *)v82[1];
  if ( v32 )
  {
    v91 = 0;
    if ( !UpdateProcThreadAttribute(v40, 0, 0x20016u, lpValue, 8u, 0, 0) )
      wil::details::in1diag3::Throw_GetLastError(
        retaddr,
        (void *)0x3BB,
        (unsigned int)"onecore\\vm\\compute\\service\\cexec\\lib\\cexecprocess.cpp",
        v43);
  }
  else
  {
    v91 = v82[1];
    if ( !UpdateProcThreadAttribute(v40, 0, 0x2000Au, &v91, 8u, 0, 0) )
      wil::details::in1diag3::Throw_GetLastError(
        retaddr,
        (void *)0x3C6,
        (unsigned int)"onecore\\vm\\compute\\service\\cexec\\lib\\cexecprocess.cpp",
        v48);
  }
  if ( v92 != -1 && !UpdateProcThreadAttribute(lpAttributeList, 0, 0x2000Du, &v92, 8u, 0, 0) )
    wil::details::in1diag3::Throw_GetLastError(
      retaddr,
      (void *)0x3D1,
      (unsigned int)"onecore\\vm\\compute\\service\\cexec\\lib\\cexecprocess.cpp",
      v44);
  memset(&ProcessInformation, 0, sizeof(ProcessInformation));
  memset_0(&v108, 0, 0x150u);
  v109 = 0;
  v110 = 0;
  v114 = 0;
  v111 = 0;
  v112 = "CreateProcessAsUserW";
  v113 = 0;
  v115 = 0;
  v117 = 0;
  v118 = 0;
  memset_0(v116, 0, sizeof(v116));
  v119 = 1;
  v120 = 0;
  v121 = &v109;
  v122 = 0;
  v123 = 0;
  v124 = &v108;
  v125 = 0;
  v126 = 0;
  v127 = &v111;
  v128 = 0;
  v108 = &CExec::Diagnostics::TraceProvider::CreateProcessAsUserW::`vftable';
  CExec::Diagnostics::TraceProvider::CreateProcessAsUserW::StartActivity((CExec::Diagnostics::TraceProvider::CreateProcessAsUserW *)&v108);
  lpCurrentDirectory = (const WCHAR *)(a2 + 120);
  if ( *(_QWORD *)(a2 + 136) )
  {
    if ( *(_QWORD *)(a2 + 144) <= 7u )
      v47 = (const WCHAR *)(a2 + 120);
    else
      v47 = *(const WCHAR **)lpCurrentDirectory;
    Vml::CreateDirectoryW(v47, v45);
  }
  UserData = 0;
  v151.Ptr = 0;
  *(_QWORD *)&v151.Size = 7;
  LOWORD(UserData.Ptr) = 0;
  v152 = 0;
  v153.Ptr = 0;
  *(_QWORD *)&v153.Size = 7;
  LOWORD(v152.Ptr) = 0;
  if ( *(_QWORD *)(a2 + 24) <= 7u )
    p_UserData = (const WCHAR *)a2;
  else
    p_UserData = *(const WCHAR **)a2;
  Ptr = (WCHAR *)(a2 + 32);
  if ( *(_QWORD *)(a2 + 56) > 7u )
  {
    Ptr = *(WCHAR **)Ptr;
    v78 = Ptr;
  }
  if ( !*p_UserData )
  {
    *(_OWORD *)hToken = 0;
    v101 = 0;
    v102 = 0;
    std::wstring::_Construct<1,unsigned short const *>(hToken, L"PATH", 4);
    lpCurrentDirectory = (const WCHAR *)(a2 + 120);
    std::map<std::wstring,std::wstring,Vml::CaseInsensitiveLess,std::allocator<std::pair<std::wstring const,std::wstring>>>::operator[](
      &v104,
      hToken);
    ApplicationName = GetApplicationName(Src, (_QWORD *)(a2 + 32), a2 + 120);
    std::wstring::operator=(&UserData, ApplicationName);
    std::wstring::operator=(&v152, ApplicationName + 4);
    std::wstring::~wstring(v90);
    std::wstring::~wstring(Src);
    std::wstring::~wstring(hToken);
    p_UserData = (const WCHAR *)&UserData;
    if ( *(_QWORD *)&v151.Size > 7u )
      p_UserData = (const WCHAR *)UserData.Ptr;
    if ( v153.Ptr )
    {
      Ptr = (WCHAR *)&v152;
      if ( *(_QWORD *)&v153.Size > 7u )
        Ptr = (WCHAR *)v152.Ptr;
    }
    else
    {
      Ptr = v78;
    }
  }
  if ( *(_QWORD *)(a2 + 136) )
  {
    if ( *((_QWORD *)lpCurrentDirectory + 3) > 7u )
      lpCurrentDirectory = *(const WCHAR **)lpCurrentDirectory;
  }
  else
  {
    lpCurrentDirectory = 0;
  }
  if ( v106 )
  {
    lpEnvironment = &v105;
    if ( v107 > 7 )
      lpEnvironment = (__int128 *)v105;
  }
  else
  {
    lpEnvironment = (__int128 *)v103;
  }
  v53 = v75;
  if ( !CreateProcessAsUserW(
          v75,
          p_UserData,
          Ptr,
          0,
          0,
          1,
          0x80400u,
          lpEnvironment,
          lpCurrentDirectory,
          &StartupInfo,
          &ProcessInformation) )
    wil::details::in1diag3::Throw_GetLastError(
      retaddr,
      (void *)0x3F7,
      (unsigned int)"onecore\\vm\\compute\\service\\cexec\\lib\\cexecprocess.cpp",
      v54);
  wil::ActivityBase<CExec::Diagnostics::TraceProvider,0,2,4,0,_TlgReflectorTag_Param0IsProviderType>::Stop(&v108);
  std::wstring::~wstring(&v152);
  std::wstring::~wstring(&UserData);
  v108 = &CExec::Diagnostics::TraceProvider::CreateProcessAsUserW::`vftable';
  wil::ActivityBase<CExec::Diagnostics::TraceProvider,0,2,4,0,_TlgReflectorTag_Param0IsProviderType>::Destroy(&v108);
  wil::ActivityBase<CExec::Diagnostics::TraceProvider,0,2,4,0,_TlgReflectorTag_Param0IsProviderType>::~ActivityBase<CExec::Diagnostics::TraceProvider,0,2,4,0,_TlgReflectorTag_Param0IsProviderType>(&v108);
  hProcess = ProcessInformation.hProcess;
  v75 = ProcessInformation.hProcess;
  ProcessInformation.hProcess = 0;
  *lpTargetHandle = 0;
  CurrentProcess = GetCurrentProcess();
  v57 = GetCurrentProcess();
  if ( !DuplicateHandle(v57, hProcess, CurrentProcess, lpTargetHandle, 0x101041u, 0, 0) )
    wil::details::in1diag3::Throw_GetLastError(
      retaddr,
      (void *)0x405,
      (unsigned int)"onecore\\vm\\compute\\service\\cexec\\lib\\cexecprocess.cpp",
      v58);
  if ( v13 )
  {
    CspReadNextConsoleIo(*(_QWORD *)v13);
    ConsoleToPipeRedirector::StartRead(v13);
  }
  v59 = operator new(0x40u);
  *(_OWORD *)v59 = 0;
  v59[2] = 1;
  v59[3] = 1;
  *(_QWORD *)v59 = &std::_Ref_count_obj2<CExec::ProcessTracker>::`vftable';
  dwProcessId = ProcessInformation.dwProcessId;
  *((_QWORD *)v59 + 2) = hProcess;
  v75 = 0;
  v70 = 0;
  *((_QWORD *)v59 + 3) = v13;
  *((_QWORD *)v59 + 4) = lpValue;
  lpValue = 0;
  *((_QWORD *)v59 + 5) = v53;
  v80 = 0;
  v59[12] = dwProcessId;
  *((_QWORD *)v59 + 7) = 0;
  v78 = (WCHAR *)(v59 + 4);
  v79 = v59;
  CExec::TrackProcess(ProcessInformation.dwProcessId, &v78);
  v61 = v79;
  if ( v79 )
  {
    if ( _InterlockedExchangeAdd(v79 + 2, 0xFFFFFFFF) == 1 )
    {
      (**(void (__fastcall ***)(volatile signed __int32 *))v61)(v61);
      if ( _InterlockedExchangeAdd(v61 + 3, 0xFFFFFFFF) == 1 )
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v61 + 8LL))(v61);
    }
  }
  wil::ActivityBase<CExec::Diagnostics::TraceProvider,0,2,4,0,_TlgReflectorTag_Param0IsProviderType>::Stop(&v129);
  if ( ProcessInformation.hProcess && !CloseHandle(ProcessInformation.hProcess) )
    wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v62, v63);
  if ( ProcessInformation.hThread && !CloseHandle(ProcessInformation.hThread) )
    wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v64, v65);
  v66 = lpAttributeList;
  lpAttributeList = 0;
  if ( v66 )
    LocalFree(v66);
  if ( lpValue )
    ClosePseudoConsole();
  if ( (unsigned __int64)(v42 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
    CloseHandle(v42);
  if ( (unsigned __int64)v82[0] - 1 <= 0xFFFFFFFFFFFFFFFDuLL )
    CloseHandle(v82[0]);
  std::_Tree<std::_Tmap_traits<std::wstring,std::wstring,Vml::CaseInsensitiveLess,std::allocator<std::pair<std::wstring const,std::wstring>>,0>>::~_Tree<std::_Tmap_traits<std::wstring,std::wstring,Vml::CaseInsensitiveLess,std::allocator<std::pair<std::wstring const,std::wstring>>,0>>(&v104);
  std::wstring::~wstring(&v105);
  if ( v103 )
    DestroyEnvBlock();
  RevertToSelf();
  if ( (unsigned __int64)(v36 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
    CloseHandle((HANDLE)v36);
  if ( (char *)v74 - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
    CloseHandle(v74);
  if ( (char *)hObject - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
    CloseHandle(hObject);
  if ( (char *)v98 - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
    CloseHandle(v98);
  if ( (char *)TargetHandle - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
    CloseHandle(TargetHandle);
  v129 = &CExec::Diagnostics::TraceProvider::ExecuteProcess::`vftable';
  wil::ActivityBase<CExec::Diagnostics::TraceProvider,0,2,4,0,_TlgReflectorTag_Param0IsProviderType>::Destroy(&v129);
  wil::ActivityBase<CExec::Diagnostics::TraceProvider,0,2,4,0,_TlgReflectorTag_Param0IsProviderType>::~ActivityBase<CExec::Diagnostics::TraceProvider,0,2,4,0,_TlgReflectorTag_Param0IsProviderType>(&v129);
  return lpTargetHandle;
}

```

## disassembly

```asm
0x140016cc0  push    rbp
0x140016cc2  push    rbx
0x140016cc3  push    rsi
0x140016cc4  push    rdi
0x140016cc5  push    r12
0x140016cc7  push    r13
0x140016cc9  push    r14
0x140016ccb  push    r15
0x140016ccd  lea     rbp, [rsp-468h]
0x140016cd5  sub     rsp, 568h
0x140016cdc  mov     rax, cs:__security_cookie
0x140016ce3  xor     rax, rsp
0x140016ce6  mov     [rbp+4A0h+var_48], rax
0x140016ced  mov     r12, r9
0x140016cf0  mov     r15, r8
0x140016cf3  mov     rsi, rdx
0x140016cf6  mov     [rbp+4A0h+lpTargetHandle], rcx
0x140016cfa  mov     [rbp+4A0h+var_4B8], rcx
0x140016cfe  mov     r13, [rbp+4A0h+hSourceHandle]
0x140016d05  mov     rax, [rbp+4A0h+arg_28]
0x140016d0c  mov     [rsp+5A0h+var_538], rax
0x140016d11  xor     ebx, ebx
0x140016d13  mov     [rsp+5A0h+var_53C], ebx
0x140016d17  mov     [rbp+4A0h+var_458], 0FFFFFFFFFFFFFFFFh
0x140016d1f  xor     edx, edx; Val
0x140016d21  mov     r8d, 150h; Size
0x140016d27  lea     rcx, [rbp+4A0h+var_1F0]; void *
0x140016d2e  call    memset_0
0x140016d33  mov     [rbp+4A0h+var_1E8], ebx
0x140016d39  mov     [rbp+4A0h+var_1E4], bl
0x140016d3f  mov     [rbp+4A0h+var_1A8], bl
0x140016d45  mov     [rbp+4A0h+var_1C0], ebx
0x140016d4b  lea     rax, aExecuteprocess_0; "ExecuteProcess"
0x140016d52  mov     [rbp+4A0h+var_1B8], rax
0x140016d59  mov     [rbp+4A0h+var_1B0], rbx
0x140016d60  mov     [rbp+4A0h+var_1A0], ebx
0x140016d66  mov     [rbp+4A0h+var_100], rbx
0x140016d6d  mov     [rbp+4A0h+var_F8], rbx
0x140016d74  xor     edx, edx; Val
0x140016d76  mov     r8d, 98h; Size
0x140016d7c  lea     rcx, [rbp+4A0h+var_198]; void *
0x140016d83  call    memset_0
0x140016d88  mov     [rbp+4A0h+var_F0], 1
0x140016d92  xor     eax, eax
0x140016d94  mov     [rbp+4A0h+var_E8], rax
0x140016d9b  lea     rax, [rbp+4A0h+var_1E8]
0x140016da2  mov     [rbp+4A0h+var_E0], rax
0x140016da9  mov     [rbp+4A0h+var_D8], rbx
0x140016db0  mov     [rbp+4A0h+var_D0], rbx
0x140016db7  lea     rax, [rbp+4A0h+var_1F0]
0x140016dbe  mov     [rbp+4A0h+var_C8], rax
0x140016dc5  mov     [rbp+4A0h+var_C0], rbx
0x140016dcc  mov     [rbp+4A0h+var_B8], ebx
0x140016dd2  lea     rax, [rbp+4A0h+var_1C0]
0x140016dd9  mov     [rbp+4A0h+var_B0], rax
0x140016de0  mov     [rbp+4A0h+var_A8], bl
0x140016de6  lea     rax, ??_7ExecuteProcess@TraceProvider@Diagnostics@CExec@@6B@; const CExec::Diagnostics::TraceProvider::ExecuteProcess::`vftable'
0x140016ded  mov     [rbp+4A0h+var_1F0], rax
0x140016df4  lea     rcx, [rbp+4A0h+var_1F0]; this
0x140016dfb  call    ?StartActivity@ExecuteProcess@TraceProvider@Diagnostics@CExec@@QEAAXXZ; CExec::Diagnostics::TraceProvider::ExecuteProcess::StartActivity(void)
0x140016e00  nop
0x140016e01  lea     rax, aNA; "<n/a>"
0x140016e08  lea     rdi, aPipe; "pipe"
0x140016e0f  mov     r8, rdi
0x140016e12  test    r13, r13
0x140016e15  cmovz   r8, rax; unsigned __int16 *
0x140016e19  mov     r14, rdi
0x140016e1c  test    r12, r12
0x140016e1f  cmovz   r14, rax
0x140016e23  test    r15, r15
0x140016e26  cmovz   rdi, rax
0x140016e2a  lea     rbx, [rsi+20h]
0x140016e2e  mov     qword ptr [rbp+4A0h+var_4F8], rbx
0x140016e32  cmp     qword ptr [rbx+18h], 7
0x140016e37  jbe     short loc_140016E3C
0x140016e39  mov     rbx, [rbx]
0x140016e3c  xor     edx, edx
0x140016e3e  cmp     cs:?g_VmlEtwTrace@@3PEAU_VML_ETW_TRACE@@EA, rdx; _VML_ETW_TRACE * g_VmlEtwTrace
0x140016e45  jz      short loc_140016EBD
0x140016e47  lea     rdx, [rbp+4A0h+var_4BC]; unsigned int *
0x140016e4b  lea     rcx, [rbp+4A0h+var_70]; struct _EVENT_DATA_DESCRIPTOR *
0x140016e52  call    ?VmCreateDataDescriptor@@YAXPEAU_EVENT_DATA_DESCRIPTOR@@AEAIPEBG@Z; VmCreateDataDescriptor(_EVENT_DATA_DESCRIPTOR *,uint &,ushort const *)
0x140016e57  mov     r8, r14; unsigned __int16 *
0x140016e5a  lea     rdx, [rbp+4A0h+var_4C0]; unsigned int *
0x140016e5e  lea     rcx, [rbp+4A0h+var_80]; struct _EVENT_DATA_DESCRIPTOR *
0x140016e65  call    ?VmCreateDataDescriptor@@YAXPEAU_EVENT_DATA_DESCRIPTOR@@AEAIPEBG@Z; VmCreateDataDescriptor(_EVENT_DATA_DESCRIPTOR *,uint &,ushort const *)
0x140016e6a  mov     r8, rdi; unsigned __int16 *
0x140016e6d  lea     rdx, [rbp+4A0h+var_4C8+4]; unsigned int *
0x140016e71  lea     rcx, [rbp+4A0h+var_90]; struct _EVENT_DATA_DESCRIPTOR *
0x140016e78  call    ?VmCreateDataDescriptor@@YAXPEAU_EVENT_DATA_DESCRIPTOR@@AEAIPEBG@Z; VmCreateDataDescriptor(_EVENT_DATA_DESCRIPTOR *,uint &,ushort const *)
0x140016e7d  mov     r8, rbx; unsigned __int16 *
0x140016e80  lea     rdx, [rbp+4A0h+var_4C8]; unsigned int *
0x140016e84  lea     rcx, [rbp+4A0h+UserData]; struct _EVENT_DATA_DESCRIPTOR *
0x140016e8b  call    ?VmCreateDataDescriptor@@YAXPEAU_EVENT_DATA_DESCRIPTOR@@AEAIPEBG@Z; VmCreateDataDescriptor(_EVENT_DATA_DESCRIPTOR *,uint &,ushort const *)
0x140016e90  mov     rcx, cs:?g_VmlEtwTrace@@3PEAU_VML_ETW_TRACE@@EA; _VML_ETW_TRACE * g_VmlEtwTrace
0x140016e97  xor     r14d, r14d
0x140016e9a  test    rcx, rcx
0x140016e9d  jz      short loc_140016EC0
0x140016e9f  lea     r9, [rbp+4A0h+UserData]; UserData
0x140016ea6  lea     r8d, [r14+4]; UserDataCount
0x140016eaa  lea     rdx, MSCEXEC_CREATE_PROCESS; EventDescriptor
0x140016eb1  mov     rcx, [rcx+10h]; RegHandle
0x140016eb5  call    cs:__imp_EventWrite
0x140016ebb  jmp     short loc_140016EC0
0x140016ebd  xor     r14d, r14d
0x140016ec0  mov     bl, [rsi+0A9h]
0x140016ec6  mov     [rsp+5A0h+var_540], bl
0x140016eca  mov     [rbp+4A0h+TargetHandle], r14
0x140016ed1  mov     r9b, bl
0x140016ed4  mov     r8b, 1
0x140016ed7  mov     rdx, r15; hSourceHandle
0x140016eda  lea     rcx, [rbp+4A0h+TargetHandle]; lpTargetHandle
0x140016ee1  call    ?ConnectStdDevicePipe@CExec@@YA?AV?$unique_any_t@V?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@PEAX_N1@Z; CExec::ConnectStdDevicePipe(void *,bool,bool)
0x140016ee6  nop
0x140016ee7  mov     [rbp+4A0h+var_3B0], r14
0x140016eee  mov     r9b, bl
0x140016ef1  xor     r8d, r8d
0x140016ef4  mov     rdx, r12; hSourceHandle
0x140016ef7  lea     rcx, [rbp+4A0h+var_3B0]; lpTargetHandle
0x140016efe  call    ?ConnectStdDevicePipe@CExec@@YA?AV?$unique_any_t@V?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@PEAX_N1@Z; CExec::ConnectStdDevicePipe(void *,bool,bool)
0x140016f03  nop
0x140016f04  mov     [rbp+4A0h+hObject], r14
0x140016f0b  mov     r9b, bl
0x140016f0e  xor     r8d, r8d
0x140016f11  mov     rdx, r13; hSourceHandle
0x140016f14  lea     rcx, [rbp+4A0h+hObject]; lpTargetHandle
0x140016f1b  call    ?ConnectStdDevicePipe@CExec@@YA?AV?$unique_any_t@V?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@PEAX_N1@Z; CExec::ConnectStdDevicePipe(void *,bool,bool)
0x140016f20  nop
0x140016f21  or      r12, 0FFFFFFFFFFFFFFFFh
0x140016f25  mov     [rbp+4A0h+var_4B0], r12
0x140016f29  mov     [rbp+4A0h+var_4A8], r12
0x140016f2d  mov     qword ptr [rbp+4A0h+var_4C8], r12
0x140016f31  mov     r15, r12
0x140016f34  mov     [rbp+4A0h+var_518], r12
0x140016f38  mov     r13, r12
0x140016f3b  mov     [rbp+4A0h+var_508], r12
0x140016f3f  test    bl, bl
0x140016f41  jz      short loc_140016F9C
0x140016f43  mov     r15, [rbp+4A0h+TargetHandle]
0x140016f4a  mov     [rbp+4A0h+var_518], r15
0x140016f4e  mov     [rbp+4A0h+TargetHandle], r12
0x140016f55  mov     r13, [rbp+4A0h+var_3B0]
0x140016f5c  mov     [rbp+4A0h+var_508], r13
0x140016f60  mov     [rbp+4A0h+var_3B0], r12
0x140016f67  mov     rdi, [rbp+4A0h+hObject]
0x140016f6e  lea     rax, [rdi-1]
0x140016f72  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x140016f76  ja      short loc_140016F95
0x140016f78  call    cs:__imp_GetLastError
0x140016f7e  mov     ebx, eax
0x140016f80  mov     rcx, rdi; hObject
0x140016f83  call    cs:__imp_CloseHandle
0x140016f89  mov     ecx, ebx; dwErrCode
0x140016f8b  call    cs:__imp_SetLastError
0x140016f91  mov     bl, [rsp+5A0h+var_540]
0x140016f95  mov     [rbp+4A0h+hObject], r12
0x140016f9c  movzx   eax, word ptr [rsi+0AEh]
0x140016fa3  test    ax, ax
0x140016fa6  jnz     short loc_140016FB2
0x140016fa8  mov     dword ptr [rsp+5A0h+var_528], 19h
0x140016fb0  jmp     short loc_140016FB7
0x140016fb2  mov     [rsp+5A0h+var_528], ax
0x140016fb7  movzx   eax, word ptr [rsi+0B0h]
0x140016fbe  test    ax, ax
0x140016fc1  jnz     short loc_140016FCB
0x140016fc3  mov     r12d, 50h ; 'P'
0x140016fc9  jmp     short loc_140016FCF
0x140016fcb  movzx   r12d, ax
0x140016fcf  mov     [rbp+4A0h+var_4E8], r14
0x140016fd3  mov     [rbp+4A0h+hToken], r14
0x140016fda  mov     rdx, rsi
0x140016fdd  lea     rcx, [rbp+4A0h+hToken]
0x140016fe4  call    ?GetProcessToken@CExec@@YA?AV?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@AEBUProcessParameters@Process@Schema@@@Z; CExec::GetProcessToken(Schema::Process::ProcessParameters const &)
0x140016fe9  nop
0x140016fea  xor     edx, edx; Val
0x140016fec  mov     r8d, 150h; Size
0x140016ff2  lea     rcx, [rbp+4A0h+var_340]; void *
0x140016ff9  call    memset_0
0x140016ffe  mov     [rbp+4A0h+var_338], r14d
0x140017005  mov     [rbp+4A0h+var_334], r14b
0x14001700c  mov     [rbp+4A0h+var_2F8], r14b
0x140017013  mov     [rbp+4A0h+var_310], r14d
0x14001701a  lea     rax, aExecuteprocess; "ExecuteProcess_LoadProfile"
0x140017021  mov     [rbp+4A0h+var_308], rax
0x140017028  mov     [rbp+4A0h+var_300], r14
0x14001702f  mov     [rbp+4A0h+var_2F0], r14d
0x140017036  mov     [rbp+4A0h+var_250], r14
0x14001703d  mov     [rbp+4A0h+var_248], r14
0x140017044  xor     edx, edx; Val
0x140017046  mov     r8d, 98h; Size
0x14001704c  lea     rcx, [rbp+4A0h+var_2E8]; void *
0x140017053  call    memset_0
0x140017058  mov     [rbp+4A0h+var_240], 1
0x140017062  xor     eax, eax
0x140017064  mov     [rbp+4A0h+var_238], rax
0x14001706b  lea     rax, [rbp+4A0h+var_338]
0x140017072  mov     [rbp+4A0h+var_230], rax
0x140017079  mov     [rbp+4A0h+var_228], r14
0x140017080  mov     [rbp+4A0h+var_220], r14
0x140017087  lea     rax, [rbp+4A0h+var_340]
0x14001708e  mov     [rbp+4A0h+var_218], rax
0x140017095  mov     [rbp+4A0h+var_210], r14
0x14001709c  mov     [rbp+4A0h+var_208], r14d
0x1400170a3  lea     rax, [rbp+4A0h+var_310]
0x1400170aa  mov     [rbp+4A0h+var_200], rax
0x1400170b1  mov     [rbp+4A0h+var_1F8], r14b
0x1400170b8  lea     rax, ??_7ExecuteProcess_LoadProfile@TraceProvider@Diagnostics@CExec@@6B@; const CExec::Diagnostics::TraceProvider::ExecuteProcess_LoadProfile::`vftable'
0x1400170bf  mov     [rbp+4A0h+var_340], rax
0x1400170c6  lea     rcx, [rbp+4A0h+var_340]; this
0x1400170cd  call    ?StartActivity@ExecuteProcess_LoadProfile@TraceProvider@Diagnostics@CExec@@QEAAXXZ; CExec::Diagnostics::TraceProvider::ExecuteProcess_LoadProfile::StartActivity(void)
0x1400170d2  nop
0x1400170d3  xor     edx, edx
0x1400170d5  mov     rcx, [rbp+4A0h+hToken]
0x1400170dc  call    cs:__imp_LoadProfileBasic
0x1400170e2  mov     rcx, [rbp+4A8h]; this
0x1400170e9  test    eax, eax
0x1400170eb  js      loc_140017C51
0x1400170f1  mov     rdi, [rbp+4A0h+hToken]
0x1400170f8  mov     [rbp+4A0h+var_510], rdi
0x1400170fc  mov     [rbp+4A0h+hToken], r14
0x140017103  mov     [rbp+4A0h+var_4E8], rdi
0x140017107  lea     rcx, [rbp+4A0h+var_340]
0x14001710e  call    ?Stop@?$ActivityBase@VTraceProvider@Diagnostics@CExec@@$0A@$01$03$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXJ@Z; wil::ActivityBase<CExec::Diagnostics::TraceProvider,0,2,4,0,_TlgReflectorTag_Param0IsProviderType>::Stop(long)
0x140017113  nop
0x140017114  lea     rax, ??_7ExecuteProcess_LoadProfile@TraceProvider@Diagnostics@CExec@@6B@; const CExec::Diagnostics::TraceProvider::ExecuteProcess_LoadProfile::`vftable'
0x14001711b  mov     [rbp+4A0h+var_340], rax
0x140017122  lea     rcx, [rbp+4A0h+var_340]
0x140017129  call    ?Destroy@?$ActivityBase@VTraceProvider@Diagnostics@CExec@@$0A@$01$03$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@IEAAXXZ; wil::ActivityBase<CExec::Diagnostics::TraceProvider,0,2,4,0,_TlgReflectorTag_Param0IsProviderType>::Destroy(void)
0x14001712e  lea     rcx, [rbp+4A0h+var_340]
0x140017135  call    ??1?$ActivityBase@VTraceProvider@Diagnostics@CExec@@$0A@$01$03$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@XZ; wil::ActivityBase<CExec::Diagnostics::TraceProvider,0,2,4,0,_TlgReflectorTag_Param0IsProviderType>::~ActivityBase<CExec::Diagnostics::TraceProvider,0,2,4,0,_TlgReflectorTag_Param0IsProviderType>(void)
0x14001713a  nop
0x14001713b  mov     rcx, [rbp+4A0h+hToken]; hObject
0x140017142  lea     rax, [rcx-1]
0x140017146  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x14001714a  ja      short loc_140017152
0x14001714c  call    cs:__imp_CloseHandle
0x140017152  mov     rcx, rdi; hToken
0x140017155  call    cs:__imp_ImpersonateLoggedOnUser
0x14001715b  mov     rcx, [rbp+4A8h]; this
0x140017162  test    eax, eax
0x140017164  jz      loc_140017C66
0x14001716a  mov     [rbp+4A0h+var_4FF], 1
0x14001716e  mov     [rbp+4A0h+var_380], r14
0x140017175  xor     r8d, r8d
0x140017178  mov     rdx, rdi
0x14001717b  lea     rcx, [rbp+4A0h+var_380]
0x140017182  call    cs:__imp_CreateEnvBlock
0x140017188  mov     rcx, [rbp+4A8h]; this
0x14001718f  test    eax, eax
0x140017191  js      loc_140017C78
0x140017197  xorps   xmm0, xmm0
0x14001719a  movups  [rbp+4A0h+var_368], xmm0
0x1400171a1  mov     [rbp+4A0h+var_358], r14
0x1400171a8  mov     [rbp+4A0h+var_350], 7
0x1400171b3  mov     word ptr [rbp+4A0h+var_368], r14w
0x1400171bb  movups  [rbp+4A0h+var_378], xmm0
0x1400171c2  mov     rdx, [rbp+4A0h+var_380]
0x1400171c9  lea     rcx, [rbp+4A0h+var_378]
0x1400171d0  call    ?EnvironmentBlockToMap@CExec@@YA?AV?$map@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@UCaseInsensitiveLess@Vml@@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@@2@@std@@PEBG@Z; CExec::EnvironmentBlockToMap(ushort const *)
0x1400171d5  nop
0x1400171d6  mov     r8, [rsp+5A0h+var_538]
0x1400171db  cmp     [rsi+0A0h], r14
0x1400171e2  jnz     short loc_1400171EE
0x1400171e4  cmp     [r8+10h], r14
0x1400171e8  jz      loc_140017307
0x1400171ee  lea     rdx, [rsi+98h]
0x1400171f5  lea     rcx, [rbp+4A0h+var_378]
0x1400171fc  call    ?UpdateEnvironmentMap@CExec@@YAXAEAV?$map@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@UCaseInsensitiveLess@Vml@@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@@2@@std@@AEBV?$map@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@U?$less@X@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@@2@@3@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@3@@Z; CExec::UpdateEnvironmentMap(std::map<std::wstring,std::wstring,Vml::CaseInsensitiveLess,std::allocator<std::pair<std::wstring const,std::wstring>>> &,std::map<std::wstring,std::wstring> const &,std::wstring const &)
0x140017201  mov     [rsp+5A0h+var_538], r14
0x140017206  mov     [rsp+5A0h+var_530], r14
0x14001720b  lea     rax, [rsp+5A0h+var_538]
0x140017210  mov     [rbp+4A0h+hToken], rax
0x140017217  lea     rax, [rsp+5A0h+var_538]
0x14001721c  mov     [rbp+4A0h+hToken+8], rax
0x140017223  mov     ecx, 60h ; '`'; Size
0x140017228  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x14001722d  mov     [rax], rax
0x140017230  mov     [rax+8], rax
0x140017234  mov     [rax+10h], rax
0x140017238  mov     word ptr [rax+18h], 101h
0x14001723e  mov     [rsp+5A0h+var_538], rax
0x140017243  mov     r8, rax
0x140017246  mov     rdx, qword ptr [rbp+4A0h+var_378]
0x14001724d  mov     rdx, [rdx+8]
0x140017251  lea     rcx, [rsp+5A0h+var_538]
0x140017256  call    ??$_Copy_nodes@$0A@@?$_Tree@V?$_Tmap_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@UCaseInsensitiveLess@Vml@@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@@2@$0A@@std@@@std@@IEAAPEAU?$_Tree_node@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@PEAX@1@PEAU21@0@Z; std::_Tree<std::_Tmap_traits<std::wstring,std::wstring,Vml::CaseInsensitiveLess,std::allocator<std::pair<std::wstring const,std::wstring>>,0>>::_Copy_nodes<0>(std::_Tree_node<std::pair<std::wstring const,std::wstring>,void *> *,std::_Tree_node<std::pair<std::wstring const,std::wstring>,void *> *)
0x14001725b  mov     rcx, rax
0x14001725e  mov     rax, [rsp+5A0h+var_538]
0x140017263  mov     [rax+8], rcx
0x140017267  mov     rax, qword ptr [rbp+4A0h+var_378+8]
0x14001726e  mov     [rsp+5A0h+var_530], rax
0x140017273  mov     r8, [rsp+5A0h+var_538]
0x140017278  mov     rdx, [r8+8]
0x14001727c  cmp     [rdx+19h], r14b
0x140017280  jnz     short loc_1400172BC
0x140017282  mov     rcx, [rdx]
0x140017285  cmp     [rcx+19h], r14b
0x140017289  jnz     short loc_14001729A
0x14001728b  mov     rdx, rcx
0x14001728e  mov     rax, [rcx]
  ... truncated ...
```
