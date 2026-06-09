# ATL::CRegParser::NextToken(ushort *)

- ea: `0x180006dbc`
- end: `0x180006f53`
- name: `?NextToken@CRegParser@ATL@@IEAAJPEAG@Z`
- size: `407`
- prototype: `__int64 __fastcall(ATL::CRegParser *__hidden this, unsigned __int16 *)`
- caller_count: `4`
- callee_count: `1`
- tags: ``

## callers

- `0x180003f3c`
- `0x1800074dc`
- `0x18000784c`
- `0x180008a98`

## callees

- `0x180006dbc`

## import_xrefs

- `USER32!CharNextW` at `0x180006df1`
- `USER32!CharNextW` at `0x180006e1f`
- `USER32!CharNextW` at `0x180006e3f`
- `USER32!CharNextW` at `0x180006e57`
- `USER32!CharNextW` at `0x180006e66`
- `USER32!CharNextW` at `0x180006ed1`
- `USER32!CharNextW` at `0x180006ef6`
- `USER32!CharNextW` at `0x180006df1`
- `USER32!CharNextW` at `0x180006e1f`
- `USER32!CharNextW` at `0x180006e3f`
- `USER32!CharNextW` at `0x180006e57`
- `USER32!CharNextW` at `0x180006e66`
- `USER32!CharNextW` at `0x180006ed1`
- `USER32!CharNextW` at `0x180006ef6`

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
0x180006dbc  push    rbx
0x180006dbe  push    rbp
0x180006dbf  push    rsi
0x180006dc0  push    rdi
0x180006dc1  push    r14
0x180006dc3  sub     rsp, 20h
0x180006dc7  mov     rbx, rdx
0x180006dca  mov     rdi, rcx
0x180006dcd  mov     rsi, [rdi]
0x180006dd0  movzx   ecx, word ptr [rsi]
0x180006dd3  mov     r8d, ecx
0x180006dd6  sub     r8d, 9
0x180006dda  jz      short loc_180006DEE
0x180006ddc  sub     r8d, 1
0x180006de0  jz      short loc_180006DEE
0x180006de2  sub     r8d, 3
0x180006de6  jz      short loc_180006DEE
0x180006de8  cmp     r8d, 13h
0x180006dec  jnz     short loc_180006DFC
0x180006dee  mov     rcx, rsi; lpsz
0x180006df1  call    cs:__imp_CharNextW
0x180006df7  mov     [rdi], rax
0x180006dfa  jmp     short loc_180006DCD
0x180006dfc  xor     eax, eax
0x180006dfe  cmp     ax, cx
0x180006e01  jz      loc_180006EAC
0x180006e07  lea     r14d, [rax+27h]
0x180006e0b  lea     rbp, [rbx+2000h]
0x180006e12  cmp     r14w, cx
0x180006e16  jnz     loc_180006EDC
0x180006e1c  mov     rcx, rsi; lpsz
0x180006e1f  call    cs:__imp_CharNextW
0x180006e25  mov     [rdi], rax
0x180006e28  mov     rcx, rax; lpsz
0x180006e2b  movzx   edx, word ptr [rax]
0x180006e2e  xor     eax, eax
0x180006e30  cmp     ax, dx
0x180006e33  jz      loc_180006EBC
0x180006e39  cmp     r14w, dx
0x180006e3d  jnz     short loc_180006E4B
0x180006e3f  call    cs:__imp_CharNextW
0x180006e45  cmp     r14w, [rax]
0x180006e49  jnz     short loc_180006EBC
0x180006e4b  mov     rsi, [rdi]
0x180006e4e  cmp     r14w, [rsi]
0x180006e52  jnz     short loc_180006E63
0x180006e54  mov     rcx, rsi; lpsz
0x180006e57  call    cs:__imp_CharNextW
0x180006e5d  mov     rsi, rax
0x180006e60  mov     [rdi], rax
0x180006e63  mov     rcx, rsi; lpsz
0x180006e66  call    cs:__imp_CharNextW
0x180006e6c  mov     rdx, rax
0x180006e6f  mov     [rdi], rax
0x180006e72  sub     rdx, rsi
0x180006e75  sar     rdx, 1
0x180006e78  lea     rcx, [rdx+1]
0x180006e7c  lea     rcx, [rbx+rcx*2]
0x180006e80  cmp     rcx, rbp
0x180006e83  jnb     short loc_180006EAC
0x180006e85  xor     ecx, ecx
0x180006e87  test    edx, edx
0x180006e89  jle     short loc_180006E9F
0x180006e8b  movzx   eax, word ptr [rsi]
0x180006e8e  inc     ecx
0x180006e90  mov     [rbx], ax
0x180006e93  lea     rsi, [rsi+2]
0x180006e97  add     rbx, 2
0x180006e9b  cmp     ecx, edx
0x180006e9d  jl      short loc_180006E8B
0x180006e9f  mov     rcx, [rdi]
0x180006ea2  xor     eax, eax
0x180006ea4  movzx   edx, word ptr [rcx]
0x180006ea7  cmp     ax, dx
0x180006eaa  jnz     short loc_180006E39
0x180006eac  mov     eax, 80020009h
0x180006eb1  add     rsp, 20h
0x180006eb5  pop     r14
0x180006eb7  pop     rdi
0x180006eb8  pop     rsi
0x180006eb9  pop     rbp
0x180006eba  pop     rbx
0x180006ebb  retn
0x180006ebc  mov     rcx, [rdi]
0x180006ebf  xor     eax, eax
0x180006ec1  cmp     ax, [rcx]
0x180006ec4  jz      short loc_180006EAC
0x180006ec6  cmp     rbx, rbp
0x180006ec9  jnb     short loc_180006EAC
0x180006ecb  mov     [rbx], ax
0x180006ece  mov     rcx, [rdi]; lpsz
0x180006ed1  call    cs:__imp_CharNextW
0x180006ed7  mov     [rdi], rax
0x180006eda  jmp     short loc_180006F4C
0x180006edc  movzx   ecx, cx
0x180006edf  sub     ecx, 9
0x180006ee2  jz      short loc_180006F3E
0x180006ee4  sub     ecx, 1
0x180006ee7  jz      short loc_180006F3E
0x180006ee9  sub     ecx, 3
0x180006eec  jz      short loc_180006F3E
0x180006eee  cmp     ecx, 13h
0x180006ef1  jz      short loc_180006F3E
0x180006ef3  mov     rcx, rsi; lpsz
0x180006ef6  call    cs:__imp_CharNextW
0x180006efc  mov     rdx, rax
0x180006eff  mov     [rdi], rax
0x180006f02  sub     rdx, rsi
0x180006f05  sar     rdx, 1
0x180006f08  lea     rcx, [rdx+1]
0x180006f0c  lea     rcx, [rbx+rcx*2]
0x180006f10  cmp     rcx, rbp
0x180006f13  jnb     short loc_180006EAC
0x180006f15  xor     ecx, ecx
0x180006f17  test    edx, edx
0x180006f19  jle     short loc_180006F2F
0x180006f1b  movzx   eax, word ptr [rsi]
0x180006f1e  inc     ecx
0x180006f20  mov     [rbx], ax
0x180006f23  lea     rsi, [rsi+2]
0x180006f27  add     rbx, 2
0x180006f2b  cmp     ecx, edx
0x180006f2d  jl      short loc_180006F1B
0x180006f2f  mov     rsi, [rdi]
0x180006f32  xor     eax, eax
0x180006f34  cmp     ax, [rsi]
0x180006f37  jz      short loc_180006F3E
0x180006f39  movzx   ecx, word ptr [rsi]
0x180006f3c  jmp     short loc_180006EDC
0x180006f3e  cmp     rbx, rbp
0x180006f41  jnb     loc_180006EAC
0x180006f47  xor     eax, eax
0x180006f49  mov     [rbx], ax
0x180006f4c  xor     eax, eax
0x180006f4e  jmp     loc_180006EB1
```
