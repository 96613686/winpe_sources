# DeviceConfiguration::ConfigurationManager::_EnableWindowsProtectedPrint(PrintCore::WindowsProtectedPrintConfigurationSource)

- ea: `0x180012df8`
- end: `0x1800131d3`
- name: `?_EnableWindowsProtectedPrint@ConfigurationManager@DeviceConfiguration@@AEAAJW4WindowsProtectedPrintConfigurationSource@PrintCore@@@Z`
- size: `987`
- prototype: `__int64 __fastcall(__int64, int)`
- caller_count: `2`
- callee_count: `19`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x180011c38`
- `0x180013534`

## callees

- `0x1800047d0`
- `0x18000c158`
- `0x18000d8e4`
- `0x18000ea48`
- `0x180011be8`
- `0x1800124ac`
- `0x1800124f8`
- `0x180012530`
- `0x18001260c`
- `0x180012df8`
- `0x180013360`
- `0x180013600`
- `0x180013914`
- `0x180013a30`
- `0x180013b24`
- `0x180013c3c`
- `0x180013c98`
- `0x180013e50`
- `0x180014114`

## import_xrefs

- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180013035`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180013035`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180012f49`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180012fb2`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180013069`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800130ba`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180012f49`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180012fb2`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180013069`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800130ba`
- `api-ms-win-core-registry-l2-1-0!RegCreateKeyTransactedW` at `0x180012ef5`
- `api-ms-win-core-registry-l2-1-0!RegCreateKeyTransactedW` at `0x180012ef5`
- `ktmw32!CommitTransaction` at `0x180013113`
- `ktmw32!CommitTransaction` at `0x180013113`
- `ktmw32!CreateTransaction` at `0x180012e5a`
- `ktmw32!CreateTransaction` at `0x180012e5a`

## string_xrefs

- `0x180012e7f`: `printscan\print\spooler\configuration\deviceconfigurationservice\lib\configurationmanager.cpp`
- `0x180012e70`: `Failed to open transaction!`
- `0x180013121`: `CommitTransaction failed!`
- `0x180012f06`: `RegCreateKeyTransacted (WPP Key) failed!`
- `0x180012f5a`: `RegSetValueEx (WPP Enablement Mode) failed!`
- `0x180012fc3`: `RegSetValueEx (WPP Enablement Setup) failed!`
- `0x18001307a`: `RegSetValueEx (WPP Enabled By) failed!`
- `0x1800130cb`: `RegSetValueEx (WPP Enabled Timestamp) failed!`

## pseudocode

```c
__int64 __fastcall DeviceConfiguration::ConfigurationManager::_EnableWindowsProtectedPrint(__int64 a1, int a2)
{
  DeviceConfiguration::ConfigurationManager *v3; // rcx
  DeviceConfiguration::ConfigurationManager *v4; // rcx
  char *hTransaction; // rbx
  unsigned int v6; // eax
  unsigned int v7; // eax
  unsigned int v8; // eax
  int v9; // esi
  unsigned int v10; // eax
  unsigned int v11; // eax
  DeviceConfiguration::ConfigurationManager *v12; // rcx
  DeviceConfiguration::ConfigurationManager *v13; // rcx
  DeviceConfiguration::ConfigurationManager *v14; // rcx
  DeviceConfiguration::ConfigurationManager *v15; // rcx
  unsigned int v16; // eax
  DeviceConfiguration::ConfigurationManager *v17; // rcx
  DeviceConfiguration::ConfigurationManager *v18; // rcx
  DeviceConfiguration::ConfigurationManager *v19; // rcx
  const unsigned __int16 *v20; // rdx
  const unsigned __int16 *v21; // r8
  const char *v22; // r9
  __int64 result; // rax
  const char *v24; // r9
  const char *Timeouta; // [rsp+28h] [rbp-70h]
  const char *Timeoutb; // [rsp+28h] [rbp-70h]
  const char *Timeoutc; // [rsp+28h] [rbp-70h]
  const char *Timeout; // [rsp+28h] [rbp-70h]
  const char *Timeoutd; // [rsp+28h] [rbp-70h]
  const char *Timeoute; // [rsp+28h] [rbp-70h]
  const char *Timeoutf; // [rsp+28h] [rbp-70h]
  const char *Timeoutg; // [rsp+28h] [rbp-70h]
  HKEY hKey; // [rsp+60h] [rbp-38h] BYREF
  struct _FILETIME SystemTimeAsFileTime; // [rsp+68h] [rbp-30h] BYREF
  BYTE v35[8]; // [rsp+70h] [rbp-28h] BYREF
  char *v36; // [rsp+78h] [rbp-20h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+98h] [rbp+0h]
  __int64 v38; // [rsp+A0h] [rbp+8h] BYREF
  int Data; // [rsp+B0h] [rbp+18h] BYREF
  __int64 v40; // [rsp+B8h] [rbp+20h] BYREF

  v38 = a1;
  try
  {
    if ( (unsigned __int8)((__int64 (*)(void))wil::details::FeatureImpl<__WilFeatureTraits_Feature_WindowsProtectedPrintSpoolerWorker>::__private_IsEnabled)() )
    {
      DeviceConfiguration::ConfigurationManager::_ChangeSpoolerServiceState(v3, 3u, 1u, 0x10u);
      DeviceConfiguration::ConfigurationManager::_WaitForSpoolerServiceRunning(v4);
    }
    hTransaction = (char *)CreateTransaction(0, 0, 0, 0, 0, 0, 0);
    v36 = hTransaction;
    wil::details::in1diag3::Throw_IfHandleInvalidMsg(
      retaddr,
      (void *)0xDB,
      (unsigned int)"printscan\\print\\spooler\\configuration\\deviceconfigurationservice\\lib\\configurationmanager.cpp",
      hTransaction,
      "Failed to open transaction!",
      Timeouta);
    Data = 1;
    hKey = 0;
    v6 = RegCreateKeyTransactedW(
           HKEY_LOCAL_MACHINE,
           L"Software\\Policies\\Microsoft\\Windows NT\\Printers\\WPP",
           0,
           0,
           0,
           0xF003Fu,
           0,
           &hKey,
           0,
           hTransaction,
           0);
    wil::details::in1diag3::Throw_IfWin32ErrorMsg(
      retaddr,
      (void *)0xE0,
      (unsigned int)"printscan\\print\\spooler\\configuration\\deviceconfigurationservice\\lib\\configurationmanager.cpp",
      (const char *)v6,
      (unsigned int)"RegCreateKeyTransacted (WPP Key) failed!",
      Timeoutb);
    v7 = RegSetValueExW(hKey, L"WindowsProtectedPrintMode", 0, 4u, (const BYTE *)&Data, 4u);
    wil::details::in1diag3::Throw_IfWin32ErrorMsg(
      retaddr,
      (void *)0xE1,
      (unsigned int)"printscan\\print\\spooler\\configuration\\deviceconfigurationservice\\lib\\configurationmanager.cpp",
      (const char *)v7,
      (unsigned int)"RegSetValueEx (WPP Enablement Mode) failed!",
      Timeoutc);
    if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_WindowsProtectedPrintSpoolerWorker>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_WindowsProtectedPrintSpoolerWorker>::GetImpl'::`2'::impl) )
    {
      LODWORD(v40) = 1;
      v8 = RegSetValueExW(hKey, L"WindowsProtectedPrintSetup", 0, 4u, (const BYTE *)&v40, 4u);
      wil::details::in1diag3::Throw_IfWin32ErrorMsg(
        retaddr,
        (void *)0xE8,
        (unsigned int)"printscan\\print\\spooler\\configuration\\deviceconfigurationservice\\lib\\configurationmanager.cpp",
        (const char *)v8,
        (unsigned int)"RegSetValueEx (WPP Enablement Setup) failed!",
        Timeoutd);
    }
    LODWORD(v38) = 0;
    if ( a2 )
    {
      v9 = a2 - 1;
      if ( v9 )
      {
        if ( v9 != 1 )
        {
          v24 = (const char *)(unsigned int)wil::verify_hresult<long>(2147942487LL);
          wil::details::in1diag3::Throw_HrMsg(
            retaddr,
            (void *)0xF9,
            (unsigned int)"printscan\\print\\spooler\\configuration\\deviceconfigurationservice\\lib\\configurationmanager.cpp",
            v24,
            (int)"Enabled by source is invalid!",
            Timeout);
        }
        LODWORD(v38) = 3;
      }
      else
      {
        LODWORD(v38) = 2;
      }
    }
    else
    {
      LODWORD(v38) = 1;
    }
    SystemTimeAsFileTime = 0;
    *(_QWORD *)v35 = 0;
    GetSystemTimeAsFileTime(&SystemTimeAsFileTime);
    *(struct _FILETIME *)v35 = SystemTimeAsFileTime;
    v10 = RegSetValueExW(hKey, L"EnabledBy", 0, 4u, (const BYTE *)&v38, 4u);
    wil::details::in1diag3::Throw_IfWin32ErrorMsg(
      retaddr,
      (void *)0x101,
      (unsigned int)"printscan\\print\\spooler\\configuration\\deviceconfigurationservice\\lib\\configurationmanager.cpp",
      (const char *)v10,
      (unsigned int)"RegSetValueEx (WPP Enabled By) failed!",
      Timeoute);
    v11 = RegSetValueExW(hKey, L"EnabledTimestamp", 0, 0xBu, v35, 8u);
    wil::details::in1diag3::Throw_IfWin32ErrorMsg(
      retaddr,
      (void *)0x102,
      (unsigned int)"printscan\\print\\spooler\\configuration\\deviceconfigurationservice\\lib\\configurationmanager.cpp",
      (const char *)v11,
      (unsigned int)"RegSetValueEx (WPP Enabled Timestamp) failed!",
      Timeoutf);
    DeviceConfiguration::ConfigurationManager::_UpdateOobeConfigCompleteFlag(v12, hTransaction, 1);
    DeviceConfiguration::ConfigurationManager::_UpdateSpoolerService(v13, hTransaction, 1);
    DeviceConfiguration::ConfigurationManager::_UpdatePrintFilterPipelineSvc(v14, hTransaction, 1);
    DeviceConfiguration::ConfigurationManager::_UpdateSpoolerImageMitigationOptions(v15, hTransaction, 1);
    v16 = CommitTransaction(hTransaction);
    wil::details::in1diag3::Throw_IfWin32BoolFalseMsg(
      retaddr,
      (void *)0x119,
      (unsigned int)"printscan\\print\\spooler\\configuration\\deviceconfigurationservice\\lib\\configurationmanager.cpp",
      (const char *)v16,
      (int)"CommitTransaction failed!",
      Timeoutg);
    DeviceConfiguration::ConfigurationManager::_UpdateSpoolerMitigations(v17, 1);
    DeviceConfiguration::ConfigurationManager::_RemoveInternetPrintComponents(v18);
    DeviceConfiguration::ConfigurationManager::_RestartSpoolerService(v19);
    v40 = -2147483646;
    PrintCore::RegHelpers::SetDwordValue((HKEY *)&v40, v20, v21, 1u);
    wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
    wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&v36);
    result = 0;
  }
  catch ( ... )
  {
    return (unsigned int)wil::details::in1diag3::Return_CaughtException(
                           retaddr,
                           (void *)0x129,
                           (unsigned int)"printscan\\print\\spooler\\configuration\\deviceconfigurationservice\\lib\\conf"
                                         "igurationmanager.cpp",
                           v22);
  }
  return result;
}

```

## disassembly

```asm
0x180012df8  mov     [rsp+arg_8], rbx
0x180012dfd  mov     [rsp+arg_0], rcx
0x180012e02  push    rsi
0x180012e03  push    r12
0x180012e05  push    r15
0x180012e07  sub     rsp, 80h
0x180012e0e  mov     esi, edx
0x180012e10  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_WindowsProtectedPrintSpoolerWorker@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_WindowsProtectedPrintSpoolerWorker@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_WindowsProtectedPrintSpoolerWorker> `wil::Feature<__WilFeatureTraits_Feature_WindowsProtectedPrintSpoolerWorker>::GetImpl(void)'::`2'::impl
0x180012e17  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_WindowsProtectedPrintSpoolerWorker@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_WindowsProtectedPrintSpoolerWorker>::__private_IsEnabled(void)
0x180012e1c  test    al, al
0x180012e1e  jz      short loc_180012E37
0x180012e20  mov     edx, 3; unsigned int
0x180012e25  lea     r9d, [rdx+0Dh]; unsigned int
0x180012e29  lea     r8d, [rdx-2]; unsigned int
0x180012e2d  call    ?_ChangeSpoolerServiceState@ConfigurationManager@DeviceConfiguration@@AEAAJKKK@Z; DeviceConfiguration::ConfigurationManager::_ChangeSpoolerServiceState(ulong,ulong,ulong)
0x180012e32  call    ?_WaitForSpoolerServiceRunning@ConfigurationManager@DeviceConfiguration@@AEAAXXZ; DeviceConfiguration::ConfigurationManager::_WaitForSpoolerServiceRunning(void)
0x180012e37  mov     [rsp+98h+Description], 0; Description
0x180012e40  mov     dword ptr [rsp+98h+Timeout], 0; char *
0x180012e48  mov     [rsp+98h+IsolationFlags], 0; IsolationFlags
0x180012e50  xor     r9d, r9d; IsolationLevel
0x180012e53  xor     r8d, r8d; CreateOptions
0x180012e56  xor     edx, edx; UOW
0x180012e58  xor     ecx, ecx; lpTransactionAttributes
0x180012e5a  call    cs:__imp_CreateTransaction
0x180012e60  mov     rbx, rax
0x180012e63  mov     [rsp+98h+var_20], rax
0x180012e68  mov     rcx, [rsp+98h]; this
0x180012e70  lea     rax, aFailedToOpenTr; "Failed to open transaction!"
0x180012e77  mov     qword ptr [rsp+98h+IsolationFlags], rax; void *
0x180012e7c  mov     r9, rbx; char *
0x180012e7f  lea     r15, aPrintscanPrint_2; "printscan\\print\\spooler\\configuratio"...
0x180012e86  mov     r8, r15; unsigned int
0x180012e89  mov     edx, 0DBh; void *
0x180012e8e  call    ?Throw_IfHandleInvalidMsg@in1diag3@details@wil@@YAPEAXPEAXIPEBD01ZZ; wil::details::in1diag3::Throw_IfHandleInvalidMsg(void *,uint,char const *,void *,char const *,...)
0x180012e93  mov     [rsp+98h+Data], 1
0x180012e9e  mov     [rsp+98h+hKey], 0
0x180012ea7  mov     [rsp+98h+pExtendedParemeter], 0; pExtendedParemeter
0x180012eb0  mov     [rsp+98h+hTransaction], rbx; hTransaction
0x180012eb5  mov     [rsp+98h+lpdwDisposition], 0; lpdwDisposition
0x180012ebe  lea     rax, [rsp+98h+hKey]
0x180012ec3  mov     [rsp+98h+phkResult], rax; phkResult
0x180012ec8  mov     [rsp+98h+Description], 0; lpSecurityAttributes
0x180012ed1  mov     dword ptr [rsp+98h+Timeout], 0F003Fh; char *
0x180012ed9  mov     [rsp+98h+IsolationFlags], 0; dwOptions
0x180012ee1  xor     r9d, r9d; lpClass
0x180012ee4  xor     r8d, r8d; Reserved
0x180012ee7  lea     rdx, SubKey; "Software\\Policies\\Microsoft\\Windows "...
0x180012eee  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180012ef5  call    cs:__imp_RegCreateKeyTransactedW
0x180012efb  mov     r9d, eax; char *
0x180012efe  mov     rcx, [rsp+98h]; this
0x180012f06  lea     rax, aRegcreatekeytr_0; "RegCreateKeyTransacted (WPP Key) failed"...
0x180012f0d  mov     qword ptr [rsp+98h+IsolationFlags], rax; unsigned int
0x180012f12  mov     r8, r15; unsigned int
0x180012f15  mov     edx, 0E0h; void *
0x180012f1a  call    ?Throw_IfWin32ErrorMsg@in1diag3@details@wil@@YAKPEAXIPEBDK1ZZ; wil::details::in1diag3::Throw_IfWin32ErrorMsg(void *,uint,char const *,ulong,char const *,...)
0x180012f1f  mov     r12d, 4
0x180012f25  mov     dword ptr [rsp+98h+Timeout], r12d; char *
0x180012f2a  lea     rax, [rsp+98h+Data]
0x180012f32  mov     qword ptr [rsp+98h+IsolationFlags], rax; lpData
0x180012f37  mov     r9d, r12d; dwType
0x180012f3a  xor     r8d, r8d; Reserved
0x180012f3d  lea     rdx, aWindowsprotect_2; "WindowsProtectedPrintMode"
0x180012f44  mov     rcx, [rsp+98h+hKey]; hKey
0x180012f49  call    cs:__imp_RegSetValueExW
0x180012f4f  mov     r9d, eax; char *
0x180012f52  mov     rcx, [rsp+98h]; this
0x180012f5a  lea     rax, aRegsetvalueexW_3; "RegSetValueEx (WPP Enablement Mode) fai"...
0x180012f61  mov     qword ptr [rsp+98h+IsolationFlags], rax; unsigned int
0x180012f66  mov     r8, r15; unsigned int
0x180012f69  mov     edx, 0E1h; void *
0x180012f6e  call    ?Throw_IfWin32ErrorMsg@in1diag3@details@wil@@YAKPEAXIPEBDK1ZZ; wil::details::in1diag3::Throw_IfWin32ErrorMsg(void *,uint,char const *,ulong,char const *,...)
0x180012f73  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_WindowsProtectedPrintSpoolerWorker@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_WindowsProtectedPrintSpoolerWorker@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_WindowsProtectedPrintSpoolerWorker> `wil::Feature<__WilFeatureTraits_Feature_WindowsProtectedPrintSpoolerWorker>::GetImpl(void)'::`2'::impl
0x180012f7a  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_WindowsProtectedPrintSpoolerWorker@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_WindowsProtectedPrintSpoolerWorker>::__private_IsEnabled(void)
0x180012f7f  test    al, al
0x180012f81  jz      short loc_180012FDC
0x180012f83  mov     dword ptr [rsp+98h+arg_18], 1
0x180012f8e  mov     dword ptr [rsp+98h+Timeout], r12d; char *
0x180012f93  lea     rax, [rsp+98h+arg_18]
0x180012f9b  mov     qword ptr [rsp+98h+IsolationFlags], rax; lpData
0x180012fa0  mov     r9d, r12d; dwType
0x180012fa3  xor     r8d, r8d; Reserved
0x180012fa6  lea     rdx, aWindowsprotect_3; "WindowsProtectedPrintSetup"
0x180012fad  mov     rcx, [rsp+98h+hKey]; hKey
0x180012fb2  call    cs:__imp_RegSetValueExW
0x180012fb8  mov     r9d, eax; char *
0x180012fbb  mov     rcx, [rsp+98h]; this
0x180012fc3  lea     rax, aRegsetvalueexW_1; "RegSetValueEx (WPP Enablement Setup) fa"...
0x180012fca  mov     qword ptr [rsp+98h+IsolationFlags], rax; unsigned int
0x180012fcf  mov     r8, r15; unsigned int
0x180012fd2  mov     edx, 0E8h; void *
0x180012fd7  call    ?Throw_IfWin32ErrorMsg@in1diag3@details@wil@@YAKPEAXIPEBDK1ZZ; wil::details::in1diag3::Throw_IfWin32ErrorMsg(void *,uint,char const *,ulong,char const *,...)
0x180012fdc  mov     dword ptr [rsp+98h+arg_0], 0
0x180012fe7  test    esi, esi
0x180012fe9  jz      short loc_180013013
0x180012feb  sub     esi, 1
0x180012fee  jz      short loc_180013006
0x180012ff0  cmp     esi, 1
0x180012ff3  jnz     loc_1800131A3
0x180012ff9  mov     dword ptr [rsp+98h+arg_0], 3
0x180013004  jmp     short loc_18001301E
0x180013006  mov     dword ptr [rsp+98h+arg_0], 2
0x180013011  jmp     short loc_18001301E
0x180013013  mov     dword ptr [rsp+98h+arg_0], 1
0x18001301e  mov     qword ptr [rsp+98h+SystemTimeAsFileTime.dwLowDateTime], 0
0x180013027  mov     qword ptr [rsp+98h+var_28], 0
0x180013030  lea     rcx, [rsp+98h+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x180013035  call    cs:__imp_GetSystemTimeAsFileTime
0x18001303b  mov     rax, qword ptr [rsp+98h+SystemTimeAsFileTime.dwLowDateTime]
0x180013040  mov     qword ptr [rsp+98h+var_28], rax
0x180013045  mov     dword ptr [rsp+98h+Timeout], r12d; char *
0x18001304a  lea     rax, [rsp+98h+arg_0]
0x180013052  mov     qword ptr [rsp+98h+IsolationFlags], rax; lpData
0x180013057  mov     r9d, r12d; dwType
0x18001305a  xor     r8d, r8d; Reserved
0x18001305d  lea     rdx, aEnabledby; "EnabledBy"
0x180013064  mov     rcx, [rsp+98h+hKey]; hKey
0x180013069  call    cs:__imp_RegSetValueExW
0x18001306f  mov     r9d, eax; char *
0x180013072  mov     rcx, [rsp+98h]; this
0x18001307a  lea     rax, aRegsetvalueexW; "RegSetValueEx (WPP Enabled By) failed!"
0x180013081  mov     qword ptr [rsp+98h+IsolationFlags], rax; unsigned int
0x180013086  mov     r8, r15; unsigned int
0x180013089  mov     edx, 101h; void *
0x18001308e  call    ?Throw_IfWin32ErrorMsg@in1diag3@details@wil@@YAKPEAXIPEBDK1ZZ; wil::details::in1diag3::Throw_IfWin32ErrorMsg(void *,uint,char const *,ulong,char const *,...)
0x180013093  mov     dword ptr [rsp+98h+Timeout], 8; char *
0x18001309b  lea     rax, [rsp+98h+var_28]
0x1800130a0  mov     qword ptr [rsp+98h+IsolationFlags], rax; lpData
0x1800130a5  mov     r9d, 0Bh; dwType
0x1800130ab  xor     r8d, r8d; Reserved
0x1800130ae  lea     rdx, aEnabledtimesta; "EnabledTimestamp"
0x1800130b5  mov     rcx, [rsp+98h+hKey]; hKey
0x1800130ba  call    cs:__imp_RegSetValueExW
0x1800130c0  mov     r9d, eax; char *
0x1800130c3  mov     rcx, [rsp+98h]; this
0x1800130cb  lea     rax, aRegsetvalueexW_2; "RegSetValueEx (WPP Enabled Timestamp) f"...
0x1800130d2  mov     qword ptr [rsp+98h+IsolationFlags], rax; unsigned int
0x1800130d7  mov     r8, r15; unsigned int
0x1800130da  mov     edx, 102h; void *
0x1800130df  call    ?Throw_IfWin32ErrorMsg@in1diag3@details@wil@@YAKPEAXIPEBDK1ZZ; wil::details::in1diag3::Throw_IfWin32ErrorMsg(void *,uint,char const *,ulong,char const *,...)
0x1800130e4  mov     r8b, 1; bool
0x1800130e7  mov     rdx, rbx; void *
0x1800130ea  call    ?_UpdateOobeConfigCompleteFlag@ConfigurationManager@DeviceConfiguration@@AEAAXPEAX_N@Z; DeviceConfiguration::ConfigurationManager::_UpdateOobeConfigCompleteFlag(void *,bool)
0x1800130ef  mov     r8b, 1; bool
0x1800130f2  mov     rdx, rbx; void *
0x1800130f5  call    ?_UpdateSpoolerService@ConfigurationManager@DeviceConfiguration@@AEAAXPEAX_N@Z; DeviceConfiguration::ConfigurationManager::_UpdateSpoolerService(void *,bool)
0x1800130fa  mov     r8b, 1; bool
0x1800130fd  mov     rdx, rbx; void *
0x180013100  call    ?_UpdatePrintFilterPipelineSvc@ConfigurationManager@DeviceConfiguration@@AEAAXPEAX_N@Z; DeviceConfiguration::ConfigurationManager::_UpdatePrintFilterPipelineSvc(void *,bool)
0x180013105  mov     r8b, 1; bool
0x180013108  mov     rdx, rbx; void *
0x18001310b  call    ?_UpdateSpoolerImageMitigationOptions@ConfigurationManager@DeviceConfiguration@@AEAAXPEAX_N@Z; DeviceConfiguration::ConfigurationManager::_UpdateSpoolerImageMitigationOptions(void *,bool)
0x180013110  mov     rcx, rbx; TransactionHandle
0x180013113  call    cs:__imp_CommitTransaction
0x180013119  mov     rcx, [rsp+98h]; this
0x180013121  lea     rdx, aCommittransact_0; "CommitTransaction failed!"
0x180013128  mov     qword ptr [rsp+98h+IsolationFlags], rdx; int
0x18001312d  mov     r9d, eax; char *
0x180013130  mov     r8, r15; unsigned int
0x180013133  mov     edx, 119h; void *
0x180013138  call    ?Throw_IfWin32BoolFalseMsg@in1diag3@details@wil@@YAHPEAXIPEBDH1ZZ; wil::details::in1diag3::Throw_IfWin32BoolFalseMsg(void *,uint,char const *,int,char const *,...)
0x18001313d  mov     dl, 1; bool
0x18001313f  call    ?_UpdateSpoolerMitigations@ConfigurationManager@DeviceConfiguration@@AEAAX_N@Z; DeviceConfiguration::ConfigurationManager::_UpdateSpoolerMitigations(bool)
0x180013144  call    ?_RemoveInternetPrintComponents@ConfigurationManager@DeviceConfiguration@@AEAAXXZ; DeviceConfiguration::ConfigurationManager::_RemoveInternetPrintComponents(void)
0x180013149  call    ?_RestartSpoolerService@ConfigurationManager@DeviceConfiguration@@AEAAXXZ; DeviceConfiguration::ConfigurationManager::_RestartSpoolerService(void)
0x18001314e  mov     [rsp+98h+arg_18], 0FFFFFFFF80000002h
0x18001315a  mov     r9d, 1; unsigned int
0x180013160  lea     rcx, [rsp+98h+arg_18]; HKEY *
0x180013168  call    ?SetDwordValue@RegHelpers@PrintCore@@SAJAEBQEAUHKEY__@@PEBG1K@Z; PrintCore::RegHelpers::SetDwordValue(HKEY__ * const &,ushort const *,ushort const *,ulong)
0x18001316d  nop
0x18001316e  lea     rcx, [rsp+98h+hKey]
0x180013173  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x180013178  nop
0x180013179  lea     rcx, [rsp+98h+var_20]
0x18001317e  call    ??1?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x180013183  xor     eax, eax
0x180013185  jmp     short loc_18001318E
0x180013187  mov     eax, dword ptr [rsp+98h+arg_0]
0x18001318e  mov     rbx, [rsp+98h+arg_8]
0x180013196  add     rsp, 80h
0x18001319d  pop     r15
0x18001319f  pop     r12
0x1800131a1  pop     rsi
0x1800131a2  retn
0x1800131a3  mov     ecx, 80070057h
0x1800131a8  call    ??$verify_hresult@J@wil@@YAJJ@Z; wil::verify_hresult<long>(long)
0x1800131ad  mov     r9d, eax; char *
0x1800131b0  mov     rcx, [rsp+98h]; this
0x1800131b8  lea     rax, aEnabledBySourc; "Enabled by source is invalid!"
0x1800131bf  mov     qword ptr [rsp+98h+IsolationFlags], rax; int
0x1800131c4  mov     r8, r15; unsigned int
0x1800131c7  mov     edx, 0F9h; void *
0x1800131cc  call    ?Throw_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Throw_HrMsg(void *,uint,char const *,long,char const *,...)
```
