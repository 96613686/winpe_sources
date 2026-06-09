# ATL::CRegParser::NextToken(ushort *)

- ea: `0x140004070`
- end: `0x140004207`
- name: `?NextToken@CRegParser@ATL@@IEAAJPEAG@Z`
- size: `407`
- prototype: `__int64 __fastcall(LPCWSTR *this, unsigned __int16 *)`
- caller_count: `4`
- callee_count: `1`
- tags: ``

## callers

- `0x140002bec`
- `0x140004d28`
- `0x140005098`
- `0x140005af0`

## callees

- `0x140004070`

## import_xrefs

- `USER32!CharNextW` at `0x1400040a5`
- `USER32!CharNextW` at `0x1400040d3`
- `USER32!CharNextW` at `0x1400040f3`
- `USER32!CharNextW` at `0x14000410b`
- `USER32!CharNextW` at `0x14000411a`
- `USER32!CharNextW` at `0x140004185`
- `USER32!CharNextW` at `0x1400041aa`
- `USER32!CharNextW` at `0x1400040a5`
- `USER32!CharNextW` at `0x1400040d3`
- `USER32!CharNextW` at `0x1400040f3`
- `USER32!CharNextW` at `0x14000410b`
- `USER32!CharNextW` at `0x14000411a`
- `USER32!CharNextW` at `0x140004185`
- `USER32!CharNextW` at `0x1400041aa`

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
0x140004070  push    rbx
0x140004072  push    rbp
0x140004073  push    rsi
0x140004074  push    rdi
0x140004075  push    r14
0x140004077  sub     rsp, 20h
0x14000407b  mov     rbx, rdx
0x14000407e  mov     rdi, rcx
0x140004081  mov     rsi, [rdi]
0x140004084  movzx   ecx, word ptr [rsi]
0x140004087  mov     r8d, ecx
0x14000408a  sub     r8d, 9
0x14000408e  jz      short loc_1400040A2
0x140004090  sub     r8d, 1
0x140004094  jz      short loc_1400040A2
0x140004096  sub     r8d, 3
0x14000409a  jz      short loc_1400040A2
0x14000409c  cmp     r8d, 13h
0x1400040a0  jnz     short loc_1400040B0
0x1400040a2  mov     rcx, rsi; lpsz
0x1400040a5  call    cs:__imp_CharNextW
0x1400040ab  mov     [rdi], rax
0x1400040ae  jmp     short loc_140004081
0x1400040b0  xor     eax, eax
0x1400040b2  cmp     ax, cx
0x1400040b5  jz      loc_140004160
0x1400040bb  lea     r14d, [rax+27h]
0x1400040bf  lea     rbp, [rbx+2000h]
0x1400040c6  cmp     r14w, cx
0x1400040ca  jnz     loc_140004190
0x1400040d0  mov     rcx, rsi; lpsz
0x1400040d3  call    cs:__imp_CharNextW
0x1400040d9  mov     [rdi], rax
0x1400040dc  mov     rcx, rax; lpsz
0x1400040df  movzx   edx, word ptr [rax]
0x1400040e2  xor     eax, eax
0x1400040e4  cmp     ax, dx
0x1400040e7  jz      loc_140004170
0x1400040ed  cmp     r14w, dx
0x1400040f1  jnz     short loc_1400040FF
0x1400040f3  call    cs:__imp_CharNextW
0x1400040f9  cmp     r14w, [rax]
0x1400040fd  jnz     short loc_140004170
0x1400040ff  mov     rsi, [rdi]
0x140004102  cmp     r14w, [rsi]
0x140004106  jnz     short loc_140004117
0x140004108  mov     rcx, rsi; lpsz
0x14000410b  call    cs:__imp_CharNextW
0x140004111  mov     rsi, rax
0x140004114  mov     [rdi], rax
0x140004117  mov     rcx, rsi; lpsz
0x14000411a  call    cs:__imp_CharNextW
0x140004120  mov     rdx, rax
0x140004123  mov     [rdi], rax
0x140004126  sub     rdx, rsi
0x140004129  sar     rdx, 1
0x14000412c  lea     rcx, [rdx+1]
0x140004130  lea     rcx, [rbx+rcx*2]
0x140004134  cmp     rcx, rbp
0x140004137  jnb     short loc_140004160
0x140004139  xor     ecx, ecx
0x14000413b  test    edx, edx
0x14000413d  jle     short loc_140004153
0x14000413f  movzx   eax, word ptr [rsi]
0x140004142  inc     ecx
0x140004144  mov     [rbx], ax
0x140004147  lea     rsi, [rsi+2]
0x14000414b  add     rbx, 2
0x14000414f  cmp     ecx, edx
0x140004151  jl      short loc_14000413F
0x140004153  mov     rcx, [rdi]
0x140004156  xor     eax, eax
0x140004158  movzx   edx, word ptr [rcx]
0x14000415b  cmp     ax, dx
0x14000415e  jnz     short loc_1400040ED
0x140004160  mov     eax, 80020009h
0x140004165  add     rsp, 20h
0x140004169  pop     r14
0x14000416b  pop     rdi
0x14000416c  pop     rsi
0x14000416d  pop     rbp
0x14000416e  pop     rbx
0x14000416f  retn
0x140004170  mov     rcx, [rdi]
0x140004173  xor     eax, eax
0x140004175  cmp     ax, [rcx]
0x140004178  jz      short loc_140004160
0x14000417a  cmp     rbx, rbp
0x14000417d  jnb     short loc_140004160
0x14000417f  mov     [rbx], ax
0x140004182  mov     rcx, [rdi]; lpsz
0x140004185  call    cs:__imp_CharNextW
0x14000418b  mov     [rdi], rax
0x14000418e  jmp     short loc_140004200
0x140004190  movzx   ecx, cx
0x140004193  sub     ecx, 9
0x140004196  jz      short loc_1400041F2
0x140004198  sub     ecx, 1
0x14000419b  jz      short loc_1400041F2
0x14000419d  sub     ecx, 3
0x1400041a0  jz      short loc_1400041F2
0x1400041a2  cmp     ecx, 13h
0x1400041a5  jz      short loc_1400041F2
0x1400041a7  mov     rcx, rsi; lpsz
0x1400041aa  call    cs:__imp_CharNextW
0x1400041b0  mov     rdx, rax
0x1400041b3  mov     [rdi], rax
0x1400041b6  sub     rdx, rsi
0x1400041b9  sar     rdx, 1
0x1400041bc  lea     rcx, [rdx+1]
0x1400041c0  lea     rcx, [rbx+rcx*2]
0x1400041c4  cmp     rcx, rbp
0x1400041c7  jnb     short loc_140004160
0x1400041c9  xor     ecx, ecx
0x1400041cb  test    edx, edx
0x1400041cd  jle     short loc_1400041E3
0x1400041cf  movzx   eax, word ptr [rsi]
0x1400041d2  inc     ecx
0x1400041d4  mov     [rbx], ax
0x1400041d7  lea     rsi, [rsi+2]
0x1400041db  add     rbx, 2
0x1400041df  cmp     ecx, edx
0x1400041e1  jl      short loc_1400041CF
0x1400041e3  mov     rsi, [rdi]
0x1400041e6  xor     eax, eax
0x1400041e8  cmp     ax, [rsi]
0x1400041eb  jz      short loc_1400041F2
0x1400041ed  movzx   ecx, word ptr [rsi]
0x1400041f0  jmp     short loc_140004190
0x1400041f2  cmp     rbx, rbp
0x1400041f5  jnb     loc_140004160
0x1400041fb  xor     eax, eax
0x1400041fd  mov     [rbx], ax
0x140004200  xor     eax, eax
0x140004202  jmp     loc_140004165
```
