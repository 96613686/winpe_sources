# Print::Driver::PrinterExtensionRegistrarService::WaitForThenProcessPrinterExtensionInstallations(std::shared_ptr<Print::Driver::PrinterExtensionRegistrarService>)

- ea: `0x1800827f0`
- end: `0x180082b1f`
- name: `?WaitForThenProcessPrinterExtensionInstallations@PrinterExtensionRegistrarService@Driver@Print@@CAXV?$shared_ptr@VPrinterExtensionRegistrarService@Driver@Print@@@std@@@Z`
- size: `815`
- prototype: `void __fastcall(__int64)`
- caller_count: `0`
- callee_count: `14`
- tags: `registry_config, loader_planting, service_task, installer_update, broker_com_uri`

## callees

- `0x1800032e0`
- `0x18000da28`
- `0x18000f590`
- `0x1800183a0`
- `0x1800183f8`
- `0x1800361b8`
- `0x180036514`
- `0x180036568`
- `0x18007e8ec`
- `0x18007f0a4`
- `0x18007f2a8`
- `0x18008091c`
- `0x1800827f0`
- `0x1801c3010`

## import_xrefs

- `KERNEL32!LeaveCriticalSection` at `0x1800829bd`
- `KERNEL32!LeaveCriticalSection` at `0x1800829bd`
- `KERNEL32!EnterCriticalSection` at `0x18008293a`
- `KERNEL32!EnterCriticalSection` at `0x18008293a`
- `KERNEL32!SetEvent` at `0x1800829ca`
- `KERNEL32!SetEvent` at `0x1800829f5`
- `KERNEL32!SetEvent` at `0x180082a86`
- `KERNEL32!SetEvent` at `0x180082a93`
- `KERNEL32!SetEvent` at `0x1800829ca`
- `KERNEL32!SetEvent` at `0x1800829f5`
- `KERNEL32!SetEvent` at `0x180082a86`
- `KERNEL32!SetEvent` at `0x180082a93`
- `KERNEL32!WaitForMultipleObjects` at `0x1800829e0`
- `KERNEL32!WaitForMultipleObjects` at `0x1800829e0`
- `ADVAPI32!RegCloseKey` at `0x180082a19`
- `ADVAPI32!RegCloseKey` at `0x180082a32`
- `ADVAPI32!RegCloseKey` at `0x180082a19`
- `ADVAPI32!RegCloseKey` at `0x180082a32`

## string_xrefs

- `0x180082827`: `Print::Driver::PrinterExtensionRegistrarService::WaitForThenProcessPrinterExtensionInstallations`
- `0x180082842`: `Print::Driver::PrinterExtensionRegistrarService::WaitForThenProcessPrinterExtensionInstallations`
- `0x1800828e0`: `Print::Driver::PrinterExtensionRegistrarService::WaitForThenProcessPrinterExtensionInstallations`
- `0x18008290f`: `Print::Driver::PrinterExtensionRegistrarService::WaitForThenProcessPrinterExtensionInstallations`
- `0x180082a02`: `Print::Driver::PrinterExtensionRegistrarService::WaitForThenProcessPrinterExtensionInstallations`
- `0x180082aa5`: `Print::Driver::PrinterExtensionRegistrarService::WaitForThenProcessPrinterExtensionInstallations`
- `0x1800828d9`: `Worker has access to necessary parent keys.`
- `0x180082941`: `Beginning a processing iteration for pending installs.`
- `0x180082948`: `Print::Driver::PrinterExtensionRegistrarService::ProcessPendingInstallations`
- `0x18008299f`: `Print::Driver::PrinterExtensionRegistrarService::ProcessPendingInstallations`
- `0x180082998`: `Completed a processing iteration for pending installs.`
- `0x18008289f`: `OfflinePrinterExtensions`

## pseudocode

```c
void __fastcall Print::Driver::PrinterExtensionRegistrarService::WaitForThenProcessPrinterExtensionInstallations(
        __int64 a1)
{
  __int64 v1; // rdi
  LPCWSTR v2; // rcx
  struct RegistryHandleRAII *v3; // rdx
  bool v4; // r8
  LPCWSTR v5; // rbx
  __int64 v6; // r8
  __int64 *v7; // rsi
  __int64 *i; // rbx
  __int64 v9; // rax
  volatile signed __int32 *v10; // rbx
  PHKEY v11; // [rsp+20h] [rbp-C8h]
  bool v12; // [rsp+28h] [rbp-C0h]
  unsigned int v13; // [rsp+30h] [rbp-B8h]
  char v14; // [rsp+34h] [rbp-B4h]
  HKEY hKey; // [rsp+40h] [rbp-A8h] BYREF
  HKEY v18; // [rsp+48h] [rbp-A0h] BYREF
  __int128 v19; // [rsp+50h] [rbp-98h] BYREF
  LPCWSTR v20; // [rsp+60h] [rbp-88h] BYREF
  HANDLE Handles[4]; // [rsp+68h] [rbp-80h] BYREF
  const hr_error *v22; // [rsp+88h] [rbp-60h] BYREF
  const PrintCore::WindowsError *v23; // [rsp+90h] [rbp-58h] BYREF
  WCHAR SubKey[8]; // [rsp+98h] [rbp-50h] BYREF
  __int128 v25; // [rsp+A8h] [rbp-40h]

  Handles[2] = (HANDLE)-2LL;
  v1 = a1;
  Print::Driver::Telemetry::PrintConfigTelemetry::WriteDbgTraceInfo(
    "Print::Driver::PrinterExtensionRegistrarService::WaitForThenProcessPrinterExtensionInstallations",
    L"Entering worker callback.");
  try
  {
    v13 = 0;
    Print::Driver::Telemetry::PrintConfigTelemetry::WriteDbgTraceInfo(
      "Print::Driver::PrinterExtensionRegistrarService::WaitForThenProcessPrinterExtensionInstallations",
      L"Worker has started.");
    v18 = 0;
    Win32Adapters::Registry::RegOpenKeyExW(HKEY_LOCAL_MACHINE, *(LPCWSTR *)v1, 0x20019u, &v18);
    hKey = 0;
    *(_OWORD *)SubKey = 0;
    v25 = 0;
    std::wstring::_Construct<1,unsigned short const *>(SubKey, L"OfflinePrinterExtensions");
    Win32Adapters::Registry::RegCreateKeyW(v18, SubKey, &hKey);
    std::wstring::~wstring(SubKey);
    Print::Driver::Telemetry::PrintConfigTelemetry::WriteDbgTraceInfo(
      "Print::Driver::PrinterExtensionRegistrarService::WaitForThenProcessPrinterExtensionInstallations",
      L"Worker has access to necessary parent keys.");
    v2 = *(LPCWSTR *)v1;
    Handles[0] = *(HANDLE *)(*(_QWORD *)v1 + 32LL);
    Handles[1] = *((HANDLE *)v2 + 6);
    do
    {
      Print::Driver::Telemetry::PrintConfigTelemetry::WriteDbgTraceInfo(
        "Print::Driver::PrinterExtensionRegistrarService::WaitForThenProcessPrinterExtensionInstallations",
        L"Worker has been signaled.");
      Win32Adapters::Registry::RegNotifyChangeKeyValue(
        (Win32Adapters::Registry *)&hKey,
        v3,
        v4,
        *(_QWORD *)(*(_QWORD *)v1 + 32LL),
        v11,
        v12);
      v5 = *(LPCWSTR *)v1;
      Handles[3] = &Print::Driver::PrinterExtensionRegistrar::s_printerExtensionRegistrarCS;
      EnterCriticalSection(&Print::Driver::PrinterExtensionRegistrar::s_printerExtensionRegistrarCS);
      Print::Driver::Telemetry::PrintConfigTelemetry::WriteDbgTraceInfo(
        "Print::Driver::PrinterExtensionRegistrarService::ProcessPendingInstallations",
        L"Beginning a processing iteration for pending installs.");
      Print::Driver::PrinterExtensionRegistrarService::GetPendingInstallations(v5, SubKey);
      LOBYTE(v6) = v14;
      std::_List_val_std::_List_simple_types_std::shared_ptr_Print::Driver::PrinterExtensionInstallAction_____::_Sort__lambda_48055721eafb7b1d79ecfd42a7cec9a7___(
        *(_QWORD *)SubKey,
        *(_QWORD *)&SubKey[4],
        v6);
      v20 = v5;
      v7 = *(__int64 **)SubKey;
      for ( i = **(__int64 ***)SubKey; i != v7; i = (__int64 *)*i )
      {
        v19 = 0;
        v9 = i[3];
        if ( v9 )
          _InterlockedIncrement((volatile signed __int32 *)(v9 + 8));
        v19 = *((_OWORD *)i + 1);
        lambda_59ac2e359e082a145f71a712d8ff998b_::operator()(&v20, &v19);
      }
      Print::Driver::Telemetry::PrintConfigTelemetry::WriteDbgTraceInfo(
        "Print::Driver::PrinterExtensionRegistrarService::ProcessPendingInstallations",
        L"Completed a processing iteration for pending installs.");
      std::list<std::shared_ptr<Print::Driver::PrinterExtensionInstallAction>>::~list<std::shared_ptr<Print::Driver::PrinterExtensionInstallAction>>(SubKey);
      LeaveCriticalSection(&Print::Driver::PrinterExtensionRegistrar::s_printerExtensionRegistrarCS);
      SetEvent(*(HANDLE *)(*(_QWORD *)v1 + 40LL));
    }
    while ( !WaitForMultipleObjects(2u, Handles, 0, 0xFFFFFFFF) );
    SetEvent(*(HANDLE *)(*(_QWORD *)v1 + 56LL));
    Print::Driver::Telemetry::PrintConfigTelemetry::WriteDbgTraceInfo(
      "Print::Driver::PrinterExtensionRegistrarService::WaitForThenProcessPrinterExtensionInstallations",
      L"Worker signaled stopped event.");
    if ( hKey )
    {
      RegCloseKey(hKey);
      hKey = 0;
    }
    if ( v18 )
      RegCloseKey(v18);
  }
  catch ( std::bad_alloc )
  {
    v13 = -2147024882;
    v1 = a1;
  }
  catch ( const hr_error *v22 )
  {
    v13 = *((_DWORD *)v22 + 6);
    v1 = a1;
  }
  catch ( const PrintCore::WindowsError *v23 )
  {
    v13 = *((_DWORD *)v23 + 6);
    v1 = a1;
  }
  catch ( std::exception )
  {
    v13 = -2147467259;
    v1 = a1;
  }
  catch ( ... )
  {
    v13 = -2147418113;
    v1 = a1;
  }
  SetEvent(*(HANDLE *)(*(_QWORD *)v1 + 40LL));
  SetEvent(*(HANDLE *)(*(_QWORD *)v1 + 56LL));
  Print::Driver::Telemetry::PrintConfigTelemetry::WriteDbgTraceWarning(
    "Print::Driver::PrinterExtensionRegistrarService::WaitForThenProcessPrinterExtensionInstallations",
    L"Worker encountered exception; signaled all events to unblock waiters. hr=0x%x",
    v13);
  v10 = *(volatile signed __int32 **)(v1 + 8);
  if ( v10 && _InterlockedExchangeAdd(v10 + 2, 0xFFFFFFFF) == 1 )
  {
    (**(void (__fastcall ***)(volatile signed __int32 *))v10)(v10);
    if ( !_InterlockedDecrement(v10 + 3) )
      (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v10 + 8LL))(v10);
  }
}

```

## disassembly

```asm
0x1800827f0  push    rbx
0x1800827f2  push    rsi
0x1800827f3  push    rdi
0x1800827f4  push    r14
0x1800827f6  sub     rsp, 0C8h
0x1800827fd  mov     [rsp+0E8h+var_70], 0FFFFFFFFFFFFFFFEh
0x180082806  mov     rax, cs:__security_cookie
0x18008280d  xor     rax, rsp
0x180082810  mov     [rsp+0E8h+var_30], rax
0x180082818  mov     rdi, rcx
0x18008281b  mov     [rsp+0E8h+var_B0], rcx
0x180082820  lea     rdx, aEnteringWorker; "Entering worker callback."
0x180082827  lea     rcx, aPrintDriverPri_4; "Print::Driver::PrinterExtensionRegistra"...
0x18008282e  call    ?WriteDbgTraceInfo@PrintConfigTelemetry@Telemetry@Driver@Print@@SAXPEADPEAGZZ; Print::Driver::Telemetry::PrintConfigTelemetry::WriteDbgTraceInfo(char *,ushort *,...)
0x180082833  mov     [rsp+0E8h+var_B8], 0
0x18008283b  lea     rdx, aWorkerHasStart; "Worker has started."
0x180082842  lea     rcx, aPrintDriverPri_4; "Print::Driver::PrinterExtensionRegistra"...
0x180082849  call    ?WriteDbgTraceInfo@PrintConfigTelemetry@Telemetry@Driver@Print@@SAXPEADPEAGZZ; Print::Driver::Telemetry::PrintConfigTelemetry::WriteDbgTraceInfo(char *,ushort *,...)
0x18008284e  mov     [rsp+0E8h+var_A0], 0
0x180082857  lea     rax, [rsp+0E8h+var_A0]
0x18008285c  mov     [rsp+0E8h+var_C8], rax; void *
0x180082861  mov     r9b, 1
0x180082864  mov     r8d, 20019h; samDesired
0x18008286a  mov     rdx, [rdi]; lpSubKey
0x18008286d  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180082874  call    ?RegOpenKeyExW@Registry@Win32Adapters@@YAXPEAUHKEY__@@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@K_NAEAVRegistryHandleRAII@@@Z; Win32Adapters::Registry::RegOpenKeyExW(HKEY__ *,std::wstring const &,ulong,bool,RegistryHandleRAII &)
0x180082879  mov     [rsp+0E8h+hKey], 0
0x180082882  xorps   xmm0, xmm0
0x180082885  movups  xmmword ptr [rsp+0E8h+SubKey], xmm0
0x18008288d  xorps   xmm1, xmm1
0x180082890  movdqu  [rsp+0E8h+var_40], xmm1
0x180082899  mov     r8d, 18h
0x18008289f  lea     rdx, aOfflineprinter; "OfflinePrinterExtensions"
0x1800828a6  lea     rcx, [rsp+0E8h+SubKey]
0x1800828ae  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x1800828b3  nop
0x1800828b4  lea     r8, [rsp+0E8h+hKey]; phkResult
0x1800828b9  lea     rdx, [rsp+0E8h+SubKey]; lpSubKey
0x1800828c1  mov     rcx, [rsp+0E8h+var_A0]; hKey
0x1800828c6  call    ?RegCreateKeyW@Registry@Win32Adapters@@YAXPEAUHKEY__@@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAVRegistryHandleRAII@@@Z; Win32Adapters::Registry::RegCreateKeyW(HKEY__ *,std::wstring const &,RegistryHandleRAII &)
0x1800828cb  nop
0x1800828cc  lea     rcx, [rsp+0E8h+SubKey]
0x1800828d4  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800828d9  lea     rdx, aWorkerHasAcces; "Worker has access to necessary parent k"...
0x1800828e0  lea     rcx, aPrintDriverPri_4; "Print::Driver::PrinterExtensionRegistra"...
0x1800828e7  call    ?WriteDbgTraceInfo@PrintConfigTelemetry@Telemetry@Driver@Print@@SAXPEADPEAGZZ; Print::Driver::Telemetry::PrintConfigTelemetry::WriteDbgTraceInfo(char *,ushort *,...)
0x1800828ec  mov     rcx, [rdi]
0x1800828ef  mov     rax, [rcx+20h]
0x1800828f3  mov     [rsp+0E8h+Handles], rax
0x1800828f8  mov     rax, [rcx+30h]
0x1800828fc  mov     [rsp+0E8h+var_78], rax
0x180082901  lea     r14, ?s_printerExtensionRegistrarCS@PrinterExtensionRegistrar@Driver@Print@@2VCriticalSectionRAII@@A; CriticalSectionRAII Print::Driver::PrinterExtensionRegistrar::s_printerExtensionRegistrarCS
0x180082908  lea     rdx, aWorkerHasBeenS; "Worker has been signaled."
0x18008290f  lea     rcx, aPrintDriverPri_4; "Print::Driver::PrinterExtensionRegistra"...
0x180082916  call    ?WriteDbgTraceInfo@PrintConfigTelemetry@Telemetry@Driver@Print@@SAXPEADPEAGZZ; Print::Driver::Telemetry::PrintConfigTelemetry::WriteDbgTraceInfo(char *,ushort *,...)
0x18008291b  mov     r9, [rdi]
0x18008291e  mov     r9, [r9+20h]; unsigned int
0x180082922  lea     rcx, [rsp+0E8h+hKey]; this
0x180082927  call    ?RegNotifyChangeKeyValue@Registry@Win32Adapters@@YAXAEAVRegistryHandleRAII@@_NKPEAX1@Z; Win32Adapters::Registry::RegNotifyChangeKeyValue(RegistryHandleRAII &,bool,ulong,void *,bool)
0x18008292c  mov     rbx, [rdi]
0x18008292f  mov     [rsp+0E8h+var_68], r14
0x180082937  mov     rcx, r14; lpCriticalSection
0x18008293a  call    cs:__imp_EnterCriticalSection
0x180082940  nop
0x180082941  lea     rdx, aBeginningAProc; "Beginning a processing iteration for pe"...
0x180082948  lea     rcx, aPrintDriverPri_9; "Print::Driver::PrinterExtensionRegistra"...
0x18008294f  call    ?WriteDbgTraceInfo@PrintConfigTelemetry@Telemetry@Driver@Print@@SAXPEADPEAGZZ; Print::Driver::Telemetry::PrintConfigTelemetry::WriteDbgTraceInfo(char *,ushort *,...)
0x180082954  lea     rdx, [rsp+0E8h+SubKey]
0x18008295c  mov     rcx, rbx
0x18008295f  call    ?GetPendingInstallations@PrinterExtensionRegistrarService@Driver@Print@@AEAA?AV?$list@V?$shared_ptr@VPrinterExtensionInstallAction@Driver@Print@@@std@@V?$allocator@V?$shared_ptr@VPrinterExtensionInstallAction@Driver@Print@@@std@@@2@@std@@XZ; Print::Driver::PrinterExtensionRegistrarService::GetPendingInstallations(void)
0x180082964  nop
0x180082965  mov     r8b, [rsp+0E8h+var_B4]
0x18008296a  mov     rdx, qword ptr [rsp+0E8h+SubKey+8]
0x180082972  mov     rcx, qword ptr [rsp+0E8h+SubKey]
0x18008297a  call    std___List_val_std___List_simple_types_std__shared_ptr_Print__Driver__PrinterExtensionInstallAction________Sort__lambda_48055721eafb7b1d79ecfd42a7cec9a7___
0x18008297f  mov     [rsp+0E8h+var_88], rbx
0x180082984  mov     rsi, qword ptr [rsp+0E8h+SubKey]
0x18008298c  mov     rbx, [rsi]
0x18008298f  cmp     rbx, rsi
0x180082992  jnz     loc_180082A3B
0x180082998  lea     rdx, aCompletedAProc; "Completed a processing iteration for pe"...
0x18008299f  lea     rcx, aPrintDriverPri_9; "Print::Driver::PrinterExtensionRegistra"...
0x1800829a6  call    ?WriteDbgTraceInfo@PrintConfigTelemetry@Telemetry@Driver@Print@@SAXPEADPEAGZZ; Print::Driver::Telemetry::PrintConfigTelemetry::WriteDbgTraceInfo(char *,ushort *,...)
0x1800829ab  nop
0x1800829ac  lea     rcx, [rsp+0E8h+SubKey]
0x1800829b4  call    ??1?$list@V?$shared_ptr@VPrinterExtensionInstallAction@Driver@Print@@@std@@V?$allocator@V?$shared_ptr@VPrinterExtensionInstallAction@Driver@Print@@@std@@@2@@std@@QEAA@XZ; std::list<std::shared_ptr<Print::Driver::PrinterExtensionInstallAction>>::~list<std::shared_ptr<Print::Driver::PrinterExtensionInstallAction>>(void)
0x1800829b9  nop
0x1800829ba  mov     rcx, r14; lpCriticalSection
0x1800829bd  call    cs:__imp_LeaveCriticalSection
0x1800829c3  mov     rcx, [rdi]
0x1800829c6  mov     rcx, [rcx+28h]; hEvent
0x1800829ca  call    cs:__imp_SetEvent
0x1800829d0  or      r9d, 0FFFFFFFFh; dwMilliseconds
0x1800829d4  xor     r8d, r8d; bWaitAll
0x1800829d7  lea     rdx, [rsp+0E8h+Handles]; lpHandles
0x1800829dc  lea     ecx, [r8+2]; nCount
0x1800829e0  call    cs:__imp_WaitForMultipleObjects
0x1800829e6  test    eax, eax
0x1800829e8  jz      loc_180082908
0x1800829ee  mov     rcx, [rdi]
0x1800829f1  mov     rcx, [rcx+38h]; hEvent
0x1800829f5  call    cs:__imp_SetEvent
0x1800829fb  lea     rdx, aWorkerSignaled; "Worker signaled stopped event."
0x180082a02  lea     rcx, aPrintDriverPri_4; "Print::Driver::PrinterExtensionRegistra"...
0x180082a09  call    ?WriteDbgTraceInfo@PrintConfigTelemetry@Telemetry@Driver@Print@@SAXPEADPEAGZZ; Print::Driver::Telemetry::PrintConfigTelemetry::WriteDbgTraceInfo(char *,ushort *,...)
0x180082a0e  nop
0x180082a0f  mov     rcx, [rsp+0E8h+hKey]; hKey
0x180082a14  test    rcx, rcx
0x180082a17  jz      short loc_180082A28
0x180082a19  call    cs:__imp_RegCloseKey
0x180082a1f  mov     [rsp+0E8h+hKey], 0
0x180082a28  mov     rcx, [rsp+0E8h+var_A0]; hKey
0x180082a2d  test    rcx, rcx
0x180082a30  jz      short loc_180082A39
0x180082a32  call    cs:__imp_RegCloseKey
0x180082a38  nop
0x180082a39  jmp     short loc_180082A7F
0x180082a3b  xorps   xmm0, xmm0
0x180082a3e  movdqu  [rsp+0E8h+var_98], xmm0
0x180082a44  mov     rax, [rbx+18h]
0x180082a48  test    rax, rax
0x180082a4b  jz      short loc_180082A51
0x180082a4d  lock inc dword ptr [rax+8]
0x180082a51  mov     rax, [rbx+10h]
0x180082a55  mov     qword ptr [rsp+0E8h+var_98], rax
0x180082a5a  mov     rax, [rbx+18h]
0x180082a5e  mov     qword ptr [rsp+0E8h+var_98+8], rax
0x180082a63  lea     rdx, [rsp+0E8h+var_98]
0x180082a68  lea     rcx, [rsp+0E8h+var_88]
0x180082a6d  call    _lambda_59ac2e359e082a145f71a712d8ff998b___operator__
0x180082a72  mov     rbx, [rbx]
0x180082a75  jmp     loc_18008298F
0x180082a7a  mov     rdi, [rsp+0E8h+var_B0]
0x180082a7f  mov     rcx, [rdi]
0x180082a82  mov     rcx, [rcx+28h]; hEvent
0x180082a86  call    cs:__imp_SetEvent
0x180082a8c  mov     rcx, [rdi]
0x180082a8f  mov     rcx, [rcx+38h]; hEvent
0x180082a93  call    cs:__imp_SetEvent
0x180082a99  mov     r8d, [rsp+0E8h+var_B8]
0x180082a9e  lea     rdx, aWorkerEncounte; "Worker encountered exception; signaled "...
0x180082aa5  lea     rcx, aPrintDriverPri_4; "Print::Driver::PrinterExtensionRegistra"...
0x180082aac  call    ?WriteDbgTraceWarning@PrintConfigTelemetry@Telemetry@Driver@Print@@SAXPEADPEAGZZ; Print::Driver::Telemetry::PrintConfigTelemetry::WriteDbgTraceWarning(char *,ushort *,...)
0x180082ab1  nop
0x180082ab2  mov     rbx, [rdi+8]
0x180082ab6  test    rbx, rbx
0x180082ab9  jz      short loc_180082AF2
0x180082abb  or      edi, 0FFFFFFFFh
0x180082abe  mov     eax, edi
0x180082ac0  lock xadd [rbx+8], eax
0x180082ac5  add     eax, edi
0x180082ac7  jnz     short loc_180082AF2
0x180082ac9  mov     rax, [rbx]
0x180082acc  mov     rcx, rbx
0x180082acf  mov     rax, [rax]
0x180082ad2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180082ad7  mov     eax, edi
0x180082ad9  lock xadd [rbx+0Ch], eax
0x180082ade  add     eax, edi
0x180082ae0  jnz     short loc_180082AF2
0x180082ae2  mov     rax, [rbx]
0x180082ae5  mov     rcx, rbx
0x180082ae8  mov     rax, [rax+8]
0x180082aec  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180082af1  nop
0x180082af2  mov     rcx, [rsp+0E8h+var_30]
0x180082afa  xor     rcx, rsp; StackCookie
0x180082afd  call    __security_check_cookie
0x180082b02  add     rsp, 0C8h
0x180082b09  pop     r14
0x180082b0b  pop     rdi
0x180082b0c  pop     rsi
0x180082b0d  pop     rbx
0x180082b0e  retn
0x180082b0f  jmp     loc_180082A7A
0x180082b14  jmp     loc_180082A7A
0x180082b19  jmp     loc_180082A7A
```
