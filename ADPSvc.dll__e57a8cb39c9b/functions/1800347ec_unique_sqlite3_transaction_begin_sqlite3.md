# unique_sqlite3_transaction::begin(sqlite3 *)

- ea: `0x1800347ec`
- end: `0x1800348ba`
- name: `?begin@unique_sqlite3_transaction@@SA?AU1@PEAUsqlite3@@@Z`
- size: `206`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `3`
- callee_count: `5`
- tags: `installer_update, broker_com_uri`

## callers

- `0x180031978`
- `0x180031bdc`
- `0x1800338d0`

## callees

- `0x18002888c`
- `0x1800347ec`
- `0x180034d54`
- `0x180034e10`
- `0x180034e98`

## string_xrefs

- `0x18003488c`: `COMMIT TRANSACTION;`
- `0x18003486c`: `ROLLBACK TRANSACTION;`

## pseudocode

```c
__int64 __fastcall unique_sqlite3_transaction::begin(__int64 a1, __int64 a2)
{
  const char *v4; // rsi
  __int64 v5; // rbx
  const char *v7; // [rsp+30h] [rbp-10h] BYREF
  __int64 v8; // [rsp+38h] [rbp-8h]
  const char *v9; // [rsp+80h] [rbp+40h] BYREF
  struct sqlite3_stmt *v10; // [rsp+88h] [rbp+48h] BYREF

  v4 = "BEGIN TRANSACTION IMMEDIATE;";
  v5 = 28;
  while ( v5 )
  {
    v9 = 0;
    v7 = v4;
    v8 = v5;
    sqlite3_prepare_v2_cpp(&v10, a2, &v7, &v9);
    sqlite3_run_no_result_cpp(v10);
    if ( v9 )
    {
      v4 = v9;
      v5 = -1;
      do
        ++v5;
      while ( v9[v5] );
    }
    if ( v10 )
      unique_sqlite3_stmt::release_or_terminate(v10);
  }
  v7 = "ROLLBACK TRANSACTION;";
  v8 = 21;
  sqlite3_prepare_v2_entire_cpp(a1, a2, &v7);
  v7 = "COMMIT TRANSACTION;";
  v8 = 19;
  sqlite3_prepare_v2_entire_cpp(a1 + 8, a2, &v7);
  return a1;
}

```

## disassembly

```asm
0x1800347ec  mov     [rsp-28h+arg_0], rcx
0x1800347f1  push    rbp
0x1800347f2  push    rbx
0x1800347f3  push    rsi
0x1800347f4  push    rdi
0x1800347f5  push    r14
0x1800347f7  mov     rbp, rsp
0x1800347fa  sub     rsp, 40h
0x1800347fe  mov     r14, rdx
0x180034801  mov     rdi, rcx
0x180034804  lea     rsi, aBeginTransacti; "BEGIN TRANSACTION IMMEDIATE;"
0x18003480b  mov     ebx, 1Ch
0x180034810  lea     r8, [rbp+var_10]
0x180034814  mov     rdx, r14
0x180034817  test    rbx, rbx
0x18003481a  jz      short loc_18003486C
0x18003481c  mov     [rbp+arg_10], 0
0x180034824  mov     [rbp+var_10], rsi
0x180034828  mov     [rbp+var_8], rbx
0x18003482c  lea     r9, [rbp+arg_10]
0x180034830  lea     rcx, [rbp+arg_18]
0x180034834  call    ?sqlite3_prepare_v2_cpp@@YA?AUunique_sqlite3_stmt@@PEAUsqlite3@@V?$basic_string_view@DU?$char_traits@D@std@@@std@@PEAPEBD@Z; sqlite3_prepare_v2_cpp(sqlite3 *,std::string_view,char const * *)
0x180034839  nop
0x18003483a  mov     rcx, [rbp+arg_18]; struct sqlite3_stmt *
0x18003483e  call    ?sqlite3_run_no_result_cpp@@YAXPEAUsqlite3_stmt@@@Z; sqlite3_run_no_result_cpp(sqlite3_stmt *)
0x180034843  mov     rax, [rbp+arg_10]
0x180034847  test    rax, rax
0x18003484a  jz      short loc_18003485C
0x18003484c  mov     rsi, rax
0x18003484f  or      rbx, 0FFFFFFFFFFFFFFFFh
0x180034853  inc     rbx
0x180034856  cmp     byte ptr [rax+rbx], 0
0x18003485a  jnz     short loc_180034853
0x18003485c  mov     rcx, [rbp+arg_18]; struct sqlite3_stmt *
0x180034860  test    rcx, rcx
0x180034863  jz      short loc_180034810
0x180034865  call    ?release_or_terminate@unique_sqlite3_stmt@@CAXPEAUsqlite3_stmt@@@Z; unique_sqlite3_stmt::release_or_terminate(sqlite3_stmt *)
0x18003486a  jmp     short loc_180034810
0x18003486c  lea     rax, aRollbackTransa; "ROLLBACK TRANSACTION;"
0x180034873  mov     [rbp+var_10], rax
0x180034877  mov     [rbp+var_8], 15h
0x18003487f  mov     rcx, rdi
0x180034882  call    ?sqlite3_prepare_v2_entire_cpp@@YA?AUunique_sqlite3_stmt@@PEAUsqlite3@@V?$basic_string_view@DU?$char_traits@D@std@@@std@@@Z; sqlite3_prepare_v2_entire_cpp(sqlite3 *,std::string_view)
0x180034887  nop
0x180034888  lea     rcx, [rdi+8]
0x18003488c  lea     rax, aCommitTransact; "COMMIT TRANSACTION;"
0x180034893  mov     [rbp+var_10], rax
0x180034897  mov     [rbp+var_8], 13h
0x18003489f  lea     r8, [rbp+var_10]
0x1800348a3  mov     rdx, r14
0x1800348a6  call    ?sqlite3_prepare_v2_entire_cpp@@YA?AUunique_sqlite3_stmt@@PEAUsqlite3@@V?$basic_string_view@DU?$char_traits@D@std@@@std@@@Z; sqlite3_prepare_v2_entire_cpp(sqlite3 *,std::string_view)
0x1800348ab  nop
0x1800348ac  mov     rax, rdi
0x1800348af  add     rsp, 40h
0x1800348b3  pop     r14
0x1800348b5  pop     rdi
0x1800348b6  pop     rsi
0x1800348b7  pop     rbx
0x1800348b8  pop     rbp
0x1800348b9  retn
```
