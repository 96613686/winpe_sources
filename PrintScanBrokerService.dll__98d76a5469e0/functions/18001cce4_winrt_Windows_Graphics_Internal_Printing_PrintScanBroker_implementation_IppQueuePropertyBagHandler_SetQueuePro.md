# winrt::Windows::Graphics::Internal::Printing::PrintScanBroker::implementation::IppQueuePropertyBagHandler::SetQueuePropertyBag(winrt::Windows::Foundation::Collections::IIterable<winrt::Windows::Foundation::Collections::IKeyValuePair<winrt::hstring,winrt::Windows::Foundation::IInspectable>> const &)

- ea: `0x18001cce4`
- end: `0x18001cdb7`
- name: `?SetQueuePropertyBag@IppQueuePropertyBagHandler@implementation@PrintScanBroker@Printing@Internal@Graphics@Windows@winrt@@QEAAXAEBU?$IIterable@U?$IKeyValuePair@Uhstring@winrt@@UIInspectable@Foundation@Windows@2@@Collections@Foundation@Windows@winrt@@@Collections@Foundation@78@@Z`
- size: `211`
- prototype: `int __fastcall(winrt::Windows::Graphics::Internal::Printing::PrintScanBroker::implementation::IppQueuePropertyBagHandler *this, __int64)`
- caller_count: `1`
- callee_count: `9`
- tags: `authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x18001ccb0`

## callees

- `0x18000fa2c`
- `0x18000fb60`
- `0x1800182ec`
- `0x18001cce4`
- `0x18001cf40`
- `0x18001f93c`
- `0x180022b44`
- `0x180022dac`
- `0x180022ef0`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x18001cda9`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x18001cda9`
- `ext-ms-win-printer-winspool-core-l1-1-0!OpenPrinterW` at `0x18001cd3e`
- `ext-ms-win-printer-winspool-core-l1-1-0!OpenPrinterW` at `0x18001cd3e`

## string_xrefs

- `0x18001cd5d`: `onecoreuap\printscan\print\printscanbroker\class\ippqueuepropertybaghandler.cpp`
- `0x18001cd4d`: `Failed to open printer`

## pseudocode

```c
int __fastcall winrt::Windows::Graphics::Internal::Printing::PrintScanBroker::implementation::IppQueuePropertyBagHandler::SetQueuePropertyBag(
        winrt::Windows::Graphics::Internal::Printing::PrintScanBroker::implementation::IppQueuePropertyBagHandler *this,
        __int64 a2)
{
  WCHAR *v4; // rax
  BOOL v5; // eax
  int result; // eax
  const char *v7; // [rsp+28h] [rbp-38h]
  struct _PRINTER_DEFAULTSW pDefault; // [rsp+40h] [rbp-20h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+78h] [rbp+18h]
  bool v10; // [rsp+80h] [rbp+20h]
  HANDLE phPrinter; // [rsp+90h] [rbp+30h] BYREF
  char v12; // [rsp+98h] [rbp+38h] BYREF

  v10 = winrt::Windows::Graphics::Internal::Printing::PrintScanBroker::implementation::IppQueuePropertyBagHandler::_ImpersonateUserIfNeeded(this);
  winrt::Windows::Graphics::Internal::Printing::PrintScanBroker::implementation::IppQueuePropertyBagHandler::_PropertyBagAccessCheck(this);
  *(_OWORD *)&pDefault.pDatatype = 0;
  *(_QWORD *)&pDefault.DesiredAccess = 983052;
  phPrinter = 0;
  v4 = (WCHAR *)winrt::hstring::c_str((winrt::Windows::Graphics::Internal::Printing::PrintScanBroker::implementation::IppQueuePropertyBagHandler *)((char *)this + 24));
  v5 = OpenPrinterW(v4, &phPrinter, &pDefault);
  wil::details::in1diag3::Throw_GetLastErrorIfFalseMsg(
    retaddr,
    (void *)0x7C,
    (unsigned int)"onecoreuap\\printscan\\print\\printscanbroker\\class\\ippqueuepropertybaghandler.cpp",
    (const char *)v5,
    (bool)"Failed to open printer",
    v7);
  winrt::Windows::Graphics::Internal::Printing::PrintScanBroker::implementation::IppQueuePropertyBagHandler::_ConvertKeyValuePairsToJson(
    this,
    &v12,
    a2);
  winrt::Windows::Graphics::Internal::Printing::PrintScanBroker::implementation::IppQueuePropertyBagHandler::_InternalSetQueuePropertyBag(
    this,
    phPrinter,
    (const struct winrt::hstring *)&v12);
  winrt::handle_type<winrt::impl::hstring_traits>::close(&v12);
  result = wil::details::unique_storage<wil::details::resource_policy<void *,int (*)(void *),&int ClosePrinter(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,int (*)(void *),&int ClosePrinter(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&phPrinter);
  if ( v10 )
    return RevertToSelf();
  return result;
}

```

## disassembly

```asm
0x18001cce4  push    rbp
0x18001cce6  push    rbx
0x18001cce7  push    rdi
0x18001cce8  mov     rbp, rsp
0x18001cceb  sub     rsp, 60h
0x18001ccef  mov     rbx, rdx
0x18001ccf2  mov     rdi, rcx
0x18001ccf5  call    ?_ImpersonateUserIfNeeded@IppQueuePropertyBagHandler@implementation@PrintScanBroker@Printing@Internal@Graphics@Windows@winrt@@AEAA_NXZ; winrt::Windows::Graphics::Internal::Printing::PrintScanBroker::implementation::IppQueuePropertyBagHandler::_ImpersonateUserIfNeeded(void)
0x18001ccfa  mov     [rbp+arg_0], al
0x18001ccfd  lea     rax, [rbp+arg_0]
0x18001cd01  mov     [rbp+var_30], rax
0x18001cd05  mov     [rbp+var_28], 1
0x18001cd09  mov     rcx, rdi; this
0x18001cd0c  call    ?_PropertyBagAccessCheck@IppQueuePropertyBagHandler@implementation@PrintScanBroker@Printing@Internal@Graphics@Windows@winrt@@AEAAXXZ; winrt::Windows::Graphics::Internal::Printing::PrintScanBroker::implementation::IppQueuePropertyBagHandler::_PropertyBagAccessCheck(void)
0x18001cd11  nop
0x18001cd12  xorps   xmm0, xmm0
0x18001cd15  movdqu  xmmword ptr [rbp+pDefault.pDatatype], xmm0
0x18001cd1a  mov     qword ptr [rbp+pDefault.DesiredAccess], 0F000Ch
0x18001cd22  mov     [rbp+phPrinter], 0
0x18001cd2a  lea     rcx, [rdi+18h]; this
0x18001cd2e  call    ?c_str@hstring@winrt@@QEBAPEBGXZ; winrt::hstring::c_str(void)
0x18001cd33  lea     r8, [rbp+pDefault]; pDefault
0x18001cd37  lea     rdx, [rbp+phPrinter]; phPrinter
0x18001cd3b  mov     rcx, rax; pPrinterName
0x18001cd3e  call    cs:__imp_OpenPrinterW
0x18001cd44  test    eax, eax
0x18001cd46  setnz   al
0x18001cd49  mov     rcx, [rbp+18h]; this
0x18001cd4d  lea     rdx, aFailedToOpenPr; "Failed to open printer"
0x18001cd54  mov     qword ptr [rsp+60h+var_40], rdx; bool
0x18001cd59  movzx   r9d, al; char *
0x18001cd5d  lea     r8, aOnecoreuapPrin; "onecoreuap\\printscan\\print\\printscan"...
0x18001cd64  mov     edx, 7Ch ; '|'; void *
0x18001cd69  call    ?Throw_GetLastErrorIfFalseMsg@in1diag3@details@wil@@YA_NPEAXIPEBD_N1ZZ; wil::details::in1diag3::Throw_GetLastErrorIfFalseMsg(void *,uint,char const *,bool,char const *,...)
0x18001cd6e  mov     r8, rbx
0x18001cd71  lea     rdx, [rbp+arg_18]
0x18001cd75  mov     rcx, rdi
0x18001cd78  call    ?_ConvertKeyValuePairsToJson@IppQueuePropertyBagHandler@implementation@PrintScanBroker@Printing@Internal@Graphics@Windows@winrt@@AEAA?AUhstring@8@AEBU?$IIterable@U?$IKeyValuePair@Uhstring@winrt@@UIInspectable@Foundation@Windows@2@@Collections@Foundation@Windows@winrt@@@Collections@Foundation@78@@Z; winrt::Windows::Graphics::Internal::Printing::PrintScanBroker::implementation::IppQueuePropertyBagHandler::_ConvertKeyValuePairsToJson(winrt::Windows::Foundation::Collections::IIterable<winrt::Windows::Foundation::Collections::IKeyValuePair<winrt::hstring,winrt::Windows::Foundation::IInspectable>> const &)
0x18001cd7d  nop
0x18001cd7e  lea     r8, [rbp+arg_18]; struct winrt::hstring *
0x18001cd82  mov     rdx, [rbp+phPrinter]; void *
0x18001cd86  mov     rcx, rdi; this
0x18001cd89  call    ?_InternalSetQueuePropertyBag@IppQueuePropertyBagHandler@implementation@PrintScanBroker@Printing@Internal@Graphics@Windows@winrt@@AEAAXPEAXAEBUhstring@8@@Z; winrt::Windows::Graphics::Internal::Printing::PrintScanBroker::implementation::IppQueuePropertyBagHandler::_InternalSetQueuePropertyBag(void *,winrt::hstring const &)
0x18001cd8e  nop
0x18001cd8f  lea     rcx, [rbp+arg_18]
0x18001cd93  call    ?close@?$handle_type@Uhstring_traits@impl@winrt@@@winrt@@QEAAXXZ; winrt::handle_type<winrt::impl::hstring_traits>::close(void)
0x18001cd98  nop
0x18001cd99  lea     rcx, [rbp+phPrinter]
0x18001cd9d  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AHPEAX@Z$1?ClosePrinter@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,int (*)(void *),&ClosePrinter(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,int (*)(void *),&ClosePrinter(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x18001cda2  nop
0x18001cda3  cmp     [rbp+arg_0], 0
0x18001cda7  jz      short loc_18001CDAF
0x18001cda9  call    cs:__imp_RevertToSelf
0x18001cdaf  add     rsp, 60h
0x18001cdb3  pop     rdi
0x18001cdb4  pop     rbx
0x18001cdb5  pop     rbp
0x18001cdb6  retn
```
