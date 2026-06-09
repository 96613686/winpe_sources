# UniDrvUI::PLoadCommonInfoRO

- ea: `0x18010fc20`
- end: `0x18010fff0`
- name: `UniDrvUI::PLoadCommonInfoRO`
- size: `976`
- prototype: `__int64 __usercall@<rax>(void *@<rcx>, __int64)`
- caller_count: `1`
- callee_count: `20`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x18010f270`

## callees

- `0x1800032e0`
- `0x180004418`
- `0x180102674`
- `0x18010427c`
- `0x18010fc20`
- `0x1801111c0`
- `0x1801480c8`
- `0x180148100`
- `0x1801481f4`
- `0x1801489dc`
- `0x180148a3c`
- `0x18014d948`
- `0x18014e970`
- `0x18014fefc`
- `0x180150744`
- `0x1801508dc`
- `0x180150aac`
- `0x180151820`
- `0x180151e28`
- `0x1801c3010`

## import_xrefs

- `KERNEL32!GetLastError` at `0x18010fef9`
- `KERNEL32!GetLastError` at `0x18010ff4e`
- `KERNEL32!GetLastError` at `0x18010ff8c`
- `KERNEL32!GetLastError` at `0x18010fef9`
- `KERNEL32!GetLastError` at `0x18010ff4e`
- `KERNEL32!GetLastError` at `0x18010ff8c`
- `KERNEL32!LocalAlloc` at `0x18010fc73`
- `KERNEL32!LocalAlloc` at `0x18010fc73`

## string_xrefs

- `0x18010fd8c`: `Get the file directly from RemotePrintConfigData if this is a v4 connection.`
- `0x18010fc59`: `UniDrvUI::PLoadCommonInfoRO`
- `0x18010fcf6`: `UniDrvUI::PLoadCommonInfoRO`
- `0x18010fd0e`: `UniDrvUI::PLoadCommonInfoRO`
- `0x18010fd39`: `UniDrvUI::PLoadCommonInfoRO`
- `0x18010fd93`: `UniDrvUI::PLoadCommonInfoRO`
- `0x18010fe0b`: `UniDrvUI::PLoadCommonInfoRO`
- `0x18010fea1`: `UniDrvUI::PLoadCommonInfoRO`
- `0x18010ffa5`: `UniDrvUI::PLoadCommonInfoRO`
- `0x18010ffb8`: `UniDrvUI::PLoadCommonInfoRO`
- `0x18010fd07`: `Attempt to populate the cache change id.`
- `0x18010fcef`: `The driver is using PrintConfig.dll.`
- `0x18010ff60`: `Cannot load OEM plugins (hr: 0x%x).`
- `0x18010fece`: `Get information about OEM plugins and load them.`
- `0x18010ff2a`: `Preloads the plugins and keeps the DLL loaded.`
- `0x18010ff0b`: `Cannot get OEM plugins info (hr: 0x%x).`
- `0x18010fcd8`: `PrintConfig.dll`

## pseudocode

```c
_QWORD *__fastcall UniDrvUI::PLoadCommonInfoRO(void *a1, wchar_t *a2, unsigned int a3, _QWORD *a4, __int64 *a5)
{
  _QWORD *v9; // rbx
  wchar_t *v10; // rcx
  __int64 v11; // rax
  bool matched; // al
  BOOL v13; // ebp
  __int64 v14; // rax
  __int64 v15; // rdx
  __int64 v16; // r9
  struct RemotePrintConfigData *v17; // rdi
  const wchar_t *v18; // rax
  __int64 v19; // rcx
  __int64 inited; // rdi
  __int64 v21; // rsi
  __int64 v22; // rcx
  __int64 v23; // rcx
  _QWORD *v24; // rax
  signed int LastError; // eax
  unsigned __int16 *v26; // rdx
  _QWORD *result; // rax
  signed int v28; // eax
  struct RemotePrintConfigData *v29; // [rsp+30h] [rbp-268h] BYREF
  wchar_t pszSrc[264]; // [rsp+40h] [rbp-258h] BYREF

  DriverUi::DriverUiTelemetry::WriteDbgTraceInfo(
    "UniDrvUI::PLoadCommonInfoRO",
    L"Loads basic information needed by the driver UI.");
  v9 = LocalAlloc(0x40u, 0x98u);
  if ( !v9 )
    goto LABEL_42;
  v10 = a2;
  if ( !a2 )
    v10 = L"NULL";
  v11 = DuplicateString(v10);
  v9[2] = v11;
  if ( !v11 )
  {
LABEL_42:
    DriverUi::DriverUiTelemetry::WriteDbgTraceWarning("UniDrvUI::PLoadCommonInfoRO", L"Memory allocation failed.");
    goto LABEL_43;
  }
  v9[4] = *a4;
  *a4 = 0;
  *((_DWORD *)v9 + 6) = a3;
  v9[5] = 0;
  memset_0((char *)v9 + 68, 0, 0x4Eu);
  matched = DoesFullPathMatchFile(*(const unsigned __int16 **)(v9[4] + 40LL), L"PrintConfig.dll");
  v13 = matched;
  if ( matched )
  {
    DriverUi::DriverUiTelemetry::WriteDbgTraceInfo(
      "UniDrvUI::PLoadCommonInfoRO",
      L"The driver is using PrintConfig.dll.");
    *((_DWORD *)v9 + 6) |= 0x100000u;
    DriverUi::DriverUiTelemetry::WriteDbgTraceInfo(
      "UniDrvUI::PLoadCommonInfoRO",
      L"Attempt to populate the cache change id.");
    if ( (int)GetV4PrinterCacheChangeID(a2, a1, v9 + 8) >= 0 )
      *((_DWORD *)v9 + 6) |= 0x200000u;
    DriverUi::DriverUiTelemetry::WriteDbgTraceInfo("UniDrvUI::PLoadCommonInfoRO", L"Retrieve the printer driver ID.");
    if ( (int)GetPrinterDriverIDAsString(a1, (char *)v9 + 68) < 0 )
      CopyStringW((char *)v9 + 68, L"****  PrinterDriverID Not Found  *****", 39);
  }
  if ( (a3 & 0x8000) != 0 && (v14 = v9[4]) != 0 && *(_QWORD *)(v14 + 40) && v13 )
  {
    DriverUi::DriverUiTelemetry::WriteDbgTraceInfo(
      "UniDrvUI::PLoadCommonInfoRO",
      L"Get the file directly from RemotePrintConfigData if this is a v4 connection.");
    v29 = 0;
    if ( (int)RemotePrintConfigData::CreateRemotePrintConfigData(a1, &v29) >= 0 )
    {
      v17 = v29;
      LOBYTE(v16) = 1;
      v18 = (const wchar_t *)(*(__int64 (__fastcall **)(struct RemotePrintConfigData *, __int64, _QWORD, __int64))(*(_QWORD *)v29 + 8LL))(
                               v29,
                               2,
                               0,
                               v16);
      v9[5] = LoadRawBinaryData(v18);
      if ( v17 )
        (*(void (__fastcall **)(struct RemotePrintConfigData *, __int64))(*(_QWORD *)v17 + 32LL))(v17, 1);
    }
  }
  else
  {
    DriverUi::DriverUiTelemetry::WriteDbgTraceInfo(
      "UniDrvUI::PLoadCommonInfoRO",
      L"Go through the GetFilenameByRole because we don't know if this is a connection or a local printer.");
    memset_0(pszSrc, 0, 0x208u);
    if ( (int)GetFilenameByRole(a1, 2, pszSrc, 260) >= 0 )
      v9[5] = LoadRawBinaryData(pszSrc);
  }
  v19 = v9[5];
  if ( v19 )
  {
    inited = InitBinaryData(v19, v15, 0);
    if ( inited && *(_DWORD *)(inited + 56) )
      v21 = inited + *(unsigned int *)(inited + 56);
    else
      v21 = 0;
    if ( v9[5] && inited && v21 )
    {
      DriverUi::DriverUiTelemetry::WriteDbgTraceInfo(
        "UniDrvUI::PLoadCommonInfoRO",
        L"Calculate the maximum size needed to store JT expansion block.");
      *((_DWORD *)v9 + 14) = cbCalcJTExpSize(v22, v21, v9[4], (a3 >> 13) & 1);
      DriverUi::DriverUiTelemetry::WriteDbgTraceInfo(
        "UniDrvUI::PLoadCommonInfoRO",
        L"Get information about OEM plugins and load them.");
      v24 = (_QWORD *)PGetOemPluginInfo(v23, *(_QWORD *)(v9[4] + 40LL), v9[4]);
      v9[6] = v24;
      if ( v24 )
      {
        *v24 = v9;
        DriverUi::DriverUiTelemetry::WriteDbgTraceInfo(
          "UniDrvUI::PLoadCommonInfoRO",
          L"Preloads the plugins and keeps the DLL loaded.");
        if ( (unsigned int)BLoadOEMPluginModulesInternal(0) )
        {
          *(_DWORD *)v9 = 16;
          v9[1] = &UniDrvUI::OemUIHelperFuncs;
          result = v9;
          *((_DWORD *)v9 + 15) = 1;
          *a5 = inited;
          return result;
        }
        LastError = GetLastError();
        if ( LastError > 0 )
          LastError = (unsigned __int16)LastError | 0x80070000;
        v26 = L"Cannot load OEM plugins (hr: 0x%x).";
      }
      else
      {
        LastError = GetLastError();
        if ( LastError > 0 )
          LastError = (unsigned __int16)LastError | 0x80070000;
        v26 = L"Cannot get OEM plugins info (hr: 0x%x).";
      }
      DriverUi::DriverUiTelemetry::WriteDbgTraceWarning("UniDrvUI::PLoadCommonInfoRO", v26, (unsigned int)LastError);
      goto LABEL_32;
    }
  }
  else
  {
    inited = 0;
  }
  v28 = GetLastError();
  if ( v28 > 0 )
    v28 = (unsigned __int16)v28 | 0x80070000;
  DriverUi::DriverUiTelemetry::WriteDbgTraceWarning(
    "UniDrvUI::PLoadCommonInfoRO",
    L"Cannot load printer description data (hr: 0x%x).",
    (unsigned int)v28);
LABEL_32:
  FreeBinaryData(inited);
LABEL_43:
  PSUI::VFreeCommonInfoRO(v9);
  return 0;
}

```

## disassembly

```asm
0x18010fc20  push    rbx
0x18010fc22  push    rbp
0x18010fc23  push    rsi
0x18010fc24  push    rdi
0x18010fc25  push    r12
0x18010fc27  push    r14
0x18010fc29  push    r15
0x18010fc2b  sub     rsp, 260h
0x18010fc32  mov     rax, cs:__security_cookie
0x18010fc39  xor     rax, rsp
0x18010fc3c  mov     [rsp+298h+var_48], rax
0x18010fc44  mov     r12, [rsp+298h+arg_20]
0x18010fc4c  mov     rdi, rdx
0x18010fc4f  mov     r14, rcx
0x18010fc52  lea     rdx, aLoadsBasicInfo; "Loads basic information needed by the d"...
0x18010fc59  lea     rcx, aUnidrvuiPloadc; "UniDrvUI::PLoadCommonInfoRO"
0x18010fc60  mov     rsi, r9
0x18010fc63  mov     r15d, r8d
0x18010fc66  call    ?WriteDbgTraceInfo@DriverUiTelemetry@DriverUi@@SAXPEADPEAGZZ; DriverUi::DriverUiTelemetry::WriteDbgTraceInfo(char *,ushort *,...)
0x18010fc6b  mov     edx, 98h; uBytes
0x18010fc70  lea     ecx, [rdx-58h]; uFlags
0x18010fc73  call    cs:__imp_LocalAlloc
0x18010fc79  mov     rbx, rax
0x18010fc7c  test    rax, rax
0x18010fc7f  jz      loc_18010FFB1
0x18010fc85  lea     rax, aNull_0; "NULL"
0x18010fc8c  test    rdi, rdi
0x18010fc8f  mov     rcx, rdi
0x18010fc92  cmovz   rcx, rax; Src
0x18010fc96  call    DuplicateString
0x18010fc9b  mov     [rbx+10h], rax
0x18010fc9f  test    rax, rax
0x18010fca2  jz      loc_18010FFB1
0x18010fca8  mov     rax, [rsi]
0x18010fcab  xor     edx, edx; Val
0x18010fcad  mov     [rbx+20h], rax
0x18010fcb1  mov     qword ptr [rsi], 0
0x18010fcb8  lea     rsi, [rbx+44h]
0x18010fcbc  mov     rcx, rsi; void *
0x18010fcbf  mov     [rbx+18h], r15d
0x18010fcc3  lea     r8d, [rdx+4Eh]; Size
0x18010fcc7  mov     qword ptr [rbx+28h], 0
0x18010fccf  call    memset_0
0x18010fcd4  mov     rcx, [rbx+20h]
0x18010fcd8  lea     rdx, aPrintconfigDll_1; "PrintConfig.dll"
0x18010fcdf  mov     rcx, [rcx+28h]; unsigned __int16 *
0x18010fce3  call    ?DoesFullPathMatchFile@@YA_NPEBG0@Z; DoesFullPathMatchFile(ushort const *,ushort const *)
0x18010fce8  movzx   ebp, al
0x18010fceb  test    al, al
0x18010fced  jz      short loc_18010FD69
0x18010fcef  lea     rdx, aTheDriverIsUsi; "The driver is using PrintConfig.dll."
0x18010fcf6  lea     rcx, aUnidrvuiPloadc; "UniDrvUI::PLoadCommonInfoRO"
0x18010fcfd  call    ?WriteDbgTraceInfo@DriverUiTelemetry@DriverUi@@SAXPEADPEAGZZ; DriverUi::DriverUiTelemetry::WriteDbgTraceInfo(char *,ushort *,...)
0x18010fd02  bts     dword ptr [rbx+18h], 14h
0x18010fd07  lea     rdx, aAttemptToPopul; "Attempt to populate the cache change id"...
0x18010fd0e  lea     rcx, aUnidrvuiPloadc; "UniDrvUI::PLoadCommonInfoRO"
0x18010fd15  call    ?WriteDbgTraceInfo@DriverUiTelemetry@DriverUi@@SAXPEADPEAGZZ; DriverUi::DriverUiTelemetry::WriteDbgTraceInfo(char *,ushort *,...)
0x18010fd1a  lea     r8, [rbx+40h]
0x18010fd1e  mov     rdx, r14
0x18010fd21  mov     rcx, rdi
0x18010fd24  call    GetV4PrinterCacheChangeID
0x18010fd29  test    eax, eax
0x18010fd2b  js      short loc_18010FD32
0x18010fd2d  bts     dword ptr [rbx+18h], 15h
0x18010fd32  lea     rdx, aRetrieveThePri; "Retrieve the printer driver ID."
0x18010fd39  lea     rcx, aUnidrvuiPloadc; "UniDrvUI::PLoadCommonInfoRO"
0x18010fd40  call    ?WriteDbgTraceInfo@DriverUiTelemetry@DriverUi@@SAXPEADPEAGZZ; DriverUi::DriverUiTelemetry::WriteDbgTraceInfo(char *,ushort *,...)
0x18010fd45  mov     rdx, rsi
0x18010fd48  mov     rcx, r14
0x18010fd4b  call    GetPrinterDriverIDAsString
0x18010fd50  test    eax, eax
0x18010fd52  jns     short loc_18010FD69
0x18010fd54  mov     r8d, 27h ; '''
0x18010fd5a  lea     rdx, aPrinterdriveri_1; "****  PrinterDriverID Not Found  *****"
0x18010fd61  mov     rcx, rsi
0x18010fd64  call    CopyStringW
0x18010fd69  bt      r15d, 0Fh
0x18010fd6e  jnb     loc_18010FE04
0x18010fd74  mov     rax, [rbx+20h]
0x18010fd78  test    rax, rax
0x18010fd7b  jz      loc_18010FE04
0x18010fd81  cmp     qword ptr [rax+28h], 0
0x18010fd86  jz      short loc_18010FE04
0x18010fd88  test    ebp, ebp
0x18010fd8a  jz      short loc_18010FE04
0x18010fd8c  lea     rdx, aGetTheFileDire; "Get the file directly from RemotePrintC"...
0x18010fd93  lea     rcx, aUnidrvuiPloadc; "UniDrvUI::PLoadCommonInfoRO"
0x18010fd9a  call    ?WriteDbgTraceInfo@DriverUiTelemetry@DriverUi@@SAXPEADPEAGZZ; DriverUi::DriverUiTelemetry::WriteDbgTraceInfo(char *,ushort *,...)
0x18010fd9f  lea     rdx, [rsp+298h+var_268]; struct RemotePrintConfigData **
0x18010fda4  mov     [rsp+298h+var_268], 0
0x18010fdad  mov     rcx, r14; void *
0x18010fdb0  call    ?CreateRemotePrintConfigData@RemotePrintConfigData@@SAJPEAXPEAPEAV1@@Z; RemotePrintConfigData::CreateRemotePrintConfigData(void *,RemotePrintConfigData * *)
0x18010fdb5  test    eax, eax
0x18010fdb7  js      loc_18010FE55
0x18010fdbd  mov     rdi, [rsp+298h+var_268]
0x18010fdc2  xor     r8d, r8d
0x18010fdc5  mov     r9b, 1
0x18010fdc8  mov     rcx, rdi
0x18010fdcb  mov     rax, [rdi]
0x18010fdce  lea     edx, [r8+2]
0x18010fdd2  mov     rax, [rax+8]
0x18010fdd6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18010fddb  mov     rcx, rax; pszSrc
0x18010fdde  mov     edx, ebp
0x18010fde0  call    LoadRawBinaryData
0x18010fde5  mov     [rbx+28h], rax
0x18010fde9  test    rdi, rdi
0x18010fdec  jz      short loc_18010FE55
0x18010fdee  mov     rax, [rdi]
0x18010fdf1  mov     edx, 1
0x18010fdf6  mov     rcx, rdi
0x18010fdf9  mov     rax, [rax+20h]
0x18010fdfd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18010fe02  jmp     short loc_18010FE55
0x18010fe04  lea     rdx, aGoThroughTheGe; "Go through the GetFilenameByRole becaus"...
0x18010fe0b  lea     rcx, aUnidrvuiPloadc; "UniDrvUI::PLoadCommonInfoRO"
0x18010fe12  call    ?WriteDbgTraceInfo@DriverUiTelemetry@DriverUi@@SAXPEADPEAGZZ; DriverUi::DriverUiTelemetry::WriteDbgTraceInfo(char *,ushort *,...)
0x18010fe17  xor     edx, edx; Val
0x18010fe19  lea     rcx, [rsp+298h+pszSrc]; void *
0x18010fe1e  mov     r8d, 208h; Size
0x18010fe24  call    memset_0
0x18010fe29  mov     r9d, 104h
0x18010fe2f  lea     r8, [rsp+298h+pszSrc]
0x18010fe34  mov     edx, 2
0x18010fe39  mov     rcx, r14
0x18010fe3c  call    GetFilenameByRole
0x18010fe41  test    eax, eax
0x18010fe43  js      short loc_18010FE55
0x18010fe45  mov     edx, ebp
0x18010fe47  lea     rcx, [rsp+298h+pszSrc]; pszSrc
0x18010fe4c  call    LoadRawBinaryData
0x18010fe51  mov     [rbx+28h], rax
0x18010fe55  mov     rcx, [rbx+28h]
0x18010fe59  test    rcx, rcx
0x18010fe5c  jz      loc_18010FF8A
0x18010fe62  xor     r8d, r8d
0x18010fe65  call    InitBinaryData
0x18010fe6a  mov     rdi, rax
0x18010fe6d  mov     rax, [rbx+28h]
0x18010fe71  test    rdi, rdi
0x18010fe74  jz      short loc_18010FE84
0x18010fe76  cmp     dword ptr [rdi+38h], 0
0x18010fe7a  jz      short loc_18010FE84
0x18010fe7c  mov     esi, [rdi+38h]
0x18010fe7f  add     rsi, rdi
0x18010fe82  jmp     short loc_18010FE86
0x18010fe84  xor     esi, esi
0x18010fe86  test    rax, rax
0x18010fe89  jz      loc_18010FF8C
0x18010fe8f  test    rdi, rdi
0x18010fe92  jz      loc_18010FF8C
0x18010fe98  test    rsi, rsi
0x18010fe9b  jz      loc_18010FF8C
0x18010fea1  lea     rbp, aUnidrvuiPloadc; "UniDrvUI::PLoadCommonInfoRO"
0x18010fea8  mov     rcx, rbp; char *
0x18010feab  lea     rdx, aCalculateTheMa; "Calculate the maximum size needed to st"...
0x18010feb2  call    ?WriteDbgTraceInfo@DriverUiTelemetry@DriverUi@@SAXPEADPEAGZZ; DriverUi::DriverUiTelemetry::WriteDbgTraceInfo(char *,ushort *,...)
0x18010feb7  mov     r8, [rbx+20h]
0x18010febb  mov     rdx, rsi
0x18010febe  shr     r15d, 0Dh
0x18010fec2  and     r15d, 1
0x18010fec6  mov     r9d, r15d
0x18010fec9  call    cbCalcJTExpSize
0x18010fece  lea     rdx, aGetInformation; "Get information about OEM plugins and l"...
0x18010fed5  mov     [rbx+38h], eax
0x18010fed8  mov     rcx, rbp; char *
0x18010fedb  call    ?WriteDbgTraceInfo@DriverUiTelemetry@DriverUi@@SAXPEADPEAGZZ; DriverUi::DriverUiTelemetry::WriteDbgTraceInfo(char *,ushort *,...)
0x18010fee0  mov     rdx, [rbx+20h]
0x18010fee4  mov     r8, rdx
0x18010fee7  mov     rdx, [rdx+28h]
0x18010feeb  call    PGetOemPluginInfo
0x18010fef0  mov     [rbx+30h], rax
0x18010fef4  test    rax, rax
0x18010fef7  jnz     short loc_18010FF2A
0x18010fef9  call    cs:__imp_GetLastError
0x18010feff  test    eax, eax
0x18010ff01  jle     short loc_18010FF0B
0x18010ff03  movzx   eax, ax
0x18010ff06  or      eax, 80070000h
0x18010ff0b  lea     rdx, aCannotGetOemPl_0; "Cannot get OEM plugins info (hr: 0x%x)."
0x18010ff12  mov     rcx, rbp; char *
0x18010ff15  mov     r8d, eax
0x18010ff18  call    ?WriteDbgTraceWarning@DriverUiTelemetry@DriverUi@@SAXPEADPEAGZZ; DriverUi::DriverUiTelemetry::WriteDbgTraceWarning(char *,ushort *,...)
0x18010ff1d  mov     rcx, rdi
0x18010ff20  call    FreeBinaryData
0x18010ff25  jmp     loc_18010FFC4
0x18010ff2a  lea     rdx, aPreloadsThePlu; "Preloads the plugins and keeps the DLL "...
0x18010ff31  mov     [rax], rbx
0x18010ff34  mov     rcx, rbp; char *
0x18010ff37  call    ?WriteDbgTraceInfo@DriverUiTelemetry@DriverUi@@SAXPEADPEAGZZ; DriverUi::DriverUiTelemetry::WriteDbgTraceInfo(char *,ushort *,...)
0x18010ff3c  mov     rdx, [rbx+30h]
0x18010ff40  xor     r8d, r8d
0x18010ff43  xor     ecx, ecx; this
0x18010ff45  call    BLoadOEMPluginModulesInternal
0x18010ff4a  test    eax, eax
0x18010ff4c  jnz     short loc_18010FF69
0x18010ff4e  call    cs:__imp_GetLastError
0x18010ff54  test    eax, eax
0x18010ff56  jle     short loc_18010FF60
0x18010ff58  movzx   eax, ax
0x18010ff5b  or      eax, 80070000h
0x18010ff60  lea     rdx, aCannotLoadOemP; "Cannot load OEM plugins (hr: 0x%x)."
0x18010ff67  jmp     short loc_18010FF12
0x18010ff69  lea     rax, ?OemUIHelperFuncs@UniDrvUI@@3U_OEMUIPROCS@@B; _OEMUIPROCS const UniDrvUI::OemUIHelperFuncs
0x18010ff70  mov     dword ptr [rbx], 10h
0x18010ff76  mov     [rbx+8], rax
0x18010ff7a  mov     rax, rbx
0x18010ff7d  mov     dword ptr [rbx+3Ch], 1
0x18010ff84  mov     [r12], rdi
0x18010ff88  jmp     short loc_18010FFCE
0x18010ff8a  xor     edi, edi
0x18010ff8c  call    cs:__imp_GetLastError
0x18010ff92  test    eax, eax
0x18010ff94  jle     short loc_18010FF9E
0x18010ff96  movzx   eax, ax
0x18010ff99  or      eax, 80070000h
0x18010ff9e  lea     rdx, aCannotLoadPrin_1; "Cannot load printer description data (h"...
0x18010ffa5  lea     rcx, aUnidrvuiPloadc; "UniDrvUI::PLoadCommonInfoRO"
0x18010ffac  jmp     loc_18010FF15
0x18010ffb1  lea     rdx, aMemoryAllocati_1; "Memory allocation failed."
0x18010ffb8  lea     rcx, aUnidrvuiPloadc; "UniDrvUI::PLoadCommonInfoRO"
0x18010ffbf  call    ?WriteDbgTraceWarning@DriverUiTelemetry@DriverUi@@SAXPEADPEAGZZ; DriverUi::DriverUiTelemetry::WriteDbgTraceWarning(char *,ushort *,...)
0x18010ffc4  mov     rcx, rbx; hMem
0x18010ffc7  call    PSUI__VFreeCommonInfoRO
0x18010ffcc  xor     eax, eax
0x18010ffce  mov     rcx, [rsp+298h+var_48]
0x18010ffd6  xor     rcx, rsp; StackCookie
0x18010ffd9  call    __security_check_cookie
0x18010ffde  add     rsp, 260h
0x18010ffe5  pop     r15
0x18010ffe7  pop     r14
0x18010ffe9  pop     r12
0x18010ffeb  pop     rdi
0x18010ffec  pop     rsi
0x18010ffed  pop     rbp
0x18010ffee  pop     rbx
0x18010ffef  retn
```
