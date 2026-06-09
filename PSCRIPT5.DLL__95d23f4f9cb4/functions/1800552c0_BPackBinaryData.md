# BPackBinaryData

- ea: `0x1800552c0`
- end: `0x180056180`
- name: `BPackBinaryData`
- size: `3776`
- prototype: ``
- caller_count: `1`
- callee_count: `18`
- tags: `file_ops`

## callers

- `0x1800564d8`

## callees

- `0x180001ee0`
- `0x1800552c0`
- `0x180056450`
- `0x180056744`
- `0x1800567e4`
- `0x180056948`
- `0x180056d0c`
- `0x180056d98`
- `0x180056f4c`
- `0x180057310`
- `0x180057cc4`
- `0x180057d38`
- `0x180057e68`
- `0x180057ee0`
- `0x180057f44`
- `0x180058444`
- `0x18005c404`
- `0x18005c434`

## import_xrefs

- `KERNEL32!MultiByteToWideChar` at `0x180056068`
- `KERNEL32!MultiByteToWideChar` at `0x180056068`
- `KERNEL32!GetCPInfo` at `0x18005555d`
- `KERNEL32!GetCPInfo` at `0x18005555d`
- `KERNEL32!GetFileTime` at `0x18005544a`
- `KERNEL32!GetFileTime` at `0x18005544a`
- `KERNEL32!GetSystemTimeAsFileTime` at `0x180055458`
- `KERNEL32!GetSystemTimeAsFileTime` at `0x180055458`
- `KERNEL32!HeapAlloc` at `0x180055aa6`
- `KERNEL32!HeapAlloc` at `0x180055ae6`
- `KERNEL32!HeapAlloc` at `0x180055aa6`
- `KERNEL32!HeapAlloc` at `0x180055ae6`
- `KERNEL32!CreateFileW` at `0x18005542f`
- `KERNEL32!CreateFileW` at `0x18005542f`
- `KERNEL32!CloseHandle` at `0x180055467`
- `KERNEL32!CloseHandle` at `0x180055467`
- `KERNEL32!RaiseException` at `0x180055ac1`
- `KERNEL32!RaiseException` at `0x180055b01`
- `KERNEL32!RaiseException` at `0x180055ac1`
- `KERNEL32!RaiseException` at `0x180055b01`

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
  const WCHAR *v12; // rbx
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
  __int64 v38; // r8
  __int64 v39; // r8
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
  __int64 v57; // rdi
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
  int v78; // eax
  const CHAR *v79; // r8
  __int64 v80; // r9
  int v81; // eax
  int v83; // [rsp+44h] [rbp-D4h] BYREF
  int v84; // [rsp+48h] [rbp-D0h]
  int v85; // [rsp+4Ch] [rbp-CCh]
  int v86; // [rsp+50h] [rbp-C8h]
  int v87; // [rsp+54h] [rbp-C4h]
  int v88; // [rsp+58h] [rbp-C0h]
  int v89; // [rsp+5Ch] [rbp-BCh]
  int v90; // [rsp+60h] [rbp-B8h]
  int v91; // [rsp+64h] [rbp-B4h]
  WCHAR *v92; // [rsp+68h] [rbp-B0h]
  _DWORD *v93; // [rsp+70h] [rbp-A8h]
  int v94; // [rsp+78h] [rbp-A0h]
  _QWORD *v95; // [rsp+80h] [rbp-98h]
  _QWORD *v96; // [rsp+88h] [rbp-90h]
  _DWORD *v97; // [rsp+90h] [rbp-88h]
  __int64 v98; // [rsp+98h] [rbp-80h]
  _DWORD *v99; // [rsp+A0h] [rbp-78h]
  unsigned __int64 v100; // [rsp+A8h] [rbp-70h]
  __int64 v101; // [rsp+B0h] [rbp-68h]
  const CHAR *v102; // [rsp+B8h] [rbp-60h]
  WCHAR *v103; // [rsp+C0h] [rbp-58h]
  _cpinfo CPInfo; // [rsp+C8h] [rbp-50h] BYREF

  v83 = a2;
  v91 = 0;
  VGrowPackBuffer(a1, 628);
  *(_DWORD *)(a1 + 1040) = 628;
  v3 = *(_DWORD **)(a1 + 1048);
  v93 = v3;
  v4 = *(_DWORD **)(a1 + 1056);
  v5 = *(_QWORD *)(a1 + 1064);
  v100 = v5;
  v3[1] = 1347437600;
  v3[2] = 1703966;
  v3[14] = 64;
  v3[15] = 400;
  v85 = 0;
  v6 = *(_QWORD *)(a1 + 1048);
  v84 = 0;
  v7 = *(_QWORD **)(a1 + 64);
  LODWORD(v8) = 0;
  v84 = 0;
  while ( v7 )
  {
    v7 = (_QWORD *)*v7;
    LODWORD(v8) = v8 + 1;
    v84 = v8;
  }
  v85 = v8;
  *(_DWORD *)(v6 + 28) = v8;
  if ( (_DWORD)v8 )
  {
    VGrowPackBuffer(a1, (unsigned int)(12 * v8));
    *(_DWORD *)(v6 + 32) = *(_DWORD *)(a1 + 1040);
    v9 = *(_DWORD *)(a1 + 1040);
    v10 = *(_QWORD *)(a1 + 1024) + v9;
    v101 = v10;
    *(_DWORD *)(a1 + 1040) = v9 + ((12 * v8 + 3) & 0xFFFFFFFC);
    v11 = *(_QWORD **)(a1 + 64);
    while ( v11 )
    {
      v8 = (unsigned int)(v8 - 1);
      v85 = v8;
      v12 = (const WCHAR *)v11[1];
      v13 = v10 + 12 * v8;
      VPackStringUnicode(a1, v13, v12);
      FileW = CreateFileW(v12, 0x80000000, 1u, 0, 3u, 0x100080u, 0);
      v15 = FileW;
      if ( FileW == (HANDLE)-1LL || !GetFileTime(FileW, 0, 0, (LPFILETIME)(v13 + 4)) )
        GetSystemTimeAsFileTime((LPFILETIME)(v13 + 4));
      if ( v15 != (void *)-1LL )
        CloseHandle(v15);
      v11 = (_QWORD *)*v11;
      v10 = v101;
    }
    v5 = v100;
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
  v95 = 0;
  v23 = 0;
  v96 = 0;
  v24 = 0;
  v86 = 0;
  v25 = 0;
  v87 = 0;
  for ( i = *(__int64 **)(a1 + 152); i; i = v27 )
  {
    v27 = (__int64 *)*i;
    if ( *((_DWORD *)i + 13) )
    {
      *i = (__int64)v22;
      v22 = i;
      v95 = i;
      v86 = ++v24;
    }
    else
    {
      *i = (__int64)v23;
      v23 = i;
      v96 = i;
      v87 = ++v25;
    }
  }
  v28 = 0;
  while ( v22 )
  {
    v29 = (_QWORD *)*v22;
    *v22 = v28;
    v28 = v22;
    v22 = v29;
    v95 = v29;
  }
  while ( v23 )
  {
    v30 = (_QWORD *)*v23;
    *v23 = v28;
    v28 = v23;
    v23 = v30;
    v96 = v30;
  }
  *(_QWORD *)(a1 + 152) = v28;
  *(_DWORD *)(*(_QWORD *)(a1 + 1048) + 20LL) = v25;
  *(_DWORD *)(*(_QWORD *)(a1 + 1048) + 24LL) = v24;
  if ( v83 )
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
  v32 = v93;
  v4[6] = v93[5];
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
  if ( PvFindListItem(*(_QWORD *)(a1 + 152), "StapleLocation", 0)
    || PvFindListItem(*(_QWORD *)(a1 + 152), "StapleX", v38) && PvFindListItem(*(_QWORD *)(a1 + 152), "StapleY", v39) )
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
  VPackStringAnsiToUnicode(a1, v4 + 3, *(_QWORD *)(a1 + 80), *(unsigned int *)(a1 + 72));
  for ( j = *(__int64 **)(a1 + 200); j; j = (__int64 *)*j )
  {
    v41 = *((_DWORD *)j + 4);
    if ( v41 )
    {
      VGrowPackBuffer(a1, (unsigned int)(v41 + 1));
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
    VResolveSymbolInvocation(a1, k + 8);
    for ( m = (_QWORD *)k[11]; m; m = (_QWORD *)*m )
      VResolveSymbolInvocation(a1, m + 4);
  }
  for ( n = *(_QWORD **)(a1 + 192); n; n = (_QWORD *)*n )
    VResolveSymbolInvocation(a1, n + 3);
  VPackInvocation(a1, v4 + 21, a1 + 216);
  VPackInvocation(a1, v4 + 23, a1 + 232);
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
  VPackOrderDependency(a1, v5 + 196, *(_QWORD *)(a1 + 168));
  VPackOrderDependency(a1, v5 + 204, *(_QWORD *)(a1 + 176));
  VPackPrinterFeatures(a1);
  *(_DWORD *)v5 = 228;
  *(_DWORD *)(v5 + 8) = *(_DWORD *)(a1 + 392);
  *(_DWORD *)(v5 + 12) = *(_DWORD *)(a1 + 396);
  *(_DWORD *)(v5 + 20) = *(_DWORD *)(a1 + 100);
  *(_DWORD *)(v5 + 224) = *(_DWORD *)(a1 + 372);
  v97 = 0;
  v88 = 0;
  *(_DWORD *)(v5 + 40) = -1;
  v48 = v93;
  if ( v4[8] )
    v49 = (_DWORD *)((char *)v93 + (unsigned int)v4[8]);
  else
    v49 = 0;
  v50 = 0;
  v88 = 0;
  while ( 1 )
  {
    v97 = v49;
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
    v88 = ++v50;
    v49 += 21;
    v48 = v93;
  }
  VPackInvocation(a1, v5 + 24, a1 + 104);
  VPackInvocation(a1, v5 + 32, a1 + 120);
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
  VPackInvocation(a1, v5 + 144, a1 + 248);
  VPackInvocation(a1, v5 + 152, a1 + 264);
  VPackInvocation(a1, v5 + 160, a1 + 280);
  VPackInvocation(a1, v5 + 168, a1 + 296);
  VPackInvocation(a1, v5 + 176, a1 + 312);
  VPackNt4Mapping(a1);
  v98 = 0;
  v83 = 0;
  v89 = 0;
  v53 = *(_QWORD **)(a1 + 184);
  v54 = 0;
  v89 = 0;
  while ( v53 )
  {
    v53 = (_QWORD *)*v53;
    v89 = ++v54;
  }
  if ( v54 )
  {
    v55 = 24 * v54;
    VGrowPackBuffer(a1, (unsigned int)(24 * v54));
    *(_DWORD *)(*(_QWORD *)(a1 + 1064) + 188LL) = v54;
    *(_DWORD *)(*(_QWORD *)(a1 + 1064) + 192LL) = *(_DWORD *)(a1 + 1040);
    v56 = *(_DWORD *)(a1 + 1040);
    v57 = *(_QWORD *)(a1 + 1024) + v56;
    v98 = v57;
    *(_DWORD *)(a1 + 1040) = v56 + ((v55 + 3) & 0xFFFFFFFC);
    for ( jj = *(__int64 **)(a1 + 184); jj; jj = (__int64 *)*jj )
    {
      VPackStringAnsi(a1, v57, jj[1]);
      VPackStringXlation(a1, v57 + 4, jj[1], jj + 2);
      VPackStringAnsi(a1, v57 + 8, jj[4]);
      VPackStringAnsi(a1, v57 + 12, jj[5]);
      VPackStringAnsi(a1, v57 + 16, jj[6]);
      *(_DWORD *)(v57 + 20) = *((_DWORD *)jj + 14);
      v57 += 24;
      v98 = v57;
    }
    v59 = *(_QWORD *)(a1 + 408);
    if ( v59 )
    {
      if ( PvFindListItem(*(_QWORD *)(a1 + 184), v59, &v83) )
        *(_DWORD *)(*(_QWORD *)(a1 + 1064) + 184LL) = *(_DWORD *)(*(_QWORD *)(a1 + 1064) + 192LL) + 24 * v83;
    }
  }
  v99 = 0;
  v90 = 0;
  v60 = *(_QWORD **)(a1 + 192);
  v61 = 0;
  v90 = 0;
  while ( v60 )
  {
    v60 = (_QWORD *)*v60;
    v90 = ++v61;
  }
  if ( v61 )
  {
    v62 = 12 * v61;
    VGrowPackBuffer(a1, (unsigned int)(12 * v61));
    *(_DWORD *)(*(_QWORD *)(a1 + 1064) + 212LL) = v61;
    *(_DWORD *)(*(_QWORD *)(a1 + 1064) + 216LL) = *(_DWORD *)(a1 + 1040);
    v63 = *(_DWORD *)(a1 + 1040);
    v64 = (_DWORD *)(*(_QWORD *)(a1 + 1024) + v63);
    v99 = v64;
    *(_DWORD *)(a1 + 1040) = v63 + ((v62 + 3) & 0xFFFFFFFC);
    for ( kk = *(__int64 **)(a1 + 192); kk; kk = (__int64 *)*kk )
    {
      v66 = *((_DWORD *)kk + 6);
      if ( v66 )
      {
        VGrowPackBuffer(a1, (unsigned int)(v66 + 1));
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
      v99 = v64;
    }
  }
  v67 = *(__int64 **)(a1 + 208);
  if ( !v67 || *(_DWORD *)(a1 + 332) == -1 )
  {
    VPackDefaultTrueTypeSubstTable(a1);
  }
  else
  {
    v92 = 0;
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
    v92 = v74;
    v75 = v74;
    *(_DWORD *)(*(_QWORD *)(a1 + 1056) + 36LL) = v73;
    *(_DWORD *)(a1 + 1040) += (v72 + 3) & 0xFFFFFFFC;
    for ( mm = *(__int64 **)(a1 + 208); ; mm = (__int64 *)*mm )
    {
      v77 = mm == 0;
      if ( !mm )
        break;
      if ( *((_DWORD *)mm + 4) )
      {
        v78 = ITranslateToUnicodeString(v74, *(_DWORD *)(a1 + 332));
      }
      else
      {
        v79 = (const CHAR *)mm[1];
        v80 = -1;
        do
          ++v80;
        while ( v79[v80] );
        v94 = v80;
        v102 = v79;
        v100 = (*(_QWORD *)(a1 + 1024) + *(unsigned int *)(a1 + 1036) - (unsigned __int64)v74) >> 1;
        v103 = v74;
        v78 = MultiByteToWideChar(0x4E4u, 0, v79, v80, v74, v80);
        v94 = v78;
      }
      if ( v78 <= 0
        || (v74 += v78 + 1, v92 = v74, v81 = ITranslateToUnicodeString(v74, *(_DWORD *)(a1 + 332)), v81 <= 0) )
      {
        v77 = mm == 0;
        break;
      }
      v74 += v81 + 1;
      v92 = v74;
    }
    if ( !v77 )
      v74 = v75;
    *v74 = 0;
    v92 = v74 + 1;
    *(_DWORD *)(*(_QWORD *)(a1 + 1056) + 40LL) = 2 * (v74 + 1 - v75);
  }
  VPackStringAnsiToUnicode(a1, v4 + 46, *(_QWORD *)(a1 + 144), *(unsigned int *)(a1 + 136));
  VPackStringUnicode(a1, v4 + 78, *(_QWORD *)(a1 + 504));
  *v93 = *(_DWORD *)(a1 + 1040);
  return 1;
}

```

## disassembly

```asm
0x1800552c0  mov     [rsp+arg_8], rbx
0x1800552c5  mov     [rsp+arg_10], rsi
0x1800552ca  push    rdi
0x1800552cb  push    r12
0x1800552cd  push    r13
0x1800552cf  push    r14
0x1800552d1  push    r15
0x1800552d3  sub     rsp, 0F0h
0x1800552da  mov     rax, cs:__security_cookie
0x1800552e1  xor     rax, rsp
0x1800552e4  mov     [rsp+118h+var_38], rax
0x1800552ec  mov     [rsp+118h+var_D4], edx
0x1800552f0  mov     rsi, rcx
0x1800552f3  xor     r15d, r15d
0x1800552f6  mov     [rsp+118h+var_B4], r15d
0x1800552fb  mov     ebx, 274h
0x180055300  mov     edx, ebx
0x180055302  call    VGrowPackBuffer
0x180055307  mov     [rsi+410h], ebx
0x18005530d  mov     rax, [rsi+418h]
0x180055314  mov     [rsp+118h+var_A8], rax
0x180055319  mov     r14, [rsi+420h]
0x180055320  mov     r13, [rsi+428h]
0x180055327  mov     [rsp+118h+var_70], r13
0x18005532f  mov     dword ptr [rax+4], 50504420h
0x180055336  mov     dword ptr [rax+8], 1A001Eh
0x18005533d  mov     dword ptr [rax+38h], 40h ; '@'
0x180055344  mov     dword ptr [rax+3Ch], 190h
0x18005534b  mov     [rsp+118h+var_CC], r15d
0x180055350  mov     rdi, [rsi+418h]
0x180055357  mov     [rsp+118h+var_D0], r15d
0x18005535c  mov     rax, [rsi+40h]
0x180055360  mov     r12d, r15d
0x180055363  mov     [rsp+118h+var_D0], r15d
0x180055368  mov     r15d, 1
0x18005536e  test    rax, rax
0x180055371  jz      short loc_180055380
0x180055373  mov     rax, [rax]
0x180055376  add     r12d, r15d
0x180055379  mov     [rsp+118h+var_D0], r12d
0x18005537e  jmp     short loc_18005536E
0x180055380  mov     [rsp+118h+var_CC], r12d
0x180055385  mov     [rdi+1Ch], r12d
0x180055389  test    r12d, r12d
0x18005538c  jz      loc_18005547E
0x180055392  lea     eax, [r12+r12*2]
0x180055396  lea     ebx, ds:0[rax*4]
0x18005539d  mov     edx, ebx
0x18005539f  mov     rcx, rsi
0x1800553a2  call    VGrowPackBuffer
0x1800553a7  mov     eax, [rsi+410h]
0x1800553ad  mov     [rdi+20h], eax
0x1800553b0  mov     ecx, [rsi+410h]
0x1800553b6  mov     r8d, ecx
0x1800553b9  add     r8, [rsi+400h]
0x1800553c0  mov     [rsp+118h+var_68], r8
0x1800553c8  lea     eax, [rbx+3]
0x1800553cb  and     eax, 0FFFFFFFCh
0x1800553ce  add     eax, ecx
0x1800553d0  mov     [rsi+410h], eax
0x1800553d6  mov     r13, [rsi+40h]
0x1800553da  or      edi, 0FFFFFFFFh
0x1800553dd  test    r13, r13
0x1800553e0  jz      loc_180055483
0x1800553e6  add     r12d, edi
0x1800553e9  mov     [rsp+118h+var_CC], r12d
0x1800553ee  mov     rbx, [r13+8]
0x1800553f2  lea     rdx, [r12+r12*2]
0x1800553f6  lea     rdi, [r8+rdx*4]
0x1800553fa  mov     r8, rbx
0x1800553fd  mov     rdx, rdi
0x180055400  mov     rcx, rsi
0x180055403  call    VPackStringUnicode
0x180055408  mov     [rsp+118h+hTemplateFile], 0; hTemplateFile
0x180055411  mov     [rsp+118h+dwFlagsAndAttributes], 100080h; dwFlagsAndAttributes
0x180055419  mov     [rsp+118h+dwCreationDisposition], 3; dwCreationDisposition
0x180055421  xor     r9d, r9d; lpSecurityAttributes
0x180055424  mov     r8d, r15d; dwShareMode
0x180055427  mov     edx, 80000000h; dwDesiredAccess
0x18005542c  mov     rcx, rbx; lpFileName
0x18005542f  call    cs:__imp_CreateFileW
0x180055435  mov     rbx, rax
0x180055438  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18005543c  jz      short loc_180055454
0x18005543e  lea     r9, [rdi+4]; lpLastWriteTime
0x180055442  xor     r8d, r8d; lpLastAccessTime
0x180055445  xor     edx, edx; lpCreationTime
0x180055447  mov     rcx, rax; hFile
0x18005544a  call    cs:__imp_GetFileTime
0x180055450  test    eax, eax
0x180055452  jnz     short loc_18005545E
0x180055454  lea     rcx, [rdi+4]; lpSystemTimeAsFileTime
0x180055458  call    cs:__imp_GetSystemTimeAsFileTime
0x18005545e  cmp     rbx, 0FFFFFFFFFFFFFFFFh
0x180055462  jz      short loc_18005546D
0x180055464  mov     rcx, rbx; hObject
0x180055467  call    cs:__imp_CloseHandle
0x18005546d  mov     r13, [r13+0]
0x180055471  mov     r8, [rsp+118h+var_68]
0x180055479  jmp     loc_1800553DA
0x18005547e  or      edi, 0FFFFFFFFh
0x180055481  jmp     short loc_18005548B
0x180055483  mov     r13, [rsp+118h+var_70]
0x18005548b  xor     r12d, r12d
0x18005548e  cmp     [rsi+30h], r12
0x180055492  jz      short loc_180055498
0x180055494  mov     [rsi+28h], r15d
0x180055498  cmp     [rsi+3Ch], r12d
0x18005549c  jz      short loc_1800554A2
0x18005549e  mov     [rsi+28h], r15d
0x1800554a2  cmp     [rsi+48h], r12d
0x1800554a6  jnz     short loc_1800554AC
0x1800554a8  mov     [rsi+28h], r15d
0x1800554ac  cmp     [rsi+78h], r12d
0x1800554b0  jnz     short loc_1800554B6
0x1800554b2  mov     [rsi+28h], r15d
0x1800554b6  cmp     [rsi+60h], r12d
0x1800554ba  jnz     short loc_1800554C0
0x1800554bc  mov     [rsi+28h], r15d
0x1800554c0  mov     ecx, [rsi+150h]
0x1800554c6  test    ecx, ecx
0x1800554c8  jnz     short loc_1800554D8
0x1800554ca  mov     [rsi+28h], r15d
0x1800554ce  mov     [rsi+150h], r15d
0x1800554d5  mov     ecx, r15d
0x1800554d8  mov     eax, 2B000h
0x1800554dd  mov     edx, 3E400h
0x1800554e2  cmp     ecx, r15d
0x1800554e5  cmova   eax, edx
0x1800554e8  cmp     [rsi+154h], eax
0x1800554ee  jnb     short loc_1800554FA
0x1800554f0  mov     [rsi+28h], r15d
0x1800554f4  mov     [rsi+154h], eax
0x1800554fa  mov     ebx, r12d
0x1800554fd  mov     [rsp+118h+var_D8], ebx
0x180055501  xorps   xmm0, xmm0
0x180055504  xor     eax, eax
0x180055506  movups  xmmword ptr [rsp+118h+CPInfo.MaxCharSize], xmm0
0x18005550e  mov     dword ptr [rsp+118h+CPInfo.LeadByte+0Ah], eax
0x180055515  mov     ecx, [rsi+148h]
0x18005551b  test    ecx, ecx
0x18005551d  jz      short loc_180055549
0x18005551f  sub     ecx, r15d
0x180055522  jz      short loc_180055540
0x180055524  sub     ecx, r15d
0x180055527  jz      short loc_180055539
0x180055529  cmp     ecx, r15d
0x18005552c  jnz     short loc_180055549
0x18005552e  mov     ebx, 3A4h
0x180055533  mov     [rsp+118h+var_D8], ebx
0x180055537  jmp     short loc_180055553
0x180055539  mov     ebx, 0FFFFFFFEh
0x18005553e  jmp     short loc_180055568
0x180055540  mov     ebx, 4E4h
0x180055545  mov     [rsp+118h+var_D8], ebx
0x180055549  lea     eax, [rbx+2]
0x18005554c  test    eax, 0FFFFFFFDh
0x180055551  jz      short loc_18005556C
0x180055553  lea     rdx, [rsp+118h+CPInfo]; lpCPInfo
0x18005555b  mov     ecx, ebx; CodePage
0x18005555d  call    cs:__imp_GetCPInfo
0x180055563  test    eax, eax
0x180055565  cmovz   ebx, edi
0x180055568  mov     [rsp+118h+var_D8], ebx
0x18005556c  mov     [rsi+14Ch], ebx
0x180055572  mov     [rsp+118h+var_90], r12
0x18005557a  mov     [rsp+118h+var_98], r12
0x180055582  mov     [rsp+118h+var_C4], r12d
0x180055587  mov     [rsp+118h+var_C8], r12d
0x18005558c  mov     rcx, r12
0x18005558f  mov     [rsp+118h+var_98], rcx
0x180055597  mov     rdx, r12
0x18005559a  mov     [rsp+118h+var_90], rdx
0x1800555a2  mov     r9d, r12d
0x1800555a5  mov     [rsp+118h+var_C8], r12d
0x1800555aa  mov     r10d, r12d
0x1800555ad  mov     [rsp+118h+var_C4], r12d
0x1800555b2  mov     rax, [rsi+98h]
0x1800555b9  test    rax, rax
0x1800555bc  jz      short loc_1800555FA
0x1800555be  mov     r8, [rax]
0x1800555c1  cmp     [rax+34h], r12d
0x1800555c5  jz      short loc_1800555DF
0x1800555c7  mov     [rax], rcx
0x1800555ca  mov     rcx, rax
0x1800555cd  mov     [rsp+118h+var_98], rax
0x1800555d5  add     r9d, r15d
0x1800555d8  mov     [rsp+118h+var_C8], r9d
0x1800555dd  jmp     short loc_1800555F5
0x1800555df  mov     [rax], rdx
0x1800555e2  mov     rdx, rax
0x1800555e5  mov     [rsp+118h+var_90], rax
0x1800555ed  add     r10d, r15d
0x1800555f0  mov     [rsp+118h+var_C4], r10d
0x1800555f5  mov     rax, r8
0x1800555f8  jmp     short loc_1800555B9
0x1800555fa  mov     r8, r12
0x1800555fd  test    rcx, rcx
0x180055600  jz      short loc_180055618
0x180055602  mov     rax, [rcx]
0x180055605  mov     [rcx], r8
0x180055608  mov     r8, rcx
0x18005560b  mov     rcx, rax
0x18005560e  mov     [rsp+118h+var_98], rax
0x180055616  jmp     short loc_1800555FD
0x180055618  test    rdx, rdx
0x18005561b  jz      short loc_180055633
0x18005561d  mov     rax, [rdx]
0x180055620  mov     [rdx], r8
0x180055623  mov     r8, rdx
0x180055626  mov     rdx, rax
0x180055629  mov     [rsp+118h+var_90], rax
0x180055631  jmp     short loc_180055618
0x180055633  mov     [rsi+98h], r8
0x18005563a  mov     rax, [rsi+418h]
0x180055641  mov     [rax+14h], r10d
0x180055645  mov     rax, [rsi+418h]
0x18005564c  mov     [rax+18h], r9d
0x180055650  cmp     [rsp+118h+var_D4], r12d
0x180055655  jz      short loc_180055663
0x180055657  mov     [r14+12Ch], r15d
0x18005565e  mov     ecx, r15d
0x180055661  jmp     short loc_180055670
0x180055663  mov     ecx, [rsi+1ECh]
0x180055669  mov     [r14+12Ch], ecx
0x180055670  mov     dword ptr [r14], 150h
0x180055677  mov     rdx, [rsp+118h+var_A8]
0x18005567c  mov     eax, [rdx+14h]
0x18005567f  mov     [r14+18h], eax
0x180055683  mov     eax, [rdx+18h]
0x180055686  mov     [r14+1Ch], eax
0x18005568a  mov     dword ptr [r14+14h], 2
0x180055692  test    ecx, ecx
0x180055694  jnz     short loc_1800556A0
0x180055696  mov     dword ptr [r14+3Ch], 270Fh
0x18005569e  jmp     short loc_1800556B2
0x1800556a0  mov     ecx, [rsi+1F0h]
0x1800556a6  mov     eax, r15d
0x1800556a9  test    ecx, ecx
0x1800556ab  cmovnz  eax, ecx
0x1800556ae  mov     [r14+3Ch], eax
0x1800556b2  mov     [r14+44h], r15d
0x1800556b6  mov     dword ptr [r14+48h], 3E8h
0x1800556be  mov     eax, [rsi+60h]
0x1800556c1  mov     [r14+10h], eax
0x1800556c5  mov     eax, [rsi+148h]
0x1800556cb  mov     [r14+4Ch], eax
0x1800556cf  mov     eax, [rsi+150h]
0x1800556d5  mov     [r14+50h], eax
0x1800556d9  mov     eax, [rsi+158h]
0x1800556df  mov     [r14+80h], eax
0x1800556e6  mov     [r14+78h], eax
0x1800556ea  mov     [r14+7Ch], r15d
0x1800556ee  mov     eax, [rsi+204h]
0x1800556f4  test    eax, eax
0x1800556f6  jnz     short loc_180055701
0x1800556f8  cmp     [rsi+208h], r12d
0x1800556ff  jz      short loc_18005572F
0x180055701  cmp     eax, 4
0x180055704  jb      short loc_18005572B
0x180055706  mov     ecx, [rsi+208h]
0x18005570c  cmp     ecx, 0Fh
0x18005570f  ja      short loc_18005572B
0x180055711  cmp     eax, ecx
0x180055713  ja      short loc_18005572B
0x180055715  mov     [r14+130h], eax
0x18005571c  mov     eax, [rsi+208h]
0x180055722  mov     [r14+134h], eax
0x180055729  jmp     short loc_18005572F
0x18005572b  mov     [rsi+28h], r15d
0x18005572f  mov     eax, [rsi+168h]
0x180055735  or      eax, 10h
0x180055738  mov     [r14+64h], eax
0x18005573c  mov     eax, [rsi+15Ch]
0x180055742  mov     [r14+68h], eax
0x180055746  mov     eax, [rsi+160h]
0x18005574c  mov     [r14+6Ch], eax
0x180055750  mov     eax, [rsi+16Ch]
0x180055756  mov     [r14+70h], eax
0x18005575a  mov     eax, [rsi+154h]
0x180055760  mov     [r14+74h], eax
0x180055764  mov     eax, [rsi+17Ch]
0x18005576a  mov     [r14+84h], eax
0x180055771  mov     eax, [rsi+178h]
0x180055777  mov     [r14+88h], eax
0x18005577e  mov     dword ptr [r14+90h], 0FFh
0x180055789  mov     eax, [rsi+5Ch]
0x18005578c  mov     [r13+10h], eax
0x180055790  mov     eax, [rsi+194h]
0x180055796  mov     [r13+4], eax
0x18005579a  mov     eax, 6338h
0x18005579f  mov     [r14+0B0h], eax
0x1800557a6  mov     [r14+0ACh], eax
0x1800557ad  mov     eax, 12h
0x1800557b2  mov     [r14+8Ch], eax
0x1800557b9  cmp     [rsi+164h], r12d
0x1800557c0  jz      short loc_1800557CE
0x1800557c2  mov     eax, 1Ah
0x1800557c7  mov     [r14+8Ch], eax
0x1800557ce  cmp     dword ptr [rsi+170h], 10Eh
  ... truncated ...
```
