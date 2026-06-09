# MapSqliteBusySnapshotToSqliteBusyIfRaceCondition(long,sqlite3 *)

- ea: `0x1800195ac`
- end: `0x18001960c`
- name: `?MapSqliteBusySnapshotToSqliteBusyIfRaceCondition@@YAJJPEAUsqlite3@@@Z`
- size: `96`
- prototype: `__int64 __fastcall(int, struct sqlite3 *)`
- caller_count: `3`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x18001a0e0`
- `0x18001abec`
- `0x18001c314`

## callees

- `0x1800195ac`

## import_xrefs

- `StateRepository.Core!sqlite3_get_autocommit` at `0x1800195c8`
- `StateRepository.Core!sqlite3_get_autocommit` at `0x1800195c8`
- `StateRepository.Core!sqlite3_next_stmt` at `0x1800195da`
- `StateRepository.Core!sqlite3_next_stmt` at `0x1800195da`
- `StateRepository.Core!sqlite3_stmt_busy` at `0x1800195eb`
- `StateRepository.Core!sqlite3_stmt_busy` at `0x1800195eb`

## pseudocode

```c
__int64 __fastcall MapSqliteBusySnapshotToSqliteBusyIfRaceCondition(unsigned int a1, struct sqlite3 *a2)
{
  __int64 v4; // rbx
  __int64 stmt; // rax

  if ( a1 != -2018573819 )
    return a1;
  if ( !(unsigned int)sqlite3_get_autocommit(a2) )
    return 2276393477LL;
  v4 = 0;
  while ( 1 )
  {
    stmt = sqlite3_next_stmt(a2, v4);
    v4 = stmt;
    if ( !stmt )
      break;
    if ( (unsigned int)sqlite3_stmt_busy(stmt) )
      return 2276393477LL;
  }
  return 2276392965LL;
}

```

## disassembly

```asm
0x1800195ac  mov     [rsp+arg_0], rbx
0x1800195b1  push    rdi
0x1800195b2  sub     rsp, 20h
0x1800195b6  mov     rdi, rdx
0x1800195b9  cmp     ecx, 87AF0205h
0x1800195bf  jz      short loc_1800195C5
0x1800195c1  mov     eax, ecx
0x1800195c3  jmp     short loc_1800195FA
0x1800195c5  mov     rcx, rdi
0x1800195c8  call    cs:__imp_sqlite3_get_autocommit
0x1800195ce  test    eax, eax
0x1800195d0  jz      short loc_1800195F5
0x1800195d2  xor     ebx, ebx
0x1800195d4  mov     rdx, rbx
0x1800195d7  mov     rcx, rdi
0x1800195da  call    cs:__imp_sqlite3_next_stmt
0x1800195e0  mov     rbx, rax
0x1800195e3  test    rax, rax
0x1800195e6  jz      short loc_180019605
0x1800195e8  mov     rcx, rax
0x1800195eb  call    cs:__imp_sqlite3_stmt_busy
0x1800195f1  test    eax, eax
0x1800195f3  jz      short loc_1800195D4
0x1800195f5  mov     eax, 87AF0205h
0x1800195fa  mov     rbx, [rsp+28h+arg_0]
0x1800195ff  add     rsp, 20h
0x180019603  pop     rdi
0x180019604  retn
0x180019605  mov     eax, 87AF0005h
0x18001960a  jmp     short loc_1800195FA
```
