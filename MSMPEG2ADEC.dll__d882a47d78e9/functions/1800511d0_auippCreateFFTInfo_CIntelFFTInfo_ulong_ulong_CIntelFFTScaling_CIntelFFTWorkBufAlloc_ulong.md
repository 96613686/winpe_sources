# auippCreateFFTInfo(CIntelFFTInfo * *,ulong,ulong,CIntelFFTScaling,CIntelFFTWorkBufAlloc,ulong *)

- ea: `0x1800511d0`
- end: `0x18005142b`
- name: `?auippCreateFFTInfo@@YAJPEAPEAUCIntelFFTInfo@@KKW4CIntelFFTScaling@@W4CIntelFFTWorkBufAlloc@@PEAK@Z`
- size: `603`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x18004eba0`

## callees

- `0x1800021a8`
- `0x1800511d0`
- `0x180051440`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x180051203`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x18005123b`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x180051203`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x18005123b`
- `mfperfhelper!__imp_ippsFFTGetBufSize_R_32f` at `0x180051307`
- `mfperfhelper!__imp_ippsFFTGetBufSize_R_32f` at `0x180051307`
- `mfperfhelper!__imp_ippsMalloc_8u` at `0x180051372`
- `mfperfhelper!__imp_ippsMalloc_8u` at `0x1800513a5`
- `mfperfhelper!__imp_ippsMalloc_8u` at `0x180051372`
- `mfperfhelper!__imp_ippsMalloc_8u` at `0x1800513a5`
- `mfperfhelper!__imp_ippsFFTInitAlloc_R_32f` at `0x1800512d3`
- `mfperfhelper!__imp_ippsFFTInitAlloc_R_32f` at `0x1800512d3`

## pseudocode

```c
__int64 __fastcall auippCreateFFTInfo(struct CIntelFFTInfo **a1)
{
  struct CIntelFFTInfo *v2; // rax
  struct CIntelFFTInfo *v3; // rdi
  int v4; // ebx
  void *v5; // rax
  unsigned int v6; // eax
  unsigned int v7; // eax
  int v8; // r15d
  unsigned int v9; // ebx
  int v10; // edi
  unsigned int v11; // eax
  __int64 v12; // rdx
  __int64 v13; // r14
  unsigned int v14; // r14d
  unsigned int v15; // r12d
  int v16; // r13d
  __int64 v17; // rbp
  __int64 v18; // rbx
  __int64 v19; // rax
  __int64 v20; // rax
  __int64 v21; // rdx
  __int64 result; // rax
  int v23; // [rsp+68h] [rbp+20h] BYREF

  v23 = 0;
  if ( !a1 || *a1 )
  {
    v4 = -2147024809;
    goto LABEL_32;
  }
  v2 = (struct CIntelFFTInfo *)malloc(0x18u);
  v3 = v2;
  if ( !v2 )
  {
    v4 = -2147024882;
    goto LABEL_32;
  }
  *((_QWORD *)v2 + 2) = 0;
  *(_DWORD *)v2 = 6;
  *((_DWORD *)v2 + 1) = 11;
  v5 = malloc(0xC0u);
  *((_QWORD *)v3 + 1) = v5;
  if ( v5 )
  {
    v4 = 0;
    memset_0(v5, 0, 0xC0u);
  }
  else
  {
    v4 = -2147024882;
  }
  *a1 = v3;
  if ( v4 < 0 )
    goto LABEL_32;
  if ( !*((_QWORD *)v3 + 1)
    || (v6 = *((_DWORD *)v3 + 1), v6 < *(_DWORD *)v3)
    || (v7 = v6 - *(_DWORD *)v3, v8 = v7 + 1, v7 + 1 < v7) )
  {
LABEL_10:
    v4 = -2147467259;
    goto LABEL_32;
  }
  v9 = 0;
  v10 = 1;
  if ( v7 != -1 )
  {
    do
    {
      v11 = *(_DWORD *)*a1;
      v12 = v11 + v9;
      if ( (unsigned int)v12 < v11 )
        goto LABEL_10;
      v13 = 32LL * v9;
      if ( (int)ippsFFTInitAlloc_R_32f(v13 + *((_QWORD *)*a1 + 1), v12, 2, 0) < 0 )
        goto LABEL_10;
      *(_DWORD *)(*((_QWORD *)*a1 + 1) + v13 + 8) = 1 << (v9 + *(_DWORD *)*a1);
      if ( (int)ippsFFTGetBufSize_R_32f(*(_QWORD *)(*((_QWORD *)*a1 + 1) + 32LL * v9), &v23) < 0 )
        goto LABEL_10;
      ++v9;
      *(_DWORD *)(*((_QWORD *)*a1 + 1) + v13 + 24) = v23;
    }
    while ( v9 < v8 );
  }
  v14 = 0;
  v15 = 0;
  *((_DWORD *)*a1 + 4) = 1;
  v16 = *((_DWORD *)*a1 + 4);
  v17 = *((_QWORD *)*a1 + 1);
  if ( v8 > 0 )
  {
    while ( 1 )
    {
      v18 = 32LL * v15;
      if ( v16 == 2 )
      {
        v19 = ippsMalloc_8u(*(unsigned int *)(v18 + v17 + 24));
        *(_QWORD *)(v18 + v17 + 16) = v19;
        if ( !v19 )
          break;
      }
      if ( v14 < *(_DWORD *)(v18 + v17 + 24) )
        v14 = *(_DWORD *)(v18 + v17 + 24);
      if ( (int)++v15 >= v8 )
        goto LABEL_24;
    }
LABEL_26:
    v4 = -2147024882;
    goto LABEL_29;
  }
LABEL_24:
  v4 = 0;
  if ( v16 != 1 )
    goto LABEL_29;
  v20 = ippsMalloc_8u(v14);
  *(_QWORD *)(v17 + 16) = v20;
  if ( !v20 )
    goto LABEL_26;
  if ( v8 > 1 )
  {
    do
    {
      v21 = (unsigned int)v10++;
      *(_QWORD *)(32 * v21 + v17 + 16) = *(_QWORD *)(v17 + 16);
    }
    while ( v10 < v8 );
  }
LABEL_29:
  if ( v4 >= 0 )
    return (unsigned int)v4;
LABEL_32:
  auippDeleteFFTInfo(*a1);
  result = (unsigned int)v4;
  *a1 = 0;
  return result;
}

```

## disassembly

```asm
0x1800511d0  mov     [rsp+arg_18], r9d
0x1800511d5  push    rbx
0x1800511d6  push    rsi
0x1800511d7  push    rdi
0x1800511d8  push    r14
0x1800511da  push    r15
0x1800511dc  sub     rsp, 20h
0x1800511e0  mov     [rsp+48h+arg_18], 0
0x1800511e8  mov     rsi, rcx
0x1800511eb  test    rcx, rcx
0x1800511ee  jz      loc_180051408
0x1800511f4  cmp     qword ptr [rcx], 0
0x1800511f8  jnz     loc_180051408
0x1800511fe  mov     ecx, 18h; Size
0x180051203  call    cs:__imp_malloc
0x18005120a  nop     dword ptr [rax+rax+00h]
0x18005120f  mov     rdi, rax
0x180051212  test    rax, rax
0x180051215  jnz     short loc_180051221
0x180051217  mov     ebx, 8007000Eh
0x18005121c  jmp     loc_18005140D
0x180051221  mov     qword ptr [rax+10h], 0
0x180051229  mov     ecx, 0C0h; Size
0x18005122e  mov     dword ptr [rax], 6
0x180051234  mov     dword ptr [rax+4], 0Bh
0x18005123b  call    cs:__imp_malloc
0x180051242  nop     dword ptr [rax+rax+00h]
0x180051247  mov     [rdi+8], rax
0x18005124b  test    rax, rax
0x18005124e  jnz     short loc_180051257
0x180051250  mov     ebx, 8007000Eh
0x180051255  jmp     short loc_180051269
0x180051257  xor     ebx, ebx
0x180051259  xor     edx, edx; Val
0x18005125b  mov     r8d, 0C0h; Size
0x180051261  mov     rcx, rax; void *
0x180051264  call    memset_0
0x180051269  mov     [rsi], rdi
0x18005126c  test    ebx, ebx
0x18005126e  js      loc_18005140D
0x180051274  cmp     qword ptr [rdi+8], 0
0x180051279  jnz     short loc_180051285
0x18005127b  mov     ebx, 80004005h
0x180051280  jmp     loc_18005140D
0x180051285  mov     ecx, [rdi]
0x180051287  mov     eax, [rdi+4]
0x18005128a  cmp     eax, ecx
0x18005128c  jb      short loc_18005127B
0x18005128e  sub     eax, ecx
0x180051290  lea     r15d, [rax+1]
0x180051294  cmp     r15d, eax
0x180051297  jb      short loc_18005127B
0x180051299  xor     ebx, ebx
0x18005129b  mov     edi, 1
0x1800512a0  test    r15d, r15d
0x1800512a3  jz      loc_180051336
0x1800512a9  nop     dword ptr [rax+00000000h]
0x1800512b0  mov     rcx, [rsi]
0x1800512b3  mov     eax, [rcx]
0x1800512b5  lea     edx, [rax+rbx]
0x1800512b8  cmp     edx, eax
0x1800512ba  jb      short loc_18005127B
0x1800512bc  mov     rcx, [rcx+8]
0x1800512c0  xor     r9d, r9d
0x1800512c3  mov     r14d, ebx
0x1800512c6  mov     r8d, 2
0x1800512cc  shl     r14, 5
0x1800512d0  add     rcx, r14
0x1800512d3  call    cs:__imp_ippsFFTInitAlloc_R_32f
0x1800512da  nop     dword ptr [rax+rax+00h]
0x1800512df  test    eax, eax
0x1800512e1  js      short loc_18005127B
0x1800512e3  mov     rax, [rsi]
0x1800512e6  mov     edx, edi
0x1800512e8  mov     ecx, [rax]
0x1800512ea  mov     rax, [rax+8]
0x1800512ee  add     ecx, ebx
0x1800512f0  shl     edx, cl
0x1800512f2  mov     [rax+r14+8], edx
0x1800512f7  lea     rdx, [rsp+48h+arg_18]
0x1800512fc  mov     rax, [rsi]
0x1800512ff  mov     rcx, [rax+8]
0x180051303  mov     rcx, [rcx+r14]
0x180051307  call    cs:__imp_ippsFFTGetBufSize_R_32f
0x18005130e  nop     dword ptr [rax+rax+00h]
0x180051313  test    eax, eax
0x180051315  js      loc_18005127B
0x18005131b  mov     rax, [rsi]
0x18005131e  inc     ebx
0x180051320  mov     rcx, [rax+8]
0x180051324  mov     eax, [rsp+48h+arg_18]
0x180051328  mov     [rcx+r14+18h], eax
0x18005132d  cmp     ebx, r15d
0x180051330  jb      loc_1800512B0
0x180051336  mov     rax, [rsi]
0x180051339  xor     r14d, r14d
0x18005133c  mov     [rsp+48h+arg_0], rbp
0x180051341  mov     [rsp+48h+arg_8], r12
0x180051346  xor     r12d, r12d
0x180051349  mov     [rsp+48h+arg_10], r13
0x18005134e  mov     [rax+10h], edi
0x180051351  mov     rax, [rsi]
0x180051354  mov     r13d, [rax+10h]
0x180051358  mov     rbp, [rax+8]
0x18005135c  test    r15d, r15d
0x18005135f  jle     short loc_18005139B
0x180051361  mov     ebx, r12d
0x180051364  shl     rbx, 5
0x180051368  cmp     r13d, 2
0x18005136c  jnz     short loc_180051388
0x18005136e  mov     ecx, [rbx+rbp+18h]
0x180051372  call    cs:__imp_ippsMalloc_8u
0x180051379  nop     dword ptr [rax+rax+00h]
0x18005137e  mov     [rbx+rbp+10h], rax
0x180051383  test    rax, rax
0x180051386  jz      short loc_1800513BA
0x180051388  cmp     r14d, [rbx+rbp+18h]
0x18005138d  cmovb   r14d, [rbx+rbp+18h]
0x180051393  inc     r12d
0x180051396  cmp     r12d, r15d
0x180051399  jl      short loc_180051361
0x18005139b  xor     ebx, ebx
0x18005139d  cmp     r13d, edi
0x1800513a0  jnz     short loc_1800513E6
0x1800513a2  mov     ecx, r14d
0x1800513a5  call    cs:__imp_ippsMalloc_8u
0x1800513ac  nop     dword ptr [rax+rax+00h]
0x1800513b1  mov     [rbp+10h], rax
0x1800513b5  test    rax, rax
0x1800513b8  jnz     short loc_1800513C1
0x1800513ba  mov     ebx, 8007000Eh
0x1800513bf  jmp     short loc_1800513E6
0x1800513c1  cmp     r15d, edi
0x1800513c4  jle     short loc_1800513E6
0x1800513c6  nop     word ptr [rax+rax+00000000h]
0x1800513d0  mov     rcx, [rbp+10h]
0x1800513d4  mov     edx, edi
0x1800513d6  inc     edi
0x1800513d8  shl     rdx, 5
0x1800513dc  mov     [rdx+rbp+10h], rcx
0x1800513e1  cmp     edi, r15d
0x1800513e4  jl      short loc_1800513D0
0x1800513e6  mov     r13, [rsp+48h+arg_10]
0x1800513eb  mov     r12, [rsp+48h+arg_8]
0x1800513f0  mov     rbp, [rsp+48h+arg_0]
0x1800513f5  test    ebx, ebx
0x1800513f7  js      short loc_18005140D
0x1800513f9  mov     eax, ebx
0x1800513fb  add     rsp, 20h
0x1800513ff  pop     r15
0x180051401  pop     r14
0x180051403  pop     rdi
0x180051404  pop     rsi
0x180051405  pop     rbx
0x180051406  retn
0x180051408  mov     ebx, 80070057h
0x18005140d  mov     rcx, [rsi]; Block
0x180051410  call    ?auippDeleteFFTInfo@@YAXPEAUCIntelFFTInfo@@@Z; auippDeleteFFTInfo(CIntelFFTInfo *)
0x180051415  mov     eax, ebx
0x180051417  mov     qword ptr [rsi], 0
0x18005141e  add     rsp, 20h
0x180051422  pop     r15
0x180051424  pop     r14
0x180051426  pop     rdi
0x180051427  pop     rsi
0x180051428  pop     rbx
0x180051429  retn
```
