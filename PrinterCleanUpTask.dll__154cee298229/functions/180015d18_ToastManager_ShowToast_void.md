# ToastManager::ShowToast(void)

- ea: `0x180015d18`
- end: `0x180015ddb`
- name: `?ShowToast@ToastManager@@QEAAJXZ`
- size: `195`
- prototype: `__int64 __fastcall(ToastManager *__hidden this)`
- caller_count: `3`
- callee_count: `8`
- tags: `service_task`

## callers

- `0x18000d424`
- `0x180011a10`
- `0x180012f8c`

## callees

- `0x18000a2d4`
- `0x18000a360`
- `0x18000d1c0`
- `0x180015920`
- `0x180015b60`
- `0x180015cd4`
- `0x180015d18`
- `0x180015de4`

## string_xrefs

- `0x180015d7f`: `Windows.SystemToast.Print.PrinterCleanupTask`

## pseudocode

```c
__int64 __fastcall ToastManager::ShowToast(ToastManager *this)
{
  const char *v2; // r9
  __int64 result; // rax
  __int64 v4[5]; // [rsp+20h] [rbp-28h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+0h]
  __int64 *v6; // [rsp+58h] [rbp+10h] BYREF
  __int64 v7; // [rsp+60h] [rbp+18h] BYREF
  void (__fastcall *v8)(__int64, __int64 *); // [rsp+68h] [rbp+20h] BYREF

  try
  {
    v8 = (void (__fastcall *)(__int64, __int64 *))&qword_180022818;
    _InterlockedIncrement64(&qword_180022818);
    if ( winrt::impl::factory_cache_entry_v<winrt::Windows::UI::Notifications::ToastNotificationManager,winrt::Windows::UI::Notifications::IToastNotificationManagerStatics5> )
    {
      winrt::impl::consume_Windows_UI_Notifications_IToastNotificationManagerStatics5<winrt::Windows::UI::Notifications::IToastNotificationManagerStatics5>::GetDefault(
        (__int64 **)&winrt::impl::factory_cache_entry_v<winrt::Windows::UI::Notifications::ToastNotificationManager,winrt::Windows::UI::Notifications::IToastNotificationManagerStatics5>,
        &v6);
      _InterlockedDecrement64(&qword_180022818);
    }
    else
    {
      _InterlockedDecrement64(&qword_180022818);
      v8 = (void (__fastcall *)(__int64, __int64 *))_lambda_35086ee1531464b88cd6c8965568282d_::_lambda_invoker_cdecl_;
      winrt::impl::factory_cache_entry<winrt::Windows::UI::Notifications::ToastNotificationManager,winrt::Windows::UI::Notifications::IToastNotificationManagerStatics5>::call<winrt::Windows::UI::Notifications::ToastNotificationManagerForUser (*)(winrt::Windows::UI::Notifications::IToastNotificationManagerStatics5 const &)>(
        (void (__fastcall ***)(_QWORD, __int64 *, __int64 **))this,
        (__int64)&v6,
        &v8);
    }
    winrt::param::hstring::hstring((winrt::param::hstring *)v4, L"Windows.SystemToast.Print.PrinterCleanupTask");
    winrt::impl::consume_Windows_UI_Notifications_IToastNotificationManagerForUser<winrt::Windows::UI::Notifications::IToastNotificationManagerForUser>::CreateToastNotifier(
      &v6,
      &v7,
      v4);
    winrt::Windows::Devices::Enumeration::IDeviceInformation::~IDeviceInformation((winrt::Windows::Devices::Enumeration::IDeviceInformation *)&v6);
    winrt::impl::consume_Windows_UI_Notifications_IToastNotifier<winrt::Windows::UI::Notifications::IToastNotifier>::Show(
      &v7,
      this);
    PrinterCleanUpTelemetry::StalePrintJobCleanupToastShown();
    winrt::Windows::Devices::Enumeration::IDeviceInformation::~IDeviceInformation((winrt::Windows::Devices::Enumeration::IDeviceInformation *)&v7);
    result = 0;
  }
  catch ( ... )
  {
    return (unsigned int)wil::details::in1diag3::Return_CaughtException(
                           retaddr,
                           (void *)0x1B,
                           (int)"printscan\\print\\shared\\printercleanuptask\\lib\\toastmanager.cpp",
                           v2);
  }
  return result;
}

```

## disassembly

```asm
0x180015d18  push    rbx
0x180015d1a  sub     rsp, 40h
0x180015d1e  mov     rbx, rcx
0x180015d21  lea     rax, qword_180022818
0x180015d28  mov     [rsp+48h+arg_18], rax
0x180015d2d  lock inc cs:qword_180022818
0x180015d35  cmp     cs:??$factory_cache_entry_v@UToastNotificationManager@Notifications@UI@Windows@winrt@@UIToastNotificationManagerStatics5@2345@@impl@winrt@@3U?$factory_cache_entry@UToastNotificationManager@Notifications@UI@Windows@winrt@@UIToastNotificationManagerStatics5@2345@@12@A, 0; factory_cache_entry<winrt::Windows::UI::Notifications::ToastNotificationManager,winrt::Windows::UI::Notifications::IToastNotificationManagerStatics5>::winrt::factory_cache_entry<winrt::Windows::UI::Notifications::ToastNotificationManager,winrt::Windows::UI::Notifications::IToastNotificationManagerStatics5> winrt::impl::factory_cache_entry_v<winrt::Windows::UI::Notifications::ToastNotificationManager,winrt::Windows::UI::Notifications::IToastNotificationManagerStatics5>
0x180015d3d  jz      short loc_180015D5B
0x180015d3f  lea     rdx, [rsp+48h+arg_8]
0x180015d44  lea     rcx, ??$factory_cache_entry_v@UToastNotificationManager@Notifications@UI@Windows@winrt@@UIToastNotificationManagerStatics5@2345@@impl@winrt@@3U?$factory_cache_entry@UToastNotificationManager@Notifications@UI@Windows@winrt@@UIToastNotificationManagerStatics5@2345@@12@A; factory_cache_entry<winrt::Windows::UI::Notifications::ToastNotificationManager,winrt::Windows::UI::Notifications::IToastNotificationManagerStatics5>::winrt::factory_cache_entry<winrt::Windows::UI::Notifications::ToastNotificationManager,winrt::Windows::UI::Notifications::IToastNotificationManagerStatics5> winrt::impl::factory_cache_entry_v<winrt::Windows::UI::Notifications::ToastNotificationManager,winrt::Windows::UI::Notifications::IToastNotificationManagerStatics5>
0x180015d4b  call    ?GetDefault@?$consume_Windows_UI_Notifications_IToastNotificationManagerStatics5@UIToastNotificationManagerStatics5@Notifications@UI@Windows@winrt@@@impl@winrt@@QEBA@XZ; winrt::impl::consume_Windows_UI_Notifications_IToastNotificationManagerStatics5<winrt::Windows::UI::Notifications::IToastNotificationManagerStatics5>::GetDefault(void)
0x180015d50  nop
0x180015d51  lock dec cs:qword_180022818
0x180015d59  jmp     short loc_180015D7F
0x180015d5b  lock dec cs:qword_180022818
0x180015d63  lea     rax, ?_lambda_invoker_cdecl_@_lambda_35086ee1531464b88cd6c8965568282d_@@CA@AEBUIToastNotificationManagerStatics5@Notifications@UI@Windows@winrt@@@Z; _lambda_35086ee1531464b88cd6c8965568282d_::_lambda_invoker_cdecl_(winrt::Windows::UI::Notifications::IToastNotificationManagerStatics5 const &)
0x180015d6a  mov     [rsp+48h+arg_18], rax
0x180015d6f  lea     r8, [rsp+48h+arg_18]
0x180015d74  lea     rdx, [rsp+48h+arg_8]
0x180015d79  call    ??$call@P6A?AUToastNotificationManagerForUser@Notifications@UI@Windows@winrt@@AEBUIToastNotificationManagerStatics5@2345@@Z@?$factory_cache_entry@UToastNotificationManager@Notifications@UI@Windows@winrt@@UIToastNotificationManagerStatics5@2345@@impl@winrt@@QEAA?A_P$$QEAP6A?AUToastNotificationManagerForUser@Notifications@UI@Windows@2@AEBUIToastNotificationManagerStatics5@4562@@Z@Z
0x180015d7e  nop
0x180015d7f  lea     rdx, aWindowsSystemt; "Windows.SystemToast.Print.PrinterCleanu"...
0x180015d86  lea     rcx, [rsp+48h+var_28]; this
0x180015d8b  call    ??0hstring@param@winrt@@QEAA@QEBG@Z; winrt::param::hstring::hstring(ushort const * const)
0x180015d90  lea     r8, [rsp+48h+var_28]
0x180015d95  lea     rdx, [rsp+48h+arg_10]
0x180015d9a  lea     rcx, [rsp+48h+arg_8]
0x180015d9f  call    ?CreateToastNotifier@?$consume_Windows_UI_Notifications_IToastNotificationManagerForUser@UIToastNotificationManagerForUser@Notifications@UI@Windows@winrt@@@impl@winrt@@QEBA@AEBUhstring@param@3@@Z; winrt::impl::consume_Windows_UI_Notifications_IToastNotificationManagerForUser<winrt::Windows::UI::Notifications::IToastNotificationManagerForUser>::CreateToastNotifier(winrt::param::hstring const &)
0x180015da4  nop
0x180015da5  lea     rcx, [rsp+48h+arg_8]; this
0x180015daa  call    ??1IDeviceInformation@Enumeration@Devices@Windows@winrt@@QEAA@XZ; winrt::Windows::Devices::Enumeration::IDeviceInformation::~IDeviceInformation(void)
0x180015daf  mov     rdx, rbx
0x180015db2  lea     rcx, [rsp+48h+arg_10]
0x180015db7  call    ?Show@?$consume_Windows_UI_Notifications_IToastNotifier@UIToastNotifier@Notifications@UI@Windows@winrt@@@impl@winrt@@QEBA@AEBUToastNotification@Notifications@UI@Windows@3@@Z; winrt::impl::consume_Windows_UI_Notifications_IToastNotifier<winrt::Windows::UI::Notifications::IToastNotifier>::Show(winrt::Windows::UI::Notifications::ToastNotification const &)
0x180015dbc  call    ?StalePrintJobCleanupToastShown@PrinterCleanUpTelemetry@@SAXXZ; PrinterCleanUpTelemetry::StalePrintJobCleanupToastShown(void)
0x180015dc1  nop
0x180015dc2  lea     rcx, [rsp+48h+arg_10]; this
0x180015dc7  call    ??1IDeviceInformation@Enumeration@Devices@Windows@winrt@@QEAA@XZ; winrt::Windows::Devices::Enumeration::IDeviceInformation::~IDeviceInformation(void)
0x180015dcc  xor     eax, eax
0x180015dce  jmp     short loc_180015DD4
0x180015dd0  mov     eax, dword ptr [rsp+48h+arg_8]
0x180015dd4  add     rsp, 40h
0x180015dd8  pop     rbx
0x180015dd9  retn
```
