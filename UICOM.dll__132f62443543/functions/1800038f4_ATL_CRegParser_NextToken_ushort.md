# ATL::CRegParser::NextToken(ushort *)

- ea: `0x1800038f4`
- end: `0x180003a8b`
- name: `?NextToken@CRegParser@ATL@@IEAAJPEAG@Z`
- size: `407`
- prototype: `__int64 __fastcall(ATL::CRegParser *__hidden this, unsigned __int16 *)`
- caller_count: `4`
- callee_count: `1`
- tags: ``

## callers

- `0x1800026a4`
- `0x180003ea8`
- `0x1800041fc`
- `0x1800049ac`

## callees

- `0x1800038f4`

## import_xrefs

- `USER32!CharNextW` at `0x180003929`
- `USER32!CharNextW` at `0x180003957`
- `USER32!CharNextW` at `0x180003977`
- `USER32!CharNextW` at `0x18000398f`
- `USER32!CharNextW` at `0x18000399e`
- `USER32!CharNextW` at `0x180003a09`
- `USER32!CharNextW` at `0x180003a2e`
- `USER32!CharNextW` at `0x180003929`
- `USER32!CharNextW` at `0x180003957`
- `USER32!CharNextW` at `0x180003977`
- `USER32!CharNextW` at `0x18000398f`
- `USER32!CharNextW` at `0x18000399e`
- `USER32!CharNextW` at `0x180003a09`
- `USER32!CharNextW` at `0x180003a2e`

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
0x1800038f4  push    rbx
0x1800038f6  push    rbp
0x1800038f7  push    rsi
0x1800038f8  push    rdi
0x1800038f9  push    r14
0x1800038fb  sub     rsp, 20h
0x1800038ff  mov     rbx, rdx
0x180003902  mov     rdi, rcx
0x180003905  mov     rsi, [rdi]
0x180003908  movzx   ecx, word ptr [rsi]
0x18000390b  mov     r8d, ecx
0x18000390e  sub     r8d, 9
0x180003912  jz      short loc_180003926
0x180003914  sub     r8d, 1
0x180003918  jz      short loc_180003926
0x18000391a  sub     r8d, 3
0x18000391e  jz      short loc_180003926
0x180003920  cmp     r8d, 13h
0x180003924  jnz     short loc_180003934
0x180003926  mov     rcx, rsi; lpsz
0x180003929  call    cs:__imp_CharNextW
0x18000392f  mov     [rdi], rax
0x180003932  jmp     short loc_180003905
0x180003934  xor     eax, eax
0x180003936  cmp     ax, cx
0x180003939  jz      loc_1800039E4
0x18000393f  lea     r14d, [rax+27h]
0x180003943  lea     rbp, [rbx+2000h]
0x18000394a  cmp     r14w, cx
0x18000394e  jnz     loc_180003A14
0x180003954  mov     rcx, rsi; lpsz
0x180003957  call    cs:__imp_CharNextW
0x18000395d  mov     [rdi], rax
0x180003960  mov     rcx, rax; lpsz
0x180003963  movzx   edx, word ptr [rax]
0x180003966  xor     eax, eax
0x180003968  cmp     ax, dx
0x18000396b  jz      loc_1800039F4
0x180003971  cmp     r14w, dx
0x180003975  jnz     short loc_180003983
0x180003977  call    cs:__imp_CharNextW
0x18000397d  cmp     r14w, [rax]
0x180003981  jnz     short loc_1800039F4
0x180003983  mov     rsi, [rdi]
0x180003986  cmp     r14w, [rsi]
0x18000398a  jnz     short loc_18000399B
0x18000398c  mov     rcx, rsi; lpsz
0x18000398f  call    cs:__imp_CharNextW
0x180003995  mov     rsi, rax
0x180003998  mov     [rdi], rax
0x18000399b  mov     rcx, rsi; lpsz
0x18000399e  call    cs:__imp_CharNextW
0x1800039a4  mov     rdx, rax
0x1800039a7  mov     [rdi], rax
0x1800039aa  sub     rdx, rsi
0x1800039ad  sar     rdx, 1
0x1800039b0  lea     rcx, [rdx+1]
0x1800039b4  lea     rcx, [rbx+rcx*2]
0x1800039b8  cmp     rcx, rbp
0x1800039bb  jnb     short loc_1800039E4
0x1800039bd  xor     ecx, ecx
0x1800039bf  test    edx, edx
0x1800039c1  jle     short loc_1800039D7
0x1800039c3  movzx   eax, word ptr [rsi]
0x1800039c6  inc     ecx
0x1800039c8  mov     [rbx], ax
0x1800039cb  lea     rsi, [rsi+2]
0x1800039cf  add     rbx, 2
0x1800039d3  cmp     ecx, edx
0x1800039d5  jl      short loc_1800039C3
0x1800039d7  mov     rcx, [rdi]
0x1800039da  xor     eax, eax
0x1800039dc  movzx   edx, word ptr [rcx]
0x1800039df  cmp     ax, dx
0x1800039e2  jnz     short loc_180003971
0x1800039e4  mov     eax, 80020009h
0x1800039e9  add     rsp, 20h
0x1800039ed  pop     r14
0x1800039ef  pop     rdi
0x1800039f0  pop     rsi
0x1800039f1  pop     rbp
0x1800039f2  pop     rbx
0x1800039f3  retn
0x1800039f4  mov     rcx, [rdi]
0x1800039f7  xor     eax, eax
0x1800039f9  cmp     ax, [rcx]
0x1800039fc  jz      short loc_1800039E4
0x1800039fe  cmp     rbx, rbp
0x180003a01  jnb     short loc_1800039E4
0x180003a03  mov     [rbx], ax
0x180003a06  mov     rcx, [rdi]; lpsz
0x180003a09  call    cs:__imp_CharNextW
0x180003a0f  mov     [rdi], rax
0x180003a12  jmp     short loc_180003A84
0x180003a14  movzx   ecx, cx
0x180003a17  sub     ecx, 9
0x180003a1a  jz      short loc_180003A76
0x180003a1c  sub     ecx, 1
0x180003a1f  jz      short loc_180003A76
0x180003a21  sub     ecx, 3
0x180003a24  jz      short loc_180003A76
0x180003a26  cmp     ecx, 13h
0x180003a29  jz      short loc_180003A76
0x180003a2b  mov     rcx, rsi; lpsz
0x180003a2e  call    cs:__imp_CharNextW
0x180003a34  mov     rdx, rax
0x180003a37  mov     [rdi], rax
0x180003a3a  sub     rdx, rsi
0x180003a3d  sar     rdx, 1
0x180003a40  lea     rcx, [rdx+1]
0x180003a44  lea     rcx, [rbx+rcx*2]
0x180003a48  cmp     rcx, rbp
0x180003a4b  jnb     short loc_1800039E4
0x180003a4d  xor     ecx, ecx
0x180003a4f  test    edx, edx
0x180003a51  jle     short loc_180003A67
0x180003a53  movzx   eax, word ptr [rsi]
0x180003a56  inc     ecx
0x180003a58  mov     [rbx], ax
0x180003a5b  lea     rsi, [rsi+2]
0x180003a5f  add     rbx, 2
0x180003a63  cmp     ecx, edx
0x180003a65  jl      short loc_180003A53
0x180003a67  mov     rsi, [rdi]
0x180003a6a  xor     eax, eax
0x180003a6c  cmp     ax, [rsi]
0x180003a6f  jz      short loc_180003A76
0x180003a71  movzx   ecx, word ptr [rsi]
0x180003a74  jmp     short loc_180003A14
0x180003a76  cmp     rbx, rbp
0x180003a79  jnb     loc_1800039E4
0x180003a7f  xor     eax, eax
0x180003a81  mov     [rbx], ax
0x180003a84  xor     eax, eax
0x180003a86  jmp     loc_1800039E9
```
