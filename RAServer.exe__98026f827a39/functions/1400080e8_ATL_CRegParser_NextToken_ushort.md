# ATL::CRegParser::NextToken(ushort *)

- ea: `0x1400080e8`
- end: `0x14000823f`
- name: `?NextToken@CRegParser@ATL@@IEAAJPEAG@Z`
- size: `343`
- prototype: `__int64 __fastcall(ATL::CRegParser *__hidden this, unsigned __int16 *)`
- caller_count: `4`
- callee_count: `2`
- tags: ``

## callers

- `0x1400046ac`
- `0x140009430`
- `0x140009754`
- `0x14000a7e4`

## callees

- `0x1400080e8`
- `0x14000a938`

## import_xrefs

- `USER32!CharNextW` at `0x140008121`
- `USER32!CharNextW` at `0x14000813a`
- `USER32!CharNextW` at `0x140008152`
- `USER32!CharNextW` at `0x140008161`
- `USER32!CharNextW` at `0x1400081b9`
- `USER32!CharNextW` at `0x1400081e8`
- `USER32!CharNextW` at `0x140008121`
- `USER32!CharNextW` at `0x14000813a`
- `USER32!CharNextW` at `0x140008152`
- `USER32!CharNextW` at `0x140008161`
- `USER32!CharNextW` at `0x1400081b9`
- `USER32!CharNextW` at `0x1400081e8`

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
0x1400080e8  push    rbx
0x1400080ea  push    rbp
0x1400080eb  push    rsi
0x1400080ec  push    rdi
0x1400080ed  push    r14
0x1400080ef  sub     rsp, 20h
0x1400080f3  mov     rbx, rdx
0x1400080f6  mov     rdi, rcx
0x1400080f9  call    ?SkipWhiteSpace@CRegParser@ATL@@IEAAXXZ; ATL::CRegParser::SkipWhiteSpace(void)
0x1400080fe  mov     rcx, [rdi]; lpsz
0x140008101  xor     eax, eax
0x140008103  cmp     ax, [rcx]
0x140008106  jz      loc_14000822F
0x14000810c  lea     r14d, [rax+27h]
0x140008110  lea     rbp, [rbx+2000h]
0x140008117  cmp     r14w, [rcx]
0x14000811b  jnz     loc_1400081C4
0x140008121  call    cs:__imp_CharNextW
0x140008127  mov     [rdi], rax
0x14000812a  mov     rcx, [rdi]; lpsz
0x14000812d  xor     eax, eax
0x14000812f  cmp     ax, [rcx]
0x140008132  jz      short loc_1400081A0
0x140008134  cmp     r14w, [rcx]
0x140008138  jnz     short loc_140008146
0x14000813a  call    cs:__imp_CharNextW
0x140008140  cmp     r14w, [rax]
0x140008144  jnz     short loc_1400081A0
0x140008146  mov     rsi, [rdi]
0x140008149  cmp     r14w, [rsi]
0x14000814d  jnz     short loc_14000815E
0x14000814f  mov     rcx, rsi; lpsz
0x140008152  call    cs:__imp_CharNextW
0x140008158  mov     rsi, rax
0x14000815b  mov     [rdi], rax
0x14000815e  mov     rcx, rsi; lpsz
0x140008161  call    cs:__imp_CharNextW
0x140008167  mov     rdx, rax
0x14000816a  mov     [rdi], rax
0x14000816d  sub     rdx, rsi
0x140008170  sar     rdx, 1
0x140008173  lea     rcx, [rdx+1]
0x140008177  lea     rcx, [rbx+rcx*2]
0x14000817b  cmp     rcx, rbp
0x14000817e  jnb     loc_14000822F
0x140008184  xor     ecx, ecx
0x140008186  test    edx, edx
0x140008188  jle     short loc_14000812A
0x14000818a  movzx   eax, word ptr [rsi]
0x14000818d  inc     ecx
0x14000818f  mov     [rbx], ax
0x140008192  lea     rsi, [rsi+2]
0x140008196  add     rbx, 2
0x14000819a  cmp     ecx, edx
0x14000819c  jl      short loc_14000818A
0x14000819e  jmp     short loc_14000812A
0x1400081a0  mov     rcx, [rdi]
0x1400081a3  xor     eax, eax
0x1400081a5  cmp     ax, [rcx]
0x1400081a8  jz      loc_14000822F
0x1400081ae  cmp     rbx, rbp
0x1400081b1  jnb     short loc_14000822F
0x1400081b3  mov     [rbx], ax
0x1400081b6  mov     rcx, [rdi]; lpsz
0x1400081b9  call    cs:__imp_CharNextW
0x1400081bf  mov     [rdi], rax
0x1400081c2  jmp     short loc_14000822B
0x1400081c4  mov     rsi, [rdi]
0x1400081c7  xor     eax, eax
0x1400081c9  cmp     ax, [rsi]
0x1400081cc  jz      short loc_140008223
0x1400081ce  movzx   ecx, word ptr [rsi]
0x1400081d1  sub     ecx, 9
0x1400081d4  jz      short loc_140008223
0x1400081d6  sub     ecx, 1
0x1400081d9  jz      short loc_140008223
0x1400081db  sub     ecx, 3
0x1400081de  jz      short loc_140008223
0x1400081e0  cmp     ecx, 13h
0x1400081e3  jz      short loc_140008223
0x1400081e5  mov     rcx, rsi; lpsz
0x1400081e8  call    cs:__imp_CharNextW
0x1400081ee  mov     rdx, rax
0x1400081f1  mov     [rdi], rax
0x1400081f4  sub     rdx, rsi
0x1400081f7  sar     rdx, 1
0x1400081fa  lea     rcx, [rdx+1]
0x1400081fe  lea     rcx, [rbx+rcx*2]
0x140008202  cmp     rcx, rbp
0x140008205  jnb     short loc_14000822F
0x140008207  xor     ecx, ecx
0x140008209  test    edx, edx
0x14000820b  jle     short loc_1400081C4
0x14000820d  movzx   eax, word ptr [rsi]
0x140008210  inc     ecx
0x140008212  mov     [rbx], ax
0x140008215  lea     rsi, [rsi+2]
0x140008219  add     rbx, 2
0x14000821d  cmp     ecx, edx
0x14000821f  jl      short loc_14000820D
0x140008221  jmp     short loc_1400081C4
0x140008223  cmp     rbx, rbp
0x140008226  jnb     short loc_14000822F
0x140008228  mov     [rbx], ax
0x14000822b  xor     eax, eax
0x14000822d  jmp     short loc_140008234
0x14000822f  mov     eax, 80020009h
0x140008234  add     rsp, 20h
0x140008238  pop     r14
0x14000823a  pop     rdi
0x14000823b  pop     rsi
0x14000823c  pop     rbp
0x14000823d  pop     rbx
0x14000823e  retn
```
