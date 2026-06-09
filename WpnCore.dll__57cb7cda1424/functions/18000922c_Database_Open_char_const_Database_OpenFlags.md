# Database::Open(char const *,Database::OpenFlags)

- ea: `0x18000922c`
- end: `0x180009414`
- name: `?Open@Database@@QEAAXPEBDW4OpenFlags@1@@Z`
- size: `488`
- prototype: `void __fastcall(Database *, __int64, unsigned int)`
- caller_count: `1`
- callee_count: `11`
- tags: ``

## callers

- `0x18004f21c`

## callees

- `0x1800090e4`
- `0x18000922c`
- `0x18000941c`
- `0x1800098a8`
- `0x18000e5f4`
- `0x1800831f8`
- `0x18008758c`
- `0x18009d390`
- `0x1800a277c`
- `0x1800a4130`
- `0x1800f55f0`

## import_xrefs

- `winsqlite3!sqlite3_file_control` at `0x1800092b7`
- `winsqlite3!sqlite3_file_control` at `0x1800092b7`
- `winsqlite3!sqlite3_extended_result_codes` at `0x180009309`
- `winsqlite3!sqlite3_extended_result_codes` at `0x180009309`
- `winsqlite3!sqlite3_extended_errcode` at `0x180009273`
- `winsqlite3!sqlite3_extended_errcode` at `0x180009273`
- `winsqlite3!sqlite3_open_v2` at `0x180009256`
- `winsqlite3!sqlite3_open_v2` at `0x180009256`
- `winsqlite3!sqlite3_errmsg` at `0x18000928b`
- `winsqlite3!sqlite3_errmsg` at `0x18000928b`
- `winsqlite3!sqlite3_log` at `0x1800092db`
- `winsqlite3!sqlite3_log` at `0x1800092db`

## string_xrefs

- `0x18000936f`: `temp_store`
- `0x1800092c5`: `[sqlite3_open: lastErrNo:0x%X filecontrolrc:%d] Database %p: %s`

## pseudocode

```c
// Hidden C++ exception states: #wind=4 #try_helpers=1
void __fastcall Database::Open(Database *a1, __int64 a2, unsigned int a3)
{
  unsigned int v6; // eax
  int v7; // eax
  bool v8; // sf
  __int64 v9; // rcx
  int v10; // eax
  unsigned int v11; // ebx
  __int64 v12; // rax
  __int64 v13; // rcx
  int v14; // r8d
  const char *v15; // rdi
  int v16; // eax
  signed int v17; // eax
  __int64 v18; // rdx
  bool v19; // sf
  unsigned int v20; // ebx
  int v21; // eax
  __int64 v22; // r8
  const char *v23; // rdx
  unsigned int v24; // eax
  int v25; // eax
  __int64 v26; // rdx
  int v27; // edi
  int v28; // [rsp+20h] [rbp-38h]
  int v29; // [rsp+20h] [rbp-38h]
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+0h]
  int v31; // [rsp+60h] [rbp+8h] BYREF

  Database::Close(a1);
  v6 = Database::OpenFlagsToOpenFlags(a3);
  v7 = sqlite3_open_v2(a2, a1, v6, 0);
  v8 = v7 < 0;
  if ( v7 > 0 )
    v8 = 1;
  v9 = *(_QWORD *)a1;
  if ( v8 )
  {
    v10 = sqlite3_extended_errcode(v9);
    v11 = v10;
    if ( v10 > 0 )
      v11 = (unsigned __int16)v10 | 0x87AF0000;
    v12 = sqlite3_errmsg(*(_QWORD *)a1);
    v13 = *(_QWORD *)a1;
    v14 = -2147024882;
    v31 = -2147024882;
    v15 = (const char *)v12;
    v16 = 7;
    if ( v13 )
    {
      v16 = sqlite3_file_control(v13, 0, 4, &v31);
      v14 = v31;
    }
    sqlite3_log(
      v11,
      "[sqlite3_open: lastErrNo:0x%X filecontrolrc:%d] Database %p: %s",
      v14,
      v16,
      *(const void **)a1,
      v15);
    *(_QWORD *)a1 = 0;
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x8A,
      (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\platform\\sqlitewrapper\\database.cpp",
      (const char *)v11,
      v29);
  }
  v17 = sqlite3_extended_result_codes(v9, 1);
  v19 = v17 < 0;
  if ( v17 > 0 )
  {
    v17 = (unsigned __int16)v17 | 0x87AF0000;
    v19 = v17 < 0;
  }
  if ( v19 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x8F,
      (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\platform\\sqlitewrapper\\database.cpp",
      (const char *)(unsigned int)v17,
      v28);
  v20 = 2;
  v21 = a3 & 0x700000;
  if ( (a3 & 0x700000) != 0x100000 )
  {
    if ( !v21 || (v22 = 1, v21 != 0x200000) )
      v22 = 2;
    Database::SetWalFilesPersistence(a1, v18, v22);
  }
  Database::SetPragma(a1, "temp_store", "MEMORY");
  if ( (a3 & 0x70) != 0x10 )
  {
    v24 = Database::OpenFlagsToJournalMode(a3);
    Database::SetJournalMode(a1, v24);
  }
  v25 = a3 & 0x300;
  if ( v25 != 256 )
  {
    if ( (a3 & 0x300) == 0 || v25 == 512 )
      v26 = 1;
    else
      v26 = (unsigned int)(v25 == 768) + 1;
    Database::SetLockingMode(a1, v26);
  }
  v27 = a3 & 0x7000;
  if ( v27 != 4096 )
  {
    if ( v27 )
    {
      if ( v27 == 0x2000 )
      {
        v20 = 1;
      }
      else if ( v27 != 12288 )
      {
        v20 = 3 - (v27 != 0x4000);
      }
    }
    Database::SetSynchronous(a1, v20);
  }
  Database::SetPragma(a1, v23, 1);
}

```

## disassembly

```asm
0x18000922c  push    rbx
0x18000922e  push    rbp
0x18000922f  push    rsi
0x180009230  push    rdi
0x180009231  sub     rsp, 38h
0x180009235  mov     edi, r8d
0x180009238  mov     rbx, rdx
0x18000923b  mov     rsi, rcx
0x18000923e  call    ?Close@Database@@QEAAXXZ; Database::Close(void)
0x180009243  mov     ecx, edi
0x180009245  call    ?OpenFlagsToOpenFlags@Database@@CAHW4OpenFlags@1@@Z; Database::OpenFlagsToOpenFlags(Database::OpenFlags)
0x18000924a  mov     r8d, eax
0x18000924d  mov     rdx, rsi
0x180009250  mov     rcx, rbx
0x180009253  xor     r9d, r9d
0x180009256  call    cs:__imp_sqlite3_open_v2
0x18000925c  test    eax, eax
0x18000925e  jle     short loc_18000926A
0x180009260  movzx   eax, ax
0x180009263  or      eax, 87AF0000h
0x180009268  test    eax, eax
0x18000926a  mov     rcx, [rsi]
0x18000926d  jns     loc_180009302
0x180009273  call    cs:__imp_sqlite3_extended_errcode
0x180009279  mov     ebx, eax
0x18000927b  test    eax, eax
0x18000927d  jle     short loc_180009288
0x18000927f  movzx   ebx, ax
0x180009282  or      ebx, 87AF0000h
0x180009288  mov     rcx, [rsi]
0x18000928b  call    cs:__imp_sqlite3_errmsg
0x180009291  mov     rcx, [rsi]
0x180009294  mov     r8d, 8007000Eh
0x18000929a  mov     [rsp+58h+arg_0], r8d
0x18000929f  mov     rdi, rax
0x1800092a2  mov     eax, 7
0x1800092a7  test    rcx, rcx
0x1800092aa  jz      short loc_1800092C2
0x1800092ac  lea     r9, [rsp+58h+arg_0]
0x1800092b1  xor     edx, edx
0x1800092b3  lea     r8d, [rax-3]
0x1800092b7  call    cs:__imp_sqlite3_file_control
0x1800092bd  mov     r8d, [rsp+58h+arg_0]
0x1800092c2  mov     rcx, [rsi]
0x1800092c5  lea     rdx, aSqlite3OpenLas; "[sqlite3_open: lastErrNo:0x%X filecontr"...
0x1800092cc  mov     [rsp+58h+var_30], rdi
0x1800092d1  mov     r9d, eax
0x1800092d4  mov     qword ptr [rsp+58h+var_38], rcx; int
0x1800092d9  mov     ecx, ebx
0x1800092db  call    cs:__imp_sqlite3_log
0x1800092e1  mov     rcx, [rsp+58h]; this
0x1800092e6  lea     r8, aOnecoreuapBase_1; "onecoreuap\\base\\diagnosis\\platform\\"...
0x1800092ed  mov     r9d, ebx; char *
0x1800092f0  mov     qword ptr [rsi], 0
0x1800092f7  mov     edx, 8Ah; void *
0x1800092fc  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180009302  mov     ebp, 1
0x180009307  mov     edx, ebp
0x180009309  call    cs:__imp_sqlite3_extended_result_codes
0x18000930f  test    eax, eax
0x180009311  jle     short loc_18000931D
0x180009313  movzx   eax, ax
0x180009316  or      eax, 87AF0000h
0x18000931b  test    eax, eax
0x18000931d  jns     short loc_180009339
0x18000931f  mov     rcx, [rsp+58h]; this
0x180009324  lea     r8, aOnecoreuapBase_1; "onecoreuap\\base\\diagnosis\\platform\\"...
0x18000932b  mov     r9d, eax; char *
0x18000932e  mov     edx, 8Fh; void *
0x180009333  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180009339  mov     eax, edi
0x18000933b  mov     ebx, 2
0x180009340  and     eax, 700000h
0x180009345  cmp     eax, 100000h
0x18000934a  jz      short loc_180009365
0x18000934c  test    eax, eax
0x18000934e  jz      short loc_18000935A
0x180009350  mov     r8d, ebp
0x180009353  cmp     eax, 200000h
0x180009358  jz      short loc_18000935D
0x18000935a  mov     r8d, ebx
0x18000935d  mov     rcx, rsi
0x180009360  call    ?SetWalFilesPersistence@Database@@QEAAXPEBDW4WalFilesPersistence@1@@Z; Database::SetWalFilesPersistence(char const *,Database::WalFilesPersistence)
0x180009365  lea     r8, aMemory; "MEMORY"
0x18000936c  mov     rcx, rsi; this
0x18000936f  lea     rdx, aTempStore; "temp_store"
0x180009376  call    ?SetPragma@Database@@QEAAXPEBD0@Z; Database::SetPragma(char const *,char const *)
0x18000937b  mov     eax, edi
0x18000937d  and     al, 70h
0x18000937f  cmp     al, 10h
0x180009381  jz      short loc_180009394
0x180009383  mov     ecx, edi
0x180009385  call    ?OpenFlagsToJournalMode@Database@@CA?AW4JournalMode@1@W4OpenFlags@1@@Z; Database::OpenFlagsToJournalMode(Database::OpenFlags)
0x18000938a  mov     edx, eax
0x18000938c  mov     rcx, rsi
0x18000938f  call    ?SetJournalMode@Database@@QEAAXW4JournalMode@1@@Z; Database::SetJournalMode(Database::JournalMode)
0x180009394  mov     eax, edi
0x180009396  mov     ecx, 300h
0x18000939b  and     eax, ecx
0x18000939d  cmp     eax, 100h
0x1800093a2  jz      short loc_1800093C4
0x1800093a4  test    eax, eax
0x1800093a6  jz      short loc_1800093BA
0x1800093a8  cmp     eax, 200h
0x1800093ad  jz      short loc_1800093BA
0x1800093af  xor     edx, edx
0x1800093b1  cmp     eax, ecx
0x1800093b3  setz    dl
0x1800093b6  add     edx, ebp
0x1800093b8  jmp     short loc_1800093BC
0x1800093ba  mov     edx, ebp
0x1800093bc  mov     rcx, rsi
0x1800093bf  call    ?SetLockingMode@Database@@QEAAXW4LockingMode@1@@Z; Database::SetLockingMode(Database::LockingMode)
0x1800093c4  and     edi, 7000h
0x1800093ca  cmp     edi, 1000h
0x1800093d0  jz      short loc_180009401
0x1800093d2  test    edi, edi
0x1800093d4  jz      short loc_1800093F7
0x1800093d6  cmp     edi, 2000h
0x1800093dc  jz      short loc_1800093F5
0x1800093de  cmp     edi, 3000h
0x1800093e4  jz      short loc_1800093F7
0x1800093e6  sub     edi, 4000h
0x1800093ec  neg     edi
0x1800093ee  sbb     ebx, ebx
0x1800093f0  add     ebx, 3
0x1800093f3  jmp     short loc_1800093F7
0x1800093f5  mov     ebx, ebp
0x1800093f7  mov     edx, ebx
0x1800093f9  mov     rcx, rsi
0x1800093fc  call    ?SetSynchronous@Database@@QEAAXW4Synchronous@1@@Z; Database::SetSynchronous(Database::Synchronous)
0x180009401  mov     r8b, bpl; bool
0x180009404  mov     rcx, rsi; this
0x180009407  add     rsp, 38h
0x18000940b  pop     rdi
0x18000940c  pop     rsi
0x18000940d  pop     rbp
0x18000940e  pop     rbx
0x18000940f  jmp     ?SetPragma@Database@@QEAAXPEBD_N@Z; Database::SetPragma(char const *,bool)
```
