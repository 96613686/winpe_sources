# DrvEnablePDEV

- ea: `0x180025dc0`
- end: `0x18002649d`
- name: `DrvEnablePDEV`
- size: `1757`
- prototype: `DHPDEV __stdcall(DEVMODEW *pdm, LPWSTR pwszLogAddress, ULONG cPat, HSURF *phsurfPatterns, ULONG cjCaps, ULONG *pdevcaps, ULONG cjDevInfo, DEVINFO *pdi, HDEV hdev, LPWSTR pwszDeviceName, HANDLE hDriver)`
- caller_count: `0`
- callee_count: `28`
- tags: `registry_config, loader_planting, installer_update, broker_com_uri`

## callees

- `0x18000414c`
- `0x1800246f0`
- `0x180024c24`
- `0x180024d0c`
- `0x180025248`
- `0x18002571c`
- `0x18002598c`
- `0x180025a1c`
- `0x180025c34`
- `0x180025cec`
- `0x180025dc0`
- `0x1800264a4`
- `0x18002681c`
- `0x180026bac`
- `0x180027788`
- `0x1800278e0`
- `0x180027a04`
- `0x180027c58`
- `0x18002806c`
- `0x1800280ec`
- `0x18003f860`
- `0x1800436cc`
- `0x180049d00`
- `0x18004a668`
- `0x18004a71c`
- `0x18004bd38`
- `0x18005039c`
- `0x180077010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!wcsrchr` at `0x180025fa7`
- `api-ms-win-crt-private-l1-1-0!wcsrchr` at `0x1800261d7`
- `api-ms-win-crt-private-l1-1-0!wcsrchr` at `0x180025fa7`
- `api-ms-win-crt-private-l1-1-0!wcsrchr` at `0x1800261d7`
- `KERNEL32!LocalAlloc` at `0x180026005`
- `KERNEL32!LocalAlloc` at `0x180026028`
- `KERNEL32!LocalAlloc` at `0x180026005`
- `KERNEL32!LocalAlloc` at `0x180026028`

## string_xrefs

- `0x180025fc3`: `PrintConfig.dll`
- `0x1800261f3`: `PrintConfig.dll`

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
  __int64 v13; // rdx
  _QWORD *v14; // rdi
  BYTE *PrinterDriver; // rax
  __int64 v16; // rdx
  __int64 v17; // r9
  HRESULT FilenameByRole; // r14d
  int v19; // r15d
  struct PrintConfigData *v20; // rbx
  _QWORD *v21; // rax
  __int64 v22; // rcx
  __int64 v23; // rax
  __int64 v24; // rcx
  __int64 v25; // rax
  const wchar_t *v26; // rbx
  wchar_t *v27; // rax
  const wchar_t *v28; // rcx
  HLOCAL v29; // rax
  HLOCAL v30; // rax
  __int64 v31; // rdx
  __int64 updated; // rax
  __int64 v33; // rcx
  __int64 v35; // rdx
  bool v36; // zf
  __int64 v37; // rdx
  __int64 v38; // rdx
  const wchar_t *v39; // rbx
  wchar_t *v40; // rax
  const wchar_t *v41; // rcx
  __int64 v42; // r10
  __int64 v43; // rax
  __int64 v44; // rax
  int v45; // r15d
  __int64 v46; // rbx
  __int64 v47; // rax
  _QWORD *v48; // r14
  __int64 v49; // rcx
  __int64 v50; // rax
  __int64 v51; // rbx
  __int64 v52; // rax
  __int64 v53; // rax
  __int64 (__fastcall *v54)(_QWORD *, LPWSTR, _QWORD, HSURF *, ULONG, ULONG *, ULONG, DEVINFO *, __int128 *); // rax
  int v55; // [rsp+28h] [rbp-D8h]
  __int64 v56; // [rsp+28h] [rbp-D8h]
  __int64 v57; // [rsp+38h] [rbp-C8h]
  __int128 v60; // [rsp+80h] [rbp-80h] BYREF
  struct PrintConfigData *v61; // [rsp+90h] [rbp-70h] BYREF
  struct _devicemodeW *v62; // [rsp+98h] [rbp-68h]
  __int128 v63; // [rsp+A0h] [rbp-60h] BYREF
  wchar_t pszSrc[264]; // [rsp+B0h] [rbp-50h] BYREF

  v62 = pdm;
  v63 = 0;
  v60 = 0;
  memset_0(pszSrc, 0, 0x208u);
  if ( cjCaps < 0x140 )
    return 0;
  memset_0(phsurfPatterns, 0, 8LL * cPat);
  v14 = PAllocPDEVData((__int64)hDriver);
  if ( !v14 )
    goto LABEL_29;
  PrinterDriver = MyGetPrinterDriver(hDriver, v13, 3u);
  v14[215] = PrinterDriver;
  if ( !PrinterDriver )
    goto LABEL_29;
  v61 = 0;
  FilenameByRole = CreatePrintConfigData(hDriver, &v61);
  v19 = 1;
  if ( FilenameByRole >= 0 )
  {
    v20 = v61;
    FilenameByRole = CommonGetFilenameByRole((__int64)v61, v16, pszSrc, v17);
    if ( v20 )
      (*(void (__fastcall **)(struct PrintConfigData *, __int64))(*(_QWORD *)v20 + 32LL))(v20, 1);
  }
  if ( FilenameByRole < 0 )
    goto LABEL_29;
  v21 = GPDLoadRawBinaryData(pszSrc);
  v14[251] = v21;
  if ( !v21 )
    goto LABEL_29;
  v23 = PGetDefaultDriverInfo(v22, (__int64)v21);
  v14[250] = v23;
  if ( !v23 )
    goto LABEL_29;
  v24 = *(_QWORD *)(v23 + 104);
  v14[252] = v24;
  if ( !v24 )
    goto LABEL_29;
  v25 = *(_DWORD *)(v24 + 56) ? v24 + *(unsigned int *)(v24 + 56) : 0LL;
  v14[253] = v25;
  if ( !v25
    || !(unsigned int)BGetPrinterProperties((HANDLE)v14[3], (_DWORD *)v14[251], (_DWORD *)v14 + 508)
    || !(unsigned int)BLoadAndInitOemPlugins((__int64)v14) )
  {
    goto LABEL_29;
  }
  v26 = *(const wchar_t **)(v14[215] + 40LL);
  v27 = wcsrchr(v26, 0x5Cu);
  v28 = v27 + 1;
  if ( !v27 )
    v28 = v26;
  if ( !v28 || wcsicmp(v28, L"PrintConfig.dll") )
    v19 = 0;
  if ( !(unsigned int)BInitWinResData(v14 + 16, (__int64)hDriver, v14[253], v19) )
    goto LABEL_29;
  v29 = LocalAlloc(0x40u, 0x200u);
  v14[324] = v29;
  if ( !v29 )
    goto LABEL_29;
  v30 = LocalAlloc(0x40u, 0x1000u);
  v14[514] = v30;
  if ( !v30 || !(unsigned int)BMergeAndValidateDevmode((__int64)v14, v62, (__int64)&v63) )
    goto LABEL_29;
  updated = PGetUpdateDriverInfo((__int64)v14, v31, v14[252], v14[324], v14[251], v55, v14[497], (__int64)(v14 + 254));
  v14[250] = updated;
  if ( !updated )
  {
    v14[252] = 0;
    goto LABEL_29;
  }
  v33 = *(_QWORD *)(updated + 104);
  v14[252] = v33;
  if ( !v33 )
  {
LABEL_29:
    VFreePDEVData(v14);
    return 0;
  }
  if ( !*(_DWORD *)(v33 + 56) )
  {
    v14[253] = 0;
    goto LABEL_29;
  }
  v35 = *(unsigned int *)(v33 + 56);
  v36 = v33 + v35 == 0;
  v37 = v33 + v35;
  v14[253] = v37;
  if ( v36 )
    goto LABEL_29;
  *((_DWORD *)v14 + 468) |= 0xAu;
  v14[211] = v37;
  v14[2] = hdev;
  *((_DWORD *)v14 + 30) = 239103;
  if ( !(unsigned int)BInitPDEV((__int64)v14, (int *)&v63)
    || !(unsigned int)BInitGdiInfo((__int64)v14, pdevcaps)
    || !(unsigned int)BInitDevInfo((__int64)v14, pdi, cjDevInfo)
    || !(unsigned int)VMInit((struct _PDEV *)v14, v38, (__int64)pdevcaps)
    || !(unsigned int)RMInit((__int64)v14, (__int64)pdi, (__int64)pdevcaps)
    || !(unsigned int)BInitPalDevInfo((__int64)v14, (__int64)pdi, (__int64)pdevcaps)
    || !(unsigned int)FMInit((__int64)v14, (__int64)pdi, (__int64)pdevcaps) )
  {
    goto LABEL_29;
  }
  *(_QWORD *)&v60 = 0x2800010000LL;
  *((_QWORD *)&v60 + 1) = &qword_180092000;
  v39 = *(const wchar_t **)(v14[215] + 40LL);
  v40 = wcsrchr(v39, 0x5Cu);
  v41 = v40 + 1;
  if ( !v40 )
    v41 = v39;
  if ( v41 && !wcsicmp(v41, L"PrintConfig.dll") )
  {
    *((_DWORD *)v14 + 29) |= 0x100u;
    GetPrinterDriverIDAsString(hDriver, (wchar_t *)v14 + 2172);
  }
  v42 = v14[523];
  if ( v42 && *(_QWORD *)(v42 + 112) )
  {
    v51 = v14[1];
    v14[1] = v14[522];
    v14[522] = (*(__int64 (__fastcall **)(_QWORD *, LPWSTR, _QWORD, HSURF *, ULONG, ULONG *, ULONG, DEVINFO *, __int128 *))(v42 + 112))(
                 v14,
                 pwszDeviceName,
                 cPat,
                 phsurfPatterns,
                 cjCaps,
                 pdevcaps,
                 cjDevInfo,
                 pdi,
                 &v60);
    v14[1] = v51;
  }
  v43 = v14[523];
  if ( v43 )
  {
    if ( *(_QWORD *)(v43 + 112) && !v14[522] )
      goto LABEL_29;
  }
  v44 = v14[235];
  v45 = *(_DWORD *)(v44 + 8);
  v46 = v44 + 24;
  while ( v45 )
  {
    v47 = *(_QWORD *)(v46 + 32);
    if ( !v47 )
      goto LABEL_59;
    v14[4] = v47;
    v48 = (_QWORD *)(v46 + 40);
    v14[1] = *(_QWORD *)(v46 + 40);
    v14[6] = *(_QWORD *)(v46 + 56);
    v49 = *(_QWORD *)(v46 + 72);
    if ( v49 )
    {
      v50 = *(_QWORD *)(v46 + 80) - *(_QWORD *)&IID_IPrintOemUni.Data1;
      if ( !v50 )
        v50 = *(_QWORD *)(v46 + 88) - *(_QWORD *)IID_IPrintOemUni.Data4;
      if ( !v50 )
        goto LABEL_82;
      v52 = *(_QWORD *)(v46 + 80) - *(_QWORD *)&IID_IPrintOemUni2.Data1;
      if ( !v52 )
        v52 = *(_QWORD *)(v46 + 88) - *(_QWORD *)IID_IPrintOemUni2.Data4;
      if ( !v52 )
        goto LABEL_82;
      v53 = *(_QWORD *)(v46 + 80) - *(_QWORD *)&IID_IPrintOemUni3.Data1;
      if ( !v53 )
        v53 = *(_QWORD *)(v46 + 88) - *(_QWORD *)IID_IPrintOemUni3.Data4;
      if ( !v53 )
      {
LABEL_82:
        LODWORD(v57) = cjDevInfo;
        LODWORD(v56) = cjCaps;
        if ( (*(unsigned int (__fastcall **)(__int64, _QWORD *, LPWSTR, _QWORD, HSURF *, __int64, ULONG *, __int64, DEVINFO *, __int128 *, __int64))(*(_QWORD *)v49 + 56LL))(
               v49,
               v14,
               pwszDeviceName,
               cPat,
               phsurfPatterns,
               v56,
               pdevcaps,
               v57,
               pdi,
               &v60,
               v46 + 40) == -2147467263 )
          goto LABEL_59;
      }
    }
    else
    {
      if ( (*(_BYTE *)(v46 + 100) & 0x10) != 0 )
        v54 = *(__int64 (__fastcall **)(_QWORD *, LPWSTR, _QWORD, HSURF *, ULONG, ULONG *, ULONG, DEVINFO *, __int128 *))(v46 + 136);
      else
        v54 = (__int64 (__fastcall *)(_QWORD *, LPWSTR, _QWORD, HSURF *, ULONG, ULONG *, ULONG, DEVINFO *, __int128 *))PGetOemEntrypointAddress(v46, 4u);
      if ( !v54 )
        goto LABEL_59;
      *v48 = v54(v14, pwszDeviceName, cPat, phsurfPatterns, cjCaps, pdevcaps, cjDevInfo, pdi, &v60);
    }
    if ( !*v48 )
      goto LABEL_29;
    if ( pdevcaps[60] == 4 && (pdevcaps[61] & 0xFF000000) != 0 && (pdevcaps[61] & 8) != 0 )
      VInitPal8BPPMaskMode((__int64)v14, (__int64)pdevcaps);
    *(_DWORD *)(v46 + 48) |= 2u;
LABEL_59:
    --v45;
    v46 += 176;
  }
  VUnloadFreeBinaryData(v14);
  return (DHPDEV)v14;
}

```

## disassembly

```asm
0x180025dc0  mov     [rsp-8+arg_8], rbx
0x180025dc5  push    rbp
0x180025dc6  push    rsi
0x180025dc7  push    rdi
0x180025dc8  push    r12
0x180025dca  push    r13
0x180025dcc  push    r14
0x180025dce  push    r15
0x180025dd0  lea     rbp, [rsp-1D0h]
0x180025dd8  sub     rsp, 2D0h
0x180025ddf  mov     rax, cs:__security_cookie
0x180025de6  xor     rax, rsp
0x180025de9  mov     [rbp+200h+var_40], rax
0x180025df0  mov     eax, [rbp+200h+cjDevInfo]
0x180025df6  xorps   xmm0, xmm0
0x180025df9  mov     r14d, [rbp+200h+cjCaps]
0x180025e00  xorps   xmm1, xmm1
0x180025e03  mov     rsi, [rbp+200h+pdevcaps]
0x180025e0a  xor     edx, edx; Val
0x180025e0c  mov     r13, [rbp+200h+pdi]
0x180025e13  mov     rdi, r9
0x180025e16  mov     r12, [rbp+200h+hDriver]
0x180025e1d  mov     ebx, r8d
0x180025e20  mov     r8d, 208h; Size
0x180025e26  mov     [rsp+300h+var_2A0], eax
0x180025e2a  mov     rax, [rbp+200h+pwszDeviceName]
0x180025e31  mov     [rbp+200h+var_268], rcx
0x180025e35  lea     rcx, [rbp+200h+pszSrc]; void *
0x180025e39  mov     [rsp+300h+var_288], rax
0x180025e3e  mov     [rsp+300h+var_290], r9
0x180025e43  mov     [rsp+300h+var_298], ebx
0x180025e47  mov     [rsp+300h+var_29C], r14d
0x180025e4c  movups  [rbp+200h+var_260], xmm0
0x180025e50  movups  [rbp+200h+var_280], xmm1
0x180025e54  call    memset_0
0x180025e59  cmp     r14d, 140h
0x180025e60  jb      loc_1800260BC
0x180025e66  mov     r8d, ebx
0x180025e69  xor     edx, edx; Val
0x180025e6b  shl     r8, 3; Size
0x180025e6f  mov     rcx, rdi; void *
0x180025e72  call    memset_0
0x180025e77  mov     rcx, r12
0x180025e7a  call    PAllocPDEVData
0x180025e7f  mov     rdi, rax
0x180025e82  test    rax, rax
0x180025e85  jz      loc_1800260B4
0x180025e8b  mov     r8d, 3
0x180025e91  mov     rcx, r12; hPrinter
0x180025e94  call    MyGetPrinterDriver
0x180025e99  mov     [rdi+6B8h], rax
0x180025ea0  test    rax, rax
0x180025ea3  jz      loc_1800260B4
0x180025ea9  lea     rdx, [rbp+200h+var_270]; struct PrintConfigData **
0x180025ead  mov     [rbp+200h+var_270], 0
0x180025eb5  mov     rcx, r12; void *
0x180025eb8  call    ?CreatePrintConfigData@@YAJPEAXPEAPEAVPrintConfigData@@@Z; CreatePrintConfigData(void *,PrintConfigData * *)
0x180025ebd  mov     r14d, eax
0x180025ec0  mov     r15d, 1
0x180025ec6  test    eax, eax
0x180025ec8  js      short loc_180025EF4
0x180025eca  mov     rbx, [rbp+200h+var_270]
0x180025ece  lea     r8, [rbp+200h+pszSrc]
0x180025ed2  mov     rcx, rbx
0x180025ed5  call    ?CommonGetFilenameByRole@@YAJPEAVPrintConfigData@@W4PrinterDriverRole@@PEAGK@Z; CommonGetFilenameByRole(PrintConfigData *,PrinterDriverRole,ushort *,ulong)
0x180025eda  mov     r14d, eax
0x180025edd  test    rbx, rbx
0x180025ee0  jz      short loc_180025EF4
0x180025ee2  mov     rax, [rbx]
0x180025ee5  mov     edx, r15d
0x180025ee8  mov     rcx, rbx
0x180025eeb  mov     rax, [rax+20h]
0x180025eef  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180025ef4  test    r14d, r14d
0x180025ef7  js      loc_1800260B4
0x180025efd  lea     rcx, [rbp+200h+pszSrc]; pszSrc
0x180025f01  call    GPDLoadRawBinaryData
0x180025f06  mov     [rdi+7D8h], rax
0x180025f0d  test    rax, rax
0x180025f10  jz      loc_1800260B4
0x180025f16  mov     rdx, rax
0x180025f19  call    PGetDefaultDriverInfo
0x180025f1e  mov     [rdi+7D0h], rax
0x180025f25  test    rax, rax
0x180025f28  jz      loc_1800260B4
0x180025f2e  mov     rcx, [rax+68h]
0x180025f32  mov     [rdi+7E0h], rcx
0x180025f39  test    rcx, rcx
0x180025f3c  jz      loc_1800260B4
0x180025f42  cmp     dword ptr [rcx+38h], 0
0x180025f46  jz      loc_180026316
0x180025f4c  mov     eax, [rcx+38h]
0x180025f4f  add     rax, rcx
0x180025f52  mov     [rdi+7E8h], rax
0x180025f59  test    rax, rax
0x180025f5c  jz      loc_1800260B4
0x180025f62  mov     rdx, [rdi+7D8h]
0x180025f69  lea     r14, [rdi+7F0h]
0x180025f70  mov     rcx, [rdi+18h]; hPrinter
0x180025f74  mov     r8, r14
0x180025f77  call    BGetPrinterProperties
0x180025f7c  test    eax, eax
0x180025f7e  jz      loc_1800260B4
0x180025f84  mov     rcx, rdi
0x180025f87  call    BLoadAndInitOemPlugins
0x180025f8c  test    eax, eax
0x180025f8e  jz      loc_1800260B4
0x180025f94  mov     rax, [rdi+6B8h]
0x180025f9b  mov     edx, 5Ch ; '\'; Ch
0x180025fa0  mov     rbx, [rax+28h]
0x180025fa4  mov     rcx, rbx; Str
0x180025fa7  call    cs:__imp_wcsrchr
0x180025fae  nop     dword ptr [rax+rax+00h]
0x180025fb3  test    rax, rax
0x180025fb6  lea     rcx, [rax+2]
0x180025fba  cmovz   rcx, rbx; String1
0x180025fbe  test    rcx, rcx
0x180025fc1  jz      short loc_180025FD3
0x180025fc3  lea     rdx, aPrintconfigDll; "PrintConfig.dll"
0x180025fca  call    _wcsicmp
0x180025fcf  test    eax, eax
0x180025fd1  jz      short loc_180025FD6
0x180025fd3  xor     r15d, r15d
0x180025fd6  mov     r8, [rdi+7E8h]
0x180025fdd  lea     rcx, [rdi+80h]
0x180025fe4  mov     r9d, r15d
0x180025fe7  mov     rdx, r12
0x180025fea  call    BInitWinResData
0x180025fef  xor     r15d, r15d
0x180025ff2  test    eax, eax
0x180025ff4  jz      loc_1800260B4
0x180025ffa  lea     ebx, [r15+40h]
0x180025ffe  mov     edx, 200h; uBytes
0x180026003  mov     ecx, ebx; uFlags
0x180026005  call    cs:__imp_LocalAlloc
0x18002600c  nop     dword ptr [rax+rax+00h]
0x180026011  mov     [rdi+0A20h], rax
0x180026018  test    rax, rax
0x18002601b  jz      loc_1800260B4
0x180026021  mov     edx, 1000h; uBytes
0x180026026  mov     ecx, ebx; uFlags
0x180026028  call    cs:__imp_LocalAlloc
0x18002602f  nop     dword ptr [rax+rax+00h]
0x180026034  mov     [rdi+1010h], rax
0x18002603b  test    rax, rax
0x18002603e  jz      short loc_1800260B4
0x180026040  mov     rdx, [rbp+200h+var_268]
0x180026044  lea     r8, [rbp+200h+var_260]
0x180026048  mov     rcx, rdi
0x18002604b  call    BMergeAndValidateDevmode
0x180026050  test    eax, eax
0x180026052  jz      short loc_1800260B4
0x180026054  mov     rax, [rdi+0F88h]
0x18002605b  mov     rcx, rdi
0x18002605e  mov     r9, [rdi+0A20h]
0x180026065  mov     r8, [rdi+7E0h]
0x18002606c  mov     [rsp+300h+var_2C8], r14
0x180026071  mov     [rsp+300h+var_2D0], rax
0x180026076  mov     rax, [rdi+7D8h]
0x18002607d  mov     [rsp+300h+var_2E0], rax
0x180026082  call    PGetUpdateDriverInfo
0x180026087  mov     [rdi+7D0h], rax
0x18002608e  test    rax, rax
0x180026091  jz      loc_18002632D
0x180026097  mov     rcx, [rax+68h]
0x18002609b  mov     [rdi+7E0h], rcx
0x1800260a2  test    rcx, rcx
0x1800260a5  jz      short loc_1800260B4
0x1800260a7  cmp     [rcx+38h], r15d
0x1800260ab  jnz     short loc_1800260E9
0x1800260ad  mov     [rdi+7E8h], r15
0x1800260b4  mov     rcx, rdi; hMem
0x1800260b7  call    VFreePDEVData
0x1800260bc  xor     eax, eax
0x1800260be  mov     rcx, [rbp+200h+var_40]
0x1800260c5  xor     rcx, rsp; StackCookie
0x1800260c8  call    __security_check_cookie
0x1800260cd  mov     rbx, [rsp+300h+arg_8]
0x1800260d5  add     rsp, 2D0h
0x1800260dc  pop     r15
0x1800260de  pop     r14
0x1800260e0  pop     r13
0x1800260e2  pop     r12
0x1800260e4  pop     rdi
0x1800260e5  pop     rsi
0x1800260e6  pop     rbp
0x1800260e7  retn
0x1800260e9  mov     edx, [rcx+38h]
0x1800260ec  add     rdx, rcx
0x1800260ef  mov     [rdi+7E8h], rdx
0x1800260f6  jz      short loc_1800260B4
0x1800260f8  mov     rax, [rbp+200h+hdev]
0x1800260ff  mov     rcx, rdi
0x180026102  or      dword ptr [rdi+750h], 0Ah
0x180026109  mov     [rdi+698h], rdx
0x180026110  lea     rdx, [rbp+200h+var_260]
0x180026114  mov     [rdi+10h], rax
0x180026118  mov     dword ptr [rdi+78h], 3A5FFh
0x18002611f  call    BInitPDEV
0x180026124  test    eax, eax
0x180026126  jz      short loc_1800260B4
0x180026128  mov     rdx, rsi
0x18002612b  mov     rcx, rdi
0x18002612e  call    BInitGdiInfo
0x180026133  test    eax, eax
0x180026135  jz      loc_1800260B4
0x18002613b  mov     r14d, [rsp+300h+var_2A0]
0x180026140  mov     rdx, r13
0x180026143  mov     r8d, r14d
0x180026146  mov     rcx, rdi
0x180026149  call    BInitDevInfo
0x18002614e  test    eax, eax
0x180026150  jz      loc_1800260B4
0x180026156  mov     r8, rsi
0x180026159  mov     rcx, rdi; struct _PDEV *
0x18002615c  call    VMInit
0x180026161  test    eax, eax
0x180026163  jz      loc_1800260B4
0x180026169  mov     r8, rsi
0x18002616c  mov     rdx, r13
0x18002616f  mov     rcx, rdi
0x180026172  call    RMInit
0x180026177  test    eax, eax
0x180026179  jz      loc_1800260B4
0x18002617f  mov     r8, rsi
0x180026182  mov     rdx, r13
0x180026185  mov     rcx, rdi
0x180026188  call    BInitPalDevInfo
0x18002618d  test    eax, eax
0x18002618f  jz      loc_1800260B4
0x180026195  mov     r8, rsi
0x180026198  mov     rdx, r13
0x18002619b  mov     rcx, rdi
0x18002619e  call    FMInit
0x1800261a3  test    eax, eax
0x1800261a5  jz      loc_1800260B4
0x1800261ab  mov     dword ptr [rbp+200h+var_280], 10000h
0x1800261b2  lea     rax, qword_180092000
0x1800261b9  mov     qword ptr [rbp+200h+var_280+8], rax
0x1800261bd  mov     edx, 5Ch ; '\'; Ch
0x1800261c2  mov     dword ptr [rbp+200h+var_280+4], 28h ; '('
0x1800261c9  mov     rax, [rdi+6B8h]
0x1800261d0  mov     rbx, [rax+28h]
0x1800261d4  mov     rcx, rbx; Str
0x1800261d7  call    cs:__imp_wcsrchr
0x1800261de  nop     dword ptr [rax+rax+00h]
0x1800261e3  test    rax, rax
0x1800261e6  lea     rcx, [rax+2]
0x1800261ea  cmovz   rcx, rbx; String1
0x1800261ee  test    rcx, rcx
0x1800261f1  jz      short loc_180026207
0x1800261f3  lea     rdx, aPrintconfigDll; "PrintConfig.dll"
0x1800261fa  call    _wcsicmp
0x1800261ff  test    eax, eax
0x180026201  jz      loc_180026339
0x180026207  mov     r10, [rdi+1058h]
0x18002620e  mov     r12d, [rsp+300h+var_298]
0x180026213  test    r10, r10
0x180026216  jz      short loc_180026222
0x180026218  cmp     [r10+70h], r15
0x18002621c  jnz     loc_180026352
0x180026222  mov     rax, [rdi+1058h]
0x180026229  test    rax, rax
0x18002622c  jnz     loc_1800263AA
0x180026232  mov     rax, [rdi+758h]
0x180026239  mov     r15d, [rax+8]
0x18002623d  lea     rbx, [rax+18h]
0x180026241  test    r15d, r15d
0x180026244  jz      loc_18002631D
0x18002624a  mov     rax, [rbx+20h]
0x18002624e  test    rax, rax
0x180026251  jz      loc_180026307
0x180026257  mov     [rdi+20h], rax
0x18002625b  lea     r14, [rbx+28h]
0x18002625f  mov     rax, [r14]
0x180026262  mov     [rdi+8], rax
0x180026266  mov     rax, [rbx+38h]
0x18002626a  mov     [rdi+30h], rax
0x18002626e  mov     rcx, [rbx+48h]
0x180026272  test    rcx, rcx
0x180026275  jz      loc_18002640D
0x18002627b  mov     rax, [rbx+50h]
0x18002627f  sub     rax, qword ptr cs:IID_IPrintOemUni.Data1
0x180026286  jnz     short loc_180026293
0x180026288  mov     rax, [rbx+58h]
0x18002628c  sub     rax, qword ptr cs:IID_IPrintOemUni.Data4
0x180026293  test    rax, rax
0x180026296  jnz     loc_1800263C6
0x18002629c  mov     rax, [rcx]
0x18002629f  lea     rdx, [rbp+200h+var_280]
0x1800262a3  mov     r8, [rsp+300h+var_288]
0x1800262a8  mov     r9d, r12d
0x1800262ab  mov     [rsp+300h+var_2B0], r14
0x1800262b0  mov     [rsp+300h+var_2B8], rdx
0x1800262b5  mov     edx, [rsp+300h+var_2A0]
0x1800262b9  mov     rax, [rax+38h]
0x1800262bd  mov     [rsp+300h+var_2C0], r13
0x1800262c2  mov     dword ptr [rsp+300h+var_2C8], edx
0x1800262c6  mov     edx, [rsp+300h+var_29C]
0x1800262ca  mov     [rsp+300h+var_2D0], rsi
  ... truncated ...
```
