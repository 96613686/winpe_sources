# LocalPrintConfigData::GetFileByRole(PrinterDriverRole,bool,bool)

- ea: `0x18003fab0`
- end: `0x180040085`
- name: `?GetFileByRole@LocalPrintConfigData@@UEAAPEBGW4PrinterDriverRole@@_N1@Z`
- size: `1493`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `registry_config, loader_planting`

## callees

- `0x180033504`
- `0x18003fab0`
- `0x1800491e8`
- `0x1800522b4`
- `0x180075010`

## import_xrefs

- `WINSPOOL!GetPrinterDataW` at `0x18003fbd4`
- `WINSPOOL!GetPrinterDataW` at `0x18003fc47`
- `WINSPOOL!GetPrinterDataW` at `0x18003ff65`
- `WINSPOOL!GetPrinterDataW` at `0x18003ffdb`
- `WINSPOOL!GetPrinterDataW` at `0x18003fbd4`
- `WINSPOOL!GetPrinterDataW` at `0x18003fc47`
- `WINSPOOL!GetPrinterDataW` at `0x18003ff65`
- `WINSPOOL!GetPrinterDataW` at `0x18003ffdb`

## string_xrefs

- `0x18003fc15`: `V4_Merged_ConfigFile_Name`
- `0x18003fbc9`: `PrintQueueV4DriverDirectory`
- `0x18003ff4f`: `PrintQueueV4DriverDirectory`
- `0x18003fd67`: `unires.dll`
- `0x18003fd8e`: `unires.dll`
- `0x18003fdce`: `PCLXL.dll`
- `0x18003fedd`: `PCL5ERES.dll`
- `0x18004003f`: `PCL4RES.dll`
- `0x180040036`: `PCL5URES.dll`

## pseudocode

```c
const wchar_t *__fastcall LocalPrintConfigData::GetFileByRole(__int64 a1, signed int a2, __int64 a3, char a4)
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
          return L"unires.dll";
        return (const wchar_t *)v10;
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
                  return (const wchar_t *)(a1 + 144);
                return (const wchar_t *)v10;
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
              return (const wchar_t *)(**(__int64 (__fastcall ***)(__int64, LPBYTE, __int64))a1)(a1, v10, a3);
            }
          }
          return (const wchar_t *)v10;
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
      v51 = (BYTE *)operator new(0x208u, (const struct std::nothrow_t *)byte_18007F401);
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
      return *(const wchar_t **)(a1 + 664);
    else
      return (const wchar_t *)v59;
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
      return (const wchar_t *)v10;
    v39 = (wchar_t *)(a1 + 1192);
    v40 = -1;
    do
      ++v40;
    while ( v39[v40] );
    if ( v40 )
      return v39;
    v41 = (const unsigned __int16 *)(a1 + 2232);
  }
  else
  {
    if ( !a4 )
      return (const wchar_t *)v10;
    v42 = -1;
    v39 = (wchar_t *)(a1 + 672);
    v43 = -1;
    do
      ++v43;
    while ( v39[v43] );
    if ( v43 )
      return v39;
    v44 = *(_QWORD *)(a1 + 96);
    if ( v44 && *(_QWORD *)(v44 + 72) )
    {
      v41 = *(const unsigned __int16 **)(a1 + 128);
      if ( !v41 )
        return (const wchar_t *)v10;
    }
    else
    {
      v45 = *(_QWORD *)(a1 + 104);
      if ( !v45 || !*(_QWORD *)(v45 + 72) )
        return (const wchar_t *)v10;
      do
        ++v42;
      while ( *(_WORD *)(a1 + 2 * v42 + 1712) );
      if ( !v42 )
        return (const wchar_t *)v10;
      v41 = (const unsigned __int16 *)(a1 + 1712);
    }
  }
  if ( (int)GetCatalogPathFromInfPath(v41, v39, a3) >= 0 )
    return v39;
  return (const wchar_t *)v10;
}

```

## disassembly

```asm
0x18003fab0  push    rbp
0x18003fab2  push    rbx
0x18003fab3  push    rsi
0x18003fab4  push    rdi
0x18003fab5  push    r12
0x18003fab7  push    r13
0x18003fab9  push    r14
0x18003fabb  push    r15
0x18003fabd  mov     rbp, rsp
0x18003fac0  sub     rsp, 48h
0x18003fac4  xor     r14d, r14d
0x18003fac7  mov     rbx, rcx
0x18003faca  mov     r13b, r9b
0x18003facd  mov     r12b, r8b
0x18003fad0  mov     cl, r14b
0x18003fad3  cmp     edx, 15h
0x18003fad6  ja      short loc_18003FAE2
0x18003fad8  mov     eax, 20C004h
0x18003fadd  bt      eax, edx
0x18003fae0  jb      short loc_18003FB10
0x18003fae2  test    byte ptr [rbx+78h], 8
0x18003fae6  jz      short loc_18003FB00
0x18003fae8  test    r12b, r12b
0x18003faeb  jnz     short loc_18003FB10
0x18003faed  xor     eax, eax
0x18003faef  add     rsp, 48h
0x18003faf3  pop     r15
0x18003faf5  pop     r14
0x18003faf7  pop     r13
0x18003faf9  pop     r12
0x18003fafb  pop     rdi
0x18003fafc  pop     rsi
0x18003fafd  pop     rbx
0x18003fafe  pop     rbp
0x18003faff  retn
0x18003fb00  test    byte ptr [rbx+78h], 10h
0x18003fb04  jz      short loc_18003FB0B
0x18003fb06  mov     cl, r12b
0x18003fb09  jmp     short loc_18003FB10
0x18003fb0b  test    r12b, r12b
0x18003fb0e  jnz     short loc_18003FAED
0x18003fb10  mov     rdi, r14
0x18003fb13  mov     sil, r14b
0x18003fb16  cmp     edx, 0Bh
0x18003fb19  jg      loc_18003FD9A
0x18003fb1f  jz      loc_18003FD64
0x18003fb25  cmp     edx, 5
0x18003fb28  jg      loc_18003FCCC
0x18003fb2e  jz      loc_18003FCAC
0x18003fb34  test    edx, edx
0x18003fb36  jz      loc_18003FC8D
0x18003fb3c  sub     edx, 1
0x18003fb3f  jz      loc_18003FC7C
0x18003fb45  sub     edx, 1
0x18003fb48  jz      short loc_18003FB90
0x18003fb4a  sub     edx, 1
0x18003fb4d  jz      short loc_18003FB71
0x18003fb4f  cmp     edx, 1
0x18003fb52  jnz     loc_180040057
0x18003fb58  test    cl, cl
0x18003fb5a  jnz     short loc_18003FB62
0x18003fb5c  mov     rax, [rbx+60h]
0x18003fb60  jmp     short loc_18003FB66
0x18003fb62  mov     rax, [rbx+68h]
0x18003fb66  test    rax, rax
0x18003fb69  jz      short loc_18003FB88
0x18003fb6b  mov     rdi, [rax+30h]
0x18003fb6f  jmp     short loc_18003FB88
0x18003fb71  test    cl, cl
0x18003fb73  jnz     short loc_18003FB7B
0x18003fb75  mov     rax, [rbx+60h]
0x18003fb79  jmp     short loc_18003FB7F
0x18003fb7b  mov     rax, [rbx+68h]
0x18003fb7f  test    rax, rax
0x18003fb82  jz      short loc_18003FB88
0x18003fb84  mov     rdi, [rax+20h]
0x18003fb88  mov     sil, 1
0x18003fb8b  jmp     loc_180040057
0x18003fb90  mov     rax, [rbx+8]
0x18003fb94  cmp     dword ptr [rax], 4
0x18003fb97  jnb     short loc_18003FBA2
0x18003fb99  mov     rdi, [rax+20h]
0x18003fb9d  jmp     loc_180040057
0x18003fba2  mov     rcx, [rbx+70h]; hPrinter
0x18003fba6  lea     rax, [rbp+arg_8]
0x18003fbaa  mov     [rsp+48h+pcbNeeded], rax; pcbNeeded
0x18003fbaf  lea     r15, [rbx+90h]
0x18003fbb6  mov     r9, r15; pData
0x18003fbb9  mov     [rsp+48h+nSize], 208h; nSize
0x18003fbc1  lea     r8, [rbp+pType]; pType
0x18003fbc5  mov     [rbp+arg_8], r14d
0x18003fbc9  lea     rdx, aPrintqueuev4dr; "PrintQueueV4DriverDirectory"
0x18003fbd0  mov     [rbp+pType], r14d
0x18003fbd4  call    cs:__imp_GetPrinterDataW
0x18003fbda  test    eax, eax
0x18003fbdc  jnz     loc_180040057
0x18003fbe2  mov     r14d, 104h
0x18003fbe8  lea     r8, asc_180080C28; "\\"
0x18003fbef  mov     edx, r14d; cchDest
0x18003fbf2  mov     rcx, r15; pszDest
0x18003fbf5  call    StringCchCatW
0x18003fbfa  xor     r8d, r8d; pType
0x18003fbfd  test    eax, eax
0x18003fbff  js      loc_180040057
0x18003fc05  or      rcx, 0FFFFFFFFFFFFFFFFh
0x18003fc09  inc     rcx
0x18003fc0c  cmp     [r15+rcx*2], r8w
0x18003fc11  jnz     short loc_18003FC09
0x18003fc13  mov     eax, ecx
0x18003fc15  lea     rdx, aV4MergedConfig; "V4_Merged_ConfigFile_Name"
0x18003fc1c  sub     r14d, ecx
0x18003fc1f  mov     [rbp+var_14], r8d
0x18003fc23  add     rax, 48h ; 'H'
0x18003fc27  lea     rcx, [rbp+var_14]
0x18003fc2b  mov     [rsp+48h+pcbNeeded], rcx; pcbNeeded
0x18003fc30  add     r14d, r14d
0x18003fc33  mov     rcx, [rbx+70h]; hPrinter
0x18003fc37  mov     [rsp+48h+nSize], r14d; nSize
0x18003fc3c  lea     rax, [rbx+rax*2]
0x18003fc40  mov     r9, rax; pData
0x18003fc43  mov     qword ptr [rbp+var_10], rax
0x18003fc47  call    cs:__imp_GetPrinterDataW
0x18003fc4d  xor     r14d, r14d
0x18003fc50  test    eax, eax
0x18003fc52  jle     short loc_18003FC5E
0x18003fc54  movzx   eax, ax
0x18003fc57  or      eax, 80070000h
0x18003fc5c  test    eax, eax
0x18003fc5e  js      loc_180040057
0x18003fc64  mov     rdi, qword ptr [rbp+var_10]
0x18003fc68  test    r13b, r13b
0x18003fc6b  mov     [rbx+296h], r14w
0x18003fc73  cmovnz  rdi, r15
0x18003fc77  jmp     loc_18004007D
0x18003fc7c  movzx   eax, cl
0x18003fc7f  shl     rax, 5
0x18003fc83  mov     rdi, [rax+rbx+28h]
0x18003fc88  jmp     loc_180040057
0x18003fc8d  mov     rax, [rbx+8]
0x18003fc91  cmp     dword ptr [rax], 4
0x18003fc94  jb      short loc_18003FCA3
0x18003fc96  test    cl, cl
0x18003fc98  jz      short loc_18003FCA3
0x18003fc9a  mov     rdi, [rbx+40h]
0x18003fc9e  jmp     loc_180040057
0x18003fca3  mov     rdi, [rbx+20h]
0x18003fca7  jmp     loc_180040057
0x18003fcac  test    cl, cl
0x18003fcae  jnz     short loc_18003FCB6
0x18003fcb0  mov     rax, [rbx+60h]
0x18003fcb4  jmp     short loc_18003FCBA
0x18003fcb6  mov     rax, [rbx+68h]
0x18003fcba  test    rax, rax
0x18003fcbd  jz      loc_18003FB88
0x18003fcc3  mov     rdi, [rax+28h]
0x18003fcc7  jmp     loc_18003FB88
0x18003fccc  sub     edx, 6
0x18003fccf  jz      short loc_18003FD44
0x18003fcd1  sub     edx, 1
0x18003fcd4  jz      short loc_18003FD24
0x18003fcd6  sub     edx, 2
0x18003fcd9  jz      short loc_18003FD04
0x18003fcdb  cmp     edx, 1
0x18003fcde  jnz     loc_180040057
0x18003fce4  test    cl, cl
0x18003fce6  jnz     short loc_18003FCEE
0x18003fce8  mov     rax, [rbx+60h]
0x18003fcec  jmp     short loc_18003FCF2
0x18003fcee  mov     rax, [rbx+68h]
0x18003fcf2  test    rax, rax
0x18003fcf5  jz      loc_18003FB88
0x18003fcfb  mov     rdi, [rax+50h]
0x18003fcff  jmp     loc_18003FB88
0x18003fd04  test    cl, cl
0x18003fd06  jnz     short loc_18003FD0E
0x18003fd08  mov     rax, [rbx+60h]
0x18003fd0c  jmp     short loc_18003FD12
0x18003fd0e  mov     rax, [rbx+68h]
0x18003fd12  test    rax, rax
0x18003fd15  jz      loc_18003FB88
0x18003fd1b  mov     rdi, [rax+48h]
0x18003fd1f  jmp     loc_18003FB88
0x18003fd24  test    cl, cl
0x18003fd26  jnz     short loc_18003FD2E
0x18003fd28  mov     rax, [rbx+60h]
0x18003fd2c  jmp     short loc_18003FD32
0x18003fd2e  mov     rax, [rbx+68h]
0x18003fd32  test    rax, rax
0x18003fd35  jz      loc_18003FB88
0x18003fd3b  mov     rdi, [rax+40h]
0x18003fd3f  jmp     loc_18003FB88
0x18003fd44  test    cl, cl
0x18003fd46  jnz     short loc_18003FD4E
0x18003fd48  mov     rax, [rbx+60h]
0x18003fd4c  jmp     short loc_18003FD52
0x18003fd4e  mov     rax, [rbx+68h]
0x18003fd52  test    rax, rax
0x18003fd55  jz      loc_18003FB88
0x18003fd5b  mov     rdi, [rax+38h]
0x18003fd5f  jmp     loc_18003FB88
0x18003fd64  mov     rax, [rbx]
0x18003fd67  lea     rdx, aUniresDll; "unires.dll"
0x18003fd6e  mov     rcx, rbx
0x18003fd71  mov     rax, [rax]
0x18003fd74  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003fd79  mov     rdi, rax
0x18003fd7c  test    rax, rax
0x18003fd7f  jz      loc_180040057
0x18003fd85  test    r13b, r13b
0x18003fd88  jnz     loc_18004007D
0x18003fd8e  lea     rdi, aUniresDll; "unires.dll"
0x18003fd95  jmp     loc_18004007D
0x18003fd9a  cmp     edx, 11h
0x18003fd9d  jg      loc_18003FEE9
0x18003fda3  jz      loc_18003FEDD
0x18003fda9  sub     edx, 0Ch
0x18003fdac  jz      loc_18003FEBD
0x18003fdb2  sub     edx, 1
0x18003fdb5  jz      loc_18003FE9D
0x18003fdbb  sub     edx, 1
0x18003fdbe  jz      short loc_18003FE1C
0x18003fdc0  sub     edx, 1
0x18003fdc3  jz      short loc_18003FDDA
0x18003fdc5  cmp     edx, 1
0x18003fdc8  jnz     loc_180040057
0x18003fdce  lea     rdx, aPclxlDll; "PCLXL.dll"
0x18003fdd5  jmp     loc_180040046
0x18003fdda  test    r13b, r13b
0x18003fddd  jz      loc_18004007D
0x18003fde3  lea     rsi, [rbx+4A8h]
0x18003fdea  or      rcx, 0FFFFFFFFFFFFFFFFh
0x18003fdee  inc     rcx
0x18003fdf1  cmp     [rsi+rcx*2], r14w
0x18003fdf6  jnz     short loc_18003FDEE
0x18003fdf8  test    rcx, rcx
0x18003fdfb  jnz     short loc_18003FE14
0x18003fdfd  lea     rcx, [rbx+8B8h]; unsigned __int16 *
0x18003fe04  mov     rdx, rsi; Str
0x18003fe07  call    ?GetCatalogPathFromInfPath@@YAJPEBGPEAGK@Z; GetCatalogPathFromInfPath(ushort const *,ushort *,ulong)
0x18003fe0c  test    eax, eax
0x18003fe0e  js      loc_18004007D
0x18003fe14  mov     rdi, rsi
0x18003fe17  jmp     loc_18004007D
0x18003fe1c  test    r13b, r13b
0x18003fe1f  jz      loc_18004007D
0x18003fe25  or      rcx, 0FFFFFFFFFFFFFFFFh
0x18003fe29  lea     rsi, [rbx+2A0h]
0x18003fe30  mov     rax, rcx
0x18003fe33  inc     rax
0x18003fe36  cmp     [rsi+rax*2], r14w
0x18003fe3b  jnz     short loc_18003FE33
0x18003fe3d  test    rax, rax
0x18003fe40  jnz     short loc_18003FE14
0x18003fe42  mov     rax, [rbx+60h]
0x18003fe46  test    rax, rax
0x18003fe49  jz      short loc_18003FE63
0x18003fe4b  cmp     [rax+48h], r14
0x18003fe4f  jz      short loc_18003FE63
0x18003fe51  mov     rcx, [rbx+80h]
0x18003fe58  test    rcx, rcx
0x18003fe5b  jz      loc_18004007D
0x18003fe61  jmp     short loc_18003FE04
0x18003fe63  mov     rax, [rbx+68h]
0x18003fe67  test    rax, rax
0x18003fe6a  jz      loc_18004007D
0x18003fe70  cmp     [rax+48h], r14
0x18003fe74  jz      loc_18004007D
0x18003fe7a  inc     rcx
0x18003fe7d  cmp     [rbx+rcx*2+6B0h], r14w
0x18003fe86  jnz     short loc_18003FE7A
0x18003fe88  test    rcx, rcx
0x18003fe8b  jz      loc_18004007D
0x18003fe91  lea     rcx, [rbx+6B0h]
0x18003fe98  jmp     loc_18003FE04
0x18003fe9d  test    cl, cl
0x18003fe9f  jnz     short loc_18003FEA7
0x18003fea1  mov     rax, [rbx+60h]
0x18003fea5  jmp     short loc_18003FEAB
0x18003fea7  mov     rax, [rbx+68h]
0x18003feab  test    rax, rax
0x18003feae  jz      loc_18003FB88
0x18003feb4  mov     rdi, [rax+68h]
0x18003feb8  jmp     loc_18003FB88
0x18003febd  test    cl, cl
0x18003febf  jnz     short loc_18003FEC7
0x18003fec1  mov     rax, [rbx+60h]
0x18003fec5  jmp     short loc_18003FECB
0x18003fec7  mov     rax, [rbx+68h]
0x18003fecb  test    rax, rax
0x18003fece  jz      loc_18003FB88
0x18003fed4  mov     rdi, [rax+58h]
0x18003fed8  jmp     loc_18003FB88
0x18003fedd  lea     rdx, aPcl5eresDll; "PCL5ERES.dll"
0x18003fee4  jmp     loc_180040046
0x18003fee9  sub     edx, 12h
0x18003feec  jz      loc_18004003F
0x18003fef2  sub     edx, 1
0x18003fef5  jz      loc_180040036
0x18003fefb  sub     edx, 1
0x18003fefe  jz      loc_180040016
  ... truncated ...
```
