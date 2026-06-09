# CopyFileFromPrinterData(void *,HKEY__ *,ushort const *,ushort *,ushort *,ulong,ushort const *,Win32HandleRAII *)

- ea: `0x18001053c`
- end: `0x180010ac0`
- name: `?CopyFileFromPrinterData@@YAJPEAXPEAUHKEY__@@PEBGPEAG3K2PEAVWin32HandleRAII@@@Z`
- size: `1412`
- prototype: `__int64 __usercall@<rax>(HANDLE hPrinter@<rcx>, HKEY@<rdx>, const unsigned __int16 *@<r8>, unsigned __int16 *@<r9>, LPCWSTR lpFileName, unsigned int, const unsigned __int16 *, struct Win32HandleRAII *)`
- caller_count: `2`
- callee_count: `29`
- tags: `file_ops, registry_config, loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x180013ea4`
- `0x180018200`

## callees

- `0x1800032e0`
- `0x180003310`
- `0x180003b00`
- `0x180004424`
- `0x1800060ec`
- `0x18000e550`
- `0x18000f380`
- `0x18000f590`
- `0x18000f770`
- `0x18001053c`
- `0x180010d40`
- `0x180013a1c`
- `0x180014344`
- `0x180017e70`
- `0x18001878c`
- `0x180018bbc`
- `0x180018bfc`
- `0x180038ed8`
- `0x180041038`
- `0x180041154`
- `0x180041588`
- `0x180045828`
- `0x1800480f0`
- `0x180048240`
- `0x180049be0`
- `0x180053468`
- `0x180057994`
- `0x1801adb1c`
- `0x1801c3010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180010995`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180010995`
- `KERNEL32!FreeLibrary` at `0x180010a26`
- `KERNEL32!FreeLibrary` at `0x180010a26`
- `KERNEL32!SetLastError` at `0x180010825`
- `KERNEL32!SetLastError` at `0x180010825`
- `KERNEL32!GetLastError` at `0x180010810`
- `KERNEL32!GetLastError` at `0x180010810`
- `ole32!CoTaskMemAlloc` at `0x1800105ff`
- `ole32!CoTaskMemAlloc` at `0x1800105ff`
- `ole32!CoTaskMemFree` at `0x18001081d`
- `ole32!CoTaskMemFree` at `0x18001091c`
- `ole32!CoTaskMemFree` at `0x180010a3d`
- `ole32!CoTaskMemFree` at `0x18001081d`
- `ole32!CoTaskMemFree` at `0x18001091c`
- `ole32!CoTaskMemFree` at `0x180010a3d`
- `WINSPOOL!GetPrinterDataExW` at `0x1800105cd`
- `WINSPOOL!GetPrinterDataExW` at `0x18001064a`
- `WINSPOOL!GetPrinterDataExW` at `0x1800105cd`
- `WINSPOOL!GetPrinterDataExW` at `0x18001064a`
- `Print.PrintSupport.Source!IsPsaEnabledForContractAsCurrentUser` at `0x1800106cf`
- `Print.PrintSupport.Source!IsPsaEnabledForContractAsCurrentUser` at `0x1800106cf`

## string_xrefs

- `0x1800105c3`: `ConfigDriverData`
- `0x18001063e`: `ConfigDriverData`
- `0x1800106c5`: `Windows.PrintSupportExtension`
- `0x1800106e4`: `printscan\print\drivers\usermode\driverui\dll\printconfig\connectionmanagement.cpp`

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
  void *v12; // rbx
  unsigned __int64 v13; // r9
  int v14; // eax
  int v15; // r14d
  void *v16; // rax
  PrintConfig::CConfigManager *v17; // r14
  char v18; // bl
  int v19; // eax
  PrintConfig::CConfigManager *v20; // rcx
  UINT v21; // r9d
  DWORD LastError; // ebx
  __int128 *v23; // rax
  int v24; // r8d
  DWORD v25; // r12d
  unsigned __int8 *v26; // rbx
  void *v27; // rbx
  unsigned __int64 v28; // r8
  int pData; // [rsp+20h] [rbp-128h]
  unsigned int v31; // [rsp+40h] [rbp-108h] BYREF
  _BYTE v32[4]; // [rsp+44h] [rbp-104h] BYREF
  DWORD pcbNeeded; // [rsp+48h] [rbp-100h] BYREF
  LPVOID pv; // [rsp+50h] [rbp-F8h] BYREF
  void *Block; // [rsp+58h] [rbp-F0h] BYREF
  HANDLE hPrintera; // [rsp+60h] [rbp-E8h] BYREF
  DWORD pType; // [rsp+68h] [rbp-E0h] BYREF
  int v38; // [rsp+6Ch] [rbp-DCh] BYREF
  DWORD nNumberOfBytesToWrite; // [rsp+70h] [rbp-D8h] BYREF
  struct Win32HandleRAII *v40; // [rsp+78h] [rbp-D0h]
  LPCVOID lpBuffer; // [rsp+80h] [rbp-C8h] BYREF
  _QWORD v42[2]; // [rsp+88h] [rbp-C0h] BYREF
  HMODULE hLibModule[2]; // [rsp+98h] [rbp-B0h] BYREF
  void (*v44)(void); // [rsp+A8h] [rbp-A0h]
  __int64 v45; // [rsp+B0h] [rbp-98h]
  const PrintCore::WindowsError *v46; // [rsp+B8h] [rbp-90h] BYREF
  const hr_error *v47; // [rsp+C0h] [rbp-88h] BYREF
  _BYTE pExceptionObject[32]; // [rsp+C8h] [rbp-80h] BYREF
  __int128 v49; // [rsp+E8h] [rbp-60h] BYREF
  __int64 v50; // [rsp+F8h] [rbp-50h]
  unsigned __int64 v51; // [rsp+100h] [rbp-48h]
  wil::details::in1diag3 *retaddr; // [rsp+148h] [rbp+0h]

  v45 = -2;
  Block = a2;
  hPrintera = hPrinter;
  v40 = a8;
  v31 = 0;
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
  v12 = CoTaskMemAlloc(pcbNeeded);
  lpBuffer = v12;
  if ( !v12 )
  {
    ConnectionSpecificFilePath = -2147024882;
    goto LABEL_55;
  }
  if ( !GetPrinterDataExW(hPrintera, L"ConfigDriverData", a3, &pType, (LPBYTE)v12, pcbNeeded, &pcbNeeded) )
  {
    RevertToPrinterRAII::RevertToPrinterRAII((RevertToPrinterRAII *)hLibModule, (int *)&v31);
    *lpFileName = 0;
    ConnectionSpecificFilePath = v31;
    if ( (v31 & 0x80000000) != 0
      || (ConnectionSpecificFilePath = GetConnectionSpecificFilePath((HKEY)Block, a4, lpFileName, v13),
          ConnectionSpecificFilePath < 0) )
    {
LABEL_50:
      if ( v44 && hLibModule[1] )
        v44();
      if ( hLibModule[0] )
        FreeLibrary(hLibModule[0]);
      goto LABEL_55;
    }
    v32[0] = 0;
    if ( !a7 || wcscmp_0(a3, L"PrintDeviceCapabilities") )
      goto LABEL_77;
    v14 = IsPsaEnabledForContractAsCurrentUser(a7, L"Windows.PrintSupportExtension", v32);
    if ( v14 < 0 )
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x690,
        (unsigned int)"printscan\\print\\drivers\\usermode\\driverui\\dll\\printconfig\\connectionmanagement.cpp",
        (const char *)(unsigned int)v14,
        pData);
    if ( !v32[0] )
    {
LABEL_77:
      if ( (unsigned int)_o__wcsicmp(a4, L"Catalog.cat")
        || (ConnectionSpecificFilePath = GetTempCatalogPath(a4, lpFileName, v28), ConnectionSpecificFilePath >= 0) )
      {
        ConnectionSpecificFilePath = CreateDataFile(lpFileName, v12, pcbNeeded, v40);
      }
      else if ( WPP_GLOBAL_Control != (PrintConfig::CPageImageableSize *)&WPP_GLOBAL_Control
             && *((char *)WPP_GLOBAL_Control + 68) < 0 )
      {
        WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 7), 58, WPP_590161d01b393194d11d22bd3bfd07b4_Traceguids, a4);
      }
      goto LABEL_50;
    }
    try
    {
      Block = 0;
      hPrintera = a7;
      v42[0] = &hPrintera;
      v42[1] = &Block;
      if ( (int)ExceptionBoundary__lambda_5648f5919d1758734759f438906712d7_(v42) < 0 )
      {
LABEL_41:
        v27 = Block;
        if ( Block )
        {
          PrintConfig::CConfigManager::~CConfigManager((PrintConfig::CConfigManager *)Block);
          operator delete(v27);
        }
        goto LABEL_64;
      }
      hPrintera = 0;
      v15 = PrintConfig::CPrinterQueue::Create(a7);
      if ( v15 < 0 )
      {
        if ( WPP_GLOBAL_Control != (PrintConfig::CPageImageableSize *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 1) != 0 )
        {
          WPP_SF_d(
            *((_QWORD *)WPP_GLOBAL_Control + 7),
            57,
            WPP_590161d01b393194d11d22bd3bfd07b4_Traceguids,
            (unsigned int)v15);
        }
        hr_error::hr_error((hr_error *)pExceptionObject, v15);
        throw (hr_error *)pExceptionObject;
      }
      v16 = operator new(0x80u);
      v17 = (PrintConfig::CConfigManager *)PrintConfig::CConfigManager::CConfigManager(
                                             (__int64)v16,
                                             (__int64 *)&hPrintera);
      v42[0] = v17;
      PrintConfig::CConfigManager::Initialize(v17);
      v38 = 0;
      nNumberOfBytesToWrite = pcbNeeded;
      v49 = 0;
      v50 = 0;
      v51 = 7;
      LOWORD(v49) = 0;
      v31 = 0;
      v18 = 0;
      pv = 0;
      v19 = PrintConfig::CConfigManager::RetrieveBestLanguageResource(Block, &v49, &pv, &v31);
      v21 = v31;
      if ( v31 || v19 != -2147024893 )
      {
        if ( v19 < 0 )
        {
LABEL_35:
          if ( pv )
            CoTaskMemFree(pv);
          std::wstring::~wstring(&v49);
          if ( v17 )
          {
            PrintConfig::CConfigManager::~CConfigManager(v17);
            operator delete(v17);
          }
          if ( hPrintera )
            (*(void (__fastcall **)(HANDLE))(*(_QWORD *)hPrintera + 16LL))(hPrintera);
          goto LABEL_41;
        }
      }
      else
      {
        if ( !v50 )
          PrintConfig::CConfigManager::RetrieveBestLanguage(Block, &v49);
        if ( pv )
        {
          LastError = GetLastError();
          CoTaskMemFree(pv);
          SetLastError(LastError);
        }
        pv = 0;
        PrintConfig::CConfigManager::CreateEmptyPdr(v20, (unsigned __int8 **)&pv, &v31);
        v18 = 1;
        v21 = v31;
      }
      v23 = &v49;
      if ( v51 > 7 )
        v23 = (__int128 *)v49;
      ConnectionSpecificFilePath = PrintConfig::CIppCSRHelper::CallPsaUpdatePdcAndPdrIfNeeded(
                                     (const BYTE **)&lpBuffer,
                                     pcbNeeded,
                                     (const BYTE **)&pv,
                                     v21,
                                     (__int64)v23,
                                     (__int64)a7,
                                     &nNumberOfBytesToWrite,
                                     &v38);
      if ( ConnectionSpecificFilePath >= 0 )
      {
        if ( v38 )
        {
          LOBYTE(v24) = v18;
          PrintConfig::CConfigManager::CommitLanguageResources((_DWORD)Block, (unsigned int)&v49, v24, (_DWORD)pv, v38);
        }
        v25 = nNumberOfBytesToWrite;
        v26 = (unsigned __int8 *)lpBuffer;
        ConnectionSpecificFilePath = CreateDataFile(lpFileName, lpBuffer, nNumberOfBytesToWrite, v40);
        if ( ConnectionSpecificFilePath >= 0 )
        {
          UpdateGpdConfigData(lpFileName, v17, v26, v25);
          PrintConfig::CConfigManager::DeletePrintCapabilitiesCacheFile(v17);
          PrintConfig::CConfigManager::SavePrintCapabilitesToCacheFile((PCWSTR *)v17);
        }
      }
      goto LABEL_35;
    }
    catch ( std::bad_alloc )
    {
      v31 = -2147024882;
      ConnectionSpecificFilePath = -2147024882;
      goto LABEL_50;
    }
    catch ( const hr_error *v47 )
    {
      v31 = *((_DWORD *)v47 + 6);
      ConnectionSpecificFilePath = v31;
      goto LABEL_50;
    }
    catch ( const PrintCore::WindowsError *v46 )
    {
      v31 = *((_DWORD *)v46 + 6);
      ConnectionSpecificFilePath = v31;
      goto LABEL_50;
    }
    catch ( std::exception )
    {
      v31 = -2147467259;
      ConnectionSpecificFilePath = -2147467259;
      goto LABEL_50;
    }
    catch ( ... )
    {
      v31 = -2147418113;
      ConnectionSpecificFilePath = -2147418113;
      goto LABEL_50;
    }
LABEL_64:
    goto LABEL_50;
  }
  ConnectionSpecificFilePath = -2147024662;
LABEL_55:
  if ( lpBuffer )
    CoTaskMemFree((LPVOID)lpBuffer);
  return (unsigned int)ConnectionSpecificFilePath;
}

```

## disassembly

```asm
0x18001053c  push    rbx
0x18001053e  push    rsi
0x18001053f  push    rdi
0x180010540  push    r12
0x180010542  push    r13
0x180010544  push    r14
0x180010546  push    r15
0x180010548  sub     rsp, 110h
0x18001054f  mov     [rsp+148h+var_98], 0FFFFFFFFFFFFFFFEh
0x18001055b  mov     rax, cs:__security_cookie
0x180010562  xor     rax, rsp
0x180010565  mov     [rsp+148h+var_40], rax
0x18001056d  mov     r14, r9
0x180010570  mov     r13, r8
0x180010573  mov     [rsp+148h+Block], rdx
0x180010578  mov     rax, rcx
0x18001057b  mov     [rsp+148h+hPrinter], rcx
0x180010580  mov     r15, [rsp+148h+lpFileName]
0x180010588  mov     r12, [rsp+148h+arg_30]
0x180010590  mov     rcx, [rsp+148h+arg_38]
0x180010598  mov     [rsp+148h+var_D0], rcx
0x18001059d  xor     edi, edi
0x18001059f  mov     [rsp+148h+var_108], edi
0x1800105a3  mov     [rsp+148h+var_100], edi
0x1800105a7  mov     [rsp+148h+pType], edi
0x1800105ab  lea     rcx, [rsp+148h+var_100]
0x1800105b0  mov     [rsp+148h+pcbNeeded], rcx; pcbNeeded
0x1800105b5  mov     [rsp+148h+nSize], edi; nSize
0x1800105b9  mov     [rsp+148h+pData], rdi; pData
0x1800105be  lea     r9, [rsp+148h+pType]; pType
0x1800105c3  lea     rdx, pKeyName; "ConfigDriverData"
0x1800105ca  mov     rcx, rax; hPrinter
0x1800105cd  call    cs:__imp_GetPrinterDataExW
0x1800105d3  mov     esi, eax
0x1800105d5  cmp     eax, 0EAh
0x1800105da  jz      short loc_1800105FB
0x1800105dc  test    eax, eax
0x1800105de  jle     short loc_1800105E9
0x1800105e0  movzx   esi, ax
0x1800105e3  or      esi, 80070000h
0x1800105e9  test    esi, esi
0x1800105eb  js      loc_180010A43
0x1800105f1  mov     esi, 80004005h
0x1800105f6  jmp     loc_180010A43
0x1800105fb  mov     ecx, [rsp+148h+var_100]; cb
0x1800105ff  call    cs:__imp_CoTaskMemAlloc
0x180010605  mov     rbx, rax
0x180010608  mov     [rsp+148h+lpBuffer], rax
0x180010610  test    rax, rax
0x180010613  jnz     short loc_18001061F
0x180010615  mov     esi, 8007000Eh
0x18001061a  jmp     loc_180010A2D
0x18001061f  mov     eax, [rsp+148h+var_100]
0x180010623  lea     rcx, [rsp+148h+var_100]
0x180010628  mov     [rsp+148h+pcbNeeded], rcx; pcbNeeded
0x18001062d  mov     [rsp+148h+nSize], eax; nSize
0x180010631  mov     [rsp+148h+pData], rbx; int
0x180010636  lea     r9, [rsp+148h+pType]; pType
0x18001063b  mov     r8, r13; pValueName
0x18001063e  lea     rdx, pKeyName; "ConfigDriverData"
0x180010645  mov     rcx, [rsp+148h+hPrinter]; hPrinter
0x18001064a  call    cs:__imp_GetPrinterDataExW
0x180010650  test    eax, eax
0x180010652  jz      short loc_18001065E
0x180010654  mov     esi, 800700EAh
0x180010659  jmp     loc_180010A2D
0x18001065e  lea     rdx, [rsp+148h+var_108]; int *
0x180010663  lea     rcx, [rsp+148h+hLibModule]; this
0x18001066b  call    ??0RevertToPrinterRAII@@QEAA@PEAJ@Z; RevertToPrinterRAII::RevertToPrinterRAII(long *)
0x180010670  nop
0x180010671  mov     [r15], di
0x180010675  mov     esi, [rsp+148h+var_108]
0x180010679  test    esi, esi
0x18001067b  js      loc_1800109FA
0x180010681  mov     r8, r15; unsigned __int16 *
0x180010684  mov     rdx, r14; unsigned __int16 *
0x180010687  mov     rcx, [rsp+148h+Block]; hkey
0x18001068c  call    ?GetConnectionSpecificFilePath@@YAJPEAUHKEY__@@PEBGPEAG_K@Z; GetConnectionSpecificFilePath(HKEY__ *,ushort const *,ushort *,unsigned __int64)
0x180010691  mov     esi, eax
0x180010693  test    eax, eax
0x180010695  js      loc_1800109FA
0x18001069b  mov     [rsp+148h+var_104], dil
0x1800106a0  test    r12, r12
0x1800106a3  jz      loc_18001098B
0x1800106a9  lea     rdx, aPrintdevicecap_5; "PrintDeviceCapabilities"
0x1800106b0  mov     rcx, r13; String1
0x1800106b3  call    wcscmp_0
0x1800106b8  test    eax, eax
0x1800106ba  jnz     loc_18001098B
0x1800106c0  lea     r8, [rsp+148h+var_104]
0x1800106c5  lea     rdx, aWindowsPrintsu_1; "Windows.PrintSupportExtension"
0x1800106cc  mov     rcx, r12
0x1800106cf  call    cs:__imp_IsPsaEnabledForContractAsCurrentUser
0x1800106d5  mov     rcx, [rsp+148h]; this
0x1800106dd  test    eax, eax
0x1800106df  jns     short loc_1800106F5
0x1800106e1  mov     r9d, eax; char *
0x1800106e4  lea     r8, aPrintscanPrint_3; "printscan\\print\\drivers\\usermode\\dr"...
0x1800106eb  mov     edx, 690h; void *
0x1800106f0  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1800106f5  cmp     [rsp+148h+var_104], dil
0x1800106fa  jz      loc_18001098B
0x180010700  mov     [rsp+148h+Block], rdi
0x180010705  mov     [rsp+148h+hPrinter], r12
0x18001070a  lea     rax, [rsp+148h+hPrinter]
0x18001070f  mov     [rsp+148h+var_C0], rax
0x180010717  lea     rax, [rsp+148h+Block]
0x18001071c  mov     [rsp+148h+var_B8], rax
0x180010724  lea     rcx, [rsp+148h+var_C0]
0x18001072c  call    ExceptionBoundary__lambda_5648f5919d1758734759f438906712d7___; ExceptionBoundary__lambda_5648f5919d1758734759f438906712d7_
0x180010731  nop
0x180010732  test    eax, eax
0x180010734  js      loc_180010963
0x18001073a  mov     [rsp+148h+hPrinter], rdi
0x18001073f  lea     rdx, [rsp+148h+hPrinter]
0x180010744  mov     rcx, r12; unsigned __int16 *
0x180010747  call    ?Create@CPrinterQueue@PrintConfig@@SAJPEBGAEAV?$CComPtr@UIPrinterQueue@@@ATL@@@Z; PrintConfig::CPrinterQueue::Create(ushort const *,ATL::CComPtr<IPrinterQueue> &)
0x18001074c  mov     r14d, eax
0x18001074f  test    eax, eax
0x180010751  js      loc_180010A68
0x180010757  mov     ecx, 80h; Size
0x18001075c  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180010761  lea     rdx, [rsp+148h+hPrinter]
0x180010766  mov     rcx, rax
0x180010769  call    ??0CConfigManager@PrintConfig@@QEAA@AEBV?$CComPtr@UIPrinterQueue@@@ATL@@@Z; PrintConfig::CConfigManager::CConfigManager(ATL::CComPtr<IPrinterQueue> const &)
0x18001076e  mov     r14, rax
0x180010771  mov     [rsp+148h+var_C0], rax
0x180010779  mov     rcx, rax; this
0x18001077c  call    ?Initialize@CConfigManager@PrintConfig@@QEAAXXZ; PrintConfig::CConfigManager::Initialize(void)
0x180010781  mov     [rsp+148h+var_DC], edi
0x180010785  mov     eax, [rsp+148h+var_100]
0x180010789  mov     [rsp+148h+nNumberOfBytesToWrite], eax
0x18001078d  xorps   xmm0, xmm0
0x180010790  movups  [rsp+148h+var_60], xmm0
0x180010798  mov     [rsp+148h+var_50], rdi
0x1800107a0  mov     [rsp+148h+var_48], 7
0x1800107ac  mov     word ptr [rsp+148h+var_60], di
0x1800107b4  mov     [rsp+148h+var_108], edi
0x1800107b8  mov     bl, dil
0x1800107bb  mov     [rsp+148h+pv], rdi
0x1800107c0  lea     r9, [rsp+148h+var_108]
0x1800107c5  lea     r8, [rsp+148h+pv]
0x1800107ca  lea     rdx, [rsp+148h+var_60]
0x1800107d2  mov     rcx, [rsp+148h+Block]
0x1800107d7  call    ?RetrieveBestLanguageResource@CConfigManager@PrintConfig@@QEAAJAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAPEAEPEAK@Z; PrintConfig::CConfigManager::RetrieveBestLanguageResource(std::wstring &,uchar * *,ulong *)
0x1800107dc  mov     r9d, [rsp+148h+var_108]
0x1800107e1  test    r9d, r9d
0x1800107e4  jnz     short loc_180010848
0x1800107e6  cmp     eax, 80070003h
0x1800107eb  jnz     short loc_180010848
0x1800107ed  cmp     [rsp+148h+var_50], rdi
0x1800107f5  jnz     short loc_180010809
0x1800107f7  lea     rdx, [rsp+148h+var_60]
0x1800107ff  mov     rcx, [rsp+148h+Block]
0x180010804  call    ?RetrieveBestLanguage@CConfigManager@PrintConfig@@QEAAJAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; PrintConfig::CConfigManager::RetrieveBestLanguage(std::wstring &)
0x180010809  cmp     [rsp+148h+pv], rdi
0x18001080e  jz      short loc_18001082B
0x180010810  call    cs:__imp_GetLastError
0x180010816  mov     ebx, eax
0x180010818  mov     rcx, [rsp+148h+pv]; pv
0x18001081d  call    cs:__imp_CoTaskMemFree
0x180010823  mov     ecx, ebx; dwErrCode
0x180010825  call    cs:__imp_SetLastError
0x18001082b  mov     [rsp+148h+pv], rdi
0x180010830  lea     r8, [rsp+148h+var_108]; unsigned int *
0x180010835  lea     rdx, [rsp+148h+pv]; unsigned __int8 **
0x18001083a  call    ?CreateEmptyPdr@CConfigManager@PrintConfig@@QEAAJPEAPEAEPEAK@Z; PrintConfig::CConfigManager::CreateEmptyPdr(uchar * *,ulong *)
0x18001083f  mov     bl, 1
0x180010841  mov     r9d, [rsp+148h+var_108]
0x180010846  jmp     short loc_180010850
0x180010848  test    eax, eax
0x18001084a  js      loc_180010912
0x180010850  lea     rax, [rsp+148h+var_60]
0x180010858  cmp     [rsp+148h+var_48], 7
0x180010861  cmova   rax, qword ptr [rsp+148h+var_60]
0x18001086a  lea     rcx, [rsp+148h+var_DC]
0x18001086f  mov     [rsp+148h+var_110], rcx
0x180010874  lea     rcx, [rsp+148h+nNumberOfBytesToWrite]
0x180010879  mov     [rsp+148h+pcbNeeded], rcx
0x18001087e  mov     qword ptr [rsp+148h+nSize], r12
0x180010883  mov     [rsp+148h+pData], rax
0x180010888  lea     r8, [rsp+148h+pv]
0x18001088d  mov     edx, [rsp+148h+var_100]
0x180010891  lea     rcx, [rsp+148h+lpBuffer]
0x180010899  call    ?CallPsaUpdatePdcAndPdrIfNeeded@CIppCSRHelper@PrintConfig@@SAJAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@wil@@H0HPEBG1PEAK2@Z; PrintConfig::CIppCSRHelper::CallPsaUpdatePdcAndPdrIfNeeded(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>> &,int,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>> &,int,ushort const *,ushort const *,ulong *,ulong *)
0x18001089e  mov     esi, eax
0x1800108a0  test    eax, eax
0x1800108a2  js      short loc_180010912
0x1800108a4  mov     eax, [rsp+148h+var_DC]
0x1800108a8  test    eax, eax
0x1800108aa  jz      short loc_1800108CA
0x1800108ac  mov     dword ptr [rsp+148h+pData], eax
0x1800108b0  mov     r9, [rsp+148h+pv]
0x1800108b5  mov     r8b, bl
0x1800108b8  lea     rdx, [rsp+148h+var_60]
0x1800108c0  mov     rcx, [rsp+148h+Block]
0x1800108c5  call    ?CommitLanguageResources@CConfigManager@PrintConfig@@QEAAXAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@_NPEBEK@Z; PrintConfig::CConfigManager::CommitLanguageResources(std::wstring const &,bool,uchar const *,ulong)
0x1800108ca  mov     r12d, [rsp+148h+nNumberOfBytesToWrite]
0x1800108cf  mov     r9, [rsp+148h+var_D0]; struct Win32HandleRAII *
0x1800108d4  mov     r8d, r12d; nNumberOfBytesToWrite
0x1800108d7  mov     rbx, [rsp+148h+lpBuffer]
0x1800108df  mov     rdx, rbx; lpBuffer
0x1800108e2  mov     rcx, r15; lpFileName
0x1800108e5  call    ?CreateDataFile@@YAJPEBGPEAE_KPEAVWin32HandleRAII@@@Z; CreateDataFile(ushort const *,uchar *,unsigned __int64,Win32HandleRAII *)
0x1800108ea  mov     esi, eax
0x1800108ec  test    eax, eax
0x1800108ee  js      short loc_180010912
0x1800108f0  mov     r9d, r12d; unsigned __int64
0x1800108f3  mov     r8, rbx; unsigned __int8 *
0x1800108f6  mov     rdx, r14; struct PrintConfig::CConfigManager *
0x1800108f9  mov     rcx, r15; lpFileName
0x1800108fc  call    ?UpdateGpdConfigData@@YAXPEBGPEAVCConfigManager@PrintConfig@@PEAE_K@Z; UpdateGpdConfigData(ushort const *,PrintConfig::CConfigManager *,uchar *,unsigned __int64)
0x180010901  mov     rcx, r14; this
0x180010904  call    ?DeletePrintCapabilitiesCacheFile@CConfigManager@PrintConfig@@QEAAXXZ; PrintConfig::CConfigManager::DeletePrintCapabilitiesCacheFile(void)
0x180010909  mov     rcx, r14; this
0x18001090c  call    ?SavePrintCapabilitesToCacheFile@CConfigManager@PrintConfig@@QEAAXXZ; PrintConfig::CConfigManager::SavePrintCapabilitesToCacheFile(void)
0x180010911  nop
0x180010912  mov     rcx, [rsp+148h+pv]; pv
0x180010917  test    rcx, rcx
0x18001091a  jz      short loc_180010923
0x18001091c  call    cs:__imp_CoTaskMemFree
0x180010922  nop
0x180010923  lea     rcx, [rsp+148h+var_60]
0x18001092b  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180010930  nop
0x180010931  test    r14, r14
0x180010934  jz      short loc_18001094C
0x180010936  mov     rcx, r14; this
0x180010939  call    ??1CConfigManager@PrintConfig@@QEAA@XZ; PrintConfig::CConfigManager::~CConfigManager(void)
0x18001093e  mov     edx, 80h
0x180010943  mov     rcx, r14; Block
0x180010946  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18001094b  nop
0x18001094c  mov     rcx, [rsp+148h+hPrinter]
0x180010951  test    rcx, rcx
0x180010954  jz      short loc_180010963
0x180010956  mov     rax, [rcx]
0x180010959  mov     rax, [rax+10h]
0x18001095d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010962  nop
0x180010963  mov     rbx, [rsp+148h+Block]
0x180010968  test    rbx, rbx
0x18001096b  jz      short loc_180010983
0x18001096d  mov     rcx, rbx; this
0x180010970  call    ??1CConfigManager@PrintConfig@@QEAA@XZ; PrintConfig::CConfigManager::~CConfigManager(void)
0x180010975  mov     edx, 80h
0x18001097a  mov     rcx, rbx; Block
0x18001097d  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180010982  nop
0x180010983  jmp     short loc_1800109FA
0x180010985  mov     esi, [rsp+148h+var_108]
0x180010989  jmp     short loc_1800109FA
0x18001098b  lea     rdx, aCatalogCat; "Catalog.cat"
0x180010992  mov     rcx, r14
0x180010995  call    cs:__imp__o__wcsicmp
0x18001099b  test    eax, eax
0x18001099d  jnz     short loc_1800109E3
0x18001099f  mov     rdx, r15; unsigned __int16 *
0x1800109a2  mov     rcx, r14; unsigned __int16 *
0x1800109a5  call    ?GetTempCatalogPath@@YAJPEBGPEAG_K@Z; GetTempCatalogPath(ushort const *,ushort *,unsigned __int64)
0x1800109aa  mov     esi, eax
0x1800109ac  test    eax, eax
0x1800109ae  jns     short loc_1800109E3
0x1800109b0  lea     rax, WPP_GLOBAL_Control
0x1800109b7  mov     rcx, cs:WPP_GLOBAL_Control
0x1800109be  cmp     rcx, rax
0x1800109c1  jz      short loc_1800109FA
0x1800109c3  test    byte ptr [rcx+44h], 80h
0x1800109c7  jz      short loc_1800109FA
0x1800109c9  mov     edx, 3Ah ; ':'
0x1800109ce  mov     r9, r14
0x1800109d1  lea     r8, WPP_590161d01b393194d11d22bd3bfd07b4_Traceguids
0x1800109d8  mov     rcx, [rcx+38h]
0x1800109dc  call    WPP_SF_S
0x1800109e1  jmp     short loc_1800109FA
0x1800109e3  mov     r9, [rsp+148h+var_D0]; struct Win32HandleRAII *
0x1800109e8  mov     r8d, [rsp+148h+var_100]; nNumberOfBytesToWrite
0x1800109ed  mov     rdx, rbx; lpBuffer
0x1800109f0  mov     rcx, r15; lpFileName
0x1800109f3  call    ?CreateDataFile@@YAJPEBGPEAE_KPEAVWin32HandleRAII@@@Z; CreateDataFile(ushort const *,uchar *,unsigned __int64,Win32HandleRAII *)
0x1800109f8  mov     esi, eax
0x1800109fa  mov     rax, [rsp+148h+var_A0]
0x180010a02  test    rax, rax
0x180010a05  jz      short loc_180010A19
0x180010a07  mov     rcx, [rsp+148h+var_A8]
0x180010a0f  test    rcx, rcx
0x180010a12  jz      short loc_180010A19
0x180010a14  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010a19  mov     rcx, [rsp+148h+hLibModule]; hLibModule
0x180010a21  test    rcx, rcx
0x180010a24  jz      short loc_180010A2D
0x180010a26  call    cs:__imp_FreeLibrary
0x180010a2c  nop
0x180010a2d  mov     rbx, [rsp+148h+lpBuffer]
0x180010a35  test    rbx, rbx
0x180010a38  jz      short loc_180010A43
0x180010a3a  mov     rcx, rbx; pv
0x180010a3d  call    cs:__imp_CoTaskMemFree
0x180010a43  mov     eax, esi
0x180010a45  mov     rcx, [rsp+148h+var_40]
  ... truncated ...
```
