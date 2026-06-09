# _lambda_3a3b13dd1e30bcf0d85eb7df3b802851_::operator()(void)

- ea: `0x18000846c`
- end: `0x180008662`
- name: `??R_lambda_3a3b13dd1e30bcf0d85eb7df3b802851_@@QEBA@XZ`
- size: `502`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x18000ac70`

## callees

- `0x180005fe0`
- `0x18000637c`
- `0x18000846c`
- `0x180008d6c`
- `0x180008da4`
- `0x18000aba4`
- `0x18000abc4`
- `0x18000ae60`
- `0x18000c41c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800084c6`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800084c6`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180008614`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180008614`
- `api-ms-win-service-core-l1-1-0!RegisterServiceCtrlHandlerExW` at `0x18000848a`
- `api-ms-win-service-core-l1-1-0!RegisterServiceCtrlHandlerExW` at `0x18000848a`
- `api-ms-win-service-core-l1-1-0!SetServiceStatus` at `0x180008604`
- `api-ms-win-service-core-l1-1-0!SetServiceStatus` at `0x18000863b`
- `api-ms-win-service-core-l1-1-0!SetServiceStatus` at `0x180008604`
- `api-ms-win-service-core-l1-1-0!SetServiceStatus` at `0x18000863b`

## string_xrefs

- `0x1800084ab`: `onecore\internal\com\inc\comservicehelper.h`
- `0x1800085ae`: `onecore\internal\com\inc\comservicehelper.h`

## pseudocode

```c
__int64 __fastcall _lambda_3a3b13dd1e30bcf0d85eb7df3b802851_::operator()(__int64 a1)
{
  const char *v2; // r9
  __int64 v3; // rdx
  LPVOID v5; // rdi
  __int64 v6; // rcx
  __int64 v7; // r8
  __int64 v8; // r9
  __int64 *v9; // rax
  int v10; // edi
  __int64 v11; // rdx
  _lambda_249230bd792972bce8c42ec595a35649_ *v12; // rax
  __int64 v13; // [rsp+20h] [rbp-38h]
  int v14; // [rsp+20h] [rbp-38h]
  __int64 v15; // [rsp+40h] [rbp-18h] BYREF
  char v16; // [rsp+48h] [rbp-10h]
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+0h]
  char v18; // [rsp+60h] [rbp+8h] BYREF

  *(_QWORD *)(*(_QWORD *)a1 + 8LL) = RegisterServiceCtrlHandlerExW(
                                       L"XblGameSave",
                                       Windows::Internal::Service<ConnectedStorageService,3,Windows::Internal::ServiceModuleBase::SecurityPolicyEveryoneLocalAndRemote,2,Windows::Internal::DefaultServerDescriptor>::HandlerExStatic,
                                       *(LPVOID *)a1);
  if ( !*(_QWORD *)(*(_QWORD *)a1 + 8LL) )
  {
    v3 = 509;
    return wil::details::in1diag3::Return_GetLastError(
             retaddr,
             (void *)v3,
             (unsigned int)"onecore\\internal\\com\\inc\\comservicehelper.h",
             v2);
  }
  *(_QWORD *)(*(_QWORD *)a1 + 48LL) = CreateEventW(0, 0, 0, 0);
  v5 = *(LPVOID *)a1;
  if ( !*(_QWORD *)(*(_QWORD *)a1 + 48LL) )
  {
    v3 = 512;
    return wil::details::in1diag3::Return_GetLastError(
             retaddr,
             (void *)v3,
             (unsigned int)"onecore\\internal\\com\\inc\\comservicehelper.h",
             v2);
  }
  if ( **(_BYTE **)(a1 + 8) )
  {
    v6 = Microsoft::WRL::Details::OutOfProcModuleBase<Windows::Internal::ServiceModule>::Create();
    if ( *(_QWORD *)(v6 + 48) )
      goto LABEL_12;
    byte_1800C0AC0 = 1;
    Microsoft::WRL::Details::StaticStorage<Microsoft::WRL::Details::OutOfProcModuleBase<Windows::Internal::ServiceModule>::MethodReleaseNotifier<Windows::Internal::Service<ConnectedStorageService,3,Windows::Internal::ServiceModuleBase::SecurityPolicyEveryoneLocalAndRemote,2,Windows::Internal::DefaultServerDescriptor>>,3,Windows::Internal::ServiceModule>::instance_ = (__int64)&Microsoft::WRL::Details::OutOfProcModuleBase<Windows::Internal::ServiceModule>::MethodReleaseNotifier<Windows::Internal::Service<ConnectedStorageService,3,Windows::Internal::ServiceModuleBase::SecurityPolicyEveryoneLocalAndRemote,2,Windows::Internal::DefaultServerDescriptor>>::`vftable';
    qword_1800C0AB8 = (__int64)wistd::__function::__func<_lambda_8db0ce862824541f40dfb767113f1e28_,bool (void *,unsigned __int64,void *,unsigned __int64,unsigned int)>::destroy;
    v9 = &Microsoft::WRL::Details::StaticStorage<Microsoft::WRL::Details::OutOfProcModuleBase<Windows::Internal::ServiceModule>::MethodReleaseNotifier<Windows::Internal::Service<ConnectedStorageService,3,Windows::Internal::ServiceModuleBase::SecurityPolicyEveryoneLocalAndRemote,2,Windows::Internal::DefaultServerDescriptor>>,3,Windows::Internal::ServiceModule>::instance_;
    byte_1800C0AA8 = 0;
    qword_1800C0AB0 = (__int64)v5;
  }
  else
  {
    v6 = Microsoft::WRL::Details::OutOfProcModuleBase<Windows::Internal::SvcHostModule>::Create();
    if ( *(_QWORD *)(v6 + 48) )
      goto LABEL_12;
    byte_1800C0AE8 = 1;
    Microsoft::WRL::Details::StaticStorage<Microsoft::WRL::Details::OutOfProcModuleBase<Windows::Internal::SvcHostModule>::MethodReleaseNotifier<Windows::Internal::Service<ConnectedStorageService,3,Windows::Internal::ServiceModuleBase::SecurityPolicyEveryoneLocalAndRemote,2,Windows::Internal::DefaultServerDescriptor>>,3,Windows::Internal::SvcHostModule>::instance_ = (__int64)&Microsoft::WRL::Details::OutOfProcModuleBase<Windows::Internal::ServiceModule>::MethodReleaseNotifier<Windows::Internal::Service<ConnectedStorageService,3,Windows::Internal::ServiceModuleBase::SecurityPolicyEveryoneLocalAndRemote,2,Windows::Internal::DefaultServerDescriptor>>::`vftable';
    qword_1800C0AE0 = (__int64)wistd::__function::__func<_lambda_8db0ce862824541f40dfb767113f1e28_,bool (void *,unsigned __int64,void *,unsigned __int64,unsigned int)>::destroy;
    v9 = &Microsoft::WRL::Details::StaticStorage<Microsoft::WRL::Details::OutOfProcModuleBase<Windows::Internal::SvcHostModule>::MethodReleaseNotifier<Windows::Internal::Service<ConnectedStorageService,3,Windows::Internal::ServiceModuleBase::SecurityPolicyEveryoneLocalAndRemote,2,Windows::Internal::DefaultServerDescriptor>>,3,Windows::Internal::SvcHostModule>::instance_;
    byte_1800C0AD0 = 0;
    qword_1800C0AD8 = (__int64)v5;
  }
  *(_QWORD *)(v6 + 48) = v9;
LABEL_12:
  **(_QWORD **)(a1 + 16) = v6;
  v10 = Windows::Internal::ServiceModuleBase::Initialize<Windows::Internal::ServiceModuleBase::SecurityPolicyEveryoneLocalAndRemote,2,Windows::Internal::DefaultServerDescriptor>(
          **(LPVOID ***)(a1 + 16),
          **(_BYTE **)(a1 + 8),
          v7,
          v8,
          v13);
  if ( v10 < 0 )
  {
    v11 = 545;
LABEL_14:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v11,
      (unsigned int)"onecore\\internal\\com\\inc\\comservicehelper.h",
      (const char *)(unsigned int)v10,
      v14);
    return (unsigned int)v10;
  }
  v10 = ConnectedStorageService::ServiceStarted(*(ConnectedStorageService **)a1);
  **(_DWORD **)(a1 + 24) = v10;
  if ( v10 < 0 )
  {
    v11 = 547;
    goto LABEL_14;
  }
  v12 = _lambda_249230bd792972bce8c42ec595a35649_::_lambda_249230bd792972bce8c42ec595a35649_(
          (_lambda_249230bd792972bce8c42ec595a35649_ *)&v18,
          *(struct ConnectedStorageService **)a1);
  v16 = 1;
  v15 = *(_QWORD *)v12;
  SetServiceStatus(*(SERVICE_STATUS_HANDLE *)(*(_QWORD *)a1 + 8LL), (LPSERVICE_STATUS)(*(_QWORD *)a1 + 16LL));
  WaitForSingleObject(*(HANDLE *)(*(_QWORD *)a1 + 48LL), 0xFFFFFFFF);
  if ( ((*(_DWORD *)(*(_QWORD *)a1 + 20LL) - 1) & 0xFFFFFFFD) != 0 )
  {
    *(_DWORD *)(*(_QWORD *)a1 + 20LL) = 3;
    SetServiceStatus(*(SERVICE_STATUS_HANDLE *)(*(_QWORD *)a1 + 8LL), (LPSERVICE_STATUS)(*(_QWORD *)a1 + 16LL));
  }
  wil::details::lambda_call<_lambda_b3a628f36f3ab0f7a5f58ea66bbe6304_>::reset(&v15);
  wil::details::lambda_call<_lambda_b3a628f36f3ab0f7a5f58ea66bbe6304_>::reset(&v15);
  return 0;
}

```

## disassembly

```asm
0x18000846c  mov     [rsp+arg_8], rbx
0x180008471  push    rdi
0x180008472  sub     rsp, 50h
0x180008476  mov     r8, [rcx]; lpContext
0x180008479  lea     rdx, ?HandlerExStatic@?$Service@VConnectedStorageService@@$02USecurityPolicyEveryoneLocalAndRemote@ServiceModuleBase@Internal@Windows@@$01UDefaultServerDescriptor@45@@Internal@Windows@@CAKKKPEAX0@Z; lpHandlerProc
0x180008480  mov     rbx, rcx
0x180008483  lea     rcx, ServiceName; "XblGameSave"
0x18000848a  call    cs:__imp_RegisterServiceCtrlHandlerExW
0x180008490  mov     rdx, [rbx]
0x180008493  mov     [rdx+8], rax
0x180008497  mov     rax, [rbx]
0x18000849a  cmp     qword ptr [rax+8], 0
0x18000849f  jnz     short loc_1800084BC
0x1800084a1  mov     edx, 1FDh; void *
0x1800084a6  mov     rcx, [rsp+58h]; this
0x1800084ab  lea     r8, aOnecoreInterna_0; "onecore\\internal\\com\\inc\\comservice"...
0x1800084b2  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1800084b7  jmp     loc_180008657
0x1800084bc  xor     r9d, r9d; lpName
0x1800084bf  xor     r8d, r8d; bInitialState
0x1800084c2  xor     edx, edx; bManualReset
0x1800084c4  xor     ecx, ecx; lpEventAttributes
0x1800084c6  call    cs:__imp_CreateEventW
0x1800084cc  mov     rcx, [rbx]
0x1800084cf  mov     [rcx+30h], rax
0x1800084d3  mov     rdi, [rbx]
0x1800084d6  cmp     qword ptr [rdi+30h], 0
0x1800084db  jnz     short loc_1800084E4
0x1800084dd  mov     edx, 200h
0x1800084e2  jmp     short loc_1800084A6
0x1800084e4  mov     rax, [rbx+8]
0x1800084e8  cmp     byte ptr [rax], 0
0x1800084eb  jz      short loc_18000853A
0x1800084ed  call    ?Create@?$OutOfProcModuleBase@VServiceModule@Internal@Windows@@@Details@WRL@Microsoft@@SAAEAVServiceModule@Internal@Windows@@XZ; Microsoft::WRL::Details::OutOfProcModuleBase<Windows::Internal::ServiceModule>::Create(void)
0x1800084f2  mov     rcx, rax
0x1800084f5  cmp     qword ptr [rax+30h], 0
0x1800084fa  jnz     loc_180008585
0x180008500  lea     rax, ??_7?$MethodReleaseNotifier@V?$Service@VConnectedStorageService@@$02USecurityPolicyEveryoneLocalAndRemote@ServiceModuleBase@Internal@Windows@@$01UDefaultServerDescriptor@45@@Internal@Windows@@@?$OutOfProcModuleBase@VServiceModule@Internal@Windows@@@Details@WRL@Microsoft@@6B@; const Microsoft::WRL::Details::OutOfProcModuleBase<Windows::Internal::ServiceModule>::MethodReleaseNotifier<Windows::Internal::Service<ConnectedStorageService,3,Windows::Internal::ServiceModuleBase::SecurityPolicyEveryoneLocalAndRemote,2,Windows::Internal::DefaultServerDescriptor>>::`vftable'
0x180008507  mov     cs:byte_1800C0AC0, 1
0x18000850e  mov     cs:?instance_@?$StaticStorage@V?$MethodReleaseNotifier@V?$Service@VConnectedStorageService@@$02USecurityPolicyEveryoneLocalAndRemote@ServiceModuleBase@Internal@Windows@@$01UDefaultServerDescriptor@45@@Internal@Windows@@@?$OutOfProcModuleBase@VServiceModule@Internal@Windows@@@Details@WRL@Microsoft@@$02VServiceModule@Internal@Windows@@@Details@WRL@Microsoft@@0V1234@A, rax; Microsoft::WRL::Details::StaticStorage<Microsoft::WRL::Details::OutOfProcModuleBase<Windows::Internal::ServiceModule>::MethodReleaseNotifier<Windows::Internal::Service<ConnectedStorageService,3,Windows::Internal::ServiceModuleBase::SecurityPolicyEveryoneLocalAndRemote,2,Windows::Internal::DefaultServerDescriptor>>,3,Windows::Internal::ServiceModule> Microsoft::WRL::Details::StaticStorage<Microsoft::WRL::Details::OutOfProcModuleBase<Windows::Internal::ServiceModule>::MethodReleaseNotifier<Windows::Internal::Service<ConnectedStorageService,3,Windows::Internal::ServiceModuleBase::SecurityPolicyEveryoneLocalAndRemote,2,Windows::Internal::DefaultServerDescriptor>>,3,Windows::Internal::ServiceModule>::instance_
0x180008515  lea     rax, ?destroy@?$__func@V_lambda_8db0ce862824541f40dfb767113f1e28_@@$$A6A_NPEAX_K01I@Z@__function@wistd@@UEAAXXZ; wistd::__function::__func<_lambda_8db0ce862824541f40dfb767113f1e28_,bool (void *,unsigned __int64,void *,unsigned __int64,uint)>::destroy(void)
0x18000851c  mov     cs:qword_1800C0AB8, rax
0x180008523  lea     rax, ?instance_@?$StaticStorage@V?$MethodReleaseNotifier@V?$Service@VConnectedStorageService@@$02USecurityPolicyEveryoneLocalAndRemote@ServiceModuleBase@Internal@Windows@@$01UDefaultServerDescriptor@45@@Internal@Windows@@@?$OutOfProcModuleBase@VServiceModule@Internal@Windows@@@Details@WRL@Microsoft@@$02VServiceModule@Internal@Windows@@@Details@WRL@Microsoft@@0V1234@A; Microsoft::WRL::Details::StaticStorage<Microsoft::WRL::Details::OutOfProcModuleBase<Windows::Internal::ServiceModule>::MethodReleaseNotifier<Windows::Internal::Service<ConnectedStorageService,3,Windows::Internal::ServiceModuleBase::SecurityPolicyEveryoneLocalAndRemote,2,Windows::Internal::DefaultServerDescriptor>>,3,Windows::Internal::ServiceModule> Microsoft::WRL::Details::StaticStorage<Microsoft::WRL::Details::OutOfProcModuleBase<Windows::Internal::ServiceModule>::MethodReleaseNotifier<Windows::Internal::Service<ConnectedStorageService,3,Windows::Internal::ServiceModuleBase::SecurityPolicyEveryoneLocalAndRemote,2,Windows::Internal::DefaultServerDescriptor>>,3,Windows::Internal::ServiceModule>::instance_
0x18000852a  mov     cs:byte_1800C0AA8, 0
0x180008531  mov     cs:qword_1800C0AB0, rdi
0x180008538  jmp     short loc_180008581
0x18000853a  call    ?Create@?$OutOfProcModuleBase@VSvcHostModule@Internal@Windows@@@Details@WRL@Microsoft@@SAAEAVSvcHostModule@Internal@Windows@@XZ; Microsoft::WRL::Details::OutOfProcModuleBase<Windows::Internal::SvcHostModule>::Create(void)
0x18000853f  mov     rcx, rax
0x180008542  cmp     qword ptr [rax+30h], 0
0x180008547  jnz     short loc_180008585
0x180008549  lea     rax, ??_7?$MethodReleaseNotifier@V?$Service@VConnectedStorageService@@$02USecurityPolicyEveryoneLocalAndRemote@ServiceModuleBase@Internal@Windows@@$01UDefaultServerDescriptor@45@@Internal@Windows@@@?$OutOfProcModuleBase@VServiceModule@Internal@Windows@@@Details@WRL@Microsoft@@6B@; const Microsoft::WRL::Details::OutOfProcModuleBase<Windows::Internal::ServiceModule>::MethodReleaseNotifier<Windows::Internal::Service<ConnectedStorageService,3,Windows::Internal::ServiceModuleBase::SecurityPolicyEveryoneLocalAndRemote,2,Windows::Internal::DefaultServerDescriptor>>::`vftable'
0x180008550  mov     cs:byte_1800C0AE8, 1
0x180008557  mov     cs:?instance_@?$StaticStorage@V?$MethodReleaseNotifier@V?$Service@VConnectedStorageService@@$02USecurityPolicyEveryoneLocalAndRemote@ServiceModuleBase@Internal@Windows@@$01UDefaultServerDescriptor@45@@Internal@Windows@@@?$OutOfProcModuleBase@VSvcHostModule@Internal@Windows@@@Details@WRL@Microsoft@@$02VSvcHostModule@Internal@Windows@@@Details@WRL@Microsoft@@0V1234@A, rax; Microsoft::WRL::Details::StaticStorage<Microsoft::WRL::Details::OutOfProcModuleBase<Windows::Internal::SvcHostModule>::MethodReleaseNotifier<Windows::Internal::Service<ConnectedStorageService,3,Windows::Internal::ServiceModuleBase::SecurityPolicyEveryoneLocalAndRemote,2,Windows::Internal::DefaultServerDescriptor>>,3,Windows::Internal::SvcHostModule> Microsoft::WRL::Details::StaticStorage<Microsoft::WRL::Details::OutOfProcModuleBase<Windows::Internal::SvcHostModule>::MethodReleaseNotifier<Windows::Internal::Service<ConnectedStorageService,3,Windows::Internal::ServiceModuleBase::SecurityPolicyEveryoneLocalAndRemote,2,Windows::Internal::DefaultServerDescriptor>>,3,Windows::Internal::SvcHostModule>::instance_
0x18000855e  lea     rax, ?destroy@?$__func@V_lambda_8db0ce862824541f40dfb767113f1e28_@@$$A6A_NPEAX_K01I@Z@__function@wistd@@UEAAXXZ; wistd::__function::__func<_lambda_8db0ce862824541f40dfb767113f1e28_,bool (void *,unsigned __int64,void *,unsigned __int64,uint)>::destroy(void)
0x180008565  mov     cs:qword_1800C0AE0, rax
0x18000856c  lea     rax, ?instance_@?$StaticStorage@V?$MethodReleaseNotifier@V?$Service@VConnectedStorageService@@$02USecurityPolicyEveryoneLocalAndRemote@ServiceModuleBase@Internal@Windows@@$01UDefaultServerDescriptor@45@@Internal@Windows@@@?$OutOfProcModuleBase@VSvcHostModule@Internal@Windows@@@Details@WRL@Microsoft@@$02VSvcHostModule@Internal@Windows@@@Details@WRL@Microsoft@@0V1234@A; Microsoft::WRL::Details::StaticStorage<Microsoft::WRL::Details::OutOfProcModuleBase<Windows::Internal::SvcHostModule>::MethodReleaseNotifier<Windows::Internal::Service<ConnectedStorageService,3,Windows::Internal::ServiceModuleBase::SecurityPolicyEveryoneLocalAndRemote,2,Windows::Internal::DefaultServerDescriptor>>,3,Windows::Internal::SvcHostModule> Microsoft::WRL::Details::StaticStorage<Microsoft::WRL::Details::OutOfProcModuleBase<Windows::Internal::SvcHostModule>::MethodReleaseNotifier<Windows::Internal::Service<ConnectedStorageService,3,Windows::Internal::ServiceModuleBase::SecurityPolicyEveryoneLocalAndRemote,2,Windows::Internal::DefaultServerDescriptor>>,3,Windows::Internal::SvcHostModule>::instance_
0x180008573  mov     cs:byte_1800C0AD0, 0
0x18000857a  mov     cs:qword_1800C0AD8, rdi
0x180008581  mov     [rcx+30h], rax
0x180008585  mov     rax, [rbx+10h]
0x180008589  mov     [rax], rcx
0x18000858c  mov     rdx, [rbx+8]
0x180008590  mov     rcx, [rbx+10h]
0x180008594  mov     dl, [rdx]
0x180008596  mov     rcx, [rcx]; struct ConnectedStorageService *
0x180008599  call    ??$Initialize@USecurityPolicyEveryoneLocalAndRemote@ServiceModuleBase@Internal@Windows@@$01UDefaultServerDescriptor@34@@ServiceModuleBase@Internal@Windows@@QEAAJEEEEPEAXK@Z; Windows::Internal::ServiceModuleBase::Initialize<Windows::Internal::ServiceModuleBase::SecurityPolicyEveryoneLocalAndRemote,2,Windows::Internal::DefaultServerDescriptor>(uchar,uchar,uchar,uchar,void *,ulong)
0x18000859e  mov     edi, eax
0x1800085a0  test    eax, eax
0x1800085a2  jns     short loc_1800085C4
0x1800085a4  mov     edx, 221h; void *
0x1800085a9  mov     rcx, [rsp+58h]; this
0x1800085ae  lea     r8, aOnecoreInterna_0; "onecore\\internal\\com\\inc\\comservice"...
0x1800085b5  mov     r9d, edi; char *
0x1800085b8  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800085bd  mov     eax, edi
0x1800085bf  jmp     loc_180008657
0x1800085c4  mov     rcx, [rbx]; this
0x1800085c7  call    ?ServiceStarted@ConnectedStorageService@@QEAAJXZ; ConnectedStorageService::ServiceStarted(void)
0x1800085cc  mov     rcx, [rbx+18h]
0x1800085d0  mov     edi, eax
0x1800085d2  mov     [rcx], eax
0x1800085d4  test    eax, eax
0x1800085d6  jns     short loc_1800085DF
0x1800085d8  mov     edx, 223h
0x1800085dd  jmp     short loc_1800085A9
0x1800085df  mov     rdx, [rbx]; struct ConnectedStorageService *
0x1800085e2  lea     rcx, [rsp+58h+arg_0]; this
0x1800085e7  call    ??0_lambda_249230bd792972bce8c42ec595a35649_@@QEAA@PEAVConnectedStorageService@@@Z; _lambda_249230bd792972bce8c42ec595a35649_::_lambda_249230bd792972bce8c42ec595a35649_(ConnectedStorageService *)
0x1800085ec  mov     [rsp+58h+var_10], 1
0x1800085f1  mov     rcx, [rax]
0x1800085f4  mov     [rsp+58h+var_18], rcx
0x1800085f9  mov     rcx, [rbx]
0x1800085fc  lea     rdx, [rcx+10h]; lpServiceStatus
0x180008600  mov     rcx, [rcx+8]; hServiceStatus
0x180008604  call    cs:__imp_SetServiceStatus
0x18000860a  mov     rcx, [rbx]
0x18000860d  or      edx, 0FFFFFFFFh; dwMilliseconds
0x180008610  mov     rcx, [rcx+30h]; hHandle
0x180008614  call    cs:__imp_WaitForSingleObject
0x18000861a  mov     rcx, [rbx]
0x18000861d  mov     eax, [rcx+14h]
0x180008620  dec     eax
0x180008622  test    eax, 0FFFFFFFDh
0x180008627  jz      short loc_180008641
0x180008629  mov     dword ptr [rcx+14h], 3
0x180008630  mov     rcx, [rbx]
0x180008633  lea     rdx, [rcx+10h]; lpServiceStatus
0x180008637  mov     rcx, [rcx+8]; hServiceStatus
0x18000863b  call    cs:__imp_SetServiceStatus
0x180008641  lea     rcx, [rsp+58h+var_18]
0x180008646  call    ?reset@?$lambda_call@V_lambda_b3a628f36f3ab0f7a5f58ea66bbe6304_@@@details@wil@@QEAAXXZ; wil::details::lambda_call<_lambda_b3a628f36f3ab0f7a5f58ea66bbe6304_>::reset(void)
0x18000864b  lea     rcx, [rsp+58h+var_18]
0x180008650  call    ?reset@?$lambda_call@V_lambda_b3a628f36f3ab0f7a5f58ea66bbe6304_@@@details@wil@@QEAAXXZ; wil::details::lambda_call<_lambda_b3a628f36f3ab0f7a5f58ea66bbe6304_>::reset(void)
0x180008655  xor     eax, eax
0x180008657  mov     rbx, [rsp+58h+arg_8]
0x18000865c  add     rsp, 50h
0x180008660  pop     rdi
0x180008661  retn
```
