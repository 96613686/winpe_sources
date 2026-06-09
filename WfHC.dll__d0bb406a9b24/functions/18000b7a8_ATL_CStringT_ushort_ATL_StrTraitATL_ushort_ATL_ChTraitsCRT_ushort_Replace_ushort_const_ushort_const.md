# ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::Replace(ushort const *,ushort const *)

- ea: `0x18000b7a8`
- end: `0x18000b9a1`
- name: `?Replace@?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAAHPEBG0@Z`
- size: `505`
- prototype: `__int64 __fastcall(__int64 *)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x18000b3e4`

## callees

- `0x180006a80`
- `0x18000b6ec`
- `0x18000b7a8`

## import_xrefs

- `msvcrt!memcpy_s` at `0x18000b905`
- `msvcrt!memcpy_s` at `0x18000b905`
- `msvcrt!wcsstr` at `0x18000b7f1`
- `msvcrt!wcsstr` at `0x18000b940`
- `msvcrt!wcsstr` at `0x18000b7f1`
- `msvcrt!wcsstr` at `0x18000b940`
- `msvcrt!memmove_s` at `0x18000b8c3`
- `msvcrt!memmove_s` at `0x18000b8c3`

## string_xrefs

- `0x18000b8f6`: `__CDATA_XML_CLOSE_SYMBOL__`

## pseudocode

```c
__int64 __fastcall ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::Replace(
        __int64 *a1)
{
  const wchar_t *v1; // rbx
  int v3; // r14d
  unsigned __int64 v4; // rbp
  wchar_t *v5; // rax
  __int64 v6; // rax
  __int64 v7; // rbp
  int v8; // ebx
  int v9; // edx
  __int64 v10; // r12
  const wchar_t *v11; // rdi
  unsigned __int64 v12; // r13
  errno_t v14; // eax
  errno_t v15; // eax
  wchar_t *v16; // rax
  wchar_t *v17; // r15
  __int64 v18; // rax
  int v19; // [rsp+80h] [rbp+18h]

  v1 = (const wchar_t *)*a1;
  v3 = 0;
  v4 = *a1 + 2LL * *(int *)(*a1 - 16);
  if ( *a1 < v4 )
  {
    do
    {
      while ( 1 )
      {
        v5 = wcsstr(v1, L"]]>");
        if ( !v5 )
          break;
        ++v3;
        v1 = v5 + 3;
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
      v7 = *(int *)(*a1 - 16);
      v8 = v7 + 23 * v3;
      v9 = v8;
      if ( v8 <= (int)v7 )
        v9 = *(_DWORD *)(*a1 - 16);
      if ( ((*(_DWORD *)(*a1 - 12) - v9) | (1 - *(_DWORD *)(*a1 - 8))) < 0 )
        ATL::CSimpleStringT<unsigned short,0>::PrepareWrite2(a1, v9);
      v10 = *a1;
      v11 = (const wchar_t *)*a1;
      v12 = *a1 + 2 * v7;
      if ( *a1 < v12 )
      {
        while ( 1 )
        {
          while ( 1 )
          {
            v16 = wcsstr(v11, L"]]>");
            v17 = v16;
            if ( v16 )
              break;
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
            if ( (unsigned __int64)v11 >= v12 )
              goto LABEL_17;
          }
          v11 = v16 + 26;
          v19 = v7 - (((__int64)v16 - v10) >> 1) - 3;
          v14 = memmove_s(v16 + 26, 2LL * v19, v16 + 3, 2LL * v19);
          if ( v14 )
          {
            if ( v14 == 12 )
              goto LABEL_40;
            if ( v14 == 22 || v14 == 34 )
              goto LABEL_41;
            if ( v14 != 80 )
              goto LABEL_42;
          }
          v15 = memcpy_s(v17, 0x34u, L"__CDATA_XML_CLOSE_SYMBOL__", 0x34u);
          if ( v15 )
          {
            if ( v15 == 12 )
LABEL_40:
              ATL::AtlThrowImpl(-2147024882);
            if ( v15 == 22 || v15 == 34 )
              goto LABEL_41;
            if ( v15 != 80 )
LABEL_42:
              ATL::AtlThrowImpl(-2147467259);
          }
          LODWORD(v7) = v7 + 23;
          v17[v19 + 26] = 0;
        }
      }
LABEL_17:
      if ( v8 < 0 || v8 > *(_DWORD *)(*a1 - 12) )
LABEL_41:
        ATL::AtlThrowImpl(-2147024809);
      *(_DWORD *)(*a1 - 16) = v8;
      *(_WORD *)(*a1 + 2LL * v8) = 0;
    }
  }
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x18000b7a8  mov     [rsp+arg_10], r8
0x18000b7ad  push    rbx
0x18000b7ae  push    rbp
0x18000b7af  push    rsi
0x18000b7b0  push    rdi
0x18000b7b1  push    r12
0x18000b7b3  push    r13
0x18000b7b5  push    r14
0x18000b7b7  push    r15
0x18000b7b9  sub     rsp, 28h
0x18000b7bd  mov     rbx, [rcx]
0x18000b7c0  xor     r15d, r15d
0x18000b7c3  mov     rsi, rcx
0x18000b7c6  mov     r14d, r15d
0x18000b7c9  movsxd  rax, dword ptr [rbx-10h]
0x18000b7cd  lea     rbp, [rbx+rax*2]
0x18000b7d1  cmp     rbx, rbp
0x18000b7d4  jnb     loc_18000B884
0x18000b7da  lea     edi, [r15+1]
0x18000b7de  jmp     short loc_18000B7E7
0x18000b7e0  add     r14d, edi
0x18000b7e3  lea     rbx, [rax+6]
0x18000b7e7  lea     rdx, SubStr; "]]>"
0x18000b7ee  mov     rcx, rbx; Str
0x18000b7f1  call    cs:__imp_wcsstr
0x18000b7f7  test    rax, rax
0x18000b7fa  jnz     short loc_18000B7E0
0x18000b7fc  test    rbx, rbx
0x18000b7ff  jz      short loc_18000B811
0x18000b801  or      rax, 0FFFFFFFFFFFFFFFFh
0x18000b805  inc     rax
0x18000b808  cmp     [rbx+rax*2], r15w
0x18000b80d  jnz     short loc_18000B805
0x18000b80f  jmp     short loc_18000B814
0x18000b811  mov     eax, r15d
0x18000b814  inc     eax
0x18000b816  movsxd  rcx, eax
0x18000b819  lea     rbx, [rbx+rcx*2]
0x18000b81d  cmp     rbx, rbp
0x18000b820  jb      short loc_18000B7E7
0x18000b822  test    r14d, r14d
0x18000b825  jle     short loc_18000B884
0x18000b827  mov     rcx, [rsi]
0x18000b82a  imul    ebx, r14d, 17h
0x18000b82e  movsxd  rbp, dword ptr [rcx-10h]
0x18000b832  mov     eax, [rcx-0Ch]
0x18000b835  add     ebx, ebp
0x18000b837  cmp     ebx, ebp
0x18000b839  mov     edx, ebx
0x18000b83b  cmovle  edx, ebp
0x18000b83e  sub     edi, [rcx-8]
0x18000b841  sub     eax, edx
0x18000b843  or      edi, eax
0x18000b845  jge     short loc_18000B84F
0x18000b847  mov     rcx, rsi
0x18000b84a  call    ?PrepareWrite2@?$CSimpleStringT@G$0A@@ATL@@AEAAXH@Z; ATL::CSimpleStringT<ushort,0>::PrepareWrite2(int)
0x18000b84f  mov     r12, [rsi]
0x18000b852  mov     rdi, r12
0x18000b855  lea     r13, [r12+rbp*2]
0x18000b859  cmp     r12, r13
0x18000b85c  jb      loc_18000B936
0x18000b862  test    ebx, ebx
0x18000b864  js      loc_18000B98B
0x18000b86a  mov     rax, [rsi]
0x18000b86d  cmp     ebx, [rax-0Ch]
0x18000b870  jg      loc_18000B98B
0x18000b876  mov     [rax-10h], ebx
0x18000b879  mov     rcx, [rsi]
0x18000b87c  movsxd  rdx, ebx
0x18000b87f  mov     [rcx+rdx*2], r15w
0x18000b884  mov     eax, r14d
0x18000b887  add     rsp, 28h
0x18000b88b  pop     r15
0x18000b88d  pop     r14
0x18000b88f  pop     r13
0x18000b891  pop     r12
0x18000b893  pop     rdi
0x18000b894  pop     rsi
0x18000b895  pop     rbp
0x18000b896  pop     rbx
0x18000b897  retn
0x18000b898  mov     eax, ebp
0x18000b89a  lea     rdi, [r15+34h]
0x18000b89e  mov     rcx, r15
0x18000b8a1  lea     r8, [r15+6]; Source
0x18000b8a5  sub     rcx, r12
0x18000b8a8  sar     rcx, 1
0x18000b8ab  sub     eax, ecx
0x18000b8ad  mov     rcx, rdi; Destination
0x18000b8b0  add     eax, 0FFFFFFFDh
0x18000b8b3  movsxd  rdx, eax
0x18000b8b6  add     rdx, rdx; DestinationSize
0x18000b8b9  mov     dword ptr [rsp+68h+arg_10], eax
0x18000b8c0  mov     r9, rdx; SourceSize
0x18000b8c3  call    cs:__imp_memmove_s
0x18000b8c9  test    eax, eax
0x18000b8cb  jz      short loc_18000B8F1
0x18000b8cd  cmp     eax, 0Ch
0x18000b8d0  jz      loc_18000B980
0x18000b8d6  cmp     eax, 16h
0x18000b8d9  jz      loc_18000B98B
0x18000b8df  cmp     eax, 22h ; '"'
0x18000b8e2  jz      loc_18000B98B
0x18000b8e8  cmp     eax, 50h ; 'P'
0x18000b8eb  jnz     loc_18000B996
0x18000b8f1  mov     eax, 34h ; '4'
0x18000b8f6  lea     r8, aCdataXmlCloseS; "__CDATA_XML_CLOSE_SYMBOL__"
0x18000b8fd  mov     r9d, eax; SourceSize
0x18000b900  mov     edx, eax; DestinationSize
0x18000b902  mov     rcx, r15; Destination
0x18000b905  call    cs:__imp_memcpy_s
0x18000b90b  test    eax, eax
0x18000b90d  jz      short loc_18000B923
0x18000b90f  cmp     eax, 0Ch
0x18000b912  jz      short loc_18000B980
0x18000b914  cmp     eax, 16h
0x18000b917  jz      short loc_18000B98B
0x18000b919  cmp     eax, 22h ; '"'
0x18000b91c  jz      short loc_18000B98B
0x18000b91e  cmp     eax, 50h ; 'P'
0x18000b921  jnz     short loc_18000B996
0x18000b923  movsxd  rcx, dword ptr [rsp+68h+arg_10]
0x18000b92b  xor     eax, eax
0x18000b92d  add     ebp, 17h
0x18000b930  mov     [r15+rcx*2+34h], ax
0x18000b936  lea     rdx, SubStr; "]]>"
0x18000b93d  mov     rcx, rdi; Str
0x18000b940  call    cs:__imp_wcsstr
0x18000b946  mov     r15, rax
0x18000b949  test    rax, rax
0x18000b94c  jnz     loc_18000B898
0x18000b952  xor     r15d, r15d
0x18000b955  test    rdi, rdi
0x18000b958  jz      short loc_18000B96A
0x18000b95a  or      rax, 0FFFFFFFFFFFFFFFFh
0x18000b95e  inc     rax
0x18000b961  cmp     [rdi+rax*2], r15w
0x18000b966  jnz     short loc_18000B95E
0x18000b968  jmp     short loc_18000B96D
0x18000b96a  mov     eax, r15d
0x18000b96d  inc     eax
0x18000b96f  movsxd  rcx, eax
0x18000b972  lea     rdi, [rdi+rcx*2]
0x18000b976  cmp     rdi, r13
0x18000b979  jb      short loc_18000B936
0x18000b97b  jmp     loc_18000B862
0x18000b980  mov     ecx, 8007000Eh; int
0x18000b985  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x18000b98b  mov     ecx, 80070057h; int
0x18000b990  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x18000b996  mov     ecx, 80004005h; int
0x18000b99b  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
```
