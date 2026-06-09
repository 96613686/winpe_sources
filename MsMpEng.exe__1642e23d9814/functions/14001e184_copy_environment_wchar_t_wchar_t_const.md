# copy_environment<wchar_t>(wchar_t * * const)

- ea: `0x14001e184`
- end: `0x14001e273`
- name: `??$copy_environment@_W@@YAPEAPEA_WQEAPEA_W@Z`
- size: `239`
- prototype: `_BYTE *__fastcall(_QWORD *)`
- caller_count: `1`
- callee_count: `6`
- tags: ``

## callers

- `0x14001de20`

## callees

- `0x1400160bc`
- `0x140019148`
- `0x140019930`
- `0x14001b910`
- `0x14001d490`
- `0x14001e184`

## pseudocode

```c
_BYTE *__fastcall copy_environment<wchar_t>(_QWORD *a1)
{
  _QWORD *v1; // rdi
  __int64 v3; // rcx
  _QWORD *i; // rax
  _BYTE *v5; // rbx
  __int64 v6; // rax
  signed __int64 v7; // r14
  __int64 v8; // rsi
  __int64 v9; // rcx

  v1 = a1;
  if ( !a1 )
    return 0;
  v3 = 0;
  for ( i = v1; *i; ++i )
    ++v3;
  v5 = calloc_base(v3 + 1, 8u);
  if ( !v5 )
LABEL_15:
    abort();
  v6 = *v1;
  if ( *v1 )
  {
    v7 = v5 - (_BYTE *)v1;
    do
    {
      v8 = -1;
      do
        ++v8;
      while ( *(_WORD *)(v6 + 2 * v8) );
      *(_QWORD *)((char *)v1 + v7) = calloc_base(v8 + 1, 2u);
      free_base(0);
      v9 = *(_QWORD *)((char *)v1 + v7);
      if ( !v9 )
        goto LABEL_15;
      if ( (unsigned int)sub_14001D490(v9, v8 + 1, *v1) )
        invoke_watson(0, 0, 0, 0, 0);
      v6 = *++v1;
    }
    while ( *v1 );
  }
  free_base(0);
  return v5;
}

```

## disassembly

```asm
0x14001e184  mov     rax, rsp
0x14001e187  mov     [rax+8], rbx
0x14001e18b  mov     [rax+10h], rbp
0x14001e18f  mov     [rax+18h], rsi
0x14001e193  mov     [rax+20h], rdi
0x14001e197  push    r14
0x14001e199  sub     rsp, 30h
0x14001e19d  xor     ebp, ebp
0x14001e19f  mov     rdi, rcx
0x14001e1a2  test    rcx, rcx
0x14001e1a5  jnz     short loc_14001E1C4
0x14001e1a7  xor     eax, eax
0x14001e1a9  mov     rbx, [rsp+38h+arg_0]
0x14001e1ae  mov     rbp, [rsp+38h+arg_8]
0x14001e1b3  mov     rsi, [rsp+38h+arg_10]
0x14001e1b8  mov     rdi, [rsp+38h+arg_18]
0x14001e1bd  add     rsp, 30h
0x14001e1c1  pop     r14
0x14001e1c3  retn
0x14001e1c4  mov     rcx, rbp
0x14001e1c7  mov     rax, rdi
0x14001e1ca  cmp     [rdi], rbp
0x14001e1cd  jz      short loc_14001E1DB
0x14001e1cf  inc     rcx
0x14001e1d2  lea     rax, [rax+8]
0x14001e1d6  cmp     [rax], rbp
0x14001e1d9  jnz     short loc_14001E1CF
0x14001e1db  inc     rcx; Count
0x14001e1de  mov     edx, 8; Size
0x14001e1e3  call    _calloc_base
0x14001e1e8  mov     rbx, rax
0x14001e1eb  test    rax, rax
0x14001e1ee  jz      short loc_14001E26D
0x14001e1f0  mov     rax, [rdi]
0x14001e1f3  test    rax, rax
0x14001e1f6  jz      short loc_14001E249
0x14001e1f8  mov     r14, rbx
0x14001e1fb  sub     r14, rdi
0x14001e1fe  or      rsi, 0FFFFFFFFFFFFFFFFh
0x14001e202  inc     rsi
0x14001e205  cmp     [rax+rsi*2], bp
0x14001e209  jnz     short loc_14001E202
0x14001e20b  mov     edx, 2; Size
0x14001e210  lea     rcx, [rsi+1]; Count
0x14001e214  call    _calloc_base
0x14001e219  xor     ecx, ecx; Block
0x14001e21b  mov     [r14+rdi], rax
0x14001e21f  call    _free_base
0x14001e224  mov     rcx, [r14+rdi]
0x14001e228  test    rcx, rcx
0x14001e22b  jz      short loc_14001E26D
0x14001e22d  mov     r8, [rdi]
0x14001e230  lea     rdx, [rsi+1]
0x14001e234  call    sub_14001D490
0x14001e239  test    eax, eax
0x14001e23b  jnz     short loc_14001E258
0x14001e23d  add     rdi, 8
0x14001e241  mov     rax, [rdi]
0x14001e244  test    rax, rax
0x14001e247  jnz     short loc_14001E1FE
0x14001e249  xor     ecx, ecx; Block
0x14001e24b  call    _free_base
0x14001e250  mov     rax, rbx
0x14001e253  jmp     loc_14001E1A9
0x14001e258  xor     r9d, r9d; LineNo
0x14001e25b  mov     [rsp+38h+Reserved], rbp; Reserved
0x14001e260  xor     r8d, r8d; FileName
0x14001e263  xor     edx, edx; FunctionName
0x14001e265  xor     ecx, ecx; Expression
0x14001e267  call    _invoke_watson
0x14001e26d  call    abort
```
