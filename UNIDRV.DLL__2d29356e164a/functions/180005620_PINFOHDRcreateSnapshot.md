# PINFOHDRcreateSnapshot

- ea: `0x180005620`
- end: `0x180005be6`
- name: `PINFOHDRcreateSnapshot`
- size: `1478`
- prototype: ``
- caller_count: `5`
- callee_count: `9`
- tags: `broker_com_uri`

## callers

- `0x18000420c`
- `0x180023e18`
- `0x18003ea30`
- `0x180042518`
- `0x18004413c`

## callees

- `0x1800039d8`
- `0x180003c70`
- `0x180005500`
- `0x180005620`
- `0x1800064a0`
- `0x180006970`
- `0x180007220`
- `0x180007270`
- `0x180042e74`

## import_xrefs

- `KERNEL32!LocalFree` at `0x180005696`
- `KERNEL32!LocalFree` at `0x180005696`
- `KERNEL32!LocalAlloc` at `0x1800056c8`
- `KERNEL32!LocalAlloc` at `0x1800056c8`

## string_xrefs

- `0x18000567e`: `Fatal: PINFOHDRcreateSnapshot - INFOHEADER size overflow.`
- `0x180005685`: `PINFOHDRcreateSnapshot`
- `0x180005b56`: `PINFOHDRcreateSnapshot`
- `0x180005b4f`: `Fatal: PINFOHDRcreateSnapshot - unable to alloc %d bytes.`

## pseudocode

```c
__int64 __fastcall PINFOHDRcreateSnapshot(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  __int64 v4; // r10
  __int64 v6; // r12
  unsigned int v7; // ecx
  __int64 i; // r9
  __int64 v9; // rdx
  unsigned int v10; // ebp
  int v12; // edi
  char *v13; // rax
  __int64 v14; // rdx
  __int64 v15; // rbx
  _DWORD *v16; // rbp
  __int64 v17; // r13
  unsigned int j; // r9d
  __int64 v19; // rax
  __int64 v20; // r8
  __int64 v21; // rdx
  unsigned int v22; // r11d
  unsigned int v23; // r10d
  __int64 v24; // rax
  __int64 v25; // r11
  unsigned int v26; // ecx
  unsigned int v27; // edi
  __int64 v28; // r9
  __int64 v29; // rax
  unsigned int v30; // r10d
  __int64 v31; // rcx
  _DWORD *v32; // rdx
  __int64 v33; // rcx
  __int64 v34; // r8
  unsigned int v35; // r10d
  int v36; // r9d
  int v37; // edx
  unsigned int v38; // r12d
  unsigned int v39; // r11d
  int v40; // eax
  __int64 v41; // rdi
  unsigned int v42; // r15d
  unsigned int k; // eax
  int v44; // r8d
  unsigned int v45; // ecx
  unsigned int v46; // r11d
  unsigned __int64 v47; // rax
  __int64 v48; // r13
  int v49; // ecx
  signed int v50; // ecx
  __int64 v51; // rdi
  __int64 v52; // rbx
  unsigned int v53; // eax
  unsigned int v54; // edx
  unsigned int v55; // eax
  __int64 v56; // rax
  unsigned __int64 v57; // rcx
  unsigned int v58; // ecx
  unsigned int v59; // edx
  unsigned int v60; // eax
  unsigned int v61; // eax
  __int64 v62; // rdx
  __int64 m; // r9
  __int64 v64; // rax
  int v65; // r9d
  int v66; // [rsp+48h] [rbp-80h]
  int v67; // [rsp+50h] [rbp-78h] BYREF
  unsigned int v68; // [rsp+54h] [rbp-74h]
  unsigned int v69; // [rsp+58h] [rbp-70h]
  unsigned int v70; // [rsp+5Ch] [rbp-6Ch]
  int v71; // [rsp+60h] [rbp-68h]
  __int64 v72; // [rsp+68h] [rbp-60h]
  __int64 v73; // [rsp+70h] [rbp-58h]
  unsigned int v74; // [rsp+D0h] [rbp+8h] BYREF
  __int64 v75; // [rsp+D8h] [rbp+10h]
  int v76; // [rsp+E0h] [rbp+18h]
  __int64 v77; // [rsp+E8h] [rbp+20h]

  v77 = a4;
  v76 = a3;
  v75 = a2;
  v4 = *(unsigned int *)(a1 + 120);
  v6 = a2;
  v7 = v4;
  for ( i = 0; (unsigned int)i < (unsigned int)v4; i = (unsigned int)(i + 1) )
  {
    LODWORD(v9) = i;
    if ( *(_BYTE *)(v6 + 2LL * (unsigned int)i + 1) )
    {
      do
      {
        ++v7;
        v9 = *(unsigned __int8 *)(v6 + 2LL * (unsigned int)v9 + 1);
      }
      while ( *(_BYTE *)(v6 + 2 * v9 + 1) );
    }
  }
  v10 = v7 + 8;
  if ( v7 + 8 < v7 )
    goto LABEL_5;
  v46 = -1;
  v47 = 8LL * v10;
  if ( v47 > 0xFFFFFFFF )
    goto LABEL_5;
  v48 = (unsigned int)(v47 + 1276);
  v71 = v47 + 1276;
  if ( (unsigned int)v47 >= 0xFFFFFB04 )
    goto LABEL_5;
  v49 = 84 * v4;
  if ( (unsigned __int64)(84 * v4) > 0xFFFFFFFF )
    goto LABEL_5;
  v42 = v49 + v48;
  if ( v49 + (int)v48 < (unsigned int)v48 )
    goto LABEL_5;
  i = 0;
  a3 = 0;
  v50 = 0;
  while ( (unsigned int)a3 < (unsigned int)v4 )
  {
    v51 = *(_QWORD *)(a1 + 112);
    v52 = 396LL * (unsigned int)a3;
    v53 = *(_DWORD *)(v52 + v51 + 388);
    if ( v53 == 0xFFFF )
    {
      v46 = 56;
    }
    else
    {
      v54 = *(_DWORD *)(*(_QWORD *)(a1 + 192) + 4LL * v53);
      v55 = v54 + *(_DWORD *)(*(_QWORD *)(a1 + 200) + 4LL * v53);
      if ( v55 >= v54 )
        v46 = v55;
      v50 = v55 < v54 ? 0x80070216 : 0;
    }
    if ( v50 >= 0 )
    {
      v56 = v46;
      v46 = -1;
      v57 = v56 * *(unsigned int *)(v52 + v51 + 392);
      if ( v57 > 0xFFFFFFFF )
        goto LABEL_5;
      v58 = i + v57;
      v59 = i;
      v60 = -1;
      if ( v58 >= (unsigned int)i )
        v60 = v58;
      i = v60;
      v50 = v58 < v59 ? 0x80070216 : 0;
    }
    else
    {
      v46 = -1;
    }
    a3 = (unsigned int)(a3 + 1);
    if ( v50 < 0 )
      goto LABEL_5;
  }
  if ( (unsigned int)i + v42 < v42 )
  {
LABEL_5:
    WriteDbgTraceErrorGpd("PINFOHDRcreateSnapshot", "Fatal: PINFOHDRcreateSnapshot - INFOHEADER size overflow.", a3, i);
    return 0;
  }
  v12 = i + v42;
  v13 = (char *)LocalAlloc(0x40u, (unsigned int)i + v42);
  v15 = (__int64)v13;
  if ( !v13 )
  {
    WriteDbgTraceErrorGpd("PINFOHDRcreateSnapshot", "Fatal: PINFOHDRcreateSnapshot - unable to alloc %d bytes.", v12);
    return 0;
  }
  if ( !(unsigned int)BinitCommandTable(v13 + 880, v14, a1, v6) )
    goto LABEL_6;
  *(_QWORD *)(v15 + 504) = v15;
  *(_DWORD *)(v15 + 408) = 880;
  *(_DWORD *)(v15 + 404) = 99;
  *(_DWORD *)(v15 + 448) = 1276;
  *(_DWORD *)(v15 + 444) = v10;
  if ( !(unsigned int)BinitGPDdriverInfo(v15 + 400, a1, v6) )
    goto LABEL_6;
  *(_DWORD *)(v15 + 56) = 64;
  v16 = (_DWORD *)(v15 + 204);
  *(_DWORD *)(v15 + 60) = 400;
  *(_DWORD *)v15 = **(_DWORD **)(a1 + 88);
  *(_DWORD *)(v15 + 4) = *(_DWORD *)(*(_QWORD *)(a1 + 88) + 4LL);
  *(_DWORD *)(v15 + 8) = *(_DWORD *)(*(_QWORD *)(a1 + 88) + 8LL);
  *(_DWORD *)(v15 + 12) = *(_DWORD *)(*(_QWORD *)(a1 + 88) + 12LL);
  *(_DWORD *)(v15 + 16) = *(_DWORD *)(*(_QWORD *)(a1 + 88) + 16LL);
  *(_DWORD *)(v15 + 20) = *(_DWORD *)(*(_QWORD *)(a1 + 88) + 20LL);
  *(_DWORD *)(v15 + 24) = *(_DWORD *)(*(_QWORD *)(a1 + 88) + 24LL);
  *(_QWORD *)(v15 + 48) = a1;
  *(_QWORD *)(v15 + 40) = 0;
  *(_QWORD *)(v15 + 392) = v15;
  *(_DWORD *)(v15 + 96) = v48;
  *(_DWORD *)(v15 + 100) = *(_DWORD *)(v15 + 464);
  *(_DWORD *)(v15 + 104) = *(_DWORD *)(v15 + 460);
  *(_DWORD *)(v15 + 116) = 0;
  *(_DWORD *)(v15 + 224) = *(_DWORD *)(v15 + 456);
  *(_DWORD *)(v15 + 220) = *(_DWORD *)(v15 + 452);
  if ( *(_DWORD *)(v15 + 832) != -1 )
    *v16 |= 2u;
  if ( *(_DWORD *)(v15 + 776) != -1 )
    *v16 |= 0x40u;
  if ( !(unsigned int)BinitUIinfo(v15 + 64, a1, v6) )
    goto LABEL_6;
  v17 = v15 + v48;
  for ( j = 0; ; j = v36 + 1 )
  {
    LODWORD(v77) = j;
    if ( j >= *(_DWORD *)(a1 + 120) )
      break;
    v19 = *(_QWORD *)(a1 + 112);
    v20 = 84LL * j;
    v21 = 396LL * j;
    v67 = 0;
    v72 = v20;
    v22 = *(_DWORD *)(v21 + v19 + 392);
    v23 = *(_DWORD *)(v21 + v19 + 388);
    *(_DWORD *)(v20 + v17 + 52) = v22;
    *(_DWORD *)(v20 + v17 + 56) = v42;
    *(_DWORD *)(v20 + v17 + 16) = 0;
    v24 = *(_QWORD *)(a1 + 184);
    v68 = v22;
    v25 = v21 + *(_QWORD *)(a1 + 112);
    v70 = v23;
    v26 = *(_DWORD *)(v24 + 44);
    v27 = *(_DWORD *)(v24 + 32);
    v69 = v26;
    v73 = v25;
    while ( v27 < v26 )
    {
      v28 = *(_QWORD *)(a1 + 176);
      v29 = 32LL * v27;
      v30 = *(_DWORD *)(v29 + v28 + 12);
      if ( v30 )
      {
        v31 = *(unsigned int *)(v29 + v28 + 16);
        if ( (int)v31 + 4 < (unsigned int)v31 || (unsigned int)(v31 + 4) > 0x18C )
          v32 = 0;
        else
          v32 = (_DWORD *)(v25 + v31);
        v33 = *(unsigned int *)(v29 + v28 + 20);
        if ( (unsigned int)v33 + v30 < (unsigned int)v33 )
          goto LABEL_6;
        if ( (unsigned int)v33 + v30 > 0x54 )
          goto LABEL_6;
        v74 = 0;
        v34 = v17 + v33 + v20;
        if ( !v34 || (unsigned int)EextractValueFromTree(a1, v27, v34, v30, &v67, *v32, v6, 0, &v74) != 1 )
          goto LABEL_6;
        v20 = v72;
        v26 = v69;
        v25 = v73;
      }
      ++v27;
    }
    v35 = v70;
    v36 = v77;
    if ( v70 == 0xFFFF )
    {
      v37 = 0;
      v38 = 56;
    }
    else
    {
      v38 = *(_DWORD *)(*(_QWORD *)(a1 + 192) + 4LL * v70);
      v37 = *(_DWORD *)(*(_QWORD *)(a1 + 200) + 4LL * v70);
      *(_DWORD *)(v15 + 4LL * v70 + 268) = v71 + 84 * v77;
    }
    v39 = v68;
    v40 = v68 * v38;
    v41 = v15 + *(unsigned int *)(v20 + v17 + 56);
    v67 = v37;
    *(_DWORD *)(v20 + v17 + 28) = v35;
    *(_DWORD *)(v20 + v17 + 48) = v38;
    v42 += v40;
    for ( k = 0; ; k = v74 + 1 )
    {
      v74 = k;
      if ( k >= v39 )
        break;
      if ( v37 )
      {
        v45 = v42;
        v44 = v15 + v42;
        v42 += v37;
      }
      else
      {
        v44 = 0;
        v45 = 0;
      }
      *(_DWORD *)(v41 + 44) = v45;
      if ( !(unsigned int)BinitOptionFields(v41, v38, v44, v37, a1, v36, k, v75, v15, v66) )
        goto LABEL_6;
      v37 = v67;
      v36 = v77;
      v39 = v68;
      v41 += v38;
    }
    v6 = v75;
  }
  if ( v76 && !(unsigned int)BCheckGPDSemantics(v15, v6) )
  {
LABEL_6:
    LocalFree((HLOCAL)v15);
    return 0;
  }
  v61 = *(_DWORD *)(v15 + 272);
  if ( v61 )
  {
    v62 = *(_QWORD *)(v15 + 392) + v61;
    if ( v62 )
    {
      for ( m = 0; (unsigned int)m < *(_DWORD *)(v62 + 52); m = (unsigned int)(v65 + 1) )
      {
        v64 = PGetIndexedOption(v15 + 64, v62, (unsigned int)m, m);
        if ( v64 && *(_DWORD *)(v64 + 80) == 256 )
        {
          *v16 |= 0x20u;
          *(_DWORD *)(v15 + 208) = v65;
          return v15;
        }
      }
    }
  }
  return v15;
}

```

## disassembly

```asm
0x180005620  mov     [rsp+arg_18], r9
0x180005625  mov     [rsp+arg_10], r8d
0x18000562a  mov     [rsp+arg_8], rdx
0x18000562f  push    rbx
0x180005630  push    rbp
0x180005631  push    rsi
0x180005632  push    rdi
0x180005633  push    r12
0x180005635  push    r13
0x180005637  push    r14
0x180005639  push    r15
0x18000563b  sub     rsp, 88h
0x180005642  mov     r10d, [rcx+78h]
0x180005646  xor     r14d, r14d
0x180005649  mov     rsi, rcx
0x18000564c  mov     r12, rdx
0x18000564f  mov     ecx, r10d
0x180005652  mov     r9d, r14d
0x180005655  test    r10d, r10d
0x180005658  jz      short loc_180005673
0x18000565a  mov     eax, r9d
0x18000565d  mov     edx, r9d
0x180005660  cmp     [r12+rax*2+1], r14b
0x180005665  jnz     loc_180005B24
0x18000566b  inc     r9d
0x18000566e  cmp     r9d, r10d
0x180005671  jb      short loc_18000565A
0x180005673  lea     ebp, [rcx+8]
0x180005676  cmp     ebp, ecx
0x180005678  jnb     loc_180005A39
0x18000567e  lea     rdx, aFatalPinfohdrc; "Fatal: PINFOHDRcreateSnapshot - INFOHEA"...
0x180005685  lea     rcx, aPinfohdrcreate; "PINFOHDRcreateSnapshot"
0x18000568c  call    WriteDbgTraceErrorGpd
0x180005691  jmp     short loc_18000569C
0x180005693  mov     rcx, rbx; hMem
0x180005696  call    cs:__imp_LocalFree
0x18000569c  xor     eax, eax
0x18000569e  add     rsp, 88h
0x1800056a5  pop     r15
0x1800056a7  pop     r14
0x1800056a9  pop     r13
0x1800056ab  pop     r12
0x1800056ad  pop     rdi
0x1800056ae  pop     rsi
0x1800056af  pop     rbp
0x1800056b0  pop     rbx
0x1800056b1  retn
0x1800056b2  lea     eax, [r9+r15]
0x1800056b6  mov     edi, r11d
0x1800056b9  cmp     eax, r15d
0x1800056bc  cmovnb  edi, eax
0x1800056bf  jb      short loc_18000567E
0x1800056c1  mov     edx, edi; uBytes
0x1800056c3  mov     ecx, 40h ; '@'; uFlags
0x1800056c8  call    cs:__imp_LocalAlloc
0x1800056ce  mov     rbx, rax
0x1800056d1  test    rax, rax
0x1800056d4  jz      loc_180005B4C
0x1800056da  lea     rcx, [rax+370h]
0x1800056e1  mov     r9, r12
0x1800056e4  mov     r8, rsi
0x1800056e7  call    BinitCommandTable
0x1800056ec  test    eax, eax
0x1800056ee  jz      short loc_180005693
0x1800056f0  lea     rdi, [rbx+190h]
0x1800056f7  mov     r8, r12
0x1800056fa  mov     rcx, rdi
0x1800056fd  mov     [rdi+68h], rbx
0x180005701  mov     rdx, rsi
0x180005704  mov     dword ptr [rdi+8], 370h
0x18000570b  mov     dword ptr [rdi+4], 63h ; 'c'
0x180005712  mov     dword ptr [rdi+30h], 4FCh
0x180005719  mov     [rdi+2Ch], ebp
0x18000571c  call    BinitGPDdriverInfo
0x180005721  test    eax, eax
0x180005723  jz      loc_180005693
0x180005729  mov     dword ptr [rbx+38h], 40h ; '@'
0x180005730  lea     rbp, [rbx+0CCh]
0x180005737  mov     dword ptr [rbx+3Ch], 190h
0x18000573e  mov     rax, [rsi+58h]
0x180005742  mov     ecx, [rax]
0x180005744  mov     [rbx], ecx
0x180005746  mov     rax, [rsi+58h]
0x18000574a  mov     ecx, [rax+4]
0x18000574d  mov     [rbx+4], ecx
0x180005750  mov     rax, [rsi+58h]
0x180005754  mov     ecx, [rax+8]
0x180005757  mov     [rbx+8], ecx
0x18000575a  mov     rax, [rsi+58h]
0x18000575e  mov     ecx, [rax+0Ch]
0x180005761  mov     [rbx+0Ch], ecx
0x180005764  mov     rax, [rsi+58h]
0x180005768  mov     ecx, [rax+10h]
0x18000576b  mov     [rbx+10h], ecx
0x18000576e  mov     rax, [rsi+58h]
0x180005772  mov     ecx, [rax+14h]
0x180005775  mov     [rbx+14h], ecx
0x180005778  mov     rax, [rsi+58h]
0x18000577c  mov     ecx, [rax+18h]
0x18000577f  mov     [rbx+18h], ecx
0x180005782  mov     [rbx+30h], rsi
0x180005786  mov     [rbx+28h], r14
0x18000578a  mov     [rbx+188h], rbx
0x180005791  mov     [rbx+60h], r13d
0x180005795  mov     eax, [rdi+40h]
0x180005798  mov     [rbx+64h], eax
0x18000579b  mov     eax, [rdi+3Ch]
0x18000579e  mov     [rbx+68h], eax
0x1800057a1  mov     [rbx+74h], r14d
0x1800057a5  mov     eax, [rdi+38h]
0x1800057a8  mov     [rbx+0E0h], eax
0x1800057ae  mov     eax, [rdi+34h]
0x1800057b1  mov     [rbx+0DCh], eax
0x1800057b7  mov     eax, 0FFFFFFFFh
0x1800057bc  cmp     [rdi+1B0h], eax
0x1800057c2  jnz     loc_180005B67
0x1800057c8  cmp     [rdi+178h], eax
0x1800057ce  jnz     loc_180005B70
0x1800057d4  mov     r8, r12
0x1800057d7  lea     rcx, [rbx+40h]
0x1800057db  mov     rdx, rsi
0x1800057de  call    BinitUIinfo
0x1800057e3  test    eax, eax
0x1800057e5  jz      loc_180005693
0x1800057eb  add     r13, rbx
0x1800057ee  xor     r9d, r9d
0x1800057f1  mov     dword ptr [rsp+0C8h+arg_18], r9d
0x1800057f9  cmp     r9d, [rsi+78h]
0x1800057fd  jnb     loc_180005B79
0x180005803  mov     rax, [rsi+70h]
0x180005807  mov     ecx, r9d
0x18000580a  imul    r8, rcx, 54h ; 'T'
0x18000580e  imul    rdx, rcx, 18Ch
0x180005815  mov     [rsp+0C8h+var_78], r14d
0x18000581a  mov     [rsp+0C8h+var_60], r8
0x18000581f  mov     r11d, [rdx+rax+188h]
0x180005827  mov     r10d, [rdx+rax+184h]
0x18000582f  mov     [r8+r13+34h], r11d
0x180005834  mov     [r8+r13+38h], r15d
0x180005839  mov     [r8+r13+10h], r14d
0x18000583e  mov     rax, [rsi+0B8h]
0x180005845  mov     [rsp+0C8h+var_74], r11d
0x18000584a  mov     r11, [rsi+70h]
0x18000584e  add     r11, rdx
0x180005851  mov     [rsp+0C8h+var_6C], r10d
0x180005856  mov     ecx, [rax+2Ch]
0x180005859  mov     edi, [rax+20h]
0x18000585c  mov     [rsp+0C8h+var_70], ecx
0x180005860  mov     [rsp+0C8h+var_58], r11
0x180005865  cmp     edi, ecx
0x180005867  jnb     loc_18000592F
0x18000586d  mov     r9, [rsi+0B0h]
0x180005874  mov     eax, edi
0x180005876  shl     rax, 5
0x18000587a  mov     r10d, [rax+r9+0Ch]
0x18000587f  test    r10d, r10d
0x180005882  jz      loc_180005921
0x180005888  mov     ecx, [rax+r9+10h]
0x18000588d  lea     edx, [rcx+4]
0x180005890  cmp     edx, ecx
0x180005892  jb      loc_180005928
0x180005898  cmp     edx, 18Ch
0x18000589e  ja      loc_180005928
0x1800058a4  lea     rdx, [r11+rcx]
0x1800058a8  mov     ecx, [rax+r9+14h]
0x1800058ad  lea     eax, [rcx+r10]
0x1800058b1  cmp     eax, ecx
0x1800058b3  jb      loc_180005693
0x1800058b9  cmp     eax, 54h ; 'T'
0x1800058bc  ja      loc_180005693
0x1800058c2  add     r8, rcx
0x1800058c5  mov     [rsp+0C8h+arg_0], r14d
0x1800058cd  add     r8, r13
0x1800058d0  jz      loc_180005693
0x1800058d6  lea     rax, [rsp+0C8h+arg_0]
0x1800058de  mov     r9d, r10d
0x1800058e1  mov     [rsp+0C8h+var_88], rax
0x1800058e6  mov     rcx, rsi
0x1800058e9  mov     eax, [rdx]
0x1800058eb  mov     edx, edi
0x1800058ed  mov     dword ptr [rsp+0C8h+var_90], r14d
0x1800058f2  mov     [rsp+0C8h+var_98], r12
0x1800058f7  mov     [rsp+0C8h+var_A0], eax
0x1800058fb  lea     rax, [rsp+0C8h+var_78]
0x180005900  mov     [rsp+0C8h+var_A8], rax
0x180005905  call    EextractValueFromTree
0x18000590a  cmp     eax, 1
0x18000590d  jnz     loc_180005693
0x180005913  mov     r8, [rsp+0C8h+var_60]
0x180005918  mov     ecx, [rsp+0C8h+var_70]
0x18000591c  mov     r11, [rsp+0C8h+var_58]
0x180005921  inc     edi
0x180005923  jmp     loc_180005865
0x180005928  xor     edx, edx
0x18000592a  jmp     loc_1800058A8
0x18000592f  mov     r10d, [rsp+0C8h+var_6C]
0x180005934  mov     r9d, dword ptr [rsp+0C8h+arg_18]
0x18000593c  cmp     r10d, 0FFFFh
0x180005943  jnz     loc_1800059FD
0x180005949  xor     edx, edx
0x18000594b  lea     r12d, [rdx+38h]
0x18000594f  mov     r11d, [rsp+0C8h+var_74]
0x180005954  mov     eax, r12d
0x180005957  mov     edi, [r8+r13+38h]
0x18000595c  imul    eax, r11d
0x180005960  add     rdi, rbx
0x180005963  mov     [rsp+0C8h+var_78], edx
0x180005967  mov     [r8+r13+1Ch], r10d
0x18000596c  mov     [r8+r13+30h], r12d
0x180005971  add     r15d, eax
0x180005974  xor     eax, eax
0x180005976  mov     [rsp+0C8h+arg_0], eax
0x18000597d  cmp     eax, r11d
0x180005980  jb      short loc_180005992
0x180005982  mov     r12, [rsp+0C8h+arg_8]
0x18000598a  inc     r9d
0x18000598d  jmp     loc_1800057F1
0x180005992  test    edx, edx
0x180005994  jnz     loc_180005A28
0x18000599a  xor     r8d, r8d
0x18000599d  xor     ecx, ecx
0x18000599f  mov     [rsp+0C8h+var_88], rbx
0x1800059a4  mov     [rdi+2Ch], ecx
0x1800059a7  mov     rcx, [rsp+0C8h+arg_8]
0x1800059af  mov     [rsp+0C8h+var_90], rcx
0x1800059b4  mov     rcx, rdi
0x1800059b7  mov     dword ptr [rsp+0C8h+var_98], eax
0x1800059bb  mov     [rsp+0C8h+var_A0], r9d
0x1800059c0  mov     r9d, edx
0x1800059c3  mov     edx, r12d
0x1800059c6  mov     [rsp+0C8h+var_A8], rsi
0x1800059cb  call    BinitOptionFields
0x1800059d0  test    eax, eax
0x1800059d2  jz      loc_180005693
0x1800059d8  mov     edx, [rsp+0C8h+var_78]
0x1800059dc  mov     r9d, dword ptr [rsp+0C8h+arg_18]
0x1800059e4  mov     r11d, [rsp+0C8h+var_74]
0x1800059e9  mov     eax, r12d
0x1800059ec  add     rdi, rax
0x1800059ef  mov     eax, [rsp+0C8h+arg_0]
0x1800059f6  inc     eax
0x1800059f8  jmp     loc_180005976
0x1800059fd  mov     rax, [rsi+0C0h]
0x180005a04  mov     r12d, [rax+r10*4]
0x180005a08  mov     rax, [rsi+0C8h]
0x180005a0f  mov     edx, [rax+r10*4]
0x180005a13  imul    eax, r9d, 54h ; 'T'
0x180005a17  add     eax, [rsp+0C8h+var_68]
0x180005a1b  mov     [rbx+r10*4+10Ch], eax
0x180005a23  jmp     loc_18000594F
0x180005a28  mov     r8d, r15d
0x180005a2b  mov     ecx, r15d
0x180005a2e  add     r8, rbx
0x180005a31  add     r15d, edx
0x180005a34  jmp     loc_18000599F
0x180005a39  mov     eax, ebp
0x180005a3b  mov     r11d, 0FFFFFFFFh
0x180005a41  shl     rax, 3
0x180005a45  cmp     rax, r11
0x180005a48  ja      loc_18000567E
0x180005a4e  lea     r13d, [rax+4FCh]
0x180005a55  mov     [rsp+0C8h+var_68], r13d
0x180005a5a  cmp     r13d, 4FCh
0x180005a61  jb      loc_18000567E
0x180005a67  imul    rcx, r10, 54h ; 'T'
0x180005a6b  cmp     rcx, r11
0x180005a6e  ja      loc_18000567E
0x180005a74  lea     r15d, [rcx+r13]
0x180005a78  cmp     r15d, r13d
0x180005a7b  jb      loc_18000567E
0x180005a81  mov     r9d, r14d
0x180005a84  mov     r8d, r14d
0x180005a87  mov     ecx, r14d
0x180005a8a  cmp     r8d, r10d
0x180005a8d  jnb     loc_1800056B2
0x180005a93  mov     rdi, [rsi+70h]
0x180005a97  mov     eax, r8d
0x180005a9a  imul    rbx, rax, 18Ch
0x180005aa1  mov     eax, [rbx+rdi+184h]
0x180005aa8  cmp     eax, 0FFFFh
0x180005aad  jz      loc_180005B3A
0x180005ab3  mov     ecx, eax
0x180005ab5  mov     rax, [rsi+0C0h]
0x180005abc  mov     edx, [rax+rcx*4]
0x180005abf  mov     rax, [rsi+0C8h]
0x180005ac6  mov     eax, [rax+rcx*4]
0x180005ac9  add     eax, edx
0x180005acb  cmp     eax, edx
0x180005acd  cmovnb  r11d, eax
0x180005ad1  sbb     ecx, ecx
0x180005ad3  and     ecx, 80070216h
0x180005ad9  jmp     short loc_180005B40
0x180005adb  mov     ecx, [rbx+rdi+188h]
0x180005ae2  mov     eax, r11d
0x180005ae5  mov     r11d, 0FFFFFFFFh
0x180005aeb  imul    rcx, rax
0x180005aef  cmp     rcx, r11
0x180005af2  ja      loc_18000567E
0x180005af8  add     ecx, r9d
0x180005afb  mov     edx, r9d
  ... truncated ...
```
