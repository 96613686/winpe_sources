# copy_and_add_argument_to_buffer_wchar_t_

- ea: `0x1800084a0`
- end: `0x180008626`
- name: `copy_and_add_argument_to_buffer_wchar_t_`
- size: `390`
- prototype: `__int64 __fastcall(wchar_t *Source, wchar_t *, rsize_t MaxCount)`
- caller_count: `2`
- callee_count: `6`
- tags: ``

## callers

- `0x180007f1c`
- `0x180008988`

## callees

- `0x1800074f0`
- `0x180007860`
- `0x1800078e0`
- `0x1800084a0`
- `0x18000be80`
- `0x1800125a0`

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
0x1800084a0  mov     [rsp+arg_0], rbx
0x1800084a5  mov     [rsp+arg_8], rbp
0x1800084aa  mov     [rsp+arg_10], rsi
0x1800084af  push    rdi
0x1800084b0  push    r12
0x1800084b2  push    r13
0x1800084b4  push    r14
0x1800084b6  push    r15
0x1800084b8  sub     rsp, 30h
0x1800084bc  or      rbp, 0FFFFFFFFFFFFFFFFh
0x1800084c0  mov     rsi, r9
0x1800084c3  xor     edi, edi
0x1800084c5  mov     r14, r8
0x1800084c8  mov     r13, rdx
0x1800084cb  mov     r12, rcx
0x1800084ce  inc     rbp
0x1800084d1  cmp     [rcx+rbp*2], di
0x1800084d5  jnz     short loc_1800084CE
0x1800084d7  mov     rax, r14
0x1800084da  inc     rbp
0x1800084dd  not     rax
0x1800084e0  cmp     rbp, rax
0x1800084e3  jbe     short loc_180008507
0x1800084e5  mov     eax, 0Ch
0x1800084ea  mov     rbx, [rsp+58h+arg_0]
0x1800084ef  mov     rbp, [rsp+58h+arg_8]
0x1800084f4  mov     rsi, [rsp+58h+arg_10]
0x1800084f9  add     rsp, 30h
0x1800084fd  pop     r15
0x1800084ff  pop     r14
0x180008501  pop     r13
0x180008503  pop     r12
0x180008505  pop     rdi
0x180008506  retn
0x180008507  lea     r15, [r8+1]
0x18000850b  mov     edx, 2; Size
0x180008510  add     r15, rbp
0x180008513  mov     rcx, r15; Count
0x180008516  call    _calloc_base
0x18000851b  mov     rbx, rax
0x18000851e  test    r14, r14
0x180008521  jz      short loc_18000853C
0x180008523  mov     r9, r14; MaxCount
0x180008526  mov     r8, r13; Source
0x180008529  mov     rdx, r15; SizeInWords
0x18000852c  mov     rcx, rax; Destination
0x18000852f  call    wcsncpy_s
0x180008534  test    eax, eax
0x180008536  jnz     loc_180008611
0x18000853c  sub     r15, r14
0x18000853f  lea     rcx, [rbx+r14*2]; Destination
0x180008543  mov     rdx, r15; SizeInWords
0x180008546  mov     r9, rbp; MaxCount
0x180008549  mov     r8, r12; Source
0x18000854c  call    wcsncpy_s
0x180008551  test    eax, eax
0x180008553  jnz     loc_180008611
0x180008559  mov     r14, [rsi+10h]
0x18000855d  lea     r15d, [rax+8]
0x180008561  cmp     [rsi+8], r14
0x180008565  jnz     loc_1800085F8
0x18000856b  cmp     [rsi], rdi
0x18000856e  jnz     short loc_18000859B
0x180008570  mov     edx, r15d; Size
0x180008573  lea     ecx, [rax+4]; Count
0x180008576  call    _calloc_base
0x18000857b  xor     ecx, ecx; Block
0x18000857d  mov     [rsi], rax
0x180008580  call    _free_base
0x180008585  mov     rax, [rsi]
0x180008588  test    rax, rax
0x18000858b  jz      short loc_1800085CF
0x18000858d  mov     [rsi+8], rax
0x180008591  add     rax, 20h ; ' '
0x180008595  mov     [rsi+10h], rax
0x180008599  jmp     short loc_1800085F8
0x18000859b  sub     r14, [rsi]
0x18000859e  mov     rax, 7FFFFFFFFFFFFFFFh
0x1800085a8  sar     r14, 3
0x1800085ac  cmp     r14, rax
0x1800085af  ja      short loc_1800085CF
0x1800085b1  mov     rcx, [rsi]; Block
0x1800085b4  lea     rbp, [r14+r14]
0x1800085b8  mov     rdx, rbp; Count
0x1800085bb  mov     r8, r15; Size
0x1800085be  call    _recalloc_base
0x1800085c3  test    rax, rax
0x1800085c6  jnz     short loc_1800085DE
0x1800085c8  xor     ecx, ecx; Block
0x1800085ca  call    _free_base
0x1800085cf  mov     rcx, rbx; Block
0x1800085d2  mov     edi, 0Ch
0x1800085d7  call    _free_base
0x1800085dc  jmp     short loc_180008603
0x1800085de  lea     rcx, [rax+r14*8]
0x1800085e2  mov     [rsi], rax
0x1800085e5  mov     [rsi+8], rcx
0x1800085e9  lea     rcx, [rax+rbp*8]
0x1800085ed  mov     [rsi+10h], rcx
0x1800085f1  xor     ecx, ecx; Block
0x1800085f3  call    _free_base
0x1800085f8  mov     rcx, [rsi+8]
0x1800085fc  mov     [rcx], rbx
0x1800085ff  add     [rsi+8], r15
0x180008603  xor     ecx, ecx; Block
0x180008605  call    _free_base
0x18000860a  mov     eax, edi
0x18000860c  jmp     loc_1800084EA
0x180008611  xor     r9d, r9d; LineNo
0x180008614  mov     [rsp+58h+Reserved], rdi; Reserved
0x180008619  xor     r8d, r8d; FileName
0x18000861c  xor     edx, edx; FunctionName
0x18000861e  xor     ecx, ecx; Expression
0x180008620  call    _invoke_watson
```
