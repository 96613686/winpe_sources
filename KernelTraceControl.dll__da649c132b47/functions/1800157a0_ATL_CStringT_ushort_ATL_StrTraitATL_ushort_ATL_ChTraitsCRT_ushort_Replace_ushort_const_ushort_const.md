# ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::Replace(ushort const *,ushort const *)

- ea: `0x1800157a0`
- end: `0x180015a08`
- name: `?Replace@?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAAHPEBG0@Z`
- size: `616`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x1800140dc`

## callees

- `0x18000139c`
- `0x180013048`
- `0x1800157a0`

## import_xrefs

- `msvcrt!memcpy_s` at `0x1800158f5`
- `msvcrt!memcpy_s` at `0x1800158f5`
- `msvcrt!memmove_s` at `0x1800158b3`
- `msvcrt!memmove_s` at `0x1800158b3`
- `msvcrt!wcsstr` at `0x1800157f4`
- `msvcrt!wcsstr` at `0x18001587a`
- `msvcrt!wcsstr` at `0x18001593e`
- `msvcrt!wcsstr` at `0x1800157f4`
- `msvcrt!wcsstr` at `0x18001587a`
- `msvcrt!wcsstr` at `0x18001593e`

## pseudocode

```c
__int64 __fastcall ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::Replace(
        const wchar_t **a1)
{
  const wchar_t *v1; // rbx
  int v3; // r14d
  unsigned __int64 v4; // rbp
  wchar_t *v5; // rax
  __int64 v6; // rax
  __int64 v7; // rbp
  int v8; // edx
  int v9; // ebx
  const wchar_t *v10; // r12
  const wchar_t *v11; // rdi
  unsigned __int64 v12; // r13
  bool i; // cf
  wchar_t *v14; // r15
  int v15; // r13d
  errno_t v16; // eax
  errno_t v17; // eax
  __int64 v18; // rax
  unsigned __int64 v20; // [rsp+60h] [rbp+18h]

  v1 = *a1;
  v3 = 0;
  v4 = (unsigned __int64)&(*a1)[*((int *)*a1 - 4)];
  if ( (unsigned __int64)*a1 < v4 )
  {
    do
    {
      while ( 1 )
      {
        v5 = wcsstr(v1, L"\\Framework64\\");
        if ( !v5 )
          break;
        ++v3;
        v1 = v5 + 13;
      }
      if ( v1 )
      {
        v6 = -1;
        do
          ++v6;
        while ( v1[v6] );
      }
      else
      {
        LODWORD(v6) = 0;
      }
      v1 += (int)v6 + 1;
    }
    while ( (unsigned __int64)v1 < v4 );
    if ( v3 > 0 )
    {
      v7 = *((int *)*a1 - 4);
      v8 = *((_DWORD *)*a1 - 4);
      v9 = v7 - 2 * v3;
      if ( v9 > (int)v7 )
        v8 = v7 - 2 * v3;
      if ( ((*((_DWORD *)*a1 - 3) - v8) | (1 - *((_DWORD *)*a1 - 2))) < 0 )
        ATL::CSimpleStringT<unsigned short,0>::PrepareWrite2(a1);
      v10 = *a1;
      v11 = *a1;
      v12 = (unsigned __int64)&(*a1)[v7];
      v20 = v12;
      for ( i = (unsigned __int64)*a1 < v12; i; i = (unsigned __int64)v11 < v12 )
      {
        v14 = wcsstr(v11, L"\\Framework64\\");
        if ( v14 )
        {
          do
          {
            v11 = v14 + 11;
            v15 = v7 - (v14 - v10) - 13;
            v16 = memmove_s(v14 + 11, 2LL * v15, v14 + 13, 2LL * v15);
            if ( v16 )
            {
              if ( v16 == 12 )
                ATL::AtlThrowImpl(-2147024882);
              if ( v16 == 22 || v16 == 34 )
                ATL::AtlThrowImpl(-2147024809);
              if ( v16 != 80 )
                ATL::AtlThrowImpl(-2147467259);
            }
            v17 = memcpy_s(v14, 0x16u, L"\\Framework\\", 0x16u);
            if ( v17 )
            {
              if ( v17 == 12 )
                ATL::AtlThrowImpl(-2147024882);
              if ( v17 == 22 || v17 == 34 )
                ATL::AtlThrowImpl(-2147024809);
              if ( v17 != 80 )
                ATL::AtlThrowImpl(-2147467259);
            }
            LODWORD(v7) = v7 - 2;
            v14[v15 + 11] = 0;
            v14 = wcsstr(v14 + 11, L"\\Framework64\\");
          }
          while ( v14 );
          v12 = v20;
        }
        if ( v11 )
        {
          v18 = -1;
          do
            ++v18;
          while ( v11[v18] );
        }
        else
        {
          LODWORD(v18) = 0;
        }
        v11 += (int)v18 + 1;
      }
      if ( v9 < 0 || v9 > *((_DWORD *)*a1 - 3) )
        ATL::AtlThrowImpl(-2147024809);
      *((_DWORD *)*a1 - 4) = v9;
      (*a1)[v9] = 0;
    }
  }
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x1800157a0  mov     rax, rsp
0x1800157a3  mov     [rax+8], rbx
0x1800157a7  mov     [rax+10h], rbp
0x1800157ab  mov     [rax+20h], rsi
0x1800157af  mov     [rax+18h], r8
0x1800157b3  push    rdi
0x1800157b4  push    r12
0x1800157b6  push    r13
0x1800157b8  push    r14
0x1800157ba  push    r15
0x1800157bc  sub     rsp, 20h
0x1800157c0  mov     rbx, [rcx]
0x1800157c3  xor     r15d, r15d
0x1800157c6  mov     rsi, rcx
0x1800157c9  mov     r14d, r15d
0x1800157cc  movsxd  rax, dword ptr [rbx-10h]
0x1800157d0  lea     rbp, [rbx+rax*2]
0x1800157d4  cmp     rbx, rbp
0x1800157d7  jnb     loc_18001599B
0x1800157dd  lea     edi, [r15+1]
0x1800157e1  jmp     short loc_1800157EA
0x1800157e3  add     r14d, edi
0x1800157e6  lea     rbx, [rax+1Ah]
0x1800157ea  lea     rdx, aFramework64; "\\Framework64\\"
0x1800157f1  mov     rcx, rbx; Str
0x1800157f4  call    cs:__imp_wcsstr
0x1800157fa  test    rax, rax
0x1800157fd  jnz     short loc_1800157E3
0x1800157ff  test    rbx, rbx
0x180015802  jz      short loc_180015814
0x180015804  or      rax, 0FFFFFFFFFFFFFFFFh
0x180015808  inc     rax
0x18001580b  cmp     [rbx+rax*2], r15w
0x180015810  jnz     short loc_180015808
0x180015812  jmp     short loc_180015817
0x180015814  mov     eax, r15d
0x180015817  inc     eax
0x180015819  movsxd  rcx, eax
0x18001581c  lea     rbx, [rbx+rcx*2]
0x180015820  cmp     rbx, rbp
0x180015823  jb      short loc_1800157EA
0x180015825  test    r14d, r14d
0x180015828  jle     loc_18001599B
0x18001582e  mov     rcx, [rsi]
0x180015831  lea     eax, [r14+r14]
0x180015835  movsxd  rbp, dword ptr [rcx-10h]
0x180015839  mov     ebx, ebp
0x18001583b  mov     edx, ebp
0x18001583d  sub     ebx, eax
0x18001583f  mov     eax, [rcx-0Ch]
0x180015842  cmp     ebx, ebp
0x180015844  cmovg   edx, ebx
0x180015847  sub     edi, [rcx-8]
0x18001584a  sub     eax, edx
0x18001584c  or      edi, eax
0x18001584e  jge     short loc_180015858
0x180015850  mov     rcx, rsi
0x180015853  call    ?PrepareWrite2@?$CSimpleStringT@G$0A@@ATL@@AEAAXH@Z; ATL::CSimpleStringT<ushort,0>::PrepareWrite2(int)
0x180015858  mov     r12, [rsi]
0x18001585b  mov     rdi, r12
0x18001585e  lea     r13, [r12+rbp*2]
0x180015862  mov     [rsp+48h+arg_10], r13
0x180015867  cmp     r12, r13
0x18001586a  jnb     loc_180015981
0x180015870  lea     rdx, aFramework64; "\\Framework64\\"
0x180015877  mov     rcx, rdi; Str
0x18001587a  call    cs:__imp_wcsstr
0x180015880  mov     r15, rax
0x180015883  test    rax, rax
0x180015886  jz      loc_180015955
0x18001588c  mov     rax, r15
0x18001588f  lea     rdi, [r15+16h]
0x180015893  sub     rax, r12
0x180015896  lea     r8, [r15+1Ah]; Source
0x18001589a  sar     rax, 1
0x18001589d  mov     r13d, ebp
0x1800158a0  sub     r13d, eax
0x1800158a3  mov     rcx, rdi; Destination
0x1800158a6  sub     r13d, 0Dh
0x1800158aa  movsxd  rdx, r13d
0x1800158ad  add     rdx, rdx; DestinationSize
0x1800158b0  mov     r9, rdx; SourceSize
0x1800158b3  call    cs:__imp_memmove_s
0x1800158b9  test    eax, eax
0x1800158bb  jz      short loc_1800158E1
0x1800158bd  cmp     eax, 0Ch
0x1800158c0  jz      loc_1800159D1
0x1800158c6  cmp     eax, 16h
0x1800158c9  jz      loc_1800159C6
0x1800158cf  cmp     eax, 22h ; '"'
0x1800158d2  jz      loc_1800159C6
0x1800158d8  cmp     eax, 50h ; 'P'
0x1800158db  jnz     loc_1800159BB
0x1800158e1  mov     eax, 16h
0x1800158e6  lea     r8, aFramework; "\\Framework\\"
0x1800158ed  mov     r9d, eax; SourceSize
0x1800158f0  mov     edx, eax; DestinationSize
0x1800158f2  mov     rcx, r15; Destination
0x1800158f5  call    cs:__imp_memcpy_s
0x1800158fb  xor     edx, edx
0x1800158fd  test    eax, eax
0x1800158ff  jz      short loc_180015925
0x180015901  cmp     eax, 0Ch
0x180015904  jz      loc_1800159F2
0x18001590a  cmp     eax, 16h
0x18001590d  jz      loc_1800159E7
0x180015913  cmp     eax, 22h ; '"'
0x180015916  jz      loc_1800159E7
0x18001591c  cmp     eax, 50h ; 'P'
0x18001591f  jnz     loc_1800159DC
0x180015925  lea     eax, [r13+0Bh]
0x180015929  sub     ebp, 2
0x18001592c  movsxd  rcx, eax
0x18001592f  mov     [r15+rcx*2], dx
0x180015934  lea     rdx, aFramework64; "\\Framework64\\"
0x18001593b  mov     rcx, rdi; Str
0x18001593e  call    cs:__imp_wcsstr
0x180015944  mov     r15, rax
0x180015947  test    rax, rax
0x18001594a  jnz     loc_18001588C
0x180015950  mov     r13, [rsp+48h+arg_10]
0x180015955  xor     r15d, r15d
0x180015958  test    rdi, rdi
0x18001595b  jz      short loc_18001596D
0x18001595d  or      rax, 0FFFFFFFFFFFFFFFFh
0x180015961  inc     rax
0x180015964  cmp     [rdi+rax*2], r15w
0x180015969  jnz     short loc_180015961
0x18001596b  jmp     short loc_180015970
0x18001596d  mov     eax, r15d
0x180015970  inc     eax
0x180015972  movsxd  rcx, eax
0x180015975  lea     rdi, [rdi+rcx*2]
0x180015979  cmp     rdi, r13
0x18001597c  jmp     loc_18001586A
0x180015981  test    ebx, ebx
0x180015983  js      short loc_1800159FD
0x180015985  mov     rax, [rsi]
0x180015988  cmp     ebx, [rax-0Ch]
0x18001598b  jg      short loc_1800159FD
0x18001598d  mov     [rax-10h], ebx
0x180015990  mov     rax, [rsi]
0x180015993  movsxd  rcx, ebx
0x180015996  mov     [rax+rcx*2], r15w
0x18001599b  mov     rbx, [rsp+48h+arg_0]
0x1800159a0  mov     eax, r14d
0x1800159a3  mov     rbp, [rsp+48h+arg_8]
0x1800159a8  mov     rsi, [rsp+48h+arg_18]
0x1800159ad  add     rsp, 20h
0x1800159b1  pop     r15
0x1800159b3  pop     r14
0x1800159b5  pop     r13
0x1800159b7  pop     r12
0x1800159b9  pop     rdi
0x1800159ba  retn
0x1800159bb  mov     ecx, 80004005h; int
0x1800159c0  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x1800159c6  mov     ecx, 80070057h; int
0x1800159cb  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x1800159d1  mov     ecx, 8007000Eh; int
0x1800159d6  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x1800159dc  mov     ecx, 80004005h; int
0x1800159e1  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x1800159e7  mov     ecx, 80070057h; int
0x1800159ec  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x1800159f2  mov     ecx, 8007000Eh; int
0x1800159f7  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x1800159fd  mov     ecx, 80070057h; int
0x180015a02  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
```
