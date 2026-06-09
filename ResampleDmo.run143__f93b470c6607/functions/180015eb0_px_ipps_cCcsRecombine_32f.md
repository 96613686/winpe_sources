# px_ipps_cCcsRecombine_32f

- ea: `0x180015eb0`
- end: `0x1800160da`
- name: `px_ipps_cCcsRecombine_32f`
- size: `554`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x18000dd90`
- `0x18000e0cc`

## callees

- `0x180015eb0`

## pseudocode

```c
void __fastcall px_ipps_cCcsRecombine_32f(__int64 a1, __int64 a2, int a3, int a4, __int64 a5)
{
  int v5; // eax
  float *v6; // rdi
  __int64 v7; // r11
  float *v8; // rbx
  __int64 v9; // r9
  __int64 v10; // r10
  __int64 v11; // rax
  float v12; // xmm7_4
  float v13; // xmm0_4
  float v14; // xmm6_4
  float v15; // xmm4_4
  float v16; // xmm7_4
  float v17; // xmm2_4
  float v18; // xmm6_4
  float v19; // xmm5_4
  float v20; // xmm3_4
  float *v21; // rdi
  __int64 v22; // r11
  float *v23; // rbx
  __int64 v24; // r9
  __int64 v25; // r10
  __int64 v26; // rax
  float v27; // xmm7_4
  float v28; // xmm2_4
  float v29; // xmm6_4
  float v30; // xmm4_4
  float v31; // xmm7_4
  float v32; // xmm3_4
  float v33; // xmm5_4

  if ( a3 != 1 )
  {
    v5 = 2 * a3 - 2;
    if ( a4 <= 0 )
    {
      if ( a3 > 2 )
      {
        v21 = (float *)(a2 + 4 * (v5 + 1LL));
        v22 = a1 - a2;
        v23 = (float *)(a5 + 12);
        v24 = a1 - a5;
        v25 = a2 - a5;
        v26 = ((unsigned int)(a3 - 3) >> 1) + 1;
        do
        {
          v27 = *(float *)((char *)v21 + v22 - 4);
          v28 = *(float *)((char *)v23 + v24) + *(float *)((char *)v21 + v22);
          v29 = *(float *)((char *)v23 + v24) - *(float *)((char *)v21 + v22);
          v30 = *(float *)((char *)v23 + v24 - 4) - v27;
          v31 = v27 + *(float *)((char *)v23 + v24 - 4);
          v32 = (float)(*v23 * v30) - (float)(*(v23 - 1) * v28);
          v33 = (float)(*(v23 - 1) * v30) + (float)(*v23 * v28);
          *(float *)((char *)v23 + v25 - 4) = v32 + v31;
          *(float *)((char *)v23 + v25) = v33 + v29;
          v23 += 2;
          *(v21 - 1) = v31 - v32;
          *v21 = v33 - v29;
          v21 -= 2;
          --v26;
        }
        while ( v26 );
      }
      *(float *)(a2 + 4LL * a3) = *(float *)(a1 + 4LL * a3) * 2.0;
      *(float *)(a2 + 4LL * a3 + 4) = *(float *)(a1 + 4LL * a3 + 4) * -2.0;
    }
    else
    {
      if ( a3 > 2 )
      {
        v6 = (float *)(a2 + 4 * (v5 + 1LL));
        v7 = a1 - a2;
        v8 = (float *)(a5 + 12);
        v9 = a1 - a5;
        v10 = a2 - a5;
        v11 = ((unsigned int)(a3 - 3) >> 1) + 1;
        do
        {
          v12 = *(float *)((char *)v6 + v7 - 4);
          v13 = *(v8 - 1);
          v14 = *(float *)((char *)v8 + v9);
          v15 = *(float *)((char *)v8 + v9 - 4) - v12;
          v16 = v12 + *(float *)((char *)v8 + v9 - 4);
          v17 = *(float *)((char *)v6 + v7) + v14;
          v18 = v14 - *(float *)((char *)v6 + v7);
          v19 = (float)(v13 * v15) - (float)(*v8 * v17);
          v20 = (float)(*v8 * v15) + (float)(v13 * v17);
          *(float *)((char *)v8 + v10) = v19 + v18;
          v8 += 2;
          *(float *)((char *)v8 + v10 - 12) = v16 - v20;
          *(v6 - 1) = v20 + v16;
          *v6 = v19 - v18;
          v6 -= 2;
          --v11;
        }
        while ( v11 );
      }
      *(float *)(a2 + 4LL * a3) = *(float *)(a1 + 4LL * a3) * 2.0;
      *(float *)(a2 + 4LL * a3 + 4) = *(float *)(a1 + 4LL * a3 + 4) * 2.0;
    }
  }
}

```

## disassembly

```asm
0x180015eb0  cmp     r8d, 1
0x180015eb4  jz      locret_1800160D9
0x180015eba  mov     [rsp+arg_0], rbx
0x180015ebf  push    rdi
0x180015ec0  sub     rsp, 20h
0x180015ec4  movaps  [rsp+28h+var_18], xmm6
0x180015ec9  lea     eax, ds:0FFFFFFFFFFFFFFFEh[r8*2]
0x180015ed1  movaps  [rsp+28h+var_28], xmm7
0x180015ed5  test    r9d, r9d
0x180015ed8  jle     loc_180015FD5
0x180015ede  cmp     r8d, 2
0x180015ee2  jle     loc_180015FA7
0x180015ee8  cdqe
0x180015eea  mov     r9, rcx
0x180015eed  mov     r10, rdx
0x180015ef0  inc     rax
0x180015ef3  mov     r11, rcx
0x180015ef6  lea     rdi, [rdx+rax*4]
0x180015efa  mov     rax, [rsp+28h+arg_20]
0x180015eff  sub     r11, rdx
0x180015f02  lea     rbx, [rax+0Ch]
0x180015f06  sub     r9, rax
0x180015f09  sub     r10, rax
0x180015f0c  lea     eax, [r8-3]
0x180015f10  shr     eax, 1
0x180015f12  inc     eax
0x180015f14  movss   xmm7, dword ptr [rdi+r11-4]
0x180015f1b  movss   xmm1, dword ptr [rbx]
0x180015f1f  movss   xmm5, dword ptr [rbx-4]
0x180015f24  movaps  xmm0, xmm5
0x180015f27  movaps  xmm3, xmm1
0x180015f2a  movss   xmm6, dword ptr [rbx+r9]
0x180015f30  movss   xmm4, dword ptr [rbx+r9-4]
0x180015f37  movss   xmm2, dword ptr [r11+rdi]
0x180015f3d  subss   xmm4, xmm7
0x180015f41  addss   xmm7, dword ptr [rbx+r9-4]
0x180015f48  addss   xmm2, xmm6
0x180015f4c  mulss   xmm5, xmm4
0x180015f50  mulss   xmm1, xmm2
0x180015f54  mulss   xmm0, xmm2
0x180015f58  subss   xmm6, dword ptr [r11+rdi]
0x180015f5e  subss   xmm5, xmm1
0x180015f62  mulss   xmm3, xmm4
0x180015f66  movaps  xmm1, xmm5
0x180015f69  addss   xmm3, xmm0
0x180015f6d  addss   xmm1, xmm6
0x180015f71  subss   xmm5, xmm6
0x180015f75  movaps  xmm0, xmm7
0x180015f78  movss   dword ptr [rbx+r10], xmm1
0x180015f7e  subss   xmm0, xmm3
0x180015f82  addss   xmm3, xmm7
0x180015f86  add     rbx, 8
0x180015f8a  movss   dword ptr [rbx+r10-0Ch], xmm0
0x180015f91  movss   dword ptr [rdi-4], xmm3
0x180015f96  movss   dword ptr [rdi], xmm5
0x180015f9a  sub     rdi, 8
0x180015f9e  dec     rax
0x180015fa1  jnz     loc_180015F14
0x180015fa7  movsxd  rax, r8d
0x180015faa  movss   xmm0, dword ptr [rcx+rax*4]
0x180015faf  mulss   xmm0, cs:__real@40000000
0x180015fb7  movss   dword ptr [rdx+rax*4], xmm0
0x180015fbc  movss   xmm0, dword ptr [rcx+rax*4+4]
0x180015fc2  mulss   xmm0, cs:__real@40000000
0x180015fca  movss   dword ptr [rdx+rax*4+4], xmm0
0x180015fd0  jmp     loc_1800160C6
0x180015fd5  cmp     r8d, 2
0x180015fd9  jle     loc_18001609D
0x180015fdf  cdqe
0x180015fe1  mov     r9, rcx
0x180015fe4  mov     r10, rdx
0x180015fe7  inc     rax
0x180015fea  mov     r11, rcx
0x180015fed  lea     rdi, [rdx+rax*4]
0x180015ff1  mov     rax, [rsp+28h+arg_20]
0x180015ff6  sub     r11, rdx
0x180015ff9  lea     rbx, [rax+0Ch]
0x180015ffd  sub     r9, rax
0x180016000  sub     r10, rax
0x180016003  lea     eax, [r8-3]
0x180016007  shr     eax, 1
0x180016009  inc     eax
0x18001600b  movss   xmm1, dword ptr [rbx]
0x18001600f  movss   xmm5, dword ptr [rbx-4]
0x180016014  movss   xmm6, dword ptr [rbx+r9]
0x18001601a  movaps  xmm3, xmm1
0x18001601d  movaps  xmm0, xmm5
0x180016020  movaps  xmm2, xmm6
0x180016023  movss   xmm7, dword ptr [rdi+r11-4]
0x18001602a  addss   xmm2, dword ptr [r11+rdi]
0x180016030  subss   xmm6, dword ptr [r11+rdi]
0x180016036  mulss   xmm0, xmm2
0x18001603a  mulss   xmm1, xmm2
0x18001603e  movss   xmm4, dword ptr [rbx+r9-4]
0x180016045  subss   xmm4, xmm7
0x180016049  addss   xmm7, dword ptr [rbx+r9-4]
0x180016050  mulss   xmm5, xmm4
0x180016054  mulss   xmm3, xmm4
0x180016058  subss   xmm3, xmm0
0x18001605c  addss   xmm5, xmm1
0x180016060  movaps  xmm1, xmm5
0x180016063  movaps  xmm0, xmm3
0x180016066  addss   xmm0, xmm7
0x18001606a  addss   xmm1, xmm6
0x18001606e  subss   xmm7, xmm3
0x180016072  movss   dword ptr [rbx+r10-4], xmm0
0x180016079  movss   dword ptr [rbx+r10], xmm1
0x18001607f  subss   xmm5, xmm6
0x180016083  add     rbx, 8
0x180016087  movss   dword ptr [rdi-4], xmm7
0x18001608c  movss   dword ptr [rdi], xmm5
0x180016090  sub     rdi, 8
0x180016094  dec     rax
0x180016097  jnz     loc_18001600B
0x18001609d  movsxd  rax, r8d
0x1800160a0  movss   xmm0, dword ptr [rcx+rax*4]
0x1800160a5  mulss   xmm0, cs:__real@40000000
0x1800160ad  movss   dword ptr [rdx+rax*4], xmm0
0x1800160b2  movss   xmm1, dword ptr [rcx+rax*4+4]
0x1800160b8  mulss   xmm1, cs:__real@c0000000
0x1800160c0  movss   dword ptr [rdx+rax*4+4], xmm1
0x1800160c6  mov     rbx, [rsp+28h+arg_0]
0x1800160cb  movaps  xmm6, [rsp+28h+var_18]
0x1800160d0  movaps  xmm7, [rsp+28h+var_28]
0x1800160d4  add     rsp, 20h
0x1800160d8  pop     rdi
0x1800160d9  retn
```
