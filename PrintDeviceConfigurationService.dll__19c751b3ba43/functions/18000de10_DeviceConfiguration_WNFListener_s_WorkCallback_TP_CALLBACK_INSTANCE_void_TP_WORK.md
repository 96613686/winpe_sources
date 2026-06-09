# DeviceConfiguration::WNFListener::s_WorkCallback(_TP_CALLBACK_INSTANCE *,void *,_TP_WORK *)

- ea: `0x18000de10`
- end: `0x18000ded3`
- name: `?s_WorkCallback@WNFListener@DeviceConfiguration@@CAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_WORK@@@Z`
- size: `195`
- prototype: `void __fastcall(PTP_CALLBACK_INSTANCE Instance, _DWORD *Context, PTP_WORK Work, const char *)`
- caller_count: `0`
- callee_count: `6`
- tags: `registry_config, service_task, installer_update`

## callees

- `0x18000d268`
- `0x18000d89c`
- `0x18000de10`
- `0x18000ed18`
- `0x180011c38`
- `0x1800121c0`

## string_xrefs

- `0x18000de7a`: `printscan\print\spooler\configuration\deviceconfigurationservice\lib\wnflistener.cpp`
- `0x18000deaf`: `printscan\print\spooler\configuration\deviceconfigurationservice\lib\wnflistener.cpp`
- `0x18000dea0`: `ConfigureAndInstallPrinters failed!`
- `0x18000de69`: `ConfigureWindowsProtectedPrint failed!`
- `0x18000de43`: `RepairWindowsProtectedPrintConfiguration failed!`

## pseudocode

```c
void __fastcall DeviceConfiguration::WNFListener::s_WorkCallback(
        PTP_CALLBACK_INSTANCE Instance,
        _DWORD *Context,
        PTP_WORK Work,
        const char *a4)
{
  int v4; // ecx
  int v5; // ecx
  unsigned int v6; // eax
  __int64 v7; // rdx
  unsigned int v8; // eax
  const char *v9; // [rsp+20h] [rbp-18h]
  const char *v10; // [rsp+28h] [rbp-10h]
  wil::details::in1diag3 *retaddr; // [rsp+38h] [rbp+0h]
  _DWORD *v12; // [rsp+48h] [rbp+10h] BYREF

  try
  {
    if ( Context )
    {
      v12 = Context;
      v4 = Context[2];
      if ( !v4 )
      {
        v8 = DeviceConfiguration::DeviceManager::ConfigureAndInstallPrinters(**(RTL_SRWLOCK ***)Context);
        wil::details::in1diag3::Throw_IfFailedMsg(
          retaddr,
          (void *)0x82,
          (unsigned int)"printscan\\print\\spooler\\configuration\\deviceconfigurationservice\\lib\\wnflistener.cpp",
          (const char *)v8,
          (int)"ConfigureAndInstallPrinters failed!",
          v10);
        goto LABEL_10;
      }
      v5 = v4 - 1;
      if ( v5 )
      {
        if ( v5 != 1 )
        {
LABEL_10:
          std::unique_ptr<DeviceConfiguration::NotificationContext>::~unique_ptr<DeviceConfiguration::NotificationContext>(&v12);
          return;
        }
        v6 = DeviceConfiguration::ConfigurationManager::RepairWindowsProtectedPrintConfiguration(*(DeviceConfiguration::ConfigurationManager **)(*(_QWORD *)Context + 24LL));
        v9 = "RepairWindowsProtectedPrintConfiguration failed!";
        v7 = 178;
      }
      else
      {
        v6 = DeviceConfiguration::ConfigurationManager::ConfigureWindowsProtectedPrint(
               *(_QWORD *)(*(_QWORD *)Context + 24LL),
               (unsigned int)Context[3],
               (unsigned int)Context[4]);
        v9 = "ConfigureWindowsProtectedPrint failed!";
        v7 = 154;
      }
      wil::details::in1diag3::Throw_IfFailedMsg(
        retaddr,
        (void *)v7,
        (unsigned int)"printscan\\print\\spooler\\configuration\\deviceconfigurationservice\\lib\\wnflistener.cpp",
        (const char *)v6,
        (int)v9,
        v10);
      goto LABEL_10;
    }
  }
  catch ( ... )
  {
    wil::details::in1diag3::Log_CaughtException(
      retaddr,
      (void *)0xEF,
      (unsigned int)"printscan\\print\\spooler\\configuration\\deviceconfigurationservice\\lib\\wnflistener.cpp",
      a4);
  }
}

```

## disassembly

```asm
0x18000de10  sub     rsp, 38h
0x18000de14  test    rdx, rdx
0x18000de17  jz      loc_18000DECC
0x18000de1d  mov     [rsp+38h+arg_8], rdx
0x18000de22  mov     ecx, [rdx+8]
0x18000de25  test    ecx, ecx
0x18000de27  jz      short loc_18000DE90
0x18000de29  sub     ecx, 1
0x18000de2c  jz      short loc_18000DE56
0x18000de2e  cmp     ecx, 1
0x18000de31  jnz     loc_18000DEC1
0x18000de37  mov     rcx, [rdx]
0x18000de3a  mov     rcx, [rcx+18h]; this
0x18000de3e  call    ?RepairWindowsProtectedPrintConfiguration@ConfigurationManager@DeviceConfiguration@@QEAAJXZ; DeviceConfiguration::ConfigurationManager::RepairWindowsProtectedPrintConfiguration(void)
0x18000de43  lea     rdx, aRepairwindowsp; "RepairWindowsProtectedPrintConfiguratio"...
0x18000de4a  mov     qword ptr [rsp+38h+var_18], rdx
0x18000de4f  mov     edx, 0B2h
0x18000de54  jmp     short loc_18000DE7A
0x18000de56  mov     rcx, [rdx]
0x18000de59  mov     r8d, [rdx+10h]
0x18000de5d  mov     edx, [rdx+0Ch]
0x18000de60  mov     rcx, [rcx+18h]
0x18000de64  call    ?ConfigureWindowsProtectedPrint@ConfigurationManager@DeviceConfiguration@@QEAAJW4WindowsProtectedPrintConfigurationState@PrintCore@@W4WindowsProtectedPrintConfigurationSource@4@@Z; DeviceConfiguration::ConfigurationManager::ConfigureWindowsProtectedPrint(PrintCore::WindowsProtectedPrintConfigurationState,PrintCore::WindowsProtectedPrintConfigurationSource)
0x18000de69  lea     rdx, aConfigurewindo; "ConfigureWindowsProtectedPrint failed!"
0x18000de70  mov     qword ptr [rsp+38h+var_18], rdx; int
0x18000de75  mov     edx, 9Ah; void *
0x18000de7a  lea     r8, aPrintscanPrint; "printscan\\print\\spooler\\configuratio"...
0x18000de81  mov     r9d, eax; char *
0x18000de84  mov     rcx, [rsp+38h]; this
0x18000de89  call    ?Throw_IfFailedMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Throw_IfFailedMsg(void *,uint,char const *,long,char const *,...)
0x18000de8e  jmp     short loc_18000DEC1
0x18000de90  mov     rcx, [rdx]
0x18000de93  mov     rcx, [rcx]; this
0x18000de96  call    ?ConfigureAndInstallPrinters@DeviceManager@DeviceConfiguration@@QEAAJXZ; DeviceConfiguration::DeviceManager::ConfigureAndInstallPrinters(void)
0x18000de9b  mov     rcx, [rsp+38h]; this
0x18000dea0  lea     rdx, aConfigureandin; "ConfigureAndInstallPrinters failed!"
0x18000dea7  mov     qword ptr [rsp+38h+var_18], rdx; int
0x18000deac  mov     r9d, eax; char *
0x18000deaf  lea     r8, aPrintscanPrint; "printscan\\print\\spooler\\configuratio"...
0x18000deb6  mov     edx, 82h; void *
0x18000debb  call    ?Throw_IfFailedMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Throw_IfFailedMsg(void *,uint,char const *,long,char const *,...)
0x18000dec0  nop
0x18000dec1  lea     rcx, [rsp+38h+arg_8]
0x18000dec6  call    ??1?$unique_ptr@UNotificationContext@DeviceConfiguration@@U?$default_delete@UNotificationContext@DeviceConfiguration@@@std@@@std@@QEAA@XZ; std::unique_ptr<DeviceConfiguration::NotificationContext>::~unique_ptr<DeviceConfiguration::NotificationContext>(void)
0x18000decb  nop
0x18000decc  jmp     short $+2
0x18000dece  add     rsp, 38h
0x18000ded2  retn
```
