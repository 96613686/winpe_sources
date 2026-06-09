# create_environment<wchar_t>(wchar_t * const)

- ea: `0x140070e00`
- end: `0x140070f1e`
- name: `??$create_environment@_W@@YAQEAPEA_WQEA_W@Z`
- size: `286`
- prototype: `void *__fastcall(__int16 *)`
- caller_count: `1`
- callee_count: `6`
- tags: ``

## callers

- `0x140070d90`

## callees

- `0x140061554`
- `0x14006c410`
- `0x140070e00`
- `0x140070f20`
- `0x140072280`
- `0x140073d10`

## pseudocode

```c
void *__fastcall create_environment<wchar_t>(__int16 *a1)
{
  __int64 v2; // rcx
  __int16 *v3; // r8
  __int16 i; // dx
  __int64 v5; // rax
  __int64 v6; // rax
  void *v7; // rax
  void *v8; // rbx
  _QWORD *v10; // r15
  __int64 v11; // rsi
  size_t v12; // rsi
  void *v13; // rax
  void *v14; // rdi

  v2 = 0;
  v3 = a1;
  for ( i = *a1; i; i = *v3 )
  {
    v5 = v2 + 1;
    if ( i == 61 )
      v5 = v2;
    v2 = v5;
    v6 = -1;
    do
      ++v6;
    while ( v3[v6] );
    v3 += v6 + 1;
  }
  v7 = calloc_base(v2 + 1, 8u);
  v8 = v7;
  if ( !v7 )
    goto LABEL_9;
  v10 = v7;
  while ( 1 )
  {
    if ( !*a1 )
    {
      free_base(0);
      return v8;
    }
    v11 = -1;
    do
      ++v11;
    while ( a1[v11] );
    v12 = v11 + 1;
    if ( *a1 != 61 )
      break;
LABEL_17:
    a1 += v12;
  }
  v13 = calloc_base(v12, 2u);
  v14 = v13;
  if ( v13 )
  {
    if ( (unsigned int)sub_14006C410(v13, v12, a1) )
      invoke_watson(0, 0, 0, 0, 0);
    *v10++ = v14;
    free_base(0);
    goto LABEL_17;
  }
  unknown_libname_90(v8);
  free_base(0);
LABEL_9:
  free_base(0);
  return 0;
}

```

## disassembly

```asm
0x140070e00  mov     [rsp+arg_0], rbx
0x140070e05  mov     [rsp+arg_8], rbp
0x140070e0a  mov     [rsp+arg_10], rsi
0x140070e0f  push    rdi
0x140070e10  push    r14
0x140070e12  push    r15
0x140070e14  sub     rsp, 30h
0x140070e18  mov     r14, rcx
0x140070e1b  xor     ebp, ebp
0x140070e1d  mov     ecx, ebp
0x140070e1f  mov     r8, r14
0x140070e22  movzx   edx, word ptr [r14]
0x140070e26  jmp     short loc_140070E51
0x140070e28  cmp     dx, 3Dh ; '='
0x140070e2c  lea     rax, [rcx+1]
0x140070e30  cmovz   rax, rcx
0x140070e34  mov     rcx, rax
0x140070e37  or      rax, 0FFFFFFFFFFFFFFFFh
0x140070e3b  inc     rax
0x140070e3e  cmp     [r8+rax*2], bp
0x140070e43  jnz     short loc_140070E3B
0x140070e45  lea     r8, [r8+rax*2]
0x140070e49  add     r8, 2
0x140070e4d  movzx   edx, word ptr [r8]
0x140070e51  test    dx, dx
0x140070e54  jnz     short loc_140070E28
0x140070e56  inc     rcx; Count
0x140070e59  mov     edx, 8; Size
0x140070e5e  call    _calloc_base
0x140070e63  mov     rbx, rax
0x140070e66  test    rax, rax
0x140070e69  jnz     short loc_140070E76
0x140070e6b  xor     ecx, ecx; Block
0x140070e6d  call    _free_base
0x140070e72  xor     eax, eax
0x140070e74  jmp     short loc_140070EDE
0x140070e76  mov     r15, rbx
0x140070e79  jmp     short loc_140070ECB
0x140070e7b  or      rsi, 0FFFFFFFFFFFFFFFFh
0x140070e7f  inc     rsi
0x140070e82  cmp     [r14+rsi*2], bp
0x140070e87  jnz     short loc_140070E7F
0x140070e89  inc     rsi
0x140070e8c  cmp     ax, 3Dh ; '='
0x140070e90  jz      short loc_140070EC7
0x140070e92  mov     edx, 2; Size
0x140070e97  mov     rcx, rsi; Count
0x140070e9a  call    _calloc_base
0x140070e9f  mov     rdi, rax
0x140070ea2  test    rax, rax
0x140070ea5  jz      short loc_140070EF7
0x140070ea7  mov     r8, r14
0x140070eaa  mov     rdx, rsi
0x140070ead  mov     rcx, rax
0x140070eb0  call    sub_14006C410
0x140070eb5  xor     ecx, ecx; Block
0x140070eb7  test    eax, eax
0x140070eb9  jnz     short loc_140070F0B
0x140070ebb  mov     [r15], rdi
0x140070ebe  add     r15, 8
0x140070ec2  call    _free_base
0x140070ec7  lea     r14, [r14+rsi*2]
0x140070ecb  movzx   eax, word ptr [r14]
0x140070ecf  test    ax, ax
0x140070ed2  jnz     short loc_140070E7B
0x140070ed4  xor     ecx, ecx; Block
0x140070ed6  call    _free_base
0x140070edb  mov     rax, rbx
0x140070ede  mov     rbx, [rsp+48h+arg_0]
0x140070ee3  mov     rbp, [rsp+48h+arg_8]
0x140070ee8  mov     rsi, [rsp+48h+arg_10]
0x140070eed  add     rsp, 30h
0x140070ef1  pop     r15
0x140070ef3  pop     r14
0x140070ef5  pop     rdi
0x140070ef6  retn
0x140070ef7  mov     rcx, rbx; Block
0x140070efa  call    unknown_libname_90; Microsoft VisualC 64bit universal runtime
0x140070eff  xor     ecx, ecx; Block
0x140070f01  call    _free_base
0x140070f06  jmp     loc_140070E6B
0x140070f0b  xor     r9d, r9d; LineNo
0x140070f0e  mov     [rsp+48h+Reserved], rbp; Reserved
0x140070f13  xor     r8d, r8d; FileName
0x140070f16  xor     edx, edx; FunctionName
0x140070f18  call    _invoke_watson
```
