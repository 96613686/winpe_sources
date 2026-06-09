# LocalPrintConfigData::GetFileByRole(PrinterDriverRole,bool,bool)

- ea: `0x180159310`
- end: `0x1801598fe`
- name: `?GetFileByRole@LocalPrintConfigData@@UEAAPEBGW4PrinterDriverRole@@_N1@Z`
- size: `1518`
- prototype: `const wchar_t *__fastcall(__int64, signed int, __int64, char)`
- caller_count: `0`
- callee_count: `5`
- tags: `registry_config, loader_planting`

## callees

- `0x180003c64`
- `0x18000be68`
- `0x180159064`
- `0x180159310`
- `0x1801cb010`

## import_xrefs

- `WINSPOOL!GetPrinterDataW` at `0x180159435`
- `WINSPOOL!GetPrinterDataW` at `0x1801594ae`
- `WINSPOOL!GetPrinterDataW` at `0x1801597d2`
- `WINSPOOL!GetPrinterDataW` at `0x18015984e`
- `WINSPOOL!GetPrinterDataW` at `0x180159435`
- `WINSPOOL!GetPrinterDataW` at `0x1801594ae`
- `WINSPOOL!GetPrinterDataW` at `0x1801597d2`
- `WINSPOOL!GetPrinterDataW` at `0x18015984e`

## string_xrefs

- `0x18015963b`: `PCLXL.dll`
- `0x18015974a`: `PCL5ERES.dll`
- `0x1801598b8`: `PCL4RES.dll`
- `0x1801598af`: `PCL5URES.dll`
- `0x18015942a`: `PrintQueueV4DriverDirectory`
- `0x1801597bc`: `PrintQueueV4DriverDirectory`
- `0x18015947c`: `V4_Merged_ConfigFile_Name`
- `0x1801595d4`: `unires.dll`
- `0x1801595fb`: `unires.dll`

## pseudocode

```c
BYTE *__fastcall LocalPrintConfigData::GetFileByRole(__int64 a1, signed int a2, __int64 a3, char a4)
{
  char v6; // r12
  unsigned __int8 v7; // cl
  int v8; // eax
  LPBYTE v10; // rdi
  char v11; // si
  int v12; // edx
  int v13; // edx
  int v14; // edx
  __int64 v15; // rax
  __int64 v16; // rax
  __int64 v17; // rax
  void *v18; // rcx
  int v19; // eax
  __int64 v20; // rcx
  __int64 v21; // rax
  DWORD nSize; // r14d
  void *v23; // rcx
  signed int PrinterDataW; // eax
  bool v25; // sf
  __int64 v26; // rax
  int v27; // edx
  int v28; // edx
  int v29; // edx
  __int64 v30; // rax
  __int64 v31; // rax
  __int64 v32; // rax
  __int64 v33; // rax
  int v34; // edx
  int v35; // edx
  int v36; // edx
  int v37; // edx
  const unsigned __int16 *v38; // rdx
  wchar_t *v39; // rsi
  __int64 v40; // rcx
  const unsigned __int16 *v41; // rcx
  __int64 v42; // rcx
  __int64 v43; // rax
  __int64 v44; // rax
  __int64 v45; // rax
  __int64 v46; // rax
  __int64 v47; // rax
  int v48; // edx
  int v49; // edx
  int v50; // edx
  BYTE *v51; // rax
  void *v52; // rcx
  int v53; // eax
  __int64 v54; // rdx
  __int64 v55; // rcx
  __int64 v56; // rax
  int v57; // r14d
  void *v58; // rcx
  BYTE *v59; // r15
  signed int v60; // eax
  bool v61; // sf
  __int64 v62; // rax
  DWORD pType; // [rsp+30h] [rbp-18h] BYREF
  DWORD v64; // [rsp+34h] [rbp-14h] BYREF
  DWORD v65[2]; // [rsp+38h] [rbp-10h] BYREF
  DWORD pcbNeeded; // [rsp+98h] [rbp+50h] BYREF

  v6 = a3;
  v7 = 0;
  if ( (unsigned int)a2 > 0x15 || (v8 = 2146308, !_bittest(&v8, a2)) )
  {
    if ( (*(_BYTE *)(a1 + 120) & 8) != 0 )
    {
      if ( !(_BYTE)a3 )
        return 0;
    }
    else if ( (*(_BYTE *)(a1 + 120) & 0x10) != 0 )
    {
      v7 = a3;
    }
    else if ( (_BYTE)a3 )
    {
      return 0;
    }
  }
  v10 = 0;
  v11 = 0;
  if ( a2 <= 11 )
  {
    if ( a2 == 11 )
    {
      v10 = (LPBYTE)(**(__int64 (__fastcall ***)(__int64, const wchar_t *))a1)(a1, L"unires.dll");
      if ( v10 )
      {
        if ( !a4 )
          return (BYTE *)L"unires.dll";
        return v10;
      }
      goto LABEL_141;
    }
    if ( a2 > 5 )
    {
      v27 = a2 - 6;
      if ( v27 )
      {
        v28 = v27 - 1;
        if ( v28 )
        {
          v29 = v28 - 2;
          if ( v29 )
          {
            if ( v29 != 1 )
              goto LABEL_141;
            if ( v7 )
              v30 = *(_QWORD *)(a1 + 104);
            else
              v30 = *(_QWORD *)(a1 + 96);
            if ( v30 )
              v10 = *(LPBYTE *)(v30 + 80);
          }
          else
          {
            if ( v7 )
              v31 = *(_QWORD *)(a1 + 104);
            else
              v31 = *(_QWORD *)(a1 + 96);
            if ( v31 )
              v10 = *(LPBYTE *)(v31 + 72);
          }
        }
        else
        {
          if ( v7 )
            v32 = *(_QWORD *)(a1 + 104);
          else
            v32 = *(_QWORD *)(a1 + 96);
          if ( v32 )
            v10 = *(LPBYTE *)(v32 + 64);
        }
      }
      else
      {
        if ( v7 )
          v33 = *(_QWORD *)(a1 + 104);
        else
          v33 = *(_QWORD *)(a1 + 96);
        if ( v33 )
          v10 = *(LPBYTE *)(v33 + 56);
      }
    }
    else if ( a2 == 5 )
    {
      if ( v7 )
        v26 = *(_QWORD *)(a1 + 104);
      else
        v26 = *(_QWORD *)(a1 + 96);
      if ( v26 )
        v10 = *(LPBYTE *)(v26 + 40);
    }
    else
    {
      if ( !a2 )
      {
        if ( **(_DWORD **)(a1 + 8) >= 4u && v7 )
          v10 = *(LPBYTE *)(a1 + 64);
        else
          v10 = *(LPBYTE *)(a1 + 32);
        goto LABEL_141;
      }
      v12 = a2 - 1;
      if ( !v12 )
      {
        v10 = *(LPBYTE *)(32LL * v7 + a1 + 40);
        goto LABEL_141;
      }
      v13 = v12 - 1;
      if ( !v13 )
      {
        v17 = *(_QWORD *)(a1 + 8);
        if ( *(_DWORD *)v17 >= 4u )
        {
          v18 = *(void **)(a1 + 112);
          pcbNeeded = 0;
          pType = 0;
          if ( !GetPrinterDataW(
                  v18,
                  (LPWSTR)L"PrintQueueV4DriverDirectory",
                  &pType,
                  (LPBYTE)(a1 + 144),
                  0x208u,
                  &pcbNeeded) )
          {
            v19 = StringCchCatW((unsigned __int16 *)(a1 + 144), 260, L"\\");
            a3 = 0;
            if ( v19 >= 0 )
            {
              v20 = -1;
              do
                ++v20;
              while ( *(_WORD *)(a1 + 144 + 2 * v20) );
              v64 = 0;
              v21 = (unsigned int)v20 + 72LL;
              nSize = 2 * (260 - v20);
              v23 = *(void **)(a1 + 112);
              *(_QWORD *)v65 = a1 + 2 * v21;
              PrinterDataW = GetPrinterDataW(v23, (LPWSTR)L"V4_Merged_ConfigFile_Name", 0, *(LPBYTE *)v65, nSize, &v64);
              v25 = PrinterDataW < 0;
              if ( PrinterDataW > 0 )
                v25 = 1;
              if ( !v25 )
              {
                v10 = *(LPBYTE *)v65;
                *(_WORD *)(a1 + 662) = 0;
                if ( a4 )
                  return (BYTE *)(a1 + 144);
                return v10;
              }
            }
          }
        }
        else
        {
          v10 = *(LPBYTE *)(v17 + 32);
        }
        goto LABEL_141;
      }
      v14 = v13 - 1;
      if ( v14 )
      {
        if ( v14 != 1 )
        {
LABEL_141:
          if ( a4 && v11 )
          {
            if ( v10 )
            {
              LOBYTE(a3) = v6;
              return (BYTE *)(**(__int64 (__fastcall ***)(__int64, LPBYTE, __int64))a1)(a1, v10, a3);
            }
          }
          return v10;
        }
        if ( v7 )
          v15 = *(_QWORD *)(a1 + 104);
        else
          v15 = *(_QWORD *)(a1 + 96);
        if ( v15 )
          v10 = *(LPBYTE *)(v15 + 48);
      }
      else
      {
        if ( v7 )
          v16 = *(_QWORD *)(a1 + 104);
        else
          v16 = *(_QWORD *)(a1 + 96);
        if ( v16 )
          v10 = *(LPBYTE *)(v16 + 32);
      }
    }
LABEL_28:
    v11 = 1;
    goto LABEL_141;
  }
  if ( a2 > 17 )
  {
    v48 = a2 - 18;
    if ( !v48 )
    {
      v38 = L"PCL4RES.dll";
      goto LABEL_140;
    }
    v49 = v48 - 1;
    if ( !v49 )
    {
      v38 = L"PCL5URES.dll";
      goto LABEL_140;
    }
    v50 = v49 - 1;
    if ( !v50 )
    {
      if ( v7 )
        v62 = *(_QWORD *)(a1 + 104);
      else
        v62 = *(_QWORD *)(a1 + 96);
      if ( v62 )
        v10 = *(LPBYTE *)(v62 + 112);
      goto LABEL_28;
    }
    if ( v50 != 1 )
      goto LABEL_141;
    v51 = *(BYTE **)(a1 + 664);
    if ( !v51 )
    {
      v51 = (BYTE *)operator new(0x208u, (const struct std::nothrow_t *)&qword_18023A6C8);
      *(_QWORD *)(a1 + 664) = v51;
      if ( !v51 )
        goto LABEL_141;
    }
    v64 = 0;
    v52 = *(void **)(a1 + 112);
    v65[0] = 0;
    if ( GetPrinterDataW(v52, (LPWSTR)L"PrintQueueV4DriverDirectory", v65, v51, 0x208u, &v64) )
      goto LABEL_141;
    v53 = StringCchCatW(*(unsigned __int16 **)(a1 + 664), 260, L"\\");
    a3 = 0;
    if ( v53 < 0 )
      goto LABEL_141;
    v54 = *(_QWORD *)(a1 + 664);
    v55 = -1;
    do
      ++v55;
    while ( *(_WORD *)(v54 + 2 * v55) );
    v56 = (unsigned int)v55;
    v57 = 260 - v55;
    v58 = *(void **)(a1 + 112);
    pcbNeeded = 0;
    v59 = (BYTE *)(v54 + 2 * v56);
    v60 = GetPrinterDataW(v58, (LPWSTR)L"V4_PrintDeviceCapabilities", 0, v59, 2 * v57, &pcbNeeded);
    v61 = v60 < 0;
    if ( v60 > 0 )
      v61 = 1;
    if ( v61 )
      goto LABEL_141;
    *(_WORD *)(*(_QWORD *)(a1 + 664) + 518LL) = 0;
    if ( a4 )
      return *(BYTE **)(a1 + 664);
    else
      return v59;
  }
  if ( a2 == 17 )
  {
    v38 = L"PCL5ERES.dll";
    goto LABEL_140;
  }
  v34 = a2 - 12;
  if ( !v34 )
  {
    if ( v7 )
      v47 = *(_QWORD *)(a1 + 104);
    else
      v47 = *(_QWORD *)(a1 + 96);
    if ( v47 )
      v10 = *(LPBYTE *)(v47 + 88);
    goto LABEL_28;
  }
  v35 = v34 - 1;
  if ( !v35 )
  {
    if ( v7 )
      v46 = *(_QWORD *)(a1 + 104);
    else
      v46 = *(_QWORD *)(a1 + 96);
    if ( v46 )
      v10 = *(LPBYTE *)(v46 + 104);
    goto LABEL_28;
  }
  v36 = v35 - 1;
  if ( v36 )
  {
    v37 = v36 - 1;
    if ( v37 )
    {
      if ( v37 != 1 )
        goto LABEL_141;
      v38 = L"PCLXL.dll";
LABEL_140:
      v10 = (LPBYTE)(**(__int64 (__fastcall ***)(__int64, const unsigned __int16 *))a1)(a1, v38);
      goto LABEL_141;
    }
    if ( !a4 )
      return v10;
    v39 = (wchar_t *)(a1 + 1192);
    v40 = -1;
    do
      ++v40;
    while ( v39[v40] );
    if ( v40 )
      return (BYTE *)v39;
    v41 = (const unsigned __int16 *)(a1 + 2232);
  }
  else
  {
    if ( !a4 )
      return v10;
    v42 = -1;
    v39 = (wchar_t *)(a1 + 672);
    v43 = -1;
    do
      ++v43;
    while ( v39[v43] );
    if ( v43 )
      return (BYTE *)v39;
    v44 = *(_QWORD *)(a1 + 96);
    if ( v44 && *(_QWORD *)(v44 + 72) )
    {
      v41 = *(const unsigned __int16 **)(a1 + 128);
      if ( !v41 )
        return v10;
    }
    else
    {
      v45 = *(_QWORD *)(a1 + 104);
      if ( !v45 || !*(_QWORD *)(v45 + 72) )
        return v10;
      do
        ++v42;
      while ( *(_WORD *)(a1 + 2 * v42 + 1712) );
      if ( !v42 )
        return v10;
      v41 = (const unsigned __int16 *)(a1 + 1712);
    }
  }
  if ( (int)GetCatalogPathFromInfPath(v41, v39) >= 0 )
    return (BYTE *)v39;
  return v10;
}

```

## disassembly

```asm
0x180159310  push    rbp
0x180159312  push    rbx
0x180159313  push    rsi
0x180159314  push    rdi
0x180159315  push    r12
0x180159317  push    r13
0x180159319  push    r14
0x18015931b  push    r15
0x18015931d  mov     rbp, rsp
0x180159320  sub     rsp, 48h
0x180159324  xor     r14d, r14d
0x180159327  mov     rbx, rcx
0x18015932a  mov     r13b, r9b
0x18015932d  mov     r12b, r8b
0x180159330  mov     cl, r14b
0x180159333  cmp     edx, 15h
0x180159336  ja      short loc_180159342
0x180159338  mov     eax, 20C004h
0x18015933d  bt      eax, edx
0x180159340  jb      short loc_180159371
0x180159342  test    byte ptr [rbx+78h], 8
0x180159346  jz      short loc_180159361
0x180159348  test    r12b, r12b
0x18015934b  jnz     short loc_180159371
0x18015934d  xor     eax, eax
0x18015934f  add     rsp, 48h
0x180159353  pop     r15
0x180159355  pop     r14
0x180159357  pop     r13
0x180159359  pop     r12
0x18015935b  pop     rdi
0x18015935c  pop     rsi
0x18015935d  pop     rbx
0x18015935e  pop     rbp
0x18015935f  retn
0x180159361  test    byte ptr [rbx+78h], 10h
0x180159365  jz      short loc_18015936C
0x180159367  mov     cl, r12b
0x18015936a  jmp     short loc_180159371
0x18015936c  test    r12b, r12b
0x18015936f  jnz     short loc_18015934D
0x180159371  mov     rdi, r14
0x180159374  mov     sil, r14b
0x180159377  cmp     edx, 0Bh
0x18015937a  jg      loc_180159607
0x180159380  jz      loc_1801595D1
0x180159386  cmp     edx, 5
0x180159389  jg      loc_180159539
0x18015938f  jz      loc_180159519
0x180159395  test    edx, edx
0x180159397  jz      loc_1801594FA
0x18015939d  sub     edx, 1
0x1801593a0  jz      loc_1801594E9
0x1801593a6  sub     edx, 1
0x1801593a9  jz      short loc_1801593F1
0x1801593ab  sub     edx, 1
0x1801593ae  jz      short loc_1801593D2
0x1801593b0  cmp     edx, 1
0x1801593b3  jnz     loc_1801598D0
0x1801593b9  test    cl, cl
0x1801593bb  jnz     short loc_1801593C3
0x1801593bd  mov     rax, [rbx+60h]
0x1801593c1  jmp     short loc_1801593C7
0x1801593c3  mov     rax, [rbx+68h]
0x1801593c7  test    rax, rax
0x1801593ca  jz      short loc_1801593E9
0x1801593cc  mov     rdi, [rax+30h]
0x1801593d0  jmp     short loc_1801593E9
0x1801593d2  test    cl, cl
0x1801593d4  jnz     short loc_1801593DC
0x1801593d6  mov     rax, [rbx+60h]
0x1801593da  jmp     short loc_1801593E0
0x1801593dc  mov     rax, [rbx+68h]
0x1801593e0  test    rax, rax
0x1801593e3  jz      short loc_1801593E9
0x1801593e5  mov     rdi, [rax+20h]
0x1801593e9  mov     sil, 1
0x1801593ec  jmp     loc_1801598D0
0x1801593f1  mov     rax, [rbx+8]
0x1801593f5  cmp     dword ptr [rax], 4
0x1801593f8  jnb     short loc_180159403
0x1801593fa  mov     rdi, [rax+20h]
0x1801593fe  jmp     loc_1801598D0
0x180159403  mov     rcx, [rbx+70h]; hPrinter
0x180159407  lea     rax, [rbp+arg_8]
0x18015940b  mov     [rsp+48h+pcbNeeded], rax; pcbNeeded
0x180159410  lea     r15, [rbx+90h]
0x180159417  mov     r9, r15; pData
0x18015941a  mov     [rsp+48h+nSize], 208h; nSize
0x180159422  lea     r8, [rbp+pType]; pType
0x180159426  mov     [rbp+arg_8], r14d
0x18015942a  lea     rdx, aPrintqueuev4dr; "PrintQueueV4DriverDirectory"
0x180159431  mov     [rbp+pType], r14d
0x180159435  call    cs:__imp_GetPrinterDataW
0x18015943c  nop     dword ptr [rax+rax+00h]
0x180159441  test    eax, eax
0x180159443  jnz     loc_1801598D0
0x180159449  mov     r14d, 104h
0x18015944f  lea     r8, SubBlock; "\\"
0x180159456  mov     edx, r14d; unsigned __int64
0x180159459  mov     rcx, r15; unsigned __int16 *
0x18015945c  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180159461  xor     r8d, r8d; pType
0x180159464  test    eax, eax
0x180159466  js      loc_1801598D0
0x18015946c  or      rcx, 0FFFFFFFFFFFFFFFFh
0x180159470  inc     rcx
0x180159473  cmp     [r15+rcx*2], r8w
0x180159478  jnz     short loc_180159470
0x18015947a  mov     eax, ecx
0x18015947c  lea     rdx, aV4MergedConfig_0; "V4_Merged_ConfigFile_Name"
0x180159483  sub     r14d, ecx
0x180159486  mov     [rbp+var_14], r8d
0x18015948a  add     rax, 48h ; 'H'
0x18015948e  lea     rcx, [rbp+var_14]
0x180159492  mov     [rsp+48h+pcbNeeded], rcx; pcbNeeded
0x180159497  add     r14d, r14d
0x18015949a  mov     rcx, [rbx+70h]; hPrinter
0x18015949e  mov     [rsp+48h+nSize], r14d; nSize
0x1801594a3  lea     rax, [rbx+rax*2]
0x1801594a7  mov     r9, rax; pData
0x1801594aa  mov     qword ptr [rbp+var_10], rax
0x1801594ae  call    cs:__imp_GetPrinterDataW
0x1801594b5  nop     dword ptr [rax+rax+00h]
0x1801594ba  xor     r14d, r14d
0x1801594bd  test    eax, eax
0x1801594bf  jle     short loc_1801594CB
0x1801594c1  movzx   eax, ax
0x1801594c4  or      eax, 80070000h
0x1801594c9  test    eax, eax
0x1801594cb  js      loc_1801598D0
0x1801594d1  mov     rdi, qword ptr [rbp+var_10]
0x1801594d5  test    r13b, r13b
0x1801594d8  mov     [rbx+296h], r14w
0x1801594e0  cmovnz  rdi, r15
0x1801594e4  jmp     loc_1801598F6
0x1801594e9  movzx   eax, cl
0x1801594ec  shl     rax, 5
0x1801594f0  mov     rdi, [rax+rbx+28h]
0x1801594f5  jmp     loc_1801598D0
0x1801594fa  mov     rax, [rbx+8]
0x1801594fe  cmp     dword ptr [rax], 4
0x180159501  jb      short loc_180159510
0x180159503  test    cl, cl
0x180159505  jz      short loc_180159510
0x180159507  mov     rdi, [rbx+40h]
0x18015950b  jmp     loc_1801598D0
0x180159510  mov     rdi, [rbx+20h]
0x180159514  jmp     loc_1801598D0
0x180159519  test    cl, cl
0x18015951b  jnz     short loc_180159523
0x18015951d  mov     rax, [rbx+60h]
0x180159521  jmp     short loc_180159527
0x180159523  mov     rax, [rbx+68h]
0x180159527  test    rax, rax
0x18015952a  jz      loc_1801593E9
0x180159530  mov     rdi, [rax+28h]
0x180159534  jmp     loc_1801593E9
0x180159539  sub     edx, 6
0x18015953c  jz      short loc_1801595B1
0x18015953e  sub     edx, 1
0x180159541  jz      short loc_180159591
0x180159543  sub     edx, 2
0x180159546  jz      short loc_180159571
0x180159548  cmp     edx, 1
0x18015954b  jnz     loc_1801598D0
0x180159551  test    cl, cl
0x180159553  jnz     short loc_18015955B
0x180159555  mov     rax, [rbx+60h]
0x180159559  jmp     short loc_18015955F
0x18015955b  mov     rax, [rbx+68h]
0x18015955f  test    rax, rax
0x180159562  jz      loc_1801593E9
0x180159568  mov     rdi, [rax+50h]
0x18015956c  jmp     loc_1801593E9
0x180159571  test    cl, cl
0x180159573  jnz     short loc_18015957B
0x180159575  mov     rax, [rbx+60h]
0x180159579  jmp     short loc_18015957F
0x18015957b  mov     rax, [rbx+68h]
0x18015957f  test    rax, rax
0x180159582  jz      loc_1801593E9
0x180159588  mov     rdi, [rax+48h]
0x18015958c  jmp     loc_1801593E9
0x180159591  test    cl, cl
0x180159593  jnz     short loc_18015959B
0x180159595  mov     rax, [rbx+60h]
0x180159599  jmp     short loc_18015959F
0x18015959b  mov     rax, [rbx+68h]
0x18015959f  test    rax, rax
0x1801595a2  jz      loc_1801593E9
0x1801595a8  mov     rdi, [rax+40h]
0x1801595ac  jmp     loc_1801593E9
0x1801595b1  test    cl, cl
0x1801595b3  jnz     short loc_1801595BB
0x1801595b5  mov     rax, [rbx+60h]
0x1801595b9  jmp     short loc_1801595BF
0x1801595bb  mov     rax, [rbx+68h]
0x1801595bf  test    rax, rax
0x1801595c2  jz      loc_1801593E9
0x1801595c8  mov     rdi, [rax+38h]
0x1801595cc  jmp     loc_1801593E9
0x1801595d1  mov     rax, [rbx]
0x1801595d4  lea     rdx, aUniresDll; "unires.dll"
0x1801595db  mov     rcx, rbx
0x1801595de  mov     rax, [rax]
0x1801595e1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801595e6  mov     rdi, rax
0x1801595e9  test    rax, rax
0x1801595ec  jz      loc_1801598D0
0x1801595f2  test    r13b, r13b
0x1801595f5  jnz     loc_1801598F6
0x1801595fb  lea     rdi, aUniresDll; "unires.dll"
0x180159602  jmp     loc_1801598F6
0x180159607  cmp     edx, 11h
0x18015960a  jg      loc_180159756
0x180159610  jz      loc_18015974A
0x180159616  sub     edx, 0Ch
0x180159619  jz      loc_18015972A
0x18015961f  sub     edx, 1
0x180159622  jz      loc_18015970A
0x180159628  sub     edx, 1
0x18015962b  jz      short loc_180159689
0x18015962d  sub     edx, 1
0x180159630  jz      short loc_180159647
0x180159632  cmp     edx, 1
0x180159635  jnz     loc_1801598D0
0x18015963b  lea     rdx, aPclxlDll; "PCLXL.dll"
0x180159642  jmp     loc_1801598BF
0x180159647  test    r13b, r13b
0x18015964a  jz      loc_1801598F6
0x180159650  lea     rsi, [rbx+4A8h]
0x180159657  or      rcx, 0FFFFFFFFFFFFFFFFh
0x18015965b  inc     rcx
0x18015965e  cmp     [rsi+rcx*2], r14w
0x180159663  jnz     short loc_18015965B
0x180159665  test    rcx, rcx
0x180159668  jnz     short loc_180159681
0x18015966a  lea     rcx, [rbx+8B8h]; unsigned __int16 *
0x180159671  mov     rdx, rsi; Str
0x180159674  call    ?GetCatalogPathFromInfPath@@YAJPEBGPEAGK@Z; GetCatalogPathFromInfPath(ushort const *,ushort *,ulong)
0x180159679  test    eax, eax
0x18015967b  js      loc_1801598F6
0x180159681  mov     rdi, rsi
0x180159684  jmp     loc_1801598F6
0x180159689  test    r13b, r13b
0x18015968c  jz      loc_1801598F6
0x180159692  or      rcx, 0FFFFFFFFFFFFFFFFh
0x180159696  lea     rsi, [rbx+2A0h]
0x18015969d  mov     rax, rcx
0x1801596a0  inc     rax
0x1801596a3  cmp     [rsi+rax*2], r14w
0x1801596a8  jnz     short loc_1801596A0
0x1801596aa  test    rax, rax
0x1801596ad  jnz     short loc_180159681
0x1801596af  mov     rax, [rbx+60h]
0x1801596b3  test    rax, rax
0x1801596b6  jz      short loc_1801596D0
0x1801596b8  cmp     [rax+48h], r14
0x1801596bc  jz      short loc_1801596D0
0x1801596be  mov     rcx, [rbx+80h]
0x1801596c5  test    rcx, rcx
0x1801596c8  jz      loc_1801598F6
0x1801596ce  jmp     short loc_180159671
0x1801596d0  mov     rax, [rbx+68h]
0x1801596d4  test    rax, rax
0x1801596d7  jz      loc_1801598F6
0x1801596dd  cmp     [rax+48h], r14
0x1801596e1  jz      loc_1801598F6
0x1801596e7  inc     rcx
0x1801596ea  cmp     [rbx+rcx*2+6B0h], r14w
0x1801596f3  jnz     short loc_1801596E7
0x1801596f5  test    rcx, rcx
0x1801596f8  jz      loc_1801598F6
0x1801596fe  lea     rcx, [rbx+6B0h]
0x180159705  jmp     loc_180159671
0x18015970a  test    cl, cl
0x18015970c  jnz     short loc_180159714
0x18015970e  mov     rax, [rbx+60h]
0x180159712  jmp     short loc_180159718
0x180159714  mov     rax, [rbx+68h]
0x180159718  test    rax, rax
0x18015971b  jz      loc_1801593E9
0x180159721  mov     rdi, [rax+68h]
0x180159725  jmp     loc_1801593E9
0x18015972a  test    cl, cl
0x18015972c  jnz     short loc_180159734
0x18015972e  mov     rax, [rbx+60h]
0x180159732  jmp     short loc_180159738
0x180159734  mov     rax, [rbx+68h]
0x180159738  test    rax, rax
0x18015973b  jz      loc_1801593E9
0x180159741  mov     rdi, [rax+58h]
0x180159745  jmp     loc_1801593E9
0x18015974a  lea     rdx, aPcl5eresDll; "PCL5ERES.dll"
0x180159751  jmp     loc_1801598BF
0x180159756  sub     edx, 12h
0x180159759  jz      loc_1801598B8
0x18015975f  sub     edx, 1
0x180159762  jz      loc_1801598AF
  ... truncated ...
```
