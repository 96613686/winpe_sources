# parse_command_line_wchar_t_

- ea: `0x180004948`
- end: `0x180004aea`
- name: `parse_command_line_wchar_t_`
- size: `418`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x1800045f4`
- `0x180004e80`

## callees

- `0x180004948`

## pseudocode

```c
__int64 __fastcall parse_command_line_wchar_t_(__int16 *a1, __int16 **a2, __int16 *a3, _QWORD *a4, _QWORD *a5)
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
0x180004948  mov     rax, rsp
0x18000494b  mov     [rax+8], rbx
0x18000494f  mov     [rax+10h], rsi
0x180004953  mov     [rax+18h], rdi
0x180004957  mov     [rax+20h], r14
0x18000495b  push    r15
0x18000495d  mov     r11, [rsp+8+arg_20]
0x180004962  xor     esi, esi
0x180004964  mov     rbx, r9
0x180004967  mov     [r11], rsi
0x18000496a  mov     qword ptr [r9], 1
0x180004971  test    rdx, rdx
0x180004974  jz      short loc_18000497D
0x180004976  mov     [rdx], r8
0x180004979  add     rdx, 8
0x18000497d  mov     r9b, sil
0x180004980  mov     r15d, 22h ; '"'
0x180004986  mov     r10, rcx
0x180004989  cmp     [rcx], r15w
0x18000498d  jnz     short loc_1800049A0
0x18000498f  test    r9b, r9b
0x180004992  movzx   eax, r15w
0x180004996  setz    r9b
0x18000499a  add     rcx, 2
0x18000499e  jmp     short loc_1800049BF
0x1800049a0  inc     qword ptr [r11]
0x1800049a3  test    r8, r8
0x1800049a6  jz      short loc_1800049B3
0x1800049a8  movzx   eax, word ptr [rcx]
0x1800049ab  mov     [r8], ax
0x1800049af  add     r8, 2
0x1800049b3  movzx   eax, word ptr [rcx]
0x1800049b6  add     rcx, 2
0x1800049ba  test    ax, ax
0x1800049bd  jz      short loc_1800049DC
0x1800049bf  test    r9b, r9b
0x1800049c2  jnz     short loc_180004986
0x1800049c4  cmp     ax, 20h ; ' '
0x1800049c8  jz      short loc_1800049D0
0x1800049ca  cmp     ax, 9
0x1800049ce  jnz     short loc_180004986
0x1800049d0  test    r8, r8
0x1800049d3  jz      short loc_1800049DF
0x1800049d5  mov     [r8-2], si
0x1800049da  jmp     short loc_1800049DF
0x1800049dc  mov     rcx, r10
0x1800049df  mov     dil, sil
0x1800049e2  mov     r14d, 5Ch ; '\'
0x1800049e8  movzx   eax, word ptr [rcx]
0x1800049eb  test    ax, ax
0x1800049ee  jz      loc_180004AC8
0x1800049f4  cmp     ax, 20h ; ' '
0x1800049f8  jz      short loc_180004A00
0x1800049fa  cmp     ax, 9
0x1800049fe  jnz     short loc_180004A09
0x180004a00  add     rcx, 2
0x180004a04  movzx   eax, word ptr [rcx]
0x180004a07  jmp     short loc_1800049F4
0x180004a09  test    ax, ax
0x180004a0c  jz      loc_180004AC8
0x180004a12  test    rdx, rdx
0x180004a15  jz      short loc_180004A1E
0x180004a17  mov     [rdx], r8
0x180004a1a  add     rdx, 8
0x180004a1e  inc     qword ptr [rbx]
0x180004a21  mov     r10d, 1
0x180004a27  mov     eax, esi
0x180004a29  jmp     short loc_180004A31
0x180004a2b  add     rcx, 2
0x180004a2f  inc     eax
0x180004a31  movzx   r9d, word ptr [rcx]
0x180004a35  cmp     r9w, r14w
0x180004a39  jz      short loc_180004A2B
0x180004a3b  cmp     r9w, r15w
0x180004a3f  jnz     short loc_180004A78
0x180004a41  test    r10b, al
0x180004a44  jnz     short loc_180004A62
0x180004a46  test    dil, dil
0x180004a49  jz      short loc_180004A58
0x180004a4b  cmp     [rcx+2], r15w
0x180004a50  jnz     short loc_180004A58
0x180004a52  add     rcx, 2
0x180004a56  jmp     short loc_180004A62
0x180004a58  test    dil, dil
0x180004a5b  mov     r10d, esi
0x180004a5e  setz    dil
0x180004a62  shr     eax, 1
0x180004a64  jmp     short loc_180004A78
0x180004a66  dec     eax
0x180004a68  test    r8, r8
0x180004a6b  jz      short loc_180004A75
0x180004a6d  mov     [r8], r14w
0x180004a71  add     r8, 2
0x180004a75  inc     qword ptr [r11]
0x180004a78  test    eax, eax
0x180004a7a  jnz     short loc_180004A66
0x180004a7c  movzx   eax, word ptr [rcx]
0x180004a7f  test    ax, ax
0x180004a82  jz      short loc_180004AB3
0x180004a84  test    dil, dil
0x180004a87  jnz     short loc_180004A95
0x180004a89  cmp     ax, 20h ; ' '
0x180004a8d  jz      short loc_180004AB3
0x180004a8f  cmp     ax, 9
0x180004a93  jz      short loc_180004AB3
0x180004a95  test    r10d, r10d
0x180004a98  jz      short loc_180004AAA
0x180004a9a  test    r8, r8
0x180004a9d  jz      short loc_180004AA7
0x180004a9f  mov     [r8], ax
0x180004aa3  add     r8, 2
0x180004aa7  inc     qword ptr [r11]
0x180004aaa  add     rcx, 2
0x180004aae  jmp     loc_180004A21
0x180004ab3  test    r8, r8
0x180004ab6  jz      short loc_180004AC0
0x180004ab8  mov     [r8], si
0x180004abc  add     r8, 2
0x180004ac0  inc     qword ptr [r11]
0x180004ac3  jmp     loc_1800049E8
0x180004ac8  test    rdx, rdx
0x180004acb  jz      short loc_180004AD0
0x180004acd  mov     [rdx], rsi
0x180004ad0  inc     qword ptr [rbx]
0x180004ad3  mov     rbx, [rsp+8+arg_0]
0x180004ad8  mov     rsi, [rsp+8+arg_8]
0x180004add  mov     rdi, [rsp+8+arg_10]
0x180004ae2  mov     r14, [rsp+8+arg_18]
0x180004ae7  pop     r15
0x180004ae9  retn
```
