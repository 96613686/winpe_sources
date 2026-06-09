# _anonymous_namespace_::StopClockAppFocusSession

- ea: `0x180023898`
- end: `0x180023d60`
- name: `_anonymous_namespace_::StopClockAppFocusSession`
- size: `1224`
- prototype: ``
- caller_count: `1`
- callee_count: `31`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x1800211c4`

## callees

- `0x180006f04`
- `0x1800072d8`
- `0x18000cf94`
- `0x18000dfc0`
- `0x18001a860`
- `0x18001a91c`
- `0x18001d7f8`
- `0x18001dc5c`
- `0x18001dd78`
- `0x18001f420`
- `0x18001f844`
- `0x18001f90c`
- `0x18001fb34`
- `0x1800203ac`
- `0x18002086c`
- `0x18002094c`
- `0x180021080`
- `0x180021b74`
- `0x180021bc8`
- `0x180021c48`
- `0x180021cc8`
- `0x180021dc4`
- `0x180022538`
- `0x180022608`
- `0x180022860`
- `0x1800228c0`
- `0x180023724`
- `0x180023788`
- `0x1800237dc`
- `0x180023898`
- `0x18002435c`

## string_xrefs

- `0x180023908`: `ms-alarmsService`
- `0x1800239aa`: `onecoreuap\windows\accessibletech\experience\src\winrt\lib\windows.internal.shell.focussessionthememanager.cpp`
- `0x180023b21`: `onecoreuap\windows\accessibletech\experience\src\winrt\lib\windows.internal.shell.focussessionthememanager.cpp`
- `0x180023b6d`: `onecoreuap\windows\accessibletech\experience\src\winrt\lib\windows.internal.shell.focussessionthememanager.cpp`
- `0x180023bd1`: `onecoreuap\windows\accessibletech\experience\src\winrt\lib\windows.internal.shell.focussessionthememanager.cpp`
- `0x180023d00`: `onecoreuap\windows\accessibletech\experience\src\winrt\lib\windows.internal.shell.focussessionthememanager.cpp`
- `0x180023a65`: `Command`
- `0x180023ba1`: `FocusSessionJson`
- `0x180023c02`: `FocusSessionJson`

## pseudocode

```c
// Hidden C++ exception states: #wind=18
__int64 __fastcall anonymous_namespace_::StopClockAppFocusSession(__int64 a1)
{
  __int64 v1; // rbx
  unsigned int v2; // eax
  enum AsyncStatus v3; // edx
  int Results; // ebx
  __int64 **v5; // rax
  __int64 *v6; // rcx
  __int64 v7; // rbx
  unsigned int v8; // eax
  enum AsyncStatus v9; // edx
  __int64 Default; // rax
  __int64 v11; // rbx
  __int64 v12; // rbx
  __int64 v13; // rax
  __int64 v14; // rcx
  __int64 result; // rax
  const char *v16; // r9
  int v17[2]; // [rsp+20h] [rbp-98h] BYREF
  __int64 v18; // [rsp+28h] [rbp-90h] BYREF
  __int64 v19; // [rsp+30h] [rbp-88h] BYREF
  _BYTE v20[8]; // [rsp+38h] [rbp-80h] BYREF
  int v21[2]; // [rsp+40h] [rbp-78h] BYREF
  _BYTE v22[32]; // [rsp+60h] [rbp-58h] BYREF
  __int64 *v23; // [rsp+80h] [rbp-38h]
  _BYTE v24[48]; // [rsp+88h] [rbp-30h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+B8h] [rbp+0h]
  char v26; // [rsp+C0h] [rbp+8h] BYREF
  char v27; // [rsp+C8h] [rbp+10h] BYREF
  char v28; // [rsp+D0h] [rbp+18h] BYREF
  __int64 *v29; // [rsp+D8h] [rbp+20h] BYREF

  try
  {
    v29 = &qword_180046BF8;
    _InterlockedIncrement64(&qword_180046BF8);
    if ( winrt::impl::factory_cache_entry_v<winrt::Windows::ApplicationModel::AppService::AppServiceConnection,winrt::Windows::Foundation::IActivationFactory> )
    {
      winrt::Windows::Foundation::IActivationFactory::ActivateInstance<winrt::Windows::ApplicationModel::AppService::AppServiceConnection>(
        &winrt::impl::factory_cache_entry_v<winrt::Windows::ApplicationModel::AppService::AppServiceConnection,winrt::Windows::Foundation::IActivationFactory>,
        &v26);
      _InterlockedDecrement64(&qword_180046BF8);
    }
    else
    {
      _InterlockedDecrement64(&qword_180046BF8);
      v29 = (__int64 *)_lambda_738c25de178d0da10aac81a19adbfa44_::_lambda_invoker_cdecl_;
      winrt::impl::factory_cache_entry<winrt::Windows::ApplicationModel::AppService::AppServiceConnection,winrt::Windows::Foundation::IActivationFactory>::call<winrt::Windows::ApplicationModel::AppService::AppServiceConnection (*)(winrt::Windows::Foundation::IActivationFactory const &)>(
        a1,
        &v26,
        &v29);
    }
    winrt::param::hstring::hstring((winrt::param::hstring *)v21, L"ms-alarmsService");
    winrt::impl::consume_Windows_ApplicationModel_AppService_IAppServiceConnection<winrt::Windows::ApplicationModel::AppService::IAppServiceConnection>::AppServiceName(
      &v26,
      v21);
    winrt::param::hstring::hstring((winrt::param::hstring *)v21, L"Microsoft.WindowsAlarms_8wekyb3d8bbwe");
    winrt::impl::consume_Windows_ApplicationModel_AppService_IAppServiceConnection<winrt::Windows::ApplicationModel::AppService::IAppServiceConnection>::PackageFamilyName(
      &v26,
      v21);
    v1 = winrt::impl::consume_Windows_ApplicationModel_AppService_IAppServiceConnection<winrt::Windows::ApplicationModel::AppService::IAppServiceConnection>::OpenAsync(
           &v26,
           &v29);
    v2 = winrt::impl::consume_Windows_Foundation_IAsyncInfo<winrt::Windows::Foundation::IAsyncOperation<winrt::Windows::ApplicationModel::AppService::AppServiceResponse>>::Status(v1);
    if ( !v2 )
      v2 = winrt::impl::wait_for_completed<winrt::Windows::Foundation::IAsyncOperation<enum winrt::Windows::ApplicationModel::AppService::AppServiceConnectionStatus>>(v1);
    winrt::impl::check_status_canceled((winrt::impl *)v2, v3);
    Results = winrt::impl::consume_Windows_Foundation_IAsyncOperation<winrt::Windows::Foundation::IAsyncOperation<enum winrt::Windows::ApplicationModel::AppService::AppServiceConnectionStatus>,enum winrt::Windows::ApplicationModel::AppService::AppServiceConnectionStatus>::GetResults(v1);
    winrt::com_ptr<winrt::impl::IWeakReferenceSource>::~com_ptr<winrt::impl::IWeakReferenceSource>(&v29);
    if ( Results )
      wil::details::in1diag3::_Throw_Hr(
        retaddr,
        (void *)0x4B,
        (unsigned int)"onecoreuap\\windows\\accessibletech\\experience\\src\\winrt\\lib\\windows.internal.shell.focussess"
                      "ionthememanager.cpp",
        (const char *)0x80004005LL,
        v17[0]);
    v29 = &qword_180046C78;
    _InterlockedIncrement64(&qword_180046C78);
    if ( winrt::impl::factory_cache_entry_v<winrt::Windows::Foundation::Collections::ValueSet,winrt::Windows::Foundation::IActivationFactory> )
    {
      winrt::Windows::Foundation::IActivationFactory::ActivateInstance<winrt::Windows::Foundation::Collections::ValueSet>(
        &winrt::impl::factory_cache_entry_v<winrt::Windows::Foundation::Collections::ValueSet,winrt::Windows::Foundation::IActivationFactory>,
        &v28);
      _InterlockedDecrement64(&qword_180046C78);
    }
    else
    {
      _InterlockedDecrement64(&qword_180046C78);
      v29 = (__int64 *)_lambda_f635e0c3324166f0c8ad227de6175e83_::_lambda_invoker_cdecl_;
      winrt::impl::factory_cache_entry<winrt::Windows::Foundation::Collections::ValueSet,winrt::Windows::Foundation::IActivationFactory>::call<winrt::Windows::Foundation::Collections::ValueSet (*)(winrt::Windows::Foundation::IActivationFactory const &)>(
        retaddr,
        &v28,
        &v29);
    }
    winrt::param::hstring::hstring((winrt::param::hstring *)v21, L"StopFocusSession");
    v5 = (__int64 **)winrt::Windows::Foundation::IReference<winrt::hstring>::IReference<winrt::hstring>(v17, v21);
    v6 = *v5;
    *v5 = 0;
    v29 = v6;
    winrt::com_ptr<winrt::impl::IWeakReferenceSource>::~com_ptr<winrt::impl::IWeakReferenceSource>(v17);
    winrt::param::hstring::hstring((winrt::param::hstring *)v22, L"Command");
    winrt::impl::consume_Windows_Foundation_Collections_IMap<winrt::Windows::Foundation::Collections::IPropertySet,winrt::hstring,winrt::Windows::Foundation::IInspectable>::Insert(
      &v28,
      v22,
      &v29);
    if ( v29 )
      winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v29);
    v7 = winrt::impl::consume_Windows_ApplicationModel_AppService_IAppServiceConnection<winrt::Windows::ApplicationModel::AppService::IAppServiceConnection>::SendMessageAsync(
           &v26,
           &v29,
           &v28);
    v8 = winrt::impl::consume_Windows_Foundation_IAsyncInfo<winrt::Windows::Foundation::IAsyncOperation<winrt::Windows::ApplicationModel::AppService::AppServiceResponse>>::Status(v7);
    if ( !v8 )
      v8 = winrt::impl::wait_for_completed<winrt::Windows::Foundation::IAsyncOperation<winrt::Windows::ApplicationModel::AppService::AppServiceResponse>>(v7);
    winrt::impl::check_status_canceled((winrt::impl *)v8, v9);
    winrt::impl::consume_Windows_Foundation_IAsyncOperation<winrt::Windows::Foundation::IAsyncOperation<winrt::Windows::ApplicationModel::AppService::AppServiceResponse>,winrt::Windows::ApplicationModel::AppService::AppServiceResponse>::GetResults(
      v7,
      &v27);
    winrt::com_ptr<winrt::impl::IWeakReferenceSource>::~com_ptr<winrt::impl::IWeakReferenceSource>(&v29);
    if ( (unsigned int)winrt::impl::consume_Windows_ApplicationModel_AppService_IAppServiceResponse<winrt::Windows::ApplicationModel::AppService::IAppServiceResponse>::Status(&v27) )
      wil::details::in1diag3::_Throw_Hr(
        retaddr,
        (void *)0x51,
        (unsigned int)"onecoreuap\\windows\\accessibletech\\experience\\src\\winrt\\lib\\windows.internal.shell.focussess"
                      "ionthememanager.cpp",
        (const char *)0x80004005LL,
        v17[0]);
    Default = winrt::impl::consume_Windows_Internal_UI_Notifications_IQuietHoursSettingsInteropStatics<winrt::Windows::Internal::UI::Notifications::IQuietHoursSettingsInteropStatics>::GetDefault(
                &v27,
                &v18);
    *(_QWORD *)v17 = 0;
    if ( (unsigned __int8)winrt::Windows::Foundation::operator==(Default, v17) )
      wil::details::in1diag3::_Throw_Hr(
        retaddr,
        (void *)0x52,
        (unsigned int)"onecoreuap\\windows\\accessibletech\\experience\\src\\winrt\\lib\\windows.internal.shell.focussess"
                      "ionthememanager.cpp",
        (const char *)0x80004005LL,
        v17[0]);
    winrt::com_ptr<winrt::impl::IWeakReferenceSource>::~com_ptr<winrt::impl::IWeakReferenceSource>(&v18);
    v11 = winrt::impl::consume_Windows_Internal_UI_Notifications_IQuietHoursSettingsInteropStatics<winrt::Windows::Internal::UI::Notifications::IQuietHoursSettingsInteropStatics>::GetDefault(
            &v27,
            v17);
    winrt::param::hstring::hstring((winrt::param::hstring *)v22, L"FocusSessionJson");
    if ( !(unsigned __int8)winrt::impl::consume_Windows_Foundation_Collections_IMap<winrt::Windows::Foundation::Collections::IPropertySet,winrt::hstring,winrt::Windows::Foundation::IInspectable>::HasKey(
                             v11,
                             v22) )
      wil::details::in1diag3::_Throw_Hr(
        retaddr,
        (void *)0x53,
        (unsigned int)"onecoreuap\\windows\\accessibletech\\experience\\src\\winrt\\lib\\windows.internal.shell.focussess"
                      "ionthememanager.cpp",
        (const char *)0x80004005LL,
        v17[0]);
    winrt::com_ptr<winrt::impl::IWeakReferenceSource>::~com_ptr<winrt::impl::IWeakReferenceSource>(v17);
    v12 = winrt::impl::consume_Windows_Internal_UI_Notifications_IQuietHoursSettingsInteropStatics<winrt::Windows::Internal::UI::Notifications::IQuietHoursSettingsInteropStatics>::GetDefault(
            &v27,
            v20);
    winrt::param::hstring::hstring((winrt::param::hstring *)v22, L"FocusSessionJson");
    v13 = winrt::impl::consume_Windows_Foundation_Collections_IMap<winrt::Windows::Foundation::Collections::IPropertySet,winrt::hstring,winrt::Windows::Foundation::IInspectable>::Lookup(
            v12,
            &v18,
            v22);
    winrt::impl::unbox_value_type<winrt::hstring,winrt::Windows::Foundation::IInspectable const &>(&v19, v13);
    if ( v18 )
      winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v18);
    winrt::com_ptr<winrt::impl::IWeakReferenceSource>::~com_ptr<winrt::impl::IWeakReferenceSource>(v20);
    *(_QWORD *)v21 = v19;
    *(_QWORD *)v17 = v21;
    v23 = &qword_180046C18;
    _InterlockedIncrement64(&qword_180046C18);
    if ( winrt::impl::factory_cache_entry_v<winrt::Windows::Data::Json::JsonObject,winrt::Windows::Data::Json::IJsonObjectStatics> )
    {
      _lambda_6572cb39eb053ecf8aa601a8cecd7f9b_::operator()(
        v17,
        &v29,
        &winrt::impl::factory_cache_entry_v<winrt::Windows::Data::Json::JsonObject,winrt::Windows::Data::Json::IJsonObjectStatics>);
      _InterlockedDecrement64(&qword_180046C18);
    }
    else
    {
      _InterlockedDecrement64(&qword_180046C18);
      winrt::impl::factory_cache_entry<winrt::Windows::Data::Json::JsonObject,winrt::Windows::Data::Json::IJsonObjectStatics>::call<_lambda_6572cb39eb053ecf8aa601a8cecd7f9b_ &>(
        v14,
        &v29,
        v17);
    }
    winrt::param::hstring::hstring((winrt::param::hstring *)v24, L"isSuccess");
    if ( !(unsigned __int8)winrt::impl::consume_Windows_Data_Json_IJsonObject<winrt::Windows::Data::Json::IJsonObject>::GetNamedBoolean(
                             &v29,
                             v24) )
      wil::details::in1diag3::_Throw_Hr(
        retaddr,
        (void *)0x56,
        (unsigned int)"onecoreuap\\windows\\accessibletech\\experience\\src\\winrt\\lib\\windows.internal.shell.focussess"
                      "ionthememanager.cpp",
        (const char *)0x80004005LL,
        v17[0]);
    winrt::com_ptr<winrt::impl::IWeakReferenceSource>::~com_ptr<winrt::impl::IWeakReferenceSource>(&v29);
    winrt::handle_type<winrt::impl::hstring_traits>::close(&v19);
    winrt::com_ptr<winrt::impl::IWeakReferenceSource>::~com_ptr<winrt::impl::IWeakReferenceSource>(&v27);
    winrt::com_ptr<winrt::impl::IWeakReferenceSource>::~com_ptr<winrt::impl::IWeakReferenceSource>(&v28);
    result = winrt::com_ptr<winrt::impl::IWeakReferenceSource>::~com_ptr<winrt::impl::IWeakReferenceSource>(&v26);
  }
  catch ( ... )
  {
    return wil::details::in1diag3::Log_CaughtException(
             retaddr,
             (void *)0x58,
             (unsigned int)"onecoreuap\\windows\\accessibletech\\experience\\src\\winrt\\lib\\windows.internal.shell.focu"
                           "ssessionthememanager.cpp",
             v16);
  }
  return result;
}

```

## disassembly

```asm
0x180023898  mov     r11, rsp
0x18002389b  push    rbx
0x18002389c  sub     rsp, 0B0h
0x1800238a3  lea     rax, qword_180046BF8
0x1800238aa  mov     [r11+20h], rax
0x1800238ae  lock inc cs:qword_180046BF8
0x1800238b6  cmp     cs:??$factory_cache_entry_v@UAppServiceConnection@AppService@ApplicationModel@Windows@winrt@@UIActivationFactory@Foundation@45@@impl@winrt@@3U?$factory_cache_entry@UAppServiceConnection@AppService@ApplicationModel@Windows@winrt@@UIActivationFactory@Foundation@45@@12@A, 0; factory_cache_entry<winrt::Windows::ApplicationModel::AppService::AppServiceConnection,winrt::Windows::Foundation::IActivationFactory>::winrt::factory_cache_entry<winrt::Windows::ApplicationModel::AppService::AppServiceConnection,winrt::Windows::Foundation::IActivationFactory> winrt::impl::factory_cache_entry_v<winrt::Windows::ApplicationModel::AppService::AppServiceConnection,winrt::Windows::Foundation::IActivationFactory>
0x1800238be  jz      short loc_1800238DB
0x1800238c0  lea     rdx, [r11+8]
0x1800238c4  lea     rcx, ??$factory_cache_entry_v@UAppServiceConnection@AppService@ApplicationModel@Windows@winrt@@UIActivationFactory@Foundation@45@@impl@winrt@@3U?$factory_cache_entry@UAppServiceConnection@AppService@ApplicationModel@Windows@winrt@@UIActivationFactory@Foundation@45@@12@A; factory_cache_entry<winrt::Windows::ApplicationModel::AppService::AppServiceConnection,winrt::Windows::Foundation::IActivationFactory>::winrt::factory_cache_entry<winrt::Windows::ApplicationModel::AppService::AppServiceConnection,winrt::Windows::Foundation::IActivationFactory> winrt::impl::factory_cache_entry_v<winrt::Windows::ApplicationModel::AppService::AppServiceConnection,winrt::Windows::Foundation::IActivationFactory>
0x1800238cb  call    ??$ActivateInstance@UAppServiceConnection@AppService@ApplicationModel@Windows@winrt@@@IActivationFactory@Foundation@Windows@winrt@@QEBA?AUAppServiceConnection@AppService@ApplicationModel@23@XZ; winrt::Windows::Foundation::IActivationFactory::ActivateInstance<winrt::Windows::ApplicationModel::AppService::AppServiceConnection>(void)
0x1800238d0  nop
0x1800238d1  lock dec cs:qword_180046BF8
0x1800238d9  jmp     short loc_180023908
0x1800238db  lock dec cs:qword_180046BF8
0x1800238e3  lea     rax, ?_lambda_invoker_cdecl_@_lambda_738c25de178d0da10aac81a19adbfa44_@@CA@AEBUIActivationFactory@Foundation@Windows@winrt@@@Z; _lambda_738c25de178d0da10aac81a19adbfa44_::_lambda_invoker_cdecl_(winrt::Windows::Foundation::IActivationFactory const &)
0x1800238ea  mov     [rsp+0B8h+arg_18], rax
0x1800238f2  lea     r8, [rsp+0B8h+arg_18]
0x1800238fa  lea     rdx, [rsp+0B8h+arg_0]
0x180023902  call    ??$call@P6A?AUAppServiceConnection@AppService@ApplicationModel@Windows@winrt@@AEBUIActivationFactory@Foundation@45@@Z@?$factory_cache_entry@UAppServiceConnection@AppService@ApplicationModel@Windows@winrt@@UIActivationFactory@Foundation@45@@impl@winrt@@QEAA?A_P$$QEAP6A?AUAppServiceConnection@AppService@ApplicationModel@Windows@2@AEBUIActivationFactory@Foundation@62@@Z@Z
0x180023907  nop
0x180023908  lea     rdx, aMsAlarmsservic; "ms-alarmsService"
0x18002390f  lea     rcx, [rsp+0B8h+var_78]; this
0x180023914  call    ??0hstring@param@winrt@@QEAA@QEBG@Z; winrt::param::hstring::hstring(ushort const * const)
0x180023919  lea     rdx, [rsp+0B8h+var_78]
0x18002391e  lea     rcx, [rsp+0B8h+arg_0]
0x180023926  call    ?AppServiceName@?$consume_Windows_ApplicationModel_AppService_IAppServiceConnection@UIAppServiceConnection@AppService@ApplicationModel@Windows@winrt@@@impl@winrt@@QEBA@AEBUhstring@param@3@@Z; winrt::impl::consume_Windows_ApplicationModel_AppService_IAppServiceConnection<winrt::Windows::ApplicationModel::AppService::IAppServiceConnection>::AppServiceName(winrt::param::hstring const &)
0x18002392b  lea     rdx, aMicrosoftWindo; "Microsoft.WindowsAlarms_8wekyb3d8bbwe"
0x180023932  lea     rcx, [rsp+0B8h+var_78]; this
0x180023937  call    ??0hstring@param@winrt@@QEAA@QEBG@Z; winrt::param::hstring::hstring(ushort const * const)
0x18002393c  lea     rdx, [rsp+0B8h+var_78]
0x180023941  lea     rcx, [rsp+0B8h+arg_0]
0x180023949  call    ?PackageFamilyName@?$consume_Windows_ApplicationModel_AppService_IAppServiceConnection@UIAppServiceConnection@AppService@ApplicationModel@Windows@winrt@@@impl@winrt@@QEBA@AEBUhstring@param@3@@Z; winrt::impl::consume_Windows_ApplicationModel_AppService_IAppServiceConnection<winrt::Windows::ApplicationModel::AppService::IAppServiceConnection>::PackageFamilyName(winrt::param::hstring const &)
0x18002394e  lea     rdx, [rsp+0B8h+arg_18]
0x180023956  lea     rcx, [rsp+0B8h+arg_0]
0x18002395e  call    ?OpenAsync@?$consume_Windows_ApplicationModel_AppService_IAppServiceConnection@UIAppServiceConnection@AppService@ApplicationModel@Windows@winrt@@@impl@winrt@@QEBA@XZ; winrt::impl::consume_Windows_ApplicationModel_AppService_IAppServiceConnection<winrt::Windows::ApplicationModel::AppService::IAppServiceConnection>::OpenAsync(void)
0x180023963  mov     rbx, rax
0x180023966  mov     rcx, rax
0x180023969  call    ?Status@?$consume_Windows_Foundation_IAsyncInfo@U?$IAsyncOperation@UAppServiceResponse@AppService@ApplicationModel@Windows@winrt@@@Foundation@Windows@winrt@@@impl@winrt@@QEBA@XZ; winrt::impl::consume_Windows_Foundation_IAsyncInfo<winrt::Windows::Foundation::IAsyncOperation<winrt::Windows::ApplicationModel::AppService::AppServiceResponse>>::Status(void)
0x18002396e  test    eax, eax
0x180023970  jnz     short loc_18002397A
0x180023972  mov     rcx, rbx
0x180023975  call    ??$wait_for_completed@U?$IAsyncOperation@W4AppServiceConnectionStatus@AppService@ApplicationModel@Windows@winrt@@@Foundation@Windows@winrt@@@impl@winrt@@YA?A_PAEBU?$IAsyncOperation@W4AppServiceConnectionStatus@AppService@ApplicationModel@Windows@winrt@@@Foundation@Windows@1@I@Z
0x18002397a  mov     ecx, eax; this
0x18002397c  call    ?check_status_canceled@impl@winrt@@YAXW4AsyncStatus@Foundation@Windows@2@@Z; winrt::impl::check_status_canceled(winrt::Windows::Foundation::AsyncStatus)
0x180023981  mov     rcx, rbx
0x180023984  call    ?GetResults@?$consume_Windows_Foundation_IAsyncOperation@U?$IAsyncOperation@W4AppServiceConnectionStatus@AppService@ApplicationModel@Windows@winrt@@@Foundation@Windows@winrt@@W4AppServiceConnectionStatus@AppService@ApplicationModel@34@@impl@winrt@@QEBA@XZ; winrt::impl::consume_Windows_Foundation_IAsyncOperation<winrt::Windows::Foundation::IAsyncOperation<winrt::Windows::ApplicationModel::AppService::AppServiceConnectionStatus>,winrt::Windows::ApplicationModel::AppService::AppServiceConnectionStatus>::GetResults(void)
0x180023989  mov     ebx, eax
0x18002398b  lea     rcx, [rsp+0B8h+arg_18]
0x180023993  call    ??1?$com_ptr@UIWeakReferenceSource@impl@winrt@@@winrt@@QEAA@XZ; winrt::com_ptr<winrt::impl::IWeakReferenceSource>::~com_ptr<winrt::impl::IWeakReferenceSource>(void)
0x180023998  mov     rcx, [rsp+0B8h]; this
0x1800239a0  test    ebx, ebx
0x1800239a2  jz      short loc_1800239BB
0x1800239a4  mov     r9d, 80004005h; char *
0x1800239aa  lea     r8, aOnecoreuapWind_4; "onecoreuap\\windows\\accessibletech\\ex"...
0x1800239b1  mov     edx, 4Bh ; 'K'; void *
0x1800239b6  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x1800239bb  lea     rax, qword_180046C78
0x1800239c2  mov     [rsp+0B8h+arg_18], rax
0x1800239ca  lock inc cs:qword_180046C78
0x1800239d2  cmp     cs:??$factory_cache_entry_v@UValueSet@Collections@Foundation@Windows@winrt@@UIActivationFactory@345@@impl@winrt@@3U?$factory_cache_entry@UValueSet@Collections@Foundation@Windows@winrt@@UIActivationFactory@345@@12@A, 0; factory_cache_entry<winrt::Windows::Foundation::Collections::ValueSet,winrt::Windows::Foundation::IActivationFactory>::winrt::factory_cache_entry<winrt::Windows::Foundation::Collections::ValueSet,winrt::Windows::Foundation::IActivationFactory> winrt::impl::factory_cache_entry_v<winrt::Windows::Foundation::Collections::ValueSet,winrt::Windows::Foundation::IActivationFactory>
0x1800239da  jz      short loc_1800239FB
0x1800239dc  lea     rdx, [rsp+0B8h+arg_10]
0x1800239e4  lea     rcx, ??$factory_cache_entry_v@UValueSet@Collections@Foundation@Windows@winrt@@UIActivationFactory@345@@impl@winrt@@3U?$factory_cache_entry@UValueSet@Collections@Foundation@Windows@winrt@@UIActivationFactory@345@@12@A; factory_cache_entry<winrt::Windows::Foundation::Collections::ValueSet,winrt::Windows::Foundation::IActivationFactory>::winrt::factory_cache_entry<winrt::Windows::Foundation::Collections::ValueSet,winrt::Windows::Foundation::IActivationFactory> winrt::impl::factory_cache_entry_v<winrt::Windows::Foundation::Collections::ValueSet,winrt::Windows::Foundation::IActivationFactory>
0x1800239eb  call    ??$ActivateInstance@UValueSet@Collections@Foundation@Windows@winrt@@@IActivationFactory@Foundation@Windows@winrt@@QEBA?AUValueSet@Collections@123@XZ; winrt::Windows::Foundation::IActivationFactory::ActivateInstance<winrt::Windows::Foundation::Collections::ValueSet>(void)
0x1800239f0  nop
0x1800239f1  lock dec cs:qword_180046C78
0x1800239f9  jmp     short loc_180023A28
0x1800239fb  lock dec cs:qword_180046C78
0x180023a03  lea     rax, ?_lambda_invoker_cdecl_@_lambda_f635e0c3324166f0c8ad227de6175e83_@@CA@AEBUIActivationFactory@Foundation@Windows@winrt@@@Z; _lambda_f635e0c3324166f0c8ad227de6175e83_::_lambda_invoker_cdecl_(winrt::Windows::Foundation::IActivationFactory const &)
0x180023a0a  mov     [rsp+0B8h+arg_18], rax
0x180023a12  lea     r8, [rsp+0B8h+arg_18]
0x180023a1a  lea     rdx, [rsp+0B8h+arg_10]
0x180023a22  call    ??$call@P6A?AUValueSet@Collections@Foundation@Windows@winrt@@AEBUIActivationFactory@345@@Z@?$factory_cache_entry@UValueSet@Collections@Foundation@Windows@winrt@@UIActivationFactory@345@@impl@winrt@@QEAA?A_P$$QEAP6A?AUValueSet@Collections@Foundation@Windows@2@AEBUIActivationFactory@562@@Z@Z
0x180023a27  nop
0x180023a28  lea     rdx, aStopfocussessi; "StopFocusSession"
0x180023a2f  lea     rcx, [rsp+0B8h+var_78]; this
0x180023a34  call    ??0hstring@param@winrt@@QEAA@QEBG@Z; winrt::param::hstring::hstring(ushort const * const)
0x180023a39  lea     rdx, [rsp+0B8h+var_78]
0x180023a3e  lea     rcx, [rsp+0B8h+var_98]
0x180023a43  call    ??0?$IReference@Uhstring@winrt@@@Foundation@Windows@winrt@@QEAA@AEBUhstring@3@@Z; winrt::Windows::Foundation::IReference<winrt::hstring>::IReference<winrt::hstring>(winrt::hstring const &)
0x180023a48  mov     rcx, [rax]
0x180023a4b  mov     qword ptr [rax], 0
0x180023a52  mov     [rsp+0B8h+arg_18], rcx
0x180023a5a  lea     rcx, [rsp+0B8h+var_98]
0x180023a5f  call    ??1?$com_ptr@UIWeakReferenceSource@impl@winrt@@@winrt@@QEAA@XZ; winrt::com_ptr<winrt::impl::IWeakReferenceSource>::~com_ptr<winrt::impl::IWeakReferenceSource>(void)
0x180023a64  nop
0x180023a65  lea     rdx, aCommand; "Command"
0x180023a6c  lea     rcx, [rsp+0B8h+var_58]; this
0x180023a71  call    ??0hstring@param@winrt@@QEAA@QEBG@Z; winrt::param::hstring::hstring(ushort const * const)
0x180023a76  lea     r8, [rsp+0B8h+arg_18]
0x180023a7e  lea     rdx, [rsp+0B8h+var_58]
0x180023a83  lea     rcx, [rsp+0B8h+arg_10]
0x180023a8b  call    ?Insert@?$consume_Windows_Foundation_Collections_IMap@UIPropertySet@Collections@Foundation@Windows@winrt@@Uhstring@5@UIInspectable@345@@impl@winrt@@QEBA@AEBUhstring@param@3@AEBUIInspectable@Foundation@Windows@3@@Z; winrt::impl::consume_Windows_Foundation_Collections_IMap<winrt::Windows::Foundation::Collections::IPropertySet,winrt::hstring,winrt::Windows::Foundation::IInspectable>::Insert(winrt::param::hstring const &,winrt::Windows::Foundation::IInspectable const &)
0x180023a90  nop
0x180023a91  cmp     [rsp+0B8h+arg_18], 0
0x180023a9a  jz      short loc_180023AA9
0x180023a9c  lea     rcx, [rsp+0B8h+arg_18]
0x180023aa4  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x180023aa9  lea     r8, [rsp+0B8h+arg_10]
0x180023ab1  lea     rdx, [rsp+0B8h+arg_18]
0x180023ab9  lea     rcx, [rsp+0B8h+arg_0]
0x180023ac1  call    ?SendMessageAsync@?$consume_Windows_ApplicationModel_AppService_IAppServiceConnection@UIAppServiceConnection@AppService@ApplicationModel@Windows@winrt@@@impl@winrt@@QEBA@AEBUValueSet@Collections@Foundation@Windows@3@@Z; winrt::impl::consume_Windows_ApplicationModel_AppService_IAppServiceConnection<winrt::Windows::ApplicationModel::AppService::IAppServiceConnection>::SendMessageAsync(winrt::Windows::Foundation::Collections::ValueSet const &)
0x180023ac6  mov     rbx, rax
0x180023ac9  mov     rcx, rax
0x180023acc  call    ?Status@?$consume_Windows_Foundation_IAsyncInfo@U?$IAsyncOperation@UAppServiceResponse@AppService@ApplicationModel@Windows@winrt@@@Foundation@Windows@winrt@@@impl@winrt@@QEBA@XZ; winrt::impl::consume_Windows_Foundation_IAsyncInfo<winrt::Windows::Foundation::IAsyncOperation<winrt::Windows::ApplicationModel::AppService::AppServiceResponse>>::Status(void)
0x180023ad1  test    eax, eax
0x180023ad3  jnz     short loc_180023ADD
0x180023ad5  mov     rcx, rbx
0x180023ad8  call    ??$wait_for_completed@U?$IAsyncOperation@UAppServiceResponse@AppService@ApplicationModel@Windows@winrt@@@Foundation@Windows@winrt@@@impl@winrt@@YA?A_PAEBU?$IAsyncOperation@UAppServiceResponse@AppService@ApplicationModel@Windows@winrt@@@Foundation@Windows@1@I@Z
0x180023add  mov     ecx, eax; this
0x180023adf  call    ?check_status_canceled@impl@winrt@@YAXW4AsyncStatus@Foundation@Windows@2@@Z; winrt::impl::check_status_canceled(winrt::Windows::Foundation::AsyncStatus)
0x180023ae4  lea     rdx, [rsp+0B8h+arg_8]
0x180023aec  mov     rcx, rbx
0x180023aef  call    ?GetResults@?$consume_Windows_Foundation_IAsyncOperation@U?$IAsyncOperation@UAppServiceResponse@AppService@ApplicationModel@Windows@winrt@@@Foundation@Windows@winrt@@UAppServiceResponse@AppService@ApplicationModel@34@@impl@winrt@@QEBA@XZ; winrt::impl::consume_Windows_Foundation_IAsyncOperation<winrt::Windows::Foundation::IAsyncOperation<winrt::Windows::ApplicationModel::AppService::AppServiceResponse>,winrt::Windows::ApplicationModel::AppService::AppServiceResponse>::GetResults(void)
0x180023af4  nop
0x180023af5  lea     rcx, [rsp+0B8h+arg_18]
0x180023afd  call    ??1?$com_ptr@UIWeakReferenceSource@impl@winrt@@@winrt@@QEAA@XZ; winrt::com_ptr<winrt::impl::IWeakReferenceSource>::~com_ptr<winrt::impl::IWeakReferenceSource>(void)
0x180023b02  lea     rcx, [rsp+0B8h+arg_8]
0x180023b0a  call    ?Status@?$consume_Windows_ApplicationModel_AppService_IAppServiceResponse@UIAppServiceResponse@AppService@ApplicationModel@Windows@winrt@@@impl@winrt@@QEBA@XZ; winrt::impl::consume_Windows_ApplicationModel_AppService_IAppServiceResponse<winrt::Windows::ApplicationModel::AppService::IAppServiceResponse>::Status(void)
0x180023b0f  mov     rcx, [rsp+0B8h]; this
0x180023b17  test    eax, eax
0x180023b19  jz      short loc_180023B32
0x180023b1b  mov     r9d, 80004005h; char *
0x180023b21  lea     r8, aOnecoreuapWind_4; "onecoreuap\\windows\\accessibletech\\ex"...
0x180023b28  mov     edx, 51h ; 'Q'; void *
0x180023b2d  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x180023b32  lea     rdx, [rsp+0B8h+var_90]
0x180023b37  lea     rcx, [rsp+0B8h+arg_8]
0x180023b3f  call    ?GetDefault@?$consume_Windows_Internal_UI_Notifications_IQuietHoursSettingsInteropStatics@UIQuietHoursSettingsInteropStatics@Notifications@UI@Internal@Windows@winrt@@@impl@winrt@@QEBA@XZ; winrt::impl::consume_Windows_Internal_UI_Notifications_IQuietHoursSettingsInteropStatics<winrt::Windows::Internal::UI::Notifications::IQuietHoursSettingsInteropStatics>::GetDefault(void)
0x180023b44  nop
0x180023b45  mov     rbx, [rsp+0B8h]
0x180023b4d  mov     qword ptr [rsp+0B8h+var_98], 0; int
0x180023b56  lea     rdx, [rsp+0B8h+var_98]
0x180023b5b  mov     rcx, rax
0x180023b5e  call    ??8Foundation@Windows@winrt@@YA_NAEBUIUnknown@012@0@Z; winrt::Windows::Foundation::operator==(winrt::Windows::Foundation::IUnknown const &,winrt::Windows::Foundation::IUnknown const &)
0x180023b63  test    al, al
0x180023b65  jz      short loc_180023B82
0x180023b67  mov     r9d, 80004005h; char *
0x180023b6d  lea     r8, aOnecoreuapWind_4; "onecoreuap\\windows\\accessibletech\\ex"...
0x180023b74  mov     edx, 52h ; 'R'; void *
0x180023b79  mov     rcx, rbx; this
0x180023b7c  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x180023b82  lea     rcx, [rsp+0B8h+var_90]
0x180023b87  call    ??1?$com_ptr@UIWeakReferenceSource@impl@winrt@@@winrt@@QEAA@XZ; winrt::com_ptr<winrt::impl::IWeakReferenceSource>::~com_ptr<winrt::impl::IWeakReferenceSource>(void)
0x180023b8c  lea     rdx, [rsp+0B8h+var_98]
0x180023b91  lea     rcx, [rsp+0B8h+arg_8]
0x180023b99  call    ?GetDefault@?$consume_Windows_Internal_UI_Notifications_IQuietHoursSettingsInteropStatics@UIQuietHoursSettingsInteropStatics@Notifications@UI@Internal@Windows@winrt@@@impl@winrt@@QEBA@XZ; winrt::impl::consume_Windows_Internal_UI_Notifications_IQuietHoursSettingsInteropStatics<winrt::Windows::Internal::UI::Notifications::IQuietHoursSettingsInteropStatics>::GetDefault(void)
0x180023b9e  mov     rbx, rax
0x180023ba1  lea     rdx, aFocussessionjs; "FocusSessionJson"
0x180023ba8  lea     rcx, [rsp+0B8h+var_58]; this
0x180023bad  call    ??0hstring@param@winrt@@QEAA@QEBG@Z; winrt::param::hstring::hstring(ushort const * const)
0x180023bb2  lea     rdx, [rsp+0B8h+var_58]
0x180023bb7  mov     rcx, rbx
0x180023bba  call    ?HasKey@?$consume_Windows_Foundation_Collections_IMap@UIPropertySet@Collections@Foundation@Windows@winrt@@Uhstring@5@UIInspectable@345@@impl@winrt@@QEBA@AEBUhstring@param@3@@Z; winrt::impl::consume_Windows_Foundation_Collections_IMap<winrt::Windows::Foundation::Collections::IPropertySet,winrt::hstring,winrt::Windows::Foundation::IInspectable>::HasKey(winrt::param::hstring const &)
0x180023bbf  mov     rcx, [rsp+0B8h]; this
0x180023bc7  test    al, al
0x180023bc9  jnz     short loc_180023BE3
0x180023bcb  mov     r9d, 80004005h; char *
0x180023bd1  lea     r8, aOnecoreuapWind_4; "onecoreuap\\windows\\accessibletech\\ex"...
0x180023bd8  mov     edx, 53h ; 'S'; void *
0x180023bdd  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x180023be3  lea     rcx, [rsp+0B8h+var_98]
0x180023be8  call    ??1?$com_ptr@UIWeakReferenceSource@impl@winrt@@@winrt@@QEAA@XZ; winrt::com_ptr<winrt::impl::IWeakReferenceSource>::~com_ptr<winrt::impl::IWeakReferenceSource>(void)
0x180023bed  lea     rdx, [rsp+0B8h+var_80]
0x180023bf2  lea     rcx, [rsp+0B8h+arg_8]
0x180023bfa  call    ?GetDefault@?$consume_Windows_Internal_UI_Notifications_IQuietHoursSettingsInteropStatics@UIQuietHoursSettingsInteropStatics@Notifications@UI@Internal@Windows@winrt@@@impl@winrt@@QEBA@XZ; winrt::impl::consume_Windows_Internal_UI_Notifications_IQuietHoursSettingsInteropStatics<winrt::Windows::Internal::UI::Notifications::IQuietHoursSettingsInteropStatics>::GetDefault(void)
0x180023bff  mov     rbx, rax
0x180023c02  lea     rdx, aFocussessionjs; "FocusSessionJson"
0x180023c09  lea     rcx, [rsp+0B8h+var_58]; this
0x180023c0e  call    ??0hstring@param@winrt@@QEAA@QEBG@Z; winrt::param::hstring::hstring(ushort const * const)
0x180023c13  lea     r8, [rsp+0B8h+var_58]
0x180023c18  lea     rdx, [rsp+0B8h+var_90]
0x180023c1d  mov     rcx, rbx
0x180023c20  call    ?Lookup@?$consume_Windows_Foundation_Collections_IMap@UIPropertySet@Collections@Foundation@Windows@winrt@@Uhstring@5@UIInspectable@345@@impl@winrt@@QEBA@AEBUhstring@param@3@@Z; winrt::impl::consume_Windows_Foundation_Collections_IMap<winrt::Windows::Foundation::Collections::IPropertySet,winrt::hstring,winrt::Windows::Foundation::IInspectable>::Lookup(winrt::param::hstring const &)
0x180023c25  nop
0x180023c26  mov     rdx, rax
0x180023c29  lea     rcx, [rsp+0B8h+var_88]
0x180023c2e  call    ??$unbox_value_type@Uhstring@winrt@@AEBUIInspectable@Foundation@Windows@2@@impl@winrt@@YA?AUhstring@1@AEBUIInspectable@Foundation@Windows@1@@Z; winrt::impl::unbox_value_type<winrt::hstring,winrt::Windows::Foundation::IInspectable const &>(winrt::Windows::Foundation::IInspectable const &)
0x180023c33  nop
0x180023c34  cmp     [rsp+0B8h+var_90], 0
0x180023c3a  jz      short loc_180023C47
0x180023c3c  lea     rcx, [rsp+0B8h+var_90]
0x180023c41  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x180023c46  nop
0x180023c47  lea     rcx, [rsp+0B8h+var_80]
0x180023c4c  call    ??1?$com_ptr@UIWeakReferenceSource@impl@winrt@@@winrt@@QEAA@XZ; winrt::com_ptr<winrt::impl::IWeakReferenceSource>::~com_ptr<winrt::impl::IWeakReferenceSource>(void)
0x180023c51  mov     rax, [rsp+0B8h+var_88]
0x180023c56  mov     qword ptr [rsp+0B8h+var_78], rax
0x180023c5b  lea     rax, [rsp+0B8h+var_78]
0x180023c60  mov     qword ptr [rsp+0B8h+var_98], rax; int
0x180023c65  lea     rax, qword_180046C18
0x180023c6c  mov     [rsp+0B8h+var_38], rax
0x180023c74  lock inc cs:qword_180046C18
0x180023c7c  cmp     cs:??$factory_cache_entry_v@UJsonObject@Json@Data@Windows@winrt@@UIJsonObjectStatics@2345@@impl@winrt@@3U?$factory_cache_entry@UJsonObject@Json@Data@Windows@winrt@@UIJsonObjectStatics@2345@@12@A, 0; factory_cache_entry<winrt::Windows::Data::Json::JsonObject,winrt::Windows::Data::Json::IJsonObjectStatics>::winrt::factory_cache_entry<winrt::Windows::Data::Json::JsonObject,winrt::Windows::Data::Json::IJsonObjectStatics> winrt::impl::factory_cache_entry_v<winrt::Windows::Data::Json::JsonObject,winrt::Windows::Data::Json::IJsonObjectStatics>
0x180023c84  jz      short loc_180023CAA
0x180023c86  lea     r8, ??$factory_cache_entry_v@UJsonObject@Json@Data@Windows@winrt@@UIJsonObjectStatics@2345@@impl@winrt@@3U?$factory_cache_entry@UJsonObject@Json@Data@Windows@winrt@@UIJsonObjectStatics@2345@@12@A; factory_cache_entry<winrt::Windows::Data::Json::JsonObject,winrt::Windows::Data::Json::IJsonObjectStatics>::winrt::factory_cache_entry<winrt::Windows::Data::Json::JsonObject,winrt::Windows::Data::Json::IJsonObjectStatics> winrt::impl::factory_cache_entry_v<winrt::Windows::Data::Json::JsonObject,winrt::Windows::Data::Json::IJsonObjectStatics>
0x180023c8d  lea     rdx, [rsp+0B8h+arg_18]
0x180023c95  lea     rcx, [rsp+0B8h+var_98]
0x180023c9a  call    ??R_lambda_6572cb39eb053ecf8aa601a8cecd7f9b_@@QEBA@AEBUIJsonObjectStatics@Json@Data@Windows@winrt@@@Z; _lambda_6572cb39eb053ecf8aa601a8cecd7f9b_::operator()(winrt::Windows::Data::Json::IJsonObjectStatics const &)
0x180023c9f  nop
0x180023ca0  lock dec cs:qword_180046C18
0x180023ca8  jmp     short loc_180023CC5
0x180023caa  lock dec cs:qword_180046C18
0x180023cb2  lea     r8, [rsp+0B8h+var_98]
0x180023cb7  lea     rdx, [rsp+0B8h+arg_18]
0x180023cbf  call    ??$call@AEAV_lambda_6572cb39eb053ecf8aa601a8cecd7f9b_@@@?$factory_cache_entry@UJsonObject@Json@Data@Windows@winrt@@UIJsonObjectStatics@2345@@impl@winrt@@QEAA?A_PAEAV_lambda_6572cb39eb053ecf8aa601a8cecd7f9b_@@@Z
0x180023cc4  nop
0x180023cc5  lea     rdx, aIssuccess; "isSuccess"
0x180023ccc  lea     rcx, [rsp+0B8h+var_30]; this
0x180023cd4  call    ??0hstring@param@winrt@@QEAA@QEBG@Z; winrt::param::hstring::hstring(ushort const * const)
0x180023cd9  lea     rdx, [rsp+0B8h+var_30]
0x180023ce1  lea     rcx, [rsp+0B8h+arg_18]
0x180023ce9  call    ?GetNamedBoolean@?$consume_Windows_Data_Json_IJsonObject@UIJsonObject@Json@Data@Windows@winrt@@@impl@winrt@@QEBA@AEBUhstring@param@3@@Z; winrt::impl::consume_Windows_Data_Json_IJsonObject<winrt::Windows::Data::Json::IJsonObject>::GetNamedBoolean(winrt::param::hstring const &)
0x180023cee  mov     rcx, [rsp+0B8h]; this
0x180023cf6  test    al, al
0x180023cf8  jnz     short loc_180023D12
0x180023cfa  mov     r9d, 80004005h; char *
0x180023d00  lea     r8, aOnecoreuapWind_4; "onecoreuap\\windows\\accessibletech\\ex"...
0x180023d07  mov     edx, 56h ; 'V'; void *
0x180023d0c  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x180023d12  lea     rcx, [rsp+0B8h+arg_18]
0x180023d1a  call    ??1?$com_ptr@UIWeakReferenceSource@impl@winrt@@@winrt@@QEAA@XZ; winrt::com_ptr<winrt::impl::IWeakReferenceSource>::~com_ptr<winrt::impl::IWeakReferenceSource>(void)
0x180023d1f  nop
0x180023d20  lea     rcx, [rsp+0B8h+var_88]
0x180023d25  call    ?close@?$handle_type@Uhstring_traits@impl@winrt@@@winrt@@QEAAXXZ; winrt::handle_type<winrt::impl::hstring_traits>::close(void)
0x180023d2a  nop
0x180023d2b  lea     rcx, [rsp+0B8h+arg_8]
0x180023d33  call    ??1?$com_ptr@UIWeakReferenceSource@impl@winrt@@@winrt@@QEAA@XZ; winrt::com_ptr<winrt::impl::IWeakReferenceSource>::~com_ptr<winrt::impl::IWeakReferenceSource>(void)
0x180023d38  nop
0x180023d39  lea     rcx, [rsp+0B8h+arg_10]
0x180023d41  call    ??1?$com_ptr@UIWeakReferenceSource@impl@winrt@@@winrt@@QEAA@XZ; winrt::com_ptr<winrt::impl::IWeakReferenceSource>::~com_ptr<winrt::impl::IWeakReferenceSource>(void)
0x180023d46  nop
0x180023d47  lea     rcx, [rsp+0B8h+arg_0]
0x180023d4f  call    ??1?$com_ptr@UIWeakReferenceSource@impl@winrt@@@winrt@@QEAA@XZ; winrt::com_ptr<winrt::impl::IWeakReferenceSource>::~com_ptr<winrt::impl::IWeakReferenceSource>(void)
0x180023d54  nop
0x180023d55  jmp     short $+2
0x180023d57  add     rsp, 0B0h
0x180023d5e  pop     rbx
0x180023d5f  retn
```
