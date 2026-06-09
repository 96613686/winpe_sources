# copy_and_add_argument_to_buffer<wchar_t>(wchar_t const * const,wchar_t const * const,unsigned __int64,`anonymous namespace'::argument_list<wchar_t> &)

- ea: `0x140006db4`
- end: `0x140006f3a`
- name: `??$copy_and_add_argument_to_buffer@_W@@YAHQEB_W0_KAEAV?$argument_list@_W@?A0x5f5c8891@@@Z`
- size: `390`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: ``

## callers

- `0x1400069b4`

## callees

- `0x140006564`
- `0x140006640`
- `0x1400068c0`
- `0x140006940`
- `0x140006db4`
- `0x140009920`

## pseudocode

```c
__int64 __fastcall copy_and_add_argument_to_buffer<wchar_t>(__int64 a1, __int64 a2, __int64 a3, void **a4)
{
  __int64 v4; // rbp
  unsigned int v6; // edi
  unsigned __int64 v10; // rbp
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
  while ( *(_WORD *)(a1 + 2 * v4) );
  v10 = v4 + 1;
  if ( v10 > ~a3 )
    return 12;
  v12 = v10 + a3 + 1;
  v13 = (char *)calloc_base(v12, 2u);
  v14 = v13;
  if ( a3 && (unsigned int)sub_140006640(v13, v12, a2, a3)
    || (unsigned int)sub_140006640(&v14[2 * a3], v12 - a3, a1, v10) )
  {
    invoke_watson(0, 0, 0, 0, 0);
  }
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
0x140006db4  mov     [rsp+arg_0], rbx
0x140006db9  mov     [rsp+arg_8], rbp
0x140006dbe  mov     [rsp+arg_10], rsi
0x140006dc3  push    rdi
0x140006dc4  push    r12
0x140006dc6  push    r13
0x140006dc8  push    r14
0x140006dca  push    r15
0x140006dcc  sub     rsp, 30h
0x140006dd0  or      rbp, 0FFFFFFFFFFFFFFFFh
0x140006dd4  mov     rsi, r9
0x140006dd7  xor     edi, edi
0x140006dd9  mov     r14, r8
0x140006ddc  mov     r13, rdx
0x140006ddf  mov     r12, rcx
0x140006de2  inc     rbp
0x140006de5  cmp     [rcx+rbp*2], di
0x140006de9  jnz     short loc_140006DE2
0x140006deb  mov     rax, r14
0x140006dee  inc     rbp
0x140006df1  not     rax
0x140006df4  cmp     rbp, rax
0x140006df7  jbe     short loc_140006E1B
0x140006df9  mov     eax, 0Ch
0x140006dfe  mov     rbx, [rsp+58h+arg_0]
0x140006e03  mov     rbp, [rsp+58h+arg_8]
0x140006e08  mov     rsi, [rsp+58h+arg_10]
0x140006e0d  add     rsp, 30h
0x140006e11  pop     r15
0x140006e13  pop     r14
0x140006e15  pop     r13
0x140006e17  pop     r12
0x140006e19  pop     rdi
0x140006e1a  retn
0x140006e1b  lea     r15, [r8+1]
0x140006e1f  mov     edx, 2; Size
0x140006e24  add     r15, rbp
0x140006e27  mov     rcx, r15; Count
0x140006e2a  call    _calloc_base
0x140006e2f  mov     rbx, rax
0x140006e32  test    r14, r14
0x140006e35  jz      short loc_140006E50
0x140006e37  mov     r9, r14
0x140006e3a  mov     r8, r13
0x140006e3d  mov     rdx, r15
0x140006e40  mov     rcx, rax
0x140006e43  call    sub_140006640
0x140006e48  test    eax, eax
0x140006e4a  jnz     loc_140006F25
0x140006e50  sub     r15, r14
0x140006e53  lea     rcx, [rbx+r14*2]
0x140006e57  mov     rdx, r15
0x140006e5a  mov     r9, rbp
0x140006e5d  mov     r8, r12
0x140006e60  call    sub_140006640
0x140006e65  test    eax, eax
0x140006e67  jnz     loc_140006F25
0x140006e6d  mov     r14, [rsi+10h]
0x140006e71  lea     r15d, [rax+8]
0x140006e75  cmp     [rsi+8], r14
0x140006e79  jnz     loc_140006F0C
0x140006e7f  cmp     [rsi], rdi
0x140006e82  jnz     short loc_140006EAF
0x140006e84  mov     edx, r15d; Size
0x140006e87  lea     ecx, [rax+4]; Count
0x140006e8a  call    _calloc_base
0x140006e8f  xor     ecx, ecx; Block
0x140006e91  mov     [rsi], rax
0x140006e94  call    _free_base
0x140006e99  mov     rax, [rsi]
0x140006e9c  test    rax, rax
0x140006e9f  jz      short loc_140006EE3
0x140006ea1  mov     [rsi+8], rax
0x140006ea5  add     rax, 20h ; ' '
0x140006ea9  mov     [rsi+10h], rax
0x140006ead  jmp     short loc_140006F0C
0x140006eaf  sub     r14, [rsi]
0x140006eb2  mov     rax, 7FFFFFFFFFFFFFFFh
0x140006ebc  sar     r14, 3
0x140006ec0  cmp     r14, rax
0x140006ec3  ja      short loc_140006EE3
0x140006ec5  mov     rcx, [rsi]; Block
0x140006ec8  lea     rbp, [r14+r14]
0x140006ecc  mov     rdx, rbp; Count
0x140006ecf  mov     r8, r15; Size
0x140006ed2  call    _recalloc_base
0x140006ed7  test    rax, rax
0x140006eda  jnz     short loc_140006EF2
0x140006edc  xor     ecx, ecx; Block
0x140006ede  call    _free_base
0x140006ee3  mov     rcx, rbx; Block
0x140006ee6  mov     edi, 0Ch
0x140006eeb  call    _free_base
0x140006ef0  jmp     short loc_140006F17
0x140006ef2  lea     rcx, [rax+r14*8]
0x140006ef6  mov     [rsi], rax
0x140006ef9  mov     [rsi+8], rcx
0x140006efd  lea     rcx, [rax+rbp*8]
0x140006f01  mov     [rsi+10h], rcx
0x140006f05  xor     ecx, ecx; Block
0x140006f07  call    _free_base
0x140006f0c  mov     rcx, [rsi+8]
0x140006f10  mov     [rcx], rbx
0x140006f13  add     [rsi+8], r15
0x140006f17  xor     ecx, ecx; Block
0x140006f19  call    _free_base
0x140006f1e  mov     eax, edi
0x140006f20  jmp     loc_140006DFE
0x140006f25  xor     r9d, r9d; LineNo
0x140006f28  mov     [rsp+58h+Reserved], rdi; Reserved
0x140006f2d  xor     r8d, r8d; FileName
0x140006f30  xor     edx, edx; FunctionName
0x140006f32  xor     ecx, ecx; Expression
0x140006f34  call    _invoke_watson
```
