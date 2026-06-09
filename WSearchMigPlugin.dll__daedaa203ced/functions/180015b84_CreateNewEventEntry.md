# CreateNewEventEntry

- ea: `0x180015b84`
- end: `0x180015dbc`
- name: `CreateNewEventEntry`
- size: `568`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180016070`

## callees

- `0x180015b84`
- `0x180016ddc`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180015c1c`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180015c1c`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180015c2a`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180015c2a`

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
0x180015b84  mov     rax, rsp
0x180015b87  mov     [rax+18h], rbx
0x180015b8b  mov     [rax+20h], r9b
0x180015b8f  mov     [rax+10h], dl
0x180015b92  mov     [rax+8], rcx
0x180015b96  push    rbp
0x180015b97  push    rsi
0x180015b98  push    rdi
0x180015b99  push    r12
0x180015b9b  push    r13
0x180015b9d  push    r14
0x180015b9f  push    r15
0x180015ba1  sub     rsp, 30h
0x180015ba5  mov     rax, [rsp+68h+arg_28]
0x180015bad  xor     r10d, r10d
0x180015bb0  xor     r11d, r11d
0x180015bb3  movzx   r12d, dl
0x180015bb7  xor     bl, bl
0x180015bb9  mov     r14b, r9b
0x180015bbc  mov     r13, r8
0x180015bbf  mov     [rax], r10
0x180015bc2  test    dl, dl
0x180015bc4  jz      short loc_180015C03
0x180015bc6  movzx   eax, bl
0x180015bc9  add     rax, rax
0x180015bcc  cmp     bl, 2
0x180015bcf  mov     ecx, [r8+rax*8+8]
0x180015bd4  lea     rax, [rcx+r10]
0x180015bd8  cmovnb  r10, rax
0x180015bdc  lea     rax, [rcx+r11]
0x180015be0  cmovnb  rax, r11
0x180015be4  inc     bl
0x180015be6  mov     r11, rax
0x180015be9  cmp     bl, r12b
0x180015bec  jb      short loc_180015BC6
0x180015bee  add     rax, r10
0x180015bf1  cmp     rax, 0FFFFh
0x180015bf7  jbe     short loc_180015C03
0x180015bf9  mov     eax, 216h
0x180015bfe  jmp     loc_180015DA4
0x180015c03  mov     rdi, r12
0x180015c06  mov     esi, 8
0x180015c0b  shl     rdi, 4
0x180015c0f  lea     rbx, [rdi+2Eh]
0x180015c13  add     rbx, r10
0x180015c16  jz      loc_180015DA2
0x180015c1c  call    cs:__imp_GetProcessHeap
0x180015c22  mov     r8, rbx; dwBytes
0x180015c25  mov     edx, esi; dwFlags
0x180015c27  mov     rcx, rax; hHeap
0x180015c2a  call    cs:__imp_HeapAlloc
0x180015c30  mov     rbp, rax
0x180015c33  test    rax, rax
0x180015c36  jz      loc_180015DA2
0x180015c3c  test    rdi, rdi
0x180015c3f  jz      short loc_180015C4F
0x180015c41  cmp     rbx, rdi
0x180015c44  jb      short loc_180015C4F
0x180015c46  lea     rsi, [rdi+rax]
0x180015c4a  sub     rbx, rdi
0x180015c4d  jmp     short loc_180015C54
0x180015c4f  mov     rsi, rax
0x180015c52  xor     ebp, ebp
0x180015c54  xor     r15b, r15b
0x180015c57  add     r14b, 2
0x180015c5b  mov     dl, r14b
0x180015c5e  mov     [rsp+68h+var_48], edx
0x180015c62  jz      short loc_180015CDF
0x180015c64  xor     r12d, r12d
0x180015c67  mov     rdi, r12
0x180015c6a  add     rdi, rdi
0x180015c6d  cmp     r15b, 2
0x180015c71  jnb     short loc_180015C81
0x180015c73  movups  xmm0, xmmword ptr [r13+rdi*8+0]
0x180015c79  movdqu  xmmword ptr [rbp+rdi*8+0], xmm0
0x180015c7f  jmp     short loc_180015CCB
0x180015c81  mov     r8d, [r13+rdi*8+8]; Size
0x180015c86  test    r8, r8
0x180015c89  jz      short loc_180015C9B
0x180015c8b  cmp     rbx, r8
0x180015c8e  jb      short loc_180015C9B
0x180015c90  mov     rax, rsi
0x180015c93  add     rsi, r8
0x180015c96  sub     rbx, r8
0x180015c99  jmp     short loc_180015C9D
0x180015c9b  xor     eax, eax
0x180015c9d  mov     rdx, [r13+rdi*8+0]; Src
0x180015ca2  mov     rcx, rax; void *
0x180015ca5  mov     [rsp+68h+var_40], rax
0x180015caa  call    memcpy_0
0x180015caf  mov     rax, [rsp+68h+var_40]
0x180015cb4  mov     [rbp+rdi*8+0], rax
0x180015cb9  mov     eax, [r13+rdi*8+0Ch]
0x180015cbe  mov     [rbp+rdi*8+0Ch], eax
0x180015cc2  mov     eax, [r13+rdi*8+8]
0x180015cc7  mov     [rbp+rdi*8+8], eax
0x180015ccb  inc     r15b
0x180015cce  inc     r12
0x180015cd1  cmp     r15b, r14b
0x180015cd4  jb      short loc_180015C67
0x180015cd6  mov     r12b, [rsp+68h+arg_8]
0x180015cdb  mov     edx, [rsp+68h+var_48]
0x180015cdf  mov     rcx, rbx
0x180015ce2  mov     rdi, rsi
0x180015ce5  cmp     rbx, 2Eh ; '.'
0x180015ce9  jb      short loc_180015CF3
0x180015ceb  add     rsi, 2Eh ; '.'
0x180015cef  sub     rbx, 2Eh ; '.'
0x180015cf3  xor     eax, eax
0x180015cf5  cmp     rcx, 2Eh ; '.'
0x180015cf9  cmovb   rdi, rax
0x180015cfd  mov     rax, [rsp+68h+arg_0]
0x180015d02  mov     [rdi+10h], rbp
0x180015d06  movups  xmm0, xmmword ptr [rax]
0x180015d09  mov     al, [rsp+68h+arg_18]
0x180015d10  mov     [rdi+2Dh], al
0x180015d13  mov     eax, [rsp+68h+arg_20]
0x180015d1a  mov     [rdi+28h], eax
0x180015d1d  mov     [rdi+2Ch], r12b
0x180015d21  movdqu  xmmword ptr [rdi], xmm0
0x180015d25  cmp     dl, r12b
0x180015d28  jnb     short loc_180015D93
0x180015d2a  movzx   r15d, r14b
0x180015d2e  mov     r14, r15
0x180015d31  add     r14, r14
0x180015d34  mov     r8d, [r13+r14*8+8]; Size
0x180015d39  test    r8, r8
0x180015d3c  jz      short loc_180015D4E
0x180015d3e  cmp     rbx, r8
0x180015d41  jb      short loc_180015D4E
0x180015d43  mov     rbp, rsi
0x180015d46  add     rsi, r8
0x180015d49  sub     rbx, r8
0x180015d4c  jmp     short loc_180015D50
0x180015d4e  xor     ebp, ebp
0x180015d50  mov     rdx, [r13+r14*8+0]; Src
0x180015d55  mov     rcx, rbp; void *
0x180015d58  call    memcpy_0
0x180015d5d  mov     rax, [rdi+10h]
0x180015d61  inc     r15
0x180015d64  mov     edx, [rsp+68h+var_48]
0x180015d68  inc     dl
0x180015d6a  mov     [rsp+68h+var_48], edx
0x180015d6e  mov     [rax+r14*8], rbp
0x180015d72  mov     rcx, [rdi+10h]
0x180015d76  mov     eax, [r13+r14*8+0Ch]
0x180015d7b  mov     [rcx+r14*8+0Ch], eax
0x180015d80  mov     rcx, [rdi+10h]
0x180015d84  mov     eax, [r13+r14*8+8]
0x180015d89  mov     [rcx+r14*8+8], eax
0x180015d8e  cmp     dl, r12b
0x180015d91  jb      short loc_180015D2E
0x180015d93  mov     rax, [rsp+68h+arg_28]
0x180015d9b  mov     [rax], rdi
0x180015d9e  xor     eax, eax
0x180015da0  jmp     short loc_180015DA4
0x180015da2  mov     eax, esi
0x180015da4  mov     rbx, [rsp+68h+arg_10]
0x180015dac  add     rsp, 30h
0x180015db0  pop     r15
0x180015db2  pop     r14
0x180015db4  pop     r13
0x180015db6  pop     r12
0x180015db8  pop     rdi
0x180015db9  pop     rsi
0x180015dba  pop     rbp
0x180015dbb  retn
```
