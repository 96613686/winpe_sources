# ATL::CRegParser::NextToken(ushort *)

- ea: `0x180020980`
- end: `0x180020b17`
- name: `?NextToken@CRegParser@ATL@@IEAAJPEAG@Z`
- size: `407`
- prototype: `__int64 __fastcall(ATL::CRegParser *__hidden this, unsigned __int16 *)`
- caller_count: `4`
- callee_count: `1`
- tags: ``

## callers

- `0x18001f49c`
- `0x180021098`
- `0x18002140c`
- `0x180021de8`

## callees

- `0x180020980`

## import_xrefs

- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x1800209b5`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x1800209e3`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x180020a03`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x180020a1b`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x180020a2a`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x180020a95`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x180020aba`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x1800209b5`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x1800209e3`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x180020a03`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x180020a1b`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x180020a2a`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x180020a95`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x180020aba`

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
0x180020980  push    rbx
0x180020982  push    rbp
0x180020983  push    rsi
0x180020984  push    rdi
0x180020985  push    r14
0x180020987  sub     rsp, 20h
0x18002098b  mov     rbx, rdx
0x18002098e  mov     rdi, rcx
0x180020991  mov     rsi, [rdi]
0x180020994  movzx   ecx, word ptr [rsi]
0x180020997  mov     r8d, ecx
0x18002099a  sub     r8d, 9
0x18002099e  jz      short loc_1800209B2
0x1800209a0  sub     r8d, 1
0x1800209a4  jz      short loc_1800209B2
0x1800209a6  sub     r8d, 3
0x1800209aa  jz      short loc_1800209B2
0x1800209ac  cmp     r8d, 13h
0x1800209b0  jnz     short loc_1800209C0
0x1800209b2  mov     rcx, rsi; lpsz
0x1800209b5  call    cs:__imp_CharNextW
0x1800209bb  mov     [rdi], rax
0x1800209be  jmp     short loc_180020991
0x1800209c0  xor     eax, eax
0x1800209c2  cmp     ax, cx
0x1800209c5  jz      loc_180020A70
0x1800209cb  lea     r14d, [rax+27h]
0x1800209cf  lea     rbp, [rbx+2000h]
0x1800209d6  cmp     r14w, cx
0x1800209da  jnz     loc_180020AA0
0x1800209e0  mov     rcx, rsi; lpsz
0x1800209e3  call    cs:__imp_CharNextW
0x1800209e9  mov     [rdi], rax
0x1800209ec  mov     rcx, rax; lpsz
0x1800209ef  movzx   edx, word ptr [rax]
0x1800209f2  xor     eax, eax
0x1800209f4  cmp     ax, dx
0x1800209f7  jz      loc_180020A80
0x1800209fd  cmp     r14w, dx
0x180020a01  jnz     short loc_180020A0F
0x180020a03  call    cs:__imp_CharNextW
0x180020a09  cmp     r14w, [rax]
0x180020a0d  jnz     short loc_180020A80
0x180020a0f  mov     rsi, [rdi]
0x180020a12  cmp     r14w, [rsi]
0x180020a16  jnz     short loc_180020A27
0x180020a18  mov     rcx, rsi; lpsz
0x180020a1b  call    cs:__imp_CharNextW
0x180020a21  mov     rsi, rax
0x180020a24  mov     [rdi], rax
0x180020a27  mov     rcx, rsi; lpsz
0x180020a2a  call    cs:__imp_CharNextW
0x180020a30  mov     rdx, rax
0x180020a33  mov     [rdi], rax
0x180020a36  sub     rdx, rsi
0x180020a39  sar     rdx, 1
0x180020a3c  lea     rcx, [rdx+1]
0x180020a40  lea     rcx, [rbx+rcx*2]
0x180020a44  cmp     rcx, rbp
0x180020a47  jnb     short loc_180020A70
0x180020a49  xor     ecx, ecx
0x180020a4b  test    edx, edx
0x180020a4d  jle     short loc_180020A63
0x180020a4f  movzx   eax, word ptr [rsi]
0x180020a52  inc     ecx
0x180020a54  mov     [rbx], ax
0x180020a57  lea     rsi, [rsi+2]
0x180020a5b  add     rbx, 2
0x180020a5f  cmp     ecx, edx
0x180020a61  jl      short loc_180020A4F
0x180020a63  mov     rcx, [rdi]
0x180020a66  xor     eax, eax
0x180020a68  movzx   edx, word ptr [rcx]
0x180020a6b  cmp     ax, dx
0x180020a6e  jnz     short loc_1800209FD
0x180020a70  mov     eax, 80020009h
0x180020a75  add     rsp, 20h
0x180020a79  pop     r14
0x180020a7b  pop     rdi
0x180020a7c  pop     rsi
0x180020a7d  pop     rbp
0x180020a7e  pop     rbx
0x180020a7f  retn
0x180020a80  mov     rcx, [rdi]
0x180020a83  xor     eax, eax
0x180020a85  cmp     ax, [rcx]
0x180020a88  jz      short loc_180020A70
0x180020a8a  cmp     rbx, rbp
0x180020a8d  jnb     short loc_180020A70
0x180020a8f  mov     [rbx], ax
0x180020a92  mov     rcx, [rdi]; lpsz
0x180020a95  call    cs:__imp_CharNextW
0x180020a9b  mov     [rdi], rax
0x180020a9e  jmp     short loc_180020B10
0x180020aa0  movzx   ecx, cx
0x180020aa3  sub     ecx, 9
0x180020aa6  jz      short loc_180020B02
0x180020aa8  sub     ecx, 1
0x180020aab  jz      short loc_180020B02
0x180020aad  sub     ecx, 3
0x180020ab0  jz      short loc_180020B02
0x180020ab2  cmp     ecx, 13h
0x180020ab5  jz      short loc_180020B02
0x180020ab7  mov     rcx, rsi; lpsz
0x180020aba  call    cs:__imp_CharNextW
0x180020ac0  mov     rdx, rax
0x180020ac3  mov     [rdi], rax
0x180020ac6  sub     rdx, rsi
0x180020ac9  sar     rdx, 1
0x180020acc  lea     rcx, [rdx+1]
0x180020ad0  lea     rcx, [rbx+rcx*2]
0x180020ad4  cmp     rcx, rbp
0x180020ad7  jnb     short loc_180020A70
0x180020ad9  xor     ecx, ecx
0x180020adb  test    edx, edx
0x180020add  jle     short loc_180020AF3
0x180020adf  movzx   eax, word ptr [rsi]
0x180020ae2  inc     ecx
0x180020ae4  mov     [rbx], ax
0x180020ae7  lea     rsi, [rsi+2]
0x180020aeb  add     rbx, 2
0x180020aef  cmp     ecx, edx
0x180020af1  jl      short loc_180020ADF
0x180020af3  mov     rsi, [rdi]
0x180020af6  xor     eax, eax
0x180020af8  cmp     ax, [rsi]
0x180020afb  jz      short loc_180020B02
0x180020afd  movzx   ecx, word ptr [rsi]
0x180020b00  jmp     short loc_180020AA0
0x180020b02  cmp     rbx, rbp
0x180020b05  jnb     loc_180020A70
0x180020b0b  xor     eax, eax
0x180020b0d  mov     [rbx], ax
0x180020b10  xor     eax, eax
0x180020b12  jmp     loc_180020A75
```
