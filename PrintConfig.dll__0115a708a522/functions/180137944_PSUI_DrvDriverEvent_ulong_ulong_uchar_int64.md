# PSUI::DrvDriverEvent(ulong,ulong,uchar *,__int64)

- ea: `0x180137944`
- end: `0x180137dbe`
- name: `?DrvDriverEvent@PSUI@@YAHKKPEAE_J@Z`
- size: `1146`
- prototype: `_BOOL8 __fastcall(PSUI *this, int, __int64, unsigned __int8 *)`
- caller_count: `1`
- callee_count: `15`
- tags: `file_ops, registry_config, loader_planting, broker_com_uri`

## callers

- `0x180030760`

## callees

- `0x180107214`
- `0x18010f894`
- `0x180137944`
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

- `api-ms-win-crt-private-l1-1-0!wcsrchr` at `0x180137a18`
- `api-ms-win-crt-private-l1-1-0!wcsrchr` at `0x180137a18`
- `KERNEL32!DeleteFileW` at `0x180137a87`
- `KERNEL32!DeleteFileW` at `0x180137d48`
- `KERNEL32!DeleteFileW` at `0x180137a87`
- `KERNEL32!DeleteFileW` at `0x180137d48`
- `KERNEL32!GetLastError` at `0x180137be1`
- `KERNEL32!GetLastError` at `0x180137c78`
- `KERNEL32!GetLastError` at `0x180137cd6`
- `KERNEL32!GetLastError` at `0x180137be1`
- `KERNEL32!GetLastError` at `0x180137c78`
- `KERNEL32!GetLastError` at `0x180137cd6`
- `KERNEL32!LocalFree` at `0x180137a96`
- `KERNEL32!LocalFree` at `0x180137ac1`
- `KERNEL32!LocalFree` at `0x180137ad5`
- `KERNEL32!LocalFree` at `0x180137d8a`
- `KERNEL32!LocalFree` at `0x180137a96`
- `KERNEL32!LocalFree` at `0x180137ac1`
- `KERNEL32!LocalFree` at `0x180137ad5`
- `KERNEL32!LocalFree` at `0x180137d8a`
- `KERNEL32!MoveFileExW` at `0x180137d61`
- `KERNEL32!MoveFileExW` at `0x180137d61`

## string_xrefs

- `0x180137bf0`: `Cannot load printer description data during DRIVER_EVENT_DELETE: %d\n`
- `0x180137ce5`: `DrvDriverEvent, Cannot load OEM plugins: %d\n`
- `0x180137aa4`: `Fail to expand loBidiQueryFileName to full path name.\n`
- `0x180137d74`: `OEMDriverEvent failed to delete BUD temp file: '%ws'\n`
- `0x1801379a1`: `PrintConfig.dll`

## pseudocode

```c
_BOOL8 __fastcall PSUI::DrvDriverEvent(PSUI *this, int a2, __int64 a3, unsigned __int8 *a4)
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
        "PSUI::DrvDriverEvent",
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
          v43 = L".PPD";
          if ( L".PPD" )
          {
            v44 = &off_1801D9B70;
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
                    "PSUI::DrvDriverEvent",
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
                    "PSUI::DrvDriverEvent",
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
          "PSUI::DrvDriverEvent",
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
        "PSUI::DrvDriverEvent",
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
0x180137944  mov     [rsp+arg_8], rbx
0x180137949  mov     [rsp+arg_18], r9
0x18013794e  mov     [rsp+arg_0], ecx
0x180137952  push    rbp
0x180137953  push    rsi
0x180137954  push    rdi
0x180137955  push    r12
0x180137957  push    r13
0x180137959  push    r14
0x18013795b  push    r15
0x18013795d  sub     rsp, 30h
0x180137961  mov     r12, r9
0x180137964  mov     rsi, r8
0x180137967  mov     r15d, ecx
0x18013796a  cmp     edx, 3
0x18013796d  jnz     loc_180137DA6
0x180137973  test    r8, r8
0x180137976  jz      loc_180137DA6
0x18013797c  cmp     qword ptr [r8+20h], 0
0x180137981  jz      loc_180137DA6
0x180137987  lea     ebp, [rdx-2]
0x18013798a  cmp     ecx, 2
0x18013798d  jnz     loc_180137B0B
0x180137993  cmp     dword ptr [r8], 4
0x180137997  jnb     loc_180137B0B
0x18013799d  mov     rcx, [r8+28h]; unsigned __int16 *
0x1801379a1  lea     rdx, aPrintconfigDll_1; "PrintConfig.dll"
0x1801379a8  xor     ebx, ebx
0x1801379aa  call    ?DoesFullPathMatchFile@@YA_NPEBG0@Z; DoesFullPathMatchFile(ushort const *,ushort const *)
0x1801379af  mov     rcx, [rsi+20h]; pszSrc
0x1801379b3  movzx   edx, al
0x1801379b6  call    LoadRawBinaryData
0x1801379bb  mov     r12, rax
0x1801379be  test    rax, rax
0x1801379c1  jz      loc_180137BE1
0x1801379c7  xor     r8d, r8d
0x1801379ca  mov     rcx, rax
0x1801379cd  call    InitBinaryData
0x1801379d2  mov     rbx, rax
0x1801379d5  test    rax, rax
0x1801379d8  jz      loc_180137BE1
0x1801379de  cmp     dword ptr [rax+38h], 0
0x1801379e2  jz      loc_180137BE1
0x1801379e8  mov     eax, [rax+38h]
0x1801379eb  add     rax, rbx
0x1801379ee  jz      loc_180137BE1
0x1801379f4  mov     ecx, [rax+138h]
0x1801379fa  test    ecx, ecx
0x1801379fc  jz      loc_180137AE6
0x180137a02  mov     r15, [rax+140h]
0x180137a09  add     r15, rcx
0x180137a0c  jz      loc_180137AE1
0x180137a12  lea     edx, [rbp+2Dh]; Ch
0x180137a15  mov     rcx, r15; Str
0x180137a18  call    cs:__imp_wcsrchr
0x180137a1f  nop     dword ptr [rax+rax+00h]
0x180137a24  mov     r13, rax
0x180137a27  test    rax, rax
0x180137a2a  jz      loc_180137AE1
0x180137a30  mov     rcx, [rsi+20h]; Src
0x180137a34  xor     edi, edi
0x180137a36  mov     [rsp+68h+pszSrc], rdi
0x180137a3e  call    PtstrGetDriverDirectory
0x180137a43  mov     r14, rax
0x180137a46  test    rax, rax
0x180137a49  jz      short loc_180137AA4
0x180137a4b  mov     r8, rax
0x180137a4e  lea     rcx, [rsp+68h+pszSrc]
0x180137a56  mov     rdx, r15
0x180137a59  call    BExpandOemFilename
0x180137a5e  mov     rdi, [rsp+68h+pszSrc]
0x180137a66  test    eax, eax
0x180137a68  jz      short loc_180137AA4
0x180137a6a  lea     r8, aSer; ".SER"
0x180137a71  mov     rdx, r13; unsigned __int16 *
0x180137a74  mov     rcx, rdi; pszSrc
0x180137a77  call    ?GetBinaryFileName@UniDrvUI@@YAPEBGPEBG00@Z; UniDrvUI::GetBinaryFileName(ushort const *,ushort const *,ushort const *)
0x180137a7c  mov     r15, rax
0x180137a7f  test    rax, rax
0x180137a82  jz      short loc_180137ABE
0x180137a84  mov     rcx, rax; lpFileName
0x180137a87  call    cs:__imp_DeleteFileW
0x180137a8e  nop     dword ptr [rax+rax+00h]
0x180137a93  mov     rcx, r15; hMem
0x180137a96  call    cs:__imp_LocalFree
0x180137a9d  nop     dword ptr [rax+rax+00h]
0x180137aa2  jmp     short loc_180137ABE
0x180137aa4  lea     rdx, aFailToExpandLo; "Fail to expand loBidiQueryFileName to f"...
0x180137aab  lea     rcx, aPsuiDrvdrivere; "PSUI::DrvDriverEvent"
0x180137ab2  call    ?WriteDbgTraceWarning@DriverUiTelemetry@DriverUi@@SAXPEADPEAGZZ; DriverUi::DriverUiTelemetry::WriteDbgTraceWarning(char *,ushort *,...)
0x180137ab7  xor     ebp, ebp
0x180137ab9  test    r14, r14
0x180137abc  jz      short loc_180137ACD
0x180137abe  mov     rcx, r14; hMem
0x180137ac1  call    cs:__imp_LocalFree
0x180137ac8  nop     dword ptr [rax+rax+00h]
0x180137acd  test    rdi, rdi
0x180137ad0  jz      short loc_180137AE1
0x180137ad2  mov     rcx, rdi; hMem
0x180137ad5  call    cs:__imp_LocalFree
0x180137adc  nop     dword ptr [rax+rax+00h]
0x180137ae1  mov     r15d, [rsp+68h+arg_0]
0x180137ae6  mov     rcx, rbx
0x180137ae9  call    FreeBinaryData
0x180137aee  test    r12, r12
0x180137af1  jz      short loc_180137AFB
0x180137af3  mov     rcx, r12
0x180137af6  call    UnloadRawBinaryData
0x180137afb  test    ebp, ebp
0x180137afd  jz      loc_180137D11
0x180137b03  mov     r12, [rsp+68h+arg_18]
0x180137b0b  mov     rdx, [rsi+28h]
0x180137b0f  mov     r8, rsi
0x180137b12  call    PGetOemPluginInfo
0x180137b17  mov     rdi, rax
0x180137b1a  test    rax, rax
0x180137b1d  jz      loc_180137CD6
0x180137b23  mov     r8d, 1
0x180137b29  mov     rdx, rax
0x180137b2c  xor     ecx, ecx; this
0x180137b2e  call    BLoadOEMPluginModulesInternal
0x180137b33  test    eax, eax
0x180137b35  jz      loc_180137CD6
0x180137b3b  mov     r14d, [rdi+8]
0x180137b3f  lea     rbx, [rdi+18h]
0x180137b43  test    r14d, r14d
0x180137b46  jz      loc_180137CCC
0x180137b4c  mov     r8, qword ptr cs:IID_IPrintOemUI.Data4
0x180137b53  mov     r9, qword ptr cs:IID_IPrintOemUI.Data1
0x180137b5a  mov     rdx, qword ptr cs:IID_IPrintOemUI2.Data4
0x180137b61  mov     r10, qword ptr cs:IID_IPrintOemUI2.Data1
0x180137b68  dec     r14d
0x180137b6b  cmp     qword ptr [rbx+20h], 0
0x180137b70  jz      loc_180137CBC
0x180137b76  mov     rcx, [rbx+48h]
0x180137b7a  test    rcx, rcx
0x180137b7d  jz      loc_180137C24
0x180137b83  cmp     [rbx+50h], r9
0x180137b87  jnz     short loc_180137B8F
0x180137b89  cmp     [rbx+58h], r8
0x180137b8d  jz      short loc_180137B9B
0x180137b8f  cmp     [rbx+50h], r10
0x180137b93  jnz     short loc_180137C13
0x180137b95  cmp     [rbx+58h], rdx
0x180137b99  jnz     short loc_180137C13
0x180137b9b  mov     rax, [rcx]
0x180137b9e  mov     r9, rsi
0x180137ba1  mov     r8d, 3
0x180137ba7  mov     [rsp+68h+var_48], r12
0x180137bac  mov     edx, r15d
0x180137baf  mov     rax, [rax+68h]
0x180137bb3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180137bb8  cmp     eax, 80004001h
0x180137bbd  jz      loc_180137CA0
0x180137bc3  mov     r8, qword ptr cs:IID_IPrintOemUI.Data4
0x180137bca  mov     r9, qword ptr cs:IID_IPrintOemUI.Data1
0x180137bd1  mov     rdx, qword ptr cs:IID_IPrintOemUI2.Data4
0x180137bd8  mov     r10, qword ptr cs:IID_IPrintOemUI2.Data1
0x180137bdf  jmp     short loc_180137C18
0x180137be1  call    cs:__imp_GetLastError
0x180137be8  nop     dword ptr [rax+rax+00h]
0x180137bed  mov     r8d, eax
0x180137bf0  lea     rdx, aCannotLoadPrin_0; "Cannot load printer description data du"...
0x180137bf7  lea     rcx, aPsuiDrvdrivere; "PSUI::DrvDriverEvent"
0x180137bfe  call    ?WriteDbgTraceWarning@DriverUiTelemetry@DriverUi@@SAXPEADPEAGZZ; DriverUi::DriverUiTelemetry::WriteDbgTraceWarning(char *,ushort *,...)
0x180137c03  xor     ebp, ebp
0x180137c05  test    rbx, rbx
0x180137c08  jz      loc_180137AEE
0x180137c0e  jmp     loc_180137AE6
0x180137c13  mov     eax, 80004002h
0x180137c18  mov     ebp, eax
0x180137c1a  not     ebp
0x180137c1c  shr     ebp, 1Fh
0x180137c1f  jmp     loc_180137CBC
0x180137c24  test    byte ptr [rbx+65h], 20h
0x180137c28  jz      short loc_180137C33
0x180137c2a  mov     rax, [rbx+0D0h]
0x180137c31  jmp     short loc_180137C5C
0x180137c33  mov     edx, 0Dh
0x180137c38  mov     rcx, rbx
0x180137c3b  call    PGetOemEntrypointAddress
0x180137c40  mov     r8, qword ptr cs:IID_IPrintOemUI.Data4
0x180137c47  mov     r9, qword ptr cs:IID_IPrintOemUI.Data1
0x180137c4e  mov     rdx, qword ptr cs:IID_IPrintOemUI2.Data4
0x180137c55  mov     r10, qword ptr cs:IID_IPrintOemUI2.Data1
0x180137c5c  test    rax, rax
0x180137c5f  jz      short loc_180137CBC
0x180137c61  mov     r9, r12
0x180137c64  mov     r8, rsi
0x180137c67  mov     edx, 3
0x180137c6c  mov     ecx, r15d
0x180137c6f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180137c74  test    eax, eax
0x180137c76  jnz     short loc_180137CA0
0x180137c78  call    cs:__imp_GetLastError
0x180137c7f  nop     dword ptr [rax+rax+00h]
0x180137c84  mov     r8, [rbx+8]
0x180137c88  lea     rdx, aOemdriverevent_1; "OEMDriverEvent failed for '%ws': %d\n"
0x180137c8f  mov     r9d, eax
0x180137c92  lea     rcx, aPsuiDrvdrivere; "PSUI::DrvDriverEvent"
0x180137c99  call    ?WriteDbgTraceWarning@DriverUiTelemetry@DriverUi@@SAXPEADPEAGZZ; DriverUi::DriverUiTelemetry::WriteDbgTraceWarning(char *,ushort *,...)
0x180137c9e  xor     ebp, ebp
0x180137ca0  mov     r10, qword ptr cs:IID_IPrintOemUI2.Data1
0x180137ca7  mov     rdx, qword ptr cs:IID_IPrintOemUI2.Data4
0x180137cae  mov     r9, qword ptr cs:IID_IPrintOemUI.Data1
0x180137cb5  mov     r8, qword ptr cs:IID_IPrintOemUI.Data4
0x180137cbc  add     rbx, 0D8h
0x180137cc3  test    r14d, r14d
0x180137cc6  jnz     loc_180137B68
0x180137ccc  mov     rcx, rdi
0x180137ccf  call    VFreeOemPluginInfo
0x180137cd4  jmp     short loc_180137D07
0x180137cd6  call    cs:__imp_GetLastError
0x180137cdd  nop     dword ptr [rax+rax+00h]
0x180137ce2  mov     r8d, eax
0x180137ce5  lea     rdx, aDrvdriverevent_2; "DrvDriverEvent, Cannot load OEM plugins"...
0x180137cec  lea     rcx, aPsuiDrvdrivere; "PSUI::DrvDriverEvent"
0x180137cf3  call    ?WriteDbgTraceWarning@DriverUiTelemetry@DriverUi@@SAXPEADPEAGZZ; DriverUi::DriverUiTelemetry::WriteDbgTraceWarning(char *,ushort *,...)
0x180137cf8  test    rdi, rdi
0x180137cfb  jz      short loc_180137D05
0x180137cfd  mov     rcx, rdi
0x180137d00  call    VFreeOemPluginInfo
0x180137d05  xor     ebp, ebp
0x180137d07  cmp     r15d, 2
0x180137d0b  jnz     loc_180137DA2
0x180137d11  cmp     dword ptr [rsi], 4
0x180137d14  jnb     loc_180137DA2
0x180137d1a  mov     rax, cs:off_1801D9B70; ".PPD"
0x180137d21  test    rax, rax
0x180137d24  jz      short loc_180137DA2
0x180137d26  lea     rdi, off_1801D9B70; ".PPD"
0x180137d2d  mov     r8, [rdi+8]; unsigned __int16 *
0x180137d31  mov     rdx, rax; unsigned __int16 *
0x180137d34  mov     rcx, [rsi+20h]; pszSrc
0x180137d38  call    ?GetBinaryFileName@UniDrvUI@@YAPEBGPEBG00@Z; UniDrvUI::GetBinaryFileName(ushort const *,ushort const *,ushort const *)
0x180137d3d  mov     rbx, rax
0x180137d40  test    rax, rax
0x180137d43  jz      short loc_180137D96
0x180137d45  mov     rcx, rax; lpFileName
0x180137d48  call    cs:__imp_DeleteFileW
0x180137d4f  nop     dword ptr [rax+rax+00h]
0x180137d54  test    eax, eax
0x180137d56  jnz     short loc_180137D87
0x180137d58  xor     edx, edx; lpNewFileName
0x180137d5a  lea     r8d, [rax+4]; dwFlags
0x180137d5e  mov     rcx, rbx; lpExistingFileName
0x180137d61  call    cs:__imp_MoveFileExW
0x180137d68  nop     dword ptr [rax+rax+00h]
0x180137d6d  test    eax, eax
0x180137d6f  jnz     short loc_180137D87
0x180137d71  mov     r8, rbx
0x180137d74  lea     rdx, aOemdriverevent_0; "OEMDriverEvent failed to delete BUD tem"...
0x180137d7b  lea     rcx, aPsuiDrvdrivere; "PSUI::DrvDriverEvent"
0x180137d82  call    ?WriteDbgTraceWarning@DriverUiTelemetry@DriverUi@@SAXPEADPEAGZZ; DriverUi::DriverUiTelemetry::WriteDbgTraceWarning(char *,ushort *,...)
0x180137d87  mov     rcx, rbx; hMem
0x180137d8a  call    cs:__imp_LocalFree
0x180137d91  nop     dword ptr [rax+rax+00h]
0x180137d96  add     rdi, 10h
0x180137d9a  mov     rax, [rdi]
0x180137d9d  test    rax, rax
0x180137da0  jnz     short loc_180137D2D
0x180137da2  mov     eax, ebp
0x180137da4  jmp     short loc_180137DA8
0x180137da6  xor     eax, eax
0x180137da8  mov     rbx, [rsp+68h+arg_8]
0x180137dad  add     rsp, 30h
0x180137db1  pop     r15
0x180137db3  pop     r14
0x180137db5  pop     r13
0x180137db7  pop     r12
0x180137db9  pop     rdi
0x180137dba  pop     rsi
0x180137dbb  pop     rbp
0x180137dbc  retn
```
