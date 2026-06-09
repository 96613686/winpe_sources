# ATL::CRegParser::NextToken(ushort *)

- ea: `0x180004a10`
- end: `0x180004bb3`
- name: `?NextToken@CRegParser@ATL@@IEAAJPEAG@Z`
- size: `419`
- prototype: `__int64 __fastcall(LPCWSTR *this, unsigned __int16 *)`
- caller_count: `4`
- callee_count: `1`
- tags: ``

## callers

- `0x18000421c`
- `0x18000483c`
- `0x180004bb4`
- `0x180005394`

## callees

- `0x180004a10`

## import_xrefs

- `USER32!CharNextW` at `0x180004a4d`
- `USER32!CharNextW` at `0x180004a79`
- `USER32!CharNextW` at `0x180004a98`
- `USER32!CharNextW` at `0x180004ab4`
- `USER32!CharNextW` at `0x180004ac3`
- `USER32!CharNextW` at `0x180004b3a`
- `USER32!CharNextW` at `0x180004b5f`
- `USER32!CharNextW` at `0x180004a4d`
- `USER32!CharNextW` at `0x180004a79`
- `USER32!CharNextW` at `0x180004a98`
- `USER32!CharNextW` at `0x180004ab4`
- `USER32!CharNextW` at `0x180004ac3`
- `USER32!CharNextW` at `0x180004b3a`
- `USER32!CharNextW` at `0x180004b5f`

## pseudocode

```c
__int64 __fastcall ATL::CRegParser::NextToken(LPCWSTR *this, unsigned __int16 *a2)
{
  const WCHAR *v4; // rsi
  WCHAR v5; // cx
  unsigned __int16 *v6; // rbp
  LPWSTR v7; // rax
  WCHAR v8; // cx
  const WCHAR *v9; // rsi
  LPWSTR v10; // rax
  __int64 v11; // rax
  signed __int64 v12; // rsi
  __int64 v13; // rcx
  int v15; // ecx
  int v16; // ecx
  int v17; // ecx
  LPWSTR v18; // rax
  __int64 v19; // rax
  signed __int64 v20; // rsi
  __int64 v21; // rcx

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
  v6 = a2;
  if ( v5 != 39 )
  {
    do
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
      if ( &a2[v19 + 1] >= v6 + 4096 )
        return 2147614729LL;
      if ( (int)v19 > 0 )
      {
        v20 = (char *)v4 - (char *)a2;
        v21 = (unsigned int)v19;
        do
        {
          *a2 = *(unsigned __int16 *)((char *)a2 + v20);
          ++a2;
          --v21;
        }
        while ( v21 );
      }
      v4 = *this;
      v5 = **this;
    }
    while ( v5 );
    *a2 = 0;
    return 0;
  }
  v7 = CharNextW(*this);
  *this = v7;
  v8 = *v7;
  if ( *v7 )
  {
    while ( v8 != 39 || *CharNextW(v7) == 39 )
    {
      v9 = *this;
      if ( **this == 39 )
      {
        v9 = CharNextW(*this);
        *this = v9;
      }
      v10 = CharNextW(v9);
      *this = v10;
      v11 = v10 - v9;
      if ( &a2[v11 + 1] < v6 + 4096 )
      {
        if ( (int)v11 > 0 )
        {
          v12 = (char *)v9 - (char *)a2;
          v13 = (unsigned int)v11;
          do
          {
            *a2 = *(unsigned __int16 *)((char *)a2 + v12);
            ++a2;
            --v13;
          }
          while ( v13 );
        }
        v7 = (LPWSTR)*this;
        v8 = **this;
        if ( v8 )
          continue;
      }
      return 2147614729LL;
    }
  }
  if ( !**this )
    return 2147614729LL;
  *a2 = 0;
  *this = CharNextW(*this);
  return 0;
}

```

## disassembly

```asm
0x180004a10  mov     [rsp+arg_0], rbx
0x180004a15  mov     [rsp+arg_8], rbp
0x180004a1a  mov     [rsp+arg_10], rsi
0x180004a1f  push    rdi
0x180004a20  push    r14
0x180004a22  push    r15
0x180004a24  sub     rsp, 20h
0x180004a28  mov     rbx, rdx
0x180004a2b  mov     rdi, rcx
0x180004a2e  mov     rsi, [rdi]
0x180004a31  movzx   ecx, word ptr [rsi]
0x180004a34  mov     edx, ecx
0x180004a36  sub     edx, 9
0x180004a39  jz      short loc_180004A4A
0x180004a3b  sub     edx, 1
0x180004a3e  jz      short loc_180004A4A
0x180004a40  sub     edx, 3
0x180004a43  jz      short loc_180004A4A
0x180004a45  cmp     edx, 13h
0x180004a48  jnz     short loc_180004A58
0x180004a4a  mov     rcx, rsi; lpsz
0x180004a4d  call    cs:__imp_CharNextW
0x180004a53  mov     [rdi], rax
0x180004a56  jmp     short loc_180004A2E
0x180004a58  xor     r14d, r14d
0x180004a5b  cmp     r14w, cx
0x180004a5f  jz      loc_180004B0C
0x180004a65  lea     r15d, [r14+27h]
0x180004a69  mov     rbp, rbx
0x180004a6c  cmp     r15w, cx
0x180004a70  jnz     loc_180004B45
0x180004a76  mov     rcx, rsi; lpsz
0x180004a79  call    cs:__imp_CharNextW
0x180004a7f  mov     [rdi], rax
0x180004a82  movzx   ecx, word ptr [rax]
0x180004a85  cmp     r14w, cx
0x180004a89  jz      loc_180004B2A
0x180004a8f  cmp     r15w, cx
0x180004a93  jnz     short loc_180004AA8
0x180004a95  mov     rcx, rax; lpsz
0x180004a98  call    cs:__imp_CharNextW
0x180004a9e  cmp     r15w, [rax]
0x180004aa2  jnz     loc_180004B2A
0x180004aa8  mov     rsi, [rdi]
0x180004aab  cmp     r15w, [rsi]
0x180004aaf  jnz     short loc_180004AC0
0x180004ab1  mov     rcx, rsi; lpsz
0x180004ab4  call    cs:__imp_CharNextW
0x180004aba  mov     rsi, rax
0x180004abd  mov     [rdi], rax
0x180004ac0  mov     rcx, rsi; lpsz
0x180004ac3  call    cs:__imp_CharNextW
0x180004ac9  mov     [rdi], rax
0x180004acc  lea     rcx, [rbp+2000h]
0x180004ad3  sub     rax, rsi
0x180004ad6  sar     rax, 1
0x180004ad9  lea     rdx, [rax+1]
0x180004add  lea     rdx, [rbx+rdx*2]
0x180004ae1  cmp     rdx, rcx
0x180004ae4  jnb     short loc_180004B0C
0x180004ae6  test    eax, eax
0x180004ae8  jle     short loc_180004B00
0x180004aea  sub     rsi, rbx
0x180004aed  mov     ecx, eax
0x180004aef  movzx   eax, word ptr [rsi+rbx]
0x180004af3  mov     [rbx], ax
0x180004af6  add     rbx, 2
0x180004afa  sub     rcx, 1
0x180004afe  jnz     short loc_180004AEF
0x180004b00  mov     rax, [rdi]
0x180004b03  movzx   ecx, word ptr [rax]
0x180004b06  cmp     r14w, cx
0x180004b0a  jnz     short loc_180004A8F
0x180004b0c  mov     eax, 80020009h
0x180004b11  mov     rbx, [rsp+38h+arg_0]
0x180004b16  mov     rbp, [rsp+38h+arg_8]
0x180004b1b  mov     rsi, [rsp+38h+arg_10]
0x180004b20  add     rsp, 20h
0x180004b24  pop     r15
0x180004b26  pop     r14
0x180004b28  pop     rdi
0x180004b29  retn
0x180004b2a  mov     rax, [rdi]
0x180004b2d  cmp     r14w, [rax]
0x180004b31  jz      short loc_180004B0C
0x180004b33  mov     [rbx], r14w
0x180004b37  mov     rcx, [rdi]; lpsz
0x180004b3a  call    cs:__imp_CharNextW
0x180004b40  mov     [rdi], rax
0x180004b43  jmp     short loc_180004BAC
0x180004b45  movzx   ecx, cx
0x180004b48  sub     ecx, 9
0x180004b4b  jz      short loc_180004BA8
0x180004b4d  sub     ecx, 1
0x180004b50  jz      short loc_180004BA8
0x180004b52  sub     ecx, 3
0x180004b55  jz      short loc_180004BA8
0x180004b57  cmp     ecx, 13h
0x180004b5a  jz      short loc_180004BA8
0x180004b5c  mov     rcx, rsi; lpsz
0x180004b5f  call    cs:__imp_CharNextW
0x180004b65  mov     [rdi], rax
0x180004b68  lea     rcx, [rbp+2000h]
0x180004b6f  sub     rax, rsi
0x180004b72  sar     rax, 1
0x180004b75  lea     rdx, [rax+1]
0x180004b79  lea     rdx, [rbx+rdx*2]
0x180004b7d  cmp     rdx, rcx
0x180004b80  jnb     short loc_180004B0C
0x180004b82  test    eax, eax
0x180004b84  jle     short loc_180004B9C
0x180004b86  sub     rsi, rbx
0x180004b89  mov     ecx, eax
0x180004b8b  movzx   eax, word ptr [rsi+rbx]
0x180004b8f  mov     [rbx], ax
0x180004b92  add     rbx, 2
0x180004b96  sub     rcx, 1
0x180004b9a  jnz     short loc_180004B8B
0x180004b9c  mov     rsi, [rdi]
0x180004b9f  movzx   ecx, word ptr [rsi]
0x180004ba2  cmp     r14w, cx
0x180004ba6  jnz     short loc_180004B45
0x180004ba8  mov     [rbx], r14w
0x180004bac  xor     eax, eax
0x180004bae  jmp     loc_180004B11
```
