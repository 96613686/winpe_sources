# BPackBinaryData

- ea: `0x180056d1c`
- end: `0x180057c19`
- name: `BPackBinaryData`
- size: `3837`
- prototype: `__int64 __fastcall(__int64, int)`
- caller_count: `1`
- callee_count: `18`
- tags: `file_ops`

## callers

- `0x1800581bc`

## callees

- `0x180001f20`
- `0x180056d1c`
- `0x180057f70`
- `0x1800582c4`
- `0x180058374`
- `0x1800584fc`
- `0x180058908`
- `0x180058998`
- `0x180058b50`
- `0x180058f18`
- `0x1800598cc`
- `0x180059940`
- `0x180059a78`
- `0x180059af0`
- `0x180059b58`
- `0x18005a058`
- `0x18005e094`
- `0x18005e0c4`

## import_xrefs

- `KERNEL32!MultiByteToWideChar` at `0x180057afa`
- `KERNEL32!MultiByteToWideChar` at `0x180057afa`
- `KERNEL32!GetCPInfo` at `0x180056fd1`
- `KERNEL32!GetCPInfo` at `0x180056fd1`
- `KERNEL32!GetFileTime` at `0x180056eac`
- `KERNEL32!GetFileTime` at `0x180056eac`
- `KERNEL32!GetSystemTimeAsFileTime` at `0x180056ec0`
- `KERNEL32!GetSystemTimeAsFileTime` at `0x180056ec0`
- `KERNEL32!HeapAlloc` at `0x180057520`
- `KERNEL32!HeapAlloc` at `0x18005756c`
- `KERNEL32!HeapAlloc` at `0x180057520`
- `KERNEL32!HeapAlloc` at `0x18005756c`
- `KERNEL32!CreateFileW` at `0x180056e8b`
- `KERNEL32!CreateFileW` at `0x180056e8b`
- `KERNEL32!CloseHandle` at `0x180056ed5`
- `KERNEL32!CloseHandle` at `0x180056ed5`
- `KERNEL32!RaiseException` at `0x180057541`
- `KERNEL32!RaiseException` at `0x18005758d`
- `KERNEL32!RaiseException` at `0x180057541`
- `KERNEL32!RaiseException` at `0x18005758d`

## pseudocode

```c
__int64 __fastcall BPackBinaryData(__int64 a1, int a2)
{
  _DWORD *v3; // rax
  _DWORD *v4; // r14
  unsigned __int64 v5; // r13
  __int64 v6; // rdi
  _QWORD *v7; // rax
  __int64 v8; // r12
  unsigned int v9; // ecx
  __int64 v10; // r8
  _QWORD *v11; // r13
  WCHAR *v12; // rbx
  __int64 v13; // rdi
  HANDLE FileW; // rax
  void *v15; // rbx
  unsigned int v16; // ecx
  unsigned int v17; // eax
  UINT v18; // ebx
  int v19; // ecx
  int v20; // ecx
  int v21; // ecx
  _QWORD *v22; // rcx
  _QWORD *v23; // rdx
  int v24; // r9d
  int v25; // r10d
  __int64 *i; // rax
  __int64 *v27; // r8
  _QWORD *v28; // r8
  _QWORD *v29; // rax
  _QWORD *v30; // rax
  int v31; // ecx
  _DWORD *v32; // rdx
  int v33; // eax
  int v34; // eax
  unsigned int v35; // eax
  unsigned int v36; // ecx
  int v37; // eax
  _DWORD *v38; // r8
  _DWORD *v39; // r8
  __int64 *j; // rbx
  int v41; // edx
  _QWORD *k; // rdi
  _QWORD *m; // rbx
  _QWORD *n; // rbx
  __int64 *ii; // rbx
  _QWORD *v46; // rdi
  _QWORD *v47; // rdi
  _DWORD *v48; // rax
  _DWORD *v49; // rbx
  unsigned int v50; // edi
  const char *v51; // rcx
  int v52; // eax
  _QWORD *v53; // rax
  int v54; // edi
  int v55; // ebx
  unsigned int v56; // ecx
  _DWORD *v57; // rdi
  __int64 *jj; // rbx
  __int64 v59; // rdx
  _QWORD *v60; // rax
  int v61; // edi
  int v62; // ebx
  unsigned int v63; // ecx
  _DWORD *v64; // rdi
  __int64 *kk; // rbx
  int v66; // edx
  __int64 *v67; // rcx
  int v68; // ebx
  int v69; // eax
  int v70; // edx
  __int64 v71; // rax
  unsigned int v72; // ebx
  unsigned int v73; // ecx
  WCHAR *v74; // rdi
  WCHAR *v75; // r12
  __int64 *mm; // rbx
  bool v77; // zf
  int v78; // r9d
  int v79; // eax
  const CHAR *v80; // r8
  __int64 v81; // r9
  int v82; // eax
  int v84; // [rsp+44h] [rbp-D4h] BYREF
  int v85; // [rsp+48h] [rbp-D0h]
  int v86; // [rsp+4Ch] [rbp-CCh]
  int v87; // [rsp+50h] [rbp-C8h]
  int v88; // [rsp+54h] [rbp-C4h]
  int v89; // [rsp+58h] [rbp-C0h]
  int v90; // [rsp+5Ch] [rbp-BCh]
  int v91; // [rsp+60h] [rbp-B8h]
  int v92; // [rsp+64h] [rbp-B4h]
  WCHAR *v93; // [rsp+68h] [rbp-B0h]
  _DWORD *v94; // [rsp+70h] [rbp-A8h]
  int v95; // [rsp+78h] [rbp-A0h]
  _QWORD *v96; // [rsp+80h] [rbp-98h]
  _QWORD *v97; // [rsp+88h] [rbp-90h]
  _DWORD *v98; // [rsp+90h] [rbp-88h]
  _DWORD *v99; // [rsp+98h] [rbp-80h]
  _DWORD *v100; // [rsp+A0h] [rbp-78h]
  unsigned __int64 v101; // [rsp+A8h] [rbp-70h]
  __int64 v102; // [rsp+B0h] [rbp-68h]
  const CHAR *v103; // [rsp+B8h] [rbp-60h]
  WCHAR *v104; // [rsp+C0h] [rbp-58h]
  _cpinfo CPInfo; // [rsp+C8h] [rbp-50h] BYREF

  v84 = a2;
  v92 = 0;
  VGrowPackBuffer(a1, 0x274u);
  *(_DWORD *)(a1 + 1040) = 628;
  v3 = *(_DWORD **)(a1 + 1048);
  v94 = v3;
  v4 = *(_DWORD **)(a1 + 1056);
  v5 = *(_QWORD *)(a1 + 1064);
  v101 = v5;
  v3[1] = 1347437600;
  v3[2] = 1703966;
  v3[14] = 64;
  v3[15] = 400;
  v86 = 0;
  v6 = *(_QWORD *)(a1 + 1048);
  v85 = 0;
  v7 = *(_QWORD **)(a1 + 64);
  LODWORD(v8) = 0;
  v85 = 0;
  while ( v7 )
  {
    v7 = (_QWORD *)*v7;
    LODWORD(v8) = v8 + 1;
    v85 = v8;
  }
  v86 = v8;
  *(_DWORD *)(v6 + 28) = v8;
  if ( (_DWORD)v8 )
  {
    VGrowPackBuffer(a1, 12 * v8);
    *(_DWORD *)(v6 + 32) = *(_DWORD *)(a1 + 1040);
    v9 = *(_DWORD *)(a1 + 1040);
    v10 = *(_QWORD *)(a1 + 1024) + v9;
    v102 = v10;
    *(_DWORD *)(a1 + 1040) = v9 + ((12 * v8 + 3) & 0xFFFFFFFC);
    v11 = *(_QWORD **)(a1 + 64);
    while ( v11 )
    {
      v8 = (unsigned int)(v8 - 1);
      v86 = v8;
      v12 = (WCHAR *)v11[1];
      v13 = v10 + 12 * v8;
      VPackStringUnicode(a1, (_DWORD *)v13, v12);
      FileW = CreateFileW(v12, 0x80000000, 1u, 0, 3u, 0x100080u, 0);
      v15 = FileW;
      if ( FileW == (HANDLE)-1LL || !GetFileTime(FileW, 0, 0, (LPFILETIME)(v13 + 4)) )
        GetSystemTimeAsFileTime((LPFILETIME)(v13 + 4));
      if ( v15 != (void *)-1LL )
        CloseHandle(v15);
      v11 = (_QWORD *)*v11;
      v10 = v102;
    }
    v5 = v101;
  }
  if ( *(_QWORD *)(a1 + 48) )
    *(_DWORD *)(a1 + 40) = 1;
  if ( *(_DWORD *)(a1 + 60) )
    *(_DWORD *)(a1 + 40) = 1;
  if ( !*(_DWORD *)(a1 + 72) )
    *(_DWORD *)(a1 + 40) = 1;
  if ( !*(_DWORD *)(a1 + 120) )
    *(_DWORD *)(a1 + 40) = 1;
  if ( !*(_DWORD *)(a1 + 96) )
    *(_DWORD *)(a1 + 40) = 1;
  v16 = *(_DWORD *)(a1 + 336);
  if ( !v16 )
  {
    *(_DWORD *)(a1 + 40) = 1;
    *(_DWORD *)(a1 + 336) = 1;
    v16 = 1;
  }
  v17 = 176128;
  if ( v16 > 1 )
    v17 = 254976;
  if ( *(_DWORD *)(a1 + 340) < v17 )
  {
    *(_DWORD *)(a1 + 40) = 1;
    *(_DWORD *)(a1 + 340) = v17;
  }
  v18 = 0;
  memset(&CPInfo, 0, sizeof(CPInfo));
  v19 = *(_DWORD *)(a1 + 328);
  if ( !v19 )
  {
LABEL_38:
    if ( ((v18 + 2) & 0xFFFFFFFD) == 0 )
      goto LABEL_41;
    goto LABEL_39;
  }
  v20 = v19 - 1;
  if ( !v20 )
  {
    v18 = 1252;
    goto LABEL_38;
  }
  v21 = v20 - 1;
  if ( !v21 )
  {
    v18 = -2;
    goto LABEL_41;
  }
  if ( v21 != 1 )
    goto LABEL_38;
  v18 = 932;
LABEL_39:
  if ( !GetCPInfo(v18, &CPInfo) )
    v18 = -1;
LABEL_41:
  *(_DWORD *)(a1 + 332) = v18;
  v22 = 0;
  v96 = 0;
  v23 = 0;
  v97 = 0;
  v24 = 0;
  v87 = 0;
  v25 = 0;
  v88 = 0;
  for ( i = *(__int64 **)(a1 + 152); i; i = v27 )
  {
    v27 = (__int64 *)*i;
    if ( *((_DWORD *)i + 13) )
    {
      *i = (__int64)v22;
      v22 = i;
      v96 = i;
      v87 = ++v24;
    }
    else
    {
      *i = (__int64)v23;
      v23 = i;
      v97 = i;
      v88 = ++v25;
    }
  }
  v28 = 0;
  while ( v22 )
  {
    v29 = (_QWORD *)*v22;
    *v22 = v28;
    v28 = v22;
    v22 = v29;
    v96 = v29;
  }
  while ( v23 )
  {
    v30 = (_QWORD *)*v23;
    *v23 = v28;
    v28 = v23;
    v23 = v30;
    v97 = v30;
  }
  *(_QWORD *)(a1 + 152) = v28;
  *(_DWORD *)(*(_QWORD *)(a1 + 1048) + 20LL) = v25;
  *(_DWORD *)(*(_QWORD *)(a1 + 1048) + 24LL) = v24;
  if ( v84 )
  {
    v4[75] = 1;
    v31 = 1;
  }
  else
  {
    v31 = *(_DWORD *)(a1 + 492);
    v4[75] = v31;
  }
  *v4 = 336;
  v32 = v94;
  v4[6] = v94[5];
  v4[7] = v32[6];
  v4[5] = 2;
  if ( v31 )
  {
    v33 = 1;
    if ( *(_DWORD *)(a1 + 496) )
      v33 = *(_DWORD *)(a1 + 496);
    v4[15] = v33;
  }
  else
  {
    v4[15] = 9999;
  }
  v4[17] = 1;
  v4[18] = 1000;
  v4[4] = *(_DWORD *)(a1 + 96);
  v4[19] = *(_DWORD *)(a1 + 328);
  v4[20] = *(_DWORD *)(a1 + 336);
  v34 = *(_DWORD *)(a1 + 344);
  v4[32] = v34;
  v4[30] = v34;
  v4[31] = 1;
  v35 = *(_DWORD *)(a1 + 516);
  if ( v35 || *(_DWORD *)(a1 + 520) )
  {
    if ( v35 < 4 || (v36 = *(_DWORD *)(a1 + 520), v36 > 0xF) || v35 > v36 )
    {
      *(_DWORD *)(a1 + 40) = 1;
    }
    else
    {
      v4[76] = v35;
      v4[77] = *(_DWORD *)(a1 + 520);
    }
  }
  v4[25] = *(_DWORD *)(a1 + 360) | 0x10;
  v4[26] = *(_DWORD *)(a1 + 348);
  v4[27] = *(_DWORD *)(a1 + 352);
  v4[28] = *(_DWORD *)(a1 + 364);
  v4[29] = *(_DWORD *)(a1 + 340);
  v4[33] = *(_DWORD *)(a1 + 380);
  v4[34] = *(_DWORD *)(a1 + 376);
  v4[36] = 255;
  *(_DWORD *)(v5 + 16) = *(_DWORD *)(a1 + 92);
  *(_DWORD *)(v5 + 4) = *(_DWORD *)(a1 + 404);
  v4[44] = 25400;
  v4[43] = 25400;
  v37 = 18;
  v4[35] = 18;
  if ( *(_DWORD *)(a1 + 356) )
  {
    v37 = 26;
    v4[35] = 26;
  }
  if ( *(_DWORD *)(a1 + 368) != 270 )
    v4[35] = v37 | 4;
  if ( PvFindListItem(*(_QWORD **)(a1 + 152), (__int64)"StapleLocation", 0)
    || PvFindListItem(*(_QWORD **)(a1 + 152), (__int64)"StapleX", v38)
    && PvFindListItem(*(_QWORD **)(a1 + 152), (__int64)"StapleY", v39) )
  {
    v4[35] |= 0x80u;
  }
  if ( *(_DWORD *)(a1 + 384) )
    v4[35] |= 0x100u;
  if ( *(_DWORD *)(a1 + 336) <= 1u )
    goto LABEL_83;
  if ( *(_DWORD *)(a1 + 480) )
  {
    if ( !*(_DWORD *)(a1 + 484) )
      goto LABEL_82;
  }
  else if ( *(_DWORD *)(a1 + 100) < 0xBC3u )
  {
LABEL_82:
    v4[35] |= 0x800u;
  }
LABEL_83:
  if ( *(_DWORD *)(a1 + 488) )
    v4[35] |= 0x1000u;
  if ( *(_DWORD *)(a1 + 512) )
    v4[35] |= 0x8000u;
  v4[74] = *(_DWORD *)(a1 + 500);
  VPackStringAnsiToUnicode(a1, v4 + 3, *(const CHAR **)(a1 + 80), *(_DWORD *)(a1 + 72));
  for ( j = *(__int64 **)(a1 + 200); j; j = (__int64 *)*j )
  {
    v41 = *((_DWORD *)j + 4);
    if ( v41 )
    {
      VGrowPackBuffer(a1, v41 + 1);
      memcpy_0(
        (void *)(*(_QWORD *)(a1 + 1024) + *(unsigned int *)(a1 + 1040)),
        (const void *)j[3],
        *((unsigned int *)j + 4));
      j[3] = *(unsigned int *)(a1 + 1040);
      *(_DWORD *)(a1 + 1040) += (*((_DWORD *)j + 4) + 4) & 0xFFFFFFFC;
    }
    else
    {
      j[3] = 0;
    }
  }
  VResolveSymbolInvocation(a1, a1 + 216);
  VResolveSymbolInvocation(a1, a1 + 232);
  VResolveSymbolInvocation(a1, a1 + 248);
  VResolveSymbolInvocation(a1, a1 + 264);
  VResolveSymbolInvocation(a1, a1 + 280);
  VResolveSymbolInvocation(a1, a1 + 296);
  VResolveSymbolInvocation(a1, a1 + 312);
  for ( k = *(_QWORD **)(a1 + 152); k; k = (_QWORD *)*k )
  {
    VResolveSymbolInvocation(a1, (__int64)(k + 8));
    for ( m = (_QWORD *)k[11]; m; m = (_QWORD *)*m )
      VResolveSymbolInvocation(a1, (__int64)(m + 4));
  }
  for ( n = *(_QWORD **)(a1 + 192); n; n = (_QWORD *)*n )
    VResolveSymbolInvocation(a1, (__int64)(n + 3));
  VPackInvocation(a1, v4 + 21, (unsigned int *)(a1 + 216));
  VPackInvocation(a1, v4 + 23, (unsigned int *)(a1 + 232));
  *(_DWORD *)(v5 + 52) = 255;
  *(_DWORD *)(v5 + 48) = 255;
  *(_DWORD *)(v5 + 60) = 255;
  *(_DWORD *)(v5 + 56) = 255;
  *(_DWORD *)(v5 + 44) = *(_DWORD *)(a1 + 416);
  *(_OWORD *)(v5 + 64) = *(_OWORD *)(a1 + 420);
  *(_OWORD *)(v5 + 80) = *(_OWORD *)(a1 + 436);
  *(_OWORD *)(v5 + 96) = *(_OWORD *)(a1 + 452);
  *(_OWORD *)(v5 + 108) = *(_OWORD *)(a1 + 464);
  for ( ii = *(__int64 **)(a1 + 152); ii; ii = (__int64 *)*ii )
  {
    if ( ii[5] && !ii[11] )
    {
      v46 = HeapAlloc(*(HANDLE *)(a1 + 8), 8u, *((unsigned int *)ii + 21));
      if ( !v46 )
        RaiseException(0xC0000000, 0, 0, 0);
      v46[1] = ii[5];
      ii[11] = (__int64)v46;
    }
    if ( *((_DWORD *)ii + 12) == 4 )
    {
      v47 = HeapAlloc(*(HANDLE *)(a1 + 8), 8u, *((unsigned int *)ii + 21));
      if ( !v47 )
        RaiseException(0xC0000000, 0, 0, 0);
      v47[1] = "*UseFormTrayTable";
      *v47 = ii[11];
      ii[11] = (__int64)v47;
      *((_DWORD *)v47 + 17) = 15;
    }
  }
  VPackUIConstraints(a1);
  VPackOrderDependency(a1, (unsigned int *)(v5 + 196), *(_QWORD **)(a1 + 168));
  VPackOrderDependency(a1, (unsigned int *)(v5 + 204), *(_QWORD **)(a1 + 176));
  VPackPrinterFeatures(a1);
  *(_DWORD *)v5 = 228;
  *(_DWORD *)(v5 + 8) = *(_DWORD *)(a1 + 392);
  *(_DWORD *)(v5 + 12) = *(_DWORD *)(a1 + 396);
  *(_DWORD *)(v5 + 20) = *(_DWORD *)(a1 + 100);
  *(_DWORD *)(v5 + 224) = *(_DWORD *)(a1 + 372);
  v98 = 0;
  v89 = 0;
  *(_DWORD *)(v5 + 40) = -1;
  v48 = v94;
  if ( v4[8] )
    v49 = (_DWORD *)((char *)v94 + (unsigned int)v4[8]);
  else
    v49 = 0;
  v50 = 0;
  v89 = 0;
  while ( 1 )
  {
    v98 = v49;
    if ( v50 >= v4[6] )
      break;
    if ( *v49 )
      v51 = (char *)v48 + (unsigned int)*v49;
    else
      v51 = 0;
    if ( v51 && !strcmp_0(v51, "OutputOrder") )
    {
      *(_DWORD *)(v5 + 40) = v50;
      break;
    }
    v89 = ++v50;
    v49 += 21;
    v48 = v94;
  }
  VPackInvocation(a1, (_DWORD *)(v5 + 24), (unsigned int *)(a1 + 104));
  VPackInvocation(a1, (_DWORD *)(v5 + 32), (unsigned int *)(a1 + 120));
  if ( (v4[35] & 0x20) != 0 )
  {
    v52 = *(_DWORD *)(v5 + 44);
    if ( (v52 & 3) == 0 )
    {
      v52 |= 2u;
      *(_DWORD *)(v5 + 44) = v52;
    }
    if ( (v52 & 2) == 0 )
      *(_DWORD *)(v5 + 44) = v52 | 4;
  }
  VPackInvocation(a1, (_DWORD *)(v5 + 144), (unsigned int *)(a1 + 248));
  VPackInvocation(a1, (_DWORD *)(v5 + 152), (unsigned int *)(a1 + 264));
  VPackInvocation(a1, (_DWORD *)(v5 + 160), (unsigned int *)(a1 + 280));
  VPackInvocation(a1, (_DWORD *)(v5 + 168), (unsigned int *)(a1 + 296));
  VPackInvocation(a1, (_DWORD *)(v5 + 176), (unsigned int *)(a1 + 312));
  VPackNt4Mapping(a1);
  v99 = 0;
  v84 = 0;
  v90 = 0;
  v53 = *(_QWORD **)(a1 + 184);
  v54 = 0;
  v90 = 0;
  while ( v53 )
  {
    v53 = (_QWORD *)*v53;
    v90 = ++v54;
  }
  if ( v54 )
  {
    v55 = 24 * v54;
    VGrowPackBuffer(a1, 24 * v54);
    *(_DWORD *)(*(_QWORD *)(a1 + 1064) + 188LL) = v54;
    *(_DWORD *)(*(_QWORD *)(a1 + 1064) + 192LL) = *(_DWORD *)(a1 + 1040);
    v56 = *(_DWORD *)(a1 + 1040);
    v57 = (_DWORD *)(*(_QWORD *)(a1 + 1024) + v56);
    v99 = v57;
    *(_DWORD *)(a1 + 1040) = v56 + ((v55 + 3) & 0xFFFFFFFC);
    for ( jj = *(__int64 **)(a1 + 184); jj; jj = (__int64 *)*jj )
    {
      VPackStringAnsi(a1, v57, (_BYTE *)jj[1]);
      VPackStringXlation(a1, v57 + 1, (const CHAR *)jj[1], (__int64)(jj + 2));
      VPackStringAnsi(a1, v57 + 2, (_BYTE *)jj[4]);
      VPackStringAnsi(a1, v57 + 3, (_BYTE *)jj[5]);
      VPackStringAnsi(a1, v57 + 4, (_BYTE *)jj[6]);
      v57[5] = *((_DWORD *)jj + 14);
      v57 += 6;
      v99 = v57;
    }
    v59 = *(_QWORD *)(a1 + 408);
    if ( v59 )
    {
      if ( PvFindListItem(*(_QWORD **)(a1 + 184), v59, &v84) )
        *(_DWORD *)(*(_QWORD *)(a1 + 1064) + 184LL) = *(_DWORD *)(*(_QWORD *)(a1 + 1064) + 192LL) + 24 * v84;
    }
  }
  v100 = 0;
  v91 = 0;
  v60 = *(_QWORD **)(a1 + 192);
  v61 = 0;
  v91 = 0;
  while ( v60 )
  {
    v60 = (_QWORD *)*v60;
    v91 = ++v61;
  }
  if ( v61 )
  {
    v62 = 12 * v61;
    VGrowPackBuffer(a1, 12 * v61);
    *(_DWORD *)(*(_QWORD *)(a1 + 1064) + 212LL) = v61;
    *(_DWORD *)(*(_QWORD *)(a1 + 1064) + 216LL) = *(_DWORD *)(a1 + 1040);
    v63 = *(_DWORD *)(a1 + 1040);
    v64 = (_DWORD *)(*(_QWORD *)(a1 + 1024) + v63);
    v100 = v64;
    *(_DWORD *)(a1 + 1040) = v63 + ((v62 + 3) & 0xFFFFFFFC);
    for ( kk = *(__int64 **)(a1 + 192); kk; kk = (__int64 *)*kk )
    {
      v66 = *((_DWORD *)kk + 6);
      if ( v66 )
      {
        VGrowPackBuffer(a1, v66 + 1);
        memcpy_0(
          (void *)(*(_QWORD *)(a1 + 1024) + *(unsigned int *)(a1 + 1040)),
          (const void *)kk[4],
          *((unsigned int *)kk + 6));
        v64[1] = *(_DWORD *)(a1 + 1040);
        *v64 = *((_DWORD *)kk + 6);
        *(_DWORD *)(a1 + 1040) += (*((_DWORD *)kk + 6) + 4) & 0xFFFFFFFC;
      }
      else
      {
        *(_QWORD *)v64 = 0;
      }
      v64[2] = *((_DWORD *)kk + 4);
      v64 += 3;
      v100 = v64;
    }
  }
  v67 = *(__int64 **)(a1 + 208);
  if ( !v67 || *(_DWORD *)(a1 + 332) == -1 )
  {
    VPackDefaultTrueTypeSubstTable(a1);
  }
  else
  {
    v93 = 0;
    v68 = 1;
    while ( v67 )
    {
      v69 = *((_DWORD *)v67 + 4);
      if ( v69 )
      {
        v70 = v69 + v68;
      }
      else
      {
        v71 = -1;
        do
          ++v71;
        while ( *(_BYTE *)(v67[1] + v71) );
        v70 = v68 + v71;
      }
      v68 = v70 + 2 + *((_DWORD *)v67 + 8);
      v67 = (__int64 *)*v67;
    }
    v72 = 2 * v68;
    VGrowPackBuffer(a1, v72);
    v73 = *(_DWORD *)(a1 + 1040);
    v74 = (WCHAR *)(*(_QWORD *)(a1 + 1024) + v73);
    v93 = v74;
    v75 = v74;
    *(_DWORD *)(*(_QWORD *)(a1 + 1056) + 36LL) = v73;
    *(_DWORD *)(a1 + 1040) += (v72 + 3) & 0xFFFFFFFC;
    for ( mm = *(__int64 **)(a1 + 208); ; mm = (__int64 *)*mm )
    {
      v77 = mm == 0;
      if ( !mm )
        break;
      v78 = *((_DWORD *)mm + 4);
      if ( v78 )
      {
        v79 = ITranslateToUnicodeString(
                v74,
                (*(_QWORD *)(a1 + 1024) + *(unsigned int *)(a1 + 1036) - (unsigned __int64)v74) >> 1,
                (const CHAR *)mm[3],
                v78,
                *(_DWORD *)(a1 + 332));
      }
      else
      {
        v80 = (const CHAR *)mm[1];
        v81 = -1;
        do
          ++v81;
        while ( v80[v81] );
        v95 = v81;
        v103 = v80;
        v101 = (*(_QWORD *)(a1 + 1024) + *(unsigned int *)(a1 + 1036) - (unsigned __int64)v74) >> 1;
        v104 = v74;
        v79 = MultiByteToWideChar(0x4E4u, 0, v80, v81, v74, v81);
        v95 = v79;
      }
      if ( v79 <= 0
        || (v74 += v79 + 1,
            v93 = v74,
            v82 = ITranslateToUnicodeString(
                    v74,
                    ((unsigned __int64)*(unsigned int *)(a1 + 1036) + *(_QWORD *)(a1 + 1024) - (_QWORD)v74) >> 1,
                    (const CHAR *)mm[5],
                    *((_DWORD *)mm + 8),
                    *(_DWORD *)(a1 + 332)),
            v82 <= 0) )
      {
        v77 = mm == 0;
        break;
      }
      v74 += v82 + 1;
      v93 = v74;
    }
    if ( !v77 )
      v74 = v75;
    *v74 = 0;
    v93 = v74 + 1;
    *(_DWORD *)(*(_QWORD *)(a1 + 1056) + 40LL) = 2 * (v74 + 1 - v75);
  }
  VPackStringAnsiToUnicode(a1, v4 + 46, *(const CHAR **)(a1 + 144), *(_DWORD *)(a1 + 136));
  VPackStringUnicode(a1, v4 + 78, *(_WORD **)(a1 + 504));
  *v94 = *(_DWORD *)(a1 + 1040);
  return 1;
}

```

## disassembly

```asm
0x180056d1c  mov     [rsp+arg_8], rbx
0x180056d21  mov     [rsp+arg_10], rsi
0x180056d26  push    rdi
0x180056d27  push    r12
0x180056d29  push    r13
0x180056d2b  push    r14
0x180056d2d  push    r15
0x180056d2f  sub     rsp, 0F0h
0x180056d36  mov     rax, cs:__security_cookie
0x180056d3d  xor     rax, rsp
0x180056d40  mov     [rsp+118h+var_38], rax
0x180056d48  mov     [rsp+118h+var_D4], edx
0x180056d4c  mov     rsi, rcx
0x180056d4f  xor     r15d, r15d
0x180056d52  mov     [rsp+118h+var_B4], r15d
0x180056d57  mov     ebx, 274h
0x180056d5c  mov     edx, ebx
0x180056d5e  call    VGrowPackBuffer
0x180056d63  mov     [rsi+410h], ebx
0x180056d69  mov     rax, [rsi+418h]
0x180056d70  mov     [rsp+118h+var_A8], rax
0x180056d75  mov     r14, [rsi+420h]
0x180056d7c  mov     r13, [rsi+428h]
0x180056d83  mov     [rsp+118h+var_70], r13
0x180056d8b  mov     dword ptr [rax+4], 50504420h
0x180056d92  mov     dword ptr [rax+8], 1A001Eh
0x180056d99  mov     dword ptr [rax+38h], 40h ; '@'
0x180056da0  mov     dword ptr [rax+3Ch], 190h
0x180056da7  mov     [rsp+118h+var_CC], r15d
0x180056dac  mov     rdi, [rsi+418h]
0x180056db3  mov     [rsp+118h+var_D0], r15d
0x180056db8  mov     rax, [rsi+40h]
0x180056dbc  mov     r12d, r15d
0x180056dbf  mov     [rsp+118h+var_D0], r15d
0x180056dc4  mov     r15d, 1
0x180056dca  test    rax, rax
0x180056dcd  jz      short loc_180056DDC
0x180056dcf  mov     rax, [rax]
0x180056dd2  add     r12d, r15d
0x180056dd5  mov     [rsp+118h+var_D0], r12d
0x180056dda  jmp     short loc_180056DCA
0x180056ddc  mov     [rsp+118h+var_CC], r12d
0x180056de1  mov     [rdi+1Ch], r12d
0x180056de5  test    r12d, r12d
0x180056de8  jz      loc_180056EF2
0x180056dee  lea     eax, [r12+r12*2]
0x180056df2  lea     ebx, ds:0[rax*4]
0x180056df9  mov     edx, ebx
0x180056dfb  mov     rcx, rsi
0x180056dfe  call    VGrowPackBuffer
0x180056e03  mov     eax, [rsi+410h]
0x180056e09  mov     [rdi+20h], eax
0x180056e0c  mov     ecx, [rsi+410h]
0x180056e12  mov     r8d, ecx
0x180056e15  add     r8, [rsi+400h]
0x180056e1c  mov     [rsp+118h+var_68], r8
0x180056e24  lea     eax, [rbx+3]
0x180056e27  and     eax, 0FFFFFFFCh
0x180056e2a  add     eax, ecx
0x180056e2c  mov     [rsi+410h], eax
0x180056e32  mov     r13, [rsi+40h]
0x180056e36  or      edi, 0FFFFFFFFh
0x180056e39  test    r13, r13
0x180056e3c  jz      loc_180056EF7
0x180056e42  add     r12d, edi
0x180056e45  mov     [rsp+118h+var_CC], r12d
0x180056e4a  mov     rbx, [r13+8]
0x180056e4e  lea     rdx, [r12+r12*2]
0x180056e52  lea     rdi, [r8+rdx*4]
0x180056e56  mov     r8, rbx
0x180056e59  mov     rdx, rdi
0x180056e5c  mov     rcx, rsi
0x180056e5f  call    VPackStringUnicode
0x180056e64  mov     [rsp+118h+hTemplateFile], 0; hTemplateFile
0x180056e6d  mov     [rsp+118h+dwFlagsAndAttributes], 100080h; dwFlagsAndAttributes
0x180056e75  mov     [rsp+118h+dwCreationDisposition], 3; dwCreationDisposition
0x180056e7d  xor     r9d, r9d; lpSecurityAttributes
0x180056e80  mov     r8d, r15d; dwShareMode
0x180056e83  mov     edx, 80000000h; dwDesiredAccess
0x180056e88  mov     rcx, rbx; lpFileName
0x180056e8b  call    cs:__imp_CreateFileW
0x180056e92  nop     dword ptr [rax+rax+00h]
0x180056e97  mov     rbx, rax
0x180056e9a  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180056e9e  jz      short loc_180056EBC
0x180056ea0  lea     r9, [rdi+4]; lpLastWriteTime
0x180056ea4  xor     r8d, r8d; lpLastAccessTime
0x180056ea7  xor     edx, edx; lpCreationTime
0x180056ea9  mov     rcx, rax; hFile
0x180056eac  call    cs:__imp_GetFileTime
0x180056eb3  nop     dword ptr [rax+rax+00h]
0x180056eb8  test    eax, eax
0x180056eba  jnz     short loc_180056ECC
0x180056ebc  lea     rcx, [rdi+4]; lpSystemTimeAsFileTime
0x180056ec0  call    cs:__imp_GetSystemTimeAsFileTime
0x180056ec7  nop     dword ptr [rax+rax+00h]
0x180056ecc  cmp     rbx, 0FFFFFFFFFFFFFFFFh
0x180056ed0  jz      short loc_180056EE1
0x180056ed2  mov     rcx, rbx; hObject
0x180056ed5  call    cs:__imp_CloseHandle
0x180056edc  nop     dword ptr [rax+rax+00h]
0x180056ee1  mov     r13, [r13+0]
0x180056ee5  mov     r8, [rsp+118h+var_68]
0x180056eed  jmp     loc_180056E36
0x180056ef2  or      edi, 0FFFFFFFFh
0x180056ef5  jmp     short loc_180056EFF
0x180056ef7  mov     r13, [rsp+118h+var_70]
0x180056eff  xor     r12d, r12d
0x180056f02  cmp     [rsi+30h], r12
0x180056f06  jz      short loc_180056F0C
0x180056f08  mov     [rsi+28h], r15d
0x180056f0c  cmp     [rsi+3Ch], r12d
0x180056f10  jz      short loc_180056F16
0x180056f12  mov     [rsi+28h], r15d
0x180056f16  cmp     [rsi+48h], r12d
0x180056f1a  jnz     short loc_180056F20
0x180056f1c  mov     [rsi+28h], r15d
0x180056f20  cmp     [rsi+78h], r12d
0x180056f24  jnz     short loc_180056F2A
0x180056f26  mov     [rsi+28h], r15d
0x180056f2a  cmp     [rsi+60h], r12d
0x180056f2e  jnz     short loc_180056F34
0x180056f30  mov     [rsi+28h], r15d
0x180056f34  mov     ecx, [rsi+150h]
0x180056f3a  test    ecx, ecx
0x180056f3c  jnz     short loc_180056F4C
0x180056f3e  mov     [rsi+28h], r15d
0x180056f42  mov     [rsi+150h], r15d
0x180056f49  mov     ecx, r15d
0x180056f4c  mov     eax, 2B000h
0x180056f51  mov     edx, 3E400h
0x180056f56  cmp     ecx, r15d
0x180056f59  cmova   eax, edx
0x180056f5c  cmp     [rsi+154h], eax
0x180056f62  jnb     short loc_180056F6E
0x180056f64  mov     [rsi+28h], r15d
0x180056f68  mov     [rsi+154h], eax
0x180056f6e  mov     ebx, r12d
0x180056f71  mov     [rsp+118h+var_D8], ebx
0x180056f75  xorps   xmm0, xmm0
0x180056f78  xor     eax, eax
0x180056f7a  movups  xmmword ptr [rsp+118h+CPInfo.MaxCharSize], xmm0
0x180056f82  mov     dword ptr [rsp+118h+CPInfo.LeadByte+0Ah], eax
0x180056f89  mov     ecx, [rsi+148h]
0x180056f8f  test    ecx, ecx
0x180056f91  jz      short loc_180056FBD
0x180056f93  sub     ecx, r15d
0x180056f96  jz      short loc_180056FB4
0x180056f98  sub     ecx, r15d
0x180056f9b  jz      short loc_180056FAD
0x180056f9d  cmp     ecx, r15d
0x180056fa0  jnz     short loc_180056FBD
0x180056fa2  mov     ebx, 3A4h
0x180056fa7  mov     [rsp+118h+var_D8], ebx
0x180056fab  jmp     short loc_180056FC7
0x180056fad  mov     ebx, 0FFFFFFFEh
0x180056fb2  jmp     short loc_180056FE2
0x180056fb4  mov     ebx, 4E4h
0x180056fb9  mov     [rsp+118h+var_D8], ebx
0x180056fbd  lea     eax, [rbx+2]
0x180056fc0  test    eax, 0FFFFFFFDh
0x180056fc5  jz      short loc_180056FE6
0x180056fc7  lea     rdx, [rsp+118h+CPInfo]; lpCPInfo
0x180056fcf  mov     ecx, ebx; CodePage
0x180056fd1  call    cs:__imp_GetCPInfo
0x180056fd8  nop     dword ptr [rax+rax+00h]
0x180056fdd  test    eax, eax
0x180056fdf  cmovz   ebx, edi
0x180056fe2  mov     [rsp+118h+var_D8], ebx
0x180056fe6  mov     [rsi+14Ch], ebx
0x180056fec  mov     [rsp+118h+var_90], r12
0x180056ff4  mov     [rsp+118h+var_98], r12
0x180056ffc  mov     [rsp+118h+var_C4], r12d
0x180057001  mov     [rsp+118h+var_C8], r12d
0x180057006  mov     rcx, r12
0x180057009  mov     [rsp+118h+var_98], rcx
0x180057011  mov     rdx, r12
0x180057014  mov     [rsp+118h+var_90], rdx
0x18005701c  mov     r9d, r12d
0x18005701f  mov     [rsp+118h+var_C8], r12d
0x180057024  mov     r10d, r12d
0x180057027  mov     [rsp+118h+var_C4], r12d
0x18005702c  mov     rax, [rsi+98h]
0x180057033  test    rax, rax
0x180057036  jz      short loc_180057074
0x180057038  mov     r8, [rax]
0x18005703b  cmp     [rax+34h], r12d
0x18005703f  jz      short loc_180057059
0x180057041  mov     [rax], rcx
0x180057044  mov     rcx, rax
0x180057047  mov     [rsp+118h+var_98], rax
0x18005704f  add     r9d, r15d
0x180057052  mov     [rsp+118h+var_C8], r9d
0x180057057  jmp     short loc_18005706F
0x180057059  mov     [rax], rdx
0x18005705c  mov     rdx, rax
0x18005705f  mov     [rsp+118h+var_90], rax
0x180057067  add     r10d, r15d
0x18005706a  mov     [rsp+118h+var_C4], r10d
0x18005706f  mov     rax, r8
0x180057072  jmp     short loc_180057033
0x180057074  mov     r8, r12
0x180057077  test    rcx, rcx
0x18005707a  jz      short loc_180057092
0x18005707c  mov     rax, [rcx]
0x18005707f  mov     [rcx], r8
0x180057082  mov     r8, rcx
0x180057085  mov     rcx, rax
0x180057088  mov     [rsp+118h+var_98], rax
0x180057090  jmp     short loc_180057077
0x180057092  test    rdx, rdx
0x180057095  jz      short loc_1800570AD
0x180057097  mov     rax, [rdx]
0x18005709a  mov     [rdx], r8
0x18005709d  mov     r8, rdx
0x1800570a0  mov     rdx, rax
0x1800570a3  mov     [rsp+118h+var_90], rax
0x1800570ab  jmp     short loc_180057092
0x1800570ad  mov     [rsi+98h], r8
0x1800570b4  mov     rax, [rsi+418h]
0x1800570bb  mov     [rax+14h], r10d
0x1800570bf  mov     rax, [rsi+418h]
0x1800570c6  mov     [rax+18h], r9d
0x1800570ca  cmp     [rsp+118h+var_D4], r12d
0x1800570cf  jz      short loc_1800570DD
0x1800570d1  mov     [r14+12Ch], r15d
0x1800570d8  mov     ecx, r15d
0x1800570db  jmp     short loc_1800570EA
0x1800570dd  mov     ecx, [rsi+1ECh]
0x1800570e3  mov     [r14+12Ch], ecx
0x1800570ea  mov     dword ptr [r14], 150h
0x1800570f1  mov     rdx, [rsp+118h+var_A8]
0x1800570f6  mov     eax, [rdx+14h]
0x1800570f9  mov     [r14+18h], eax
0x1800570fd  mov     eax, [rdx+18h]
0x180057100  mov     [r14+1Ch], eax
0x180057104  mov     dword ptr [r14+14h], 2
0x18005710c  test    ecx, ecx
0x18005710e  jnz     short loc_18005711A
0x180057110  mov     dword ptr [r14+3Ch], 270Fh
0x180057118  jmp     short loc_18005712C
0x18005711a  mov     ecx, [rsi+1F0h]
0x180057120  mov     eax, r15d
0x180057123  test    ecx, ecx
0x180057125  cmovnz  eax, ecx
0x180057128  mov     [r14+3Ch], eax
0x18005712c  mov     [r14+44h], r15d
0x180057130  mov     dword ptr [r14+48h], 3E8h
0x180057138  mov     eax, [rsi+60h]
0x18005713b  mov     [r14+10h], eax
0x18005713f  mov     eax, [rsi+148h]
0x180057145  mov     [r14+4Ch], eax
0x180057149  mov     eax, [rsi+150h]
0x18005714f  mov     [r14+50h], eax
0x180057153  mov     eax, [rsi+158h]
0x180057159  mov     [r14+80h], eax
0x180057160  mov     [r14+78h], eax
0x180057164  mov     [r14+7Ch], r15d
0x180057168  mov     eax, [rsi+204h]
0x18005716e  test    eax, eax
0x180057170  jnz     short loc_18005717B
0x180057172  cmp     [rsi+208h], r12d
0x180057179  jz      short loc_1800571A9
0x18005717b  cmp     eax, 4
0x18005717e  jb      short loc_1800571A5
0x180057180  mov     ecx, [rsi+208h]
0x180057186  cmp     ecx, 0Fh
0x180057189  ja      short loc_1800571A5
0x18005718b  cmp     eax, ecx
0x18005718d  ja      short loc_1800571A5
0x18005718f  mov     [r14+130h], eax
0x180057196  mov     eax, [rsi+208h]
0x18005719c  mov     [r14+134h], eax
0x1800571a3  jmp     short loc_1800571A9
0x1800571a5  mov     [rsi+28h], r15d
0x1800571a9  mov     eax, [rsi+168h]
0x1800571af  or      eax, 10h
0x1800571b2  mov     [r14+64h], eax
0x1800571b6  mov     eax, [rsi+15Ch]
0x1800571bc  mov     [r14+68h], eax
0x1800571c0  mov     eax, [rsi+160h]
0x1800571c6  mov     [r14+6Ch], eax
0x1800571ca  mov     eax, [rsi+16Ch]
0x1800571d0  mov     [r14+70h], eax
0x1800571d4  mov     eax, [rsi+154h]
0x1800571da  mov     [r14+74h], eax
0x1800571de  mov     eax, [rsi+17Ch]
0x1800571e4  mov     [r14+84h], eax
0x1800571eb  mov     eax, [rsi+178h]
0x1800571f1  mov     [r14+88h], eax
0x1800571f8  mov     dword ptr [r14+90h], 0FFh
0x180057203  mov     eax, [rsi+5Ch]
0x180057206  mov     [r13+10h], eax
0x18005720a  mov     eax, [rsi+194h]
0x180057210  mov     [r13+4], eax
0x180057214  mov     eax, 6338h
0x180057219  mov     [r14+0B0h], eax
0x180057220  mov     [r14+0ACh], eax
0x180057227  mov     eax, 12h
0x18005722c  mov     [r14+8Ch], eax
  ... truncated ...
```
