# ATL::CRegParser::NextToken(ushort *)

- ea: `0x1800061ec`
- end: `0x180006383`
- name: `?NextToken@CRegParser@ATL@@IEAAJPEAG@Z`
- size: `407`
- prototype: `__int64 __fastcall(ATL::CRegParser *__hidden this, unsigned __int16 *)`
- caller_count: `4`
- callee_count: `1`
- tags: ``

## callers

- `0x1800041c0`
- `0x1800069ac`
- `0x180006d1c`
- `0x180008140`

## callees

- `0x1800061ec`

## import_xrefs

- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x180006221`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x18000624f`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x18000626f`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x180006287`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x180006296`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x180006301`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x180006326`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x180006221`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x18000624f`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x18000626f`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x180006287`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x180006296`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x180006301`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x180006326`

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
0x1800061ec  push    rbx
0x1800061ee  push    rbp
0x1800061ef  push    rsi
0x1800061f0  push    rdi
0x1800061f1  push    r14
0x1800061f3  sub     rsp, 20h
0x1800061f7  mov     rbx, rdx
0x1800061fa  mov     rdi, rcx
0x1800061fd  mov     rsi, [rdi]
0x180006200  movzx   ecx, word ptr [rsi]
0x180006203  mov     r8d, ecx
0x180006206  sub     r8d, 9
0x18000620a  jz      short loc_18000621E
0x18000620c  sub     r8d, 1
0x180006210  jz      short loc_18000621E
0x180006212  sub     r8d, 3
0x180006216  jz      short loc_18000621E
0x180006218  cmp     r8d, 13h
0x18000621c  jnz     short loc_18000622C
0x18000621e  mov     rcx, rsi; lpsz
0x180006221  call    cs:__imp_CharNextW
0x180006227  mov     [rdi], rax
0x18000622a  jmp     short loc_1800061FD
0x18000622c  xor     eax, eax
0x18000622e  cmp     ax, cx
0x180006231  jz      loc_1800062DC
0x180006237  lea     r14d, [rax+27h]
0x18000623b  lea     rbp, [rbx+2000h]
0x180006242  cmp     r14w, cx
0x180006246  jnz     loc_18000630C
0x18000624c  mov     rcx, rsi; lpsz
0x18000624f  call    cs:__imp_CharNextW
0x180006255  mov     [rdi], rax
0x180006258  mov     rcx, rax; lpsz
0x18000625b  movzx   edx, word ptr [rax]
0x18000625e  xor     eax, eax
0x180006260  cmp     ax, dx
0x180006263  jz      loc_1800062EC
0x180006269  cmp     r14w, dx
0x18000626d  jnz     short loc_18000627B
0x18000626f  call    cs:__imp_CharNextW
0x180006275  cmp     r14w, [rax]
0x180006279  jnz     short loc_1800062EC
0x18000627b  mov     rsi, [rdi]
0x18000627e  cmp     r14w, [rsi]
0x180006282  jnz     short loc_180006293
0x180006284  mov     rcx, rsi; lpsz
0x180006287  call    cs:__imp_CharNextW
0x18000628d  mov     rsi, rax
0x180006290  mov     [rdi], rax
0x180006293  mov     rcx, rsi; lpsz
0x180006296  call    cs:__imp_CharNextW
0x18000629c  mov     rdx, rax
0x18000629f  mov     [rdi], rax
0x1800062a2  sub     rdx, rsi
0x1800062a5  sar     rdx, 1
0x1800062a8  lea     rcx, [rdx+1]
0x1800062ac  lea     rcx, [rbx+rcx*2]
0x1800062b0  cmp     rcx, rbp
0x1800062b3  jnb     short loc_1800062DC
0x1800062b5  xor     ecx, ecx
0x1800062b7  test    edx, edx
0x1800062b9  jle     short loc_1800062CF
0x1800062bb  movzx   eax, word ptr [rsi]
0x1800062be  inc     ecx
0x1800062c0  mov     [rbx], ax
0x1800062c3  lea     rsi, [rsi+2]
0x1800062c7  add     rbx, 2
0x1800062cb  cmp     ecx, edx
0x1800062cd  jl      short loc_1800062BB
0x1800062cf  mov     rcx, [rdi]
0x1800062d2  xor     eax, eax
0x1800062d4  movzx   edx, word ptr [rcx]
0x1800062d7  cmp     ax, dx
0x1800062da  jnz     short loc_180006269
0x1800062dc  mov     eax, 80020009h
0x1800062e1  add     rsp, 20h
0x1800062e5  pop     r14
0x1800062e7  pop     rdi
0x1800062e8  pop     rsi
0x1800062e9  pop     rbp
0x1800062ea  pop     rbx
0x1800062eb  retn
0x1800062ec  mov     rcx, [rdi]
0x1800062ef  xor     eax, eax
0x1800062f1  cmp     ax, [rcx]
0x1800062f4  jz      short loc_1800062DC
0x1800062f6  cmp     rbx, rbp
0x1800062f9  jnb     short loc_1800062DC
0x1800062fb  mov     [rbx], ax
0x1800062fe  mov     rcx, [rdi]; lpsz
0x180006301  call    cs:__imp_CharNextW
0x180006307  mov     [rdi], rax
0x18000630a  jmp     short loc_18000637C
0x18000630c  movzx   ecx, cx
0x18000630f  sub     ecx, 9
0x180006312  jz      short loc_18000636E
0x180006314  sub     ecx, 1
0x180006317  jz      short loc_18000636E
0x180006319  sub     ecx, 3
0x18000631c  jz      short loc_18000636E
0x18000631e  cmp     ecx, 13h
0x180006321  jz      short loc_18000636E
0x180006323  mov     rcx, rsi; lpsz
0x180006326  call    cs:__imp_CharNextW
0x18000632c  mov     rdx, rax
0x18000632f  mov     [rdi], rax
0x180006332  sub     rdx, rsi
0x180006335  sar     rdx, 1
0x180006338  lea     rcx, [rdx+1]
0x18000633c  lea     rcx, [rbx+rcx*2]
0x180006340  cmp     rcx, rbp
0x180006343  jnb     short loc_1800062DC
0x180006345  xor     ecx, ecx
0x180006347  test    edx, edx
0x180006349  jle     short loc_18000635F
0x18000634b  movzx   eax, word ptr [rsi]
0x18000634e  inc     ecx
0x180006350  mov     [rbx], ax
0x180006353  lea     rsi, [rsi+2]
0x180006357  add     rbx, 2
0x18000635b  cmp     ecx, edx
0x18000635d  jl      short loc_18000634B
0x18000635f  mov     rsi, [rdi]
0x180006362  xor     eax, eax
0x180006364  cmp     ax, [rsi]
0x180006367  jz      short loc_18000636E
0x180006369  movzx   ecx, word ptr [rsi]
0x18000636c  jmp     short loc_18000630C
0x18000636e  cmp     rbx, rbp
0x180006371  jnb     loc_1800062DC
0x180006377  xor     eax, eax
0x180006379  mov     [rbx], ax
0x18000637c  xor     eax, eax
0x18000637e  jmp     loc_1800062E1
```
