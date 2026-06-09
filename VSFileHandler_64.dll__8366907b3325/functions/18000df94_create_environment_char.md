# create_environment_char_

- ea: `0x18000df94`
- end: `0x18000e09a`
- name: `create_environment_char_`
- size: `262`
- prototype: `__int64 __fastcall(char *Source)`
- caller_count: `1`
- callee_count: `6`
- tags: ``

## callers

- `0x18000df28`

## callees

- `0x18000bebc`
- `0x18000df94`
- `0x18000e09c`
- `0x18000e820`
- `0x18000fe3c`
- `0x1800120b0`

## pseudocode

```c
void *__fastcall create_environment_char_(char *Source)
{
  void *v2; // rsi
  __int64 v3; // rcx
  char *v4; // r8
  char i; // dl
  __int64 v6; // rax
  __int64 v7; // rax
  void *v8; // rax
  void *v9; // rbx
  char **v10; // r15
  __int64 v11; // rbp
  size_t v12; // rbp
  char *v13; // rax
  char *v14; // rdi

  v2 = 0;
  v3 = 0;
  v4 = Source;
  for ( i = *Source; i; i = *v4 )
  {
    v6 = v3 + 1;
    if ( i == 61 )
      v6 = v3;
    v3 = v6;
    v7 = -1;
    do
      ++v7;
    while ( v4[v7] );
    v4 += v7 + 1;
  }
  v8 = calloc_base(v3 + 1, 8u);
  v9 = v8;
  if ( v8 )
  {
    v10 = (char **)v8;
    while ( *Source )
    {
      v11 = -1;
      do
        ++v11;
      while ( Source[v11] );
      v12 = v11 + 1;
      if ( *Source != 61 )
      {
        v13 = (char *)calloc_base(v12, 1u);
        v14 = v13;
        if ( !v13 )
        {
          free_environment_wchar_t_(v9);
          free_base(0);
          goto LABEL_20;
        }
        if ( strcpy_s(v13, v12, Source) )
          invoke_watson(0, 0, 0, 0, 0);
        *v10++ = v14;
        free_base(0);
      }
      Source += v12;
    }
    v2 = v9;
  }
LABEL_20:
  free_base(0);
  return v2;
}

```

## disassembly

```asm
0x18000df94  mov     [rsp+arg_0], rbx
0x18000df99  mov     [rsp+arg_8], rbp
0x18000df9e  mov     [rsp+arg_10], rsi
0x18000dfa3  push    rdi
0x18000dfa4  push    r14
0x18000dfa6  push    r15
0x18000dfa8  sub     rsp, 30h
0x18000dfac  mov     r14, rcx
0x18000dfaf  xor     esi, esi
0x18000dfb1  mov     ecx, esi
0x18000dfb3  mov     r8, r14
0x18000dfb6  mov     dl, [r14]
0x18000dfb9  jmp     short loc_18000DFDF
0x18000dfbb  cmp     dl, 3Dh ; '='
0x18000dfbe  lea     rax, [rcx+1]
0x18000dfc2  cmovz   rax, rcx
0x18000dfc6  mov     rcx, rax
0x18000dfc9  or      rax, 0FFFFFFFFFFFFFFFFh
0x18000dfcd  inc     rax
0x18000dfd0  cmp     [r8+rax], sil
0x18000dfd4  jnz     short loc_18000DFCD
0x18000dfd6  inc     r8
0x18000dfd9  add     r8, rax
0x18000dfdc  mov     dl, [r8]
0x18000dfdf  test    dl, dl
0x18000dfe1  jnz     short loc_18000DFBB
0x18000dfe3  inc     rcx; Count
0x18000dfe6  mov     edx, 8; Size
0x18000dfeb  call    _calloc_base
0x18000dff0  mov     rbx, rax
0x18000dff3  test    rax, rax
0x18000dff6  jz      short loc_18000E064
0x18000dff8  mov     r15, rax
0x18000dffb  mov     al, [r14]
0x18000dffe  test    al, al
0x18000e000  jz      short loc_18000E061
0x18000e002  or      rbp, 0FFFFFFFFFFFFFFFFh
0x18000e006  inc     rbp
0x18000e009  cmp     [r14+rbp], sil
0x18000e00d  jnz     short loc_18000E006
0x18000e00f  inc     rbp
0x18000e012  cmp     al, 3Dh ; '='
0x18000e014  jz      short loc_18000E04B
0x18000e016  mov     edx, 1; Size
0x18000e01b  mov     rcx, rbp; Count
0x18000e01e  call    _calloc_base
0x18000e023  mov     rdi, rax
0x18000e026  test    rax, rax
0x18000e029  jz      short loc_18000E050
0x18000e02b  mov     r8, r14; Source
0x18000e02e  mov     rdx, rbp; SizeInBytes
0x18000e031  mov     rcx, rax; Destination
0x18000e034  call    strcpy_s
0x18000e039  xor     ecx, ecx; Expression
0x18000e03b  test    eax, eax
0x18000e03d  jnz     short loc_18000E087
0x18000e03f  mov     [r15], rdi
0x18000e042  add     r15, 8
0x18000e046  call    _free_base
0x18000e04b  add     r14, rbp
0x18000e04e  jmp     short loc_18000DFFB
0x18000e050  mov     rcx, rbx; Block
0x18000e053  call    free_environment_wchar_t_
0x18000e058  xor     ecx, ecx; Block
0x18000e05a  call    _free_base
0x18000e05f  jmp     short loc_18000E064
0x18000e061  mov     rsi, rbx
0x18000e064  xor     ecx, ecx; Block
0x18000e066  call    _free_base
0x18000e06b  mov     rbx, [rsp+48h+arg_0]
0x18000e070  mov     rax, rsi
0x18000e073  mov     rsi, [rsp+48h+arg_10]
0x18000e078  mov     rbp, [rsp+48h+arg_8]
0x18000e07d  add     rsp, 30h
0x18000e081  pop     r15
0x18000e083  pop     r14
0x18000e085  pop     rdi
0x18000e086  retn
0x18000e087  xor     r9d, r9d; LineNo
0x18000e08a  mov     [rsp+48h+Reserved], rsi; Reserved
0x18000e08f  xor     r8d, r8d; FileName
0x18000e092  xor     edx, edx; FunctionName
0x18000e094  call    _invoke_watson
```
