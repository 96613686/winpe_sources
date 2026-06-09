# crxIdwt53FilterTransform(CrxPlaneComp *,uint)

- ea: `0x1800213d0`
- end: `0x180021a38`
- name: `?crxIdwt53FilterTransform@@YAHPEAUCrxPlaneComp@@I@Z`
- size: `1640`
- prototype: `__int64 __fastcall(struct CrxPlaneComp *, unsigned int)`
- caller_count: `3`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x180020eb0`
- `0x1800213d0`
- `0x180021a40`

## callees

- `0x1800213d0`

## pseudocode

```c
__int64 __fastcall crxIdwt53FilterTransform(struct CrxPlaneComp *a1, unsigned int a2)
{
  __int64 v4; // rbx
  int v5; // edx
  __int64 v6; // r10
  __int64 v7; // r8
  __int64 v8; // rax
  __int64 v9; // r8
  int *v10; // rdi
  int v11; // r11d
  int *v12; // rsi
  int *v13; // r10
  __int64 v14; // r12
  __int64 v15; // r13
  __int64 v16; // rcx
  __int64 v17; // rbp
  int v18; // r14d
  int v19; // r14d
  int *v20; // rdi
  int v21; // ecx
  int i; // ebp
  int v23; // r8d
  int v24; // r8d
  int v25; // eax
  int v26; // eax
  int v27; // r8d
  int v28; // r8d
  bool v29; // zf
  int v30; // ecx
  int v31; // edx
  int *v32; // r8
  __int64 v33; // r9
  __int64 v34; // r12
  __int64 v35; // r13
  __int64 v36; // rbp
  int v37; // edx
  int v38; // ecx
  int v39; // ecx
  int v40; // ecx
  __int64 v41; // rcx
  _DWORD *v42; // r8
  int v43; // r11d
  __int64 v44; // r9
  __int64 v45; // rcx
  __int64 v46; // r9
  __int64 v47; // rcx
  __int64 v49; // r10
  __int64 v50; // r8
  __int64 v51; // rax
  __int64 v52; // r8
  int *v53; // r14
  int v54; // r11d
  int *v55; // rsi
  int *v56; // r13
  int *v57; // rbp
  int *v58; // r12
  int *v59; // rdi
  __int64 v60; // rcx
  int v61; // eax
  int v62; // ecx
  int v63; // edx
  int v64; // ecx
  int *v65; // r14
  int v66; // ecx
  int *v67; // rbp
  int v68; // edx
  int v69; // edx
  int v70; // ecx
  int v71; // edx
  int v72; // edx
  int v73; // ecx
  int v74; // r8d
  int v75; // r9d
  int v76; // r8d
  int v77; // ecx
  int v78; // edx
  int v79; // r8d
  int v80; // edx
  int v81; // ecx
  _DWORD *v82; // r9
  __int64 v83; // rdi
  __int64 v84; // rsi
  __int64 v85; // rbp
  __int64 v86; // r10
  __int64 v87; // r14
  int v88; // edx
  int v89; // ecx
  int v90; // eax
  int v91; // edx
  int v92; // r8d
  int v93; // edx
  int v94; // ecx
  __int64 v95; // [rsp+70h] [rbp+8h]
  __int64 v96; // [rsp+70h] [rbp+8h]
  __int64 v97; // [rsp+80h] [rbp+18h]
  __int64 v98; // [rsp+88h] [rbp+20h]

  v4 = *((_QWORD *)a1 + 2) + 112LL * a2;
  if ( *(_WORD *)(v4 + 98) )
    return 0;
  v5 = *(__int16 *)(v4 + 102);
  if ( *(__int16 *)(v4 + 96) < v5 - 3 )
  {
    if ( a2 )
    {
      if ( !*(_WORD *)(v4 - 14) && (unsigned int)crxIdwt53FilterTransform(a1, a2 - 1) )
        return 0xFFFFFFFFLL;
      v49 = *((_QWORD *)a1 + 2);
      v50 = (int)(a2 - 1);
      v51 = *(_QWORD *)(v49
                      + 8
                      * (14 * v50
                       + (*(char *)(112 * v50 + v49 + 100) - (__int16)(*(_WORD *)(112 * v50 + v49 + 98))-- + 5) % 5)
                      + 56);
      *(_QWORD *)v4 = v51;
    }
    v52 = *(char *)(v4 + 100);
    v53 = *(int **)v4;
    v54 = 0;
    v55 = *(int **)(v4 + 40);
    v56 = *(int **)(v4 + 8);
    v57 = *(int **)(v4 + 16);
    v58 = *(int **)(v4 + 24);
    v59 = *(int **)(v4 + 32);
    v96 = *(_QWORD *)(v4 + 8 * v52 + 56);
    v97 = *(_QWORD *)(v4 + 8LL * (((int)v52 + 1) % 5) + 56);
    v60 = *(_QWORD *)(v4 + 8LL * (((int)v52 + 2) % 5) + 56);
    *(_QWORD *)(v4 + 40) = *(_QWORD *)(v4 + 48);
    *(_QWORD *)(v4 + 48) = v55;
    v61 = *v53;
    v98 = v60;
    if ( *(__int16 *)(v4 + 104) > 1 )
    {
      v62 = *v56;
      if ( (*((_BYTE *)a1 + 52) & 2) != 0 )
      {
        v63 = v62 + 2 + v56[1];
        ++v56;
        *v59 = v61 - (v63 >> 2);
        v64 = *v57 - ((v58[1] + *v58 + 2) >> 2);
        ++v58;
      }
      else
      {
        *v59 = v61 - ((v62 + 1) >> 1);
        v64 = *v57 - ((*v58 + 1) >> 1);
      }
      *v55 = v64;
      v65 = v53 + 1;
      v66 = *(__int16 *)(v4 + 104);
      v67 = v57 + 1;
      if ( v66 - 3 > 0 )
      {
        do
        {
          v54 += 2;
          v68 = *v65++;
          v69 = v68 - ((*v56 + v56[1] + 2) >> 2);
          v70 = *v56++ + ((v69 + *v59) >> 1);
          v59[1] = v70;
          v59 += 2;
          *v59 = v69;
          v71 = *v67++;
          v72 = v71 - ((*v58 + v58[1] + 2) >> 2);
          v73 = *v58++ + ((v72 + *v55) >> 1);
          v55[1] = v73;
          v55 += 2;
          *v55 = v72;
          v66 = *(__int16 *)(v4 + 104);
        }
        while ( v54 < v66 - 3 );
        v54 = 0;
      }
      if ( (*((_BYTE *)a1 + 52) & 1) != 0 )
      {
        v74 = *v65 - ((v56[1] + *v56 + 2) >> 2);
        v59[1] = *v56 + ((v74 + *v59) >> 1);
        v75 = *v67 - ((v58[1] + *v58 + 2) >> 2);
        v55[1] = *v58 + ((v75 + *v55) >> 1);
        if ( (*(_BYTE *)(v4 + 104) & 1) != 0 )
        {
          v59[2] = v74;
          v55[2] = v75;
        }
      }
      else
      {
        v76 = *v56;
        v29 = (v66 & 1) == 0;
        v77 = *v59;
        if ( v29 )
        {
          v59[1] = v76 + v77;
          v55[1] = *v58 + *v55;
        }
        else
        {
          v78 = *v65 - ((v76 + 1) >> 1);
          v59[2] = v78;
          v59[1] = v76 + ((v78 + v77) >> 1);
          v79 = *v58;
          v80 = *v67 - ((*v58 + 1) >> 1);
          v81 = v80 + *v55;
          v55[2] = v80;
          v55[1] = v79 + (v81 >> 1);
        }
      }
    }
    else
    {
      *v59 = v61;
      *v55 = *v57;
    }
    v82 = *(_DWORD **)(v4 + 48);
    if ( *(__int16 *)(v4 + 104) > 0 )
    {
      v83 = *(_QWORD *)(v4 + 40) - (_QWORD)v82;
      v84 = v96 - (_QWORD)v82;
      v85 = v97 - (_QWORD)v82;
      v86 = *(_QWORD *)(v4 + 32) - (_QWORD)v82;
      v87 = v98 - (_QWORD)v82;
      do
      {
        ++v54;
        v88 = *(_DWORD *)((char *)v82 + v86);
        v89 = *(_DWORD *)((char *)v82 + v83) + *v82 + 2;
        v90 = *(_DWORD *)((char *)v82++ + v84);
        v91 = v88 - (v89 >> 2);
        *(_DWORD *)((char *)v82 + v85 - 4) = *(_DWORD *)((char *)v82 + v83 - 4) + ((v91 + v90) >> 1);
        *(_DWORD *)((char *)v82 + v87 - 4) = v91;
      }
      while ( v54 < *(__int16 *)(v4 + 104) );
    }
    v92 = *(__int16 *)(v4 + 102);
    v93 = *(__int16 *)(v4 + 96);
    if ( v93 >= v92 - 3 && (v92 & 1) != 0 )
    {
      *(_WORD *)(v4 + 98) += 3;
      v94 = *(char *)(v4 + 100);
      *(_WORD *)(v4 + 96) = v93 + 3;
      v40 = v94 + 3;
LABEL_57:
      *(_BYTE *)(v4 + 100) = v40 % 5;
      return 0;
    }
    *(_WORD *)(v4 + 96) = v93 + 2;
LABEL_56:
    *(_WORD *)(v4 + 98) += 2;
    v40 = *(char *)(v4 + 100) + 2;
    goto LABEL_57;
  }
  if ( (*((_BYTE *)a1 + 52) & 4) == 0 )
  {
    if ( (v5 & 1) != 0 )
    {
      if ( !a2 )
      {
LABEL_9:
        v9 = *(char *)(v4 + 100);
        v10 = *(int **)v4;
        v11 = 0;
        v12 = *(int **)(v4 + 8);
        v13 = *(int **)(v4 + 32);
        v14 = *(_QWORD *)(v4 + 8 * v9 + 56);
        v15 = *(_QWORD *)(v4 + 8LL * (((int)v9 + 1) % 5) + 56);
        v16 = *(_QWORD *)(v4 + 40);
        v17 = *(_QWORD *)(v4 + 8LL * (((int)v9 + 2) % 5) + 56);
        *(_QWORD *)(v4 + 40) = *(_QWORD *)(v4 + 48);
        *(_QWORD *)(v4 + 48) = v16;
        v95 = v17;
        if ( *(__int16 *)(v4 + 104) > 1 )
        {
          v18 = *v10;
          if ( (*((_BYTE *)a1 + 52) & 2) != 0 )
          {
            v19 = v18 - ((*v12 + 2 + v12[1]) >> 2);
            ++v12;
          }
          else
          {
            v19 = v18 - ((*v12 + 1) >> 1);
          }
          *v13 = v19;
          v20 = v10 + 1;
          v21 = *(__int16 *)(v4 + 104);
          for ( i = 0; i < v21 - 3; v21 = *(__int16 *)(v4 + 104) )
          {
            i += 2;
            v23 = *v20++;
            v24 = v23 - ((*v12 + v12[1] + 2) >> 2);
            v25 = v19 + v24;
            v19 = v24;
            v26 = *v12++ + (v25 >> 1);
            v13[1] = v26;
            v13 += 2;
            *v13 = v24;
          }
          v17 = v95;
          if ( (*((_BYTE *)a1 + 52) & 1) != 0 )
          {
            v27 = *v20 - ((v12[1] + *v12 + 2) >> 2);
            v13[1] = *v12 + ((v27 + *v13) >> 1);
            if ( (*(_BYTE *)(v4 + 104) & 1) != 0 )
              v13[2] = v27;
          }
          else
          {
            v28 = *v12;
            v29 = (v21 & 1) == 0;
            v30 = *v13;
            if ( !v29 )
            {
              v31 = *v20 - ((v28 + 1) >> 1);
              v13[2] = v31;
              v30 = (v31 + v30) >> 1;
            }
            v13[1] = v28 + v30;
          }
        }
        else
        {
          *v13 = *v10;
        }
        v32 = *(int **)(v4 + 32);
        if ( *(__int16 *)(v4 + 104) > 0 )
        {
          v33 = *(_QWORD *)(v4 + 40) - (_QWORD)v32;
          v34 = v14 - (_QWORD)v32;
          v35 = v15 - (_QWORD)v32;
          v36 = v17 - (_QWORD)v32;
          do
          {
            v37 = *(int *)((char *)v32 + v33);
            ++v11;
            v38 = *v32++;
            v39 = v38 - ((v37 + 1) >> 1);
            *(int *)((char *)v32 + v35 - 4) = v37 + ((v39 + *(int *)((char *)v32 + v34 - 4)) >> 1);
            *(int *)((char *)v32 + v36 - 4) = v39;
          }
          while ( v11 < *(__int16 *)(v4 + 104) );
        }
        *(_WORD *)(v4 + 98) += 3;
        *(_WORD *)(v4 + 96) += 3;
        v40 = *(char *)(v4 + 100) + 3;
        goto LABEL_57;
      }
      if ( *(_WORD *)(v4 - 14) || !(unsigned int)crxIdwt53FilterTransform(a1, a2 - 1) )
      {
        v6 = *((_QWORD *)a1 + 2);
        v7 = (int)(a2 - 1);
        v8 = *(_QWORD *)(v6
                       + 8
                       * (14 * v7
                        + (*(char *)(112 * v7 + v6 + 100) - (__int16)(*(_WORD *)(112 * v7 + v6 + 98))-- + 5) % 5)
                       + 56);
        *(_QWORD *)v4 = v8;
        goto LABEL_9;
      }
      return 0xFFFFFFFFLL;
    }
    v41 = *(char *)(v4 + 100);
    v42 = *(_DWORD **)(v4 + 48);
    v43 = 0;
    v44 = *(_QWORD *)(v4 + 8 * v41 + 56);
    v45 = *(_QWORD *)(v4 + 8LL * (((int)v41 + 1) % 5) + 56);
    *(_QWORD *)(v4 + 40) = v42;
    if ( *(__int16 *)(v4 + 104) > 0 )
    {
      v46 = v44 - (_QWORD)v42;
      v47 = v45 - (_QWORD)v42;
      do
      {
        ++v43;
        *(_DWORD *)((char *)v42 + v47) = *v42 + *(_DWORD *)((char *)v42 + v46);
        ++v42;
      }
      while ( v43 < *(__int16 *)(v4 + 104) );
    }
    *(_WORD *)(v4 + 96) += 2;
    goto LABEL_56;
  }
  return 0;
}

```

## disassembly

```asm
0x1800213d0  push    rbx
0x1800213d2  push    rbp
0x1800213d3  push    rsi
0x1800213d4  push    rdi
0x1800213d5  push    r12
0x1800213d7  push    r13
0x1800213d9  push    r14
0x1800213db  push    r15
0x1800213dd  sub     rsp, 28h
0x1800213e1  mov     edi, edx
0x1800213e3  mov     r15, rcx
0x1800213e6  imul    rbx, rdi, 70h ; 'p'
0x1800213ea  add     rbx, [rcx+10h]
0x1800213ee  cmp     word ptr [rbx+62h], 0
0x1800213f3  jnz     loc_180021A25
0x1800213f9  movsx   edx, word ptr [rbx+66h]
0x1800213fd  movsx   eax, word ptr [rbx+60h]
0x180021401  lea     ecx, [rdx-3]
0x180021404  cmp     eax, ecx
0x180021406  jl      loc_1800216C5
0x18002140c  test    byte ptr [r15+34h], 4
0x180021411  jnz     loc_180021A25
0x180021417  test    dl, 1
0x18002141a  jz      loc_180021659
0x180021420  test    edi, edi
0x180021422  jz      short loc_18002148F
0x180021424  cmp     word ptr [rbx-0Eh], 0
0x180021429  jnz     short loc_18002143E
0x18002142b  lea     edx, [rdi-1]; unsigned int
0x18002142e  mov     rcx, r15; struct CrxPlaneComp *
0x180021431  call    ?crxIdwt53FilterTransform@@YAHPEAUCrxPlaneComp@@I@Z; crxIdwt53FilterTransform(CrxPlaneComp *,uint)
0x180021436  test    eax, eax
0x180021438  jnz     loc_1800216DF
0x18002143e  mov     r10, [r15+10h]
0x180021442  lea     eax, [rdi-1]
0x180021445  movsxd  r8, eax
0x180021448  mov     eax, 66666667h
0x18002144d  imul    r11, r8, 70h ; 'p'
0x180021451  movsx   r9d, word ptr [r11+r10+62h]
0x180021457  movsx   ecx, byte ptr [r11+r10+64h]
0x18002145d  sub     ecx, r9d
0x180021460  add     ecx, 5
0x180021463  imul    ecx
0x180021465  sar     edx, 1
0x180021467  mov     eax, edx
0x180021469  shr     eax, 1Fh
0x18002146c  add     edx, eax
0x18002146e  lea     eax, [rdx+rdx*4]
0x180021471  sub     ecx, eax
0x180021473  imul    rax, r8, 0Eh
0x180021477  movsxd  rcx, ecx
0x18002147a  add     rcx, rax
0x18002147d  dec     r9w
0x180021481  mov     rax, [r10+rcx*8+38h]
0x180021486  mov     [r11+r10+62h], r9w
0x18002148c  mov     [rbx], rax
0x18002148f  movsx   r8, byte ptr [rbx+64h]
0x180021494  mov     eax, 66666667h
0x180021499  mov     rdi, [rbx]
0x18002149c  xor     r11d, r11d
0x18002149f  mov     rsi, [rbx+8]
0x1800214a3  mov     r10, [rbx+20h]
0x1800214a7  mov     r12, [rbx+r8*8+38h]
0x1800214ac  lea     ecx, [r8+1]
0x1800214b0  imul    ecx
0x1800214b2  sar     edx, 1
0x1800214b4  mov     eax, edx
0x1800214b6  shr     eax, 1Fh
0x1800214b9  add     edx, eax
0x1800214bb  lea     eax, [rdx+rdx*4]
0x1800214be  sub     ecx, eax
0x1800214c0  movsxd  rax, ecx
0x1800214c3  lea     ecx, [r8+2]
0x1800214c7  mov     r13, [rbx+rax*8+38h]
0x1800214cc  mov     eax, 66666667h
0x1800214d1  imul    ecx
0x1800214d3  sar     edx, 1
0x1800214d5  mov     eax, edx
0x1800214d7  shr     eax, 1Fh
0x1800214da  add     edx, eax
0x1800214dc  lea     eax, [rdx+rdx*4]
0x1800214df  sub     ecx, eax
0x1800214e1  movsxd  rax, ecx
0x1800214e4  mov     rcx, [rbx+28h]
0x1800214e8  mov     rbp, [rbx+rax*8+38h]
0x1800214ed  mov     rax, [rbx+30h]
0x1800214f1  mov     [rbx+28h], rax
0x1800214f5  mov     [rbx+30h], rcx
0x1800214f9  cmp     word ptr [rbx+68h], 1
0x1800214fe  mov     [rsp+68h+arg_0], rbp
0x180021503  jg      short loc_18002150F
0x180021505  mov     eax, [rdi]
0x180021507  mov     [r10], eax
0x18002150a  jmp     loc_1800215E8
0x18002150f  test    byte ptr [r15+34h], 2
0x180021514  mov     r14d, [rdi]
0x180021517  jz      short loc_18002152F
0x180021519  mov     ecx, [rsi]
0x18002151b  mov     edx, [rsi+4]
0x18002151e  add     ecx, 2
0x180021521  add     edx, ecx
0x180021523  sar     edx, 2
0x180021526  sub     r14d, edx
0x180021529  add     rsi, 4
0x18002152d  jmp     short loc_180021538
0x18002152f  mov     eax, [rsi]
0x180021531  inc     eax
0x180021533  sar     eax, 1
0x180021535  sub     r14d, eax
0x180021538  mov     [r10], r14d
0x18002153b  add     rdi, 4
0x18002153f  movsx   ecx, word ptr [rbx+68h]
0x180021543  mov     ebp, r11d
0x180021546  lea     eax, [rcx-3]
0x180021549  test    eax, eax
0x18002154b  jle     short loc_18002158D
0x18002154d  nop     dword ptr [rax]
0x180021550  mov     ecx, [rsi+4]
0x180021553  add     ebp, 2
0x180021556  mov     r8d, [rdi]
0x180021559  add     ecx, 2
0x18002155c  add     ecx, [rsi]
0x18002155e  add     rdi, 4
0x180021562  sar     ecx, 2
0x180021565  sub     r8d, ecx
0x180021568  lea     eax, [r14+r8]
0x18002156c  mov     r14d, r8d
0x18002156f  sar     eax, 1
0x180021571  add     eax, [rsi]
0x180021573  add     rsi, 4
0x180021577  mov     [r10+4], eax
0x18002157b  add     r10, 8
0x18002157f  mov     [r10], r8d
0x180021582  movsx   ecx, word ptr [rbx+68h]
0x180021586  lea     eax, [rcx-3]
0x180021589  cmp     ebp, eax
0x18002158b  jl      short loc_180021550
0x18002158d  test    byte ptr [r15+34h], 1
0x180021592  mov     rbp, [rsp+68h+arg_0]
0x180021597  jz      short loc_1800215C4
0x180021599  mov     edx, [rsi]
0x18002159b  mov     r8d, [rdi]
0x18002159e  lea     ecx, [rdx+2]
0x1800215a1  add     ecx, [rsi+4]
0x1800215a4  sar     ecx, 2
0x1800215a7  sub     r8d, ecx
0x1800215aa  mov     ecx, [r10]
0x1800215ad  add     ecx, r8d
0x1800215b0  sar     ecx, 1
0x1800215b2  add     ecx, edx
0x1800215b4  mov     [r10+4], ecx
0x1800215b8  test    byte ptr [rbx+68h], 1
0x1800215bc  jz      short loc_1800215E8
0x1800215be  mov     [r10+8], r8d
0x1800215c2  jmp     short loc_1800215E8
0x1800215c4  mov     r8d, [rsi]
0x1800215c7  test    cl, 1
0x1800215ca  mov     ecx, [r10]
0x1800215cd  jz      short loc_1800215E1
0x1800215cf  mov     edx, [rdi]
0x1800215d1  lea     eax, [r8+1]
0x1800215d5  sar     eax, 1
0x1800215d7  sub     edx, eax
0x1800215d9  add     ecx, edx
0x1800215db  mov     [r10+8], edx
0x1800215df  sar     ecx, 1
0x1800215e1  add     ecx, r8d
0x1800215e4  mov     [r10+4], ecx
0x1800215e8  mov     r8, [rbx+20h]
0x1800215ec  mov     r9, [rbx+28h]
0x1800215f0  cmp     r11w, [rbx+68h]
0x1800215f5  jge     short loc_180021643
0x1800215f7  sub     r9, r8
0x1800215fa  sub     r12, r8
0x1800215fd  sub     r13, r8
0x180021600  sub     rbp, r8
0x180021603  nop     dword ptr [rax+00h]
0x180021607  nop     word ptr [rax+rax+00000000h]
0x180021610  mov     edx, [r8+r9]
0x180021614  inc     r11d
0x180021617  mov     ecx, [r8]
0x18002161a  lea     r8, [r8+4]
0x18002161e  lea     eax, [rdx+1]
0x180021621  sar     eax, 1
0x180021623  sub     ecx, eax
0x180021625  mov     eax, [r8+r12-4]
0x18002162a  add     eax, ecx
0x18002162c  sar     eax, 1
0x18002162e  add     eax, edx
0x180021630  mov     [r8+r13-4], eax
0x180021635  mov     [r8+rbp-4], ecx
0x18002163a  movsx   ecx, word ptr [rbx+68h]
0x18002163e  cmp     r11d, ecx
0x180021641  jl      short loc_180021610
0x180021643  add     word ptr [rbx+62h], 3
0x180021648  add     word ptr [rbx+60h], 3
0x18002164d  movsx   ecx, byte ptr [rbx+64h]
0x180021651  add     ecx, 3
0x180021654  jmp     loc_180021A0D
0x180021659  movsx   rcx, byte ptr [rbx+64h]
0x18002165e  mov     eax, 66666667h
0x180021663  mov     r8, [rbx+30h]
0x180021667  xor     r11d, r11d
0x18002166a  mov     r9, [rbx+rcx*8+38h]
0x18002166f  inc     ecx
0x180021671  imul    ecx
0x180021673  sar     edx, 1
0x180021675  mov     eax, edx
0x180021677  shr     eax, 1Fh
0x18002167a  add     edx, eax
0x18002167c  lea     eax, [rdx+rdx*4]
0x18002167f  sub     ecx, eax
0x180021681  movsxd  rax, ecx
0x180021684  mov     rcx, [rbx+rax*8+38h]
0x180021689  mov     [rbx+28h], r8
0x18002168d  cmp     r11w, [rbx+68h]
0x180021692  jge     short loc_1800216BB
0x180021694  sub     r9, r8
0x180021697  sub     rcx, r8
0x18002169a  nop     word ptr [rax+rax+00h]
0x1800216a0  mov     eax, [r8+r9]
0x1800216a4  inc     r11d
0x1800216a7  add     eax, [r8]
0x1800216aa  mov     [rcx+r8], eax
0x1800216ae  lea     r8, [r8+4]
0x1800216b2  movsx   eax, word ptr [rbx+68h]
0x1800216b6  cmp     r11d, eax
0x1800216b9  jl      short loc_1800216A0
0x1800216bb  add     word ptr [rbx+60h], 2
0x1800216c0  jmp     loc_180021A01
0x1800216c5  test    edi, edi
0x1800216c7  jz      short loc_18002173A
0x1800216c9  cmp     word ptr [rbx-0Eh], 0
0x1800216ce  jnz     short loc_1800216E9
0x1800216d0  lea     edx, [rdi-1]; unsigned int
0x1800216d3  mov     rcx, r15; struct CrxPlaneComp *
0x1800216d6  call    ?crxIdwt53FilterTransform@@YAHPEAUCrxPlaneComp@@I@Z; crxIdwt53FilterTransform(CrxPlaneComp *,uint)
0x1800216db  test    eax, eax
0x1800216dd  jz      short loc_1800216E9
0x1800216df  mov     eax, 0FFFFFFFFh
0x1800216e4  jmp     loc_180021A27
0x1800216e9  mov     r10, [r15+10h]
0x1800216ed  lea     eax, [rdi-1]
0x1800216f0  movsxd  r8, eax
0x1800216f3  mov     eax, 66666667h
0x1800216f8  imul    r11, r8, 70h ; 'p'
0x1800216fc  movsx   r9d, word ptr [r11+r10+62h]
0x180021702  movsx   ecx, byte ptr [r11+r10+64h]
0x180021708  sub     ecx, r9d
0x18002170b  add     ecx, 5
0x18002170e  imul    ecx
0x180021710  sar     edx, 1
0x180021712  mov     eax, edx
0x180021714  shr     eax, 1Fh
0x180021717  add     edx, eax
0x180021719  lea     eax, [rdx+rdx*4]
0x18002171c  sub     ecx, eax
0x18002171e  imul    rax, r8, 0Eh
0x180021722  movsxd  rcx, ecx
0x180021725  add     rcx, rax
0x180021728  dec     r9w
0x18002172c  mov     rax, [r10+rcx*8+38h]
0x180021731  mov     [r11+r10+62h], r9w
0x180021737  mov     [rbx], rax
0x18002173a  movsx   r8, byte ptr [rbx+64h]
0x18002173f  mov     eax, 66666667h
0x180021744  mov     r14, [rbx]
0x180021747  xor     r11d, r11d
0x18002174a  mov     rsi, [rbx+28h]
0x18002174e  mov     r13, [rbx+8]
0x180021752  mov     rcx, [rbx+r8*8+38h]
0x180021757  mov     rbp, [rbx+10h]
0x18002175b  mov     r12, [rbx+18h]
0x18002175f  mov     rdi, [rbx+20h]
0x180021763  mov     [rsp+68h+arg_0], rcx
0x180021768  lea     ecx, [r8+1]
0x18002176c  imul    ecx
0x18002176e  sar     edx, 1
0x180021770  mov     eax, edx
0x180021772  shr     eax, 1Fh
0x180021775  add     edx, eax
0x180021777  lea     eax, [rdx+rdx*4]
0x18002177a  sub     ecx, eax
0x18002177c  movsxd  rax, ecx
0x18002177f  mov     rcx, [rbx+rax*8+38h]
0x180021784  mov     eax, 66666667h
0x180021789  mov     [rsp+68h+arg_10], rcx
0x180021791  lea     ecx, [r8+2]
0x180021795  imul    ecx
0x180021797  sar     edx, 1
0x180021799  mov     eax, edx
0x18002179b  shr     eax, 1Fh
0x18002179e  add     edx, eax
0x1800217a0  lea     eax, [rdx+rdx*4]
0x1800217a3  sub     ecx, eax
0x1800217a5  movsxd  rax, ecx
0x1800217a8  mov     rcx, [rbx+rax*8+38h]
0x1800217ad  mov     rax, [rbx+30h]
0x1800217b1  mov     [rbx+28h], rax
0x1800217b5  mov     [rbx+30h], rsi
  ... truncated ...
```
