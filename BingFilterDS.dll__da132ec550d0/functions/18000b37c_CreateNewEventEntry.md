# CreateNewEventEntry

- ea: `0x18000b37c`
- end: `0x18000b5b4`
- name: `CreateNewEventEntry`
- size: `568`
- prototype: `__int64 __fastcall(__int128 *, unsigned __int8, __int64, char, int, char **)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x18000b870`

## callees

- `0x180002766`
- `0x18000b37c`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000b414`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000b414`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000b422`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000b422`

## pseudocode

```c
__int64 __fastcall CreateNewEventEntry(__int128 *a1, unsigned __int8 a2, __int64 a3, char a4, int a5, char **a6)
{
  __int64 v6; // r10
  __int64 v7; // r11
  unsigned __int8 v8; // r12
  unsigned __int8 v9; // bl
  __int64 v12; // rcx
  __int64 v13; // rax
  unsigned __int64 v15; // rdi
  SIZE_T v16; // rbx
  HANDLE ProcessHeap; // rax
  char *v18; // rax
  int v19; // edx
  char *v20; // rbp
  char *v21; // rsi
  unsigned __int8 v22; // r15
  bool v23; // zf
  unsigned __int8 v24; // r14
  __int64 v25; // r12
  size_t v26; // r8
  char *v27; // rax
  unsigned __int64 v28; // rcx
  char *v29; // rdi
  __int128 v30; // xmm0
  __int64 v31; // r15
  __int64 v32; // r14
  size_t v33; // r8
  char *v34; // rbp
  int v35; // edx
  int v36; // [rsp+20h] [rbp-48h]
  char *v37; // [rsp+28h] [rbp-40h]

  v6 = 0;
  v7 = 0;
  v8 = a2;
  v9 = 0;
  *a6 = 0;
  if ( a2 )
  {
    do
    {
      v12 = *(unsigned int *)(a3 + 16LL * v9 + 8);
      if ( v9 >= 2u )
        v6 += v12;
      v13 = v12 + v7;
      if ( v9 >= 2u )
        v13 = v7;
      ++v9;
      v7 = v13;
    }
    while ( v9 < a2 );
    if ( (unsigned __int64)(v6 + v13) > 0xFFFF )
      return 534;
  }
  v15 = 16LL * a2;
  v16 = v6 + v15 + 46;
  if ( !v16 )
    return 8;
  ProcessHeap = GetProcessHeap();
  v18 = (char *)HeapAlloc(ProcessHeap, 8u, v16);
  v20 = v18;
  if ( !v18 )
    return 8;
  if ( v15 && v16 >= v15 )
  {
    v21 = &v18[v15];
    v16 -= v15;
  }
  else
  {
    v21 = v18;
    v20 = 0;
  }
  v22 = 0;
  v23 = a4 == -2;
  v24 = a4 + 2;
  LOBYTE(v19) = v24;
  v36 = v19;
  if ( !v23 )
  {
    v25 = 0;
    do
    {
      if ( v22 >= 2u )
      {
        v26 = *(unsigned int *)(a3 + 16 * v25 + 8);
        if ( *(_DWORD *)(a3 + 16 * v25 + 8) && v16 >= v26 )
        {
          v27 = v21;
          v21 += v26;
          v16 -= v26;
        }
        else
        {
          v27 = 0;
        }
        v37 = v27;
        memcpy_0(v27, *(const void **)(a3 + 16 * v25), v26);
        *(_QWORD *)&v20[16 * v25] = v37;
        *(_DWORD *)&v20[16 * v25 + 12] = *(_DWORD *)(a3 + 16 * v25 + 12);
        *(_DWORD *)&v20[16 * v25 + 8] = *(_DWORD *)(a3 + 16 * v25 + 8);
      }
      else
      {
        *(_OWORD *)&v20[16 * v25] = *(_OWORD *)(a3 + 16 * v25);
      }
      ++v22;
      ++v25;
    }
    while ( v22 < v24 );
    v8 = a2;
    LOBYTE(v19) = v36;
  }
  v28 = v16;
  v29 = v21;
  if ( v16 >= 0x2E )
  {
    v21 += 46;
    v16 -= 46LL;
  }
  if ( v28 < 0x2E )
    v29 = 0;
  *((_QWORD *)v29 + 2) = v20;
  v30 = *a1;
  v29[45] = a4;
  *((_DWORD *)v29 + 10) = a5;
  v29[44] = v8;
  *(_OWORD *)v29 = v30;
  if ( (unsigned __int8)v19 < v8 )
  {
    v31 = v24;
    do
    {
      v32 = 2 * v31;
      v33 = *(unsigned int *)(a3 + 16 * v31 + 8);
      if ( *(_DWORD *)(a3 + 16 * v31 + 8) && v16 >= v33 )
      {
        v34 = v21;
        v21 += v33;
        v16 -= v33;
      }
      else
      {
        v34 = 0;
      }
      memcpy_0(v34, *(const void **)(a3 + 16 * v31++), v33);
      v35 = v36;
      LOBYTE(v35) = v36 + 1;
      v36 = v35;
      *(_QWORD *)(*((_QWORD *)v29 + 2) + 8 * v32) = v34;
      *(_DWORD *)(*((_QWORD *)v29 + 2) + 8 * v32 + 12) = *(_DWORD *)(a3 + 8 * v32 + 12);
      *(_DWORD *)(*((_QWORD *)v29 + 2) + 8 * v32 + 8) = *(_DWORD *)(a3 + 8 * v32 + 8);
    }
    while ( (unsigned __int8)v35 < v8 );
  }
  *a6 = v29;
  return 0;
}

```

## disassembly

```asm
0x18000b37c  mov     rax, rsp
0x18000b37f  mov     [rax+18h], rbx
0x18000b383  mov     [rax+20h], r9b
0x18000b387  mov     [rax+10h], dl
0x18000b38a  mov     [rax+8], rcx
0x18000b38e  push    rbp
0x18000b38f  push    rsi
0x18000b390  push    rdi
0x18000b391  push    r12
0x18000b393  push    r13
0x18000b395  push    r14
0x18000b397  push    r15
0x18000b399  sub     rsp, 30h
0x18000b39d  mov     rax, [rsp+68h+arg_28]
0x18000b3a5  xor     r10d, r10d
0x18000b3a8  xor     r11d, r11d
0x18000b3ab  movzx   r12d, dl
0x18000b3af  xor     bl, bl
0x18000b3b1  mov     r14b, r9b
0x18000b3b4  mov     r13, r8
0x18000b3b7  mov     [rax], r10
0x18000b3ba  test    dl, dl
0x18000b3bc  jz      short loc_18000B3FB
0x18000b3be  movzx   eax, bl
0x18000b3c1  add     rax, rax
0x18000b3c4  cmp     bl, 2
0x18000b3c7  mov     ecx, [r8+rax*8+8]
0x18000b3cc  lea     rax, [rcx+r10]
0x18000b3d0  cmovnb  r10, rax
0x18000b3d4  lea     rax, [rcx+r11]
0x18000b3d8  cmovnb  rax, r11
0x18000b3dc  inc     bl
0x18000b3de  mov     r11, rax
0x18000b3e1  cmp     bl, r12b
0x18000b3e4  jb      short loc_18000B3BE
0x18000b3e6  add     rax, r10
0x18000b3e9  cmp     rax, 0FFFFh
0x18000b3ef  jbe     short loc_18000B3FB
0x18000b3f1  mov     eax, 216h
0x18000b3f6  jmp     loc_18000B59C
0x18000b3fb  mov     rdi, r12
0x18000b3fe  mov     esi, 8
0x18000b403  shl     rdi, 4
0x18000b407  lea     rbx, [rdi+2Eh]
0x18000b40b  add     rbx, r10
0x18000b40e  jz      loc_18000B59A
0x18000b414  call    cs:__imp_GetProcessHeap
0x18000b41a  mov     r8, rbx; dwBytes
0x18000b41d  mov     edx, esi; dwFlags
0x18000b41f  mov     rcx, rax; hHeap
0x18000b422  call    cs:__imp_HeapAlloc
0x18000b428  mov     rbp, rax
0x18000b42b  test    rax, rax
0x18000b42e  jz      loc_18000B59A
0x18000b434  test    rdi, rdi
0x18000b437  jz      short loc_18000B447
0x18000b439  cmp     rbx, rdi
0x18000b43c  jb      short loc_18000B447
0x18000b43e  lea     rsi, [rdi+rax]
0x18000b442  sub     rbx, rdi
0x18000b445  jmp     short loc_18000B44C
0x18000b447  mov     rsi, rax
0x18000b44a  xor     ebp, ebp
0x18000b44c  xor     r15b, r15b
0x18000b44f  add     r14b, 2
0x18000b453  mov     dl, r14b
0x18000b456  mov     [rsp+68h+var_48], edx
0x18000b45a  jz      short loc_18000B4D7
0x18000b45c  xor     r12d, r12d
0x18000b45f  mov     rdi, r12
0x18000b462  add     rdi, rdi
0x18000b465  cmp     r15b, 2
0x18000b469  jnb     short loc_18000B479
0x18000b46b  movups  xmm0, xmmword ptr [r13+rdi*8+0]
0x18000b471  movdqu  xmmword ptr [rbp+rdi*8+0], xmm0
0x18000b477  jmp     short loc_18000B4C3
0x18000b479  mov     r8d, [r13+rdi*8+8]; Size
0x18000b47e  test    r8, r8
0x18000b481  jz      short loc_18000B493
0x18000b483  cmp     rbx, r8
0x18000b486  jb      short loc_18000B493
0x18000b488  mov     rax, rsi
0x18000b48b  add     rsi, r8
0x18000b48e  sub     rbx, r8
0x18000b491  jmp     short loc_18000B495
0x18000b493  xor     eax, eax
0x18000b495  mov     rdx, [r13+rdi*8+0]; Src
0x18000b49a  mov     rcx, rax; void *
0x18000b49d  mov     [rsp+68h+var_40], rax
0x18000b4a2  call    memcpy_0
0x18000b4a7  mov     rax, [rsp+68h+var_40]
0x18000b4ac  mov     [rbp+rdi*8+0], rax
0x18000b4b1  mov     eax, [r13+rdi*8+0Ch]
0x18000b4b6  mov     [rbp+rdi*8+0Ch], eax
0x18000b4ba  mov     eax, [r13+rdi*8+8]
0x18000b4bf  mov     [rbp+rdi*8+8], eax
0x18000b4c3  inc     r15b
0x18000b4c6  inc     r12
0x18000b4c9  cmp     r15b, r14b
0x18000b4cc  jb      short loc_18000B45F
0x18000b4ce  mov     r12b, [rsp+68h+arg_8]
0x18000b4d3  mov     edx, [rsp+68h+var_48]
0x18000b4d7  mov     rcx, rbx
0x18000b4da  mov     rdi, rsi
0x18000b4dd  cmp     rbx, 2Eh ; '.'
0x18000b4e1  jb      short loc_18000B4EB
0x18000b4e3  add     rsi, 2Eh ; '.'
0x18000b4e7  sub     rbx, 2Eh ; '.'
0x18000b4eb  xor     eax, eax
0x18000b4ed  cmp     rcx, 2Eh ; '.'
0x18000b4f1  cmovb   rdi, rax
0x18000b4f5  mov     rax, [rsp+68h+arg_0]
0x18000b4fa  mov     [rdi+10h], rbp
0x18000b4fe  movups  xmm0, xmmword ptr [rax]
0x18000b501  mov     al, [rsp+68h+arg_18]
0x18000b508  mov     [rdi+2Dh], al
0x18000b50b  mov     eax, [rsp+68h+arg_20]
0x18000b512  mov     [rdi+28h], eax
0x18000b515  mov     [rdi+2Ch], r12b
0x18000b519  movdqu  xmmword ptr [rdi], xmm0
0x18000b51d  cmp     dl, r12b
0x18000b520  jnb     short loc_18000B58B
0x18000b522  movzx   r15d, r14b
0x18000b526  mov     r14, r15
0x18000b529  add     r14, r14
0x18000b52c  mov     r8d, [r13+r14*8+8]; Size
0x18000b531  test    r8, r8
0x18000b534  jz      short loc_18000B546
0x18000b536  cmp     rbx, r8
0x18000b539  jb      short loc_18000B546
0x18000b53b  mov     rbp, rsi
0x18000b53e  add     rsi, r8
0x18000b541  sub     rbx, r8
0x18000b544  jmp     short loc_18000B548
0x18000b546  xor     ebp, ebp
0x18000b548  mov     rdx, [r13+r14*8+0]; Src
0x18000b54d  mov     rcx, rbp; void *
0x18000b550  call    memcpy_0
0x18000b555  mov     rax, [rdi+10h]
0x18000b559  inc     r15
0x18000b55c  mov     edx, [rsp+68h+var_48]
0x18000b560  inc     dl
0x18000b562  mov     [rsp+68h+var_48], edx
0x18000b566  mov     [rax+r14*8], rbp
0x18000b56a  mov     rcx, [rdi+10h]
0x18000b56e  mov     eax, [r13+r14*8+0Ch]
0x18000b573  mov     [rcx+r14*8+0Ch], eax
0x18000b578  mov     rcx, [rdi+10h]
0x18000b57c  mov     eax, [r13+r14*8+8]
0x18000b581  mov     [rcx+r14*8+8], eax
0x18000b586  cmp     dl, r12b
0x18000b589  jb      short loc_18000B526
0x18000b58b  mov     rax, [rsp+68h+arg_28]
0x18000b593  mov     [rax], rdi
0x18000b596  xor     eax, eax
0x18000b598  jmp     short loc_18000B59C
0x18000b59a  mov     eax, esi
0x18000b59c  mov     rbx, [rsp+68h+arg_10]
0x18000b5a4  add     rsp, 30h
0x18000b5a8  pop     r15
0x18000b5aa  pop     r14
0x18000b5ac  pop     r13
0x18000b5ae  pop     r12
0x18000b5b0  pop     rdi
0x18000b5b1  pop     rsi
0x18000b5b2  pop     rbp
0x18000b5b3  retn
```
