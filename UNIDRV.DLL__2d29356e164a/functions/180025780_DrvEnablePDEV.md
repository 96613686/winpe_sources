# DrvEnablePDEV

- ea: `0x180025780`
- end: `0x180025e44`
- name: `DrvEnablePDEV`
- size: `1732`
- prototype: `DHPDEV __stdcall(DEVMODEW *pdm, LPWSTR pwszLogAddress, ULONG cPat, HSURF *phsurfPatterns, ULONG cjCaps, ULONG *pdevcaps, ULONG cjDevInfo, DEVINFO *pdi, HDEV hdev, LPWSTR pwszDeviceName, HANDLE hDriver)`
- caller_count: `0`
- callee_count: `28`
- tags: `registry_config, loader_planting, installer_update, broker_com_uri`

## callees

- `0x18000420c`
- `0x1800241ac`
- `0x1800246a4`
- `0x18002478c`
- `0x180024c64`
- `0x18002511c`
- `0x18002537c`
- `0x18002540c`
- `0x180025618`
- `0x1800256c8`
- `0x180025780`
- `0x180025e4c`
- `0x180026154`
- `0x1800264bc`
- `0x18002707c`
- `0x1800271d4`
- `0x1800272f0`
- `0x180027544`
- `0x1800278ec`
- `0x180027964`
- `0x18003e994`
- `0x180042518`
- `0x1800487e0`
- `0x180049128`
- `0x1800491dc`
- `0x18004a744`
- `0x18004ec64`
- `0x180075010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!wcsrchr` at `0x180025967`
- `api-ms-win-crt-private-l1-1-0!wcsrchr` at `0x180025b84`
- `api-ms-win-crt-private-l1-1-0!wcsrchr` at `0x180025967`
- `api-ms-win-crt-private-l1-1-0!wcsrchr` at `0x180025b84`
- `KERNEL32!LocalAlloc` at `0x1800259bf`
- `KERNEL32!LocalAlloc` at `0x1800259dc`
- `KERNEL32!LocalAlloc` at `0x1800259bf`
- `KERNEL32!LocalAlloc` at `0x1800259dc`

## string_xrefs

- `0x18002597d`: `PrintConfig.dll`
- `0x180025b9a`: `PrintConfig.dll`

## pseudocode

```c
DHPDEV __stdcall DrvEnablePDEV(
        DEVMODEW *pdm,
        LPWSTR pwszLogAddress,
        ULONG cPat,
        HSURF *phsurfPatterns,
        ULONG cjCaps,
        ULONG *pdevcaps,
        ULONG cjDevInfo,
        DEVINFO *pdi,
        HDEV hdev,
        LPWSTR pwszDeviceName,
        HANDLE hDriver)
{
  __int64 v13; // rdi
  __int64 PrinterDriver; // rax
  __int64 v15; // rdx
  int FilenameByRole; // r14d
  unsigned int v17; // r15d
  struct PrintConfigData *v18; // rbx
  __int64 v19; // rax
  __int64 v20; // rcx
  __int64 v21; // rax
  __int64 v22; // rcx
  __int64 v23; // rax
  const wchar_t *v24; // rbx
  wchar_t *v25; // rax
  const wchar_t *v26; // rcx
  HLOCAL v27; // rax
  HLOCAL v28; // rax
  __int64 v29; // rdx
  __int64 updated; // rax
  __int64 v31; // rcx
  __int64 v33; // rdx
  bool v34; // zf
  __int64 v35; // rdx
  const wchar_t *v36; // rbx
  wchar_t *v37; // rax
  const wchar_t *v38; // rcx
  __int64 v39; // r10
  __int64 v40; // rax
  __int64 v41; // rax
  int v42; // r15d
  __int64 v43; // rbx
  __int64 v44; // rax
  _QWORD *v45; // r14
  __int64 v46; // rcx
  __int64 v47; // rax
  __int64 v48; // rbx
  __int64 v49; // rax
  __int64 v50; // rax
  __int64 (__fastcall *v51)(__int64, LPWSTR, _QWORD, HSURF *, ULONG, ULONG *, __int64, DEVINFO *, __int128 *); // rax
  __int64 v52; // [rsp+28h] [rbp-D8h]
  __int64 v53; // [rsp+30h] [rbp-D0h]
  __int64 v54; // [rsp+38h] [rbp-C8h]
  __int128 v57; // [rsp+80h] [rbp-80h] BYREF
  struct PrintConfigData *v58; // [rsp+90h] [rbp-70h] BYREF
  DEVMODEW *v59; // [rsp+98h] [rbp-68h]
  __int128 v60; // [rsp+A0h] [rbp-60h] BYREF
  wchar_t pszSrc[264]; // [rsp+B0h] [rbp-50h] BYREF

  v59 = pdm;
  v60 = 0;
  v57 = 0;
  memset_0(pszSrc, 0, 0x208u);
  if ( cjCaps < 0x140 )
    return 0;
  memset_0(phsurfPatterns, 0, 8LL * cPat);
  v13 = PAllocPDEVData(hDriver);
  if ( !v13 )
    goto LABEL_29;
  PrinterDriver = MyGetPrinterDriver(hDriver);
  *(_QWORD *)(v13 + 1720) = PrinterDriver;
  if ( !PrinterDriver )
    goto LABEL_29;
  v58 = 0;
  FilenameByRole = CreatePrintConfigData(hDriver, &v58);
  v17 = 1;
  if ( FilenameByRole >= 0 )
  {
    v18 = v58;
    FilenameByRole = CommonGetFilenameByRole(v58, v15, pszSrc);
    if ( v18 )
      (*(void (__fastcall **)(struct PrintConfigData *, __int64))(*(_QWORD *)v18 + 32LL))(v18, 1);
  }
  if ( FilenameByRole < 0 )
    goto LABEL_29;
  v19 = GPDLoadRawBinaryData(pszSrc);
  *(_QWORD *)(v13 + 2008) = v19;
  if ( !v19 )
    goto LABEL_29;
  v21 = PGetDefaultDriverInfo(v20, v19);
  *(_QWORD *)(v13 + 2000) = v21;
  if ( !v21 )
    goto LABEL_29;
  v22 = *(_QWORD *)(v21 + 104);
  *(_QWORD *)(v13 + 2016) = v22;
  if ( !v22 )
    goto LABEL_29;
  v23 = *(_DWORD *)(v22 + 56) ? v22 + *(unsigned int *)(v22 + 56) : 0LL;
  *(_QWORD *)(v13 + 2024) = v23;
  if ( !v23 || !(unsigned int)BGetPrinterProperties(*(HANDLE *)(v13 + 24)) || !(unsigned int)BLoadAndInitOemPlugins(v13) )
    goto LABEL_29;
  v24 = *(const wchar_t **)(*(_QWORD *)(v13 + 1720) + 40LL);
  v25 = wcsrchr(v24, 0x5Cu);
  v26 = v25 + 1;
  if ( !v25 )
    v26 = v24;
  if ( !v26 || wcsicmp(v26, L"PrintConfig.dll") )
    v17 = 0;
  if ( !(unsigned int)BInitWinResData(v13 + 128, hDriver, *(_QWORD *)(v13 + 2024), v17) )
    goto LABEL_29;
  v27 = LocalAlloc(0x40u, 0x200u);
  *(_QWORD *)(v13 + 2592) = v27;
  if ( !v27 )
    goto LABEL_29;
  v28 = LocalAlloc(0x40u, 0x1000u);
  *(_QWORD *)(v13 + 4112) = v28;
  if ( !v28 || !(unsigned int)BMergeAndValidateDevmode(v13, v59, &v60) )
    goto LABEL_29;
  v54 = v13 + 2032;
  v53 = *(_QWORD *)(v13 + 3976);
  updated = PGetUpdateDriverInfo(v13, v29, *(_QWORD *)(v13 + 2016), *(_QWORD *)(v13 + 2592), *(_QWORD *)(v13 + 2008));
  *(_QWORD *)(v13 + 2000) = updated;
  if ( !updated )
  {
    *(_QWORD *)(v13 + 2016) = 0;
    goto LABEL_29;
  }
  v31 = *(_QWORD *)(updated + 104);
  *(_QWORD *)(v13 + 2016) = v31;
  if ( !v31 )
  {
LABEL_29:
    VFreePDEVData((_DWORD *)v13);
    return 0;
  }
  if ( !*(_DWORD *)(v31 + 56) )
  {
    *(_QWORD *)(v13 + 2024) = 0;
    goto LABEL_29;
  }
  v33 = *(unsigned int *)(v31 + 56);
  v34 = v31 + v33 == 0;
  v35 = v31 + v33;
  *(_QWORD *)(v13 + 2024) = v35;
  if ( v34 )
    goto LABEL_29;
  *(_DWORD *)(v13 + 1872) |= 0xAu;
  *(_QWORD *)(v13 + 1688) = v35;
  *(_QWORD *)(v13 + 16) = hdev;
  *(_DWORD *)(v13 + 120) = 239103;
  if ( !(unsigned int)BInitPDEV(v13, &v60)
    || !(unsigned int)BInitGdiInfo(v13, pdevcaps)
    || !(unsigned int)BInitDevInfo(v13, pdi, cjDevInfo)
    || !(unsigned int)VMInit((struct _PDEV *)v13)
    || !(unsigned int)RMInit(v13, pdi, pdevcaps)
    || !(unsigned int)BInitPalDevInfo(v13, (__int64)pdi, (__int64)pdevcaps)
    || !(unsigned int)FMInit(v13, pdi, pdevcaps) )
  {
    goto LABEL_29;
  }
  *(_QWORD *)&v57 = 0x2800010000LL;
  *((_QWORD *)&v57 + 1) = &qword_180090000;
  v36 = *(const wchar_t **)(*(_QWORD *)(v13 + 1720) + 40LL);
  v37 = wcsrchr(v36, 0x5Cu);
  v38 = v37 + 1;
  if ( !v37 )
    v38 = v36;
  if ( v38 && !wcsicmp(v38, L"PrintConfig.dll") )
  {
    *(_DWORD *)(v13 + 116) |= 0x100u;
    GetPrinterDriverIDAsString(hDriver, v13 + 4344);
  }
  v39 = *(_QWORD *)(v13 + 4184);
  if ( v39 && *(_QWORD *)(v39 + 112) )
  {
    v48 = *(_QWORD *)(v13 + 8);
    *(_QWORD *)(v13 + 8) = *(_QWORD *)(v13 + 4176);
    LODWORD(v53) = cjDevInfo;
    *(_QWORD *)(v13 + 4176) = (*(__int64 (__fastcall **)(__int64, LPWSTR, _QWORD, HSURF *, ULONG, ULONG *, __int64, DEVINFO *, __int128 *))(v39 + 112))(
                                v13,
                                pwszDeviceName,
                                cPat,
                                phsurfPatterns,
                                cjCaps,
                                pdevcaps,
                                v53,
                                pdi,
                                &v57);
    *(_QWORD *)(v13 + 8) = v48;
  }
  v40 = *(_QWORD *)(v13 + 4184);
  if ( v40 )
  {
    if ( *(_QWORD *)(v40 + 112) && !*(_QWORD *)(v13 + 4176) )
      goto LABEL_29;
  }
  v41 = *(_QWORD *)(v13 + 1880);
  v42 = *(_DWORD *)(v41 + 8);
  v43 = v41 + 24;
  while ( v42 )
  {
    v44 = *(_QWORD *)(v43 + 32);
    if ( !v44 )
      goto LABEL_59;
    *(_QWORD *)(v13 + 32) = v44;
    v45 = (_QWORD *)(v43 + 40);
    *(_QWORD *)(v13 + 8) = *(_QWORD *)(v43 + 40);
    *(_QWORD *)(v13 + 48) = *(_QWORD *)(v43 + 56);
    v46 = *(_QWORD *)(v43 + 72);
    if ( v46 )
    {
      v47 = *(_QWORD *)(v43 + 80) - *(_QWORD *)&IID_IPrintOemUni.Data1;
      if ( !v47 )
        v47 = *(_QWORD *)(v43 + 88) - *(_QWORD *)IID_IPrintOemUni.Data4;
      if ( !v47 )
        goto LABEL_82;
      v49 = *(_QWORD *)(v43 + 80) - *(_QWORD *)&IID_IPrintOemUni2.Data1;
      if ( !v49 )
        v49 = *(_QWORD *)(v43 + 88) - *(_QWORD *)IID_IPrintOemUni2.Data4;
      if ( !v49 )
        goto LABEL_82;
      v50 = *(_QWORD *)(v43 + 80) - *(_QWORD *)&IID_IPrintOemUni3.Data1;
      if ( !v50 )
        v50 = *(_QWORD *)(v43 + 88) - *(_QWORD *)IID_IPrintOemUni3.Data4;
      if ( !v50 )
      {
LABEL_82:
        LODWORD(v54) = cjDevInfo;
        LODWORD(v52) = cjCaps;
        if ( (*(unsigned int (__fastcall **)(__int64, __int64, LPWSTR, _QWORD, HSURF *, __int64, ULONG *, __int64, DEVINFO *, __int128 *, __int64))(*(_QWORD *)v46 + 56LL))(
               v46,
               v13,
               pwszDeviceName,
               cPat,
               phsurfPatterns,
               v52,
               pdevcaps,
               v54,
               pdi,
               &v57,
               v43 + 40) == -2147467263 )
          goto LABEL_59;
      }
    }
    else
    {
      if ( (*(_BYTE *)(v43 + 100) & 0x10) != 0 )
        v51 = *(__int64 (__fastcall **)(__int64, LPWSTR, _QWORD, HSURF *, ULONG, ULONG *, __int64, DEVINFO *, __int128 *))(v43 + 136);
      else
        v51 = (__int64 (__fastcall *)(__int64, LPWSTR, _QWORD, HSURF *, ULONG, ULONG *, __int64, DEVINFO *, __int128 *))PGetOemEntrypointAddress(v43, 4);
      if ( !v51 )
        goto LABEL_59;
      LODWORD(v53) = cjDevInfo;
      *v45 = v51(v13, pwszDeviceName, cPat, phsurfPatterns, cjCaps, pdevcaps, v53, pdi, &v57);
    }
    if ( !*v45 )
      goto LABEL_29;
    if ( pdevcaps[60] == 4 && (pdevcaps[61] & 0xFF000000) != 0 && (pdevcaps[61] & 8) != 0 )
      VInitPal8BPPMaskMode(v13, pdevcaps);
    *(_DWORD *)(v43 + 48) |= 2u;
LABEL_59:
    --v42;
    v43 += 176;
  }
  VUnloadFreeBinaryData(v13);
  return (DHPDEV)v13;
}

```

## disassembly

```asm
0x180025780  mov     [rsp-8+arg_8], rbx
0x180025785  push    rbp
0x180025786  push    rsi
0x180025787  push    rdi
0x180025788  push    r12
0x18002578a  push    r13
0x18002578c  push    r14
0x18002578e  push    r15
0x180025790  lea     rbp, [rsp-1D0h]
0x180025798  sub     rsp, 2D0h
0x18002579f  mov     rax, cs:__security_cookie
0x1800257a6  xor     rax, rsp
0x1800257a9  mov     [rbp+200h+var_40], rax
0x1800257b0  mov     eax, [rbp+200h+cjDevInfo]
0x1800257b6  xorps   xmm0, xmm0
0x1800257b9  mov     r14d, [rbp+200h+cjCaps]
0x1800257c0  xorps   xmm1, xmm1
0x1800257c3  mov     rsi, [rbp+200h+pdevcaps]
0x1800257ca  xor     edx, edx; Val
0x1800257cc  mov     r13, [rbp+200h+pdi]
0x1800257d3  mov     rdi, r9
0x1800257d6  mov     r12, [rbp+200h+hDriver]
0x1800257dd  mov     ebx, r8d
0x1800257e0  mov     r8d, 208h; Size
0x1800257e6  mov     [rsp+300h+var_2A0], eax
0x1800257ea  mov     rax, [rbp+200h+pwszDeviceName]
0x1800257f1  mov     [rbp+200h+var_268], rcx
0x1800257f5  lea     rcx, [rbp+200h+pszSrc]; void *
0x1800257f9  mov     [rsp+300h+var_288], rax
0x1800257fe  mov     [rsp+300h+var_290], r9
0x180025803  mov     [rsp+300h+var_298], ebx
0x180025807  mov     [rsp+300h+var_29C], r14d
0x18002580c  movups  [rbp+200h+var_260], xmm0
0x180025810  movups  [rbp+200h+var_280], xmm1
0x180025814  call    memset_0
0x180025819  cmp     r14d, 140h
0x180025820  jb      loc_180025A6A
0x180025826  mov     r8d, ebx
0x180025829  xor     edx, edx; Val
0x18002582b  shl     r8, 3; Size
0x18002582f  mov     rcx, rdi; void *
0x180025832  call    memset_0
0x180025837  mov     rcx, r12
0x18002583a  call    PAllocPDEVData
0x18002583f  mov     rdi, rax
0x180025842  test    rax, rax
0x180025845  jz      loc_180025A62
0x18002584b  mov     r8d, 3
0x180025851  mov     rcx, r12; hPrinter
0x180025854  call    MyGetPrinterDriver
0x180025859  mov     [rdi+6B8h], rax
0x180025860  test    rax, rax
0x180025863  jz      loc_180025A62
0x180025869  lea     rdx, [rbp+200h+var_270]; struct PrintConfigData **
0x18002586d  mov     [rbp+200h+var_270], 0
0x180025875  mov     rcx, r12; void *
0x180025878  call    ?CreatePrintConfigData@@YAJPEAXPEAPEAVPrintConfigData@@@Z; CreatePrintConfigData(void *,PrintConfigData * *)
0x18002587d  mov     r14d, eax
0x180025880  mov     r15d, 1
0x180025886  test    eax, eax
0x180025888  js      short loc_1800258B4
0x18002588a  mov     rbx, [rbp+200h+var_270]
0x18002588e  lea     r8, [rbp+200h+pszSrc]
0x180025892  mov     rcx, rbx
0x180025895  call    ?CommonGetFilenameByRole@@YAJPEAVPrintConfigData@@W4PrinterDriverRole@@PEAGK@Z; CommonGetFilenameByRole(PrintConfigData *,PrinterDriverRole,ushort *,ulong)
0x18002589a  mov     r14d, eax
0x18002589d  test    rbx, rbx
0x1800258a0  jz      short loc_1800258B4
0x1800258a2  mov     rax, [rbx]
0x1800258a5  mov     edx, r15d
0x1800258a8  mov     rcx, rbx
0x1800258ab  mov     rax, [rax+20h]
0x1800258af  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800258b4  test    r14d, r14d
0x1800258b7  js      loc_180025A62
0x1800258bd  lea     rcx, [rbp+200h+pszSrc]; pszSrc
0x1800258c1  call    GPDLoadRawBinaryData
0x1800258c6  mov     [rdi+7D8h], rax
0x1800258cd  test    rax, rax
0x1800258d0  jz      loc_180025A62
0x1800258d6  mov     rdx, rax
0x1800258d9  call    PGetDefaultDriverInfo
0x1800258de  mov     [rdi+7D0h], rax
0x1800258e5  test    rax, rax
0x1800258e8  jz      loc_180025A62
0x1800258ee  mov     rcx, [rax+68h]
0x1800258f2  mov     [rdi+7E0h], rcx
0x1800258f9  test    rcx, rcx
0x1800258fc  jz      loc_180025A62
0x180025902  cmp     dword ptr [rcx+38h], 0
0x180025906  jz      loc_180025CBD
0x18002590c  mov     eax, [rcx+38h]
0x18002590f  add     rax, rcx
0x180025912  mov     [rdi+7E8h], rax
0x180025919  test    rax, rax
0x18002591c  jz      loc_180025A62
0x180025922  mov     rdx, [rdi+7D8h]
0x180025929  lea     r14, [rdi+7F0h]
0x180025930  mov     rcx, [rdi+18h]; hPrinter
0x180025934  mov     r8, r14
0x180025937  call    BGetPrinterProperties
0x18002593c  test    eax, eax
0x18002593e  jz      loc_180025A62
0x180025944  mov     rcx, rdi
0x180025947  call    BLoadAndInitOemPlugins
0x18002594c  test    eax, eax
0x18002594e  jz      loc_180025A62
0x180025954  mov     rax, [rdi+6B8h]
0x18002595b  mov     edx, 5Ch ; '\'; Ch
0x180025960  mov     rbx, [rax+28h]
0x180025964  mov     rcx, rbx; Str
0x180025967  call    cs:__imp_wcsrchr
0x18002596d  test    rax, rax
0x180025970  lea     rcx, [rax+2]
0x180025974  cmovz   rcx, rbx; String1
0x180025978  test    rcx, rcx
0x18002597b  jz      short loc_18002598D
0x18002597d  lea     rdx, aPrintconfigDll; "PrintConfig.dll"
0x180025984  call    _wcsicmp
0x180025989  test    eax, eax
0x18002598b  jz      short loc_180025990
0x18002598d  xor     r15d, r15d
0x180025990  mov     r8, [rdi+7E8h]
0x180025997  lea     rcx, [rdi+80h]
0x18002599e  mov     r9d, r15d
0x1800259a1  mov     rdx, r12
0x1800259a4  call    BInitWinResData
0x1800259a9  xor     r15d, r15d
0x1800259ac  test    eax, eax
0x1800259ae  jz      loc_180025A62
0x1800259b4  lea     ebx, [r15+40h]
0x1800259b8  mov     edx, 200h; uBytes
0x1800259bd  mov     ecx, ebx; uFlags
0x1800259bf  call    cs:__imp_LocalAlloc
0x1800259c5  mov     [rdi+0A20h], rax
0x1800259cc  test    rax, rax
0x1800259cf  jz      loc_180025A62
0x1800259d5  mov     edx, 1000h; uBytes
0x1800259da  mov     ecx, ebx; uFlags
0x1800259dc  call    cs:__imp_LocalAlloc
0x1800259e2  mov     [rdi+1010h], rax
0x1800259e9  test    rax, rax
0x1800259ec  jz      short loc_180025A62
0x1800259ee  mov     rdx, [rbp+200h+var_268]
0x1800259f2  lea     r8, [rbp+200h+var_260]
0x1800259f6  mov     rcx, rdi
0x1800259f9  call    BMergeAndValidateDevmode
0x1800259fe  test    eax, eax
0x180025a00  jz      short loc_180025A62
0x180025a02  mov     rax, [rdi+0F88h]
0x180025a09  mov     rcx, rdi
0x180025a0c  mov     r9, [rdi+0A20h]
0x180025a13  mov     r8, [rdi+7E0h]
0x180025a1a  mov     [rsp+300h+var_2C8], r14
0x180025a1f  mov     [rsp+300h+var_2D0], rax
0x180025a24  mov     rax, [rdi+7D8h]
0x180025a2b  mov     [rsp+300h+var_2E0], rax
0x180025a30  call    PGetUpdateDriverInfo
0x180025a35  mov     [rdi+7D0h], rax
0x180025a3c  test    rax, rax
0x180025a3f  jz      loc_180025CD4
0x180025a45  mov     rcx, [rax+68h]
0x180025a49  mov     [rdi+7E0h], rcx
0x180025a50  test    rcx, rcx
0x180025a53  jz      short loc_180025A62
0x180025a55  cmp     [rcx+38h], r15d
0x180025a59  jnz     short loc_180025A96
0x180025a5b  mov     [rdi+7E8h], r15
0x180025a62  mov     rcx, rdi; hMem
0x180025a65  call    VFreePDEVData
0x180025a6a  xor     eax, eax
0x180025a6c  mov     rcx, [rbp+200h+var_40]
0x180025a73  xor     rcx, rsp; StackCookie
0x180025a76  call    __security_check_cookie
0x180025a7b  mov     rbx, [rsp+300h+arg_8]
0x180025a83  add     rsp, 2D0h
0x180025a8a  pop     r15
0x180025a8c  pop     r14
0x180025a8e  pop     r13
0x180025a90  pop     r12
0x180025a92  pop     rdi
0x180025a93  pop     rsi
0x180025a94  pop     rbp
0x180025a95  retn
0x180025a96  mov     edx, [rcx+38h]
0x180025a99  add     rdx, rcx
0x180025a9c  mov     [rdi+7E8h], rdx
0x180025aa3  jz      short loc_180025A62
0x180025aa5  mov     rax, [rbp+200h+hdev]
0x180025aac  mov     rcx, rdi
0x180025aaf  or      dword ptr [rdi+750h], 0Ah
0x180025ab6  mov     [rdi+698h], rdx
0x180025abd  lea     rdx, [rbp+200h+var_260]
0x180025ac1  mov     [rdi+10h], rax
0x180025ac5  mov     dword ptr [rdi+78h], 3A5FFh
0x180025acc  call    BInitPDEV
0x180025ad1  test    eax, eax
0x180025ad3  jz      short loc_180025A62
0x180025ad5  mov     rdx, rsi
0x180025ad8  mov     rcx, rdi
0x180025adb  call    BInitGdiInfo
0x180025ae0  test    eax, eax
0x180025ae2  jz      loc_180025A62
0x180025ae8  mov     r14d, [rsp+300h+var_2A0]
0x180025aed  mov     rdx, r13
0x180025af0  mov     r8d, r14d
0x180025af3  mov     rcx, rdi
0x180025af6  call    BInitDevInfo
0x180025afb  test    eax, eax
0x180025afd  jz      loc_180025A62
0x180025b03  mov     r8, rsi
0x180025b06  mov     rcx, rdi; struct _PDEV *
0x180025b09  call    VMInit
0x180025b0e  test    eax, eax
0x180025b10  jz      loc_180025A62
0x180025b16  mov     r8, rsi
0x180025b19  mov     rdx, r13
0x180025b1c  mov     rcx, rdi
0x180025b1f  call    RMInit
0x180025b24  test    eax, eax
0x180025b26  jz      loc_180025A62
0x180025b2c  mov     r8, rsi
0x180025b2f  mov     rdx, r13
0x180025b32  mov     rcx, rdi
0x180025b35  call    BInitPalDevInfo
0x180025b3a  test    eax, eax
0x180025b3c  jz      loc_180025A62
0x180025b42  mov     r8, rsi
0x180025b45  mov     rdx, r13
0x180025b48  mov     rcx, rdi
0x180025b4b  call    FMInit
0x180025b50  test    eax, eax
0x180025b52  jz      loc_180025A62
0x180025b58  mov     dword ptr [rbp+200h+var_280], 10000h
0x180025b5f  lea     rax, qword_180090000
0x180025b66  mov     qword ptr [rbp+200h+var_280+8], rax
0x180025b6a  mov     edx, 5Ch ; '\'; Ch
0x180025b6f  mov     dword ptr [rbp+200h+var_280+4], 28h ; '('
0x180025b76  mov     rax, [rdi+6B8h]
0x180025b7d  mov     rbx, [rax+28h]
0x180025b81  mov     rcx, rbx; Str
0x180025b84  call    cs:__imp_wcsrchr
0x180025b8a  test    rax, rax
0x180025b8d  lea     rcx, [rax+2]
0x180025b91  cmovz   rcx, rbx; String1
0x180025b95  test    rcx, rcx
0x180025b98  jz      short loc_180025BAE
0x180025b9a  lea     rdx, aPrintconfigDll; "PrintConfig.dll"
0x180025ba1  call    _wcsicmp
0x180025ba6  test    eax, eax
0x180025ba8  jz      loc_180025CE0
0x180025bae  mov     r10, [rdi+1058h]
0x180025bb5  mov     r12d, [rsp+300h+var_298]
0x180025bba  test    r10, r10
0x180025bbd  jz      short loc_180025BC9
0x180025bbf  cmp     [r10+70h], r15
0x180025bc3  jnz     loc_180025CF9
0x180025bc9  mov     rax, [rdi+1058h]
0x180025bd0  test    rax, rax
0x180025bd3  jnz     loc_180025D51
0x180025bd9  mov     rax, [rdi+758h]
0x180025be0  mov     r15d, [rax+8]
0x180025be4  lea     rbx, [rax+18h]
0x180025be8  test    r15d, r15d
0x180025beb  jz      loc_180025CC4
0x180025bf1  mov     rax, [rbx+20h]
0x180025bf5  test    rax, rax
0x180025bf8  jz      loc_180025CAE
0x180025bfe  mov     [rdi+20h], rax
0x180025c02  lea     r14, [rbx+28h]
0x180025c06  mov     rax, [r14]
0x180025c09  mov     [rdi+8], rax
0x180025c0d  mov     rax, [rbx+38h]
0x180025c11  mov     [rdi+30h], rax
0x180025c15  mov     rcx, [rbx+48h]
0x180025c19  test    rcx, rcx
0x180025c1c  jz      loc_180025DB4
0x180025c22  mov     rax, [rbx+50h]
0x180025c26  sub     rax, qword ptr cs:IID_IPrintOemUni.Data1
0x180025c2d  jnz     short loc_180025C3A
0x180025c2f  mov     rax, [rbx+58h]
0x180025c33  sub     rax, qword ptr cs:IID_IPrintOemUni.Data4
0x180025c3a  test    rax, rax
0x180025c3d  jnz     loc_180025D6D
0x180025c43  mov     rax, [rcx]
0x180025c46  lea     rdx, [rbp+200h+var_280]
0x180025c4a  mov     r8, [rsp+300h+var_288]
0x180025c4f  mov     r9d, r12d
0x180025c52  mov     [rsp+300h+var_2B0], r14
0x180025c57  mov     [rsp+300h+var_2B8], rdx
0x180025c5c  mov     edx, [rsp+300h+var_2A0]
0x180025c60  mov     rax, [rax+38h]
0x180025c64  mov     [rsp+300h+var_2C0], r13
0x180025c69  mov     dword ptr [rsp+300h+var_2C8], edx
0x180025c6d  mov     edx, [rsp+300h+var_29C]
0x180025c71  mov     [rsp+300h+var_2D0], rsi
0x180025c76  mov     dword ptr [rsp+300h+var_2D8], edx
0x180025c7a  mov     rdx, [rsp+300h+var_290]
0x180025c7f  mov     [rsp+300h+var_2E0], rdx
0x180025c84  mov     rdx, rdi
  ... truncated ...
```
