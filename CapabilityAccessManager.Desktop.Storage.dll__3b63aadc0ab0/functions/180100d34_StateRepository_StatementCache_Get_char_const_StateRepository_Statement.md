# StateRepository::StatementCache::Get(char const *,StateRepository::Statement &)

- ea: `0x180100d34`
- end: `0x180100f7c`
- name: `?Get@StatementCache@StateRepository@@QEAAPEAVStatement@2@PEBDAEAV32@@Z`
- size: `584`
- prototype: `struct StateRepository::Statement *__fastcall(StateRepository::StatementCache *__hidden this, const char *, struct StateRepository::Statement *)`
- caller_count: `1`
- callee_count: `9`
- tags: `file_ops`

## callers

- `0x1800fb06c`

## callees

- `0x180003430`
- `0x180007040`
- `0x18000ed00`
- `0x180016970`
- `0x1800e4e0a`
- `0x1800eabf4`
- `0x1800f7630`
- `0x1800ffb60`
- `0x180100d34`

## string_xrefs

- `0x180100ef5`: `onecore\base\appmodel\staterepository\dataaccesslayer\statementcache.cpp`
- `0x180100d7e`: `[pre-StatementCache.Get] #%u StatementCache Size/Hits/Misses %u/%llu/%llu`
- `0x180100e95`: `[StatementCache.Get(Hit)] #%u Database %llu: StatementCache Size/Hits/Misses %u/%llu/%llu: SQL %s`
- `0x180100f5f`: `[StatementCache.Get(Miss)] #%u StatementCache Size/Hits/Misses %u/%llu/%llu: SQL %s`
- `0x180100ed8`: `onecore\base\appmodel\StateRepository\DataAccessLayer\StatementCache.hpp`

## pseudocode

```c
struct StateRepository::Statement *__fastcall StateRepository::StatementCache::Get(
        StateRepository::StatementCache *this,
        const char *a2,
        struct StateRepository::Statement *a3)
{
  _DWORD *v6; // r15
  unsigned __int64 i; // rsi
  __int64 v8; // rcx
  const char *v9; // rax
  StateRepository::Statement *v10; // rdi
  StateRepository::Statement **v11; // rcx
  const char *v12; // r9
  int v13; // ebx
  __int64 v14; // rdx
  __int64 v15; // rax
  int v17; // [rsp+20h] [rbp-58h]
  wil::details::in1diag3 *retaddr; // [rsp+78h] [rbp+0h]

  v6 = (_DWORD *)((char *)this + 16);
  if ( (dword_18013F948 & 8) != 0 )
    sqlite3_log(
      0,
      "[pre-StatementCache.Get] #%u StatementCache Size/Hits/Misses %u/%llu/%llu",
      _InterlockedIncrement(&dword_180140410),
      *v6,
      *((_QWORD *)this + 4),
      *((_QWORD *)this + 5));
  if ( !*(_QWORD *)v6 )
    goto LABEL_34;
  for ( i = *(_QWORD *)v6 - 1LL; ; --i )
  {
    v8 = **(_QWORD **)(*(_QWORD *)this + 8 * i);
    v9 = v8 ? (const char *)sqlite3_sql(v8) : 0LL;
    if ( !strcmp(a2, v9) )
      break;
    if ( !i )
      goto LABEL_34;
  }
  if ( i == 0x40000000 )
  {
LABEL_34:
    ++*((_QWORD *)this + 5);
    if ( (dword_18013F948 & 8) != 0 )
      sqlite3_log(
        0,
        "[StatementCache.Get(Miss)] #%u StatementCache Size/Hits/Misses %u/%llu/%llu: SQL %s",
        _InterlockedIncrement(&dword_180140410),
        *v6,
        *((_QWORD *)this + 4),
        *((_QWORD *)this + 5),
        a2);
    return 0;
  }
  ++*((_QWORD *)this + 4);
  if ( i < *(_QWORD *)v6 )
  {
    _mm_lfence();
    v11 = (StateRepository::Statement **)(*(_QWORD *)this + 8 * i);
    v10 = *v11;
    memmove_0(v11, v11 + 1, 8 * (*(_QWORD *)v6 - i) - 8);
    --*(_QWORD *)v6;
  }
  else
  {
    v10 = 0;
  }
  if ( (dword_18013F948 & 8) != 0 )
  {
    sqlite3_db_handle(*(_QWORD *)a3);
    if ( *(_QWORD *)a3 && sqlite3_sql(*(_QWORD *)a3) )
    {
      if ( *(_QWORD *)a3 )
        v12 = (const char *)sqlite3_sql(*(_QWORD *)a3);
      else
        v12 = 0;
    }
    else
    {
      v12 = "<null>";
    }
    sqlite3_log(
      0,
      "[StatementCache.Get(Hit)] #%u Database %llu: StatementCache Size/Hits/Misses %u/%llu/%llu: SQL %s",
      _InterlockedIncrement(&dword_180140410),
      0,
      *v6,
      *((_QWORD *)this + 4),
      *((_QWORD *)this + 5),
      v12);
  }
  if ( *(_QWORD *)a3 )
  {
    v13 = -2147024809;
    v14 = 39;
LABEL_28:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v14,
      (unsigned int)"onecore\\base\\appmodel\\StateRepository\\DataAccessLayer\\StatementCache.hpp",
      (const char *)(unsigned int)v13,
      v17);
    goto LABEL_29;
  }
  v15 = *(_QWORD *)v10;
  if ( !*(_QWORD *)v10 )
  {
    v13 = -2147019873;
    v14 = 41;
    goto LABEL_28;
  }
  *(_QWORD *)v10 = 0;
  *(_QWORD *)a3 = v15;
  v13 = 0;
LABEL_29:
  if ( v13 < 0 )
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x70,
      (int)"onecore\\base\\appmodel\\staterepository\\dataaccesslayer\\statementcache.cpp",
      (const char *)(unsigned int)v13);
  if ( v10 )
  {
    StateRepository::Statement::~Statement(v10);
    operator delete(v10);
  }
  return a3;
}

```

## disassembly

```asm
0x180100d34  push    rbx
0x180100d36  push    rbp
0x180100d37  push    rsi
0x180100d38  push    rdi
0x180100d39  push    r14
0x180100d3b  push    r15
0x180100d3d  sub     rsp, 48h
0x180100d41  mov     r14, r8
0x180100d44  mov     rbp, rdx
0x180100d47  mov     rbx, rcx
0x180100d4a  lea     r15, [rcx+10h]
0x180100d4e  test    byte ptr cs:dword_18013F948, 8
0x180100d55  jz      short loc_180100D8C
0x180100d57  mov     rax, [rcx+28h]
0x180100d5b  mov     r10, [rcx+20h]
0x180100d5f  mov     r9d, [r15]
0x180100d62  mov     r8d, 1
0x180100d68  lock xadd cs:dword_180140410, r8d
0x180100d71  inc     r8d
0x180100d74  mov     [rsp+78h+var_50], rax
0x180100d79  mov     qword ptr [rsp+78h+var_58], r10
0x180100d7e  lea     rdx, aPreStatementca; "[pre-StatementCache.Get] #%u StatementC"...
0x180100d85  xor     ecx, ecx
0x180100d87  call    sqlite3_log
0x180100d8c  mov     rsi, [r15]
0x180100d8f  test    rsi, rsi
0x180100d92  jz      loc_180100F26
0x180100d98  dec     rsi
0x180100d9b  mov     rax, [rbx]
0x180100d9e  mov     rcx, [rax+rsi*8]
0x180100da2  mov     rcx, [rcx]
0x180100da5  test    rcx, rcx
0x180100da8  jnz     short loc_180100DAE
0x180100daa  xor     eax, eax
0x180100dac  jmp     short loc_180100DB3
0x180100dae  call    sqlite3_sql
0x180100db3  mov     rcx, rbp
0x180100db6  sub     rax, rbp
0x180100db9  movzx   edx, byte ptr [rcx]
0x180100dbc  movzx   r8d, byte ptr [rcx+rax]
0x180100dc1  sub     edx, r8d
0x180100dc4  jnz     short loc_180100DCE
0x180100dc6  inc     rcx
0x180100dc9  test    r8d, r8d
0x180100dcc  jnz     short loc_180100DB9
0x180100dce  test    edx, edx
0x180100dd0  jz      short loc_180100DE0
0x180100dd2  test    rsi, rsi
0x180100dd5  jz      loc_180100F26
0x180100ddb  dec     rsi
0x180100dde  jmp     short loc_180100D9B
0x180100de0  cmp     rsi, 40000000h
0x180100de7  jz      loc_180100F26
0x180100ded  inc     qword ptr [rbx+20h]
0x180100df1  mov     r8, [r15]
0x180100df4  cmp     rsi, r8
0x180100df7  jb      short loc_180100DFD
0x180100df9  xor     edi, edi
0x180100dfb  jmp     short loc_180100E21
0x180100dfd  lfence
0x180100e00  mov     rax, [rbx]
0x180100e03  lea     rcx, [rax+rsi*8]; void *
0x180100e07  mov     rdi, [rcx]
0x180100e0a  sub     r8, rsi
0x180100e0d  lea     r8, ds:0FFFFFFFFFFFFFFF8h[r8*8]; Size
0x180100e15  lea     rdx, [rcx+8]; Src
0x180100e19  call    memmove_0
0x180100e1e  dec     qword ptr [r15]
0x180100e21  test    byte ptr cs:dword_18013F948, 8
0x180100e28  jz      short loc_180100EA3
0x180100e2a  mov     rcx, [r14]
0x180100e2d  call    sqlite3_db_handle
0x180100e32  mov     rcx, [r14]
0x180100e35  test    rcx, rcx
0x180100e38  jz      short loc_180100E5B
0x180100e3a  call    sqlite3_sql
0x180100e3f  test    rax, rax
0x180100e42  jz      short loc_180100E5B
0x180100e44  mov     rcx, [r14]
0x180100e47  test    rcx, rcx
0x180100e4a  jnz     short loc_180100E51
0x180100e4c  xor     r9d, r9d
0x180100e4f  jmp     short loc_180100E62
0x180100e51  call    sqlite3_sql
0x180100e56  mov     r9, rax
0x180100e59  jmp     short loc_180100E62
0x180100e5b  lea     r9, aNull_1; "<null>"
0x180100e62  mov     rax, [rbx+28h]
0x180100e66  mov     rcx, [rbx+20h]
0x180100e6a  mov     edx, [r15]
0x180100e6d  mov     r8d, 1
0x180100e73  lock xadd cs:dword_180140410, r8d
0x180100e7c  inc     r8d
0x180100e7f  mov     [rsp+78h+var_40], r9
0x180100e84  mov     [rsp+78h+var_48], rax
0x180100e89  mov     [rsp+78h+var_50], rcx
0x180100e8e  mov     [rsp+78h+var_58], edx; int
0x180100e92  xor     r9d, r9d
0x180100e95  lea     rdx, aStatementcache_2; "[StatementCache.Get(Hit)] #%u Database "...
0x180100e9c  xor     ecx, ecx
0x180100e9e  call    sqlite3_log
0x180100ea3  cmp     qword ptr [r14], 0
0x180100ea7  jz      short loc_180100EB5
0x180100ea9  mov     ebx, 80070057h
0x180100eae  mov     edx, 27h ; '''
0x180100eb3  jmp     short loc_180100ED5
0x180100eb5  mov     rax, [rdi]
0x180100eb8  test    rax, rax
0x180100ebb  jz      short loc_180100ECB
0x180100ebd  mov     qword ptr [rdi], 0
0x180100ec4  mov     [r14], rax
0x180100ec7  xor     ebx, ebx
0x180100ec9  jmp     short loc_180100EE9
0x180100ecb  mov     ebx, 8007139Fh
0x180100ed0  mov     edx, 29h ; ')'; void *
0x180100ed5  mov     r9d, ebx; char *
0x180100ed8  lea     r8, aOnecoreBaseApp_25; "onecore\\base\\appmodel\\StateRepositor"...
0x180100edf  mov     rcx, [rsp+78h]; this
0x180100ee4  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180100ee9  mov     rcx, [rsp+78h]; this
0x180100eee  test    ebx, ebx
0x180100ef0  jns     short loc_180100F06
0x180100ef2  mov     r9d, ebx; char *
0x180100ef5  lea     r8, aOnecoreBaseApp_23; "onecore\\base\\appmodel\\staterepositor"...
0x180100efc  mov     edx, 70h ; 'p'; void *
0x180100f01  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180100f06  test    rdi, rdi
0x180100f09  jz      short loc_180100F21
0x180100f0b  mov     rcx, rdi; this
0x180100f0e  call    ??1Statement@StateRepository@@QEAA@XZ; StateRepository::Statement::~Statement(void)
0x180100f13  nop
0x180100f14  mov     edx, 10h; unsigned __int64
0x180100f19  mov     rcx, rdi; void *
0x180100f1c  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180100f21  mov     rax, r14
0x180100f24  jmp     short loc_180100F6F
0x180100f26  inc     qword ptr [rbx+28h]
0x180100f2a  mov     rcx, [rbx+28h]
0x180100f2e  test    byte ptr cs:dword_18013F948, 8
0x180100f35  jz      short loc_180100F6D
0x180100f37  mov     rax, [rbx+20h]
0x180100f3b  mov     r9d, [r15]
0x180100f3e  mov     r8d, 1
0x180100f44  lock xadd cs:dword_180140410, r8d
0x180100f4d  inc     r8d
0x180100f50  mov     [rsp+78h+var_48], rbp
0x180100f55  mov     [rsp+78h+var_50], rcx
0x180100f5a  mov     qword ptr [rsp+78h+var_58], rax
0x180100f5f  lea     rdx, aStatementcache_1; "[StatementCache.Get(Miss)] #%u Statemen"...
0x180100f66  xor     ecx, ecx
0x180100f68  call    sqlite3_log
0x180100f6d  xor     eax, eax
0x180100f6f  add     rsp, 48h
0x180100f73  pop     r15
0x180100f75  pop     r14
0x180100f77  pop     rdi
0x180100f78  pop     rsi
0x180100f79  pop     rbp
0x180100f7a  pop     rbx
0x180100f7b  retn
```
