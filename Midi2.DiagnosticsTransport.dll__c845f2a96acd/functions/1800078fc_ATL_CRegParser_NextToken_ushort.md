# ATL::CRegParser::NextToken(ushort *)

- ea: `0x1800078fc`
- end: `0x180007a93`
- name: `?NextToken@CRegParser@ATL@@IEAAJPEAG@Z`
- size: `407`
- prototype: `__int64 __fastcall(ATL::CRegParser *__hidden this, unsigned __int16 *)`
- caller_count: `4`
- callee_count: `1`
- tags: ``

## callers

- `0x1800058d0`
- `0x1800080bc`
- `0x18000842c`
- `0x180009840`

## callees

- `0x1800078fc`

## import_xrefs

- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x180007931`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x18000795f`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x18000797f`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x180007997`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x1800079a6`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x180007a11`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x180007a36`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x180007931`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x18000795f`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x18000797f`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x180007997`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x1800079a6`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x180007a11`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x180007a36`

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
0x1800078fc  push    rbx
0x1800078fe  push    rbp
0x1800078ff  push    rsi
0x180007900  push    rdi
0x180007901  push    r14
0x180007903  sub     rsp, 20h
0x180007907  mov     rbx, rdx
0x18000790a  mov     rdi, rcx
0x18000790d  mov     rsi, [rdi]
0x180007910  movzx   ecx, word ptr [rsi]
0x180007913  mov     r8d, ecx
0x180007916  sub     r8d, 9
0x18000791a  jz      short loc_18000792E
0x18000791c  sub     r8d, 1
0x180007920  jz      short loc_18000792E
0x180007922  sub     r8d, 3
0x180007926  jz      short loc_18000792E
0x180007928  cmp     r8d, 13h
0x18000792c  jnz     short loc_18000793C
0x18000792e  mov     rcx, rsi; lpsz
0x180007931  call    cs:__imp_CharNextW
0x180007937  mov     [rdi], rax
0x18000793a  jmp     short loc_18000790D
0x18000793c  xor     eax, eax
0x18000793e  cmp     ax, cx
0x180007941  jz      loc_1800079EC
0x180007947  lea     r14d, [rax+27h]
0x18000794b  lea     rbp, [rbx+2000h]
0x180007952  cmp     r14w, cx
0x180007956  jnz     loc_180007A1C
0x18000795c  mov     rcx, rsi; lpsz
0x18000795f  call    cs:__imp_CharNextW
0x180007965  mov     [rdi], rax
0x180007968  mov     rcx, rax; lpsz
0x18000796b  movzx   edx, word ptr [rax]
0x18000796e  xor     eax, eax
0x180007970  cmp     ax, dx
0x180007973  jz      loc_1800079FC
0x180007979  cmp     r14w, dx
0x18000797d  jnz     short loc_18000798B
0x18000797f  call    cs:__imp_CharNextW
0x180007985  cmp     r14w, [rax]
0x180007989  jnz     short loc_1800079FC
0x18000798b  mov     rsi, [rdi]
0x18000798e  cmp     r14w, [rsi]
0x180007992  jnz     short loc_1800079A3
0x180007994  mov     rcx, rsi; lpsz
0x180007997  call    cs:__imp_CharNextW
0x18000799d  mov     rsi, rax
0x1800079a0  mov     [rdi], rax
0x1800079a3  mov     rcx, rsi; lpsz
0x1800079a6  call    cs:__imp_CharNextW
0x1800079ac  mov     rdx, rax
0x1800079af  mov     [rdi], rax
0x1800079b2  sub     rdx, rsi
0x1800079b5  sar     rdx, 1
0x1800079b8  lea     rcx, [rdx+1]
0x1800079bc  lea     rcx, [rbx+rcx*2]
0x1800079c0  cmp     rcx, rbp
0x1800079c3  jnb     short loc_1800079EC
0x1800079c5  xor     ecx, ecx
0x1800079c7  test    edx, edx
0x1800079c9  jle     short loc_1800079DF
0x1800079cb  movzx   eax, word ptr [rsi]
0x1800079ce  inc     ecx
0x1800079d0  mov     [rbx], ax
0x1800079d3  lea     rsi, [rsi+2]
0x1800079d7  add     rbx, 2
0x1800079db  cmp     ecx, edx
0x1800079dd  jl      short loc_1800079CB
0x1800079df  mov     rcx, [rdi]
0x1800079e2  xor     eax, eax
0x1800079e4  movzx   edx, word ptr [rcx]
0x1800079e7  cmp     ax, dx
0x1800079ea  jnz     short loc_180007979
0x1800079ec  mov     eax, 80020009h
0x1800079f1  add     rsp, 20h
0x1800079f5  pop     r14
0x1800079f7  pop     rdi
0x1800079f8  pop     rsi
0x1800079f9  pop     rbp
0x1800079fa  pop     rbx
0x1800079fb  retn
0x1800079fc  mov     rcx, [rdi]
0x1800079ff  xor     eax, eax
0x180007a01  cmp     ax, [rcx]
0x180007a04  jz      short loc_1800079EC
0x180007a06  cmp     rbx, rbp
0x180007a09  jnb     short loc_1800079EC
0x180007a0b  mov     [rbx], ax
0x180007a0e  mov     rcx, [rdi]; lpsz
0x180007a11  call    cs:__imp_CharNextW
0x180007a17  mov     [rdi], rax
0x180007a1a  jmp     short loc_180007A8C
0x180007a1c  movzx   ecx, cx
0x180007a1f  sub     ecx, 9
0x180007a22  jz      short loc_180007A7E
0x180007a24  sub     ecx, 1
0x180007a27  jz      short loc_180007A7E
0x180007a29  sub     ecx, 3
0x180007a2c  jz      short loc_180007A7E
0x180007a2e  cmp     ecx, 13h
0x180007a31  jz      short loc_180007A7E
0x180007a33  mov     rcx, rsi; lpsz
0x180007a36  call    cs:__imp_CharNextW
0x180007a3c  mov     rdx, rax
0x180007a3f  mov     [rdi], rax
0x180007a42  sub     rdx, rsi
0x180007a45  sar     rdx, 1
0x180007a48  lea     rcx, [rdx+1]
0x180007a4c  lea     rcx, [rbx+rcx*2]
0x180007a50  cmp     rcx, rbp
0x180007a53  jnb     short loc_1800079EC
0x180007a55  xor     ecx, ecx
0x180007a57  test    edx, edx
0x180007a59  jle     short loc_180007A6F
0x180007a5b  movzx   eax, word ptr [rsi]
0x180007a5e  inc     ecx
0x180007a60  mov     [rbx], ax
0x180007a63  lea     rsi, [rsi+2]
0x180007a67  add     rbx, 2
0x180007a6b  cmp     ecx, edx
0x180007a6d  jl      short loc_180007A5B
0x180007a6f  mov     rsi, [rdi]
0x180007a72  xor     eax, eax
0x180007a74  cmp     ax, [rsi]
0x180007a77  jz      short loc_180007A7E
0x180007a79  movzx   ecx, word ptr [rsi]
0x180007a7c  jmp     short loc_180007A1C
0x180007a7e  cmp     rbx, rbp
0x180007a81  jnb     loc_1800079EC
0x180007a87  xor     eax, eax
0x180007a89  mov     [rbx], ax
0x180007a8c  xor     eax, eax
0x180007a8e  jmp     loc_1800079F1
```
