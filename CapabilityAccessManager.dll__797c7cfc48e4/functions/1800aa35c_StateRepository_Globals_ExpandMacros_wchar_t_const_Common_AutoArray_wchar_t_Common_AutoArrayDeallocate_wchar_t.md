# StateRepository::Globals::ExpandMacros(wchar_t const *,Common::AutoArray<wchar_t,&Common::AutoArrayDeallocate<wchar_t>(wchar_t *)> &)

- ea: `0x1800aa35c`
- end: `0x1800aa5f3`
- name: `?ExpandMacros@Globals@StateRepository@@YAJPEB_WAEAV?$AutoArray@_W$1??$AutoArrayDeallocate@_W@Common@@YAXPEA_W@Z@Common@@@Z`
- size: `663`
- prototype: ``
- caller_count: `1`
- callee_count: `10`
- tags: `file_ops, broker_com_uri`

## callers

- `0x1800aad24`

## callees

- `0x1800099c8`
- `0x180009a0c`
- `0x18001ab9c`
- `0x180021074`
- `0x1800a213c`
- `0x1800a9060`
- `0x1800a908c`
- `0x1800a9260`
- `0x1800aa35c`
- `0x1800aa760`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!wcschr` at `0x1800aa3b9`
- `api-ms-win-crt-private-l1-1-0!wcschr` at `0x1800aa3b9`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1800aa420`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1800aa420`

## string_xrefs

- `0x1800aa47c`: `onecore\base\appmodel\staterepository\dataaccesslayer\globals.cpp`
- `0x1800aa4a4`: `onecore\base\appmodel\staterepository\dataaccesslayer\globals.cpp`
- `0x1800aa4f9`: `onecore\base\appmodel\staterepository\dataaccesslayer\globals.cpp`
- `0x1800aa568`: `onecore\base\appmodel\staterepository\dataaccesslayer\globals.cpp`
- `0x1800aa5ab`: `onecore\base\appmodel\staterepository\dataaccesslayer\globals.cpp`

## pseudocode

```c
__int64 __fastcall StateRepository::Globals::ExpandMacros(__int64 a1, void **a2)
{
  const wchar_t *v4; // rdi
  char v5; // r13
  unsigned __int64 v6; // rdi
  unsigned __int64 v7; // rsi
  unsigned __int64 v8; // rbx
  wchar_t *v9; // rax
  const WCHAR *v10; // r12
  int v11; // eax
  unsigned int v12; // ebx
  __int64 v13; // rsi
  int AppRepositoryPath; // eax
  void *v15; // rbx
  int v16; // eax
  unsigned int v17; // r12d
  __int64 v18; // rdx
  void *v19; // rcx
  __int64 v20; // rcx
  unsigned __int64 v21; // rsi
  unsigned __int64 v22; // rax
  wchar_t *v23; // rax
  wchar_t *v24; // rbx
  int v26; // eax
  BOOL bIgnoreCase; // [rsp+20h] [rbp-28h]
  _QWORD v28[3]; // [rsp+30h] [rbp-18h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+88h] [rbp+40h]
  void *Block; // [rsp+90h] [rbp+48h] BYREF

  v28[0] = 0;
  v28[1] = 0;
  v4 = 0;
  if ( a1 )
  {
    v5 = 0;
    v6 = -1;
    do
      ++v6;
    while ( *(_WORD *)(a1 + 2 * v6) );
    v7 = 0;
    while ( 1 )
    {
      v8 = a1 + 2 * v7;
      if ( v7 >= v6 )
        break;
      v9 = wcschr((const wchar_t *)(a1 + 2 * v7), 0x25u);
      v10 = v9;
      if ( !v9 )
        break;
      if ( (unsigned __int64)v9 > v8 )
      {
        v11 = StateRepository::Text::Append(
                (StateRepository::Text *)v28,
                (const wchar_t *)(a1 + 2 * v7),
                (__int64)((__int64)v9 - v8) >> 1);
        v12 = v11;
        if ( v11 < 0 )
        {
          v18 = 1420;
LABEL_22:
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)v18,
            (unsigned int)"onecore\\base\\appmodel\\staterepository\\dataaccesslayer\\globals.cpp",
            (const char *)(unsigned int)v11,
            bIgnoreCase);
          goto LABEL_34;
        }
      }
      v13 = ((__int64)v10 - a1) >> 1;
      if ( (unsigned int)(v6 - v13) < 0xF || CompareStringOrdinal(v10, 15, L"%AppRepository%", 15, 1) != 2 )
      {
        v12 = -2140733437;
        goto LABEL_34;
      }
      Block = 0;
      AppRepositoryPath = StateRepository::Globals::GetAppRepositoryPath(&Block);
      v12 = AppRepositoryPath;
      if ( AppRepositoryPath < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x594,
          (unsigned int)"onecore\\base\\appmodel\\staterepository\\dataaccesslayer\\globals.cpp",
          (const char *)(unsigned int)AppRepositoryPath,
          bIgnoreCase);
        v19 = Block;
        goto LABEL_33;
      }
      v15 = Block;
      v16 = StateRepository::Text::Append((StateRepository::Text *)v28, (const wchar_t *)Block);
      v17 = v16;
      if ( v16 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x595,
          (unsigned int)"onecore\\base\\appmodel\\staterepository\\dataaccesslayer\\globals.cpp",
          (const char *)(unsigned int)v16,
          bIgnoreCase);
        operator delete(v15);
        v12 = v17;
        goto LABEL_34;
      }
      v7 = v13 + 15;
      v5 = 1;
      operator delete(v15);
    }
    if ( v5 )
    {
      if ( v7 < v6 )
      {
        v11 = StateRepository::Text::Append((StateRepository::Text *)v28, (const wchar_t *)(a1 + 2 * v7), v6 - v7);
        v12 = v11;
        if ( v11 < 0 )
        {
          v18 = 1443;
          goto LABEL_22;
        }
      }
    }
    v4 = (const wchar_t *)v28[0];
  }
  if ( !v4 )
  {
    if ( *a2 )
    {
      operator delete(*a2);
      *a2 = 0;
    }
LABEL_40:
    StateRepository::TextA::Reset((StateRepository::TextA *)v28);
    return 0;
  }
  v20 = -1;
  do
    ++v20;
  while ( v4[v20] );
  v21 = v20 + 1;
  v22 = 2 * (v20 + 1);
  if ( !is_mul_ok(v20 + 1, 2u) )
    v22 = -1;
  v23 = (wchar_t *)operator new[](v22, (const struct std::nothrow_t *)&std::nothrow);
  v24 = v23;
  if ( v23 )
  {
    v26 = StringCchCopyW(v23, v21, v4);
    if ( v26 < 0 )
      wil::details::in1diag3::_FailFast_Hr(
        retaddr,
        (void *)0x5B1,
        (unsigned int)"onecore\\base\\appmodel\\staterepository\\dataaccesslayer\\globals.cpp",
        (const char *)(unsigned int)v26,
        bIgnoreCase);
    if ( *a2 != v24 )
    {
      operator delete(*a2);
      *a2 = v24;
    }
    operator delete(0);
    goto LABEL_40;
  }
  v12 = -2147024882;
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x5B0,
    (unsigned int)"onecore\\base\\appmodel\\staterepository\\dataaccesslayer\\globals.cpp",
    (const char *)0x8007000ELL,
    bIgnoreCase);
  v19 = 0;
LABEL_33:
  operator delete(v19);
LABEL_34:
  StateRepository::TextA::Reset((StateRepository::TextA *)v28);
  return v12;
}

```

## disassembly

```asm
0x1800aa35c  push    rbp
0x1800aa35e  push    rbx
0x1800aa35f  push    rsi
0x1800aa360  push    rdi
0x1800aa361  push    r12
0x1800aa363  push    r13
0x1800aa365  push    r14
0x1800aa367  push    r15
0x1800aa369  mov     rbp, rsp
0x1800aa36c  sub     rsp, 48h
0x1800aa370  xor     r12d, r12d
0x1800aa373  or      rbx, 0FFFFFFFFFFFFFFFFh
0x1800aa377  mov     [rbp+var_18], r12
0x1800aa37b  mov     r14, rdx
0x1800aa37e  mov     [rbp+var_10], r12
0x1800aa382  mov     r15, rcx
0x1800aa385  mov     edi, r12d
0x1800aa388  test    rcx, rcx
0x1800aa38b  jz      loc_1800AA512
0x1800aa391  mov     r13b, r12b
0x1800aa394  mov     rdi, rbx
0x1800aa397  inc     rdi
0x1800aa39a  cmp     [rcx+rdi*2], r12w
0x1800aa39f  jnz     short loc_1800AA397
0x1800aa3a1  mov     rsi, r12
0x1800aa3a4  lea     rbx, [r15+rsi*2]
0x1800aa3a8  cmp     rsi, rdi
0x1800aa3ab  jnb     loc_1800AA4CB
0x1800aa3b1  mov     edx, 25h ; '%'; Ch
0x1800aa3b6  mov     rcx, rbx; Str
0x1800aa3b9  call    cs:__imp_wcschr
0x1800aa3bf  mov     r12, rax
0x1800aa3c2  test    rax, rax
0x1800aa3c5  jz      loc_1800AA4CB
0x1800aa3cb  cmp     rax, rbx
0x1800aa3ce  jbe     short loc_1800AA3EF
0x1800aa3d0  mov     r8, rax
0x1800aa3d3  lea     rcx, [rbp+var_18]; this
0x1800aa3d7  sub     r8, rbx
0x1800aa3da  mov     rdx, rbx; wchar_t *
0x1800aa3dd  sar     r8, 1; unsigned __int64
0x1800aa3e0  call    ?Append@Text@StateRepository@@QEAAJPEB_W_K@Z; StateRepository::Text::Append(wchar_t const *,unsigned __int64)
0x1800aa3e5  mov     ebx, eax
0x1800aa3e7  test    eax, eax
0x1800aa3e9  js      loc_1800AA471
0x1800aa3ef  mov     rsi, r12
0x1800aa3f2  mov     eax, edi
0x1800aa3f4  sub     rsi, r15
0x1800aa3f7  mov     ecx, 0Fh
0x1800aa3fc  sar     rsi, 1
0x1800aa3ff  sub     eax, esi
0x1800aa401  cmp     eax, ecx
0x1800aa403  jb      loc_1800AA4C1
0x1800aa409  mov     r9d, ecx; cchCount2
0x1800aa40c  mov     [rsp+48h+bIgnoreCase], 1; int
0x1800aa414  mov     edx, ecx; cchCount1
0x1800aa416  lea     r8, ?appRepositoryPrefix@StateRepository@@3QB_WB; "%AppRepository%"
0x1800aa41d  mov     rcx, r12; lpString1
0x1800aa420  call    cs:__imp_CompareStringOrdinal
0x1800aa426  cmp     eax, 2
0x1800aa429  jnz     loc_1800AA4C1
0x1800aa42f  lea     rcx, [rbp+Block]
0x1800aa433  mov     [rbp+Block], 0
0x1800aa43b  call    ?GetAppRepositoryPath@Globals@StateRepository@@YAJAEAV?$AutoArray@_W$1??$AutoArrayDeallocate@_W@Common@@YAXPEA_W@Z@Common@@@Z; StateRepository::Globals::GetAppRepositoryPath(Common::AutoArray<wchar_t,&Common::AutoArrayDeallocate<wchar_t>(wchar_t *)> &)
0x1800aa440  mov     ebx, eax
0x1800aa442  test    eax, eax
0x1800aa444  js      short loc_1800AA4A0
0x1800aa446  mov     rbx, [rbp+Block]
0x1800aa44a  lea     rcx, [rbp+var_18]; this
0x1800aa44e  mov     rdx, rbx; wchar_t *
0x1800aa451  call    ?Append@Text@StateRepository@@QEAAJPEB_W@Z; StateRepository::Text::Append(wchar_t const *)
0x1800aa456  mov     r12d, eax
0x1800aa459  test    eax, eax
0x1800aa45b  js      short loc_1800AA478
0x1800aa45d  add     rsi, 0Fh
0x1800aa461  mov     rcx, rbx; Block
0x1800aa464  mov     r13b, 1
0x1800aa467  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1800aa46c  jmp     loc_1800AA3A4
0x1800aa471  mov     edx, 58Ch
0x1800aa476  jmp     short loc_1800AA4F5
0x1800aa478  mov     rcx, [rbp+40h]; this
0x1800aa47c  lea     r8, aOnecoreBaseApp_24; "onecore\\base\\appmodel\\staterepositor"...
0x1800aa483  mov     r9d, r12d; char *
0x1800aa486  mov     edx, 595h; void *
0x1800aa48b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800aa490  mov     rcx, rbx; Block
0x1800aa493  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1800aa498  mov     ebx, r12d
0x1800aa49b  jmp     loc_1800AA588
0x1800aa4a0  mov     rcx, [rbp+40h]; this
0x1800aa4a4  lea     r8, aOnecoreBaseApp_24; "onecore\\base\\appmodel\\staterepositor"...
0x1800aa4ab  mov     r9d, eax; char *
0x1800aa4ae  mov     edx, 594h; void *
0x1800aa4b3  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800aa4b8  mov     rcx, [rbp+Block]
0x1800aa4bc  jmp     loc_1800AA583
0x1800aa4c1  mov     ebx, 80670003h
0x1800aa4c6  jmp     loc_1800AA588
0x1800aa4cb  xor     r12d, r12d
0x1800aa4ce  test    r13b, r13b
0x1800aa4d1  jz      short loc_1800AA50A
0x1800aa4d3  cmp     rsi, rdi
0x1800aa4d6  jnb     short loc_1800AA50A
0x1800aa4d8  sub     rdi, rsi
0x1800aa4db  lea     rcx, [rbp+var_18]; this
0x1800aa4df  mov     r8, rdi; unsigned __int64
0x1800aa4e2  mov     rdx, rbx; wchar_t *
0x1800aa4e5  call    ?Append@Text@StateRepository@@QEAAJPEB_W_K@Z; StateRepository::Text::Append(wchar_t const *,unsigned __int64)
0x1800aa4ea  mov     ebx, eax
0x1800aa4ec  test    eax, eax
0x1800aa4ee  jns     short loc_1800AA50A
0x1800aa4f0  mov     edx, 5A3h; void *
0x1800aa4f5  mov     rcx, [rbp+40h]; this
0x1800aa4f9  lea     r8, aOnecoreBaseApp_24; "onecore\\base\\appmodel\\staterepositor"...
0x1800aa500  mov     r9d, eax; char *
0x1800aa503  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800aa508  jmp     short loc_1800AA588
0x1800aa50a  mov     rdi, [rbp+var_18]
0x1800aa50e  or      rbx, 0FFFFFFFFFFFFFFFFh
0x1800aa512  test    rdi, rdi
0x1800aa515  jnz     short loc_1800AA530
0x1800aa517  mov     rcx, [r14]; Block
0x1800aa51a  test    rcx, rcx
0x1800aa51d  jz      loc_1800AA5D7
0x1800aa523  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1800aa528  mov     [r14], r12
0x1800aa52b  jmp     loc_1800AA5D7
0x1800aa530  mov     rcx, rbx
0x1800aa533  inc     rcx
0x1800aa536  cmp     [rdi+rcx*2], r12w
0x1800aa53b  jnz     short loc_1800AA533
0x1800aa53d  lea     rsi, [rcx+1]
0x1800aa541  mov     eax, 2
0x1800aa546  mul     rsi
0x1800aa549  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x1800aa550  cmovb   rax, rbx
0x1800aa554  mov     rcx, rax; unsigned __int64
0x1800aa557  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x1800aa55c  mov     rbx, rax
0x1800aa55f  test    rax, rax
0x1800aa562  jnz     short loc_1800AA595
0x1800aa564  mov     rcx, [rbp+40h]; this
0x1800aa568  lea     r8, aOnecoreBaseApp_24; "onecore\\base\\appmodel\\staterepositor"...
0x1800aa56f  mov     ebx, 8007000Eh
0x1800aa574  mov     edx, 5B0h; void *
0x1800aa579  mov     r9d, ebx; char *
0x1800aa57c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800aa581  xor     ecx, ecx; Block
0x1800aa583  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1800aa588  lea     rcx, [rbp+var_18]; this
0x1800aa58c  call    ?Reset@TextA@StateRepository@@QEAAXXZ; StateRepository::TextA::Reset(void)
0x1800aa591  mov     eax, ebx
0x1800aa593  jmp     short loc_1800AA5E2
0x1800aa595  mov     r8, rdi; wchar_t *
0x1800aa598  mov     rdx, rsi; unsigned __int64
0x1800aa59b  mov     rcx, rbx; wchar_t *
0x1800aa59e  call    ?StringCchCopyW@@YAJPEA_W_KPEB_W@Z; StringCchCopyW(wchar_t *,unsigned __int64,wchar_t const *)
0x1800aa5a3  test    eax, eax
0x1800aa5a5  jns     short loc_1800AA5C0
0x1800aa5a7  mov     rcx, [rbp+40h]; this
0x1800aa5ab  lea     r8, aOnecoreBaseApp_24; "onecore\\base\\appmodel\\staterepositor"...
0x1800aa5b2  mov     r9d, eax; char *
0x1800aa5b5  mov     edx, 5B1h; void *
0x1800aa5ba  call    ?_FailFast_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_FailFast_Hr(void *,uint,char const *,long)
0x1800aa5c0  cmp     [r14], rbx
0x1800aa5c3  jz      short loc_1800AA5D0
0x1800aa5c5  mov     rcx, [r14]; Block
0x1800aa5c8  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1800aa5cd  mov     [r14], rbx
0x1800aa5d0  xor     ecx, ecx; Block
0x1800aa5d2  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1800aa5d7  lea     rcx, [rbp+var_18]; this
0x1800aa5db  call    ?Reset@TextA@StateRepository@@QEAAXXZ; StateRepository::TextA::Reset(void)
0x1800aa5e0  xor     eax, eax
0x1800aa5e2  add     rsp, 48h
0x1800aa5e6  pop     r15
0x1800aa5e8  pop     r14
0x1800aa5ea  pop     r13
0x1800aa5ec  pop     r12
0x1800aa5ee  pop     rdi
0x1800aa5ef  pop     rsi
0x1800aa5f0  pop     rbx
0x1800aa5f1  pop     rbp
0x1800aa5f2  retn
```
