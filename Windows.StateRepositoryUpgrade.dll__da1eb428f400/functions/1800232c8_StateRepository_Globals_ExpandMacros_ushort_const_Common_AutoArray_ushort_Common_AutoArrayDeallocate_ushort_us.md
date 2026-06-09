# StateRepository::Globals::ExpandMacros(ushort const *,Common::AutoArray<ushort,&Common::AutoArrayDeallocate<ushort>(ushort *)> &)

- ea: `0x1800232c8`
- end: `0x180023558`
- name: `?ExpandMacros@Globals@StateRepository@@YAJPEBGAEAV?$AutoArray@G$1??$AutoArrayDeallocate@G@Common@@YAXPEAG@Z@Common@@@Z`
- size: `656`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: `file_ops, broker_com_uri`

## callers

- `0x180023ccc`

## callees

- `0x1800041cc`
- `0x180007f28`
- `0x18000a3c0`
- `0x18000a77c`
- `0x1800146fc`
- `0x180014728`
- `0x1800148b8`
- `0x180014ca0`
- `0x1800230d0`
- `0x1800232c8`
- `0x1800236c4`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!wcschr` at `0x180023323`
- `api-ms-win-crt-private-l1-1-0!wcschr` at `0x180023323`

## string_xrefs

- `0x1800233fd`: `onecore\base\appmodel\staterepository\dataaccesslayer\globals.cpp`
- `0x180023424`: `onecore\base\appmodel\staterepository\dataaccesslayer\globals.cpp`
- `0x180023485`: `onecore\base\appmodel\staterepository\dataaccesslayer\globals.cpp`
- `0x1800234cd`: `onecore\base\appmodel\staterepository\dataaccesslayer\globals.cpp`
- `0x180023543`: `onecore\base\appmodel\staterepository\dataaccesslayer\globals.cpp`

## pseudocode

```c
__int64 __fastcall StateRepository::Globals::ExpandMacros(__int64 a1, void **a2)
{
  const unsigned __int16 *v4; // rsi
  char v5; // r13
  unsigned __int64 v6; // rdi
  unsigned __int64 v7; // r14
  const wchar_t *v8; // rbx
  wchar_t *v9; // rax
  const unsigned __int16 *v10; // r8
  unsigned int v11; // r9d
  const unsigned __int16 *v12; // rsi
  int v13; // eax
  unsigned int v14; // ebx
  __int64 v15; // rdx
  __int64 v16; // r14
  int AppRepositoryPath; // eax
  void *v18; // rbx
  int v19; // eax
  unsigned int v20; // esi
  void *v21; // rcx
  __int64 v22; // rax
  unsigned __int64 v23; // rdi
  unsigned __int64 v24; // rax
  unsigned __int64 v25; // kr00_8
  unsigned __int16 *v26; // rax
  unsigned __int16 *v27; // rbx
  int v29; // eax
  _QWORD v30[3]; // [rsp+20h] [rbp-18h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+78h] [rbp+40h]
  void *Block; // [rsp+80h] [rbp+48h] BYREF

  v30[0] = 0;
  v4 = 0;
  v30[1] = 0;
  if ( a1 )
  {
    v5 = 0;
    v6 = -1;
    do
      ++v6;
    while ( *(_WORD *)(a1 + 2 * v6) );
    v7 = 0;
    if ( v6 )
    {
      while ( 1 )
      {
        v8 = (const wchar_t *)(a1 + 2 * v7);
        v9 = wcschr(v8, 0x25u);
        v12 = v9;
        if ( !v9 )
          break;
        if ( v9 > v8 )
        {
          v13 = StateRepository::Text::Append(
                  (StateRepository::Text *)v30,
                  (const unsigned __int16 *)(a1 + 2 * v7),
                  v9 - v8);
          v14 = v13;
          if ( v13 < 0 )
          {
            v15 = 1420;
            goto LABEL_24;
          }
        }
        v16 = ((__int64)v12 - a1) >> 1;
        if ( !(unsigned int)Common::String::CaseInsensitiveStartsWith(v12, (int)v6 - (int)v16, v10, v11) )
        {
          v14 = -2140733437;
          goto LABEL_32;
        }
        Block = 0;
        AppRepositoryPath = StateRepository::Globals::GetAppRepositoryPath(&Block);
        v14 = AppRepositoryPath;
        if ( AppRepositoryPath < 0 )
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x594,
            (unsigned int)"onecore\\base\\appmodel\\staterepository\\dataaccesslayer\\globals.cpp",
            (const char *)(unsigned int)AppRepositoryPath,
            v30[0]);
          v21 = Block;
          goto LABEL_31;
        }
        v18 = Block;
        v19 = StateRepository::Text::Append((StateRepository::Text *)v30, (const unsigned __int16 *)Block);
        v20 = v19;
        if ( v19 < 0 )
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x595,
            (unsigned int)"onecore\\base\\appmodel\\staterepository\\dataaccesslayer\\globals.cpp",
            (const char *)(unsigned int)v19,
            v30[0]);
          operator delete(v18);
          v14 = v20;
          goto LABEL_32;
        }
        v7 = v16 + 15;
        v5 = 1;
        operator delete(v18);
        if ( v7 >= v6 )
          goto LABEL_13;
      }
      if ( !v5
        || v7 >= v6
        || (v13 = StateRepository::Text::Append(
                    (StateRepository::Text *)v30,
                    (const unsigned __int16 *)(a1 + 2 * v7),
                    v6 - v7),
            v14 = v13,
            v13 >= 0) )
      {
LABEL_13:
        v4 = (const unsigned __int16 *)v30[0];
        goto LABEL_14;
      }
      v15 = 1443;
LABEL_24:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v15,
        (unsigned int)"onecore\\base\\appmodel\\staterepository\\dataaccesslayer\\globals.cpp",
        (const char *)(unsigned int)v13,
        v30[0]);
      goto LABEL_32;
    }
  }
LABEL_14:
  if ( v4 )
  {
    v22 = -1;
    do
      ++v22;
    while ( v4[v22] );
    v23 = v22 + 1;
    v25 = v22 + 1;
    v24 = 2 * (v22 + 1);
    if ( !is_mul_ok(v25, 2u) )
      v24 = -1;
    v26 = (unsigned __int16 *)operator new[](v24, (const struct std::nothrow_t *)&std::nothrow);
    v27 = v26;
    if ( !v26 )
    {
      v14 = -2147024882;
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x5B0,
        (unsigned int)"onecore\\base\\appmodel\\staterepository\\dataaccesslayer\\globals.cpp",
        (const char *)0x8007000ELL,
        v30[0]);
      v21 = 0;
LABEL_31:
      operator delete(v21);
LABEL_32:
      StateRepository::Text::Reset((StateRepository::Text *)v30);
      return v14;
    }
    v29 = StringCchCopyW(v26, v23, v4);
    if ( v29 < 0 )
      wil::details::in1diag3::_FailFast_Hr(
        retaddr,
        (void *)0x5B1,
        (unsigned int)"onecore\\base\\appmodel\\staterepository\\dataaccesslayer\\globals.cpp",
        (const char *)(unsigned int)v29,
        v30[0]);
    if ( *a2 != v27 )
    {
      operator delete(*a2);
      *a2 = v27;
    }
    operator delete(0);
  }
  else if ( *a2 )
  {
    operator delete(*a2);
    *a2 = 0;
  }
  StateRepository::Text::Reset((StateRepository::Text *)v30);
  return 0;
}

```

## disassembly

```asm
0x1800232c8  push    rbp
0x1800232ca  push    rbx
0x1800232cb  push    rsi
0x1800232cc  push    rdi
0x1800232cd  push    r12
0x1800232cf  push    r13
0x1800232d1  push    r14
0x1800232d3  push    r15
0x1800232d5  mov     rbp, rsp
0x1800232d8  sub     rsp, 38h
0x1800232dc  mov     r12, rcx
0x1800232df  mov     r15, rdx
0x1800232e2  xor     edx, edx
0x1800232e4  or      rcx, 0FFFFFFFFFFFFFFFFh
0x1800232e8  mov     [rbp+var_18], rdx
0x1800232ec  mov     esi, edx
0x1800232ee  mov     [rbp+var_10], rdx
0x1800232f2  test    r12, r12
0x1800232f5  jz      loc_1800233D4
0x1800232fb  mov     r13b, dl
0x1800232fe  mov     rdi, rcx
0x180023301  inc     rdi
0x180023304  cmp     [r12+rdi*2], dx
0x180023309  jnz     short loc_180023301
0x18002330b  mov     r14, rdx
0x18002330e  test    rdi, rdi
0x180023311  jz      loc_1800233D4
0x180023317  lea     rbx, [r12+r14*2]
0x18002331b  mov     edx, 25h ; '%'; Ch
0x180023320  mov     rcx, rbx; Str
0x180023323  call    cs:__imp_wcschr
0x180023329  xor     edx, edx
0x18002332b  mov     rsi, rax
0x18002332e  test    rax, rax
0x180023331  jz      loc_18002344B
0x180023337  cmp     rax, rbx
0x18002333a  jbe     short loc_180023364
0x18002333c  mov     r8, rax
0x18002333f  lea     rcx, [rbp+var_18]; this
0x180023343  sub     r8, rbx
0x180023346  mov     rdx, rbx; unsigned __int16 *
0x180023349  sar     r8, 1; unsigned __int64
0x18002334c  call    ?Append@Text@StateRepository@@QEAAJPEBG_K@Z; StateRepository::Text::Append(ushort const *,unsigned __int64)
0x180023351  xor     r13d, r13d
0x180023354  mov     ebx, eax
0x180023356  test    eax, eax
0x180023358  jns     short loc_180023367
0x18002335a  mov     edx, 58Ch
0x18002335f  jmp     loc_180023481
0x180023364  xor     r13d, r13d
0x180023367  mov     edx, edi
0x180023369  mov     r14, rsi
0x18002336c  sub     r14, r12
0x18002336f  mov     rcx, rsi; unsigned __int16 *
0x180023372  sar     r14, 1
0x180023375  sub     edx, r14d; unsigned int
0x180023378  call    ?CaseInsensitiveStartsWith@String@Common@@SAHPEBGK0K@Z; Common::String::CaseInsensitiveStartsWith(ushort const *,ulong,ushort const *,ulong)
0x18002337d  test    eax, eax
0x18002337f  jz      loc_180023441
0x180023385  lea     rcx, [rbp+Block]
0x180023389  mov     [rbp+Block], r13
0x18002338d  call    ?GetAppRepositoryPath@Globals@StateRepository@@YAJAEAV?$AutoArray@G$1??$AutoArrayDeallocate@G@Common@@YAXPEAG@Z@Common@@@Z; StateRepository::Globals::GetAppRepositoryPath(Common::AutoArray<ushort,&Common::AutoArrayDeallocate<ushort>(ushort *)> &)
0x180023392  mov     ebx, eax
0x180023394  test    eax, eax
0x180023396  js      loc_180023420
0x18002339c  mov     rbx, [rbp+Block]
0x1800233a0  lea     rcx, [rbp+var_18]; this
0x1800233a4  mov     rdx, rbx; unsigned __int16 *
0x1800233a7  call    ?Append@Text@StateRepository@@QEAAJPEBG@Z; StateRepository::Text::Append(ushort const *)
0x1800233ac  mov     esi, eax
0x1800233ae  test    eax, eax
0x1800233b0  js      short loc_1800233F9
0x1800233b2  mov     rcx, rbx; Block
0x1800233b5  add     r14, 0Fh
0x1800233b9  mov     r13b, 1
0x1800233bc  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1800233c1  cmp     r14, rdi
0x1800233c4  jb      loc_180023317
0x1800233ca  xor     edx, edx
0x1800233cc  mov     rsi, [rbp+var_18]
0x1800233d0  or      rcx, 0FFFFFFFFFFFFFFFFh
0x1800233d4  test    rsi, rsi
0x1800233d7  jnz     loc_180023496
0x1800233dd  mov     rcx, [r15]; Block
0x1800233e0  test    rcx, rcx
0x1800233e3  jz      loc_180023523
0x1800233e9  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1800233ee  xor     r13d, r13d
0x1800233f1  mov     [r15], r13
0x1800233f4  jmp     loc_180023523
0x1800233f9  mov     rcx, [rbp+40h]; this
0x1800233fd  lea     r8, aOnecoreBaseApp_53; "onecore\\base\\appmodel\\staterepositor"...
0x180023404  mov     r9d, esi; char *
0x180023407  mov     edx, 595h; void *
0x18002340c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180023411  mov     rcx, rbx; Block
0x180023414  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180023419  mov     ebx, esi
0x18002341b  jmp     loc_1800234ED
0x180023420  mov     rcx, [rbp+40h]; this
0x180023424  lea     r8, aOnecoreBaseApp_53; "onecore\\base\\appmodel\\staterepositor"...
0x18002342b  mov     r9d, eax; char *
0x18002342e  mov     edx, 594h; void *
0x180023433  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180023438  mov     rcx, [rbp+Block]
0x18002343c  jmp     loc_1800234E8
0x180023441  mov     ebx, 80670003h
0x180023446  jmp     loc_1800234ED
0x18002344b  test    r13b, r13b
0x18002344e  jz      loc_1800233CC
0x180023454  cmp     r14, rdi
0x180023457  jnb     loc_1800233CC
0x18002345d  sub     rdi, r14
0x180023460  lea     rdx, [r12+r14*2]; unsigned __int16 *
0x180023464  mov     r8, rdi; unsigned __int64
0x180023467  lea     rcx, [rbp+var_18]; this
0x18002346b  call    ?Append@Text@StateRepository@@QEAAJPEBG_K@Z; StateRepository::Text::Append(ushort const *,unsigned __int64)
0x180023470  xor     edx, edx
0x180023472  mov     ebx, eax
0x180023474  test    eax, eax
0x180023476  jns     loc_1800233CC
0x18002347c  mov     edx, 5A3h; void *
0x180023481  mov     rcx, [rbp+40h]; this
0x180023485  lea     r8, aOnecoreBaseApp_53; "onecore\\base\\appmodel\\staterepositor"...
0x18002348c  mov     r9d, eax; char *
0x18002348f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180023494  jmp     short loc_1800234ED
0x180023496  mov     rax, rcx
0x180023499  inc     rax
0x18002349c  cmp     [rsi+rax*2], dx
0x1800234a0  jnz     short loc_180023499
0x1800234a2  lea     rdi, [rax+1]
0x1800234a6  mov     eax, 2
0x1800234ab  mul     rdi
0x1800234ae  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x1800234b5  cmovb   rax, rcx
0x1800234b9  mov     rcx, rax; unsigned __int64
0x1800234bc  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x1800234c1  mov     rbx, rax
0x1800234c4  test    rax, rax
0x1800234c7  jnz     short loc_1800234FA
0x1800234c9  mov     rcx, [rbp+40h]; this
0x1800234cd  lea     r8, aOnecoreBaseApp_53; "onecore\\base\\appmodel\\staterepositor"...
0x1800234d4  mov     ebx, 8007000Eh
0x1800234d9  mov     edx, 5B0h; void *
0x1800234de  mov     r9d, ebx; char *
0x1800234e1  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800234e6  xor     ecx, ecx; Block
0x1800234e8  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1800234ed  lea     rcx, [rbp+var_18]; this
0x1800234f1  call    ?Reset@Text@StateRepository@@QEAAXXZ; StateRepository::Text::Reset(void)
0x1800234f6  mov     eax, ebx
0x1800234f8  jmp     short loc_18002352E
0x1800234fa  mov     r8, rsi; unsigned __int16 *
0x1800234fd  mov     rdx, rdi; unsigned __int64
0x180023500  mov     rcx, rbx; unsigned __int16 *
0x180023503  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180023508  test    eax, eax
0x18002350a  js      short loc_18002353F
0x18002350c  cmp     [r15], rbx
0x18002350f  jz      short loc_18002351C
0x180023511  mov     rcx, [r15]; Block
0x180023514  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180023519  mov     [r15], rbx
0x18002351c  xor     ecx, ecx; Block
0x18002351e  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180023523  lea     rcx, [rbp+var_18]; this
0x180023527  call    ?Reset@Text@StateRepository@@QEAAXXZ; StateRepository::Text::Reset(void)
0x18002352c  xor     eax, eax
0x18002352e  add     rsp, 38h
0x180023532  pop     r15
0x180023534  pop     r14
0x180023536  pop     r13
0x180023538  pop     r12
0x18002353a  pop     rdi
0x18002353b  pop     rsi
0x18002353c  pop     rbx
0x18002353d  pop     rbp
0x18002353e  retn
0x18002353f  mov     rcx, [rbp+40h]; this
0x180023543  lea     r8, aOnecoreBaseApp_53; "onecore\\base\\appmodel\\staterepositor"...
0x18002354a  mov     r9d, eax; char *
0x18002354d  mov     edx, 5B1h; void *
0x180023552  call    ?_FailFast_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_FailFast_Hr(void *,uint,char const *,long)
```
