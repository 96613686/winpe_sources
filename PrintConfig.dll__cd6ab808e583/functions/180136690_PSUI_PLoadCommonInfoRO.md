# PSUI::PLoadCommonInfoRO

- ea: `0x180136690`
- end: `0x180136a60`
- name: `PSUI::PLoadCommonInfoRO`
- size: `976`
- prototype: `__int64 __usercall@<rax>(void *@<rcx>, __int64)`
- caller_count: `1`
- callee_count: `20`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x180135ccc`

## callees

- `0x1800032e0`
- `0x180004418`
- `0x180102674`
- `0x18010427c`
- `0x1801111c0`
- `0x180136690`
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

- `KERNEL32!GetLastError` at `0x180136969`
- `KERNEL32!GetLastError` at `0x1801369be`
- `KERNEL32!GetLastError` at `0x1801369fc`
- `KERNEL32!GetLastError` at `0x180136969`
- `KERNEL32!GetLastError` at `0x1801369be`
- `KERNEL32!GetLastError` at `0x1801369fc`
- `KERNEL32!LocalAlloc` at `0x1801366e3`
- `KERNEL32!LocalAlloc` at `0x1801366e3`

## string_xrefs

- `0x1801367fc`: `Get the file directly from RemotePrintConfigData if this is a v4 connection.`
- `0x180136777`: `Attempt to populate the cache change id.`
- `0x18013675f`: `The driver is using PrintConfig.dll.`
- `0x1801369d0`: `Cannot load OEM plugins (hr: 0x%x).`
- `0x18013693e`: `Get information about OEM plugins and load them.`
- `0x18013699a`: `Preloads the plugins and keeps the DLL loaded.`
- `0x18013697b`: `Cannot get OEM plugins info (hr: 0x%x).`
- `0x1801366c9`: `PSUI::PLoadCommonInfoRO`
- `0x180136766`: `PSUI::PLoadCommonInfoRO`
- `0x18013677e`: `PSUI::PLoadCommonInfoRO`
- `0x1801367a9`: `PSUI::PLoadCommonInfoRO`
- `0x180136803`: `PSUI::PLoadCommonInfoRO`
- `0x18013687b`: `PSUI::PLoadCommonInfoRO`
- `0x180136911`: `PSUI::PLoadCommonInfoRO`
- `0x180136a15`: `PSUI::PLoadCommonInfoRO`
- `0x180136a28`: `PSUI::PLoadCommonInfoRO`
- `0x180136748`: `PrintConfig.dll`

## pseudocode

```c
_QWORD *__fastcall PSUI::PLoadCommonInfoRO(void *a1, wchar_t *a2, unsigned int a3, _QWORD *a4, __int64 *a5)
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
    "PSUI::PLoadCommonInfoRO",
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
    DriverUi::DriverUiTelemetry::WriteDbgTraceWarning("PSUI::PLoadCommonInfoRO", L"Memory allocation failed.");
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
    DriverUi::DriverUiTelemetry::WriteDbgTraceInfo("PSUI::PLoadCommonInfoRO", L"The driver is using PrintConfig.dll.");
    *((_DWORD *)v9 + 6) |= 0x100000u;
    DriverUi::DriverUiTelemetry::WriteDbgTraceInfo(
      "PSUI::PLoadCommonInfoRO",
      L"Attempt to populate the cache change id.");
    if ( (int)GetV4PrinterCacheChangeID(a2, a1, v9 + 8) >= 0 )
      *((_DWORD *)v9 + 6) |= 0x200000u;
    DriverUi::DriverUiTelemetry::WriteDbgTraceInfo("PSUI::PLoadCommonInfoRO", L"Retrieve the printer driver ID.");
    if ( (int)GetPrinterDriverIDAsString(a1, (char *)v9 + 68) < 0 )
      CopyStringW((char *)v9 + 68, L"****  PrinterDriverID Not Found  *****", 39);
  }
  if ( (a3 & 0x8000) != 0 && (v14 = v9[4]) != 0 && *(_QWORD *)(v14 + 40) && v13 )
  {
    DriverUi::DriverUiTelemetry::WriteDbgTraceInfo(
      "PSUI::PLoadCommonInfoRO",
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
      "PSUI::PLoadCommonInfoRO",
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
        "PSUI::PLoadCommonInfoRO",
        L"Calculate the maximum size needed to store JT expansion block.");
      *((_DWORD *)v9 + 14) = cbCalcJTExpSize(v22, v21, v9[4], (a3 >> 13) & 1);
      DriverUi::DriverUiTelemetry::WriteDbgTraceInfo(
        "PSUI::PLoadCommonInfoRO",
        L"Get information about OEM plugins and load them.");
      v24 = (_QWORD *)PGetOemPluginInfo(v23, *(_QWORD *)(v9[4] + 40LL), v9[4]);
      v9[6] = v24;
      if ( v24 )
      {
        *v24 = v9;
        DriverUi::DriverUiTelemetry::WriteDbgTraceInfo(
          "PSUI::PLoadCommonInfoRO",
          L"Preloads the plugins and keeps the DLL loaded.");
        if ( (unsigned int)BLoadOEMPluginModulesInternal(0) )
        {
          *(_DWORD *)v9 = 16;
          v9[1] = &PSUI::OemUIHelperFuncs;
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
      DriverUi::DriverUiTelemetry::WriteDbgTraceWarning("PSUI::PLoadCommonInfoRO", v26, (unsigned int)LastError);
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
    "PSUI::PLoadCommonInfoRO",
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
0x180136690  push    rbx
0x180136692  push    rbp
0x180136693  push    rsi
0x180136694  push    rdi
0x180136695  push    r12
0x180136697  push    r14
0x180136699  push    r15
0x18013669b  sub     rsp, 260h
0x1801366a2  mov     rax, cs:__security_cookie
0x1801366a9  xor     rax, rsp
0x1801366ac  mov     [rsp+298h+var_48], rax
0x1801366b4  mov     r12, [rsp+298h+arg_20]
0x1801366bc  mov     rdi, rdx
0x1801366bf  mov     r14, rcx
0x1801366c2  lea     rdx, aLoadsBasicInfo; "Loads basic information needed by the d"...
0x1801366c9  lea     rcx, aPsuiPloadcommo_0; "PSUI::PLoadCommonInfoRO"
0x1801366d0  mov     rsi, r9
0x1801366d3  mov     r15d, r8d
0x1801366d6  call    ?WriteDbgTraceInfo@DriverUiTelemetry@DriverUi@@SAXPEADPEAGZZ; DriverUi::DriverUiTelemetry::WriteDbgTraceInfo(char *,ushort *,...)
0x1801366db  mov     edx, 98h; uBytes
0x1801366e0  lea     ecx, [rdx-58h]; uFlags
0x1801366e3  call    cs:__imp_LocalAlloc
0x1801366e9  mov     rbx, rax
0x1801366ec  test    rax, rax
0x1801366ef  jz      loc_180136A21
0x1801366f5  lea     rax, aNull_0; "NULL"
0x1801366fc  test    rdi, rdi
0x1801366ff  mov     rcx, rdi
0x180136702  cmovz   rcx, rax; Src
0x180136706  call    DuplicateString
0x18013670b  mov     [rbx+10h], rax
0x18013670f  test    rax, rax
0x180136712  jz      loc_180136A21
0x180136718  mov     rax, [rsi]
0x18013671b  xor     edx, edx; Val
0x18013671d  mov     [rbx+20h], rax
0x180136721  mov     qword ptr [rsi], 0
0x180136728  lea     rsi, [rbx+44h]
0x18013672c  mov     rcx, rsi; void *
0x18013672f  mov     [rbx+18h], r15d
0x180136733  lea     r8d, [rdx+4Eh]; Size
0x180136737  mov     qword ptr [rbx+28h], 0
0x18013673f  call    memset_0
0x180136744  mov     rcx, [rbx+20h]
0x180136748  lea     rdx, aPrintconfigDll_1; "PrintConfig.dll"
0x18013674f  mov     rcx, [rcx+28h]; unsigned __int16 *
0x180136753  call    ?DoesFullPathMatchFile@@YA_NPEBG0@Z; DoesFullPathMatchFile(ushort const *,ushort const *)
0x180136758  movzx   ebp, al
0x18013675b  test    al, al
0x18013675d  jz      short loc_1801367D9
0x18013675f  lea     rdx, aTheDriverIsUsi; "The driver is using PrintConfig.dll."
0x180136766  lea     rcx, aPsuiPloadcommo_0; "PSUI::PLoadCommonInfoRO"
0x18013676d  call    ?WriteDbgTraceInfo@DriverUiTelemetry@DriverUi@@SAXPEADPEAGZZ; DriverUi::DriverUiTelemetry::WriteDbgTraceInfo(char *,ushort *,...)
0x180136772  bts     dword ptr [rbx+18h], 14h
0x180136777  lea     rdx, aAttemptToPopul; "Attempt to populate the cache change id"...
0x18013677e  lea     rcx, aPsuiPloadcommo_0; "PSUI::PLoadCommonInfoRO"
0x180136785  call    ?WriteDbgTraceInfo@DriverUiTelemetry@DriverUi@@SAXPEADPEAGZZ; DriverUi::DriverUiTelemetry::WriteDbgTraceInfo(char *,ushort *,...)
0x18013678a  lea     r8, [rbx+40h]
0x18013678e  mov     rdx, r14
0x180136791  mov     rcx, rdi
0x180136794  call    GetV4PrinterCacheChangeID
0x180136799  test    eax, eax
0x18013679b  js      short loc_1801367A2
0x18013679d  bts     dword ptr [rbx+18h], 15h
0x1801367a2  lea     rdx, aRetrieveThePri; "Retrieve the printer driver ID."
0x1801367a9  lea     rcx, aPsuiPloadcommo_0; "PSUI::PLoadCommonInfoRO"
0x1801367b0  call    ?WriteDbgTraceInfo@DriverUiTelemetry@DriverUi@@SAXPEADPEAGZZ; DriverUi::DriverUiTelemetry::WriteDbgTraceInfo(char *,ushort *,...)
0x1801367b5  mov     rdx, rsi
0x1801367b8  mov     rcx, r14
0x1801367bb  call    GetPrinterDriverIDAsString
0x1801367c0  test    eax, eax
0x1801367c2  jns     short loc_1801367D9
0x1801367c4  mov     r8d, 27h ; '''
0x1801367ca  lea     rdx, aPrinterdriveri_2; "****  PrinterDriverID Not Found  *****"
0x1801367d1  mov     rcx, rsi
0x1801367d4  call    CopyStringW
0x1801367d9  bt      r15d, 0Fh
0x1801367de  jnb     loc_180136874
0x1801367e4  mov     rax, [rbx+20h]
0x1801367e8  test    rax, rax
0x1801367eb  jz      loc_180136874
0x1801367f1  cmp     qword ptr [rax+28h], 0
0x1801367f6  jz      short loc_180136874
0x1801367f8  test    ebp, ebp
0x1801367fa  jz      short loc_180136874
0x1801367fc  lea     rdx, aGetTheFileDire; "Get the file directly from RemotePrintC"...
0x180136803  lea     rcx, aPsuiPloadcommo_0; "PSUI::PLoadCommonInfoRO"
0x18013680a  call    ?WriteDbgTraceInfo@DriverUiTelemetry@DriverUi@@SAXPEADPEAGZZ; DriverUi::DriverUiTelemetry::WriteDbgTraceInfo(char *,ushort *,...)
0x18013680f  lea     rdx, [rsp+298h+var_268]; struct RemotePrintConfigData **
0x180136814  mov     [rsp+298h+var_268], 0
0x18013681d  mov     rcx, r14; void *
0x180136820  call    ?CreateRemotePrintConfigData@RemotePrintConfigData@@SAJPEAXPEAPEAV1@@Z; RemotePrintConfigData::CreateRemotePrintConfigData(void *,RemotePrintConfigData * *)
0x180136825  test    eax, eax
0x180136827  js      loc_1801368C5
0x18013682d  mov     rdi, [rsp+298h+var_268]
0x180136832  xor     r8d, r8d
0x180136835  mov     r9b, 1
0x180136838  mov     rcx, rdi
0x18013683b  mov     rax, [rdi]
0x18013683e  lea     edx, [r8+2]
0x180136842  mov     rax, [rax+8]
0x180136846  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18013684b  mov     rcx, rax; pszSrc
0x18013684e  mov     edx, ebp
0x180136850  call    LoadRawBinaryData
0x180136855  mov     [rbx+28h], rax
0x180136859  test    rdi, rdi
0x18013685c  jz      short loc_1801368C5
0x18013685e  mov     rax, [rdi]
0x180136861  mov     edx, 1
0x180136866  mov     rcx, rdi
0x180136869  mov     rax, [rax+20h]
0x18013686d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180136872  jmp     short loc_1801368C5
0x180136874  lea     rdx, aGoThroughTheGe; "Go through the GetFilenameByRole becaus"...
0x18013687b  lea     rcx, aPsuiPloadcommo_0; "PSUI::PLoadCommonInfoRO"
0x180136882  call    ?WriteDbgTraceInfo@DriverUiTelemetry@DriverUi@@SAXPEADPEAGZZ; DriverUi::DriverUiTelemetry::WriteDbgTraceInfo(char *,ushort *,...)
0x180136887  xor     edx, edx; Val
0x180136889  lea     rcx, [rsp+298h+pszSrc]; void *
0x18013688e  mov     r8d, 208h; Size
0x180136894  call    memset_0
0x180136899  mov     r9d, 104h
0x18013689f  lea     r8, [rsp+298h+pszSrc]
0x1801368a4  mov     edx, 2
0x1801368a9  mov     rcx, r14
0x1801368ac  call    GetFilenameByRole
0x1801368b1  test    eax, eax
0x1801368b3  js      short loc_1801368C5
0x1801368b5  mov     edx, ebp
0x1801368b7  lea     rcx, [rsp+298h+pszSrc]; pszSrc
0x1801368bc  call    LoadRawBinaryData
0x1801368c1  mov     [rbx+28h], rax
0x1801368c5  mov     rcx, [rbx+28h]
0x1801368c9  test    rcx, rcx
0x1801368cc  jz      loc_1801369FA
0x1801368d2  xor     r8d, r8d
0x1801368d5  call    InitBinaryData
0x1801368da  mov     rdi, rax
0x1801368dd  mov     rax, [rbx+28h]
0x1801368e1  test    rdi, rdi
0x1801368e4  jz      short loc_1801368F4
0x1801368e6  cmp     dword ptr [rdi+38h], 0
0x1801368ea  jz      short loc_1801368F4
0x1801368ec  mov     esi, [rdi+38h]
0x1801368ef  add     rsi, rdi
0x1801368f2  jmp     short loc_1801368F6
0x1801368f4  xor     esi, esi
0x1801368f6  test    rax, rax
0x1801368f9  jz      loc_1801369FC
0x1801368ff  test    rdi, rdi
0x180136902  jz      loc_1801369FC
0x180136908  test    rsi, rsi
0x18013690b  jz      loc_1801369FC
0x180136911  lea     rbp, aPsuiPloadcommo_0; "PSUI::PLoadCommonInfoRO"
0x180136918  mov     rcx, rbp; char *
0x18013691b  lea     rdx, aCalculateTheMa; "Calculate the maximum size needed to st"...
0x180136922  call    ?WriteDbgTraceInfo@DriverUiTelemetry@DriverUi@@SAXPEADPEAGZZ; DriverUi::DriverUiTelemetry::WriteDbgTraceInfo(char *,ushort *,...)
0x180136927  mov     r8, [rbx+20h]
0x18013692b  mov     rdx, rsi
0x18013692e  shr     r15d, 0Dh
0x180136932  and     r15d, 1
0x180136936  mov     r9d, r15d
0x180136939  call    cbCalcJTExpSize
0x18013693e  lea     rdx, aGetInformation; "Get information about OEM plugins and l"...
0x180136945  mov     [rbx+38h], eax
0x180136948  mov     rcx, rbp; char *
0x18013694b  call    ?WriteDbgTraceInfo@DriverUiTelemetry@DriverUi@@SAXPEADPEAGZZ; DriverUi::DriverUiTelemetry::WriteDbgTraceInfo(char *,ushort *,...)
0x180136950  mov     rdx, [rbx+20h]
0x180136954  mov     r8, rdx
0x180136957  mov     rdx, [rdx+28h]
0x18013695b  call    PGetOemPluginInfo
0x180136960  mov     [rbx+30h], rax
0x180136964  test    rax, rax
0x180136967  jnz     short loc_18013699A
0x180136969  call    cs:__imp_GetLastError
0x18013696f  test    eax, eax
0x180136971  jle     short loc_18013697B
0x180136973  movzx   eax, ax
0x180136976  or      eax, 80070000h
0x18013697b  lea     rdx, aCannotGetOemPl_0; "Cannot get OEM plugins info (hr: 0x%x)."
0x180136982  mov     rcx, rbp; char *
0x180136985  mov     r8d, eax
0x180136988  call    ?WriteDbgTraceWarning@DriverUiTelemetry@DriverUi@@SAXPEADPEAGZZ; DriverUi::DriverUiTelemetry::WriteDbgTraceWarning(char *,ushort *,...)
0x18013698d  mov     rcx, rdi
0x180136990  call    FreeBinaryData
0x180136995  jmp     loc_180136A34
0x18013699a  lea     rdx, aPreloadsThePlu; "Preloads the plugins and keeps the DLL "...
0x1801369a1  mov     [rax], rbx
0x1801369a4  mov     rcx, rbp; char *
0x1801369a7  call    ?WriteDbgTraceInfo@DriverUiTelemetry@DriverUi@@SAXPEADPEAGZZ; DriverUi::DriverUiTelemetry::WriteDbgTraceInfo(char *,ushort *,...)
0x1801369ac  mov     rdx, [rbx+30h]
0x1801369b0  xor     r8d, r8d
0x1801369b3  xor     ecx, ecx; this
0x1801369b5  call    BLoadOEMPluginModulesInternal
0x1801369ba  test    eax, eax
0x1801369bc  jnz     short loc_1801369D9
0x1801369be  call    cs:__imp_GetLastError
0x1801369c4  test    eax, eax
0x1801369c6  jle     short loc_1801369D0
0x1801369c8  movzx   eax, ax
0x1801369cb  or      eax, 80070000h
0x1801369d0  lea     rdx, aCannotLoadOemP; "Cannot load OEM plugins (hr: 0x%x)."
0x1801369d7  jmp     short loc_180136982
0x1801369d9  lea     rax, ?OemUIHelperFuncs@PSUI@@3U_OEMUIPROCS@@B; _OEMUIPROCS const PSUI::OemUIHelperFuncs
0x1801369e0  mov     dword ptr [rbx], 10h
0x1801369e6  mov     [rbx+8], rax
0x1801369ea  mov     rax, rbx
0x1801369ed  mov     dword ptr [rbx+3Ch], 1
0x1801369f4  mov     [r12], rdi
0x1801369f8  jmp     short loc_180136A3E
0x1801369fa  xor     edi, edi
0x1801369fc  call    cs:__imp_GetLastError
0x180136a02  test    eax, eax
0x180136a04  jle     short loc_180136A0E
0x180136a06  movzx   eax, ax
0x180136a09  or      eax, 80070000h
0x180136a0e  lea     rdx, aCannotLoadPrin_1; "Cannot load printer description data (h"...
0x180136a15  lea     rcx, aPsuiPloadcommo_0; "PSUI::PLoadCommonInfoRO"
0x180136a1c  jmp     loc_180136985
0x180136a21  lea     rdx, aMemoryAllocati_1; "Memory allocation failed."
0x180136a28  lea     rcx, aPsuiPloadcommo_0; "PSUI::PLoadCommonInfoRO"
0x180136a2f  call    ?WriteDbgTraceWarning@DriverUiTelemetry@DriverUi@@SAXPEADPEAGZZ; DriverUi::DriverUiTelemetry::WriteDbgTraceWarning(char *,ushort *,...)
0x180136a34  mov     rcx, rbx; hMem
0x180136a37  call    PSUI__VFreeCommonInfoRO
0x180136a3c  xor     eax, eax
0x180136a3e  mov     rcx, [rsp+298h+var_48]
0x180136a46  xor     rcx, rsp; StackCookie
0x180136a49  call    __security_check_cookie
0x180136a4e  add     rsp, 260h
0x180136a55  pop     r15
0x180136a57  pop     r14
0x180136a59  pop     r12
0x180136a5b  pop     rdi
0x180136a5c  pop     rsi
0x180136a5d  pop     rbp
0x180136a5e  pop     rbx
0x180136a5f  retn
```
