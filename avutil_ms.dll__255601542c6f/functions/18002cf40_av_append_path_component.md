# av_append_path_component

- ea: `0x18002cf40`
- end: `0x18002d01d`
- name: `av_append_path_component`
- size: `221`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `broker_com_uri`

## callees

- `0x18002cf40`
- `0x18002d8b0`
- `0x180044a20`
- `0x180044f00`
- `0x180078c1a`

## pseudocode

```c
__int64 __fastcall av_append_path_component(const char *a1, const char *a2)
{
  const char *v3; // rbp
  size_t v5; // rbx
  size_t v6; // rax
  size_t v7; // r14
  _BYTE *v8; // rax
  _BYTE *v9; // rdi

  v3 = a1;
  if ( !a1 )
  {
    a1 = a2;
    return av_strdup(a1);
  }
  if ( !a2 )
    return av_strdup(a1);
  v5 = strlen(a1);
  v6 = strlen(a2);
  v7 = v6;
  if ( v5 > ~v6 || v6 + v5 > 0xFFFFFFFFFFFFFFFDuLL )
    return 0;
  _mm_lfence();
  v8 = av_malloc(v6 + v5 + 2);
  v9 = v8;
  if ( v8 )
  {
    if ( v5 )
    {
      av_strlcpy(v8, v3, v5 + 1);
      if ( v7 )
      {
        if ( v9[v5 - 1] == 47 )
        {
          if ( *a2 == 47 )
            --v5;
        }
        else if ( *a2 != 47 )
        {
          v9[v5++] = 47;
        }
      }
    }
    av_strlcpy(&v9[v5], a2, v7 + 1);
    v9[v7 + v5] = 0;
  }
  return (__int64)v9;
}

```

## disassembly

```asm
0x18002cf40  mov     [rsp+arg_0], rbx
0x18002cf45  mov     [rsp+arg_8], rbp
0x18002cf4a  mov     [rsp+arg_10], rsi
0x18002cf4f  push    rdi
0x18002cf50  push    r14
0x18002cf52  push    r15
0x18002cf54  sub     rsp, 20h
0x18002cf58  mov     rsi, rdx
0x18002cf5b  mov     rbp, rcx
0x18002cf5e  test    rcx, rcx
0x18002cf61  jnz     short loc_18002CF70
0x18002cf63  mov     rcx, rdx
0x18002cf66  call    av_strdup
0x18002cf6b  jmp     loc_18002D004
0x18002cf70  test    rsi, rsi
0x18002cf73  jz      short loc_18002CF66
0x18002cf75  call    strlen
0x18002cf7a  mov     rcx, rsi; Str
0x18002cf7d  mov     rbx, rax
0x18002cf80  call    strlen
0x18002cf85  mov     rcx, rax
0x18002cf88  mov     r14, rax
0x18002cf8b  not     rcx
0x18002cf8e  cmp     rbx, rcx
0x18002cf91  ja      short loc_18002D002
0x18002cf93  lea     rcx, [rax+rbx]
0x18002cf97  cmp     rcx, 0FFFFFFFFFFFFFFFDh
0x18002cf9b  ja      short loc_18002D002
0x18002cf9d  lfence
0x18002cfa0  add     rcx, 2
0x18002cfa4  call    av_malloc
0x18002cfa9  mov     rdi, rax
0x18002cfac  test    rax, rax
0x18002cfaf  jz      short loc_18002CFFD
0x18002cfb1  test    rbx, rbx
0x18002cfb4  jz      short loc_18002CFE5
0x18002cfb6  lea     r8, [rbx+1]
0x18002cfba  mov     rdx, rbp
0x18002cfbd  mov     rcx, rax
0x18002cfc0  call    av_strlcpy
0x18002cfc5  test    r14, r14
0x18002cfc8  jz      short loc_18002CFE5
0x18002cfca  mov     al, 2Fh ; '/'
0x18002cfcc  cmp     [rdi+rbx-1], al
0x18002cfd0  jz      short loc_18002CFDE
0x18002cfd2  cmp     [rsi], al
0x18002cfd4  jz      short loc_18002CFE5
0x18002cfd6  mov     [rdi+rbx], al
0x18002cfd9  inc     rbx
0x18002cfdc  jmp     short loc_18002CFE5
0x18002cfde  cmp     [rsi], al
0x18002cfe0  jnz     short loc_18002CFE5
0x18002cfe2  dec     rbx
0x18002cfe5  lea     r8, [r14+1]
0x18002cfe9  mov     rdx, rsi
0x18002cfec  lea     rcx, [rdi+rbx]
0x18002cff0  call    av_strlcpy
0x18002cff5  lea     rax, [r14+rdi]
0x18002cff9  mov     byte ptr [rax+rbx], 0
0x18002cffd  mov     rax, rdi
0x18002d000  jmp     short loc_18002D004
0x18002d002  xor     eax, eax
0x18002d004  mov     rbx, [rsp+38h+arg_0]
0x18002d009  mov     rbp, [rsp+38h+arg_8]
0x18002d00e  mov     rsi, [rsp+38h+arg_10]
0x18002d013  add     rsp, 20h
0x18002d017  pop     r15
0x18002d019  pop     r14
0x18002d01b  pop     rdi
0x18002d01c  retn
```
