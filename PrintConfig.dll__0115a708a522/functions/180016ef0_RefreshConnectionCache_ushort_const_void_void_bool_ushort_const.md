# RefreshConnectionCache(ushort const *,void *,void *,bool,ushort const *)

- ea: `0x180016ef0`
- end: `0x1800177a8`
- name: `?RefreshConnectionCache@@YAJPEBGPEAX1_N0@Z`
- size: `2232`
- prototype: `__int64 __fastcall(const unsigned __int16 *, HANDLE hPrinter, HANDLE, char, WCHAR *pName)`
- caller_count: `1`
- callee_count: `15`
- tags: `file_ops, registry_config, loader_planting, installer_update`

## callers

- `0x180015fa4`

## callees

- `0x180003430`
- `0x180006268`
- `0x18000fc40`
- `0x1800136f0`
- `0x180014558`
- `0x18001470c`
- `0x180016ef0`
- `0x180017b40`
- `0x180018710`
- `0x180018f00`
- `0x180018f58`
- `0x18003a470`
- `0x18003a550`
- `0x18015a2d4`
- `0x1801cb010`

## import_xrefs

- `KERNEL32!FreeLibrary` at `0x180017030`
- `KERNEL32!FreeLibrary` at `0x180017263`
- `KERNEL32!FreeLibrary` at `0x1800172dd`
- `KERNEL32!FreeLibrary` at `0x18001773e`
- `KERNEL32!FreeLibrary` at `0x180017030`
- `KERNEL32!FreeLibrary` at `0x180017263`
- `KERNEL32!FreeLibrary` at `0x1800172dd`
- `KERNEL32!FreeLibrary` at `0x18001773e`
- `ADVAPI32!RegCloseKey` at `0x180016f62`
- `ADVAPI32!RegCloseKey` at `0x180017000`
- `ADVAPI32!RegCloseKey` at `0x180017785`
- `ADVAPI32!RegCloseKey` at `0x180016f62`
- `ADVAPI32!RegCloseKey` at `0x180017000`
- `ADVAPI32!RegCloseKey` at `0x180017785`
- `ADVAPI32!RegSetValueExW` at `0x180017190`
- `ADVAPI32!RegSetValueExW` at `0x180017221`
- `ADVAPI32!RegSetValueExW` at `0x180017190`
- `ADVAPI32!RegSetValueExW` at `0x180017221`
- `ADVAPI32!RegGetValueW` at `0x180016fc6`
- `ADVAPI32!RegGetValueW` at `0x1800170f2`
- `ADVAPI32!RegGetValueW` at `0x180016fc6`
- `ADVAPI32!RegGetValueW` at `0x1800170f2`
- `ADVAPI32!RegDeleteValueW` at `0x180017704`
- `ADVAPI32!RegDeleteValueW` at `0x180017704`
- `WINSPOOL!GetPrinterDataW` at `0x180017068`
- `WINSPOOL!GetPrinterDataW` at `0x180017068`

## string_xrefs

- `0x180016fb9`: `CachedChangeID`
- `0x180017185`: `CachedChangeID`
- `0x180017061`: `V4_Config_ChangeID`
- `0x1800170a7`: `RefreshConnectionCache`
- `0x18001714c`: `RefreshConnectionCache`
- `0x1800171ee`: `RefreshConnectionCache`
- `0x18001728b`: `RefreshConnectionCache`
- `0x180017753`: `RefreshConnectionCache`
- `0x1800170e5`: `FailedSyncAttempts`
- `0x180017216`: `FailedSyncAttempts`
- `0x1800176f9`: `FailedSyncAttempts`
- `0x180017145`: `Cache Refresh attempt %d of %d.`
- `0x1800171e7`: `Already failed to refresh cache %d times for %ws. Skipping.`
- `0x180017284`: `Performing a cache refresh for %ws!`
- `0x1800173c9`: `PCLXL.dll`
- `0x180017410`: `PCL5ERES.dll`
- `0x180017457`: `PCL4RES.dll`
- `0x18001749e`: `PCL5URES.dll`
- `0x18001756c`: `DevmodeMap.xml`
- `0x1800175ac`: `QueuePropertyMap.xml`
- `0x1800175ef`: `PDC.xml`
- `0x18001775e`: `Successful connection cache refresh for %ws!`
- `0x18001776f`: `Failed to refresh connection cache for %ws (hr: 0x%x)!`
- `0x180017683`: `PrintConfig::CConfigManager::RetrieveConnectionLanguageDatabase`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
__int64 __fastcall RefreshConnectionCache(unsigned __int16 *a1, HANDLE hPrinter, HANDLE a3, char a4, WCHAR *pName)
{
  int v9; // ebx
  LSTATUS ValueW; // eax
  HANDLE v11; // rcx
  signed int PrinterDataW; // eax
  LSTATUS v13; // eax
  int v14; // r8d
  int updated; // ebx
  LSTATUS v16; // eax
  __int64 v17; // rdx
  LSTATUS v18; // eax
  __int64 v19; // rdx
  __int64 v20; // r8
  char *v21; // rsi
  int v22; // eax
  void *v23; // rbx
  int v24; // ebx
  __int64 v25; // rdx
  HKEY hKey; // [rsp+50h] [rbp-51h] BYREF
  BYTE Data[4]; // [rsp+58h] [rbp-49h] BYREF
  DWORD pcbNeeded; // [rsp+5Ch] [rbp-45h] BYREF
  DWORD pType; // [rsp+60h] [rbp-41h] BYREF
  BYTE pData[12]; // [rsp+64h] [rbp-3Dh] BYREF
  HMODULE hLibModule[2]; // [rsp+70h] [rbp-31h] BYREF
  void (*v33)(void); // [rsp+80h] [rbp-21h]
  int pvData; // [rsp+90h] [rbp-11h] BYREF
  void *Block; // [rsp+98h] [rbp-9h] BYREF
  __int64 v36[10]; // [rsp+A0h] [rbp-1h] BYREF
  int FileAndFilenameFromServer; // [rsp+118h] [rbp+77h] BYREF

  v36[1] = -2;
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
  if ( v33 && hLibModule[1] )
    v33();
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
  if ( v33 && hLibModule[1] )
    v33();
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
    if ( v33 && hLibModule[1] )
      v33();
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
    v36[0] = (__int64)a1;
    hLibModule[0] = (HMODULE)v36;
    hLibModule[1] = (HMODULE)&Block;
    if ( (int)ExceptionBoundary__lambda_5648f5919d1758734759f438906712d7_((__int64)hLibModule) >= 0 )
    {
      v21 = (char *)Block;
      v36[0] = (__int64)Block;
      v22 = ExceptionBoundary__lambda_a402ae3cd7da9c177cf78f147a0fd8c2_(v36, v19, v20);
      if ( v22 < 0 )
      {
        *(_OWORD *)hLibModule = *(_OWORD *)(v21 + 8);
        Print::Driver::Telemetry::PrintConfigTelemetry::WriteDbgTraceWarning(
          "PrintConfig::CConfigManager::RetrieveConnectionLanguageDatabase",
          L"Failed to retrieve connection language database for printer \"%ws\" (hr: 0x%x)",
          hLibModule,
          (unsigned int)v22);
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
  v23 = Block;
  if ( Block )
  {
    PrintConfig::CConfigManager::~CConfigManager((PrintConfig::CConfigManager *)Block);
    operator delete(v23);
  }
  RevertToPrinterRAII::RevertToPrinterRAII((RevertToPrinterRAII *)hLibModule, &FileAndFilenameFromServer);
  v24 = FileAndFilenameFromServer;
  if ( FileAndFilenameFromServer >= 0 )
  {
    RegDeleteValueW(hKey, L"FailedSyncAttempts");
    v24 = UpdateConnectionStatusFlags_nothrow((struct RegistryHandleRAII *)&hKey, v25, 1);
  }
  if ( v33 && hLibModule[1] )
    v33();
  if ( hLibModule[0] )
    FreeLibrary(hLibModule[0]);
  if ( a4 )
  {
    if ( v24 < 0 )
      Print::Driver::Telemetry::PrintConfigTelemetry::WriteDbgTraceWarning(
        "RefreshConnectionCache",
        L"Failed to refresh connection cache for %ws (hr: 0x%x)!",
        a1,
        (unsigned int)v24);
    else
      Print::Driver::Telemetry::PrintConfigTelemetry::WriteDbgTraceInfo(
        "RefreshConnectionCache",
        L"Successful connection cache refresh for %ws!",
        a1);
  }
  if ( hKey )
    RegCloseKey(hKey);
  return (unsigned int)v24;
}

```

## disassembly

```asm
0x180016ef0  push    rbp
0x180016ef2  push    rbx
0x180016ef3  push    rsi
0x180016ef4  push    rdi
0x180016ef5  push    r12
0x180016ef7  push    r13
0x180016ef9  push    r14
0x180016efb  push    r15
0x180016efd  lea     rbp, [rsp-17h]
0x180016f02  sub     rsp, 0B8h
0x180016f09  mov     [rbp+4Fh+var_48], 0FFFFFFFFFFFFFFFEh
0x180016f11  mov     r14b, r9b
0x180016f14  mov     rdi, r8
0x180016f17  mov     rsi, rdx
0x180016f1a  mov     r15, rcx
0x180016f1d  xor     r12d, r12d
0x180016f20  mov     [rbp+4Fh+pType], r12d
0x180016f24  mov     [rbp+4Fh+pcbNeeded], r12d
0x180016f28  mov     [rbp+4Fh+var_60], r12d
0x180016f2c  mov     dword ptr [rbp+4Fh+pData], r12d
0x180016f30  mov     dword ptr [rbp+4Fh+Data], r12d
0x180016f34  mov     [rbp+4Fh+arg_18], r12d
0x180016f38  mov     [rbp+4Fh+hKey], r12
0x180016f3c  lea     rdx, [rbp+4Fh+arg_18]; int *
0x180016f40  lea     rcx, [rbp+4Fh+hLibModule]; this
0x180016f44  call    ??0RevertToPrinterRAII@@QEAA@PEAJ@Z; RevertToPrinterRAII::RevertToPrinterRAII(long *)
0x180016f49  lea     r13d, [r12+4]
0x180016f4e  mov     ebx, [rbp+4Fh+arg_18]
0x180016f51  test    ebx, ebx
0x180016f53  js      loc_180016FF7
0x180016f59  mov     rcx, [rbp+4Fh+hKey]; hKey
0x180016f5d  test    rcx, rcx
0x180016f60  jz      short loc_180016F72
0x180016f62  call    cs:__imp_RegCloseKey
0x180016f69  nop     dword ptr [rax+rax+00h]
0x180016f6e  mov     [rbp+4Fh+hKey], r12
0x180016f72  mov     [rsp+0F0h+pdwType], r12; bool *
0x180016f77  lea     r9, [rbp+4Fh+hKey]; HKEY *
0x180016f7b  xor     r8d, r8d; bool
0x180016f7e  mov     edx, 2001Fh; samDesired
0x180016f83  mov     rcx, r15; unsigned __int16 *
0x180016f86  call    ?OpenConnectionRegistryKey@@YAJPEBGK_NPEAPEAUHKEY__@@PEA_N@Z; OpenConnectionRegistryKey(ushort const *,ulong,bool,HKEY__ * *,bool *)
0x180016f8b  mov     ebx, eax
0x180016f8d  mov     [rbp+4Fh+arg_18], eax
0x180016f90  test    eax, eax
0x180016f92  js      short loc_180016FF7
0x180016f94  mov     [rbp+4Fh+pcbNeeded], r13d
0x180016f98  lea     rax, [rbp+4Fh+pcbNeeded]
0x180016f9c  mov     [rsp+0F0h+pcbData], rax; pcbData
0x180016fa1  lea     rax, [rbp+4Fh+var_60]
0x180016fa5  mov     [rsp+0F0h+pvData], rax; pvData
0x180016faa  lea     rax, [rbp+4Fh+pType]
0x180016fae  mov     [rsp+0F0h+pdwType], rax; pdwType
0x180016fb3  mov     r9d, 18h; dwFlags
0x180016fb9  lea     r8, ValueName; "CachedChangeID"
0x180016fc0  xor     edx, edx; lpSubKey
0x180016fc2  mov     rcx, [rbp+4Fh+hKey]; hkey
0x180016fc6  call    cs:__imp_RegGetValueW
0x180016fcd  nop     dword ptr [rax+rax+00h]
0x180016fd2  test    eax, eax
0x180016fd4  jz      short loc_180016FE7
0x180016fd6  jg      short loc_180016FDC
0x180016fd8  mov     ebx, eax
0x180016fda  jmp     short loc_180016FF2
0x180016fdc  movzx   ebx, ax
0x180016fdf  or      ebx, 80070000h
0x180016fe5  jmp     short loc_180016FF2
0x180016fe7  cmp     [rbp+4Fh+pType], r13d
0x180016feb  jz      short loc_180017010
0x180016fed  mov     ebx, 8000FFFFh
0x180016ff2  mov     [rbp+4Fh+arg_18], ebx
0x180016ff5  jmp     short loc_180017010
0x180016ff7  mov     rcx, [rbp+4Fh+hKey]; hKey
0x180016ffb  test    rcx, rcx
0x180016ffe  jz      short loc_180017010
0x180017000  call    cs:__imp_RegCloseKey
0x180017007  nop     dword ptr [rax+rax+00h]
0x18001700c  mov     [rbp+4Fh+hKey], r12
0x180017010  mov     rax, [rbp+4Fh+var_70]
0x180017014  test    rax, rax
0x180017017  jz      short loc_180017027
0x180017019  mov     rcx, [rbp+4Fh+hLibModule+8]
0x18001701d  test    rcx, rcx
0x180017020  jz      short loc_180017027
0x180017022  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017027  mov     rcx, [rbp+4Fh+hLibModule]; hLibModule
0x18001702b  test    rcx, rcx
0x18001702e  jz      short loc_18001703D
0x180017030  call    cs:__imp_FreeLibrary
0x180017037  nop     dword ptr [rax+rax+00h]
0x18001703c  nop
0x18001703d  test    ebx, ebx
0x18001703f  js      short loc_18001708A
0x180017041  mov     rcx, rdi
0x180017044  test    r14b, r14b
0x180017047  cmovz   rcx, rsi; hPrinter
0x18001704b  lea     rax, [rbp+4Fh+pcbNeeded]
0x18001704f  mov     [rsp+0F0h+pvData], rax; pcbNeeded
0x180017054  mov     dword ptr [rsp+0F0h+pdwType], r13d; nSize
0x180017059  lea     r9, [rbp+4Fh+pData]; pData
0x18001705d  lea     r8, [rbp+4Fh+pType]; pType
0x180017061  lea     rdx, aV4ConfigChange; "V4_Config_ChangeID"
0x180017068  call    cs:__imp_GetPrinterDataW
0x18001706f  nop     dword ptr [rax+rax+00h]
0x180017074  test    eax, eax
0x180017076  jz      short loc_180017098
0x180017078  jg      short loc_18001707E
0x18001707a  mov     ebx, eax
0x18001707c  jmp     short loc_180017087
0x18001707e  movzx   ebx, ax
0x180017081  or      ebx, 80070000h
0x180017087  mov     [rbp+4Fh+arg_18], ebx
0x18001708a  test    r14b, r14b
0x18001708d  jz      short loc_1800170B8
0x18001708f  mov     dword ptr [rbp+4Fh+Data], r12d
0x180017093  jmp     loc_180017158
0x180017098  mov     eax, [rbp+4Fh+var_60]
0x18001709b  cmp     dword ptr [rbp+4Fh+pData], eax
0x18001709e  jz      short loc_18001708A
0x1800170a0  lea     rdx, aChangeIdHasCha; "Change ID has changed!"
0x1800170a7  lea     rcx, aRefreshconnect; "RefreshConnectionCache"
0x1800170ae  call    ?WriteDbgTraceInfo@PrintConfigTelemetry@Telemetry@Driver@Print@@SAXPEADPEAGZZ; Print::Driver::Telemetry::PrintConfigTelemetry::WriteDbgTraceInfo(char *,ushort *,...)
0x1800170b3  mov     r14b, 1
0x1800170b6  jmp     short loc_18001708F
0x1800170b8  test    ebx, ebx
0x1800170ba  js      loc_180017158
0x1800170c0  mov     [rbp+4Fh+pcbNeeded], r13d
0x1800170c4  lea     rax, [rbp+4Fh+pcbNeeded]
0x1800170c8  mov     [rsp+0F0h+pcbData], rax; pcbData
0x1800170cd  lea     rax, [rbp+4Fh+Data]
0x1800170d1  mov     [rsp+0F0h+pvData], rax; pvData
0x1800170d6  lea     rax, [rbp+4Fh+pType]
0x1800170da  mov     [rsp+0F0h+pdwType], rax; pdwType
0x1800170df  mov     r9d, 18h; dwFlags
0x1800170e5  lea     r8, aFailedsyncatte; "FailedSyncAttempts"
0x1800170ec  xor     edx, edx; lpSubKey
0x1800170ee  mov     rcx, [rbp+4Fh+hKey]; hkey
0x1800170f2  call    cs:__imp_RegGetValueW
0x1800170f9  nop     dword ptr [rax+rax+00h]
0x1800170fe  cmp     eax, 2
0x180017101  jz      short loc_180017125
0x180017103  cmp     [rbp+4Fh+pType], r13d
0x180017107  jnz     short loc_180017125
0x180017109  test    eax, eax
0x18001710b  jz      short loc_18001711F
0x18001710d  jg      short loc_180017113
0x18001710f  mov     ebx, eax
0x180017111  jmp     short loc_18001711C
0x180017113  movzx   ebx, ax
0x180017116  or      ebx, 80070000h
0x18001711c  mov     [rbp+4Fh+arg_18], ebx
0x18001711f  mov     r8d, dword ptr [rbp+4Fh+Data]
0x180017123  jmp     short loc_18001712C
0x180017125  mov     r8d, r12d
0x180017128  mov     dword ptr [rbp+4Fh+Data], r12d
0x18001712c  test    ebx, ebx
0x18001712e  js      short loc_180017158
0x180017130  lea     eax, [r8-1]
0x180017134  cmp     eax, 1
0x180017137  ja      short loc_180017158
0x180017139  mov     r14b, 1
0x18001713c  inc     r8d
0x18001713f  mov     r9d, 3
0x180017145  lea     rdx, aCacheRefreshAt; "Cache Refresh attempt %d of %d."
0x18001714c  lea     rcx, aRefreshconnect; "RefreshConnectionCache"
0x180017153  call    ?WriteDbgTraceInfo@PrintConfigTelemetry@Telemetry@Driver@Print@@SAXPEADPEAGZZ; Print::Driver::Telemetry::PrintConfigTelemetry::WriteDbgTraceInfo(char *,ushort *,...)
0x180017158  lea     rdx, [rbp+4Fh+arg_18]; int *
0x18001715c  lea     rcx, [rbp+4Fh+hLibModule]; this
0x180017160  call    ??0RevertToPrinterRAII@@QEAA@PEAJ@Z; RevertToPrinterRAII::RevertToPrinterRAII(long *)
0x180017165  nop
0x180017166  mov     ebx, [rbp+4Fh+arg_18]
0x180017169  test    ebx, ebx
0x18001716b  js      loc_180017243
0x180017171  mov     dword ptr [rsp+0F0h+pvData], r13d; cbData
0x180017176  lea     rax, [rbp+4Fh+pData]
0x18001717a  mov     [rsp+0F0h+pdwType], rax; lpData
0x18001717f  mov     r9d, r13d; dwType
0x180017182  xor     r8d, r8d; Reserved
0x180017185  lea     rdx, ValueName; "CachedChangeID"
0x18001718c  mov     rcx, [rbp+4Fh+hKey]; hKey
0x180017190  call    cs:__imp_RegSetValueExW
0x180017197  nop     dword ptr [rax+rax+00h]
0x18001719c  test    eax, eax
0x18001719e  jz      short loc_1800171B2
0x1800171a0  jg      short loc_1800171A6
0x1800171a2  mov     ebx, eax
0x1800171a4  jmp     short loc_1800171AF
0x1800171a6  movzx   ebx, ax
0x1800171a9  or      ebx, 80070000h
0x1800171af  mov     [rbp+4Fh+arg_18], ebx
0x1800171b2  test    ebx, ebx
0x1800171b4  js      loc_180017243
0x1800171ba  xor     r8d, r8d; bool
0x1800171bd  lea     rcx, [rbp+4Fh+hKey]; struct RegistryHandleRAII *
0x1800171c1  call    ?UpdateConnectionStatusFlags_nothrow@@YAJAEAVRegistryHandleRAII@@K_N@Z; UpdateConnectionStatusFlags_nothrow(RegistryHandleRAII &,ulong,bool)
0x1800171c6  mov     ebx, eax
0x1800171c8  mov     [rbp+4Fh+arg_18], eax
0x1800171cb  test    eax, eax
0x1800171cd  js      short loc_180017243
0x1800171cf  mov     eax, dword ptr [rbp+4Fh+Data]
0x1800171d2  cmp     eax, 3
0x1800171d5  jnb     short loc_1800171DE
0x1800171d7  inc     eax
0x1800171d9  mov     dword ptr [rbp+4Fh+Data], eax
0x1800171dc  jmp     short loc_180017202
0x1800171de  mov     r9, r15
0x1800171e1  mov     r8d, 3
0x1800171e7  lea     rdx, aAlreadyFailedT; "Already failed to refresh cache %d time"...
0x1800171ee  lea     rcx, aRefreshconnect; "RefreshConnectionCache"
0x1800171f5  call    ?WriteDbgTraceInfo@PrintConfigTelemetry@Telemetry@Driver@Print@@SAXPEADPEAGZZ; Print::Driver::Telemetry::PrintConfigTelemetry::WriteDbgTraceInfo(char *,ushort *,...)
0x1800171fa  mov     ebx, 80004005h
0x1800171ff  mov     [rbp+4Fh+arg_18], ebx
0x180017202  mov     dword ptr [rsp+0F0h+pvData], r13d; cbData
0x180017207  lea     rax, [rbp+4Fh+Data]
0x18001720b  mov     [rsp+0F0h+pdwType], rax; lpData
0x180017210  mov     r9d, r13d; dwType
0x180017213  xor     r8d, r8d; Reserved
0x180017216  lea     rdx, aFailedsyncatte; "FailedSyncAttempts"
0x18001721d  mov     rcx, [rbp+4Fh+hKey]; hKey
0x180017221  call    cs:__imp_RegSetValueExW
0x180017228  nop     dword ptr [rax+rax+00h]
0x18001722d  test    eax, eax
0x18001722f  jz      short loc_180017243
0x180017231  jg      short loc_180017237
0x180017233  mov     ebx, eax
0x180017235  jmp     short loc_180017240
0x180017237  movzx   ebx, ax
0x18001723a  or      ebx, 80070000h
0x180017240  mov     [rbp+4Fh+arg_18], ebx
0x180017243  mov     rax, [rbp+4Fh+var_70]
0x180017247  test    rax, rax
0x18001724a  jz      short loc_18001725A
0x18001724c  mov     rcx, [rbp+4Fh+hLibModule+8]
0x180017250  test    rcx, rcx
0x180017253  jz      short loc_18001725A
0x180017255  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001725a  mov     rcx, [rbp+4Fh+hLibModule]; hLibModule
0x18001725e  test    rcx, rcx
0x180017261  jz      short loc_180017270
0x180017263  call    cs:__imp_FreeLibrary
0x18001726a  nop     dword ptr [rax+rax+00h]
0x18001726f  nop
0x180017270  test    r14b, r14b
0x180017273  jz      loc_180017620
0x180017279  test    ebx, ebx
0x18001727b  js      loc_180017620
0x180017281  mov     r8, r15
0x180017284  lea     rdx, aPerformingACac; "Performing a cache refresh for %ws!"
0x18001728b  lea     rcx, aRefreshconnect; "RefreshConnectionCache"
0x180017292  call    ?WriteDbgTraceInfo@PrintConfigTelemetry@Telemetry@Driver@Print@@SAXPEADPEAGZZ; Print::Driver::Telemetry::PrintConfigTelemetry::WriteDbgTraceInfo(char *,ushort *,...)
0x180017297  test    ebx, ebx
0x180017299  js      loc_180017620
0x18001729f  lea     rdx, [rbp+4Fh+arg_18]; int *
0x1800172a3  lea     rcx, [rbp+4Fh+hLibModule]; this
0x1800172a7  call    ??0RevertToPrinterRAII@@QEAA@PEAJ@Z; RevertToPrinterRAII::RevertToPrinterRAII(long *)
0x1800172ac  mov     ebx, [rbp+4Fh+arg_18]
0x1800172af  test    ebx, ebx
0x1800172b1  js      short loc_1800172BD
0x1800172b3  mov     rcx, [rbp+4Fh+hKey]; hkey
0x1800172b7  call    ?RemoveAllConnectionFiles@@YAXPEAUHKEY__@@@Z; RemoveAllConnectionFiles(HKEY__ *)
0x1800172bc  nop
0x1800172bd  mov     rax, [rbp+4Fh+var_70]
0x1800172c1  test    rax, rax
0x1800172c4  jz      short loc_1800172D4
0x1800172c6  mov     rcx, [rbp+4Fh+hLibModule+8]
0x1800172ca  test    rcx, rcx
0x1800172cd  jz      short loc_1800172D4
0x1800172cf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800172d4  mov     rcx, [rbp+4Fh+hLibModule]; hLibModule
0x1800172d8  test    rcx, rcx
0x1800172db  jz      short loc_1800172EA
0x1800172dd  call    cs:__imp_FreeLibrary
0x1800172e4  nop     dword ptr [rax+rax+00h]
0x1800172e9  nop
0x1800172ea  test    ebx, ebx
0x1800172ec  js      loc_180017620
0x1800172f2  mov     byte ptr [rsp+0F0h+pcbData], 1; bool
0x1800172f7  mov     byte ptr [rsp+0F0h+pvData], r12b; bool
0x1800172fc  lea     rax, aResourceBase; "Resource_Base"
0x180017303  mov     [rsp+0F0h+pdwType], rax; unsigned __int16 *
0x180017308  lea     r9, aClasslangresou; "ClassLangResourceName"
0x18001730f  lea     r8, aClasslanguager; "ClassLanguageResource"
0x180017316  mov     rdx, [rbp+4Fh+hKey]; HKEY
0x18001731a  mov     rcx, rdi; hPrinter
0x18001731d  call    ?GetFileAndFilenameFromServer@@YAJPEAXPEAUHKEY__@@PEBGPEAG3_N4@Z; GetFileAndFilenameFromServer(void *,HKEY__ *,ushort const *,ushort *,ushort *,bool,bool)
0x180017322  mov     ebx, eax
0x180017324  mov     [rbp+4Fh+arg_18], eax
0x180017327  test    eax, eax
0x180017329  js      loc_180017620
0x18001732f  mov     byte ptr [rsp+0F0h+pcbData], 1; bool
0x180017334  mov     byte ptr [rsp+0F0h+pvData], r12b; bool
0x180017339  lea     rax, aResourceDerive; "Resource_Derived"
0x180017340  mov     [rsp+0F0h+pdwType], rax; unsigned __int16 *
0x180017345  lea     r9, aDerivedlangres; "DerivedLangResourceName"
0x18001734c  lea     r8, aDerivedlanguag; "DerivedLanguageResource"
0x180017353  mov     rdx, [rbp+4Fh+hKey]; HKEY
0x180017357  mov     rcx, rdi; hPrinter
0x18001735a  call    ?GetFileAndFilenameFromServer@@YAJPEAXPEAUHKEY__@@PEBGPEAG3_N4@Z; GetFileAndFilenameFromServer(void *,HKEY__ *,ushort const *,ushort *,ushort *,bool,bool)
0x18001735f  mov     ebx, eax
0x180017361  mov     [rbp+4Fh+arg_18], eax
  ... truncated ...
```
