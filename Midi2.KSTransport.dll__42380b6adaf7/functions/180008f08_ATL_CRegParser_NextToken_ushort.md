# ATL::CRegParser::NextToken(ushort *)

- ea: `0x180008f08`
- end: `0x18000909f`
- name: `?NextToken@CRegParser@ATL@@IEAAJPEAG@Z`
- size: `407`
- prototype: `__int64 __fastcall(ATL::CRegParser *__hidden this, unsigned __int16 *)`
- caller_count: `4`
- callee_count: `1`
- tags: ``

## callers

- `0x180006df0`
- `0x180009954`
- `0x180009cc4`
- `0x18000b0f0`

## callees

- `0x180008f08`

## import_xrefs

- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x180008f3d`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x180008f6b`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x180008f8b`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x180008fa3`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x180008fb2`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x18000901d`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x180009042`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x180008f3d`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x180008f6b`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x180008f8b`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x180008fa3`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x180008fb2`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x18000901d`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x180009042`

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
0x180008f08  push    rbx
0x180008f0a  push    rbp
0x180008f0b  push    rsi
0x180008f0c  push    rdi
0x180008f0d  push    r14
0x180008f0f  sub     rsp, 20h
0x180008f13  mov     rbx, rdx
0x180008f16  mov     rdi, rcx
0x180008f19  mov     rsi, [rdi]
0x180008f1c  movzx   ecx, word ptr [rsi]
0x180008f1f  mov     r8d, ecx
0x180008f22  sub     r8d, 9
0x180008f26  jz      short loc_180008F3A
0x180008f28  sub     r8d, 1
0x180008f2c  jz      short loc_180008F3A
0x180008f2e  sub     r8d, 3
0x180008f32  jz      short loc_180008F3A
0x180008f34  cmp     r8d, 13h
0x180008f38  jnz     short loc_180008F48
0x180008f3a  mov     rcx, rsi; lpsz
0x180008f3d  call    cs:__imp_CharNextW
0x180008f43  mov     [rdi], rax
0x180008f46  jmp     short loc_180008F19
0x180008f48  xor     eax, eax
0x180008f4a  cmp     ax, cx
0x180008f4d  jz      loc_180008FF8
0x180008f53  lea     r14d, [rax+27h]
0x180008f57  lea     rbp, [rbx+2000h]
0x180008f5e  cmp     r14w, cx
0x180008f62  jnz     loc_180009028
0x180008f68  mov     rcx, rsi; lpsz
0x180008f6b  call    cs:__imp_CharNextW
0x180008f71  mov     [rdi], rax
0x180008f74  mov     rcx, rax; lpsz
0x180008f77  movzx   edx, word ptr [rax]
0x180008f7a  xor     eax, eax
0x180008f7c  cmp     ax, dx
0x180008f7f  jz      loc_180009008
0x180008f85  cmp     r14w, dx
0x180008f89  jnz     short loc_180008F97
0x180008f8b  call    cs:__imp_CharNextW
0x180008f91  cmp     r14w, [rax]
0x180008f95  jnz     short loc_180009008
0x180008f97  mov     rsi, [rdi]
0x180008f9a  cmp     r14w, [rsi]
0x180008f9e  jnz     short loc_180008FAF
0x180008fa0  mov     rcx, rsi; lpsz
0x180008fa3  call    cs:__imp_CharNextW
0x180008fa9  mov     rsi, rax
0x180008fac  mov     [rdi], rax
0x180008faf  mov     rcx, rsi; lpsz
0x180008fb2  call    cs:__imp_CharNextW
0x180008fb8  mov     rdx, rax
0x180008fbb  mov     [rdi], rax
0x180008fbe  sub     rdx, rsi
0x180008fc1  sar     rdx, 1
0x180008fc4  lea     rcx, [rdx+1]
0x180008fc8  lea     rcx, [rbx+rcx*2]
0x180008fcc  cmp     rcx, rbp
0x180008fcf  jnb     short loc_180008FF8
0x180008fd1  xor     ecx, ecx
0x180008fd3  test    edx, edx
0x180008fd5  jle     short loc_180008FEB
0x180008fd7  movzx   eax, word ptr [rsi]
0x180008fda  inc     ecx
0x180008fdc  mov     [rbx], ax
0x180008fdf  lea     rsi, [rsi+2]
0x180008fe3  add     rbx, 2
0x180008fe7  cmp     ecx, edx
0x180008fe9  jl      short loc_180008FD7
0x180008feb  mov     rcx, [rdi]
0x180008fee  xor     eax, eax
0x180008ff0  movzx   edx, word ptr [rcx]
0x180008ff3  cmp     ax, dx
0x180008ff6  jnz     short loc_180008F85
0x180008ff8  mov     eax, 80020009h
0x180008ffd  add     rsp, 20h
0x180009001  pop     r14
0x180009003  pop     rdi
0x180009004  pop     rsi
0x180009005  pop     rbp
0x180009006  pop     rbx
0x180009007  retn
0x180009008  mov     rcx, [rdi]
0x18000900b  xor     eax, eax
0x18000900d  cmp     ax, [rcx]
0x180009010  jz      short loc_180008FF8
0x180009012  cmp     rbx, rbp
0x180009015  jnb     short loc_180008FF8
0x180009017  mov     [rbx], ax
0x18000901a  mov     rcx, [rdi]; lpsz
0x18000901d  call    cs:__imp_CharNextW
0x180009023  mov     [rdi], rax
0x180009026  jmp     short loc_180009098
0x180009028  movzx   ecx, cx
0x18000902b  sub     ecx, 9
0x18000902e  jz      short loc_18000908A
0x180009030  sub     ecx, 1
0x180009033  jz      short loc_18000908A
0x180009035  sub     ecx, 3
0x180009038  jz      short loc_18000908A
0x18000903a  cmp     ecx, 13h
0x18000903d  jz      short loc_18000908A
0x18000903f  mov     rcx, rsi; lpsz
0x180009042  call    cs:__imp_CharNextW
0x180009048  mov     rdx, rax
0x18000904b  mov     [rdi], rax
0x18000904e  sub     rdx, rsi
0x180009051  sar     rdx, 1
0x180009054  lea     rcx, [rdx+1]
0x180009058  lea     rcx, [rbx+rcx*2]
0x18000905c  cmp     rcx, rbp
0x18000905f  jnb     short loc_180008FF8
0x180009061  xor     ecx, ecx
0x180009063  test    edx, edx
0x180009065  jle     short loc_18000907B
0x180009067  movzx   eax, word ptr [rsi]
0x18000906a  inc     ecx
0x18000906c  mov     [rbx], ax
0x18000906f  lea     rsi, [rsi+2]
0x180009073  add     rbx, 2
0x180009077  cmp     ecx, edx
0x180009079  jl      short loc_180009067
0x18000907b  mov     rsi, [rdi]
0x18000907e  xor     eax, eax
0x180009080  cmp     ax, [rsi]
0x180009083  jz      short loc_18000908A
0x180009085  movzx   ecx, word ptr [rsi]
0x180009088  jmp     short loc_180009028
0x18000908a  cmp     rbx, rbp
0x18000908d  jnb     loc_180008FF8
0x180009093  xor     eax, eax
0x180009095  mov     [rbx], ax
0x180009098  xor     eax, eax
0x18000909a  jmp     loc_180008FFD
```
