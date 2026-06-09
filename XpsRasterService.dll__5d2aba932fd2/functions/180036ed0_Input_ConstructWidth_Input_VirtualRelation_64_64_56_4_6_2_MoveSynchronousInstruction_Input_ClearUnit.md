# Input::ConstructWidth<Input::VirtualRelation<64,64,56,4>,6,2>::MoveSynchronousInstruction(Input::ClearUnit &)

- ea: `0x180036ed0`
- end: `0x1800376da`
- name: `?MoveSynchronousInstruction@?$ConstructWidth@V?$VirtualRelation@$0EA@$0EA@$0DI@$03@Input@@$05$01@Input@@QEAAXAEAVClearUnit@2@@Z`
- size: `2058`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x180036e70`

## callees

- `0x180003180`
- `0x180036ed0`
- `0x18003ab80`

## pseudocode

```c
__int64 __fastcall Input::ConstructWidth<Input::VirtualRelation<64,64,56,4>,6,2>::MoveSynchronousInstruction(
        _QWORD *a1,
        int *a2)
{
  int *v2; // rbx
  _QWORD *v3; // rdi
  unsigned int v4; // r9d
  int v5; // edx
  char *v6; // rax
  __int64 v7; // rcx
  int v8; // r14d
  __int64 v9; // r8
  int v10; // r12d
  int v11; // r11d
  __int16 *v12; // r10
  __int64 v13; // rdx
  unsigned __int16 *v14; // rax
  char *v15; // r8
  __int64 v16; // r9
  int v17; // edi
  int v18; // r15d
  char *v19; // r8
  __int64 v20; // r9
  int v21; // ebx
  int v22; // r9d
  unsigned __int8 *v23; // r13
  __int64 v24; // rcx
  int v25; // r10d
  int v26; // r8d
  int v27; // r11d
  int v28; // r9d
  int v29; // r10d
  int v30; // r8d
  int v31; // r11d
  int v32; // r9d
  int v33; // r10d
  int v34; // r8d
  int v35; // r11d
  int v36; // r9d
  int v37; // r10d
  int v38; // r8d
  int v39; // r11d
  int v40; // r9d
  int v41; // r10d
  int v42; // r8d
  int v43; // r11d
  int v44; // r9d
  int v45; // r10d
  int v46; // r8d
  int v47; // r11d
  int v48; // r9d
  int v49; // r10d
  int v50; // r8d
  signed int v51; // r8d
  __int64 v52; // rcx
  int v53; // r12d
  int v54; // esi
  int v55; // r13d
  __int64 v56; // rdx
  unsigned __int16 *v57; // r11
  int v58; // r9d
  _BYTE *v59; // r10
  __int64 v60; // r8
  int v61; // r9d
  _BYTE *v62; // r10
  int v63; // r13d
  __int64 v64; // rdx
  __int64 v65; // rcx
  unsigned __int16 *v66; // r11
  int v67; // r9d
  _BYTE *v68; // r10
  __int64 v69; // r8
  int v70; // r9d
  _BYTE *v71; // r10
  int v72; // esi
  int *v73; // rax
  int v74; // edx
  _BYTE *v75; // r8
  __int64 v76; // rdx
  int v77; // edx
  _BYTE *v78; // r8
  int *v79; // rax
  int v80; // edx
  _BYTE *v81; // r8
  __int64 v82; // rdx
  int v83; // edx
  _BYTE *v84; // r8
  __int64 result; // rax
  int v86; // [rsp+20h] [rbp-E0h]
  unsigned int v87; // [rsp+24h] [rbp-DCh]
  unsigned int v88; // [rsp+28h] [rbp-D8h]
  int v89; // [rsp+2Ch] [rbp-D4h]
  int v90; // [rsp+30h] [rbp-D0h]
  __int64 v91; // [rsp+40h] [rbp-C0h]
  int v92; // [rsp+48h] [rbp-B8h]
  __int64 v93; // [rsp+50h] [rbp-B0h]
  __int16 *v94; // [rsp+58h] [rbp-A8h]
  __int64 v95; // [rsp+60h] [rbp-A0h]
  __int64 v96; // [rsp+68h] [rbp-98h]
  __int128 v99; // [rsp+80h] [rbp-80h]
  __int128 v100; // [rsp+90h] [rbp-70h] BYREF
  _BYTE v101[16]; // [rsp+A0h] [rbp-60h] BYREF
  int v102; // [rsp+B0h] [rbp-50h] BYREF
  int v103; // [rsp+B4h] [rbp-4Ch]
  __int128 v104; // [rsp+C0h] [rbp-40h] BYREF
  _BYTE v105[112]; // [rsp+D0h] [rbp-30h] BYREF
  int v106; // [rsp+140h] [rbp+40h]
  int v107; // [rsp+144h] [rbp+44h]
  __int128 v108; // [rsp+150h] [rbp+50h] BYREF
  _BYTE v109[80]; // [rsp+160h] [rbp+60h] BYREF
  int v110; // [rsp+1B0h] [rbp+B0h] BYREF
  int v111; // [rsp+1B4h] [rbp+B4h]

  v2 = a2;
  v3 = a1;
  if ( *(_DWORD *)Input::IntegratedSelection::NewAPI == 2 )
  {
    v4 = 1;
    v5 = 62;
  }
  else
  {
    v4 = 13;
    v5 = 45;
  }
  v89 = v5;
  v6 = (char *)&v104 + 8;
  v87 = v4;
  v7 = 8;
  v8 = 0;
  do
  {
    *((_WORD *)v6 - 4) = 0;
    *(_QWORD *)(v6 - 4) = 0;
    *((_DWORD *)v6 + 1) = 0;
    v6 += 16;
    --v7;
  }
  while ( v7 );
  v9 = v2[1906];
  v10 = 0;
  v106 = 0;
  v86 = -1;
  v107 = -1;
  v90 = v9;
  if ( (int)v9 < v2[1907] )
  {
    v11 = v5 + 1;
    v92 = v5 + 1;
    v12 = &word_1800CA702[56 * v9];
    v13 = *v3 + (((v9 << 6) + 1 + v4) << 7);
    v95 = v13;
    v94 = v12;
    do
    {
      HIDWORD(v99) = v9;
      v91 = v13 - 128;
      v14 = (unsigned __int16 *)(v13 - 256);
      v93 = v13;
      v15 = (char *)&v108 + 8;
      v16 = 6;
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
      v18 = 0;
      v111 = -1;
      v19 = (char *)&v100 + 8;
      v20 = 2;
      do
      {
        *((_WORD *)v19 - 4) = 0;
        *(_QWORD *)(v19 - 4) = 0;
        *((_DWORD *)v19 + 1) = 0;
        v19 += 16;
        --v20;
      }
      while ( v20 );
      v21 = -1;
      v102 = 0;
      v103 = -1;
      v22 = -1;
      v23 = (unsigned __int8 *)v12;
      v24 = 4;
      do
      {
        v25 = *(v23 - 2);
        v26 = v25;
        if ( v11 <= v25 )
          v26 = v11;
        v27 = *(v23 - 1);
        if ( v22 >= v25 )
          v25 = v22;
        v28 = *(v23 - 1);
        if ( v26 <= v27 )
          v28 = v26;
        if ( v25 >= v27 )
          v27 = v25;
        v29 = *v23;
        v30 = v29;
        if ( v28 <= v29 )
          v30 = v28;
        if ( v27 >= v29 )
          v29 = v27;
        v31 = v23[1];
        v32 = v31;
        if ( v30 <= v31 )
          v32 = v30;
        if ( v29 >= v31 )
          v31 = v29;
        v33 = v23[2];
        v34 = v33;
        if ( v32 <= v33 )
          v34 = v32;
        if ( v31 >= v33 )
          v33 = v31;
        v35 = v23[3];
        v36 = v35;
        if ( v34 <= v35 )
          v36 = v34;
        if ( v33 >= v35 )
          v35 = v33;
        v37 = v23[4];
        v38 = v37;
        if ( v36 <= v37 )
          v38 = v36;
        if ( v35 >= v37 )
          v37 = v35;
        v39 = v23[5];
        v40 = v39;
        if ( v38 <= v39 )
          v40 = v38;
        if ( v37 >= v39 )
          v39 = v37;
        v41 = v23[6];
        v42 = v41;
        if ( v40 <= v41 )
          v42 = v40;
        if ( v39 >= v41 )
          v41 = v39;
        v43 = v23[7];
        v44 = v43;
        if ( v42 <= v43 )
          v44 = v42;
        if ( v41 >= v43 )
          v43 = v41;
        v45 = v23[8];
        v46 = v45;
        if ( v44 <= v45 )
          v46 = v44;
        if ( v43 >= v45 )
          v45 = v43;
        v47 = v23[9];
        v48 = v47;
        if ( v46 <= v47 )
          v48 = v46;
        if ( v45 >= v47 )
          v47 = v45;
        v49 = v23[10];
        v50 = v49;
        if ( v48 <= v49 )
          v50 = v48;
        v22 = v23[11];
        if ( v47 >= v49 )
          v49 = v47;
        v11 = v23[11];
        if ( v50 <= v22 )
          v11 = v50;
        v23 += 14;
        if ( v49 >= v22 )
          v22 = v49;
        --v24;
      }
      while ( v24 );
      v51 = v87;
      v52 = v13 - 128;
      v53 = 32 - v11;
      v88 = v87;
      v54 = 96 - v22;
      do
      {
        DWORD2(v99) = v51;
        if ( v51 < v53 || v51 > v54 )
        {
          v63 = 0;
          v64 = v13 - (_QWORD)v14;
          v65 = v52 - (_QWORD)v14;
          v66 = v14;
          do
          {
            DWORD1(v99) = v63;
            LOWORD(v99) = (*(unsigned __int16 *)((char *)v66 + v65) >> 1)
                        + ((26 * (unsigned int)*v66) >> 8)
                        + ((26 * (unsigned int)*(unsigned __int16 *)((char *)v66 + v64)) >> 8);
            if ( v8 >= 2 )
            {
              v69 = 2LL * v21;
              if ( (unsigned __int16)((*(unsigned __int16 *)((char *)v66 + v65) >> 1)
                                    + ((26 * (unsigned int)*v66) >> 8)
                                    + ((26 * (unsigned int)*(unsigned __int16 *)((char *)v66 + v64)) >> 8)) > *(_WORD *)&v101[16 * v21 - 16] )
              {
                v21 = 0;
                v70 = 1;
                *(_OWORD *)&v101[8 * v69 - 16] = v99;
                v8 = v102;
                v103 = 0;
                if ( v102 > 1 )
                {
                  v71 = v101;
                  do
                  {
                    v71 += 16;
                    if ( *((_WORD *)v71 - 8) < *(_WORD *)&v101[16 * v21 - 16] )
                      v21 = v70;
                    ++v70;
                    v103 = v21;
                  }
                  while ( v70 < v102 );
                }
              }
            }
            else
            {
              v21 = 0;
              v67 = 1;
              *(_OWORD *)&v101[16 * v8 - 16] = v99;
              v8 = v102 + 1;
              v103 = 0;
              v102 = v8;
              if ( v8 > 1 )
              {
                v68 = v101;
                do
                {
                  v68 += 16;
                  if ( *((_WORD *)v68 - 8) < *(_WORD *)&v101[16 * v21 - 16] )
                    v21 = v67;
                  ++v67;
                  v103 = v21;
                }
                while ( v67 < v8 );
              }
            }
            ++v63;
            ++v66;
          }
          while ( v63 < 64 );
        }
        else
        {
          v55 = 0;
          v96 = v13 - (_QWORD)v14;
          v56 = v52 - (_QWORD)v14;
          v57 = v14;
          do
          {
            DWORD1(v99) = v55;
            LOWORD(v99) = (*(unsigned __int16 *)((char *)v57 + v56) >> 1)
                        + ((26 * (unsigned int)*v57) >> 8)
                        + ((26 * (unsigned int)*(unsigned __int16 *)((char *)v57 + v96)) >> 8);
            if ( v18 >= 6 )
            {
              v60 = 2LL * v17;
              if ( (unsigned __int16)((*(unsigned __int16 *)((char *)v57 + v56) >> 1)
                                    + ((26 * (unsigned int)*v57) >> 8)
                                    + ((26 * (unsigned int)*(unsigned __int16 *)((char *)v57 + v96)) >> 8)) > *(_WORD *)&v109[16 * v17 - 16] )
              {
                v17 = 0;
                v61 = 1;
                *(_OWORD *)&v109[8 * v60 - 16] = v99;
                v18 = v110;
                v111 = 0;
                if ( v110 > 1 )
                {
                  v62 = v109;
                  do
                  {
                    v62 += 16;
                    if ( *((_WORD *)v62 - 8) < *(_WORD *)&v109[16 * v17 - 16] )
                      v17 = v61;
                    ++v61;
                    v111 = v17;
                  }
                  while ( v61 < v110 );
                }
              }
            }
            else
            {
              v17 = 0;
              v58 = 1;
              *(_OWORD *)&v109[16 * v18 - 16] = v99;
              v18 = v110 + 1;
              v111 = 0;
              v110 = v18;
              if ( v18 > 1 )
              {
                v59 = v109;
                do
                {
                  v59 += 16;
                  if ( *((_WORD *)v59 - 8) < *(_WORD *)&v109[16 * v17 - 16] )
                    v17 = v58;
                  ++v58;
                  v111 = v17;
                }
                while ( v58 < v18 );
              }
            }
            ++v55;
            ++v57;
          }
          while ( v55 < 64 );
        }
        v14 += 64;
        v13 = v93 + 128;
        v52 = v91 + 128;
        v51 = v88 + 1;
        v91 += 128;
        v93 += 128;
        v88 = v51;
      }
      while ( v51 <= v89 );
      v72 = v86;
      v73 = (int *)&v100;
      v10 = v106;
      do
      {
        v8 = 0;
        if ( v10 >= 8 )
        {
          v76 = 2LL * v72;
          if ( *(_WORD *)v73 > *(_WORD *)&v105[16 * v72 - 16] )
          {
            v72 = 0;
            *(_OWORD *)&v105[8 * v76 - 16] = *(_OWORD *)v73;
            v10 = v106;
            v77 = 1;
            v107 = 0;
            if ( v106 > 1 )
            {
              v78 = v105;
              do
              {
                v78 += 16;
                if ( *((_WORD *)v78 - 8) < *(_WORD *)&v105[16 * v72 - 16] )
                  v72 = v77;
                ++v77;
                v107 = v72;
              }
              while ( v77 < v106 );
            }
          }
        }
        else
        {
          v74 = 1;
          v72 = 0;
          *(_OWORD *)&v105[16 * v10 - 16] = *(_OWORD *)v73;
          v10 = v106 + 1;
          v107 = 0;
          v106 = v10;
          if ( v10 > 1 )
          {
            v75 = v105;
            do
            {
              v75 += 16;
              if ( *((_WORD *)v75 - 8) < *(_WORD *)&v105[16 * v72 - 16] )
                v72 = v74;
              ++v74;
              v107 = v72;
            }
            while ( v74 < v10 );
          }
        }
        v73 += 4;
      }
      while ( v73 != &v102 );
      v79 = (int *)&v108;
      do
      {
        if ( v10 >= 8 )
        {
          v82 = 2LL * v72;
          if ( *(_WORD *)v79 > *(_WORD *)&v105[16 * v72 - 16] )
          {
            v72 = 0;
            *(_OWORD *)&v105[8 * v82 - 16] = *(_OWORD *)v79;
            v10 = v106;
            v83 = 1;
            v107 = 0;
            if ( v106 > 1 )
            {
              v84 = v105;
              do
              {
                v84 += 16;
                if ( *((_WORD *)v84 - 8) < *(_WORD *)&v105[16 * v72 - 16] )
                  v72 = v83;
                ++v83;
                v107 = v72;
              }
              while ( v83 < v106 );
            }
          }
        }
        else
        {
          v80 = 1;
          v72 = 0;
          *(_OWORD *)&v105[16 * v10 - 16] = *(_OWORD *)v79;
          v10 = v106 + 1;
          v107 = 0;
          v106 = v10;
          if ( v10 > 1 )
          {
            v81 = v105;
            do
            {
              v81 += 16;
              if ( *((_WORD *)v81 - 8) < *(_WORD *)&v105[16 * v72 - 16] )
                v72 = v80;
              ++v80;
              v107 = v72;
            }
            while ( v80 < v10 );
          }
        }
        v79 += 4;
      }
      while ( v79 != &v110 );
      LODWORD(v9) = v90 + 1;
      v12 = v94 + 56;
      v2 = a2;
      v13 = v95 + 0x2000;
      v11 = v92;
      v86 = v72;
      v90 = v9;
      v94 += 56;
      v95 += 0x2000;
    }
    while ( (int)v9 < a2[1907] );
    v3 = a1;
  }
  result = Input::ConstructWidth<Input::VirtualRelation<64,64,56,4>,6,2>::StoreCommonDefinition(
             v3,
             &v104,
             (unsigned int)v10,
             v2);
  if ( (unsigned __int64)(int)result > 0x7FFFFFFF )
    result = 0;
  v2[1908] = result;
  return result;
}

```

## disassembly

```asm
0x180036ed0  push    rbp
0x180036ed2  push    rbx
0x180036ed3  push    rsi
0x180036ed4  push    rdi
0x180036ed5  push    r12
0x180036ed7  push    r14
0x180036ed9  lea     rbp, [rsp-0D8h]
0x180036ee1  sub     rsp, 1D8h
0x180036ee8  mov     rax, cs:__security_cookie
0x180036eef  xor     rax, rsp
0x180036ef2  mov     [rbp+100h+var_40], rax
0x180036ef9  mov     rax, cs:?NewAPI@IntegratedSelection@Input@@1PEAV12@EA; Input::IntegratedSelection * Input::IntegratedSelection::NewAPI
0x180036f00  mov     rbx, rdx
0x180036f03  mov     [rsp+200h+var_190], rdx
0x180036f08  mov     rdi, rcx
0x180036f0b  mov     [rsp+200h+var_188], rcx
0x180036f10  cmp     dword ptr [rax], 2
0x180036f13  jnz     short loc_180036F21
0x180036f15  mov     r9d, 1
0x180036f1b  lea     edx, [r9+3Dh]
0x180036f1f  jmp     short loc_180036F2C
0x180036f21  mov     r9d, 0Dh
0x180036f27  mov     edx, 2Dh ; '-'
0x180036f2c  mov     [rsp+200h+var_1D4], edx
0x180036f30  lea     rax, [rbp+100h+var_140+8]
0x180036f34  mov     [rsp+200h+var_1DC], r9d
0x180036f39  mov     ecx, 8
0x180036f3e  xor     r14d, r14d
0x180036f41  mov     [rax-8], r14w
0x180036f46  mov     [rax-4], r14
0x180036f4a  mov     [rax+4], r14d
0x180036f4e  lea     rax, [rax+10h]
0x180036f52  sub     rcx, 1
0x180036f56  jnz     short loc_180036F41
0x180036f58  movsxd  r8, dword ptr [rbx+1DC8h]
0x180036f5f  mov     esi, 0FFFFFFFFh
0x180036f64  mov     r12d, r14d
0x180036f67  mov     [rbp+100h+var_C0], r14d
0x180036f6b  mov     [rsp+200h+var_1E0], esi
0x180036f6f  mov     [rbp+100h+var_BC], esi
0x180036f72  mov     word ptr [rbp+100h+var_180], r14w
0x180036f77  mov     [rsp+200h+var_1D0], r8d
0x180036f7c  cmp     r8d, [rbx+1DCCh]
0x180036f83  jge     loc_180037695
0x180036f89  lea     r11d, [rdx+1]
0x180036f8d  mov     [rsp+200h+arg_10], r13
0x180036f95  imul    r10, r8, 70h ; 'p'
0x180036f99  mov     rcx, r8
0x180036f9c  mov     edx, r9d
0x180036f9f  shl     rcx, 6
0x180036fa3  lea     rax, word_1800CA702
0x180036faa  inc     rcx
0x180036fad  mov     [rsp+200h+var_30], r15
0x180036fb5  add     rdx, rcx
0x180036fb8  mov     [rsp+200h+var_1B8], r11d
0x180036fbd  add     r10, rax
0x180036fc0  shl     rdx, 7
0x180036fc4  add     rdx, [rdi]
0x180036fc7  mov     [rsp+200h+var_1A0], rdx
0x180036fcc  mov     [rsp+200h+var_1A8], r10
0x180036fd1  lea     rcx, [rdx-80h]
0x180036fd5  mov     dword ptr [rbp+100h+var_180+0Ch], r8d
0x180036fd9  mov     [rsp+200h+var_1C0], rcx
0x180036fde  lea     rax, [rdx-100h]
0x180036fe5  mov     [rsp+200h+var_1B0], rdx
0x180036fea  lea     r8, [rbp+100h+var_B0+8]
0x180036fee  mov     r9d, 6
0x180036ff4  nop     dword ptr [rax+00h]
0x180036ff8  nop     dword ptr [rax+rax+00000000h]
0x180037000  mov     [r8-8], r14w
0x180037005  mov     qword ptr [r8-4], 0
0x18003700d  mov     [r8+4], r14d
0x180037011  lea     r8, [r8+10h]
0x180037015  sub     r9, 1
0x180037019  jnz     short loc_180037000
0x18003701b  mov     edi, 0FFFFFFFFh
0x180037020  mov     [rbp+100h+var_50], r14d
0x180037027  mov     r15d, r14d
0x18003702a  mov     [rbp+100h+var_4C], edi
0x180037030  lea     r8, [rbp+100h+var_170+8]
0x180037034  lea     r9d, [rdi+3]
0x180037038  nop     dword ptr [rax+rax+00000000h]
0x180037040  mov     [r8-8], r14w
0x180037045  mov     qword ptr [r8-4], 0
0x18003704d  mov     [r8+4], r14d
0x180037051  lea     r8, [r8+10h]
0x180037055  sub     r9, 1
0x180037059  jnz     short loc_180037040
0x18003705b  mov     ebx, edi
0x18003705d  mov     [rbp+100h+var_150], r14d
0x180037061  mov     [rbp+100h+var_14C], ebx
0x180037064  mov     r9d, edi
0x180037067  mov     r13, r10
0x18003706a  mov     ecx, 4
0x18003706f  nop
0x180037070  movzx   r10d, byte ptr [r13-2]
0x180037075  cmp     r11d, r10d
0x180037078  mov     r8d, r10d
0x18003707b  cmovle  r8d, r11d
0x18003707f  cmp     r9d, r10d
0x180037082  movzx   r11d, byte ptr [r13-1]
0x180037087  cmovge  r10d, r9d
0x18003708b  cmp     r8d, r11d
0x18003708e  mov     r9d, r11d
0x180037091  cmovle  r9d, r8d
0x180037095  cmp     r10d, r11d
0x180037098  cmovge  r11d, r10d
0x18003709c  movzx   r10d, byte ptr [r13+0]
0x1800370a1  cmp     r9d, r10d
0x1800370a4  mov     r8d, r10d
0x1800370a7  cmovle  r8d, r9d
0x1800370ab  cmp     r11d, r10d
0x1800370ae  cmovge  r10d, r11d
0x1800370b2  movzx   r11d, byte ptr [r13+1]
0x1800370b7  cmp     r8d, r11d
0x1800370ba  mov     r9d, r11d
0x1800370bd  cmovle  r9d, r8d
0x1800370c1  cmp     r10d, r11d
0x1800370c4  cmovge  r11d, r10d
0x1800370c8  movzx   r10d, byte ptr [r13+2]
0x1800370cd  cmp     r9d, r10d
0x1800370d0  mov     r8d, r10d
0x1800370d3  cmovle  r8d, r9d
0x1800370d7  cmp     r11d, r10d
0x1800370da  cmovge  r10d, r11d
0x1800370de  movzx   r11d, byte ptr [r13+3]
0x1800370e3  cmp     r8d, r11d
0x1800370e6  mov     r9d, r11d
0x1800370e9  cmovle  r9d, r8d
0x1800370ed  cmp     r10d, r11d
0x1800370f0  cmovge  r11d, r10d
0x1800370f4  movzx   r10d, byte ptr [r13+4]
0x1800370f9  cmp     r9d, r10d
0x1800370fc  mov     r8d, r10d
0x1800370ff  cmovle  r8d, r9d
0x180037103  cmp     r11d, r10d
0x180037106  cmovge  r10d, r11d
0x18003710a  movzx   r11d, byte ptr [r13+5]
0x18003710f  cmp     r8d, r11d
0x180037112  mov     r9d, r11d
0x180037115  cmovle  r9d, r8d
0x180037119  cmp     r10d, r11d
0x18003711c  cmovge  r11d, r10d
0x180037120  movzx   r10d, byte ptr [r13+6]
0x180037125  cmp     r9d, r10d
0x180037128  mov     r8d, r10d
0x18003712b  cmovle  r8d, r9d
0x18003712f  cmp     r11d, r10d
0x180037132  cmovge  r10d, r11d
0x180037136  movzx   r11d, byte ptr [r13+7]
0x18003713b  cmp     r8d, r11d
0x18003713e  mov     r9d, r11d
0x180037141  cmovle  r9d, r8d
0x180037145  cmp     r10d, r11d
0x180037148  cmovge  r11d, r10d
0x18003714c  movzx   r10d, byte ptr [r13+8]
0x180037151  cmp     r9d, r10d
0x180037154  mov     r8d, r10d
0x180037157  cmovle  r8d, r9d
0x18003715b  cmp     r11d, r10d
0x18003715e  cmovge  r10d, r11d
0x180037162  movzx   r11d, byte ptr [r13+9]
0x180037167  cmp     r8d, r11d
0x18003716a  mov     r9d, r11d
0x18003716d  cmovle  r9d, r8d
0x180037171  cmp     r10d, r11d
0x180037174  cmovge  r11d, r10d
0x180037178  movzx   r10d, byte ptr [r13+0Ah]
0x18003717d  cmp     r9d, r10d
0x180037180  mov     r8d, r10d
0x180037183  cmovle  r8d, r9d
0x180037187  movzx   r9d, byte ptr [r13+0Bh]
0x18003718c  cmp     r11d, r10d
0x18003718f  cmovge  r10d, r11d
0x180037193  mov     r11d, r9d
0x180037196  cmp     r8d, r9d
0x180037199  cmovle  r11d, r8d
0x18003719d  lea     r13, [r13+0Eh]
0x1800371a1  cmp     r10d, r9d
0x1800371a4  cmovge  r9d, r10d
0x1800371a8  sub     rcx, 1
0x1800371ac  jnz     loc_180037070
0x1800371b2  mov     r8d, [rsp+200h+var_1DC]
0x1800371b7  mov     r12d, 20h ; ' '
0x1800371bd  mov     rcx, [rsp+200h+var_1C0]
0x1800371c2  sub     r12d, r11d
0x1800371c5  mov     esi, 60h ; '`'
0x1800371ca  mov     [rsp+200h+var_1D8], r8d
0x1800371cf  sub     esi, r9d
0x1800371d2  mov     dword ptr [rbp+100h+var_180+8], r8d
0x1800371d6  cmp     r8d, r12d
0x1800371d9  jl      loc_18003731D
0x1800371df  cmp     r8d, esi
0x1800371e2  jg      loc_18003731D
0x1800371e8  mov     r8, rdx
0x1800371eb  xor     r13d, r13d
0x1800371ee  sub     r8, rax
0x1800371f1  mov     rdx, rcx
0x1800371f4  mov     [rsp+200h+var_198], r8
0x1800371f9  sub     rdx, rax
0x1800371fc  mov     rcx, r8
0x1800371ff  mov     r11, rax
0x180037202  movzx   r8d, word ptr [rcx+r11]
0x180037207  imul    r10d, r8d, 1Ah
0x18003720b  movzx   r8d, word ptr [r11]
0x18003720f  imul    r9d, r8d, 1Ah
0x180037213  movzx   r8d, word ptr [rdx+r11]
0x180037218  shr     r8w, 1
0x18003721c  shr     r10d, 8
0x180037220  mov     dword ptr [rbp+100h+var_180+4], r13d
0x180037224  shr     r9d, 8
0x180037228  add     r10w, r9w
0x18003722c  add     r10w, r8w
0x180037230  mov     word ptr [rbp+100h+var_180], r10w
0x180037235  cmp     r15d, 6
0x180037239  jge     short loc_1800372A9
0x18003723b  movups  xmm0, [rbp+100h+var_180]
0x18003723f  movsxd  r8, r15d
0x180037242  xor     edi, edi
0x180037244  add     r8, r8
0x180037247  mov     r9d, 1
0x18003724d  movups  xmmword ptr [rbp+r8*8+50h], xmm0
0x180037253  mov     r15d, [rbp+100h+var_50]
0x18003725a  inc     r15d
0x18003725d  mov     [rbp+100h+var_4C], edi
0x180037263  mov     [rbp+100h+var_50], r15d
0x18003726a  cmp     r15d, r9d
0x18003726d  jle     loc_180037307
0x180037273  lea     r10, [rbp+100h+var_A0]
0x180037277  nop     word ptr [rax+rax+00000000h]
0x180037280  movsxd  r8, edi
0x180037283  lea     r10, [r10+10h]
0x180037287  add     r8, r8
0x18003728a  movzx   r8d, word ptr [rbp+r8*8+100h+var_B0]
0x180037290  cmp     [r10-10h], r8w
0x180037295  cmovb   edi, r9d
0x180037299  inc     r9d
0x18003729c  mov     [rbp+100h+var_4C], edi
0x1800372a2  cmp     r9d, r15d
0x1800372a5  jl      short loc_180037280
0x1800372a7  jmp     short loc_180037307
0x1800372a9  movsxd  r8, edi
0x1800372ac  add     r8, r8
0x1800372af  cmp     r10w, word ptr [rbp+r8*8+100h+var_B0]
0x1800372b5  jbe     short loc_180037307
0x1800372b7  movups  xmm0, [rbp+100h+var_180]
0x1800372bb  xor     edi, edi
0x1800372bd  mov     r9d, 1
0x1800372c3  movups  [rbp+r8*8+100h+var_B0], xmm0
0x1800372c9  mov     r15d, [rbp+100h+var_50]
0x1800372d0  mov     [rbp+100h+var_4C], edi
0x1800372d6  cmp     r15d, r9d
0x1800372d9  jle     short loc_180037307
0x1800372db  lea     r10, [rbp+100h+var_A0]
0x1800372df  nop
0x1800372e0  movsxd  r8, edi
0x1800372e3  lea     r10, [r10+10h]
0x1800372e7  add     r8, r8
0x1800372ea  movzx   r8d, word ptr [rbp+r8*8+100h+var_B0]
0x1800372f0  cmp     [r10-10h], r8w
0x1800372f5  cmovb   edi, r9d
0x1800372f9  inc     r9d
0x1800372fc  mov     [rbp+100h+var_4C], edi
0x180037302  cmp     r9d, r15d
0x180037305  jl      short loc_1800372E0
0x180037307  inc     r13d
0x18003730a  add     r11, 2
0x18003730e  cmp     r13d, 40h ; '@'
0x180037312  jl      loc_180037202
0x180037318  jmp     loc_180037435
0x18003731d  xor     r13d, r13d
0x180037320  sub     rdx, rax
0x180037323  sub     rcx, rax
0x180037326  mov     r11, rax
0x180037329  nop     dword ptr [rax+00000000h]
0x180037330  movzx   r8d, word ptr [r11+rdx]
0x180037335  imul    r10d, r8d, 1Ah
0x180037339  movzx   r8d, word ptr [r11]
0x18003733d  imul    r9d, r8d, 1Ah
0x180037341  movzx   r8d, word ptr [r11+rcx]
0x180037346  shr     r8w, 1
0x18003734a  shr     r10d, 8
0x18003734e  mov     dword ptr [rbp+100h+var_180+4], r13d
0x180037352  shr     r9d, 8
0x180037356  add     r10w, r9w
0x18003735a  add     r10w, r8w
0x18003735e  mov     word ptr [rbp+100h+var_180], r10w
0x180037363  cmp     r14d, 2
0x180037367  jge     short loc_1800373C6
0x180037369  movups  xmm0, [rbp+100h+var_180]
0x18003736d  movsxd  r8, r14d
0x180037370  xor     ebx, ebx
0x180037372  add     r8, r8
0x180037375  mov     r9d, 1
0x18003737b  movups  xmmword ptr [rbp+r8*8-70h], xmm0
0x180037381  mov     r14d, [rbp+100h+var_150]
0x180037385  inc     r14d
0x180037388  mov     [rbp+100h+var_14C], ebx
0x18003738b  mov     [rbp+100h+var_150], r14d
0x18003738f  cmp     r14d, r9d
  ... truncated ...
```
