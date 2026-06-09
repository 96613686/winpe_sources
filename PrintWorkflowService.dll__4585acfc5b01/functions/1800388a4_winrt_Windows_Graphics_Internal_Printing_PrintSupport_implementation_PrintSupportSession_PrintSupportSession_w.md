# winrt::Windows::Graphics::Internal::Printing::PrintSupport::implementation::PrintSupportSession::PrintSupportSession(winrt::hstring)

- ea: `0x1800388a4`
- end: `0x180038bfd`
- name: `??0PrintSupportSession@implementation@PrintSupport@Printing@Internal@Graphics@Windows@winrt@@QEAA@Uhstring@7@@Z`
- size: `857`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `17`
- tags: `registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x180024850`

## callees

- `0x180001314`
- `0x180003cd0`
- `0x18000495c`
- `0x18000874c`
- `0x180009718`
- `0x1800097ec`
- `0x18000a6a0`
- `0x180012b10`
- `0x1800147dc`
- `0x180015920`
- `0x180029208`
- `0x180030d94`
- `0x1800388a4`
- `0x180038c04`
- `0x18003905c`
- `0x1800394bc`
- `0x18003efb4`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateGuid` at `0x180038b16`
- `api-ms-win-core-com-l1-1-0!CoCreateGuid` at `0x180038b16`

## pseudocode

```c
// Hidden C++ exception states: #wind=25
__int64 __fastcall winrt::Windows::Graphics::Internal::Printing::PrintSupport::implementation::PrintSupportSession::PrintSupportSession(
        __int64 a1,
        const struct winrt::hstring *a2)
{
  _QWORD *v4; // r13
  _QWORD *v5; // rax
  _QWORD *v6; // rsi
  __int64 v7; // rax
  __int64 v8; // rdx
  __int64 v9; // rax
  __int64 PrinterPdcAsync; // rax
  _QWORD *v12; // [rsp+80h] [rbp+58h] BYREF
  void *v13; // [rsp+88h] [rbp+60h] BYREF

  *(_QWORD *)(a1 + 16) = &winrt::impl::produce<winrt::Windows::Graphics::Internal::Printing::PrintSupport::implementation::PrintSupportSession,winrt::Windows::Graphics::Internal::Printing::PrintSupport::IPrintSupportWorkflowSessionCommon>::`vftable';
  winrt::impl::module_lock_updater<1>::module_lock_updater<1>(a1 + 8);
  *(_QWORD *)(a1 + 8) = 1;
  *(_QWORD *)a1 = &winrt::Windows::Graphics::Internal::Printing::PrintSupport::implementation::PrintSupportSession_base<winrt::Windows::Graphics::Internal::Printing::PrintSupport::implementation::PrintSupportSession,>::`vftable';
  winrt::hstring::hstring((winrt::hstring *)&v12, L"Windows.PrintSupportWorkflow");
  PrintSupportSessionCommon::PrintSupportSessionCommon(
    (PrintSupportSessionCommon *)(a1 + 24),
    a2,
    (const struct winrt::hstring *)&v12,
    731);
  winrt::handle_type<winrt::impl::hstring_traits>::close(&v12);
  *(_QWORD *)a1 = &winrt::impl::heap_implements<winrt::Windows::Graphics::Internal::Printing::PrintSupport::implementation::PrintSupportSession>::`vftable'{for `winrt::Windows::Graphics::Internal::Printing::PrintSupport::implementation::PrintSupportSession_base<winrt::Windows::Graphics::Internal::Printing::PrintSupport::implementation::PrintSupportSession,>'};
  *(_QWORD *)(a1 + 24) = &winrt::Windows::Graphics::Internal::Printing::PrintSupport::implementation::PrintSupportSession::`vftable'{for `PrintSupportSessionCommon'};
  *(_BYTE *)(a1 + 320) = 0;
  *(_QWORD *)(a1 + 328) = 0;
  *(_WORD *)(a1 + 336) = 256;
  LODWORD(v12) = 1;
  ____0W4EventOptions_wil____V___unique_any_t_V__event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_exception_policy_3__wil___wil__QEAA___QEAW4EventOptions_1__Z(
    a1 + 344,
    &v12);
  LODWORD(v12) = 1;
  ____0W4EventOptions_wil____V___unique_any_t_V__event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_exception_policy_3__wil___wil__QEAA___QEAW4EventOptions_1__Z(
    a1 + 352,
    &v12);
  LODWORD(v12) = 1;
  ____0W4EventOptions_wil____V___unique_any_t_V__event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_exception_policy_3__wil___wil__QEAA___QEAW4EventOptions_1__Z(
    a1 + 360,
    &v12);
  LODWORD(v12) = 1;
  ____0W4EventOptions_wil____V___unique_any_t_V__event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_exception_policy_3__wil___wil__QEAA___QEAW4EventOptions_1__Z(
    a1 + 368,
    &v12);
  LODWORD(v12) = 1;
  ____0W4EventOptions_wil____V___unique_any_t_V__event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_exception_policy_3__wil___wil__QEAA___QEAW4EventOptions_1__Z(
    a1 + 376,
    &v12);
  LODWORD(v12) = 1;
  ____0W4EventOptions_wil____V___unique_any_t_V__event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_exception_policy_3__wil___wil__QEAA___QEAW4EventOptions_1__Z(
    a1 + 384,
    &v12);
  LODWORD(v12) = 1;
  ____0W4EventOptions_wil____V___unique_any_t_V__event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_exception_policy_3__wil___wil__QEAA___QEAW4EventOptions_1__Z(
    a1 + 392,
    &v12);
  *(_QWORD *)(a1 + 400) = 0;
  v4 = (_QWORD *)(a1 + 408);
  *(_QWORD *)(a1 + 408) = 0;
  *(_QWORD *)(a1 + 416) = 0;
  *(_QWORD *)(a1 + 424) = 0;
  *(_QWORD *)(a1 + 432) = 0;
  *(_QWORD *)(a1 + 440) = 0;
  *(_QWORD *)(a1 + 448) = 0;
  *(_QWORD *)(a1 + 456) = 0;
  *(_QWORD *)(a1 + 464) = 0;
  *(_QWORD *)(a1 + 472) = 0;
  *(_QWORD *)(a1 + 480) = 0;
  *(_QWORD *)(a1 + 488) = 0;
  *(_QWORD *)(a1 + 496) = 0;
  v5 = operator new(0x20u);
  *v5 = v5;
  v5[1] = v5;
  v5[2] = v5;
  *((_WORD *)v5 + 12) = 257;
  *(_QWORD *)(a1 + 488) = v5;
  *(_OWORD *)(a1 + 504) = 0;
  *(_QWORD *)(a1 + 520) = 0;
  *(_QWORD *)(a1 + 528) = 0;
  *(_QWORD *)(a1 + 536) = 0;
  *(_QWORD *)(a1 + 544) = 0;
  *(_QWORD *)(a1 + 552) = 0;
  *(_QWORD *)(a1 + 560) = 0;
  *(_QWORD *)(a1 + 568) = 0;
  *(_WORD *)(a1 + 576) = 0;
  v6 = operator new(0x50u);
  memset_0(v6, 0, 0x50u);
  v6[2] = &winrt::impl::produce<winrt::Windows::Graphics::Internal::Printing::PrintSupport::implementation::PrintSupportJobHandler,winrt::Windows::Graphics::Internal::Printing::PrintSupport::IPrintSupportJobHandler>::`vftable';
  winrt::impl::module_lock_updater<1>::module_lock_updater<1>((__int64)(v6 + 1));
  v6[1] = 1;
  v6[3] = 0;
  v6[4] = 0;
  *((_DWORD *)v6 + 10) = 0;
  v6[6] = 0;
  *((_BYTE *)v6 + 56) = 0;
  *(_OWORD *)((char *)v6 + 60) = 0;
  *v6 = &winrt::impl::heap_implements<winrt::Windows::Graphics::Internal::Printing::PrintSupport::implementation::PrintSupportJobHandler>::`vftable';
  v12 = v6 + 2;
  winrt::Windows::Foundation::IUnknown::operator=(a1 + 408, &v12);
  winrt::Windows::Internal::ApplicationModel::WindowManagement::IWindow::~IWindow((winrt::Windows::Internal::ApplicationModel::WindowManagement::IWindow *)&v12);
  if ( CoCreateGuid((GUID *)(a1 + 504)) && (unsigned int)dword_180083000 > 5 )
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(
      (__int64)&dword_180083000,
      (__int64)byte_1800747FB,
      0);
  winrt::impl::root_implements<winrt::Windows::Graphics::Internal::Printing::PrintSupport::implementation::PrintSupportSession,winrt::Windows::Graphics::Internal::Printing::PrintSupport::PrintSupportSession>::get_weak<winrt::Windows::Graphics::Internal::Printing::PrintSupport::implementation::PrintSupportSession>(
    a1,
    &v12);
  v13 = operator new(0x58u);
  v7 = winrt::Windows::Graphics::Internal::Printing::PrintSupport::implementation::PrintSupportVirtualPrinterSession::VirtualPrinterSessionStateHandler::VirtualPrinterSessionStateHandler(
         v13,
         &v12,
         a1 + 504);
  v13 = 0;
  v8 = *(_QWORD *)(a1 + 544);
  *(_QWORD *)(a1 + 544) = v7;
  if ( v8 )
    std::default_delete<winrt::Windows::Graphics::Internal::Printing::PrintSupport::implementation::PrintSupportSession::SessionStateHandler>::operator()();
  std::unique_ptr<winrt::Windows::Graphics::Internal::Printing::PrintSupport::implementation::PrintSupportSession::SessionStateHandler>::~unique_ptr<winrt::Windows::Graphics::Internal::Printing::PrintSupport::implementation::PrintSupportSession::SessionStateHandler>(&v13);
  if ( v12 )
    winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v12);
  v9 = *v4 + 44LL;
  if ( !*v4 )
    v9 = 60;
  *(_OWORD *)v9 = *(_OWORD *)(a1 + 504);
  PrinterPdcAsync = winrt::Windows::Graphics::Internal::Printing::PrintSupport::implementation::PrintSupportSession::ReadPrinterPdcAsync(
                      a1,
                      (__int64)&v12);
  winrt::Windows::Foundation::IUnknown::operator=(a1 + 560, PrinterPdcAsync);
  winrt::Windows::Internal::ApplicationModel::WindowManagement::IWindow::~IWindow((winrt::Windows::Internal::ApplicationModel::WindowManagement::IWindow *)&v12);
  winrt::handle_type<winrt::impl::hstring_traits>::close(a2);
  return a1;
}

```

## disassembly

```asm
0x1800388a4  mov     [rsp-40h+arg_8], rdx
0x1800388a9  mov     [rsp-40h+arg_0], rcx
0x1800388ae  push    rbp
0x1800388af  push    rbx
0x1800388b0  push    rsi
0x1800388b1  push    rdi
0x1800388b2  push    r12
0x1800388b4  push    r13
0x1800388b6  push    r14
0x1800388b8  push    r15
0x1800388ba  mov     rbp, rsp
0x1800388bd  sub     rsp, 28h
0x1800388c1  mov     r12, rdx
0x1800388c4  mov     r14, rcx
0x1800388c7  xor     esi, esi
0x1800388c9  lea     rax, ??_7?$produce@UPrintSupportSession@implementation@PrintSupport@Printing@Internal@Graphics@Windows@winrt@@UIPrintSupportWorkflowSessionCommon@345678@@impl@winrt@@6B@; const winrt::impl::produce<winrt::Windows::Graphics::Internal::Printing::PrintSupport::implementation::PrintSupportSession,winrt::Windows::Graphics::Internal::Printing::PrintSupport::IPrintSupportWorkflowSessionCommon>::`vftable'
0x1800388d0  mov     [rcx+10h], rax
0x1800388d4  add     rcx, 8
0x1800388d8  call    ??0?$module_lock_updater@$00@impl@winrt@@QEAA@XZ; winrt::impl::module_lock_updater<1>::module_lock_updater<1>(void)
0x1800388dd  lea     edi, [rsi+1]
0x1800388e0  mov     [r14+8], rdi
0x1800388e4  lea     rax, ??_7?$PrintSupportSession_base@UPrintSupportSession@implementation@PrintSupport@Printing@Internal@Graphics@Windows@winrt@@$$V@implementation@PrintSupport@Printing@Internal@Graphics@Windows@winrt@@6B@; const winrt::Windows::Graphics::Internal::Printing::PrintSupport::implementation::PrintSupportSession_base<winrt::Windows::Graphics::Internal::Printing::PrintSupport::implementation::PrintSupportSession,>::`vftable'
0x1800388eb  mov     [r14], rax
0x1800388ee  lea     rdx, aWindowsPrintsu; "Windows.PrintSupportWorkflow"
0x1800388f5  lea     rcx, [rbp+arg_10]; this
0x1800388f9  call    ??0hstring@winrt@@QEAA@PEBG@Z; winrt::hstring::hstring(ushort const *)
0x1800388fe  nop
0x1800388ff  mov     r9d, 2DBh; unsigned int
0x180038905  lea     r8, [rbp+arg_10]; struct winrt::hstring *
0x180038909  mov     rdx, r12; struct winrt::hstring *
0x18003890c  lea     rcx, [r14+18h]; this
0x180038910  call    ??0PrintSupportSessionCommon@@QEAA@AEBUhstring@winrt@@0K@Z; PrintSupportSessionCommon::PrintSupportSessionCommon(winrt::hstring const &,winrt::hstring const &,ulong)
0x180038915  nop
0x180038916  lea     rcx, [rbp+arg_10]
0x18003891a  call    ?close@?$handle_type@Uhstring_traits@impl@winrt@@@winrt@@QEAAXXZ; winrt::handle_type<winrt::impl::hstring_traits>::close(void)
0x18003891f  lea     rax, ??_7?$heap_implements@UPrintSupportSession@implementation@PrintSupport@Printing@Internal@Graphics@Windows@winrt@@@impl@winrt@@6B?$PrintSupportSession_base@UPrintSupportSession@implementation@PrintSupport@Printing@Internal@Graphics@Windows@winrt@@$$V@implementation@PrintSupport@Printing@Internal@Graphics@Windows@2@@; const winrt::impl::heap_implements<winrt::Windows::Graphics::Internal::Printing::PrintSupport::implementation::PrintSupportSession>::`vftable'{for `winrt::Windows::Graphics::Internal::Printing::PrintSupport::implementation::PrintSupportSession_base<winrt::Windows::Graphics::Internal::Printing::PrintSupport::implementation::PrintSupportSession,>'}
0x180038926  mov     [r14], rax
0x180038929  lea     rax, ??_7PrintSupportSession@implementation@PrintSupport@Printing@Internal@Graphics@Windows@winrt@@6BPrintSupportSessionCommon@@@; const winrt::Windows::Graphics::Internal::Printing::PrintSupport::implementation::PrintSupportSession::`vftable'{for `PrintSupportSessionCommon'}
0x180038930  mov     [r14+18h], rax
0x180038934  mov     [r14+140h], sil
0x18003893b  mov     [r14+148h], rsi
0x180038942  mov     word ptr [r14+150h], 100h
0x18003894c  mov     dword ptr [rbp+arg_10], edi
0x18003894f  lea     rcx, [r14+158h]
0x180038956  lea     rdx, [rbp+arg_10]
0x18003895a  call    ??$?0W4EventOptions@wil@@$$V@?$unique_any_t@V?$event_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_exception_policy@3@@wil@@@wil@@QEAA@$$QEAW4EventOptions@1@@Z
0x18003895f  nop
0x180038960  mov     dword ptr [rbp+arg_10], edi
0x180038963  lea     rcx, [r14+160h]
0x18003896a  lea     rdx, [rbp+arg_10]
0x18003896e  call    ??$?0W4EventOptions@wil@@$$V@?$unique_any_t@V?$event_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_exception_policy@3@@wil@@@wil@@QEAA@$$QEAW4EventOptions@1@@Z
0x180038973  nop
0x180038974  mov     dword ptr [rbp+arg_10], edi
0x180038977  lea     rcx, [r14+168h]
0x18003897e  lea     rdx, [rbp+arg_10]
0x180038982  call    ??$?0W4EventOptions@wil@@$$V@?$unique_any_t@V?$event_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_exception_policy@3@@wil@@@wil@@QEAA@$$QEAW4EventOptions@1@@Z
0x180038987  nop
0x180038988  mov     dword ptr [rbp+arg_10], edi
0x18003898b  lea     rcx, [r14+170h]
0x180038992  lea     rdx, [rbp+arg_10]
0x180038996  call    ??$?0W4EventOptions@wil@@$$V@?$unique_any_t@V?$event_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_exception_policy@3@@wil@@@wil@@QEAA@$$QEAW4EventOptions@1@@Z
0x18003899b  nop
0x18003899c  mov     dword ptr [rbp+arg_10], edi
0x18003899f  lea     rcx, [r14+178h]
0x1800389a6  lea     rdx, [rbp+arg_10]
0x1800389aa  call    ??$?0W4EventOptions@wil@@$$V@?$unique_any_t@V?$event_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_exception_policy@3@@wil@@@wil@@QEAA@$$QEAW4EventOptions@1@@Z
0x1800389af  nop
0x1800389b0  mov     dword ptr [rbp+arg_10], edi
0x1800389b3  lea     rcx, [r14+180h]
0x1800389ba  lea     rdx, [rbp+arg_10]
0x1800389be  call    ??$?0W4EventOptions@wil@@$$V@?$unique_any_t@V?$event_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_exception_policy@3@@wil@@@wil@@QEAA@$$QEAW4EventOptions@1@@Z
0x1800389c3  nop
0x1800389c4  mov     dword ptr [rbp+arg_10], edi
0x1800389c7  lea     rcx, [r14+188h]
0x1800389ce  lea     rdx, [rbp+arg_10]
0x1800389d2  call    ??$?0W4EventOptions@wil@@$$V@?$unique_any_t@V?$event_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_exception_policy@3@@wil@@@wil@@QEAA@$$QEAW4EventOptions@1@@Z
0x1800389d7  nop
0x1800389d8  mov     [r14+190h], rsi
0x1800389df  lea     r13, [r14+198h]
0x1800389e6  mov     [r13+0], rsi
0x1800389ea  mov     [r14+1A0h], rsi
0x1800389f1  mov     [r14+1A8h], rsi
0x1800389f8  mov     [r14+1B0h], rsi
0x1800389ff  mov     [r14+1B8h], rsi
0x180038a06  mov     [r14+1C0h], rsi
0x180038a0d  mov     [r14+1C8h], rsi
0x180038a14  mov     [r14+1D0h], rsi
0x180038a1b  mov     [r14+1D8h], rsi
0x180038a22  mov     [r14+1E0h], rsi
0x180038a29  lea     rbx, [r14+1E8h]
0x180038a30  mov     [rbx], rsi
0x180038a33  mov     [rbx+8], rsi
0x180038a37  lea     ecx, [rsi+20h]; Size
0x180038a3a  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180038a3f  mov     [rax], rax
0x180038a42  mov     [rax+8], rax
0x180038a46  mov     [rax+10h], rax
0x180038a4a  mov     word ptr [rax+18h], 101h
0x180038a50  mov     [rbx], rax
0x180038a53  lea     r15, [r14+1F8h]
0x180038a5a  xorps   xmm0, xmm0
0x180038a5d  movups  xmmword ptr [r15], xmm0
0x180038a61  mov     [r14+208h], rsi
0x180038a68  mov     [r14+210h], rsi
0x180038a6f  mov     [r14+218h], rsi
0x180038a76  mov     [r14+220h], rsi
0x180038a7d  mov     [r14+228h], rsi
0x180038a84  mov     [r14+230h], rsi
0x180038a8b  xor     eax, eax
0x180038a8d  mov     [r14+238h], rax
0x180038a94  mov     [r14+240h], si
0x180038a9c  lea     ebx, [rsi+50h]
0x180038a9f  mov     ecx, ebx; Size
0x180038aa1  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180038aa6  mov     rsi, rax
0x180038aa9  mov     r8d, ebx; Size
0x180038aac  xor     edx, edx; Val
0x180038aae  mov     rcx, rax; void *
0x180038ab1  call    memset_0
0x180038ab6  lea     rdi, [rsi+10h]
0x180038aba  lea     rax, ??_7?$produce@UPrintSupportJobHandler@implementation@PrintSupport@Printing@Internal@Graphics@Windows@winrt@@UIPrintSupportJobHandler@345678@@impl@winrt@@6B@; const winrt::impl::produce<winrt::Windows::Graphics::Internal::Printing::PrintSupport::implementation::PrintSupportJobHandler,winrt::Windows::Graphics::Internal::Printing::PrintSupport::IPrintSupportJobHandler>::`vftable'
0x180038ac1  mov     [rdi], rax
0x180038ac4  lea     rcx, [rsi+8]
0x180038ac8  call    ??0?$module_lock_updater@$00@impl@winrt@@QEAA@XZ; winrt::impl::module_lock_updater<1>::module_lock_updater<1>(void)
0x180038acd  mov     qword ptr [rsi+8], 1
0x180038ad5  xor     ebx, ebx
0x180038ad7  mov     [rsi+18h], rbx
0x180038adb  mov     [rsi+20h], rbx
0x180038adf  mov     [rsi+28h], ebx
0x180038ae2  mov     [rsi+30h], rbx
0x180038ae6  mov     [rsi+38h], bl
0x180038ae9  xorps   xmm0, xmm0
0x180038aec  movups  xmmword ptr [rsi+3Ch], xmm0
0x180038af0  lea     rax, ??_7?$heap_implements@UPrintSupportJobHandler@implementation@PrintSupport@Printing@Internal@Graphics@Windows@winrt@@@impl@winrt@@6B@; const winrt::impl::heap_implements<winrt::Windows::Graphics::Internal::Printing::PrintSupport::implementation::PrintSupportJobHandler>::`vftable'
0x180038af7  mov     [rsi], rax
0x180038afa  mov     [rbp+arg_10], rdi
0x180038afe  lea     rdx, [rbp+arg_10]
0x180038b02  mov     rcx, r13
0x180038b05  call    ??4IUnknown@Foundation@Windows@winrt@@QEAAAEAU0123@$$QEAU0123@@Z; winrt::Windows::Foundation::IUnknown::operator=(winrt::Windows::Foundation::IUnknown &&)
0x180038b0a  lea     rcx, [rbp+arg_10]; this
0x180038b0e  call    ??1IWindow@WindowManagement@ApplicationModel@Internal@Windows@winrt@@QEAA@XZ; winrt::Windows::Internal::ApplicationModel::WindowManagement::IWindow::~IWindow(void)
0x180038b13  mov     rcx, r15; pguid
0x180038b16  call    cs:__imp_CoCreateGuid
0x180038b1c  test    eax, eax
0x180038b1e  jz      short loc_180038B41
0x180038b20  mov     eax, cs:dword_180083000
0x180038b26  cmp     eax, 5
0x180038b29  jbe     short loc_180038B41
0x180038b2b  xor     r8d, r8d
0x180038b2e  lea     rdx, byte_1800747FB
0x180038b35  lea     rcx, dword_180083000
0x180038b3c  call    ??$Write@$$V@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *)
0x180038b41  lea     rdx, [rbp+arg_10]
0x180038b45  mov     rcx, r14
0x180038b48  call    ??$get_weak@UPrintSupportSession@implementation@PrintSupport@Printing@Internal@Graphics@Windows@winrt@@@?$root_implements@UPrintSupportSession@implementation@PrintSupport@Printing@Internal@Graphics@Windows@winrt@@U1345678@@impl@winrt@@IEAA?AU?$weak_ref@UPrintSupportSession@implementation@PrintSupport@Printing@Internal@Graphics@Windows@winrt@@@2@XZ; winrt::impl::root_implements<winrt::Windows::Graphics::Internal::Printing::PrintSupport::implementation::PrintSupportSession,winrt::Windows::Graphics::Internal::Printing::PrintSupport::PrintSupportSession>::get_weak<winrt::Windows::Graphics::Internal::Printing::PrintSupport::implementation::PrintSupportSession>(void)
0x180038b4d  nop
0x180038b4e  mov     ecx, 58h ; 'X'; Size
0x180038b53  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180038b58  mov     [rbp+arg_18], rax
0x180038b5c  mov     r8, r15
0x180038b5f  lea     rdx, [rbp+arg_10]
0x180038b63  mov     rcx, rax
0x180038b66  call    ??0VirtualPrinterSessionStateHandler@PrintSupportVirtualPrinterSession@implementation@PrintSupport@Printing@Internal@Graphics@Windows@winrt@@QEAA@AEBU?$weak_ref@UPrintSupportVirtualPrinterSession@implementation@PrintSupport@Printing@Internal@Graphics@Windows@winrt@@@8@AEBU_GUID@@@Z; winrt::Windows::Graphics::Internal::Printing::PrintSupport::implementation::PrintSupportVirtualPrinterSession::VirtualPrinterSessionStateHandler::VirtualPrinterSessionStateHandler(winrt::weak_ref<winrt::Windows::Graphics::Internal::Printing::PrintSupport::implementation::PrintSupportVirtualPrinterSession> const &,_GUID const &)
0x180038b6b  mov     [rbp+arg_18], rbx
0x180038b6f  mov     rdx, [r14+220h]
0x180038b76  mov     [r14+220h], rax
0x180038b7d  test    rdx, rdx
0x180038b80  jz      short loc_180038B87
0x180038b82  call    ??R?$default_delete@USessionStateHandler@PrintSupportSession@implementation@PrintSupport@Printing@Internal@Graphics@Windows@winrt@@@std@@QEBAXPEAUSessionStateHandler@PrintSupportSession@implementation@PrintSupport@Printing@Internal@Graphics@Windows@winrt@@@Z; std::default_delete<winrt::Windows::Graphics::Internal::Printing::PrintSupport::implementation::PrintSupportSession::SessionStateHandler>::operator()(winrt::Windows::Graphics::Internal::Printing::PrintSupport::implementation::PrintSupportSession::SessionStateHandler *)
0x180038b87  lea     rcx, [rbp+arg_18]
0x180038b8b  call    ??1?$unique_ptr@USessionStateHandler@PrintSupportSession@implementation@PrintSupport@Printing@Internal@Graphics@Windows@winrt@@U?$default_delete@USessionStateHandler@PrintSupportSession@implementation@PrintSupport@Printing@Internal@Graphics@Windows@winrt@@@std@@@std@@QEAA@XZ; std::unique_ptr<winrt::Windows::Graphics::Internal::Printing::PrintSupport::implementation::PrintSupportSession::SessionStateHandler>::~unique_ptr<winrt::Windows::Graphics::Internal::Printing::PrintSupport::implementation::PrintSupportSession::SessionStateHandler>(void)
0x180038b90  nop
0x180038b91  cmp     [rbp+arg_10], rbx
0x180038b95  jz      short loc_180038BA0
0x180038b97  lea     rcx, [rbp+arg_10]
0x180038b9b  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x180038ba0  mov     rdx, [r13+0]
0x180038ba4  movups  xmm0, xmmword ptr [r15]
0x180038ba8  lea     rax, [rdx+2Ch]
0x180038bac  mov     ecx, 3Ch ; '<'
0x180038bb1  test    rdx, rdx
0x180038bb4  cmovz   rax, rcx
0x180038bb8  movdqu  xmmword ptr [rax], xmm0
0x180038bbc  lea     rdx, [rbp+arg_10]
0x180038bc0  mov     rcx, r14
0x180038bc3  call    ?ReadPrinterPdcAsync@PrintSupportSession@implementation@PrintSupport@Printing@Internal@Graphics@Windows@winrt@@AEAA?AUIAsyncAction@Foundation@78@XZ; winrt::Windows::Graphics::Internal::Printing::PrintSupport::implementation::PrintSupportSession::ReadPrinterPdcAsync(void)
0x180038bc8  mov     rdx, rax
0x180038bcb  lea     rcx, [r14+230h]
0x180038bd2  call    ??4IUnknown@Foundation@Windows@winrt@@QEAAAEAU0123@$$QEAU0123@@Z; winrt::Windows::Foundation::IUnknown::operator=(winrt::Windows::Foundation::IUnknown &&)
0x180038bd7  lea     rcx, [rbp+arg_10]; this
0x180038bdb  call    ??1IWindow@WindowManagement@ApplicationModel@Internal@Windows@winrt@@QEAA@XZ; winrt::Windows::Internal::ApplicationModel::WindowManagement::IWindow::~IWindow(void)
0x180038be0  nop
0x180038be1  mov     rcx, r12
0x180038be4  call    ?close@?$handle_type@Uhstring_traits@impl@winrt@@@winrt@@QEAAXXZ; winrt::handle_type<winrt::impl::hstring_traits>::close(void)
0x180038be9  mov     rax, r14
0x180038bec  add     rsp, 28h
0x180038bf0  pop     r15
0x180038bf2  pop     r14
0x180038bf4  pop     r13
0x180038bf6  pop     r12
0x180038bf8  pop     rdi
0x180038bf9  pop     rsi
0x180038bfa  pop     rbx
0x180038bfb  pop     rbp
0x180038bfc  retn
```
