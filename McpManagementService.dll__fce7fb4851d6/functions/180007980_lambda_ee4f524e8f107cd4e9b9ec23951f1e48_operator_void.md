# _lambda_ee4f524e8f107cd4e9b9ec23951f1e48_::operator()(void)

- ea: `0x180007980`
- end: `0x180007ba4`
- name: `??R_lambda_ee4f524e8f107cd4e9b9ec23951f1e48_@@QEBA@XZ`
- size: `548`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `1`
- callee_count: `10`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x18000c570`

## callees

- `0x180004d1c`
- `0x1800050e4`
- `0x180007980`
- `0x1800085bc`
- `0x1800085f4`
- `0x1800098d8`
- `0x18000c4ac`
- `0x18000c4cc`
- `0x18000df30`
- `0x18000e708`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180007b56`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180007b56`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800079da`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800079da`
- `api-ms-win-service-core-l1-1-0!RegisterServiceCtrlHandlerExW` at `0x18000799e`
- `api-ms-win-service-core-l1-1-0!RegisterServiceCtrlHandlerExW` at `0x18000799e`
- `api-ms-win-service-core-l1-1-0!SetServiceStatus` at `0x180007b46`
- `api-ms-win-service-core-l1-1-0!SetServiceStatus` at `0x180007b7d`
- `api-ms-win-service-core-l1-1-0!SetServiceStatus` at `0x180007b46`
- `api-ms-win-service-core-l1-1-0!SetServiceStatus` at `0x180007b7d`

## string_xrefs

- `0x1800079bf`: `onecore\internal\com\inc\comservicehelper.h`
- `0x180007ae2`: `onecore\internal\com\inc\comservicehelper.h`
- `0x180007997`: `McpManagementService`
- `0x180007afd`: `McpManagementService`
- `0x180007b0b`: `McpManagementService::ServiceStarted`

## pseudocode

```c
// Hidden C++ exception states: #wind=9
__int64 __fastcall _lambda_ee4f524e8f107cd4e9b9ec23951f1e48_::operator()(__int64 a1)
{
  const char *v2; // r9
  __int64 v3; // rdx
  LPVOID v5; // rdi
  McpManagementService *v6; // rcx
  __int64 *v7; // rax
  unsigned int ShutdownDelay; // eax
  __int64 v9; // r9
  int v10; // eax
  unsigned int v11; // edi
  __int64 *v12; // rax
  int v13; // [rsp+20h] [rbp-38h]
  __int64 v14; // [rsp+40h] [rbp-18h] BYREF
  char v15; // [rsp+48h] [rbp-10h]
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+0h]
  __int64 v17; // [rsp+60h] [rbp+8h] BYREF

  *(_QWORD *)(*(_QWORD *)a1 + 8LL) = RegisterServiceCtrlHandlerExW(
                                       L"McpManagementService",
                                       Windows::Internal::Service<McpManagementService,2,Windows::Internal::ServiceModuleBase::SecurityPolicyEveryoneLocal,2,Windows::Internal::DefaultServerDescriptor>::HandlerExStatic,
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
    v6 = (McpManagementService *)Microsoft::WRL::Details::OutOfProcModuleBase<Windows::Internal::ServiceModule>::Create();
    if ( *((_QWORD *)v6 + 6) )
      goto LABEL_12;
    byte_18003F958 = 1;
    Microsoft::WRL::Details::StaticStorage<Microsoft::WRL::Details::OutOfProcModuleBase<Windows::Internal::ServiceModule>::MethodReleaseNotifier<Windows::Internal::Service<McpManagementService,2,Windows::Internal::ServiceModuleBase::SecurityPolicyEveryoneLocal,2,Windows::Internal::DefaultServerDescriptor>>,3,Windows::Internal::ServiceModule>::instance_ = (__int64)&Microsoft::WRL::Details::OutOfProcModuleBase<Windows::Internal::SvcHostModule>::MethodReleaseNotifier<Windows::Internal::Service<McpManagementService,2,Windows::Internal::ServiceModuleBase::SecurityPolicyEveryoneLocal,2,Windows::Internal::DefaultServerDescriptor>>::`vftable';
    qword_18003F950 = (__int64)wistd::__function::__func<_lambda_8db0ce862824541f40dfb767113f1e28_,bool (void *,unsigned __int64,void *,unsigned __int64,unsigned int)>::destroy;
    v7 = &Microsoft::WRL::Details::StaticStorage<Microsoft::WRL::Details::OutOfProcModuleBase<Windows::Internal::ServiceModule>::MethodReleaseNotifier<Windows::Internal::Service<McpManagementService,2,Windows::Internal::ServiceModuleBase::SecurityPolicyEveryoneLocal,2,Windows::Internal::DefaultServerDescriptor>>,3,Windows::Internal::ServiceModule>::instance_;
    byte_18003F940 = 0;
    qword_18003F948 = (__int64)v5;
  }
  else
  {
    v6 = (McpManagementService *)Microsoft::WRL::Details::OutOfProcModuleBase<Windows::Internal::SvcHostModule>::Create();
    if ( *((_QWORD *)v6 + 6) )
      goto LABEL_12;
    byte_18003F9C8 = 1;
    Microsoft::WRL::Details::StaticStorage<Microsoft::WRL::Details::OutOfProcModuleBase<Windows::Internal::SvcHostModule>::MethodReleaseNotifier<Windows::Internal::Service<McpManagementService,2,Windows::Internal::ServiceModuleBase::SecurityPolicyEveryoneLocal,2,Windows::Internal::DefaultServerDescriptor>>,3,Windows::Internal::SvcHostModule>::instance_ = (__int64)&Microsoft::WRL::Details::OutOfProcModuleBase<Windows::Internal::SvcHostModule>::MethodReleaseNotifier<Windows::Internal::Service<McpManagementService,2,Windows::Internal::ServiceModuleBase::SecurityPolicyEveryoneLocal,2,Windows::Internal::DefaultServerDescriptor>>::`vftable';
    qword_18003F9C0 = (__int64)wistd::__function::__func<_lambda_8db0ce862824541f40dfb767113f1e28_,bool (void *,unsigned __int64,void *,unsigned __int64,unsigned int)>::destroy;
    v7 = &Microsoft::WRL::Details::StaticStorage<Microsoft::WRL::Details::OutOfProcModuleBase<Windows::Internal::SvcHostModule>::MethodReleaseNotifier<Windows::Internal::Service<McpManagementService,2,Windows::Internal::ServiceModuleBase::SecurityPolicyEveryoneLocal,2,Windows::Internal::DefaultServerDescriptor>>,3,Windows::Internal::SvcHostModule>::instance_;
    byte_18003F9B0 = 0;
    qword_18003F9B8 = (__int64)v5;
  }
  *((_QWORD *)v6 + 6) = v7;
LABEL_12:
  **(_QWORD **)(a1 + 16) = v6;
  ShutdownDelay = McpManagementService::GetShutdownDelay(v6);
  LOBYTE(v9) = ShutdownDelay != -1;
  v10 = Windows::Internal::ServiceModuleBase::Initialize<Windows::Internal::ServiceModuleBase::SecurityPolicyEveryoneLocal,2,Windows::Internal::DefaultServerDescriptor>(
          **(_DWORD ***)(a1 + 16),
          **(_BYTE **)(a1 + 8),
          ShutdownDelay == -1,
          v9,
          v9,
          *(_QWORD *)(*(_QWORD *)a1 + 48LL),
          ShutdownDelay);
  v11 = v10;
  if ( v10 >= 0 )
  {
    McpManagementTelemetry::WriteDbgTraceInfo(
      "McpManagementService::ServiceStarted",
      L"%s Started",
      L"McpManagementService");
    **(_DWORD **)(a1 + 24) = 0;
    v12 = _lambda_5b5155d6716aa02bd4bfa3a7051e2a37_::_lambda_5b5155d6716aa02bd4bfa3a7051e2a37_(&v17, *(_QWORD *)a1);
    v15 = 1;
    v14 = *v12;
    SetServiceStatus(*(SERVICE_STATUS_HANDLE *)(*(_QWORD *)a1 + 8LL), (LPSERVICE_STATUS)(*(_QWORD *)a1 + 16LL));
    WaitForSingleObject(*(HANDLE *)(*(_QWORD *)a1 + 48LL), 0xFFFFFFFF);
    if ( ((*(_DWORD *)(*(_QWORD *)a1 + 20LL) - 1) & 0xFFFFFFFD) != 0 )
    {
      *(_DWORD *)(*(_QWORD *)a1 + 20LL) = 3;
      SetServiceStatus(*(SERVICE_STATUS_HANDLE *)(*(_QWORD *)a1 + 8LL), (LPSERVICE_STATUS)(*(_QWORD *)a1 + 16LL));
    }
    wil::details::lambda_call<_lambda_5b5155d6716aa02bd4bfa3a7051e2a37_>::reset(&v14);
    wil::details::lambda_call<_lambda_5b5155d6716aa02bd4bfa3a7051e2a37_>::reset(&v14);
    return 0;
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x221,
      (unsigned int)"onecore\\internal\\com\\inc\\comservicehelper.h",
      (const char *)(unsigned int)v10,
      v13);
    return v11;
  }
}

```

## disassembly

```asm
0x180007980  mov     [rsp+arg_8], rbx
0x180007985  push    rdi
0x180007986  sub     rsp, 50h
0x18000798a  mov     r8, [rcx]; lpContext
0x18000798d  lea     rdx, ?HandlerExStatic@?$Service@VMcpManagementService@@$01USecurityPolicyEveryoneLocal@ServiceModuleBase@Internal@Windows@@$01UDefaultServerDescriptor@45@@Internal@Windows@@CAKKKPEAX0@Z; lpHandlerProc
0x180007994  mov     rbx, rcx
0x180007997  lea     rcx, ServiceName; "McpManagementService"
0x18000799e  call    cs:__imp_RegisterServiceCtrlHandlerExW
0x1800079a4  mov     rdx, [rbx]
0x1800079a7  mov     [rdx+8], rax
0x1800079ab  mov     rax, [rbx]
0x1800079ae  cmp     qword ptr [rax+8], 0
0x1800079b3  jnz     short loc_1800079D0
0x1800079b5  mov     edx, 1FDh; void *
0x1800079ba  mov     rcx, [rsp+58h]; this
0x1800079bf  lea     r8, aOnecoreInterna_0; "onecore\\internal\\com\\inc\\comservice"...
0x1800079c6  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1800079cb  jmp     loc_180007B99
0x1800079d0  xor     r9d, r9d; lpName
0x1800079d3  xor     r8d, r8d; bInitialState
0x1800079d6  xor     edx, edx; bManualReset
0x1800079d8  xor     ecx, ecx; lpEventAttributes
0x1800079da  call    cs:__imp_CreateEventW
0x1800079e0  mov     rcx, [rbx]
0x1800079e3  mov     [rcx+30h], rax
0x1800079e7  mov     rdi, [rbx]
0x1800079ea  cmp     qword ptr [rdi+30h], 0
0x1800079ef  jnz     short loc_1800079F8
0x1800079f1  mov     edx, 200h
0x1800079f6  jmp     short loc_1800079BA
0x1800079f8  mov     rax, [rbx+8]
0x1800079fc  cmp     byte ptr [rax], 0
0x1800079ff  jz      short loc_180007A4E
0x180007a01  call    ?Create@?$OutOfProcModuleBase@VServiceModule@Internal@Windows@@@Details@WRL@Microsoft@@SAAEAVServiceModule@Internal@Windows@@XZ; Microsoft::WRL::Details::OutOfProcModuleBase<Windows::Internal::ServiceModule>::Create(void)
0x180007a06  mov     rcx, rax
0x180007a09  cmp     qword ptr [rax+30h], 0
0x180007a0e  jnz     loc_180007A99
0x180007a14  lea     rax, ??_7?$MethodReleaseNotifier@V?$Service@VMcpManagementService@@$01USecurityPolicyEveryoneLocal@ServiceModuleBase@Internal@Windows@@$01UDefaultServerDescriptor@45@@Internal@Windows@@@?$OutOfProcModuleBase@VSvcHostModule@Internal@Windows@@@Details@WRL@Microsoft@@6B@; const Microsoft::WRL::Details::OutOfProcModuleBase<Windows::Internal::SvcHostModule>::MethodReleaseNotifier<Windows::Internal::Service<McpManagementService,2,Windows::Internal::ServiceModuleBase::SecurityPolicyEveryoneLocal,2,Windows::Internal::DefaultServerDescriptor>>::`vftable'
0x180007a1b  mov     cs:byte_18003F958, 1
0x180007a22  mov     cs:?instance_@?$StaticStorage@V?$MethodReleaseNotifier@V?$Service@VMcpManagementService@@$01USecurityPolicyEveryoneLocal@ServiceModuleBase@Internal@Windows@@$01UDefaultServerDescriptor@45@@Internal@Windows@@@?$OutOfProcModuleBase@VServiceModule@Internal@Windows@@@Details@WRL@Microsoft@@$02VServiceModule@Internal@Windows@@@Details@WRL@Microsoft@@0V1234@A, rax; Microsoft::WRL::Details::StaticStorage<Microsoft::WRL::Details::OutOfProcModuleBase<Windows::Internal::ServiceModule>::MethodReleaseNotifier<Windows::Internal::Service<McpManagementService,2,Windows::Internal::ServiceModuleBase::SecurityPolicyEveryoneLocal,2,Windows::Internal::DefaultServerDescriptor>>,3,Windows::Internal::ServiceModule> Microsoft::WRL::Details::StaticStorage<Microsoft::WRL::Details::OutOfProcModuleBase<Windows::Internal::ServiceModule>::MethodReleaseNotifier<Windows::Internal::Service<McpManagementService,2,Windows::Internal::ServiceModuleBase::SecurityPolicyEveryoneLocal,2,Windows::Internal::DefaultServerDescriptor>>,3,Windows::Internal::ServiceModule>::instance_
0x180007a29  lea     rax, ?destroy@?$__func@V_lambda_8db0ce862824541f40dfb767113f1e28_@@$$A6A_NPEAX_K01I@Z@__function@wistd@@UEAAXXZ; wistd::__function::__func<_lambda_8db0ce862824541f40dfb767113f1e28_,bool (void *,unsigned __int64,void *,unsigned __int64,uint)>::destroy(void)
0x180007a30  mov     cs:qword_18003F950, rax
0x180007a37  lea     rax, ?instance_@?$StaticStorage@V?$MethodReleaseNotifier@V?$Service@VMcpManagementService@@$01USecurityPolicyEveryoneLocal@ServiceModuleBase@Internal@Windows@@$01UDefaultServerDescriptor@45@@Internal@Windows@@@?$OutOfProcModuleBase@VServiceModule@Internal@Windows@@@Details@WRL@Microsoft@@$02VServiceModule@Internal@Windows@@@Details@WRL@Microsoft@@0V1234@A; Microsoft::WRL::Details::StaticStorage<Microsoft::WRL::Details::OutOfProcModuleBase<Windows::Internal::ServiceModule>::MethodReleaseNotifier<Windows::Internal::Service<McpManagementService,2,Windows::Internal::ServiceModuleBase::SecurityPolicyEveryoneLocal,2,Windows::Internal::DefaultServerDescriptor>>,3,Windows::Internal::ServiceModule> Microsoft::WRL::Details::StaticStorage<Microsoft::WRL::Details::OutOfProcModuleBase<Windows::Internal::ServiceModule>::MethodReleaseNotifier<Windows::Internal::Service<McpManagementService,2,Windows::Internal::ServiceModuleBase::SecurityPolicyEveryoneLocal,2,Windows::Internal::DefaultServerDescriptor>>,3,Windows::Internal::ServiceModule>::instance_
0x180007a3e  mov     cs:byte_18003F940, 0
0x180007a45  mov     cs:qword_18003F948, rdi
0x180007a4c  jmp     short loc_180007A95
0x180007a4e  call    ?Create@?$OutOfProcModuleBase@VSvcHostModule@Internal@Windows@@@Details@WRL@Microsoft@@SAAEAVSvcHostModule@Internal@Windows@@XZ; Microsoft::WRL::Details::OutOfProcModuleBase<Windows::Internal::SvcHostModule>::Create(void)
0x180007a53  mov     rcx, rax; this
0x180007a56  cmp     qword ptr [rax+30h], 0
0x180007a5b  jnz     short loc_180007A99
0x180007a5d  lea     rax, ??_7?$MethodReleaseNotifier@V?$Service@VMcpManagementService@@$01USecurityPolicyEveryoneLocal@ServiceModuleBase@Internal@Windows@@$01UDefaultServerDescriptor@45@@Internal@Windows@@@?$OutOfProcModuleBase@VSvcHostModule@Internal@Windows@@@Details@WRL@Microsoft@@6B@; const Microsoft::WRL::Details::OutOfProcModuleBase<Windows::Internal::SvcHostModule>::MethodReleaseNotifier<Windows::Internal::Service<McpManagementService,2,Windows::Internal::ServiceModuleBase::SecurityPolicyEveryoneLocal,2,Windows::Internal::DefaultServerDescriptor>>::`vftable'
0x180007a64  mov     cs:byte_18003F9C8, 1
0x180007a6b  mov     cs:?instance_@?$StaticStorage@V?$MethodReleaseNotifier@V?$Service@VMcpManagementService@@$01USecurityPolicyEveryoneLocal@ServiceModuleBase@Internal@Windows@@$01UDefaultServerDescriptor@45@@Internal@Windows@@@?$OutOfProcModuleBase@VSvcHostModule@Internal@Windows@@@Details@WRL@Microsoft@@$02VSvcHostModule@Internal@Windows@@@Details@WRL@Microsoft@@0V1234@A, rax; Microsoft::WRL::Details::StaticStorage<Microsoft::WRL::Details::OutOfProcModuleBase<Windows::Internal::SvcHostModule>::MethodReleaseNotifier<Windows::Internal::Service<McpManagementService,2,Windows::Internal::ServiceModuleBase::SecurityPolicyEveryoneLocal,2,Windows::Internal::DefaultServerDescriptor>>,3,Windows::Internal::SvcHostModule> Microsoft::WRL::Details::StaticStorage<Microsoft::WRL::Details::OutOfProcModuleBase<Windows::Internal::SvcHostModule>::MethodReleaseNotifier<Windows::Internal::Service<McpManagementService,2,Windows::Internal::ServiceModuleBase::SecurityPolicyEveryoneLocal,2,Windows::Internal::DefaultServerDescriptor>>,3,Windows::Internal::SvcHostModule>::instance_
0x180007a72  lea     rax, ?destroy@?$__func@V_lambda_8db0ce862824541f40dfb767113f1e28_@@$$A6A_NPEAX_K01I@Z@__function@wistd@@UEAAXXZ; wistd::__function::__func<_lambda_8db0ce862824541f40dfb767113f1e28_,bool (void *,unsigned __int64,void *,unsigned __int64,uint)>::destroy(void)
0x180007a79  mov     cs:qword_18003F9C0, rax
0x180007a80  lea     rax, ?instance_@?$StaticStorage@V?$MethodReleaseNotifier@V?$Service@VMcpManagementService@@$01USecurityPolicyEveryoneLocal@ServiceModuleBase@Internal@Windows@@$01UDefaultServerDescriptor@45@@Internal@Windows@@@?$OutOfProcModuleBase@VSvcHostModule@Internal@Windows@@@Details@WRL@Microsoft@@$02VSvcHostModule@Internal@Windows@@@Details@WRL@Microsoft@@0V1234@A; Microsoft::WRL::Details::StaticStorage<Microsoft::WRL::Details::OutOfProcModuleBase<Windows::Internal::SvcHostModule>::MethodReleaseNotifier<Windows::Internal::Service<McpManagementService,2,Windows::Internal::ServiceModuleBase::SecurityPolicyEveryoneLocal,2,Windows::Internal::DefaultServerDescriptor>>,3,Windows::Internal::SvcHostModule> Microsoft::WRL::Details::StaticStorage<Microsoft::WRL::Details::OutOfProcModuleBase<Windows::Internal::SvcHostModule>::MethodReleaseNotifier<Windows::Internal::Service<McpManagementService,2,Windows::Internal::ServiceModuleBase::SecurityPolicyEveryoneLocal,2,Windows::Internal::DefaultServerDescriptor>>,3,Windows::Internal::SvcHostModule>::instance_
0x180007a87  mov     cs:byte_18003F9B0, 0
0x180007a8e  mov     cs:qword_18003F9B8, rdi
0x180007a95  mov     [rcx+30h], rax
0x180007a99  mov     rax, [rbx+10h]
0x180007a9d  mov     [rax], rcx
0x180007aa0  call    ?GetShutdownDelay@McpManagementService@@QEAAKXZ; McpManagementService::GetShutdownDelay(void)
0x180007aa5  mov     r10, [rbx]
0x180007aa8  cmp     eax, 0FFFFFFFFh
0x180007aab  mov     rdx, [rbx+8]
0x180007aaf  mov     rcx, [rbx+10h]
0x180007ab3  setnz   r9b
0x180007ab7  mov     [rsp+58h+var_28], eax
0x180007abb  setz    r8b
0x180007abf  mov     rax, [r10+30h]
0x180007ac3  mov     dl, [rdx]
0x180007ac5  mov     rcx, [rcx]
0x180007ac8  mov     [rsp+58h+var_30], rax
0x180007acd  mov     byte ptr [rsp+58h+var_38], r9b; int
0x180007ad2  call    ??$Initialize@USecurityPolicyEveryoneLocal@ServiceModuleBase@Internal@Windows@@$01UDefaultServerDescriptor@34@@ServiceModuleBase@Internal@Windows@@QEAAJEEEEPEAXK@Z; Windows::Internal::ServiceModuleBase::Initialize<Windows::Internal::ServiceModuleBase::SecurityPolicyEveryoneLocal,2,Windows::Internal::DefaultServerDescriptor>(uchar,uchar,uchar,uchar,void *,ulong)
0x180007ad7  mov     edi, eax
0x180007ad9  test    eax, eax
0x180007adb  jns     short loc_180007AFD
0x180007add  mov     rcx, [rsp+58h]; this
0x180007ae2  lea     r8, aOnecoreInterna_0; "onecore\\internal\\com\\inc\\comservice"...
0x180007ae9  mov     r9d, eax; char *
0x180007aec  mov     edx, 221h; void *
0x180007af1  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180007af6  mov     eax, edi
0x180007af8  jmp     loc_180007B99
0x180007afd  lea     r8, ServiceName; "McpManagementService"
0x180007b04  lea     rdx, aSStarted; "%s Started"
0x180007b0b  lea     rcx, aMcpmanagements_2; "McpManagementService::ServiceStarted"
0x180007b12  call    ?WriteDbgTraceInfo@McpManagementTelemetry@@SAXPEADPEAGZZ; McpManagementTelemetry::WriteDbgTraceInfo(char *,ushort *,...)
0x180007b17  mov     rax, [rbx+18h]
0x180007b1b  lea     rcx, [rsp+58h+arg_0]
0x180007b20  mov     dword ptr [rax], 0
0x180007b26  mov     rdx, [rbx]
0x180007b29  call    ??0_lambda_5b5155d6716aa02bd4bfa3a7051e2a37_@@QEAA@PEAV?$Service@VMcpManagementService@@$01USecurityPolicyEveryoneLocal@ServiceModuleBase@Internal@Windows@@$01UDefaultServerDescriptor@45@@Internal@Windows@@@Z; _lambda_5b5155d6716aa02bd4bfa3a7051e2a37_::_lambda_5b5155d6716aa02bd4bfa3a7051e2a37_(Windows::Internal::Service<McpManagementService,2,Windows::Internal::ServiceModuleBase::SecurityPolicyEveryoneLocal,2,Windows::Internal::DefaultServerDescriptor> *)
0x180007b2e  mov     [rsp+58h+var_10], 1
0x180007b33  mov     rcx, [rax]
0x180007b36  mov     [rsp+58h+var_18], rcx
0x180007b3b  mov     rcx, [rbx]
0x180007b3e  lea     rdx, [rcx+10h]; lpServiceStatus
0x180007b42  mov     rcx, [rcx+8]; hServiceStatus
0x180007b46  call    cs:__imp_SetServiceStatus
0x180007b4c  mov     rcx, [rbx]
0x180007b4f  or      edx, 0FFFFFFFFh; dwMilliseconds
0x180007b52  mov     rcx, [rcx+30h]; hHandle
0x180007b56  call    cs:__imp_WaitForSingleObject
0x180007b5c  mov     rcx, [rbx]
0x180007b5f  mov     eax, [rcx+14h]
0x180007b62  dec     eax
0x180007b64  test    eax, 0FFFFFFFDh
0x180007b69  jz      short loc_180007B83
0x180007b6b  mov     dword ptr [rcx+14h], 3
0x180007b72  mov     rcx, [rbx]
0x180007b75  lea     rdx, [rcx+10h]; lpServiceStatus
0x180007b79  mov     rcx, [rcx+8]; hServiceStatus
0x180007b7d  call    cs:__imp_SetServiceStatus
0x180007b83  lea     rcx, [rsp+58h+var_18]
0x180007b88  call    ?reset@?$lambda_call@V_lambda_5b5155d6716aa02bd4bfa3a7051e2a37_@@@details@wil@@QEAAXXZ; wil::details::lambda_call<_lambda_5b5155d6716aa02bd4bfa3a7051e2a37_>::reset(void)
0x180007b8d  lea     rcx, [rsp+58h+var_18]
0x180007b92  call    ?reset@?$lambda_call@V_lambda_5b5155d6716aa02bd4bfa3a7051e2a37_@@@details@wil@@QEAAXXZ; wil::details::lambda_call<_lambda_5b5155d6716aa02bd4bfa3a7051e2a37_>::reset(void)
0x180007b97  xor     eax, eax
0x180007b99  mov     rbx, [rsp+58h+arg_8]
0x180007b9e  add     rsp, 50h
0x180007ba2  pop     rdi
0x180007ba3  retn
```
