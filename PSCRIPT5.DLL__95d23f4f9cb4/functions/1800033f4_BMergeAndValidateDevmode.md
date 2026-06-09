# BMergeAndValidateDevmode

- ea: `0x1800033f4`
- end: `0x180003bc3`
- name: `BMergeAndValidateDevmode`
- size: `1999`
- prototype: ``
- caller_count: `1`
- callee_count: `13`
- tags: `registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x1800041a0`

## callees

- `0x1800028d8`
- `0x1800033f4`
- `0x1800224c0`
- `0x18002888c`
- `0x18002d90c`
- `0x18002f274`
- `0x18002fd80`
- `0x1800303ec`
- `0x180030650`
- `0x180030a2c`
- `0x180034afc`
- `0x1800545cc`
- `0x18005bc24`

## import_xrefs

- `WINSPOOL!GetPrinterW` at `0x1800036f2`
- `WINSPOOL!GetPrinterW` at `0x18000373c`
- `WINSPOOL!GetPrinterW` at `0x1800036f2`
- `WINSPOOL!GetPrinterW` at `0x18000373c`
- `KERNEL32!LocalFree` at `0x1800036b2`
- `KERNEL32!LocalFree` at `0x1800037a5`
- `KERNEL32!LocalFree` at `0x1800037c1`
- `KERNEL32!LocalFree` at `0x1800036b2`
- `KERNEL32!LocalFree` at `0x1800037a5`
- `KERNEL32!LocalFree` at `0x1800037c1`
- `KERNEL32!LocalAlloc` at `0x1800035f0`
- `KERNEL32!LocalAlloc` at `0x180003714`
- `KERNEL32!LocalAlloc` at `0x1800035f0`
- `KERNEL32!LocalAlloc` at `0x180003714`
- `KERNEL32!GetLastError` at `0x180003700`
- `KERNEL32!GetLastError` at `0x180003700`

## string_xrefs

- `0x18000341d`: `PrintConfig.dll`

## pseudocode

```c
__int64 BMergeAndValidateDevmode(__int64 a1, ...)
{
  __int64 v1; // rsi
  __int64 v2; // rbx
  int v4; // r15d
  unsigned int v5; // edx
  __int64 v6; // rdx
  unsigned int v7; // r12d
  unsigned int *v8; // r8
  unsigned int v9; // r14d
  __int64 v10; // rax
  unsigned int v11; // r11d
  _DWORD *v12; // r9
  __int64 v13; // rcx
  unsigned int v14; // r10d
  int v15; // esi
  __int64 v16; // rcx
  __int64 v17; // rax
  __int64 v18; // r14
  unsigned int v19; // r15d
  int v20; // ecx
  int v21; // eax
  unsigned int v22; // esi
  __int64 v23; // r13
  void *v24; // rcx
  int v25; // r12d
  struct _devicemodeW *v26; // rax
  int v27; // edx
  struct _devicemodeW *v28; // rbx
  void *v29; // rcx
  int v30; // r12d
  __int64 v31; // r14
  __int64 v32; // rsi
  struct _OEM_DMEXTRAHEADER *v33; // r14
  __int64 v34; // rax
  void *v35; // rsi
  _QWORD *v36; // rbx
  struct _devicemodeW *v37; // rdx
  __int64 v39; // r9
  __int64 v40; // rcx
  int v41; // r9d
  __int64 v42; // rax
  int v43; // eax
  __int64 v44; // rax
  int v45; // esi
  _QWORD *v46; // rbx
  __int64 v47; // rax
  int v48; // eax
  __int64 v49; // rax
  int v50; // ecx
  __int64 v51; // rbx
  __int16 v52; // ax
  __int64 v53; // rax
  int v54; // edx
  __int64 v55; // rcx
  __int64 v56; // rax
  int v57; // ecx
  __int64 v58; // rdx
  __int64 v59; // rsi
  int v60; // r8d
  _QWORD *v61; // rcx
  _QWORD *v62; // rsi
  __int64 v63; // rbx
  int v64; // r8d
  int v65; // r8d
  int v66; // r8d
  int v67; // r8d
  int v68; // r8d
  __int64 v69; // rcx
  int pcbNeeded; // [rsp+20h] [rbp-48h]
  unsigned int v71; // [rsp+30h] [rbp-38h]
  void *v72; // [rsp+50h] [rbp-18h]
  __int64 v73; // [rsp+B0h] [rbp+48h] BYREF
  __int64 cbBuf; // [rsp+B8h] [rbp+50h] BYREF
  va_list cbBufa; // [rsp+B8h] [rbp+50h]
  struct _devicemodeW *v76; // [rsp+C0h] [rbp+58h]
  _QWORD *v77; // [rsp+C8h] [rbp+60h]
  va_list va1; // [rsp+D0h] [rbp+68h] BYREF

  va_start(va1, a1);
  va_start(cbBufa, a1);
  cbBuf = va_arg(va1, _QWORD);
  v76 = va_arg(va1, struct _devicemodeW *);
  v77 = va_arg(va1, _QWORD *);
  v1 = *(_QWORD *)(a1 + 696);
  v2 = *(_QWORD *)(a1 + 2136);
  v4 = 0;
  if ( DoesFullPathMatchFile(*(const unsigned __int16 **)(v1 + 40), L"PrintConfig.dll") )
  {
    v5 = 94;
  }
  else
  {
    v6 = -1;
    do
      ++v6;
    while ( *(_WORD *)(*(_QWORD *)(v1 + 8) + 2 * v6) );
    v5 = 2 * v6 + 18;
  }
  v7 = *(_DWORD *)(v2 + 24) + *(_DWORD *)(v2 + 28);
  if ( v7 )
  {
    v8 = (unsigned int *)(*(_QWORD *)(v2 + 328) + *(unsigned int *)(v2 + 32));
    if ( v8 )
    {
      v9 = 0;
      while ( v8[11] == 2 )
      {
LABEL_30:
        ++v9;
        v8 += 21;
        if ( v9 >= v7 )
        {
          v4 = 1;
          v5 = (v5 + 9) & 0xFFFFFFF8;
          goto LABEL_32;
        }
      }
      if ( *v8 )
        v10 = *(_QWORD *)(v2 + 320) + *v8;
      else
        v10 = 0;
      v11 = v8[13];
      if ( v11 )
        v12 = (_DWORD *)(*(_QWORD *)(v2 + 328) + v8[14]);
      else
        v12 = 0;
      if ( v10 && v11 && v12 )
      {
        v13 = -1;
        do
          ++v13;
        while ( *(_BYTE *)(v10 + v13) );
        v14 = 0;
        v5 += v13 + 1;
        v15 = 0;
        while ( *v12 )
        {
          v16 = *(_QWORD *)(v2 + 320) + (unsigned int)*v12;
          if ( !v16 )
            break;
          v17 = -1;
          do
            ++v17;
          while ( *(_BYTE *)(v16 + v17) );
          if ( v14 < (unsigned int)v17 )
            v14 = v17;
          v12 = (_DWORD *)((char *)v12 + v8[12]);
          if ( ++v15 >= v11 )
          {
            v5 += v14 + 1;
            goto LABEL_30;
          }
        }
      }
    }
  }
LABEL_32:
  v18 = *(_QWORD *)(a1 + 2128);
  LODWORD(cbBuf) = 0;
  v19 = v4 != 0 ? v5 : 0;
  *(_DWORD *)(a1 + 3756) = v19;
  if ( !v18 )
    goto LABEL_53;
  v20 = 0;
  if ( *(_DWORD *)(v18 + 4) == 1196442656 )
  {
    v21 = 1;
  }
  else
  {
    v21 = 0;
    if ( *(_DWORD *)(v18 + 4) != 1347437600 )
      v20 = -2147418113;
  }
  if ( v20 < 0 )
    goto LABEL_53;
  if ( v21 )
    goto LABEL_53;
  v22 = v19 + 976;
  if ( v19 >= 0xFFFFFC30 )
    goto LABEL_53;
  v23 = *(_QWORD *)(a1 + 3464);
  v24 = *(void **)(a1 + 24);
  v25 = *(_DWORD *)(a1 + 132);
  v72 = v24;
  v73 = *(_QWORD *)(a1 + 2136);
  if ( !(unsigned int)BCalcTotalOEMDMSize(v24, v23, (__int64 *)cbBufa) )
    goto LABEL_53;
  if ( v22 + (unsigned int)cbBuf < (unsigned int)cbBuf )
    goto LABEL_53;
  v26 = (struct _devicemodeW *)LocalAlloc(0x40u, v22 + (unsigned int)cbBuf);
  v28 = v26;
  if ( !v26 )
    goto LABEL_53;
  if ( !(unsigned int)PSBInitDriverDefaultDevmode((_DWORD)v26, v27, v73, v18, v25 & 1) )
    goto LABEL_52;
  v30 = *(_DWORD *)(v23 + 8);
  if ( v30 )
  {
    v31 = v22;
    v32 = v23 + 24;
    v33 = (struct _OEM_DMEXTRAHEADER *)((char *)v28 + v31);
    do
    {
      if ( *(_QWORD *)(v32 + 32) )
      {
        if ( !(unsigned int)BCallOEMDevMode(v72, *(void **)v23, (struct _OEM_PLUGIN_ENTRY *)v32, 2u, 0, v28, v33, 0) )
          goto LABEL_52;
        if ( *(_DWORD *)(v32 + 64) )
        {
          v34 = *(unsigned int *)(v32 + 64);
          *(_QWORD *)(v32 + 56) = v33;
          v33 = (struct _OEM_DMEXTRAHEADER *)((char *)v33 + v34);
        }
      }
      v32 += 176;
      --v30;
    }
    while ( v30 );
  }
  if ( (int)PatchDevmodeSizeFieldsAndJTHdr(v29, v28, v19, cbBuf, 0) < 0 )
  {
LABEL_52:
    LocalFree(v28);
LABEL_53:
    v28 = 0;
  }
  *(_QWORD *)(a1 + 88) = v28;
  if ( !v28 )
    return 0;
  v35 = *(void **)(a1 + 24);
  *(_QWORD *)(a1 + 40) = v28;
  LODWORD(cbBuf) = 0;
  if ( !GetPrinterW(v35, 2u, 0, 0, (LPDWORD)cbBufa) && GetLastError() == 122 )
  {
    v36 = LocalAlloc(0, (unsigned int)cbBuf);
    if ( v36 )
    {
      if ( GetPrinterW(v35, 2u, (LPBYTE)v36, cbBuf, (LPDWORD)cbBufa) )
      {
        v37 = (struct _devicemodeW *)v36[7];
        if ( v37 )
        {
          if ( !(unsigned int)BValidateAndMergeDevmodeWithOemPlugins(
                                *(struct _devicemodeW **)(a1 + 88),
                                *(_QWORD *)(a1 + 696),
                                a1 + 3764,
                                v71,
                                v37,
                                *(struct _OEM_PLUGINS **)(a1 + 3464),
                                *(void **)(a1 + 24)) )
          {
            LocalFree(v36);
            return 0;
          }
        }
      }
      LocalFree(v36);
    }
  }
  if ( !(unsigned int)BValidateAndMergeDevmodeWithOemPlugins(
                        *(struct _devicemodeW **)(a1 + 88),
                        *(_QWORD *)(a1 + 696),
                        a1 + 3764,
                        v71,
                        v76,
                        *(struct _OEM_PLUGINS **)(a1 + 3464),
                        *(void **)(a1 + 24)) )
    return 0;
  v39 = *(_QWORD *)(a1 + 88) + *(unsigned __int16 *)(*(_QWORD *)(a1 + 88) + 68LL);
  v40 = *(_QWORD *)(a1 + 2128);
  *(_QWORD *)(a1 + 96) = v39;
  CombineOptionArray(v40, a1 + 2372, 256, v39 + 196, a1 + 176);
  v42 = *(_QWORD *)(a1 + 2136);
  *(_DWORD *)(a1 + 2368) = 1;
  if ( (*(_BYTE *)(v42 + 140) & 8) != 0 )
  {
    if ( *(_WORD *)(*(_QWORD *)(a1 + 88) + 92LL) != 2 )
    {
LABEL_69:
      v43 = 0;
      if ( (*(_BYTE *)(a1 + 80) & 1) == 0 )
        goto LABEL_71;
    }
  }
  else if ( !*(_DWORD *)(*(_QWORD *)(a1 + 96) + 124LL) )
  {
    goto LABEL_69;
  }
  v43 = 1;
LABEL_71:
  *(_DWORD *)(a1 + 708) = v43;
  v44 = *(_QWORD *)(a1 + 3464);
  LODWORD(v73) = 0;
  LODWORD(cbBuf) = 0;
  v45 = *(_DWORD *)(v44 + 8);
  v46 = (_QWORD *)(v44 + 24);
  if ( v45 )
  {
    while ( 1 )
    {
      v47 = v46[4];
      if ( v47 )
      {
        *(_QWORD *)(a1 + 32) = v47;
        *(_QWORD *)(a1 + 8) = v46[5];
        *(_QWORD *)(a1 + 48) = v46[7];
        if ( v46[9] )
        {
          LODWORD(v73) = *(_DWORD *)(a1 + 708);
          LODWORD(cbBuf) = 0;
          v48 = HComOEMGetPDEVAdjustment((_DWORD)v46, a1, 3, (unsigned int)&v73, 4, (__int64)cbBufa);
          if ( (unsigned int)(v48 + 2147467263) > 1 && v48 != 1 )
            break;
        }
      }
      v46 += 22;
      if ( !--v45 )
        goto LABEL_82;
    }
    if ( v48 >= 0 && (_DWORD)cbBuf && !v48 )
      *(_DWORD *)(a1 + 708) = v73;
  }
LABEL_82:
  v49 = *(_QWORD *)(a1 + 96);
  if ( *(_DWORD *)(v49 + 136) == 6 )
    *(_DWORD *)(a1 + 2152) |= 0x1000u;
  v50 = *(_DWORD *)(v49 + 124);
  if ( v50 == 2 )
  {
    *(_DWORD *)(v49 + 136) = 0;
LABEL_87:
    *(_WORD *)(a1 + 166) = 0;
    goto LABEL_88;
  }
  if ( v50 == 3 )
    goto LABEL_87;
LABEL_88:
  v51 = *(_QWORD *)(a1 + 88);
  v52 = *(_WORD *)(v51 + 90);
  if ( v52 <= *(__int16 *)(v51 + 96) )
    v52 = *(_WORD *)(v51 + 96);
  *(_DWORD *)(a1 + 712) = v52;
  if ( *(_WORD *)(v51 + 76) == 2 )
  {
    v53 = *(_QWORD *)(a1 + 96);
    v54 = (*(_DWORD *)(*(_QWORD *)(a1 + 2136) + 140LL) & 4) != 0 ? 90 : -90;
    *(_DWORD *)(a1 + 716) = v54;
    if ( (*(_DWORD *)(v53 + 4) & 0x200) != 0 )
      *(_DWORD *)(a1 + 716) = -v54;
  }
  else
  {
    *(_DWORD *)(a1 + 716) = 0;
  }
  v55 = *(_QWORD *)(a1 + 2128);
  if ( *(_DWORD *)(v55 + 60) )
    v56 = v55 + *(unsigned int *)(v55 + 60);
  else
    v56 = 0;
  v57 = *(_DWORD *)(v51 + 72);
  if ( (v57 & 2) != 0
    && *(_WORD *)(v51 + 78) == 0x7FFF
    && (v58 = *(_QWORD *)(a1 + 2136), (*(_BYTE *)(v58 + 140) & 0x20) != 0)
    && (*(_DWORD *)(v58 + 16) >= 0x40003u || (*(_BYTE *)(v56 + 44) & 2) != 0) )
  {
    v59 = *(unsigned __int16 *)(v51 + 68);
    *(_DWORD *)(v51 + 72) = v57 & 0xFFFEFFF3;
    *(_WORD *)(v51 + 82) = *(_DWORD *)(v59 + v51 + 152) / 0x64u;
    *(_WORD *)(v51 + 80) = *(_DWORD *)(v59 + v51 + 156) / 0x64u;
    memset_0((void *)(v51 + 102), 0, 0x40u);
    v61 = v77;
    if ( v77 )
    {
      *v77 = 0;
      *((_DWORD *)v61 + 2) = *(_DWORD *)(v59 + v51 + 152);
      *((_DWORD *)v61 + 3) = *(_DWORD *)(v59 + v51 + 156);
    }
  }
  else
  {
    v62 = v77;
    if ( !(unsigned int)BValidateDevmodeFormFields(*(_QWORD *)(a1 + 24), v51, (_DWORD)v77, v41, pcbNeeded) )
    {
      VDefaultDevmodeFormFields(*(_QWORD *)(a1 + 2136), *(_QWORD *)(a1 + 88), *(_DWORD *)(a1 + 132) & 1);
      *v62 = 0;
      *((_DWORD *)v62 + 2) = 100 * *(__int16 *)(*(_QWORD *)(a1 + 88) + 82LL);
      *((_DWORD *)v62 + 3) = 100 * *(__int16 *)(*(_QWORD *)(a1 + 88) + 80LL);
    }
  }
  v63 = *(_QWORD *)(*(_QWORD *)(a1 + 2136) + 328LL);
  PPDChangeOptionsViaID(v63, a1 + 2372, v60, 1, *(_QWORD *)(a1 + 88));
  PPDChangeOptionsViaID(v63, a1 + 2372, v64, 4, *(_QWORD *)(a1 + 88));
  PPDChangeOptionsViaID(v63, a1 + 2372, v65, 0, *(_QWORD *)(a1 + 88));
  PPDChangeOptionsViaID(v63, a1 + 2372, v66, 3, *(_QWORD *)(a1 + 88));
  PPDChangeOptionsViaID(v63, a1 + 2372, v67, 10, *(_QWORD *)(a1 + 88));
  PPDChangeOptionsViaID(v63, a1 + 2372, v68, 5, *(_QWORD *)(a1 + 88));
  v69 = *(_QWORD *)(a1 + 88);
  if ( (*(_BYTE *)(v69 + 72) & 0x40) != 0 && *(_DWORD *)(v69 + 180) == 2
    || *(_DWORD *)(*(_QWORD *)(a1 + 96) + 136LL) == 6 )
  {
    *(_DWORD *)(*(_QWORD *)(a1 + 96) + 136LL) = 0;
  }
  return 1;
}

```

## disassembly

```asm
0x1800033f4  mov     [rsp-40h+arg_18], r9
0x1800033f9  mov     [rsp-40h+arg_10], r8
0x1800033fe  mov     [rsp-40h+cbBuf], rdx
0x180003403  push    rbp
0x180003404  push    rbx
0x180003405  push    rsi
0x180003406  push    rdi
0x180003407  push    r12
0x180003409  push    r13
0x18000340b  push    r14
0x18000340d  push    r15
0x18000340f  mov     rbp, rsp
0x180003412  sub     rsp, 68h
0x180003416  mov     rsi, [rcx+2B8h]
0x18000341d  lea     rdx, aPrintconfigDll; "PrintConfig.dll"
0x180003424  mov     rbx, [rcx+858h]
0x18000342b  mov     rdi, rcx
0x18000342e  xor     r13d, r13d
0x180003431  mov     r15d, r13d
0x180003434  mov     rcx, [rsi+28h]; unsigned __int16 *
0x180003438  call    ?DoesFullPathMatchFile@@YA_NPEBG0@Z; DoesFullPathMatchFile(ushort const *,ushort const *)
0x18000343d  test    al, al
0x18000343f  jz      short loc_180003447
0x180003441  lea     edx, [r13+5Eh]
0x180003445  jmp     short loc_180003460
0x180003447  mov     rax, [rsi+8]
0x18000344b  or      rdx, 0FFFFFFFFFFFFFFFFh
0x18000344f  inc     rdx
0x180003452  cmp     [rax+rdx*2], r13w
0x180003457  jnz     short loc_18000344F
0x180003459  lea     edx, ds:12h[rdx*2]
0x180003460  mov     r12d, [rbx+1Ch]
0x180003464  add     r12d, [rbx+18h]
0x180003468  jz      loc_180003539
0x18000346e  mov     r8d, [rbx+20h]
0x180003472  add     r8, [rbx+148h]
0x180003479  jz      loc_180003539
0x18000347f  mov     r14d, r13d
0x180003482  cmp     dword ptr [r8+2Ch], 2
0x180003487  jz      loc_18000351D
0x18000348d  cmp     [r8], r13d
0x180003490  jz      short loc_18000349E
0x180003492  mov     eax, [r8]
0x180003495  add     rax, [rbx+140h]
0x18000349c  jmp     short loc_1800034A1
0x18000349e  mov     rax, r13
0x1800034a1  mov     r11d, [r8+34h]
0x1800034a5  test    r11d, r11d
0x1800034a8  jz      short loc_1800034B7
0x1800034aa  mov     r9d, [r8+38h]
0x1800034ae  add     r9, [rbx+148h]
0x1800034b5  jmp     short loc_1800034BA
0x1800034b7  mov     r9, r13
0x1800034ba  test    rax, rax
0x1800034bd  jz      short loc_180003539
0x1800034bf  test    r11d, r11d
0x1800034c2  jz      short loc_180003539
0x1800034c4  test    r9, r9
0x1800034c7  jz      short loc_180003539
0x1800034c9  or      rcx, 0FFFFFFFFFFFFFFFFh
0x1800034cd  inc     rcx
0x1800034d0  cmp     [rax+rcx], r13b
0x1800034d4  jnz     short loc_1800034CD
0x1800034d6  inc     edx
0x1800034d8  mov     r10d, r13d
0x1800034db  add     edx, ecx
0x1800034dd  test    r11d, r11d
0x1800034e0  jz      short loc_180003518
0x1800034e2  mov     esi, r13d
0x1800034e5  cmp     [r9], r13d
0x1800034e8  jz      short loc_180003539
0x1800034ea  mov     ecx, [r9]
0x1800034ed  add     rcx, [rbx+140h]
0x1800034f4  jz      short loc_180003539
0x1800034f6  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800034fa  inc     rax
0x1800034fd  cmp     [rcx+rax], r13b
0x180003501  jnz     short loc_1800034FA
0x180003503  cmp     r10d, eax
0x180003506  cmovb   r10d, eax
0x18000350a  mov     eax, [r8+30h]
0x18000350e  add     r9, rax
0x180003511  inc     esi
0x180003513  cmp     esi, r11d
0x180003516  jb      short loc_1800034E5
0x180003518  inc     edx
0x18000351a  add     edx, r10d
0x18000351d  inc     r14d
0x180003520  add     r8, 54h ; 'T'
0x180003524  cmp     r14d, r12d
0x180003527  jb      loc_180003482
0x18000352d  add     edx, 9
0x180003530  mov     r15d, 1
0x180003536  and     edx, 0FFFFFFF8h
0x180003539  mov     r14, [rdi+850h]
0x180003540  neg     r15d
0x180003543  mov     dword ptr [rbp+cbBuf], r13d
0x180003547  sbb     r15d, r15d
0x18000354a  and     r15d, edx
0x18000354d  mov     [rdi+0EACh], r15d
0x180003554  test    r14, r14
0x180003557  jz      loc_1800036BD
0x18000355d  cmp     dword ptr [r14+4], 47504420h
0x180003565  mov     ecx, r13d
0x180003568  jz      short loc_18000357E
0x18000356a  cmp     dword ptr [r14+4], 50504420h
0x180003572  mov     eax, r13d
0x180003575  jz      short loc_180003583
0x180003577  mov     ecx, 8000FFFFh
0x18000357c  jmp     short loc_180003583
0x18000357e  mov     eax, 1
0x180003583  test    ecx, ecx
0x180003585  js      loc_1800036BD
0x18000358b  test    eax, eax
0x18000358d  jnz     loc_1800036BD
0x180003593  lea     esi, [r15+3D0h]
0x18000359a  cmp     esi, 3D0h
0x1800035a0  jb      loc_1800036BD
0x1800035a6  mov     r13, [rdi+0D88h]
0x1800035ad  lea     r8, [rbp+cbBuf]
0x1800035b1  mov     rcx, [rdi+18h]
0x1800035b5  mov     rdx, r13
0x1800035b8  mov     rax, [rdi+858h]
0x1800035bf  mov     r12d, [rdi+84h]
0x1800035c6  mov     [rbp+var_18], rcx
0x1800035ca  mov     [rbp+arg_0], rax
0x1800035ce  call    BCalcTotalOEMDMSize
0x1800035d3  test    eax, eax
0x1800035d5  jz      loc_1800036BA
0x1800035db  mov     ecx, dword ptr [rbp+cbBuf]
0x1800035de  lea     eax, [rsi+rcx]
0x1800035e1  cmp     eax, ecx
0x1800035e3  jb      loc_1800036BA
0x1800035e9  mov     edx, eax; uBytes
0x1800035eb  mov     ecx, 40h ; '@'; uFlags
0x1800035f0  call    cs:__imp_LocalAlloc
0x1800035f6  mov     rbx, rax
0x1800035f9  test    rax, rax
0x1800035fc  jz      loc_1800036BA
0x180003602  mov     r8, [rbp+arg_0]
0x180003606  and     r12d, 1
0x18000360a  mov     r9, r14
0x18000360d  mov     dword ptr [rsp+68h+pcbNeeded], r12d
0x180003612  mov     rcx, rax
0x180003615  call    PSBInitDriverDefaultDevmode
0x18000361a  test    eax, eax
0x18000361c  jz      loc_1800036AC
0x180003622  mov     r12d, [r13+8]
0x180003626  test    r12d, r12d
0x180003629  jz      short loc_18000368F
0x18000362b  mov     r14d, esi
0x18000362e  lea     rsi, [r13+18h]
0x180003632  add     r14, rbx
0x180003635  cmp     qword ptr [rsi+20h], 0
0x18000363a  jz      short loc_180003682
0x18000363c  mov     rdx, [r13+0]; void *
0x180003640  mov     r9d, 2; unsigned int
0x180003646  mov     rcx, [rbp+var_18]; void *
0x18000364a  mov     r8, rsi; struct _OEM_PLUGIN_ENTRY *
0x18000364d  mov     [rsp+68h+var_30], 0; struct _OEM_DMEXTRAHEADER *
0x180003656  mov     [rsp+68h+var_38], r14; struct _OEM_DMEXTRAHEADER *
0x18000365b  mov     [rsp+68h+var_40], rbx; struct _devicemodeW *
0x180003660  mov     [rsp+68h+pcbNeeded], 0; struct _devicemodeW *
0x180003669  call    ?BCallOEMDevMode@@YAHPEAX0PEAU_OEM_PLUGIN_ENTRY@@KPEAU_devicemodeW@@2PEAU_OEM_DMEXTRAHEADER@@3@Z; BCallOEMDevMode(void *,void *,_OEM_PLUGIN_ENTRY *,ulong,_devicemodeW *,_devicemodeW *,_OEM_DMEXTRAHEADER *,_OEM_DMEXTRAHEADER *)
0x18000366e  test    eax, eax
0x180003670  jz      short loc_1800036AC
0x180003672  cmp     dword ptr [rsi+40h], 0
0x180003676  jz      short loc_180003682
0x180003678  mov     eax, [rsi+40h]
0x18000367b  mov     [rsi+38h], r14
0x18000367f  add     r14, rax
0x180003682  add     rsi, 0B0h
0x180003689  add     r12d, 0FFFFFFFFh
0x18000368d  jnz     short loc_180003635
0x18000368f  mov     r9d, dword ptr [rbp+cbBuf]; unsigned int
0x180003693  xor     r13d, r13d
0x180003696  mov     r8d, r15d; unsigned int
0x180003699  mov     dword ptr [rsp+68h+pcbNeeded], r13d; int
0x18000369e  mov     rdx, rbx; struct _devicemodeW *
0x1800036a1  call    ?PatchDevmodeSizeFieldsAndJTHdr@@YAJPEAXPEAU_devicemodeW@@KKH@Z; PatchDevmodeSizeFieldsAndJTHdr(void *,_devicemodeW *,ulong,ulong,int)
0x1800036a6  test    eax, eax
0x1800036a8  js      short loc_1800036AF
0x1800036aa  jmp     short loc_1800036C0
0x1800036ac  xor     r13d, r13d
0x1800036af  mov     rcx, rbx; hMem
0x1800036b2  call    cs:__imp_LocalFree
0x1800036b8  jmp     short loc_1800036BD
0x1800036ba  xor     r13d, r13d
0x1800036bd  mov     rbx, r13
0x1800036c0  mov     [rdi+58h], rbx
0x1800036c4  test    rbx, rbx
0x1800036c7  jz      loc_1800037AB
0x1800036cd  mov     rsi, [rdi+18h]
0x1800036d1  lea     rax, [rbp+cbBuf]
0x1800036d5  xor     r9d, r9d; cbBuf
0x1800036d8  mov     [rdi+28h], rbx
0x1800036dc  xor     r8d, r8d; pPrinter
0x1800036df  mov     dword ptr [rbp+cbBuf], r13d
0x1800036e3  mov     rcx, rsi; hPrinter
0x1800036e6  mov     [rsp+68h+pcbNeeded], rax; pcbNeeded
0x1800036eb  lea     r12d, [r9+2]
0x1800036ef  mov     edx, r12d; Level
0x1800036f2  call    cs:__imp_GetPrinterW
0x1800036f8  test    eax, eax
0x1800036fa  jnz     loc_1800037C7
0x180003700  call    cs:__imp_GetLastError
0x180003706  cmp     eax, 7Ah ; 'z'
0x180003709  jnz     loc_1800037C7
0x18000370f  mov     edx, dword ptr [rbp+cbBuf]; uBytes
0x180003712  xor     ecx, ecx; uFlags
0x180003714  call    cs:__imp_LocalAlloc
0x18000371a  mov     rbx, rax
0x18000371d  test    rax, rax
0x180003720  jz      loc_1800037C7
0x180003726  mov     r9d, dword ptr [rbp+cbBuf]; cbBuf
0x18000372a  lea     rax, [rbp+cbBuf]
0x18000372e  mov     r8, rbx; pPrinter
0x180003731  mov     [rsp+68h+pcbNeeded], rax; pcbNeeded
0x180003736  mov     edx, r12d; Level
0x180003739  mov     rcx, rsi; hPrinter
0x18000373c  call    cs:__imp_GetPrinterW
0x180003742  test    eax, eax
0x180003744  jz      short loc_1800037BE
0x180003746  mov     rdx, [rbx+38h]
0x18000374a  test    rdx, rdx
0x18000374d  jz      short loc_1800037BE
0x18000374f  mov     rax, [rdi+18h]
0x180003753  lea     rcx, [rdi+0EB4h]
0x18000375a  mov     r9, [rdi+850h]
0x180003761  mov     r8, [rdi+858h]
0x180003768  mov     [rsp+68h+var_20], rax; void *
0x18000376d  mov     rax, [rdi+0D88h]
0x180003774  mov     [rsp+68h+var_28], rax; struct _OEM_PLUGINS *
0x180003779  mov     rax, [rdi+2B8h]
0x180003780  mov     [rsp+68h+var_30], rdx; struct _devicemodeW *
0x180003785  mov     edx, [rdi+0EACh]
0x18000378b  mov     [rsp+68h+var_40], rcx; __int64
0x180003790  mov     rcx, [rdi+58h]; struct _devicemodeW *
0x180003794  mov     [rsp+68h+pcbNeeded], rax; __int64
0x180003799  call    BValidateAndMergeDevmodeWithOemPlugins
0x18000379e  test    eax, eax
0x1800037a0  jnz     short loc_1800037BE
0x1800037a2  mov     rcx, rbx; hMem
0x1800037a5  call    cs:__imp_LocalFree
0x1800037ab  xor     eax, eax
0x1800037ad  add     rsp, 68h
0x1800037b1  pop     r15
0x1800037b3  pop     r14
0x1800037b5  pop     r13
0x1800037b7  pop     r12
0x1800037b9  pop     rdi
0x1800037ba  pop     rsi
0x1800037bb  pop     rbx
0x1800037bc  pop     rbp
0x1800037bd  retn
0x1800037be  mov     rcx, rbx; hMem
0x1800037c1  call    cs:__imp_LocalFree
0x1800037c7  mov     rax, [rdi+18h]
0x1800037cb  lea     rcx, [rdi+0EB4h]
0x1800037d2  mov     r9, [rdi+850h]
0x1800037d9  mov     r8, [rdi+858h]
0x1800037e0  mov     edx, [rdi+0EACh]
0x1800037e6  mov     [rsp+68h+var_20], rax; void *
0x1800037eb  mov     rax, [rdi+0D88h]
0x1800037f2  mov     [rsp+68h+var_28], rax; struct _OEM_PLUGINS *
0x1800037f7  mov     rax, [rbp+arg_10]
0x1800037fb  mov     [rsp+68h+var_30], rax; struct _devicemodeW *
0x180003800  mov     rax, [rdi+2B8h]
0x180003807  mov     [rsp+68h+var_40], rcx; __int64
0x18000380c  mov     rcx, [rdi+58h]; struct _devicemodeW *
0x180003810  mov     [rsp+68h+pcbNeeded], rax; __int64
0x180003815  call    BValidateAndMergeDevmodeWithOemPlugins
0x18000381a  test    eax, eax
0x18000381c  jz      short loc_1800037AB
0x18000381e  mov     rcx, [rdi+58h]
0x180003822  lea     rax, [rdi+0B0h]
0x180003829  lea     r14, [rdi+944h]
0x180003830  mov     [rsp+68h+pcbNeeded], rax
0x180003835  mov     r8d, 100h
0x18000383b  mov     rdx, r14
0x18000383e  movzx   r9d, word ptr [rcx+44h]
0x180003843  add     r9, rcx
0x180003846  mov     rcx, [rdi+850h]
0x18000384d  mov     [rdi+60h], r9
0x180003851  add     r9, 0C4h
0x180003858  call    CombineOptionArray
0x18000385d  mov     rax, [rdi+858h]
0x180003864  mov     r15d, 1
0x18000386a  mov     [rdi+940h], r15d
0x180003871  test    byte ptr [rax+8Ch], 8
0x180003878  jz      short loc_180003887
0x18000387a  mov     rax, [rdi+58h]
0x18000387e  cmp     r12w, [rax+5Ch]
0x180003883  jz      short loc_18000389A
0x180003885  jmp     short loc_180003891
0x180003887  mov     rax, [rdi+60h]
0x18000388b  cmp     [rax+7Ch], r13d
0x18000388f  jnz     short loc_18000389A
0x180003891  mov     eax, r13d
0x180003894  test    [rdi+50h], r15b
  ... truncated ...
```
