# px_ipps_rDftInvRecombine_32f

- ea: `0x18005931c`
- end: `0x180059462`
- name: `px_ipps_rDftInvRecombine_32f`
- size: `326`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x18001ce80`

## callees

- `0x18005931c`

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
0x18005931c  mov     [rsp+arg_0], rbx
0x180059321  push    rdi
0x180059322  sub     rsp, 20h
0x180059326  movss   xmm1, dword ptr [rcx+4]
0x18005932b  movss   xmm0, dword ptr [rcx]
0x18005932f  movaps  [rsp+28h+var_18], xmm6
0x180059334  movaps  [rsp+28h+var_28], xmm7
0x180059338  subss   xmm0, xmm1
0x18005933c  addss   xmm1, dword ptr [rcx]
0x180059340  movss   dword ptr [rdx], xmm1
0x180059344  movss   dword ptr [rdx+4], xmm0
0x180059349  cmp     r8d, 1
0x18005934d  jz      loc_18005944E
0x180059353  lea     eax, ds:0FFFFFFFFFFFFFFFEh[r8*2]
0x18005935b  cmp     r8d, 2
0x18005935f  jle     loc_18005941F
0x180059365  movsxd  rdi, eax
0x180059368  lea     rbx, [r9+0Ch]
0x18005936c  mov     r10, rcx
0x18005936f  sub     r10, r9
0x180059372  inc     rdi
0x180059375  lea     eax, [r8-3]
0x180059379  mov     r11, rdx
0x18005937c  shr     eax, 1
0x18005937e  lea     rdi, [rdx+rdi*4]
0x180059382  sub     r11, r9
0x180059385  mov     r9, rcx
0x180059388  sub     r9, rdx
0x18005938b  inc     eax
0x18005938d  movss   xmm1, dword ptr [rbx]
0x180059391  movss   xmm5, dword ptr [rbx-4]
0x180059396  movss   xmm6, dword ptr [r10+rbx]
0x18005939c  movaps  xmm3, xmm1
0x18005939f  movaps  xmm0, xmm5
0x1800593a2  movaps  xmm2, xmm6
0x1800593a5  movss   xmm7, dword ptr [r9+rdi-4]
0x1800593ac  addss   xmm2, dword ptr [r9+rdi]
0x1800593b2  subss   xmm6, dword ptr [r9+rdi]
0x1800593b8  mulss   xmm0, xmm2
0x1800593bc  mulss   xmm1, xmm2
0x1800593c0  movss   xmm4, dword ptr [r10+rbx-4]
0x1800593c7  subss   xmm4, xmm7
0x1800593cb  addss   xmm7, dword ptr [r10+rbx-4]
0x1800593d2  mulss   xmm5, xmm4
0x1800593d6  mulss   xmm3, xmm4
0x1800593da  subss   xmm3, xmm0
0x1800593de  addss   xmm5, xmm1
0x1800593e2  movaps  xmm1, xmm5
0x1800593e5  movaps  xmm0, xmm3
0x1800593e8  addss   xmm0, xmm7
0x1800593ec  addss   xmm1, xmm6
0x1800593f0  subss   xmm7, xmm3
0x1800593f4  movss   dword ptr [r11+rbx-4], xmm0
0x1800593fb  movss   dword ptr [r11+rbx], xmm1
0x180059401  subss   xmm5, xmm6
0x180059405  add     rbx, 8
0x180059409  movss   dword ptr [rdi-4], xmm7
0x18005940e  movss   dword ptr [rdi], xmm5
0x180059412  sub     rdi, 8
0x180059416  dec     rax
0x180059419  jnz     loc_18005938D
0x18005941f  test    r8b, 1
0x180059423  jnz     short loc_18005944E
0x180059425  movsxd  rax, r8d
0x180059428  movss   xmm0, dword ptr [rcx+rax*4]
0x18005942d  mulss   xmm0, cs:__real@40000000
0x180059435  movss   dword ptr [rdx+rax*4], xmm0
0x18005943a  movss   xmm1, dword ptr [rcx+rax*4+4]
0x180059440  mulss   xmm1, cs:__real@c0000000
0x180059448  movss   dword ptr [rdx+rax*4+4], xmm1
0x18005944e  mov     rbx, [rsp+28h+arg_0]
0x180059453  movaps  xmm6, [rsp+28h+var_18]
0x180059458  movaps  xmm7, [rsp+28h+var_28]
0x18005945c  add     rsp, 20h
0x180059460  pop     rdi
0x180059461  retn
```
