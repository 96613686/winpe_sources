# parse_command_line_char_

- ea: `0x180004788`
- end: `0x180004945`
- name: `parse_command_line_char_`
- size: `445`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180004478`
- `0x180004d00`

## callees

- `0x180004788`
- `0x18000b230`

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
0x180004788  mov     rax, rsp
0x18000478b  mov     [rax+8], rbx
0x18000478f  mov     [rax+10h], rbp
0x180004793  mov     [rax+18h], rsi
0x180004797  mov     [rax+20h], rdi
0x18000479b  push    r12
0x18000479d  push    r14
0x18000479f  push    r15
0x1800047a1  sub     rsp, 20h
0x1800047a5  mov     r15, [rsp+38h+arg_20]
0x1800047aa  mov     r12, r9
0x1800047ad  mov     rbx, r8
0x1800047b0  mov     r14, rdx
0x1800047b3  mov     rdi, rcx
0x1800047b6  and     qword ptr [r15], 0
0x1800047ba  mov     qword ptr [r9], 1
0x1800047c1  test    rdx, rdx
0x1800047c4  jz      short loc_1800047CD
0x1800047c6  mov     [rdx], rbx
0x1800047c9  add     r14, 8
0x1800047cd  xor     bpl, bpl
0x1800047d0  cmp     byte ptr [rdi], 22h ; '"'
0x1800047d3  jnz     short loc_1800047E4
0x1800047d5  test    bpl, bpl
0x1800047d8  mov     sil, 22h ; '"'
0x1800047db  setz    bpl
0x1800047df  inc     rdi
0x1800047e2  jmp     short loc_18000481B
0x1800047e4  inc     qword ptr [r15]
0x1800047e7  test    rbx, rbx
0x1800047ea  jz      short loc_1800047F3
0x1800047ec  mov     al, [rdi]
0x1800047ee  mov     [rbx], al
0x1800047f0  inc     rbx
0x1800047f3  movsx   esi, byte ptr [rdi]
0x1800047f6  inc     rdi
0x1800047f9  mov     ecx, esi; Ch
0x1800047fb  call    _ismbblead
0x180004800  test    eax, eax
0x180004802  jz      short loc_180004816
0x180004804  inc     qword ptr [r15]
0x180004807  test    rbx, rbx
0x18000480a  jz      short loc_180004813
0x18000480c  mov     al, [rdi]
0x18000480e  mov     [rbx], al
0x180004810  inc     rbx
0x180004813  inc     rdi
0x180004816  test    sil, sil
0x180004819  jz      short loc_180004837
0x18000481b  test    bpl, bpl
0x18000481e  jnz     short loc_1800047D0
0x180004820  cmp     sil, 20h ; ' '
0x180004824  jz      short loc_18000482C
0x180004826  cmp     sil, 9
0x18000482a  jnz     short loc_1800047D0
0x18000482c  test    rbx, rbx
0x18000482f  jz      short loc_18000483A
0x180004831  mov     byte ptr [rbx-1], 0
0x180004835  jmp     short loc_18000483A
0x180004837  dec     rdi
0x18000483a  xor     sil, sil
0x18000483d  mov     al, [rdi]
0x18000483f  test    al, al
0x180004841  jz      loc_180004919
0x180004847  cmp     al, 20h ; ' '
0x180004849  jz      short loc_18000484F
0x18000484b  cmp     al, 9
0x18000484d  jnz     short loc_180004856
0x18000484f  inc     rdi
0x180004852  mov     al, [rdi]
0x180004854  jmp     short loc_180004847
0x180004856  test    al, al
0x180004858  jz      loc_180004919
0x18000485e  test    r14, r14
0x180004861  jz      short loc_18000486A
0x180004863  mov     [r14], rbx
0x180004866  add     r14, 8
0x18000486a  inc     qword ptr [r12]
0x18000486e  mov     edx, 1
0x180004873  xor     eax, eax
0x180004875  jmp     short loc_18000487C
0x180004877  inc     rdi
0x18000487a  inc     eax
0x18000487c  mov     cl, [rdi]
0x18000487e  cmp     cl, 5Ch ; '\'
0x180004881  jz      short loc_180004877
0x180004883  cmp     cl, 22h ; '"'
0x180004886  jnz     short loc_1800048B8
0x180004888  test    dl, al
0x18000488a  jnz     short loc_1800048A4
0x18000488c  test    sil, sil
0x18000488f  jz      short loc_18000489B
0x180004891  cmp     [rdi+1], cl
0x180004894  jnz     short loc_18000489B
0x180004896  inc     rdi
0x180004899  jmp     short loc_1800048A4
0x18000489b  xor     edx, edx
0x18000489d  test    sil, sil
0x1800048a0  setz    sil
0x1800048a4  shr     eax, 1
0x1800048a6  jmp     short loc_1800048B8
0x1800048a8  dec     eax
0x1800048aa  test    rbx, rbx
0x1800048ad  jz      short loc_1800048B5
0x1800048af  mov     byte ptr [rbx], 5Ch ; '\'
0x1800048b2  inc     rbx
0x1800048b5  inc     qword ptr [r15]
0x1800048b8  test    eax, eax
0x1800048ba  jnz     short loc_1800048A8
0x1800048bc  mov     al, [rdi]
0x1800048be  test    al, al
0x1800048c0  jz      short loc_180004906
0x1800048c2  test    sil, sil
0x1800048c5  jnz     short loc_1800048CF
0x1800048c7  cmp     al, 20h ; ' '
0x1800048c9  jz      short loc_180004906
0x1800048cb  cmp     al, 9
0x1800048cd  jz      short loc_180004906
0x1800048cf  test    edx, edx
0x1800048d1  jz      short loc_1800048FE
0x1800048d3  test    rbx, rbx
0x1800048d6  jz      short loc_1800048DD
0x1800048d8  mov     [rbx], al
0x1800048da  inc     rbx
0x1800048dd  movsx   ecx, byte ptr [rdi]; Ch
0x1800048e0  call    _ismbblead
0x1800048e5  test    eax, eax
0x1800048e7  jz      short loc_1800048FB
0x1800048e9  inc     qword ptr [r15]
0x1800048ec  inc     rdi
0x1800048ef  test    rbx, rbx
0x1800048f2  jz      short loc_1800048FB
0x1800048f4  mov     al, [rdi]
0x1800048f6  mov     [rbx], al
0x1800048f8  inc     rbx
0x1800048fb  inc     qword ptr [r15]
0x1800048fe  inc     rdi
0x180004901  jmp     loc_18000486E
0x180004906  test    rbx, rbx
0x180004909  jz      short loc_180004911
0x18000490b  mov     byte ptr [rbx], 0
0x18000490e  inc     rbx
0x180004911  inc     qword ptr [r15]
0x180004914  jmp     loc_18000483D
0x180004919  test    r14, r14
0x18000491c  jz      short loc_180004922
0x18000491e  and     qword ptr [r14], 0
0x180004922  inc     qword ptr [r12]
0x180004926  mov     rbx, [rsp+38h+arg_0]
0x18000492b  mov     rbp, [rsp+38h+arg_8]
0x180004930  mov     rsi, [rsp+38h+arg_10]
0x180004935  mov     rdi, [rsp+38h+arg_18]
0x18000493a  add     rsp, 20h
0x18000493e  pop     r15
0x180004940  pop     r14
0x180004942  pop     r12
0x180004944  retn
```
