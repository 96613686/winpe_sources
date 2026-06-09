# g_MotionCompAndAddError(uchar *,Buffer const *,uchar const *,long,long,long)

- ea: `0x180015270`
- end: `0x1800157e0`
- name: `?g_MotionCompAndAddError@@YAXPEAEPEBTBuffer@@PEBEJJJ@Z`
- size: `1392`
- prototype: `void __fastcall(unsigned __int8 *, const union Buffer *, const unsigned __int8 *, int, int, int)`
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x180015270`

## pseudocode

```c
void __fastcall g_MotionCompAndAddError(
        unsigned __int8 *a1,
        const union Buffer *a2,
        const unsigned __int8 *a3,
        int a4,
        int a5,
        int a6)
{
  __int64 v6; // r14
  int v10; // edi
  unsigned __int8 *v11; // r8
  int v12; // edx
  int v13; // r15d
  int v14; // ebp
  int v15; // r9d
  int v16; // edx
  int v17; // edx
  int v18; // r15d
  int v19; // ebp
  int v20; // r9d
  int v21; // edx
  unsigned __int8 *v22; // r9
  int v23; // r8d
  int v24; // edx
  unsigned int v25; // ebp
  int v26; // r15d
  int v27; // r8d
  unsigned int v28; // r15d
  int v29; // ebp
  signed int v30; // r12d
  signed int v31; // edx
  int v32; // r15d
  int v33; // edx
  int v34; // r8d
  int v35; // edx
  unsigned int v36; // ebp
  int v37; // r15d
  int v38; // r8d
  unsigned int v39; // r15d
  int v40; // ebp
  signed int v41; // r12d
  signed int v42; // edx
  int v43; // r15d
  int v44; // edx
  unsigned __int8 *v45; // r9
  const unsigned __int8 *v46; // rbp
  signed int v47; // r12d
  signed int v48; // r13d
  signed int v49; // r8d
  signed int v50; // r15d
  int v51; // r8d
  signed int v52; // r12d
  signed int v53; // r13d
  signed int v54; // r8d
  signed int v55; // r15d
  int v56; // r8d
  unsigned __int8 *v57; // rsi
  int v58; // r8d
  int v59; // edx
  int v60; // r8d
  int v61; // edx
  int v62; // r8d
  int v63; // edx
  int v64; // r8d
  __int64 v65; // rax

  v6 = a4;
  v10 = 8;
  if ( a6 )
  {
    if ( a5 )
    {
      v11 = g_rgiClapTabMC;
      do
      {
        v12 = *((_DWORD *)a2 + 3) + a3[3];
        v13 = *((_DWORD *)a2 + 2) + a3[2];
        v14 = *((_DWORD *)a2 + 1) + a3[1];
        v15 = *(_DWORD *)a2 + *a3;
        if ( ((v15 | v14 | v13 | v12) & 0xFFFFFF00) != 0 )
          v16 = v11[v15] | ((v11[v14] | ((v11[v13] | (v11[v12] << 8)) << 8)) << 8);
        else
          v16 = v15 | ((v14 | ((v13 | (v12 << 8)) << 8)) << 8);
        *(_DWORD *)a1 = v16;
        v17 = *((_DWORD *)a2 + 7) + a3[7];
        v18 = *((_DWORD *)a2 + 6) + a3[6];
        v19 = *((_DWORD *)a2 + 5) + a3[5];
        v20 = *((_DWORD *)a2 + 4) + a3[4];
        if ( ((v20 | v19 | v18 | v17) & 0xFFFFFF00) != 0 )
          v21 = v11[v20] | ((v11[v19] | ((v11[v18] | (v11[v17] << 8)) << 8)) << 8);
        else
          v21 = v20 | ((v19 | ((v18 | (v17 << 8)) << 8)) << 8);
        *((_DWORD *)a1 + 1) = v21;
        a3 += v6;
        a1 += v6;
        a2 = (const union Buffer *)((char *)a2 + 32);
        --v10;
      }
      while ( v10 );
    }
    else
    {
      v22 = g_rgiClapTabMC;
      do
      {
        v23 = a3[1];
        v24 = a3[2];
        v25 = v23 + *a3 + 1;
        v26 = v23 + 1;
        v27 = a3[3];
        v28 = v24 + v26;
        v29 = *(_DWORD *)a2 + (v25 >> 1);
        v30 = *((_DWORD *)a2 + 2) + ((unsigned int)(v27 + v24 + 1) >> 1);
        v31 = *((_DWORD *)a2 + 3) + ((v27 + (unsigned int)a3[4] + 1) >> 1);
        v32 = *((_DWORD *)a2 + 1) + (v28 >> 1);
        if ( ((v29 | v32 | v30 | v31) & 0xFFFFFF00) != 0 )
          v33 = v22[v29] | ((v22[v32] | ((v22[v30] | (v22[v31] << 8)) << 8)) << 8);
        else
          v33 = v29 | ((v32 | ((v30 | (v31 << 8)) << 8)) << 8);
        *(_DWORD *)a1 = v33;
        v34 = a3[5];
        v35 = a3[6];
        v36 = v34 + a3[4] + 1;
        v37 = v34 + 1;
        v38 = a3[7];
        v39 = v35 + v37;
        v40 = *((_DWORD *)a2 + 4) + (v36 >> 1);
        v41 = *((_DWORD *)a2 + 6) + ((unsigned int)(v38 + v35 + 1) >> 1);
        v42 = *((_DWORD *)a2 + 7) + ((v38 + (unsigned int)a3[8] + 1) >> 1);
        v43 = *((_DWORD *)a2 + 5) + (v39 >> 1);
        if ( ((v40 | v43 | v41 | v42) & 0xFFFFFF00) != 0 )
          v44 = v22[v40] | ((v22[v43] | ((v22[v41] | (v22[v42] << 8)) << 8)) << 8);
        else
          v44 = v40 | ((v43 | ((v41 | (v42 << 8)) << 8)) << 8);
        *((_DWORD *)a1 + 1) = v44;
        a3 += v6;
        a1 += v6;
        a2 = (const union Buffer *)((char *)a2 + 32);
        --v10;
      }
      while ( v10 );
    }
  }
  else if ( a5 )
  {
    v45 = g_rgiClapTabMC;
    do
    {
      v46 = &a3[v6];
      v47 = *((_DWORD *)a2 + 1) + ((a3[v6 + 1] + 1 + (unsigned int)a3[1]) >> 1);
      v48 = *((_DWORD *)a2 + 2) + ((a3[v6 + 2] + 1 + (unsigned int)a3[2]) >> 1);
      v49 = *((_DWORD *)a2 + 3) + ((a3[v6 + 3] + (unsigned int)a3[3] + 1) >> 1);
      v50 = *(_DWORD *)a2 + ((*a3 + 1 + (unsigned int)a3[v6]) >> 1);
      if ( ((v50 | v47 | v48 | v49) & 0xFFFFFF00) != 0 )
        v51 = v45[v50] | ((v45[v47] | ((v45[v48] | (v45[v49] << 8)) << 8)) << 8);
      else
        v51 = v50 | ((v47 | ((v48 | (v49 << 8)) << 8)) << 8);
      *(_DWORD *)a1 = v51;
      v52 = *((_DWORD *)a2 + 5) + ((v46[5] + 1 + (unsigned int)a3[5]) >> 1);
      v53 = *((_DWORD *)a2 + 6) + ((v46[6] + 1 + (unsigned int)a3[6]) >> 1);
      v54 = *((_DWORD *)a2 + 7) + ((v46[7] + (unsigned int)a3[7] + 1) >> 1);
      v55 = *((_DWORD *)a2 + 4) + ((v46[4] + 1 + (unsigned int)a3[4]) >> 1);
      if ( ((v55 | v52 | v53 | v54) & 0xFFFFFF00) != 0 )
        v56 = v45[v55] | ((v45[v52] | ((v45[v53] | (v45[v54] << 8)) << 8)) << 8);
      else
        v56 = v55 | ((v52 | ((v53 | (v54 << 8)) << 8)) << 8);
      *((_DWORD *)a1 + 1) = v56;
      a2 = (const union Buffer *)((char *)a2 + 32);
      a1 += v6;
      a3 += v6;
      --v10;
    }
    while ( v10 );
  }
  else
  {
    v57 = g_rgiClapTabMC;
    do
    {
      v58 = a3[a4 + 1] + 2 + a3[1];
      *a1 = v57[*(_DWORD *)a2 + ((v58 + *a3 + (unsigned int)a3[a4]) >> 2)];
      v59 = a3[2] + a3[a4 + 2];
      a1[1] = v57[*((_DWORD *)a2 + 1) + ((unsigned int)(v58 + v59) >> 2)];
      v60 = a3[3] + a3[a4 + 3];
      a1[2] = v57[*((_DWORD *)a2 + 2) + ((unsigned int)(v60 + v59 + 2) >> 2)];
      v61 = a3[4] + a3[a4 + 4];
      a1[3] = v57[*((_DWORD *)a2 + 3) + ((unsigned int)(v61 + v60 + 2) >> 2)];
      v62 = a3[5] + a3[a4 + 5];
      a1[4] = v57[*((_DWORD *)a2 + 4) + ((unsigned int)(v62 + v61 + 2) >> 2)];
      v63 = a3[6] + a3[a4 + 6];
      a1[5] = v57[*((_DWORD *)a2 + 5) + ((unsigned int)(v63 + v62 + 2) >> 2)];
      v64 = a3[7] + a3[a4 + 7];
      a1[6] = v57[*((_DWORD *)a2 + 6) + ((unsigned int)(v64 + v63 + 2) >> 2)];
      v65 = (int)(*((_DWORD *)a2 + 7) + ((a3[8] + (unsigned int)a3[a4 + 8] + v64 + 2) >> 2));
      a3 += a4;
      a1[7] = v57[v65];
      a2 = (const union Buffer *)((char *)a2 + 32);
      a1 += a4;
      --v10;
    }
    while ( v10 );
  }
}

```

## disassembly

```asm
0x180015270  push    rbx
0x180015272  push    rbp
0x180015273  push    rsi
0x180015274  push    rdi
0x180015275  push    r12
0x180015277  push    r13
0x180015279  push    r14
0x18001527b  push    r15
0x18001527d  xor     eax, eax
0x18001527f  movsxd  r14, r9d
0x180015282  mov     r10, r8
0x180015285  mov     r11, rdx
0x180015288  mov     rbx, rcx
0x18001528b  lea     edi, [rax+8]
0x18001528e  cmp     [rsp+40h+arg_28], eax
0x180015292  jz      loc_180015509
0x180015298  mov     esi, 0FFFFFF00h
0x18001529d  cmp     [rsp+40h+arg_20], eax
0x1800152a1  jz      loc_1800153B1
0x1800152a7  mov     r8, cs:?g_rgiClapTabMC@@3PEAEEA; uchar * g_rgiClapTabMC
0x1800152ae  movzx   edx, byte ptr [r10+3]
0x1800152b3  add     edx, [r11+0Ch]
0x1800152b7  movzx   r15d, byte ptr [r10+2]
0x1800152bc  mov     eax, edx
0x1800152be  add     r15d, [r11+8]
0x1800152c2  movzx   ebp, byte ptr [r10+1]
0x1800152c7  or      eax, r15d
0x1800152ca  add     ebp, [r11+4]
0x1800152ce  movzx   r9d, byte ptr [r10]
0x1800152d2  or      eax, ebp
0x1800152d4  add     r9d, [r11]
0x1800152d7  or      eax, r9d
0x1800152da  test    esi, eax
0x1800152dc  jnz     short loc_1800152F1
0x1800152de  shl     edx, 8
0x1800152e1  or      edx, r15d
0x1800152e4  shl     edx, 8
0x1800152e7  or      edx, ebp
0x1800152e9  shl     edx, 8
0x1800152ec  or      edx, r9d
0x1800152ef  jmp     short loc_180015320
0x1800152f1  movsxd  rax, edx
0x1800152f4  movzx   edx, byte ptr [rax+r8]
0x1800152f9  shl     edx, 8
0x1800152fc  movsxd  rax, r15d
0x1800152ff  movzx   ecx, byte ptr [rax+r8]
0x180015304  or      edx, ecx
0x180015306  movsxd  rax, ebp
0x180015309  shl     edx, 8
0x18001530c  movzx   ecx, byte ptr [rax+r8]
0x180015311  or      edx, ecx
0x180015313  movsxd  rax, r9d
0x180015316  shl     edx, 8
0x180015319  movzx   ecx, byte ptr [rax+r8]
0x18001531e  or      edx, ecx
0x180015320  mov     [rbx], edx
0x180015322  movzx   edx, byte ptr [r10+7]
0x180015327  add     edx, [r11+1Ch]
0x18001532b  movzx   r15d, byte ptr [r10+6]
0x180015330  mov     eax, edx
0x180015332  add     r15d, [r11+18h]
0x180015336  movzx   ebp, byte ptr [r10+5]
0x18001533b  or      eax, r15d
0x18001533e  add     ebp, [r11+14h]
0x180015342  movzx   r9d, byte ptr [r10+4]
0x180015347  or      eax, ebp
0x180015349  add     r9d, [r11+10h]
0x18001534d  or      eax, r9d
0x180015350  test    esi, eax
0x180015352  jnz     short loc_180015367
0x180015354  shl     edx, 8
0x180015357  or      edx, r15d
0x18001535a  shl     edx, 8
0x18001535d  or      edx, ebp
0x18001535f  shl     edx, 8
0x180015362  or      edx, r9d
0x180015365  jmp     short loc_180015396
0x180015367  movsxd  rax, edx
0x18001536a  movzx   edx, byte ptr [rax+r8]
0x18001536f  shl     edx, 8
0x180015372  movsxd  rax, r15d
0x180015375  movzx   ecx, byte ptr [rax+r8]
0x18001537a  or      edx, ecx
0x18001537c  movsxd  rax, ebp
0x18001537f  shl     edx, 8
0x180015382  movzx   ecx, byte ptr [rax+r8]
0x180015387  or      edx, ecx
0x180015389  movsxd  rax, r9d
0x18001538c  shl     edx, 8
0x18001538f  movzx   ecx, byte ptr [rax+r8]
0x180015394  or      edx, ecx
0x180015396  mov     [rbx+4], edx
0x180015399  add     r10, r14
0x18001539c  add     rbx, r14
0x18001539f  add     r11, 20h ; ' '
0x1800153a3  sub     edi, 1
0x1800153a6  jnz     loc_1800152AE
0x1800153ac  jmp     loc_1800157D3
0x1800153b1  mov     r9, cs:?g_rgiClapTabMC@@3PEAEEA; uchar * g_rgiClapTabMC
0x1800153b8  movzx   r8d, byte ptr [r10+1]
0x1800153bd  movzx   edx, byte ptr [r10+2]
0x1800153c2  movzx   ebp, byte ptr [r10]
0x1800153c6  inc     ebp
0x1800153c8  add     ebp, r8d
0x1800153cb  lea     r15d, [r8+1]
0x1800153cf  movzx   r8d, byte ptr [r10+3]
0x1800153d4  lea     r12d, [rdx+1]
0x1800153d8  add     r15d, edx
0x1800153db  shr     ebp, 1
0x1800153dd  add     ebp, [r11]
0x1800153e0  add     r12d, r8d
0x1800153e3  movzx   edx, byte ptr [r10+4]
0x1800153e8  inc     edx
0x1800153ea  shr     r12d, 1
0x1800153ed  add     r12d, [r11+8]
0x1800153f1  add     edx, r8d
0x1800153f4  shr     edx, 1
0x1800153f6  add     edx, [r11+0Ch]
0x1800153fa  shr     r15d, 1
0x1800153fd  mov     eax, edx
0x1800153ff  add     r15d, [r11+4]
0x180015403  or      eax, r12d
0x180015406  or      eax, r15d
0x180015409  or      eax, ebp
0x18001540b  test    esi, eax
0x18001540d  jnz     short loc_180015422
0x18001540f  shl     edx, 8
0x180015412  or      edx, r12d
0x180015415  shl     edx, 8
0x180015418  or      edx, r15d
0x18001541b  shl     edx, 8
0x18001541e  or      edx, ebp
0x180015420  jmp     short loc_180015451
0x180015422  movsxd  rax, edx
0x180015425  movzx   edx, byte ptr [rax+r9]
0x18001542a  shl     edx, 8
0x18001542d  movsxd  rax, r12d
0x180015430  movzx   ecx, byte ptr [rax+r9]
0x180015435  or      edx, ecx
0x180015437  movsxd  rax, r15d
0x18001543a  shl     edx, 8
0x18001543d  movzx   ecx, byte ptr [rax+r9]
0x180015442  or      edx, ecx
0x180015444  movsxd  rax, ebp
0x180015447  shl     edx, 8
0x18001544a  movzx   ecx, byte ptr [rax+r9]
0x18001544f  or      edx, ecx
0x180015451  mov     [rbx], edx
0x180015453  movzx   r8d, byte ptr [r10+5]
0x180015458  movzx   edx, byte ptr [r10+6]
0x18001545d  movzx   ebp, byte ptr [r10+4]
0x180015462  inc     ebp
0x180015464  add     ebp, r8d
0x180015467  lea     r15d, [r8+1]
0x18001546b  movzx   r8d, byte ptr [r10+7]
0x180015470  lea     r12d, [rdx+1]
0x180015474  add     r15d, edx
0x180015477  shr     ebp, 1
0x180015479  add     ebp, [r11+10h]
0x18001547d  add     r12d, r8d
0x180015480  movzx   edx, byte ptr [r10+8]
0x180015485  inc     edx
0x180015487  shr     r12d, 1
0x18001548a  add     r12d, [r11+18h]
0x18001548e  add     edx, r8d
0x180015491  shr     edx, 1
0x180015493  add     edx, [r11+1Ch]
0x180015497  shr     r15d, 1
0x18001549a  mov     eax, edx
0x18001549c  add     r15d, [r11+14h]
0x1800154a0  or      eax, r12d
0x1800154a3  or      eax, r15d
0x1800154a6  or      eax, ebp
0x1800154a8  test    esi, eax
0x1800154aa  jnz     short loc_1800154BF
0x1800154ac  shl     edx, 8
0x1800154af  or      edx, r12d
0x1800154b2  shl     edx, 8
0x1800154b5  or      edx, r15d
0x1800154b8  shl     edx, 8
0x1800154bb  or      edx, ebp
0x1800154bd  jmp     short loc_1800154EE
0x1800154bf  movsxd  rax, edx
0x1800154c2  movzx   edx, byte ptr [rax+r9]
0x1800154c7  shl     edx, 8
0x1800154ca  movsxd  rax, r12d
0x1800154cd  movzx   ecx, byte ptr [rax+r9]
0x1800154d2  or      edx, ecx
0x1800154d4  movsxd  rax, r15d
0x1800154d7  shl     edx, 8
0x1800154da  movzx   ecx, byte ptr [rax+r9]
0x1800154df  or      edx, ecx
0x1800154e1  movsxd  rax, ebp
0x1800154e4  shl     edx, 8
0x1800154e7  movzx   ecx, byte ptr [rax+r9]
0x1800154ec  or      edx, ecx
0x1800154ee  mov     [rbx+4], edx
0x1800154f1  add     r10, r14
0x1800154f4  add     rbx, r14
0x1800154f7  add     r11, 20h ; ' '
0x1800154fb  sub     edi, 1
0x1800154fe  jnz     loc_1800153B8
0x180015504  jmp     loc_1800157D3
0x180015509  cmp     [rsp+40h+arg_20], eax
0x18001550d  jz      loc_1800156A3
0x180015513  mov     r9, cs:?g_rgiClapTabMC@@3PEAEEA; uchar * g_rgiClapTabMC
0x18001551a  mov     esi, 0FFFFFF00h
0x18001551f  movzx   ecx, byte ptr [r10]
0x180015523  lea     rbp, [r14+r10]
0x180015527  movzx   r15d, byte ptr [rbp+0]
0x18001552c  inc     ecx
0x18001552e  movzx   r12d, byte ptr [r10+1]
0x180015533  add     r15d, ecx
0x180015536  movzx   ecx, byte ptr [rbp+1]
0x18001553a  movzx   r13d, byte ptr [r10+2]
0x18001553f  inc     ecx
0x180015541  movzx   r8d, byte ptr [r10+3]
0x180015546  add     r12d, ecx
0x180015549  movzx   ecx, byte ptr [rbp+2]
0x18001554d  inc     r8d
0x180015550  inc     ecx
0x180015552  shr     r12d, 1
0x180015555  add     r12d, [r11+4]
0x180015559  add     r13d, ecx
0x18001555c  movzx   ecx, byte ptr [rbp+3]
0x180015560  add     r8d, ecx
0x180015563  shr     r13d, 1
0x180015566  add     r13d, [r11+8]
0x18001556a  shr     r8d, 1
0x18001556d  add     r8d, [r11+0Ch]
0x180015571  shr     r15d, 1
0x180015574  mov     eax, r8d
0x180015577  add     r15d, [r11]
0x18001557a  or      eax, r13d
0x18001557d  or      eax, r12d
0x180015580  or      eax, r15d
0x180015583  test    esi, eax
0x180015585  jnz     short loc_18001559E
0x180015587  shl     r8d, 8
0x18001558b  or      r8d, r13d
0x18001558e  shl     r8d, 8
0x180015592  or      r8d, r12d
0x180015595  shl     r8d, 8
0x180015599  or      r8d, r15d
0x18001559c  jmp     short loc_1800155D3
0x18001559e  movsxd  rax, r8d
0x1800155a1  movzx   r8d, byte ptr [rax+r9]
0x1800155a6  shl     r8d, 8
0x1800155aa  movsxd  rax, r13d
0x1800155ad  movzx   ecx, byte ptr [rax+r9]
0x1800155b2  or      r8d, ecx
0x1800155b5  movsxd  rax, r12d
0x1800155b8  shl     r8d, 8
0x1800155bc  movzx   ecx, byte ptr [rax+r9]
0x1800155c1  or      r8d, ecx
0x1800155c4  movsxd  rax, r15d
0x1800155c7  shl     r8d, 8
0x1800155cb  movzx   ecx, byte ptr [rax+r9]
0x1800155d0  or      r8d, ecx
0x1800155d3  mov     [rbx], r8d
0x1800155d6  movzx   ecx, byte ptr [rbp+4]
0x1800155da  movzx   r15d, byte ptr [r10+4]
0x1800155df  inc     ecx
0x1800155e1  movzx   r12d, byte ptr [r10+5]
0x1800155e6  add     r15d, ecx
0x1800155e9  movzx   ecx, byte ptr [rbp+5]
0x1800155ed  movzx   r13d, byte ptr [r10+6]
0x1800155f2  inc     ecx
0x1800155f4  movzx   r8d, byte ptr [r10+7]
0x1800155f9  add     r12d, ecx
0x1800155fc  movzx   ecx, byte ptr [rbp+6]
0x180015600  inc     r8d
0x180015603  inc     ecx
0x180015605  shr     r12d, 1
0x180015608  add     r12d, [r11+14h]
0x18001560c  add     r13d, ecx
0x18001560f  movzx   ecx, byte ptr [rbp+7]
0x180015613  add     r8d, ecx
0x180015616  shr     r13d, 1
0x180015619  add     r13d, [r11+18h]
0x18001561d  shr     r8d, 1
0x180015620  add     r8d, [r11+1Ch]
0x180015624  shr     r15d, 1
0x180015627  mov     eax, r8d
0x18001562a  add     r15d, [r11+10h]
0x18001562e  or      eax, r13d
0x180015631  or      eax, r12d
0x180015634  or      eax, r15d
0x180015637  test    esi, eax
0x180015639  jnz     short loc_180015652
0x18001563b  shl     r8d, 8
0x18001563f  or      r8d, r13d
0x180015642  shl     r8d, 8
0x180015646  or      r8d, r12d
0x180015649  shl     r8d, 8
0x18001564d  or      r8d, r15d
0x180015650  jmp     short loc_180015687
0x180015652  movsxd  rax, r8d
0x180015655  movzx   r8d, byte ptr [rax+r9]
0x18001565a  shl     r8d, 8
  ... truncated ...
```
