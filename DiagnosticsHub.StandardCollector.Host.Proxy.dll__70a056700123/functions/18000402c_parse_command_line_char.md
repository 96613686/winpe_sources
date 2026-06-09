# parse_command_line_char_

- ea: `0x18000402c`
- end: `0x1800041e9`
- name: `parse_command_line_char_`
- size: `445`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180003d1c`
- `0x1800045a4`

## callees

- `0x18000402c`
- `0x18000aad0`

## pseudocode

```c
char __fastcall parse_command_line_char_(char *a1, _QWORD *a2, _BYTE *a3, _QWORD *a4, _QWORD *a5)
{
  _BYTE *v6; // rbx
  _QWORD *v7; // r14
  bool v9; // bp
  unsigned int v10; // esi
  bool v11; // si
  char result; // al
  int v13; // edx
  unsigned int v14; // eax
  char v15; // al

  v6 = a3;
  v7 = a2;
  *a5 = 0;
  *a4 = 1;
  if ( a2 )
  {
    *a2 = a3;
    v7 = a2 + 1;
  }
  v9 = 0;
  do
  {
    if ( *a1 == 34 )
    {
      LOBYTE(v10) = 34;
      v9 = !v9;
      ++a1;
    }
    else
    {
      ++*a5;
      if ( v6 )
        *v6++ = *a1;
      v10 = *a1++;
      if ( ismbblead(v10) )
      {
        ++*a5;
        if ( v6 )
          *v6++ = *a1;
        ++a1;
      }
      if ( !(_BYTE)v10 )
      {
        --a1;
        goto LABEL_19;
      }
    }
  }
  while ( v9 || (_BYTE)v10 != 32 && (_BYTE)v10 != 9 );
  if ( v6 )
    *(v6 - 1) = 0;
LABEL_19:
  v11 = 0;
  while ( 1 )
  {
    result = *a1;
    if ( !*a1 )
      break;
    while ( result == 32 || result == 9 )
      result = *++a1;
    if ( !result )
      break;
    if ( v7 )
      *v7++ = v6;
    ++*a4;
    while ( 1 )
    {
      v13 = 1;
      v14 = 0;
      while ( *a1 == 92 )
      {
        ++a1;
        ++v14;
      }
      if ( *a1 == 34 )
      {
        if ( (v14 & 1) == 0 )
        {
          if ( v11 && a1[1] == 34 )
          {
            ++a1;
          }
          else
          {
            v13 = 0;
            v11 = !v11;
          }
        }
        v14 >>= 1;
      }
      while ( v14 )
      {
        --v14;
        if ( v6 )
          *v6++ = 92;
        ++*a5;
      }
      v15 = *a1;
      if ( !*a1 || !v11 && (v15 == 32 || v15 == 9) )
        break;
      if ( v13 )
      {
        if ( v6 )
          *v6++ = v15;
        if ( ismbblead(*a1) )
        {
          ++*a5;
          ++a1;
          if ( v6 )
            *v6++ = *a1;
        }
        ++*a5;
      }
      ++a1;
    }
    if ( v6 )
      *v6++ = 0;
    ++*a5;
  }
  if ( v7 )
    *v7 = 0;
  ++*a4;
  return result;
}

```

## disassembly

```asm
0x18000402c  mov     rax, rsp
0x18000402f  mov     [rax+8], rbx
0x180004033  mov     [rax+10h], rbp
0x180004037  mov     [rax+18h], rsi
0x18000403b  mov     [rax+20h], rdi
0x18000403f  push    r12
0x180004041  push    r14
0x180004043  push    r15
0x180004045  sub     rsp, 20h
0x180004049  mov     r15, [rsp+38h+arg_20]
0x18000404e  mov     r12, r9
0x180004051  mov     rbx, r8
0x180004054  mov     r14, rdx
0x180004057  mov     rdi, rcx
0x18000405a  and     qword ptr [r15], 0
0x18000405e  mov     qword ptr [r9], 1
0x180004065  test    rdx, rdx
0x180004068  jz      short loc_180004071
0x18000406a  mov     [rdx], rbx
0x18000406d  add     r14, 8
0x180004071  xor     bpl, bpl
0x180004074  cmp     byte ptr [rdi], 22h ; '"'
0x180004077  jnz     short loc_180004088
0x180004079  test    bpl, bpl
0x18000407c  mov     sil, 22h ; '"'
0x18000407f  setz    bpl
0x180004083  inc     rdi
0x180004086  jmp     short loc_1800040BF
0x180004088  inc     qword ptr [r15]
0x18000408b  test    rbx, rbx
0x18000408e  jz      short loc_180004097
0x180004090  mov     al, [rdi]
0x180004092  mov     [rbx], al
0x180004094  inc     rbx
0x180004097  movsx   esi, byte ptr [rdi]
0x18000409a  inc     rdi
0x18000409d  mov     ecx, esi; Ch
0x18000409f  call    _ismbblead
0x1800040a4  test    eax, eax
0x1800040a6  jz      short loc_1800040BA
0x1800040a8  inc     qword ptr [r15]
0x1800040ab  test    rbx, rbx
0x1800040ae  jz      short loc_1800040B7
0x1800040b0  mov     al, [rdi]
0x1800040b2  mov     [rbx], al
0x1800040b4  inc     rbx
0x1800040b7  inc     rdi
0x1800040ba  test    sil, sil
0x1800040bd  jz      short loc_1800040DB
0x1800040bf  test    bpl, bpl
0x1800040c2  jnz     short loc_180004074
0x1800040c4  cmp     sil, 20h ; ' '
0x1800040c8  jz      short loc_1800040D0
0x1800040ca  cmp     sil, 9
0x1800040ce  jnz     short loc_180004074
0x1800040d0  test    rbx, rbx
0x1800040d3  jz      short loc_1800040DE
0x1800040d5  mov     byte ptr [rbx-1], 0
0x1800040d9  jmp     short loc_1800040DE
0x1800040db  dec     rdi
0x1800040de  xor     sil, sil
0x1800040e1  mov     al, [rdi]
0x1800040e3  test    al, al
0x1800040e5  jz      loc_1800041BD
0x1800040eb  cmp     al, 20h ; ' '
0x1800040ed  jz      short loc_1800040F3
0x1800040ef  cmp     al, 9
0x1800040f1  jnz     short loc_1800040FA
0x1800040f3  inc     rdi
0x1800040f6  mov     al, [rdi]
0x1800040f8  jmp     short loc_1800040EB
0x1800040fa  test    al, al
0x1800040fc  jz      loc_1800041BD
0x180004102  test    r14, r14
0x180004105  jz      short loc_18000410E
0x180004107  mov     [r14], rbx
0x18000410a  add     r14, 8
0x18000410e  inc     qword ptr [r12]
0x180004112  mov     edx, 1
0x180004117  xor     eax, eax
0x180004119  jmp     short loc_180004120
0x18000411b  inc     rdi
0x18000411e  inc     eax
0x180004120  mov     cl, [rdi]
0x180004122  cmp     cl, 5Ch ; '\'
0x180004125  jz      short loc_18000411B
0x180004127  cmp     cl, 22h ; '"'
0x18000412a  jnz     short loc_18000415C
0x18000412c  test    dl, al
0x18000412e  jnz     short loc_180004148
0x180004130  test    sil, sil
0x180004133  jz      short loc_18000413F
0x180004135  cmp     [rdi+1], cl
0x180004138  jnz     short loc_18000413F
0x18000413a  inc     rdi
0x18000413d  jmp     short loc_180004148
0x18000413f  xor     edx, edx
0x180004141  test    sil, sil
0x180004144  setz    sil
0x180004148  shr     eax, 1
0x18000414a  jmp     short loc_18000415C
0x18000414c  dec     eax
0x18000414e  test    rbx, rbx
0x180004151  jz      short loc_180004159
0x180004153  mov     byte ptr [rbx], 5Ch ; '\'
0x180004156  inc     rbx
0x180004159  inc     qword ptr [r15]
0x18000415c  test    eax, eax
0x18000415e  jnz     short loc_18000414C
0x180004160  mov     al, [rdi]
0x180004162  test    al, al
0x180004164  jz      short loc_1800041AA
0x180004166  test    sil, sil
0x180004169  jnz     short loc_180004173
0x18000416b  cmp     al, 20h ; ' '
0x18000416d  jz      short loc_1800041AA
0x18000416f  cmp     al, 9
0x180004171  jz      short loc_1800041AA
0x180004173  test    edx, edx
0x180004175  jz      short loc_1800041A2
0x180004177  test    rbx, rbx
0x18000417a  jz      short loc_180004181
0x18000417c  mov     [rbx], al
0x18000417e  inc     rbx
0x180004181  movsx   ecx, byte ptr [rdi]; Ch
0x180004184  call    _ismbblead
0x180004189  test    eax, eax
0x18000418b  jz      short loc_18000419F
0x18000418d  inc     qword ptr [r15]
0x180004190  inc     rdi
0x180004193  test    rbx, rbx
0x180004196  jz      short loc_18000419F
0x180004198  mov     al, [rdi]
0x18000419a  mov     [rbx], al
0x18000419c  inc     rbx
0x18000419f  inc     qword ptr [r15]
0x1800041a2  inc     rdi
0x1800041a5  jmp     loc_180004112
0x1800041aa  test    rbx, rbx
0x1800041ad  jz      short loc_1800041B5
0x1800041af  mov     byte ptr [rbx], 0
0x1800041b2  inc     rbx
0x1800041b5  inc     qword ptr [r15]
0x1800041b8  jmp     loc_1800040E1
0x1800041bd  test    r14, r14
0x1800041c0  jz      short loc_1800041C6
0x1800041c2  and     qword ptr [r14], 0
0x1800041c6  inc     qword ptr [r12]
0x1800041ca  mov     rbx, [rsp+38h+arg_0]
0x1800041cf  mov     rbp, [rsp+38h+arg_8]
0x1800041d4  mov     rsi, [rsp+38h+arg_10]
0x1800041d9  mov     rdi, [rsp+38h+arg_18]
0x1800041de  add     rsp, 20h
0x1800041e2  pop     r15
0x1800041e4  pop     r14
0x1800041e6  pop     r12
0x1800041e8  retn
```
