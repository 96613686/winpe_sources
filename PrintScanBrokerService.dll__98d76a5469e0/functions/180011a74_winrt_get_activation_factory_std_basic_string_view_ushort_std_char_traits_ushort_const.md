# winrt_get_activation_factory(std::basic_string_view<ushort,std::char_traits<ushort>> const &)

- ea: `0x180011a74`
- end: `0x180011b47`
- name: `?winrt_get_activation_factory@@YAPEAXAEBV?$basic_string_view@GU?$char_traits@G@std@@@std@@@Z`
- size: `211`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `loader_planting, installer_update, broker_com_uri`

## callers

- `0x180011be8`

## callees

- `0x180006674`
- `0x1800066e0`
- `0x180006744`
- `0x180007a58`
- `0x1800089bc`
- `0x18000f760`
- `0x180011a74`

## string_xrefs

- `0x180011b0c`: `Windows.Graphics.Internal.Printing.PrintScanBroker.IppQueuePropertyBagHandler`
- `0x180011a9a`: `Windows.Graphics.Internal.Printing.PrintScanBroker.PrintScanBrokerHandler`
- `0x180011ade`: `Windows.Graphics.Internal.Printing.PrintScanBroker.VirtualPrinterInstallerBroker`

## pseudocode

```c
__int64 __fastcall winrt_get_activation_factory(_QWORD *a1)
{
  __int64 v2; // rcx
  __int64 v3; // rcx
  __int64 *v4; // rax
  __int64 v5; // rbx
  __int64 v7; // rcx
  const unsigned __int16 *v8; // [rsp+20h] [rbp-10h] BYREF
  __int64 v9; // [rsp+28h] [rbp-8h]
  __int64 v10; // [rsp+40h] [rbp+10h] BYREF

  PrintScanBrokerTelemetry::WriteDbgTraceInfo(
    "winrt_get_activation_factory",
    L"winrt_get_activation_factory called for: %ws",
    *a1);
  v9 = 73;
  v8 = L"Windows.Graphics.Internal.Printing.PrintScanBroker.PrintScanBrokerHandler";
  if ( (unsigned __int8)lambda_a3880ac6e2091b289c243255c71de565_::operator()(v2, a1, &v8) )
  {
    v4 = winrt::make<winrt::Windows::Graphics::Internal::Printing::PrintScanBroker::factory_implementation::PrintScanBrokerHandler,>(&v10);
LABEL_3:
    v5 = *v4;
    *v4 = 0;
    winrt::Windows::Internal::StateRepository::IApplication::~IApplication((winrt::Windows::Internal::StateRepository::IApplication *)&v10);
    return v5;
  }
  v9 = 80;
  v8 = L"Windows.Graphics.Internal.Printing.PrintScanBroker.VirtualPrinterInstallerBroker";
  if ( (unsigned __int8)lambda_a3880ac6e2091b289c243255c71de565_::operator()(v3, a1, &v8) )
  {
    v4 = winrt::make<winrt::Windows::Graphics::Internal::Printing::PrintScanBroker::factory_implementation::VirtualPrinterInstallerBroker,>(&v10);
    goto LABEL_3;
  }
  v9 = 77;
  v8 = L"Windows.Graphics.Internal.Printing.PrintScanBroker.IppQueuePropertyBagHandler";
  if ( (unsigned __int8)lambda_a3880ac6e2091b289c243255c71de565_::operator()(v7, a1, &v8) )
  {
    v4 = winrt::make<winrt::Windows::Graphics::Internal::Printing::PrintScanBroker::factory_implementation::IppQueuePropertyBagHandler,>(&v10);
    goto LABEL_3;
  }
  return 0;
}

```

## disassembly

```asm
0x180011a74  mov     [rsp-8+arg_8], rbx
0x180011a79  push    rbp
0x180011a7a  mov     rbp, rsp
0x180011a7d  sub     rsp, 30h
0x180011a81  mov     r8, [rcx]
0x180011a84  lea     rdx, aWinrtGetActiva_0; "winrt_get_activation_factory called for"...
0x180011a8b  mov     rbx, rcx
0x180011a8e  lea     rcx, aWinrtGetActiva; "winrt_get_activation_factory"
0x180011a95  call    ?WriteDbgTraceInfo@PrintScanBrokerTelemetry@@SAXPEADPEAGZZ; PrintScanBrokerTelemetry::WriteDbgTraceInfo(char *,ushort *,...)
0x180011a9a  lea     rax, aWindowsGraphic_0; "Windows.Graphics.Internal.Printing.Prin"...
0x180011aa1  mov     [rbp+var_8], 49h ; 'I'
0x180011aa9  lea     r8, [rbp+var_10]
0x180011aad  mov     [rbp+var_10], rax
0x180011ab1  mov     rdx, rbx
0x180011ab4  call    _lambda_a3880ac6e2091b289c243255c71de565___operator__
0x180011ab9  test    al, al
0x180011abb  jz      short loc_180011ADE
0x180011abd  lea     rcx, [rbp+arg_0]
0x180011ac1  call    ??$make@UPrintScanBrokerHandler@factory_implementation@PrintScanBroker@Printing@Internal@Graphics@Windows@winrt@@$$V@winrt@@YA?A_PXZ
0x180011ac6  mov     rbx, [rax]
0x180011ac9  lea     rcx, [rbp+arg_0]; this
0x180011acd  mov     qword ptr [rax], 0
0x180011ad4  call    ??1IApplication@StateRepository@Internal@Windows@winrt@@QEAA@XZ; winrt::Windows::Internal::StateRepository::IApplication::~IApplication(void)
0x180011ad9  mov     rax, rbx
0x180011adc  jmp     short loc_180011B3C
0x180011ade  lea     rax, aWindowsGraphic; "Windows.Graphics.Internal.Printing.Prin"...
0x180011ae5  mov     [rbp+var_8], 50h ; 'P'
0x180011aed  lea     r8, [rbp+var_10]
0x180011af1  mov     [rbp+var_10], rax
0x180011af5  mov     rdx, rbx
0x180011af8  call    _lambda_a3880ac6e2091b289c243255c71de565___operator__
0x180011afd  test    al, al
0x180011aff  jz      short loc_180011B0C
0x180011b01  lea     rcx, [rbp+arg_0]
0x180011b05  call    ??$make@UVirtualPrinterInstallerBroker@factory_implementation@PrintScanBroker@Printing@Internal@Graphics@Windows@winrt@@$$V@winrt@@YA?A_PXZ
0x180011b0a  jmp     short loc_180011AC6
0x180011b0c  lea     rax, aWindowsGraphic_1; "Windows.Graphics.Internal.Printing.Prin"...
0x180011b13  mov     [rbp+var_8], 4Dh ; 'M'
0x180011b1b  lea     r8, [rbp+var_10]
0x180011b1f  mov     [rbp+var_10], rax
0x180011b23  mov     rdx, rbx
0x180011b26  call    _lambda_a3880ac6e2091b289c243255c71de565___operator__
0x180011b2b  test    al, al
0x180011b2d  jz      short loc_180011B3A
0x180011b2f  lea     rcx, [rbp+arg_0]
0x180011b33  call    ??$make@UIppQueuePropertyBagHandler@factory_implementation@PrintScanBroker@Printing@Internal@Graphics@Windows@winrt@@$$V@winrt@@YA?A_PXZ
0x180011b38  jmp     short loc_180011AC6
0x180011b3a  xor     eax, eax
0x180011b3c  mov     rbx, [rsp+30h+arg_8]
0x180011b41  add     rsp, 30h
0x180011b45  pop     rbp
0x180011b46  retn
```
