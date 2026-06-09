# ImmersiveShellFocusSingletonConnector::GetSingletonThemeManager(void)

- ea: `0x18002e730`
- end: `0x18002e795`
- name: `?GetSingletonThemeManager@ImmersiveShellFocusSingletonConnector@@UEAA?AUFocusSessionThemeManager@Shell@Internal@Windows@winrt@@XZ`
- size: `101`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0x180008ebc`
- `0x18000dfc0`
- `0x180022608`
- `0x18002e64c`
- `0x18002e6bc`

## import_xrefs

- `api-ms-win-shcore-comhelpers-l1-1-0!IUnknown_QueryService` at `0x18002e757`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall ImmersiveShellFocusSingletonConnector::GetSingletonThemeManager(__int64 a1, __int64 a2)
{
  __int64 v4; // [rsp+48h] [rbp+10h] BYREF
  LPVOID v5; // [rsp+50h] [rbp+18h] BYREF
  LPVOID v6; // [rsp+58h] [rbp+20h] BYREF

  v4 = a2;
  wil::CoCreateInstance<IServiceProvider,wil::err_exception_policy>(&v5);
  v6 = v5;
  winrt::capture<winrt::Windows::Internal::Shell::IFocusSessionComponent,long (&)(IUnknown *,_GUID const &,_GUID const &,void * *),IServiceProvider *,_GUID const &>(
    &v4,
    IUnknown_QueryService,
    &v6);
  winrt::impl::consume_Windows_Internal_UI_Notifications_IQuietHoursSettingsInteropStatics<winrt::Windows::Internal::UI::Notifications::IQuietHoursSettingsInteropStatics>::GetDefault(
    &v4,
    a2);
  winrt::com_ptr<winrt::impl::IWeakReferenceSource>::~com_ptr<winrt::impl::IWeakReferenceSource>(&v4);
  wil::com_ptr_t<Windows::Security::Credentials::IWebAccount,wil::err_exception_policy>::~com_ptr_t<Windows::Security::Credentials::IWebAccount,wil::err_exception_policy>(&v5);
  return a2;
}

```

## disassembly

```asm
0x18002e730  mov     [rsp+arg_8], rdx
0x18002e735  push    rbx
0x18002e736  sub     rsp, 30h
0x18002e73a  mov     rbx, rdx
0x18002e73d  lea     rcx, [rsp+38h+arg_10]
0x18002e742  call    ??$CoCreateInstance@UIServiceProvider@@Uerr_exception_policy@wil@@@wil@@YA?AV?$com_ptr_t@UIServiceProvider@@Uerr_exception_policy@wil@@@0@AEBU_GUID@@K@Z; wil::CoCreateInstance<IServiceProvider,wil::err_exception_policy>(_GUID const &,ulong)
0x18002e747  nop
0x18002e748  mov     rax, [rsp+38h+arg_10]
0x18002e74d  mov     [rsp+38h+arg_18], rax
0x18002e752  lea     r8, [rsp+38h+arg_18]
0x18002e757  mov     rdx, cs:__imp_IUnknown_QueryService
0x18002e75e  lea     rcx, [rsp+38h+arg_8]
0x18002e763  call    ??$capture@UIFocusSessionComponent@Shell@Internal@Windows@winrt@@A6AJPEAUIUnknown@@AEBU_GUID@@1PEAPEAX@ZPEAUIServiceProvider@@AEBU7@@winrt@@YA?AUIFocusSessionComponent@Shell@Internal@Windows@0@A6AJPEAUIUnknown@@AEBU_GUID@@1PEAPEAX@Z$$QEAPEAUIServiceProvider@@1@Z; winrt::capture<winrt::Windows::Internal::Shell::IFocusSessionComponent,long (&)(IUnknown *,_GUID const &,_GUID const &,void * *),IServiceProvider *,_GUID const &>(long (&)(IUnknown *,_GUID const &,_GUID const &,void * *),IServiceProvider * &&,_GUID const &)
0x18002e768  nop
0x18002e769  mov     rdx, rbx
0x18002e76c  lea     rcx, [rsp+38h+arg_8]
0x18002e771  call    ?GetDefault@?$consume_Windows_Internal_UI_Notifications_IQuietHoursSettingsInteropStatics@UIQuietHoursSettingsInteropStatics@Notifications@UI@Internal@Windows@winrt@@@impl@winrt@@QEBA@XZ; winrt::impl::consume_Windows_Internal_UI_Notifications_IQuietHoursSettingsInteropStatics<winrt::Windows::Internal::UI::Notifications::IQuietHoursSettingsInteropStatics>::GetDefault(void)
0x18002e776  nop
0x18002e777  lea     rcx, [rsp+38h+arg_8]
0x18002e77c  call    ??1?$com_ptr@UIWeakReferenceSource@impl@winrt@@@winrt@@QEAA@XZ; winrt::com_ptr<winrt::impl::IWeakReferenceSource>::~com_ptr<winrt::impl::IWeakReferenceSource>(void)
0x18002e781  nop
0x18002e782  lea     rcx, [rsp+38h+arg_10]
0x18002e787  call    ??1?$com_ptr_t@UIWebAccount@Credentials@Security@Windows@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Security::Credentials::IWebAccount,wil::err_exception_policy>::~com_ptr_t<Windows::Security::Credentials::IWebAccount,wil::err_exception_policy>(void)
0x18002e78c  mov     rax, rbx
0x18002e78f  add     rsp, 30h
0x18002e793  pop     rbx
0x18002e794  retn
```
