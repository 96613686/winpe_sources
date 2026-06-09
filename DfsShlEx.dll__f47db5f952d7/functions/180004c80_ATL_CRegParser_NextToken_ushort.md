# ATL::CRegParser::NextToken(ushort *)

- ea: `0x180004c80`
- end: `0x180004e17`
- name: `?NextToken@CRegParser@ATL@@IEAAJPEAG@Z`
- size: `407`
- prototype: `__int64 __fastcall(ATL::CRegParser *__hidden this, unsigned __int16 *)`
- caller_count: `4`
- callee_count: `1`
- tags: ``

## callers

- `0x180003280`
- `0x1800053f8`
- `0x180005764`
- `0x180006184`

## callees

- `0x180004c80`

## import_xrefs

- `USER32!CharNextW` at `0x180004cb5`
- `USER32!CharNextW` at `0x180004ce3`
- `USER32!CharNextW` at `0x180004d03`
- `USER32!CharNextW` at `0x180004d1b`
- `USER32!CharNextW` at `0x180004d2a`
- `USER32!CharNextW` at `0x180004d95`
- `USER32!CharNextW` at `0x180004dba`
- `USER32!CharNextW` at `0x180004cb5`
- `USER32!CharNextW` at `0x180004ce3`
- `USER32!CharNextW` at `0x180004d03`
- `USER32!CharNextW` at `0x180004d1b`
- `USER32!CharNextW` at `0x180004d2a`
- `USER32!CharNextW` at `0x180004d95`
- `USER32!CharNextW` at `0x180004dba`

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
0x180004c80  push    rbx
0x180004c82  push    rbp
0x180004c83  push    rsi
0x180004c84  push    rdi
0x180004c85  push    r14
0x180004c87  sub     rsp, 20h
0x180004c8b  mov     rbx, rdx
0x180004c8e  mov     rdi, rcx
0x180004c91  mov     rsi, [rdi]
0x180004c94  movzx   ecx, word ptr [rsi]
0x180004c97  mov     r8d, ecx
0x180004c9a  sub     r8d, 9
0x180004c9e  jz      short loc_180004CB2
0x180004ca0  sub     r8d, 1
0x180004ca4  jz      short loc_180004CB2
0x180004ca6  sub     r8d, 3
0x180004caa  jz      short loc_180004CB2
0x180004cac  cmp     r8d, 13h
0x180004cb0  jnz     short loc_180004CC0
0x180004cb2  mov     rcx, rsi; lpsz
0x180004cb5  call    cs:__imp_CharNextW
0x180004cbb  mov     [rdi], rax
0x180004cbe  jmp     short loc_180004C91
0x180004cc0  xor     eax, eax
0x180004cc2  cmp     ax, cx
0x180004cc5  jz      loc_180004D70
0x180004ccb  lea     r14d, [rax+27h]
0x180004ccf  lea     rbp, [rbx+2000h]
0x180004cd6  cmp     r14w, cx
0x180004cda  jnz     loc_180004DA0
0x180004ce0  mov     rcx, rsi; lpsz
0x180004ce3  call    cs:__imp_CharNextW
0x180004ce9  mov     [rdi], rax
0x180004cec  mov     rcx, rax; lpsz
0x180004cef  movzx   edx, word ptr [rax]
0x180004cf2  xor     eax, eax
0x180004cf4  cmp     ax, dx
0x180004cf7  jz      loc_180004D80
0x180004cfd  cmp     r14w, dx
0x180004d01  jnz     short loc_180004D0F
0x180004d03  call    cs:__imp_CharNextW
0x180004d09  cmp     r14w, [rax]
0x180004d0d  jnz     short loc_180004D80
0x180004d0f  mov     rsi, [rdi]
0x180004d12  cmp     r14w, [rsi]
0x180004d16  jnz     short loc_180004D27
0x180004d18  mov     rcx, rsi; lpsz
0x180004d1b  call    cs:__imp_CharNextW
0x180004d21  mov     rsi, rax
0x180004d24  mov     [rdi], rax
0x180004d27  mov     rcx, rsi; lpsz
0x180004d2a  call    cs:__imp_CharNextW
0x180004d30  mov     rdx, rax
0x180004d33  mov     [rdi], rax
0x180004d36  sub     rdx, rsi
0x180004d39  sar     rdx, 1
0x180004d3c  lea     rcx, [rdx+1]
0x180004d40  lea     rcx, [rbx+rcx*2]
0x180004d44  cmp     rcx, rbp
0x180004d47  jnb     short loc_180004D70
0x180004d49  xor     ecx, ecx
0x180004d4b  test    edx, edx
0x180004d4d  jle     short loc_180004D63
0x180004d4f  movzx   eax, word ptr [rsi]
0x180004d52  inc     ecx
0x180004d54  mov     [rbx], ax
0x180004d57  lea     rsi, [rsi+2]
0x180004d5b  add     rbx, 2
0x180004d5f  cmp     ecx, edx
0x180004d61  jl      short loc_180004D4F
0x180004d63  mov     rcx, [rdi]
0x180004d66  xor     eax, eax
0x180004d68  movzx   edx, word ptr [rcx]
0x180004d6b  cmp     ax, dx
0x180004d6e  jnz     short loc_180004CFD
0x180004d70  mov     eax, 80020009h
0x180004d75  add     rsp, 20h
0x180004d79  pop     r14
0x180004d7b  pop     rdi
0x180004d7c  pop     rsi
0x180004d7d  pop     rbp
0x180004d7e  pop     rbx
0x180004d7f  retn
0x180004d80  mov     rcx, [rdi]
0x180004d83  xor     eax, eax
0x180004d85  cmp     ax, [rcx]
0x180004d88  jz      short loc_180004D70
0x180004d8a  cmp     rbx, rbp
0x180004d8d  jnb     short loc_180004D70
0x180004d8f  mov     [rbx], ax
0x180004d92  mov     rcx, [rdi]; lpsz
0x180004d95  call    cs:__imp_CharNextW
0x180004d9b  mov     [rdi], rax
0x180004d9e  jmp     short loc_180004E10
0x180004da0  movzx   ecx, cx
0x180004da3  sub     ecx, 9
0x180004da6  jz      short loc_180004E02
0x180004da8  sub     ecx, 1
0x180004dab  jz      short loc_180004E02
0x180004dad  sub     ecx, 3
0x180004db0  jz      short loc_180004E02
0x180004db2  cmp     ecx, 13h
0x180004db5  jz      short loc_180004E02
0x180004db7  mov     rcx, rsi; lpsz
0x180004dba  call    cs:__imp_CharNextW
0x180004dc0  mov     rdx, rax
0x180004dc3  mov     [rdi], rax
0x180004dc6  sub     rdx, rsi
0x180004dc9  sar     rdx, 1
0x180004dcc  lea     rcx, [rdx+1]
0x180004dd0  lea     rcx, [rbx+rcx*2]
0x180004dd4  cmp     rcx, rbp
0x180004dd7  jnb     short loc_180004D70
0x180004dd9  xor     ecx, ecx
0x180004ddb  test    edx, edx
0x180004ddd  jle     short loc_180004DF3
0x180004ddf  movzx   eax, word ptr [rsi]
0x180004de2  inc     ecx
0x180004de4  mov     [rbx], ax
0x180004de7  lea     rsi, [rsi+2]
0x180004deb  add     rbx, 2
0x180004def  cmp     ecx, edx
0x180004df1  jl      short loc_180004DDF
0x180004df3  mov     rsi, [rdi]
0x180004df6  xor     eax, eax
0x180004df8  cmp     ax, [rsi]
0x180004dfb  jz      short loc_180004E02
0x180004dfd  movzx   ecx, word ptr [rsi]
0x180004e00  jmp     short loc_180004DA0
0x180004e02  cmp     rbx, rbp
0x180004e05  jnb     loc_180004D70
0x180004e0b  xor     eax, eax
0x180004e0d  mov     [rbx], ax
0x180004e10  xor     eax, eax
0x180004e12  jmp     loc_180004D75
```
