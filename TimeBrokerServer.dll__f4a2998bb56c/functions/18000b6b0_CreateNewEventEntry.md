# CreateNewEventEntry

- ea: `0x18000b6b0`
- end: `0x18000b95a`
- name: `CreateNewEventEntry`
- size: `682`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x18000aa90`
- `0x18000b0d0`

## callees

- `0x18000b6b0`
- `0x180019d47`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000b751`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000b751`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000b762`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000b762`

## pseudocode

```c
__int64 __fastcall CreateNewEventEntry(__int128 *a1, unsigned __int8 a2, __int64 a3, char a4, int a5, char **a6)
{
  __int64 v6; // rsi
  __int64 v7; // rax
  __int64 v8; // r11
  unsigned __int8 v9; // r10
  char v10; // r12
  __int64 v12; // rdx
  __int64 v13; // rcx
  unsigned __int64 v14; // rdi
  SIZE_T v15; // rbx
  HANDLE ProcessHeap; // rax
  char *v17; // rax
  char *v18; // r15
  char *v19; // rbp
  unsigned __int8 v20; // r14
  unsigned __int8 v21; // di
  unsigned __int8 v22; // cl
  __int64 v23; // rax
  __int64 v24; // r12
  size_t v25; // r8
  char *v26; // rax
  char *v27; // r14
  __int128 v28; // xmm0
  __int64 v29; // r15
  __int64 v30; // rdi
  size_t v31; // r8
  char *v32; // r12
  int v33; // ecx
  char *v35; // [rsp+20h] [rbp-48h]
  __int64 v36; // [rsp+28h] [rbp-40h]
  int v38; // [rsp+78h] [rbp+10h]

  v6 = a2;
  v7 = 0;
  v8 = 0;
  v9 = 0;
  v10 = a4;
  *a6 = 0;
  if ( a2 )
  {
    do
    {
      v12 = *(unsigned int *)(a3 + 16LL * v9 + 8);
      if ( v9 >= 2u )
        v7 += v12;
      v13 = v12 + v8;
      if ( v9 >= 2u )
        v13 = v8;
      ++v9;
      v8 = v13;
    }
    while ( v9 < (unsigned __int8)v6 );
    if ( (unsigned __int64)(v7 + v13) > 0xFFFF )
      return 534;
  }
  v14 = 16 * v6;
  v15 = v7 + 16 * v6 + 46;
  if ( !v15 )
    return 8;
  ProcessHeap = GetProcessHeap();
  v17 = (char *)HeapAlloc(ProcessHeap, 8u, v15);
  v18 = v17;
  if ( !v17 )
    return 8;
  if ( v14 && v15 >= v14 )
  {
    v19 = &v17[v14];
    v15 -= v14;
  }
  else
  {
    v19 = v17;
    v18 = 0;
  }
  v20 = 0;
  v21 = v10 + 2;
  v22 = v10 + 2;
  v38 = (unsigned __int8)(v10 + 2);
  if ( v10 != -2 )
  {
    v23 = 0;
    v36 = 0;
    do
    {
      v24 = 2 * v23;
      if ( v20 < 2u )
      {
        *(_OWORD *)&v18[16 * v23] = *(_OWORD *)(a3 + 16 * v23);
      }
      else
      {
        v25 = *(unsigned int *)(a3 + 16 * v23 + 8);
        if ( *(_DWORD *)(a3 + 16 * v23 + 8) && v15 >= v25 )
        {
          v26 = v19;
          v19 += v25;
          v15 -= v25;
        }
        else
        {
          v26 = 0;
        }
        v35 = v26;
        memcpy_0(v26, *(const void **)(a3 + 8 * v24), v25);
        *(_QWORD *)&v18[8 * v24] = v35;
        *(_DWORD *)&v18[8 * v24 + 12] = *(_DWORD *)(a3 + 8 * v24 + 12);
        *(_DWORD *)&v18[8 * v24 + 8] = *(_DWORD *)(a3 + 8 * v24 + 8);
        v23 = v36;
      }
      ++v23;
      ++v20;
      v36 = v23;
    }
    while ( v20 < v21 );
    v22 = v38;
    v10 = a4;
  }
  if ( v15 < 0x2E )
  {
    v27 = 0;
  }
  else
  {
    v27 = v19;
    v19 += 46;
    v15 -= 46LL;
  }
  *((_QWORD *)v27 + 2) = v18;
  v28 = *a1;
  v27[44] = v6;
  v27[45] = v10;
  *((_DWORD *)v27 + 10) = a5;
  *(_OWORD *)v27 = v28;
  if ( v22 < (unsigned __int8)v6 )
  {
    v29 = v21;
    do
    {
      v30 = 2 * v29;
      v31 = *(unsigned int *)(a3 + 16 * v29 + 8);
      if ( *(_DWORD *)(a3 + 16 * v29 + 8) && v15 >= v31 )
      {
        v32 = v19;
        v19 += v31;
        v15 -= v31;
      }
      else
      {
        v32 = 0;
      }
      memcpy_0(v32, *(const void **)(a3 + 16 * v29++), v31);
      *(_QWORD *)(*((_QWORD *)v27 + 2) + 8 * v30) = v32;
      *(_DWORD *)(*((_QWORD *)v27 + 2) + 8 * v30 + 12) = *(_DWORD *)(a3 + 8 * v30 + 12);
      *(_DWORD *)(*((_QWORD *)v27 + 2) + 8 * v30 + 8) = *(_DWORD *)(a3 + 8 * v30 + 8);
      v33 = v38;
      LOBYTE(v33) = v38 + 1;
      v38 = v33;
    }
    while ( (unsigned __int8)v33 < (unsigned __int8)v6 );
  }
  *a6 = v27;
  return 0;
}

```

## disassembly

```asm
0x18000b6b0  mov     [rsp+arg_18], r9b
0x18000b6b5  mov     [rsp+arg_0], rcx
0x18000b6ba  push    rsi
0x18000b6bb  push    r12
0x18000b6bd  push    r13
0x18000b6bf  sub     rsp, 50h
0x18000b6c3  movzx   esi, dl
0x18000b6c6  xor     eax, eax
0x18000b6c8  mov     rdx, [rsp+68h+arg_28]
0x18000b6d0  xor     r11d, r11d
0x18000b6d3  xor     r10b, r10b
0x18000b6d6  movzx   r12d, r9b
0x18000b6da  mov     r13, r8
0x18000b6dd  mov     [rdx], rax
0x18000b6e0  test    sil, sil
0x18000b6e3  jz      short loc_18000B72B
0x18000b6e5  nop     word ptr [rax+rax+00000000h]
0x18000b6f0  movzx   ecx, r10b
0x18000b6f4  add     rcx, rcx
0x18000b6f7  cmp     r10b, 2
0x18000b6fb  mov     edx, [r8+rcx*8+8]
0x18000b700  lea     rcx, [rdx+rax]
0x18000b704  cmovnb  rax, rcx
0x18000b708  lea     rcx, [rdx+r11]
0x18000b70c  cmovnb  rcx, r11
0x18000b710  inc     r10b
0x18000b713  mov     r11, rcx
0x18000b716  cmp     r10b, sil
0x18000b719  jb      short loc_18000B6F0
0x18000b71b  add     rcx, rax
0x18000b71e  cmp     rcx, 0FFFFh
0x18000b725  ja      loc_18000B931
0x18000b72b  mov     [rsp+68h+arg_10], rbx
0x18000b733  mov     [rsp+68h+var_28], rdi
0x18000b738  mov     rdi, rsi
0x18000b73b  shl     rdi, 4
0x18000b73f  mov     [rsp+68h+var_38], r15
0x18000b744  lea     rbx, [rdi+2Eh]
0x18000b748  add     rbx, rax
0x18000b74b  jz      loc_18000B91A
0x18000b751  call    cs:__imp_GetProcessHeap
0x18000b757  mov     r8, rbx; dwBytes
0x18000b75a  mov     edx, 8; dwFlags
0x18000b75f  mov     rcx, rax; hHeap
0x18000b762  call    cs:__imp_HeapAlloc
0x18000b768  mov     r15, rax
0x18000b76b  test    rax, rax
0x18000b76e  jz      loc_18000B91A
0x18000b774  mov     [rsp+68h+var_30], r14
0x18000b779  mov     [rsp+68h+var_20], rbp
0x18000b77e  test    rdi, rdi
0x18000b781  jz      loc_18000B938
0x18000b787  cmp     rbx, rdi
0x18000b78a  jb      loc_18000B938
0x18000b790  lea     rbp, [rdi+rax]
0x18000b794  sub     rbx, rdi
0x18000b797  xor     r14b, r14b
0x18000b79a  movzx   edi, r12b
0x18000b79e  add     dil, 2
0x18000b7a2  movzx   ecx, dil
0x18000b7a6  mov     [rsp+68h+arg_8], ecx
0x18000b7aa  jz      loc_18000B838
0x18000b7b0  xor     eax, eax
0x18000b7b2  mov     [rsp+68h+var_40], rax
0x18000b7b7  mov     r12, rax
0x18000b7ba  add     r12, r12
0x18000b7bd  cmp     r14b, 2
0x18000b7c1  jb      loc_18000B921
0x18000b7c7  mov     r8d, [r13+r12*8+8]; Size
0x18000b7cc  test    r8, r8
0x18000b7cf  jz      loc_18000B943
0x18000b7d5  cmp     rbx, r8
0x18000b7d8  jb      loc_18000B943
0x18000b7de  mov     rax, rbp
0x18000b7e1  add     rbp, r8
0x18000b7e4  sub     rbx, r8
0x18000b7e7  mov     rdx, [r13+r12*8+0]; Src
0x18000b7ec  mov     rcx, rax; void *
0x18000b7ef  mov     [rsp+68h+var_48], rax
0x18000b7f4  call    memcpy_0
0x18000b7f9  mov     rax, [rsp+68h+var_48]
0x18000b7fe  mov     [r15+r12*8], rax
0x18000b802  mov     eax, [r13+r12*8+0Ch]
0x18000b807  mov     [r15+r12*8+0Ch], eax
0x18000b80c  mov     eax, [r13+r12*8+8]
0x18000b811  mov     [r15+r12*8+8], eax
0x18000b816  mov     rax, [rsp+68h+var_40]
0x18000b81b  inc     rax
0x18000b81e  inc     r14b
0x18000b821  mov     [rsp+68h+var_40], rax
0x18000b826  cmp     r14b, dil
0x18000b829  jb      short loc_18000B7B7
0x18000b82b  mov     ecx, [rsp+68h+arg_8]
0x18000b82f  movzx   r12d, [rsp+68h+arg_18]
0x18000b838  cmp     rbx, 2Eh ; '.'
0x18000b83c  jb      loc_18000B94A
0x18000b842  mov     r14, rbp
0x18000b845  add     rbp, 2Eh ; '.'
0x18000b849  sub     rbx, 2Eh ; '.'
0x18000b84d  mov     rax, [rsp+68h+arg_0]
0x18000b852  mov     [r14+10h], r15
0x18000b856  movups  xmm0, xmmword ptr [rax]
0x18000b859  mov     eax, [rsp+68h+arg_20]
0x18000b860  mov     [r14+2Ch], sil
0x18000b864  mov     [r14+2Dh], r12b
0x18000b868  mov     [r14+28h], eax
0x18000b86c  movups  xmmword ptr [r14], xmm0
0x18000b870  cmp     cl, sil
0x18000b873  jnb     short loc_18000B8E7
0x18000b875  movzx   r15d, dil
0x18000b879  nop     dword ptr [rax+00000000h]
0x18000b880  mov     rdi, r15
0x18000b883  add     rdi, rdi
0x18000b886  mov     r8d, [r13+rdi*8+8]; Size
0x18000b88b  test    r8, r8
0x18000b88e  jz      loc_18000B952
0x18000b894  cmp     rbx, r8
0x18000b897  jb      loc_18000B952
0x18000b89d  mov     r12, rbp
0x18000b8a0  add     rbp, r8
0x18000b8a3  sub     rbx, r8
0x18000b8a6  mov     rdx, [r13+rdi*8+0]; Src
0x18000b8ab  mov     rcx, r12; void *
0x18000b8ae  call    memcpy_0
0x18000b8b3  mov     rax, [r14+10h]
0x18000b8b7  inc     r15
0x18000b8ba  mov     [rax+rdi*8], r12
0x18000b8be  mov     rcx, [r14+10h]
0x18000b8c2  mov     eax, [r13+rdi*8+0Ch]
0x18000b8c7  mov     [rcx+rdi*8+0Ch], eax
0x18000b8cb  mov     rcx, [r14+10h]
0x18000b8cf  mov     eax, [r13+rdi*8+8]
0x18000b8d4  mov     [rcx+rdi*8+8], eax
0x18000b8d8  mov     ecx, [rsp+68h+arg_8]
0x18000b8dc  inc     cl
0x18000b8de  mov     [rsp+68h+arg_8], ecx
0x18000b8e2  cmp     cl, sil
0x18000b8e5  jb      short loc_18000B880
0x18000b8e7  mov     rax, [rsp+68h+arg_28]
0x18000b8ef  mov     rbp, [rsp+68h+var_20]
0x18000b8f4  mov     [rax], r14
0x18000b8f7  xor     eax, eax
0x18000b8f9  mov     r14, [rsp+68h+var_30]
0x18000b8fe  mov     rdi, [rsp+68h+var_28]
0x18000b903  mov     rbx, [rsp+68h+arg_10]
0x18000b90b  mov     r15, [rsp+68h+var_38]
0x18000b910  add     rsp, 50h
0x18000b914  pop     r13
0x18000b916  pop     r12
0x18000b918  pop     rsi
0x18000b919  retn
0x18000b91a  mov     eax, 8
0x18000b91f  jmp     short loc_18000B8FE
0x18000b921  movups  xmm0, xmmword ptr [r13+r12*8+0]
0x18000b927  movups  xmmword ptr [r15+r12*8], xmm0
0x18000b92c  jmp     loc_18000B81B
0x18000b931  mov     eax, 216h
0x18000b936  jmp     short loc_18000B910
0x18000b938  mov     rbp, rax
0x18000b93b  xor     r15d, r15d
0x18000b93e  jmp     loc_18000B797
0x18000b943  xor     eax, eax
0x18000b945  jmp     loc_18000B7E7
0x18000b94a  xor     r14d, r14d
0x18000b94d  jmp     loc_18000B84D
0x18000b952  xor     r12d, r12d
0x18000b955  jmp     loc_18000B8A6
```
