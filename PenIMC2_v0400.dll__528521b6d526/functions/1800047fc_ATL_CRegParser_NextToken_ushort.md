# ATL::CRegParser::NextToken(ushort *)

- ea: `0x1800047fc`
- end: `0x1800049b5`
- name: `?NextToken@CRegParser@ATL@@IEAAJPEAG@Z`
- size: `441`
- prototype: `__int64 __fastcall(ATL::CRegParser *__hidden this, unsigned __int16 *)`
- caller_count: `4`
- callee_count: `1`
- tags: ``

## callers

- `0x180003ea0`
- `0x1800044a8`
- `0x1800049b8`
- `0x180005454`

## callees

- `0x1800047fc`

## import_xrefs

- `USER32!CharNextW` at `0x18000483b`
- `USER32!CharNextW` at `0x180004867`
- `USER32!CharNextW` at `0x180004881`
- `USER32!CharNextW` at `0x180004899`
- `USER32!CharNextW` at `0x1800048a8`
- `USER32!CharNextW` at `0x180004915`
- `USER32!CharNextW` at `0x18000493b`
- `USER32!CharNextW` at `0x18000483b`
- `USER32!CharNextW` at `0x180004867`
- `USER32!CharNextW` at `0x180004881`
- `USER32!CharNextW` at `0x180004899`
- `USER32!CharNextW` at `0x1800048a8`
- `USER32!CharNextW` at `0x180004915`
- `USER32!CharNextW` at `0x18000493b`

## pseudocode

```c
__int64 __fastcall ATL::CRegParser::NextToken(LPCWSTR *this, unsigned __int16 *a2)
{
  const WCHAR *v4; // rsi
  __int16 v5; // r8
  unsigned __int16 *v6; // rbp
  LPWSTR v7; // rdx
  WCHAR i; // ax
  const WCHAR *v9; // rsi
  LPWSTR v10; // rax
  __int64 v11; // r8
  signed __int64 v12; // rsi
  __int64 v13; // rcx
  LPWSTR v14; // rax
  __int64 v15; // r8
  signed __int64 v16; // rsi
  __int64 v17; // rcx

  while ( 1 )
  {
    v4 = *this;
    v5 = **this;
    if ( v5 != 9 && **this != 10 && **this != 13 && **this != 32 )
      break;
    *this = CharNextW(*this);
  }
  if ( v5 )
  {
    v6 = a2;
    if ( v5 != 39 )
    {
      while ( v5 != 9 && v5 != 10 && v5 != 13 && v5 != 32 )
      {
        v14 = CharNextW(v4);
        *this = v14;
        v15 = v14 - v4;
        if ( &a2[v15 + 1] >= v6 + 4096 )
          return 2147614729LL;
        if ( (int)v15 > 0 )
        {
          v16 = (char *)v4 - (char *)a2;
          v17 = (unsigned int)v15;
          do
          {
            *a2 = *(unsigned __int16 *)((char *)a2 + v16);
            ++a2;
            --v17;
          }
          while ( v17 );
          v14 = (LPWSTR)*this;
        }
        v4 = v14;
        if ( !*v14 )
          break;
        v5 = *v14;
      }
      *a2 = 0;
      return 0;
    }
    v7 = CharNextW(*this);
    *this = v7;
    for ( i = *v7; i && (i != 39 || *CharNextW(v7) == 39); i = *v7 )
    {
      v9 = *this;
      if ( **this == 39 )
      {
        v9 = CharNextW(*this);
        *this = v9;
      }
      v10 = CharNextW(v9);
      *this = v10;
      v7 = v10;
      v11 = v10 - v9;
      if ( &a2[v11 + 1] >= v6 + 4096 )
        return 2147614729LL;
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
        v7 = (LPWSTR)*this;
      }
    }
    if ( **this )
    {
      *a2 = 0;
      *this = CharNextW(*this);
      return 0;
    }
  }
  return 2147614729LL;
}

```

## disassembly

```asm
0x1800047fc  mov     [rsp+arg_0], rbx
0x180004801  mov     [rsp+arg_8], rbp
0x180004806  mov     [rsp+arg_10], rsi
0x18000480b  push    rdi
0x18000480c  push    r14
0x18000480e  push    r15
0x180004810  sub     rsp, 20h
0x180004814  mov     rbx, rdx
0x180004817  mov     rdi, rcx
0x18000481a  mov     rsi, [rdi]
0x18000481d  movzx   r8d, word ptr [rsi]
0x180004821  mov     edx, r8d
0x180004824  sub     edx, 9
0x180004827  jz      short loc_180004838
0x180004829  sub     edx, 1
0x18000482c  jz      short loc_180004838
0x18000482e  sub     edx, 3
0x180004831  jz      short loc_180004838
0x180004833  cmp     edx, 13h
0x180004836  jnz     short loc_180004846
0x180004838  mov     rcx, rsi; lpsz
0x18000483b  call    cs:__imp_CharNextW
0x180004841  mov     [rdi], rax
0x180004844  jmp     short loc_18000481A
0x180004846  xor     r14d, r14d
0x180004849  cmp     r14w, r8w
0x18000484d  jz      loc_180004997
0x180004853  lea     r15d, [r14+27h]
0x180004857  mov     rbp, rbx
0x18000485a  cmp     r15w, r8w
0x18000485e  jnz     loc_180004920
0x180004864  mov     rcx, rsi; lpsz
0x180004867  call    cs:__imp_CharNextW
0x18000486d  mov     rdx, rax
0x180004870  mov     [rdi], rax
0x180004873  movzx   eax, word ptr [rax]
0x180004876  jmp     short loc_1800048F7
0x180004878  cmp     r15w, ax
0x18000487c  jnz     short loc_18000488D
0x18000487e  mov     rcx, rdx; lpsz
0x180004881  call    cs:__imp_CharNextW
0x180004887  cmp     r15w, [rax]
0x18000488b  jnz     short loc_180004901
0x18000488d  mov     rsi, [rdi]
0x180004890  cmp     r15w, [rsi]
0x180004894  jnz     short loc_1800048A5
0x180004896  mov     rcx, rsi; lpsz
0x180004899  call    cs:__imp_CharNextW
0x18000489f  mov     rsi, rax
0x1800048a2  mov     [rdi], rax
0x1800048a5  mov     rcx, rsi; lpsz
0x1800048a8  call    cs:__imp_CharNextW
0x1800048ae  mov     r8, rax
0x1800048b1  mov     [rdi], rax
0x1800048b4  sub     r8, rsi
0x1800048b7  mov     rdx, rax
0x1800048ba  sar     r8, 1
0x1800048bd  lea     rax, [rbp+2000h]
0x1800048c4  lea     rcx, [r8+1]
0x1800048c8  lea     rcx, [rbx+rcx*2]
0x1800048cc  cmp     rcx, rax
0x1800048cf  jnb     loc_180004997
0x1800048d5  test    r8d, r8d
0x1800048d8  jle     short loc_1800048F4
0x1800048da  sub     rsi, rbx
0x1800048dd  mov     ecx, r8d
0x1800048e0  movzx   eax, word ptr [rsi+rbx]
0x1800048e4  mov     [rbx], ax
0x1800048e7  add     rbx, 2
0x1800048eb  sub     rcx, 1
0x1800048ef  jnz     short loc_1800048E0
0x1800048f1  mov     rdx, [rdi]
0x1800048f4  movzx   eax, word ptr [rdx]
0x1800048f7  cmp     r14w, ax
0x1800048fb  jnz     loc_180004878
0x180004901  mov     rax, [rdi]
0x180004904  cmp     r14w, [rax]
0x180004908  jz      loc_180004997
0x18000490e  mov     [rbx], r14w
0x180004912  mov     rcx, [rdi]; lpsz
0x180004915  call    cs:__imp_CharNextW
0x18000491b  mov     [rdi], rax
0x18000491e  jmp     short loc_180004993
0x180004920  movzx   ecx, r8w
0x180004924  sub     ecx, 9
0x180004927  jz      short loc_18000498F
0x180004929  sub     ecx, 1
0x18000492c  jz      short loc_18000498F
0x18000492e  sub     ecx, 3
0x180004931  jz      short loc_18000498F
0x180004933  cmp     ecx, 13h
0x180004936  jz      short loc_18000498F
0x180004938  mov     rcx, rsi; lpsz
0x18000493b  call    cs:__imp_CharNextW
0x180004941  mov     r8, rax
0x180004944  mov     [rdi], rax
0x180004947  sub     r8, rsi
0x18000494a  lea     rcx, [rbp+2000h]
0x180004951  sar     r8, 1
0x180004954  lea     rdx, [r8+1]
0x180004958  lea     rdx, [rbx+rdx*2]
0x18000495c  cmp     rdx, rcx
0x18000495f  jnb     short loc_180004997
0x180004961  test    r8d, r8d
0x180004964  jle     short loc_180004980
0x180004966  sub     rsi, rbx
0x180004969  mov     ecx, r8d
0x18000496c  movzx   eax, word ptr [rsi+rbx]
0x180004970  mov     [rbx], ax
0x180004973  add     rbx, 2
0x180004977  sub     rcx, 1
0x18000497b  jnz     short loc_18000496C
0x18000497d  mov     rax, [rdi]
0x180004980  mov     rsi, rax
0x180004983  cmp     r14w, [rax]
0x180004987  jz      short loc_18000498F
0x180004989  movzx   r8d, word ptr [rax]
0x18000498d  jmp     short loc_180004920
0x18000498f  mov     [rbx], r14w
0x180004993  xor     eax, eax
0x180004995  jmp     short loc_18000499C
0x180004997  mov     eax, 80020009h
0x18000499c  mov     rbx, [rsp+38h+arg_0]
0x1800049a1  mov     rbp, [rsp+38h+arg_8]
0x1800049a6  mov     rsi, [rsp+38h+arg_10]
0x1800049ab  add     rsp, 20h
0x1800049af  pop     r15
0x1800049b1  pop     r14
0x1800049b3  pop     rdi
0x1800049b4  retn
```
