# copy_and_add_argument_to_buffer_char_

- ea: `0x180008a7c`
- end: `0x180008c00`
- name: `copy_and_add_argument_to_buffer_char_`
- size: `388`
- prototype: `__int64 __fastcall(char *Source, char *, rsize_t MaxCount)`
- caller_count: `2`
- callee_count: `6`
- tags: ``

## callers

- `0x180008440`
- `0x180008d88`

## callees

- `0x180007c50`
- `0x180007fc0`
- `0x180008040`
- `0x180008a7c`
- `0x18000c5e0`
- `0x180012fd0`

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
0x180008a7c  mov     [rsp+arg_0], rbx
0x180008a81  mov     [rsp+arg_8], rbp
0x180008a86  mov     [rsp+arg_10], rsi
0x180008a8b  push    rdi
0x180008a8c  push    r12
0x180008a8e  push    r13
0x180008a90  push    r14
0x180008a92  push    r15
0x180008a94  sub     rsp, 30h
0x180008a98  or      rbp, 0FFFFFFFFFFFFFFFFh
0x180008a9c  mov     rsi, r9
0x180008a9f  xor     edi, edi
0x180008aa1  mov     r14, r8
0x180008aa4  mov     r13, rdx
0x180008aa7  mov     r12, rcx
0x180008aaa  inc     rbp
0x180008aad  cmp     [rcx+rbp], dil
0x180008ab1  jnz     short loc_180008AAA
0x180008ab3  mov     edx, 1; Size
0x180008ab8  mov     rax, r14
0x180008abb  add     rbp, rdx
0x180008abe  not     rax
0x180008ac1  cmp     rbp, rax
0x180008ac4  jbe     short loc_180008AE6
0x180008ac6  lea     eax, [rdx+0Bh]
0x180008ac9  mov     rbx, [rsp+58h+arg_0]
0x180008ace  mov     rbp, [rsp+58h+arg_8]
0x180008ad3  mov     rsi, [rsp+58h+arg_10]
0x180008ad8  add     rsp, 30h
0x180008adc  pop     r15
0x180008ade  pop     r14
0x180008ae0  pop     r13
0x180008ae2  pop     r12
0x180008ae4  pop     rdi
0x180008ae5  retn
0x180008ae6  lea     r15, [r8+1]
0x180008aea  add     r15, rbp
0x180008aed  mov     rcx, r15; Count
0x180008af0  call    _calloc_base
0x180008af5  mov     rbx, rax
0x180008af8  test    r14, r14
0x180008afb  jz      short loc_180008B16
0x180008afd  mov     r9, r14; MaxCount
0x180008b00  mov     r8, r13; Source
0x180008b03  mov     rdx, r15; SizeInBytes
0x180008b06  mov     rcx, rax; Destination
0x180008b09  call    strncpy_s
0x180008b0e  test    eax, eax
0x180008b10  jnz     loc_180008BEB
0x180008b16  sub     r15, r14
0x180008b19  lea     rcx, [rbx+r14]; Destination
0x180008b1d  mov     rdx, r15; SizeInBytes
0x180008b20  mov     r9, rbp; MaxCount
0x180008b23  mov     r8, r12; Source
0x180008b26  call    strncpy_s
0x180008b2b  test    eax, eax
0x180008b2d  jnz     loc_180008BEB
0x180008b33  mov     r14, [rsi+10h]
0x180008b37  lea     r15d, [rax+8]
0x180008b3b  cmp     [rsi+8], r14
0x180008b3f  jnz     loc_180008BD2
0x180008b45  cmp     [rsi], rdi
0x180008b48  jnz     short loc_180008B75
0x180008b4a  mov     edx, r15d; Size
0x180008b4d  lea     ecx, [rax+4]; Count
0x180008b50  call    _calloc_base
0x180008b55  xor     ecx, ecx; Block
0x180008b57  mov     [rsi], rax
0x180008b5a  call    _free_base
0x180008b5f  mov     rax, [rsi]
0x180008b62  test    rax, rax
0x180008b65  jz      short loc_180008BA9
0x180008b67  mov     [rsi+8], rax
0x180008b6b  add     rax, 20h ; ' '
0x180008b6f  mov     [rsi+10h], rax
0x180008b73  jmp     short loc_180008BD2
0x180008b75  sub     r14, [rsi]
0x180008b78  mov     rax, 7FFFFFFFFFFFFFFFh
0x180008b82  sar     r14, 3
0x180008b86  cmp     r14, rax
0x180008b89  ja      short loc_180008BA9
0x180008b8b  mov     rcx, [rsi]; Block
0x180008b8e  lea     rbp, [r14+r14]
0x180008b92  mov     rdx, rbp; Count
0x180008b95  mov     r8, r15; Size
0x180008b98  call    _recalloc_base
0x180008b9d  test    rax, rax
0x180008ba0  jnz     short loc_180008BB8
0x180008ba2  xor     ecx, ecx; Block
0x180008ba4  call    _free_base
0x180008ba9  mov     rcx, rbx; Block
0x180008bac  mov     edi, 0Ch
0x180008bb1  call    _free_base
0x180008bb6  jmp     short loc_180008BDD
0x180008bb8  lea     rcx, [rax+r14*8]
0x180008bbc  mov     [rsi], rax
0x180008bbf  mov     [rsi+8], rcx
0x180008bc3  lea     rcx, [rax+rbp*8]
0x180008bc7  mov     [rsi+10h], rcx
0x180008bcb  xor     ecx, ecx; Block
0x180008bcd  call    _free_base
0x180008bd2  mov     rcx, [rsi+8]
0x180008bd6  mov     [rcx], rbx
0x180008bd9  add     [rsi+8], r15
0x180008bdd  xor     ecx, ecx; Block
0x180008bdf  call    _free_base
0x180008be4  mov     eax, edi
0x180008be6  jmp     loc_180008AC9
0x180008beb  xor     r9d, r9d; LineNo
0x180008bee  mov     [rsp+58h+Reserved], rdi; Reserved
0x180008bf3  xor     r8d, r8d; FileName
0x180008bf6  xor     edx, edx; FunctionName
0x180008bf8  xor     ecx, ecx; Expression
0x180008bfa  call    _invoke_watson
```
