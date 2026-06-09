# ATL::CRegParser::NextToken(ushort *)

- ea: `0x180015400`
- end: `0x180015597`
- name: `?NextToken@CRegParser@ATL@@IEAAJPEAG@Z`
- size: `407`
- prototype: `__int64 __fastcall(ATL::CRegParser *__hidden this, unsigned __int16 *)`
- caller_count: `4`
- callee_count: `1`
- tags: ``

## callers

- `0x180012a40`
- `0x180015acc`
- `0x180015e40`
- `0x1800170d8`

## callees

- `0x180015400`

## import_xrefs

- `USER32!CharNextW` at `0x180015435`
- `USER32!CharNextW` at `0x180015463`
- `USER32!CharNextW` at `0x180015483`
- `USER32!CharNextW` at `0x18001549b`
- `USER32!CharNextW` at `0x1800154aa`
- `USER32!CharNextW` at `0x180015515`
- `USER32!CharNextW` at `0x18001553a`
- `USER32!CharNextW` at `0x180015435`
- `USER32!CharNextW` at `0x180015463`
- `USER32!CharNextW` at `0x180015483`
- `USER32!CharNextW` at `0x18001549b`
- `USER32!CharNextW` at `0x1800154aa`
- `USER32!CharNextW` at `0x180015515`
- `USER32!CharNextW` at `0x18001553a`

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
0x180015400  push    rbx
0x180015402  push    rbp
0x180015403  push    rsi
0x180015404  push    rdi
0x180015405  push    r14
0x180015407  sub     rsp, 20h
0x18001540b  mov     rbx, rdx
0x18001540e  mov     rdi, rcx
0x180015411  mov     rsi, [rdi]
0x180015414  movzx   ecx, word ptr [rsi]
0x180015417  mov     r8d, ecx
0x18001541a  sub     r8d, 9
0x18001541e  jz      short loc_180015432
0x180015420  sub     r8d, 1
0x180015424  jz      short loc_180015432
0x180015426  sub     r8d, 3
0x18001542a  jz      short loc_180015432
0x18001542c  cmp     r8d, 13h
0x180015430  jnz     short loc_180015440
0x180015432  mov     rcx, rsi; lpsz
0x180015435  call    cs:__imp_CharNextW
0x18001543b  mov     [rdi], rax
0x18001543e  jmp     short loc_180015411
0x180015440  xor     eax, eax
0x180015442  cmp     ax, cx
0x180015445  jz      loc_1800154F0
0x18001544b  lea     r14d, [rax+27h]
0x18001544f  lea     rbp, [rbx+2000h]
0x180015456  cmp     r14w, cx
0x18001545a  jnz     loc_180015520
0x180015460  mov     rcx, rsi; lpsz
0x180015463  call    cs:__imp_CharNextW
0x180015469  mov     [rdi], rax
0x18001546c  mov     rcx, rax; lpsz
0x18001546f  movzx   edx, word ptr [rax]
0x180015472  xor     eax, eax
0x180015474  cmp     ax, dx
0x180015477  jz      loc_180015500
0x18001547d  cmp     r14w, dx
0x180015481  jnz     short loc_18001548F
0x180015483  call    cs:__imp_CharNextW
0x180015489  cmp     r14w, [rax]
0x18001548d  jnz     short loc_180015500
0x18001548f  mov     rsi, [rdi]
0x180015492  cmp     r14w, [rsi]
0x180015496  jnz     short loc_1800154A7
0x180015498  mov     rcx, rsi; lpsz
0x18001549b  call    cs:__imp_CharNextW
0x1800154a1  mov     rsi, rax
0x1800154a4  mov     [rdi], rax
0x1800154a7  mov     rcx, rsi; lpsz
0x1800154aa  call    cs:__imp_CharNextW
0x1800154b0  mov     rdx, rax
0x1800154b3  mov     [rdi], rax
0x1800154b6  sub     rdx, rsi
0x1800154b9  sar     rdx, 1
0x1800154bc  lea     rcx, [rdx+1]
0x1800154c0  lea     rcx, [rbx+rcx*2]
0x1800154c4  cmp     rcx, rbp
0x1800154c7  jnb     short loc_1800154F0
0x1800154c9  xor     ecx, ecx
0x1800154cb  test    edx, edx
0x1800154cd  jle     short loc_1800154E3
0x1800154cf  movzx   eax, word ptr [rsi]
0x1800154d2  inc     ecx
0x1800154d4  mov     [rbx], ax
0x1800154d7  lea     rsi, [rsi+2]
0x1800154db  add     rbx, 2
0x1800154df  cmp     ecx, edx
0x1800154e1  jl      short loc_1800154CF
0x1800154e3  mov     rcx, [rdi]
0x1800154e6  xor     eax, eax
0x1800154e8  movzx   edx, word ptr [rcx]
0x1800154eb  cmp     ax, dx
0x1800154ee  jnz     short loc_18001547D
0x1800154f0  mov     eax, 80020009h
0x1800154f5  add     rsp, 20h
0x1800154f9  pop     r14
0x1800154fb  pop     rdi
0x1800154fc  pop     rsi
0x1800154fd  pop     rbp
0x1800154fe  pop     rbx
0x1800154ff  retn
0x180015500  mov     rcx, [rdi]
0x180015503  xor     eax, eax
0x180015505  cmp     ax, [rcx]
0x180015508  jz      short loc_1800154F0
0x18001550a  cmp     rbx, rbp
0x18001550d  jnb     short loc_1800154F0
0x18001550f  mov     [rbx], ax
0x180015512  mov     rcx, [rdi]; lpsz
0x180015515  call    cs:__imp_CharNextW
0x18001551b  mov     [rdi], rax
0x18001551e  jmp     short loc_180015590
0x180015520  movzx   ecx, cx
0x180015523  sub     ecx, 9
0x180015526  jz      short loc_180015582
0x180015528  sub     ecx, 1
0x18001552b  jz      short loc_180015582
0x18001552d  sub     ecx, 3
0x180015530  jz      short loc_180015582
0x180015532  cmp     ecx, 13h
0x180015535  jz      short loc_180015582
0x180015537  mov     rcx, rsi; lpsz
0x18001553a  call    cs:__imp_CharNextW
0x180015540  mov     rdx, rax
0x180015543  mov     [rdi], rax
0x180015546  sub     rdx, rsi
0x180015549  sar     rdx, 1
0x18001554c  lea     rcx, [rdx+1]
0x180015550  lea     rcx, [rbx+rcx*2]
0x180015554  cmp     rcx, rbp
0x180015557  jnb     short loc_1800154F0
0x180015559  xor     ecx, ecx
0x18001555b  test    edx, edx
0x18001555d  jle     short loc_180015573
0x18001555f  movzx   eax, word ptr [rsi]
0x180015562  inc     ecx
0x180015564  mov     [rbx], ax
0x180015567  lea     rsi, [rsi+2]
0x18001556b  add     rbx, 2
0x18001556f  cmp     ecx, edx
0x180015571  jl      short loc_18001555F
0x180015573  mov     rsi, [rdi]
0x180015576  xor     eax, eax
0x180015578  cmp     ax, [rsi]
0x18001557b  jz      short loc_180015582
0x18001557d  movzx   ecx, word ptr [rsi]
0x180015580  jmp     short loc_180015520
0x180015582  cmp     rbx, rbp
0x180015585  jnb     loc_1800154F0
0x18001558b  xor     eax, eax
0x18001558d  mov     [rbx], ax
0x180015590  xor     eax, eax
0x180015592  jmp     loc_1800154F5
```
