# FilterAgent::LoadFilterDictionary(void)

- ea: `0x18000f1d8`
- end: `0x18000f50b`
- name: `?LoadFilterDictionary@FilterAgent@@QEAAJXZ`
- size: `819`
- prototype: `__int64 __fastcall(FilterAgent *__hidden this)`
- caller_count: `1`
- callee_count: `7`
- tags: `file_ops, registry_config, service_task`

## callers

- `0x18000e140`

## callees

- `0x180005ca4`
- `0x18000f1d8`
- `0x18000f710`
- `0x180016714`
- `0x180017774`
- `0x180021850`
- `0x180024010`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x18000f27c`
- `msvcrt!??3@YAXPEAX@Z` at `0x18000f2f6`
- `msvcrt!??3@YAXPEAX@Z` at `0x18000f308`
- `msvcrt!??3@YAXPEAX@Z` at `0x18000f38a`
- `msvcrt!??3@YAXPEAX@Z` at `0x18000f39c`
- `msvcrt!??3@YAXPEAX@Z` at `0x18000f42c`
- `msvcrt!??3@YAXPEAX@Z` at `0x18000f43e`
- `msvcrt!??3@YAXPEAX@Z` at `0x18000f4ae`
- `msvcrt!??3@YAXPEAX@Z` at `0x18000f4c0`
- `msvcrt!??3@YAXPEAX@Z` at `0x18000f27c`
- `msvcrt!??3@YAXPEAX@Z` at `0x18000f2f6`
- `msvcrt!??3@YAXPEAX@Z` at `0x18000f308`
- `msvcrt!??3@YAXPEAX@Z` at `0x18000f38a`
- `msvcrt!??3@YAXPEAX@Z` at `0x18000f39c`
- `msvcrt!??3@YAXPEAX@Z` at `0x18000f42c`
- `msvcrt!??3@YAXPEAX@Z` at `0x18000f43e`
- `msvcrt!??3@YAXPEAX@Z` at `0x18000f4ae`
- `msvcrt!??3@YAXPEAX@Z` at `0x18000f4c0`

## string_xrefs

- `0x18000f356`: `mincore\textinput\dev\mtf\datasources\filterds\lib\filteragent.cpp`
- `0x18000f3f8`: `mincore\textinput\dev\mtf\datasources\filterds\lib\filteragent.cpp`

## pseudocode

```c
__int64 __fastcall FilterAgent::LoadFilterDictionary(FilterAgent *this)
{
  void **v2; // rdx
  int v3; // ebx
  struct IJDictsDictionaryManifest *v4; // rcx
  void *v6; // rbx
  unsigned int v7; // esi
  struct IJDictsDictionaryManifest *v8; // rcx
  int v9; // eax
  struct IJDictsFilterDictionary *v10; // rcx
  struct IJDictsDictionaryManifest *v11; // rcx
  int v12; // eax
  struct IJDictsFilterDictionary *v13; // rcx
  struct IJDictsDictionaryManifest *v14; // rcx
  struct IJDictsFilterDictionary *v15; // rcx
  struct IJDictsDictionaryManifest *v16; // rcx
  int v17; // [rsp+20h] [rbp-49h]
  struct IJDictsDictionaryManifest *v18; // [rsp+30h] [rbp-39h] BYREF
  struct IJDictsFilterDictionary *v19; // [rsp+38h] [rbp-31h] BYREF
  unsigned int v20; // [rsp+40h] [rbp-29h] BYREF
  __int128 v21; // [rsp+48h] [rbp-21h] BYREF
  __int64 v22; // [rsp+58h] [rbp-11h]
  void *v23[2]; // [rsp+60h] [rbp-9h] BYREF
  __int64 v24; // [rsp+70h] [rbp+7h]
  unsigned __int64 v25; // [rsp+78h] [rbp+Fh]
  wil::details::in1diag3 *retaddr; // [rsp+C8h] [rbp+5Fh]

  if ( *(_BYTE *)(*((_QWORD *)this + 2) + 12LL) == 2 )
    *(_BYTE *)this = 1;
  if ( *(_BYTE *)this )
    return 0;
  v18 = 0;
  JDictsDictionaryManifest::CreateInstance(&v18);
  v25 = 7;
  v24 = 0;
  LOWORD(v23[0]) = 0;
  (*(void (__fastcall **)(_QWORD, void **))(**((_QWORD **)this + 2) + 24LL))(*((_QWORD *)this + 2), v23);
  v2 = v23;
  if ( v25 >= 8 )
    v2 = (void **)v23[0];
  v3 = (*(__int64 (__fastcall **)(struct IJDictsDictionaryManifest *, void **, __int64))(*(_QWORD *)v18 + 24LL))(
         v18,
         v2,
         1);
  if ( v3 >= 0 )
  {
    v21 = 0;
    v22 = 0;
    v20 = 32;
    std::vector<_ChunkDescriptorType>::resize(&v21);
    v6 = (void *)v21;
    v7 = (*(__int64 (__fastcall **)(struct IJDictsDictionaryManifest *, _QWORD, unsigned int *))(*(_QWORD *)v18 + 40LL))(
           v18,
           v21,
           &v20);
    if ( v7 )
    {
      if ( v6 )
        operator delete(v6);
      if ( v25 >= 8 )
        operator delete(v23[0]);
      v25 = 7;
      v24 = 0;
      LOWORD(v23[0]) = 0;
      v8 = v18;
      if ( v18 )
      {
        v18 = 0;
        (*(void (__fastcall **)(struct IJDictsDictionaryManifest *))(*(_QWORD *)v8 + 16LL))(v8);
      }
      return v7;
    }
    v19 = 0;
    v9 = JDictsFilterDictionary::CreateInstance(&v19);
    v7 = v9;
    if ( v9 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x5C,
        (unsigned int)"mincore\\textinput\\dev\\mtf\\datasources\\filterds\\lib\\filteragent.cpp",
        (const char *)(unsigned int)v9,
        v17);
      v10 = v19;
      if ( v19 )
      {
        v19 = 0;
        (*(void (__fastcall **)(struct IJDictsFilterDictionary *))(*(_QWORD *)v10 + 16LL))(v10);
      }
      if ( v6 )
        operator delete(v6);
      if ( v25 >= 8 )
        operator delete(v23[0]);
      v25 = 7;
      v24 = 0;
      LOWORD(v23[0]) = 0;
      v11 = v18;
      if ( v18 )
      {
        v18 = 0;
        (*(void (__fastcall **)(struct IJDictsDictionaryManifest *))(*(_QWORD *)v11 + 16LL))(v11);
      }
      return v7;
    }
    v12 = (*(__int64 (__fastcall **)(struct IJDictsFilterDictionary *, void *, _QWORD, __int64))(*(_QWORD *)v19 + 24LL))(
            v19,
            v6,
            v20,
            1);
    v7 = v12;
    if ( v12 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x5D,
        (unsigned int)"mincore\\textinput\\dev\\mtf\\datasources\\filterds\\lib\\filteragent.cpp",
        (const char *)(unsigned int)v12,
        v17);
      v13 = v19;
      if ( v19 )
      {
        v19 = 0;
        (*(void (__fastcall **)(struct IJDictsFilterDictionary *))(*(_QWORD *)v13 + 16LL))(v13);
      }
      if ( v6 )
        operator delete(v6);
      if ( v25 >= 8 )
        operator delete(v23[0]);
      v25 = 7;
      v24 = 0;
      LOWORD(v23[0]) = 0;
      v14 = v18;
      if ( v18 )
      {
        v18 = 0;
        (*(void (__fastcall **)(struct IJDictsDictionaryManifest *))(*(_QWORD *)v14 + 16LL))(v14);
      }
      return v7;
    }
    v15 = v19;
    if ( v19 )
    {
      (*(void (__fastcall **)(struct IJDictsFilterDictionary *))(*(_QWORD *)v19 + 8LL))(v19);
      v15 = v19;
    }
    *((_QWORD *)this + 1) = v15;
    *(_BYTE *)this = 1;
    if ( v15 )
    {
      v19 = 0;
      (*(void (__fastcall **)(struct IJDictsFilterDictionary *))(*(_QWORD *)v15 + 16LL))(v15);
    }
    if ( v6 )
      operator delete(v6);
    if ( v25 >= 8 )
      operator delete(v23[0]);
    v25 = 7;
    v24 = 0;
    LOWORD(v23[0]) = 0;
    v16 = v18;
    if ( v18 )
    {
      v18 = 0;
      (*(void (__fastcall **)(struct IJDictsDictionaryManifest *))(*(_QWORD *)v16 + 16LL))(v16);
    }
    return 0;
  }
  if ( v25 >= 8 )
    operator delete(v23[0]);
  v25 = 7;
  v24 = 0;
  LOWORD(v23[0]) = 0;
  v4 = v18;
  if ( v18 )
  {
    v18 = 0;
    (*(void (__fastcall **)(struct IJDictsDictionaryManifest *))(*(_QWORD *)v4 + 16LL))(v4);
  }
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x18000f1d8  push    rbp
0x18000f1da  push    rbx
0x18000f1db  push    rsi
0x18000f1dc  push    rdi
0x18000f1dd  push    r14
0x18000f1df  push    r15
0x18000f1e1  lea     rbp, [rsp-2Fh]
0x18000f1e6  sub     rsp, 98h
0x18000f1ed  mov     rax, cs:__security_cookie
0x18000f1f4  xor     rax, rsp
0x18000f1f7  mov     [rbp+57h+var_40], rax
0x18000f1fb  mov     rdi, rcx
0x18000f1fe  mov     rax, [rcx+10h]
0x18000f202  cmp     byte ptr [rax+0Ch], 2
0x18000f206  jnz     short loc_18000F20B
0x18000f208  mov     byte ptr [rcx], 1
0x18000f20b  xor     r14d, r14d
0x18000f20e  cmp     [rcx], r14b
0x18000f211  jnz     loc_18000F4ED
0x18000f217  mov     [rbp+57h+var_90], r14
0x18000f21b  lea     rcx, [rbp+57h+var_90]; struct IJDictsDictionaryManifest **
0x18000f21f  call    ?CreateInstance@JDictsDictionaryManifest@@SAJPEAPEAUIJDictsDictionaryManifest@@@Z; JDictsDictionaryManifest::CreateInstance(IJDictsDictionaryManifest * *)
0x18000f224  lea     r15d, [r14+7]
0x18000f228  mov     [rbp+57h+var_48], r15
0x18000f22c  mov     [rbp+57h+var_50], r14
0x18000f230  mov     word ptr [rbp+57h+var_60], r14w
0x18000f235  mov     rcx, [rdi+10h]
0x18000f239  mov     rax, [rcx]
0x18000f23c  lea     rdx, [rbp+57h+var_60]
0x18000f240  mov     rax, [rax+18h]
0x18000f244  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f249  mov     rcx, [rbp+57h+var_90]
0x18000f24d  mov     rax, [rcx]
0x18000f250  lea     rdx, [rbp+57h+var_60]
0x18000f254  cmp     [rbp+57h+var_48], 8
0x18000f259  cmovnb  rdx, [rbp+57h+var_60]
0x18000f25e  lea     r8d, [r14+1]
0x18000f262  mov     rax, [rax+18h]
0x18000f266  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f26b  mov     ebx, eax
0x18000f26d  test    eax, eax
0x18000f26f  jns     short loc_18000F2B0
0x18000f271  cmp     [rbp+57h+var_48], 8
0x18000f276  jb      short loc_18000F282
0x18000f278  mov     rcx, [rbp+57h+var_60]
0x18000f27c  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x18000f282  mov     [rbp+57h+var_48], r15
0x18000f286  mov     [rbp+57h+var_50], r14
0x18000f28a  mov     word ptr [rbp+57h+var_60], r14w
0x18000f28f  mov     rcx, [rbp+57h+var_90]
0x18000f293  test    rcx, rcx
0x18000f296  jz      short loc_18000F2A9
0x18000f298  mov     [rbp+57h+var_90], r14
0x18000f29c  mov     rax, [rcx]
0x18000f29f  mov     rax, [rax+10h]
0x18000f2a3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f2a8  nop
0x18000f2a9  mov     eax, ebx
0x18000f2ab  jmp     loc_18000F4EF
0x18000f2b0  xorps   xmm0, xmm0
0x18000f2b3  movdqu  [rbp+57h+var_78], xmm0
0x18000f2b8  mov     [rbp+57h+var_68], r14
0x18000f2bc  mov     edx, 20h ; ' '
0x18000f2c1  mov     [rbp+57h+var_80], edx
0x18000f2c4  lea     rcx, [rbp+57h+var_78]
0x18000f2c8  call    ?resize@?$vector@U_ChunkDescriptorType@@V?$allocator@U_ChunkDescriptorType@@@std@@@std@@QEAAX_K@Z; std::vector<_ChunkDescriptorType>::resize(unsigned __int64)
0x18000f2cd  mov     rcx, [rbp+57h+var_90]
0x18000f2d1  mov     rax, [rcx]
0x18000f2d4  lea     r8, [rbp+57h+var_80]
0x18000f2d8  mov     rbx, qword ptr [rbp+57h+var_78]
0x18000f2dc  mov     rdx, rbx
0x18000f2df  mov     rax, [rax+28h]
0x18000f2e3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f2e8  mov     esi, eax
0x18000f2ea  test    eax, eax
0x18000f2ec  jz      short loc_18000F33C
0x18000f2ee  test    rbx, rbx
0x18000f2f1  jz      short loc_18000F2FD
0x18000f2f3  mov     rcx, rbx
0x18000f2f6  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x18000f2fc  nop
0x18000f2fd  cmp     [rbp+57h+var_48], 8
0x18000f302  jb      short loc_18000F30E
0x18000f304  mov     rcx, [rbp+57h+var_60]
0x18000f308  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x18000f30e  mov     [rbp+57h+var_48], r15
0x18000f312  mov     [rbp+57h+var_50], r14
0x18000f316  mov     word ptr [rbp+57h+var_60], r14w
0x18000f31b  mov     rcx, [rbp+57h+var_90]
0x18000f31f  test    rcx, rcx
0x18000f322  jz      short loc_18000F335
0x18000f324  mov     [rbp+57h+var_90], r14
0x18000f328  mov     rax, [rcx]
0x18000f32b  mov     rax, [rax+10h]
0x18000f32f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f334  nop
0x18000f335  mov     eax, esi
0x18000f337  jmp     loc_18000F4EF
0x18000f33c  mov     [rbp+57h+var_88], r14
0x18000f340  lea     rcx, [rbp+57h+var_88]; struct IJDictsFilterDictionary **
0x18000f344  call    ?CreateInstance@JDictsFilterDictionary@@SAJPEAPEAUIJDictsFilterDictionary@@@Z; JDictsFilterDictionary::CreateInstance(IJDictsFilterDictionary * *)
0x18000f349  mov     esi, eax
0x18000f34b  test    eax, eax
0x18000f34d  jns     short loc_18000F3CE
0x18000f34f  mov     rcx, [rbp+5Fh]; this
0x18000f353  mov     r9d, eax; char *
0x18000f356  lea     r8, aMincoreTextinp_10; "mincore\\textinput\\dev\\mtf\\datasourc"...
0x18000f35d  mov     edx, 5Ch ; '\'; void *
0x18000f362  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000f367  nop
0x18000f368  mov     rcx, [rbp+57h+var_88]
0x18000f36c  test    rcx, rcx
0x18000f36f  jz      short loc_18000F382
0x18000f371  mov     [rbp+57h+var_88], r14
0x18000f375  mov     rax, [rcx]
0x18000f378  mov     rax, [rax+10h]
0x18000f37c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f381  nop
0x18000f382  test    rbx, rbx
0x18000f385  jz      short loc_18000F391
0x18000f387  mov     rcx, rbx
0x18000f38a  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x18000f390  nop
0x18000f391  cmp     [rbp+57h+var_48], 8
0x18000f396  jb      short loc_18000F3A2
0x18000f398  mov     rcx, [rbp+57h+var_60]
0x18000f39c  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x18000f3a2  mov     [rbp+57h+var_48], r15
0x18000f3a6  mov     [rbp+57h+var_50], r14
0x18000f3aa  mov     word ptr [rbp+57h+var_60], r14w
0x18000f3af  mov     rcx, [rbp+57h+var_90]
0x18000f3b3  test    rcx, rcx
0x18000f3b6  jz      short loc_18000F3C9
0x18000f3b8  mov     [rbp+57h+var_90], r14
0x18000f3bc  mov     rax, [rcx]
0x18000f3bf  mov     rax, [rax+10h]
0x18000f3c3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f3c8  nop
0x18000f3c9  jmp     loc_18000F335
0x18000f3ce  mov     rcx, [rbp+57h+var_88]
0x18000f3d2  mov     rax, [rcx]
0x18000f3d5  mov     r9d, 1
0x18000f3db  mov     r8d, [rbp+57h+var_80]
0x18000f3df  mov     rdx, rbx
0x18000f3e2  mov     rax, [rax+18h]
0x18000f3e6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f3eb  mov     esi, eax
0x18000f3ed  test    eax, eax
0x18000f3ef  jns     short loc_18000F470
0x18000f3f1  mov     rcx, [rbp+5Fh]; this
0x18000f3f5  mov     r9d, eax; char *
0x18000f3f8  lea     r8, aMincoreTextinp_10; "mincore\\textinput\\dev\\mtf\\datasourc"...
0x18000f3ff  mov     edx, 5Dh ; ']'; void *
0x18000f404  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000f409  nop
0x18000f40a  mov     rcx, [rbp+57h+var_88]
0x18000f40e  test    rcx, rcx
0x18000f411  jz      short loc_18000F424
0x18000f413  mov     [rbp+57h+var_88], r14
0x18000f417  mov     rax, [rcx]
0x18000f41a  mov     rax, [rax+10h]
0x18000f41e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f423  nop
0x18000f424  test    rbx, rbx
0x18000f427  jz      short loc_18000F433
0x18000f429  mov     rcx, rbx
0x18000f42c  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x18000f432  nop
0x18000f433  cmp     [rbp+57h+var_48], 8
0x18000f438  jb      short loc_18000F444
0x18000f43a  mov     rcx, [rbp+57h+var_60]
0x18000f43e  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x18000f444  mov     [rbp+57h+var_48], r15
0x18000f448  mov     [rbp+57h+var_50], r14
0x18000f44c  mov     word ptr [rbp+57h+var_60], r14w
0x18000f451  mov     rcx, [rbp+57h+var_90]
0x18000f455  test    rcx, rcx
0x18000f458  jz      short loc_18000F46B
0x18000f45a  mov     [rbp+57h+var_90], r14
0x18000f45e  mov     rax, [rcx]
0x18000f461  mov     rax, [rax+10h]
0x18000f465  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f46a  nop
0x18000f46b  jmp     loc_18000F335
0x18000f470  mov     rcx, [rbp+57h+var_88]
0x18000f474  test    rcx, rcx
0x18000f477  jz      short loc_18000F489
0x18000f479  mov     rax, [rcx]
0x18000f47c  mov     rax, [rax+8]
0x18000f480  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f485  mov     rcx, [rbp+57h+var_88]
0x18000f489  mov     [rdi+8], rcx
0x18000f48d  mov     byte ptr [rdi], 1
0x18000f490  test    rcx, rcx
0x18000f493  jz      short loc_18000F4A6
0x18000f495  mov     [rbp+57h+var_88], r14
0x18000f499  mov     rax, [rcx]
0x18000f49c  mov     rax, [rax+10h]
0x18000f4a0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f4a5  nop
0x18000f4a6  test    rbx, rbx
0x18000f4a9  jz      short loc_18000F4B5
0x18000f4ab  mov     rcx, rbx
0x18000f4ae  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x18000f4b4  nop
0x18000f4b5  cmp     [rbp+57h+var_48], 8
0x18000f4ba  jb      short loc_18000F4C6
0x18000f4bc  mov     rcx, [rbp+57h+var_60]
0x18000f4c0  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x18000f4c6  mov     [rbp+57h+var_48], r15
0x18000f4ca  mov     [rbp+57h+var_50], r14
0x18000f4ce  mov     word ptr [rbp+57h+var_60], r14w
0x18000f4d3  mov     rcx, [rbp+57h+var_90]
0x18000f4d7  test    rcx, rcx
0x18000f4da  jz      short loc_18000F4ED
0x18000f4dc  mov     [rbp+57h+var_90], r14
0x18000f4e0  mov     rax, [rcx]
0x18000f4e3  mov     rax, [rax+10h]
0x18000f4e7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f4ec  nop
0x18000f4ed  xor     eax, eax
0x18000f4ef  mov     rcx, [rbp+57h+var_40]
0x18000f4f3  xor     rcx, rsp; StackCookie
0x18000f4f6  call    __security_check_cookie
0x18000f4fb  add     rsp, 98h
0x18000f502  pop     r15
0x18000f504  pop     r14
0x18000f506  pop     rdi
0x18000f507  pop     rsi
0x18000f508  pop     rbx
0x18000f509  pop     rbp
0x18000f50a  retn
```
