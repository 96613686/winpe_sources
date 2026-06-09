# common_xtox_unsigned_long_char_

- ea: `0x18001d404`
- end: `0x18001d4ca`
- name: `common_xtox_unsigned_long_char_`
- size: `198`
- prototype: ``
- caller_count: `4`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x18001d744`
- `0x18001d99c`
- `0x18001da3c`
- `0x18001db4c`

## callees

- `0x1800074a0`
- `0x180007788`
- `0x18001d404`

## pseudocode

```c
__int64 __fastcall common_xtox_unsigned_long_char_(
        unsigned int a1,
        char *a2,
        unsigned __int64 a3,
        unsigned int a4,
        char a5)
{
  unsigned __int64 v5; // rbx
  char *v9; // r11
  char *v10; // r8
  _BYTE *v11; // rsi
  char *v12; // r9
  unsigned int v13; // edx
  char v14; // al
  char v16; // cl

  v5 = 0;
  v9 = a2;
  if ( a5 )
  {
    *a2 = 45;
    v9 = a2 + 1;
    v5 = 1;
    a1 = -a1;
  }
  v10 = v9;
  do
  {
    v11 = v9 + 1;
    v12 = v9;
    v13 = a1 % a4;
    a1 /= a4;
    v14 = 87;
    if ( v13 <= 9 )
      v14 = 48;
    ++v5;
    *v9 = v13 + v14;
    if ( !a1 )
      break;
    ++v9;
  }
  while ( v5 < a3 );
  if ( v5 < a3 )
  {
    *v11 = 0;
    do
    {
      v16 = *v12;
      *v12-- = *v10;
      *v10++ = v16;
    }
    while ( v10 < v12 );
    return 0;
  }
  else
  {
    *a2 = 0;
    *errno() = 34;
    invalid_parameter_noinfo();
    return 34;
  }
}

```

## disassembly

```asm
0x18001d404  mov     rax, rsp
0x18001d407  mov     [rax+8], rbx
0x18001d40b  mov     [rax+10h], rbp
0x18001d40f  mov     [rax+18h], rsi
0x18001d413  mov     [rax+20h], rdi
0x18001d417  push    r14
0x18001d419  sub     rsp, 20h
0x18001d41d  xor     ebx, ebx
0x18001d41f  mov     ebp, r9d
0x18001d422  mov     rdi, r8
0x18001d425  mov     r10, rdx
0x18001d428  mov     r11, rdx
0x18001d42b  cmp     [rsp+28h+arg_20], bl
0x18001d42f  jz      short loc_18001D43F
0x18001d431  mov     byte ptr [rdx], 2Dh ; '-'
0x18001d434  lea     r11, [rdx+1]
0x18001d438  mov     ebx, 1
0x18001d43d  neg     ecx
0x18001d43f  mov     r8, r11
0x18001d442  xor     edx, edx
0x18001d444  lea     rsi, [r11+1]
0x18001d448  mov     eax, ecx
0x18001d44a  mov     r9, r11
0x18001d44d  div     ebp
0x18001d44f  mov     ecx, eax
0x18001d451  cmp     edx, 9
0x18001d454  mov     eax, 57h ; 'W'
0x18001d459  lea     r14d, [rax-27h]
0x18001d45d  cmovbe  eax, r14d
0x18001d461  inc     rbx
0x18001d464  add     al, dl
0x18001d466  mov     [r11], al
0x18001d469  test    ecx, ecx
0x18001d46b  jz      short loc_18001D475
0x18001d46d  mov     r11, rsi
0x18001d470  cmp     rbx, rdi
0x18001d473  jb      short loc_18001D442
0x18001d475  cmp     rbx, rdi
0x18001d478  jb      short loc_18001D493
0x18001d47a  mov     byte ptr [r10], 0
0x18001d47e  call    _errno
0x18001d483  mov     ebx, 22h ; '"'
0x18001d488  mov     [rax], ebx
0x18001d48a  call    _invalid_parameter_noinfo
0x18001d48f  mov     eax, ebx
0x18001d491  jmp     short loc_18001D4AF
0x18001d493  mov     byte ptr [rsi], 0
0x18001d496  mov     al, [r8]
0x18001d499  mov     cl, [r9]
0x18001d49c  mov     [r9], al
0x18001d49f  dec     r9
0x18001d4a2  mov     [r8], cl
0x18001d4a5  inc     r8
0x18001d4a8  cmp     r8, r9
0x18001d4ab  jb      short loc_18001D496
0x18001d4ad  xor     eax, eax
0x18001d4af  mov     rbx, [rsp+28h+arg_0]
0x18001d4b4  mov     rbp, [rsp+28h+arg_8]
0x18001d4b9  mov     rsi, [rsp+28h+arg_10]
0x18001d4be  mov     rdi, [rsp+28h+arg_18]
0x18001d4c3  add     rsp, 20h
0x18001d4c7  pop     r14
0x18001d4c9  retn
```
