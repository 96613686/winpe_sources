# UniDrvUI::PLoadCommonInfo(void *,ushort *,ulong)

- ea: `0x1801146b4`
- end: `0x180114a40`
- name: `?PLoadCommonInfo@UniDrvUI@@YAPEAU_COMMONINFO@1@PEAXPEAGK@Z`
- size: `908`
- prototype: `struct UniDrvUI::_COMMONINFO *__fastcall(UniDrvUI *this, WCHAR *, unsigned __int16 *)`
- caller_count: `14`
- callee_count: `14`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x1800fc0d4`
- `0x180109e0c`
- `0x18010b01c`
- `0x18010b490`
- `0x18010bf20`
- `0x18010db18`
- `0x18010ea34`
- `0x18010f0b4`
- `0x18011150c`
- `0x180111908`
- `0x1801139d8`
- `0x1801143f4`
- `0x180116494`
- `0x1801168b8`

## callees

- `0x180018f58`
- `0x180035314`
- `0x180107214`
- `0x180108e2c`
- `0x180114024`
- `0x1801146b4`
- `0x180116080`
- `0x18014f63c`
- `0x18014fa24`
- `0x18014fae0`
- `0x180151098`
- `0x180151750`
- `0x180154838`
- `0x1801558d0`

## import_xrefs

- `KERNEL32!GetLastError` at `0x18011475a`
- `KERNEL32!GetLastError` at `0x1801147fb`
- `KERNEL32!GetLastError` at `0x18011483a`
- `KERNEL32!GetLastError` at `0x1801148e4`
- `KERNEL32!GetLastError` at `0x180114915`
- `KERNEL32!GetLastError` at `0x180114946`
- `KERNEL32!GetLastError` at `0x1801149de`
- `KERNEL32!GetLastError` at `0x18011475a`
- `KERNEL32!GetLastError` at `0x1801147fb`
- `KERNEL32!GetLastError` at `0x18011483a`
- `KERNEL32!GetLastError` at `0x1801148e4`
- `KERNEL32!GetLastError` at `0x180114915`
- `KERNEL32!GetLastError` at `0x180114946`
- `KERNEL32!GetLastError` at `0x1801149de`
- `KERNEL32!LocalFree` at `0x1801147e5`
- `KERNEL32!LocalFree` at `0x1801148a6`
- `KERNEL32!LocalFree` at `0x180114a12`
- `KERNEL32!LocalFree` at `0x180114a26`
- `KERNEL32!LocalFree` at `0x1801147e5`
- `KERNEL32!LocalFree` at `0x1801148a6`
- `KERNEL32!LocalFree` at `0x180114a12`
- `KERNEL32!LocalFree` at `0x180114a26`
- `KERNEL32!LocalAlloc` at `0x1801146e8`
- `KERNEL32!LocalAlloc` at `0x1801146e8`
- `WINSPOOL!OpenPrinterW` at `0x18011474a`
- `WINSPOOL!OpenPrinterW` at `0x18011474a`

## string_xrefs

- `0x1801149ea`: `Cannot load read only common info: %d\n`
- `0x180114773`: `UniDrvUI::PLoadCommonInfo`
- `0x180114811`: `UniDrvUI::PLoadCommonInfo`
- `0x180114850`: `UniDrvUI::PLoadCommonInfo`
- `0x1801149fd`: `UniDrvUI::PLoadCommonInfo`
- `0x180114769`: `OpenPrinter failed for '%ws': %d\n`
- `0x180114952`: `Cannot load OEM plugins: %d\n`
- `0x180114921`: `Cannot get OEM plugins info: %d\n`

## pseudocode

```c
struct UniDrvUI::_COMMONINFO *__fastcall UniDrvUI::PLoadCommonInfo(UniDrvUI *this, WCHAR *a2, unsigned __int16 *a3)
{
  unsigned int v4; // esi
  __int64 *v5; // rbx
  wchar_t *v6; // rcx
  HLOCAL v7; // rax
  DWORD LastError; // eax
  struct UniDrvUI::_COMMONINFO *v9; // rdx
  __int64 v10; // rdx
  BYTE *Printer; // rax
  BYTE *v12; // rdi
  int v13; // eax
  DWORD v14; // eax
  DWORD v15; // eax
  __int64 *v16; // rdi
  _QWORD *v17; // rax
  HLOCAL v18; // rcx
  __int64 v19; // rdx
  __int64 v20; // rcx
  __int64 v21; // rax
  DWORD v22; // eax
  _QWORD *v23; // rax
  DWORD v24; // eax
  DWORD v25; // eax
  int v26; // eax
  DWORD v28; // eax
  void *v29; // rcx
  HANDLE v30; // [rsp+30h] [rbp-30h] BYREF
  WCHAR *v31; // [rsp+38h] [rbp-28h] BYREF
  _QWORD v32[4]; // [rsp+40h] [rbp-20h] BYREF
  HANDLE phPrinter; // [rsp+90h] [rbp+30h] BYREF
  int v34; // [rsp+A0h] [rbp+40h] BYREF
  HLOCAL hMem; // [rsp+A8h] [rbp+48h] BYREF

  phPrinter = this;
  v4 = (unsigned int)a3;
  v5 = (__int64 *)LocalAlloc(0x40u, ((unsigned __int8)a3 & 0x10) != 0 ? 1544LL : 168LL);
  if ( !v5 )
    goto LABEL_41;
  v6 = a2;
  if ( !a2 )
    v6 = L"NULL";
  v7 = DuplicateString(v6);
  v5[3] = (__int64)v7;
  if ( !v7 )
  {
LABEL_41:
    DriverUi::DriverUiTelemetry::WriteDbgTraceWarning("UniDrvUI::PLoadCommonInfo", L"Memory allocation failed\n");
    v29 = (void *)v5[3];
    if ( v29 )
      LocalFree(v29);
    if ( v5 )
      LocalFree(v5);
    return 0;
  }
  v5[2] = (__int64)v5;
  *((_DWORD *)v5 + 10) = v4;
  if ( (v4 & 5) != 0
    && !OpenPrinterW(
          a2,
          &phPrinter,
          (LPPRINTER_DEFAULTSW)((unsigned __int64)qword_1802A4928 & -(__int64)((v4 & 4) != 0))) )
  {
    LastError = GetLastError();
    DriverUi::DriverUiTelemetry::WriteDbgTraceWarning(
      "UniDrvUI::PLoadCommonInfo",
      L"OpenPrinter failed for '%ws': %d\n",
      a2,
      LastError);
LABEL_8:
    UniDrvUI::VFreeCommonInfo((UniDrvUI *)v5, v9);
    return 0;
  }
  v10 = 2;
  v5[4] = (__int64)phPrinter;
  if ( (v4 & 2) != 0 )
  {
    v34 = 1539;
    Printer = MyGetPrinter(phPrinter, 2u);
    v12 = Printer;
    if ( Printer && (*(_QWORD *)Printer || BGetPrinterDataDWord(phPrinter, L"InitDriverVersion", (BYTE *)&v34))
      || (v13 = 0, v34 = 0, v12) )
    {
      LocalFree(v12);
      v13 = v34;
    }
    if ( v13 != 1539 )
    {
      v14 = GetLastError();
      DriverUi::DriverUiTelemetry::WriteDbgTraceInfo(
        "UniDrvUI::PLoadCommonInfo",
        L"Printer not fully initialized yet: %d\n",
        v14);
      goto LABEL_8;
    }
  }
  hMem = MyGetPrinterDriver(phPrinter, v10, 3u);
  if ( !hMem )
  {
    v15 = GetLastError();
    DriverUi::DriverUiTelemetry::WriteDbgTraceWarning(
      "UniDrvUI::PLoadCommonInfo",
      L"Cannot get printer driver info: %d\n",
      v15);
    goto LABEL_8;
  }
  if ( (v4 & 8) != 0 )
    BSetPrinterDataDWord(phPrinter, L"InitDriverVersion", 1539);
  v16 = v5 + 8;
  v17 = UniDrvUI::PAcquireCommonInfoRO(phPrinter, a2, v4, &hMem, v5 + 8);
  v18 = hMem;
  v5[6] = (__int64)v17;
  if ( v18 )
    LocalFree(v18);
  v19 = v5[6];
  if ( !v19 || (v20 = *v16) == 0 )
  {
    v28 = GetLastError();
    DriverUi::DriverUiTelemetry::WriteDbgTraceWarning(
      "UniDrvUI::PLoadCommonInfo",
      L"Cannot load read only common info: %d\n",
      v28);
    goto LABEL_8;
  }
  if ( *(_DWORD *)(v20 + 56) )
    v21 = v20 + *(unsigned int *)(v20 + 56);
  else
    v21 = 0;
  v5[9] = v21;
  if ( !v21 )
  {
    v22 = GetLastError();
    DriverUi::DriverUiTelemetry::WriteDbgTraceWarning(
      "UniDrvUI::PLoadCommonInfo",
      L"Cannot load printer description data: %d\n",
      v22);
    goto LABEL_8;
  }
  v23 = (_QWORD *)PGetOemPluginInfo(v20, *(const wchar_t **)(*(_QWORD *)(v19 + 32) + 40LL), *(_QWORD *)(v19 + 32));
  v5[10] = (__int64)v23;
  if ( !v23 )
  {
    v24 = GetLastError();
    DriverUi::DriverUiTelemetry::WriteDbgTraceWarning(
      "UniDrvUI::PLoadCommonInfo",
      L"Cannot get OEM plugins info: %d\n",
      v24);
    goto LABEL_8;
  }
  *v23 = v5;
  if ( !(unsigned int)BLoadOEMPluginModulesInternal((UniDrvUI *)v5, v5[10], 1) )
  {
    v25 = GetLastError();
    DriverUi::DriverUiTelemetry::WriteDbgTraceWarning(
      "UniDrvUI::PLoadCommonInfo",
      L"Cannot load OEM plugins: %d\n",
      v25);
    goto LABEL_8;
  }
  *(_DWORD *)v5 = 16;
  hMem = v5 + 19;
  v5[1] = (__int64)&UniDrvUI::OemUIHelperFuncs;
  v30 = phPrinter;
  v32[0] = &hMem;
  v32[1] = &v30;
  v31 = a2;
  v5[19] = 0;
  v32[2] = &v31;
  v26 = ExceptionBoundary__lambda_dc033fb7bf91e463ed547d613a2e4276_((__int64)v32);
  if ( v26 >= 0 )
  {
    if ( *(_QWORD *)hMem )
      *((_DWORD *)v5 + 10) |= 0x800000u;
  }
  else
  {
    Print::Driver::Telemetry::PrintConfigTelemetry::WriteDbgTraceWarning(
      "ModuleDisplayNameImpl::GetLanguageHelper",
      L"Failed to retrieve language helper (hr: 0x%x)",
      (unsigned int)v26);
  }
  return (struct UniDrvUI::_COMMONINFO *)v5;
}

```

## disassembly

```asm
0x1801146b4  mov     [rsp-28h+phPrinter], rcx
0x1801146b9  push    rbp
0x1801146ba  push    rbx
0x1801146bb  push    rsi
0x1801146bc  push    rdi
0x1801146bd  push    r14
0x1801146bf  mov     rbp, rsp
0x1801146c2  sub     rsp, 60h
0x1801146c6  mov     r14, rdx
0x1801146c9  mov     eax, r8d
0x1801146cc  and     al, 10h
0x1801146ce  mov     ecx, 40h ; '@'; uFlags
0x1801146d3  neg     al
0x1801146d5  mov     esi, r8d
0x1801146d8  sbb     rdx, rdx
0x1801146db  and     edx, 560h
0x1801146e1  add     rdx, 0A8h; uBytes
0x1801146e8  call    cs:__imp_LocalAlloc
0x1801146ef  nop     dword ptr [rax+rax+00h]
0x1801146f4  mov     rbx, rax
0x1801146f7  test    rax, rax
0x1801146fa  jz      loc_1801149F6
0x180114700  lea     rax, aNull_0; "NULL"
0x180114707  test    r14, r14
0x18011470a  mov     rcx, r14
0x18011470d  cmovz   rcx, rax; Src
0x180114711  call    DuplicateString
0x180114716  mov     [rbx+18h], rax
0x18011471a  test    rax, rax
0x18011471d  jz      loc_1801149F6
0x180114723  mov     [rbx+10h], rbx
0x180114727  mov     [rbx+28h], esi
0x18011472a  test    sil, 5
0x18011472e  jz      short loc_18011478C
0x180114730  mov     eax, esi
0x180114732  lea     rcx, qword_1802A4928
0x180114739  and     al, 4
0x18011473b  lea     rdx, [rbp+phPrinter]; phPrinter
0x18011473f  neg     al
0x180114741  sbb     r8, r8
0x180114744  and     r8, rcx; pDefault
0x180114747  mov     rcx, r14; pPrinterName
0x18011474a  call    cs:__imp_OpenPrinterW
0x180114751  nop     dword ptr [rax+rax+00h]
0x180114756  test    eax, eax
0x180114758  jnz     short loc_18011478C
0x18011475a  call    cs:__imp_GetLastError
0x180114761  nop     dword ptr [rax+rax+00h]
0x180114766  mov     r8, r14
0x180114769  lea     rdx, aOpenprinterFai; "OpenPrinter failed for '%ws': %d\n"
0x180114770  mov     r9d, eax
0x180114773  lea     rcx, aUnidrvuiPloadc_0; "UniDrvUI::PLoadCommonInfo"
0x18011477a  call    ?WriteDbgTraceWarning@DriverUiTelemetry@DriverUi@@SAXPEADPEAGZZ; DriverUi::DriverUiTelemetry::WriteDbgTraceWarning(char *,ushort *,...)
0x18011477f  mov     rcx, rbx; this
0x180114782  call    ?VFreeCommonInfo@UniDrvUI@@YAXPEAU_COMMONINFO@1@@Z; UniDrvUI::VFreeCommonInfo(UniDrvUI::_COMMONINFO *)
0x180114787  jmp     loc_180114A32
0x18011478c  mov     rax, [rbp+phPrinter]
0x180114790  mov     edx, 2; Level
0x180114795  mov     [rbx+20h], rax
0x180114799  test    dl, sil
0x18011479c  jz      loc_180114822
0x1801147a2  mov     rcx, [rbp+phPrinter]; hPrinter
0x1801147a6  mov     [rbp+arg_10], 603h
0x1801147ad  call    MyGetPrinter
0x1801147b2  mov     rdi, rax
0x1801147b5  test    rax, rax
0x1801147b8  jz      short loc_1801147D8
0x1801147ba  cmp     qword ptr [rax], 0
0x1801147be  jnz     short loc_1801147E2
0x1801147c0  mov     rcx, [rbp+phPrinter]
0x1801147c4  lea     r8, [rbp+arg_10]
0x1801147c8  lea     rdx, aInitdriververs; "InitDriverVersion"
0x1801147cf  call    BGetPrinterDataDWord
0x1801147d4  test    eax, eax
0x1801147d6  jnz     short loc_1801147E2
0x1801147d8  xor     eax, eax
0x1801147da  mov     [rbp+arg_10], eax
0x1801147dd  test    rdi, rdi
0x1801147e0  jz      short loc_1801147F4
0x1801147e2  mov     rcx, rdi; hMem
0x1801147e5  call    cs:__imp_LocalFree
0x1801147ec  nop     dword ptr [rax+rax+00h]
0x1801147f1  mov     eax, [rbp+arg_10]
0x1801147f4  cmp     eax, 603h
0x1801147f9  jz      short loc_180114822
0x1801147fb  call    cs:__imp_GetLastError
0x180114802  nop     dword ptr [rax+rax+00h]
0x180114807  mov     r8d, eax
0x18011480a  lea     rdx, aPrinterNotFull; "Printer not fully initialized yet: %d\n"
0x180114811  lea     rcx, aUnidrvuiPloadc_0; "UniDrvUI::PLoadCommonInfo"
0x180114818  call    ?WriteDbgTraceInfo@DriverUiTelemetry@DriverUi@@SAXPEADPEAGZZ; DriverUi::DriverUiTelemetry::WriteDbgTraceInfo(char *,ushort *,...)
0x18011481d  jmp     loc_18011477F
0x180114822  mov     rcx, [rbp+phPrinter]; hPrinter
0x180114826  mov     r8d, 3
0x18011482c  call    MyGetPrinterDriver
0x180114831  mov     [rbp+hMem], rax
0x180114835  test    rax, rax
0x180114838  jnz     short loc_180114861
0x18011483a  call    cs:__imp_GetLastError
0x180114841  nop     dword ptr [rax+rax+00h]
0x180114846  lea     rdx, aCannotGetPrint_0; "Cannot get printer driver info: %d\n"
0x18011484d  mov     r8d, eax
0x180114850  lea     rcx, aUnidrvuiPloadc_0; "UniDrvUI::PLoadCommonInfo"
0x180114857  call    ?WriteDbgTraceWarning@DriverUiTelemetry@DriverUi@@SAXPEADPEAGZZ; DriverUi::DriverUiTelemetry::WriteDbgTraceWarning(char *,ushort *,...)
0x18011485c  jmp     loc_18011477F
0x180114861  test    sil, 8
0x180114865  jz      short loc_18011487D
0x180114867  mov     rcx, [rbp+phPrinter]
0x18011486b  lea     rdx, aInitdriververs; "InitDriverVersion"
0x180114872  mov     r8d, 603h
0x180114878  call    BSetPrinterDataDWord
0x18011487d  mov     rcx, [rbp+phPrinter]; void *
0x180114881  lea     rdi, [rbx+40h]
0x180114885  lea     r9, [rbp+hMem]
0x180114889  mov     [rsp+60h+var_40], rdi; __int64
0x18011488e  mov     r8d, esi
0x180114891  mov     rdx, r14; pPrinterName
0x180114894  call    UniDrvUI__PAcquireCommonInfoRO
0x180114899  mov     rcx, [rbp+hMem]; hMem
0x18011489d  mov     [rbx+30h], rax
0x1801148a1  test    rcx, rcx
0x1801148a4  jz      short loc_1801148B2
0x1801148a6  call    cs:__imp_LocalFree
0x1801148ad  nop     dword ptr [rax+rax+00h]
0x1801148b2  mov     rdx, [rbx+30h]
0x1801148b6  test    rdx, rdx
0x1801148b9  jz      loc_1801149DE
0x1801148bf  mov     rcx, [rdi]
0x1801148c2  test    rcx, rcx
0x1801148c5  jz      loc_1801149DE
0x1801148cb  cmp     dword ptr [rcx+38h], 0
0x1801148cf  jz      short loc_1801148D9
0x1801148d1  mov     eax, [rcx+38h]
0x1801148d4  add     rax, rcx
0x1801148d7  jmp     short loc_1801148DB
0x1801148d9  xor     eax, eax
0x1801148db  mov     [rbx+48h], rax
0x1801148df  test    rax, rax
0x1801148e2  jnz     short loc_1801148FC
0x1801148e4  call    cs:__imp_GetLastError
0x1801148eb  nop     dword ptr [rax+rax+00h]
0x1801148f0  lea     rdx, aCannotLoadPrin; "Cannot load printer description data: %"...
0x1801148f7  jmp     loc_18011484D
0x1801148fc  mov     rdx, [rdx+20h]
0x180114900  mov     r8, rdx
0x180114903  mov     rdx, [rdx+28h]
0x180114907  call    PGetOemPluginInfo
0x18011490c  mov     [rbx+50h], rax
0x180114910  test    rax, rax
0x180114913  jnz     short loc_18011492D
0x180114915  call    cs:__imp_GetLastError
0x18011491c  nop     dword ptr [rax+rax+00h]
0x180114921  lea     rdx, aCannotGetOemPl; "Cannot get OEM plugins info: %d\n"
0x180114928  jmp     loc_18011484D
0x18011492d  mov     [rax], rbx
0x180114930  mov     r8d, 1
0x180114936  mov     rdx, [rbx+50h]
0x18011493a  mov     rcx, rbx; this
0x18011493d  call    BLoadOEMPluginModulesInternal
0x180114942  test    eax, eax
0x180114944  jnz     short loc_18011495E
0x180114946  call    cs:__imp_GetLastError
0x18011494d  nop     dword ptr [rax+rax+00h]
0x180114952  lea     rdx, aCannotLoadOemP_0; "Cannot load OEM plugins: %d\n"
0x180114959  jmp     loc_18011484D
0x18011495e  mov     dword ptr [rbx], 10h
0x180114964  lea     rcx, [rbx+98h]
0x18011496b  mov     [rbp+hMem], rcx
0x18011496f  lea     rax, ?OemUIHelperFuncs@UniDrvUI@@3U_OEMUIPROCS@@B; _OEMUIPROCS const UniDrvUI::OemUIHelperFuncs
0x180114976  mov     [rbx+8], rax
0x18011497a  mov     rax, [rbp+phPrinter]
0x18011497e  mov     [rbp+var_30], rax
0x180114982  lea     rax, [rbp+hMem]
0x180114986  mov     [rbp+var_20], rax
0x18011498a  lea     rax, [rbp+var_30]
0x18011498e  mov     [rbp+var_18], rax
0x180114992  lea     rax, [rbp+var_28]
0x180114996  mov     [rbp+var_28], r14
0x18011499a  mov     qword ptr [rcx], 0
0x1801149a1  lea     rcx, [rbp+var_20]
0x1801149a5  mov     [rbp+var_10], rax
0x1801149a9  call    ExceptionBoundary__lambda_dc033fb7bf91e463ed547d613a2e4276___; ExceptionBoundary__lambda_dc033fb7bf91e463ed547d613a2e4276_
0x1801149ae  test    eax, eax
0x1801149b0  jns     short loc_1801149CA
0x1801149b2  mov     r8d, eax
0x1801149b5  lea     rdx, aFailedToRetrie_2; "Failed to retrieve language helper (hr:"...
0x1801149bc  lea     rcx, aModuledisplayn; "ModuleDisplayNameImpl::GetLanguageHelpe"...
0x1801149c3  call    ?WriteDbgTraceWarning@PrintConfigTelemetry@Telemetry@Driver@Print@@SAXPEADPEAGZZ; Print::Driver::Telemetry::PrintConfigTelemetry::WriteDbgTraceWarning(char *,ushort *,...)
0x1801149c8  jmp     short loc_1801149D9
0x1801149ca  mov     rax, [rbp+hMem]
0x1801149ce  cmp     qword ptr [rax], 0
0x1801149d2  jz      short loc_1801149D9
0x1801149d4  bts     dword ptr [rbx+28h], 17h
0x1801149d9  mov     rax, rbx
0x1801149dc  jmp     short loc_180114A34
0x1801149de  call    cs:__imp_GetLastError
0x1801149e5  nop     dword ptr [rax+rax+00h]
0x1801149ea  lea     rdx, aCannotLoadRead; "Cannot load read only common info: %d\n"
0x1801149f1  jmp     loc_18011484D
0x1801149f6  lea     rdx, aMemoryAllocati; "Memory allocation failed\n"
0x1801149fd  lea     rcx, aUnidrvuiPloadc_0; "UniDrvUI::PLoadCommonInfo"
0x180114a04  call    ?WriteDbgTraceWarning@DriverUiTelemetry@DriverUi@@SAXPEADPEAGZZ; DriverUi::DriverUiTelemetry::WriteDbgTraceWarning(char *,ushort *,...)
0x180114a09  mov     rcx, [rbx+18h]; hMem
0x180114a0d  test    rcx, rcx
0x180114a10  jz      short loc_180114A1E
0x180114a12  call    cs:__imp_LocalFree
0x180114a19  nop     dword ptr [rax+rax+00h]
0x180114a1e  test    rbx, rbx
0x180114a21  jz      short loc_180114A32
0x180114a23  mov     rcx, rbx; hMem
0x180114a26  call    cs:__imp_LocalFree
0x180114a2d  nop     dword ptr [rax+rax+00h]
0x180114a32  xor     eax, eax
0x180114a34  add     rsp, 60h
0x180114a38  pop     r14
0x180114a3a  pop     rdi
0x180114a3b  pop     rsi
0x180114a3c  pop     rbx
0x180114a3d  pop     rbp
0x180114a3e  retn
```
