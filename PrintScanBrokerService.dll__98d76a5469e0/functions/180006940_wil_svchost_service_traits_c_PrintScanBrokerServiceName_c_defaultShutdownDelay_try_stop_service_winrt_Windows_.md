# wil::svchost_service_traits_&c_PrintScanBrokerServiceName_&c_defaultShutdownDelay_::try_stop_service_winrt::Windows::Graphics::Internal::Printing::PrintScanBroker::PrintScanBrokerHandler_winrt::Windows::Graphics::Internal::Printing::PrintScanBroker::VirtualPrinterInstallerBroker_winrt::Windows::Graphics::Internal::Printing::PrintScanBroker::IppQueuePropertyBagHandler_

- ea: `0x180006940`
- end: `0x180006ad9`
- name: `wil::svchost_service_traits_&c_PrintScanBrokerServiceName_&c_defaultShutdownDelay_::try_stop_service_winrt::Windows::Graphics::Internal::Printing::PrintScanBroker::PrintScanBrokerHandler_winrt::Windows::Graphics::Internal::Printing::PrintScanBroker::VirtualPrinterInstallerBroker_winrt::Windows::Graphics::Internal::Printing::PrintScanBroker::IppQueuePropertyBagHandler_`
- size: `409`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `8`
- tags: `loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x180006ae0`

## callees

- `0x180004a5c`
- `0x18000624c`
- `0x180006940`
- `0x1800078e4`
- `0x180007a58`
- `0x180008920`
- `0x18000fa48`
- `0x180048010`

## string_xrefs

- `0x180006a7a`: `Windows.Graphics.Internal.Printing.PrintScanBroker.IppQueuePropertyBagHandler`
- `0x180006a22`: `Windows.Graphics.Internal.Printing.PrintScanBroker.PrintScanBrokerHandler`
- `0x180006a4e`: `Windows.Graphics.Internal.Printing.PrintScanBroker.VirtualPrinterInstallerBroker`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
char __fastcall wil::svchost_service_traits__c_PrintScanBrokerServiceName__c_defaultShutdownDelay_::try_stop_service_winrt::Windows::Graphics::Internal::Printing::PrintScanBroker::PrintScanBrokerHandler_winrt::Windows::Graphics::Internal::Printing::PrintScanBroker::VirtualPrinterInstallerBroker_winrt::Windows::Graphics::Internal::Printing::PrintScanBroker::IppQueuePropertyBagHandler_(
        __int64 a1,
        __int64 a2,
        void (__fastcall ***a3)(_QWORD, __int64 *, __int64 *))
{
  unsigned int v3; // eax
  __int64 v4; // rcx
  unsigned int v5; // eax
  winrt::param::hstring *v6; // rax
  winrt::param::hstring *v7; // rax
  winrt::param::hstring *v8; // rax
  const unsigned __int16 *v10; // [rsp+20h] [rbp-29h] BYREF
  __int128 v11; // [rsp+28h] [rbp-21h]
  _BYTE v12[32]; // [rsp+38h] [rbp-11h] BYREF
  _BYTE v13[32]; // [rsp+58h] [rbp+Fh] BYREF
  _BYTE v14[40]; // [rsp+78h] [rbp+2Fh] BYREF
  __int64 v15; // [rsp+B0h] [rbp+67h] BYREF
  signed __int64 v16; // [rsp+B8h] [rbp+6Fh] BYREF
  __int64 v17; // [rsp+C0h] [rbp+77h] BYREF
  __int64 v18; // [rsp+C8h] [rbp+7Fh] BYREF

  _InterlockedIncrement64(&qword_180060CA8);
  if ( winrt::impl::factory_cache_entry_v<winrt::Windows::ApplicationModel::Core::CoreApplication,winrt::Windows::ApplicationModel::Core::ICoreApplicationPrivate> )
  {
    _lambda_bd4c9e68528376f1507e0bbe85836699_::operator()<winrt::Windows::ApplicationModel::Core::ICoreApplicationPrivate const &>(
      a1,
      &v16);
    _InterlockedDecrement64(&qword_180060CA8);
  }
  else
  {
    _InterlockedDecrement64(&qword_180060CA8);
    winrt::impl::factory_cache_entry<winrt::Windows::ApplicationModel::Core::CoreApplication,winrt::Windows::ApplicationModel::Core::ICoreApplicationPrivate>::call<_lambda_bd4c9e68528376f1507e0bbe85836699_ &>(
      a1,
      &v16,
      a3);
  }
  v17 = 0;
  LODWORD(v10) = 0;
  v11 = 0;
  v3 = (*(__int64 (__fastcall **)(signed __int64, __int64 *))(*(_QWORD *)v16 + 56LL))(v16, &v17);
  winrt::check_hresult(&v15, v3, &v10);
  v4 = v17;
  v18 = v17;
  v17 = 0;
  if ( v18 )
  {
    LODWORD(v10) = 0;
    v11 = 0;
    v5 = (**(__int64 (__fastcall ***)(__int64, __int64 *, __int64 *))v4)(
           v4,
           winrt::impl::guid_v<winrt::Windows::Foundation::Collections::IMap<winrt::hstring,winrt::Windows::Foundation::IInspectable>>,
           &v17);
    winrt::check_hresult(&v15, v5, &v10);
    v4 = v17;
  }
  v15 = v4;
  if ( v4 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v4 + 8LL))(v4);
  v10 = L"Windows.Graphics.Internal.Printing.PrintScanBroker.PrintScanBrokerHandler";
  *(_QWORD *)&v11 = 73;
  v6 = winrt::param::hstring::hstring((winrt::param::hstring *)v12, (__int64)&v10);
  lambda_9ea05cc3d6896b746d1fa9df09bb70bd_::operator()(&v15, v6);
  v10 = L"Windows.Graphics.Internal.Printing.PrintScanBroker.VirtualPrinterInstallerBroker";
  *(_QWORD *)&v11 = 80;
  v7 = winrt::param::hstring::hstring((winrt::param::hstring *)v13, (__int64)&v10);
  lambda_9ea05cc3d6896b746d1fa9df09bb70bd_::operator()(&v15, v7);
  v10 = L"Windows.Graphics.Internal.Printing.PrintScanBroker.IppQueuePropertyBagHandler";
  *(_QWORD *)&v11 = 77;
  v8 = winrt::param::hstring::hstring((winrt::param::hstring *)v14, (__int64)&v10);
  lambda_9ea05cc3d6896b746d1fa9df09bb70bd_::operator()(&v15, v8);
  winrt::Windows::Internal::StateRepository::IApplication::~IApplication((winrt::Windows::Internal::StateRepository::IApplication *)&v15);
  winrt::Windows::Internal::StateRepository::IApplication::~IApplication((winrt::Windows::Internal::StateRepository::IApplication *)&v17);
  winrt::Windows::Internal::StateRepository::IApplication::~IApplication((winrt::Windows::Internal::StateRepository::IApplication *)&v18);
  winrt::Windows::Internal::StateRepository::IApplication::~IApplication((winrt::Windows::Internal::StateRepository::IApplication *)&v16);
  return 1;
}

```

## disassembly

```asm
0x180006940  push    rbp
0x180006942  lea     rbp, [rsp-57h]
0x180006947  sub     rsp, 0A0h
0x18000694e  lock inc cs:qword_180060CA8
0x180006956  lea     rdx, [rbp+57h+arg_8]
0x18000695a  cmp     cs:??$factory_cache_entry_v@UCoreApplication@Core@ApplicationModel@Windows@winrt@@UICoreApplicationPrivate@2345@@impl@winrt@@3U?$factory_cache_entry@UCoreApplication@Core@ApplicationModel@Windows@winrt@@UICoreApplicationPrivate@2345@@12@A, 0; factory_cache_entry<winrt::Windows::ApplicationModel::Core::CoreApplication,winrt::Windows::ApplicationModel::Core::ICoreApplicationPrivate>::winrt::factory_cache_entry<winrt::Windows::ApplicationModel::Core::CoreApplication,winrt::Windows::ApplicationModel::Core::ICoreApplicationPrivate> winrt::impl::factory_cache_entry_v<winrt::Windows::ApplicationModel::Core::CoreApplication,winrt::Windows::ApplicationModel::Core::ICoreApplicationPrivate>
0x180006962  jz      short loc_180006973
0x180006964  call    ??$?RAEBUICoreApplicationPrivate@Core@ApplicationModel@Windows@winrt@@@_lambda_bd4c9e68528376f1507e0bbe85836699_@@QEBA?A_PAEBUICoreApplicationPrivate@Core@ApplicationModel@Windows@winrt@@@Z
0x180006969  lock dec cs:qword_180060CA8
0x180006971  jmp     short loc_180006981
0x180006973  lock dec cs:qword_180060CA8
0x18000697b  call    ??$call@AEAV_lambda_bd4c9e68528376f1507e0bbe85836699_@@@?$factory_cache_entry@UCoreApplication@Core@ApplicationModel@Windows@winrt@@UICoreApplicationPrivate@2345@@impl@winrt@@QEAA?A_PAEAV_lambda_bd4c9e68528376f1507e0bbe85836699_@@@Z
0x180006980  nop
0x180006981  mov     [rbp+57h+arg_10], 0
0x180006989  mov     rcx, [rbp+57h+arg_8]
0x18000698d  mov     dword ptr [rbp+57h+var_80], 0
0x180006994  xorps   xmm0, xmm0
0x180006997  movdqu  [rbp+57h+var_78], xmm0
0x18000699c  mov     rax, [rcx]
0x18000699f  lea     rdx, [rbp+57h+arg_10]
0x1800069a3  mov     rax, [rax+38h]
0x1800069a7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800069ac  lea     r8, [rbp+57h+var_80]
0x1800069b0  mov     edx, eax
0x1800069b2  lea     rcx, [rbp+57h+arg_0]
0x1800069b6  call    ?check_hresult@winrt@@YA?AUhresult@1@U21@AEBUslim_source_location@impl@1@@Z; winrt::check_hresult(winrt::hresult,winrt::impl::slim_source_location const &)
0x1800069bb  mov     rcx, [rbp+57h+arg_10]
0x1800069bf  mov     [rbp+57h+arg_18], rcx
0x1800069c3  mov     [rbp+57h+arg_10], 0
0x1800069cb  test    rcx, rcx
0x1800069ce  jz      short loc_180006A0C
0x1800069d0  mov     dword ptr [rbp+57h+var_80], 0
0x1800069d7  xorps   xmm0, xmm0
0x1800069da  movdqu  [rbp+57h+var_78], xmm0
0x1800069df  mov     rax, [rcx]
0x1800069e2  lea     r8, [rbp+57h+arg_10]
0x1800069e6  lea     rdx, ??$guid_v@U?$IMap@Uhstring@winrt@@UIInspectable@Foundation@Windows@2@@Collections@Foundation@Windows@winrt@@@impl@winrt@@3Uguid@2@B; guid::guid const winrt::impl::guid_v<winrt::Windows::Foundation::Collections::IMap<winrt::hstring,winrt::Windows::Foundation::IInspectable>>
0x1800069ed  mov     rax, [rax]
0x1800069f0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800069f5  lea     r8, [rbp+57h+var_80]
0x1800069f9  mov     edx, eax
0x1800069fb  lea     rcx, [rbp+57h+arg_0]
0x1800069ff  call    ?check_hresult@winrt@@YA?AUhresult@1@U21@AEBUslim_source_location@impl@1@@Z; winrt::check_hresult(winrt::hresult,winrt::impl::slim_source_location const &)
0x180006a04  mov     rcx, [rbp+57h+arg_10]
0x180006a08  mov     [rbp+57h+arg_10], rcx
0x180006a0c  mov     [rbp+57h+arg_0], rcx
0x180006a10  test    rcx, rcx
0x180006a13  jz      short loc_180006A22
0x180006a15  mov     rax, [rcx]
0x180006a18  mov     rax, [rax+8]
0x180006a1c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006a21  nop
0x180006a22  lea     rax, aWindowsGraphic_0; "Windows.Graphics.Internal.Printing.Prin"...
0x180006a29  mov     [rbp+57h+var_80], rax
0x180006a2d  mov     qword ptr [rbp+57h+var_78], 49h ; 'I'
0x180006a35  lea     rdx, [rbp+57h+var_80]
0x180006a39  lea     rcx, [rbp+57h+var_68]
0x180006a3d  call    ??0hstring@param@winrt@@QEAA@AEBV?$basic_string_view@GU?$char_traits@G@std@@@std@@@Z; winrt::param::hstring::hstring(std::basic_string_view<ushort> const &)
0x180006a42  mov     rdx, rax
0x180006a45  lea     rcx, [rbp+57h+arg_0]
0x180006a49  call    _lambda_9ea05cc3d6896b746d1fa9df09bb70bd___operator__
0x180006a4e  lea     rax, aWindowsGraphic; "Windows.Graphics.Internal.Printing.Prin"...
0x180006a55  mov     [rbp+57h+var_80], rax
0x180006a59  mov     qword ptr [rbp+57h+var_78], 50h ; 'P'
0x180006a61  lea     rdx, [rbp+57h+var_80]
0x180006a65  lea     rcx, [rbp+57h+var_48]
0x180006a69  call    ??0hstring@param@winrt@@QEAA@AEBV?$basic_string_view@GU?$char_traits@G@std@@@std@@@Z; winrt::param::hstring::hstring(std::basic_string_view<ushort> const &)
0x180006a6e  mov     rdx, rax
0x180006a71  lea     rcx, [rbp+57h+arg_0]
0x180006a75  call    _lambda_9ea05cc3d6896b746d1fa9df09bb70bd___operator__
0x180006a7a  lea     rax, aWindowsGraphic_1; "Windows.Graphics.Internal.Printing.Prin"...
0x180006a81  mov     [rbp+57h+var_80], rax
0x180006a85  mov     qword ptr [rbp+57h+var_78], 4Dh ; 'M'
0x180006a8d  lea     rdx, [rbp+57h+var_80]
0x180006a91  lea     rcx, [rbp+57h+var_28]
0x180006a95  call    ??0hstring@param@winrt@@QEAA@AEBV?$basic_string_view@GU?$char_traits@G@std@@@std@@@Z; winrt::param::hstring::hstring(std::basic_string_view<ushort> const &)
0x180006a9a  mov     rdx, rax
0x180006a9d  lea     rcx, [rbp+57h+arg_0]
0x180006aa1  call    _lambda_9ea05cc3d6896b746d1fa9df09bb70bd___operator__
0x180006aa6  nop
0x180006aa7  lea     rcx, [rbp+57h+arg_0]; this
0x180006aab  call    ??1IApplication@StateRepository@Internal@Windows@winrt@@QEAA@XZ; winrt::Windows::Internal::StateRepository::IApplication::~IApplication(void)
0x180006ab0  nop
0x180006ab1  lea     rcx, [rbp+57h+arg_10]; this
0x180006ab5  call    ??1IApplication@StateRepository@Internal@Windows@winrt@@QEAA@XZ; winrt::Windows::Internal::StateRepository::IApplication::~IApplication(void)
0x180006aba  nop
0x180006abb  lea     rcx, [rbp+57h+arg_18]; this
0x180006abf  call    ??1IApplication@StateRepository@Internal@Windows@winrt@@QEAA@XZ; winrt::Windows::Internal::StateRepository::IApplication::~IApplication(void)
0x180006ac4  nop
0x180006ac5  lea     rcx, [rbp+57h+arg_8]; this
0x180006ac9  call    ??1IApplication@StateRepository@Internal@Windows@winrt@@QEAA@XZ; winrt::Windows::Internal::StateRepository::IApplication::~IApplication(void)
0x180006ace  mov     al, 1
0x180006ad0  add     rsp, 0A0h
0x180006ad7  pop     rbp
0x180006ad8  retn
```
