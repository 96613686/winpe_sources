# MDM_Policy_Result01_LocalPoliciesSecurityOptions02_InvokeCreateInstance

- ea: `0x1801646cc`
- end: `0x18016566c`
- name: `MDM_Policy_Result01_LocalPoliciesSecurityOptions02_InvokeCreateInstance`
- size: `4000`
- prototype: `__int64 __fastcall(MI_Instance *self, struct _MI_Instance *)`
- caller_count: `1`
- callee_count: `17`
- tags: `registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x180164610`

## callees

- `0x180001008`
- `0x18000104c`
- `0x180003abc`
- `0x180005160`
- `0x180005198`
- `0x180008ac0`
- `0x180008b08`
- `0x18000a768`
- `0x1801646cc`
- `0x18023f3ac`
- `0x180241010`
- `0x18024237c`
- `0x180245824`
- `0x180245930`
- `0x18024ccee`
- `0x18024cd20`
- `0x18024f010`

## string_xrefs

- `0x18016498c`: `Accounts_RenameAdministratorAccount`
- `0x1801649cc`: `Accounts_RenameGuestAccount`
- `0x180164a8c`: `Devices_PreventUsersFromInstallingPrinterDriversWhenConnectingToSharedPrinters`
- `0x180164acc`: `Devices_RestrictCDROMAccessToLocallyLoggedOnUserOnly`
- `0x180164c4c`: `InteractiveLogon_MessageTextForUsersAttemptingToLogOn`
- `0x180164c8c`: `InteractiveLogon_MessageTitleForUsersAttemptingToLogOn`
- `0x180164d0c`: `MicrosoftNetworkClient_DigitallySignCommunicationsAlways`
- `0x180164d4c`: `MicrosoftNetworkClient_DigitallySignCommunicationsIfServerAgrees`
- `0x180164dcc`: `MicrosoftNetworkServer_DigitallySignCommunicationsAlways`
- `0x180164e0c`: `MicrosoftNetworkServer_DigitallySignCommunicationsIfClientAgrees`
- `0x180164e4c`: `NetworkAccess_DoNotAllowAnonymousEnumerationOfSAMAccounts`
- `0x180164e8c`: `NetworkAccess_DoNotAllowAnonymousEnumerationOfSamAccountsAndShares`
- `0x180164ecc`: `NetworkAccess_RestrictAnonymousAccessToNamedPipesAndShares`
- `0x180164f0c`: `NetworkAccess_RestrictClientsAllowedToMakeRemoteCallsToSAM`
- `0x180164f4c`: `NetworkSecurity_AllowLocalSystemToUseComputerIdentityForNTLM`
- `0x180164f8c`: `NetworkSecurity_AllowPKU2UAuthenticationRequests`
- `0x180164fcc`: `NetworkSecurity_DoNotStoreLANManagerHashValueOnNextPasswordChange`
- `0x18016500c`: `NetworkSecurity_LANManagerAuthenticationLevel`
- `0x18016504c`: `NetworkSecurity_MinimumSessionSecurityForNTLMSSPBasedClients`
- `0x18016508c`: `NetworkSecurity_MinimumSessionSecurityForNTLMSSPBasedServers`
- `0x1801650cc`: `NetworkSecurity_RestrictNTLM_AddRemoteServerExceptionsForNTLMAuthentication`
- `0x18016510c`: `NetworkSecurity_RestrictNTLM_AuditIncomingNTLMTraffic`
- `0x18016514c`: `NetworkSecurity_RestrictNTLM_IncomingNTLMTraffic`
- `0x18016518c`: `NetworkSecurity_RestrictNTLM_OutgoingNTLMTrafficToRemoteServers`
- `0x18016524c`: `UserAccountControl_AllowUIAccessApplicationsToPromptForElevation`
- `0x18016530c`: `UserAccountControl_DetectApplicationInstallationsAndPromptForElevation`
- `0x18016538c`: `UserAccountControl_OnlyElevateUIAccessApplicationsThatAreInstalledInSecureLocations`
- `0x18016548c`: `UserAccountControl_VirtualizeFileAndRegistryWriteFailuresToPerUserLocations`
- `0x1801647f5`: `CreateInstanceStart`
- `0x1801655d2`: `CreateInstanceEnd`
- `0x18016473c`: `MDM_Policy_Result01_LocalPoliciesSecurityOptions02`

## pseudocode

```c
__int64 __fastcall MDM_Policy_Result01_LocalPoliciesSecurityOptions02_InvokeCreateInstance(
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
  v10[2] = "MDM_Policy_Result01_LocalPoliciesSecurityOptions02";
  _TlgActivityBase<TraceLoggingActivity<&_tlgProvider_t const * const g_hTraceLoggingProvider,35184372088832,5,_TlgReflectorTag_Param0IsHProvider>,35184372088832,5>::zInternalStart(&v12);
  if ( (unsigned int)dword_180380B68 > 5 && (unsigned __int8)tlgKeywordOn(&dword_180380B68, 0x200000000000LL) )
  {
    if ( v13 && (v15[0] || v15[1] || v15[2] || v15[3]) )
      v4 = v15;
    else
      v4 = 0;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(
      &dword_180380B68,
      qword_180352FE8,
      v14,
      v4);
  }
  if ( LOBYTE(a2[1].classDecl) && (v9 = 0, LOBYTE(a2[1].nameSpace)) )
  {
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
                               &MDM_Policy_Result01_LocalPoliciesSecurityOptions02_NodeList,
                               51,
                               4,
                               &v8);
    if ( inserted == MI_RESULT_OK )
    {
      v10[4] = &v8;
      v11 = 1;
      v6 = v8;
      if ( v8 )
      {
        WmiRequestHandler::SetRequestMIInstance(
          v8,
          a2,
          (struct WmiNodeInfo *)&MDM_Policy_Result01_LocalPoliciesSecurityOptions02_NodeList,
          0x33u);
        if ( BYTE4(a2[1].reserved[0]) == 1
          && (inserted = WmiRequestHandlerAdd::InsertDataForNode(v6, L"Accounts_BlockMicrosoftAccounts", a2[1].reserved)) != MI_RESULT_OK )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( BYTE4(a2[1].reserved[1]) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                v6,
                                L"Accounts_EnableAdministratorAccountStatus",
                                &a2[1].reserved[1])) != MI_RESULT_OK )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( BYTE4(a2[1].reserved[2]) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                v6,
                                L"Accounts_EnableGuestAccountStatus",
                                &a2[1].reserved[2])) != MI_RESULT_OK )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( BYTE4(a2[1].reserved[3]) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                v6,
                                L"Accounts_LimitLocalAccountUseOfBlankPasswordsToConsoleLogonOnly",
                                &a2[1].reserved[3])) != MI_RESULT_OK )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( LOBYTE(a2[2].classDecl) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                v6,
                                L"Accounts_RenameAdministratorAccount",
                                &a2[2])) != MI_RESULT_OK )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( LOBYTE(a2[2].nameSpace) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                v6,
                                L"Accounts_RenameGuestAccount",
                                &a2[2].serverName)) != MI_RESULT_OK )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( LOBYTE(a2[2].reserved[1]) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                v6,
                                L"Devices_AllowedToFormatAndEjectRemovableMedia",
                                a2[2].reserved)) != MI_RESULT_OK )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( BYTE4(a2[2].reserved[2]) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                v6,
                                L"Devices_AllowUndockWithoutHavingToLogon",
                                &a2[2].reserved[2])) != MI_RESULT_OK )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( BYTE4(a2[2].reserved[3]) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                v6,
                                L"Devices_PreventUsersFromInstallingPrinterDriversWhenConnectingToSharedPrinters",
                                &a2[2].reserved[3])) != MI_RESULT_OK )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( LOBYTE(a2[3].classDecl) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                v6,
                                L"Devices_RestrictCDROMAccessToLocallyLoggedOnUserOnly",
                                &a2[3])) != MI_RESULT_OK )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( BYTE4(a2[3].serverName) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                v6,
                                L"InteractiveLogon_DisplayUserInformationWhenTheSessionIsLocked",
                                &a2[3].serverName)) != MI_RESULT_OK )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( BYTE4(a2[3].nameSpace) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                v6,
                                L"InteractiveLogon_DoNotDisplayLastSignedIn",
                                &a2[3].nameSpace)) != MI_RESULT_OK )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( BYTE4(a2[3].reserved[0]) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                v6,
                                L"InteractiveLogon_DoNotDisplayUsernameAtSignIn",
                                a2[3].reserved)) != MI_RESULT_OK )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( BYTE4(a2[3].reserved[1]) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                v6,
                                L"InteractiveLogon_DoNotRequireCTRLALTDEL",
                                &a2[3].reserved[1])) != MI_RESULT_OK )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( BYTE4(a2[3].reserved[2]) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                v6,
                                L"InteractiveLogon_MachineInactivityLimit",
                                &a2[3].reserved[2])) != MI_RESULT_OK )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( LOBYTE(a2[4].ft) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                v6,
                                L"InteractiveLogon_MessageTextForUsersAttemptingToLogOn",
                                &a2[3].reserved[3])) != MI_RESULT_OK )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( LOBYTE(a2[4].serverName) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                v6,
                                L"InteractiveLogon_MessageTitleForUsersAttemptingToLogOn",
                                &a2[4].classDecl)) != MI_RESULT_OK )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( LOBYTE(a2[4].reserved[0]) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                v6,
                                L"InteractiveLogon_SmartCardRemovalBehavior",
                                &a2[4].nameSpace)) != MI_RESULT_OK )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( BYTE4(a2[4].reserved[1]) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                v6,
                                L"MicrosoftNetworkClient_DigitallySignCommunicationsAlways",
                                &a2[4].reserved[1])) != MI_RESULT_OK )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( BYTE4(a2[4].reserved[2]) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                v6,
                                L"MicrosoftNetworkClient_DigitallySignCommunicationsIfServerAgrees",
                                &a2[4].reserved[2])) != MI_RESULT_OK )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( BYTE4(a2[4].reserved[3]) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                v6,
                                L"MicrosoftNetworkClient_SendUnencryptedPasswordToThirdPartySMBServers",
                                &a2[4].reserved[3])) != MI_RESULT_OK )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( BYTE4(a2[5].ft) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                v6,
                                L"MicrosoftNetworkServer_DigitallySignCommunicationsAlways",
                                &a2[5])) != MI_RESULT_OK )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( BYTE4(a2[5].classDecl) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                v6,
                                L"MicrosoftNetworkServer_DigitallySignCommunicationsIfClientAgrees",
                                &a2[5].classDecl)) != MI_RESULT_OK )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( BYTE4(a2[5].serverName) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                v6,
                                L"NetworkAccess_DoNotAllowAnonymousEnumerationOfSAMAccounts",
                                &a2[5].serverName)) != MI_RESULT_OK )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( BYTE4(a2[5].nameSpace) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                v6,
                                L"NetworkAccess_DoNotAllowAnonymousEnumerationOfSamAccountsAndShares",
                                &a2[5].nameSpace)) != MI_RESULT_OK )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( BYTE4(a2[5].reserved[0]) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                v6,
                                L"NetworkAccess_RestrictAnonymousAccessToNamedPipesAndShares",
                                a2[5].reserved)) != MI_RESULT_OK )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( LOBYTE(a2[5].reserved[2]) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                v6,
                                L"NetworkAccess_RestrictClientsAllowedToMakeRemoteCallsToSAM",
                                &a2[5].reserved[1])) != MI_RESULT_OK )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( BYTE4(a2[5].reserved[3]) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                v6,
                                L"NetworkSecurity_AllowLocalSystemToUseComputerIdentityForNTLM",
                                &a2[5].reserved[3])) != MI_RESULT_OK )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( BYTE4(a2[6].ft) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                v6,
                                L"NetworkSecurity_AllowPKU2UAuthenticationRequests",
                                &a2[6])) != MI_RESULT_OK )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( BYTE4(a2[6].classDecl) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                v6,
                                L"NetworkSecurity_DoNotStoreLANManagerHashValueOnNextPasswordChange",
                                &a2[6].classDecl)) != MI_RESULT_OK )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( BYTE4(a2[6].serverName) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                v6,
                                L"NetworkSecurity_LANManagerAuthenticationLevel",
                                &a2[6].serverName)) != MI_RESULT_OK )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( BYTE4(a2[6].nameSpace) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                v6,
                                L"NetworkSecurity_MinimumSessionSecurityForNTLMSSPBasedClients",
                                &a2[6].nameSpace)) != MI_RESULT_OK )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( BYTE4(a2[6].reserved[0]) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                v6,
                                L"NetworkSecurity_MinimumSessionSecurityForNTLMSSPBasedServers",
                                a2[6].reserved)) != MI_RESULT_OK )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( LOBYTE(a2[6].reserved[2]) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                v6,
                                L"NetworkSecurity_RestrictNTLM_AddRemoteServerExceptionsForNTLMAuthentication",
                                &a2[6].reserved[1])) != MI_RESULT_OK )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( BYTE4(a2[6].reserved[3]) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                v6,
                                L"NetworkSecurity_RestrictNTLM_AuditIncomingNTLMTraffic",
                                &a2[6].reserved[3])) != MI_RESULT_OK )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( BYTE4(a2[7].ft) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                v6,
                                L"NetworkSecurity_RestrictNTLM_IncomingNTLMTraffic",
                                &a2[7])) != MI_RESULT_OK )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( BYTE4(a2[7].classDecl) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                v6,
                                L"NetworkSecurity_RestrictNTLM_OutgoingNTLMTrafficToRemoteServers",
                                &a2[7].classDecl)) != MI_RESULT_OK )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( BYTE4(a2[7].serverName) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                v6,
                                L"Shutdown_AllowSystemToBeShutDownWithoutHavingToLogOn",
                                &a2[7].serverName)) != MI_RESULT_OK )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( BYTE4(a2[7].nameSpace) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                v6,
                                L"Shutdown_ClearVirtualMemoryPageFile",
                                &a2[7].nameSpace)) != MI_RESULT_OK )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( BYTE4(a2[7].reserved[0]) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                v6,
                                L"UserAccountControl_AllowUIAccessApplicationsToPromptForElevation",
                                a2[7].reserved)) != MI_RESULT_OK )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( BYTE4(a2[7].reserved[1]) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                v6,
                                L"UserAccountControl_BehaviorOfTheElevationPromptForAdministrators",
                                &a2[7].reserved[1])) != MI_RESULT_OK )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( BYTE4(a2[7].reserved[2]) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                v6,
                                L"UserAccountControl_BehaviorOfTheElevationPromptForStandardUsers",
                                &a2[7].reserved[2])) != MI_RESULT_OK )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( BYTE4(a2[7].reserved[3]) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                v6,
                                L"UserAccountControl_DetectApplicationInstallationsAndPromptForElevation",
                                &a2[7].reserved[3])) != MI_RESULT_OK )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( BYTE4(a2[8].ft) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                v6,
                                L"UserAccountControl_OnlyElevateExecutableFilesThatAreSignedAndValidated",
                                &a2[8])) != MI_RESULT_OK )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( BYTE4(a2[8].classDecl) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                v6,
                                L"UserAccountControl_OnlyElevateUIAccessApplicationsThatAreInstalledInSecureLocations",
                                &a2[8].classDecl)) != MI_RESULT_OK )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( BYTE4(a2[8].serverName) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                v6,
                                L"UserAccountControl_RunAllAdministratorsInAdminApprovalMode",
                                &a2[8].serverName)) != MI_RESULT_OK )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( BYTE4(a2[8].nameSpace) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                v6,
                                L"UserAccountControl_SwitchToTheSecureDesktopWhenPromptingForElevation",
                                &a2[8].nameSpace)) != MI_RESULT_OK )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( BYTE4(a2[8].reserved[0]) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                v6,
                                L"UserAccountControl_UseAdminApprovalMode",
                                a2[8].reserved)) != MI_RESULT_OK )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( BYTE4(a2[8].reserved[1]) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                v6,
                                L"UserAccountControl_VirtualizeFileAndRegistryWriteFailuresToPerUserLocations",
                                &a2[8].reserved[1])) != MI_RESULT_OK )
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
            else
            {
              inserted = MI_Context_ConstructInstance(
                           self,
                           &MDM_Policy_Result01_LocalPoliciesSecurityOptions02_rtti,
                           &instance);
              if ( inserted )
              {
                if ( v8 )
                  (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
              }
              else
              {
                v9 = 1;
                MDM_WindowsLicensing_Subscriptions01_01_Set_InstanceID(&instance, a2[1].ft);
                MDM_WindowsLicensing_Subscriptions01_01_Set_ParentID(&instance, a2[1].serverName);
                MI_Instance_Destruct((MI_Instance *)self);
                if ( v8 )
                  (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
                MI_Instance_Destruct(&instance);
              }
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
  TelemetryEventWriter::WriteEnd((TelemetryEventWriter *)v10, "CreateInstanceEnd", inserted);
  v12 = 2;
  if ( (unsigned int)dword_180380B68 > 5 && (unsigned __int8)tlgKeywordOn(&dword_180380B68, 0x200000000000LL) )
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(
      &dword_180380B68,
      byte_180343C45,
      v14,
      0);
  _TlgActivityBase<TraceLoggingActivity<&_tlgProvider_t const * const g_hTraceLoggingProvider,35184372088832,5,_TlgReflectorTag_Param0IsHProvider>,35184372088832,5>::~_TlgActivityBase<TraceLoggingActivity<&_tlgProvider_t const * const g_hTraceLoggingProvider,35184372088832,5,_TlgReflectorTag_Param0IsHProvider>,35184372088832,5>(&v12);
  return (unsigned int)inserted;
}

```

## disassembly

```asm
0x1801646cc  mov     [rsp+arg_10], rsi
0x1801646d1  mov     [rsp+arg_18], rdi
0x1801646d6  push    r12
0x1801646d8  push    r14
0x1801646da  push    r15
0x1801646dc  sub     rsp, 2F0h
0x1801646e3  mov     rax, cs:__security_cookie
0x1801646ea  xor     rax, rsp
0x1801646ed  mov     [rsp+308h+var_28], rax
0x1801646f5  mov     rsi, rdx
0x1801646f8  mov     r15, rcx
0x1801646fb  xor     edx, edx; Val
0x1801646fd  mov     r8d, 230h; Size
0x180164703  lea     rcx, [rsp+308h+instance]; void *
0x18016470b  call    memset_0
0x180164710  mov     [rsp+308h+var_288], 0
0x18016471b  mov     [rsp+308h+var_284], 0
0x180164723  lea     rax, ??_7TelemetryEventWriter@@6B@; const TelemetryEventWriter::`vftable'
0x18016472a  mov     [rsp+308h+var_2B8], rax
0x18016472f  lea     rax, [rsp+308h+var_288]
0x180164737  mov     [rsp+308h+var_2B0], rax
0x18016473c  lea     rax, aMdmPolicyResul_192; "MDM_Policy_Result01_LocalPoliciesSecuri"...
0x180164743  mov     [rsp+308h+var_2A8], rax
0x180164748  lea     rcx, [rsp+308h+var_288]
0x180164750  call    ?zInternalStart@?$_TlgActivityBase@V?$TraceLoggingActivity@$1?g_hTraceLoggingProvider@@3QEBU_tlgProvider_t@@EB$0CAAAAAAAAAAA@$04U_TlgReflectorTag_Param0IsHProvider@@@@$0CAAAAAAAAAAA@$04@@QEAAXXZ; _TlgActivityBase<TraceLoggingActivity<&_tlgProvider_t const * const g_hTraceLoggingProvider,35184372088832,5,_TlgReflectorTag_Param0IsHProvider>,35184372088832,5>::zInternalStart(void)
0x180164755  mov     eax, cs:dword_180380B68
0x18016475b  cmp     eax, 5
0x18016475e  jbe     short loc_1801647D4
0x180164760  mov     rdx, 200000000000h
0x18016476a  lea     rcx, dword_180380B68
0x180164771  call    _tlgKeywordOn
0x180164776  test    al, al
0x180164778  jz      short loc_1801647D4
0x18016477a  cmp     [rsp+308h+var_284], 0
0x180164782  jz      short loc_1801647B6
0x180164784  cmp     [rsp+308h+var_270], 0
0x18016478c  jnz     short loc_1801647AC
0x18016478e  cmp     [rsp+308h+var_26C], 0
0x180164796  jnz     short loc_1801647AC
0x180164798  cmp     [rsp+308h+var_268], 0
0x1801647a0  jnz     short loc_1801647AC
0x1801647a2  cmp     [rsp+308h+var_264], 0
0x1801647aa  jz      short loc_1801647B6
0x1801647ac  lea     r9, [rsp+308h+var_270]
0x1801647b4  jmp     short loc_1801647B9
0x1801647b6  xor     r9d, r9d
0x1801647b9  lea     r8, [rsp+308h+var_280]
0x1801647c1  lea     rdx, qword_180352FE8
0x1801647c8  lea     rcx, dword_180380B68
0x1801647cf  call    ??$Write@$$V@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *)
0x1801647d4  cmp     byte ptr [rsi+48h], 0
0x1801647d8  jz      loc_1801655CA
0x1801647de  mov     [rsp+308h+var_2C0], 0
0x1801647e3  cmp     byte ptr [rsi+58h], 0
0x1801647e7  jz      loc_1801655CA
0x1801647ed  mov     r9, [rsi+40h]; unsigned __int16 *
0x1801647f1  mov     r8, [rsi+50h]; unsigned __int16 *
0x1801647f5  lea     rdx, aCreateinstance_0; "CreateInstanceStart"
0x1801647fc  lea     rcx, [rsp+308h+var_2B8]; this
0x180164801  call    ?WriteStart@TelemetryEventWriter@@QEAAXPEBDPEBG1@Z; TelemetryEventWriter::WriteStart(char const *,ushort const *,ushort const *)
0x180164806  nop
0x180164807  mov     [rsp+308h+var_2C8], 0
0x180164810  lea     rax, [rsp+308h+var_2C8]
0x180164815  mov     [rsp+308h+var_2D8], rax
0x18016481a  mov     [rsp+308h+var_2E0], 4
0x180164822  mov     [rsp+308h+var_2E8], 33h ; '3'
0x18016482a  lea     r9, ?MDM_Policy_Result01_LocalPoliciesSecurityOptions02_NodeList@@3PAUWmiNodeInfo@@A; WmiNodeInfo near * MDM_Policy_Result01_LocalPoliciesSecurityOptions02_NodeList
0x180164831  mov     r8, [rsi+40h]
0x180164835  mov     rdx, [rsi+50h]
0x180164839  mov     rcx, r15
0x18016483c  call    ?CreateRequestHandlerInstance@@YA?AW4_MI_Result@@PEAU_MI_Context@@PEBG1PEAUWmiNodeInfo@@KW4RequestType@@AEAPEAVWmiRequestHandler@@@Z; CreateRequestHandlerInstance(_MI_Context *,ushort const *,ushort const *,WmiNodeInfo *,ulong,RequestType,WmiRequestHandler * &)
0x180164841  mov     edi, eax
0x180164843  test    eax, eax
0x180164845  jz      short loc_18016484C
0x180164847  jmp     loc_1801655CF
0x18016484c  lea     rax, [rsp+308h+var_2C8]
0x180164851  mov     [rsp+308h+var_298], rax
0x180164856  mov     r12d, 1
0x18016485c  mov     [rsp+308h+var_290], r12b
0x180164861  mov     r14, [rsp+308h+var_2C8]
0x180164866  test    r14, r14
0x180164869  jnz     short loc_180164873
0x18016486b  mov     edi, r12d
0x18016486e  jmp     loc_1801655CF
0x180164873  mov     r9d, 33h ; '3'; unsigned int
0x180164879  lea     r8, ?MDM_Policy_Result01_LocalPoliciesSecurityOptions02_NodeList@@3PAUWmiNodeInfo@@A; struct WmiNodeInfo *
0x180164880  mov     rdx, rsi; struct _MI_Instance *
0x180164883  mov     rcx, r14; this
0x180164886  call    ?SetRequestMIInstance@WmiRequestHandler@@QEAA?AW4_MI_Result@@PEBU_MI_Instance@@PEAUWmiNodeInfo@@K@Z; WmiRequestHandler::SetRequestMIInstance(_MI_Instance const *,WmiNodeInfo *,ulong)
0x18016488b  lea     r8, [rsi+60h]; void *
0x18016488f  cmp     [r8+4], r12b
0x180164893  jnz     short loc_1801648C8
0x180164895  lea     rdx, aAccountsBlockm; "Accounts_BlockMicrosoftAccounts"
0x18016489c  mov     rcx, r14; this
0x18016489f  call    ?InsertDataForNode@WmiRequestHandlerAdd@@QEAA?AW4_MI_Result@@PEBGPEAX@Z; WmiRequestHandlerAdd::InsertDataForNode(ushort const *,void *)
0x1801648a4  mov     edi, eax
0x1801648a6  test    eax, eax
0x1801648a8  jz      short loc_1801648C8
0x1801648aa  mov     rcx, [rsp+308h+var_2C8]
0x1801648af  test    rcx, rcx
0x1801648b2  jz      short loc_1801648C3
0x1801648b4  mov     rax, [rcx]
0x1801648b7  mov     edx, r12d
0x1801648ba  mov     rax, [rax]
0x1801648bd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801648c2  nop
0x1801648c3  jmp     loc_1801655CF
0x1801648c8  lea     r8, [rsi+68h]; void *
0x1801648cc  cmp     [r8+4], r12b
0x1801648d0  jnz     short loc_180164905
0x1801648d2  lea     rdx, aAccountsEnable_0; "Accounts_EnableAdministratorAccountStat"...
0x1801648d9  mov     rcx, r14; this
0x1801648dc  call    ?InsertDataForNode@WmiRequestHandlerAdd@@QEAA?AW4_MI_Result@@PEBGPEAX@Z; WmiRequestHandlerAdd::InsertDataForNode(ushort const *,void *)
0x1801648e1  mov     edi, eax
0x1801648e3  test    eax, eax
0x1801648e5  jz      short loc_180164905
0x1801648e7  mov     rcx, [rsp+308h+var_2C8]
0x1801648ec  test    rcx, rcx
0x1801648ef  jz      short loc_180164900
0x1801648f1  mov     rax, [rcx]
0x1801648f4  mov     edx, r12d
0x1801648f7  mov     rax, [rax]
0x1801648fa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801648ff  nop
0x180164900  jmp     loc_1801655CF
0x180164905  lea     r8, [rsi+70h]; void *
0x180164909  cmp     [r8+4], r12b
0x18016490d  jnz     short loc_180164942
0x18016490f  lea     rdx, aAccountsEnable; "Accounts_EnableGuestAccountStatus"
0x180164916  mov     rcx, r14; this
0x180164919  call    ?InsertDataForNode@WmiRequestHandlerAdd@@QEAA?AW4_MI_Result@@PEBGPEAX@Z; WmiRequestHandlerAdd::InsertDataForNode(ushort const *,void *)
0x18016491e  mov     edi, eax
0x180164920  test    eax, eax
0x180164922  jz      short loc_180164942
0x180164924  mov     rcx, [rsp+308h+var_2C8]
0x180164929  test    rcx, rcx
0x18016492c  jz      short loc_18016493D
0x18016492e  mov     rax, [rcx]
0x180164931  mov     edx, r12d
0x180164934  mov     rax, [rax]
0x180164937  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18016493c  nop
0x18016493d  jmp     loc_1801655CF
0x180164942  lea     r8, [rsi+78h]; void *
0x180164946  cmp     [r8+4], r12b
0x18016494a  jnz     short loc_18016497F
0x18016494c  lea     rdx, aAccountsLimitl; "Accounts_LimitLocalAccountUseOfBlankPas"...
0x180164953  mov     rcx, r14; this
0x180164956  call    ?InsertDataForNode@WmiRequestHandlerAdd@@QEAA?AW4_MI_Result@@PEBGPEAX@Z; WmiRequestHandlerAdd::InsertDataForNode(ushort const *,void *)
0x18016495b  mov     edi, eax
0x18016495d  test    eax, eax
0x18016495f  jz      short loc_18016497F
0x180164961  mov     rcx, [rsp+308h+var_2C8]
0x180164966  test    rcx, rcx
0x180164969  jz      short loc_18016497A
0x18016496b  mov     rax, [rcx]
0x18016496e  mov     edx, r12d
0x180164971  mov     rax, [rax]
0x180164974  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180164979  nop
0x18016497a  jmp     loc_1801655CF
0x18016497f  lea     r8, [rsi+80h]; void *
0x180164986  cmp     [r8+8], r12b
0x18016498a  jnz     short loc_1801649BF
0x18016498c  lea     rdx, aAccountsRename_0; "Accounts_RenameAdministratorAccount"
0x180164993  mov     rcx, r14; this
0x180164996  call    ?InsertDataForNode@WmiRequestHandlerAdd@@QEAA?AW4_MI_Result@@PEBGPEAX@Z; WmiRequestHandlerAdd::InsertDataForNode(ushort const *,void *)
0x18016499b  mov     edi, eax
0x18016499d  test    eax, eax
0x18016499f  jz      short loc_1801649BF
0x1801649a1  mov     rcx, [rsp+308h+var_2C8]
0x1801649a6  test    rcx, rcx
0x1801649a9  jz      short loc_1801649BA
0x1801649ab  mov     rax, [rcx]
0x1801649ae  mov     edx, r12d
0x1801649b1  mov     rax, [rax]
0x1801649b4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801649b9  nop
0x1801649ba  jmp     loc_1801655CF
0x1801649bf  lea     r8, [rsi+90h]; void *
0x1801649c6  cmp     [r8+8], r12b
0x1801649ca  jnz     short loc_1801649FF
0x1801649cc  lea     rdx, aAccountsRename; "Accounts_RenameGuestAccount"
0x1801649d3  mov     rcx, r14; this
0x1801649d6  call    ?InsertDataForNode@WmiRequestHandlerAdd@@QEAA?AW4_MI_Result@@PEBGPEAX@Z; WmiRequestHandlerAdd::InsertDataForNode(ushort const *,void *)
0x1801649db  mov     edi, eax
0x1801649dd  test    eax, eax
0x1801649df  jz      short loc_1801649FF
0x1801649e1  mov     rcx, [rsp+308h+var_2C8]
0x1801649e6  test    rcx, rcx
0x1801649e9  jz      short loc_1801649FA
0x1801649eb  mov     rax, [rcx]
0x1801649ee  mov     edx, r12d
0x1801649f1  mov     rax, [rax]
0x1801649f4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801649f9  nop
0x1801649fa  jmp     loc_1801655CF
0x1801649ff  lea     r8, [rsi+0A0h]; void *
0x180164a06  cmp     [r8+8], r12b
0x180164a0a  jnz     short loc_180164A3F
0x180164a0c  lea     rdx, aDevicesAllowed; "Devices_AllowedToFormatAndEjectRemovabl"...
0x180164a13  mov     rcx, r14; this
0x180164a16  call    ?InsertDataForNode@WmiRequestHandlerAdd@@QEAA?AW4_MI_Result@@PEBGPEAX@Z; WmiRequestHandlerAdd::InsertDataForNode(ushort const *,void *)
0x180164a1b  mov     edi, eax
0x180164a1d  test    eax, eax
0x180164a1f  jz      short loc_180164A3F
0x180164a21  mov     rcx, [rsp+308h+var_2C8]
0x180164a26  test    rcx, rcx
0x180164a29  jz      short loc_180164A3A
0x180164a2b  mov     rax, [rcx]
0x180164a2e  mov     edx, r12d
0x180164a31  mov     rax, [rax]
0x180164a34  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180164a39  nop
0x180164a3a  jmp     loc_1801655CF
0x180164a3f  lea     r8, [rsi+0B0h]; void *
0x180164a46  cmp     [r8+4], r12b
0x180164a4a  jnz     short loc_180164A7F
0x180164a4c  lea     rdx, aDevicesAllowun; "Devices_AllowUndockWithoutHavingToLogon"
0x180164a53  mov     rcx, r14; this
0x180164a56  call    ?InsertDataForNode@WmiRequestHandlerAdd@@QEAA?AW4_MI_Result@@PEBGPEAX@Z; WmiRequestHandlerAdd::InsertDataForNode(ushort const *,void *)
0x180164a5b  mov     edi, eax
0x180164a5d  test    eax, eax
0x180164a5f  jz      short loc_180164A7F
0x180164a61  mov     rcx, [rsp+308h+var_2C8]
0x180164a66  test    rcx, rcx
0x180164a69  jz      short loc_180164A7A
0x180164a6b  mov     rax, [rcx]
0x180164a6e  mov     edx, r12d
0x180164a71  mov     rax, [rax]
0x180164a74  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180164a79  nop
0x180164a7a  jmp     loc_1801655CF
0x180164a7f  lea     r8, [rsi+0B8h]; void *
0x180164a86  cmp     [r8+4], r12b
0x180164a8a  jnz     short loc_180164ABF
0x180164a8c  lea     rdx, aDevicesPrevent; "Devices_PreventUsersFromInstallingPrint"...
0x180164a93  mov     rcx, r14; this
0x180164a96  call    ?InsertDataForNode@WmiRequestHandlerAdd@@QEAA?AW4_MI_Result@@PEBGPEAX@Z; WmiRequestHandlerAdd::InsertDataForNode(ushort const *,void *)
0x180164a9b  mov     edi, eax
0x180164a9d  test    eax, eax
0x180164a9f  jz      short loc_180164ABF
0x180164aa1  mov     rcx, [rsp+308h+var_2C8]
0x180164aa6  test    rcx, rcx
0x180164aa9  jz      short loc_180164ABA
0x180164aab  mov     rax, [rcx]
0x180164aae  mov     edx, r12d
0x180164ab1  mov     rax, [rax]
0x180164ab4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180164ab9  nop
0x180164aba  jmp     loc_1801655CF
0x180164abf  lea     r8, [rsi+0C0h]; void *
0x180164ac6  cmp     [r8+8], r12b
0x180164aca  jnz     short loc_180164AFF
0x180164acc  lea     rdx, aDevicesRestric; "Devices_RestrictCDROMAccessToLocallyLog"...
0x180164ad3  mov     rcx, r14; this
0x180164ad6  call    ?InsertDataForNode@WmiRequestHandlerAdd@@QEAA?AW4_MI_Result@@PEBGPEAX@Z; WmiRequestHandlerAdd::InsertDataForNode(ushort const *,void *)
0x180164adb  mov     edi, eax
0x180164add  test    eax, eax
0x180164adf  jz      short loc_180164AFF
0x180164ae1  mov     rcx, [rsp+308h+var_2C8]
0x180164ae6  test    rcx, rcx
0x180164ae9  jz      short loc_180164AFA
0x180164aeb  mov     rax, [rcx]
0x180164aee  mov     edx, r12d
0x180164af1  mov     rax, [rax]
0x180164af4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180164af9  nop
0x180164afa  jmp     loc_1801655CF
0x180164aff  lea     r8, [rsi+0D0h]; void *
0x180164b06  cmp     [r8+4], r12b
0x180164b0a  jnz     short loc_180164B3F
0x180164b0c  lea     rdx, aInteractivelog; "InteractiveLogon_DisplayUserInformation"...
0x180164b13  mov     rcx, r14; this
0x180164b16  call    ?InsertDataForNode@WmiRequestHandlerAdd@@QEAA?AW4_MI_Result@@PEBGPEAX@Z; WmiRequestHandlerAdd::InsertDataForNode(ushort const *,void *)
0x180164b1b  mov     edi, eax
0x180164b1d  test    eax, eax
0x180164b1f  jz      short loc_180164B3F
0x180164b21  mov     rcx, [rsp+308h+var_2C8]
0x180164b26  test    rcx, rcx
0x180164b29  jz      short loc_180164B3A
0x180164b2b  mov     rax, [rcx]
0x180164b2e  mov     edx, r12d
0x180164b31  mov     rax, [rax]
0x180164b34  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180164b39  nop
0x180164b3a  jmp     loc_1801655CF
0x180164b3f  lea     r8, [rsi+0D8h]; void *
0x180164b46  cmp     [r8+4], r12b
0x180164b4a  jnz     short loc_180164B7F
0x180164b4c  lea     rdx, aInteractivelog_5; "InteractiveLogon_DoNotDisplayLastSigned"...
0x180164b53  mov     rcx, r14; this
0x180164b56  call    ?InsertDataForNode@WmiRequestHandlerAdd@@QEAA?AW4_MI_Result@@PEBGPEAX@Z; WmiRequestHandlerAdd::InsertDataForNode(ushort const *,void *)
0x180164b5b  mov     edi, eax
0x180164b5d  test    eax, eax
0x180164b5f  jz      short loc_180164B7F
0x180164b61  mov     rcx, [rsp+308h+var_2C8]
0x180164b66  test    rcx, rcx
0x180164b69  jz      short loc_180164B7A
0x180164b6b  mov     rax, [rcx]
  ... truncated ...
```
