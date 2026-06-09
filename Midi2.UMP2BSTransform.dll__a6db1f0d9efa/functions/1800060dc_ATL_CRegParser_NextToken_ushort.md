# ATL::CRegParser::NextToken(ushort *)

- ea: `0x1800060dc`
- end: `0x180006273`
- name: `?NextToken@CRegParser@ATL@@IEAAJPEAG@Z`
- size: `407`
- prototype: `__int64 __fastcall(ATL::CRegParser *__hidden this, unsigned __int16 *)`
- caller_count: `4`
- callee_count: `1`
- tags: ``

## callers

- `0x1800040b0`
- `0x18000689c`
- `0x180006c0c`
- `0x180008020`

## callees

- `0x1800060dc`

## import_xrefs

- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x180006111`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x18000613f`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x18000615f`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x180006177`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x180006186`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x1800061f1`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x180006216`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x180006111`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x18000613f`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x18000615f`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x180006177`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x180006186`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x1800061f1`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x180006216`

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
0x1800060dc  push    rbx
0x1800060de  push    rbp
0x1800060df  push    rsi
0x1800060e0  push    rdi
0x1800060e1  push    r14
0x1800060e3  sub     rsp, 20h
0x1800060e7  mov     rbx, rdx
0x1800060ea  mov     rdi, rcx
0x1800060ed  mov     rsi, [rdi]
0x1800060f0  movzx   ecx, word ptr [rsi]
0x1800060f3  mov     r8d, ecx
0x1800060f6  sub     r8d, 9
0x1800060fa  jz      short loc_18000610E
0x1800060fc  sub     r8d, 1
0x180006100  jz      short loc_18000610E
0x180006102  sub     r8d, 3
0x180006106  jz      short loc_18000610E
0x180006108  cmp     r8d, 13h
0x18000610c  jnz     short loc_18000611C
0x18000610e  mov     rcx, rsi; lpsz
0x180006111  call    cs:__imp_CharNextW
0x180006117  mov     [rdi], rax
0x18000611a  jmp     short loc_1800060ED
0x18000611c  xor     eax, eax
0x18000611e  cmp     ax, cx
0x180006121  jz      loc_1800061CC
0x180006127  lea     r14d, [rax+27h]
0x18000612b  lea     rbp, [rbx+2000h]
0x180006132  cmp     r14w, cx
0x180006136  jnz     loc_1800061FC
0x18000613c  mov     rcx, rsi; lpsz
0x18000613f  call    cs:__imp_CharNextW
0x180006145  mov     [rdi], rax
0x180006148  mov     rcx, rax; lpsz
0x18000614b  movzx   edx, word ptr [rax]
0x18000614e  xor     eax, eax
0x180006150  cmp     ax, dx
0x180006153  jz      loc_1800061DC
0x180006159  cmp     r14w, dx
0x18000615d  jnz     short loc_18000616B
0x18000615f  call    cs:__imp_CharNextW
0x180006165  cmp     r14w, [rax]
0x180006169  jnz     short loc_1800061DC
0x18000616b  mov     rsi, [rdi]
0x18000616e  cmp     r14w, [rsi]
0x180006172  jnz     short loc_180006183
0x180006174  mov     rcx, rsi; lpsz
0x180006177  call    cs:__imp_CharNextW
0x18000617d  mov     rsi, rax
0x180006180  mov     [rdi], rax
0x180006183  mov     rcx, rsi; lpsz
0x180006186  call    cs:__imp_CharNextW
0x18000618c  mov     rdx, rax
0x18000618f  mov     [rdi], rax
0x180006192  sub     rdx, rsi
0x180006195  sar     rdx, 1
0x180006198  lea     rcx, [rdx+1]
0x18000619c  lea     rcx, [rbx+rcx*2]
0x1800061a0  cmp     rcx, rbp
0x1800061a3  jnb     short loc_1800061CC
0x1800061a5  xor     ecx, ecx
0x1800061a7  test    edx, edx
0x1800061a9  jle     short loc_1800061BF
0x1800061ab  movzx   eax, word ptr [rsi]
0x1800061ae  inc     ecx
0x1800061b0  mov     [rbx], ax
0x1800061b3  lea     rsi, [rsi+2]
0x1800061b7  add     rbx, 2
0x1800061bb  cmp     ecx, edx
0x1800061bd  jl      short loc_1800061AB
0x1800061bf  mov     rcx, [rdi]
0x1800061c2  xor     eax, eax
0x1800061c4  movzx   edx, word ptr [rcx]
0x1800061c7  cmp     ax, dx
0x1800061ca  jnz     short loc_180006159
0x1800061cc  mov     eax, 80020009h
0x1800061d1  add     rsp, 20h
0x1800061d5  pop     r14
0x1800061d7  pop     rdi
0x1800061d8  pop     rsi
0x1800061d9  pop     rbp
0x1800061da  pop     rbx
0x1800061db  retn
0x1800061dc  mov     rcx, [rdi]
0x1800061df  xor     eax, eax
0x1800061e1  cmp     ax, [rcx]
0x1800061e4  jz      short loc_1800061CC
0x1800061e6  cmp     rbx, rbp
0x1800061e9  jnb     short loc_1800061CC
0x1800061eb  mov     [rbx], ax
0x1800061ee  mov     rcx, [rdi]; lpsz
0x1800061f1  call    cs:__imp_CharNextW
0x1800061f7  mov     [rdi], rax
0x1800061fa  jmp     short loc_18000626C
0x1800061fc  movzx   ecx, cx
0x1800061ff  sub     ecx, 9
0x180006202  jz      short loc_18000625E
0x180006204  sub     ecx, 1
0x180006207  jz      short loc_18000625E
0x180006209  sub     ecx, 3
0x18000620c  jz      short loc_18000625E
0x18000620e  cmp     ecx, 13h
0x180006211  jz      short loc_18000625E
0x180006213  mov     rcx, rsi; lpsz
0x180006216  call    cs:__imp_CharNextW
0x18000621c  mov     rdx, rax
0x18000621f  mov     [rdi], rax
0x180006222  sub     rdx, rsi
0x180006225  sar     rdx, 1
0x180006228  lea     rcx, [rdx+1]
0x18000622c  lea     rcx, [rbx+rcx*2]
0x180006230  cmp     rcx, rbp
0x180006233  jnb     short loc_1800061CC
0x180006235  xor     ecx, ecx
0x180006237  test    edx, edx
0x180006239  jle     short loc_18000624F
0x18000623b  movzx   eax, word ptr [rsi]
0x18000623e  inc     ecx
0x180006240  mov     [rbx], ax
0x180006243  lea     rsi, [rsi+2]
0x180006247  add     rbx, 2
0x18000624b  cmp     ecx, edx
0x18000624d  jl      short loc_18000623B
0x18000624f  mov     rsi, [rdi]
0x180006252  xor     eax, eax
0x180006254  cmp     ax, [rsi]
0x180006257  jz      short loc_18000625E
0x180006259  movzx   ecx, word ptr [rsi]
0x18000625c  jmp     short loc_1800061FC
0x18000625e  cmp     rbx, rbp
0x180006261  jnb     loc_1800061CC
0x180006267  xor     eax, eax
0x180006269  mov     [rbx], ax
0x18000626c  xor     eax, eax
0x18000626e  jmp     loc_1800061D1
```
