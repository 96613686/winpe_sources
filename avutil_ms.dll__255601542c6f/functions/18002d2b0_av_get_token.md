# av_get_token

- ea: `0x18002d2b0`
- end: `0x18002d3cf`
- name: `av_get_token`
- size: `287`
- prototype: ``
- caller_count: `3`
- callee_count: `4`
- tags: ``

## callers

- `0x180036100`
- `0x180046350`
- `0x180048010`

## callees

- `0x18002d2b0`
- `0x180044d10`
- `0x180078c1a`
- `0x180078c26`

## pseudocode

```c
char *__fastcall av_get_token(const char **a1, const char *a2)
{
  size_t v4; // rax
  char *result; // rax
  const char *v6; // rdi
  char *v7; // rbx
  char *v8; // rsi
  char *v9; // r14
  const char *v10; // rdi
  const char *v11; // rbp
  char v12; // al
  char v13; // al
  void *v14; // rax

  v4 = strlen(*a1);
  result = (char *)av_realloc(0, v4 + 1);
  v7 = result;
  v8 = result;
  v9 = result;
  if ( !result )
    return result;
  v6 = *a1;
  v10 = &v6[strspn(v6, " \n\t\r")];
  while ( *v10 )
  {
    v11 = v10;
    if ( strspn(v10, a2) )
      break;
    v12 = *v10++;
    if ( v12 == 92 )
    {
      if ( !*v10 )
        goto LABEL_13;
      *v7 = *v10;
      v10 = v11 + 2;
      v9 = ++v7;
    }
    else if ( v12 == 39 )
    {
      v13 = *v10;
      if ( !*v10 )
        goto LABEL_15;
      do
      {
        if ( v13 == 39 )
          break;
        ++v10;
        *v7++ = v13;
        v13 = *v10;
      }
      while ( *v10 );
      if ( !*v10 )
        goto LABEL_15;
      ++v10;
      v9 = v7;
    }
    else
    {
LABEL_13:
      *v7++ = v12;
    }
  }
  do
  {
LABEL_15:
    *v7-- = 0;
    if ( v7 < v9 )
      break;
    _mm_lfence();
  }
  while ( strspn(v7, " \n\t\r") );
  *a1 = v10;
  v14 = av_realloc(v8, v7 - v8 + 2);
  if ( v14 )
    return (char *)v14;
  return v8;
}

```

## disassembly

```asm
0x18002d2b0  mov     rax, rsp
0x18002d2b3  mov     [rax+8], rbx
0x18002d2b7  mov     [rax+10h], rbp
0x18002d2bb  mov     [rax+18h], rsi
0x18002d2bf  mov     [rax+20h], rdi
0x18002d2c3  push    r12
0x18002d2c5  push    r14
0x18002d2c7  push    r15
0x18002d2c9  sub     rsp, 20h
0x18002d2cd  mov     r15, rcx
0x18002d2d0  mov     r12, rdx
0x18002d2d3  mov     rcx, [rcx]; Str
0x18002d2d6  call    strlen
0x18002d2db  xor     ecx, ecx
0x18002d2dd  lea     rdx, [rax+1]
0x18002d2e1  call    av_realloc
0x18002d2e6  mov     rdi, [r15]
0x18002d2e9  mov     rbx, rax
0x18002d2ec  mov     rsi, rax
0x18002d2ef  mov     r14, rax
0x18002d2f2  test    rax, rax
0x18002d2f5  jz      loc_18002D3B0
0x18002d2fb  lea     rdx, Control; " \n\t\r"
0x18002d302  mov     rcx, rdi; Str
0x18002d305  call    strspn
0x18002d30a  add     rdi, rax
0x18002d30d  jmp     short loc_18002D36D
0x18002d30f  mov     rdx, r12; Control
0x18002d312  mov     rcx, rdi; Str
0x18002d315  mov     rbp, rdi
0x18002d318  call    strspn
0x18002d31d  test    rax, rax
0x18002d320  jnz     short loc_18002D372
0x18002d322  mov     al, [rdi]
0x18002d324  inc     rdi
0x18002d327  cmp     al, 5Ch ; '\'
0x18002d329  jnz     short loc_18002D33F
0x18002d32b  mov     cl, [rdi]
0x18002d32d  test    cl, cl
0x18002d32f  jz      short loc_18002D368
0x18002d331  mov     [rbx], cl
0x18002d333  lea     rdi, [rbp+2]
0x18002d337  inc     rbx
0x18002d33a  mov     r14, rbx
0x18002d33d  jmp     short loc_18002D36D
0x18002d33f  cmp     al, 27h ; '''
0x18002d341  jnz     short loc_18002D368
0x18002d343  mov     al, [rdi]
0x18002d345  test    al, al
0x18002d347  jz      short loc_18002D372
0x18002d349  cmp     al, 27h ; '''
0x18002d34b  jz      short loc_18002D35B
0x18002d34d  inc     rdi
0x18002d350  mov     [rbx], al
0x18002d352  inc     rbx
0x18002d355  mov     al, [rdi]
0x18002d357  test    al, al
0x18002d359  jnz     short loc_18002D349
0x18002d35b  cmp     byte ptr [rdi], 0
0x18002d35e  jz      short loc_18002D372
0x18002d360  inc     rdi
0x18002d363  mov     r14, rbx
0x18002d366  jmp     short loc_18002D36D
0x18002d368  mov     [rbx], al
0x18002d36a  inc     rbx
0x18002d36d  cmp     byte ptr [rdi], 0
0x18002d370  jnz     short loc_18002D30F
0x18002d372  mov     byte ptr [rbx], 0
0x18002d375  dec     rbx
0x18002d378  cmp     rbx, r14
0x18002d37b  jb      short loc_18002D394
0x18002d37d  lfence
0x18002d380  lea     rdx, Control; " \n\t\r"
0x18002d387  mov     rcx, rbx; Str
0x18002d38a  call    strspn
0x18002d38f  test    rax, rax
0x18002d392  jnz     short loc_18002D372
0x18002d394  sub     rbx, rsi
0x18002d397  mov     [r15], rdi
0x18002d39a  mov     rcx, rsi
0x18002d39d  lea     rdx, [rbx+2]
0x18002d3a1  call    av_realloc
0x18002d3a6  test    rax, rax
0x18002d3a9  cmovnz  rsi, rax
0x18002d3ad  mov     rax, rsi
0x18002d3b0  mov     rbx, [rsp+38h+arg_0]
0x18002d3b5  mov     rbp, [rsp+38h+arg_8]
0x18002d3ba  mov     rsi, [rsp+38h+arg_10]
0x18002d3bf  mov     rdi, [rsp+38h+arg_18]
0x18002d3c4  add     rsp, 20h
0x18002d3c8  pop     r15
0x18002d3ca  pop     r14
0x18002d3cc  pop     r12
0x18002d3ce  retn
```
