# ATL::CRegParser::NextToken(ushort *)

- ea: `0x180004ef0`
- end: `0x180005087`
- name: `?NextToken@CRegParser@ATL@@IEAAJPEAG@Z`
- size: `407`
- prototype: `__int64 __fastcall(ATL::CRegParser *__hidden this, unsigned __int16 *)`
- caller_count: `4`
- callee_count: `1`
- tags: ``

## callers

- `0x18000369c`
- `0x180005528`
- `0x18000589c`
- `0x180006164`

## callees

- `0x180004ef0`

## import_xrefs

- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x180004f25`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x180004f53`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x180004f73`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x180004f8b`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x180004f9a`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x180005005`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x18000502a`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x180004f25`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x180004f53`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x180004f73`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x180004f8b`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x180004f9a`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x180005005`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x18000502a`

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
0x180004ef0  push    rbx
0x180004ef2  push    rbp
0x180004ef3  push    rsi
0x180004ef4  push    rdi
0x180004ef5  push    r14
0x180004ef7  sub     rsp, 20h
0x180004efb  mov     rbx, rdx
0x180004efe  mov     rdi, rcx
0x180004f01  mov     rsi, [rdi]
0x180004f04  movzx   ecx, word ptr [rsi]
0x180004f07  mov     r8d, ecx
0x180004f0a  sub     r8d, 9
0x180004f0e  jz      short loc_180004F22
0x180004f10  sub     r8d, 1
0x180004f14  jz      short loc_180004F22
0x180004f16  sub     r8d, 3
0x180004f1a  jz      short loc_180004F22
0x180004f1c  cmp     r8d, 13h
0x180004f20  jnz     short loc_180004F30
0x180004f22  mov     rcx, rsi; lpsz
0x180004f25  call    cs:__imp_CharNextW
0x180004f2b  mov     [rdi], rax
0x180004f2e  jmp     short loc_180004F01
0x180004f30  xor     eax, eax
0x180004f32  cmp     ax, cx
0x180004f35  jz      loc_180004FE0
0x180004f3b  lea     r14d, [rax+27h]
0x180004f3f  lea     rbp, [rbx+2000h]
0x180004f46  cmp     r14w, cx
0x180004f4a  jnz     loc_180005010
0x180004f50  mov     rcx, rsi; lpsz
0x180004f53  call    cs:__imp_CharNextW
0x180004f59  mov     [rdi], rax
0x180004f5c  mov     rcx, rax; lpsz
0x180004f5f  movzx   edx, word ptr [rax]
0x180004f62  xor     eax, eax
0x180004f64  cmp     ax, dx
0x180004f67  jz      loc_180004FF0
0x180004f6d  cmp     r14w, dx
0x180004f71  jnz     short loc_180004F7F
0x180004f73  call    cs:__imp_CharNextW
0x180004f79  cmp     r14w, [rax]
0x180004f7d  jnz     short loc_180004FF0
0x180004f7f  mov     rsi, [rdi]
0x180004f82  cmp     r14w, [rsi]
0x180004f86  jnz     short loc_180004F97
0x180004f88  mov     rcx, rsi; lpsz
0x180004f8b  call    cs:__imp_CharNextW
0x180004f91  mov     rsi, rax
0x180004f94  mov     [rdi], rax
0x180004f97  mov     rcx, rsi; lpsz
0x180004f9a  call    cs:__imp_CharNextW
0x180004fa0  mov     rdx, rax
0x180004fa3  mov     [rdi], rax
0x180004fa6  sub     rdx, rsi
0x180004fa9  sar     rdx, 1
0x180004fac  lea     rcx, [rdx+1]
0x180004fb0  lea     rcx, [rbx+rcx*2]
0x180004fb4  cmp     rcx, rbp
0x180004fb7  jnb     short loc_180004FE0
0x180004fb9  xor     ecx, ecx
0x180004fbb  test    edx, edx
0x180004fbd  jle     short loc_180004FD3
0x180004fbf  movzx   eax, word ptr [rsi]
0x180004fc2  inc     ecx
0x180004fc4  mov     [rbx], ax
0x180004fc7  lea     rsi, [rsi+2]
0x180004fcb  add     rbx, 2
0x180004fcf  cmp     ecx, edx
0x180004fd1  jl      short loc_180004FBF
0x180004fd3  mov     rcx, [rdi]
0x180004fd6  xor     eax, eax
0x180004fd8  movzx   edx, word ptr [rcx]
0x180004fdb  cmp     ax, dx
0x180004fde  jnz     short loc_180004F6D
0x180004fe0  mov     eax, 80020009h
0x180004fe5  add     rsp, 20h
0x180004fe9  pop     r14
0x180004feb  pop     rdi
0x180004fec  pop     rsi
0x180004fed  pop     rbp
0x180004fee  pop     rbx
0x180004fef  retn
0x180004ff0  mov     rcx, [rdi]
0x180004ff3  xor     eax, eax
0x180004ff5  cmp     ax, [rcx]
0x180004ff8  jz      short loc_180004FE0
0x180004ffa  cmp     rbx, rbp
0x180004ffd  jnb     short loc_180004FE0
0x180004fff  mov     [rbx], ax
0x180005002  mov     rcx, [rdi]; lpsz
0x180005005  call    cs:__imp_CharNextW
0x18000500b  mov     [rdi], rax
0x18000500e  jmp     short loc_180005080
0x180005010  movzx   ecx, cx
0x180005013  sub     ecx, 9
0x180005016  jz      short loc_180005072
0x180005018  sub     ecx, 1
0x18000501b  jz      short loc_180005072
0x18000501d  sub     ecx, 3
0x180005020  jz      short loc_180005072
0x180005022  cmp     ecx, 13h
0x180005025  jz      short loc_180005072
0x180005027  mov     rcx, rsi; lpsz
0x18000502a  call    cs:__imp_CharNextW
0x180005030  mov     rdx, rax
0x180005033  mov     [rdi], rax
0x180005036  sub     rdx, rsi
0x180005039  sar     rdx, 1
0x18000503c  lea     rcx, [rdx+1]
0x180005040  lea     rcx, [rbx+rcx*2]
0x180005044  cmp     rcx, rbp
0x180005047  jnb     short loc_180004FE0
0x180005049  xor     ecx, ecx
0x18000504b  test    edx, edx
0x18000504d  jle     short loc_180005063
0x18000504f  movzx   eax, word ptr [rsi]
0x180005052  inc     ecx
0x180005054  mov     [rbx], ax
0x180005057  lea     rsi, [rsi+2]
0x18000505b  add     rbx, 2
0x18000505f  cmp     ecx, edx
0x180005061  jl      short loc_18000504F
0x180005063  mov     rsi, [rdi]
0x180005066  xor     eax, eax
0x180005068  cmp     ax, [rsi]
0x18000506b  jz      short loc_180005072
0x18000506d  movzx   ecx, word ptr [rsi]
0x180005070  jmp     short loc_180005010
0x180005072  cmp     rbx, rbp
0x180005075  jnb     loc_180004FE0
0x18000507b  xor     eax, eax
0x18000507d  mov     [rbx], ax
0x180005080  xor     eax, eax
0x180005082  jmp     loc_180004FE5
```
