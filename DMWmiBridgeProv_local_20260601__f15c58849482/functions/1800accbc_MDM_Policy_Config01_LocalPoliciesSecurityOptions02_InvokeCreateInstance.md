# MDM_Policy_Config01_LocalPoliciesSecurityOptions02_InvokeCreateInstance

- ea: `0x1800accbc`
- end: `0x1800adc5c`
- name: `MDM_Policy_Config01_LocalPoliciesSecurityOptions02_InvokeCreateInstance`
- size: `4000`
- prototype: `__int64 __fastcall(MI_Instance *self, struct _MI_Instance *)`
- caller_count: `1`
- callee_count: `17`
- tags: `registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x1800acc00`

## callees

- `0x180001008`
- `0x18000104c`
- `0x180003abc`
- `0x180005160`
- `0x180005198`
- `0x180008ac0`
- `0x180008b08`
- `0x18000a768`
- `0x1800accbc`
- `0x18023f3ac`
- `0x180241010`
- `0x18024237c`
- `0x180245824`
- `0x180245930`
- `0x18024ccee`
- `0x18024cd20`
- `0x18024f010`

## string_xrefs

- `0x1800acf7c`: `Accounts_RenameAdministratorAccount`
- `0x1800acfbc`: `Accounts_RenameGuestAccount`
- `0x1800ad07c`: `Devices_PreventUsersFromInstallingPrinterDriversWhenConnectingToSharedPrinters`
- `0x1800ad0bc`: `Devices_RestrictCDROMAccessToLocallyLoggedOnUserOnly`
- `0x1800ad23c`: `InteractiveLogon_MessageTextForUsersAttemptingToLogOn`
- `0x1800ad27c`: `InteractiveLogon_MessageTitleForUsersAttemptingToLogOn`
- `0x1800ad2fc`: `MicrosoftNetworkClient_DigitallySignCommunicationsAlways`
- `0x1800ad33c`: `MicrosoftNetworkClient_DigitallySignCommunicationsIfServerAgrees`
- `0x1800ad3bc`: `MicrosoftNetworkServer_DigitallySignCommunicationsAlways`
- `0x1800ad3fc`: `MicrosoftNetworkServer_DigitallySignCommunicationsIfClientAgrees`
- `0x1800ad43c`: `NetworkAccess_DoNotAllowAnonymousEnumerationOfSAMAccounts`
- `0x1800ad47c`: `NetworkAccess_DoNotAllowAnonymousEnumerationOfSamAccountsAndShares`
- `0x1800ad4bc`: `NetworkAccess_RestrictAnonymousAccessToNamedPipesAndShares`
- `0x1800ad4fc`: `NetworkAccess_RestrictClientsAllowedToMakeRemoteCallsToSAM`
- `0x1800ad53c`: `NetworkSecurity_AllowLocalSystemToUseComputerIdentityForNTLM`
- `0x1800ad57c`: `NetworkSecurity_AllowPKU2UAuthenticationRequests`
- `0x1800ad5bc`: `NetworkSecurity_DoNotStoreLANManagerHashValueOnNextPasswordChange`
- `0x1800ad5fc`: `NetworkSecurity_LANManagerAuthenticationLevel`
- `0x1800ad63c`: `NetworkSecurity_MinimumSessionSecurityForNTLMSSPBasedClients`
- `0x1800ad67c`: `NetworkSecurity_MinimumSessionSecurityForNTLMSSPBasedServers`
- `0x1800ad6bc`: `NetworkSecurity_RestrictNTLM_AddRemoteServerExceptionsForNTLMAuthentication`
- `0x1800ad6fc`: `NetworkSecurity_RestrictNTLM_AuditIncomingNTLMTraffic`
- `0x1800ad73c`: `NetworkSecurity_RestrictNTLM_IncomingNTLMTraffic`
- `0x1800ad77c`: `NetworkSecurity_RestrictNTLM_OutgoingNTLMTrafficToRemoteServers`
- `0x1800ad83c`: `UserAccountControl_AllowUIAccessApplicationsToPromptForElevation`
- `0x1800ad8fc`: `UserAccountControl_DetectApplicationInstallationsAndPromptForElevation`
- `0x1800ad97c`: `UserAccountControl_OnlyElevateUIAccessApplicationsThatAreInstalledInSecureLocations`
- `0x1800ada7c`: `UserAccountControl_VirtualizeFileAndRegistryWriteFailuresToPerUserLocations`
- `0x1800acde5`: `CreateInstanceStart`
- `0x1800adbc2`: `CreateInstanceEnd`
- `0x1800acd2c`: `MDM_Policy_Config01_LocalPoliciesSecurityOptions02`

## pseudocode

```c
// Hidden C++ exception states: #wind=3 #try_helpers=1
__int64 __fastcall MDM_Policy_Config01_LocalPoliciesSecurityOptions02_InvokeCreateInstance(
        MI_Context *self,
        struct _MI_Instance *a2)
{
  _DWORD *v4; // r9
  enum _MI_Result inserted; // edi
  WmiRequestHandler *v6; // r14
  WmiRequestHandler *v8; // [rsp+40h] [rbp-2C8h] BYREF
  char v9; // [rsp+48h] [rbp-2C0h]
  _QWORD v10[5]; // [rsp+50h] [rbp-2B8h] BYREF
  char v11; // [rsp+78h] [rbp-290h]
  int v12; // [rsp+80h] [rbp-288h] BYREF
  char v13; // [rsp+84h] [rbp-284h]
  _BYTE v14[16]; // [rsp+88h] [rbp-280h] BYREF
  _DWORD v15[6]; // [rsp+98h] [rbp-270h] BYREF
  MI_Instance instance; // [rsp+B0h] [rbp-258h] BYREF

  memset_0(&instance, 0, 0x230u);
  v12 = 0;
  v13 = 0;
  v10[0] = &TelemetryEventWriter::`vftable';
  v10[1] = &v12;
  v10[2] = "MDM_Policy_Config01_LocalPoliciesSecurityOptions02";
  _TlgActivityBase<TraceLoggingActivity<&_tlgProvider_t const * const g_hTraceLoggingProvider,35184372088832,5,_TlgReflectorTag_Param0IsHProvider>,35184372088832,5>::zInternalStart(&v12);
  if ( (unsigned int)dword_180380B68 > 5 && (unsigned __int8)tlgKeywordOn(&dword_180380B68, 0x200000000000LL) )
  {
    if ( v13 && (v15[0] || v15[1] || v15[2] || v15[3]) )
      v4 = v15;
    else
      v4 = 0;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(
      &dword_180380B68,
      byte_18033E02D,
      v14,
      v4);
  }
  if ( !LOBYTE(a2[1].classDecl) || (v9 = 0, !LOBYTE(a2[1].nameSpace)) )
  {
    inserted = MI_RESULT_INVALID_PARAMETER;
    goto LABEL_225;
  }
  TelemetryEventWriter::WriteStart(
    (TelemetryEventWriter *)v10,
    "CreateInstanceStart",
    a2[1].serverName,
    (const unsigned __int16 *)a2[1].ft);
  v8 = 0;
  inserted = (unsigned int)CreateRequestHandlerInstance(
                             self,
                             a2[1].serverName,
                             a2[1].ft,
                             &MDM_Policy_Config01_LocalPoliciesSecurityOptions02_NodeList,
                             51,
                             4,
                             &v8);
  if ( inserted == MI_RESULT_OK )
  {
    v10[4] = &v8;
    v11 = 1;
    v6 = v8;
    if ( !v8 )
    {
      inserted = MI_RESULT_FAILED;
      goto LABEL_225;
    }
    WmiRequestHandler::SetRequestMIInstance(
      v8,
      a2,
      (struct WmiNodeInfo *)&MDM_Policy_Config01_LocalPoliciesSecurityOptions02_NodeList,
      0x33u);
    if ( BYTE4(a2[1].reserved[0]) == 1 )
    {
      inserted = WmiRequestHandlerAdd::InsertDataForNode(v6, L"Accounts_BlockMicrosoftAccounts", a2[1].reserved);
      if ( inserted )
      {
        if ( !v8 )
          goto LABEL_225;
LABEL_220:
        (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        goto LABEL_225;
      }
    }
    if ( BYTE4(a2[1].reserved[1]) == 1 )
    {
      inserted = WmiRequestHandlerAdd::InsertDataForNode(
                   v6,
                   L"Accounts_EnableAdministratorAccountStatus",
                   &a2[1].reserved[1]);
      if ( inserted )
      {
        if ( !v8 )
          goto LABEL_225;
        goto LABEL_220;
      }
    }
    if ( BYTE4(a2[1].reserved[2]) == 1 )
    {
      inserted = WmiRequestHandlerAdd::InsertDataForNode(v6, L"Accounts_EnableGuestAccountStatus", &a2[1].reserved[2]);
      if ( inserted )
      {
        if ( !v8 )
          goto LABEL_225;
        goto LABEL_220;
      }
    }
    if ( BYTE4(a2[1].reserved[3]) == 1 )
    {
      inserted = WmiRequestHandlerAdd::InsertDataForNode(
                   v6,
                   L"Accounts_LimitLocalAccountUseOfBlankPasswordsToConsoleLogonOnly",
                   &a2[1].reserved[3]);
      if ( inserted )
      {
        if ( !v8 )
          goto LABEL_225;
        goto LABEL_220;
      }
    }
    if ( LOBYTE(a2[2].classDecl) == 1 )
    {
      inserted = WmiRequestHandlerAdd::InsertDataForNode(v6, L"Accounts_RenameAdministratorAccount", &a2[2]);
      if ( inserted )
      {
        if ( !v8 )
          goto LABEL_225;
        goto LABEL_220;
      }
    }
    if ( LOBYTE(a2[2].nameSpace) == 1 )
    {
      inserted = WmiRequestHandlerAdd::InsertDataForNode(v6, L"Accounts_RenameGuestAccount", &a2[2].serverName);
      if ( inserted )
      {
        if ( !v8 )
          goto LABEL_225;
        goto LABEL_220;
      }
    }
    if ( LOBYTE(a2[2].reserved[1]) == 1 )
    {
      inserted = WmiRequestHandlerAdd::InsertDataForNode(
                   v6,
                   L"Devices_AllowedToFormatAndEjectRemovableMedia",
                   a2[2].reserved);
      if ( inserted )
      {
        if ( !v8 )
          goto LABEL_225;
        goto LABEL_220;
      }
    }
    if ( BYTE4(a2[2].reserved[2]) == 1 )
    {
      inserted = WmiRequestHandlerAdd::InsertDataForNode(
                   v6,
                   L"Devices_AllowUndockWithoutHavingToLogon",
                   &a2[2].reserved[2]);
      if ( inserted )
      {
        if ( !v8 )
          goto LABEL_225;
        goto LABEL_220;
      }
    }
    if ( BYTE4(a2[2].reserved[3]) == 1 )
    {
      inserted = WmiRequestHandlerAdd::InsertDataForNode(
                   v6,
                   L"Devices_PreventUsersFromInstallingPrinterDriversWhenConnectingToSharedPrinters",
                   &a2[2].reserved[3]);
      if ( inserted )
      {
        if ( !v8 )
          goto LABEL_225;
        goto LABEL_220;
      }
    }
    if ( LOBYTE(a2[3].classDecl) == 1 )
    {
      inserted = WmiRequestHandlerAdd::InsertDataForNode(
                   v6,
                   L"Devices_RestrictCDROMAccessToLocallyLoggedOnUserOnly",
                   &a2[3]);
      if ( inserted )
      {
        if ( !v8 )
          goto LABEL_225;
        goto LABEL_220;
      }
    }
    if ( BYTE4(a2[3].serverName) == 1 )
    {
      inserted = WmiRequestHandlerAdd::InsertDataForNode(
                   v6,
                   L"InteractiveLogon_DisplayUserInformationWhenTheSessionIsLocked",
                   &a2[3].serverName);
      if ( inserted )
      {
        if ( !v8 )
          goto LABEL_225;
        goto LABEL_220;
      }
    }
    if ( BYTE4(a2[3].nameSpace) == 1 )
    {
      inserted = WmiRequestHandlerAdd::InsertDataForNode(
                   v6,
                   L"InteractiveLogon_DoNotDisplayLastSignedIn",
                   &a2[3].nameSpace);
      if ( inserted )
      {
        if ( !v8 )
          goto LABEL_225;
        goto LABEL_220;
      }
    }
    if ( BYTE4(a2[3].reserved[0]) == 1 )
    {
      inserted = WmiRequestHandlerAdd::InsertDataForNode(
                   v6,
                   L"InteractiveLogon_DoNotDisplayUsernameAtSignIn",
                   a2[3].reserved);
      if ( inserted )
      {
        if ( !v8 )
          goto LABEL_225;
        goto LABEL_220;
      }
    }
    if ( BYTE4(a2[3].reserved[1]) == 1 )
    {
      inserted = WmiRequestHandlerAdd::InsertDataForNode(
                   v6,
                   L"InteractiveLogon_DoNotRequireCTRLALTDEL",
                   &a2[3].reserved[1]);
      if ( inserted )
      {
        if ( !v8 )
          goto LABEL_225;
        goto LABEL_220;
      }
    }
    if ( BYTE4(a2[3].reserved[2]) == 1 )
    {
      inserted = WmiRequestHandlerAdd::InsertDataForNode(
                   v6,
                   L"InteractiveLogon_MachineInactivityLimit",
                   &a2[3].reserved[2]);
      if ( inserted )
      {
        if ( !v8 )
          goto LABEL_225;
        goto LABEL_220;
      }
    }
    if ( LOBYTE(a2[4].ft) == 1 )
    {
      inserted = WmiRequestHandlerAdd::InsertDataForNode(
                   v6,
                   L"InteractiveLogon_MessageTextForUsersAttemptingToLogOn",
                   &a2[3].reserved[3]);
      if ( inserted )
      {
        if ( !v8 )
          goto LABEL_225;
        goto LABEL_220;
      }
    }
    if ( LOBYTE(a2[4].serverName) == 1 )
    {
      inserted = WmiRequestHandlerAdd::InsertDataForNode(
                   v6,
                   L"InteractiveLogon_MessageTitleForUsersAttemptingToLogOn",
                   &a2[4].classDecl);
      if ( inserted )
      {
        if ( !v8 )
          goto LABEL_225;
        goto LABEL_220;
      }
    }
    if ( LOBYTE(a2[4].reserved[0]) == 1 )
    {
      inserted = WmiRequestHandlerAdd::InsertDataForNode(
                   v6,
                   L"InteractiveLogon_SmartCardRemovalBehavior",
                   &a2[4].nameSpace);
      if ( inserted )
      {
        if ( !v8 )
          goto LABEL_225;
        goto LABEL_220;
      }
    }
    if ( BYTE4(a2[4].reserved[1]) == 1 )
    {
      inserted = WmiRequestHandlerAdd::InsertDataForNode(
                   v6,
                   L"MicrosoftNetworkClient_DigitallySignCommunicationsAlways",
                   &a2[4].reserved[1]);
      if ( inserted )
      {
        if ( !v8 )
          goto LABEL_225;
        goto LABEL_220;
      }
    }
    if ( BYTE4(a2[4].reserved[2]) == 1 )
    {
      inserted = WmiRequestHandlerAdd::InsertDataForNode(
                   v6,
                   L"MicrosoftNetworkClient_DigitallySignCommunicationsIfServerAgrees",
                   &a2[4].reserved[2]);
      if ( inserted )
      {
        if ( !v8 )
          goto LABEL_225;
        goto LABEL_220;
      }
    }
    if ( BYTE4(a2[4].reserved[3]) == 1 )
    {
      inserted = WmiRequestHandlerAdd::InsertDataForNode(
                   v6,
                   L"MicrosoftNetworkClient_SendUnencryptedPasswordToThirdPartySMBServers",
                   &a2[4].reserved[3]);
      if ( inserted )
      {
        if ( !v8 )
          goto LABEL_225;
        goto LABEL_220;
      }
    }
    if ( BYTE4(a2[5].ft) == 1 )
    {
      inserted = WmiRequestHandlerAdd::InsertDataForNode(
                   v6,
                   L"MicrosoftNetworkServer_DigitallySignCommunicationsAlways",
                   &a2[5]);
      if ( inserted )
      {
        if ( !v8 )
          goto LABEL_225;
        goto LABEL_220;
      }
    }
    if ( BYTE4(a2[5].classDecl) == 1 )
    {
      inserted = WmiRequestHandlerAdd::InsertDataForNode(
                   v6,
                   L"MicrosoftNetworkServer_DigitallySignCommunicationsIfClientAgrees",
                   &a2[5].classDecl);
      if ( inserted )
      {
        if ( !v8 )
          goto LABEL_225;
        goto LABEL_220;
      }
    }
    if ( BYTE4(a2[5].serverName) == 1 )
    {
      inserted = WmiRequestHandlerAdd::InsertDataForNode(
                   v6,
                   L"NetworkAccess_DoNotAllowAnonymousEnumerationOfSAMAccounts",
                   &a2[5].serverName);
      if ( inserted )
      {
        if ( !v8 )
          goto LABEL_225;
        goto LABEL_220;
      }
    }
    if ( BYTE4(a2[5].nameSpace) == 1 )
    {
      inserted = WmiRequestHandlerAdd::InsertDataForNode(
                   v6,
                   L"NetworkAccess_DoNotAllowAnonymousEnumerationOfSamAccountsAndShares",
                   &a2[5].nameSpace);
      if ( inserted )
      {
        if ( !v8 )
          goto LABEL_225;
        goto LABEL_220;
      }
    }
    if ( BYTE4(a2[5].reserved[0]) == 1 )
    {
      inserted = WmiRequestHandlerAdd::InsertDataForNode(
                   v6,
                   L"NetworkAccess_RestrictAnonymousAccessToNamedPipesAndShares",
                   a2[5].reserved);
      if ( inserted )
      {
        if ( !v8 )
          goto LABEL_225;
        goto LABEL_220;
      }
    }
    if ( LOBYTE(a2[5].reserved[2]) == 1 )
    {
      inserted = WmiRequestHandlerAdd::InsertDataForNode(
                   v6,
                   L"NetworkAccess_RestrictClientsAllowedToMakeRemoteCallsToSAM",
                   &a2[5].reserved[1]);
      if ( inserted )
      {
        if ( !v8 )
          goto LABEL_225;
        goto LABEL_220;
      }
    }
    if ( BYTE4(a2[5].reserved[3]) == 1 )
    {
      inserted = WmiRequestHandlerAdd::InsertDataForNode(
                   v6,
                   L"NetworkSecurity_AllowLocalSystemToUseComputerIdentityForNTLM",
                   &a2[5].reserved[3]);
      if ( inserted )
      {
        if ( !v8 )
          goto LABEL_225;
        goto LABEL_220;
      }
    }
    if ( BYTE4(a2[6].ft) == 1 )
    {
      inserted = WmiRequestHandlerAdd::InsertDataForNode(
                   v6,
                   L"NetworkSecurity_AllowPKU2UAuthenticationRequests",
                   &a2[6]);
      if ( inserted )
      {
        if ( !v8 )
          goto LABEL_225;
        goto LABEL_220;
      }
    }
    if ( BYTE4(a2[6].classDecl) == 1 )
    {
      inserted = WmiRequestHandlerAdd::InsertDataForNode(
                   v6,
                   L"NetworkSecurity_DoNotStoreLANManagerHashValueOnNextPasswordChange",
                   &a2[6].classDecl);
      if ( inserted )
      {
        if ( !v8 )
          goto LABEL_225;
        goto LABEL_220;
      }
    }
    if ( BYTE4(a2[6].serverName) == 1 )
    {
      inserted = WmiRequestHandlerAdd::InsertDataForNode(
                   v6,
                   L"NetworkSecurity_LANManagerAuthenticationLevel",
                   &a2[6].serverName);
      if ( inserted )
      {
        if ( !v8 )
          goto LABEL_225;
        goto LABEL_220;
      }
    }
    if ( BYTE4(a2[6].nameSpace) == 1 )
    {
      inserted = WmiRequestHandlerAdd::InsertDataForNode(
                   v6,
                   L"NetworkSecurity_MinimumSessionSecurityForNTLMSSPBasedClients",
                   &a2[6].nameSpace);
      if ( inserted )
      {
        if ( !v8 )
          goto LABEL_225;
        goto LABEL_220;
      }
    }
    if ( BYTE4(a2[6].reserved[0]) == 1 )
    {
      inserted = WmiRequestHandlerAdd::InsertDataForNode(
                   v6,
                   L"NetworkSecurity_MinimumSessionSecurityForNTLMSSPBasedServers",
                   a2[6].reserved);
      if ( inserted )
      {
        if ( !v8 )
          goto LABEL_225;
        goto LABEL_220;
      }
    }
    if ( LOBYTE(a2[6].reserved[2]) == 1 )
    {
      inserted = WmiRequestHandlerAdd::InsertDataForNode(
                   v6,
                   L"NetworkSecurity_RestrictNTLM_AddRemoteServerExceptionsForNTLMAuthentication",
                   &a2[6].reserved[1]);
      if ( inserted )
      {
        if ( !v8 )
          goto LABEL_225;
        goto LABEL_220;
      }
    }
    if ( BYTE4(a2[6].reserved[3]) == 1 )
    {
      inserted = WmiRequestHandlerAdd::InsertDataForNode(
                   v6,
                   L"NetworkSecurity_RestrictNTLM_AuditIncomingNTLMTraffic",
                   &a2[6].reserved[3]);
      if ( inserted )
      {
        if ( !v8 )
          goto LABEL_225;
        goto LABEL_220;
      }
    }
    if ( BYTE4(a2[7].ft) == 1 )
    {
      inserted = WmiRequestHandlerAdd::InsertDataForNode(
                   v6,
                   L"NetworkSecurity_RestrictNTLM_IncomingNTLMTraffic",
                   &a2[7]);
      if ( inserted )
      {
        if ( !v8 )
          goto LABEL_225;
        goto LABEL_220;
      }
    }
    if ( BYTE4(a2[7].classDecl) == 1 )
    {
      inserted = WmiRequestHandlerAdd::InsertDataForNode(
                   v6,
                   L"NetworkSecurity_RestrictNTLM_OutgoingNTLMTrafficToRemoteServers",
                   &a2[7].classDecl);
      if ( inserted )
      {
        if ( !v8 )
          goto LABEL_225;
        goto LABEL_220;
      }
    }
    if ( BYTE4(a2[7].serverName) == 1 )
    {
      inserted = WmiRequestHandlerAdd::InsertDataForNode(
                   v6,
                   L"Shutdown_AllowSystemToBeShutDownWithoutHavingToLogOn",
                   &a2[7].serverName);
      if ( inserted )
      {
        if ( !v8 )
          goto LABEL_225;
        goto LABEL_220;
      }
    }
    if ( BYTE4(a2[7].nameSpace) == 1 )
    {
      inserted = WmiRequestHandlerAdd::InsertDataForNode(v6, L"Shutdown_ClearVirtualMemoryPageFile", &a2[7].nameSpace);
      if ( inserted )
      {
        if ( !v8 )
          goto LABEL_225;
        goto LABEL_220;
      }
    }
    if ( BYTE4(a2[7].reserved[0]) == 1 )
    {
      inserted = WmiRequestHandlerAdd::InsertDataForNode(
                   v6,
                   L"UserAccountControl_AllowUIAccessApplicationsToPromptForElevation",
                   a2[7].reserved);
      if ( inserted )
      {
        if ( !v8 )
          goto LABEL_225;
        goto LABEL_220;
      }
    }
    if ( BYTE4(a2[7].reserved[1]) == 1 )
    {
      inserted = WmiRequestHandlerAdd::InsertDataForNode(
                   v6,
                   L"UserAccountControl_BehaviorOfTheElevationPromptForAdministrators",
                   &a2[7].reserved[1]);
      if ( inserted )
      {
        if ( !v8 )
          goto LABEL_225;
        goto LABEL_220;
      }
    }
    if ( BYTE4(a2[7].reserved[2]) == 1 )
    {
      inserted = WmiRequestHandlerAdd::InsertDataForNode(
                   v6,
                   L"UserAccountControl_BehaviorOfTheElevationPromptForStandardUsers",
                   &a2[7].reserved[2]);
      if ( inserted )
      {
        if ( !v8 )
          goto LABEL_225;
        goto LABEL_220;
      }
    }
    if ( BYTE4(a2[7].reserved[3]) == 1 )
    {
      inserted = WmiRequestHandlerAdd::InsertDataForNode(
                   v6,
                   L"UserAccountControl_DetectApplicationInstallationsAndPromptForElevation",
                   &a2[7].reserved[3]);
      if ( inserted )
      {
        if ( !v8 )
          goto LABEL_225;
        goto LABEL_220;
      }
    }
    if ( BYTE4(a2[8].ft) == 1 )
    {
      inserted = WmiRequestHandlerAdd::InsertDataForNode(
                   v6,
                   L"UserAccountControl_OnlyElevateExecutableFilesThatAreSignedAndValidated",
                   &a2[8]);
      if ( inserted )
      {
        if ( !v8 )
          goto LABEL_225;
        goto LABEL_220;
      }
    }
    if ( BYTE4(a2[8].classDecl) == 1 )
    {
      inserted = WmiRequestHandlerAdd::InsertDataForNode(
                   v6,
                   L"UserAccountControl_OnlyElevateUIAccessApplicationsThatAreInstalledInSecureLocations",
                   &a2[8].classDecl);
      if ( inserted )
      {
        if ( !v8 )
          goto LABEL_225;
        goto LABEL_220;
      }
    }
    if ( BYTE4(a2[8].serverName) == 1 )
    {
      inserted = WmiRequestHandlerAdd::InsertDataForNode(
                   v6,
                   L"UserAccountControl_RunAllAdministratorsInAdminApprovalMode",
                   &a2[8].serverName);
      if ( inserted )
      {
        if ( !v8 )
          goto LABEL_225;
        goto LABEL_220;
      }
    }
    if ( BYTE4(a2[8].nameSpace) == 1 )
    {
      inserted = WmiRequestHandlerAdd::InsertDataForNode(
                   v6,
                   L"UserAccountControl_SwitchToTheSecureDesktopWhenPromptingForElevation",
                   &a2[8].nameSpace);
      if ( inserted )
      {
        if ( !v8 )
          goto LABEL_225;
        goto LABEL_220;
      }
    }
    if ( BYTE4(a2[8].reserved[0]) == 1 )
    {
      inserted = WmiRequestHandlerAdd::InsertDataForNode(v6, L"UserAccountControl_UseAdminApprovalMode", a2[8].reserved);
      if ( inserted )
      {
        if ( !v8 )
          goto LABEL_225;
        goto LABEL_220;
      }
    }
    if ( BYTE4(a2[8].reserved[1]) == 1 )
    {
      inserted = WmiRequestHandlerAdd::InsertDataForNode(
                   v6,
                   L"UserAccountControl_VirtualizeFileAndRegistryWriteFailuresToPerUserLocations",
                   &a2[8].reserved[1]);
      if ( inserted )
      {
        if ( !v8 )
          goto LABEL_225;
        goto LABEL_220;
      }
    }
    inserted = (*(unsigned int (__fastcall **)(WmiRequestHandler *))(*(_QWORD *)v6 + 16LL))(v6);
    if ( inserted )
    {
      if ( !v8 )
        goto LABEL_225;
      goto LABEL_220;
    }
    inserted = (*(unsigned int (__fastcall **)(WmiRequestHandler *))(*(_QWORD *)v6 + 8LL))(v6);
    if ( inserted )
    {
      if ( !v8 )
        goto LABEL_225;
      goto LABEL_220;
    }
    inserted = MI_Context_ConstructInstance(self, &MDM_Policy_Config01_LocalPoliciesSecurityOptions02_rtti, &instance);
    if ( inserted )
    {
      if ( !v8 )
        goto LABEL_225;
      goto LABEL_220;
    }
    v9 = 1;
    MDM_WindowsLicensing_Subscriptions01_01_Set_InstanceID(&instance, a2[1].ft);
    MDM_WindowsLicensing_Subscriptions01_01_Set_ParentID(&instance, a2[1].serverName);
    MI_Instance_Destruct((MI_Instance *)self);
    if ( v8 )
      (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
    MI_Instance_Destruct(&instance);
  }
LABEL_225:
  TelemetryEventWriter::WriteEnd((TelemetryEventWriter *)v10, "CreateInstanceEnd", inserted);
  v12 = 2;
  if ( (unsigned int)dword_180380B68 > 5 && (unsigned __int8)tlgKeywordOn(&dword_180380B68, 0x200000000000LL) )
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(
      &dword_180380B68,
      word_18034EB5A,
      v14,
      0);
  _TlgActivityBase<TraceLoggingActivity<&_tlgProvider_t const * const g_hTraceLoggingProvider,35184372088832,5,_TlgReflectorTag_Param0IsHProvider>,35184372088832,5>::~_TlgActivityBase<TraceLoggingActivity<&_tlgProvider_t const * const g_hTraceLoggingProvider,35184372088832,5,_TlgReflectorTag_Param0IsHProvider>,35184372088832,5>(&v12);
  return (unsigned int)inserted;
}

```

## disassembly

```asm
0x1800accbc  mov     [rsp+arg_10], rsi
0x1800accc1  mov     [rsp+arg_18], rdi
0x1800accc6  push    r12
0x1800accc8  push    r14
0x1800accca  push    r15
0x1800acccc  sub     rsp, 2F0h
0x1800accd3  mov     rax, cs:__security_cookie
0x1800accda  xor     rax, rsp
0x1800accdd  mov     [rsp+308h+var_28], rax
0x1800acce5  mov     rsi, rdx
0x1800acce8  mov     r15, rcx
0x1800acceb  xor     edx, edx; Val
0x1800acced  mov     r8d, 230h; Size
0x1800accf3  lea     rcx, [rsp+308h+instance]; void *
0x1800accfb  call    memset_0
0x1800acd00  mov     [rsp+308h+var_288], 0
0x1800acd0b  mov     [rsp+308h+var_284], 0
0x1800acd13  lea     rax, ??_7TelemetryEventWriter@@6B@; const TelemetryEventWriter::`vftable'
0x1800acd1a  mov     [rsp+308h+var_2B8], rax
0x1800acd1f  lea     rax, [rsp+308h+var_288]
0x1800acd27  mov     [rsp+308h+var_2B0], rax
0x1800acd2c  lea     rax, aMdmPolicyConfi_55; "MDM_Policy_Config01_LocalPoliciesSecuri"...
0x1800acd33  mov     [rsp+308h+var_2A8], rax
0x1800acd38  lea     rcx, [rsp+308h+var_288]
0x1800acd40  call    ?zInternalStart@?$_TlgActivityBase@V?$TraceLoggingActivity@$1?g_hTraceLoggingProvider@@3QEBU_tlgProvider_t@@EB$0CAAAAAAAAAAA@$04U_TlgReflectorTag_Param0IsHProvider@@@@$0CAAAAAAAAAAA@$04@@QEAAXXZ; _TlgActivityBase<TraceLoggingActivity<&_tlgProvider_t const * const g_hTraceLoggingProvider,35184372088832,5,_TlgReflectorTag_Param0IsHProvider>,35184372088832,5>::zInternalStart(void)
0x1800acd45  mov     eax, cs:dword_180380B68
0x1800acd4b  cmp     eax, 5
0x1800acd4e  jbe     short loc_1800ACDC4
0x1800acd50  mov     rdx, 200000000000h
0x1800acd5a  lea     rcx, dword_180380B68
0x1800acd61  call    _tlgKeywordOn
0x1800acd66  test    al, al
0x1800acd68  jz      short loc_1800ACDC4
0x1800acd6a  cmp     [rsp+308h+var_284], 0
0x1800acd72  jz      short loc_1800ACDA6
0x1800acd74  cmp     [rsp+308h+var_270], 0
0x1800acd7c  jnz     short loc_1800ACD9C
0x1800acd7e  cmp     [rsp+308h+var_26C], 0
0x1800acd86  jnz     short loc_1800ACD9C
0x1800acd88  cmp     [rsp+308h+var_268], 0
0x1800acd90  jnz     short loc_1800ACD9C
0x1800acd92  cmp     [rsp+308h+var_264], 0
0x1800acd9a  jz      short loc_1800ACDA6
0x1800acd9c  lea     r9, [rsp+308h+var_270]
0x1800acda4  jmp     short loc_1800ACDA9
0x1800acda6  xor     r9d, r9d
0x1800acda9  lea     r8, [rsp+308h+var_280]
0x1800acdb1  lea     rdx, byte_18033E02D
0x1800acdb8  lea     rcx, dword_180380B68
0x1800acdbf  call    ??$Write@$$V@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *)
0x1800acdc4  cmp     byte ptr [rsi+48h], 0
0x1800acdc8  jz      loc_1800ADBBA
0x1800acdce  mov     [rsp+308h+var_2C0], 0
0x1800acdd3  cmp     byte ptr [rsi+58h], 0
0x1800acdd7  jz      loc_1800ADBBA
0x1800acddd  mov     r9, [rsi+40h]; unsigned __int16 *
0x1800acde1  mov     r8, [rsi+50h]; unsigned __int16 *
0x1800acde5  lea     rdx, aCreateinstance_0; "CreateInstanceStart"
0x1800acdec  lea     rcx, [rsp+308h+var_2B8]; this
0x1800acdf1  call    ?WriteStart@TelemetryEventWriter@@QEAAXPEBDPEBG1@Z; TelemetryEventWriter::WriteStart(char const *,ushort const *,ushort const *)
0x1800acdf6  nop
0x1800acdf7  mov     [rsp+308h+var_2C8], 0
0x1800ace00  lea     rax, [rsp+308h+var_2C8]
0x1800ace05  mov     [rsp+308h+var_2D8], rax
0x1800ace0a  mov     [rsp+308h+var_2E0], 4
0x1800ace12  mov     [rsp+308h+var_2E8], 33h ; '3'
0x1800ace1a  lea     r9, ?MDM_Policy_Config01_LocalPoliciesSecurityOptions02_NodeList@@3PAUWmiNodeInfo@@A; WmiNodeInfo near * MDM_Policy_Config01_LocalPoliciesSecurityOptions02_NodeList
0x1800ace21  mov     r8, [rsi+40h]
0x1800ace25  mov     rdx, [rsi+50h]
0x1800ace29  mov     rcx, r15
0x1800ace2c  call    ?CreateRequestHandlerInstance@@YA?AW4_MI_Result@@PEAU_MI_Context@@PEBG1PEAUWmiNodeInfo@@KW4RequestType@@AEAPEAVWmiRequestHandler@@@Z; CreateRequestHandlerInstance(_MI_Context *,ushort const *,ushort const *,WmiNodeInfo *,ulong,RequestType,WmiRequestHandler * &)
0x1800ace31  mov     edi, eax
0x1800ace33  test    eax, eax
0x1800ace35  jz      short loc_1800ACE3C
0x1800ace37  jmp     loc_1800ADBBF
0x1800ace3c  lea     rax, [rsp+308h+var_2C8]
0x1800ace41  mov     [rsp+308h+var_298], rax
0x1800ace46  mov     r12d, 1
0x1800ace4c  mov     [rsp+308h+var_290], r12b
0x1800ace51  mov     r14, [rsp+308h+var_2C8]
0x1800ace56  test    r14, r14
0x1800ace59  jnz     short loc_1800ACE63
0x1800ace5b  mov     edi, r12d
0x1800ace5e  jmp     loc_1800ADBBF
0x1800ace63  mov     r9d, 33h ; '3'; unsigned int
0x1800ace69  lea     r8, ?MDM_Policy_Config01_LocalPoliciesSecurityOptions02_NodeList@@3PAUWmiNodeInfo@@A; struct WmiNodeInfo *
0x1800ace70  mov     rdx, rsi; struct _MI_Instance *
0x1800ace73  mov     rcx, r14; this
0x1800ace76  call    ?SetRequestMIInstance@WmiRequestHandler@@QEAA?AW4_MI_Result@@PEBU_MI_Instance@@PEAUWmiNodeInfo@@K@Z; WmiRequestHandler::SetRequestMIInstance(_MI_Instance const *,WmiNodeInfo *,ulong)
0x1800ace7b  lea     r8, [rsi+60h]; void *
0x1800ace7f  cmp     [r8+4], r12b
0x1800ace83  jnz     short loc_1800ACEB8
0x1800ace85  lea     rdx, aAccountsBlockm; "Accounts_BlockMicrosoftAccounts"
0x1800ace8c  mov     rcx, r14; this
0x1800ace8f  call    ?InsertDataForNode@WmiRequestHandlerAdd@@QEAA?AW4_MI_Result@@PEBGPEAX@Z; WmiRequestHandlerAdd::InsertDataForNode(ushort const *,void *)
0x1800ace94  mov     edi, eax
0x1800ace96  test    eax, eax
0x1800ace98  jz      short loc_1800ACEB8
0x1800ace9a  mov     rcx, [rsp+308h+var_2C8]
0x1800ace9f  test    rcx, rcx
0x1800acea2  jz      short loc_1800ACEB3
0x1800acea4  mov     rax, [rcx]
0x1800acea7  mov     edx, r12d
0x1800aceaa  mov     rax, [rax]
0x1800acead  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800aceb2  nop
0x1800aceb3  jmp     loc_1800ADBBF
0x1800aceb8  lea     r8, [rsi+68h]; void *
0x1800acebc  cmp     [r8+4], r12b
0x1800acec0  jnz     short loc_1800ACEF5
0x1800acec2  lea     rdx, aAccountsEnable_0; "Accounts_EnableAdministratorAccountStat"...
0x1800acec9  mov     rcx, r14; this
0x1800acecc  call    ?InsertDataForNode@WmiRequestHandlerAdd@@QEAA?AW4_MI_Result@@PEBGPEAX@Z; WmiRequestHandlerAdd::InsertDataForNode(ushort const *,void *)
0x1800aced1  mov     edi, eax
0x1800aced3  test    eax, eax
0x1800aced5  jz      short loc_1800ACEF5
0x1800aced7  mov     rcx, [rsp+308h+var_2C8]
0x1800acedc  test    rcx, rcx
0x1800acedf  jz      short loc_1800ACEF0
0x1800acee1  mov     rax, [rcx]
0x1800acee4  mov     edx, r12d
0x1800acee7  mov     rax, [rax]
0x1800aceea  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800aceef  nop
0x1800acef0  jmp     loc_1800ADBBF
0x1800acef5  lea     r8, [rsi+70h]; void *
0x1800acef9  cmp     [r8+4], r12b
0x1800acefd  jnz     short loc_1800ACF32
0x1800aceff  lea     rdx, aAccountsEnable; "Accounts_EnableGuestAccountStatus"
0x1800acf06  mov     rcx, r14; this
0x1800acf09  call    ?InsertDataForNode@WmiRequestHandlerAdd@@QEAA?AW4_MI_Result@@PEBGPEAX@Z; WmiRequestHandlerAdd::InsertDataForNode(ushort const *,void *)
0x1800acf0e  mov     edi, eax
0x1800acf10  test    eax, eax
0x1800acf12  jz      short loc_1800ACF32
0x1800acf14  mov     rcx, [rsp+308h+var_2C8]
0x1800acf19  test    rcx, rcx
0x1800acf1c  jz      short loc_1800ACF2D
0x1800acf1e  mov     rax, [rcx]
0x1800acf21  mov     edx, r12d
0x1800acf24  mov     rax, [rax]
0x1800acf27  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800acf2c  nop
0x1800acf2d  jmp     loc_1800ADBBF
0x1800acf32  lea     r8, [rsi+78h]; void *
0x1800acf36  cmp     [r8+4], r12b
0x1800acf3a  jnz     short loc_1800ACF6F
0x1800acf3c  lea     rdx, aAccountsLimitl; "Accounts_LimitLocalAccountUseOfBlankPas"...
0x1800acf43  mov     rcx, r14; this
0x1800acf46  call    ?InsertDataForNode@WmiRequestHandlerAdd@@QEAA?AW4_MI_Result@@PEBGPEAX@Z; WmiRequestHandlerAdd::InsertDataForNode(ushort const *,void *)
0x1800acf4b  mov     edi, eax
0x1800acf4d  test    eax, eax
0x1800acf4f  jz      short loc_1800ACF6F
0x1800acf51  mov     rcx, [rsp+308h+var_2C8]
0x1800acf56  test    rcx, rcx
0x1800acf59  jz      short loc_1800ACF6A
0x1800acf5b  mov     rax, [rcx]
0x1800acf5e  mov     edx, r12d
0x1800acf61  mov     rax, [rax]
0x1800acf64  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800acf69  nop
0x1800acf6a  jmp     loc_1800ADBBF
0x1800acf6f  lea     r8, [rsi+80h]; void *
0x1800acf76  cmp     [r8+8], r12b
0x1800acf7a  jnz     short loc_1800ACFAF
0x1800acf7c  lea     rdx, aAccountsRename_0; "Accounts_RenameAdministratorAccount"
0x1800acf83  mov     rcx, r14; this
0x1800acf86  call    ?InsertDataForNode@WmiRequestHandlerAdd@@QEAA?AW4_MI_Result@@PEBGPEAX@Z; WmiRequestHandlerAdd::InsertDataForNode(ushort const *,void *)
0x1800acf8b  mov     edi, eax
0x1800acf8d  test    eax, eax
0x1800acf8f  jz      short loc_1800ACFAF
0x1800acf91  mov     rcx, [rsp+308h+var_2C8]
0x1800acf96  test    rcx, rcx
0x1800acf99  jz      short loc_1800ACFAA
0x1800acf9b  mov     rax, [rcx]
0x1800acf9e  mov     edx, r12d
0x1800acfa1  mov     rax, [rax]
0x1800acfa4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800acfa9  nop
0x1800acfaa  jmp     loc_1800ADBBF
0x1800acfaf  lea     r8, [rsi+90h]; void *
0x1800acfb6  cmp     [r8+8], r12b
0x1800acfba  jnz     short loc_1800ACFEF
0x1800acfbc  lea     rdx, aAccountsRename; "Accounts_RenameGuestAccount"
0x1800acfc3  mov     rcx, r14; this
0x1800acfc6  call    ?InsertDataForNode@WmiRequestHandlerAdd@@QEAA?AW4_MI_Result@@PEBGPEAX@Z; WmiRequestHandlerAdd::InsertDataForNode(ushort const *,void *)
0x1800acfcb  mov     edi, eax
0x1800acfcd  test    eax, eax
0x1800acfcf  jz      short loc_1800ACFEF
0x1800acfd1  mov     rcx, [rsp+308h+var_2C8]
0x1800acfd6  test    rcx, rcx
0x1800acfd9  jz      short loc_1800ACFEA
0x1800acfdb  mov     rax, [rcx]
0x1800acfde  mov     edx, r12d
0x1800acfe1  mov     rax, [rax]
0x1800acfe4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800acfe9  nop
0x1800acfea  jmp     loc_1800ADBBF
0x1800acfef  lea     r8, [rsi+0A0h]; void *
0x1800acff6  cmp     [r8+8], r12b
0x1800acffa  jnz     short loc_1800AD02F
0x1800acffc  lea     rdx, aDevicesAllowed; "Devices_AllowedToFormatAndEjectRemovabl"...
0x1800ad003  mov     rcx, r14; this
0x1800ad006  call    ?InsertDataForNode@WmiRequestHandlerAdd@@QEAA?AW4_MI_Result@@PEBGPEAX@Z; WmiRequestHandlerAdd::InsertDataForNode(ushort const *,void *)
0x1800ad00b  mov     edi, eax
0x1800ad00d  test    eax, eax
0x1800ad00f  jz      short loc_1800AD02F
0x1800ad011  mov     rcx, [rsp+308h+var_2C8]
0x1800ad016  test    rcx, rcx
0x1800ad019  jz      short loc_1800AD02A
0x1800ad01b  mov     rax, [rcx]
0x1800ad01e  mov     edx, r12d
0x1800ad021  mov     rax, [rax]
0x1800ad024  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ad029  nop
0x1800ad02a  jmp     loc_1800ADBBF
0x1800ad02f  lea     r8, [rsi+0B0h]; void *
0x1800ad036  cmp     [r8+4], r12b
0x1800ad03a  jnz     short loc_1800AD06F
0x1800ad03c  lea     rdx, aDevicesAllowun; "Devices_AllowUndockWithoutHavingToLogon"
0x1800ad043  mov     rcx, r14; this
0x1800ad046  call    ?InsertDataForNode@WmiRequestHandlerAdd@@QEAA?AW4_MI_Result@@PEBGPEAX@Z; WmiRequestHandlerAdd::InsertDataForNode(ushort const *,void *)
0x1800ad04b  mov     edi, eax
0x1800ad04d  test    eax, eax
0x1800ad04f  jz      short loc_1800AD06F
0x1800ad051  mov     rcx, [rsp+308h+var_2C8]
0x1800ad056  test    rcx, rcx
0x1800ad059  jz      short loc_1800AD06A
0x1800ad05b  mov     rax, [rcx]
0x1800ad05e  mov     edx, r12d
0x1800ad061  mov     rax, [rax]
0x1800ad064  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ad069  nop
0x1800ad06a  jmp     loc_1800ADBBF
0x1800ad06f  lea     r8, [rsi+0B8h]; void *
0x1800ad076  cmp     [r8+4], r12b
0x1800ad07a  jnz     short loc_1800AD0AF
0x1800ad07c  lea     rdx, aDevicesPrevent; "Devices_PreventUsersFromInstallingPrint"...
0x1800ad083  mov     rcx, r14; this
0x1800ad086  call    ?InsertDataForNode@WmiRequestHandlerAdd@@QEAA?AW4_MI_Result@@PEBGPEAX@Z; WmiRequestHandlerAdd::InsertDataForNode(ushort const *,void *)
0x1800ad08b  mov     edi, eax
0x1800ad08d  test    eax, eax
0x1800ad08f  jz      short loc_1800AD0AF
0x1800ad091  mov     rcx, [rsp+308h+var_2C8]
0x1800ad096  test    rcx, rcx
0x1800ad099  jz      short loc_1800AD0AA
0x1800ad09b  mov     rax, [rcx]
0x1800ad09e  mov     edx, r12d
0x1800ad0a1  mov     rax, [rax]
0x1800ad0a4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ad0a9  nop
0x1800ad0aa  jmp     loc_1800ADBBF
0x1800ad0af  lea     r8, [rsi+0C0h]; void *
0x1800ad0b6  cmp     [r8+8], r12b
0x1800ad0ba  jnz     short loc_1800AD0EF
0x1800ad0bc  lea     rdx, aDevicesRestric; "Devices_RestrictCDROMAccessToLocallyLog"...
0x1800ad0c3  mov     rcx, r14; this
0x1800ad0c6  call    ?InsertDataForNode@WmiRequestHandlerAdd@@QEAA?AW4_MI_Result@@PEBGPEAX@Z; WmiRequestHandlerAdd::InsertDataForNode(ushort const *,void *)
0x1800ad0cb  mov     edi, eax
0x1800ad0cd  test    eax, eax
0x1800ad0cf  jz      short loc_1800AD0EF
0x1800ad0d1  mov     rcx, [rsp+308h+var_2C8]
0x1800ad0d6  test    rcx, rcx
0x1800ad0d9  jz      short loc_1800AD0EA
0x1800ad0db  mov     rax, [rcx]
0x1800ad0de  mov     edx, r12d
0x1800ad0e1  mov     rax, [rax]
0x1800ad0e4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ad0e9  nop
0x1800ad0ea  jmp     loc_1800ADBBF
0x1800ad0ef  lea     r8, [rsi+0D0h]; void *
0x1800ad0f6  cmp     [r8+4], r12b
0x1800ad0fa  jnz     short loc_1800AD12F
0x1800ad0fc  lea     rdx, aInteractivelog; "InteractiveLogon_DisplayUserInformation"...
0x1800ad103  mov     rcx, r14; this
0x1800ad106  call    ?InsertDataForNode@WmiRequestHandlerAdd@@QEAA?AW4_MI_Result@@PEBGPEAX@Z; WmiRequestHandlerAdd::InsertDataForNode(ushort const *,void *)
0x1800ad10b  mov     edi, eax
0x1800ad10d  test    eax, eax
0x1800ad10f  jz      short loc_1800AD12F
0x1800ad111  mov     rcx, [rsp+308h+var_2C8]
0x1800ad116  test    rcx, rcx
0x1800ad119  jz      short loc_1800AD12A
0x1800ad11b  mov     rax, [rcx]
0x1800ad11e  mov     edx, r12d
0x1800ad121  mov     rax, [rax]
0x1800ad124  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ad129  nop
0x1800ad12a  jmp     loc_1800ADBBF
0x1800ad12f  lea     r8, [rsi+0D8h]; void *
0x1800ad136  cmp     [r8+4], r12b
0x1800ad13a  jnz     short loc_1800AD16F
0x1800ad13c  lea     rdx, aInteractivelog_5; "InteractiveLogon_DoNotDisplayLastSigned"...
0x1800ad143  mov     rcx, r14; this
0x1800ad146  call    ?InsertDataForNode@WmiRequestHandlerAdd@@QEAA?AW4_MI_Result@@PEBGPEAX@Z; WmiRequestHandlerAdd::InsertDataForNode(ushort const *,void *)
0x1800ad14b  mov     edi, eax
0x1800ad14d  test    eax, eax
0x1800ad14f  jz      short loc_1800AD16F
0x1800ad151  mov     rcx, [rsp+308h+var_2C8]
0x1800ad156  test    rcx, rcx
0x1800ad159  jz      short loc_1800AD16A
0x1800ad15b  mov     rax, [rcx]
  ... truncated ...
```
