# StateRepository::StatementCache::Add(StateRepository::Statement &)

- ea: `0x180100908`
- end: `0x180100be4`
- name: `?Add@StatementCache@StateRepository@@QEAAJAEAVStatement@2@@Z`
- size: `732`
- prototype: `__int64 __fastcall(StateRepository::StatementCache *this, struct StateRepository::Statement *)`
- caller_count: `17`
- callee_count: `12`
- tags: `file_ops, loader_planting`

## callers

- `0x1800eeb2c`
- `0x1800ef1c4`
- `0x1800ef690`
- `0x1800ef874`
- `0x1800f097c`
- `0x1800f0d48`
- `0x1800f1320`
- `0x1800f15c4`
- `0x1800f1808`
- `0x1800f23bc`
- `0x1800f25b4`
- `0x1800f3298`
- `0x1800f3528`
- `0x1800f3efc`
- `0x1800f40c8`
- `0x1800f9a10`
- `0x1800f9acc`

## callees

- `0x180003430`
- `0x180007040`
- `0x180008270`
- `0x18000ed00`
- `0x180016970`
- `0x1800e4c4c`
- `0x1800e4e0a`
- `0x1800eabf4`
- `0x1800ffb60`
- `0x1800ffd20`
- `0x180100108`
- `0x180100908`

## import_xrefs

- `ntdll!RtlAllocateHeap` at `0x180100ac1`
- `ntdll!RtlAllocateHeap` at `0x180100ac1`
- `ntdll!RtlFreeHeap` at `0x180100b05`
- `ntdll!RtlFreeHeap` at `0x180100b05`
- `api-ms-win-core-realtime-l1-1-0!QueryUnbiasedInterruptTime` at `0x180100a3f`
- `api-ms-win-core-realtime-l1-1-0!QueryUnbiasedInterruptTime` at `0x180100a3f`

## string_xrefs

- `0x1801009bd`: `onecore\base\appmodel\staterepository\dataaccesslayer\statement.cpp`
- `0x1801009d3`: `onecore\base\appmodel\staterepository\dataaccesslayer\statementcache.cpp`
- `0x180100b97`: `[StatementCache.Add] #%u Database %llu: StatementCache Size/Hits/Misses %u/%llu/%llu: SQL %s`

## pseudocode

```c
__int64 __fastcall StateRepository::StatementCache::Add(
        StateRepository::StatementCache *this,
        struct StateRepository::Statement *a2)
{
  const char *v4; // rsi
  __int64 v5; // rdi
  __int64 v6; // rcx
  const char *v7; // rax
  int v8; // edi
  __int64 v9; // rdx
  __int64 v11; // rdx
  StateRepository::Statement *v12; // rax
  StateRepository::Statement *v13; // rsi
  __int64 v14; // rcx
  __int64 v15; // rcx
  unsigned __int64 v16; // rdi
  unsigned __int64 v17; // rax
  int v18; // edi
  unsigned __int64 v19; // rax
  PVOID Heap; // rax
  PVOID v21; // rbp
  const char *v22; // r9
  StateRepository::Statement *v23; // rbx
  int v24; // [rsp+20h] [rbp-58h]
  wil::details::in1diag3 *retaddr; // [rsp+78h] [rbp+0h]
  unsigned __int64 UnbiasedTime; // [rsp+88h] [rbp+10h] BYREF

  if ( *(_QWORD *)a2 )
  {
    v4 = (const char *)sqlite3_sql(*(_QWORD *)a2);
    v5 = 0;
    if ( *((_QWORD *)this + 2) )
    {
      while ( 1 )
      {
        v6 = **(_QWORD **)(*(_QWORD *)this + 8 * v5);
        v7 = v6 ? (const char *)sqlite3_sql(v6) : 0LL;
        if ( !strcmp(v4, v7) )
          break;
        if ( (unsigned __int64)++v5 >= *((_QWORD *)this + 2) )
          goto LABEL_8;
      }
      if ( v5 != 0x40000000 )
        return StateRepository::Statement::Finalize(a2);
    }
LABEL_8:
    v8 = StateRepository::Statement::Reset(a2);
    if ( v8 < 0 )
    {
      v9 = 55;
LABEL_15:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v9,
        (unsigned int)"onecore\\base\\appmodel\\staterepository\\dataaccesslayer\\statement.cpp",
        (const char *)(unsigned int)v8,
        v24);
      v11 = 29;
LABEL_16:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v11,
        (unsigned int)"onecore\\base\\appmodel\\staterepository\\dataaccesslayer\\statementcache.cpp",
        (const char *)(unsigned int)v8,
        v24);
      return (unsigned int)v8;
    }
    if ( *(_QWORD *)a2 )
    {
      v8 = sqlite3_clear_bindings();
      if ( v8 < 0 )
      {
        v9 = 56;
        goto LABEL_15;
      }
    }
    v12 = (StateRepository::Statement *)operator new(0x10u, (const struct std::nothrow_t *)&std::nothrow);
    v13 = v12;
    if ( !v12 )
    {
      v8 = -2147024882;
      v11 = 32;
      goto LABEL_16;
    }
    *(_QWORD *)v12 = 0;
    *((_QWORD *)v12 + 1) = 0;
    v14 = *(_QWORD *)a2;
    *(_QWORD *)a2 = 0;
    *(_QWORD *)v12 = v14;
    UnbiasedTime = 0;
    QueryUnbiasedInterruptTime(&UnbiasedTime);
    *((_QWORD *)v13 + 1) = UnbiasedTime / 0x2710;
    v15 = *((_QWORD *)this + 2);
    v16 = v15 + 1;
    v17 = *((_QWORD *)this + 1);
    if ( v15 + 1 > v17 )
    {
      if ( v17 == 0x3FFFFFFF )
      {
        v18 = -2147483637;
LABEL_35:
        if ( (dword_18013F948 & 8) != 0 )
        {
          sqlite3_db_handle(*(_QWORD *)v13);
          if ( *(_QWORD *)v13 && sqlite3_sql(*(_QWORD *)v13) )
          {
            if ( *(_QWORD *)v13 )
              v22 = (const char *)sqlite3_sql(*(_QWORD *)v13);
            else
              v22 = 0;
          }
          else
          {
            v22 = "<null>";
          }
          sqlite3_log(
            (unsigned int)v18,
            "[StatementCache.Add] #%u Database %llu: StatementCache Size/Hits/Misses %u/%llu/%llu: SQL %s",
            _InterlockedIncrement(&dword_180140410),
            0,
            *((_DWORD *)this + 4),
            *((_QWORD *)this + 4),
            *((_QWORD *)this + 5),
            v22);
        }
        v23 = 0;
        if ( v18 < 0 )
          v23 = v13;
        if ( v23 )
        {
          StateRepository::Statement::~Statement(v23);
          operator delete(v23);
        }
        return 0;
      }
      if ( v17 )
        v19 = ((3 * v17) >> 1) + 1;
      else
        v19 = 16;
      if ( v16 <= v19 )
        v16 = v19;
      if ( v16 > 0x3FFFFFFF )
        v16 = 0x3FFFFFFF;
      Heap = RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 0, 8 * v16);
      v21 = Heap;
      if ( !Heap )
      {
        v18 = -2147024882;
        goto LABEL_35;
      }
      if ( *(_QWORD *)this )
      {
        memmove_0(Heap, *(const void **)this, 8LL * *((_QWORD *)this + 2));
        if ( *(_QWORD *)this )
          RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, *(PVOID *)this);
      }
      *(_QWORD *)this = v21;
      *((_QWORD *)this + 1) = v16;
      v15 = *((_QWORD *)this + 2);
    }
    *(_QWORD *)(*(_QWORD *)this + 8 * v15) = v13;
    ++*((_QWORD *)this + 2);
    v18 = 0;
    goto LABEL_35;
  }
  return 0;
}

```

## disassembly

```asm
0x180100908  push    rbx
0x18010090a  push    rbp
0x18010090b  push    rsi
0x18010090c  push    rdi
0x18010090d  push    r12
0x18010090f  push    r14
0x180100911  sub     rsp, 48h
0x180100915  mov     r14, rdx
0x180100918  mov     rbx, rcx
0x18010091b  mov     rcx, [rdx]
0x18010091e  test    rcx, rcx
0x180100921  jz      loc_180100BC6
0x180100927  call    sqlite3_sql
0x18010092c  mov     rsi, rax
0x18010092f  xor     edi, edi
0x180100931  cmp     [rbx+10h], rdi
0x180100935  jbe     short loc_180100977
0x180100937  mov     rcx, [rbx]
0x18010093a  mov     rdx, [rcx+rdi*8]
0x18010093e  mov     rcx, [rdx]
0x180100941  test    rcx, rcx
0x180100944  jnz     short loc_18010094A
0x180100946  xor     eax, eax
0x180100948  jmp     short loc_18010094F
0x18010094a  call    sqlite3_sql
0x18010094f  mov     rcx, rsi
0x180100952  sub     rax, rsi
0x180100955  movzx   edx, byte ptr [rcx]
0x180100958  movzx   r8d, byte ptr [rcx+rax]
0x18010095d  sub     edx, r8d
0x180100960  jnz     short loc_18010096A
0x180100962  inc     rcx
0x180100965  test    r8d, r8d
0x180100968  jnz     short loc_180100955
0x18010096a  test    edx, edx
0x18010096c  jz      short loc_18010098C
0x18010096e  inc     rdi
0x180100971  cmp     rdi, [rbx+10h]
0x180100975  jb      short loc_180100937
0x180100977  mov     rcx, r14; this
0x18010097a  call    ?Reset@Statement@StateRepository@@QEAAJXZ; StateRepository::Statement::Reset(void)
0x18010097f  mov     edi, eax
0x180100981  test    eax, eax
0x180100983  jns     short loc_1801009A2
0x180100985  mov     edx, 37h ; '7'
0x18010098a  jmp     short loc_1801009BA
0x18010098c  cmp     rdi, 40000000h
0x180100993  jz      short loc_180100977
0x180100995  mov     rcx, r14; this
0x180100998  call    ?Finalize@Statement@StateRepository@@QEAAJXZ; StateRepository::Statement::Finalize(void)
0x18010099d  jmp     loc_180100BC8
0x1801009a2  mov     rcx, [r14]
0x1801009a5  test    rcx, rcx
0x1801009a8  jz      short loc_1801009EE
0x1801009aa  call    sqlite3_clear_bindings
0x1801009af  mov     edi, eax
0x1801009b1  test    eax, eax
0x1801009b3  jns     short loc_1801009EE
0x1801009b5  mov     edx, 38h ; '8'; void *
0x1801009ba  mov     r9d, edi; char *
0x1801009bd  lea     r8, aOnecoreBaseApp_27; "onecore\\base\\appmodel\\staterepositor"...
0x1801009c4  mov     rcx, [rsp+78h]; this
0x1801009c9  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1801009ce  mov     edx, 1Dh; void *
0x1801009d3  lea     r8, aOnecoreBaseApp_23; "onecore\\base\\appmodel\\staterepositor"...
0x1801009da  mov     r9d, edi; char *
0x1801009dd  mov     rcx, [rsp+78h]; this
0x1801009e2  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1801009e7  mov     eax, edi
0x1801009e9  jmp     loc_180100BC8
0x1801009ee  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x1801009f5  mov     r12d, 10h
0x1801009fb  mov     ecx, r12d; unsigned __int64
0x1801009fe  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x180100a03  mov     rsi, rax
0x180100a06  test    rax, rax
0x180100a09  jz      loc_180100BD5
0x180100a0f  mov     qword ptr [rax], 0
0x180100a16  mov     qword ptr [rax+8], 0
0x180100a1e  mov     rcx, [r14]
0x180100a21  mov     qword ptr [r14], 0
0x180100a28  mov     [rax], rcx
0x180100a2b  mov     [rsp+78h+UnbiasedTime], 0
0x180100a37  lea     rcx, [rsp+78h+UnbiasedTime]; UnbiasedTime
0x180100a3f  call    cs:__imp_QueryUnbiasedInterruptTime
0x180100a45  mov     rax, 346DC5D63886594Bh
0x180100a4f  mul     [rsp+78h+UnbiasedTime]
0x180100a57  shr     rdx, 0Bh
0x180100a5b  mov     [rsi+8], rdx
0x180100a5f  mov     rcx, [rbx+10h]
0x180100a63  lea     rdi, [rcx+1]
0x180100a67  mov     rax, [rbx+8]
0x180100a6b  cmp     rdi, rax
0x180100a6e  jbe     loc_180100B16
0x180100a74  mov     ecx, 3FFFFFFFh
0x180100a79  cmp     rax, rcx
0x180100a7c  jnz     short loc_180100A88
0x180100a7e  mov     edi, 8000000Bh
0x180100a83  jmp     loc_180100B23
0x180100a88  test    rax, rax
0x180100a8b  jnz     short loc_180100A92
0x180100a8d  mov     rax, r12
0x180100a90  jmp     short loc_180100A9C
0x180100a92  lea     rax, [rax+rax*2]
0x180100a96  shr     rax, 1
0x180100a99  inc     rax
0x180100a9c  cmp     rdi, rax
0x180100a9f  cmovbe  rdi, rax
0x180100aa3  cmp     rdi, rcx
0x180100aa6  cmova   rdi, rcx
0x180100aaa  lea     r8, ds:0[rdi*8]; Size
0x180100ab2  mov     rcx, gs:60h
0x180100abb  xor     edx, edx; Flags
0x180100abd  mov     rcx, [rcx+30h]; HeapHandle
0x180100ac1  call    cs:__imp_RtlAllocateHeap
0x180100ac7  mov     rbp, rax
0x180100aca  test    rax, rax
0x180100acd  jnz     short loc_180100AD6
0x180100acf  mov     edi, 8007000Eh
0x180100ad4  jmp     short loc_180100B23
0x180100ad6  mov     rdx, [rbx]; Src
0x180100ad9  test    rdx, rdx
0x180100adc  jz      short loc_180100B0B
0x180100ade  mov     r8, [rbx+10h]
0x180100ae2  shl     r8, 3; Size
0x180100ae6  mov     rcx, rbp; void *
0x180100ae9  call    memmove_0
0x180100aee  mov     r8, [rbx]; P
0x180100af1  test    r8, r8
0x180100af4  jz      short loc_180100B0B
0x180100af6  mov     rcx, gs:60h
0x180100aff  xor     edx, edx; Flags
0x180100b01  mov     rcx, [rcx+30h]; HeapHandle
0x180100b05  call    cs:__imp_RtlFreeHeap
0x180100b0b  mov     [rbx], rbp
0x180100b0e  mov     [rbx+8], rdi
0x180100b12  mov     rcx, [rbx+10h]
0x180100b16  mov     rax, [rbx]
0x180100b19  mov     [rax+rcx*8], rsi
0x180100b1d  inc     qword ptr [rbx+10h]
0x180100b21  xor     edi, edi
0x180100b23  test    byte ptr cs:dword_18013F948, 8
0x180100b2a  jz      short loc_180100BA5
0x180100b2c  mov     rcx, [rsi]
0x180100b2f  call    sqlite3_db_handle
0x180100b34  mov     rcx, [rsi]
0x180100b37  test    rcx, rcx
0x180100b3a  jz      short loc_180100B5D
0x180100b3c  call    sqlite3_sql
0x180100b41  test    rax, rax
0x180100b44  jz      short loc_180100B5D
0x180100b46  mov     rcx, [rsi]
0x180100b49  test    rcx, rcx
0x180100b4c  jnz     short loc_180100B53
0x180100b4e  xor     r9d, r9d
0x180100b51  jmp     short loc_180100B64
0x180100b53  call    sqlite3_sql
0x180100b58  mov     r9, rax
0x180100b5b  jmp     short loc_180100B64
0x180100b5d  lea     r9, aNull_1; "<null>"
0x180100b64  mov     rax, [rbx+28h]
0x180100b68  mov     rcx, [rbx+20h]
0x180100b6c  mov     edx, [rbx+10h]
0x180100b6f  mov     r8d, 1
0x180100b75  lock xadd cs:dword_180140410, r8d
0x180100b7e  inc     r8d
0x180100b81  mov     [rsp+78h+var_40], r9
0x180100b86  mov     [rsp+78h+var_48], rax
0x180100b8b  mov     [rsp+78h+var_50], rcx
0x180100b90  mov     [rsp+78h+var_58], edx
0x180100b94  xor     r9d, r9d
0x180100b97  lea     rdx, aStatementcache_0; "[StatementCache.Add] #%u Database %llu:"...
0x180100b9e  mov     ecx, edi
0x180100ba0  call    sqlite3_log
0x180100ba5  xor     ebx, ebx
0x180100ba7  test    edi, edi
0x180100ba9  cmovs   rbx, rsi
0x180100bad  test    rbx, rbx
0x180100bb0  jz      short loc_180100BC6
0x180100bb2  mov     rcx, rbx; this
0x180100bb5  call    ??1Statement@StateRepository@@QEAA@XZ; StateRepository::Statement::~Statement(void)
0x180100bba  nop
0x180100bbb  mov     rdx, r12; unsigned __int64
0x180100bbe  mov     rcx, rbx; void *
0x180100bc1  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180100bc6  xor     eax, eax
0x180100bc8  add     rsp, 48h
0x180100bcc  pop     r14
0x180100bce  pop     r12
0x180100bd0  pop     rdi
0x180100bd1  pop     rsi
0x180100bd2  pop     rbp
0x180100bd3  pop     rbx
0x180100bd4  retn
0x180100bd5  mov     edi, 8007000Eh
0x180100bda  mov     edx, 20h ; ' '
0x180100bdf  jmp     loc_1801009D3
```
