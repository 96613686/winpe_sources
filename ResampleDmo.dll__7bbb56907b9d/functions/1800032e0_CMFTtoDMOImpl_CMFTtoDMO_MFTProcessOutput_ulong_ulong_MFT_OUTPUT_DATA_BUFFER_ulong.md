# CMFTtoDMOImpl<CMFTtoDMO>::MFTProcessOutput(ulong,ulong,_MFT_OUTPUT_DATA_BUFFER *,ulong *)

- ea: `0x1800032e0`
- end: `0x180003982`
- name: `?MFTProcessOutput@?$CMFTtoDMOImpl@VCMFTtoDMO@@@@UEAAJKKPEAU_MFT_OUTPUT_DATA_BUFFER@@PEAK@Z`
- size: `1698`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `loader_planting`

## callees

- `0x1800032e0`
- `0x180007850`
- `0x1800085d0`
- `0x18000b79c`
- `0x180085010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180003820`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000383e`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180003820`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000383e`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExA` at `0x1800038ba`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExA` at `0x1800038ba`

## string_xrefs

- `0x180003816`: `MFCreateMediaTypeFromRepresentation`
- `0x180003837`: `MFCreateLegacyMediaBufferOnMFMediaBuffer`
- `0x1800038ad`: `MFPLAT.DLL`

## pseudocode

```c
__int64 __fastcall CMFTtoDMOImpl<CMFTtoDMO>::MFTProcessOutput(
        __int64 a1,
        unsigned int a2,
        unsigned int a3,
        __int64 a4,
        __int64 a5)
{
  unsigned __int64 v5; // rbp
  __int64 v6; // r14
  int v8; // edi
  int v9; // ebx
  unsigned __int128 v10; // rax
  char *v11; // r13
  unsigned int i; // esi
  __int64 v13; // r12
  __int64 *v14; // r14
  __int64 v15; // rax
  __int64 v16; // rdx
  __int64 v17; // r14
  int v18; // eax
  unsigned int v19; // r12d
  __int64 v20; // r8
  unsigned int v21; // ecx
  __int64 v22; // r14
  __int64 v23; // rax
  __int64 *v24; // rsi
  __int64 v25; // rax
  __int64 v26; // rcx
  unsigned int j; // r14d
  __int64 v28; // rax
  __int64 v29; // rdx
  unsigned int k; // esi
  __int64 v31; // r14
  __int64 v32; // rcx
  __int64 v33; // rax
  __int64 v35; // r9
  int v36; // eax
  __int64 v37; // rcx
  __int64 v38; // rcx
  __int64 v39; // rcx
  HMODULE Library; // rax
  FARPROC ProcAddress; // rax
  FARPROC v42; // rax
  unsigned int v43; // [rsp+30h] [rbp-78h] BYREF
  __int64 v44; // [rsp+38h] [rbp-70h] BYREF
  unsigned int v45; // [rsp+40h] [rbp-68h]
  unsigned int v46; // [rsp+44h] [rbp-64h] BYREF
  int v47; // [rsp+48h] [rbp-60h]
  __int64 v48; // [rsp+50h] [rbp-58h] BYREF
  __int64 v49; // [rsp+58h] [rbp-50h]
  __int64 v50; // [rsp+60h] [rbp-48h]
  unsigned int v52; // [rsp+C0h] [rbp+18h]

  v5 = a3;
  v6 = a4;
  if ( !a3 )
  {
    v9 = -2147024809;
    v8 = 0;
    v19 = -2147024809;
    goto LABEL_60;
  }
  if ( !a4 )
  {
    v9 = -2147467261;
    v8 = 0;
    v19 = -2147467261;
    goto LABEL_60;
  }
  if ( !*(_QWORD *)(a1 + 16) )
  {
    Library = *(HMODULE *)(a1 + 8);
    if ( Library == (HMODULE)-1LL )
    {
      v19 = -2147467259;
      v8 = 0;
      v9 = -2147467259;
      goto LABEL_60;
    }
    if ( !Library )
    {
      Library = LoadLibraryExA("MFPLAT.DLL", 0, 0x800u);
      *(_QWORD *)(a1 + 8) = Library;
      if ( !Library )
      {
        v19 = -2147467259;
        *(_QWORD *)(a1 + 8) = -1;
        v9 = -2147467259;
        v8 = 0;
        goto LABEL_60;
      }
    }
    ProcAddress = GetProcAddress(Library, "MFCreateMediaTypeFromRepresentation");
    *(_QWORD *)(a1 + 16) = ProcAddress;
    if ( !ProcAddress )
    {
      v19 = -2147467259;
      *(_QWORD *)(a1 + 8) = -1;
      v9 = -2147467259;
      v8 = 0;
      goto LABEL_60;
    }
    v42 = GetProcAddress(*(HMODULE *)(a1 + 8), "MFCreateLegacyMediaBufferOnMFMediaBuffer");
    *(_QWORD *)(a1 + 24) = v42;
    if ( !v42 )
    {
      v19 = -2147467259;
      *(_QWORD *)(a1 + 8) = -1;
      v9 = -2147467259;
      v8 = 0;
      goto LABEL_60;
    }
  }
  v8 = 0;
  if ( !*(_BYTE *)(a1 + 42) )
  {
    v9 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)(a1 + 48) + 144LL))(a1 + 48);
    if ( v9 < 0 )
      goto LABEL_63;
    *(_BYTE *)(a1 + 42) = 1;
  }
  v10 = v5 * (unsigned __int128)0x20uLL;
  v52 = 0;
  v47 = 0;
  if ( !is_mul_ok(v5, 0x20u) )
    *(_QWORD *)&v10 = -1;
  v11 = (char *)auMalloc(v10, *((_QWORD *)&v10 + 1));
  memset_0(v11, 0, 32 * v5);
  for ( i = 0; i < (unsigned int)v5; ++i )
  {
    v13 = 32LL * i;
    v14 = *(__int64 **)(v13 + v6 + 8);
    if ( !v14 )
      goto LABEL_19;
    v15 = *v14;
    v44 = 0;
    v43 = 0;
    v9 = (*(__int64 (__fastcall **)(__int64 *, unsigned int *))(v15 + 312))(v14, &v43);
    if ( v9 < 0 )
      goto LABEL_13;
    if ( v43 )
    {
      v35 = *v14;
      if ( v43 == 1 )
      {
        v9 = (*(__int64 (__fastcall **)(__int64 *, _QWORD, __int64 *))(v35 + 320))(v14, 0, &v44);
        if ( v9 < 0 )
          goto LABEL_13;
        v36 = (*(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v44 + 48LL))(v44, 0);
      }
      else
      {
        v36 = (*(__int64 (__fastcall **)(__int64 *, __int64 *))(v35 + 328))(v14, &v44);
      }
      v9 = v36;
      if ( v36 < 0 )
      {
LABEL_13:
        v17 = 0;
        if ( v44 )
        {
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v44 + 16LL))(v44);
          v44 = 0;
        }
        if ( v9 < 0 )
        {
LABEL_78:
          v19 = -1072861855;
          goto LABEL_52;
        }
        goto LABEL_16;
      }
    }
    v17 = v44;
    v44 = 0;
LABEL_16:
    v9 = (*(__int64 (__fastcall **)(_QWORD, __int64, _QWORD, char *))(a1 + 24))(
           *(_QWORD *)(v13 + a4 + 8),
           v17,
           0,
           &v11[v13]);
    if ( v9 < 0 )
      goto LABEL_78;
    if ( v17 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v17 + 16LL))(v17);
LABEL_19:
    v6 = a4;
  }
  v18 = (*(__int64 (__fastcall **)(__int64, _QWORD, _QWORD, char *, __int64))(*(_QWORD *)(a1 + 48) + 176LL))(
          a1 + 48,
          a2,
          (unsigned int)v5,
          v11,
          a5);
  v19 = -1072861855;
  v9 = v18;
  if ( v18 == -1072861855 )
  {
    v20 = 1;
    v9 = 0;
    v52 = 1;
  }
  else
  {
    if ( v18 == 1 )
    {
      v9 = -1072861838;
      goto LABEL_52;
    }
    if ( v18 < 0 )
      goto LABEL_52;
    v20 = 0;
  }
  v21 = 0;
  while ( 1 )
  {
    v43 = v21;
    if ( v21 >= (unsigned int)v5 )
      break;
    v16 = 0;
    v22 = 32LL * v21;
    v23 = v22 + a4;
    v45 = 0;
    v49 = v22;
    v50 = v22 + a4;
    v24 = *(__int64 **)(v22 + a4 + 8);
    if ( v24 )
    {
      if ( !(_DWORD)v20 )
      {
        v25 = *v24;
        v26 = *(_QWORD *)(v22 + a4 + 8);
        v46 = 0;
        v9 = (*(__int64 (__fastcall **)(__int64, unsigned int *))(v25 + 312))(v26, &v46);
        if ( v9 < 0 )
          goto LABEL_52;
        for ( j = 0; j < v46; ++j )
        {
          v28 = *v24;
          v48 = 0;
          LODWORD(v44) = 0;
          v9 = (*(__int64 (__fastcall **)(__int64 *, _QWORD, __int64 *))(v28 + 320))(v24, j, &v48);
          if ( v9 < 0 )
            goto LABEL_52;
          v9 = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v48 + 40LL))(v48, &v44);
          if ( v9 < 0 )
            goto LABEL_52;
          if ( v48 )
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v48 + 16LL))(v48);
          if ( (_DWORD)v44 )
          {
            v47 = 1;
            v45 = 1;
            break;
          }
        }
        v22 = v49;
      }
      v9 = (*(__int64 (__fastcall **)(__int64 *, const GUID *, _QWORD))(*v24 + 168))(
             v24,
             &MFSampleExtension_CleanPoint,
             *(_DWORD *)&v11[v22 + 8] & 1);
      if ( v9 < 0 )
        goto LABEL_52;
      if ( (v11[v22 + 8] & 8) != 0 )
      {
        v9 = (*(__int64 (__fastcall **)(__int64 *, const GUID *, __int64))(*v24 + 168))(
               v24,
               &MFSampleExtension_Discontinuity,
               1);
        if ( v9 < 0 )
          goto LABEL_52;
      }
      if ( (v11[v22 + 8] & 2) != 0 )
      {
        v9 = (*(__int64 (__fastcall **)(__int64 *, _QWORD))(*v24 + 288))(v24, *(_QWORD *)&v11[v22 + 16]);
        if ( v9 < 0 )
          goto LABEL_52;
      }
      v29 = (v11[v22 + 8] & 4) != 0 ? *(_QWORD *)&v11[v22 + 24] : 0LL;
      v9 = (*(__int64 (__fastcall **)(__int64 *, __int64))(*v24 + 304))(v24, v29);
      if ( v9 < 0 )
        goto LABEL_52;
      v20 = v52;
      v23 = v50;
      v16 = v45;
      v21 = v43;
    }
    *(_DWORD *)(v23 + 16) = 0;
    if ( (_DWORD)v20 )
    {
      *(_DWORD *)(v23 + 16) = 256;
      ++v21;
    }
    else
    {
      if ( (_DWORD)v16 )
      {
        if ( (*(_DWORD *)&v11[v22 + 8] & 0x1000000) != 0 )
          *(_DWORD *)(v23 + 16) = 0x1000000;
      }
      else
      {
        *(_DWORD *)(v23 + 16) = 768;
      }
      ++v21;
    }
  }
  v37 = *(_QWORD *)(a4 + 24);
  if ( v37 )
  {
    (*(void (__fastcall **)(__int64, __int64, __int64))(*(_QWORD *)v37 + 16LL))(v37, v16, v20);
    *(_QWORD *)(a4 + 24) = 0;
  }
  v38 = *(_QWORD *)(a1 + 32);
  if ( v38 )
    (*(void (__fastcall **)(__int64, __int64, __int64))(*(_QWORD *)v38 + 8LL))(v38, v16, v20);
  *(_QWORD *)(a4 + 24) = *(_QWORD *)(a1 + 32);
  v39 = *(_QWORD *)(a1 + 32);
  if ( v39 )
    (*(void (__fastcall **)(__int64, __int64, __int64))(*(_QWORD *)v39 + 16LL))(v39, v16, v20);
  *(_QWORD *)(a1 + 32) = 0;
LABEL_52:
  for ( k = 0; k < (unsigned int)v5; ++k )
  {
    v31 = 32LL * k;
    v32 = *(_QWORD *)&v11[v31];
    if ( v32 )
    {
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v32 + 16LL))(v32);
      *(_QWORD *)&v11[v31] = 0;
    }
  }
  auFree(v11, v16);
  if ( v9 < 0 )
  {
LABEL_63:
    v19 = v9;
    if ( v9 )
      goto LABEL_60;
    return 0;
  }
  else
  {
    if ( !v52 )
    {
      if ( !v47 )
      {
        v9 = -1072861838;
        v19 = -1072861838;
        goto LABEL_60;
      }
      goto LABEL_63;
    }
    v9 = -1072861855;
    while ( 1 )
    {
LABEL_60:
      if ( (unsigned __int64)v8 >= 6 )
        return v19;
      v33 = v8;
      if ( LODWORD(`CMFTtoDMOImpl<CMFTtoDMO>::DMOErrToMFErr'::`2'::s_DMOtoMFMap[v33]) == v9 )
        break;
      ++v8;
    }
    return HIDWORD(`CMFTtoDMOImpl<CMFTtoDMO>::DMOErrToMFErr'::`2'::s_DMOtoMFMap[v33]);
  }
}

```

## disassembly

```asm
0x1800032e0  mov     [rsp+arg_18], r9
0x1800032e5  mov     [rsp+arg_8], edx
0x1800032e9  push    rbx
0x1800032ea  push    rbp
0x1800032eb  push    rdi
0x1800032ec  push    r12
0x1800032ee  push    r14
0x1800032f0  push    r15
0x1800032f2  sub     rsp, 78h
0x1800032f6  mov     ebp, r8d
0x1800032f9  mov     r14, r9
0x1800032fc  mov     r15, rcx
0x1800032ff  test    r8d, r8d
0x180003302  jz      loc_18000387D
0x180003308  test    r9, r9
0x18000330b  jz      loc_18000388C
0x180003311  cmp     qword ptr [rcx+10h], 0
0x180003316  jz      loc_1800037FF
0x18000331c  xor     edi, edi
0x18000331e  cmp     [r15+2Ah], dil
0x180003322  jnz     short loc_180003347
0x180003324  mov     rax, [r15+30h]
0x180003328  lea     rcx, [r15+30h]
0x18000332c  mov     rax, [rax+90h]
0x180003333  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003338  mov     ebx, eax
0x18000333a  test    eax, eax
0x18000333c  js      loc_1800036F2
0x180003342  mov     byte ptr [r15+2Ah], 1
0x180003347  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x18000334e  mov     [rsp+0A8h+arg_0], rsi
0x180003356  mov     eax, 20h ; ' '
0x18000335b  mov     [rsp+0A8h+var_38], r13
0x180003360  mul     rbp
0x180003363  mov     [rsp+0A8h+arg_10], edi
0x18000336a  mov     rbx, rbp
0x18000336d  mov     [rsp+0A8h+var_60], edi
0x180003371  cmovb   rax, rcx
0x180003375  mov     rcx, rax
0x180003378  call    auMalloc
0x18000337d  shl     rbx, 5
0x180003381  xor     edx, edx; Val
0x180003383  mov     r8, rbx; Size
0x180003386  mov     rcx, rax; void *
0x180003389  mov     r13, rax
0x18000338c  call    memset_0
0x180003391  mov     esi, edi
0x180003393  cmp     esi, ebp
0x180003395  jnb     loc_18000344D
0x18000339b  mov     r12d, esi
0x18000339e  shl     r12, 5
0x1800033a2  mov     r14, [r12+r14+8]
0x1800033a7  test    r14, r14
0x1800033aa  jz      loc_18000343E
0x1800033b0  mov     rax, [r14]
0x1800033b3  lea     rdx, [rsp+0A8h+var_78]
0x1800033b8  mov     rcx, r14
0x1800033bb  mov     [rsp+0A8h+var_70], rdi
0x1800033c0  mov     [rsp+0A8h+var_78], edi
0x1800033c4  mov     rax, [rax+138h]
0x1800033cb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800033d0  mov     ebx, eax
0x1800033d2  test    eax, eax
0x1800033d4  jns     loc_180003709
0x1800033da  mov     rcx, [rsp+0A8h+var_70]
0x1800033df  mov     r14, rdi
0x1800033e2  test    rcx, rcx
0x1800033e5  jz      short loc_1800033F8
0x1800033e7  mov     rax, [rcx]
0x1800033ea  mov     rax, [rax+10h]
0x1800033ee  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800033f3  mov     [rsp+0A8h+var_70], rdi
0x1800033f8  test    ebx, ebx
0x1800033fa  js      loc_1800037A9
0x180003400  mov     rcx, [rsp+0A8h+arg_18]
0x180003408  lea     r9, [r12+r13]
0x18000340c  mov     rax, [r15+18h]
0x180003410  xor     r8d, r8d
0x180003413  mov     rdx, r14
0x180003416  mov     rcx, [r12+rcx+8]
0x18000341b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003420  mov     ebx, eax
0x180003422  test    eax, eax
0x180003424  js      loc_1800037A9
0x18000342a  test    r14, r14
0x18000342d  jz      short loc_18000343E
0x18000342f  mov     rax, [r14]
0x180003432  mov     rcx, r14
0x180003435  mov     rax, [rax+10h]
0x180003439  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000343e  mov     r14, [rsp+0A8h+arg_18]
0x180003446  inc     esi
0x180003448  jmp     loc_180003393
0x18000344d  mov     rdx, [rsp+0A8h+arg_20]
0x180003455  lea     rcx, [r15+30h]
0x180003459  mov     rax, [rcx]
0x18000345c  mov     r9, r13
0x18000345f  mov     [rsp+0A8h+var_88], rdx
0x180003464  mov     r8d, ebp
0x180003467  mov     edx, [rsp+0A8h+arg_8]
0x18000346e  mov     rax, [rax+0B0h]
0x180003475  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000347a  mov     r12d, 0C00D6D61h
0x180003480  mov     ebx, eax
0x180003482  cmp     eax, r12d
0x180003485  jz      loc_180003919
0x18000348b  cmp     eax, 1
0x18000348e  jz      loc_18000365E
0x180003494  test    eax, eax
0x180003496  js      loc_180003663
0x18000349c  mov     r8d, edi
0x18000349f  mov     ecx, edi
0x1800034a1  mov     [rsp+0A8h+var_78], ecx
0x1800034a5  cmp     ecx, ebp
0x1800034a7  jnb     loc_180003769
0x1800034ad  mov     rax, [rsp+0A8h+arg_18]
0x1800034b5  mov     edx, edi
0x1800034b7  mov     r14d, ecx
0x1800034ba  shl     r14, 5
0x1800034be  add     rax, r14
0x1800034c1  mov     [rsp+0A8h+var_68], edx
0x1800034c5  mov     [rsp+0A8h+var_50], r14
0x1800034ca  mov     [rsp+0A8h+var_48], rax
0x1800034cf  mov     rsi, [rax+8]
0x1800034d3  test    rsi, rsi
0x1800034d6  jz      loc_180003631
0x1800034dc  test    r8d, r8d
0x1800034df  jnz     loc_180003596
0x1800034e5  mov     rax, [rsi]
0x1800034e8  lea     rdx, [rsp+0A8h+var_64]
0x1800034ed  mov     rcx, rsi
0x1800034f0  mov     [rsp+0A8h+var_64], edi
0x1800034f4  mov     rax, [rax+138h]
0x1800034fb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003500  mov     ebx, eax
0x180003502  test    eax, eax
0x180003504  js      loc_180003663
0x18000350a  mov     r14d, edi
0x18000350d  cmp     r14d, [rsp+0A8h+var_64]
0x180003512  jnb     short loc_180003591
0x180003514  mov     rax, [rsi]
0x180003517  lea     r8, [rsp+0A8h+var_58]
0x18000351c  mov     edx, r14d
0x18000351f  mov     [rsp+0A8h+var_58], rdi
0x180003524  mov     rcx, rsi
0x180003527  mov     dword ptr [rsp+0A8h+var_70], edi
0x18000352b  mov     rax, [rax+140h]
0x180003532  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003537  mov     ebx, eax
0x180003539  test    eax, eax
0x18000353b  js      loc_180003663
0x180003541  mov     rcx, [rsp+0A8h+var_58]
0x180003546  lea     rdx, [rsp+0A8h+var_70]
0x18000354b  mov     rax, [rcx]
0x18000354e  mov     rax, [rax+28h]
0x180003552  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003557  mov     ebx, eax
0x180003559  test    eax, eax
0x18000355b  js      loc_180003663
0x180003561  mov     rcx, [rsp+0A8h+var_58]
0x180003566  test    rcx, rcx
0x180003569  jz      short loc_180003577
0x18000356b  mov     rax, [rcx]
0x18000356e  mov     rax, [rax+10h]
0x180003572  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003577  cmp     dword ptr [rsp+0A8h+var_70], edi
0x18000357b  jz      loc_1800037BB
0x180003581  mov     [rsp+0A8h+var_60], 1
0x180003589  mov     [rsp+0A8h+var_68], 1
0x180003591  mov     r14, [rsp+0A8h+var_50]
0x180003596  mov     rax, [rsi]
0x180003599  lea     rdx, MFSampleExtension_CleanPoint
0x1800035a0  mov     r8d, [r14+r13+8]
0x1800035a5  mov     rcx, rsi
0x1800035a8  and     r8d, 1
0x1800035ac  mov     rax, [rax+0A8h]
0x1800035b3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800035b8  mov     ebx, eax
0x1800035ba  test    eax, eax
0x1800035bc  js      loc_180003663
0x1800035c2  test    byte ptr [r14+r13+8], 8
0x1800035c8  jnz     loc_1800037D1
0x1800035ce  test    byte ptr [r14+r13+8], 2
0x1800035d4  jz      short loc_1800035F3
0x1800035d6  mov     rax, [rsi]
0x1800035d9  mov     rcx, rsi
0x1800035dc  mov     rdx, [r14+r13+10h]
0x1800035e1  mov     rax, [rax+120h]
0x1800035e8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800035ed  mov     ebx, eax
0x1800035ef  test    eax, eax
0x1800035f1  js      short loc_180003663
0x1800035f3  test    byte ptr [r14+r13+8], 4
0x1800035f9  mov     rcx, rsi
0x1800035fc  mov     rax, [rsi]
0x1800035ff  mov     rax, [rax+130h]
0x180003606  jz      loc_1800037B4
0x18000360c  mov     rdx, [r14+r13+18h]
0x180003611  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003616  mov     ebx, eax
0x180003618  test    eax, eax
0x18000361a  js      short loc_180003663
0x18000361c  mov     r8d, [rsp+0A8h+arg_10]
0x180003624  mov     rax, [rsp+0A8h+var_48]
0x180003629  mov     edx, [rsp+0A8h+var_68]
0x18000362d  mov     ecx, [rsp+0A8h+var_78]
0x180003631  mov     [rax+10h], edi
0x180003634  test    r8d, r8d
0x180003637  jnz     loc_1800037C3
0x18000363d  test    edx, edx
0x18000363f  jz      loc_18000392E
0x180003645  test    dword ptr [r14+r13+8], 1000000h
0x18000364e  jz      short loc_180003657
0x180003650  mov     dword ptr [rax+10h], 1000000h
0x180003657  inc     ecx
0x180003659  jmp     loc_1800034A1
0x18000365e  mov     ebx, 0C00D6D72h
0x180003663  mov     esi, edi
0x180003665  test    ebp, ebp
0x180003667  jz      short loc_18000368F
0x180003669  mov     r14d, esi
0x18000366c  shl     r14, 5
0x180003670  mov     rcx, [r14+r13]
0x180003674  test    rcx, rcx
0x180003677  jz      short loc_180003689
0x180003679  mov     rax, [rcx]
0x18000367c  mov     rax, [rax+10h]
0x180003680  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003685  mov     [r14+r13], rdi
0x180003689  inc     esi
0x18000368b  cmp     esi, ebp
0x18000368d  jb      short loc_180003669
0x18000368f  mov     rcx, r13
0x180003692  call    auFree
0x180003697  mov     r13, [rsp+0A8h+var_38]
0x18000369c  mov     rsi, [rsp+0A8h+arg_0]
0x1800036a4  test    ebx, ebx
0x1800036a6  js      short loc_1800036F2
0x1800036a8  cmp     [rsp+0A8h+arg_10], edi
0x1800036af  jnz     loc_180003971
0x1800036b5  cmp     [rsp+0A8h+var_60], edi
0x1800036b9  jnz     short loc_1800036F2
0x1800036bb  mov     ebx, 0C00D6D72h
0x1800036c0  mov     r12d, ebx
0x1800036c3  lea     rcx, ?s_DMOtoMFMap@?1??DMOErrToMFErr@?$CMFTtoDMOImpl@VCMFTtoDMO@@@@IEAAJJ@Z@4QBU_DMOtoMFMap@?1??12@IEAAJJ@Z@B; `CMFTtoDMOImpl<CMFTtoDMO>::DMOErrToMFErr(long)'::`2'::_DMOtoMFMap const near * const `CMFTtoDMOImpl<CMFTtoDMO>::DMOErrToMFErr(long)'::`2'::s_DMOtoMFMap
0x1800036ca  nop     word ptr [rax+rax+00h]
0x1800036d0  movsxd  rax, edi
0x1800036d3  cmp     rax, 6
0x1800036d7  jnb     loc_18000386C
0x1800036dd  lea     rax, ds:0[rax*8]
0x1800036e5  cmp     [rax+rcx], ebx
0x1800036e8  jz      loc_180003979
0x1800036ee  inc     edi
0x1800036f0  jmp     short loc_1800036D0
0x1800036f2  mov     r12d, ebx
0x1800036f5  test    ebx, ebx
0x1800036f7  jnz     short loc_1800036C3
0x1800036f9  mov     eax, ebx
0x1800036fb  add     rsp, 78h
0x1800036ff  pop     r15
0x180003701  pop     r14
0x180003703  pop     r12
0x180003705  pop     rdi
0x180003706  pop     rbp
0x180003707  pop     rbx
0x180003708  retn
0x180003709  mov     eax, [rsp+0A8h+var_78]
0x18000370d  test    eax, eax
0x18000370f  jz      short loc_18000375A
0x180003711  mov     r9, [r14]
0x180003714  mov     rcx, r14
0x180003717  cmp     eax, 1
0x18000371a  jnz     loc_180003903
0x180003720  mov     rax, [r9+140h]
0x180003727  lea     r8, [rsp+0A8h+var_70]
0x18000372c  xor     edx, edx
0x18000372e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003733  mov     ebx, eax
0x180003735  test    eax, eax
0x180003737  js      loc_1800033DA
0x18000373d  mov     rcx, [rsp+0A8h+var_70]
0x180003742  xor     edx, edx
0x180003744  mov     rax, [rcx]
0x180003747  mov     rax, [rax+30h]
0x18000374b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003750  mov     ebx, eax
0x180003752  test    eax, eax
0x180003754  js      loc_1800033DA
0x18000375a  mov     r14, [rsp+0A8h+var_70]
0x18000375f  mov     [rsp+0A8h+var_70], rdi
0x180003764  jmp     loc_180003400
0x180003769  mov     r14, [rsp+0A8h+arg_18]
0x180003771  mov     rcx, [r14+18h]
0x180003775  test    rcx, rcx
0x180003778  jnz     loc_18000393A
0x18000377e  mov     rcx, [r15+20h]
0x180003782  test    rcx, rcx
0x180003785  jnz     loc_18000394F
0x18000378b  mov     rax, [r15+20h]
0x18000378f  mov     [r14+18h], rax
  ... truncated ...
```
