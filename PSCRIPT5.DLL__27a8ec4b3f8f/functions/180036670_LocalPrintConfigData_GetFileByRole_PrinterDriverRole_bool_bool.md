# LocalPrintConfigData::GetFileByRole(PrinterDriverRole,bool,bool)

- ea: `0x180036670`
- end: `0x180036c5e`
- name: `?GetFileByRole@LocalPrintConfigData@@UEAAPEBGW4PrinterDriverRole@@_N1@Z`
- size: `1518`
- prototype: `const wchar_t *__fastcall(__int64, signed int, __int64, char)`
- caller_count: `0`
- callee_count: `5`
- tags: `registry_config, loader_planting`

## callees

- `0x1800029ec`
- `0x180020acc`
- `0x18003638c`
- `0x180036670`
- `0x18005f010`

## import_xrefs

- `WINSPOOL!GetPrinterDataW` at `0x180036795`
- `WINSPOOL!GetPrinterDataW` at `0x18003680e`
- `WINSPOOL!GetPrinterDataW` at `0x180036b32`
- `WINSPOOL!GetPrinterDataW` at `0x180036bae`
- `WINSPOOL!GetPrinterDataW` at `0x180036795`
- `WINSPOOL!GetPrinterDataW` at `0x18003680e`
- `WINSPOOL!GetPrinterDataW` at `0x180036b32`
- `WINSPOOL!GetPrinterDataW` at `0x180036bae`

## string_xrefs

- `0x180036934`: `unires.dll`
- `0x18003695b`: `unires.dll`
- `0x1800367dc`: `V4_Merged_ConfigFile_Name`
- `0x18003678a`: `PrintQueueV4DriverDirectory`
- `0x180036b1c`: `PrintQueueV4DriverDirectory`
- `0x18003699b`: `PCLXL.dll`
- `0x180036aaa`: `PCL5ERES.dll`
- `0x180036c18`: `PCL4RES.dll`
- `0x180036c0f`: `PCL5URES.dll`

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
  HRESULT v19; // eax
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
  const wchar_t *v38; // rdx
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
  HRESULT v53; // eax
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
            v19 = StringCchCatW((STRSAFE_LPWSTR)(a1 + 144), 0x104u, L"\\");
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
      v51 = (BYTE *)operator new(0x208u, (const struct std::nothrow_t *)byte_18006E400);
      *(_QWORD *)(a1 + 664) = v51;
      if ( !v51 )
        goto LABEL_141;
    }
    v64 = 0;
    v52 = *(void **)(a1 + 112);
    v65[0] = 0;
    if ( GetPrinterDataW(v52, (LPWSTR)L"PrintQueueV4DriverDirectory", v65, v51, 0x208u, &v64) )
      goto LABEL_141;
    v53 = StringCchCatW(*(STRSAFE_LPWSTR *)(a1 + 664), 0x104u, L"\\");
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
      v10 = (LPBYTE)(**(__int64 (__fastcall ***)(__int64, const wchar_t *))a1)(a1, v38);
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
0x180036670  push    rbp
0x180036672  push    rbx
0x180036673  push    rsi
0x180036674  push    rdi
0x180036675  push    r12
0x180036677  push    r13
0x180036679  push    r14
0x18003667b  push    r15
0x18003667d  mov     rbp, rsp
0x180036680  sub     rsp, 48h
0x180036684  xor     r14d, r14d
0x180036687  mov     rbx, rcx
0x18003668a  mov     r13b, r9b
0x18003668d  mov     r12b, r8b
0x180036690  mov     cl, r14b
0x180036693  cmp     edx, 15h
0x180036696  ja      short loc_1800366A2
0x180036698  mov     eax, 20C004h
0x18003669d  bt      eax, edx
0x1800366a0  jb      short loc_1800366D1
0x1800366a2  test    byte ptr [rbx+78h], 8
0x1800366a6  jz      short loc_1800366C1
0x1800366a8  test    r12b, r12b
0x1800366ab  jnz     short loc_1800366D1
0x1800366ad  xor     eax, eax
0x1800366af  add     rsp, 48h
0x1800366b3  pop     r15
0x1800366b5  pop     r14
0x1800366b7  pop     r13
0x1800366b9  pop     r12
0x1800366bb  pop     rdi
0x1800366bc  pop     rsi
0x1800366bd  pop     rbx
0x1800366be  pop     rbp
0x1800366bf  retn
0x1800366c1  test    byte ptr [rbx+78h], 10h
0x1800366c5  jz      short loc_1800366CC
0x1800366c7  mov     cl, r12b
0x1800366ca  jmp     short loc_1800366D1
0x1800366cc  test    r12b, r12b
0x1800366cf  jnz     short loc_1800366AD
0x1800366d1  mov     rdi, r14
0x1800366d4  mov     sil, r14b
0x1800366d7  cmp     edx, 0Bh
0x1800366da  jg      loc_180036967
0x1800366e0  jz      loc_180036931
0x1800366e6  cmp     edx, 5
0x1800366e9  jg      loc_180036899
0x1800366ef  jz      loc_180036879
0x1800366f5  test    edx, edx
0x1800366f7  jz      loc_18003685A
0x1800366fd  sub     edx, 1
0x180036700  jz      loc_180036849
0x180036706  sub     edx, 1
0x180036709  jz      short loc_180036751
0x18003670b  sub     edx, 1
0x18003670e  jz      short loc_180036732
0x180036710  cmp     edx, 1
0x180036713  jnz     loc_180036C30
0x180036719  test    cl, cl
0x18003671b  jnz     short loc_180036723
0x18003671d  mov     rax, [rbx+60h]
0x180036721  jmp     short loc_180036727
0x180036723  mov     rax, [rbx+68h]
0x180036727  test    rax, rax
0x18003672a  jz      short loc_180036749
0x18003672c  mov     rdi, [rax+30h]
0x180036730  jmp     short loc_180036749
0x180036732  test    cl, cl
0x180036734  jnz     short loc_18003673C
0x180036736  mov     rax, [rbx+60h]
0x18003673a  jmp     short loc_180036740
0x18003673c  mov     rax, [rbx+68h]
0x180036740  test    rax, rax
0x180036743  jz      short loc_180036749
0x180036745  mov     rdi, [rax+20h]
0x180036749  mov     sil, 1
0x18003674c  jmp     loc_180036C30
0x180036751  mov     rax, [rbx+8]
0x180036755  cmp     dword ptr [rax], 4
0x180036758  jnb     short loc_180036763
0x18003675a  mov     rdi, [rax+20h]
0x18003675e  jmp     loc_180036C30
0x180036763  mov     rcx, [rbx+70h]; hPrinter
0x180036767  lea     rax, [rbp+arg_8]
0x18003676b  mov     [rsp+48h+pcbNeeded], rax; pcbNeeded
0x180036770  lea     r15, [rbx+90h]
0x180036777  mov     r9, r15; pData
0x18003677a  mov     [rsp+48h+nSize], 208h; nSize
0x180036782  lea     r8, [rbp+pType]; pType
0x180036786  mov     [rbp+arg_8], r14d
0x18003678a  lea     rdx, aPrintqueuev4dr; "PrintQueueV4DriverDirectory"
0x180036791  mov     [rbp+pType], r14d
0x180036795  call    cs:__imp_GetPrinterDataW
0x18003679c  nop     dword ptr [rax+rax+00h]
0x1800367a1  test    eax, eax
0x1800367a3  jnz     loc_180036C30
0x1800367a9  mov     r14d, 104h
0x1800367af  lea     r8, SubBlock; "\\"
0x1800367b6  mov     edx, r14d; cchDest
0x1800367b9  mov     rcx, r15; pszDest
0x1800367bc  call    StringCchCatW
0x1800367c1  xor     r8d, r8d; pType
0x1800367c4  test    eax, eax
0x1800367c6  js      loc_180036C30
0x1800367cc  or      rcx, 0FFFFFFFFFFFFFFFFh
0x1800367d0  inc     rcx
0x1800367d3  cmp     [r15+rcx*2], r8w
0x1800367d8  jnz     short loc_1800367D0
0x1800367da  mov     eax, ecx
0x1800367dc  lea     rdx, aV4MergedConfig; "V4_Merged_ConfigFile_Name"
0x1800367e3  sub     r14d, ecx
0x1800367e6  mov     [rbp+var_14], r8d
0x1800367ea  add     rax, 48h ; 'H'
0x1800367ee  lea     rcx, [rbp+var_14]
0x1800367f2  mov     [rsp+48h+pcbNeeded], rcx; pcbNeeded
0x1800367f7  add     r14d, r14d
0x1800367fa  mov     rcx, [rbx+70h]; hPrinter
0x1800367fe  mov     [rsp+48h+nSize], r14d; nSize
0x180036803  lea     rax, [rbx+rax*2]
0x180036807  mov     r9, rax; pData
0x18003680a  mov     qword ptr [rbp+var_10], rax
0x18003680e  call    cs:__imp_GetPrinterDataW
0x180036815  nop     dword ptr [rax+rax+00h]
0x18003681a  xor     r14d, r14d
0x18003681d  test    eax, eax
0x18003681f  jle     short loc_18003682B
0x180036821  movzx   eax, ax
0x180036824  or      eax, 80070000h
0x180036829  test    eax, eax
0x18003682b  js      loc_180036C30
0x180036831  mov     rdi, qword ptr [rbp+var_10]
0x180036835  test    r13b, r13b
0x180036838  mov     [rbx+296h], r14w
0x180036840  cmovnz  rdi, r15
0x180036844  jmp     loc_180036C56
0x180036849  movzx   eax, cl
0x18003684c  shl     rax, 5
0x180036850  mov     rdi, [rax+rbx+28h]
0x180036855  jmp     loc_180036C30
0x18003685a  mov     rax, [rbx+8]
0x18003685e  cmp     dword ptr [rax], 4
0x180036861  jb      short loc_180036870
0x180036863  test    cl, cl
0x180036865  jz      short loc_180036870
0x180036867  mov     rdi, [rbx+40h]
0x18003686b  jmp     loc_180036C30
0x180036870  mov     rdi, [rbx+20h]
0x180036874  jmp     loc_180036C30
0x180036879  test    cl, cl
0x18003687b  jnz     short loc_180036883
0x18003687d  mov     rax, [rbx+60h]
0x180036881  jmp     short loc_180036887
0x180036883  mov     rax, [rbx+68h]
0x180036887  test    rax, rax
0x18003688a  jz      loc_180036749
0x180036890  mov     rdi, [rax+28h]
0x180036894  jmp     loc_180036749
0x180036899  sub     edx, 6
0x18003689c  jz      short loc_180036911
0x18003689e  sub     edx, 1
0x1800368a1  jz      short loc_1800368F1
0x1800368a3  sub     edx, 2
0x1800368a6  jz      short loc_1800368D1
0x1800368a8  cmp     edx, 1
0x1800368ab  jnz     loc_180036C30
0x1800368b1  test    cl, cl
0x1800368b3  jnz     short loc_1800368BB
0x1800368b5  mov     rax, [rbx+60h]
0x1800368b9  jmp     short loc_1800368BF
0x1800368bb  mov     rax, [rbx+68h]
0x1800368bf  test    rax, rax
0x1800368c2  jz      loc_180036749
0x1800368c8  mov     rdi, [rax+50h]
0x1800368cc  jmp     loc_180036749
0x1800368d1  test    cl, cl
0x1800368d3  jnz     short loc_1800368DB
0x1800368d5  mov     rax, [rbx+60h]
0x1800368d9  jmp     short loc_1800368DF
0x1800368db  mov     rax, [rbx+68h]
0x1800368df  test    rax, rax
0x1800368e2  jz      loc_180036749
0x1800368e8  mov     rdi, [rax+48h]
0x1800368ec  jmp     loc_180036749
0x1800368f1  test    cl, cl
0x1800368f3  jnz     short loc_1800368FB
0x1800368f5  mov     rax, [rbx+60h]
0x1800368f9  jmp     short loc_1800368FF
0x1800368fb  mov     rax, [rbx+68h]
0x1800368ff  test    rax, rax
0x180036902  jz      loc_180036749
0x180036908  mov     rdi, [rax+40h]
0x18003690c  jmp     loc_180036749
0x180036911  test    cl, cl
0x180036913  jnz     short loc_18003691B
0x180036915  mov     rax, [rbx+60h]
0x180036919  jmp     short loc_18003691F
0x18003691b  mov     rax, [rbx+68h]
0x18003691f  test    rax, rax
0x180036922  jz      loc_180036749
0x180036928  mov     rdi, [rax+38h]
0x18003692c  jmp     loc_180036749
0x180036931  mov     rax, [rbx]
0x180036934  lea     rdx, aUniresDll; "unires.dll"
0x18003693b  mov     rcx, rbx
0x18003693e  mov     rax, [rax]
0x180036941  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180036946  mov     rdi, rax
0x180036949  test    rax, rax
0x18003694c  jz      loc_180036C30
0x180036952  test    r13b, r13b
0x180036955  jnz     loc_180036C56
0x18003695b  lea     rdi, aUniresDll; "unires.dll"
0x180036962  jmp     loc_180036C56
0x180036967  cmp     edx, 11h
0x18003696a  jg      loc_180036AB6
0x180036970  jz      loc_180036AAA
0x180036976  sub     edx, 0Ch
0x180036979  jz      loc_180036A8A
0x18003697f  sub     edx, 1
0x180036982  jz      loc_180036A6A
0x180036988  sub     edx, 1
0x18003698b  jz      short loc_1800369E9
0x18003698d  sub     edx, 1
0x180036990  jz      short loc_1800369A7
0x180036992  cmp     edx, 1
0x180036995  jnz     loc_180036C30
0x18003699b  lea     rdx, aPclxlDll; "PCLXL.dll"
0x1800369a2  jmp     loc_180036C1F
0x1800369a7  test    r13b, r13b
0x1800369aa  jz      loc_180036C56
0x1800369b0  lea     rsi, [rbx+4A8h]
0x1800369b7  or      rcx, 0FFFFFFFFFFFFFFFFh
0x1800369bb  inc     rcx
0x1800369be  cmp     [rsi+rcx*2], r14w
0x1800369c3  jnz     short loc_1800369BB
0x1800369c5  test    rcx, rcx
0x1800369c8  jnz     short loc_1800369E1
0x1800369ca  lea     rcx, [rbx+8B8h]; unsigned __int16 *
0x1800369d1  mov     rdx, rsi; Str
0x1800369d4  call    ?GetCatalogPathFromInfPath@@YAJPEBGPEAGK@Z; GetCatalogPathFromInfPath(ushort const *,ushort *,ulong)
0x1800369d9  test    eax, eax
0x1800369db  js      loc_180036C56
0x1800369e1  mov     rdi, rsi
0x1800369e4  jmp     loc_180036C56
0x1800369e9  test    r13b, r13b
0x1800369ec  jz      loc_180036C56
0x1800369f2  or      rcx, 0FFFFFFFFFFFFFFFFh
0x1800369f6  lea     rsi, [rbx+2A0h]
0x1800369fd  mov     rax, rcx
0x180036a00  inc     rax
0x180036a03  cmp     [rsi+rax*2], r14w
0x180036a08  jnz     short loc_180036A00
0x180036a0a  test    rax, rax
0x180036a0d  jnz     short loc_1800369E1
0x180036a0f  mov     rax, [rbx+60h]
0x180036a13  test    rax, rax
0x180036a16  jz      short loc_180036A30
0x180036a18  cmp     [rax+48h], r14
0x180036a1c  jz      short loc_180036A30
0x180036a1e  mov     rcx, [rbx+80h]
0x180036a25  test    rcx, rcx
0x180036a28  jz      loc_180036C56
0x180036a2e  jmp     short loc_1800369D1
0x180036a30  mov     rax, [rbx+68h]
0x180036a34  test    rax, rax
0x180036a37  jz      loc_180036C56
0x180036a3d  cmp     [rax+48h], r14
0x180036a41  jz      loc_180036C56
0x180036a47  inc     rcx
0x180036a4a  cmp     [rbx+rcx*2+6B0h], r14w
0x180036a53  jnz     short loc_180036A47
0x180036a55  test    rcx, rcx
0x180036a58  jz      loc_180036C56
0x180036a5e  lea     rcx, [rbx+6B0h]
0x180036a65  jmp     loc_1800369D1
0x180036a6a  test    cl, cl
0x180036a6c  jnz     short loc_180036A74
0x180036a6e  mov     rax, [rbx+60h]
0x180036a72  jmp     short loc_180036A78
0x180036a74  mov     rax, [rbx+68h]
0x180036a78  test    rax, rax
0x180036a7b  jz      loc_180036749
0x180036a81  mov     rdi, [rax+68h]
0x180036a85  jmp     loc_180036749
0x180036a8a  test    cl, cl
0x180036a8c  jnz     short loc_180036A94
0x180036a8e  mov     rax, [rbx+60h]
0x180036a92  jmp     short loc_180036A98
0x180036a94  mov     rax, [rbx+68h]
0x180036a98  test    rax, rax
0x180036a9b  jz      loc_180036749
0x180036aa1  mov     rdi, [rax+58h]
0x180036aa5  jmp     loc_180036749
0x180036aaa  lea     rdx, aPcl5eresDll; "PCL5ERES.dll"
0x180036ab1  jmp     loc_180036C1F
0x180036ab6  sub     edx, 12h
0x180036ab9  jz      loc_180036C18
0x180036abf  sub     edx, 1
0x180036ac2  jz      loc_180036C0F
  ... truncated ...
```
