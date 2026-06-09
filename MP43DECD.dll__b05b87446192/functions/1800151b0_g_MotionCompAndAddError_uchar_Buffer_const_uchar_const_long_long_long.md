# g_MotionCompAndAddError(uchar *,Buffer const *,uchar const *,long,long,long)

- ea: `0x1800151b0`
- end: `0x180015720`
- name: `?g_MotionCompAndAddError@@YAXPEAEPEBTBuffer@@PEBEJJJ@Z`
- size: `1392`
- prototype: `void __fastcall(unsigned __int8 *, const union Buffer *, const unsigned __int8 *, int, int, int)`
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x1800151b0`

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
0x1800151b0  push    rbx
0x1800151b2  push    rbp
0x1800151b3  push    rsi
0x1800151b4  push    rdi
0x1800151b5  push    r12
0x1800151b7  push    r13
0x1800151b9  push    r14
0x1800151bb  push    r15
0x1800151bd  xor     eax, eax
0x1800151bf  movsxd  r14, r9d
0x1800151c2  mov     r10, r8
0x1800151c5  mov     r11, rdx
0x1800151c8  mov     rbx, rcx
0x1800151cb  lea     edi, [rax+8]
0x1800151ce  cmp     [rsp+40h+arg_28], eax
0x1800151d2  jz      loc_180015449
0x1800151d8  mov     esi, 0FFFFFF00h
0x1800151dd  cmp     [rsp+40h+arg_20], eax
0x1800151e1  jz      loc_1800152F1
0x1800151e7  mov     r8, cs:?g_rgiClapTabMC@@3PEAEEA; uchar * g_rgiClapTabMC
0x1800151ee  movzx   edx, byte ptr [r10+3]
0x1800151f3  add     edx, [r11+0Ch]
0x1800151f7  movzx   r15d, byte ptr [r10+2]
0x1800151fc  mov     eax, edx
0x1800151fe  add     r15d, [r11+8]
0x180015202  movzx   ebp, byte ptr [r10+1]
0x180015207  or      eax, r15d
0x18001520a  add     ebp, [r11+4]
0x18001520e  movzx   r9d, byte ptr [r10]
0x180015212  or      eax, ebp
0x180015214  add     r9d, [r11]
0x180015217  or      eax, r9d
0x18001521a  test    esi, eax
0x18001521c  jnz     short loc_180015231
0x18001521e  shl     edx, 8
0x180015221  or      edx, r15d
0x180015224  shl     edx, 8
0x180015227  or      edx, ebp
0x180015229  shl     edx, 8
0x18001522c  or      edx, r9d
0x18001522f  jmp     short loc_180015260
0x180015231  movsxd  rax, edx
0x180015234  movzx   edx, byte ptr [rax+r8]
0x180015239  shl     edx, 8
0x18001523c  movsxd  rax, r15d
0x18001523f  movzx   ecx, byte ptr [rax+r8]
0x180015244  or      edx, ecx
0x180015246  movsxd  rax, ebp
0x180015249  shl     edx, 8
0x18001524c  movzx   ecx, byte ptr [rax+r8]
0x180015251  or      edx, ecx
0x180015253  movsxd  rax, r9d
0x180015256  shl     edx, 8
0x180015259  movzx   ecx, byte ptr [rax+r8]
0x18001525e  or      edx, ecx
0x180015260  mov     [rbx], edx
0x180015262  movzx   edx, byte ptr [r10+7]
0x180015267  add     edx, [r11+1Ch]
0x18001526b  movzx   r15d, byte ptr [r10+6]
0x180015270  mov     eax, edx
0x180015272  add     r15d, [r11+18h]
0x180015276  movzx   ebp, byte ptr [r10+5]
0x18001527b  or      eax, r15d
0x18001527e  add     ebp, [r11+14h]
0x180015282  movzx   r9d, byte ptr [r10+4]
0x180015287  or      eax, ebp
0x180015289  add     r9d, [r11+10h]
0x18001528d  or      eax, r9d
0x180015290  test    esi, eax
0x180015292  jnz     short loc_1800152A7
0x180015294  shl     edx, 8
0x180015297  or      edx, r15d
0x18001529a  shl     edx, 8
0x18001529d  or      edx, ebp
0x18001529f  shl     edx, 8
0x1800152a2  or      edx, r9d
0x1800152a5  jmp     short loc_1800152D6
0x1800152a7  movsxd  rax, edx
0x1800152aa  movzx   edx, byte ptr [rax+r8]
0x1800152af  shl     edx, 8
0x1800152b2  movsxd  rax, r15d
0x1800152b5  movzx   ecx, byte ptr [rax+r8]
0x1800152ba  or      edx, ecx
0x1800152bc  movsxd  rax, ebp
0x1800152bf  shl     edx, 8
0x1800152c2  movzx   ecx, byte ptr [rax+r8]
0x1800152c7  or      edx, ecx
0x1800152c9  movsxd  rax, r9d
0x1800152cc  shl     edx, 8
0x1800152cf  movzx   ecx, byte ptr [rax+r8]
0x1800152d4  or      edx, ecx
0x1800152d6  mov     [rbx+4], edx
0x1800152d9  add     r10, r14
0x1800152dc  add     rbx, r14
0x1800152df  add     r11, 20h ; ' '
0x1800152e3  sub     edi, 1
0x1800152e6  jnz     loc_1800151EE
0x1800152ec  jmp     loc_180015713
0x1800152f1  mov     r9, cs:?g_rgiClapTabMC@@3PEAEEA; uchar * g_rgiClapTabMC
0x1800152f8  movzx   r8d, byte ptr [r10+1]
0x1800152fd  movzx   edx, byte ptr [r10+2]
0x180015302  movzx   ebp, byte ptr [r10]
0x180015306  inc     ebp
0x180015308  add     ebp, r8d
0x18001530b  lea     r15d, [r8+1]
0x18001530f  movzx   r8d, byte ptr [r10+3]
0x180015314  lea     r12d, [rdx+1]
0x180015318  add     r15d, edx
0x18001531b  shr     ebp, 1
0x18001531d  add     ebp, [r11]
0x180015320  add     r12d, r8d
0x180015323  movzx   edx, byte ptr [r10+4]
0x180015328  inc     edx
0x18001532a  shr     r12d, 1
0x18001532d  add     r12d, [r11+8]
0x180015331  add     edx, r8d
0x180015334  shr     edx, 1
0x180015336  add     edx, [r11+0Ch]
0x18001533a  shr     r15d, 1
0x18001533d  mov     eax, edx
0x18001533f  add     r15d, [r11+4]
0x180015343  or      eax, r12d
0x180015346  or      eax, r15d
0x180015349  or      eax, ebp
0x18001534b  test    esi, eax
0x18001534d  jnz     short loc_180015362
0x18001534f  shl     edx, 8
0x180015352  or      edx, r12d
0x180015355  shl     edx, 8
0x180015358  or      edx, r15d
0x18001535b  shl     edx, 8
0x18001535e  or      edx, ebp
0x180015360  jmp     short loc_180015391
0x180015362  movsxd  rax, edx
0x180015365  movzx   edx, byte ptr [rax+r9]
0x18001536a  shl     edx, 8
0x18001536d  movsxd  rax, r12d
0x180015370  movzx   ecx, byte ptr [rax+r9]
0x180015375  or      edx, ecx
0x180015377  movsxd  rax, r15d
0x18001537a  shl     edx, 8
0x18001537d  movzx   ecx, byte ptr [rax+r9]
0x180015382  or      edx, ecx
0x180015384  movsxd  rax, ebp
0x180015387  shl     edx, 8
0x18001538a  movzx   ecx, byte ptr [rax+r9]
0x18001538f  or      edx, ecx
0x180015391  mov     [rbx], edx
0x180015393  movzx   r8d, byte ptr [r10+5]
0x180015398  movzx   edx, byte ptr [r10+6]
0x18001539d  movzx   ebp, byte ptr [r10+4]
0x1800153a2  inc     ebp
0x1800153a4  add     ebp, r8d
0x1800153a7  lea     r15d, [r8+1]
0x1800153ab  movzx   r8d, byte ptr [r10+7]
0x1800153b0  lea     r12d, [rdx+1]
0x1800153b4  add     r15d, edx
0x1800153b7  shr     ebp, 1
0x1800153b9  add     ebp, [r11+10h]
0x1800153bd  add     r12d, r8d
0x1800153c0  movzx   edx, byte ptr [r10+8]
0x1800153c5  inc     edx
0x1800153c7  shr     r12d, 1
0x1800153ca  add     r12d, [r11+18h]
0x1800153ce  add     edx, r8d
0x1800153d1  shr     edx, 1
0x1800153d3  add     edx, [r11+1Ch]
0x1800153d7  shr     r15d, 1
0x1800153da  mov     eax, edx
0x1800153dc  add     r15d, [r11+14h]
0x1800153e0  or      eax, r12d
0x1800153e3  or      eax, r15d
0x1800153e6  or      eax, ebp
0x1800153e8  test    esi, eax
0x1800153ea  jnz     short loc_1800153FF
0x1800153ec  shl     edx, 8
0x1800153ef  or      edx, r12d
0x1800153f2  shl     edx, 8
0x1800153f5  or      edx, r15d
0x1800153f8  shl     edx, 8
0x1800153fb  or      edx, ebp
0x1800153fd  jmp     short loc_18001542E
0x1800153ff  movsxd  rax, edx
0x180015402  movzx   edx, byte ptr [rax+r9]
0x180015407  shl     edx, 8
0x18001540a  movsxd  rax, r12d
0x18001540d  movzx   ecx, byte ptr [rax+r9]
0x180015412  or      edx, ecx
0x180015414  movsxd  rax, r15d
0x180015417  shl     edx, 8
0x18001541a  movzx   ecx, byte ptr [rax+r9]
0x18001541f  or      edx, ecx
0x180015421  movsxd  rax, ebp
0x180015424  shl     edx, 8
0x180015427  movzx   ecx, byte ptr [rax+r9]
0x18001542c  or      edx, ecx
0x18001542e  mov     [rbx+4], edx
0x180015431  add     r10, r14
0x180015434  add     rbx, r14
0x180015437  add     r11, 20h ; ' '
0x18001543b  sub     edi, 1
0x18001543e  jnz     loc_1800152F8
0x180015444  jmp     loc_180015713
0x180015449  cmp     [rsp+40h+arg_20], eax
0x18001544d  jz      loc_1800155E3
0x180015453  mov     r9, cs:?g_rgiClapTabMC@@3PEAEEA; uchar * g_rgiClapTabMC
0x18001545a  mov     esi, 0FFFFFF00h
0x18001545f  movzx   ecx, byte ptr [r10]
0x180015463  lea     rbp, [r14+r10]
0x180015467  movzx   r15d, byte ptr [rbp+0]
0x18001546c  inc     ecx
0x18001546e  movzx   r12d, byte ptr [r10+1]
0x180015473  add     r15d, ecx
0x180015476  movzx   ecx, byte ptr [rbp+1]
0x18001547a  movzx   r13d, byte ptr [r10+2]
0x18001547f  inc     ecx
0x180015481  movzx   r8d, byte ptr [r10+3]
0x180015486  add     r12d, ecx
0x180015489  movzx   ecx, byte ptr [rbp+2]
0x18001548d  inc     r8d
0x180015490  inc     ecx
0x180015492  shr     r12d, 1
0x180015495  add     r12d, [r11+4]
0x180015499  add     r13d, ecx
0x18001549c  movzx   ecx, byte ptr [rbp+3]
0x1800154a0  add     r8d, ecx
0x1800154a3  shr     r13d, 1
0x1800154a6  add     r13d, [r11+8]
0x1800154aa  shr     r8d, 1
0x1800154ad  add     r8d, [r11+0Ch]
0x1800154b1  shr     r15d, 1
0x1800154b4  mov     eax, r8d
0x1800154b7  add     r15d, [r11]
0x1800154ba  or      eax, r13d
0x1800154bd  or      eax, r12d
0x1800154c0  or      eax, r15d
0x1800154c3  test    esi, eax
0x1800154c5  jnz     short loc_1800154DE
0x1800154c7  shl     r8d, 8
0x1800154cb  or      r8d, r13d
0x1800154ce  shl     r8d, 8
0x1800154d2  or      r8d, r12d
0x1800154d5  shl     r8d, 8
0x1800154d9  or      r8d, r15d
0x1800154dc  jmp     short loc_180015513
0x1800154de  movsxd  rax, r8d
0x1800154e1  movzx   r8d, byte ptr [rax+r9]
0x1800154e6  shl     r8d, 8
0x1800154ea  movsxd  rax, r13d
0x1800154ed  movzx   ecx, byte ptr [rax+r9]
0x1800154f2  or      r8d, ecx
0x1800154f5  movsxd  rax, r12d
0x1800154f8  shl     r8d, 8
0x1800154fc  movzx   ecx, byte ptr [rax+r9]
0x180015501  or      r8d, ecx
0x180015504  movsxd  rax, r15d
0x180015507  shl     r8d, 8
0x18001550b  movzx   ecx, byte ptr [rax+r9]
0x180015510  or      r8d, ecx
0x180015513  mov     [rbx], r8d
0x180015516  movzx   ecx, byte ptr [rbp+4]
0x18001551a  movzx   r15d, byte ptr [r10+4]
0x18001551f  inc     ecx
0x180015521  movzx   r12d, byte ptr [r10+5]
0x180015526  add     r15d, ecx
0x180015529  movzx   ecx, byte ptr [rbp+5]
0x18001552d  movzx   r13d, byte ptr [r10+6]
0x180015532  inc     ecx
0x180015534  movzx   r8d, byte ptr [r10+7]
0x180015539  add     r12d, ecx
0x18001553c  movzx   ecx, byte ptr [rbp+6]
0x180015540  inc     r8d
0x180015543  inc     ecx
0x180015545  shr     r12d, 1
0x180015548  add     r12d, [r11+14h]
0x18001554c  add     r13d, ecx
0x18001554f  movzx   ecx, byte ptr [rbp+7]
0x180015553  add     r8d, ecx
0x180015556  shr     r13d, 1
0x180015559  add     r13d, [r11+18h]
0x18001555d  shr     r8d, 1
0x180015560  add     r8d, [r11+1Ch]
0x180015564  shr     r15d, 1
0x180015567  mov     eax, r8d
0x18001556a  add     r15d, [r11+10h]
0x18001556e  or      eax, r13d
0x180015571  or      eax, r12d
0x180015574  or      eax, r15d
0x180015577  test    esi, eax
0x180015579  jnz     short loc_180015592
0x18001557b  shl     r8d, 8
0x18001557f  or      r8d, r13d
0x180015582  shl     r8d, 8
0x180015586  or      r8d, r12d
0x180015589  shl     r8d, 8
0x18001558d  or      r8d, r15d
0x180015590  jmp     short loc_1800155C7
0x180015592  movsxd  rax, r8d
0x180015595  movzx   r8d, byte ptr [rax+r9]
0x18001559a  shl     r8d, 8
  ... truncated ...
```
