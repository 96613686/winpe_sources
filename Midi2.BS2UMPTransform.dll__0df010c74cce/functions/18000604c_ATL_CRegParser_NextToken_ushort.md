# ATL::CRegParser::NextToken(ushort *)

- ea: `0x18000604c`
- end: `0x1800061e3`
- name: `?NextToken@CRegParser@ATL@@IEAAJPEAG@Z`
- size: `407`
- prototype: `__int64 __fastcall(ATL::CRegParser *__hidden this, unsigned __int16 *)`
- caller_count: `4`
- callee_count: `1`
- tags: ``

## callers

- `0x180004020`
- `0x18000680c`
- `0x180006b7c`
- `0x180007f90`

## callees

- `0x18000604c`

## import_xrefs

- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x180006081`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x1800060af`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x1800060cf`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x1800060e7`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x1800060f6`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x180006161`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x180006186`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x180006081`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x1800060af`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x1800060cf`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x1800060e7`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x1800060f6`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x180006161`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x180006186`

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
0x18000604c  push    rbx
0x18000604e  push    rbp
0x18000604f  push    rsi
0x180006050  push    rdi
0x180006051  push    r14
0x180006053  sub     rsp, 20h
0x180006057  mov     rbx, rdx
0x18000605a  mov     rdi, rcx
0x18000605d  mov     rsi, [rdi]
0x180006060  movzx   ecx, word ptr [rsi]
0x180006063  mov     r8d, ecx
0x180006066  sub     r8d, 9
0x18000606a  jz      short loc_18000607E
0x18000606c  sub     r8d, 1
0x180006070  jz      short loc_18000607E
0x180006072  sub     r8d, 3
0x180006076  jz      short loc_18000607E
0x180006078  cmp     r8d, 13h
0x18000607c  jnz     short loc_18000608C
0x18000607e  mov     rcx, rsi; lpsz
0x180006081  call    cs:__imp_CharNextW
0x180006087  mov     [rdi], rax
0x18000608a  jmp     short loc_18000605D
0x18000608c  xor     eax, eax
0x18000608e  cmp     ax, cx
0x180006091  jz      loc_18000613C
0x180006097  lea     r14d, [rax+27h]
0x18000609b  lea     rbp, [rbx+2000h]
0x1800060a2  cmp     r14w, cx
0x1800060a6  jnz     loc_18000616C
0x1800060ac  mov     rcx, rsi; lpsz
0x1800060af  call    cs:__imp_CharNextW
0x1800060b5  mov     [rdi], rax
0x1800060b8  mov     rcx, rax; lpsz
0x1800060bb  movzx   edx, word ptr [rax]
0x1800060be  xor     eax, eax
0x1800060c0  cmp     ax, dx
0x1800060c3  jz      loc_18000614C
0x1800060c9  cmp     r14w, dx
0x1800060cd  jnz     short loc_1800060DB
0x1800060cf  call    cs:__imp_CharNextW
0x1800060d5  cmp     r14w, [rax]
0x1800060d9  jnz     short loc_18000614C
0x1800060db  mov     rsi, [rdi]
0x1800060de  cmp     r14w, [rsi]
0x1800060e2  jnz     short loc_1800060F3
0x1800060e4  mov     rcx, rsi; lpsz
0x1800060e7  call    cs:__imp_CharNextW
0x1800060ed  mov     rsi, rax
0x1800060f0  mov     [rdi], rax
0x1800060f3  mov     rcx, rsi; lpsz
0x1800060f6  call    cs:__imp_CharNextW
0x1800060fc  mov     rdx, rax
0x1800060ff  mov     [rdi], rax
0x180006102  sub     rdx, rsi
0x180006105  sar     rdx, 1
0x180006108  lea     rcx, [rdx+1]
0x18000610c  lea     rcx, [rbx+rcx*2]
0x180006110  cmp     rcx, rbp
0x180006113  jnb     short loc_18000613C
0x180006115  xor     ecx, ecx
0x180006117  test    edx, edx
0x180006119  jle     short loc_18000612F
0x18000611b  movzx   eax, word ptr [rsi]
0x18000611e  inc     ecx
0x180006120  mov     [rbx], ax
0x180006123  lea     rsi, [rsi+2]
0x180006127  add     rbx, 2
0x18000612b  cmp     ecx, edx
0x18000612d  jl      short loc_18000611B
0x18000612f  mov     rcx, [rdi]
0x180006132  xor     eax, eax
0x180006134  movzx   edx, word ptr [rcx]
0x180006137  cmp     ax, dx
0x18000613a  jnz     short loc_1800060C9
0x18000613c  mov     eax, 80020009h
0x180006141  add     rsp, 20h
0x180006145  pop     r14
0x180006147  pop     rdi
0x180006148  pop     rsi
0x180006149  pop     rbp
0x18000614a  pop     rbx
0x18000614b  retn
0x18000614c  mov     rcx, [rdi]
0x18000614f  xor     eax, eax
0x180006151  cmp     ax, [rcx]
0x180006154  jz      short loc_18000613C
0x180006156  cmp     rbx, rbp
0x180006159  jnb     short loc_18000613C
0x18000615b  mov     [rbx], ax
0x18000615e  mov     rcx, [rdi]; lpsz
0x180006161  call    cs:__imp_CharNextW
0x180006167  mov     [rdi], rax
0x18000616a  jmp     short loc_1800061DC
0x18000616c  movzx   ecx, cx
0x18000616f  sub     ecx, 9
0x180006172  jz      short loc_1800061CE
0x180006174  sub     ecx, 1
0x180006177  jz      short loc_1800061CE
0x180006179  sub     ecx, 3
0x18000617c  jz      short loc_1800061CE
0x18000617e  cmp     ecx, 13h
0x180006181  jz      short loc_1800061CE
0x180006183  mov     rcx, rsi; lpsz
0x180006186  call    cs:__imp_CharNextW
0x18000618c  mov     rdx, rax
0x18000618f  mov     [rdi], rax
0x180006192  sub     rdx, rsi
0x180006195  sar     rdx, 1
0x180006198  lea     rcx, [rdx+1]
0x18000619c  lea     rcx, [rbx+rcx*2]
0x1800061a0  cmp     rcx, rbp
0x1800061a3  jnb     short loc_18000613C
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
0x1800061bf  mov     rsi, [rdi]
0x1800061c2  xor     eax, eax
0x1800061c4  cmp     ax, [rsi]
0x1800061c7  jz      short loc_1800061CE
0x1800061c9  movzx   ecx, word ptr [rsi]
0x1800061cc  jmp     short loc_18000616C
0x1800061ce  cmp     rbx, rbp
0x1800061d1  jnb     loc_18000613C
0x1800061d7  xor     eax, eax
0x1800061d9  mov     [rbx], ax
0x1800061dc  xor     eax, eax
0x1800061de  jmp     loc_180006141
```
