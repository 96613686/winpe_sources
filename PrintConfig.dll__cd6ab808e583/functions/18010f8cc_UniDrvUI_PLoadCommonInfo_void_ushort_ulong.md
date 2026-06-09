# UniDrvUI::PLoadCommonInfo(void *,ushort *,ulong)

- ea: `0x18010f8cc`
- end: `0x18010fc19`
- name: `?PLoadCommonInfo@UniDrvUI@@YAPEAU_COMMONINFO@1@PEAXPEAGK@Z`
- size: `845`
- prototype: `struct UniDrvUI::_COMMONINFO *(UniDrvUI *__hidden this, void *, unsigned __int16 *, unsigned int)`
- caller_count: `14`
- callee_count: `13`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x1800f7444`
- `0x180105174`
- `0x180106350`
- `0x1801067bc`
- `0x18010722c`
- `0x180108df4`
- `0x180109cd8`
- `0x18010a2fc`
- `0x18010c890`
- `0x18010cc88`
- `0x18010ec78`
- `0x18010f628`
- `0x180111520`
- `0x180111920`

## callees

- `0x1800183f8`
- `0x180034228`
- `0x180102674`
- `0x18010427c`
- `0x18010f270`
- `0x18010f8cc`
- `0x180111180`
- `0x180148a3c`
- `0x180148d9c`
- `0x180148e38`
- `0x18014a300`
- `0x18014d948`
- `0x18014e970`

## import_xrefs

- `KERNEL32!GetLastError` at `0x18010f966`
- `KERNEL32!GetLastError` at `0x18010f9f7`
- `KERNEL32!GetLastError` at `0x18010fa30`
- `KERNEL32!GetLastError` at `0x18010fae2`
- `KERNEL32!GetLastError` at `0x18010fb0d`
- `KERNEL32!GetLastError` at `0x18010fb38`
- `KERNEL32!GetLastError` at `0x18010fbca`
- `KERNEL32!GetLastError` at `0x18010f966`
- `KERNEL32!GetLastError` at `0x18010f9f7`
- `KERNEL32!GetLastError` at `0x18010fa30`
- `KERNEL32!GetLastError` at `0x18010fae2`
- `KERNEL32!GetLastError` at `0x18010fb0d`
- `KERNEL32!GetLastError` at `0x18010fb38`
- `KERNEL32!GetLastError` at `0x18010fbca`
- `KERNEL32!LocalFree` at `0x18010f9e7`
- `KERNEL32!LocalFree` at `0x18010faaa`
- `KERNEL32!LocalFree` at `0x18010fbf8`
- `KERNEL32!LocalFree` at `0x18010fc06`
- `KERNEL32!LocalFree` at `0x18010f9e7`
- `KERNEL32!LocalFree` at `0x18010faaa`
- `KERNEL32!LocalFree` at `0x18010fbf8`
- `KERNEL32!LocalFree` at `0x18010fc06`
- `KERNEL32!LocalAlloc` at `0x18010f900`
- `KERNEL32!LocalAlloc` at `0x18010f900`
- `WINSPOOL!SetPrinterDataW` at `0x18010fa7b`
- `WINSPOOL!SetPrinterDataW` at `0x18010fa7b`
- `WINSPOOL!OpenPrinterW` at `0x18010f95c`
- `WINSPOOL!OpenPrinterW` at `0x18010f95c`

## string_xrefs

- `0x18010f96f`: `OpenPrinter failed for '%ws': %d\n`
- `0x18010f979`: `UniDrvUI::PLoadCommonInfo`
- `0x18010fa07`: `UniDrvUI::PLoadCommonInfo`
- `0x18010fa40`: `UniDrvUI::PLoadCommonInfo`
- `0x18010fbe3`: `UniDrvUI::PLoadCommonInfo`
- `0x18010fb3e`: `Cannot load OEM plugins: %d\n`
- `0x18010fbd0`: `Cannot load read only common info: %d\n`
- `0x18010fb13`: `Cannot get OEM plugins info: %d\n`

## pseudocode

```c
struct UniDrvUI::_COMMONINFO *__fastcall UniDrvUI::PLoadCommonInfo(UniDrvUI *this, WCHAR *a2, unsigned __int16 *a3)
{
  int v4; // esi
  __int64 *v5; // rbx
  wchar_t *v6; // rcx
  __int64 v7; // rax
  DWORD LastError; // eax
  struct UniDrvUI::_COMMONINFO *v9; // rdx
  _QWORD *Printer; // rax
  void *v11; // rdi
  int v12; // eax
  DWORD v13; // eax
  DWORD v14; // eax
  __int64 *v15; // rdi
  __int64 v16; // rax
  HLOCAL v17; // rcx
  __int64 v18; // rdx
  __int64 v19; // rcx
  __int64 v20; // rax
  DWORD v21; // eax
  __int64 **v22; // rax
  DWORD v23; // eax
  DWORD v24; // eax
  int v25; // eax
  DWORD v27; // eax
  void *v28; // rcx
  HANDLE v29; // [rsp+30h] [rbp-30h] BYREF
  WCHAR *v30; // [rsp+38h] [rbp-28h] BYREF
  _QWORD v31[4]; // [rsp+40h] [rbp-20h] BYREF
  HANDLE phPrinter; // [rsp+90h] [rbp+30h] BYREF
  int pData; // [rsp+A0h] [rbp+40h] BYREF
  HLOCAL hMem; // [rsp+A8h] [rbp+48h] BYREF

  phPrinter = this;
  v4 = (int)a3;
  v5 = (__int64 *)LocalAlloc(0x40u, ((unsigned __int8)a3 & 0x10) != 0 ? 1544LL : 168LL);
  if ( !v5 )
    goto LABEL_41;
  v6 = a2;
  if ( !a2 )
    v6 = L"NULL";
  v7 = DuplicateString(v6);
  v5[3] = v7;
  if ( !v7 )
  {
LABEL_41:
    DriverUi::DriverUiTelemetry::WriteDbgTraceWarning("UniDrvUI::PLoadCommonInfo", L"Memory allocation failed\n");
    v28 = (void *)v5[3];
    if ( v28 )
      LocalFree(v28);
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
          (LPPRINTER_DEFAULTSW)((unsigned __int64)qword_18029D7B8 & -(__int64)((v4 & 4) != 0))) )
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
  v5[4] = (__int64)phPrinter;
  if ( (v4 & 2) != 0 )
  {
    pData = 1539;
    Printer = (_QWORD *)MyGetPrinter(phPrinter, 2u);
    v11 = Printer;
    if ( Printer && (*Printer || (unsigned int)BGetPrinterDataDWord(phPrinter, L"InitDriverVersion", &pData))
      || (v12 = 0, pData = 0, v11) )
    {
      LocalFree(v11);
      v12 = pData;
    }
    if ( v12 != 1539 )
    {
      v13 = GetLastError();
      DriverUi::DriverUiTelemetry::WriteDbgTraceInfo(
        "UniDrvUI::PLoadCommonInfo",
        L"Printer not fully initialized yet: %d\n",
        v13);
      goto LABEL_8;
    }
  }
  hMem = (HLOCAL)MyGetPrinterDriver(phPrinter);
  if ( !hMem )
  {
    v14 = GetLastError();
    DriverUi::DriverUiTelemetry::WriteDbgTraceWarning(
      "UniDrvUI::PLoadCommonInfo",
      L"Cannot get printer driver info: %d\n",
      v14);
    goto LABEL_8;
  }
  if ( (v4 & 8) != 0 )
  {
    pData = 1539;
    SetPrinterDataW(phPrinter, (LPWSTR)L"InitDriverVersion", 4u, (LPBYTE)&pData, 4u);
  }
  v15 = v5 + 8;
  v16 = UniDrvUI::PAcquireCommonInfoRO(phPrinter, a2, (__int64)(v5 + 8));
  v17 = hMem;
  v5[6] = v16;
  if ( v17 )
    LocalFree(v17);
  v18 = v5[6];
  if ( !v18 || (v19 = *v15) == 0 )
  {
    v27 = GetLastError();
    DriverUi::DriverUiTelemetry::WriteDbgTraceWarning(
      "UniDrvUI::PLoadCommonInfo",
      L"Cannot load read only common info: %d\n",
      v27);
    goto LABEL_8;
  }
  if ( *(_DWORD *)(v19 + 56) )
    v20 = v19 + *(unsigned int *)(v19 + 56);
  else
    v20 = 0;
  v5[9] = v20;
  if ( !v20 )
  {
    v21 = GetLastError();
    DriverUi::DriverUiTelemetry::WriteDbgTraceWarning(
      "UniDrvUI::PLoadCommonInfo",
      L"Cannot load printer description data: %d\n",
      v21);
    goto LABEL_8;
  }
  v22 = (__int64 **)PGetOemPluginInfo(v19, *(_QWORD *)(*(_QWORD *)(v18 + 32) + 40LL), *(_QWORD *)(v18 + 32));
  v5[10] = (__int64)v22;
  if ( !v22 )
  {
    v23 = GetLastError();
    DriverUi::DriverUiTelemetry::WriteDbgTraceWarning(
      "UniDrvUI::PLoadCommonInfo",
      L"Cannot get OEM plugins info: %d\n",
      v23);
    goto LABEL_8;
  }
  *v22 = v5;
  if ( !(unsigned int)BLoadOEMPluginModulesInternal((UniDrvUI *)v5) )
  {
    v24 = GetLastError();
    DriverUi::DriverUiTelemetry::WriteDbgTraceWarning(
      "UniDrvUI::PLoadCommonInfo",
      L"Cannot load OEM plugins: %d\n",
      v24);
    goto LABEL_8;
  }
  *(_DWORD *)v5 = 16;
  hMem = v5 + 19;
  v5[1] = (__int64)&UniDrvUI::OemUIHelperFuncs;
  v29 = phPrinter;
  v31[0] = &hMem;
  v31[1] = &v29;
  v30 = a2;
  v5[19] = 0;
  v31[2] = &v30;
  v25 = ExceptionBoundary__lambda_dc033fb7bf91e463ed547d613a2e4276_(v31);
  if ( v25 >= 0 )
  {
    if ( *(_QWORD *)hMem )
      *((_DWORD *)v5 + 10) |= 0x800000u;
  }
  else
  {
    Print::Driver::Telemetry::PrintConfigTelemetry::WriteDbgTraceWarning(
      "ModuleDisplayNameImpl::GetLanguageHelper",
      L"Failed to retrieve language helper (hr: 0x%x)",
      (unsigned int)v25);
  }
  return (struct UniDrvUI::_COMMONINFO *)v5;
}

```

## disassembly

```asm
0x18010f8cc  mov     [rsp-28h+phPrinter], rcx
0x18010f8d1  push    rbp
0x18010f8d2  push    rbx
0x18010f8d3  push    rsi
0x18010f8d4  push    rdi
0x18010f8d5  push    r14
0x18010f8d7  mov     rbp, rsp
0x18010f8da  sub     rsp, 60h
0x18010f8de  mov     r14, rdx
0x18010f8e1  mov     eax, r8d
0x18010f8e4  and     al, 10h
0x18010f8e6  mov     ecx, 40h ; '@'; uFlags
0x18010f8eb  neg     al
0x18010f8ed  mov     esi, r8d
0x18010f8f0  sbb     rdx, rdx
0x18010f8f3  and     edx, 560h
0x18010f8f9  add     rdx, 0A8h; uBytes
0x18010f900  call    cs:__imp_LocalAlloc
0x18010f906  mov     rbx, rax
0x18010f909  test    rax, rax
0x18010f90c  jz      loc_18010FBDC
0x18010f912  lea     rax, aNull_0; "NULL"
0x18010f919  test    r14, r14
0x18010f91c  mov     rcx, r14
0x18010f91f  cmovz   rcx, rax; Src
0x18010f923  call    DuplicateString
0x18010f928  mov     [rbx+18h], rax
0x18010f92c  test    rax, rax
0x18010f92f  jz      loc_18010FBDC
0x18010f935  mov     [rbx+10h], rbx
0x18010f939  mov     [rbx+28h], esi
0x18010f93c  test    sil, 5
0x18010f940  jz      short loc_18010F992
0x18010f942  mov     eax, esi
0x18010f944  lea     rcx, qword_18029D7B8
0x18010f94b  and     al, 4
0x18010f94d  lea     rdx, [rbp+phPrinter]; phPrinter
0x18010f951  neg     al
0x18010f953  sbb     r8, r8
0x18010f956  and     r8, rcx; pDefault
0x18010f959  mov     rcx, r14; pPrinterName
0x18010f95c  call    cs:__imp_OpenPrinterW
0x18010f962  test    eax, eax
0x18010f964  jnz     short loc_18010F992
0x18010f966  call    cs:__imp_GetLastError
0x18010f96c  mov     r8, r14
0x18010f96f  lea     rdx, aOpenprinterFai; "OpenPrinter failed for '%ws': %d\n"
0x18010f976  mov     r9d, eax
0x18010f979  lea     rcx, aUnidrvuiPloadc_0; "UniDrvUI::PLoadCommonInfo"
0x18010f980  call    ?WriteDbgTraceWarning@DriverUiTelemetry@DriverUi@@SAXPEADPEAGZZ; DriverUi::DriverUiTelemetry::WriteDbgTraceWarning(char *,ushort *,...)
0x18010f985  mov     rcx, rbx; this
0x18010f988  call    ?VFreeCommonInfo@UniDrvUI@@YAXPEAU_COMMONINFO@1@@Z; UniDrvUI::VFreeCommonInfo(UniDrvUI::_COMMONINFO *)
0x18010f98d  jmp     loc_18010FC0C
0x18010f992  mov     rax, [rbp+phPrinter]
0x18010f996  mov     edx, 2; Level
0x18010f99b  mov     [rbx+20h], rax
0x18010f99f  test    dl, sil
0x18010f9a2  jz      short loc_18010FA18
0x18010f9a4  mov     rcx, [rbp+phPrinter]; hPrinter
0x18010f9a8  mov     [rbp+pData], 603h
0x18010f9af  call    MyGetPrinter
0x18010f9b4  mov     rdi, rax
0x18010f9b7  test    rax, rax
0x18010f9ba  jz      short loc_18010F9DA
0x18010f9bc  cmp     qword ptr [rax], 0
0x18010f9c0  jnz     short loc_18010F9E4
0x18010f9c2  mov     rcx, [rbp+phPrinter]
0x18010f9c6  lea     r8, [rbp+pData]
0x18010f9ca  lea     rdx, aInitdriververs; "InitDriverVersion"
0x18010f9d1  call    BGetPrinterDataDWord
0x18010f9d6  test    eax, eax
0x18010f9d8  jnz     short loc_18010F9E4
0x18010f9da  xor     eax, eax
0x18010f9dc  mov     [rbp+pData], eax
0x18010f9df  test    rdi, rdi
0x18010f9e2  jz      short loc_18010F9F0
0x18010f9e4  mov     rcx, rdi; hMem
0x18010f9e7  call    cs:__imp_LocalFree
0x18010f9ed  mov     eax, [rbp+pData]
0x18010f9f0  cmp     eax, 603h
0x18010f9f5  jz      short loc_18010FA18
0x18010f9f7  call    cs:__imp_GetLastError
0x18010f9fd  mov     r8d, eax
0x18010fa00  lea     rdx, aPrinterNotFull; "Printer not fully initialized yet: %d\n"
0x18010fa07  lea     rcx, aUnidrvuiPloadc_0; "UniDrvUI::PLoadCommonInfo"
0x18010fa0e  call    ?WriteDbgTraceInfo@DriverUiTelemetry@DriverUi@@SAXPEADPEAGZZ; DriverUi::DriverUiTelemetry::WriteDbgTraceInfo(char *,ushort *,...)
0x18010fa13  jmp     loc_18010F985
0x18010fa18  mov     rcx, [rbp+phPrinter]; hPrinter
0x18010fa1c  mov     r8d, 3
0x18010fa22  call    MyGetPrinterDriver
0x18010fa27  mov     [rbp+hMem], rax
0x18010fa2b  test    rax, rax
0x18010fa2e  jnz     short loc_18010FA51
0x18010fa30  call    cs:__imp_GetLastError
0x18010fa36  lea     rdx, aCannotGetPrint_0; "Cannot get printer driver info: %d\n"
0x18010fa3d  mov     r8d, eax
0x18010fa40  lea     rcx, aUnidrvuiPloadc_0; "UniDrvUI::PLoadCommonInfo"
0x18010fa47  call    ?WriteDbgTraceWarning@DriverUiTelemetry@DriverUi@@SAXPEADPEAGZZ; DriverUi::DriverUiTelemetry::WriteDbgTraceWarning(char *,ushort *,...)
0x18010fa4c  jmp     loc_18010F985
0x18010fa51  test    sil, 8
0x18010fa55  jz      short loc_18010FA81
0x18010fa57  mov     rcx, [rbp+phPrinter]; hPrinter
0x18010fa5b  lea     r9, [rbp+pData]; pData
0x18010fa5f  mov     r8d, 4; Type
0x18010fa65  mov     [rbp+pData], 603h
0x18010fa6c  lea     rdx, aInitdriververs; "InitDriverVersion"
0x18010fa73  mov     [rsp+60h+cbData], 4; cbData
0x18010fa7b  call    cs:__imp_SetPrinterDataW
0x18010fa81  mov     rcx, [rbp+phPrinter]; void *
0x18010fa85  lea     rdi, [rbx+40h]
0x18010fa89  lea     r9, [rbp+hMem]
0x18010fa8d  mov     qword ptr [rsp+60h+cbData], rdi; __int64
0x18010fa92  mov     r8d, esi
0x18010fa95  mov     rdx, r14; pPrinterName
0x18010fa98  call    UniDrvUI__PAcquireCommonInfoRO
0x18010fa9d  mov     rcx, [rbp+hMem]; hMem
0x18010faa1  mov     [rbx+30h], rax
0x18010faa5  test    rcx, rcx
0x18010faa8  jz      short loc_18010FAB0
0x18010faaa  call    cs:__imp_LocalFree
0x18010fab0  mov     rdx, [rbx+30h]
0x18010fab4  test    rdx, rdx
0x18010fab7  jz      loc_18010FBCA
0x18010fabd  mov     rcx, [rdi]
0x18010fac0  test    rcx, rcx
0x18010fac3  jz      loc_18010FBCA
0x18010fac9  cmp     dword ptr [rcx+38h], 0
0x18010facd  jz      short loc_18010FAD7
0x18010facf  mov     eax, [rcx+38h]
0x18010fad2  add     rax, rcx
0x18010fad5  jmp     short loc_18010FAD9
0x18010fad7  xor     eax, eax
0x18010fad9  mov     [rbx+48h], rax
0x18010fadd  test    rax, rax
0x18010fae0  jnz     short loc_18010FAF4
0x18010fae2  call    cs:__imp_GetLastError
0x18010fae8  lea     rdx, aCannotLoadPrin; "Cannot load printer description data: %"...
0x18010faef  jmp     loc_18010FA3D
0x18010faf4  mov     rdx, [rdx+20h]
0x18010faf8  mov     r8, rdx
0x18010fafb  mov     rdx, [rdx+28h]
0x18010faff  call    PGetOemPluginInfo
0x18010fb04  mov     [rbx+50h], rax
0x18010fb08  test    rax, rax
0x18010fb0b  jnz     short loc_18010FB1F
0x18010fb0d  call    cs:__imp_GetLastError
0x18010fb13  lea     rdx, aCannotGetOemPl; "Cannot get OEM plugins info: %d\n"
0x18010fb1a  jmp     loc_18010FA3D
0x18010fb1f  mov     [rax], rbx
0x18010fb22  mov     r8d, 1
0x18010fb28  mov     rdx, [rbx+50h]
0x18010fb2c  mov     rcx, rbx; this
0x18010fb2f  call    BLoadOEMPluginModulesInternal
0x18010fb34  test    eax, eax
0x18010fb36  jnz     short loc_18010FB4A
0x18010fb38  call    cs:__imp_GetLastError
0x18010fb3e  lea     rdx, aCannotLoadOemP_0; "Cannot load OEM plugins: %d\n"
0x18010fb45  jmp     loc_18010FA3D
0x18010fb4a  mov     dword ptr [rbx], 10h
0x18010fb50  lea     rcx, [rbx+98h]
0x18010fb57  mov     [rbp+hMem], rcx
0x18010fb5b  lea     rax, ?OemUIHelperFuncs@UniDrvUI@@3U_OEMUIPROCS@@B; _OEMUIPROCS const UniDrvUI::OemUIHelperFuncs
0x18010fb62  mov     [rbx+8], rax
0x18010fb66  mov     rax, [rbp+phPrinter]
0x18010fb6a  mov     [rbp+var_30], rax
0x18010fb6e  lea     rax, [rbp+hMem]
0x18010fb72  mov     [rbp+var_20], rax
0x18010fb76  lea     rax, [rbp+var_30]
0x18010fb7a  mov     [rbp+var_18], rax
0x18010fb7e  lea     rax, [rbp+var_28]
0x18010fb82  mov     [rbp+var_28], r14
0x18010fb86  mov     qword ptr [rcx], 0
0x18010fb8d  lea     rcx, [rbp+var_20]
0x18010fb91  mov     [rbp+var_10], rax
0x18010fb95  call    ExceptionBoundary__lambda_dc033fb7bf91e463ed547d613a2e4276___; ExceptionBoundary__lambda_dc033fb7bf91e463ed547d613a2e4276_
0x18010fb9a  test    eax, eax
0x18010fb9c  jns     short loc_18010FBB6
0x18010fb9e  mov     r8d, eax
0x18010fba1  lea     rdx, aFailedToRetrie_2; "Failed to retrieve language helper (hr:"...
0x18010fba8  lea     rcx, aModuledisplayn; "ModuleDisplayNameImpl::GetLanguageHelpe"...
0x18010fbaf  call    ?WriteDbgTraceWarning@PrintConfigTelemetry@Telemetry@Driver@Print@@SAXPEADPEAGZZ; Print::Driver::Telemetry::PrintConfigTelemetry::WriteDbgTraceWarning(char *,ushort *,...)
0x18010fbb4  jmp     short loc_18010FBC5
0x18010fbb6  mov     rax, [rbp+hMem]
0x18010fbba  cmp     qword ptr [rax], 0
0x18010fbbe  jz      short loc_18010FBC5
0x18010fbc0  bts     dword ptr [rbx+28h], 17h
0x18010fbc5  mov     rax, rbx
0x18010fbc8  jmp     short loc_18010FC0E
0x18010fbca  call    cs:__imp_GetLastError
0x18010fbd0  lea     rdx, aCannotLoadRead; "Cannot load read only common info: %d\n"
0x18010fbd7  jmp     loc_18010FA3D
0x18010fbdc  lea     rdx, aMemoryAllocati; "Memory allocation failed\n"
0x18010fbe3  lea     rcx, aUnidrvuiPloadc_0; "UniDrvUI::PLoadCommonInfo"
0x18010fbea  call    ?WriteDbgTraceWarning@DriverUiTelemetry@DriverUi@@SAXPEADPEAGZZ; DriverUi::DriverUiTelemetry::WriteDbgTraceWarning(char *,ushort *,...)
0x18010fbef  mov     rcx, [rbx+18h]; hMem
0x18010fbf3  test    rcx, rcx
0x18010fbf6  jz      short loc_18010FBFE
0x18010fbf8  call    cs:__imp_LocalFree
0x18010fbfe  test    rbx, rbx
0x18010fc01  jz      short loc_18010FC0C
0x18010fc03  mov     rcx, rbx; hMem
0x18010fc06  call    cs:__imp_LocalFree
0x18010fc0c  xor     eax, eax
0x18010fc0e  add     rsp, 60h
0x18010fc12  pop     r14
0x18010fc14  pop     rdi
0x18010fc15  pop     rsi
0x18010fc16  pop     rbx
0x18010fc17  pop     rbp
0x18010fc18  retn
```
