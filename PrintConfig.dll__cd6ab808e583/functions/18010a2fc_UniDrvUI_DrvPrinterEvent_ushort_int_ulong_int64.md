# UniDrvUI::DrvPrinterEvent(ushort *,int,ulong,__int64)

- ea: `0x18010a2fc`
- end: `0x18010a9e2`
- name: `?DrvPrinterEvent@UniDrvUI@@YAHPEAGHK_J@Z`
- size: `1766`
- prototype: `int(UniDrvUI *__hidden this, unsigned __int16 *, int, unsigned int, __int64)`
- caller_count: `1`
- callee_count: `25`
- tags: `file_ops, authz_impersonation, loader_planting, installer_update, broker_com_uri`

## callers

- `0x18002f970`

## callees

- `0x1800060ec`
- `0x180102674`
- `0x18010427c`
- `0x180108df4`
- `0x180109b58`
- `0x18010a2fc`
- `0x18010adb0`
- `0x18010ae90`
- `0x18010b084`
- `0x18010b24c`
- `0x18010b36c`
- `0x18010b3dc`
- `0x18010e3d8`
- `0x18010e8e0`
- `0x18010f8cc`
- `0x180111180`
- `0x1801114c8`
- `0x1801231e4`
- `0x180149448`
- `0x18014a5f4`
- `0x18014a968`
- `0x18014ab8c`
- `0x18014e910`
- `0x180150ce8`
- `0x1801c3010`

## import_xrefs

- `KERNEL32!DeleteFileW` at `0x18010a7c5`
- `KERNEL32!DeleteFileW` at `0x18010a7c5`
- `KERNEL32!GetProcAddress` at `0x18010a5a5`
- `KERNEL32!GetProcAddress` at `0x18010a5c1`
- `KERNEL32!GetProcAddress` at `0x18010a5a5`
- `KERNEL32!GetProcAddress` at `0x18010a5c1`
- `KERNEL32!FreeLibrary` at `0x18010a427`
- `KERNEL32!FreeLibrary` at `0x18010a517`
- `KERNEL32!FreeLibrary` at `0x18010a639`
- `KERNEL32!FreeLibrary` at `0x18010a668`
- `KERNEL32!FreeLibrary` at `0x18010a427`
- `KERNEL32!FreeLibrary` at `0x18010a517`
- `KERNEL32!FreeLibrary` at `0x18010a639`
- `KERNEL32!FreeLibrary` at `0x18010a668`
- `KERNEL32!GetLastError` at `0x18010a546`
- `KERNEL32!GetLastError` at `0x18010a61a`
- `KERNEL32!GetLastError` at `0x18010a644`
- `KERNEL32!GetLastError` at `0x18010a91d`
- `KERNEL32!GetLastError` at `0x18010a546`
- `KERNEL32!GetLastError` at `0x18010a61a`
- `KERNEL32!GetLastError` at `0x18010a644`
- `KERNEL32!GetLastError` at `0x18010a91d`
- `KERNEL32!LocalFree` at `0x18010a7ce`
- `KERNEL32!LocalFree` at `0x18010a7dc`
- `KERNEL32!LocalFree` at `0x18010a7ea`
- `KERNEL32!LocalFree` at `0x18010a7ce`
- `KERNEL32!LocalFree` at `0x18010a7dc`
- `KERNEL32!LocalFree` at `0x18010a7ea`
- `KERNEL32!LoadLibraryExW` at `0x18010a412`
- `KERNEL32!LoadLibraryExW` at `0x18010a412`
- `OLEAUT32!__imp_SysStringLen` at `0x18010a3af`
- `OLEAUT32!__imp_SysStringLen` at `0x18010a3af`
- `WINSPOOL!ClosePrinter` at `0x18010a9be`
- `WINSPOOL!ClosePrinter` at `0x18010a9be`
- `WINSPOOL!OpenPrinterW` at `0x18010a53c`
- `WINSPOOL!OpenPrinterW` at `0x18010a759`
- `WINSPOOL!OpenPrinterW` at `0x18010a53c`
- `WINSPOOL!OpenPrinterW` at `0x18010a759`
- `IppCommon!IsModernPrinter` at `0x18010a44b`
- `IppCommon!IsModernPrinter` at `0x18010a4ab`
- `IppCommon!IsModernPrinter` at `0x18010a44b`
- `IppCommon!IsModernPrinter` at `0x18010a4ab`

## string_xrefs

- `0x18010a583`: `spoolss.dll`
- `0x18010a5b7`: `ImpersonatePrinterClient`
- `0x18010a40b`: `ippcommon.dll`
- `0x18010a553`: `OpenPrinter '%ws' failed: %d\n`
- `0x18010a623`: `PrinterEvent-ImpersonatePrinterClient failed: %d\n`
- `0x18010a64d`: `Couldn't load spoolss.dll: %d\n`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall UniDrvUI::DrvPrinterEvent(WCHAR *this, unsigned __int16 *a2, unsigned int a3, OLECHAR *a4)
{
  unsigned int v6; // r15d
  unsigned int v7; // r9d
  struct UniDrvUI::_COMMONINFO *v8; // rdx
  HMODULE Library; // rax
  unsigned __int16 *v10; // r9
  DWORD LastError; // eax
  __int64 (*ProcAddress)(void); // rsi
  FARPROC v13; // rdi
  __int64 v14; // rsi
  unsigned int v15; // r9d
  UniDrvUI *v16; // rcx
  struct UniDrvUI::_CACHEDFILE *v17; // r8
  struct PSUI::_CACHEDFILE *v18; // rdx
  DWORD v19; // eax
  DWORD v20; // eax
  struct PSUI::_CACHEDFILE *v21; // rdx
  UniDrvUI *v22; // rcx
  struct UniDrvUI::_COMMONINFO *v23; // rdx
  struct UniDrvUI::_COMMONINFO *v24; // rdx
  struct UniDrvUI::_COMMONINFO *v25; // r8
  UniDrvUI *v26; // rcx
  unsigned int v27; // r9d
  wchar_t *PrinterDataString; // rax
  wchar_t *v29; // rsi
  wchar_t *v30; // rdi
  WCHAR *v31; // rbx
  const wchar_t *v32; // rax
  unsigned __int16 *v33; // r8
  const WCHAR *v34; // rax
  __int64 v35; // rcx
  __int64 v36; // rbx
  int v37; // edi
  __int64 v38; // r9
  __int64 v39; // r10
  __int64 v40; // r8
  __int64 v41; // r11
  __int64 v42; // rcx
  int v43; // eax
  unsigned int (__fastcall *v44)(LPWSTR, _QWORD, _QWORD, OLECHAR *); // rax
  DWORD v45; // eax
  unsigned int v47; // [rsp+38h] [rbp-49h] BYREF
  UniDrvUI *v48; // [rsp+40h] [rbp-41h] BYREF
  HMODULE hModule; // [rsp+48h] [rbp-39h] BYREF
  HANDLE phPrinter; // [rsp+50h] [rbp-31h] BYREF
  HMODULE hLibModule[2]; // [rsp+58h] [rbp-29h] BYREF
  void (*v52)(void); // [rsp+68h] [rbp-19h]
  __int128 v53; // [rsp+70h] [rbp-11h] BYREF
  __int128 v54; // [rsp+80h] [rbp-1h]
  _QWORD v55[9]; // [rsp+90h] [rbp+Fh] BYREF
  LPWSTR pPrinterName; // [rsp+E8h] [rbp+67h] BYREF
  char v57; // [rsp+F0h] [rbp+6Fh] BYREF

  pPrinterName = this;
  v55[1] = -2;
  v6 = (unsigned int)a2;
  hModule = 0;
  v48 = 0;
  phPrinter = 0;
  v47 = 1;
  v53 = 0;
  v54 = 0;
  DriverUi::DriverUiTelemetry::WriteDbgTraceInfo(
    "UniDrvUI::DrvPrinterEvent",
    L"Entering DrvPrinterEvent: %d ...\n",
    (unsigned int)a2);
  switch ( v6 )
  {
    case 2u:
      goto LABEL_52;
    case 3u:
      v22 = UniDrvUI::PLoadCommonInfo(0, pPrinterName, (unsigned __int16 *)0xC, v7);
      v48 = v22;
      if ( v22 )
      {
        UniDrvUI::BInitOrUpgradePrinterProperties(v22, v8);
        if ( (unsigned int)UniDrvUI::BFillCommonInfoPrinterData(v48, v23)
          && (unsigned int)UniDrvUI::BCombineCommonInfoOptionsArray(v48, v24) )
        {
          v26 = v48;
          if ( *(_DWORD *)(*((_QWORD *)v48 + 9) + 312LL) )
          {
            UniDrvUI::InitBidiAtPrinterInstall((UniDrvUI *)pPrinterName, (unsigned __int16 *)v48, v25);
            v26 = v48;
          }
          if ( (*(_DWORD *)(*((_QWORD *)v26 + 6) + 24LL) & 0x100000) != 0
            && !(unsigned int)BSetPrinterDataString(*((HANDLE *)v26 + 4)) )
          {
            DriverUi::DriverUiTelemetry::WriteDbgTraceWarning(
              "UniDrvUI::DrvPrinterEvent",
              L"Unable to initialize the form-tray database queue property.\n");
          }
          if ( !(unsigned int)bIsOnWin8AndAbove() )
            UniDrvUI::VNotifyDSOfUpdate(*((UniDrvUI **)v48 + 4), v8);
        }
        else
        {
          DriverUi::DriverUiTelemetry::WriteDbgTraceWarning(
            "UniDrvUI::DrvPrinterEvent",
            L"PRINTER_EVENT_INITIALIZE failed. Unable to load printer data.\n");
        }
      }
      break;
    case 4u:
LABEL_52:
      if ( !OpenPrinterW(pPrinterName, &phPrinter, 0) )
        goto LABEL_32;
      v48 = UniDrvUI::PLoadCommonInfo(0, pPrinterName, (unsigned __int16 *)1, v27);
      PrinterDataString = (wchar_t *)PtstrGetPrinterDataString(phPrinter, (LPWSTR)L"ExternalFontFile");
      v29 = PrinterDataString;
      if ( PrinterDataString )
      {
        v30 = 0;
        v31 = 0;
        if ( *PrinterDataString )
        {
          v32 = UniDrvUI::PGetFileDirectory(0, (unsigned __int16 *)v8);
          v30 = (wchar_t *)v32;
          if ( v32 )
          {
            v34 = UniDrvUI::PConcatFilename(v32, v29, v33);
            v31 = (WCHAR *)v34;
            if ( v34 )
              DeleteFileW(v34);
          }
        }
        LocalFree(v29);
        if ( v30 )
          LocalFree(v30);
        if ( v31 )
          LocalFree(v31);
      }
      break;
    case 5u:
      if ( !OpenPrinterW(pPrinterName, &phPrinter, 0) )
      {
LABEL_32:
        LastError = GetLastError();
        DriverUi::DriverUiTelemetry::WriteDbgTraceWarning(
          "UniDrvUI::DrvPrinterEvent",
          L"OpenPrinter '%ws' failed: %d\n",
          pPrinterName,
          LastError);
        phPrinter = 0;
        break;
      }
      UniDrvUI::_BPrepareToCopyCachedFile(phPrinter, (PSUI *)&v53, (LPWSTR)L"ExternalFontFile", v10);
      if ( (int)LoadLibraryFromSystemDirectory(L"spoolss.dll") >= 0
        && (ProcAddress = GetProcAddress(hModule, "RevertToPrinterSelf")) != 0
        && (v13 = GetProcAddress(hModule, "ImpersonatePrinterClient")) != 0 )
      {
        v14 = ProcAddress();
        v48 = UniDrvUI::PLoadCommonInfo((UniDrvUI *)phPrinter, pPrinterName, (unsigned __int16 *)0x8000, v15);
        UniDrvUI::_BCopyCachedFile(v16, (struct UniDrvUI::_COMMONINFO *)&v53, v17);
        PSUI::_VDisposeCachedFileInfo((PSUI *)&v53, v18);
        if ( v14 )
        {
          v47 = ((__int64 (__fastcall *)(__int64))v13)(v14);
          if ( !v47 )
          {
            v19 = GetLastError();
            DriverUi::DriverUiTelemetry::WriteDbgTraceWarning(
              "UniDrvUI::DrvPrinterEvent",
              L"PrinterEvent-ImpersonatePrinterClient failed: %d\n",
              v19);
          }
        }
        FreeLibrary(hModule);
      }
      else
      {
        v20 = GetLastError();
        DriverUi::DriverUiTelemetry::WriteDbgTraceWarning(
          "UniDrvUI::DrvPrinterEvent",
          L"Couldn't load spoolss.dll: %d\n",
          v20);
        PSUI::_VDisposeCachedFileInfo((PSUI *)&v53, v21);
      }
      break;
    case 8u:
      v55[0] = a4;
      if ( !SysStringLen(a4) )
      {
        v47 = 0;
        break;
      }
      *(_QWORD *)&v53 = &v48;
      *((_QWORD *)&v53 + 1) = &pPrinterName;
      *(_QWORD *)&v54 = v55;
      *((_QWORD *)&v54 + 1) = &v47;
      v57 = 0;
      if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_UniDrv_DelayLoad_CrashFix>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_UniDrv_DelayLoad_CrashFix>::GetImpl'::`2'::impl) )
      {
        if ( !`IppCommonUtil::IsIppCommonAvailable'::`2'::s_isLoadLibraryCheckDone )
        {
          Library = LoadLibraryExW(L"ippcommon.dll", 0, 0x800u);
          if ( Library )
          {
            `IppCommonUtil::IsIppCommonAvailable'::`2'::s_isIppCommonAvailable = 1;
            FreeLibrary(Library);
          }
          `IppCommonUtil::IsIppCommonAvailable'::`2'::s_isLoadLibraryCheckDone = 1;
        }
        if ( `IppCommonUtil::IsIppCommonAvailable'::`2'::s_isIppCommonAvailable
          && (int)IsModernPrinter(pPrinterName, 0, &v57) >= 0
          && v57 )
        {
          LODWORD(hModule) = 0;
          RevertToPrinterRAII::RevertToPrinterRAII((RevertToPrinterRAII *)hLibModule, (int *)&hModule);
          if ( (int)hModule >= 0 )
          {
LABEL_18:
            lambda_97e360d8fabff85a69a15679bfe5c655_::operator()(&v53);
            goto LABEL_24;
          }
LABEL_23:
          DriverUi::DriverUiTelemetry::WriteDbgTraceWarning(
            "UniDrvUI::DrvPrinterEvent",
            L"Failed to revert to printer self: %d\n",
            (unsigned __int16)hModule);
          v47 = 0;
LABEL_24:
          if ( v52 && hLibModule[1] )
            v52();
          if ( hLibModule[0] )
            FreeLibrary(hLibModule[0]);
          break;
        }
      }
      else if ( (int)IsModernPrinter(pPrinterName, 0, &v57) >= 0 && v57 )
      {
        LODWORD(hModule) = 0;
        RevertToPrinterRAII::RevertToPrinterRAII((RevertToPrinterRAII *)hLibModule, (int *)&hModule);
        if ( (int)hModule >= 0 )
          goto LABEL_18;
        goto LABEL_23;
      }
      lambda_97e360d8fabff85a69a15679bfe5c655_::operator()(&v53);
      break;
    default:
      v48 = UniDrvUI::PLoadCommonInfo(0, pPrinterName, (unsigned __int16 *)1, v7);
      break;
  }
  if ( v48 )
  {
    if ( v47 )
    {
      if ( *((_QWORD *)v48 + 14) )
        *((_DWORD *)v48 + 36) |= 0xCu;
      v35 = *((_QWORD *)v48 + 10);
      v36 = v35 + 24;
      v37 = *(_DWORD *)(v35 + 8);
      if ( v37 )
      {
        v38 = *(_QWORD *)IID_IPrintOemUI.Data4;
        v39 = *(_QWORD *)&IID_IPrintOemUI.Data1;
        v40 = *(_QWORD *)IID_IPrintOemUI2.Data4;
        v41 = *(_QWORD *)&IID_IPrintOemUI2.Data1;
        do
        {
          --v37;
          if ( *(_QWORD *)(v36 + 32) )
          {
            v42 = *(_QWORD *)(v36 + 72);
            if ( !v42 )
            {
              if ( (*(_BYTE *)(v36 + 101) & 1) != 0 )
              {
                v44 = *(unsigned int (__fastcall **)(LPWSTR, _QWORD, _QWORD, OLECHAR *))(v36 + 168);
              }
              else
              {
                v44 = (unsigned int (__fastcall *)(LPWSTR, _QWORD, _QWORD, OLECHAR *))PGetOemEntrypointAddress(
                                                                                        v36,
                                                                                        8,
                                                                                        v40,
                                                                                        v38);
                v38 = *(_QWORD *)IID_IPrintOemUI.Data4;
                v39 = *(_QWORD *)&IID_IPrintOemUI.Data1;
                v40 = *(_QWORD *)IID_IPrintOemUI2.Data4;
                v41 = *(_QWORD *)&IID_IPrintOemUI2.Data1;
              }
              if ( !v44 )
                goto LABEL_85;
              if ( !v44(pPrinterName, v6, a3, a4) )
              {
                v45 = GetLastError();
                DriverUi::DriverUiTelemetry::WriteDbgTraceWarning(
                  "UniDrvUI::DrvPrinterEvent",
                  L"OEMPrinterEvent failed for '%ws': %d\n",
                  *(_QWORD *)(v36 + 8),
                  v45);
                v47 = 0;
              }
LABEL_84:
              v41 = *(_QWORD *)&IID_IPrintOemUI2.Data1;
              v40 = *(_QWORD *)IID_IPrintOemUI2.Data4;
              v39 = *(_QWORD *)&IID_IPrintOemUI.Data1;
              v38 = *(_QWORD *)IID_IPrintOemUI.Data4;
              goto LABEL_85;
            }
            v8 = (struct UniDrvUI::_COMMONINFO *)pPrinterName;
            if ( *(_QWORD *)(v36 + 80) == v39 && *(_QWORD *)(v36 + 88) == v38
              || *(_QWORD *)(v36 + 80) == v41 && *(_QWORD *)(v36 + 88) == v40 )
            {
              v43 = (*(__int64 (__fastcall **)(__int64, LPWSTR, _QWORD, _QWORD, OLECHAR *))(*(_QWORD *)v42 + 96LL))(
                      v42,
                      pPrinterName,
                      v6,
                      a3,
                      a4);
              if ( v43 == -2147467263 )
                goto LABEL_84;
              v38 = *(_QWORD *)IID_IPrintOemUI.Data4;
              v39 = *(_QWORD *)&IID_IPrintOemUI.Data1;
              v40 = *(_QWORD *)IID_IPrintOemUI2.Data4;
              v41 = *(_QWORD *)&IID_IPrintOemUI2.Data1;
            }
            else
            {
              v43 = -2147467262;
            }
            v47 = v43 >= 0;
          }
LABEL_85:
          v36 += 216;
        }
        while ( v37 );
      }
      if ( v47 && (*((_DWORD *)v48 + 36) & 0x100) != 0 )
        v47 = BSavePrinterProperties(*((void **)v48 + 4), *(_DWORD *)(*((_QWORD *)v48 + 6) + 24LL) & 0x100000);
    }
    UniDrvUI::VFreeCommonInfo(v48, v8);
  }
  else
  {
    v47 = 0;
  }
  if ( phPrinter )
    ClosePrinter(phPrinter);
  return v47;
}

```

## disassembly

```asm
0x18010a2fc  mov     rax, rsp
0x18010a2ff  mov     [rax+8], rcx
0x18010a303  push    rbp
0x18010a304  push    rsi
0x18010a305  push    rdi
0x18010a306  push    r12
0x18010a308  push    r13
0x18010a30a  push    r14
0x18010a30c  push    r15
0x18010a30e  lea     rbp, [rax-5Fh]
0x18010a312  sub     rsp, 0A0h
0x18010a319  mov     [rbp+57h+var_40], 0FFFFFFFFFFFFFFFEh
0x18010a321  mov     [rax+18h], rbx
0x18010a325  mov     r14, r9
0x18010a328  mov     r12d, r8d
0x18010a32b  mov     r15d, edx
0x18010a32e  xor     r13d, r13d
0x18010a331  mov     [rbp+57h+hModule], r13
0x18010a335  mov     [rbp+57h+var_98], r13
0x18010a339  mov     [rbp+57h+phPrinter], r13
0x18010a33d  lea     edi, [r13+1]
0x18010a341  mov     [rbp+57h+var_A0], edi
0x18010a344  xorps   xmm0, xmm0
0x18010a347  movups  [rbp+57h+var_68], xmm0
0x18010a34b  movups  [rbp+57h+var_58], xmm0
0x18010a34f  mov     r8d, edx
0x18010a352  lea     rdx, aEnteringDrvpri; "Entering DrvPrinterEvent: %d ...\n"
0x18010a359  lea     rbx, aUnidrvuiDrvpri; "UniDrvUI::DrvPrinterEvent"
0x18010a360  mov     rcx, rbx; char *
0x18010a363  call    ?WriteDbgTraceInfo@DriverUiTelemetry@DriverUi@@SAXPEADPEAGZZ; DriverUi::DriverUiTelemetry::WriteDbgTraceInfo(char *,ushort *,...)
0x18010a368  mov     ecx, r15d
0x18010a36b  sub     ecx, 2
0x18010a36e  jz      loc_18010A74E
0x18010a374  sub     ecx, edi
0x18010a376  jz      loc_18010A67C
0x18010a37c  sub     ecx, edi
0x18010a37e  jz      loc_18010A74E
0x18010a384  sub     ecx, edi
0x18010a386  jz      loc_18010A531
0x18010a38c  cmp     ecx, 3
0x18010a38f  jz      short loc_18010A3A8
0x18010a391  mov     r8d, edi; unsigned __int16 *
0x18010a394  mov     rdx, [rbp+57h+pPrinterName]; void *
0x18010a398  xor     ecx, ecx; this
0x18010a39a  call    ?PLoadCommonInfo@UniDrvUI@@YAPEAU_COMMONINFO@1@PEAXPEAGK@Z; UniDrvUI::PLoadCommonInfo(void *,ushort *,ulong)
0x18010a39f  mov     [rbp+57h+var_98], rax
0x18010a3a3  jmp     loc_18010A7F0
0x18010a3a8  mov     [rbp+57h+var_48], r14
0x18010a3ac  mov     rcx, r14; pbstr
0x18010a3af  call    cs:__imp_SysStringLen
0x18010a3b5  test    eax, eax
0x18010a3b7  jnz     short loc_18010A3C2
0x18010a3b9  mov     [rbp+57h+var_A0], r13d
0x18010a3bd  jmp     loc_18010A7F0
0x18010a3c2  lea     rax, [rbp+57h+var_98]
0x18010a3c6  mov     qword ptr [rbp+57h+var_68], rax
0x18010a3ca  lea     rax, [rbp+57h+pPrinterName]
0x18010a3ce  mov     qword ptr [rbp+57h+var_68+8], rax
0x18010a3d2  lea     rax, [rbp+57h+var_48]
0x18010a3d6  mov     qword ptr [rbp+57h+var_58], rax
0x18010a3da  lea     rax, [rbp+57h+var_A0]
0x18010a3de  mov     qword ptr [rbp+57h+var_58+8], rax
0x18010a3e2  mov     [rbp+57h+arg_8], r13b
0x18010a3e6  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_UniDrv_DelayLoad_CrashFix@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_UniDrv_DelayLoad_CrashFix@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_UniDrv_DelayLoad_CrashFix> `wil::Feature<__WilFeatureTraits_Feature_UniDrv_DelayLoad_CrashFix>::GetImpl(void)'::`2'::impl
0x18010a3ed  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_UniDrv_DelayLoad_CrashFix@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_UniDrv_DelayLoad_CrashFix>::__private_IsEnabled(void)
0x18010a3f2  test    al, al
0x18010a3f4  jz      loc_18010A4A1
0x18010a3fa  cmp     cs:?s_isLoadLibraryCheckDone@?1??IsIppCommonAvailable@IppCommonUtil@@YA_NXZ@4_NA, r13b; bool `IppCommonUtil::IsIppCommonAvailable(void)'::`2'::s_isLoadLibraryCheckDone
0x18010a401  jnz     short loc_18010A434
0x18010a403  xor     edx, edx; hFile
0x18010a405  mov     r8d, 800h; dwFlags
0x18010a40b  lea     rcx, aIppcommonDll_0; "ippcommon.dll"
0x18010a412  call    cs:__imp_LoadLibraryExW
0x18010a418  test    rax, rax
0x18010a41b  jz      short loc_18010A42D
0x18010a41d  mov     cs:?s_isIppCommonAvailable@?1??IsIppCommonAvailable@IppCommonUtil@@YA_NXZ@4_NA, dil; bool `IppCommonUtil::IsIppCommonAvailable(void)'::`2'::s_isIppCommonAvailable
0x18010a424  mov     rcx, rax; hLibModule
0x18010a427  call    cs:__imp_FreeLibrary
0x18010a42d  mov     cs:?s_isLoadLibraryCheckDone@?1??IsIppCommonAvailable@IppCommonUtil@@YA_NXZ@4_NA, dil; bool `IppCommonUtil::IsIppCommonAvailable(void)'::`2'::s_isLoadLibraryCheckDone
0x18010a434  cmp     cs:?s_isIppCommonAvailable@?1??IsIppCommonAvailable@IppCommonUtil@@YA_NXZ@4_NA, r13b; bool `IppCommonUtil::IsIppCommonAvailable(void)'::`2'::s_isIppCommonAvailable
0x18010a43b  jz      loc_18010A523
0x18010a441  lea     r8, [rbp+57h+arg_8]
0x18010a445  xor     edx, edx
0x18010a447  mov     rcx, [rbp+57h+pPrinterName]
0x18010a44b  call    cs:__imp_IsModernPrinter
0x18010a451  test    eax, eax
0x18010a453  js      loc_18010A523
0x18010a459  cmp     [rbp+57h+arg_8], r13b
0x18010a45d  jz      loc_18010A523
0x18010a463  mov     dword ptr [rbp+57h+hModule], r13d
0x18010a467  lea     rdx, [rbp+57h+hModule]; int *
0x18010a46b  lea     rcx, [rbp+57h+hLibModule]; this
0x18010a46f  call    ??0RevertToPrinterRAII@@QEAA@PEAJ@Z; RevertToPrinterRAII::RevertToPrinterRAII(long *)
0x18010a474  nop
0x18010a475  mov     eax, dword ptr [rbp+57h+hModule]
0x18010a478  test    eax, eax
0x18010a47a  js      short loc_18010A488
0x18010a47c  lea     rcx, [rbp+57h+var_68]
0x18010a480  call    _lambda_97e360d8fabff85a69a15679bfe5c655___operator__
0x18010a485  nop
0x18010a486  jmp     short loc_18010A4F7
0x18010a488  movzx   r8d, ax
0x18010a48c  lea     rdx, aFailedToRevert; "Failed to revert to printer self: %d\n"
0x18010a493  mov     rcx, rbx; char *
0x18010a496  call    ?WriteDbgTraceWarning@DriverUiTelemetry@DriverUi@@SAXPEADPEAGZZ; DriverUi::DriverUiTelemetry::WriteDbgTraceWarning(char *,ushort *,...)
0x18010a49b  mov     [rbp+57h+var_A0], r13d
0x18010a49f  jmp     short loc_18010A4F7
0x18010a4a1  lea     r8, [rbp+57h+arg_8]
0x18010a4a5  xor     edx, edx
0x18010a4a7  mov     rcx, [rbp+57h+pPrinterName]
0x18010a4ab  call    cs:__imp_IsModernPrinter
0x18010a4b1  test    eax, eax
0x18010a4b3  js      short loc_18010A523
0x18010a4b5  cmp     [rbp+57h+arg_8], r13b
0x18010a4b9  jz      short loc_18010A523
0x18010a4bb  mov     dword ptr [rbp+57h+hModule], r13d
0x18010a4bf  lea     rdx, [rbp+57h+hModule]; int *
0x18010a4c3  lea     rcx, [rbp+57h+hLibModule]; this
0x18010a4c7  call    ??0RevertToPrinterRAII@@QEAA@PEAJ@Z; RevertToPrinterRAII::RevertToPrinterRAII(long *)
0x18010a4cc  nop
0x18010a4cd  mov     eax, dword ptr [rbp+57h+hModule]
0x18010a4d0  test    eax, eax
0x18010a4d2  js      short loc_18010A4E0
0x18010a4d4  lea     rcx, [rbp+57h+var_68]
0x18010a4d8  call    _lambda_97e360d8fabff85a69a15679bfe5c655___operator__
0x18010a4dd  nop
0x18010a4de  jmp     short loc_18010A4F7
0x18010a4e0  movzx   r8d, ax
0x18010a4e4  lea     rdx, aFailedToRevert; "Failed to revert to printer self: %d\n"
0x18010a4eb  mov     rcx, rbx; char *
0x18010a4ee  call    ?WriteDbgTraceWarning@DriverUiTelemetry@DriverUi@@SAXPEADPEAGZZ; DriverUi::DriverUiTelemetry::WriteDbgTraceWarning(char *,ushort *,...)
0x18010a4f3  mov     [rbp+57h+var_A0], r13d
0x18010a4f7  mov     rax, [rbp+57h+var_70]
0x18010a4fb  test    rax, rax
0x18010a4fe  jz      short loc_18010A50E
0x18010a500  mov     rcx, [rbp+57h+var_78]
0x18010a504  test    rcx, rcx
0x18010a507  jz      short loc_18010A50E
0x18010a509  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18010a50e  mov     rcx, [rbp+57h+hLibModule]; hLibModule
0x18010a512  test    rcx, rcx
0x18010a515  jz      short loc_18010A51E
0x18010a517  call    cs:__imp_FreeLibrary
0x18010a51d  nop
0x18010a51e  jmp     loc_18010A7F0
0x18010a523  lea     rcx, [rbp+57h+var_68]
0x18010a527  call    _lambda_97e360d8fabff85a69a15679bfe5c655___operator__
0x18010a52c  jmp     loc_18010A7F0
0x18010a531  xor     r8d, r8d; pDefault
0x18010a534  lea     rdx, [rbp+57h+phPrinter]; phPrinter
0x18010a538  mov     rcx, [rbp+57h+pPrinterName]; pPrinterName
0x18010a53c  call    cs:__imp_OpenPrinterW
0x18010a542  test    eax, eax
0x18010a544  jnz     short loc_18010A56B
0x18010a546  call    cs:__imp_GetLastError
0x18010a54c  mov     r9d, eax
0x18010a54f  mov     r8, [rbp+57h+pPrinterName]
0x18010a553  lea     rdx, aOpenprinterWsF; "OpenPrinter '%ws' failed: %d\n"
0x18010a55a  mov     rcx, rbx; char *
0x18010a55d  call    ?WriteDbgTraceWarning@DriverUiTelemetry@DriverUi@@SAXPEADPEAGZZ; DriverUi::DriverUiTelemetry::WriteDbgTraceWarning(char *,ushort *,...)
0x18010a562  mov     [rbp+57h+phPrinter], r13
0x18010a566  jmp     loc_18010A7F0
0x18010a56b  lea     r8, aExternalfontfi; "ExternalFontFile"
0x18010a572  lea     rdx, [rbp+57h+var_68]; this
0x18010a576  mov     rcx, [rbp+57h+phPrinter]; hPrinter
0x18010a57a  call    ?_BPrepareToCopyCachedFile@UniDrvUI@@YAHPEAXPEAU_CACHEDFILE@1@PEAG@Z; UniDrvUI::_BPrepareToCopyCachedFile(void *,UniDrvUI::_CACHEDFILE *,ushort *)
0x18010a57f  lea     rdx, [rbp+57h+hModule]
0x18010a583  lea     rcx, aSpoolssDll; "spoolss.dll"
0x18010a58a  call    LoadLibraryFromSystemDirectory
0x18010a58f  mov     rbx, [rbp+57h+hModule]
0x18010a593  test    eax, eax
0x18010a595  js      loc_18010A644
0x18010a59b  lea     rdx, aReverttoprinte; "RevertToPrinterSelf"
0x18010a5a2  mov     rcx, rbx; hModule
0x18010a5a5  call    cs:__imp_GetProcAddress
0x18010a5ab  mov     rsi, rax
0x18010a5ae  test    rax, rax
0x18010a5b1  jz      loc_18010A644
0x18010a5b7  lea     rdx, aImpersonatepri; "ImpersonatePrinterClient"
0x18010a5be  mov     rcx, rbx; hModule
0x18010a5c1  call    cs:__imp_GetProcAddress
0x18010a5c7  mov     rdi, rax
0x18010a5ca  test    rax, rax
0x18010a5cd  jz      short loc_18010A644
0x18010a5cf  mov     rax, rsi
0x18010a5d2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18010a5d7  mov     rsi, rax
0x18010a5da  mov     r8d, 8000h; unsigned __int16 *
0x18010a5e0  mov     rdx, [rbp+57h+pPrinterName]; void *
0x18010a5e4  mov     rcx, [rbp+57h+phPrinter]; this
0x18010a5e8  call    ?PLoadCommonInfo@UniDrvUI@@YAPEAU_COMMONINFO@1@PEAXPEAGK@Z; UniDrvUI::PLoadCommonInfo(void *,ushort *,ulong)
0x18010a5ed  mov     [rbp+57h+var_98], rax
0x18010a5f1  lea     rdx, [rbp+57h+var_68]; struct UniDrvUI::_COMMONINFO *
0x18010a5f5  call    ?_BCopyCachedFile@UniDrvUI@@YAHPEAU_COMMONINFO@1@PEAU_CACHEDFILE@1@@Z; UniDrvUI::_BCopyCachedFile(UniDrvUI::_COMMONINFO *,UniDrvUI::_CACHEDFILE *)
0x18010a5fa  lea     rcx, [rbp+57h+var_68]; this
0x18010a5fe  call    ?_VDisposeCachedFileInfo@PSUI@@YAXPEAU_CACHEDFILE@1@@Z; PSUI::_VDisposeCachedFileInfo(PSUI::_CACHEDFILE *)
0x18010a603  test    rsi, rsi
0x18010a606  jz      short loc_18010A636
0x18010a608  mov     rcx, rsi
0x18010a60b  mov     rax, rdi
0x18010a60e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18010a613  mov     [rbp+57h+var_A0], eax
0x18010a616  test    eax, eax
0x18010a618  jnz     short loc_18010A636
0x18010a61a  call    cs:__imp_GetLastError
0x18010a620  mov     r8d, eax
0x18010a623  lea     rdx, aPrintereventIm; "PrinterEvent-ImpersonatePrinterClient f"...
0x18010a62a  lea     rcx, aUnidrvuiDrvpri; "UniDrvUI::DrvPrinterEvent"
0x18010a631  call    ?WriteDbgTraceWarning@DriverUiTelemetry@DriverUi@@SAXPEADPEAGZZ; DriverUi::DriverUiTelemetry::WriteDbgTraceWarning(char *,ushort *,...)
0x18010a636  mov     rcx, rbx; hLibModule
0x18010a639  call    cs:__imp_FreeLibrary
0x18010a63f  jmp     loc_18010A7F0
0x18010a644  call    cs:__imp_GetLastError
0x18010a64a  mov     r8d, eax
0x18010a64d  lea     rdx, aCouldnTLoadSpo; "Couldn't load spoolss.dll: %d\n"
0x18010a654  lea     rcx, aUnidrvuiDrvpri; "UniDrvUI::DrvPrinterEvent"
0x18010a65b  call    ?WriteDbgTraceWarning@DriverUiTelemetry@DriverUi@@SAXPEADPEAGZZ; DriverUi::DriverUiTelemetry::WriteDbgTraceWarning(char *,ushort *,...)
0x18010a660  test    rbx, rbx
0x18010a663  jz      short loc_18010A66E
0x18010a665  mov     rcx, rbx; hLibModule
0x18010a668  call    cs:__imp_FreeLibrary
0x18010a66e  lea     rcx, [rbp+57h+var_68]; this
0x18010a672  call    ?_VDisposeCachedFileInfo@PSUI@@YAXPEAU_CACHEDFILE@1@@Z; PSUI::_VDisposeCachedFileInfo(PSUI::_CACHEDFILE *)
0x18010a677  jmp     loc_18010A7F0
0x18010a67c  mov     r8d, 0Ch; unsigned __int16 *
0x18010a682  mov     rdx, [rbp+57h+pPrinterName]; void *
0x18010a686  xor     ecx, ecx; this
0x18010a688  call    ?PLoadCommonInfo@UniDrvUI@@YAPEAU_COMMONINFO@1@PEAXPEAGK@Z; UniDrvUI::PLoadCommonInfo(void *,ushort *,ulong)
0x18010a68d  mov     rcx, rax; this
0x18010a690  mov     [rbp+57h+var_98], rax
0x18010a694  test    rax, rax
0x18010a697  jz      loc_18010A7F0
0x18010a69d  call    ?BInitOrUpgradePrinterProperties@UniDrvUI@@YAHPEAU_COMMONINFO@1@@Z; UniDrvUI::BInitOrUpgradePrinterProperties(UniDrvUI::_COMMONINFO *)
0x18010a6a2  mov     rcx, [rbp+57h+var_98]; this
0x18010a6a6  call    ?BFillCommonInfoPrinterData@UniDrvUI@@YAHPEAU_COMMONINFO@1@@Z; UniDrvUI::BFillCommonInfoPrinterData(UniDrvUI::_COMMONINFO *)
0x18010a6ab  test    eax, eax
0x18010a6ad  jz      loc_18010A73A
0x18010a6b3  mov     rcx, [rbp+57h+var_98]; this
0x18010a6b7  call    ?BCombineCommonInfoOptionsArray@UniDrvUI@@YAHPEAU_COMMONINFO@1@@Z; UniDrvUI::BCombineCommonInfoOptionsArray(UniDrvUI::_COMMONINFO *)
0x18010a6bc  test    eax, eax
0x18010a6be  jz      short loc_18010A73A
0x18010a6c0  mov     rcx, [rbp+57h+var_98]
0x18010a6c4  mov     rax, [rcx+48h]
0x18010a6c8  cmp     [rax+138h], r13d
0x18010a6cf  jz      short loc_18010A6E1
0x18010a6d1  mov     rdx, rcx; unsigned __int16 *
0x18010a6d4  mov     rcx, [rbp+57h+pPrinterName]; this
0x18010a6d8  call    ?InitBidiAtPrinterInstall@UniDrvUI@@YAHPEAGPEAU_COMMONINFO@1@@Z; UniDrvUI::InitBidiAtPrinterInstall(ushort *,UniDrvUI::_COMMONINFO *)
0x18010a6dd  mov     rcx, [rbp+57h+var_98]
0x18010a6e1  mov     rax, [rcx+30h]
0x18010a6e5  test    dword ptr [rax+18h], 100000h
0x18010a6ec  jz      short loc_18010A71B
0x18010a6ee  mov     r9d, edi
0x18010a6f1  lea     r8, Filename
0x18010a6f8  lea     rdx, aTrayformqueuep; "TrayFormQueueProp"
0x18010a6ff  mov     rcx, [rcx+20h]; hPrinter
0x18010a703  call    BSetPrinterDataString
0x18010a708  test    eax, eax
0x18010a70a  jnz     short loc_18010A71B
0x18010a70c  lea     rdx, aUnableToInitia; "Unable to initialize the form-tray data"...
0x18010a713  mov     rcx, rbx; char *
0x18010a716  call    ?WriteDbgTraceWarning@DriverUiTelemetry@DriverUi@@SAXPEADPEAGZZ; DriverUi::DriverUiTelemetry::WriteDbgTraceWarning(char *,ushort *,...)
0x18010a71b  call    bIsOnWin8AndAbove
0x18010a720  test    eax, eax
0x18010a722  jnz     loc_18010A7F0
0x18010a728  mov     rcx, [rbp+57h+var_98]
0x18010a72c  mov     rcx, [rcx+20h]; this
0x18010a730  call    ?VNotifyDSOfUpdate@UniDrvUI@@YAXPEAX@Z; UniDrvUI::VNotifyDSOfUpdate(void *)
0x18010a735  jmp     loc_18010A7F0
0x18010a73a  lea     rdx, aPrinterEventIn; "PRINTER_EVENT_INITIALIZE failed. Unable"...
0x18010a741  mov     rcx, rbx; char *
0x18010a744  call    ?WriteDbgTraceWarning@DriverUiTelemetry@DriverUi@@SAXPEADPEAGZZ; DriverUi::DriverUiTelemetry::WriteDbgTraceWarning(char *,ushort *,...)
0x18010a749  jmp     loc_18010A7F0
0x18010a74e  xor     r8d, r8d; pDefault
0x18010a751  lea     rdx, [rbp+57h+phPrinter]; phPrinter
0x18010a755  mov     rcx, [rbp+57h+pPrinterName]; pPrinterName
0x18010a759  call    cs:__imp_OpenPrinterW
0x18010a75f  test    eax, eax
0x18010a761  jz      loc_18010A546
0x18010a767  mov     r8d, edi; unsigned __int16 *
0x18010a76a  mov     rdx, [rbp+57h+pPrinterName]; void *
0x18010a76e  xor     ecx, ecx; this
0x18010a770  call    ?PLoadCommonInfo@UniDrvUI@@YAPEAU_COMMONINFO@1@PEAXPEAGK@Z; UniDrvUI::PLoadCommonInfo(void *,ushort *,ulong)
0x18010a775  mov     [rbp+57h+var_98], rax
0x18010a779  xor     r8d, r8d
0x18010a77c  lea     rdx, aExternalfontfi; "ExternalFontFile"
0x18010a783  mov     rcx, [rbp+57h+phPrinter]; hPrinter
0x18010a787  call    PtstrGetPrinterDataString
0x18010a78c  mov     rsi, rax
0x18010a78f  test    rax, rax
0x18010a792  jz      short loc_18010A7F0
0x18010a794  mov     rdi, r13
0x18010a797  mov     rbx, r13
0x18010a79a  cmp     [rax], r13w
0x18010a79e  jz      short loc_18010A7CB
0x18010a7a0  xor     ecx, ecx; pName
0x18010a7a2  call    ?PGetFileDirectory@UniDrvUI@@YAPEAGPEAG@Z; UniDrvUI::PGetFileDirectory(ushort *)
0x18010a7a7  mov     rdi, rax
0x18010a7aa  test    rax, rax
0x18010a7ad  jz      short loc_18010A7CB
  ... truncated ...
```
