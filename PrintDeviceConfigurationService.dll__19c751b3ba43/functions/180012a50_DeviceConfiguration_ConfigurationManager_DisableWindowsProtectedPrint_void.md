# DeviceConfiguration::ConfigurationManager::_DisableWindowsProtectedPrint(void)

- ea: `0x180012a50`
- end: `0x180012c6a`
- name: `?_DisableWindowsProtectedPrint@ConfigurationManager@DeviceConfiguration@@AEAAJXZ`
- size: `538`
- prototype: `__int64 __fastcall(DeviceConfiguration::ConfigurationManager *__hidden this)`
- caller_count: `2`
- callee_count: `13`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x180011c38`
- `0x180013534`

## callees

- `0x18000c158`
- `0x18000d8e4`
- `0x18000ea48`
- `0x180011be8`
- `0x1800124ac`
- `0x180012530`
- `0x180012a50`
- `0x180013600`
- `0x180013914`
- `0x180013a30`
- `0x180013b24`
- `0x180013c3c`
- `0x180013c98`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180012b46`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180012b46`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x180012b79`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x180012bac`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x180012b79`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x180012bac`
- `api-ms-win-core-registry-l2-1-0!RegOpenKeyTransactedW` at `0x180012afb`
- `api-ms-win-core-registry-l2-1-0!RegOpenKeyTransactedW` at `0x180012afb`
- `ktmw32!CommitTransaction` at `0x180012c02`
- `ktmw32!CommitTransaction` at `0x180012c02`
- `ktmw32!CreateTransaction` at `0x180012a85`
- `ktmw32!CreateTransaction` at `0x180012a85`

## string_xrefs

- `0x180012aa7`: `printscan\print\spooler\configuration\deviceconfigurationservice\lib\configurationmanager.cpp`
- `0x180012a98`: `Failed to open transaction!`
- `0x180012b09`: `RegOpenKeyTransacted (WPP Key) failed!`
- `0x180012c0d`: `CommitTransaction failed!`
- `0x180012b54`: `RegSetValueEx (WPP Enablement Mode) failed!`
- `0x180012b87`: `RegDeleteValue (WPP Enabled By) failed!`
- `0x180012bba`: `RegDeleteValue (WPP Enabled Timestamp) failed!`

## pseudocode

```c
__int64 __fastcall DeviceConfiguration::ConfigurationManager::_DisableWindowsProtectedPrint(
        DeviceConfiguration::ConfigurationManager *this)
{
  char *Transaction; // rbx
  const char *v2; // r9
  unsigned int v3; // eax
  unsigned int v4; // eax
  unsigned int v5; // eax
  DeviceConfiguration::ConfigurationManager *v6; // rcx
  DeviceConfiguration::ConfigurationManager *v7; // rcx
  DeviceConfiguration::ConfigurationManager *v8; // rcx
  DeviceConfiguration::ConfigurationManager *v9; // rcx
  unsigned int v10; // eax
  DeviceConfiguration::ConfigurationManager *v11; // rcx
  const unsigned __int16 *v12; // rdx
  const unsigned __int16 *v13; // r8
  const char *v14; // r9
  __int64 result; // rax
  const char *Timeout; // [rsp+28h] [rbp-30h]
  const char *Timeouta; // [rsp+28h] [rbp-30h]
  const char *Timeoutb; // [rsp+28h] [rbp-30h]
  const char *Timeoutc; // [rsp+28h] [rbp-30h]
  const char *Timeoutd; // [rsp+28h] [rbp-30h]
  const char *Timeoute; // [rsp+28h] [rbp-30h]
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+0h]
  DeviceConfiguration::ConfigurationManager *Data; // [rsp+60h] [rbp+8h] BYREF
  HKEY phkResult; // [rsp+68h] [rbp+10h] BYREF
  HKEY v25; // [rsp+70h] [rbp+18h] BYREF
  char *v26; // [rsp+78h] [rbp+20h] BYREF

  Data = this;
  try
  {
    DeviceConfiguration::ConfigurationManager::_UpdateSpoolerMitigations(this, 0);
    Transaction = (char *)CreateTransaction(0, 0, 0, 0, 0, 0, 0);
    v26 = Transaction;
    wil::details::in1diag3::Throw_IfHandleInvalidMsg(
      retaddr,
      (void *)0x135,
      (unsigned int)"printscan\\print\\spooler\\configuration\\deviceconfigurationservice\\lib\\configurationmanager.cpp",
      Transaction,
      "Failed to open transaction!",
      Timeout);
    LODWORD(Data) = 0;
    phkResult = 0;
    v2 = (const char *)(unsigned int)RegOpenKeyTransactedW(
                                       HKEY_LOCAL_MACHINE,
                                       L"Software\\Policies\\Microsoft\\Windows NT\\Printers\\WPP",
                                       0,
                                       0xF003Fu,
                                       &phkResult,
                                       Transaction,
                                       0);
    wil::details::in1diag3::Throw_IfWin32ErrorMsg(
      retaddr,
      (void *)0x13A,
      (unsigned int)"printscan\\print\\spooler\\configuration\\deviceconfigurationservice\\lib\\configurationmanager.cpp",
      v2,
      (unsigned int)"RegOpenKeyTransacted (WPP Key) failed!",
      Timeouta);
    v3 = RegSetValueExW(phkResult, L"WindowsProtectedPrintMode", 0, 4u, (const BYTE *)&Data, 4u);
    wil::details::in1diag3::Throw_IfWin32ErrorMsg(
      retaddr,
      (void *)0x13B,
      (unsigned int)"printscan\\print\\spooler\\configuration\\deviceconfigurationservice\\lib\\configurationmanager.cpp",
      (const char *)v3,
      (unsigned int)"RegSetValueEx (WPP Enablement Mode) failed!",
      Timeoutb);
    v4 = RegDeleteValueW(phkResult, L"EnabledBy");
    wil::details::in1diag3::Throw_IfWin32ErrorMsg(
      retaddr,
      (void *)0x13E,
      (unsigned int)"printscan\\print\\spooler\\configuration\\deviceconfigurationservice\\lib\\configurationmanager.cpp",
      (const char *)v4,
      (unsigned int)"RegDeleteValue (WPP Enabled By) failed!",
      Timeoutc);
    v5 = RegDeleteValueW(phkResult, L"EnabledTimestamp");
    wil::details::in1diag3::Throw_IfWin32ErrorMsg(
      retaddr,
      (void *)0x13F,
      (unsigned int)"printscan\\print\\spooler\\configuration\\deviceconfigurationservice\\lib\\configurationmanager.cpp",
      (const char *)v5,
      (unsigned int)"RegDeleteValue (WPP Enabled Timestamp) failed!",
      Timeoutd);
    DeviceConfiguration::ConfigurationManager::_UpdateOobeConfigCompleteFlag(v6, Transaction, 0);
    DeviceConfiguration::ConfigurationManager::_UpdateSpoolerService(v7, Transaction, 0);
    DeviceConfiguration::ConfigurationManager::_UpdatePrintFilterPipelineSvc(v8, Transaction, 0);
    DeviceConfiguration::ConfigurationManager::_UpdateSpoolerImageMitigationOptions(v9, Transaction, 0);
    v10 = CommitTransaction(Transaction);
    wil::details::in1diag3::Throw_IfWin32BoolFalseMsg(
      retaddr,
      (void *)0x156,
      (unsigned int)"printscan\\print\\spooler\\configuration\\deviceconfigurationservice\\lib\\configurationmanager.cpp",
      (const char *)v10,
      (int)"CommitTransaction failed!",
      Timeoute);
    DeviceConfiguration::ConfigurationManager::_RestartSpoolerService(v11);
    v25 = HKEY_LOCAL_MACHINE;
    PrintCore::RegHelpers::SetDwordValue(&v25, v12, v13, 0);
    wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&phkResult);
    wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&v26);
    result = 0;
  }
  catch ( ... )
  {
    return (unsigned int)wil::details::in1diag3::Return_CaughtException(
                           retaddr,
                           (void *)0x160,
                           (unsigned int)"printscan\\print\\spooler\\configuration\\deviceconfigurationservice\\lib\\conf"
                                         "igurationmanager.cpp",
                           v14);
  }
  return result;
}

```

## disassembly

```asm
0x180012a50  mov     [rsp+Data], rcx
0x180012a55  push    rbx
0x180012a56  push    rdi
0x180012a57  sub     rsp, 48h
0x180012a5b  xor     edx, edx; bool
0x180012a5d  call    ?_UpdateSpoolerMitigations@ConfigurationManager@DeviceConfiguration@@AEAAX_N@Z; DeviceConfiguration::ConfigurationManager::_UpdateSpoolerMitigations(bool)
0x180012a62  mov     [rsp+58h+Description], 0; Description
0x180012a6b  mov     [rsp+58h+Timeout], 0; char *
0x180012a73  mov     [rsp+58h+IsolationFlags], 0; IsolationFlags
0x180012a7b  xor     r9d, r9d; IsolationLevel
0x180012a7e  xor     r8d, r8d; CreateOptions
0x180012a81  xor     edx, edx; UOW
0x180012a83  xor     ecx, ecx; lpTransactionAttributes
0x180012a85  call    cs:__imp_CreateTransaction
0x180012a8b  mov     rbx, rax
0x180012a8e  mov     [rsp+58h+arg_18], rax
0x180012a93  mov     rcx, [rsp+58h]; this
0x180012a98  lea     rax, aFailedToOpenTr; "Failed to open transaction!"
0x180012a9f  mov     qword ptr [rsp+58h+IsolationFlags], rax; void *
0x180012aa4  mov     r9, rbx; char *
0x180012aa7  lea     rdi, aPrintscanPrint_2; "printscan\\print\\spooler\\configuratio"...
0x180012aae  mov     r8, rdi; unsigned int
0x180012ab1  mov     edx, 135h; void *
0x180012ab6  call    ?Throw_IfHandleInvalidMsg@in1diag3@details@wil@@YAPEAXPEAXIPEBD01ZZ; wil::details::in1diag3::Throw_IfHandleInvalidMsg(void *,uint,char const *,void *,char const *,...)
0x180012abb  mov     dword ptr [rsp+58h+Data], 0
0x180012ac3  mov     [rsp+58h+phkResult], 0
0x180012acc  mov     [rsp+58h+Description], 0; pExtendedParemeter
0x180012ad5  mov     qword ptr [rsp+58h+Timeout], rbx; char *
0x180012ada  lea     rax, [rsp+58h+phkResult]
0x180012adf  mov     qword ptr [rsp+58h+IsolationFlags], rax; phkResult
0x180012ae4  mov     r9d, 0F003Fh; samDesired
0x180012aea  xor     r8d, r8d; ulOptions
0x180012aed  lea     rdx, SubKey; "Software\\Policies\\Microsoft\\Windows "...
0x180012af4  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180012afb  call    cs:__imp_RegOpenKeyTransactedW
0x180012b01  mov     r9d, eax; char *
0x180012b04  mov     rcx, [rsp+58h]; this
0x180012b09  lea     rax, aRegopenkeytran_3; "RegOpenKeyTransacted (WPP Key) failed!"
0x180012b10  mov     qword ptr [rsp+58h+IsolationFlags], rax; unsigned int
0x180012b15  mov     r8, rdi; unsigned int
0x180012b18  mov     edx, 13Ah; void *
0x180012b1d  call    ?Throw_IfWin32ErrorMsg@in1diag3@details@wil@@YAKPEAXIPEBDK1ZZ; wil::details::in1diag3::Throw_IfWin32ErrorMsg(void *,uint,char const *,ulong,char const *,...)
0x180012b22  mov     r9d, 4; dwType
0x180012b28  mov     [rsp+58h+Timeout], r9d; char *
0x180012b2d  lea     rax, [rsp+58h+Data]
0x180012b32  mov     qword ptr [rsp+58h+IsolationFlags], rax; lpData
0x180012b37  xor     r8d, r8d; Reserved
0x180012b3a  lea     rdx, aWindowsprotect_2; "WindowsProtectedPrintMode"
0x180012b41  mov     rcx, [rsp+58h+phkResult]; hKey
0x180012b46  call    cs:__imp_RegSetValueExW
0x180012b4c  mov     r9d, eax; char *
0x180012b4f  mov     rcx, [rsp+58h]; this
0x180012b54  lea     rax, aRegsetvalueexW_3; "RegSetValueEx (WPP Enablement Mode) fai"...
0x180012b5b  mov     qword ptr [rsp+58h+IsolationFlags], rax; unsigned int
0x180012b60  mov     r8, rdi; unsigned int
0x180012b63  mov     edx, 13Bh; void *
0x180012b68  call    ?Throw_IfWin32ErrorMsg@in1diag3@details@wil@@YAKPEAXIPEBDK1ZZ; wil::details::in1diag3::Throw_IfWin32ErrorMsg(void *,uint,char const *,ulong,char const *,...)
0x180012b6d  lea     rdx, aEnabledby; "EnabledBy"
0x180012b74  mov     rcx, [rsp+58h+phkResult]; hKey
0x180012b79  call    cs:__imp_RegDeleteValueW
0x180012b7f  mov     r9d, eax; char *
0x180012b82  mov     rcx, [rsp+58h]; this
0x180012b87  lea     rax, aRegdeletevalue_2; "RegDeleteValue (WPP Enabled By) failed!"
0x180012b8e  mov     qword ptr [rsp+58h+IsolationFlags], rax; unsigned int
0x180012b93  mov     r8, rdi; unsigned int
0x180012b96  mov     edx, 13Eh; void *
0x180012b9b  call    ?Throw_IfWin32ErrorMsg@in1diag3@details@wil@@YAKPEAXIPEBDK1ZZ; wil::details::in1diag3::Throw_IfWin32ErrorMsg(void *,uint,char const *,ulong,char const *,...)
0x180012ba0  lea     rdx, aEnabledtimesta; "EnabledTimestamp"
0x180012ba7  mov     rcx, [rsp+58h+phkResult]; hKey
0x180012bac  call    cs:__imp_RegDeleteValueW
0x180012bb2  mov     r9d, eax; char *
0x180012bb5  mov     rcx, [rsp+58h]; this
0x180012bba  lea     rax, aRegdeletevalue_0; "RegDeleteValue (WPP Enabled Timestamp) "...
0x180012bc1  mov     qword ptr [rsp+58h+IsolationFlags], rax; unsigned int
0x180012bc6  mov     r8, rdi; unsigned int
0x180012bc9  mov     edx, 13Fh; void *
0x180012bce  call    ?Throw_IfWin32ErrorMsg@in1diag3@details@wil@@YAKPEAXIPEBDK1ZZ; wil::details::in1diag3::Throw_IfWin32ErrorMsg(void *,uint,char const *,ulong,char const *,...)
0x180012bd3  xor     r8d, r8d; bool
0x180012bd6  mov     rdx, rbx; void *
0x180012bd9  call    ?_UpdateOobeConfigCompleteFlag@ConfigurationManager@DeviceConfiguration@@AEAAXPEAX_N@Z; DeviceConfiguration::ConfigurationManager::_UpdateOobeConfigCompleteFlag(void *,bool)
0x180012bde  xor     r8d, r8d; bool
0x180012be1  mov     rdx, rbx; void *
0x180012be4  call    ?_UpdateSpoolerService@ConfigurationManager@DeviceConfiguration@@AEAAXPEAX_N@Z; DeviceConfiguration::ConfigurationManager::_UpdateSpoolerService(void *,bool)
0x180012be9  xor     r8d, r8d; bool
0x180012bec  mov     rdx, rbx; void *
0x180012bef  call    ?_UpdatePrintFilterPipelineSvc@ConfigurationManager@DeviceConfiguration@@AEAAXPEAX_N@Z; DeviceConfiguration::ConfigurationManager::_UpdatePrintFilterPipelineSvc(void *,bool)
0x180012bf4  xor     r8d, r8d; bool
0x180012bf7  mov     rdx, rbx; void *
0x180012bfa  call    ?_UpdateSpoolerImageMitigationOptions@ConfigurationManager@DeviceConfiguration@@AEAAXPEAX_N@Z; DeviceConfiguration::ConfigurationManager::_UpdateSpoolerImageMitigationOptions(void *,bool)
0x180012bff  mov     rcx, rbx; TransactionHandle
0x180012c02  call    cs:__imp_CommitTransaction
0x180012c08  mov     rcx, [rsp+58h]; this
0x180012c0d  lea     rdx, aCommittransact_0; "CommitTransaction failed!"
0x180012c14  mov     qword ptr [rsp+58h+IsolationFlags], rdx; int
0x180012c19  mov     r9d, eax; char *
0x180012c1c  mov     r8, rdi; unsigned int
0x180012c1f  mov     edx, 156h; void *
0x180012c24  call    ?Throw_IfWin32BoolFalseMsg@in1diag3@details@wil@@YAHPEAXIPEBDH1ZZ; wil::details::in1diag3::Throw_IfWin32BoolFalseMsg(void *,uint,char const *,int,char const *,...)
0x180012c29  call    ?_RestartSpoolerService@ConfigurationManager@DeviceConfiguration@@AEAAXXZ; DeviceConfiguration::ConfigurationManager::_RestartSpoolerService(void)
0x180012c2e  mov     [rsp+58h+arg_10], 0FFFFFFFF80000002h
0x180012c37  xor     r9d, r9d; unsigned int
0x180012c3a  lea     rcx, [rsp+58h+arg_10]; HKEY *
0x180012c3f  call    ?SetDwordValue@RegHelpers@PrintCore@@SAJAEBQEAUHKEY__@@PEBG1K@Z; PrintCore::RegHelpers::SetDwordValue(HKEY__ * const &,ushort const *,ushort const *,ulong)
0x180012c44  nop
0x180012c45  lea     rcx, [rsp+58h+phkResult]
0x180012c4a  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x180012c4f  nop
0x180012c50  lea     rcx, [rsp+58h+arg_18]
0x180012c55  call    ??1?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x180012c5a  xor     eax, eax
0x180012c5c  jmp     short loc_180012C62
0x180012c5e  mov     eax, dword ptr [rsp+58h+Data]
0x180012c62  add     rsp, 48h
0x180012c66  pop     rdi
0x180012c67  pop     rbx
0x180012c68  retn
```
