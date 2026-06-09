# parse_command_line_wchar_t_

- ea: `0x1800041ec`
- end: `0x18000438e`
- name: `parse_command_line_wchar_t_`
- size: `418`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x180003e98`
- `0x180004724`

## callees

- `0x1800041ec`

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
0x1800041ec  mov     rax, rsp
0x1800041ef  mov     [rax+8], rbx
0x1800041f3  mov     [rax+10h], rsi
0x1800041f7  mov     [rax+18h], rdi
0x1800041fb  mov     [rax+20h], r14
0x1800041ff  push    r15
0x180004201  mov     r11, [rsp+8+arg_20]
0x180004206  xor     esi, esi
0x180004208  mov     rbx, r9
0x18000420b  mov     [r11], rsi
0x18000420e  mov     qword ptr [r9], 1
0x180004215  test    rdx, rdx
0x180004218  jz      short loc_180004221
0x18000421a  mov     [rdx], r8
0x18000421d  add     rdx, 8
0x180004221  mov     r9b, sil
0x180004224  mov     r15d, 22h ; '"'
0x18000422a  mov     r10, rcx
0x18000422d  cmp     [rcx], r15w
0x180004231  jnz     short loc_180004244
0x180004233  test    r9b, r9b
0x180004236  movzx   eax, r15w
0x18000423a  setz    r9b
0x18000423e  add     rcx, 2
0x180004242  jmp     short loc_180004263
0x180004244  inc     qword ptr [r11]
0x180004247  test    r8, r8
0x18000424a  jz      short loc_180004257
0x18000424c  movzx   eax, word ptr [rcx]
0x18000424f  mov     [r8], ax
0x180004253  add     r8, 2
0x180004257  movzx   eax, word ptr [rcx]
0x18000425a  add     rcx, 2
0x18000425e  test    ax, ax
0x180004261  jz      short loc_180004280
0x180004263  test    r9b, r9b
0x180004266  jnz     short loc_18000422A
0x180004268  cmp     ax, 20h ; ' '
0x18000426c  jz      short loc_180004274
0x18000426e  cmp     ax, 9
0x180004272  jnz     short loc_18000422A
0x180004274  test    r8, r8
0x180004277  jz      short loc_180004283
0x180004279  mov     [r8-2], si
0x18000427e  jmp     short loc_180004283
0x180004280  mov     rcx, r10
0x180004283  mov     dil, sil
0x180004286  mov     r14d, 5Ch ; '\'
0x18000428c  movzx   eax, word ptr [rcx]
0x18000428f  test    ax, ax
0x180004292  jz      loc_18000436C
0x180004298  cmp     ax, 20h ; ' '
0x18000429c  jz      short loc_1800042A4
0x18000429e  cmp     ax, 9
0x1800042a2  jnz     short loc_1800042AD
0x1800042a4  add     rcx, 2
0x1800042a8  movzx   eax, word ptr [rcx]
0x1800042ab  jmp     short loc_180004298
0x1800042ad  test    ax, ax
0x1800042b0  jz      loc_18000436C
0x1800042b6  test    rdx, rdx
0x1800042b9  jz      short loc_1800042C2
0x1800042bb  mov     [rdx], r8
0x1800042be  add     rdx, 8
0x1800042c2  inc     qword ptr [rbx]
0x1800042c5  mov     r10d, 1
0x1800042cb  mov     eax, esi
0x1800042cd  jmp     short loc_1800042D5
0x1800042cf  add     rcx, 2
0x1800042d3  inc     eax
0x1800042d5  movzx   r9d, word ptr [rcx]
0x1800042d9  cmp     r9w, r14w
0x1800042dd  jz      short loc_1800042CF
0x1800042df  cmp     r9w, r15w
0x1800042e3  jnz     short loc_18000431C
0x1800042e5  test    r10b, al
0x1800042e8  jnz     short loc_180004306
0x1800042ea  test    dil, dil
0x1800042ed  jz      short loc_1800042FC
0x1800042ef  cmp     [rcx+2], r15w
0x1800042f4  jnz     short loc_1800042FC
0x1800042f6  add     rcx, 2
0x1800042fa  jmp     short loc_180004306
0x1800042fc  test    dil, dil
0x1800042ff  mov     r10d, esi
0x180004302  setz    dil
0x180004306  shr     eax, 1
0x180004308  jmp     short loc_18000431C
0x18000430a  dec     eax
0x18000430c  test    r8, r8
0x18000430f  jz      short loc_180004319
0x180004311  mov     [r8], r14w
0x180004315  add     r8, 2
0x180004319  inc     qword ptr [r11]
0x18000431c  test    eax, eax
0x18000431e  jnz     short loc_18000430A
0x180004320  movzx   eax, word ptr [rcx]
0x180004323  test    ax, ax
0x180004326  jz      short loc_180004357
0x180004328  test    dil, dil
0x18000432b  jnz     short loc_180004339
0x18000432d  cmp     ax, 20h ; ' '
0x180004331  jz      short loc_180004357
0x180004333  cmp     ax, 9
0x180004337  jz      short loc_180004357
0x180004339  test    r10d, r10d
0x18000433c  jz      short loc_18000434E
0x18000433e  test    r8, r8
0x180004341  jz      short loc_18000434B
0x180004343  mov     [r8], ax
0x180004347  add     r8, 2
0x18000434b  inc     qword ptr [r11]
0x18000434e  add     rcx, 2
0x180004352  jmp     loc_1800042C5
0x180004357  test    r8, r8
0x18000435a  jz      short loc_180004364
0x18000435c  mov     [r8], si
0x180004360  add     r8, 2
0x180004364  inc     qword ptr [r11]
0x180004367  jmp     loc_18000428C
0x18000436c  test    rdx, rdx
0x18000436f  jz      short loc_180004374
0x180004371  mov     [rdx], rsi
0x180004374  inc     qword ptr [rbx]
0x180004377  mov     rbx, [rsp+8+arg_0]
0x18000437c  mov     rsi, [rsp+8+arg_8]
0x180004381  mov     rdi, [rsp+8+arg_10]
0x180004386  mov     r14, [rsp+8+arg_18]
0x18000438b  pop     r15
0x18000438d  retn
```
