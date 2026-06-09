# parse_command_line<wchar_t>(wchar_t *,wchar_t * *,wchar_t *,unsigned __int64 *,unsigned __int64 *)

- ea: `0x140017d04`
- end: `0x140017ea6`
- name: `??$parse_command_line@_W@@YAXPEA_WPEAPEA_W0PEA_K2@Z`
- size: `418`
- prototype: `__int64 __fastcall(__int16 *, __int16 **, __int16 *, _QWORD *, _QWORD *)`
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x140017f08`

## callees

- `0x140017d04`

## pseudocode

```c
__int64 __fastcall parse_command_line<wchar_t>(__int16 *a1, __int16 **a2, __int16 *a3, _QWORD *a4, _QWORD *a5)
{
  bool v6; // r9
  __int16 *v7; // r10
  __int16 v8; // ax
  bool v9; // di
  __int64 result; // rax
  int v11; // r10d
  unsigned int v12; // eax
  __int16 v13; // ax

  *a5 = 0;
  *a4 = 1;
  if ( a2 )
    *a2++ = a3;
  v6 = 0;
  do
  {
    v7 = a1;
    if ( *a1 == 34 )
    {
      v8 = 34;
      v6 = !v6;
      ++a1;
    }
    else
    {
      ++*a5;
      if ( a3 )
        *a3++ = *a1;
      v8 = *a1++;
      if ( !v8 )
      {
        a1 = v7;
        goto LABEL_15;
      }
    }
  }
  while ( v6 || v8 != 32 && v8 != 9 );
  if ( a3 )
    *(a3 - 1) = 0;
LABEL_15:
  v9 = 0;
  while ( 1 )
  {
    result = (unsigned __int16)*a1;
    if ( !(_WORD)result )
      break;
    while ( (_WORD)result == 32 || (_WORD)result == 9 )
      result = (unsigned __int16)*++a1;
    if ( !(_WORD)result )
      break;
    if ( a2 )
      *a2++ = a3;
    ++*a4;
    while ( 1 )
    {
      v11 = 1;
      v12 = 0;
      while ( *a1 == 92 )
      {
        ++a1;
        ++v12;
      }
      if ( *a1 == 34 )
      {
        if ( (v12 & 1) == 0 )
        {
          if ( v9 && a1[1] == 34 )
          {
            ++a1;
          }
          else
          {
            v11 = 0;
            v9 = !v9;
          }
        }
        v12 >>= 1;
      }
      while ( v12 )
      {
        --v12;
        if ( a3 )
          *a3++ = 92;
        ++*a5;
      }
      v13 = *a1;
      if ( !*a1 || !v9 && (v13 == 32 || v13 == 9) )
        break;
      if ( v11 )
      {
        if ( a3 )
          *a3++ = v13;
        ++*a5;
      }
      ++a1;
    }
    if ( a3 )
      *a3++ = 0;
    ++*a5;
  }
  if ( a2 )
    *a2 = 0;
  ++*a4;
  return result;
}

```

## disassembly

```asm
0x140017d04  mov     rax, rsp
0x140017d07  mov     [rax+8], rbx
0x140017d0b  mov     [rax+10h], rsi
0x140017d0f  mov     [rax+18h], rdi
0x140017d13  mov     [rax+20h], r14
0x140017d17  push    r15
0x140017d19  mov     r11, [rsp+8+arg_20]
0x140017d1e  xor     esi, esi
0x140017d20  mov     rbx, r9
0x140017d23  mov     [r11], rsi
0x140017d26  mov     qword ptr [r9], 1
0x140017d2d  test    rdx, rdx
0x140017d30  jz      short loc_140017D39
0x140017d32  mov     [rdx], r8
0x140017d35  add     rdx, 8
0x140017d39  mov     r9b, sil
0x140017d3c  mov     r15d, 22h ; '"'
0x140017d42  mov     r10, rcx
0x140017d45  cmp     [rcx], r15w
0x140017d49  jnz     short loc_140017D5C
0x140017d4b  test    r9b, r9b
0x140017d4e  movzx   eax, r15w
0x140017d52  setz    r9b
0x140017d56  add     rcx, 2
0x140017d5a  jmp     short loc_140017D7B
0x140017d5c  inc     qword ptr [r11]
0x140017d5f  test    r8, r8
0x140017d62  jz      short loc_140017D6F
0x140017d64  movzx   eax, word ptr [rcx]
0x140017d67  mov     [r8], ax
0x140017d6b  add     r8, 2
0x140017d6f  movzx   eax, word ptr [rcx]
0x140017d72  add     rcx, 2
0x140017d76  test    ax, ax
0x140017d79  jz      short loc_140017D98
0x140017d7b  test    r9b, r9b
0x140017d7e  jnz     short loc_140017D42
0x140017d80  cmp     ax, 20h ; ' '
0x140017d84  jz      short loc_140017D8C
0x140017d86  cmp     ax, 9
0x140017d8a  jnz     short loc_140017D42
0x140017d8c  test    r8, r8
0x140017d8f  jz      short loc_140017D9B
0x140017d91  mov     [r8-2], si
0x140017d96  jmp     short loc_140017D9B
0x140017d98  mov     rcx, r10
0x140017d9b  mov     dil, sil
0x140017d9e  mov     r14d, 5Ch ; '\'
0x140017da4  movzx   eax, word ptr [rcx]
0x140017da7  test    ax, ax
0x140017daa  jz      loc_140017E84
0x140017db0  cmp     ax, 20h ; ' '
0x140017db4  jz      short loc_140017DBC
0x140017db6  cmp     ax, 9
0x140017dba  jnz     short loc_140017DC5
0x140017dbc  add     rcx, 2
0x140017dc0  movzx   eax, word ptr [rcx]
0x140017dc3  jmp     short loc_140017DB0
0x140017dc5  test    ax, ax
0x140017dc8  jz      loc_140017E84
0x140017dce  test    rdx, rdx
0x140017dd1  jz      short loc_140017DDA
0x140017dd3  mov     [rdx], r8
0x140017dd6  add     rdx, 8
0x140017dda  inc     qword ptr [rbx]
0x140017ddd  mov     r10d, 1
0x140017de3  mov     eax, esi
0x140017de5  jmp     short loc_140017DED
0x140017de7  add     rcx, 2
0x140017deb  inc     eax
0x140017ded  movzx   r9d, word ptr [rcx]
0x140017df1  cmp     r9w, r14w
0x140017df5  jz      short loc_140017DE7
0x140017df7  cmp     r9w, r15w
0x140017dfb  jnz     short loc_140017E34
0x140017dfd  test    r10b, al
0x140017e00  jnz     short loc_140017E1E
0x140017e02  test    dil, dil
0x140017e05  jz      short loc_140017E14
0x140017e07  cmp     [rcx+2], r15w
0x140017e0c  jnz     short loc_140017E14
0x140017e0e  add     rcx, 2
0x140017e12  jmp     short loc_140017E1E
0x140017e14  test    dil, dil
0x140017e17  mov     r10d, esi
0x140017e1a  setz    dil
0x140017e1e  shr     eax, 1
0x140017e20  jmp     short loc_140017E34
0x140017e22  dec     eax
0x140017e24  test    r8, r8
0x140017e27  jz      short loc_140017E31
0x140017e29  mov     [r8], r14w
0x140017e2d  add     r8, 2
0x140017e31  inc     qword ptr [r11]
0x140017e34  test    eax, eax
0x140017e36  jnz     short loc_140017E22
0x140017e38  movzx   eax, word ptr [rcx]
0x140017e3b  test    ax, ax
0x140017e3e  jz      short loc_140017E6F
0x140017e40  test    dil, dil
0x140017e43  jnz     short loc_140017E51
0x140017e45  cmp     ax, 20h ; ' '
0x140017e49  jz      short loc_140017E6F
0x140017e4b  cmp     ax, 9
0x140017e4f  jz      short loc_140017E6F
0x140017e51  test    r10d, r10d
0x140017e54  jz      short loc_140017E66
0x140017e56  test    r8, r8
0x140017e59  jz      short loc_140017E63
0x140017e5b  mov     [r8], ax
0x140017e5f  add     r8, 2
0x140017e63  inc     qword ptr [r11]
0x140017e66  add     rcx, 2
0x140017e6a  jmp     loc_140017DDD
0x140017e6f  test    r8, r8
0x140017e72  jz      short loc_140017E7C
0x140017e74  mov     [r8], si
0x140017e78  add     r8, 2
0x140017e7c  inc     qword ptr [r11]
0x140017e7f  jmp     loc_140017DA4
0x140017e84  test    rdx, rdx
0x140017e87  jz      short loc_140017E8C
0x140017e89  mov     [rdx], rsi
0x140017e8c  inc     qword ptr [rbx]
0x140017e8f  mov     rbx, [rsp+8+arg_0]
0x140017e94  mov     rsi, [rsp+8+arg_8]
0x140017e99  mov     rdi, [rsp+8+arg_10]
0x140017e9e  mov     r14, [rsp+8+arg_18]
0x140017ea3  pop     r15
0x140017ea5  retn
```
