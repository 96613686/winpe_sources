# PSUI::PLoadCommonInfo(void *,ushort *,ulong)

- ea: `0x18013c480`
- end: `0x18013c7df`
- name: `?PLoadCommonInfo@PSUI@@YAPEAU_COMMONINFO@1@PEAXPEAGK@Z`
- size: `863`
- prototype: `struct PSUI::_COMMONINFO *__fastcall(PSUI *this, WCHAR *, unsigned __int16 *)`
- caller_count: `14`
- callee_count: `13`
- tags: `file_ops, loader_planting, broker_com_uri`

## callers

- `0x180131324`
- `0x180132a00`
- `0x180133fc0`
- `0x1801343c0`
- `0x180134ce0`
- `0x180136728`
- `0x180137744`
- `0x180137dc4`
- `0x180139bb4`
- `0x180139f20`
- `0x18013b9fc`
- `0x18013c170`
- `0x18013df94`
- `0x18013e3a8`

## callees

- `0x180107214`
- `0x180108e2c`
- `0x18013bda0`
- `0x18013c480`
- `0x18013dcf0`
- `0x18014f63c`
- `0x18014fa24`
- `0x18014fae0`
- `0x180151098`
- `0x180151750`
- `0x180154838`
- `0x1801558d0`
- `0x1801ad39c`

## import_xrefs

- `KERNEL32!DeleteFileW` at `0x18013c66b`
- `KERNEL32!DeleteFileW` at `0x18013c66b`
- `KERNEL32!GetLastError` at `0x18013c526`
- `KERNEL32!GetLastError` at `0x18013c5c7`
- `KERNEL32!GetLastError` at `0x18013c609`
- `KERNEL32!GetLastError` at `0x18013c6ed`
- `KERNEL32!GetLastError` at `0x18013c71e`
- `KERNEL32!GetLastError` at `0x18013c74f`
- `KERNEL32!GetLastError` at `0x18013c77d`
- `KERNEL32!GetLastError` at `0x18013c526`
- `KERNEL32!GetLastError` at `0x18013c5c7`
- `KERNEL32!GetLastError` at `0x18013c609`
- `KERNEL32!GetLastError` at `0x18013c6ed`
- `KERNEL32!GetLastError` at `0x18013c71e`
- `KERNEL32!GetLastError` at `0x18013c74f`
- `KERNEL32!GetLastError` at `0x18013c77d`
- `KERNEL32!LocalFree` at `0x18013c5b1`
- `KERNEL32!LocalFree` at `0x18013c67a`
- `KERNEL32!LocalFree` at `0x18013c6af`
- `KERNEL32!LocalFree` at `0x18013c7b1`
- `KERNEL32!LocalFree` at `0x18013c7c5`
- `KERNEL32!LocalFree` at `0x18013c5b1`
- `KERNEL32!LocalFree` at `0x18013c67a`
- `KERNEL32!LocalFree` at `0x18013c6af`
- `KERNEL32!LocalFree` at `0x18013c7b1`
- `KERNEL32!LocalFree` at `0x18013c7c5`
- `KERNEL32!LocalAlloc` at `0x18013c4b4`
- `KERNEL32!LocalAlloc` at `0x18013c4b4`
- `WINSPOOL!OpenPrinterW` at `0x18013c516`
- `WINSPOOL!OpenPrinterW` at `0x18013c516`

## string_xrefs

- `0x18013c789`: `Cannot load read only common info: %d\n`
- `0x18013c535`: `OpenPrinter failed for '%ws': %d\n`
- `0x18013c75b`: `Cannot load OEM plugins: %d\n`
- `0x18013c72a`: `Cannot get OEM plugins info: %d\n`
- `0x18013c53f`: `PSUI::PLoadCommonInfo`
- `0x18013c5dd`: `PSUI::PLoadCommonInfo`
- `0x18013c61f`: `PSUI::PLoadCommonInfo`
- `0x18013c79c`: `PSUI::PLoadCommonInfo`

## pseudocode

```c
struct PSUI::_COMMONINFO *__fastcall PSUI::PLoadCommonInfo(PSUI *this, WCHAR *a2, unsigned __int16 *a3)
{
  int v4; // edi
  _QWORD *v5; // rbx
  wchar_t *v6; // rcx
  HLOCAL v7; // rax
  DWORD v8; // eax
  struct PSUI::_COMMONINFO *v9; // rdx
  __int64 v10; // rdx
  BYTE *Printer; // rax
  BYTE *v12; // rsi
  int v13; // eax
  DWORD v14; // eax
  HLOCAL v15; // rsi
  DWORD v16; // eax
  const wchar_t *v17; // rcx
  wchar_t *FilenameWithExtName; // rax
  wchar_t *v19; // rsi
  __int64 *v20; // rsi
  __int64 v21; // rax
  HLOCAL v22; // rcx
  __int64 v23; // rdx
  __int64 v24; // rcx
  __int64 v25; // rax
  DWORD v26; // eax
  _QWORD *v27; // rax
  DWORD v28; // eax
  DWORD LastError; // eax
  DWORD v31; // eax
  void *v32; // rcx
  HANDLE phPrinter; // [rsp+60h] [rbp+30h] BYREF
  int v34; // [rsp+70h] [rbp+40h] BYREF
  HLOCAL hMem; // [rsp+78h] [rbp+48h] BYREF

  phPrinter = this;
  v4 = (int)a3;
  v5 = LocalAlloc(0x40u, ((unsigned __int8)a3 & 0x10) != 0 ? 1512LL : 160LL);
  if ( !v5 )
    goto LABEL_41;
  v6 = a2;
  if ( !a2 )
    v6 = L"NULL";
  v7 = DuplicateString(v6);
  v5[3] = v7;
  if ( v7 )
  {
    v5[2] = v5;
    *((_DWORD *)v5 + 10) = v4;
    if ( (v4 & 5) == 0
      || OpenPrinterW(
           a2,
           &phPrinter,
           (LPPRINTER_DEFAULTSW)((unsigned __int64)qword_1802A4A30 & -(__int64)((v4 & 4) != 0))) )
    {
      v10 = 2;
      v5[4] = phPrinter;
      if ( (v4 & 2) == 0 )
        goto LABEL_17;
      v34 = 1539;
      Printer = MyGetPrinter(phPrinter, 2u);
      v12 = Printer;
      if ( Printer && (*(_QWORD *)Printer || BGetPrinterDataDWord(phPrinter, L"InitDriverVersion", (BYTE *)&v34))
        || (v13 = 0, v34 = 0, v12) )
      {
        LocalFree(v12);
        v13 = v34;
      }
      if ( v13 == 1539 )
      {
LABEL_17:
        hMem = MyGetPrinterDriver(phPrinter, v10, 3u);
        v15 = hMem;
        if ( hMem )
        {
          if ( (v4 & 8) != 0 )
            BSetPrinterDataDWord(phPrinter, L"InitDriverVersion", 1539);
          if ( (v4 & 0x40) != 0 )
          {
            v17 = (const wchar_t *)*((_QWORD *)v15 + 4);
            if ( v17 )
            {
              FilenameWithExtName = GenerateFilenameWithExtName(v17);
              v19 = FilenameWithExtName;
              if ( FilenameWithExtName )
              {
                DeleteFileW(FilenameWithExtName);
                LocalFree(v19);
              }
            }
          }
          v20 = v5 + 8;
          v21 = PSUI::PAcquireCommonInfoRO(phPrinter, a2, v4, (__int64 *)&hMem, v5 + 8);
          v22 = hMem;
          v5[6] = v21;
          if ( v22 )
            LocalFree(v22);
          v23 = v5[6];
          if ( v23 && (v24 = *v20) != 0 )
          {
            if ( *(_DWORD *)(v24 + 56) )
              v25 = v24 + *(unsigned int *)(v24 + 56);
            else
              v25 = 0;
            v5[9] = v25;
            if ( v25 )
            {
              v27 = (_QWORD *)PGetOemPluginInfo(
                                v24,
                                *(const wchar_t **)(*(_QWORD *)(v23 + 32) + 40LL),
                                *(_QWORD *)(v23 + 32));
              v5[10] = v27;
              if ( v27 )
              {
                *v27 = v5;
                if ( (unsigned int)BLoadOEMPluginModulesInternal((UniDrvUI *)v5, v5[10], 1) )
                {
                  *(_DWORD *)v5 = 16;
                  v5[1] = &PSUI::OemUIHelperFuncs;
                  return (struct PSUI::_COMMONINFO *)v5;
                }
                LastError = GetLastError();
                DriverUi::DriverUiTelemetry::WriteDbgTraceWarning(
                  "PSUI::PLoadCommonInfo",
                  L"Cannot load OEM plugins: %d\n",
                  LastError);
              }
              else
              {
                v28 = GetLastError();
                DriverUi::DriverUiTelemetry::WriteDbgTraceWarning(
                  "PSUI::PLoadCommonInfo",
                  L"Cannot get OEM plugins info: %d\n",
                  v28);
              }
            }
            else
            {
              v26 = GetLastError();
              DriverUi::DriverUiTelemetry::WriteDbgTraceWarning(
                "PSUI::PLoadCommonInfo",
                L"Cannot load printer description data: %d\n",
                v26);
            }
          }
          else
          {
            v31 = GetLastError();
            DriverUi::DriverUiTelemetry::WriteDbgTraceWarning(
              "PSUI::PLoadCommonInfo",
              L"Cannot load read only common info: %d\n",
              v31);
          }
        }
        else
        {
          v16 = GetLastError();
          DriverUi::DriverUiTelemetry::WriteDbgTraceWarning(
            "PSUI::PLoadCommonInfo",
            L"Cannot get printer driver info: %d\n",
            v16);
        }
      }
      else
      {
        v14 = GetLastError();
        DriverUi::DriverUiTelemetry::WriteDbgTraceInfo(
          "PSUI::PLoadCommonInfo",
          L"Printer not fully initialized yet: %d\n",
          v14);
      }
    }
    else
    {
      v8 = GetLastError();
      DriverUi::DriverUiTelemetry::WriteDbgTraceWarning(
        "PSUI::PLoadCommonInfo",
        L"OpenPrinter failed for '%ws': %d\n",
        a2,
        v8);
    }
    PSUI::VFreeCommonInfo((PSUI *)v5, v9);
  }
  else
  {
LABEL_41:
    DriverUi::DriverUiTelemetry::WriteDbgTraceWarning("PSUI::PLoadCommonInfo", L"Memory allocation failed\n");
    v32 = (void *)v5[3];
    if ( v32 )
      LocalFree(v32);
    if ( v5 )
      LocalFree(v5);
  }
  return 0;
}

```

## disassembly

```asm
0x18013c480  mov     [rsp-28h+phPrinter], rcx
0x18013c485  push    rbp
0x18013c486  push    rbx
0x18013c487  push    rsi
0x18013c488  push    rdi
0x18013c489  push    r14
0x18013c48b  mov     rbp, rsp
0x18013c48e  sub     rsp, 30h
0x18013c492  mov     r14, rdx
0x18013c495  mov     eax, r8d
0x18013c498  and     al, 10h
0x18013c49a  mov     ecx, 40h ; '@'; uFlags
0x18013c49f  neg     al
0x18013c4a1  mov     edi, r8d
0x18013c4a4  sbb     rdx, rdx
0x18013c4a7  and     edx, 548h
0x18013c4ad  add     rdx, 0A0h; uBytes
0x18013c4b4  call    cs:__imp_LocalAlloc
0x18013c4bb  nop     dword ptr [rax+rax+00h]
0x18013c4c0  mov     rbx, rax
0x18013c4c3  test    rax, rax
0x18013c4c6  jz      loc_18013C795
0x18013c4cc  lea     rax, aNull_0; "NULL"
0x18013c4d3  test    r14, r14
0x18013c4d6  mov     rcx, r14
0x18013c4d9  cmovz   rcx, rax; Src
0x18013c4dd  call    DuplicateString
0x18013c4e2  mov     [rbx+18h], rax
0x18013c4e6  test    rax, rax
0x18013c4e9  jz      loc_18013C795
0x18013c4ef  mov     [rbx+10h], rbx
0x18013c4f3  mov     [rbx+28h], edi
0x18013c4f6  test    dil, 5
0x18013c4fa  jz      short loc_18013C558
0x18013c4fc  mov     eax, edi
0x18013c4fe  lea     rcx, qword_1802A4A30
0x18013c505  and     al, 4
0x18013c507  lea     rdx, [rbp+phPrinter]; phPrinter
0x18013c50b  neg     al
0x18013c50d  sbb     r8, r8
0x18013c510  and     r8, rcx; pDefault
0x18013c513  mov     rcx, r14; pPrinterName
0x18013c516  call    cs:__imp_OpenPrinterW
0x18013c51d  nop     dword ptr [rax+rax+00h]
0x18013c522  test    eax, eax
0x18013c524  jnz     short loc_18013C558
0x18013c526  call    cs:__imp_GetLastError
0x18013c52d  nop     dword ptr [rax+rax+00h]
0x18013c532  mov     r8, r14
0x18013c535  lea     rdx, aOpenprinterFai; "OpenPrinter failed for '%ws': %d\n"
0x18013c53c  mov     r9d, eax
0x18013c53f  lea     rcx, aPsuiPloadcommo; "PSUI::PLoadCommonInfo"
0x18013c546  call    ?WriteDbgTraceWarning@DriverUiTelemetry@DriverUi@@SAXPEADPEAGZZ; DriverUi::DriverUiTelemetry::WriteDbgTraceWarning(char *,ushort *,...)
0x18013c54b  mov     rcx, rbx; this
0x18013c54e  call    ?VFreeCommonInfo@PSUI@@YAXPEAU_COMMONINFO@1@@Z; PSUI::VFreeCommonInfo(PSUI::_COMMONINFO *)
0x18013c553  jmp     loc_18013C7D1
0x18013c558  mov     rax, [rbp+phPrinter]
0x18013c55c  mov     edx, 2; Level
0x18013c561  mov     [rbx+20h], rax
0x18013c565  test    dl, dil
0x18013c568  jz      loc_18013C5EE
0x18013c56e  mov     rcx, [rbp+phPrinter]; hPrinter
0x18013c572  mov     [rbp+arg_10], 603h
0x18013c579  call    MyGetPrinter
0x18013c57e  mov     rsi, rax
0x18013c581  test    rax, rax
0x18013c584  jz      short loc_18013C5A4
0x18013c586  cmp     qword ptr [rax], 0
0x18013c58a  jnz     short loc_18013C5AE
0x18013c58c  mov     rcx, [rbp+phPrinter]
0x18013c590  lea     r8, [rbp+arg_10]
0x18013c594  lea     rdx, aInitdriververs; "InitDriverVersion"
0x18013c59b  call    BGetPrinterDataDWord
0x18013c5a0  test    eax, eax
0x18013c5a2  jnz     short loc_18013C5AE
0x18013c5a4  xor     eax, eax
0x18013c5a6  mov     [rbp+arg_10], eax
0x18013c5a9  test    rsi, rsi
0x18013c5ac  jz      short loc_18013C5C0
0x18013c5ae  mov     rcx, rsi; hMem
0x18013c5b1  call    cs:__imp_LocalFree
0x18013c5b8  nop     dword ptr [rax+rax+00h]
0x18013c5bd  mov     eax, [rbp+arg_10]
0x18013c5c0  cmp     eax, 603h
0x18013c5c5  jz      short loc_18013C5EE
0x18013c5c7  call    cs:__imp_GetLastError
0x18013c5ce  nop     dword ptr [rax+rax+00h]
0x18013c5d3  mov     r8d, eax
0x18013c5d6  lea     rdx, aPrinterNotFull; "Printer not fully initialized yet: %d\n"
0x18013c5dd  lea     rcx, aPsuiPloadcommo; "PSUI::PLoadCommonInfo"
0x18013c5e4  call    ?WriteDbgTraceInfo@DriverUiTelemetry@DriverUi@@SAXPEADPEAGZZ; DriverUi::DriverUiTelemetry::WriteDbgTraceInfo(char *,ushort *,...)
0x18013c5e9  jmp     loc_18013C54B
0x18013c5ee  mov     rcx, [rbp+phPrinter]; hPrinter
0x18013c5f2  mov     r8d, 3
0x18013c5f8  call    MyGetPrinterDriver
0x18013c5fd  mov     [rbp+hMem], rax
0x18013c601  mov     rsi, rax
0x18013c604  test    rax, rax
0x18013c607  jnz     short loc_18013C630
0x18013c609  call    cs:__imp_GetLastError
0x18013c610  nop     dword ptr [rax+rax+00h]
0x18013c615  lea     rdx, aCannotGetPrint_0; "Cannot get printer driver info: %d\n"
0x18013c61c  mov     r8d, eax
0x18013c61f  lea     rcx, aPsuiPloadcommo; "PSUI::PLoadCommonInfo"
0x18013c626  call    ?WriteDbgTraceWarning@DriverUiTelemetry@DriverUi@@SAXPEADPEAGZZ; DriverUi::DriverUiTelemetry::WriteDbgTraceWarning(char *,ushort *,...)
0x18013c62b  jmp     loc_18013C54B
0x18013c630  test    dil, 8
0x18013c634  jz      short loc_18013C64C
0x18013c636  mov     rcx, [rbp+phPrinter]
0x18013c63a  lea     rdx, aInitdriververs; "InitDriverVersion"
0x18013c641  mov     r8d, 603h
0x18013c647  call    BSetPrinterDataDWord
0x18013c64c  test    dil, 40h
0x18013c650  jz      short loc_18013C686
0x18013c652  mov     rcx, [rsi+20h]; pszSrc
0x18013c656  test    rcx, rcx
0x18013c659  jz      short loc_18013C686
0x18013c65b  call    GenerateFilenameWithExtName
0x18013c660  mov     rsi, rax
0x18013c663  test    rax, rax
0x18013c666  jz      short loc_18013C686
0x18013c668  mov     rcx, rax; lpFileName
0x18013c66b  call    cs:__imp_DeleteFileW
0x18013c672  nop     dword ptr [rax+rax+00h]
0x18013c677  mov     rcx, rsi; hMem
0x18013c67a  call    cs:__imp_LocalFree
0x18013c681  nop     dword ptr [rax+rax+00h]
0x18013c686  mov     rcx, [rbp+phPrinter]; void *
0x18013c68a  lea     rsi, [rbx+40h]
0x18013c68e  lea     r9, [rbp+hMem]
0x18013c692  mov     [rsp+30h+var_10], rsi; __int64
0x18013c697  mov     r8d, edi
0x18013c69a  mov     rdx, r14; pPrinterName
0x18013c69d  call    PSUI__PAcquireCommonInfoRO
0x18013c6a2  mov     rcx, [rbp+hMem]; hMem
0x18013c6a6  mov     [rbx+30h], rax
0x18013c6aa  test    rcx, rcx
0x18013c6ad  jz      short loc_18013C6BB
0x18013c6af  call    cs:__imp_LocalFree
0x18013c6b6  nop     dword ptr [rax+rax+00h]
0x18013c6bb  mov     rdx, [rbx+30h]
0x18013c6bf  test    rdx, rdx
0x18013c6c2  jz      loc_18013C77D
0x18013c6c8  mov     rcx, [rsi]
0x18013c6cb  test    rcx, rcx
0x18013c6ce  jz      loc_18013C77D
0x18013c6d4  cmp     dword ptr [rcx+38h], 0
0x18013c6d8  jz      short loc_18013C6E2
0x18013c6da  mov     eax, [rcx+38h]
0x18013c6dd  add     rax, rcx
0x18013c6e0  jmp     short loc_18013C6E4
0x18013c6e2  xor     eax, eax
0x18013c6e4  mov     [rbx+48h], rax
0x18013c6e8  test    rax, rax
0x18013c6eb  jnz     short loc_18013C705
0x18013c6ed  call    cs:__imp_GetLastError
0x18013c6f4  nop     dword ptr [rax+rax+00h]
0x18013c6f9  lea     rdx, aCannotLoadPrin; "Cannot load printer description data: %"...
0x18013c700  jmp     loc_18013C61C
0x18013c705  mov     rdx, [rdx+20h]
0x18013c709  mov     r8, rdx
0x18013c70c  mov     rdx, [rdx+28h]
0x18013c710  call    PGetOemPluginInfo
0x18013c715  mov     [rbx+50h], rax
0x18013c719  test    rax, rax
0x18013c71c  jnz     short loc_18013C736
0x18013c71e  call    cs:__imp_GetLastError
0x18013c725  nop     dword ptr [rax+rax+00h]
0x18013c72a  lea     rdx, aCannotGetOemPl; "Cannot get OEM plugins info: %d\n"
0x18013c731  jmp     loc_18013C61C
0x18013c736  mov     [rax], rbx
0x18013c739  mov     r8d, 1
0x18013c73f  mov     rdx, [rbx+50h]
0x18013c743  mov     rcx, rbx; this
0x18013c746  call    BLoadOEMPluginModulesInternal
0x18013c74b  test    eax, eax
0x18013c74d  jnz     short loc_18013C767
0x18013c74f  call    cs:__imp_GetLastError
0x18013c756  nop     dword ptr [rax+rax+00h]
0x18013c75b  lea     rdx, aCannotLoadOemP_0; "Cannot load OEM plugins: %d\n"
0x18013c762  jmp     loc_18013C61C
0x18013c767  lea     rax, ?OemUIHelperFuncs@PSUI@@3U_OEMUIPROCS@@B; _OEMUIPROCS const PSUI::OemUIHelperFuncs
0x18013c76e  mov     dword ptr [rbx], 10h
0x18013c774  mov     [rbx+8], rax
0x18013c778  mov     rax, rbx
0x18013c77b  jmp     short loc_18013C7D3
0x18013c77d  call    cs:__imp_GetLastError
0x18013c784  nop     dword ptr [rax+rax+00h]
0x18013c789  lea     rdx, aCannotLoadRead; "Cannot load read only common info: %d\n"
0x18013c790  jmp     loc_18013C61C
0x18013c795  lea     rdx, aMemoryAllocati; "Memory allocation failed\n"
0x18013c79c  lea     rcx, aPsuiPloadcommo; "PSUI::PLoadCommonInfo"
0x18013c7a3  call    ?WriteDbgTraceWarning@DriverUiTelemetry@DriverUi@@SAXPEADPEAGZZ; DriverUi::DriverUiTelemetry::WriteDbgTraceWarning(char *,ushort *,...)
0x18013c7a8  mov     rcx, [rbx+18h]; hMem
0x18013c7ac  test    rcx, rcx
0x18013c7af  jz      short loc_18013C7BD
0x18013c7b1  call    cs:__imp_LocalFree
0x18013c7b8  nop     dword ptr [rax+rax+00h]
0x18013c7bd  test    rbx, rbx
0x18013c7c0  jz      short loc_18013C7D1
0x18013c7c2  mov     rcx, rbx; hMem
0x18013c7c5  call    cs:__imp_LocalFree
0x18013c7cc  nop     dword ptr [rax+rax+00h]
0x18013c7d1  xor     eax, eax
0x18013c7d3  add     rsp, 30h
0x18013c7d7  pop     r14
0x18013c7d9  pop     rdi
0x18013c7da  pop     rsi
0x18013c7db  pop     rbx
0x18013c7dc  pop     rbp
0x18013c7dd  retn
```
