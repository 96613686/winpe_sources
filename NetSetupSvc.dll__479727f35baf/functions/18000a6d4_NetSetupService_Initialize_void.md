# NetSetupService::Initialize(void)

- ea: `0x18000a6d4`
- end: `0x18000a875`
- name: `?Initialize@NetSetupService@@QEAAXXZ`
- size: `417`
- prototype: `void __fastcall(NetSetupService *__hidden this)`
- caller_count: `1`
- callee_count: `21`
- tags: `loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x180006d08`

## callees

- `0x1800027c0`
- `0x1800076e0`
- `0x180008b70`
- `0x1800093b4`
- `0x180009cfc`
- `0x18000a4d0`
- `0x18000a570`
- `0x18000a6d4`
- `0x18000a95c`
- `0x18000b4b4`
- `0x18000c420`
- `0x18000c5e0`
- `0x18000cf2c`
- `0x18000d384`
- `0x18000da24`
- `0x18000deec`
- `0x18000dfc0`
- `0x18000f6bc`
- `0x18001039c`
- `0x180020bcc`
- `0x180025214`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000a856`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000a856`
- `api-ms-win-service-core-l1-1-0!RegisterServiceCtrlHandlerExW` at `0x18000a705`
- `api-ms-win-service-core-l1-1-0!RegisterServiceCtrlHandlerExW` at `0x18000a705`

## pseudocode

```c
void __fastcall NetSetupService::Initialize(NetSetupService *this)
{
  NetSetupService *v1; // rdi
  SERVICE_STATUS_HANDLE v2; // rax
  bool v3; // al
  __int64 v4; // r8
  _QWORD *RpcIdleTimeout; // rax
  __int64 v6; // rcx
  DWORD LastError; // eax
  __int64 v8; // rdx
  __int64 v9; // r8
  _BYTE v10[16]; // [rsp+30h] [rbp-38h] BYREF

  v1 = g_NetSetupService;
  v2 = RegisterServiceCtrlHandlerExW(L"netsetupsvc", NetSetupService::ServiceEventHandlerExThunk, g_NetSetupService);
  *((_QWORD *)v1 + 12) = v2;
  if ( !v2 )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      LastError = GetLastError();
      WPP_SF_Ds(*((_QWORD *)WPP_GLOBAL_Control + 2), v8, v9, LastError);
    }
    Win32Exception::ThrowLastError();
  }
  NetSetupService::SetServiceStatus(v1, 1);
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_DemandStartNetsetupInAI>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_DemandStartNetsetupInAI>::GetImpl'::`2'::impl) )
  {
    v3 = IsServicingInProgress();
    *((_BYTE *)v1 + 400) = v3;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
      WPP_SF_l(*((_QWORD *)WPP_GLOBAL_Control + 2), v3, v4, v3);
  }
  NetSetupService::PrepareHostEnvironment(v1);
  RpcIdleTimeout = (_QWORD *)NetSetupService::GetRpcIdleTimeout(v1, v10);
  NetSetupSvcRpc::Start((char *)v1 + 136, *RpcIdleTimeout);
  NetSetupService::FinishMigration(v1);
  NetSetupService::ReplayPendedNotifyObjectEvents(v1);
  *((_DWORD *)v1 + 52) = NetSetupService::GetMaximumNumberOfNetworkInterfacesPerDevice(v1);
  NetSetupSvcDeviceManager::NotifyDeviceListOutOfDate((NetSetupService *)((char *)v1 + 168));
  NetSetupSvcWnf::Start((NetSetupService *)((char *)v1 + 152));
  NetSetupSvcDeviceQuery::Start((NetSetupService *)((char *)v1 + 216));
  RtlLockThisExclusive::RtlLockThisExclusive((RtlLockThisExclusive *)v10, (NetSetupService *)((char *)v1 + 384));
  NetSetupService::RegisterStopCallback(v1);
  NetSetupService::SetServiceStatus(v1, 2);
  if ( (Microsoft_Windows_Network_SetupEnableBits & 1) != 0 )
    McGenEventWrite_EventWriteTransfer(v6, EtwServiceStarted);
  RtlLockHolder::~RtlLockHolder((RtlLockHolder *)v10);
}

```

## disassembly

```asm
0x18000a6d4  mov     [rsp+arg_0], rbx
0x18000a6d9  push    rdi
0x18000a6da  sub     rsp, 60h
0x18000a6de  mov     rax, cs:__security_cookie
0x18000a6e5  xor     rax, rsp
0x18000a6e8  mov     [rsp+68h+var_18], rax
0x18000a6ed  mov     rdi, cs:?g_NetSetupService@@3PEAVNetSetupService@@EA; NetSetupService * g_NetSetupService
0x18000a6f4  mov     r8, rdi; lpContext
0x18000a6f7  lea     rdx, ?ServiceEventHandlerExThunk@NetSetupService@@CAKKKPEAX0@Z; lpHandlerProc
0x18000a6fe  lea     rcx, ServiceName; "netsetupsvc"
0x18000a705  call    cs:__imp_RegisterServiceCtrlHandlerExW
0x18000a70b  mov     [rdi+60h], rax
0x18000a70f  test    rax, rax
0x18000a712  jz      loc_18000A83D
0x18000a718  mov     edx, 1
0x18000a71d  mov     rcx, rdi
0x18000a720  call    ?SetServiceStatus@NetSetupService@@AEAAXW4ServiceState@1@K@Z; NetSetupService::SetServiceStatus(NetSetupService::ServiceState,ulong)
0x18000a725  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_DemandStartNetsetupInAI@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_DemandStartNetsetupInAI@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_DemandStartNetsetupInAI> `wil::Feature<__WilFeatureTraits_Feature_DemandStartNetsetupInAI>::GetImpl(void)'::`2'::impl
0x18000a72c  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_DemandStartNetsetupInAI@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_DemandStartNetsetupInAI>::__private_IsEnabled(void)
0x18000a731  test    al, al
0x18000a733  jz      short loc_18000A768
0x18000a735  call    ?IsServicingInProgress@@YA_NXZ; IsServicingInProgress(void)
0x18000a73a  movzx   edx, al
0x18000a73d  mov     [rdi+190h], dl
0x18000a743  lea     rax, WPP_GLOBAL_Control
0x18000a74a  mov     rcx, cs:WPP_GLOBAL_Control
0x18000a751  cmp     rcx, rax
0x18000a754  jz      short loc_18000A768
0x18000a756  cmp     byte ptr [rcx+19h], 4
0x18000a75a  jb      short loc_18000A768
0x18000a75c  mov     r9d, edx
0x18000a75f  mov     rcx, [rcx+10h]
0x18000a763  call    WPP_SF_l
0x18000a768  mov     rcx, rdi; this
0x18000a76b  call    ?PrepareHostEnvironment@NetSetupService@@AEAAXXZ; NetSetupService::PrepareHostEnvironment(void)
0x18000a770  lea     rdx, [rsp+68h+var_38]
0x18000a775  mov     rcx, rdi
0x18000a778  call    ?GetRpcIdleTimeout@NetSetupService@@AEAA?AV?$duration@_JU?$ratio@$00$00@std@@@chrono@std@@XZ; NetSetupService::GetRpcIdleTimeout(void)
0x18000a77d  lea     rcx, [rdi+88h]
0x18000a784  mov     rdx, [rax]
0x18000a787  call    ?Start@NetSetupSvcRpc@@QEAAXV?$duration@_JU?$ratio@$00$00@std@@@chrono@std@@@Z; NetSetupSvcRpc::Start(std::chrono::duration<__int64,std::ratio<1,1>>)
0x18000a78c  mov     rcx, rdi; this
0x18000a78f  call    ?FinishMigration@NetSetupService@@AEAAXXZ; NetSetupService::FinishMigration(void)
0x18000a794  mov     rcx, rdi; this
0x18000a797  call    ?ReplayPendedNotifyObjectEvents@NetSetupService@@AEAAXXZ; NetSetupService::ReplayPendedNotifyObjectEvents(void)
0x18000a79c  lea     rbx, [rdi+0A8h]
0x18000a7a3  mov     rcx, rdi; this
0x18000a7a6  call    ?GetMaximumNumberOfNetworkInterfacesPerDevice@NetSetupService@@AEAAKXZ; NetSetupService::GetMaximumNumberOfNetworkInterfacesPerDevice(void)
0x18000a7ab  mov     [rbx+28h], eax
0x18000a7ae  mov     rcx, rbx; this
0x18000a7b1  call    ?NotifyDeviceListOutOfDate@NetSetupSvcDeviceManager@@QEAAXXZ; NetSetupSvcDeviceManager::NotifyDeviceListOutOfDate(void)
0x18000a7b6  lea     rcx, [rdi+98h]; this
0x18000a7bd  call    ?Start@NetSetupSvcWnf@@QEAAXXZ; NetSetupSvcWnf::Start(void)
0x18000a7c2  lea     rcx, [rdi+0D8h]; this
0x18000a7c9  call    ?Start@NetSetupSvcDeviceQuery@@QEAAXXZ; NetSetupSvcDeviceQuery::Start(void)
0x18000a7ce  lea     rdx, [rdi+180h]; struct RtlSrwLock *
0x18000a7d5  lea     rcx, [rsp+68h+var_38]; this
0x18000a7da  call    ??0RtlLockThisExclusive@@QEAA@AEAVRtlSrwLock@@@Z; RtlLockThisExclusive::RtlLockThisExclusive(RtlSrwLock &)
0x18000a7df  nop
0x18000a7e0  mov     rcx, rdi; this
0x18000a7e3  call    ?RegisterStopCallback@NetSetupService@@AEAAXXZ; NetSetupService::RegisterStopCallback(void)
0x18000a7e8  mov     edx, 2
0x18000a7ed  mov     rcx, rdi
0x18000a7f0  call    ?SetServiceStatus@NetSetupService@@AEAAXW4ServiceState@1@K@Z; NetSetupService::SetServiceStatus(NetSetupService::ServiceState,ulong)
0x18000a7f5  test    cs:Microsoft_Windows_Network_SetupEnableBits, 1
0x18000a7fc  jz      short loc_18000A81B
0x18000a7fe  lea     rax, [rsp+68h+var_28]
0x18000a803  mov     [rsp+68h+var_48], rax
0x18000a808  mov     r9d, 1
0x18000a80e  lea     rdx, EtwServiceStarted
0x18000a815  call    McGenEventWrite_EventWriteTransfer
0x18000a81a  nop
0x18000a81b  lea     rcx, [rsp+68h+var_38]; this
0x18000a820  call    ??1RtlLockHolder@@QEAA@XZ; RtlLockHolder::~RtlLockHolder(void)
0x18000a825  mov     rcx, [rsp+68h+var_18]
0x18000a82a  xor     rcx, rsp; StackCookie
0x18000a82d  call    __security_check_cookie
0x18000a832  mov     rbx, [rsp+68h+arg_0]
0x18000a837  add     rsp, 60h
0x18000a83b  pop     rdi
0x18000a83c  retn
0x18000a83d  lea     rax, WPP_GLOBAL_Control
0x18000a844  mov     rcx, cs:WPP_GLOBAL_Control
0x18000a84b  cmp     rcx, rax
0x18000a84e  jz      short loc_18000A86F
0x18000a850  cmp     byte ptr [rcx+19h], 2
0x18000a854  jb      short loc_18000A86F
0x18000a856  call    cs:__imp_GetLastError
0x18000a85c  mov     r9d, eax
0x18000a85f  mov     rcx, cs:WPP_GLOBAL_Control
0x18000a866  mov     rcx, [rcx+10h]
0x18000a86a  call    WPP_SF_Ds
0x18000a86f  call    ?ThrowLastError@Win32Exception@@SAXXZ; Win32Exception::ThrowLastError(void)
```
