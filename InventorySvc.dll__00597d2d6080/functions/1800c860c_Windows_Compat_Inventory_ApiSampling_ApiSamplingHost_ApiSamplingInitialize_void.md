# Windows::Compat::Inventory::ApiSampling::ApiSamplingHost::ApiSamplingInitialize(void)

- ea: `0x1800c860c`
- end: `0x1800c88d1`
- name: `?ApiSamplingInitialize@ApiSamplingHost@ApiSampling@Inventory@Compat@Windows@@AEAAXXZ`
- size: `709`
- prototype: `void __fastcall(Windows::Compat::Inventory::ApiSampling::ApiSamplingHost *__hidden this)`
- caller_count: `2`
- callee_count: `12`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800c7cec`
- `0x1800c9a50`

## callees

- `0x1800108d4`
- `0x1800110f8`
- `0x1800152d0`
- `0x1800c0380`
- `0x1800c860c`
- `0x1800c8940`
- `0x1800c8ebc`
- `0x1800c9020`
- `0x1800c9150`
- `0x1800c92b8`
- `0x1800c98a8`
- `0x1800c99cc`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x1800c8863`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x1800c8863`
- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x1800c8636`
- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x1800c887d`
- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x1800c8636`
- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x1800c887d`
- `api-ms-win-power-setting-l1-1-0!PowerSettingRegisterNotification` at `0x1800c8809`
- `api-ms-win-power-setting-l1-1-0!PowerSettingRegisterNotification` at `0x1800c8834`
- `api-ms-win-power-setting-l1-1-0!PowerSettingRegisterNotification` at `0x1800c8809`
- `api-ms-win-power-setting-l1-1-0!PowerSettingRegisterNotification` at `0x1800c8834`

## string_xrefs

- `0x1800c88a8`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`
- `0x1800c8891`: `onecore\internal\sdk\inc\wil\opensource/wil/resource.h`
- `0x1800c88bf`: `onecore\internal\sdk\inc\wil\opensource/wil/resource.h`
- `0x1800c8769`: `Windows::Compat::Inventory::ApiSampling::ApiSamplingHost::IsEnabledByOneSettings`
- `0x1800c8694`: `Windows::Compat::Inventory::ApiSampling::ApiSamplingHost::ApiSamplingInitialize`
- `0x1800c86be`: `Windows::Compat::Inventory::ApiSampling::ApiSamplingHost::ApiSamplingInitialize`
- `0x1800c86f0`: `Windows::Compat::Inventory::ApiSampling::ApiSamplingHost::ApiSamplingInitialize`
- `0x1800c8795`: `Windows::Compat::Inventory::ApiSampling::ApiSamplingHost::ApiSamplingInitialize`
- `0x1800c884b`: `Windows::Compat::Inventory::ApiSampling::ApiSamplingHost::ApiSamplingInitialize`

## pseudocode

```c
void __fastcall Windows::Compat::Inventory::ApiSampling::ApiSamplingHost::ApiSamplingInitialize(
        Windows::Compat::Inventory::ApiSampling::ApiSamplingHost *this,
        __int64 a2,
        __int64 a3)
{
  HANDLE *v3; // rbx
  __int64 v5; // rcx
  const char *v6; // r9
  _QWORD *v7; // rsi
  int ApiSamplingOneSettingsKey; // eax
  const char *v9; // r9
  __int64 v10; // r8
  const char *v11; // r9
  __int64 v12; // r8
  int v13; // eax
  bool v14; // cc
  const char *v15; // rax
  unsigned __int64 v16; // rdx
  unsigned __int8 v17; // cl
  const char *v18; // r9
  const char *v19; // r9
  __int64 v20; // [rsp+20h] [rbp-28h]
  _QWORD Recipient[3]; // [rsp+30h] [rbp-18h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+0h]
  int v23; // [rsp+50h] [rbp+8h] BYREF

  v3 = (HANDLE *)((char *)this + 8);
  if ( !*((_QWORD *)this + 1) )
    _create___event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_exception_policy_3__wil__QEAAXW4EventOptions_2_PEBGPEAU_SECURITY_ATTRIBUTES__PEA_N_Z(
      (char *)this + 8,
      a2,
      a3,
      0);
  if ( !ResetEvent(*v3) )
    wil::details::in1diag3::_FailFast_GetLastError(
      retaddr,
      (void *)0xA06,
      (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource/wil/resource.h",
      v6);
  v7 = (_QWORD *)((char *)this + 56);
  if ( !*((_QWORD *)this + 9) )
  {
    ApiSamplingOneSettingsKey = Windows::Compat::Inventory::ApiSampling::ApiSamplingHost::GetApiSamplingOneSettingsKey(
                                  v5,
                                  (char **)this + 7);
    if ( ApiSamplingOneSettingsKey )
    {
      v9 = "GetApiSamplingOneSettingsKey failed [%d]";
      v10 = 729;
LABEL_28:
      LODWORD(v20) = ApiSamplingOneSettingsKey;
      AslLogCallPrintf(
        1,
        "Windows::Compat::Inventory::ApiSampling::ApiSamplingHost::ApiSamplingInitialize",
        v10,
        v9,
        v20);
LABEL_29:
      if ( !SetEvent(*v3) )
        wil::details::in1diag3::_FailFast_GetLastError(
          retaddr,
          (void *)0xA01,
          (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\resource.h",
          v18);
      return;
    }
  }
  if ( !Windows::Compat::Inventory::ApiSampling::ApiSamplingHost::IsApiSamplingTestOverride(this) && IsWindowsServer() )
  {
    v11 = "API Sampling not supported for Server. Skipping initialization.";
    v12 = 736;
LABEL_10:
    AslLogCallPrintf(3, "Windows::Compat::Inventory::ApiSampling::ApiSamplingHost::ApiSamplingInitialize", v12, v11);
    goto LABEL_29;
  }
  if ( Windows::Compat::Inventory::ApiSampling::ApiSamplingHost::IsApiSamplingTestOverride(this) )
  {
    AslLogCallPrintf(
      3,
      "Windows::Compat::Inventory::ApiSampling::ApiSamplingHost::ApiSamplingInitialize",
      743,
      "Initializing ApiSampling for test.");
    v13 = Windows::Compat::Inventory::ApiSampling::ApiSamplingHost::LazyApiSamplingInitialize(this);
    if ( v13 < 0 )
    {
      AslLogCallPrintf(
        1,
        "Windows::Compat::Inventory::ApiSampling::ApiSamplingHost::ApiSamplingInitialize",
        747,
        "LazyApiSamplingInitialize failed [%#x]",
        v13);
      return;
    }
  }
  else
  {
    v14 = *((_QWORD *)this + 10) <= 7u;
    v23 = 0;
    if ( !v14 )
      v7 = (_QWORD *)*v7;
    Windows::Compat::Shared::RegistryKeyWrapper<-2147483646>::ReadDword(&v23, 0, v7, L"DynApiEnabled");
    v15 = "en";
    if ( v23 != 1 )
      v15 = "dis";
    AslLogCallPrintf(
      3,
      "Windows::Compat::Inventory::ApiSampling::ApiSamplingHost::IsEnabledByOneSettings",
      570,
      "ApiSampling is %sabled by OneSettings",
      v15);
    if ( v23 != 1 )
    {
      v11 = "ApiSampling is disabled by OneSettings.";
      v12 = 758;
      goto LABEL_10;
    }
    if ( !CovSampler::CTraceLog::IsEnabled(v17, v16) )
    {
      AslLogCallPrintf(
        3,
        "Windows::Compat::Inventory::ApiSampling::ApiSamplingHost::ApiSamplingInitialize",
        765,
        "ApiSampling TraceloggingProvider is disabled (sampled out).");
      goto LABEL_29;
    }
    AslLogCallPrintf(
      3,
      "Windows::Compat::Inventory::ApiSampling::ApiSamplingHost::ApiSamplingInitialize",
      770,
      "ApiSampling TraceloggingProvider is enabled.");
    if ( !Windows::Compat::Inventory::ApiSampling::ApiSamplingHost::MachineMeetsMinimumSpecs(this) )
    {
      v11 = "ApiSampling minimum machine specs not met.";
      v12 = 778;
      goto LABEL_10;
    }
    Recipient[1] = this;
    Recipient[0] = Windows::Compat::Inventory::ApiSampling::ApiSamplingHost::PowerNotificationCallback;
    ApiSamplingOneSettingsKey = PowerSettingRegisterNotification(
                                  &GUID_POWER_SAVING_STATUS,
                                  2u,
                                  Recipient,
                                  (PHPOWERNOTIFY)this + 3);
    if ( ApiSamplingOneSettingsKey )
    {
      v9 = "Failed to register GUID_POWER_SAVING_STATUS [%d]";
      v10 = 795;
      goto LABEL_28;
    }
    ApiSamplingOneSettingsKey = PowerSettingRegisterNotification(
                                  &GUID_POWERSCHEME_PERSONALITY,
                                  2u,
                                  Recipient,
                                  (PHPOWERNOTIFY)this + 4);
    if ( ApiSamplingOneSettingsKey )
    {
      v9 = "Failed to register GUID_POWERSCHEME_PERSONALITY [%d]";
      v10 = 803;
      goto LABEL_28;
    }
    Windows::Compat::Inventory::ApiSampling::ApiSamplingHost::QueryApiSamplingOneSettings(this);
  }
  if ( !ResetEvent(*v3) )
    wil::details::in1diag3::_FailFast_GetLastError(
      retaddr,
      (void *)0xA06,
      (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource/wil/resource.h",
      v19);
}

```

## disassembly

```asm
0x1800c860c  mov     [rsp+arg_8], rbx
0x1800c8611  mov     [rsp+arg_10], rsi
0x1800c8616  push    rdi
0x1800c8617  sub     rsp, 40h
0x1800c861b  lea     rbx, [rcx+8]
0x1800c861f  mov     rdi, rcx
0x1800c8622  cmp     qword ptr [rbx], 0
0x1800c8626  jnz     short loc_1800C8633
0x1800c8628  xor     r9d, r9d
0x1800c862b  mov     rcx, rbx
0x1800c862e  call    ?create@?$event_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_exception_policy@3@@wil@@QEAAXW4EventOptions@2@PEBGPEAU_SECURITY_ATTRIBUTES@@PEA_N@Z
0x1800c8633  mov     rcx, [rbx]; hEvent
0x1800c8636  call    cs:__imp_ResetEvent
0x1800c863c  test    eax, eax
0x1800c863e  jz      loc_1800C888C
0x1800c8644  lea     rsi, [rdi+38h]
0x1800c8648  cmp     qword ptr [rsi+10h], 0
0x1800c864d  jnz     short loc_1800C866D
0x1800c864f  mov     rdx, rsi
0x1800c8652  call    ?GetApiSamplingOneSettingsKey@ApiSamplingHost@ApiSampling@Inventory@Compat@Windows@@AEAAKAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; Windows::Compat::Inventory::ApiSampling::ApiSamplingHost::GetApiSamplingOneSettingsKey(std::wstring &)
0x1800c8657  test    eax, eax
0x1800c8659  jz      short loc_1800C866D
0x1800c865b  lea     r9, aGetapisampling; "GetApiSamplingOneSettingsKey failed [%d"...
0x1800c8662  mov     r8d, 2D9h
0x1800c8668  jmp     loc_1800C884B
0x1800c866d  mov     rcx, rdi; this
0x1800c8670  call    ?IsApiSamplingTestOverride@ApiSamplingHost@ApiSampling@Inventory@Compat@Windows@@AEAA_NXZ; Windows::Compat::Inventory::ApiSampling::ApiSamplingHost::IsApiSamplingTestOverride(void)
0x1800c8675  test    al, al
0x1800c8677  jnz     short loc_1800C86A5
0x1800c8679  call    ?IsWindowsServer@@YA_NXZ; IsWindowsServer(void)
0x1800c867e  test    al, al
0x1800c8680  jz      short loc_1800C86A5
0x1800c8682  lea     r9, aApiSamplingNot; "API Sampling not supported for Server. "...
0x1800c8689  mov     r8d, 2E0h
0x1800c868f  mov     ecx, 3
0x1800c8694  lea     rdx, aWindowsCompatI_81; "Windows::Compat::Inventory::ApiSampling"...
0x1800c869b  call    AslLogCallPrintf
0x1800c86a0  jmp     loc_1800C8860
0x1800c86a5  mov     rcx, rdi; this
0x1800c86a8  call    ?IsApiSamplingTestOverride@ApiSamplingHost@ApiSampling@Inventory@Compat@Windows@@AEAA_NXZ; Windows::Compat::Inventory::ApiSampling::ApiSamplingHost::IsApiSamplingTestOverride(void)
0x1800c86ad  test    al, al
0x1800c86af  jz      short loc_1800C8711
0x1800c86b1  lea     r9, aInitializingAp; "Initializing ApiSampling for test."
0x1800c86b8  mov     r8d, 2E7h
0x1800c86be  lea     rdx, aWindowsCompatI_81; "Windows::Compat::Inventory::ApiSampling"...
0x1800c86c5  mov     ecx, 3
0x1800c86ca  call    AslLogCallPrintf
0x1800c86cf  mov     rcx, rdi; this
0x1800c86d2  call    ?LazyApiSamplingInitialize@ApiSamplingHost@ApiSampling@Inventory@Compat@Windows@@AEAAJXZ; Windows::Compat::Inventory::ApiSampling::ApiSamplingHost::LazyApiSamplingInitialize(void)
0x1800c86d7  test    eax, eax
0x1800c86d9  jns     loc_1800C887A
0x1800c86df  lea     r9, aLazyapisamplin; "LazyApiSamplingInitialize failed [%#x]"
0x1800c86e6  mov     dword ptr [rsp+48h+var_28], eax
0x1800c86ea  mov     r8d, 2EBh
0x1800c86f0  lea     rdx, aWindowsCompatI_81; "Windows::Compat::Inventory::ApiSampling"...
0x1800c86f7  mov     ecx, 1
0x1800c86fc  call    AslLogCallPrintf
0x1800c8701  mov     rbx, [rsp+48h+arg_8]
0x1800c8706  mov     rsi, [rsp+48h+arg_10]
0x1800c870b  add     rsp, 40h
0x1800c870f  pop     rdi
0x1800c8710  retn
0x1800c8711  cmp     qword ptr [rsi+18h], 7
0x1800c8716  mov     [rsp+48h+arg_0], 0
0x1800c871e  jbe     short loc_1800C8723
0x1800c8720  mov     rsi, [rsi]
0x1800c8723  lea     r9, ?DynApiEnabled@ApiSamplingHost@ApiSampling@Inventory@Compat@Windows@@0QBGB; "DynApiEnabled"
0x1800c872a  mov     r8, rsi
0x1800c872d  xor     edx, edx
0x1800c872f  lea     rcx, [rsp+48h+arg_0]
0x1800c8734  call    ?ReadDword@?$RegistryKeyWrapper@$0?HPPPPPPO@@Shared@Compat@Windows@@SAJAEAKKPEBG1@Z; Windows::Compat::Shared::RegistryKeyWrapper<-2147483646>::ReadDword(ulong &,ulong,ushort const *,ushort const *)
0x1800c8739  cmp     [rsp+48h+arg_0], 1
0x1800c873e  lea     rcx, aDis; "dis"
0x1800c8745  lea     rax, aEn; "en"
0x1800c874c  mov     esi, 3
0x1800c8751  cmovnz  rax, rcx
0x1800c8755  lea     r9, aApisamplingIsS; "ApiSampling is %sabled by OneSettings"
0x1800c875c  mov     ecx, esi
0x1800c875e  mov     [rsp+48h+var_28], rax
0x1800c8763  mov     r8d, 23Ah
0x1800c8769  lea     rdx, aWindowsCompatI_80; "Windows::Compat::Inventory::ApiSampling"...
0x1800c8770  call    AslLogCallPrintf
0x1800c8775  cmp     [rsp+48h+arg_0], 1
0x1800c877a  jz      short loc_1800C8790
0x1800c877c  lea     r9, aApisamplingIsD; "ApiSampling is disabled by OneSettings."
0x1800c8783  mov     r8d, 2F6h
0x1800c8789  mov     ecx, esi
0x1800c878b  jmp     loc_1800C8694
0x1800c8790  call    ?IsEnabled@CTraceLog@CovSampler@@SA_NE_K@Z; CovSampler::CTraceLog::IsEnabled(uchar,unsigned __int64)
0x1800c8795  lea     rdx, aWindowsCompatI_81; "Windows::Compat::Inventory::ApiSampling"...
0x1800c879c  mov     ecx, esi
0x1800c879e  test    al, al
0x1800c87a0  jnz     short loc_1800C87B4
0x1800c87a2  lea     r9, aApisamplingTra; "ApiSampling TraceloggingProvider is dis"...
0x1800c87a9  mov     r8d, 2FDh
0x1800c87af  jmp     loc_1800C869B
0x1800c87b4  lea     r9, aApisamplingTra_0; "ApiSampling TraceloggingProvider is ena"...
0x1800c87bb  mov     r8d, 302h
0x1800c87c1  call    AslLogCallPrintf
0x1800c87c6  mov     rcx, rdi; this
0x1800c87c9  call    ?MachineMeetsMinimumSpecs@ApiSamplingHost@ApiSampling@Inventory@Compat@Windows@@AEAA_NXZ; Windows::Compat::Inventory::ApiSampling::ApiSamplingHost::MachineMeetsMinimumSpecs(void)
0x1800c87ce  test    al, al
0x1800c87d0  jnz     short loc_1800C87E1
0x1800c87d2  lea     r9, aApisamplingMin; "ApiSampling minimum machine specs not m"...
0x1800c87d9  mov     r8d, 30Ah
0x1800c87df  jmp     short loc_1800C8789
0x1800c87e1  lea     rax, ?PowerNotificationCallback@ApiSamplingHost@ApiSampling@Inventory@Compat@Windows@@CAKPEAXK0@Z; Windows::Compat::Inventory::ApiSampling::ApiSamplingHost::PowerNotificationCallback(void *,ulong,void *)
0x1800c87e8  mov     [rsp+48h+var_10], rdi
0x1800c87ed  mov     esi, 2
0x1800c87f2  mov     [rsp+48h+Recipient], rax
0x1800c87f7  mov     edx, esi; Flags
0x1800c87f9  lea     r9, [rdi+18h]; RegistrationHandle
0x1800c87fd  lea     r8, [rsp+48h+Recipient]; Recipient
0x1800c8802  lea     rcx, GUID_POWER_SAVING_STATUS; SettingGuid
0x1800c8809  call    cs:__imp_PowerSettingRegisterNotification
0x1800c880f  test    eax, eax
0x1800c8811  jz      short loc_1800C8822
0x1800c8813  lea     r9, aFailedToRegist; "Failed to register GUID_POWER_SAVING_ST"...
0x1800c881a  mov     r8d, 31Bh
0x1800c8820  jmp     short loc_1800C884B
0x1800c8822  lea     r9, [rdi+20h]; RegistrationHandle
0x1800c8826  mov     edx, esi; Flags
0x1800c8828  lea     r8, [rsp+48h+Recipient]; Recipient
0x1800c882d  lea     rcx, GUID_POWERSCHEME_PERSONALITY; SettingGuid
0x1800c8834  call    cs:__imp_PowerSettingRegisterNotification
0x1800c883a  test    eax, eax
0x1800c883c  jz      short loc_1800C8872
0x1800c883e  lea     r9, aFailedToRegist_0; "Failed to register GUID_POWERSCHEME_PER"...
0x1800c8845  mov     r8d, 323h
0x1800c884b  lea     rdx, aWindowsCompatI_81; "Windows::Compat::Inventory::ApiSampling"...
0x1800c8852  mov     dword ptr [rsp+48h+var_28], eax
0x1800c8856  mov     ecx, 1
0x1800c885b  call    AslLogCallPrintf
0x1800c8860  mov     rcx, [rbx]; hEvent
0x1800c8863  call    cs:__imp_SetEvent
0x1800c8869  test    eax, eax
0x1800c886b  jz      short loc_1800C88A3
0x1800c886d  jmp     loc_1800C8701
0x1800c8872  mov     rcx, rdi; this
0x1800c8875  call    ?QueryApiSamplingOneSettings@ApiSamplingHost@ApiSampling@Inventory@Compat@Windows@@AEAAXXZ; Windows::Compat::Inventory::ApiSampling::ApiSamplingHost::QueryApiSamplingOneSettings(void)
0x1800c887a  mov     rcx, [rbx]; hEvent
0x1800c887d  call    cs:__imp_ResetEvent
0x1800c8883  test    eax, eax
0x1800c8885  jz      short loc_1800C88BA
0x1800c8887  jmp     loc_1800C8701
0x1800c888c  mov     rcx, [rsp+48h]; this
0x1800c8891  lea     r8, aOnecoreInterna_3; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x1800c8898  mov     edx, 0A06h; void *
0x1800c889d  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x1800c88a3  mov     rcx, [rsp+48h]; this
0x1800c88a8  lea     r8, aOnecoreInterna_0; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x1800c88af  mov     edx, 0A01h; void *
0x1800c88b4  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x1800c88ba  mov     rcx, [rsp+48h]; this
0x1800c88bf  lea     r8, aOnecoreInterna_3; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x1800c88c6  mov     edx, 0A06h; void *
0x1800c88cb  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
