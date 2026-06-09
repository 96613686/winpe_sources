# MDM_Policy_Result01_LocalPoliciesSecurityOptions02_InvokeModifyInstance

- ea: `0x1801678bc`
- end: `0x180168790`
- name: `MDM_Policy_Result01_LocalPoliciesSecurityOptions02_InvokeModifyInstance`
- size: `3796`
- prototype: ``
- caller_count: `1`
- callee_count: `12`
- tags: `registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x1801687a0`

## callees

- `0x180001008`
- `0x18000104c`
- `0x180003abc`
- `0x18000a768`
- `0x1801678bc`
- `0x18023f3ac`
- `0x180241010`
- `0x18024237c`
- `0x180245824`
- `0x180245930`
- `0x18024cd20`
- `0x18024f010`

## string_xrefs

- `0x180167b4a`: `Accounts_RenameAdministratorAccount`
- `0x180167b8a`: `Accounts_RenameGuestAccount`
- `0x180167c4a`: `Devices_PreventUsersFromInstallingPrinterDriversWhenConnectingToSharedPrinters`
- `0x180167c8a`: `Devices_RestrictCDROMAccessToLocallyLoggedOnUserOnly`
- `0x180167e0a`: `InteractiveLogon_MessageTextForUsersAttemptingToLogOn`
- `0x180167e4a`: `InteractiveLogon_MessageTitleForUsersAttemptingToLogOn`
- `0x180167eca`: `MicrosoftNetworkClient_DigitallySignCommunicationsAlways`
- `0x180167f0a`: `MicrosoftNetworkClient_DigitallySignCommunicationsIfServerAgrees`
- `0x180167f8a`: `MicrosoftNetworkServer_DigitallySignCommunicationsAlways`
- `0x180167fca`: `MicrosoftNetworkServer_DigitallySignCommunicationsIfClientAgrees`
- `0x18016800a`: `NetworkAccess_DoNotAllowAnonymousEnumerationOfSAMAccounts`
- `0x18016804a`: `NetworkAccess_DoNotAllowAnonymousEnumerationOfSamAccountsAndShares`
- `0x18016808a`: `NetworkAccess_RestrictAnonymousAccessToNamedPipesAndShares`
- `0x1801680ca`: `NetworkAccess_RestrictClientsAllowedToMakeRemoteCallsToSAM`
- `0x18016810a`: `NetworkSecurity_AllowLocalSystemToUseComputerIdentityForNTLM`
- `0x18016814a`: `NetworkSecurity_AllowPKU2UAuthenticationRequests`
- `0x18016818a`: `NetworkSecurity_DoNotStoreLANManagerHashValueOnNextPasswordChange`
- `0x1801681ca`: `NetworkSecurity_LANManagerAuthenticationLevel`
- `0x18016820a`: `NetworkSecurity_MinimumSessionSecurityForNTLMSSPBasedClients`
- `0x18016824a`: `NetworkSecurity_MinimumSessionSecurityForNTLMSSPBasedServers`
- `0x18016828a`: `NetworkSecurity_RestrictNTLM_AddRemoteServerExceptionsForNTLMAuthentication`
- `0x1801682ca`: `NetworkSecurity_RestrictNTLM_AuditIncomingNTLMTraffic`
- `0x18016830a`: `NetworkSecurity_RestrictNTLM_IncomingNTLMTraffic`
- `0x18016834a`: `NetworkSecurity_RestrictNTLM_OutgoingNTLMTrafficToRemoteServers`
- `0x18016840a`: `UserAccountControl_AllowUIAccessApplicationsToPromptForElevation`
- `0x1801684ca`: `UserAccountControl_DetectApplicationInstallationsAndPromptForElevation`
- `0x18016854a`: `UserAccountControl_OnlyElevateUIAccessApplicationsThatAreInstalledInSecureLocations`
- `0x18016864a`: `UserAccountControl_VirtualizeFileAndRegistryWriteFailuresToPerUserLocations`
- `0x180167907`: `MDM_Policy_Result01_LocalPoliciesSecurityOptions02`

## pseudocode

```c
__int64 __fastcall MDM_Policy_Result01_LocalPoliciesSecurityOptions02_InvokeModifyInstance(__int64 a1, __int64 a2)
{
  _DWORD *v4; // r9
  enum _MI_Result inserted; // edi
  WmiRequestHandler *v6; // r14
  WmiRequestHandler *v8; // [rsp+40h] [rbp-88h] BYREF
  _QWORD v9[5]; // [rsp+48h] [rbp-80h] BYREF
  char v10; // [rsp+70h] [rbp-58h]
  int v11; // [rsp+78h] [rbp-50h] BYREF
  char v12; // [rsp+7Ch] [rbp-4Ch]
  _BYTE v13[16]; // [rsp+80h] [rbp-48h] BYREF
  _DWORD v14[4]; // [rsp+90h] [rbp-38h] BYREF

  v11 = 0;
  v12 = 0;
  v9[0] = &TelemetryEventWriter::`vftable';
  v9[1] = &v11;
  v9[2] = "MDM_Policy_Result01_LocalPoliciesSecurityOptions02";
  _TlgActivityBase<TraceLoggingActivity<&_tlgProvider_t const * const g_hTraceLoggingProvider,35184372088832,5,_TlgReflectorTag_Param0IsHProvider>,35184372088832,5>::zInternalStart(&v11);
  if ( (unsigned int)dword_180380B68 > 5 && (unsigned __int8)tlgKeywordOn(&dword_180380B68, 0x200000000000LL) )
  {
    if ( v12 && (v14[0] || v14[1] || v14[2] || v14[3]) )
      v4 = v14;
    else
      v4 = 0;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(
      &dword_180380B68,
      &byte_1803561E7,
      v13,
      v4);
  }
  if ( *(_BYTE *)(a2 + 72) && *(_BYTE *)(a2 + 88) )
  {
    TelemetryEventWriter::WriteStart(
      (TelemetryEventWriter *)v9,
      "ModifyInstanceStart",
      *(const unsigned __int16 **)(a2 + 80),
      *(const unsigned __int16 **)(a2 + 64));
    v8 = 0;
    inserted = (unsigned int)CreateRequestHandlerInstance(
                               a1,
                               *(_QWORD *)(a2 + 80),
                               *(_QWORD *)(a2 + 64),
                               &MDM_Policy_Result01_LocalPoliciesSecurityOptions02_NodeList,
                               51,
                               3,
                               &v8);
    if ( inserted == MI_RESULT_OK )
    {
      v9[4] = &v8;
      v10 = 1;
      v6 = v8;
      if ( v8 )
      {
        WmiRequestHandler::SetRequestMIInstance(
          v8,
          (const struct _MI_Instance *)a2,
          (struct WmiNodeInfo *)&MDM_Policy_Result01_LocalPoliciesSecurityOptions02_NodeList,
          0x33u);
        if ( *(_BYTE *)(a2 + 100) == 1
          && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                           v6,
                           L"Accounts_BlockMicrosoftAccounts",
                           (void *)(a2 + 96))) != MI_RESULT_OK )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( *(_BYTE *)(a2 + 108) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                v6,
                                L"Accounts_EnableAdministratorAccountStatus",
                                (void *)(a2 + 104))) != MI_RESULT_OK )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( *(_BYTE *)(a2 + 116) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                v6,
                                L"Accounts_EnableGuestAccountStatus",
                                (void *)(a2 + 112))) != MI_RESULT_OK )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( *(_BYTE *)(a2 + 124) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                v6,
                                L"Accounts_LimitLocalAccountUseOfBlankPasswordsToConsoleLogonOnly",
                                (void *)(a2 + 120))) != MI_RESULT_OK )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( *(_BYTE *)(a2 + 136) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                v6,
                                L"Accounts_RenameAdministratorAccount",
                                (void *)(a2 + 128))) != MI_RESULT_OK )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( *(_BYTE *)(a2 + 152) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                v6,
                                L"Accounts_RenameGuestAccount",
                                (void *)(a2 + 144))) != MI_RESULT_OK )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( *(_BYTE *)(a2 + 168) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                v6,
                                L"Devices_AllowedToFormatAndEjectRemovableMedia",
                                (void *)(a2 + 160))) != MI_RESULT_OK )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( *(_BYTE *)(a2 + 180) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                v6,
                                L"Devices_AllowUndockWithoutHavingToLogon",
                                (void *)(a2 + 176))) != MI_RESULT_OK )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( *(_BYTE *)(a2 + 188) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                v6,
                                L"Devices_PreventUsersFromInstallingPrinterDriversWhenConnectingToSharedPrinters",
                                (void *)(a2 + 184))) != MI_RESULT_OK )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( *(_BYTE *)(a2 + 200) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                v6,
                                L"Devices_RestrictCDROMAccessToLocallyLoggedOnUserOnly",
                                (void *)(a2 + 192))) != MI_RESULT_OK )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( *(_BYTE *)(a2 + 212) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                v6,
                                L"InteractiveLogon_DisplayUserInformationWhenTheSessionIsLocked",
                                (void *)(a2 + 208))) != MI_RESULT_OK )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( *(_BYTE *)(a2 + 220) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                v6,
                                L"InteractiveLogon_DoNotDisplayLastSignedIn",
                                (void *)(a2 + 216))) != MI_RESULT_OK )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( *(_BYTE *)(a2 + 228) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                v6,
                                L"InteractiveLogon_DoNotDisplayUsernameAtSignIn",
                                (void *)(a2 + 224))) != MI_RESULT_OK )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( *(_BYTE *)(a2 + 236) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                v6,
                                L"InteractiveLogon_DoNotRequireCTRLALTDEL",
                                (void *)(a2 + 232))) != MI_RESULT_OK )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( *(_BYTE *)(a2 + 244) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                v6,
                                L"InteractiveLogon_MachineInactivityLimit",
                                (void *)(a2 + 240))) != MI_RESULT_OK )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( *(_BYTE *)(a2 + 256) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                v6,
                                L"InteractiveLogon_MessageTextForUsersAttemptingToLogOn",
                                (void *)(a2 + 248))) != MI_RESULT_OK )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( *(_BYTE *)(a2 + 272) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                v6,
                                L"InteractiveLogon_MessageTitleForUsersAttemptingToLogOn",
                                (void *)(a2 + 264))) != MI_RESULT_OK )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( *(_BYTE *)(a2 + 288) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                v6,
                                L"InteractiveLogon_SmartCardRemovalBehavior",
                                (void *)(a2 + 280))) != MI_RESULT_OK )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( *(_BYTE *)(a2 + 300) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                v6,
                                L"MicrosoftNetworkClient_DigitallySignCommunicationsAlways",
                                (void *)(a2 + 296))) != MI_RESULT_OK )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( *(_BYTE *)(a2 + 308) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                v6,
                                L"MicrosoftNetworkClient_DigitallySignCommunicationsIfServerAgrees",
                                (void *)(a2 + 304))) != MI_RESULT_OK )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( *(_BYTE *)(a2 + 316) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                v6,
                                L"MicrosoftNetworkClient_SendUnencryptedPasswordToThirdPartySMBServers",
                                (void *)(a2 + 312))) != MI_RESULT_OK )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( *(_BYTE *)(a2 + 324) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                v6,
                                L"MicrosoftNetworkServer_DigitallySignCommunicationsAlways",
                                (void *)(a2 + 320))) != MI_RESULT_OK )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( *(_BYTE *)(a2 + 332) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                v6,
                                L"MicrosoftNetworkServer_DigitallySignCommunicationsIfClientAgrees",
                                (void *)(a2 + 328))) != MI_RESULT_OK )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( *(_BYTE *)(a2 + 340) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                v6,
                                L"NetworkAccess_DoNotAllowAnonymousEnumerationOfSAMAccounts",
                                (void *)(a2 + 336))) != MI_RESULT_OK )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( *(_BYTE *)(a2 + 348) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                v6,
                                L"NetworkAccess_DoNotAllowAnonymousEnumerationOfSamAccountsAndShares",
                                (void *)(a2 + 344))) != MI_RESULT_OK )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( *(_BYTE *)(a2 + 356) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                v6,
                                L"NetworkAccess_RestrictAnonymousAccessToNamedPipesAndShares",
                                (void *)(a2 + 352))) != MI_RESULT_OK )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( *(_BYTE *)(a2 + 368) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                v6,
                                L"NetworkAccess_RestrictClientsAllowedToMakeRemoteCallsToSAM",
                                (void *)(a2 + 360))) != MI_RESULT_OK )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( *(_BYTE *)(a2 + 380) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                v6,
                                L"NetworkSecurity_AllowLocalSystemToUseComputerIdentityForNTLM",
                                (void *)(a2 + 376))) != MI_RESULT_OK )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( *(_BYTE *)(a2 + 388) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                v6,
                                L"NetworkSecurity_AllowPKU2UAuthenticationRequests",
                                (void *)(a2 + 384))) != MI_RESULT_OK )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( *(_BYTE *)(a2 + 396) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                v6,
                                L"NetworkSecurity_DoNotStoreLANManagerHashValueOnNextPasswordChange",
                                (void *)(a2 + 392))) != MI_RESULT_OK )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( *(_BYTE *)(a2 + 404) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                v6,
                                L"NetworkSecurity_LANManagerAuthenticationLevel",
                                (void *)(a2 + 400))) != MI_RESULT_OK )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( *(_BYTE *)(a2 + 412) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                v6,
                                L"NetworkSecurity_MinimumSessionSecurityForNTLMSSPBasedClients",
                                (void *)(a2 + 408))) != MI_RESULT_OK )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( *(_BYTE *)(a2 + 420) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                v6,
                                L"NetworkSecurity_MinimumSessionSecurityForNTLMSSPBasedServers",
                                (void *)(a2 + 416))) != MI_RESULT_OK )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( *(_BYTE *)(a2 + 432) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                v6,
                                L"NetworkSecurity_RestrictNTLM_AddRemoteServerExceptionsForNTLMAuthentication",
                                (void *)(a2 + 424))) != MI_RESULT_OK )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( *(_BYTE *)(a2 + 444) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                v6,
                                L"NetworkSecurity_RestrictNTLM_AuditIncomingNTLMTraffic",
                                (void *)(a2 + 440))) != MI_RESULT_OK )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( *(_BYTE *)(a2 + 452) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                v6,
                                L"NetworkSecurity_RestrictNTLM_IncomingNTLMTraffic",
                                (void *)(a2 + 448))) != MI_RESULT_OK )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( *(_BYTE *)(a2 + 460) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                v6,
                                L"NetworkSecurity_RestrictNTLM_OutgoingNTLMTrafficToRemoteServers",
                                (void *)(a2 + 456))) != MI_RESULT_OK )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( *(_BYTE *)(a2 + 468) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                v6,
                                L"Shutdown_AllowSystemToBeShutDownWithoutHavingToLogOn",
                                (void *)(a2 + 464))) != MI_RESULT_OK )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( *(_BYTE *)(a2 + 476) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                v6,
                                L"Shutdown_ClearVirtualMemoryPageFile",
                                (void *)(a2 + 472))) != MI_RESULT_OK )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( *(_BYTE *)(a2 + 484) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                v6,
                                L"UserAccountControl_AllowUIAccessApplicationsToPromptForElevation",
                                (void *)(a2 + 480))) != MI_RESULT_OK )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( *(_BYTE *)(a2 + 492) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                v6,
                                L"UserAccountControl_BehaviorOfTheElevationPromptForAdministrators",
                                (void *)(a2 + 488))) != MI_RESULT_OK )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( *(_BYTE *)(a2 + 500) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                v6,
                                L"UserAccountControl_BehaviorOfTheElevationPromptForStandardUsers",
                                (void *)(a2 + 496))) != MI_RESULT_OK )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( *(_BYTE *)(a2 + 508) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                v6,
                                L"UserAccountControl_DetectApplicationInstallationsAndPromptForElevation",
                                (void *)(a2 + 504))) != MI_RESULT_OK )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( *(_BYTE *)(a2 + 516) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                v6,
                                L"UserAccountControl_OnlyElevateExecutableFilesThatAreSignedAndValidated",
                                (void *)(a2 + 512))) != MI_RESULT_OK )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( *(_BYTE *)(a2 + 524) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                v6,
                                L"UserAccountControl_OnlyElevateUIAccessApplicationsThatAreInstalledInSecureLocations",
                                (void *)(a2 + 520))) != MI_RESULT_OK )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( *(_BYTE *)(a2 + 532) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                v6,
                                L"UserAccountControl_RunAllAdministratorsInAdminApprovalMode",
                                (void *)(a2 + 528))) != MI_RESULT_OK )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( *(_BYTE *)(a2 + 540) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                v6,
                                L"UserAccountControl_SwitchToTheSecureDesktopWhenPromptingForElevation",
                                (void *)(a2 + 536))) != MI_RESULT_OK )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( *(_BYTE *)(a2 + 548) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                v6,
                                L"UserAccountControl_UseAdminApprovalMode",
                                (void *)(a2 + 544))) != MI_RESULT_OK )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( *(_BYTE *)(a2 + 556) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                v6,
                                L"UserAccountControl_VirtualizeFileAndRegistryWriteFailuresToPerUserLocations",
                                (void *)(a2 + 552))) != MI_RESULT_OK )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else
        {
          inserted = (*(unsigned int (__fastcall **)(WmiRequestHandler *))(*(_QWORD *)v6 + 16LL))(v6);
          if ( inserted )
          {
            if ( v8 )
              (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
          }
          else
          {
            inserted = (*(unsigned int (__fastcall **)(WmiRequestHandler *))(*(_QWORD *)v6 + 8LL))(v6);
            if ( inserted )
            {
              if ( v8 )
                (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
            }
            else if ( v8 )
            {
              (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
            }
          }
        }
      }
      else
      {
        inserted = MI_RESULT_FAILED;
      }
    }
  }
  else
  {
    inserted = MI_RESULT_INVALID_PARAMETER;
  }
  TelemetryEventWriter::WriteEnd((TelemetryEventWriter *)v9, "ModifyInstanceEnd", inserted);
  v11 = 2;
  if ( (unsigned int)dword_180380B68 > 5 && (unsigned __int8)tlgKeywordOn(&dword_180380B68, 0x200000000000LL) )
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(
      &dword_180380B68,
      qword_180338F90,
      v13,
      0);
  _TlgActivityBase<TraceLoggingActivity<&_tlgProvider_t const * const g_hTraceLoggingProvider,35184372088832,5,_TlgReflectorTag_Param0IsHProvider>,35184372088832,5>::~_TlgActivityBase<TraceLoggingActivity<&_tlgProvider_t const * const g_hTraceLoggingProvider,35184372088832,5,_TlgReflectorTag_Param0IsHProvider>,35184372088832,5>(&v11);
  return (unsigned int)inserted;
}

```

## disassembly

```asm
0x1801678bc  mov     r11, rsp
0x1801678bf  mov     [r11+18h], rsi
0x1801678c3  push    rdi
0x1801678c4  push    r14
0x1801678c6  push    r15
0x1801678c8  sub     rsp, 0B0h
0x1801678cf  mov     rax, cs:__security_cookie
0x1801678d6  xor     rax, rsp
0x1801678d9  mov     [rsp+0C8h+var_28], rax
0x1801678e1  mov     rsi, rdx
0x1801678e4  mov     rdi, rcx
0x1801678e7  mov     [rsp+0C8h+var_50], 0
0x1801678ef  mov     [rsp+0C8h+var_4C], 0
0x1801678f4  lea     rax, ??_7TelemetryEventWriter@@6B@; const TelemetryEventWriter::`vftable'
0x1801678fb  mov     [r11-80h], rax
0x1801678ff  lea     rax, [r11-50h]
0x180167903  mov     [r11-78h], rax
0x180167907  lea     rax, aMdmPolicyResul_192; "MDM_Policy_Result01_LocalPoliciesSecuri"...
0x18016790e  mov     [r11-70h], rax
0x180167912  lea     rcx, [r11-50h]
0x180167916  call    ?zInternalStart@?$_TlgActivityBase@V?$TraceLoggingActivity@$1?g_hTraceLoggingProvider@@3QEBU_tlgProvider_t@@EB$0CAAAAAAAAAAA@$04U_TlgReflectorTag_Param0IsHProvider@@@@$0CAAAAAAAAAAA@$04@@QEAAXXZ; _TlgActivityBase<TraceLoggingActivity<&_tlgProvider_t const * const g_hTraceLoggingProvider,35184372088832,5,_TlgReflectorTag_Param0IsHProvider>,35184372088832,5>::zInternalStart(void)
0x18016791b  mov     eax, cs:dword_180380B68
0x180167921  cmp     eax, 5
0x180167924  jbe     short loc_180167997
0x180167926  mov     rdx, 200000000000h
0x180167930  lea     rcx, dword_180380B68
0x180167937  call    _tlgKeywordOn
0x18016793c  test    al, al
0x18016793e  jz      short loc_180167997
0x180167940  cmp     [rsp+0C8h+var_4C], 0
0x180167945  jz      short loc_180167979
0x180167947  cmp     [rsp+0C8h+var_38], 0
0x18016794f  jnz     short loc_18016796F
0x180167951  cmp     [rsp+0C8h+var_34], 0
0x180167959  jnz     short loc_18016796F
0x18016795b  cmp     [rsp+0C8h+var_30], 0
0x180167963  jnz     short loc_18016796F
0x180167965  cmp     [rsp+0C8h+var_2C], 0
0x18016796d  jz      short loc_180167979
0x18016796f  lea     r9, [rsp+0C8h+var_38]
0x180167977  jmp     short loc_18016797C
0x180167979  xor     r9d, r9d
0x18016797c  lea     r8, [rsp+0C8h+var_48]
0x180167984  lea     rdx, byte_1803561E7
0x18016798b  lea     rcx, dword_180380B68
0x180167992  call    ??$Write@$$V@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *)
0x180167997  cmp     byte ptr [rsi+48h], 0
0x18016799b  jz      loc_1801686F9
0x1801679a1  cmp     byte ptr [rsi+58h], 0
0x1801679a5  jz      loc_1801686F9
0x1801679ab  mov     r9, [rsi+40h]; unsigned __int16 *
0x1801679af  mov     r8, [rsi+50h]; unsigned __int16 *
0x1801679b3  lea     rdx, aModifyinstance; "ModifyInstanceStart"
0x1801679ba  lea     rcx, [rsp+0C8h+var_80]; this
0x1801679bf  call    ?WriteStart@TelemetryEventWriter@@QEAAXPEBDPEBG1@Z; TelemetryEventWriter::WriteStart(char const *,ushort const *,ushort const *)
0x1801679c4  nop
0x1801679c5  mov     [rsp+0C8h+var_88], 0
0x1801679ce  lea     rax, [rsp+0C8h+var_88]
0x1801679d3  mov     [rsp+0C8h+var_98], rax
0x1801679d8  mov     [rsp+0C8h+var_A0], 3
0x1801679e0  mov     [rsp+0C8h+var_A8], 33h ; '3'
0x1801679e8  lea     r9, ?MDM_Policy_Result01_LocalPoliciesSecurityOptions02_NodeList@@3PAUWmiNodeInfo@@A; WmiNodeInfo near * MDM_Policy_Result01_LocalPoliciesSecurityOptions02_NodeList
0x1801679ef  mov     r8, [rsi+40h]
0x1801679f3  mov     rdx, [rsi+50h]
0x1801679f7  mov     rcx, rdi
0x1801679fa  call    ?CreateRequestHandlerInstance@@YA?AW4_MI_Result@@PEAU_MI_Context@@PEBG1PEAUWmiNodeInfo@@KW4RequestType@@AEAPEAVWmiRequestHandler@@@Z; CreateRequestHandlerInstance(_MI_Context *,ushort const *,ushort const *,WmiNodeInfo *,ulong,RequestType,WmiRequestHandler * &)
0x1801679ff  mov     edi, eax
0x180167a01  test    eax, eax
0x180167a03  jz      short loc_180167A0A
0x180167a05  jmp     loc_1801686FE
0x180167a0a  lea     rax, [rsp+0C8h+var_88]
0x180167a0f  mov     [rsp+0C8h+var_60], rax
0x180167a14  mov     r15d, 1
0x180167a1a  mov     [rsp+0C8h+var_58], r15b
0x180167a1f  mov     r14, [rsp+0C8h+var_88]
0x180167a24  test    r14, r14
0x180167a27  jnz     short loc_180167A31
0x180167a29  mov     edi, r15d
0x180167a2c  jmp     loc_1801686FE
0x180167a31  mov     r9d, 33h ; '3'; unsigned int
0x180167a37  lea     r8, ?MDM_Policy_Result01_LocalPoliciesSecurityOptions02_NodeList@@3PAUWmiNodeInfo@@A; struct WmiNodeInfo *
0x180167a3e  mov     rdx, rsi; struct _MI_Instance *
0x180167a41  mov     rcx, r14; this
0x180167a44  call    ?SetRequestMIInstance@WmiRequestHandler@@QEAA?AW4_MI_Result@@PEBU_MI_Instance@@PEAUWmiNodeInfo@@K@Z; WmiRequestHandler::SetRequestMIInstance(_MI_Instance const *,WmiNodeInfo *,ulong)
0x180167a49  lea     r8, [rsi+60h]; void *
0x180167a4d  cmp     [r8+4], r15b
0x180167a51  jnz     short loc_180167A86
0x180167a53  lea     rdx, aAccountsBlockm; "Accounts_BlockMicrosoftAccounts"
0x180167a5a  mov     rcx, r14; this
0x180167a5d  call    ?InsertDataForNode@WmiRequestHandlerAdd@@QEAA?AW4_MI_Result@@PEBGPEAX@Z; WmiRequestHandlerAdd::InsertDataForNode(ushort const *,void *)
0x180167a62  mov     edi, eax
0x180167a64  test    eax, eax
0x180167a66  jz      short loc_180167A86
0x180167a68  mov     rcx, [rsp+0C8h+var_88]
0x180167a6d  test    rcx, rcx
0x180167a70  jz      short loc_180167A81
0x180167a72  mov     rax, [rcx]
0x180167a75  mov     edx, r15d
0x180167a78  mov     rax, [rax]
0x180167a7b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180167a80  nop
0x180167a81  jmp     loc_1801686FE
0x180167a86  lea     r8, [rsi+68h]; void *
0x180167a8a  cmp     [r8+4], r15b
0x180167a8e  jnz     short loc_180167AC3
0x180167a90  lea     rdx, aAccountsEnable_0; "Accounts_EnableAdministratorAccountStat"...
0x180167a97  mov     rcx, r14; this
0x180167a9a  call    ?InsertDataForNode@WmiRequestHandlerAdd@@QEAA?AW4_MI_Result@@PEBGPEAX@Z; WmiRequestHandlerAdd::InsertDataForNode(ushort const *,void *)
0x180167a9f  mov     edi, eax
0x180167aa1  test    eax, eax
0x180167aa3  jz      short loc_180167AC3
0x180167aa5  mov     rcx, [rsp+0C8h+var_88]
0x180167aaa  test    rcx, rcx
0x180167aad  jz      short loc_180167ABE
0x180167aaf  mov     rax, [rcx]
0x180167ab2  mov     edx, r15d
0x180167ab5  mov     rax, [rax]
0x180167ab8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180167abd  nop
0x180167abe  jmp     loc_1801686FE
0x180167ac3  lea     r8, [rsi+70h]; void *
0x180167ac7  cmp     [r8+4], r15b
0x180167acb  jnz     short loc_180167B00
0x180167acd  lea     rdx, aAccountsEnable; "Accounts_EnableGuestAccountStatus"
0x180167ad4  mov     rcx, r14; this
0x180167ad7  call    ?InsertDataForNode@WmiRequestHandlerAdd@@QEAA?AW4_MI_Result@@PEBGPEAX@Z; WmiRequestHandlerAdd::InsertDataForNode(ushort const *,void *)
0x180167adc  mov     edi, eax
0x180167ade  test    eax, eax
0x180167ae0  jz      short loc_180167B00
0x180167ae2  mov     rcx, [rsp+0C8h+var_88]
0x180167ae7  test    rcx, rcx
0x180167aea  jz      short loc_180167AFB
0x180167aec  mov     rax, [rcx]
0x180167aef  mov     edx, r15d
0x180167af2  mov     rax, [rax]
0x180167af5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180167afa  nop
0x180167afb  jmp     loc_1801686FE
0x180167b00  lea     r8, [rsi+78h]; void *
0x180167b04  cmp     [r8+4], r15b
0x180167b08  jnz     short loc_180167B3D
0x180167b0a  lea     rdx, aAccountsLimitl; "Accounts_LimitLocalAccountUseOfBlankPas"...
0x180167b11  mov     rcx, r14; this
0x180167b14  call    ?InsertDataForNode@WmiRequestHandlerAdd@@QEAA?AW4_MI_Result@@PEBGPEAX@Z; WmiRequestHandlerAdd::InsertDataForNode(ushort const *,void *)
0x180167b19  mov     edi, eax
0x180167b1b  test    eax, eax
0x180167b1d  jz      short loc_180167B3D
0x180167b1f  mov     rcx, [rsp+0C8h+var_88]
0x180167b24  test    rcx, rcx
0x180167b27  jz      short loc_180167B38
0x180167b29  mov     rax, [rcx]
0x180167b2c  mov     edx, r15d
0x180167b2f  mov     rax, [rax]
0x180167b32  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180167b37  nop
0x180167b38  jmp     loc_1801686FE
0x180167b3d  lea     r8, [rsi+80h]; void *
0x180167b44  cmp     [r8+8], r15b
0x180167b48  jnz     short loc_180167B7D
0x180167b4a  lea     rdx, aAccountsRename_0; "Accounts_RenameAdministratorAccount"
0x180167b51  mov     rcx, r14; this
0x180167b54  call    ?InsertDataForNode@WmiRequestHandlerAdd@@QEAA?AW4_MI_Result@@PEBGPEAX@Z; WmiRequestHandlerAdd::InsertDataForNode(ushort const *,void *)
0x180167b59  mov     edi, eax
0x180167b5b  test    eax, eax
0x180167b5d  jz      short loc_180167B7D
0x180167b5f  mov     rcx, [rsp+0C8h+var_88]
0x180167b64  test    rcx, rcx
0x180167b67  jz      short loc_180167B78
0x180167b69  mov     rax, [rcx]
0x180167b6c  mov     edx, r15d
0x180167b6f  mov     rax, [rax]
0x180167b72  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180167b77  nop
0x180167b78  jmp     loc_1801686FE
0x180167b7d  lea     r8, [rsi+90h]; void *
0x180167b84  cmp     [r8+8], r15b
0x180167b88  jnz     short loc_180167BBD
0x180167b8a  lea     rdx, aAccountsRename; "Accounts_RenameGuestAccount"
0x180167b91  mov     rcx, r14; this
0x180167b94  call    ?InsertDataForNode@WmiRequestHandlerAdd@@QEAA?AW4_MI_Result@@PEBGPEAX@Z; WmiRequestHandlerAdd::InsertDataForNode(ushort const *,void *)
0x180167b99  mov     edi, eax
0x180167b9b  test    eax, eax
0x180167b9d  jz      short loc_180167BBD
0x180167b9f  mov     rcx, [rsp+0C8h+var_88]
0x180167ba4  test    rcx, rcx
0x180167ba7  jz      short loc_180167BB8
0x180167ba9  mov     rax, [rcx]
0x180167bac  mov     edx, r15d
0x180167baf  mov     rax, [rax]
0x180167bb2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180167bb7  nop
0x180167bb8  jmp     loc_1801686FE
0x180167bbd  lea     r8, [rsi+0A0h]; void *
0x180167bc4  cmp     [r8+8], r15b
0x180167bc8  jnz     short loc_180167BFD
0x180167bca  lea     rdx, aDevicesAllowed; "Devices_AllowedToFormatAndEjectRemovabl"...
0x180167bd1  mov     rcx, r14; this
0x180167bd4  call    ?InsertDataForNode@WmiRequestHandlerAdd@@QEAA?AW4_MI_Result@@PEBGPEAX@Z; WmiRequestHandlerAdd::InsertDataForNode(ushort const *,void *)
0x180167bd9  mov     edi, eax
0x180167bdb  test    eax, eax
0x180167bdd  jz      short loc_180167BFD
0x180167bdf  mov     rcx, [rsp+0C8h+var_88]
0x180167be4  test    rcx, rcx
0x180167be7  jz      short loc_180167BF8
0x180167be9  mov     rax, [rcx]
0x180167bec  mov     edx, r15d
0x180167bef  mov     rax, [rax]
0x180167bf2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180167bf7  nop
0x180167bf8  jmp     loc_1801686FE
0x180167bfd  lea     r8, [rsi+0B0h]; void *
0x180167c04  cmp     [r8+4], r15b
0x180167c08  jnz     short loc_180167C3D
0x180167c0a  lea     rdx, aDevicesAllowun; "Devices_AllowUndockWithoutHavingToLogon"
0x180167c11  mov     rcx, r14; this
0x180167c14  call    ?InsertDataForNode@WmiRequestHandlerAdd@@QEAA?AW4_MI_Result@@PEBGPEAX@Z; WmiRequestHandlerAdd::InsertDataForNode(ushort const *,void *)
0x180167c19  mov     edi, eax
0x180167c1b  test    eax, eax
0x180167c1d  jz      short loc_180167C3D
0x180167c1f  mov     rcx, [rsp+0C8h+var_88]
0x180167c24  test    rcx, rcx
0x180167c27  jz      short loc_180167C38
0x180167c29  mov     rax, [rcx]
0x180167c2c  mov     edx, r15d
0x180167c2f  mov     rax, [rax]
0x180167c32  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180167c37  nop
0x180167c38  jmp     loc_1801686FE
0x180167c3d  lea     r8, [rsi+0B8h]; void *
0x180167c44  cmp     [r8+4], r15b
0x180167c48  jnz     short loc_180167C7D
0x180167c4a  lea     rdx, aDevicesPrevent; "Devices_PreventUsersFromInstallingPrint"...
0x180167c51  mov     rcx, r14; this
0x180167c54  call    ?InsertDataForNode@WmiRequestHandlerAdd@@QEAA?AW4_MI_Result@@PEBGPEAX@Z; WmiRequestHandlerAdd::InsertDataForNode(ushort const *,void *)
0x180167c59  mov     edi, eax
0x180167c5b  test    eax, eax
0x180167c5d  jz      short loc_180167C7D
0x180167c5f  mov     rcx, [rsp+0C8h+var_88]
0x180167c64  test    rcx, rcx
0x180167c67  jz      short loc_180167C78
0x180167c69  mov     rax, [rcx]
0x180167c6c  mov     edx, r15d
0x180167c6f  mov     rax, [rax]
0x180167c72  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180167c77  nop
0x180167c78  jmp     loc_1801686FE
0x180167c7d  lea     r8, [rsi+0C0h]; void *
0x180167c84  cmp     [r8+8], r15b
0x180167c88  jnz     short loc_180167CBD
0x180167c8a  lea     rdx, aDevicesRestric; "Devices_RestrictCDROMAccessToLocallyLog"...
0x180167c91  mov     rcx, r14; this
0x180167c94  call    ?InsertDataForNode@WmiRequestHandlerAdd@@QEAA?AW4_MI_Result@@PEBGPEAX@Z; WmiRequestHandlerAdd::InsertDataForNode(ushort const *,void *)
0x180167c99  mov     edi, eax
0x180167c9b  test    eax, eax
0x180167c9d  jz      short loc_180167CBD
0x180167c9f  mov     rcx, [rsp+0C8h+var_88]
0x180167ca4  test    rcx, rcx
0x180167ca7  jz      short loc_180167CB8
0x180167ca9  mov     rax, [rcx]
0x180167cac  mov     edx, r15d
0x180167caf  mov     rax, [rax]
0x180167cb2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180167cb7  nop
0x180167cb8  jmp     loc_1801686FE
0x180167cbd  lea     r8, [rsi+0D0h]; void *
0x180167cc4  cmp     [r8+4], r15b
0x180167cc8  jnz     short loc_180167CFD
0x180167cca  lea     rdx, aInteractivelog; "InteractiveLogon_DisplayUserInformation"...
0x180167cd1  mov     rcx, r14; this
0x180167cd4  call    ?InsertDataForNode@WmiRequestHandlerAdd@@QEAA?AW4_MI_Result@@PEBGPEAX@Z; WmiRequestHandlerAdd::InsertDataForNode(ushort const *,void *)
0x180167cd9  mov     edi, eax
0x180167cdb  test    eax, eax
0x180167cdd  jz      short loc_180167CFD
0x180167cdf  mov     rcx, [rsp+0C8h+var_88]
0x180167ce4  test    rcx, rcx
0x180167ce7  jz      short loc_180167CF8
0x180167ce9  mov     rax, [rcx]
0x180167cec  mov     edx, r15d
0x180167cef  mov     rax, [rax]
0x180167cf2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180167cf7  nop
0x180167cf8  jmp     loc_1801686FE
0x180167cfd  lea     r8, [rsi+0D8h]; void *
0x180167d04  cmp     [r8+4], r15b
0x180167d08  jnz     short loc_180167D3D
0x180167d0a  lea     rdx, aInteractivelog_5; "InteractiveLogon_DoNotDisplayLastSigned"...
0x180167d11  mov     rcx, r14; this
0x180167d14  call    ?InsertDataForNode@WmiRequestHandlerAdd@@QEAA?AW4_MI_Result@@PEBGPEAX@Z; WmiRequestHandlerAdd::InsertDataForNode(ushort const *,void *)
0x180167d19  mov     edi, eax
0x180167d1b  test    eax, eax
0x180167d1d  jz      short loc_180167D3D
0x180167d1f  mov     rcx, [rsp+0C8h+var_88]
0x180167d24  test    rcx, rcx
0x180167d27  jz      short loc_180167D38
0x180167d29  mov     rax, [rcx]
0x180167d2c  mov     edx, r15d
0x180167d2f  mov     rax, [rax]
0x180167d32  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180167d37  nop
0x180167d38  jmp     loc_1801686FE
  ... truncated ...
```
