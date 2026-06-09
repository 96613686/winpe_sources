# copy_and_add_argument_to_buffer_wchar_t_

- ea: `0x180008c00`
- end: `0x180008d86`
- name: `copy_and_add_argument_to_buffer_wchar_t_`
- size: `390`
- prototype: `__int64 __fastcall(wchar_t *Source, wchar_t *, rsize_t MaxCount)`
- caller_count: `2`
- callee_count: `6`
- tags: ``

## callers

- `0x18000867c`
- `0x1800090e8`

## callees

- `0x180007c50`
- `0x180007fc0`
- `0x180008040`
- `0x180008c00`
- `0x18000c5e0`
- `0x180012d00`

## pseudocode

```c
__int64 __fastcall copy_and_add_argument_to_buffer_wchar_t_(wchar_t *Source, wchar_t *a2, rsize_t MaxCount, void **a4)
{
  __int64 v4; // rbp
  unsigned int v6; // edi
  rsize_t v10; // rbp
  size_t v12; // r15
  wchar_t *v13; // rax
  wchar_t *v14; // rbx
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
  v13 = (wchar_t *)calloc_base(v12, 2u);
  v14 = v13;
  if ( MaxCount && wcsncpy_s(v13, v12, a2, MaxCount) || wcsncpy_s(&v14[MaxCount], v12 - MaxCount, Source, v10) )
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
0x180008c00  mov     [rsp+arg_0], rbx
0x180008c05  mov     [rsp+arg_8], rbp
0x180008c0a  mov     [rsp+arg_10], rsi
0x180008c0f  push    rdi
0x180008c10  push    r12
0x180008c12  push    r13
0x180008c14  push    r14
0x180008c16  push    r15
0x180008c18  sub     rsp, 30h
0x180008c1c  or      rbp, 0FFFFFFFFFFFFFFFFh
0x180008c20  mov     rsi, r9
0x180008c23  xor     edi, edi
0x180008c25  mov     r14, r8
0x180008c28  mov     r13, rdx
0x180008c2b  mov     r12, rcx
0x180008c2e  inc     rbp
0x180008c31  cmp     [rcx+rbp*2], di
0x180008c35  jnz     short loc_180008C2E
0x180008c37  mov     rax, r14
0x180008c3a  inc     rbp
0x180008c3d  not     rax
0x180008c40  cmp     rbp, rax
0x180008c43  jbe     short loc_180008C67
0x180008c45  mov     eax, 0Ch
0x180008c4a  mov     rbx, [rsp+58h+arg_0]
0x180008c4f  mov     rbp, [rsp+58h+arg_8]
0x180008c54  mov     rsi, [rsp+58h+arg_10]
0x180008c59  add     rsp, 30h
0x180008c5d  pop     r15
0x180008c5f  pop     r14
0x180008c61  pop     r13
0x180008c63  pop     r12
0x180008c65  pop     rdi
0x180008c66  retn
0x180008c67  lea     r15, [r8+1]
0x180008c6b  mov     edx, 2; Size
0x180008c70  add     r15, rbp
0x180008c73  mov     rcx, r15; Count
0x180008c76  call    _calloc_base
0x180008c7b  mov     rbx, rax
0x180008c7e  test    r14, r14
0x180008c81  jz      short loc_180008C9C
0x180008c83  mov     r9, r14; MaxCount
0x180008c86  mov     r8, r13; Source
0x180008c89  mov     rdx, r15; SizeInWords
0x180008c8c  mov     rcx, rax; Destination
0x180008c8f  call    wcsncpy_s
0x180008c94  test    eax, eax
0x180008c96  jnz     loc_180008D71
0x180008c9c  sub     r15, r14
0x180008c9f  lea     rcx, [rbx+r14*2]; Destination
0x180008ca3  mov     rdx, r15; SizeInWords
0x180008ca6  mov     r9, rbp; MaxCount
0x180008ca9  mov     r8, r12; Source
0x180008cac  call    wcsncpy_s
0x180008cb1  test    eax, eax
0x180008cb3  jnz     loc_180008D71
0x180008cb9  mov     r14, [rsi+10h]
0x180008cbd  lea     r15d, [rax+8]
0x180008cc1  cmp     [rsi+8], r14
0x180008cc5  jnz     loc_180008D58
0x180008ccb  cmp     [rsi], rdi
0x180008cce  jnz     short loc_180008CFB
0x180008cd0  mov     edx, r15d; Size
0x180008cd3  lea     ecx, [rax+4]; Count
0x180008cd6  call    _calloc_base
0x180008cdb  xor     ecx, ecx; Block
0x180008cdd  mov     [rsi], rax
0x180008ce0  call    _free_base
0x180008ce5  mov     rax, [rsi]
0x180008ce8  test    rax, rax
0x180008ceb  jz      short loc_180008D2F
0x180008ced  mov     [rsi+8], rax
0x180008cf1  add     rax, 20h ; ' '
0x180008cf5  mov     [rsi+10h], rax
0x180008cf9  jmp     short loc_180008D58
0x180008cfb  sub     r14, [rsi]
0x180008cfe  mov     rax, 7FFFFFFFFFFFFFFFh
0x180008d08  sar     r14, 3
0x180008d0c  cmp     r14, rax
0x180008d0f  ja      short loc_180008D2F
0x180008d11  mov     rcx, [rsi]; Block
0x180008d14  lea     rbp, [r14+r14]
0x180008d18  mov     rdx, rbp; Count
0x180008d1b  mov     r8, r15; Size
0x180008d1e  call    _recalloc_base
0x180008d23  test    rax, rax
0x180008d26  jnz     short loc_180008D3E
0x180008d28  xor     ecx, ecx; Block
0x180008d2a  call    _free_base
0x180008d2f  mov     rcx, rbx; Block
0x180008d32  mov     edi, 0Ch
0x180008d37  call    _free_base
0x180008d3c  jmp     short loc_180008D63
0x180008d3e  lea     rcx, [rax+r14*8]
0x180008d42  mov     [rsi], rax
0x180008d45  mov     [rsi+8], rcx
0x180008d49  lea     rcx, [rax+rbp*8]
0x180008d4d  mov     [rsi+10h], rcx
0x180008d51  xor     ecx, ecx; Block
0x180008d53  call    _free_base
0x180008d58  mov     rcx, [rsi+8]
0x180008d5c  mov     [rcx], rbx
0x180008d5f  add     [rsi+8], r15
0x180008d63  xor     ecx, ecx; Block
0x180008d65  call    _free_base
0x180008d6a  mov     eax, edi
0x180008d6c  jmp     loc_180008C4A
0x180008d71  xor     r9d, r9d; LineNo
0x180008d74  mov     [rsp+58h+Reserved], rdi; Reserved
0x180008d79  xor     r8d, r8d; FileName
0x180008d7c  xor     edx, edx; FunctionName
0x180008d7e  xor     ecx, ecx; Expression
0x180008d80  call    _invoke_watson
```
