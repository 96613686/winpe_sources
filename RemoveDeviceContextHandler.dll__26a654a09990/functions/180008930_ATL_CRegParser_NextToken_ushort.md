# ATL::CRegParser::NextToken(ushort *)

- ea: `0x180008930`
- end: `0x180008ac7`
- name: `?NextToken@CRegParser@ATL@@IEAAJPEAG@Z`
- size: `407`
- prototype: `__int64 __fastcall(ATL::CRegParser *__hidden this, unsigned __int16 *)`
- caller_count: `4`
- callee_count: `1`
- tags: ``

## callers

- `0x180006784`
- `0x180009538`
- `0x180009884`
- `0x18000abe0`

## callees

- `0x180008930`

## import_xrefs

- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x180008965`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x180008993`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x1800089b3`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x1800089cb`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x1800089da`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x180008a45`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x180008a6a`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x180008965`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x180008993`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x1800089b3`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x1800089cb`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x1800089da`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x180008a45`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x180008a6a`

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
0x180008930  push    rbx
0x180008932  push    rbp
0x180008933  push    rsi
0x180008934  push    rdi
0x180008935  push    r14
0x180008937  sub     rsp, 20h
0x18000893b  mov     rbx, rdx
0x18000893e  mov     rdi, rcx
0x180008941  mov     rsi, [rdi]
0x180008944  movzx   ecx, word ptr [rsi]
0x180008947  mov     r8d, ecx
0x18000894a  sub     r8d, 9
0x18000894e  jz      short loc_180008962
0x180008950  sub     r8d, 1
0x180008954  jz      short loc_180008962
0x180008956  sub     r8d, 3
0x18000895a  jz      short loc_180008962
0x18000895c  cmp     r8d, 13h
0x180008960  jnz     short loc_180008970
0x180008962  mov     rcx, rsi; lpsz
0x180008965  call    cs:__imp_CharNextW
0x18000896b  mov     [rdi], rax
0x18000896e  jmp     short loc_180008941
0x180008970  xor     eax, eax
0x180008972  cmp     ax, cx
0x180008975  jz      loc_180008A20
0x18000897b  lea     r14d, [rax+27h]
0x18000897f  lea     rbp, [rbx+2000h]
0x180008986  cmp     r14w, cx
0x18000898a  jnz     loc_180008A50
0x180008990  mov     rcx, rsi; lpsz
0x180008993  call    cs:__imp_CharNextW
0x180008999  mov     [rdi], rax
0x18000899c  mov     rcx, rax; lpsz
0x18000899f  movzx   edx, word ptr [rax]
0x1800089a2  xor     eax, eax
0x1800089a4  cmp     ax, dx
0x1800089a7  jz      loc_180008A30
0x1800089ad  cmp     r14w, dx
0x1800089b1  jnz     short loc_1800089BF
0x1800089b3  call    cs:__imp_CharNextW
0x1800089b9  cmp     r14w, [rax]
0x1800089bd  jnz     short loc_180008A30
0x1800089bf  mov     rsi, [rdi]
0x1800089c2  cmp     r14w, [rsi]
0x1800089c6  jnz     short loc_1800089D7
0x1800089c8  mov     rcx, rsi; lpsz
0x1800089cb  call    cs:__imp_CharNextW
0x1800089d1  mov     rsi, rax
0x1800089d4  mov     [rdi], rax
0x1800089d7  mov     rcx, rsi; lpsz
0x1800089da  call    cs:__imp_CharNextW
0x1800089e0  mov     rdx, rax
0x1800089e3  mov     [rdi], rax
0x1800089e6  sub     rdx, rsi
0x1800089e9  sar     rdx, 1
0x1800089ec  lea     rcx, [rdx+1]
0x1800089f0  lea     rcx, [rbx+rcx*2]
0x1800089f4  cmp     rcx, rbp
0x1800089f7  jnb     short loc_180008A20
0x1800089f9  xor     ecx, ecx
0x1800089fb  test    edx, edx
0x1800089fd  jle     short loc_180008A13
0x1800089ff  movzx   eax, word ptr [rsi]
0x180008a02  inc     ecx
0x180008a04  mov     [rbx], ax
0x180008a07  lea     rsi, [rsi+2]
0x180008a0b  add     rbx, 2
0x180008a0f  cmp     ecx, edx
0x180008a11  jl      short loc_1800089FF
0x180008a13  mov     rcx, [rdi]
0x180008a16  xor     eax, eax
0x180008a18  movzx   edx, word ptr [rcx]
0x180008a1b  cmp     ax, dx
0x180008a1e  jnz     short loc_1800089AD
0x180008a20  mov     eax, 80020009h
0x180008a25  add     rsp, 20h
0x180008a29  pop     r14
0x180008a2b  pop     rdi
0x180008a2c  pop     rsi
0x180008a2d  pop     rbp
0x180008a2e  pop     rbx
0x180008a2f  retn
0x180008a30  mov     rcx, [rdi]
0x180008a33  xor     eax, eax
0x180008a35  cmp     ax, [rcx]
0x180008a38  jz      short loc_180008A20
0x180008a3a  cmp     rbx, rbp
0x180008a3d  jnb     short loc_180008A20
0x180008a3f  mov     [rbx], ax
0x180008a42  mov     rcx, [rdi]; lpsz
0x180008a45  call    cs:__imp_CharNextW
0x180008a4b  mov     [rdi], rax
0x180008a4e  jmp     short loc_180008AC0
0x180008a50  movzx   ecx, cx
0x180008a53  sub     ecx, 9
0x180008a56  jz      short loc_180008AB2
0x180008a58  sub     ecx, 1
0x180008a5b  jz      short loc_180008AB2
0x180008a5d  sub     ecx, 3
0x180008a60  jz      short loc_180008AB2
0x180008a62  cmp     ecx, 13h
0x180008a65  jz      short loc_180008AB2
0x180008a67  mov     rcx, rsi; lpsz
0x180008a6a  call    cs:__imp_CharNextW
0x180008a70  mov     rdx, rax
0x180008a73  mov     [rdi], rax
0x180008a76  sub     rdx, rsi
0x180008a79  sar     rdx, 1
0x180008a7c  lea     rcx, [rdx+1]
0x180008a80  lea     rcx, [rbx+rcx*2]
0x180008a84  cmp     rcx, rbp
0x180008a87  jnb     short loc_180008A20
0x180008a89  xor     ecx, ecx
0x180008a8b  test    edx, edx
0x180008a8d  jle     short loc_180008AA3
0x180008a8f  movzx   eax, word ptr [rsi]
0x180008a92  inc     ecx
0x180008a94  mov     [rbx], ax
0x180008a97  lea     rsi, [rsi+2]
0x180008a9b  add     rbx, 2
0x180008a9f  cmp     ecx, edx
0x180008aa1  jl      short loc_180008A8F
0x180008aa3  mov     rsi, [rdi]
0x180008aa6  xor     eax, eax
0x180008aa8  cmp     ax, [rsi]
0x180008aab  jz      short loc_180008AB2
0x180008aad  movzx   ecx, word ptr [rsi]
0x180008ab0  jmp     short loc_180008A50
0x180008ab2  cmp     rbx, rbp
0x180008ab5  jnb     loc_180008A20
0x180008abb  xor     eax, eax
0x180008abd  mov     [rbx], ax
0x180008ac0  xor     eax, eax
0x180008ac2  jmp     loc_180008A25
```
