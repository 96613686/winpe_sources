# ATL::CRegParser::NextToken(ushort *)

- ea: `0x180018bfc`
- end: `0x180018d53`
- name: `?NextToken@CRegParser@ATL@@IEAAJPEAG@Z`
- size: `343`
- prototype: `__int64 __fastcall(ATL::CRegParser *__hidden this, unsigned __int16 *)`
- caller_count: `4`
- callee_count: `2`
- tags: ``

## callers

- `0x180017adc`
- `0x18001916c`
- `0x180019528`
- `0x180019c24`

## callees

- `0x180018bfc`
- `0x180019cb8`

## import_xrefs

- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x180018c35`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x180018c4e`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x180018c66`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x180018c75`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x180018ccd`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x180018cfc`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x180018c35`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x180018c4e`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x180018c66`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x180018c75`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x180018ccd`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x180018cfc`

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
0x180018bfc  push    rbx
0x180018bfe  push    rbp
0x180018bff  push    rsi
0x180018c00  push    rdi
0x180018c01  push    r14
0x180018c03  sub     rsp, 20h
0x180018c07  mov     rbx, rdx
0x180018c0a  mov     rdi, rcx
0x180018c0d  call    ?SkipWhiteSpace@CRegParser@ATL@@IEAAXXZ; ATL::CRegParser::SkipWhiteSpace(void)
0x180018c12  mov     rcx, [rdi]; lpsz
0x180018c15  xor     eax, eax
0x180018c17  cmp     ax, [rcx]
0x180018c1a  jz      loc_180018D43
0x180018c20  lea     r14d, [rax+27h]
0x180018c24  lea     rbp, [rbx+2000h]
0x180018c2b  cmp     r14w, [rcx]
0x180018c2f  jnz     loc_180018CD8
0x180018c35  call    cs:__imp_CharNextW
0x180018c3b  mov     [rdi], rax
0x180018c3e  mov     rcx, [rdi]; lpsz
0x180018c41  xor     eax, eax
0x180018c43  cmp     ax, [rcx]
0x180018c46  jz      short loc_180018CB4
0x180018c48  cmp     r14w, [rcx]
0x180018c4c  jnz     short loc_180018C5A
0x180018c4e  call    cs:__imp_CharNextW
0x180018c54  cmp     r14w, [rax]
0x180018c58  jnz     short loc_180018CB4
0x180018c5a  mov     rsi, [rdi]
0x180018c5d  cmp     r14w, [rsi]
0x180018c61  jnz     short loc_180018C72
0x180018c63  mov     rcx, rsi; lpsz
0x180018c66  call    cs:__imp_CharNextW
0x180018c6c  mov     rsi, rax
0x180018c6f  mov     [rdi], rax
0x180018c72  mov     rcx, rsi; lpsz
0x180018c75  call    cs:__imp_CharNextW
0x180018c7b  mov     rdx, rax
0x180018c7e  mov     [rdi], rax
0x180018c81  sub     rdx, rsi
0x180018c84  sar     rdx, 1
0x180018c87  lea     rcx, [rdx+1]
0x180018c8b  lea     rcx, [rbx+rcx*2]
0x180018c8f  cmp     rcx, rbp
0x180018c92  jnb     loc_180018D43
0x180018c98  xor     ecx, ecx
0x180018c9a  test    edx, edx
0x180018c9c  jle     short loc_180018C3E
0x180018c9e  movzx   eax, word ptr [rsi]
0x180018ca1  inc     ecx
0x180018ca3  mov     [rbx], ax
0x180018ca6  lea     rsi, [rsi+2]
0x180018caa  add     rbx, 2
0x180018cae  cmp     ecx, edx
0x180018cb0  jl      short loc_180018C9E
0x180018cb2  jmp     short loc_180018C3E
0x180018cb4  mov     rcx, [rdi]
0x180018cb7  xor     eax, eax
0x180018cb9  cmp     ax, [rcx]
0x180018cbc  jz      loc_180018D43
0x180018cc2  cmp     rbx, rbp
0x180018cc5  jnb     short loc_180018D43
0x180018cc7  mov     [rbx], ax
0x180018cca  mov     rcx, [rdi]; lpsz
0x180018ccd  call    cs:__imp_CharNextW
0x180018cd3  mov     [rdi], rax
0x180018cd6  jmp     short loc_180018D3F
0x180018cd8  mov     rsi, [rdi]
0x180018cdb  xor     eax, eax
0x180018cdd  cmp     ax, [rsi]
0x180018ce0  jz      short loc_180018D37
0x180018ce2  movzx   ecx, word ptr [rsi]
0x180018ce5  sub     ecx, 9
0x180018ce8  jz      short loc_180018D37
0x180018cea  sub     ecx, 1
0x180018ced  jz      short loc_180018D37
0x180018cef  sub     ecx, 3
0x180018cf2  jz      short loc_180018D37
0x180018cf4  cmp     ecx, 13h
0x180018cf7  jz      short loc_180018D37
0x180018cf9  mov     rcx, rsi; lpsz
0x180018cfc  call    cs:__imp_CharNextW
0x180018d02  mov     rdx, rax
0x180018d05  mov     [rdi], rax
0x180018d08  sub     rdx, rsi
0x180018d0b  sar     rdx, 1
0x180018d0e  lea     rcx, [rdx+1]
0x180018d12  lea     rcx, [rbx+rcx*2]
0x180018d16  cmp     rcx, rbp
0x180018d19  jnb     short loc_180018D43
0x180018d1b  xor     ecx, ecx
0x180018d1d  test    edx, edx
0x180018d1f  jle     short loc_180018CD8
0x180018d21  movzx   eax, word ptr [rsi]
0x180018d24  inc     ecx
0x180018d26  mov     [rbx], ax
0x180018d29  lea     rsi, [rsi+2]
0x180018d2d  add     rbx, 2
0x180018d31  cmp     ecx, edx
0x180018d33  jl      short loc_180018D21
0x180018d35  jmp     short loc_180018CD8
0x180018d37  cmp     rbx, rbp
0x180018d3a  jnb     short loc_180018D43
0x180018d3c  mov     [rbx], ax
0x180018d3f  xor     eax, eax
0x180018d41  jmp     short loc_180018D48
0x180018d43  mov     eax, 80020009h
0x180018d48  add     rsp, 20h
0x180018d4c  pop     r14
0x180018d4e  pop     rdi
0x180018d4f  pop     rsi
0x180018d50  pop     rbp
0x180018d51  pop     rbx
0x180018d52  retn
```
