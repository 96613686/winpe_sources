# winrt::Windows::Graphics::Internal::Printing::PrintSupport::implementation::PrintSupportVirtualPrinterSession::PrintSupportVirtualPrinterSession(winrt::hstring)

- ea: `0x180041d24`
- end: `0x180041f77`
- name: `??0PrintSupportVirtualPrinterSession@implementation@PrintSupport@Printing@Internal@Graphics@Windows@winrt@@QEAA@Uhstring@7@@Z`
- size: `595`
- prototype: `_QWORD __high(struct winrt::hstring)`
- caller_count: `1`
- callee_count: `13`
- tags: `registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x180024efc`

## callees

- `0x180001314`
- `0x180003cd0`
- `0x18000874c`
- `0x180009718`
- `0x180012b10`
- `0x1800147dc`
- `0x180015920`
- `0x180029208`
- `0x180030d94`
- `0x180038c04`
- `0x18003905c`
- `0x1800394bc`
- `0x180041d24`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateGuid` at `0x180041ed2`
- `api-ms-win-core-com-l1-1-0!CoCreateGuid` at `0x180041ed2`

## pseudocode

```c
// Hidden C++ exception states: #wind=22
__int64 __fastcall winrt::Windows::Graphics::Internal::Printing::PrintSupport::implementation::PrintSupportVirtualPrinterSession::PrintSupportVirtualPrinterSession(
        __int64 a1,
        const struct winrt::hstring *a2)
{
  _QWORD *v4; // rax
  __int64 v5; // rax
  __int64 v6; // rdx
  const struct winrt::hstring *v8; // [rsp+68h] [rbp+48h] BYREF
  __int64 v9; // [rsp+70h] [rbp+50h] BYREF

  v8 = a2;
  *(_QWORD *)(a1 + 16) = &winrt::impl::produce<winrt::Windows::Graphics::Internal::Printing::PrintSupport::implementation::PrintSupportVirtualPrinterSession,winrt::Windows::Graphics::Internal::Printing::PrintSupport::IPrintSupportWorkflowSessionCommon>::`vftable';
  winrt::impl::module_lock_updater<1>::module_lock_updater<1>(a1 + 8);
  *(_QWORD *)(a1 + 8) = 1;
  *(_QWORD *)a1 = &winrt::Windows::Graphics::Internal::Printing::PrintSupport::implementation::PrintSupportVirtualPrinterSession_base<winrt::Windows::Graphics::Internal::Printing::PrintSupport::implementation::PrintSupportVirtualPrinterSession,>::`vftable';
  winrt::hstring::hstring((winrt::hstring *)&v9, L"Windows.PrintSupportVirtualPrinterWorkflow");
  PrintSupportSessionCommon::PrintSupportSessionCommon(
    (PrintSupportSessionCommon *)(a1 + 24),
    a2,
    (const struct winrt::hstring *)&v9,
    733);
  winrt::handle_type<winrt::impl::hstring_traits>::close(&v9);
  *(_QWORD *)a1 = &winrt::Windows::Graphics::Internal::Printing::PrintSupport::implementation::PrintSupportVirtualPrinterSession::`vftable'{for `winrt::Windows::Graphics::Internal::Printing::PrintSupport::implementation::PrintSupportVirtualPrinterSession_base<winrt::Windows::Graphics::Internal::Printing::PrintSupport::implementation::PrintSupportVirtualPrinterSession,>'};
  *(_QWORD *)(a1 + 24) = &winrt::impl::heap_implements<winrt::Windows::Graphics::Internal::Printing::PrintSupport::implementation::PrintSupportVirtualPrinterSession>::`vftable'{for `PrintSupportSessionCommon'};
  *(_QWORD *)(a1 + 320) = 0;
  *(_BYTE *)(a1 + 328) = 0;
  *(_QWORD *)(a1 + 336) = 0;
  *(_QWORD *)(a1 + 344) = 0;
  *(_QWORD *)(a1 + 352) = 0;
  *(_OWORD *)(a1 + 360) = 0;
  LODWORD(v9) = 1;
  ____0W4EventOptions_wil____V___unique_any_t_V__event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_exception_policy_3__wil___wil__QEAA___QEAW4EventOptions_1__Z(
    a1 + 376,
    &v9);
  LODWORD(v9) = 1;
  ____0W4EventOptions_wil____V___unique_any_t_V__event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_exception_policy_3__wil___wil__QEAA___QEAW4EventOptions_1__Z(
    a1 + 384,
    &v9);
  *(_QWORD *)(a1 + 392) = 0;
  *(_QWORD *)(a1 + 400) = 0;
  *(_QWORD *)(a1 + 408) = 0;
  v4 = operator new(0x20u);
  *v4 = v4;
  v4[1] = v4;
  v4[2] = v4;
  *((_WORD *)v4 + 12) = 257;
  *(_QWORD *)(a1 + 400) = v4;
  LODWORD(v9) = 1;
  ____0W4EventOptions_wil____V___unique_any_t_V__event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_exception_policy_3__wil___wil__QEAA___QEAW4EventOptions_1__Z(
    a1 + 416,
    &v9);
  LODWORD(v9) = 1;
  ____0W4EventOptions_wil____V___unique_any_t_V__event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_exception_policy_3__wil___wil__QEAA___QEAW4EventOptions_1__Z(
    a1 + 424,
    &v9);
  LODWORD(v9) = 1;
  ____0W4EventOptions_wil____V___unique_any_t_V__event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_exception_policy_3__wil___wil__QEAA___QEAW4EventOptions_1__Z(
    a1 + 432,
    &v9);
  *(_QWORD *)(a1 + 440) = -1;
  *(_QWORD *)(a1 + 448) = -1;
  *(_QWORD *)(a1 + 456) = -1;
  *(_QWORD *)(a1 + 464) = 0;
  *(_QWORD *)(a1 + 472) = 0;
  *(_QWORD *)(a1 + 480) = 0;
  *(_WORD *)(a1 + 488) = 0;
  *(_QWORD *)(a1 + 496) = 0;
  *(_BYTE *)(a1 + 504) = 0;
  *(_QWORD *)(a1 + 512) = 0;
  if ( CoCreateGuid((GUID *)(a1 + 360)) && (unsigned int)dword_180083000 > 5 )
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(
      (__int64)&dword_180083000,
      (__int64)word_18007511A,
      0);
  winrt::impl::root_implements<winrt::Windows::Graphics::Internal::Printing::PrintSupport::implementation::PrintSupportSession,winrt::Windows::Graphics::Internal::Printing::PrintSupport::PrintSupportSession>::get_weak<winrt::Windows::Graphics::Internal::Printing::PrintSupport::implementation::PrintSupportSession>(
    a1,
    &v9);
  v8 = (const struct winrt::hstring *)operator new(0x58u);
  v5 = winrt::Windows::Graphics::Internal::Printing::PrintSupport::implementation::PrintSupportVirtualPrinterSession::VirtualPrinterSessionStateHandler::VirtualPrinterSessionStateHandler(
         v8,
         &v9,
         a1 + 360);
  v8 = 0;
  v6 = *(_QWORD *)(a1 + 320);
  *(_QWORD *)(a1 + 320) = v5;
  if ( v6 )
    std::default_delete<winrt::Windows::Graphics::Internal::Printing::PrintSupport::implementation::PrintSupportSession::SessionStateHandler>::operator()();
  std::unique_ptr<winrt::Windows::Graphics::Internal::Printing::PrintSupport::implementation::PrintSupportSession::SessionStateHandler>::~unique_ptr<winrt::Windows::Graphics::Internal::Printing::PrintSupport::implementation::PrintSupportSession::SessionStateHandler>(&v8);
  if ( v9 )
    winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v9);
  winrt::handle_type<winrt::impl::hstring_traits>::close(a2);
  return a1;
}

```

## disassembly

```asm
0x180041d24  mov     [rsp-38h+arg_8], rdx
0x180041d29  mov     [rsp-38h+arg_0], rcx
0x180041d2e  push    rbp
0x180041d2f  push    rbx
0x180041d30  push    rsi
0x180041d31  push    rdi
0x180041d32  push    r12
0x180041d34  push    r14
0x180041d36  push    r15
0x180041d38  mov     rbp, rsp
0x180041d3b  sub     rsp, 20h
0x180041d3f  mov     rsi, rdx
0x180041d42  mov     rdi, rcx
0x180041d45  xor     r12d, r12d
0x180041d48  lea     rax, ??_7?$produce@UPrintSupportVirtualPrinterSession@implementation@PrintSupport@Printing@Internal@Graphics@Windows@winrt@@UIPrintSupportWorkflowSessionCommon@345678@@impl@winrt@@6B@; const winrt::impl::produce<winrt::Windows::Graphics::Internal::Printing::PrintSupport::implementation::PrintSupportVirtualPrinterSession,winrt::Windows::Graphics::Internal::Printing::PrintSupport::IPrintSupportWorkflowSessionCommon>::`vftable'
0x180041d4f  mov     [rcx+10h], rax
0x180041d53  add     rcx, 8
0x180041d57  call    ??0?$module_lock_updater@$00@impl@winrt@@QEAA@XZ; winrt::impl::module_lock_updater<1>::module_lock_updater<1>(void)
0x180041d5c  lea     r15d, [r12+1]
0x180041d61  mov     [rdi+8], r15
0x180041d65  lea     rax, ??_7?$PrintSupportVirtualPrinterSession_base@UPrintSupportVirtualPrinterSession@implementation@PrintSupport@Printing@Internal@Graphics@Windows@winrt@@$$V@implementation@PrintSupport@Printing@Internal@Graphics@Windows@winrt@@6B@; const winrt::Windows::Graphics::Internal::Printing::PrintSupport::implementation::PrintSupportVirtualPrinterSession_base<winrt::Windows::Graphics::Internal::Printing::PrintSupport::implementation::PrintSupportVirtualPrinterSession,>::`vftable'
0x180041d6c  mov     [rdi], rax
0x180041d6f  lea     rdx, aWindowsPrintsu_1; "Windows.PrintSupportVirtualPrinterWorkf"...
0x180041d76  lea     rcx, [rbp+arg_10]; this
0x180041d7a  call    ??0hstring@winrt@@QEAA@PEBG@Z; winrt::hstring::hstring(ushort const *)
0x180041d7f  nop
0x180041d80  mov     r9d, 2DDh; unsigned int
0x180041d86  lea     r8, [rbp+arg_10]; struct winrt::hstring *
0x180041d8a  mov     rdx, rsi; struct winrt::hstring *
0x180041d8d  lea     rcx, [rdi+18h]; this
0x180041d91  call    ??0PrintSupportSessionCommon@@QEAA@AEBUhstring@winrt@@0K@Z; PrintSupportSessionCommon::PrintSupportSessionCommon(winrt::hstring const &,winrt::hstring const &,ulong)
0x180041d96  nop
0x180041d97  lea     rcx, [rbp+arg_10]
0x180041d9b  call    ?close@?$handle_type@Uhstring_traits@impl@winrt@@@winrt@@QEAAXXZ; winrt::handle_type<winrt::impl::hstring_traits>::close(void)
0x180041da0  lea     rax, ??_7PrintSupportVirtualPrinterSession@implementation@PrintSupport@Printing@Internal@Graphics@Windows@winrt@@6B?$PrintSupportVirtualPrinterSession_base@UPrintSupportVirtualPrinterSession@implementation@PrintSupport@Printing@Internal@Graphics@Windows@winrt@@$$V@1234567@@; const winrt::Windows::Graphics::Internal::Printing::PrintSupport::implementation::PrintSupportVirtualPrinterSession::`vftable'{for `winrt::Windows::Graphics::Internal::Printing::PrintSupport::implementation::PrintSupportVirtualPrinterSession_base<winrt::Windows::Graphics::Internal::Printing::PrintSupport::implementation::PrintSupportVirtualPrinterSession,>'}
0x180041da7  mov     [rdi], rax
0x180041daa  lea     rax, ??_7?$heap_implements@UPrintSupportVirtualPrinterSession@implementation@PrintSupport@Printing@Internal@Graphics@Windows@winrt@@@impl@winrt@@6BPrintSupportSessionCommon@@@; const winrt::impl::heap_implements<winrt::Windows::Graphics::Internal::Printing::PrintSupport::implementation::PrintSupportVirtualPrinterSession>::`vftable'{for `PrintSupportSessionCommon'}
0x180041db1  mov     [rdi+18h], rax
0x180041db5  mov     [rdi+140h], r12
0x180041dbc  mov     [rdi+148h], r12b
0x180041dc3  mov     [rdi+150h], r12
0x180041dca  mov     [rdi+158h], r12
0x180041dd1  mov     [rdi+160h], r12
0x180041dd8  lea     r14, [rdi+168h]
0x180041ddf  xorps   xmm0, xmm0
0x180041de2  movups  xmmword ptr [r14], xmm0
0x180041de6  mov     dword ptr [rbp+arg_10], r15d
0x180041dea  lea     rcx, [rdi+178h]
0x180041df1  lea     rdx, [rbp+arg_10]
0x180041df5  call    ??$?0W4EventOptions@wil@@$$V@?$unique_any_t@V?$event_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_exception_policy@3@@wil@@@wil@@QEAA@$$QEAW4EventOptions@1@@Z
0x180041dfa  nop
0x180041dfb  mov     dword ptr [rbp+arg_10], r15d
0x180041dff  lea     rcx, [rdi+180h]
0x180041e06  lea     rdx, [rbp+arg_10]
0x180041e0a  call    ??$?0W4EventOptions@wil@@$$V@?$unique_any_t@V?$event_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_exception_policy@3@@wil@@@wil@@QEAA@$$QEAW4EventOptions@1@@Z
0x180041e0f  nop
0x180041e10  mov     [rdi+188h], r12
0x180041e17  lea     rbx, [rdi+190h]
0x180041e1e  mov     [rbx], r12
0x180041e21  mov     [rbx+8], r12
0x180041e25  lea     ecx, [r12+20h]; Size
0x180041e2a  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180041e2f  mov     [rax], rax
0x180041e32  mov     [rax+8], rax
0x180041e36  mov     [rax+10h], rax
0x180041e3a  mov     word ptr [rax+18h], 101h
0x180041e40  mov     [rbx], rax
0x180041e43  mov     dword ptr [rbp+arg_10], r15d
0x180041e47  lea     rcx, [rdi+1A0h]
0x180041e4e  lea     rdx, [rbp+arg_10]
0x180041e52  call    ??$?0W4EventOptions@wil@@$$V@?$unique_any_t@V?$event_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_exception_policy@3@@wil@@@wil@@QEAA@$$QEAW4EventOptions@1@@Z
0x180041e57  nop
0x180041e58  mov     dword ptr [rbp+arg_10], r15d
0x180041e5c  lea     rcx, [rdi+1A8h]
0x180041e63  lea     rdx, [rbp+arg_10]
0x180041e67  call    ??$?0W4EventOptions@wil@@$$V@?$unique_any_t@V?$event_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_exception_policy@3@@wil@@@wil@@QEAA@$$QEAW4EventOptions@1@@Z
0x180041e6c  nop
0x180041e6d  mov     dword ptr [rbp+arg_10], r15d
0x180041e71  lea     rcx, [rdi+1B0h]
0x180041e78  lea     rdx, [rbp+arg_10]
0x180041e7c  call    ??$?0W4EventOptions@wil@@$$V@?$unique_any_t@V?$event_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_exception_policy@3@@wil@@@wil@@QEAA@$$QEAW4EventOptions@1@@Z
0x180041e81  nop
0x180041e82  or      rax, 0FFFFFFFFFFFFFFFFh
0x180041e86  mov     [rdi+1B8h], rax
0x180041e8d  mov     [rdi+1C0h], rax
0x180041e94  mov     [rdi+1C8h], rax
0x180041e9b  mov     [rdi+1D0h], r12
0x180041ea2  mov     [rdi+1D8h], r12
0x180041ea9  mov     [rdi+1E0h], r12
0x180041eb0  mov     [rdi+1E8h], r12w
0x180041eb8  xor     eax, eax
0x180041eba  mov     [rdi+1F0h], rax
0x180041ec1  mov     [rdi+1F8h], r12b
0x180041ec8  mov     [rdi+200h], r12
0x180041ecf  mov     rcx, r14; pguid
0x180041ed2  call    cs:__imp_CoCreateGuid
0x180041ed8  test    eax, eax
0x180041eda  jz      short loc_180041EFD
0x180041edc  mov     eax, cs:dword_180083000
0x180041ee2  cmp     eax, 5
0x180041ee5  jbe     short loc_180041EFD
0x180041ee7  xor     r8d, r8d
0x180041eea  lea     rdx, word_18007511A
0x180041ef1  lea     rcx, dword_180083000
0x180041ef8  call    ??$Write@$$V@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *)
0x180041efd  lea     rdx, [rbp+arg_10]
0x180041f01  mov     rcx, rdi
0x180041f04  call    ??$get_weak@UPrintSupportSession@implementation@PrintSupport@Printing@Internal@Graphics@Windows@winrt@@@?$root_implements@UPrintSupportSession@implementation@PrintSupport@Printing@Internal@Graphics@Windows@winrt@@U1345678@@impl@winrt@@IEAA?AU?$weak_ref@UPrintSupportSession@implementation@PrintSupport@Printing@Internal@Graphics@Windows@winrt@@@2@XZ; winrt::impl::root_implements<winrt::Windows::Graphics::Internal::Printing::PrintSupport::implementation::PrintSupportSession,winrt::Windows::Graphics::Internal::Printing::PrintSupport::PrintSupportSession>::get_weak<winrt::Windows::Graphics::Internal::Printing::PrintSupport::implementation::PrintSupportSession>(void)
0x180041f09  nop
0x180041f0a  mov     ecx, 58h ; 'X'; Size
0x180041f0f  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180041f14  mov     [rbp+arg_8], rax
0x180041f18  mov     r8, r14
0x180041f1b  lea     rdx, [rbp+arg_10]
0x180041f1f  mov     rcx, rax
0x180041f22  call    ??0VirtualPrinterSessionStateHandler@PrintSupportVirtualPrinterSession@implementation@PrintSupport@Printing@Internal@Graphics@Windows@winrt@@QEAA@AEBU?$weak_ref@UPrintSupportVirtualPrinterSession@implementation@PrintSupport@Printing@Internal@Graphics@Windows@winrt@@@8@AEBU_GUID@@@Z; winrt::Windows::Graphics::Internal::Printing::PrintSupport::implementation::PrintSupportVirtualPrinterSession::VirtualPrinterSessionStateHandler::VirtualPrinterSessionStateHandler(winrt::weak_ref<winrt::Windows::Graphics::Internal::Printing::PrintSupport::implementation::PrintSupportVirtualPrinterSession> const &,_GUID const &)
0x180041f27  mov     [rbp+arg_8], r12
0x180041f2b  mov     rdx, [rdi+140h]
0x180041f32  mov     [rdi+140h], rax
0x180041f39  test    rdx, rdx
0x180041f3c  jz      short loc_180041F43
0x180041f3e  call    ??R?$default_delete@USessionStateHandler@PrintSupportSession@implementation@PrintSupport@Printing@Internal@Graphics@Windows@winrt@@@std@@QEBAXPEAUSessionStateHandler@PrintSupportSession@implementation@PrintSupport@Printing@Internal@Graphics@Windows@winrt@@@Z; std::default_delete<winrt::Windows::Graphics::Internal::Printing::PrintSupport::implementation::PrintSupportSession::SessionStateHandler>::operator()(winrt::Windows::Graphics::Internal::Printing::PrintSupport::implementation::PrintSupportSession::SessionStateHandler *)
0x180041f43  lea     rcx, [rbp+arg_8]
0x180041f47  call    ??1?$unique_ptr@USessionStateHandler@PrintSupportSession@implementation@PrintSupport@Printing@Internal@Graphics@Windows@winrt@@U?$default_delete@USessionStateHandler@PrintSupportSession@implementation@PrintSupport@Printing@Internal@Graphics@Windows@winrt@@@std@@@std@@QEAA@XZ; std::unique_ptr<winrt::Windows::Graphics::Internal::Printing::PrintSupport::implementation::PrintSupportSession::SessionStateHandler>::~unique_ptr<winrt::Windows::Graphics::Internal::Printing::PrintSupport::implementation::PrintSupportSession::SessionStateHandler>(void)
0x180041f4c  nop
0x180041f4d  cmp     [rbp+arg_10], r12
0x180041f51  jz      short loc_180041F5D
0x180041f53  lea     rcx, [rbp+arg_10]
0x180041f57  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x180041f5c  nop
0x180041f5d  mov     rcx, rsi
0x180041f60  call    ?close@?$handle_type@Uhstring_traits@impl@winrt@@@winrt@@QEAAXXZ; winrt::handle_type<winrt::impl::hstring_traits>::close(void)
0x180041f65  mov     rax, rdi
0x180041f68  add     rsp, 20h
0x180041f6c  pop     r15
0x180041f6e  pop     r14
0x180041f70  pop     r12
0x180041f72  pop     rdi
0x180041f73  pop     rsi
0x180041f74  pop     rbx
0x180041f75  pop     rbp
0x180041f76  retn
```
