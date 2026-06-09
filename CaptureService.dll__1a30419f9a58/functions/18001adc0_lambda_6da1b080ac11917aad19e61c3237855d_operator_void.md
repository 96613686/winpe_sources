# _lambda_6da1b080ac11917aad19e61c3237855d_::operator()(void)

- ea: `0x18001adc0`
- end: `0x18001af81`
- name: `??R_lambda_6da1b080ac11917aad19e61c3237855d_@@QEBA@XZ`
- size: `449`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x18001b750`

## callees

- `0x180003edc`
- `0x18000603c`
- `0x180006074`
- `0x18000905c`
- `0x18000907c`
- `0x18001a538`
- `0x18001adc0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18001ae1a`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18001ae1a`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18001af47`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18001af47`
- `api-ms-win-service-core-l1-1-0!SetServiceStatus` at `0x18001af37`
- `api-ms-win-service-core-l1-1-0!SetServiceStatus` at `0x18001af6e`
- `api-ms-win-service-core-l1-1-0!SetServiceStatus` at `0x18001af37`
- `api-ms-win-service-core-l1-1-0!SetServiceStatus` at `0x18001af6e`
- `api-ms-win-service-core-l1-1-0!RegisterServiceCtrlHandlerExW` at `0x18001adde`
- `api-ms-win-service-core-l1-1-0!RegisterServiceCtrlHandlerExW` at `0x18001adde`

## string_xrefs

- `0x18001adff`: `onecore\internal\com\inc\comservicehelper.h`
- `0x18001aefd`: `onecore\internal\com\inc\comservicehelper.h`
- `0x18001add7`: `CaptureService`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall _lambda_6da1b080ac11917aad19e61c3237855d_::operator()(__int64 a1)
{
  const char *v2; // r9
  __int64 v3; // rdx
  LPVOID v5; // rdi
  __int64 v6; // rcx
  __int64 v7; // r8
  __int64 v8; // r9
  __int64 *v9; // rax
  int v10; // eax
  unsigned int v11; // edi
  __int64 v12; // [rsp+20h] [rbp-28h]
  int v13; // [rsp+20h] [rbp-28h]
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+0h]
  __int64 v15; // [rsp+50h] [rbp+8h] BYREF

  *(_QWORD *)(*(_QWORD *)a1 + 8LL) = RegisterServiceCtrlHandlerExW(
                                       L"CaptureService",
                                       Windows::Internal::Service<CCaptureService,1,Windows::Internal::ServiceModuleBase::SecurityPolicyEveryoneLocal,2,Windows::Internal::DefaultServerDescriptor>::HandlerExStatic,
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
    byte_180033150 = 1;
    Microsoft::WRL::Details::StaticStorage<Microsoft::WRL::Details::OutOfProcModuleBase<Windows::Internal::ServiceModule>::MethodReleaseNotifier<Windows::Internal::Service<CCaptureService,1,Windows::Internal::ServiceModuleBase::SecurityPolicyEveryoneLocal,2,Windows::Internal::DefaultServerDescriptor>>,3,Windows::Internal::ServiceModule>::instance_ = (__int64)&Microsoft::WRL::Details::OutOfProcModuleBase<Windows::Internal::SvcHostModule>::MethodReleaseNotifier<Windows::Internal::Service<CCaptureService,1,Windows::Internal::ServiceModuleBase::SecurityPolicyEveryoneLocal,2,Windows::Internal::DefaultServerDescriptor>>::`vftable';
    qword_180033148 = (__int64)Windows::Internal::Service<CCaptureService,1,Windows::Internal::ServiceModuleBase::SecurityPolicyEveryoneLocal,2,Windows::Internal::DefaultServerDescriptor>::StopAsync;
    v9 = &Microsoft::WRL::Details::StaticStorage<Microsoft::WRL::Details::OutOfProcModuleBase<Windows::Internal::ServiceModule>::MethodReleaseNotifier<Windows::Internal::Service<CCaptureService,1,Windows::Internal::ServiceModuleBase::SecurityPolicyEveryoneLocal,2,Windows::Internal::DefaultServerDescriptor>>,3,Windows::Internal::ServiceModule>::instance_;
    byte_180033138 = 0;
    qword_180033140 = (__int64)v5;
  }
  else
  {
    v6 = Microsoft::WRL::Details::OutOfProcModuleBase<Windows::Internal::SvcHostModule>::Create();
    if ( *(_QWORD *)(v6 + 48) )
      goto LABEL_12;
    byte_180033178 = 1;
    Microsoft::WRL::Details::StaticStorage<Microsoft::WRL::Details::OutOfProcModuleBase<Windows::Internal::SvcHostModule>::MethodReleaseNotifier<Windows::Internal::Service<CCaptureService,1,Windows::Internal::ServiceModuleBase::SecurityPolicyEveryoneLocal,2,Windows::Internal::DefaultServerDescriptor>>,3,Windows::Internal::SvcHostModule>::instance_ = (__int64)&Microsoft::WRL::Details::OutOfProcModuleBase<Windows::Internal::SvcHostModule>::MethodReleaseNotifier<Windows::Internal::Service<CCaptureService,1,Windows::Internal::ServiceModuleBase::SecurityPolicyEveryoneLocal,2,Windows::Internal::DefaultServerDescriptor>>::`vftable';
    qword_180033170 = (__int64)Windows::Internal::Service<CCaptureService,1,Windows::Internal::ServiceModuleBase::SecurityPolicyEveryoneLocal,2,Windows::Internal::DefaultServerDescriptor>::StopAsync;
    v9 = &Microsoft::WRL::Details::StaticStorage<Microsoft::WRL::Details::OutOfProcModuleBase<Windows::Internal::SvcHostModule>::MethodReleaseNotifier<Windows::Internal::Service<CCaptureService,1,Windows::Internal::ServiceModuleBase::SecurityPolicyEveryoneLocal,2,Windows::Internal::DefaultServerDescriptor>>,3,Windows::Internal::SvcHostModule>::instance_;
    byte_180033160 = 0;
    qword_180033168 = (__int64)v5;
  }
  *(_QWORD *)(v6 + 48) = v9;
LABEL_12:
  **(_QWORD **)(a1 + 16) = v6;
  v10 = Windows::Internal::ServiceModuleBase::Initialize<Windows::Internal::ServiceModuleBase::SecurityPolicyEveryoneLocal,2,Windows::Internal::DefaultServerDescriptor>(
          **(_QWORD **)(a1 + 16),
          **(_BYTE **)(a1 + 8),
          v7,
          v8,
          v12);
  v11 = v10;
  if ( v10 >= 0 )
  {
    **(_DWORD **)(a1 + 24) = 0;
    wistd::unique_ptr<void,wil::process_heap_deleter>::unique_ptr<void,wil::process_heap_deleter>(&v15, *(_QWORD *)a1);
    SetServiceStatus(*(SERVICE_STATUS_HANDLE *)(*(_QWORD *)a1 + 8LL), (LPSERVICE_STATUS)(*(_QWORD *)a1 + 16LL));
    WaitForSingleObject(*(HANDLE *)(*(_QWORD *)a1 + 48LL), 0xFFFFFFFF);
    if ( ((*(_DWORD *)(*(_QWORD *)a1 + 20LL) - 1) & 0xFFFFFFFD) != 0 )
    {
      *(_DWORD *)(*(_QWORD *)a1 + 20LL) = 3;
      SetServiceStatus(*(SERVICE_STATUS_HANDLE *)(*(_QWORD *)a1 + 8LL), (LPSERVICE_STATUS)(*(_QWORD *)a1 + 16LL));
    }
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
0x18001adc0  mov     [rsp+arg_8], rbx
0x18001adc5  push    rdi
0x18001adc6  sub     rsp, 40h
0x18001adca  mov     r8, [rcx]; lpContext
0x18001adcd  lea     rdx, ?HandlerExStatic@?$Service@VCCaptureService@@$00USecurityPolicyEveryoneLocal@ServiceModuleBase@Internal@Windows@@$01UDefaultServerDescriptor@45@@Internal@Windows@@CAKKKPEAX0@Z; lpHandlerProc
0x18001add4  mov     rbx, rcx
0x18001add7  lea     rcx, ServiceName; "CaptureService"
0x18001adde  call    cs:__imp_RegisterServiceCtrlHandlerExW
0x18001ade4  mov     rdx, [rbx]
0x18001ade7  mov     [rdx+8], rax
0x18001adeb  mov     rax, [rbx]
0x18001adee  cmp     qword ptr [rax+8], 0
0x18001adf3  jnz     short loc_18001AE10
0x18001adf5  mov     edx, 1FDh; void *
0x18001adfa  mov     rcx, [rsp+48h]; this
0x18001adff  lea     r8, aOnecoreInterna_0; "onecore\\internal\\com\\inc\\comservice"...
0x18001ae06  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18001ae0b  jmp     loc_18001AF76
0x18001ae10  xor     r9d, r9d; lpName
0x18001ae13  xor     r8d, r8d; bInitialState
0x18001ae16  xor     edx, edx; bManualReset
0x18001ae18  xor     ecx, ecx; lpEventAttributes
0x18001ae1a  call    cs:__imp_CreateEventW
0x18001ae20  mov     rcx, [rbx]
0x18001ae23  mov     [rcx+30h], rax
0x18001ae27  mov     rdi, [rbx]
0x18001ae2a  cmp     qword ptr [rdi+30h], 0
0x18001ae2f  jnz     short loc_18001AE38
0x18001ae31  mov     edx, 200h
0x18001ae36  jmp     short loc_18001ADFA
0x18001ae38  mov     rax, [rbx+8]
0x18001ae3c  cmp     byte ptr [rax], 0
0x18001ae3f  jz      short loc_18001AE8E
0x18001ae41  call    ?Create@?$OutOfProcModuleBase@VServiceModule@Internal@Windows@@@Details@WRL@Microsoft@@SAAEAVServiceModule@Internal@Windows@@XZ; Microsoft::WRL::Details::OutOfProcModuleBase<Windows::Internal::ServiceModule>::Create(void)
0x18001ae46  mov     rcx, rax
0x18001ae49  cmp     qword ptr [rax+30h], 0
0x18001ae4e  jnz     loc_18001AED9
0x18001ae54  lea     rax, ??_7?$MethodReleaseNotifier@V?$Service@VCCaptureService@@$00USecurityPolicyEveryoneLocal@ServiceModuleBase@Internal@Windows@@$01UDefaultServerDescriptor@45@@Internal@Windows@@@?$OutOfProcModuleBase@VSvcHostModule@Internal@Windows@@@Details@WRL@Microsoft@@6B@; const Microsoft::WRL::Details::OutOfProcModuleBase<Windows::Internal::SvcHostModule>::MethodReleaseNotifier<Windows::Internal::Service<CCaptureService,1,Windows::Internal::ServiceModuleBase::SecurityPolicyEveryoneLocal,2,Windows::Internal::DefaultServerDescriptor>>::`vftable'
0x18001ae5b  mov     cs:byte_180033150, 1
0x18001ae62  mov     cs:?instance_@?$StaticStorage@V?$MethodReleaseNotifier@V?$Service@VCCaptureService@@$00USecurityPolicyEveryoneLocal@ServiceModuleBase@Internal@Windows@@$01UDefaultServerDescriptor@45@@Internal@Windows@@@?$OutOfProcModuleBase@VServiceModule@Internal@Windows@@@Details@WRL@Microsoft@@$02VServiceModule@Internal@Windows@@@Details@WRL@Microsoft@@0V1234@A, rax; Microsoft::WRL::Details::StaticStorage<Microsoft::WRL::Details::OutOfProcModuleBase<Windows::Internal::ServiceModule>::MethodReleaseNotifier<Windows::Internal::Service<CCaptureService,1,Windows::Internal::ServiceModuleBase::SecurityPolicyEveryoneLocal,2,Windows::Internal::DefaultServerDescriptor>>,3,Windows::Internal::ServiceModule> Microsoft::WRL::Details::StaticStorage<Microsoft::WRL::Details::OutOfProcModuleBase<Windows::Internal::ServiceModule>::MethodReleaseNotifier<Windows::Internal::Service<CCaptureService,1,Windows::Internal::ServiceModuleBase::SecurityPolicyEveryoneLocal,2,Windows::Internal::DefaultServerDescriptor>>,3,Windows::Internal::ServiceModule>::instance_
0x18001ae69  lea     rax, ?StopAsync@?$Service@VCCaptureService@@$00USecurityPolicyEveryoneLocal@ServiceModuleBase@Internal@Windows@@$01UDefaultServerDescriptor@45@@Internal@Windows@@IEAAXXZ; Windows::Internal::Service<CCaptureService,1,Windows::Internal::ServiceModuleBase::SecurityPolicyEveryoneLocal,2,Windows::Internal::DefaultServerDescriptor>::StopAsync(void)
0x18001ae70  mov     cs:qword_180033148, rax
0x18001ae77  lea     rax, ?instance_@?$StaticStorage@V?$MethodReleaseNotifier@V?$Service@VCCaptureService@@$00USecurityPolicyEveryoneLocal@ServiceModuleBase@Internal@Windows@@$01UDefaultServerDescriptor@45@@Internal@Windows@@@?$OutOfProcModuleBase@VServiceModule@Internal@Windows@@@Details@WRL@Microsoft@@$02VServiceModule@Internal@Windows@@@Details@WRL@Microsoft@@0V1234@A; Microsoft::WRL::Details::StaticStorage<Microsoft::WRL::Details::OutOfProcModuleBase<Windows::Internal::ServiceModule>::MethodReleaseNotifier<Windows::Internal::Service<CCaptureService,1,Windows::Internal::ServiceModuleBase::SecurityPolicyEveryoneLocal,2,Windows::Internal::DefaultServerDescriptor>>,3,Windows::Internal::ServiceModule> Microsoft::WRL::Details::StaticStorage<Microsoft::WRL::Details::OutOfProcModuleBase<Windows::Internal::ServiceModule>::MethodReleaseNotifier<Windows::Internal::Service<CCaptureService,1,Windows::Internal::ServiceModuleBase::SecurityPolicyEveryoneLocal,2,Windows::Internal::DefaultServerDescriptor>>,3,Windows::Internal::ServiceModule>::instance_
0x18001ae7e  mov     cs:byte_180033138, 0
0x18001ae85  mov     cs:qword_180033140, rdi
0x18001ae8c  jmp     short loc_18001AED5
0x18001ae8e  call    ?Create@?$OutOfProcModuleBase@VSvcHostModule@Internal@Windows@@@Details@WRL@Microsoft@@SAAEAVSvcHostModule@Internal@Windows@@XZ; Microsoft::WRL::Details::OutOfProcModuleBase<Windows::Internal::SvcHostModule>::Create(void)
0x18001ae93  mov     rcx, rax
0x18001ae96  cmp     qword ptr [rax+30h], 0
0x18001ae9b  jnz     short loc_18001AED9
0x18001ae9d  lea     rax, ??_7?$MethodReleaseNotifier@V?$Service@VCCaptureService@@$00USecurityPolicyEveryoneLocal@ServiceModuleBase@Internal@Windows@@$01UDefaultServerDescriptor@45@@Internal@Windows@@@?$OutOfProcModuleBase@VSvcHostModule@Internal@Windows@@@Details@WRL@Microsoft@@6B@; const Microsoft::WRL::Details::OutOfProcModuleBase<Windows::Internal::SvcHostModule>::MethodReleaseNotifier<Windows::Internal::Service<CCaptureService,1,Windows::Internal::ServiceModuleBase::SecurityPolicyEveryoneLocal,2,Windows::Internal::DefaultServerDescriptor>>::`vftable'
0x18001aea4  mov     cs:byte_180033178, 1
0x18001aeab  mov     cs:?instance_@?$StaticStorage@V?$MethodReleaseNotifier@V?$Service@VCCaptureService@@$00USecurityPolicyEveryoneLocal@ServiceModuleBase@Internal@Windows@@$01UDefaultServerDescriptor@45@@Internal@Windows@@@?$OutOfProcModuleBase@VSvcHostModule@Internal@Windows@@@Details@WRL@Microsoft@@$02VSvcHostModule@Internal@Windows@@@Details@WRL@Microsoft@@0V1234@A, rax; Microsoft::WRL::Details::StaticStorage<Microsoft::WRL::Details::OutOfProcModuleBase<Windows::Internal::SvcHostModule>::MethodReleaseNotifier<Windows::Internal::Service<CCaptureService,1,Windows::Internal::ServiceModuleBase::SecurityPolicyEveryoneLocal,2,Windows::Internal::DefaultServerDescriptor>>,3,Windows::Internal::SvcHostModule> Microsoft::WRL::Details::StaticStorage<Microsoft::WRL::Details::OutOfProcModuleBase<Windows::Internal::SvcHostModule>::MethodReleaseNotifier<Windows::Internal::Service<CCaptureService,1,Windows::Internal::ServiceModuleBase::SecurityPolicyEveryoneLocal,2,Windows::Internal::DefaultServerDescriptor>>,3,Windows::Internal::SvcHostModule>::instance_
0x18001aeb2  lea     rax, ?StopAsync@?$Service@VCCaptureService@@$00USecurityPolicyEveryoneLocal@ServiceModuleBase@Internal@Windows@@$01UDefaultServerDescriptor@45@@Internal@Windows@@IEAAXXZ; Windows::Internal::Service<CCaptureService,1,Windows::Internal::ServiceModuleBase::SecurityPolicyEveryoneLocal,2,Windows::Internal::DefaultServerDescriptor>::StopAsync(void)
0x18001aeb9  mov     cs:qword_180033170, rax
0x18001aec0  lea     rax, ?instance_@?$StaticStorage@V?$MethodReleaseNotifier@V?$Service@VCCaptureService@@$00USecurityPolicyEveryoneLocal@ServiceModuleBase@Internal@Windows@@$01UDefaultServerDescriptor@45@@Internal@Windows@@@?$OutOfProcModuleBase@VSvcHostModule@Internal@Windows@@@Details@WRL@Microsoft@@$02VSvcHostModule@Internal@Windows@@@Details@WRL@Microsoft@@0V1234@A; Microsoft::WRL::Details::StaticStorage<Microsoft::WRL::Details::OutOfProcModuleBase<Windows::Internal::SvcHostModule>::MethodReleaseNotifier<Windows::Internal::Service<CCaptureService,1,Windows::Internal::ServiceModuleBase::SecurityPolicyEveryoneLocal,2,Windows::Internal::DefaultServerDescriptor>>,3,Windows::Internal::SvcHostModule> Microsoft::WRL::Details::StaticStorage<Microsoft::WRL::Details::OutOfProcModuleBase<Windows::Internal::SvcHostModule>::MethodReleaseNotifier<Windows::Internal::Service<CCaptureService,1,Windows::Internal::ServiceModuleBase::SecurityPolicyEveryoneLocal,2,Windows::Internal::DefaultServerDescriptor>>,3,Windows::Internal::SvcHostModule>::instance_
0x18001aec7  mov     cs:byte_180033160, 0
0x18001aece  mov     cs:qword_180033168, rdi
0x18001aed5  mov     [rcx+30h], rax
0x18001aed9  mov     rax, [rbx+10h]
0x18001aedd  mov     [rax], rcx
0x18001aee0  mov     rdx, [rbx+8]
0x18001aee4  mov     rcx, [rbx+10h]
0x18001aee8  mov     dl, [rdx]
0x18001aeea  mov     rcx, [rcx]
0x18001aeed  call    ??$Initialize@USecurityPolicyEveryoneLocal@ServiceModuleBase@Internal@Windows@@$01UDefaultServerDescriptor@34@@ServiceModuleBase@Internal@Windows@@QEAAJEEEEPEAXK@Z; Windows::Internal::ServiceModuleBase::Initialize<Windows::Internal::ServiceModuleBase::SecurityPolicyEveryoneLocal,2,Windows::Internal::DefaultServerDescriptor>(uchar,uchar,uchar,uchar,void *,ulong)
0x18001aef2  mov     edi, eax
0x18001aef4  test    eax, eax
0x18001aef6  jns     short loc_18001AF15
0x18001aef8  mov     rcx, [rsp+48h]; this
0x18001aefd  lea     r8, aOnecoreInterna_0; "onecore\\internal\\com\\inc\\comservice"...
0x18001af04  mov     r9d, eax; char *
0x18001af07  mov     edx, 221h; void *
0x18001af0c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001af11  mov     eax, edi
0x18001af13  jmp     short loc_18001AF76
0x18001af15  mov     rax, [rbx+18h]
0x18001af19  lea     rcx, [rsp+48h+arg_0]
0x18001af1e  mov     dword ptr [rax], 0
0x18001af24  mov     rdx, [rbx]
0x18001af27  call    ??$?0$00X@?$unique_ptr@XUprocess_heap_deleter@wil@@@wistd@@QEAA@PEAX@Z; wistd::unique_ptr<void,wil::process_heap_deleter>::unique_ptr<void,wil::process_heap_deleter>(void *)
0x18001af2c  mov     rcx, [rbx]
0x18001af2f  lea     rdx, [rcx+10h]; lpServiceStatus
0x18001af33  mov     rcx, [rcx+8]; hServiceStatus
0x18001af37  call    cs:__imp_SetServiceStatus
0x18001af3d  mov     rcx, [rbx]
0x18001af40  or      edx, 0FFFFFFFFh; dwMilliseconds
0x18001af43  mov     rcx, [rcx+30h]; hHandle
0x18001af47  call    cs:__imp_WaitForSingleObject
0x18001af4d  mov     rcx, [rbx]
0x18001af50  mov     eax, [rcx+14h]
0x18001af53  dec     eax
0x18001af55  test    eax, 0FFFFFFFDh
0x18001af5a  jz      short loc_18001AF74
0x18001af5c  mov     dword ptr [rcx+14h], 3
0x18001af63  mov     rcx, [rbx]
0x18001af66  lea     rdx, [rcx+10h]; lpServiceStatus
0x18001af6a  mov     rcx, [rcx+8]; hServiceStatus
0x18001af6e  call    cs:__imp_SetServiceStatus
0x18001af74  xor     eax, eax
0x18001af76  mov     rbx, [rsp+48h+arg_8]
0x18001af7b  add     rsp, 40h
0x18001af7f  pop     rdi
0x18001af80  retn
```
