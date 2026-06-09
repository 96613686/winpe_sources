# crxIdwt53FilterInitialize(CrxPlaneComp *,int,CrxQStep *)

- ea: `0x180020eb0`
- end: `0x1800213c9`
- name: `?crxIdwt53FilterInitialize@@YAHPEAUCrxPlaneComp@@HPEAUCrxQStep@@@Z`
- size: `1305`
- prototype: `__int64 __fastcall(struct CrxPlaneComp *, int, struct CrxQStep *)`
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x180021a40`

## callees

- `0x18001c700`
- `0x180020ba0`
- `0x180020d90`
- `0x180020eb0`
- `0x1800213d0`

## pseudocode

```c
__int64 __fastcall crxIdwt53FilterInitialize(struct CrxPlaneComp *a1, int a2, struct CrxQStep *a3)
{
  struct CrxPlaneComp *v3; // r14
  signed int v4; // edi
  int v5; // r10d
  __int64 v6; // r11
  __int64 v7; // r15
  char *v8; // rcx
  _QWORD *v9; // rsi
  struct CrxQStep *v10; // rbp
  __int64 v11; // r9
  __int64 v12; // rbx
  bool v13; // zf
  __int64 v14; // rdi
  __int64 v15; // rcx
  __int64 v16; // rdi
  char *v17; // r15
  struct CrxSubband *v18; // rcx
  __int64 v19; // r12
  __int64 v20; // r13
  int *v21; // rdi
  char *v22; // r14
  char *v23; // rsi
  unsigned int v24; // r9d
  int *v25; // r10
  int *v26; // r11
  int v27; // ebp
  int v28; // ebp
  int *v29; // r10
  int v30; // ecx
  int i; // r12d
  int v32; // r8d
  int v33; // r8d
  int v34; // eax
  int v35; // eax
  int v36; // edx
  int v37; // r8d
  int v38; // ecx
  int v39; // eax
  int v40; // r8d
  signed __int64 v41; // rsi
  signed __int64 v42; // rdi
  signed __int64 v43; // r15
  int v44; // edx
  int v45; // eax
  int v46; // edx
  signed __int64 v47; // rsi
  signed __int64 v48; // r15
  int v49; // ecx
  int v50; // eax
  unsigned int v51; // edi
  _DWORD *v52; // r10
  int *v53; // rcx
  int v54; // r11d
  int v55; // edx
  int v56; // r11d
  int *v57; // r10
  int v58; // edx
  int j; // edi
  int v60; // edx
  int v61; // r8d
  int v62; // r8d
  int v63; // eax
  int v64; // r8d
  int v65; // edx
  int v66; // ecx
  int v67; // ecx
  int v69; // [rsp+20h] [rbp-68h]
  _QWORD *v70; // [rsp+28h] [rbp-60h]
  __int64 v71; // [rsp+30h] [rbp-58h]
  __int64 v72; // [rsp+38h] [rbp-50h]
  struct CrxQStep *v75; // [rsp+A0h] [rbp+18h]
  unsigned int v76; // [rsp+A8h] [rbp+20h]

  v75 = a3;
  v3 = a1;
  if ( a2 )
  {
    v76 = 0;
    v4 = 0;
    v69 = 0;
    v5 = 0;
    if ( a2 > 0 )
    {
      v6 = -112;
      v7 = -14;
      v8 = (char *)a1 + 8;
      v72 = -112;
      v71 = -14;
      v9 = v8;
      while ( 1 )
      {
        v70 = v9;
        if ( a3 )
        {
          v10 = (struct CrxQStep *)((char *)a3 + 16 * v4);
        }
        else
        {
          v10 = 0;
          v70 = v8;
          v9 = v8;
        }
        v11 = *((_QWORD *)v3 + 2);
        v12 = v11 + 112LL * v4;
        v13 = v4 == 0;
        v14 = v5;
        if ( v13 )
        {
          if ( (unsigned int)crxDecodeLineWithIQuantization((struct CrxSubband *)(*v9 + 88LL * v5), v10) )
            return 0xFFFFFFFFLL;
        }
        else
        {
          v15 = *(_QWORD *)(v11
                          + 8 * (v7 + (*(char *)(v6 + v11 + 100) - (__int16)(*(_WORD *)(v6 + v11 + 98))-- + 5) % 5)
                          + 56);
          *(_QWORD *)v12 = v15;
        }
        v16 = 88 * v14;
        v17 = *(char **)(v12 + 8LL * *(char *)(v12 + 100) + 56);
        v18 = (struct CrxSubband *)(*v9 + v16 + 88);
        if ( *(__int16 *)(v12 + 102) <= 1 )
          break;
        if ( (unsigned int)crxDecodeLineWithIQuantization(v18, v10) )
          return 0xFFFFFFFFLL;
        v19 = v16 + 176;
        if ( (unsigned int)crxDecodeLineWithIQuantization((struct CrxSubband *)(v16 + 176 + *v9), v10) )
          return 0xFFFFFFFFLL;
        v20 = v16 + 264;
        if ( (unsigned int)crxDecodeLineWithIQuantization((struct CrxSubband *)(v16 + 264 + *v9), v10) )
          return 0xFFFFFFFFLL;
        v21 = *(int **)(v12 + 32);
        v22 = *(char **)(v12 + 40);
        v23 = *(char **)(v12 + 48);
        v24 = *((char *)a1 + 52);
        if ( (*((_BYTE *)a1 + 52) & 8) != 0 )
        {
          crxHorizontal53(v21, *(int **)(v12 + 40), (struct CrxWaveletTransform *)v12, v24);
          if ( (unsigned int)crxDecodeLineWithIQuantization((struct CrxSubband *)(v20 + *v70), v10)
            || (unsigned int)crxDecodeLineWithIQuantization((struct CrxSubband *)(v19 + *v70), v10) )
          {
            return 0xFFFFFFFFLL;
          }
          v25 = *(int **)(v12 + 16);
          v26 = *(int **)(v12 + 24);
          if ( *(__int16 *)(v12 + 104) > 1 )
          {
            v27 = *v25;
            if ( (*((_BYTE *)a1 + 52) & 2) != 0 )
            {
              v28 = v27 - ((v26[1] + *v26 + 2) >> 2);
              ++v26;
            }
            else
            {
              v28 = v27 - ((*v26 + 1) >> 1);
            }
            *(_DWORD *)v23 = v28;
            v29 = v25 + 1;
            v30 = *(__int16 *)(v12 + 104);
            for ( i = 0; i < v30 - 3; v30 = *(__int16 *)(v12 + 104) )
            {
              i += 2;
              v32 = *v29++;
              v33 = v32 - ((*v26 + v26[1] + 2) >> 2);
              v34 = v33 + v28;
              v28 = v33;
              v35 = *v26++ + (v34 >> 1);
              *((_DWORD *)v23 + 1) = v35;
              v23 += 8;
              *(_DWORD *)v23 = v33;
            }
            v36 = *v26;
            if ( (*((_BYTE *)a1 + 52) & 1) != 0 )
            {
              v37 = *v29 - ((v26[1] + v36 + 2) >> 2);
              *((_DWORD *)v23 + 1) = v36 + ((v37 + *(_DWORD *)v23) >> 1);
              if ( (*(_BYTE *)(v12 + 104) & 1) != 0 )
                *((_DWORD *)v23 + 2) = v37;
            }
            else if ( (v30 & 1) != 0 )
            {
              v38 = *v29 - ((v36 + 1) >> 1);
              v39 = v38 + *(_DWORD *)v23;
              *((_DWORD *)v23 + 2) = v38;
              *((_DWORD *)v23 + 1) = v36 + (v39 >> 1);
            }
            else
            {
              *((_DWORD *)v23 + 1) = v36 + *(_DWORD *)v23;
            }
          }
          else
          {
            *(_DWORD *)v23 = *v25;
          }
          v40 = 0;
          if ( *(__int16 *)(v12 + 104) > 0 )
          {
            v41 = v23 - v22;
            v42 = (char *)v21 - v22;
            v43 = v17 - v22;
            do
            {
              v44 = *(_DWORD *)v22;
              ++v40;
              v45 = *(_DWORD *)&v22[v42];
              v22 += 4;
              *(_DWORD *)&v22[v43 - 4] = v45 - ((*(_DWORD *)&v22[v41 - 4] + v44 + 2) >> 2);
            }
            while ( v40 < *(__int16 *)(v12 + 104) );
          }
        }
        else
        {
          crxHorizontal53(v21, *(int **)(v12 + 48), (struct CrxWaveletTransform *)v12, v24);
          v46 = 0;
          if ( *(__int16 *)(v12 + 104) > 0 )
          {
            v47 = v23 - (char *)v21;
            v48 = v17 - (char *)v21;
            do
            {
              v49 = *(int *)((char *)v21 + v47);
              ++v46;
              v50 = *v21++;
              *(int *)((char *)v21 + v48 - 4) = v50 - ((v49 + 1) >> 1);
            }
            while ( v46 < *(__int16 *)(v12 + 104) );
          }
        }
        v3 = a1;
        v51 = v76;
        if ( (unsigned int)crxIdwt53FilterDecode(a1, v76, v75) || (unsigned int)crxIdwt53FilterTransform(a1, v76) )
          return 0xFFFFFFFFLL;
        v9 = v70;
LABEL_55:
        v4 = v51 + 1;
        v7 = v71 + 14;
        v6 = v72 + 112;
        v5 = v69 + 3;
        v76 = v4;
        v71 += 14;
        v72 += 112;
        v69 += 3;
        if ( v4 >= a2 )
          return 0;
        a3 = v75;
        v8 = (char *)v3 + 8;
      }
      if ( (unsigned int)crxDecodeLineWithIQuantization(v18, v10) )
        return 0xFFFFFFFFLL;
      v52 = *(_DWORD **)v12;
      v53 = *(int **)(v12 + 8);
      if ( *(__int16 *)(v12 + 104) <= 1 )
      {
        *(_DWORD *)v17 = *v52;
LABEL_54:
        v67 = *(char *)(v12 + 100);
        ++*(_WORD *)(v12 + 96);
        ++*(_WORD *)(v12 + 98);
        v51 = v76;
        *(_BYTE *)(v12 + 100) = (v67 + 1) % 5;
        goto LABEL_55;
      }
      v54 = *v52;
      if ( (*((_BYTE *)v3 + 52) & 2) != 0 )
      {
        v55 = *v53 + 2 + v53[1];
        ++v53;
        v56 = v54 - (v55 >> 2);
      }
      else
      {
        v56 = v54 - ((*v53 + 1) >> 1);
      }
      *(_DWORD *)v17 = v56;
      v57 = v52 + 1;
      v58 = *(__int16 *)(v12 + 104);
      for ( j = 0; j < v58 - 3; v58 = *(__int16 *)(v12 + 104) )
      {
        v60 = *v53;
        j += 2;
        v61 = *v57++;
        v62 = v61 - ((*v53 + v53[1] + 2) >> 2);
        ++v53;
        *((_DWORD *)v17 + 2) = v62;
        v63 = v62 + v56;
        v56 = v62;
        *((_DWORD *)v17 + 1) = v60 + (v63 >> 1);
        v17 += 8;
      }
      v64 = *v53;
      if ( (*((_BYTE *)v3 + 52) & 1) != 0 )
      {
        v65 = *v57 - ((v53[1] + v64 + 2) >> 2);
        v66 = *(_DWORD *)v17;
      }
      else
      {
        v66 = *(_DWORD *)v17;
        if ( (v58 & 1) == 0 )
        {
LABEL_53:
          *((_DWORD *)v17 + 1) = v64 + v66;
          goto LABEL_54;
        }
        v65 = *v57 - ((v64 + 1) >> 1);
      }
      *((_DWORD *)v17 + 2) = v65;
      v66 = (v65 + v66) >> 1;
      goto LABEL_53;
    }
  }
  return 0;
}

```

## disassembly

```asm
0x180020eb0  mov     [rsp+arg_10], r8
0x180020eb5  mov     [rsp+arg_8], edx
0x180020eb9  mov     [rsp+arg_0], rcx
0x180020ebe  push    rbx
0x180020ebf  push    rbp
0x180020ec0  push    rsi
0x180020ec1  push    rdi
0x180020ec2  push    r12
0x180020ec4  push    r13
0x180020ec6  push    r14
0x180020ec8  push    r15
0x180020eca  sub     rsp, 48h
0x180020ece  mov     r14, rcx
0x180020ed1  test    edx, edx
0x180020ed3  jz      loc_1800213B6
0x180020ed9  xor     r12d, r12d
0x180020edc  mov     [rsp+88h+arg_18], r12d
0x180020ee4  mov     edi, r12d
0x180020ee7  mov     [rsp+88h+var_68], r12d
0x180020eec  mov     r10d, r12d
0x180020eef  test    edx, edx
0x180020ef1  jle     loc_1800213B6
0x180020ef7  mov     r11, 0FFFFFFFFFFFFFF90h
0x180020efe  mov     r15, 0FFFFFFFFFFFFFFF2h
0x180020f05  add     rcx, 8
0x180020f09  mov     [rsp+88h+var_50], r11
0x180020f0e  mov     [rsp+88h+var_58], r15
0x180020f13  mov     rsi, rcx
0x180020f16  nop     word ptr [rax+rax+00000000h]
0x180020f20  mov     [rsp+88h+var_60], rsi
0x180020f25  movsxd  rax, edi
0x180020f28  test    r8, r8
0x180020f2b  jz      short loc_180020F39
0x180020f2d  mov     rbp, rax
0x180020f30  shl     rbp, 4
0x180020f34  add     rbp, r8
0x180020f37  jmp     short loc_180020F44
0x180020f39  mov     rbp, r12
0x180020f3c  mov     [rsp+88h+var_60], rcx
0x180020f41  mov     rsi, rcx
0x180020f44  mov     r9, [r14+10h]
0x180020f48  imul    rbx, rax, 70h ; 'p'
0x180020f4c  add     rbx, r9
0x180020f4f  test    edi, edi
0x180020f51  movsxd  rdi, r10d
0x180020f54  jz      short loc_180020F97
0x180020f56  movsx   r8d, word ptr [r11+r9+62h]
0x180020f5c  mov     eax, 66666667h
0x180020f61  movsx   ecx, byte ptr [r11+r9+64h]
0x180020f67  sub     ecx, r8d
0x180020f6a  add     ecx, 5
0x180020f6d  imul    ecx
0x180020f6f  sar     edx, 1
0x180020f71  mov     eax, edx
0x180020f73  shr     eax, 1Fh
0x180020f76  add     edx, eax
0x180020f78  lea     eax, [rdx+rdx*4]
0x180020f7b  sub     ecx, eax
0x180020f7d  movsxd  rax, ecx
0x180020f80  add     rax, r15
0x180020f83  dec     r8w
0x180020f87  mov     rcx, [r9+rax*8+38h]
0x180020f8c  mov     [r11+r9+62h], r8w
0x180020f92  mov     [rbx], rcx
0x180020f95  jmp     short loc_180020FAE
0x180020f97  imul    rcx, rdi, 58h ; 'X'
0x180020f9b  mov     rdx, rbp; struct CrxQStep *
0x180020f9e  add     rcx, [rsi]; struct CrxSubband *
0x180020fa1  call    ?crxDecodeLineWithIQuantization@@YAHPEAUCrxSubband@@PEAUCrxQStep@@@Z; crxDecodeLineWithIQuantization(CrxSubband *,CrxQStep *)
0x180020fa6  test    eax, eax
0x180020fa8  jnz     loc_1800213AF
0x180020fae  movsx   rax, byte ptr [rbx+64h]
0x180020fb3  mov     rdx, rbp; struct CrxQStep *
0x180020fb6  imul    rdi, 58h ; 'X'
0x180020fba  mov     r15, [rbx+rax*8+38h]
0x180020fbf  lea     rcx, [rdi+58h]
0x180020fc3  add     rcx, [rsi]; struct CrxSubband *
0x180020fc6  cmp     word ptr [rbx+66h], 1
0x180020fcb  jle     loc_180021243
0x180020fd1  call    ?crxDecodeLineWithIQuantization@@YAHPEAUCrxSubband@@PEAUCrxQStep@@@Z; crxDecodeLineWithIQuantization(CrxSubband *,CrxQStep *)
0x180020fd6  test    eax, eax
0x180020fd8  jnz     loc_1800213AF
0x180020fde  mov     rcx, [rsi]
0x180020fe1  lea     r12, [rdi+0B0h]
0x180020fe8  add     rcx, r12; struct CrxSubband *
0x180020feb  mov     rdx, rbp; struct CrxQStep *
0x180020fee  call    ?crxDecodeLineWithIQuantization@@YAHPEAUCrxSubband@@PEAUCrxQStep@@@Z; crxDecodeLineWithIQuantization(CrxSubband *,CrxQStep *)
0x180020ff3  test    eax, eax
0x180020ff5  jnz     loc_1800213AF
0x180020ffb  mov     rcx, [rsi]
0x180020ffe  lea     r13, [rdi+108h]
0x180021005  add     rcx, r13; struct CrxSubband *
0x180021008  mov     rdx, rbp; struct CrxQStep *
0x18002100b  call    ?crxDecodeLineWithIQuantization@@YAHPEAUCrxSubband@@PEAUCrxQStep@@@Z; crxDecodeLineWithIQuantization(CrxSubband *,CrxQStep *)
0x180021010  test    eax, eax
0x180021012  jnz     loc_1800213AF
0x180021018  mov     rax, [rsp+88h+arg_0]
0x180021020  mov     r8, rbx; struct CrxWaveletTransform *
0x180021023  mov     rdi, [rbx+20h]
0x180021027  mov     r14, [rbx+28h]
0x18002102b  mov     rcx, rdi; int *
0x18002102e  mov     rsi, [rbx+30h]
0x180021032  movsx   eax, byte ptr [rax+34h]
0x180021036  mov     r9d, eax; unsigned int
0x180021039  test    al, 8
0x18002103b  jz      loc_1800211BB
0x180021041  mov     rdx, r14; int *
0x180021044  call    ?crxHorizontal53@@YAXPEAH0PEAUCrxWaveletTransform@@I@Z; crxHorizontal53(int *,int *,CrxWaveletTransform *,uint)
0x180021049  mov     rcx, [rsp+88h+var_60]
0x18002104e  mov     rdx, rbp; struct CrxQStep *
0x180021051  mov     rcx, [rcx]
0x180021054  add     rcx, r13; struct CrxSubband *
0x180021057  call    ?crxDecodeLineWithIQuantization@@YAHPEAUCrxSubband@@PEAUCrxQStep@@@Z; crxDecodeLineWithIQuantization(CrxSubband *,CrxQStep *)
0x18002105c  test    eax, eax
0x18002105e  jnz     loc_1800213AF
0x180021064  mov     rax, [rsp+88h+var_60]
0x180021069  mov     rdx, rbp; struct CrxQStep *
0x18002106c  mov     rcx, [rax]
0x18002106f  add     rcx, r12; struct CrxSubband *
0x180021072  call    ?crxDecodeLineWithIQuantization@@YAHPEAUCrxSubband@@PEAUCrxQStep@@@Z; crxDecodeLineWithIQuantization(CrxSubband *,CrxQStep *)
0x180021077  test    eax, eax
0x180021079  jnz     loc_1800213AF
0x18002107f  cmp     word ptr [rbx+68h], 1
0x180021084  mov     r10, [rbx+10h]
0x180021088  mov     r11, [rbx+18h]
0x18002108c  jg      short loc_180021098
0x18002108e  mov     eax, [r10]
0x180021091  mov     [rsi], eax
0x180021093  jmp     loc_180021179
0x180021098  mov     r13, [rsp+88h+arg_0]
0x1800210a0  mov     ebp, [r10]
0x1800210a3  test    byte ptr [r13+34h], 2
0x1800210a8  jz      short loc_1800210BF
0x1800210aa  mov     edx, [r11]
0x1800210ad  add     edx, 2
0x1800210b0  add     edx, [r11+4]
0x1800210b4  sar     edx, 2
0x1800210b7  sub     ebp, edx
0x1800210b9  add     r11, 4
0x1800210bd  jmp     short loc_1800210C8
0x1800210bf  mov     eax, [r11]
0x1800210c2  inc     eax
0x1800210c4  sar     eax, 1
0x1800210c6  sub     ebp, eax
0x1800210c8  mov     [rsi], ebp
0x1800210ca  add     r10, 4
0x1800210ce  movsx   ecx, word ptr [rbx+68h]
0x1800210d2  xor     r12d, r12d
0x1800210d5  lea     eax, [rcx-3]
0x1800210d8  test    eax, eax
0x1800210da  jle     short loc_180021121
0x1800210dc  nop     dword ptr [rax+00h]
0x1800210e0  mov     ecx, [r11+4]
0x1800210e4  add     r12d, 2
0x1800210e8  mov     r8d, [r10]
0x1800210eb  add     ecx, 2
0x1800210ee  add     ecx, [r11]
0x1800210f1  add     r10, 4
0x1800210f5  sar     ecx, 2
0x1800210f8  sub     r8d, ecx
0x1800210fb  lea     eax, [r8+rbp]
0x1800210ff  mov     ebp, r8d
0x180021102  sar     eax, 1
0x180021104  add     eax, [r11]
0x180021107  add     r11, 4
0x18002110b  mov     [rsi+4], eax
0x18002110e  add     rsi, 8
0x180021112  mov     [rsi], r8d
0x180021115  movsx   ecx, word ptr [rbx+68h]
0x180021119  lea     eax, [rcx-3]
0x18002111c  cmp     r12d, eax
0x18002111f  jl      short loc_1800210E0
0x180021121  test    byte ptr [r13+34h], 1
0x180021126  mov     edx, [r11]
0x180021129  jz      short loc_180021153
0x18002112b  mov     r8d, [r10]
0x18002112e  lea     ecx, [rdx+2]
0x180021131  add     ecx, [r11+4]
0x180021135  sar     ecx, 2
0x180021138  sub     r8d, ecx
0x18002113b  mov     ecx, [rsi]
0x18002113d  add     ecx, r8d
0x180021140  sar     ecx, 1
0x180021142  add     ecx, edx
0x180021144  mov     [rsi+4], ecx
0x180021147  test    byte ptr [rbx+68h], 1
0x18002114b  jz      short loc_180021179
0x18002114d  mov     [rsi+8], r8d
0x180021151  jmp     short loc_180021179
0x180021153  test    cl, 1
0x180021156  jz      short loc_180021172
0x180021158  mov     ecx, [r10]
0x18002115b  lea     eax, [rdx+1]
0x18002115e  sar     eax, 1
0x180021160  sub     ecx, eax
0x180021162  mov     eax, [rsi]
0x180021164  add     eax, ecx
0x180021166  mov     [rsi+8], ecx
0x180021169  sar     eax, 1
0x18002116b  add     eax, edx
0x18002116d  mov     [rsi+4], eax
0x180021170  jmp     short loc_180021179
0x180021172  mov     ecx, [rsi]
0x180021174  add     ecx, edx
0x180021176  mov     [rsi+4], ecx
0x180021179  xor     r12d, r12d
0x18002117c  mov     r8d, r12d
0x18002117f  cmp     r12w, [rbx+68h]
0x180021184  jge     short loc_1800211FE
0x180021186  sub     rsi, r14
0x180021189  sub     rdi, r14
0x18002118c  sub     r15, r14
0x18002118f  nop
0x180021190  mov     edx, [r14]
0x180021193  inc     r8d
0x180021196  mov     eax, [r14+rdi]
0x18002119a  lea     r14, [r14+4]
0x18002119e  add     edx, 2
0x1800211a1  add     edx, [rsi+r14-4]
0x1800211a6  sar     edx, 2
0x1800211a9  sub     eax, edx
0x1800211ab  mov     [r14+r15-4], eax
0x1800211b0  movsx   eax, word ptr [rbx+68h]
0x1800211b4  cmp     r8d, eax
0x1800211b7  jl      short loc_180021190
0x1800211b9  jmp     short loc_1800211FE
0x1800211bb  mov     rdx, rsi; int *
0x1800211be  call    ?crxHorizontal53@@YAXPEAH0PEAUCrxWaveletTransform@@I@Z; crxHorizontal53(int *,int *,CrxWaveletTransform *,uint)
0x1800211c3  xor     r12d, r12d
0x1800211c6  mov     edx, r12d
0x1800211c9  cmp     r12w, [rbx+68h]
0x1800211ce  jge     short loc_1800211FE
0x1800211d0  sub     rsi, rdi
0x1800211d3  sub     r15, rdi
0x1800211d6  nop     word ptr [rax+rax+00000000h]
0x1800211e0  mov     ecx, [rdi+rsi]
0x1800211e3  inc     edx
0x1800211e5  mov     eax, [rdi]
0x1800211e7  lea     rdi, [rdi+4]
0x1800211eb  inc     ecx
0x1800211ed  sar     ecx, 1
0x1800211ef  sub     eax, ecx
0x1800211f1  mov     [rdi+r15-4], eax
0x1800211f6  movsx   eax, word ptr [rbx+68h]
0x1800211fa  cmp     edx, eax
0x1800211fc  jl      short loc_1800211E0
0x1800211fe  mov     r14, [rsp+88h+arg_0]
0x180021206  mov     edi, [rsp+88h+arg_18]
0x18002120d  mov     rcx, r14; struct CrxPlaneComp *
0x180021210  mov     r8, [rsp+88h+arg_10]; struct CrxQStep *
0x180021218  mov     edx, edi; int
0x18002121a  call    ?crxIdwt53FilterDecode@@YAHPEAUCrxPlaneComp@@HPEAUCrxQStep@@@Z; crxIdwt53FilterDecode(CrxPlaneComp *,int,CrxQStep *)
0x18002121f  test    eax, eax
0x180021221  jnz     loc_1800213AF
0x180021227  mov     edx, edi; unsigned int
0x180021229  mov     rcx, r14; struct CrxPlaneComp *
0x18002122c  call    ?crxIdwt53FilterTransform@@YAHPEAUCrxPlaneComp@@I@Z; crxIdwt53FilterTransform(CrxPlaneComp *,uint)
0x180021231  test    eax, eax
0x180021233  jnz     loc_1800213AF
0x180021239  mov     rsi, [rsp+88h+var_60]
0x18002123e  jmp     loc_180021362
0x180021243  call    ?crxDecodeLineWithIQuantization@@YAHPEAUCrxSubband@@PEAUCrxQStep@@@Z; crxDecodeLineWithIQuantization(CrxSubband *,CrxQStep *)
0x180021248  test    eax, eax
0x18002124a  jnz     loc_1800213AF
0x180021250  cmp     word ptr [rbx+68h], 1
0x180021255  mov     r10, [rbx]
0x180021258  mov     rcx, [rbx+8]
0x18002125c  jg      short loc_180021269
0x18002125e  mov     eax, [r10]
0x180021261  mov     [r15], eax
0x180021264  jmp     loc_180021335
0x180021269  test    byte ptr [r14+34h], 2
0x18002126e  mov     r11d, [r10]
0x180021271  jz      short loc_18002128C
0x180021273  mov     edx, [rcx+4]
0x180021276  lea     r8, [rcx+4]
0x18002127a  mov     ecx, [rcx]
0x18002127c  add     ecx, 2
0x18002127f  add     edx, ecx
0x180021281  mov     rcx, r8
0x180021284  sar     edx, 2
0x180021287  sub     r11d, edx
0x18002128a  jmp     short loc_180021295
0x18002128c  mov     eax, [rcx]
0x18002128e  inc     eax
0x180021290  sar     eax, 1
0x180021292  sub     r11d, eax
0x180021295  mov     [r15], r11d
0x180021298  add     r10, 4
0x18002129c  movsx   edx, word ptr [rbx+68h]
0x1800212a0  mov     edi, r12d
0x1800212a3  lea     eax, [rdx-3]
0x1800212a6  test    eax, eax
0x1800212a8  jle     short loc_1800212F3
0x1800212aa  nop     word ptr [rax+rax+00h]
0x1800212b0  mov     edx, [rcx]
0x1800212b2  lea     r9, [rcx+4]
0x1800212b6  mov     ecx, [rcx+4]
0x1800212b9  add     edi, 2
0x1800212bc  mov     r8d, [r10]
  ... truncated ...
```
