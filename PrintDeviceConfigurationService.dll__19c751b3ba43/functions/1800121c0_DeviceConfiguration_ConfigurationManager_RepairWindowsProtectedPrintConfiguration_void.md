# DeviceConfiguration::ConfigurationManager::RepairWindowsProtectedPrintConfiguration(void)

- ea: `0x1800121c0`
- end: `0x18001237f`
- name: `?RepairWindowsProtectedPrintConfiguration@ConfigurationManager@DeviceConfiguration@@QEAAJXZ`
- size: `447`
- prototype: `__int64 __fastcall(DeviceConfiguration::ConfigurationManager *__hidden this)`
- caller_count: `1`
- callee_count: `17`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x18000de10`

## callees

- `0x180004e44`
- `0x18000c06c`
- `0x18000c158`
- `0x18000d8e4`
- `0x18000ea48`
- `0x18000ece4`
- `0x18000fa2c`
- `0x180011be8`
- `0x1800121c0`
- `0x1800124ac`
- `0x180012530`
- `0x180013600`
- `0x180013914`
- `0x180013a30`
- `0x180013b24`
- `0x180013c3c`
- `0x180013c98`

## import_xrefs

- `api-ms-win-core-registry-l2-1-0!RegOpenKeyTransactedW` at `0x1800122a5`
- `api-ms-win-core-registry-l2-1-0!RegOpenKeyTransactedW` at `0x1800122a5`
- `ktmw32!CommitTransaction` at `0x1800122ff`
- `ktmw32!CommitTransaction` at `0x1800122ff`
- `ktmw32!CreateTransaction` at `0x180012239`
- `ktmw32!CreateTransaction` at `0x180012239`

## string_xrefs

- `0x1800121f3`: `printscan\print\spooler\configuration\deviceconfigurationservice\lib\configurationmanager.cpp`
- `0x18001225b`: `printscan\print\spooler\configuration\deviceconfigurationservice\lib\configurationmanager.cpp`
- `0x1800122bf`: `printscan\print\spooler\configuration\deviceconfigurationservice\lib\configurationmanager.cpp`
- `0x180012319`: `printscan\print\spooler\configuration\deviceconfigurationservice\lib\configurationmanager.cpp`
- `0x18001224c`: `Failed to open transaction!`
- `0x1800122b3`: `RegOpenKeyTransacted (WPP Key) failed!`
- `0x18001230a`: `CommitTransaction failed!`

## pseudocode

```c
__int64 __fastcall DeviceConfiguration::ConfigurationManager::RepairWindowsProtectedPrintConfiguration(
        DeviceConfiguration::ConfigurationManager *this)
{
  char *Transaction; // rbx
  const char *v3; // r9
  DeviceConfiguration::ConfigurationManager *v4; // rcx
  DeviceConfiguration::ConfigurationManager *v5; // rcx
  DeviceConfiguration::ConfigurationManager *v6; // rcx
  DeviceConfiguration::ConfigurationManager *v7; // rcx
  unsigned int v8; // eax
  DeviceConfiguration::ConfigurationManager *v9; // rcx
  DeviceConfiguration::ConfigurationManager *v10; // rcx
  const unsigned __int16 *v11; // rdx
  const unsigned __int16 *v12; // r8
  const char *v13; // r9
  __int64 result; // rax
  const char *Timeout; // [rsp+28h] [rbp-20h]
  const char *Timeouta; // [rsp+28h] [rbp-20h]
  const char *Timeoutb; // [rsp+28h] [rbp-20h]
  const char *Description; // [rsp+30h] [rbp-18h]
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+0h]
  HKEY phkResult; // [rsp+50h] [rbp+8h] BYREF
  HKEY v21; // [rsp+58h] [rbp+10h] BYREF
  char *v22; // [rsp+60h] [rbp+18h] BYREF
  char v23; // [rsp+68h] [rbp+20h] BYREF

  DeviceConfiguration::PrintDeviceConfigurationService::ResetStopTimer(g_printDeviceConfigurationService);
  try
  {
    wil::details::in1diag3::Throw_Win32IfMsg(
      retaddr,
      (void *)0x9F,
      (unsigned int)"printscan\\print\\spooler\\configuration\\deviceconfigurationservice\\lib\\configurationmanager.cpp",
      (const char *)0x45B,
      *(_BYTE *)this,
      (bool)"Shutdown in progress!",
      Description);
    DeviceConfiguration::PrintDeviceConfigurationService::AcquireSpoolerLock(g_printDeviceConfigurationService, &v23);
    Transaction = (char *)CreateTransaction(0, 0, 0, 0, 0, 0, 0);
    v22 = Transaction;
    wil::details::in1diag3::Throw_IfHandleInvalidMsg(
      retaddr,
      (void *)0xA6,
      (unsigned int)"printscan\\print\\spooler\\configuration\\deviceconfigurationservice\\lib\\configurationmanager.cpp",
      Transaction,
      "Failed to open transaction!",
      Timeout);
    phkResult = 0;
    v3 = (const char *)(unsigned int)RegOpenKeyTransactedW(
                                       HKEY_LOCAL_MACHINE,
                                       L"Software\\Policies\\Microsoft\\Windows NT\\Printers\\WPP",
                                       0,
                                       0xF003Fu,
                                       &phkResult,
                                       Transaction,
                                       0);
    wil::details::in1diag3::Throw_IfWin32ErrorMsg(
      retaddr,
      (void *)0xAA,
      (unsigned int)"printscan\\print\\spooler\\configuration\\deviceconfigurationservice\\lib\\configurationmanager.cpp",
      v3,
      (unsigned int)"RegOpenKeyTransacted (WPP Key) failed!",
      Timeouta);
    DeviceConfiguration::ConfigurationManager::_UpdateOobeConfigCompleteFlag(v4, Transaction, 1);
    DeviceConfiguration::ConfigurationManager::_UpdateSpoolerService(v5, Transaction, 1);
    DeviceConfiguration::ConfigurationManager::_UpdatePrintFilterPipelineSvc(v6, Transaction, 1);
    DeviceConfiguration::ConfigurationManager::_UpdateSpoolerImageMitigationOptions(v7, Transaction, 1);
    v8 = CommitTransaction(Transaction);
    wil::details::in1diag3::Throw_IfWin32BoolFalseMsg(
      retaddr,
      (void *)0xB9,
      (unsigned int)"printscan\\print\\spooler\\configuration\\deviceconfigurationservice\\lib\\configurationmanager.cpp",
      (const char *)v8,
      (int)"CommitTransaction failed!",
      Timeoutb);
    DeviceConfiguration::ConfigurationManager::_UpdateSpoolerMitigations(v9, 1);
    DeviceConfiguration::ConfigurationManager::_RestartSpoolerService(v10);
    v21 = HKEY_LOCAL_MACHINE;
    PrintCore::RegHelpers::SetDwordValue(&v21, v11, v12, 1u);
    wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&phkResult);
    wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&v22);
    wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&void LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&void LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>(&v23);
    result = 0;
  }
  catch ( ... )
  {
    return (unsigned int)wil::details::in1diag3::Return_CaughtException(
                           retaddr,
                           (void *)0xC6,
                           (unsigned int)"printscan\\print\\spooler\\configuration\\deviceconfigurationservice\\lib\\conf"
                                         "igurationmanager.cpp",
                           v13);
  }
  return result;
}

```

## disassembly

```asm
0x1800121c0  push    rbx
0x1800121c2  sub     rsp, 40h
0x1800121c6  mov     rbx, rcx
0x1800121c9  mov     rcx, cs:?g_printDeviceConfigurationService@@3V?$unique_ptr@VPrintDeviceConfigurationService@DeviceConfiguration@@U?$default_delete@VPrintDeviceConfigurationService@DeviceConfiguration@@@std@@@std@@A; this
0x1800121d0  call    ?ResetStopTimer@PrintDeviceConfigurationService@DeviceConfiguration@@QEAAXXZ; DeviceConfiguration::PrintDeviceConfigurationService::ResetStopTimer(void)
0x1800121d5  mov     al, [rbx]
0x1800121d7  nop
0x1800121d8  mov     rcx, [rsp+48h]; this
0x1800121dd  lea     rdx, aShutdownInProg; "Shutdown in progress!"
0x1800121e4  mov     qword ptr [rsp+48h+Timeout], rdx; bool
0x1800121e9  mov     byte ptr [rsp+48h+IsolationFlags], al; char
0x1800121ed  mov     r9d, 45Bh; char *
0x1800121f3  lea     r8, aPrintscanPrint_2; "printscan\\print\\spooler\\configuratio"...
0x1800121fa  mov     edx, 9Fh; void *
0x1800121ff  call    ?Throw_Win32IfMsg@in1diag3@details@wil@@YA_NPEAXIPEBDK_N1ZZ; wil::details::in1diag3::Throw_Win32IfMsg(void *,uint,char const *,ulong,bool,char const *,...)
0x180012204  lea     rdx, [rsp+48h+arg_18]
0x180012209  mov     rcx, cs:?g_printDeviceConfigurationService@@3V?$unique_ptr@VPrintDeviceConfigurationService@DeviceConfiguration@@U?$default_delete@VPrintDeviceConfigurationService@DeviceConfiguration@@@std@@@std@@A; std::unique_ptr<DeviceConfiguration::PrintDeviceConfigurationService> g_printDeviceConfigurationService
0x180012210  call    ?AcquireSpoolerLock@PrintDeviceConfigurationService@DeviceConfiguration@@QEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_CRITICAL_SECTION@@P6AXPEAU1@@Z$1?LeaveCriticalSection@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@XZ; DeviceConfiguration::PrintDeviceConfigurationService::AcquireSpoolerLock(void)
0x180012215  nop
0x180012216  mov     [rsp+48h+Description], 0; Description
0x18001221f  mov     [rsp+48h+Timeout], 0; char *
0x180012227  mov     [rsp+48h+IsolationFlags], 0; IsolationFlags
0x18001222f  xor     r9d, r9d; IsolationLevel
0x180012232  xor     r8d, r8d; CreateOptions
0x180012235  xor     edx, edx; UOW
0x180012237  xor     ecx, ecx; lpTransactionAttributes
0x180012239  call    cs:__imp_CreateTransaction
0x18001223f  mov     rbx, rax
0x180012242  mov     [rsp+48h+arg_10], rax
0x180012247  mov     rcx, [rsp+48h]; this
0x18001224c  lea     rax, aFailedToOpenTr; "Failed to open transaction!"
0x180012253  mov     qword ptr [rsp+48h+IsolationFlags], rax; void *
0x180012258  mov     r9, rbx; char *
0x18001225b  lea     r8, aPrintscanPrint_2; "printscan\\print\\spooler\\configuratio"...
0x180012262  mov     edx, 0A6h; void *
0x180012267  call    ?Throw_IfHandleInvalidMsg@in1diag3@details@wil@@YAPEAXPEAXIPEBD01ZZ; wil::details::in1diag3::Throw_IfHandleInvalidMsg(void *,uint,char const *,void *,char const *,...)
0x18001226c  nop
0x18001226d  mov     [rsp+48h+phkResult], 0
0x180012276  mov     [rsp+48h+Description], 0; pExtendedParemeter
0x18001227f  mov     qword ptr [rsp+48h+Timeout], rbx; char *
0x180012284  lea     rax, [rsp+48h+phkResult]
0x180012289  mov     qword ptr [rsp+48h+IsolationFlags], rax; phkResult
0x18001228e  mov     r9d, 0F003Fh; samDesired
0x180012294  xor     r8d, r8d; ulOptions
0x180012297  lea     rdx, SubKey; "Software\\Policies\\Microsoft\\Windows "...
0x18001229e  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1800122a5  call    cs:__imp_RegOpenKeyTransactedW
0x1800122ab  mov     r9d, eax; char *
0x1800122ae  mov     rcx, [rsp+48h]; this
0x1800122b3  lea     rax, aRegopenkeytran_3; "RegOpenKeyTransacted (WPP Key) failed!"
0x1800122ba  mov     qword ptr [rsp+48h+IsolationFlags], rax; unsigned int
0x1800122bf  lea     r8, aPrintscanPrint_2; "printscan\\print\\spooler\\configuratio"...
0x1800122c6  mov     edx, 0AAh; void *
0x1800122cb  call    ?Throw_IfWin32ErrorMsg@in1diag3@details@wil@@YAKPEAXIPEBDK1ZZ; wil::details::in1diag3::Throw_IfWin32ErrorMsg(void *,uint,char const *,ulong,char const *,...)
0x1800122d0  mov     r8b, 1; bool
0x1800122d3  mov     rdx, rbx; void *
0x1800122d6  call    ?_UpdateOobeConfigCompleteFlag@ConfigurationManager@DeviceConfiguration@@AEAAXPEAX_N@Z; DeviceConfiguration::ConfigurationManager::_UpdateOobeConfigCompleteFlag(void *,bool)
0x1800122db  mov     r8b, 1; bool
0x1800122de  mov     rdx, rbx; void *
0x1800122e1  call    ?_UpdateSpoolerService@ConfigurationManager@DeviceConfiguration@@AEAAXPEAX_N@Z; DeviceConfiguration::ConfigurationManager::_UpdateSpoolerService(void *,bool)
0x1800122e6  mov     r8b, 1; bool
0x1800122e9  mov     rdx, rbx; void *
0x1800122ec  call    ?_UpdatePrintFilterPipelineSvc@ConfigurationManager@DeviceConfiguration@@AEAAXPEAX_N@Z; DeviceConfiguration::ConfigurationManager::_UpdatePrintFilterPipelineSvc(void *,bool)
0x1800122f1  mov     r8b, 1; bool
0x1800122f4  mov     rdx, rbx; void *
0x1800122f7  call    ?_UpdateSpoolerImageMitigationOptions@ConfigurationManager@DeviceConfiguration@@AEAAXPEAX_N@Z; DeviceConfiguration::ConfigurationManager::_UpdateSpoolerImageMitigationOptions(void *,bool)
0x1800122fc  mov     rcx, rbx; TransactionHandle
0x1800122ff  call    cs:__imp_CommitTransaction
0x180012305  mov     rcx, [rsp+48h]; this
0x18001230a  lea     rdx, aCommittransact_0; "CommitTransaction failed!"
0x180012311  mov     qword ptr [rsp+48h+IsolationFlags], rdx; int
0x180012316  mov     r9d, eax; char *
0x180012319  lea     r8, aPrintscanPrint_2; "printscan\\print\\spooler\\configuratio"...
0x180012320  mov     edx, 0B9h; void *
0x180012325  call    ?Throw_IfWin32BoolFalseMsg@in1diag3@details@wil@@YAHPEAXIPEBDH1ZZ; wil::details::in1diag3::Throw_IfWin32BoolFalseMsg(void *,uint,char const *,int,char const *,...)
0x18001232a  mov     dl, 1; bool
0x18001232c  call    ?_UpdateSpoolerMitigations@ConfigurationManager@DeviceConfiguration@@AEAAX_N@Z; DeviceConfiguration::ConfigurationManager::_UpdateSpoolerMitigations(bool)
0x180012331  call    ?_RestartSpoolerService@ConfigurationManager@DeviceConfiguration@@AEAAXXZ; DeviceConfiguration::ConfigurationManager::_RestartSpoolerService(void)
0x180012336  mov     [rsp+48h+arg_8], 0FFFFFFFF80000002h
0x18001233f  mov     r9d, 1; unsigned int
0x180012345  lea     rcx, [rsp+48h+arg_8]; HKEY *
0x18001234a  call    ?SetDwordValue@RegHelpers@PrintCore@@SAJAEBQEAUHKEY__@@PEBG1K@Z; PrintCore::RegHelpers::SetDwordValue(HKEY__ * const &,ushort const *,ushort const *,ulong)
0x18001234f  nop
0x180012350  lea     rcx, [rsp+48h+phkResult]
0x180012355  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x18001235a  nop
0x18001235b  lea     rcx, [rsp+48h+arg_10]
0x180012360  call    ??1?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x180012365  nop
0x180012366  lea     rcx, [rsp+48h+arg_18]
0x18001236b  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_CRITICAL_SECTION@@P6AXPEAU1@@Z$1?LeaveCriticalSection@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>(void)
0x180012370  xor     eax, eax
0x180012372  jmp     short loc_180012378
0x180012374  mov     eax, dword ptr [rsp+48h+phkResult]
0x180012378  add     rsp, 40h
0x18001237c  pop     rbx
0x18001237d  retn
```
