# PSUI::DrvPrinterEvent(ushort *,int,ulong,__int64)

- ea: `0x180137dc4`
- end: `0x18013837a`
- name: `?DrvPrinterEvent@PSUI@@YAHPEAGHK_J@Z`
- size: `1462`
- prototype: `__int64 __fastcall(WCHAR *this, unsigned __int16 *, unsigned int, OLECHAR *)`
- caller_count: `1`
- callee_count: `20`
- tags: `authz_impersonation, loader_planting, installer_update, broker_com_uri`

## callers

- `0x180030a20`

## callees

- `0x180006268`
- `0x180107214`
- `0x180108e2c`
- `0x180110010`
- `0x180136728`
- `0x1801374d8`
- `0x180137dc4`
- `0x180138478`
- `0x18013b280`
- `0x18013b73c`
- `0x18013c480`
- `0x18013dcf0`
- `0x18013df30`
- `0x18014cf54`
- `0x180150158`
- `0x1801513b8`
- `0x18015178c`
- `0x180155868`
- `0x180157d60`
- `0x1801cb010`

## import_xrefs

- `KERNEL32!GetProcAddress` at `0x180137fb6`
- `KERNEL32!GetProcAddress` at `0x180137fd8`
- `KERNEL32!GetProcAddress` at `0x180137fb6`
- `KERNEL32!GetProcAddress` at `0x180137fd8`
- `KERNEL32!FreeLibrary` at `0x180137f16`
- `KERNEL32!FreeLibrary` at `0x180138060`
- `KERNEL32!FreeLibrary` at `0x18013809b`
- `KERNEL32!FreeLibrary` at `0x180137f16`
- `KERNEL32!FreeLibrary` at `0x180138060`
- `KERNEL32!FreeLibrary` at `0x18013809b`
- `KERNEL32!GetLastError` at `0x180137f51`
- `KERNEL32!GetLastError` at `0x18013803b`
- `KERNEL32!GetLastError` at `0x180138071`
- `KERNEL32!GetLastError` at `0x1801382a8`
- `KERNEL32!GetLastError` at `0x180137f51`
- `KERNEL32!GetLastError` at `0x18013803b`
- `KERNEL32!GetLastError` at `0x180138071`
- `KERNEL32!GetLastError` at `0x1801382a8`
- `OLEAUT32!__imp_SysStringLen` at `0x180137e5d`
- `OLEAUT32!__imp_SysStringLen` at `0x180137e5d`
- `WINSPOOL!ClosePrinter` at `0x18013834f`
- `WINSPOOL!ClosePrinter` at `0x18013834f`
- `WINSPOOL!OpenPrinterW` at `0x180137f41`
- `WINSPOOL!OpenPrinterW` at `0x180137f41`
- `IppCommon!IsModernPrinter` at `0x180137ea4`
- `IppCommon!IsModernPrinter` at `0x180137ea4`

## string_xrefs

- `0x180137f94`: `spoolss.dll`
- `0x180137fce`: `ImpersonatePrinterClient`
- `0x180137f64`: `OpenPrinter '%ws' failed: %d\n`
- `0x180138080`: `Couldn't load spoolss.dll: %d\n`
- `0x18013804a`: `PrinterEvent-ImpersonatePrinterClient failed: %d\n`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall PSUI::DrvPrinterEvent(WCHAR *this, unsigned __int16 *a2, unsigned int a3, OLECHAR *a4)
{
  unsigned int v6; // r14d
  struct PSUI::_COMMONINFO *v7; // rdx
  __int64 v8; // r9
  __int64 v9; // rdx
  __int64 v10; // r8
  unsigned int v11; // r9d
  __int64 v12; // rdx
  __int64 v13; // r8
  unsigned int v14; // r9d
  DWORD v15; // eax
  int v16; // eax
  HMODULE v17; // rbx
  __int64 (*ProcAddress)(void); // rsi
  FARPROC v19; // rdi
  __int64 v20; // rsi
  PSUI *v21; // rcx
  struct PSUI::_CACHEDFILE *v22; // r8
  struct PSUI::_CACHEDFILE *v23; // rdx
  DWORD LastError; // eax
  DWORD v25; // eax
  struct PSUI::_CACHEDFILE *v26; // rdx
  PSUI *v27; // rcx
  struct PSUI::_COMMONINFO *v28; // rdx
  struct PSUI::_COMMONINFO *v29; // rdx
  struct PSUI::_COMMONINFO *v30; // r8
  PSUI *v31; // rcx
  __int64 v32; // rcx
  __int64 v33; // rbx
  int v34; // edi
  __int64 v35; // r10
  __int64 v36; // r8
  __int64 v37; // r11
  __int64 v38; // rcx
  int v39; // eax
  unsigned int (__fastcall *v40)(LPWSTR, _QWORD, _QWORD, OLECHAR *); // rax
  DWORD v41; // eax
  unsigned int v43; // [rsp+38h] [rbp-49h] BYREF
  PSUI *v44; // [rsp+40h] [rbp-41h] BYREF
  HMODULE hModule; // [rsp+48h] [rbp-39h] BYREF
  HANDLE phPrinter; // [rsp+50h] [rbp-31h] BYREF
  __int64 v47; // [rsp+58h] [rbp-29h] BYREF
  __int128 v48; // [rsp+60h] [rbp-21h]
  unsigned int *v49; // [rsp+70h] [rbp-11h]
  HMODULE hLibModule[2]; // [rsp+78h] [rbp-9h] BYREF
  void (*v51)(void); // [rsp+88h] [rbp+7h]
  _QWORD v52[9]; // [rsp+90h] [rbp+Fh] BYREF
  LPWSTR pPrinterName; // [rsp+E8h] [rbp+67h] BYREF
  char v54; // [rsp+F0h] [rbp+6Fh] BYREF

  pPrinterName = this;
  v52[1] = -2;
  v6 = (unsigned int)a2;
  hModule = 0;
  v44 = 0;
  phPrinter = 0;
  v43 = 1;
  DriverUi::DriverUiTelemetry::WriteDbgTraceInfo(
    "PSUI::DrvPrinterEvent",
    L"Entering DrvPrinterEvent: %d ...\n",
    (unsigned int)a2);
  switch ( v6 )
  {
    case 3u:
      v27 = PSUI::PLoadCommonInfo(0, pPrinterName, (unsigned __int16 *)0xC);
      v44 = v27;
      if ( v27 )
      {
        PSUI::BInitOrUpgradePrinterProperties(v27, v7);
        if ( (unsigned int)PSUI::BFillCommonInfoPrinterData(v44, v28)
          && (unsigned int)PSUI::BCombineCommonInfoOptionsArray(v44, v29) )
        {
          v31 = v44;
          if ( *(_DWORD *)(*((_QWORD *)v44 + 9) + 312LL) )
          {
            PSUI::InitBidiAtPrinterInstall((PSUI *)pPrinterName, (unsigned __int16 *)v44, v30);
            v31 = v44;
          }
          if ( (*(_DWORD *)(*((_QWORD *)v31 + 6) + 24LL) & 0x100000) != 0
            && !BSetPrinterDataString(*((HANDLE *)v31 + 4), (WCHAR *)L"TrayFormQueueProp", (BYTE *)&Filename, 1u) )
          {
            DriverUi::DriverUiTelemetry::WriteDbgTraceWarning(
              "PSUI::DrvPrinterEvent",
              L"Unable to initialize the form-tray database queue property.\n");
          }
          if ( !bIsOnWin8AndAbove() )
            PSUI::VNotifyDSOfUpdate(*((PSUI **)v44 + 4), v7);
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
        v48 = 0;
        v49 = 0;
        v47 = -1;
        v16 = LoadLibraryFromSystemDirectory(L"spoolss.dll", &hModule);
        v17 = hModule;
        if ( v16 >= 0
          && (ProcAddress = GetProcAddress(hModule, "RevertToPrinterSelf")) != 0
          && (v19 = GetProcAddress(v17, "ImpersonatePrinterClient")) != 0 )
        {
          v20 = ProcAddress();
          v44 = PSUI::PLoadCommonInfo((PSUI *)phPrinter, pPrinterName, (unsigned __int16 *)0x8000);
          PSUI::_BCopyCachedFile(v21, (struct PSUI::_COMMONINFO *)&v47, v22);
          PSUI::_VDisposeCachedFileInfo((HANDLE *)&v47, v23);
          if ( v20 )
          {
            v43 = ((__int64 (__fastcall *)(__int64))v19)(v20);
            if ( !v43 )
            {
              LastError = GetLastError();
              DriverUi::DriverUiTelemetry::WriteDbgTraceWarning(
                "PSUI::DrvPrinterEvent",
                L"PrinterEvent-ImpersonatePrinterClient failed: %d\n",
                LastError);
            }
          }
          FreeLibrary(v17);
        }
        else
        {
          v25 = GetLastError();
          DriverUi::DriverUiTelemetry::WriteDbgTraceWarning(
            "PSUI::DrvPrinterEvent",
            L"Couldn't load spoolss.dll: %d\n",
            v25);
          if ( v17 )
            FreeLibrary(v17);
          PSUI::_VDisposeCachedFileInfo((HANDLE *)&v47, v26);
        }
      }
      else
      {
        v15 = GetLastError();
        DriverUi::DriverUiTelemetry::WriteDbgTraceWarning(
          "PSUI::DrvPrinterEvent",
          L"OpenPrinter '%ws' failed: %d\n",
          pPrinterName,
          v15);
        phPrinter = 0;
      }
      break;
    case 8u:
      v52[0] = a4;
      if ( SysStringLen(a4) )
      {
        v47 = (__int64)&v44;
        *(_QWORD *)&v48 = &pPrinterName;
        *((_QWORD *)&v48 + 1) = v52;
        v49 = &v43;
        v54 = 0;
        if ( (int)IsModernPrinter(pPrinterName, 0, &v54) >= 0 && v54 )
        {
          LODWORD(hModule) = 0;
          RevertToPrinterRAII::RevertToPrinterRAII((RevertToPrinterRAII *)hLibModule, (int *)&hModule);
          if ( (int)hModule < 0 )
          {
            DriverUi::DriverUiTelemetry::WriteDbgTraceWarning(
              "PSUI::DrvPrinterEvent",
              L"Failed to revert to printer self: %d\n",
              (unsigned __int16)hModule);
            v43 = 0;
          }
          else
          {
            lambda_7709aa7672fa7c7d1651f7628bf4b04b_::operator()((struct PSUI::_COMMONINFO ***)&v47, v12, v13, v14);
          }
          if ( v51 && hLibModule[1] )
            v51();
          if ( hLibModule[0] )
            FreeLibrary(hLibModule[0]);
        }
        else
        {
          lambda_7709aa7672fa7c7d1651f7628bf4b04b_::operator()((struct PSUI::_COMMONINFO ***)&v47, v9, v10, v11);
        }
      }
      else
      {
        v43 = 0;
      }
      break;
    default:
      v44 = PSUI::PLoadCommonInfo(0, pPrinterName, (unsigned __int16 *)1);
      break;
  }
  if ( v44 )
  {
    if ( v43 )
    {
      if ( *((_QWORD *)v44 + 14) )
        *((_DWORD *)v44 + 36) |= 0xCu;
      v32 = *((_QWORD *)v44 + 10);
      v33 = v32 + 24;
      v34 = *(_DWORD *)(v32 + 8);
      if ( v34 )
      {
        v8 = *(_QWORD *)IID_IPrintOemUI.Data4;
        v35 = *(_QWORD *)&IID_IPrintOemUI.Data1;
        v36 = *(_QWORD *)IID_IPrintOemUI2.Data4;
        v37 = *(_QWORD *)&IID_IPrintOemUI2.Data1;
        do
        {
          --v34;
          if ( *(_QWORD *)(v33 + 32) )
          {
            v38 = *(_QWORD *)(v33 + 72);
            if ( !v38 )
            {
              if ( (*(_BYTE *)(v33 + 101) & 1) != 0 )
              {
                v40 = *(unsigned int (__fastcall **)(LPWSTR, _QWORD, _QWORD, OLECHAR *))(v33 + 168);
              }
              else
              {
                v40 = (unsigned int (__fastcall *)(LPWSTR, _QWORD, _QWORD, OLECHAR *))PGetOemEntrypointAddress(v33, 8u);
                v8 = *(_QWORD *)IID_IPrintOemUI.Data4;
                v35 = *(_QWORD *)&IID_IPrintOemUI.Data1;
                v36 = *(_QWORD *)IID_IPrintOemUI2.Data4;
                v37 = *(_QWORD *)&IID_IPrintOemUI2.Data1;
              }
              if ( !v40 )
                goto LABEL_65;
              if ( !v40(pPrinterName, v6, a3, a4) )
              {
                v41 = GetLastError();
                DriverUi::DriverUiTelemetry::WriteDbgTraceWarning(
                  "PSUI::DrvPrinterEvent",
                  L"OEMPrinterEvent failed for '%ws': %d\n",
                  *(_QWORD *)(v33 + 8),
                  v41);
                v43 = 0;
              }
LABEL_64:
              v37 = *(_QWORD *)&IID_IPrintOemUI2.Data1;
              v36 = *(_QWORD *)IID_IPrintOemUI2.Data4;
              v35 = *(_QWORD *)&IID_IPrintOemUI.Data1;
              v8 = *(_QWORD *)IID_IPrintOemUI.Data4;
              goto LABEL_65;
            }
            v7 = (struct PSUI::_COMMONINFO *)pPrinterName;
            if ( *(_QWORD *)(v33 + 80) == v35 && *(_QWORD *)(v33 + 88) == v8
              || *(_QWORD *)(v33 + 80) == v37 && *(_QWORD *)(v33 + 88) == v36 )
            {
              v39 = (*(__int64 (__fastcall **)(__int64, LPWSTR, _QWORD, _QWORD, OLECHAR *))(*(_QWORD *)v38 + 96LL))(
                      v38,
                      pPrinterName,
                      v6,
                      a3,
                      a4);
              if ( v39 == -2147467263 )
                goto LABEL_64;
              v8 = *(_QWORD *)IID_IPrintOemUI.Data4;
              v35 = *(_QWORD *)&IID_IPrintOemUI.Data1;
              v36 = *(_QWORD *)IID_IPrintOemUI2.Data4;
              v37 = *(_QWORD *)&IID_IPrintOemUI2.Data1;
            }
            else
            {
              v39 = -2147467262;
            }
            v43 = v39 >= 0;
          }
LABEL_65:
          v33 += 216;
        }
        while ( v34 );
      }
      if ( v43 && (*((_DWORD *)v44 + 36) & 0x100) != 0 )
        v43 = BSavePrinterProperties(
                *((void **)v44 + 4),
                *(_QWORD *)(*((_QWORD *)v44 + 6) + 40LL),
                *((_QWORD *)v44 + 13),
                v8,
                *(_DWORD *)(*((_QWORD *)v44 + 6) + 24LL) & 0x100000);
    }
    PSUI::VFreeCommonInfo(v44, v7);
  }
  else
  {
    v43 = 0;
  }
  if ( phPrinter )
    ClosePrinter(phPrinter);
  return v43;
}

```

## disassembly

```asm
0x180137dc4  mov     rax, rsp
0x180137dc7  mov     [rax+8], rcx
0x180137dcb  push    rbp
0x180137dcc  push    rsi
0x180137dcd  push    rdi
0x180137dce  push    r12
0x180137dd0  push    r13
0x180137dd2  push    r14
0x180137dd4  push    r15
0x180137dd6  lea     rbp, [rax-5Fh]
0x180137dda  sub     rsp, 0A0h
0x180137de1  mov     [rbp+57h+var_40], 0FFFFFFFFFFFFFFFEh
0x180137de9  mov     [rax+18h], rbx
0x180137ded  mov     r15, r9
0x180137df0  mov     r12d, r8d
0x180137df3  mov     r14d, edx
0x180137df6  xor     r13d, r13d
0x180137df9  mov     [rbp+57h+hModule], r13
0x180137dfd  mov     [rbp+57h+var_98], r13
0x180137e01  mov     [rbp+57h+phPrinter], r13
0x180137e05  lea     edi, [r13+1]
0x180137e09  mov     [rbp+57h+var_A0], edi
0x180137e0c  mov     r8d, edx
0x180137e0f  lea     rdx, aEnteringDrvpri; "Entering DrvPrinterEvent: %d ...\n"
0x180137e16  lea     rbx, aPsuiDrvprinter_0; "PSUI::DrvPrinterEvent"
0x180137e1d  mov     rcx, rbx; char *
0x180137e20  call    ?WriteDbgTraceInfo@DriverUiTelemetry@DriverUi@@SAXPEADPEAGZZ; DriverUi::DriverUiTelemetry::WriteDbgTraceInfo(char *,ushort *,...)
0x180137e25  cmp     r14d, 3
0x180137e29  jz      loc_1801380B5
0x180137e2f  cmp     r14d, 5
0x180137e33  jz      loc_180137F36
0x180137e39  cmp     r14d, 8
0x180137e3d  jz      short loc_180137E56
0x180137e3f  mov     r8d, edi; unsigned __int16 *
0x180137e42  mov     rdx, [rbp+57h+pPrinterName]; void *
0x180137e46  xor     ecx, ecx; this
0x180137e48  call    ?PLoadCommonInfo@PSUI@@YAPEAU_COMMONINFO@1@PEAXPEAGK@Z; PSUI::PLoadCommonInfo(void *,ushort *,ulong)
0x180137e4d  mov     [rbp+57h+var_98], rax
0x180137e51  jmp     loc_18013817B
0x180137e56  mov     [rbp+57h+var_48], r15
0x180137e5a  mov     rcx, r15; pbstr
0x180137e5d  call    cs:__imp_SysStringLen
0x180137e64  nop     dword ptr [rax+rax+00h]
0x180137e69  test    eax, eax
0x180137e6b  jnz     short loc_180137E76
0x180137e6d  mov     [rbp+57h+var_A0], r13d
0x180137e71  jmp     loc_18013817B
0x180137e76  lea     rax, [rbp+57h+var_98]
0x180137e7a  mov     [rbp+57h+var_80], rax
0x180137e7e  lea     rax, [rbp+57h+pPrinterName]
0x180137e82  mov     qword ptr [rbp+57h+var_78], rax
0x180137e86  lea     rax, [rbp+57h+var_48]
0x180137e8a  mov     qword ptr [rbp+57h+var_78+8], rax
0x180137e8e  lea     rax, [rbp+57h+var_A0]
0x180137e92  mov     [rbp+57h+var_68], rax
0x180137e96  mov     [rbp+57h+arg_8], r13b
0x180137e9a  lea     r8, [rbp+57h+arg_8]
0x180137e9e  xor     edx, edx
0x180137ea0  mov     rcx, [rbp+57h+pPrinterName]
0x180137ea4  call    cs:__imp_IsModernPrinter
0x180137eab  nop     dword ptr [rax+rax+00h]
0x180137eb0  test    eax, eax
0x180137eb2  js      short loc_180137F28
0x180137eb4  cmp     [rbp+57h+arg_8], r13b
0x180137eb8  jz      short loc_180137F28
0x180137eba  mov     dword ptr [rbp+57h+hModule], r13d
0x180137ebe  lea     rdx, [rbp+57h+hModule]; int *
0x180137ec2  lea     rcx, [rbp+57h+hLibModule]; this
0x180137ec6  call    ??0RevertToPrinterRAII@@QEAA@PEAJ@Z; RevertToPrinterRAII::RevertToPrinterRAII(long *)
0x180137ecb  nop
0x180137ecc  mov     eax, dword ptr [rbp+57h+hModule]
0x180137ecf  test    eax, eax
0x180137ed1  js      short loc_180137EDF
0x180137ed3  lea     rcx, [rbp+57h+var_80]
0x180137ed7  call    _lambda_7709aa7672fa7c7d1651f7628bf4b04b___operator__
0x180137edc  nop
0x180137edd  jmp     short loc_180137EF6
0x180137edf  movzx   r8d, ax
0x180137ee3  lea     rdx, aFailedToRevert; "Failed to revert to printer self: %d\n"
0x180137eea  mov     rcx, rbx; char *
0x180137eed  call    ?WriteDbgTraceWarning@DriverUiTelemetry@DriverUi@@SAXPEADPEAGZZ; DriverUi::DriverUiTelemetry::WriteDbgTraceWarning(char *,ushort *,...)
0x180137ef2  mov     [rbp+57h+var_A0], r13d
0x180137ef6  mov     rax, [rbp+57h+var_50]
0x180137efa  test    rax, rax
0x180137efd  jz      short loc_180137F0D
0x180137eff  mov     rcx, [rbp+57h+var_58]
0x180137f03  test    rcx, rcx
0x180137f06  jz      short loc_180137F0D
0x180137f08  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180137f0d  mov     rcx, [rbp+57h+hLibModule]; hLibModule
0x180137f11  test    rcx, rcx
0x180137f14  jz      short loc_180137F23
0x180137f16  call    cs:__imp_FreeLibrary
0x180137f1d  nop     dword ptr [rax+rax+00h]
0x180137f22  nop
0x180137f23  jmp     loc_18013817B
0x180137f28  lea     rcx, [rbp+57h+var_80]
0x180137f2c  call    _lambda_7709aa7672fa7c7d1651f7628bf4b04b___operator__
0x180137f31  jmp     loc_18013817B
0x180137f36  xor     r8d, r8d; pDefault
0x180137f39  lea     rdx, [rbp+57h+phPrinter]; phPrinter
0x180137f3d  mov     rcx, [rbp+57h+pPrinterName]; pPrinterName
0x180137f41  call    cs:__imp_OpenPrinterW
0x180137f48  nop     dword ptr [rax+rax+00h]
0x180137f4d  test    eax, eax
0x180137f4f  jnz     short loc_180137F7C
0x180137f51  call    cs:__imp_GetLastError
0x180137f58  nop     dword ptr [rax+rax+00h]
0x180137f5d  mov     r9d, eax
0x180137f60  mov     r8, [rbp+57h+pPrinterName]
0x180137f64  lea     rdx, aOpenprinterWsF; "OpenPrinter '%ws' failed: %d\n"
0x180137f6b  mov     rcx, rbx; char *
0x180137f6e  call    ?WriteDbgTraceWarning@DriverUiTelemetry@DriverUi@@SAXPEADPEAGZZ; DriverUi::DriverUiTelemetry::WriteDbgTraceWarning(char *,ushort *,...)
0x180137f73  mov     [rbp+57h+phPrinter], r13
0x180137f77  jmp     loc_18013817B
0x180137f7c  xorps   xmm0, xmm0
0x180137f7f  movdqu  [rbp+57h+var_78], xmm0
0x180137f84  mov     [rbp+57h+var_68], r13
0x180137f88  mov     [rbp+57h+var_80], 0FFFFFFFFFFFFFFFFh
0x180137f90  lea     rdx, [rbp+57h+hModule]
0x180137f94  lea     rcx, aSpoolssDll; "spoolss.dll"
0x180137f9b  call    LoadLibraryFromSystemDirectory
0x180137fa0  mov     rbx, [rbp+57h+hModule]
0x180137fa4  test    eax, eax
0x180137fa6  js      loc_180138071
0x180137fac  lea     rdx, aReverttoprinte; "RevertToPrinterSelf"
0x180137fb3  mov     rcx, rbx; hModule
0x180137fb6  call    cs:__imp_GetProcAddress
0x180137fbd  nop     dword ptr [rax+rax+00h]
0x180137fc2  mov     rsi, rax
0x180137fc5  test    rax, rax
0x180137fc8  jz      loc_180138071
0x180137fce  lea     rdx, aImpersonatepri; "ImpersonatePrinterClient"
0x180137fd5  mov     rcx, rbx; hModule
0x180137fd8  call    cs:__imp_GetProcAddress
0x180137fdf  nop     dword ptr [rax+rax+00h]
0x180137fe4  mov     rdi, rax
0x180137fe7  test    rax, rax
0x180137fea  jz      loc_180138071
0x180137ff0  mov     rax, rsi
0x180137ff3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180137ff8  mov     rsi, rax
0x180137ffb  mov     r8d, 8000h; unsigned __int16 *
0x180138001  mov     rdx, [rbp+57h+pPrinterName]; void *
0x180138005  mov     rcx, [rbp+57h+phPrinter]; this
0x180138009  call    ?PLoadCommonInfo@PSUI@@YAPEAU_COMMONINFO@1@PEAXPEAGK@Z; PSUI::PLoadCommonInfo(void *,ushort *,ulong)
0x18013800e  mov     [rbp+57h+var_98], rax
0x180138012  lea     rdx, [rbp+57h+var_80]; struct PSUI::_COMMONINFO *
0x180138016  call    ?_BCopyCachedFile@PSUI@@YAHPEAU_COMMONINFO@1@PEAU_CACHEDFILE@1@@Z; PSUI::_BCopyCachedFile(PSUI::_COMMONINFO *,PSUI::_CACHEDFILE *)
0x18013801b  lea     rcx, [rbp+57h+var_80]; this
0x18013801f  call    ?_VDisposeCachedFileInfo@PSUI@@YAXPEAU_CACHEDFILE@1@@Z; PSUI::_VDisposeCachedFileInfo(PSUI::_CACHEDFILE *)
0x180138024  test    rsi, rsi
0x180138027  jz      short loc_18013805D
0x180138029  mov     rcx, rsi
0x18013802c  mov     rax, rdi
0x18013802f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180138034  mov     [rbp+57h+var_A0], eax
0x180138037  test    eax, eax
0x180138039  jnz     short loc_18013805D
0x18013803b  call    cs:__imp_GetLastError
0x180138042  nop     dword ptr [rax+rax+00h]
0x180138047  mov     r8d, eax
0x18013804a  lea     rdx, aPrintereventIm; "PrinterEvent-ImpersonatePrinterClient f"...
0x180138051  lea     rcx, aPsuiDrvprinter_0; "PSUI::DrvPrinterEvent"
0x180138058  call    ?WriteDbgTraceWarning@DriverUiTelemetry@DriverUi@@SAXPEADPEAGZZ; DriverUi::DriverUiTelemetry::WriteDbgTraceWarning(char *,ushort *,...)
0x18013805d  mov     rcx, rbx; hLibModule
0x180138060  call    cs:__imp_FreeLibrary
0x180138067  nop     dword ptr [rax+rax+00h]
0x18013806c  jmp     loc_18013817B
0x180138071  call    cs:__imp_GetLastError
0x180138078  nop     dword ptr [rax+rax+00h]
0x18013807d  mov     r8d, eax
0x180138080  lea     rdx, aCouldnTLoadSpo; "Couldn't load spoolss.dll: %d\n"
0x180138087  lea     rcx, aPsuiDrvprinter_0; "PSUI::DrvPrinterEvent"
0x18013808e  call    ?WriteDbgTraceWarning@DriverUiTelemetry@DriverUi@@SAXPEADPEAGZZ; DriverUi::DriverUiTelemetry::WriteDbgTraceWarning(char *,ushort *,...)
0x180138093  test    rbx, rbx
0x180138096  jz      short loc_1801380A7
0x180138098  mov     rcx, rbx; hLibModule
0x18013809b  call    cs:__imp_FreeLibrary
0x1801380a2  nop     dword ptr [rax+rax+00h]
0x1801380a7  lea     rcx, [rbp+57h+var_80]; this
0x1801380ab  call    ?_VDisposeCachedFileInfo@PSUI@@YAXPEAU_CACHEDFILE@1@@Z; PSUI::_VDisposeCachedFileInfo(PSUI::_CACHEDFILE *)
0x1801380b0  jmp     loc_18013817B
0x1801380b5  mov     r8d, 0Ch; unsigned __int16 *
0x1801380bb  mov     rdx, [rbp+57h+pPrinterName]; void *
0x1801380bf  xor     ecx, ecx; this
0x1801380c1  call    ?PLoadCommonInfo@PSUI@@YAPEAU_COMMONINFO@1@PEAXPEAGK@Z; PSUI::PLoadCommonInfo(void *,ushort *,ulong)
0x1801380c6  mov     rcx, rax; this
0x1801380c9  mov     [rbp+57h+var_98], rax
0x1801380cd  test    rax, rax
0x1801380d0  jz      loc_18013817B
0x1801380d6  call    ?BInitOrUpgradePrinterProperties@PSUI@@YAHPEAU_COMMONINFO@1@@Z; PSUI::BInitOrUpgradePrinterProperties(PSUI::_COMMONINFO *)
0x1801380db  mov     rcx, [rbp+57h+var_98]; this
0x1801380df  call    ?BFillCommonInfoPrinterData@PSUI@@YAHPEAU_COMMONINFO@1@@Z; PSUI::BFillCommonInfoPrinterData(PSUI::_COMMONINFO *)
0x1801380e4  test    eax, eax
0x1801380e6  jz      loc_18013816C
0x1801380ec  mov     rcx, [rbp+57h+var_98]; this
0x1801380f0  call    ?BCombineCommonInfoOptionsArray@PSUI@@YAHPEAU_COMMONINFO@1@@Z; PSUI::BCombineCommonInfoOptionsArray(PSUI::_COMMONINFO *)
0x1801380f5  test    eax, eax
0x1801380f7  jz      short loc_18013816C
0x1801380f9  mov     rcx, [rbp+57h+var_98]
0x1801380fd  mov     rax, [rcx+48h]
0x180138101  cmp     [rax+138h], r13d
0x180138108  jz      short loc_18013811A
0x18013810a  mov     rdx, rcx; unsigned __int16 *
0x18013810d  mov     rcx, [rbp+57h+pPrinterName]; this
0x180138111  call    ?InitBidiAtPrinterInstall@PSUI@@YAHPEAGPEAU_COMMONINFO@1@@Z; PSUI::InitBidiAtPrinterInstall(ushort *,PSUI::_COMMONINFO *)
0x180138116  mov     rcx, [rbp+57h+var_98]
0x18013811a  mov     rax, [rcx+30h]
0x18013811e  test    dword ptr [rax+18h], 100000h
0x180138125  jz      short loc_180138154
0x180138127  mov     r9d, edi
0x18013812a  lea     r8, Filename
0x180138131  lea     rdx, aTrayformqueuep; "TrayFormQueueProp"
0x180138138  mov     rcx, [rcx+20h]; hPrinter
0x18013813c  call    BSetPrinterDataString
0x180138141  test    eax, eax
0x180138143  jnz     short loc_180138154
0x180138145  lea     rdx, aUnableToInitia; "Unable to initialize the form-tray data"...
0x18013814c  mov     rcx, rbx; char *
0x18013814f  call    ?WriteDbgTraceWarning@DriverUiTelemetry@DriverUi@@SAXPEADPEAGZZ; DriverUi::DriverUiTelemetry::WriteDbgTraceWarning(char *,ushort *,...)
0x180138154  call    bIsOnWin8AndAbove
0x180138159  test    eax, eax
0x18013815b  jnz     short loc_18013817B
0x18013815d  mov     rcx, [rbp+57h+var_98]
0x180138161  mov     rcx, [rcx+20h]; this
0x180138165  call    ?VNotifyDSOfUpdate@PSUI@@YAXPEAX@Z; PSUI::VNotifyDSOfUpdate(void *)
0x18013816a  jmp     short loc_18013817B
0x18013816c  lea     rdx, aPrinterEventIn; "PRINTER_EVENT_INITIALIZE failed. Unable"...
0x180138173  mov     rcx, rbx; char *
0x180138176  call    ?WriteDbgTraceWarning@DriverUiTelemetry@DriverUi@@SAXPEADPEAGZZ; DriverUi::DriverUiTelemetry::WriteDbgTraceWarning(char *,ushort *,...)
0x18013817b  mov     rcx, [rbp+57h+var_98]
0x18013817f  test    rcx, rcx
0x180138182  jz      loc_180138342
0x180138188  cmp     [rbp+57h+var_A0], r13d
0x18013818c  jz      loc_180138337
0x180138192  cmp     [rcx+70h], r13
0x180138196  jz      short loc_18013819F
0x180138198  or      dword ptr [rcx+90h], 0Ch
0x18013819f  mov     rax, [rbp+57h+var_98]
0x1801381a3  mov     rcx, [rax+50h]
0x1801381a7  lea     rbx, [rcx+18h]
0x1801381ab  mov     edi, [rcx+8]
0x1801381ae  test    edi, edi
0x1801381b0  jz      loc_1801382FD
0x1801381b6  mov     r9, qword ptr cs:IID_IPrintOemUI.Data4
0x1801381bd  mov     r10, qword ptr cs:IID_IPrintOemUI.Data1
0x1801381c4  mov     r8, qword ptr cs:IID_IPrintOemUI2.Data4
0x1801381cb  mov     r11, qword ptr cs:IID_IPrintOemUI2.Data1
0x1801381d2  dec     edi
0x1801381d4  cmp     [rbx+20h], r13
0x1801381d8  jz      loc_1801382EE
0x1801381de  mov     rcx, [rbx+48h]
0x1801381e2  test    rcx, rcx
0x1801381e5  jz      short loc_180138255
0x1801381e7  mov     rdx, [rbp+57h+pPrinterName]
0x1801381eb  cmp     [rbx+50h], r10
0x1801381ef  jnz     short loc_1801381F7
0x1801381f1  cmp     [rbx+58h], r9
0x1801381f5  jz      short loc_180138203
0x1801381f7  cmp     [rbx+50h], r11
0x1801381fb  jnz     short loc_180138243
0x1801381fd  cmp     [rbx+58h], r8
0x180138201  jnz     short loc_180138243
0x180138203  mov     rax, [rcx]
0x180138206  mov     [rsp+20h], r15
0x18013820b  mov     r9d, r12d
0x18013820e  mov     r8d, r14d
0x180138211  mov     rax, [rax+60h]
0x180138215  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18013821a  cmp     eax, 80004001h
0x18013821f  jz      loc_1801382D2
0x180138225  mov     r9, qword ptr cs:IID_IPrintOemUI.Data4
0x18013822c  mov     r10, qword ptr cs:IID_IPrintOemUI.Data1
0x180138233  mov     r8, qword ptr cs:IID_IPrintOemUI2.Data4
0x18013823a  mov     r11, qword ptr cs:IID_IPrintOemUI2.Data1
0x180138241  jmp     short loc_180138248
0x180138243  mov     eax, 80004002h
0x180138248  not     eax
0x18013824a  shr     eax, 1Fh
0x18013824d  mov     [rbp+57h+var_A0], eax
0x180138250  jmp     loc_1801382EE
0x180138255  test    byte ptr [rbx+65h], 1
0x180138259  jz      short loc_180138264
0x18013825b  mov     rax, [rbx+0A8h]
0x180138262  jmp     short loc_18013828D
0x180138264  mov     edx, 8
0x180138269  mov     rcx, rbx
0x18013826c  call    PGetOemEntrypointAddress
0x180138271  mov     r9, qword ptr cs:IID_IPrintOemUI.Data4
0x180138278  mov     r10, qword ptr cs:IID_IPrintOemUI.Data1
0x18013827f  mov     r8, qword ptr cs:IID_IPrintOemUI2.Data4
0x180138286  mov     r11, qword ptr cs:IID_IPrintOemUI2.Data1
0x18013828d  test    rax, rax
0x180138290  jz      short loc_1801382EE
0x180138292  mov     r9, r15
0x180138295  mov     r8d, r12d
0x180138298  mov     edx, r14d
0x18013829b  mov     rcx, [rbp+57h+pPrinterName]
0x18013829f  call    _guard_dispatch_icall$thunk$10345483385596137414
  ... truncated ...
```
