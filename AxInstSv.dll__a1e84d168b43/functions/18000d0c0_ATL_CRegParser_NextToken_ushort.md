# ATL::CRegParser::NextToken(ushort *)

- ea: `0x18000d0c0`
- end: `0x18000d217`
- name: `?NextToken@CRegParser@ATL@@IEAAJPEAG@Z`
- size: `343`
- prototype: `__int64 __fastcall(ATL::CRegParser *__hidden this, unsigned __int16 *)`
- caller_count: `4`
- callee_count: `2`
- tags: ``

## callers

- `0x1800096cc`
- `0x18000e458`
- `0x18000e810`
- `0x18000fb80`

## callees

- `0x18000d0c0`
- `0x18000fcd4`

## import_xrefs

- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x18000d0f9`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x18000d112`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x18000d12a`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x18000d139`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x18000d191`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x18000d1c0`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x18000d0f9`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x18000d112`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x18000d12a`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x18000d139`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x18000d191`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x18000d1c0`

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
0x18000d0c0  push    rbx
0x18000d0c2  push    rbp
0x18000d0c3  push    rsi
0x18000d0c4  push    rdi
0x18000d0c5  push    r14
0x18000d0c7  sub     rsp, 20h
0x18000d0cb  mov     rbx, rdx
0x18000d0ce  mov     rdi, rcx
0x18000d0d1  call    ?SkipWhiteSpace@CRegParser@ATL@@IEAAXXZ; ATL::CRegParser::SkipWhiteSpace(void)
0x18000d0d6  mov     rcx, [rdi]; lpsz
0x18000d0d9  xor     eax, eax
0x18000d0db  cmp     ax, [rcx]
0x18000d0de  jz      loc_18000D207
0x18000d0e4  lea     r14d, [rax+27h]
0x18000d0e8  lea     rbp, [rbx+2000h]
0x18000d0ef  cmp     r14w, [rcx]
0x18000d0f3  jnz     loc_18000D19C
0x18000d0f9  call    cs:__imp_CharNextW
0x18000d0ff  mov     [rdi], rax
0x18000d102  mov     rcx, [rdi]; lpsz
0x18000d105  xor     eax, eax
0x18000d107  cmp     ax, [rcx]
0x18000d10a  jz      short loc_18000D178
0x18000d10c  cmp     r14w, [rcx]
0x18000d110  jnz     short loc_18000D11E
0x18000d112  call    cs:__imp_CharNextW
0x18000d118  cmp     r14w, [rax]
0x18000d11c  jnz     short loc_18000D178
0x18000d11e  mov     rsi, [rdi]
0x18000d121  cmp     r14w, [rsi]
0x18000d125  jnz     short loc_18000D136
0x18000d127  mov     rcx, rsi; lpsz
0x18000d12a  call    cs:__imp_CharNextW
0x18000d130  mov     rsi, rax
0x18000d133  mov     [rdi], rax
0x18000d136  mov     rcx, rsi; lpsz
0x18000d139  call    cs:__imp_CharNextW
0x18000d13f  mov     rdx, rax
0x18000d142  mov     [rdi], rax
0x18000d145  sub     rdx, rsi
0x18000d148  sar     rdx, 1
0x18000d14b  lea     rcx, [rdx+1]
0x18000d14f  lea     rcx, [rbx+rcx*2]
0x18000d153  cmp     rcx, rbp
0x18000d156  jnb     loc_18000D207
0x18000d15c  xor     ecx, ecx
0x18000d15e  test    edx, edx
0x18000d160  jle     short loc_18000D102
0x18000d162  movzx   eax, word ptr [rsi]
0x18000d165  inc     ecx
0x18000d167  mov     [rbx], ax
0x18000d16a  lea     rsi, [rsi+2]
0x18000d16e  add     rbx, 2
0x18000d172  cmp     ecx, edx
0x18000d174  jl      short loc_18000D162
0x18000d176  jmp     short loc_18000D102
0x18000d178  mov     rcx, [rdi]
0x18000d17b  xor     eax, eax
0x18000d17d  cmp     ax, [rcx]
0x18000d180  jz      loc_18000D207
0x18000d186  cmp     rbx, rbp
0x18000d189  jnb     short loc_18000D207
0x18000d18b  mov     [rbx], ax
0x18000d18e  mov     rcx, [rdi]; lpsz
0x18000d191  call    cs:__imp_CharNextW
0x18000d197  mov     [rdi], rax
0x18000d19a  jmp     short loc_18000D203
0x18000d19c  mov     rsi, [rdi]
0x18000d19f  xor     eax, eax
0x18000d1a1  cmp     ax, [rsi]
0x18000d1a4  jz      short loc_18000D1FB
0x18000d1a6  movzx   ecx, word ptr [rsi]
0x18000d1a9  sub     ecx, 9
0x18000d1ac  jz      short loc_18000D1FB
0x18000d1ae  sub     ecx, 1
0x18000d1b1  jz      short loc_18000D1FB
0x18000d1b3  sub     ecx, 3
0x18000d1b6  jz      short loc_18000D1FB
0x18000d1b8  cmp     ecx, 13h
0x18000d1bb  jz      short loc_18000D1FB
0x18000d1bd  mov     rcx, rsi; lpsz
0x18000d1c0  call    cs:__imp_CharNextW
0x18000d1c6  mov     rdx, rax
0x18000d1c9  mov     [rdi], rax
0x18000d1cc  sub     rdx, rsi
0x18000d1cf  sar     rdx, 1
0x18000d1d2  lea     rcx, [rdx+1]
0x18000d1d6  lea     rcx, [rbx+rcx*2]
0x18000d1da  cmp     rcx, rbp
0x18000d1dd  jnb     short loc_18000D207
0x18000d1df  xor     ecx, ecx
0x18000d1e1  test    edx, edx
0x18000d1e3  jle     short loc_18000D19C
0x18000d1e5  movzx   eax, word ptr [rsi]
0x18000d1e8  inc     ecx
0x18000d1ea  mov     [rbx], ax
0x18000d1ed  lea     rsi, [rsi+2]
0x18000d1f1  add     rbx, 2
0x18000d1f5  cmp     ecx, edx
0x18000d1f7  jl      short loc_18000D1E5
0x18000d1f9  jmp     short loc_18000D19C
0x18000d1fb  cmp     rbx, rbp
0x18000d1fe  jnb     short loc_18000D207
0x18000d200  mov     [rbx], ax
0x18000d203  xor     eax, eax
0x18000d205  jmp     short loc_18000D20C
0x18000d207  mov     eax, 80020009h
0x18000d20c  add     rsp, 20h
0x18000d210  pop     r14
0x18000d212  pop     rdi
0x18000d213  pop     rsi
0x18000d214  pop     rbp
0x18000d215  pop     rbx
0x18000d216  retn
```
