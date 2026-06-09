# copy_and_add_argument_to_buffer<wchar_t>(wchar_t const * const,wchar_t const * const,unsigned __int64,`anonymous namespace'::argument_list<wchar_t> &)

- ea: `0x140023a04`
- end: `0x140023b8a`
- name: `??$copy_and_add_argument_to_buffer@_W@@YAHQEB_W0_KAEAV?$argument_list@_W@?A0x5f5c8891@@@Z`
- size: `390`
- prototype: `__int64 __fastcall(wchar_t *Src, wchar_t *, size_t MaxCount, void **)`
- caller_count: `1`
- callee_count: `6`
- tags: ``

## callers

- `0x140023604`

## callees

- `0x14000471c`
- `0x140004958`
- `0x14001074c`
- `0x1400107c4`
- `0x14001a8d8`
- `0x140023a04`

## pseudocode

```c
__int64 __fastcall copy_and_add_argument_to_buffer<wchar_t>(wchar_t *Src, wchar_t *a2, size_t MaxCount, void **a4)
{
  __int64 v4; // rbp
  unsigned int v6; // edi
  size_t v10; // rbp
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
  while ( Src[v4] );
  v10 = v4 + 1;
  if ( v10 > ~MaxCount )
    return 12;
  v12 = v10 + MaxCount + 1;
  v13 = (wchar_t *)calloc_base(v12, 2u);
  v14 = v13;
  if ( MaxCount && wcsncpy_s(v13, v12, a2, MaxCount) || wcsncpy_s(&v14[MaxCount], v12 - MaxCount, Src, v10) )
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
0x140023a04  mov     [rsp+arg_0], rbx
0x140023a09  mov     [rsp+arg_8], rbp
0x140023a0e  mov     [rsp+arg_10], rsi
0x140023a13  push    rdi
0x140023a14  push    r12
0x140023a16  push    r13
0x140023a18  push    r14
0x140023a1a  push    r15
0x140023a1c  sub     rsp, 30h
0x140023a20  or      rbp, 0FFFFFFFFFFFFFFFFh
0x140023a24  mov     rsi, r9
0x140023a27  xor     edi, edi
0x140023a29  mov     r14, r8
0x140023a2c  mov     r13, rdx
0x140023a2f  mov     r12, rcx
0x140023a32  inc     rbp
0x140023a35  cmp     [rcx+rbp*2], di
0x140023a39  jnz     short loc_140023A32
0x140023a3b  mov     rax, r14
0x140023a3e  inc     rbp
0x140023a41  not     rax
0x140023a44  cmp     rbp, rax
0x140023a47  jbe     short loc_140023A6B
0x140023a49  mov     eax, 0Ch
0x140023a4e  mov     rbx, [rsp+58h+arg_0]
0x140023a53  mov     rbp, [rsp+58h+arg_8]
0x140023a58  mov     rsi, [rsp+58h+arg_10]
0x140023a5d  add     rsp, 30h
0x140023a61  pop     r15
0x140023a63  pop     r14
0x140023a65  pop     r13
0x140023a67  pop     r12
0x140023a69  pop     rdi
0x140023a6a  retn
0x140023a6b  lea     r15, [r8+1]
0x140023a6f  mov     edx, 2; Size
0x140023a74  add     r15, rbp
0x140023a77  mov     rcx, r15; Count
0x140023a7a  call    _calloc_base
0x140023a7f  mov     rbx, rax
0x140023a82  test    r14, r14
0x140023a85  jz      short loc_140023AA0
0x140023a87  mov     r9, r14; MaxCount
0x140023a8a  mov     r8, r13; Src
0x140023a8d  mov     rdx, r15; DstSizeInChars
0x140023a90  mov     rcx, rax; Dst
0x140023a93  call    wcsncpy_s
0x140023a98  test    eax, eax
0x140023a9a  jnz     loc_140023B75
0x140023aa0  sub     r15, r14
0x140023aa3  lea     rcx, [rbx+r14*2]; Dst
0x140023aa7  mov     rdx, r15; DstSizeInChars
0x140023aaa  mov     r9, rbp; MaxCount
0x140023aad  mov     r8, r12; Src
0x140023ab0  call    wcsncpy_s
0x140023ab5  test    eax, eax
0x140023ab7  jnz     loc_140023B75
0x140023abd  mov     r14, [rsi+10h]
0x140023ac1  lea     r15d, [rax+8]
0x140023ac5  cmp     [rsi+8], r14
0x140023ac9  jnz     loc_140023B5C
0x140023acf  cmp     [rsi], rdi
0x140023ad2  jnz     short loc_140023AFF
0x140023ad4  mov     edx, r15d; Size
0x140023ad7  lea     ecx, [rax+4]; Count
0x140023ada  call    _calloc_base
0x140023adf  xor     ecx, ecx; Block
0x140023ae1  mov     [rsi], rax
0x140023ae4  call    _free_base
0x140023ae9  mov     rax, [rsi]
0x140023aec  test    rax, rax
0x140023aef  jz      short loc_140023B33
0x140023af1  mov     [rsi+8], rax
0x140023af5  add     rax, 20h ; ' '
0x140023af9  mov     [rsi+10h], rax
0x140023afd  jmp     short loc_140023B5C
0x140023aff  sub     r14, [rsi]
0x140023b02  mov     rax, 7FFFFFFFFFFFFFFFh
0x140023b0c  sar     r14, 3
0x140023b10  cmp     r14, rax
0x140023b13  ja      short loc_140023B33
0x140023b15  mov     rcx, [rsi]; Block
0x140023b18  lea     rbp, [r14+r14]
0x140023b1c  mov     rdx, rbp; Count
0x140023b1f  mov     r8, r15; Size
0x140023b22  call    _recalloc_base
0x140023b27  test    rax, rax
0x140023b2a  jnz     short loc_140023B42
0x140023b2c  xor     ecx, ecx; Block
0x140023b2e  call    _free_base
0x140023b33  mov     rcx, rbx; Block
0x140023b36  mov     edi, 0Ch
0x140023b3b  call    _free_base
0x140023b40  jmp     short loc_140023B67
0x140023b42  lea     rcx, [rax+r14*8]
0x140023b46  mov     [rsi], rax
0x140023b49  mov     [rsi+8], rcx
0x140023b4d  lea     rcx, [rax+rbp*8]
0x140023b51  mov     [rsi+10h], rcx
0x140023b55  xor     ecx, ecx; Block
0x140023b57  call    _free_base
0x140023b5c  mov     rcx, [rsi+8]
0x140023b60  mov     [rcx], rbx
0x140023b63  add     [rsi+8], r15
0x140023b67  xor     ecx, ecx; Block
0x140023b69  call    _free_base
0x140023b6e  mov     eax, edi
0x140023b70  jmp     loc_140023A4E
0x140023b75  xor     r9d, r9d; LineNo
0x140023b78  mov     [rsp+58h+Reserved], rdi; Reserved
0x140023b7d  xor     r8d, r8d; FileName
0x140023b80  xor     edx, edx; FunctionName
0x140023b82  xor     ecx, ecx; Expression
0x140023b84  call    _invoke_watson
```
