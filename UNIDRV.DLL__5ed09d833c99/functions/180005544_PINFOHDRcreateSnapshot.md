# PINFOHDRcreateSnapshot

- ea: `0x180005544`
- end: `0x180005b17`
- name: `PINFOHDRcreateSnapshot`
- size: `1491`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, __int64)`
- caller_count: `5`
- callee_count: `9`
- tags: `broker_com_uri`

## callers

- `0x18002431c`
- `0x18003fb40`
- `0x1800436cc`
- `0x180045334`
- `0x1800453d0`

## callees

- `0x1800039ac`
- `0x180003c88`
- `0x180005420`
- `0x180005544`
- `0x1800063d0`
- `0x1800068a0`
- `0x180007150`
- `0x1800071a0`
- `0x180043d98`

## import_xrefs

- `KERNEL32!LocalFree` at `0x1800055ba`
- `KERNEL32!LocalFree` at `0x1800055ba`
- `KERNEL32!LocalAlloc` at `0x1800055f3`
- `KERNEL32!LocalAlloc` at `0x1800055f3`

## string_xrefs

- `0x1800055a2`: `Fatal: PINFOHDRcreateSnapshot - INFOHEADER size overflow.`
- `0x1800055a9`: `PINFOHDRcreateSnapshot`
- `0x180005a87`: `PINFOHDRcreateSnapshot`
- `0x180005a80`: `Fatal: PINFOHDRcreateSnapshot - unable to alloc %d bytes.`

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
  HLOCAL v13; // rax
  int v14; // edx
  __int64 v15; // rbx
  unsigned int v16; // r9d
  _DWORD *v17; // rbp
  __int64 v18; // r13
  unsigned int j; // r9d
  __int64 v20; // rax
  __int64 v21; // r8
  __int64 v22; // rdx
  unsigned int v23; // r11d
  unsigned int v24; // r10d
  __int64 v25; // rax
  __int64 v26; // r11
  unsigned int v27; // ecx
  unsigned int v28; // edi
  __int64 v29; // r9
  __int64 v30; // rax
  unsigned int v31; // r10d
  __int64 v32; // rcx
  unsigned int *v33; // rdx
  __int64 v34; // rcx
  int *v35; // r8
  unsigned int v36; // r10d
  unsigned int v37; // r9d
  unsigned int v38; // edx
  unsigned int v39; // r12d
  unsigned int v40; // r11d
  int v41; // eax
  __int64 v42; // rdi
  unsigned int v43; // r15d
  unsigned int k; // eax
  __int64 v45; // r8
  unsigned int v46; // ecx
  unsigned int v47; // r11d
  unsigned __int64 v48; // rax
  __int64 v49; // r13
  int v50; // ecx
  signed int v51; // ecx
  __int64 v52; // rdi
  __int64 v53; // rbx
  unsigned int v54; // eax
  unsigned int v55; // edx
  unsigned int v56; // eax
  __int64 v57; // rax
  unsigned __int64 v58; // rcx
  unsigned int v59; // ecx
  unsigned int v60; // edx
  unsigned int v61; // eax
  unsigned int v62; // eax
  _DWORD *v63; // rdx
  unsigned int m; // r9d
  __int64 v65; // rax
  int v66; // r9d
  int v67; // [rsp+48h] [rbp-80h]
  unsigned int v68; // [rsp+50h] [rbp-78h] BYREF
  unsigned int v69; // [rsp+54h] [rbp-74h]
  unsigned int v70; // [rsp+58h] [rbp-70h]
  unsigned int v71; // [rsp+5Ch] [rbp-6Ch]
  int v72; // [rsp+60h] [rbp-68h]
  __int64 v73; // [rsp+68h] [rbp-60h]
  __int64 v74; // [rsp+70h] [rbp-58h]
  unsigned int v75; // [rsp+D0h] [rbp+8h] BYREF
  __int64 v76; // [rsp+D8h] [rbp+10h]
  int v77; // [rsp+E0h] [rbp+18h]
  __int64 v78; // [rsp+E8h] [rbp+20h]

  v78 = a4;
  v77 = a3;
  v76 = a2;
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
  v47 = -1;
  v48 = 8LL * v10;
  if ( v48 > 0xFFFFFFFF )
    goto LABEL_5;
  v49 = (unsigned int)(v48 + 1276);
  v72 = v48 + 1276;
  if ( (unsigned int)v48 >= 0xFFFFFB04 )
    goto LABEL_5;
  v50 = 84 * v4;
  if ( (unsigned __int64)(84 * v4) > 0xFFFFFFFF )
    goto LABEL_5;
  v43 = v50 + v49;
  if ( v50 + (int)v49 < (unsigned int)v49 )
    goto LABEL_5;
  i = 0;
  a3 = 0;
  v51 = 0;
  while ( (unsigned int)a3 < (unsigned int)v4 )
  {
    v52 = *(_QWORD *)(a1 + 112);
    v53 = 396LL * (unsigned int)a3;
    v54 = *(_DWORD *)(v53 + v52 + 388);
    if ( v54 == 0xFFFF )
    {
      v47 = 56;
    }
    else
    {
      v55 = *(_DWORD *)(*(_QWORD *)(a1 + 192) + 4LL * v54);
      v56 = v55 + *(_DWORD *)(*(_QWORD *)(a1 + 200) + 4LL * v54);
      if ( v56 >= v55 )
        v47 = v56;
      v51 = v56 < v55 ? 0x80070216 : 0;
    }
    if ( v51 >= 0 )
    {
      v57 = v47;
      v47 = -1;
      v58 = v57 * *(unsigned int *)(v53 + v52 + 392);
      if ( v58 > 0xFFFFFFFF )
        goto LABEL_5;
      v59 = i + v58;
      v60 = i;
      v61 = -1;
      if ( v59 >= (unsigned int)i )
        v61 = v59;
      i = v61;
      v51 = v59 < v60 ? 0x80070216 : 0;
    }
    else
    {
      v47 = -1;
    }
    a3 = (unsigned int)(a3 + 1);
    if ( v51 < 0 )
      goto LABEL_5;
  }
  if ( (unsigned int)i + v43 < v43 )
  {
LABEL_5:
    WriteDbgTraceErrorGpd(
      (__int64)"PINFOHDRcreateSnapshot",
      "Fatal: PINFOHDRcreateSnapshot - INFOHEADER size overflow.",
      a3,
      i);
    return 0;
  }
  v12 = i + v43;
  v13 = LocalAlloc(0x40u, (unsigned int)i + v43);
  v15 = (__int64)v13;
  if ( !v13 )
  {
    WriteDbgTraceErrorGpd(
      (__int64)"PINFOHDRcreateSnapshot",
      "Fatal: PINFOHDRcreateSnapshot - unable to alloc %d bytes.",
      v12);
    return 0;
  }
  if ( !(unsigned int)BinitCommandTable((__int64)v13 + 880, v14, a1, v6) )
    goto LABEL_6;
  *(_QWORD *)(v15 + 504) = v15;
  *(_DWORD *)(v15 + 408) = 880;
  *(_DWORD *)(v15 + 404) = 99;
  *(_DWORD *)(v15 + 448) = 1276;
  *(_DWORD *)(v15 + 444) = v10;
  if ( !(unsigned int)BinitGPDdriverInfo(v15 + 400, a1, v6) )
    goto LABEL_6;
  *(_DWORD *)(v15 + 56) = 64;
  v17 = (_DWORD *)(v15 + 204);
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
  *(_DWORD *)(v15 + 96) = v49;
  *(_DWORD *)(v15 + 100) = *(_DWORD *)(v15 + 464);
  *(_DWORD *)(v15 + 104) = *(_DWORD *)(v15 + 460);
  *(_DWORD *)(v15 + 116) = 0;
  *(_DWORD *)(v15 + 224) = *(_DWORD *)(v15 + 456);
  *(_DWORD *)(v15 + 220) = *(_DWORD *)(v15 + 452);
  if ( *(_DWORD *)(v15 + 832) != -1 )
    *v17 |= 2u;
  if ( *(_DWORD *)(v15 + 776) != -1 )
    *v17 |= 0x40u;
  if ( !(unsigned int)BinitUIinfo(v15 + 64, a1, v6, v16) )
    goto LABEL_6;
  v18 = v15 + v49;
  for ( j = 0; ; j = v37 + 1 )
  {
    LODWORD(v78) = j;
    if ( j >= *(_DWORD *)(a1 + 120) )
      break;
    v20 = *(_QWORD *)(a1 + 112);
    v21 = 84LL * j;
    v22 = 396LL * j;
    v68 = 0;
    v73 = v21;
    v23 = *(_DWORD *)(v22 + v20 + 392);
    v24 = *(_DWORD *)(v22 + v20 + 388);
    *(_DWORD *)(v21 + v18 + 52) = v23;
    *(_DWORD *)(v21 + v18 + 56) = v43;
    *(_DWORD *)(v21 + v18 + 16) = 0;
    v25 = *(_QWORD *)(a1 + 184);
    v69 = v23;
    v26 = v22 + *(_QWORD *)(a1 + 112);
    v71 = v24;
    v27 = *(_DWORD *)(v25 + 44);
    v28 = *(_DWORD *)(v25 + 32);
    v70 = v27;
    v74 = v26;
    while ( v28 < v27 )
    {
      v29 = *(_QWORD *)(a1 + 176);
      v30 = 32LL * v28;
      v31 = *(_DWORD *)(v30 + v29 + 12);
      if ( v31 )
      {
        v32 = *(unsigned int *)(v30 + v29 + 16);
        if ( (int)v32 + 4 < (unsigned int)v32 || (unsigned int)(v32 + 4) > 0x18C )
          v33 = 0;
        else
          v33 = (unsigned int *)(v26 + v32);
        v34 = *(unsigned int *)(v30 + v29 + 20);
        if ( (unsigned int)v34 + v31 < (unsigned int)v34 )
          goto LABEL_6;
        if ( (unsigned int)v34 + v31 > 0x54 )
          goto LABEL_6;
        v75 = 0;
        v35 = (int *)(v18 + v34 + v21);
        if ( !v35
          || (unsigned int)EextractValueFromTree((_QWORD *)a1, v28, v35, v31, (int *)&v68, *v33, v6, 0, &v75) != 1 )
        {
          goto LABEL_6;
        }
        v21 = v73;
        v27 = v70;
        v26 = v74;
      }
      ++v28;
    }
    v36 = v71;
    v37 = v78;
    if ( v71 == 0xFFFF )
    {
      v38 = 0;
      v39 = 56;
    }
    else
    {
      v39 = *(_DWORD *)(*(_QWORD *)(a1 + 192) + 4LL * v71);
      v38 = *(_DWORD *)(*(_QWORD *)(a1 + 200) + 4LL * v71);
      *(_DWORD *)(v15 + 4LL * v71 + 268) = v72 + 84 * v78;
    }
    v40 = v69;
    v41 = v69 * v39;
    v42 = v15 + *(unsigned int *)(v21 + v18 + 56);
    v68 = v38;
    *(_DWORD *)(v21 + v18 + 28) = v36;
    *(_DWORD *)(v21 + v18 + 48) = v39;
    v43 += v41;
    for ( k = 0; ; k = v75 + 1 )
    {
      v75 = k;
      if ( k >= v40 )
        break;
      if ( v38 )
      {
        v46 = v43;
        v45 = v15 + v43;
        v43 += v38;
      }
      else
      {
        v45 = 0;
        v46 = 0;
      }
      *(_DWORD *)(v42 + 44) = v46;
      if ( !(unsigned int)BinitOptionFields(v42, v39, v45, v38, a1, v37, k, v76, v15, v67) )
        goto LABEL_6;
      v38 = v68;
      v37 = v78;
      v40 = v69;
      v42 += v39;
    }
    v6 = v76;
  }
  if ( v77 && !(unsigned int)BCheckGPDSemantics(v15, v6) )
  {
LABEL_6:
    LocalFree((HLOCAL)v15);
    return 0;
  }
  v62 = *(_DWORD *)(v15 + 272);
  if ( v62 )
  {
    v63 = (_DWORD *)(*(_QWORD *)(v15 + 392) + v62);
    if ( v63 )
    {
      for ( m = 0; m < v63[13]; m = v66 + 1 )
      {
        v65 = PGetIndexedOption(v15 + 64, v63, m);
        if ( v65 && *(_DWORD *)(v65 + 80) == 256 )
        {
          *v17 |= 0x20u;
          *(_DWORD *)(v15 + 208) = v66;
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
0x180005544  mov     [rsp+arg_18], r9
0x180005549  mov     [rsp+arg_10], r8d
0x18000554e  mov     [rsp+arg_8], rdx
0x180005553  push    rbx
0x180005554  push    rbp
0x180005555  push    rsi
0x180005556  push    rdi
0x180005557  push    r12
0x180005559  push    r13
0x18000555b  push    r14
0x18000555d  push    r15
0x18000555f  sub     rsp, 88h
0x180005566  mov     r10d, [rcx+78h]
0x18000556a  xor     r14d, r14d
0x18000556d  mov     rsi, rcx
0x180005570  mov     r12, rdx
0x180005573  mov     ecx, r10d
0x180005576  mov     r9d, r14d
0x180005579  test    r10d, r10d
0x18000557c  jz      short loc_180005597
0x18000557e  mov     eax, r9d
0x180005581  mov     edx, r9d
0x180005584  cmp     [r12+rax*2+1], r14b
0x180005589  jnz     loc_180005A55
0x18000558f  inc     r9d
0x180005592  cmp     r9d, r10d
0x180005595  jb      short loc_18000557E
0x180005597  lea     ebp, [rcx+8]
0x18000559a  cmp     ebp, ecx
0x18000559c  jnb     loc_18000596A
0x1800055a2  lea     rdx, aFatalPinfohdrc; "Fatal: PINFOHDRcreateSnapshot - INFOHEA"...
0x1800055a9  lea     rcx, aPinfohdrcreate; "PINFOHDRcreateSnapshot"
0x1800055b0  call    WriteDbgTraceErrorGpd
0x1800055b5  jmp     short loc_1800055C6
0x1800055b7  mov     rcx, rbx; hMem
0x1800055ba  call    cs:__imp_LocalFree
0x1800055c1  nop     dword ptr [rax+rax+00h]
0x1800055c6  xor     eax, eax
0x1800055c8  add     rsp, 88h
0x1800055cf  pop     r15
0x1800055d1  pop     r14
0x1800055d3  pop     r13
0x1800055d5  pop     r12
0x1800055d7  pop     rdi
0x1800055d8  pop     rsi
0x1800055d9  pop     rbp
0x1800055da  pop     rbx
0x1800055db  retn
0x1800055dd  lea     eax, [r9+r15]
0x1800055e1  mov     edi, r11d
0x1800055e4  cmp     eax, r15d
0x1800055e7  cmovnb  edi, eax
0x1800055ea  jb      short loc_1800055A2
0x1800055ec  mov     edx, edi; uBytes
0x1800055ee  mov     ecx, 40h ; '@'; uFlags
0x1800055f3  call    cs:__imp_LocalAlloc
0x1800055fa  nop     dword ptr [rax+rax+00h]
0x1800055ff  mov     rbx, rax
0x180005602  test    rax, rax
0x180005605  jz      loc_180005A7D
0x18000560b  lea     rcx, [rax+370h]
0x180005612  mov     r9, r12
0x180005615  mov     r8, rsi
0x180005618  call    BinitCommandTable
0x18000561d  test    eax, eax
0x18000561f  jz      short loc_1800055B7
0x180005621  lea     rdi, [rbx+190h]
0x180005628  mov     r8, r12
0x18000562b  mov     rcx, rdi
0x18000562e  mov     [rdi+68h], rbx
0x180005632  mov     rdx, rsi
0x180005635  mov     dword ptr [rdi+8], 370h
0x18000563c  mov     dword ptr [rdi+4], 63h ; 'c'
0x180005643  mov     dword ptr [rdi+30h], 4FCh
0x18000564a  mov     [rdi+2Ch], ebp
0x18000564d  call    BinitGPDdriverInfo
0x180005652  test    eax, eax
0x180005654  jz      loc_1800055B7
0x18000565a  mov     dword ptr [rbx+38h], 40h ; '@'
0x180005661  lea     rbp, [rbx+0CCh]
0x180005668  mov     dword ptr [rbx+3Ch], 190h
0x18000566f  mov     rax, [rsi+58h]
0x180005673  mov     ecx, [rax]
0x180005675  mov     [rbx], ecx
0x180005677  mov     rax, [rsi+58h]
0x18000567b  mov     ecx, [rax+4]
0x18000567e  mov     [rbx+4], ecx
0x180005681  mov     rax, [rsi+58h]
0x180005685  mov     ecx, [rax+8]
0x180005688  mov     [rbx+8], ecx
0x18000568b  mov     rax, [rsi+58h]
0x18000568f  mov     ecx, [rax+0Ch]
0x180005692  mov     [rbx+0Ch], ecx
0x180005695  mov     rax, [rsi+58h]
0x180005699  mov     ecx, [rax+10h]
0x18000569c  mov     [rbx+10h], ecx
0x18000569f  mov     rax, [rsi+58h]
0x1800056a3  mov     ecx, [rax+14h]
0x1800056a6  mov     [rbx+14h], ecx
0x1800056a9  mov     rax, [rsi+58h]
0x1800056ad  mov     ecx, [rax+18h]
0x1800056b0  mov     [rbx+18h], ecx
0x1800056b3  mov     [rbx+30h], rsi
0x1800056b7  mov     [rbx+28h], r14
0x1800056bb  mov     [rbx+188h], rbx
0x1800056c2  mov     [rbx+60h], r13d
0x1800056c6  mov     eax, [rdi+40h]
0x1800056c9  mov     [rbx+64h], eax
0x1800056cc  mov     eax, [rdi+3Ch]
0x1800056cf  mov     [rbx+68h], eax
0x1800056d2  mov     [rbx+74h], r14d
0x1800056d6  mov     eax, [rdi+38h]
0x1800056d9  mov     [rbx+0E0h], eax
0x1800056df  mov     eax, [rdi+34h]
0x1800056e2  mov     [rbx+0DCh], eax
0x1800056e8  mov     eax, 0FFFFFFFFh
0x1800056ed  cmp     [rdi+1B0h], eax
0x1800056f3  jnz     loc_180005A98
0x1800056f9  cmp     [rdi+178h], eax
0x1800056ff  jnz     loc_180005AA1
0x180005705  mov     r8, r12
0x180005708  lea     rcx, [rbx+40h]
0x18000570c  mov     rdx, rsi
0x18000570f  call    BinitUIinfo
0x180005714  test    eax, eax
0x180005716  jz      loc_1800055B7
0x18000571c  add     r13, rbx
0x18000571f  xor     r9d, r9d
0x180005722  mov     dword ptr [rsp+0C8h+arg_18], r9d
0x18000572a  cmp     r9d, [rsi+78h]
0x18000572e  jnb     loc_180005AAA
0x180005734  mov     rax, [rsi+70h]
0x180005738  mov     ecx, r9d
0x18000573b  imul    r8, rcx, 54h ; 'T'
0x18000573f  imul    rdx, rcx, 18Ch
0x180005746  mov     [rsp+0C8h+var_78], r14d
0x18000574b  mov     [rsp+0C8h+var_60], r8
0x180005750  mov     r11d, [rdx+rax+188h]
0x180005758  mov     r10d, [rdx+rax+184h]
0x180005760  mov     [r8+r13+34h], r11d
0x180005765  mov     [r8+r13+38h], r15d
0x18000576a  mov     [r8+r13+10h], r14d
0x18000576f  mov     rax, [rsi+0B8h]
0x180005776  mov     [rsp+0C8h+var_74], r11d
0x18000577b  mov     r11, [rsi+70h]
0x18000577f  add     r11, rdx
0x180005782  mov     [rsp+0C8h+var_6C], r10d
0x180005787  mov     ecx, [rax+2Ch]
0x18000578a  mov     edi, [rax+20h]
0x18000578d  mov     [rsp+0C8h+var_70], ecx
0x180005791  mov     [rsp+0C8h+var_58], r11
0x180005796  cmp     edi, ecx
0x180005798  jnb     loc_180005860
0x18000579e  mov     r9, [rsi+0B0h]
0x1800057a5  mov     eax, edi
0x1800057a7  shl     rax, 5
0x1800057ab  mov     r10d, [rax+r9+0Ch]
0x1800057b0  test    r10d, r10d
0x1800057b3  jz      loc_180005852
0x1800057b9  mov     ecx, [rax+r9+10h]
0x1800057be  lea     edx, [rcx+4]
0x1800057c1  cmp     edx, ecx
0x1800057c3  jb      loc_180005859
0x1800057c9  cmp     edx, 18Ch
0x1800057cf  ja      loc_180005859
0x1800057d5  lea     rdx, [r11+rcx]
0x1800057d9  mov     ecx, [rax+r9+14h]
0x1800057de  lea     eax, [rcx+r10]
0x1800057e2  cmp     eax, ecx
0x1800057e4  jb      loc_1800055B7
0x1800057ea  cmp     eax, 54h ; 'T'
0x1800057ed  ja      loc_1800055B7
0x1800057f3  add     r8, rcx
0x1800057f6  mov     [rsp+0C8h+arg_0], r14d
0x1800057fe  add     r8, r13
0x180005801  jz      loc_1800055B7
0x180005807  lea     rax, [rsp+0C8h+arg_0]
0x18000580f  mov     r9d, r10d
0x180005812  mov     [rsp+0C8h+var_88], rax
0x180005817  mov     rcx, rsi
0x18000581a  mov     eax, [rdx]
0x18000581c  mov     edx, edi
0x18000581e  mov     dword ptr [rsp+0C8h+var_90], r14d
0x180005823  mov     [rsp+0C8h+var_98], r12
0x180005828  mov     [rsp+0C8h+var_A0], eax
0x18000582c  lea     rax, [rsp+0C8h+var_78]
0x180005831  mov     [rsp+0C8h+var_A8], rax
0x180005836  call    EextractValueFromTree
0x18000583b  cmp     eax, 1
0x18000583e  jnz     loc_1800055B7
0x180005844  mov     r8, [rsp+0C8h+var_60]
0x180005849  mov     ecx, [rsp+0C8h+var_70]
0x18000584d  mov     r11, [rsp+0C8h+var_58]
0x180005852  inc     edi
0x180005854  jmp     loc_180005796
0x180005859  xor     edx, edx
0x18000585b  jmp     loc_1800057D9
0x180005860  mov     r10d, [rsp+0C8h+var_6C]
0x180005865  mov     r9d, dword ptr [rsp+0C8h+arg_18]
0x18000586d  cmp     r10d, 0FFFFh
0x180005874  jnz     loc_18000592E
0x18000587a  xor     edx, edx
0x18000587c  lea     r12d, [rdx+38h]
0x180005880  mov     r11d, [rsp+0C8h+var_74]
0x180005885  mov     eax, r12d
0x180005888  mov     edi, [r8+r13+38h]
0x18000588d  imul    eax, r11d
0x180005891  add     rdi, rbx
0x180005894  mov     [rsp+0C8h+var_78], edx
0x180005898  mov     [r8+r13+1Ch], r10d
0x18000589d  mov     [r8+r13+30h], r12d
0x1800058a2  add     r15d, eax
0x1800058a5  xor     eax, eax
0x1800058a7  mov     [rsp+0C8h+arg_0], eax
0x1800058ae  cmp     eax, r11d
0x1800058b1  jb      short loc_1800058C3
0x1800058b3  mov     r12, [rsp+0C8h+arg_8]
0x1800058bb  inc     r9d
0x1800058be  jmp     loc_180005722
0x1800058c3  test    edx, edx
0x1800058c5  jnz     loc_180005959
0x1800058cb  xor     r8d, r8d
0x1800058ce  xor     ecx, ecx
0x1800058d0  mov     [rsp+0C8h+var_88], rbx
0x1800058d5  mov     [rdi+2Ch], ecx
0x1800058d8  mov     rcx, [rsp+0C8h+arg_8]
0x1800058e0  mov     [rsp+0C8h+var_90], rcx
0x1800058e5  mov     rcx, rdi
0x1800058e8  mov     dword ptr [rsp+0C8h+var_98], eax
0x1800058ec  mov     [rsp+0C8h+var_A0], r9d
0x1800058f1  mov     r9d, edx
0x1800058f4  mov     edx, r12d
0x1800058f7  mov     [rsp+0C8h+var_A8], rsi
0x1800058fc  call    BinitOptionFields
0x180005901  test    eax, eax
0x180005903  jz      loc_1800055B7
0x180005909  mov     edx, [rsp+0C8h+var_78]
0x18000590d  mov     r9d, dword ptr [rsp+0C8h+arg_18]
0x180005915  mov     r11d, [rsp+0C8h+var_74]
0x18000591a  mov     eax, r12d
0x18000591d  add     rdi, rax
0x180005920  mov     eax, [rsp+0C8h+arg_0]
0x180005927  inc     eax
0x180005929  jmp     loc_1800058A7
0x18000592e  mov     rax, [rsi+0C0h]
0x180005935  mov     r12d, [rax+r10*4]
0x180005939  mov     rax, [rsi+0C8h]
0x180005940  mov     edx, [rax+r10*4]
0x180005944  imul    eax, r9d, 54h ; 'T'
0x180005948  add     eax, [rsp+0C8h+var_68]
0x18000594c  mov     [rbx+r10*4+10Ch], eax
0x180005954  jmp     loc_180005880
0x180005959  mov     r8d, r15d
0x18000595c  mov     ecx, r15d
0x18000595f  add     r8, rbx
0x180005962  add     r15d, edx
0x180005965  jmp     loc_1800058D0
0x18000596a  mov     eax, ebp
0x18000596c  mov     r11d, 0FFFFFFFFh
0x180005972  shl     rax, 3
0x180005976  cmp     rax, r11
0x180005979  ja      loc_1800055A2
0x18000597f  lea     r13d, [rax+4FCh]
0x180005986  mov     [rsp+0C8h+var_68], r13d
0x18000598b  cmp     r13d, 4FCh
0x180005992  jb      loc_1800055A2
0x180005998  imul    rcx, r10, 54h ; 'T'
0x18000599c  cmp     rcx, r11
0x18000599f  ja      loc_1800055A2
0x1800059a5  lea     r15d, [rcx+r13]
0x1800059a9  cmp     r15d, r13d
0x1800059ac  jb      loc_1800055A2
0x1800059b2  mov     r9d, r14d
0x1800059b5  mov     r8d, r14d
0x1800059b8  mov     ecx, r14d
0x1800059bb  cmp     r8d, r10d
0x1800059be  jnb     loc_1800055DD
0x1800059c4  mov     rdi, [rsi+70h]
0x1800059c8  mov     eax, r8d
0x1800059cb  imul    rbx, rax, 18Ch
0x1800059d2  mov     eax, [rbx+rdi+184h]
0x1800059d9  cmp     eax, 0FFFFh
0x1800059de  jz      loc_180005A6B
0x1800059e4  mov     ecx, eax
0x1800059e6  mov     rax, [rsi+0C0h]
0x1800059ed  mov     edx, [rax+rcx*4]
0x1800059f0  mov     rax, [rsi+0C8h]
0x1800059f7  mov     eax, [rax+rcx*4]
0x1800059fa  add     eax, edx
0x1800059fc  cmp     eax, edx
0x1800059fe  cmovnb  r11d, eax
0x180005a02  sbb     ecx, ecx
0x180005a04  and     ecx, 80070216h
0x180005a0a  jmp     short loc_180005A71
0x180005a0c  mov     ecx, [rbx+rdi+188h]
0x180005a13  mov     eax, r11d
0x180005a16  mov     r11d, 0FFFFFFFFh
0x180005a1c  imul    rcx, rax
0x180005a20  cmp     rcx, r11
0x180005a23  ja      loc_1800055A2
  ... truncated ...
```
