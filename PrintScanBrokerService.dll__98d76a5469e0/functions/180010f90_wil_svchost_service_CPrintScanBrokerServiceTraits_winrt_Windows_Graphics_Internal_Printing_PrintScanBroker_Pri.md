# wil::svchost_service<CPrintScanBrokerServiceTraits,winrt::Windows::Graphics::Internal::Printing::PrintScanBroker::PrintScanBrokerHandler,winrt::Windows::Graphics::Internal::Printing::PrintScanBroker::VirtualPrinterInstallerBroker,winrt::Windows::Graphics::Internal::Printing::PrintScanBroker::IppQueuePropertyBagHandler>::start(void)

- ea: `0x180010f90`
- end: `0x1800110fe`
- name: `?start@?$svchost_service@UCPrintScanBrokerServiceTraits@@UPrintScanBrokerHandler@PrintScanBroker@Printing@Internal@Graphics@Windows@winrt@@UVirtualPrinterInstallerBroker@345678@UIppQueuePropertyBagHandler@345678@@wil@@AEAAXXZ`
- size: `366`
- prototype: `__int64 __fastcall(void *)`
- caller_count: `1`
- callee_count: `11`
- tags: `registry_config, loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x180010328`

## callees

- `0x180002d70`
- `0x180006e58`
- `0x180008114`
- `0x180008ab4`
- `0x18000ec78`
- `0x18000fa48`
- `0x180010d9c`
- `0x180010df0`
- `0x180010f90`
- `0x1800115f0`
- `0x180048010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventExW` at `0x180010ff9`
- `api-ms-win-core-synch-l1-1-0!CreateEventExW` at `0x180010ff9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001100b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001100b`
- `combase!__imp_CoGetSharedServiceId` at `0x180010fcd`
- `combase!__imp_CoGetSharedServiceId` at `0x180010fcd`
- `combase!__imp_CoRegisterServerShutdownDelay` at `0x180011037`
- `combase!__imp_CoRegisterServerShutdownDelay` at `0x180011037`

## string_xrefs

- `0x1800110c0`: `PrintScanBrokerService`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall wil::svchost_service<CPrintScanBrokerServiceTraits,winrt::Windows::Graphics::Internal::Printing::PrintScanBroker::PrintScanBrokerHandler,winrt::Windows::Graphics::Internal::Printing::PrintScanBroker::VirtualPrinterInstallerBroker,winrt::Windows::Graphics::Internal::Printing::PrintScanBroker::IppQueuePropertyBagHandler>::start(
        void *a1)
{
  unsigned int SharedServiceId; // eax
  void *v2; // rdx
  HANDLE Event; // rbx
  unsigned int v4; // r8d
  const char *v5; // r9
  unsigned int v6; // eax
  __int64 v7; // rax
  __int64 v8; // rdx
  void (__fastcall *v9)(char *, const WCHAR *, __int64, __int64 (__fastcall *)(void *, unsigned __int8), __int128 *, int); // rdi
  __int64 v10; // rbx
  int v12; // [rsp+40h] [rbp-20h] BYREF
  __int128 v13; // [rsp+48h] [rbp-18h]
  wil::details::in1diag3 *retaddr; // [rsp+78h] [rbp+18h]
  void *v15; // [rsp+80h] [rbp+20h] BYREF
  char v16; // [rsp+88h] [rbp+28h] BYREF

  v15 = a1;
  wil::svchost_service<CPrintScanBrokerServiceTraits,winrt::Windows::Graphics::Internal::Printing::PrintScanBroker::PrintScanBrokerHandler,winrt::Windows::Graphics::Internal::Printing::PrintScanBroker::VirtualPrinterInstallerBroker,winrt::Windows::Graphics::Internal::Printing::PrintScanBroker::IppQueuePropertyBagHandler>::update_status(
    &g_serviceWithBroker,
    2,
    0);
  LODWORD(v15) = 0;
  v12 = 0;
  v13 = 0;
  SharedServiceId = CoGetSharedServiceId(&v15);
  winrt::check_hresult(&v16, SharedServiceId, &v12);
  wil::details::g_service_id = (unsigned int)v15;
  Event = CreateEventExW(0, 0, 1u, 0x1F0003u);
  if ( !Event )
    wil::details::in1diag3::Throw_GetLastError(retaddr, v2, v4, v5);
  GetLastError();
  _reset___unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAAXPEAX_Z(
    &xmmword_180060F38,
    Event);
  v12 = 0;
  v13 = 0;
  v6 = CoRegisterServerShutdownDelay(xmmword_180060F38, 60000);
  winrt::check_hresult(&v15, v6, &v12);
  v15 = operator new(0x18u);
  v7 = wil::details::svchost_module<winrt::Windows::Graphics::Internal::Printing::PrintScanBroker::PrintScanBrokerHandler,winrt::Windows::Graphics::Internal::Printing::PrintScanBroker::VirtualPrinterInstallerBroker,winrt::Windows::Graphics::Internal::Printing::PrintScanBroker::IppQueuePropertyBagHandler>::svchost_module<winrt::Windows::Graphics::Internal::Printing::PrintScanBroker::PrintScanBrokerHandler,winrt::Windows::Graphics::Internal::Printing::PrintScanBroker::VirtualPrinterInstallerBroker,winrt::Windows::Graphics::Internal::Printing::PrintScanBroker::IppQueuePropertyBagHandler>(v15);
  v15 = 0;
  v8 = *((_QWORD *)&xmmword_180060F38 + 1);
  *((_QWORD *)&xmmword_180060F38 + 1) = v7;
  if ( v8 )
    std::default_delete<wil::details::svchost_module<winrt::Windows::Graphics::Internal::Printing::PrintScanBroker::PrintScanBrokerHandler,winrt::Windows::Graphics::Internal::Printing::PrintScanBroker::VirtualPrinterInstallerBroker,winrt::Windows::Graphics::Internal::Printing::PrintScanBroker::IppQueuePropertyBagHandler>>::operator()();
  std::unique_ptr<wil::details::svchost_module<winrt::Windows::Graphics::Internal::Printing::PrintScanBroker::PrintScanBrokerHandler,winrt::Windows::Graphics::Internal::Printing::PrintScanBroker::VirtualPrinterInstallerBroker,winrt::Windows::Graphics::Internal::Printing::PrintScanBroker::IppQueuePropertyBagHandler>>::~unique_ptr<wil::details::svchost_module<winrt::Windows::Graphics::Internal::Printing::PrintScanBroker::PrintScanBrokerHandler,winrt::Windows::Graphics::Internal::Printing::PrintScanBroker::VirtualPrinterInstallerBroker,winrt::Windows::Graphics::Internal::Printing::PrintScanBroker::IppQueuePropertyBagHandler>>(&v15);
  v9 = *(void (__fastcall **)(char *, const WCHAR *, __int64, __int64 (__fastcall *)(void *, unsigned __int8), __int128 *, int))(g_serviceWithBroker + 192);
  v10 = xmmword_180060F38;
  wil::details::unique_storage<wil::details::resource_policy<void *,int (*)(void *),&int UnregisterWait(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::reset(
    (char *)&g_serviceWithBroker + 8,
    0);
  v9(
    (char *)&g_serviceWithBroker + 8,
    L"PrintScanBrokerService",
    v10,
    _lambda_413d026c646ef47bf3d5d1f9f522520c_::_lambda_invoker_cdecl_,
    &g_serviceWithBroker,
    8);
  return wil::svchost_service<CPrintScanBrokerServiceTraits,winrt::Windows::Graphics::Internal::Printing::PrintScanBroker::PrintScanBrokerHandler,winrt::Windows::Graphics::Internal::Printing::PrintScanBroker::VirtualPrinterInstallerBroker,winrt::Windows::Graphics::Internal::Printing::PrintScanBroker::IppQueuePropertyBagHandler>::update_status(
           &g_serviceWithBroker,
           4,
           0);
}

```

## disassembly

```asm
0x180010f90  mov     [rsp-18h+arg_10], rbx
0x180010f95  mov     [rsp-18h+arg_0], rcx
0x180010f9a  push    rbp
0x180010f9b  push    rsi
0x180010f9c  push    rdi
0x180010f9d  mov     rbp, rsp
0x180010fa0  sub     rsp, 60h
0x180010fa4  xor     edi, edi
0x180010fa6  xor     r8d, r8d
0x180010fa9  lea     edx, [rdi+2]
0x180010fac  lea     rsi, ?g_serviceWithBroker@@3V?$svchost_service@UCPrintScanBrokerServiceTraits@@UPrintScanBrokerHandler@PrintScanBroker@Printing@Internal@Graphics@Windows@winrt@@UVirtualPrinterInstallerBroker@345678@UIppQueuePropertyBagHandler@345678@@wil@@A; wil::svchost_service<CPrintScanBrokerServiceTraits,winrt::Windows::Graphics::Internal::Printing::PrintScanBroker::PrintScanBrokerHandler,winrt::Windows::Graphics::Internal::Printing::PrintScanBroker::VirtualPrinterInstallerBroker,winrt::Windows::Graphics::Internal::Printing::PrintScanBroker::IppQueuePropertyBagHandler> g_serviceWithBroker
0x180010fb3  mov     rcx, rsi
0x180010fb6  call    ?update_status@?$svchost_service@UCPrintScanBrokerServiceTraits@@UPrintScanBrokerHandler@PrintScanBroker@Printing@Internal@Graphics@Windows@winrt@@UVirtualPrinterInstallerBroker@345678@UIppQueuePropertyBagHandler@345678@@wil@@AEAAXKK@Z; wil::svchost_service<CPrintScanBrokerServiceTraits,winrt::Windows::Graphics::Internal::Printing::PrintScanBroker::PrintScanBrokerHandler,winrt::Windows::Graphics::Internal::Printing::PrintScanBroker::VirtualPrinterInstallerBroker,winrt::Windows::Graphics::Internal::Printing::PrintScanBroker::IppQueuePropertyBagHandler>::update_status(ulong,ulong)
0x180010fbb  mov     dword ptr [rbp+arg_0], edi
0x180010fbe  mov     [rbp+var_20], edi
0x180010fc1  xorps   xmm0, xmm0
0x180010fc4  movdqu  [rbp+var_18], xmm0
0x180010fc9  lea     rcx, [rbp+arg_0]
0x180010fcd  call    cs:__imp_CoGetSharedServiceId
0x180010fd3  lea     r8, [rbp+var_20]
0x180010fd7  mov     edx, eax
0x180010fd9  lea     rcx, [rbp+arg_8]
0x180010fdd  call    ?check_hresult@winrt@@YA?AUhresult@1@U21@AEBUslim_source_location@impl@1@@Z; winrt::check_hresult(winrt::hresult,winrt::impl::slim_source_location const &)
0x180010fe2  mov     eax, dword ptr [rbp+arg_0]
0x180010fe5  mov     cs:?g_service_id@details@wil@@3KA, eax; ulong wil::details::g_service_id
0x180010feb  xor     edx, edx; lpName
0x180010fed  xor     ecx, ecx; lpEventAttributes
0x180010fef  mov     r9d, 1F0003h; dwDesiredAccess
0x180010ff5  lea     r8d, [rdi+1]; dwFlags
0x180010ff9  call    cs:__imp_CreateEventExW
0x180010fff  mov     rbx, rax
0x180011002  test    rax, rax
0x180011005  jz      loc_1800110F4
0x18001100b  call    cs:__imp_GetLastError
0x180011011  mov     rdx, rbx
0x180011014  lea     rcx, xmmword_180060F38
0x18001101b  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z
0x180011020  mov     [rbp+var_20], edi
0x180011023  xorps   xmm0, xmm0
0x180011026  movdqu  [rbp+var_18], xmm0
0x18001102b  mov     edx, 0EA60h
0x180011030  mov     rcx, qword ptr cs:xmmword_180060F38
0x180011037  call    cs:__imp_CoRegisterServerShutdownDelay
0x18001103d  lea     r8, [rbp+var_20]
0x180011041  mov     edx, eax
0x180011043  lea     rcx, [rbp+arg_0]
0x180011047  call    ?check_hresult@winrt@@YA?AUhresult@1@U21@AEBUslim_source_location@impl@1@@Z; winrt::check_hresult(winrt::hresult,winrt::impl::slim_source_location const &)
0x18001104c  lea     ecx, [rdi+18h]; Size
0x18001104f  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180011054  mov     [rbp+arg_0], rax
0x180011058  mov     rcx, rax
0x18001105b  call    ??0?$svchost_module@UPrintScanBrokerHandler@PrintScanBroker@Printing@Internal@Graphics@Windows@winrt@@UVirtualPrinterInstallerBroker@234567@UIppQueuePropertyBagHandler@234567@@details@wil@@QEAA@XZ; wil::details::svchost_module<winrt::Windows::Graphics::Internal::Printing::PrintScanBroker::PrintScanBrokerHandler,winrt::Windows::Graphics::Internal::Printing::PrintScanBroker::VirtualPrinterInstallerBroker,winrt::Windows::Graphics::Internal::Printing::PrintScanBroker::IppQueuePropertyBagHandler>::svchost_module<winrt::Windows::Graphics::Internal::Printing::PrintScanBroker::PrintScanBrokerHandler,winrt::Windows::Graphics::Internal::Printing::PrintScanBroker::VirtualPrinterInstallerBroker,winrt::Windows::Graphics::Internal::Printing::PrintScanBroker::IppQueuePropertyBagHandler>(void)
0x180011060  nop
0x180011061  mov     [rbp+arg_0], rdi
0x180011065  mov     rdx, qword ptr cs:xmmword_180060F38+8
0x18001106c  mov     qword ptr cs:xmmword_180060F38+8, rax
0x180011073  test    rdx, rdx
0x180011076  jz      short loc_18001107D
0x180011078  call    ??R?$default_delete@V?$svchost_module@UPrintScanBrokerHandler@PrintScanBroker@Printing@Internal@Graphics@Windows@winrt@@UVirtualPrinterInstallerBroker@234567@UIppQueuePropertyBagHandler@234567@@details@wil@@@std@@QEBAXPEAV?$svchost_module@UPrintScanBrokerHandler@PrintScanBroker@Printing@Internal@Graphics@Windows@winrt@@UVirtualPrinterInstallerBroker@234567@UIppQueuePropertyBagHandler@234567@@details@wil@@@Z; std::default_delete<wil::details::svchost_module<winrt::Windows::Graphics::Internal::Printing::PrintScanBroker::PrintScanBrokerHandler,winrt::Windows::Graphics::Internal::Printing::PrintScanBroker::VirtualPrinterInstallerBroker,winrt::Windows::Graphics::Internal::Printing::PrintScanBroker::IppQueuePropertyBagHandler>>::operator()(wil::details::svchost_module<winrt::Windows::Graphics::Internal::Printing::PrintScanBroker::PrintScanBrokerHandler,winrt::Windows::Graphics::Internal::Printing::PrintScanBroker::VirtualPrinterInstallerBroker,winrt::Windows::Graphics::Internal::Printing::PrintScanBroker::IppQueuePropertyBagHandler> *)
0x18001107d  lea     rcx, [rbp+arg_0]
0x180011081  call    ??1?$unique_ptr@V?$svchost_module@UPrintScanBrokerHandler@PrintScanBroker@Printing@Internal@Graphics@Windows@winrt@@UVirtualPrinterInstallerBroker@234567@UIppQueuePropertyBagHandler@234567@@details@wil@@U?$default_delete@V?$svchost_module@UPrintScanBrokerHandler@PrintScanBroker@Printing@Internal@Graphics@Windows@winrt@@UVirtualPrinterInstallerBroker@234567@UIppQueuePropertyBagHandler@234567@@details@wil@@@std@@@std@@QEAA@XZ; std::unique_ptr<wil::details::svchost_module<winrt::Windows::Graphics::Internal::Printing::PrintScanBroker::PrintScanBrokerHandler,winrt::Windows::Graphics::Internal::Printing::PrintScanBroker::VirtualPrinterInstallerBroker,winrt::Windows::Graphics::Internal::Printing::PrintScanBroker::IppQueuePropertyBagHandler>>::~unique_ptr<wil::details::svchost_module<winrt::Windows::Graphics::Internal::Printing::PrintScanBroker::PrintScanBrokerHandler,winrt::Windows::Graphics::Internal::Printing::PrintScanBroker::VirtualPrinterInstallerBroker,winrt::Windows::Graphics::Internal::Printing::PrintScanBroker::IppQueuePropertyBagHandler>>(void)
0x180011086  mov     rax, qword ptr cs:?g_serviceWithBroker@@3V?$svchost_service@UCPrintScanBrokerServiceTraits@@UPrintScanBrokerHandler@PrintScanBroker@Printing@Internal@Graphics@Windows@winrt@@UVirtualPrinterInstallerBroker@345678@UIppQueuePropertyBagHandler@345678@@wil@@A; wil::svchost_service<CPrintScanBrokerServiceTraits,winrt::Windows::Graphics::Internal::Printing::PrintScanBroker::PrintScanBrokerHandler,winrt::Windows::Graphics::Internal::Printing::PrintScanBroker::VirtualPrinterInstallerBroker,winrt::Windows::Graphics::Internal::Printing::PrintScanBroker::IppQueuePropertyBagHandler> g_serviceWithBroker
0x18001108d  mov     rdi, [rax+0C0h]
0x180011094  mov     rbx, qword ptr cs:xmmword_180060F38
0x18001109b  xor     edx, edx
0x18001109d  lea     rcx, ?g_serviceWithBroker@@3V?$svchost_service@UCPrintScanBrokerServiceTraits@@UPrintScanBrokerHandler@PrintScanBroker@Printing@Internal@Graphics@Windows@winrt@@UVirtualPrinterInstallerBroker@345678@UIppQueuePropertyBagHandler@345678@@wil@@A+8; wil::svchost_service<CPrintScanBrokerServiceTraits,winrt::Windows::Graphics::Internal::Printing::PrintScanBroker::PrintScanBrokerHandler,winrt::Windows::Graphics::Internal::Printing::PrintScanBroker::VirtualPrinterInstallerBroker,winrt::Windows::Graphics::Internal::Printing::PrintScanBroker::IppQueuePropertyBagHandler> g_serviceWithBroker
0x1800110a4  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AHPEAX@Z$1?UnregisterWait@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::resource_policy<void *,int (*)(void *),&UnregisterWait(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::reset(void *)
0x1800110a9  mov     [rsp+60h+var_38], 8
0x1800110b1  mov     [rsp+60h+var_40], rsi
0x1800110b6  lea     r9, ?_lambda_invoker_cdecl_@_lambda_413d026c646ef47bf3d5d1f9f522520c_@@CA@PEAXE@Z; _lambda_413d026c646ef47bf3d5d1f9f522520c_::_lambda_invoker_cdecl_(void *,uchar)
0x1800110bd  mov     r8, rbx
0x1800110c0  lea     rdx, ServiceName; "PrintScanBrokerService"
0x1800110c7  lea     rcx, ?g_serviceWithBroker@@3V?$svchost_service@UCPrintScanBrokerServiceTraits@@UPrintScanBrokerHandler@PrintScanBroker@Printing@Internal@Graphics@Windows@winrt@@UVirtualPrinterInstallerBroker@345678@UIppQueuePropertyBagHandler@345678@@wil@@A+8; wil::svchost_service<CPrintScanBrokerServiceTraits,winrt::Windows::Graphics::Internal::Printing::PrintScanBroker::PrintScanBrokerHandler,winrt::Windows::Graphics::Internal::Printing::PrintScanBroker::VirtualPrinterInstallerBroker,winrt::Windows::Graphics::Internal::Printing::PrintScanBroker::IppQueuePropertyBagHandler> g_serviceWithBroker
0x1800110ce  mov     rax, rdi
0x1800110d1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800110d6  xor     r8d, r8d
0x1800110d9  lea     edx, [r8+4]
0x1800110dd  mov     rcx, rsi
0x1800110e0  mov     rbx, [rsp+60h+arg_10]
0x1800110e8  add     rsp, 60h
0x1800110ec  pop     rdi
0x1800110ed  pop     rsi
0x1800110ee  pop     rbp
0x1800110ef  jmp     ?update_status@?$svchost_service@UCPrintScanBrokerServiceTraits@@UPrintScanBrokerHandler@PrintScanBroker@Printing@Internal@Graphics@Windows@winrt@@UVirtualPrinterInstallerBroker@345678@UIppQueuePropertyBagHandler@345678@@wil@@AEAAXKK@Z; wil::svchost_service<CPrintScanBrokerServiceTraits,winrt::Windows::Graphics::Internal::Printing::PrintScanBroker::PrintScanBrokerHandler,winrt::Windows::Graphics::Internal::Printing::PrintScanBroker::VirtualPrinterInstallerBroker,winrt::Windows::Graphics::Internal::Printing::PrintScanBroker::IppQueuePropertyBagHandler>::update_status(ulong,ulong)
0x1800110f4  mov     rcx, [rbp+18h]; this
0x1800110f8  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
```
