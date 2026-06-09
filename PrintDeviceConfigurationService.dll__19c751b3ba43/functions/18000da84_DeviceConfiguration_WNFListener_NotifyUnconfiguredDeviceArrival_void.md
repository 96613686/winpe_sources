# DeviceConfiguration::WNFListener::_NotifyUnconfiguredDeviceArrival(void)

- ea: `0x18000da84`
- end: `0x18000db2c`
- name: `?_NotifyUnconfiguredDeviceArrival@WNFListener@DeviceConfiguration@@AEAAXXZ`
- size: `168`
- prototype: `void __fastcall(DeviceConfiguration::WNFListener *__hidden this)`
- caller_count: `2`
- callee_count: `9`
- tags: `registry_config, service_task, installer_update`

## callers

- `0x18000d3d0`
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
- `0x18000da84`

## string_xrefs

- `0x18000da96`: `Unconfigured printers are available. Starting configuration and installation process...`
- `0x18000da9d`: `DeviceConfiguration::WNFListener::_NotifyUnconfiguredDeviceArrival`
- `0x18000db07`: `DeviceConfiguration::WNFListener::_NotifyUnconfiguredDeviceArrival`
- `0x18000db00`: `Failed to create work for device arrival notification!`

## pseudocode

```c
void __fastcall DeviceConfiguration::WNFListener::_NotifyUnconfiguredDeviceArrival(
        DeviceConfiguration::WNFListener *this)
{
  DeviceConfiguration::NotificationContext *v2; // rbx
  __int64 CurrentModule; // rax
  const char *v4; // r9
  unsigned int v5; // edx
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]
  HMODULE phModule; // [rsp+38h] [rbp+10h] BYREF

  DeviceConfigurationTelemetry::WriteDbgTraceInfo(
    "DeviceConfiguration::WNFListener::_NotifyUnconfiguredDeviceArrival",
    L"Unconfigured printers are available. Starting configuration and installation process...");
  try
  {
    v2 = (DeviceConfiguration::NotificationContext *)operator new(0x20u);
    *((_QWORD *)v2 + 2) = 0;
    *((_QWORD *)v2 + 3) = 0;
    *((_QWORD *)v2 + 1) = 0;
    *(_QWORD *)v2 = this;
    CurrentModule = DeviceConfiguration::GetCurrentModule(&phModule);
    wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&int FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>>::operator=(
      (char *)v2 + 24,
      CurrentModule);
    wil::details::unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&int FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&int FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>(&phModule);
    if ( (int)DeviceConfiguration::WNFListener::_CreateWorkForNotification(this, v2) < 0 )
    {
      DeviceConfigurationTelemetry::WriteDbgTraceError(
        "DeviceConfiguration::WNFListener::_NotifyUnconfiguredDeviceArrival",
        L"Failed to create work for device arrival notification!");
      DeviceConfiguration::NotificationContext::`scalar deleting destructor'(v2, v5);
    }
  }
  catch ( ... )
  {
    wil::details::in1diag3::Log_CaughtException(
      retaddr,
      (void *)0x7E,
      (unsigned int)"printscan\\print\\spooler\\configuration\\deviceconfigurationservice\\lib\\wnflistener.cpp",
      v4);
  }
}

```

## disassembly

```asm
0x18000da84  mov     [rsp+arg_0], rbx
0x18000da89  mov     [rsp+arg_10], rsi
0x18000da8e  push    rdi
0x18000da8f  sub     rsp, 20h
0x18000da93  mov     rdi, rcx
0x18000da96  lea     rdx, aUnconfiguredPr; "Unconfigured printers are available. St"...
0x18000da9d  lea     rcx, aDeviceconfigur_16; "DeviceConfiguration::WNFListener::_Noti"...
0x18000daa4  call    ?WriteDbgTraceInfo@DeviceConfigurationTelemetry@@SAXPEADPEAGZZ; DeviceConfigurationTelemetry::WriteDbgTraceInfo(char *,ushort *,...)
0x18000daa9  mov     ecx, 20h ; ' '; Size
0x18000daae  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000dab3  mov     rbx, rax
0x18000dab6  mov     qword ptr [rax+10h], 0
0x18000dabe  mov     qword ptr [rax+18h], 0
0x18000dac6  mov     qword ptr [rax+8], 0
0x18000dace  mov     [rax], rdi
0x18000dad1  lea     rcx, [rsp+28h+phModule]; phModule
0x18000dad6  call    ?GetCurrentModule@DeviceConfiguration@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHINSTANCE__@@P6AHPEAU1@@Z$1?FreeLibrary@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@XZ; DeviceConfiguration::GetCurrentModule(void)
0x18000dadb  mov     rdx, rax
0x18000dade  lea     rcx, [rbx+18h]
0x18000dae2  call    ??4?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHINSTANCE__@@P6AHPEAU1@@Z$1?FreeLibrary@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@QEAAAEAV01@$$QEAV01@@Z; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>>::operator=(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>> &&)
0x18000dae7  lea     rcx, [rsp+28h+phModule]
0x18000daec  call    ??1?$unique_storage@U?$resource_policy@PEAUHINSTANCE__@@P6AHPEAU1@@Z$1?FreeLibrary@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>(void)
0x18000daf1  mov     rdx, rbx; void *
0x18000daf4  mov     rcx, rdi; this
0x18000daf7  call    ?_CreateWorkForNotification@WNFListener@DeviceConfiguration@@AEAAJPEAX@Z; DeviceConfiguration::WNFListener::_CreateWorkForNotification(void *)
0x18000dafc  test    eax, eax
0x18000dafe  jns     short loc_18000DB1C
0x18000db00  lea     rdx, aFailedToCreate_2; "Failed to create work for device arriva"...
0x18000db07  lea     rcx, aDeviceconfigur_16; "DeviceConfiguration::WNFListener::_Noti"...
0x18000db0e  call    ?WriteDbgTraceError@DeviceConfigurationTelemetry@@SAXPEADPEAGZZ; DeviceConfigurationTelemetry::WriteDbgTraceError(char *,ushort *,...)
0x18000db13  mov     rcx, rbx; this
0x18000db16  call    ??_GNotificationContext@DeviceConfiguration@@QEAAPEAXI@Z; DeviceConfiguration::NotificationContext::`scalar deleting destructor'(uint)
0x18000db1b  nop
0x18000db1c  mov     rbx, [rsp+28h+arg_0]
0x18000db21  mov     rsi, [rsp+28h+arg_10]
0x18000db26  add     rsp, 20h
0x18000db2a  pop     rdi
0x18000db2b  retn
```
