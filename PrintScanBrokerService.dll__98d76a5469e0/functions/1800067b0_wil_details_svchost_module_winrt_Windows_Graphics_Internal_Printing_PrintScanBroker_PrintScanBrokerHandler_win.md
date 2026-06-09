# wil::details::svchost_module<winrt::Windows::Graphics::Internal::Printing::PrintScanBroker::PrintScanBrokerHandler,winrt::Windows::Graphics::Internal::Printing::PrintScanBroker::VirtualPrinterInstallerBroker,winrt::Windows::Graphics::Internal::Printing::PrintScanBroker::IppQueuePropertyBagHandler>::populate_winrt_runtime_classes_helper<1>(std::array<winrt::hstring,3> &,std::array<HSTRING__ *,3> &,std::array<long (*)(HSTRING__ *,IActivationFactory * *),3> &)

- ea: `0x1800067b0`
- end: `0x180006883`
- name: `??$populate_winrt_runtime_classes_helper@$00@?$svchost_module@UPrintScanBrokerHandler@PrintScanBroker@Printing@Internal@Graphics@Windows@winrt@@UVirtualPrinterInstallerBroker@234567@UIppQueuePropertyBagHandler@234567@@details@wil@@AEAAXAEAV?$array@Uhstring@winrt@@$02@std@@AEAV?$array@PEAUHSTRING__@@$02@4@AEAV?$array@P6AJPEAUHSTRING__@@PEAPEAUIActivationFactory@@@Z$02@4@@Z`
- size: `211`
- prototype: `__int64 (__fastcall *__fastcall(__int64, __int64, __int64, __int64))(HSTRING, struct IActivationFactory **)`
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting, installer_update, broker_com_uri`

## callers

- `0x180010750`

## callees

- `0x1800067b0`
- `0x180007908`
- `0x18000f9e4`
- `0x18000fb60`

## string_xrefs

- `0x180006832`: `Windows.Graphics.Internal.Printing.PrintScanBroker.IppQueuePropertyBagHandler`
- `0x1800067ca`: `Windows.Graphics.Internal.Printing.PrintScanBroker.VirtualPrinterInstallerBroker`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 (__fastcall *__fastcall wil::details::svchost_module<winrt::Windows::Graphics::Internal::Printing::PrintScanBroker::PrintScanBrokerHandler,winrt::Windows::Graphics::Internal::Printing::PrintScanBroker::VirtualPrinterInstallerBroker,winrt::Windows::Graphics::Internal::Printing::PrintScanBroker::IppQueuePropertyBagHandler>::populate_winrt_runtime_classes_helper<1>(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        __int64 a4))(HSTRING, struct IActivationFactory **)
{
  __int64 *v7; // rax
  __int64 v8; // rdx
  __int64 *v9; // rax
  __int64 v10; // rdx
  __int64 (__fastcall *result)(HSTRING, struct IActivationFactory **); // rax
  const unsigned __int16 *v12; // [rsp+20h] [rbp-38h] BYREF
  __int64 v13; // [rsp+28h] [rbp-30h]
  __int64 v14; // [rsp+60h] [rbp+8h] BYREF

  v14 = a1;
  v13 = 80;
  v12 = L"Windows.Graphics.Internal.Printing.PrintScanBroker.VirtualPrinterInstallerBroker";
  v7 = (__int64 *)winrt::hstring::hstring(&v14, &v12);
  if ( (__int64 *)(a2 + 8) != v7 )
  {
    v8 = *v7;
    *v7 = 0;
    winrt::handle_type<winrt::impl::hstring_traits>::attach(a2 + 8, v8);
  }
  winrt::handle_type<winrt::impl::hstring_traits>::close(&v14);
  *(_QWORD *)(a3 + 8) = *(_QWORD *)(a2 + 8);
  v13 = 77;
  *(_QWORD *)(a4 + 8) = _lambda_7b07dda4ae1ef9ba284f70f557fc27c8_::_lambda_invoker_cdecl_;
  v12 = L"Windows.Graphics.Internal.Printing.PrintScanBroker.IppQueuePropertyBagHandler";
  v9 = (__int64 *)winrt::hstring::hstring(&v14, &v12);
  if ( (__int64 *)(a2 + 16) != v9 )
  {
    v10 = *v9;
    *v9 = 0;
    winrt::handle_type<winrt::impl::hstring_traits>::attach(a2 + 16, v10);
  }
  winrt::handle_type<winrt::impl::hstring_traits>::close(&v14);
  *(_QWORD *)(a3 + 16) = *(_QWORD *)(a2 + 16);
  result = _lambda_7b07dda4ae1ef9ba284f70f557fc27c8_::_lambda_invoker_cdecl_;
  *(_QWORD *)(a4 + 16) = _lambda_7b07dda4ae1ef9ba284f70f557fc27c8_::_lambda_invoker_cdecl_;
  return result;
}

```

## disassembly

```asm
0x1800067b0  mov     r11, rsp
0x1800067b3  mov     [r11+8], rcx
0x1800067b7  push    rbx
0x1800067b8  push    rbp
0x1800067b9  push    rsi
0x1800067ba  push    rdi
0x1800067bb  sub     rsp, 38h
0x1800067bf  mov     rbp, rdx
0x1800067c2  mov     qword ptr [r11-30h], 50h ; 'P'
0x1800067ca  lea     rax, aWindowsGraphic; "Windows.Graphics.Internal.Printing.Prin"...
0x1800067d1  mov     rdi, r9
0x1800067d4  lea     rdx, [r11-38h]
0x1800067d8  mov     [r11-38h], rax
0x1800067dc  lea     rcx, [r11+8]
0x1800067e0  mov     rsi, r8
0x1800067e3  call    ??0hstring@winrt@@QEAA@AEBV?$basic_string_view@GU?$char_traits@G@std@@@std@@@Z; winrt::hstring::hstring(std::basic_string_view<ushort> const &)
0x1800067e8  lea     rbx, [rbp+8]
0x1800067ec  cmp     rbx, rax
0x1800067ef  jz      short loc_180006803
0x1800067f1  mov     rdx, [rax]
0x1800067f4  mov     rcx, rbx
0x1800067f7  mov     qword ptr [rax], 0
0x1800067fe  call    ?attach@?$handle_type@Uhstring_traits@impl@winrt@@@winrt@@QEAAXPEAUhstring_header@impl@2@@Z; winrt::handle_type<winrt::impl::hstring_traits>::attach(winrt::impl::hstring_header *)
0x180006803  lea     rcx, [rsp+58h+arg_0]
0x180006808  call    ?close@?$handle_type@Uhstring_traits@impl@winrt@@@winrt@@QEAAXXZ; winrt::handle_type<winrt::impl::hstring_traits>::close(void)
0x18000680d  mov     rax, [rbx]
0x180006810  lea     rdx, [rsp+58h+var_38]
0x180006815  mov     [rsi+8], rax
0x180006819  lea     rcx, [rsp+58h+arg_0]
0x18000681e  lea     rax, ?_lambda_invoker_cdecl_@_lambda_7b07dda4ae1ef9ba284f70f557fc27c8_@@CAJPEAUHSTRING__@@PEAPEAUIActivationFactory@@@Z; _lambda_7b07dda4ae1ef9ba284f70f557fc27c8_::_lambda_invoker_cdecl_(HSTRING__ *,IActivationFactory * *)
0x180006825  mov     [rsp+58h+var_30], 4Dh ; 'M'
0x18000682e  mov     [rdi+8], rax
0x180006832  lea     rax, aWindowsGraphic_1; "Windows.Graphics.Internal.Printing.Prin"...
0x180006839  mov     [rsp+58h+var_38], rax
0x18000683e  call    ??0hstring@winrt@@QEAA@AEBV?$basic_string_view@GU?$char_traits@G@std@@@std@@@Z; winrt::hstring::hstring(std::basic_string_view<ushort> const &)
0x180006843  lea     rbx, [rbp+10h]
0x180006847  cmp     rbx, rax
0x18000684a  jz      short loc_18000685E
0x18000684c  mov     rdx, [rax]
0x18000684f  mov     rcx, rbx
0x180006852  mov     qword ptr [rax], 0
0x180006859  call    ?attach@?$handle_type@Uhstring_traits@impl@winrt@@@winrt@@QEAAXPEAUhstring_header@impl@2@@Z; winrt::handle_type<winrt::impl::hstring_traits>::attach(winrt::impl::hstring_header *)
0x18000685e  lea     rcx, [rsp+58h+arg_0]
0x180006863  call    ?close@?$handle_type@Uhstring_traits@impl@winrt@@@winrt@@QEAAXXZ; winrt::handle_type<winrt::impl::hstring_traits>::close(void)
0x180006868  mov     rax, [rbx]
0x18000686b  mov     [rsi+10h], rax
0x18000686f  lea     rax, ?_lambda_invoker_cdecl_@_lambda_7b07dda4ae1ef9ba284f70f557fc27c8_@@CAJPEAUHSTRING__@@PEAPEAUIActivationFactory@@@Z; _lambda_7b07dda4ae1ef9ba284f70f557fc27c8_::_lambda_invoker_cdecl_(HSTRING__ *,IActivationFactory * *)
0x180006876  mov     [rdi+10h], rax
0x18000687a  add     rsp, 38h
0x18000687e  pop     rdi
0x18000687f  pop     rsi
0x180006880  pop     rbp
0x180006881  pop     rbx
0x180006882  retn
```
