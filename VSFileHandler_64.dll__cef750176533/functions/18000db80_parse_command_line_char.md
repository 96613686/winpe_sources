# parse_command_line_char_

- ea: `0x18000db80`
- end: `0x18000dd3f`
- name: `parse_command_line_char_`
- size: `447`
- prototype: `char __fastcall(char *, _QWORD *, _BYTE *, _QWORD *, _QWORD *)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x18000dda0`

## callees

- `0x18000db80`
- `0x180013800`

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
        {
          *v6++ = v15;
          v15 = *a1;
        }
        if ( ismbblead(v15) )
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
0x18000db80  mov     rax, rsp
0x18000db83  mov     [rax+8], rbx
0x18000db87  mov     [rax+10h], rbp
0x18000db8b  mov     [rax+18h], rsi
0x18000db8f  mov     [rax+20h], rdi
0x18000db93  push    r12
0x18000db95  push    r14
0x18000db97  push    r15
0x18000db99  sub     rsp, 20h
0x18000db9d  mov     r15, [rsp+38h+arg_20]
0x18000dba2  mov     r12, r9
0x18000dba5  mov     rbx, r8
0x18000dba8  mov     r14, rdx
0x18000dbab  mov     rdi, rcx
0x18000dbae  and     qword ptr [r15], 0
0x18000dbb2  mov     qword ptr [r9], 1
0x18000dbb9  test    rdx, rdx
0x18000dbbc  jz      short loc_18000DBC5
0x18000dbbe  mov     [rdx], rbx
0x18000dbc1  add     r14, 8
0x18000dbc5  xor     bpl, bpl
0x18000dbc8  cmp     byte ptr [rdi], 22h ; '"'
0x18000dbcb  jnz     short loc_18000DBDC
0x18000dbcd  test    bpl, bpl
0x18000dbd0  mov     sil, 22h ; '"'
0x18000dbd3  setz    bpl
0x18000dbd7  inc     rdi
0x18000dbda  jmp     short loc_18000DC13
0x18000dbdc  inc     qword ptr [r15]
0x18000dbdf  test    rbx, rbx
0x18000dbe2  jz      short loc_18000DBEB
0x18000dbe4  mov     al, [rdi]
0x18000dbe6  mov     [rbx], al
0x18000dbe8  inc     rbx
0x18000dbeb  movsx   esi, byte ptr [rdi]
0x18000dbee  inc     rdi
0x18000dbf1  mov     ecx, esi; Ch
0x18000dbf3  call    _ismbblead
0x18000dbf8  test    eax, eax
0x18000dbfa  jz      short loc_18000DC0E
0x18000dbfc  inc     qword ptr [r15]
0x18000dbff  test    rbx, rbx
0x18000dc02  jz      short loc_18000DC0B
0x18000dc04  mov     al, [rdi]
0x18000dc06  mov     [rbx], al
0x18000dc08  inc     rbx
0x18000dc0b  inc     rdi
0x18000dc0e  test    sil, sil
0x18000dc11  jz      short loc_18000DC2F
0x18000dc13  test    bpl, bpl
0x18000dc16  jnz     short loc_18000DBC8
0x18000dc18  cmp     sil, 20h ; ' '
0x18000dc1c  jz      short loc_18000DC24
0x18000dc1e  cmp     sil, 9
0x18000dc22  jnz     short loc_18000DBC8
0x18000dc24  test    rbx, rbx
0x18000dc27  jz      short loc_18000DC32
0x18000dc29  mov     byte ptr [rbx-1], 0
0x18000dc2d  jmp     short loc_18000DC32
0x18000dc2f  dec     rdi
0x18000dc32  xor     sil, sil
0x18000dc35  mov     al, [rdi]
0x18000dc37  test    al, al
0x18000dc39  jz      loc_18000DD13
0x18000dc3f  cmp     al, 20h ; ' '
0x18000dc41  jz      short loc_18000DC47
0x18000dc43  cmp     al, 9
0x18000dc45  jnz     short loc_18000DC4E
0x18000dc47  inc     rdi
0x18000dc4a  mov     al, [rdi]
0x18000dc4c  jmp     short loc_18000DC3F
0x18000dc4e  test    al, al
0x18000dc50  jz      loc_18000DD13
0x18000dc56  test    r14, r14
0x18000dc59  jz      short loc_18000DC62
0x18000dc5b  mov     [r14], rbx
0x18000dc5e  add     r14, 8
0x18000dc62  inc     qword ptr [r12]
0x18000dc66  mov     edx, 1
0x18000dc6b  xor     eax, eax
0x18000dc6d  jmp     short loc_18000DC74
0x18000dc6f  inc     rdi
0x18000dc72  inc     eax
0x18000dc74  mov     cl, [rdi]
0x18000dc76  cmp     cl, 5Ch ; '\'
0x18000dc79  jz      short loc_18000DC6F
0x18000dc7b  cmp     cl, 22h ; '"'
0x18000dc7e  jnz     short loc_18000DCB0
0x18000dc80  test    dl, al
0x18000dc82  jnz     short loc_18000DC9C
0x18000dc84  test    sil, sil
0x18000dc87  jz      short loc_18000DC93
0x18000dc89  cmp     [rdi+1], cl
0x18000dc8c  jnz     short loc_18000DC93
0x18000dc8e  inc     rdi
0x18000dc91  jmp     short loc_18000DC9C
0x18000dc93  xor     edx, edx
0x18000dc95  test    sil, sil
0x18000dc98  setz    sil
0x18000dc9c  shr     eax, 1
0x18000dc9e  jmp     short loc_18000DCB0
0x18000dca0  dec     eax
0x18000dca2  test    rbx, rbx
0x18000dca5  jz      short loc_18000DCAD
0x18000dca7  mov     byte ptr [rbx], 5Ch ; '\'
0x18000dcaa  inc     rbx
0x18000dcad  inc     qword ptr [r15]
0x18000dcb0  test    eax, eax
0x18000dcb2  jnz     short loc_18000DCA0
0x18000dcb4  mov     al, [rdi]
0x18000dcb6  test    al, al
0x18000dcb8  jz      short loc_18000DD00
0x18000dcba  test    sil, sil
0x18000dcbd  jnz     short loc_18000DCC7
0x18000dcbf  cmp     al, 20h ; ' '
0x18000dcc1  jz      short loc_18000DD00
0x18000dcc3  cmp     al, 9
0x18000dcc5  jz      short loc_18000DD00
0x18000dcc7  test    edx, edx
0x18000dcc9  jz      short loc_18000DCF8
0x18000dccb  test    rbx, rbx
0x18000dcce  jz      short loc_18000DCD7
0x18000dcd0  mov     [rbx], al
0x18000dcd2  inc     rbx
0x18000dcd5  mov     al, [rdi]
0x18000dcd7  movsx   ecx, al; Ch
0x18000dcda  call    _ismbblead
0x18000dcdf  test    eax, eax
0x18000dce1  jz      short loc_18000DCF5
0x18000dce3  inc     qword ptr [r15]
0x18000dce6  inc     rdi
0x18000dce9  test    rbx, rbx
0x18000dcec  jz      short loc_18000DCF5
0x18000dcee  mov     al, [rdi]
0x18000dcf0  mov     [rbx], al
0x18000dcf2  inc     rbx
0x18000dcf5  inc     qword ptr [r15]
0x18000dcf8  inc     rdi
0x18000dcfb  jmp     loc_18000DC66
0x18000dd00  test    rbx, rbx
0x18000dd03  jz      short loc_18000DD0B
0x18000dd05  mov     byte ptr [rbx], 0
0x18000dd08  inc     rbx
0x18000dd0b  inc     qword ptr [r15]
0x18000dd0e  jmp     loc_18000DC35
0x18000dd13  test    r14, r14
0x18000dd16  jz      short loc_18000DD1C
0x18000dd18  and     qword ptr [r14], 0
0x18000dd1c  inc     qword ptr [r12]
0x18000dd20  mov     rbx, [rsp+38h+arg_0]
0x18000dd25  mov     rbp, [rsp+38h+arg_8]
0x18000dd2a  mov     rsi, [rsp+38h+arg_10]
0x18000dd2f  mov     rdi, [rsp+38h+arg_18]
0x18000dd34  add     rsp, 20h
0x18000dd38  pop     r15
0x18000dd3a  pop     r14
0x18000dd3c  pop     r12
0x18000dd3e  retn
```
