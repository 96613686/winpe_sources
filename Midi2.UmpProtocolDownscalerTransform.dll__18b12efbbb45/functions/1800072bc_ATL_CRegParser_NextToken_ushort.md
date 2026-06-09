# ATL::CRegParser::NextToken(ushort *)

- ea: `0x1800072bc`
- end: `0x180007453`
- name: `?NextToken@CRegParser@ATL@@IEAAJPEAG@Z`
- size: `407`
- prototype: `__int64 __fastcall(ATL::CRegParser *__hidden this, unsigned __int16 *)`
- caller_count: `4`
- callee_count: `1`
- tags: ``

## callers

- `0x180005290`
- `0x180007a7c`
- `0x180007dec`
- `0x180009200`

## callees

- `0x1800072bc`

## import_xrefs

- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x1800072f1`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x18000731f`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x18000733f`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x180007357`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x180007366`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x1800073d1`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x1800073f6`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x1800072f1`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x18000731f`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x18000733f`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x180007357`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x180007366`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x1800073d1`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x1800073f6`

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
0x1800072bc  push    rbx
0x1800072be  push    rbp
0x1800072bf  push    rsi
0x1800072c0  push    rdi
0x1800072c1  push    r14
0x1800072c3  sub     rsp, 20h
0x1800072c7  mov     rbx, rdx
0x1800072ca  mov     rdi, rcx
0x1800072cd  mov     rsi, [rdi]
0x1800072d0  movzx   ecx, word ptr [rsi]
0x1800072d3  mov     r8d, ecx
0x1800072d6  sub     r8d, 9
0x1800072da  jz      short loc_1800072EE
0x1800072dc  sub     r8d, 1
0x1800072e0  jz      short loc_1800072EE
0x1800072e2  sub     r8d, 3
0x1800072e6  jz      short loc_1800072EE
0x1800072e8  cmp     r8d, 13h
0x1800072ec  jnz     short loc_1800072FC
0x1800072ee  mov     rcx, rsi; lpsz
0x1800072f1  call    cs:__imp_CharNextW
0x1800072f7  mov     [rdi], rax
0x1800072fa  jmp     short loc_1800072CD
0x1800072fc  xor     eax, eax
0x1800072fe  cmp     ax, cx
0x180007301  jz      loc_1800073AC
0x180007307  lea     r14d, [rax+27h]
0x18000730b  lea     rbp, [rbx+2000h]
0x180007312  cmp     r14w, cx
0x180007316  jnz     loc_1800073DC
0x18000731c  mov     rcx, rsi; lpsz
0x18000731f  call    cs:__imp_CharNextW
0x180007325  mov     [rdi], rax
0x180007328  mov     rcx, rax; lpsz
0x18000732b  movzx   edx, word ptr [rax]
0x18000732e  xor     eax, eax
0x180007330  cmp     ax, dx
0x180007333  jz      loc_1800073BC
0x180007339  cmp     r14w, dx
0x18000733d  jnz     short loc_18000734B
0x18000733f  call    cs:__imp_CharNextW
0x180007345  cmp     r14w, [rax]
0x180007349  jnz     short loc_1800073BC
0x18000734b  mov     rsi, [rdi]
0x18000734e  cmp     r14w, [rsi]
0x180007352  jnz     short loc_180007363
0x180007354  mov     rcx, rsi; lpsz
0x180007357  call    cs:__imp_CharNextW
0x18000735d  mov     rsi, rax
0x180007360  mov     [rdi], rax
0x180007363  mov     rcx, rsi; lpsz
0x180007366  call    cs:__imp_CharNextW
0x18000736c  mov     rdx, rax
0x18000736f  mov     [rdi], rax
0x180007372  sub     rdx, rsi
0x180007375  sar     rdx, 1
0x180007378  lea     rcx, [rdx+1]
0x18000737c  lea     rcx, [rbx+rcx*2]
0x180007380  cmp     rcx, rbp
0x180007383  jnb     short loc_1800073AC
0x180007385  xor     ecx, ecx
0x180007387  test    edx, edx
0x180007389  jle     short loc_18000739F
0x18000738b  movzx   eax, word ptr [rsi]
0x18000738e  inc     ecx
0x180007390  mov     [rbx], ax
0x180007393  lea     rsi, [rsi+2]
0x180007397  add     rbx, 2
0x18000739b  cmp     ecx, edx
0x18000739d  jl      short loc_18000738B
0x18000739f  mov     rcx, [rdi]
0x1800073a2  xor     eax, eax
0x1800073a4  movzx   edx, word ptr [rcx]
0x1800073a7  cmp     ax, dx
0x1800073aa  jnz     short loc_180007339
0x1800073ac  mov     eax, 80020009h
0x1800073b1  add     rsp, 20h
0x1800073b5  pop     r14
0x1800073b7  pop     rdi
0x1800073b8  pop     rsi
0x1800073b9  pop     rbp
0x1800073ba  pop     rbx
0x1800073bb  retn
0x1800073bc  mov     rcx, [rdi]
0x1800073bf  xor     eax, eax
0x1800073c1  cmp     ax, [rcx]
0x1800073c4  jz      short loc_1800073AC
0x1800073c6  cmp     rbx, rbp
0x1800073c9  jnb     short loc_1800073AC
0x1800073cb  mov     [rbx], ax
0x1800073ce  mov     rcx, [rdi]; lpsz
0x1800073d1  call    cs:__imp_CharNextW
0x1800073d7  mov     [rdi], rax
0x1800073da  jmp     short loc_18000744C
0x1800073dc  movzx   ecx, cx
0x1800073df  sub     ecx, 9
0x1800073e2  jz      short loc_18000743E
0x1800073e4  sub     ecx, 1
0x1800073e7  jz      short loc_18000743E
0x1800073e9  sub     ecx, 3
0x1800073ec  jz      short loc_18000743E
0x1800073ee  cmp     ecx, 13h
0x1800073f1  jz      short loc_18000743E
0x1800073f3  mov     rcx, rsi; lpsz
0x1800073f6  call    cs:__imp_CharNextW
0x1800073fc  mov     rdx, rax
0x1800073ff  mov     [rdi], rax
0x180007402  sub     rdx, rsi
0x180007405  sar     rdx, 1
0x180007408  lea     rcx, [rdx+1]
0x18000740c  lea     rcx, [rbx+rcx*2]
0x180007410  cmp     rcx, rbp
0x180007413  jnb     short loc_1800073AC
0x180007415  xor     ecx, ecx
0x180007417  test    edx, edx
0x180007419  jle     short loc_18000742F
0x18000741b  movzx   eax, word ptr [rsi]
0x18000741e  inc     ecx
0x180007420  mov     [rbx], ax
0x180007423  lea     rsi, [rsi+2]
0x180007427  add     rbx, 2
0x18000742b  cmp     ecx, edx
0x18000742d  jl      short loc_18000741B
0x18000742f  mov     rsi, [rdi]
0x180007432  xor     eax, eax
0x180007434  cmp     ax, [rsi]
0x180007437  jz      short loc_18000743E
0x180007439  movzx   ecx, word ptr [rsi]
0x18000743c  jmp     short loc_1800073DC
0x18000743e  cmp     rbx, rbp
0x180007441  jnb     loc_1800073AC
0x180007447  xor     eax, eax
0x180007449  mov     [rbx], ax
0x18000744c  xor     eax, eax
0x18000744e  jmp     loc_1800073B1
```
