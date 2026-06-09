# copy_environment<wchar_t>(wchar_t * * const)

- ea: `0x1400080a4`
- end: `0x140008193`
- name: `??$copy_environment@_W@@YAPEAPEA_WQEAPEA_W@Z`
- size: `239`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: ``

## callers

- `0x140007d40`

## callees

- `0x140005a20`
- `0x140006564`
- `0x1400065b0`
- `0x1400068c0`
- `0x140006940`
- `0x1400080a4`

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
      if ( (unsigned int)sub_1400065B0(v9, v8 + 1, *v1) )
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
0x1400080a4  mov     rax, rsp
0x1400080a7  mov     [rax+8], rbx
0x1400080ab  mov     [rax+10h], rbp
0x1400080af  mov     [rax+18h], rsi
0x1400080b3  mov     [rax+20h], rdi
0x1400080b7  push    r14
0x1400080b9  sub     rsp, 30h
0x1400080bd  xor     ebp, ebp
0x1400080bf  mov     rdi, rcx
0x1400080c2  test    rcx, rcx
0x1400080c5  jnz     short loc_1400080E4
0x1400080c7  xor     eax, eax
0x1400080c9  mov     rbx, [rsp+38h+arg_0]
0x1400080ce  mov     rbp, [rsp+38h+arg_8]
0x1400080d3  mov     rsi, [rsp+38h+arg_10]
0x1400080d8  mov     rdi, [rsp+38h+arg_18]
0x1400080dd  add     rsp, 30h
0x1400080e1  pop     r14
0x1400080e3  retn
0x1400080e4  mov     rcx, rbp
0x1400080e7  mov     rax, rdi
0x1400080ea  cmp     [rdi], rbp
0x1400080ed  jz      short loc_1400080FB
0x1400080ef  inc     rcx
0x1400080f2  lea     rax, [rax+8]
0x1400080f6  cmp     [rax], rbp
0x1400080f9  jnz     short loc_1400080EF
0x1400080fb  inc     rcx; Count
0x1400080fe  mov     edx, 8; Size
0x140008103  call    _calloc_base
0x140008108  mov     rbx, rax
0x14000810b  test    rax, rax
0x14000810e  jz      short loc_14000818D
0x140008110  mov     rax, [rdi]
0x140008113  test    rax, rax
0x140008116  jz      short loc_140008169
0x140008118  mov     r14, rbx
0x14000811b  sub     r14, rdi
0x14000811e  or      rsi, 0FFFFFFFFFFFFFFFFh
0x140008122  inc     rsi
0x140008125  cmp     [rax+rsi*2], bp
0x140008129  jnz     short loc_140008122
0x14000812b  mov     edx, 2; Size
0x140008130  lea     rcx, [rsi+1]; Count
0x140008134  call    _calloc_base
0x140008139  xor     ecx, ecx; Block
0x14000813b  mov     [r14+rdi], rax
0x14000813f  call    _free_base
0x140008144  mov     rcx, [r14+rdi]
0x140008148  test    rcx, rcx
0x14000814b  jz      short loc_14000818D
0x14000814d  mov     r8, [rdi]
0x140008150  lea     rdx, [rsi+1]
0x140008154  call    sub_1400065B0
0x140008159  test    eax, eax
0x14000815b  jnz     short loc_140008178
0x14000815d  add     rdi, 8
0x140008161  mov     rax, [rdi]
0x140008164  test    rax, rax
0x140008167  jnz     short loc_14000811E
0x140008169  xor     ecx, ecx; Block
0x14000816b  call    _free_base
0x140008170  mov     rax, rbx
0x140008173  jmp     loc_1400080C9
0x140008178  xor     r9d, r9d; LineNo
0x14000817b  mov     [rsp+38h+Reserved], rbp; Reserved
0x140008180  xor     r8d, r8d; FileName
0x140008183  xor     edx, edx; FunctionName
0x140008185  xor     ecx, ecx; Expression
0x140008187  call    _invoke_watson
0x14000818d  call    abort
```
