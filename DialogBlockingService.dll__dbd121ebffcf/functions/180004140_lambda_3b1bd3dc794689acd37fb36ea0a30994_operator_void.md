# _lambda_3b1bd3dc794689acd37fb36ea0a30994_::operator()(void)

- ea: `0x180004140`
- end: `0x180004374`
- name: `??R_lambda_3b1bd3dc794689acd37fb36ea0a30994_@@QEBA@XZ`
- size: `564`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `1`
- callee_count: `7`
- tags: `file_ops, registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x180007fa0`

## callees

- `0x180001644`
- `0x1800023c8`
- `0x180004140`
- `0x1800067e4`
- `0x180006804`
- `0x180006890`
- `0x1800099d8`

## import_xrefs

- `api-ms-win-core-synch-l1-2-0!InitOnceExecuteOnce` at `0x1800041d5`
- `api-ms-win-core-synch-l1-2-0!InitOnceExecuteOnce` at `0x180004242`
- `api-ms-win-core-synch-l1-2-0!InitOnceExecuteOnce` at `0x1800041d5`
- `api-ms-win-core-synch-l1-2-0!InitOnceExecuteOnce` at `0x180004242`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18000419a`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18000419a`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180004314`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180004314`
- `api-ms-win-service-core-l1-1-0!RegisterServiceCtrlHandlerExW` at `0x18000415e`
- `api-ms-win-service-core-l1-1-0!RegisterServiceCtrlHandlerExW` at `0x18000415e`
- `api-ms-win-service-core-l1-1-0!SetServiceStatus` at `0x180004304`
- `api-ms-win-service-core-l1-1-0!SetServiceStatus` at `0x18000433b`
- `api-ms-win-service-core-l1-1-0!SetServiceStatus` at `0x180004304`
- `api-ms-win-service-core-l1-1-0!SetServiceStatus` at `0x18000433b`

## string_xrefs

- `0x18000417f`: `onecore\internal\com\inc\comservicehelper.h`
- `0x1800042c8`: `onecore\internal\com\inc\comservicehelper.h`
- `0x180004157`: `DialogBlockingService`

## pseudocode

```c
__int64 __fastcall _lambda_3b1bd3dc794689acd37fb36ea0a30994_::operator()(__int64 a1)
{
  const char *v2; // r9
  __int64 v3; // rdx
  LPVOID v5; // rdi
  __int64 *v6; // rcx
  int v7; // edi
  __int64 v8; // rdx
  LPVOID v9; // rdi
  Windows::Internal::DialogBlocking::ServiceSessions *v10; // rbx
  int v11; // [rsp+20h] [rbp-28h]
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+0h]

  *(_QWORD *)(*(_QWORD *)a1 + 8LL) = RegisterServiceCtrlHandlerExW(
                                       L"DialogBlockingService",
                                       Windows::Internal::Service<DialogBlockingService,1,Windows::Internal::ServiceModuleBase::SecurityPolicyEveryoneLocal,2,Windows::Internal::DefaultServerDescriptor>::HandlerExStatic,
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
    InitOnceExecuteOnce(
      &Microsoft::WRL::Details::OutOfProcModuleBase<Windows::Internal::ServiceModule>::initOnceOutOfProc_,
      _lambda_0436b89998ddae64b987abcfc9f7e79b_::_lambda_invoker_cdecl_,
      0,
      0);
    byte_180014568 = 1;
    if ( !qword_180014560 )
    {
      byte_1800144A0 = 1;
      Microsoft::WRL::Details::StaticStorage<Microsoft::WRL::Details::OutOfProcModuleBase<Windows::Internal::ServiceModule>::MethodReleaseNotifier<Windows::Internal::Service<DialogBlockingService,1,Windows::Internal::ServiceModuleBase::SecurityPolicyEveryoneLocal,2,Windows::Internal::DefaultServerDescriptor>>,3,Windows::Internal::ServiceModule>::instance_ = (__int64)&Microsoft::WRL::Details::OutOfProcModuleBase<Windows::Internal::SvcHostModule>::MethodReleaseNotifier<Windows::Internal::Service<DialogBlockingService,1,Windows::Internal::ServiceModuleBase::SecurityPolicyEveryoneLocal,2,Windows::Internal::DefaultServerDescriptor>>::`vftable';
      qword_180014498 = (__int64)Windows::Internal::Service<DialogBlockingService,1,Windows::Internal::ServiceModuleBase::SecurityPolicyEveryoneLocal,2,Windows::Internal::DefaultServerDescriptor>::StopAsync;
      qword_180014560 = (__int64)&Microsoft::WRL::Details::StaticStorage<Microsoft::WRL::Details::OutOfProcModuleBase<Windows::Internal::ServiceModule>::MethodReleaseNotifier<Windows::Internal::Service<DialogBlockingService,1,Windows::Internal::ServiceModuleBase::SecurityPolicyEveryoneLocal,2,Windows::Internal::DefaultServerDescriptor>>,3,Windows::Internal::ServiceModule>::instance_;
      byte_180014488 = 0;
      qword_180014490 = (__int64)v5;
    }
    v6 = &Microsoft::WRL::Details::StaticStorage<Windows::Internal::ServiceModule,1,int>::instance_;
  }
  else
  {
    InitOnceExecuteOnce(
      &Microsoft::WRL::Details::OutOfProcModuleBase<Windows::Internal::SvcHostModule>::initOnceOutOfProc_,
      _lambda_253709c146e3c4eefdc38a0c994771db_::_lambda_invoker_cdecl_,
      0,
      0);
    byte_180014520 = 1;
    if ( !qword_180014510 )
    {
      byte_1800144D0 = 1;
      Microsoft::WRL::Details::StaticStorage<Microsoft::WRL::Details::OutOfProcModuleBase<Windows::Internal::SvcHostModule>::MethodReleaseNotifier<Windows::Internal::Service<DialogBlockingService,1,Windows::Internal::ServiceModuleBase::SecurityPolicyEveryoneLocal,2,Windows::Internal::DefaultServerDescriptor>>,3,Windows::Internal::SvcHostModule>::instance_ = (__int64)&Microsoft::WRL::Details::OutOfProcModuleBase<Windows::Internal::SvcHostModule>::MethodReleaseNotifier<Windows::Internal::Service<DialogBlockingService,1,Windows::Internal::ServiceModuleBase::SecurityPolicyEveryoneLocal,2,Windows::Internal::DefaultServerDescriptor>>::`vftable';
      qword_1800144C8 = (__int64)Windows::Internal::Service<DialogBlockingService,1,Windows::Internal::ServiceModuleBase::SecurityPolicyEveryoneLocal,2,Windows::Internal::DefaultServerDescriptor>::StopAsync;
      qword_180014510 = (__int64)&Microsoft::WRL::Details::StaticStorage<Microsoft::WRL::Details::OutOfProcModuleBase<Windows::Internal::SvcHostModule>::MethodReleaseNotifier<Windows::Internal::Service<DialogBlockingService,1,Windows::Internal::ServiceModuleBase::SecurityPolicyEveryoneLocal,2,Windows::Internal::DefaultServerDescriptor>>,3,Windows::Internal::SvcHostModule>::instance_;
      byte_1800144B8 = 0;
      qword_1800144C0 = (__int64)v5;
    }
    v6 = &Microsoft::WRL::Details::StaticStorage<Windows::Internal::SvcHostModule,1,int>::instance_;
  }
  **(_QWORD **)(a1 + 16) = v6;
  v7 = Windows::Internal::ServiceModuleBase::Initialize<Windows::Internal::ServiceModuleBase::SecurityPolicyEveryoneLocal,2,Windows::Internal::DefaultServerDescriptor>(
         **(Windows::Internal::ServiceModuleBase ***)(a1 + 16),
         **(_BYTE **)(a1 + 8));
  if ( v7 < 0 )
  {
    v8 = 545;
LABEL_15:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v8,
      (unsigned int)"onecore\\internal\\com\\inc\\comservicehelper.h",
      (const char *)(unsigned int)v7,
      v11);
    return (unsigned int)v7;
  }
  v7 = DialogBlockingService::ServiceStarted(*(DialogBlockingService **)a1);
  **(_DWORD **)(a1 + 24) = v7;
  if ( v7 < 0 )
  {
    v8 = 547;
    goto LABEL_15;
  }
  v9 = *(LPVOID *)a1;
  SetServiceStatus(*(SERVICE_STATUS_HANDLE *)(*(_QWORD *)a1 + 8LL), (LPSERVICE_STATUS)(*(_QWORD *)a1 + 16LL));
  WaitForSingleObject(*(HANDLE *)(*(_QWORD *)a1 + 48LL), 0xFFFFFFFF);
  if ( ((*(_DWORD *)(*(_QWORD *)a1 + 20LL) - 1) & 0xFFFFFFFD) != 0 )
  {
    *(_DWORD *)(*(_QWORD *)a1 + 20LL) = 3;
    SetServiceStatus(*(SERVICE_STATUS_HANDLE *)(*(_QWORD *)a1 + 8LL), (LPSERVICE_STATUS)(*(_QWORD *)a1 + 16LL));
  }
  v10 = (Windows::Internal::DialogBlocking::ServiceSessions *)*((_QWORD *)v9 + 7);
  *((_QWORD *)v9 + 7) = 0;
  if ( v10 )
  {
    Windows::Internal::DialogBlocking::ServiceSessions::~ServiceSessions(v10);
    operator delete(v10);
  }
  return 0;
}

```

## disassembly

```asm
0x180004140  mov     [rsp+arg_0], rbx
0x180004145  push    rdi
0x180004146  sub     rsp, 40h
0x18000414a  mov     r8, [rcx]; lpContext
0x18000414d  lea     rdx, ?HandlerExStatic@?$Service@VDialogBlockingService@@$00USecurityPolicyEveryoneLocal@ServiceModuleBase@Internal@Windows@@$01UDefaultServerDescriptor@45@@Internal@Windows@@CAKKKPEAX0@Z; lpHandlerProc
0x180004154  mov     rbx, rcx
0x180004157  lea     rcx, ServiceName; "DialogBlockingService"
0x18000415e  call    cs:__imp_RegisterServiceCtrlHandlerExW
0x180004164  mov     rdx, [rbx]
0x180004167  mov     [rdx+8], rax
0x18000416b  mov     rax, [rbx]
0x18000416e  cmp     qword ptr [rax+8], 0
0x180004173  jnz     short loc_180004190
0x180004175  mov     edx, 1FDh; void *
0x18000417a  mov     rcx, [rsp+48h]; this
0x18000417f  lea     r8, aOnecoreInterna; "onecore\\internal\\com\\inc\\comservice"...
0x180004186  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18000418b  jmp     loc_180004369
0x180004190  xor     r9d, r9d; lpName
0x180004193  xor     r8d, r8d; bInitialState
0x180004196  xor     edx, edx; bManualReset
0x180004198  xor     ecx, ecx; lpEventAttributes
0x18000419a  call    cs:__imp_CreateEventW
0x1800041a0  mov     rcx, [rbx]
0x1800041a3  mov     [rcx+30h], rax
0x1800041a7  mov     rdi, [rbx]
0x1800041aa  cmp     qword ptr [rdi+30h], 0
0x1800041af  jnz     short loc_1800041B8
0x1800041b1  mov     edx, 200h
0x1800041b6  jmp     short loc_18000417A
0x1800041b8  mov     rax, [rbx+8]
0x1800041bc  xor     r9d, r9d; Context
0x1800041bf  xor     r8d, r8d; Parameter
0x1800041c2  cmp     [rax], r8b
0x1800041c5  jz      short loc_180004234
0x1800041c7  lea     rdx, ?_lambda_invoker_cdecl_@_lambda_0436b89998ddae64b987abcfc9f7e79b_@@CAHPEAT_RTL_RUN_ONCE@@PEAXPEAPEAX@Z; InitFn
0x1800041ce  lea     rcx, ?initOnceOutOfProc_@?$OutOfProcModuleBase@VServiceModule@Internal@Windows@@@Details@WRL@Microsoft@@1T_RTL_RUN_ONCE@@A; InitOnce
0x1800041d5  call    cs:__imp_InitOnceExecuteOnce
0x1800041db  cmp     cs:qword_180014560, 0
0x1800041e3  mov     cs:byte_180014568, 1
0x1800041ea  jnz     short loc_18000422B
0x1800041ec  lea     rax, ??_7?$MethodReleaseNotifier@V?$Service@VDialogBlockingService@@$00USecurityPolicyEveryoneLocal@ServiceModuleBase@Internal@Windows@@$01UDefaultServerDescriptor@45@@Internal@Windows@@@?$OutOfProcModuleBase@VSvcHostModule@Internal@Windows@@@Details@WRL@Microsoft@@6B@; const Microsoft::WRL::Details::OutOfProcModuleBase<Windows::Internal::SvcHostModule>::MethodReleaseNotifier<Windows::Internal::Service<DialogBlockingService,1,Windows::Internal::ServiceModuleBase::SecurityPolicyEveryoneLocal,2,Windows::Internal::DefaultServerDescriptor>>::`vftable'
0x1800041f3  mov     cs:byte_1800144A0, 1
0x1800041fa  mov     cs:?instance_@?$StaticStorage@V?$MethodReleaseNotifier@V?$Service@VDialogBlockingService@@$00USecurityPolicyEveryoneLocal@ServiceModuleBase@Internal@Windows@@$01UDefaultServerDescriptor@45@@Internal@Windows@@@?$OutOfProcModuleBase@VServiceModule@Internal@Windows@@@Details@WRL@Microsoft@@$02VServiceModule@Internal@Windows@@@Details@WRL@Microsoft@@0V1234@A, rax; Microsoft::WRL::Details::StaticStorage<Microsoft::WRL::Details::OutOfProcModuleBase<Windows::Internal::ServiceModule>::MethodReleaseNotifier<Windows::Internal::Service<DialogBlockingService,1,Windows::Internal::ServiceModuleBase::SecurityPolicyEveryoneLocal,2,Windows::Internal::DefaultServerDescriptor>>,3,Windows::Internal::ServiceModule> Microsoft::WRL::Details::StaticStorage<Microsoft::WRL::Details::OutOfProcModuleBase<Windows::Internal::ServiceModule>::MethodReleaseNotifier<Windows::Internal::Service<DialogBlockingService,1,Windows::Internal::ServiceModuleBase::SecurityPolicyEveryoneLocal,2,Windows::Internal::DefaultServerDescriptor>>,3,Windows::Internal::ServiceModule>::instance_
0x180004201  lea     rax, ?StopAsync@?$Service@VDialogBlockingService@@$00USecurityPolicyEveryoneLocal@ServiceModuleBase@Internal@Windows@@$01UDefaultServerDescriptor@45@@Internal@Windows@@IEAAXXZ; Windows::Internal::Service<DialogBlockingService,1,Windows::Internal::ServiceModuleBase::SecurityPolicyEveryoneLocal,2,Windows::Internal::DefaultServerDescriptor>::StopAsync(void)
0x180004208  mov     cs:qword_180014498, rax
0x18000420f  lea     rax, ?instance_@?$StaticStorage@V?$MethodReleaseNotifier@V?$Service@VDialogBlockingService@@$00USecurityPolicyEveryoneLocal@ServiceModuleBase@Internal@Windows@@$01UDefaultServerDescriptor@45@@Internal@Windows@@@?$OutOfProcModuleBase@VServiceModule@Internal@Windows@@@Details@WRL@Microsoft@@$02VServiceModule@Internal@Windows@@@Details@WRL@Microsoft@@0V1234@A; Microsoft::WRL::Details::StaticStorage<Microsoft::WRL::Details::OutOfProcModuleBase<Windows::Internal::ServiceModule>::MethodReleaseNotifier<Windows::Internal::Service<DialogBlockingService,1,Windows::Internal::ServiceModuleBase::SecurityPolicyEveryoneLocal,2,Windows::Internal::DefaultServerDescriptor>>,3,Windows::Internal::ServiceModule> Microsoft::WRL::Details::StaticStorage<Microsoft::WRL::Details::OutOfProcModuleBase<Windows::Internal::ServiceModule>::MethodReleaseNotifier<Windows::Internal::Service<DialogBlockingService,1,Windows::Internal::ServiceModuleBase::SecurityPolicyEveryoneLocal,2,Windows::Internal::DefaultServerDescriptor>>,3,Windows::Internal::ServiceModule>::instance_
0x180004216  mov     cs:qword_180014560, rax
0x18000421d  mov     cs:byte_180014488, 0
0x180004224  mov     cs:qword_180014490, rdi
0x18000422b  lea     rcx, ?instance_@?$StaticStorage@VServiceModule@Internal@Windows@@$00H@Details@WRL@Microsoft@@0V1234@A; Microsoft::WRL::Details::StaticStorage<Windows::Internal::ServiceModule,1,int> Microsoft::WRL::Details::StaticStorage<Windows::Internal::ServiceModule,1,int>::instance_
0x180004232  jmp     short loc_18000429F
0x180004234  lea     rdx, ?_lambda_invoker_cdecl_@_lambda_253709c146e3c4eefdc38a0c994771db_@@CAHPEAT_RTL_RUN_ONCE@@PEAXPEAPEAX@Z; InitFn
0x18000423b  lea     rcx, ?initOnceOutOfProc_@?$OutOfProcModuleBase@VSvcHostModule@Internal@Windows@@@Details@WRL@Microsoft@@1T_RTL_RUN_ONCE@@A; InitOnce
0x180004242  call    cs:__imp_InitOnceExecuteOnce
0x180004248  cmp     cs:qword_180014510, 0
0x180004250  mov     cs:byte_180014520, 1
0x180004257  jnz     short loc_180004298
0x180004259  lea     rax, ??_7?$MethodReleaseNotifier@V?$Service@VDialogBlockingService@@$00USecurityPolicyEveryoneLocal@ServiceModuleBase@Internal@Windows@@$01UDefaultServerDescriptor@45@@Internal@Windows@@@?$OutOfProcModuleBase@VSvcHostModule@Internal@Windows@@@Details@WRL@Microsoft@@6B@; const Microsoft::WRL::Details::OutOfProcModuleBase<Windows::Internal::SvcHostModule>::MethodReleaseNotifier<Windows::Internal::Service<DialogBlockingService,1,Windows::Internal::ServiceModuleBase::SecurityPolicyEveryoneLocal,2,Windows::Internal::DefaultServerDescriptor>>::`vftable'
0x180004260  mov     cs:byte_1800144D0, 1
0x180004267  mov     cs:?instance_@?$StaticStorage@V?$MethodReleaseNotifier@V?$Service@VDialogBlockingService@@$00USecurityPolicyEveryoneLocal@ServiceModuleBase@Internal@Windows@@$01UDefaultServerDescriptor@45@@Internal@Windows@@@?$OutOfProcModuleBase@VSvcHostModule@Internal@Windows@@@Details@WRL@Microsoft@@$02VSvcHostModule@Internal@Windows@@@Details@WRL@Microsoft@@0V1234@A, rax; Microsoft::WRL::Details::StaticStorage<Microsoft::WRL::Details::OutOfProcModuleBase<Windows::Internal::SvcHostModule>::MethodReleaseNotifier<Windows::Internal::Service<DialogBlockingService,1,Windows::Internal::ServiceModuleBase::SecurityPolicyEveryoneLocal,2,Windows::Internal::DefaultServerDescriptor>>,3,Windows::Internal::SvcHostModule> Microsoft::WRL::Details::StaticStorage<Microsoft::WRL::Details::OutOfProcModuleBase<Windows::Internal::SvcHostModule>::MethodReleaseNotifier<Windows::Internal::Service<DialogBlockingService,1,Windows::Internal::ServiceModuleBase::SecurityPolicyEveryoneLocal,2,Windows::Internal::DefaultServerDescriptor>>,3,Windows::Internal::SvcHostModule>::instance_
0x18000426e  lea     rax, ?StopAsync@?$Service@VDialogBlockingService@@$00USecurityPolicyEveryoneLocal@ServiceModuleBase@Internal@Windows@@$01UDefaultServerDescriptor@45@@Internal@Windows@@IEAAXXZ; Windows::Internal::Service<DialogBlockingService,1,Windows::Internal::ServiceModuleBase::SecurityPolicyEveryoneLocal,2,Windows::Internal::DefaultServerDescriptor>::StopAsync(void)
0x180004275  mov     cs:qword_1800144C8, rax
0x18000427c  lea     rax, ?instance_@?$StaticStorage@V?$MethodReleaseNotifier@V?$Service@VDialogBlockingService@@$00USecurityPolicyEveryoneLocal@ServiceModuleBase@Internal@Windows@@$01UDefaultServerDescriptor@45@@Internal@Windows@@@?$OutOfProcModuleBase@VSvcHostModule@Internal@Windows@@@Details@WRL@Microsoft@@$02VSvcHostModule@Internal@Windows@@@Details@WRL@Microsoft@@0V1234@A; Microsoft::WRL::Details::StaticStorage<Microsoft::WRL::Details::OutOfProcModuleBase<Windows::Internal::SvcHostModule>::MethodReleaseNotifier<Windows::Internal::Service<DialogBlockingService,1,Windows::Internal::ServiceModuleBase::SecurityPolicyEveryoneLocal,2,Windows::Internal::DefaultServerDescriptor>>,3,Windows::Internal::SvcHostModule> Microsoft::WRL::Details::StaticStorage<Microsoft::WRL::Details::OutOfProcModuleBase<Windows::Internal::SvcHostModule>::MethodReleaseNotifier<Windows::Internal::Service<DialogBlockingService,1,Windows::Internal::ServiceModuleBase::SecurityPolicyEveryoneLocal,2,Windows::Internal::DefaultServerDescriptor>>,3,Windows::Internal::SvcHostModule>::instance_
0x180004283  mov     cs:qword_180014510, rax
0x18000428a  mov     cs:byte_1800144B8, 0
0x180004291  mov     cs:qword_1800144C0, rdi
0x180004298  lea     rcx, ?instance_@?$StaticStorage@VSvcHostModule@Internal@Windows@@$00H@Details@WRL@Microsoft@@0V1234@A; Microsoft::WRL::Details::StaticStorage<Windows::Internal::SvcHostModule,1,int> Microsoft::WRL::Details::StaticStorage<Windows::Internal::SvcHostModule,1,int>::instance_
0x18000429f  mov     rax, [rbx+10h]
0x1800042a3  mov     [rax], rcx
0x1800042a6  mov     rdx, [rbx+8]
0x1800042aa  mov     rcx, [rbx+10h]
0x1800042ae  mov     dl, [rdx]
0x1800042b0  mov     rcx, [rcx]
0x1800042b3  call    ??$Initialize@USecurityPolicyEveryoneLocal@ServiceModuleBase@Internal@Windows@@$01UDefaultServerDescriptor@34@@ServiceModuleBase@Internal@Windows@@QEAAJEEEEPEAXK@Z; Windows::Internal::ServiceModuleBase::Initialize<Windows::Internal::ServiceModuleBase::SecurityPolicyEveryoneLocal,2,Windows::Internal::DefaultServerDescriptor>(uchar,uchar,uchar,uchar,void *,ulong)
0x1800042b8  mov     edi, eax
0x1800042ba  test    eax, eax
0x1800042bc  jns     short loc_1800042DE
0x1800042be  mov     edx, 221h; void *
0x1800042c3  mov     rcx, [rsp+48h]; this
0x1800042c8  lea     r8, aOnecoreInterna; "onecore\\internal\\com\\inc\\comservice"...
0x1800042cf  mov     r9d, edi; char *
0x1800042d2  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800042d7  mov     eax, edi
0x1800042d9  jmp     loc_180004369
0x1800042de  mov     rcx, [rbx]; this
0x1800042e1  call    ?ServiceStarted@DialogBlockingService@@QEAAJXZ; DialogBlockingService::ServiceStarted(void)
0x1800042e6  mov     rcx, [rbx+18h]
0x1800042ea  mov     edi, eax
0x1800042ec  mov     [rcx], eax
0x1800042ee  test    eax, eax
0x1800042f0  jns     short loc_1800042F9
0x1800042f2  mov     edx, 223h
0x1800042f7  jmp     short loc_1800042C3
0x1800042f9  mov     rdi, [rbx]
0x1800042fc  mov     rcx, [rdi+8]; hServiceStatus
0x180004300  lea     rdx, [rdi+10h]; lpServiceStatus
0x180004304  call    cs:__imp_SetServiceStatus
0x18000430a  mov     rcx, [rbx]
0x18000430d  or      edx, 0FFFFFFFFh; dwMilliseconds
0x180004310  mov     rcx, [rcx+30h]; hHandle
0x180004314  call    cs:__imp_WaitForSingleObject
0x18000431a  mov     rcx, [rbx]
0x18000431d  mov     eax, [rcx+14h]
0x180004320  dec     eax
0x180004322  test    eax, 0FFFFFFFDh
0x180004327  jz      short loc_180004341
0x180004329  mov     dword ptr [rcx+14h], 3
0x180004330  mov     rcx, [rbx]
0x180004333  lea     rdx, [rcx+10h]; lpServiceStatus
0x180004337  mov     rcx, [rcx+8]; hServiceStatus
0x18000433b  call    cs:__imp_SetServiceStatus
0x180004341  mov     rbx, [rdi+38h]
0x180004345  mov     qword ptr [rdi+38h], 0
0x18000434d  test    rbx, rbx
0x180004350  jz      short loc_180004367
0x180004352  mov     rcx, rbx; this
0x180004355  call    ??1ServiceSessions@DialogBlocking@Internal@Windows@@QEAA@XZ; Windows::Internal::DialogBlocking::ServiceSessions::~ServiceSessions(void)
0x18000435a  mov     edx, 60h ; '`'; unsigned __int64
0x18000435f  mov     rcx, rbx; void *
0x180004362  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180004367  xor     eax, eax
0x180004369  mov     rbx, [rsp+48h+arg_0]
0x18000436e  add     rsp, 40h
0x180004372  pop     rdi
0x180004373  retn
```
