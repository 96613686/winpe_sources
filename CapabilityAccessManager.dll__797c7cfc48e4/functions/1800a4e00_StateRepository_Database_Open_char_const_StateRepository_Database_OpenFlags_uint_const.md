# StateRepository::Database::Open(char const *,StateRepository::Database::OpenFlags,uint const *)

- ea: `0x1800a4e00`
- end: `0x1800a512b`
- name: `?Open@Database@StateRepository@@QEAAJPEBDW4OpenFlags@12@PEBI@Z`
- size: `811`
- prototype: ``
- caller_count: `2`
- callee_count: `18`
- tags: ``

## callers

- `0x1800a1930`
- `0x1800a5134`

## callees

- `0x18001ab9c`
- `0x1800210d4`
- `0x1800a1610`
- `0x1800a3b74`
- `0x1800a3e50`
- `0x1800a3ea8`
- `0x1800a4e00`
- `0x1800a5294`
- `0x1800a5320`
- `0x1800a5380`
- `0x1800a543c`
- `0x1800a54b8`
- `0x1800a55f0`
- `0x1800a5e94`
- `0x1800a5f44`
- `0x1800a5ff4`
- `0x1800a610c`
- `0x1800a61bc`

## import_xrefs

- `winsqlite3!sqlite3_extended_result_codes` at `0x1800a4fb5`
- `winsqlite3!sqlite3_extended_result_codes` at `0x1800a4fb5`
- `winsqlite3!sqlite3_file_control` at `0x1800a4ec0`
- `winsqlite3!sqlite3_file_control` at `0x1800a4ec0`
- `winsqlite3!sqlite3_extended_errcode` at `0x1800a4e7c`
- `winsqlite3!sqlite3_extended_errcode` at `0x1800a4e7c`
- `winsqlite3!sqlite3_open_v2` at `0x1800a4e5b`
- `winsqlite3!sqlite3_open_v2` at `0x1800a4e5b`
- `winsqlite3!sqlite3_close` at `0x1800a4f4b`
- `winsqlite3!sqlite3_close` at `0x1800a4f4b`
- `winsqlite3!sqlite3_errmsg` at `0x1800a4e91`
- `winsqlite3!sqlite3_errmsg` at `0x1800a4e91`
- `winsqlite3!sqlite3_log` at `0x1800a4ef6`
- `winsqlite3!sqlite3_log` at `0x1800a4ef6`

## string_xrefs

- `0x1800a4edf`: `[sqlite3_open: lastErrNo:0x%X filecontrolrc:%d] #%u : %s`
- `0x1800a4e32`: `onecore\base\appmodel\staterepository\dataaccesslayer\database.cpp`
- `0x1800a4f0e`: `onecore\base\appmodel\staterepository\dataaccesslayer\database.cpp`
- `0x1800a4f67`: `onecore\base\appmodel\staterepository\dataaccesslayer\database.cpp`
- `0x1800a5104`: `onecore\base\appmodel\staterepository\dataaccesslayer\database.cpp`
- `0x1800a5063`: `temp_store`
- `0x1800a4f37`: `[sqlite3_open: lastErrNo:0x%X filecontrolrc:%d] #%u : %hs`

## pseudocode

```c
__int64 StateRepository::Database::Open(StateRepository::Database *a1, __int64 a2, unsigned int a3, ...)
{
  signed int v6; // esi
  __int64 v7; // rdx
  unsigned int v9; // eax
  int v10; // eax
  bool v11; // sf
  int v12; // eax
  unsigned int v13; // edi
  __int64 v14; // rax
  __int64 v15; // rcx
  int v16; // ebp
  const char *v17; // r14
  signed int v18; // eax
  bool v19; // sf
  signed __int64 v20; // rax
  __int64 v21; // rcx
  int v22; // eax
  bool v23; // dl
  unsigned int v24; // eax
  __int64 v25; // rdx
  unsigned int v26; // eax
  unsigned int v27; // eax
  unsigned int v28; // eax
  int v29; // eax
  unsigned int v30; // ebx
  int v31; // [rsp+20h] [rbp-68h]
  int v32; // [rsp+20h] [rbp-68h]
  char *v33; // [rsp+28h] [rbp-60h]
  wil::details::in1diag3 *retaddr; // [rsp+88h] [rbp+0h]
  char *v35; // [rsp+A8h] [rbp+20h] BYREF
  va_list va; // [rsp+A8h] [rbp+20h]
  va_list va1; // [rsp+B0h] [rbp+28h] BYREF

  va_start(va1, a3);
  va_start(va, a3);
  v35 = va_arg(va1, char *);
  v6 = StateRepository::Database::Close(a1);
  if ( v6 < 0 )
  {
    v7 = 164;
LABEL_3:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v7,
      (unsigned int)"onecore\\base\\appmodel\\staterepository\\dataaccesslayer\\database.cpp",
      (const char *)(unsigned int)v6,
      v31);
    return (unsigned int)v6;
  }
  v9 = StateRepository::Database::OpenFlagsToOpenFlags(a3);
  v10 = sqlite3_open_v2(a2, a1, v9, 0);
  v11 = v10 < 0;
  if ( v10 > 0 )
    v11 = 1;
  if ( v11 )
  {
    v12 = sqlite3_extended_errcode(*(_QWORD *)a1);
    v13 = v12;
    if ( v12 > 0 )
      v13 = (unsigned __int16)v12 | 0x87AF0000;
    v14 = sqlite3_errmsg(*(_QWORD *)a1);
    v15 = *(_QWORD *)a1;
    v16 = 7;
    LODWORD(v35) = -2147024882;
    v17 = (const char *)v14;
    if ( v15 )
      v16 = sqlite3_file_control(v15, 0, 4, (char **)va);
    sqlite3_log(
      v13,
      "[sqlite3_open: lastErrNo:0x%X filecontrolrc:%d] #%u : %s",
      (_DWORD)v35,
      v16,
      _InterlockedIncrement(&dword_180169080),
      v17);
    _InterlockedIncrement(&dword_180169080);
    LODWORD(v33) = (_DWORD)v35;
    wil::details::in1diag3::Log_HrMsg(
      retaddr,
      (void *)0xBE,
      (unsigned int)"onecore\\base\\appmodel\\staterepository\\dataaccesslayer\\database.cpp",
      (const char *)v13,
      (int)"[sqlite3_open: lastErrNo:0x%X filecontrolrc:%d] #%u : %hs",
      v33);
    v18 = sqlite3_close(*(_QWORD *)a1);
    v19 = v18 < 0;
    if ( v18 > 0 )
    {
      v18 = (unsigned __int16)v18 | 0x87AF0000;
      v19 = v18 < 0;
    }
    if ( v19 )
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0xBF,
        (unsigned int)"onecore\\base\\appmodel\\staterepository\\dataaccesslayer\\database.cpp",
        (const char *)(unsigned int)v18,
        v32);
    *(_QWORD *)a1 = 0;
    return v13;
  }
  else
  {
    v20 = _InterlockedIncrement64(&qword_180168E88);
    if ( !v20 )
      v20 = _InterlockedIncrement64(&qword_180168E88);
    v21 = *(_QWORD *)a1;
    *((_QWORD *)a1 + 15) = v20;
    v22 = sqlite3_extended_result_codes(v21, 1);
    v6 = v22;
    if ( v22 > 0 )
      v6 = (unsigned __int16)v22 | 0x87AF0000;
    if ( v6 < 0 )
    {
      v7 = 201;
      goto LABEL_3;
    }
    if ( (a3 & 0x20000) != 0 )
    {
      v6 = StateRepository::Database::EnableTrace(a1, v23);
      if ( v6 < 0 )
      {
        v7 = 205;
        goto LABEL_3;
      }
    }
    if ( (a3 & 0x80000) != 0 )
    {
      v6 = StateRepository::Database::EnableProfile(a1, v23);
      if ( v6 < 0 )
      {
        v7 = 210;
        goto LABEL_3;
      }
    }
    v6 = StateRepository::Database::RegisterFunctions(a1);
    if ( v6 < 0 )
    {
      v7 = 213;
      goto LABEL_3;
    }
    if ( (a3 & 0x700000) != 0x100000 )
    {
      v24 = StateRepository::Database::OpenFlagsToWalFilesPersistence(a3);
      v6 = StateRepository::Database::SetWalFilesPersistence(a1, v25, v24);
      if ( v6 < 0 )
      {
        v7 = 221;
        goto LABEL_3;
      }
    }
    v6 = StateRepository::Database::SetPragma(a1, "temp_store", "MEMORY");
    if ( v6 < 0 )
    {
      v7 = 224;
      goto LABEL_3;
    }
    if ( (a3 & 0x70) != 0x10 )
    {
      v26 = StateRepository::Database::OpenFlagsToJournalMode(a3);
      v6 = StateRepository::Database::SetJournalMode(a1, v26);
      if ( v6 < 0 )
      {
        v7 = 229;
        goto LABEL_3;
      }
    }
    if ( (a3 & 0x300) != 0x100 )
    {
      v27 = StateRepository::Database::OpenFlagsToLockingMode(a3);
      v6 = StateRepository::Database::SetLockingMode(a1, v27);
      if ( v6 < 0 )
      {
        v7 = 235;
        goto LABEL_3;
      }
    }
    if ( (a3 & 0x7000) == 0x1000 )
      return 0;
    v28 = StateRepository::Database::OpenFlagsToSynchronous(a3);
    v29 = StateRepository::Database::SetSynchronous(a1, v28);
    v30 = v29;
    if ( v29 >= 0 )
    {
      return 0;
    }
    else
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xF1,
        (unsigned int)"onecore\\base\\appmodel\\staterepository\\dataaccesslayer\\database.cpp",
        (const char *)(unsigned int)v29,
        v31);
      return v30;
    }
  }
}

```

## disassembly

```asm
0x1800a4e00  mov     [rsp+arg_18], r9
0x1800a4e05  push    rbx
0x1800a4e06  push    rbp
0x1800a4e07  push    rsi
0x1800a4e08  push    rdi
0x1800a4e09  push    r14
0x1800a4e0b  push    r15
0x1800a4e0d  sub     rsp, 58h
0x1800a4e11  mov     edi, r8d
0x1800a4e14  mov     rbp, rdx
0x1800a4e17  mov     rbx, rcx
0x1800a4e1a  call    ?Close@Database@StateRepository@@QEAAJXZ; StateRepository::Database::Close(void)
0x1800a4e1f  mov     esi, eax
0x1800a4e21  test    eax, eax
0x1800a4e23  jns     short loc_1800A4E48
0x1800a4e25  mov     edx, 0A4h; void *
0x1800a4e2a  mov     rcx, [rsp+88h]; this
0x1800a4e32  lea     r8, aOnecoreBaseApp_18; "onecore\\base\\appmodel\\staterepositor"...
0x1800a4e39  mov     r9d, esi; char *
0x1800a4e3c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800a4e41  mov     eax, esi
0x1800a4e43  jmp     loc_1800A511E
0x1800a4e48  mov     ecx, edi
0x1800a4e4a  call    ?OpenFlagsToOpenFlags@Database@StateRepository@@CAHW4OpenFlags@12@@Z; StateRepository::Database::OpenFlagsToOpenFlags(StateRepository::Database::OpenFlags)
0x1800a4e4f  mov     r8d, eax
0x1800a4e52  xor     r9d, r9d
0x1800a4e55  mov     rdx, rbx
0x1800a4e58  mov     rcx, rbp
0x1800a4e5b  call    cs:__imp_sqlite3_open_v2
0x1800a4e61  mov     r15d, 87AF0000h
0x1800a4e67  test    eax, eax
0x1800a4e69  jle     short loc_1800A4E73
0x1800a4e6b  movzx   eax, ax
0x1800a4e6e  or      eax, r15d
0x1800a4e71  test    eax, eax
0x1800a4e73  jns     loc_1800A4F89
0x1800a4e79  mov     rcx, [rbx]
0x1800a4e7c  call    cs:__imp_sqlite3_extended_errcode
0x1800a4e82  mov     edi, eax
0x1800a4e84  test    eax, eax
0x1800a4e86  jle     short loc_1800A4E8E
0x1800a4e88  movzx   edi, ax
0x1800a4e8b  or      edi, r15d
0x1800a4e8e  mov     rcx, [rbx]
0x1800a4e91  call    cs:__imp_sqlite3_errmsg
0x1800a4e97  mov     rcx, [rbx]
0x1800a4e9a  mov     ebp, 7
0x1800a4e9f  mov     dword ptr [rsp+88h+arg_18], 8007000Eh
0x1800a4eaa  mov     r14, rax
0x1800a4ead  test    rcx, rcx
0x1800a4eb0  jz      short loc_1800A4EC8
0x1800a4eb2  lea     r9, [rsp+88h+arg_18]
0x1800a4eba  xor     edx, edx
0x1800a4ebc  lea     r8d, [rbp-3]
0x1800a4ec0  call    cs:__imp_sqlite3_file_control
0x1800a4ec6  mov     ebp, eax
0x1800a4ec8  mov     esi, 1
0x1800a4ecd  mov     ecx, esi
0x1800a4ecf  lock xadd cs:dword_180169080, ecx
0x1800a4ed7  mov     r8d, dword ptr [rsp+88h+arg_18]
0x1800a4edf  lea     rdx, aSqlite3OpenLas_0; "[sqlite3_open: lastErrNo:0x%X filecontr"...
0x1800a4ee6  add     ecx, esi
0x1800a4ee8  mov     [rsp+88h+var_60], r14
0x1800a4eed  mov     [rsp+88h+var_68], ecx
0x1800a4ef1  mov     r9d, ebp
0x1800a4ef4  mov     ecx, edi
0x1800a4ef6  call    cs:__imp_sqlite3_log
0x1800a4efc  mov     eax, esi
0x1800a4efe  lock xadd cs:dword_180169080, eax
0x1800a4f06  mov     rcx, [rsp+88h]; this
0x1800a4f0e  lea     r8, aOnecoreBaseApp_18; "onecore\\base\\appmodel\\staterepositor"...
0x1800a4f15  add     eax, esi
0x1800a4f17  mov     [rsp+88h+var_48], r14
0x1800a4f1c  mov     [rsp+88h+var_50], eax
0x1800a4f20  mov     r9d, edi; char *
0x1800a4f23  mov     eax, dword ptr [rsp+88h+arg_18]
0x1800a4f2a  mov     edx, 0BEh; void *
0x1800a4f2f  mov     [rsp+88h+var_58], ebp
0x1800a4f33  mov     dword ptr [rsp+88h+var_60], eax; char *
0x1800a4f37  lea     rax, aSqlite3OpenLas; "[sqlite3_open: lastErrNo:0x%X filecontr"...
0x1800a4f3e  mov     qword ptr [rsp+88h+var_68], rax; int
0x1800a4f43  call    ?Log_HrMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Log_HrMsg(void *,uint,char const *,long,char const *,...)
0x1800a4f48  mov     rcx, [rbx]
0x1800a4f4b  call    cs:__imp_sqlite3_close
0x1800a4f51  test    eax, eax
0x1800a4f53  jle     short loc_1800A4F5D
0x1800a4f55  movzx   eax, ax
0x1800a4f58  or      eax, r15d
0x1800a4f5b  test    eax, eax
0x1800a4f5d  jns     short loc_1800A4F7B
0x1800a4f5f  mov     rcx, [rsp+88h]; this
0x1800a4f67  lea     r8, aOnecoreBaseApp_18; "onecore\\base\\appmodel\\staterepositor"...
0x1800a4f6e  mov     r9d, eax; char *
0x1800a4f71  mov     edx, 0BFh; void *
0x1800a4f76  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1800a4f7b  mov     qword ptr [rbx], 0
0x1800a4f82  mov     eax, edi
0x1800a4f84  jmp     loc_1800A511E
0x1800a4f89  mov     esi, 1
0x1800a4f8e  mov     eax, esi
0x1800a4f90  lock xadd cs:qword_180168E88, rax
0x1800a4f99  add     rax, rsi
0x1800a4f9c  jnz     short loc_1800A4FAC
0x1800a4f9e  mov     eax, esi
0x1800a4fa0  lock xadd cs:qword_180168E88, rax
0x1800a4fa9  add     rax, rsi
0x1800a4fac  mov     rcx, [rbx]
0x1800a4faf  mov     edx, esi
0x1800a4fb1  mov     [rbx+78h], rax
0x1800a4fb5  call    cs:__imp_sqlite3_extended_result_codes
0x1800a4fbb  mov     esi, eax
0x1800a4fbd  test    eax, eax
0x1800a4fbf  jle     short loc_1800A4FC7
0x1800a4fc1  movzx   esi, ax
0x1800a4fc4  or      esi, r15d
0x1800a4fc7  test    esi, esi
0x1800a4fc9  jns     short loc_1800A4FD5
0x1800a4fcb  mov     edx, 0C9h
0x1800a4fd0  jmp     loc_1800A4E2A
0x1800a4fd5  bt      edi, 11h
0x1800a4fd9  jnb     short loc_1800A4FF3
0x1800a4fdb  mov     rcx, rbx; this
0x1800a4fde  call    ?EnableTrace@Database@StateRepository@@QEAAJ_N@Z; StateRepository::Database::EnableTrace(bool)
0x1800a4fe3  mov     esi, eax
0x1800a4fe5  test    eax, eax
0x1800a4fe7  jns     short loc_1800A4FF3
0x1800a4fe9  mov     edx, 0CDh
0x1800a4fee  jmp     loc_1800A4E2A
0x1800a4ff3  bt      edi, 13h
0x1800a4ff7  jnb     short loc_1800A5011
0x1800a4ff9  mov     rcx, rbx; this
0x1800a4ffc  call    ?EnableProfile@Database@StateRepository@@QEAAJ_N@Z; StateRepository::Database::EnableProfile(bool)
0x1800a5001  mov     esi, eax
0x1800a5003  test    eax, eax
0x1800a5005  jns     short loc_1800A5011
0x1800a5007  mov     edx, 0D2h
0x1800a500c  jmp     loc_1800A4E2A
0x1800a5011  mov     rcx, rbx; this
0x1800a5014  call    ?RegisterFunctions@Database@StateRepository@@QEAAJXZ; StateRepository::Database::RegisterFunctions(void)
0x1800a5019  mov     esi, eax
0x1800a501b  test    eax, eax
0x1800a501d  jns     short loc_1800A5029
0x1800a501f  mov     edx, 0D5h
0x1800a5024  jmp     loc_1800A4E2A
0x1800a5029  mov     eax, edi
0x1800a502b  and     eax, 700000h
0x1800a5030  cmp     eax, 100000h
0x1800a5035  jz      short loc_1800A5059
0x1800a5037  mov     ecx, edi
0x1800a5039  call    ?OpenFlagsToWalFilesPersistence@Database@StateRepository@@CA?AW4WalFilesPersistence@12@W4OpenFlags@12@@Z; StateRepository::Database::OpenFlagsToWalFilesPersistence(StateRepository::Database::OpenFlags)
0x1800a503e  mov     r8d, eax
0x1800a5041  mov     rcx, rbx
0x1800a5044  call    ?SetWalFilesPersistence@Database@StateRepository@@QEAAJPEBDW4WalFilesPersistence@12@@Z; StateRepository::Database::SetWalFilesPersistence(char const *,StateRepository::Database::WalFilesPersistence)
0x1800a5049  mov     esi, eax
0x1800a504b  test    eax, eax
0x1800a504d  jns     short loc_1800A5059
0x1800a504f  mov     edx, 0DDh
0x1800a5054  jmp     loc_1800A4E2A
0x1800a5059  lea     r8, aMemory; "MEMORY"
0x1800a5060  mov     rcx, rbx; this
0x1800a5063  lea     rdx, aTempStore; "temp_store"
0x1800a506a  call    ?SetPragma@Database@StateRepository@@QEAAJPEBD0@Z; StateRepository::Database::SetPragma(char const *,char const *)
0x1800a506f  mov     esi, eax
0x1800a5071  test    eax, eax
0x1800a5073  jns     short loc_1800A507F
0x1800a5075  mov     edx, 0E0h
0x1800a507a  jmp     loc_1800A4E2A
0x1800a507f  mov     eax, edi
0x1800a5081  and     al, 70h
0x1800a5083  cmp     al, 10h
0x1800a5085  jz      short loc_1800A50A8
0x1800a5087  mov     ecx, edi
0x1800a5089  call    ?OpenFlagsToJournalMode@Database@StateRepository@@CA?AW4JournalMode@12@W4OpenFlags@12@@Z; StateRepository::Database::OpenFlagsToJournalMode(StateRepository::Database::OpenFlags)
0x1800a508e  mov     edx, eax
0x1800a5090  mov     rcx, rbx
0x1800a5093  call    ?SetJournalMode@Database@StateRepository@@QEAAJW4JournalMode@12@@Z; StateRepository::Database::SetJournalMode(StateRepository::Database::JournalMode)
0x1800a5098  mov     esi, eax
0x1800a509a  test    eax, eax
0x1800a509c  jns     short loc_1800A50A8
0x1800a509e  mov     edx, 0E5h
0x1800a50a3  jmp     loc_1800A4E2A
0x1800a50a8  mov     eax, edi
0x1800a50aa  and     eax, 300h
0x1800a50af  cmp     eax, 100h
0x1800a50b4  jz      short loc_1800A50D7
0x1800a50b6  mov     ecx, edi
0x1800a50b8  call    ?OpenFlagsToLockingMode@Database@StateRepository@@CA?AW4LockingMode@12@W4OpenFlags@12@@Z; StateRepository::Database::OpenFlagsToLockingMode(StateRepository::Database::OpenFlags)
0x1800a50bd  mov     edx, eax
0x1800a50bf  mov     rcx, rbx
0x1800a50c2  call    ?SetLockingMode@Database@StateRepository@@QEAAJW4LockingMode@12@@Z; StateRepository::Database::SetLockingMode(StateRepository::Database::LockingMode)
0x1800a50c7  mov     esi, eax
0x1800a50c9  test    eax, eax
0x1800a50cb  jns     short loc_1800A50D7
0x1800a50cd  mov     edx, 0EBh
0x1800a50d2  jmp     loc_1800A4E2A
0x1800a50d7  mov     eax, edi
0x1800a50d9  and     eax, 7000h
0x1800a50de  cmp     eax, 1000h
0x1800a50e3  jz      short loc_1800A511C
0x1800a50e5  mov     ecx, edi
0x1800a50e7  call    ?OpenFlagsToSynchronous@Database@StateRepository@@CA?AW4Synchronous@12@W4OpenFlags@12@@Z; StateRepository::Database::OpenFlagsToSynchronous(StateRepository::Database::OpenFlags)
0x1800a50ec  mov     edx, eax
0x1800a50ee  mov     rcx, rbx
0x1800a50f1  call    ?SetSynchronous@Database@StateRepository@@QEAAJW4Synchronous@12@@Z; StateRepository::Database::SetSynchronous(StateRepository::Database::Synchronous)
0x1800a50f6  mov     ebx, eax
0x1800a50f8  test    eax, eax
0x1800a50fa  jns     short loc_1800A511C
0x1800a50fc  mov     rcx, [rsp+88h]; this
0x1800a5104  lea     r8, aOnecoreBaseApp_18; "onecore\\base\\appmodel\\staterepositor"...
0x1800a510b  mov     r9d, eax; char *
0x1800a510e  mov     edx, 0F1h; void *
0x1800a5113  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800a5118  mov     eax, ebx
0x1800a511a  jmp     short loc_1800A511E
0x1800a511c  xor     eax, eax
0x1800a511e  add     rsp, 58h
0x1800a5122  pop     r15
0x1800a5124  pop     r14
0x1800a5126  pop     rdi
0x1800a5127  pop     rsi
0x1800a5128  pop     rbp
0x1800a5129  pop     rbx
0x1800a512a  retn
```
