# common_xtox_unsigned___int64_char_

- ea: `0x18001dd00`
- end: `0x18001ddcb`
- name: `common_xtox_unsigned___int64_char_`
- size: `203`
- prototype: ``
- caller_count: `3`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x18001df78`
- `0x18001e04c`
- `0x18001e23c`

## callees

- `0x180007c00`
- `0x180007ee8`
- `0x18001dd00`

## pseudocode

```c
__int64 __fastcall common_xtox_unsigned___int64_char_(
        unsigned __int64 a1,
        char *a2,
        unsigned __int64 a3,
        unsigned int a4,
        char a5)
{
  unsigned __int64 v5; // rbx
  char *v8; // r11
  char *v9; // r8
  unsigned __int64 v10; // rbp
  _BYTE *v11; // rsi
  char *v12; // r9
  unsigned __int64 v13; // rdx
  char v14; // al
  char v16; // cl

  v5 = 0;
  v8 = a2;
  if ( a5 )
  {
    *a2 = 45;
    v8 = a2 + 1;
    v5 = 1;
    a1 = -(__int64)a1;
  }
  v9 = v8;
  v10 = a4;
  do
  {
    v11 = v8 + 1;
    v12 = v8;
    v13 = a1 % v10;
    a1 /= v10;
    v14 = 87;
    if ( (unsigned int)v13 <= 9 )
      v14 = 48;
    ++v5;
    *v8 = v13 + v14;
    if ( !a1 )
      break;
    ++v8;
  }
  while ( v5 < a3 );
  if ( v5 < a3 )
  {
    *v11 = 0;
    do
    {
      v16 = *v12;
      *v12-- = *v9;
      *v9++ = v16;
    }
    while ( v9 < v12 );
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
0x18001dd00  mov     rax, rsp
0x18001dd03  mov     [rax+8], rbx
0x18001dd07  mov     [rax+10h], rbp
0x18001dd0b  mov     [rax+18h], rsi
0x18001dd0f  mov     [rax+20h], rdi
0x18001dd13  push    r14
0x18001dd15  sub     rsp, 20h
0x18001dd19  xor     ebx, ebx
0x18001dd1b  mov     rdi, r8
0x18001dd1e  mov     r10, rdx
0x18001dd21  mov     r11, rdx
0x18001dd24  cmp     [rsp+28h+arg_20], bl
0x18001dd28  jz      short loc_18001DD39
0x18001dd2a  mov     byte ptr [rdx], 2Dh ; '-'
0x18001dd2d  lea     r11, [rdx+1]
0x18001dd31  mov     ebx, 1
0x18001dd36  neg     rcx
0x18001dd39  mov     r8, r11
0x18001dd3c  mov     ebp, r9d
0x18001dd3f  xor     edx, edx
0x18001dd41  lea     rsi, [r11+1]
0x18001dd45  mov     rax, rcx
0x18001dd48  mov     r9, r11
0x18001dd4b  div     rbp
0x18001dd4e  mov     rcx, rax
0x18001dd51  cmp     edx, 9
0x18001dd54  mov     eax, 57h ; 'W'
0x18001dd59  lea     r14d, [rax-27h]
0x18001dd5d  cmovbe  eax, r14d
0x18001dd61  inc     rbx
0x18001dd64  add     al, dl
0x18001dd66  mov     [r11], al
0x18001dd69  test    rcx, rcx
0x18001dd6c  jz      short loc_18001DD76
0x18001dd6e  mov     r11, rsi
0x18001dd71  cmp     rbx, rdi
0x18001dd74  jb      short loc_18001DD3F
0x18001dd76  cmp     rbx, rdi
0x18001dd79  jb      short loc_18001DD94
0x18001dd7b  mov     byte ptr [r10], 0
0x18001dd7f  call    _errno
0x18001dd84  mov     ebx, 22h ; '"'
0x18001dd89  mov     [rax], ebx
0x18001dd8b  call    _invalid_parameter_noinfo
0x18001dd90  mov     eax, ebx
0x18001dd92  jmp     short loc_18001DDB0
0x18001dd94  mov     byte ptr [rsi], 0
0x18001dd97  mov     al, [r8]
0x18001dd9a  mov     cl, [r9]
0x18001dd9d  mov     [r9], al
0x18001dda0  dec     r9
0x18001dda3  mov     [r8], cl
0x18001dda6  inc     r8
0x18001dda9  cmp     r8, r9
0x18001ddac  jb      short loc_18001DD97
0x18001ddae  xor     eax, eax
0x18001ddb0  mov     rbx, [rsp+28h+arg_0]
0x18001ddb5  mov     rbp, [rsp+28h+arg_8]
0x18001ddba  mov     rsi, [rsp+28h+arg_10]
0x18001ddbf  mov     rdi, [rsp+28h+arg_18]
0x18001ddc4  add     rsp, 20h
0x18001ddc8  pop     r14
0x18001ddca  retn
```
