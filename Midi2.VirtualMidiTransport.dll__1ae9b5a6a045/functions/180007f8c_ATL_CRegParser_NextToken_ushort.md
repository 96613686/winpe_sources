# ATL::CRegParser::NextToken(ushort *)

- ea: `0x180007f8c`
- end: `0x180008123`
- name: `?NextToken@CRegParser@ATL@@IEAAJPEAG@Z`
- size: `407`
- prototype: `__int64 __fastcall(ATL::CRegParser *__hidden this, unsigned __int16 *)`
- caller_count: `4`
- callee_count: `1`
- tags: ``

## callers

- `0x180005f60`
- `0x18000878c`
- `0x180008afc`
- `0x18000a060`

## callees

- `0x180007f8c`

## import_xrefs

- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x180007fc1`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x180007fef`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x18000800f`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x180008027`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x180008036`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x1800080a1`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x1800080c6`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x180007fc1`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x180007fef`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x18000800f`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x180008027`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x180008036`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x1800080a1`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x1800080c6`

## pseudocode

```c
__int64 __fastcall ATL::CRegParser::NextToken(LPCWSTR *this, unsigned __int16 *a2)
{
  const WCHAR *v4; // rsi
  WCHAR v5; // cx
  unsigned __int16 *v6; // rbp
  LPWSTR v7; // rax
  const WCHAR *v8; // rcx
  __int16 v9; // dx
  const WCHAR *v10; // rsi
  LPWSTR v11; // rax
  __int64 v12; // rdx
  int j; // ecx
  int v15; // ecx
  int v16; // ecx
  int v17; // ecx
  LPWSTR v18; // rax
  __int64 v19; // rdx
  int i; // ecx

  while ( 1 )
  {
    v4 = *this;
    v5 = **this;
    if ( v5 != 9 && **this != 10 && **this != 13 && **this != 32 )
      break;
    *this = CharNextW(*this);
  }
  if ( !v5 )
    return 2147614729LL;
  v6 = a2 + 4096;
  if ( v5 != 39 )
  {
    while ( 1 )
    {
      v15 = v5 - 9;
      if ( !v15 )
        break;
      v16 = v15 - 1;
      if ( !v16 )
        break;
      v17 = v16 - 3;
      if ( !v17 || v17 == 19 )
        break;
      v18 = CharNextW(v4);
      *this = v18;
      v19 = v18 - v4;
      if ( &a2[v19 + 1] >= v6 )
        return 2147614729LL;
      for ( i = 0; i < (int)v19; ++a2 )
      {
        ++i;
        *a2 = *v4++;
      }
      v4 = *this;
      if ( !**this )
        break;
      v5 = *v4;
    }
    if ( a2 < v6 )
    {
      *a2 = 0;
      return 0;
    }
    return 2147614729LL;
  }
  v7 = CharNextW(*this);
  *this = v7;
  v8 = v7;
  v9 = *v7;
  if ( *v7 )
  {
    while ( v9 != 39 || *CharNextW(v8) == 39 )
    {
      v10 = *this;
      if ( **this == 39 )
      {
        v10 = CharNextW(*this);
        *this = v10;
      }
      v11 = CharNextW(v10);
      *this = v11;
      v12 = v11 - v10;
      if ( &a2[v12 + 1] < v6 )
      {
        for ( j = 0; j < (int)v12; ++a2 )
        {
          ++j;
          *a2 = *v10++;
        }
        v8 = *this;
        v9 = **this;
        if ( v9 )
          continue;
      }
      return 2147614729LL;
    }
  }
  if ( !**this || a2 >= v6 )
    return 2147614729LL;
  *a2 = 0;
  *this = CharNextW(*this);
  return 0;
}

```

## disassembly

```asm
0x180007f8c  push    rbx
0x180007f8e  push    rbp
0x180007f8f  push    rsi
0x180007f90  push    rdi
0x180007f91  push    r14
0x180007f93  sub     rsp, 20h
0x180007f97  mov     rbx, rdx
0x180007f9a  mov     rdi, rcx
0x180007f9d  mov     rsi, [rdi]
0x180007fa0  movzx   ecx, word ptr [rsi]
0x180007fa3  mov     r8d, ecx
0x180007fa6  sub     r8d, 9
0x180007faa  jz      short loc_180007FBE
0x180007fac  sub     r8d, 1
0x180007fb0  jz      short loc_180007FBE
0x180007fb2  sub     r8d, 3
0x180007fb6  jz      short loc_180007FBE
0x180007fb8  cmp     r8d, 13h
0x180007fbc  jnz     short loc_180007FCC
0x180007fbe  mov     rcx, rsi; lpsz
0x180007fc1  call    cs:__imp_CharNextW
0x180007fc7  mov     [rdi], rax
0x180007fca  jmp     short loc_180007F9D
0x180007fcc  xor     eax, eax
0x180007fce  cmp     ax, cx
0x180007fd1  jz      loc_18000807C
0x180007fd7  lea     r14d, [rax+27h]
0x180007fdb  lea     rbp, [rbx+2000h]
0x180007fe2  cmp     r14w, cx
0x180007fe6  jnz     loc_1800080AC
0x180007fec  mov     rcx, rsi; lpsz
0x180007fef  call    cs:__imp_CharNextW
0x180007ff5  mov     [rdi], rax
0x180007ff8  mov     rcx, rax; lpsz
0x180007ffb  movzx   edx, word ptr [rax]
0x180007ffe  xor     eax, eax
0x180008000  cmp     ax, dx
0x180008003  jz      loc_18000808C
0x180008009  cmp     r14w, dx
0x18000800d  jnz     short loc_18000801B
0x18000800f  call    cs:__imp_CharNextW
0x180008015  cmp     r14w, [rax]
0x180008019  jnz     short loc_18000808C
0x18000801b  mov     rsi, [rdi]
0x18000801e  cmp     r14w, [rsi]
0x180008022  jnz     short loc_180008033
0x180008024  mov     rcx, rsi; lpsz
0x180008027  call    cs:__imp_CharNextW
0x18000802d  mov     rsi, rax
0x180008030  mov     [rdi], rax
0x180008033  mov     rcx, rsi; lpsz
0x180008036  call    cs:__imp_CharNextW
0x18000803c  mov     rdx, rax
0x18000803f  mov     [rdi], rax
0x180008042  sub     rdx, rsi
0x180008045  sar     rdx, 1
0x180008048  lea     rcx, [rdx+1]
0x18000804c  lea     rcx, [rbx+rcx*2]
0x180008050  cmp     rcx, rbp
0x180008053  jnb     short loc_18000807C
0x180008055  xor     ecx, ecx
0x180008057  test    edx, edx
0x180008059  jle     short loc_18000806F
0x18000805b  movzx   eax, word ptr [rsi]
0x18000805e  inc     ecx
0x180008060  mov     [rbx], ax
0x180008063  lea     rsi, [rsi+2]
0x180008067  add     rbx, 2
0x18000806b  cmp     ecx, edx
0x18000806d  jl      short loc_18000805B
0x18000806f  mov     rcx, [rdi]
0x180008072  xor     eax, eax
0x180008074  movzx   edx, word ptr [rcx]
0x180008077  cmp     ax, dx
0x18000807a  jnz     short loc_180008009
0x18000807c  mov     eax, 80020009h
0x180008081  add     rsp, 20h
0x180008085  pop     r14
0x180008087  pop     rdi
0x180008088  pop     rsi
0x180008089  pop     rbp
0x18000808a  pop     rbx
0x18000808b  retn
0x18000808c  mov     rcx, [rdi]
0x18000808f  xor     eax, eax
0x180008091  cmp     ax, [rcx]
0x180008094  jz      short loc_18000807C
0x180008096  cmp     rbx, rbp
0x180008099  jnb     short loc_18000807C
0x18000809b  mov     [rbx], ax
0x18000809e  mov     rcx, [rdi]; lpsz
0x1800080a1  call    cs:__imp_CharNextW
0x1800080a7  mov     [rdi], rax
0x1800080aa  jmp     short loc_18000811C
0x1800080ac  movzx   ecx, cx
0x1800080af  sub     ecx, 9
0x1800080b2  jz      short loc_18000810E
0x1800080b4  sub     ecx, 1
0x1800080b7  jz      short loc_18000810E
0x1800080b9  sub     ecx, 3
0x1800080bc  jz      short loc_18000810E
0x1800080be  cmp     ecx, 13h
0x1800080c1  jz      short loc_18000810E
0x1800080c3  mov     rcx, rsi; lpsz
0x1800080c6  call    cs:__imp_CharNextW
0x1800080cc  mov     rdx, rax
0x1800080cf  mov     [rdi], rax
0x1800080d2  sub     rdx, rsi
0x1800080d5  sar     rdx, 1
0x1800080d8  lea     rcx, [rdx+1]
0x1800080dc  lea     rcx, [rbx+rcx*2]
0x1800080e0  cmp     rcx, rbp
0x1800080e3  jnb     short loc_18000807C
0x1800080e5  xor     ecx, ecx
0x1800080e7  test    edx, edx
0x1800080e9  jle     short loc_1800080FF
0x1800080eb  movzx   eax, word ptr [rsi]
0x1800080ee  inc     ecx
0x1800080f0  mov     [rbx], ax
0x1800080f3  lea     rsi, [rsi+2]
0x1800080f7  add     rbx, 2
0x1800080fb  cmp     ecx, edx
0x1800080fd  jl      short loc_1800080EB
0x1800080ff  mov     rsi, [rdi]
0x180008102  xor     eax, eax
0x180008104  cmp     ax, [rsi]
0x180008107  jz      short loc_18000810E
0x180008109  movzx   ecx, word ptr [rsi]
0x18000810c  jmp     short loc_1800080AC
0x18000810e  cmp     rbx, rbp
0x180008111  jnb     loc_18000807C
0x180008117  xor     eax, eax
0x180008119  mov     [rbx], ax
0x18000811c  xor     eax, eax
0x18000811e  jmp     loc_180008081
```
