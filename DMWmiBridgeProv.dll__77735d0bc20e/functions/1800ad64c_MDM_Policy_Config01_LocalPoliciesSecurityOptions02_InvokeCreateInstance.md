# MDM_Policy_Config01_LocalPoliciesSecurityOptions02_InvokeCreateInstance

- ea: `0x1800ad64c`
- end: `0x1800ae5eb`
- name: `MDM_Policy_Config01_LocalPoliciesSecurityOptions02_InvokeCreateInstance`
- size: `3999`
- prototype: `__int64 __fastcall(MI_Instance *self, struct _MI_Instance *)`
- caller_count: `1`
- callee_count: `17`
- tags: `registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x1800ad550`

## callees

- `0x180001008`
- `0x18000104c`
- `0x180003a5c`
- `0x180004f8c`
- `0x180004fc4`
- `0x18000871c`
- `0x180008764`
- `0x18000a280`
- `0x1800ad64c`
- `0x180240078`
- `0x180241ce0`
- `0x180243010`
- `0x180246310`
- `0x180246418`
- `0x18024d12e`
- `0x18024d160`
- `0x18024f010`

## string_xrefs

- `0x1800ad90c`: `Accounts_RenameAdministratorAccount`
- `0x1800ad94c`: `Accounts_RenameGuestAccount`
- `0x1800ada0c`: `Devices_PreventUsersFromInstallingPrinterDriversWhenConnectingToSharedPrinters`
- `0x1800ada4c`: `Devices_RestrictCDROMAccessToLocallyLoggedOnUserOnly`
- `0x1800adbcc`: `InteractiveLogon_MessageTextForUsersAttemptingToLogOn`
- `0x1800adc0c`: `InteractiveLogon_MessageTitleForUsersAttemptingToLogOn`
- `0x1800adc8c`: `MicrosoftNetworkClient_DigitallySignCommunicationsAlways`
- `0x1800adccc`: `MicrosoftNetworkClient_DigitallySignCommunicationsIfServerAgrees`
- `0x1800add4c`: `MicrosoftNetworkServer_DigitallySignCommunicationsAlways`
- `0x1800add8c`: `MicrosoftNetworkServer_DigitallySignCommunicationsIfClientAgrees`
- `0x1800addcc`: `NetworkAccess_DoNotAllowAnonymousEnumerationOfSAMAccounts`
- `0x1800ade0c`: `NetworkAccess_DoNotAllowAnonymousEnumerationOfSamAccountsAndShares`
- `0x1800ade4c`: `NetworkAccess_RestrictAnonymousAccessToNamedPipesAndShares`
- `0x1800ade8c`: `NetworkAccess_RestrictClientsAllowedToMakeRemoteCallsToSAM`
- `0x1800adecc`: `NetworkSecurity_AllowLocalSystemToUseComputerIdentityForNTLM`
- `0x1800adf0c`: `NetworkSecurity_AllowPKU2UAuthenticationRequests`
- `0x1800adf4c`: `NetworkSecurity_DoNotStoreLANManagerHashValueOnNextPasswordChange`
- `0x1800adf8c`: `NetworkSecurity_LANManagerAuthenticationLevel`
- `0x1800adfcc`: `NetworkSecurity_MinimumSessionSecurityForNTLMSSPBasedClients`
- `0x1800ae00c`: `NetworkSecurity_MinimumSessionSecurityForNTLMSSPBasedServers`
- `0x1800ae04c`: `NetworkSecurity_RestrictNTLM_AddRemoteServerExceptionsForNTLMAuthentication`
- `0x1800ae08c`: `NetworkSecurity_RestrictNTLM_AuditIncomingNTLMTraffic`
- `0x1800ae0cc`: `NetworkSecurity_RestrictNTLM_IncomingNTLMTraffic`
- `0x1800ae10c`: `NetworkSecurity_RestrictNTLM_OutgoingNTLMTrafficToRemoteServers`
- `0x1800ae1cc`: `UserAccountControl_AllowUIAccessApplicationsToPromptForElevation`
- `0x1800ae28c`: `UserAccountControl_DetectApplicationInstallationsAndPromptForElevation`
- `0x1800ae30c`: `UserAccountControl_OnlyElevateUIAccessApplicationsThatAreInstalledInSecureLocations`
- `0x1800ae40c`: `UserAccountControl_VirtualizeFileAndRegistryWriteFailuresToPerUserLocations`
- `0x1800ad775`: `CreateInstanceStart`
- `0x1800ae552`: `CreateInstanceEnd`
- `0x1800ad6bc`: `MDM_Policy_Config01_LocalPoliciesSecurityOptions02`

## pseudocode

```c
// Hidden C++ exception states: #wind=3 #try_helpers=1
__int64 __fastcall MDM_Policy_Config01_LocalPoliciesSecurityOptions02_InvokeCreateInstance(
        MI_Context *self,
        struct _MI_Instance *a2)
{
  _DWORD *v4; // r9
  unsigned int inserted; // edi
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
    inserted = 4;
    goto LABEL_225;
  }
  TelemetryEventWriter::WriteStart(
    (TelemetryEventWriter *)v10,
    "CreateInstanceStart",
    a2[1].serverName,
    (const unsigned __int16 *)a2[1].ft);
  v8 = 0;
  inserted = CreateRequestHandlerInstance(
               (__int64)self,
               (wchar_t *)a2[1].serverName,
               (const unsigned __int16 *)a2[1].ft,
               (struct WmiNodeInfo *)&MDM_Policy_Config01_LocalPoliciesSecurityOptions02_NodeList,
               0x33u,
               4,
               &v8);
  if ( !inserted )
  {
    v10[4] = &v8;
    v11 = 1;
    v6 = v8;
    if ( !v8 )
    {
      inserted = 1;
      goto LABEL_225;
    }
    WmiRequestHandler::SetRequestMIInstance(
      v8,
      a2,
      (struct WmiNodeInfo *)&MDM_Policy_Config01_LocalPoliciesSecurityOptions02_NodeList,
      0x33u);
    if ( BYTE4(a2[1].reserved[0]) == 1 )
    {
      inserted = WmiRequestHandlerAdd::InsertDataForNode(v6, L"Accounts_BlockMicrosoftAccounts", (LONG *)a2[1].reserved);
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
                   (LONG *)&a2[1].reserved[1]);
      if ( inserted )
      {
        if ( !v8 )
          goto LABEL_225;
        goto LABEL_220;
      }
    }
    if ( BYTE4(a2[1].reserved[2]) == 1 )
    {
      inserted = WmiRequestHandlerAdd::InsertDataForNode(
                   v6,
                   L"Accounts_EnableGuestAccountStatus",
                   (LONG *)&a2[1].reserved[2]);
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
                   (LONG *)&a2[1].reserved[3]);
      if ( inserted )
      {
        if ( !v8 )
          goto LABEL_225;
        goto LABEL_220;
      }
    }
    if ( LOBYTE(a2[2].classDecl) == 1 )
    {
      inserted = WmiRequestHandlerAdd::InsertDataForNode(v6, L"Accounts_RenameAdministratorAccount", (LONG *)&a2[2]);
      if ( inserted )
      {
        if ( !v8 )
          goto LABEL_225;
        goto LABEL_220;
      }
    }
    if ( LOBYTE(a2[2].nameSpace) == 1 )
    {
      inserted = WmiRequestHandlerAdd::InsertDataForNode(v6, L"Accounts_RenameGuestAccount", (LONG *)&a2[2].serverName);
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
                   (LONG *)a2[2].reserved);
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
                   (LONG *)&a2[2].reserved[2]);
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
                   (LONG *)&a2[2].reserved[3]);
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
                   (LONG *)&a2[3]);
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
                   (LONG *)&a2[3].serverName);
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
                   (LONG *)&a2[3].nameSpace);
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
                   (LONG *)a2[3].reserved);
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
                   (LONG *)&a2[3].reserved[1]);
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
                   (LONG *)&a2[3].reserved[2]);
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
                   (LONG *)&a2[3].reserved[3]);
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
                   (LONG *)&a2[4].classDecl);
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
                   (LONG *)&a2[4].nameSpace);
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
                   (LONG *)&a2[4].reserved[1]);
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
                   (LONG *)&a2[4].reserved[2]);
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
                   (LONG *)&a2[4].reserved[3]);
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
                   (LONG *)&a2[5]);
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
                   (LONG *)&a2[5].classDecl);
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
                   (LONG *)&a2[5].serverName);
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
                   (LONG *)&a2[5].nameSpace);
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
                   (LONG *)a2[5].reserved);
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
                   (LONG *)&a2[5].reserved[1]);
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
                   (LONG *)&a2[5].reserved[3]);
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
                   (LONG *)&a2[6]);
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
                   (LONG *)&a2[6].classDecl);
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
                   (LONG *)&a2[6].serverName);
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
                   (LONG *)&a2[6].nameSpace);
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
                   (LONG *)a2[6].reserved);
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
                   (LONG *)&a2[6].reserved[1]);
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
                   (LONG *)&a2[6].reserved[3]);
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
                   (LONG *)&a2[7]);
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
                   (LONG *)&a2[7].classDecl);
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
                   (LONG *)&a2[7].serverName);
      if ( inserted )
      {
        if ( !v8 )
          goto LABEL_225;
        goto LABEL_220;
      }
    }
    if ( BYTE4(a2[7].nameSpace) == 1 )
    {
      inserted = WmiRequestHandlerAdd::InsertDataForNode(
                   v6,
                   L"Shutdown_ClearVirtualMemoryPageFile",
                   (LONG *)&a2[7].nameSpace);
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
                   (LONG *)a2[7].reserved);
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
                   (LONG *)&a2[7].reserved[1]);
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
                   (LONG *)&a2[7].reserved[2]);
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
                   (LONG *)&a2[7].reserved[3]);
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
                   (LONG *)&a2[8]);
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
                   (LONG *)&a2[8].classDecl);
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
                   (LONG *)&a2[8].serverName);
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
                   (LONG *)&a2[8].nameSpace);
      if ( inserted )
      {
        if ( !v8 )
          goto LABEL_225;
        goto LABEL_220;
      }
    }
    if ( BYTE4(a2[8].reserved[0]) == 1 )
    {
      inserted = WmiRequestHandlerAdd::InsertDataForNode(
                   v6,
                   L"UserAccountControl_UseAdminApprovalMode",
                   (LONG *)a2[8].reserved);
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
                   (LONG *)&a2[8].reserved[1]);
      if ( inserted )
      {
        if ( !v8 )
          goto LABEL_225;
        goto LABEL_220;
      }
    }
    inserted = (*(__int64 (__fastcall **)(WmiRequestHandler *))(*(_QWORD *)v6 + 16LL))(v6);
    if ( inserted )
    {
      if ( !v8 )
        goto LABEL_225;
      goto LABEL_220;
    }
    inserted = (*(__int64 (__fastcall **)(WmiRequestHandler *))(*(_QWORD *)v6 + 8LL))(v6);
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
  return inserted;
}

```

## disassembly

```asm
0x1800ad64c  mov     [rsp+arg_10], rsi
0x1800ad651  mov     [rsp+arg_18], rdi
0x1800ad656  push    r12
0x1800ad658  push    r14
0x1800ad65a  push    r15
0x1800ad65c  sub     rsp, 2F0h
0x1800ad663  mov     rax, cs:__security_cookie
0x1800ad66a  xor     rax, rsp
0x1800ad66d  mov     [rsp+308h+var_28], rax
0x1800ad675  mov     rsi, rdx
0x1800ad678  mov     r15, rcx
0x1800ad67b  xor     edx, edx; Val
0x1800ad67d  mov     r8d, 230h; Size
0x1800ad683  lea     rcx, [rsp+308h+instance]; void *
0x1800ad68b  call    memset_0
0x1800ad690  mov     [rsp+308h+var_288], 0
0x1800ad69b  mov     [rsp+308h+var_284], 0
0x1800ad6a3  lea     rax, ??_7TelemetryEventWriter@@6B@; const TelemetryEventWriter::`vftable'
0x1800ad6aa  mov     [rsp+308h+var_2B8], rax
0x1800ad6af  lea     rax, [rsp+308h+var_288]
0x1800ad6b7  mov     [rsp+308h+var_2B0], rax
0x1800ad6bc  lea     rax, aMdmPolicyConfi_55; "MDM_Policy_Config01_LocalPoliciesSecuri"...
0x1800ad6c3  mov     [rsp+308h+var_2A8], rax
0x1800ad6c8  lea     rcx, [rsp+308h+var_288]
0x1800ad6d0  call    ?zInternalStart@?$_TlgActivityBase@V?$TraceLoggingActivity@$1?g_hTraceLoggingProvider@@3QEBU_tlgProvider_t@@EB$0CAAAAAAAAAAA@$04U_TlgReflectorTag_Param0IsHProvider@@@@$0CAAAAAAAAAAA@$04@@QEAAXXZ; _TlgActivityBase<TraceLoggingActivity<&_tlgProvider_t const * const g_hTraceLoggingProvider,35184372088832,5,_TlgReflectorTag_Param0IsHProvider>,35184372088832,5>::zInternalStart(void)
0x1800ad6d5  mov     eax, cs:dword_180380B68
0x1800ad6db  cmp     eax, 5
0x1800ad6de  jbe     short loc_1800AD754
0x1800ad6e0  mov     rdx, 200000000000h
0x1800ad6ea  lea     rcx, dword_180380B68
0x1800ad6f1  call    _tlgKeywordOn
0x1800ad6f6  test    al, al
0x1800ad6f8  jz      short loc_1800AD754
0x1800ad6fa  cmp     [rsp+308h+var_284], 0
0x1800ad702  jz      short loc_1800AD736
0x1800ad704  cmp     [rsp+308h+var_270], 0
0x1800ad70c  jnz     short loc_1800AD72C
0x1800ad70e  cmp     [rsp+308h+var_26C], 0
0x1800ad716  jnz     short loc_1800AD72C
0x1800ad718  cmp     [rsp+308h+var_268], 0
0x1800ad720  jnz     short loc_1800AD72C
0x1800ad722  cmp     [rsp+308h+var_264], 0
0x1800ad72a  jz      short loc_1800AD736
0x1800ad72c  lea     r9, [rsp+308h+var_270]
0x1800ad734  jmp     short loc_1800AD739
0x1800ad736  xor     r9d, r9d
0x1800ad739  lea     r8, [rsp+308h+var_280]
0x1800ad741  lea     rdx, byte_18033E02D
0x1800ad748  lea     rcx, dword_180380B68
0x1800ad74f  call    ??$Write@$$V@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *)
0x1800ad754  cmp     byte ptr [rsi+48h], 0
0x1800ad758  jz      loc_1800AE54A
0x1800ad75e  mov     [rsp+308h+var_2C0], 0
0x1800ad763  cmp     byte ptr [rsi+58h], 0
0x1800ad767  jz      loc_1800AE54A
0x1800ad76d  mov     r9, [rsi+40h]; unsigned __int16 *
0x1800ad771  mov     r8, [rsi+50h]; unsigned __int16 *
0x1800ad775  lea     rdx, aCreateinstance_0; "CreateInstanceStart"
0x1800ad77c  lea     rcx, [rsp+308h+var_2B8]; this
0x1800ad781  call    ?WriteStart@TelemetryEventWriter@@QEAAXPEBDPEBG1@Z; TelemetryEventWriter::WriteStart(char const *,ushort const *,ushort const *)
0x1800ad786  nop
0x1800ad787  mov     [rsp+308h+var_2C8], 0
0x1800ad790  lea     rax, [rsp+308h+var_2C8]
0x1800ad795  mov     [rsp+308h+var_2D8], rax
0x1800ad79a  mov     [rsp+308h+var_2E0], 4
0x1800ad7a2  mov     [rsp+308h+var_2E8], 33h ; '3'
0x1800ad7aa  lea     r9, ?MDM_Policy_Config01_LocalPoliciesSecurityOptions02_NodeList@@3PAUWmiNodeInfo@@A; WmiNodeInfo near * MDM_Policy_Config01_LocalPoliciesSecurityOptions02_NodeList
0x1800ad7b1  mov     r8, [rsi+40h]
0x1800ad7b5  mov     rdx, [rsi+50h]
0x1800ad7b9  mov     rcx, r15
0x1800ad7bc  call    ?CreateRequestHandlerInstance@@YA?AW4_MI_Result@@PEAU_MI_Context@@PEBG1PEAUWmiNodeInfo@@KW4RequestType@@AEAPEAVWmiRequestHandler@@@Z; CreateRequestHandlerInstance(_MI_Context *,ushort const *,ushort const *,WmiNodeInfo *,ulong,RequestType,WmiRequestHandler * &)
0x1800ad7c1  mov     edi, eax
0x1800ad7c3  test    eax, eax
0x1800ad7c5  jz      short loc_1800AD7CC
0x1800ad7c7  jmp     loc_1800AE54F
0x1800ad7cc  lea     rax, [rsp+308h+var_2C8]
0x1800ad7d1  mov     [rsp+308h+var_298], rax
0x1800ad7d6  mov     r12d, 1
0x1800ad7dc  mov     [rsp+308h+var_290], r12b
0x1800ad7e1  mov     r14, [rsp+308h+var_2C8]
0x1800ad7e6  test    r14, r14
0x1800ad7e9  jnz     short loc_1800AD7F3
0x1800ad7eb  mov     edi, r12d
0x1800ad7ee  jmp     loc_1800AE54F
0x1800ad7f3  mov     r9d, 33h ; '3'; unsigned int
0x1800ad7f9  lea     r8, ?MDM_Policy_Config01_LocalPoliciesSecurityOptions02_NodeList@@3PAUWmiNodeInfo@@A; struct WmiNodeInfo *
0x1800ad800  mov     rdx, rsi; struct _MI_Instance *
0x1800ad803  mov     rcx, r14; this
0x1800ad806  call    ?SetRequestMIInstance@WmiRequestHandler@@QEAA?AW4_MI_Result@@PEBU_MI_Instance@@PEAUWmiNodeInfo@@K@Z; WmiRequestHandler::SetRequestMIInstance(_MI_Instance const *,WmiNodeInfo *,ulong)
0x1800ad80b  lea     r8, [rsi+60h]; void *
0x1800ad80f  cmp     [r8+4], r12b
0x1800ad813  jnz     short loc_1800AD848
0x1800ad815  lea     rdx, aAccountsBlockm; "Accounts_BlockMicrosoftAccounts"
0x1800ad81c  mov     rcx, r14; this
0x1800ad81f  call    ?InsertDataForNode@WmiRequestHandlerAdd@@QEAA?AW4_MI_Result@@PEBGPEAX@Z; WmiRequestHandlerAdd::InsertDataForNode(ushort const *,void *)
0x1800ad824  mov     edi, eax
0x1800ad826  test    eax, eax
0x1800ad828  jz      short loc_1800AD848
0x1800ad82a  mov     rcx, [rsp+308h+var_2C8]
0x1800ad82f  test    rcx, rcx
0x1800ad832  jz      short loc_1800AD843
0x1800ad834  mov     rax, [rcx]
0x1800ad837  mov     edx, r12d
0x1800ad83a  mov     rax, [rax]
0x1800ad83d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ad842  nop
0x1800ad843  jmp     loc_1800AE54F
0x1800ad848  lea     r8, [rsi+68h]; void *
0x1800ad84c  cmp     [r8+4], r12b
0x1800ad850  jnz     short loc_1800AD885
0x1800ad852  lea     rdx, aAccountsEnable_0; "Accounts_EnableAdministratorAccountStat"...
0x1800ad859  mov     rcx, r14; this
0x1800ad85c  call    ?InsertDataForNode@WmiRequestHandlerAdd@@QEAA?AW4_MI_Result@@PEBGPEAX@Z; WmiRequestHandlerAdd::InsertDataForNode(ushort const *,void *)
0x1800ad861  mov     edi, eax
0x1800ad863  test    eax, eax
0x1800ad865  jz      short loc_1800AD885
0x1800ad867  mov     rcx, [rsp+308h+var_2C8]
0x1800ad86c  test    rcx, rcx
0x1800ad86f  jz      short loc_1800AD880
0x1800ad871  mov     rax, [rcx]
0x1800ad874  mov     edx, r12d
0x1800ad877  mov     rax, [rax]
0x1800ad87a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ad87f  nop
0x1800ad880  jmp     loc_1800AE54F
0x1800ad885  lea     r8, [rsi+70h]; void *
0x1800ad889  cmp     [r8+4], r12b
0x1800ad88d  jnz     short loc_1800AD8C2
0x1800ad88f  lea     rdx, aAccountsEnable; "Accounts_EnableGuestAccountStatus"
0x1800ad896  mov     rcx, r14; this
0x1800ad899  call    ?InsertDataForNode@WmiRequestHandlerAdd@@QEAA?AW4_MI_Result@@PEBGPEAX@Z; WmiRequestHandlerAdd::InsertDataForNode(ushort const *,void *)
0x1800ad89e  mov     edi, eax
0x1800ad8a0  test    eax, eax
0x1800ad8a2  jz      short loc_1800AD8C2
0x1800ad8a4  mov     rcx, [rsp+308h+var_2C8]
0x1800ad8a9  test    rcx, rcx
0x1800ad8ac  jz      short loc_1800AD8BD
0x1800ad8ae  mov     rax, [rcx]
0x1800ad8b1  mov     edx, r12d
0x1800ad8b4  mov     rax, [rax]
0x1800ad8b7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ad8bc  nop
0x1800ad8bd  jmp     loc_1800AE54F
0x1800ad8c2  lea     r8, [rsi+78h]; void *
0x1800ad8c6  cmp     [r8+4], r12b
0x1800ad8ca  jnz     short loc_1800AD8FF
0x1800ad8cc  lea     rdx, aAccountsLimitl; "Accounts_LimitLocalAccountUseOfBlankPas"...
0x1800ad8d3  mov     rcx, r14; this
0x1800ad8d6  call    ?InsertDataForNode@WmiRequestHandlerAdd@@QEAA?AW4_MI_Result@@PEBGPEAX@Z; WmiRequestHandlerAdd::InsertDataForNode(ushort const *,void *)
0x1800ad8db  mov     edi, eax
0x1800ad8dd  test    eax, eax
0x1800ad8df  jz      short loc_1800AD8FF
0x1800ad8e1  mov     rcx, [rsp+308h+var_2C8]
0x1800ad8e6  test    rcx, rcx
0x1800ad8e9  jz      short loc_1800AD8FA
0x1800ad8eb  mov     rax, [rcx]
0x1800ad8ee  mov     edx, r12d
0x1800ad8f1  mov     rax, [rax]
0x1800ad8f4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ad8f9  nop
0x1800ad8fa  jmp     loc_1800AE54F
0x1800ad8ff  lea     r8, [rsi+80h]; void *
0x1800ad906  cmp     [r8+8], r12b
0x1800ad90a  jnz     short loc_1800AD93F
0x1800ad90c  lea     rdx, aAccountsRename_0; "Accounts_RenameAdministratorAccount"
0x1800ad913  mov     rcx, r14; this
0x1800ad916  call    ?InsertDataForNode@WmiRequestHandlerAdd@@QEAA?AW4_MI_Result@@PEBGPEAX@Z; WmiRequestHandlerAdd::InsertDataForNode(ushort const *,void *)
0x1800ad91b  mov     edi, eax
0x1800ad91d  test    eax, eax
0x1800ad91f  jz      short loc_1800AD93F
0x1800ad921  mov     rcx, [rsp+308h+var_2C8]
0x1800ad926  test    rcx, rcx
0x1800ad929  jz      short loc_1800AD93A
0x1800ad92b  mov     rax, [rcx]
0x1800ad92e  mov     edx, r12d
0x1800ad931  mov     rax, [rax]
0x1800ad934  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ad939  nop
0x1800ad93a  jmp     loc_1800AE54F
0x1800ad93f  lea     r8, [rsi+90h]; void *
0x1800ad946  cmp     [r8+8], r12b
0x1800ad94a  jnz     short loc_1800AD97F
0x1800ad94c  lea     rdx, aAccountsRename; "Accounts_RenameGuestAccount"
0x1800ad953  mov     rcx, r14; this
0x1800ad956  call    ?InsertDataForNode@WmiRequestHandlerAdd@@QEAA?AW4_MI_Result@@PEBGPEAX@Z; WmiRequestHandlerAdd::InsertDataForNode(ushort const *,void *)
0x1800ad95b  mov     edi, eax
0x1800ad95d  test    eax, eax
0x1800ad95f  jz      short loc_1800AD97F
0x1800ad961  mov     rcx, [rsp+308h+var_2C8]
0x1800ad966  test    rcx, rcx
0x1800ad969  jz      short loc_1800AD97A
0x1800ad96b  mov     rax, [rcx]
0x1800ad96e  mov     edx, r12d
0x1800ad971  mov     rax, [rax]
0x1800ad974  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ad979  nop
0x1800ad97a  jmp     loc_1800AE54F
0x1800ad97f  lea     r8, [rsi+0A0h]; void *
0x1800ad986  cmp     [r8+8], r12b
0x1800ad98a  jnz     short loc_1800AD9BF
0x1800ad98c  lea     rdx, aDevicesAllowed; "Devices_AllowedToFormatAndEjectRemovabl"...
0x1800ad993  mov     rcx, r14; this
0x1800ad996  call    ?InsertDataForNode@WmiRequestHandlerAdd@@QEAA?AW4_MI_Result@@PEBGPEAX@Z; WmiRequestHandlerAdd::InsertDataForNode(ushort const *,void *)
0x1800ad99b  mov     edi, eax
0x1800ad99d  test    eax, eax
0x1800ad99f  jz      short loc_1800AD9BF
0x1800ad9a1  mov     rcx, [rsp+308h+var_2C8]
0x1800ad9a6  test    rcx, rcx
0x1800ad9a9  jz      short loc_1800AD9BA
0x1800ad9ab  mov     rax, [rcx]
0x1800ad9ae  mov     edx, r12d
0x1800ad9b1  mov     rax, [rax]
0x1800ad9b4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ad9b9  nop
0x1800ad9ba  jmp     loc_1800AE54F
0x1800ad9bf  lea     r8, [rsi+0B0h]; void *
0x1800ad9c6  cmp     [r8+4], r12b
0x1800ad9ca  jnz     short loc_1800AD9FF
0x1800ad9cc  lea     rdx, aDevicesAllowun; "Devices_AllowUndockWithoutHavingToLogon"
0x1800ad9d3  mov     rcx, r14; this
0x1800ad9d6  call    ?InsertDataForNode@WmiRequestHandlerAdd@@QEAA?AW4_MI_Result@@PEBGPEAX@Z; WmiRequestHandlerAdd::InsertDataForNode(ushort const *,void *)
0x1800ad9db  mov     edi, eax
0x1800ad9dd  test    eax, eax
0x1800ad9df  jz      short loc_1800AD9FF
0x1800ad9e1  mov     rcx, [rsp+308h+var_2C8]
0x1800ad9e6  test    rcx, rcx
0x1800ad9e9  jz      short loc_1800AD9FA
0x1800ad9eb  mov     rax, [rcx]
0x1800ad9ee  mov     edx, r12d
0x1800ad9f1  mov     rax, [rax]
0x1800ad9f4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ad9f9  nop
0x1800ad9fa  jmp     loc_1800AE54F
0x1800ad9ff  lea     r8, [rsi+0B8h]; void *
0x1800ada06  cmp     [r8+4], r12b
0x1800ada0a  jnz     short loc_1800ADA3F
0x1800ada0c  lea     rdx, aDevicesPrevent; "Devices_PreventUsersFromInstallingPrint"...
0x1800ada13  mov     rcx, r14; this
0x1800ada16  call    ?InsertDataForNode@WmiRequestHandlerAdd@@QEAA?AW4_MI_Result@@PEBGPEAX@Z; WmiRequestHandlerAdd::InsertDataForNode(ushort const *,void *)
0x1800ada1b  mov     edi, eax
0x1800ada1d  test    eax, eax
0x1800ada1f  jz      short loc_1800ADA3F
0x1800ada21  mov     rcx, [rsp+308h+var_2C8]
0x1800ada26  test    rcx, rcx
0x1800ada29  jz      short loc_1800ADA3A
0x1800ada2b  mov     rax, [rcx]
0x1800ada2e  mov     edx, r12d
0x1800ada31  mov     rax, [rax]
0x1800ada34  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ada39  nop
0x1800ada3a  jmp     loc_1800AE54F
0x1800ada3f  lea     r8, [rsi+0C0h]; void *
0x1800ada46  cmp     [r8+8], r12b
0x1800ada4a  jnz     short loc_1800ADA7F
0x1800ada4c  lea     rdx, aDevicesRestric; "Devices_RestrictCDROMAccessToLocallyLog"...
0x1800ada53  mov     rcx, r14; this
0x1800ada56  call    ?InsertDataForNode@WmiRequestHandlerAdd@@QEAA?AW4_MI_Result@@PEBGPEAX@Z; WmiRequestHandlerAdd::InsertDataForNode(ushort const *,void *)
0x1800ada5b  mov     edi, eax
0x1800ada5d  test    eax, eax
0x1800ada5f  jz      short loc_1800ADA7F
0x1800ada61  mov     rcx, [rsp+308h+var_2C8]
0x1800ada66  test    rcx, rcx
0x1800ada69  jz      short loc_1800ADA7A
0x1800ada6b  mov     rax, [rcx]
0x1800ada6e  mov     edx, r12d
0x1800ada71  mov     rax, [rax]
0x1800ada74  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ada79  nop
0x1800ada7a  jmp     loc_1800AE54F
0x1800ada7f  lea     r8, [rsi+0D0h]; void *
0x1800ada86  cmp     [r8+4], r12b
0x1800ada8a  jnz     short loc_1800ADABF
0x1800ada8c  lea     rdx, aInteractivelog; "InteractiveLogon_DisplayUserInformation"...
0x1800ada93  mov     rcx, r14; this
0x1800ada96  call    ?InsertDataForNode@WmiRequestHandlerAdd@@QEAA?AW4_MI_Result@@PEBGPEAX@Z; WmiRequestHandlerAdd::InsertDataForNode(ushort const *,void *)
0x1800ada9b  mov     edi, eax
0x1800ada9d  test    eax, eax
0x1800ada9f  jz      short loc_1800ADABF
0x1800adaa1  mov     rcx, [rsp+308h+var_2C8]
0x1800adaa6  test    rcx, rcx
0x1800adaa9  jz      short loc_1800ADABA
0x1800adaab  mov     rax, [rcx]
0x1800adaae  mov     edx, r12d
0x1800adab1  mov     rax, [rax]
0x1800adab4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800adab9  nop
0x1800adaba  jmp     loc_1800AE54F
0x1800adabf  lea     r8, [rsi+0D8h]; void *
0x1800adac6  cmp     [r8+4], r12b
0x1800adaca  jnz     short loc_1800ADAFF
0x1800adacc  lea     rdx, aInteractivelog_5; "InteractiveLogon_DoNotDisplayLastSigned"...
0x1800adad3  mov     rcx, r14; this
0x1800adad6  call    ?InsertDataForNode@WmiRequestHandlerAdd@@QEAA?AW4_MI_Result@@PEBGPEAX@Z; WmiRequestHandlerAdd::InsertDataForNode(ushort const *,void *)
0x1800adadb  mov     edi, eax
0x1800adadd  test    eax, eax
0x1800adadf  jz      short loc_1800ADAFF
0x1800adae1  mov     rcx, [rsp+308h+var_2C8]
0x1800adae6  test    rcx, rcx
0x1800adae9  jz      short loc_1800ADAFA
0x1800adaeb  mov     rax, [rcx]
  ... truncated ...
```
