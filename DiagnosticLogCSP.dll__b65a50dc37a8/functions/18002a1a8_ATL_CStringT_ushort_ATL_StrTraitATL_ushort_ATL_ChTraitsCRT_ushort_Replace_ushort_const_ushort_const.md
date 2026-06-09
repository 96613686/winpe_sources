# ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::Replace(ushort const *,ushort const *)

- ea: `0x18002a1a8`
- end: `0x18002a3f3`
- name: `?Replace@?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAAHPEBG0@Z`
- size: `587`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: ``

## callers

- `0x180028664`

## callees

- `0x1800025b2`
- `0x180002d31`
- `0x180006c7c`
- `0x180011648`
- `0x18001994c`
- `0x18002a1a8`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18002a3c6`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18002a3c6`
- `api-ms-win-crt-private-l1-1-0!wcsstr` at `0x18002a1f8`
- `api-ms-win-crt-private-l1-1-0!wcsstr` at `0x18002a289`
- `api-ms-win-crt-private-l1-1-0!wcsstr` at `0x18002a339`
- `api-ms-win-crt-private-l1-1-0!wcsstr` at `0x18002a1f8`
- `api-ms-win-crt-private-l1-1-0!wcsstr` at `0x18002a289`
- `api-ms-win-crt-private-l1-1-0!wcsstr` at `0x18002a339`

## pseudocode

```c
__int64 __fastcall ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::Replace(
        __int64 *a1)
{
  const wchar_t *v1; // rbx
  int v2; // r15d
  unsigned __int64 v3; // rdi
  wchar_t *v4; // rax
  __int64 v5; // rax
  __int64 v6; // rbp
  int v7; // edi
  int v8; // edx
  __int64 v9; // r12
  const wchar_t *v10; // rbx
  unsigned __int64 v11; // r13
  const void *v12; // rdx
  wchar_t *v13; // rsi
  __int64 v14; // rcx
  int v15; // r13d
  size_t v16; // r8
  errno_t v17; // eax
  __int64 v18; // rax
  unsigned __int64 v21; // [rsp+70h] [rbp+18h]

  v1 = (const wchar_t *)*a1;
  v2 = 0;
  v3 = *a1 + 2LL * *(int *)(*a1 - 16);
  if ( *a1 < v3 )
  {
    do
    {
      while ( 1 )
      {
        v4 = wcsstr(v1, L"\\Framework64\\");
        if ( !v4 )
          break;
        ++v2;
        v1 = v4 + 13;
      }
      if ( v1 )
      {
        v5 = -1;
        do
          ++v5;
        while ( v1[v5] );
      }
      else
      {
        LODWORD(v5) = 0;
      }
      v1 += (int)v5 + 1;
    }
    while ( (unsigned __int64)v1 < v3 );
    if ( v2 > 0 )
    {
      v6 = *(int *)(*a1 - 16);
      v7 = *(_DWORD *)(*a1 - 16) - 2 * v2;
      v8 = v7;
      if ( v7 <= (int)v6 )
        v8 = *(_DWORD *)(*a1 - 16);
      if ( ((*(_DWORD *)(*a1 - 12) - v8) | (1 - *(_DWORD *)(*a1 - 8))) < 0 )
        ATL::CSimpleStringT<unsigned short,0>::PrepareWrite2(a1, v8);
      v9 = *a1;
      v10 = (const wchar_t *)*a1;
      v11 = *a1 + 2 * v6;
      v21 = v11;
      if ( *a1 >= v11 )
        goto LABEL_35;
      while ( 1 )
      {
        v13 = wcsstr(v10, L"\\Framework64\\");
        if ( !v13 )
          goto LABEL_29;
        do
        {
          v10 = v13 + 11;
          v14 = ((__int64)v13 - v9) >> 1;
          v15 = v6 - v14 - 13;
          v16 = 2LL * v15;
          if ( v16 )
          {
            if ( v13 == (wchar_t *)-22LL || (v12 = v13 + 13, v13 == (wchar_t *)-26LL) )
            {
              *(_DWORD *)_o__errno(v14, v12, v16, 0) = 22;
              invalid_parameter_noinfo();
              goto LABEL_41;
            }
            memmove_0(v13 + 11, v12, v16);
          }
          v17 = memcpy_s_0(v13, 0x16u, L"\\Framework\\", 0x16u);
          if ( v17 )
          {
            if ( v17 == 12 )
              ATL::AtlThrowImpl(-2147024882);
            if ( v17 == 22 || v17 == 34 )
              goto LABEL_41;
            if ( v17 != 80 )
              ATL::AtlThrowImpl(-2147467259);
          }
          LODWORD(v6) = v6 - 2;
          v13[v15 + 11] = 0;
          v13 = wcsstr(v13 + 11, L"\\Framework64\\");
        }
        while ( v13 );
        v11 = v21;
LABEL_29:
        if ( v10 )
        {
          v18 = -1;
          do
            ++v18;
          while ( v10[v18] );
        }
        else
        {
          LODWORD(v18) = 0;
        }
        v10 += (int)v18 + 1;
        if ( (unsigned __int64)v10 >= v11 )
        {
LABEL_35:
          if ( v7 >= 0 && v7 <= *(_DWORD *)(*a1 - 12) )
          {
            *(_DWORD *)(*a1 - 16) = v7;
            *(_WORD *)(*a1 + 2LL * v7) = 0;
            return (unsigned int)v2;
          }
LABEL_41:
          ATL::AtlThrowImpl(-2147024809);
        }
      }
    }
  }
  return (unsigned int)v2;
}

```

## disassembly

```asm
0x18002a1a8  mov     [rsp+arg_8], rbx
0x18002a1ad  mov     [rsp+arg_10], r8
0x18002a1b2  mov     [rsp+arg_0], rcx
0x18002a1b7  push    rbp
0x18002a1b8  push    rsi
0x18002a1b9  push    rdi
0x18002a1ba  push    r12
0x18002a1bc  push    r13
0x18002a1be  push    r14
0x18002a1c0  push    r15
0x18002a1c2  sub     rsp, 20h
0x18002a1c6  mov     rbx, [rcx]
0x18002a1c9  xor     edx, edx
0x18002a1cb  mov     r15d, edx
0x18002a1ce  movsxd  rax, dword ptr [rbx-10h]
0x18002a1d2  lea     rdi, [rbx+rax*2]
0x18002a1d6  cmp     rbx, rdi
0x18002a1d9  jnb     loc_18002A3A2
0x18002a1df  lea     esi, [rdx+1]
0x18002a1e2  xor     r14d, r14d
0x18002a1e5  jmp     short loc_18002A1EE
0x18002a1e7  add     r15d, esi
0x18002a1ea  lea     rbx, [rax+1Ah]
0x18002a1ee  lea     rdx, aFramework64; "\\Framework64\\"
0x18002a1f5  mov     rcx, rbx; Str
0x18002a1f8  call    cs:__imp_wcsstr
0x18002a1ff  nop     dword ptr [rax+rax+00h]
0x18002a204  test    rax, rax
0x18002a207  jnz     short loc_18002A1E7
0x18002a209  test    rbx, rbx
0x18002a20c  jz      short loc_18002A21E
0x18002a20e  or      rax, 0FFFFFFFFFFFFFFFFh
0x18002a212  inc     rax
0x18002a215  cmp     [rbx+rax*2], r14w
0x18002a21a  jnz     short loc_18002A212
0x18002a21c  jmp     short loc_18002A221
0x18002a21e  mov     eax, r14d
0x18002a221  inc     eax
0x18002a223  movsxd  rcx, eax
0x18002a226  lea     rbx, [rbx+rcx*2]
0x18002a22a  cmp     rbx, rdi
0x18002a22d  jb      short loc_18002A1EE
0x18002a22f  mov     r14, [rsp+58h+arg_0]
0x18002a234  test    r15d, r15d
0x18002a237  jle     loc_18002A3A2
0x18002a23d  mov     rcx, [r14]
0x18002a240  lea     eax, [r15+r15]
0x18002a244  movsxd  rbp, dword ptr [rcx-10h]
0x18002a248  mov     edi, ebp
0x18002a24a  sub     edi, eax
0x18002a24c  mov     eax, [rcx-0Ch]
0x18002a24f  cmp     edi, ebp
0x18002a251  mov     edx, edi
0x18002a253  cmovle  edx, ebp
0x18002a256  sub     esi, [rcx-8]
0x18002a259  sub     eax, edx
0x18002a25b  or      esi, eax
0x18002a25d  jge     short loc_18002A267
0x18002a25f  mov     rcx, r14
0x18002a262  call    ?PrepareWrite2@?$CSimpleStringT@G$0A@@ATL@@AEAAXH@Z; ATL::CSimpleStringT<ushort,0>::PrepareWrite2(int)
0x18002a267  mov     r12, [r14]
0x18002a26a  mov     rbx, r12
0x18002a26d  lea     r13, [r12+rbp*2]
0x18002a271  mov     [rsp+58h+arg_10], r13
0x18002a276  cmp     r12, r13
0x18002a279  jnb     loc_18002A385
0x18002a27f  lea     rdx, aFramework64; "\\Framework64\\"
0x18002a286  mov     rcx, rbx; Str
0x18002a289  call    cs:__imp_wcsstr
0x18002a290  nop     dword ptr [rax+rax+00h]
0x18002a295  xor     r9d, r9d
0x18002a298  mov     rsi, rax
0x18002a29b  test    rax, rax
0x18002a29e  jz      loc_18002A359
0x18002a2a4  mov     rcx, rsi
0x18002a2a7  lea     rbx, [rsi+16h]
0x18002a2ab  sub     rcx, r12
0x18002a2ae  mov     r13d, ebp
0x18002a2b1  sar     rcx, 1
0x18002a2b4  sub     r13d, ecx
0x18002a2b7  add     r13d, 0FFFFFFF3h
0x18002a2bb  movsxd  r8, r13d
0x18002a2be  add     r8, r8; Size
0x18002a2c1  jz      short loc_18002A2E1
0x18002a2c3  test    rbx, rbx
0x18002a2c6  jz      loc_18002A3C6
0x18002a2cc  lea     rdx, [rsi+1Ah]; Src
0x18002a2d0  test    rdx, rdx
0x18002a2d3  jz      loc_18002A3C6
0x18002a2d9  mov     rcx, rbx; void *
0x18002a2dc  call    memmove_0
0x18002a2e1  mov     eax, 16h
0x18002a2e6  lea     r8, aFramework; "\\Framework\\"
0x18002a2ed  mov     r9d, eax; SourceSize
0x18002a2f0  mov     edx, eax; DestinationSize
0x18002a2f2  mov     rcx, rsi; Destination
0x18002a2f5  call    memcpy_s_0
0x18002a2fa  xor     edx, edx
0x18002a2fc  test    eax, eax
0x18002a2fe  jz      short loc_18002A324
0x18002a300  cmp     eax, 0Ch
0x18002a303  jz      loc_18002A3BB
0x18002a309  cmp     eax, 16h
0x18002a30c  jz      loc_18002A3DD
0x18002a312  cmp     eax, 22h ; '"'
0x18002a315  jz      loc_18002A3DD
0x18002a31b  cmp     eax, 50h ; 'P'
0x18002a31e  jnz     loc_18002A3E8
0x18002a324  movsxd  rcx, r13d
0x18002a327  sub     ebp, 2
0x18002a32a  mov     [rsi+rcx*2+16h], dx
0x18002a32f  lea     rdx, aFramework64; "\\Framework64\\"
0x18002a336  mov     rcx, rbx; Str
0x18002a339  call    cs:__imp_wcsstr
0x18002a340  nop     dword ptr [rax+rax+00h]
0x18002a345  xor     r9d, r9d
0x18002a348  mov     rsi, rax
0x18002a34b  test    rax, rax
0x18002a34e  jnz     loc_18002A2A4
0x18002a354  mov     r13, [rsp+58h+arg_10]
0x18002a359  test    rbx, rbx
0x18002a35c  jz      short loc_18002A36E
0x18002a35e  or      rax, 0FFFFFFFFFFFFFFFFh
0x18002a362  inc     rax
0x18002a365  cmp     [rbx+rax*2], r9w
0x18002a36a  jnz     short loc_18002A362
0x18002a36c  jmp     short loc_18002A371
0x18002a36e  mov     eax, r9d
0x18002a371  inc     eax
0x18002a373  movsxd  rcx, eax
0x18002a376  lea     rbx, [rbx+rcx*2]
0x18002a37a  cmp     rbx, r13
0x18002a37d  jb      loc_18002A27F
0x18002a383  jmp     short loc_18002A388
0x18002a385  xor     r9d, r9d
0x18002a388  test    edi, edi
0x18002a38a  js      short loc_18002A3DD
0x18002a38c  mov     rax, [r14]
0x18002a38f  cmp     edi, [rax-0Ch]
0x18002a392  jg      short loc_18002A3DD
0x18002a394  mov     [rax-10h], edi
0x18002a397  mov     rcx, [r14]
0x18002a39a  movsxd  rdx, edi
0x18002a39d  mov     [rcx+rdx*2], r9w
0x18002a3a2  mov     rbx, [rsp+58h+arg_8]
0x18002a3a7  mov     eax, r15d
0x18002a3aa  add     rsp, 20h
0x18002a3ae  pop     r15
0x18002a3b0  pop     r14
0x18002a3b2  pop     r13
0x18002a3b4  pop     r12
0x18002a3b6  pop     rdi
0x18002a3b7  pop     rsi
0x18002a3b8  pop     rbp
0x18002a3b9  retn
0x18002a3bb  mov     ecx, 8007000Eh; int
0x18002a3c0  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x18002a3c6  call    cs:__imp__o__errno
0x18002a3cd  nop     dword ptr [rax+rax+00h]
0x18002a3d2  mov     dword ptr [rax], 16h
0x18002a3d8  call    _invalid_parameter_noinfo
0x18002a3dd  mov     ecx, 80070057h; int
0x18002a3e2  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x18002a3e8  mov     ecx, 80004005h; int
0x18002a3ed  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
```
