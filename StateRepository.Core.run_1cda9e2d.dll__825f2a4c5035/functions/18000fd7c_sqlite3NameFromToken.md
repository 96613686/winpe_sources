# sqlite3NameFromToken

- ea: `0x18000fd7c`
- end: `0x18000fe2c`
- name: `sqlite3NameFromToken`
- size: `176`
- prototype: ``
- caller_count: `18`
- callee_count: `3`
- tags: ``

## callers

- `0x180003128`
- `0x18000ded0`
- `0x1800137fc`
- `0x180015168`
- `0x180017fac`
- `0x180031b38`
- `0x180050420`
- `0x1800551f0`
- `0x180058e44`
- `0x18005c8b0`
- `0x18005f234`
- `0x1800644e4`
- `0x180080120`
- `0x1800809a0`
- `0x180080c08`
- `0x180086c1c`
- `0x180087564`
- `0x1800896b8`

## callees

- `0x18000fd7c`
- `0x180010390`
- `0x180099814`

## pseudocode

```c
char *__fastcall sqlite3NameFromToken(__int64 a1, __int64 a2)
{
  const void *v2; // rsi
  __int64 v3; // rdi
  char *v4; // rax
  char *v5; // rbx
  __int64 v6; // rax
  char v8; // dl
  int v9; // r10d
  int i; // ecx
  char v11; // r8

  if ( !a2 )
    return 0;
  v2 = *(const void **)a2;
  if ( !*(_QWORD *)a2 )
    return 0;
  v3 = *(unsigned int *)(a2 + 8);
  v4 = (char *)sqlite3DbMallocRawNN(a1, v3 + 1);
  v5 = v4;
  if ( v4 )
  {
    memcpy_0(v4, v2, (unsigned int)v3);
    v5[v3] = 0;
    v6 = (unsigned __int8)*v5;
    if ( (char)byte_18009E630[v6] < 0 )
    {
      v8 = *v5;
      if ( (_BYTE)v6 == 91 )
        v8 = 93;
      v9 = 0;
      for ( i = 1; ; ++i )
      {
        v11 = v5[i];
        if ( v11 == v8 )
        {
          if ( v5[i + 1] != v8 )
          {
            v5[v9] = 0;
            return v5;
          }
          ++i;
          v11 = v8;
        }
        v5[v9++] = v11;
      }
    }
  }
  return v5;
}

```

## disassembly

```asm
0x18000fd7c  mov     [rsp+arg_0], rbx
0x18000fd81  mov     [rsp+arg_8], rsi
0x18000fd86  push    rdi
0x18000fd87  sub     rsp, 20h
0x18000fd8b  test    rdx, rdx
0x18000fd8e  jz      short loc_18000FDE1
0x18000fd90  mov     rsi, [rdx]
0x18000fd93  test    rsi, rsi
0x18000fd96  jz      short loc_18000FDE1
0x18000fd98  mov     edi, [rdx+8]
0x18000fd9b  lea     rdx, [rdi+1]
0x18000fd9f  call    sqlite3DbMallocRawNN
0x18000fda4  mov     rbx, rax
0x18000fda7  test    rax, rax
0x18000fdaa  jz      short loc_18000FDCE
0x18000fdac  mov     r8d, edi; Size
0x18000fdaf  mov     rdx, rsi; Src
0x18000fdb2  mov     rcx, rax; void *
0x18000fdb5  call    memcpy_0
0x18000fdba  mov     byte ptr [rdi+rbx], 0
0x18000fdbe  lea     rcx, byte_18009E630
0x18000fdc5  movzx   eax, byte ptr [rbx]
0x18000fdc8  cmp     byte ptr [rax+rcx], 0
0x18000fdcc  jl      short loc_18000FDE5
0x18000fdce  mov     rsi, [rsp+28h+arg_8]
0x18000fdd3  mov     rax, rbx
0x18000fdd6  mov     rbx, [rsp+28h+arg_0]
0x18000fddb  add     rsp, 20h
0x18000fddf  pop     rdi
0x18000fde0  retn
0x18000fde1  xor     ebx, ebx
0x18000fde3  jmp     short loc_18000FDCE
0x18000fde5  mov     ecx, 5Dh ; ']'
0x18000fdea  cmp     al, 5Bh ; '['
0x18000fdec  mov     edx, eax
0x18000fdee  cmovz   edx, ecx
0x18000fdf1  xor     r10d, r10d
0x18000fdf4  lea     r11d, [rcx-5Ch]
0x18000fdf8  mov     ecx, r11d
0x18000fdfb  movsxd  rax, ecx
0x18000fdfe  movsxd  r9, r10d
0x18000fe01  mov     r8b, [rax+rbx]
0x18000fe05  cmp     r8b, dl
0x18000fe08  jnz     short loc_18000FE20
0x18000fe0a  movsxd  rax, ecx
0x18000fe0d  cmp     [rax+rbx+1], dl
0x18000fe11  jz      short loc_18000FE1A
0x18000fe13  mov     byte ptr [r9+rbx], 0
0x18000fe18  jmp     short loc_18000FDCE
0x18000fe1a  add     ecx, r11d
0x18000fe1d  mov     r8b, dl
0x18000fe20  add     ecx, r11d
0x18000fe23  mov     [r9+rbx], r8b
0x18000fe27  add     r10d, r11d
0x18000fe2a  jmp     short loc_18000FDFB
```
