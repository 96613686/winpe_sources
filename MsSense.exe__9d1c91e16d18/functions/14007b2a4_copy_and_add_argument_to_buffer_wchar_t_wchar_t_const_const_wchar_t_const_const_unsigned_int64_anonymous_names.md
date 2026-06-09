# copy_and_add_argument_to_buffer<wchar_t>(wchar_t const * const,wchar_t const * const,unsigned __int64,`anonymous namespace'::argument_list<wchar_t> &)

- ea: `0x14007b2a4`
- end: `0x14007b42a`
- name: `??$copy_and_add_argument_to_buffer@_W@@YAHQEB_W0_KAEAV?$argument_list@_W@?A0x5f5c8891@@@Z`
- size: `390`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, void **)`
- caller_count: `1`
- callee_count: `6`
- tags: ``

## callers

- `0x14007aea4`

## callees

- `0x140061554`
- `0x140066da0`
- `0x1400719e0`
- `0x140072280`
- `0x140073d10`
- `0x14007b2a4`

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
  if ( a3 && (unsigned int)sub_140066DA0(v13, v12, a2, a3)
    || (unsigned int)sub_140066DA0(&v14[2 * a3], v12 - a3, a1, v10) )
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
0x14007b2a4  mov     [rsp+arg_0], rbx
0x14007b2a9  mov     [rsp+arg_8], rbp
0x14007b2ae  mov     [rsp+arg_10], rsi
0x14007b2b3  push    rdi
0x14007b2b4  push    r12
0x14007b2b6  push    r13
0x14007b2b8  push    r14
0x14007b2ba  push    r15
0x14007b2bc  sub     rsp, 30h
0x14007b2c0  or      rbp, 0FFFFFFFFFFFFFFFFh
0x14007b2c4  mov     rsi, r9
0x14007b2c7  xor     edi, edi
0x14007b2c9  mov     r14, r8
0x14007b2cc  mov     r13, rdx
0x14007b2cf  mov     r12, rcx
0x14007b2d2  inc     rbp
0x14007b2d5  cmp     [rcx+rbp*2], di
0x14007b2d9  jnz     short loc_14007B2D2
0x14007b2db  mov     rax, r14
0x14007b2de  inc     rbp
0x14007b2e1  not     rax
0x14007b2e4  cmp     rbp, rax
0x14007b2e7  jbe     short loc_14007B30B
0x14007b2e9  mov     eax, 0Ch
0x14007b2ee  mov     rbx, [rsp+58h+arg_0]
0x14007b2f3  mov     rbp, [rsp+58h+arg_8]
0x14007b2f8  mov     rsi, [rsp+58h+arg_10]
0x14007b2fd  add     rsp, 30h
0x14007b301  pop     r15
0x14007b303  pop     r14
0x14007b305  pop     r13
0x14007b307  pop     r12
0x14007b309  pop     rdi
0x14007b30a  retn
0x14007b30b  lea     r15, [r8+1]
0x14007b30f  mov     edx, 2; Size
0x14007b314  add     r15, rbp
0x14007b317  mov     rcx, r15; Count
0x14007b31a  call    _calloc_base
0x14007b31f  mov     rbx, rax
0x14007b322  test    r14, r14
0x14007b325  jz      short loc_14007B340
0x14007b327  mov     r9, r14
0x14007b32a  mov     r8, r13
0x14007b32d  mov     rdx, r15
0x14007b330  mov     rcx, rax
0x14007b333  call    sub_140066DA0
0x14007b338  test    eax, eax
0x14007b33a  jnz     loc_14007B415
0x14007b340  sub     r15, r14
0x14007b343  lea     rcx, [rbx+r14*2]
0x14007b347  mov     rdx, r15
0x14007b34a  mov     r9, rbp
0x14007b34d  mov     r8, r12
0x14007b350  call    sub_140066DA0
0x14007b355  test    eax, eax
0x14007b357  jnz     loc_14007B415
0x14007b35d  mov     r14, [rsi+10h]
0x14007b361  lea     r15d, [rax+8]
0x14007b365  cmp     [rsi+8], r14
0x14007b369  jnz     loc_14007B3FC
0x14007b36f  cmp     [rsi], rdi
0x14007b372  jnz     short loc_14007B39F
0x14007b374  mov     edx, r15d; Size
0x14007b377  lea     ecx, [rax+4]; Count
0x14007b37a  call    _calloc_base
0x14007b37f  xor     ecx, ecx; Block
0x14007b381  mov     [rsi], rax
0x14007b384  call    _free_base
0x14007b389  mov     rax, [rsi]
0x14007b38c  test    rax, rax
0x14007b38f  jz      short loc_14007B3D3
0x14007b391  mov     [rsi+8], rax
0x14007b395  add     rax, 20h ; ' '
0x14007b399  mov     [rsi+10h], rax
0x14007b39d  jmp     short loc_14007B3FC
0x14007b39f  sub     r14, [rsi]
0x14007b3a2  mov     rax, 7FFFFFFFFFFFFFFFh
0x14007b3ac  sar     r14, 3
0x14007b3b0  cmp     r14, rax
0x14007b3b3  ja      short loc_14007B3D3
0x14007b3b5  mov     rcx, [rsi]; Block
0x14007b3b8  lea     rbp, [r14+r14]
0x14007b3bc  mov     rdx, rbp; Count
0x14007b3bf  mov     r8, r15; Size
0x14007b3c2  call    _recalloc_base
0x14007b3c7  test    rax, rax
0x14007b3ca  jnz     short loc_14007B3E2
0x14007b3cc  xor     ecx, ecx; Block
0x14007b3ce  call    _free_base
0x14007b3d3  mov     rcx, rbx; Block
0x14007b3d6  mov     edi, 0Ch
0x14007b3db  call    _free_base
0x14007b3e0  jmp     short loc_14007B407
0x14007b3e2  lea     rcx, [rax+r14*8]
0x14007b3e6  mov     [rsi], rax
0x14007b3e9  mov     [rsi+8], rcx
0x14007b3ed  lea     rcx, [rax+rbp*8]
0x14007b3f1  mov     [rsi+10h], rcx
0x14007b3f5  xor     ecx, ecx; Block
0x14007b3f7  call    _free_base
0x14007b3fc  mov     rcx, [rsi+8]
0x14007b400  mov     [rcx], rbx
0x14007b403  add     [rsi+8], r15
0x14007b407  xor     ecx, ecx; Block
0x14007b409  call    _free_base
0x14007b40e  mov     eax, edi
0x14007b410  jmp     loc_14007B2EE
0x14007b415  xor     r9d, r9d; LineNo
0x14007b418  mov     [rsp+58h+Reserved], rdi; Reserved
0x14007b41d  xor     r8d, r8d; FileName
0x14007b420  xor     edx, edx; FunctionName
0x14007b422  xor     ecx, ecx; Expression
0x14007b424  call    _invoke_watson
```
