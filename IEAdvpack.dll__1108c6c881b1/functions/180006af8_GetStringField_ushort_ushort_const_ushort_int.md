# GetStringField(ushort * *,ushort const *,ushort,int)

- ea: `0x180006af8`
- end: `0x180006c78`
- name: `?GetStringField@@YAPEAGPEAPEAGPEBGGH@Z`
- size: `384`
- prototype: `unsigned __int16 *__fastcall(unsigned __int16 **, unsigned __int16 *, __int16, int)`
- caller_count: `11`
- callee_count: `4`
- tags: ``

## callers

- `0x180006e54`
- `0x180008330`
- `0x18000931c`
- `0x180009478`
- `0x1800096f0`
- `0x18000a0c0`
- `0x18000a428`
- `0x18000b1d0`
- `0x18000b8f0`
- `0x18000d7ac`
- `0x1800104c0`

## callees

- `0x180006af8`
- `0x18000861c`
- `0x18000a8bc`
- `0x18001b942`

## import_xrefs

- `USER32!CharNextW` at `0x180006b4b`
- `USER32!CharNextW` at `0x180006bb5`
- `USER32!CharNextW` at `0x180006c21`
- `USER32!CharNextW` at `0x180006b4b`
- `USER32!CharNextW` at `0x180006bb5`
- `USER32!CharNextW` at `0x180006c21`

## pseudocode

```c
unsigned __int16 *__fastcall GetStringField(unsigned __int16 **a1, unsigned __int16 *a2, __int16 a3, int a4)
{
  WCHAR *v4; // rbx
  __int16 v6; // ax
  WCHAR v9; // di
  BOOL v10; // ebp
  WCHAR v11; // r15
  unsigned __int16 *v12; // r14
  const WCHAR *v13; // rax
  const WCHAR *v14; // rsi
  __int64 v15; // r8
  LPWSTR v16; // rax
  __int64 v17; // r8
  const void *v18; // rdx
  WCHAR *v19; // rcx
  WCHAR v20; // r9
  LPWSTR v21; // rax
  unsigned __int16 *v22; // rbx
  unsigned __int16 *v23; // [rsp+68h] [rbp+10h]

  v23 = a2;
  v4 = *a1;
  v6 = a3;
  if ( !*a1 )
    return 0;
  v9 = *v4;
  v10 = 0;
  v11 = 0;
  v12 = *a1;
  while ( 1 )
  {
    do
    {
      if ( v9 != v6 )
        goto LABEL_20;
      v13 = CharNextW(v4);
      v14 = v13;
      if ( v11 )
      {
        if ( v11 == v9 )
        {
          if ( *v13 == v9 )
          {
            v16 = CharNextW(v13);
            v17 = -1;
            do
              ++v17;
            while ( v16[v17] );
            v18 = v16;
            v19 = (WCHAR *)v14;
          }
          else
          {
            v11 = 0;
            v17 = -1;
            v10 = !v10;
            do
              ++v17;
            while ( v13[v17] );
            v18 = v13;
            v19 = v4;
          }
          memmove_0(v19, v18, 2 * v17 + 2);
        }
        break;
      }
      v11 = v9;
      v15 = -1;
      v10 = !v10;
      do
        ++v15;
      while ( v13[v15] );
      memmove_0(v4, v13, 2 * v15 + 2);
      v9 = *v4;
      v6 = a3;
      a2 = v23;
    }
    while ( *v4 == v11 );
    a2 = v23;
LABEL_20:
    if ( !*v4 )
      break;
    if ( !v10 && (unsigned int)IsSeparator(*v4, a2) )
    {
      *v4 = v20;
      v22 = v4 + 1;
      goto LABEL_26;
    }
    v21 = CharNextW(v4);
    a2 = v23;
    v4 = v21;
    v9 = *v21;
    v6 = a3;
  }
  v22 = 0;
LABEL_26:
  if ( a4 )
    v12 = StripWhitespace(v12);
  *a1 = v22;
  return v12;
}

```

## disassembly

```asm
0x180006af8  mov     [rsp+arg_0], rbx
0x180006afd  mov     [rsp+arg_10], r8w
0x180006b03  mov     [rsp+arg_8], rdx
0x180006b08  push    rbp
0x180006b09  push    rsi
0x180006b0a  push    rdi
0x180006b0b  push    r12
0x180006b0d  push    r13
0x180006b0f  push    r14
0x180006b11  push    r15
0x180006b13  sub     rsp, 20h
0x180006b17  mov     rbx, [rcx]
0x180006b1a  mov     r13d, r9d
0x180006b1d  xor     r9d, r9d
0x180006b20  movzx   eax, r8w
0x180006b24  mov     r12, rcx
0x180006b27  test    rbx, rbx
0x180006b2a  jnz     short loc_180006B33
0x180006b2c  xor     eax, eax
0x180006b2e  jmp     loc_180006C63
0x180006b33  movzx   edi, word ptr [rbx]
0x180006b36  mov     ebp, r9d
0x180006b39  mov     r15d, r9d
0x180006b3c  mov     r14, rbx
0x180006b3f  cmp     di, ax
0x180006b42  jnz     loc_180006C09
0x180006b48  mov     rcx, rbx; lpsz
0x180006b4b  call    cs:__imp_CharNextW
0x180006b51  xor     r9d, r9d
0x180006b54  mov     rsi, rax
0x180006b57  test    r15w, r15w
0x180006b5b  jnz     short loc_180006BA7
0x180006b5d  test    ebp, ebp
0x180006b5f  mov     ecx, r9d
0x180006b62  movzx   r15d, di
0x180006b66  setz    cl
0x180006b69  or      r8, 0FFFFFFFFFFFFFFFFh
0x180006b6d  mov     ebp, ecx
0x180006b6f  inc     r8
0x180006b72  cmp     [rax+r8*2], r9w
0x180006b77  jnz     short loc_180006B6F
0x180006b79  lea     r8, ds:2[r8*2]; Size
0x180006b81  mov     rdx, rsi; Src
0x180006b84  mov     rcx, rbx; void *
0x180006b87  call    memmove_0
0x180006b8c  movzx   edi, word ptr [rbx]
0x180006b8f  mov     r9d, 0
0x180006b95  movzx   eax, [rsp+58h+arg_10]
0x180006b9a  mov     rdx, [rsp+58h+arg_8]
0x180006b9f  cmp     di, r15w
0x180006ba3  jz      short loc_180006B3F
0x180006ba5  jmp     short loc_180006C04
0x180006ba7  cmp     r15w, di
0x180006bab  jnz     short loc_180006C04
0x180006bad  cmp     [rax], di
0x180006bb0  jnz     short loc_180006BD3
0x180006bb2  mov     rcx, rsi; lpsz
0x180006bb5  call    cs:__imp_CharNextW
0x180006bbb  or      r8, 0FFFFFFFFFFFFFFFFh
0x180006bbf  xor     ecx, ecx
0x180006bc1  inc     r8
0x180006bc4  cmp     [rax+r8*2], cx
0x180006bc9  jnz     short loc_180006BC1
0x180006bcb  mov     rdx, rax
0x180006bce  mov     rcx, rsi
0x180006bd1  jmp     short loc_180006BF4
0x180006bd3  test    ebp, ebp
0x180006bd5  mov     eax, r9d
0x180006bd8  mov     r15d, r9d
0x180006bdb  setz    al
0x180006bde  or      r8, 0FFFFFFFFFFFFFFFFh
0x180006be2  mov     ebp, eax
0x180006be4  inc     r8
0x180006be7  cmp     [rsi+r8*2], r9w
0x180006bec  jnz     short loc_180006BE4
0x180006bee  mov     rdx, rsi; Src
0x180006bf1  mov     rcx, rbx; void *
0x180006bf4  lea     r8, ds:2[r8*2]; Size
0x180006bfc  call    memmove_0
0x180006c01  xor     r9d, r9d
0x180006c04  mov     rdx, [rsp+58h+arg_8]; unsigned __int16 *
0x180006c09  movzx   ecx, word ptr [rbx]; unsigned __int16
0x180006c0c  test    cx, cx
0x180006c0f  jz      short loc_180006C49
0x180006c11  test    ebp, ebp
0x180006c13  jnz     short loc_180006C1E
0x180006c15  call    ?IsSeparator@@YAHGPEBG@Z; IsSeparator(ushort,ushort const *)
0x180006c1a  test    eax, eax
0x180006c1c  jnz     short loc_180006C3F
0x180006c1e  mov     rcx, rbx; lpsz
0x180006c21  call    cs:__imp_CharNextW
0x180006c27  mov     rdx, [rsp+58h+arg_8]
0x180006c2c  xor     r9d, r9d
0x180006c2f  mov     rbx, rax
0x180006c32  movzx   edi, word ptr [rax]
0x180006c35  movzx   eax, [rsp+58h+arg_10]
0x180006c3a  jmp     loc_180006B3F
0x180006c3f  mov     [rbx], r9w
0x180006c43  add     rbx, 2
0x180006c47  jmp     short loc_180006C4C
0x180006c49  mov     rbx, r9
0x180006c4c  test    r13d, r13d
0x180006c4f  jz      short loc_180006C5C
0x180006c51  mov     rcx, r14; unsigned __int16 *
0x180006c54  call    ?StripWhitespace@@YAPEAGPEAG@Z; StripWhitespace(ushort *)
0x180006c59  mov     r14, rax
0x180006c5c  mov     [r12], rbx
0x180006c60  mov     rax, r14
0x180006c63  mov     rbx, [rsp+58h+arg_0]
0x180006c68  add     rsp, 20h
0x180006c6c  pop     r15
0x180006c6e  pop     r14
0x180006c70  pop     r13
0x180006c72  pop     r12
0x180006c74  pop     rdi
0x180006c75  pop     rsi
0x180006c76  pop     rbp
0x180006c77  retn
```
