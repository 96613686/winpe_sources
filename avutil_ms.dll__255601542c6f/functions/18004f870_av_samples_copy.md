# av_samples_copy

- ea: `0x18004f870`
- end: `0x18004f98d`
- name: `av_samples_copy`
- size: `285`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x18003bf24`

## callees

- `0x18004f870`
- `0x18007a960`

## pseudocode

```c
__int64 __fastcall av_samples_copy(char *a1, char *a2, int a3, int a4, int a5, int a6, unsigned int a7)
{
  char *v8; // rbx
  int v11; // r9d
  int v12; // r8d
  int v13; // r10d
  int v14; // eax
  unsigned __int64 v15; // rcx
  __int64 v16; // rdx
  int v17; // r8d
  int v18; // r9d
  int v19; // r11d
  int v20; // r8d
  int v21; // r11d
  __int64 v22; // rsi
  unsigned __int64 v23; // rbp
  __int64 v24; // r14
  signed __int64 v25; // rdi
  __int64 v26; // r15

  v8 = a1;
  if ( a7 > 0xB )
    v11 = 0;
  else
    v11 = *((_DWORD *)&qword_1800934B0 + 5 * (int)a7 + 3);
  v12 = a6;
  v13 = 1;
  if ( v11 )
    v13 = a6;
  if ( a7 > 0xB )
    v14 = 0;
  else
    v14 = *((int *)&qword_1800934B0 + 5 * (int)a7 + 2) >> 3;
  v15 = *(_QWORD *)a1;
  if ( v11 )
    v12 = 1;
  v16 = *(_QWORD *)a2 - v15;
  v17 = v14 * v12;
  v18 = a3 * v17;
  v19 = v17;
  v20 = a5 * v17;
  v21 = a4 * v19;
  v22 = v13;
  if ( v15 >= *(_QWORD *)a2 )
    v16 = v15 - *(_QWORD *)a2;
  v23 = v20;
  if ( v13 > 0 )
  {
    v24 = v21;
    v25 = a2 - v8;
    v26 = v18;
    _mm_lfence();
    if ( v16 < v20 )
    {
      do
      {
        sub_18007A960((__m128i *)(v26 + *(_QWORD *)v8), (const __m128i *)(v24 + *(_QWORD *)&v8[v25]), v23);
        v8 += 8;
        --v22;
      }
      while ( v22 );
    }
    else
    {
      do
      {
        sub_18007A960((__m128i *)(v26 + *(_QWORD *)v8), (const __m128i *)(v24 + *(_QWORD *)&v8[v25]), v23);
        v8 += 8;
        --v22;
      }
      while ( v22 );
    }
  }
  return 0;
}

```

## disassembly

```asm
0x18004f870  mov     rax, rsp
0x18004f873  mov     [rax+8], rbx
0x18004f877  mov     [rax+10h], rbp
0x18004f87b  mov     [rax+18h], rsi
0x18004f87f  mov     [rax+20h], rdi
0x18004f883  push    r12
0x18004f885  push    r14
0x18004f887  push    r15
0x18004f889  sub     rsp, 20h
0x18004f88d  mov     rdi, rdx
0x18004f890  lea     rax, qword_1800934B0
0x18004f897  movsxd  rdx, [rsp+38h+arg_30]
0x18004f89c  mov     rbx, rcx
0x18004f89f  mov     esi, r9d
0x18004f8a2  mov     r11d, r8d
0x18004f8a5  lea     rcx, [rdx+rdx*4]
0x18004f8a9  cmp     edx, 0Bh
0x18004f8ac  ja      short loc_18004F8B5
0x18004f8ae  mov     r9d, [rax+rcx*4+0Ch]
0x18004f8b3  jmp     short loc_18004F8B8
0x18004f8b5  xor     r9d, r9d
0x18004f8b8  mov     r8d, [rsp+38h+arg_28]
0x18004f8bd  test    r9d, r9d
0x18004f8c0  mov     r12d, 1
0x18004f8c6  mov     r10d, r12d
0x18004f8c9  cmovnz  r10d, r8d
0x18004f8cd  cmp     edx, 0Bh
0x18004f8d0  ja      short loc_18004F8DB
0x18004f8d2  mov     eax, [rax+rcx*4+8]
0x18004f8d6  sar     eax, 3
0x18004f8d9  jmp     short loc_18004F8DD
0x18004f8db  xor     eax, eax
0x18004f8dd  mov     rcx, [rbx]
0x18004f8e0  test    r9d, r9d
0x18004f8e3  mov     rdx, [rdi]
0x18004f8e6  cmovnz  r8d, r12d
0x18004f8ea  sub     rdx, rcx
0x18004f8ed  imul    r8d, eax
0x18004f8f1  mov     rax, rcx
0x18004f8f4  sub     rax, [rdi]
0x18004f8f7  mov     r9d, r8d
0x18004f8fa  imul    r9d, r11d
0x18004f8fe  mov     r11d, r8d
0x18004f901  imul    r8d, [rsp+38h+arg_20]
0x18004f907  imul    r11d, esi
0x18004f90b  cmp     rcx, [rdi]
0x18004f90e  movsxd  rsi, r10d
0x18004f911  cmovnb  rdx, rax
0x18004f915  movsxd  rbp, r8d
0x18004f918  test    r10d, r10d
0x18004f91b  jle     short loc_18004F96C
0x18004f91d  movsxd  r14, r11d
0x18004f920  sub     rdi, rbx
0x18004f923  movsxd  r15, r9d
0x18004f926  lfence
0x18004f929  cmp     rdx, rbp
0x18004f92c  jl      short loc_18004F94E
0x18004f92e  mov     rdx, [rbx+rdi]
0x18004f932  mov     r8, rbp
0x18004f935  mov     rcx, [rbx]
0x18004f938  add     rdx, r14
0x18004f93b  add     rcx, r15
0x18004f93e  call    sub_18007A960
0x18004f943  lea     rbx, [rbx+8]
0x18004f947  sub     rsi, r12
0x18004f94a  jnz     short loc_18004F92E
0x18004f94c  jmp     short loc_18004F96C
0x18004f94e  mov     rdx, [rdi+rbx]
0x18004f952  mov     r8, rbp
0x18004f955  mov     rcx, [rbx]
0x18004f958  add     rdx, r14
0x18004f95b  add     rcx, r15
0x18004f95e  call    sub_18007A960
0x18004f963  lea     rbx, [rbx+8]
0x18004f967  sub     rsi, r12
0x18004f96a  jnz     short loc_18004F94E
0x18004f96c  mov     rbx, [rsp+38h+arg_0]
0x18004f971  xor     eax, eax
0x18004f973  mov     rbp, [rsp+38h+arg_8]
0x18004f978  mov     rsi, [rsp+38h+arg_10]
0x18004f97d  mov     rdi, [rsp+38h+arg_18]
0x18004f982  add     rsp, 20h
0x18004f986  pop     r15
0x18004f988  pop     r14
0x18004f98a  pop     r12
0x18004f98c  retn
```
