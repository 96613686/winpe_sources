# MDM_Policy_Config01_LocalPoliciesSecurityOptions02_InvokeModifyInstance

- ea: `0x1800b0658`
- end: `0x1800b152b`
- name: `MDM_Policy_Config01_LocalPoliciesSecurityOptions02_InvokeModifyInstance`
- size: `3795`
- prototype: ``
- caller_count: `1`
- callee_count: `12`
- tags: `registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x1800b1540`

## callees

- `0x180001008`
- `0x18000104c`
- `0x180003a5c`
- `0x18000a280`
- `0x1800b0658`
- `0x180240078`
- `0x180241ce0`
- `0x180243010`
- `0x180246310`
- `0x180246418`
- `0x18024d160`
- `0x18024f010`

## string_xrefs

- `0x1800b08e6`: `Accounts_RenameAdministratorAccount`
- `0x1800b0926`: `Accounts_RenameGuestAccount`
- `0x1800b09e6`: `Devices_PreventUsersFromInstallingPrinterDriversWhenConnectingToSharedPrinters`
- `0x1800b0a26`: `Devices_RestrictCDROMAccessToLocallyLoggedOnUserOnly`
- `0x1800b0ba6`: `InteractiveLogon_MessageTextForUsersAttemptingToLogOn`
- `0x1800b0be6`: `InteractiveLogon_MessageTitleForUsersAttemptingToLogOn`
- `0x1800b0c66`: `MicrosoftNetworkClient_DigitallySignCommunicationsAlways`
- `0x1800b0ca6`: `MicrosoftNetworkClient_DigitallySignCommunicationsIfServerAgrees`
- `0x1800b0d26`: `MicrosoftNetworkServer_DigitallySignCommunicationsAlways`
- `0x1800b0d66`: `MicrosoftNetworkServer_DigitallySignCommunicationsIfClientAgrees`
- `0x1800b0da6`: `NetworkAccess_DoNotAllowAnonymousEnumerationOfSAMAccounts`
- `0x1800b0de6`: `NetworkAccess_DoNotAllowAnonymousEnumerationOfSamAccountsAndShares`
- `0x1800b0e26`: `NetworkAccess_RestrictAnonymousAccessToNamedPipesAndShares`
- `0x1800b0e66`: `NetworkAccess_RestrictClientsAllowedToMakeRemoteCallsToSAM`
- `0x1800b0ea6`: `NetworkSecurity_AllowLocalSystemToUseComputerIdentityForNTLM`
- `0x1800b0ee6`: `NetworkSecurity_AllowPKU2UAuthenticationRequests`
- `0x1800b0f26`: `NetworkSecurity_DoNotStoreLANManagerHashValueOnNextPasswordChange`
- `0x1800b0f66`: `NetworkSecurity_LANManagerAuthenticationLevel`
- `0x1800b0fa6`: `NetworkSecurity_MinimumSessionSecurityForNTLMSSPBasedClients`
- `0x1800b0fe6`: `NetworkSecurity_MinimumSessionSecurityForNTLMSSPBasedServers`
- `0x1800b1026`: `NetworkSecurity_RestrictNTLM_AddRemoteServerExceptionsForNTLMAuthentication`
- `0x1800b1066`: `NetworkSecurity_RestrictNTLM_AuditIncomingNTLMTraffic`
- `0x1800b10a6`: `NetworkSecurity_RestrictNTLM_IncomingNTLMTraffic`
- `0x1800b10e6`: `NetworkSecurity_RestrictNTLM_OutgoingNTLMTrafficToRemoteServers`
- `0x1800b11a6`: `UserAccountControl_AllowUIAccessApplicationsToPromptForElevation`
- `0x1800b1266`: `UserAccountControl_DetectApplicationInstallationsAndPromptForElevation`
- `0x1800b12e6`: `UserAccountControl_OnlyElevateUIAccessApplicationsThatAreInstalledInSecureLocations`
- `0x1800b13e6`: `UserAccountControl_VirtualizeFileAndRegistryWriteFailuresToPerUserLocations`
- `0x1800b06a3`: `MDM_Policy_Config01_LocalPoliciesSecurityOptions02`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall MDM_Policy_Config01_LocalPoliciesSecurityOptions02_InvokeModifyInstance(__int64 a1, __int64 a2)
{
  _DWORD *v4; // r9
  wil *v5; // rcx
  unsigned int inserted; // edi
  WmiRequestHandler *v7; // r14
  const char *v9; // rax
  int v10; // eax
  WmiRequestHandler *v11; // [rsp+40h] [rbp-88h] BYREF
  _QWORD v12[3]; // [rsp+48h] [rbp-80h] BYREF
  const exception *v13[2]; // [rsp+60h] [rbp-68h] BYREF
  char v14; // [rsp+70h] [rbp-58h]
  int v15; // [rsp+78h] [rbp-50h] BYREF
  char v16; // [rsp+7Ch] [rbp-4Ch]
  _BYTE v17[16]; // [rsp+80h] [rbp-48h] BYREF
  _DWORD v18[4]; // [rsp+90h] [rbp-38h] BYREF

  v15 = 0;
  v16 = 0;
  v12[0] = &TelemetryEventWriter::`vftable';
  v12[1] = &v15;
  v12[2] = "MDM_Policy_Config01_LocalPoliciesSecurityOptions02";
  _TlgActivityBase<TraceLoggingActivity<&_tlgProvider_t const * const g_hTraceLoggingProvider,35184372088832,5,_TlgReflectorTag_Param0IsHProvider>,35184372088832,5>::zInternalStart(&v15);
  if ( (unsigned int)dword_180380B68 > 5 && (unsigned __int8)tlgKeywordOn(&dword_180380B68, 0x200000000000LL) )
  {
    if ( v16 && (v18[0] || v18[1] || v18[2] || v18[3]) )
      v4 = v18;
    else
      v4 = 0;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(
      &dword_180380B68,
      word_18034AA22,
      v17,
      v4);
  }
  if ( *(_BYTE *)(a2 + 72) && *(_BYTE *)(a2 + 88) )
  {
    TelemetryEventWriter::WriteStart(
      (TelemetryEventWriter *)v12,
      "ModifyInstanceStart",
      *(const unsigned __int16 **)(a2 + 80),
      *(const unsigned __int16 **)(a2 + 64));
    try
    {
      v11 = 0;
      inserted = CreateRequestHandlerInstance(
                   a1,
                   *(wchar_t **)(a2 + 80),
                   *(const unsigned __int16 **)(a2 + 64),
                   (struct WmiNodeInfo *)&MDM_Policy_Config01_LocalPoliciesSecurityOptions02_NodeList,
                   0x33u,
                   3,
                   &v11);
      if ( !inserted )
      {
        v13[1] = (const exception *)&v11;
        v14 = 1;
        v7 = v11;
        if ( v11 )
        {
          WmiRequestHandler::SetRequestMIInstance(
            v11,
            (const struct _MI_Instance *)a2,
            (struct WmiNodeInfo *)&MDM_Policy_Config01_LocalPoliciesSecurityOptions02_NodeList,
            0x33u);
          if ( *(_BYTE *)(a2 + 100) == 1
            && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                             v7,
                             L"Accounts_BlockMicrosoftAccounts",
                             (LONG *)(a2 + 96))) != 0 )
          {
            v5 = v11;
            if ( v11 )
              (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v11)(v11, 1);
          }
          else if ( *(_BYTE *)(a2 + 108) == 1
                 && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                  v7,
                                  L"Accounts_EnableAdministratorAccountStatus",
                                  (LONG *)(a2 + 104))) != 0 )
          {
            v5 = v11;
            if ( v11 )
              (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v11)(v11, 1);
          }
          else if ( *(_BYTE *)(a2 + 116) == 1
                 && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                  v7,
                                  L"Accounts_EnableGuestAccountStatus",
                                  (LONG *)(a2 + 112))) != 0 )
          {
            v5 = v11;
            if ( v11 )
              (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v11)(v11, 1);
          }
          else if ( *(_BYTE *)(a2 + 124) == 1
                 && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                  v7,
                                  L"Accounts_LimitLocalAccountUseOfBlankPasswordsToConsoleLogonOnly",
                                  (LONG *)(a2 + 120))) != 0 )
          {
            v5 = v11;
            if ( v11 )
              (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v11)(v11, 1);
          }
          else if ( *(_BYTE *)(a2 + 136) == 1
                 && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                  v7,
                                  L"Accounts_RenameAdministratorAccount",
                                  (LONG *)(a2 + 128))) != 0 )
          {
            v5 = v11;
            if ( v11 )
              (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v11)(v11, 1);
          }
          else if ( *(_BYTE *)(a2 + 152) == 1
                 && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                  v7,
                                  L"Accounts_RenameGuestAccount",
                                  (LONG *)(a2 + 144))) != 0 )
          {
            v5 = v11;
            if ( v11 )
              (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v11)(v11, 1);
          }
          else if ( *(_BYTE *)(a2 + 168) == 1
                 && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                  v7,
                                  L"Devices_AllowedToFormatAndEjectRemovableMedia",
                                  (LONG *)(a2 + 160))) != 0 )
          {
            v5 = v11;
            if ( v11 )
              (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v11)(v11, 1);
          }
          else if ( *(_BYTE *)(a2 + 180) == 1
                 && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                  v7,
                                  L"Devices_AllowUndockWithoutHavingToLogon",
                                  (LONG *)(a2 + 176))) != 0 )
          {
            v5 = v11;
            if ( v11 )
              (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v11)(v11, 1);
          }
          else if ( *(_BYTE *)(a2 + 188) == 1
                 && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                  v7,
                                  L"Devices_PreventUsersFromInstallingPrinterDriversWhenConnectingToSharedPrinters",
                                  (LONG *)(a2 + 184))) != 0 )
          {
            v5 = v11;
            if ( v11 )
              (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v11)(v11, 1);
          }
          else if ( *(_BYTE *)(a2 + 200) == 1
                 && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                  v7,
                                  L"Devices_RestrictCDROMAccessToLocallyLoggedOnUserOnly",
                                  (LONG *)(a2 + 192))) != 0 )
          {
            v5 = v11;
            if ( v11 )
              (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v11)(v11, 1);
          }
          else if ( *(_BYTE *)(a2 + 212) == 1
                 && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                  v7,
                                  L"InteractiveLogon_DisplayUserInformationWhenTheSessionIsLocked",
                                  (LONG *)(a2 + 208))) != 0 )
          {
            v5 = v11;
            if ( v11 )
              (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v11)(v11, 1);
          }
          else if ( *(_BYTE *)(a2 + 220) == 1
                 && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                  v7,
                                  L"InteractiveLogon_DoNotDisplayLastSignedIn",
                                  (LONG *)(a2 + 216))) != 0 )
          {
            v5 = v11;
            if ( v11 )
              (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v11)(v11, 1);
          }
          else if ( *(_BYTE *)(a2 + 228) == 1
                 && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                  v7,
                                  L"InteractiveLogon_DoNotDisplayUsernameAtSignIn",
                                  (LONG *)(a2 + 224))) != 0 )
          {
            v5 = v11;
            if ( v11 )
              (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v11)(v11, 1);
          }
          else if ( *(_BYTE *)(a2 + 236) == 1
                 && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                  v7,
                                  L"InteractiveLogon_DoNotRequireCTRLALTDEL",
                                  (LONG *)(a2 + 232))) != 0 )
          {
            v5 = v11;
            if ( v11 )
              (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v11)(v11, 1);
          }
          else if ( *(_BYTE *)(a2 + 244) == 1
                 && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                  v7,
                                  L"InteractiveLogon_MachineInactivityLimit",
                                  (LONG *)(a2 + 240))) != 0 )
          {
            v5 = v11;
            if ( v11 )
              (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v11)(v11, 1);
          }
          else if ( *(_BYTE *)(a2 + 256) == 1
                 && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                  v7,
                                  L"InteractiveLogon_MessageTextForUsersAttemptingToLogOn",
                                  (LONG *)(a2 + 248))) != 0 )
          {
            v5 = v11;
            if ( v11 )
              (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v11)(v11, 1);
          }
          else if ( *(_BYTE *)(a2 + 272) == 1
                 && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                  v7,
                                  L"InteractiveLogon_MessageTitleForUsersAttemptingToLogOn",
                                  (LONG *)(a2 + 264))) != 0 )
          {
            v5 = v11;
            if ( v11 )
              (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v11)(v11, 1);
          }
          else if ( *(_BYTE *)(a2 + 288) == 1
                 && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                  v7,
                                  L"InteractiveLogon_SmartCardRemovalBehavior",
                                  (LONG *)(a2 + 280))) != 0 )
          {
            v5 = v11;
            if ( v11 )
              (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v11)(v11, 1);
          }
          else if ( *(_BYTE *)(a2 + 300) == 1
                 && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                  v7,
                                  L"MicrosoftNetworkClient_DigitallySignCommunicationsAlways",
                                  (LONG *)(a2 + 296))) != 0 )
          {
            v5 = v11;
            if ( v11 )
              (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v11)(v11, 1);
          }
          else if ( *(_BYTE *)(a2 + 308) == 1
                 && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                  v7,
                                  L"MicrosoftNetworkClient_DigitallySignCommunicationsIfServerAgrees",
                                  (LONG *)(a2 + 304))) != 0 )
          {
            v5 = v11;
            if ( v11 )
              (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v11)(v11, 1);
          }
          else if ( *(_BYTE *)(a2 + 316) == 1
                 && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                  v7,
                                  L"MicrosoftNetworkClient_SendUnencryptedPasswordToThirdPartySMBServers",
                                  (LONG *)(a2 + 312))) != 0 )
          {
            v5 = v11;
            if ( v11 )
              (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v11)(v11, 1);
          }
          else if ( *(_BYTE *)(a2 + 324) == 1
                 && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                  v7,
                                  L"MicrosoftNetworkServer_DigitallySignCommunicationsAlways",
                                  (LONG *)(a2 + 320))) != 0 )
          {
            v5 = v11;
            if ( v11 )
              (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v11)(v11, 1);
          }
          else if ( *(_BYTE *)(a2 + 332) == 1
                 && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                  v7,
                                  L"MicrosoftNetworkServer_DigitallySignCommunicationsIfClientAgrees",
                                  (LONG *)(a2 + 328))) != 0 )
          {
            v5 = v11;
            if ( v11 )
              (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v11)(v11, 1);
          }
          else if ( *(_BYTE *)(a2 + 340) == 1
                 && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                  v7,
                                  L"NetworkAccess_DoNotAllowAnonymousEnumerationOfSAMAccounts",
                                  (LONG *)(a2 + 336))) != 0 )
          {
            v5 = v11;
            if ( v11 )
              (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v11)(v11, 1);
          }
          else if ( *(_BYTE *)(a2 + 348) == 1
                 && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                  v7,
                                  L"NetworkAccess_DoNotAllowAnonymousEnumerationOfSamAccountsAndShares",
                                  (LONG *)(a2 + 344))) != 0 )
          {
            v5 = v11;
            if ( v11 )
              (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v11)(v11, 1);
          }
          else if ( *(_BYTE *)(a2 + 356) == 1
                 && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                  v7,
                                  L"NetworkAccess_RestrictAnonymousAccessToNamedPipesAndShares",
                                  (LONG *)(a2 + 352))) != 0 )
          {
            v5 = v11;
            if ( v11 )
              (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v11)(v11, 1);
          }
          else if ( *(_BYTE *)(a2 + 368) == 1
                 && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                  v7,
                                  L"NetworkAccess_RestrictClientsAllowedToMakeRemoteCallsToSAM",
                                  (LONG *)(a2 + 360))) != 0 )
          {
            v5 = v11;
            if ( v11 )
              (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v11)(v11, 1);
          }
          else if ( *(_BYTE *)(a2 + 380) == 1
                 && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                  v7,
                                  L"NetworkSecurity_AllowLocalSystemToUseComputerIdentityForNTLM",
                                  (LONG *)(a2 + 376))) != 0 )
          {
            v5 = v11;
            if ( v11 )
              (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v11)(v11, 1);
          }
          else if ( *(_BYTE *)(a2 + 388) == 1
                 && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                  v7,
                                  L"NetworkSecurity_AllowPKU2UAuthenticationRequests",
                                  (LONG *)(a2 + 384))) != 0 )
          {
            v5 = v11;
            if ( v11 )
              (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v11)(v11, 1);
          }
          else if ( *(_BYTE *)(a2 + 396) == 1
                 && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                  v7,
                                  L"NetworkSecurity_DoNotStoreLANManagerHashValueOnNextPasswordChange",
                                  (LONG *)(a2 + 392))) != 0 )
          {
            v5 = v11;
            if ( v11 )
              (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v11)(v11, 1);
          }
          else if ( *(_BYTE *)(a2 + 404) == 1
                 && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                  v7,
                                  L"NetworkSecurity_LANManagerAuthenticationLevel",
                                  (LONG *)(a2 + 400))) != 0 )
          {
            v5 = v11;
            if ( v11 )
              (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v11)(v11, 1);
          }
          else if ( *(_BYTE *)(a2 + 412) == 1
                 && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                  v7,
                                  L"NetworkSecurity_MinimumSessionSecurityForNTLMSSPBasedClients",
                                  (LONG *)(a2 + 408))) != 0 )
          {
            v5 = v11;
            if ( v11 )
              (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v11)(v11, 1);
          }
          else if ( *(_BYTE *)(a2 + 420) == 1
                 && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                  v7,
                                  L"NetworkSecurity_MinimumSessionSecurityForNTLMSSPBasedServers",
                                  (LONG *)(a2 + 416))) != 0 )
          {
            v5 = v11;
            if ( v11 )
              (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v11)(v11, 1);
          }
          else if ( *(_BYTE *)(a2 + 432) == 1
                 && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                  v7,
                                  L"NetworkSecurity_RestrictNTLM_AddRemoteServerExceptionsForNTLMAuthentication",
                                  (LONG *)(a2 + 424))) != 0 )
          {
            v5 = v11;
            if ( v11 )
              (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v11)(v11, 1);
          }
          else if ( *(_BYTE *)(a2 + 444) == 1
                 && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                  v7,
                                  L"NetworkSecurity_RestrictNTLM_AuditIncomingNTLMTraffic",
                                  (LONG *)(a2 + 440))) != 0 )
          {
            v5 = v11;
            if ( v11 )
              (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v11)(v11, 1);
          }
          else if ( *(_BYTE *)(a2 + 452) == 1
                 && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                  v7,
                                  L"NetworkSecurity_RestrictNTLM_IncomingNTLMTraffic",
                                  (LONG *)(a2 + 448))) != 0 )
          {
            v5 = v11;
            if ( v11 )
              (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v11)(v11, 1);
          }
          else if ( *(_BYTE *)(a2 + 460) == 1
                 && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                  v7,
                                  L"NetworkSecurity_RestrictNTLM_OutgoingNTLMTrafficToRemoteServers",
                                  (LONG *)(a2 + 456))) != 0 )
          {
            v5 = v11;
            if ( v11 )
              (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v11)(v11, 1);
          }
          else if ( *(_BYTE *)(a2 + 468) == 1
                 && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                  v7,
                                  L"Shutdown_AllowSystemToBeShutDownWithoutHavingToLogOn",
                                  (LONG *)(a2 + 464))) != 0 )
          {
            v5 = v11;
            if ( v11 )
              (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v11)(v11, 1);
          }
          else if ( *(_BYTE *)(a2 + 476) == 1
                 && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                  v7,
                                  L"Shutdown_ClearVirtualMemoryPageFile",
                                  (LONG *)(a2 + 472))) != 0 )
          {
            v5 = v11;
            if ( v11 )
              (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v11)(v11, 1);
          }
          else if ( *(_BYTE *)(a2 + 484) == 1
                 && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                  v7,
                                  L"UserAccountControl_AllowUIAccessApplicationsToPromptForElevation",
                                  (LONG *)(a2 + 480))) != 0 )
          {
            v5 = v11;
            if ( v11 )
              (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v11)(v11, 1);
          }
          else if ( *(_BYTE *)(a2 + 492) == 1
                 && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                  v7,
                                  L"UserAccountControl_BehaviorOfTheElevationPromptForAdministrators",
                                  (LONG *)(a2 + 488))) != 0 )
          {
            v5 = v11;
            if ( v11 )
              (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v11)(v11, 1);
          }
          else if ( *(_BYTE *)(a2 + 500) == 1
                 && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                  v7,
                                  L"UserAccountControl_BehaviorOfTheElevationPromptForStandardUsers",
                                  (LONG *)(a2 + 496))) != 0 )
          {
            v5 = v11;
            if ( v11 )
              (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v11)(v11, 1);
          }
          else if ( *(_BYTE *)(a2 + 508) == 1
                 && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                  v7,
                                  L"UserAccountControl_DetectApplicationInstallationsAndPromptForElevation",
                                  (LONG *)(a2 + 504))) != 0 )
          {
            v5 = v11;
            if ( v11 )
              (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v11)(v11, 1);
          }
          else if ( *(_BYTE *)(a2 + 516) == 1
                 && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                  v7,
                                  L"UserAccountControl_OnlyElevateExecutableFilesThatAreSignedAndValidated",
                                  (LONG *)(a2 + 512))) != 0 )
          {
            v5 = v11;
            if ( v11 )
              (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v11)(v11, 1);
          }
          else if ( *(_BYTE *)(a2 + 524) == 1
                 && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                  v7,
                                  L"UserAccountControl_OnlyElevateUIAccessApplicationsThatAreInstalledInSecureLocations",
                                  (LONG *)(a2 + 520))) != 0 )
          {
            v5 = v11;
            if ( v11 )
              (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v11)(v11, 1);
          }
          else if ( *(_BYTE *)(a2 + 532) == 1
                 && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                  v7,
                                  L"UserAccountControl_RunAllAdministratorsInAdminApprovalMode",
                                  (LONG *)(a2 + 528))) != 0 )
          {
            v5 = v11;
            if ( v11 )
              (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v11)(v11, 1);
          }
          else if ( *(_BYTE *)(a2 + 540) == 1
                 && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                  v7,
                                  L"UserAccountControl_SwitchToTheSecureDesktopWhenPromptingForElevation",
                                  (LONG *)(a2 + 536))) != 0 )
          {
            v5 = v11;
            if ( v11 )
              (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v11)(v11, 1);
          }
          else if ( *(_BYTE *)(a2 + 548) == 1
                 && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                  v7,
                                  L"UserAccountControl_UseAdminApprovalMode",
                                  (LONG *)(a2 + 544))) != 0 )
          {
            v5 = v11;
            if ( v11 )
              (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v11)(v11, 1);
          }
          else if ( *(_BYTE *)(a2 + 556) == 1
                 && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                  v7,
                                  L"UserAccountControl_VirtualizeFileAndRegistryWriteFailuresToPerUserLocations",
                                  (LONG *)(a2 + 552))) != 0 )
          {
            v5 = v11;
            if ( v11 )
              (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v11)(v11, 1);
          }
          else
          {
            inserted = (*(__int64 (__fastcall **)(WmiRequestHandler *))(*(_QWORD *)v7 + 16LL))(v7);
            if ( inserted )
            {
              v5 = v11;
              if ( v11 )
                (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v11)(v11, 1);
            }
            else
            {
              inserted = (*(__int64 (__fastcall **)(WmiRequestHandler *))(*(_QWORD *)v7 + 8LL))(v7);
              v5 = v11;
              if ( inserted )
              {
                if ( v11 )
                  (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v11)(v11, 1);
              }
              else if ( v11 )
              {
                (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v11)(v11, 1);
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
    catch ( const exception *v13 )
    {
      v9 = (const char *)(*(__int64 (__fastcall **)(const exception *))(*(_QWORD *)v13[0] + 8LL))(v13[0]);
      TelemetryEventWriter::WriteStdException((TelemetryEventWriter *)v12, v9);
      LODWORD(v11) = 1;
      inserted = 1;
    }
    catch ( ... )
    {
      v10 = wil::ResultFromCaughtException(v5);
      TelemetryEventWriter::WriteDefaultExceptionHr((TelemetryEventWriter *)v12, v10);
      LODWORD(v11) = 1;
      inserted = 1;
    }
  }
  else
  {
    inserted = 4;
  }
  TelemetryEventWriter::WriteEnd((TelemetryEventWriter *)v12, "ModifyInstanceEnd", inserted);
  v15 = 2;
  if ( (unsigned int)dword_180380B68 > 5 && (unsigned __int8)tlgKeywordOn(&dword_180380B68, 0x200000000000LL) )
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(
      &dword_180380B68,
      &byte_180345EA7,
      v17,
      0);
  _TlgActivityBase<TraceLoggingActivity<&_tlgProvider_t const * const g_hTraceLoggingProvider,35184372088832,5,_TlgReflectorTag_Param0IsHProvider>,35184372088832,5>::~_TlgActivityBase<TraceLoggingActivity<&_tlgProvider_t const * const g_hTraceLoggingProvider,35184372088832,5,_TlgReflectorTag_Param0IsHProvider>,35184372088832,5>(&v15);
  return inserted;
}

```

## disassembly

```asm
0x1800b0658  mov     r11, rsp
0x1800b065b  mov     [r11+18h], rsi
0x1800b065f  push    rdi
0x1800b0660  push    r14
0x1800b0662  push    r15
0x1800b0664  sub     rsp, 0B0h
0x1800b066b  mov     rax, cs:__security_cookie
0x1800b0672  xor     rax, rsp
0x1800b0675  mov     [rsp+0C8h+var_28], rax
0x1800b067d  mov     rsi, rdx
0x1800b0680  mov     rdi, rcx
0x1800b0683  mov     [rsp+0C8h+var_50], 0
0x1800b068b  mov     [rsp+0C8h+var_4C], 0
0x1800b0690  lea     rax, ??_7TelemetryEventWriter@@6B@; const TelemetryEventWriter::`vftable'
0x1800b0697  mov     [r11-80h], rax
0x1800b069b  lea     rax, [r11-50h]
0x1800b069f  mov     [r11-78h], rax
0x1800b06a3  lea     rax, aMdmPolicyConfi_55; "MDM_Policy_Config01_LocalPoliciesSecuri"...
0x1800b06aa  mov     [r11-70h], rax
0x1800b06ae  lea     rcx, [r11-50h]
0x1800b06b2  call    ?zInternalStart@?$_TlgActivityBase@V?$TraceLoggingActivity@$1?g_hTraceLoggingProvider@@3QEBU_tlgProvider_t@@EB$0CAAAAAAAAAAA@$04U_TlgReflectorTag_Param0IsHProvider@@@@$0CAAAAAAAAAAA@$04@@QEAAXXZ; _TlgActivityBase<TraceLoggingActivity<&_tlgProvider_t const * const g_hTraceLoggingProvider,35184372088832,5,_TlgReflectorTag_Param0IsHProvider>,35184372088832,5>::zInternalStart(void)
0x1800b06b7  mov     eax, cs:dword_180380B68
0x1800b06bd  cmp     eax, 5
0x1800b06c0  jbe     short loc_1800B0733
0x1800b06c2  mov     rdx, 200000000000h
0x1800b06cc  lea     rcx, dword_180380B68
0x1800b06d3  call    _tlgKeywordOn
0x1800b06d8  test    al, al
0x1800b06da  jz      short loc_1800B0733
0x1800b06dc  cmp     [rsp+0C8h+var_4C], 0
0x1800b06e1  jz      short loc_1800B0715
0x1800b06e3  cmp     [rsp+0C8h+var_38], 0
0x1800b06eb  jnz     short loc_1800B070B
0x1800b06ed  cmp     [rsp+0C8h+var_34], 0
0x1800b06f5  jnz     short loc_1800B070B
0x1800b06f7  cmp     [rsp+0C8h+var_30], 0
0x1800b06ff  jnz     short loc_1800B070B
0x1800b0701  cmp     [rsp+0C8h+var_2C], 0
0x1800b0709  jz      short loc_1800B0715
0x1800b070b  lea     r9, [rsp+0C8h+var_38]
0x1800b0713  jmp     short loc_1800B0718
0x1800b0715  xor     r9d, r9d
0x1800b0718  lea     r8, [rsp+0C8h+var_48]
0x1800b0720  lea     rdx, word_18034AA22
0x1800b0727  lea     rcx, dword_180380B68
0x1800b072e  call    ??$Write@$$V@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *)
0x1800b0733  cmp     byte ptr [rsi+48h], 0
0x1800b0737  jz      loc_1800B1495
0x1800b073d  cmp     byte ptr [rsi+58h], 0
0x1800b0741  jz      loc_1800B1495
0x1800b0747  mov     r9, [rsi+40h]; unsigned __int16 *
0x1800b074b  mov     r8, [rsi+50h]; unsigned __int16 *
0x1800b074f  lea     rdx, aModifyinstance; "ModifyInstanceStart"
0x1800b0756  lea     rcx, [rsp+0C8h+var_80]; this
0x1800b075b  call    ?WriteStart@TelemetryEventWriter@@QEAAXPEBDPEBG1@Z; TelemetryEventWriter::WriteStart(char const *,ushort const *,ushort const *)
0x1800b0760  nop
0x1800b0761  mov     [rsp+0C8h+var_88], 0
0x1800b076a  lea     rax, [rsp+0C8h+var_88]
0x1800b076f  mov     [rsp+0C8h+var_98], rax
0x1800b0774  mov     [rsp+0C8h+var_A0], 3
0x1800b077c  mov     [rsp+0C8h+var_A8], 33h ; '3'
0x1800b0784  lea     r9, ?MDM_Policy_Config01_LocalPoliciesSecurityOptions02_NodeList@@3PAUWmiNodeInfo@@A; WmiNodeInfo near * MDM_Policy_Config01_LocalPoliciesSecurityOptions02_NodeList
0x1800b078b  mov     r8, [rsi+40h]
0x1800b078f  mov     rdx, [rsi+50h]
0x1800b0793  mov     rcx, rdi
0x1800b0796  call    ?CreateRequestHandlerInstance@@YA?AW4_MI_Result@@PEAU_MI_Context@@PEBG1PEAUWmiNodeInfo@@KW4RequestType@@AEAPEAVWmiRequestHandler@@@Z; CreateRequestHandlerInstance(_MI_Context *,ushort const *,ushort const *,WmiNodeInfo *,ulong,RequestType,WmiRequestHandler * &)
0x1800b079b  mov     edi, eax
0x1800b079d  test    eax, eax
0x1800b079f  jz      short loc_1800B07A6
0x1800b07a1  jmp     loc_1800B149A
0x1800b07a6  lea     rax, [rsp+0C8h+var_88]
0x1800b07ab  mov     [rsp+0C8h+var_60], rax
0x1800b07b0  mov     r15d, 1
0x1800b07b6  mov     [rsp+0C8h+var_58], r15b
0x1800b07bb  mov     r14, [rsp+0C8h+var_88]
0x1800b07c0  test    r14, r14
0x1800b07c3  jnz     short loc_1800B07CD
0x1800b07c5  mov     edi, r15d
0x1800b07c8  jmp     loc_1800B149A
0x1800b07cd  mov     r9d, 33h ; '3'; unsigned int
0x1800b07d3  lea     r8, ?MDM_Policy_Config01_LocalPoliciesSecurityOptions02_NodeList@@3PAUWmiNodeInfo@@A; struct WmiNodeInfo *
0x1800b07da  mov     rdx, rsi; struct _MI_Instance *
0x1800b07dd  mov     rcx, r14; this
0x1800b07e0  call    ?SetRequestMIInstance@WmiRequestHandler@@QEAA?AW4_MI_Result@@PEBU_MI_Instance@@PEAUWmiNodeInfo@@K@Z; WmiRequestHandler::SetRequestMIInstance(_MI_Instance const *,WmiNodeInfo *,ulong)
0x1800b07e5  lea     r8, [rsi+60h]; void *
0x1800b07e9  cmp     [r8+4], r15b
0x1800b07ed  jnz     short loc_1800B0822
0x1800b07ef  lea     rdx, aAccountsBlockm; "Accounts_BlockMicrosoftAccounts"
0x1800b07f6  mov     rcx, r14; this
0x1800b07f9  call    ?InsertDataForNode@WmiRequestHandlerAdd@@QEAA?AW4_MI_Result@@PEBGPEAX@Z; WmiRequestHandlerAdd::InsertDataForNode(ushort const *,void *)
0x1800b07fe  mov     edi, eax
0x1800b0800  test    eax, eax
0x1800b0802  jz      short loc_1800B0822
0x1800b0804  mov     rcx, [rsp+0C8h+var_88]
0x1800b0809  test    rcx, rcx
0x1800b080c  jz      short loc_1800B081D
0x1800b080e  mov     rax, [rcx]
0x1800b0811  mov     edx, r15d
0x1800b0814  mov     rax, [rax]
0x1800b0817  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b081c  nop
0x1800b081d  jmp     loc_1800B149A
0x1800b0822  lea     r8, [rsi+68h]; void *
0x1800b0826  cmp     [r8+4], r15b
0x1800b082a  jnz     short loc_1800B085F
0x1800b082c  lea     rdx, aAccountsEnable_0; "Accounts_EnableAdministratorAccountStat"...
0x1800b0833  mov     rcx, r14; this
0x1800b0836  call    ?InsertDataForNode@WmiRequestHandlerAdd@@QEAA?AW4_MI_Result@@PEBGPEAX@Z; WmiRequestHandlerAdd::InsertDataForNode(ushort const *,void *)
0x1800b083b  mov     edi, eax
0x1800b083d  test    eax, eax
0x1800b083f  jz      short loc_1800B085F
0x1800b0841  mov     rcx, [rsp+0C8h+var_88]
0x1800b0846  test    rcx, rcx
0x1800b0849  jz      short loc_1800B085A
0x1800b084b  mov     rax, [rcx]
0x1800b084e  mov     edx, r15d
0x1800b0851  mov     rax, [rax]
0x1800b0854  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b0859  nop
0x1800b085a  jmp     loc_1800B149A
0x1800b085f  lea     r8, [rsi+70h]; void *
0x1800b0863  cmp     [r8+4], r15b
0x1800b0867  jnz     short loc_1800B089C
0x1800b0869  lea     rdx, aAccountsEnable; "Accounts_EnableGuestAccountStatus"
0x1800b0870  mov     rcx, r14; this
0x1800b0873  call    ?InsertDataForNode@WmiRequestHandlerAdd@@QEAA?AW4_MI_Result@@PEBGPEAX@Z; WmiRequestHandlerAdd::InsertDataForNode(ushort const *,void *)
0x1800b0878  mov     edi, eax
0x1800b087a  test    eax, eax
0x1800b087c  jz      short loc_1800B089C
0x1800b087e  mov     rcx, [rsp+0C8h+var_88]
0x1800b0883  test    rcx, rcx
0x1800b0886  jz      short loc_1800B0897
0x1800b0888  mov     rax, [rcx]
0x1800b088b  mov     edx, r15d
0x1800b088e  mov     rax, [rax]
0x1800b0891  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b0896  nop
0x1800b0897  jmp     loc_1800B149A
0x1800b089c  lea     r8, [rsi+78h]; void *
0x1800b08a0  cmp     [r8+4], r15b
0x1800b08a4  jnz     short loc_1800B08D9
0x1800b08a6  lea     rdx, aAccountsLimitl; "Accounts_LimitLocalAccountUseOfBlankPas"...
0x1800b08ad  mov     rcx, r14; this
0x1800b08b0  call    ?InsertDataForNode@WmiRequestHandlerAdd@@QEAA?AW4_MI_Result@@PEBGPEAX@Z; WmiRequestHandlerAdd::InsertDataForNode(ushort const *,void *)
0x1800b08b5  mov     edi, eax
0x1800b08b7  test    eax, eax
0x1800b08b9  jz      short loc_1800B08D9
0x1800b08bb  mov     rcx, [rsp+0C8h+var_88]
0x1800b08c0  test    rcx, rcx
0x1800b08c3  jz      short loc_1800B08D4
0x1800b08c5  mov     rax, [rcx]
0x1800b08c8  mov     edx, r15d
0x1800b08cb  mov     rax, [rax]
0x1800b08ce  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b08d3  nop
0x1800b08d4  jmp     loc_1800B149A
0x1800b08d9  lea     r8, [rsi+80h]; void *
0x1800b08e0  cmp     [r8+8], r15b
0x1800b08e4  jnz     short loc_1800B0919
0x1800b08e6  lea     rdx, aAccountsRename_0; "Accounts_RenameAdministratorAccount"
0x1800b08ed  mov     rcx, r14; this
0x1800b08f0  call    ?InsertDataForNode@WmiRequestHandlerAdd@@QEAA?AW4_MI_Result@@PEBGPEAX@Z; WmiRequestHandlerAdd::InsertDataForNode(ushort const *,void *)
0x1800b08f5  mov     edi, eax
0x1800b08f7  test    eax, eax
0x1800b08f9  jz      short loc_1800B0919
0x1800b08fb  mov     rcx, [rsp+0C8h+var_88]
0x1800b0900  test    rcx, rcx
0x1800b0903  jz      short loc_1800B0914
0x1800b0905  mov     rax, [rcx]
0x1800b0908  mov     edx, r15d
0x1800b090b  mov     rax, [rax]
0x1800b090e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b0913  nop
0x1800b0914  jmp     loc_1800B149A
0x1800b0919  lea     r8, [rsi+90h]; void *
0x1800b0920  cmp     [r8+8], r15b
0x1800b0924  jnz     short loc_1800B0959
0x1800b0926  lea     rdx, aAccountsRename; "Accounts_RenameGuestAccount"
0x1800b092d  mov     rcx, r14; this
0x1800b0930  call    ?InsertDataForNode@WmiRequestHandlerAdd@@QEAA?AW4_MI_Result@@PEBGPEAX@Z; WmiRequestHandlerAdd::InsertDataForNode(ushort const *,void *)
0x1800b0935  mov     edi, eax
0x1800b0937  test    eax, eax
0x1800b0939  jz      short loc_1800B0959
0x1800b093b  mov     rcx, [rsp+0C8h+var_88]
0x1800b0940  test    rcx, rcx
0x1800b0943  jz      short loc_1800B0954
0x1800b0945  mov     rax, [rcx]
0x1800b0948  mov     edx, r15d
0x1800b094b  mov     rax, [rax]
0x1800b094e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b0953  nop
0x1800b0954  jmp     loc_1800B149A
0x1800b0959  lea     r8, [rsi+0A0h]; void *
0x1800b0960  cmp     [r8+8], r15b
0x1800b0964  jnz     short loc_1800B0999
0x1800b0966  lea     rdx, aDevicesAllowed; "Devices_AllowedToFormatAndEjectRemovabl"...
0x1800b096d  mov     rcx, r14; this
0x1800b0970  call    ?InsertDataForNode@WmiRequestHandlerAdd@@QEAA?AW4_MI_Result@@PEBGPEAX@Z; WmiRequestHandlerAdd::InsertDataForNode(ushort const *,void *)
0x1800b0975  mov     edi, eax
0x1800b0977  test    eax, eax
0x1800b0979  jz      short loc_1800B0999
0x1800b097b  mov     rcx, [rsp+0C8h+var_88]
0x1800b0980  test    rcx, rcx
0x1800b0983  jz      short loc_1800B0994
0x1800b0985  mov     rax, [rcx]
0x1800b0988  mov     edx, r15d
0x1800b098b  mov     rax, [rax]
0x1800b098e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b0993  nop
0x1800b0994  jmp     loc_1800B149A
0x1800b0999  lea     r8, [rsi+0B0h]; void *
0x1800b09a0  cmp     [r8+4], r15b
0x1800b09a4  jnz     short loc_1800B09D9
0x1800b09a6  lea     rdx, aDevicesAllowun; "Devices_AllowUndockWithoutHavingToLogon"
0x1800b09ad  mov     rcx, r14; this
0x1800b09b0  call    ?InsertDataForNode@WmiRequestHandlerAdd@@QEAA?AW4_MI_Result@@PEBGPEAX@Z; WmiRequestHandlerAdd::InsertDataForNode(ushort const *,void *)
0x1800b09b5  mov     edi, eax
0x1800b09b7  test    eax, eax
0x1800b09b9  jz      short loc_1800B09D9
0x1800b09bb  mov     rcx, [rsp+0C8h+var_88]
0x1800b09c0  test    rcx, rcx
0x1800b09c3  jz      short loc_1800B09D4
0x1800b09c5  mov     rax, [rcx]
0x1800b09c8  mov     edx, r15d
0x1800b09cb  mov     rax, [rax]
0x1800b09ce  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b09d3  nop
0x1800b09d4  jmp     loc_1800B149A
0x1800b09d9  lea     r8, [rsi+0B8h]; void *
0x1800b09e0  cmp     [r8+4], r15b
0x1800b09e4  jnz     short loc_1800B0A19
0x1800b09e6  lea     rdx, aDevicesPrevent; "Devices_PreventUsersFromInstallingPrint"...
0x1800b09ed  mov     rcx, r14; this
0x1800b09f0  call    ?InsertDataForNode@WmiRequestHandlerAdd@@QEAA?AW4_MI_Result@@PEBGPEAX@Z; WmiRequestHandlerAdd::InsertDataForNode(ushort const *,void *)
0x1800b09f5  mov     edi, eax
0x1800b09f7  test    eax, eax
0x1800b09f9  jz      short loc_1800B0A19
0x1800b09fb  mov     rcx, [rsp+0C8h+var_88]
0x1800b0a00  test    rcx, rcx
0x1800b0a03  jz      short loc_1800B0A14
0x1800b0a05  mov     rax, [rcx]
0x1800b0a08  mov     edx, r15d
0x1800b0a0b  mov     rax, [rax]
0x1800b0a0e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b0a13  nop
0x1800b0a14  jmp     loc_1800B149A
0x1800b0a19  lea     r8, [rsi+0C0h]; void *
0x1800b0a20  cmp     [r8+8], r15b
0x1800b0a24  jnz     short loc_1800B0A59
0x1800b0a26  lea     rdx, aDevicesRestric; "Devices_RestrictCDROMAccessToLocallyLog"...
0x1800b0a2d  mov     rcx, r14; this
0x1800b0a30  call    ?InsertDataForNode@WmiRequestHandlerAdd@@QEAA?AW4_MI_Result@@PEBGPEAX@Z; WmiRequestHandlerAdd::InsertDataForNode(ushort const *,void *)
0x1800b0a35  mov     edi, eax
0x1800b0a37  test    eax, eax
0x1800b0a39  jz      short loc_1800B0A59
0x1800b0a3b  mov     rcx, [rsp+0C8h+var_88]
0x1800b0a40  test    rcx, rcx
0x1800b0a43  jz      short loc_1800B0A54
0x1800b0a45  mov     rax, [rcx]
0x1800b0a48  mov     edx, r15d
0x1800b0a4b  mov     rax, [rax]
0x1800b0a4e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b0a53  nop
0x1800b0a54  jmp     loc_1800B149A
0x1800b0a59  lea     r8, [rsi+0D0h]; void *
0x1800b0a60  cmp     [r8+4], r15b
0x1800b0a64  jnz     short loc_1800B0A99
0x1800b0a66  lea     rdx, aInteractivelog; "InteractiveLogon_DisplayUserInformation"...
0x1800b0a6d  mov     rcx, r14; this
0x1800b0a70  call    ?InsertDataForNode@WmiRequestHandlerAdd@@QEAA?AW4_MI_Result@@PEBGPEAX@Z; WmiRequestHandlerAdd::InsertDataForNode(ushort const *,void *)
0x1800b0a75  mov     edi, eax
0x1800b0a77  test    eax, eax
0x1800b0a79  jz      short loc_1800B0A99
0x1800b0a7b  mov     rcx, [rsp+0C8h+var_88]
0x1800b0a80  test    rcx, rcx
0x1800b0a83  jz      short loc_1800B0A94
0x1800b0a85  mov     rax, [rcx]
0x1800b0a88  mov     edx, r15d
0x1800b0a8b  mov     rax, [rax]
0x1800b0a8e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b0a93  nop
0x1800b0a94  jmp     loc_1800B149A
0x1800b0a99  lea     r8, [rsi+0D8h]; void *
0x1800b0aa0  cmp     [r8+4], r15b
0x1800b0aa4  jnz     short loc_1800B0AD9
0x1800b0aa6  lea     rdx, aInteractivelog_5; "InteractiveLogon_DoNotDisplayLastSigned"...
0x1800b0aad  mov     rcx, r14; this
0x1800b0ab0  call    ?InsertDataForNode@WmiRequestHandlerAdd@@QEAA?AW4_MI_Result@@PEBGPEAX@Z; WmiRequestHandlerAdd::InsertDataForNode(ushort const *,void *)
0x1800b0ab5  mov     edi, eax
0x1800b0ab7  test    eax, eax
0x1800b0ab9  jz      short loc_1800B0AD9
0x1800b0abb  mov     rcx, [rsp+0C8h+var_88]
0x1800b0ac0  test    rcx, rcx
0x1800b0ac3  jz      short loc_1800B0AD4
0x1800b0ac5  mov     rax, [rcx]
0x1800b0ac8  mov     edx, r15d
0x1800b0acb  mov     rax, [rax]
0x1800b0ace  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b0ad3  nop
0x1800b0ad4  jmp     loc_1800B149A
  ... truncated ...
```
