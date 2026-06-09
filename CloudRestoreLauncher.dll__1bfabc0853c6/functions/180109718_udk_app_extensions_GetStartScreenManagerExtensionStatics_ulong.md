# udk::app_extensions::GetStartScreenManagerExtensionStatics(ulong)

- ea: `0x180109718`
- end: `0x180109a67`
- name: `?GetStartScreenManagerExtensionStatics@app_extensions@udk@@YA?AUIStartScreenManagerExtensionStatics@StartScreen@UI@WindowsUdk@winrt@@K@Z`
- size: `847`
- prototype: ``
- caller_count: `1`
- callee_count: `21`
- tags: `authz_impersonation, registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x1801077b0`

## callees

- `0x18000c6e0`
- `0x18001024c`
- `0x180012b84`
- `0x180012c0c`
- `0x18001315c`
- `0x1800161ec`
- `0x1800162a4`
- `0x180016cec`
- `0x180016d9c`
- `0x18001cfa4`
- `0x180028584`
- `0x1800285e8`
- `0x180037e04`
- `0x180101080`
- `0x1801010f0`
- `0x180101338`
- `0x180101b58`
- `0x1801025a8`
- `0x180105484`
- `0x180109718`
- `0x180109ce4`

## import_xrefs

- `twinapi.appcore!__imp_CoreQueryWindowService` at `0x1801099b6`
- `USER32!FindWindowW` at `0x18010995a`
- `USER32!FindWindowW` at `0x18010995a`

## string_xrefs

- `0x1801097ea`: `StartScreenManagerWindowService`
- `0x180109836`: `@ServiceClassId`
- `0x180109a56`: `shellcommon\internal\undockeddevkit\inc\udk\app_extension_helpers.h`
- `0x180109753`: `com.microsoft.windows.extension.windowservice.startmenu`

## pseudocode

```c
// Hidden C++ exception states: #wind=17
_QWORD *__fastcall udk::app_extensions::GetStartScreenManagerExtensionStatics(_QWORD *a1)
{
  _QWORD *v1; // rbx
  __int64 v2; // rcx
  __int64 v3; // rax
  __int64 v4; // rax
  __int64 v5; // rax
  __int64 v6; // rax
  __int64 v7; // rdx
  unsigned int v8; // r8d
  int v9; // r9d
  const WCHAR *v10; // rax
  LPCWSTR v11; // rdx
  __int64 v12; // rax
  const char *v13; // r9
  int v15; // [rsp+20h] [rbp-D8h]
  wil *v16; // [rsp+30h] [rbp-C8h] BYREF
  HWND WindowW; // [rsp+38h] [rbp-C0h] BYREF
  int v18; // [rsp+40h] [rbp-B8h]
  char v19[8]; // [rsp+48h] [rbp-B0h] BYREF
  __int64 v20; // [rsp+50h] [rbp-A8h] BYREF
  char v21[8]; // [rsp+58h] [rbp-A0h] BYREF
  char v22[8]; // [rsp+60h] [rbp-98h] BYREF
  char v23[8]; // [rsp+68h] [rbp-90h] BYREF
  char v24[8]; // [rsp+70h] [rbp-88h] BYREF
  __int64 *v25; // [rsp+78h] [rbp-80h] BYREF
  _QWORD *v26; // [rsp+80h] [rbp-78h]
  _BYTE v27[40]; // [rsp+88h] [rbp-70h] BYREF
  __int128 v28; // [rsp+B0h] [rbp-48h] BYREF
  _BYTE v29[32]; // [rsp+C0h] [rbp-38h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+F8h] [rbp+0h]

  v1 = a1;
  v26 = a1;
  *a1 = 0;
  v18 = 1;
  winrt::param::hstring::hstring(
    (winrt::param::hstring *)v27,
    L"com.microsoft.windows.extension.windowservice.startmenu");
  try
  {
    v16 = (wil *)v27;
    v25 = &qword_18017B108;
    _InterlockedIncrement64(&qword_18017B108);
    if ( winrt::impl::factory_cache_entry_v<winrt::WindowsUdk::ApplicationModel::AppExtensions::AppExtension,winrt::WindowsUdk::ApplicationModel::AppExtensions::IAppExtensionStatics> )
    {
      _lambda_e84bcefeb7ed3703767eef0b25e91c21_::operator()(
        &v16,
        &v20,
        &winrt::impl::factory_cache_entry_v<winrt::WindowsUdk::ApplicationModel::AppExtensions::AppExtension,winrt::WindowsUdk::ApplicationModel::AppExtensions::IAppExtensionStatics>);
      _InterlockedDecrement64(&qword_18017B108);
    }
    else
    {
      _InterlockedDecrement64(&qword_18017B108);
      winrt::impl::factory_cache_entry<winrt::WindowsUdk::ApplicationModel::AppExtensions::AppExtension,winrt::WindowsUdk::ApplicationModel::AppExtensions::IAppExtensionStatics>::call<_lambda_e84bcefeb7ed3703767eef0b25e91c21_ &>(
        v2,
        &v20,
        &v16);
    }
    v18 = 7;
    if ( v20 )
    {
      winrt::impl::consume_WindowsUdk_UI_StartScreen_ITile<winrt::WindowsUdk::UI::StartScreen::ITile>::SuiteName(
        &v20,
        v24);
      winrt::param::hstring::hstring((winrt::param::hstring *)v27, L"StartScreenManagerWindowService");
      v3 = winrt::impl::consume_Windows_Foundation_Collections_IMap<winrt::Windows::Foundation::Collections::IPropertySet,winrt::hstring,winrt::Windows::Foundation::IInspectable>::Lookup(
             v24,
             &v16,
             v27);
      winrt::Windows::Foundation::IUnknown::as<winrt::Windows::Foundation::Collections::IPropertySet>(v3, v19);
      if ( v16 )
        winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v16);
      winrt::param::hstring::hstring((winrt::param::hstring *)v29, L"@ServiceClassId");
      v4 = winrt::impl::consume_Windows_Foundation_Collections_IMap<winrt::Windows::Foundation::Collections::IPropertySet,winrt::hstring,winrt::Windows::Foundation::IInspectable>::Lookup(
             v19,
             &WindowW,
             v29);
      winrt::Windows::Foundation::IUnknown::as<winrt::hstring>(v4, v23);
      if ( WindowW )
        winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&WindowW);
      winrt::param::hstring::hstring((winrt::param::hstring *)v27, L"@WindowName");
      v5 = winrt::impl::consume_Windows_Foundation_Collections_IMap<winrt::Windows::Foundation::Collections::IPropertySet,winrt::hstring,winrt::Windows::Foundation::IInspectable>::Lookup(
             v19,
             &v16,
             v27);
      winrt::Windows::Foundation::IUnknown::as<winrt::hstring>(v5, v22);
      if ( v16 )
        winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v16);
      winrt::param::hstring::hstring((winrt::param::hstring *)v29, L"@ClassName");
      v6 = winrt::impl::consume_Windows_Foundation_Collections_IMap<winrt::Windows::Foundation::Collections::IPropertySet,winrt::hstring,winrt::Windows::Foundation::IInspectable>::Lookup(
             v19,
             &WindowW,
             v29);
      winrt::Windows::Foundation::IUnknown::as<winrt::hstring>(v6, v21);
      if ( WindowW )
        winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&WindowW);
      v16 = 0;
      _create___event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_exception_policy_3__wil__QEAAXW4EventOptions_2_PEBGPEAU_SECURITY_ATTRIBUTES__PEA_N_Z(
        &v16,
        v7,
        L"__StartScreenManagerWindowRegisteredEvent__");
      wil::handle_wait(v16, 0, v8, v9);
      winrt::hstring::c_str((winrt::hstring *)v22);
      v10 = winrt::hstring::c_str((winrt::hstring *)v21);
      WindowW = FindWindowW(v10, v11);
      if ( !WindowW )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x2E,
          (unsigned int)"shellcommon\\internal\\undockeddevkit\\inc\\udk\\app_extension_helpers.h",
          (const char *)0x80070490LL,
          v15);
      v28 = *(_OWORD *)winrt::hstring::operator std::basic_string_view<unsigned short>(v23, v27);
      winrt::guid::parse<std::basic_string_view<unsigned short>>(v29, &v28);
      v12 = winrt::capture<winrt::WindowsUdk::UI::StartScreen::IStartScreenManagerExtensionStatics,long (&)(HWND__ *,_GUID const &,_GUID const &,void * *),HWND__ * const &,winrt::guid>(
              &v25,
              CoreQueryWindowService,
              &WindowW,
              v29);
      winrt::Windows::Foundation::IUnknown::operator=(v1, v12);
      _lambda_12ef4a55c56a96ec7ad58335194b061f_::~_lambda_12ef4a55c56a96ec7ad58335194b061f_((_lambda_12ef4a55c56a96ec7ad58335194b061f_ *)&v25);
      __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&v16);
      winrt::handle_type<winrt::impl::hstring_traits>::close(v21);
      winrt::handle_type<winrt::impl::hstring_traits>::close(v22);
      winrt::handle_type<winrt::impl::hstring_traits>::close(v23);
      _lambda_12ef4a55c56a96ec7ad58335194b061f_::~_lambda_12ef4a55c56a96ec7ad58335194b061f_((_lambda_12ef4a55c56a96ec7ad58335194b061f_ *)v19);
      _lambda_12ef4a55c56a96ec7ad58335194b061f_::~_lambda_12ef4a55c56a96ec7ad58335194b061f_((_lambda_12ef4a55c56a96ec7ad58335194b061f_ *)v24);
    }
    _lambda_12ef4a55c56a96ec7ad58335194b061f_::~_lambda_12ef4a55c56a96ec7ad58335194b061f_((_lambda_12ef4a55c56a96ec7ad58335194b061f_ *)&v20);
  }
  catch ( ... )
  {
    wil::details::in1diag3::Log_CaughtException(
      retaddr,
      (void *)0x37,
      (unsigned int)"shellcommon\\internal\\undockeddevkit\\inc\\udk\\app_extension_helpers.h",
      v13);
    return v26;
  }
  return v1;
}

```

## disassembly

```asm
0x180109718  mov     r11, rsp
0x18010971b  push    rbx
0x18010971c  sub     rsp, 0F0h
0x180109723  mov     rax, cs:__security_cookie
0x18010972a  xor     rax, rsp
0x18010972d  mov     [rsp+0F8h+var_18], rax
0x180109735  mov     rbx, rcx
0x180109738  mov     [r11-78h], rcx
0x18010973c  mov     [rsp+0F8h+var_B8], 0
0x180109744  mov     qword ptr [rcx], 0
0x18010974b  mov     [rsp+0F8h+var_B8], 1
0x180109753  lea     rdx, aComMicrosoftWi; "com.microsoft.windows.extension.windows"...
0x18010975a  lea     rcx, [r11-70h]; this
0x18010975e  call    ??0hstring@param@winrt@@QEAA@QEBG@Z; winrt::param::hstring::hstring(ushort const * const)
0x180109763  lea     rax, [rsp+0F8h+var_70]
0x18010976b  mov     [rsp+0F8h+var_C8], rax
0x180109770  lea     rax, qword_18017B108
0x180109777  mov     [rsp+0F8h+var_80], rax
0x18010977c  lock inc cs:qword_18017B108
0x180109784  cmp     cs:??$factory_cache_entry_v@UAppExtension@AppExtensions@ApplicationModel@WindowsUdk@winrt@@UIAppExtensionStatics@2345@@impl@winrt@@3U?$factory_cache_entry@UAppExtension@AppExtensions@ApplicationModel@WindowsUdk@winrt@@UIAppExtensionStatics@2345@@12@A, 0; factory_cache_entry<winrt::WindowsUdk::ApplicationModel::AppExtensions::AppExtension,winrt::WindowsUdk::ApplicationModel::AppExtensions::IAppExtensionStatics>::winrt::factory_cache_entry<winrt::WindowsUdk::ApplicationModel::AppExtensions::AppExtension,winrt::WindowsUdk::ApplicationModel::AppExtensions::IAppExtensionStatics> winrt::impl::factory_cache_entry_v<winrt::WindowsUdk::ApplicationModel::AppExtensions::AppExtension,winrt::WindowsUdk::ApplicationModel::AppExtensions::IAppExtensionStatics>
0x18010978c  jz      short loc_1801097AF
0x18010978e  lea     r8, ??$factory_cache_entry_v@UAppExtension@AppExtensions@ApplicationModel@WindowsUdk@winrt@@UIAppExtensionStatics@2345@@impl@winrt@@3U?$factory_cache_entry@UAppExtension@AppExtensions@ApplicationModel@WindowsUdk@winrt@@UIAppExtensionStatics@2345@@12@A; factory_cache_entry<winrt::WindowsUdk::ApplicationModel::AppExtensions::AppExtension,winrt::WindowsUdk::ApplicationModel::AppExtensions::IAppExtensionStatics>::winrt::factory_cache_entry<winrt::WindowsUdk::ApplicationModel::AppExtensions::AppExtension,winrt::WindowsUdk::ApplicationModel::AppExtensions::IAppExtensionStatics> winrt::impl::factory_cache_entry_v<winrt::WindowsUdk::ApplicationModel::AppExtensions::AppExtension,winrt::WindowsUdk::ApplicationModel::AppExtensions::IAppExtensionStatics>
0x180109795  lea     rdx, [rsp+0F8h+var_A8]
0x18010979a  lea     rcx, [rsp+0F8h+var_C8]
0x18010979f  call    ??R_lambda_e84bcefeb7ed3703767eef0b25e91c21_@@QEBA@AEBUIAppExtensionStatics@AppExtensions@ApplicationModel@WindowsUdk@winrt@@@Z; _lambda_e84bcefeb7ed3703767eef0b25e91c21_::operator()(winrt::WindowsUdk::ApplicationModel::AppExtensions::IAppExtensionStatics const &)
0x1801097a4  nop
0x1801097a5  lock dec cs:qword_18017B108
0x1801097ad  jmp     short loc_1801097C6
0x1801097af  lock dec cs:qword_18017B108
0x1801097b7  lea     r8, [rsp+0F8h+var_C8]
0x1801097bc  lea     rdx, [rsp+0F8h+var_A8]
0x1801097c1  call    ??$call@AEAV_lambda_e84bcefeb7ed3703767eef0b25e91c21_@@@?$factory_cache_entry@UAppExtension@AppExtensions@ApplicationModel@WindowsUdk@winrt@@UIAppExtensionStatics@2345@@impl@winrt@@QEAA?A_PAEAV_lambda_e84bcefeb7ed3703767eef0b25e91c21_@@@Z
0x1801097c6  mov     [rsp+0F8h+var_B8], 7
0x1801097ce  cmp     [rsp+0F8h+var_A8], 0
0x1801097d4  jz      loc_180109A1F
0x1801097da  lea     rdx, [rsp+0F8h+var_88]
0x1801097df  lea     rcx, [rsp+0F8h+var_A8]
0x1801097e4  call    ?SuiteName@?$consume_WindowsUdk_UI_StartScreen_ITile@UITile@StartScreen@UI@WindowsUdk@winrt@@@impl@winrt@@QEBA@XZ; winrt::impl::consume_WindowsUdk_UI_StartScreen_ITile<winrt::WindowsUdk::UI::StartScreen::ITile>::SuiteName(void)
0x1801097e9  nop
0x1801097ea  lea     rdx, aStartscreenman_0; "StartScreenManagerWindowService"
0x1801097f1  lea     rcx, [rsp+0F8h+var_70]; this
0x1801097f9  call    ??0hstring@param@winrt@@QEAA@QEBG@Z; winrt::param::hstring::hstring(ushort const * const)
0x1801097fe  lea     r8, [rsp+0F8h+var_70]
0x180109806  lea     rdx, [rsp+0F8h+var_C8]
0x18010980b  lea     rcx, [rsp+0F8h+var_88]
0x180109810  call    ?Lookup@?$consume_Windows_Foundation_Collections_IMap@UIPropertySet@Collections@Foundation@Windows@winrt@@Uhstring@5@UIInspectable@345@@impl@winrt@@QEBA@AEBUhstring@param@3@@Z; winrt::impl::consume_Windows_Foundation_Collections_IMap<winrt::Windows::Foundation::Collections::IPropertySet,winrt::hstring,winrt::Windows::Foundation::IInspectable>::Lookup(winrt::param::hstring const &)
0x180109815  nop
0x180109816  lea     rdx, [rsp+0F8h+var_B0]
0x18010981b  mov     rcx, rax
0x18010981e  call    ??$as@UIPropertySet@Collections@Foundation@Windows@winrt@@@IUnknown@Foundation@Windows@winrt@@QEBA?A_PXZ
0x180109823  nop
0x180109824  cmp     [rsp+0F8h+var_C8], 0
0x18010982a  jz      short loc_180109836
0x18010982c  lea     rcx, [rsp+0F8h+var_C8]
0x180109831  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x180109836  lea     rdx, aServiceclassid; "@ServiceClassId"
0x18010983d  lea     rcx, [rsp+0F8h+var_38]; this
0x180109845  call    ??0hstring@param@winrt@@QEAA@QEBG@Z; winrt::param::hstring::hstring(ushort const * const)
0x18010984a  lea     r8, [rsp+0F8h+var_38]
0x180109852  lea     rdx, [rsp+0F8h+var_C0]
0x180109857  lea     rcx, [rsp+0F8h+var_B0]
0x18010985c  call    ?Lookup@?$consume_Windows_Foundation_Collections_IMap@UIPropertySet@Collections@Foundation@Windows@winrt@@Uhstring@5@UIInspectable@345@@impl@winrt@@QEBA@AEBUhstring@param@3@@Z; winrt::impl::consume_Windows_Foundation_Collections_IMap<winrt::Windows::Foundation::Collections::IPropertySet,winrt::hstring,winrt::Windows::Foundation::IInspectable>::Lookup(winrt::param::hstring const &)
0x180109861  nop
0x180109862  lea     rdx, [rsp+0F8h+var_90]
0x180109867  mov     rcx, rax
0x18010986a  call    ??$as@Uhstring@winrt@@@IUnknown@Foundation@Windows@winrt@@QEBA?A_PXZ
0x18010986f  nop
0x180109870  cmp     [rsp+0F8h+var_C0], 0
0x180109876  jz      short loc_180109882
0x180109878  lea     rcx, [rsp+0F8h+var_C0]
0x18010987d  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x180109882  lea     rdx, aWindowname; "@WindowName"
0x180109889  lea     rcx, [rsp+0F8h+var_70]; this
0x180109891  call    ??0hstring@param@winrt@@QEAA@QEBG@Z; winrt::param::hstring::hstring(ushort const * const)
0x180109896  lea     r8, [rsp+0F8h+var_70]
0x18010989e  lea     rdx, [rsp+0F8h+var_C8]
0x1801098a3  lea     rcx, [rsp+0F8h+var_B0]
0x1801098a8  call    ?Lookup@?$consume_Windows_Foundation_Collections_IMap@UIPropertySet@Collections@Foundation@Windows@winrt@@Uhstring@5@UIInspectable@345@@impl@winrt@@QEBA@AEBUhstring@param@3@@Z; winrt::impl::consume_Windows_Foundation_Collections_IMap<winrt::Windows::Foundation::Collections::IPropertySet,winrt::hstring,winrt::Windows::Foundation::IInspectable>::Lookup(winrt::param::hstring const &)
0x1801098ad  nop
0x1801098ae  lea     rdx, [rsp+0F8h+var_98]
0x1801098b3  mov     rcx, rax
0x1801098b6  call    ??$as@Uhstring@winrt@@@IUnknown@Foundation@Windows@winrt@@QEBA?A_PXZ
0x1801098bb  nop
0x1801098bc  cmp     [rsp+0F8h+var_C8], 0
0x1801098c2  jz      short loc_1801098CE
0x1801098c4  lea     rcx, [rsp+0F8h+var_C8]
0x1801098c9  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x1801098ce  lea     rdx, aClassname; "@ClassName"
0x1801098d5  lea     rcx, [rsp+0F8h+var_38]; this
0x1801098dd  call    ??0hstring@param@winrt@@QEAA@QEBG@Z; winrt::param::hstring::hstring(ushort const * const)
0x1801098e2  lea     r8, [rsp+0F8h+var_38]
0x1801098ea  lea     rdx, [rsp+0F8h+var_C0]
0x1801098ef  lea     rcx, [rsp+0F8h+var_B0]
0x1801098f4  call    ?Lookup@?$consume_Windows_Foundation_Collections_IMap@UIPropertySet@Collections@Foundation@Windows@winrt@@Uhstring@5@UIInspectable@345@@impl@winrt@@QEBA@AEBUhstring@param@3@@Z; winrt::impl::consume_Windows_Foundation_Collections_IMap<winrt::Windows::Foundation::Collections::IPropertySet,winrt::hstring,winrt::Windows::Foundation::IInspectable>::Lookup(winrt::param::hstring const &)
0x1801098f9  nop
0x1801098fa  lea     rdx, [rsp+0F8h+var_A0]
0x1801098ff  mov     rcx, rax
0x180109902  call    ??$as@Uhstring@winrt@@@IUnknown@Foundation@Windows@winrt@@QEBA?A_PXZ
0x180109907  nop
0x180109908  cmp     [rsp+0F8h+var_C0], 0
0x18010990e  jz      short loc_18010991A
0x180109910  lea     rcx, [rsp+0F8h+var_C0]
0x180109915  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x18010991a  mov     [rsp+0F8h+var_C8], 0
0x180109923  lea     r8, aStartscreenman; "__StartScreenManagerWindowRegisteredEve"...
0x18010992a  lea     rcx, [rsp+0F8h+var_C8]
0x18010992f  call    ?create@?$event_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_exception_policy@3@@wil@@QEAAXW4EventOptions@2@PEBGPEAU_SECURITY_ATTRIBUTES@@PEA_N@Z
0x180109934  xor     edx, edx; void *
0x180109936  mov     rcx, [rsp+0F8h+var_C8]; this
0x18010993b  call    ?handle_wait@wil@@YA_NPEAXKH@Z; wil::handle_wait(void *,ulong,int)
0x180109940  lea     rcx, [rsp+0F8h+var_98]; this
0x180109945  call    ?c_str@hstring@winrt@@QEBAPEBGXZ; winrt::hstring::c_str(void)
0x18010994a  mov     rdx, rax
0x18010994d  lea     rcx, [rsp+0F8h+var_A0]; this
0x180109952  call    ?c_str@hstring@winrt@@QEBAPEBGXZ; winrt::hstring::c_str(void)
0x180109957  mov     rcx, rax; lpClassName
0x18010995a  call    cs:__imp_FindWindowW
0x180109960  mov     [rsp+0F8h+var_C0], rax
0x180109965  mov     rcx, [rsp+0F8h]; this
0x18010996d  test    rax, rax
0x180109970  jz      loc_180109A50
0x180109976  lea     rdx, [rsp+0F8h+var_70]
0x18010997e  lea     rcx, [rsp+0F8h+var_90]
0x180109983  call    ??Bhstring@winrt@@QEBA?AV?$basic_string_view@GU?$char_traits@G@std@@@std@@XZ; winrt::hstring::operator std::basic_string_view<ushort>(void)
0x180109988  movups  xmm0, xmmword ptr [rax]
0x18010998b  movdqu  [rsp+0F8h+var_48], xmm0
0x180109994  lea     rdx, [rsp+0F8h+var_48]
0x18010999c  lea     rcx, [rsp+0F8h+var_38]
0x1801099a4  call    ??$parse@V?$basic_string_view@GU?$char_traits@G@std@@@std@@@guid@winrt@@CA?AU01@V?$basic_string_view@GU?$char_traits@G@std@@@std@@@Z; winrt::guid::parse<std::basic_string_view<ushort>>(std::basic_string_view<ushort>)
0x1801099a9  lea     r9, [rsp+0F8h+var_38]
0x1801099b1  lea     r8, [rsp+0F8h+var_C0]
0x1801099b6  mov     rdx, cs:__imp_CoreQueryWindowService
0x1801099bd  lea     rcx, [rsp+0F8h+var_80]
0x1801099c2  call    ??$capture@UIStartScreenManagerExtensionStatics@StartScreen@UI@WindowsUdk@winrt@@A6AJPEAUHWND__@@AEBU_GUID@@1PEAPEAX@ZAEBQEAU6@Uguid@5@@winrt@@YA?AUIStartScreenManagerExtensionStatics@StartScreen@UI@WindowsUdk@0@A6AJPEAUHWND__@@AEBU_GUID@@1PEAPEAX@ZAEBQEAU5@$$QEAUguid@0@@Z; winrt::capture<winrt::WindowsUdk::UI::StartScreen::IStartScreenManagerExtensionStatics,long (&)(HWND__ *,_GUID const &,_GUID const &,void * *),HWND__ * const &,winrt::guid>(long (&)(HWND__ *,_GUID const &,_GUID const &,void * *),HWND__ * const &,winrt::guid &&)
0x1801099c7  mov     rdx, rax
0x1801099ca  mov     rcx, rbx
0x1801099cd  call    ??4IUnknown@Foundation@Windows@winrt@@QEAAAEAU0123@$$QEAU0123@@Z; winrt::Windows::Foundation::IUnknown::operator=(winrt::Windows::Foundation::IUnknown &&)
0x1801099d2  lea     rcx, [rsp+0F8h+var_80]; this
0x1801099d7  call    ??1_lambda_12ef4a55c56a96ec7ad58335194b061f_@@QEAA@XZ; _lambda_12ef4a55c56a96ec7ad58335194b061f_::~_lambda_12ef4a55c56a96ec7ad58335194b061f_(void)
0x1801099dc  nop
0x1801099dd  lea     rcx, [rsp+0F8h+var_C8]
0x1801099e2  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x1801099e7  nop
0x1801099e8  lea     rcx, [rsp+0F8h+var_A0]
0x1801099ed  call    ?close@?$handle_type@Uhstring_traits@impl@winrt@@@winrt@@QEAAXXZ; winrt::handle_type<winrt::impl::hstring_traits>::close(void)
0x1801099f2  nop
0x1801099f3  lea     rcx, [rsp+0F8h+var_98]
0x1801099f8  call    ?close@?$handle_type@Uhstring_traits@impl@winrt@@@winrt@@QEAAXXZ; winrt::handle_type<winrt::impl::hstring_traits>::close(void)
0x1801099fd  nop
0x1801099fe  lea     rcx, [rsp+0F8h+var_90]
0x180109a03  call    ?close@?$handle_type@Uhstring_traits@impl@winrt@@@winrt@@QEAAXXZ; winrt::handle_type<winrt::impl::hstring_traits>::close(void)
0x180109a08  nop
0x180109a09  lea     rcx, [rsp+0F8h+var_B0]; this
0x180109a0e  call    ??1_lambda_12ef4a55c56a96ec7ad58335194b061f_@@QEAA@XZ; _lambda_12ef4a55c56a96ec7ad58335194b061f_::~_lambda_12ef4a55c56a96ec7ad58335194b061f_(void)
0x180109a13  nop
0x180109a14  lea     rcx, [rsp+0F8h+var_88]; this
0x180109a19  call    ??1_lambda_12ef4a55c56a96ec7ad58335194b061f_@@QEAA@XZ; _lambda_12ef4a55c56a96ec7ad58335194b061f_::~_lambda_12ef4a55c56a96ec7ad58335194b061f_(void)
0x180109a1e  nop
0x180109a1f  lea     rcx, [rsp+0F8h+var_A8]; this
0x180109a24  call    ??1_lambda_12ef4a55c56a96ec7ad58335194b061f_@@QEAA@XZ; _lambda_12ef4a55c56a96ec7ad58335194b061f_::~_lambda_12ef4a55c56a96ec7ad58335194b061f_(void)
0x180109a29  nop
0x180109a2a  jmp     short loc_180109A34
0x180109a2c  mov     rbx, [rsp+0F8h+var_78]
0x180109a34  mov     rax, rbx
0x180109a37  mov     rcx, [rsp+0F8h+var_18]
0x180109a3f  xor     rcx, rsp; StackCookie
0x180109a42  call    __security_check_cookie
0x180109a47  add     rsp, 0F0h
0x180109a4e  pop     rbx
0x180109a4f  retn
0x180109a50  mov     r9d, 80070490h; char *
0x180109a56  lea     r8, aShellcommonInt; "shellcommon\\internal\\undockeddevkit\\"...
0x180109a5d  lea     edx, [rax+2Eh]; void *
0x180109a60  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
```
