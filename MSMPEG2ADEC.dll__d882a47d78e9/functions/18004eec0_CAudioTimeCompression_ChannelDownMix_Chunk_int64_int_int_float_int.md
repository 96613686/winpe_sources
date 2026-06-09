# CAudioTimeCompression::ChannelDownMix(Chunk *,__int64,int,int,float *,int)

- ea: `0x18004eec0`
- end: `0x18004f209`
- name: `?ChannelDownMix@CAudioTimeCompression@@IEAAJPEAVChunk@@_JHHPEAMH@Z`
- size: `841`
- prototype: `__int64 __fastcall(CAudioTimeCompression *__hidden this, struct Chunk *, __int64, int, int, float *, int)`
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x1800504f0`

## callees

- `0x18004eec0`

## pseudocode

```c
__int64 __fastcall CAudioTimeCompression::ChannelDownMix(
        CAudioTimeCompression *this,
        struct Chunk *a2,
        __int64 a3,
        int a4,
        int a5,
        float *a6,
        int a7)
{
  int v7; // ebx
  int v8; // r10d
  __int16 v10; // ax
  __int64 v11; // r8
  float *v12; // rdx
  int v13; // r8d
  __int64 v14; // rcx
  __int64 v15; // r11
  __int64 v16; // rax
  float v17; // xmm1_4
  float v18; // xmm0_4
  __int64 v19; // rax
  __int64 v20; // r8
  float *v21; // rdx
  int v22; // r8d
  __int64 v23; // rax
  __int64 v24; // rcx
  __int64 v25; // r11
  __int64 v26; // r13
  __int64 v27; // rbx
  __int64 v28; // r10
  __int64 v29; // rsi
  __int64 v30; // rbp
  __int64 v31; // r14
  __int64 v32; // r15
  __int64 v33; // rax
  float v34; // xmm0_4
  float v35; // xmm2_4
  float v36; // xmm0_4
  __int64 v37; // rcx
  float v38; // xmm1_4

  v7 = a5;
  v8 = a4;
  if ( a5 && a4 >= 0x7FFFFFFF / a5 || a4 > a7 )
    return 2147500037LL;
  v10 = *((_WORD *)this + 3);
  if ( v10 != 2 )
  {
    if ( v10 != 6 )
      return 2147500037LL;
    v20 = a3 - *(_QWORD *)a2;
    if ( v20 < 0 || v20 >= *((int *)a2 + 2) )
      v21 = 0;
    else
      v21 = (float *)(*((_QWORD *)a2 + 3) + v20 * *((int *)a2 + 3));
    v22 = 0;
    if ( a4 >= 4 )
    {
      v23 = 6 * a5;
      v24 = v23;
      v25 = 8 * v23;
      v26 = 3 * v23;
      v27 = 3 * v23;
      v28 = 3 * v23;
      v29 = 8 * v23 + 4;
      v30 = 8 * v23 + 8;
      v31 = 8 * v23 + 16;
      v32 = 8 * v23 + 20;
      do
      {
        v33 = v22;
        v22 += 4;
        a6[v33] = (float)((float)((float)(v21[5] + v21[4]) + v21[2]) + (float)(v21[1] + *v21)) * 0.2;
        a6[v33 + 1] = (float)((float)((float)(v21[v24 + 5] + v21[v24 + 4]) + v21[v24 + 2])
                            + (float)(v21[v24] + v21[v24 + 1]))
                    * 0.2;
        a6[v33 + 2] = (float)((float)((float)(*(float *)((char *)v21 + v32) + *(float *)((char *)v21 + v31))
                                    + *(float *)((char *)v21 + v30))
                            + (float)(v21[(unsigned __int64)v25 / 4] + *(float *)((char *)v21 + v29)))
                    * 0.2;
        v34 = v21[v26 + 1] + v21[v24 + (unsigned __int64)v25 / 4];
        v35 = (float)(v21[(unsigned __int64)v25 / 4 + 5 + v24] + v21[v28 + 4]) + v21[v27 + 2];
        v21 = (float *)((char *)v21 + 2 * v25);
        a6[v33 + 3] = (float)(v35 + v34) * 0.2;
      }
      while ( v22 < a4 - 3 );
      v8 = a4;
      v7 = a5;
    }
    for ( ; v22 < v8; a6[v37] = (float)(v38 + v36) * 0.2 )
    {
      v36 = v21[1] + *v21;
      v37 = v22++;
      v38 = (float)(v21[5] + v21[4]) + v21[2];
      v21 += 6 * v7;
    }
    return 0;
  }
  v11 = a3 - *(_QWORD *)a2;
  if ( v11 < 0 || v11 >= *((int *)a2 + 2) )
    v12 = 0;
  else
    v12 = (float *)(*((_QWORD *)a2 + 3) + v11 * *((int *)a2 + 3));
  v13 = 0;
  if ( a4 >= 4 )
  {
    v14 = 2LL * a5;
    v15 = 4LL * a5;
    do
    {
      v16 = v13;
      v13 += 4;
      a6[v16] = (float)(v12[1] + *v12) * 0.5;
      a6[v16 + 1] = (float)(v12[v14] + v12[v14 + 1]) * 0.5;
      a6[v16 + 2] = (float)(v12[4 * a5 + 1] + v12[v15]) * 0.5;
      v17 = v12[v14 + 1 + v15] + v12[v14 + v15];
      v12 += 8 * a5;
      a6[v16 + 3] = v17 * 0.5;
    }
    while ( v13 < a4 - 3 );
  }
  if ( v13 >= a4 )
    return 0;
  do
  {
    v18 = v12[1] + *v12;
    v19 = v13;
    v12 += 2 * a5;
    ++v13;
    a6[v19] = v18 * 0.5;
  }
  while ( v13 < a4 );
  return 0;
}

```

## disassembly

```asm
0x18004eec0  mov     [rsp+arg_18], r9d
0x18004eec5  push    rbx
0x18004eec6  sub     rsp, 20h
0x18004eeca  mov     ebx, [rsp+28h+arg_20]
0x18004eece  mov     r10d, r9d
0x18004eed1  mov     r11, rdx
0x18004eed4  test    ebx, ebx
0x18004eed6  jz      short loc_18004EEF1
0x18004eed8  mov     eax, 7FFFFFFFh
0x18004eedd  cdq
0x18004eede  idiv    ebx
0x18004eee0  cmp     r9d, eax
0x18004eee3  jl      short loc_18004EEF1
0x18004eee5  mov     eax, 80004005h
0x18004eeea  add     rsp, 20h
0x18004eeee  pop     rbx
0x18004eeef  retn
0x18004eef1  cmp     r10d, [rsp+28h+arg_30]
0x18004eef6  jg      short loc_18004EEE5
0x18004eef8  movzx   eax, word ptr [rcx+6]
0x18004eefc  mov     ecx, 2
0x18004ef01  mov     r9, [rsp+28h+arg_28]
0x18004ef06  mov     [rsp+28h+arg_0], rbp
0x18004ef0b  mov     [rsp+28h+arg_8], rsi
0x18004ef10  mov     [rsp+28h+arg_10], rdi
0x18004ef15  mov     [rsp+28h+var_20], r14
0x18004ef1a  mov     [rsp+28h+var_28], r15
0x18004ef1e  cmp     cx, ax
0x18004ef21  jnz     loc_18004F030
0x18004ef27  sub     r8, [r11]
0x18004ef2a  js      short loc_18004EF43
0x18004ef2c  movsxd  rax, dword ptr [r11+8]
0x18004ef30  cmp     r8, rax
0x18004ef33  jge     short loc_18004EF43
0x18004ef35  movsxd  rdx, dword ptr [r11+0Ch]
0x18004ef39  imul    rdx, r8
0x18004ef3d  add     rdx, [r11+18h]
0x18004ef41  jmp     short loc_18004EF45
0x18004ef43  xor     edx, edx
0x18004ef45  movss   xmm2, cs:__real@3f000000
0x18004ef4d  xor     r8d, r8d
0x18004ef50  cmp     r10d, 4
0x18004ef54  jl      loc_18004EFF5
0x18004ef5a  lea     eax, [rbx+rbx]
0x18004ef5d  movsxd  rcx, eax
0x18004ef60  lea     edi, [r10-3]
0x18004ef64  lea     rcx, ds:0[rcx*4]
0x18004ef6c  lea     r11, [rcx+rcx]
0x18004ef70  lea     rbp, [rcx+r11]
0x18004ef74  lea     r14, [rcx+r11]
0x18004ef78  lea     r15, [r11+r11]
0x18004ef7c  lea     rsi, ds:4[rcx*2]
0x18004ef84  nop     dword ptr [rax+00h]
0x18004ef88  nop     dword ptr [rax+rax+00000000h]
0x18004ef90  movss   xmm0, dword ptr [rdx+4]
0x18004ef95  addss   xmm0, dword ptr [rdx]
0x18004ef99  movsxd  rax, r8d
0x18004ef9c  add     r8d, 4
0x18004efa0  mulss   xmm0, xmm2
0x18004efa4  movss   dword ptr [r9+rax*4], xmm0
0x18004efaa  movss   xmm1, dword ptr [rcx+rdx]
0x18004efaf  addss   xmm1, dword ptr [rdx+rcx+4]
0x18004efb5  mulss   xmm1, xmm2
0x18004efb9  movss   dword ptr [r9+rax*4+4], xmm1
0x18004efc0  movss   xmm0, dword ptr [rsi+rdx]
0x18004efc5  addss   xmm0, dword ptr [r11+rdx]
0x18004efcb  mulss   xmm0, xmm2
0x18004efcf  movss   dword ptr [r9+rax*4+8], xmm0
0x18004efd6  movss   xmm1, dword ptr [r14+rdx+4]
0x18004efdd  addss   xmm1, dword ptr [rdx+rbp]
0x18004efe2  add     rdx, r15
0x18004efe5  mulss   xmm1, xmm2
0x18004efe9  movss   dword ptr [r9+rax*4+0Ch], xmm1
0x18004eff0  cmp     r8d, edi
0x18004eff3  jl      short loc_18004EF90
0x18004eff5  cmp     r8d, r10d
0x18004eff8  jge     loc_18004F1E1
0x18004effe  lea     eax, [rbx+rbx]
0x18004f001  movsxd  rcx, eax
0x18004f004  shl     rcx, 2
0x18004f008  movss   xmm0, dword ptr [rdx+4]
0x18004f00d  addss   xmm0, dword ptr [rdx]
0x18004f011  movsxd  rax, r8d
0x18004f014  add     rdx, rcx
0x18004f017  inc     r8d
0x18004f01a  mulss   xmm0, xmm2
0x18004f01e  movss   dword ptr [r9+rax*4], xmm0
0x18004f024  cmp     r8d, r10d
0x18004f027  jl      short loc_18004F008
0x18004f029  xor     eax, eax
0x18004f02b  jmp     loc_18004F1EA
0x18004f030  mov     ecx, 6
0x18004f035  cmp     cx, ax
0x18004f038  jnz     loc_18004F1E5
0x18004f03e  sub     r8, [r11]
0x18004f041  js      short loc_18004F05A
0x18004f043  movsxd  rax, dword ptr [r11+8]
0x18004f047  cmp     r8, rax
0x18004f04a  jge     short loc_18004F05A
0x18004f04c  movsxd  rdx, dword ptr [r11+0Ch]
0x18004f050  imul    rdx, r8
0x18004f054  add     rdx, [r11+18h]
0x18004f058  jmp     short loc_18004F05C
0x18004f05a  xor     edx, edx
0x18004f05c  movss   xmm3, cs:__real@3e4ccccd
0x18004f064  xor     r8d, r8d
0x18004f067  cmp     r10d, 4
0x18004f06b  jl      loc_18004F19C
0x18004f071  lea     eax, [rbx+rbx*2]
0x18004f074  mov     [rsp+28h+var_10], r12
0x18004f079  add     eax, eax
0x18004f07b  mov     [rsp+28h+var_18], r13
0x18004f080  cdqe
0x18004f082  lea     edi, [r10-3]
0x18004f086  lea     rcx, ds:0[rax*4]
0x18004f08e  lea     r11, [rcx+rcx]
0x18004f092  lea     r13, [r11+rcx]
0x18004f096  lea     rbx, [r11+rcx]
0x18004f09a  lea     r10, [r11+rcx]
0x18004f09e  lea     rsi, ds:4[rcx*2]
0x18004f0a6  lea     rbp, ds:8[rcx*2]
0x18004f0ae  lea     r14, ds:10h[rcx*2]
0x18004f0b6  lea     r15, ds:14h[rcx*2]
0x18004f0be  xchg    ax, ax
0x18004f0c0  movss   xmm1, dword ptr [rdx+14h]
0x18004f0c5  lea     r12, [r11+rcx]
0x18004f0c9  addss   xmm1, dword ptr [rdx+10h]
0x18004f0ce  movss   xmm0, dword ptr [rdx+4]
0x18004f0d3  addss   xmm0, dword ptr [rdx]
0x18004f0d7  movsxd  rax, r8d
0x18004f0da  add     r8d, 4
0x18004f0de  addss   xmm1, dword ptr [rdx+8]
0x18004f0e3  addss   xmm1, xmm0
0x18004f0e7  mulss   xmm1, xmm3
0x18004f0eb  movss   dword ptr [r9+rax*4], xmm1
0x18004f0f1  movss   xmm2, dword ptr [rcx+rdx+14h]
0x18004f0f7  movss   xmm0, dword ptr [rcx+rdx]
0x18004f0fc  addss   xmm2, dword ptr [rcx+rdx+10h]
0x18004f102  addss   xmm0, dword ptr [rcx+rdx+4]
0x18004f108  addss   xmm2, dword ptr [rcx+rdx+8]
0x18004f10e  addss   xmm2, xmm0
0x18004f112  mulss   xmm2, xmm3
0x18004f116  movss   dword ptr [r9+rax*4+4], xmm2
0x18004f11d  movss   xmm0, dword ptr [r11+rdx]
0x18004f123  movss   xmm1, dword ptr [r15+rdx]
0x18004f129  addss   xmm1, dword ptr [r14+rdx]
0x18004f12f  addss   xmm0, dword ptr [rsi+rdx]
0x18004f134  addss   xmm1, dword ptr [rdx+rbp]
0x18004f139  addss   xmm1, xmm0
0x18004f13d  mulss   xmm1, xmm3
0x18004f141  movss   dword ptr [r9+rax*4+8], xmm1
0x18004f148  movss   xmm2, dword ptr [r12+rdx+14h]
0x18004f14f  lea     r12, [rcx+r11]
0x18004f153  movss   xmm0, dword ptr [rdx+r13+4]
0x18004f15a  addss   xmm2, dword ptr [r10+rdx+10h]
0x18004f161  addss   xmm0, dword ptr [r12+rdx]
0x18004f167  addss   xmm2, dword ptr [rbx+rdx+8]
0x18004f16d  lea     rdx, [rdx+r11*2]
0x18004f171  addss   xmm2, xmm0
0x18004f175  mulss   xmm2, xmm3
0x18004f179  movss   dword ptr [r9+rax*4+0Ch], xmm2
0x18004f180  cmp     r8d, edi
0x18004f183  jl      loc_18004F0C0
0x18004f189  mov     r13, [rsp+28h+var_18]
0x18004f18e  mov     r12, [rsp+28h+var_10]
0x18004f193  mov     r10d, [rsp+28h+arg_18]
0x18004f198  mov     ebx, [rsp+28h+arg_20]
0x18004f19c  cmp     r8d, r10d
0x18004f19f  jge     short loc_18004F1E1
0x18004f1a1  lea     eax, [rbx+rbx*2]
0x18004f1a4  add     eax, eax
0x18004f1a6  movsxd  r11, eax
0x18004f1a9  shl     r11, 2
0x18004f1ad  movss   xmm1, dword ptr [rdx+14h]
0x18004f1b2  addss   xmm1, dword ptr [rdx+10h]
0x18004f1b7  movss   xmm0, dword ptr [rdx+4]
0x18004f1bc  addss   xmm0, dword ptr [rdx]
0x18004f1c0  movsxd  rcx, r8d
0x18004f1c3  inc     r8d
0x18004f1c6  addss   xmm1, dword ptr [rdx+8]
0x18004f1cb  add     rdx, r11
0x18004f1ce  addss   xmm1, xmm0
0x18004f1d2  mulss   xmm1, xmm3
0x18004f1d6  movss   dword ptr [r9+rcx*4], xmm1
0x18004f1dc  cmp     r8d, r10d
0x18004f1df  jl      short loc_18004F1AD
0x18004f1e1  xor     eax, eax
0x18004f1e3  jmp     short loc_18004F1EA
0x18004f1e5  mov     eax, 80004005h
0x18004f1ea  mov     r14, [rsp+28h+var_20]
0x18004f1ef  mov     rdi, [rsp+28h+arg_10]
0x18004f1f4  mov     rsi, [rsp+28h+arg_8]
0x18004f1f9  mov     rbp, [rsp+28h+arg_0]
0x18004f1fe  mov     r15, [rsp+28h+var_28]
0x18004f202  add     rsp, 20h
0x18004f206  pop     rbx
0x18004f207  retn
```
