# BMergeAndValidateDevmode

- ea: `0x1800034bc`
- end: `0x180003c50`
- name: `BMergeAndValidateDevmode`
- size: `1940`
- prototype: `__int64(__int64, ...)`
- caller_count: `1`
- callee_count: `15`
- tags: `registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x180004240`

## callees

- `0x180002938`
- `0x1800034bc`
- `0x1800231fc`
- `0x1800299d4`
- `0x18002ed2c`
- `0x18002f400`
- `0x180030794`
- `0x180031004`
- `0x18003136c`
- `0x1800319e0`
- `0x180031c70`
- `0x180032054`
- `0x180036224`
- `0x180055f94`
- `0x18005d890`

## import_xrefs

- `KERNEL32!LocalFree` at `0x180003777`
- `KERNEL32!LocalFree` at `0x180003812`
- `KERNEL32!LocalFree` at `0x180003835`
- `KERNEL32!LocalFree` at `0x180003777`
- `KERNEL32!LocalFree` at `0x180003812`
- `KERNEL32!LocalFree` at `0x180003835`
- `KERNEL32!LocalAlloc` at `0x1800036ad`
- `KERNEL32!LocalAlloc` at `0x1800036ad`

## string_xrefs

- `0x1800034e5`: `PrintConfig.dll`

## pseudocode

```c
__int64 BMergeAndValidateDevmode(__int64 a1, ...)
{
  __int64 v1; // rsi
  __int64 v2; // rbx
  int v4; // r12d
  unsigned int v5; // edx
  __int64 v6; // rdx
  unsigned int v7; // r15d
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
  __int64 v18; // r15
  unsigned int v19; // r13d
  unsigned int v20; // esi
  __int64 v21; // r12
  __int64 v22; // rcx
  int v23; // r14d
  struct _devicemodeW *v24; // rax
  __int64 v25; // rdx
  struct _devicemodeW *v26; // rbx
  void *v27; // rcx
  int v28; // r15d
  __int64 v29; // r14
  __int64 v30; // rsi
  struct _OEM_DMEXTRAHEADER *v31; // r14
  __int64 v32; // rax
  struct _devicemodeW **v33; // rsi
  void *v34; // rcx
  BYTE *Printer; // rax
  BYTE *v36; // rbx
  struct _devicemodeW *v37; // rax
  __int64 v39; // rbx
  char *v40; // r9
  __int64 v41; // rcx
  __int64 v42; // rax
  int v43; // eax
  __int64 v44; // rax
  int v45; // r14d
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
  __int64 v59; // r14
  __int64 v60; // r8
  _QWORD *v61; // rcx
  _QWORD *v62; // r14
  __int64 v63; // rbx
  __int64 v64; // r8
  __int64 v65; // r8
  __int64 v66; // r8
  __int64 v67; // r8
  __int64 v68; // r8
  int v69; // [rsp+30h] [rbp-38h]
  void *v70; // [rsp+50h] [rbp-18h]
  __int64 v71; // [rsp+B0h] [rbp+48h] BYREF
  __int64 v72; // [rsp+B8h] [rbp+50h] BYREF
  va_list va; // [rsp+B8h] [rbp+50h]
  struct _devicemodeW *v74; // [rsp+C0h] [rbp+58h]
  _QWORD *v75; // [rsp+C8h] [rbp+60h]
  va_list va1; // [rsp+D0h] [rbp+68h] BYREF

  va_start(va1, a1);
  va_start(va, a1);
  v72 = va_arg(va1, _QWORD);
  v74 = va_arg(va1, struct _devicemodeW *);
  v75 = va_arg(va1, _QWORD *);
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
  v19 = v4 != 0 ? v5 : 0;
  LODWORD(v72) = 0;
  *(_DWORD *)(a1 + 3756) = v19;
  LODWORD(v71) = 0;
  if ( (int)IsRawBinaryDataFromGPD(v18, &v71) < 0 )
    goto LABEL_48;
  if ( (_DWORD)v71 )
    goto LABEL_48;
  v20 = v19 + 976;
  if ( v19 >= 0xFFFFFC30 )
    goto LABEL_48;
  v21 = *(_QWORD *)(a1 + 3464);
  v22 = *(_QWORD *)(a1 + 24);
  v23 = *(_DWORD *)(a1 + 132);
  v70 = (void *)v22;
  v71 = *(_QWORD *)(a1 + 2136);
  if ( !(unsigned int)BCalcTotalOEMDMSize(v22, (__int64 *)v21, (__int64 *)va) )
    goto LABEL_48;
  if ( v20 + (unsigned int)v72 < (unsigned int)v72 )
    goto LABEL_48;
  v24 = (struct _devicemodeW *)LocalAlloc(0x40u, v20 + (unsigned int)v72);
  v26 = v24;
  if ( !v24 )
    goto LABEL_48;
  if ( !(unsigned int)PSBInitDriverDefaultDevmode((__int64)v24, v25, v71, v18, v23 & 1) )
    goto LABEL_47;
  v28 = *(_DWORD *)(v21 + 8);
  if ( v28 )
  {
    v29 = v20;
    v30 = v21 + 24;
    v31 = (struct _OEM_DMEXTRAHEADER *)((char *)v26 + v29);
    do
    {
      if ( *(_QWORD *)(v30 + 32) )
      {
        if ( !(unsigned int)BCallOEMDevMode(v70, *(void **)v21, (struct _OEM_PLUGIN_ENTRY *)v30, 2u, 0, v26, v31, 0) )
          goto LABEL_47;
        if ( *(_DWORD *)(v30 + 64) )
        {
          v32 = *(unsigned int *)(v30 + 64);
          *(_QWORD *)(v30 + 56) = v31;
          v31 = (struct _OEM_DMEXTRAHEADER *)((char *)v31 + v32);
        }
      }
      v30 += 176;
      --v28;
    }
    while ( v28 );
  }
  if ( (int)PatchDevmodeSizeFieldsAndJTHdr(v27, v26, v19, v72, 0) < 0 )
  {
LABEL_47:
    LocalFree(v26);
LABEL_48:
    v26 = 0;
  }
  v33 = (struct _devicemodeW **)(a1 + 88);
  *(_QWORD *)(a1 + 88) = v26;
  if ( !v26 )
    return 0;
  v34 = *(void **)(a1 + 24);
  *(_QWORD *)(a1 + 40) = v26;
  Printer = MyGetPrinter(v34);
  v36 = Printer;
  if ( Printer )
  {
    v37 = (struct _devicemodeW *)*((_QWORD *)Printer + 7);
    if ( v37
      && !(unsigned int)BValidateAndMergeDevmodeWithOemPlugins(
                          *v33,
                          *(_DWORD *)(a1 + 3756),
                          *(_QWORD *)(a1 + 2136),
                          *(struct _RAWBINARYDATA **)(a1 + 2128),
                          *(_QWORD *)(a1 + 696),
                          a1 + 3764,
                          v69,
                          v37,
                          *(struct _OEM_PLUGINS **)(a1 + 3464),
                          *(void **)(a1 + 24)) )
    {
      LocalFree(v36);
      return 0;
    }
    LocalFree(v36);
    v39 = a1 + 88;
  }
  else
  {
    v39 = a1 + 88;
  }
  if ( !(unsigned int)BValidateAndMergeDevmodeWithOemPlugins(
                        *v33,
                        *(_DWORD *)(a1 + 3756),
                        *(_QWORD *)(a1 + 2136),
                        *(struct _RAWBINARYDATA **)(a1 + 2128),
                        *(_QWORD *)(a1 + 696),
                        a1 + 3764,
                        v69,
                        v74,
                        *(struct _OEM_PLUGINS **)(a1 + 3464),
                        *(void **)(a1 + 24)) )
    return 0;
  v40 = (char *)*v33 + (*v33)->dmSize;
  v41 = *(_QWORD *)(a1 + 2128);
  *(_QWORD *)(a1 + 96) = v40;
  CombineOptionArray(v41, a1 + 2372, 0x100u, (__int64)(v40 + 196), a1 + 176);
  v42 = *(_QWORD *)(a1 + 2136);
  *(_DWORD *)(a1 + 2368) = 1;
  if ( (*(_BYTE *)(v42 + 140) & 8) != 0 )
  {
    if ( *(_WORD *)(*(_QWORD *)v39 + 92LL) != 2 )
    {
LABEL_62:
      v43 = 0;
      if ( (*(_BYTE *)(a1 + 80) & 1) == 0 )
        goto LABEL_64;
    }
  }
  else if ( !*(_DWORD *)(*(_QWORD *)(a1 + 96) + 124LL) )
  {
    goto LABEL_62;
  }
  v43 = 1;
LABEL_64:
  *(_DWORD *)(a1 + 708) = v43;
  v44 = *(_QWORD *)(a1 + 3464);
  LODWORD(v71) = 0;
  LODWORD(v72) = 0;
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
          LODWORD(v71) = *(_DWORD *)(a1 + 708);
          LODWORD(v72) = 0;
          v48 = HComOEMGetPDEVAdjustment((__int64)v46, a1);
          if ( (unsigned int)(v48 + 2147467263) > 1 && v48 != 1 )
            break;
        }
      }
      v46 += 22;
      if ( !--v45 )
        goto LABEL_75;
    }
    if ( v48 >= 0 && (_DWORD)v72 && !v48 )
      *(_DWORD *)(a1 + 708) = v71;
  }
LABEL_75:
  v49 = *(_QWORD *)(a1 + 96);
  if ( *(_DWORD *)(v49 + 136) == 6 )
    *(_DWORD *)(a1 + 2152) |= 0x1000u;
  v50 = *(_DWORD *)(v49 + 124);
  if ( v50 == 2 )
  {
    *(_DWORD *)(v49 + 136) = 0;
LABEL_80:
    *(_WORD *)(a1 + 166) = 0;
    goto LABEL_81;
  }
  if ( v50 == 3 )
    goto LABEL_80;
LABEL_81:
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
    v61 = v75;
    if ( v75 )
    {
      *v75 = 0;
      *((_DWORD *)v61 + 2) = *(_DWORD *)(v59 + v51 + 152);
      *((_DWORD *)v61 + 3) = *(_DWORD *)(v59 + v51 + 156);
    }
  }
  else
  {
    v62 = v75;
    if ( !(unsigned int)BValidateDevmodeFormFields(*(void **)(a1 + 24), v51, (__int64)v75) )
    {
      VDefaultDevmodeFormFields(*(_QWORD *)(a1 + 2136), (__int64)*v33, *(_DWORD *)(a1 + 132) & 1);
      *v62 = 0;
      *((_DWORD *)v62 + 2) = 100 * (*v33)->dmPaperWidth;
      *((_DWORD *)v62 + 3) = 100 * (*v33)->dmPaperLength;
    }
  }
  v63 = *(_QWORD *)(*(_QWORD *)(a1 + 2136) + 328LL);
  PPDChangeOptionsViaID(v63, a1 + 2372, v60, 1u, (__int64)*v33);
  PPDChangeOptionsViaID(v63, a1 + 2372, v64, 4u, (__int64)*v33);
  PPDChangeOptionsViaID(v63, a1 + 2372, v65, 0, (__int64)*v33);
  PPDChangeOptionsViaID(v63, a1 + 2372, v66, 3u, (__int64)*v33);
  PPDChangeOptionsViaID(v63, a1 + 2372, v67, 0xAu, (__int64)*v33);
  PPDChangeOptionsViaID(v63, a1 + 2372, v68, 5u, (__int64)*v33);
  if ( ((*v33)->dmFields & 0x40) != 0 && (*v33)->dmDisplayFlags == 2 || *(_DWORD *)(*(_QWORD *)(a1 + 96) + 136LL) == 6 )
    *(_DWORD *)(*(_QWORD *)(a1 + 96) + 136LL) = 0;
  return 1;
}

```

## disassembly

```asm
0x1800034bc  mov     [rsp-40h+arg_18], r9
0x1800034c1  mov     [rsp-40h+arg_10], r8
0x1800034c6  mov     [rsp-40h+arg_8], rdx
0x1800034cb  push    rbp
0x1800034cc  push    rbx
0x1800034cd  push    rsi
0x1800034ce  push    rdi
0x1800034cf  push    r12
0x1800034d1  push    r13
0x1800034d3  push    r14
0x1800034d5  push    r15
0x1800034d7  mov     rbp, rsp
0x1800034da  sub     rsp, 68h
0x1800034de  mov     rsi, [rcx+2B8h]
0x1800034e5  lea     rdx, aPrintconfigDll; "PrintConfig.dll"
0x1800034ec  mov     rbx, [rcx+858h]
0x1800034f3  mov     rdi, rcx
0x1800034f6  xor     r13d, r13d
0x1800034f9  mov     r12d, r13d
0x1800034fc  mov     rcx, [rsi+28h]; unsigned __int16 *
0x180003500  call    ?DoesFullPathMatchFile@@YA_NPEBG0@Z; DoesFullPathMatchFile(ushort const *,ushort const *)
0x180003505  test    al, al
0x180003507  jz      short loc_18000350F
0x180003509  lea     edx, [r13+5Eh]
0x18000350d  jmp     short loc_180003528
0x18000350f  mov     rax, [rsi+8]
0x180003513  or      rdx, 0FFFFFFFFFFFFFFFFh
0x180003517  inc     rdx
0x18000351a  cmp     [rax+rdx*2], r13w
0x18000351f  jnz     short loc_180003517
0x180003521  lea     edx, ds:12h[rdx*2]
0x180003528  mov     r15d, [rbx+1Ch]
0x18000352c  mov     r9d, 2
0x180003532  add     r15d, [rbx+18h]
0x180003536  jz      loc_180003610
0x18000353c  mov     r8d, [rbx+20h]
0x180003540  add     r8, [rbx+148h]
0x180003547  jz      loc_180003610
0x18000354d  mov     r14d, r13d
0x180003550  cmp     [r8+2Ch], r9d
0x180003554  jz      loc_1800035F4
0x18000355a  cmp     [r8], r13d
0x18000355d  jz      short loc_18000356B
0x18000355f  mov     eax, [r8]
0x180003562  add     rax, [rbx+140h]
0x180003569  jmp     short loc_18000356E
0x18000356b  mov     rax, r13
0x18000356e  mov     r11d, [r8+34h]
0x180003572  test    r11d, r11d
0x180003575  jz      short loc_180003584
0x180003577  mov     r9d, [r8+38h]
0x18000357b  add     r9, [rbx+148h]
0x180003582  jmp     short loc_180003587
0x180003584  mov     r9, r13
0x180003587  test    rax, rax
0x18000358a  jz      loc_180003610
0x180003590  test    r11d, r11d
0x180003593  jz      short loc_180003610
0x180003595  test    r9, r9
0x180003598  jz      short loc_180003610
0x18000359a  or      rcx, 0FFFFFFFFFFFFFFFFh
0x18000359e  inc     rcx
0x1800035a1  cmp     [rax+rcx], r13b
0x1800035a5  jnz     short loc_18000359E
0x1800035a7  inc     edx
0x1800035a9  mov     r10d, r13d
0x1800035ac  add     edx, ecx
0x1800035ae  test    r11d, r11d
0x1800035b1  jz      short loc_1800035E9
0x1800035b3  mov     esi, r13d
0x1800035b6  cmp     [r9], r13d
0x1800035b9  jz      short loc_180003610
0x1800035bb  mov     ecx, [r9]
0x1800035be  add     rcx, [rbx+140h]
0x1800035c5  jz      short loc_180003610
0x1800035c7  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800035cb  inc     rax
0x1800035ce  cmp     [rcx+rax], r13b
0x1800035d2  jnz     short loc_1800035CB
0x1800035d4  cmp     r10d, eax
0x1800035d7  cmovb   r10d, eax
0x1800035db  mov     eax, [r8+30h]
0x1800035df  add     r9, rax
0x1800035e2  inc     esi
0x1800035e4  cmp     esi, r11d
0x1800035e7  jb      short loc_1800035B6
0x1800035e9  inc     edx
0x1800035eb  mov     r9d, 2
0x1800035f1  add     edx, r10d
0x1800035f4  inc     r14d
0x1800035f7  add     r8, 54h ; 'T'
0x1800035fb  cmp     r14d, r15d
0x1800035fe  jb      loc_180003550
0x180003604  add     edx, 9
0x180003607  mov     r12d, 1
0x18000360d  and     edx, 0FFFFFFF8h
0x180003610  mov     r15, [rdi+850h]
0x180003617  neg     r12d
0x18000361a  mov     rcx, r15
0x18000361d  sbb     r13d, r13d
0x180003620  xor     r12d, r12d
0x180003623  and     r13d, edx
0x180003626  mov     dword ptr [rbp+arg_8], r12d
0x18000362a  lea     rdx, [rbp+arg_0]
0x18000362e  mov     [rdi+0EACh], r13d
0x180003635  mov     dword ptr [rbp+arg_0], r12d
0x180003639  call    IsRawBinaryDataFromGPD
0x18000363e  test    eax, eax
0x180003640  js      loc_180003788
0x180003646  cmp     dword ptr [rbp+arg_0], r12d
0x18000364a  jnz     loc_180003788
0x180003650  lea     esi, [r13+3D0h]
0x180003657  cmp     esi, 3D0h
0x18000365d  jb      loc_180003788
0x180003663  mov     r12, [rdi+0D88h]
0x18000366a  lea     r8, [rbp+arg_8]
0x18000366e  mov     rcx, [rdi+18h]
0x180003672  mov     rdx, r12
0x180003675  mov     rax, [rdi+858h]
0x18000367c  mov     r14d, [rdi+84h]
0x180003683  mov     [rbp+var_18], rcx
0x180003687  mov     [rbp+arg_0], rax
0x18000368b  call    BCalcTotalOEMDMSize
0x180003690  test    eax, eax
0x180003692  jz      loc_180003785
0x180003698  mov     ecx, dword ptr [rbp+arg_8]
0x18000369b  lea     eax, [rsi+rcx]
0x18000369e  cmp     eax, ecx
0x1800036a0  jb      loc_180003785
0x1800036a6  mov     edx, eax; uBytes
0x1800036a8  mov     ecx, 40h ; '@'; uFlags
0x1800036ad  call    cs:__imp_LocalAlloc
0x1800036b4  nop     dword ptr [rax+rax+00h]
0x1800036b9  mov     rbx, rax
0x1800036bc  test    rax, rax
0x1800036bf  jz      loc_180003785
0x1800036c5  mov     r8, [rbp+arg_0]
0x1800036c9  and     r14d, 1
0x1800036cd  mov     r9, r15
0x1800036d0  mov     dword ptr [rsp+68h+var_48], r14d
0x1800036d5  mov     rcx, rax
0x1800036d8  call    PSBInitDriverDefaultDevmode
0x1800036dd  test    eax, eax
0x1800036df  jz      loc_180003771
0x1800036e5  mov     r15d, [r12+8]
0x1800036ea  test    r15d, r15d
0x1800036ed  jz      short loc_180003754
0x1800036ef  mov     r14d, esi
0x1800036f2  lea     rsi, [r12+18h]
0x1800036f7  add     r14, rbx
0x1800036fa  cmp     qword ptr [rsi+20h], 0
0x1800036ff  jz      short loc_180003747
0x180003701  mov     rdx, [r12]; void *
0x180003705  mov     r9d, 2; unsigned int
0x18000370b  mov     rcx, [rbp+var_18]; void *
0x18000370f  mov     r8, rsi; struct _OEM_PLUGIN_ENTRY *
0x180003712  mov     [rsp+68h+var_30], 0; struct _OEM_DMEXTRAHEADER *
0x18000371b  mov     [rsp+68h+var_38], r14; struct _OEM_DMEXTRAHEADER *
0x180003720  mov     [rsp+68h+var_40], rbx; struct _devicemodeW *
0x180003725  mov     [rsp+68h+var_48], 0; struct _devicemodeW *
0x18000372e  call    ?BCallOEMDevMode@@YAHPEAX0PEAU_OEM_PLUGIN_ENTRY@@KPEAU_devicemodeW@@2PEAU_OEM_DMEXTRAHEADER@@3@Z; BCallOEMDevMode(void *,void *,_OEM_PLUGIN_ENTRY *,ulong,_devicemodeW *,_devicemodeW *,_OEM_DMEXTRAHEADER *,_OEM_DMEXTRAHEADER *)
0x180003733  test    eax, eax
0x180003735  jz      short loc_180003771
0x180003737  cmp     dword ptr [rsi+40h], 0
0x18000373b  jz      short loc_180003747
0x18000373d  mov     eax, [rsi+40h]
0x180003740  mov     [rsi+38h], r14
0x180003744  add     r14, rax
0x180003747  add     rsi, 0B0h
0x18000374e  add     r15d, 0FFFFFFFFh
0x180003752  jnz     short loc_1800036FA
0x180003754  mov     r9d, dword ptr [rbp+arg_8]; unsigned int
0x180003758  xor     r12d, r12d
0x18000375b  mov     r8d, r13d; unsigned int
0x18000375e  mov     dword ptr [rsp+68h+var_48], r12d; int
0x180003763  mov     rdx, rbx; struct _devicemodeW *
0x180003766  call    ?PatchDevmodeSizeFieldsAndJTHdr@@YAJPEAXPEAU_devicemodeW@@KKH@Z; PatchDevmodeSizeFieldsAndJTHdr(void *,_devicemodeW *,ulong,ulong,int)
0x18000376b  test    eax, eax
0x18000376d  js      short loc_180003774
0x18000376f  jmp     short loc_18000378B
0x180003771  xor     r12d, r12d
0x180003774  mov     rcx, rbx; hMem
0x180003777  call    cs:__imp_LocalFree
0x18000377e  nop     dword ptr [rax+rax+00h]
0x180003783  jmp     short loc_180003788
0x180003785  xor     r12d, r12d
0x180003788  mov     rbx, r12
0x18000378b  lea     rsi, [rdi+58h]
0x18000378f  mov     [rsi], rbx
0x180003792  test    rbx, rbx
0x180003795  jz      loc_18000381E
0x18000379b  mov     rcx, [rdi+18h]; hPrinter
0x18000379f  mov     [rdi+28h], rbx
0x1800037a3  call    MyGetPrinter
0x1800037a8  mov     rbx, rax
0x1800037ab  test    rax, rax
0x1800037ae  jz      loc_180003847
0x1800037b4  mov     rax, [rax+38h]
0x1800037b8  test    rax, rax
0x1800037bb  jz      short loc_180003832
0x1800037bd  mov     rcx, [rdi+18h]
0x1800037c1  lea     rdx, [rdi+0EB4h]
0x1800037c8  mov     r9, [rdi+850h]
0x1800037cf  mov     r8, [rdi+858h]
0x1800037d6  mov     [rsp+68h+var_20], rcx; void *
0x1800037db  mov     rcx, [rdi+0D88h]
0x1800037e2  mov     [rsp+68h+var_28], rcx; struct _OEM_PLUGINS *
0x1800037e7  mov     rcx, [rsi]; struct _devicemodeW *
0x1800037ea  mov     [rsp+68h+var_30], rax; struct _devicemodeW *
0x1800037ef  mov     rax, [rdi+2B8h]
0x1800037f6  mov     [rsp+68h+var_40], rdx; __int64
0x1800037fb  mov     edx, [rdi+0EACh]; unsigned int
0x180003801  mov     [rsp+68h+var_48], rax; __int64
0x180003806  call    BValidateAndMergeDevmodeWithOemPlugins
0x18000380b  test    eax, eax
0x18000380d  jnz     short loc_180003832
0x18000380f  mov     rcx, rbx; hMem
0x180003812  call    cs:__imp_LocalFree
0x180003819  nop     dword ptr [rax+rax+00h]
0x18000381e  xor     eax, eax
0x180003820  add     rsp, 68h
0x180003824  pop     r15
0x180003826  pop     r14
0x180003828  pop     r13
0x18000382a  pop     r12
0x18000382c  pop     rdi
0x18000382d  pop     rsi
0x18000382e  pop     rbx
0x18000382f  pop     rbp
0x180003830  retn
0x180003832  mov     rcx, rbx; hMem
0x180003835  call    cs:__imp_LocalFree
0x18000383c  nop     dword ptr [rax+rax+00h]
0x180003841  lea     rbx, [rdi+58h]
0x180003845  jmp     short loc_18000384A
0x180003847  mov     rbx, rsi
0x18000384a  mov     rax, [rdi+18h]
0x18000384e  lea     rcx, [rdi+0EB4h]
0x180003855  mov     r9, [rdi+850h]
0x18000385c  mov     r8, [rdi+858h]
0x180003863  mov     edx, [rdi+0EACh]; unsigned int
0x180003869  mov     [rsp+68h+var_20], rax; void *
0x18000386e  mov     rax, [rdi+0D88h]
0x180003875  mov     [rsp+68h+var_28], rax; struct _OEM_PLUGINS *
0x18000387a  mov     rax, [rbp+arg_10]
0x18000387e  mov     [rsp+68h+var_30], rax; struct _devicemodeW *
0x180003883  mov     rax, [rdi+2B8h]
0x18000388a  mov     [rsp+68h+var_40], rcx; __int64
0x18000388f  mov     rcx, [rsi]; struct _devicemodeW *
0x180003892  mov     [rsp+68h+var_48], rax; __int64
0x180003897  call    BValidateAndMergeDevmodeWithOemPlugins
0x18000389c  test    eax, eax
0x18000389e  jz      loc_18000381E
0x1800038a4  mov     rcx, [rsi]
0x1800038a7  lea     rax, [rdi+0B0h]
0x1800038ae  lea     r15, [rdi+944h]
0x1800038b5  mov     [rsp+68h+var_48], rax
0x1800038ba  mov     r8d, 100h
0x1800038c0  mov     rdx, r15
0x1800038c3  movzx   r9d, word ptr [rcx+44h]
0x1800038c8  add     r9, rcx
0x1800038cb  mov     rcx, [rdi+850h]
0x1800038d2  mov     [rdi+60h], r9
0x1800038d6  add     r9, 0C4h
0x1800038dd  call    CombineOptionArray
0x1800038e2  mov     rax, [rdi+858h]
0x1800038e9  mov     r13d, 1
0x1800038ef  mov     [rdi+940h], r13d
0x1800038f6  test    byte ptr [rax+8Ch], 8
0x1800038fd  jz      short loc_18000390E
0x1800038ff  mov     rax, [rbx]
0x180003902  lea     ecx, [r13+1]
0x180003906  cmp     cx, [rax+5Ch]
0x18000390a  jz      short loc_180003921
0x18000390c  jmp     short loc_180003918
0x18000390e  mov     rax, [rdi+60h]
0x180003912  cmp     [rax+7Ch], r12d
0x180003916  jnz     short loc_180003921
0x180003918  mov     eax, r12d
0x18000391b  test    [rdi+50h], r13b
0x18000391f  jz      short loc_180003924
0x180003921  mov     eax, r13d
0x180003924  mov     [rdi+2C4h], eax
0x18000392a  mov     rax, [rdi+0D88h]
0x180003931  mov     dword ptr [rbp+arg_0], r12d
0x180003935  mov     dword ptr [rbp+arg_8], r12d
0x180003939  mov     r14d, [rax+8]
0x18000393d  lea     rbx, [rax+18h]
0x180003941  test    r14d, r14d
0x180003944  jz      loc_1800039D6
0x18000394a  mov     rax, [rbx+20h]
0x18000394e  test    rax, rax
0x180003951  jz      short loc_1800039B0
0x180003953  mov     [rdi+20h], rax
0x180003957  mov     rax, [rbx+28h]
0x18000395b  mov     [rdi+8], rax
0x18000395f  mov     rax, [rbx+38h]
0x180003963  mov     [rdi+30h], rax
0x180003967  cmp     [rbx+48h], r12
0x18000396b  jz      short loc_1800039B0
  ... truncated ...
```
