# PSUI::PLoadCommonInfo(void *,ushort *,ulong)

- ea: `0x180136374`
- end: `0x180136688`
- name: `?PLoadCommonInfo@PSUI@@YAPEAU_COMMONINFO@1@PEAXPEAGK@Z`
- size: `788`
- prototype: `struct PSUI::_COMMONINFO *(PSUI *__hidden this, void *, unsigned __int16 *, unsigned int)`
- caller_count: `14`
- callee_count: `12`
- tags: `file_ops, loader_planting, broker_com_uri`

## callers

- `0x18012b4e4`
- `0x18012cb5c`
- `0x18012e0a8`
- `0x18012e4a0`
- `0x18012ed9c`
- `0x1801307b0`
- `0x1801317a8`
- `0x180131dcc`
- `0x180133b68`
- `0x180133ecc`
- `0x18013592c`
- `0x180136084`
- `0x180137d14`
- `0x180138104`

## callees

- `0x180102674`
- `0x18010427c`
- `0x180135ccc`
- `0x180136374`
- `0x180137ac0`
- `0x180148a3c`
- `0x180148d9c`
- `0x180148e38`
- `0x18014a300`
- `0x18014d948`
- `0x18014e970`
- `0x1801a5b38`

## import_xrefs

- `KERNEL32!DeleteFileW` at `0x18013654b`
- `KERNEL32!DeleteFileW` at `0x18013654b`
- `KERNEL32!GetLastError` at `0x18013640e`
- `KERNEL32!GetLastError` at `0x18013649f`
- `KERNEL32!GetLastError` at `0x1801364db`
- `KERNEL32!GetLastError` at `0x1801365bb`
- `KERNEL32!GetLastError` at `0x1801365e6`
- `KERNEL32!GetLastError` at `0x180136611`
- `KERNEL32!GetLastError` at `0x180136639`
- `KERNEL32!GetLastError` at `0x18013640e`
- `KERNEL32!GetLastError` at `0x18013649f`
- `KERNEL32!GetLastError` at `0x1801364db`
- `KERNEL32!GetLastError` at `0x1801365bb`
- `KERNEL32!GetLastError` at `0x1801365e6`
- `KERNEL32!GetLastError` at `0x180136611`
- `KERNEL32!GetLastError` at `0x180136639`
- `KERNEL32!LocalFree` at `0x18013648f`
- `KERNEL32!LocalFree` at `0x180136554`
- `KERNEL32!LocalFree` at `0x180136583`
- `KERNEL32!LocalFree` at `0x180136667`
- `KERNEL32!LocalFree` at `0x180136675`
- `KERNEL32!LocalFree` at `0x18013648f`
- `KERNEL32!LocalFree` at `0x180136554`
- `KERNEL32!LocalFree` at `0x180136583`
- `KERNEL32!LocalFree` at `0x180136667`
- `KERNEL32!LocalFree` at `0x180136675`
- `KERNEL32!LocalAlloc` at `0x1801363a8`
- `KERNEL32!LocalAlloc` at `0x1801363a8`
- `WINSPOOL!SetPrinterDataW` at `0x180136526`
- `WINSPOOL!SetPrinterDataW` at `0x180136526`
- `WINSPOOL!OpenPrinterW` at `0x180136404`
- `WINSPOOL!OpenPrinterW` at `0x180136404`

## string_xrefs

- `0x180136417`: `OpenPrinter failed for '%ws': %d\n`
- `0x180136617`: `Cannot load OEM plugins: %d\n`
- `0x18013663f`: `Cannot load read only common info: %d\n`
- `0x1801365ec`: `Cannot get OEM plugins info: %d\n`
- `0x180136421`: `PSUI::PLoadCommonInfo`
- `0x1801364af`: `PSUI::PLoadCommonInfo`
- `0x1801364eb`: `PSUI::PLoadCommonInfo`
- `0x180136652`: `PSUI::PLoadCommonInfo`

## pseudocode

```c
struct PSUI::_COMMONINFO *__fastcall PSUI::PLoadCommonInfo(PSUI *this, WCHAR *a2, unsigned __int16 *a3)
{
  int v4; // esi
  _QWORD *v5; // rbx
  wchar_t *v6; // rcx
  __int64 v7; // rax
  DWORD v8; // eax
  struct PSUI::_COMMONINFO *v9; // rdx
  _QWORD *Printer; // rax
  void *v11; // rdi
  int v12; // eax
  DWORD v13; // eax
  HLOCAL v14; // rdi
  DWORD v15; // eax
  const wchar_t *v16; // rcx
  const WCHAR *FilenameWithExtName; // rax
  WCHAR *v18; // rdi
  __int64 *v19; // rdi
  __int64 v20; // rax
  HLOCAL v21; // rcx
  __int64 v22; // rdx
  __int64 v23; // rcx
  __int64 v24; // rax
  DWORD v25; // eax
  _QWORD *v26; // rax
  DWORD v27; // eax
  DWORD LastError; // eax
  DWORD v30; // eax
  void *v31; // rcx
  HANDLE phPrinter; // [rsp+60h] [rbp+30h] BYREF
  int pData; // [rsp+70h] [rbp+40h] BYREF
  HLOCAL hMem; // [rsp+78h] [rbp+48h]

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
           (LPPRINTER_DEFAULTSW)((unsigned __int64)qword_18029D8C0 & -(__int64)((v4 & 4) != 0))) )
    {
      v5[4] = phPrinter;
      if ( (v4 & 2) == 0 )
        goto LABEL_17;
      pData = 1539;
      Printer = (_QWORD *)MyGetPrinter(phPrinter, 2u);
      v11 = Printer;
      if ( Printer && (*Printer || (unsigned int)BGetPrinterDataDWord(phPrinter, L"InitDriverVersion", &pData))
        || (v12 = 0, pData = 0, v11) )
      {
        LocalFree(v11);
        v12 = pData;
      }
      if ( v12 == 1539 )
      {
LABEL_17:
        hMem = (HLOCAL)MyGetPrinterDriver(phPrinter);
        v14 = hMem;
        if ( hMem )
        {
          if ( (v4 & 8) != 0 )
          {
            pData = 1539;
            SetPrinterDataW(phPrinter, (LPWSTR)L"InitDriverVersion", 4u, (LPBYTE)&pData, 4u);
          }
          if ( (v4 & 0x40) != 0 )
          {
            v16 = (const wchar_t *)*((_QWORD *)v14 + 4);
            if ( v16 )
            {
              FilenameWithExtName = (const WCHAR *)GenerateFilenameWithExtName(v16);
              v18 = (WCHAR *)FilenameWithExtName;
              if ( FilenameWithExtName )
              {
                DeleteFileW(FilenameWithExtName);
                LocalFree(v18);
              }
            }
          }
          v19 = v5 + 8;
          v20 = PSUI::PAcquireCommonInfoRO(phPrinter, a2, (__int64)(v5 + 8));
          v21 = hMem;
          v5[6] = v20;
          if ( v21 )
            LocalFree(v21);
          v22 = v5[6];
          if ( v22 && (v23 = *v19) != 0 )
          {
            if ( *(_DWORD *)(v23 + 56) )
              v24 = v23 + *(unsigned int *)(v23 + 56);
            else
              v24 = 0;
            v5[9] = v24;
            if ( v24 )
            {
              v26 = (_QWORD *)PGetOemPluginInfo(v23, *(_QWORD *)(*(_QWORD *)(v22 + 32) + 40LL), *(_QWORD *)(v22 + 32));
              v5[10] = v26;
              if ( v26 )
              {
                *v26 = v5;
                if ( (unsigned int)BLoadOEMPluginModulesInternal((UniDrvUI *)v5) )
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
                v27 = GetLastError();
                DriverUi::DriverUiTelemetry::WriteDbgTraceWarning(
                  "PSUI::PLoadCommonInfo",
                  L"Cannot get OEM plugins info: %d\n",
                  v27);
              }
            }
            else
            {
              v25 = GetLastError();
              DriverUi::DriverUiTelemetry::WriteDbgTraceWarning(
                "PSUI::PLoadCommonInfo",
                L"Cannot load printer description data: %d\n",
                v25);
            }
          }
          else
          {
            v30 = GetLastError();
            DriverUi::DriverUiTelemetry::WriteDbgTraceWarning(
              "PSUI::PLoadCommonInfo",
              L"Cannot load read only common info: %d\n",
              v30);
          }
        }
        else
        {
          v15 = GetLastError();
          DriverUi::DriverUiTelemetry::WriteDbgTraceWarning(
            "PSUI::PLoadCommonInfo",
            L"Cannot get printer driver info: %d\n",
            v15);
        }
      }
      else
      {
        v13 = GetLastError();
        DriverUi::DriverUiTelemetry::WriteDbgTraceInfo(
          "PSUI::PLoadCommonInfo",
          L"Printer not fully initialized yet: %d\n",
          v13);
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
    v31 = (void *)v5[3];
    if ( v31 )
      LocalFree(v31);
    if ( v5 )
      LocalFree(v5);
  }
  return 0;
}

```

## disassembly

```asm
0x180136374  mov     [rsp-28h+phPrinter], rcx
0x180136379  push    rbp
0x18013637a  push    rbx
0x18013637b  push    rsi
0x18013637c  push    rdi
0x18013637d  push    r14
0x18013637f  mov     rbp, rsp
0x180136382  sub     rsp, 30h
0x180136386  mov     r14, rdx
0x180136389  mov     eax, r8d
0x18013638c  and     al, 10h
0x18013638e  mov     ecx, 40h ; '@'; uFlags
0x180136393  neg     al
0x180136395  mov     esi, r8d
0x180136398  sbb     rdx, rdx
0x18013639b  and     edx, 548h
0x1801363a1  add     rdx, 0A0h; uBytes
0x1801363a8  call    cs:__imp_LocalAlloc
0x1801363ae  mov     rbx, rax
0x1801363b1  test    rax, rax
0x1801363b4  jz      loc_18013664B
0x1801363ba  lea     rax, aNull_0; "NULL"
0x1801363c1  test    r14, r14
0x1801363c4  mov     rcx, r14
0x1801363c7  cmovz   rcx, rax; Src
0x1801363cb  call    DuplicateString
0x1801363d0  mov     [rbx+18h], rax
0x1801363d4  test    rax, rax
0x1801363d7  jz      loc_18013664B
0x1801363dd  mov     [rbx+10h], rbx
0x1801363e1  mov     [rbx+28h], esi
0x1801363e4  test    sil, 5
0x1801363e8  jz      short loc_18013643A
0x1801363ea  mov     eax, esi
0x1801363ec  lea     rcx, qword_18029D8C0
0x1801363f3  and     al, 4
0x1801363f5  lea     rdx, [rbp+phPrinter]; phPrinter
0x1801363f9  neg     al
0x1801363fb  sbb     r8, r8
0x1801363fe  and     r8, rcx; pDefault
0x180136401  mov     rcx, r14; pPrinterName
0x180136404  call    cs:__imp_OpenPrinterW
0x18013640a  test    eax, eax
0x18013640c  jnz     short loc_18013643A
0x18013640e  call    cs:__imp_GetLastError
0x180136414  mov     r8, r14
0x180136417  lea     rdx, aOpenprinterFai; "OpenPrinter failed for '%ws': %d\n"
0x18013641e  mov     r9d, eax
0x180136421  lea     rcx, aPsuiPloadcommo; "PSUI::PLoadCommonInfo"
0x180136428  call    ?WriteDbgTraceWarning@DriverUiTelemetry@DriverUi@@SAXPEADPEAGZZ; DriverUi::DriverUiTelemetry::WriteDbgTraceWarning(char *,ushort *,...)
0x18013642d  mov     rcx, rbx; this
0x180136430  call    ?VFreeCommonInfo@PSUI@@YAXPEAU_COMMONINFO@1@@Z; PSUI::VFreeCommonInfo(PSUI::_COMMONINFO *)
0x180136435  jmp     loc_18013667B
0x18013643a  mov     rax, [rbp+phPrinter]
0x18013643e  mov     edx, 2; Level
0x180136443  mov     [rbx+20h], rax
0x180136447  test    dl, sil
0x18013644a  jz      short loc_1801364C0
0x18013644c  mov     rcx, [rbp+phPrinter]; hPrinter
0x180136450  mov     [rbp+pData], 603h
0x180136457  call    MyGetPrinter
0x18013645c  mov     rdi, rax
0x18013645f  test    rax, rax
0x180136462  jz      short loc_180136482
0x180136464  cmp     qword ptr [rax], 0
0x180136468  jnz     short loc_18013648C
0x18013646a  mov     rcx, [rbp+phPrinter]
0x18013646e  lea     r8, [rbp+pData]
0x180136472  lea     rdx, aInitdriververs; "InitDriverVersion"
0x180136479  call    BGetPrinterDataDWord
0x18013647e  test    eax, eax
0x180136480  jnz     short loc_18013648C
0x180136482  xor     eax, eax
0x180136484  mov     [rbp+pData], eax
0x180136487  test    rdi, rdi
0x18013648a  jz      short loc_180136498
0x18013648c  mov     rcx, rdi; hMem
0x18013648f  call    cs:__imp_LocalFree
0x180136495  mov     eax, [rbp+pData]
0x180136498  cmp     eax, 603h
0x18013649d  jz      short loc_1801364C0
0x18013649f  call    cs:__imp_GetLastError
0x1801364a5  mov     r8d, eax
0x1801364a8  lea     rdx, aPrinterNotFull; "Printer not fully initialized yet: %d\n"
0x1801364af  lea     rcx, aPsuiPloadcommo; "PSUI::PLoadCommonInfo"
0x1801364b6  call    ?WriteDbgTraceInfo@DriverUiTelemetry@DriverUi@@SAXPEADPEAGZZ; DriverUi::DriverUiTelemetry::WriteDbgTraceInfo(char *,ushort *,...)
0x1801364bb  jmp     loc_18013642D
0x1801364c0  mov     rcx, [rbp+phPrinter]; hPrinter
0x1801364c4  mov     r8d, 3
0x1801364ca  call    MyGetPrinterDriver
0x1801364cf  mov     [rbp+hMem], rax
0x1801364d3  mov     rdi, rax
0x1801364d6  test    rax, rax
0x1801364d9  jnz     short loc_1801364FC
0x1801364db  call    cs:__imp_GetLastError
0x1801364e1  lea     rdx, aCannotGetPrint_0; "Cannot get printer driver info: %d\n"
0x1801364e8  mov     r8d, eax
0x1801364eb  lea     rcx, aPsuiPloadcommo; "PSUI::PLoadCommonInfo"
0x1801364f2  call    ?WriteDbgTraceWarning@DriverUiTelemetry@DriverUi@@SAXPEADPEAGZZ; DriverUi::DriverUiTelemetry::WriteDbgTraceWarning(char *,ushort *,...)
0x1801364f7  jmp     loc_18013642D
0x1801364fc  test    sil, 8
0x180136500  jz      short loc_18013652C
0x180136502  mov     rcx, [rbp+phPrinter]; hPrinter
0x180136506  lea     r9, [rbp+pData]; pData
0x18013650a  mov     r8d, 4; Type
0x180136510  mov     [rbp+pData], 603h
0x180136517  lea     rdx, aInitdriververs; "InitDriverVersion"
0x18013651e  mov     [rsp+30h+cbData], 4; cbData
0x180136526  call    cs:__imp_SetPrinterDataW
0x18013652c  test    sil, 40h
0x180136530  jz      short loc_18013655A
0x180136532  mov     rcx, [rdi+20h]; pszSrc
0x180136536  test    rcx, rcx
0x180136539  jz      short loc_18013655A
0x18013653b  call    GenerateFilenameWithExtName
0x180136540  mov     rdi, rax
0x180136543  test    rax, rax
0x180136546  jz      short loc_18013655A
0x180136548  mov     rcx, rax; lpFileName
0x18013654b  call    cs:__imp_DeleteFileW
0x180136551  mov     rcx, rdi; hMem
0x180136554  call    cs:__imp_LocalFree
0x18013655a  mov     rcx, [rbp+phPrinter]; void *
0x18013655e  lea     rdi, [rbx+40h]
0x180136562  lea     r9, [rbp+hMem]
0x180136566  mov     qword ptr [rsp+30h+cbData], rdi; __int64
0x18013656b  mov     r8d, esi
0x18013656e  mov     rdx, r14; pPrinterName
0x180136571  call    PSUI__PAcquireCommonInfoRO
0x180136576  mov     rcx, [rbp+hMem]; hMem
0x18013657a  mov     [rbx+30h], rax
0x18013657e  test    rcx, rcx
0x180136581  jz      short loc_180136589
0x180136583  call    cs:__imp_LocalFree
0x180136589  mov     rdx, [rbx+30h]
0x18013658d  test    rdx, rdx
0x180136590  jz      loc_180136639
0x180136596  mov     rcx, [rdi]
0x180136599  test    rcx, rcx
0x18013659c  jz      loc_180136639
0x1801365a2  cmp     dword ptr [rcx+38h], 0
0x1801365a6  jz      short loc_1801365B0
0x1801365a8  mov     eax, [rcx+38h]
0x1801365ab  add     rax, rcx
0x1801365ae  jmp     short loc_1801365B2
0x1801365b0  xor     eax, eax
0x1801365b2  mov     [rbx+48h], rax
0x1801365b6  test    rax, rax
0x1801365b9  jnz     short loc_1801365CD
0x1801365bb  call    cs:__imp_GetLastError
0x1801365c1  lea     rdx, aCannotLoadPrin; "Cannot load printer description data: %"...
0x1801365c8  jmp     loc_1801364E8
0x1801365cd  mov     rdx, [rdx+20h]
0x1801365d1  mov     r8, rdx
0x1801365d4  mov     rdx, [rdx+28h]
0x1801365d8  call    PGetOemPluginInfo
0x1801365dd  mov     [rbx+50h], rax
0x1801365e1  test    rax, rax
0x1801365e4  jnz     short loc_1801365F8
0x1801365e6  call    cs:__imp_GetLastError
0x1801365ec  lea     rdx, aCannotGetOemPl; "Cannot get OEM plugins info: %d\n"
0x1801365f3  jmp     loc_1801364E8
0x1801365f8  mov     [rax], rbx
0x1801365fb  mov     r8d, 1
0x180136601  mov     rdx, [rbx+50h]
0x180136605  mov     rcx, rbx; this
0x180136608  call    BLoadOEMPluginModulesInternal
0x18013660d  test    eax, eax
0x18013660f  jnz     short loc_180136623
0x180136611  call    cs:__imp_GetLastError
0x180136617  lea     rdx, aCannotLoadOemP_0; "Cannot load OEM plugins: %d\n"
0x18013661e  jmp     loc_1801364E8
0x180136623  lea     rax, ?OemUIHelperFuncs@PSUI@@3U_OEMUIPROCS@@B; _OEMUIPROCS const PSUI::OemUIHelperFuncs
0x18013662a  mov     dword ptr [rbx], 10h
0x180136630  mov     [rbx+8], rax
0x180136634  mov     rax, rbx
0x180136637  jmp     short loc_18013667D
0x180136639  call    cs:__imp_GetLastError
0x18013663f  lea     rdx, aCannotLoadRead; "Cannot load read only common info: %d\n"
0x180136646  jmp     loc_1801364E8
0x18013664b  lea     rdx, aMemoryAllocati; "Memory allocation failed\n"
0x180136652  lea     rcx, aPsuiPloadcommo; "PSUI::PLoadCommonInfo"
0x180136659  call    ?WriteDbgTraceWarning@DriverUiTelemetry@DriverUi@@SAXPEADPEAGZZ; DriverUi::DriverUiTelemetry::WriteDbgTraceWarning(char *,ushort *,...)
0x18013665e  mov     rcx, [rbx+18h]; hMem
0x180136662  test    rcx, rcx
0x180136665  jz      short loc_18013666D
0x180136667  call    cs:__imp_LocalFree
0x18013666d  test    rbx, rbx
0x180136670  jz      short loc_18013667B
0x180136672  mov     rcx, rbx; hMem
0x180136675  call    cs:__imp_LocalFree
0x18013667b  xor     eax, eax
0x18013667d  add     rsp, 30h
0x180136681  pop     r14
0x180136683  pop     rdi
0x180136684  pop     rsi
0x180136685  pop     rbx
0x180136686  pop     rbp
0x180136687  retn
```
