# CreateNewEventEntry

- ea: `0x180011b94`
- end: `0x180011dbb`
- name: `CreateNewEventEntry`
- size: `551`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x180011104`

## callees

- `0x180011b94`
- `0x180011dc4`
- `0x180012290`
- `0x18001b79d`

## pseudocode

```c
__int64 __fastcall CreateNewEventEntry(__int128 *a1, unsigned __int8 a2, __int64 a3, char a4, int a5, _QWORD *a6)
{
  __int64 v6; // r10
  __int64 v7; // r11
  unsigned __int8 v8; // r13
  unsigned __int8 v9; // bl
  __int64 v11; // rcx
  __int64 v12; // rax
  unsigned __int64 v14; // rdi
  unsigned __int64 v15; // rbx
  __int64 v16; // r14
  _OWORD *v17; // rsi
  unsigned __int8 v18; // r12
  unsigned __int8 v19; // r15
  __int64 v20; // rax
  __int64 v21; // rdi
  size_t v22; // r8
  void *v23; // rax
  unsigned __int8 v24; // r12
  __int128 v25; // xmm0
  __int64 v26; // r14
  __int64 v27; // rdi
  unsigned int v28; // edx
  void *NextOffset; // rbx
  void *v30; // [rsp+28h] [rbp-30h]
  __int64 v31; // [rsp+30h] [rbp-28h]
  _OWORD v32[2]; // [rsp+38h] [rbp-20h] BYREF

  v6 = 0;
  v7 = 0;
  v8 = a2;
  v9 = 0;
  *a6 = 0;
  v32[0] = 0;
  if ( a2 )
  {
    do
    {
      v11 = *(unsigned int *)(a3 + 16LL * v9 + 8);
      if ( v9 >= 2u )
        v6 += v11;
      v12 = v11 + v7;
      if ( v9 >= 2u )
        v12 = v7;
      ++v9;
      v7 = v12;
    }
    while ( v9 < a2 );
    if ( (unsigned __int64)(v6 + v12) > 0xFFFF )
      return 534;
  }
  v14 = 16LL * a2;
  if ( !(unsigned int)CBufferAllocate(v32, v6 + v14 + 46) )
    return 8;
  v15 = *((_QWORD *)&v32[0] + 1);
  if ( v14 && *((_QWORD *)&v32[0] + 1) >= v14 )
  {
    v16 = *(_QWORD *)&v32[0];
    v15 = *((_QWORD *)&v32[0] + 1) - v14;
    *((_QWORD *)&v32[0] + 1) -= v14;
    v17 = (_OWORD *)(v14 + *(_QWORD *)&v32[0]);
    *(_QWORD *)&v32[0] += v14;
  }
  else
  {
    v17 = *(_OWORD **)&v32[0];
    v16 = 0;
  }
  v18 = 0;
  v19 = a4 + 2;
  if ( v19 )
  {
    v20 = 0;
    v31 = 0;
    do
    {
      v21 = 2 * v20;
      if ( v18 >= 2u )
      {
        v22 = *(unsigned int *)(a3 + 16 * v20 + 8);
        if ( *(_DWORD *)(a3 + 16 * v20 + 8) && v15 >= v22 )
        {
          v23 = v17;
          v17 = (_OWORD *)((char *)v17 + v22);
          v15 -= v22;
          *(_QWORD *)&v32[0] = v17;
          *((_QWORD *)&v32[0] + 1) = v15;
        }
        else
        {
          v23 = 0;
        }
        v30 = v23;
        memcpy_0(v23, *(const void **)(a3 + 8 * v21), v22);
        *(_QWORD *)(v16 + 8 * v21) = v30;
        *(_DWORD *)(v16 + 8 * v21 + 12) = *(_DWORD *)(a3 + 8 * v21 + 12);
        *(_DWORD *)(v16 + 8 * v21 + 8) = *(_DWORD *)(a3 + 8 * v21 + 8);
        v20 = v31;
      }
      else
      {
        *(_OWORD *)(v16 + 16 * v20) = *(_OWORD *)(a3 + 16 * v20);
      }
      ++v20;
      ++v18;
      v31 = v20;
    }
    while ( v18 < v19 );
    v8 = a2;
  }
  if ( v15 < 0x2E )
  {
    v17 = 0;
  }
  else
  {
    *(_QWORD *)&v32[0] = (char *)v17 + 46;
    *((_QWORD *)&v32[0] + 1) = v15 - 46;
  }
  v24 = v19;
  *((_QWORD *)v17 + 2) = v16;
  v25 = *a1;
  *((_BYTE *)v17 + 45) = a4;
  *((_DWORD *)v17 + 10) = a5;
  *((_BYTE *)v17 + 44) = v8;
  *v17 = v25;
  if ( v19 < v8 )
  {
    v26 = v19;
    do
    {
      v27 = 2 * v26;
      NextOffset = (void *)CBufferGetNextOffset(v32, *(unsigned int *)(a3 + 16 * v26 + 8));
      memcpy_0(NextOffset, *(const void **)(a3 + 16 * v26), v28);
      ++v24;
      ++v26;
      *(_QWORD *)(*((_QWORD *)v17 + 2) + 8 * v27) = NextOffset;
      *(_DWORD *)(*((_QWORD *)v17 + 2) + 8 * v27 + 12) = *(_DWORD *)(a3 + 8 * v27 + 12);
      *(_DWORD *)(*((_QWORD *)v17 + 2) + 8 * v27 + 8) = *(_DWORD *)(a3 + 8 * v27 + 8);
    }
    while ( v24 < v8 );
  }
  *a6 = v17;
  return 0;
}

```

## disassembly

```asm
0x180011b94  mov     rax, rsp
0x180011b97  mov     [rax+20h], r9b
0x180011b9b  mov     [rax+18h], r8
0x180011b9f  mov     [rax+10h], dl
0x180011ba2  mov     [rax+8], rcx
0x180011ba6  push    rbp
0x180011ba7  push    rbx
0x180011ba8  push    rsi
0x180011ba9  push    rdi
0x180011baa  push    r12
0x180011bac  push    r13
0x180011bae  push    r14
0x180011bb0  push    r15
0x180011bb2  mov     rbp, rsp
0x180011bb5  sub     rsp, 58h
0x180011bb9  mov     rax, [rbp+arg_28]
0x180011bbd  xor     r10d, r10d
0x180011bc0  xor     r11d, r11d
0x180011bc3  movzx   r13d, dl
0x180011bc7  xor     bl, bl
0x180011bc9  xorps   xmm0, xmm0
0x180011bcc  mov     r15b, r9b
0x180011bcf  mov     [rax], r10
0x180011bd2  movups  [rbp+var_20], xmm0
0x180011bd6  test    dl, dl
0x180011bd8  jz      short loc_180011C17
0x180011bda  movzx   eax, bl
0x180011bdd  add     rax, rax
0x180011be0  cmp     bl, 2
0x180011be3  mov     ecx, [r8+rax*8+8]
0x180011be8  lea     rax, [rcx+r10]
0x180011bec  cmovnb  r10, rax
0x180011bf0  lea     rax, [rcx+r11]
0x180011bf4  cmovnb  rax, r11
0x180011bf8  inc     bl
0x180011bfa  mov     r11, rax
0x180011bfd  cmp     bl, r13b
0x180011c00  jb      short loc_180011BDA
0x180011c02  add     rax, r10
0x180011c05  cmp     rax, 0FFFFh
0x180011c0b  jbe     short loc_180011C17
0x180011c0d  mov     eax, 216h
0x180011c12  jmp     loc_180011DA9
0x180011c17  mov     rdi, r13
0x180011c1a  lea     rcx, [rbp+var_20]
0x180011c1e  shl     rdi, 4
0x180011c22  lea     rdx, [rdi+2Eh]
0x180011c26  add     rdx, r10
0x180011c29  call    CBufferAllocate
0x180011c2e  test    eax, eax
0x180011c30  jnz     short loc_180011C3C
0x180011c32  mov     eax, 8
0x180011c37  jmp     loc_180011DA9
0x180011c3c  mov     rbx, qword ptr [rbp+var_20+8]
0x180011c40  test    rdi, rdi
0x180011c43  jz      short loc_180011C5F
0x180011c45  cmp     rbx, rdi
0x180011c48  jb      short loc_180011C5F
0x180011c4a  mov     r14, qword ptr [rbp+var_20]
0x180011c4e  sub     rbx, rdi
0x180011c51  mov     qword ptr [rbp+var_20+8], rbx
0x180011c55  lea     rsi, [rdi+r14]
0x180011c59  mov     qword ptr [rbp+var_20], rsi
0x180011c5d  jmp     short loc_180011C66
0x180011c5f  mov     rsi, qword ptr [rbp+var_20]
0x180011c63  xor     r14d, r14d
0x180011c66  xor     r12b, r12b
0x180011c69  add     r15b, 2
0x180011c6d  mov     byte ptr [rbp+var_38], r15b
0x180011c71  jz      loc_180011D03
0x180011c77  mov     r13, [rbp+arg_10]
0x180011c7b  xor     eax, eax
0x180011c7d  mov     [rbp+var_28], rax
0x180011c81  mov     rdi, rax
0x180011c84  add     rdi, rdi
0x180011c87  cmp     r12b, 2
0x180011c8b  jnb     short loc_180011C9B
0x180011c8d  movups  xmm0, xmmword ptr [r13+rdi*8+0]
0x180011c93  movdqu  xmmword ptr [r14+rdi*8], xmm0
0x180011c99  jmp     short loc_180011CF0
0x180011c9b  mov     r8d, [r13+rdi*8+8]; Size
0x180011ca0  test    r8, r8
0x180011ca3  jz      short loc_180011CBD
0x180011ca5  cmp     rbx, r8
0x180011ca8  jb      short loc_180011CBD
0x180011caa  mov     rax, rsi
0x180011cad  add     rsi, r8
0x180011cb0  sub     rbx, r8
0x180011cb3  mov     qword ptr [rbp+var_20], rsi
0x180011cb7  mov     qword ptr [rbp+var_20+8], rbx
0x180011cbb  jmp     short loc_180011CBF
0x180011cbd  xor     eax, eax
0x180011cbf  mov     rdx, [r13+rdi*8+0]; Src
0x180011cc4  mov     rcx, rax; void *
0x180011cc7  mov     [rbp+var_30], rax
0x180011ccb  call    memcpy_0
0x180011cd0  mov     rax, [rbp+var_30]
0x180011cd4  mov     [r14+rdi*8], rax
0x180011cd8  mov     eax, [r13+rdi*8+0Ch]
0x180011cdd  mov     [r14+rdi*8+0Ch], eax
0x180011ce2  mov     eax, [r13+rdi*8+8]
0x180011ce7  mov     [r14+rdi*8+8], eax
0x180011cec  mov     rax, [rbp+var_28]
0x180011cf0  inc     rax
0x180011cf3  inc     r12b
0x180011cf6  mov     [rbp+var_28], rax
0x180011cfa  cmp     r12b, r15b
0x180011cfd  jb      short loc_180011C81
0x180011cff  mov     r13b, [rbp+arg_8]
0x180011d03  cmp     rbx, 2Eh ; '.'
0x180011d07  jb      short loc_180011D1B
0x180011d09  lea     rax, [rsi+2Eh]
0x180011d0d  mov     qword ptr [rbp+var_20], rax
0x180011d11  lea     rax, [rbx-2Eh]
0x180011d15  mov     qword ptr [rbp+var_20+8], rax
0x180011d19  jmp     short loc_180011D1D
0x180011d1b  xor     esi, esi
0x180011d1d  mov     rax, [rbp+arg_0]
0x180011d21  mov     r12d, [rbp+var_38]
0x180011d25  mov     [rsi+10h], r14
0x180011d29  movups  xmm0, xmmword ptr [rax]
0x180011d2c  mov     al, [rbp+arg_18]
0x180011d2f  mov     [rsi+2Dh], al
0x180011d32  mov     eax, [rbp+arg_20]
0x180011d35  mov     [rsi+28h], eax
0x180011d38  mov     [rsi+2Ch], r13b
0x180011d3c  movdqu  xmmword ptr [rsi], xmm0
0x180011d40  cmp     r12b, r13b
0x180011d43  jnb     short loc_180011DA0
0x180011d45  movzx   r14d, r15b
0x180011d49  mov     r15, [rbp+arg_10]
0x180011d4d  mov     rdi, r14
0x180011d50  lea     rcx, [rbp+var_20]
0x180011d54  add     rdi, rdi
0x180011d57  mov     edx, [r15+rdi*8+8]
0x180011d5c  call    CBufferGetNextOffset
0x180011d61  mov     r8d, edx; Size
0x180011d64  mov     rcx, rax; void *
0x180011d67  mov     rdx, [r15+rdi*8]; Src
0x180011d6b  mov     rbx, rax
0x180011d6e  call    memcpy_0
0x180011d73  mov     rcx, [rsi+10h]
0x180011d77  inc     r12b
0x180011d7a  inc     r14
0x180011d7d  mov     [rcx+rdi*8], rbx
0x180011d81  mov     rcx, [rsi+10h]
0x180011d85  mov     eax, [r15+rdi*8+0Ch]
0x180011d8a  mov     [rcx+rdi*8+0Ch], eax
0x180011d8e  mov     rcx, [rsi+10h]
0x180011d92  mov     eax, [r15+rdi*8+8]
0x180011d97  mov     [rcx+rdi*8+8], eax
0x180011d9b  cmp     r12b, r13b
0x180011d9e  jb      short loc_180011D4D
0x180011da0  mov     rax, [rbp+arg_28]
0x180011da4  mov     [rax], rsi
0x180011da7  xor     eax, eax
0x180011da9  add     rsp, 58h
0x180011dad  pop     r15
0x180011daf  pop     r14
0x180011db1  pop     r13
0x180011db3  pop     r12
0x180011db5  pop     rdi
0x180011db6  pop     rsi
0x180011db7  pop     rbx
0x180011db8  pop     rbp
0x180011db9  retn
```
