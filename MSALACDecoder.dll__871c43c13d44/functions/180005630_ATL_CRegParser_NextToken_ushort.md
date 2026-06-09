# ATL::CRegParser::NextToken(ushort *)

- ea: `0x180005630`
- end: `0x1800057c7`
- name: `?NextToken@CRegParser@ATL@@IEAAJPEAG@Z`
- size: `407`
- prototype: `__int64 __fastcall(ATL::CRegParser *__hidden this, unsigned __int16 *)`
- caller_count: `4`
- callee_count: `1`
- tags: ``

## callers

- `0x18000462c`
- `0x180005d08`
- `0x18000607c`
- `0x180006a18`

## callees

- `0x180005630`

## import_xrefs

- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x180005665`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x180005693`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x1800056b3`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x1800056cb`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x1800056da`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x180005745`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x18000576a`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x180005665`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x180005693`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x1800056b3`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x1800056cb`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x1800056da`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x180005745`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x18000576a`

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
0x180005630  push    rbx
0x180005632  push    rbp
0x180005633  push    rsi
0x180005634  push    rdi
0x180005635  push    r14
0x180005637  sub     rsp, 20h
0x18000563b  mov     rbx, rdx
0x18000563e  mov     rdi, rcx
0x180005641  mov     rsi, [rdi]
0x180005644  movzx   ecx, word ptr [rsi]
0x180005647  mov     r8d, ecx
0x18000564a  sub     r8d, 9
0x18000564e  jz      short loc_180005662
0x180005650  sub     r8d, 1
0x180005654  jz      short loc_180005662
0x180005656  sub     r8d, 3
0x18000565a  jz      short loc_180005662
0x18000565c  cmp     r8d, 13h
0x180005660  jnz     short loc_180005670
0x180005662  mov     rcx, rsi; lpsz
0x180005665  call    cs:__imp_CharNextW
0x18000566b  mov     [rdi], rax
0x18000566e  jmp     short loc_180005641
0x180005670  xor     eax, eax
0x180005672  cmp     ax, cx
0x180005675  jz      loc_180005720
0x18000567b  lea     r14d, [rax+27h]
0x18000567f  lea     rbp, [rbx+2000h]
0x180005686  cmp     r14w, cx
0x18000568a  jnz     loc_180005750
0x180005690  mov     rcx, rsi; lpsz
0x180005693  call    cs:__imp_CharNextW
0x180005699  mov     [rdi], rax
0x18000569c  mov     rcx, rax; lpsz
0x18000569f  movzx   edx, word ptr [rax]
0x1800056a2  xor     eax, eax
0x1800056a4  cmp     ax, dx
0x1800056a7  jz      loc_180005730
0x1800056ad  cmp     r14w, dx
0x1800056b1  jnz     short loc_1800056BF
0x1800056b3  call    cs:__imp_CharNextW
0x1800056b9  cmp     r14w, [rax]
0x1800056bd  jnz     short loc_180005730
0x1800056bf  mov     rsi, [rdi]
0x1800056c2  cmp     r14w, [rsi]
0x1800056c6  jnz     short loc_1800056D7
0x1800056c8  mov     rcx, rsi; lpsz
0x1800056cb  call    cs:__imp_CharNextW
0x1800056d1  mov     rsi, rax
0x1800056d4  mov     [rdi], rax
0x1800056d7  mov     rcx, rsi; lpsz
0x1800056da  call    cs:__imp_CharNextW
0x1800056e0  mov     rdx, rax
0x1800056e3  mov     [rdi], rax
0x1800056e6  sub     rdx, rsi
0x1800056e9  sar     rdx, 1
0x1800056ec  lea     rcx, [rdx+1]
0x1800056f0  lea     rcx, [rbx+rcx*2]
0x1800056f4  cmp     rcx, rbp
0x1800056f7  jnb     short loc_180005720
0x1800056f9  xor     ecx, ecx
0x1800056fb  test    edx, edx
0x1800056fd  jle     short loc_180005713
0x1800056ff  movzx   eax, word ptr [rsi]
0x180005702  inc     ecx
0x180005704  mov     [rbx], ax
0x180005707  lea     rsi, [rsi+2]
0x18000570b  add     rbx, 2
0x18000570f  cmp     ecx, edx
0x180005711  jl      short loc_1800056FF
0x180005713  mov     rcx, [rdi]
0x180005716  xor     eax, eax
0x180005718  movzx   edx, word ptr [rcx]
0x18000571b  cmp     ax, dx
0x18000571e  jnz     short loc_1800056AD
0x180005720  mov     eax, 80020009h
0x180005725  add     rsp, 20h
0x180005729  pop     r14
0x18000572b  pop     rdi
0x18000572c  pop     rsi
0x18000572d  pop     rbp
0x18000572e  pop     rbx
0x18000572f  retn
0x180005730  mov     rcx, [rdi]
0x180005733  xor     eax, eax
0x180005735  cmp     ax, [rcx]
0x180005738  jz      short loc_180005720
0x18000573a  cmp     rbx, rbp
0x18000573d  jnb     short loc_180005720
0x18000573f  mov     [rbx], ax
0x180005742  mov     rcx, [rdi]; lpsz
0x180005745  call    cs:__imp_CharNextW
0x18000574b  mov     [rdi], rax
0x18000574e  jmp     short loc_1800057C0
0x180005750  movzx   ecx, cx
0x180005753  sub     ecx, 9
0x180005756  jz      short loc_1800057B2
0x180005758  sub     ecx, 1
0x18000575b  jz      short loc_1800057B2
0x18000575d  sub     ecx, 3
0x180005760  jz      short loc_1800057B2
0x180005762  cmp     ecx, 13h
0x180005765  jz      short loc_1800057B2
0x180005767  mov     rcx, rsi; lpsz
0x18000576a  call    cs:__imp_CharNextW
0x180005770  mov     rdx, rax
0x180005773  mov     [rdi], rax
0x180005776  sub     rdx, rsi
0x180005779  sar     rdx, 1
0x18000577c  lea     rcx, [rdx+1]
0x180005780  lea     rcx, [rbx+rcx*2]
0x180005784  cmp     rcx, rbp
0x180005787  jnb     short loc_180005720
0x180005789  xor     ecx, ecx
0x18000578b  test    edx, edx
0x18000578d  jle     short loc_1800057A3
0x18000578f  movzx   eax, word ptr [rsi]
0x180005792  inc     ecx
0x180005794  mov     [rbx], ax
0x180005797  lea     rsi, [rsi+2]
0x18000579b  add     rbx, 2
0x18000579f  cmp     ecx, edx
0x1800057a1  jl      short loc_18000578F
0x1800057a3  mov     rsi, [rdi]
0x1800057a6  xor     eax, eax
0x1800057a8  cmp     ax, [rsi]
0x1800057ab  jz      short loc_1800057B2
0x1800057ad  movzx   ecx, word ptr [rsi]
0x1800057b0  jmp     short loc_180005750
0x1800057b2  cmp     rbx, rbp
0x1800057b5  jnb     loc_180005720
0x1800057bb  xor     eax, eax
0x1800057bd  mov     [rbx], ax
0x1800057c0  xor     eax, eax
0x1800057c2  jmp     loc_180005725
```
