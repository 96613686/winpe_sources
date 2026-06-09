# ATL::CRegParser::NextToken(char *)

- ea: `0x1800048d0`
- end: `0x180004a32`
- name: `?NextToken@CRegParser@ATL@@IEAAJPEAD@Z`
- size: `354`
- prototype: `__int64 __fastcall(ATL::CRegParser *__hidden this, char *)`
- caller_count: `4`
- callee_count: `1`
- tags: ``

## callers

- `0x180002e4c`
- `0x180004f3c`
- `0x180005408`
- `0x18000640c`

## callees

- `0x1800048d0`

## import_xrefs

- `USER32!CharNextA` at `0x180004903`
- `USER32!CharNextA` at `0x180004929`
- `USER32!CharNextA` at `0x180004940`
- `USER32!CharNextA` at `0x180004956`
- `USER32!CharNextA` at `0x180004965`
- `USER32!CharNextA` at `0x1800049c0`
- `USER32!CharNextA` at `0x1800049e5`
- `USER32!CharNextA` at `0x180004903`
- `USER32!CharNextA` at `0x180004929`
- `USER32!CharNextA` at `0x180004940`
- `USER32!CharNextA` at `0x180004956`
- `USER32!CharNextA` at `0x180004965`
- `USER32!CharNextA` at `0x1800049c0`
- `USER32!CharNextA` at `0x1800049e5`

## pseudocode

```c
__int64 __fastcall ATL::CRegParser::NextToken(LPCSTR *this, char *a2)
{
  const CHAR *v4; // rsi
  CHAR v5; // cl
  char *v6; // rbp
  LPSTR v7; // rax
  CHAR v8; // cl
  const CHAR *v9; // rsi
  LPSTR v10; // rax
  int v11; // edx
  int j; // ecx
  int v14; // ecx
  int v15; // ecx
  int v16; // ecx
  LPSTR v17; // rax
  int v18; // edx
  int i; // ecx

  while ( 1 )
  {
    v4 = *this;
    v5 = **this;
    if ( v5 != 9 && **this != 10 && **this != 13 && **this != 32 )
      break;
    *this = CharNextA(*this);
  }
  if ( !v5 )
    return 2147614729LL;
  v6 = a2 + 4096;
  if ( v5 != 39 )
  {
    do
    {
      v14 = v5 - 9;
      if ( !v14 )
        break;
      v15 = v14 - 1;
      if ( !v15 )
        break;
      v16 = v15 - 3;
      if ( !v16 || v16 == 19 )
        break;
      v17 = CharNextA(v4);
      *this = v17;
      v18 = (_DWORD)v17 - (_DWORD)v4;
      if ( &a2[v17 - v4 + 1] >= v6 )
        return 2147614729LL;
      for ( i = 0; i < v18; ++a2 )
      {
        ++i;
        *a2 = *v4++;
      }
      v4 = *this;
      v5 = **this;
    }
    while ( v5 );
    if ( a2 < v6 )
    {
      *a2 = 0;
      return 0;
    }
    return 2147614729LL;
  }
  v7 = CharNextA(*this);
  *this = v7;
  v8 = *v7;
  if ( *v7 )
  {
    while ( v8 != 39 || *CharNextA(v7) == 39 )
    {
      v9 = *this;
      if ( **this == 39 )
      {
        v9 = CharNextA(*this);
        *this = v9;
      }
      v10 = CharNextA(v9);
      *this = v10;
      v11 = (_DWORD)v10 - (_DWORD)v9;
      if ( &a2[v10 - v9 + 1] < v6 )
      {
        for ( j = 0; j < v11; ++a2 )
        {
          ++j;
          *a2 = *v9++;
        }
        v7 = (LPSTR)*this;
        v8 = **this;
        if ( v8 )
          continue;
      }
      return 2147614729LL;
    }
  }
  if ( !**this || a2 >= v6 )
    return 2147614729LL;
  *a2 = 0;
  *this = CharNextA(*this);
  return 0;
}

```

## disassembly

```asm
0x1800048d0  push    rbx
0x1800048d2  push    rbp
0x1800048d3  push    rsi
0x1800048d4  push    rdi
0x1800048d5  sub     rsp, 28h
0x1800048d9  mov     rbx, rdx
0x1800048dc  mov     rdi, rcx
0x1800048df  mov     rsi, [rdi]
0x1800048e2  movsx   ecx, byte ptr [rsi]
0x1800048e5  mov     r8d, ecx
0x1800048e8  sub     r8d, 9
0x1800048ec  jz      short loc_180004900
0x1800048ee  sub     r8d, 1
0x1800048f2  jz      short loc_180004900
0x1800048f4  sub     r8d, 3
0x1800048f8  jz      short loc_180004900
0x1800048fa  cmp     r8d, 13h
0x1800048fe  jnz     short loc_18000490E
0x180004900  mov     rcx, rsi; lpsz
0x180004903  call    cs:__imp_CharNextA
0x180004909  mov     [rdi], rax
0x18000490c  jmp     short loc_1800048DF
0x18000490e  test    cl, cl
0x180004910  jz      loc_18000499F
0x180004916  lea     rbp, [rbx+1000h]
0x18000491d  cmp     cl, 27h ; '''
0x180004920  jnz     loc_1800049CB
0x180004926  mov     rcx, rsi; lpsz
0x180004929  call    cs:__imp_CharNextA
0x18000492f  mov     [rdi], rax
0x180004932  mov     cl, [rax]
0x180004934  test    cl, cl
0x180004936  jz      short loc_1800049AD
0x180004938  cmp     cl, 27h ; '''
0x18000493b  jnz     short loc_18000494B
0x18000493d  mov     rcx, rax; lpsz
0x180004940  call    cs:__imp_CharNextA
0x180004946  cmp     byte ptr [rax], 27h ; '''
0x180004949  jnz     short loc_1800049AD
0x18000494b  mov     rsi, [rdi]
0x18000494e  cmp     byte ptr [rsi], 27h ; '''
0x180004951  jnz     short loc_180004962
0x180004953  mov     rcx, rsi; lpsz
0x180004956  call    cs:__imp_CharNextA
0x18000495c  mov     rsi, rax
0x18000495f  mov     [rdi], rax
0x180004962  mov     rcx, rsi; lpsz
0x180004965  call    cs:__imp_CharNextA
0x18000496b  mov     rdx, rax
0x18000496e  mov     [rdi], rax
0x180004971  sub     rdx, rsi
0x180004974  lea     rcx, [rdx+1]
0x180004978  add     rcx, rbx
0x18000497b  cmp     rcx, rbp
0x18000497e  jnb     short loc_18000499F
0x180004980  xor     ecx, ecx
0x180004982  test    edx, edx
0x180004984  jle     short loc_180004996
0x180004986  mov     al, [rsi]
0x180004988  inc     ecx
0x18000498a  mov     [rbx], al
0x18000498c  inc     rsi
0x18000498f  inc     rbx
0x180004992  cmp     ecx, edx
0x180004994  jl      short loc_180004986
0x180004996  mov     rax, [rdi]
0x180004999  mov     cl, [rax]
0x18000499b  test    cl, cl
0x18000499d  jnz     short loc_180004938
0x18000499f  mov     eax, 80020009h
0x1800049a4  add     rsp, 28h
0x1800049a8  pop     rdi
0x1800049a9  pop     rsi
0x1800049aa  pop     rbp
0x1800049ab  pop     rbx
0x1800049ac  retn
0x1800049ad  mov     rax, [rdi]
0x1800049b0  cmp     byte ptr [rax], 0
0x1800049b3  jz      short loc_18000499F
0x1800049b5  cmp     rbx, rbp
0x1800049b8  jnb     short loc_18000499F
0x1800049ba  mov     byte ptr [rbx], 0
0x1800049bd  mov     rcx, [rdi]; lpsz
0x1800049c0  call    cs:__imp_CharNextA
0x1800049c6  mov     [rdi], rax
0x1800049c9  jmp     short loc_180004A2B
0x1800049cb  movsx   ecx, cl
0x1800049ce  sub     ecx, 9
0x1800049d1  jz      short loc_180004A1F
0x1800049d3  sub     ecx, 1
0x1800049d6  jz      short loc_180004A1F
0x1800049d8  sub     ecx, 3
0x1800049db  jz      short loc_180004A1F
0x1800049dd  cmp     ecx, 13h
0x1800049e0  jz      short loc_180004A1F
0x1800049e2  mov     rcx, rsi; lpsz
0x1800049e5  call    cs:__imp_CharNextA
0x1800049eb  mov     rdx, rax
0x1800049ee  mov     [rdi], rax
0x1800049f1  sub     rdx, rsi
0x1800049f4  lea     rcx, [rdx+1]
0x1800049f8  add     rcx, rbx
0x1800049fb  cmp     rcx, rbp
0x1800049fe  jnb     short loc_18000499F
0x180004a00  xor     ecx, ecx
0x180004a02  test    edx, edx
0x180004a04  jle     short loc_180004A16
0x180004a06  mov     al, [rsi]
0x180004a08  inc     ecx
0x180004a0a  mov     [rbx], al
0x180004a0c  inc     rsi
0x180004a0f  inc     rbx
0x180004a12  cmp     ecx, edx
0x180004a14  jl      short loc_180004A06
0x180004a16  mov     rsi, [rdi]
0x180004a19  mov     cl, [rsi]
0x180004a1b  test    cl, cl
0x180004a1d  jnz     short loc_1800049CB
0x180004a1f  cmp     rbx, rbp
0x180004a22  jnb     loc_18000499F
0x180004a28  mov     byte ptr [rbx], 0
0x180004a2b  xor     eax, eax
0x180004a2d  jmp     loc_1800049A4
```
