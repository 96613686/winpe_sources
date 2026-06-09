# common_xtox_unsigned_long_char_

- ea: `0x18001db64`
- end: `0x18001dc2a`
- name: `common_xtox_unsigned_long_char_`
- size: `198`
- prototype: ``
- caller_count: `4`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x18001dea4`
- `0x18001e0fc`
- `0x18001e19c`
- `0x18001e2ac`

## callees

- `0x180007c00`
- `0x180007ee8`
- `0x18001db64`

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
0x18001db64  mov     rax, rsp
0x18001db67  mov     [rax+8], rbx
0x18001db6b  mov     [rax+10h], rbp
0x18001db6f  mov     [rax+18h], rsi
0x18001db73  mov     [rax+20h], rdi
0x18001db77  push    r14
0x18001db79  sub     rsp, 20h
0x18001db7d  xor     ebx, ebx
0x18001db7f  mov     ebp, r9d
0x18001db82  mov     rdi, r8
0x18001db85  mov     r10, rdx
0x18001db88  mov     r11, rdx
0x18001db8b  cmp     [rsp+28h+arg_20], bl
0x18001db8f  jz      short loc_18001DB9F
0x18001db91  mov     byte ptr [rdx], 2Dh ; '-'
0x18001db94  lea     r11, [rdx+1]
0x18001db98  mov     ebx, 1
0x18001db9d  neg     ecx
0x18001db9f  mov     r8, r11
0x18001dba2  xor     edx, edx
0x18001dba4  lea     rsi, [r11+1]
0x18001dba8  mov     eax, ecx
0x18001dbaa  mov     r9, r11
0x18001dbad  div     ebp
0x18001dbaf  mov     ecx, eax
0x18001dbb1  cmp     edx, 9
0x18001dbb4  mov     eax, 57h ; 'W'
0x18001dbb9  lea     r14d, [rax-27h]
0x18001dbbd  cmovbe  eax, r14d
0x18001dbc1  inc     rbx
0x18001dbc4  add     al, dl
0x18001dbc6  mov     [r11], al
0x18001dbc9  test    ecx, ecx
0x18001dbcb  jz      short loc_18001DBD5
0x18001dbcd  mov     r11, rsi
0x18001dbd0  cmp     rbx, rdi
0x18001dbd3  jb      short loc_18001DBA2
0x18001dbd5  cmp     rbx, rdi
0x18001dbd8  jb      short loc_18001DBF3
0x18001dbda  mov     byte ptr [r10], 0
0x18001dbde  call    _errno
0x18001dbe3  mov     ebx, 22h ; '"'
0x18001dbe8  mov     [rax], ebx
0x18001dbea  call    _invalid_parameter_noinfo
0x18001dbef  mov     eax, ebx
0x18001dbf1  jmp     short loc_18001DC0F
0x18001dbf3  mov     byte ptr [rsi], 0
0x18001dbf6  mov     al, [r8]
0x18001dbf9  mov     cl, [r9]
0x18001dbfc  mov     [r9], al
0x18001dbff  dec     r9
0x18001dc02  mov     [r8], cl
0x18001dc05  inc     r8
0x18001dc08  cmp     r8, r9
0x18001dc0b  jb      short loc_18001DBF6
0x18001dc0d  xor     eax, eax
0x18001dc0f  mov     rbx, [rsp+28h+arg_0]
0x18001dc14  mov     rbp, [rsp+28h+arg_8]
0x18001dc19  mov     rsi, [rsp+28h+arg_10]
0x18001dc1e  mov     rdi, [rsp+28h+arg_18]
0x18001dc23  add     rsp, 20h
0x18001dc27  pop     r14
0x18001dc29  retn
```
