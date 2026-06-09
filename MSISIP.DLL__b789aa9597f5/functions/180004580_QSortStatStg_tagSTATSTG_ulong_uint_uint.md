# QSortStatStg(tagSTATSTG *,ulong,uint,uint)

- ea: `0x180004580`
- end: `0x1800049fd`
- name: `?QSortStatStg@@YAXPEAUtagSTATSTG@@KII@Z`
- size: `1149`
- prototype: `void __fastcall(struct tagSTATSTG *, unsigned int, unsigned int, unsigned int)`
- caller_count: `3`
- callee_count: `2`
- tags: ``

## callers

- `0x180003370`
- `0x180003a70`
- `0x180004580`

## callees

- `0x180004580`
- `0x18000d2b6`

## pseudocode

```c
void __fastcall QSortStatStg(struct tagSTATSTG *a1, unsigned int a2, unsigned int a3, unsigned int a4)
{
  unsigned int v4; // r13d
  unsigned int v5; // r12d
  unsigned int v6; // r10d
  struct tagSTATSTG *v7; // rdi
  __int64 v8; // r8
  __int128 *v9; // rdx
  __int64 v10; // rcx
  __int128 v11; // xmm2
  __int128 v12; // xmm3
  __int128 v13; // xmm4
  __int128 v14; // xmm5
  __int128 v15; // xmm6
  __int64 v16; // r14
  __int64 v17; // rsi
  __int128 v18; // xmm3
  _WORD *v19; // rcx
  __int64 v20; // rax
  bool v21; // zf
  unsigned int v22; // edi
  __int64 v23; // rax
  unsigned int v24; // ebx
  size_t v25; // r8
  int v26; // eax
  __int128 v27; // xmm3
  _WORD *v28; // rcx
  __int64 v29; // rax
  unsigned int v30; // edi
  __int64 v31; // rax
  unsigned int v32; // ebx
  size_t v33; // r8
  int v34; // eax
  __int128 *v35; // rcx
  __int64 v36; // rax
  __int128 v37; // xmm2
  __int128 v38; // xmm3
  __int128 v39; // xmm4
  __int128 v40; // xmm5
  __int128 v41; // xmm6
  __int64 v42; // rcx
  __int64 v43; // rax
  __int128 v44; // xmm2
  __int128 v45; // xmm3
  __int128 v46; // xmm4
  __int128 v47; // xmm5
  __int128 v48; // xmm6
  unsigned int v49; // r15d
  unsigned int v50; // r14d
  unsigned int v51; // ebx
  __int128 v52; // xmm3
  __int64 v53; // rax
  _WORD *v54; // rcx
  unsigned int v55; // esi
  __int64 v56; // rax
  unsigned int v57; // edi
  size_t v58; // r8
  int v59; // eax
  __int128 *v60; // rdx
  __int64 v61; // rcx
  __int128 v62; // xmm2
  __int128 v63; // xmm3
  __int128 v64; // xmm4
  __int128 v65; // xmm5
  __int128 v66; // xmm6
  unsigned int v69; // [rsp+E0h] [rbp+77h]

  v69 = a3;
  v4 = a4;
  v5 = a3;
  v6 = a2;
  v7 = a1;
  while ( v5 < v4 )
  {
    if ( v4 - v5 + 1 < 8 )
    {
      v49 = v5 + 1;
      while ( 1 )
      {
        v50 = v5;
        v51 = v49;
        if ( v49 <= v4 )
          break;
LABEL_50:
        if ( v50 < v6 && v4 < v6 )
        {
          v60 = (__int128 *)((char *)v7 + 80 * v50);
          v61 = 10LL * v4;
          v62 = *v60;
          v63 = v60[1];
          v64 = v60[2];
          v65 = v60[3];
          v66 = v60[4];
          *v60 = *((_OWORD *)v7 + 5 * v4);
          v60[1] = *((_OWORD *)v7 + 5 * v4 + 1);
          v60[2] = *((_OWORD *)v7 + 5 * v4 + 2);
          v60[3] = *((_OWORD *)v7 + 5 * v4 + 3);
          v60[4] = *((_OWORD *)v7 + 5 * v4 + 4);
          *(_OWORD *)((char *)v7 + 8 * v61) = v62;
          *(_OWORD *)((char *)v7 + 8 * v61 + 16) = v63;
          *(_OWORD *)((char *)v7 + 8 * v61 + 32) = v64;
          *(_OWORD *)((char *)v7 + 8 * v61 + 48) = v65;
          *(_OWORD *)((char *)v7 + 8 * v61 + 64) = v66;
        }
        if ( --v4 <= v5 )
          return;
      }
      while ( 2 )
      {
        v52 = *((_OWORD *)a1 + 5 * v50);
        v53 = -1;
        v54 = (_WORD *)*((_QWORD *)a1 + 10 * v51);
        do
          v21 = v54[++v53] == 0;
        while ( !v21 );
        v55 = 2 * v53;
        v56 = -1;
        do
          v21 = *(_WORD *)(v52 + 2 * v56++ + 2) == 0;
        while ( !v21 );
        v57 = 2 * v56;
        v58 = v55;
        if ( v55 >= 2 * (int)v56 )
          v58 = v57;
        v59 = memcmp_0(v54, (const void *)v52, v58);
        if ( v59 )
        {
          if ( v59 >= 0 )
            goto LABEL_47;
        }
        else if ( v55 >= v57 )
        {
LABEL_47:
          v50 = v51;
        }
        if ( ++v51 > v4 )
        {
          v5 = v69;
          v7 = a1;
          v6 = a2;
          goto LABEL_50;
        }
        continue;
      }
    }
    if ( v5 < v6 )
    {
      v8 = (v5 + v4) >> 1;
      if ( (unsigned int)v8 < v6 )
      {
        v9 = (__int128 *)((char *)v7 + 80 * v5);
        v10 = 10 * v8;
        v11 = *v9;
        v12 = v9[1];
        v13 = v9[2];
        v14 = v9[3];
        v15 = v9[4];
        *v9 = *((_OWORD *)v7 + 5 * v8);
        v9[1] = *((_OWORD *)v7 + 5 * v8 + 1);
        v9[2] = *((_OWORD *)v7 + 5 * v8 + 2);
        v9[3] = *((_OWORD *)v7 + 5 * v8 + 3);
        v9[4] = *((_OWORD *)v7 + 5 * v8 + 4);
        *(_OWORD *)((char *)v7 + 8 * v10) = v11;
        *(_OWORD *)((char *)v7 + 8 * v10 + 16) = v12;
        *(_OWORD *)((char *)v7 + 8 * v10 + 32) = v13;
        *(_OWORD *)((char *)v7 + 8 * v10 + 48) = v14;
        *(_OWORD *)((char *)v7 + 8 * v10 + 64) = v15;
      }
    }
    LODWORD(v16) = v5;
    LODWORD(v17) = v4 + 1;
    while ( 1 )
    {
      do
      {
        while ( 1 )
        {
          v16 = (unsigned int)(v16 + 1);
          if ( (unsigned int)v16 > v4 )
            goto LABEL_17;
          v18 = *((_OWORD *)a1 + 5 * v5);
          v19 = (_WORD *)*((_QWORD *)a1 + 10 * v16);
          v20 = -1;
          do
            v21 = v19[++v20] == 0;
          while ( !v21 );
          v22 = 2 * v20;
          v23 = -1;
          do
            v21 = *(_WORD *)(v18 + 2 * v23++ + 2) == 0;
          while ( !v21 );
          v24 = 2 * v23;
          v25 = v22;
          if ( v22 >= 2 * (int)v23 )
            v25 = v24;
          v26 = memcmp_0(v19, (const void *)v18, v25);
          if ( !v26 )
            break;
          if ( v26 > 0 )
            goto LABEL_17;
        }
      }
      while ( v22 <= v24 );
LABEL_17:
      while ( 1 )
      {
        v17 = (unsigned int)(v17 - 1);
        if ( (unsigned int)v17 <= v69 )
          break;
        v27 = *((_OWORD *)a1 + 5 * v5);
        v28 = (_WORD *)*((_QWORD *)a1 + 10 * v17);
        v29 = -1;
        do
          v21 = v28[++v29] == 0;
        while ( !v21 );
        v30 = 2 * v29;
        v31 = -1;
        do
          v21 = *(_WORD *)(v27 + 2 * v31++ + 2) == 0;
        while ( !v21 );
        v32 = 2 * v31;
        v33 = v30;
        if ( v30 >= 2 * (int)v31 )
          v33 = v32;
        v34 = memcmp_0(v28, (const void *)v27, v33);
        if ( v34 )
        {
          if ( v34 < 0 )
            break;
        }
        else if ( v30 < v32 )
        {
          break;
        }
      }
      v4 = a4;
      v6 = a2;
      if ( (unsigned int)v17 < (unsigned int)v16 )
        break;
      if ( (unsigned int)v16 < a2 && (unsigned int)v17 < a2 )
      {
        v42 = 10 * v16;
        v43 = 10 * v17;
        v44 = *((_OWORD *)a1 + 5 * v16);
        v45 = *((_OWORD *)a1 + 5 * v16 + 1);
        v46 = *((_OWORD *)a1 + 5 * v16 + 2);
        v47 = *((_OWORD *)a1 + 5 * v16 + 3);
        v48 = *((_OWORD *)a1 + 5 * v16 + 4);
        *(_OWORD *)((char *)a1 + 8 * v42) = *((_OWORD *)a1 + 5 * v17);
        *(_OWORD *)((char *)a1 + 8 * v42 + 16) = *((_OWORD *)a1 + 5 * v17 + 1);
        *(_OWORD *)((char *)a1 + 8 * v42 + 32) = *((_OWORD *)a1 + 5 * v17 + 2);
        *(_OWORD *)((char *)a1 + 8 * v42 + 48) = *((_OWORD *)a1 + 5 * v17 + 3);
        *(_OWORD *)((char *)a1 + 8 * v42 + 64) = *((_OWORD *)a1 + 5 * v17 + 4);
        *(_OWORD *)((char *)a1 + 8 * v43) = v44;
        *(_OWORD *)((char *)a1 + 8 * v43 + 16) = v45;
        *(_OWORD *)((char *)a1 + 8 * v43 + 32) = v46;
        *(_OWORD *)((char *)a1 + 8 * v43 + 48) = v47;
        *(_OWORD *)((char *)a1 + 8 * v43 + 64) = v48;
      }
    }
    v7 = a1;
    if ( v69 < a2 && (unsigned int)v17 < a2 )
    {
      v35 = (__int128 *)((char *)a1 + 80 * v5);
      v36 = 10 * v17;
      v37 = *v35;
      v38 = v35[1];
      v39 = v35[2];
      v40 = v35[3];
      v41 = v35[4];
      *v35 = *((_OWORD *)a1 + 5 * v17);
      v35[1] = *((_OWORD *)a1 + 5 * v17 + 1);
      v35[2] = *((_OWORD *)a1 + 5 * v17 + 2);
      v35[3] = *((_OWORD *)a1 + 5 * v17 + 3);
      v35[4] = *((_OWORD *)a1 + 5 * v17 + 4);
      *(_OWORD *)((char *)a1 + 8 * v36) = v37;
      *(_OWORD *)((char *)a1 + 8 * v36 + 16) = v38;
      *(_OWORD *)((char *)a1 + 8 * v36 + 32) = v39;
      *(_OWORD *)((char *)a1 + 8 * v36 + 48) = v40;
      *(_OWORD *)((char *)a1 + 8 * v36 + 64) = v41;
    }
    if ( v69 != (_DWORD)v17 )
    {
      QSortStatStg(a1, a2, v69, v17 - 1);
      v6 = a2;
    }
    if ( (_DWORD)v16 == a4 )
      return;
    v5 = v16;
    v69 = v16;
  }
}

```

## disassembly

```asm
0x180004580  mov     [rsp-8+arg_18], r9d
0x180004585  mov     [rsp-8+arg_10], r8d
0x18000458a  mov     [rsp-8+arg_8], edx
0x18000458e  mov     [rsp-8+arg_0], rcx
0x180004593  push    rbp
0x180004594  push    rbx
0x180004595  push    rsi
0x180004596  push    rdi
0x180004597  push    r12
0x180004599  push    r13
0x18000459b  push    r14
0x18000459d  push    r15
0x18000459f  lea     rbp, [rsp-1Fh]
0x1800045a4  sub     rsp, 88h
0x1800045ab  movaps  [rsp+0C0h+var_50], xmm6
0x1800045b0  mov     r13d, r9d
0x1800045b3  mov     r12d, r8d
0x1800045b6  mov     r10d, edx
0x1800045b9  mov     rdi, rcx
0x1800045bc  cmp     r12d, r13d
0x1800045bf  jnb     loc_1800049B1
0x1800045c5  mov     eax, r13d
0x1800045c8  sub     eax, r12d
0x1800045cb  inc     eax
0x1800045cd  cmp     eax, 8
0x1800045d0  jb      loc_180004897
0x1800045d6  cmp     r12d, r10d
0x1800045d9  jnb     short loc_180004652
0x1800045db  lea     r8d, [r12+r13]
0x1800045df  shr     r8d, 1
0x1800045e2  cmp     r8d, r10d
0x1800045e5  jnb     short loc_180004652
0x1800045e7  mov     eax, r12d
0x1800045ea  lea     rcx, [r8+r8*4]
0x1800045ee  lea     rdx, [rax+rax*4]
0x1800045f2  shl     rdx, 4
0x1800045f6  add     rdx, rdi
0x1800045f9  add     rcx, rcx
0x1800045fc  movups  xmm2, xmmword ptr [rdx]
0x1800045ff  movups  xmm0, xmmword ptr [rdi+rcx*8]
0x180004603  movups  xmm3, xmmword ptr [rdx+10h]
0x180004607  movups  xmm4, xmmword ptr [rdx+20h]
0x18000460b  movups  xmm5, xmmword ptr [rdx+30h]
0x18000460f  movups  xmm6, xmmword ptr [rdx+40h]
0x180004613  movups  xmmword ptr [rdx], xmm0
0x180004616  movups  xmm1, xmmword ptr [rdi+rcx*8+10h]
0x18000461b  movups  xmmword ptr [rdx+10h], xmm1
0x18000461f  movups  xmm0, xmmword ptr [rdi+rcx*8+20h]
0x180004624  movups  xmmword ptr [rdx+20h], xmm0
0x180004628  movups  xmm1, xmmword ptr [rdi+rcx*8+30h]
0x18000462d  movups  xmmword ptr [rdx+30h], xmm1
0x180004631  movups  xmm0, xmmword ptr [rdi+rcx*8+40h]
0x180004636  movups  xmmword ptr [rdx+40h], xmm0
0x18000463a  movups  xmmword ptr [rdi+rcx*8], xmm2
0x18000463e  movups  xmmword ptr [rdi+rcx*8+10h], xmm3
0x180004643  movups  xmmword ptr [rdi+rcx*8+20h], xmm4
0x180004648  movups  xmmword ptr [rdi+rcx*8+30h], xmm5
0x18000464d  movups  xmmword ptr [rdi+rcx*8+40h], xmm6
0x180004652  mov     r14d, r12d
0x180004655  mov     r15d, r12d
0x180004658  lea     esi, [r13+1]
0x18000465c  mov     r12, [rbp+57h+arg_0]
0x180004660  inc     r14d
0x180004663  cmp     r14d, r13d
0x180004666  ja      short loc_1800046D7
0x180004668  lea     rax, [r15+r15*4]
0x18000466c  add     rax, rax
0x18000466f  lea     rcx, [r14+r14*4]
0x180004673  add     rcx, rcx
0x180004676  movups  xmm3, xmmword ptr [r12+rax*8]
0x18000467b  mov     rcx, [r12+rcx*8]; Buf1
0x18000467f  mov     rax, 0FFFFFFFFFFFFFFFFh
0x180004686  nop     word ptr [rax+rax+00000000h]
0x180004690  cmp     word ptr [rcx+rax*2+2], 0
0x180004696  lea     rax, [rax+1]
0x18000469a  jnz     short loc_180004690
0x18000469c  lea     edi, [rax+rax]
0x18000469f  movq    rdx, xmm3; Buf2
0x1800046a4  mov     rax, 0FFFFFFFFFFFFFFFFh
0x1800046ab  nop     dword ptr [rax+rax+00h]
0x1800046b0  cmp     word ptr [rdx+rax*2+2], 0
0x1800046b6  lea     rax, [rax+1]
0x1800046ba  jnz     short loc_1800046B0
0x1800046bc  lea     ebx, [rax+rax]
0x1800046bf  mov     r8d, edi
0x1800046c2  cmp     edi, ebx
0x1800046c4  cmovnb  r8d, ebx; Size
0x1800046c8  call    memcmp_0
0x1800046cd  test    eax, eax
0x1800046cf  jz      loc_1800049CA
0x1800046d5  jle     short loc_180004660
0x1800046d7  mov     r12d, [rbp+57h+arg_10]
0x1800046db  mov     r13, [rbp+57h+arg_0]
0x1800046df  nop
0x1800046e0  dec     esi
0x1800046e2  cmp     esi, r12d
0x1800046e5  jbe     short loc_180004757
0x1800046e7  lea     rax, [r15+r15*4]
0x1800046eb  add     rax, rax
0x1800046ee  lea     rcx, [rsi+rsi*4]
0x1800046f2  add     rcx, rcx
0x1800046f5  movups  xmm3, xmmword ptr [r13+rax*8+0]
0x1800046fb  mov     rcx, [r13+rcx*8+0]; Buf1
0x180004700  mov     rax, 0FFFFFFFFFFFFFFFFh
0x180004707  nop     word ptr [rax+rax+00000000h]
0x180004710  cmp     word ptr [rcx+rax*2+2], 0
0x180004716  lea     rax, [rax+1]
0x18000471a  jnz     short loc_180004710
0x18000471c  lea     edi, [rax+rax]
0x18000471f  movq    rdx, xmm3; Buf2
0x180004724  mov     rax, 0FFFFFFFFFFFFFFFFh
0x18000472b  nop     dword ptr [rax+rax+00h]
0x180004730  cmp     word ptr [rdx+rax*2+2], 0
0x180004736  lea     rax, [rax+1]
0x18000473a  jnz     short loc_180004730
0x18000473c  lea     ebx, [rax+rax]
0x18000473f  mov     r8d, edi
0x180004742  cmp     edi, ebx
0x180004744  cmovnb  r8d, ebx; Size
0x180004748  call    memcmp_0
0x18000474d  test    eax, eax
0x18000474f  jz      loc_1800049DD
0x180004755  jns     short loc_1800046E0
0x180004757  mov     r13d, [rbp+57h+arg_18]
0x18000475b  mov     r10d, [rbp+57h+arg_8]
0x18000475f  cmp     esi, r14d
0x180004762  jnb     loc_18000480E
0x180004768  mov     rdi, [rbp+57h+arg_0]
0x18000476c  cmp     r12d, r10d
0x18000476f  jnb     short loc_1800047DE
0x180004771  cmp     esi, r10d
0x180004774  jnb     short loc_1800047DE
0x180004776  lea     rcx, [r15+r15*4]
0x18000477a  shl     rcx, 4
0x18000477e  lea     rax, [rsi+rsi*4]
0x180004782  add     rcx, rdi
0x180004785  add     rax, rax
0x180004788  movups  xmm2, xmmword ptr [rcx]
0x18000478b  movups  xmm0, xmmword ptr [rdi+rax*8]
0x18000478f  movups  xmm3, xmmword ptr [rcx+10h]
0x180004793  movups  xmm4, xmmword ptr [rcx+20h]
0x180004797  movups  xmm5, xmmword ptr [rcx+30h]
0x18000479b  movups  xmm6, xmmword ptr [rcx+40h]
0x18000479f  movups  xmmword ptr [rcx], xmm0
0x1800047a2  movups  xmm1, xmmword ptr [rdi+rax*8+10h]
0x1800047a7  movups  xmmword ptr [rcx+10h], xmm1
0x1800047ab  movups  xmm0, xmmword ptr [rdi+rax*8+20h]
0x1800047b0  movups  xmmword ptr [rcx+20h], xmm0
0x1800047b4  movups  xmm1, xmmword ptr [rdi+rax*8+30h]
0x1800047b9  movups  xmmword ptr [rcx+30h], xmm1
0x1800047bd  movups  xmm0, xmmword ptr [rdi+rax*8+40h]
0x1800047c2  movups  xmmword ptr [rcx+40h], xmm0
0x1800047c6  movups  xmmword ptr [rdi+rax*8], xmm2
0x1800047ca  movups  xmmword ptr [rdi+rax*8+10h], xmm3
0x1800047cf  movups  xmmword ptr [rdi+rax*8+20h], xmm4
0x1800047d4  movups  xmmword ptr [rdi+rax*8+30h], xmm5
0x1800047d9  movups  xmmword ptr [rdi+rax*8+40h], xmm6
0x1800047de  cmp     r12d, esi
0x1800047e1  jz      short loc_1800047F9
0x1800047e3  lea     r9d, [rsi-1]; unsigned int
0x1800047e7  mov     r8d, r12d; unsigned int
0x1800047ea  mov     edx, r10d; unsigned int
0x1800047ed  mov     rcx, rdi; struct tagSTATSTG *
0x1800047f0  call    ?QSortStatStg@@YAXPEAUtagSTATSTG@@KII@Z; QSortStatStg(tagSTATSTG *,ulong,uint,uint)
0x1800047f5  mov     r10d, [rbp+57h+arg_8]
0x1800047f9  cmp     r14d, r13d
0x1800047fc  jz      loc_1800049B1
0x180004802  mov     r12d, r14d
0x180004805  mov     [rbp+57h+arg_10], r14d
0x180004809  jmp     loc_1800045BC
0x18000480e  cmp     r14d, r10d
0x180004811  jnb     loc_18000465C
0x180004817  cmp     esi, r10d
0x18000481a  jnb     loc_18000465C
0x180004820  mov     rdi, [rbp+57h+arg_0]
0x180004824  lea     rcx, [r14+r14*4]
0x180004828  add     rcx, rcx
0x18000482b  lea     rax, [rsi+rsi*4]
0x18000482f  add     rax, rax
0x180004832  movups  xmm2, xmmword ptr [rdi+rcx*8]
0x180004836  movups  xmm0, xmmword ptr [rdi+rax*8]
0x18000483a  movups  xmm3, xmmword ptr [rdi+rcx*8+10h]
0x18000483f  movups  xmm4, xmmword ptr [rdi+rcx*8+20h]
0x180004844  movups  xmm5, xmmword ptr [rdi+rcx*8+30h]
0x180004849  movups  xmm6, xmmword ptr [rdi+rcx*8+40h]
0x18000484e  movups  xmmword ptr [rdi+rcx*8], xmm0
0x180004852  movups  xmm1, xmmword ptr [rdi+rax*8+10h]
0x180004857  movups  xmmword ptr [rdi+rcx*8+10h], xmm1
0x18000485c  movups  xmm0, xmmword ptr [rdi+rax*8+20h]
0x180004861  movups  xmmword ptr [rdi+rcx*8+20h], xmm0
0x180004866  movups  xmm1, xmmword ptr [rdi+rax*8+30h]
0x18000486b  movups  xmmword ptr [rdi+rcx*8+30h], xmm1
0x180004870  movups  xmm0, xmmword ptr [rdi+rax*8+40h]
0x180004875  movups  xmmword ptr [rdi+rcx*8+40h], xmm0
0x18000487a  movups  xmmword ptr [rdi+rax*8], xmm2
0x18000487e  movups  xmmword ptr [rdi+rax*8+10h], xmm3
0x180004883  movups  xmmword ptr [rdi+rax*8+20h], xmm4
0x180004888  movups  xmmword ptr [rdi+rax*8+30h], xmm5
0x18000488d  movups  xmmword ptr [rdi+rax*8+40h], xmm6
0x180004892  jmp     loc_18000465C
0x180004897  lea     r15d, [r12+1]
0x18000489c  mov     r14d, r12d
0x18000489f  mov     ebx, r15d
0x1800048a2  cmp     r15d, r13d
0x1800048a5  ja      loc_18000492D
0x1800048ab  mov     r12, [rbp+57h+arg_0]
0x1800048af  nop
0x1800048b0  mov     eax, r14d
0x1800048b3  lea     rcx, [rax+rax*4]
0x1800048b7  mov     eax, ebx
0x1800048b9  add     rcx, rcx
0x1800048bc  movups  xmm3, xmmword ptr [r12+rcx*8]
0x1800048c1  lea     rcx, [rax+rax*4]
0x1800048c5  mov     rax, 0FFFFFFFFFFFFFFFFh
0x1800048cc  add     rcx, rcx
0x1800048cf  mov     rcx, [r12+rcx*8]; Buf1
0x1800048d3  cmp     word ptr [rcx+rax*2+2], 0
0x1800048d9  lea     rax, [rax+1]
0x1800048dd  jnz     short loc_1800048D3
0x1800048df  lea     esi, [rax+rax]
0x1800048e2  movq    rdx, xmm3; Buf2
0x1800048e7  mov     rax, 0FFFFFFFFFFFFFFFFh
0x1800048ee  xchg    ax, ax
0x1800048f0  cmp     word ptr [rdx+rax*2+2], 0
0x1800048f6  lea     rax, [rax+1]
0x1800048fa  jnz     short loc_1800048F0
0x1800048fc  lea     edi, [rax+rax]
0x1800048ff  mov     r8d, esi
0x180004902  cmp     esi, edi
0x180004904  cmovnb  r8d, edi; Size
0x180004908  call    memcmp_0
0x18000490d  test    eax, eax
0x18000490f  jz      loc_1800049EA
0x180004915  js      short loc_18000491A
0x180004917  mov     r14d, ebx
0x18000491a  inc     ebx
0x18000491c  cmp     ebx, r13d
0x18000491f  jbe     short loc_1800048B0
0x180004921  mov     r12d, [rbp+57h+arg_10]
0x180004925  mov     rdi, [rbp+57h+arg_0]
0x180004929  mov     r10d, [rbp+57h+arg_8]
0x18000492d  cmp     r14d, r10d
0x180004930  jnb     short loc_1800049A5
0x180004932  cmp     r13d, r10d
0x180004935  jnb     short loc_1800049A5
0x180004937  mov     eax, r14d
0x18000493a  lea     rdx, [rax+rax*4]
0x18000493e  mov     eax, r13d
0x180004941  shl     rdx, 4
0x180004945  add     rdx, rdi
0x180004948  lea     rcx, [rax+rax*4]
0x18000494c  add     rcx, rcx
0x18000494f  movups  xmm2, xmmword ptr [rdx]
0x180004952  movups  xmm3, xmmword ptr [rdx+10h]
0x180004956  movups  xmm0, xmmword ptr [rdi+rcx*8]
0x18000495a  movups  xmm4, xmmword ptr [rdx+20h]
0x18000495e  movups  xmm5, xmmword ptr [rdx+30h]
0x180004962  movups  xmm6, xmmword ptr [rdx+40h]
0x180004966  movups  xmmword ptr [rdx], xmm0
0x180004969  movups  xmm1, xmmword ptr [rdi+rcx*8+10h]
0x18000496e  movups  xmmword ptr [rdx+10h], xmm1
0x180004972  movups  xmm0, xmmword ptr [rdi+rcx*8+20h]
0x180004977  movups  xmmword ptr [rdx+20h], xmm0
0x18000497b  movups  xmm1, xmmword ptr [rdi+rcx*8+30h]
0x180004980  movups  xmmword ptr [rdx+30h], xmm1
0x180004984  movups  xmm0, xmmword ptr [rdi+rcx*8+40h]
0x180004989  movups  xmmword ptr [rdx+40h], xmm0
0x18000498d  movups  xmmword ptr [rdi+rcx*8], xmm2
0x180004991  movups  xmmword ptr [rdi+rcx*8+10h], xmm3
0x180004996  movups  xmmword ptr [rdi+rcx*8+20h], xmm4
0x18000499b  movups  xmmword ptr [rdi+rcx*8+30h], xmm5
0x1800049a0  movups  xmmword ptr [rdi+rcx*8+40h], xmm6
0x1800049a5  dec     r13d
0x1800049a8  cmp     r13d, r12d
0x1800049ab  ja      loc_18000489C
0x1800049b1  movaps  xmm6, [rsp+0C0h+var_50]
0x1800049b6  add     rsp, 88h
0x1800049bd  pop     r15
0x1800049bf  pop     r14
0x1800049c1  pop     r13
0x1800049c3  pop     r12
0x1800049c5  pop     rdi
0x1800049c6  pop     rsi
0x1800049c7  pop     rbx
0x1800049c8  pop     rbp
0x1800049c9  retn
0x1800049ca  cmp     edi, ebx
0x1800049cc  jb      loc_180004660
0x1800049d2  jz      loc_180004660
0x1800049d8  jmp     loc_1800046D7
0x1800049dd  cmp     edi, ebx
0x1800049df  jnb     loc_1800046E0
0x1800049e5  jmp     loc_180004757
0x1800049ea  cmp     esi, edi
0x1800049ec  jb      loc_18000491A
0x1800049f2  jz      loc_180004917
0x1800049f8  jmp     loc_180004917
```
