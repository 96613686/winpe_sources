# ATL::CRegParser::NextToken(ushort *)

- ea: `0x180019700`
- end: `0x180019887`
- name: `?NextToken@CRegParser@ATL@@IEAAJPEAG@Z`
- size: `391`
- prototype: `__int64 __fastcall(ATL::CRegParser *__hidden this, unsigned __int16 *)`
- caller_count: `4`
- callee_count: `2`
- tags: ``

## callers

- `0x1800185b8`
- `0x180019cec`
- `0x18001a0d8`
- `0x18001a810`

## callees

- `0x180019700`
- `0x18001a8a4`

## import_xrefs

- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x180019739`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x18001975c`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x18001977a`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x18001978f`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x1800197f4`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x180019829`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x180019739`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x18001975c`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x18001977a`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x18001978f`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x1800197f4`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x180019829`

## pseudocode

```c
__int64 __fastcall ATL::CRegParser::NextToken(ATL::CRegParser *this, unsigned __int16 *a2)
{
  const WCHAR *v4; // rcx
  unsigned __int16 *v5; // rbp
  const WCHAR *v6; // rcx
  const WCHAR *v7; // rsi
  LPWSTR v8; // rax
  __int64 v9; // rdx
  int i; // ecx
  unsigned __int16 *v11; // rsi
  LPWSTR v12; // rax
  __int64 v13; // rdx
  int j; // ecx

  ATL::CRegParser::SkipWhiteSpace(this);
  v4 = *(const WCHAR **)this;
  if ( **(_WORD **)this )
  {
    v5 = a2 + 4096;
    if ( *v4 == 39 )
    {
      *(_QWORD *)this = CharNextW(v4);
      while ( 1 )
      {
        v6 = *(const WCHAR **)this;
        if ( !**(_WORD **)this || *v6 == 39 && *CharNextW(v6) != 39 )
          break;
        v7 = *(const WCHAR **)this;
        if ( **(_WORD **)this == 39 )
        {
          v7 = CharNextW(*(LPCWSTR *)this);
          *(_QWORD *)this = v7;
        }
        v8 = CharNextW(v7);
        *(_QWORD *)this = v8;
        v9 = v8 - v7;
        if ( &a2[v9 + 1] >= v5 )
          return 2147614729LL;
        for ( i = 0; i < (int)v9; ++a2 )
        {
          ++i;
          *a2 = *v7++;
        }
      }
      if ( **(_WORD **)this && a2 < v5 )
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
        v11 = *(unsigned __int16 **)this;
        if ( !**(_WORD **)this || *v11 == 9 || *v11 == 10 || *v11 == 13 || *v11 == 32 )
          break;
        v12 = CharNextW(*(LPCWSTR *)this);
        *(_QWORD *)this = v12;
        v13 = v12 - v11;
        if ( &a2[v13 + 1] >= v5 )
          return 2147614729LL;
        for ( j = 0; j < (int)v13; ++a2 )
        {
          ++j;
          *a2 = *v11++;
        }
      }
      if ( a2 < v5 )
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
0x180019700  push    rbx
0x180019702  push    rbp
0x180019703  push    rsi
0x180019704  push    rdi
0x180019705  push    r14
0x180019707  sub     rsp, 20h
0x18001970b  mov     rbx, rdx
0x18001970e  mov     rdi, rcx
0x180019711  call    ?SkipWhiteSpace@CRegParser@ATL@@IEAAXXZ; ATL::CRegParser::SkipWhiteSpace(void)
0x180019716  mov     rcx, [rdi]; lpsz
0x180019719  xor     eax, eax
0x18001971b  cmp     ax, [rcx]
0x18001971e  jz      loc_180019876
0x180019724  lea     r14d, [rax+27h]
0x180019728  lea     rbp, [rbx+2000h]
0x18001972f  cmp     r14w, [rcx]
0x180019733  jnz     loc_180019805
0x180019739  call    cs:__imp_CharNextW
0x180019740  nop     dword ptr [rax+rax+00h]
0x180019745  mov     [rdi], rax
0x180019748  mov     rcx, [rdi]; lpsz
0x18001974b  xor     eax, eax
0x18001974d  cmp     ax, [rcx]
0x180019750  jz      loc_1800197D7
0x180019756  cmp     r14w, [rcx]
0x18001975a  jnz     short loc_18001976E
0x18001975c  call    cs:__imp_CharNextW
0x180019763  nop     dword ptr [rax+rax+00h]
0x180019768  cmp     r14w, [rax]
0x18001976c  jnz     short loc_1800197D7
0x18001976e  mov     rsi, [rdi]
0x180019771  cmp     r14w, [rsi]
0x180019775  jnz     short loc_18001978C
0x180019777  mov     rcx, rsi; lpsz
0x18001977a  call    cs:__imp_CharNextW
0x180019781  nop     dword ptr [rax+rax+00h]
0x180019786  mov     rsi, rax
0x180019789  mov     [rdi], rax
0x18001978c  mov     rcx, rsi; lpsz
0x18001978f  call    cs:__imp_CharNextW
0x180019796  nop     dword ptr [rax+rax+00h]
0x18001979b  mov     rdx, rax
0x18001979e  mov     [rdi], rax
0x1800197a1  sub     rdx, rsi
0x1800197a4  sar     rdx, 1
0x1800197a7  lea     rcx, [rdx+1]
0x1800197ab  lea     rcx, [rbx+rcx*2]
0x1800197af  cmp     rcx, rbp
0x1800197b2  jnb     loc_180019876
0x1800197b8  xor     ecx, ecx
0x1800197ba  test    edx, edx
0x1800197bc  jle     short loc_180019748
0x1800197be  movzx   eax, word ptr [rsi]
0x1800197c1  inc     ecx
0x1800197c3  mov     [rbx], ax
0x1800197c6  lea     rsi, [rsi+2]
0x1800197ca  add     rbx, 2
0x1800197ce  cmp     ecx, edx
0x1800197d0  jl      short loc_1800197BE
0x1800197d2  jmp     loc_180019748
0x1800197d7  mov     rcx, [rdi]
0x1800197da  xor     eax, eax
0x1800197dc  cmp     ax, [rcx]
0x1800197df  jz      loc_180019876
0x1800197e5  cmp     rbx, rbp
0x1800197e8  jnb     loc_180019876
0x1800197ee  mov     [rbx], ax
0x1800197f1  mov     rcx, [rdi]; lpsz
0x1800197f4  call    cs:__imp_CharNextW
0x1800197fb  nop     dword ptr [rax+rax+00h]
0x180019800  mov     [rdi], rax
0x180019803  jmp     short loc_180019872
0x180019805  mov     rsi, [rdi]
0x180019808  xor     eax, eax
0x18001980a  cmp     ax, [rsi]
0x18001980d  jz      short loc_18001986A
0x18001980f  movzx   ecx, word ptr [rsi]
0x180019812  sub     ecx, 9
0x180019815  jz      short loc_18001986A
0x180019817  sub     ecx, 1
0x18001981a  jz      short loc_18001986A
0x18001981c  sub     ecx, 3
0x18001981f  jz      short loc_18001986A
0x180019821  cmp     ecx, 13h
0x180019824  jz      short loc_18001986A
0x180019826  mov     rcx, rsi; lpsz
0x180019829  call    cs:__imp_CharNextW
0x180019830  nop     dword ptr [rax+rax+00h]
0x180019835  mov     rdx, rax
0x180019838  mov     [rdi], rax
0x18001983b  sub     rdx, rsi
0x18001983e  sar     rdx, 1
0x180019841  lea     rcx, [rdx+1]
0x180019845  lea     rcx, [rbx+rcx*2]
0x180019849  cmp     rcx, rbp
0x18001984c  jnb     short loc_180019876
0x18001984e  xor     ecx, ecx
0x180019850  test    edx, edx
0x180019852  jle     short loc_180019805
0x180019854  movzx   eax, word ptr [rsi]
0x180019857  inc     ecx
0x180019859  mov     [rbx], ax
0x18001985c  lea     rsi, [rsi+2]
0x180019860  add     rbx, 2
0x180019864  cmp     ecx, edx
0x180019866  jl      short loc_180019854
0x180019868  jmp     short loc_180019805
0x18001986a  cmp     rbx, rbp
0x18001986d  jnb     short loc_180019876
0x18001986f  mov     [rbx], ax
0x180019872  xor     eax, eax
0x180019874  jmp     short loc_18001987B
0x180019876  mov     eax, 80020009h
0x18001987b  add     rsp, 20h
0x18001987f  pop     r14
0x180019881  pop     rdi
0x180019882  pop     rsi
0x180019883  pop     rbp
0x180019884  pop     rbx
0x180019885  retn
```
