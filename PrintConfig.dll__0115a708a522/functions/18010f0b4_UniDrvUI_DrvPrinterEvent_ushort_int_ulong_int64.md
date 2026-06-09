# UniDrvUI::DrvPrinterEvent(ushort *,int,ulong,__int64)

- ea: `0x18010f0b4`
- end: `0x18010f750`
- name: `?DrvPrinterEvent@UniDrvUI@@YAHPEAGHK_J@Z`
- size: `1692`
- prototype: `__int64 __fastcall(WCHAR *this, unsigned __int16 *, unsigned int, OLECHAR *)`
- caller_count: `1`
- callee_count: `24`
- tags: `file_ops, authz_impersonation, loader_planting, installer_update, broker_com_uri`

## callers

- `0x180030a20`

## callees

- `0x180006268`
- `0x180107214`
- `0x180108e2c`
- `0x18010db18`
- `0x18010e88c`
- `0x18010f0b4`
- `0x18010f97c`
- `0x18010fa74`
- `0x18010fcb8`
- `0x18010fed0`
- `0x180110010`
- `0x18011307c`
- `0x1801135cc`
- `0x1801146b4`
- `0x180116080`
- `0x180116430`
- `0x180128d10`
- `0x180150158`
- `0x1801513b8`
- `0x18015178c`
- `0x1801519e4`
- `0x180155868`
- `0x180157d60`
- `0x1801cb010`

## import_xrefs

- `KERNEL32!DeleteFileW` at `0x18010f50e`
- `KERNEL32!DeleteFileW` at `0x18010f50e`
- `KERNEL32!GetProcAddress` at `0x18010f2c0`
- `KERNEL32!GetProcAddress` at `0x18010f2e2`
- `KERNEL32!GetProcAddress` at `0x18010f2c0`
- `KERNEL32!GetProcAddress` at `0x18010f2e2`
- `KERNEL32!FreeLibrary` at `0x18010f220`
- `KERNEL32!FreeLibrary` at `0x18010f36a`
- `KERNEL32!FreeLibrary` at `0x18010f3a5`
- `KERNEL32!FreeLibrary` at `0x18010f220`
- `KERNEL32!FreeLibrary` at `0x18010f36a`
- `KERNEL32!FreeLibrary` at `0x18010f3a5`
- `KERNEL32!GetLastError` at `0x18010f25b`
- `KERNEL32!GetLastError` at `0x18010f345`
- `KERNEL32!GetLastError` at `0x18010f37b`
- `KERNEL32!GetLastError` at `0x18010f67e`
- `KERNEL32!GetLastError` at `0x18010f25b`
- `KERNEL32!GetLastError` at `0x18010f345`
- `KERNEL32!GetLastError` at `0x18010f37b`
- `KERNEL32!GetLastError` at `0x18010f67e`
- `KERNEL32!LocalFree` at `0x18010f51d`
- `KERNEL32!LocalFree` at `0x18010f531`
- `KERNEL32!LocalFree` at `0x18010f545`
- `KERNEL32!LocalFree` at `0x18010f51d`
- `KERNEL32!LocalFree` at `0x18010f531`
- `KERNEL32!LocalFree` at `0x18010f545`
- `OLEAUT32!__imp_SysStringLen` at `0x18010f167`
- `OLEAUT32!__imp_SysStringLen` at `0x18010f167`
- `WINSPOOL!ClosePrinter` at `0x18010f725`
- `WINSPOOL!ClosePrinter` at `0x18010f725`
- `WINSPOOL!OpenPrinterW` at `0x18010f24b`
- `WINSPOOL!OpenPrinterW` at `0x18010f49c`
- `WINSPOOL!OpenPrinterW` at `0x18010f24b`
- `WINSPOOL!OpenPrinterW` at `0x18010f49c`
- `IppCommon!IsModernPrinter` at `0x18010f1ae`
- `IppCommon!IsModernPrinter` at `0x18010f1ae`

## string_xrefs

- `0x18010f29e`: `spoolss.dll`
- `0x18010f2d8`: `ImpersonatePrinterClient`
- `0x18010f26e`: `OpenPrinter '%ws' failed: %d\n`
- `0x18010f38a`: `Couldn't load spoolss.dll: %d\n`
- `0x18010f354`: `PrinterEvent-ImpersonatePrinterClient failed: %d\n`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall UniDrvUI::DrvPrinterEvent(WCHAR *this, unsigned __int16 *a2, unsigned int a3, OLECHAR *a4)
{
  unsigned int v6; // r15d
  struct UniDrvUI::_COMMONINFO *v7; // rdx
  __int64 v8; // r9
  unsigned __int16 *v9; // r9
  DWORD LastError; // eax
  int v11; // eax
  HMODULE v12; // rbx
  __int64 (*ProcAddress)(void); // rsi
  FARPROC v14; // rdi
  __int64 v15; // rsi
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
  wchar_t *PrinterDataString; // rax
  wchar_t *v28; // rsi
  wchar_t *v29; // rdi
  WCHAR *v30; // rbx
  const wchar_t *v31; // rax
  unsigned __int16 *v32; // r8
  const WCHAR *v33; // rax
  __int64 v34; // rcx
  __int64 v35; // rbx
  int v36; // edi
  __int64 v37; // r10
  __int64 v38; // r8
  __int64 v39; // r11
  __int64 v40; // rcx
  int v41; // eax
  unsigned int (__fastcall *v42)(LPWSTR, _QWORD, _QWORD, OLECHAR *); // rax
  DWORD v43; // eax
  unsigned int v45; // [rsp+38h] [rbp-49h] BYREF
  UniDrvUI *v46; // [rsp+40h] [rbp-41h] BYREF
  HANDLE phPrinter; // [rsp+48h] [rbp-39h] BYREF
  HMODULE hModule; // [rsp+50h] [rbp-31h] BYREF
  __int128 v49; // [rsp+58h] [rbp-29h] BYREF
  __int128 v50; // [rsp+68h] [rbp-19h]
  HMODULE hLibModule[2]; // [rsp+78h] [rbp-9h] BYREF
  void (*v52)(void); // [rsp+88h] [rbp+7h]
  _QWORD v53[9]; // [rsp+90h] [rbp+Fh] BYREF
  LPWSTR pPrinterName; // [rsp+E8h] [rbp+67h] BYREF
  char v55; // [rsp+F0h] [rbp+6Fh] BYREF

  pPrinterName = this;
  v53[1] = -2;
  v6 = (unsigned int)a2;
  hModule = 0;
  v46 = 0;
  phPrinter = 0;
  v45 = 1;
  v49 = 0;
  v50 = 0;
  DriverUi::DriverUiTelemetry::WriteDbgTraceInfo(
    "UniDrvUI::DrvPrinterEvent",
    L"Entering DrvPrinterEvent: %d ...\n",
    (unsigned int)a2);
  if ( v6 == 2 )
    goto LABEL_44;
  if ( v6 == 3 )
  {
    v22 = UniDrvUI::PLoadCommonInfo(0, pPrinterName, (unsigned __int16 *)0xC);
    v46 = v22;
    if ( v22 )
    {
      UniDrvUI::BInitOrUpgradePrinterProperties(v22, v7);
      if ( (unsigned int)UniDrvUI::BFillCommonInfoPrinterData(v46, v23)
        && (unsigned int)UniDrvUI::BCombineCommonInfoOptionsArray(v46, v24) )
      {
        v26 = v46;
        if ( *(_DWORD *)(*((_QWORD *)v46 + 9) + 312LL) )
        {
          UniDrvUI::InitBidiAtPrinterInstall((UniDrvUI *)pPrinterName, (unsigned __int16 *)v46, v25);
          v26 = v46;
        }
        if ( (*(_DWORD *)(*((_QWORD *)v26 + 6) + 24LL) & 0x100000) != 0
          && !BSetPrinterDataString(*((HANDLE *)v26 + 4), (WCHAR *)L"TrayFormQueueProp", (BYTE *)&Filename, 1u) )
        {
          DriverUi::DriverUiTelemetry::WriteDbgTraceWarning(
            "UniDrvUI::DrvPrinterEvent",
            L"Unable to initialize the form-tray database queue property.\n");
        }
        if ( !bIsOnWin8AndAbove() )
          UniDrvUI::VNotifyDSOfUpdate(*((UniDrvUI **)v46 + 4), v7);
      }
      else
      {
        DriverUi::DriverUiTelemetry::WriteDbgTraceWarning(
          "UniDrvUI::DrvPrinterEvent",
          L"PRINTER_EVENT_INITIALIZE failed. Unable to load printer data.\n");
      }
    }
    goto LABEL_54;
  }
  if ( v6 == 4 )
  {
LABEL_44:
    if ( !OpenPrinterW(pPrinterName, &phPrinter, 0) )
      goto LABEL_22;
    v46 = UniDrvUI::PLoadCommonInfo(0, pPrinterName, (unsigned __int16 *)1);
    PrinterDataString = (wchar_t *)PtstrGetPrinterDataString(phPrinter, (LPWSTR)L"ExternalFontFile", 0);
    v28 = PrinterDataString;
    if ( PrinterDataString )
    {
      v29 = 0;
      v30 = 0;
      if ( *PrinterDataString )
      {
        v31 = UniDrvUI::PGetFileDirectory(0, (unsigned __int16 *)v7);
        v29 = (wchar_t *)v31;
        if ( v31 )
        {
          v33 = UniDrvUI::PConcatFilename(v31, v28, v32);
          v30 = (WCHAR *)v33;
          if ( v33 )
            DeleteFileW(v33);
        }
      }
      LocalFree(v28);
      if ( v29 )
        LocalFree(v29);
      if ( v30 )
        LocalFree(v30);
    }
  }
  else
  {
    if ( v6 != 5 )
    {
      if ( v6 == 8 )
      {
        v53[0] = a4;
        if ( SysStringLen(a4) )
        {
          *(_QWORD *)&v49 = &v46;
          *((_QWORD *)&v49 + 1) = &pPrinterName;
          *(_QWORD *)&v50 = v53;
          *((_QWORD *)&v50 + 1) = &v45;
          v55 = 0;
          if ( (int)IsModernPrinter(pPrinterName, 0, &v55) >= 0 && v55 )
          {
            LODWORD(hModule) = 0;
            RevertToPrinterRAII::RevertToPrinterRAII((RevertToPrinterRAII *)hLibModule, (int *)&hModule);
            if ( (int)hModule < 0 )
            {
              DriverUi::DriverUiTelemetry::WriteDbgTraceWarning(
                "UniDrvUI::DrvPrinterEvent",
                L"Failed to revert to printer self: %d\n",
                (unsigned __int16)hModule);
              v45 = 0;
            }
            else
            {
              lambda_97e360d8fabff85a69a15679bfe5c655_::operator()((struct UniDrvUI::_COMMONINFO ***)&v49);
            }
            if ( v52 && hLibModule[1] )
              v52();
            if ( hLibModule[0] )
              FreeLibrary(hLibModule[0]);
          }
          else
          {
            lambda_97e360d8fabff85a69a15679bfe5c655_::operator()((struct UniDrvUI::_COMMONINFO ***)&v49);
          }
        }
        else
        {
          v45 = 0;
        }
      }
      else
      {
        v46 = UniDrvUI::PLoadCommonInfo(0, pPrinterName, (unsigned __int16 *)1);
      }
      goto LABEL_54;
    }
    if ( !OpenPrinterW(pPrinterName, &phPrinter, 0) )
    {
LABEL_22:
      LastError = GetLastError();
      DriverUi::DriverUiTelemetry::WriteDbgTraceWarning(
        "UniDrvUI::DrvPrinterEvent",
        L"OpenPrinter '%ws' failed: %d\n",
        pPrinterName,
        LastError);
      phPrinter = 0;
      goto LABEL_54;
    }
    UniDrvUI::_BPrepareToCopyCachedFile(phPrinter, (PSUI *)&v49, (LPWSTR)L"ExternalFontFile", v9);
    v11 = LoadLibraryFromSystemDirectory(L"spoolss.dll", &hModule);
    v12 = hModule;
    if ( v11 >= 0
      && (ProcAddress = GetProcAddress(hModule, "RevertToPrinterSelf")) != 0
      && (v14 = GetProcAddress(v12, "ImpersonatePrinterClient")) != 0 )
    {
      v15 = ProcAddress();
      v46 = UniDrvUI::PLoadCommonInfo((UniDrvUI *)phPrinter, pPrinterName, (unsigned __int16 *)0x8000);
      UniDrvUI::_BCopyCachedFile(v16, (struct UniDrvUI::_COMMONINFO *)&v49, v17);
      PSUI::_VDisposeCachedFileInfo((HANDLE *)&v49, v18);
      if ( v15 )
      {
        v45 = ((__int64 (__fastcall *)(__int64))v14)(v15);
        if ( !v45 )
        {
          v19 = GetLastError();
          DriverUi::DriverUiTelemetry::WriteDbgTraceWarning(
            "UniDrvUI::DrvPrinterEvent",
            L"PrinterEvent-ImpersonatePrinterClient failed: %d\n",
            v19);
        }
      }
      FreeLibrary(v12);
    }
    else
    {
      v20 = GetLastError();
      DriverUi::DriverUiTelemetry::WriteDbgTraceWarning(
        "UniDrvUI::DrvPrinterEvent",
        L"Couldn't load spoolss.dll: %d\n",
        v20);
      if ( v12 )
        FreeLibrary(v12);
      PSUI::_VDisposeCachedFileInfo((HANDLE *)&v49, v21);
    }
  }
LABEL_54:
  if ( v46 )
  {
    if ( v45 )
    {
      if ( *((_QWORD *)v46 + 14) )
        *((_DWORD *)v46 + 36) |= 0xCu;
      v34 = *((_QWORD *)v46 + 10);
      v35 = v34 + 24;
      v36 = *(_DWORD *)(v34 + 8);
      if ( v36 )
      {
        v8 = *(_QWORD *)IID_IPrintOemUI.Data4;
        v37 = *(_QWORD *)&IID_IPrintOemUI.Data1;
        v38 = *(_QWORD *)IID_IPrintOemUI2.Data4;
        v39 = *(_QWORD *)&IID_IPrintOemUI2.Data1;
        do
        {
          --v36;
          if ( *(_QWORD *)(v35 + 32) )
          {
            v40 = *(_QWORD *)(v35 + 72);
            if ( !v40 )
            {
              if ( (*(_BYTE *)(v35 + 101) & 1) != 0 )
              {
                v42 = *(unsigned int (__fastcall **)(LPWSTR, _QWORD, _QWORD, OLECHAR *))(v35 + 168);
              }
              else
              {
                v42 = (unsigned int (__fastcall *)(LPWSTR, _QWORD, _QWORD, OLECHAR *))PGetOemEntrypointAddress(v35, 8u);
                v8 = *(_QWORD *)IID_IPrintOemUI.Data4;
                v37 = *(_QWORD *)&IID_IPrintOemUI.Data1;
                v38 = *(_QWORD *)IID_IPrintOemUI2.Data4;
                v39 = *(_QWORD *)&IID_IPrintOemUI2.Data1;
              }
              if ( !v42 )
                goto LABEL_77;
              if ( !v42(pPrinterName, v6, a3, a4) )
              {
                v43 = GetLastError();
                DriverUi::DriverUiTelemetry::WriteDbgTraceWarning(
                  "UniDrvUI::DrvPrinterEvent",
                  L"OEMPrinterEvent failed for '%ws': %d\n",
                  *(_QWORD *)(v35 + 8),
                  v43);
                v45 = 0;
              }
LABEL_76:
              v39 = *(_QWORD *)&IID_IPrintOemUI2.Data1;
              v38 = *(_QWORD *)IID_IPrintOemUI2.Data4;
              v37 = *(_QWORD *)&IID_IPrintOemUI.Data1;
              v8 = *(_QWORD *)IID_IPrintOemUI.Data4;
              goto LABEL_77;
            }
            v7 = (struct UniDrvUI::_COMMONINFO *)pPrinterName;
            if ( *(_QWORD *)(v35 + 80) == v37 && *(_QWORD *)(v35 + 88) == v8
              || *(_QWORD *)(v35 + 80) == v39 && *(_QWORD *)(v35 + 88) == v38 )
            {
              v41 = (*(__int64 (__fastcall **)(__int64, LPWSTR, _QWORD, _QWORD, OLECHAR *))(*(_QWORD *)v40 + 96LL))(
                      v40,
                      pPrinterName,
                      v6,
                      a3,
                      a4);
              if ( v41 == -2147467263 )
                goto LABEL_76;
              v8 = *(_QWORD *)IID_IPrintOemUI.Data4;
              v37 = *(_QWORD *)&IID_IPrintOemUI.Data1;
              v38 = *(_QWORD *)IID_IPrintOemUI2.Data4;
              v39 = *(_QWORD *)&IID_IPrintOemUI2.Data1;
            }
            else
            {
              v41 = -2147467262;
            }
            v45 = v41 >= 0;
          }
LABEL_77:
          v35 += 216;
        }
        while ( v36 );
      }
      if ( v45 && (*((_DWORD *)v46 + 36) & 0x100) != 0 )
        v45 = BSavePrinterProperties(
                *((void **)v46 + 4),
                *(_QWORD *)(*((_QWORD *)v46 + 6) + 40LL),
                *((_QWORD *)v46 + 13),
                v8,
                *(_DWORD *)(*((_QWORD *)v46 + 6) + 24LL) & 0x100000);
    }
    UniDrvUI::VFreeCommonInfo(v46, v7);
  }
  else
  {
    v45 = 0;
  }
  if ( phPrinter )
    ClosePrinter(phPrinter);
  return v45;
}

```

## disassembly

```asm
0x18010f0b4  mov     rax, rsp
0x18010f0b7  mov     [rax+8], rcx
0x18010f0bb  push    rbp
0x18010f0bc  push    rsi
0x18010f0bd  push    rdi
0x18010f0be  push    r12
0x18010f0c0  push    r13
0x18010f0c2  push    r14
0x18010f0c4  push    r15
0x18010f0c6  lea     rbp, [rax-5Fh]
0x18010f0ca  sub     rsp, 0A0h
0x18010f0d1  mov     [rbp+57h+var_40], 0FFFFFFFFFFFFFFFEh
0x18010f0d9  mov     [rax+18h], rbx
0x18010f0dd  mov     r14, r9
0x18010f0e0  mov     r12d, r8d
0x18010f0e3  mov     r15d, edx
0x18010f0e6  xor     r13d, r13d
0x18010f0e9  mov     [rbp+57h+hModule], r13
0x18010f0ed  mov     [rbp+57h+var_98], r13
0x18010f0f1  mov     [rbp+57h+phPrinter], r13
0x18010f0f5  lea     edi, [r13+1]
0x18010f0f9  mov     [rbp+57h+var_A0], edi
0x18010f0fc  xorps   xmm0, xmm0
0x18010f0ff  movups  [rbp+57h+var_80], xmm0
0x18010f103  movups  [rbp+57h+var_70], xmm0
0x18010f107  mov     r8d, edx
0x18010f10a  lea     rdx, aEnteringDrvpri; "Entering DrvPrinterEvent: %d ...\n"
0x18010f111  lea     rbx, aUnidrvuiDrvpri; "UniDrvUI::DrvPrinterEvent"
0x18010f118  mov     rcx, rbx; char *
0x18010f11b  call    ?WriteDbgTraceInfo@DriverUiTelemetry@DriverUi@@SAXPEADPEAGZZ; DriverUi::DriverUiTelemetry::WriteDbgTraceInfo(char *,ushort *,...)
0x18010f120  mov     ecx, r15d
0x18010f123  sub     ecx, 2
0x18010f126  jz      loc_18010F491
0x18010f12c  sub     ecx, edi
0x18010f12e  jz      loc_18010F3BF
0x18010f134  sub     ecx, edi
0x18010f136  jz      loc_18010F491
0x18010f13c  sub     ecx, edi
0x18010f13e  jz      loc_18010F240
0x18010f144  cmp     ecx, 3
0x18010f147  jz      short loc_18010F160
0x18010f149  mov     r8d, edi; unsigned __int16 *
0x18010f14c  mov     rdx, [rbp+57h+pPrinterName]; void *
0x18010f150  xor     ecx, ecx; this
0x18010f152  call    ?PLoadCommonInfo@UniDrvUI@@YAPEAU_COMMONINFO@1@PEAXPEAGK@Z; UniDrvUI::PLoadCommonInfo(void *,ushort *,ulong)
0x18010f157  mov     [rbp+57h+var_98], rax
0x18010f15b  jmp     loc_18010F551
0x18010f160  mov     [rbp+57h+var_48], r14
0x18010f164  mov     rcx, r14; pbstr
0x18010f167  call    cs:__imp_SysStringLen
0x18010f16e  nop     dword ptr [rax+rax+00h]
0x18010f173  test    eax, eax
0x18010f175  jnz     short loc_18010F180
0x18010f177  mov     [rbp+57h+var_A0], r13d
0x18010f17b  jmp     loc_18010F551
0x18010f180  lea     rax, [rbp+57h+var_98]
0x18010f184  mov     qword ptr [rbp+57h+var_80], rax
0x18010f188  lea     rax, [rbp+57h+pPrinterName]
0x18010f18c  mov     qword ptr [rbp+57h+var_80+8], rax
0x18010f190  lea     rax, [rbp+57h+var_48]
0x18010f194  mov     qword ptr [rbp+57h+var_70], rax
0x18010f198  lea     rax, [rbp+57h+var_A0]
0x18010f19c  mov     qword ptr [rbp+57h+var_70+8], rax
0x18010f1a0  mov     [rbp+57h+arg_8], r13b
0x18010f1a4  lea     r8, [rbp+57h+arg_8]
0x18010f1a8  xor     edx, edx
0x18010f1aa  mov     rcx, [rbp+57h+pPrinterName]
0x18010f1ae  call    cs:__imp_IsModernPrinter
0x18010f1b5  nop     dword ptr [rax+rax+00h]
0x18010f1ba  test    eax, eax
0x18010f1bc  js      short loc_18010F232
0x18010f1be  cmp     [rbp+57h+arg_8], r13b
0x18010f1c2  jz      short loc_18010F232
0x18010f1c4  mov     dword ptr [rbp+57h+hModule], r13d
0x18010f1c8  lea     rdx, [rbp+57h+hModule]; int *
0x18010f1cc  lea     rcx, [rbp+57h+hLibModule]; this
0x18010f1d0  call    ??0RevertToPrinterRAII@@QEAA@PEAJ@Z; RevertToPrinterRAII::RevertToPrinterRAII(long *)
0x18010f1d5  nop
0x18010f1d6  mov     eax, dword ptr [rbp+57h+hModule]
0x18010f1d9  test    eax, eax
0x18010f1db  js      short loc_18010F1E9
0x18010f1dd  lea     rcx, [rbp+57h+var_80]
0x18010f1e1  call    _lambda_97e360d8fabff85a69a15679bfe5c655___operator__
0x18010f1e6  nop
0x18010f1e7  jmp     short loc_18010F200
0x18010f1e9  movzx   r8d, ax
0x18010f1ed  lea     rdx, aFailedToRevert; "Failed to revert to printer self: %d\n"
0x18010f1f4  mov     rcx, rbx; char *
0x18010f1f7  call    ?WriteDbgTraceWarning@DriverUiTelemetry@DriverUi@@SAXPEADPEAGZZ; DriverUi::DriverUiTelemetry::WriteDbgTraceWarning(char *,ushort *,...)
0x18010f1fc  mov     [rbp+57h+var_A0], r13d
0x18010f200  mov     rax, [rbp+57h+var_50]
0x18010f204  test    rax, rax
0x18010f207  jz      short loc_18010F217
0x18010f209  mov     rcx, [rbp+57h+var_58]
0x18010f20d  test    rcx, rcx
0x18010f210  jz      short loc_18010F217
0x18010f212  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18010f217  mov     rcx, [rbp+57h+hLibModule]; hLibModule
0x18010f21b  test    rcx, rcx
0x18010f21e  jz      short loc_18010F22D
0x18010f220  call    cs:__imp_FreeLibrary
0x18010f227  nop     dword ptr [rax+rax+00h]
0x18010f22c  nop
0x18010f22d  jmp     loc_18010F551
0x18010f232  lea     rcx, [rbp+57h+var_80]
0x18010f236  call    _lambda_97e360d8fabff85a69a15679bfe5c655___operator__
0x18010f23b  jmp     loc_18010F551
0x18010f240  xor     r8d, r8d; pDefault
0x18010f243  lea     rdx, [rbp+57h+phPrinter]; phPrinter
0x18010f247  mov     rcx, [rbp+57h+pPrinterName]; pPrinterName
0x18010f24b  call    cs:__imp_OpenPrinterW
0x18010f252  nop     dword ptr [rax+rax+00h]
0x18010f257  test    eax, eax
0x18010f259  jnz     short loc_18010F286
0x18010f25b  call    cs:__imp_GetLastError
0x18010f262  nop     dword ptr [rax+rax+00h]
0x18010f267  mov     r9d, eax
0x18010f26a  mov     r8, [rbp+57h+pPrinterName]
0x18010f26e  lea     rdx, aOpenprinterWsF; "OpenPrinter '%ws' failed: %d\n"
0x18010f275  mov     rcx, rbx; char *
0x18010f278  call    ?WriteDbgTraceWarning@DriverUiTelemetry@DriverUi@@SAXPEADPEAGZZ; DriverUi::DriverUiTelemetry::WriteDbgTraceWarning(char *,ushort *,...)
0x18010f27d  mov     [rbp+57h+phPrinter], r13
0x18010f281  jmp     loc_18010F551
0x18010f286  lea     r8, aExternalfontfi; "ExternalFontFile"
0x18010f28d  lea     rdx, [rbp+57h+var_80]; this
0x18010f291  mov     rcx, [rbp+57h+phPrinter]; hPrinter
0x18010f295  call    ?_BPrepareToCopyCachedFile@UniDrvUI@@YAHPEAXPEAU_CACHEDFILE@1@PEAG@Z; UniDrvUI::_BPrepareToCopyCachedFile(void *,UniDrvUI::_CACHEDFILE *,ushort *)
0x18010f29a  lea     rdx, [rbp+57h+hModule]
0x18010f29e  lea     rcx, aSpoolssDll; "spoolss.dll"
0x18010f2a5  call    LoadLibraryFromSystemDirectory
0x18010f2aa  mov     rbx, [rbp+57h+hModule]
0x18010f2ae  test    eax, eax
0x18010f2b0  js      loc_18010F37B
0x18010f2b6  lea     rdx, aReverttoprinte; "RevertToPrinterSelf"
0x18010f2bd  mov     rcx, rbx; hModule
0x18010f2c0  call    cs:__imp_GetProcAddress
0x18010f2c7  nop     dword ptr [rax+rax+00h]
0x18010f2cc  mov     rsi, rax
0x18010f2cf  test    rax, rax
0x18010f2d2  jz      loc_18010F37B
0x18010f2d8  lea     rdx, aImpersonatepri; "ImpersonatePrinterClient"
0x18010f2df  mov     rcx, rbx; hModule
0x18010f2e2  call    cs:__imp_GetProcAddress
0x18010f2e9  nop     dword ptr [rax+rax+00h]
0x18010f2ee  mov     rdi, rax
0x18010f2f1  test    rax, rax
0x18010f2f4  jz      loc_18010F37B
0x18010f2fa  mov     rax, rsi
0x18010f2fd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18010f302  mov     rsi, rax
0x18010f305  mov     r8d, 8000h; unsigned __int16 *
0x18010f30b  mov     rdx, [rbp+57h+pPrinterName]; void *
0x18010f30f  mov     rcx, [rbp+57h+phPrinter]; this
0x18010f313  call    ?PLoadCommonInfo@UniDrvUI@@YAPEAU_COMMONINFO@1@PEAXPEAGK@Z; UniDrvUI::PLoadCommonInfo(void *,ushort *,ulong)
0x18010f318  mov     [rbp+57h+var_98], rax
0x18010f31c  lea     rdx, [rbp+57h+var_80]; struct UniDrvUI::_COMMONINFO *
0x18010f320  call    ?_BCopyCachedFile@UniDrvUI@@YAHPEAU_COMMONINFO@1@PEAU_CACHEDFILE@1@@Z; UniDrvUI::_BCopyCachedFile(UniDrvUI::_COMMONINFO *,UniDrvUI::_CACHEDFILE *)
0x18010f325  lea     rcx, [rbp+57h+var_80]; this
0x18010f329  call    ?_VDisposeCachedFileInfo@PSUI@@YAXPEAU_CACHEDFILE@1@@Z; PSUI::_VDisposeCachedFileInfo(PSUI::_CACHEDFILE *)
0x18010f32e  test    rsi, rsi
0x18010f331  jz      short loc_18010F367
0x18010f333  mov     rcx, rsi
0x18010f336  mov     rax, rdi
0x18010f339  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18010f33e  mov     [rbp+57h+var_A0], eax
0x18010f341  test    eax, eax
0x18010f343  jnz     short loc_18010F367
0x18010f345  call    cs:__imp_GetLastError
0x18010f34c  nop     dword ptr [rax+rax+00h]
0x18010f351  mov     r8d, eax
0x18010f354  lea     rdx, aPrintereventIm; "PrinterEvent-ImpersonatePrinterClient f"...
0x18010f35b  lea     rcx, aUnidrvuiDrvpri; "UniDrvUI::DrvPrinterEvent"
0x18010f362  call    ?WriteDbgTraceWarning@DriverUiTelemetry@DriverUi@@SAXPEADPEAGZZ; DriverUi::DriverUiTelemetry::WriteDbgTraceWarning(char *,ushort *,...)
0x18010f367  mov     rcx, rbx; hLibModule
0x18010f36a  call    cs:__imp_FreeLibrary
0x18010f371  nop     dword ptr [rax+rax+00h]
0x18010f376  jmp     loc_18010F551
0x18010f37b  call    cs:__imp_GetLastError
0x18010f382  nop     dword ptr [rax+rax+00h]
0x18010f387  mov     r8d, eax
0x18010f38a  lea     rdx, aCouldnTLoadSpo; "Couldn't load spoolss.dll: %d\n"
0x18010f391  lea     rcx, aUnidrvuiDrvpri; "UniDrvUI::DrvPrinterEvent"
0x18010f398  call    ?WriteDbgTraceWarning@DriverUiTelemetry@DriverUi@@SAXPEADPEAGZZ; DriverUi::DriverUiTelemetry::WriteDbgTraceWarning(char *,ushort *,...)
0x18010f39d  test    rbx, rbx
0x18010f3a0  jz      short loc_18010F3B1
0x18010f3a2  mov     rcx, rbx; hLibModule
0x18010f3a5  call    cs:__imp_FreeLibrary
0x18010f3ac  nop     dword ptr [rax+rax+00h]
0x18010f3b1  lea     rcx, [rbp+57h+var_80]; this
0x18010f3b5  call    ?_VDisposeCachedFileInfo@PSUI@@YAXPEAU_CACHEDFILE@1@@Z; PSUI::_VDisposeCachedFileInfo(PSUI::_CACHEDFILE *)
0x18010f3ba  jmp     loc_18010F551
0x18010f3bf  mov     r8d, 0Ch; unsigned __int16 *
0x18010f3c5  mov     rdx, [rbp+57h+pPrinterName]; void *
0x18010f3c9  xor     ecx, ecx; this
0x18010f3cb  call    ?PLoadCommonInfo@UniDrvUI@@YAPEAU_COMMONINFO@1@PEAXPEAGK@Z; UniDrvUI::PLoadCommonInfo(void *,ushort *,ulong)
0x18010f3d0  mov     rcx, rax; this
0x18010f3d3  mov     [rbp+57h+var_98], rax
0x18010f3d7  test    rax, rax
0x18010f3da  jz      loc_18010F551
0x18010f3e0  call    ?BInitOrUpgradePrinterProperties@UniDrvUI@@YAHPEAU_COMMONINFO@1@@Z; UniDrvUI::BInitOrUpgradePrinterProperties(UniDrvUI::_COMMONINFO *)
0x18010f3e5  mov     rcx, [rbp+57h+var_98]; this
0x18010f3e9  call    ?BFillCommonInfoPrinterData@UniDrvUI@@YAHPEAU_COMMONINFO@1@@Z; UniDrvUI::BFillCommonInfoPrinterData(UniDrvUI::_COMMONINFO *)
0x18010f3ee  test    eax, eax
0x18010f3f0  jz      loc_18010F47D
0x18010f3f6  mov     rcx, [rbp+57h+var_98]; this
0x18010f3fa  call    ?BCombineCommonInfoOptionsArray@UniDrvUI@@YAHPEAU_COMMONINFO@1@@Z; UniDrvUI::BCombineCommonInfoOptionsArray(UniDrvUI::_COMMONINFO *)
0x18010f3ff  test    eax, eax
0x18010f401  jz      short loc_18010F47D
0x18010f403  mov     rcx, [rbp+57h+var_98]
0x18010f407  mov     rax, [rcx+48h]
0x18010f40b  cmp     [rax+138h], r13d
0x18010f412  jz      short loc_18010F424
0x18010f414  mov     rdx, rcx; unsigned __int16 *
0x18010f417  mov     rcx, [rbp+57h+pPrinterName]; this
0x18010f41b  call    ?InitBidiAtPrinterInstall@UniDrvUI@@YAHPEAGPEAU_COMMONINFO@1@@Z; UniDrvUI::InitBidiAtPrinterInstall(ushort *,UniDrvUI::_COMMONINFO *)
0x18010f420  mov     rcx, [rbp+57h+var_98]
0x18010f424  mov     rax, [rcx+30h]
0x18010f428  test    dword ptr [rax+18h], 100000h
0x18010f42f  jz      short loc_18010F45E
0x18010f431  mov     r9d, edi
0x18010f434  lea     r8, Filename
0x18010f43b  lea     rdx, aTrayformqueuep; "TrayFormQueueProp"
0x18010f442  mov     rcx, [rcx+20h]; hPrinter
0x18010f446  call    BSetPrinterDataString
0x18010f44b  test    eax, eax
0x18010f44d  jnz     short loc_18010F45E
0x18010f44f  lea     rdx, aUnableToInitia; "Unable to initialize the form-tray data"...
0x18010f456  mov     rcx, rbx; char *
0x18010f459  call    ?WriteDbgTraceWarning@DriverUiTelemetry@DriverUi@@SAXPEADPEAGZZ; DriverUi::DriverUiTelemetry::WriteDbgTraceWarning(char *,ushort *,...)
0x18010f45e  call    bIsOnWin8AndAbove
0x18010f463  test    eax, eax
0x18010f465  jnz     loc_18010F551
0x18010f46b  mov     rcx, [rbp+57h+var_98]
0x18010f46f  mov     rcx, [rcx+20h]; this
0x18010f473  call    ?VNotifyDSOfUpdate@UniDrvUI@@YAXPEAX@Z; UniDrvUI::VNotifyDSOfUpdate(void *)
0x18010f478  jmp     loc_18010F551
0x18010f47d  lea     rdx, aPrinterEventIn; "PRINTER_EVENT_INITIALIZE failed. Unable"...
0x18010f484  mov     rcx, rbx; char *
0x18010f487  call    ?WriteDbgTraceWarning@DriverUiTelemetry@DriverUi@@SAXPEADPEAGZZ; DriverUi::DriverUiTelemetry::WriteDbgTraceWarning(char *,ushort *,...)
0x18010f48c  jmp     loc_18010F551
0x18010f491  xor     r8d, r8d; pDefault
0x18010f494  lea     rdx, [rbp+57h+phPrinter]; phPrinter
0x18010f498  mov     rcx, [rbp+57h+pPrinterName]; pPrinterName
0x18010f49c  call    cs:__imp_OpenPrinterW
0x18010f4a3  nop     dword ptr [rax+rax+00h]
0x18010f4a8  test    eax, eax
0x18010f4aa  jz      loc_18010F25B
0x18010f4b0  mov     r8d, edi; unsigned __int16 *
0x18010f4b3  mov     rdx, [rbp+57h+pPrinterName]; void *
0x18010f4b7  xor     ecx, ecx; this
0x18010f4b9  call    ?PLoadCommonInfo@UniDrvUI@@YAPEAU_COMMONINFO@1@PEAXPEAGK@Z; UniDrvUI::PLoadCommonInfo(void *,ushort *,ulong)
0x18010f4be  mov     [rbp+57h+var_98], rax
0x18010f4c2  xor     r8d, r8d
0x18010f4c5  lea     rdx, aExternalfontfi; "ExternalFontFile"
0x18010f4cc  mov     rcx, [rbp+57h+phPrinter]; hPrinter
0x18010f4d0  call    PtstrGetPrinterDataString
0x18010f4d5  mov     rsi, rax
0x18010f4d8  test    rax, rax
0x18010f4db  jz      short loc_18010F551
0x18010f4dd  mov     rdi, r13
0x18010f4e0  mov     rbx, r13
0x18010f4e3  cmp     [rax], r13w
0x18010f4e7  jz      short loc_18010F51A
0x18010f4e9  xor     ecx, ecx; pName
0x18010f4eb  call    ?PGetFileDirectory@UniDrvUI@@YAPEAGPEAG@Z; UniDrvUI::PGetFileDirectory(ushort *)
0x18010f4f0  mov     rdi, rax
0x18010f4f3  test    rax, rax
0x18010f4f6  jz      short loc_18010F51A
0x18010f4f8  mov     rdx, rsi; Str
0x18010f4fb  mov     rcx, rax; pszSrc
0x18010f4fe  call    ?PConcatFilename@UniDrvUI@@YAPEAGPEAG0@Z; UniDrvUI::PConcatFilename(ushort *,ushort *)
0x18010f503  mov     rbx, rax
0x18010f506  test    rax, rax
0x18010f509  jz      short loc_18010F51A
0x18010f50b  mov     rcx, rax; lpFileName
0x18010f50e  call    cs:__imp_DeleteFileW
0x18010f515  nop     dword ptr [rax+rax+00h]
0x18010f51a  mov     rcx, rsi; hMem
0x18010f51d  call    cs:__imp_LocalFree
0x18010f524  nop     dword ptr [rax+rax+00h]
0x18010f529  test    rdi, rdi
0x18010f52c  jz      short loc_18010F53D
0x18010f52e  mov     rcx, rdi; hMem
0x18010f531  call    cs:__imp_LocalFree
0x18010f538  nop     dword ptr [rax+rax+00h]
0x18010f53d  test    rbx, rbx
0x18010f540  jz      short loc_18010F551
0x18010f542  mov     rcx, rbx; hMem
0x18010f545  call    cs:__imp_LocalFree
0x18010f54c  nop     dword ptr [rax+rax+00h]
0x18010f551  mov     rcx, [rbp+57h+var_98]
0x18010f555  test    rcx, rcx
0x18010f558  jz      loc_18010F718
0x18010f55e  cmp     [rbp+57h+var_A0], r13d
0x18010f562  jz      loc_18010F70D
0x18010f568  cmp     [rcx+70h], r13
0x18010f56c  jz      short loc_18010F575
0x18010f56e  or      dword ptr [rcx+90h], 0Ch
0x18010f575  mov     rax, [rbp+57h+var_98]
0x18010f579  mov     rcx, [rax+50h]
  ... truncated ...
```
