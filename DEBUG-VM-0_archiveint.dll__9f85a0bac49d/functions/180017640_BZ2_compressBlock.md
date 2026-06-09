# BZ2_compressBlock

- ea: `0x180017640`
- end: `0x180017e6e`
- name: `BZ2_compressBlock`
- size: `2094`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x180016750`

## callees

- `0x1800158b8`
- `0x180017640`
- `0x180017e80`
- `0x180017f90`
- `0x180018220`
- `0x18001ef30`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o___acrt_iob_func` at `0x1800176b1`
- `api-ms-win-crt-private-l1-1-0!_o___acrt_iob_func` at `0x180017e0a`
- `api-ms-win-crt-private-l1-1-0!_o___acrt_iob_func` at `0x1800176b1`
- `api-ms-win-crt-private-l1-1-0!_o___acrt_iob_func` at `0x180017e0a`

## string_xrefs

- `0x1800176bc`: `    block %d: crc = 0x%08x, combined CRC = 0x%08x, size = %d\n`
- `0x180017e13`: `    final combined CRC = 0x%08x\n   `

## pseudocode

```c
int __fastcall BZ2_compressBlock(__int64 a1, char a2)
{
  int v4; // r14d
  int v5; // ebp
  int v6; // edi
  int v7; // r15d
  FILE *v8; // rax
  __int64 v9; // rax
  bool v10; // zf
  int v11; // r8d
  int v12; // eax
  int v13; // r9d
  int v14; // edx
  unsigned __int8 v15; // r10
  int v16; // r8d
  int v17; // edx
  int i; // edx
  int v19; // eax
  int v20; // edx
  int v21; // eax
  int v22; // r8d
  int v23; // r8d
  int v24; // eax
  char v25; // cl
  int v26; // eax
  int v27; // edx
  int v28; // edx
  int v29; // eax
  int v30; // r8d
  int v31; // eax
  int v32; // r8d
  int v33; // r8d
  int v34; // eax
  char v35; // cl
  int v36; // eax
  int v37; // edx
  int v38; // edx
  int v39; // eax
  char v40; // cl
  int v41; // eax
  int v42; // r8d
  int v43; // r8d
  int v44; // eax
  __int64 v45; // rdx
  int j; // eax
  int v47; // eax
  int v48; // edx
  int v49; // eax
  int v50; // r8d
  int v51; // edx
  int v52; // eax
  int k; // edx
  int v54; // eax
  int v55; // edx
  int v56; // eax
  int v57; // r8d
  int v58; // r8d
  int v59; // eax
  char v60; // cl
  int v61; // eax
  int v62; // edx
  int v63; // edx
  int v64; // eax
  char v65; // cl
  int v66; // eax
  int v67; // r8d
  int v68; // r8d
  int v69; // eax
  int v70; // r9d
  int v71; // r8d
  int v72; // r9d
  int v73; // r8d
  char v74; // cl
  int v75; // r8d
  int v76; // edx
  int v77; // edx
  int v78; // r8d
  int v79; // eax
  __int64 v80; // rdx
  int v81; // edi
  FILE *v82; // rax
  int v83; // eax

  v4 = *(_DWORD *)(a1 + 108);
  if ( v4 > 0 )
  {
    v5 = ~*(_DWORD *)(a1 + 648);
    v6 = v5 ^ __ROR4__(*(_DWORD *)(a1 + 652), 31);
    v7 = *(_DWORD *)(a1 + 660);
    *(_DWORD *)(a1 + 648) = v5;
    *(_DWORD *)(a1 + 652) = v6;
    if ( v7 > 1 )
      *(_DWORD *)(a1 + 116) = 0;
    if ( *(int *)(a1 + 656) >= 2 )
    {
      v8 = __acrt_iob_func(2u);
      fprintf(v8, "    block %d: crc = 0x%08x, combined CRC = 0x%08x, size = %d\n", v7, v5, v6, v4);
    }
    BZ2_blockSort(a1);
  }
  v9 = *(_QWORD *)(a1 + 32) + *(int *)(a1 + 108);
  v10 = *(_DWORD *)(a1 + 660) == 1;
  *(_QWORD *)(a1 + 80) = v9;
  if ( v10 )
  {
    HIBYTE(v11) = 66;
    *(_DWORD *)(a1 + 644) = 8;
    *(_DWORD *)(a1 + 640) = 1107296256;
    do
    {
      *(_BYTE *)(*(int *)(a1 + 116) + *(_QWORD *)(a1 + 80)) = HIBYTE(v11);
      v12 = *(_DWORD *)(a1 + 644);
      v13 = *(_DWORD *)(a1 + 116) + 1;
      v11 = *(_DWORD *)(a1 + 640) << 8;
      *(_DWORD *)(a1 + 116) = v13;
      *(_DWORD *)(a1 + 640) = v11;
      *(_DWORD *)(a1 + 644) = v12 - 8;
    }
    while ( v12 - 8 >= 8 );
    *(_DWORD *)(a1 + 644) = v12;
    v14 = v11 | (90 << (24 - (v12 - 8)));
    for ( *(_DWORD *)(a1 + 640) = v14; v12 >= 8; *(_DWORD *)(a1 + 644) = v12 )
    {
      *(_BYTE *)(v13 + *(_QWORD *)(a1 + 80)) = HIBYTE(v14);
      v13 = *(_DWORD *)(a1 + 116) + 1;
      v14 = *(_DWORD *)(a1 + 640) << 8;
      v12 = *(_DWORD *)(a1 + 644) - 8;
      *(_DWORD *)(a1 + 116) = v13;
      *(_DWORD *)(a1 + 640) = v14;
    }
    v15 = *(_BYTE *)(a1 + 664) + 48;
    v16 = v14 | (104 << (24 - v12));
    v17 = v12 + 8;
    *(_DWORD *)(a1 + 640) = v16;
    for ( *(_DWORD *)(a1 + 644) = v12 + 8; v17 >= 8; *(_DWORD *)(a1 + 644) = v17 )
    {
      *(_BYTE *)(v13 + *(_QWORD *)(a1 + 80)) = HIBYTE(v16);
      v13 = *(_DWORD *)(a1 + 116) + 1;
      v16 = *(_DWORD *)(a1 + 640) << 8;
      v17 = *(_DWORD *)(a1 + 644) - 8;
      *(_DWORD *)(a1 + 116) = v13;
      *(_DWORD *)(a1 + 640) = v16;
    }
    *(_DWORD *)(a1 + 640) = v16 | (v15 << (24 - v17));
    LODWORD(v9) = v17 + 8;
    *(_DWORD *)(a1 + 644) = v17 + 8;
  }
  if ( *(int *)(a1 + 108) > 0 )
  {
    for ( i = *(_DWORD *)(a1 + 644); i >= 8; *(_DWORD *)(a1 + 644) = i )
    {
      *(_BYTE *)(*(int *)(a1 + 116) + *(_QWORD *)(a1 + 80)) = *(_BYTE *)(a1 + 643);
      v19 = *(_DWORD *)(a1 + 640);
      v20 = *(_DWORD *)(a1 + 644);
      ++*(_DWORD *)(a1 + 116);
      i = v20 - 8;
      *(_DWORD *)(a1 + 640) = v19 << 8;
    }
    *(_DWORD *)(a1 + 640) |= 49 << (24 - i);
    v21 = i + 8;
    v22 = *(_DWORD *)(a1 + 640);
    for ( *(_DWORD *)(a1 + 644) = i + 8; v21 >= 8; *(_DWORD *)(a1 + 644) = v21 )
    {
      *(_BYTE *)(*(int *)(a1 + 116) + *(_QWORD *)(a1 + 80)) = HIBYTE(v22);
      v23 = *(_DWORD *)(a1 + 640);
      v24 = *(_DWORD *)(a1 + 644);
      ++*(_DWORD *)(a1 + 116);
      v21 = v24 - 8;
      v22 = v23 << 8;
      *(_DWORD *)(a1 + 640) = v22;
    }
    v25 = 24 - v21;
    v26 = v21 + 8;
    v27 = v22 | (65 << v25);
    *(_DWORD *)(a1 + 644) = v26;
    for ( *(_DWORD *)(a1 + 640) = v27; v26 >= 8; *(_DWORD *)(a1 + 644) = v26 )
    {
      *(_BYTE *)(*(int *)(a1 + 116) + *(_QWORD *)(a1 + 80)) = HIBYTE(v27);
      v28 = *(_DWORD *)(a1 + 640);
      v29 = *(_DWORD *)(a1 + 644);
      ++*(_DWORD *)(a1 + 116);
      v26 = v29 - 8;
      v27 = v28 << 8;
      *(_DWORD *)(a1 + 640) = v27;
    }
    v30 = 89 << (24 - v26);
    v31 = v26 + 8;
    v32 = v27 | v30;
    *(_DWORD *)(a1 + 644) = v31;
    for ( *(_DWORD *)(a1 + 640) = v32; v31 >= 8; *(_DWORD *)(a1 + 644) = v31 )
    {
      *(_BYTE *)(*(int *)(a1 + 116) + *(_QWORD *)(a1 + 80)) = HIBYTE(v32);
      v33 = *(_DWORD *)(a1 + 640);
      v34 = *(_DWORD *)(a1 + 644);
      ++*(_DWORD *)(a1 + 116);
      v31 = v34 - 8;
      v32 = v33 << 8;
      *(_DWORD *)(a1 + 640) = v32;
    }
    v35 = 24 - v31;
    v36 = v31 + 8;
    v37 = v32 | (38 << v35);
    *(_DWORD *)(a1 + 644) = v36;
    for ( *(_DWORD *)(a1 + 640) = v37; v36 >= 8; *(_DWORD *)(a1 + 644) = v36 )
    {
      *(_BYTE *)(*(int *)(a1 + 116) + *(_QWORD *)(a1 + 80)) = HIBYTE(v37);
      v38 = *(_DWORD *)(a1 + 640);
      v39 = *(_DWORD *)(a1 + 644);
      ++*(_DWORD *)(a1 + 116);
      v36 = v39 - 8;
      v37 = v38 << 8;
      *(_DWORD *)(a1 + 640) = v37;
    }
    v40 = 24 - v36;
    v41 = v36 + 8;
    v42 = v37 | (83 << v40);
    *(_DWORD *)(a1 + 644) = v41;
    for ( *(_DWORD *)(a1 + 640) = v42; v41 >= 8; *(_DWORD *)(a1 + 644) = v41 )
    {
      *(_BYTE *)(*(int *)(a1 + 116) + *(_QWORD *)(a1 + 80)) = HIBYTE(v42);
      v43 = *(_DWORD *)(a1 + 640);
      v44 = *(_DWORD *)(a1 + 644);
      ++*(_DWORD *)(a1 + 116);
      v41 = v44 - 8;
      v42 = v43 << 8;
      *(_DWORD *)(a1 + 640) = v42;
    }
    v45 = *(unsigned int *)(a1 + 648);
    *(_DWORD *)(a1 + 644) = v41 + 8;
    *(_DWORD *)(a1 + 640) = v42 | (89 << (24 - v41));
    bsPutUInt32(a1, v45);
    for ( j = *(_DWORD *)(a1 + 644); j >= 8; *(_DWORD *)(a1 + 644) = j )
    {
      *(_BYTE *)(*(int *)(a1 + 116) + *(_QWORD *)(a1 + 80)) = *(_BYTE *)(a1 + 643);
      v47 = *(_DWORD *)(a1 + 640);
      ++*(_DWORD *)(a1 + 116);
      *(_DWORD *)(a1 + 640) = v47 << 8;
      j = *(_DWORD *)(a1 + 644) - 8;
    }
    v48 = *(_DWORD *)(a1 + 640);
    v49 = j + 1;
    v50 = *(_DWORD *)(a1 + 48);
    for ( *(_DWORD *)(a1 + 644) = v49; v49 >= 8; *(_DWORD *)(a1 + 644) = v49 )
    {
      *(_BYTE *)(*(int *)(a1 + 116) + *(_QWORD *)(a1 + 80)) = HIBYTE(v48);
      v51 = *(_DWORD *)(a1 + 640);
      v52 = *(_DWORD *)(a1 + 644);
      ++*(_DWORD *)(a1 + 116);
      v49 = v52 - 8;
      v48 = v51 << 8;
      *(_DWORD *)(a1 + 640) = v48;
    }
    *(_DWORD *)(a1 + 644) = v49 + 24;
    *(_DWORD *)(a1 + 640) = v48 | (v50 << (8 - v49));
    generateMTFValues(a1);
    LODWORD(v9) = sendMTFValues(a1);
  }
  if ( a2 )
  {
    for ( k = *(_DWORD *)(a1 + 644); k >= 8; *(_DWORD *)(a1 + 644) = k )
    {
      *(_BYTE *)(*(int *)(a1 + 116) + *(_QWORD *)(a1 + 80)) = *(_BYTE *)(a1 + 643);
      v54 = *(_DWORD *)(a1 + 640);
      v55 = *(_DWORD *)(a1 + 644);
      ++*(_DWORD *)(a1 + 116);
      k = v55 - 8;
      *(_DWORD *)(a1 + 640) = v54 << 8;
    }
    *(_DWORD *)(a1 + 640) |= 23 << (24 - k);
    v56 = k + 8;
    v57 = *(_DWORD *)(a1 + 640);
    for ( *(_DWORD *)(a1 + 644) = k + 8; v56 >= 8; *(_DWORD *)(a1 + 644) = v56 )
    {
      *(_BYTE *)(*(int *)(a1 + 116) + *(_QWORD *)(a1 + 80)) = HIBYTE(v57);
      v58 = *(_DWORD *)(a1 + 640);
      v59 = *(_DWORD *)(a1 + 644);
      ++*(_DWORD *)(a1 + 116);
      v56 = v59 - 8;
      v57 = v58 << 8;
      *(_DWORD *)(a1 + 640) = v57;
    }
    v60 = 24 - v56;
    v61 = v56 + 8;
    v62 = v57 | (114 << v60);
    *(_DWORD *)(a1 + 644) = v61;
    for ( *(_DWORD *)(a1 + 640) = v62; v61 >= 8; *(_DWORD *)(a1 + 644) = v61 )
    {
      *(_BYTE *)(*(int *)(a1 + 116) + *(_QWORD *)(a1 + 80)) = HIBYTE(v62);
      v63 = *(_DWORD *)(a1 + 640);
      v64 = *(_DWORD *)(a1 + 644);
      ++*(_DWORD *)(a1 + 116);
      v61 = v64 - 8;
      v62 = v63 << 8;
      *(_DWORD *)(a1 + 640) = v62;
    }
    v65 = 24 - v61;
    v66 = v61 + 8;
    v67 = v62 | (69 << v65);
    *(_DWORD *)(a1 + 644) = v66;
    for ( *(_DWORD *)(a1 + 640) = v67; v66 >= 8; *(_DWORD *)(a1 + 644) = v66 )
    {
      *(_BYTE *)(*(int *)(a1 + 116) + *(_QWORD *)(a1 + 80)) = HIBYTE(v67);
      v68 = *(_DWORD *)(a1 + 640);
      v69 = *(_DWORD *)(a1 + 644);
      ++*(_DWORD *)(a1 + 116);
      v66 = v69 - 8;
      v67 = v68 << 8;
      *(_DWORD *)(a1 + 640) = v67;
    }
    v70 = v67 | (56 << (24 - v66));
    v71 = v66 + 8;
    *(_DWORD *)(a1 + 640) = v70;
    for ( *(_DWORD *)(a1 + 644) = v66 + 8; v71 >= 8; *(_DWORD *)(a1 + 644) = v71 )
    {
      *(_BYTE *)(*(int *)(a1 + 116) + *(_QWORD *)(a1 + 80)) = HIBYTE(v70);
      v72 = *(_DWORD *)(a1 + 640);
      v73 = *(_DWORD *)(a1 + 644);
      ++*(_DWORD *)(a1 + 116);
      v71 = v73 - 8;
      v70 = v72 << 8;
      *(_DWORD *)(a1 + 640) = v70;
    }
    v74 = 24 - v71;
    v75 = v71 + 8;
    v76 = v70 | (80 << v74);
    *(_DWORD *)(a1 + 644) = v75;
    for ( *(_DWORD *)(a1 + 640) = v76; v75 >= 8; *(_DWORD *)(a1 + 644) = v75 )
    {
      *(_BYTE *)(*(int *)(a1 + 116) + *(_QWORD *)(a1 + 80)) = HIBYTE(v76);
      v77 = *(_DWORD *)(a1 + 640);
      v78 = *(_DWORD *)(a1 + 644);
      ++*(_DWORD *)(a1 + 116);
      v75 = v78 - 8;
      v76 = v77 << 8;
      *(_DWORD *)(a1 + 640) = v76;
    }
    v79 = v76 | (144 << (24 - v75));
    v80 = *(unsigned int *)(a1 + 652);
    *(_DWORD *)(a1 + 640) = v79;
    *(_DWORD *)(a1 + 644) = v75 + 8;
    LODWORD(v9) = bsPutUInt32(a1, v80);
    if ( *(int *)(a1 + 656) >= 2 )
    {
      v81 = *(_DWORD *)(a1 + 652);
      v82 = __acrt_iob_func(2u);
      LODWORD(v9) = fprintf(v82, "    final combined CRC = 0x%08x\n   ", v81);
    }
    if ( *(int *)(a1 + 644) > 0 )
    {
      do
      {
        *(_BYTE *)(*(int *)(a1 + 116) + *(_QWORD *)(a1 + 80)) = *(_BYTE *)(a1 + 643);
        v83 = *(_DWORD *)(a1 + 640);
        ++*(_DWORD *)(a1 + 116);
        *(_DWORD *)(a1 + 640) = v83 << 8;
        LODWORD(v9) = *(_DWORD *)(a1 + 644) - 8;
        *(_DWORD *)(a1 + 644) = v9;
      }
      while ( (int)v9 > 0 );
    }
  }
  return v9;
}

```

## disassembly

```asm
0x180017640  push    rbx
0x180017642  push    rdi
0x180017643  sub     rsp, 38h
0x180017647  mov     [rsp+48h+arg_0], rbp
0x18001764c  mov     rbx, rcx
0x18001764f  mov     [rsp+48h+arg_8], rsi
0x180017654  mov     [rsp+48h+arg_10], r12
0x180017659  movzx   r12d, dl
0x18001765d  mov     [rsp+48h+arg_18], r14
0x180017662  mov     r14d, [rcx+6Ch]
0x180017666  test    r14d, r14d
0x180017669  jle     short loc_1800176E2
0x18001766b  mov     ebp, [rcx+288h]
0x180017671  mov     edi, [rcx+28Ch]
0x180017677  not     ebp
0x180017679  ror     edi, 1Fh
0x18001767c  xor     edi, ebp
0x18001767e  mov     [rsp+48h+var_18], r15
0x180017683  mov     r15d, [rcx+294h]
0x18001768a  mov     [rcx+288h], ebp
0x180017690  mov     [rcx+28Ch], edi
0x180017696  cmp     r15d, 1
0x18001769a  jle     short loc_1800176A3
0x18001769c  mov     dword ptr [rcx+74h], 0
0x1800176a3  cmp     dword ptr [rcx+290h], 2
0x1800176aa  jl      short loc_1800176D5
0x1800176ac  mov     ecx, 2; Ix
0x1800176b1  call    cs:__imp___acrt_iob_func
0x1800176b7  mov     [rsp+48h+var_20], r14d
0x1800176bc  lea     rdx, aBlockDCrc0x08x; "    block %d: crc = 0x%08x, combined CR"...
0x1800176c3  mov     rcx, rax; Stream
0x1800176c6  mov     [rsp+48h+var_28], edi
0x1800176ca  mov     r9d, ebp
0x1800176cd  mov     r8d, r15d
0x1800176d0  call    fprintf
0x1800176d5  mov     rcx, rbx
0x1800176d8  call    BZ2_blockSort
0x1800176dd  mov     r15, [rsp+48h+var_18]
0x1800176e2  movsxd  rax, dword ptr [rbx+6Ch]
0x1800176e6  mov     ebp, 8
0x1800176eb  add     rax, [rbx+20h]
0x1800176ef  mov     edi, 18h
0x1800176f4  cmp     dword ptr [rbx+294h], 1
0x1800176fb  mov     r14, [rsp+48h+arg_18]
0x180017700  mov     rsi, [rsp+48h+arg_8]
0x180017705  mov     [rbx+50h], rax
0x180017709  jnz     loc_18001785B
0x18001770f  mov     r8d, 42000000h
0x180017715  mov     [rbx+284h], ebp
0x18001771b  mov     [rbx+280h], r8d
0x180017722  nop     dword ptr [rax+00h]
0x180017726  nop     word ptr [rax+rax+00000000h]
0x180017730  movsxd  rcx, dword ptr [rbx+74h]
0x180017734  mov     rax, [rbx+50h]
0x180017738  shr     r8d, 18h
0x18001773c  mov     [rcx+rax], r8b
0x180017740  mov     eax, [rbx+284h]
0x180017746  mov     r9d, [rbx+74h]
0x18001774a  mov     r8d, [rbx+280h]
0x180017751  inc     r9d
0x180017754  shl     r8d, 8
0x180017758  lea     edx, [rax-8]
0x18001775b  mov     [rbx+74h], r9d
0x18001775f  mov     [rbx+280h], r8d
0x180017766  mov     [rbx+284h], edx
0x18001776c  cmp     edx, ebp
0x18001776e  jge     short loc_180017730
0x180017770  mov     ecx, edi
0x180017772  mov     [rbx+284h], eax
0x180017778  sub     ecx, edx
0x18001777a  mov     edx, 5Ah ; 'Z'
0x18001777f  shl     edx, cl
0x180017781  or      edx, r8d
0x180017784  mov     [rbx+280h], edx
0x18001778a  cmp     eax, ebp
0x18001778c  jl      short loc_1800177CA
0x18001778e  xchg    ax, ax
0x180017790  mov     rax, [rbx+50h]
0x180017794  shr     edx, 18h
0x180017797  movsxd  rcx, r9d
0x18001779a  mov     [rcx+rax], dl
0x18001779d  mov     r9d, [rbx+74h]
0x1800177a1  mov     edx, [rbx+280h]
0x1800177a7  inc     r9d
0x1800177aa  mov     eax, [rbx+284h]
0x1800177b0  shl     edx, 8
0x1800177b3  add     eax, 0FFFFFFF8h
0x1800177b6  mov     [rbx+74h], r9d
0x1800177ba  mov     [rbx+280h], edx
0x1800177c0  mov     [rbx+284h], eax
0x1800177c6  cmp     eax, ebp
0x1800177c8  jge     short loc_180017790
0x1800177ca  movzx   r10d, byte ptr [rbx+298h]
0x1800177d2  mov     ecx, edi
0x1800177d4  sub     ecx, eax
0x1800177d6  mov     r8d, 68h ; 'h'
0x1800177dc  shl     r8d, cl
0x1800177df  add     r10b, 30h ; '0'
0x1800177e3  or      r8d, edx
0x1800177e6  lea     edx, [rax+8]
0x1800177e9  mov     [rbx+280h], r8d
0x1800177f0  mov     [rbx+284h], edx
0x1800177f6  cmp     edx, ebp
0x1800177f8  jl      short loc_18001783F
0x1800177fa  nop     word ptr [rax+rax+00h]
0x180017800  mov     rax, [rbx+50h]
0x180017804  shr     r8d, 18h
0x180017808  movsxd  rcx, r9d
0x18001780b  mov     [rcx+rax], r8b
0x18001780f  mov     r9d, [rbx+74h]
0x180017813  mov     r8d, [rbx+280h]
0x18001781a  inc     r9d
0x18001781d  mov     edx, [rbx+284h]
0x180017823  shl     r8d, 8
0x180017827  add     edx, 0FFFFFFF8h
0x18001782a  mov     [rbx+74h], r9d
0x18001782e  mov     [rbx+280h], r8d
0x180017835  mov     [rbx+284h], edx
0x18001783b  cmp     edx, ebp
0x18001783d  jge     short loc_180017800
0x18001783f  mov     ecx, edi
0x180017841  movzx   eax, r10b
0x180017845  sub     ecx, edx
0x180017847  shl     eax, cl
0x180017849  or      eax, r8d
0x18001784c  mov     [rbx+280h], eax
0x180017852  lea     eax, [rdx+8]
0x180017855  mov     [rbx+284h], eax
0x18001785b  cmp     dword ptr [rbx+6Ch], 0
0x18001785f  jle     loc_180017B6E
0x180017865  mov     edx, [rbx+284h]
0x18001786b  cmp     edx, ebp
0x18001786d  jl      short loc_1800178A7
0x18001786f  nop
0x180017870  movsxd  rdx, dword ptr [rbx+74h]
0x180017874  movzx   eax, byte ptr [rbx+283h]
0x18001787b  mov     rcx, [rbx+50h]
0x18001787f  mov     [rdx+rcx], al
0x180017882  mov     eax, [rbx+280h]
0x180017888  mov     edx, [rbx+284h]
0x18001788e  inc     dword ptr [rbx+74h]
0x180017891  add     edx, 0FFFFFFF8h
0x180017894  shl     eax, 8
0x180017897  mov     [rbx+280h], eax
0x18001789d  mov     [rbx+284h], edx
0x1800178a3  cmp     edx, ebp
0x1800178a5  jge     short loc_180017870
0x1800178a7  mov     ecx, edi
0x1800178a9  mov     eax, 31h ; '1'
0x1800178ae  sub     ecx, edx
0x1800178b0  shl     eax, cl
0x1800178b2  or      [rbx+280h], eax
0x1800178b8  lea     eax, [rdx+8]
0x1800178bb  mov     r8d, [rbx+280h]
0x1800178c2  mov     [rbx+284h], eax
0x1800178c8  cmp     eax, ebp
0x1800178ca  jl      short loc_180017908
0x1800178cc  nop     dword ptr [rax+00h]
0x1800178d0  movsxd  rcx, dword ptr [rbx+74h]
0x1800178d4  mov     rax, [rbx+50h]
0x1800178d8  shr     r8d, 18h
0x1800178dc  mov     [rcx+rax], r8b
0x1800178e0  mov     r8d, [rbx+280h]
0x1800178e7  mov     eax, [rbx+284h]
0x1800178ed  inc     dword ptr [rbx+74h]
0x1800178f0  add     eax, 0FFFFFFF8h
0x1800178f3  shl     r8d, 8
0x1800178f7  mov     [rbx+280h], r8d
0x1800178fe  mov     [rbx+284h], eax
0x180017904  cmp     eax, ebp
0x180017906  jge     short loc_1800178D0
0x180017908  mov     ecx, edi
0x18001790a  mov     edx, 41h ; 'A'
0x18001790f  sub     ecx, eax
0x180017911  add     eax, ebp
0x180017913  shl     edx, cl
0x180017915  or      edx, r8d
0x180017918  mov     [rbx+284h], eax
0x18001791e  mov     [rbx+280h], edx
0x180017924  cmp     eax, ebp
0x180017926  jl      short loc_180017963
0x180017928  nop     dword ptr [rax+rax+00000000h]
0x180017930  movsxd  rcx, dword ptr [rbx+74h]
0x180017934  mov     rax, [rbx+50h]
0x180017938  shr     edx, 18h
0x18001793b  mov     [rcx+rax], dl
0x18001793e  mov     edx, [rbx+280h]
0x180017944  mov     eax, [rbx+284h]
0x18001794a  inc     dword ptr [rbx+74h]
0x18001794d  add     eax, 0FFFFFFF8h
0x180017950  shl     edx, 8
0x180017953  mov     [rbx+280h], edx
0x180017959  mov     [rbx+284h], eax
0x18001795f  cmp     eax, ebp
0x180017961  jge     short loc_180017930
0x180017963  mov     ecx, edi
0x180017965  mov     r9d, 59h ; 'Y'
0x18001796b  sub     ecx, eax
0x18001796d  mov     r8d, r9d
0x180017970  shl     r8d, cl
0x180017973  add     eax, ebp
0x180017975  or      r8d, edx
0x180017978  mov     [rbx+284h], eax
0x18001797e  mov     [rbx+280h], r8d
0x180017985  cmp     eax, ebp
0x180017987  jl      short loc_1800179C8
0x180017989  nop     dword ptr [rax+00000000h]
0x180017990  movsxd  rcx, dword ptr [rbx+74h]
0x180017994  mov     rax, [rbx+50h]
0x180017998  shr     r8d, 18h
0x18001799c  mov     [rcx+rax], r8b
0x1800179a0  mov     r8d, [rbx+280h]
0x1800179a7  mov     eax, [rbx+284h]
0x1800179ad  inc     dword ptr [rbx+74h]
0x1800179b0  add     eax, 0FFFFFFF8h
0x1800179b3  shl     r8d, 8
0x1800179b7  mov     [rbx+280h], r8d
0x1800179be  mov     [rbx+284h], eax
0x1800179c4  cmp     eax, ebp
0x1800179c6  jge     short loc_180017990
0x1800179c8  mov     ecx, edi
0x1800179ca  mov     edx, 26h ; '&'
0x1800179cf  sub     ecx, eax
0x1800179d1  add     eax, ebp
0x1800179d3  shl     edx, cl
0x1800179d5  or      edx, r8d
0x1800179d8  mov     [rbx+284h], eax
0x1800179de  mov     [rbx+280h], edx
0x1800179e4  cmp     eax, ebp
0x1800179e6  jl      short loc_180017A23
0x1800179e8  nop     dword ptr [rax+rax+00000000h]
0x1800179f0  movsxd  rcx, dword ptr [rbx+74h]
0x1800179f4  mov     rax, [rbx+50h]
0x1800179f8  shr     edx, 18h
0x1800179fb  mov     [rcx+rax], dl
0x1800179fe  mov     edx, [rbx+280h]
0x180017a04  mov     eax, [rbx+284h]
0x180017a0a  inc     dword ptr [rbx+74h]
0x180017a0d  add     eax, 0FFFFFFF8h
0x180017a10  shl     edx, 8
0x180017a13  mov     [rbx+280h], edx
0x180017a19  mov     [rbx+284h], eax
0x180017a1f  cmp     eax, ebp
0x180017a21  jge     short loc_1800179F0
0x180017a23  mov     ecx, edi
0x180017a25  mov     r8d, 53h ; 'S'
0x180017a2b  sub     ecx, eax
0x180017a2d  add     eax, ebp
0x180017a2f  shl     r8d, cl
0x180017a32  or      r8d, edx
0x180017a35  mov     [rbx+284h], eax
0x180017a3b  mov     [rbx+280h], r8d
0x180017a42  cmp     eax, ebp
0x180017a44  jl      short loc_180017A88
0x180017a46  nop     word ptr [rax+rax+00000000h]
0x180017a50  movsxd  rcx, dword ptr [rbx+74h]
0x180017a54  mov     rax, [rbx+50h]
0x180017a58  shr     r8d, 18h
0x180017a5c  mov     [rcx+rax], r8b
0x180017a60  mov     r8d, [rbx+280h]
0x180017a67  mov     eax, [rbx+284h]
0x180017a6d  inc     dword ptr [rbx+74h]
0x180017a70  add     eax, 0FFFFFFF8h
0x180017a73  shl     r8d, 8
0x180017a77  mov     [rbx+280h], r8d
0x180017a7e  mov     [rbx+284h], eax
0x180017a84  cmp     eax, ebp
0x180017a86  jge     short loc_180017A50
0x180017a88  mov     edx, [rbx+288h]
0x180017a8e  mov     ecx, edi
0x180017a90  sub     ecx, eax
0x180017a92  add     eax, ebp
0x180017a94  shl     r9d, cl
0x180017a97  mov     rcx, rbx
0x180017a9a  or      r9d, r8d
0x180017a9d  mov     [rbx+284h], eax
0x180017aa3  mov     [rbx+280h], r9d
0x180017aaa  call    bsPutUInt32
0x180017aaf  mov     eax, [rbx+284h]
0x180017ab5  cmp     eax, ebp
0x180017ab7  jl      short loc_180017AF7
0x180017ab9  nop     dword ptr [rax+00000000h]
0x180017ac0  movzx   eax, byte ptr [rbx+283h]
0x180017ac7  movsxd  rdx, dword ptr [rbx+74h]
0x180017acb  mov     rcx, [rbx+50h]
0x180017acf  mov     [rdx+rcx], al
0x180017ad2  mov     eax, [rbx+280h]
0x180017ad8  inc     dword ptr [rbx+74h]
0x180017adb  shl     eax, 8
0x180017ade  mov     [rbx+280h], eax
0x180017ae4  mov     eax, [rbx+284h]
0x180017aea  add     eax, 0FFFFFFF8h
0x180017aed  mov     [rbx+284h], eax
0x180017af3  cmp     eax, ebp
0x180017af5  jge     short loc_180017AC0
0x180017af7  mov     edx, [rbx+280h]
0x180017afd  inc     eax
0x180017aff  mov     r8d, [rbx+30h]
0x180017b03  mov     [rbx+284h], eax
0x180017b09  cmp     eax, ebp
  ... truncated ...
```
