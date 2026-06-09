# GeoBundle::UpdateNextCascadeCost(void)

- ea: `0x100429520`
- end: `0x1004297f7`
- name: `?UpdateNextCascadeCost@GeoBundle@@QEAAXXZ`
- size: `727`
- prototype: `void __fastcall(GeoBundle *__hidden this)`
- caller_count: `2`
- callee_count: `2`
- tags: `installer_update`

## callers

- `0x100412450`
- `0x1004130f0`

## callees

- `0x100429520`
- `0x100469ae0`

## pseudocode

```c
void __fastcall GeoBundle::UpdateNextCascadeCost(GeoBundle *this)
{
  __int64 v2; // r11
  double *v3; // r9
  double *v4; // r8
  int v5; // r10d
  __int64 v6; // rcx
  double *v7; // rax
  double v8; // xmm6_8
  __int64 v9; // rdx
  int v10; // eax
  int v11; // r8d
  double v12; // xmm1_8
  double v13; // xmm9_8
  double v14; // xmm0_8
  double v15; // xmm8_8
  unsigned __int64 v16; // rax
  double v17; // xmm1_8
  unsigned __int64 v18; // rdi
  double v19; // xmm6_8
  double v20; // xmm6_8
  unsigned __int64 v21; // rax
  double v22; // xmm9_8
  double v23; // xmm0_8
  unsigned __int64 v24; // rax
  double v25; // xmm9_8
  double v26; // xmm8_8
  unsigned __int64 v27; // rax

  if ( (*(_BYTE *)this & 4) == 0 )
    return;
  v2 = *((int *)this + 20);
  v3 = (double *)qword_10047B3A0;
  v4 = (double *)qword_10047B3A0;
  v5 = 0;
  while ( 1 )
  {
    v6 = 0;
    if ( (int)v2 > 0 )
    {
      v7 = (double *)*((_QWORD *)this + 9);
      while ( *v7 != *v4 )
      {
        ++v6;
        ++v7;
        if ( v6 >= v2 )
          goto LABEL_7;
      }
      goto LABEL_11;
    }
LABEL_7:
    v8 = *v4;
    if ( (*v4 >= 0.0 || *(_QWORD *)(*((_QWORD *)this + 11) + 16LL))
      && (v8 <= 0.0 || *(_QWORD *)(*((_QWORD *)this + 11) + 24LL)) )
    {
      break;
    }
LABEL_11:
    ++v5;
    ++v4;
    if ( v5 >= 4 )
      goto LABEL_14;
  }
  if ( v8 == 0.0 )
  {
LABEL_14:
    *(_QWORD *)(*((_QWORD *)this + 11) + 48LL) = -1;
    *(_QWORD *)(*((_QWORD *)this + 11) + 56LL) = -1;
    return;
  }
  v9 = *((_QWORD *)this + 1);
  v10 = 0;
  v11 = *(_DWORD *)(v9 + 8);
  while ( *v3 != v8 )
  {
    ++v10;
    if ( (__int64)++v3 >= (__int64)&CHAIN_SELF_REDUNDANT )
    {
      v12 = 0.0;
      goto LABEL_19;
    }
  }
  v12 = *(double *)&qword_10047B380[v10];
LABEL_19:
  v13 = (double)v11;
  v14 = (double)v11 * v12;
  v15 = (double)(int)v14;
  v16 = 0;
  v17 = (double)v11 * 43.904 + v15 * 18.688 + (double)(v11 * (int)v14) * 0.00074496;
  if ( v17 >= 9.223372036854776e18 )
  {
    v17 = v17 - 9.223372036854776e18;
    if ( v17 < 9.223372036854776e18 )
      v16 = 0x8000000000000000uLL;
  }
  v18 = v16 + (unsigned int)(int)v17;
  if ( *(_BYTE *)(*(_QWORD *)(v9 + 48) + 8LL) == 7 || v8 >= 0.0 && *(_DWORD *)(v9 + 56) != 1 )
  {
    v22 = pow_0(v13, 1.065313790904282);
    v23 = pow_0(v8, -0.1353867974684922);
    v24 = 0;
    v25 = v22 * (v23 * 0.030859454619738);
    if ( v25 >= 9.223372036854776e18 )
    {
      v25 = v25 - 9.223372036854776e18;
      if ( v25 < 9.223372036854776e18 )
        v24 = 0x8000000000000000uLL;
    }
    v26 = v15 * 1.60679168;
    *(_QWORD *)(*((_QWORD *)this + 11) + 48LL) = v18 + v24 + (unsigned int)(int)v25;
    v27 = 0;
    if ( v26 >= 9.223372036854776e18 )
    {
      v26 = v26 - 9.223372036854776e18;
      if ( v26 < 9.223372036854776e18 )
        v27 = 0x8000000000000000uLL;
    }
    *(_QWORD *)(*((_QWORD *)this + 11) + 56LL) = v18 + v27 + (unsigned int)(int)v26;
  }
  else
  {
    v19 = pow_0(v8, -0.02954677305975792) * 0.1776789890524849;
    v20 = v19 * pow_0(v13, 0.9608922274934082);
    v21 = 0;
    if ( v20 >= 9.223372036854776e18 )
    {
      v20 = v20 - 9.223372036854776e18;
      if ( v20 < 9.223372036854776e18 )
        v21 = 0x8000000000000000uLL;
    }
    *(_QWORD *)(*((_QWORD *)this + 11) + 48LL) = v18 + v21 + (unsigned int)(int)v20;
    *(_QWORD *)(*((_QWORD *)this + 11) + 56LL) = 0;
  }
}

```

## disassembly

```asm
0x100429520  push    rbx
0x100429522  sub     rsp, 60h
0x100429526  test    byte ptr [rcx], 4
0x100429529  mov     rbx, rcx
0x10042952c  jz      loc_1004297F1
0x100429532  movsxd  r11, dword ptr [rcx+50h]
0x100429536  lea     r9, qword_10047B3A0
0x10042953d  mov     r8, r9
0x100429540  movaps  [rsp+68h+var_18], xmm6
0x100429545  xor     r10d, r10d
0x100429548  xorps   xmm2, xmm2
0x10042954b  nop     dword ptr [rax+rax+00h]
0x100429550  xor     ecx, ecx
0x100429552  test    r11d, r11d
0x100429555  jle     short loc_100429578
0x100429557  movsd   xmm1, qword ptr [r8]
0x10042955c  mov     rax, [rbx+48h]
0x100429560  movsd   xmm0, qword ptr [rax]
0x100429564  ucomisd xmm0, xmm1
0x100429568  jp      short loc_10042956C
0x10042956a  jz      short loc_10042959F
0x10042956c  inc     rcx
0x10042956f  add     rax, 8
0x100429573  cmp     rcx, r11
0x100429576  jl      short loc_100429560
0x100429578  movsd   xmm6, qword ptr [r8]
0x10042957d  comisd  xmm2, xmm6
0x100429581  jbe     short loc_10042958E
0x100429583  mov     rax, [rbx+58h]
0x100429587  cmp     qword ptr [rax+10h], 0
0x10042958c  jz      short loc_10042959F
0x10042958e  comisd  xmm6, xmm2
0x100429592  jbe     short loc_1004295AE
0x100429594  mov     rax, [rbx+58h]
0x100429598  cmp     qword ptr [rax+18h], 0
0x10042959d  jnz     short loc_1004295AE
0x10042959f  inc     r10d
0x1004295a2  add     r8, 8
0x1004295a6  cmp     r10d, 4
0x1004295aa  jl      short loc_100429550
0x1004295ac  jmp     short loc_1004295B6
0x1004295ae  ucomisd xmm6, xmm2
0x1004295b2  jp      short loc_1004295D9
0x1004295b4  jnz     short loc_1004295D9
0x1004295b6  mov     rax, [rbx+58h]
0x1004295ba  movaps  xmm6, [rsp+68h+var_18]
0x1004295bf  mov     qword ptr [rax+30h], 0FFFFFFFFFFFFFFFFh
0x1004295c7  mov     rax, [rbx+58h]
0x1004295cb  mov     qword ptr [rax+38h], 0FFFFFFFFFFFFFFFFh
0x1004295d3  add     rsp, 60h
0x1004295d7  pop     rbx
0x1004295d8  retn
0x1004295d9  mov     rdx, [rbx+8]
0x1004295dd  lea     rcx, ?CHAIN_SELF_REDUNDANT@@3GB; ushort const CHAIN_SELF_REDUNDANT
0x1004295e4  mov     [rsp+68h+arg_0], rsi
0x1004295e9  xor     eax, eax
0x1004295eb  mov     [rsp+68h+arg_8], rdi
0x1004295f0  movaps  [rsp+68h+var_28], xmm7
0x1004295f5  mov     r8d, [rdx+8]
0x1004295f9  movaps  [rsp+68h+var_38], xmm8
0x1004295ff  movaps  [rsp+68h+var_48], xmm9
0x100429605  movsd   xmm0, qword ptr [r9]
0x10042960a  ucomisd xmm0, xmm6
0x10042960e  jp      short loc_100429616
0x100429610  jz      loc_10042972D
0x100429616  inc     eax
0x100429618  add     r9, 8
0x10042961c  cmp     r9, rcx
0x10042961f  jl      short loc_100429605
0x100429621  movaps  xmm1, xmm2
0x100429624  movsd   xmm7, cs:__real@43e0000000000000
0x10042962c  xorps   xmm9, xmm9
0x100429630  cvtsi2sd xmm9, r8
0x100429635  mov     rsi, 8000000000000000h
0x10042963f  xorps   xmm8, xmm8
0x100429643  movaps  xmm0, xmm9
0x100429647  mulsd   xmm0, xmm1
0x10042964b  movaps  xmm1, xmm9
0x10042964f  mulsd   xmm1, cs:__real@4045f3b645a1cac1
0x100429657  cvttsd2si rcx, xmm0
0x10042965c  mov     eax, ecx
0x10042965e  imul    ecx, r8d
0x100429662  cvtsi2sd xmm8, rax
0x100429667  mov     eax, ecx
0x100429669  movaps  xmm0, xmm8
0x10042966d  mulsd   xmm0, cs:__real@4032b020c49ba5e3
0x100429675  addsd   xmm1, xmm0
0x100429679  xorps   xmm0, xmm0
0x10042967c  cvtsi2sd xmm0, rax
0x100429681  xor     eax, eax
0x100429683  mulsd   xmm0, cs:__real@3f48692d6b1d2f66
0x10042968b  addsd   xmm1, xmm0
0x10042968f  comisd  xmm1, xmm7
0x100429693  jb      short loc_1004296A2
0x100429695  subsd   xmm1, xmm7
0x100429699  comisd  xmm1, xmm7
0x10042969d  jnb     short loc_1004296A2
0x10042969f  mov     rax, rsi
0x1004296a2  cvttsd2si rdi, xmm1
0x1004296a7  add     rdi, rax
0x1004296aa  mov     rax, [rdx+30h]
0x1004296ae  cmp     byte ptr [rax+8], 7
0x1004296b2  jz      loc_100429740
0x1004296b8  comisd  xmm2, xmm6
0x1004296bc  ja      short loc_1004296C4
0x1004296be  cmp     dword ptr [rdx+38h], 1
0x1004296c2  jnz     short loc_100429740
0x1004296c4  movsd   xmm1, cs:__real@bf9e41825ff9d998; Y
0x1004296cc  movaps  xmm0, xmm6; X
0x1004296cf  call    pow_0
0x1004296d4  movsd   xmm1, cs:__real@3feebfa10e8212ae; Y
0x1004296dc  movaps  xmm6, xmm0
0x1004296df  mulsd   xmm6, cs:__real@3fc6be2f6395588b
0x1004296e7  movaps  xmm0, xmm9; X
0x1004296eb  call    pow_0
0x1004296f0  mulsd   xmm6, xmm0
0x1004296f4  xor     eax, eax
0x1004296f6  comisd  xmm6, xmm7
0x1004296fa  jb      short loc_100429709
0x1004296fc  subsd   xmm6, xmm7
0x100429700  comisd  xmm6, xmm7
0x100429704  jnb     short loc_100429709
0x100429706  mov     rax, rsi
0x100429709  cvttsd2si rcx, xmm6
0x10042970e  add     rcx, rax
0x100429711  mov     rax, [rbx+58h]
0x100429715  add     rcx, rdi
0x100429718  mov     [rax+30h], rcx
0x10042971c  mov     rax, [rbx+58h]
0x100429720  mov     qword ptr [rax+38h], 0
0x100429728  jmp     loc_1004297D1
0x10042972d  cdqe
0x10042972f  lea     rcx, qword_10047B380
0x100429736  movsd   xmm1, qword ptr [rcx+rax*8]
0x10042973b  jmp     loc_100429624
0x100429740  movsd   xmm1, cs:__real@3ff10b86793e9635; Y
0x100429748  movaps  xmm0, xmm9; X
0x10042974c  call    pow_0
0x100429751  movsd   xmm1, cs:__real@bfc1545ac5b7fb14; Y
0x100429759  movaps  xmm9, xmm0
0x10042975d  movaps  xmm0, xmm6; X
0x100429760  call    pow_0
0x100429765  mulsd   xmm0, cs:__real@3f9f999ef174e932
0x10042976d  xor     eax, eax
0x10042976f  mulsd   xmm9, xmm0
0x100429774  comisd  xmm9, xmm7
0x100429779  jb      short loc_10042978A
0x10042977b  subsd   xmm9, xmm7
0x100429780  comisd  xmm9, xmm7
0x100429785  jnb     short loc_10042978A
0x100429787  mov     rax, rsi
0x10042978a  mulsd   xmm8, cs:__real@3ff9b56b31515bbd
0x100429793  cvttsd2si rcx, xmm9
0x100429798  add     rcx, rax
0x10042979b  mov     rax, [rbx+58h]
0x10042979f  add     rcx, rdi
0x1004297a2  mov     [rax+30h], rcx
0x1004297a6  xor     eax, eax
0x1004297a8  comisd  xmm8, xmm7
0x1004297ad  jb      short loc_1004297BE
0x1004297af  subsd   xmm8, xmm7
0x1004297b4  comisd  xmm8, xmm7
0x1004297b9  jnb     short loc_1004297BE
0x1004297bb  mov     rax, rsi
0x1004297be  cvttsd2si rcx, xmm8
0x1004297c3  add     rcx, rax
0x1004297c6  mov     rax, [rbx+58h]
0x1004297ca  add     rcx, rdi
0x1004297cd  mov     [rax+38h], rcx
0x1004297d1  movaps  xmm8, [rsp+68h+var_38]
0x1004297d7  movaps  xmm7, [rsp+68h+var_28]
0x1004297dc  mov     rsi, [rsp+68h+arg_0]
0x1004297e1  mov     rdi, [rsp+68h+arg_8]
0x1004297e6  movaps  xmm9, [rsp+68h+var_48]
0x1004297ec  movaps  xmm6, [rsp+68h+var_18]
0x1004297f1  add     rsp, 60h
0x1004297f5  pop     rbx
0x1004297f6  retn
```
