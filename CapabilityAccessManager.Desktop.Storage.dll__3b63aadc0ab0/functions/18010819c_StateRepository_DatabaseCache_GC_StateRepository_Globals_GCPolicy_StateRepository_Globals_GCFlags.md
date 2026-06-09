# StateRepository::DatabaseCache::GC(StateRepository::Globals::GCPolicy,StateRepository::Globals::GCFlags)

- ea: `0x18010819c`
- end: `0x1801083be`
- name: `?GC@DatabaseCache@StateRepository@@QEAAJW4GCPolicy@Globals@2@W4GCFlags@42@@Z`
- size: `546`
- prototype: `__int64 __fastcall(void ***)`
- caller_count: `2`
- callee_count: `7`
- tags: `file_ops, registry_config`

## callers

- `0x1800f70c4`
- `0x1801019b8`

## callees

- `0x1800038f0`
- `0x1800e4e0a`
- `0x1800f7630`
- `0x1800f875c`
- `0x1800fa538`
- `0x180100bec`
- `0x18010819c`

## import_xrefs

- `api-ms-win-core-realtime-l1-1-0!QueryUnbiasedInterruptTime` at `0x1801081f4`
- `api-ms-win-core-realtime-l1-1-0!QueryUnbiasedInterruptTime` at `0x1801081f4`

## string_xrefs

- `0x1801081ca`: `onecore\base\appmodel\staterepository\dataaccesslayer\databasecache.cpp`
- `0x18010829f`: `onecore\base\appmodel\staterepository\dataaccesslayer\databasecache.cpp`
- `0x180108337`: `onecore\base\appmodel\staterepository\dataaccesslayer\databasecache.cpp`
- `0x180108389`: `onecore\base\appmodel\staterepository\dataaccesslayer\databasecache.cpp`

## pseudocode

```c
__int64 __fastcall StateRepository::DatabaseCache::GC(void ***a1)
{
  unsigned __int64 v2; // r14
  unsigned __int64 v3; // rdx
  void *v4; // rdi
  unsigned __int64 v5; // rdi
  unsigned __int64 v6; // rsi
  void *v7; // rbp
  void **v8; // rsi
  unsigned __int64 v9; // rdi
  _QWORD *v10; // rcx
  int v11; // eax
  int v13; // [rsp+20h] [rbp-38h]
  char *v14; // [rsp+30h] [rbp-28h]
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+0h]
  unsigned __int64 UnbiasedTime; // [rsp+78h] [rbp+20h] BYREF

  LODWORD(v14) = 0;
  LOBYTE(v13) = 0;
  wil::details::in1diag3::Log_HrIfMsg(
    retaddr,
    (void *)0x83,
    (unsigned int)"onecore\\base\\appmodel\\staterepository\\dataaccesslayer\\databasecache.cpp",
    (const char *)0x8000FFFFLL,
    v13,
    (bool)"policy=%d",
    v14);
  UnbiasedTime = 0;
  QueryUnbiasedInterruptTime(&UnbiasedTime);
  v2 = UnbiasedTime / 0x2710;
  if ( a1[6] && v2 - (unsigned __int64)a1[6] < (unsigned int)dword_180140448 )
    return 0;
  while ( 1 )
  {
    v3 = (unsigned __int64)a1[2];
    if ( !v3 || v2 - *((_QWORD *)**a1 + 16) <= StateRepository::Globals::PolicySettings::normal )
      break;
    if ( *((_BYTE *)a1 + 24) )
    {
      v4 = **a1;
      if ( v4 )
      {
        StateRepository::Database::~Database((StateRepository::Database *)**a1);
        operator delete(v4);
      }
    }
    memmove_0(*a1, *a1 + 1, 8LL * (_QWORD)a1[2] - 8);
    a1[2] = (void **)((char *)a1[2] - 1);
  }
  if ( v3 > *(&StateRepository::Globals::PolicySettings::normal + 1) )
  {
    if ( !v3 || (v5 = v3 - *(&StateRepository::Globals::PolicySettings::normal + 2), v5 > v3) )
    {
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0xAD,
        (int)"onecore\\base\\appmodel\\staterepository\\dataaccesslayer\\databasecache.cpp",
        (const char *)0x80070057LL);
      goto LABEL_22;
    }
    if ( *((_BYTE *)a1 + 24) )
    {
      v6 = 0;
      if ( v5 )
      {
        do
        {
          v7 = (*a1)[v6];
          if ( v7 )
          {
            StateRepository::Database::~Database((StateRepository::Database *)(*a1)[v6]);
            operator delete(v7);
          }
          ++v6;
        }
        while ( v6 < v5 );
        goto LABEL_19;
      }
    }
    else if ( v5 )
    {
LABEL_19:
      memmove_0(*a1, &(*a1)[v5], 8 * ((_QWORD)a1[2] - v5));
    }
    a1[2] = (void **)((char *)a1[2] - v5);
  }
LABEL_22:
  v8 = a1[2];
  v9 = 0;
  if ( v8 )
  {
    do
    {
      if ( v9 < (unsigned __int64)a1[2] )
        v10 = (*a1)[v9];
      else
        v10 = 0;
      if ( *v10 )
      {
        v11 = StateRepository::StatementCache::GC(
                (StateRepository::StatementCache *)(v10 + 5),
                (const struct StateRepository::Globals::PolicySettings *)&StateRepository::Globals::PolicySettings::normal,
                v2);
        if ( v11 < 0 )
          wil::details::in1diag3::_Log_Hr(
            retaddr,
            (void *)0xB7,
            (int)"onecore\\base\\appmodel\\staterepository\\dataaccesslayer\\databasecache.cpp",
            (const char *)(unsigned int)v11);
      }
      ++v9;
    }
    while ( v9 < (unsigned __int64)v8 );
  }
  a1[6] = (void **)v2;
  return 0;
}

```

## disassembly

```asm
0x18010819c  mov     [rsp+arg_0], rbx
0x1801081a1  mov     [rsp+arg_8], rbp
0x1801081a6  push    rsi
0x1801081a7  push    rdi
0x1801081a8  push    r14
0x1801081aa  sub     rsp, 40h
0x1801081ae  lea     rax, aPolicyD; "policy=%d"
0x1801081b5  mov     dword ptr [rsp+58h+var_28], 0; char *
0x1801081bd  mov     rbx, rcx
0x1801081c0  mov     qword ptr [rsp+58h+var_30], rax; bool
0x1801081c5  mov     rcx, [rsp+58h]; this
0x1801081ca  lea     r8, aOnecoreBaseApp_13; "onecore\\base\\appmodel\\staterepositor"...
0x1801081d1  mov     r9d, 8000FFFFh; char *
0x1801081d7  mov     byte ptr [rsp+58h+var_38], 0; int
0x1801081dc  mov     edx, 83h; void *
0x1801081e1  call    ?Log_HrIfMsg@in1diag3@details@wil@@YA_NPEAXIPEBDJ_N1ZZ; wil::details::in1diag3::Log_HrIfMsg(void *,uint,char const *,long,bool,char const *,...)
0x1801081e6  lea     rcx, [rsp+58h+UnbiasedTime]; UnbiasedTime
0x1801081eb  mov     [rsp+58h+UnbiasedTime], 0
0x1801081f4  call    cs:__imp_QueryUnbiasedInterruptTime
0x1801081fa  mov     rax, 346DC5D63886594Bh
0x180108204  mul     [rsp+58h+UnbiasedTime]
0x180108209  mov     r14, rdx
0x18010820c  shr     r14, 0Bh
0x180108210  cmp     qword ptr [rbx+30h], 0
0x180108215  jz      short loc_18010822D
0x180108217  mov     eax, cs:dword_180140448
0x18010821d  mov     rcx, r14
0x180108220  sub     rcx, [rbx+30h]
0x180108224  cmp     rcx, rax
0x180108227  jb      loc_1801083A9
0x18010822d  mov     esi, 80070057h
0x180108232  mov     rdx, [rbx+10h]
0x180108236  test    rdx, rdx
0x180108239  jz      short loc_1801082B8
0x18010823b  mov     rax, [rbx]
0x18010823e  mov     rcx, r14
0x180108241  mov     rax, [rax]
0x180108244  sub     rcx, [rax+80h]
0x18010824b  mov     eax, dword ptr cs:?normal@PolicySettings@Globals@StateRepository@@0U123@A; StateRepository::Globals::PolicySettings StateRepository::Globals::PolicySettings::normal
0x180108251  cmp     rcx, rax
0x180108254  jbe     short loc_1801082B8
0x180108256  test    rdx, rdx
0x180108259  jz      short loc_18010829A
0x18010825b  cmp     byte ptr [rbx+18h], 0
0x18010825f  jz      short loc_18010827C
0x180108261  mov     rax, [rbx]
0x180108264  mov     rdi, [rax]
0x180108267  test    rdi, rdi
0x18010826a  jz      short loc_18010827C
0x18010826c  mov     rcx, rdi; this
0x18010826f  call    ??1Database@StateRepository@@QEAA@XZ; StateRepository::Database::~Database(void)
0x180108274  mov     rcx, rdi; Block
0x180108277  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18010827c  mov     rcx, [rbx]; void *
0x18010827f  mov     r8, [rbx+10h]
0x180108283  lea     rdx, [rcx+8]; Src
0x180108287  lea     r8, ds:0FFFFFFFFFFFFFFF8h[r8*8]; Size
0x18010828f  call    memmove_0
0x180108294  dec     qword ptr [rbx+10h]
0x180108298  jmp     short loc_180108232
0x18010829a  mov     rcx, [rsp+58h]; this
0x18010829f  lea     r8, aOnecoreBaseApp_13; "onecore\\base\\appmodel\\staterepositor"...
0x1801082a6  mov     r9d, esi; char *
0x1801082a9  mov     edx, 0A4h; void *
0x1801082ae  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1801082b3  jmp     loc_180108232
0x1801082b8  mov     eax, dword ptr cs:?normal@PolicySettings@Globals@StateRepository@@0U123@A+4; StateRepository::Globals::PolicySettings StateRepository::Globals::PolicySettings::normal
0x1801082be  cmp     rdx, rax
0x1801082c1  jbe     loc_18010834B
0x1801082c7  test    rdx, rdx
0x1801082ca  jz      short loc_180108332
0x1801082cc  mov     eax, dword ptr cs:?normal@PolicySettings@Globals@StateRepository@@0U123@A+8; StateRepository::Globals::PolicySettings StateRepository::Globals::PolicySettings::normal
0x1801082d2  mov     rdi, rdx
0x1801082d5  sub     rdi, rax
0x1801082d8  cmp     rdi, rdx
0x1801082db  ja      short loc_180108332
0x1801082dd  cmp     byte ptr [rbx+18h], 0
0x1801082e1  jz      short loc_180108310
0x1801082e3  xor     esi, esi
0x1801082e5  test    rdi, rdi
0x1801082e8  jz      short loc_18010832C
0x1801082ea  mov     rax, [rbx]
0x1801082ed  mov     rbp, [rax+rsi*8]
0x1801082f1  test    rbp, rbp
0x1801082f4  jz      short loc_180108306
0x1801082f6  mov     rcx, rbp; this
0x1801082f9  call    ??1Database@StateRepository@@QEAA@XZ; StateRepository::Database::~Database(void)
0x1801082fe  mov     rcx, rbp; Block
0x180108301  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180108306  inc     rsi
0x180108309  cmp     rsi, rdi
0x18010830c  jb      short loc_1801082EA
0x18010830e  jmp     short loc_180108315
0x180108310  test    rdi, rdi
0x180108313  jz      short loc_18010832C
0x180108315  mov     rcx, [rbx]; void *
0x180108318  mov     r8, [rbx+10h]
0x18010831c  sub     r8, rdi
0x18010831f  shl     r8, 3; Size
0x180108323  lea     rdx, [rcx+rdi*8]; Src
0x180108327  call    memmove_0
0x18010832c  sub     [rbx+10h], rdi
0x180108330  jmp     short loc_18010834B
0x180108332  mov     rcx, [rsp+58h]; this
0x180108337  lea     r8, aOnecoreBaseApp_13; "onecore\\base\\appmodel\\staterepositor"...
0x18010833e  mov     r9d, esi; char *
0x180108341  mov     edx, 0ADh; void *
0x180108346  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18010834b  mov     rsi, [rbx+10h]
0x18010834f  xor     edi, edi
0x180108351  test    rsi, rsi
0x180108354  jz      short loc_1801083A5
0x180108356  cmp     rdi, [rbx+10h]
0x18010835a  jb      short loc_180108360
0x18010835c  xor     ecx, ecx
0x18010835e  jmp     short loc_180108367
0x180108360  mov     rax, [rbx]
0x180108363  mov     rcx, [rax+rdi*8]
0x180108367  cmp     qword ptr [rcx], 0
0x18010836b  jz      short loc_18010839D
0x18010836d  add     rcx, 28h ; '('; this
0x180108371  lea     rdx, ?normal@PolicySettings@Globals@StateRepository@@0U123@A; struct StateRepository::Globals::PolicySettings *
0x180108378  mov     r8, r14; unsigned __int64
0x18010837b  call    ?GC@StatementCache@StateRepository@@QEAAJAEBUPolicySettings@Globals@2@_K@Z; StateRepository::StatementCache::GC(StateRepository::Globals::PolicySettings const &,unsigned __int64)
0x180108380  test    eax, eax
0x180108382  jns     short loc_18010839D
0x180108384  mov     rcx, [rsp+58h]; this
0x180108389  lea     r8, aOnecoreBaseApp_13; "onecore\\base\\appmodel\\staterepositor"...
0x180108390  mov     r9d, eax; char *
0x180108393  mov     edx, 0B7h; void *
0x180108398  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18010839d  inc     rdi
0x1801083a0  cmp     rdi, rsi
0x1801083a3  jb      short loc_180108356
0x1801083a5  mov     [rbx+30h], r14
0x1801083a9  mov     rbx, [rsp+58h+arg_0]
0x1801083ae  xor     eax, eax
0x1801083b0  mov     rbp, [rsp+58h+arg_8]
0x1801083b5  add     rsp, 40h
0x1801083b9  pop     r14
0x1801083bb  pop     rdi
0x1801083bc  pop     rsi
0x1801083bd  retn
```
