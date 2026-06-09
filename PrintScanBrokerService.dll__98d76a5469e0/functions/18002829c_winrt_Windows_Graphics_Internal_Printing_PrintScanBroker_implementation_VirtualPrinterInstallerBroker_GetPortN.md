# winrt::Windows::Graphics::Internal::Printing::PrintScanBroker::implementation::VirtualPrinterInstallerBroker::GetPortNameFromPrinter(winrt::hstring const &,winrt::hstring const &)

- ea: `0x18002829c`
- end: `0x180028452`
- name: `?GetPortNameFromPrinter@VirtualPrinterInstallerBroker@implementation@PrintScanBroker@Printing@Internal@Graphics@Windows@winrt@@CA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEBUhstring@8@0@Z`
- size: `438`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x18002a148`

## callees

- `0x180003254`
- `0x1800080f8`
- `0x18000f760`
- `0x18000fa2c`
- `0x180012498`
- `0x1800182ec`
- `0x18001cfb4`
- `0x18002829c`
- `0x18002f194`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180028358`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180028358`
- `ext-ms-win-printer-winspool-core-l1-1-0!GetPrinterW` at `0x180028346`
- `ext-ms-win-printer-winspool-core-l1-1-0!GetPrinterW` at `0x1800283ad`
- `ext-ms-win-printer-winspool-core-l1-1-0!GetPrinterW` at `0x180028346`
- `ext-ms-win-printer-winspool-core-l1-1-0!GetPrinterW` at `0x1800283ad`
- `ext-ms-win-printer-winspool-core-l1-1-0!OpenPrinterW` at `0x1800282f4`
- `ext-ms-win-printer-winspool-core-l1-1-0!OpenPrinterW` at `0x1800282f4`

## string_xrefs

- `0x1800283fe`: `onecoreuap\printscan\print\printscanbroker\class\virtualprinterinstallerbroker.cpp`
- `0x180028410`: `onecoreuap\printscan\print\printscanbroker\class\virtualprinterinstallerbroker.cpp`
- `0x180028428`: `onecoreuap\printscan\print\printscanbroker\class\virtualprinterinstallerbroker.cpp`
- `0x18002843d`: `onecoreuap\printscan\print\printscanbroker\class\virtualprinterinstallerbroker.cpp`
- `0x1800282c3`: `winrt::Windows::Graphics::Internal::Printing::PrintScanBroker::implementation::VirtualPrinterInstallerBroker::GetPortNameFromPrinter`
- `0x180028318`: `winrt::Windows::Graphics::Internal::Printing::PrintScanBroker::implementation::VirtualPrinterInstallerBroker::GetPortNameFromPrinter`
- `0x180028388`: `winrt::Windows::Graphics::Internal::Printing::PrintScanBroker::implementation::VirtualPrinterInstallerBroker::GetPortNameFromPrinter`
- `0x1800283c6`: `winrt::Windows::Graphics::Internal::Printing::PrintScanBroker::implementation::VirtualPrinterInstallerBroker::GetPortNameFromPrinter`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall winrt::Windows::Graphics::Internal::Printing::PrintScanBroker::implementation::VirtualPrinterInstallerBroker::GetPortNameFromPrinter(
        __int64 a1,
        winrt::hstring *a2,
        winrt::hstring *a3)
{
  const unsigned __int16 *v6; // rax
  WCHAR *v7; // rax
  const char *v8; // r9
  const unsigned __int16 *v9; // rax
  const char *v10; // r9
  __int64 *v11; // rbx
  const unsigned __int16 *v12; // rax
  const char *v13; // r9
  unsigned __int64 v14; // rdx
  int pcbNeeded; // [rsp+20h] [rbp-48h]
  HANDLE phPrinter; // [rsp+38h] [rbp-30h] BYREF
  __int64 *v18; // [rsp+40h] [rbp-28h] BYREF
  struct _PRINTER_DEFAULTSW pDefault; // [rsp+48h] [rbp-20h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+88h] [rbp+20h]
  DWORD cbBuf; // [rsp+A8h] [rbp+40h] BYREF

  v6 = winrt::hstring::c_str(a2);
  PrintScanBrokerTelemetry::WriteDbgTraceInfo(
    "winrt::Windows::Graphics::Internal::Printing::PrintScanBroker::implementation::VirtualPrinterInstallerBroker::GetPor"
    "tNameFromPrinter",
    L"GetPortNameFromPrinter for %ws",
    v6);
  memset(&pDefault, 0, sizeof(pDefault));
  phPrinter = 0;
  v7 = (WCHAR *)winrt::hstring::c_str(a2);
  if ( !OpenPrinterW(v7, &phPrinter, &pDefault) )
    wil::details::in1diag3::_Throw_GetLastError(
      retaddr,
      (void *)0x19C,
      (unsigned int)"onecoreuap\\printscan\\print\\printscanbroker\\class\\virtualprinterinstallerbroker.cpp",
      v8);
  v9 = winrt::hstring::c_str(a3);
  PrintScanBrokerTelemetry::WriteDbgTraceInfo(
    "winrt::Windows::Graphics::Internal::Printing::PrintScanBroker::implementation::VirtualPrinterInstallerBroker::GetPor"
    "tNameFromPrinter",
    L"GetPrinter size probe for %ws",
    v9);
  cbBuf = 0;
  if ( GetPrinterW(phPrinter, 2u, 0, 0, &cbBuf) )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x1A1,
      (unsigned int)"onecoreuap\\printscan\\print\\printscanbroker\\class\\virtualprinterinstallerbroker.cpp",
      (const char *)0x8000FFFFLL,
      pcbNeeded);
  if ( GetLastError() != 122 )
    wil::details::in1diag3::_Throw_GetLastError(
      retaddr,
      (void *)0x1A2,
      (unsigned int)"onecoreuap\\printscan\\print\\printscanbroker\\class\\virtualprinterinstallerbroker.cpp",
      v10);
  v11 = (__int64 *)operator new[](cbBuf);
  v18 = v11;
  v12 = winrt::hstring::c_str(a3);
  PrintScanBrokerTelemetry::WriteDbgTraceInfo(
    "winrt::Windows::Graphics::Internal::Printing::PrintScanBroker::implementation::VirtualPrinterInstallerBroker::GetPor"
    "tNameFromPrinter",
    L"GetPrinter for %ws",
    v12);
  if ( !GetPrinterW(phPrinter, 2u, (LPBYTE)v11, cbBuf, &cbBuf) )
    wil::details::in1diag3::_Throw_GetLastError(
      retaddr,
      (void *)0x1A8,
      (unsigned int)"onecoreuap\\printscan\\print\\printscanbroker\\class\\virtualprinterinstallerbroker.cpp",
      v13);
  PrintScanBrokerTelemetry::WriteDbgTraceInfo(
    "winrt::Windows::Graphics::Internal::Printing::PrintScanBroker::implementation::VirtualPrinterInstallerBroker::GetPor"
    "tNameFromPrinter",
    L"Port name %ws",
    v11[3]);
  std::wstring::wstring(a1, v11[3]);
  std::unique_ptr<unsigned short [0]>::~unique_ptr<unsigned short [0]>((void **)&v18, v14);
  wil::details::unique_storage<wil::details::resource_policy<void *,int (*)(void *),&int ClosePrinter(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,int (*)(void *),&int ClosePrinter(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&phPrinter);
  return a1;
}

```

## disassembly

```asm
0x18002829c  push    rbp
0x18002829e  push    rbx
0x18002829f  push    rsi
0x1800282a0  push    rdi
0x1800282a1  mov     rbp, rsp
0x1800282a4  sub     rsp, 68h
0x1800282a8  mov     rsi, r8
0x1800282ab  mov     rbx, rdx
0x1800282ae  mov     rdi, rcx
0x1800282b1  mov     rcx, rdx; this
0x1800282b4  call    ?c_str@hstring@winrt@@QEBAPEBGXZ; winrt::hstring::c_str(void)
0x1800282b9  mov     r8, rax
0x1800282bc  lea     rdx, aGetportnamefro; "GetPortNameFromPrinter for %ws"
0x1800282c3  lea     rcx, aWinrtWindowsGr; "winrt::Windows::Graphics::Internal::Pri"...
0x1800282ca  call    ?WriteDbgTraceInfo@PrintScanBrokerTelemetry@@SAXPEADPEAGZZ; PrintScanBrokerTelemetry::WriteDbgTraceInfo(char *,ushort *,...)
0x1800282cf  nop
0x1800282d0  xorps   xmm0, xmm0
0x1800282d3  xor     eax, eax
0x1800282d5  movups  xmmword ptr [rbp+pDefault.pDatatype], xmm0
0x1800282d9  mov     qword ptr [rbp+pDefault.DesiredAccess], rax
0x1800282dd  mov     [rbp+phPrinter], rax
0x1800282e1  mov     rcx, rbx; this
0x1800282e4  call    ?c_str@hstring@winrt@@QEBAPEBGXZ; winrt::hstring::c_str(void)
0x1800282e9  lea     r8, [rbp+pDefault]; pDefault
0x1800282ed  lea     rdx, [rbp+phPrinter]; phPrinter
0x1800282f1  mov     rcx, rax; pPrinterName
0x1800282f4  call    cs:__imp_OpenPrinterW
0x1800282fa  mov     rcx, [rbp+20h]; this
0x1800282fe  test    eax, eax
0x180028300  jz      loc_180028410
0x180028306  mov     rcx, rsi; this
0x180028309  call    ?c_str@hstring@winrt@@QEBAPEBGXZ; winrt::hstring::c_str(void)
0x18002830e  mov     r8, rax
0x180028311  lea     rdx, aGetprinterSize; "GetPrinter size probe for %ws"
0x180028318  lea     rcx, aWinrtWindowsGr; "winrt::Windows::Graphics::Internal::Pri"...
0x18002831f  call    ?WriteDbgTraceInfo@PrintScanBrokerTelemetry@@SAXPEADPEAGZZ; PrintScanBrokerTelemetry::WriteDbgTraceInfo(char *,ushort *,...)
0x180028324  mov     [rbp+cbBuf], 0
0x18002832b  mov     rbx, [rbp+20h]
0x18002832f  lea     rax, [rbp+cbBuf]
0x180028333  mov     qword ptr [rsp+68h+pcbNeeded], rax; int
0x180028338  xor     r9d, r9d; cbBuf
0x18002833b  xor     r8d, r8d; pPrinter
0x18002833e  lea     edx, [r9+2]; Level
0x180028342  mov     rcx, [rbp+phPrinter]; hPrinter
0x180028346  call    cs:__imp_GetPrinterW
0x18002834c  test    eax, eax
0x18002834e  jnz     loc_180028422
0x180028354  mov     rbx, [rbp+20h]
0x180028358  call    cs:__imp_GetLastError
0x18002835e  cmp     eax, 7Ah ; 'z'
0x180028361  jnz     loc_18002843D
0x180028367  mov     ecx, [rbp+cbBuf]; unsigned __int64
0x18002836a  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x18002836f  mov     rbx, rax
0x180028372  mov     [rbp+var_28], rax
0x180028376  mov     rcx, rsi; this
0x180028379  call    ?c_str@hstring@winrt@@QEBAPEBGXZ; winrt::hstring::c_str(void)
0x18002837e  mov     r8, rax
0x180028381  lea     rdx, aGetprinterForW; "GetPrinter for %ws"
0x180028388  lea     rcx, aWinrtWindowsGr; "winrt::Windows::Graphics::Internal::Pri"...
0x18002838f  call    ?WriteDbgTraceInfo@PrintScanBrokerTelemetry@@SAXPEADPEAGZZ; PrintScanBrokerTelemetry::WriteDbgTraceInfo(char *,ushort *,...)
0x180028394  lea     rax, [rbp+cbBuf]
0x180028398  mov     qword ptr [rsp+68h+pcbNeeded], rax; pcbNeeded
0x18002839d  mov     r9d, [rbp+cbBuf]; cbBuf
0x1800283a1  mov     r8, rbx; pPrinter
0x1800283a4  mov     edx, 2; Level
0x1800283a9  mov     rcx, [rbp+phPrinter]; hPrinter
0x1800283ad  call    cs:__imp_GetPrinterW
0x1800283b3  mov     rcx, [rbp+20h]; this
0x1800283b7  test    eax, eax
0x1800283b9  jz      short loc_1800283FE
0x1800283bb  mov     r8, [rbx+18h]
0x1800283bf  lea     rdx, aPortNameWs; "Port name %ws"
0x1800283c6  lea     rcx, aWinrtWindowsGr; "winrt::Windows::Graphics::Internal::Pri"...
0x1800283cd  call    ?WriteDbgTraceInfo@PrintScanBrokerTelemetry@@SAXPEADPEAGZZ; PrintScanBrokerTelemetry::WriteDbgTraceInfo(char *,ushort *,...)
0x1800283d2  mov     rdx, [rbx+18h]
0x1800283d6  mov     rcx, rdi
0x1800283d9  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x1800283de  nop
0x1800283df  lea     rcx, [rbp+var_28]
0x1800283e3  call    ??1?$unique_ptr@$$BY0A@GU?$default_delete@$$BY0A@G@std@@@std@@QEAA@XZ; std::unique_ptr<ushort [0]>::~unique_ptr<ushort [0]>(void)
0x1800283e8  nop
0x1800283e9  lea     rcx, [rbp+phPrinter]
0x1800283ed  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AHPEAX@Z$1?ClosePrinter@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,int (*)(void *),&ClosePrinter(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,int (*)(void *),&ClosePrinter(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x1800283f2  mov     rax, rdi
0x1800283f5  add     rsp, 68h
0x1800283f9  pop     rdi
0x1800283fa  pop     rsi
0x1800283fb  pop     rbx
0x1800283fc  pop     rbp
0x1800283fd  retn
0x1800283fe  lea     r8, aOnecoreuapPrin_7; "onecoreuap\\printscan\\print\\printscan"...
0x180028405  mov     edx, 1A8h; void *
0x18002840a  call    ?_Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_GetLastError(void *,uint,char const *)
0x180028410  lea     r8, aOnecoreuapPrin_7; "onecoreuap\\printscan\\print\\printscan"...
0x180028417  mov     edx, 19Ch; void *
0x18002841c  call    ?_Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_GetLastError(void *,uint,char const *)
0x180028422  mov     r9d, 8000FFFFh; char *
0x180028428  lea     r8, aOnecoreuapPrin_7; "onecoreuap\\printscan\\print\\printscan"...
0x18002842f  mov     edx, 1A1h; void *
0x180028434  mov     rcx, rbx; this
0x180028437  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18002843d  lea     r8, aOnecoreuapPrin_7; "onecoreuap\\printscan\\print\\printscan"...
0x180028444  mov     edx, 1A2h; void *
0x180028449  mov     rcx, rbx; this
0x18002844c  call    ?_Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_GetLastError(void *,uint,char const *)
```
