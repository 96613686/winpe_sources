# copy_and_add_argument_to_buffer_wchar_t_

- ea: `0x140016e94`
- end: `0x14001701a`
- name: `copy_and_add_argument_to_buffer_wchar_t_`
- size: `390`
- prototype: `__int64 __fastcall(wchar_t *Source, wchar_t *, rsize_t MaxCount)`
- caller_count: `1`
- callee_count: `6`
- tags: ``

## callers

- `0x140016a94`

## callees

- `0x14000bf7c`
- `0x140013e10`
- `0x140013fe0`
- `0x140016930`
- `0x140016e94`
- `0x140018130`

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
0x140016e94  mov     [rsp+arg_0], rbx
0x140016e99  mov     [rsp+arg_8], rbp
0x140016e9e  mov     [rsp+arg_10], rsi
0x140016ea3  push    rdi
0x140016ea4  push    r12
0x140016ea6  push    r13
0x140016ea8  push    r14
0x140016eaa  push    r15
0x140016eac  sub     rsp, 30h
0x140016eb0  or      rbp, 0FFFFFFFFFFFFFFFFh
0x140016eb4  mov     rsi, r9
0x140016eb7  xor     edi, edi
0x140016eb9  mov     r14, r8
0x140016ebc  mov     r13, rdx
0x140016ebf  mov     r12, rcx
0x140016ec2  inc     rbp
0x140016ec5  cmp     [rcx+rbp*2], di
0x140016ec9  jnz     short loc_140016EC2
0x140016ecb  mov     rax, r14
0x140016ece  inc     rbp
0x140016ed1  not     rax
0x140016ed4  cmp     rbp, rax
0x140016ed7  jbe     short loc_140016EFB
0x140016ed9  mov     eax, 0Ch
0x140016ede  mov     rbx, [rsp+58h+arg_0]
0x140016ee3  mov     rbp, [rsp+58h+arg_8]
0x140016ee8  mov     rsi, [rsp+58h+arg_10]
0x140016eed  add     rsp, 30h
0x140016ef1  pop     r15
0x140016ef3  pop     r14
0x140016ef5  pop     r13
0x140016ef7  pop     r12
0x140016ef9  pop     rdi
0x140016efa  retn
0x140016efb  lea     r15, [r8+1]
0x140016eff  mov     edx, 2; Size
0x140016f04  add     r15, rbp
0x140016f07  mov     rcx, r15; Count
0x140016f0a  call    _calloc_base
0x140016f0f  mov     rbx, rax
0x140016f12  test    r14, r14
0x140016f15  jz      short loc_140016F30
0x140016f17  mov     r9, r14; MaxCount
0x140016f1a  mov     r8, r13; Source
0x140016f1d  mov     rdx, r15; SizeInWords
0x140016f20  mov     rcx, rax; Destination
0x140016f23  call    wcsncpy_s
0x140016f28  test    eax, eax
0x140016f2a  jnz     loc_140017005
0x140016f30  sub     r15, r14
0x140016f33  lea     rcx, [rbx+r14*2]; Destination
0x140016f37  mov     rdx, r15; SizeInWords
0x140016f3a  mov     r9, rbp; MaxCount
0x140016f3d  mov     r8, r12; Source
0x140016f40  call    wcsncpy_s
0x140016f45  test    eax, eax
0x140016f47  jnz     loc_140017005
0x140016f4d  mov     r14, [rsi+10h]
0x140016f51  lea     r15d, [rax+8]
0x140016f55  cmp     [rsi+8], r14
0x140016f59  jnz     loc_140016FEC
0x140016f5f  cmp     [rsi], rdi
0x140016f62  jnz     short loc_140016F8F
0x140016f64  mov     edx, r15d; Size
0x140016f67  lea     ecx, [rax+4]; Count
0x140016f6a  call    _calloc_base
0x140016f6f  xor     ecx, ecx; Block
0x140016f71  mov     [rsi], rax
0x140016f74  call    _free_base
0x140016f79  mov     rax, [rsi]
0x140016f7c  test    rax, rax
0x140016f7f  jz      short loc_140016FC3
0x140016f81  mov     [rsi+8], rax
0x140016f85  add     rax, 20h ; ' '
0x140016f89  mov     [rsi+10h], rax
0x140016f8d  jmp     short loc_140016FEC
0x140016f8f  sub     r14, [rsi]
0x140016f92  mov     rax, 7FFFFFFFFFFFFFFFh
0x140016f9c  sar     r14, 3
0x140016fa0  cmp     r14, rax
0x140016fa3  ja      short loc_140016FC3
0x140016fa5  mov     rcx, [rsi]; Block
0x140016fa8  lea     rbp, [r14+r14]
0x140016fac  mov     rdx, rbp; Count
0x140016faf  mov     r8, r15; Size
0x140016fb2  call    _recalloc_base
0x140016fb7  test    rax, rax
0x140016fba  jnz     short loc_140016FD2
0x140016fbc  xor     ecx, ecx; Block
0x140016fbe  call    _free_base
0x140016fc3  mov     rcx, rbx; Block
0x140016fc6  mov     edi, 0Ch
0x140016fcb  call    _free_base
0x140016fd0  jmp     short loc_140016FF7
0x140016fd2  lea     rcx, [rax+r14*8]
0x140016fd6  mov     [rsi], rax
0x140016fd9  mov     [rsi+8], rcx
0x140016fdd  lea     rcx, [rax+rbp*8]
0x140016fe1  mov     [rsi+10h], rcx
0x140016fe5  xor     ecx, ecx; Block
0x140016fe7  call    _free_base
0x140016fec  mov     rcx, [rsi+8]
0x140016ff0  mov     [rcx], rbx
0x140016ff3  add     [rsi+8], r15
0x140016ff7  xor     ecx, ecx; Block
0x140016ff9  call    _free_base
0x140016ffe  mov     eax, edi
0x140017000  jmp     loc_140016EDE
0x140017005  xor     r9d, r9d; LineNo
0x140017008  mov     [rsp+58h+Reserved], rdi; Reserved
0x14001700d  xor     r8d, r8d; FileName
0x140017010  xor     edx, edx; FunctionName
0x140017012  xor     ecx, ecx; Expression
0x140017014  call    _invoke_watson
```
