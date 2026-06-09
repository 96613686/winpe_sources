# DeviceConfiguration::WNFListener::_NotifyWindowsProtectedPrintUpgradeRepair(void)

- ea: `0x18000dbe4`
- end: `0x18000dc8c`
- name: `?_NotifyWindowsProtectedPrintUpgradeRepair@WNFListener@DeviceConfiguration@@AEAAXXZ`
- size: `168`
- prototype: `void __fastcall(DeviceConfiguration::WNFListener *__hidden this)`
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config, service_task, installer_update`

## callers

- `0x18000d668`

## callees

- `0x1800024cc`
- `0x18000ae04`
- `0x18000aeac`
- `0x18000d284`
- `0x18000d314`
- `0x18000d47c`
- `0x18000d500`
- `0x18000d928`
- `0x18000dbe4`

## string_xrefs

- `0x18000dbf6`: `Windows Protected Print configuration needs to be repaired after upgrade. Starting the repair process...`
- `0x18000dbfd`: `DeviceConfiguration::WNFListener::_NotifyWindowsProtectedPrintUpgradeRepair`
- `0x18000dc67`: `DeviceConfiguration::WNFListener::_NotifyWindowsProtectedPrintUpgradeRepair`
- `0x18000dc60`: `Failed to create work for upgrade notification!`

## pseudocode

```c
void __fastcall DeviceConfiguration::WNFListener::_NotifyWindowsProtectedPrintUpgradeRepair(
        DeviceConfiguration::WNFListener *this)
{
  DeviceConfiguration::NotificationContext *v2; // rbx
  __int64 CurrentModule; // rax
  const char *v4; // r9
  unsigned int v5; // edx
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]
  HMODULE phModule; // [rsp+38h] [rbp+10h] BYREF

  DeviceConfigurationTelemetry::WriteDbgTraceInfo(
    "DeviceConfiguration::WNFListener::_NotifyWindowsProtectedPrintUpgradeRepair",
    L"Windows Protected Print configuration needs to be repaired after upgrade. Starting the repair process...");
  try
  {
    v2 = (DeviceConfiguration::NotificationContext *)operator new(0x20u);
    *((_QWORD *)v2 + 2) = 0;
    *((_QWORD *)v2 + 3) = 0;
    *((_QWORD *)v2 + 1) = 2;
    *(_QWORD *)v2 = this;
    CurrentModule = DeviceConfiguration::GetCurrentModule(&phModule);
    wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&int FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>>::operator=(
      (char *)v2 + 24,
      CurrentModule);
    wil::details::unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&int FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&int FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>(&phModule);
    if ( (int)DeviceConfiguration::WNFListener::_CreateWorkForNotification(this, v2) < 0 )
    {
      DeviceConfigurationTelemetry::WriteDbgTraceError(
        "DeviceConfiguration::WNFListener::_NotifyWindowsProtectedPrintUpgradeRepair",
        L"Failed to create work for upgrade notification!");
      DeviceConfiguration::NotificationContext::`scalar deleting destructor'(v2, v5);
    }
  }
  catch ( ... )
  {
    wil::details::in1diag3::Log_CaughtException(
      retaddr,
      (void *)0xAE,
      (unsigned int)"printscan\\print\\spooler\\configuration\\deviceconfigurationservice\\lib\\wnflistener.cpp",
      v4);
  }
}

```

## disassembly

```asm
0x18000dbe4  mov     [rsp+arg_0], rbx
0x18000dbe9  mov     [rsp+arg_10], rsi
0x18000dbee  push    rdi
0x18000dbef  sub     rsp, 20h
0x18000dbf3  mov     rdi, rcx
0x18000dbf6  lea     rdx, aWindowsProtect_0; "Windows Protected Print configuration n"...
0x18000dbfd  lea     rcx, aDeviceconfigur_23; "DeviceConfiguration::WNFListener::_Noti"...
0x18000dc04  call    ?WriteDbgTraceInfo@DeviceConfigurationTelemetry@@SAXPEADPEAGZZ; DeviceConfigurationTelemetry::WriteDbgTraceInfo(char *,ushort *,...)
0x18000dc09  mov     ecx, 20h ; ' '; Size
0x18000dc0e  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000dc13  mov     rbx, rax
0x18000dc16  mov     qword ptr [rax+10h], 0
0x18000dc1e  mov     qword ptr [rax+18h], 0
0x18000dc26  mov     qword ptr [rax+8], 2
0x18000dc2e  mov     [rax], rdi
0x18000dc31  lea     rcx, [rsp+28h+phModule]; phModule
0x18000dc36  call    ?GetCurrentModule@DeviceConfiguration@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHINSTANCE__@@P6AHPEAU1@@Z$1?FreeLibrary@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@XZ; DeviceConfiguration::GetCurrentModule(void)
0x18000dc3b  mov     rdx, rax
0x18000dc3e  lea     rcx, [rbx+18h]
0x18000dc42  call    ??4?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHINSTANCE__@@P6AHPEAU1@@Z$1?FreeLibrary@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@QEAAAEAV01@$$QEAV01@@Z; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>>::operator=(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>> &&)
0x18000dc47  lea     rcx, [rsp+28h+phModule]
0x18000dc4c  call    ??1?$unique_storage@U?$resource_policy@PEAUHINSTANCE__@@P6AHPEAU1@@Z$1?FreeLibrary@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>(void)
0x18000dc51  mov     rdx, rbx; void *
0x18000dc54  mov     rcx, rdi; this
0x18000dc57  call    ?_CreateWorkForNotification@WNFListener@DeviceConfiguration@@AEAAJPEAX@Z; DeviceConfiguration::WNFListener::_CreateWorkForNotification(void *)
0x18000dc5c  test    eax, eax
0x18000dc5e  jns     short loc_18000DC7C
0x18000dc60  lea     rdx, aFailedToCreate_1; "Failed to create work for upgrade notif"...
0x18000dc67  lea     rcx, aDeviceconfigur_23; "DeviceConfiguration::WNFListener::_Noti"...
0x18000dc6e  call    ?WriteDbgTraceError@DeviceConfigurationTelemetry@@SAXPEADPEAGZZ; DeviceConfigurationTelemetry::WriteDbgTraceError(char *,ushort *,...)
0x18000dc73  mov     rcx, rbx; this
0x18000dc76  call    ??_GNotificationContext@DeviceConfiguration@@QEAAPEAXI@Z; DeviceConfiguration::NotificationContext::`scalar deleting destructor'(uint)
0x18000dc7b  nop
0x18000dc7c  mov     rbx, [rsp+28h+arg_0]
0x18000dc81  mov     rsi, [rsp+28h+arg_10]
0x18000dc86  add     rsp, 20h
0x18000dc8a  pop     rdi
0x18000dc8b  retn
```
