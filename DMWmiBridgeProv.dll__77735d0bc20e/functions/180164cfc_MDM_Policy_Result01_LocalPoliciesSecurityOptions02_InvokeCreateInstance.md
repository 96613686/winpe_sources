# MDM_Policy_Result01_LocalPoliciesSecurityOptions02_InvokeCreateInstance

- ea: `0x180164cfc`
- end: `0x180165c9b`
- name: `MDM_Policy_Result01_LocalPoliciesSecurityOptions02_InvokeCreateInstance`
- size: `3999`
- prototype: `__int64 __fastcall(MI_Instance *self, struct _MI_Instance *)`
- caller_count: `1`
- callee_count: `17`
- tags: `registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x180164c00`

## callees

- `0x180001008`
- `0x18000104c`
- `0x180003a5c`
- `0x180004f8c`
- `0x180004fc4`
- `0x18000871c`
- `0x180008764`
- `0x18000a280`
- `0x180164cfc`
- `0x180240078`
- `0x180241ce0`
- `0x180243010`
- `0x180246310`
- `0x180246418`
- `0x18024d12e`
- `0x18024d160`
- `0x18024f010`

## string_xrefs

- `0x180164fbc`: `Accounts_RenameAdministratorAccount`
- `0x180164ffc`: `Accounts_RenameGuestAccount`
- `0x1801650bc`: `Devices_PreventUsersFromInstallingPrinterDriversWhenConnectingToSharedPrinters`
- `0x1801650fc`: `Devices_RestrictCDROMAccessToLocallyLoggedOnUserOnly`
- `0x18016527c`: `InteractiveLogon_MessageTextForUsersAttemptingToLogOn`
- `0x1801652bc`: `InteractiveLogon_MessageTitleForUsersAttemptingToLogOn`
- `0x18016533c`: `MicrosoftNetworkClient_DigitallySignCommunicationsAlways`
- `0x18016537c`: `MicrosoftNetworkClient_DigitallySignCommunicationsIfServerAgrees`
- `0x1801653fc`: `MicrosoftNetworkServer_DigitallySignCommunicationsAlways`
- `0x18016543c`: `MicrosoftNetworkServer_DigitallySignCommunicationsIfClientAgrees`
- `0x18016547c`: `NetworkAccess_DoNotAllowAnonymousEnumerationOfSAMAccounts`
- `0x1801654bc`: `NetworkAccess_DoNotAllowAnonymousEnumerationOfSamAccountsAndShares`
- `0x1801654fc`: `NetworkAccess_RestrictAnonymousAccessToNamedPipesAndShares`
- `0x18016553c`: `NetworkAccess_RestrictClientsAllowedToMakeRemoteCallsToSAM`
- `0x18016557c`: `NetworkSecurity_AllowLocalSystemToUseComputerIdentityForNTLM`
- `0x1801655bc`: `NetworkSecurity_AllowPKU2UAuthenticationRequests`
- `0x1801655fc`: `NetworkSecurity_DoNotStoreLANManagerHashValueOnNextPasswordChange`
- `0x18016563c`: `NetworkSecurity_LANManagerAuthenticationLevel`
- `0x18016567c`: `NetworkSecurity_MinimumSessionSecurityForNTLMSSPBasedClients`
- `0x1801656bc`: `NetworkSecurity_MinimumSessionSecurityForNTLMSSPBasedServers`
- `0x1801656fc`: `NetworkSecurity_RestrictNTLM_AddRemoteServerExceptionsForNTLMAuthentication`
- `0x18016573c`: `NetworkSecurity_RestrictNTLM_AuditIncomingNTLMTraffic`
- `0x18016577c`: `NetworkSecurity_RestrictNTLM_IncomingNTLMTraffic`
- `0x1801657bc`: `NetworkSecurity_RestrictNTLM_OutgoingNTLMTrafficToRemoteServers`
- `0x18016587c`: `UserAccountControl_AllowUIAccessApplicationsToPromptForElevation`
- `0x18016593c`: `UserAccountControl_DetectApplicationInstallationsAndPromptForElevation`
- `0x1801659bc`: `UserAccountControl_OnlyElevateUIAccessApplicationsThatAreInstalledInSecureLocations`
- `0x180165abc`: `UserAccountControl_VirtualizeFileAndRegistryWriteFailuresToPerUserLocations`
- `0x180164e25`: `CreateInstanceStart`
- `0x180165c02`: `CreateInstanceEnd`
- `0x180164d6c`: `MDM_Policy_Result01_LocalPoliciesSecurityOptions02`

## pseudocode

```c
__int64 __fastcall MDM_Policy_Result01_LocalPoliciesSecurityOptions02_InvokeCreateInstance(
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
    inserted = CreateRequestHandlerInstance(
                 (__int64)self,
                 (wchar_t *)a2[1].serverName,
                 (const unsigned __int16 *)a2[1].ft,
                 (struct WmiNodeInfo *)&MDM_Policy_Result01_LocalPoliciesSecurityOptions02_NodeList,
                 0x33u,
                 4,
                 &v8);
    if ( !inserted )
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
          && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                           v6,
                           L"Accounts_BlockMicrosoftAccounts",
                           (LONG *)a2[1].reserved)) != 0 )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( BYTE4(a2[1].reserved[1]) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                v6,
                                L"Accounts_EnableAdministratorAccountStatus",
                                (LONG *)&a2[1].reserved[1])) != 0 )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( BYTE4(a2[1].reserved[2]) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                v6,
                                L"Accounts_EnableGuestAccountStatus",
                                (LONG *)&a2[1].reserved[2])) != 0 )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( BYTE4(a2[1].reserved[3]) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                v6,
                                L"Accounts_LimitLocalAccountUseOfBlankPasswordsToConsoleLogonOnly",
                                (LONG *)&a2[1].reserved[3])) != 0 )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( LOBYTE(a2[2].classDecl) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                v6,
                                L"Accounts_RenameAdministratorAccount",
                                (LONG *)&a2[2])) != 0 )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( LOBYTE(a2[2].nameSpace) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                v6,
                                L"Accounts_RenameGuestAccount",
                                (LONG *)&a2[2].serverName)) != 0 )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( LOBYTE(a2[2].reserved[1]) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                v6,
                                L"Devices_AllowedToFormatAndEjectRemovableMedia",
                                (LONG *)a2[2].reserved)) != 0 )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( BYTE4(a2[2].reserved[2]) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                v6,
                                L"Devices_AllowUndockWithoutHavingToLogon",
                                (LONG *)&a2[2].reserved[2])) != 0 )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( BYTE4(a2[2].reserved[3]) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                v6,
                                L"Devices_PreventUsersFromInstallingPrinterDriversWhenConnectingToSharedPrinters",
                                (LONG *)&a2[2].reserved[3])) != 0 )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( LOBYTE(a2[3].classDecl) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                v6,
                                L"Devices_RestrictCDROMAccessToLocallyLoggedOnUserOnly",
                                (LONG *)&a2[3])) != 0 )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( BYTE4(a2[3].serverName) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                v6,
                                L"InteractiveLogon_DisplayUserInformationWhenTheSessionIsLocked",
                                (LONG *)&a2[3].serverName)) != 0 )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( BYTE4(a2[3].nameSpace) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                v6,
                                L"InteractiveLogon_DoNotDisplayLastSignedIn",
                                (LONG *)&a2[3].nameSpace)) != 0 )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( BYTE4(a2[3].reserved[0]) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                v6,
                                L"InteractiveLogon_DoNotDisplayUsernameAtSignIn",
                                (LONG *)a2[3].reserved)) != 0 )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( BYTE4(a2[3].reserved[1]) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                v6,
                                L"InteractiveLogon_DoNotRequireCTRLALTDEL",
                                (LONG *)&a2[3].reserved[1])) != 0 )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( BYTE4(a2[3].reserved[2]) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                v6,
                                L"InteractiveLogon_MachineInactivityLimit",
                                (LONG *)&a2[3].reserved[2])) != 0 )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( LOBYTE(a2[4].ft) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                v6,
                                L"InteractiveLogon_MessageTextForUsersAttemptingToLogOn",
                                (LONG *)&a2[3].reserved[3])) != 0 )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( LOBYTE(a2[4].serverName) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                v6,
                                L"InteractiveLogon_MessageTitleForUsersAttemptingToLogOn",
                                (LONG *)&a2[4].classDecl)) != 0 )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( LOBYTE(a2[4].reserved[0]) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                v6,
                                L"InteractiveLogon_SmartCardRemovalBehavior",
                                (LONG *)&a2[4].nameSpace)) != 0 )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( BYTE4(a2[4].reserved[1]) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                v6,
                                L"MicrosoftNetworkClient_DigitallySignCommunicationsAlways",
                                (LONG *)&a2[4].reserved[1])) != 0 )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( BYTE4(a2[4].reserved[2]) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                v6,
                                L"MicrosoftNetworkClient_DigitallySignCommunicationsIfServerAgrees",
                                (LONG *)&a2[4].reserved[2])) != 0 )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( BYTE4(a2[4].reserved[3]) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                v6,
                                L"MicrosoftNetworkClient_SendUnencryptedPasswordToThirdPartySMBServers",
                                (LONG *)&a2[4].reserved[3])) != 0 )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( BYTE4(a2[5].ft) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                v6,
                                L"MicrosoftNetworkServer_DigitallySignCommunicationsAlways",
                                (LONG *)&a2[5])) != 0 )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( BYTE4(a2[5].classDecl) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                v6,
                                L"MicrosoftNetworkServer_DigitallySignCommunicationsIfClientAgrees",
                                (LONG *)&a2[5].classDecl)) != 0 )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( BYTE4(a2[5].serverName) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                v6,
                                L"NetworkAccess_DoNotAllowAnonymousEnumerationOfSAMAccounts",
                                (LONG *)&a2[5].serverName)) != 0 )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( BYTE4(a2[5].nameSpace) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                v6,
                                L"NetworkAccess_DoNotAllowAnonymousEnumerationOfSamAccountsAndShares",
                                (LONG *)&a2[5].nameSpace)) != 0 )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( BYTE4(a2[5].reserved[0]) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                v6,
                                L"NetworkAccess_RestrictAnonymousAccessToNamedPipesAndShares",
                                (LONG *)a2[5].reserved)) != 0 )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( LOBYTE(a2[5].reserved[2]) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                v6,
                                L"NetworkAccess_RestrictClientsAllowedToMakeRemoteCallsToSAM",
                                (LONG *)&a2[5].reserved[1])) != 0 )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( BYTE4(a2[5].reserved[3]) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                v6,
                                L"NetworkSecurity_AllowLocalSystemToUseComputerIdentityForNTLM",
                                (LONG *)&a2[5].reserved[3])) != 0 )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( BYTE4(a2[6].ft) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                v6,
                                L"NetworkSecurity_AllowPKU2UAuthenticationRequests",
                                (LONG *)&a2[6])) != 0 )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( BYTE4(a2[6].classDecl) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                v6,
                                L"NetworkSecurity_DoNotStoreLANManagerHashValueOnNextPasswordChange",
                                (LONG *)&a2[6].classDecl)) != 0 )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( BYTE4(a2[6].serverName) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                v6,
                                L"NetworkSecurity_LANManagerAuthenticationLevel",
                                (LONG *)&a2[6].serverName)) != 0 )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( BYTE4(a2[6].nameSpace) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                v6,
                                L"NetworkSecurity_MinimumSessionSecurityForNTLMSSPBasedClients",
                                (LONG *)&a2[6].nameSpace)) != 0 )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( BYTE4(a2[6].reserved[0]) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                v6,
                                L"NetworkSecurity_MinimumSessionSecurityForNTLMSSPBasedServers",
                                (LONG *)a2[6].reserved)) != 0 )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( LOBYTE(a2[6].reserved[2]) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                v6,
                                L"NetworkSecurity_RestrictNTLM_AddRemoteServerExceptionsForNTLMAuthentication",
                                (LONG *)&a2[6].reserved[1])) != 0 )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( BYTE4(a2[6].reserved[3]) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                v6,
                                L"NetworkSecurity_RestrictNTLM_AuditIncomingNTLMTraffic",
                                (LONG *)&a2[6].reserved[3])) != 0 )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( BYTE4(a2[7].ft) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                v6,
                                L"NetworkSecurity_RestrictNTLM_IncomingNTLMTraffic",
                                (LONG *)&a2[7])) != 0 )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( BYTE4(a2[7].classDecl) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                v6,
                                L"NetworkSecurity_RestrictNTLM_OutgoingNTLMTrafficToRemoteServers",
                                (LONG *)&a2[7].classDecl)) != 0 )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( BYTE4(a2[7].serverName) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                v6,
                                L"Shutdown_AllowSystemToBeShutDownWithoutHavingToLogOn",
                                (LONG *)&a2[7].serverName)) != 0 )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( BYTE4(a2[7].nameSpace) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                v6,
                                L"Shutdown_ClearVirtualMemoryPageFile",
                                (LONG *)&a2[7].nameSpace)) != 0 )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( BYTE4(a2[7].reserved[0]) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                v6,
                                L"UserAccountControl_AllowUIAccessApplicationsToPromptForElevation",
                                (LONG *)a2[7].reserved)) != 0 )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( BYTE4(a2[7].reserved[1]) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                v6,
                                L"UserAccountControl_BehaviorOfTheElevationPromptForAdministrators",
                                (LONG *)&a2[7].reserved[1])) != 0 )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( BYTE4(a2[7].reserved[2]) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                v6,
                                L"UserAccountControl_BehaviorOfTheElevationPromptForStandardUsers",
                                (LONG *)&a2[7].reserved[2])) != 0 )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( BYTE4(a2[7].reserved[3]) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                v6,
                                L"UserAccountControl_DetectApplicationInstallationsAndPromptForElevation",
                                (LONG *)&a2[7].reserved[3])) != 0 )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( BYTE4(a2[8].ft) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                v6,
                                L"UserAccountControl_OnlyElevateExecutableFilesThatAreSignedAndValidated",
                                (LONG *)&a2[8])) != 0 )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( BYTE4(a2[8].classDecl) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                v6,
                                L"UserAccountControl_OnlyElevateUIAccessApplicationsThatAreInstalledInSecureLocations",
                                (LONG *)&a2[8].classDecl)) != 0 )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( BYTE4(a2[8].serverName) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                v6,
                                L"UserAccountControl_RunAllAdministratorsInAdminApprovalMode",
                                (LONG *)&a2[8].serverName)) != 0 )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( BYTE4(a2[8].nameSpace) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                v6,
                                L"UserAccountControl_SwitchToTheSecureDesktopWhenPromptingForElevation",
                                (LONG *)&a2[8].nameSpace)) != 0 )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( BYTE4(a2[8].reserved[0]) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                v6,
                                L"UserAccountControl_UseAdminApprovalMode",
                                (LONG *)a2[8].reserved)) != 0 )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( BYTE4(a2[8].reserved[1]) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                v6,
                                L"UserAccountControl_VirtualizeFileAndRegistryWriteFailuresToPerUserLocations",
                                (LONG *)&a2[8].reserved[1])) != 0 )
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
        inserted = 1;
      }
    }
  }
  else
  {
    inserted = 4;
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
  return inserted;
}

```

## disassembly

```asm
0x180164cfc  mov     [rsp+arg_10], rsi
0x180164d01  mov     [rsp+arg_18], rdi
0x180164d06  push    r12
0x180164d08  push    r14
0x180164d0a  push    r15
0x180164d0c  sub     rsp, 2F0h
0x180164d13  mov     rax, cs:__security_cookie
0x180164d1a  xor     rax, rsp
0x180164d1d  mov     [rsp+308h+var_28], rax
0x180164d25  mov     rsi, rdx
0x180164d28  mov     r15, rcx
0x180164d2b  xor     edx, edx; Val
0x180164d2d  mov     r8d, 230h; Size
0x180164d33  lea     rcx, [rsp+308h+instance]; void *
0x180164d3b  call    memset_0
0x180164d40  mov     [rsp+308h+var_288], 0
0x180164d4b  mov     [rsp+308h+var_284], 0
0x180164d53  lea     rax, ??_7TelemetryEventWriter@@6B@; const TelemetryEventWriter::`vftable'
0x180164d5a  mov     [rsp+308h+var_2B8], rax
0x180164d5f  lea     rax, [rsp+308h+var_288]
0x180164d67  mov     [rsp+308h+var_2B0], rax
0x180164d6c  lea     rax, aMdmPolicyResul_192; "MDM_Policy_Result01_LocalPoliciesSecuri"...
0x180164d73  mov     [rsp+308h+var_2A8], rax
0x180164d78  lea     rcx, [rsp+308h+var_288]
0x180164d80  call    ?zInternalStart@?$_TlgActivityBase@V?$TraceLoggingActivity@$1?g_hTraceLoggingProvider@@3QEBU_tlgProvider_t@@EB$0CAAAAAAAAAAA@$04U_TlgReflectorTag_Param0IsHProvider@@@@$0CAAAAAAAAAAA@$04@@QEAAXXZ; _TlgActivityBase<TraceLoggingActivity<&_tlgProvider_t const * const g_hTraceLoggingProvider,35184372088832,5,_TlgReflectorTag_Param0IsHProvider>,35184372088832,5>::zInternalStart(void)
0x180164d85  mov     eax, cs:dword_180380B68
0x180164d8b  cmp     eax, 5
0x180164d8e  jbe     short loc_180164E04
0x180164d90  mov     rdx, 200000000000h
0x180164d9a  lea     rcx, dword_180380B68
0x180164da1  call    _tlgKeywordOn
0x180164da6  test    al, al
0x180164da8  jz      short loc_180164E04
0x180164daa  cmp     [rsp+308h+var_284], 0
0x180164db2  jz      short loc_180164DE6
0x180164db4  cmp     [rsp+308h+var_270], 0
0x180164dbc  jnz     short loc_180164DDC
0x180164dbe  cmp     [rsp+308h+var_26C], 0
0x180164dc6  jnz     short loc_180164DDC
0x180164dc8  cmp     [rsp+308h+var_268], 0
0x180164dd0  jnz     short loc_180164DDC
0x180164dd2  cmp     [rsp+308h+var_264], 0
0x180164dda  jz      short loc_180164DE6
0x180164ddc  lea     r9, [rsp+308h+var_270]
0x180164de4  jmp     short loc_180164DE9
0x180164de6  xor     r9d, r9d
0x180164de9  lea     r8, [rsp+308h+var_280]
0x180164df1  lea     rdx, qword_180352FE8
0x180164df8  lea     rcx, dword_180380B68
0x180164dff  call    ??$Write@$$V@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *)
0x180164e04  cmp     byte ptr [rsi+48h], 0
0x180164e08  jz      loc_180165BFA
0x180164e0e  mov     [rsp+308h+var_2C0], 0
0x180164e13  cmp     byte ptr [rsi+58h], 0
0x180164e17  jz      loc_180165BFA
0x180164e1d  mov     r9, [rsi+40h]; unsigned __int16 *
0x180164e21  mov     r8, [rsi+50h]; unsigned __int16 *
0x180164e25  lea     rdx, aCreateinstance_0; "CreateInstanceStart"
0x180164e2c  lea     rcx, [rsp+308h+var_2B8]; this
0x180164e31  call    ?WriteStart@TelemetryEventWriter@@QEAAXPEBDPEBG1@Z; TelemetryEventWriter::WriteStart(char const *,ushort const *,ushort const *)
0x180164e36  nop
0x180164e37  mov     [rsp+308h+var_2C8], 0
0x180164e40  lea     rax, [rsp+308h+var_2C8]
0x180164e45  mov     [rsp+308h+var_2D8], rax
0x180164e4a  mov     [rsp+308h+var_2E0], 4
0x180164e52  mov     [rsp+308h+var_2E8], 33h ; '3'
0x180164e5a  lea     r9, ?MDM_Policy_Result01_LocalPoliciesSecurityOptions02_NodeList@@3PAUWmiNodeInfo@@A; WmiNodeInfo near * MDM_Policy_Result01_LocalPoliciesSecurityOptions02_NodeList
0x180164e61  mov     r8, [rsi+40h]
0x180164e65  mov     rdx, [rsi+50h]
0x180164e69  mov     rcx, r15
0x180164e6c  call    ?CreateRequestHandlerInstance@@YA?AW4_MI_Result@@PEAU_MI_Context@@PEBG1PEAUWmiNodeInfo@@KW4RequestType@@AEAPEAVWmiRequestHandler@@@Z; CreateRequestHandlerInstance(_MI_Context *,ushort const *,ushort const *,WmiNodeInfo *,ulong,RequestType,WmiRequestHandler * &)
0x180164e71  mov     edi, eax
0x180164e73  test    eax, eax
0x180164e75  jz      short loc_180164E7C
0x180164e77  jmp     loc_180165BFF
0x180164e7c  lea     rax, [rsp+308h+var_2C8]
0x180164e81  mov     [rsp+308h+var_298], rax
0x180164e86  mov     r12d, 1
0x180164e8c  mov     [rsp+308h+var_290], r12b
0x180164e91  mov     r14, [rsp+308h+var_2C8]
0x180164e96  test    r14, r14
0x180164e99  jnz     short loc_180164EA3
0x180164e9b  mov     edi, r12d
0x180164e9e  jmp     loc_180165BFF
0x180164ea3  mov     r9d, 33h ; '3'; unsigned int
0x180164ea9  lea     r8, ?MDM_Policy_Result01_LocalPoliciesSecurityOptions02_NodeList@@3PAUWmiNodeInfo@@A; struct WmiNodeInfo *
0x180164eb0  mov     rdx, rsi; struct _MI_Instance *
0x180164eb3  mov     rcx, r14; this
0x180164eb6  call    ?SetRequestMIInstance@WmiRequestHandler@@QEAA?AW4_MI_Result@@PEBU_MI_Instance@@PEAUWmiNodeInfo@@K@Z; WmiRequestHandler::SetRequestMIInstance(_MI_Instance const *,WmiNodeInfo *,ulong)
0x180164ebb  lea     r8, [rsi+60h]; void *
0x180164ebf  cmp     [r8+4], r12b
0x180164ec3  jnz     short loc_180164EF8
0x180164ec5  lea     rdx, aAccountsBlockm; "Accounts_BlockMicrosoftAccounts"
0x180164ecc  mov     rcx, r14; this
0x180164ecf  call    ?InsertDataForNode@WmiRequestHandlerAdd@@QEAA?AW4_MI_Result@@PEBGPEAX@Z; WmiRequestHandlerAdd::InsertDataForNode(ushort const *,void *)
0x180164ed4  mov     edi, eax
0x180164ed6  test    eax, eax
0x180164ed8  jz      short loc_180164EF8
0x180164eda  mov     rcx, [rsp+308h+var_2C8]
0x180164edf  test    rcx, rcx
0x180164ee2  jz      short loc_180164EF3
0x180164ee4  mov     rax, [rcx]
0x180164ee7  mov     edx, r12d
0x180164eea  mov     rax, [rax]
0x180164eed  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180164ef2  nop
0x180164ef3  jmp     loc_180165BFF
0x180164ef8  lea     r8, [rsi+68h]; void *
0x180164efc  cmp     [r8+4], r12b
0x180164f00  jnz     short loc_180164F35
0x180164f02  lea     rdx, aAccountsEnable_0; "Accounts_EnableAdministratorAccountStat"...
0x180164f09  mov     rcx, r14; this
0x180164f0c  call    ?InsertDataForNode@WmiRequestHandlerAdd@@QEAA?AW4_MI_Result@@PEBGPEAX@Z; WmiRequestHandlerAdd::InsertDataForNode(ushort const *,void *)
0x180164f11  mov     edi, eax
0x180164f13  test    eax, eax
0x180164f15  jz      short loc_180164F35
0x180164f17  mov     rcx, [rsp+308h+var_2C8]
0x180164f1c  test    rcx, rcx
0x180164f1f  jz      short loc_180164F30
0x180164f21  mov     rax, [rcx]
0x180164f24  mov     edx, r12d
0x180164f27  mov     rax, [rax]
0x180164f2a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180164f2f  nop
0x180164f30  jmp     loc_180165BFF
0x180164f35  lea     r8, [rsi+70h]; void *
0x180164f39  cmp     [r8+4], r12b
0x180164f3d  jnz     short loc_180164F72
0x180164f3f  lea     rdx, aAccountsEnable; "Accounts_EnableGuestAccountStatus"
0x180164f46  mov     rcx, r14; this
0x180164f49  call    ?InsertDataForNode@WmiRequestHandlerAdd@@QEAA?AW4_MI_Result@@PEBGPEAX@Z; WmiRequestHandlerAdd::InsertDataForNode(ushort const *,void *)
0x180164f4e  mov     edi, eax
0x180164f50  test    eax, eax
0x180164f52  jz      short loc_180164F72
0x180164f54  mov     rcx, [rsp+308h+var_2C8]
0x180164f59  test    rcx, rcx
0x180164f5c  jz      short loc_180164F6D
0x180164f5e  mov     rax, [rcx]
0x180164f61  mov     edx, r12d
0x180164f64  mov     rax, [rax]
0x180164f67  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180164f6c  nop
0x180164f6d  jmp     loc_180165BFF
0x180164f72  lea     r8, [rsi+78h]; void *
0x180164f76  cmp     [r8+4], r12b
0x180164f7a  jnz     short loc_180164FAF
0x180164f7c  lea     rdx, aAccountsLimitl; "Accounts_LimitLocalAccountUseOfBlankPas"...
0x180164f83  mov     rcx, r14; this
0x180164f86  call    ?InsertDataForNode@WmiRequestHandlerAdd@@QEAA?AW4_MI_Result@@PEBGPEAX@Z; WmiRequestHandlerAdd::InsertDataForNode(ushort const *,void *)
0x180164f8b  mov     edi, eax
0x180164f8d  test    eax, eax
0x180164f8f  jz      short loc_180164FAF
0x180164f91  mov     rcx, [rsp+308h+var_2C8]
0x180164f96  test    rcx, rcx
0x180164f99  jz      short loc_180164FAA
0x180164f9b  mov     rax, [rcx]
0x180164f9e  mov     edx, r12d
0x180164fa1  mov     rax, [rax]
0x180164fa4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180164fa9  nop
0x180164faa  jmp     loc_180165BFF
0x180164faf  lea     r8, [rsi+80h]; void *
0x180164fb6  cmp     [r8+8], r12b
0x180164fba  jnz     short loc_180164FEF
0x180164fbc  lea     rdx, aAccountsRename_0; "Accounts_RenameAdministratorAccount"
0x180164fc3  mov     rcx, r14; this
0x180164fc6  call    ?InsertDataForNode@WmiRequestHandlerAdd@@QEAA?AW4_MI_Result@@PEBGPEAX@Z; WmiRequestHandlerAdd::InsertDataForNode(ushort const *,void *)
0x180164fcb  mov     edi, eax
0x180164fcd  test    eax, eax
0x180164fcf  jz      short loc_180164FEF
0x180164fd1  mov     rcx, [rsp+308h+var_2C8]
0x180164fd6  test    rcx, rcx
0x180164fd9  jz      short loc_180164FEA
0x180164fdb  mov     rax, [rcx]
0x180164fde  mov     edx, r12d
0x180164fe1  mov     rax, [rax]
0x180164fe4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180164fe9  nop
0x180164fea  jmp     loc_180165BFF
0x180164fef  lea     r8, [rsi+90h]; void *
0x180164ff6  cmp     [r8+8], r12b
0x180164ffa  jnz     short loc_18016502F
0x180164ffc  lea     rdx, aAccountsRename; "Accounts_RenameGuestAccount"
0x180165003  mov     rcx, r14; this
0x180165006  call    ?InsertDataForNode@WmiRequestHandlerAdd@@QEAA?AW4_MI_Result@@PEBGPEAX@Z; WmiRequestHandlerAdd::InsertDataForNode(ushort const *,void *)
0x18016500b  mov     edi, eax
0x18016500d  test    eax, eax
0x18016500f  jz      short loc_18016502F
0x180165011  mov     rcx, [rsp+308h+var_2C8]
0x180165016  test    rcx, rcx
0x180165019  jz      short loc_18016502A
0x18016501b  mov     rax, [rcx]
0x18016501e  mov     edx, r12d
0x180165021  mov     rax, [rax]
0x180165024  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180165029  nop
0x18016502a  jmp     loc_180165BFF
0x18016502f  lea     r8, [rsi+0A0h]; void *
0x180165036  cmp     [r8+8], r12b
0x18016503a  jnz     short loc_18016506F
0x18016503c  lea     rdx, aDevicesAllowed; "Devices_AllowedToFormatAndEjectRemovabl"...
0x180165043  mov     rcx, r14; this
0x180165046  call    ?InsertDataForNode@WmiRequestHandlerAdd@@QEAA?AW4_MI_Result@@PEBGPEAX@Z; WmiRequestHandlerAdd::InsertDataForNode(ushort const *,void *)
0x18016504b  mov     edi, eax
0x18016504d  test    eax, eax
0x18016504f  jz      short loc_18016506F
0x180165051  mov     rcx, [rsp+308h+var_2C8]
0x180165056  test    rcx, rcx
0x180165059  jz      short loc_18016506A
0x18016505b  mov     rax, [rcx]
0x18016505e  mov     edx, r12d
0x180165061  mov     rax, [rax]
0x180165064  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180165069  nop
0x18016506a  jmp     loc_180165BFF
0x18016506f  lea     r8, [rsi+0B0h]; void *
0x180165076  cmp     [r8+4], r12b
0x18016507a  jnz     short loc_1801650AF
0x18016507c  lea     rdx, aDevicesAllowun; "Devices_AllowUndockWithoutHavingToLogon"
0x180165083  mov     rcx, r14; this
0x180165086  call    ?InsertDataForNode@WmiRequestHandlerAdd@@QEAA?AW4_MI_Result@@PEBGPEAX@Z; WmiRequestHandlerAdd::InsertDataForNode(ushort const *,void *)
0x18016508b  mov     edi, eax
0x18016508d  test    eax, eax
0x18016508f  jz      short loc_1801650AF
0x180165091  mov     rcx, [rsp+308h+var_2C8]
0x180165096  test    rcx, rcx
0x180165099  jz      short loc_1801650AA
0x18016509b  mov     rax, [rcx]
0x18016509e  mov     edx, r12d
0x1801650a1  mov     rax, [rax]
0x1801650a4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801650a9  nop
0x1801650aa  jmp     loc_180165BFF
0x1801650af  lea     r8, [rsi+0B8h]; void *
0x1801650b6  cmp     [r8+4], r12b
0x1801650ba  jnz     short loc_1801650EF
0x1801650bc  lea     rdx, aDevicesPrevent; "Devices_PreventUsersFromInstallingPrint"...
0x1801650c3  mov     rcx, r14; this
0x1801650c6  call    ?InsertDataForNode@WmiRequestHandlerAdd@@QEAA?AW4_MI_Result@@PEBGPEAX@Z; WmiRequestHandlerAdd::InsertDataForNode(ushort const *,void *)
0x1801650cb  mov     edi, eax
0x1801650cd  test    eax, eax
0x1801650cf  jz      short loc_1801650EF
0x1801650d1  mov     rcx, [rsp+308h+var_2C8]
0x1801650d6  test    rcx, rcx
0x1801650d9  jz      short loc_1801650EA
0x1801650db  mov     rax, [rcx]
0x1801650de  mov     edx, r12d
0x1801650e1  mov     rax, [rax]
0x1801650e4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801650e9  nop
0x1801650ea  jmp     loc_180165BFF
0x1801650ef  lea     r8, [rsi+0C0h]; void *
0x1801650f6  cmp     [r8+8], r12b
0x1801650fa  jnz     short loc_18016512F
0x1801650fc  lea     rdx, aDevicesRestric; "Devices_RestrictCDROMAccessToLocallyLog"...
0x180165103  mov     rcx, r14; this
0x180165106  call    ?InsertDataForNode@WmiRequestHandlerAdd@@QEAA?AW4_MI_Result@@PEBGPEAX@Z; WmiRequestHandlerAdd::InsertDataForNode(ushort const *,void *)
0x18016510b  mov     edi, eax
0x18016510d  test    eax, eax
0x18016510f  jz      short loc_18016512F
0x180165111  mov     rcx, [rsp+308h+var_2C8]
0x180165116  test    rcx, rcx
0x180165119  jz      short loc_18016512A
0x18016511b  mov     rax, [rcx]
0x18016511e  mov     edx, r12d
0x180165121  mov     rax, [rax]
0x180165124  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180165129  nop
0x18016512a  jmp     loc_180165BFF
0x18016512f  lea     r8, [rsi+0D0h]; void *
0x180165136  cmp     [r8+4], r12b
0x18016513a  jnz     short loc_18016516F
0x18016513c  lea     rdx, aInteractivelog; "InteractiveLogon_DisplayUserInformation"...
0x180165143  mov     rcx, r14; this
0x180165146  call    ?InsertDataForNode@WmiRequestHandlerAdd@@QEAA?AW4_MI_Result@@PEBGPEAX@Z; WmiRequestHandlerAdd::InsertDataForNode(ushort const *,void *)
0x18016514b  mov     edi, eax
0x18016514d  test    eax, eax
0x18016514f  jz      short loc_18016516F
0x180165151  mov     rcx, [rsp+308h+var_2C8]
0x180165156  test    rcx, rcx
0x180165159  jz      short loc_18016516A
0x18016515b  mov     rax, [rcx]
0x18016515e  mov     edx, r12d
0x180165161  mov     rax, [rax]
0x180165164  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180165169  nop
0x18016516a  jmp     loc_180165BFF
0x18016516f  lea     r8, [rsi+0D8h]; void *
0x180165176  cmp     [r8+4], r12b
0x18016517a  jnz     short loc_1801651AF
0x18016517c  lea     rdx, aInteractivelog_5; "InteractiveLogon_DoNotDisplayLastSigned"...
0x180165183  mov     rcx, r14; this
0x180165186  call    ?InsertDataForNode@WmiRequestHandlerAdd@@QEAA?AW4_MI_Result@@PEBGPEAX@Z; WmiRequestHandlerAdd::InsertDataForNode(ushort const *,void *)
0x18016518b  mov     edi, eax
0x18016518d  test    eax, eax
0x18016518f  jz      short loc_1801651AF
0x180165191  mov     rcx, [rsp+308h+var_2C8]
0x180165196  test    rcx, rcx
0x180165199  jz      short loc_1801651AA
0x18016519b  mov     rax, [rcx]
  ... truncated ...
```
