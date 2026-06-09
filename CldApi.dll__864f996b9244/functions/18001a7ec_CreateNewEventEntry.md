# CreateNewEventEntry

- ea: `0x18001a7ec`
- end: `0x18001aa24`
- name: `CreateNewEventEntry`
- size: `568`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x18001ace0`

## callees

- `0x18001a7ec`
- `0x18001be5c`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001a884`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001a884`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18001a892`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18001a892`

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
0x18001a7ec  mov     rax, rsp
0x18001a7ef  mov     [rax+18h], rbx
0x18001a7f3  mov     [rax+20h], r9b
0x18001a7f7  mov     [rax+10h], dl
0x18001a7fa  mov     [rax+8], rcx
0x18001a7fe  push    rbp
0x18001a7ff  push    rsi
0x18001a800  push    rdi
0x18001a801  push    r12
0x18001a803  push    r13
0x18001a805  push    r14
0x18001a807  push    r15
0x18001a809  sub     rsp, 30h
0x18001a80d  mov     rax, [rsp+68h+arg_28]
0x18001a815  xor     r10d, r10d
0x18001a818  xor     r11d, r11d
0x18001a81b  movzx   r12d, dl
0x18001a81f  xor     bl, bl
0x18001a821  mov     r14b, r9b
0x18001a824  mov     r13, r8
0x18001a827  mov     [rax], r10
0x18001a82a  test    dl, dl
0x18001a82c  jz      short loc_18001A86B
0x18001a82e  movzx   eax, bl
0x18001a831  add     rax, rax
0x18001a834  cmp     bl, 2
0x18001a837  mov     ecx, [r8+rax*8+8]
0x18001a83c  lea     rax, [rcx+r10]
0x18001a840  cmovnb  r10, rax
0x18001a844  lea     rax, [rcx+r11]
0x18001a848  cmovnb  rax, r11
0x18001a84c  inc     bl
0x18001a84e  mov     r11, rax
0x18001a851  cmp     bl, r12b
0x18001a854  jb      short loc_18001A82E
0x18001a856  add     rax, r10
0x18001a859  cmp     rax, 0FFFFh
0x18001a85f  jbe     short loc_18001A86B
0x18001a861  mov     eax, 216h
0x18001a866  jmp     loc_18001AA0C
0x18001a86b  mov     rdi, r12
0x18001a86e  mov     esi, 8
0x18001a873  shl     rdi, 4
0x18001a877  lea     rbx, [rdi+2Eh]
0x18001a87b  add     rbx, r10
0x18001a87e  jz      loc_18001AA0A
0x18001a884  call    cs:__imp_GetProcessHeap
0x18001a88a  mov     r8, rbx; dwBytes
0x18001a88d  mov     edx, esi; dwFlags
0x18001a88f  mov     rcx, rax; hHeap
0x18001a892  call    cs:__imp_HeapAlloc
0x18001a898  mov     rbp, rax
0x18001a89b  test    rax, rax
0x18001a89e  jz      loc_18001AA0A
0x18001a8a4  test    rdi, rdi
0x18001a8a7  jz      short loc_18001A8B7
0x18001a8a9  cmp     rbx, rdi
0x18001a8ac  jb      short loc_18001A8B7
0x18001a8ae  lea     rsi, [rdi+rax]
0x18001a8b2  sub     rbx, rdi
0x18001a8b5  jmp     short loc_18001A8BC
0x18001a8b7  mov     rsi, rax
0x18001a8ba  xor     ebp, ebp
0x18001a8bc  xor     r15b, r15b
0x18001a8bf  add     r14b, 2
0x18001a8c3  mov     dl, r14b
0x18001a8c6  mov     [rsp+68h+var_48], edx
0x18001a8ca  jz      short loc_18001A947
0x18001a8cc  xor     r12d, r12d
0x18001a8cf  mov     rdi, r12
0x18001a8d2  add     rdi, rdi
0x18001a8d5  cmp     r15b, 2
0x18001a8d9  jnb     short loc_18001A8E9
0x18001a8db  movups  xmm0, xmmword ptr [r13+rdi*8+0]
0x18001a8e1  movdqu  xmmword ptr [rbp+rdi*8+0], xmm0
0x18001a8e7  jmp     short loc_18001A933
0x18001a8e9  mov     r8d, [r13+rdi*8+8]; Size
0x18001a8ee  test    r8, r8
0x18001a8f1  jz      short loc_18001A903
0x18001a8f3  cmp     rbx, r8
0x18001a8f6  jb      short loc_18001A903
0x18001a8f8  mov     rax, rsi
0x18001a8fb  add     rsi, r8
0x18001a8fe  sub     rbx, r8
0x18001a901  jmp     short loc_18001A905
0x18001a903  xor     eax, eax
0x18001a905  mov     rdx, [r13+rdi*8+0]; Src
0x18001a90a  mov     rcx, rax; void *
0x18001a90d  mov     [rsp+68h+var_40], rax
0x18001a912  call    memcpy_0
0x18001a917  mov     rax, [rsp+68h+var_40]
0x18001a91c  mov     [rbp+rdi*8+0], rax
0x18001a921  mov     eax, [r13+rdi*8+0Ch]
0x18001a926  mov     [rbp+rdi*8+0Ch], eax
0x18001a92a  mov     eax, [r13+rdi*8+8]
0x18001a92f  mov     [rbp+rdi*8+8], eax
0x18001a933  inc     r15b
0x18001a936  inc     r12
0x18001a939  cmp     r15b, r14b
0x18001a93c  jb      short loc_18001A8CF
0x18001a93e  mov     r12b, [rsp+68h+arg_8]
0x18001a943  mov     edx, [rsp+68h+var_48]
0x18001a947  mov     rcx, rbx
0x18001a94a  mov     rdi, rsi
0x18001a94d  cmp     rbx, 2Eh ; '.'
0x18001a951  jb      short loc_18001A95B
0x18001a953  add     rsi, 2Eh ; '.'
0x18001a957  sub     rbx, 2Eh ; '.'
0x18001a95b  xor     eax, eax
0x18001a95d  cmp     rcx, 2Eh ; '.'
0x18001a961  cmovb   rdi, rax
0x18001a965  mov     rax, [rsp+68h+arg_0]
0x18001a96a  mov     [rdi+10h], rbp
0x18001a96e  movups  xmm0, xmmword ptr [rax]
0x18001a971  mov     al, [rsp+68h+arg_18]
0x18001a978  mov     [rdi+2Dh], al
0x18001a97b  mov     eax, [rsp+68h+arg_20]
0x18001a982  mov     [rdi+28h], eax
0x18001a985  mov     [rdi+2Ch], r12b
0x18001a989  movdqu  xmmword ptr [rdi], xmm0
0x18001a98d  cmp     dl, r12b
0x18001a990  jnb     short loc_18001A9FB
0x18001a992  movzx   r15d, r14b
0x18001a996  mov     r14, r15
0x18001a999  add     r14, r14
0x18001a99c  mov     r8d, [r13+r14*8+8]; Size
0x18001a9a1  test    r8, r8
0x18001a9a4  jz      short loc_18001A9B6
0x18001a9a6  cmp     rbx, r8
0x18001a9a9  jb      short loc_18001A9B6
0x18001a9ab  mov     rbp, rsi
0x18001a9ae  add     rsi, r8
0x18001a9b1  sub     rbx, r8
0x18001a9b4  jmp     short loc_18001A9B8
0x18001a9b6  xor     ebp, ebp
0x18001a9b8  mov     rdx, [r13+r14*8+0]; Src
0x18001a9bd  mov     rcx, rbp; void *
0x18001a9c0  call    memcpy_0
0x18001a9c5  mov     rax, [rdi+10h]
0x18001a9c9  inc     r15
0x18001a9cc  mov     edx, [rsp+68h+var_48]
0x18001a9d0  inc     dl
0x18001a9d2  mov     [rsp+68h+var_48], edx
0x18001a9d6  mov     [rax+r14*8], rbp
0x18001a9da  mov     rcx, [rdi+10h]
0x18001a9de  mov     eax, [r13+r14*8+0Ch]
0x18001a9e3  mov     [rcx+r14*8+0Ch], eax
0x18001a9e8  mov     rcx, [rdi+10h]
0x18001a9ec  mov     eax, [r13+r14*8+8]
0x18001a9f1  mov     [rcx+r14*8+8], eax
0x18001a9f6  cmp     dl, r12b
0x18001a9f9  jb      short loc_18001A996
0x18001a9fb  mov     rax, [rsp+68h+arg_28]
0x18001aa03  mov     [rax], rdi
0x18001aa06  xor     eax, eax
0x18001aa08  jmp     short loc_18001AA0C
0x18001aa0a  mov     eax, esi
0x18001aa0c  mov     rbx, [rsp+68h+arg_10]
0x18001aa14  add     rsp, 30h
0x18001aa18  pop     r15
0x18001aa1a  pop     r14
0x18001aa1c  pop     r13
0x18001aa1e  pop     r12
0x18001aa20  pop     rdi
0x18001aa21  pop     rsi
0x18001aa22  pop     rbp
0x18001aa23  retn
```
