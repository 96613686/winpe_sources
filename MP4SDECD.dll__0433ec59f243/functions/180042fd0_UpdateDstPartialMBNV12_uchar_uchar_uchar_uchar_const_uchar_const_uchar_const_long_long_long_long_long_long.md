# UpdateDstPartialMBNV12(uchar *,uchar *,uchar *,uchar const *,uchar const *,uchar const *,long,long,long,long,long,long)

- ea: `0x180042fd0`
- end: `0x180043115`
- name: `?UpdateDstPartialMBNV12@@YAXPEAE00PEBE11JJJJJJ@Z`
- size: `325`
- prototype: `void(unsigned __int8 *, unsigned __int8 *, unsigned __int8 *, const unsigned __int8 *, const unsigned __int8 *, const unsigned __int8 *, int, int, int, int, int, int)`
- caller_count: `0`
- callee_count: `2`
- tags: `installer_update`

## callees

- `0x180042fd0`
- `0x180045805`

## pseudocode

```c
void __fastcall UpdateDstPartialMBNV12(
        unsigned __int8 *a1,
        unsigned __int8 *a2,
        unsigned __int8 *a3,
        const unsigned __int8 *a4,
        const unsigned __int8 *a5,
        const unsigned __int8 *a6,
        int a7,
        int a8,
        int a9,
        int a10,
        int a11,
        int a12)
{
  int v12; // edi
  const unsigned __int8 *v13; // rax
  int v15; // esi
  size_t v16; // r9
  __int64 v19; // r8
  unsigned __int8 *v20; // rdx
  unsigned __int8 v21; // al
  __int64 v22; // [rsp+20h] [rbp-48h]
  __int64 v23; // [rsp+28h] [rbp-40h]
  unsigned __int8 *v24; // [rsp+70h] [rbp+8h]
  const unsigned __int8 *v25; // [rsp+88h] [rbp+20h]

  v25 = a4;
  v24 = a1;
  v12 = 0;
  v13 = a4;
  v15 = a11 >> 1;
  if ( a12 >> 1 > 0 )
  {
    v16 = a11;
    v22 = 2LL * a7;
    v23 = 2LL * a9;
    do
    {
      memcpy_0(a1, v13, v16);
      memcpy_0(&v24[a9], &v25[a7], a11);
      v19 = 0;
      v20 = a3;
      v13 = &v25[v22];
      a1 = &v24[v23];
      v25 += v22;
      v24 += v23;
      if ( v15 > 0 )
      {
        do
        {
          *v20 = a5[v19];
          v20 += 2;
          v21 = a6[v19];
          v19 = (unsigned int)(v19 + 1);
          *(v20 - 1) = v21;
        }
        while ( (int)v19 < v15 );
        v13 = v25;
        a1 = v24;
      }
      v16 = a11;
      a5 += a8;
      a6 += a8;
      a3 += 2 * a10;
      ++v12;
    }
    while ( v12 < a12 >> 1 );
  }
}

```

## disassembly

```asm
0x180042fd0  mov     [rsp+arg_8], rbx
0x180042fd5  mov     [rsp+arg_18], r9
0x180042fda  mov     [rsp+arg_0], rcx
0x180042fdf  push    rbp
0x180042fe0  push    rsi
0x180042fe1  push    rdi
0x180042fe2  push    r12
0x180042fe4  push    r13
0x180042fe6  push    r14
0x180042fe8  push    r15
0x180042fea  sub     rsp, 30h
0x180042fee  mov     ebx, [rsp+68h+arg_58]
0x180042ff5  xor     edi, edi
0x180042ff7  mov     esi, [rsp+68h+arg_50]
0x180042ffe  mov     rax, r9
0x180043001  sar     ebx, 1
0x180043003  mov     rbp, r8
0x180043006  sar     esi, 1
0x180043008  test    ebx, ebx
0x18004300a  jle     loc_180043100
0x180043010  movsxd  rdx, [rsp+68h+arg_30]
0x180043018  movsxd  r8, [rsp+68h+arg_40]
0x180043020  add     rdx, rdx
0x180043023  movsxd  r13, [rsp+68h+arg_48]
0x18004302b  movsxd  r9, [rsp+68h+arg_50]
0x180043033  add     r13, r13
0x180043036  movsxd  r12, [rsp+68h+arg_38]
0x18004303e  mov     r14, [rsp+68h+arg_28]
0x180043046  mov     r15, [rsp+68h+arg_20]
0x18004304e  mov     [rsp+68h+var_48], rdx
0x180043053  lea     rdx, [r8+r8]
0x180043057  mov     [rsp+68h+var_40], rdx
0x18004305c  mov     r8, r9; Size
0x18004305f  mov     rdx, rax; Src
0x180043062  call    memcpy_0
0x180043067  movsxd  rdx, [rsp+68h+arg_30]
0x18004306f  movsxd  rcx, [rsp+68h+arg_40]
0x180043077  add     rdx, [rsp+68h+arg_18]; Src
0x18004307f  add     rcx, [rsp+68h+arg_0]; void *
0x180043084  movsxd  r8, [rsp+68h+arg_50]; Size
0x18004308c  call    memcpy_0
0x180043091  mov     rax, [rsp+68h+arg_18]
0x180043099  xor     r8d, r8d
0x18004309c  mov     rcx, [rsp+68h+arg_0]
0x1800430a1  mov     rdx, rbp
0x1800430a4  add     rax, [rsp+68h+var_48]
0x1800430a9  add     rcx, [rsp+68h+var_40]
0x1800430ae  mov     [rsp+68h+arg_18], rax
0x1800430b6  mov     [rsp+68h+arg_0], rcx
0x1800430bb  test    esi, esi
0x1800430bd  jle     short loc_1800430E5
0x1800430bf  mov     al, [r8+r15]
0x1800430c3  mov     [rdx], al
0x1800430c5  lea     rdx, [rdx+2]
0x1800430c9  mov     al, [r8+r14]
0x1800430cd  inc     r8d
0x1800430d0  mov     [rdx-1], al
0x1800430d3  cmp     r8d, esi
0x1800430d6  jl      short loc_1800430BF
0x1800430d8  mov     rax, [rsp+68h+arg_18]
0x1800430e0  mov     rcx, [rsp+68h+arg_0]
0x1800430e5  movsxd  r9, [rsp+68h+arg_50]
0x1800430ed  add     r15, r12
0x1800430f0  add     r14, r12
0x1800430f3  add     rbp, r13
0x1800430f6  inc     edi
0x1800430f8  cmp     edi, ebx
0x1800430fa  jl      loc_18004305C
0x180043100  mov     rbx, [rsp+68h+arg_8]
0x180043105  add     rsp, 30h
0x180043109  pop     r15
0x18004310b  pop     r14
0x18004310d  pop     r13
0x18004310f  pop     r12
0x180043111  pop     rdi
0x180043112  pop     rsi
0x180043113  pop     rbp
0x180043114  retn
```
