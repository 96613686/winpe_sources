# ADPDatabase::BeginTransaction(TransactionLockType)

- ea: `0x180031978`
- end: `0x180031b1c`
- name: `?BeginTransaction@ADPDatabase@@QEAA?AVTransaction@@W4TransactionLockType@@@Z`
- size: `420`
- prototype: `__int64 __fastcall(__int64, __int64, int, const char *)`
- caller_count: `9`
- callee_count: `5`
- tags: `service_task, installer_update`

## callers

- `0x180014780`
- `0x180017e74`
- `0x180018470`
- `0x1800279cc`
- `0x180027d0c`
- `0x180027eb8`
- `0x180028224`
- `0x18002a148`
- `0x18002a30c`

## callees

- `0x180005290`
- `0x18002888c`
- `0x180031978`
- `0x1800347ec`
- `0x180034998`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x180031a48`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x180031a63`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x180031a48`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x180031a63`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800319f5`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180031a10`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800319f5`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180031a10`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800319d2`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800319d2`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x180031a25`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x180031a25`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800319fd`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180031a50`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800319fd`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180031a50`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800319ea`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180031a3d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800319ea`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180031a3d`

## string_xrefs

- `0x180031b0a`: `onecoreuap\base\appmodel\aggregateddataplatform\service\datastores\databasetransaction.cpp`

## pseudocode

```c
__int64 __fastcall ADPDatabase::BeginTransaction(__int64 a1, __int64 a2, int a3, const char *a4)
{
  RTL_SRWLOCK *v5; // rdi
  __int64 v6; // r13
  unique_sqlite3_transaction *v7; // rsi
  struct sqlite3_stmt **v8; // rbp
  char *v9; // r14
  char *v10; // r15
  RTL_SRWLOCK *v11; // r15
  DWORD v12; // ebx
  RTL_SRWLOCK *v13; // r14
  DWORD LastError; // ebx
  unique_sqlite3_transaction *v15; // rbx
  struct sqlite3_stmt **v16; // rbx
  char v18; // [rsp+28h] [rbp-70h] BYREF
  char v19; // [rsp+30h] [rbp-68h] BYREF
  struct sqlite3_stmt *v20; // [rsp+38h] [rbp-60h] BYREF
  struct sqlite3_stmt *v21; // [rsp+40h] [rbp-58h]
  wil::details::in1diag3 *retaddr; // [rsp+98h] [rbp+0h]

  v5 = (RTL_SRWLOCK *)(a1 + 24);
  v6 = *(_QWORD *)(a1 + 32);
  *(_QWORD *)a2 = &Transaction::`vftable';
  v7 = (unique_sqlite3_transaction *)(a2 + 8);
  *(_QWORD *)(a2 + 8) = 0;
  v8 = (struct sqlite3_stmt **)(a2 + 16);
  *(_QWORD *)(a2 + 16) = 0;
  v9 = (char *)(a2 + 24);
  *(_QWORD *)(a2 + 24) = 0;
  v10 = (char *)(a2 + 32);
  *(_QWORD *)(a2 + 32) = 0;
  *(_BYTE *)(a2 + 40) = 0;
  *(_QWORD *)(a2 + 48) = 0;
  if ( a3 )
  {
    if ( a3 != 1 )
      wil::details::in1diag3::_FailFast_Unexpected(
        retaddr,
        (void *)0x12,
        (unsigned int)"onecoreuap\\base\\appmodel\\aggregateddataplatform\\service\\datastores\\databasetransaction.cpp",
        a4);
    AcquireSRWLockShared(v5);
    if ( v10 == &v19 )
    {
      if ( v5 )
        ReleaseSRWLockShared(v5);
    }
    else
    {
      v13 = *(RTL_SRWLOCK **)v10;
      if ( *(_QWORD *)v10 )
      {
        LastError = GetLastError();
        ReleaseSRWLockShared(v13);
        SetLastError(LastError);
      }
      *(_QWORD *)v10 = v5;
    }
  }
  else
  {
    AcquireSRWLockExclusive(v5);
    if ( v9 == &v18 )
    {
      if ( v5 )
        ReleaseSRWLockExclusive(v5);
    }
    else
    {
      v11 = *(RTL_SRWLOCK **)v9;
      if ( *(_QWORD *)v9 )
      {
        v12 = GetLastError();
        ReleaseSRWLockExclusive(v11);
        SetLastError(v12);
      }
      *(_QWORD *)v9 = v5;
    }
  }
  v15 = (unique_sqlite3_transaction *)unique_sqlite3_transaction::begin((__int64)&v20, v6);
  if ( v7 != v15 )
  {
    unique_sqlite3_transaction::rollback_if_needed_or_terminate(v7);
    if ( *(_QWORD *)v7 )
      unique_sqlite3_stmt::release_or_terminate(*(struct sqlite3_stmt **)v7);
    *(_QWORD *)v7 = *(_QWORD *)v15;
    *(_QWORD *)v15 = 0;
    v16 = (struct sqlite3_stmt **)((char *)v15 + 8);
    if ( v8 != v16 )
    {
      if ( *v8 )
        unique_sqlite3_stmt::release_or_terminate(*v8);
      *v8 = *v16;
      *v16 = 0;
    }
  }
  unique_sqlite3_transaction::rollback_if_needed_or_terminate((unique_sqlite3_transaction *)&v20);
  if ( v21 )
    unique_sqlite3_stmt::release_or_terminate(v21);
  if ( v20 )
    unique_sqlite3_stmt::release_or_terminate(v20);
  return a2;
}

```

## disassembly

```asm
0x180031978  mov     [rsp+arg_8], rdx
0x18003197d  push    rbx
0x18003197e  push    rbp
0x18003197f  push    rsi
0x180031980  push    rdi
0x180031981  push    r12
0x180031983  push    r13
0x180031985  push    r14
0x180031987  push    r15
0x180031989  sub     rsp, 58h
0x18003198d  mov     r12, rdx
0x180031990  xor     ebx, ebx
0x180031992  lea     rdi, [rcx+18h]
0x180031996  mov     r13, [rcx+20h]
0x18003199a  lea     rax, ??_7Transaction@@6B@; const Transaction::`vftable'
0x1800319a1  mov     [rdx], rax
0x1800319a4  lea     rsi, [rdx+8]
0x1800319a8  mov     [rsi], rbx
0x1800319ab  lea     rbp, [rsi+8]
0x1800319af  mov     [rbp+0], rbx
0x1800319b3  lea     r14, [rdx+18h]
0x1800319b7  mov     [r14], rbx
0x1800319ba  lea     r15, [rdx+20h]
0x1800319be  mov     [r15], rbx
0x1800319c1  mov     [rdx+28h], bl
0x1800319c4  xor     eax, eax
0x1800319c6  mov     [rdx+30h], rax
0x1800319ca  test    r8d, r8d
0x1800319cd  jnz     short loc_180031A18
0x1800319cf  mov     rcx, rdi; SRWLock
0x1800319d2  call    cs:__imp_AcquireSRWLockExclusive
0x1800319d8  lea     rax, [rsp+98h+var_70]
0x1800319dd  cmp     r14, rax
0x1800319e0  jz      short loc_180031A08
0x1800319e2  mov     r15, [r14]
0x1800319e5  test    r15, r15
0x1800319e8  jz      short loc_180031A03
0x1800319ea  call    cs:__imp_GetLastError
0x1800319f0  mov     ebx, eax
0x1800319f2  mov     rcx, r15; SRWLock
0x1800319f5  call    cs:__imp_ReleaseSRWLockExclusive
0x1800319fb  mov     ecx, ebx; dwErrCode
0x1800319fd  call    cs:__imp_SetLastError
0x180031a03  mov     [r14], rdi
0x180031a06  jmp     short loc_180031A69
0x180031a08  test    rdi, rdi
0x180031a0b  jz      short loc_180031A69
0x180031a0d  mov     rcx, rdi; SRWLock
0x180031a10  call    cs:__imp_ReleaseSRWLockExclusive
0x180031a16  jmp     short loc_180031A69
0x180031a18  cmp     r8d, 1
0x180031a1c  jnz     loc_180031B02
0x180031a22  mov     rcx, rdi; SRWLock
0x180031a25  call    cs:__imp_AcquireSRWLockShared
0x180031a2b  lea     rax, [rsp+98h+var_68]
0x180031a30  cmp     r15, rax
0x180031a33  jz      short loc_180031A5B
0x180031a35  mov     r14, [r15]
0x180031a38  test    r14, r14
0x180031a3b  jz      short loc_180031A56
0x180031a3d  call    cs:__imp_GetLastError
0x180031a43  mov     ebx, eax
0x180031a45  mov     rcx, r14; SRWLock
0x180031a48  call    cs:__imp_ReleaseSRWLockShared
0x180031a4e  mov     ecx, ebx; dwErrCode
0x180031a50  call    cs:__imp_SetLastError
0x180031a56  mov     [r15], rdi
0x180031a59  jmp     short loc_180031A69
0x180031a5b  test    rdi, rdi
0x180031a5e  jz      short loc_180031A69
0x180031a60  mov     rcx, rdi; SRWLock
0x180031a63  call    cs:__imp_ReleaseSRWLockShared
0x180031a69  mov     rdx, r13
0x180031a6c  lea     rcx, [rsp+98h+var_60]
0x180031a71  call    ?begin@unique_sqlite3_transaction@@SA?AU1@PEAUsqlite3@@@Z; unique_sqlite3_transaction::begin(sqlite3 *)
0x180031a76  mov     rbx, rax
0x180031a79  cmp     rsi, rax
0x180031a7c  jz      short loc_180031AC5
0x180031a7e  mov     rcx, rsi; this
0x180031a81  call    ?rollback_if_needed_or_terminate@unique_sqlite3_transaction@@AEAAXXZ; unique_sqlite3_transaction::rollback_if_needed_or_terminate(void)
0x180031a86  mov     rcx, [rsi]; struct sqlite3_stmt *
0x180031a89  test    rcx, rcx
0x180031a8c  jz      short loc_180031A93
0x180031a8e  call    ?release_or_terminate@unique_sqlite3_stmt@@CAXPEAUsqlite3_stmt@@@Z; unique_sqlite3_stmt::release_or_terminate(sqlite3_stmt *)
0x180031a93  mov     rcx, [rbx]
0x180031a96  mov     [rsi], rcx
0x180031a99  mov     qword ptr [rbx], 0
0x180031aa0  add     rbx, 8
0x180031aa4  cmp     rbp, rbx
0x180031aa7  jz      short loc_180031AC5
0x180031aa9  mov     rcx, [rbp+0]; struct sqlite3_stmt *
0x180031aad  test    rcx, rcx
0x180031ab0  jz      short loc_180031AB7
0x180031ab2  call    ?release_or_terminate@unique_sqlite3_stmt@@CAXPEAUsqlite3_stmt@@@Z; unique_sqlite3_stmt::release_or_terminate(sqlite3_stmt *)
0x180031ab7  mov     rax, [rbx]
0x180031aba  mov     [rbp+0], rax
0x180031abe  mov     qword ptr [rbx], 0
0x180031ac5  lea     rcx, [rsp+98h+var_60]; this
0x180031aca  call    ?rollback_if_needed_or_terminate@unique_sqlite3_transaction@@AEAAXXZ; unique_sqlite3_transaction::rollback_if_needed_or_terminate(void)
0x180031acf  mov     rcx, [rsp+98h+var_58]; struct sqlite3_stmt *
0x180031ad4  test    rcx, rcx
0x180031ad7  jz      short loc_180031ADE
0x180031ad9  call    ?release_or_terminate@unique_sqlite3_stmt@@CAXPEAUsqlite3_stmt@@@Z; unique_sqlite3_stmt::release_or_terminate(sqlite3_stmt *)
0x180031ade  mov     rcx, [rsp+98h+var_60]; struct sqlite3_stmt *
0x180031ae3  test    rcx, rcx
0x180031ae6  jz      short loc_180031AEE
0x180031ae8  call    ?release_or_terminate@unique_sqlite3_stmt@@CAXPEAUsqlite3_stmt@@@Z; unique_sqlite3_stmt::release_or_terminate(sqlite3_stmt *)
0x180031aed  nop
0x180031aee  mov     rax, r12
0x180031af1  add     rsp, 58h
0x180031af5  pop     r15
0x180031af7  pop     r14
0x180031af9  pop     r13
0x180031afb  pop     r12
0x180031afd  pop     rdi
0x180031afe  pop     rsi
0x180031aff  pop     rbp
0x180031b00  pop     rbx
0x180031b01  retn
0x180031b02  mov     rcx, [rsp+98h]; this
0x180031b0a  lea     r8, aOnecoreuapBase_7; "onecoreuap\\base\\appmodel\\aggregatedd"...
0x180031b11  mov     edx, 12h; void *
0x180031b16  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
```
