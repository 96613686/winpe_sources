# PSUI::DrvPrinterEvent(ushort *,int,ulong,__int64)

- ea: `0x180131dcc`
- end: `0x1801323ea`
- name: `?DrvPrinterEvent@PSUI@@YAHPEAGHK_J@Z`
- size: `1566`
- prototype: `int(PSUI *__hidden this, unsigned __int16 *, int, unsigned int, __int64)`
- caller_count: `1`
- callee_count: `21`
- tags: `authz_impersonation, loader_planting, installer_update, broker_com_uri`

## callers

- `0x18002f970`

## callees

- `0x1800060ec`
- `0x180102674`
- `0x18010427c`
- `0x18010b36c`
- `0x18010b3dc`
- `0x1801307b0`
- `0x18013154c`
- `0x180131dcc`
- `0x1801324d0`
- `0x18013520c`
- `0x180135680`
- `0x180136374`
- `0x180137ac0`
- `0x180137cbc`
- `0x1801464b0`
- `0x180149448`
- `0x18014a5f4`
- `0x18014a968`
- `0x18014e910`
- `0x180150ce8`
- `0x1801c3010`

## import_xrefs

- `KERNEL32!GetProcAddress` at `0x18013205b`
- `KERNEL32!GetProcAddress` at `0x180132077`
- `KERNEL32!GetProcAddress` at `0x18013205b`
- `KERNEL32!GetProcAddress` at `0x180132077`
- `KERNEL32!FreeLibrary` at `0x180131edd`
- `KERNEL32!FreeLibrary` at `0x180131fcd`
- `KERNEL32!FreeLibrary` at `0x1801320ef`
- `KERNEL32!FreeLibrary` at `0x18013211e`
- `KERNEL32!FreeLibrary` at `0x180131edd`
- `KERNEL32!FreeLibrary` at `0x180131fcd`
- `KERNEL32!FreeLibrary` at `0x1801320ef`
- `KERNEL32!FreeLibrary` at `0x18013211e`
- `KERNEL32!GetLastError` at `0x180131ffc`
- `KERNEL32!GetLastError` at `0x1801320d0`
- `KERNEL32!GetLastError` at `0x1801320fa`
- `KERNEL32!GetLastError` at `0x180132325`
- `KERNEL32!GetLastError` at `0x180131ffc`
- `KERNEL32!GetLastError` at `0x1801320d0`
- `KERNEL32!GetLastError` at `0x1801320fa`
- `KERNEL32!GetLastError` at `0x180132325`
- `KERNEL32!LoadLibraryExW` at `0x180131ec8`
- `KERNEL32!LoadLibraryExW` at `0x180131ec8`
- `OLEAUT32!__imp_SysStringLen` at `0x180131e65`
- `OLEAUT32!__imp_SysStringLen` at `0x180131e65`
- `WINSPOOL!ClosePrinter` at `0x1801323c6`
- `WINSPOOL!ClosePrinter` at `0x1801323c6`
- `WINSPOOL!OpenPrinterW` at `0x180131ff2`
- `WINSPOOL!OpenPrinterW` at `0x180131ff2`
- `IppCommon!IsModernPrinter` at `0x180131f01`
- `IppCommon!IsModernPrinter` at `0x180131f61`
- `IppCommon!IsModernPrinter` at `0x180131f01`
- `IppCommon!IsModernPrinter` at `0x180131f61`

## string_xrefs

- `0x180132039`: `spoolss.dll`
- `0x18013206d`: `ImpersonatePrinterClient`
- `0x180131ec1`: `ippcommon.dll`
- `0x180132009`: `OpenPrinter '%ws' failed: %d\n`
- `0x1801320d9`: `PrinterEvent-ImpersonatePrinterClient failed: %d\n`
- `0x180132103`: `Couldn't load spoolss.dll: %d\n`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall PSUI::DrvPrinterEvent(WCHAR *this, unsigned __int16 *a2, unsigned int a3, OLECHAR *a4)
{
  unsigned int v6; // r14d
  struct PSUI::_COMMONINFO *v7; // rdx
  HMODULE Library; // rax
  DWORD v9; // eax
  __int64 (*ProcAddress)(void); // rsi
  FARPROC v11; // rdi
  __int64 v12; // rsi
  PSUI *v13; // rcx
  struct PSUI::_CACHEDFILE *v14; // r8
  struct PSUI::_CACHEDFILE *v15; // rdx
  DWORD LastError; // eax
  DWORD v17; // eax
  struct PSUI::_CACHEDFILE *v18; // rdx
  PSUI *v19; // rcx
  struct PSUI::_COMMONINFO *v20; // rdx
  struct PSUI::_COMMONINFO *v21; // rdx
  struct PSUI::_COMMONINFO *v22; // r8
  PSUI *v23; // rcx
  __int64 v24; // rcx
  __int64 v25; // rbx
  int v26; // edi
  __int64 v27; // r9
  __int64 v28; // r10
  __int64 v29; // r8
  __int64 v30; // r11
  __int64 v31; // rcx
  int v32; // eax
  unsigned int (__fastcall *v33)(LPWSTR, _QWORD, _QWORD, OLECHAR *); // rax
  DWORD v34; // eax
  unsigned int v36; // [rsp+38h] [rbp-49h] BYREF
  PSUI *v37; // [rsp+40h] [rbp-41h] BYREF
  HMODULE hModule; // [rsp+48h] [rbp-39h] BYREF
  HANDLE phPrinter; // [rsp+50h] [rbp-31h] BYREF
  HMODULE hLibModule[2]; // [rsp+58h] [rbp-29h] BYREF
  void (*v41)(void); // [rsp+68h] [rbp-19h]
  __int64 v42; // [rsp+70h] [rbp-11h] BYREF
  __int128 v43; // [rsp+78h] [rbp-9h]
  unsigned int *v44; // [rsp+88h] [rbp+7h]
  _QWORD v45[9]; // [rsp+90h] [rbp+Fh] BYREF
  LPWSTR pPrinterName; // [rsp+E8h] [rbp+67h] BYREF
  char v47; // [rsp+F0h] [rbp+6Fh] BYREF

  pPrinterName = this;
  v45[1] = -2;
  v6 = (unsigned int)a2;
  hModule = 0;
  v37 = 0;
  phPrinter = 0;
  v36 = 1;
  DriverUi::DriverUiTelemetry::WriteDbgTraceInfo(
    "PSUI::DrvPrinterEvent",
    L"Entering DrvPrinterEvent: %d ...\n",
    (unsigned int)a2);
  switch ( v6 )
  {
    case 3u:
      v19 = PSUI::PLoadCommonInfo(0, pPrinterName, (unsigned __int16 *)0xC);
      v37 = v19;
      if ( v19 )
      {
        PSUI::BInitOrUpgradePrinterProperties(v19, v7);
        if ( (unsigned int)PSUI::BFillCommonInfoPrinterData(v37, v20)
          && (unsigned int)PSUI::BCombineCommonInfoOptionsArray(v37, v21) )
        {
          v23 = v37;
          if ( *(_DWORD *)(*((_QWORD *)v37 + 9) + 312LL) )
          {
            PSUI::InitBidiAtPrinterInstall((PSUI *)pPrinterName, (unsigned __int16 *)v37, v22);
            v23 = v37;
          }
          if ( (*(_DWORD *)(*((_QWORD *)v23 + 6) + 24LL) & 0x100000) != 0
            && !(unsigned int)BSetPrinterDataString(*((HANDLE *)v23 + 4)) )
          {
            DriverUi::DriverUiTelemetry::WriteDbgTraceWarning(
              "PSUI::DrvPrinterEvent",
              L"Unable to initialize the form-tray database queue property.\n");
          }
          if ( !(unsigned int)bIsOnWin8AndAbove() )
            PSUI::VNotifyDSOfUpdate(*((PSUI **)v37 + 4), v7);
        }
        else
        {
          DriverUi::DriverUiTelemetry::WriteDbgTraceWarning(
            "PSUI::DrvPrinterEvent",
            L"PRINTER_EVENT_INITIALIZE failed. Unable to load printer data.\n");
        }
      }
      break;
    case 5u:
      if ( OpenPrinterW(pPrinterName, &phPrinter, 0) )
      {
        v43 = 0;
        v44 = 0;
        v42 = -1;
        if ( (int)LoadLibraryFromSystemDirectory(L"spoolss.dll") >= 0
          && (ProcAddress = GetProcAddress(hModule, "RevertToPrinterSelf")) != 0
          && (v11 = GetProcAddress(hModule, "ImpersonatePrinterClient")) != 0 )
        {
          v12 = ProcAddress();
          v37 = PSUI::PLoadCommonInfo((PSUI *)phPrinter, pPrinterName, (unsigned __int16 *)0x8000);
          PSUI::_BCopyCachedFile(v13, (struct PSUI::_COMMONINFO *)&v42, v14);
          PSUI::_VDisposeCachedFileInfo((PSUI *)&v42, v15);
          if ( v12 )
          {
            v36 = ((__int64 (__fastcall *)(__int64))v11)(v12);
            if ( !v36 )
            {
              LastError = GetLastError();
              DriverUi::DriverUiTelemetry::WriteDbgTraceWarning(
                "PSUI::DrvPrinterEvent",
                L"PrinterEvent-ImpersonatePrinterClient failed: %d\n",
                LastError);
            }
          }
          FreeLibrary(hModule);
        }
        else
        {
          v17 = GetLastError();
          DriverUi::DriverUiTelemetry::WriteDbgTraceWarning(
            "PSUI::DrvPrinterEvent",
            L"Couldn't load spoolss.dll: %d\n",
            v17);
          PSUI::_VDisposeCachedFileInfo((PSUI *)&v42, v18);
        }
      }
      else
      {
        v9 = GetLastError();
        DriverUi::DriverUiTelemetry::WriteDbgTraceWarning(
          "PSUI::DrvPrinterEvent",
          L"OpenPrinter '%ws' failed: %d\n",
          pPrinterName,
          v9);
        phPrinter = 0;
      }
      break;
    case 8u:
      v45[0] = a4;
      if ( !SysStringLen(a4) )
      {
        v36 = 0;
        break;
      }
      v42 = (__int64)&v37;
      *(_QWORD *)&v43 = &pPrinterName;
      *((_QWORD *)&v43 + 1) = v45;
      v44 = &v36;
      v47 = 0;
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
          && (int)IsModernPrinter(pPrinterName, 0, &v47) >= 0
          && v47 )
        {
          LODWORD(hModule) = 0;
          RevertToPrinterRAII::RevertToPrinterRAII((RevertToPrinterRAII *)hLibModule, (int *)&hModule);
          if ( (int)hModule >= 0 )
          {
LABEL_16:
            lambda_7709aa7672fa7c7d1651f7628bf4b04b_::operator()(&v42);
            goto LABEL_22;
          }
LABEL_21:
          DriverUi::DriverUiTelemetry::WriteDbgTraceWarning(
            "PSUI::DrvPrinterEvent",
            L"Failed to revert to printer self: %d\n",
            (unsigned __int16)hModule);
          v36 = 0;
LABEL_22:
          if ( v41 && hLibModule[1] )
            v41();
          if ( hLibModule[0] )
            FreeLibrary(hLibModule[0]);
          break;
        }
      }
      else if ( (int)IsModernPrinter(pPrinterName, 0, &v47) >= 0 && v47 )
      {
        LODWORD(hModule) = 0;
        RevertToPrinterRAII::RevertToPrinterRAII((RevertToPrinterRAII *)hLibModule, (int *)&hModule);
        if ( (int)hModule >= 0 )
          goto LABEL_16;
        goto LABEL_21;
      }
      lambda_7709aa7672fa7c7d1651f7628bf4b04b_::operator()(&v42);
      break;
    default:
      v37 = PSUI::PLoadCommonInfo(0, pPrinterName, (unsigned __int16 *)1);
      break;
  }
  if ( v37 )
  {
    if ( v36 )
    {
      if ( *((_QWORD *)v37 + 14) )
        *((_DWORD *)v37 + 36) |= 0xCu;
      v24 = *((_QWORD *)v37 + 10);
      v25 = v24 + 24;
      v26 = *(_DWORD *)(v24 + 8);
      if ( v26 )
      {
        v27 = *(_QWORD *)IID_IPrintOemUI.Data4;
        v28 = *(_QWORD *)&IID_IPrintOemUI.Data1;
        v29 = *(_QWORD *)IID_IPrintOemUI2.Data4;
        v30 = *(_QWORD *)&IID_IPrintOemUI2.Data1;
        do
        {
          --v26;
          if ( *(_QWORD *)(v25 + 32) )
          {
            v31 = *(_QWORD *)(v25 + 72);
            if ( !v31 )
            {
              if ( (*(_BYTE *)(v25 + 101) & 1) != 0 )
              {
                v33 = *(unsigned int (__fastcall **)(LPWSTR, _QWORD, _QWORD, OLECHAR *))(v25 + 168);
              }
              else
              {
                v33 = (unsigned int (__fastcall *)(LPWSTR, _QWORD, _QWORD, OLECHAR *))PGetOemEntrypointAddress(
                                                                                        v25,
                                                                                        8,
                                                                                        v29,
                                                                                        v27);
                v27 = *(_QWORD *)IID_IPrintOemUI.Data4;
                v28 = *(_QWORD *)&IID_IPrintOemUI.Data1;
                v29 = *(_QWORD *)IID_IPrintOemUI2.Data4;
                v30 = *(_QWORD *)&IID_IPrintOemUI2.Data1;
              }
              if ( !v33 )
                goto LABEL_73;
              if ( !v33(pPrinterName, v6, a3, a4) )
              {
                v34 = GetLastError();
                DriverUi::DriverUiTelemetry::WriteDbgTraceWarning(
                  "PSUI::DrvPrinterEvent",
                  L"OEMPrinterEvent failed for '%ws': %d\n",
                  *(_QWORD *)(v25 + 8),
                  v34);
                v36 = 0;
              }
LABEL_72:
              v30 = *(_QWORD *)&IID_IPrintOemUI2.Data1;
              v29 = *(_QWORD *)IID_IPrintOemUI2.Data4;
              v28 = *(_QWORD *)&IID_IPrintOemUI.Data1;
              v27 = *(_QWORD *)IID_IPrintOemUI.Data4;
              goto LABEL_73;
            }
            v7 = (struct PSUI::_COMMONINFO *)pPrinterName;
            if ( *(_QWORD *)(v25 + 80) == v28 && *(_QWORD *)(v25 + 88) == v27
              || *(_QWORD *)(v25 + 80) == v30 && *(_QWORD *)(v25 + 88) == v29 )
            {
              v32 = (*(__int64 (__fastcall **)(__int64, LPWSTR, _QWORD, _QWORD, OLECHAR *))(*(_QWORD *)v31 + 96LL))(
                      v31,
                      pPrinterName,
                      v6,
                      a3,
                      a4);
              if ( v32 == -2147467263 )
                goto LABEL_72;
              v27 = *(_QWORD *)IID_IPrintOemUI.Data4;
              v28 = *(_QWORD *)&IID_IPrintOemUI.Data1;
              v29 = *(_QWORD *)IID_IPrintOemUI2.Data4;
              v30 = *(_QWORD *)&IID_IPrintOemUI2.Data1;
            }
            else
            {
              v32 = -2147467262;
            }
            v36 = v32 >= 0;
          }
LABEL_73:
          v25 += 216;
        }
        while ( v26 );
      }
      if ( v36 && (*((_DWORD *)v37 + 36) & 0x100) != 0 )
        v36 = BSavePrinterProperties(*((void **)v37 + 4), *(_DWORD *)(*((_QWORD *)v37 + 6) + 24LL) & 0x100000);
    }
    PSUI::VFreeCommonInfo(v37, v7);
  }
  else
  {
    v36 = 0;
  }
  if ( phPrinter )
    ClosePrinter(phPrinter);
  return v36;
}

```

## disassembly

```asm
0x180131dcc  mov     rax, rsp
0x180131dcf  mov     [rax+8], rcx
0x180131dd3  push    rbp
0x180131dd4  push    rsi
0x180131dd5  push    rdi
0x180131dd6  push    r12
0x180131dd8  push    r13
0x180131dda  push    r14
0x180131ddc  push    r15
0x180131dde  lea     rbp, [rax-5Fh]
0x180131de2  sub     rsp, 0A0h
0x180131de9  mov     [rbp+57h+var_40], 0FFFFFFFFFFFFFFFEh
0x180131df1  mov     [rax+18h], rbx
0x180131df5  mov     r15, r9
0x180131df8  mov     r12d, r8d
0x180131dfb  mov     r14d, edx
0x180131dfe  xor     r13d, r13d
0x180131e01  mov     [rbp+57h+hModule], r13
0x180131e05  mov     [rbp+57h+var_98], r13
0x180131e09  mov     [rbp+57h+phPrinter], r13
0x180131e0d  lea     edi, [r13+1]
0x180131e11  mov     [rbp+57h+var_A0], edi
0x180131e14  mov     r8d, edx
0x180131e17  lea     rdx, aEnteringDrvpri; "Entering DrvPrinterEvent: %d ...\n"
0x180131e1e  lea     rbx, aPsuiDrvprinter_0; "PSUI::DrvPrinterEvent"
0x180131e25  mov     rcx, rbx; char *
0x180131e28  call    ?WriteDbgTraceInfo@DriverUiTelemetry@DriverUi@@SAXPEADPEAGZZ; DriverUi::DriverUiTelemetry::WriteDbgTraceInfo(char *,ushort *,...)
0x180131e2d  cmp     r14d, 3
0x180131e31  jz      loc_180132132
0x180131e37  cmp     r14d, 5
0x180131e3b  jz      loc_180131FE7
0x180131e41  cmp     r14d, 8
0x180131e45  jz      short loc_180131E5E
0x180131e47  mov     r8d, edi; unsigned __int16 *
0x180131e4a  mov     rdx, [rbp+57h+pPrinterName]; void *
0x180131e4e  xor     ecx, ecx; this
0x180131e50  call    ?PLoadCommonInfo@PSUI@@YAPEAU_COMMONINFO@1@PEAXPEAGK@Z; PSUI::PLoadCommonInfo(void *,ushort *,ulong)
0x180131e55  mov     [rbp+57h+var_98], rax
0x180131e59  jmp     loc_1801321F8
0x180131e5e  mov     [rbp+57h+var_48], r15
0x180131e62  mov     rcx, r15; pbstr
0x180131e65  call    cs:__imp_SysStringLen
0x180131e6b  test    eax, eax
0x180131e6d  jnz     short loc_180131E78
0x180131e6f  mov     [rbp+57h+var_A0], r13d
0x180131e73  jmp     loc_1801321F8
0x180131e78  lea     rax, [rbp+57h+var_98]
0x180131e7c  mov     [rbp+57h+var_68], rax
0x180131e80  lea     rax, [rbp+57h+pPrinterName]
0x180131e84  mov     qword ptr [rbp+57h+var_60], rax
0x180131e88  lea     rax, [rbp+57h+var_48]
0x180131e8c  mov     qword ptr [rbp+57h+var_60+8], rax
0x180131e90  lea     rax, [rbp+57h+var_A0]
0x180131e94  mov     [rbp+57h+var_50], rax
0x180131e98  mov     [rbp+57h+arg_8], r13b
0x180131e9c  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_UniDrv_DelayLoad_CrashFix@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_UniDrv_DelayLoad_CrashFix@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_UniDrv_DelayLoad_CrashFix> `wil::Feature<__WilFeatureTraits_Feature_UniDrv_DelayLoad_CrashFix>::GetImpl(void)'::`2'::impl
0x180131ea3  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_UniDrv_DelayLoad_CrashFix@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_UniDrv_DelayLoad_CrashFix>::__private_IsEnabled(void)
0x180131ea8  test    al, al
0x180131eaa  jz      loc_180131F57
0x180131eb0  cmp     cs:?s_isLoadLibraryCheckDone@?1??IsIppCommonAvailable@IppCommonUtil@@YA_NXZ@4_NA, r13b; bool `IppCommonUtil::IsIppCommonAvailable(void)'::`2'::s_isLoadLibraryCheckDone
0x180131eb7  jnz     short loc_180131EEA
0x180131eb9  xor     edx, edx; hFile
0x180131ebb  mov     r8d, 800h; dwFlags
0x180131ec1  lea     rcx, aIppcommonDll_0; "ippcommon.dll"
0x180131ec8  call    cs:__imp_LoadLibraryExW
0x180131ece  test    rax, rax
0x180131ed1  jz      short loc_180131EE3
0x180131ed3  mov     cs:?s_isIppCommonAvailable@?1??IsIppCommonAvailable@IppCommonUtil@@YA_NXZ@4_NA, dil; bool `IppCommonUtil::IsIppCommonAvailable(void)'::`2'::s_isIppCommonAvailable
0x180131eda  mov     rcx, rax; hLibModule
0x180131edd  call    cs:__imp_FreeLibrary
0x180131ee3  mov     cs:?s_isLoadLibraryCheckDone@?1??IsIppCommonAvailable@IppCommonUtil@@YA_NXZ@4_NA, dil; bool `IppCommonUtil::IsIppCommonAvailable(void)'::`2'::s_isLoadLibraryCheckDone
0x180131eea  cmp     cs:?s_isIppCommonAvailable@?1??IsIppCommonAvailable@IppCommonUtil@@YA_NXZ@4_NA, r13b; bool `IppCommonUtil::IsIppCommonAvailable(void)'::`2'::s_isIppCommonAvailable
0x180131ef1  jz      loc_180131FD9
0x180131ef7  lea     r8, [rbp+57h+arg_8]
0x180131efb  xor     edx, edx
0x180131efd  mov     rcx, [rbp+57h+pPrinterName]
0x180131f01  call    cs:__imp_IsModernPrinter
0x180131f07  test    eax, eax
0x180131f09  js      loc_180131FD9
0x180131f0f  cmp     [rbp+57h+arg_8], r13b
0x180131f13  jz      loc_180131FD9
0x180131f19  mov     dword ptr [rbp+57h+hModule], r13d
0x180131f1d  lea     rdx, [rbp+57h+hModule]; int *
0x180131f21  lea     rcx, [rbp+57h+hLibModule]; this
0x180131f25  call    ??0RevertToPrinterRAII@@QEAA@PEAJ@Z; RevertToPrinterRAII::RevertToPrinterRAII(long *)
0x180131f2a  nop
0x180131f2b  mov     eax, dword ptr [rbp+57h+hModule]
0x180131f2e  test    eax, eax
0x180131f30  js      short loc_180131F3E
0x180131f32  lea     rcx, [rbp+57h+var_68]
0x180131f36  call    _lambda_7709aa7672fa7c7d1651f7628bf4b04b___operator__
0x180131f3b  nop
0x180131f3c  jmp     short loc_180131FAD
0x180131f3e  movzx   r8d, ax
0x180131f42  lea     rdx, aFailedToRevert; "Failed to revert to printer self: %d\n"
0x180131f49  mov     rcx, rbx; char *
0x180131f4c  call    ?WriteDbgTraceWarning@DriverUiTelemetry@DriverUi@@SAXPEADPEAGZZ; DriverUi::DriverUiTelemetry::WriteDbgTraceWarning(char *,ushort *,...)
0x180131f51  mov     [rbp+57h+var_A0], r13d
0x180131f55  jmp     short loc_180131FAD
0x180131f57  lea     r8, [rbp+57h+arg_8]
0x180131f5b  xor     edx, edx
0x180131f5d  mov     rcx, [rbp+57h+pPrinterName]
0x180131f61  call    cs:__imp_IsModernPrinter
0x180131f67  test    eax, eax
0x180131f69  js      short loc_180131FD9
0x180131f6b  cmp     [rbp+57h+arg_8], r13b
0x180131f6f  jz      short loc_180131FD9
0x180131f71  mov     dword ptr [rbp+57h+hModule], r13d
0x180131f75  lea     rdx, [rbp+57h+hModule]; int *
0x180131f79  lea     rcx, [rbp+57h+hLibModule]; this
0x180131f7d  call    ??0RevertToPrinterRAII@@QEAA@PEAJ@Z; RevertToPrinterRAII::RevertToPrinterRAII(long *)
0x180131f82  nop
0x180131f83  mov     eax, dword ptr [rbp+57h+hModule]
0x180131f86  test    eax, eax
0x180131f88  js      short loc_180131F96
0x180131f8a  lea     rcx, [rbp+57h+var_68]
0x180131f8e  call    _lambda_7709aa7672fa7c7d1651f7628bf4b04b___operator__
0x180131f93  nop
0x180131f94  jmp     short loc_180131FAD
0x180131f96  movzx   r8d, ax
0x180131f9a  lea     rdx, aFailedToRevert; "Failed to revert to printer self: %d\n"
0x180131fa1  mov     rcx, rbx; char *
0x180131fa4  call    ?WriteDbgTraceWarning@DriverUiTelemetry@DriverUi@@SAXPEADPEAGZZ; DriverUi::DriverUiTelemetry::WriteDbgTraceWarning(char *,ushort *,...)
0x180131fa9  mov     [rbp+57h+var_A0], r13d
0x180131fad  mov     rax, [rbp+57h+var_70]
0x180131fb1  test    rax, rax
0x180131fb4  jz      short loc_180131FC4
0x180131fb6  mov     rcx, [rbp+57h+var_78]
0x180131fba  test    rcx, rcx
0x180131fbd  jz      short loc_180131FC4
0x180131fbf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180131fc4  mov     rcx, [rbp+57h+hLibModule]; hLibModule
0x180131fc8  test    rcx, rcx
0x180131fcb  jz      short loc_180131FD4
0x180131fcd  call    cs:__imp_FreeLibrary
0x180131fd3  nop
0x180131fd4  jmp     loc_1801321F8
0x180131fd9  lea     rcx, [rbp+57h+var_68]
0x180131fdd  call    _lambda_7709aa7672fa7c7d1651f7628bf4b04b___operator__
0x180131fe2  jmp     loc_1801321F8
0x180131fe7  xor     r8d, r8d; pDefault
0x180131fea  lea     rdx, [rbp+57h+phPrinter]; phPrinter
0x180131fee  mov     rcx, [rbp+57h+pPrinterName]; pPrinterName
0x180131ff2  call    cs:__imp_OpenPrinterW
0x180131ff8  test    eax, eax
0x180131ffa  jnz     short loc_180132021
0x180131ffc  call    cs:__imp_GetLastError
0x180132002  mov     r9d, eax
0x180132005  mov     r8, [rbp+57h+pPrinterName]
0x180132009  lea     rdx, aOpenprinterWsF; "OpenPrinter '%ws' failed: %d\n"
0x180132010  mov     rcx, rbx; char *
0x180132013  call    ?WriteDbgTraceWarning@DriverUiTelemetry@DriverUi@@SAXPEADPEAGZZ; DriverUi::DriverUiTelemetry::WriteDbgTraceWarning(char *,ushort *,...)
0x180132018  mov     [rbp+57h+phPrinter], r13
0x18013201c  jmp     loc_1801321F8
0x180132021  xorps   xmm0, xmm0
0x180132024  movdqu  [rbp+57h+var_60], xmm0
0x180132029  mov     [rbp+57h+var_50], r13
0x18013202d  mov     [rbp+57h+var_68], 0FFFFFFFFFFFFFFFFh
0x180132035  lea     rdx, [rbp+57h+hModule]
0x180132039  lea     rcx, aSpoolssDll; "spoolss.dll"
0x180132040  call    LoadLibraryFromSystemDirectory
0x180132045  mov     rbx, [rbp+57h+hModule]
0x180132049  test    eax, eax
0x18013204b  js      loc_1801320FA
0x180132051  lea     rdx, aReverttoprinte; "RevertToPrinterSelf"
0x180132058  mov     rcx, rbx; hModule
0x18013205b  call    cs:__imp_GetProcAddress
0x180132061  mov     rsi, rax
0x180132064  test    rax, rax
0x180132067  jz      loc_1801320FA
0x18013206d  lea     rdx, aImpersonatepri; "ImpersonatePrinterClient"
0x180132074  mov     rcx, rbx; hModule
0x180132077  call    cs:__imp_GetProcAddress
0x18013207d  mov     rdi, rax
0x180132080  test    rax, rax
0x180132083  jz      short loc_1801320FA
0x180132085  mov     rax, rsi
0x180132088  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18013208d  mov     rsi, rax
0x180132090  mov     r8d, 8000h; unsigned __int16 *
0x180132096  mov     rdx, [rbp+57h+pPrinterName]; void *
0x18013209a  mov     rcx, [rbp+57h+phPrinter]; this
0x18013209e  call    ?PLoadCommonInfo@PSUI@@YAPEAU_COMMONINFO@1@PEAXPEAGK@Z; PSUI::PLoadCommonInfo(void *,ushort *,ulong)
0x1801320a3  mov     [rbp+57h+var_98], rax
0x1801320a7  lea     rdx, [rbp+57h+var_68]; struct PSUI::_COMMONINFO *
0x1801320ab  call    ?_BCopyCachedFile@PSUI@@YAHPEAU_COMMONINFO@1@PEAU_CACHEDFILE@1@@Z; PSUI::_BCopyCachedFile(PSUI::_COMMONINFO *,PSUI::_CACHEDFILE *)
0x1801320b0  lea     rcx, [rbp+57h+var_68]; this
0x1801320b4  call    ?_VDisposeCachedFileInfo@PSUI@@YAXPEAU_CACHEDFILE@1@@Z; PSUI::_VDisposeCachedFileInfo(PSUI::_CACHEDFILE *)
0x1801320b9  test    rsi, rsi
0x1801320bc  jz      short loc_1801320EC
0x1801320be  mov     rcx, rsi
0x1801320c1  mov     rax, rdi
0x1801320c4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801320c9  mov     [rbp+57h+var_A0], eax
0x1801320cc  test    eax, eax
0x1801320ce  jnz     short loc_1801320EC
0x1801320d0  call    cs:__imp_GetLastError
0x1801320d6  mov     r8d, eax
0x1801320d9  lea     rdx, aPrintereventIm; "PrinterEvent-ImpersonatePrinterClient f"...
0x1801320e0  lea     rcx, aPsuiDrvprinter_0; "PSUI::DrvPrinterEvent"
0x1801320e7  call    ?WriteDbgTraceWarning@DriverUiTelemetry@DriverUi@@SAXPEADPEAGZZ; DriverUi::DriverUiTelemetry::WriteDbgTraceWarning(char *,ushort *,...)
0x1801320ec  mov     rcx, rbx; hLibModule
0x1801320ef  call    cs:__imp_FreeLibrary
0x1801320f5  jmp     loc_1801321F8
0x1801320fa  call    cs:__imp_GetLastError
0x180132100  mov     r8d, eax
0x180132103  lea     rdx, aCouldnTLoadSpo; "Couldn't load spoolss.dll: %d\n"
0x18013210a  lea     rcx, aPsuiDrvprinter_0; "PSUI::DrvPrinterEvent"
0x180132111  call    ?WriteDbgTraceWarning@DriverUiTelemetry@DriverUi@@SAXPEADPEAGZZ; DriverUi::DriverUiTelemetry::WriteDbgTraceWarning(char *,ushort *,...)
0x180132116  test    rbx, rbx
0x180132119  jz      short loc_180132124
0x18013211b  mov     rcx, rbx; hLibModule
0x18013211e  call    cs:__imp_FreeLibrary
0x180132124  lea     rcx, [rbp+57h+var_68]; this
0x180132128  call    ?_VDisposeCachedFileInfo@PSUI@@YAXPEAU_CACHEDFILE@1@@Z; PSUI::_VDisposeCachedFileInfo(PSUI::_CACHEDFILE *)
0x18013212d  jmp     loc_1801321F8
0x180132132  mov     r8d, 0Ch; unsigned __int16 *
0x180132138  mov     rdx, [rbp+57h+pPrinterName]; void *
0x18013213c  xor     ecx, ecx; this
0x18013213e  call    ?PLoadCommonInfo@PSUI@@YAPEAU_COMMONINFO@1@PEAXPEAGK@Z; PSUI::PLoadCommonInfo(void *,ushort *,ulong)
0x180132143  mov     rcx, rax; this
0x180132146  mov     [rbp+57h+var_98], rax
0x18013214a  test    rax, rax
0x18013214d  jz      loc_1801321F8
0x180132153  call    ?BInitOrUpgradePrinterProperties@PSUI@@YAHPEAU_COMMONINFO@1@@Z; PSUI::BInitOrUpgradePrinterProperties(PSUI::_COMMONINFO *)
0x180132158  mov     rcx, [rbp+57h+var_98]; this
0x18013215c  call    ?BFillCommonInfoPrinterData@PSUI@@YAHPEAU_COMMONINFO@1@@Z; PSUI::BFillCommonInfoPrinterData(PSUI::_COMMONINFO *)
0x180132161  test    eax, eax
0x180132163  jz      loc_1801321E9
0x180132169  mov     rcx, [rbp+57h+var_98]; this
0x18013216d  call    ?BCombineCommonInfoOptionsArray@PSUI@@YAHPEAU_COMMONINFO@1@@Z; PSUI::BCombineCommonInfoOptionsArray(PSUI::_COMMONINFO *)
0x180132172  test    eax, eax
0x180132174  jz      short loc_1801321E9
0x180132176  mov     rcx, [rbp+57h+var_98]
0x18013217a  mov     rax, [rcx+48h]
0x18013217e  cmp     [rax+138h], r13d
0x180132185  jz      short loc_180132197
0x180132187  mov     rdx, rcx; unsigned __int16 *
0x18013218a  mov     rcx, [rbp+57h+pPrinterName]; this
0x18013218e  call    ?InitBidiAtPrinterInstall@PSUI@@YAHPEAGPEAU_COMMONINFO@1@@Z; PSUI::InitBidiAtPrinterInstall(ushort *,PSUI::_COMMONINFO *)
0x180132193  mov     rcx, [rbp+57h+var_98]
0x180132197  mov     rax, [rcx+30h]
0x18013219b  test    dword ptr [rax+18h], 100000h
0x1801321a2  jz      short loc_1801321D1
0x1801321a4  mov     r9d, edi
0x1801321a7  lea     r8, Filename
0x1801321ae  lea     rdx, aTrayformqueuep; "TrayFormQueueProp"
0x1801321b5  mov     rcx, [rcx+20h]; hPrinter
0x1801321b9  call    BSetPrinterDataString
0x1801321be  test    eax, eax
0x1801321c0  jnz     short loc_1801321D1
0x1801321c2  lea     rdx, aUnableToInitia; "Unable to initialize the form-tray data"...
0x1801321c9  mov     rcx, rbx; char *
0x1801321cc  call    ?WriteDbgTraceWarning@DriverUiTelemetry@DriverUi@@SAXPEADPEAGZZ; DriverUi::DriverUiTelemetry::WriteDbgTraceWarning(char *,ushort *,...)
0x1801321d1  call    bIsOnWin8AndAbove
0x1801321d6  test    eax, eax
0x1801321d8  jnz     short loc_1801321F8
0x1801321da  mov     rcx, [rbp+57h+var_98]
0x1801321de  mov     rcx, [rcx+20h]; this
0x1801321e2  call    ?VNotifyDSOfUpdate@PSUI@@YAXPEAX@Z; PSUI::VNotifyDSOfUpdate(void *)
0x1801321e7  jmp     short loc_1801321F8
0x1801321e9  lea     rdx, aPrinterEventIn; "PRINTER_EVENT_INITIALIZE failed. Unable"...
0x1801321f0  mov     rcx, rbx; char *
0x1801321f3  call    ?WriteDbgTraceWarning@DriverUiTelemetry@DriverUi@@SAXPEADPEAGZZ; DriverUi::DriverUiTelemetry::WriteDbgTraceWarning(char *,ushort *,...)
0x1801321f8  mov     rcx, [rbp+57h+var_98]
0x1801321fc  test    rcx, rcx
0x1801321ff  jz      loc_1801323B9
0x180132205  cmp     [rbp+57h+var_A0], r13d
0x180132209  jz      loc_1801323AE
0x18013220f  cmp     [rcx+70h], r13
0x180132213  jz      short loc_18013221C
0x180132215  or      dword ptr [rcx+90h], 0Ch
0x18013221c  mov     rax, [rbp+57h+var_98]
0x180132220  mov     rcx, [rax+50h]
0x180132224  lea     rbx, [rcx+18h]
0x180132228  mov     edi, [rcx+8]
0x18013222b  test    edi, edi
0x18013222d  jz      loc_180132374
0x180132233  mov     r9, qword ptr cs:IID_IPrintOemUI.Data4
0x18013223a  mov     r10, qword ptr cs:IID_IPrintOemUI.Data1
0x180132241  mov     r8, qword ptr cs:IID_IPrintOemUI2.Data4
0x180132248  mov     r11, qword ptr cs:IID_IPrintOemUI2.Data1
0x18013224f  dec     edi
0x180132251  cmp     [rbx+20h], r13
0x180132255  jz      loc_180132365
0x18013225b  mov     rcx, [rbx+48h]
0x18013225f  test    rcx, rcx
0x180132262  jz      short loc_1801322D2
0x180132264  mov     rdx, [rbp+57h+pPrinterName]
0x180132268  cmp     [rbx+50h], r10
0x18013226c  jnz     short loc_180132274
0x18013226e  cmp     [rbx+58h], r9
0x180132272  jz      short loc_180132280
0x180132274  cmp     [rbx+50h], r11
0x180132278  jnz     short loc_1801322C0
0x18013227a  cmp     [rbx+58h], r8
0x18013227e  jnz     short loc_1801322C0
0x180132280  mov     rax, [rcx]
0x180132283  mov     [rsp+20h], r15
0x180132288  mov     r9d, r12d
  ... truncated ...
```
