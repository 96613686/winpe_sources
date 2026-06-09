# InterlaceLumaError_Daytona

- ea: `0x1800254a0`
- end: `0x180025753`
- name: `InterlaceLumaError_Daytona`
- size: `691`
- prototype: ``
- caller_count: `4`
- callee_count: `1`
- tags: ``

## callers

- `0x180004470`
- `0x18000bbd4`
- `0x18000ca20`
- `0x180017a40`

## callees

- `0x1800254a0`

## pseudocode

```c
__int64 __fastcall InterlaceLumaError_Daytona(_OWORD *a1, _OWORD *a2, _OWORD *a3, _OWORD *a4)
{
  int i; // r8d
  __int64 v7; // rdx
  int v8; // eax
  int j; // r8d
  __int64 v10; // rdx
  int v11; // eax
  int k; // r8d
  __int64 v13; // rdx
  int v14; // eax
  int m; // r8d
  __int64 v16; // rdx
  int v17; // eax
  int n; // r8d
  __int64 v19; // rdx
  int v20; // eax
  int ii; // r8d
  __int64 v22; // rdx
  int v23; // eax
  int jj; // r8d
  __int64 v25; // rdx
  int v26; // eax
  int kk; // r8d
  __int64 v28; // rdx
  __int64 result; // rax
  __int128 v30; // xmm1
  __int128 v31; // xmm0
  __int128 v32; // xmm1
  __int128 v33; // xmm0
  __int128 v34; // xmm1
  __int128 v35; // xmm0
  __int128 v36; // xmm1
  __int128 v37; // xmm0
  __int128 v38; // xmm1
  __int128 v39; // xmm0
  __int128 v40; // xmm1
  __int128 v41; // xmm0
  __int128 v42; // xmm1
  __int128 v43; // xmm0
  __int128 v44; // xmm1
  __int128 v45; // xmm0
  __int128 v46; // xmm1
  __int128 v47; // xmm0
  __int128 v48; // xmm1
  __int128 v49; // xmm0
  __int128 v50; // xmm1
  __int128 v51; // xmm0
  __int128 v52; // xmm1
  __int128 v53; // [rsp+0h] [rbp-100h]
  _OWORD v54[7]; // [rsp+10h] [rbp-F0h]
  __int128 v55; // [rsp+80h] [rbp-80h]
  _OWORD v56[7]; // [rsp+90h] [rbp-70h]
  __int128 v57; // [rsp+100h] [rbp+0h]
  _OWORD v58[7]; // [rsp+110h] [rbp+10h]
  __int128 v59; // [rsp+180h] [rbp+80h]
  _OWORD v60[8]; // [rsp+190h] [rbp+90h]

  for ( i = 0; i < 4; ++i )
  {
    v7 = i;
    v8 = 2 * i;
    v54[v8 - 1] = a1[v7];
  }
  for ( j = 0; j < 4; ++j )
  {
    v10 = j;
    v11 = 2 * j;
    v56[v11 - 1] = a2[v10];
  }
  for ( k = 0; k < 4; ++k )
  {
    v13 = 8 * k + 32;
    v14 = 2 * k;
    v58[v14 - 1] = *(_OWORD *)((char *)a1 + 2 * v13);
  }
  for ( m = 0; m < 4; ++m )
  {
    v16 = 8 * m + 32;
    v17 = 2 * m;
    v60[v17 - 1] = *(_OWORD *)((char *)a2 + 2 * v16);
  }
  for ( n = 0; n < 4; ++n )
  {
    v19 = n;
    v20 = 2 * n;
    v54[v20] = a3[v19];
  }
  for ( ii = 0; ii < 4; ++ii )
  {
    v22 = ii;
    v23 = 2 * ii;
    v56[v23] = a4[v22];
  }
  for ( jj = 0; jj < 4; ++jj )
  {
    v25 = 8 * jj + 32;
    v26 = 2 * jj;
    v58[v26] = *(_OWORD *)((char *)a3 + 2 * v25);
  }
  for ( kk = 0; kk < 4; ++kk )
  {
    v28 = 8 * kk + 32;
    result = (unsigned int)(16 * kk);
    *(_OWORD *)((char *)v60 + 2 * (int)result) = *(_OWORD *)((char *)a4 + 2 * v28);
  }
  *a1 = v53;
  a1[1] = v54[0];
  a1[2] = v54[1];
  a1[3] = v54[2];
  a1[4] = v54[3];
  a1[5] = v54[4];
  a1[6] = v54[5];
  a1[7] = v54[6];
  v30 = v56[0];
  *a2 = v55;
  v31 = v56[1];
  a2[1] = v30;
  v32 = v56[2];
  a2[2] = v31;
  v33 = v56[3];
  a2[3] = v32;
  v34 = v56[4];
  a2[4] = v33;
  v35 = v56[5];
  a2[5] = v34;
  v36 = v56[6];
  a2[6] = v35;
  v37 = v57;
  a2[7] = v36;
  v38 = v58[0];
  *a3 = v37;
  v39 = v58[1];
  a3[1] = v38;
  v40 = v58[2];
  a3[2] = v39;
  v41 = v58[3];
  a3[3] = v40;
  v42 = v58[4];
  a3[4] = v41;
  v43 = v58[5];
  a3[5] = v42;
  v44 = v58[6];
  a3[6] = v43;
  v45 = v59;
  a3[7] = v44;
  v46 = v60[0];
  *a4 = v45;
  v47 = v60[1];
  a4[1] = v46;
  v48 = v60[2];
  a4[2] = v47;
  v49 = v60[3];
  a4[3] = v48;
  v50 = v60[4];
  a4[4] = v49;
  v51 = v60[5];
  a4[5] = v50;
  v52 = v60[6];
  a4[6] = v51;
  a4[7] = v52;
  return result;
}

```

## disassembly

```asm
0x1800254a0  push    rbp
0x1800254a2  push    rbx
0x1800254a3  lea     rbp, [rsp-108h]
0x1800254ab  sub     rsp, 208h
0x1800254b2  mov     r10, r8
0x1800254b5  mov     r11, rdx
0x1800254b8  xor     r8d, r8d
0x1800254bb  mov     rbx, rcx
0x1800254be  lea     eax, ds:0[r8*8]
0x1800254c6  movsxd  rdx, eax
0x1800254c9  mov     eax, r8d
0x1800254cc  shl     eax, 4
0x1800254cf  inc     r8d
0x1800254d2  movsxd  rcx, eax
0x1800254d5  movups  xmm0, xmmword ptr [rbx+rdx*2]
0x1800254d9  movdqu  [rsp+rcx*2+210h+var_210], xmm0
0x1800254de  cmp     r8d, 4
0x1800254e2  jl      short loc_1800254BE
0x1800254e4  xor     r8d, r8d
0x1800254e7  lea     eax, ds:0[r8*8]
0x1800254ef  movsxd  rdx, eax
0x1800254f2  mov     eax, r8d
0x1800254f5  shl     eax, 4
0x1800254f8  inc     r8d
0x1800254fb  movsxd  rcx, eax
0x1800254fe  movups  xmm0, xmmword ptr [r11+rdx*2]
0x180025503  movdqu  [rbp+rcx*2+110h+var_190], xmm0
0x180025509  cmp     r8d, 4
0x18002550d  jl      short loc_1800254E7
0x18002550f  xor     r8d, r8d
0x180025512  lea     eax, ds:20h[r8*8]
0x18002551a  movsxd  rdx, eax
0x18002551d  mov     eax, r8d
0x180025520  shl     eax, 4
0x180025523  inc     r8d
0x180025526  movsxd  rcx, eax
0x180025529  movups  xmm0, xmmword ptr [rbx+rdx*2]
0x18002552d  movdqu  [rbp+rcx*2+110h+var_110], xmm0
0x180025533  cmp     r8d, 4
0x180025537  jl      short loc_180025512
0x180025539  xor     r8d, r8d
0x18002553c  lea     eax, ds:20h[r8*8]
0x180025544  movsxd  rdx, eax
0x180025547  mov     eax, r8d
0x18002554a  shl     eax, 4
0x18002554d  inc     r8d
0x180025550  movsxd  rcx, eax
0x180025553  movups  xmm0, xmmword ptr [r11+rdx*2]
0x180025558  movdqu  [rbp+rcx*2+110h+var_90], xmm0
0x180025561  cmp     r8d, 4
0x180025565  jl      short loc_18002553C
0x180025567  xor     r8d, r8d
0x18002556a  lea     eax, ds:0[r8*8]
0x180025572  movsxd  rdx, eax
0x180025575  mov     eax, r8d
0x180025578  shl     eax, 4
0x18002557b  inc     r8d
0x18002557e  movsxd  rcx, eax
0x180025581  movups  xmm0, xmmword ptr [r10+rdx*2]
0x180025586  movdqu  [rsp+rcx*2+210h+var_200], xmm0
0x18002558c  cmp     r8d, 4
0x180025590  jl      short loc_18002556A
0x180025592  xor     r8d, r8d
0x180025595  lea     eax, ds:0[r8*8]
0x18002559d  movsxd  rdx, eax
0x1800255a0  mov     eax, r8d
0x1800255a3  shl     eax, 4
0x1800255a6  inc     r8d
0x1800255a9  movsxd  rcx, eax
0x1800255ac  movups  xmm0, xmmword ptr [r9+rdx*2]
0x1800255b1  movdqu  [rbp+rcx*2+110h+var_180], xmm0
0x1800255b7  cmp     r8d, 4
0x1800255bb  jl      short loc_180025595
0x1800255bd  xor     r8d, r8d
0x1800255c0  lea     eax, ds:20h[r8*8]
0x1800255c8  movsxd  rdx, eax
0x1800255cb  mov     eax, r8d
0x1800255ce  shl     eax, 4
0x1800255d1  inc     r8d
0x1800255d4  movsxd  rcx, eax
0x1800255d7  movups  xmm0, xmmword ptr [r10+rdx*2]
0x1800255dc  movdqu  [rbp+rcx*2+110h+var_100], xmm0
0x1800255e2  cmp     r8d, 4
0x1800255e6  jl      short loc_1800255C0
0x1800255e8  xor     r8d, r8d
0x1800255eb  lea     eax, ds:20h[r8*8]
0x1800255f3  movsxd  rdx, eax
0x1800255f6  mov     eax, r8d
0x1800255f9  shl     eax, 4
0x1800255fc  inc     r8d
0x1800255ff  movsxd  rcx, eax
0x180025602  movups  xmm0, xmmword ptr [r9+rdx*2]
0x180025607  movdqu  [rbp+rcx*2+110h+var_80], xmm0
0x180025610  cmp     r8d, 4
0x180025614  jl      short loc_1800255EB
0x180025616  movaps  xmm0, [rsp+210h+var_210]
0x18002561a  movups  xmmword ptr [rbx], xmm0
0x18002561d  movaps  xmm1, [rsp+210h+var_200]
0x180025622  movups  xmmword ptr [rbx+10h], xmm1
0x180025626  movaps  xmm0, [rsp+210h+var_1F0]
0x18002562b  movups  xmmword ptr [rbx+20h], xmm0
0x18002562f  movaps  xmm1, [rsp+210h+var_1E0]
0x180025634  movups  xmmword ptr [rbx+30h], xmm1
0x180025638  movaps  xmm0, [rsp+210h+var_1D0]
0x18002563d  movups  xmmword ptr [rbx+40h], xmm0
0x180025641  movaps  xmm1, [rsp+210h+var_1C0]
0x180025646  movups  xmmword ptr [rbx+50h], xmm1
0x18002564a  movaps  xmm0, [rsp+210h+var_1B0]
0x18002564f  movups  xmmword ptr [rbx+60h], xmm0
0x180025653  movaps  xmm1, [rsp+210h+var_1A0]
0x180025658  movups  xmmword ptr [rbx+70h], xmm1
0x18002565c  movaps  xmm0, [rbp+110h+var_190]
0x180025660  movaps  xmm1, [rbp+110h+var_180]
0x180025664  movups  xmmword ptr [r11], xmm0
0x180025668  movaps  xmm0, [rbp+110h+var_170]
0x18002566c  movups  xmmword ptr [r11+10h], xmm1
0x180025671  movaps  xmm1, [rbp+110h+var_160]
0x180025675  movups  xmmword ptr [r11+20h], xmm0
0x18002567a  movaps  xmm0, [rbp+110h+var_150]
0x18002567e  movups  xmmword ptr [r11+30h], xmm1
0x180025683  movaps  xmm1, [rbp+110h+var_140]
0x180025687  movups  xmmword ptr [r11+40h], xmm0
0x18002568c  movaps  xmm0, [rbp+110h+var_130]
0x180025690  movups  xmmword ptr [r11+50h], xmm1
0x180025695  movaps  xmm1, [rbp+110h+var_120]
0x180025699  movups  xmmword ptr [r11+60h], xmm0
0x18002569e  movaps  xmm0, [rbp+110h+var_110]
0x1800256a2  movups  xmmword ptr [r11+70h], xmm1
0x1800256a7  movaps  xmm1, [rbp+110h+var_100]
0x1800256ab  movups  xmmword ptr [r10], xmm0
0x1800256af  movaps  xmm0, [rbp+110h+var_F0]
0x1800256b3  movups  xmmword ptr [r10+10h], xmm1
0x1800256b8  movaps  xmm1, [rbp+110h+var_E0]
0x1800256bc  movups  xmmword ptr [r10+20h], xmm0
0x1800256c1  movaps  xmm0, [rbp+110h+var_D0]
0x1800256c5  movups  xmmword ptr [r10+30h], xmm1
0x1800256ca  movaps  xmm1, [rbp+110h+var_C0]
0x1800256ce  movups  xmmword ptr [r10+40h], xmm0
0x1800256d3  movaps  xmm0, [rbp+110h+var_B0]
0x1800256d7  movups  xmmword ptr [r10+50h], xmm1
0x1800256dc  movaps  xmm1, [rbp+110h+var_A0]
0x1800256e0  movups  xmmword ptr [r10+60h], xmm0
0x1800256e5  movaps  xmm0, [rbp+110h+var_90]
0x1800256ec  movups  xmmword ptr [r10+70h], xmm1
0x1800256f1  movaps  xmm1, [rbp+110h+var_80]
0x1800256f8  movups  xmmword ptr [r9], xmm0
0x1800256fc  movaps  xmm0, [rbp+110h+var_70]
0x180025703  movups  xmmword ptr [r9+10h], xmm1
0x180025708  movaps  xmm1, [rbp+110h+var_60]
0x18002570f  movups  xmmword ptr [r9+20h], xmm0
0x180025714  movaps  xmm0, [rbp+110h+var_50]
0x18002571b  movups  xmmword ptr [r9+30h], xmm1
0x180025720  movaps  xmm1, [rbp+110h+var_40]
0x180025727  movups  xmmword ptr [r9+40h], xmm0
0x18002572c  movaps  xmm0, [rbp+110h+var_30]
0x180025733  movups  xmmword ptr [r9+50h], xmm1
0x180025738  movaps  xmm1, [rbp+110h+var_20]
0x18002573f  movups  xmmword ptr [r9+60h], xmm0
0x180025744  movups  xmmword ptr [r9+70h], xmm1
0x180025749  add     rsp, 208h
0x180025750  pop     rbx
0x180025751  pop     rbp
0x180025752  retn
```
