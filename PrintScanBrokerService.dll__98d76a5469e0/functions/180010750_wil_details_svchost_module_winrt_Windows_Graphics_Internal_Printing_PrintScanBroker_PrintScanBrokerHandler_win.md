# wil::details::svchost_module<winrt::Windows::Graphics::Internal::Printing::PrintScanBroker::PrintScanBrokerHandler,winrt::Windows::Graphics::Internal::Printing::PrintScanBroker::VirtualPrinterInstallerBroker,winrt::Windows::Graphics::Internal::Printing::PrintScanBroker::IppQueuePropertyBagHandler>::populate_winrt_runtime_classes(void)

- ea: `0x180010750`
- end: `0x1800108a3`
- name: `?populate_winrt_runtime_classes@?$svchost_module@UPrintScanBrokerHandler@PrintScanBroker@Printing@Internal@Graphics@Windows@winrt@@UVirtualPrinterInstallerBroker@234567@UIppQueuePropertyBagHandler@234567@@details@wil@@AEAAXXZ`
- size: `339`
- prototype: `void __fastcall(__int64)`
- caller_count: `1`
- callee_count: `10`
- tags: `registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x1800088f4`

## callees

- `0x180002d40`
- `0x180002dd8`
- `0x1800032bc`
- `0x1800067b0`
- `0x180007908`
- `0x18000f9e4`
- `0x18000fa48`
- `0x18000fb60`
- `0x180010750`
- `0x180010cf4`

## import_xrefs

- `api-ms-win-core-winrt-l1-1-0!RoRegisterActivationFactories` at `0x180010856`
- `api-ms-win-core-winrt-l1-1-0!RoRegisterActivationFactories` at `0x180010856`

## string_xrefs

- `0x1800107c1`: `Windows.Graphics.Internal.Printing.PrintScanBroker.PrintScanBrokerHandler`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall wil::details::svchost_module<winrt::Windows::Graphics::Internal::Printing::PrintScanBroker::PrintScanBrokerHandler,winrt::Windows::Graphics::Internal::Printing::PrintScanBroker::VirtualPrinterInstallerBroker,winrt::Windows::Graphics::Internal::Printing::PrintScanBroker::IppQueuePropertyBagHandler>::populate_winrt_runtime_classes(
        __int64 a1)
{
  __int128 *v2; // rax
  __int64 v3; // rdx
  __int64 v4; // rcx
  unsigned int v5; // eax
  _BYTE v6[8]; // [rsp+30h] [rbp-19h] BYREF
  const unsigned __int16 *v7; // [rsp+38h] [rbp-11h] BYREF
  __int128 v8; // [rsp+40h] [rbp-9h]
  __int128 v9; // [rsp+50h] [rbp+7h] BYREF
  __int64 v10; // [rsp+60h] [rbp+17h]
  __int128 v11; // [rsp+68h] [rbp+1Fh] BYREF
  __int64 v12; // [rsp+78h] [rbp+2Fh]
  __int128 v13; // [rsp+80h] [rbp+37h] BYREF
  __int64 v14; // [rsp+90h] [rbp+47h]

  v13 = 0;
  v14 = 0;
  `eh vector constructor iterator'(
    &v13,
    8u,
    3u,
    (void (*)(void *))winrt::hstring::hstring,
    (void (*)(void *))winrt::hstring::~hstring);
  v11 = 0;
  v12 = 0;
  v9 = 0;
  v10 = 0;
  v7 = L"Windows.Graphics.Internal.Printing.PrintScanBroker.PrintScanBrokerHandler";
  *(_QWORD *)&v8 = 73;
  v2 = (__int128 *)winrt::hstring::hstring(v6, &v7);
  if ( &v13 != v2 )
  {
    v3 = *(_QWORD *)v2;
    *(_QWORD *)v2 = 0;
    winrt::handle_type<winrt::impl::hstring_traits>::attach(&v13, v3);
  }
  winrt::handle_type<winrt::impl::hstring_traits>::close(v6);
  *(_QWORD *)&v11 = v13;
  *(_QWORD *)&v9 = _lambda_7b07dda4ae1ef9ba284f70f557fc27c8_::_lambda_invoker_cdecl_;
  wil::details::svchost_module<winrt::Windows::Graphics::Internal::Printing::PrintScanBroker::PrintScanBrokerHandler,winrt::Windows::Graphics::Internal::Printing::PrintScanBroker::VirtualPrinterInstallerBroker,winrt::Windows::Graphics::Internal::Printing::PrintScanBroker::IppQueuePropertyBagHandler>::populate_winrt_runtime_classes_helper<1>(
    v4,
    (__int64)&v13,
    (__int64)&v11,
    (__int64)&v9);
  LODWORD(v7) = 0;
  v8 = 0;
  wil::details::unique_storage<wil::details::resource_policy<_RO_REGISTRATION_COOKIE *,void (*)(_RO_REGISTRATION_COOKIE *),&void RoRevokeActivationFactories(_RO_REGISTRATION_COOKIE *),wistd::integral_constant<unsigned __int64,0>,_RO_REGISTRATION_COOKIE *,_RO_REGISTRATION_COOKIE *,0,std::nullptr_t>>::reset(
    a1 + 8,
    0);
  v5 = RoRegisterActivationFactories(&v11, &v9, 3, a1 + 8);
  winrt::check_hresult(v6, v5, &v7);
  `eh vector destructor iterator'(&v13, 8u, 3u, (void (*)(void *))winrt::hstring::~hstring);
}

```

## disassembly

```asm
0x180010750  mov     [rsp-8+arg_8], rbx
0x180010755  mov     [rsp-8+arg_10], rsi
0x18001075a  push    rbp
0x18001075b  lea     rbp, [rsp-57h]
0x180010760  sub     rsp, 0A0h
0x180010767  mov     rax, cs:__security_cookie
0x18001076e  xor     rax, rsp
0x180010771  mov     [rbp+57h+var_8], rax
0x180010775  mov     rbx, rcx
0x180010778  xorps   xmm0, xmm0
0x18001077b  xor     eax, eax
0x18001077d  movups  [rbp+57h+var_20], xmm0
0x180010781  mov     [rbp+57h+var_10], rax
0x180010785  lea     rsi, ??1hstring@winrt@@QEAA@XZ; winrt::hstring::~hstring(void)
0x18001078c  mov     [rsp+0A0h+var_80], rsi; void (*)(void *)
0x180010791  lea     r9, ??0hstring@winrt@@QEAA@XZ; void (*)(void *)
0x180010798  lea     edx, [rax+8]; unsigned __int64
0x18001079b  lea     r8d, [rax+3]; unsigned __int64
0x18001079f  lea     rcx, [rbp+57h+var_20]; void *
0x1800107a3  call    ??_L@YAXPEAX_K1P6AX0@Z2@Z; `eh vector constructor iterator'(void *,unsigned __int64,unsigned __int64,void (*)(void *),void (*)(void *))
0x1800107a8  nop
0x1800107a9  xorps   xmm0, xmm0
0x1800107ac  xor     eax, eax
0x1800107ae  movups  [rbp+57h+var_38], xmm0
0x1800107b2  mov     [rbp+57h+var_28], rax
0x1800107b6  xorps   xmm1, xmm1
0x1800107b9  movups  [rbp+57h+var_50], xmm1
0x1800107bd  mov     [rbp+57h+var_40], rax
0x1800107c1  lea     rax, aWindowsGraphic_0; "Windows.Graphics.Internal.Printing.Prin"...
0x1800107c8  mov     [rbp+57h+var_68], rax
0x1800107cc  mov     qword ptr [rbp+57h+var_60], 49h ; 'I'
0x1800107d4  lea     rdx, [rbp+57h+var_68]
0x1800107d8  lea     rcx, [rbp+57h+var_70]
0x1800107dc  call    ??0hstring@winrt@@QEAA@AEBV?$basic_string_view@GU?$char_traits@G@std@@@std@@@Z; winrt::hstring::hstring(std::basic_string_view<ushort> const &)
0x1800107e1  lea     rcx, [rbp+57h+var_20]
0x1800107e5  cmp     rcx, rax
0x1800107e8  jz      short loc_1800107FD
0x1800107ea  mov     rdx, [rax]
0x1800107ed  mov     qword ptr [rax], 0
0x1800107f4  lea     rcx, [rbp+57h+var_20]
0x1800107f8  call    ?attach@?$handle_type@Uhstring_traits@impl@winrt@@@winrt@@QEAAXPEAUhstring_header@impl@2@@Z; winrt::handle_type<winrt::impl::hstring_traits>::attach(winrt::impl::hstring_header *)
0x1800107fd  lea     rcx, [rbp+57h+var_70]
0x180010801  call    ?close@?$handle_type@Uhstring_traits@impl@winrt@@@winrt@@QEAAXXZ; winrt::handle_type<winrt::impl::hstring_traits>::close(void)
0x180010806  mov     rax, qword ptr [rbp+57h+var_20]
0x18001080a  mov     qword ptr [rbp+57h+var_38], rax
0x18001080e  lea     rax, ?_lambda_invoker_cdecl_@_lambda_7b07dda4ae1ef9ba284f70f557fc27c8_@@CAJPEAUHSTRING__@@PEAPEAUIActivationFactory@@@Z; _lambda_7b07dda4ae1ef9ba284f70f557fc27c8_::_lambda_invoker_cdecl_(HSTRING__ *,IActivationFactory * *)
0x180010815  mov     qword ptr [rbp+57h+var_50], rax
0x180010819  lea     r9, [rbp+57h+var_50]
0x18001081d  lea     r8, [rbp+57h+var_38]
0x180010821  lea     rdx, [rbp+57h+var_20]
0x180010825  call    ??$populate_winrt_runtime_classes_helper@$00@?$svchost_module@UPrintScanBrokerHandler@PrintScanBroker@Printing@Internal@Graphics@Windows@winrt@@UVirtualPrinterInstallerBroker@234567@UIppQueuePropertyBagHandler@234567@@details@wil@@AEAAXAEAV?$array@Uhstring@winrt@@$02@std@@AEAV?$array@PEAUHSTRING__@@$02@4@AEAV?$array@P6AJPEAUHSTRING__@@PEAPEAUIActivationFactory@@@Z$02@4@@Z; wil::details::svchost_module<winrt::Windows::Graphics::Internal::Printing::PrintScanBroker::PrintScanBrokerHandler,winrt::Windows::Graphics::Internal::Printing::PrintScanBroker::VirtualPrinterInstallerBroker,winrt::Windows::Graphics::Internal::Printing::PrintScanBroker::IppQueuePropertyBagHandler>::populate_winrt_runtime_classes_helper<1>(std::array<winrt::hstring,3> &,std::array<HSTRING__ *,3> &,std::array<long (*)(HSTRING__ *,IActivationFactory * *),3> &)
0x18001082a  mov     dword ptr [rbp+57h+var_68], 0
0x180010831  xorps   xmm0, xmm0
0x180010834  movdqu  [rbp+57h+var_60], xmm0
0x180010839  xor     edx, edx
0x18001083b  lea     rcx, [rbx+8]
0x18001083f  call    ?reset@?$unique_storage@U?$resource_policy@PEAU_RO_REGISTRATION_COOKIE@@P6AXPEAU1@@Z$1?RoRevokeActivationFactories@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAU_RO_REGISTRATION_COOKIE@@@Z; wil::details::unique_storage<wil::details::resource_policy<_RO_REGISTRATION_COOKIE *,void (*)(_RO_REGISTRATION_COOKIE *),&RoRevokeActivationFactories(_RO_REGISTRATION_COOKIE *),wistd::integral_constant<unsigned __int64,0>,_RO_REGISTRATION_COOKIE *,_RO_REGISTRATION_COOKIE *,0,std::nullptr_t>>::reset(_RO_REGISTRATION_COOKIE *)
0x180010844  lea     r9, [rbx+8]
0x180010848  mov     r8d, 3
0x18001084e  lea     rdx, [rbp+57h+var_50]
0x180010852  lea     rcx, [rbp+57h+var_38]
0x180010856  call    cs:__imp_RoRegisterActivationFactories
0x18001085c  lea     r8, [rbp+57h+var_68]
0x180010860  mov     edx, eax
0x180010862  lea     rcx, [rbp+57h+var_70]
0x180010866  call    ?check_hresult@winrt@@YA?AUhresult@1@U21@AEBUslim_source_location@impl@1@@Z; winrt::check_hresult(winrt::hresult,winrt::impl::slim_source_location const &)
0x18001086b  nop
0x18001086c  mov     r9, rsi; void (*)(void *)
0x18001086f  mov     edx, 8; unsigned __int64
0x180010874  lea     r8d, [rdx-5]; unsigned __int64
0x180010878  lea     rcx, [rbp+57h+var_20]; void *
0x18001087c  call    ??_M@YAXPEAX_K1P6AX0@Z@Z; `eh vector destructor iterator'(void *,unsigned __int64,unsigned __int64,void (*)(void *))
0x180010881  nop
0x180010882  mov     rcx, [rbp+57h+var_8]
0x180010886  xor     rcx, rsp; StackCookie
0x180010889  call    __security_check_cookie
0x18001088e  lea     r11, [rsp+0A0h+var_s0]
0x180010896  mov     rbx, [r11+18h]
0x18001089a  mov     rsi, [r11+20h]
0x18001089e  mov     rsp, r11
0x1800108a1  pop     rbp
0x1800108a2  retn
```
