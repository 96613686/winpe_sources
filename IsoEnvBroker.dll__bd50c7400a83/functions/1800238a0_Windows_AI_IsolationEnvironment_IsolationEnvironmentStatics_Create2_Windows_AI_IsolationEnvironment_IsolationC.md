# Windows::AI::IsolationEnvironment::IsolationEnvironmentStatics::Create2(Windows::AI::IsolationEnvironment::IsolationConfigurationId,HSTRING__ *,HSTRING__ *,Windows::AI::IsolationEnvironment::IIsolationEnvironmentCreationResult * *)

- ea: `0x1800238a0`
- end: `0x180023f45`
- name: `?Create2@IsolationEnvironmentStatics@IsolationEnvironment@AI@Windows@@UEAAJW4IsolationConfigurationId@234@PEAUHSTRING__@@1PEAPEAUIIsolationEnvironmentCreationResult@234@@Z`
- size: `1701`
- prototype: ``
- caller_count: `0`
- callee_count: `22`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callees

- `0x180002520`
- `0x1800075e4`
- `0x18000a464`
- `0x18001045c`
- `0x180011e18`
- `0x180013230`
- `0x1800134e8`
- `0x18001402c`
- `0x180014128`
- `0x180014c04`
- `0x1800238a0`
- `0x180032e60`
- `0x180035700`
- `0x1800357a0`
- `0x180036fb4`
- `0x18003783c`
- `0x180039b3c`
- `0x18003a79c`
- `0x18003aa54`
- `0x18003cfc8`
- `0x18004e5cc`
- `0x180068010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180023981`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180023ad4`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180023f0b`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180023981`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180023ad4`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180023f0b`
- `api-ms-win-core-processthreads-l1-1-0!GetProcessId` at `0x180023a04`
- `api-ms-win-core-processthreads-l1-1-0!GetProcessId` at `0x180023a04`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002396d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180023ac0`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180023ef7`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002396d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180023ac0`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180023ef7`

## string_xrefs

- `0x180023910`: `onecoreuap\windows\core\isoenvbroker\lib\isoenvbrokersvc\isolationenvironmentstatics.cpp`
- `0x180023952`: `onecoreuap\windows\core\isoenvbroker\lib\isoenvbrokersvc\isolationenvironmentstatics.cpp`
- `0x180023d9e`: `onecoreuap\windows\core\isoenvbroker\lib\isoenvbrokersvc\isolationenvironmentstatics.cpp`
- `0x180023df3`: `onecoreuap\windows\core\isoenvbroker\lib\isoenvbrokersvc\isolationenvironmentstatics.cpp`
- `0x180023e59`: `onecoreuap\windows\core\isoenvbroker\lib\isoenvbrokersvc\isolationenvironmentstatics.cpp`
- `0x1800238d7`: `IsolationEnvironment::Create2 called.`
- `0x180023d88`: `onecoreuap\windows\core\isoenvbroker\lib\isoenvbrokersvc\agentuser.cpp`
- `0x180023f33`: `onecoreuap\windows\core\isoenvbroker\lib\isoenvbrokersvc\agentuser.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall Windows::AI::IsolationEnvironment::IsolationEnvironmentStatics::Create2(
        __int64 a1,
        unsigned int a2,
        __int64 a3,
        __int64 a4,
        _QWORD *a5)
{
  __int64 v9; // rcx
  unsigned int v10; // ebx
  __int64 v12; // rdx
  int CallingProcessHandle; // eax
  RTL_SRWLOCK *v14; // rcx
  HANDLE v15; // r12
  __int64 v16; // rbx
  __int64 v17; // r15
  __int64 v18; // rsi
  int v19; // eax
  volatile signed __int32 *v20; // rbx
  int v21; // esi
  RTL_SRWLOCK *v22; // rcx
  volatile signed __int32 *v23; // rbx
  volatile signed __int32 *v24; // rbx
  volatile signed __int32 *v25; // rbx
  volatile signed __int32 *v26; // rbx
  volatile signed __int32 *v27; // rbx
  __int64 v28; // rbx
  int v29; // eax
  __int64 v30; // rdx
  int v31; // eax
  int v32; // eax
  volatile signed __int32 *v33; // rbx
  RTL_SRWLOCK *v34; // rcx
  int v35; // [rsp+20h] [rbp-C1h]
  const char *v36; // [rsp+28h] [rbp-B9h]
  int AppIdentity; // [rsp+30h] [rbp-B1h] BYREF
  int v38; // [rsp+34h] [rbp-ADh] BYREF
  HANDLE hObject; // [rsp+38h] [rbp-A9h] BYREF
  PSRWLOCK SRWLock; // [rsp+40h] [rbp-A1h] BYREF
  __int64 v41; // [rsp+48h] [rbp-99h] BYREF
  __int64 v42; // [rsp+50h] [rbp-91h] BYREF
  __int128 v43; // [rsp+58h] [rbp-89h] BYREF
  __int128 v44; // [rsp+68h] [rbp-79h] BYREF
  __int128 v45; // [rsp+78h] [rbp-69h] BYREF
  WCHAR String2[16]; // [rsp+88h] [rbp-59h] BYREF
  WCHAR v47[16]; // [rsp+A8h] [rbp-39h] BYREF
  _OWORD v48[2]; // [rsp+C8h] [rbp-19h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+138h] [rbp+57h]

  Log(4u, L"IsolationEnvironment::Create2 called.");
  *a5 = 0;
  v10 = CheckCallingProcessCohort(0, 0);
  if ( (v10 & 0x80000000) != 0 )
  {
    wil::details::in1diag3::Return_HrMsg(
      retaddr,
      (void *)0x2FC,
      (unsigned int)"onecoreuap\\windows\\core\\isoenvbroker\\lib\\isoenvbrokersvc\\isolationenvironmentstatics.cpp",
      (const char *)v10,
      (int)"Calling user is not in a supported cohort",
      v36);
    return v10;
  }
  checked_srwlock::lock_exclusive(v9, &SRWLock);
  hObject = 0;
  CallingProcessHandle = ClientIdentity::GetCallingProcessHandle(a1 - 24, v12, &hObject);
  v10 = CallingProcessHandle;
  if ( CallingProcessHandle < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x306,
      (unsigned int)"onecoreuap\\windows\\core\\isoenvbroker\\lib\\isoenvbrokersvc\\isolationenvironmentstatics.cpp",
      (const char *)(unsigned int)CallingProcessHandle,
      v35);
    if ( hObject )
      CloseHandle(hObject);
    v14 = SRWLock;
    if ( SRWLock )
    {
      LODWORD(SRWLock[1].Ptr) = 0;
      ReleaseSRWLockExclusive(v14);
    }
    return v10;
  }
  GetString(v47, a3);
  GetString(String2, a4);
  v43 = 0;
  v15 = hObject;
  v16 = AgentManager::s_agentUsersInUse;
  v17 = qword_1800B9348;
  while ( v16 != v17 )
  {
    if ( (unsigned __int8)AreStringsEqual((PCNZWCH)(*(_QWORD *)v16 + 248LL), String2) )
    {
      if ( (unsigned __int8)AreStringsEqual((PCNZWCH)(*(_QWORD *)(*(_QWORD *)v16 + 48LL) + 80LL), v47) )
      {
        if ( *(_QWORD *)(*(_QWORD *)v16 + 8LL) )
        {
          v18 = *(_QWORD *)v16;
          if ( *(_DWORD *)(*(_QWORD *)(v18 + 8) + 64LL) == GetProcessId(v15) )
          {
            std::shared_ptr<ClientIdentity>::operator=(&v43, v16);
            goto LABEL_55;
          }
        }
      }
    }
    v16 += 16;
  }
  v44 = 0;
  AppIdentity = AppIdentity::QueryAppIdentity((__int64)&v44, 0);
  if ( AppIdentity < 0 )
  {
    v41 = 0;
    v38 = 1;
    v19 = Microsoft::WRL::Details::MakeAndInitialize<Windows::AI::IsolationEnvironment::EnvironmentCreationResult,Windows::AI::IsolationEnvironment::IIsolationEnvironmentCreationResult,enum Windows::AI::IsolationEnvironment::IsolationEnvironmentCreationStatus,long &,std::nullptr_t>(
            a5,
            &v38,
            &AppIdentity,
            &v41);
    v20 = (volatile signed __int32 *)*((_QWORD *)&v44 + 1);
LABEL_18:
    v21 = v19;
    if ( v20 && _InterlockedExchangeAdd(v20 + 2, 0xFFFFFFFF) == 1 )
      goto LABEL_20;
    goto LABEL_22;
  }
  v45 = 0;
  memset(v48, 0, sizeof(v48));
  std::wstring::_Construct<1,wchar_t const *>((char **)v48, &word_180096C4C, 0);
  AppIdentity = ClientIdentity::Find(v48, &v44, v47, &v45);
  std::wstring::~wstring((char **)v48);
  if ( AppIdentity < 0 )
  {
    v41 = 0;
    v38 = 4;
    v21 = Microsoft::WRL::Details::MakeAndInitialize<Windows::AI::IsolationEnvironment::EnvironmentCreationResult,Windows::AI::IsolationEnvironment::IIsolationEnvironmentCreationResult,enum Windows::AI::IsolationEnvironment::IsolationEnvironmentCreationStatus,long &,std::nullptr_t>(
            a5,
            &v38,
            &AppIdentity,
            &v41);
    v23 = (volatile signed __int32 *)*((_QWORD *)&v45 + 1);
    if ( *((_QWORD *)&v45 + 1) )
    {
      if ( _InterlockedExchangeAdd((volatile signed __int32 *)(*((_QWORD *)&v45 + 1) + 8LL), 0xFFFFFFFF) == 1 )
      {
        (**(void (__fastcall ***)(volatile signed __int32 *))v23)(v23);
        if ( _InterlockedExchangeAdd(v23 + 3, 0xFFFFFFFF) == 1 )
          (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v23 + 8LL))(v23);
      }
    }
    v20 = (volatile signed __int32 *)*((_QWORD *)&v44 + 1);
LABEL_34:
    if ( v20 && _InterlockedExchangeAdd(v20 + 2, 0xFFFFFFFF) == 1 )
    {
LABEL_20:
      (**(void (__fastcall ***)(volatile signed __int32 *))v20)(v20);
      if ( _InterlockedExchangeAdd(v20 + 3, 0xFFFFFFFF) == 1 )
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v20 + 8LL))(v20);
    }
LABEL_22:
    std::wstring::~wstring((char **)String2);
    std::wstring::~wstring((char **)v47);
    if ( hObject )
      CloseHandle(hObject);
    v22 = SRWLock;
    if ( SRWLock )
    {
      LODWORD(SRWLock[1].Ptr) = 0;
      ReleaseSRWLockExclusive(v22);
    }
    return (unsigned int)v21;
  }
  AppIdentity = AgentManager::FindActiveAgentUserByProvisionId(v45, String2, &v43);
  if ( AppIdentity < 0 )
  {
    v41 = 0;
    v38 = 3;
    v21 = Microsoft::WRL::Details::MakeAndInitialize<Windows::AI::IsolationEnvironment::EnvironmentCreationResult,Windows::AI::IsolationEnvironment::IIsolationEnvironmentCreationResult,enum Windows::AI::IsolationEnvironment::IsolationEnvironmentCreationStatus,long &,std::nullptr_t>(
            a5,
            &v38,
            &AppIdentity,
            &v41);
    v24 = (volatile signed __int32 *)*((_QWORD *)&v45 + 1);
    if ( *((_QWORD *)&v45 + 1) )
    {
      if ( _InterlockedExchangeAdd((volatile signed __int32 *)(*((_QWORD *)&v45 + 1) + 8LL), 0xFFFFFFFF) == 1 )
      {
        (**(void (__fastcall ***)(volatile signed __int32 *))v24)(v24);
        if ( _InterlockedExchangeAdd(v24 + 3, 0xFFFFFFFF) == 1 )
          (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v24 + 8LL))(v24);
      }
    }
    v25 = (volatile signed __int32 *)*((_QWORD *)&v44 + 1);
    if ( *((_QWORD *)&v44 + 1) )
    {
      if ( _InterlockedExchangeAdd((volatile signed __int32 *)(*((_QWORD *)&v44 + 1) + 8LL), 0xFFFFFFFF) == 1 )
      {
        (**(void (__fastcall ***)(volatile signed __int32 *))v25)(v25);
        if ( _InterlockedExchangeAdd(v25 + 3, 0xFFFFFFFF) == 1 )
          (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v25 + 8LL))(v25);
      }
    }
    goto LABEL_46;
  }
  v26 = (volatile signed __int32 *)*((_QWORD *)&v45 + 1);
  if ( *((_QWORD *)&v45 + 1) )
  {
    if ( !_InterlockedDecrement((volatile signed __int32 *)(*((_QWORD *)&v45 + 1) + 8LL)) )
    {
      (**(void (__fastcall ***)(volatile signed __int32 *))v26)(v26);
      if ( !_InterlockedDecrement(v26 + 3) )
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v26 + 8LL))(v26);
    }
  }
  v27 = (volatile signed __int32 *)*((_QWORD *)&v44 + 1);
  if ( *((_QWORD *)&v44 + 1) )
  {
    if ( !_InterlockedDecrement((volatile signed __int32 *)(*((_QWORD *)&v44 + 1) + 8LL)) )
    {
      (**(void (__fastcall ***)(volatile signed __int32 *))v27)(v27);
      if ( !_InterlockedDecrement(v27 + 3) )
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v27 + 8LL))(v27);
    }
  }
LABEL_55:
  v28 = v43;
  if ( *(_QWORD *)(v43 + 64) )
  {
    v41 = 0;
    v38 = -2147024713;
    AppIdentity = 1;
    v19 = Microsoft::WRL::Details::MakeAndInitialize<Windows::AI::IsolationEnvironment::EnvironmentCreationResult,Windows::AI::IsolationEnvironment::IIsolationEnvironmentCreationResult,enum Windows::AI::IsolationEnvironment::IsolationEnvironmentCreationStatus,long &,std::nullptr_t>(
            a5,
            &AppIdentity,
            &v38,
            &v41);
    v20 = (volatile signed __int32 *)*((_QWORD *)&v43 + 1);
    goto LABEL_18;
  }
  if ( !*(_QWORD *)(v43 + 8) )
  {
    v29 = ProcessConnection::Create(&hObject, v43);
    v21 = v29;
    if ( v29 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x16D,
        (unsigned int)"onecoreuap\\windows\\core\\isoenvbroker\\lib\\isoenvbrokersvc\\agentuser.cpp",
        (const char *)(unsigned int)v29,
        v35);
      v30 = 863;
LABEL_60:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v30,
        (unsigned int)"onecoreuap\\windows\\core\\isoenvbroker\\lib\\isoenvbrokersvc\\isolationenvironmentstatics.cpp",
        (const char *)(unsigned int)v21,
        v35);
LABEL_46:
      v20 = (volatile signed __int32 *)*((_QWORD *)&v43 + 1);
      goto LABEL_34;
    }
  }
  v21 = AgentUser::SetSessionConfigId(v28, a2);
  if ( v21 < 0 )
  {
    v30 = 869;
    goto LABEL_60;
  }
  v42 = 0;
  v31 = Microsoft::WRL::Details::MakeAndInitialize<Windows::AI::IsolationEnvironment::IsolationEnvironment,Windows::AI::IsolationEnvironment::IIsolationEnvironment,std::shared_ptr<AgentUser> &,std::shared_ptr<ClientIdentity> const &>(
          &v42,
          &v43,
          (_QWORD *)(v28 + 48));
  v21 = v31;
  if ( v31 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x36C,
      (unsigned int)"onecoreuap\\windows\\core\\isoenvbroker\\lib\\isoenvbrokersvc\\isolationenvironmentstatics.cpp",
      (const char *)(unsigned int)v31,
      v35);
    if ( v42 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v42 + 16LL))(v42);
    goto LABEL_46;
  }
  v41 = v42;
  v38 = 0;
  AppIdentity = 0;
  v32 = Microsoft::WRL::Details::MakeAndInitialize<Windows::AI::IsolationEnvironment::EnvironmentCreationResult,Windows::AI::IsolationEnvironment::IIsolationEnvironmentCreationResult,enum Windows::AI::IsolationEnvironment::IsolationEnvironmentCreationStatus,long &,std::nullptr_t>(
          a5,
          &AppIdentity,
          &v38,
          &v41);
  v21 = v32;
  if ( v32 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x373,
      (unsigned int)"onecoreuap\\windows\\core\\isoenvbroker\\lib\\isoenvbrokersvc\\isolationenvironmentstatics.cpp",
      (const char *)(unsigned int)v32,
      v35);
    if ( v42 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v42 + 16LL))(v42);
    goto LABEL_46;
  }
  if ( v42 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v42 + 16LL))(v42);
  v33 = (volatile signed __int32 *)*((_QWORD *)&v43 + 1);
  if ( *((_QWORD *)&v43 + 1) )
  {
    if ( _InterlockedExchangeAdd((volatile signed __int32 *)(*((_QWORD *)&v43 + 1) + 8LL), 0xFFFFFFFF) == 1 )
    {
      (**(void (__fastcall ***)(volatile signed __int32 *))v33)(v33);
      if ( _InterlockedExchangeAdd(v33 + 3, 0xFFFFFFFF) == 1 )
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v33 + 8LL))(v33);
    }
  }
  std::wstring::~wstring((char **)String2);
  std::wstring::~wstring((char **)v47);
  if ( hObject )
    CloseHandle(hObject);
  v34 = SRWLock;
  if ( SRWLock )
  {
    LODWORD(SRWLock[1].Ptr) = 0;
    ReleaseSRWLockExclusive(v34);
  }
  return 0;
}

```

## disassembly

```asm
0x1800238a0  push    rbp
0x1800238a2  push    rbx
0x1800238a3  push    rsi
0x1800238a4  push    rdi
0x1800238a5  push    r12
0x1800238a7  push    r13
0x1800238a9  push    r14
0x1800238ab  push    r15
0x1800238ad  lea     rbp, [rsp-17h]
0x1800238b2  sub     rsp, 0F8h
0x1800238b9  mov     rax, cs:__security_cookie
0x1800238c0  xor     rax, rsp
0x1800238c3  mov     [rbp+4Fh+var_48], rax
0x1800238c7  mov     r15, r9
0x1800238ca  mov     rsi, r8
0x1800238cd  mov     r13d, edx
0x1800238d0  mov     rdi, rcx
0x1800238d3  mov     r14, [rbp+4Fh+arg_20]
0x1800238d7  lea     rdx, aIsolationenvir_13; "IsolationEnvironment::Create2 called."
0x1800238de  mov     ecx, 4; unsigned __int8
0x1800238e3  call    ?Log@@YAXEPEB_WZZ; Log(uchar,wchar_t const *,...)
0x1800238e8  xor     r12d, r12d
0x1800238eb  mov     [r14], r12
0x1800238ee  xor     edx, edx; enum Windows::AI::IsolationEnvironment::IsolationUserCohortKind *
0x1800238f0  xor     ecx, ecx; bool
0x1800238f2  call    ?CheckCallingProcessCohort@@YAJ_NPEAW4IsolationUserCohortKind@IsolationEnvironment@AI@Windows@@@Z; CheckCallingProcessCohort(bool,Windows::AI::IsolationEnvironment::IsolationUserCohortKind *)
0x1800238f7  mov     ebx, eax
0x1800238f9  test    eax, eax
0x1800238fb  jns     short loc_180023928
0x1800238fd  mov     rcx, [rbp+57h]; this
0x180023901  lea     rax, aCallingUserIsN; "Calling user is not in a supported coho"...
0x180023908  mov     qword ptr [rsp+130h+var_110], rax; int
0x18002390d  mov     r9d, ebx; char *
0x180023910  lea     r8, aOnecoreuapWind_18; "onecoreuap\\windows\\core\\isoenvbroker"...
0x180023917  mov     edx, 2FCh; void *
0x18002391c  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x180023921  mov     eax, ebx
0x180023923  jmp     loc_180023F13
0x180023928  lea     rdx, [rsp+130h+SRWLock]
0x18002392d  call    ?lock_exclusive@checked_srwlock@@QEAA?AV?$holder@UExclusiveTag@checked_srwlock@@UAcquireTag@2@$0A@@1@XZ; checked_srwlock::lock_exclusive(void)
0x180023932  mov     [rsp+130h+hObject], r12
0x180023937  lea     rcx, [rdi-18h]
0x18002393b  lea     r8, [rsp+130h+hObject]
0x180023940  call    ?GetCallingProcessHandle@ClientIdentity@@SAJPEAUIUnknown@@KAEAV?$unique_any_t@V?$unique_storage@U?$handle_null_only_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@@Z; ClientIdentity::GetCallingProcessHandle(IUnknown *,ulong,wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_only_resource_policy<int (*)(void *),&CloseHandle(void *)>>> &)
0x180023945  mov     ebx, eax
0x180023947  test    eax, eax
0x180023949  jns     short loc_180023989
0x18002394b  mov     rcx, [rbp+57h]; this
0x18002394f  mov     r9d, eax; char *
0x180023952  lea     r8, aOnecoreuapWind_18; "onecoreuap\\windows\\core\\isoenvbroker"...
0x180023959  mov     edx, 306h; void *
0x18002395e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180023963  mov     rcx, [rsp+130h+hObject]; hObject
0x180023968  test    rcx, rcx
0x18002396b  jz      short loc_180023973
0x18002396d  call    cs:__imp_CloseHandle
0x180023973  mov     rcx, [rsp+130h+SRWLock]; SRWLock
0x180023978  test    rcx, rcx
0x18002397b  jz      short loc_180023921
0x18002397d  mov     [rcx+8], r12d
0x180023981  call    cs:__imp_ReleaseSRWLockExclusive
0x180023987  jmp     short loc_180023921
0x180023989  mov     rdx, rsi
0x18002398c  lea     rcx, [rbp+4Fh+var_88]
0x180023990  call    ?GetString@@YA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@PEAUHSTRING__@@@Z; GetString(HSTRING__ *)
0x180023995  mov     rdx, r15
0x180023998  lea     rcx, [rbp+4Fh+String2]
0x18002399c  call    ?GetString@@YA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@PEAUHSTRING__@@@Z; GetString(HSTRING__ *)
0x1800239a1  xorps   xmm0, xmm0
0x1800239a4  movdqu  [rsp+130h+var_D8], xmm0
0x1800239aa  mov     r12, [rsp+130h+hObject]
0x1800239af  mov     rbx, cs:?s_agentUsersInUse@AgentManager@@0V?$vector@V?$shared_ptr@VAgentUser@@@std@@V?$allocator@V?$shared_ptr@VAgentUser@@@std@@@2@@std@@A; std::vector<std::shared_ptr<AgentUser>> AgentManager::s_agentUsersInUse
0x1800239b6  mov     r15, cs:qword_1800B9348
0x1800239bd  or      edi, 0FFFFFFFFh
0x1800239c0  jmp     short loc_180023A1B
0x1800239c2  mov     rcx, [rbx]
0x1800239c5  add     rcx, 0F8h; lpString1
0x1800239cc  mov     r8b, 1
0x1800239cf  lea     rdx, [rbp+4Fh+String2]; lpString2
0x1800239d3  call    ?AreStringsEqual@@YA_NAEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@0_N@Z; AreStringsEqual(std::wstring const &,std::wstring const &,bool)
0x1800239d8  test    al, al
0x1800239da  jz      short loc_180023A17
0x1800239dc  mov     rax, [rbx]
0x1800239df  mov     rcx, [rax+30h]
0x1800239e3  add     rcx, 50h ; 'P'; lpString1
0x1800239e7  mov     r8b, 1
0x1800239ea  lea     rdx, [rbp+4Fh+var_88]; lpString2
0x1800239ee  call    ?AreStringsEqual@@YA_NAEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@0_N@Z; AreStringsEqual(std::wstring const &,std::wstring const &,bool)
0x1800239f3  test    al, al
0x1800239f5  jz      short loc_180023A17
0x1800239f7  mov     rsi, [rbx]
0x1800239fa  cmp     qword ptr [rsi+8], 0
0x1800239ff  jz      short loc_180023A17
0x180023a01  mov     rcx, r12; Process
0x180023a04  call    cs:__imp_GetProcessId
0x180023a0a  mov     rcx, [rsi+8]
0x180023a0e  cmp     [rcx+40h], eax
0x180023a11  jz      loc_180023AE1
0x180023a17  add     rbx, 10h
0x180023a1b  cmp     rbx, r15
0x180023a1e  jnz     short loc_1800239C2
0x180023a20  xorps   xmm0, xmm0
0x180023a23  movdqu  [rbp+4Fh+var_C8], xmm0
0x180023a28  xor     edx, edx
0x180023a2a  lea     rcx, [rbp+4Fh+var_C8]
0x180023a2e  call    ?QueryAppIdentity@AppIdentity@@SAJAEAV?$shared_ptr@VAppIdentity@@@std@@PEAW4IsolationQueryAppIdentityStatus@IsolationEnvironment@AI@Windows@@@Z; AppIdentity::QueryAppIdentity(std::shared_ptr<AppIdentity> &,Windows::AI::IsolationEnvironment::IsolationQueryAppIdentityStatus *)
0x180023a33  mov     [rsp+130h+var_100], eax
0x180023a37  xor     r15d, r15d
0x180023a3a  test    eax, eax
0x180023a3c  jns     loc_180023AF6
0x180023a42  mov     [rsp+130h+var_E8], r15
0x180023a47  mov     [rsp+130h+var_FC], 1
0x180023a4f  lea     r9, [rsp+130h+var_E8]
0x180023a54  lea     r8, [rsp+130h+var_100]
0x180023a59  lea     rdx, [rsp+130h+var_FC]
0x180023a5e  mov     rcx, r14
0x180023a61  call    ??$MakeAndInitialize@VEnvironmentCreationResult@IsolationEnvironment@AI@Windows@@UIIsolationEnvironmentCreationResult@234@W4IsolationEnvironmentCreationStatus@234@AEAJ$$T@Details@WRL@Microsoft@@YAJPEAPEAUIIsolationEnvironmentCreationResult@IsolationEnvironment@AI@Windows@@$$QEAW4IsolationEnvironmentCreationStatus@456@AEAJ$$QEA$$T@Z
0x180023a66  mov     rbx, qword ptr [rbp+4Fh+var_C8+8]
0x180023a6a  test    rbx, rbx
0x180023a6d  mov     esi, eax
0x180023a6f  jz      short loc_180023AA4
0x180023a71  mov     ecx, edi
0x180023a73  lock xadd [rbx+8], ecx
0x180023a78  add     ecx, edi
0x180023a7a  jnz     short loc_180023AA4
0x180023a7c  mov     rdx, [rbx]
0x180023a7f  mov     rax, [rdx]
0x180023a82  mov     rcx, rbx
0x180023a85  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180023a8a  mov     eax, edi
0x180023a8c  lock xadd [rbx+0Ch], eax
0x180023a91  add     eax, edi
0x180023a93  jnz     short loc_180023AA4
0x180023a95  mov     rax, [rbx]
0x180023a98  mov     rcx, rbx
0x180023a9b  mov     rax, [rax+8]
0x180023a9f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180023aa4  lea     rcx, [rbp+4Fh+String2]
0x180023aa8  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180023aad  lea     rcx, [rbp+4Fh+var_88]
0x180023ab1  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180023ab6  mov     rcx, [rsp+130h+hObject]; hObject
0x180023abb  test    rcx, rcx
0x180023abe  jz      short loc_180023AC6
0x180023ac0  call    cs:__imp_CloseHandle
0x180023ac6  mov     rcx, [rsp+130h+SRWLock]; SRWLock
0x180023acb  test    rcx, rcx
0x180023ace  jz      short loc_180023ADA
0x180023ad0  mov     [rcx+8], r15d
0x180023ad4  call    cs:__imp_ReleaseSRWLockExclusive
0x180023ada  mov     eax, esi
0x180023adc  jmp     loc_180023F13
0x180023ae1  mov     rdx, rbx
0x180023ae4  lea     rcx, [rsp+130h+var_D8]
0x180023ae9  call    ??4?$shared_ptr@VClientIdentity@@@std@@QEAAAEAV01@AEBV01@@Z; std::shared_ptr<ClientIdentity>::operator=(std::shared_ptr<ClientIdentity> const &)
0x180023aee  xor     r15d, r15d
0x180023af1  jmp     loc_180023D16
0x180023af6  xorps   xmm0, xmm0
0x180023af9  movdqu  [rbp+4Fh+var_B8], xmm0
0x180023afe  movups  [rbp+4Fh+var_68], xmm0
0x180023b02  xorps   xmm1, xmm1
0x180023b05  movdqu  [rbp+4Fh+var_58], xmm1
0x180023b0a  xor     r8d, r8d
0x180023b0d  lea     rdx, word_180096C4C
0x180023b14  lea     rcx, [rbp+4Fh+var_68]
0x180023b18  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x180023b1d  lea     r9, [rbp+4Fh+var_B8]
0x180023b21  lea     r8, [rbp+4Fh+var_88]
0x180023b25  lea     rdx, [rbp+4Fh+var_C8]
0x180023b29  lea     rcx, [rbp+4Fh+var_68]
0x180023b2d  call    ?Find@ClientIdentity@@SAJAEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEBV?$shared_ptr@VAppIdentity@@@3@0AEAV?$shared_ptr@VClientIdentity@@@3@@Z; ClientIdentity::Find(std::wstring const &,std::shared_ptr<AppIdentity> const &,std::wstring const &,std::shared_ptr<ClientIdentity> &)
0x180023b32  mov     ebx, eax
0x180023b34  mov     [rsp+130h+var_100], eax
0x180023b38  lea     rcx, [rbp+4Fh+var_68]
0x180023b3c  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180023b41  test    ebx, ebx
0x180023b43  jns     loc_180023BD5
0x180023b49  mov     [rsp+130h+var_E8], r15
0x180023b4e  mov     [rsp+130h+var_FC], 4
0x180023b56  lea     r9, [rsp+130h+var_E8]
0x180023b5b  lea     r8, [rsp+130h+var_100]
0x180023b60  lea     rdx, [rsp+130h+var_FC]
0x180023b65  mov     rcx, r14
0x180023b68  call    ??$MakeAndInitialize@VEnvironmentCreationResult@IsolationEnvironment@AI@Windows@@UIIsolationEnvironmentCreationResult@234@W4IsolationEnvironmentCreationStatus@234@AEAJ$$T@Details@WRL@Microsoft@@YAJPEAPEAUIIsolationEnvironmentCreationResult@IsolationEnvironment@AI@Windows@@$$QEAW4IsolationEnvironmentCreationStatus@456@AEAJ$$QEA$$T@Z
0x180023b6d  mov     esi, eax
0x180023b6f  or      edi, 0FFFFFFFFh
0x180023b72  mov     rbx, qword ptr [rbp+4Fh+var_B8+8]
0x180023b76  test    rbx, rbx
0x180023b79  jz      short loc_180023BAE
0x180023b7b  mov     ecx, edi
0x180023b7d  lock xadd [rbx+8], ecx
0x180023b82  add     ecx, edi
0x180023b84  jnz     short loc_180023BAE
0x180023b86  mov     rdx, [rbx]
0x180023b89  mov     rcx, rbx
0x180023b8c  mov     rax, [rdx]
0x180023b8f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180023b94  mov     eax, edi
0x180023b96  lock xadd [rbx+0Ch], eax
0x180023b9b  add     eax, edi
0x180023b9d  jnz     short loc_180023BAE
0x180023b9f  mov     rax, [rbx]
0x180023ba2  mov     rcx, rbx
0x180023ba5  mov     rax, [rax+8]
0x180023ba9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180023bae  mov     rbx, qword ptr [rbp+4Fh+var_C8+8]
0x180023bb2  test    rbx, rbx
0x180023bb5  jz      loc_180023AA4
0x180023bbb  mov     eax, edi
0x180023bbd  lock xadd [rbx+8], eax
0x180023bc2  add     eax, edi
0x180023bc4  jnz     loc_180023AA4
0x180023bca  mov     rax, [rbx]
0x180023bcd  mov     rax, [rax]
0x180023bd0  jmp     loc_180023A82
0x180023bd5  lea     r8, [rsp+130h+var_D8]
0x180023bda  lea     rdx, [rbp+4Fh+String2]
0x180023bde  mov     rcx, qword ptr [rbp+4Fh+var_B8]
0x180023be2  call    ?FindActiveAgentUserByProvisionId@AgentManager@@SAJPEBVClientIdentity@@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAV?$shared_ptr@VAgentUser@@@4@@Z; AgentManager::FindActiveAgentUserByProvisionId(ClientIdentity const *,std::wstring const &,std::shared_ptr<AgentUser> &)
0x180023be7  mov     [rsp+130h+var_100], eax
0x180023beb  test    eax, eax
0x180023bed  jns     loc_180023C9E
0x180023bf3  mov     [rsp+130h+var_E8], r15
0x180023bf8  mov     [rsp+130h+var_FC], 3
0x180023c00  lea     r9, [rsp+130h+var_E8]
0x180023c05  lea     r8, [rsp+130h+var_100]
0x180023c0a  lea     rdx, [rsp+130h+var_FC]
0x180023c0f  mov     rcx, r14
0x180023c12  call    ??$MakeAndInitialize@VEnvironmentCreationResult@IsolationEnvironment@AI@Windows@@UIIsolationEnvironmentCreationResult@234@W4IsolationEnvironmentCreationStatus@234@AEAJ$$T@Details@WRL@Microsoft@@YAJPEAPEAUIIsolationEnvironmentCreationResult@IsolationEnvironment@AI@Windows@@$$QEAW4IsolationEnvironmentCreationStatus@456@AEAJ$$QEA$$T@Z
0x180023c17  mov     esi, eax
0x180023c19  or      edi, 0FFFFFFFFh
0x180023c1c  mov     rbx, qword ptr [rbp+4Fh+var_B8+8]
0x180023c20  test    rbx, rbx
0x180023c23  jz      short loc_180023C58
0x180023c25  mov     ecx, edi
0x180023c27  lock xadd [rbx+8], ecx
0x180023c2c  add     ecx, edi
0x180023c2e  jnz     short loc_180023C58
0x180023c30  mov     rdx, [rbx]
0x180023c33  mov     rcx, rbx
0x180023c36  mov     rax, [rdx]
0x180023c39  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180023c3e  mov     eax, edi
0x180023c40  lock xadd [rbx+0Ch], eax
0x180023c45  add     eax, edi
0x180023c47  jnz     short loc_180023C58
0x180023c49  mov     rax, [rbx]
0x180023c4c  mov     rcx, rbx
0x180023c4f  mov     rax, [rax+8]
0x180023c53  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180023c58  mov     rbx, qword ptr [rbp+4Fh+var_C8+8]
0x180023c5c  test    rbx, rbx
0x180023c5f  jz      short loc_180023C94
0x180023c61  mov     eax, edi
0x180023c63  lock xadd [rbx+8], eax
0x180023c68  add     eax, edi
0x180023c6a  jnz     short loc_180023C94
0x180023c6c  mov     rax, [rbx]
0x180023c6f  mov     rcx, rbx
0x180023c72  mov     rax, [rax]
0x180023c75  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180023c7a  mov     eax, edi
0x180023c7c  lock xadd [rbx+0Ch], eax
0x180023c81  add     eax, edi
0x180023c83  jnz     short loc_180023C94
0x180023c85  mov     rax, [rbx]
0x180023c88  mov     rcx, rbx
0x180023c8b  mov     rax, [rax+8]
0x180023c8f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180023c94  mov     rbx, qword ptr [rsp+130h+var_D8+8]
0x180023c99  jmp     loc_180023BB2
0x180023c9e  mov     rbx, qword ptr [rbp+4Fh+var_B8+8]
0x180023ca2  test    rbx, rbx
0x180023ca5  jz      short loc_180023CDA
0x180023ca7  mov     eax, edi
0x180023ca9  lock xadd [rbx+8], eax
0x180023cae  add     eax, edi
0x180023cb0  jnz     short loc_180023CDA
0x180023cb2  mov     rax, [rbx]
0x180023cb5  mov     rcx, rbx
0x180023cb8  mov     rax, [rax]
0x180023cbb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180023cc0  mov     eax, edi
0x180023cc2  lock xadd [rbx+0Ch], eax
0x180023cc7  add     eax, edi
0x180023cc9  jnz     short loc_180023CDA
0x180023ccb  mov     rax, [rbx]
0x180023cce  mov     rcx, rbx
0x180023cd1  mov     rax, [rax+8]
0x180023cd5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180023cda  mov     rbx, qword ptr [rbp+4Fh+var_C8+8]
0x180023cde  test    rbx, rbx
0x180023ce1  jz      short loc_180023D16
0x180023ce3  mov     eax, edi
0x180023ce5  lock xadd [rbx+8], eax
0x180023cea  add     eax, edi
0x180023cec  jnz     short loc_180023D16
0x180023cee  mov     rax, [rbx]
0x180023cf1  mov     rcx, rbx
0x180023cf4  mov     rax, [rax]
  ... truncated ...
```
