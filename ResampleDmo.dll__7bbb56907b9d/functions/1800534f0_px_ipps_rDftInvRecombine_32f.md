# px_ipps_rDftInvRecombine_32f

- ea: `0x1800534f0`
- end: `0x180053636`
- name: `px_ipps_rDftInvRecombine_32f`
- size: `326`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x1800483c0`

## callees

- `0x1800534f0`

## pseudocode

```c
void __fastcall px_ipps_rDftInvRecombine_32f(float *a1, float *a2, int a3, __int64 a4)
{
  float v4; // xmm1_4
  float v5; // xmm0_4
  float *v6; // rbx
  char *v7; // r10
  float *v8; // rdi
  char *v9; // r11
  signed __int64 v10; // r9
  __int64 v11; // rax
  float v12; // xmm7_4
  float v13; // xmm2_4
  float v14; // xmm6_4
  float v15; // xmm4_4
  float v16; // xmm7_4
  float v17; // xmm3_4
  float v18; // xmm5_4

  v4 = a1[1];
  v5 = *a1 - v4;
  *a2 = v4 + *a1;
  a2[1] = v5;
  if ( a3 != 1 )
  {
    if ( a3 > 2 )
    {
      v6 = (float *)(a4 + 12);
      v7 = (char *)a1 - a4;
      v8 = &a2[2 * a3 - 1];
      v9 = (char *)a2 - a4;
      v10 = (char *)a1 - (char *)a2;
      v11 = ((unsigned int)(a3 - 3) >> 1) + 1;
      do
      {
        v12 = *(float *)((char *)v8 + v10 - 4);
        v13 = *(float *)((char *)v6 + (_QWORD)v7) + *(float *)((char *)v8 + v10);
        v14 = *(float *)((char *)v6 + (_QWORD)v7) - *(float *)((char *)v8 + v10);
        v15 = *(float *)((char *)v6 + (_QWORD)v7 - 4) - v12;
        v16 = v12 + *(float *)((char *)v6 + (_QWORD)v7 - 4);
        v17 = (float)(*v6 * v15) - (float)(*(v6 - 1) * v13);
        v18 = (float)(*(v6 - 1) * v15) + (float)(*v6 * v13);
        *(float *)((char *)v6 + (_QWORD)v9 - 4) = v17 + v16;
        *(float *)((char *)v6 + (_QWORD)v9) = v18 + v14;
        v6 += 2;
        *(v8 - 1) = v16 - v17;
        *v8 = v18 - v14;
        v8 -= 2;
        --v11;
      }
      while ( v11 );
    }
    if ( (a3 & 1) == 0 )
    {
      a2[a3] = a1[a3] * 2.0;
      a2[a3 + 1] = a1[a3 + 1] * -2.0;
    }
  }
}

```

## disassembly

```asm
0x1800534f0  mov     [rsp+arg_0], rbx
0x1800534f5  push    rdi
0x1800534f6  sub     rsp, 20h
0x1800534fa  movss   xmm1, dword ptr [rcx+4]
0x1800534ff  movss   xmm0, dword ptr [rcx]
0x180053503  movaps  [rsp+28h+var_18], xmm6
0x180053508  movaps  [rsp+28h+var_28], xmm7
0x18005350c  subss   xmm0, xmm1
0x180053510  addss   xmm1, dword ptr [rcx]
0x180053514  movss   dword ptr [rdx], xmm1
0x180053518  movss   dword ptr [rdx+4], xmm0
0x18005351d  cmp     r8d, 1
0x180053521  jz      loc_180053622
0x180053527  lea     eax, ds:0FFFFFFFFFFFFFFFEh[r8*2]
0x18005352f  cmp     r8d, 2
0x180053533  jle     loc_1800535F3
0x180053539  movsxd  rdi, eax
0x18005353c  lea     rbx, [r9+0Ch]
0x180053540  mov     r10, rcx
0x180053543  sub     r10, r9
0x180053546  inc     rdi
0x180053549  lea     eax, [r8-3]
0x18005354d  mov     r11, rdx
0x180053550  shr     eax, 1
0x180053552  lea     rdi, [rdx+rdi*4]
0x180053556  sub     r11, r9
0x180053559  mov     r9, rcx
0x18005355c  sub     r9, rdx
0x18005355f  inc     eax
0x180053561  movss   xmm1, dword ptr [rbx]
0x180053565  movss   xmm5, dword ptr [rbx-4]
0x18005356a  movss   xmm6, dword ptr [r10+rbx]
0x180053570  movaps  xmm3, xmm1
0x180053573  movaps  xmm0, xmm5
0x180053576  movaps  xmm2, xmm6
0x180053579  movss   xmm7, dword ptr [r9+rdi-4]
0x180053580  addss   xmm2, dword ptr [r9+rdi]
0x180053586  subss   xmm6, dword ptr [r9+rdi]
0x18005358c  mulss   xmm0, xmm2
0x180053590  mulss   xmm1, xmm2
0x180053594  movss   xmm4, dword ptr [r10+rbx-4]
0x18005359b  subss   xmm4, xmm7
0x18005359f  addss   xmm7, dword ptr [r10+rbx-4]
0x1800535a6  mulss   xmm5, xmm4
0x1800535aa  mulss   xmm3, xmm4
0x1800535ae  subss   xmm3, xmm0
0x1800535b2  addss   xmm5, xmm1
0x1800535b6  movaps  xmm1, xmm5
0x1800535b9  movaps  xmm0, xmm3
0x1800535bc  addss   xmm0, xmm7
0x1800535c0  addss   xmm1, xmm6
0x1800535c4  subss   xmm7, xmm3
0x1800535c8  movss   dword ptr [r11+rbx-4], xmm0
0x1800535cf  movss   dword ptr [r11+rbx], xmm1
0x1800535d5  subss   xmm5, xmm6
0x1800535d9  add     rbx, 8
0x1800535dd  movss   dword ptr [rdi-4], xmm7
0x1800535e2  movss   dword ptr [rdi], xmm5
0x1800535e6  sub     rdi, 8
0x1800535ea  dec     rax
0x1800535ed  jnz     loc_180053561
0x1800535f3  test    r8b, 1
0x1800535f7  jnz     short loc_180053622
0x1800535f9  movsxd  rax, r8d
0x1800535fc  movss   xmm0, dword ptr [rcx+rax*4]
0x180053601  mulss   xmm0, cs:__real@40000000
0x180053609  movss   dword ptr [rdx+rax*4], xmm0
0x18005360e  movss   xmm1, dword ptr [rcx+rax*4+4]
0x180053614  mulss   xmm1, cs:__real@c0000000
0x18005361c  movss   dword ptr [rdx+rax*4+4], xmm1
0x180053622  mov     rbx, [rsp+28h+arg_0]
0x180053627  movaps  xmm6, [rsp+28h+var_18]
0x18005362c  movaps  xmm7, [rsp+28h+var_28]
0x180053630  add     rsp, 20h
0x180053634  pop     rdi
0x180053635  retn
```
