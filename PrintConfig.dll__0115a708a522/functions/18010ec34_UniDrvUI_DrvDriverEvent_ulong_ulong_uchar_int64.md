# UniDrvUI::DrvDriverEvent(ulong,ulong,uchar *,__int64)

- ea: `0x18010ec34`
- end: `0x18010f0ae`
- name: `?DrvDriverEvent@UniDrvUI@@YAHKKPEAE_J@Z`
- size: `1146`
- prototype: `_BOOL8 __fastcall(UniDrvUI *this, int, __int64, unsigned __int8 *)`
- caller_count: `1`
- callee_count: `15`
- tags: `file_ops, registry_config, loader_planting, broker_com_uri`

## callers

- `0x180030760`

## callees

- `0x180107214`
- `0x18010ec34`
- `0x18010f894`
- `0x18014ed04`
- `0x18014ed44`
- `0x18014ee44`
- `0x18014f0f4`
- `0x18014f448`
- `0x18015183c`
- `0x180154838`
- `0x180155868`
- `0x1801558d0`
- `0x180155cb8`
- `0x180158efc`
- `0x1801cb010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!wcsrchr` at `0x18010ed08`
- `api-ms-win-crt-private-l1-1-0!wcsrchr` at `0x18010ed08`
- `KERNEL32!DeleteFileW` at `0x18010ed77`
- `KERNEL32!DeleteFileW` at `0x18010f038`
- `KERNEL32!DeleteFileW` at `0x18010ed77`
- `KERNEL32!DeleteFileW` at `0x18010f038`
- `KERNEL32!GetLastError` at `0x18010eed1`
- `KERNEL32!GetLastError` at `0x18010ef68`
- `KERNEL32!GetLastError` at `0x18010efc6`
- `KERNEL32!GetLastError` at `0x18010eed1`
- `KERNEL32!GetLastError` at `0x18010ef68`
- `KERNEL32!GetLastError` at `0x18010efc6`
- `KERNEL32!LocalFree` at `0x18010ed86`
- `KERNEL32!LocalFree` at `0x18010edb1`
- `KERNEL32!LocalFree` at `0x18010edc5`
- `KERNEL32!LocalFree` at `0x18010f07a`
- `KERNEL32!LocalFree` at `0x18010ed86`
- `KERNEL32!LocalFree` at `0x18010edb1`
- `KERNEL32!LocalFree` at `0x18010edc5`
- `KERNEL32!LocalFree` at `0x18010f07a`
- `KERNEL32!MoveFileExW` at `0x18010f051`
- `KERNEL32!MoveFileExW` at `0x18010f051`

## string_xrefs

- `0x18010eee0`: `Cannot load printer description data during DRIVER_EVENT_DELETE: %d\n`
- `0x18010efd5`: `DrvDriverEvent, Cannot load OEM plugins: %d\n`
- `0x18010ed94`: `Fail to expand loBidiQueryFileName to full path name.\n`
- `0x18010f064`: `OEMDriverEvent failed to delete BUD temp file: '%ws'\n`
- `0x18010ec91`: `PrintConfig.dll`

## pseudocode

```c
_BOOL8 __fastcall UniDrvUI::DrvDriverEvent(UniDrvUI *this, int a2, __int64 a3, unsigned __int8 *a4)
{
  unsigned __int8 *v4; // r12
  unsigned int v6; // r15d
  BOOL v7; // ebp
  __int64 v8; // rbx
  bool matched; // al
  __int64 RawBinaryData; // rax
  __int64 v11; // rdx
  __int64 v12; // r12
  __int64 inited; // rax
  __int64 v14; // rdx
  __int64 v15; // r8
  __int64 v16; // rax
  __int64 v17; // rcx
  wchar_t *v18; // r15
  wchar_t *v19; // r13
  const wchar_t *v20; // rcx
  wchar_t *v21; // rdi
  char *DriverDirectory; // rax
  char *v23; // r14
  int v24; // eax
  const unsigned __int16 *v25; // r9
  wchar_t *v26; // rax
  wchar_t *v27; // r15
  const unsigned __int16 *v28; // r9
  __int64 v29; // rax
  _DWORD *v30; // rdi
  int v31; // r14d
  __int64 v32; // rbx
  __int64 v33; // r8
  __int64 v34; // r9
  __int64 v35; // rdx
  __int64 v36; // r10
  __int64 v37; // rcx
  int v38; // eax
  DWORD LastError; // eax
  unsigned int (__fastcall *v40)(_QWORD, __int64, __int64, unsigned __int8 *); // rax
  DWORD v41; // eax
  DWORD v42; // eax
  const unsigned __int16 *v43; // rax
  unsigned __int16 *const *v44; // rdi
  wchar_t *BinaryFileName; // rax
  WCHAR *v46; // rbx
  unsigned int v48; // [rsp+70h] [rbp+8h]
  STRSAFE_LPCWSTR pszSrc; // [rsp+80h] [rbp+18h] BYREF
  unsigned __int8 *v50; // [rsp+88h] [rbp+20h]

  v50 = a4;
  v48 = (unsigned int)this;
  v4 = a4;
  v6 = (unsigned int)this;
  if ( a2 == 3 && a3 && *(_QWORD *)(a3 + 32) )
  {
    v7 = 1;
    if ( (_DWORD)this != 2 || *(_DWORD *)a3 >= 4u )
      goto LABEL_27;
    v8 = 0;
    matched = DoesFullPathMatchFile(*(const unsigned __int16 **)(a3 + 40), L"PrintConfig.dll");
    RawBinaryData = LoadRawBinaryData(*(wchar_t **)(a3 + 32), matched);
    v12 = RawBinaryData;
    if ( !RawBinaryData
      || (inited = InitBinaryData(RawBinaryData, v11, 0), (v8 = inited) == 0)
      || !*(_DWORD *)(inited + 56)
      || (v16 = inited + *(unsigned int *)(inited + 56)) == 0 )
    {
      LastError = GetLastError();
      DriverUi::DriverUiTelemetry::WriteDbgTraceWarning(
        "UniDrvUI::DrvDriverEvent",
        L"Cannot load printer description data during DRIVER_EVENT_DELETE: %d\n",
        LastError);
      v7 = 0;
      if ( !v8 )
        goto LABEL_23;
      goto LABEL_22;
    }
    v17 = *(unsigned int *)(v16 + 312);
    if ( !(_DWORD)v17 )
    {
LABEL_22:
      FreeBinaryData(v8, v14, v15);
LABEL_23:
      if ( v12 )
        UnloadRawBinaryData(v12, v14, v15);
      if ( !v7 )
      {
LABEL_56:
        if ( *(_DWORD *)a3 < 4u )
        {
          v43 = L".GPD";
          if ( L".GPD" )
          {
            v44 = &off_1801D9700;
            do
            {
              BinaryFileName = UniDrvUI::GetBinaryFileName(
                                 *(STRSAFE_LPCWSTR *)(a3 + 32),
                                 v43,
                                 *((const unsigned __int16 **)v44 + 1),
                                 v28);
              v46 = BinaryFileName;
              if ( BinaryFileName )
              {
                if ( !DeleteFileW(BinaryFileName) && !MoveFileExW(v46, 0, 4u) )
                  DriverUi::DriverUiTelemetry::WriteDbgTraceWarning(
                    "UniDrvUI::DrvDriverEvent",
                    L"OEMDriverEvent failed to delete BUD temp file: '%ws'\n",
                    v46);
                LocalFree(v46);
              }
              v44 += 2;
              v43 = *v44;
            }
            while ( *v44 );
          }
        }
        return v7;
      }
      v4 = v50;
LABEL_27:
      v29 = PGetOemPluginInfo((__int64)this, *(const wchar_t **)(a3 + 40), a3);
      v30 = (_DWORD *)v29;
      if ( v29 && (unsigned int)BLoadOEMPluginModulesInternal(0, v29, 1) )
      {
        v31 = v30[2];
        v32 = (__int64)(v30 + 6);
        if ( v31 )
        {
          v33 = *(_QWORD *)IID_IPrintOemUI.Data4;
          v34 = *(_QWORD *)&IID_IPrintOemUI.Data1;
          v35 = *(_QWORD *)IID_IPrintOemUI2.Data4;
          v36 = *(_QWORD *)&IID_IPrintOemUI2.Data1;
          do
          {
            --v31;
            if ( *(_QWORD *)(v32 + 32) )
            {
              v37 = *(_QWORD *)(v32 + 72);
              if ( !v37 )
              {
                if ( (*(_BYTE *)(v32 + 101) & 0x20) != 0 )
                {
                  v40 = *(unsigned int (__fastcall **)(_QWORD, __int64, __int64, unsigned __int8 *))(v32 + 208);
                }
                else
                {
                  v40 = (unsigned int (__fastcall *)(_QWORD, __int64, __int64, unsigned __int8 *))PGetOemEntrypointAddress(
                                                                                                    v32,
                                                                                                    0xDu);
                  v33 = *(_QWORD *)IID_IPrintOemUI.Data4;
                  v34 = *(_QWORD *)&IID_IPrintOemUI.Data1;
                  v35 = *(_QWORD *)IID_IPrintOemUI2.Data4;
                  v36 = *(_QWORD *)&IID_IPrintOemUI2.Data1;
                }
                if ( !v40 )
                  goto LABEL_50;
                if ( !v40(v6, 3, a3, v4) )
                {
                  v41 = GetLastError();
                  DriverUi::DriverUiTelemetry::WriteDbgTraceWarning(
                    "UniDrvUI::DrvDriverEvent",
                    L"OEMDriverEvent failed for '%ws': %d\n",
                    *(_QWORD *)(v32 + 8),
                    v41);
                  v7 = 0;
                }
LABEL_49:
                v36 = *(_QWORD *)&IID_IPrintOemUI2.Data1;
                v35 = *(_QWORD *)IID_IPrintOemUI2.Data4;
                v34 = *(_QWORD *)&IID_IPrintOemUI.Data1;
                v33 = *(_QWORD *)IID_IPrintOemUI.Data4;
                goto LABEL_50;
              }
              if ( *(_QWORD *)(v32 + 80) == v34 && *(_QWORD *)(v32 + 88) == v33
                || *(_QWORD *)(v32 + 80) == v36 && *(_QWORD *)(v32 + 88) == v35 )
              {
                v38 = (*(__int64 (__fastcall **)(__int64, _QWORD, __int64, __int64, unsigned __int8 *))(*(_QWORD *)v37 + 104LL))(
                        v37,
                        v6,
                        3,
                        a3,
                        v4);
                if ( v38 == -2147467263 )
                  goto LABEL_49;
                v33 = *(_QWORD *)IID_IPrintOemUI.Data4;
                v34 = *(_QWORD *)&IID_IPrintOemUI.Data1;
                v35 = *(_QWORD *)IID_IPrintOemUI2.Data4;
                v36 = *(_QWORD *)&IID_IPrintOemUI2.Data1;
              }
              else
              {
                v38 = -2147467262;
              }
              v7 = v38 >= 0;
            }
LABEL_50:
            v32 += 216;
          }
          while ( v31 );
        }
        VFreeOemPluginInfo(v30);
      }
      else
      {
        v42 = GetLastError();
        DriverUi::DriverUiTelemetry::WriteDbgTraceWarning(
          "UniDrvUI::DrvDriverEvent",
          L"DrvDriverEvent, Cannot load OEM plugins: %d\n",
          v42);
        if ( v30 )
          VFreeOemPluginInfo(v30);
        v7 = 0;
      }
      if ( v6 != 2 )
        return v7;
      goto LABEL_56;
    }
    v18 = (wchar_t *)(v17 + *(_QWORD *)(v16 + 320));
    if ( !v18 || (v19 = wcsrchr(v18, 0x2Eu)) == 0 )
    {
LABEL_21:
      v6 = v48;
      goto LABEL_22;
    }
    v20 = *(const wchar_t **)(a3 + 32);
    v21 = 0;
    pszSrc = 0;
    DriverDirectory = PtstrGetDriverDirectory(v20);
    v23 = DriverDirectory;
    if ( DriverDirectory && (v24 = BExpandOemFilename(&pszSrc, v18, DriverDirectory), v21 = (wchar_t *)pszSrc, v24) )
    {
      v26 = UniDrvUI::GetBinaryFileName(pszSrc, v19, L".SER", v25);
      v27 = v26;
      if ( v26 )
      {
        DeleteFileW(v26);
        LocalFree(v27);
      }
    }
    else
    {
      DriverUi::DriverUiTelemetry::WriteDbgTraceWarning(
        "UniDrvUI::DrvDriverEvent",
        L"Fail to expand loBidiQueryFileName to full path name.\n");
      v7 = 0;
      if ( !v23 )
        goto LABEL_19;
    }
    LocalFree(v23);
LABEL_19:
    if ( v21 )
      LocalFree(v21);
    goto LABEL_21;
  }
  return 0;
}

```

## disassembly

```asm
0x18010ec34  mov     [rsp+arg_8], rbx
0x18010ec39  mov     [rsp+arg_18], r9
0x18010ec3e  mov     [rsp+arg_0], ecx
0x18010ec42  push    rbp
0x18010ec43  push    rsi
0x18010ec44  push    rdi
0x18010ec45  push    r12
0x18010ec47  push    r13
0x18010ec49  push    r14
0x18010ec4b  push    r15
0x18010ec4d  sub     rsp, 30h
0x18010ec51  mov     r12, r9
0x18010ec54  mov     rsi, r8
0x18010ec57  mov     r15d, ecx
0x18010ec5a  cmp     edx, 3
0x18010ec5d  jnz     loc_18010F096
0x18010ec63  test    r8, r8
0x18010ec66  jz      loc_18010F096
0x18010ec6c  cmp     qword ptr [r8+20h], 0
0x18010ec71  jz      loc_18010F096
0x18010ec77  lea     ebp, [rdx-2]
0x18010ec7a  cmp     ecx, 2
0x18010ec7d  jnz     loc_18010EDFB
0x18010ec83  cmp     dword ptr [r8], 4
0x18010ec87  jnb     loc_18010EDFB
0x18010ec8d  mov     rcx, [r8+28h]; unsigned __int16 *
0x18010ec91  lea     rdx, aPrintconfigDll_1; "PrintConfig.dll"
0x18010ec98  xor     ebx, ebx
0x18010ec9a  call    ?DoesFullPathMatchFile@@YA_NPEBG0@Z; DoesFullPathMatchFile(ushort const *,ushort const *)
0x18010ec9f  mov     rcx, [rsi+20h]; pszSrc
0x18010eca3  movzx   edx, al
0x18010eca6  call    LoadRawBinaryData
0x18010ecab  mov     r12, rax
0x18010ecae  test    rax, rax
0x18010ecb1  jz      loc_18010EED1
0x18010ecb7  xor     r8d, r8d
0x18010ecba  mov     rcx, rax
0x18010ecbd  call    InitBinaryData
0x18010ecc2  mov     rbx, rax
0x18010ecc5  test    rax, rax
0x18010ecc8  jz      loc_18010EED1
0x18010ecce  cmp     dword ptr [rax+38h], 0
0x18010ecd2  jz      loc_18010EED1
0x18010ecd8  mov     eax, [rax+38h]
0x18010ecdb  add     rax, rbx
0x18010ecde  jz      loc_18010EED1
0x18010ece4  mov     ecx, [rax+138h]
0x18010ecea  test    ecx, ecx
0x18010ecec  jz      loc_18010EDD6
0x18010ecf2  mov     r15, [rax+140h]
0x18010ecf9  add     r15, rcx
0x18010ecfc  jz      loc_18010EDD1
0x18010ed02  lea     edx, [rbp+2Dh]; Ch
0x18010ed05  mov     rcx, r15; Str
0x18010ed08  call    cs:__imp_wcsrchr
0x18010ed0f  nop     dword ptr [rax+rax+00h]
0x18010ed14  mov     r13, rax
0x18010ed17  test    rax, rax
0x18010ed1a  jz      loc_18010EDD1
0x18010ed20  mov     rcx, [rsi+20h]; Src
0x18010ed24  xor     edi, edi
0x18010ed26  mov     [rsp+68h+pszSrc], rdi
0x18010ed2e  call    PtstrGetDriverDirectory
0x18010ed33  mov     r14, rax
0x18010ed36  test    rax, rax
0x18010ed39  jz      short loc_18010ED94
0x18010ed3b  mov     r8, rax
0x18010ed3e  lea     rcx, [rsp+68h+pszSrc]
0x18010ed46  mov     rdx, r15
0x18010ed49  call    BExpandOemFilename
0x18010ed4e  mov     rdi, [rsp+68h+pszSrc]
0x18010ed56  test    eax, eax
0x18010ed58  jz      short loc_18010ED94
0x18010ed5a  lea     r8, aSer; ".SER"
0x18010ed61  mov     rdx, r13; unsigned __int16 *
0x18010ed64  mov     rcx, rdi; pszSrc
0x18010ed67  call    ?GetBinaryFileName@UniDrvUI@@YAPEBGPEBG00@Z; UniDrvUI::GetBinaryFileName(ushort const *,ushort const *,ushort const *)
0x18010ed6c  mov     r15, rax
0x18010ed6f  test    rax, rax
0x18010ed72  jz      short loc_18010EDAE
0x18010ed74  mov     rcx, rax; lpFileName
0x18010ed77  call    cs:__imp_DeleteFileW
0x18010ed7e  nop     dword ptr [rax+rax+00h]
0x18010ed83  mov     rcx, r15; hMem
0x18010ed86  call    cs:__imp_LocalFree
0x18010ed8d  nop     dword ptr [rax+rax+00h]
0x18010ed92  jmp     short loc_18010EDAE
0x18010ed94  lea     rdx, aFailToExpandLo; "Fail to expand loBidiQueryFileName to f"...
0x18010ed9b  lea     rcx, aUnidrvuiDrvdri; "UniDrvUI::DrvDriverEvent"
0x18010eda2  call    ?WriteDbgTraceWarning@DriverUiTelemetry@DriverUi@@SAXPEADPEAGZZ; DriverUi::DriverUiTelemetry::WriteDbgTraceWarning(char *,ushort *,...)
0x18010eda7  xor     ebp, ebp
0x18010eda9  test    r14, r14
0x18010edac  jz      short loc_18010EDBD
0x18010edae  mov     rcx, r14; hMem
0x18010edb1  call    cs:__imp_LocalFree
0x18010edb8  nop     dword ptr [rax+rax+00h]
0x18010edbd  test    rdi, rdi
0x18010edc0  jz      short loc_18010EDD1
0x18010edc2  mov     rcx, rdi; hMem
0x18010edc5  call    cs:__imp_LocalFree
0x18010edcc  nop     dword ptr [rax+rax+00h]
0x18010edd1  mov     r15d, [rsp+68h+arg_0]
0x18010edd6  mov     rcx, rbx
0x18010edd9  call    FreeBinaryData
0x18010edde  test    r12, r12
0x18010ede1  jz      short loc_18010EDEB
0x18010ede3  mov     rcx, r12
0x18010ede6  call    UnloadRawBinaryData
0x18010edeb  test    ebp, ebp
0x18010eded  jz      loc_18010F001
0x18010edf3  mov     r12, [rsp+68h+arg_18]
0x18010edfb  mov     rdx, [rsi+28h]
0x18010edff  mov     r8, rsi
0x18010ee02  call    PGetOemPluginInfo
0x18010ee07  mov     rdi, rax
0x18010ee0a  test    rax, rax
0x18010ee0d  jz      loc_18010EFC6
0x18010ee13  mov     r8d, 1
0x18010ee19  mov     rdx, rax
0x18010ee1c  xor     ecx, ecx; this
0x18010ee1e  call    BLoadOEMPluginModulesInternal
0x18010ee23  test    eax, eax
0x18010ee25  jz      loc_18010EFC6
0x18010ee2b  mov     r14d, [rdi+8]
0x18010ee2f  lea     rbx, [rdi+18h]
0x18010ee33  test    r14d, r14d
0x18010ee36  jz      loc_18010EFBC
0x18010ee3c  mov     r8, qword ptr cs:IID_IPrintOemUI.Data4
0x18010ee43  mov     r9, qword ptr cs:IID_IPrintOemUI.Data1
0x18010ee4a  mov     rdx, qword ptr cs:IID_IPrintOemUI2.Data4
0x18010ee51  mov     r10, qword ptr cs:IID_IPrintOemUI2.Data1
0x18010ee58  dec     r14d
0x18010ee5b  cmp     qword ptr [rbx+20h], 0
0x18010ee60  jz      loc_18010EFAC
0x18010ee66  mov     rcx, [rbx+48h]
0x18010ee6a  test    rcx, rcx
0x18010ee6d  jz      loc_18010EF14
0x18010ee73  cmp     [rbx+50h], r9
0x18010ee77  jnz     short loc_18010EE7F
0x18010ee79  cmp     [rbx+58h], r8
0x18010ee7d  jz      short loc_18010EE8B
0x18010ee7f  cmp     [rbx+50h], r10
0x18010ee83  jnz     short loc_18010EF03
0x18010ee85  cmp     [rbx+58h], rdx
0x18010ee89  jnz     short loc_18010EF03
0x18010ee8b  mov     rax, [rcx]
0x18010ee8e  mov     r9, rsi
0x18010ee91  mov     r8d, 3
0x18010ee97  mov     [rsp+68h+var_48], r12
0x18010ee9c  mov     edx, r15d
0x18010ee9f  mov     rax, [rax+68h]
0x18010eea3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18010eea8  cmp     eax, 80004001h
0x18010eead  jz      loc_18010EF90
0x18010eeb3  mov     r8, qword ptr cs:IID_IPrintOemUI.Data4
0x18010eeba  mov     r9, qword ptr cs:IID_IPrintOemUI.Data1
0x18010eec1  mov     rdx, qword ptr cs:IID_IPrintOemUI2.Data4
0x18010eec8  mov     r10, qword ptr cs:IID_IPrintOemUI2.Data1
0x18010eecf  jmp     short loc_18010EF08
0x18010eed1  call    cs:__imp_GetLastError
0x18010eed8  nop     dword ptr [rax+rax+00h]
0x18010eedd  mov     r8d, eax
0x18010eee0  lea     rdx, aCannotLoadPrin_0; "Cannot load printer description data du"...
0x18010eee7  lea     rcx, aUnidrvuiDrvdri; "UniDrvUI::DrvDriverEvent"
0x18010eeee  call    ?WriteDbgTraceWarning@DriverUiTelemetry@DriverUi@@SAXPEADPEAGZZ; DriverUi::DriverUiTelemetry::WriteDbgTraceWarning(char *,ushort *,...)
0x18010eef3  xor     ebp, ebp
0x18010eef5  test    rbx, rbx
0x18010eef8  jz      loc_18010EDDE
0x18010eefe  jmp     loc_18010EDD6
0x18010ef03  mov     eax, 80004002h
0x18010ef08  mov     ebp, eax
0x18010ef0a  not     ebp
0x18010ef0c  shr     ebp, 1Fh
0x18010ef0f  jmp     loc_18010EFAC
0x18010ef14  test    byte ptr [rbx+65h], 20h
0x18010ef18  jz      short loc_18010EF23
0x18010ef1a  mov     rax, [rbx+0D0h]
0x18010ef21  jmp     short loc_18010EF4C
0x18010ef23  mov     edx, 0Dh
0x18010ef28  mov     rcx, rbx
0x18010ef2b  call    PGetOemEntrypointAddress
0x18010ef30  mov     r8, qword ptr cs:IID_IPrintOemUI.Data4
0x18010ef37  mov     r9, qword ptr cs:IID_IPrintOemUI.Data1
0x18010ef3e  mov     rdx, qword ptr cs:IID_IPrintOemUI2.Data4
0x18010ef45  mov     r10, qword ptr cs:IID_IPrintOemUI2.Data1
0x18010ef4c  test    rax, rax
0x18010ef4f  jz      short loc_18010EFAC
0x18010ef51  mov     r9, r12
0x18010ef54  mov     r8, rsi
0x18010ef57  mov     edx, 3
0x18010ef5c  mov     ecx, r15d
0x18010ef5f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18010ef64  test    eax, eax
0x18010ef66  jnz     short loc_18010EF90
0x18010ef68  call    cs:__imp_GetLastError
0x18010ef6f  nop     dword ptr [rax+rax+00h]
0x18010ef74  mov     r8, [rbx+8]
0x18010ef78  lea     rdx, aOemdriverevent_1; "OEMDriverEvent failed for '%ws': %d\n"
0x18010ef7f  mov     r9d, eax
0x18010ef82  lea     rcx, aUnidrvuiDrvdri; "UniDrvUI::DrvDriverEvent"
0x18010ef89  call    ?WriteDbgTraceWarning@DriverUiTelemetry@DriverUi@@SAXPEADPEAGZZ; DriverUi::DriverUiTelemetry::WriteDbgTraceWarning(char *,ushort *,...)
0x18010ef8e  xor     ebp, ebp
0x18010ef90  mov     r10, qword ptr cs:IID_IPrintOemUI2.Data1
0x18010ef97  mov     rdx, qword ptr cs:IID_IPrintOemUI2.Data4
0x18010ef9e  mov     r9, qword ptr cs:IID_IPrintOemUI.Data1
0x18010efa5  mov     r8, qword ptr cs:IID_IPrintOemUI.Data4
0x18010efac  add     rbx, 0D8h
0x18010efb3  test    r14d, r14d
0x18010efb6  jnz     loc_18010EE58
0x18010efbc  mov     rcx, rdi
0x18010efbf  call    VFreeOemPluginInfo
0x18010efc4  jmp     short loc_18010EFF7
0x18010efc6  call    cs:__imp_GetLastError
0x18010efcd  nop     dword ptr [rax+rax+00h]
0x18010efd2  mov     r8d, eax
0x18010efd5  lea     rdx, aDrvdriverevent_2; "DrvDriverEvent, Cannot load OEM plugins"...
0x18010efdc  lea     rcx, aUnidrvuiDrvdri; "UniDrvUI::DrvDriverEvent"
0x18010efe3  call    ?WriteDbgTraceWarning@DriverUiTelemetry@DriverUi@@SAXPEADPEAGZZ; DriverUi::DriverUiTelemetry::WriteDbgTraceWarning(char *,ushort *,...)
0x18010efe8  test    rdi, rdi
0x18010efeb  jz      short loc_18010EFF5
0x18010efed  mov     rcx, rdi
0x18010eff0  call    VFreeOemPluginInfo
0x18010eff5  xor     ebp, ebp
0x18010eff7  cmp     r15d, 2
0x18010effb  jnz     loc_18010F092
0x18010f001  cmp     dword ptr [rsi], 4
0x18010f004  jnb     loc_18010F092
0x18010f00a  mov     rax, cs:off_1801D9700; ".GPD"
0x18010f011  test    rax, rax
0x18010f014  jz      short loc_18010F092
0x18010f016  lea     rdi, off_1801D9700; ".GPD"
0x18010f01d  mov     r8, [rdi+8]; unsigned __int16 *
0x18010f021  mov     rdx, rax; unsigned __int16 *
0x18010f024  mov     rcx, [rsi+20h]; pszSrc
0x18010f028  call    ?GetBinaryFileName@UniDrvUI@@YAPEBGPEBG00@Z; UniDrvUI::GetBinaryFileName(ushort const *,ushort const *,ushort const *)
0x18010f02d  mov     rbx, rax
0x18010f030  test    rax, rax
0x18010f033  jz      short loc_18010F086
0x18010f035  mov     rcx, rax; lpFileName
0x18010f038  call    cs:__imp_DeleteFileW
0x18010f03f  nop     dword ptr [rax+rax+00h]
0x18010f044  test    eax, eax
0x18010f046  jnz     short loc_18010F077
0x18010f048  xor     edx, edx; lpNewFileName
0x18010f04a  lea     r8d, [rax+4]; dwFlags
0x18010f04e  mov     rcx, rbx; lpExistingFileName
0x18010f051  call    cs:__imp_MoveFileExW
0x18010f058  nop     dword ptr [rax+rax+00h]
0x18010f05d  test    eax, eax
0x18010f05f  jnz     short loc_18010F077
0x18010f061  mov     r8, rbx
0x18010f064  lea     rdx, aOemdriverevent_0; "OEMDriverEvent failed to delete BUD tem"...
0x18010f06b  lea     rcx, aUnidrvuiDrvdri; "UniDrvUI::DrvDriverEvent"
0x18010f072  call    ?WriteDbgTraceWarning@DriverUiTelemetry@DriverUi@@SAXPEADPEAGZZ; DriverUi::DriverUiTelemetry::WriteDbgTraceWarning(char *,ushort *,...)
0x18010f077  mov     rcx, rbx; hMem
0x18010f07a  call    cs:__imp_LocalFree
0x18010f081  nop     dword ptr [rax+rax+00h]
0x18010f086  add     rdi, 10h
0x18010f08a  mov     rax, [rdi]
0x18010f08d  test    rax, rax
0x18010f090  jnz     short loc_18010F01D
0x18010f092  mov     eax, ebp
0x18010f094  jmp     short loc_18010F098
0x18010f096  xor     eax, eax
0x18010f098  mov     rbx, [rsp+68h+arg_8]
0x18010f09d  add     rsp, 30h
0x18010f0a1  pop     r15
0x18010f0a3  pop     r14
0x18010f0a5  pop     r13
0x18010f0a7  pop     r12
0x18010f0a9  pop     rdi
0x18010f0aa  pop     rsi
0x18010f0ab  pop     rbp
0x18010f0ac  retn
```
