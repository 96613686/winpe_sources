# PSUI::DrvDriverEvent(ulong,ulong,uchar *,__int64)

- ea: `0x180131994`
- end: `0x180131dc3`
- name: `?DrvDriverEvent@PSUI@@YAHKKPEAE_J@Z`
- size: `1071`
- prototype: `__int64 __fastcall(PSUI *__hidden this, unsigned int, unsigned int, unsigned __int8 *, __int64)`
- caller_count: `1`
- callee_count: `15`
- tags: `file_ops, registry_config, loader_planting, broker_com_uri`

## callers

- `0x18002f640`

## callees

- `0x180102674`
- `0x18010ab1c`
- `0x180131994`
- `0x1801480c8`
- `0x180148100`
- `0x1801481f4`
- `0x1801484a0`
- `0x18014885c`
- `0x18014aa0c`
- `0x18014d948`
- `0x18014e910`
- `0x18014e970`
- `0x18014ed30`
- `0x180151e28`
- `0x1801c3010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!wcsrchr` at `0x180131a68`
- `api-ms-win-crt-private-l1-1-0!wcsrchr` at `0x180131a68`
- `KERNEL32!DeleteFileW` at `0x180131ad1`
- `KERNEL32!DeleteFileW` at `0x180131d60`
- `KERNEL32!DeleteFileW` at `0x180131ad1`
- `KERNEL32!DeleteFileW` at `0x180131d60`
- `KERNEL32!GetLastError` at `0x180131c13`
- `KERNEL32!GetLastError` at `0x180131ca4`
- `KERNEL32!GetLastError` at `0x180131cfc`
- `KERNEL32!GetLastError` at `0x180131c13`
- `KERNEL32!GetLastError` at `0x180131ca4`
- `KERNEL32!GetLastError` at `0x180131cfc`
- `KERNEL32!LocalFree` at `0x180131ada`
- `KERNEL32!LocalFree` at `0x180131aff`
- `KERNEL32!LocalFree` at `0x180131b0d`
- `KERNEL32!LocalFree` at `0x180131d96`
- `KERNEL32!LocalFree` at `0x180131ada`
- `KERNEL32!LocalFree` at `0x180131aff`
- `KERNEL32!LocalFree` at `0x180131b0d`
- `KERNEL32!LocalFree` at `0x180131d96`
- `KERNEL32!MoveFileExW` at `0x180131d73`
- `KERNEL32!MoveFileExW` at `0x180131d73`

## string_xrefs

- `0x180131d05`: `DrvDriverEvent, Cannot load OEM plugins: %d\n`
- `0x180131c1c`: `Cannot load printer description data during DRIVER_EVENT_DELETE: %d\n`
- `0x180131d80`: `OEMDriverEvent failed to delete BUD temp file: '%ws'\n`
- `0x180131ae2`: `Fail to expand loBidiQueryFileName to full path name.\n`
- `0x1801319f1`: `PrintConfig.dll`

## pseudocode

```c
_BOOL8 __fastcall PSUI::DrvDriverEvent(PSUI *this, int a2, __int64 a3, unsigned __int8 *a4)
{
  unsigned __int8 *v4; // r12
  unsigned int v6; // r15d
  BOOL v7; // ebp
  __int64 v8; // rbx
  __int64 RawBinaryData; // rax
  __int64 v10; // rdx
  void *v11; // r12
  __int64 inited; // rax
  __int64 v13; // rax
  __int64 v14; // rcx
  const wchar_t *v15; // r15
  wchar_t *v16; // r13
  void *v17; // rcx
  wchar_t *v18; // rdi
  __int64 DriverDirectory; // rax
  void *v20; // r14
  int v21; // eax
  const unsigned __int16 *v22; // r9
  const WCHAR *v23; // rax
  WCHAR *v24; // r15
  const unsigned __int16 *v25; // r9
  __int64 v26; // rdi
  int v27; // r14d
  __int64 v28; // rbx
  __int64 v29; // r8
  __int64 v30; // r9
  __int64 v31; // rdx
  __int64 v32; // r10
  __int64 v33; // rcx
  int v34; // eax
  DWORD LastError; // eax
  unsigned int (__fastcall *v36)(_QWORD, __int64, __int64, unsigned __int8 *); // rax
  DWORD v37; // eax
  DWORD v38; // eax
  const unsigned __int16 *v39; // rax
  unsigned __int16 *const *v40; // rdi
  const WCHAR *BinaryFileName; // rax
  WCHAR *v42; // rbx
  unsigned int v44; // [rsp+70h] [rbp+8h]
  STRSAFE_LPCWSTR pszSrc; // [rsp+80h] [rbp+18h] BYREF
  unsigned __int8 *v46; // [rsp+88h] [rbp+20h]

  v46 = a4;
  v44 = (unsigned int)this;
  v4 = a4;
  v6 = (unsigned int)this;
  if ( a2 == 3 && a3 && *(_QWORD *)(a3 + 32) )
  {
    v7 = 1;
    if ( (_DWORD)this != 2 || *(_DWORD *)a3 >= 4u )
      goto LABEL_27;
    v8 = 0;
    DoesFullPathMatchFile(*(const unsigned __int16 **)(a3 + 40), L"PrintConfig.dll");
    RawBinaryData = LoadRawBinaryData(*(STRSAFE_LPCWSTR *)(a3 + 32));
    v11 = (void *)RawBinaryData;
    if ( !RawBinaryData
      || (inited = InitBinaryData(RawBinaryData, v10, 0), (v8 = inited) == 0)
      || !*(_DWORD *)(inited + 56)
      || (v13 = inited + *(unsigned int *)(inited + 56)) == 0 )
    {
      LastError = GetLastError();
      DriverUi::DriverUiTelemetry::WriteDbgTraceWarning(
        "PSUI::DrvDriverEvent",
        L"Cannot load printer description data during DRIVER_EVENT_DELETE: %d\n",
        LastError);
      v7 = 0;
      if ( !v8 )
        goto LABEL_23;
      goto LABEL_22;
    }
    v14 = *(unsigned int *)(v13 + 312);
    if ( !(_DWORD)v14 )
    {
LABEL_22:
      FreeBinaryData(v8);
LABEL_23:
      if ( v11 )
        UnloadRawBinaryData(v11);
      if ( !v7 )
      {
LABEL_56:
        if ( *(_DWORD *)a3 < 4u )
        {
          v39 = L".PPD";
          if ( L".PPD" )
          {
            v40 = &off_1801D1DA0;
            do
            {
              BinaryFileName = UniDrvUI::GetBinaryFileName(
                                 *(STRSAFE_LPCWSTR *)(a3 + 32),
                                 v39,
                                 *((const unsigned __int16 **)v40 + 1),
                                 v25);
              v42 = (WCHAR *)BinaryFileName;
              if ( BinaryFileName )
              {
                if ( !DeleteFileW(BinaryFileName) && !MoveFileExW(v42, 0, 4u) )
                  DriverUi::DriverUiTelemetry::WriteDbgTraceWarning(
                    "PSUI::DrvDriverEvent",
                    L"OEMDriverEvent failed to delete BUD temp file: '%ws'\n",
                    v42);
                LocalFree(v42);
              }
              v40 += 2;
              v39 = *v40;
            }
            while ( *v40 );
          }
        }
        return v7;
      }
      v4 = v46;
LABEL_27:
      v26 = PGetOemPluginInfo(this, *(_QWORD *)(a3 + 40), a3);
      if ( v26 && (unsigned int)BLoadOEMPluginModulesInternal(0) )
      {
        v27 = *(_DWORD *)(v26 + 8);
        v28 = v26 + 24;
        if ( v27 )
        {
          v29 = *(_QWORD *)IID_IPrintOemUI.Data4;
          v30 = *(_QWORD *)&IID_IPrintOemUI.Data1;
          v31 = *(_QWORD *)IID_IPrintOemUI2.Data4;
          v32 = *(_QWORD *)&IID_IPrintOemUI2.Data1;
          do
          {
            --v27;
            if ( *(_QWORD *)(v28 + 32) )
            {
              v33 = *(_QWORD *)(v28 + 72);
              if ( !v33 )
              {
                if ( (*(_BYTE *)(v28 + 101) & 0x20) != 0 )
                {
                  v36 = *(unsigned int (__fastcall **)(_QWORD, __int64, __int64, unsigned __int8 *))(v28 + 208);
                }
                else
                {
                  v36 = (unsigned int (__fastcall *)(_QWORD, __int64, __int64, unsigned __int8 *))PGetOemEntrypointAddress(
                                                                                                    v28,
                                                                                                    13,
                                                                                                    v29,
                                                                                                    v30);
                  v29 = *(_QWORD *)IID_IPrintOemUI.Data4;
                  v30 = *(_QWORD *)&IID_IPrintOemUI.Data1;
                  v31 = *(_QWORD *)IID_IPrintOemUI2.Data4;
                  v32 = *(_QWORD *)&IID_IPrintOemUI2.Data1;
                }
                if ( !v36 )
                  goto LABEL_50;
                if ( !v36(v6, 3, a3, v4) )
                {
                  v37 = GetLastError();
                  DriverUi::DriverUiTelemetry::WriteDbgTraceWarning(
                    "PSUI::DrvDriverEvent",
                    L"OEMDriverEvent failed for '%ws': %d\n",
                    *(_QWORD *)(v28 + 8),
                    v37);
                  v7 = 0;
                }
LABEL_49:
                v32 = *(_QWORD *)&IID_IPrintOemUI2.Data1;
                v31 = *(_QWORD *)IID_IPrintOemUI2.Data4;
                v30 = *(_QWORD *)&IID_IPrintOemUI.Data1;
                v29 = *(_QWORD *)IID_IPrintOemUI.Data4;
                goto LABEL_50;
              }
              if ( *(_QWORD *)(v28 + 80) == v30 && *(_QWORD *)(v28 + 88) == v29
                || *(_QWORD *)(v28 + 80) == v32 && *(_QWORD *)(v28 + 88) == v31 )
              {
                v34 = (*(__int64 (__fastcall **)(__int64, _QWORD, __int64, __int64, unsigned __int8 *))(*(_QWORD *)v33 + 104LL))(
                        v33,
                        v6,
                        3,
                        a3,
                        v4);
                if ( v34 == -2147467263 )
                  goto LABEL_49;
                v29 = *(_QWORD *)IID_IPrintOemUI.Data4;
                v30 = *(_QWORD *)&IID_IPrintOemUI.Data1;
                v31 = *(_QWORD *)IID_IPrintOemUI2.Data4;
                v32 = *(_QWORD *)&IID_IPrintOemUI2.Data1;
              }
              else
              {
                v34 = -2147467262;
              }
              v7 = v34 >= 0;
            }
LABEL_50:
            v28 += 216;
          }
          while ( v27 );
        }
        VFreeOemPluginInfo(v26);
      }
      else
      {
        v38 = GetLastError();
        DriverUi::DriverUiTelemetry::WriteDbgTraceWarning(
          "PSUI::DrvDriverEvent",
          L"DrvDriverEvent, Cannot load OEM plugins: %d\n",
          v38);
        if ( v26 )
          VFreeOemPluginInfo(v26);
        v7 = 0;
      }
      if ( v6 != 2 )
        return v7;
      goto LABEL_56;
    }
    v15 = (const wchar_t *)(v14 + *(_QWORD *)(v13 + 320));
    if ( !v15 || (v16 = wcsrchr(v15, 0x2Eu)) == 0 )
    {
LABEL_21:
      v6 = v44;
      goto LABEL_22;
    }
    v17 = *(void **)(a3 + 32);
    v18 = 0;
    pszSrc = 0;
    DriverDirectory = PtstrGetDriverDirectory(v17);
    v20 = (void *)DriverDirectory;
    if ( DriverDirectory && (v21 = BExpandOemFilename(&pszSrc, v15, DriverDirectory), v18 = (wchar_t *)pszSrc, v21) )
    {
      v23 = UniDrvUI::GetBinaryFileName(pszSrc, v16, L".SER", v22);
      v24 = (WCHAR *)v23;
      if ( v23 )
      {
        DeleteFileW(v23);
        LocalFree(v24);
      }
    }
    else
    {
      DriverUi::DriverUiTelemetry::WriteDbgTraceWarning(
        "PSUI::DrvDriverEvent",
        L"Fail to expand loBidiQueryFileName to full path name.\n");
      v7 = 0;
      if ( !v20 )
        goto LABEL_19;
    }
    LocalFree(v20);
LABEL_19:
    if ( v18 )
      LocalFree(v18);
    goto LABEL_21;
  }
  return 0;
}

```

## disassembly

```asm
0x180131994  mov     [rsp+arg_8], rbx
0x180131999  mov     [rsp+arg_18], r9
0x18013199e  mov     [rsp+arg_0], ecx
0x1801319a2  push    rbp
0x1801319a3  push    rsi
0x1801319a4  push    rdi
0x1801319a5  push    r12
0x1801319a7  push    r13
0x1801319a9  push    r14
0x1801319ab  push    r15
0x1801319ad  sub     rsp, 30h
0x1801319b1  mov     r12, r9
0x1801319b4  mov     rsi, r8
0x1801319b7  mov     r15d, ecx
0x1801319ba  cmp     edx, 3
0x1801319bd  jnz     loc_180131DAC
0x1801319c3  test    r8, r8
0x1801319c6  jz      loc_180131DAC
0x1801319cc  cmp     qword ptr [r8+20h], 0
0x1801319d1  jz      loc_180131DAC
0x1801319d7  lea     ebp, [rdx-2]
0x1801319da  cmp     ecx, 2
0x1801319dd  jnz     loc_180131B3D
0x1801319e3  cmp     dword ptr [r8], 4
0x1801319e7  jnb     loc_180131B3D
0x1801319ed  mov     rcx, [r8+28h]; unsigned __int16 *
0x1801319f1  lea     rdx, aPrintconfigDll_1; "PrintConfig.dll"
0x1801319f8  xor     ebx, ebx
0x1801319fa  call    ?DoesFullPathMatchFile@@YA_NPEBG0@Z; DoesFullPathMatchFile(ushort const *,ushort const *)
0x1801319ff  mov     rcx, [rsi+20h]; pszSrc
0x180131a03  movzx   edx, al
0x180131a06  call    LoadRawBinaryData
0x180131a0b  mov     r12, rax
0x180131a0e  test    rax, rax
0x180131a11  jz      loc_180131C13
0x180131a17  xor     r8d, r8d
0x180131a1a  mov     rcx, rax
0x180131a1d  call    InitBinaryData
0x180131a22  mov     rbx, rax
0x180131a25  test    rax, rax
0x180131a28  jz      loc_180131C13
0x180131a2e  cmp     dword ptr [rax+38h], 0
0x180131a32  jz      loc_180131C13
0x180131a38  mov     eax, [rax+38h]
0x180131a3b  add     rax, rbx
0x180131a3e  jz      loc_180131C13
0x180131a44  mov     ecx, [rax+138h]
0x180131a4a  test    ecx, ecx
0x180131a4c  jz      loc_180131B18
0x180131a52  mov     r15, [rax+140h]
0x180131a59  add     r15, rcx
0x180131a5c  jz      loc_180131B13
0x180131a62  lea     edx, [rbp+2Dh]; Ch
0x180131a65  mov     rcx, r15; Str
0x180131a68  call    cs:__imp_wcsrchr
0x180131a6e  mov     r13, rax
0x180131a71  test    rax, rax
0x180131a74  jz      loc_180131B13
0x180131a7a  mov     rcx, [rsi+20h]; Src
0x180131a7e  xor     edi, edi
0x180131a80  mov     [rsp+68h+pszSrc], rdi
0x180131a88  call    PtstrGetDriverDirectory
0x180131a8d  mov     r14, rax
0x180131a90  test    rax, rax
0x180131a93  jz      short loc_180131AE2
0x180131a95  mov     r8, rax
0x180131a98  lea     rcx, [rsp+68h+pszSrc]
0x180131aa0  mov     rdx, r15
0x180131aa3  call    BExpandOemFilename
0x180131aa8  mov     rdi, [rsp+68h+pszSrc]
0x180131ab0  test    eax, eax
0x180131ab2  jz      short loc_180131AE2
0x180131ab4  lea     r8, aSer; ".SER"
0x180131abb  mov     rdx, r13; unsigned __int16 *
0x180131abe  mov     rcx, rdi; pszSrc
0x180131ac1  call    ?GetBinaryFileName@UniDrvUI@@YAPEBGPEBG00@Z; UniDrvUI::GetBinaryFileName(ushort const *,ushort const *,ushort const *)
0x180131ac6  mov     r15, rax
0x180131ac9  test    rax, rax
0x180131acc  jz      short loc_180131AFC
0x180131ace  mov     rcx, rax; lpFileName
0x180131ad1  call    cs:__imp_DeleteFileW
0x180131ad7  mov     rcx, r15; hMem
0x180131ada  call    cs:__imp_LocalFree
0x180131ae0  jmp     short loc_180131AFC
0x180131ae2  lea     rdx, aFailToExpandLo; "Fail to expand loBidiQueryFileName to f"...
0x180131ae9  lea     rcx, aPsuiDrvdrivere; "PSUI::DrvDriverEvent"
0x180131af0  call    ?WriteDbgTraceWarning@DriverUiTelemetry@DriverUi@@SAXPEADPEAGZZ; DriverUi::DriverUiTelemetry::WriteDbgTraceWarning(char *,ushort *,...)
0x180131af5  xor     ebp, ebp
0x180131af7  test    r14, r14
0x180131afa  jz      short loc_180131B05
0x180131afc  mov     rcx, r14; hMem
0x180131aff  call    cs:__imp_LocalFree
0x180131b05  test    rdi, rdi
0x180131b08  jz      short loc_180131B13
0x180131b0a  mov     rcx, rdi; hMem
0x180131b0d  call    cs:__imp_LocalFree
0x180131b13  mov     r15d, [rsp+68h+arg_0]
0x180131b18  mov     rcx, rbx
0x180131b1b  call    FreeBinaryData
0x180131b20  test    r12, r12
0x180131b23  jz      short loc_180131B2D
0x180131b25  mov     rcx, r12; hMem
0x180131b28  call    UnloadRawBinaryData
0x180131b2d  test    ebp, ebp
0x180131b2f  jz      loc_180131D2D
0x180131b35  mov     r12, [rsp+68h+arg_18]
0x180131b3d  mov     rdx, [rsi+28h]
0x180131b41  mov     r8, rsi
0x180131b44  call    PGetOemPluginInfo
0x180131b49  mov     rdi, rax
0x180131b4c  test    rax, rax
0x180131b4f  jz      loc_180131CFC
0x180131b55  mov     r8d, 1
0x180131b5b  mov     rdx, rax
0x180131b5e  xor     ecx, ecx; this
0x180131b60  call    BLoadOEMPluginModulesInternal
0x180131b65  test    eax, eax
0x180131b67  jz      loc_180131CFC
0x180131b6d  mov     r14d, [rdi+8]
0x180131b71  lea     rbx, [rdi+18h]
0x180131b75  test    r14d, r14d
0x180131b78  jz      loc_180131CF2
0x180131b7e  mov     r8, qword ptr cs:IID_IPrintOemUI.Data4
0x180131b85  mov     r9, qword ptr cs:IID_IPrintOemUI.Data1
0x180131b8c  mov     rdx, qword ptr cs:IID_IPrintOemUI2.Data4
0x180131b93  mov     r10, qword ptr cs:IID_IPrintOemUI2.Data1
0x180131b9a  dec     r14d
0x180131b9d  cmp     qword ptr [rbx+20h], 0
0x180131ba2  jz      loc_180131CE2
0x180131ba8  mov     rcx, [rbx+48h]
0x180131bac  test    rcx, rcx
0x180131baf  jz      loc_180131C50
0x180131bb5  cmp     [rbx+50h], r9
0x180131bb9  jnz     short loc_180131BC1
0x180131bbb  cmp     [rbx+58h], r8
0x180131bbf  jz      short loc_180131BCD
0x180131bc1  cmp     [rbx+50h], r10
0x180131bc5  jnz     short loc_180131C3F
0x180131bc7  cmp     [rbx+58h], rdx
0x180131bcb  jnz     short loc_180131C3F
0x180131bcd  mov     rax, [rcx]
0x180131bd0  mov     r9, rsi
0x180131bd3  mov     r8d, 3
0x180131bd9  mov     [rsp+68h+var_48], r12
0x180131bde  mov     edx, r15d
0x180131be1  mov     rax, [rax+68h]
0x180131be5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180131bea  cmp     eax, 80004001h
0x180131bef  jz      loc_180131CC6
0x180131bf5  mov     r8, qword ptr cs:IID_IPrintOemUI.Data4
0x180131bfc  mov     r9, qword ptr cs:IID_IPrintOemUI.Data1
0x180131c03  mov     rdx, qword ptr cs:IID_IPrintOemUI2.Data4
0x180131c0a  mov     r10, qword ptr cs:IID_IPrintOemUI2.Data1
0x180131c11  jmp     short loc_180131C44
0x180131c13  call    cs:__imp_GetLastError
0x180131c19  mov     r8d, eax
0x180131c1c  lea     rdx, aCannotLoadPrin_0; "Cannot load printer description data du"...
0x180131c23  lea     rcx, aPsuiDrvdrivere; "PSUI::DrvDriverEvent"
0x180131c2a  call    ?WriteDbgTraceWarning@DriverUiTelemetry@DriverUi@@SAXPEADPEAGZZ; DriverUi::DriverUiTelemetry::WriteDbgTraceWarning(char *,ushort *,...)
0x180131c2f  xor     ebp, ebp
0x180131c31  test    rbx, rbx
0x180131c34  jz      loc_180131B20
0x180131c3a  jmp     loc_180131B18
0x180131c3f  mov     eax, 80004002h
0x180131c44  mov     ebp, eax
0x180131c46  not     ebp
0x180131c48  shr     ebp, 1Fh
0x180131c4b  jmp     loc_180131CE2
0x180131c50  test    byte ptr [rbx+65h], 20h
0x180131c54  jz      short loc_180131C5F
0x180131c56  mov     rax, [rbx+0D0h]
0x180131c5d  jmp     short loc_180131C88
0x180131c5f  mov     edx, 0Dh
0x180131c64  mov     rcx, rbx
0x180131c67  call    PGetOemEntrypointAddress
0x180131c6c  mov     r8, qword ptr cs:IID_IPrintOemUI.Data4
0x180131c73  mov     r9, qword ptr cs:IID_IPrintOemUI.Data1
0x180131c7a  mov     rdx, qword ptr cs:IID_IPrintOemUI2.Data4
0x180131c81  mov     r10, qword ptr cs:IID_IPrintOemUI2.Data1
0x180131c88  test    rax, rax
0x180131c8b  jz      short loc_180131CE2
0x180131c8d  mov     r9, r12
0x180131c90  mov     r8, rsi
0x180131c93  mov     edx, 3
0x180131c98  mov     ecx, r15d
0x180131c9b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180131ca0  test    eax, eax
0x180131ca2  jnz     short loc_180131CC6
0x180131ca4  call    cs:__imp_GetLastError
0x180131caa  mov     r8, [rbx+8]
0x180131cae  lea     rdx, aOemdriverevent_1; "OEMDriverEvent failed for '%ws': %d\n"
0x180131cb5  mov     r9d, eax
0x180131cb8  lea     rcx, aPsuiDrvdrivere; "PSUI::DrvDriverEvent"
0x180131cbf  call    ?WriteDbgTraceWarning@DriverUiTelemetry@DriverUi@@SAXPEADPEAGZZ; DriverUi::DriverUiTelemetry::WriteDbgTraceWarning(char *,ushort *,...)
0x180131cc4  xor     ebp, ebp
0x180131cc6  mov     r10, qword ptr cs:IID_IPrintOemUI2.Data1
0x180131ccd  mov     rdx, qword ptr cs:IID_IPrintOemUI2.Data4
0x180131cd4  mov     r9, qword ptr cs:IID_IPrintOemUI.Data1
0x180131cdb  mov     r8, qword ptr cs:IID_IPrintOemUI.Data4
0x180131ce2  add     rbx, 0D8h
0x180131ce9  test    r14d, r14d
0x180131cec  jnz     loc_180131B9A
0x180131cf2  mov     rcx, rdi
0x180131cf5  call    VFreeOemPluginInfo
0x180131cfa  jmp     short loc_180131D27
0x180131cfc  call    cs:__imp_GetLastError
0x180131d02  mov     r8d, eax
0x180131d05  lea     rdx, aDrvdriverevent_2; "DrvDriverEvent, Cannot load OEM plugins"...
0x180131d0c  lea     rcx, aPsuiDrvdrivere; "PSUI::DrvDriverEvent"
0x180131d13  call    ?WriteDbgTraceWarning@DriverUiTelemetry@DriverUi@@SAXPEADPEAGZZ; DriverUi::DriverUiTelemetry::WriteDbgTraceWarning(char *,ushort *,...)
0x180131d18  test    rdi, rdi
0x180131d1b  jz      short loc_180131D25
0x180131d1d  mov     rcx, rdi
0x180131d20  call    VFreeOemPluginInfo
0x180131d25  xor     ebp, ebp
0x180131d27  cmp     r15d, 2
0x180131d2b  jnz     short loc_180131DA8
0x180131d2d  cmp     dword ptr [rsi], 4
0x180131d30  jnb     short loc_180131DA8
0x180131d32  mov     rax, cs:off_1801D1DA0; ".PPD"
0x180131d39  test    rax, rax
0x180131d3c  jz      short loc_180131DA8
0x180131d3e  lea     rdi, off_1801D1DA0; ".PPD"
0x180131d45  mov     r8, [rdi+8]; unsigned __int16 *
0x180131d49  mov     rdx, rax; unsigned __int16 *
0x180131d4c  mov     rcx, [rsi+20h]; pszSrc
0x180131d50  call    ?GetBinaryFileName@UniDrvUI@@YAPEBGPEBG00@Z; UniDrvUI::GetBinaryFileName(ushort const *,ushort const *,ushort const *)
0x180131d55  mov     rbx, rax
0x180131d58  test    rax, rax
0x180131d5b  jz      short loc_180131D9C
0x180131d5d  mov     rcx, rax; lpFileName
0x180131d60  call    cs:__imp_DeleteFileW
0x180131d66  test    eax, eax
0x180131d68  jnz     short loc_180131D93
0x180131d6a  xor     edx, edx; lpNewFileName
0x180131d6c  lea     r8d, [rax+4]; dwFlags
0x180131d70  mov     rcx, rbx; lpExistingFileName
0x180131d73  call    cs:__imp_MoveFileExW
0x180131d79  test    eax, eax
0x180131d7b  jnz     short loc_180131D93
0x180131d7d  mov     r8, rbx
0x180131d80  lea     rdx, aOemdriverevent_0; "OEMDriverEvent failed to delete BUD tem"...
0x180131d87  lea     rcx, aPsuiDrvdrivere; "PSUI::DrvDriverEvent"
0x180131d8e  call    ?WriteDbgTraceWarning@DriverUiTelemetry@DriverUi@@SAXPEADPEAGZZ; DriverUi::DriverUiTelemetry::WriteDbgTraceWarning(char *,ushort *,...)
0x180131d93  mov     rcx, rbx; hMem
0x180131d96  call    cs:__imp_LocalFree
0x180131d9c  add     rdi, 10h
0x180131da0  mov     rax, [rdi]
0x180131da3  test    rax, rax
0x180131da6  jnz     short loc_180131D45
0x180131da8  mov     eax, ebp
0x180131daa  jmp     short loc_180131DAE
0x180131dac  xor     eax, eax
0x180131dae  mov     rbx, [rsp+68h+arg_8]
0x180131db3  add     rsp, 30h
0x180131db7  pop     r15
0x180131db9  pop     r14
0x180131dbb  pop     r13
0x180131dbd  pop     r12
0x180131dbf  pop     rdi
0x180131dc0  pop     rsi
0x180131dc1  pop     rbp
0x180131dc2  retn
```
