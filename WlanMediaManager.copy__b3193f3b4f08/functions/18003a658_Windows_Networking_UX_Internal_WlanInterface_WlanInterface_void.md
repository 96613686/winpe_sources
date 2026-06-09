# Windows::Networking::UX::Internal::WlanInterface::~WlanInterface(void)

- ea: `0x18003a658`
- end: `0x18003a878`
- name: `??1WlanInterface@Internal@UX@Networking@Windows@@QEAA@XZ`
- size: `544`
- prototype: `void __fastcall(PVOID Parameter)`
- caller_count: `1`
- callee_count: `14`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x180020a9c`

## callees

- `0x180003ed0`
- `0x180008e30`
- `0x18000b5e0`
- `0x1800121e8`
- `0x1800141a0`
- `0x180037578`
- `0x180037770`
- `0x18003a190`
- `0x18003a600`
- `0x18003a658`
- `0x180047680`
- `0x180048424`
- `0x18004bc5c`
- `0x18004ca40`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18003a777`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18003a818`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18003a777`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18003a818`
- `ntdll!RtlUnsubscribeWnfNotificationWaitForCompletion` at `0x18003a714`
- `ntdll!RtlUnsubscribeWnfNotificationWaitForCompletion` at `0x18003a714`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003a742`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003a790`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003a7a8`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003a7c0`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003a7d8`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003a842`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003a742`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003a790`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003a7a8`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003a7c0`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003a7d8`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003a842`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003a835`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003a835`

## pseudocode

```c
void __fastcall Windows::Networking::UX::Internal::WlanInterface::~WlanInterface(char *Parameter)
{
  struct _RTL_CRITICAL_SECTION *v2; // rsi
  __int64 v3; // rdx
  __int64 v4; // r8
  __int64 v5; // rcx
  __int64 v6; // rdx
  __int64 v7; // r8
  __int64 v8; // rdx
  __int64 v9; // r8
  __int64 v10; // rdx
  __int64 v11; // r8
  void *v12; // rcx
  int v13; // [rsp+20h] [rbp-178h] BYREF
  _BYTE v14[8]; // [rsp+28h] [rbp-170h] BYREF
  _BYTE v15[336]; // [rsp+30h] [rbp-168h] BYREF

  *(_QWORD *)Parameter = &Windows::Networking::UX::Internal::WlanInterface::`vftable'{for `Windows::Networking::UX::Internal::IWlanConnectionFlowCallback'};
  *((_QWORD *)Parameter + 1) = &Windows::Networking::UX::Internal::WlanInterface::`vftable'{for `Windows::Networking::UX::Internal::IInterfaceNlmChangeListener'};
  v2 = (struct _RTL_CRITICAL_SECTION *)(Parameter + 752);
  wil::EnterCriticalSection(v14, Parameter + 752);
  if ( **((_DWORD **)Parameter + 138) == 1 )
  {
    NetworkUxTelemetry::WlanConnectionFlow::TransferToCurrentThread(Parameter + 832, v15);
    v13 = 2;
    NetworkUxTelemetry::WlanConnectionFlow::StopWithResult<enum ConnectionFlowResult>(v15, 2147483674LL, &v13);
    NetworkUxTelemetry::WlanConnectionFlow::~WlanConnectionFlow((NetworkUxTelemetry::WlanConnectionFlow *)v15);
  }
  Windows::Networking::UX::Internal::WlanInterface::_CleanupConnectionFlow(Parameter);
  Windows::Networking::UX::Internal::WlanInterface::_ResetScanTimer(Parameter, 0);
  Windows::Networking::UX::Internal::WlanInterface::_UnsubscribeWnfMediaUIEvent((Windows::Networking::UX::Internal::WlanInterface *)Parameter);
  if ( *((_QWORD *)Parameter + 175) )
  {
    RtlUnsubscribeWnfNotificationWaitForCompletion();
    *((_QWORD *)Parameter + 175) = 0;
  }
  wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&void LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&void LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>(v14);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(
    Parameter + 1408,
    v3,
    v4);
  WindowsDeleteString(*((HSTRING *)Parameter + 174));
  *((_QWORD *)Parameter + 174) = 0;
  std::_List_node<std::wstring,void *>::_Free_non_head<std::allocator<std::_List_node<std::wstring,void *>>>(
    v5,
    *((_QWORD *)Parameter + 168));
  std::_Deallocate<16>(*((_QWORD *)Parameter + 168), 48);
  DeleteCriticalSection((LPCRITICAL_SECTION)(Parameter + 1304));
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(
    Parameter + 1296,
    v6,
    v7);
  WindowsDeleteString(*((HSTRING *)Parameter + 157));
  *((_QWORD *)Parameter + 157) = 0;
  WindowsDeleteString(*((HSTRING *)Parameter + 155));
  *((_QWORD *)Parameter + 155) = 0;
  WindowsDeleteString(*((HSTRING *)Parameter + 154));
  *((_QWORD *)Parameter + 154) = 0;
  WindowsDeleteString(*((HSTRING *)Parameter + 153));
  *((_QWORD *)Parameter + 153) = 0;
  NetworkUxTelemetry::WlanConnectionFlow::~WlanConnectionFlow((NetworkUxTelemetry::WlanConnectionFlow *)(Parameter + 832));
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(
    Parameter + 816,
    v8,
    v9);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(
    Parameter + 808,
    v10,
    v11);
  std::unique_ptr<CMediaUiRequestSubscriber>::~unique_ptr<CMediaUiRequestSubscriber>(Parameter + 800);
  DeleteCriticalSection(v2);
  v12 = (void *)*((_QWORD *)Parameter + 92);
  *((_QWORD *)Parameter + 92) = 0;
  if ( v12 )
    CoTaskMemFree(v12);
  WindowsDeleteString(*((HSTRING *)Parameter + 87));
  *((_QWORD *)Parameter + 87) = 0;
}

```

## disassembly

```asm
0x18003a658  mov     [rsp+arg_8], rbx
0x18003a65d  mov     [rsp+arg_10], rsi
0x18003a662  push    rdi
0x18003a663  sub     rsp, 190h
0x18003a66a  mov     rax, cs:__security_cookie
0x18003a671  xor     rax, rsp
0x18003a674  mov     [rsp+198h+var_18], rax
0x18003a67c  mov     rbx, rcx
0x18003a67f  lea     rax, ??_7WlanInterface@Internal@UX@Networking@Windows@@6BIWlanConnectionFlowCallback@1234@@; const Windows::Networking::UX::Internal::WlanInterface::`vftable'{for `Windows::Networking::UX::Internal::IWlanConnectionFlowCallback'}
0x18003a686  mov     [rcx], rax
0x18003a689  lea     rax, ??_7WlanInterface@Internal@UX@Networking@Windows@@6BIInterfaceNlmChangeListener@1234@@; const Windows::Networking::UX::Internal::WlanInterface::`vftable'{for `Windows::Networking::UX::Internal::IInterfaceNlmChangeListener'}
0x18003a690  mov     [rcx+8], rax
0x18003a694  lea     rsi, [rcx+2F0h]
0x18003a69b  mov     rdx, rsi
0x18003a69e  lea     rcx, [rsp+198h+var_170]
0x18003a6a3  call    ?EnterCriticalSection@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_CRITICAL_SECTION@@P6AXPEAU1@@Z$1?LeaveCriticalSection@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@1@PEAU_RTL_CRITICAL_SECTION@@@Z; wil::EnterCriticalSection(_RTL_CRITICAL_SECTION *)
0x18003a6a8  lea     rdi, [rbx+340h]
0x18003a6af  mov     rax, [rdi+110h]
0x18003a6b6  cmp     dword ptr [rax], 1
0x18003a6b9  jnz     short loc_18003A6EE
0x18003a6bb  lea     rdx, [rsp+198h+var_168]
0x18003a6c0  mov     rcx, rdi
0x18003a6c3  call    ?TransferToCurrentThread@WlanConnectionFlow@NetworkUxTelemetry@@QEAA?AV12@XZ; NetworkUxTelemetry::WlanConnectionFlow::TransferToCurrentThread(void)
0x18003a6c8  mov     [rsp+198h+var_178], 2
0x18003a6d0  lea     r8, [rsp+198h+var_178]
0x18003a6d5  mov     edx, 8000001Ah
0x18003a6da  lea     rcx, [rsp+198h+var_168]
0x18003a6df  call    ??$StopWithResult@W4ConnectionFlowResult@@@WlanConnectionFlow@NetworkUxTelemetry@@QEAAXJ$$QEAW4ConnectionFlowResult@@@Z; NetworkUxTelemetry::WlanConnectionFlow::StopWithResult<ConnectionFlowResult>(long,ConnectionFlowResult &&)
0x18003a6e4  lea     rcx, [rsp+198h+var_168]; this
0x18003a6e9  call    ??1WlanConnectionFlow@NetworkUxTelemetry@@QEAA@XZ; NetworkUxTelemetry::WlanConnectionFlow::~WlanConnectionFlow(void)
0x18003a6ee  mov     rcx, rbx
0x18003a6f1  call    ?_CleanupConnectionFlow@WlanInterface@Internal@UX@Networking@Windows@@IEAAJUwrite_lock_required@wil@@@Z; Windows::Networking::UX::Internal::WlanInterface::_CleanupConnectionFlow(wil::write_lock_required)
0x18003a6f6  xor     edx, edx; bool
0x18003a6f8  mov     rcx, rbx; Parameter
0x18003a6fb  call    ?_ResetScanTimer@WlanInterface@Internal@UX@Networking@Windows@@IEAAX_N@Z; Windows::Networking::UX::Internal::WlanInterface::_ResetScanTimer(bool)
0x18003a700  mov     rcx, rbx; this
0x18003a703  call    ?_UnsubscribeWnfMediaUIEvent@WlanInterface@Internal@UX@Networking@Windows@@IEAAJXZ; Windows::Networking::UX::Internal::WlanInterface::_UnsubscribeWnfMediaUIEvent(void)
0x18003a708  mov     rcx, [rbx+578h]
0x18003a70f  test    rcx, rcx
0x18003a712  jz      short loc_18003A725
0x18003a714  call    cs:__imp_RtlUnsubscribeWnfNotificationWaitForCompletion
0x18003a71a  mov     qword ptr [rbx+578h], 0
0x18003a725  lea     rcx, [rsp+198h+var_170]
0x18003a72a  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_CRITICAL_SECTION@@P6AXPEAU1@@Z$1?LeaveCriticalSection@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>(void)
0x18003a72f  lea     rcx, [rbx+580h]
0x18003a736  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18003a73b  mov     rcx, [rbx+570h]; string
0x18003a742  call    cs:__imp_WindowsDeleteString
0x18003a748  mov     qword ptr [rbx+570h], 0
0x18003a753  mov     rdx, [rbx+540h]
0x18003a75a  call    ??$_Free_non_head@V?$allocator@U?$_List_node@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAX@std@@@std@@@?$_List_node@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAX@std@@SAXAEAV?$allocator@U?$_List_node@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAX@std@@@1@PEAU01@@Z; std::_List_node<std::wstring,void *>::_Free_non_head<std::allocator<std::_List_node<std::wstring,void *>>>(std::allocator<std::_List_node<std::wstring,void *>> &,std::_List_node<std::wstring,void *> *)
0x18003a75f  mov     edx, 30h ; '0'
0x18003a764  mov     rcx, [rbx+540h]
0x18003a76b  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x18003a770  lea     rcx, [rbx+518h]; lpCriticalSection
0x18003a777  call    cs:__imp_DeleteCriticalSection
0x18003a77d  lea     rcx, [rbx+510h]
0x18003a784  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18003a789  mov     rcx, [rbx+4E8h]; string
0x18003a790  call    cs:__imp_WindowsDeleteString
0x18003a796  mov     qword ptr [rbx+4E8h], 0
0x18003a7a1  mov     rcx, [rbx+4D8h]; string
0x18003a7a8  call    cs:__imp_WindowsDeleteString
0x18003a7ae  mov     qword ptr [rbx+4D8h], 0
0x18003a7b9  mov     rcx, [rbx+4D0h]; string
0x18003a7c0  call    cs:__imp_WindowsDeleteString
0x18003a7c6  mov     qword ptr [rbx+4D0h], 0
0x18003a7d1  mov     rcx, [rbx+4C8h]; string
0x18003a7d8  call    cs:__imp_WindowsDeleteString
0x18003a7de  mov     qword ptr [rbx+4C8h], 0
0x18003a7e9  mov     rcx, rdi; this
0x18003a7ec  call    ??1WlanConnectionFlow@NetworkUxTelemetry@@QEAA@XZ; NetworkUxTelemetry::WlanConnectionFlow::~WlanConnectionFlow(void)
0x18003a7f1  lea     rcx, [rbx+330h]
0x18003a7f8  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18003a7fd  lea     rcx, [rbx+328h]
0x18003a804  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18003a809  lea     rcx, [rbx+320h]
0x18003a810  call    ??1?$unique_ptr@VCMediaUiRequestSubscriber@@U?$default_delete@VCMediaUiRequestSubscriber@@@std@@@std@@QEAA@XZ; std::unique_ptr<CMediaUiRequestSubscriber>::~unique_ptr<CMediaUiRequestSubscriber>(void)
0x18003a815  mov     rcx, rsi; lpCriticalSection
0x18003a818  call    cs:__imp_DeleteCriticalSection
0x18003a81e  mov     rcx, [rbx+2E0h]; pv
0x18003a825  mov     qword ptr [rbx+2E0h], 0
0x18003a830  test    rcx, rcx
0x18003a833  jz      short loc_18003A83B
0x18003a835  call    cs:__imp_CoTaskMemFree
0x18003a83b  mov     rcx, [rbx+2B8h]; string
0x18003a842  call    cs:__imp_WindowsDeleteString
0x18003a848  mov     qword ptr [rbx+2B8h], 0
0x18003a853  mov     rcx, [rsp+198h+var_18]
0x18003a85b  xor     rcx, rsp; StackCookie
0x18003a85e  call    __security_check_cookie
0x18003a863  lea     r11, [rsp+198h+var_8]
0x18003a86b  mov     rbx, [r11+18h]
0x18003a86f  mov     rsi, [r11+20h]
0x18003a873  mov     rsp, r11
0x18003a876  pop     rdi
0x18003a877  retn
```
