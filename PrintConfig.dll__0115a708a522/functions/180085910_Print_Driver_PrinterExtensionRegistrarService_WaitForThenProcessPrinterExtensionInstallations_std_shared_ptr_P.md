# Print::Driver::PrinterExtensionRegistrarService::WaitForThenProcessPrinterExtensionInstallations(std::shared_ptr<Print::Driver::PrinterExtensionRegistrarService>)

- ea: `0x180085910`
- end: `0x180085cc8`
- name: `?WaitForThenProcessPrinterExtensionInstallations@PrinterExtensionRegistrarService@Driver@Print@@CAXV?$shared_ptr@VPrinterExtensionRegistrarService@Driver@Print@@@std@@@Z`
- size: `952`
- prototype: `void __fastcall(__int64)`
- caller_count: `0`
- callee_count: `15`
- tags: `registry_config, loader_planting, service_task, installer_update, broker_com_uri`

## callees

- `0x180003400`
- `0x18000de1c`
- `0x18000fa4c`
- `0x180018f00`
- `0x180018f58`
- `0x180037588`
- `0x1800378fc`
- `0x180037958`
- `0x1800817b0`
- `0x1800818b0`
- `0x180081fb0`
- `0x1800821dc`
- `0x1800838ec`
- `0x180085910`
- `0x1801cb010`

## import_xrefs

- `KERNEL32!LeaveCriticalSection` at `0x180085b31`
- `KERNEL32!LeaveCriticalSection` at `0x180085b31`
- `KERNEL32!EnterCriticalSection` at `0x180085a61`
- `KERNEL32!EnterCriticalSection` at `0x180085a61`
- `KERNEL32!SetEvent` at `0x180085b44`
- `KERNEL32!SetEvent` at `0x180085b7b`
- `KERNEL32!SetEvent` at `0x180085c1e`
- `KERNEL32!SetEvent` at `0x180085c31`
- `KERNEL32!SetEvent` at `0x180085b44`
- `KERNEL32!SetEvent` at `0x180085b7b`
- `KERNEL32!SetEvent` at `0x180085c1e`
- `KERNEL32!SetEvent` at `0x180085c31`
- `KERNEL32!WaitForMultipleObjects` at `0x180085b60`
- `KERNEL32!WaitForMultipleObjects` at `0x180085b60`
- `ADVAPI32!RegCloseKey` at `0x180085ba5`
- `ADVAPI32!RegCloseKey` at `0x180085bc4`
- `ADVAPI32!RegCloseKey` at `0x180085ba5`
- `ADVAPI32!RegCloseKey` at `0x180085bc4`

## string_xrefs

- `0x18008594e`: `Print::Driver::PrinterExtensionRegistrarService::WaitForThenProcessPrinterExtensionInstallations`
- `0x180085969`: `Print::Driver::PrinterExtensionRegistrarService::WaitForThenProcessPrinterExtensionInstallations`
- `0x180085a07`: `Print::Driver::PrinterExtensionRegistrarService::WaitForThenProcessPrinterExtensionInstallations`
- `0x180085a36`: `Print::Driver::PrinterExtensionRegistrarService::WaitForThenProcessPrinterExtensionInstallations`
- `0x180085b8e`: `Print::Driver::PrinterExtensionRegistrarService::WaitForThenProcessPrinterExtensionInstallations`
- `0x180085c49`: `Print::Driver::PrinterExtensionRegistrarService::WaitForThenProcessPrinterExtensionInstallations`
- `0x180085a00`: `Worker has access to necessary parent keys.`
- `0x180085a6e`: `Beginning a processing iteration for pending installs.`
- `0x180085a75`: `Print::Driver::PrinterExtensionRegistrarService::ProcessPendingInstallations`
- `0x180085b13`: `Print::Driver::PrinterExtensionRegistrarService::ProcessPendingInstallations`
- `0x180085b0c`: `Completed a processing iteration for pending installs.`
- `0x1800859c6`: `OfflinePrinterExtensions`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
void __fastcall Print::Driver::PrinterExtensionRegistrarService::WaitForThenProcessPrinterExtensionInstallations(
        __int64 a1)
{
  __int64 v1; // rdi
  const WCHAR *v2; // rcx
  struct RegistryHandleRAII *v3; // rdx
  __int64 v4; // r8
  const WCHAR *v5; // r15
  __int64 v6; // rbx
  _QWORD **v7; // r14
  __int64 v8; // rsi
  _QWORD *v9; // rax
  __int64 *v10; // rsi
  __int64 *i; // rbx
  __int64 v12; // rax
  volatile signed __int32 *v13; // rbx
  unsigned int v14; // [rsp+34h] [rbp-D4h]
  HKEY hKey; // [rsp+40h] [rbp-C8h] BYREF
  HKEY v18; // [rsp+48h] [rbp-C0h] BYREF
  _QWORD *v19; // [rsp+50h] [rbp-B8h] BYREF
  __int128 v20; // [rsp+58h] [rbp-B0h] BYREF
  const WCHAR *v21; // [rsp+68h] [rbp-A0h] BYREF
  HANDLE Handles[4]; // [rsp+70h] [rbp-98h] BYREF
  const hr_error *v23; // [rsp+90h] [rbp-78h] BYREF
  const PrintCore::WindowsError *v24; // [rsp+98h] [rbp-70h] BYREF
  WCHAR SubKey[8]; // [rsp+A0h] [rbp-68h] BYREF
  __int128 v26; // [rsp+B0h] [rbp-58h]

  Handles[2] = (HANDLE)-2LL;
  v1 = a1;
  Print::Driver::Telemetry::PrintConfigTelemetry::WriteDbgTraceInfo(
    "Print::Driver::PrinterExtensionRegistrarService::WaitForThenProcessPrinterExtensionInstallations",
    L"Entering worker callback.");
  try
  {
    v14 = 0;
    Print::Driver::Telemetry::PrintConfigTelemetry::WriteDbgTraceInfo(
      "Print::Driver::PrinterExtensionRegistrarService::WaitForThenProcessPrinterExtensionInstallations",
      L"Worker has started.");
    v18 = 0;
    Win32Adapters::Registry::RegOpenKeyExW(HKEY_LOCAL_MACHINE, *(const WCHAR **)v1, 0x20019u, 1, &v18);
    hKey = 0;
    *(_OWORD *)SubKey = 0;
    v26 = 0;
    std::wstring::_Construct<1,unsigned short const *>(SubKey, L"OfflinePrinterExtensions", 0x18u);
    Win32Adapters::Registry::RegCreateKeyW(v18, SubKey, &hKey);
    std::wstring::~wstring((char **)SubKey);
    Print::Driver::Telemetry::PrintConfigTelemetry::WriteDbgTraceInfo(
      "Print::Driver::PrinterExtensionRegistrarService::WaitForThenProcessPrinterExtensionInstallations",
      L"Worker has access to necessary parent keys.");
    v2 = *(const WCHAR **)v1;
    Handles[0] = *(HANDLE *)(*(_QWORD *)v1 + 32LL);
    Handles[1] = *((HANDLE *)v2 + 6);
    do
    {
      Print::Driver::Telemetry::PrintConfigTelemetry::WriteDbgTraceInfo(
        "Print::Driver::PrinterExtensionRegistrarService::WaitForThenProcessPrinterExtensionInstallations",
        L"Worker has been signaled.");
      Win32Adapters::Registry::RegNotifyChangeKeyValue(&hKey, v3, v4, *(void **)(*(_QWORD *)v1 + 32LL));
      v5 = *(const WCHAR **)v1;
      Handles[3] = &Print::Driver::PrinterExtensionRegistrar::s_printerExtensionRegistrarCS;
      EnterCriticalSection(&Print::Driver::PrinterExtensionRegistrar::s_printerExtensionRegistrarCS);
      Print::Driver::Telemetry::PrintConfigTelemetry::WriteDbgTraceInfo(
        "Print::Driver::PrinterExtensionRegistrarService::ProcessPendingInstallations",
        L"Beginning a processing iteration for pending installs.");
      Print::Driver::PrinterExtensionRegistrarService::GetPendingInstallations((__int64)v5, SubKey);
      v6 = *(_QWORD *)&SubKey[4];
      if ( *(_QWORD *)&SubKey[4] >= 2u )
      {
        v7 = *(_QWORD ***)SubKey;
        v8 = *(_QWORD *)&SubKey[4] >> 1;
        v19 = std::_List_val_std::_List_simple_types_std::shared_ptr_Print::Driver::PrinterExtensionInstallAction_____::_Sort__lambda_48055721eafb7b1d79ecfd42a7cec9a7___(
                *(_QWORD ***)SubKey,
                *(_QWORD *)&SubKey[4] >> 1);
        v9 = std::_List_val_std::_List_simple_types_std::shared_ptr_Print::Driver::PrinterExtensionInstallAction_____::_Sort__lambda_48055721eafb7b1d79ecfd42a7cec9a7___(
               &v19,
               v6 - v8);
        *v7 = std::_List_val_std::_List_simple_types_std::shared_ptr_Print::Driver::PrinterExtensionInstallAction_____::_Merge_same__lambda_48055721eafb7b1d79ecfd42a7cec9a7___(
                *v7,
                v19,
                v9);
      }
      v21 = v5;
      v10 = *(__int64 **)SubKey;
      for ( i = **(__int64 ***)SubKey; i != v10; i = (__int64 *)*i )
      {
        v20 = 0;
        v12 = i[3];
        if ( v12 )
          _InterlockedIncrement((volatile signed __int32 *)(v12 + 8));
        v20 = *((_OWORD *)i + 1);
        lambda_59ac2e359e082a145f71a712d8ff998b_::operator()((__int64 *)&v21, (const IID **)&v20);
      }
      Print::Driver::Telemetry::PrintConfigTelemetry::WriteDbgTraceInfo(
        "Print::Driver::PrinterExtensionRegistrarService::ProcessPendingInstallations",
        L"Completed a processing iteration for pending installs.");
      std::list<std::shared_ptr<Print::Driver::PrinterExtensionInstallAction>>::~list<std::shared_ptr<Print::Driver::PrinterExtensionInstallAction>>((void **)SubKey);
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
    v14 = -2147024882;
    v1 = a1;
  }
  catch ( const hr_error *v23 )
  {
    v14 = *((_DWORD *)v23 + 6);
    v1 = a1;
  }
  catch ( const PrintCore::WindowsError *v24 )
  {
    v14 = *((_DWORD *)v24 + 6);
    v1 = a1;
  }
  catch ( std::exception )
  {
    v14 = -2147467259;
    v1 = a1;
  }
  catch ( ... )
  {
    v14 = -2147418113;
    v1 = a1;
  }
  SetEvent(*(HANDLE *)(*(_QWORD *)v1 + 40LL));
  SetEvent(*(HANDLE *)(*(_QWORD *)v1 + 56LL));
  Print::Driver::Telemetry::PrintConfigTelemetry::WriteDbgTraceWarning(
    "Print::Driver::PrinterExtensionRegistrarService::WaitForThenProcessPrinterExtensionInstallations",
    L"Worker encountered exception; signaled all events to unblock waiters. hr=0x%x",
    v14);
  v13 = *(volatile signed __int32 **)(v1 + 8);
  if ( v13 && _InterlockedExchangeAdd(v13 + 2, 0xFFFFFFFF) == 1 )
  {
    (**(void (__fastcall ***)(volatile signed __int32 *))v13)(v13);
    if ( !_InterlockedDecrement(v13 + 3) )
      (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v13 + 8LL))(v13);
  }
}

```

## disassembly

```asm
0x180085910  push    rbx
0x180085912  push    rsi
0x180085913  push    rdi
0x180085914  push    r12
0x180085916  push    r14
0x180085918  push    r15
0x18008591a  sub     rsp, 0D8h
0x180085921  mov     [rsp+108h+var_88], 0FFFFFFFFFFFFFFFEh
0x18008592d  mov     rax, cs:__security_cookie
0x180085934  xor     rax, rsp
0x180085937  mov     [rsp+108h+var_48], rax
0x18008593f  mov     rdi, rcx
0x180085942  mov     [rsp+108h+var_D0], rcx
0x180085947  lea     rdx, aEnteringWorker; "Entering worker callback."
0x18008594e  lea     rcx, aPrintDriverPri_4; "Print::Driver::PrinterExtensionRegistra"...
0x180085955  call    ?WriteDbgTraceInfo@PrintConfigTelemetry@Telemetry@Driver@Print@@SAXPEADPEAGZZ; Print::Driver::Telemetry::PrintConfigTelemetry::WriteDbgTraceInfo(char *,ushort *,...)
0x18008595a  mov     [rsp+108h+var_D4], 0
0x180085962  lea     rdx, aWorkerHasStart; "Worker has started."
0x180085969  lea     rcx, aPrintDriverPri_4; "Print::Driver::PrinterExtensionRegistra"...
0x180085970  call    ?WriteDbgTraceInfo@PrintConfigTelemetry@Telemetry@Driver@Print@@SAXPEADPEAGZZ; Print::Driver::Telemetry::PrintConfigTelemetry::WriteDbgTraceInfo(char *,ushort *,...)
0x180085975  mov     [rsp+108h+var_C0], 0
0x18008597e  lea     rax, [rsp+108h+var_C0]
0x180085983  mov     [rsp+108h+var_E8], rax; void *
0x180085988  mov     r9b, 1
0x18008598b  mov     r8d, 20019h; samDesired
0x180085991  mov     rdx, [rdi]; lpSubKey
0x180085994  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18008599b  call    ?RegOpenKeyExW@Registry@Win32Adapters@@YAXPEAUHKEY__@@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@K_NAEAVRegistryHandleRAII@@@Z; Win32Adapters::Registry::RegOpenKeyExW(HKEY__ *,std::wstring const &,ulong,bool,RegistryHandleRAII &)
0x1800859a0  mov     [rsp+108h+hKey], 0
0x1800859a9  xorps   xmm0, xmm0
0x1800859ac  movups  xmmword ptr [rsp+108h+SubKey], xmm0
0x1800859b4  xorps   xmm1, xmm1
0x1800859b7  movdqu  [rsp+108h+var_58], xmm1
0x1800859c0  mov     r8d, 18h
0x1800859c6  lea     rdx, aOfflineprinter; "OfflinePrinterExtensions"
0x1800859cd  lea     rcx, [rsp+108h+SubKey]
0x1800859d5  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x1800859da  nop
0x1800859db  lea     r8, [rsp+108h+hKey]; phkResult
0x1800859e0  lea     rdx, [rsp+108h+SubKey]; lpSubKey
0x1800859e8  mov     rcx, [rsp+108h+var_C0]; hKey
0x1800859ed  call    ?RegCreateKeyW@Registry@Win32Adapters@@YAXPEAUHKEY__@@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAVRegistryHandleRAII@@@Z; Win32Adapters::Registry::RegCreateKeyW(HKEY__ *,std::wstring const &,RegistryHandleRAII &)
0x1800859f2  nop
0x1800859f3  lea     rcx, [rsp+108h+SubKey]
0x1800859fb  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180085a00  lea     rdx, aWorkerHasAcces; "Worker has access to necessary parent k"...
0x180085a07  lea     rcx, aPrintDriverPri_4; "Print::Driver::PrinterExtensionRegistra"...
0x180085a0e  call    ?WriteDbgTraceInfo@PrintConfigTelemetry@Telemetry@Driver@Print@@SAXPEADPEAGZZ; Print::Driver::Telemetry::PrintConfigTelemetry::WriteDbgTraceInfo(char *,ushort *,...)
0x180085a13  mov     rcx, [rdi]
0x180085a16  mov     rax, [rcx+20h]
0x180085a1a  mov     [rsp+108h+Handles], rax
0x180085a1f  mov     rax, [rcx+30h]
0x180085a23  mov     [rsp+108h+var_90], rax
0x180085a28  lea     r12, ?s_printerExtensionRegistrarCS@PrinterExtensionRegistrar@Driver@Print@@2VCriticalSectionRAII@@A; CriticalSectionRAII Print::Driver::PrinterExtensionRegistrar::s_printerExtensionRegistrarCS
0x180085a2f  lea     rdx, aWorkerHasBeenS; "Worker has been signaled."
0x180085a36  lea     rcx, aPrintDriverPri_4; "Print::Driver::PrinterExtensionRegistra"...
0x180085a3d  call    ?WriteDbgTraceInfo@PrintConfigTelemetry@Telemetry@Driver@Print@@SAXPEADPEAGZZ; Print::Driver::Telemetry::PrintConfigTelemetry::WriteDbgTraceInfo(char *,ushort *,...)
0x180085a42  mov     r9, [rdi]
0x180085a45  mov     r9, [r9+20h]; unsigned int
0x180085a49  lea     rcx, [rsp+108h+hKey]; this
0x180085a4e  call    ?RegNotifyChangeKeyValue@Registry@Win32Adapters@@YAXAEAVRegistryHandleRAII@@_NKPEAX1@Z; Win32Adapters::Registry::RegNotifyChangeKeyValue(RegistryHandleRAII &,bool,ulong,void *,bool)
0x180085a53  mov     r15, [rdi]
0x180085a56  mov     [rsp+108h+var_80], r12
0x180085a5e  mov     rcx, r12; lpCriticalSection
0x180085a61  call    cs:__imp_EnterCriticalSection
0x180085a68  nop     dword ptr [rax+rax+00h]
0x180085a6d  nop
0x180085a6e  lea     rdx, aBeginningAProc; "Beginning a processing iteration for pe"...
0x180085a75  lea     rcx, aPrintDriverPri_9; "Print::Driver::PrinterExtensionRegistra"...
0x180085a7c  call    ?WriteDbgTraceInfo@PrintConfigTelemetry@Telemetry@Driver@Print@@SAXPEADPEAGZZ; Print::Driver::Telemetry::PrintConfigTelemetry::WriteDbgTraceInfo(char *,ushort *,...)
0x180085a81  lea     rdx, [rsp+108h+SubKey]
0x180085a89  mov     rcx, r15
0x180085a8c  call    ?GetPendingInstallations@PrinterExtensionRegistrarService@Driver@Print@@AEAA?AV?$list@V?$shared_ptr@VPrinterExtensionInstallAction@Driver@Print@@@std@@V?$allocator@V?$shared_ptr@VPrinterExtensionInstallAction@Driver@Print@@@std@@@2@@std@@XZ; Print::Driver::PrinterExtensionRegistrarService::GetPendingInstallations(void)
0x180085a91  nop
0x180085a92  mov     rbx, qword ptr [rsp+108h+SubKey+8]
0x180085a9a  mov     rax, rbx
0x180085a9d  test    rbx, rbx
0x180085aa0  jz      short loc_180085AF3
0x180085aa2  cmp     rax, 1
0x180085aa6  jz      short loc_180085AF3
0x180085aa8  mov     r14, qword ptr [rsp+108h+SubKey]
0x180085ab0  mov     rsi, rbx
0x180085ab3  shr     rsi, 1
0x180085ab6  mov     r8b, [rsp+108h+var_D8]
0x180085abb  mov     rdx, rsi
0x180085abe  mov     rcx, r14
0x180085ac1  call    std___List_val_std___List_simple_types_std__shared_ptr_Print__Driver__PrinterExtensionInstallAction________Sort__lambda_48055721eafb7b1d79ecfd42a7cec9a7___
0x180085ac6  mov     [rsp+108h+var_B8], rax
0x180085acb  sub     rbx, rsi
0x180085ace  mov     r8b, [rsp+108h+var_D8]
0x180085ad3  mov     rdx, rbx
0x180085ad6  lea     rcx, [rsp+108h+var_B8]
0x180085adb  call    std___List_val_std___List_simple_types_std__shared_ptr_Print__Driver__PrinterExtensionInstallAction________Sort__lambda_48055721eafb7b1d79ecfd42a7cec9a7___
0x180085ae0  mov     r8, rax
0x180085ae3  mov     rdx, [rsp+108h+var_B8]
0x180085ae8  mov     rcx, [r14]
0x180085aeb  call    std___List_val_std___List_simple_types_std__shared_ptr_Print__Driver__PrinterExtensionInstallAction________Merge_same__lambda_48055721eafb7b1d79ecfd42a7cec9a7___
0x180085af0  mov     [r14], rax
0x180085af3  mov     [rsp+108h+var_A0], r15
0x180085af8  mov     rsi, qword ptr [rsp+108h+SubKey]
0x180085b00  mov     rbx, [rsi]
0x180085b03  cmp     rbx, rsi
0x180085b06  jnz     loc_180085BD3
0x180085b0c  lea     rdx, aCompletedAProc; "Completed a processing iteration for pe"...
0x180085b13  lea     rcx, aPrintDriverPri_9; "Print::Driver::PrinterExtensionRegistra"...
0x180085b1a  call    ?WriteDbgTraceInfo@PrintConfigTelemetry@Telemetry@Driver@Print@@SAXPEADPEAGZZ; Print::Driver::Telemetry::PrintConfigTelemetry::WriteDbgTraceInfo(char *,ushort *,...)
0x180085b1f  nop
0x180085b20  lea     rcx, [rsp+108h+SubKey]
0x180085b28  call    ??1?$list@V?$shared_ptr@VPrinterExtensionInstallAction@Driver@Print@@@std@@V?$allocator@V?$shared_ptr@VPrinterExtensionInstallAction@Driver@Print@@@std@@@2@@std@@QEAA@XZ; std::list<std::shared_ptr<Print::Driver::PrinterExtensionInstallAction>>::~list<std::shared_ptr<Print::Driver::PrinterExtensionInstallAction>>(void)
0x180085b2d  nop
0x180085b2e  mov     rcx, r12; lpCriticalSection
0x180085b31  call    cs:__imp_LeaveCriticalSection
0x180085b38  nop     dword ptr [rax+rax+00h]
0x180085b3d  mov     rcx, [rdi]
0x180085b40  mov     rcx, [rcx+28h]; hEvent
0x180085b44  call    cs:__imp_SetEvent
0x180085b4b  nop     dword ptr [rax+rax+00h]
0x180085b50  or      r9d, 0FFFFFFFFh; dwMilliseconds
0x180085b54  xor     r8d, r8d; bWaitAll
0x180085b57  lea     rdx, [rsp+108h+Handles]; lpHandles
0x180085b5c  lea     ecx, [r8+2]; nCount
0x180085b60  call    cs:__imp_WaitForMultipleObjects
0x180085b67  nop     dword ptr [rax+rax+00h]
0x180085b6c  test    eax, eax
0x180085b6e  jz      loc_180085A2F
0x180085b74  mov     rcx, [rdi]
0x180085b77  mov     rcx, [rcx+38h]; hEvent
0x180085b7b  call    cs:__imp_SetEvent
0x180085b82  nop     dword ptr [rax+rax+00h]
0x180085b87  lea     rdx, aWorkerSignaled; "Worker signaled stopped event."
0x180085b8e  lea     rcx, aPrintDriverPri_4; "Print::Driver::PrinterExtensionRegistra"...
0x180085b95  call    ?WriteDbgTraceInfo@PrintConfigTelemetry@Telemetry@Driver@Print@@SAXPEADPEAGZZ; Print::Driver::Telemetry::PrintConfigTelemetry::WriteDbgTraceInfo(char *,ushort *,...)
0x180085b9a  nop
0x180085b9b  mov     rcx, [rsp+108h+hKey]; hKey
0x180085ba0  test    rcx, rcx
0x180085ba3  jz      short loc_180085BBA
0x180085ba5  call    cs:__imp_RegCloseKey
0x180085bac  nop     dword ptr [rax+rax+00h]
0x180085bb1  mov     [rsp+108h+hKey], 0
0x180085bba  mov     rcx, [rsp+108h+var_C0]; hKey
0x180085bbf  test    rcx, rcx
0x180085bc2  jz      short loc_180085BD1
0x180085bc4  call    cs:__imp_RegCloseKey
0x180085bcb  nop     dword ptr [rax+rax+00h]
0x180085bd0  nop
0x180085bd1  jmp     short loc_180085C17
0x180085bd3  xorps   xmm0, xmm0
0x180085bd6  movdqu  [rsp+108h+var_B0], xmm0
0x180085bdc  mov     rax, [rbx+18h]
0x180085be0  test    rax, rax
0x180085be3  jz      short loc_180085BE9
0x180085be5  lock inc dword ptr [rax+8]
0x180085be9  mov     rax, [rbx+10h]
0x180085bed  mov     qword ptr [rsp+108h+var_B0], rax
0x180085bf2  mov     rax, [rbx+18h]
0x180085bf6  mov     qword ptr [rsp+108h+var_B0+8], rax
0x180085bfb  lea     rdx, [rsp+108h+var_B0]
0x180085c00  lea     rcx, [rsp+108h+var_A0]
0x180085c05  call    _lambda_59ac2e359e082a145f71a712d8ff998b___operator__
0x180085c0a  mov     rbx, [rbx]
0x180085c0d  jmp     loc_180085B03
0x180085c12  mov     rdi, [rsp+108h+var_D0]
0x180085c17  mov     rcx, [rdi]
0x180085c1a  mov     rcx, [rcx+28h]; hEvent
0x180085c1e  call    cs:__imp_SetEvent
0x180085c25  nop     dword ptr [rax+rax+00h]
0x180085c2a  mov     rcx, [rdi]
0x180085c2d  mov     rcx, [rcx+38h]; hEvent
0x180085c31  call    cs:__imp_SetEvent
0x180085c38  nop     dword ptr [rax+rax+00h]
0x180085c3d  mov     r8d, [rsp+108h+var_D4]
0x180085c42  lea     rdx, aWorkerEncounte; "Worker encountered exception; signaled "...
0x180085c49  lea     rcx, aPrintDriverPri_4; "Print::Driver::PrinterExtensionRegistra"...
0x180085c50  call    ?WriteDbgTraceWarning@PrintConfigTelemetry@Telemetry@Driver@Print@@SAXPEADPEAGZZ; Print::Driver::Telemetry::PrintConfigTelemetry::WriteDbgTraceWarning(char *,ushort *,...)
0x180085c55  nop
0x180085c56  mov     rbx, [rdi+8]
0x180085c5a  test    rbx, rbx
0x180085c5d  jz      short loc_180085C96
0x180085c5f  or      edi, 0FFFFFFFFh
0x180085c62  mov     eax, edi
0x180085c64  lock xadd [rbx+8], eax
0x180085c69  add     eax, edi
0x180085c6b  jnz     short loc_180085C96
0x180085c6d  mov     rax, [rbx]
0x180085c70  mov     rcx, rbx
0x180085c73  mov     rax, [rax]
0x180085c76  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180085c7b  mov     eax, edi
0x180085c7d  lock xadd [rbx+0Ch], eax
0x180085c82  add     eax, edi
0x180085c84  jnz     short loc_180085C96
0x180085c86  mov     rax, [rbx]
0x180085c89  mov     rcx, rbx
0x180085c8c  mov     rax, [rax+8]
0x180085c90  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180085c95  nop
0x180085c96  mov     rcx, [rsp+108h+var_48]
0x180085c9e  xor     rcx, rsp; StackCookie
0x180085ca1  call    __security_check_cookie
0x180085ca6  add     rsp, 0D8h
0x180085cad  pop     r15
0x180085caf  pop     r14
0x180085cb1  pop     r12
0x180085cb3  pop     rdi
0x180085cb4  pop     rsi
0x180085cb5  pop     rbx
0x180085cb6  retn
0x180085cb8  jmp     loc_180085C12
0x180085cbd  jmp     loc_180085C12
0x180085cc2  jmp     loc_180085C12
```
