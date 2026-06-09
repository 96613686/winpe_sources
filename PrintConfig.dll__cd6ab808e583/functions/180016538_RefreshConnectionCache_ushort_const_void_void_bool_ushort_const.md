# RefreshConnectionCache(ushort const *,void *,void *,bool,ushort const *)

- ea: `0x180016538`
- end: `0x180016da1`
- name: `?RefreshConnectionCache@@YAJPEBGPEAX1_N0@Z`
- size: `2153`
- prototype: `__int64 __usercall@<rax>(const unsigned __int16 *@<rcx>, HANDLE hPrinter@<rdx>, HANDLE@<r8>, bool@<r9b>, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `15`
- tags: `file_ops, registry_config, loader_planting, installer_update`

## callers

- `0x180015604`

## callees

- `0x180003310`
- `0x1800060ec`
- `0x18000f770`
- `0x180012f3c`
- `0x180013cfc`
- `0x180013ea4`
- `0x180016538`
- `0x180017118`
- `0x180017c00`
- `0x1800183a0`
- `0x1800183f8`
- `0x180038ed8`
- `0x180038fb4`
- `0x180153110`
- `0x1801c3010`

## import_xrefs

- `KERNEL32!FreeLibrary` at `0x180016666`
- `KERNEL32!FreeLibrary` at `0x18001687b`
- `KERNEL32!FreeLibrary` at `0x1800168ef`
- `KERNEL32!FreeLibrary` at `0x180016d44`
- `KERNEL32!FreeLibrary` at `0x180016666`
- `KERNEL32!FreeLibrary` at `0x18001687b`
- `KERNEL32!FreeLibrary` at `0x1800168ef`
- `KERNEL32!FreeLibrary` at `0x180016d44`
- `ADVAPI32!RegCloseKey` at `0x1800165aa`
- `ADVAPI32!RegCloseKey` at `0x18001663c`
- `ADVAPI32!RegCloseKey` at `0x180016d85`
- `ADVAPI32!RegCloseKey` at `0x1800165aa`
- `ADVAPI32!RegCloseKey` at `0x18001663c`
- `ADVAPI32!RegCloseKey` at `0x180016d85`
- `ADVAPI32!RegSetValueExW` at `0x1800167b4`
- `ADVAPI32!RegSetValueExW` at `0x18001683f`
- `ADVAPI32!RegSetValueExW` at `0x1800167b4`
- `ADVAPI32!RegSetValueExW` at `0x18001683f`
- `ADVAPI32!RegGetValueW` at `0x180016608`
- `ADVAPI32!RegGetValueW` at `0x18001671c`
- `ADVAPI32!RegGetValueW` at `0x180016608`
- `ADVAPI32!RegGetValueW` at `0x18001671c`
- `ADVAPI32!RegDeleteValueW` at `0x180016d10`
- `ADVAPI32!RegDeleteValueW` at `0x180016d10`
- `WINSPOOL!GetPrinterDataW` at `0x180016698`
- `WINSPOOL!GetPrinterDataW` at `0x180016698`

## string_xrefs

- `0x1800165fb`: `CachedChangeID`
- `0x1800167a9`: `CachedChangeID`
- `0x180016691`: `V4_Config_ChangeID`
- `0x1800166d1`: `RefreshConnectionCache`
- `0x180016770`: `RefreshConnectionCache`
- `0x18001680c`: `RefreshConnectionCache`
- `0x18001689d`: `RefreshConnectionCache`
- `0x180016d53`: `RefreshConnectionCache`
- `0x18001670f`: `FailedSyncAttempts`
- `0x180016834`: `FailedSyncAttempts`
- `0x180016d05`: `FailedSyncAttempts`
- `0x180016769`: `Cache Refresh attempt %d of %d.`
- `0x180016805`: `Already failed to refresh cache %d times for %ws. Skipping.`
- `0x180016896`: `Performing a cache refresh for %ws!`
- `0x1800169d5`: `PCLXL.dll`
- `0x180016a1c`: `PCL5ERES.dll`
- `0x180016a63`: `PCL4RES.dll`
- `0x180016aaa`: `PCL5URES.dll`
- `0x180016b78`: `DevmodeMap.xml`
- `0x180016bb8`: `QueuePropertyMap.xml`
- `0x180016bfb`: `PDC.xml`
- `0x180016d5e`: `Successful connection cache refresh for %ws!`
- `0x180016d6f`: `Failed to refresh connection cache for %ws (hr: 0x%x)!`
- `0x180016c8f`: `PrintConfig::CConfigManager::RetrieveConnectionLanguageDatabase`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
__int64 __fastcall RefreshConnectionCache(
        const unsigned __int16 *a1,
        HANDLE hPrinter,
        HANDLE a3,
        char a4,
        WCHAR *pName)
{
  int v9; // ebx
  LSTATUS ValueW; // eax
  HANDLE v11; // rcx
  signed int PrinterDataW; // eax
  LSTATUS v13; // eax
  int v14; // r8d
  int updated; // ebx
  LSTATUS v16; // eax
  unsigned int v17; // edx
  LSTATUS v18; // eax
  char *v19; // rsi
  int v20; // eax
  void *v21; // rbx
  int v22; // ebx
  unsigned int v23; // edx
  HKEY hKey; // [rsp+50h] [rbp-51h] BYREF
  BYTE Data[4]; // [rsp+58h] [rbp-49h] BYREF
  DWORD pcbNeeded; // [rsp+5Ch] [rbp-45h] BYREF
  DWORD pType; // [rsp+60h] [rbp-41h] BYREF
  BYTE pData[12]; // [rsp+64h] [rbp-3Dh] BYREF
  HMODULE hLibModule[2]; // [rsp+70h] [rbp-31h] BYREF
  void (*v31)(void); // [rsp+80h] [rbp-21h]
  int pvData; // [rsp+90h] [rbp-11h] BYREF
  void *Block; // [rsp+98h] [rbp-9h] BYREF
  _QWORD v34[10]; // [rsp+A0h] [rbp-1h] BYREF
  int FileAndFilenameFromServer; // [rsp+118h] [rbp+77h] BYREF

  v34[1] = -2;
  pType = 0;
  pcbNeeded = 0;
  pvData = 0;
  *(_DWORD *)pData = 0;
  *(_DWORD *)Data = 0;
  FileAndFilenameFromServer = 0;
  hKey = 0;
  RevertToPrinterRAII::RevertToPrinterRAII((RevertToPrinterRAII *)hLibModule, &FileAndFilenameFromServer);
  v9 = FileAndFilenameFromServer;
  if ( FileAndFilenameFromServer < 0
    || (v9 = OpenConnectionRegistryKey(a1, 0x2001Fu, 0, &hKey, 0), FileAndFilenameFromServer = v9, v9 < 0) )
  {
    if ( hKey )
    {
      RegCloseKey(hKey);
      hKey = 0;
    }
  }
  else
  {
    pcbNeeded = 4;
    ValueW = RegGetValueW(hKey, 0, L"CachedChangeID", 0x18u, &pType, &pvData, &pcbNeeded);
    if ( ValueW )
    {
      if ( ValueW > 0 )
        v9 = (unsigned __int16)ValueW | 0x80070000;
      else
        v9 = ValueW;
      goto LABEL_9;
    }
    if ( pType != 4 )
    {
      v9 = -2147418113;
LABEL_9:
      FileAndFilenameFromServer = v9;
    }
  }
  if ( v31 && hLibModule[1] )
    v31();
  if ( hLibModule[0] )
    FreeLibrary(hLibModule[0]);
  if ( v9 >= 0 )
  {
    v11 = a3;
    if ( !a4 )
      v11 = hPrinter;
    PrinterDataW = GetPrinterDataW(v11, (LPWSTR)L"V4_Config_ChangeID", &pType, pData, 4u, &pcbNeeded);
    if ( PrinterDataW )
    {
      if ( PrinterDataW > 0 )
        v9 = (unsigned __int16)PrinterDataW | 0x80070000;
      else
        v9 = PrinterDataW;
      FileAndFilenameFromServer = v9;
    }
    else if ( *(_DWORD *)pData != pvData )
    {
      Print::Driver::Telemetry::PrintConfigTelemetry::WriteDbgTraceInfo(
        "RefreshConnectionCache",
        L"Change ID has changed!");
      a4 = 1;
      goto LABEL_26;
    }
  }
  if ( a4 )
  {
LABEL_26:
    *(_DWORD *)Data = 0;
    goto LABEL_42;
  }
  if ( v9 >= 0 )
  {
    pcbNeeded = 4;
    v13 = RegGetValueW(hKey, 0, L"FailedSyncAttempts", 0x18u, &pType, Data, &pcbNeeded);
    if ( v13 == 2 || pType != 4 )
    {
      v14 = 0;
      *(_DWORD *)Data = 0;
    }
    else
    {
      if ( v13 )
      {
        if ( v13 > 0 )
          v9 = (unsigned __int16)v13 | 0x80070000;
        else
          v9 = v13;
        FileAndFilenameFromServer = v9;
      }
      v14 = *(_DWORD *)Data;
    }
    if ( v9 >= 0 && (unsigned int)(v14 - 1) <= 1 )
    {
      a4 = 1;
      Print::Driver::Telemetry::PrintConfigTelemetry::WriteDbgTraceInfo(
        "RefreshConnectionCache",
        L"Cache Refresh attempt %d of %d.",
        (unsigned int)(v14 + 1),
        3);
    }
  }
LABEL_42:
  RevertToPrinterRAII::RevertToPrinterRAII((RevertToPrinterRAII *)hLibModule, &FileAndFilenameFromServer);
  updated = FileAndFilenameFromServer;
  if ( FileAndFilenameFromServer >= 0 )
  {
    v16 = RegSetValueExW(hKey, L"CachedChangeID", 0, 4u, pData, 4u);
    if ( v16 )
    {
      if ( v16 > 0 )
        updated = (unsigned __int16)v16 | 0x80070000;
      else
        updated = v16;
      FileAndFilenameFromServer = updated;
    }
    if ( updated >= 0 )
    {
      updated = UpdateConnectionStatusFlags_nothrow((struct RegistryHandleRAII *)&hKey, v17, 0);
      FileAndFilenameFromServer = updated;
      if ( updated >= 0 )
      {
        if ( *(_DWORD *)Data >= 3u )
        {
          Print::Driver::Telemetry::PrintConfigTelemetry::WriteDbgTraceInfo(
            "RefreshConnectionCache",
            L"Already failed to refresh cache %d times for %ws. Skipping.",
            3,
            a1);
          updated = -2147467259;
          FileAndFilenameFromServer = -2147467259;
        }
        else
        {
          ++*(_DWORD *)Data;
        }
        v18 = RegSetValueExW(hKey, L"FailedSyncAttempts", 0, 4u, Data, 4u);
        if ( v18 )
        {
          if ( v18 > 0 )
            updated = (unsigned __int16)v18 | 0x80070000;
          else
            updated = v18;
          FileAndFilenameFromServer = updated;
        }
      }
    }
  }
  if ( v31 && hLibModule[1] )
    v31();
  if ( hLibModule[0] )
    FreeLibrary(hLibModule[0]);
  if ( a4 && updated >= 0 )
  {
    Print::Driver::Telemetry::PrintConfigTelemetry::WriteDbgTraceInfo(
      "RefreshConnectionCache",
      L"Performing a cache refresh for %ws!",
      a1);
    RevertToPrinterRAII::RevertToPrinterRAII((RevertToPrinterRAII *)hLibModule, &FileAndFilenameFromServer);
    updated = FileAndFilenameFromServer;
    if ( FileAndFilenameFromServer >= 0 )
      RemoveAllConnectionFiles(hKey);
    if ( v31 && hLibModule[1] )
      v31();
    if ( hLibModule[0] )
      FreeLibrary(hLibModule[0]);
    if ( updated >= 0 )
    {
      updated = GetFileAndFilenameFromServer(
                  a3,
                  hKey,
                  L"ClassLanguageResource",
                  L"ClassLangResourceName",
                  L"Resource_Base",
                  0,
                  1);
      FileAndFilenameFromServer = updated;
      if ( updated >= 0 )
      {
        updated = GetFileAndFilenameFromServer(
                    a3,
                    hKey,
                    L"DerivedLanguageResource",
                    L"DerivedLangResourceName",
                    L"Resource_Derived",
                    0,
                    1);
        FileAndFilenameFromServer = updated;
        if ( updated >= 0 )
        {
          updated = GetFileAndFilenameFromServer(
                      a3,
                      hKey,
                      L"SystemResource",
                      L"SystemResourceName",
                      L"Resource_System",
                      0,
                      1);
          FileAndFilenameFromServer = updated;
          if ( updated >= 0 )
          {
            updated = GetFileFromServerAsGivenName(
                        a3,
                        hKey,
                        L"SystemResourcePCLXL",
                        L"PCLXL.dll",
                        L"Resource_System_PCLXL",
                        0,
                        1,
                        0,
                        0);
            FileAndFilenameFromServer = updated;
            if ( updated >= 0 )
            {
              updated = GetFileFromServerAsGivenName(
                          a3,
                          hKey,
                          L"SystemResourcePCL5ERES",
                          L"PCL5ERES.dll",
                          L"Resource_System_PCL5ERES",
                          0,
                          1,
                          0,
                          0);
              FileAndFilenameFromServer = updated;
              if ( updated >= 0 )
              {
                updated = GetFileFromServerAsGivenName(
                            a3,
                            hKey,
                            L"SystemResourcePCL4RES",
                            L"PCL4RES.dll",
                            L"Resource_System_PCL4RES",
                            0,
                            1,
                            0,
                            0);
                FileAndFilenameFromServer = updated;
                if ( updated >= 0 )
                {
                  updated = GetFileFromServerAsGivenName(
                              a3,
                              hKey,
                              L"SystemResourcePCL5URES",
                              L"PCL5URES.dll",
                              L"Resource_System_PCL5URES",
                              0,
                              1,
                              0,
                              0);
                  FileAndFilenameFromServer = updated;
                  if ( updated >= 0 )
                  {
                    updated = GetFileFromServerAsGivenName(
                                a3,
                                hKey,
                                L"ConstraintScript",
                                L"Constraints.js",
                                L"ConstraintScript",
                                0,
                                0,
                                L"CatalogForConstraints",
                                0);
                    FileAndFilenameFromServer = updated;
                    if ( updated >= 0 )
                    {
                      updated = GetFileFromServerAsGivenName(
                                  a3,
                                  hKey,
                                  L"PropertyBag",
                                  L"Property.bag",
                                  L"PropertyBag",
                                  0,
                                  0,
                                  0,
                                  0);
                      FileAndFilenameFromServer = updated;
                      if ( updated >= 0 )
                      {
                        updated = GetFileFromServerAsGivenName(
                                    a3,
                                    hKey,
                                    L"DevmodeMap",
                                    L"DevmodeMap.xml",
                                    L"DevmodeMap",
                                    0,
                                    0,
                                    0,
                                    0);
                        FileAndFilenameFromServer = updated;
                        if ( updated >= 0 )
                        {
                          updated = GetFileFromServerAsGivenName(
                                      a3,
                                      hKey,
                                      L"QueuePropertyMap",
                                      L"QueuePropertyMap.xml",
                                      L"QueueProperties",
                                      0,
                                      0,
                                      0,
                                      0);
                          FileAndFilenameFromServer = updated;
                          if ( updated >= 0 )
                          {
                            updated = GetFileFromServerAsGivenName(
                                        a3,
                                        hKey,
                                        L"PrintDeviceCapabilities",
                                        L"PDC.xml",
                                        L"PrintDeviceCapabilities",
                                        0,
                                        0,
                                        0,
                                        0);
                            FileAndFilenameFromServer = updated;
                            if ( updated >= 0 )
                            {
                              updated = EnsureWowPrintConfigPresent(a3, hKey, pName);
                              FileAndFilenameFromServer = updated;
                            }
                          }
                        }
                      }
                    }
                  }
                }
              }
            }
          }
        }
      }
    }
  }
  Block = 0;
  if ( a4 && updated >= 0 )
  {
    v34[0] = a1;
    hLibModule[0] = (HMODULE)v34;
    hLibModule[1] = (HMODULE)&Block;
    if ( (int)ExceptionBoundary__lambda_5648f5919d1758734759f438906712d7_(hLibModule) >= 0 )
    {
      v19 = (char *)Block;
      v34[0] = Block;
      v20 = ExceptionBoundary__lambda_a402ae3cd7da9c177cf78f147a0fd8c2_(v34);
      if ( v20 < 0 )
      {
        *(_OWORD *)hLibModule = *(_OWORD *)(v19 + 8);
        Print::Driver::Telemetry::PrintConfigTelemetry::WriteDbgTraceWarning(
          "PrintConfig::CConfigManager::RetrieveConnectionLanguageDatabase",
          L"Failed to retrieve connection language database for printer \"%ws\" (hr: 0x%x)",
          hLibModule,
          (unsigned int)v20);
      }
    }
    FileAndFilenameFromServer = GetFileAndFilenameFromServer(
                                  a3,
                                  hKey,
                                  L"MergedData",
                                  L"MergedDataName",
                                  L"MergedDataFile",
                                  1,
                                  0);
  }
  v21 = Block;
  if ( Block )
  {
    PrintConfig::CConfigManager::~CConfigManager((PrintConfig::CConfigManager *)Block);
    operator delete(v21);
  }
  RevertToPrinterRAII::RevertToPrinterRAII((RevertToPrinterRAII *)hLibModule, &FileAndFilenameFromServer);
  v22 = FileAndFilenameFromServer;
  if ( FileAndFilenameFromServer >= 0 )
  {
    RegDeleteValueW(hKey, L"FailedSyncAttempts");
    v22 = UpdateConnectionStatusFlags_nothrow((struct RegistryHandleRAII *)&hKey, v23, 1);
  }
  if ( v31 && hLibModule[1] )
    v31();
  if ( hLibModule[0] )
    FreeLibrary(hLibModule[0]);
  if ( a4 )
  {
    if ( v22 < 0 )
      Print::Driver::Telemetry::PrintConfigTelemetry::WriteDbgTraceWarning(
        "RefreshConnectionCache",
        L"Failed to refresh connection cache for %ws (hr: 0x%x)!",
        a1,
        (unsigned int)v22);
    else
      Print::Driver::Telemetry::PrintConfigTelemetry::WriteDbgTraceInfo(
        "RefreshConnectionCache",
        L"Successful connection cache refresh for %ws!",
        a1);
  }
  if ( hKey )
    RegCloseKey(hKey);
  return (unsigned int)v22;
}

```

## disassembly

```asm
0x180016538  push    rbp
0x18001653a  push    rbx
0x18001653b  push    rsi
0x18001653c  push    rdi
0x18001653d  push    r12
0x18001653f  push    r13
0x180016541  push    r14
0x180016543  push    r15
0x180016545  lea     rbp, [rsp-17h]
0x18001654a  sub     rsp, 0B8h
0x180016551  mov     [rbp+4Fh+var_48], 0FFFFFFFFFFFFFFFEh
0x180016559  mov     r14b, r9b
0x18001655c  mov     rdi, r8
0x18001655f  mov     rsi, rdx
0x180016562  mov     r15, rcx
0x180016565  xor     r12d, r12d
0x180016568  mov     [rbp+4Fh+pType], r12d
0x18001656c  mov     [rbp+4Fh+pcbNeeded], r12d
0x180016570  mov     [rbp+4Fh+var_60], r12d
0x180016574  mov     dword ptr [rbp+4Fh+pData], r12d
0x180016578  mov     dword ptr [rbp+4Fh+Data], r12d
0x18001657c  mov     [rbp+4Fh+arg_18], r12d
0x180016580  mov     [rbp+4Fh+hKey], r12
0x180016584  lea     rdx, [rbp+4Fh+arg_18]; int *
0x180016588  lea     rcx, [rbp+4Fh+hLibModule]; this
0x18001658c  call    ??0RevertToPrinterRAII@@QEAA@PEAJ@Z; RevertToPrinterRAII::RevertToPrinterRAII(long *)
0x180016591  lea     r13d, [r12+4]
0x180016596  mov     ebx, [rbp+4Fh+arg_18]
0x180016599  test    ebx, ebx
0x18001659b  js      loc_180016633
0x1800165a1  mov     rcx, [rbp+4Fh+hKey]; hKey
0x1800165a5  test    rcx, rcx
0x1800165a8  jz      short loc_1800165B4
0x1800165aa  call    cs:__imp_RegCloseKey
0x1800165b0  mov     [rbp+4Fh+hKey], r12
0x1800165b4  mov     [rsp+0F0h+pdwType], r12; bool *
0x1800165b9  lea     r9, [rbp+4Fh+hKey]; HKEY *
0x1800165bd  xor     r8d, r8d; bool
0x1800165c0  mov     edx, 2001Fh; samDesired
0x1800165c5  mov     rcx, r15; unsigned __int16 *
0x1800165c8  call    ?OpenConnectionRegistryKey@@YAJPEBGK_NPEAPEAUHKEY__@@PEA_N@Z; OpenConnectionRegistryKey(ushort const *,ulong,bool,HKEY__ * *,bool *)
0x1800165cd  mov     ebx, eax
0x1800165cf  mov     [rbp+4Fh+arg_18], eax
0x1800165d2  test    eax, eax
0x1800165d4  js      short loc_180016633
0x1800165d6  mov     [rbp+4Fh+pcbNeeded], r13d
0x1800165da  lea     rax, [rbp+4Fh+pcbNeeded]
0x1800165de  mov     [rsp+0F0h+pcbData], rax; pcbData
0x1800165e3  lea     rax, [rbp+4Fh+var_60]
0x1800165e7  mov     [rsp+0F0h+pvData], rax; pvData
0x1800165ec  lea     rax, [rbp+4Fh+pType]
0x1800165f0  mov     [rsp+0F0h+pdwType], rax; pdwType
0x1800165f5  mov     r9d, 18h; dwFlags
0x1800165fb  lea     r8, ValueName; "CachedChangeID"
0x180016602  xor     edx, edx; lpSubKey
0x180016604  mov     rcx, [rbp+4Fh+hKey]; hkey
0x180016608  call    cs:__imp_RegGetValueW
0x18001660e  test    eax, eax
0x180016610  jz      short loc_180016623
0x180016612  jg      short loc_180016618
0x180016614  mov     ebx, eax
0x180016616  jmp     short loc_18001662E
0x180016618  movzx   ebx, ax
0x18001661b  or      ebx, 80070000h
0x180016621  jmp     short loc_18001662E
0x180016623  cmp     [rbp+4Fh+pType], r13d
0x180016627  jz      short loc_180016646
0x180016629  mov     ebx, 8000FFFFh
0x18001662e  mov     [rbp+4Fh+arg_18], ebx
0x180016631  jmp     short loc_180016646
0x180016633  mov     rcx, [rbp+4Fh+hKey]; hKey
0x180016637  test    rcx, rcx
0x18001663a  jz      short loc_180016646
0x18001663c  call    cs:__imp_RegCloseKey
0x180016642  mov     [rbp+4Fh+hKey], r12
0x180016646  mov     rax, [rbp+4Fh+var_70]
0x18001664a  test    rax, rax
0x18001664d  jz      short loc_18001665D
0x18001664f  mov     rcx, [rbp+4Fh+hLibModule+8]
0x180016653  test    rcx, rcx
0x180016656  jz      short loc_18001665D
0x180016658  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001665d  mov     rcx, [rbp+4Fh+hLibModule]; hLibModule
0x180016661  test    rcx, rcx
0x180016664  jz      short loc_18001666D
0x180016666  call    cs:__imp_FreeLibrary
0x18001666c  nop
0x18001666d  test    ebx, ebx
0x18001666f  js      short loc_1800166B4
0x180016671  mov     rcx, rdi
0x180016674  test    r14b, r14b
0x180016677  cmovz   rcx, rsi; hPrinter
0x18001667b  lea     rax, [rbp+4Fh+pcbNeeded]
0x18001667f  mov     [rsp+0F0h+pvData], rax; pcbNeeded
0x180016684  mov     dword ptr [rsp+0F0h+pdwType], r13d; nSize
0x180016689  lea     r9, [rbp+4Fh+pData]; pData
0x18001668d  lea     r8, [rbp+4Fh+pType]; pType
0x180016691  lea     rdx, aV4ConfigChange; "V4_Config_ChangeID"
0x180016698  call    cs:__imp_GetPrinterDataW
0x18001669e  test    eax, eax
0x1800166a0  jz      short loc_1800166C2
0x1800166a2  jg      short loc_1800166A8
0x1800166a4  mov     ebx, eax
0x1800166a6  jmp     short loc_1800166B1
0x1800166a8  movzx   ebx, ax
0x1800166ab  or      ebx, 80070000h
0x1800166b1  mov     [rbp+4Fh+arg_18], ebx
0x1800166b4  test    r14b, r14b
0x1800166b7  jz      short loc_1800166E2
0x1800166b9  mov     dword ptr [rbp+4Fh+Data], r12d
0x1800166bd  jmp     loc_18001677C
0x1800166c2  mov     eax, [rbp+4Fh+var_60]
0x1800166c5  cmp     dword ptr [rbp+4Fh+pData], eax
0x1800166c8  jz      short loc_1800166B4
0x1800166ca  lea     rdx, aChangeIdHasCha; "Change ID has changed!"
0x1800166d1  lea     rcx, aRefreshconnect; "RefreshConnectionCache"
0x1800166d8  call    ?WriteDbgTraceInfo@PrintConfigTelemetry@Telemetry@Driver@Print@@SAXPEADPEAGZZ; Print::Driver::Telemetry::PrintConfigTelemetry::WriteDbgTraceInfo(char *,ushort *,...)
0x1800166dd  mov     r14b, 1
0x1800166e0  jmp     short loc_1800166B9
0x1800166e2  test    ebx, ebx
0x1800166e4  js      loc_18001677C
0x1800166ea  mov     [rbp+4Fh+pcbNeeded], r13d
0x1800166ee  lea     rax, [rbp+4Fh+pcbNeeded]
0x1800166f2  mov     [rsp+0F0h+pcbData], rax; pcbData
0x1800166f7  lea     rax, [rbp+4Fh+Data]
0x1800166fb  mov     [rsp+0F0h+pvData], rax; pvData
0x180016700  lea     rax, [rbp+4Fh+pType]
0x180016704  mov     [rsp+0F0h+pdwType], rax; pdwType
0x180016709  mov     r9d, 18h; dwFlags
0x18001670f  lea     r8, aFailedsyncatte; "FailedSyncAttempts"
0x180016716  xor     edx, edx; lpSubKey
0x180016718  mov     rcx, [rbp+4Fh+hKey]; hkey
0x18001671c  call    cs:__imp_RegGetValueW
0x180016722  cmp     eax, 2
0x180016725  jz      short loc_180016749
0x180016727  cmp     [rbp+4Fh+pType], r13d
0x18001672b  jnz     short loc_180016749
0x18001672d  test    eax, eax
0x18001672f  jz      short loc_180016743
0x180016731  jg      short loc_180016737
0x180016733  mov     ebx, eax
0x180016735  jmp     short loc_180016740
0x180016737  movzx   ebx, ax
0x18001673a  or      ebx, 80070000h
0x180016740  mov     [rbp+4Fh+arg_18], ebx
0x180016743  mov     r8d, dword ptr [rbp+4Fh+Data]
0x180016747  jmp     short loc_180016750
0x180016749  mov     r8d, r12d
0x18001674c  mov     dword ptr [rbp+4Fh+Data], r12d
0x180016750  test    ebx, ebx
0x180016752  js      short loc_18001677C
0x180016754  lea     eax, [r8-1]
0x180016758  cmp     eax, 1
0x18001675b  ja      short loc_18001677C
0x18001675d  mov     r14b, 1
0x180016760  inc     r8d
0x180016763  mov     r9d, 3
0x180016769  lea     rdx, aCacheRefreshAt; "Cache Refresh attempt %d of %d."
0x180016770  lea     rcx, aRefreshconnect; "RefreshConnectionCache"
0x180016777  call    ?WriteDbgTraceInfo@PrintConfigTelemetry@Telemetry@Driver@Print@@SAXPEADPEAGZZ; Print::Driver::Telemetry::PrintConfigTelemetry::WriteDbgTraceInfo(char *,ushort *,...)
0x18001677c  lea     rdx, [rbp+4Fh+arg_18]; int *
0x180016780  lea     rcx, [rbp+4Fh+hLibModule]; this
0x180016784  call    ??0RevertToPrinterRAII@@QEAA@PEAJ@Z; RevertToPrinterRAII::RevertToPrinterRAII(long *)
0x180016789  nop
0x18001678a  mov     ebx, [rbp+4Fh+arg_18]
0x18001678d  test    ebx, ebx
0x18001678f  js      loc_18001685B
0x180016795  mov     dword ptr [rsp+0F0h+pvData], r13d; cbData
0x18001679a  lea     rax, [rbp+4Fh+pData]
0x18001679e  mov     [rsp+0F0h+pdwType], rax; lpData
0x1800167a3  mov     r9d, r13d; dwType
0x1800167a6  xor     r8d, r8d; Reserved
0x1800167a9  lea     rdx, ValueName; "CachedChangeID"
0x1800167b0  mov     rcx, [rbp+4Fh+hKey]; hKey
0x1800167b4  call    cs:__imp_RegSetValueExW
0x1800167ba  test    eax, eax
0x1800167bc  jz      short loc_1800167D0
0x1800167be  jg      short loc_1800167C4
0x1800167c0  mov     ebx, eax
0x1800167c2  jmp     short loc_1800167CD
0x1800167c4  movzx   ebx, ax
0x1800167c7  or      ebx, 80070000h
0x1800167cd  mov     [rbp+4Fh+arg_18], ebx
0x1800167d0  test    ebx, ebx
0x1800167d2  js      loc_18001685B
0x1800167d8  xor     r8d, r8d; bool
0x1800167db  lea     rcx, [rbp+4Fh+hKey]; struct RegistryHandleRAII *
0x1800167df  call    ?UpdateConnectionStatusFlags_nothrow@@YAJAEAVRegistryHandleRAII@@K_N@Z; UpdateConnectionStatusFlags_nothrow(RegistryHandleRAII &,ulong,bool)
0x1800167e4  mov     ebx, eax
0x1800167e6  mov     [rbp+4Fh+arg_18], eax
0x1800167e9  test    eax, eax
0x1800167eb  js      short loc_18001685B
0x1800167ed  mov     eax, dword ptr [rbp+4Fh+Data]
0x1800167f0  cmp     eax, 3
0x1800167f3  jnb     short loc_1800167FC
0x1800167f5  inc     eax
0x1800167f7  mov     dword ptr [rbp+4Fh+Data], eax
0x1800167fa  jmp     short loc_180016820
0x1800167fc  mov     r9, r15
0x1800167ff  mov     r8d, 3
0x180016805  lea     rdx, aAlreadyFailedT; "Already failed to refresh cache %d time"...
0x18001680c  lea     rcx, aRefreshconnect; "RefreshConnectionCache"
0x180016813  call    ?WriteDbgTraceInfo@PrintConfigTelemetry@Telemetry@Driver@Print@@SAXPEADPEAGZZ; Print::Driver::Telemetry::PrintConfigTelemetry::WriteDbgTraceInfo(char *,ushort *,...)
0x180016818  mov     ebx, 80004005h
0x18001681d  mov     [rbp+4Fh+arg_18], ebx
0x180016820  mov     dword ptr [rsp+0F0h+pvData], r13d; cbData
0x180016825  lea     rax, [rbp+4Fh+Data]
0x180016829  mov     [rsp+0F0h+pdwType], rax; lpData
0x18001682e  mov     r9d, r13d; dwType
0x180016831  xor     r8d, r8d; Reserved
0x180016834  lea     rdx, aFailedsyncatte; "FailedSyncAttempts"
0x18001683b  mov     rcx, [rbp+4Fh+hKey]; hKey
0x18001683f  call    cs:__imp_RegSetValueExW
0x180016845  test    eax, eax
0x180016847  jz      short loc_18001685B
0x180016849  jg      short loc_18001684F
0x18001684b  mov     ebx, eax
0x18001684d  jmp     short loc_180016858
0x18001684f  movzx   ebx, ax
0x180016852  or      ebx, 80070000h
0x180016858  mov     [rbp+4Fh+arg_18], ebx
0x18001685b  mov     rax, [rbp+4Fh+var_70]
0x18001685f  test    rax, rax
0x180016862  jz      short loc_180016872
0x180016864  mov     rcx, [rbp+4Fh+hLibModule+8]
0x180016868  test    rcx, rcx
0x18001686b  jz      short loc_180016872
0x18001686d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016872  mov     rcx, [rbp+4Fh+hLibModule]; hLibModule
0x180016876  test    rcx, rcx
0x180016879  jz      short loc_180016882
0x18001687b  call    cs:__imp_FreeLibrary
0x180016881  nop
0x180016882  test    r14b, r14b
0x180016885  jz      loc_180016C2C
0x18001688b  test    ebx, ebx
0x18001688d  js      loc_180016C2C
0x180016893  mov     r8, r15
0x180016896  lea     rdx, aPerformingACac; "Performing a cache refresh for %ws!"
0x18001689d  lea     rcx, aRefreshconnect; "RefreshConnectionCache"
0x1800168a4  call    ?WriteDbgTraceInfo@PrintConfigTelemetry@Telemetry@Driver@Print@@SAXPEADPEAGZZ; Print::Driver::Telemetry::PrintConfigTelemetry::WriteDbgTraceInfo(char *,ushort *,...)
0x1800168a9  test    ebx, ebx
0x1800168ab  js      loc_180016C2C
0x1800168b1  lea     rdx, [rbp+4Fh+arg_18]; int *
0x1800168b5  lea     rcx, [rbp+4Fh+hLibModule]; this
0x1800168b9  call    ??0RevertToPrinterRAII@@QEAA@PEAJ@Z; RevertToPrinterRAII::RevertToPrinterRAII(long *)
0x1800168be  mov     ebx, [rbp+4Fh+arg_18]
0x1800168c1  test    ebx, ebx
0x1800168c3  js      short loc_1800168CF
0x1800168c5  mov     rcx, [rbp+4Fh+hKey]; hkey
0x1800168c9  call    ?RemoveAllConnectionFiles@@YAXPEAUHKEY__@@@Z; RemoveAllConnectionFiles(HKEY__ *)
0x1800168ce  nop
0x1800168cf  mov     rax, [rbp+4Fh+var_70]
0x1800168d3  test    rax, rax
0x1800168d6  jz      short loc_1800168E6
0x1800168d8  mov     rcx, [rbp+4Fh+hLibModule+8]
0x1800168dc  test    rcx, rcx
0x1800168df  jz      short loc_1800168E6
0x1800168e1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800168e6  mov     rcx, [rbp+4Fh+hLibModule]; hLibModule
0x1800168ea  test    rcx, rcx
0x1800168ed  jz      short loc_1800168F6
0x1800168ef  call    cs:__imp_FreeLibrary
0x1800168f5  nop
0x1800168f6  test    ebx, ebx
0x1800168f8  js      loc_180016C2C
0x1800168fe  mov     byte ptr [rsp+0F0h+pcbData], 1; bool
0x180016903  mov     byte ptr [rsp+0F0h+pvData], r12b; bool
0x180016908  lea     rax, aResourceBase; "Resource_Base"
0x18001690f  mov     [rsp+0F0h+pdwType], rax; unsigned __int16 *
0x180016914  lea     r9, aClasslangresou; "ClassLangResourceName"
0x18001691b  lea     r8, aClasslanguager; "ClassLanguageResource"
0x180016922  mov     rdx, [rbp+4Fh+hKey]; HKEY
0x180016926  mov     rcx, rdi; hPrinter
0x180016929  call    ?GetFileAndFilenameFromServer@@YAJPEAXPEAUHKEY__@@PEBGPEAG3_N4@Z; GetFileAndFilenameFromServer(void *,HKEY__ *,ushort const *,ushort *,ushort *,bool,bool)
0x18001692e  mov     ebx, eax
0x180016930  mov     [rbp+4Fh+arg_18], eax
0x180016933  test    eax, eax
0x180016935  js      loc_180016C2C
0x18001693b  mov     byte ptr [rsp+0F0h+pcbData], 1; bool
0x180016940  mov     byte ptr [rsp+0F0h+pvData], r12b; bool
0x180016945  lea     rax, aResourceDerive; "Resource_Derived"
0x18001694c  mov     [rsp+0F0h+pdwType], rax; unsigned __int16 *
0x180016951  lea     r9, aDerivedlangres; "DerivedLangResourceName"
0x180016958  lea     r8, aDerivedlanguag; "DerivedLanguageResource"
0x18001695f  mov     rdx, [rbp+4Fh+hKey]; HKEY
0x180016963  mov     rcx, rdi; hPrinter
0x180016966  call    ?GetFileAndFilenameFromServer@@YAJPEAXPEAUHKEY__@@PEBGPEAG3_N4@Z; GetFileAndFilenameFromServer(void *,HKEY__ *,ushort const *,ushort *,ushort *,bool,bool)
0x18001696b  mov     ebx, eax
0x18001696d  mov     [rbp+4Fh+arg_18], eax
0x180016970  test    eax, eax
0x180016972  js      loc_180016C2C
0x180016978  mov     byte ptr [rsp+0F0h+pcbData], 1; bool
0x18001697d  mov     byte ptr [rsp+0F0h+pvData], r12b; bool
0x180016982  lea     rax, aResourceSystem_3; "Resource_System"
0x180016989  mov     [rsp+0F0h+pdwType], rax; unsigned __int16 *
0x18001698e  lea     r9, aSystemresource_1; "SystemResourceName"
0x180016995  lea     r8, aSystemresource_0; "SystemResource"
0x18001699c  mov     rdx, [rbp+4Fh+hKey]; HKEY
0x1800169a0  mov     rcx, rdi; hPrinter
  ... truncated ...
```
