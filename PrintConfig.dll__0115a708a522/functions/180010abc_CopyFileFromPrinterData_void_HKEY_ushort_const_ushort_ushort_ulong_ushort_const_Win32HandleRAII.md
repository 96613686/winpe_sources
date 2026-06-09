# CopyFileFromPrinterData(void *,HKEY__ *,ushort const *,ushort *,ushort *,ulong,ushort const *,Win32HandleRAII *)

- ea: `0x180010abc`
- end: `0x180011093`
- name: `?CopyFileFromPrinterData@@YAJPEAXPEAUHKEY__@@PEBGPEAG3K2PEAVWin32HandleRAII@@@Z`
- size: `1495`
- prototype: `__int64 __fastcall(HANDLE hPrinter, HKEY, const unsigned __int16 *, unsigned __int16 *, unsigned __int16 *lpFileName, unsigned int, unsigned __int16 *, struct Win32HandleRAII *)`
- caller_count: `2`
- callee_count: `30`
- tags: `file_ops, registry_config, loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x18001470c`
- `0x180018d54`

## callees

- `0x180003400`
- `0x180003430`
- `0x180003c20`
- `0x180004564`
- `0x180006268`
- `0x18000e964`
- `0x18000f830`
- `0x18000fa4c`
- `0x18000fc40`
- `0x180010abc`
- `0x180011350`
- `0x18001425c`
- `0x180014bf8`
- `0x1800189a4`
- `0x1800192fc`
- `0x180019410`
- `0x1800197b4`
- `0x1800197f8`
- `0x18003a470`
- `0x180042980`
- `0x180042a9c`
- `0x180042eec`
- `0x18004746c`
- `0x180049f1c`
- `0x18004a080`
- `0x18004ba9c`
- `0x180055608`
- `0x180059c78`
- `0x1801b568c`
- `0x1801cb010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180010f55`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180010f55`
- `KERNEL32!FreeLibrary` at `0x180010fec`
- `KERNEL32!FreeLibrary` at `0x180010fec`
- `KERNEL32!SetLastError` at `0x180010dc9`
- `KERNEL32!SetLastError` at `0x180010dc9`
- `KERNEL32!GetLastError` at `0x180010da8`
- `KERNEL32!GetLastError` at `0x180010da8`
- `ole32!CoTaskMemAlloc` at `0x180010b85`
- `ole32!CoTaskMemAlloc` at `0x180010b85`
- `ole32!CoTaskMemFree` at `0x180010dbb`
- `ole32!CoTaskMemFree` at `0x180010ed6`
- `ole32!CoTaskMemFree` at `0x180011009`
- `ole32!CoTaskMemFree` at `0x180010dbb`
- `ole32!CoTaskMemFree` at `0x180010ed6`
- `ole32!CoTaskMemFree` at `0x180011009`
- `WINSPOOL!GetPrinterDataExW` at `0x180010b4d`
- `WINSPOOL!GetPrinterDataExW` at `0x180010bd6`
- `WINSPOOL!GetPrinterDataExW` at `0x180010b4d`
- `WINSPOOL!GetPrinterDataExW` at `0x180010bd6`
- `Print.PrintSupport.Source!IsPsaEnabledForContractAsCurrentUser` at `0x180010c61`
- `Print.PrintSupport.Source!IsPsaEnabledForContractAsCurrentUser` at `0x180010c61`

## string_xrefs

- `0x180010b43`: `ConfigDriverData`
- `0x180010bca`: `ConfigDriverData`
- `0x180010c57`: `Windows.PrintSupportExtension`
- `0x180010c7c`: `printscan\print\drivers\usermode\driverui\dll\printconfig\connectionmanagement.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=10
__int64 __fastcall CopyFileFromPrinterData(
        HANDLE hPrinter,
        HKEY a2,
        const unsigned __int16 *a3,
        unsigned __int16 *a4,
        unsigned __int16 *lpFileName,
        unsigned int a6,
        unsigned __int16 *a7,
        struct Win32HandleRAII *a8)
{
  signed int PrinterData; // eax
  int ConnectionSpecificFilePath; // esi
  void *pData; // rbx
  int v13; // eax
  int v14; // r14d
  void *v15; // rax
  BSTR *v16; // r14
  char v17; // bl
  int BestLanguageResource; // eax
  PrintConfig::CConfigManager *v19; // rcx
  UINT v20; // r9d
  DWORD LastError; // ebx
  __int128 *v22; // rax
  DWORD v23; // r12d
  unsigned __int8 *v24; // rbx
  __int64 v25; // rdx
  __int64 v26; // r8
  void *v27; // rbx
  unsigned int v29; // [rsp+40h] [rbp-108h] BYREF
  _BYTE v30[4]; // [rsp+44h] [rbp-104h] BYREF
  DWORD pcbNeeded; // [rsp+48h] [rbp-100h] BYREF
  LPVOID pv; // [rsp+50h] [rbp-F8h] BYREF
  void *Block; // [rsp+58h] [rbp-F0h] BYREF
  HANDLE hPrintera; // [rsp+60h] [rbp-E8h] BYREF
  DWORD pType; // [rsp+68h] [rbp-E0h] BYREF
  int v36; // [rsp+6Ch] [rbp-DCh] BYREF
  DWORD nNumberOfBytesToWrite; // [rsp+70h] [rbp-D8h] BYREF
  struct Win32HandleRAII *v38; // [rsp+78h] [rbp-D0h]
  LPCVOID lpBuffer; // [rsp+80h] [rbp-C8h] BYREF
  _QWORD v40[2]; // [rsp+88h] [rbp-C0h] BYREF
  HMODULE hLibModule[2]; // [rsp+98h] [rbp-B0h] BYREF
  void (*v42)(void); // [rsp+A8h] [rbp-A0h]
  __int64 v43; // [rsp+B0h] [rbp-98h]
  const PrintCore::WindowsError *v44; // [rsp+B8h] [rbp-90h] BYREF
  const hr_error *v45; // [rsp+C0h] [rbp-88h] BYREF
  _BYTE pExceptionObject[32]; // [rsp+C8h] [rbp-80h] BYREF
  __int128 v47; // [rsp+E8h] [rbp-60h] BYREF
  __int64 v48; // [rsp+F8h] [rbp-50h]
  unsigned __int64 v49; // [rsp+100h] [rbp-48h]
  wil::details::in1diag3 *retaddr; // [rsp+148h] [rbp+0h]

  v43 = -2;
  Block = a2;
  hPrintera = hPrinter;
  v38 = a8;
  v29 = 0;
  pcbNeeded = 0;
  pType = 0;
  PrinterData = GetPrinterDataExW(hPrinter, L"ConfigDriverData", a3, &pType, 0, 0, &pcbNeeded);
  ConnectionSpecificFilePath = PrinterData;
  if ( PrinterData != 234 )
  {
    if ( PrinterData > 0 )
      ConnectionSpecificFilePath = (unsigned __int16)PrinterData | 0x80070000;
    if ( ConnectionSpecificFilePath >= 0 )
      return (unsigned int)-2147467259;
    return (unsigned int)ConnectionSpecificFilePath;
  }
  pData = CoTaskMemAlloc(pcbNeeded);
  lpBuffer = pData;
  if ( !pData )
  {
    ConnectionSpecificFilePath = -2147024882;
    goto LABEL_56;
  }
  if ( !GetPrinterDataExW(hPrintera, L"ConfigDriverData", a3, &pType, (LPBYTE)pData, pcbNeeded, &pcbNeeded) )
  {
    RevertToPrinterRAII::RevertToPrinterRAII((RevertToPrinterRAII *)hLibModule, (int *)&v29);
    *lpFileName = 0;
    ConnectionSpecificFilePath = v29;
    if ( (v29 & 0x80000000) != 0
      || (ConnectionSpecificFilePath = GetConnectionSpecificFilePath((HKEY)Block, a4, lpFileName),
          ConnectionSpecificFilePath < 0) )
    {
LABEL_51:
      if ( v42 && hLibModule[1] )
        v42();
      if ( hLibModule[0] )
        FreeLibrary(hLibModule[0]);
      goto LABEL_56;
    }
    v30[0] = 0;
    if ( !a7 || wcscmp_0(a3, L"PrintDeviceCapabilities") )
      goto LABEL_78;
    v13 = IsPsaEnabledForContractAsCurrentUser(a7, L"Windows.PrintSupportExtension", v30);
    if ( v13 < 0 )
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x690,
        (__int64)"printscan\\print\\drivers\\usermode\\driverui\\dll\\printconfig\\connectionmanagement.cpp",
        (const char *)(unsigned int)v13);
    if ( !v30[0] )
    {
LABEL_78:
      if ( (unsigned int)_o__wcsicmp(a4, L"Catalog.cat")
        || (ConnectionSpecificFilePath = GetTempCatalogPath(a4, lpFileName), ConnectionSpecificFilePath >= 0) )
      {
        ConnectionSpecificFilePath = CreateDataFile(lpFileName, pData, pcbNeeded, v38);
      }
      else if ( WPP_GLOBAL_Control != (PrintConfig::CPageImageableSize *)&WPP_GLOBAL_Control
             && *((char *)WPP_GLOBAL_Control + 68) < 0 )
      {
        WPP_SF_S(
          *((_QWORD *)WPP_GLOBAL_Control + 7),
          0x3Au,
          (const GUID *)WPP_799f402e917533f804c44f52fde54aed_Traceguids,
          a4);
      }
      goto LABEL_51;
    }
    try
    {
      Block = 0;
      hPrintera = a7;
      v40[0] = &hPrintera;
      v40[1] = &Block;
      if ( (int)ExceptionBoundary__lambda_5648f5919d1758734759f438906712d7_((__int64)v40) < 0 )
      {
LABEL_42:
        v27 = Block;
        if ( Block )
        {
          PrintConfig::CConfigManager::~CConfigManager((PrintConfig::CConfigManager *)Block);
          operator delete(v27);
        }
        goto LABEL_65;
      }
      hPrintera = 0;
      v14 = PrintConfig::CPrinterQueue::Create(a7, &hPrintera);
      if ( v14 < 0 )
      {
        if ( WPP_GLOBAL_Control != (PrintConfig::CPageImageableSize *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 1) != 0 )
        {
          WPP_SF_d(
            *((_QWORD *)WPP_GLOBAL_Control + 7),
            0x39u,
            (const GUID *)WPP_799f402e917533f804c44f52fde54aed_Traceguids,
            v14);
        }
        hr_error::hr_error((hr_error *)pExceptionObject, v14);
        throw (hr_error *)pExceptionObject;
      }
      v15 = operator new(0x80u);
      v16 = (BSTR *)PrintConfig::CConfigManager::CConfigManager((__int64)v15, (__int64 *)&hPrintera);
      v40[0] = v16;
      PrintConfig::CConfigManager::Initialize(v16);
      v36 = 0;
      nNumberOfBytesToWrite = pcbNeeded;
      v47 = 0;
      v48 = 0;
      v49 = 7;
      LOWORD(v47) = 0;
      v29 = 0;
      v17 = 0;
      pv = 0;
      BestLanguageResource = PrintConfig::CConfigManager::RetrieveBestLanguageResource(
                               (PrintConfig **)Block,
                               (__int64)&v47,
                               (__int64)&pv,
                               (__int64)&v29);
      v20 = v29;
      if ( v29 || BestLanguageResource != -2147024893 )
      {
        if ( BestLanguageResource < 0 )
        {
LABEL_36:
          if ( pv )
            CoTaskMemFree(pv);
          std::wstring::~wstring((char **)&v47);
          if ( v16 )
          {
            PrintConfig::CConfigManager::~CConfigManager((PrintConfig::CConfigManager *)v16);
            operator delete(v16);
          }
          if ( hPrintera )
            (*(void (__fastcall **)(HANDLE))(*(_QWORD *)hPrintera + 16LL))(hPrintera);
          goto LABEL_42;
        }
      }
      else
      {
        if ( !v48 )
          PrintConfig::CConfigManager::RetrieveBestLanguage((__int64)Block, (__int64)&v47);
        if ( pv )
        {
          LastError = GetLastError();
          CoTaskMemFree(pv);
          SetLastError(LastError);
        }
        pv = 0;
        PrintConfig::CConfigManager::CreateEmptyPdr(v19, (unsigned __int8 **)&pv, &v29);
        v17 = 1;
        v20 = v29;
      }
      v22 = &v47;
      if ( v49 > 7 )
        v22 = (__int128 *)v47;
      ConnectionSpecificFilePath = PrintConfig::CIppCSRHelper::CallPsaUpdatePdcAndPdrIfNeeded(
                                     (const BYTE **)&lpBuffer,
                                     pcbNeeded,
                                     (const BYTE **)&pv,
                                     v20,
                                     (__int64)v22,
                                     a7,
                                     &nNumberOfBytesToWrite,
                                     &v36);
      if ( ConnectionSpecificFilePath >= 0 )
      {
        if ( v36 )
          PrintConfig::CConfigManager::CommitLanguageResources((__int64)Block, &v47, v17, (__int64)pv, v36);
        v23 = nNumberOfBytesToWrite;
        v24 = (unsigned __int8 *)lpBuffer;
        ConnectionSpecificFilePath = CreateDataFile(lpFileName, lpBuffer, nNumberOfBytesToWrite, v38);
        if ( ConnectionSpecificFilePath >= 0 )
        {
          UpdateGpdConfigData(lpFileName, (struct PrintConfig::CConfigManager *)v16, v24, v23);
          if ( wil::details::FeatureImpl<__WilFeatureTraits_Feature_PrintIppPsaStabilityFixes_2505>::__private_IsEnabled((wil::details *)`wil::Feature<__WilFeatureTraits_Feature_PrintIppPsaStabilityFixes_2505>::GetImpl'::`2'::impl) )
          {
            PrintConfig::CConfigManager::DeletePrintCapabilitiesCacheFile((PrintConfig::CConfigManager *)v16, v25, v26);
            PrintConfig::CConfigManager::SavePrintCapabilitesToCacheFile((PCWSTR *)v16);
          }
        }
      }
      goto LABEL_36;
    }
    catch ( std::bad_alloc )
    {
      v29 = -2147024882;
      ConnectionSpecificFilePath = -2147024882;
      goto LABEL_51;
    }
    catch ( const hr_error *v45 )
    {
      v29 = *((_DWORD *)v45 + 6);
      ConnectionSpecificFilePath = v29;
      goto LABEL_51;
    }
    catch ( const PrintCore::WindowsError *v44 )
    {
      v29 = *((_DWORD *)v44 + 6);
      ConnectionSpecificFilePath = v29;
      goto LABEL_51;
    }
    catch ( std::exception )
    {
      v29 = -2147467259;
      ConnectionSpecificFilePath = -2147467259;
      goto LABEL_51;
    }
    catch ( ... )
    {
      v29 = -2147418113;
      ConnectionSpecificFilePath = -2147418113;
      goto LABEL_51;
    }
LABEL_65:
    goto LABEL_51;
  }
  ConnectionSpecificFilePath = -2147024662;
LABEL_56:
  if ( lpBuffer )
    CoTaskMemFree((LPVOID)lpBuffer);
  return (unsigned int)ConnectionSpecificFilePath;
}

```

## disassembly

```asm
0x180010abc  push    rbx
0x180010abe  push    rsi
0x180010abf  push    rdi
0x180010ac0  push    r12
0x180010ac2  push    r13
0x180010ac4  push    r14
0x180010ac6  push    r15
0x180010ac8  sub     rsp, 110h
0x180010acf  mov     [rsp+148h+var_98], 0FFFFFFFFFFFFFFFEh
0x180010adb  mov     rax, cs:__security_cookie
0x180010ae2  xor     rax, rsp
0x180010ae5  mov     [rsp+148h+var_40], rax
0x180010aed  mov     r14, r9
0x180010af0  mov     r13, r8
0x180010af3  mov     [rsp+148h+Block], rdx
0x180010af8  mov     rax, rcx
0x180010afb  mov     [rsp+148h+hPrinter], rcx
0x180010b00  mov     r15, [rsp+148h+lpFileName]
0x180010b08  mov     r12, [rsp+148h+arg_30]
0x180010b10  mov     rcx, [rsp+148h+arg_38]
0x180010b18  mov     [rsp+148h+var_D0], rcx
0x180010b1d  xor     edi, edi
0x180010b1f  mov     [rsp+148h+var_108], edi
0x180010b23  mov     [rsp+148h+var_100], edi
0x180010b27  mov     [rsp+148h+pType], edi
0x180010b2b  lea     rcx, [rsp+148h+var_100]
0x180010b30  mov     [rsp+148h+pcbNeeded], rcx; pcbNeeded
0x180010b35  mov     [rsp+148h+nSize], edi; nSize
0x180010b39  mov     [rsp+148h+pData], rdi; pData
0x180010b3e  lea     r9, [rsp+148h+pType]; pType
0x180010b43  lea     rdx, pKeyName; "ConfigDriverData"
0x180010b4a  mov     rcx, rax; hPrinter
0x180010b4d  call    cs:__imp_GetPrinterDataExW
0x180010b54  nop     dword ptr [rax+rax+00h]
0x180010b59  mov     esi, eax
0x180010b5b  cmp     eax, 0EAh
0x180010b60  jz      short loc_180010B81
0x180010b62  test    eax, eax
0x180010b64  jle     short loc_180010B6F
0x180010b66  movzx   esi, ax
0x180010b69  or      esi, 80070000h
0x180010b6f  test    esi, esi
0x180010b71  js      loc_180011015
0x180010b77  mov     esi, 80004005h
0x180010b7c  jmp     loc_180011015
0x180010b81  mov     ecx, [rsp+148h+var_100]; cb
0x180010b85  call    cs:__imp_CoTaskMemAlloc
0x180010b8c  nop     dword ptr [rax+rax+00h]
0x180010b91  mov     rbx, rax
0x180010b94  mov     [rsp+148h+lpBuffer], rax
0x180010b9c  test    rax, rax
0x180010b9f  jnz     short loc_180010BAB
0x180010ba1  mov     esi, 8007000Eh
0x180010ba6  jmp     loc_180010FF9
0x180010bab  mov     eax, [rsp+148h+var_100]
0x180010baf  lea     rcx, [rsp+148h+var_100]
0x180010bb4  mov     [rsp+148h+pcbNeeded], rcx; pcbNeeded
0x180010bb9  mov     [rsp+148h+nSize], eax; nSize
0x180010bbd  mov     [rsp+148h+pData], rbx; int
0x180010bc2  lea     r9, [rsp+148h+pType]; pType
0x180010bc7  mov     r8, r13; pValueName
0x180010bca  lea     rdx, pKeyName; "ConfigDriverData"
0x180010bd1  mov     rcx, [rsp+148h+hPrinter]; hPrinter
0x180010bd6  call    cs:__imp_GetPrinterDataExW
0x180010bdd  nop     dword ptr [rax+rax+00h]
0x180010be2  test    eax, eax
0x180010be4  jz      short loc_180010BF0
0x180010be6  mov     esi, 800700EAh
0x180010beb  jmp     loc_180010FF9
0x180010bf0  lea     rdx, [rsp+148h+var_108]; int *
0x180010bf5  lea     rcx, [rsp+148h+hLibModule]; this
0x180010bfd  call    ??0RevertToPrinterRAII@@QEAA@PEAJ@Z; RevertToPrinterRAII::RevertToPrinterRAII(long *)
0x180010c02  nop
0x180010c03  mov     [r15], di
0x180010c07  mov     esi, [rsp+148h+var_108]
0x180010c0b  test    esi, esi
0x180010c0d  js      loc_180010FC0
0x180010c13  mov     r8, r15; unsigned __int16 *
0x180010c16  mov     rdx, r14; unsigned __int16 *
0x180010c19  mov     rcx, [rsp+148h+Block]; hkey
0x180010c1e  call    ?GetConnectionSpecificFilePath@@YAJPEAUHKEY__@@PEBGPEAG_K@Z; GetConnectionSpecificFilePath(HKEY__ *,ushort const *,ushort *,unsigned __int64)
0x180010c23  mov     esi, eax
0x180010c25  test    eax, eax
0x180010c27  js      loc_180010FC0
0x180010c2d  mov     [rsp+148h+var_104], dil
0x180010c32  test    r12, r12
0x180010c35  jz      loc_180010F4B
0x180010c3b  lea     rdx, aPrintdevicecap_5; "PrintDeviceCapabilities"
0x180010c42  mov     rcx, r13; String1
0x180010c45  call    wcscmp_0
0x180010c4a  test    eax, eax
0x180010c4c  jnz     loc_180010F4B
0x180010c52  lea     r8, [rsp+148h+var_104]
0x180010c57  lea     rdx, aWindowsPrintsu_1; "Windows.PrintSupportExtension"
0x180010c5e  mov     rcx, r12
0x180010c61  call    cs:__imp_IsPsaEnabledForContractAsCurrentUser
0x180010c68  nop     dword ptr [rax+rax+00h]
0x180010c6d  mov     rcx, [rsp+148h]; this
0x180010c75  test    eax, eax
0x180010c77  jns     short loc_180010C8D
0x180010c79  mov     r9d, eax; char *
0x180010c7c  lea     r8, aPrintscanPrint_3; "printscan\\print\\drivers\\usermode\\dr"...
0x180010c83  mov     edx, 690h; void *
0x180010c88  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180010c8d  cmp     [rsp+148h+var_104], dil
0x180010c92  jz      loc_180010F4B
0x180010c98  mov     [rsp+148h+Block], rdi
0x180010c9d  mov     [rsp+148h+hPrinter], r12
0x180010ca2  lea     rax, [rsp+148h+hPrinter]
0x180010ca7  mov     [rsp+148h+var_C0], rax
0x180010caf  lea     rax, [rsp+148h+Block]
0x180010cb4  mov     [rsp+148h+var_B8], rax
0x180010cbc  lea     rcx, [rsp+148h+var_C0]
0x180010cc4  call    ExceptionBoundary__lambda_5648f5919d1758734759f438906712d7___; ExceptionBoundary__lambda_5648f5919d1758734759f438906712d7_
0x180010cc9  nop
0x180010cca  test    eax, eax
0x180010ccc  js      loc_180010F23
0x180010cd2  mov     [rsp+148h+hPrinter], rdi
0x180010cd7  lea     rdx, [rsp+148h+hPrinter]
0x180010cdc  mov     rcx, r12; unsigned __int16 *
0x180010cdf  call    ?Create@CPrinterQueue@PrintConfig@@SAJPEBGAEAV?$CComPtr@UIPrinterQueue@@@ATL@@@Z; PrintConfig::CPrinterQueue::Create(ushort const *,ATL::CComPtr<IPrinterQueue> &)
0x180010ce4  mov     r14d, eax
0x180010ce7  test    eax, eax
0x180010ce9  js      loc_18001103B
0x180010cef  mov     ecx, 80h; Size
0x180010cf4  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180010cf9  lea     rdx, [rsp+148h+hPrinter]
0x180010cfe  mov     rcx, rax
0x180010d01  call    ??0CConfigManager@PrintConfig@@QEAA@AEBV?$CComPtr@UIPrinterQueue@@@ATL@@@Z; PrintConfig::CConfigManager::CConfigManager(ATL::CComPtr<IPrinterQueue> const &)
0x180010d06  mov     r14, rax
0x180010d09  mov     [rsp+148h+var_C0], rax
0x180010d11  mov     rcx, rax; this
0x180010d14  call    ?Initialize@CConfigManager@PrintConfig@@QEAAXXZ; PrintConfig::CConfigManager::Initialize(void)
0x180010d19  mov     [rsp+148h+var_DC], edi
0x180010d1d  mov     eax, [rsp+148h+var_100]
0x180010d21  mov     [rsp+148h+nNumberOfBytesToWrite], eax
0x180010d25  xorps   xmm0, xmm0
0x180010d28  movups  [rsp+148h+var_60], xmm0
0x180010d30  mov     [rsp+148h+var_50], rdi
0x180010d38  mov     [rsp+148h+var_48], 7
0x180010d44  mov     word ptr [rsp+148h+var_60], di
0x180010d4c  mov     [rsp+148h+var_108], edi
0x180010d50  mov     bl, dil
0x180010d53  mov     [rsp+148h+pv], rdi
0x180010d58  lea     r9, [rsp+148h+var_108]
0x180010d5d  lea     r8, [rsp+148h+pv]
0x180010d62  lea     rdx, [rsp+148h+var_60]
0x180010d6a  mov     rcx, [rsp+148h+Block]
0x180010d6f  call    ?RetrieveBestLanguageResource@CConfigManager@PrintConfig@@QEAAJAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAPEAEPEAK@Z; PrintConfig::CConfigManager::RetrieveBestLanguageResource(std::wstring &,uchar * *,ulong *)
0x180010d74  mov     r9d, [rsp+148h+var_108]
0x180010d79  test    r9d, r9d
0x180010d7c  jnz     short loc_180010DF2
0x180010d7e  cmp     eax, 80070003h
0x180010d83  jnz     short loc_180010DF2
0x180010d85  cmp     [rsp+148h+var_50], rdi
0x180010d8d  jnz     short loc_180010DA1
0x180010d8f  lea     rdx, [rsp+148h+var_60]
0x180010d97  mov     rcx, [rsp+148h+Block]
0x180010d9c  call    ?RetrieveBestLanguage@CConfigManager@PrintConfig@@QEAAJAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; PrintConfig::CConfigManager::RetrieveBestLanguage(std::wstring &)
0x180010da1  cmp     [rsp+148h+pv], rdi
0x180010da6  jz      short loc_180010DD5
0x180010da8  call    cs:__imp_GetLastError
0x180010daf  nop     dword ptr [rax+rax+00h]
0x180010db4  mov     ebx, eax
0x180010db6  mov     rcx, [rsp+148h+pv]; pv
0x180010dbb  call    cs:__imp_CoTaskMemFree
0x180010dc2  nop     dword ptr [rax+rax+00h]
0x180010dc7  mov     ecx, ebx; dwErrCode
0x180010dc9  call    cs:__imp_SetLastError
0x180010dd0  nop     dword ptr [rax+rax+00h]
0x180010dd5  mov     [rsp+148h+pv], rdi
0x180010dda  lea     r8, [rsp+148h+var_108]; unsigned int *
0x180010ddf  lea     rdx, [rsp+148h+pv]; unsigned __int8 **
0x180010de4  call    ?CreateEmptyPdr@CConfigManager@PrintConfig@@QEAAJPEAPEAEPEAK@Z; PrintConfig::CConfigManager::CreateEmptyPdr(uchar * *,ulong *)
0x180010de9  mov     bl, 1
0x180010deb  mov     r9d, [rsp+148h+var_108]
0x180010df0  jmp     short loc_180010DFA
0x180010df2  test    eax, eax
0x180010df4  js      loc_180010ECC
0x180010dfa  lea     rax, [rsp+148h+var_60]
0x180010e02  cmp     [rsp+148h+var_48], 7
0x180010e0b  cmova   rax, qword ptr [rsp+148h+var_60]
0x180010e14  lea     rcx, [rsp+148h+var_DC]
0x180010e19  mov     [rsp+148h+var_110], rcx
0x180010e1e  lea     rcx, [rsp+148h+nNumberOfBytesToWrite]
0x180010e23  mov     [rsp+148h+pcbNeeded], rcx
0x180010e28  mov     qword ptr [rsp+148h+nSize], r12
0x180010e2d  mov     [rsp+148h+pData], rax
0x180010e32  lea     r8, [rsp+148h+pv]
0x180010e37  mov     edx, [rsp+148h+var_100]
0x180010e3b  lea     rcx, [rsp+148h+lpBuffer]
0x180010e43  call    ?CallPsaUpdatePdcAndPdrIfNeeded@CIppCSRHelper@PrintConfig@@SAJAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@wil@@H0HPEBG1PEAK2@Z; PrintConfig::CIppCSRHelper::CallPsaUpdatePdcAndPdrIfNeeded(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>> &,int,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>> &,int,ushort const *,ushort const *,ulong *,ulong *)
0x180010e48  mov     esi, eax
0x180010e4a  test    eax, eax
0x180010e4c  js      short loc_180010ECC
0x180010e4e  mov     eax, [rsp+148h+var_DC]
0x180010e52  test    eax, eax
0x180010e54  jz      short loc_180010E74
0x180010e56  mov     dword ptr [rsp+148h+pData], eax
0x180010e5a  mov     r9, [rsp+148h+pv]
0x180010e5f  mov     r8b, bl
0x180010e62  lea     rdx, [rsp+148h+var_60]
0x180010e6a  mov     rcx, [rsp+148h+Block]
0x180010e6f  call    ?CommitLanguageResources@CConfigManager@PrintConfig@@QEAAXAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@_NPEBEK@Z; PrintConfig::CConfigManager::CommitLanguageResources(std::wstring const &,bool,uchar const *,ulong)
0x180010e74  mov     r12d, [rsp+148h+nNumberOfBytesToWrite]
0x180010e79  mov     r9, [rsp+148h+var_D0]; struct Win32HandleRAII *
0x180010e7e  mov     r8d, r12d; nNumberOfBytesToWrite
0x180010e81  mov     rbx, [rsp+148h+lpBuffer]
0x180010e89  mov     rdx, rbx; lpBuffer
0x180010e8c  mov     rcx, r15; lpFileName
0x180010e8f  call    ?CreateDataFile@@YAJPEBGPEAE_KPEAVWin32HandleRAII@@@Z; CreateDataFile(ushort const *,uchar *,unsigned __int64,Win32HandleRAII *)
0x180010e94  mov     esi, eax
0x180010e96  test    eax, eax
0x180010e98  js      short loc_180010ECC
0x180010e9a  mov     r9d, r12d; unsigned __int64
0x180010e9d  mov     r8, rbx; unsigned __int8 *
0x180010ea0  mov     rdx, r14; struct PrintConfig::CConfigManager *
0x180010ea3  mov     rcx, r15; lpFileName
0x180010ea6  call    ?UpdateGpdConfigData@@YAXPEBGPEAVCConfigManager@PrintConfig@@PEAE_K@Z; UpdateGpdConfigData(ushort const *,PrintConfig::CConfigManager *,uchar *,unsigned __int64)
0x180010eab  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_PrintIppPsaStabilityFixes_2505@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_PrintIppPsaStabilityFixes_2505@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_PrintIppPsaStabilityFixes_2505> `wil::Feature<__WilFeatureTraits_Feature_PrintIppPsaStabilityFixes_2505>::GetImpl(void)'::`2'::impl
0x180010eb2  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_PrintIppPsaStabilityFixes_2505@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_PrintIppPsaStabilityFixes_2505>::__private_IsEnabled(void)
0x180010eb7  test    al, al
0x180010eb9  jz      short loc_180010ECC
0x180010ebb  mov     rcx, r14; this
0x180010ebe  call    ?DeletePrintCapabilitiesCacheFile@CConfigManager@PrintConfig@@QEAAXXZ; PrintConfig::CConfigManager::DeletePrintCapabilitiesCacheFile(void)
0x180010ec3  mov     rcx, r14; this
0x180010ec6  call    ?SavePrintCapabilitesToCacheFile@CConfigManager@PrintConfig@@QEAAXXZ; PrintConfig::CConfigManager::SavePrintCapabilitesToCacheFile(void)
0x180010ecb  nop
0x180010ecc  mov     rcx, [rsp+148h+pv]; pv
0x180010ed1  test    rcx, rcx
0x180010ed4  jz      short loc_180010EE3
0x180010ed6  call    cs:__imp_CoTaskMemFree
0x180010edd  nop     dword ptr [rax+rax+00h]
0x180010ee2  nop
0x180010ee3  lea     rcx, [rsp+148h+var_60]
0x180010eeb  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180010ef0  nop
0x180010ef1  test    r14, r14
0x180010ef4  jz      short loc_180010F0C
0x180010ef6  mov     rcx, r14; this
0x180010ef9  call    ??1CConfigManager@PrintConfig@@QEAA@XZ; PrintConfig::CConfigManager::~CConfigManager(void)
0x180010efe  mov     edx, 80h
0x180010f03  mov     rcx, r14; Block
0x180010f06  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180010f0b  nop
0x180010f0c  mov     rcx, [rsp+148h+hPrinter]
0x180010f11  test    rcx, rcx
0x180010f14  jz      short loc_180010F23
0x180010f16  mov     rax, [rcx]
0x180010f19  mov     rax, [rax+10h]
0x180010f1d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010f22  nop
0x180010f23  mov     rbx, [rsp+148h+Block]
0x180010f28  test    rbx, rbx
0x180010f2b  jz      short loc_180010F43
0x180010f2d  mov     rcx, rbx; this
0x180010f30  call    ??1CConfigManager@PrintConfig@@QEAA@XZ; PrintConfig::CConfigManager::~CConfigManager(void)
0x180010f35  mov     edx, 80h
0x180010f3a  mov     rcx, rbx; Block
0x180010f3d  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180010f42  nop
0x180010f43  jmp     short loc_180010FC0
0x180010f45  mov     esi, [rsp+148h+var_108]
0x180010f49  jmp     short loc_180010FC0
0x180010f4b  lea     rdx, aCatalogCat; "Catalog.cat"
0x180010f52  mov     rcx, r14
0x180010f55  call    cs:__imp__o__wcsicmp
0x180010f5c  nop     dword ptr [rax+rax+00h]
0x180010f61  test    eax, eax
0x180010f63  jnz     short loc_180010FA9
0x180010f65  mov     rdx, r15; unsigned __int16 *
0x180010f68  mov     rcx, r14; unsigned __int16 *
0x180010f6b  call    ?GetTempCatalogPath@@YAJPEBGPEAG_K@Z; GetTempCatalogPath(ushort const *,ushort *,unsigned __int64)
0x180010f70  mov     esi, eax
0x180010f72  test    eax, eax
0x180010f74  jns     short loc_180010FA9
0x180010f76  lea     rax, WPP_GLOBAL_Control
0x180010f7d  mov     rcx, cs:WPP_GLOBAL_Control
0x180010f84  cmp     rcx, rax
0x180010f87  jz      short loc_180010FC0
0x180010f89  test    byte ptr [rcx+44h], 80h
0x180010f8d  jz      short loc_180010FC0
0x180010f8f  mov     edx, 3Ah ; ':'
0x180010f94  mov     r9, r14
0x180010f97  lea     r8, WPP_799f402e917533f804c44f52fde54aed_Traceguids
0x180010f9e  mov     rcx, [rcx+38h]
0x180010fa2  call    WPP_SF_S
0x180010fa7  jmp     short loc_180010FC0
0x180010fa9  mov     r9, [rsp+148h+var_D0]; struct Win32HandleRAII *
0x180010fae  mov     r8d, [rsp+148h+var_100]; nNumberOfBytesToWrite
0x180010fb3  mov     rdx, rbx; lpBuffer
0x180010fb6  mov     rcx, r15; lpFileName
0x180010fb9  call    ?CreateDataFile@@YAJPEBGPEAE_KPEAVWin32HandleRAII@@@Z; CreateDataFile(ushort const *,uchar *,unsigned __int64,Win32HandleRAII *)
0x180010fbe  mov     esi, eax
0x180010fc0  mov     rax, [rsp+148h+var_A0]
0x180010fc8  test    rax, rax
0x180010fcb  jz      short loc_180010FDF
0x180010fcd  mov     rcx, [rsp+148h+var_A8]
0x180010fd5  test    rcx, rcx
0x180010fd8  jz      short loc_180010FDF
  ... truncated ...
```
