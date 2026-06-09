# Input::ConstructWidth<Input::VirtualRelation<91,96,28,1>,4,1>::MoveSynchronousInstruction(Input::ClearUnit &)

- ea: `0x1800376e0`
- end: `0x180037ea4`
- name: `?MoveSynchronousInstruction@?$ConstructWidth@V?$VirtualRelation@$0FL@$0GA@$0BM@$00@Input@@$03$00@Input@@QEAAXAEAVClearUnit@2@@Z`
- size: `1988`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x180036e70`

## callees

- `0x180003180`
- `0x1800376e0`
- `0x18003ae50`

## pseudocode

```c
__int64 __fastcall Input::ConstructWidth<Input::VirtualRelation<91,96,28,1>,4,1>::MoveSynchronousInstruction(
        _QWORD *a1,
        int *a2)
{
  int *v2; // rbx
  _QWORD *v3; // rdi
  unsigned int v4; // r9d
  int v5; // edx
  char *v6; // rax
  __int64 v7; // rcx
  __int64 v8; // r8
  int v9; // r12d
  int v10; // r11d
  __int16 *v11; // r10
  __int64 v12; // rdx
  __int64 v13; // rcx
  unsigned __int16 *v14; // rax
  char *v15; // r8
  __int64 v16; // r9
  int v17; // ebx
  int v18; // r14d
  __int64 v19; // r13
  int v20; // edi
  int v21; // r9d
  unsigned __int8 *v22; // r15
  int v23; // r10d
  int v24; // r8d
  int v25; // r11d
  int v26; // r9d
  int v27; // r10d
  int v28; // r8d
  int v29; // r11d
  int v30; // r9d
  int v31; // r10d
  int v32; // r8d
  int v33; // r11d
  int v34; // r9d
  int v35; // r10d
  int v36; // r8d
  int v37; // r11d
  int v38; // r9d
  int v39; // r10d
  int v40; // r8d
  int v41; // r11d
  int v42; // r9d
  int v43; // r10d
  int v44; // r8d
  int v45; // r11d
  int v46; // r9d
  int v47; // r10d
  int v48; // r8d
  signed int v49; // r8d
  int v50; // r10d
  int v51; // r12d
  int v52; // esi
  int v53; // r13d
  unsigned __int16 *v54; // r15
  unsigned int v55; // r9d
  __int16 v56; // r8
  unsigned int v57; // r11d
  unsigned __int16 v58; // r11
  int v59; // r9d
  _BYTE *v60; // r11
  __int64 v61; // r8
  int v62; // r9d
  _BYTE *v63; // r11
  int v64; // r13d
  __int64 v65; // rdx
  __int64 v66; // rcx
  unsigned __int16 *v67; // r15
  unsigned int v68; // r9d
  __int16 v69; // r8
  unsigned int v70; // r11d
  unsigned __int16 v71; // r11
  int v72; // r9d
  _BYTE *v73; // r11
  __int64 v74; // r8
  int v75; // r9d
  _BYTE *v76; // r11
  int v77; // esi
  int v78; // ecx
  _BYTE *v79; // rdx
  int v80; // ecx
  _BYTE *v81; // rdx
  int *v82; // rax
  int v83; // edx
  _BYTE *v84; // r8
  __int64 v85; // rdx
  int v86; // edx
  _BYTE *v87; // r8
  __int64 result; // rax
  int v89; // [rsp+20h] [rbp-E0h]
  unsigned int v90; // [rsp+24h] [rbp-DCh]
  unsigned int v91; // [rsp+28h] [rbp-D8h]
  int v92; // [rsp+2Ch] [rbp-D4h]
  int v93; // [rsp+30h] [rbp-D0h]
  int v94; // [rsp+40h] [rbp-C0h]
  __int64 v95; // [rsp+48h] [rbp-B8h]
  __int64 v96; // [rsp+50h] [rbp-B0h]
  __int16 *v97; // [rsp+58h] [rbp-A8h]
  __int64 v98; // [rsp+60h] [rbp-A0h]
  _BYTE v101[20]; // [rsp+80h] [rbp-80h] BYREF
  int v102; // [rsp+94h] [rbp-6Ch]
  __int128 v103; // [rsp+98h] [rbp-68h]
  __int128 v104; // [rsp+B0h] [rbp-50h] BYREF
  _BYTE v105[64]; // [rsp+C0h] [rbp-40h] BYREF
  int v106; // [rsp+100h] [rbp+0h]
  int v107; // [rsp+104h] [rbp+4h]
  __int128 v108; // [rsp+110h] [rbp+10h] BYREF
  _BYTE v109[48]; // [rsp+120h] [rbp+20h] BYREF
  int v110; // [rsp+150h] [rbp+50h] BYREF
  int v111; // [rsp+154h] [rbp+54h]

  v2 = a2;
  v3 = a1;
  if ( *(_DWORD *)Input::IntegratedSelection::NewAPI == 2 )
  {
    v4 = 1;
    v5 = 89;
  }
  else
  {
    v4 = 19;
    v5 = 65;
  }
  v92 = v5;
  v6 = (char *)&v104 + 8;
  v90 = v4;
  v7 = 5;
  do
  {
    *((_WORD *)v6 - 4) = 0;
    *(_QWORD *)(v6 - 4) = 0;
    *((_DWORD *)v6 + 1) = 0;
    v6 += 16;
    --v7;
  }
  while ( v7 );
  v8 = v2[1906];
  v9 = 0;
  v106 = 0;
  v89 = -1;
  v107 = -1;
  LOWORD(v103) = 0;
  v93 = v8;
  if ( (int)v8 < v2[1907] )
  {
    v10 = v5 + 1;
    v11 = &word_1800CAA82[28 * v8];
    v94 = v5 + 1;
    v97 = v11;
    v12 = *v3 + 192 * (v4 + 91 * v8 + 1);
    v98 = v12;
    do
    {
      v13 = v12 - 192;
      HIDWORD(v103) = v8;
      v95 = v12 - 192;
      v14 = (unsigned __int16 *)(v12 - 384);
      v96 = v12;
      v15 = (char *)&v108 + 8;
      v16 = 4;
      do
      {
        *((_WORD *)v15 - 4) = 0;
        *(_QWORD *)(v15 - 4) = 0;
        *((_DWORD *)v15 + 1) = 0;
        v15 += 16;
        --v16;
      }
      while ( v16 );
      v17 = -1;
      v110 = 0;
      *(_WORD *)v101 = 0;
      v18 = 0;
      v111 = -1;
      *(_OWORD *)&v101[4] = 0;
      v19 = 2;
      v102 = -1;
      v20 = -1;
      v21 = -1;
      v22 = (unsigned __int8 *)v11;
      do
      {
        v23 = *(v22 - 2);
        v24 = v23;
        if ( v10 <= v23 )
          v24 = v10;
        v25 = *(v22 - 1);
        if ( v21 >= v23 )
          v23 = v21;
        v26 = *(v22 - 1);
        if ( v24 <= v25 )
          v26 = v24;
        if ( v23 >= v25 )
          v25 = v23;
        v27 = *v22;
        v28 = v27;
        if ( v26 <= v27 )
          v28 = v26;
        if ( v25 >= v27 )
          v27 = v25;
        v29 = v22[1];
        v30 = v29;
        if ( v28 <= v29 )
          v30 = v28;
        if ( v27 >= v29 )
          v29 = v27;
        v31 = v22[2];
        v32 = v31;
        if ( v30 <= v31 )
          v32 = v30;
        if ( v29 >= v31 )
          v31 = v29;
        v33 = v22[3];
        v34 = v33;
        if ( v32 <= v33 )
          v34 = v32;
        if ( v31 >= v33 )
          v33 = v31;
        v35 = v22[4];
        v36 = v35;
        if ( v34 <= v35 )
          v36 = v34;
        if ( v33 >= v35 )
          v35 = v33;
        v37 = v22[5];
        v38 = v37;
        if ( v36 <= v37 )
          v38 = v36;
        if ( v35 >= v37 )
          v37 = v35;
        v39 = v22[6];
        v40 = v39;
        if ( v38 <= v39 )
          v40 = v38;
        if ( v37 >= v39 )
          v39 = v37;
        v41 = v22[7];
        v42 = v41;
        if ( v40 <= v41 )
          v42 = v40;
        if ( v39 >= v41 )
          v41 = v39;
        v43 = v22[8];
        v44 = v43;
        if ( v42 <= v43 )
          v44 = v42;
        if ( v41 >= v43 )
          v43 = v41;
        v45 = v22[9];
        v46 = v45;
        if ( v44 <= v45 )
          v46 = v44;
        if ( v43 >= v45 )
          v45 = v43;
        v47 = v22[10];
        v48 = v47;
        if ( v46 <= v47 )
          v48 = v46;
        v21 = v22[11];
        if ( v45 >= v47 )
          v47 = v45;
        v10 = v22[11];
        if ( v48 <= v21 )
          v10 = v48;
        v22 += 14;
        if ( v47 >= v21 )
          v21 = v47;
        --v19;
      }
      while ( v19 );
      v49 = v90;
      v50 = *(_DWORD *)&v101[16];
      v51 = 45 - v10;
      v91 = v90;
      v52 = 136 - v21;
      do
      {
        DWORD2(v103) = v49;
        if ( v49 < v51 || v49 > v52 )
        {
          v64 = 0;
          v65 = v12 - (_QWORD)v14;
          v66 = v13 - (_QWORD)v14;
          v67 = v14;
          do
          {
            v68 = 26 * *v67;
            v69 = *(unsigned __int16 *)((char *)v67 + v66) >> 1;
            v70 = (26 * (unsigned int)*(unsigned __int16 *)((char *)v67 + v65)) >> 8;
            DWORD1(v103) = v64;
            v71 = v69 + (v68 >> 8) + v70;
            LOWORD(v103) = v71;
            if ( v50 >= 1 )
            {
              v74 = 2LL * v20;
              if ( v71 > *(_WORD *)&v101[16 * v20] )
              {
                v20 = 0;
                v75 = 1;
                *(_OWORD *)&v101[8 * v74] = v103;
                v50 = *(_DWORD *)&v101[16];
                v102 = 0;
                if ( *(int *)&v101[16] > 1 )
                {
                  v76 = &v101[16];
                  do
                  {
                    v76 += 16;
                    if ( *((_WORD *)v76 - 8) < *(_WORD *)&v101[16 * v20] )
                      v20 = v75;
                    ++v75;
                    v102 = v20;
                  }
                  while ( v75 < *(int *)&v101[16] );
                }
              }
            }
            else
            {
              v20 = 0;
              v72 = 1;
              *(_OWORD *)&v101[16 * v50] = v103;
              v50 = *(_DWORD *)&v101[16] + 1;
              v102 = 0;
              *(_DWORD *)&v101[16] = v50;
              if ( v50 > 1 )
              {
                v73 = &v101[16];
                do
                {
                  v73 += 16;
                  if ( *((_WORD *)v73 - 8) < *(_WORD *)&v101[16 * v20] )
                    v20 = v72;
                  ++v72;
                  v102 = v20;
                }
                while ( v72 < v50 );
              }
            }
            ++v64;
            ++v67;
          }
          while ( v64 < 96 );
        }
        else
        {
          v53 = 0;
          v54 = v14;
          do
          {
            v55 = 26 * *v54;
            v56 = *(unsigned __int16 *)((char *)v54 + v13 - (_QWORD)v14) >> 1;
            v57 = (26 * (unsigned int)*(unsigned __int16 *)((char *)v54 + v12 - (_QWORD)v14)) >> 8;
            DWORD1(v103) = v53;
            v58 = v56 + (v55 >> 8) + v57;
            LOWORD(v103) = v58;
            if ( v18 >= 4 )
            {
              v61 = 2LL * v17;
              if ( v58 > *(_WORD *)&v109[16 * v17 - 16] )
              {
                v17 = 0;
                v62 = 1;
                *(_OWORD *)&v109[8 * v61 - 16] = v103;
                v18 = v110;
                v111 = 0;
                if ( v110 > 1 )
                {
                  v63 = v109;
                  do
                  {
                    v63 += 16;
                    if ( *((_WORD *)v63 - 8) < *(_WORD *)&v109[16 * v17 - 16] )
                      v17 = v62;
                    ++v62;
                    v111 = v17;
                  }
                  while ( v62 < v110 );
                }
              }
            }
            else
            {
              v17 = 0;
              v59 = 1;
              *(_OWORD *)&v109[16 * v18 - 16] = v103;
              v18 = v110 + 1;
              v111 = 0;
              v110 = v18;
              if ( v18 > 1 )
              {
                v60 = v109;
                do
                {
                  v60 += 16;
                  if ( *((_WORD *)v60 - 8) < *(_WORD *)&v109[16 * v17 - 16] )
                    v17 = v59;
                  ++v59;
                  v111 = v17;
                }
                while ( v59 < v18 );
              }
            }
            ++v53;
            ++v54;
          }
          while ( v53 < 96 );
        }
        v14 += 96;
        v12 = v96 + 192;
        v13 = v95 + 192;
        v49 = v91 + 1;
        v95 += 192;
        v96 += 192;
        v91 = v49;
      }
      while ( v49 <= v92 );
      v9 = v106;
      v77 = v89;
      if ( v106 >= 5 )
      {
        if ( *(_WORD *)v101 > *(_WORD *)&v105[16 * v89 - 16] )
        {
          v77 = 0;
          *(_OWORD *)&v105[16 * v89 - 16] = *(_OWORD *)v101;
          v9 = v106;
          v80 = 1;
          v107 = 0;
          if ( v106 > 1 )
          {
            v81 = v105;
            do
            {
              v81 += 16;
              if ( *((_WORD *)v81 - 8) < *(_WORD *)&v105[16 * v77 - 16] )
                v77 = v80;
              ++v80;
              v107 = v77;
            }
            while ( v80 < v106 );
          }
        }
      }
      else
      {
        v78 = 1;
        v77 = 0;
        *(_OWORD *)&v105[16 * v106 - 16] = *(_OWORD *)v101;
        v9 = v106 + 1;
        v107 = 0;
        v106 = v9;
        if ( v9 > 1 )
        {
          v79 = v105;
          do
          {
            v79 += 16;
            if ( *((_WORD *)v79 - 8) < *(_WORD *)&v105[16 * v77 - 16] )
              v77 = v78;
            ++v78;
            v107 = v77;
          }
          while ( v78 < v9 );
        }
      }
      v82 = (int *)&v108;
      do
      {
        if ( v9 >= 5 )
        {
          v85 = 2LL * v77;
          if ( *(_WORD *)v82 > *(_WORD *)&v105[16 * v77 - 16] )
          {
            v77 = 0;
            *(_OWORD *)&v105[8 * v85 - 16] = *(_OWORD *)v82;
            v9 = v106;
            v86 = 1;
            v107 = 0;
            if ( v106 > 1 )
            {
              v87 = v105;
              do
              {
                v87 += 16;
                if ( *((_WORD *)v87 - 8) < *(_WORD *)&v105[16 * v77 - 16] )
                  v77 = v86;
                ++v86;
                v107 = v77;
              }
              while ( v86 < v106 );
            }
          }
        }
        else
        {
          v83 = 1;
          v77 = 0;
          *(_OWORD *)&v105[16 * v9 - 16] = *(_OWORD *)v82;
          v9 = v106 + 1;
          v107 = 0;
          v106 = v9;
          if ( v9 > 1 )
          {
            v84 = v105;
            do
            {
              v84 += 16;
              if ( *((_WORD *)v84 - 8) < *(_WORD *)&v105[16 * v77 - 16] )
                v77 = v83;
              ++v83;
              v107 = v77;
            }
            while ( v83 < v9 );
          }
        }
        v82 += 4;
      }
      while ( v82 != &v110 );
      LODWORD(v8) = v93 + 1;
      v11 = v97 + 28;
      v2 = a2;
      v12 = v98 + 17472;
      v10 = v94;
      v89 = v77;
      v93 = v8;
      v97 += 28;
      v98 += 17472;
    }
    while ( (int)v8 < a2[1907] );
    v3 = a1;
  }
  result = Input::ConstructWidth<Input::VirtualRelation<91,96,28,1>,4,1>::StoreCommonDefinition(
             v3,
             &v104,
             (unsigned int)v9,
             v2);
  if ( (unsigned __int64)(int)result > 0x7FFFFFFF )
    result = 0;
  v2[1908] = result;
  return result;
}

```

## disassembly

```asm
0x1800376e0  push    rbp
0x1800376e2  push    rbx
0x1800376e3  push    rsi
0x1800376e4  push    rdi
0x1800376e5  push    r12
0x1800376e7  push    r15
0x1800376e9  lea     rbp, [rsp-78h]
0x1800376ee  sub     rsp, 178h
0x1800376f5  mov     rax, cs:__security_cookie
0x1800376fc  xor     rax, rsp
0x1800376ff  mov     [rbp+0A0h+var_40], rax
0x180037703  mov     rax, cs:?NewAPI@IntegratedSelection@Input@@1PEAV12@EA; Input::IntegratedSelection * Input::IntegratedSelection::NewAPI
0x18003770a  mov     rbx, rdx
0x18003770d  mov     [rsp+1A0h+var_130], rdx
0x180037712  mov     rdi, rcx
0x180037715  mov     [rsp+1A0h+var_128], rcx
0x18003771a  cmp     dword ptr [rax], 2
0x18003771d  jnz     short loc_18003772B
0x18003771f  mov     r9d, 1
0x180037725  lea     edx, [r9+58h]
0x180037729  jmp     short loc_180037736
0x18003772b  mov     r9d, 13h
0x180037731  mov     edx, 41h ; 'A'
0x180037736  mov     [rsp+1A0h+var_174], edx
0x18003773a  lea     rax, [rbp+0A0h+var_F0+8]
0x18003773e  mov     [rsp+1A0h+var_17C], r9d
0x180037743  mov     ecx, 5
0x180037748  xor     r15d, r15d
0x18003774b  nop     dword ptr [rax+rax+00h]
0x180037750  mov     [rax-8], r15w
0x180037755  mov     [rax-4], r15
0x180037759  mov     [rax+4], r15d
0x18003775d  lea     rax, [rax+10h]
0x180037761  sub     rcx, 1
0x180037765  jnz     short loc_180037750
0x180037767  movsxd  r8, dword ptr [rbx+1DC8h]
0x18003776e  mov     esi, 0FFFFFFFFh
0x180037773  mov     r12d, r15d
0x180037776  mov     [rbp+0A0h+var_A0], r15d
0x18003777a  mov     [rsp+1A0h+var_180], esi
0x18003777e  mov     [rbp+0A0h+var_9C], esi
0x180037781  mov     word ptr [rbp+0A0h+var_108], r15w
0x180037786  mov     [rsp+1A0h+var_170], r8d
0x18003778b  cmp     r8d, [rbx+1DCCh]
0x180037792  jge     loc_180037E62
0x180037798  lea     r11d, [rdx+1]
0x18003779c  mov     eax, r9d
0x18003779f  imul    r10, r8, 38h ; '8'
0x1800377a3  lea     rcx, word_1800CAA82
0x1800377aa  mov     [rsp+1A0h+arg_10], r13
0x1800377b2  add     r10, rcx
0x1800377b5  mov     [rsp+1A0h+var_30], r14
0x1800377bd  imul    rcx, r8, 5Bh ; '['
0x1800377c1  mov     [rsp+1A0h+var_160], r11d
0x1800377c6  inc     rcx
0x1800377c9  mov     [rsp+1A0h+var_148], r10
0x1800377ce  add     rcx, rax
0x1800377d1  lea     rdx, [rcx+rcx*2]
0x1800377d5  shl     rdx, 6
0x1800377d9  add     rdx, [rdi]
0x1800377dc  mov     [rsp+1A0h+var_140], rdx
0x1800377e1  nop     dword ptr [rax+00h]
0x1800377e5  nop     word ptr [rax+rax+00000000h]
0x1800377f0  lea     rcx, [rdx-0C0h]
0x1800377f7  mov     dword ptr [rbp+0A0h+var_108+0Ch], r8d
0x1800377fb  mov     [rsp+1A0h+var_158], rcx
0x180037800  lea     rax, [rdx-180h]
0x180037807  mov     [rsp+1A0h+var_150], rdx
0x18003780c  lea     r8, [rbp+0A0h+var_90+8]
0x180037810  mov     r9d, 4
0x180037816  nop     word ptr [rax+rax+00000000h]
0x180037820  mov     [r8-8], r15w
0x180037825  mov     qword ptr [r8-4], 0
0x18003782d  mov     [r8+4], r15d
0x180037831  lea     r8, [r8+10h]
0x180037835  sub     r9, 1
0x180037839  jnz     short loc_180037820
0x18003783b  mov     ebx, 0FFFFFFFFh
0x180037840  mov     [rbp+0A0h+var_50], r15d
0x180037844  xorps   xmm0, xmm0
0x180037847  mov     word ptr [rbp+0A0h+var_120], r15w
0x18003784c  mov     r14d, r15d
0x18003784f  mov     [rbp+0A0h+var_4C], ebx
0x180037852  movdqu  [rbp+0A0h+var_120+4], xmm0
0x180037857  lea     r13d, [rbx+3]
0x18003785b  mov     [rbp+0A0h+var_10C], ebx
0x18003785e  mov     edi, ebx
0x180037860  mov     r9d, ebx
0x180037863  mov     r15, r10
0x180037866  nop     word ptr [rax+rax+00000000h]
0x180037870  movzx   r10d, byte ptr [r15-2]
0x180037875  cmp     r11d, r10d
0x180037878  mov     r8d, r10d
0x18003787b  cmovle  r8d, r11d
0x18003787f  cmp     r9d, r10d
0x180037882  movzx   r11d, byte ptr [r15-1]
0x180037887  cmovge  r10d, r9d
0x18003788b  cmp     r8d, r11d
0x18003788e  mov     r9d, r11d
0x180037891  cmovle  r9d, r8d
0x180037895  cmp     r10d, r11d
0x180037898  cmovge  r11d, r10d
0x18003789c  movzx   r10d, byte ptr [r15]
0x1800378a0  cmp     r9d, r10d
0x1800378a3  mov     r8d, r10d
0x1800378a6  cmovle  r8d, r9d
0x1800378aa  cmp     r11d, r10d
0x1800378ad  cmovge  r10d, r11d
0x1800378b1  movzx   r11d, byte ptr [r15+1]
0x1800378b6  cmp     r8d, r11d
0x1800378b9  mov     r9d, r11d
0x1800378bc  cmovle  r9d, r8d
0x1800378c0  cmp     r10d, r11d
0x1800378c3  cmovge  r11d, r10d
0x1800378c7  movzx   r10d, byte ptr [r15+2]
0x1800378cc  cmp     r9d, r10d
0x1800378cf  mov     r8d, r10d
0x1800378d2  cmovle  r8d, r9d
0x1800378d6  cmp     r11d, r10d
0x1800378d9  cmovge  r10d, r11d
0x1800378dd  movzx   r11d, byte ptr [r15+3]
0x1800378e2  cmp     r8d, r11d
0x1800378e5  mov     r9d, r11d
0x1800378e8  cmovle  r9d, r8d
0x1800378ec  cmp     r10d, r11d
0x1800378ef  cmovge  r11d, r10d
0x1800378f3  movzx   r10d, byte ptr [r15+4]
0x1800378f8  cmp     r9d, r10d
0x1800378fb  mov     r8d, r10d
0x1800378fe  cmovle  r8d, r9d
0x180037902  cmp     r11d, r10d
0x180037905  cmovge  r10d, r11d
0x180037909  movzx   r11d, byte ptr [r15+5]
0x18003790e  cmp     r8d, r11d
0x180037911  mov     r9d, r11d
0x180037914  cmovle  r9d, r8d
0x180037918  cmp     r10d, r11d
0x18003791b  cmovge  r11d, r10d
0x18003791f  movzx   r10d, byte ptr [r15+6]
0x180037924  cmp     r9d, r10d
0x180037927  mov     r8d, r10d
0x18003792a  cmovle  r8d, r9d
0x18003792e  cmp     r11d, r10d
0x180037931  cmovge  r10d, r11d
0x180037935  movzx   r11d, byte ptr [r15+7]
0x18003793a  cmp     r8d, r11d
0x18003793d  mov     r9d, r11d
0x180037940  cmovle  r9d, r8d
0x180037944  cmp     r10d, r11d
0x180037947  cmovge  r11d, r10d
0x18003794b  movzx   r10d, byte ptr [r15+8]
0x180037950  cmp     r9d, r10d
0x180037953  mov     r8d, r10d
0x180037956  cmovle  r8d, r9d
0x18003795a  cmp     r11d, r10d
0x18003795d  cmovge  r10d, r11d
0x180037961  movzx   r11d, byte ptr [r15+9]
0x180037966  cmp     r8d, r11d
0x180037969  mov     r9d, r11d
0x18003796c  cmovle  r9d, r8d
0x180037970  cmp     r10d, r11d
0x180037973  cmovge  r11d, r10d
0x180037977  movzx   r10d, byte ptr [r15+0Ah]
0x18003797c  cmp     r9d, r10d
0x18003797f  mov     r8d, r10d
0x180037982  cmovle  r8d, r9d
0x180037986  movzx   r9d, byte ptr [r15+0Bh]
0x18003798b  cmp     r11d, r10d
0x18003798e  cmovge  r10d, r11d
0x180037992  mov     r11d, r9d
0x180037995  cmp     r8d, r9d
0x180037998  cmovle  r11d, r8d
0x18003799c  lea     r15, [r15+0Eh]
0x1800379a0  cmp     r10d, r9d
0x1800379a3  cmovge  r9d, r10d
0x1800379a7  sub     r13, 1
0x1800379ab  jnz     loc_180037870
0x1800379b1  mov     r8d, [rsp+1A0h+var_17C]
0x1800379b6  mov     r12d, 2Dh ; '-'
0x1800379bc  mov     r10d, [rbp+0A0h+var_110]
0x1800379c0  sub     r12d, r11d
0x1800379c3  mov     esi, 88h
0x1800379c8  mov     [rsp+1A0h+var_178], r8d
0x1800379cd  sub     esi, r9d
0x1800379d0  mov     dword ptr [rbp+0A0h+var_108+8], r8d
0x1800379d4  cmp     r8d, r12d
0x1800379d7  jl      loc_180037B0A
0x1800379dd  cmp     r8d, esi
0x1800379e0  jg      loc_180037B0A
0x1800379e6  mov     r8, rdx
0x1800379e9  xor     r13d, r13d
0x1800379ec  sub     r8, rax
0x1800379ef  mov     rdx, rcx
0x1800379f2  mov     [rsp+1A0h+var_138], r8
0x1800379f7  sub     rdx, rax
0x1800379fa  mov     rcx, r8
0x1800379fd  mov     r15, rax
0x180037a00  movzx   r8d, word ptr [rcx+r15]
0x180037a05  imul    r11d, r8d, 1Ah
0x180037a09  movzx   r8d, word ptr [r15]
0x180037a0d  imul    r9d, r8d, 1Ah
0x180037a11  movzx   r8d, word ptr [rdx+r15]
0x180037a16  shr     r8w, 1
0x180037a1a  shr     r11d, 8
0x180037a1e  mov     dword ptr [rbp+0A0h+var_108+4], r13d
0x180037a22  shr     r9d, 8
0x180037a26  add     r11w, r9w
0x180037a2a  add     r11w, r8w
0x180037a2e  mov     word ptr [rbp+0A0h+var_108], r11w
0x180037a33  cmp     r14d, 4
0x180037a37  jge     short loc_180037A96
0x180037a39  movups  xmm0, [rbp+0A0h+var_108]
0x180037a3d  movsxd  r8, r14d
0x180037a40  xor     ebx, ebx
0x180037a42  add     r8, r8
0x180037a45  mov     r9d, 1
0x180037a4b  movups  xmmword ptr [rbp+r8*8+10h], xmm0
0x180037a51  mov     r14d, [rbp+0A0h+var_50]
0x180037a55  inc     r14d
0x180037a58  mov     [rbp+0A0h+var_4C], ebx
0x180037a5b  mov     [rbp+0A0h+var_50], r14d
0x180037a5f  cmp     r14d, r9d
0x180037a62  jle     loc_180037AF4
0x180037a68  lea     r11, [rbp+0A0h+var_80]
0x180037a6c  nop     dword ptr [rax+00h]
0x180037a70  movsxd  r8, ebx
0x180037a73  lea     r11, [r11+10h]
0x180037a77  add     r8, r8
0x180037a7a  movzx   r8d, word ptr [rbp+r8*8+0A0h+var_90]
0x180037a80  cmp     [r11-10h], r8w
0x180037a85  cmovb   ebx, r9d
0x180037a89  inc     r9d
0x180037a8c  mov     [rbp+0A0h+var_4C], ebx
0x180037a8f  cmp     r9d, r14d
0x180037a92  jl      short loc_180037A70
0x180037a94  jmp     short loc_180037AF4
0x180037a96  movsxd  r8, ebx
0x180037a99  add     r8, r8
0x180037a9c  cmp     r11w, word ptr [rbp+r8*8+0A0h+var_90]
0x180037aa2  jbe     short loc_180037AF4
0x180037aa4  movups  xmm0, [rbp+0A0h+var_108]
0x180037aa8  xor     ebx, ebx
0x180037aaa  mov     r9d, 1
0x180037ab0  movups  [rbp+r8*8+0A0h+var_90], xmm0
0x180037ab6  mov     r14d, [rbp+0A0h+var_50]
0x180037aba  mov     [rbp+0A0h+var_4C], ebx
0x180037abd  cmp     r14d, r9d
0x180037ac0  jle     short loc_180037AF4
0x180037ac2  lea     r11, [rbp+0A0h+var_80]
0x180037ac6  nop     word ptr [rax+rax+00000000h]
0x180037ad0  movsxd  r8, ebx
0x180037ad3  lea     r11, [r11+10h]
0x180037ad7  add     r8, r8
0x180037ada  movzx   r8d, word ptr [rbp+r8*8+0A0h+var_90]
0x180037ae0  cmp     [r11-10h], r8w
0x180037ae5  cmovb   ebx, r9d
0x180037ae9  inc     r9d
0x180037aec  mov     [rbp+0A0h+var_4C], ebx
0x180037aef  cmp     r9d, r14d
0x180037af2  jl      short loc_180037AD0
0x180037af4  inc     r13d
0x180037af7  add     r15, 2
0x180037afb  cmp     r13d, 60h ; '`'
0x180037aff  jl      loc_180037A00
0x180037b05  jmp     loc_180037C25
0x180037b0a  xor     r13d, r13d
0x180037b0d  sub     rdx, rax
0x180037b10  sub     rcx, rax
0x180037b13  mov     r15, rax
0x180037b16  nop     word ptr [rax+rax+00000000h]
0x180037b20  movzx   r8d, word ptr [r15+rdx]
0x180037b25  imul    r11d, r8d, 1Ah
0x180037b29  movzx   r8d, word ptr [r15]
0x180037b2d  imul    r9d, r8d, 1Ah
0x180037b31  movzx   r8d, word ptr [r15+rcx]
0x180037b36  shr     r8w, 1
0x180037b3a  shr     r11d, 8
0x180037b3e  mov     dword ptr [rbp+0A0h+var_108+4], r13d
0x180037b42  shr     r9d, 8
0x180037b46  add     r11w, r9w
0x180037b4a  add     r11w, r8w
0x180037b4e  mov     word ptr [rbp+0A0h+var_108], r11w
0x180037b53  cmp     r10d, 1
0x180037b57  jge     short loc_180037BB6
0x180037b59  movups  xmm0, [rbp+0A0h+var_108]
0x180037b5d  movsxd  r8, r10d
0x180037b60  xor     edi, edi
0x180037b62  add     r8, r8
0x180037b65  mov     r9d, 1
0x180037b6b  movups  [rbp+r8*8+0A0h+var_120], xmm0
0x180037b71  mov     r10d, [rbp+0A0h+var_110]
0x180037b75  inc     r10d
0x180037b78  mov     [rbp+0A0h+var_10C], edi
0x180037b7b  mov     [rbp+0A0h+var_110], r10d
0x180037b7f  cmp     r10d, r9d
0x180037b82  jle     loc_180037C14
0x180037b88  lea     r11, [rbp+0A0h+var_110]
0x180037b8c  nop     dword ptr [rax+00h]
0x180037b90  movsxd  r8, edi
0x180037b93  lea     r11, [r11+10h]
  ... truncated ...
```
