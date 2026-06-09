# ATL::CRegParser::NextToken(ushort *)

- ea: `0x180018170`
- end: `0x180018329`
- name: `?NextToken@CRegParser@ATL@@IEAAJPEAG@Z`
- size: `441`
- prototype: `__int64 __fastcall(ATL::CRegParser *__hidden this, unsigned __int16 *)`
- caller_count: `4`
- callee_count: `2`
- tags: ``

## callers

- `0x180014f74`
- `0x180018b90`
- `0x180018fb0`
- `0x180019a74`

## callees

- `0x180018170`
- `0x180019b10`

## import_xrefs

- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x1800181c0`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x1800181e2`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x180018200`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x180018215`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x18001827e`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x1800182b2`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x1800181c0`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x1800181e2`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x180018200`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x180018215`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x18001827e`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x1800182b2`

## pseudocode

```c
__int64 __fastcall ATL::CRegParser::NextToken(ATL::CRegParser *this, unsigned __int16 *a2)
{
  const WCHAR *v4; // rcx
  unsigned __int16 *v5; // r14
  unsigned __int16 *v6; // rbp
  const WCHAR *v7; // rcx
  const WCHAR *v8; // rsi
  LPWSTR v9; // rax
  __int64 v10; // rax
  signed __int64 v11; // rsi
  __int64 v12; // rcx
  char *v13; // rsi
  LPWSTR v14; // rax
  __int64 v15; // rax
  signed __int64 v16; // rsi
  __int64 v17; // rcx

  ATL::CRegParser::SkipWhiteSpace(this);
  v4 = *(const WCHAR **)this;
  if ( **(_WORD **)this )
  {
    v5 = a2;
    v6 = a2 + 4096;
    if ( *v4 == 39 )
    {
      *(_QWORD *)this = CharNextW(v4);
      while ( 1 )
      {
        v7 = *(const WCHAR **)this;
        if ( !**(_WORD **)this || *v7 == 39 && *CharNextW(v7) != 39 )
          break;
        v8 = *(const WCHAR **)this;
        if ( **(_WORD **)this == 39 )
        {
          v8 = CharNextW(*(LPCWSTR *)this);
          *(_QWORD *)this = v8;
        }
        v9 = CharNextW(v8);
        *(_QWORD *)this = v9;
        v10 = v9 - v8;
        if ( &a2[v10 + 1] >= v5 + 4096 )
          return 2147614729LL;
        if ( (int)v10 > 0 )
        {
          v11 = (char *)v8 - (char *)a2;
          v12 = (unsigned int)v10;
          do
          {
            *a2 = *(unsigned __int16 *)((char *)a2 + v11);
            ++a2;
            --v12;
          }
          while ( v12 );
        }
      }
      if ( **(_WORD **)this && a2 < v6 )
      {
        *a2 = 0;
        *(_QWORD *)this = CharNextW(*(LPCWSTR *)this);
        return 0;
      }
    }
    else
    {
      while ( 1 )
      {
        v13 = *(char **)this;
        if ( !**(_WORD **)this
          || *(_WORD *)v13 == 9
          || *(_WORD *)v13 == 10
          || *(_WORD *)v13 == 13
          || *(_WORD *)v13 == 32 )
        {
          break;
        }
        v14 = CharNextW(*(LPCWSTR *)this);
        *(_QWORD *)this = v14;
        v15 = ((char *)v14 - v13) >> 1;
        if ( &a2[v15 + 1] >= v5 + 4096 )
          return 2147614729LL;
        if ( (int)v15 > 0 )
        {
          v16 = v13 - (char *)a2;
          v17 = (unsigned int)v15;
          do
          {
            *a2 = *(unsigned __int16 *)((char *)a2 + v16);
            ++a2;
            --v17;
          }
          while ( v17 );
        }
      }
      if ( a2 < v6 )
      {
        *a2 = 0;
        return 0;
      }
    }
  }
  return 2147614729LL;
}

```

## disassembly

```asm
0x180018170  mov     rax, rsp
0x180018173  mov     [rax+8], rbx
0x180018177  mov     [rax+10h], rbp
0x18001817b  mov     [rax+18h], rsi
0x18001817f  mov     [rax+20h], rdi
0x180018183  push    r12
0x180018185  push    r14
0x180018187  push    r15
0x180018189  sub     rsp, 20h
0x18001818d  mov     rbx, rdx
0x180018190  mov     rdi, rcx
0x180018193  call    ?SkipWhiteSpace@CRegParser@ATL@@IEAAXXZ; ATL::CRegParser::SkipWhiteSpace(void)
0x180018198  mov     rcx, [rdi]; lpsz
0x18001819b  xor     r15d, r15d
0x18001819e  cmp     r15w, [rcx]
0x1800181a2  jz      loc_180018304
0x1800181a8  lea     r12d, [r15+27h]
0x1800181ac  mov     r14, rbx
0x1800181af  lea     rbp, [rbx+2000h]
0x1800181b6  cmp     r12w, [rcx]
0x1800181ba  jnz     loc_18001828F
0x1800181c0  call    cs:__imp_CharNextW
0x1800181c7  nop     dword ptr [rax+rax+00h]
0x1800181cc  mov     [rdi], rax
0x1800181cf  mov     rcx, [rdi]; lpsz
0x1800181d2  cmp     r15w, [rcx]
0x1800181d6  jz      loc_180018261
0x1800181dc  cmp     r12w, [rcx]
0x1800181e0  jnz     short loc_1800181F4
0x1800181e2  call    cs:__imp_CharNextW
0x1800181e9  nop     dword ptr [rax+rax+00h]
0x1800181ee  cmp     r12w, [rax]
0x1800181f2  jnz     short loc_180018261
0x1800181f4  mov     rsi, [rdi]
0x1800181f7  cmp     r12w, [rsi]
0x1800181fb  jnz     short loc_180018212
0x1800181fd  mov     rcx, rsi; lpsz
0x180018200  call    cs:__imp_CharNextW
0x180018207  nop     dword ptr [rax+rax+00h]
0x18001820c  mov     rsi, rax
0x18001820f  mov     [rdi], rax
0x180018212  mov     rcx, rsi; lpsz
0x180018215  call    cs:__imp_CharNextW
0x18001821c  nop     dword ptr [rax+rax+00h]
0x180018221  mov     [rdi], rax
0x180018224  lea     rcx, [r14+2000h]
0x18001822b  sub     rax, rsi
0x18001822e  sar     rax, 1
0x180018231  lea     rdx, [rax+1]
0x180018235  lea     rdx, [rbx+rdx*2]
0x180018239  cmp     rdx, rcx
0x18001823c  jnb     loc_180018304
0x180018242  test    eax, eax
0x180018244  jle     short loc_1800181CF
0x180018246  sub     rsi, rbx
0x180018249  mov     ecx, eax
0x18001824b  movzx   eax, word ptr [rsi+rbx]
0x18001824f  mov     [rbx], ax
0x180018252  add     rbx, 2
0x180018256  sub     rcx, 1
0x18001825a  jnz     short loc_18001824B
0x18001825c  jmp     loc_1800181CF
0x180018261  mov     rax, [rdi]
0x180018264  cmp     r15w, [rax]
0x180018268  jz      loc_180018304
0x18001826e  cmp     rbx, rbp
0x180018271  jnb     loc_180018304
0x180018277  mov     [rbx], r15w
0x18001827b  mov     rcx, [rdi]; lpsz
0x18001827e  call    cs:__imp_CharNextW
0x180018285  nop     dword ptr [rax+rax+00h]
0x18001828a  mov     [rdi], rax
0x18001828d  jmp     short loc_180018300
0x18001828f  mov     rsi, [rdi]
0x180018292  cmp     r15w, [rsi]
0x180018296  jz      short loc_1800182F7
0x180018298  movzx   ecx, word ptr [rsi]
0x18001829b  sub     ecx, 9
0x18001829e  jz      short loc_1800182F7
0x1800182a0  sub     ecx, 1
0x1800182a3  jz      short loc_1800182F7
0x1800182a5  sub     ecx, 3
0x1800182a8  jz      short loc_1800182F7
0x1800182aa  cmp     ecx, 13h
0x1800182ad  jz      short loc_1800182F7
0x1800182af  mov     rcx, rsi; lpsz
0x1800182b2  call    cs:__imp_CharNextW
0x1800182b9  nop     dword ptr [rax+rax+00h]
0x1800182be  mov     [rdi], rax
0x1800182c1  lea     rcx, [r14+2000h]
0x1800182c8  sub     rax, rsi
0x1800182cb  sar     rax, 1
0x1800182ce  lea     rdx, [rax+1]
0x1800182d2  lea     rdx, [rbx+rdx*2]
0x1800182d6  cmp     rdx, rcx
0x1800182d9  jnb     short loc_180018304
0x1800182db  test    eax, eax
0x1800182dd  jle     short loc_18001828F
0x1800182df  sub     rsi, rbx
0x1800182e2  mov     ecx, eax
0x1800182e4  movzx   eax, word ptr [rsi+rbx]
0x1800182e8  mov     [rbx], ax
0x1800182eb  add     rbx, 2
0x1800182ef  sub     rcx, 1
0x1800182f3  jnz     short loc_1800182E4
0x1800182f5  jmp     short loc_18001828F
0x1800182f7  cmp     rbx, rbp
0x1800182fa  jnb     short loc_180018304
0x1800182fc  mov     [rbx], r15w
0x180018300  xor     eax, eax
0x180018302  jmp     short loc_180018309
0x180018304  mov     eax, 80020009h
0x180018309  mov     rbx, [rsp+38h+arg_0]
0x18001830e  mov     rbp, [rsp+38h+arg_8]
0x180018313  mov     rsi, [rsp+38h+arg_10]
0x180018318  mov     rdi, [rsp+38h+arg_18]
0x18001831d  add     rsp, 20h
0x180018321  pop     r15
0x180018323  pop     r14
0x180018325  pop     r12
0x180018327  retn
```
