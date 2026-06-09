# ConnectedStorage::Service::Service(std::shared_ptr<ConnectedStorage::WebService>)

- ea: `0x180011734`
- end: `0x180011b8c`
- name: `??0Service@ConnectedStorage@@AEAA@V?$shared_ptr@VWebService@ConnectedStorage@@@std@@@Z`
- size: `1112`
- prototype: `struct ConnectedStorage::Mutex *__fastcall(struct ConnectedStorage::Mutex *, _QWORD *)`
- caller_count: `1`
- callee_count: `22`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x180014280`

## callees

- `0x180004078`
- `0x18000a040`
- `0x18000aae4`
- `0x18000c218`
- `0x18000cb9c`
- `0x1800100d8`
- `0x1800101e4`
- `0x1800104bc`
- `0x180011504`
- `0x180011734`
- `0x180012d0c`
- `0x18001367c`
- `0x180014980`
- `0x180014a04`
- `0x1800190f0`
- `0x180027388`
- `0x180027a04`
- `0x18002a5b4`
- `0x18002e930`
- `0x180033b90`
- `0x180084c50`
- `0x18008e010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x180011762`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x180011762`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180011a01`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180011a4b`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180011ac3`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180011b29`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180011a01`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180011a4b`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180011ac3`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180011b29`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18001188b`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18001188b`

## string_xrefs

- `0x180011b5c`: `_rpcServer.Initialize(svcIXblGameSaveRpc_v1_0_s_ifspec, L"XblGameSaveService")`
- `0x180011b7a`: `WebService::SetInstance`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
struct ConnectedStorage::Mutex *__fastcall ConnectedStorage::Service::Service(
        struct ConnectedStorage::Mutex *a1,
        _QWORD *a2)
{
  ConnectedStorage::ExecuteQueue **v4; // rsi
  __int64 v5; // rax
  __int64 v6; // rax
  _QWORD *v7; // rax
  char *v8; // r8
  HRESULT Instance; // eax
  const unsigned __int16 *v10; // r8
  __int64 *v11; // rax
  __int64 v12; // rcx
  __int64 v13; // rdx
  std::_Ref_count_base *v14; // rcx
  __int64 *v15; // rax
  __int64 v16; // rcx
  __int64 v17; // rdx
  std::_Ref_count_base *v18; // rcx
  __int64 *v19; // rax
  char *v20; // r8
  __int64 v21; // rcx
  __int64 v22; // rdx
  std::_Ref_count_base *v23; // rcx
  char *v24; // r8
  __int64 v25; // rdx
  const unsigned __int16 *v26; // r8
  bool v27; // bl
  __int64 v28; // rbx
  char *v29; // r8
  void *v30; // rdx
  const unsigned __int16 *v31; // r8
  const unsigned __int16 *v32; // r9
  int v33; // eax
  const unsigned __int16 *v34; // r8
  std::_Ref_count_base *v35; // rcx
  LPCRITICAL_SECTION lpCriticalSection; // [rsp+38h] [rbp-79h] BYREF
  std::_Ref_count_base *v38; // [rsp+40h] [rbp-71h]
  __int64 (__fastcall **v39)(); // [rsp+48h] [rbp-69h] BYREF
  struct ConnectedStorage::Mutex *v40; // [rsp+50h] [rbp-61h]
  __int64 (__fastcall ***v41)(); // [rsp+80h] [rbp-31h]
  _QWORD v42[7]; // [rsp+88h] [rbp-29h] BYREF
  _QWORD *v43; // [rsp+C0h] [rbp+Fh]
  LPCRITICAL_SECTION v44[8]; // [rsp+C8h] [rbp+17h] BYREF
  __int64 (__fastcall ***v45)(); // [rsp+128h] [rbp+77h] BYREF

  InitializeCriticalSection((LPCRITICAL_SECTION)a1);
  *((_DWORD *)a1 + 10) = 0;
  LODWORD(v45) = 1;
  v4 = (ConnectedStorage::ExecuteQueue **)((char *)a1 + 48);
  std::make_shared<ConnectedStorage::ExecuteQueue,enum ConnectedStorage::WatchdogType>((char *)a1 + 48, &v45);
  std::make_shared<ConnectedStorage::Uploader,std::shared_ptr<ConnectedStorage::ExecuteQueue> &>(
    (char *)a1 + 64,
    (char *)a1 + 48);
  *((_QWORD *)a1 + 10) = 0;
  *((_QWORD *)a1 + 11) = 0;
  *((_QWORD *)a1 + 12) = 0;
  *((_QWORD *)a1 + 13) = 0;
  v45 = (__int64 (__fastcall ***)())operator new(0x50u);
  v5 = ConnectedStorage::OperationTracker::OperationTracker((ConnectedStorage::OperationTracker *)v45);
  std::shared_ptr<ConnectedStorage::OperationTracker>::shared_ptr<ConnectedStorage::OperationTracker>(
    (char *)a1 + 112,
    v5);
  *((_QWORD *)a1 + 16) = 0;
  *((_QWORD *)a1 + 17) = 0;
  v6 = a2[1];
  if ( v6 )
    _InterlockedIncrement((volatile signed __int32 *)(v6 + 8));
  *((_QWORD *)a1 + 16) = *a2;
  *((_QWORD *)a1 + 17) = a2[1];
  *((_QWORD *)a1 + 18) = 0;
  *((_QWORD *)a1 + 19) = 0;
  ConnectedStorage::Power::Power((struct ConnectedStorage::Mutex *)((char *)a1 + 160));
  *((_QWORD *)a1 + 46) = 0;
  *((_QWORD *)a1 + 47) = 0;
  *((_DWORD *)a1 + 96) = 0;
  *((_QWORD *)a1 + 49) = 0;
  *((_QWORD *)a1 + 50) = 0;
  v7 = operator new(0x68u);
  *v7 = v7;
  v7[1] = v7;
  v7[2] = v7;
  *((_WORD *)v7 + 12) = 257;
  *((_QWORD *)a1 + 49) = v7;
  ConnectedStorage::Mutex::Lock::Lock((ConnectedStorage::Mutex::Lock *)v44, (struct _RTL_CRITICAL_SECTION *)a1, v8);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&ConnectedStorage::CoDisconnectableContext::s_spContextCallback);
  Instance = CoCreateInstance(
               &CLSID_ContextSwitcher,
               0,
               1u,
               &GUID_000001da_0000_0000_c000_000000000046,
               &ConnectedStorage::CoDisconnectableContext::s_spContextCallback);
  if ( Instance < 0 )
    ConnectedStorage::ReportErrorAndThrow(
      (ConnectedStorage *)(unsigned int)Instance,
      (int)L"CoDisconnectableContext::Initialize()",
      v10);
  v39 = off_18008FA00;
  v41 = &v39;
  v42[0] = off_18008FA30;
  v43 = v42;
  v11 = (__int64 *)ConnectedStorage::UserManager::Create(&lpCriticalSection, v42, &v39);
  v12 = *v11;
  v13 = v11[1];
  *v11 = 0;
  v11[1] = 0;
  *((_QWORD *)a1 + 10) = v12;
  v14 = (std::_Ref_count_base *)*((_QWORD *)a1 + 11);
  *((_QWORD *)a1 + 11) = v13;
  if ( v14 )
    std::_Ref_count_base::_Decref(v14);
  if ( v38 )
    std::_Ref_count_base::_Decref(v38);
  (*(void (__fastcall **)(_QWORD, _QWORD))(**((_QWORD **)a1 + 16) + 8LL))(*((_QWORD *)a1 + 16), *((_QWORD *)a1 + 10));
  v45 = (__int64 (__fastcall ***)())*((_QWORD *)a1 + 10);
  v15 = (__int64 *)std::make_shared<ConnectedStorage::Contexts,std::shared_ptr<ConnectedStorage::ExecuteQueue> &,std::shared_ptr<ConnectedStorage::Uploader> &,ConnectedStorage::UserManager *>(
                     &lpCriticalSection,
                     (char *)a1 + 48,
                     (char *)a1 + 64,
                     &v45);
  v16 = *v15;
  v17 = v15[1];
  *v15 = 0;
  v15[1] = 0;
  *((_QWORD *)a1 + 12) = v16;
  v18 = (std::_Ref_count_base *)*((_QWORD *)a1 + 13);
  *((_QWORD *)a1 + 13) = v17;
  if ( v18 )
    std::_Ref_count_base::_Decref(v18);
  if ( v38 )
    std::_Ref_count_base::_Decref(v38);
  v42[0] = off_18008F9B0;
  v43 = v42;
  v19 = (__int64 *)ConnectedStorage::NlmWrapper::Create(&lpCriticalSection, v42);
  v21 = *v19;
  v22 = v19[1];
  *v19 = 0;
  v19[1] = 0;
  *((_QWORD *)a1 + 18) = v21;
  v23 = (std::_Ref_count_base *)*((_QWORD *)a1 + 19);
  *((_QWORD *)a1 + 19) = v22;
  if ( v23 )
    std::_Ref_count_base::_Decref(v23);
  if ( v38 )
    std::_Ref_count_base::_Decref(v38);
  v39 = off_18008F980;
  v41 = &v39;
  v45 = &v39;
  ConnectedStorage::Mutex::Lock::Lock(
    (ConnectedStorage::Mutex::Lock *)&lpCriticalSection,
    (struct _RTL_CRITICAL_SECTION *)a1 + 4,
    v20);
  std::function<void (void)>::operator=((char *)a1 + 296, &v39);
  LeaveCriticalSection(lpCriticalSection);
  std::function<long (void)>::~function<long (void)>(&v39);
  v39 = off_18008F950;
  v41 = &v39;
  v45 = &v39;
  ConnectedStorage::Mutex::Lock::Lock(
    (ConnectedStorage::Mutex::Lock *)&lpCriticalSection,
    (struct _RTL_CRITICAL_SECTION *)a1 + 4,
    v24);
  std::function<void (void)>::operator=((char *)a1 + 232, &v39);
  LeaveCriticalSection(lpCriticalSection);
  std::function<long (void)>::~function<long (void)>(&v39);
  if ( ConnectedStorage::gInstance )
    ConnectedStorage::ReportErrorAndThrow((ConnectedStorage *)0x8000FFFFLL, (int)L"WebService::SetInstance", v26);
  ConnectedStorage::gInstance = (struct ConnectedStorage::WebService *)*((_QWORD *)a1 + 16);
  v27 = (*(_DWORD *)(*((_QWORD *)a1 + 18) + 32LL) & 0x440) != 0;
  LOBYTE(v25) = v27;
  (*(void (__fastcall **)(struct ConnectedStorage::WebService *, __int64))(*(_QWORD *)ConnectedStorage::gInstance + 112LL))(
    ConnectedStorage::gInstance,
    v25);
  ConnectedStorage::Contexts::OnNetworkConnectivityChanged(*((ConnectedStorage::Contexts **)a1 + 12), v27);
  v28 = *((_QWORD *)a1 + 12);
  ConnectedStorage::Mutex::Lock::Lock(
    (ConnectedStorage::Mutex::Lock *)&lpCriticalSection,
    (struct _RTL_CRITICAL_SECTION *)(v28 + 96),
    v29);
  *(_BYTE *)(v28 + 145) = 0;
  *(_BYTE *)(v28 + 147) = 0;
  LeaveCriticalSection(lpCriticalSection);
  std::_Func_class<void,>::operator()(v28 + 32);
  v39 = off_18008F920;
  v40 = a1;
  v41 = &v39;
  ConnectedStorage::ExecuteQueue::EnqueueTimerCallback(*v4);
  v33 = RpcServer::Initialize((struct ConnectedStorage::Mutex *)((char *)a1 + 360), v30, v31, v32);
  if ( v33 < 0 )
    ConnectedStorage::ReportErrorAndThrow(
      (ConnectedStorage *)(unsigned int)v33,
      (int)L"_rpcServer.Initialize(svcIXblGameSaveRpc_v1_0_s_ifspec, L\"XblGameSaveService\")",
      v34);
  v39 = off_18008F8F0;
  v40 = a1;
  v41 = &v39;
  ConnectedStorage::ExecuteQueue::Enqueue(*v4);
  LeaveCriticalSection(v44[0]);
  v35 = (std::_Ref_count_base *)a2[1];
  if ( v35 )
    std::_Ref_count_base::_Decref(v35);
  return a1;
}

```

## disassembly

```asm
0x180011734  mov     rax, rsp
0x180011737  mov     [rax+20h], rbx
0x18001173b  mov     [rax+10h], rdx
0x18001173f  mov     [rax+8], rcx
0x180011743  push    rbp
0x180011744  push    rsi
0x180011745  push    rdi
0x180011746  push    r12
0x180011748  push    r13
0x18001174a  push    r14
0x18001174c  push    r15
0x18001174e  lea     rbp, [rax-5Fh]
0x180011752  sub     rsp, 0D0h
0x180011759  mov     r14, rdx
0x18001175c  mov     rdi, rcx
0x18001175f  xor     r15d, r15d
0x180011762  call    cs:__imp_InitializeCriticalSection
0x180011768  mov     [rdi+28h], r15d
0x18001176c  mov     dword ptr [rbp+57h+arg_10], 1
0x180011773  lea     rsi, [rdi+30h]
0x180011777  lea     rdx, [rbp+57h+arg_10]
0x18001177b  mov     rcx, rsi
0x18001177e  call    ??$make_shared@VExecuteQueue@ConnectedStorage@@W4WatchdogType@2@@std@@YA?AV?$shared_ptr@VExecuteQueue@ConnectedStorage@@@0@$$QEAW4WatchdogType@ConnectedStorage@@@Z; std::make_shared<ConnectedStorage::ExecuteQueue,ConnectedStorage::WatchdogType>(ConnectedStorage::WatchdogType &&)
0x180011783  nop
0x180011784  mov     rdx, rsi
0x180011787  lea     rcx, [rdi+40h]
0x18001178b  call    ??$make_shared@VUploader@ConnectedStorage@@AEAV?$shared_ptr@VExecuteQueue@ConnectedStorage@@@std@@@std@@YA?AV?$shared_ptr@VUploader@ConnectedStorage@@@0@AEAV?$shared_ptr@VExecuteQueue@ConnectedStorage@@@0@@Z; std::make_shared<ConnectedStorage::Uploader,std::shared_ptr<ConnectedStorage::ExecuteQueue> &>(std::shared_ptr<ConnectedStorage::ExecuteQueue> &)
0x180011790  nop
0x180011791  mov     [rdi+50h], r15
0x180011795  mov     [rdi+58h], r15
0x180011799  mov     [rdi+60h], r15
0x18001179d  mov     [rdi+68h], r15
0x1800117a1  lea     ecx, [r15+50h]; Size
0x1800117a5  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800117aa  mov     [rbp+57h+arg_10], rax
0x1800117ae  mov     rcx, rax; this
0x1800117b1  call    ??0OperationTracker@ConnectedStorage@@AEAA@XZ; ConnectedStorage::OperationTracker::OperationTracker(void)
0x1800117b6  nop
0x1800117b7  mov     rdx, rax
0x1800117ba  lea     rcx, [rdi+70h]
0x1800117be  call    ??$?0VOperationTracker@ConnectedStorage@@$0A@@?$shared_ptr@VOperationTracker@ConnectedStorage@@@std@@QEAA@PEAVOperationTracker@ConnectedStorage@@@Z; std::shared_ptr<ConnectedStorage::OperationTracker>::shared_ptr<ConnectedStorage::OperationTracker>(ConnectedStorage::OperationTracker *)
0x1800117c3  nop
0x1800117c4  mov     [rdi+80h], r15
0x1800117cb  mov     [rdi+88h], r15
0x1800117d2  mov     rax, [r14+8]
0x1800117d6  test    rax, rax
0x1800117d9  jz      short loc_1800117DF
0x1800117db  lock inc dword ptr [rax+8]
0x1800117df  mov     rax, [r14]
0x1800117e2  mov     [rdi+80h], rax
0x1800117e9  mov     rax, [r14+8]
0x1800117ed  mov     [rdi+88h], rax
0x1800117f4  mov     [rdi+90h], r15
0x1800117fb  mov     [rdi+98h], r15
0x180011802  lea     r15, [rdi+0A0h]
0x180011809  mov     rcx, r15; this
0x18001180c  call    ??0Power@ConnectedStorage@@QEAA@XZ; ConnectedStorage::Power::Power(void)
0x180011811  nop
0x180011812  lea     r13, [rdi+168h]
0x180011819  xor     eax, eax
0x18001181b  mov     [r13+8], rax
0x18001181f  mov     [rdi+178h], rax
0x180011826  mov     [rdi+180h], eax
0x18001182c  lea     rbx, [rdi+188h]
0x180011833  mov     [rbx], rax
0x180011836  mov     [rbx+8], rax
0x18001183a  lea     ecx, [rax+68h]; Size
0x18001183d  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180011842  mov     [rax], rax
0x180011845  mov     [rax+8], rax
0x180011849  mov     [rax+10h], rax
0x18001184d  mov     word ptr [rax+18h], 101h
0x180011853  mov     [rbx], rax
0x180011856  mov     rdx, rdi; struct ConnectedStorage::Mutex *
0x180011859  lea     rcx, [rbp+57h+var_40]; this
0x18001185d  call    ??0Lock@Mutex@ConnectedStorage@@QEAA@AEAV12@PEAD@Z; ConnectedStorage::Mutex::Lock::Lock(ConnectedStorage::Mutex &,char *)
0x180011862  nop
0x180011863  lea     rbx, ?s_spContextCallback@CoDisconnectableContext@ConnectedStorage@@0V?$ComPtr@UIContextCallback@@@WRL@Microsoft@@A; Microsoft::WRL::ComPtr<IContextCallback> ConnectedStorage::CoDisconnectableContext::s_spContextCallback
0x18001186a  mov     rcx, rbx
0x18001186d  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180011872  mov     [rsp+20h], rbx; ppv
0x180011877  lea     r9, _GUID_000001da_0000_0000_c000_000000000046; riid
0x18001187e  xor     edx, edx; pUnkOuter
0x180011880  lea     r8d, [rdx+1]; dwClsContext
0x180011884  lea     rcx, CLSID_ContextSwitcher; rclsid
0x18001188b  call    cs:__imp_CoCreateInstance
0x180011891  xor     ebx, ebx
0x180011893  test    eax, eax
0x180011895  js      loc_180011B6B
0x18001189b  lea     rax, off_18008FA00
0x1800118a2  mov     [rbp+57h+var_C0], rax
0x1800118a6  lea     rax, [rbp+57h+var_C0]
0x1800118aa  mov     [rbp+57h+var_88], rax
0x1800118ae  lea     rax, off_18008FA30
0x1800118b5  mov     [rbp+57h+var_80], rax
0x1800118b9  lea     rax, [rbp+57h+var_80]
0x1800118bd  mov     [rbp+57h+var_48], rax
0x1800118c1  lea     r8, [rbp+57h+var_C0]
0x1800118c5  lea     rdx, [rbp+57h+var_80]
0x1800118c9  lea     rcx, [rbp+57h+lpCriticalSection]
0x1800118cd  call    ?Create@UserManager@ConnectedStorage@@SA?AV?$shared_ptr@VUserManager@ConnectedStorage@@@std@@V?$function@$$A6AXW4UserSignInOut@ConnectedStorage@@AEBVSimpleHStringWrapper@2@1@Z@4@V?$function@$$A6AXAEBVSimpleHStringWrapper@ConnectedStorage@@@Z@4@@Z; ConnectedStorage::UserManager::Create(std::function<void (ConnectedStorage::UserSignInOut,ConnectedStorage::SimpleHStringWrapper const &,ConnectedStorage::SimpleHStringWrapper const &)>,std::function<void (ConnectedStorage::SimpleHStringWrapper const &)>)
0x1800118d2  mov     rcx, [rax]
0x1800118d5  mov     rdx, [rax+8]
0x1800118d9  mov     [rax], rbx
0x1800118dc  mov     [rax+8], rbx
0x1800118e0  mov     [rdi+50h], rcx
0x1800118e4  mov     rcx, [rdi+58h]; this
0x1800118e8  mov     [rdi+58h], rdx
0x1800118ec  test    rcx, rcx
0x1800118ef  jz      short loc_1800118F6
0x1800118f1  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x1800118f6  mov     rcx, [rbp+57h+var_C8]; this
0x1800118fa  test    rcx, rcx
0x1800118fd  jz      short loc_180011904
0x1800118ff  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x180011904  mov     rcx, [rdi+80h]
0x18001190b  mov     rax, [rcx]
0x18001190e  mov     rdx, [rdi+50h]
0x180011912  mov     rax, [rax+8]
0x180011916  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001191b  mov     rax, [rdi+50h]
0x18001191f  mov     [rbp+57h+arg_10], rax
0x180011923  lea     r9, [rbp+57h+arg_10]
0x180011927  lea     r8, [rdi+40h]
0x18001192b  mov     rdx, rsi
0x18001192e  lea     rcx, [rbp+57h+lpCriticalSection]
0x180011932  call    ??$make_shared@VContexts@ConnectedStorage@@AEAV?$shared_ptr@VExecuteQueue@ConnectedStorage@@@std@@AEAV?$shared_ptr@VUploader@ConnectedStorage@@@4@PEAVUserManager@2@@std@@YA?AV?$shared_ptr@VContexts@ConnectedStorage@@@0@AEAV?$shared_ptr@VExecuteQueue@ConnectedStorage@@@0@AEAV?$shared_ptr@VUploader@ConnectedStorage@@@0@$$QEAPEAVUserManager@ConnectedStorage@@@Z; std::make_shared<ConnectedStorage::Contexts,std::shared_ptr<ConnectedStorage::ExecuteQueue> &,std::shared_ptr<ConnectedStorage::Uploader> &,ConnectedStorage::UserManager *>(std::shared_ptr<ConnectedStorage::ExecuteQueue> &,std::shared_ptr<ConnectedStorage::Uploader> &,ConnectedStorage::UserManager * &&)
0x180011937  mov     rcx, [rax]
0x18001193a  mov     rdx, [rax+8]
0x18001193e  mov     [rax], rbx
0x180011941  mov     [rax+8], rbx
0x180011945  mov     [rdi+60h], rcx
0x180011949  mov     rcx, [rdi+68h]; this
0x18001194d  mov     [rdi+68h], rdx
0x180011951  test    rcx, rcx
0x180011954  jz      short loc_18001195B
0x180011956  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18001195b  mov     rcx, [rbp+57h+var_C8]; this
0x18001195f  test    rcx, rcx
0x180011962  jz      short loc_180011969
0x180011964  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x180011969  lea     rax, off_18008F9B0
0x180011970  mov     [rbp+57h+var_80], rax
0x180011974  lea     rax, [rbp+57h+var_80]
0x180011978  mov     [rbp+57h+var_48], rax
0x18001197c  lea     rdx, [rbp+57h+var_80]
0x180011980  lea     rcx, [rbp+57h+lpCriticalSection]
0x180011984  call    ?Create@NlmWrapper@ConnectedStorage@@SA?AV?$shared_ptr@VNlmWrapper@ConnectedStorage@@@std@@V?$function@$$A6AX_N@Z@4@@Z; ConnectedStorage::NlmWrapper::Create(std::function<void (bool)>)
0x180011989  mov     rcx, [rax]
0x18001198c  mov     rdx, [rax+8]
0x180011990  mov     [rax], rbx
0x180011993  mov     [rax+8], rbx
0x180011997  mov     [rdi+90h], rcx
0x18001199e  mov     rcx, [rdi+98h]; this
0x1800119a5  mov     [rdi+98h], rdx
0x1800119ac  test    rcx, rcx
0x1800119af  jz      short loc_1800119B6
0x1800119b1  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x1800119b6  mov     rcx, [rbp+57h+var_C8]; this
0x1800119ba  test    rcx, rcx
0x1800119bd  jz      short loc_1800119C4
0x1800119bf  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x1800119c4  lea     rax, off_18008F980
0x1800119cb  mov     [rbp+57h+var_C0], rax
0x1800119cf  lea     rax, [rbp+57h+var_C0]
0x1800119d3  mov     [rbp+57h+var_88], rax
0x1800119d7  lea     rax, [rbp+57h+var_C0]
0x1800119db  mov     [rbp+57h+arg_10], rax
0x1800119df  mov     rdx, r15; struct ConnectedStorage::Mutex *
0x1800119e2  lea     rcx, [rbp+57h+lpCriticalSection]; this
0x1800119e6  call    ??0Lock@Mutex@ConnectedStorage@@QEAA@AEAV12@PEAD@Z; ConnectedStorage::Mutex::Lock::Lock(ConnectedStorage::Mutex &,char *)
0x1800119eb  nop
0x1800119ec  lea     rcx, [r15+88h]
0x1800119f3  lea     rdx, [rbp+57h+var_C0]
0x1800119f7  call    ??4?$function@$$A6AXXZ@std@@QEAAAEAV01@AEBV01@@Z; std::function<void (void)>::operator=(std::function<void (void)> const &)
0x1800119fc  nop
0x1800119fd  mov     rcx, [rbp+57h+lpCriticalSection]; lpCriticalSection
0x180011a01  call    cs:__imp_LeaveCriticalSection
0x180011a07  nop
0x180011a08  lea     rcx, [rbp+57h+var_C0]
0x180011a0c  call    ??1?$function@$$A6AJXZ@std@@QEAA@XZ; std::function<long (void)>::~function<long (void)>(void)
0x180011a11  lea     rax, off_18008F950
0x180011a18  mov     [rbp+57h+var_C0], rax
0x180011a1c  lea     rax, [rbp+57h+var_C0]
0x180011a20  mov     [rbp+57h+var_88], rax
0x180011a24  lea     rax, [rbp+57h+var_C0]
0x180011a28  mov     [rbp+57h+arg_10], rax
0x180011a2c  mov     rdx, r15; struct ConnectedStorage::Mutex *
0x180011a2f  lea     rcx, [rbp+57h+lpCriticalSection]; this
0x180011a33  call    ??0Lock@Mutex@ConnectedStorage@@QEAA@AEAV12@PEAD@Z; ConnectedStorage::Mutex::Lock::Lock(ConnectedStorage::Mutex &,char *)
0x180011a38  nop
0x180011a39  lea     rcx, [r15+48h]
0x180011a3d  lea     rdx, [rbp+57h+var_C0]
0x180011a41  call    ??4?$function@$$A6AXXZ@std@@QEAAAEAV01@AEBV01@@Z; std::function<void (void)>::operator=(std::function<void (void)> const &)
0x180011a46  nop
0x180011a47  mov     rcx, [rbp+57h+lpCriticalSection]; lpCriticalSection
0x180011a4b  call    cs:__imp_LeaveCriticalSection
0x180011a51  nop
0x180011a52  lea     rcx, [rbp+57h+var_C0]
0x180011a56  call    ??1?$function@$$A6AJXZ@std@@QEAA@XZ; std::function<long (void)>::~function<long (void)>(void)
0x180011a5b  cmp     cs:?gInstance@ConnectedStorage@@3PEAVWebService@1@EA, rbx; ConnectedStorage::WebService * ConnectedStorage::gInstance
0x180011a62  jnz     loc_180011B7A
0x180011a68  mov     rcx, [rdi+80h]
0x180011a6f  mov     cs:?gInstance@ConnectedStorage@@3PEAVWebService@1@EA, rcx; ConnectedStorage::WebService * ConnectedStorage::gInstance
0x180011a76  mov     rax, [rdi+90h]
0x180011a7d  test    dword ptr [rax+20h], 440h
0x180011a84  setnz   bl
0x180011a87  mov     rax, [rcx]
0x180011a8a  mov     dl, bl
0x180011a8c  mov     rax, [rax+70h]
0x180011a90  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011a95  mov     dl, bl; bool
0x180011a97  mov     rcx, [rdi+60h]; this
0x180011a9b  call    ?OnNetworkConnectivityChanged@Contexts@ConnectedStorage@@QEBAX_N@Z; ConnectedStorage::Contexts::OnNetworkConnectivityChanged(bool)
0x180011aa0  mov     rbx, [rdi+60h]
0x180011aa4  lea     rdx, [rbx+60h]; struct ConnectedStorage::Mutex *
0x180011aa8  lea     rcx, [rbp+57h+lpCriticalSection]; this
0x180011aac  call    ??0Lock@Mutex@ConnectedStorage@@QEAA@AEAV12@PEAD@Z; ConnectedStorage::Mutex::Lock::Lock(ConnectedStorage::Mutex &,char *)
0x180011ab1  mov     byte ptr [rbx+91h], 0
0x180011ab8  mov     byte ptr [rbx+93h], 0
0x180011abf  mov     rcx, [rbp+57h+lpCriticalSection]; lpCriticalSection
0x180011ac3  call    cs:__imp_LeaveCriticalSection
0x180011ac9  lea     rcx, [rbx+20h]
0x180011acd  call    ??R?$_Func_class@X$$V@std@@QEBAXXZ; std::_Func_class<void,>::operator()(void)
0x180011ad2  lea     rax, off_18008F920
0x180011ad9  mov     [rbp+57h+var_C0], rax
0x180011add  mov     [rbp+57h+var_B8], rdi
0x180011ae1  lea     rax, [rbp+57h+var_C0]
0x180011ae5  mov     [rbp+57h+var_88], rax
0x180011ae9  lea     rdx, [rbp+57h+var_C0]
0x180011aed  mov     rcx, [rsi]; this
0x180011af0  call    ?EnqueueTimerCallback@ExecuteQueue@ConnectedStorage@@QEAAXV?$function@$$A6AXXZ@std@@@Z; ConnectedStorage::ExecuteQueue::EnqueueTimerCallback(std::function<void (void)>)
0x180011af5  mov     rcx, r13; this
0x180011af8  call    ?Initialize@RpcServer@@QEAAJPEAXPEBG1@Z; RpcServer::Initialize(void *,ushort const *,ushort const *)
0x180011afd  test    eax, eax
0x180011aff  js      short loc_180011B5C
0x180011b01  lea     rax, off_18008F8F0
0x180011b08  mov     [rbp+57h+var_C0], rax
0x180011b0c  mov     [rbp+57h+var_B8], rdi
0x180011b10  lea     rax, [rbp+57h+var_C0]
0x180011b14  mov     [rbp+57h+var_88], rax
0x180011b18  lea     rdx, [rbp+57h+var_C0]
0x180011b1c  mov     rcx, [rsi]; this
0x180011b1f  call    ?Enqueue@ExecuteQueue@ConnectedStorage@@QEAAXV?$function@$$A6AXXZ@std@@@Z; ConnectedStorage::ExecuteQueue::Enqueue(std::function<void (void)>)
0x180011b24  nop
0x180011b25  mov     rcx, [rbp+57h+var_40]; lpCriticalSection
0x180011b29  call    cs:__imp_LeaveCriticalSection
0x180011b2f  nop
0x180011b30  mov     rcx, [r14+8]; this
0x180011b34  test    rcx, rcx
0x180011b37  jz      short loc_180011B3E
0x180011b39  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x180011b3e  mov     rax, rdi
0x180011b41  mov     rbx, [rsp+100h+arg_18]
0x180011b49  add     rsp, 0D0h
0x180011b50  pop     r15
0x180011b52  pop     r14
0x180011b54  pop     r13
0x180011b56  pop     r12
0x180011b58  pop     rdi
0x180011b59  pop     rsi
0x180011b5a  pop     rbp
0x180011b5b  retn
0x180011b5c  lea     rdx, aRpcserverIniti; "_rpcServer.Initialize(svcIXblGameSaveRp"...
0x180011b63  mov     ecx, eax; this
0x180011b65  call    ?ReportErrorAndThrow@ConnectedStorage@@YAXJPEBG@Z; ConnectedStorage::ReportErrorAndThrow(long,ushort const *)
0x180011b6b  lea     rdx, aCodisconnectab_3; "CoDisconnectableContext::Initialize()"
0x180011b72  mov     ecx, eax; this
0x180011b74  call    ?ReportErrorAndThrow@ConnectedStorage@@YAXJPEBG@Z; ConnectedStorage::ReportErrorAndThrow(long,ushort const *)
0x180011b7a  lea     rdx, aWebserviceSeti; "WebService::SetInstance"
0x180011b81  mov     ecx, 8000FFFFh; this
0x180011b86  call    ?ReportErrorAndThrow@ConnectedStorage@@YAXJPEBG@Z; ConnectedStorage::ReportErrorAndThrow(long,ushort const *)
```
