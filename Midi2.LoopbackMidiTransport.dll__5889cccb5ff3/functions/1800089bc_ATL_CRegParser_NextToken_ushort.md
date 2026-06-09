# ATL::CRegParser::NextToken(ushort *)

- ea: `0x1800089bc`
- end: `0x180008b53`
- name: `?NextToken@CRegParser@ATL@@IEAAJPEAG@Z`
- size: `407`
- prototype: `__int64 __fastcall(ATL::CRegParser *__hidden this, unsigned __int16 *)`
- caller_count: `4`
- callee_count: `1`
- tags: ``

## callers

- `0x180006970`
- `0x18000917c`
- `0x1800094ec`
- `0x18000a900`

## callees

- `0x1800089bc`

## import_xrefs

- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x1800089f1`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x180008a1f`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x180008a3f`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x180008a57`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x180008a66`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x180008ad1`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x180008af6`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x1800089f1`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x180008a1f`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x180008a3f`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x180008a57`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x180008a66`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x180008ad1`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x180008af6`

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
0x1800089bc  push    rbx
0x1800089be  push    rbp
0x1800089bf  push    rsi
0x1800089c0  push    rdi
0x1800089c1  push    r14
0x1800089c3  sub     rsp, 20h
0x1800089c7  mov     rbx, rdx
0x1800089ca  mov     rdi, rcx
0x1800089cd  mov     rsi, [rdi]
0x1800089d0  movzx   ecx, word ptr [rsi]
0x1800089d3  mov     r8d, ecx
0x1800089d6  sub     r8d, 9
0x1800089da  jz      short loc_1800089EE
0x1800089dc  sub     r8d, 1
0x1800089e0  jz      short loc_1800089EE
0x1800089e2  sub     r8d, 3
0x1800089e6  jz      short loc_1800089EE
0x1800089e8  cmp     r8d, 13h
0x1800089ec  jnz     short loc_1800089FC
0x1800089ee  mov     rcx, rsi; lpsz
0x1800089f1  call    cs:__imp_CharNextW
0x1800089f7  mov     [rdi], rax
0x1800089fa  jmp     short loc_1800089CD
0x1800089fc  xor     eax, eax
0x1800089fe  cmp     ax, cx
0x180008a01  jz      loc_180008AAC
0x180008a07  lea     r14d, [rax+27h]
0x180008a0b  lea     rbp, [rbx+2000h]
0x180008a12  cmp     r14w, cx
0x180008a16  jnz     loc_180008ADC
0x180008a1c  mov     rcx, rsi; lpsz
0x180008a1f  call    cs:__imp_CharNextW
0x180008a25  mov     [rdi], rax
0x180008a28  mov     rcx, rax; lpsz
0x180008a2b  movzx   edx, word ptr [rax]
0x180008a2e  xor     eax, eax
0x180008a30  cmp     ax, dx
0x180008a33  jz      loc_180008ABC
0x180008a39  cmp     r14w, dx
0x180008a3d  jnz     short loc_180008A4B
0x180008a3f  call    cs:__imp_CharNextW
0x180008a45  cmp     r14w, [rax]
0x180008a49  jnz     short loc_180008ABC
0x180008a4b  mov     rsi, [rdi]
0x180008a4e  cmp     r14w, [rsi]
0x180008a52  jnz     short loc_180008A63
0x180008a54  mov     rcx, rsi; lpsz
0x180008a57  call    cs:__imp_CharNextW
0x180008a5d  mov     rsi, rax
0x180008a60  mov     [rdi], rax
0x180008a63  mov     rcx, rsi; lpsz
0x180008a66  call    cs:__imp_CharNextW
0x180008a6c  mov     rdx, rax
0x180008a6f  mov     [rdi], rax
0x180008a72  sub     rdx, rsi
0x180008a75  sar     rdx, 1
0x180008a78  lea     rcx, [rdx+1]
0x180008a7c  lea     rcx, [rbx+rcx*2]
0x180008a80  cmp     rcx, rbp
0x180008a83  jnb     short loc_180008AAC
0x180008a85  xor     ecx, ecx
0x180008a87  test    edx, edx
0x180008a89  jle     short loc_180008A9F
0x180008a8b  movzx   eax, word ptr [rsi]
0x180008a8e  inc     ecx
0x180008a90  mov     [rbx], ax
0x180008a93  lea     rsi, [rsi+2]
0x180008a97  add     rbx, 2
0x180008a9b  cmp     ecx, edx
0x180008a9d  jl      short loc_180008A8B
0x180008a9f  mov     rcx, [rdi]
0x180008aa2  xor     eax, eax
0x180008aa4  movzx   edx, word ptr [rcx]
0x180008aa7  cmp     ax, dx
0x180008aaa  jnz     short loc_180008A39
0x180008aac  mov     eax, 80020009h
0x180008ab1  add     rsp, 20h
0x180008ab5  pop     r14
0x180008ab7  pop     rdi
0x180008ab8  pop     rsi
0x180008ab9  pop     rbp
0x180008aba  pop     rbx
0x180008abb  retn
0x180008abc  mov     rcx, [rdi]
0x180008abf  xor     eax, eax
0x180008ac1  cmp     ax, [rcx]
0x180008ac4  jz      short loc_180008AAC
0x180008ac6  cmp     rbx, rbp
0x180008ac9  jnb     short loc_180008AAC
0x180008acb  mov     [rbx], ax
0x180008ace  mov     rcx, [rdi]; lpsz
0x180008ad1  call    cs:__imp_CharNextW
0x180008ad7  mov     [rdi], rax
0x180008ada  jmp     short loc_180008B4C
0x180008adc  movzx   ecx, cx
0x180008adf  sub     ecx, 9
0x180008ae2  jz      short loc_180008B3E
0x180008ae4  sub     ecx, 1
0x180008ae7  jz      short loc_180008B3E
0x180008ae9  sub     ecx, 3
0x180008aec  jz      short loc_180008B3E
0x180008aee  cmp     ecx, 13h
0x180008af1  jz      short loc_180008B3E
0x180008af3  mov     rcx, rsi; lpsz
0x180008af6  call    cs:__imp_CharNextW
0x180008afc  mov     rdx, rax
0x180008aff  mov     [rdi], rax
0x180008b02  sub     rdx, rsi
0x180008b05  sar     rdx, 1
0x180008b08  lea     rcx, [rdx+1]
0x180008b0c  lea     rcx, [rbx+rcx*2]
0x180008b10  cmp     rcx, rbp
0x180008b13  jnb     short loc_180008AAC
0x180008b15  xor     ecx, ecx
0x180008b17  test    edx, edx
0x180008b19  jle     short loc_180008B2F
0x180008b1b  movzx   eax, word ptr [rsi]
0x180008b1e  inc     ecx
0x180008b20  mov     [rbx], ax
0x180008b23  lea     rsi, [rsi+2]
0x180008b27  add     rbx, 2
0x180008b2b  cmp     ecx, edx
0x180008b2d  jl      short loc_180008B1B
0x180008b2f  mov     rsi, [rdi]
0x180008b32  xor     eax, eax
0x180008b34  cmp     ax, [rsi]
0x180008b37  jz      short loc_180008B3E
0x180008b39  movzx   ecx, word ptr [rsi]
0x180008b3c  jmp     short loc_180008ADC
0x180008b3e  cmp     rbx, rbp
0x180008b41  jnb     loc_180008AAC
0x180008b47  xor     eax, eax
0x180008b49  mov     [rbx], ax
0x180008b4c  xor     eax, eax
0x180008b4e  jmp     loc_180008AB1
```
