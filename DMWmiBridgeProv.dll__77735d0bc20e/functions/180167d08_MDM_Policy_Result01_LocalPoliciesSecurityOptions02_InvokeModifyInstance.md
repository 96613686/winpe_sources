# MDM_Policy_Result01_LocalPoliciesSecurityOptions02_InvokeModifyInstance

- ea: `0x180167d08`
- end: `0x180168bdb`
- name: `MDM_Policy_Result01_LocalPoliciesSecurityOptions02_InvokeModifyInstance`
- size: `3795`
- prototype: ``
- caller_count: `1`
- callee_count: `12`
- tags: `registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x180168bf0`

## callees

- `0x180001008`
- `0x18000104c`
- `0x180003a5c`
- `0x18000a280`
- `0x180167d08`
- `0x180240078`
- `0x180241ce0`
- `0x180243010`
- `0x180246310`
- `0x180246418`
- `0x18024d160`
- `0x18024f010`

## string_xrefs

- `0x180167f96`: `Accounts_RenameAdministratorAccount`
- `0x180167fd6`: `Accounts_RenameGuestAccount`
- `0x180168096`: `Devices_PreventUsersFromInstallingPrinterDriversWhenConnectingToSharedPrinters`
- `0x1801680d6`: `Devices_RestrictCDROMAccessToLocallyLoggedOnUserOnly`
- `0x180168256`: `InteractiveLogon_MessageTextForUsersAttemptingToLogOn`
- `0x180168296`: `InteractiveLogon_MessageTitleForUsersAttemptingToLogOn`
- `0x180168316`: `MicrosoftNetworkClient_DigitallySignCommunicationsAlways`
- `0x180168356`: `MicrosoftNetworkClient_DigitallySignCommunicationsIfServerAgrees`
- `0x1801683d6`: `MicrosoftNetworkServer_DigitallySignCommunicationsAlways`
- `0x180168416`: `MicrosoftNetworkServer_DigitallySignCommunicationsIfClientAgrees`
- `0x180168456`: `NetworkAccess_DoNotAllowAnonymousEnumerationOfSAMAccounts`
- `0x180168496`: `NetworkAccess_DoNotAllowAnonymousEnumerationOfSamAccountsAndShares`
- `0x1801684d6`: `NetworkAccess_RestrictAnonymousAccessToNamedPipesAndShares`
- `0x180168516`: `NetworkAccess_RestrictClientsAllowedToMakeRemoteCallsToSAM`
- `0x180168556`: `NetworkSecurity_AllowLocalSystemToUseComputerIdentityForNTLM`
- `0x180168596`: `NetworkSecurity_AllowPKU2UAuthenticationRequests`
- `0x1801685d6`: `NetworkSecurity_DoNotStoreLANManagerHashValueOnNextPasswordChange`
- `0x180168616`: `NetworkSecurity_LANManagerAuthenticationLevel`
- `0x180168656`: `NetworkSecurity_MinimumSessionSecurityForNTLMSSPBasedClients`
- `0x180168696`: `NetworkSecurity_MinimumSessionSecurityForNTLMSSPBasedServers`
- `0x1801686d6`: `NetworkSecurity_RestrictNTLM_AddRemoteServerExceptionsForNTLMAuthentication`
- `0x180168716`: `NetworkSecurity_RestrictNTLM_AuditIncomingNTLMTraffic`
- `0x180168756`: `NetworkSecurity_RestrictNTLM_IncomingNTLMTraffic`
- `0x180168796`: `NetworkSecurity_RestrictNTLM_OutgoingNTLMTrafficToRemoteServers`
- `0x180168856`: `UserAccountControl_AllowUIAccessApplicationsToPromptForElevation`
- `0x180168916`: `UserAccountControl_DetectApplicationInstallationsAndPromptForElevation`
- `0x180168996`: `UserAccountControl_OnlyElevateUIAccessApplicationsThatAreInstalledInSecureLocations`
- `0x180168a96`: `UserAccountControl_VirtualizeFileAndRegistryWriteFailuresToPerUserLocations`
- `0x180167d53`: `MDM_Policy_Result01_LocalPoliciesSecurityOptions02`

## pseudocode

```c
__int64 __fastcall MDM_Policy_Result01_LocalPoliciesSecurityOptions02_InvokeModifyInstance(__int64 a1, __int64 a2)
{
  _DWORD *v4; // r9
  unsigned int inserted; // edi
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
    inserted = CreateRequestHandlerInstance(
                 a1,
                 *(wchar_t **)(a2 + 80),
                 *(const unsigned __int16 **)(a2 + 64),
                 (struct WmiNodeInfo *)&MDM_Policy_Result01_LocalPoliciesSecurityOptions02_NodeList,
                 0x33u,
                 3,
                 &v8);
    if ( !inserted )
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
                           (LONG *)(a2 + 96))) != 0 )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( *(_BYTE *)(a2 + 108) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                v6,
                                L"Accounts_EnableAdministratorAccountStatus",
                                (LONG *)(a2 + 104))) != 0 )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( *(_BYTE *)(a2 + 116) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                v6,
                                L"Accounts_EnableGuestAccountStatus",
                                (LONG *)(a2 + 112))) != 0 )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( *(_BYTE *)(a2 + 124) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                v6,
                                L"Accounts_LimitLocalAccountUseOfBlankPasswordsToConsoleLogonOnly",
                                (LONG *)(a2 + 120))) != 0 )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( *(_BYTE *)(a2 + 136) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                v6,
                                L"Accounts_RenameAdministratorAccount",
                                (LONG *)(a2 + 128))) != 0 )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( *(_BYTE *)(a2 + 152) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                v6,
                                L"Accounts_RenameGuestAccount",
                                (LONG *)(a2 + 144))) != 0 )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( *(_BYTE *)(a2 + 168) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                v6,
                                L"Devices_AllowedToFormatAndEjectRemovableMedia",
                                (LONG *)(a2 + 160))) != 0 )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( *(_BYTE *)(a2 + 180) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                v6,
                                L"Devices_AllowUndockWithoutHavingToLogon",
                                (LONG *)(a2 + 176))) != 0 )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( *(_BYTE *)(a2 + 188) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                v6,
                                L"Devices_PreventUsersFromInstallingPrinterDriversWhenConnectingToSharedPrinters",
                                (LONG *)(a2 + 184))) != 0 )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( *(_BYTE *)(a2 + 200) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                v6,
                                L"Devices_RestrictCDROMAccessToLocallyLoggedOnUserOnly",
                                (LONG *)(a2 + 192))) != 0 )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( *(_BYTE *)(a2 + 212) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                v6,
                                L"InteractiveLogon_DisplayUserInformationWhenTheSessionIsLocked",
                                (LONG *)(a2 + 208))) != 0 )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( *(_BYTE *)(a2 + 220) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                v6,
                                L"InteractiveLogon_DoNotDisplayLastSignedIn",
                                (LONG *)(a2 + 216))) != 0 )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( *(_BYTE *)(a2 + 228) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                v6,
                                L"InteractiveLogon_DoNotDisplayUsernameAtSignIn",
                                (LONG *)(a2 + 224))) != 0 )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( *(_BYTE *)(a2 + 236) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                v6,
                                L"InteractiveLogon_DoNotRequireCTRLALTDEL",
                                (LONG *)(a2 + 232))) != 0 )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( *(_BYTE *)(a2 + 244) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                v6,
                                L"InteractiveLogon_MachineInactivityLimit",
                                (LONG *)(a2 + 240))) != 0 )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( *(_BYTE *)(a2 + 256) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                v6,
                                L"InteractiveLogon_MessageTextForUsersAttemptingToLogOn",
                                (LONG *)(a2 + 248))) != 0 )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( *(_BYTE *)(a2 + 272) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                v6,
                                L"InteractiveLogon_MessageTitleForUsersAttemptingToLogOn",
                                (LONG *)(a2 + 264))) != 0 )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( *(_BYTE *)(a2 + 288) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                v6,
                                L"InteractiveLogon_SmartCardRemovalBehavior",
                                (LONG *)(a2 + 280))) != 0 )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( *(_BYTE *)(a2 + 300) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                v6,
                                L"MicrosoftNetworkClient_DigitallySignCommunicationsAlways",
                                (LONG *)(a2 + 296))) != 0 )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( *(_BYTE *)(a2 + 308) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                v6,
                                L"MicrosoftNetworkClient_DigitallySignCommunicationsIfServerAgrees",
                                (LONG *)(a2 + 304))) != 0 )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( *(_BYTE *)(a2 + 316) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                v6,
                                L"MicrosoftNetworkClient_SendUnencryptedPasswordToThirdPartySMBServers",
                                (LONG *)(a2 + 312))) != 0 )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( *(_BYTE *)(a2 + 324) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                v6,
                                L"MicrosoftNetworkServer_DigitallySignCommunicationsAlways",
                                (LONG *)(a2 + 320))) != 0 )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( *(_BYTE *)(a2 + 332) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                v6,
                                L"MicrosoftNetworkServer_DigitallySignCommunicationsIfClientAgrees",
                                (LONG *)(a2 + 328))) != 0 )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( *(_BYTE *)(a2 + 340) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                v6,
                                L"NetworkAccess_DoNotAllowAnonymousEnumerationOfSAMAccounts",
                                (LONG *)(a2 + 336))) != 0 )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( *(_BYTE *)(a2 + 348) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                v6,
                                L"NetworkAccess_DoNotAllowAnonymousEnumerationOfSamAccountsAndShares",
                                (LONG *)(a2 + 344))) != 0 )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( *(_BYTE *)(a2 + 356) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                v6,
                                L"NetworkAccess_RestrictAnonymousAccessToNamedPipesAndShares",
                                (LONG *)(a2 + 352))) != 0 )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( *(_BYTE *)(a2 + 368) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                v6,
                                L"NetworkAccess_RestrictClientsAllowedToMakeRemoteCallsToSAM",
                                (LONG *)(a2 + 360))) != 0 )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( *(_BYTE *)(a2 + 380) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                v6,
                                L"NetworkSecurity_AllowLocalSystemToUseComputerIdentityForNTLM",
                                (LONG *)(a2 + 376))) != 0 )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( *(_BYTE *)(a2 + 388) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                v6,
                                L"NetworkSecurity_AllowPKU2UAuthenticationRequests",
                                (LONG *)(a2 + 384))) != 0 )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( *(_BYTE *)(a2 + 396) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                v6,
                                L"NetworkSecurity_DoNotStoreLANManagerHashValueOnNextPasswordChange",
                                (LONG *)(a2 + 392))) != 0 )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( *(_BYTE *)(a2 + 404) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                v6,
                                L"NetworkSecurity_LANManagerAuthenticationLevel",
                                (LONG *)(a2 + 400))) != 0 )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( *(_BYTE *)(a2 + 412) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                v6,
                                L"NetworkSecurity_MinimumSessionSecurityForNTLMSSPBasedClients",
                                (LONG *)(a2 + 408))) != 0 )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( *(_BYTE *)(a2 + 420) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                v6,
                                L"NetworkSecurity_MinimumSessionSecurityForNTLMSSPBasedServers",
                                (LONG *)(a2 + 416))) != 0 )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( *(_BYTE *)(a2 + 432) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                v6,
                                L"NetworkSecurity_RestrictNTLM_AddRemoteServerExceptionsForNTLMAuthentication",
                                (LONG *)(a2 + 424))) != 0 )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( *(_BYTE *)(a2 + 444) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                v6,
                                L"NetworkSecurity_RestrictNTLM_AuditIncomingNTLMTraffic",
                                (LONG *)(a2 + 440))) != 0 )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( *(_BYTE *)(a2 + 452) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                v6,
                                L"NetworkSecurity_RestrictNTLM_IncomingNTLMTraffic",
                                (LONG *)(a2 + 448))) != 0 )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( *(_BYTE *)(a2 + 460) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                v6,
                                L"NetworkSecurity_RestrictNTLM_OutgoingNTLMTrafficToRemoteServers",
                                (LONG *)(a2 + 456))) != 0 )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( *(_BYTE *)(a2 + 468) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                v6,
                                L"Shutdown_AllowSystemToBeShutDownWithoutHavingToLogOn",
                                (LONG *)(a2 + 464))) != 0 )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( *(_BYTE *)(a2 + 476) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                v6,
                                L"Shutdown_ClearVirtualMemoryPageFile",
                                (LONG *)(a2 + 472))) != 0 )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( *(_BYTE *)(a2 + 484) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                v6,
                                L"UserAccountControl_AllowUIAccessApplicationsToPromptForElevation",
                                (LONG *)(a2 + 480))) != 0 )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( *(_BYTE *)(a2 + 492) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                v6,
                                L"UserAccountControl_BehaviorOfTheElevationPromptForAdministrators",
                                (LONG *)(a2 + 488))) != 0 )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( *(_BYTE *)(a2 + 500) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                v6,
                                L"UserAccountControl_BehaviorOfTheElevationPromptForStandardUsers",
                                (LONG *)(a2 + 496))) != 0 )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( *(_BYTE *)(a2 + 508) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                v6,
                                L"UserAccountControl_DetectApplicationInstallationsAndPromptForElevation",
                                (LONG *)(a2 + 504))) != 0 )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( *(_BYTE *)(a2 + 516) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                v6,
                                L"UserAccountControl_OnlyElevateExecutableFilesThatAreSignedAndValidated",
                                (LONG *)(a2 + 512))) != 0 )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( *(_BYTE *)(a2 + 524) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                v6,
                                L"UserAccountControl_OnlyElevateUIAccessApplicationsThatAreInstalledInSecureLocations",
                                (LONG *)(a2 + 520))) != 0 )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( *(_BYTE *)(a2 + 532) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                v6,
                                L"UserAccountControl_RunAllAdministratorsInAdminApprovalMode",
                                (LONG *)(a2 + 528))) != 0 )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( *(_BYTE *)(a2 + 540) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                v6,
                                L"UserAccountControl_SwitchToTheSecureDesktopWhenPromptingForElevation",
                                (LONG *)(a2 + 536))) != 0 )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( *(_BYTE *)(a2 + 548) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                v6,
                                L"UserAccountControl_UseAdminApprovalMode",
                                (LONG *)(a2 + 544))) != 0 )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( *(_BYTE *)(a2 + 556) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                v6,
                                L"UserAccountControl_VirtualizeFileAndRegistryWriteFailuresToPerUserLocations",
                                (LONG *)(a2 + 552))) != 0 )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else
        {
          inserted = (*(__int64 (__fastcall **)(WmiRequestHandler *))(*(_QWORD *)v6 + 16LL))(v6);
          if ( inserted )
          {
            if ( v8 )
              (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
          }
          else
          {
            inserted = (*(__int64 (__fastcall **)(WmiRequestHandler *))(*(_QWORD *)v6 + 8LL))(v6);
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
        inserted = 1;
      }
    }
  }
  else
  {
    inserted = 4;
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
  return inserted;
}

```

## disassembly

```asm
0x180167d08  mov     r11, rsp
0x180167d0b  mov     [r11+18h], rsi
0x180167d0f  push    rdi
0x180167d10  push    r14
0x180167d12  push    r15
0x180167d14  sub     rsp, 0B0h
0x180167d1b  mov     rax, cs:__security_cookie
0x180167d22  xor     rax, rsp
0x180167d25  mov     [rsp+0C8h+var_28], rax
0x180167d2d  mov     rsi, rdx
0x180167d30  mov     rdi, rcx
0x180167d33  mov     [rsp+0C8h+var_50], 0
0x180167d3b  mov     [rsp+0C8h+var_4C], 0
0x180167d40  lea     rax, ??_7TelemetryEventWriter@@6B@; const TelemetryEventWriter::`vftable'
0x180167d47  mov     [r11-80h], rax
0x180167d4b  lea     rax, [r11-50h]
0x180167d4f  mov     [r11-78h], rax
0x180167d53  lea     rax, aMdmPolicyResul_192; "MDM_Policy_Result01_LocalPoliciesSecuri"...
0x180167d5a  mov     [r11-70h], rax
0x180167d5e  lea     rcx, [r11-50h]
0x180167d62  call    ?zInternalStart@?$_TlgActivityBase@V?$TraceLoggingActivity@$1?g_hTraceLoggingProvider@@3QEBU_tlgProvider_t@@EB$0CAAAAAAAAAAA@$04U_TlgReflectorTag_Param0IsHProvider@@@@$0CAAAAAAAAAAA@$04@@QEAAXXZ; _TlgActivityBase<TraceLoggingActivity<&_tlgProvider_t const * const g_hTraceLoggingProvider,35184372088832,5,_TlgReflectorTag_Param0IsHProvider>,35184372088832,5>::zInternalStart(void)
0x180167d67  mov     eax, cs:dword_180380B68
0x180167d6d  cmp     eax, 5
0x180167d70  jbe     short loc_180167DE3
0x180167d72  mov     rdx, 200000000000h
0x180167d7c  lea     rcx, dword_180380B68
0x180167d83  call    _tlgKeywordOn
0x180167d88  test    al, al
0x180167d8a  jz      short loc_180167DE3
0x180167d8c  cmp     [rsp+0C8h+var_4C], 0
0x180167d91  jz      short loc_180167DC5
0x180167d93  cmp     [rsp+0C8h+var_38], 0
0x180167d9b  jnz     short loc_180167DBB
0x180167d9d  cmp     [rsp+0C8h+var_34], 0
0x180167da5  jnz     short loc_180167DBB
0x180167da7  cmp     [rsp+0C8h+var_30], 0
0x180167daf  jnz     short loc_180167DBB
0x180167db1  cmp     [rsp+0C8h+var_2C], 0
0x180167db9  jz      short loc_180167DC5
0x180167dbb  lea     r9, [rsp+0C8h+var_38]
0x180167dc3  jmp     short loc_180167DC8
0x180167dc5  xor     r9d, r9d
0x180167dc8  lea     r8, [rsp+0C8h+var_48]
0x180167dd0  lea     rdx, byte_1803561E7
0x180167dd7  lea     rcx, dword_180380B68
0x180167dde  call    ??$Write@$$V@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *)
0x180167de3  cmp     byte ptr [rsi+48h], 0
0x180167de7  jz      loc_180168B45
0x180167ded  cmp     byte ptr [rsi+58h], 0
0x180167df1  jz      loc_180168B45
0x180167df7  mov     r9, [rsi+40h]; unsigned __int16 *
0x180167dfb  mov     r8, [rsi+50h]; unsigned __int16 *
0x180167dff  lea     rdx, aModifyinstance; "ModifyInstanceStart"
0x180167e06  lea     rcx, [rsp+0C8h+var_80]; this
0x180167e0b  call    ?WriteStart@TelemetryEventWriter@@QEAAXPEBDPEBG1@Z; TelemetryEventWriter::WriteStart(char const *,ushort const *,ushort const *)
0x180167e10  nop
0x180167e11  mov     [rsp+0C8h+var_88], 0
0x180167e1a  lea     rax, [rsp+0C8h+var_88]
0x180167e1f  mov     [rsp+0C8h+var_98], rax
0x180167e24  mov     [rsp+0C8h+var_A0], 3
0x180167e2c  mov     [rsp+0C8h+var_A8], 33h ; '3'
0x180167e34  lea     r9, ?MDM_Policy_Result01_LocalPoliciesSecurityOptions02_NodeList@@3PAUWmiNodeInfo@@A; WmiNodeInfo near * MDM_Policy_Result01_LocalPoliciesSecurityOptions02_NodeList
0x180167e3b  mov     r8, [rsi+40h]
0x180167e3f  mov     rdx, [rsi+50h]
0x180167e43  mov     rcx, rdi
0x180167e46  call    ?CreateRequestHandlerInstance@@YA?AW4_MI_Result@@PEAU_MI_Context@@PEBG1PEAUWmiNodeInfo@@KW4RequestType@@AEAPEAVWmiRequestHandler@@@Z; CreateRequestHandlerInstance(_MI_Context *,ushort const *,ushort const *,WmiNodeInfo *,ulong,RequestType,WmiRequestHandler * &)
0x180167e4b  mov     edi, eax
0x180167e4d  test    eax, eax
0x180167e4f  jz      short loc_180167E56
0x180167e51  jmp     loc_180168B4A
0x180167e56  lea     rax, [rsp+0C8h+var_88]
0x180167e5b  mov     [rsp+0C8h+var_60], rax
0x180167e60  mov     r15d, 1
0x180167e66  mov     [rsp+0C8h+var_58], r15b
0x180167e6b  mov     r14, [rsp+0C8h+var_88]
0x180167e70  test    r14, r14
0x180167e73  jnz     short loc_180167E7D
0x180167e75  mov     edi, r15d
0x180167e78  jmp     loc_180168B4A
0x180167e7d  mov     r9d, 33h ; '3'; unsigned int
0x180167e83  lea     r8, ?MDM_Policy_Result01_LocalPoliciesSecurityOptions02_NodeList@@3PAUWmiNodeInfo@@A; struct WmiNodeInfo *
0x180167e8a  mov     rdx, rsi; struct _MI_Instance *
0x180167e8d  mov     rcx, r14; this
0x180167e90  call    ?SetRequestMIInstance@WmiRequestHandler@@QEAA?AW4_MI_Result@@PEBU_MI_Instance@@PEAUWmiNodeInfo@@K@Z; WmiRequestHandler::SetRequestMIInstance(_MI_Instance const *,WmiNodeInfo *,ulong)
0x180167e95  lea     r8, [rsi+60h]; void *
0x180167e99  cmp     [r8+4], r15b
0x180167e9d  jnz     short loc_180167ED2
0x180167e9f  lea     rdx, aAccountsBlockm; "Accounts_BlockMicrosoftAccounts"
0x180167ea6  mov     rcx, r14; this
0x180167ea9  call    ?InsertDataForNode@WmiRequestHandlerAdd@@QEAA?AW4_MI_Result@@PEBGPEAX@Z; WmiRequestHandlerAdd::InsertDataForNode(ushort const *,void *)
0x180167eae  mov     edi, eax
0x180167eb0  test    eax, eax
0x180167eb2  jz      short loc_180167ED2
0x180167eb4  mov     rcx, [rsp+0C8h+var_88]
0x180167eb9  test    rcx, rcx
0x180167ebc  jz      short loc_180167ECD
0x180167ebe  mov     rax, [rcx]
0x180167ec1  mov     edx, r15d
0x180167ec4  mov     rax, [rax]
0x180167ec7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180167ecc  nop
0x180167ecd  jmp     loc_180168B4A
0x180167ed2  lea     r8, [rsi+68h]; void *
0x180167ed6  cmp     [r8+4], r15b
0x180167eda  jnz     short loc_180167F0F
0x180167edc  lea     rdx, aAccountsEnable_0; "Accounts_EnableAdministratorAccountStat"...
0x180167ee3  mov     rcx, r14; this
0x180167ee6  call    ?InsertDataForNode@WmiRequestHandlerAdd@@QEAA?AW4_MI_Result@@PEBGPEAX@Z; WmiRequestHandlerAdd::InsertDataForNode(ushort const *,void *)
0x180167eeb  mov     edi, eax
0x180167eed  test    eax, eax
0x180167eef  jz      short loc_180167F0F
0x180167ef1  mov     rcx, [rsp+0C8h+var_88]
0x180167ef6  test    rcx, rcx
0x180167ef9  jz      short loc_180167F0A
0x180167efb  mov     rax, [rcx]
0x180167efe  mov     edx, r15d
0x180167f01  mov     rax, [rax]
0x180167f04  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180167f09  nop
0x180167f0a  jmp     loc_180168B4A
0x180167f0f  lea     r8, [rsi+70h]; void *
0x180167f13  cmp     [r8+4], r15b
0x180167f17  jnz     short loc_180167F4C
0x180167f19  lea     rdx, aAccountsEnable; "Accounts_EnableGuestAccountStatus"
0x180167f20  mov     rcx, r14; this
0x180167f23  call    ?InsertDataForNode@WmiRequestHandlerAdd@@QEAA?AW4_MI_Result@@PEBGPEAX@Z; WmiRequestHandlerAdd::InsertDataForNode(ushort const *,void *)
0x180167f28  mov     edi, eax
0x180167f2a  test    eax, eax
0x180167f2c  jz      short loc_180167F4C
0x180167f2e  mov     rcx, [rsp+0C8h+var_88]
0x180167f33  test    rcx, rcx
0x180167f36  jz      short loc_180167F47
0x180167f38  mov     rax, [rcx]
0x180167f3b  mov     edx, r15d
0x180167f3e  mov     rax, [rax]
0x180167f41  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180167f46  nop
0x180167f47  jmp     loc_180168B4A
0x180167f4c  lea     r8, [rsi+78h]; void *
0x180167f50  cmp     [r8+4], r15b
0x180167f54  jnz     short loc_180167F89
0x180167f56  lea     rdx, aAccountsLimitl; "Accounts_LimitLocalAccountUseOfBlankPas"...
0x180167f5d  mov     rcx, r14; this
0x180167f60  call    ?InsertDataForNode@WmiRequestHandlerAdd@@QEAA?AW4_MI_Result@@PEBGPEAX@Z; WmiRequestHandlerAdd::InsertDataForNode(ushort const *,void *)
0x180167f65  mov     edi, eax
0x180167f67  test    eax, eax
0x180167f69  jz      short loc_180167F89
0x180167f6b  mov     rcx, [rsp+0C8h+var_88]
0x180167f70  test    rcx, rcx
0x180167f73  jz      short loc_180167F84
0x180167f75  mov     rax, [rcx]
0x180167f78  mov     edx, r15d
0x180167f7b  mov     rax, [rax]
0x180167f7e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180167f83  nop
0x180167f84  jmp     loc_180168B4A
0x180167f89  lea     r8, [rsi+80h]; void *
0x180167f90  cmp     [r8+8], r15b
0x180167f94  jnz     short loc_180167FC9
0x180167f96  lea     rdx, aAccountsRename_0; "Accounts_RenameAdministratorAccount"
0x180167f9d  mov     rcx, r14; this
0x180167fa0  call    ?InsertDataForNode@WmiRequestHandlerAdd@@QEAA?AW4_MI_Result@@PEBGPEAX@Z; WmiRequestHandlerAdd::InsertDataForNode(ushort const *,void *)
0x180167fa5  mov     edi, eax
0x180167fa7  test    eax, eax
0x180167fa9  jz      short loc_180167FC9
0x180167fab  mov     rcx, [rsp+0C8h+var_88]
0x180167fb0  test    rcx, rcx
0x180167fb3  jz      short loc_180167FC4
0x180167fb5  mov     rax, [rcx]
0x180167fb8  mov     edx, r15d
0x180167fbb  mov     rax, [rax]
0x180167fbe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180167fc3  nop
0x180167fc4  jmp     loc_180168B4A
0x180167fc9  lea     r8, [rsi+90h]; void *
0x180167fd0  cmp     [r8+8], r15b
0x180167fd4  jnz     short loc_180168009
0x180167fd6  lea     rdx, aAccountsRename; "Accounts_RenameGuestAccount"
0x180167fdd  mov     rcx, r14; this
0x180167fe0  call    ?InsertDataForNode@WmiRequestHandlerAdd@@QEAA?AW4_MI_Result@@PEBGPEAX@Z; WmiRequestHandlerAdd::InsertDataForNode(ushort const *,void *)
0x180167fe5  mov     edi, eax
0x180167fe7  test    eax, eax
0x180167fe9  jz      short loc_180168009
0x180167feb  mov     rcx, [rsp+0C8h+var_88]
0x180167ff0  test    rcx, rcx
0x180167ff3  jz      short loc_180168004
0x180167ff5  mov     rax, [rcx]
0x180167ff8  mov     edx, r15d
0x180167ffb  mov     rax, [rax]
0x180167ffe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180168003  nop
0x180168004  jmp     loc_180168B4A
0x180168009  lea     r8, [rsi+0A0h]; void *
0x180168010  cmp     [r8+8], r15b
0x180168014  jnz     short loc_180168049
0x180168016  lea     rdx, aDevicesAllowed; "Devices_AllowedToFormatAndEjectRemovabl"...
0x18016801d  mov     rcx, r14; this
0x180168020  call    ?InsertDataForNode@WmiRequestHandlerAdd@@QEAA?AW4_MI_Result@@PEBGPEAX@Z; WmiRequestHandlerAdd::InsertDataForNode(ushort const *,void *)
0x180168025  mov     edi, eax
0x180168027  test    eax, eax
0x180168029  jz      short loc_180168049
0x18016802b  mov     rcx, [rsp+0C8h+var_88]
0x180168030  test    rcx, rcx
0x180168033  jz      short loc_180168044
0x180168035  mov     rax, [rcx]
0x180168038  mov     edx, r15d
0x18016803b  mov     rax, [rax]
0x18016803e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180168043  nop
0x180168044  jmp     loc_180168B4A
0x180168049  lea     r8, [rsi+0B0h]; void *
0x180168050  cmp     [r8+4], r15b
0x180168054  jnz     short loc_180168089
0x180168056  lea     rdx, aDevicesAllowun; "Devices_AllowUndockWithoutHavingToLogon"
0x18016805d  mov     rcx, r14; this
0x180168060  call    ?InsertDataForNode@WmiRequestHandlerAdd@@QEAA?AW4_MI_Result@@PEBGPEAX@Z; WmiRequestHandlerAdd::InsertDataForNode(ushort const *,void *)
0x180168065  mov     edi, eax
0x180168067  test    eax, eax
0x180168069  jz      short loc_180168089
0x18016806b  mov     rcx, [rsp+0C8h+var_88]
0x180168070  test    rcx, rcx
0x180168073  jz      short loc_180168084
0x180168075  mov     rax, [rcx]
0x180168078  mov     edx, r15d
0x18016807b  mov     rax, [rax]
0x18016807e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180168083  nop
0x180168084  jmp     loc_180168B4A
0x180168089  lea     r8, [rsi+0B8h]; void *
0x180168090  cmp     [r8+4], r15b
0x180168094  jnz     short loc_1801680C9
0x180168096  lea     rdx, aDevicesPrevent; "Devices_PreventUsersFromInstallingPrint"...
0x18016809d  mov     rcx, r14; this
0x1801680a0  call    ?InsertDataForNode@WmiRequestHandlerAdd@@QEAA?AW4_MI_Result@@PEBGPEAX@Z; WmiRequestHandlerAdd::InsertDataForNode(ushort const *,void *)
0x1801680a5  mov     edi, eax
0x1801680a7  test    eax, eax
0x1801680a9  jz      short loc_1801680C9
0x1801680ab  mov     rcx, [rsp+0C8h+var_88]
0x1801680b0  test    rcx, rcx
0x1801680b3  jz      short loc_1801680C4
0x1801680b5  mov     rax, [rcx]
0x1801680b8  mov     edx, r15d
0x1801680bb  mov     rax, [rax]
0x1801680be  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801680c3  nop
0x1801680c4  jmp     loc_180168B4A
0x1801680c9  lea     r8, [rsi+0C0h]; void *
0x1801680d0  cmp     [r8+8], r15b
0x1801680d4  jnz     short loc_180168109
0x1801680d6  lea     rdx, aDevicesRestric; "Devices_RestrictCDROMAccessToLocallyLog"...
0x1801680dd  mov     rcx, r14; this
0x1801680e0  call    ?InsertDataForNode@WmiRequestHandlerAdd@@QEAA?AW4_MI_Result@@PEBGPEAX@Z; WmiRequestHandlerAdd::InsertDataForNode(ushort const *,void *)
0x1801680e5  mov     edi, eax
0x1801680e7  test    eax, eax
0x1801680e9  jz      short loc_180168109
0x1801680eb  mov     rcx, [rsp+0C8h+var_88]
0x1801680f0  test    rcx, rcx
0x1801680f3  jz      short loc_180168104
0x1801680f5  mov     rax, [rcx]
0x1801680f8  mov     edx, r15d
0x1801680fb  mov     rax, [rax]
0x1801680fe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180168103  nop
0x180168104  jmp     loc_180168B4A
0x180168109  lea     r8, [rsi+0D0h]; void *
0x180168110  cmp     [r8+4], r15b
0x180168114  jnz     short loc_180168149
0x180168116  lea     rdx, aInteractivelog; "InteractiveLogon_DisplayUserInformation"...
0x18016811d  mov     rcx, r14; this
0x180168120  call    ?InsertDataForNode@WmiRequestHandlerAdd@@QEAA?AW4_MI_Result@@PEBGPEAX@Z; WmiRequestHandlerAdd::InsertDataForNode(ushort const *,void *)
0x180168125  mov     edi, eax
0x180168127  test    eax, eax
0x180168129  jz      short loc_180168149
0x18016812b  mov     rcx, [rsp+0C8h+var_88]
0x180168130  test    rcx, rcx
0x180168133  jz      short loc_180168144
0x180168135  mov     rax, [rcx]
0x180168138  mov     edx, r15d
0x18016813b  mov     rax, [rax]
0x18016813e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180168143  nop
0x180168144  jmp     loc_180168B4A
0x180168149  lea     r8, [rsi+0D8h]; void *
0x180168150  cmp     [r8+4], r15b
0x180168154  jnz     short loc_180168189
0x180168156  lea     rdx, aInteractivelog_5; "InteractiveLogon_DoNotDisplayLastSigned"...
0x18016815d  mov     rcx, r14; this
0x180168160  call    ?InsertDataForNode@WmiRequestHandlerAdd@@QEAA?AW4_MI_Result@@PEBGPEAX@Z; WmiRequestHandlerAdd::InsertDataForNode(ushort const *,void *)
0x180168165  mov     edi, eax
0x180168167  test    eax, eax
0x180168169  jz      short loc_180168189
0x18016816b  mov     rcx, [rsp+0C8h+var_88]
0x180168170  test    rcx, rcx
0x180168173  jz      short loc_180168184
0x180168175  mov     rax, [rcx]
0x180168178  mov     edx, r15d
0x18016817b  mov     rax, [rax]
0x18016817e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180168183  nop
0x180168184  jmp     loc_180168B4A
  ... truncated ...
```
