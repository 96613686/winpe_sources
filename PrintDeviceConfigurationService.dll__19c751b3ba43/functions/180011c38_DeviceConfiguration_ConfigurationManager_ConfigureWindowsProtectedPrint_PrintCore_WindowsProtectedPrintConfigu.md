# DeviceConfiguration::ConfigurationManager::ConfigureWindowsProtectedPrint(PrintCore::WindowsProtectedPrintConfigurationState,PrintCore::WindowsProtectedPrintConfigurationSource)

- ea: `0x180011c38`
- end: `0x180011dcf`
- name: `?ConfigureWindowsProtectedPrint@ConfigurationManager@DeviceConfiguration@@QEAAJW4WindowsProtectedPrintConfigurationState@PrintCore@@W4WindowsProtectedPrintConfigurationSource@4@@Z`
- size: `407`
- prototype: `__int64 __fastcall(char *, int, unsigned int)`
- caller_count: `1`
- callee_count: `14`
- tags: `registry_config, service_task, installer_update`

## callers

- `0x18000de10`

## callees

- `0x1800047d0`
- `0x180004e44`
- `0x18000aeac`
- `0x18000c06c`
- `0x18000ece4`
- `0x18000fa2c`
- `0x180011c38`
- `0x1800124f8`
- `0x180012a50`
- `0x180012df8`
- `0x180013274`
- `0x1800132d8`
- `0x180013534`
- `0x1800140d4`

## string_xrefs

- `0x180011c79`: `printscan\print\spooler\configuration\deviceconfigurationservice\lib\configurationmanager.cpp`
- `0x180011dbc`: `printscan\print\spooler\configuration\deviceconfigurationservice\lib\configurationmanager.cpp`
- `0x180011cc5`: `DeviceConfiguration::ConfigurationManager::ConfigureWindowsProtectedPrint`
- `0x180011ce1`: `DeviceConfiguration::ConfigurationManager::ConfigureWindowsProtectedPrint`
- `0x180011cf1`: `DeviceConfiguration::ConfigurationManager::ConfigureWindowsProtectedPrint`
- `0x180011d13`: `DeviceConfiguration::ConfigurationManager::ConfigureWindowsProtectedPrint`
- `0x180011db0`: `Invalid Windows Protected Print configuration state!`

## pseudocode

```c
__int64 __fastcall DeviceConfiguration::ConfigurationManager::ConfigureWindowsProtectedPrint(
        char *a1,
        int a2,
        unsigned int a3)
{
  int v6; // ebx
  DeviceConfiguration::ConfigurationManager *v7; // rcx
  DeviceConfiguration::ConfigurationManager *v8; // rcx
  unsigned int v9; // ebx
  unsigned int v10; // edx
  __int64 v11; // r8
  DeviceConfiguration::ConfigurationManager *v12; // rcx
  DeviceConfiguration::ConfigurationManager *v13; // rcx
  DeviceConfiguration::ConfigurationManager *v14; // rcx
  DeviceConfiguration::ConfigurationManager *v15; // rcx
  const char *v16; // r9
  __int64 result; // rax
  const char *v18; // r9
  char *v19; // [rsp+28h] [rbp-10h]
  const char *v20; // [rsp+30h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+38h] [rbp+0h]
  int v22; // [rsp+40h] [rbp+8h] BYREF

  DeviceConfiguration::PrintDeviceConfigurationService::ResetStopTimer(g_printDeviceConfigurationService);
  try
  {
    wil::details::in1diag3::Throw_Win32IfMsg(
      retaddr,
      (void *)0x4D,
      (unsigned int)"printscan\\print\\spooler\\configuration\\deviceconfigurationservice\\lib\\configurationmanager.cpp",
      (const char *)0x45B,
      *a1,
      (bool)"Shutdown in progress!",
      v20);
    DeviceConfiguration::PrintDeviceConfigurationService::AcquireSpoolerLock(g_printDeviceConfigurationService, &v22);
    if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Print_PlatformStabilizationFixes_2026_Wave1>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_Print_PlatformStabilizationFixes_2026_Wave1>::GetImpl'::`2'::impl) )
    {
      if ( !a2 )
      {
        DeviceConfigurationTelemetry::WriteDbgTraceInfo(
          "DeviceConfiguration::ConfigurationManager::ConfigureWindowsProtectedPrint",
          L"Disabling Windows Protected Print!");
        v9 = 0;
        if ( DeviceConfiguration::ConfigurationManager::_IsWindowsProtectedPrintEnabled(v12) )
          v9 = DeviceConfiguration::ConfigurationManager::_DisableWindowsProtectedPrint(v8);
        v10 = v9;
        goto LABEL_14;
      }
      v6 = a2 - 1;
      if ( v6 )
      {
        if ( v6 != 1 )
        {
          v18 = (const char *)(unsigned int)wil::verify_hresult<long>(2147942487LL);
          wil::details::in1diag3::Throw_HrMsg(
            retaddr,
            (void *)0x76,
            (unsigned int)"printscan\\print\\spooler\\configuration\\deviceconfigurationservice\\lib\\configurationmanager.cpp",
            v18,
            (int)"Invalid Windows Protected Print configuration state!",
            v19);
        }
        DeviceConfigurationTelemetry::WriteDbgTraceInfo(
          "DeviceConfiguration::ConfigurationManager::ConfigureWindowsProtectedPrint",
          L"Resetting Windows Protected Print!");
        v9 = DeviceConfiguration::ConfigurationManager::_ResetWindowsProtectedPrint(v7);
        v10 = ~v9;
        v11 = v9;
        goto LABEL_15;
      }
    }
    else if ( a2 != 1 )
    {
      DeviceConfigurationTelemetry::WriteDbgTraceInfo(
        "DeviceConfiguration::ConfigurationManager::ConfigureWindowsProtectedPrint",
        L"Disabling Windows Protected Print!");
      v9 = 0;
      if ( DeviceConfiguration::ConfigurationManager::_IsWindowsProtectedPrintEnabled(v14) )
        v9 = DeviceConfiguration::ConfigurationManager::_DisableWindowsProtectedPrint(v15);
      DeviceConfiguration::ConfigurationManager::_PublishModeUpdateNotification(v15, v9 >> 31, v9);
      goto LABEL_19;
    }
    DeviceConfigurationTelemetry::WriteDbgTraceInfo(
      "DeviceConfiguration::ConfigurationManager::ConfigureWindowsProtectedPrint",
      L"Enabling Windows Protected Print!");
    v9 = 0;
    if ( !DeviceConfiguration::ConfigurationManager::_IsWindowsProtectedPrintEnabled(v13) )
      v9 = DeviceConfiguration::ConfigurationManager::_EnableWindowsProtectedPrint(v8, a3);
    v10 = ~v9;
LABEL_14:
    v11 = v9;
LABEL_15:
    DeviceConfiguration::ConfigurationManager::_PublishModeUpdateNotification(v8, v10 >> 31, v11);
LABEL_19:
    wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&void LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&void LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>(&v22);
    result = v9;
  }
  catch ( ... )
  {
    return (unsigned int)wil::details::in1diag3::Return_CaughtException(
                           retaddr,
                           (void *)0x97,
                           (unsigned int)"printscan\\print\\spooler\\configuration\\deviceconfigurationservice\\lib\\conf"
                                         "igurationmanager.cpp",
                           v16);
  }
  return result;
}

```

## disassembly

```asm
0x180011c38  mov     [rsp+arg_8], rbx
0x180011c3d  mov     [rsp+arg_10], rsi
0x180011c42  push    rdi; char *
0x180011c43  sub     rsp, 30h
0x180011c47  mov     edi, r8d
0x180011c4a  mov     ebx, edx
0x180011c4c  mov     rsi, rcx
0x180011c4f  mov     rcx, cs:?g_printDeviceConfigurationService@@3V?$unique_ptr@VPrintDeviceConfigurationService@DeviceConfiguration@@U?$default_delete@VPrintDeviceConfigurationService@DeviceConfiguration@@@std@@@std@@A; this
0x180011c56  call    ?ResetStopTimer@PrintDeviceConfigurationService@DeviceConfiguration@@QEAAXXZ; DeviceConfiguration::PrintDeviceConfigurationService::ResetStopTimer(void)
0x180011c5b  mov     al, [rsi]
0x180011c5d  nop
0x180011c5e  mov     rcx, [rsp+38h]; this
0x180011c63  lea     rdx, aShutdownInProg; "Shutdown in progress!"
0x180011c6a  mov     [rsp+38h+var_10], rdx; char *
0x180011c6f  mov     [rsp+38h+var_18], al; char
0x180011c73  mov     r9d, 45Bh; char *
0x180011c79  lea     r8, aPrintscanPrint_2; "printscan\\print\\spooler\\configuratio"...
0x180011c80  mov     edx, 4Dh ; 'M'; void *
0x180011c85  call    ?Throw_Win32IfMsg@in1diag3@details@wil@@YA_NPEAXIPEBDK_N1ZZ; wil::details::in1diag3::Throw_Win32IfMsg(void *,uint,char const *,ulong,bool,char const *,...)
0x180011c8a  lea     rdx, [rsp+38h+arg_0]
0x180011c8f  mov     rcx, cs:?g_printDeviceConfigurationService@@3V?$unique_ptr@VPrintDeviceConfigurationService@DeviceConfiguration@@U?$default_delete@VPrintDeviceConfigurationService@DeviceConfiguration@@@std@@@std@@A; std::unique_ptr<DeviceConfiguration::PrintDeviceConfigurationService> g_printDeviceConfigurationService
0x180011c96  call    ?AcquireSpoolerLock@PrintDeviceConfigurationService@DeviceConfiguration@@QEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_CRITICAL_SECTION@@P6AXPEAU1@@Z$1?LeaveCriticalSection@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@XZ; DeviceConfiguration::PrintDeviceConfigurationService::AcquireSpoolerLock(void)
0x180011c9b  nop
0x180011c9c  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_Print_PlatformStabilizationFixes_2026_Wave1@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_Print_PlatformStabilizationFixes_2026_Wave1@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Print_PlatformStabilizationFixes_2026_Wave1> `wil::Feature<__WilFeatureTraits_Feature_Print_PlatformStabilizationFixes_2026_Wave1>::GetImpl(void)'::`2'::impl
0x180011ca3  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_Print_PlatformStabilizationFixes_2026_Wave1@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Print_PlatformStabilizationFixes_2026_Wave1>::__private_IsEnabled(void)
0x180011ca8  test    al, al
0x180011caa  jz      short loc_180011D13
0x180011cac  test    ebx, ebx
0x180011cae  jz      short loc_180011CEA
0x180011cb0  sub     ebx, 1
0x180011cb3  jz      short loc_180011CE1
0x180011cb5  cmp     ebx, 1
0x180011cb8  jnz     loc_180011D9E
0x180011cbe  lea     rdx, aResettingWindo; "Resetting Windows Protected Print!"
0x180011cc5  lea     rcx, aDeviceconfigur_17; "DeviceConfiguration::ConfigurationManag"...
0x180011ccc  call    ?WriteDbgTraceInfo@DeviceConfigurationTelemetry@@SAXPEADPEAGZZ; DeviceConfigurationTelemetry::WriteDbgTraceInfo(char *,ushort *,...)
0x180011cd1  call    ?_ResetWindowsProtectedPrint@ConfigurationManager@DeviceConfiguration@@AEAAJXZ; DeviceConfiguration::ConfigurationManager::_ResetWindowsProtectedPrint(void)
0x180011cd6  mov     ebx, eax
0x180011cd8  mov     edx, eax
0x180011cda  not     edx
0x180011cdc  mov     r8d, eax
0x180011cdf  jmp     short loc_180011D46
0x180011ce1  lea     rcx, aDeviceconfigur_17; "DeviceConfiguration::ConfigurationManag"...
0x180011ce8  jmp     short loc_180011D1F
0x180011cea  lea     rdx, aDisablingWindo; "Disabling Windows Protected Print!"
0x180011cf1  lea     rcx, aDeviceconfigur_17; "DeviceConfiguration::ConfigurationManag"...
0x180011cf8  call    ?WriteDbgTraceInfo@DeviceConfigurationTelemetry@@SAXPEADPEAGZZ; DeviceConfigurationTelemetry::WriteDbgTraceInfo(char *,ushort *,...)
0x180011cfd  xor     ebx, ebx
0x180011cff  call    ?_IsWindowsProtectedPrintEnabled@ConfigurationManager@DeviceConfiguration@@AEAA_NXZ; DeviceConfiguration::ConfigurationManager::_IsWindowsProtectedPrintEnabled(void)
0x180011d04  test    al, al
0x180011d06  jz      short loc_180011D0F
0x180011d08  call    ?_DisableWindowsProtectedPrint@ConfigurationManager@DeviceConfiguration@@AEAAJXZ; DeviceConfiguration::ConfigurationManager::_DisableWindowsProtectedPrint(void)
0x180011d0d  mov     ebx, eax
0x180011d0f  mov     edx, ebx
0x180011d11  jmp     short loc_180011D43
0x180011d13  lea     rcx, aDeviceconfigur_17; "DeviceConfiguration::ConfigurationManag"...
0x180011d1a  cmp     ebx, 1
0x180011d1d  jnz     short loc_180011D50
0x180011d1f  lea     rdx, aEnablingWindow; "Enabling Windows Protected Print!"
0x180011d26  call    ?WriteDbgTraceInfo@DeviceConfigurationTelemetry@@SAXPEADPEAGZZ; DeviceConfigurationTelemetry::WriteDbgTraceInfo(char *,ushort *,...)
0x180011d2b  xor     ebx, ebx
0x180011d2d  call    ?_IsWindowsProtectedPrintEnabled@ConfigurationManager@DeviceConfiguration@@AEAA_NXZ; DeviceConfiguration::ConfigurationManager::_IsWindowsProtectedPrintEnabled(void)
0x180011d32  test    al, al
0x180011d34  jnz     short loc_180011D3F
0x180011d36  mov     edx, edi
0x180011d38  call    ?_EnableWindowsProtectedPrint@ConfigurationManager@DeviceConfiguration@@AEAAJW4WindowsProtectedPrintConfigurationSource@PrintCore@@@Z; DeviceConfiguration::ConfigurationManager::_EnableWindowsProtectedPrint(PrintCore::WindowsProtectedPrintConfigurationSource)
0x180011d3d  mov     ebx, eax
0x180011d3f  mov     edx, ebx
0x180011d41  not     edx
0x180011d43  mov     r8d, ebx
0x180011d46  shr     edx, 1Fh
0x180011d49  call    ?_PublishModeUpdateNotification@ConfigurationManager@DeviceConfiguration@@AEAAXW4WindowsProtectedPrintConfigurationState@PrintCore@@J@Z; DeviceConfiguration::ConfigurationManager::_PublishModeUpdateNotification(PrintCore::WindowsProtectedPrintConfigurationState,long)
0x180011d4e  jmp     short loc_180011D7C
0x180011d50  lea     rdx, aDisablingWindo; "Disabling Windows Protected Print!"
0x180011d57  call    ?WriteDbgTraceInfo@DeviceConfigurationTelemetry@@SAXPEADPEAGZZ; DeviceConfigurationTelemetry::WriteDbgTraceInfo(char *,ushort *,...)
0x180011d5c  xor     ebx, ebx
0x180011d5e  call    ?_IsWindowsProtectedPrintEnabled@ConfigurationManager@DeviceConfiguration@@AEAA_NXZ; DeviceConfiguration::ConfigurationManager::_IsWindowsProtectedPrintEnabled(void)
0x180011d63  test    al, al
0x180011d65  jz      short loc_180011D6E
0x180011d67  call    ?_DisableWindowsProtectedPrint@ConfigurationManager@DeviceConfiguration@@AEAAJXZ; DeviceConfiguration::ConfigurationManager::_DisableWindowsProtectedPrint(void)
0x180011d6c  mov     ebx, eax
0x180011d6e  mov     edx, ebx
0x180011d70  shr     edx, 1Fh
0x180011d73  mov     r8d, ebx
0x180011d76  call    ?_PublishModeUpdateNotification@ConfigurationManager@DeviceConfiguration@@AEAAXW4WindowsProtectedPrintConfigurationState@PrintCore@@J@Z; DeviceConfiguration::ConfigurationManager::_PublishModeUpdateNotification(PrintCore::WindowsProtectedPrintConfigurationState,long)
0x180011d7b  nop
0x180011d7c  lea     rcx, [rsp+38h+arg_0]
0x180011d81  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_CRITICAL_SECTION@@P6AXPEAU1@@Z$1?LeaveCriticalSection@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>(void)
0x180011d86  mov     eax, ebx
0x180011d88  jmp     short loc_180011D8E
0x180011d8a  mov     eax, [rsp+38h+arg_0]
0x180011d8e  mov     rbx, [rsp+38h+arg_8]
0x180011d93  mov     rsi, [rsp+38h+arg_10]
0x180011d98  add     rsp, 30h
0x180011d9c  pop     rdi
0x180011d9d  retn
0x180011d9e  mov     ecx, 80070057h
0x180011da3  call    ??$verify_hresult@J@wil@@YAJJ@Z; wil::verify_hresult<long>(long)
0x180011da8  mov     r9d, eax; char *
0x180011dab  mov     rcx, [rsp+38h]; this
0x180011db0  lea     rax, aInvalidWindows; "Invalid Windows Protected Print configu"...
0x180011db7  mov     qword ptr [rsp+38h+var_18], rax; int
0x180011dbc  lea     r8, aPrintscanPrint_2; "printscan\\print\\spooler\\configuratio"...
0x180011dc3  mov     edx, 76h ; 'v'; void *
0x180011dc8  call    ?Throw_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Throw_HrMsg(void *,uint,char const *,long,char const *,...)
```
