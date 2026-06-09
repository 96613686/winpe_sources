# DeviceConfiguration::WNFListener::SubscribeToWNFNotifications(void)

- ea: `0x18000d668`
- end: `0x18000d862`
- name: `?SubscribeToWNFNotifications@WNFListener@DeviceConfiguration@@QEAAXXZ`
- size: `506`
- prototype: `void __fastcall(DeviceConfiguration::WNFListener *__hidden this)`
- caller_count: `1`
- callee_count: `17`
- tags: `registry_config, service_task, installer_update`

## callers

- `0x18000bac8`

## callees

- `0x1800020c0`
- `0x180004dcc`
- `0x18000b94c`
- `0x18000cbbc`
- `0x18000cc14`
- `0x18000d034`
- `0x18000d12c`
- `0x18000d228`
- `0x18000d34c`
- `0x18000d578`
- `0x18000d668`
- `0x18000da28`
- `0x18000da84`
- `0x18000db34`
- `0x18000dbe4`
- `0x18000dc94`
- `0x18000dedc`

## pseudocode

```c
void __fastcall DeviceConfiguration::WNFListener::SubscribeToWNFNotifications(DeviceConfiguration::WNFListener *this)
{
  bool IsWindowsProtectedPrintEnabled; // al
  DeviceConfiguration::WNFListener *v3; // rcx
  __int64 v4; // rcx
  int v5; // eax
  __int64 v6; // rcx
  __int64 v7; // rdx
  __int64 v8; // rax
  __int64 v9; // rcx
  __int64 v10; // rdx
  __int64 v11; // rax
  wil *v12; // rcx
  bool *v13; // r8
  struct wil::WNF_CHANGE_STAMP_STRUCT *v14; // r9
  int v15; // eax
  wil::details::in1diag3 *v16; // rcx
  int v17; // eax
  const char *v18; // r9
  _WNF_STATE_NAME v19; // [rsp+20h] [rbp-B8h] BYREF
  int v20; // [rsp+28h] [rbp-B0h] BYREF
  __int128 v21; // [rsp+30h] [rbp-A8h] BYREF
  __int128 v22; // [rsp+40h] [rbp-98h] BYREF
  _BYTE v23[8]; // [rsp+50h] [rbp-88h] BYREF
  __int64 (__fastcall **v24)(); // [rsp+58h] [rbp-80h] BYREF
  __int64 v25; // [rsp+60h] [rbp-78h]
  __int64 (__fastcall ***v26)(); // [rsp+C0h] [rbp-18h]
  wil::details::in1diag3 *retaddr; // [rsp+D8h] [rbp+0h]

  IsWindowsProtectedPrintEnabled = PrintCore::WindowsProtectedPrintHelpers::IsWindowsProtectedPrintEnabled();
  try
  {
    if ( IsWindowsProtectedPrintEnabled && DeviceConfiguration::WNFListener::_IsWPPConfigurationNeededAfterUpgrade(v3) )
    {
      v20 = 0;
      LOBYTE(v19.Data[0]) = 0;
      v5 = wil::wnf_query_nothrow<unsigned long>(v4, &v19, &v20);
      if ( v5 < 0 )
        wil::details::in1diag3::_Throw_Hr(
          retaddr,
          (void *)0x34B,
          (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\resource.h",
          (const char *)(unsigned int)v5,
          v19.Data[0]);
      if ( LOBYTE(v19.Data[0]) && v20 )
        DeviceConfiguration::WNFListener::_NotifyWindowsProtectedPrintUpgradeRepair(this);
    }
    v6 = *(_QWORD *)lambda_92da9c469b5a6e0384834bfaf56dd9a1_::_lambda_92da9c469b5a6e0384834bfaf56dd9a1_(&v21, this);
    v24 = off_180019190;
    v25 = v6;
    v26 = &v24;
    v8 = wil::make_wnf_subscription<wil::details::empty_wnf_state>(&v20, v7, v23);
    wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<wil::details::wnf_subscription_state_base *,void (*)(wil::details::wnf_subscription_state_base *),&void wil::details::delete_wnf_subscription_state(wil::details::wnf_subscription_state_base *),wistd::integral_constant<unsigned __int64,2>,wil::details::wnf_subscription_state_base *,wil::details::wnf_subscription_state_base *,0,std::nullptr_t>>>::operator=(
      (char *)this + 16,
      v8);
    wil::details::unique_storage<wil::details::resource_policy<wil::details::wnf_subscription_state_base *,void (*)(wil::details::wnf_subscription_state_base *),&void wil::details::delete_wnf_subscription_state(wil::details::wnf_subscription_state_base *),wistd::integral_constant<unsigned __int64,2>,wil::details::wnf_subscription_state_base *,wil::details::wnf_subscription_state_base *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<wil::details::wnf_subscription_state_base *,void (*)(wil::details::wnf_subscription_state_base *),&void wil::details::delete_wnf_subscription_state(wil::details::wnf_subscription_state_base *),wistd::integral_constant<unsigned __int64,2>,wil::details::wnf_subscription_state_base *,wil::details::wnf_subscription_state_base *,0,std::nullptr_t>>(&v20);
    wistd::function<void (PrintCore::_WindowsProtectedPrintNotificationData const &)>::~function<void (PrintCore::_WindowsProtectedPrintNotificationData const &)>(v23);
    v9 = *(_QWORD *)lambda_92da9c469b5a6e0384834bfaf56dd9a1_::_lambda_92da9c469b5a6e0384834bfaf56dd9a1_(&v21, this);
    v24 = off_180019168;
    v25 = v9;
    v26 = &v24;
    v11 = wil::make_wnf_subscription<PrintCore::_WindowsProtectedPrintNotificationData>(&v20, v10, v23);
    wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<wil::details::wnf_subscription_state_base *,void (*)(wil::details::wnf_subscription_state_base *),&void wil::details::delete_wnf_subscription_state(wil::details::wnf_subscription_state_base *),wistd::integral_constant<unsigned __int64,2>,wil::details::wnf_subscription_state_base *,wil::details::wnf_subscription_state_base *,0,std::nullptr_t>>>::operator=(
      (char *)this + 40,
      v11);
    wil::details::unique_storage<wil::details::resource_policy<wil::details::wnf_subscription_state_base *,void (*)(wil::details::wnf_subscription_state_base *),&void wil::details::delete_wnf_subscription_state(wil::details::wnf_subscription_state_base *),wistd::integral_constant<unsigned __int64,2>,wil::details::wnf_subscription_state_base *,wil::details::wnf_subscription_state_base *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<wil::details::wnf_subscription_state_base *,void (*)(wil::details::wnf_subscription_state_base *),&void wil::details::delete_wnf_subscription_state(wil::details::wnf_subscription_state_base *),wistd::integral_constant<unsigned __int64,2>,wil::details::wnf_subscription_state_base *,wil::details::wnf_subscription_state_base *,0,std::nullptr_t>>(&v20);
    wistd::function<void (PrintCore::_WindowsProtectedPrintNotificationData const &)>::~function<void (PrintCore::_WindowsProtectedPrintNotificationData const &)>(v23);
    LOBYTE(v19.Data[0]) = 0;
    v15 = wil::wnf_query_nothrow(v12, &v19, v13, v14);
    v16 = retaddr;
    if ( v15 < 0 )
      wil::details::in1diag3::_Throw_Hr(
        retaddr,
        (void *)0x353,
        (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\resource.h",
        (const char *)(unsigned int)v15,
        v19.Data[0]);
    if ( LOBYTE(v19.Data[0]) )
      DeviceConfiguration::WNFListener::_NotifyUnconfiguredDeviceArrival(this);
    v22 = 0;
    LOBYTE(v19.Data[0]) = 0;
    v17 = wil::wnf_query_nothrow<PrintCore::_WindowsProtectedPrintNotificationData>(v16, &v19, &v22);
    if ( v17 < 0 )
      wil::details::in1diag3::_Throw_Hr(
        retaddr,
        (void *)0x34B,
        (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\resource.h",
        (const char *)(unsigned int)v17,
        v19.Data[0]);
    if ( LOBYTE(v19.Data[0]) && !(_DWORD)v22 )
    {
      v21 = v22;
      DeviceConfiguration::WNFListener::_NotifyWindowsProtectedPrintConfigurationChange(this, (__int64)&v21);
    }
  }
  catch ( ... )
  {
    wil::details::in1diag3::Log_CaughtException(
      retaddr,
      (void *)0x61,
      (unsigned int)"printscan\\print\\spooler\\configuration\\deviceconfigurationservice\\lib\\wnflistener.cpp",
      v18);
  }
}

```

## disassembly

```asm
0x18000d668  push    rbx
0x18000d66a  sub     rsp, 0D0h
0x18000d671  mov     rax, cs:__security_cookie
0x18000d678  xor     rax, rsp
0x18000d67b  mov     [rsp+0D8h+var_10], rax
0x18000d683  mov     rbx, rcx
0x18000d686  call    ?IsWindowsProtectedPrintEnabled@WindowsProtectedPrintHelpers@PrintCore@@SA_NXZ; PrintCore::WindowsProtectedPrintHelpers::IsWindowsProtectedPrintEnabled(void)
0x18000d68b  test    al, al
0x18000d68d  jz      short loc_18000D6EA
0x18000d68f  call    ?_IsWPPConfigurationNeededAfterUpgrade@WNFListener@DeviceConfiguration@@AEAA_NXZ; DeviceConfiguration::WNFListener::_IsWPPConfigurationNeededAfterUpgrade(void)
0x18000d694  test    al, al
0x18000d696  jz      short loc_18000D6EA
0x18000d698  mov     [rsp+0D8h+var_B0], 0
0x18000d6a0  mov     byte ptr [rsp+0D8h+var_B8.Data], 0; int
0x18000d6a5  lea     r8, [rsp+0D8h+var_B0]
0x18000d6aa  lea     rdx, [rsp+0D8h+var_B8]
0x18000d6af  call    ??$wnf_query_nothrow@K@wil@@YAJAEBU_WNF_STATE_NAME@@PEA_NPEAKPEAUWNF_CHANGE_STAMP_STRUCT@0@@Z; wil::wnf_query_nothrow<ulong>(_WNF_STATE_NAME const &,bool *,ulong *,wil::WNF_CHANGE_STAMP_STRUCT *)
0x18000d6b4  mov     rcx, [rsp+0D8h]; this
0x18000d6bc  test    eax, eax
0x18000d6be  jns     short loc_18000D6D4
0x18000d6c0  mov     r9d, eax; char *
0x18000d6c3  lea     r8, aOnecoreInterna_0; "onecore\\internal\\sdk\\inc\\wil\\resou"...
0x18000d6ca  mov     edx, 34Bh; void *
0x18000d6cf  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x18000d6d4  cmp     byte ptr [rsp+0D8h+var_B8.Data], 0
0x18000d6d9  jz      short loc_18000D6EA
0x18000d6db  cmp     [rsp+0D8h+var_B0], 0
0x18000d6e0  jz      short loc_18000D6EA
0x18000d6e2  mov     rcx, rbx; this
0x18000d6e5  call    ?_NotifyWindowsProtectedPrintUpgradeRepair@WNFListener@DeviceConfiguration@@AEAAXXZ; DeviceConfiguration::WNFListener::_NotifyWindowsProtectedPrintUpgradeRepair(void)
0x18000d6ea  mov     rdx, rbx
0x18000d6ed  lea     rcx, [rsp+0D8h+var_A8]
0x18000d6f2  call    _lambda_92da9c469b5a6e0384834bfaf56dd9a1____lambda_92da9c469b5a6e0384834bfaf56dd9a1_
0x18000d6f7  mov     rcx, [rax]
0x18000d6fa  lea     rax, off_180019190
0x18000d701  mov     [rsp+0D8h+var_80], rax
0x18000d706  mov     [rsp+0D8h+var_78], rcx
0x18000d70b  lea     rax, [rsp+0D8h+var_80]
0x18000d710  mov     [rsp+0D8h+var_18], rax
0x18000d718  lea     r8, [rsp+0D8h+var_88]
0x18000d71d  lea     rcx, [rsp+0D8h+var_B0]
0x18000d722  call    ??$make_wnf_subscription@Uempty_wnf_state@details@wil@@@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUwnf_subscription_state_base@details@wil@@P6AXPEAU123@@Z$1?delete_wnf_subscription_state@23@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAU123@PEAU123@$0A@$$T@details@wil@@@details@wil@@@0@AEBU_WNF_STATE_NAME@@$$QEAV?$function@$$A6AXXZ@wistd@@K@Z; wil::make_wnf_subscription<wil::details::empty_wnf_state>(_WNF_STATE_NAME const &,wistd::function<void (void)> &&,ulong)
0x18000d727  lea     rcx, [rbx+10h]
0x18000d72b  mov     rdx, rax
0x18000d72e  call    ??4?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUwnf_subscription_state_base@details@wil@@P6AXPEAU123@@Z$1?delete_wnf_subscription_state@23@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAU123@PEAU123@$0A@$$T@details@wil@@@details@wil@@@wil@@QEAAAEAV01@$$QEAV01@@Z; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<wil::details::wnf_subscription_state_base *,void (*)(wil::details::wnf_subscription_state_base *),&wil::details::delete_wnf_subscription_state(wil::details::wnf_subscription_state_base *),wistd::integral_constant<unsigned __int64,2>,wil::details::wnf_subscription_state_base *,wil::details::wnf_subscription_state_base *,0,std::nullptr_t>>>::operator=(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<wil::details::wnf_subscription_state_base *,void (*)(wil::details::wnf_subscription_state_base *),&wil::details::delete_wnf_subscription_state(wil::details::wnf_subscription_state_base *),wistd::integral_constant<unsigned __int64,2>,wil::details::wnf_subscription_state_base *,wil::details::wnf_subscription_state_base *,0,std::nullptr_t>>> &&)
0x18000d733  lea     rcx, [rsp+0D8h+var_B0]
0x18000d738  call    ??1?$unique_storage@U?$resource_policy@PEAUwnf_subscription_state_base@details@wil@@P6AXPEAU123@@Z$1?delete_wnf_subscription_state@23@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAU123@PEAU123@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<wil::details::wnf_subscription_state_base *,void (*)(wil::details::wnf_subscription_state_base *),&wil::details::delete_wnf_subscription_state(wil::details::wnf_subscription_state_base *),wistd::integral_constant<unsigned __int64,2>,wil::details::wnf_subscription_state_base *,wil::details::wnf_subscription_state_base *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<wil::details::wnf_subscription_state_base *,void (*)(wil::details::wnf_subscription_state_base *),&wil::details::delete_wnf_subscription_state(wil::details::wnf_subscription_state_base *),wistd::integral_constant<unsigned __int64,2>,wil::details::wnf_subscription_state_base *,wil::details::wnf_subscription_state_base *,0,std::nullptr_t>>(void)
0x18000d73d  nop
0x18000d73e  lea     rcx, [rsp+0D8h+var_88]
0x18000d743  call    ??1?$function@$$A6AXAEBU_WindowsProtectedPrintNotificationData@PrintCore@@@Z@wistd@@QEAA@XZ; wistd::function<void (PrintCore::_WindowsProtectedPrintNotificationData const &)>::~function<void (PrintCore::_WindowsProtectedPrintNotificationData const &)>(void)
0x18000d748  mov     rdx, rbx
0x18000d74b  lea     rcx, [rsp+0D8h+var_A8]
0x18000d750  call    _lambda_92da9c469b5a6e0384834bfaf56dd9a1____lambda_92da9c469b5a6e0384834bfaf56dd9a1_
0x18000d755  mov     rcx, [rax]
0x18000d758  lea     rax, off_180019168
0x18000d75f  mov     [rsp+0D8h+var_80], rax
0x18000d764  mov     [rsp+0D8h+var_78], rcx
0x18000d769  lea     rax, [rsp+0D8h+var_80]
0x18000d76e  mov     [rsp+0D8h+var_18], rax
0x18000d776  lea     r8, [rsp+0D8h+var_88]
0x18000d77b  lea     rcx, [rsp+0D8h+var_B0]
0x18000d780  call    ??$make_wnf_subscription@U_WindowsProtectedPrintNotificationData@PrintCore@@@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUwnf_subscription_state_base@details@wil@@P6AXPEAU123@@Z$1?delete_wnf_subscription_state@23@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAU123@PEAU123@$0A@$$T@details@wil@@@details@wil@@@0@AEBU_WNF_STATE_NAME@@$$QEAV?$function@$$A6AXAEBU_WindowsProtectedPrintNotificationData@PrintCore@@@Z@wistd@@K@Z; wil::make_wnf_subscription<PrintCore::_WindowsProtectedPrintNotificationData>(_WNF_STATE_NAME const &,wistd::function<void (PrintCore::_WindowsProtectedPrintNotificationData const &)> &&,ulong)
0x18000d785  lea     rcx, [rbx+28h]
0x18000d789  mov     rdx, rax
0x18000d78c  call    ??4?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUwnf_subscription_state_base@details@wil@@P6AXPEAU123@@Z$1?delete_wnf_subscription_state@23@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAU123@PEAU123@$0A@$$T@details@wil@@@details@wil@@@wil@@QEAAAEAV01@$$QEAV01@@Z; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<wil::details::wnf_subscription_state_base *,void (*)(wil::details::wnf_subscription_state_base *),&wil::details::delete_wnf_subscription_state(wil::details::wnf_subscription_state_base *),wistd::integral_constant<unsigned __int64,2>,wil::details::wnf_subscription_state_base *,wil::details::wnf_subscription_state_base *,0,std::nullptr_t>>>::operator=(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<wil::details::wnf_subscription_state_base *,void (*)(wil::details::wnf_subscription_state_base *),&wil::details::delete_wnf_subscription_state(wil::details::wnf_subscription_state_base *),wistd::integral_constant<unsigned __int64,2>,wil::details::wnf_subscription_state_base *,wil::details::wnf_subscription_state_base *,0,std::nullptr_t>>> &&)
0x18000d791  lea     rcx, [rsp+0D8h+var_B0]
0x18000d796  call    ??1?$unique_storage@U?$resource_policy@PEAUwnf_subscription_state_base@details@wil@@P6AXPEAU123@@Z$1?delete_wnf_subscription_state@23@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAU123@PEAU123@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<wil::details::wnf_subscription_state_base *,void (*)(wil::details::wnf_subscription_state_base *),&wil::details::delete_wnf_subscription_state(wil::details::wnf_subscription_state_base *),wistd::integral_constant<unsigned __int64,2>,wil::details::wnf_subscription_state_base *,wil::details::wnf_subscription_state_base *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<wil::details::wnf_subscription_state_base *,void (*)(wil::details::wnf_subscription_state_base *),&wil::details::delete_wnf_subscription_state(wil::details::wnf_subscription_state_base *),wistd::integral_constant<unsigned __int64,2>,wil::details::wnf_subscription_state_base *,wil::details::wnf_subscription_state_base *,0,std::nullptr_t>>(void)
0x18000d79b  nop
0x18000d79c  lea     rcx, [rsp+0D8h+var_88]
0x18000d7a1  call    ??1?$function@$$A6AXAEBU_WindowsProtectedPrintNotificationData@PrintCore@@@Z@wistd@@QEAA@XZ; wistd::function<void (PrintCore::_WindowsProtectedPrintNotificationData const &)>::~function<void (PrintCore::_WindowsProtectedPrintNotificationData const &)>(void)
0x18000d7a6  mov     byte ptr [rsp+0D8h+var_B8.Data], 0; int
0x18000d7ab  lea     rdx, [rsp+0D8h+var_B8]; struct _WNF_STATE_NAME *
0x18000d7b0  call    ?wnf_query_nothrow@wil@@YAJAEBU_WNF_STATE_NAME@@PEA_NPEAUWNF_CHANGE_STAMP_STRUCT@1@@Z; wil::wnf_query_nothrow(_WNF_STATE_NAME const &,bool *,wil::WNF_CHANGE_STAMP_STRUCT *)
0x18000d7b5  mov     rcx, [rsp+0D8h]; this
0x18000d7bd  test    eax, eax
0x18000d7bf  jns     short loc_18000D7D5
0x18000d7c1  mov     r9d, eax; char *
0x18000d7c4  lea     r8, aOnecoreInterna_0; "onecore\\internal\\sdk\\inc\\wil\\resou"...
0x18000d7cb  mov     edx, 353h; void *
0x18000d7d0  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x18000d7d5  cmp     byte ptr [rsp+0D8h+var_B8.Data], 0
0x18000d7da  jz      short loc_18000D7E4
0x18000d7dc  mov     rcx, rbx; this
0x18000d7df  call    ?_NotifyUnconfiguredDeviceArrival@WNFListener@DeviceConfiguration@@AEAAXXZ; DeviceConfiguration::WNFListener::_NotifyUnconfiguredDeviceArrival(void)
0x18000d7e4  xorps   xmm0, xmm0
0x18000d7e7  movups  [rsp+0D8h+var_98], xmm0
0x18000d7ec  mov     byte ptr [rsp+0D8h+var_B8.Data], 0; int
0x18000d7f1  lea     r8, [rsp+0D8h+var_98]
0x18000d7f6  lea     rdx, [rsp+0D8h+var_B8]
0x18000d7fb  call    ??$wnf_query_nothrow@U_WindowsProtectedPrintNotificationData@PrintCore@@@wil@@YAJAEBU_WNF_STATE_NAME@@PEA_NPEAU_WindowsProtectedPrintNotificationData@PrintCore@@PEAUWNF_CHANGE_STAMP_STRUCT@0@@Z; wil::wnf_query_nothrow<PrintCore::_WindowsProtectedPrintNotificationData>(_WNF_STATE_NAME const &,bool *,PrintCore::_WindowsProtectedPrintNotificationData *,wil::WNF_CHANGE_STAMP_STRUCT *)
0x18000d800  mov     rcx, [rsp+0D8h]; this
0x18000d808  test    eax, eax
0x18000d80a  jns     short loc_18000D820
0x18000d80c  mov     r9d, eax; char *
0x18000d80f  lea     r8, aOnecoreInterna_0; "onecore\\internal\\sdk\\inc\\wil\\resou"...
0x18000d816  mov     edx, 34Bh; void *
0x18000d81b  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x18000d820  cmp     byte ptr [rsp+0D8h+var_B8.Data], 0
0x18000d825  jz      short loc_18000D847
0x18000d827  cmp     dword ptr [rsp+0D8h+var_98], 0
0x18000d82c  jnz     short loc_18000D847
0x18000d82e  movaps  xmm0, [rsp+0D8h+var_98]
0x18000d833  movdqa  [rsp+0D8h+var_A8], xmm0
0x18000d839  lea     rdx, [rsp+0D8h+var_A8]
0x18000d83e  mov     rcx, rbx
0x18000d841  call    ?_NotifyWindowsProtectedPrintConfigurationChange@WNFListener@DeviceConfiguration@@AEAAXU_WindowsProtectedPrintNotificationData@PrintCore@@@Z; DeviceConfiguration::WNFListener::_NotifyWindowsProtectedPrintConfigurationChange(PrintCore::_WindowsProtectedPrintNotificationData)
0x18000d846  nop
0x18000d847  jmp     short $+2
0x18000d849  mov     rcx, [rsp+0D8h+var_10]
0x18000d851  xor     rcx, rsp; StackCookie
0x18000d854  call    __security_check_cookie
0x18000d859  add     rsp, 0D0h
0x18000d860  pop     rbx
0x18000d861  retn
```
