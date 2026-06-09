# DeviceConfiguration::WNFListener::_NotifyWindowsProtectedPrintConfigurationChange(PrintCore::_WindowsProtectedPrintNotificationData)

- ea: `0x18000db34`
- end: `0x18000dbde`
- name: `?_NotifyWindowsProtectedPrintConfigurationChange@WNFListener@DeviceConfiguration@@AEAAXU_WindowsProtectedPrintNotificationData@PrintCore@@@Z`
- size: `170`
- prototype: `void *__fastcall(DeviceConfiguration::WNFListener *, __int64)`
- caller_count: `2`
- callee_count: `9`
- tags: `registry_config, service_task`

## callers

- `0x18000d390`
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
- `0x18000db34`

## string_xrefs

- `0x18000db44`: `Windows Protected Print configuration is being changed. Starting the configuration process...`
- `0x18000db4b`: `DeviceConfiguration::WNFListener::_NotifyWindowsProtectedPrintConfigurationChange`
- `0x18000dbbf`: `DeviceConfiguration::WNFListener::_NotifyWindowsProtectedPrintConfigurationChange`
- `0x18000dbb8`: `Failed to create work for configuration notification!`

## pseudocode

```c
void *__fastcall DeviceConfiguration::WNFListener::_NotifyWindowsProtectedPrintConfigurationChange(
        DeviceConfiguration::WNFListener *a1,
        __int64 a2)
{
  _DWORD *v4; // rbx
  __int64 CurrentModule; // rax
  void *result; // rax
  const char *v7; // r9
  unsigned int v8; // edx
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+0h]
  HMODULE phModule; // [rsp+60h] [rbp+18h] BYREF

  DeviceConfigurationTelemetry::WriteDbgTraceInfo(
    "DeviceConfiguration::WNFListener::_NotifyWindowsProtectedPrintConfigurationChange",
    L"Windows Protected Print configuration is being changed. Starting the configuration process...");
  try
  {
    v4 = operator new(0x20u);
    v4[5] = 0;
    *((_QWORD *)v4 + 3) = 0;
    v4[2] = 1;
    *(_QWORD *)v4 = a1;
    v4[3] = *(_DWORD *)(a2 + 4);
    v4[4] = *(_DWORD *)(a2 + 8);
    CurrentModule = DeviceConfiguration::GetCurrentModule(&phModule);
    wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&int FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>>::operator=(
      v4 + 6,
      CurrentModule);
    wil::details::unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&int FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&int FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>(&phModule);
    result = (void *)DeviceConfiguration::WNFListener::_CreateWorkForNotification(a1, v4);
    if ( (int)result < 0 )
    {
      DeviceConfigurationTelemetry::WriteDbgTraceError(
        "DeviceConfiguration::WNFListener::_NotifyWindowsProtectedPrintConfigurationChange",
        L"Failed to create work for configuration notification!");
      result = DeviceConfiguration::NotificationContext::`scalar deleting destructor'(
                 (DeviceConfiguration::NotificationContext *)v4,
                 v8);
    }
  }
  catch ( ... )
  {
    return (void *)wil::details::in1diag3::Log_CaughtException(
                     retaddr,
                     (void *)0x96,
                     (unsigned int)"printscan\\print\\spooler\\configuration\\deviceconfigurationservice\\lib\\wnflistener.cpp",
                     v7);
  }
  return result;
}

```

## disassembly

```asm
0x18000db34  push    rbx
0x18000db36  push    rsi
0x18000db37  push    rdi
0x18000db38  push    r14
0x18000db3a  sub     rsp, 28h
0x18000db3e  mov     rdi, rdx
0x18000db41  mov     rsi, rcx
0x18000db44  lea     rdx, aWindowsProtect; "Windows Protected Print configuration i"...
0x18000db4b  lea     rcx, aDeviceconfigur_1; "DeviceConfiguration::WNFListener::_Noti"...
0x18000db52  call    ?WriteDbgTraceInfo@DeviceConfigurationTelemetry@@SAXPEADPEAGZZ; DeviceConfigurationTelemetry::WriteDbgTraceInfo(char *,ushort *,...)
0x18000db57  mov     ecx, 20h ; ' '; Size
0x18000db5c  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000db61  mov     rbx, rax
0x18000db64  mov     dword ptr [rax+14h], 0
0x18000db6b  mov     qword ptr [rax+18h], 0
0x18000db73  mov     dword ptr [rax+8], 1
0x18000db7a  mov     [rax], rsi
0x18000db7d  mov     edx, [rdi+4]
0x18000db80  mov     [rax+0Ch], edx
0x18000db83  mov     edx, [rdi+8]
0x18000db86  mov     [rax+10h], edx
0x18000db89  lea     rcx, [rsp+48h+phModule]; phModule
0x18000db8e  call    ?GetCurrentModule@DeviceConfiguration@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHINSTANCE__@@P6AHPEAU1@@Z$1?FreeLibrary@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@XZ; DeviceConfiguration::GetCurrentModule(void)
0x18000db93  mov     rdx, rax
0x18000db96  lea     rcx, [rbx+18h]
0x18000db9a  call    ??4?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHINSTANCE__@@P6AHPEAU1@@Z$1?FreeLibrary@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@QEAAAEAV01@$$QEAV01@@Z; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>>::operator=(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>> &&)
0x18000db9f  lea     rcx, [rsp+48h+phModule]
0x18000dba4  call    ??1?$unique_storage@U?$resource_policy@PEAUHINSTANCE__@@P6AHPEAU1@@Z$1?FreeLibrary@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>(void)
0x18000dba9  mov     rdx, rbx; void *
0x18000dbac  mov     rcx, rsi; this
0x18000dbaf  call    ?_CreateWorkForNotification@WNFListener@DeviceConfiguration@@AEAAJPEAX@Z; DeviceConfiguration::WNFListener::_CreateWorkForNotification(void *)
0x18000dbb4  test    eax, eax
0x18000dbb6  jns     short loc_18000DBD4
0x18000dbb8  lea     rdx, aFailedToCreate; "Failed to create work for configuration"...
0x18000dbbf  lea     rcx, aDeviceconfigur_1; "DeviceConfiguration::WNFListener::_Noti"...
0x18000dbc6  call    ?WriteDbgTraceError@DeviceConfigurationTelemetry@@SAXPEADPEAGZZ; DeviceConfigurationTelemetry::WriteDbgTraceError(char *,ushort *,...)
0x18000dbcb  mov     rcx, rbx; this
0x18000dbce  call    ??_GNotificationContext@DeviceConfiguration@@QEAAPEAXI@Z; DeviceConfiguration::NotificationContext::`scalar deleting destructor'(uint)
0x18000dbd3  nop
0x18000dbd4  add     rsp, 28h
0x18000dbd8  pop     r14
0x18000dbda  pop     rdi
0x18000dbdb  pop     rsi
0x18000dbdc  pop     rbx
0x18000dbdd  retn
```
