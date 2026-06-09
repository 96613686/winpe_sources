# ATL::CRegParser::NextToken(ushort *)

- ea: `0x1800067ac`
- end: `0x180006943`
- name: `?NextToken@CRegParser@ATL@@IEAAJPEAG@Z`
- size: `407`
- prototype: `__int64 __fastcall(ATL::CRegParser *__hidden this, unsigned __int16 *)`
- caller_count: `4`
- callee_count: `1`
- tags: ``

## callers

- `0x180004770`
- `0x180006f6c`
- `0x1800072dc`
- `0x180008700`

## callees

- `0x1800067ac`

## import_xrefs

- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x1800067e1`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x18000680f`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x18000682f`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x180006847`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x180006856`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x1800068c1`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x1800068e6`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x1800067e1`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x18000680f`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x18000682f`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x180006847`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x180006856`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x1800068c1`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x1800068e6`

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
0x1800067ac  push    rbx
0x1800067ae  push    rbp
0x1800067af  push    rsi
0x1800067b0  push    rdi
0x1800067b1  push    r14
0x1800067b3  sub     rsp, 20h
0x1800067b7  mov     rbx, rdx
0x1800067ba  mov     rdi, rcx
0x1800067bd  mov     rsi, [rdi]
0x1800067c0  movzx   ecx, word ptr [rsi]
0x1800067c3  mov     r8d, ecx
0x1800067c6  sub     r8d, 9
0x1800067ca  jz      short loc_1800067DE
0x1800067cc  sub     r8d, 1
0x1800067d0  jz      short loc_1800067DE
0x1800067d2  sub     r8d, 3
0x1800067d6  jz      short loc_1800067DE
0x1800067d8  cmp     r8d, 13h
0x1800067dc  jnz     short loc_1800067EC
0x1800067de  mov     rcx, rsi; lpsz
0x1800067e1  call    cs:__imp_CharNextW
0x1800067e7  mov     [rdi], rax
0x1800067ea  jmp     short loc_1800067BD
0x1800067ec  xor     eax, eax
0x1800067ee  cmp     ax, cx
0x1800067f1  jz      loc_18000689C
0x1800067f7  lea     r14d, [rax+27h]
0x1800067fb  lea     rbp, [rbx+2000h]
0x180006802  cmp     r14w, cx
0x180006806  jnz     loc_1800068CC
0x18000680c  mov     rcx, rsi; lpsz
0x18000680f  call    cs:__imp_CharNextW
0x180006815  mov     [rdi], rax
0x180006818  mov     rcx, rax; lpsz
0x18000681b  movzx   edx, word ptr [rax]
0x18000681e  xor     eax, eax
0x180006820  cmp     ax, dx
0x180006823  jz      loc_1800068AC
0x180006829  cmp     r14w, dx
0x18000682d  jnz     short loc_18000683B
0x18000682f  call    cs:__imp_CharNextW
0x180006835  cmp     r14w, [rax]
0x180006839  jnz     short loc_1800068AC
0x18000683b  mov     rsi, [rdi]
0x18000683e  cmp     r14w, [rsi]
0x180006842  jnz     short loc_180006853
0x180006844  mov     rcx, rsi; lpsz
0x180006847  call    cs:__imp_CharNextW
0x18000684d  mov     rsi, rax
0x180006850  mov     [rdi], rax
0x180006853  mov     rcx, rsi; lpsz
0x180006856  call    cs:__imp_CharNextW
0x18000685c  mov     rdx, rax
0x18000685f  mov     [rdi], rax
0x180006862  sub     rdx, rsi
0x180006865  sar     rdx, 1
0x180006868  lea     rcx, [rdx+1]
0x18000686c  lea     rcx, [rbx+rcx*2]
0x180006870  cmp     rcx, rbp
0x180006873  jnb     short loc_18000689C
0x180006875  xor     ecx, ecx
0x180006877  test    edx, edx
0x180006879  jle     short loc_18000688F
0x18000687b  movzx   eax, word ptr [rsi]
0x18000687e  inc     ecx
0x180006880  mov     [rbx], ax
0x180006883  lea     rsi, [rsi+2]
0x180006887  add     rbx, 2
0x18000688b  cmp     ecx, edx
0x18000688d  jl      short loc_18000687B
0x18000688f  mov     rcx, [rdi]
0x180006892  xor     eax, eax
0x180006894  movzx   edx, word ptr [rcx]
0x180006897  cmp     ax, dx
0x18000689a  jnz     short loc_180006829
0x18000689c  mov     eax, 80020009h
0x1800068a1  add     rsp, 20h
0x1800068a5  pop     r14
0x1800068a7  pop     rdi
0x1800068a8  pop     rsi
0x1800068a9  pop     rbp
0x1800068aa  pop     rbx
0x1800068ab  retn
0x1800068ac  mov     rcx, [rdi]
0x1800068af  xor     eax, eax
0x1800068b1  cmp     ax, [rcx]
0x1800068b4  jz      short loc_18000689C
0x1800068b6  cmp     rbx, rbp
0x1800068b9  jnb     short loc_18000689C
0x1800068bb  mov     [rbx], ax
0x1800068be  mov     rcx, [rdi]; lpsz
0x1800068c1  call    cs:__imp_CharNextW
0x1800068c7  mov     [rdi], rax
0x1800068ca  jmp     short loc_18000693C
0x1800068cc  movzx   ecx, cx
0x1800068cf  sub     ecx, 9
0x1800068d2  jz      short loc_18000692E
0x1800068d4  sub     ecx, 1
0x1800068d7  jz      short loc_18000692E
0x1800068d9  sub     ecx, 3
0x1800068dc  jz      short loc_18000692E
0x1800068de  cmp     ecx, 13h
0x1800068e1  jz      short loc_18000692E
0x1800068e3  mov     rcx, rsi; lpsz
0x1800068e6  call    cs:__imp_CharNextW
0x1800068ec  mov     rdx, rax
0x1800068ef  mov     [rdi], rax
0x1800068f2  sub     rdx, rsi
0x1800068f5  sar     rdx, 1
0x1800068f8  lea     rcx, [rdx+1]
0x1800068fc  lea     rcx, [rbx+rcx*2]
0x180006900  cmp     rcx, rbp
0x180006903  jnb     short loc_18000689C
0x180006905  xor     ecx, ecx
0x180006907  test    edx, edx
0x180006909  jle     short loc_18000691F
0x18000690b  movzx   eax, word ptr [rsi]
0x18000690e  inc     ecx
0x180006910  mov     [rbx], ax
0x180006913  lea     rsi, [rsi+2]
0x180006917  add     rbx, 2
0x18000691b  cmp     ecx, edx
0x18000691d  jl      short loc_18000690B
0x18000691f  mov     rsi, [rdi]
0x180006922  xor     eax, eax
0x180006924  cmp     ax, [rsi]
0x180006927  jz      short loc_18000692E
0x180006929  movzx   ecx, word ptr [rsi]
0x18000692c  jmp     short loc_1800068CC
0x18000692e  cmp     rbx, rbp
0x180006931  jnb     loc_18000689C
0x180006937  xor     eax, eax
0x180006939  mov     [rbx], ax
0x18000693c  xor     eax, eax
0x18000693e  jmp     loc_1800068A1
```
