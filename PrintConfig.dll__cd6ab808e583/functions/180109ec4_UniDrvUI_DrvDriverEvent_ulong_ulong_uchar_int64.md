# UniDrvUI::DrvDriverEvent(ulong,ulong,uchar *,__int64)

- ea: `0x180109ec4`
- end: `0x18010a2f3`
- name: `?DrvDriverEvent@UniDrvUI@@YAHKKPEAE_J@Z`
- size: `1071`
- prototype: `__int64 __fastcall(UniDrvUI *__hidden this, unsigned int, unsigned int, unsigned __int8 *, __int64)`
- caller_count: `1`
- callee_count: `15`
- tags: `file_ops, registry_config, loader_planting, broker_com_uri`

## callers

- `0x18002f640`

## callees

- `0x180102674`
- `0x180109ec4`
- `0x18010ab1c`
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

- `api-ms-win-crt-private-l1-1-0!wcsrchr` at `0x180109f98`
- `api-ms-win-crt-private-l1-1-0!wcsrchr` at `0x180109f98`
- `KERNEL32!DeleteFileW` at `0x18010a001`
- `KERNEL32!DeleteFileW` at `0x18010a290`
- `KERNEL32!DeleteFileW` at `0x18010a001`
- `KERNEL32!DeleteFileW` at `0x18010a290`
- `KERNEL32!GetLastError` at `0x18010a143`
- `KERNEL32!GetLastError` at `0x18010a1d4`
- `KERNEL32!GetLastError` at `0x18010a22c`
- `KERNEL32!GetLastError` at `0x18010a143`
- `KERNEL32!GetLastError` at `0x18010a1d4`
- `KERNEL32!GetLastError` at `0x18010a22c`
- `KERNEL32!LocalFree` at `0x18010a00a`
- `KERNEL32!LocalFree` at `0x18010a02f`
- `KERNEL32!LocalFree` at `0x18010a03d`
- `KERNEL32!LocalFree` at `0x18010a2c6`
- `KERNEL32!LocalFree` at `0x18010a00a`
- `KERNEL32!LocalFree` at `0x18010a02f`
- `KERNEL32!LocalFree` at `0x18010a03d`
- `KERNEL32!LocalFree` at `0x18010a2c6`
- `KERNEL32!MoveFileExW` at `0x18010a2a3`
- `KERNEL32!MoveFileExW` at `0x18010a2a3`

## string_xrefs

- `0x18010a235`: `DrvDriverEvent, Cannot load OEM plugins: %d\n`
- `0x18010a14c`: `Cannot load printer description data during DRIVER_EVENT_DELETE: %d\n`
- `0x18010a2b0`: `OEMDriverEvent failed to delete BUD temp file: '%ws'\n`
- `0x18010a012`: `Fail to expand loBidiQueryFileName to full path name.\n`
- `0x180109f21`: `PrintConfig.dll`

## pseudocode

```c
_BOOL8 __fastcall UniDrvUI::DrvDriverEvent(UniDrvUI *this, int a2, __int64 a3, unsigned __int8 *a4)
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
        "UniDrvUI::DrvDriverEvent",
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
          v39 = L".GPD";
          if ( L".GPD" )
          {
            v40 = &off_1801D1930;
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
                    "UniDrvUI::DrvDriverEvent",
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
                    "UniDrvUI::DrvDriverEvent",
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
          "UniDrvUI::DrvDriverEvent",
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
        "UniDrvUI::DrvDriverEvent",
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
0x180109ec4  mov     [rsp+arg_8], rbx
0x180109ec9  mov     [rsp+arg_18], r9
0x180109ece  mov     [rsp+arg_0], ecx
0x180109ed2  push    rbp
0x180109ed3  push    rsi
0x180109ed4  push    rdi
0x180109ed5  push    r12
0x180109ed7  push    r13
0x180109ed9  push    r14
0x180109edb  push    r15
0x180109edd  sub     rsp, 30h
0x180109ee1  mov     r12, r9
0x180109ee4  mov     rsi, r8
0x180109ee7  mov     r15d, ecx
0x180109eea  cmp     edx, 3
0x180109eed  jnz     loc_18010A2DC
0x180109ef3  test    r8, r8
0x180109ef6  jz      loc_18010A2DC
0x180109efc  cmp     qword ptr [r8+20h], 0
0x180109f01  jz      loc_18010A2DC
0x180109f07  lea     ebp, [rdx-2]
0x180109f0a  cmp     ecx, 2
0x180109f0d  jnz     loc_18010A06D
0x180109f13  cmp     dword ptr [r8], 4
0x180109f17  jnb     loc_18010A06D
0x180109f1d  mov     rcx, [r8+28h]; unsigned __int16 *
0x180109f21  lea     rdx, aPrintconfigDll_1; "PrintConfig.dll"
0x180109f28  xor     ebx, ebx
0x180109f2a  call    ?DoesFullPathMatchFile@@YA_NPEBG0@Z; DoesFullPathMatchFile(ushort const *,ushort const *)
0x180109f2f  mov     rcx, [rsi+20h]; pszSrc
0x180109f33  movzx   edx, al
0x180109f36  call    LoadRawBinaryData
0x180109f3b  mov     r12, rax
0x180109f3e  test    rax, rax
0x180109f41  jz      loc_18010A143
0x180109f47  xor     r8d, r8d
0x180109f4a  mov     rcx, rax
0x180109f4d  call    InitBinaryData
0x180109f52  mov     rbx, rax
0x180109f55  test    rax, rax
0x180109f58  jz      loc_18010A143
0x180109f5e  cmp     dword ptr [rax+38h], 0
0x180109f62  jz      loc_18010A143
0x180109f68  mov     eax, [rax+38h]
0x180109f6b  add     rax, rbx
0x180109f6e  jz      loc_18010A143
0x180109f74  mov     ecx, [rax+138h]
0x180109f7a  test    ecx, ecx
0x180109f7c  jz      loc_18010A048
0x180109f82  mov     r15, [rax+140h]
0x180109f89  add     r15, rcx
0x180109f8c  jz      loc_18010A043
0x180109f92  lea     edx, [rbp+2Dh]; Ch
0x180109f95  mov     rcx, r15; Str
0x180109f98  call    cs:__imp_wcsrchr
0x180109f9e  mov     r13, rax
0x180109fa1  test    rax, rax
0x180109fa4  jz      loc_18010A043
0x180109faa  mov     rcx, [rsi+20h]; Src
0x180109fae  xor     edi, edi
0x180109fb0  mov     [rsp+68h+pszSrc], rdi
0x180109fb8  call    PtstrGetDriverDirectory
0x180109fbd  mov     r14, rax
0x180109fc0  test    rax, rax
0x180109fc3  jz      short loc_18010A012
0x180109fc5  mov     r8, rax
0x180109fc8  lea     rcx, [rsp+68h+pszSrc]
0x180109fd0  mov     rdx, r15
0x180109fd3  call    BExpandOemFilename
0x180109fd8  mov     rdi, [rsp+68h+pszSrc]
0x180109fe0  test    eax, eax
0x180109fe2  jz      short loc_18010A012
0x180109fe4  lea     r8, aSer; ".SER"
0x180109feb  mov     rdx, r13; unsigned __int16 *
0x180109fee  mov     rcx, rdi; pszSrc
0x180109ff1  call    ?GetBinaryFileName@UniDrvUI@@YAPEBGPEBG00@Z; UniDrvUI::GetBinaryFileName(ushort const *,ushort const *,ushort const *)
0x180109ff6  mov     r15, rax
0x180109ff9  test    rax, rax
0x180109ffc  jz      short loc_18010A02C
0x180109ffe  mov     rcx, rax; lpFileName
0x18010a001  call    cs:__imp_DeleteFileW
0x18010a007  mov     rcx, r15; hMem
0x18010a00a  call    cs:__imp_LocalFree
0x18010a010  jmp     short loc_18010A02C
0x18010a012  lea     rdx, aFailToExpandLo; "Fail to expand loBidiQueryFileName to f"...
0x18010a019  lea     rcx, aUnidrvuiDrvdri; "UniDrvUI::DrvDriverEvent"
0x18010a020  call    ?WriteDbgTraceWarning@DriverUiTelemetry@DriverUi@@SAXPEADPEAGZZ; DriverUi::DriverUiTelemetry::WriteDbgTraceWarning(char *,ushort *,...)
0x18010a025  xor     ebp, ebp
0x18010a027  test    r14, r14
0x18010a02a  jz      short loc_18010A035
0x18010a02c  mov     rcx, r14; hMem
0x18010a02f  call    cs:__imp_LocalFree
0x18010a035  test    rdi, rdi
0x18010a038  jz      short loc_18010A043
0x18010a03a  mov     rcx, rdi; hMem
0x18010a03d  call    cs:__imp_LocalFree
0x18010a043  mov     r15d, [rsp+68h+arg_0]
0x18010a048  mov     rcx, rbx
0x18010a04b  call    FreeBinaryData
0x18010a050  test    r12, r12
0x18010a053  jz      short loc_18010A05D
0x18010a055  mov     rcx, r12; hMem
0x18010a058  call    UnloadRawBinaryData
0x18010a05d  test    ebp, ebp
0x18010a05f  jz      loc_18010A25D
0x18010a065  mov     r12, [rsp+68h+arg_18]
0x18010a06d  mov     rdx, [rsi+28h]
0x18010a071  mov     r8, rsi
0x18010a074  call    PGetOemPluginInfo
0x18010a079  mov     rdi, rax
0x18010a07c  test    rax, rax
0x18010a07f  jz      loc_18010A22C
0x18010a085  mov     r8d, 1
0x18010a08b  mov     rdx, rax
0x18010a08e  xor     ecx, ecx; this
0x18010a090  call    BLoadOEMPluginModulesInternal
0x18010a095  test    eax, eax
0x18010a097  jz      loc_18010A22C
0x18010a09d  mov     r14d, [rdi+8]
0x18010a0a1  lea     rbx, [rdi+18h]
0x18010a0a5  test    r14d, r14d
0x18010a0a8  jz      loc_18010A222
0x18010a0ae  mov     r8, qword ptr cs:IID_IPrintOemUI.Data4
0x18010a0b5  mov     r9, qword ptr cs:IID_IPrintOemUI.Data1
0x18010a0bc  mov     rdx, qword ptr cs:IID_IPrintOemUI2.Data4
0x18010a0c3  mov     r10, qword ptr cs:IID_IPrintOemUI2.Data1
0x18010a0ca  dec     r14d
0x18010a0cd  cmp     qword ptr [rbx+20h], 0
0x18010a0d2  jz      loc_18010A212
0x18010a0d8  mov     rcx, [rbx+48h]
0x18010a0dc  test    rcx, rcx
0x18010a0df  jz      loc_18010A180
0x18010a0e5  cmp     [rbx+50h], r9
0x18010a0e9  jnz     short loc_18010A0F1
0x18010a0eb  cmp     [rbx+58h], r8
0x18010a0ef  jz      short loc_18010A0FD
0x18010a0f1  cmp     [rbx+50h], r10
0x18010a0f5  jnz     short loc_18010A16F
0x18010a0f7  cmp     [rbx+58h], rdx
0x18010a0fb  jnz     short loc_18010A16F
0x18010a0fd  mov     rax, [rcx]
0x18010a100  mov     r9, rsi
0x18010a103  mov     r8d, 3
0x18010a109  mov     [rsp+68h+var_48], r12
0x18010a10e  mov     edx, r15d
0x18010a111  mov     rax, [rax+68h]
0x18010a115  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18010a11a  cmp     eax, 80004001h
0x18010a11f  jz      loc_18010A1F6
0x18010a125  mov     r8, qword ptr cs:IID_IPrintOemUI.Data4
0x18010a12c  mov     r9, qword ptr cs:IID_IPrintOemUI.Data1
0x18010a133  mov     rdx, qword ptr cs:IID_IPrintOemUI2.Data4
0x18010a13a  mov     r10, qword ptr cs:IID_IPrintOemUI2.Data1
0x18010a141  jmp     short loc_18010A174
0x18010a143  call    cs:__imp_GetLastError
0x18010a149  mov     r8d, eax
0x18010a14c  lea     rdx, aCannotLoadPrin_0; "Cannot load printer description data du"...
0x18010a153  lea     rcx, aUnidrvuiDrvdri; "UniDrvUI::DrvDriverEvent"
0x18010a15a  call    ?WriteDbgTraceWarning@DriverUiTelemetry@DriverUi@@SAXPEADPEAGZZ; DriverUi::DriverUiTelemetry::WriteDbgTraceWarning(char *,ushort *,...)
0x18010a15f  xor     ebp, ebp
0x18010a161  test    rbx, rbx
0x18010a164  jz      loc_18010A050
0x18010a16a  jmp     loc_18010A048
0x18010a16f  mov     eax, 80004002h
0x18010a174  mov     ebp, eax
0x18010a176  not     ebp
0x18010a178  shr     ebp, 1Fh
0x18010a17b  jmp     loc_18010A212
0x18010a180  test    byte ptr [rbx+65h], 20h
0x18010a184  jz      short loc_18010A18F
0x18010a186  mov     rax, [rbx+0D0h]
0x18010a18d  jmp     short loc_18010A1B8
0x18010a18f  mov     edx, 0Dh
0x18010a194  mov     rcx, rbx
0x18010a197  call    PGetOemEntrypointAddress
0x18010a19c  mov     r8, qword ptr cs:IID_IPrintOemUI.Data4
0x18010a1a3  mov     r9, qword ptr cs:IID_IPrintOemUI.Data1
0x18010a1aa  mov     rdx, qword ptr cs:IID_IPrintOemUI2.Data4
0x18010a1b1  mov     r10, qword ptr cs:IID_IPrintOemUI2.Data1
0x18010a1b8  test    rax, rax
0x18010a1bb  jz      short loc_18010A212
0x18010a1bd  mov     r9, r12
0x18010a1c0  mov     r8, rsi
0x18010a1c3  mov     edx, 3
0x18010a1c8  mov     ecx, r15d
0x18010a1cb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18010a1d0  test    eax, eax
0x18010a1d2  jnz     short loc_18010A1F6
0x18010a1d4  call    cs:__imp_GetLastError
0x18010a1da  mov     r8, [rbx+8]
0x18010a1de  lea     rdx, aOemdriverevent_1; "OEMDriverEvent failed for '%ws': %d\n"
0x18010a1e5  mov     r9d, eax
0x18010a1e8  lea     rcx, aUnidrvuiDrvdri; "UniDrvUI::DrvDriverEvent"
0x18010a1ef  call    ?WriteDbgTraceWarning@DriverUiTelemetry@DriverUi@@SAXPEADPEAGZZ; DriverUi::DriverUiTelemetry::WriteDbgTraceWarning(char *,ushort *,...)
0x18010a1f4  xor     ebp, ebp
0x18010a1f6  mov     r10, qword ptr cs:IID_IPrintOemUI2.Data1
0x18010a1fd  mov     rdx, qword ptr cs:IID_IPrintOemUI2.Data4
0x18010a204  mov     r9, qword ptr cs:IID_IPrintOemUI.Data1
0x18010a20b  mov     r8, qword ptr cs:IID_IPrintOemUI.Data4
0x18010a212  add     rbx, 0D8h
0x18010a219  test    r14d, r14d
0x18010a21c  jnz     loc_18010A0CA
0x18010a222  mov     rcx, rdi
0x18010a225  call    VFreeOemPluginInfo
0x18010a22a  jmp     short loc_18010A257
0x18010a22c  call    cs:__imp_GetLastError
0x18010a232  mov     r8d, eax
0x18010a235  lea     rdx, aDrvdriverevent_2; "DrvDriverEvent, Cannot load OEM plugins"...
0x18010a23c  lea     rcx, aUnidrvuiDrvdri; "UniDrvUI::DrvDriverEvent"
0x18010a243  call    ?WriteDbgTraceWarning@DriverUiTelemetry@DriverUi@@SAXPEADPEAGZZ; DriverUi::DriverUiTelemetry::WriteDbgTraceWarning(char *,ushort *,...)
0x18010a248  test    rdi, rdi
0x18010a24b  jz      short loc_18010A255
0x18010a24d  mov     rcx, rdi
0x18010a250  call    VFreeOemPluginInfo
0x18010a255  xor     ebp, ebp
0x18010a257  cmp     r15d, 2
0x18010a25b  jnz     short loc_18010A2D8
0x18010a25d  cmp     dword ptr [rsi], 4
0x18010a260  jnb     short loc_18010A2D8
0x18010a262  mov     rax, cs:off_1801D1930; ".GPD"
0x18010a269  test    rax, rax
0x18010a26c  jz      short loc_18010A2D8
0x18010a26e  lea     rdi, off_1801D1930; ".GPD"
0x18010a275  mov     r8, [rdi+8]; unsigned __int16 *
0x18010a279  mov     rdx, rax; unsigned __int16 *
0x18010a27c  mov     rcx, [rsi+20h]; pszSrc
0x18010a280  call    ?GetBinaryFileName@UniDrvUI@@YAPEBGPEBG00@Z; UniDrvUI::GetBinaryFileName(ushort const *,ushort const *,ushort const *)
0x18010a285  mov     rbx, rax
0x18010a288  test    rax, rax
0x18010a28b  jz      short loc_18010A2CC
0x18010a28d  mov     rcx, rax; lpFileName
0x18010a290  call    cs:__imp_DeleteFileW
0x18010a296  test    eax, eax
0x18010a298  jnz     short loc_18010A2C3
0x18010a29a  xor     edx, edx; lpNewFileName
0x18010a29c  lea     r8d, [rax+4]; dwFlags
0x18010a2a0  mov     rcx, rbx; lpExistingFileName
0x18010a2a3  call    cs:__imp_MoveFileExW
0x18010a2a9  test    eax, eax
0x18010a2ab  jnz     short loc_18010A2C3
0x18010a2ad  mov     r8, rbx
0x18010a2b0  lea     rdx, aOemdriverevent_0; "OEMDriverEvent failed to delete BUD tem"...
0x18010a2b7  lea     rcx, aUnidrvuiDrvdri; "UniDrvUI::DrvDriverEvent"
0x18010a2be  call    ?WriteDbgTraceWarning@DriverUiTelemetry@DriverUi@@SAXPEADPEAGZZ; DriverUi::DriverUiTelemetry::WriteDbgTraceWarning(char *,ushort *,...)
0x18010a2c3  mov     rcx, rbx; hMem
0x18010a2c6  call    cs:__imp_LocalFree
0x18010a2cc  add     rdi, 10h
0x18010a2d0  mov     rax, [rdi]
0x18010a2d3  test    rax, rax
0x18010a2d6  jnz     short loc_18010A275
0x18010a2d8  mov     eax, ebp
0x18010a2da  jmp     short loc_18010A2DE
0x18010a2dc  xor     eax, eax
0x18010a2de  mov     rbx, [rsp+68h+arg_8]
0x18010a2e3  add     rsp, 30h
0x18010a2e7  pop     r15
0x18010a2e9  pop     r14
0x18010a2eb  pop     r13
0x18010a2ed  pop     r12
0x18010a2ef  pop     rdi
0x18010a2f0  pop     rsi
0x18010a2f1  pop     rbp
0x18010a2f2  retn
```
