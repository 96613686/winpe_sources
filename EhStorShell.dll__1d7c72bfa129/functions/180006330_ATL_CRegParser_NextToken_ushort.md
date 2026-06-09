# ATL::CRegParser::NextToken(ushort *)

- ea: `0x180006330`
- end: `0x180006487`
- name: `?NextToken@CRegParser@ATL@@IEAAJPEAG@Z`
- size: `343`
- prototype: `__int64 __fastcall(ATL::CRegParser *__hidden this, unsigned __int16 *)`
- caller_count: `4`
- callee_count: `2`
- tags: ``

## callers

- `0x180004fb8`
- `0x18000662c`
- `0x180007f20`
- `0x180008e9c`

## callees

- `0x180006330`
- `0x180006490`

## import_xrefs

- `USER32!CharNextW` at `0x180006369`
- `USER32!CharNextW` at `0x180006382`
- `USER32!CharNextW` at `0x18000639a`
- `USER32!CharNextW` at `0x1800063a9`
- `USER32!CharNextW` at `0x180006401`
- `USER32!CharNextW` at `0x180006430`
- `USER32!CharNextW` at `0x180006369`
- `USER32!CharNextW` at `0x180006382`
- `USER32!CharNextW` at `0x18000639a`
- `USER32!CharNextW` at `0x1800063a9`
- `USER32!CharNextW` at `0x180006401`
- `USER32!CharNextW` at `0x180006430`

## pseudocode

```c
__int64 __fastcall ATL::CRegParser::NextToken(ATL::CRegParser *this, unsigned __int16 *a2)
{
  const WCHAR *v4; // rcx
  unsigned __int16 *v5; // rbp
  const WCHAR *v6; // rcx
  const WCHAR *v7; // rsi
  LPWSTR v8; // rax
  __int64 v9; // rdx
  int i; // ecx
  unsigned __int16 *v11; // rsi
  LPWSTR v12; // rax
  __int64 v13; // rdx
  int j; // ecx

  ATL::CRegParser::SkipWhiteSpace(this);
  v4 = *(const WCHAR **)this;
  if ( **(_WORD **)this )
  {
    v5 = a2 + 4096;
    if ( *v4 == 39 )
    {
      *(_QWORD *)this = CharNextW(v4);
      while ( 1 )
      {
        v6 = *(const WCHAR **)this;
        if ( !**(_WORD **)this || *v6 == 39 && *CharNextW(v6) != 39 )
          break;
        v7 = *(const WCHAR **)this;
        if ( **(_WORD **)this == 39 )
        {
          v7 = CharNextW(*(LPCWSTR *)this);
          *(_QWORD *)this = v7;
        }
        v8 = CharNextW(v7);
        *(_QWORD *)this = v8;
        v9 = v8 - v7;
        if ( &a2[v9 + 1] >= v5 )
          return 2147614729LL;
        for ( i = 0; i < (int)v9; ++a2 )
        {
          ++i;
          *a2 = *v7++;
        }
      }
      if ( **(_WORD **)this && a2 < v5 )
      {
        *a2 = 0;
        *(_QWORD *)this = CharNextW(*(LPCWSTR *)this);
        return 0;
      }
    }
    else
    {
      while ( 1 )
      {
        v11 = *(unsigned __int16 **)this;
        if ( !**(_WORD **)this || *v11 == 9 || *v11 == 10 || *v11 == 13 || *v11 == 32 )
          break;
        v12 = CharNextW(*(LPCWSTR *)this);
        *(_QWORD *)this = v12;
        v13 = v12 - v11;
        if ( &a2[v13 + 1] >= v5 )
          return 2147614729LL;
        for ( j = 0; j < (int)v13; ++a2 )
        {
          ++j;
          *a2 = *v11++;
        }
      }
      if ( a2 < v5 )
      {
        *a2 = 0;
        return 0;
      }
    }
  }
  return 2147614729LL;
}

```

## disassembly

```asm
0x180006330  push    rbx
0x180006332  push    rbp
0x180006333  push    rsi
0x180006334  push    rdi
0x180006335  push    r14
0x180006337  sub     rsp, 20h
0x18000633b  mov     rbx, rdx
0x18000633e  mov     rdi, rcx
0x180006341  call    ?SkipWhiteSpace@CRegParser@ATL@@IEAAXXZ; ATL::CRegParser::SkipWhiteSpace(void)
0x180006346  mov     rcx, [rdi]; lpsz
0x180006349  xor     eax, eax
0x18000634b  cmp     ax, [rcx]
0x18000634e  jz      loc_180006477
0x180006354  lea     r14d, [rax+27h]
0x180006358  lea     rbp, [rbx+2000h]
0x18000635f  cmp     r14w, [rcx]
0x180006363  jnz     loc_18000640C
0x180006369  call    cs:__imp_CharNextW
0x18000636f  mov     [rdi], rax
0x180006372  mov     rcx, [rdi]; lpsz
0x180006375  xor     eax, eax
0x180006377  cmp     ax, [rcx]
0x18000637a  jz      short loc_1800063E8
0x18000637c  cmp     r14w, [rcx]
0x180006380  jnz     short loc_18000638E
0x180006382  call    cs:__imp_CharNextW
0x180006388  cmp     r14w, [rax]
0x18000638c  jnz     short loc_1800063E8
0x18000638e  mov     rsi, [rdi]
0x180006391  cmp     r14w, [rsi]
0x180006395  jnz     short loc_1800063A6
0x180006397  mov     rcx, rsi; lpsz
0x18000639a  call    cs:__imp_CharNextW
0x1800063a0  mov     rsi, rax
0x1800063a3  mov     [rdi], rax
0x1800063a6  mov     rcx, rsi; lpsz
0x1800063a9  call    cs:__imp_CharNextW
0x1800063af  mov     rdx, rax
0x1800063b2  mov     [rdi], rax
0x1800063b5  sub     rdx, rsi
0x1800063b8  sar     rdx, 1
0x1800063bb  lea     rcx, [rdx+1]
0x1800063bf  lea     rcx, [rbx+rcx*2]
0x1800063c3  cmp     rcx, rbp
0x1800063c6  jnb     loc_180006477
0x1800063cc  xor     ecx, ecx
0x1800063ce  test    edx, edx
0x1800063d0  jle     short loc_180006372
0x1800063d2  movzx   eax, word ptr [rsi]
0x1800063d5  inc     ecx
0x1800063d7  mov     [rbx], ax
0x1800063da  lea     rsi, [rsi+2]
0x1800063de  add     rbx, 2
0x1800063e2  cmp     ecx, edx
0x1800063e4  jl      short loc_1800063D2
0x1800063e6  jmp     short loc_180006372
0x1800063e8  mov     rcx, [rdi]
0x1800063eb  xor     eax, eax
0x1800063ed  cmp     ax, [rcx]
0x1800063f0  jz      loc_180006477
0x1800063f6  cmp     rbx, rbp
0x1800063f9  jnb     short loc_180006477
0x1800063fb  mov     [rbx], ax
0x1800063fe  mov     rcx, [rdi]; lpsz
0x180006401  call    cs:__imp_CharNextW
0x180006407  mov     [rdi], rax
0x18000640a  jmp     short loc_180006473
0x18000640c  mov     rsi, [rdi]
0x18000640f  xor     eax, eax
0x180006411  cmp     ax, [rsi]
0x180006414  jz      short loc_18000646B
0x180006416  movzx   ecx, word ptr [rsi]
0x180006419  sub     ecx, 9
0x18000641c  jz      short loc_18000646B
0x18000641e  sub     ecx, 1
0x180006421  jz      short loc_18000646B
0x180006423  sub     ecx, 3
0x180006426  jz      short loc_18000646B
0x180006428  cmp     ecx, 13h
0x18000642b  jz      short loc_18000646B
0x18000642d  mov     rcx, rsi; lpsz
0x180006430  call    cs:__imp_CharNextW
0x180006436  mov     rdx, rax
0x180006439  mov     [rdi], rax
0x18000643c  sub     rdx, rsi
0x18000643f  sar     rdx, 1
0x180006442  lea     rcx, [rdx+1]
0x180006446  lea     rcx, [rbx+rcx*2]
0x18000644a  cmp     rcx, rbp
0x18000644d  jnb     short loc_180006477
0x18000644f  xor     ecx, ecx
0x180006451  test    edx, edx
0x180006453  jle     short loc_18000640C
0x180006455  movzx   eax, word ptr [rsi]
0x180006458  inc     ecx
0x18000645a  mov     [rbx], ax
0x18000645d  lea     rsi, [rsi+2]
0x180006461  add     rbx, 2
0x180006465  cmp     ecx, edx
0x180006467  jl      short loc_180006455
0x180006469  jmp     short loc_18000640C
0x18000646b  cmp     rbx, rbp
0x18000646e  jnb     short loc_180006477
0x180006470  mov     [rbx], ax
0x180006473  xor     eax, eax
0x180006475  jmp     short loc_18000647C
0x180006477  mov     eax, 80020009h
0x18000647c  add     rsp, 20h
0x180006480  pop     r14
0x180006482  pop     rdi
0x180006483  pop     rsi
0x180006484  pop     rbp
0x180006485  pop     rbx
0x180006486  retn
```
