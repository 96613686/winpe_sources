# common_xtox_unsigned___int64_char_

- ea: `0x18001d5a0`
- end: `0x18001d66b`
- name: `common_xtox_unsigned___int64_char_`
- size: `203`
- prototype: ``
- caller_count: `3`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x18001d818`
- `0x18001d8ec`
- `0x18001dadc`

## callees

- `0x1800074a0`
- `0x180007788`
- `0x18001d5a0`

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
0x18001d5a0  mov     rax, rsp
0x18001d5a3  mov     [rax+8], rbx
0x18001d5a7  mov     [rax+10h], rbp
0x18001d5ab  mov     [rax+18h], rsi
0x18001d5af  mov     [rax+20h], rdi
0x18001d5b3  push    r14
0x18001d5b5  sub     rsp, 20h
0x18001d5b9  xor     ebx, ebx
0x18001d5bb  mov     rdi, r8
0x18001d5be  mov     r10, rdx
0x18001d5c1  mov     r11, rdx
0x18001d5c4  cmp     [rsp+28h+arg_20], bl
0x18001d5c8  jz      short loc_18001D5D9
0x18001d5ca  mov     byte ptr [rdx], 2Dh ; '-'
0x18001d5cd  lea     r11, [rdx+1]
0x18001d5d1  mov     ebx, 1
0x18001d5d6  neg     rcx
0x18001d5d9  mov     r8, r11
0x18001d5dc  mov     ebp, r9d
0x18001d5df  xor     edx, edx
0x18001d5e1  lea     rsi, [r11+1]
0x18001d5e5  mov     rax, rcx
0x18001d5e8  mov     r9, r11
0x18001d5eb  div     rbp
0x18001d5ee  mov     rcx, rax
0x18001d5f1  cmp     edx, 9
0x18001d5f4  mov     eax, 57h ; 'W'
0x18001d5f9  lea     r14d, [rax-27h]
0x18001d5fd  cmovbe  eax, r14d
0x18001d601  inc     rbx
0x18001d604  add     al, dl
0x18001d606  mov     [r11], al
0x18001d609  test    rcx, rcx
0x18001d60c  jz      short loc_18001D616
0x18001d60e  mov     r11, rsi
0x18001d611  cmp     rbx, rdi
0x18001d614  jb      short loc_18001D5DF
0x18001d616  cmp     rbx, rdi
0x18001d619  jb      short loc_18001D634
0x18001d61b  mov     byte ptr [r10], 0
0x18001d61f  call    _errno
0x18001d624  mov     ebx, 22h ; '"'
0x18001d629  mov     [rax], ebx
0x18001d62b  call    _invalid_parameter_noinfo
0x18001d630  mov     eax, ebx
0x18001d632  jmp     short loc_18001D650
0x18001d634  mov     byte ptr [rsi], 0
0x18001d637  mov     al, [r8]
0x18001d63a  mov     cl, [r9]
0x18001d63d  mov     [r9], al
0x18001d640  dec     r9
0x18001d643  mov     [r8], cl
0x18001d646  inc     r8
0x18001d649  cmp     r8, r9
0x18001d64c  jb      short loc_18001D637
0x18001d64e  xor     eax, eax
0x18001d650  mov     rbx, [rsp+28h+arg_0]
0x18001d655  mov     rbp, [rsp+28h+arg_8]
0x18001d65a  mov     rsi, [rsp+28h+arg_10]
0x18001d65f  mov     rdi, [rsp+28h+arg_18]
0x18001d664  add     rsp, 20h
0x18001d668  pop     r14
0x18001d66a  retn
```
