# Microsoft::DiagnosticsHub::StandardCollector::EtwCollectionSessionController::EtwCollectionSessionController(IStandardCollectorClientDelegate *,SessionConfiguration const &,Microsoft::DiagnosticsHub::StandardCollector::IGuidUsageTracker &,std::shared_ptr<Microsoft::DiagnosticsHub::StandardCollector::SecuredDirectory>,void *)

- ea: `0x18001a850`
- end: `0x18001aef9`
- name: `??0EtwCollectionSessionController@StandardCollector@DiagnosticsHub@Microsoft@@QEAA@PEAUIStandardCollectorClientDelegate@@AEBUSessionConfiguration@@AEAVIGuidUsageTracker@123@V?$shared_ptr@VSecuredDirectory@StandardCollector@DiagnosticsHub@Microsoft@@@std@@PEAX@Z`
- size: `1705`
- prototype: ``
- caller_count: `1`
- callee_count: `15`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x1800090a0`

## callees

- `0x180009298`
- `0x18000a524`
- `0x18001662c`
- `0x180019210`
- `0x180019a50`
- `0x18001a850`
- `0x180027d7c`
- `0x18002d9a4`
- `0x18003d864`
- `0x180043040`
- `0x180049b50`
- `0x18004a03c`
- `0x18004a088`
- `0x18004ad58`
- `0x18004b640`

## import_xrefs

- `KERNEL32!InitializeCriticalSectionAndSpinCount` at `0x18001ab37`
- `KERNEL32!InitializeCriticalSectionAndSpinCount` at `0x18001ab37`
- `KERNEL32!InitializeSRWLock` at `0x18001a93d`
- `KERNEL32!InitializeSRWLock` at `0x18001aaec`
- `KERNEL32!InitializeSRWLock` at `0x18001a93d`
- `KERNEL32!InitializeSRWLock` at `0x18001aaec`
- `KERNEL32!InitializeCriticalSection` at `0x18001ab55`
- `KERNEL32!InitializeCriticalSection` at `0x18001ab55`
- `ole32!CoCreateGuid` at `0x18001a9b9`
- `ole32!CoCreateGuid` at `0x18001a9b9`
- `ole32!StringFromGUID2` at `0x18001abe9`
- `ole32!StringFromGUID2` at `0x18001abe9`
- `ADVAPI32!RegCloseKey` at `0x18001ae40`
- `ADVAPI32!RegCloseKey` at `0x18001ae40`
- `ADVAPI32!EventRegister` at `0x18001a9d2`
- `ADVAPI32!EventRegister` at `0x18001a9d2`
- `ADVAPI32!RegQueryValueExW` at `0x18001ac64`
- `ADVAPI32!RegQueryValueExW` at `0x18001accf`
- `ADVAPI32!RegQueryValueExW` at `0x18001ad18`
- `ADVAPI32!RegQueryValueExW` at `0x18001ad61`
- `ADVAPI32!RegQueryValueExW` at `0x18001adae`
- `ADVAPI32!RegQueryValueExW` at `0x18001ac64`
- `ADVAPI32!RegQueryValueExW` at `0x18001accf`
- `ADVAPI32!RegQueryValueExW` at `0x18001ad18`
- `ADVAPI32!RegQueryValueExW` at `0x18001ad61`
- `ADVAPI32!RegQueryValueExW` at `0x18001adae`

## string_xrefs

- `0x18001acc5`: `Collector.HeapSessionAttemptTimeoutInMs`
- `0x18001ad0e`: `Collector.HeapSessionAttemptCount`
- `0x18001ada4`: `Collector.DoNotDeleteRawEtl`

## pseudocode

```c
// Hidden C++ exception states: #wind=19
__int64 __fastcall Microsoft::DiagnosticsHub::StandardCollector::EtwCollectionSessionController::EtwCollectionSessionController(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        __int64 a4,
        HKEY *a5,
        __int64 a6)
{
  _QWORD *v8; // rax
  _QWORD *v9; // rax
  HRESULT Guid; // eax
  const struct SessionConfiguration *v11; // rdx
  unsigned int v12; // edx
  _QWORD *v13; // rax
  unsigned __int16 v14; // cx
  unsigned __int16 v15; // r8
  __int64 v16; // rdi
  HKEY v17; // rdx
  unsigned int v18; // r9d
  int v19; // eax
  HKEY v20; // rbx
  bool v21; // r9
  unsigned __int16 *v22; // rdx
  unsigned __int16 v23; // ax
  unsigned __int16 *v24; // rax
  int v25; // eax
  volatile signed __int32 *v26; // rbx
  HKEY hKey[2]; // [rsp+30h] [rbp-D0h] BYREF
  __int64 v29; // [rsp+40h] [rbp-C0h]
  __int64 v30; // [rsp+48h] [rbp-B8h]
  HKEY *v31; // [rsp+50h] [rbp-B0h]
  DWORD cbData; // [rsp+58h] [rbp-A8h] BYREF
  DWORD Type; // [rsp+5Ch] [rbp-A4h] BYREF
  BYTE v34[8]; // [rsp+60h] [rbp-A0h] BYREF
  BYTE v35[8]; // [rsp+68h] [rbp-98h] BYREF
  BYTE pExceptionObject[8]; // [rsp+70h] [rbp-90h] BYREF
  BYTE Data[4]; // [rsp+78h] [rbp-88h] BYREF
  BYTE lpData[4]; // [rsp+7Ch] [rbp-84h] BYREF
  OLECHAR sz[39]; // [rsp+80h] [rbp-80h] BYREF
  unsigned __int16 v40[73]; // [rsp+CEh] [rbp-32h] BYREF

  *(_QWORD *)pExceptionObject = a4;
  v30 = a1;
  v31 = a5;
  hKey[0] = *a5;
  hKey[1] = a5[1];
  *a5 = 0;
  a5[1] = 0;
  Microsoft::DiagnosticsHub::StandardCollector::CollectionSessionController::CollectionSessionController(
    a1,
    a2,
    a3,
    hKey,
    a6);
  *(_QWORD *)v34 = a1 + 1048;
  *(_QWORD *)(a1 + 1048) = &Microsoft::DiagnosticsHub::StandardCollector::EtwCollectionProcessFilter::`vftable';
  *(_DWORD *)(a1 + 1056) = -1;
  *(_QWORD *)(a1 + 1064) = 0;
  *(_QWORD *)(a1 + 1072) = 0;
  v8 = operator new(0x20u);
  *v8 = v8;
  v8[1] = v8;
  v8[2] = v8;
  *((_WORD *)v8 + 12) = 257;
  *(_QWORD *)(a1 + 1064) = v8;
  *(_QWORD *)(a1 + 1080) = 0;
  *(_QWORD *)(a1 + 1088) = 0;
  v9 = operator new(0x20u);
  *v9 = v9;
  v9[1] = v9;
  v9[2] = v9;
  *((_WORD *)v9 + 12) = 257;
  *(_QWORD *)(a1 + 1080) = v9;
  InitializeSRWLock((PSRWLOCK)(a1 + 1096));
  *(_QWORD *)v34 = a1 + 1104;
  *(_QWORD *)(a1 + 1104) = &Microsoft::DiagnosticsHub::StandardCollector::EtwCollectionSyncController::`vftable';
  `eh vector constructor iterator'(
    (void *)(a1 + 1112),
    0x18u,
    0x20u,
    (void (*)(void *))Microsoft::DiagnosticsHub::StandardCollector::EtwCollectionSyncController::SyncEventContainer::SyncEventContainer,
    (void (*)(void *))Microsoft::DiagnosticsHub::StandardCollector::EtwCollectionSyncController::SyncEventContainer::~SyncEventContainer);
  `eh vector constructor iterator'(
    (void *)(a1 + 1880),
    0x18u,
    0x20u,
    (void (*)(void *))Microsoft::DiagnosticsHub::StandardCollector::EtwCollectionSyncController::SyncEventContainer::SyncEventContainer,
    (void (*)(void *))Microsoft::DiagnosticsHub::StandardCollector::EtwCollectionSyncController::SyncEventContainer::~SyncEventContainer);
  *(_QWORD *)(a1 + 2664) = 0;
  Guid = CoCreateGuid((GUID *)(a1 + 2648));
  if ( Guid )
  {
    cbData = Guid;
    throw (long *)&cbData;
  }
  EventRegister((LPCGUID)(a1 + 2648), 0, 0, (PREGHANDLE)(a1 + 2664));
  Microsoft::DiagnosticsHub::StandardCollector::EtwCollectionRecommendedSettings::EtwCollectionRecommendedSettings(
    (Microsoft::DiagnosticsHub::StandardCollector::EtwCollectionRecommendedSettings *)(a1 + 2672),
    v11);
  Microsoft::DiagnosticsHub::StandardCollector::EtwCollectionRundownController::EtwCollectionRundownController(
    (Microsoft::DiagnosticsHub::StandardCollector::EtwCollectionRundownController *)(a1 + 2752),
    v12);
  *(_QWORD *)a1 = &Microsoft::DiagnosticsHub::StandardCollector::EtwCollectionSessionController::`vftable'{for `ICollectionSessionController'};
  *(_QWORD *)(a1 + 8) = &Microsoft::DiagnosticsHub::StandardCollector::EtwCollectionSessionController::`vftable'{for `Microsoft::DiagnosticsHub::StandardCollector::ICollectionSessionControllerEx'};
  *(_QWORD *)(a1 + 16) = &Microsoft::DiagnosticsHub::StandardCollector::EtwCollectionSessionController::`vftable'{for `ISupportErrorInfo'};
  *(_QWORD *)(a1 + 24) = &Microsoft::DiagnosticsHub::StandardCollector::EtwCollectionSessionController::`vftable'{for `Microsoft::DiagnosticsHub::StandardCollector::AgentController'};
  *(_QWORD *)(a1 + 824) = &Microsoft::DiagnosticsHub::StandardCollector::EtwCollectionSessionController::`vftable'{for `CModuleRefCount'};
  *(_QWORD *)(a1 + 1024) = &Microsoft::DiagnosticsHub::StandardCollector::EtwCollectionSessionController::`vftable'{for `IEtwCollectionSessionController3'};
  *(_QWORD *)(a1 + 1032) = &Microsoft::DiagnosticsHub::StandardCollector::EtwCollectionSessionController::`vftable'{for `IPmcCollectionSessionController'};
  *(_QWORD *)(a1 + 1040) = &Microsoft::DiagnosticsHub::StandardCollector::EtwCollectionSessionController::`vftable'{for `ITraceEventCallback'};
  *(_QWORD *)(a1 + 1048) = &Microsoft::DiagnosticsHub::StandardCollector::EtwCollectionSessionController::`vftable'{for `Microsoft::DiagnosticsHub::StandardCollector::EtwCollectionProcessFilter'};
  *(_QWORD *)(a1 + 1104) = &Microsoft::DiagnosticsHub::StandardCollector::EtwCollectionSessionController::`vftable'{for `Microsoft::DiagnosticsHub::StandardCollector::EtwCollectionSyncController'};
  *(_QWORD *)(a1 + 2672) = &Microsoft::DiagnosticsHub::StandardCollector::EtwCollectionSessionController::`vftable'{for `Microsoft::DiagnosticsHub::StandardCollector::EtwCollectionRecommendedSettings'};
  *(_QWORD *)(a1 + 2752) = &Microsoft::DiagnosticsHub::StandardCollector::EtwCollectionSessionController::`vftable'{for `Microsoft::DiagnosticsHub::StandardCollector::EtwCollectionRundownController'};
  *(_QWORD *)v34 = a1 + 2784;
  *(_DWORD *)(a1 + 2784) = 0;
  *(_QWORD *)(a1 + 2792) = 0;
  *(_QWORD *)(a1 + 2800) = 0;
  v13 = operator new(0x30u);
  *v13 = v13;
  v13[1] = v13;
  *(_QWORD *)(a1 + 2792) = v13;
  *(_QWORD *)(a1 + 2808) = 0;
  *(_QWORD *)(a1 + 2816) = 0;
  *(_QWORD *)(a1 + 2824) = 0;
  *(_QWORD *)(a1 + 2832) = 7;
  *(_QWORD *)(a1 + 2840) = 8;
  *(_DWORD *)(a1 + 2784) = 1065353216;
  std::_Hash_vec<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<_GUID const,int>>>>>>::_Assign_grow(
    a1 + 2808,
    16,
    *(_QWORD *)(a1 + 2792));
  InitializeSRWLock((PSRWLOCK)(a1 + 2848));
  `eh vector constructor iterator'(
    (void *)(a1 + 2856),
    0x80u,
    5u,
    (void (*)(void *))Microsoft::DiagnosticsHub::StandardCollector::EtwCollectionSessionController::EtwSessionInformation::EtwSessionInformation,
    (void (*)(void *))Microsoft::DiagnosticsHub::StandardCollector::EtwCollectionSessionController::EtwSessionInformation::~EtwSessionInformation);
  *(_OWORD *)(a1 + 3496) = 0;
  *(_OWORD *)(a1 + 3512) = 0;
  *(_QWORD *)(a1 + 3528) = 0;
  InitializeCriticalSectionAndSpinCount((LPCRITICAL_SECTION)(a1 + 3496), 0xFA0u);
  *(_OWORD *)(a1 + 3536) = 0;
  *(_OWORD *)(a1 + 3552) = 0;
  *(_QWORD *)(a1 + 3568) = 0;
  InitializeCriticalSection((LPCRITICAL_SECTION)(a1 + 3536));
  *(_WORD *)(a1 + 3576) = 0;
  *(_BYTE *)(a1 + 3578) = !IsWindowsVersionOrGreater(v14, 2u, v15);
  *(_DWORD *)(a1 + 3580) = 1500;
  *(_DWORD *)(a1 + 3584) = 15;
  *(_QWORD *)(a1 + 3592) = 0;
  *(_QWORD *)(a1 + 3600) = 0;
  *(_QWORD *)(a1 + 3608) = 0;
  Microsoft::DiagnosticsHub::StandardCollector::KernelTraceControl::KernelTraceControl((Microsoft::DiagnosticsHub::StandardCollector::KernelTraceControl *)(a1 + 3616));
  *(_QWORD *)(a1 + 3920) = *(_QWORD *)pExceptionObject;
  *(_QWORD *)(a1 + 3928) = 0;
  *(_BYTE *)(a1 + 3936) = (*(_DWORD *)(a3 + 8) & 2) != 0;
  *(_WORD *)(a1 + 3937) = 0;
  v16 = 39;
  if ( !StringFromGUID2((const GUID *const)(a1 + 840), sz, 39) )
  {
    cbData = -2147024882;
    throw (long *)&cbData;
  }
  v40[0] = 0;
  v40[39] = 0;
  hKey[0] = 0;
  hKey[1] = 0;
  v29 = 0;
  v19 = ATL::CRegKey::Open((ATL::CRegKey *)hKey, v17, L"Software\\Microsoft\\VisualStudio\\DiagnosticsHub", v18);
  v20 = hKey[0];
  if ( !v19 )
  {
    cbData = 4;
    if ( !RegQueryValueExW(hKey[0], L"Collector.ForceNtKernelForSystemSession", 0, &Type, Data, &cbData)
      && Type == 4
      && *(_DWORD *)Data == 1 )
    {
      DiagHubCommon::LogStream::Write(
        (DiagHubCommon::LogStream *)((char *)_logger + 112),
        L"D:\\a\\_work\\1\\s\\sources\\Base\\Collection\\StandardCollector.Runtime\\EtwCollectionSessionController.cpp",
        L"Forcing the NT Kernel Logger for all system sessions.");
      *(_BYTE *)(a1 + 3578) = 1;
    }
    Type = 4;
    if ( !RegQueryValueExW(v20, L"Collector.HeapSessionAttemptTimeoutInMs", 0, &cbData, lpData, &Type) && cbData == 4 )
      *(_DWORD *)(a1 + 3580) = *(_DWORD *)lpData;
    Type = 4;
    if ( !RegQueryValueExW(v20, L"Collector.HeapSessionAttemptCount", 0, &cbData, v35, &Type) && cbData == 4 )
      *(_DWORD *)(a1 + 3584) = *(_DWORD *)v35;
    Type = 4;
    if ( !RegQueryValueExW(v20, L"Collector.MultiFileResult", 0, &cbData, v34, &Type) && cbData == 4 )
      *(_BYTE *)(a1 + 3937) = *(_DWORD *)v34 == 1;
    Type = 4;
    if ( !RegQueryValueExW(v20, L"Collector.DoNotDeleteRawEtl", 0, &cbData, pExceptionObject, &Type) && cbData == 4 )
      *(_BYTE *)(a1 + 3938) = *(_DWORD *)pExceptionObject == 1;
  }
  v21 = *(_BYTE *)(a1 + 3938) == 0;
  if ( !v40[0] )
  {
    v22 = v40;
    do
    {
      if ( v16 == 3 )
        break;
      v23 = *(v22 - 38);
      if ( !v23 )
        break;
      *v22++ = v23;
      --v16;
    }
    while ( v16 );
    v24 = v22 - 1;
    if ( v16 )
      v24 = v22;
    *v24 = 0;
    if ( !v16 )
      v40[0] = 0;
  }
  v25 = Microsoft::DiagnosticsHub::StandardCollector::SecuredDirectory::Create(
          *(unsigned __int16 **)(a3 + 32),
          v40,
          *(void **)(a1 + 872),
          v21,
          (Microsoft::DiagnosticsHub::StandardCollector::SecuredDirectory **)(a1 + 3928));
  if ( v25 < 0 )
  {
    *(_DWORD *)pExceptionObject = v25;
    throw (long *)pExceptionObject;
  }
  _mm_lfence();
  if ( v20 )
    RegCloseKey(v20);
  v26 = (volatile signed __int32 *)a5[1];
  if ( v26 )
  {
    if ( _InterlockedExchangeAdd(v26 + 2, 0xFFFFFFFF) == 1 )
    {
      (**(void (__fastcall ***)(volatile signed __int32 *))v26)(v26);
      if ( _InterlockedExchangeAdd(v26 + 3, 0xFFFFFFFF) == 1 )
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v26 + 8LL))(v26);
    }
  }
  return a1;
}

```

## disassembly

```asm
0x18001a850  mov     [rsp-8+arg_18], rbx
0x18001a855  push    rbp
0x18001a856  push    rsi
0x18001a857  push    rdi
0x18001a858  push    r12
0x18001a85a  push    r13
0x18001a85c  push    r14
0x18001a85e  push    r15
0x18001a860  lea     rbp, [rsp-70h]
0x18001a865  sub     rsp, 170h
0x18001a86c  mov     rax, cs:__security_cookie
0x18001a873  xor     rax, rsp
0x18001a876  mov     [rbp+0A0h+var_40], rax
0x18001a87a  mov     qword ptr [rsp+1A0h+pExceptionObject], r9
0x18001a87f  mov     r13, r8
0x18001a882  mov     rsi, rcx
0x18001a885  mov     [rsp+1A0h+var_158], rcx
0x18001a88a  mov     r12, [rbp+0A0h+arg_20]
0x18001a891  mov     [rsp+1A0h+var_150], r12
0x18001a896  mov     rcx, [rbp+0A0h+arg_28]
0x18001a89d  mov     rax, [r12]
0x18001a8a1  mov     [rsp+1A0h+hKey], rax
0x18001a8a6  mov     rax, [r12+8]
0x18001a8ab  mov     [rsp+1A0h+hKey+8], rax
0x18001a8b0  xor     r15d, r15d
0x18001a8b3  mov     [r12], r15
0x18001a8b7  mov     [r12+8], r15
0x18001a8bc  mov     [rsp+1A0h+lpData], rcx
0x18001a8c1  lea     r9, [rsp+1A0h+hKey]
0x18001a8c6  mov     rcx, rsi
0x18001a8c9  call    ??0CollectionSessionController@StandardCollector@DiagnosticsHub@Microsoft@@QEAA@PEAUIStandardCollectorClientDelegate@@AEBUSessionConfiguration@@V?$shared_ptr@VSecuredDirectory@StandardCollector@DiagnosticsHub@Microsoft@@@std@@PEAX@Z; Microsoft::DiagnosticsHub::StandardCollector::CollectionSessionController::CollectionSessionController(IStandardCollectorClientDelegate *,SessionConfiguration const &,std::shared_ptr<Microsoft::DiagnosticsHub::StandardCollector::SecuredDirectory>,void *)
0x18001a8ce  nop
0x18001a8cf  lea     r14, [rsi+418h]
0x18001a8d6  mov     qword ptr [rsp+1A0h+var_140], r14
0x18001a8db  lea     rax, ??_7EtwCollectionProcessFilter@StandardCollector@DiagnosticsHub@Microsoft@@6B@; const Microsoft::DiagnosticsHub::StandardCollector::EtwCollectionProcessFilter::`vftable'
0x18001a8e2  mov     [r14], rax
0x18001a8e5  mov     dword ptr [r14+8], 0FFFFFFFFh
0x18001a8ed  mov     [r14+10h], r15
0x18001a8f1  mov     [r14+18h], r15
0x18001a8f5  lea     edi, [r15+20h]
0x18001a8f9  mov     ecx, edi; Size
0x18001a8fb  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18001a900  mov     [rax], rax
0x18001a903  mov     [rax+8], rax
0x18001a907  mov     [rax+10h], rax
0x18001a90b  mov     word ptr [rax+18h], 101h
0x18001a911  mov     [r14+10h], rax
0x18001a915  mov     [r14+20h], r15
0x18001a919  mov     [r14+28h], r15
0x18001a91d  mov     ecx, edi; Size
0x18001a91f  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18001a924  mov     [rax], rax
0x18001a927  mov     [rax+8], rax
0x18001a92b  mov     [rax+10h], rax
0x18001a92f  mov     word ptr [rax+18h], 101h
0x18001a935  mov     [r14+20h], rax
0x18001a939  lea     rcx, [r14+30h]; SRWLock
0x18001a93d  call    cs:__imp_InitializeSRWLock
0x18001a943  nop
0x18001a944  lea     r15, [rsi+450h]
0x18001a94b  mov     qword ptr [rsp+1A0h+var_140], r15
0x18001a950  lea     rax, ??_7EtwCollectionSyncController@StandardCollector@DiagnosticsHub@Microsoft@@6B@; const Microsoft::DiagnosticsHub::StandardCollector::EtwCollectionSyncController::`vftable'
0x18001a957  mov     [r15], rax
0x18001a95a  lea     rcx, [r15+8]; void *
0x18001a95e  lea     rdi, ??1SyncEventContainer@EtwCollectionSyncController@StandardCollector@DiagnosticsHub@Microsoft@@QEAA@XZ; Microsoft::DiagnosticsHub::StandardCollector::EtwCollectionSyncController::SyncEventContainer::~SyncEventContainer(void)
0x18001a965  mov     [rsp+1A0h+lpData], rdi; void (*)(void *)
0x18001a96a  lea     r9, ??0SyncEventContainer@EtwCollectionSyncController@StandardCollector@DiagnosticsHub@Microsoft@@QEAA@XZ; void (*)(void *)
0x18001a971  mov     ebx, 18h
0x18001a976  lea     r8d, [rbx+8]; unsigned __int64
0x18001a97a  mov     edx, ebx; unsigned __int64
0x18001a97c  call    ??_L@YAXPEAX_K1P6AX0@Z2@Z; `eh vector constructor iterator'(void *,unsigned __int64,unsigned __int64,void (*)(void *),void (*)(void *))
0x18001a981  nop
0x18001a982  lea     rcx, [r15+308h]; void *
0x18001a989  mov     [rsp+1A0h+lpData], rdi; void (*)(void *)
0x18001a98e  lea     r9, ??0SyncEventContainer@EtwCollectionSyncController@StandardCollector@DiagnosticsHub@Microsoft@@QEAA@XZ; void (*)(void *)
0x18001a995  lea     r8d, [rbx+8]; unsigned __int64
0x18001a999  mov     edx, ebx; unsigned __int64
0x18001a99b  call    ??_L@YAXPEAX_K1P6AX0@Z2@Z; `eh vector constructor iterator'(void *,unsigned __int64,unsigned __int64,void (*)(void *),void (*)(void *))
0x18001a9a0  nop
0x18001a9a1  lea     rbx, [r15+618h]
0x18001a9a8  mov     qword ptr [rbx], 0
0x18001a9af  lea     rdi, [r15+608h]
0x18001a9b6  mov     rcx, rdi; pguid
0x18001a9b9  call    cs:__imp_CoCreateGuid
0x18001a9bf  test    eax, eax
0x18001a9c1  jnz     loc_18001AEC9
0x18001a9c7  mov     r9, rbx; RegHandle
0x18001a9ca  xor     r8d, r8d; CallbackContext
0x18001a9cd  xor     edx, edx; EnableCallback
0x18001a9cf  mov     rcx, rdi; ProviderId
0x18001a9d2  call    cs:__imp_EventRegister
0x18001a9d8  nop
0x18001a9d9  lea     rdi, [rsi+0A70h]
0x18001a9e0  mov     rcx, rdi; this
0x18001a9e3  call    ??0EtwCollectionRecommendedSettings@StandardCollector@DiagnosticsHub@Microsoft@@IEAA@AEBUSessionConfiguration@@@Z; Microsoft::DiagnosticsHub::StandardCollector::EtwCollectionRecommendedSettings::EtwCollectionRecommendedSettings(SessionConfiguration const &)
0x18001a9e8  nop
0x18001a9e9  lea     rbx, [rsi+0AC0h]
0x18001a9f0  mov     rcx, rbx; this
0x18001a9f3  call    ??0EtwCollectionRundownController@StandardCollector@DiagnosticsHub@Microsoft@@IEAA@I@Z; Microsoft::DiagnosticsHub::StandardCollector::EtwCollectionRundownController::EtwCollectionRundownController(uint)
0x18001a9f8  nop
0x18001a9f9  lea     rax, ??_7EtwCollectionSessionController@StandardCollector@DiagnosticsHub@Microsoft@@6BICollectionSessionController@@@; const Microsoft::DiagnosticsHub::StandardCollector::EtwCollectionSessionController::`vftable'{for `ICollectionSessionController'}
0x18001aa00  mov     [rsi], rax
0x18001aa03  lea     rax, ??_7EtwCollectionSessionController@StandardCollector@DiagnosticsHub@Microsoft@@6BICollectionSessionControllerEx@123@@; const Microsoft::DiagnosticsHub::StandardCollector::EtwCollectionSessionController::`vftable'{for `Microsoft::DiagnosticsHub::StandardCollector::ICollectionSessionControllerEx'}
0x18001aa0a  mov     [rsi+8], rax
0x18001aa0e  lea     rax, ??_7EtwCollectionSessionController@StandardCollector@DiagnosticsHub@Microsoft@@6BISupportErrorInfo@@@; const Microsoft::DiagnosticsHub::StandardCollector::EtwCollectionSessionController::`vftable'{for `ISupportErrorInfo'}
0x18001aa15  mov     [rsi+10h], rax
0x18001aa19  lea     rax, ??_7EtwCollectionSessionController@StandardCollector@DiagnosticsHub@Microsoft@@6BAgentController@123@@; const Microsoft::DiagnosticsHub::StandardCollector::EtwCollectionSessionController::`vftable'{for `Microsoft::DiagnosticsHub::StandardCollector::AgentController'}
0x18001aa20  mov     [rsi+18h], rax
0x18001aa24  lea     rax, ??_7EtwCollectionSessionController@StandardCollector@DiagnosticsHub@Microsoft@@6BCModuleRefCount@@@; const Microsoft::DiagnosticsHub::StandardCollector::EtwCollectionSessionController::`vftable'{for `CModuleRefCount'}
0x18001aa2b  mov     [rsi+338h], rax
0x18001aa32  lea     rax, ??_7EtwCollectionSessionController@StandardCollector@DiagnosticsHub@Microsoft@@6BIEtwCollectionSessionController3@@@; const Microsoft::DiagnosticsHub::StandardCollector::EtwCollectionSessionController::`vftable'{for `IEtwCollectionSessionController3'}
0x18001aa39  mov     [rsi+400h], rax
0x18001aa40  lea     rax, ??_7EtwCollectionSessionController@StandardCollector@DiagnosticsHub@Microsoft@@6BIPmcCollectionSessionController@@@; const Microsoft::DiagnosticsHub::StandardCollector::EtwCollectionSessionController::`vftable'{for `IPmcCollectionSessionController'}
0x18001aa47  mov     [rsi+408h], rax
0x18001aa4e  lea     rax, ??_7EtwCollectionSessionController@StandardCollector@DiagnosticsHub@Microsoft@@6BITraceEventCallback@@@; const Microsoft::DiagnosticsHub::StandardCollector::EtwCollectionSessionController::`vftable'{for `ITraceEventCallback'}
0x18001aa55  mov     [rsi+410h], rax
0x18001aa5c  lea     rax, ??_7EtwCollectionSessionController@StandardCollector@DiagnosticsHub@Microsoft@@6BEtwCollectionProcessFilter@123@@; const Microsoft::DiagnosticsHub::StandardCollector::EtwCollectionSessionController::`vftable'{for `Microsoft::DiagnosticsHub::StandardCollector::EtwCollectionProcessFilter'}
0x18001aa63  mov     [r14], rax
0x18001aa66  lea     rax, ??_7EtwCollectionSessionController@StandardCollector@DiagnosticsHub@Microsoft@@6BEtwCollectionSyncController@123@@; const Microsoft::DiagnosticsHub::StandardCollector::EtwCollectionSessionController::`vftable'{for `Microsoft::DiagnosticsHub::StandardCollector::EtwCollectionSyncController'}
0x18001aa6d  mov     [r15], rax
0x18001aa70  lea     rax, ??_7EtwCollectionSessionController@StandardCollector@DiagnosticsHub@Microsoft@@6BEtwCollectionRecommendedSettings@123@@; const Microsoft::DiagnosticsHub::StandardCollector::EtwCollectionSessionController::`vftable'{for `Microsoft::DiagnosticsHub::StandardCollector::EtwCollectionRecommendedSettings'}
0x18001aa77  mov     [rdi], rax
0x18001aa7a  lea     rax, ??_7EtwCollectionSessionController@StandardCollector@DiagnosticsHub@Microsoft@@6BEtwCollectionRundownController@123@@; const Microsoft::DiagnosticsHub::StandardCollector::EtwCollectionSessionController::`vftable'{for `Microsoft::DiagnosticsHub::StandardCollector::EtwCollectionRundownController'}
0x18001aa81  mov     [rbx], rax
0x18001aa84  lea     rbx, [rsi+0AE0h]
0x18001aa8b  mov     qword ptr [rsp+1A0h+var_140], rbx
0x18001aa90  xor     r15d, r15d
0x18001aa93  mov     [rbx], r15d
0x18001aa96  mov     [rbx+8], r15
0x18001aa9a  mov     [rbx+10h], r15
0x18001aa9e  lea     ecx, [r15+30h]; Size
0x18001aaa2  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18001aaa7  mov     [rax], rax
0x18001aaaa  mov     [rax+8], rax
0x18001aaae  mov     [rbx+8], rax
0x18001aab2  lea     rcx, [rbx+18h]
0x18001aab6  mov     [rcx], r15
0x18001aab9  mov     [rcx+8], r15
0x18001aabd  mov     [rcx+10h], r15
0x18001aac1  mov     qword ptr [rbx+30h], 7
0x18001aac9  mov     qword ptr [rbx+38h], 8
0x18001aad1  mov     dword ptr [rbx], 3F800000h
0x18001aad7  mov     r8, [rbx+8]
0x18001aadb  lea     edx, [r15+10h]
0x18001aadf  call    ?_Assign_grow@?$_Hash_vec@V?$allocator@V?$_List_unchecked_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBU_GUID@@H@std@@@std@@@std@@@std@@@std@@@std@@QEAAX_KV?$_List_unchecked_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBU_GUID@@H@std@@@std@@@std@@@2@@Z; std::_Hash_vec<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<_GUID const,int>>>>>>::_Assign_grow(unsigned __int64,std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<_GUID const,int>>>>)
0x18001aae4  nop
0x18001aae5  lea     rcx, [rsi+0B20h]; SRWLock
0x18001aaec  call    cs:__imp_InitializeSRWLock
0x18001aaf2  lea     rcx, [rsi+0B28h]; void *
0x18001aaf9  lea     rax, ??1EtwSessionInformation@EtwCollectionSessionController@StandardCollector@DiagnosticsHub@Microsoft@@QEAA@XZ; Microsoft::DiagnosticsHub::StandardCollector::EtwCollectionSessionController::EtwSessionInformation::~EtwSessionInformation(void)
0x18001ab00  mov     [rsp+1A0h+lpData], rax; void (*)(void *)
0x18001ab05  lea     r9, ??0EtwSessionInformation@EtwCollectionSessionController@StandardCollector@DiagnosticsHub@Microsoft@@QEAA@XZ; void (*)(void *)
0x18001ab0c  mov     edx, 80h; unsigned __int64
0x18001ab11  lea     r8d, [r15+5]; unsigned __int64
0x18001ab15  call    ??_L@YAXPEAX_K1P6AX0@Z2@Z; `eh vector constructor iterator'(void *,unsigned __int64,unsigned __int64,void (*)(void *),void (*)(void *))
0x18001ab1a  nop
0x18001ab1b  lea     rcx, [rsi+0DA8h]; lpCriticalSection
0x18001ab22  xorps   xmm0, xmm0
0x18001ab25  xor     eax, eax
0x18001ab27  movups  xmmword ptr [rcx], xmm0
0x18001ab2a  movups  xmmword ptr [rcx+10h], xmm0
0x18001ab2e  mov     [rcx+20h], rax
0x18001ab32  mov     edx, 0FA0h; dwSpinCount
0x18001ab37  call    cs:__imp_InitializeCriticalSectionAndSpinCount
0x18001ab3d  nop
0x18001ab3e  lea     rcx, [rsi+0DD0h]; lpCriticalSection
0x18001ab45  xorps   xmm0, xmm0
0x18001ab48  xor     eax, eax
0x18001ab4a  movups  xmmword ptr [rcx], xmm0
0x18001ab4d  movups  xmmword ptr [rcx+10h], xmm0
0x18001ab51  mov     [rcx+20h], rax
0x18001ab55  call    cs:__imp_InitializeCriticalSection
0x18001ab5b  nop
0x18001ab5c  mov     [rsi+0DF8h], r15w
0x18001ab64  lea     edx, [r15+2]; unsigned __int16
0x18001ab68  call    ?IsWindowsVersionOrGreater@@YA_NGGG@Z; IsWindowsVersionOrGreater(ushort,ushort,ushort)
0x18001ab6d  xor     al, 1
0x18001ab6f  mov     [rsi+0DFAh], al
0x18001ab75  mov     dword ptr [rsi+0DFCh], 5DCh
0x18001ab7f  mov     dword ptr [rsi+0E00h], 0Fh
0x18001ab89  mov     [rsi+0E08h], r15
0x18001ab90  mov     [rsi+0E10h], r15
0x18001ab97  mov     [rsi+0E18h], r15
0x18001ab9e  lea     rcx, [rsi+0E20h]; this
0x18001aba5  call    ??0KernelTraceControl@StandardCollector@DiagnosticsHub@Microsoft@@QEAA@XZ; Microsoft::DiagnosticsHub::StandardCollector::KernelTraceControl::KernelTraceControl(void)
0x18001abaa  nop
0x18001abab  mov     rax, qword ptr [rsp+1A0h+pExceptionObject]
0x18001abb0  mov     [rsi+0F50h], rax
0x18001abb7  lea     r14, [rsi+0F58h]
0x18001abbe  mov     [r14], r15
0x18001abc1  mov     eax, [r13+8]
0x18001abc5  shr     eax, 1
0x18001abc7  and     al, 1
0x18001abc9  mov     [rsi+0F60h], al
0x18001abcf  mov     [rsi+0F61h], r15w
0x18001abd7  lea     rcx, [rsi+348h]; rguid
0x18001abde  lea     edi, [r15+27h]
0x18001abe2  mov     r8d, edi; cchMax
0x18001abe5  lea     rdx, [rbp+0A0h+sz]; lpsz
0x18001abe9  call    cs:__imp_StringFromGUID2
0x18001abef  test    eax, eax
0x18001abf1  jz      loc_18001AEDF
0x18001abf7  mov     [rbp+0A0h+var_D2], r15w
0x18001abfc  mov     [rbp+0A0h+var_84], r15w
0x18001ac01  xorps   xmm0, xmm0
0x18001ac04  movups  xmmword ptr [rsp+1A0h+hKey], xmm0
0x18001ac09  mov     [rsp+1A0h+hKey], r15
0x18001ac0e  mov     dword ptr [rsp+1A0h+hKey+8], r15d
0x18001ac13  mov     [rsp+1A0h+var_160], r15
0x18001ac18  lea     r8, aSoftwareMicros_1; "Software\\Microsoft\\VisualStudio\\Diag"...
0x18001ac1f  lea     rcx, [rsp+1A0h+hKey]; this
0x18001ac24  call    ?Open@CRegKey@ATL@@QEAAJPEAUHKEY__@@PEBGK@Z; ATL::CRegKey::Open(HKEY__ *,ushort const *,ulong)
0x18001ac29  mov     rbx, [rsp+1A0h+hKey]
0x18001ac2e  test    eax, eax
0x18001ac30  jnz     loc_18001ADCD
0x18001ac36  mov     [rsp+1A0h+cbData], 4
0x18001ac3e  lea     rax, [rsp+1A0h+cbData]
0x18001ac43  mov     [rsp+1A0h+lpcbData], rax; lpcbData
0x18001ac48  lea     rax, [rsp+1A0h+Data]
0x18001ac4d  mov     [rsp+1A0h+lpData], rax; lpData
0x18001ac52  lea     r9, [rsp+1A0h+Type]; lpType
0x18001ac57  xor     r8d, r8d; lpReserved
0x18001ac5a  lea     rdx, aCollectorForce; "Collector.ForceNtKernelForSystemSession"
0x18001ac61  mov     rcx, rbx; hKey
0x18001ac64  call    cs:__imp_RegQueryValueExW
0x18001ac6a  test    eax, eax
0x18001ac6c  jnz     short loc_18001ACA1
0x18001ac6e  cmp     [rsp+1A0h+Type], 4
0x18001ac73  jnz     short loc_18001ACA1
0x18001ac75  cmp     dword ptr [rsp+1A0h+Data], 1
0x18001ac7a  jnz     short loc_18001ACA1
0x18001ac7c  mov     rcx, cs:?_logger@@3AEAVLogger@DiagHubCommon@@EA; DiagHubCommon::Logger & _logger
0x18001ac83  add     rcx, 70h ; 'p'; this
0x18001ac87  lea     r8, aForcingTheNtKe; "Forcing the NT Kernel Logger for all sy"...
0x18001ac8e  lea     rdx, aDAWork1SSource_17; "D:\\a\\_work\\1\\s\\sources\\Base\\Coll"...
0x18001ac95  call    ?Write@LogStream@DiagHubCommon@@QEAAXPEBG0ZZ; DiagHubCommon::LogStream::Write(ushort const *,ushort const *,...)
0x18001ac9a  mov     byte ptr [rsi+0DFAh], 1
0x18001aca1  mov     [rsp+1A0h+Type], 4
0x18001aca9  lea     rax, [rsp+1A0h+Type]
0x18001acae  mov     [rsp+1A0h+lpcbData], rax; lpcbData
0x18001acb3  lea     rax, [rsp+1A0h+var_124]
0x18001acb8  mov     [rsp+1A0h+lpData], rax; lpData
0x18001acbd  lea     r9, [rsp+1A0h+cbData]; lpType
0x18001acc2  xor     r8d, r8d; lpReserved
0x18001acc5  lea     rdx, aCollectorHeaps; "Collector.HeapSessionAttemptTimeoutInMs"
0x18001accc  mov     rcx, rbx; hKey
0x18001accf  call    cs:__imp_RegQueryValueExW
0x18001acd5  test    eax, eax
0x18001acd7  jnz     short loc_18001ACEA
0x18001acd9  cmp     [rsp+1A0h+cbData], 4
0x18001acde  jnz     short loc_18001ACEA
0x18001ace0  mov     eax, dword ptr [rsp+1A0h+var_124]
0x18001ace4  mov     [rsi+0DFCh], eax
0x18001acea  mov     [rsp+1A0h+Type], 4
0x18001acf2  lea     rax, [rsp+1A0h+Type]
0x18001acf7  mov     [rsp+1A0h+lpcbData], rax; lpcbData
0x18001acfc  lea     rax, [rsp+1A0h+var_138]
0x18001ad01  mov     [rsp+1A0h+lpData], rax; lpData
0x18001ad06  lea     r9, [rsp+1A0h+cbData]; lpType
0x18001ad0b  xor     r8d, r8d; lpReserved
0x18001ad0e  lea     rdx, aCollectorHeaps_0; "Collector.HeapSessionAttemptCount"
0x18001ad15  mov     rcx, rbx; hKey
0x18001ad18  call    cs:__imp_RegQueryValueExW
0x18001ad1e  test    eax, eax
0x18001ad20  jnz     short loc_18001AD33
0x18001ad22  cmp     [rsp+1A0h+cbData], 4
0x18001ad27  jnz     short loc_18001AD33
0x18001ad29  mov     eax, dword ptr [rsp+1A0h+var_138]
0x18001ad2d  mov     [rsi+0E00h], eax
0x18001ad33  mov     [rsp+1A0h+Type], 4
0x18001ad3b  lea     rax, [rsp+1A0h+Type]
0x18001ad40  mov     [rsp+1A0h+lpcbData], rax; lpcbData
0x18001ad45  lea     rax, [rsp+1A0h+var_140]
0x18001ad4a  mov     [rsp+1A0h+lpData], rax; lpData
0x18001ad4f  lea     r9, [rsp+1A0h+cbData]; lpType
0x18001ad54  xor     r8d, r8d; lpReserved
0x18001ad57  lea     rdx, aCollectorMulti; "Collector.MultiFileResult"
0x18001ad5e  mov     rcx, rbx; hKey
0x18001ad61  call    cs:__imp_RegQueryValueExW
0x18001ad67  test    eax, eax
0x18001ad69  jnz     short loc_18001AD80
0x18001ad6b  cmp     [rsp+1A0h+cbData], 4
0x18001ad70  jnz     short loc_18001AD80
0x18001ad72  cmp     dword ptr [rsp+1A0h+var_140], 1
0x18001ad77  setz    al
0x18001ad7a  mov     [rsi+0F61h], al
0x18001ad80  mov     [rsp+1A0h+Type], 4
0x18001ad88  lea     rax, [rsp+1A0h+Type]
0x18001ad8d  mov     [rsp+1A0h+lpcbData], rax; lpcbData
0x18001ad92  lea     rax, [rsp+1A0h+pExceptionObject]
0x18001ad97  mov     [rsp+1A0h+lpData], rax; lpData
0x18001ad9c  lea     r9, [rsp+1A0h+cbData]; lpType
0x18001ada1  xor     r8d, r8d; lpReserved
0x18001ada4  lea     rdx, aCollectorDonot; "Collector.DoNotDeleteRawEtl"
0x18001adab  mov     rcx, rbx; hKey
0x18001adae  call    cs:__imp_RegQueryValueExW
0x18001adb4  test    eax, eax
0x18001adb6  jnz     short loc_18001ADCD
0x18001adb8  cmp     [rsp+1A0h+cbData], 4
0x18001adbd  jnz     short loc_18001ADCD
  ... truncated ...
```
