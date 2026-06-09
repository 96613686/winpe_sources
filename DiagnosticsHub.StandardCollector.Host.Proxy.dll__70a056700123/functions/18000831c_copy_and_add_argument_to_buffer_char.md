# copy_and_add_argument_to_buffer_char_

- ea: `0x18000831c`
- end: `0x1800084a0`
- name: `copy_and_add_argument_to_buffer_char_`
- size: `388`
- prototype: `__int64 __fastcall(char *Source, char *, rsize_t MaxCount)`
- caller_count: `2`
- callee_count: `6`
- tags: ``

## callers

- `0x180007ce0`
- `0x180008628`

## callees

- `0x1800074f0`
- `0x180007860`
- `0x1800078e0`
- `0x18000831c`
- `0x18000be80`
- `0x180012870`

## pseudocode

```c
__int64 __fastcall copy_and_add_argument_to_buffer_char_(char *Source, char *a2, rsize_t MaxCount, void **a4)
{
  __int64 v4; // rbp
  unsigned int v6; // edi
  rsize_t v10; // rbp
  size_t v12; // r15
  char *v13; // rax
  char *v14; // rbx
  char *v15; // r14
  char *v16; // rax
  unsigned __int64 v17; // r14
  char *v18; // rax

  v4 = -1;
  v6 = 0;
  do
    ++v4;
  while ( Source[v4] );
  v10 = v4 + 1;
  if ( v10 > ~MaxCount )
    return 12;
  v12 = v10 + MaxCount + 1;
  v13 = (char *)calloc_base(v12, 1u);
  v14 = v13;
  if ( MaxCount && strncpy_s(v13, v12, a2, MaxCount) || strncpy_s(&v14[MaxCount], v12 - MaxCount, Source, v10) )
    invoke_watson(0, 0, 0, 0, 0);
  v15 = (char *)a4[2];
  if ( a4[1] != v15 )
    goto LABEL_17;
  if ( *a4 )
  {
    v17 = (v15 - (_BYTE *)*a4) >> 3;
    if ( v17 <= 0x7FFFFFFFFFFFFFFFLL )
    {
      v18 = (char *)recalloc_base(*a4, 2 * v17, 8u);
      if ( v18 )
      {
        *a4 = v18;
        a4[1] = &v18[8 * v17];
        a4[2] = &v18[16 * v17];
        free_base(0);
        goto LABEL_17;
      }
      free_base(0);
    }
  }
  else
  {
    *a4 = calloc_base(4u, 8u);
    free_base(0);
    v16 = (char *)*a4;
    if ( *a4 )
    {
      a4[1] = v16;
      a4[2] = v16 + 32;
LABEL_17:
      *(_QWORD *)a4[1] = v14;
      a4[1] = (char *)a4[1] + 8;
      goto LABEL_18;
    }
  }
  v6 = 12;
  free_base(v14);
LABEL_18:
  free_base(0);
  return v6;
}

```

## disassembly

```asm
0x18000831c  mov     [rsp+arg_0], rbx
0x180008321  mov     [rsp+arg_8], rbp
0x180008326  mov     [rsp+arg_10], rsi
0x18000832b  push    rdi
0x18000832c  push    r12
0x18000832e  push    r13
0x180008330  push    r14
0x180008332  push    r15
0x180008334  sub     rsp, 30h
0x180008338  or      rbp, 0FFFFFFFFFFFFFFFFh
0x18000833c  mov     rsi, r9
0x18000833f  xor     edi, edi
0x180008341  mov     r14, r8
0x180008344  mov     r13, rdx
0x180008347  mov     r12, rcx
0x18000834a  inc     rbp
0x18000834d  cmp     [rcx+rbp], dil
0x180008351  jnz     short loc_18000834A
0x180008353  mov     edx, 1; Size
0x180008358  mov     rax, r14
0x18000835b  add     rbp, rdx
0x18000835e  not     rax
0x180008361  cmp     rbp, rax
0x180008364  jbe     short loc_180008386
0x180008366  lea     eax, [rdx+0Bh]
0x180008369  mov     rbx, [rsp+58h+arg_0]
0x18000836e  mov     rbp, [rsp+58h+arg_8]
0x180008373  mov     rsi, [rsp+58h+arg_10]
0x180008378  add     rsp, 30h
0x18000837c  pop     r15
0x18000837e  pop     r14
0x180008380  pop     r13
0x180008382  pop     r12
0x180008384  pop     rdi
0x180008385  retn
0x180008386  lea     r15, [r8+1]
0x18000838a  add     r15, rbp
0x18000838d  mov     rcx, r15; Count
0x180008390  call    _calloc_base
0x180008395  mov     rbx, rax
0x180008398  test    r14, r14
0x18000839b  jz      short loc_1800083B6
0x18000839d  mov     r9, r14; MaxCount
0x1800083a0  mov     r8, r13; Source
0x1800083a3  mov     rdx, r15; SizeInBytes
0x1800083a6  mov     rcx, rax; Destination
0x1800083a9  call    strncpy_s
0x1800083ae  test    eax, eax
0x1800083b0  jnz     loc_18000848B
0x1800083b6  sub     r15, r14
0x1800083b9  lea     rcx, [rbx+r14]; Destination
0x1800083bd  mov     rdx, r15; SizeInBytes
0x1800083c0  mov     r9, rbp; MaxCount
0x1800083c3  mov     r8, r12; Source
0x1800083c6  call    strncpy_s
0x1800083cb  test    eax, eax
0x1800083cd  jnz     loc_18000848B
0x1800083d3  mov     r14, [rsi+10h]
0x1800083d7  lea     r15d, [rax+8]
0x1800083db  cmp     [rsi+8], r14
0x1800083df  jnz     loc_180008472
0x1800083e5  cmp     [rsi], rdi
0x1800083e8  jnz     short loc_180008415
0x1800083ea  mov     edx, r15d; Size
0x1800083ed  lea     ecx, [rax+4]; Count
0x1800083f0  call    _calloc_base
0x1800083f5  xor     ecx, ecx; Block
0x1800083f7  mov     [rsi], rax
0x1800083fa  call    _free_base
0x1800083ff  mov     rax, [rsi]
0x180008402  test    rax, rax
0x180008405  jz      short loc_180008449
0x180008407  mov     [rsi+8], rax
0x18000840b  add     rax, 20h ; ' '
0x18000840f  mov     [rsi+10h], rax
0x180008413  jmp     short loc_180008472
0x180008415  sub     r14, [rsi]
0x180008418  mov     rax, 7FFFFFFFFFFFFFFFh
0x180008422  sar     r14, 3
0x180008426  cmp     r14, rax
0x180008429  ja      short loc_180008449
0x18000842b  mov     rcx, [rsi]; Block
0x18000842e  lea     rbp, [r14+r14]
0x180008432  mov     rdx, rbp; Count
0x180008435  mov     r8, r15; Size
0x180008438  call    _recalloc_base
0x18000843d  test    rax, rax
0x180008440  jnz     short loc_180008458
0x180008442  xor     ecx, ecx; Block
0x180008444  call    _free_base
0x180008449  mov     rcx, rbx; Block
0x18000844c  mov     edi, 0Ch
0x180008451  call    _free_base
0x180008456  jmp     short loc_18000847D
0x180008458  lea     rcx, [rax+r14*8]
0x18000845c  mov     [rsi], rax
0x18000845f  mov     [rsi+8], rcx
0x180008463  lea     rcx, [rax+rbp*8]
0x180008467  mov     [rsi+10h], rcx
0x18000846b  xor     ecx, ecx; Block
0x18000846d  call    _free_base
0x180008472  mov     rcx, [rsi+8]
0x180008476  mov     [rcx], rbx
0x180008479  add     [rsi+8], r15
0x18000847d  xor     ecx, ecx; Block
0x18000847f  call    _free_base
0x180008484  mov     eax, edi
0x180008486  jmp     loc_180008369
0x18000848b  xor     r9d, r9d; LineNo
0x18000848e  mov     [rsp+58h+Reserved], rdi; Reserved
0x180008493  xor     r8d, r8d; FileName
0x180008496  xor     edx, edx; FunctionName
0x180008498  xor     ecx, ecx; Expression
0x18000849a  call    _invoke_watson
```
