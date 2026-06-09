# CSingleSideReducer::FTriangleConflictsWithOtherPoints(CMglPoint<double> const &,CMglPoint<double> const &,CMglPoint<double> const &,CMglPoint<double> const *,bool *,uint,bool)

- ea: `0x100438030`
- end: `0x10043853b`
- name: `?FTriangleConflictsWithOtherPoints@CSingleSideReducer@@AEAA_NAEBV?$CMglPoint@N@@00PEBV2@PEA_NI_N@Z`
- size: `1291`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation`

## callers

- `0x100438550`

## callees

- `0x100437f10`
- `0x100438030`

## pseudocode

```c
char __fastcall CSingleSideReducer::FTriangleConflictsWithOtherPoints(
        __int64 a1,
        double *a2,
        double *a3,
        double *a4,
        __int64 a5,
        __int64 a6,
        unsigned int a7,
        char a8)
{
  double v9; // xmm1_8
  double v14; // xmm11_8
  double v15; // xmm0_8
  double v16; // xmm1_8
  double v17; // xmm3_8
  double v18; // xmm2_8
  double v19; // xmm12_8
  double v20; // xmm10_8
  double v21; // xmm0_8
  double v22; // xmm10_8
  double v23; // xmm11_8
  __int64 v24; // r8
  __int64 v25; // rcx
  __int64 v26; // rdx
  double v27; // xmm0_8
  double *v28; // rax
  __int64 v29; // r9
  char v30; // r13
  unsigned int v31; // edi
  int v32; // ebx
  bool v33; // cc
  int v34; // r11d
  unsigned int v35; // eax
  _BYTE *v36; // rbp
  double *v37; // rbx
  void (*v38)(void); // r10
  double v39; // xmm1_8
  double v40; // xmm0_8
  int v41; // edx
  double v42; // xmm6_8
  double v43; // xmm4_8
  double v44; // xmm5_8
  double v45; // xmm7_8
  double v46; // xmm8_8
  double v47; // xmm1_8
  int v48; // ecx
  double v49; // xmm3_8
  double v50; // xmm1_8
  double v51; // xmm2_8
  int v52; // eax
  double v53; // xmm1_8
  __int64 v54; // rdx
  __int64 v55; // rcx
  __int64 v56; // rdx
  __int64 v57; // rcx
  unsigned __int8 v59; // [rsp+E0h] [rbp+8h]
  unsigned int v60; // [rsp+E8h] [rbp+10h]
  int v61; // [rsp+F0h] [rbp+18h]
  int v62; // [rsp+F8h] [rbp+20h]
  unsigned __int8 v63; // [rsp+100h] [rbp+28h]

  v9 = fmin(*a2, *a3);
  if ( *a4 <= v9 )
    v9 = *a4;
  v14 = *(double *)(a1 + 24);
  v15 = fmax(*a2, *a3);
  v16 = v9 - v14;
  if ( v15 <= *a4 )
    v15 = *a4;
  v17 = a3[1];
  v18 = a4[1];
  v19 = v14 + v15;
  v20 = fmin(a2[1], v17);
  if ( v18 <= v20 )
    v20 = a4[1];
  v21 = fmax(a2[1], v17);
  v22 = v20 - v14;
  if ( v21 <= v18 )
    v21 = a4[1];
  v23 = v14 + v21;
  v24 = 0;
  v25 = 0;
  v26 = a7 - 1;
  if ( (int)v26 < 0 )
    goto LABEL_27;
  while ( 1 )
  {
    v25 = (unsigned int)(((int)v24 + (int)v26) >> 1);
    v27 = *(double *)(a5 + 16LL * (int)v25);
    if ( v16 <= v27 )
      break;
    v24 = (unsigned int)(v25 + 1);
LABEL_14:
    if ( (int)v24 > (int)v26 )
      goto LABEL_27;
  }
  if ( v27 > v16 )
  {
    v26 = (unsigned int)(v25 - 1);
    goto LABEL_14;
  }
  v26 = (int)v25;
  if ( (int)v25 < 4LL )
  {
LABEL_23:
    if ( v26 > 0 )
    {
      v24 = 16 * v26 + a5 - 16;
      do
      {
        if ( *(double *)v24 != v16 )
          break;
        v25 = (unsigned int)(v25 - 1);
        --v26;
        v24 -= 16;
      }
      while ( v26 > 0 );
    }
  }
  else
  {
    v28 = (double *)(a5 + 16 * ((int)v25 - 2LL));
    while ( v28[2] == v16 )
    {
      if ( *v28 != v16 )
      {
        v25 = (unsigned int)(v25 - 1);
        break;
      }
      if ( *(v28 - 2) != v16 )
      {
        v25 = (unsigned int)(v25 - 2);
        break;
      }
      if ( *(v28 - 4) != v16 )
      {
        v25 = (unsigned int)(v25 - 3);
        break;
      }
      v25 = (unsigned int)(v25 - 4);
      v26 -= 4;
      v28 -= 8;
      if ( v26 <= 3 )
        goto LABEL_23;
    }
  }
LABEL_27:
  v29 = 0xFFFFFFFFLL;
  LOBYTE(v26) = 0;
  LOBYTE(v24) = 0;
  v30 = 0;
  v31 = v25 + 1;
  v60 = -1;
  v32 = -1;
  v61 = -1;
  v33 = v16 <= *(double *)(a5 + 16LL * (int)v25);
  v34 = -1;
  v62 = -1;
  v63 = 0;
  v59 = 0;
  if ( v33 )
    v31 = v25;
  if ( v31 >= a7 )
    goto LABEL_76;
  v35 = a7;
  v36 = (_BYTE *)(v31 + a6);
  v37 = (double *)(a5 + 16LL * v31);
  v38 = OSYieldCallback;
  while ( 2 )
  {
    v39 = *v37;
    if ( v19 >= *v37 )
    {
      if ( !*v36 )
      {
        v40 = v37[1];
        if ( v22 <= v40 && v40 <= v23 )
        {
          if ( v39 == *a2 && v40 == a2[1] )
          {
            if ( v30 )
              return 1;
            v29 = v31;
            v60 = v31;
            v30 = 1;
LABEL_70:
            v34 = v61;
LABEL_71:
            ++v31;
            ++v36;
            v37 += 2;
            if ( v31 >= v35 )
              goto LABEL_75;
            continue;
          }
          if ( v39 == *a3 && v40 == a3[1] )
          {
            if ( (_BYTE)v26 )
              return 1;
            v29 = v60;
            LOBYTE(v26) = 1;
            v63 = 1;
            v34 = v31;
            v61 = v31;
            goto LABEL_71;
          }
          if ( v39 == *a4 && v40 == a4[1] )
          {
            if ( (_BYTE)v24 )
              return 1;
            LOBYTE(v24) = 1;
            v62 = v31;
            v59 = 1;
          }
          else
          {
            if ( ++*(_DWORD *)(a1 + 120) > 0x30D40u )
            {
              if ( v38 )
                ((void (__fastcall *)(__int64, __int64, __int64, __int64))v38)(v25, v26, v24, v29);
              *(_DWORD *)(a1 + 120) = 0;
            }
            v41 = 0;
            v42 = v37[1];
            v43 = *a3 - *v37;
            v44 = a3[1] - v42;
            v45 = *a2 - *v37;
            v46 = a2[1] - v42;
            v47 = v43 * v46 - v44 * v45;
            if ( v47 >= 0.0 )
            {
              LOBYTE(v41) = v47 <= 0.0;
              ++v41;
            }
            v48 = 0;
            v49 = *a4 - *v37;
            v50 = a4[1] - v42;
            v51 = v49 * v44 - v50 * v43;
            if ( v51 >= 0.0 )
            {
              LOBYTE(v48) = v51 <= 0.0;
              ++v48;
            }
            v52 = 0;
            v53 = v50 * v45 - v49 * v46;
            if ( v53 >= 0.0 )
            {
              LOBYTE(v52) = v53 <= 0.0;
              ++v52;
            }
            if ( v41 == 2 || v48 == 2 || v52 == 2 || v41 == v48 && v48 == v52 )
              return 1;
            *(_DWORD *)(a1 + 120) += 2;
            if ( (unsigned __int8)CSingleSideReducer::FIsPointCloseToLine(a1, v37, a2, a3)
              || (unsigned __int8)CSingleSideReducer::FIsPointCloseToLine(v55, v54, a3, a4)
              || (unsigned __int8)CSingleSideReducer::FIsPointCloseToLine(v57, v56, a4, a2) )
            {
              return 1;
            }
            v26 = v63;
            v24 = v59;
            v35 = a7;
          }
        }
      }
      v29 = v60;
      goto LABEL_70;
    }
    break;
  }
  LODWORD(v29) = v60;
  v34 = v61;
LABEL_75:
  v32 = v62;
LABEL_76:
  *(_BYTE *)(v34 + a6) = 1;
  if ( a8 )
  {
    *(_BYTE *)((int)v29 + a6) = 1;
    *(_BYTE *)(v32 + a6) = 1;
  }
  return 0;
}

```

## disassembly

```asm
0x100438030  push    rbx
0x100438032  push    rbp
0x100438033  push    rsi
0x100438034  push    rdi
0x100438035  push    r12
0x100438037  push    r13
0x100438039  push    r14
0x10043803b  push    r15
0x10043803d  sub     rsp, 98h
0x100438044  movsd   xmm0, qword ptr [rdx]
0x100438048  mov     r14, r9
0x10043804b  movsd   xmm3, qword ptr [r8]
0x100438050  movaps  xmm1, xmm0
0x100438053  movsd   xmm2, qword ptr [r9]
0x100438058  minsd   xmm1, xmm3
0x10043805c  mov     r10, [rsp+0D8h+arg_20]
0x100438064  mov     r15, r8
0x100438067  movaps  [rsp+0D8h+var_98], xmm10
0x10043806d  mov     r12, rdx
0x100438070  movaps  [rsp+0D8h+var_A8], xmm11
0x100438076  mov     rsi, rcx
0x100438079  movaps  [rsp+0D8h+var_B8], xmm12
0x10043807f  comisd  xmm2, xmm1
0x100438083  ja      short loc_100438088
0x100438085  movaps  xmm1, xmm2
0x100438088  movsd   xmm11, qword ptr [rcx+18h]
0x10043808e  maxsd   xmm0, xmm3
0x100438092  subsd   xmm1, xmm11
0x100438097  comisd  xmm0, xmm2
0x10043809b  ja      short loc_1004380A0
0x10043809d  movaps  xmm0, xmm2
0x1004380a0  movsd   xmm3, qword ptr [r8+8]
0x1004380a6  movaps  xmm12, xmm11
0x1004380aa  movsd   xmm2, qword ptr [r9+8]
0x1004380b0  addsd   xmm12, xmm0
0x1004380b5  movsd   xmm0, qword ptr [rdx+8]
0x1004380ba  movaps  xmm10, xmm0
0x1004380be  minsd   xmm10, xmm3
0x1004380c3  comisd  xmm2, xmm10
0x1004380c8  ja      short loc_1004380CE
0x1004380ca  movaps  xmm10, xmm2
0x1004380ce  maxsd   xmm0, xmm3
0x1004380d2  subsd   xmm10, xmm11
0x1004380d7  comisd  xmm0, xmm2
0x1004380db  ja      short loc_1004380E0
0x1004380dd  movaps  xmm0, xmm2
0x1004380e0  mov     ebp, [rsp+0D8h+arg_30]
0x1004380e7  addsd   xmm11, xmm0
0x1004380ec  xor     r8d, r8d
0x1004380ef  xor     ecx, ecx
0x1004380f1  lea     edx, [rbp-1]
0x1004380f4  test    edx, edx
0x1004380f6  js      loc_1004381DA
0x1004380fc  nop     dword ptr [rax+00h]
0x100438100  lea     ecx, [r8+rdx]
0x100438104  sar     ecx, 1
0x100438106  movsxd  r9, ecx
0x100438109  mov     rax, r9
0x10043810c  add     rax, rax
0x10043810f  movsd   xmm0, qword ptr [r10+rax*8]
0x100438115  comisd  xmm1, xmm0
0x100438119  jbe     short loc_100438121
0x10043811b  lea     r8d, [rcx+1]
0x10043811f  jmp     short loc_10043812A
0x100438121  comisd  xmm0, xmm1
0x100438125  jbe     short loc_100438134
0x100438127  lea     edx, [rcx-1]
0x10043812a  cmp     r8d, edx
0x10043812d  jle     short loc_100438100
0x10043812f  jmp     loc_1004381DA
0x100438134  mov     rdx, r9
0x100438137  cmp     r9, 4
0x10043813b  jl      short loc_1004381AC
0x10043813d  lea     rax, [r9-2]
0x100438141  shl     rax, 4
0x100438145  add     rax, r10
0x100438148  nop     dword ptr [rax+rax+00000000h]
0x100438150  movsd   xmm0, qword ptr [rax+10h]
0x100438155  ucomisd xmm0, xmm1
0x100438159  jp      short loc_1004381DA
0x10043815b  jnz     short loc_1004381DA
0x10043815d  movsd   xmm0, qword ptr [rax]
0x100438161  ucomisd xmm0, xmm1
0x100438165  jp      loc_1004382E4
0x10043816b  jnz     loc_1004382E4
0x100438171  movsd   xmm0, qword ptr [rax-10h]
0x100438176  ucomisd xmm0, xmm1
0x10043817a  jp      loc_1004382DC
0x100438180  jnz     loc_1004382DC
0x100438186  movsd   xmm0, qword ptr [rax-20h]
0x10043818b  ucomisd xmm0, xmm1
0x10043818f  jp      loc_1004382D4
0x100438195  jnz     loc_1004382D4
0x10043819b  sub     ecx, 4
0x10043819e  sub     rdx, 4
0x1004381a2  sub     rax, 40h ; '@'
0x1004381a6  cmp     rdx, 3
0x1004381aa  jg      short loc_100438150
0x1004381ac  test    rdx, rdx
0x1004381af  jle     short loc_1004381DA
0x1004381b1  mov     rax, rdx
0x1004381b4  lea     r8, [r10-10h]
0x1004381b8  shl     rax, 4
0x1004381bc  add     r8, rax
0x1004381bf  movsd   xmm0, qword ptr [r8]
0x1004381c4  ucomisd xmm0, xmm1
0x1004381c8  jp      short loc_1004381DA
0x1004381ca  jnz     short loc_1004381DA
0x1004381cc  dec     ecx
0x1004381ce  dec     rdx
0x1004381d1  sub     r8, 10h
0x1004381d5  test    rdx, rdx
0x1004381d8  jg      short loc_1004381BF
0x1004381da  mov     r9d, 0FFFFFFFFh
0x1004381e0  movaps  [rsp+0D8h+var_58], xmm6
0x1004381e8  xor     dl, dl
0x1004381ea  movaps  [rsp+0D8h+var_68], xmm7
0x1004381ef  xor     r8b, r8b
0x1004381f2  movsxd  rax, ecx
0x1004381f5  add     rax, rax
0x1004381f8  movaps  [rsp+0D8h+var_78], xmm8
0x1004381fe  xor     r13b, r13b
0x100438201  movaps  [rsp+0D8h+var_88], xmm9
0x100438207  lea     edi, [rcx+1]
0x10043820a  mov     [rsp+0D8h+arg_8], r9d
0x100438212  mov     ebx, r9d
0x100438215  mov     [rsp+0D8h+arg_10], r9d
0x10043821d  comisd  xmm1, qword ptr [r10+rax*8]
0x100438223  mov     r11d, r9d
0x100438226  mov     [rsp+0D8h+arg_18], ebx
0x10043822d  mov     byte ptr [rsp+0D8h+arg_20], dl
0x100438234  mov     [rsp+0D8h+arg_0], r8b
0x10043823c  cmovbe  edi, ecx
0x10043823f  cmp     edi, ebp
0x100438241  jnb     loc_1004384D3
0x100438247  mov     rbp, [rsp+0D8h+arg_28]
0x10043824f  xorps   xmm9, xmm9
0x100438253  mov     eax, [rsp+0D8h+arg_30]
0x10043825a  mov     ebx, edi
0x10043825c  add     rbp, rbx
0x10043825f  shl     rbx, 4
0x100438263  add     rbx, r10
0x100438266  mov     r10, cs:?OSYieldCallback@@3P6AXXZEA; void (*OSYieldCallback)(void)
0x10043826d  nop     dword ptr [rax]
0x100438270  movsd   xmm1, qword ptr [rbx]
0x100438274  comisd  xmm12, xmm1
0x100438279  jb      loc_1004384BC
0x10043827f  cmp     byte ptr [rbp+0], 0
0x100438283  jnz     loc_100438495
0x100438289  movsd   xmm0, qword ptr [rbx+8]
0x10043828e  comisd  xmm10, xmm0
0x100438293  ja      loc_100438495
0x100438299  comisd  xmm0, xmm11
0x10043829e  ja      loc_100438495
0x1004382a4  ucomisd xmm1, qword ptr [r12]
0x1004382aa  jp      short loc_1004382EB
0x1004382ac  jnz     short loc_1004382EB
0x1004382ae  ucomisd xmm0, qword ptr [r12+8]
0x1004382b5  jp      short loc_1004382EB
0x1004382b7  jnz     short loc_1004382EB
0x1004382b9  test    r13b, r13b
0x1004382bc  jnz     loc_1004384B8
0x1004382c2  mov     r9d, edi
0x1004382c5  mov     [rsp+0D8h+arg_8], edi
0x1004382cc  mov     r13b, 1
0x1004382cf  jmp     loc_10043849D
0x1004382d4  sub     ecx, 3
0x1004382d7  jmp     loc_1004381DA
0x1004382dc  sub     ecx, 2
0x1004382df  jmp     loc_1004381DA
0x1004382e4  dec     ecx
0x1004382e6  jmp     loc_1004381DA
0x1004382eb  ucomisd xmm1, qword ptr [r15]
0x1004382f0  jp      short loc_100438326
0x1004382f2  jnz     short loc_100438326
0x1004382f4  ucomisd xmm0, qword ptr [r15+8]
0x1004382fa  jp      short loc_100438326
0x1004382fc  jnz     short loc_100438326
0x1004382fe  test    dl, dl
0x100438300  jnz     loc_1004384B8
0x100438306  mov     r9d, [rsp+0D8h+arg_8]
0x10043830e  mov     dl, 1
0x100438310  mov     byte ptr [rsp+0D8h+arg_20], dl
0x100438317  mov     r11d, edi
0x10043831a  mov     [rsp+0D8h+arg_10], edi
0x100438321  jmp     loc_1004384A5
0x100438326  ucomisd xmm1, qword ptr [r14]
0x10043832b  jp      short loc_100438359
0x10043832d  jnz     short loc_100438359
0x10043832f  ucomisd xmm0, qword ptr [r14+8]
0x100438335  jp      short loc_100438359
0x100438337  jnz     short loc_100438359
0x100438339  test    r8b, r8b
0x10043833c  jnz     loc_1004384B8
0x100438342  mov     r8b, 1
0x100438345  mov     [rsp+0D8h+arg_18], edi
0x10043834c  mov     [rsp+0D8h+arg_0], r8b
0x100438354  jmp     loc_100438495
0x100438359  inc     dword ptr [rsi+78h]
0x10043835c  cmp     dword ptr [rsi+78h], 30D40h
0x100438363  jbe     short loc_10043837B
0x100438365  test    r10, r10
0x100438368  jz      short loc_100438374
0x10043836a  call    r10 ; void (*OSYieldCallback)(void)
0x10043836d  mov     r10, cs:?OSYieldCallback@@3P6AXXZEA; void (*OSYieldCallback)(void)
0x100438374  mov     dword ptr [rsi+78h], 0
0x10043837b  movsd   xmm2, qword ptr [rbx]
0x10043837f  xor     edx, edx
0x100438381  movsd   xmm6, qword ptr [rbx+8]
0x100438386  movsd   xmm4, qword ptr [r15]
0x10043838b  movsd   xmm5, qword ptr [r15+8]
0x100438391  subsd   xmm4, xmm2
0x100438395  movsd   xmm7, qword ptr [r12]
0x10043839b  subsd   xmm5, xmm6
0x10043839f  movsd   xmm8, qword ptr [r12+8]
0x1004383a6  subsd   xmm7, xmm2
0x1004383aa  subsd   xmm8, xmm6
0x1004383af  movaps  xmm1, xmm4
0x1004383b2  movaps  xmm0, xmm5
0x1004383b5  mulsd   xmm0, xmm7
0x1004383b9  mulsd   xmm1, xmm8
0x1004383be  subsd   xmm1, xmm0
0x1004383c2  comisd  xmm9, xmm1
0x1004383c7  ja      short loc_1004383D3
0x1004383c9  comisd  xmm1, xmm9
0x1004383ce  setbe   dl
0x1004383d1  inc     edx
0x1004383d3  movsd   xmm3, qword ptr [r14]
0x1004383d8  xor     ecx, ecx
0x1004383da  movsd   xmm1, qword ptr [r14+8]
0x1004383e0  subsd   xmm3, xmm2
0x1004383e4  subsd   xmm1, xmm6
0x1004383e8  movaps  xmm2, xmm3
0x1004383eb  movaps  xmm0, xmm1
0x1004383ee  mulsd   xmm2, xmm5
0x1004383f2  mulsd   xmm0, xmm4
0x1004383f6  subsd   xmm2, xmm0
0x1004383fa  comisd  xmm9, xmm2
0x1004383ff  ja      short loc_10043840B
0x100438401  comisd  xmm2, xmm9
0x100438406  setbe   cl
0x100438409  inc     ecx
0x10043840b  mulsd   xmm1, xmm7
0x10043840f  xor     eax, eax
0x100438411  mulsd   xmm3, xmm8
0x100438416  subsd   xmm1, xmm3
0x10043841a  comisd  xmm9, xmm1
0x10043841f  ja      short loc_10043842B
0x100438421  comisd  xmm1, xmm9
0x100438426  setbe   al
0x100438429  inc     eax
0x10043842b  cmp     edx, 2
0x10043842e  jz      loc_1004384B8
0x100438434  cmp     ecx, 2
0x100438437  jz      short loc_1004384B8
0x100438439  cmp     eax, 2
0x10043843c  jz      short loc_1004384B8
0x10043843e  cmp     edx, ecx
0x100438440  jnz     short loc_100438446
0x100438442  cmp     ecx, eax
0x100438444  jz      short loc_1004384B8
0x100438446  add     dword ptr [rsi+78h], 2
0x10043844a  mov     r9, r15
0x10043844d  mov     r8, r12
0x100438450  mov     rdx, rbx
0x100438453  mov     rcx, rsi
0x100438456  call    ?FIsPointCloseToLine@CSingleSideReducer@@AEAA_NAEBV?$CMglPoint@N@@00@Z; CSingleSideReducer::FIsPointCloseToLine(CMglPoint<double> const &,CMglPoint<double> const &,CMglPoint<double> const &)
0x10043845b  test    al, al
0x10043845d  jnz     short loc_1004384B8
0x10043845f  mov     r9, r14
0x100438462  mov     r8, r15
0x100438465  call    ?FIsPointCloseToLine@CSingleSideReducer@@AEAA_NAEBV?$CMglPoint@N@@00@Z; CSingleSideReducer::FIsPointCloseToLine(CMglPoint<double> const &,CMglPoint<double> const &,CMglPoint<double> const &)
0x10043846a  test    al, al
0x10043846c  jnz     short loc_1004384B8
0x10043846e  mov     r9, r12
0x100438471  mov     r8, r14
0x100438474  call    ?FIsPointCloseToLine@CSingleSideReducer@@AEAA_NAEBV?$CMglPoint@N@@00@Z; CSingleSideReducer::FIsPointCloseToLine(CMglPoint<double> const &,CMglPoint<double> const &,CMglPoint<double> const &)
0x100438479  test    al, al
0x10043847b  jnz     short loc_1004384B8
0x10043847d  movzx   edx, byte ptr [rsp+0D8h+arg_20]
0x100438485  movzx   r8d, [rsp+0D8h+arg_0]
0x10043848e  mov     eax, [rsp+0D8h+arg_30]
0x100438495  mov     r9d, [rsp+0D8h+arg_8]
0x10043849d  mov     r11d, [rsp+0D8h+arg_10]
0x1004384a5  inc     edi
0x1004384a7  inc     rbp
0x1004384aa  add     rbx, 10h
0x1004384ae  cmp     edi, eax
0x1004384b0  jb      loc_100438270
0x1004384b6  jmp     short loc_1004384CC
0x1004384b8  mov     al, 1
0x1004384ba  jmp     short loc_1004384FC
0x1004384bc  mov     r9d, [rsp+0D8h+arg_8]
0x1004384c4  mov     r11d, [rsp+0D8h+arg_10]
0x1004384cc  mov     ebx, [rsp+0D8h+arg_18]
0x1004384d3  cmp     [rsp+0D8h+arg_38], 0
0x1004384db  mov     rdx, [rsp+0D8h+arg_28]
0x1004384e3  movsxd  rax, r11d
0x1004384e6  mov     byte ptr [rax+rdx], 1
0x1004384ea  jz      short loc_1004384FA
  ... truncated ...
```
