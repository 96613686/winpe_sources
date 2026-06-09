# ServiceMain(void)

- ea: `0x18003a5fc`
- end: `0x18003b470`
- name: `?ServiceMain@@YAXXZ`
- size: `3700`
- prototype: `void(void)`
- caller_count: `1`
- callee_count: `34`
- tags: `authz_impersonation, registry_config, loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x18006c020`

## callees

- `0x180002ad0`
- `0x180003908`
- `0x18000a038`
- `0x18000b63c`
- `0x18000ebd8`
- `0x1800101c4`
- `0x1800101ec`
- `0x18001022c`
- `0x1800351ac`
- `0x180035a44`
- `0x18003669c`
- `0x180037464`
- `0x180037a3c`
- `0x180037ac8`
- `0x180037bd0`
- `0x180038094`
- `0x1800394d8`
- `0x18003a5fc`
- `0x18003b478`
- `0x18003b5d8`
- `0x180040664`
- `0x180053ab8`
- `0x180059fa8`
- `0x18005a060`
- `0x18005a5fc`
- `0x1800717a4`
- `0x180073350`
- `0x180073f80`
- `0x1800799bc`
- `0x18007bd14`
- `0x18007be44`
- `0x18007c888`
- `0x18007e71c`
- `0x18009c010`

## import_xrefs

- `Kerberos!KerbIsInitialized` at `0x18003ac76`
- `Kerberos!KerbIsInitialized` at `0x18003ac76`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18003af24`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18003af24`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18003b206`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18003b39f`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18003b206`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18003b39f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003a770`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003a820`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003af36`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003b3d8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003a770`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003a820`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003af36`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003b3d8`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x18003b1de`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x18003b1de`
- `api-ms-win-core-processthreads-l1-1-0!TlsAlloc` at `0x18003b2c2`
- `api-ms-win-core-processthreads-l1-1-0!TlsAlloc` at `0x18003b2c2`
- `WS2_32!FreeAddrInfoW` at `0x18003abe3`
- `WS2_32!FreeAddrInfoW` at `0x18003abe3`
- `WS2_32!GetAddrInfoW` at `0x18003ab58`
- `WS2_32!GetAddrInfoW` at `0x18003ab58`
- `WS2_32!__imp_WSAStartup` at `0x18003a8a8`
- `WS2_32!__imp_WSAStartup` at `0x18003a8a8`
- `api-ms-win-core-threadpool-legacy-l1-1-0!CreateTimerQueueTimer` at `0x18003b390`
- `api-ms-win-core-threadpool-legacy-l1-1-0!CreateTimerQueueTimer` at `0x18003b390`
- `RPCRT4!RpcServerListen` at `0x18003b06d`
- `RPCRT4!RpcServerListen` at `0x18003b06d`
- `RPCRT4!I_RpcMapWin32Status` at `0x18003b0a8`
- `RPCRT4!I_RpcMapWin32Status` at `0x18003b0a8`
- `ntdll!RtlInitUnicodeString` at `0x18003a95a`
- `ntdll!RtlInitUnicodeString` at `0x18003a96e`
- `ntdll!RtlInitUnicodeString` at `0x18003a995`
- `ntdll!RtlInitUnicodeString` at `0x18003a9ab`
- `ntdll!RtlInitUnicodeString` at `0x18003aa83`
- `ntdll!RtlInitUnicodeString` at `0x18003aa98`
- `ntdll!RtlInitUnicodeString` at `0x18003a95a`
- `ntdll!RtlInitUnicodeString` at `0x18003a96e`
- `ntdll!RtlInitUnicodeString` at `0x18003a995`
- `ntdll!RtlInitUnicodeString` at `0x18003a9ab`
- `ntdll!RtlInitUnicodeString` at `0x18003aa83`
- `ntdll!RtlInitUnicodeString` at `0x18003aa98`
- `api-ms-win-service-winsvc-l1-1-0!RegisterServiceCtrlHandlerW` at `0x18003a7fc`
- `api-ms-win-service-winsvc-l1-1-0!RegisterServiceCtrlHandlerW` at `0x18003a7fc`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
void ServiceMain(void)
{
  int v0; // ecx
  int v1; // r8d
  struct IKdcBackend *v2; // rax
  struct IKdcBackend *v3; // rax
  DWORD LastError; // eax
  struct IKdcBackend *v5; // rax
  const WCHAR *v6; // rax
  DWORD v7; // eax
  unsigned int v8; // eax
  struct IKdcBackend *v9; // rax
  struct IKdcBackend *v10; // rax
  const WCHAR *v11; // rax
  int v12; // eax
  int v13; // eax
  __int64 v14; // r9
  struct _KERB_INTERNAL_NAME *v15; // rax
  int v16; // eax
  struct _KERB_INTERNAL_NAME **v17; // rcx
  int v18; // eax
  __int64 v19; // r9
  int v20; // eax
  unsigned int AddrInfoW; // eax
  struct addrinfoW *v22; // r14
  PADDRINFOW v23; // rbx
  struct sockaddr *ai_addr; // rax
  int v25; // eax
  struct IKdcBackend *v26; // rax
  int v27; // eax
  int v28; // eax
  int v29; // eax
  int started; // eax
  struct IKdcBackend *v31; // rax
  unsigned __int8 v32; // r8
  NTSTATUS v33; // eax
  DWORD v34; // eax
  struct IKdcBackend *v35; // rax
  struct IKdcBackend *v36; // rax
  unsigned int v37; // eax
  RPC_STATUS v38; // ebx
  struct IKdcBackend *v39; // rax
  Ntlmless::Kerberos *v40; // rcx
  struct IKdcBackend *v41; // rax
  struct IKdcBackend *v42; // rax
  char *Thread; // rbx
  unsigned int v44; // r14d
  DWORD v45; // eax
  DWORD v46; // eax
  int v47; // [rsp+40h] [rbp-C0h] BYREF
  char v48; // [rsp+44h] [rbp-BCh] BYREF
  _QWORD v49[7]; // [rsp+50h] [rbp-B0h] BYREF
  char v50; // [rsp+88h] [rbp-78h]
  struct _KERB_INTERNAL_NAME *v51; // [rsp+90h] [rbp-70h] BYREF
  unsigned int v52; // [rsp+98h] [rbp-68h] BYREF
  int v53; // [rsp+9Ch] [rbp-64h] BYREF
  int v54; // [rsp+A0h] [rbp-60h] BYREF
  PADDRINFOW ppResult; // [rsp+A8h] [rbp-58h] BYREF
  void *phNewTimer; // [rsp+B0h] [rbp-50h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+B8h] [rbp-48h] BYREF
  WSAData WSAData; // [rsp+D0h] [rbp-30h] BYREF
  _QWORD v59[2]; // [rsp+270h] [rbp+170h] BYREF

  v47 = 0;
  v53 = 0;
  DestinationString = 0;
  v51 = 0;
  memset_0(&WSAData, 0, sizeof(WSAData));
  v52 = 0;
  v48 = 0;
  phNewTimer = 0;
  v54 = 131104;
  v49[0] = &v53;
  v49[1] = &v54;
  v49[2] = &v51;
  v49[3] = &phNewTimer;
  v49[4] = &v52;
  v49[5] = &v47;
  v49[6] = &v48;
  v50 = 1;
  GlobalKdcService::Get();
  g_kdcState = 1;
  if ( (Microsoft_Windows_Kerberos_Local_Key_Distribution_CenterEnableBits & 2) != 0 )
    McGenEventWrite_EtwEventWriteTransfer(v0, (unsigned int)KdcStart, v1, 1, (__int64)v59);
  TlgRegisterAggregateProviderEx();
  qword_1800B2928 = 0;
  WPP_MAIN_CB = 0;
  qword_1800B2930 = 1;
  WPP_REGISTRATION_GUIDS = (__int64)WPP_ThisDir_CTLGUID_KdcGlobalDebugTraceControlGuid;
  WPP_GLOBAL_Control = (CSecurityData *)&WPP_MAIN_CB;
  WppInitUm();
  KdcLoadParameters();
  v2 = GlobalKdcService::Get();
  (*(void (__fastcall **)(struct IKdcBackend *))(*(_QWORD *)v2 + 16LL))(v2);
  v3 = GlobalKdcService::Get();
  if ( !(*(unsigned __int8 (__fastcall **)(struct IKdcBackend *))(*(_QWORD *)v3 + 24LL))(v3) )
  {
    if ( WPP_GLOBAL_Control != (CSecurityData *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
    {
      LastError = GetLastError();
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 80, WPP_4faeb9b481d0381be4025487491ed0d4_Traceguids, LastError);
    }
    goto LABEL_168;
  }
  if ( WPP_GLOBAL_Control != (CSecurityData *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 81, WPP_4faeb9b481d0381be4025487491ed0d4_Traceguids);
  v5 = GlobalKdcService::Get();
  v6 = (const WCHAR *)(*(__int64 (__fastcall **)(struct IKdcBackend *))(*(_QWORD *)v5 + 40LL))(v5);
  hService = RegisterServiceCtrlHandlerW(v6, Handler);
  if ( !hService
    && WPP_GLOBAL_Control != (CSecurityData *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
  {
    v7 = GetLastError();
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 82, WPP_4faeb9b481d0381be4025487491ed0d4_Traceguids, v7);
  }
  SStatus.dwServiceType = 32;
  *(_QWORD *)&SStatus.dwCurrentState = 1;
  *(_QWORD *)&SStatus.dwWin32ExitCode = 0;
  *(_QWORD *)&SStatus.dwCheckPoint = 0;
  if ( !UpdateStatus(2u) || !(unsigned int)InitializeEvents() )
    goto LABEL_168;
  v8 = WSAStartup(2u, &WSAData);
  v52 = v8;
  if ( v8 )
  {
    if ( WPP_GLOBAL_Control != (CSecurityData *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 83, WPP_4faeb9b481d0381be4025487491ed0d4_Traceguids, v8);
    goto LABEL_168;
  }
  v48 = 1;
  v9 = GlobalKdcService::Get();
  v47 = (*(__int64 (__fastcall **)(struct IKdcBackend *))(*(_QWORD *)v9 + 56LL))(v9);
  if ( v47 < 0 )
  {
    if ( WPP_GLOBAL_Control != (CSecurityData *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 84, WPP_4faeb9b481d0381be4025487491ed0d4_Traceguids);
    goto LABEL_168;
  }
  RtlInitUnicodeString(&GlobalKerberosName, L"Kerberos");
  RtlInitUnicodeString(&GlobalKerberosNewerKeysName, L"Kerberos-Newer-Keys");
  v10 = GlobalKdcService::Get();
  v11 = (const WCHAR *)(*(__int64 (__fastcall **)(struct IKdcBackend *))(*(_QWORD *)v10 + 40LL))(v10);
  RtlInitUnicodeString(&GlobalKdcName, v11);
  SafeAllocaInitialize();
  RtlInitUnicodeString(&DestinationString, L"Microsoft");
  v12 = KerbUnicodeStringToKerbString((struct _STRING *)&KdcGlobalFxFastCookieConstant, &DestinationString);
  if ( v12 )
  {
    v13 = KerbMapKerbError(v12);
    v47 = v13;
    if ( WPP_GLOBAL_Control != (CSecurityData *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_Dd(*((_QWORD *)WPP_GLOBAL_Control + 2), 85, WPP_4faeb9b481d0381be4025487491ed0d4_Traceguids, v14, v13);
    goto LABEL_168;
  }
  v15 = (struct _KERB_INTERNAL_NAME *)MIDL_user_allocate(0x28u);
  v51 = v15;
  if ( !v15 )
  {
    v47 = -1073741801;
    if ( WPP_GLOBAL_Control != (CSecurityData *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 86, WPP_4faeb9b481d0381be4025487491ed0d4_Traceguids, 3221225495LL);
    goto LABEL_168;
  }
  *(_WORD *)v15 = 11;
  *((_WORD *)v51 + 1) = 2;
  RtlInitUnicodeString((PUNICODE_STRING)((char *)v51 + 8), L"WELLKNOWN");
  RtlInitUnicodeString((PUNICODE_STRING)((char *)v51 + 24), L"ANONYMOUS");
  v16 = KerbConvertKdcNameToPrincipalName((struct KERB_PRINCIPAL_NAME *)&KdcGlobalAnonymousPrincipalName, v51);
  if ( v16 )
  {
    v18 = KerbMapKerbError(v16);
    v47 = v18;
    if ( WPP_GLOBAL_Control != (CSecurityData *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_Dd(*((_QWORD *)WPP_GLOBAL_Control + 2), 87, WPP_4faeb9b481d0381be4025487491ed0d4_Traceguids, v19, v18);
    goto LABEL_168;
  }
  v20 = KerbBuildKpasswdName(v17);
  v47 = v20;
  if ( v20 < 0 )
  {
    if ( WPP_GLOBAL_Control != (CSecurityData *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        88,
        WPP_4faeb9b481d0381be4025487491ed0d4_Traceguids,
        (unsigned int)v20);
    goto LABEL_168;
  }
  ppResult = 0;
  AddrInfoW = GetAddrInfoW(0, L"0", 0, &ppResult);
  if ( AddrInfoW )
  {
    if ( WPP_GLOBAL_Control != (CSecurityData *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 89, WPP_4faeb9b481d0381be4025487491ed0d4_Traceguids, AddrInfoW);
    goto LABEL_168;
  }
  v22 = ppResult;
  v23 = ppResult;
  if ( ppResult )
  {
    while ( v23->ai_family != 23 )
    {
      if ( v23->ai_family == 2 )
      {
        memset_0(&GlobalLocalhostAddress, 0, sizeof(GlobalLocalhostAddress));
        *(struct sockaddr *)&GlobalLocalhostAddress.ss_family = *v23->ai_addr;
        goto LABEL_56;
      }
      v23 = v23->ai_next;
      if ( !v23 )
        goto LABEL_56;
    }
    memset_0(&GlobalLocalhostAddress, 0, sizeof(GlobalLocalhostAddress));
    ai_addr = v23->ai_addr;
    *(struct sockaddr *)&GlobalLocalhostAddress.ss_family = *ai_addr;
    *(struct sockaddr *)((char *)&GlobalLocalhostAddress.__ss_align + 4) = *(struct sockaddr *)&ai_addr->sa_data[10];
LABEL_56:
    if ( v22 )
      FreeAddrInfoW(v22);
  }
  if ( !KdcWaitForSamService() )
  {
LABEL_59:
    v47 = -1073741604;
    v50 = 0;
    lambda_8fd44bed28da3d7ef7a2050c13fca057_::operator()(v49);
    return;
  }
  v25 = KdcInitializeAuthzRM();
  v47 = v25;
  if ( v25 < 0 )
  {
    if ( WPP_GLOBAL_Control != (CSecurityData *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        90,
        WPP_4faeb9b481d0381be4025487491ed0d4_Traceguids,
        (unsigned int)v25);
    goto LABEL_168;
  }
  if ( !UpdateStatus(2u) )
    goto LABEL_168;
  if ( !(unsigned __int8)KerbIsInitialized() )
  {
    v47 = -1073741823;
    if ( WPP_GLOBAL_Control != (CSecurityData *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 91, WPP_4faeb9b481d0381be4025487491ed0d4_Traceguids, 3221225473LL);
    goto LABEL_168;
  }
  v26 = GlobalKdcService::Get();
  if ( !(*(unsigned __int8 (__fastcall **)(struct IKdcBackend *))(*(_QWORD *)v26 + 48LL))(v26) )
    goto LABEL_59;
  if ( !UpdateStatus(2u) )
    goto LABEL_168;
  v27 = OpenAccountDomain();
  v47 = v27;
  if ( v27 < 0 )
  {
    if ( WPP_GLOBAL_Control != (CSecurityData *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        92,
        WPP_4faeb9b481d0381be4025487491ed0d4_Traceguids,
        (unsigned int)v27);
    goto LABEL_168;
  }
  if ( !UpdateStatus(2u) )
    goto LABEL_168;
  v28 = KdcInitializeGlobalOidsCache();
  v47 = v28;
  if ( v28 < 0 )
  {
    if ( WPP_GLOBAL_Control != (CSecurityData *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        93,
        WPP_4faeb9b481d0381be4025487491ed0d4_Traceguids,
        (unsigned int)v28);
    goto LABEL_168;
  }
  v29 = KdcInitializeCerts();
  v47 = v29;
  if ( v29 < 0 )
  {
    if ( WPP_GLOBAL_Control != (CSecurityData *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        94,
        WPP_4faeb9b481d0381be4025487491ed0d4_Traceguids,
        (unsigned int)v29);
    goto LABEL_168;
  }
  if ( !UpdateStatus(2u) )
    goto LABEL_168;
  started = StartAllProtSeqs();
  v47 = started;
  if ( started < 0 )
  {
    if ( WPP_GLOBAL_Control != (CSecurityData *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        95,
        WPP_4faeb9b481d0381be4025487491ed0d4_Traceguids,
        (unsigned int)started);
    goto LABEL_168;
  }
  if ( !UpdateStatus(2u) )
    goto LABEL_168;
  v31 = GlobalKdcService::Get();
  v33 = CSecurityData::Init((CSecurityData *)SecData, v31, v32);
  v47 = v33;
  if ( v33 < 0 )
  {
    if ( WPP_GLOBAL_Control != (CSecurityData *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        96,
        WPP_4faeb9b481d0381be4025487491ed0d4_Traceguids,
        (unsigned int)v33);
    goto LABEL_168;
  }
  KdcGetCbacAndArmorPolicy();
  if ( !UpdateStatus(2u) )
    goto LABEL_168;
  hKdcShutdownEvent = CreateEventW(0, 1, 0, 0);
  if ( !hKdcShutdownEvent )
  {
    v34 = GetLastError();
    v47 = v34;
    if ( WPP_GLOBAL_Control != (CSecurityData *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 97, WPP_4faeb9b481d0381be4025487491ed0d4_Traceguids, v34);
    goto LABEL_168;
  }
  if ( !UpdateStatus(2u) )
    goto LABEL_168;
  v35 = GlobalKdcService::Get();
  v47 = (*(__int64 (__fastcall **)(struct IKdcBackend *))(*(_QWORD *)v35 + 88LL))(v35);
  if ( v47 < 0 )
  {
    if ( WPP_GLOBAL_Control != (CSecurityData *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 98, WPP_4faeb9b481d0381be4025487491ed0d4_Traceguids);
    goto LABEL_168;
  }
  if ( !UpdateStatus(2u)
    || (KdcDomainList.Blink = &KdcDomainList,
        KdcDomainList.Flink = &KdcDomainList,
        v36 = GlobalKdcService::Get(),
        v47 = (*(__int64 (__fastcall **)(struct IKdcBackend *))(*(_QWORD *)v36 + 64LL))(v36),
        !UpdateStatus(2u)) )
  {
LABEL_168:
    v50 = 0;
    lambda_8fd44bed28da3d7ef7a2050c13fca057_::operator()(v49);
    return;
  }
  v37 = RpcServerListen(1u, 0x4D2u, 1u);
  v38 = v37;
  if ( !v37 || v37 == 1713 )
  {
    if ( !(unsigned int)KerbLoadDH() )
    {
      v47 = -1073741670;
      v50 = 0;
      lambda_8fd44bed28da3d7ef7a2050c13fca057_::operator()(v49);
      return;
    }
    KdcInitializeTrace();
    v39 = GlobalKdcService::Get();
    v47 = (*(__int64 (__fastcall **)(struct IKdcBackend *, __int64 (__fastcall *)(int, int, int, int, PCUNICODE_STRING)))(*(_QWORD *)v39 + 112LL))(
            v39,
            KdcAccountChangeNotification);
    if ( v47 < 0 )
    {
      if ( WPP_GLOBAL_Control != (CSecurityData *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 100, WPP_4faeb9b481d0381be4025487491ed0d4_Traceguids);
      goto LABEL_168;
    }
    if ( Ntlmless::Kerberos::IsEnabled(v40) )
    {
      v41 = GlobalKdcService::Get();
      v47 = (**(__int64 (__fastcall ***)(struct IKdcBackend *))v41)(v41);
      if ( v47 < 0 )
      {
        if ( WPP_GLOBAL_Control != (CSecurityData *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        {
          WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 101, WPP_4faeb9b481d0381be4025487491ed0d4_Traceguids);
        }
        goto LABEL_168;
      }
    }
    else
    {
      v42 = GlobalKdcService::Get();
      (**(void (__fastcall ***)(struct IKdcBackend *))v42)(v42);
    }
    Thread = (char *)CreateThread(0, 0, lambda_ccf421b28a8d9f00fddb184ff5f5b109_::_lambda_invoker_cdecl_, 0, 0, 0);
    v59[0] = Thread;
    if ( (unsigned __int64)(Thread - 1) > 0xFFFFFFFFFFFFFFFDuLL )
    {
      if ( WPP_GLOBAL_Control != (CSecurityData *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      {
        v46 = GetLastError();
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 102, WPP_4faeb9b481d0381be4025487491ed0d4_Traceguids, v46);
      }
    }
    else
    {
      v44 = 0;
      while ( 1 )
      {
        v45 = WaitForSingleObject(Thread, 0x3E8u);
        if ( !v45 )
        {
          if ( WPP_GLOBAL_Control != (CSecurityData *)&WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
          {
            WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 103, WPP_4faeb9b481d0381be4025487491ed0d4_Traceguids, v44);
          }
LABEL_153:
          KdcThreadContext::s_tlsIndex = TlsAlloc();
          if ( KdcThreadContext::s_tlsIndex == -1 )
          {
            v47 = -1073741670;
            if ( WPP_GLOBAL_Control != (CSecurityData *)&WPP_GLOBAL_Control
              && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
            {
              WPP_SF_d(
                *((_QWORD *)WPP_GLOBAL_Control + 2),
                106,
                WPP_4faeb9b481d0381be4025487491ed0d4_Traceguids,
                3221225626LL);
            }
          }
          else
          {
            v47 = 0;
            g_kdcState = 2;
            SStatus.dwControlsAccepted = 1;
            if ( UpdateStatus(4u) )
            {
              SetKdcStartEvent();
              CreateTimerQueueTimer(&phNewTimer, 0, KdcMyStoreWaitHandler, 0, 0x493E0u, 0, 8u);
              WaitForSingleObject(hKdcShutdownEvent, 0xFFFFFFFF);
            }
          }
          goto LABEL_164;
        }
        if ( v45 != 258
          && WPP_GLOBAL_Control != (CSecurityData *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        {
          WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 104, WPP_4faeb9b481d0381be4025487491ed0d4_Traceguids, v45);
        }
        if ( !UpdateStatus(2u) )
          break;
        if ( (int)++v44 >= 30 )
          goto LABEL_153;
      }
      if ( WPP_GLOBAL_Control != (CSecurityData *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 105, WPP_4faeb9b481d0381be4025487491ed0d4_Traceguids);
    }
LABEL_164:
    wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(v59);
    v50 = 0;
    lambda_8fd44bed28da3d7ef7a2050c13fca057_::operator()(v49);
  }
  else
  {
    if ( WPP_GLOBAL_Control != (CSecurityData *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 99, WPP_4faeb9b481d0381be4025487491ed0d4_Traceguids, v37);
    v47 = I_RpcMapWin32Status(v38);
    v50 = 0;
    lambda_8fd44bed28da3d7ef7a2050c13fca057_::operator()(v49);
  }
}

```

## disassembly

```asm
0x18003a5fc  push    rbp
0x18003a5fe  push    rbx
0x18003a5ff  push    rsi
0x18003a600  push    rdi
0x18003a601  push    r12
0x18003a603  push    r13
0x18003a605  push    r14
0x18003a607  push    r15
0x18003a609  lea     rbp, [rsp-198h]
0x18003a611  sub     rsp, 298h
0x18003a618  mov     rax, cs:__security_cookie
0x18003a61f  xor     rax, rsp
0x18003a622  mov     [rbp+1D0h+var_50], rax
0x18003a629  xor     r15d, r15d
0x18003a62c  mov     [rsp+2D0h+var_290], r15d
0x18003a631  mov     [rbp+1D0h+var_234], r15d
0x18003a635  xorps   xmm0, xmm0
0x18003a638  movups  xmmword ptr [rbp+1D0h+DestinationString.Length], xmm0
0x18003a63c  mov     [rbp+1D0h+var_240], r15
0x18003a640  xor     edx, edx; Val
0x18003a642  mov     r8d, 198h; Size
0x18003a648  lea     rcx, [rbp+1D0h+WSAData]; void *
0x18003a64c  call    memset_0
0x18003a651  mov     [rbp+1D0h+var_238], r15d
0x18003a655  mov     [rsp+2D0h+var_28C], r15b
0x18003a65a  mov     [rbp+1D0h+phNewTimer], r15
0x18003a65e  mov     [rbp+1D0h+var_230], 20020h
0x18003a665  lea     rax, [rbp+1D0h+var_234]
0x18003a669  mov     [rsp+2D0h+var_280], rax
0x18003a66e  lea     rax, [rbp+1D0h+var_230]
0x18003a672  mov     [rsp+2D0h+var_278], rax
0x18003a677  lea     rax, [rbp+1D0h+var_240]
0x18003a67b  mov     [rsp+2D0h+var_270], rax
0x18003a680  lea     rax, [rbp+1D0h+phNewTimer]
0x18003a684  mov     [rsp+2D0h+var_268], rax
0x18003a689  lea     rax, [rbp+1D0h+var_238]
0x18003a68d  mov     [rsp+2D0h+var_260], rax
0x18003a692  lea     rax, [rsp+2D0h+var_290]
0x18003a697  mov     [rsp+2D0h+var_258], rax
0x18003a69c  lea     rax, [rsp+2D0h+var_28C]
0x18003a6a1  mov     [rbp+1D0h+var_250], rax
0x18003a6a5  lea     r12d, [r15+1]
0x18003a6a9  mov     [rbp+1D0h+var_248], r12b
0x18003a6ad  call    ?Get@GlobalKdcService@@SAAEAUIKdcBackend@@XZ; GlobalKdcService::Get(void)
0x18003a6b2  mov     cs:?g_kdcState@@3W4KdcState@@A, r12d; KdcState g_kdcState
0x18003a6b9  lea     r13d, [r15+2]
0x18003a6bd  test    cs:Microsoft_Windows_Kerberos_Local_Key_Distribution_CenterEnableBits, r13b
0x18003a6c4  jz      short loc_18003A6E1
0x18003a6c6  lea     rax, [rbp+1D0h+var_60]
0x18003a6cd  mov     qword ptr [rsp+2D0h+dwCreationFlags], rax
0x18003a6d2  mov     r9d, r12d
0x18003a6d5  lea     rdx, KdcStart
0x18003a6dc  call    McGenEventWrite_EtwEventWriteTransfer
0x18003a6e1  call    TlgRegisterAggregateProviderEx
0x18003a6e6  mov     cs:qword_1800B2928, r15
0x18003a6ed  mov     cs:WPP_MAIN_CB, r15
0x18003a6f4  mov     cs:qword_1800B2930, 1
0x18003a6ff  lea     rax, WPP_ThisDir_CTLGUID_KdcGlobalDebugTraceControlGuid
0x18003a706  mov     cs:WPP_REGISTRATION_GUIDS, rax
0x18003a70d  lea     rax, WPP_MAIN_CB
0x18003a714  mov     cs:WPP_GLOBAL_Control, rax
0x18003a71b  call    WppInitUm
0x18003a720  call    ?KdcLoadParameters@@YAXXZ; KdcLoadParameters(void)
0x18003a725  call    ?Get@GlobalKdcService@@SAAEAUIKdcBackend@@XZ; GlobalKdcService::Get(void)
0x18003a72a  mov     rdx, rax
0x18003a72d  mov     rcx, [rax]
0x18003a730  mov     rax, [rcx+10h]
0x18003a734  mov     rcx, rdx
0x18003a737  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003a73c  call    ?Get@GlobalKdcService@@SAAEAUIKdcBackend@@XZ; GlobalKdcService::Get(void)
0x18003a741  mov     rdx, rax
0x18003a744  mov     rcx, [rax]
0x18003a747  mov     rax, [rcx+18h]
0x18003a74b  mov     rcx, rdx
0x18003a74e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003a753  test    al, al
0x18003a755  jnz     short loc_18003A7AA
0x18003a757  lea     rdi, WPP_GLOBAL_Control
0x18003a75e  mov     rax, cs:WPP_GLOBAL_Control
0x18003a765  cmp     rax, rdi
0x18003a768  jz      short loc_18003A796
0x18003a76a  test    [rax+1Ch], r13b
0x18003a76e  jz      short loc_18003A796
0x18003a770  call    cs:__imp_GetLastError
0x18003a776  mov     edx, 50h ; 'P'
0x18003a77b  mov     r9d, eax
0x18003a77e  lea     r8, WPP_4faeb9b481d0381be4025487491ed0d4_Traceguids
0x18003a785  mov     rcx, cs:WPP_GLOBAL_Control
0x18003a78c  mov     rcx, [rcx+10h]
0x18003a790  call    WPP_SF_d
0x18003a795  nop
0x18003a796  mov     [rbp+1D0h+var_248], r15b
0x18003a79a  lea     rcx, [rsp+2D0h+var_280]
0x18003a79f  call    _lambda_8fd44bed28da3d7ef7a2050c13fca057___operator__
0x18003a7a4  nop
0x18003a7a5  jmp     loc_18003B44D
0x18003a7aa  lea     rdi, WPP_GLOBAL_Control
0x18003a7b1  lea     rsi, WPP_4faeb9b481d0381be4025487491ed0d4_Traceguids
0x18003a7b8  mov     rcx, cs:WPP_GLOBAL_Control
0x18003a7bf  cmp     rcx, rdi
0x18003a7c2  jz      short loc_18003A7DB
0x18003a7c4  test    byte ptr [rcx+1Ch], 4
0x18003a7c8  jz      short loc_18003A7DB
0x18003a7ca  mov     edx, 51h ; 'Q'
0x18003a7cf  mov     r8, rsi
0x18003a7d2  mov     rcx, [rcx+10h]
0x18003a7d6  call    WPP_SF_
0x18003a7db  call    ?Get@GlobalKdcService@@SAAEAUIKdcBackend@@XZ; GlobalKdcService::Get(void)
0x18003a7e0  mov     rdx, rax
0x18003a7e3  mov     rcx, [rax]
0x18003a7e6  mov     rax, [rcx+28h]
0x18003a7ea  mov     rcx, rdx
0x18003a7ed  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003a7f2  lea     rdx, ?Handler@@YAXK@Z; lpHandlerProc
0x18003a7f9  mov     rcx, rax; lpServiceName
0x18003a7fc  call    cs:__imp_RegisterServiceCtrlHandlerW
0x18003a802  mov     cs:?hService@@3PEAUSERVICE_STATUS_HANDLE__@@EA, rax; SERVICE_STATUS_HANDLE__ * hService
0x18003a809  test    rax, rax
0x18003a80c  jnz     short loc_18003A841
0x18003a80e  mov     rax, cs:WPP_GLOBAL_Control
0x18003a815  cmp     rax, rdi
0x18003a818  jz      short loc_18003A841
0x18003a81a  test    [rax+1Ch], r12b
0x18003a81e  jz      short loc_18003A841
0x18003a820  call    cs:__imp_GetLastError
0x18003a826  mov     edx, 52h ; 'R'
0x18003a82b  mov     r9d, eax
0x18003a82e  mov     r8, rsi
0x18003a831  mov     rcx, cs:WPP_GLOBAL_Control
0x18003a838  mov     rcx, [rcx+10h]
0x18003a83c  call    WPP_SF_d
0x18003a841  mov     cs:?SStatus@@3U_SERVICE_STATUS@@A.dwServiceType, 20h ; ' '; _SERVICE_STATUS SStatus ...
0x18003a84b  mov     qword ptr cs:?SStatus@@3U_SERVICE_STATUS@@A.dwCurrentState, 1; _SERVICE_STATUS SStatus ...
0x18003a856  mov     qword ptr cs:?SStatus@@3U_SERVICE_STATUS@@A.dwWin32ExitCode, r15; _SERVICE_STATUS SStatus ...
0x18003a85d  mov     qword ptr cs:?SStatus@@3U_SERVICE_STATUS@@A.dwCheckPoint, r15; _SERVICE_STATUS SStatus ...
0x18003a864  mov     ecx, r13d; unsigned int
0x18003a867  call    ?UpdateStatus@@YAEK@Z; UpdateStatus(ulong)
0x18003a86c  test    al, al
0x18003a86e  jnz     short loc_18003A884
0x18003a870  mov     [rbp+1D0h+var_248], r15b
0x18003a874  lea     rcx, [rsp+2D0h+var_280]
0x18003a879  call    _lambda_8fd44bed28da3d7ef7a2050c13fca057___operator__
0x18003a87e  nop
0x18003a87f  jmp     loc_18003B44D
0x18003a884  call    ?InitializeEvents@@YAHXZ; InitializeEvents(void)
0x18003a889  test    eax, eax
0x18003a88b  jnz     short loc_18003A8A1
0x18003a88d  mov     [rbp+1D0h+var_248], r15b
0x18003a891  lea     rcx, [rsp+2D0h+var_280]
0x18003a896  call    _lambda_8fd44bed28da3d7ef7a2050c13fca057___operator__
0x18003a89b  nop
0x18003a89c  jmp     loc_18003B44D
0x18003a8a1  mov     ecx, r13d; wVersionRequested
0x18003a8a4  lea     rdx, [rbp+1D0h+WSAData]; lpWSAData
0x18003a8a8  call    cs:__imp_WSAStartup
0x18003a8ae  mov     [rbp+1D0h+var_238], eax
0x18003a8b1  test    eax, eax
0x18003a8b3  jz      short loc_18003A8F0
0x18003a8b5  mov     rcx, cs:WPP_GLOBAL_Control
0x18003a8bc  cmp     rcx, rdi
0x18003a8bf  jz      short loc_18003A8DC
0x18003a8c1  test    [rcx+1Ch], r12b
0x18003a8c5  jz      short loc_18003A8DC
0x18003a8c7  mov     edx, 53h ; 'S'
0x18003a8cc  mov     r9d, eax
0x18003a8cf  mov     r8, rsi
0x18003a8d2  mov     rcx, [rcx+10h]
0x18003a8d6  call    WPP_SF_d
0x18003a8db  nop
0x18003a8dc  mov     [rbp+1D0h+var_248], r15b
0x18003a8e0  lea     rcx, [rsp+2D0h+var_280]
0x18003a8e5  call    _lambda_8fd44bed28da3d7ef7a2050c13fca057___operator__
0x18003a8ea  nop
0x18003a8eb  jmp     loc_18003B44D
0x18003a8f0  mov     [rsp+2D0h+var_28C], r12b
0x18003a8f5  call    ?Get@GlobalKdcService@@SAAEAUIKdcBackend@@XZ; GlobalKdcService::Get(void)
0x18003a8fa  mov     rdx, rax
0x18003a8fd  mov     rcx, [rax]
0x18003a900  mov     rax, [rcx+38h]
0x18003a904  mov     rcx, rdx
0x18003a907  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003a90c  mov     [rsp+2D0h+var_290], eax
0x18003a910  test    eax, eax
0x18003a912  jns     short loc_18003A94C
0x18003a914  mov     rcx, cs:WPP_GLOBAL_Control
0x18003a91b  cmp     rcx, rdi
0x18003a91e  jz      short loc_18003A938
0x18003a920  test    [rcx+1Ch], r13b
0x18003a924  jz      short loc_18003A938
0x18003a926  mov     edx, 54h ; 'T'
0x18003a92b  mov     r8, rsi
0x18003a92e  mov     rcx, [rcx+10h]
0x18003a932  call    WPP_SF_
0x18003a937  nop
0x18003a938  mov     [rbp+1D0h+var_248], r15b
0x18003a93c  lea     rcx, [rsp+2D0h+var_280]
0x18003a941  call    _lambda_8fd44bed28da3d7ef7a2050c13fca057___operator__
0x18003a946  nop
0x18003a947  jmp     loc_18003B44D
0x18003a94c  lea     rdx, aKerberos_0; "Kerberos"
0x18003a953  lea     rcx, ?GlobalKerberosName@@3U_UNICODE_STRING@@A; DestinationString
0x18003a95a  call    cs:__imp_RtlInitUnicodeString
0x18003a960  lea     rdx, aKerberosNewerK; "Kerberos-Newer-Keys"
0x18003a967  lea     rcx, ?GlobalKerberosNewerKeysName@@3U_UNICODE_STRING@@A; DestinationString
0x18003a96e  call    cs:__imp_RtlInitUnicodeString
0x18003a974  call    ?Get@GlobalKdcService@@SAAEAUIKdcBackend@@XZ; GlobalKdcService::Get(void)
0x18003a979  mov     rdx, rax
0x18003a97c  mov     rcx, [rax]
0x18003a97f  mov     rax, [rcx+28h]
0x18003a983  mov     rcx, rdx
0x18003a986  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003a98b  mov     rdx, rax; SourceString
0x18003a98e  lea     rcx, ?GlobalKdcName@@3U_UNICODE_STRING@@A; DestinationString
0x18003a995  call    cs:__imp_RtlInitUnicodeString
0x18003a99b  call    SafeAllocaInitialize
0x18003a9a0  lea     rdx, aMicrosoft; "Microsoft"
0x18003a9a7  lea     rcx, [rbp+1D0h+DestinationString]; DestinationString
0x18003a9ab  call    cs:__imp_RtlInitUnicodeString
0x18003a9b1  lea     rdx, [rbp+1D0h+DestinationString]; struct _UNICODE_STRING *
0x18003a9b5  lea     rcx, ?KdcGlobalFxFastCookieConstant@@3U_STRING@@A; struct _STRING *
0x18003a9bc  call    ?KerbUnicodeStringToKerbString@@YAJPEAU_STRING@@PEAU_UNICODE_STRING@@@Z; KerbUnicodeStringToKerbString(_STRING *,_UNICODE_STRING *)
0x18003a9c1  mov     r9d, eax
0x18003a9c4  test    eax, eax
0x18003a9c6  jz      short loc_18003AA0F
0x18003a9c8  mov     ecx, eax; int
0x18003a9ca  call    ?KerbMapKerbError@@YAJJ@Z; KerbMapKerbError(long)
0x18003a9cf  mov     [rsp+2D0h+var_290], eax
0x18003a9d3  mov     rcx, cs:WPP_GLOBAL_Control
0x18003a9da  cmp     rcx, rdi
0x18003a9dd  jz      short loc_18003A9FB
0x18003a9df  test    [rcx+1Ch], r12b
0x18003a9e3  jz      short loc_18003A9FB
0x18003a9e5  mov     edx, 55h ; 'U'
0x18003a9ea  mov     [rsp+2D0h+dwCreationFlags], eax
0x18003a9ee  mov     r8, rsi
0x18003a9f1  mov     rcx, [rcx+10h]
0x18003a9f5  call    WPP_SF_Dd
0x18003a9fa  nop
0x18003a9fb  mov     [rbp+1D0h+var_248], r15b
0x18003a9ff  lea     rcx, [rsp+2D0h+var_280]
0x18003aa04  call    _lambda_8fd44bed28da3d7ef7a2050c13fca057___operator__
0x18003aa09  nop
0x18003aa0a  jmp     loc_18003B44D
0x18003aa0f  mov     ecx, 28h ; '('; size
0x18003aa14  call    MIDL_user_allocate
0x18003aa19  mov     [rbp+1D0h+var_240], rax
0x18003aa1d  test    rax, rax
0x18003aa20  jnz     short loc_18003AA66
0x18003aa22  mov     [rsp+2D0h+var_290], 0C0000017h
0x18003aa2a  mov     rcx, cs:WPP_GLOBAL_Control
0x18003aa31  cmp     rcx, rdi
0x18003aa34  jz      short loc_18003AA52
0x18003aa36  test    [rcx+1Ch], r12b
0x18003aa3a  jz      short loc_18003AA52
0x18003aa3c  lea     edx, [rax+56h]
0x18003aa3f  mov     r9d, 0C0000017h
0x18003aa45  mov     r8, rsi
0x18003aa48  mov     rcx, [rcx+10h]
0x18003aa4c  call    WPP_SF_d
0x18003aa51  nop
0x18003aa52  mov     [rbp+1D0h+var_248], r15b
0x18003aa56  lea     rcx, [rsp+2D0h+var_280]
0x18003aa5b  call    _lambda_8fd44bed28da3d7ef7a2050c13fca057___operator__
0x18003aa60  nop
0x18003aa61  jmp     loc_18003B44D
0x18003aa66  mov     word ptr [rax], 0Bh
0x18003aa6b  mov     rax, [rbp+1D0h+var_240]
0x18003aa6f  mov     [rax+2], r13w
0x18003aa74  mov     rcx, [rbp+1D0h+var_240]
0x18003aa78  add     rcx, 8; DestinationString
0x18003aa7c  lea     rdx, aWellknown; "WELLKNOWN"
0x18003aa83  call    cs:__imp_RtlInitUnicodeString
0x18003aa89  mov     rcx, [rbp+1D0h+var_240]
0x18003aa8d  add     rcx, 18h; DestinationString
0x18003aa91  lea     rdx, aAnonymous; "ANONYMOUS"
0x18003aa98  call    cs:__imp_RtlInitUnicodeString
0x18003aa9e  mov     rdx, [rbp+1D0h+var_240]; struct _KERB_INTERNAL_NAME *
0x18003aaa2  lea     rcx, ?KdcGlobalAnonymousPrincipalName@@3UKERB_PRINCIPAL_NAME@@A; struct KERB_PRINCIPAL_NAME *
0x18003aaa9  call    ?KerbConvertKdcNameToPrincipalName@@YAJPEAUKERB_PRINCIPAL_NAME@@PEAU_KERB_INTERNAL_NAME@@@Z; KerbConvertKdcNameToPrincipalName(KERB_PRINCIPAL_NAME *,_KERB_INTERNAL_NAME *)
0x18003aaae  mov     r9d, eax
0x18003aab1  test    eax, eax
0x18003aab3  jz      short loc_18003AAFC
0x18003aab5  mov     ecx, eax; int
0x18003aab7  call    ?KerbMapKerbError@@YAJJ@Z; KerbMapKerbError(long)
0x18003aabc  mov     [rsp+2D0h+var_290], eax
0x18003aac0  mov     rcx, cs:WPP_GLOBAL_Control
0x18003aac7  cmp     rcx, rdi
0x18003aaca  jz      short loc_18003AAE8
0x18003aacc  test    [rcx+1Ch], r12b
0x18003aad0  jz      short loc_18003AAE8
0x18003aad2  mov     edx, 57h ; 'W'
0x18003aad7  mov     [rsp+2D0h+dwCreationFlags], eax
0x18003aadb  mov     r8, rsi
0x18003aade  mov     rcx, [rcx+10h]
0x18003aae2  call    WPP_SF_Dd
0x18003aae7  nop
0x18003aae8  mov     [rbp+1D0h+var_248], r15b
0x18003aaec  lea     rcx, [rsp+2D0h+var_280]
0x18003aaf1  call    _lambda_8fd44bed28da3d7ef7a2050c13fca057___operator__
0x18003aaf6  nop
  ... truncated ...
```
