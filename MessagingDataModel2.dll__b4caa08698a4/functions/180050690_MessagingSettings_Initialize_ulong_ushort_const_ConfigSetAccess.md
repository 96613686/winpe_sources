# MessagingSettings::_Initialize(ulong,ushort const *,ConfigSetAccess)

- ea: `0x180050690`
- end: `0x1800519b3`
- name: `?_Initialize@MessagingSettings@@MEAAJKPEBGW4ConfigSetAccess@@@Z`
- size: `4899`
- prototype: ``
- caller_count: `0`
- callee_count: `13`
- tags: `authz_impersonation, registry_config, service_task, installer_update, broker_com_uri`

## callees

- `0x18004e50c`
- `0x18004e5b0`
- `0x18004e664`
- `0x18004e700`
- `0x18004e7b4`
- `0x18004e818`
- `0x18004e87c`
- `0x18004e928`
- `0x18004e9d0`
- `0x18004ea3c`
- `0x18004eb80`
- `0x180050690`
- `0x180051ae4`

## string_xrefs

- `0x180050a21`: `onecoreuap\private\base\inc\appmodel\messaging\MessagingSettingsConfigValues.h`
- `0x1800516ea`: `SiProtocols`
- `0x1800516bc`: `SmsInterceptPorts`
- `0x18005168e`: `SmsInterceptPrefixes`
- `0x18005160b`: `ProxyAuthorizationToken`
- `0x1800515e4`: `ImsiAuthenticationToken`
- `0x180051596`: `UAProfToken`
- `0x18005156f`: `UserAgentString`
- `0x180051519`: `SetCacheControlNoTransform`
- `0x18005146b`: `UseInsertAddressToken`
- `0x180051416`: `HideMediumSIPopups`
- `0x180051212`: `RcsIdentityState`
- `0x1800511eb`: `RcsIdentity`
- `0x1800511c0`: `RcsGroupChatCreationThreadingMode`
- `0x1800510e8`: `RcsSendReadReceipt`
- `0x180050efd`: `TaiwanPresidentialAlertEnabled`
- `0x180050dc2`: `AllowMmsIfDataIsOffWhileRoaming`
- `0x180050d83`: `AllowMmsIfDataIsOff`
- `0x180050b8f`: `AllowMmsIfDataIsOffSupported`
- `0x1800506dd`: `LinkedMode`

## pseudocode

```c
__int64 __fastcall MessagingSettings::_Initialize(_DWORD *a1, int a2)
{
  int v3; // esi
  __int64 v5; // rdx
  int v6; // eax
  int v7; // ebp
  int v8; // eax
  unsigned int v9; // ebx

  a1[2893] = a2;
  v3 = MessagingSettings::_InitializeConfigSets();
  if ( v3 < 0 )
    goto LABEL_2;
  a1[18] = 0;
  v3 = MessagingConfigValue<int>::Initialize(a1 + 2, L"LinkedMode", a1);
  if ( v3 < 0 )
    goto LABEL_2;
  a1[36] = 0;
  v3 = MessagingConfigValue<int>::Initialize(a1 + 20, L"LocationSharingConsent", a1);
  if ( v3 < 0 )
    goto LABEL_2;
  a1[54] = 0;
  v3 = MessagingConfigValue<int>::Initialize(a1 + 38, L"ShowSendingStatus", a1);
  if ( v3 < 0 )
    goto LABEL_2;
  a1[72] = 300;
  v3 = MessagingConfigValue<utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>>::Initialize(
         a1 + 56,
         L"MmsTransportIdleTimeoutInSeconds",
         a1);
  if ( v3 < 0 )
    goto LABEL_2;
  a1[90] = 0;
  v3 = MessagingConfigValue<int>::Initialize(a1 + 74, L"DisplayCMAS_LIFO", a1);
  if ( v3 < 0 )
    goto LABEL_2;
  a1[108] = 0;
  v3 = MessagingConfigValue<int>::Initialize(a1 + 92, L"ExtractPhoneNumbersInStrings", a1);
  if ( v3 < 0 )
    goto LABEL_2;
  v3 = MessagingConfigValueWithDefault<utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>>::Initialize(
         a1 + 110,
         L"MOCloudMessageCarrierSetting",
         a1);
  if ( v3 < 0 )
    goto LABEL_2;
  v3 = MessagingConfigValueWithDefault<utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>>::Initialize(
         a1 + 142,
         L"MOCloudMessageDisplayLabel",
         a1);
  if ( v3 < 0 )
    goto LABEL_2;
  a1[190] = 0;
  v3 = MessagingConfigValue<int>::Initialize(a1 + 174, L"MOCloudMessageEnabled", a1);
  if ( v3 < 0 )
    goto LABEL_2;
  a1[302] = 1;
  v3 = MessagingConfigValue<int>::Initialize(a1 + 286, L"EnableCustomLineSetupDialog", a1);
  if ( v3 < 0 )
    goto LABEL_2;
  a1[320] = 0;
  v3 = MessagingConfigValue<int>::Initialize(a1 + 304, L"RcsMultipartMessageEnabled", a1);
  if ( v3 < 0 )
    goto LABEL_2;
  a1[208] = 0;
  v3 = MessagingConfigValue<utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>>::Initialize(
         a1 + 192,
         L"MdmMessagingAuditingEnabled",
         a1);
  if ( v3 < 0 )
    goto LABEL_2;
  a1[226] = 100;
  v3 = MessagingConfigValue<utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>>::Initialize(
         a1 + 210,
         L"MdmMessagingAuditingCount",
         a1);
  if ( v3 < 0 )
    goto LABEL_2;
  v3 = MessagingConfigValueWithDefault<unsigned __int64>::Initialize(
         a1 + 228,
         L"MdmMessagingAuditingFirstRevisionId",
         a1,
         &c_defaultValue_MdmMessagingAuditingFirstRevisionId);
  if ( v3 < 0 )
    goto LABEL_2;
  v3 = MessagingConfigValueWithDefault<unsigned __int64>::Initialize(
         a1 + 248,
         L"MdmMessagingAuditingCurrentRevisionId",
         a1,
         &c_defaultValue_MdmMessagingAuditingCurrentRevisionId);
  if ( v3 < 0 )
    goto LABEL_2;
  a1[284] = 0;
  v3 = MessagingConfigValue<int>::Initialize(a1 + 268, L"LastKnownMessagingFilteringAppEnabledState", a1);
  if ( v3 < 0 )
    goto LABEL_2;
  a1[338] = 0;
  v3 = MessagingConfigValue<int>::Initialize(a1 + 322, L"UsePerProviderMmsProfile", a1);
  if ( v3 < 0 )
    goto LABEL_2;
  v3 = MMSProfileConfigValueWithDefault<utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>>::Initialize(
         a1 + 340,
         L"TO-PROXY",
         a1,
         &c_pDefaultValue_MmsProxy);
  if ( v3 < 0 )
    goto LABEL_2;
  v3 = MMSProfileConfigValueWithDefault<utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>>::Initialize(
         a1 + 424,
         L"TO-NAPID",
         a1,
         &c_pDefaultValue_MmsNapId);
  if ( v3 < 0 )
    goto LABEL_2;
  v6 = MMSProfileConfigValue<unsigned long>::Initialize(a1 + 508, v5, a1);
  v3 = v6;
  if ( v6 < 0 )
  {
    Log_HREvent_27(v6);
LABEL_2:
    Log_HREvent_27(v3);
    return (unsigned int)v3;
  }
  a1[560] = 300;
  v3 = MMSProfileConfigValueWithDefault<utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>>::Initialize(
         a1 + 562,
         L"ConnectionNameSuffix",
         a1,
         &c_pDefaultValue_MmsConnectionNameSuffix);
  if ( v3 < 0 )
    goto LABEL_2;
  v3 = MMSProfileConfigValue<utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>>::Initialize(
         a1 + 646,
         L"ADDR",
         a1);
  if ( v3 < 0 )
    goto LABEL_2;
  a1[738] = 1;
  v3 = MessagingConfigValue<int>::Initialize(a1 + 722, L"ShowMMSGroupTextUI", a1);
  if ( v3 < 0 )
    goto LABEL_2;
  a1[756] = 1;
  v3 = MessagingConfigValue<int>::Initialize(a1 + 740, L"RequestDeliveryReportIsSupported", a1);
  if ( v3 < 0 )
    goto LABEL_2;
  a1[774] = 1;
  v3 = MessagingConfigValue<int>::Initialize(a1 + 758, L"AllowSendingDeliveryReportIsSupported", a1);
  if ( v3 < 0 )
    goto LABEL_2;
  a1[792] = 0;
  v3 = MessagingConfigValue<int>::Initialize(a1 + 776, L"ShowAutomaticallyDownloadMMSToggle", a1);
  if ( v3 < 0 )
    goto LABEL_2;
  a1[810] = 1;
  v3 = MessagingConfigValue<int>::Initialize(a1 + 794, L"DeliveryNotifySupported", a1);
  if ( v3 < 0 )
    goto LABEL_2;
  a1[828] = 1;
  v3 = MessagingConfigValue<int>::Initialize(a1 + 812, L"AllowMmsIfDataIsOffSupported", a1);
  if ( v3 < 0 )
    goto LABEL_2;
  a1[846] = 0;
  v7 = MessagingConfigValue<utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>>::Initialize(
         a1 + 830,
         L"EmOperatorEnabled",
         a1);
  if ( v7 < 0 )
    goto LABEL_34;
  a1[2890] = 0;
  v7 = MessagingConfigValue<int>::Initialize(a1 + 2874, L"ShowRcsEnabled", a1);
  if ( v7 < 0 )
    goto LABEL_34;
  v7 = HideableOEMAndUserConfigValue<int,unsigned long>::Initialize(
         (int)a1 + 3392,
         (unsigned int)L"MMSGroupText",
         (int)a1 + 2888,
         (unsigned int)&c_visibleValue_MmsGroupText,
         (__int64)a1,
         (__int64)&c_defaultValue_MmsGroupText);
  if ( v7 < 0 )
    goto LABEL_34;
  v7 = HideableOEMAndUserConfigValue<int,unsigned long>::Initialize(
         (int)a1 + 3552,
         (unsigned int)L"RequestDeliveryReport",
         (int)a1 + 2960,
         (unsigned int)&c_visibleValue_RequestDeliveryReport,
         (__int64)a1,
         (__int64)&c_defaultValue_RequestDeliveryReport);
  if ( v7 < 0 )
    goto LABEL_34;
  v7 = HideableOEMAndUserConfigValue<int,unsigned long>::Initialize(
         (int)a1 + 3712,
         (unsigned int)L"AllowSendingDeliveryReport",
         (int)a1 + 3032,
         (unsigned int)&c_visibleValue_AllowSendingDeliveryReport,
         (__int64)a1,
         (__int64)&c_defaultValue_AllowSendingDeliveryReport);
  if ( v7 < 0 )
    goto LABEL_34;
  v7 = HideableOEMAndUserConfigValue<int,unsigned long>::Initialize(
         (int)a1 + 3872,
         (unsigned int)L"AutomaticallyDownload",
         (int)a1 + 3104,
         (unsigned int)&c_visibleValue_AutomaticallyDownload,
         (__int64)a1,
         (__int64)&c_defaultValue_AutomaticallyDownload);
  if ( v7 < 0 )
    goto LABEL_34;
  v7 = HideableOEMAndUserConfigValue<int,unsigned long>::Initialize(
         (int)a1 + 4032,
         (unsigned int)L"SMSDeliveryNotify",
         (int)a1 + 3176,
         (unsigned int)&c_visibleValue_SmsDeliveryNotify,
         (__int64)a1,
         (__int64)&c_defaultValue_SmsDeliveryNotify);
  if ( v7 < 0 )
    goto LABEL_34;
  v7 = HideableOEMAndUserConfigValue<int,unsigned long>::Initialize(
         (int)a1 + 4192,
         (unsigned int)L"AllowMmsIfDataIsOff",
         (int)a1 + 3248,
         (unsigned int)&c_visibleValue_AllowMmsIfDataIsOff,
         (__int64)a1,
         (__int64)&c_defaultValue_AllowMmsIfDataIsOff);
  if ( v7 < 0 )
    goto LABEL_34;
  v7 = HideableOEMAndUserConfigValue<int,unsigned long>::Initialize(
         (int)a1 + 4352,
         (unsigned int)L"AllowMmsIfDataIsOffWhileRoaming",
         (int)a1 + 3248,
         (unsigned int)&c_visibleValue_AllowMmsIfDataIsOffWhileRoaming,
         (__int64)a1,
         (__int64)&c_defaultValue_AllowMmsIfDataIsOffWhileRoaming);
  if ( v7 < 0 )
    goto LABEL_34;
  v7 = HideableOEMAndUserConfigValue<int,unsigned long>::Initialize(
         (int)a1 + 4512,
         (unsigned int)L"Cmas_AMBERAlertEnabled",
         (int)a1 + 3320,
         (unsigned int)&c_visibleValue_Cmas_AMBERAlertEnabled,
         (__int64)a1,
         (__int64)&c_defaultValue_Cmas_AMBERAlertEnabled);
  if ( v7 < 0 )
    goto LABEL_34;
  v7 = HideableOEMAndUserConfigValue<int,unsigned long>::Initialize(
         (int)a1 + 4672,
         (unsigned int)L"Cmas_ExtremeAlertEnabled",
         (int)a1 + 3320,
         (unsigned int)&c_visibleValue_Cmas_ExtremeAlertEnabled,
         (__int64)a1,
         (__int64)&c_defaultValue_Cmas_ExtremeAlertEnabled);
  if ( v7 < 0 )
    goto LABEL_34;
  v7 = HideableOEMAndUserConfigValue<int,unsigned long>::Initialize(
         (int)a1 + 4832,
         (unsigned int)L"Cmas_SevereAlertEnabled",
         (int)a1 + 3320,
         (unsigned int)&c_visibleValue_Cmas_SevereAlertEnabled,
         (__int64)a1,
         (__int64)&c_defaultValue_Cmas_SevereAlertEnabled);
  if ( v7 < 0 )
    goto LABEL_34;
  v7 = HideableOEMAndUserConfigValue<int,unsigned long>::Initialize(
         (int)a1 + 5312,
         (unsigned int)L"TaiwanAlertEnabled",
         (int)a1 + 3320,
         (unsigned int)&c_visibleValue_TaiwanAlertEnabled,
         (__int64)a1,
         (__int64)&c_defaultValue_TaiwanAlert);
  if ( v7 < 0
    || (v7 = HideableOEMAndUserConfigValue<int,unsigned long>::Initialize(
               (int)a1 + 5472,
               (unsigned int)L"TaiwanPresidentialAlertEnabled",
               (int)a1 + 3320,
               (unsigned int)&c_visibleValue_TaiwanPresidentialAlertEnabled,
               (__int64)a1,
               (__int64)&c_defaultValue_TaiwanPresidentialAlert),
        v7 < 0)
    || (v7 = HideableOEMAndUserConfigValue<int,unsigned long>::Initialize(
               (int)a1 + 5632,
               (unsigned int)L"TaiwanEmergencyAlertEnabled",
               (int)a1 + 3320,
               (unsigned int)&c_visibleValue_TaiwanEmergencyAlertEnabled,
               (__int64)a1,
               (__int64)&c_defaultValue_TaiwanEmergencyAlert),
        v7 < 0)
    || (v7 = HideableOEMAndUserConfigValue<int,unsigned long>::Initialize(
               (int)a1 + 5792,
               (unsigned int)L"TaiwanRequiredMonthlyTestEnabled",
               (int)a1 + 3320,
               (unsigned int)&c_visibleValue_TaiwanRequiredMonthlyTestEnabled,
               (__int64)a1,
               (__int64)&c_defaultValue_TaiwanRequiredMonthlyTest),
        v7 < 0)
    || (v7 = HideableOEMAndUserConfigValue<int,unsigned long>::Initialize(
               (int)a1 + 4992,
               (unsigned int)L"Nl2AlertEnabled",
               (int)a1 + 3320,
               (unsigned int)&c_visibleValue_Nl2AlertEnabled,
               (__int64)a1,
               (__int64)&c_defaultValue_Nl2AlertEnabled),
        v7 < 0)
    || (v7 = HideableOEMAndUserConfigValue<int,unsigned long>::Initialize(
               (int)a1 + 5152,
               (unsigned int)L"EtwsSoundEnabled",
               (int)a1 + 3320,
               (unsigned int)&c_visibleValue_EtwsSoundEnabled,
               (__int64)a1,
               (__int64)&c_defaultValue_EtwsSoundEnabled),
        v7 < 0)
    || (v7 = HideableOEMAndUserConfigValue<int,unsigned long>::Initialize(
               (int)a1 + 11336,
               (unsigned int)L"RcsEnabled",
               (int)a1 + 11496,
               (unsigned int)&c_visibleValue_RcsEnabled,
               (__int64)a1,
               (__int64)&c_defaultValue_RcsEnabled),
        v7 < 0)
    || (v7 = HideableOEMAndUserConfigValue<int,unsigned long>::Initialize(
               (int)a1 + 5952,
               (unsigned int)L"Cmas_SpanishLanguageAlertEnabled",
               (int)a1 + 3320,
               (unsigned int)&c_visibleValue_Cmas_SpanishLanguageAlertEnabled,
               (__int64)a1,
               (__int64)&c_defaultValue_Cmas_SpanishLanguageAlertEnabled),
        v7 < 0) )
  {
LABEL_34:
    Log_HREvent_27(v7);
    return (unsigned int)v7;
  }
  else
  {
    v3 = HideableOEMAndUserConfigValue<int,unsigned long>::Initialize(
           (int)a1 + 6112,
           (unsigned int)L"ShowRequiredMonthlyTest",
           (int)a1 + 3320,
           (unsigned int)&c_visibleValue_ShowRequiredMonthlyTest,
           (__int64)a1,
           (__int64)&c_defaultValue_ShowRequiredMonthlyTest);
    if ( v3 < 0 )
      goto LABEL_2;
    v3 = OEMAndUserConfigValue<int>::Initialize(
           a1 + 1568,
           L"RcsSendReadReceipt",
           a1,
           &c_defaultValue_RcsSendReadReceipt);
    if ( v3 < 0 )
      goto LABEL_2;
    v3 = OEMAndUserConfigValue<int>::Initialize(
           a1 + 1604,
           L"RcsFileTransferAutoAccept",
           a1,
           &c_defaultValue_RcsFileTransferAutoAccept);
    if ( v3 < 0 )
      goto LABEL_2;
    v3 = OEMAndUserConfigValue<int>::Initialize(
           a1 + 1640,
           L"RcsFileTransferAutoAcceptWhileRoaming",
           a1,
           &c_defaultValue_RcsFileTransferAutoAcceptWhileRoaming);
    if ( v3 < 0 )
      goto LABEL_2;
    a1[2526] = 1;
    v3 = MessagingConfigValue<int>::Initialize(a1 + 2510, L"RcsAllowLeaveClosedGroupChats", a1);
    if ( v3 < 0 )
      goto LABEL_2;
    a1[2544] = 0;
    v3 = MessagingConfigValue<utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>>::Initialize(
           a1 + 2528,
           L"RcsGroupChatCreationMode",
           a1);
    if ( v3 < 0 )
      goto LABEL_2;
    a1[2562] = 0;
    v3 = MessagingConfigValue<utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>>::Initialize(
           a1 + 2546,
           L"RcsGroupChatCreationThreadingMode",
           a1);
    if ( v3 < 0 )
      goto LABEL_2;
    v3 = MessagingConfigValueWithDefault<utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>>::Initialize(
           a1 + 1676,
           L"RcsIdentity",
           a1);
    if ( v3 < 0 )
      goto LABEL_2;
    a1[1724] = 0;
    v3 = MessagingConfigValue<utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>>::Initialize(
           a1 + 1708,
           L"RcsIdentityState",
           a1);
    if ( v3 < 0 )
      goto LABEL_2;
    a1[1742] = 0;
    v3 = MessagingConfigValue<utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>>::Initialize(
           a1 + 1726,
           L"LimitRecipients",
           a1);
    if ( v3 < 0 )
      goto LABEL_2;
    a1[1760] = 0;
    v3 = MessagingConfigValue<int>::Initialize(a1 + 1744, L"ErrorCodeEnabled", a1);
    if ( v3 < 0 )
      goto LABEL_2;
    a1[1778] = 0;
    v3 = MessagingConfigValue<int>::Initialize(a1 + 1762, L"AllowSelectAllContacts", a1);
    if ( v3 < 0 )
      goto LABEL_2;
    a1[1796] = 0;
    v3 = MessagingConfigValue<utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>>::Initialize(
           a1 + 1780,
           L"WapPushTechnology",
           a1);
    if ( v3 < 0 )
      goto LABEL_2;
    a1[1814] = 0;
    v3 = MessagingConfigValue<utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>>::Initialize(
           a1 + 1798,
           L"RetrySize",
           a1);
    if ( v3 < 0 )
      goto LABEL_2;
    a1[1832] = 0;
    v3 = MessagingConfigValue<utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>>::Initialize(
           a1 + 1816,
           L"MaxRetryCount",
           a1);
    if ( v3 < 0 )
      goto LABEL_2;
    a1[1850] = 0;
    v3 = MessagingConfigValue<utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>>::Initialize(
           a1 + 1834,
           L"TargetVideoFormat",
           a1);
    if ( v3 < 0 )
      goto LABEL_2;
    a1[1868] = 0;
    v3 = MessagingConfigValue<int>::Initialize(a1 + 1852, L"NlInfoEnabled", a1);
    if ( v3 < 0 )
      goto LABEL_2;
    a1[1886] = 0;
    v3 = MessagingConfigValue<int>::Initialize(a1 + 1870, L"LatLocalAlertEnabled", a1);
    if ( v3 < 0 )
      goto LABEL_2;
    a1[1904] = 0;
    v3 = MessagingConfigValue<int>::Initialize(a1 + 1888, L"AllowSMStoSMTPAddress", a1);
    if ( v3 < 0 )
      goto LABEL_2;
    a1[2832] = 0;
    v3 = MessagingConfigValue<int>::Initialize(a1 + 2816, L"ConvertLongSMStoMMS", a1);
    if ( v3 < 0 )
      goto LABEL_2;
    a1[1922] = 0;
    v3 = MessagingConfigValue<int>::Initialize(a1 + 1906, L"HideMediumSIPopups", a1);
    if ( v3 < 0 )
      goto LABEL_2;
    a1[1940] = 1;
    v3 = MessagingConfigValue<int>::Initialize(a1 + 1924, L"UseDefaultAddress", a1);
    if ( v3 < 0 )
      goto LABEL_2;
    a1[1958] = 1;
    v3 = MessagingConfigValue<int>::Initialize(a1 + 1942, L"UseInsertAddressToken", a1);
    if ( v3 < 0 )
      goto LABEL_2;
    a1[1976] = 0;
    v3 = MessagingConfigValue<int>::Initialize(a1 + 1960, L"UseUTF8ForUnspecifiedCharset", a1);
    if ( v3 < 0 )
      goto LABEL_2;
    a1[1994] = 0;
    v3 = MessagingConfigValue<int>::Initialize(a1 + 1978, L"AutoRetryDownload", a1);
    if ( v3 < 0 )
      goto LABEL_2;
    a1[2012] = 5;
    v3 = MessagingConfigValue<utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>>::Initialize(
           a1 + 1996,
           L"MMSLimitAttachments",
           a1);
    if ( v3 < 0 )
      goto LABEL_2;
    a1[2030] = 0;
    v3 = MessagingConfigValue<int>::Initialize(a1 + 2014, L"SetCacheControlNoTransform", a1);
    if ( v3 < 0 )
      goto LABEL_2;
    a1[2048] = 0;
    v3 = MessagingConfigValue<int>::Initialize(a1 + 2032, L"MmsGbaAuthenticationEnabled", a1);
    if ( v3 < 0 )
      goto LABEL_2;
    v3 = MessagingConfigValueWithDefault<utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>>::Initialize(
           a1 + 2050,
           L"UserAgentString",
           a1);
    if ( v3 < 0 )
      goto LABEL_2;
    v3 = MessagingConfigValueWithDefault<utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>>::Initialize(
           a1 + 2082,
           L"UAProfToken",
           a1);
    if ( v3 < 0 )
      goto LABEL_2;
    v3 = MessagingConfigValueWithDefault<utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>>::Initialize(
           a1 + 2114,
           L"UAProf",
           a1);
    if ( v3 < 0 )
      goto LABEL_2;
    v3 = MessagingConfigValueWithDefault<utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>>::Initialize(
           a1 + 2146,
           L"ImsiAuthenticationToken",
           a1);
    if ( v3 < 0 )
      goto LABEL_2;
    v3 = MessagingConfigValueWithDefault<utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>>::Initialize(
           a1 + 2178,
           L"ProxyAuthorizationToken",
           a1);
    if ( v3 < 0 )
      goto LABEL_2;
    v3 = MessagingConfigValueWithDefault<utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>>::Initialize(
           a1 + 2210,
           L"DefaultContentLocationUrl",
           a1);
    if ( v3 < 0 )
      goto LABEL_2;
    v3 = MessagingConfigValueWithDefault<ConfigValueStringList>::Initialize(
           a1 + 2242,
           L"BroadcastMessageChannels",
           a1,
           &c_pDefaultValue_BroadcastMessageChannels);
    if ( v3 < 0 )
      goto LABEL_2;
    v3 = MessagingConfigValueWithDefault<ConfigValueStringList>::Initialize(
           a1 + 2282,
           L"SmsInterceptPrefixes",
           a1,
           &c_pDefaultValue_SmsInterceptPrefixes);
    if ( v3 < 0 )
      goto LABEL_2;
    v3 = MessagingConfigValueWithDefault<ConfigValueStringList>::Initialize(
           a1 + 2322,
           L"SmsInterceptPorts",
           a1,
           &c_pDefaultValue_SmsInterceptPorts);
    if ( v3 < 0 )
      goto LABEL_2;
    v3 = MessagingConfigValueWithDefault<ConfigValueStringList>::Initialize(
           a1 + 2362,
           L"SiProtocols",
           a1,
           &c_pDefaultValue_SiProtocols);
    if ( v3 < 0 )
      goto LABEL_2;
    a1[2418] = 1;
    v3 = MessagingConfigValue<int>::Initialize(a1 + 2402, L"Cmas_PresedentialAlertEnabled", a1);
    if ( v3 < 0 )
      goto LABEL_2;
    a1[2436] = 0;
    v3 = MessagingConfigValue<int>::Initialize(a1 + 2420, L"DisableSMSCPanel", a1);
    if ( v3 < 0 )
      goto LABEL_2;
    a1[2454] = 0;
    v3 = MessagingConfigValue<int>::Initialize(a1 + 2438, L"ShowMmsGroupTextWarning", a1);
    if ( v3 < 0 )
      goto LABEL_2;
    a1[2472] = 0;
    v3 = MessagingConfigValue<int>::Initialize(a1 + 2456, L"MmsGroupTextWarningShown", a1);
    if ( v3 < 0 )
      goto LABEL_2;
    v3 = MessagingConfigValue<utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>>::Initialize(
           a1 + 2564,
           L"AssistedDialingMcc",
           a1);
    if ( v3 < 0 )
      goto LABEL_2;
    v3 = MessagingConfigValue<utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>>::Initialize(
           a1 + 2588,
           L"AssistedDialingMnc",
           a1);
    if ( v3 < 0 )
      goto LABEL_2;
    v3 = MessagingConfigValue<utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>>::Initialize(
           a1 + 2612,
           L"AssistedDialingLteMcc",
           a1);
    if ( v3 < 0 )
      goto LABEL_2;
    v3 = MessagingConfigValue<utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>>::Initialize(
           a1 + 2636,
           L"AssistedDialingLteMnc",
           a1);
    if ( v3 < 0 )
      goto LABEL_2;
    v3 = MessagingConfigValue<int>::Initialize(a1 + 2660, L"AssistedDialingPlusCodeSupportOverride", a1);
    if ( v3 < 0 )
      goto LABEL_2;
    v3 = MessagingConfigValue<utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>>::Initialize(
           a1 + 2676,
           L"EarthquakeMessageString",
           a1);
    if ( v3 < 0 )
      goto LABEL_2;
    v3 = MessagingConfigValue<utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>>::Initialize(
           a1 + 2700,
           L"TsunamiMessageString",
           a1);
    if ( v3 < 0 )
      goto LABEL_2;
    v3 = MessagingConfigValue<utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>>::Initialize(
           a1 + 2724,
           L"EarthquakeTsunamiMessageString",
           a1);
    if ( v3 < 0 )
      goto LABEL_2;
    v3 = MessagingConfigValue<utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>>::Initialize(
           a1 + 2748,
           L"EtwsSoundFileName",
           a1);
    if ( v3 < 0 )
      goto LABEL_2;
    v3 = MessagingConfigValue<utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>>::Initialize(
           a1 + 2772,
           L"SMStoSMTPShortCode",
           a1);
    if ( v3 < 0 )
      goto LABEL_2;
    a1[2490] = 0;
    v3 = MessagingConfigValue<int>::Initialize(a1 + 2474, L"SevereAlertDependentOnExtremeAlert", a1);
    if ( v3 < 0 )
      goto LABEL_2;
    a1[2508] = 300000;
    v8 = MessagingConfigValue<utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>>::Initialize(
           a1 + 2492,
           L"RcsTimeWindowAfterSelfLeave",
           a1);
    v9 = v8;
    if ( v8 >= 0 )
    {
      return 0;
    }
    else
    {
      Log_HREvent_27(v8);
      return v9;
    }
  }
}

```

## disassembly

```asm
0x180050690  push    rbx
0x180050692  push    rbp
0x180050693  push    rsi
0x180050694  push    rdi
0x180050695  push    r12
0x180050697  push    r13
0x180050699  push    r14
0x18005069b  push    r15
0x18005069d  sub     rsp, 38h
0x1800506a1  mov     rbx, rcx
0x1800506a4  mov     [rcx+2D34h], edx
0x1800506aa  call    ?_InitializeConfigSets@MessagingSettings@@AEAAJKPEBGW4ConfigSetAccess@@@Z; MessagingSettings::_InitializeConfigSets(ulong,ushort const *,ConfigSetAccess)
0x1800506af  xor     r13d, r13d
0x1800506b2  mov     esi, eax
0x1800506b4  test    eax, eax
0x1800506b6  jns     short loc_1800506D6
0x1800506b8  lea     r9d, [r13+2Bh]
0x1800506bc  mov     edx, 1
0x1800506c1  lea     r8, aOnecoreuapBase_65; "onecoreuap\\base\\appmodel\\messagingom"...
0x1800506c8  mov     ecx, esi; int
0x1800506ca  call    Log_HREvent_27
0x1800506cf  mov     eax, esi
0x1800506d1  jmp     loc_1800519A2
0x1800506d6  lea     rcx, [rbx+8]
0x1800506da  mov     r8, rbx
0x1800506dd  lea     rdx, ?c_pValueName_LinkedMode@@3QBGB; "LinkedMode"
0x1800506e4  mov     [rcx+40h], r13d
0x1800506e8  call    ?Initialize@?$MessagingConfigValue@H@@QEAAJPEBGPEAVMessagingSettings@@@Z; MessagingConfigValue<int>::Initialize(ushort const *,MessagingSettings *)
0x1800506ed  mov     esi, eax
0x1800506ef  test    eax, eax
0x1800506f1  jns     short loc_1800506FB
0x1800506f3  mov     r9d, 2Eh ; '.'
0x1800506f9  jmp     short loc_1800506BC
0x1800506fb  lea     rcx, [rbx+50h]
0x1800506ff  mov     r8, rbx
0x180050702  lea     rdx, ?c_pValueName_LocationSharingConsent@@3QBGB; "LocationSharingConsent"
0x180050709  mov     [rcx+40h], r13d
0x18005070d  call    ?Initialize@?$MessagingConfigValue@H@@QEAAJPEBGPEAVMessagingSettings@@@Z; MessagingConfigValue<int>::Initialize(ushort const *,MessagingSettings *)
0x180050712  mov     esi, eax
0x180050714  test    eax, eax
0x180050716  jns     short loc_180050720
0x180050718  mov     r9d, 30h ; '0'
0x18005071e  jmp     short loc_1800506BC
0x180050720  lea     rcx, [rbx+98h]
0x180050727  mov     r8, rbx
0x18005072a  lea     rdx, ?c_pValueName_ShowSendingStatus@@3QBGB; "ShowSendingStatus"
0x180050731  mov     [rcx+40h], r13d
0x180050735  call    ?Initialize@?$MessagingConfigValue@H@@QEAAJPEBGPEAVMessagingSettings@@@Z; MessagingConfigValue<int>::Initialize(ushort const *,MessagingSettings *)
0x18005073a  mov     esi, eax
0x18005073c  test    eax, eax
0x18005073e  jns     short loc_18005074B
0x180050740  mov     r9d, 32h ; '2'
0x180050746  jmp     loc_1800506BC
0x18005074b  lea     rcx, [rbx+0E0h]
0x180050752  mov     r14d, 12Ch
0x180050758  mov     r8, rbx
0x18005075b  mov     [rcx+40h], r14d
0x18005075f  lea     rdx, ?c_pValueName_MmsTransportIdleTimeoutInSeconds@@3QBGB; "MmsTransportIdleTimeoutInSeconds"
0x180050766  call    ?Initialize@?$MessagingConfigValue@V?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@@@QEAAJPEBGPEAVMessagingSettings@@@Z; MessagingConfigValue<utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>>::Initialize(ushort const *,MessagingSettings *)
0x18005076b  mov     esi, eax
0x18005076d  test    eax, eax
0x18005076f  jns     short loc_18005077C
0x180050771  mov     r9d, 35h ; '5'
0x180050777  jmp     loc_1800506BC
0x18005077c  lea     rcx, [rbx+128h]
0x180050783  mov     r8, rbx
0x180050786  lea     rdx, ?c_pValueName_DisplayCmasLifo@@3QBGB; "DisplayCMAS_LIFO"
0x18005078d  mov     [rcx+40h], r13d
0x180050791  call    ?Initialize@?$MessagingConfigValue@H@@QEAAJPEBGPEAVMessagingSettings@@@Z; MessagingConfigValue<int>::Initialize(ushort const *,MessagingSettings *)
0x180050796  mov     esi, eax
0x180050798  test    eax, eax
0x18005079a  jns     short loc_1800507A7
0x18005079c  mov     r9d, 37h ; '7'
0x1800507a2  jmp     loc_1800506BC
0x1800507a7  lea     rcx, [rbx+170h]
0x1800507ae  mov     r8, rbx
0x1800507b1  lea     rdx, ?c_pValueName_ExtractPhoneNumbersInStrings@@3QBGB; "ExtractPhoneNumbersInStrings"
0x1800507b8  mov     [rcx+40h], r13d
0x1800507bc  call    ?Initialize@?$MessagingConfigValue@H@@QEAAJPEBGPEAVMessagingSettings@@@Z; MessagingConfigValue<int>::Initialize(ushort const *,MessagingSettings *)
0x1800507c1  mov     esi, eax
0x1800507c3  test    eax, eax
0x1800507c5  jns     short loc_1800507D2
0x1800507c7  mov     r9d, 3Ah ; ':'
0x1800507cd  jmp     loc_1800506BC
0x1800507d2  lea     rcx, [rbx+1B8h]
0x1800507d9  mov     r8, rbx
0x1800507dc  lea     rdx, ?c_pValueName_MOCloudMessageCarrierSetting@@3QBGB; "MOCloudMessageCarrierSetting"
0x1800507e3  call    ?Initialize@?$MessagingConfigValueWithDefault@V?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@@@QEAAJPEBGPEAVMessagingSettings@@0@Z; MessagingConfigValueWithDefault<utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>>::Initialize(ushort const *,MessagingSettings *,ushort const *)
0x1800507e8  mov     esi, eax
0x1800507ea  test    eax, eax
0x1800507ec  jns     short loc_1800507F9
0x1800507ee  mov     r9d, 3Dh ; '='
0x1800507f4  jmp     loc_1800506BC
0x1800507f9  lea     rcx, [rbx+238h]
0x180050800  mov     r8, rbx
0x180050803  lea     rdx, ?c_pValueName_MOCloudMessageDisplayLabel@@3QBGB; "MOCloudMessageDisplayLabel"
0x18005080a  call    ?Initialize@?$MessagingConfigValueWithDefault@V?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@@@QEAAJPEBGPEAVMessagingSettings@@0@Z; MessagingConfigValueWithDefault<utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>>::Initialize(ushort const *,MessagingSettings *,ushort const *)
0x18005080f  mov     esi, eax
0x180050811  test    eax, eax
0x180050813  jns     short loc_180050820
0x180050815  mov     r9d, 40h ; '@'
0x18005081b  jmp     loc_1800506BC
0x180050820  lea     rcx, [rbx+2B8h]
0x180050827  mov     r8, rbx
0x18005082a  lea     rdx, ?c_pValueName_MOCloudMessageEnabled@@3QBGB; "MOCloudMessageEnabled"
0x180050831  mov     [rcx+40h], r13d
0x180050835  call    ?Initialize@?$MessagingConfigValue@H@@QEAAJPEBGPEAVMessagingSettings@@@Z; MessagingConfigValue<int>::Initialize(ushort const *,MessagingSettings *)
0x18005083a  mov     esi, eax
0x18005083c  test    eax, eax
0x18005083e  jns     short loc_18005084B
0x180050840  mov     r9d, 42h ; 'B'
0x180050846  jmp     loc_1800506BC
0x18005084b  lea     rcx, [rbx+478h]
0x180050852  mov     edi, 1
0x180050857  mov     r8, rbx
0x18005085a  mov     [rcx+40h], edi
0x18005085d  lea     rdx, ?c_pValueName_EnableCustomLineSetupDialog@@3QBGB; "EnableCustomLineSetupDialog"
0x180050864  call    ?Initialize@?$MessagingConfigValue@H@@QEAAJPEBGPEAVMessagingSettings@@@Z; MessagingConfigValue<int>::Initialize(ushort const *,MessagingSettings *)
0x180050869  mov     esi, eax
0x18005086b  test    eax, eax
0x18005086d  jns     short loc_18005087A
0x18005086f  lea     r9d, [rdi+44h]
0x180050873  mov     edx, edi
0x180050875  jmp     loc_1800506C1
0x18005087a  lea     rcx, [rbx+4C0h]
0x180050881  mov     r8, rbx
0x180050884  lea     rdx, ?c_pValueName_RcsMultipartMessageEnabled@@3QBGB; "RcsMultipartMessageEnabled"
0x18005088b  mov     [rcx+40h], r13d
0x18005088f  call    ?Initialize@?$MessagingConfigValue@H@@QEAAJPEBGPEAVMessagingSettings@@@Z; MessagingConfigValue<int>::Initialize(ushort const *,MessagingSettings *)
0x180050894  mov     esi, eax
0x180050896  test    eax, eax
0x180050898  jns     short loc_1800508A2
0x18005089a  mov     r9d, 48h ; 'H'
0x1800508a0  jmp     short loc_180050873
0x1800508a2  lea     rcx, [rbx+300h]
0x1800508a9  mov     r8, rbx
0x1800508ac  lea     rdx, ?c_pValueName_MdmMessagingAuditingEnabled@@3QBGB; "MdmMessagingAuditingEnabled"
0x1800508b3  mov     [rcx+40h], r13d
0x1800508b7  call    ?Initialize@?$MessagingConfigValue@V?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@@@QEAAJPEBGPEAVMessagingSettings@@@Z; MessagingConfigValue<utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>>::Initialize(ushort const *,MessagingSettings *)
0x1800508bc  mov     esi, eax
0x1800508be  test    eax, eax
0x1800508c0  jns     short loc_1800508CA
0x1800508c2  mov     r9d, 4Bh ; 'K'
0x1800508c8  jmp     short loc_180050873
0x1800508ca  lea     rcx, [rbx+348h]
0x1800508d1  mov     r8, rbx
0x1800508d4  lea     rdx, ?c_pValueName_MdmMessagingAuditingCount@@3QBGB; "MdmMessagingAuditingCount"
0x1800508db  mov     dword ptr [rcx+40h], 64h ; 'd'
0x1800508e2  call    ?Initialize@?$MessagingConfigValue@V?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@@@QEAAJPEBGPEAVMessagingSettings@@@Z; MessagingConfigValue<utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>>::Initialize(ushort const *,MessagingSettings *)
0x1800508e7  mov     esi, eax
0x1800508e9  test    eax, eax
0x1800508eb  jns     short loc_1800508F8
0x1800508ed  mov     r9d, 4Eh ; 'N'
0x1800508f3  jmp     loc_180050873
0x1800508f8  lea     rcx, [rbx+390h]
0x1800508ff  mov     r8, rbx
0x180050902  lea     r9, ?c_defaultValue_MdmMessagingAuditingFirstRevisionId@@3_KB; unsigned __int64 const c_defaultValue_MdmMessagingAuditingFirstRevisionId
0x180050909  lea     rdx, ?c_pValueName_MdmMessagingAuditingFirstRevisionId@@3QBGB; "MdmMessagingAuditingFirstRevisionId"
0x180050910  call    ?Initialize@?$MessagingConfigValueWithDefault@_K@@QEAAJPEBGPEAVMessagingSettings@@AEB_K@Z; MessagingConfigValueWithDefault<unsigned __int64>::Initialize(ushort const *,MessagingSettings *,unsigned __int64 const &)
0x180050915  mov     esi, eax
0x180050917  test    eax, eax
0x180050919  jns     short loc_180050926
0x18005091b  mov     r9d, 51h ; 'Q'
0x180050921  jmp     loc_180050873
0x180050926  lea     rcx, [rbx+3E0h]
0x18005092d  mov     r8, rbx
0x180050930  lea     r9, ?c_defaultValue_MdmMessagingAuditingCurrentRevisionId@@3_KB; unsigned __int64 const c_defaultValue_MdmMessagingAuditingCurrentRevisionId
0x180050937  lea     rdx, ?c_pValueName_MdmMessagingAuditingCurrentRevisionId@@3QBGB; "MdmMessagingAuditingCurrentRevisionId"
0x18005093e  call    ?Initialize@?$MessagingConfigValueWithDefault@_K@@QEAAJPEBGPEAVMessagingSettings@@AEB_K@Z; MessagingConfigValueWithDefault<unsigned __int64>::Initialize(ushort const *,MessagingSettings *,unsigned __int64 const &)
0x180050943  mov     esi, eax
0x180050945  test    eax, eax
0x180050947  jns     short loc_180050954
0x180050949  mov     r9d, 54h ; 'T'
0x18005094f  jmp     loc_180050873
0x180050954  lea     rcx, [rbx+430h]
0x18005095b  mov     r8, rbx
0x18005095e  lea     rdx, ?c_pValueName_MessageFilteringAppEnabled@@3QBGB; "LastKnownMessagingFilteringAppEnabledSt"...
0x180050965  mov     [rcx+40h], r13d
0x180050969  call    ?Initialize@?$MessagingConfigValue@H@@QEAAJPEBGPEAVMessagingSettings@@@Z; MessagingConfigValue<int>::Initialize(ushort const *,MessagingSettings *)
0x18005096e  mov     esi, eax
0x180050970  test    eax, eax
0x180050972  jns     short loc_18005097F
0x180050974  mov     r9d, 57h ; 'W'
0x18005097a  jmp     loc_180050873
0x18005097f  lea     rcx, [rbx+508h]
0x180050986  mov     r8, rbx
0x180050989  lea     rdx, ?c_pValueName_UsePerProviderMmsProfile@@3QBGB; "UsePerProviderMmsProfile"
0x180050990  mov     [rcx+40h], r13d
0x180050994  call    ?Initialize@?$MessagingConfigValue@H@@QEAAJPEBGPEAVMessagingSettings@@@Z; MessagingConfigValue<int>::Initialize(ushort const *,MessagingSettings *)
0x180050999  mov     esi, eax
0x18005099b  test    eax, eax
0x18005099d  jns     short loc_1800509AA
0x18005099f  mov     r9d, 5Ah ; 'Z'
0x1800509a5  jmp     loc_180050873
0x1800509aa  lea     rcx, [rbx+550h]
0x1800509b1  mov     r8, rbx
0x1800509b4  lea     r9, ?c_pDefaultValue_MmsProxy@@3QBGB; ushort const near * const c_pDefaultValue_MmsProxy
0x1800509bb  lea     rdx, ?c_pValueName_MmsProxy@@3QBGB; "TO-PROXY"
0x1800509c2  call    ?Initialize@?$MMSProfileConfigValueWithDefault@V?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@@@QEAAJPEBGPEAVMessagingSettings@@0@Z; MMSProfileConfigValueWithDefault<utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>>::Initialize(ushort const *,MessagingSettings *,ushort const *)
0x1800509c7  mov     esi, eax
0x1800509c9  test    eax, eax
0x1800509cb  jns     short loc_1800509D8
0x1800509cd  mov     r9d, 5Ch ; '\'
0x1800509d3  jmp     loc_180050873
0x1800509d8  lea     rcx, [rbx+6A0h]
0x1800509df  mov     r8, rbx
0x1800509e2  lea     r9, ?c_pDefaultValue_MmsNapId@@3QBGB; ushort const near * const c_pDefaultValue_MmsNapId
0x1800509e9  lea     rdx, ?c_pValueName_MmsNapId@@3QBGB; "TO-NAPID"
0x1800509f0  call    ?Initialize@?$MMSProfileConfigValueWithDefault@V?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@@@QEAAJPEBGPEAVMessagingSettings@@0@Z; MMSProfileConfigValueWithDefault<utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>>::Initialize(ushort const *,MessagingSettings *,ushort const *)
0x1800509f5  mov     esi, eax
0x1800509f7  test    eax, eax
0x1800509f9  jns     short loc_180050A06
0x1800509fb  mov     r9d, 5Eh ; '^'
0x180050a01  jmp     loc_180050873
0x180050a06  mov     r8, rbx
0x180050a09  lea     rcx, [rbx+7F0h]
0x180050a10  call    ?Initialize@?$MMSProfileConfigValue@K@@QEAAJPEBGPEAVMessagingSettings@@@Z; MMSProfileConfigValue<ulong>::Initialize(ushort const *,MessagingSettings *)
0x180050a15  mov     esi, eax
0x180050a17  test    eax, eax
0x180050a19  jns     short loc_180050A3C
0x180050a1b  mov     r9d, 238h
0x180050a21  lea     r8, aOnecoreuapPriv_3; "onecoreuap\\private\\base\\inc\\appmode"...
0x180050a28  mov     edx, edi
0x180050a2a  mov     ecx, eax; int
0x180050a2c  call    Log_HREvent_27
0x180050a31  mov     r9d, 60h ; '`'
0x180050a37  jmp     loc_180050873
0x180050a3c  lea     rcx, [rbx+8C8h]
0x180050a43  mov     [rbx+8C0h], r14d
0x180050a4a  lea     r9, ?c_pDefaultValue_MmsConnectionNameSuffix@@3QBGB; ushort const near * const c_pDefaultValue_MmsConnectionNameSuffix
0x180050a51  mov     r8, rbx
0x180050a54  lea     rdx, ?c_pValueName_MmsConnectionNameSuffix@@3QBGB; "ConnectionNameSuffix"
0x180050a5b  call    ?Initialize@?$MMSProfileConfigValueWithDefault@V?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@@@QEAAJPEBGPEAVMessagingSettings@@0@Z; MMSProfileConfigValueWithDefault<utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>>::Initialize(ushort const *,MessagingSettings *,ushort const *)
0x180050a60  mov     esi, eax
0x180050a62  test    eax, eax
0x180050a64  jns     short loc_180050A71
0x180050a66  mov     r9d, 63h ; 'c'
0x180050a6c  jmp     loc_180050873
0x180050a71  lea     rcx, [rbx+0A18h]
0x180050a78  mov     r8, rbx
0x180050a7b  lea     rdx, ?c_pValueName_MmsAddr@@3QBGB; "ADDR"
0x180050a82  call    ?Initialize@?$MMSProfileConfigValue@V?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@@@QEAAJPEBGPEAVMessagingSettings@@@Z; MMSProfileConfigValue<utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>>::Initialize(ushort const *,MessagingSettings *)
0x180050a87  mov     esi, eax
0x180050a89  test    eax, eax
0x180050a8b  jns     short loc_180050A98
0x180050a8d  mov     r9d, 65h ; 'e'
0x180050a93  jmp     loc_180050873
0x180050a98  lea     r14, [rbx+0B48h]
0x180050a9f  mov     r8, rbx
0x180050aa2  mov     rcx, r14
0x180050aa5  mov     [r14+40h], edi
0x180050aa9  lea     rdx, ?c_pValueName_ShowMmsGroupTextUI@@3QBGB; "ShowMMSGroupTextUI"
0x180050ab0  call    ?Initialize@?$MessagingConfigValue@H@@QEAAJPEBGPEAVMessagingSettings@@@Z; MessagingConfigValue<int>::Initialize(ushort const *,MessagingSettings *)
0x180050ab5  mov     esi, eax
0x180050ab7  test    eax, eax
0x180050ab9  jns     short loc_180050AC6
0x180050abb  mov     r9d, 68h ; 'h'
0x180050ac1  jmp     loc_180050873
0x180050ac6  lea     r15, [rbx+0B90h]
0x180050acd  mov     r8, rbx
0x180050ad0  mov     rcx, r15
0x180050ad3  mov     [r15+40h], edi
0x180050ad7  lea     rdx, ?c_pValueName_RequestDeliveryReportIsSupported@@3QBGB; "RequestDeliveryReportIsSupported"
0x180050ade  call    ?Initialize@?$MessagingConfigValue@H@@QEAAJPEBGPEAVMessagingSettings@@@Z; MessagingConfigValue<int>::Initialize(ushort const *,MessagingSettings *)
0x180050ae3  mov     esi, eax
0x180050ae5  test    eax, eax
0x180050ae7  jns     short loc_180050AF4
0x180050ae9  mov     r9d, 6Bh ; 'k'
0x180050aef  jmp     loc_180050873
0x180050af4  lea     r12, [rbx+0BD8h]
0x180050afb  mov     r8, rbx
0x180050afe  mov     rcx, r12
0x180050b01  mov     [r12+40h], edi
0x180050b06  lea     rdx, ?c_pValueName_AllowSendingDeliveryReportIsSupported@@3QBGB; "AllowSendingDeliveryReportIsSupported"
0x180050b0d  call    ?Initialize@?$MessagingConfigValue@H@@QEAAJPEBGPEAVMessagingSettings@@@Z; MessagingConfigValue<int>::Initialize(ushort const *,MessagingSettings *)
0x180050b12  mov     esi, eax
0x180050b14  test    eax, eax
0x180050b16  jns     short loc_180050B23
0x180050b18  mov     r9d, 6Eh ; 'n'
0x180050b1e  jmp     loc_180050873
0x180050b23  lea     rax, [rbx+0C20h]
0x180050b2a  mov     r8, rbx
0x180050b2d  mov     rcx, rax
0x180050b30  mov     [rax+40h], r13d
0x180050b34  lea     rdx, ?c_pValueName_ShowAutomaticallyDownloadMmsToggle@@3QBGB; "ShowAutomaticallyDownloadMMSToggle"
0x180050b3b  call    ?Initialize@?$MessagingConfigValue@H@@QEAAJPEBGPEAVMessagingSettings@@@Z; MessagingConfigValue<int>::Initialize(ushort const *,MessagingSettings *)
0x180050b40  mov     esi, eax
0x180050b42  test    eax, eax
0x180050b44  jns     short loc_180050B51
0x180050b46  mov     r9d, 71h ; 'q'
0x180050b4c  jmp     loc_180050873
0x180050b51  lea     rax, [rbx+0C68h]
0x180050b58  mov     r8, rbx
0x180050b5b  mov     rcx, rax
0x180050b5e  mov     [rax+40h], edi
0x180050b61  lea     rdx, ?c_pValueName_DeliveryNotifySupported@@3QBGB; "DeliveryNotifySupported"
0x180050b68  call    ?Initialize@?$MessagingConfigValue@H@@QEAAJPEBGPEAVMessagingSettings@@@Z; MessagingConfigValue<int>::Initialize(ushort const *,MessagingSettings *)
0x180050b6d  mov     esi, eax
0x180050b6f  test    eax, eax
0x180050b71  jns     short loc_180050B7E
  ... truncated ...
```
