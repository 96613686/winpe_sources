# CustomEntityTable::UpdateData(std::basic_string<char,std::char_traits<char>,std::allocator<char>> const &,std::basic_string<char,std::char_traits<char>,std::allocator<char>> const &,std::basic_string<char,std::char_traits<char>,std::allocator<char>> const &,std::basic_string<char,std::char_traits<char>,std::allocator<char>> const &)

- ea: `0x180028224`
- end: `0x180028602`
- name: `?UpdateData@CustomEntityTable@@QEAAXAEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@000@Z`
- size: `990`
- prototype: ``
- caller_count: `1`
- callee_count: `17`
- tags: `file_ops, service_task, installer_update, broker_com_uri`

## callers

- `0x1800142e8`

## callees

- `0x180003516`
- `0x1800047d4`
- `0x180005290`
- `0x180025dbc`
- `0x180025e14`
- `0x180028224`
- `0x18002888c`
- `0x180031978`
- `0x180034f40`
- `0x180035024`
- `0x180039be4`
- `0x1800807c0`
- `0x1800a5f80`
- `0x1800a7030`
- `0x1800a82b0`
- `0x1800a97e0`
- `0x1800abe70`

## string_xrefs

- `0x180028578`: `Already assigned.`
- `0x1800285e1`: `Already assigned.`
- `0x180028530`: `onecoreuap\base\appmodel\aggregateddataplatform\service\datastores\customentitytable.cpp`
- `0x180028599`: `onecoreuap\base\appmodel\aggregateddataplatform\service\datastores\customentitytable.cpp`
- `0x180028387`: `DELETE FROM CustomEntities WHERE rowid IN(SELECT rowid FROM CustomEntities WHERE AppId = ? ORDER BY LastUpdatedTimestamp ASC, rowid ASC LIMIT ?);`
- `0x180028439`: `REPLACE INTO CustomEntities (Trigger, Properties, EntityKind, AppId, LastUpdatedTimestamp) VALUES (?, ?, ?, ?, datetime('now'));`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
void __fastcall CustomEntityTable::UpdateData(__int64 a1, _QWORD *a2, _QWORD *a3, const char *a4, __int64 *a5)
{
  const char *v5; // r14
  int v9; // r15d
  _QWORD *v10; // r8
  struct sqlite3_stmt *v11; // rbx
  _QWORD *v12; // r8
  const char *v13; // r8
  _QWORD *v14; // r8
  struct sqlite3_stmt *v15; // rbx
  const char *v16; // r9
  struct sqlite3_stmt *v17; // rbx
  __int64 v18; // r8
  const char *v19; // r9
  struct sqlite3 *v20; // rax
  struct sqlite3 *v21; // rax
  _BYTE v22[32]; // [rsp+40h] [rbp-71h] BYREF
  _BYTE pExceptionObject[32]; // [rsp+60h] [rbp-51h] BYREF
  RTL_SRWLOCK v24[16]; // [rsp+80h] [rbp-31h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+108h] [rbp+57h]
  struct sqlite3_stmt *v26; // [rsp+110h] [rbp+5Fh] BYREF

  v5 = a4;
  ADPDatabase::BeginTransaction(*(_QWORD *)(a1 + 8), (__int64)v24, 0, a4);
  v26 = 0;
  v9 = 0;
  sqlite3LockAndPrepare(
    *(_QWORD *)(*(_QWORD *)(a1 + 8) + 32LL),
    (unsigned int)"SELECT COUNT(*) FROM CustomEntities WHERE  AppId = ? AND (EntityKind != ? OR Trigger != ?);",
    -1,
    128,
    0,
    (__int64)&v26,
    0);
  if ( a3[3] <= 0xFu )
    LODWORD(v10) = (_DWORD)a3;
  else
    v10 = (_QWORD *)*a3;
  v11 = v26;
  bindText((_DWORD)v26, 1, (_DWORD)v10, -1, 0, 1);
  if ( a2[3] <= 0xFu )
    LODWORD(v12) = (_DWORD)a2;
  else
    v12 = (_QWORD *)*a2;
  bindText((_DWORD)v11, 2, (_DWORD)v12, -1, 0, 1);
  if ( *((_QWORD *)v5 + 3) <= 0xFu )
    LODWORD(v13) = (_DWORD)v5;
  else
    v13 = *(const char **)v5;
  bindText((_DWORD)v11, 3, (_DWORD)v13, -1, 0, 1);
  if ( (unsigned int)sqlite3_step(v11) == 100 )
    v9 = sqlite3_column_int(v11, 0);
  if ( v11 )
  {
    if ( (unsigned int)sqlite3_finalize(v11) )
    {
      v20 = (struct sqlite3 *)sqlite3_db_handle(v11);
      sqlite3_error::sqlite3_error((sqlite3_error *)v22, v20);
      sqlite3_error::sqlite3_error(pExceptionObject, v22);
      throw (sqlite3_error *)pExceptionObject;
    }
    v26 = 0;
  }
  if ( v9 >= 1000 )
  {
    sqlite3LockAndPrepare(
      *(_QWORD *)(*(_QWORD *)(a1 + 8) + 32LL),
      (unsigned int)"DELETE FROM CustomEntities WHERE rowid IN(SELECT rowid FROM CustomEntities WHERE AppId = ? ORDER BY "
                    "LastUpdatedTimestamp ASC, rowid ASC LIMIT ?);",
      -1,
      128,
      0,
      (__int64)&v26,
      0);
    if ( a3[3] <= 0xFu )
      LODWORD(v14) = (_DWORD)a3;
    else
      v14 = (_QWORD *)*a3;
    v15 = v26;
    bindText((_DWORD)v26, 1, (_DWORD)v14, -1, 0, 1);
    sqlite3_bind_int64(v15, 2, v9 - 999);
    if ( (unsigned int)sqlite3_step(v15) != 101 )
      wil::details::in1diag3::_FailFast_Unexpected(
        retaddr,
        (void *)0x53,
        (unsigned int)"onecoreuap\\base\\appmodel\\aggregateddataplatform\\service\\datastores\\customentitytable.cpp",
        v16);
    if ( v15 )
    {
      if ( (unsigned int)sqlite3_finalize(v15) )
      {
        v21 = (struct sqlite3 *)sqlite3_db_handle(v15);
        sqlite3_error::sqlite3_error((sqlite3_error *)pExceptionObject, v21);
        sqlite3_error::sqlite3_error(v22, pExceptionObject);
        throw (sqlite3_error *)v22;
      }
      v26 = 0;
    }
  }
  sqlite3LockAndPrepare(
    *(_QWORD *)(*(_QWORD *)(a1 + 8) + 32LL),
    (unsigned int)"REPLACE INTO CustomEntities (Trigger, Properties, EntityKind, AppId, LastUpdatedTimestamp) VALUES (?, "
                  "?, ?, ?, datetime('now'));",
    -1,
    128,
    0,
    (__int64)&v26,
    0);
  if ( *((_QWORD *)v5 + 3) > 0xFu )
    v5 = *(const char **)v5;
  v17 = v26;
  bindText((_DWORD)v26, 1, (_DWORD)v5, -1, 0, 1);
  LODWORD(v18) = (_DWORD)a5;
  if ( (unsigned __int64)a5[3] > 0xF )
    v18 = *a5;
  bindText((_DWORD)v17, 2, v18, -1, 0, 1);
  if ( a2[3] > 0xFu )
    a2 = (_QWORD *)*a2;
  bindText((_DWORD)v17, 3, (_DWORD)a2, -1, 0, 1);
  if ( a3[3] > 0xFu )
    a3 = (_QWORD *)*a3;
  bindText((_DWORD)v17, 4, (_DWORD)a3, -1, 0, 1);
  if ( (unsigned int)sqlite3_step(v17) != 101 )
    wil::details::in1diag3::_FailFast_Unexpected(
      retaddr,
      (void *)0x5F,
      (unsigned int)"onecoreuap\\base\\appmodel\\aggregateddataplatform\\service\\datastores\\customentitytable.cpp",
      v19);
  Transaction::Commit(v24);
  if ( v17 )
    unique_sqlite3_stmt::release_or_terminate(v17);
  Transaction::~Transaction((Transaction *)v24);
}

```

## disassembly

```asm
0x180028224  push    rbp
0x180028226  push    rbx
0x180028227  push    rsi
0x180028228  push    rdi
0x180028229  push    r12
0x18002822b  push    r13
0x18002822d  push    r14
0x18002822f  push    r15
0x180028231  lea     rbp, [rsp-17h]
0x180028236  sub     rsp, 0C8h
0x18002823d  mov     r14, r9
0x180028240  mov     rdi, r8
0x180028243  mov     rsi, rdx
0x180028246  mov     r13, rcx
0x180028249  xor     r8d, r8d
0x18002824c  lea     rdx, [rbp+4Fh+var_80]
0x180028250  mov     rcx, [rcx+8]
0x180028254  call    ?BeginTransaction@ADPDatabase@@QEAA?AVTransaction@@W4TransactionLockType@@@Z; ADPDatabase::BeginTransaction(TransactionLockType)
0x180028259  nop
0x18002825a  xor     r12d, r12d
0x18002825d  mov     [rbp+4Fh+arg_0], r12
0x180028261  mov     r15d, r12d
0x180028264  mov     rcx, [r13+8]
0x180028268  mov     [rsp+100h+var_D0], r12
0x18002826d  lea     rax, [rbp+4Fh+arg_0]
0x180028271  mov     [rsp+100h+var_D8], rax
0x180028276  mov     [rsp+100h+var_E0], r12
0x18002827b  mov     r9d, 80h
0x180028281  or      rbx, 0FFFFFFFFFFFFFFFFh
0x180028285  mov     r8d, ebx
0x180028288  lea     rdx, aSelectCountFro; "SELECT COUNT(*) FROM CustomEntities WHE"...
0x18002828f  mov     rcx, [rcx+20h]
0x180028293  call    sqlite3LockAndPrepare
0x180028298  cmp     qword ptr [rdi+18h], 0Fh
0x18002829d  jbe     short loc_1800282A4
0x18002829f  mov     r8, [rdi]
0x1800282a2  jmp     short loc_1800282A7
0x1800282a4  mov     r8, rdi
0x1800282a7  mov     byte ptr [rsp+100h+var_D8], 1
0x1800282ac  mov     [rsp+100h+var_E0], r12
0x1800282b1  mov     r9, rbx
0x1800282b4  mov     edx, 1
0x1800282b9  mov     rbx, [rbp+4Fh+arg_0]
0x1800282bd  mov     rcx, rbx
0x1800282c0  call    bindText
0x1800282c5  cmp     qword ptr [rsi+18h], 0Fh
0x1800282ca  jbe     short loc_1800282D1
0x1800282cc  mov     r8, [rsi]
0x1800282cf  jmp     short loc_1800282D4
0x1800282d1  mov     r8, rsi
0x1800282d4  mov     byte ptr [rsp+100h+var_D8], 1
0x1800282d9  mov     [rsp+100h+var_E0], r12
0x1800282de  or      r9, 0FFFFFFFFFFFFFFFFh
0x1800282e2  lea     edx, [r9+3]
0x1800282e6  mov     rcx, rbx
0x1800282e9  call    bindText
0x1800282ee  cmp     qword ptr [r14+18h], 0Fh
0x1800282f3  jbe     short loc_1800282FA
0x1800282f5  mov     r8, [r14]
0x1800282f8  jmp     short loc_1800282FD
0x1800282fa  mov     r8, r14
0x1800282fd  mov     byte ptr [rsp+100h+var_D8], 1
0x180028302  mov     [rsp+100h+var_E0], r12
0x180028307  or      r9, 0FFFFFFFFFFFFFFFFh
0x18002830b  lea     edx, [r9+4]
0x18002830f  mov     rcx, rbx
0x180028312  call    bindText
0x180028317  mov     rcx, rbx
0x18002831a  call    sqlite3_step
0x18002831f  cmp     eax, 64h ; 'd'
0x180028322  jnz     short loc_180028331
0x180028324  xor     edx, edx
0x180028326  mov     rcx, rbx
0x180028329  call    sqlite3_column_int
0x18002832e  mov     r15d, eax
0x180028331  test    rbx, rbx
0x180028334  jz      short loc_18002834D
0x180028336  mov     rcx, rbx
0x180028339  call    sqlite3_finalize
0x18002833e  test    eax, eax
0x180028340  jnz     loc_180028545
0x180028346  mov     rbx, r12
0x180028349  mov     [rbp+4Fh+arg_0], rbx
0x18002834d  cmp     r15d, 3E8h
0x180028354  jl      loc_18002840C
0x18002835a  test    rbx, rbx
0x18002835d  jnz     loc_180028578
0x180028363  mov     rcx, [r13+8]
0x180028367  mov     [rsp+100h+var_D0], r12
0x18002836c  lea     rax, [rbp+4Fh+arg_0]
0x180028370  mov     [rsp+100h+var_D8], rax
0x180028375  mov     [rsp+100h+var_E0], r12
0x18002837a  mov     r9d, 80h
0x180028380  or      rbx, 0FFFFFFFFFFFFFFFFh
0x180028384  mov     r8d, ebx
0x180028387  lea     rdx, aDeleteFromCust_0; "DELETE FROM CustomEntities WHERE rowid "...
0x18002838e  mov     rcx, [rcx+20h]
0x180028392  call    sqlite3LockAndPrepare
0x180028397  cmp     qword ptr [rdi+18h], 0Fh
0x18002839c  jbe     short loc_1800283A3
0x18002839e  mov     r8, [rdi]
0x1800283a1  jmp     short loc_1800283A6
0x1800283a3  mov     r8, rdi
0x1800283a6  mov     byte ptr [rsp+100h+var_D8], 1
0x1800283ab  mov     [rsp+100h+var_E0], r12
0x1800283b0  mov     r9, rbx
0x1800283b3  mov     edx, 1
0x1800283b8  mov     rbx, [rbp+4Fh+arg_0]
0x1800283bc  mov     rcx, rbx
0x1800283bf  call    bindText
0x1800283c4  lea     eax, [r15-3E7h]
0x1800283cb  movsxd  r8, eax
0x1800283ce  mov     edx, 2
0x1800283d3  mov     rcx, rbx
0x1800283d6  call    sqlite3_bind_int64
0x1800283db  mov     r15, [rbp+57h]
0x1800283df  mov     rcx, rbx
0x1800283e2  call    sqlite3_step
0x1800283e7  cmp     eax, 65h ; 'e'
0x1800283ea  jnz     loc_180028599
0x1800283f0  test    rbx, rbx
0x1800283f3  jz      short loc_180028415
0x1800283f5  mov     rcx, rbx
0x1800283f8  call    sqlite3_finalize
0x1800283fd  test    eax, eax
0x1800283ff  jnz     loc_1800285AE
0x180028405  mov     rbx, r12
0x180028408  mov     [rbp+4Fh+arg_0], rbx
0x18002840c  test    rbx, rbx
0x18002840f  jnz     loc_1800285E1
0x180028415  mov     rcx, [r13+8]
0x180028419  mov     [rsp+100h+var_D0], r12
0x18002841e  lea     rax, [rbp+4Fh+arg_0]
0x180028422  mov     [rsp+100h+var_D8], rax
0x180028427  mov     [rsp+100h+var_E0], r12
0x18002842c  mov     r9d, 80h
0x180028432  or      r15, 0FFFFFFFFFFFFFFFFh
0x180028436  mov     r8d, r15d
0x180028439  lea     rdx, aReplaceIntoCus; "REPLACE INTO CustomEntities (Trigger, P"...
0x180028440  mov     rcx, [rcx+20h]
0x180028444  call    sqlite3LockAndPrepare
0x180028449  cmp     qword ptr [r14+18h], 0Fh
0x18002844e  jbe     short loc_180028453
0x180028450  mov     r14, [r14]
0x180028453  mov     byte ptr [rsp+100h+var_D8], 1
0x180028458  mov     [rsp+100h+var_E0], r12
0x18002845d  mov     r9, r15
0x180028460  mov     r8, r14
0x180028463  mov     edx, 1
0x180028468  mov     rbx, [rbp+4Fh+arg_0]
0x18002846c  mov     rcx, rbx
0x18002846f  call    bindText
0x180028474  mov     r8, [rbp+4Fh+arg_20]
0x180028478  cmp     qword ptr [r8+18h], 0Fh
0x18002847d  jbe     short loc_180028482
0x18002847f  mov     r8, [r8]
0x180028482  mov     byte ptr [rsp+100h+var_D8], 1
0x180028487  mov     [rsp+100h+var_E0], r12
0x18002848c  mov     r9, r15
0x18002848f  mov     edx, 2
0x180028494  mov     rcx, rbx
0x180028497  call    bindText
0x18002849c  cmp     qword ptr [rsi+18h], 0Fh
0x1800284a1  jbe     short loc_1800284A6
0x1800284a3  mov     rsi, [rsi]
0x1800284a6  mov     byte ptr [rsp+100h+var_D8], 1
0x1800284ab  mov     [rsp+100h+var_E0], r12
0x1800284b0  mov     r9, r15
0x1800284b3  mov     r8, rsi
0x1800284b6  mov     edx, 3
0x1800284bb  mov     rcx, rbx
0x1800284be  call    bindText
0x1800284c3  cmp     qword ptr [rdi+18h], 0Fh
0x1800284c8  jbe     short loc_1800284CD
0x1800284ca  mov     rdi, [rdi]
0x1800284cd  mov     byte ptr [rsp+100h+var_D8], 1
0x1800284d2  mov     [rsp+100h+var_E0], r12
0x1800284d7  mov     r9, r15
0x1800284da  mov     r8, rdi
0x1800284dd  mov     edx, 4
0x1800284e2  mov     rcx, rbx
0x1800284e5  call    bindText
0x1800284ea  mov     rdi, [rbp+57h]
0x1800284ee  mov     rcx, rbx
0x1800284f1  call    sqlite3_step
0x1800284f6  cmp     eax, 65h ; 'e'
0x1800284f9  jnz     short loc_180028530
0x1800284fb  lea     rcx, [rbp+4Fh+var_80]; this
0x1800284ff  call    ?Commit@Transaction@@QEAAXXZ; Transaction::Commit(void)
0x180028504  nop
0x180028505  test    rbx, rbx
0x180028508  jz      short loc_180028513
0x18002850a  mov     rcx, rbx; struct sqlite3_stmt *
0x18002850d  call    ?release_or_terminate@unique_sqlite3_stmt@@CAXPEAUsqlite3_stmt@@@Z; unique_sqlite3_stmt::release_or_terminate(sqlite3_stmt *)
0x180028512  nop
0x180028513  lea     rcx, [rbp+4Fh+var_80]; this
0x180028517  call    ??1Transaction@@QEAA@XZ; Transaction::~Transaction(void)
0x18002851c  add     rsp, 0C8h
0x180028523  pop     r15
0x180028525  pop     r14
0x180028527  pop     r13
0x180028529  pop     r12
0x18002852b  pop     rdi
0x18002852c  pop     rsi
0x18002852d  pop     rbx
0x18002852e  pop     rbp
0x18002852f  retn
0x180028530  lea     r8, aOnecoreuapBase_8; "onecoreuap\\base\\appmodel\\aggregatedd"...
0x180028537  mov     edx, 5Fh ; '_'; void *
0x18002853c  mov     rcx, rdi; this
0x18002853f  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
0x180028545  mov     rcx, rbx
0x180028548  call    sqlite3_db_handle
0x18002854d  mov     rdx, rax; struct sqlite3 *
0x180028550  lea     rcx, [rbp+4Fh+var_C0]; this
0x180028554  call    ??0sqlite3_error@@QEAA@PEAUsqlite3@@@Z; sqlite3_error::sqlite3_error(sqlite3 *)
0x180028559  nop
0x18002855a  lea     rdx, [rbp+4Fh+var_C0]
0x18002855e  lea     rcx, [rbp+4Fh+pExceptionObject]
0x180028562  call    ??0sqlite3_error@@QEAA@$$QEAU0@@Z; sqlite3_error::sqlite3_error(sqlite3_error &&)
0x180028567  lea     rdx, _TI2?AUsqlite3_error@@; pThrowInfo
0x18002856e  lea     rcx, [rbp+4Fh+pExceptionObject]; pExceptionObject
0x180028572  call    _CxxThrowException_0
0x180028578  lea     rdx, aAlreadyAssigne; "Already assigned."
0x18002857f  lea     rcx, [rbp+4Fh+var_C0]; this
0x180028583  call    ??0length_error@std@@QEAA@PEBD@Z; std::length_error::length_error(char const *)
0x180028588  lea     rdx, _TI2?AVruntime_error@std@@; pThrowInfo
0x18002858f  lea     rcx, [rbp+4Fh+var_C0]; pExceptionObject
0x180028593  call    _CxxThrowException_0
0x180028599  lea     r8, aOnecoreuapBase_8; "onecoreuap\\base\\appmodel\\aggregatedd"...
0x1800285a0  mov     edx, 53h ; 'S'; void *
0x1800285a5  mov     rcx, r15; this
0x1800285a8  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
0x1800285ae  mov     rcx, rbx
0x1800285b1  call    sqlite3_db_handle
0x1800285b6  mov     rdx, rax; struct sqlite3 *
0x1800285b9  lea     rcx, [rbp+4Fh+pExceptionObject]; this
0x1800285bd  call    ??0sqlite3_error@@QEAA@PEAUsqlite3@@@Z; sqlite3_error::sqlite3_error(sqlite3 *)
0x1800285c2  nop
0x1800285c3  lea     rdx, [rbp+4Fh+pExceptionObject]
0x1800285c7  lea     rcx, [rbp+4Fh+var_C0]
0x1800285cb  call    ??0sqlite3_error@@QEAA@$$QEAU0@@Z; sqlite3_error::sqlite3_error(sqlite3_error &&)
0x1800285d0  lea     rdx, _TI2?AUsqlite3_error@@; pThrowInfo
0x1800285d7  lea     rcx, [rbp+4Fh+var_C0]; pExceptionObject
0x1800285db  call    _CxxThrowException_0
0x1800285e1  lea     rdx, aAlreadyAssigne; "Already assigned."
0x1800285e8  lea     rcx, [rbp+4Fh+var_C0]; this
0x1800285ec  call    ??0length_error@std@@QEAA@PEBD@Z; std::length_error::length_error(char const *)
0x1800285f1  lea     rdx, _TI2?AVruntime_error@std@@; pThrowInfo
0x1800285f8  lea     rcx, [rbp+4Fh+var_C0]; pExceptionObject
0x1800285fc  call    _CxxThrowException_0
```
