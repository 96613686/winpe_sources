# MDM_Policy_Config01_LocalPoliciesSecurityOptions02_InvokeModifyInstance

- ea: `0x1800afeac`
- end: `0x1800b0d80`
- name: `MDM_Policy_Config01_LocalPoliciesSecurityOptions02_InvokeModifyInstance`
- size: `3796`
- prototype: ``
- caller_count: `1`
- callee_count: `12`
- tags: `registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x1800b0d90`

## callees

- `0x180001008`
- `0x18000104c`
- `0x180003abc`
- `0x18000a768`
- `0x1800afeac`
- `0x18023f3ac`
- `0x180241010`
- `0x18024237c`
- `0x180245824`
- `0x180245930`
- `0x18024cd20`
- `0x18024f010`

## string_xrefs

- `0x1800b013a`: `Accounts_RenameAdministratorAccount`
- `0x1800b017a`: `Accounts_RenameGuestAccount`
- `0x1800b023a`: `Devices_PreventUsersFromInstallingPrinterDriversWhenConnectingToSharedPrinters`
- `0x1800b027a`: `Devices_RestrictCDROMAccessToLocallyLoggedOnUserOnly`
- `0x1800b03fa`: `InteractiveLogon_MessageTextForUsersAttemptingToLogOn`
- `0x1800b043a`: `InteractiveLogon_MessageTitleForUsersAttemptingToLogOn`
- `0x1800b04ba`: `MicrosoftNetworkClient_DigitallySignCommunicationsAlways`
- `0x1800b04fa`: `MicrosoftNetworkClient_DigitallySignCommunicationsIfServerAgrees`
- `0x1800b057a`: `MicrosoftNetworkServer_DigitallySignCommunicationsAlways`
- `0x1800b05ba`: `MicrosoftNetworkServer_DigitallySignCommunicationsIfClientAgrees`
- `0x1800b05fa`: `NetworkAccess_DoNotAllowAnonymousEnumerationOfSAMAccounts`
- `0x1800b063a`: `NetworkAccess_DoNotAllowAnonymousEnumerationOfSamAccountsAndShares`
- `0x1800b067a`: `NetworkAccess_RestrictAnonymousAccessToNamedPipesAndShares`
- `0x1800b06ba`: `NetworkAccess_RestrictClientsAllowedToMakeRemoteCallsToSAM`
- `0x1800b06fa`: `NetworkSecurity_AllowLocalSystemToUseComputerIdentityForNTLM`
- `0x1800b073a`: `NetworkSecurity_AllowPKU2UAuthenticationRequests`
- `0x1800b077a`: `NetworkSecurity_DoNotStoreLANManagerHashValueOnNextPasswordChange`
- `0x1800b07ba`: `NetworkSecurity_LANManagerAuthenticationLevel`
- `0x1800b07fa`: `NetworkSecurity_MinimumSessionSecurityForNTLMSSPBasedClients`
- `0x1800b083a`: `NetworkSecurity_MinimumSessionSecurityForNTLMSSPBasedServers`
- `0x1800b087a`: `NetworkSecurity_RestrictNTLM_AddRemoteServerExceptionsForNTLMAuthentication`
- `0x1800b08ba`: `NetworkSecurity_RestrictNTLM_AuditIncomingNTLMTraffic`
- `0x1800b08fa`: `NetworkSecurity_RestrictNTLM_IncomingNTLMTraffic`
- `0x1800b093a`: `NetworkSecurity_RestrictNTLM_OutgoingNTLMTrafficToRemoteServers`
- `0x1800b09fa`: `UserAccountControl_AllowUIAccessApplicationsToPromptForElevation`
- `0x1800b0aba`: `UserAccountControl_DetectApplicationInstallationsAndPromptForElevation`
- `0x1800b0b3a`: `UserAccountControl_OnlyElevateUIAccessApplicationsThatAreInstalledInSecureLocations`
- `0x1800b0c3a`: `UserAccountControl_VirtualizeFileAndRegistryWriteFailuresToPerUserLocations`
- `0x1800afef7`: `MDM_Policy_Config01_LocalPoliciesSecurityOptions02`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall MDM_Policy_Config01_LocalPoliciesSecurityOptions02_InvokeModifyInstance(__int64 a1, __int64 a2)
{
  _DWORD *v4; // r9
  wil *v5; // rcx
  enum _MI_Result inserted; // edi
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
      inserted = (unsigned int)CreateRequestHandlerInstance(
                                 a1,
                                 *(_QWORD *)(a2 + 80),
                                 *(_QWORD *)(a2 + 64),
                                 &MDM_Policy_Config01_LocalPoliciesSecurityOptions02_NodeList,
                                 51,
                                 3,
                                 &v11);
      if ( inserted == MI_RESULT_OK )
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
                             (void *)(a2 + 96))) != MI_RESULT_OK )
          {
            v5 = v11;
            if ( v11 )
              (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v11)(v11, 1);
          }
          else if ( *(_BYTE *)(a2 + 108) == 1
                 && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                  v7,
                                  L"Accounts_EnableAdministratorAccountStatus",
                                  (void *)(a2 + 104))) != MI_RESULT_OK )
          {
            v5 = v11;
            if ( v11 )
              (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v11)(v11, 1);
          }
          else if ( *(_BYTE *)(a2 + 116) == 1
                 && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                  v7,
                                  L"Accounts_EnableGuestAccountStatus",
                                  (void *)(a2 + 112))) != MI_RESULT_OK )
          {
            v5 = v11;
            if ( v11 )
              (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v11)(v11, 1);
          }
          else if ( *(_BYTE *)(a2 + 124) == 1
                 && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                  v7,
                                  L"Accounts_LimitLocalAccountUseOfBlankPasswordsToConsoleLogonOnly",
                                  (void *)(a2 + 120))) != MI_RESULT_OK )
          {
            v5 = v11;
            if ( v11 )
              (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v11)(v11, 1);
          }
          else if ( *(_BYTE *)(a2 + 136) == 1
                 && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                  v7,
                                  L"Accounts_RenameAdministratorAccount",
                                  (void *)(a2 + 128))) != MI_RESULT_OK )
          {
            v5 = v11;
            if ( v11 )
              (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v11)(v11, 1);
          }
          else if ( *(_BYTE *)(a2 + 152) == 1
                 && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                  v7,
                                  L"Accounts_RenameGuestAccount",
                                  (void *)(a2 + 144))) != MI_RESULT_OK )
          {
            v5 = v11;
            if ( v11 )
              (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v11)(v11, 1);
          }
          else if ( *(_BYTE *)(a2 + 168) == 1
                 && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                  v7,
                                  L"Devices_AllowedToFormatAndEjectRemovableMedia",
                                  (void *)(a2 + 160))) != MI_RESULT_OK )
          {
            v5 = v11;
            if ( v11 )
              (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v11)(v11, 1);
          }
          else if ( *(_BYTE *)(a2 + 180) == 1
                 && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                  v7,
                                  L"Devices_AllowUndockWithoutHavingToLogon",
                                  (void *)(a2 + 176))) != MI_RESULT_OK )
          {
            v5 = v11;
            if ( v11 )
              (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v11)(v11, 1);
          }
          else if ( *(_BYTE *)(a2 + 188) == 1
                 && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                  v7,
                                  L"Devices_PreventUsersFromInstallingPrinterDriversWhenConnectingToSharedPrinters",
                                  (void *)(a2 + 184))) != MI_RESULT_OK )
          {
            v5 = v11;
            if ( v11 )
              (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v11)(v11, 1);
          }
          else if ( *(_BYTE *)(a2 + 200) == 1
                 && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                  v7,
                                  L"Devices_RestrictCDROMAccessToLocallyLoggedOnUserOnly",
                                  (void *)(a2 + 192))) != MI_RESULT_OK )
          {
            v5 = v11;
            if ( v11 )
              (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v11)(v11, 1);
          }
          else if ( *(_BYTE *)(a2 + 212) == 1
                 && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                  v7,
                                  L"InteractiveLogon_DisplayUserInformationWhenTheSessionIsLocked",
                                  (void *)(a2 + 208))) != MI_RESULT_OK )
          {
            v5 = v11;
            if ( v11 )
              (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v11)(v11, 1);
          }
          else if ( *(_BYTE *)(a2 + 220) == 1
                 && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                  v7,
                                  L"InteractiveLogon_DoNotDisplayLastSignedIn",
                                  (void *)(a2 + 216))) != MI_RESULT_OK )
          {
            v5 = v11;
            if ( v11 )
              (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v11)(v11, 1);
          }
          else if ( *(_BYTE *)(a2 + 228) == 1
                 && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                  v7,
                                  L"InteractiveLogon_DoNotDisplayUsernameAtSignIn",
                                  (void *)(a2 + 224))) != MI_RESULT_OK )
          {
            v5 = v11;
            if ( v11 )
              (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v11)(v11, 1);
          }
          else if ( *(_BYTE *)(a2 + 236) == 1
                 && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                  v7,
                                  L"InteractiveLogon_DoNotRequireCTRLALTDEL",
                                  (void *)(a2 + 232))) != MI_RESULT_OK )
          {
            v5 = v11;
            if ( v11 )
              (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v11)(v11, 1);
          }
          else if ( *(_BYTE *)(a2 + 244) == 1
                 && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                  v7,
                                  L"InteractiveLogon_MachineInactivityLimit",
                                  (void *)(a2 + 240))) != MI_RESULT_OK )
          {
            v5 = v11;
            if ( v11 )
              (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v11)(v11, 1);
          }
          else if ( *(_BYTE *)(a2 + 256) == 1
                 && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                  v7,
                                  L"InteractiveLogon_MessageTextForUsersAttemptingToLogOn",
                                  (void *)(a2 + 248))) != MI_RESULT_OK )
          {
            v5 = v11;
            if ( v11 )
              (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v11)(v11, 1);
          }
          else if ( *(_BYTE *)(a2 + 272) == 1
                 && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                  v7,
                                  L"InteractiveLogon_MessageTitleForUsersAttemptingToLogOn",
                                  (void *)(a2 + 264))) != MI_RESULT_OK )
          {
            v5 = v11;
            if ( v11 )
              (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v11)(v11, 1);
          }
          else if ( *(_BYTE *)(a2 + 288) == 1
                 && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                  v7,
                                  L"InteractiveLogon_SmartCardRemovalBehavior",
                                  (void *)(a2 + 280))) != MI_RESULT_OK )
          {
            v5 = v11;
            if ( v11 )
              (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v11)(v11, 1);
          }
          else if ( *(_BYTE *)(a2 + 300) == 1
                 && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                  v7,
                                  L"MicrosoftNetworkClient_DigitallySignCommunicationsAlways",
                                  (void *)(a2 + 296))) != MI_RESULT_OK )
          {
            v5 = v11;
            if ( v11 )
              (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v11)(v11, 1);
          }
          else if ( *(_BYTE *)(a2 + 308) == 1
                 && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                  v7,
                                  L"MicrosoftNetworkClient_DigitallySignCommunicationsIfServerAgrees",
                                  (void *)(a2 + 304))) != MI_RESULT_OK )
          {
            v5 = v11;
            if ( v11 )
              (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v11)(v11, 1);
          }
          else if ( *(_BYTE *)(a2 + 316) == 1
                 && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                  v7,
                                  L"MicrosoftNetworkClient_SendUnencryptedPasswordToThirdPartySMBServers",
                                  (void *)(a2 + 312))) != MI_RESULT_OK )
          {
            v5 = v11;
            if ( v11 )
              (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v11)(v11, 1);
          }
          else if ( *(_BYTE *)(a2 + 324) == 1
                 && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                  v7,
                                  L"MicrosoftNetworkServer_DigitallySignCommunicationsAlways",
                                  (void *)(a2 + 320))) != MI_RESULT_OK )
          {
            v5 = v11;
            if ( v11 )
              (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v11)(v11, 1);
          }
          else if ( *(_BYTE *)(a2 + 332) == 1
                 && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                  v7,
                                  L"MicrosoftNetworkServer_DigitallySignCommunicationsIfClientAgrees",
                                  (void *)(a2 + 328))) != MI_RESULT_OK )
          {
            v5 = v11;
            if ( v11 )
              (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v11)(v11, 1);
          }
          else if ( *(_BYTE *)(a2 + 340) == 1
                 && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                  v7,
                                  L"NetworkAccess_DoNotAllowAnonymousEnumerationOfSAMAccounts",
                                  (void *)(a2 + 336))) != MI_RESULT_OK )
          {
            v5 = v11;
            if ( v11 )
              (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v11)(v11, 1);
          }
          else if ( *(_BYTE *)(a2 + 348) == 1
                 && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                  v7,
                                  L"NetworkAccess_DoNotAllowAnonymousEnumerationOfSamAccountsAndShares",
                                  (void *)(a2 + 344))) != MI_RESULT_OK )
          {
            v5 = v11;
            if ( v11 )
              (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v11)(v11, 1);
          }
          else if ( *(_BYTE *)(a2 + 356) == 1
                 && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                  v7,
                                  L"NetworkAccess_RestrictAnonymousAccessToNamedPipesAndShares",
                                  (void *)(a2 + 352))) != MI_RESULT_OK )
          {
            v5 = v11;
            if ( v11 )
              (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v11)(v11, 1);
          }
          else if ( *(_BYTE *)(a2 + 368) == 1
                 && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                  v7,
                                  L"NetworkAccess_RestrictClientsAllowedToMakeRemoteCallsToSAM",
                                  (void *)(a2 + 360))) != MI_RESULT_OK )
          {
            v5 = v11;
            if ( v11 )
              (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v11)(v11, 1);
          }
          else if ( *(_BYTE *)(a2 + 380) == 1
                 && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                  v7,
                                  L"NetworkSecurity_AllowLocalSystemToUseComputerIdentityForNTLM",
                                  (void *)(a2 + 376))) != MI_RESULT_OK )
          {
            v5 = v11;
            if ( v11 )
              (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v11)(v11, 1);
          }
          else if ( *(_BYTE *)(a2 + 388) == 1
                 && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                  v7,
                                  L"NetworkSecurity_AllowPKU2UAuthenticationRequests",
                                  (void *)(a2 + 384))) != MI_RESULT_OK )
          {
            v5 = v11;
            if ( v11 )
              (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v11)(v11, 1);
          }
          else if ( *(_BYTE *)(a2 + 396) == 1
                 && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                  v7,
                                  L"NetworkSecurity_DoNotStoreLANManagerHashValueOnNextPasswordChange",
                                  (void *)(a2 + 392))) != MI_RESULT_OK )
          {
            v5 = v11;
            if ( v11 )
              (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v11)(v11, 1);
          }
          else if ( *(_BYTE *)(a2 + 404) == 1
                 && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                  v7,
                                  L"NetworkSecurity_LANManagerAuthenticationLevel",
                                  (void *)(a2 + 400))) != MI_RESULT_OK )
          {
            v5 = v11;
            if ( v11 )
              (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v11)(v11, 1);
          }
          else if ( *(_BYTE *)(a2 + 412) == 1
                 && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                  v7,
                                  L"NetworkSecurity_MinimumSessionSecurityForNTLMSSPBasedClients",
                                  (void *)(a2 + 408))) != MI_RESULT_OK )
          {
            v5 = v11;
            if ( v11 )
              (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v11)(v11, 1);
          }
          else if ( *(_BYTE *)(a2 + 420) == 1
                 && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                  v7,
                                  L"NetworkSecurity_MinimumSessionSecurityForNTLMSSPBasedServers",
                                  (void *)(a2 + 416))) != MI_RESULT_OK )
          {
            v5 = v11;
            if ( v11 )
              (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v11)(v11, 1);
          }
          else if ( *(_BYTE *)(a2 + 432) == 1
                 && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                  v7,
                                  L"NetworkSecurity_RestrictNTLM_AddRemoteServerExceptionsForNTLMAuthentication",
                                  (void *)(a2 + 424))) != MI_RESULT_OK )
          {
            v5 = v11;
            if ( v11 )
              (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v11)(v11, 1);
          }
          else if ( *(_BYTE *)(a2 + 444) == 1
                 && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                  v7,
                                  L"NetworkSecurity_RestrictNTLM_AuditIncomingNTLMTraffic",
                                  (void *)(a2 + 440))) != MI_RESULT_OK )
          {
            v5 = v11;
            if ( v11 )
              (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v11)(v11, 1);
          }
          else if ( *(_BYTE *)(a2 + 452) == 1
                 && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                  v7,
                                  L"NetworkSecurity_RestrictNTLM_IncomingNTLMTraffic",
                                  (void *)(a2 + 448))) != MI_RESULT_OK )
          {
            v5 = v11;
            if ( v11 )
              (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v11)(v11, 1);
          }
          else if ( *(_BYTE *)(a2 + 460) == 1
                 && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                  v7,
                                  L"NetworkSecurity_RestrictNTLM_OutgoingNTLMTrafficToRemoteServers",
                                  (void *)(a2 + 456))) != MI_RESULT_OK )
          {
            v5 = v11;
            if ( v11 )
              (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v11)(v11, 1);
          }
          else if ( *(_BYTE *)(a2 + 468) == 1
                 && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                  v7,
                                  L"Shutdown_AllowSystemToBeShutDownWithoutHavingToLogOn",
                                  (void *)(a2 + 464))) != MI_RESULT_OK )
          {
            v5 = v11;
            if ( v11 )
              (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v11)(v11, 1);
          }
          else if ( *(_BYTE *)(a2 + 476) == 1
                 && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                  v7,
                                  L"Shutdown_ClearVirtualMemoryPageFile",
                                  (void *)(a2 + 472))) != MI_RESULT_OK )
          {
            v5 = v11;
            if ( v11 )
              (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v11)(v11, 1);
          }
          else if ( *(_BYTE *)(a2 + 484) == 1
                 && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                  v7,
                                  L"UserAccountControl_AllowUIAccessApplicationsToPromptForElevation",
                                  (void *)(a2 + 480))) != MI_RESULT_OK )
          {
            v5 = v11;
            if ( v11 )
              (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v11)(v11, 1);
          }
          else if ( *(_BYTE *)(a2 + 492) == 1
                 && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                  v7,
                                  L"UserAccountControl_BehaviorOfTheElevationPromptForAdministrators",
                                  (void *)(a2 + 488))) != MI_RESULT_OK )
          {
            v5 = v11;
            if ( v11 )
              (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v11)(v11, 1);
          }
          else if ( *(_BYTE *)(a2 + 500) == 1
                 && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                  v7,
                                  L"UserAccountControl_BehaviorOfTheElevationPromptForStandardUsers",
                                  (void *)(a2 + 496))) != MI_RESULT_OK )
          {
            v5 = v11;
            if ( v11 )
              (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v11)(v11, 1);
          }
          else if ( *(_BYTE *)(a2 + 508) == 1
                 && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                  v7,
                                  L"UserAccountControl_DetectApplicationInstallationsAndPromptForElevation",
                                  (void *)(a2 + 504))) != MI_RESULT_OK )
          {
            v5 = v11;
            if ( v11 )
              (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v11)(v11, 1);
          }
          else if ( *(_BYTE *)(a2 + 516) == 1
                 && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                  v7,
                                  L"UserAccountControl_OnlyElevateExecutableFilesThatAreSignedAndValidated",
                                  (void *)(a2 + 512))) != MI_RESULT_OK )
          {
            v5 = v11;
            if ( v11 )
              (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v11)(v11, 1);
          }
          else if ( *(_BYTE *)(a2 + 524) == 1
                 && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                  v7,
                                  L"UserAccountControl_OnlyElevateUIAccessApplicationsThatAreInstalledInSecureLocations",
                                  (void *)(a2 + 520))) != MI_RESULT_OK )
          {
            v5 = v11;
            if ( v11 )
              (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v11)(v11, 1);
          }
          else if ( *(_BYTE *)(a2 + 532) == 1
                 && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                  v7,
                                  L"UserAccountControl_RunAllAdministratorsInAdminApprovalMode",
                                  (void *)(a2 + 528))) != MI_RESULT_OK )
          {
            v5 = v11;
            if ( v11 )
              (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v11)(v11, 1);
          }
          else if ( *(_BYTE *)(a2 + 540) == 1
                 && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                  v7,
                                  L"UserAccountControl_SwitchToTheSecureDesktopWhenPromptingForElevation",
                                  (void *)(a2 + 536))) != MI_RESULT_OK )
          {
            v5 = v11;
            if ( v11 )
              (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v11)(v11, 1);
          }
          else if ( *(_BYTE *)(a2 + 548) == 1
                 && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                  v7,
                                  L"UserAccountControl_UseAdminApprovalMode",
                                  (void *)(a2 + 544))) != MI_RESULT_OK )
          {
            v5 = v11;
            if ( v11 )
              (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v11)(v11, 1);
          }
          else if ( *(_BYTE *)(a2 + 556) == 1
                 && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                  v7,
                                  L"UserAccountControl_VirtualizeFileAndRegistryWriteFailuresToPerUserLocations",
                                  (void *)(a2 + 552))) != MI_RESULT_OK )
          {
            v5 = v11;
            if ( v11 )
              (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v11)(v11, 1);
          }
          else
          {
            inserted = (*(unsigned int (__fastcall **)(WmiRequestHandler *))(*(_QWORD *)v7 + 16LL))(v7);
            if ( inserted )
            {
              v5 = v11;
              if ( v11 )
                (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v11)(v11, 1);
            }
            else
            {
              inserted = (*(unsigned int (__fastcall **)(WmiRequestHandler *))(*(_QWORD *)v7 + 8LL))(v7);
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
          inserted = MI_RESULT_FAILED;
        }
      }
    }
    catch ( const exception *v13 )
    {
      v9 = (const char *)(*(__int64 (__fastcall **)(const exception *))(*(_QWORD *)v13[0] + 8LL))(v13[0]);
      TelemetryEventWriter::WriteStdException((TelemetryEventWriter *)v12, v9);
      LODWORD(v11) = 1;
      inserted = MI_RESULT_FAILED;
    }
    catch ( ... )
    {
      v10 = wil::ResultFromCaughtException(v5);
      TelemetryEventWriter::WriteDefaultExceptionHr((TelemetryEventWriter *)v12, v10);
      LODWORD(v11) = 1;
      inserted = MI_RESULT_FAILED;
    }
  }
  else
  {
    inserted = MI_RESULT_INVALID_PARAMETER;
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
  return (unsigned int)inserted;
}

```

## disassembly

```asm
0x1800afeac  mov     r11, rsp
0x1800afeaf  mov     [r11+18h], rsi
0x1800afeb3  push    rdi
0x1800afeb4  push    r14
0x1800afeb6  push    r15
0x1800afeb8  sub     rsp, 0B0h
0x1800afebf  mov     rax, cs:__security_cookie
0x1800afec6  xor     rax, rsp
0x1800afec9  mov     [rsp+0C8h+var_28], rax
0x1800afed1  mov     rsi, rdx
0x1800afed4  mov     rdi, rcx
0x1800afed7  mov     [rsp+0C8h+var_50], 0
0x1800afedf  mov     [rsp+0C8h+var_4C], 0
0x1800afee4  lea     rax, ??_7TelemetryEventWriter@@6B@; const TelemetryEventWriter::`vftable'
0x1800afeeb  mov     [r11-80h], rax
0x1800afeef  lea     rax, [r11-50h]
0x1800afef3  mov     [r11-78h], rax
0x1800afef7  lea     rax, aMdmPolicyConfi_55; "MDM_Policy_Config01_LocalPoliciesSecuri"...
0x1800afefe  mov     [r11-70h], rax
0x1800aff02  lea     rcx, [r11-50h]
0x1800aff06  call    ?zInternalStart@?$_TlgActivityBase@V?$TraceLoggingActivity@$1?g_hTraceLoggingProvider@@3QEBU_tlgProvider_t@@EB$0CAAAAAAAAAAA@$04U_TlgReflectorTag_Param0IsHProvider@@@@$0CAAAAAAAAAAA@$04@@QEAAXXZ; _TlgActivityBase<TraceLoggingActivity<&_tlgProvider_t const * const g_hTraceLoggingProvider,35184372088832,5,_TlgReflectorTag_Param0IsHProvider>,35184372088832,5>::zInternalStart(void)
0x1800aff0b  mov     eax, cs:dword_180380B68
0x1800aff11  cmp     eax, 5
0x1800aff14  jbe     short loc_1800AFF87
0x1800aff16  mov     rdx, 200000000000h
0x1800aff20  lea     rcx, dword_180380B68
0x1800aff27  call    _tlgKeywordOn
0x1800aff2c  test    al, al
0x1800aff2e  jz      short loc_1800AFF87
0x1800aff30  cmp     [rsp+0C8h+var_4C], 0
0x1800aff35  jz      short loc_1800AFF69
0x1800aff37  cmp     [rsp+0C8h+var_38], 0
0x1800aff3f  jnz     short loc_1800AFF5F
0x1800aff41  cmp     [rsp+0C8h+var_34], 0
0x1800aff49  jnz     short loc_1800AFF5F
0x1800aff4b  cmp     [rsp+0C8h+var_30], 0
0x1800aff53  jnz     short loc_1800AFF5F
0x1800aff55  cmp     [rsp+0C8h+var_2C], 0
0x1800aff5d  jz      short loc_1800AFF69
0x1800aff5f  lea     r9, [rsp+0C8h+var_38]
0x1800aff67  jmp     short loc_1800AFF6C
0x1800aff69  xor     r9d, r9d
0x1800aff6c  lea     r8, [rsp+0C8h+var_48]
0x1800aff74  lea     rdx, word_18034AA22
0x1800aff7b  lea     rcx, dword_180380B68
0x1800aff82  call    ??$Write@$$V@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *)
0x1800aff87  cmp     byte ptr [rsi+48h], 0
0x1800aff8b  jz      loc_1800B0CE9
0x1800aff91  cmp     byte ptr [rsi+58h], 0
0x1800aff95  jz      loc_1800B0CE9
0x1800aff9b  mov     r9, [rsi+40h]; unsigned __int16 *
0x1800aff9f  mov     r8, [rsi+50h]; unsigned __int16 *
0x1800affa3  lea     rdx, aModifyinstance; "ModifyInstanceStart"
0x1800affaa  lea     rcx, [rsp+0C8h+var_80]; this
0x1800affaf  call    ?WriteStart@TelemetryEventWriter@@QEAAXPEBDPEBG1@Z; TelemetryEventWriter::WriteStart(char const *,ushort const *,ushort const *)
0x1800affb4  nop
0x1800affb5  mov     [rsp+0C8h+var_88], 0
0x1800affbe  lea     rax, [rsp+0C8h+var_88]
0x1800affc3  mov     [rsp+0C8h+var_98], rax
0x1800affc8  mov     [rsp+0C8h+var_A0], 3
0x1800affd0  mov     [rsp+0C8h+var_A8], 33h ; '3'
0x1800affd8  lea     r9, ?MDM_Policy_Config01_LocalPoliciesSecurityOptions02_NodeList@@3PAUWmiNodeInfo@@A; WmiNodeInfo near * MDM_Policy_Config01_LocalPoliciesSecurityOptions02_NodeList
0x1800affdf  mov     r8, [rsi+40h]
0x1800affe3  mov     rdx, [rsi+50h]
0x1800affe7  mov     rcx, rdi
0x1800affea  call    ?CreateRequestHandlerInstance@@YA?AW4_MI_Result@@PEAU_MI_Context@@PEBG1PEAUWmiNodeInfo@@KW4RequestType@@AEAPEAVWmiRequestHandler@@@Z; CreateRequestHandlerInstance(_MI_Context *,ushort const *,ushort const *,WmiNodeInfo *,ulong,RequestType,WmiRequestHandler * &)
0x1800affef  mov     edi, eax
0x1800afff1  test    eax, eax
0x1800afff3  jz      short loc_1800AFFFA
0x1800afff5  jmp     loc_1800B0CEE
0x1800afffa  lea     rax, [rsp+0C8h+var_88]
0x1800affff  mov     [rsp+0C8h+var_60], rax
0x1800b0004  mov     r15d, 1
0x1800b000a  mov     [rsp+0C8h+var_58], r15b
0x1800b000f  mov     r14, [rsp+0C8h+var_88]
0x1800b0014  test    r14, r14
0x1800b0017  jnz     short loc_1800B0021
0x1800b0019  mov     edi, r15d
0x1800b001c  jmp     loc_1800B0CEE
0x1800b0021  mov     r9d, 33h ; '3'; unsigned int
0x1800b0027  lea     r8, ?MDM_Policy_Config01_LocalPoliciesSecurityOptions02_NodeList@@3PAUWmiNodeInfo@@A; struct WmiNodeInfo *
0x1800b002e  mov     rdx, rsi; struct _MI_Instance *
0x1800b0031  mov     rcx, r14; this
0x1800b0034  call    ?SetRequestMIInstance@WmiRequestHandler@@QEAA?AW4_MI_Result@@PEBU_MI_Instance@@PEAUWmiNodeInfo@@K@Z; WmiRequestHandler::SetRequestMIInstance(_MI_Instance const *,WmiNodeInfo *,ulong)
0x1800b0039  lea     r8, [rsi+60h]; void *
0x1800b003d  cmp     [r8+4], r15b
0x1800b0041  jnz     short loc_1800B0076
0x1800b0043  lea     rdx, aAccountsBlockm; "Accounts_BlockMicrosoftAccounts"
0x1800b004a  mov     rcx, r14; this
0x1800b004d  call    ?InsertDataForNode@WmiRequestHandlerAdd@@QEAA?AW4_MI_Result@@PEBGPEAX@Z; WmiRequestHandlerAdd::InsertDataForNode(ushort const *,void *)
0x1800b0052  mov     edi, eax
0x1800b0054  test    eax, eax
0x1800b0056  jz      short loc_1800B0076
0x1800b0058  mov     rcx, [rsp+0C8h+var_88]
0x1800b005d  test    rcx, rcx
0x1800b0060  jz      short loc_1800B0071
0x1800b0062  mov     rax, [rcx]
0x1800b0065  mov     edx, r15d
0x1800b0068  mov     rax, [rax]
0x1800b006b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b0070  nop
0x1800b0071  jmp     loc_1800B0CEE
0x1800b0076  lea     r8, [rsi+68h]; void *
0x1800b007a  cmp     [r8+4], r15b
0x1800b007e  jnz     short loc_1800B00B3
0x1800b0080  lea     rdx, aAccountsEnable_0; "Accounts_EnableAdministratorAccountStat"...
0x1800b0087  mov     rcx, r14; this
0x1800b008a  call    ?InsertDataForNode@WmiRequestHandlerAdd@@QEAA?AW4_MI_Result@@PEBGPEAX@Z; WmiRequestHandlerAdd::InsertDataForNode(ushort const *,void *)
0x1800b008f  mov     edi, eax
0x1800b0091  test    eax, eax
0x1800b0093  jz      short loc_1800B00B3
0x1800b0095  mov     rcx, [rsp+0C8h+var_88]
0x1800b009a  test    rcx, rcx
0x1800b009d  jz      short loc_1800B00AE
0x1800b009f  mov     rax, [rcx]
0x1800b00a2  mov     edx, r15d
0x1800b00a5  mov     rax, [rax]
0x1800b00a8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b00ad  nop
0x1800b00ae  jmp     loc_1800B0CEE
0x1800b00b3  lea     r8, [rsi+70h]; void *
0x1800b00b7  cmp     [r8+4], r15b
0x1800b00bb  jnz     short loc_1800B00F0
0x1800b00bd  lea     rdx, aAccountsEnable; "Accounts_EnableGuestAccountStatus"
0x1800b00c4  mov     rcx, r14; this
0x1800b00c7  call    ?InsertDataForNode@WmiRequestHandlerAdd@@QEAA?AW4_MI_Result@@PEBGPEAX@Z; WmiRequestHandlerAdd::InsertDataForNode(ushort const *,void *)
0x1800b00cc  mov     edi, eax
0x1800b00ce  test    eax, eax
0x1800b00d0  jz      short loc_1800B00F0
0x1800b00d2  mov     rcx, [rsp+0C8h+var_88]
0x1800b00d7  test    rcx, rcx
0x1800b00da  jz      short loc_1800B00EB
0x1800b00dc  mov     rax, [rcx]
0x1800b00df  mov     edx, r15d
0x1800b00e2  mov     rax, [rax]
0x1800b00e5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b00ea  nop
0x1800b00eb  jmp     loc_1800B0CEE
0x1800b00f0  lea     r8, [rsi+78h]; void *
0x1800b00f4  cmp     [r8+4], r15b
0x1800b00f8  jnz     short loc_1800B012D
0x1800b00fa  lea     rdx, aAccountsLimitl; "Accounts_LimitLocalAccountUseOfBlankPas"...
0x1800b0101  mov     rcx, r14; this
0x1800b0104  call    ?InsertDataForNode@WmiRequestHandlerAdd@@QEAA?AW4_MI_Result@@PEBGPEAX@Z; WmiRequestHandlerAdd::InsertDataForNode(ushort const *,void *)
0x1800b0109  mov     edi, eax
0x1800b010b  test    eax, eax
0x1800b010d  jz      short loc_1800B012D
0x1800b010f  mov     rcx, [rsp+0C8h+var_88]
0x1800b0114  test    rcx, rcx
0x1800b0117  jz      short loc_1800B0128
0x1800b0119  mov     rax, [rcx]
0x1800b011c  mov     edx, r15d
0x1800b011f  mov     rax, [rax]
0x1800b0122  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b0127  nop
0x1800b0128  jmp     loc_1800B0CEE
0x1800b012d  lea     r8, [rsi+80h]; void *
0x1800b0134  cmp     [r8+8], r15b
0x1800b0138  jnz     short loc_1800B016D
0x1800b013a  lea     rdx, aAccountsRename_0; "Accounts_RenameAdministratorAccount"
0x1800b0141  mov     rcx, r14; this
0x1800b0144  call    ?InsertDataForNode@WmiRequestHandlerAdd@@QEAA?AW4_MI_Result@@PEBGPEAX@Z; WmiRequestHandlerAdd::InsertDataForNode(ushort const *,void *)
0x1800b0149  mov     edi, eax
0x1800b014b  test    eax, eax
0x1800b014d  jz      short loc_1800B016D
0x1800b014f  mov     rcx, [rsp+0C8h+var_88]
0x1800b0154  test    rcx, rcx
0x1800b0157  jz      short loc_1800B0168
0x1800b0159  mov     rax, [rcx]
0x1800b015c  mov     edx, r15d
0x1800b015f  mov     rax, [rax]
0x1800b0162  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b0167  nop
0x1800b0168  jmp     loc_1800B0CEE
0x1800b016d  lea     r8, [rsi+90h]; void *
0x1800b0174  cmp     [r8+8], r15b
0x1800b0178  jnz     short loc_1800B01AD
0x1800b017a  lea     rdx, aAccountsRename; "Accounts_RenameGuestAccount"
0x1800b0181  mov     rcx, r14; this
0x1800b0184  call    ?InsertDataForNode@WmiRequestHandlerAdd@@QEAA?AW4_MI_Result@@PEBGPEAX@Z; WmiRequestHandlerAdd::InsertDataForNode(ushort const *,void *)
0x1800b0189  mov     edi, eax
0x1800b018b  test    eax, eax
0x1800b018d  jz      short loc_1800B01AD
0x1800b018f  mov     rcx, [rsp+0C8h+var_88]
0x1800b0194  test    rcx, rcx
0x1800b0197  jz      short loc_1800B01A8
0x1800b0199  mov     rax, [rcx]
0x1800b019c  mov     edx, r15d
0x1800b019f  mov     rax, [rax]
0x1800b01a2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b01a7  nop
0x1800b01a8  jmp     loc_1800B0CEE
0x1800b01ad  lea     r8, [rsi+0A0h]; void *
0x1800b01b4  cmp     [r8+8], r15b
0x1800b01b8  jnz     short loc_1800B01ED
0x1800b01ba  lea     rdx, aDevicesAllowed; "Devices_AllowedToFormatAndEjectRemovabl"...
0x1800b01c1  mov     rcx, r14; this
0x1800b01c4  call    ?InsertDataForNode@WmiRequestHandlerAdd@@QEAA?AW4_MI_Result@@PEBGPEAX@Z; WmiRequestHandlerAdd::InsertDataForNode(ushort const *,void *)
0x1800b01c9  mov     edi, eax
0x1800b01cb  test    eax, eax
0x1800b01cd  jz      short loc_1800B01ED
0x1800b01cf  mov     rcx, [rsp+0C8h+var_88]
0x1800b01d4  test    rcx, rcx
0x1800b01d7  jz      short loc_1800B01E8
0x1800b01d9  mov     rax, [rcx]
0x1800b01dc  mov     edx, r15d
0x1800b01df  mov     rax, [rax]
0x1800b01e2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b01e7  nop
0x1800b01e8  jmp     loc_1800B0CEE
0x1800b01ed  lea     r8, [rsi+0B0h]; void *
0x1800b01f4  cmp     [r8+4], r15b
0x1800b01f8  jnz     short loc_1800B022D
0x1800b01fa  lea     rdx, aDevicesAllowun; "Devices_AllowUndockWithoutHavingToLogon"
0x1800b0201  mov     rcx, r14; this
0x1800b0204  call    ?InsertDataForNode@WmiRequestHandlerAdd@@QEAA?AW4_MI_Result@@PEBGPEAX@Z; WmiRequestHandlerAdd::InsertDataForNode(ushort const *,void *)
0x1800b0209  mov     edi, eax
0x1800b020b  test    eax, eax
0x1800b020d  jz      short loc_1800B022D
0x1800b020f  mov     rcx, [rsp+0C8h+var_88]
0x1800b0214  test    rcx, rcx
0x1800b0217  jz      short loc_1800B0228
0x1800b0219  mov     rax, [rcx]
0x1800b021c  mov     edx, r15d
0x1800b021f  mov     rax, [rax]
0x1800b0222  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b0227  nop
0x1800b0228  jmp     loc_1800B0CEE
0x1800b022d  lea     r8, [rsi+0B8h]; void *
0x1800b0234  cmp     [r8+4], r15b
0x1800b0238  jnz     short loc_1800B026D
0x1800b023a  lea     rdx, aDevicesPrevent; "Devices_PreventUsersFromInstallingPrint"...
0x1800b0241  mov     rcx, r14; this
0x1800b0244  call    ?InsertDataForNode@WmiRequestHandlerAdd@@QEAA?AW4_MI_Result@@PEBGPEAX@Z; WmiRequestHandlerAdd::InsertDataForNode(ushort const *,void *)
0x1800b0249  mov     edi, eax
0x1800b024b  test    eax, eax
0x1800b024d  jz      short loc_1800B026D
0x1800b024f  mov     rcx, [rsp+0C8h+var_88]
0x1800b0254  test    rcx, rcx
0x1800b0257  jz      short loc_1800B0268
0x1800b0259  mov     rax, [rcx]
0x1800b025c  mov     edx, r15d
0x1800b025f  mov     rax, [rax]
0x1800b0262  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b0267  nop
0x1800b0268  jmp     loc_1800B0CEE
0x1800b026d  lea     r8, [rsi+0C0h]; void *
0x1800b0274  cmp     [r8+8], r15b
0x1800b0278  jnz     short loc_1800B02AD
0x1800b027a  lea     rdx, aDevicesRestric; "Devices_RestrictCDROMAccessToLocallyLog"...
0x1800b0281  mov     rcx, r14; this
0x1800b0284  call    ?InsertDataForNode@WmiRequestHandlerAdd@@QEAA?AW4_MI_Result@@PEBGPEAX@Z; WmiRequestHandlerAdd::InsertDataForNode(ushort const *,void *)
0x1800b0289  mov     edi, eax
0x1800b028b  test    eax, eax
0x1800b028d  jz      short loc_1800B02AD
0x1800b028f  mov     rcx, [rsp+0C8h+var_88]
0x1800b0294  test    rcx, rcx
0x1800b0297  jz      short loc_1800B02A8
0x1800b0299  mov     rax, [rcx]
0x1800b029c  mov     edx, r15d
0x1800b029f  mov     rax, [rax]
0x1800b02a2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b02a7  nop
0x1800b02a8  jmp     loc_1800B0CEE
0x1800b02ad  lea     r8, [rsi+0D0h]; void *
0x1800b02b4  cmp     [r8+4], r15b
0x1800b02b8  jnz     short loc_1800B02ED
0x1800b02ba  lea     rdx, aInteractivelog; "InteractiveLogon_DisplayUserInformation"...
0x1800b02c1  mov     rcx, r14; this
0x1800b02c4  call    ?InsertDataForNode@WmiRequestHandlerAdd@@QEAA?AW4_MI_Result@@PEBGPEAX@Z; WmiRequestHandlerAdd::InsertDataForNode(ushort const *,void *)
0x1800b02c9  mov     edi, eax
0x1800b02cb  test    eax, eax
0x1800b02cd  jz      short loc_1800B02ED
0x1800b02cf  mov     rcx, [rsp+0C8h+var_88]
0x1800b02d4  test    rcx, rcx
0x1800b02d7  jz      short loc_1800B02E8
0x1800b02d9  mov     rax, [rcx]
0x1800b02dc  mov     edx, r15d
0x1800b02df  mov     rax, [rax]
0x1800b02e2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b02e7  nop
0x1800b02e8  jmp     loc_1800B0CEE
0x1800b02ed  lea     r8, [rsi+0D8h]; void *
0x1800b02f4  cmp     [r8+4], r15b
0x1800b02f8  jnz     short loc_1800B032D
0x1800b02fa  lea     rdx, aInteractivelog_5; "InteractiveLogon_DoNotDisplayLastSigned"...
0x1800b0301  mov     rcx, r14; this
0x1800b0304  call    ?InsertDataForNode@WmiRequestHandlerAdd@@QEAA?AW4_MI_Result@@PEBGPEAX@Z; WmiRequestHandlerAdd::InsertDataForNode(ushort const *,void *)
0x1800b0309  mov     edi, eax
0x1800b030b  test    eax, eax
0x1800b030d  jz      short loc_1800B032D
0x1800b030f  mov     rcx, [rsp+0C8h+var_88]
0x1800b0314  test    rcx, rcx
0x1800b0317  jz      short loc_1800B0328
0x1800b0319  mov     rax, [rcx]
0x1800b031c  mov     edx, r15d
0x1800b031f  mov     rax, [rax]
0x1800b0322  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b0327  nop
0x1800b0328  jmp     loc_1800B0CEE
  ... truncated ...
```
