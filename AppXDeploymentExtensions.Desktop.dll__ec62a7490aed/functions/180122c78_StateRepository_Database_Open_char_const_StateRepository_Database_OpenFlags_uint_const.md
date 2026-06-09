# StateRepository::Database::Open(char const *,StateRepository::Database::OpenFlags,uint const *)

- ea: `0x180122c78`
- end: `0x180122ff2`
- name: `?Open@Database@StateRepository@@QEAAJPEBDW4OpenFlags@12@PEBI@Z`
- size: `890`
- prototype: ``
- caller_count: `1`
- callee_count: `19`
- tags: ``

## callers

- `0x1800955d4`

## callees

- `0x180012fc8`
- `0x18001adb4`
- `0x18005ac08`
- `0x1800764b4`
- `0x1800a7ecc`
- `0x1800ab918`
- `0x1801221e0`
- `0x18012223c`
- `0x180122c78`
- `0x180122ff8`
- `0x180123084`
- `0x1801230e4`
- `0x1801231a0`
- `0x180123220`
- `0x180123590`
- `0x180123648`
- `0x1801236f8`
- `0x1801237a8`
- `0x180123858`

## import_xrefs

- `StateRepository.Core!sqlite3_log` at `0x180122d86`
- `StateRepository.Core!sqlite3_log` at `0x180122d86`
- `StateRepository.Core!sqlite3_errmsg` at `0x180122d15`
- `StateRepository.Core!sqlite3_errmsg` at `0x180122d15`
- `StateRepository.Core!sqlite3_close` at `0x180122de4`
- `StateRepository.Core!sqlite3_close` at `0x180122de4`
- `StateRepository.Core!sqlite3_open_v2` at `0x180122cd3`
- `StateRepository.Core!sqlite3_open_v2` at `0x180122cd3`
- `StateRepository.Core!sqlite3_extended_errcode` at `0x180122cfa`
- `StateRepository.Core!sqlite3_extended_errcode` at `0x180122cfa`
- `StateRepository.Core!sqlite3_file_control` at `0x180122d4a`
- `StateRepository.Core!sqlite3_file_control` at `0x180122d4a`
- `StateRepository.Core!sqlite3_extended_result_codes` at `0x180122e61`
- `StateRepository.Core!sqlite3_extended_result_codes` at `0x180122e61`

## string_xrefs

- `0x180122c9d`: `onecore\base\appmodel\staterepository\dataaccesslayer\database.cpp`
- `0x180122dc2`: `onecore\base\appmodel\staterepository\dataaccesslayer\database.cpp`
- `0x180122e36`: `onecore\base\appmodel\staterepository\dataaccesslayer\database.cpp`
- `0x180122f24`: `temp_store`
- `0x180122dd0`: `[sqlite3_open: lastErrNo:0x%X filecontrolrc:%d] #%u : %hs`
- `0x180122d6f`: `[sqlite3_open: lastErrNo:0x%X filecontrolrc:%d] #%u : %s`

## pseudocode

```c
__int64 StateRepository::Database::Open(StateRepository::Database *a1, __int64 a2, unsigned int a3, ...)
{
  signed int v6; // ebp
  __int64 v7; // rdx
  unsigned int v9; // eax
  int v10; // eax
  bool v11; // sf
  int v12; // eax
  unsigned int v13; // esi
  __int64 v14; // rax
  __int64 v15; // rcx
  int v16; // edi
  const char *v17; // r14
  signed int v18; // eax
  bool v19; // sf
  signed int v20; // eax
  int v21; // eax
  bool v22; // dl
  unsigned int v23; // eax
  __int64 v24; // rdx
  unsigned int v25; // eax
  unsigned int v26; // eax
  unsigned int v27; // eax
  int v28; // eax
  unsigned int v29; // ebx
  int v30; // [rsp+20h] [rbp-68h]
  int v31; // [rsp+20h] [rbp-68h]
  char *v32; // [rsp+28h] [rbp-60h]
  wil::details::in1diag3 *retaddr; // [rsp+88h] [rbp+0h]
  char *v34; // [rsp+A8h] [rbp+20h] BYREF
  va_list va; // [rsp+A8h] [rbp+20h]
  va_list va1; // [rsp+B0h] [rbp+28h] BYREF

  va_start(va1, a3);
  va_start(va, a3);
  v34 = va_arg(va1, char *);
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
      v30);
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
    LODWORD(v34) = -2147024882;
    v17 = (const char *)v14;
    if ( v15 )
      v16 = sqlite3_file_control(v15, 0, 4, (char **)va);
    sqlite3_log(
      v13,
      "[sqlite3_open: lastErrNo:0x%X filecontrolrc:%d] #%u : %s",
      (_DWORD)v34,
      v16,
      _InterlockedIncrement(&dword_180245B88),
      v17);
    _InterlockedIncrement(&dword_180245B88);
    LODWORD(v32) = (_DWORD)v34;
    wil::details::in1diag3::Log_HrMsg(
      retaddr,
      (void *)0xBE,
      (unsigned int)"onecore\\base\\appmodel\\staterepository\\dataaccesslayer\\database.cpp",
      (const char *)v13,
      (int)"[sqlite3_open: lastErrNo:0x%X filecontrolrc:%d] #%u : %hs",
      v32);
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
        v31);
    *(_QWORD *)a1 = 0;
    return v13;
  }
  else
  {
    v20 = StateRepository::Database::SetConnectionId(a1);
    if ( v20 > 0 )
      v20 = (unsigned __int16)v20 | 0x87AF0000;
    if ( v20 < 0 )
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0xC5,
        (unsigned int)"onecore\\base\\appmodel\\staterepository\\dataaccesslayer\\database.cpp",
        (const char *)(unsigned int)v20,
        v30);
    v21 = sqlite3_extended_result_codes(*(_QWORD *)a1, 1);
    v6 = v21;
    if ( v21 > 0 )
      v6 = (unsigned __int16)v21 | 0x87AF0000;
    if ( v6 < 0 )
    {
      v7 = 201;
      goto LABEL_3;
    }
    if ( (a3 & 0x20000) != 0 )
    {
      v6 = StateRepository::Database::EnableTrace(a1, v22);
      if ( v6 < 0 )
      {
        v7 = 205;
        goto LABEL_3;
      }
    }
    if ( (a3 & 0x80000) != 0 )
    {
      v6 = StateRepository::Database::EnableProfile(a1, v22);
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
      v23 = StateRepository::Database::OpenFlagsToWalFilesPersistence(a3);
      v6 = StateRepository::Database::SetWalFilesPersistence(a1, v24, v23);
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
      v25 = StateRepository::Database::OpenFlagsToJournalMode(a3);
      v6 = StateRepository::Database::SetJournalMode(a1, v25);
      if ( v6 < 0 )
      {
        v7 = 229;
        goto LABEL_3;
      }
    }
    if ( (a3 & 0x300) != 0x100 )
    {
      v26 = StateRepository::Database::OpenFlagsToLockingMode(a3);
      v6 = StateRepository::Database::SetLockingMode(a1, v26);
      if ( v6 < 0 )
      {
        v7 = 235;
        goto LABEL_3;
      }
    }
    if ( (a3 & 0x7000) == 0x1000 )
      return 0;
    v27 = StateRepository::Database::OpenFlagsToSynchronous(a3);
    v28 = StateRepository::Database::SetSynchronous(a1, v27);
    v29 = v28;
    if ( v28 >= 0 )
    {
      return 0;
    }
    else
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xF1,
        (unsigned int)"onecore\\base\\appmodel\\staterepository\\dataaccesslayer\\database.cpp",
        (const char *)(unsigned int)v28,
        v30);
      return v29;
    }
  }
}

```

## disassembly

```asm
0x180122c78  mov     [rsp+arg_18], r9
0x180122c7d  push    rbx
0x180122c7e  push    rbp
0x180122c7f  push    rsi
0x180122c80  push    rdi
0x180122c81  push    r14
0x180122c83  push    r15
0x180122c85  sub     rsp, 58h
0x180122c89  mov     esi, r8d
0x180122c8c  mov     rdi, rdx
0x180122c8f  mov     rbx, rcx
0x180122c92  call    ?Close@Database@StateRepository@@QEAAJXZ; StateRepository::Database::Close(void)
0x180122c97  mov     ebp, eax
0x180122c99  test    eax, eax
0x180122c9b  jns     short loc_180122CC0
0x180122c9d  lea     r8, aOnecoreBaseApp_69; "onecore\\base\\appmodel\\staterepositor"...
0x180122ca4  mov     edx, 0A4h; void *
0x180122ca9  mov     rcx, [rsp+88h]; this
0x180122cb1  mov     r9d, ebp; char *
0x180122cb4  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180122cb9  mov     eax, ebp
0x180122cbb  jmp     loc_180122FE4
0x180122cc0  mov     ecx, esi
0x180122cc2  call    ?OpenFlagsToOpenFlags@Database@StateRepository@@CAHW4OpenFlags@12@@Z; StateRepository::Database::OpenFlagsToOpenFlags(StateRepository::Database::OpenFlags)
0x180122cc7  mov     r8d, eax
0x180122cca  xor     r9d, r9d
0x180122ccd  mov     rdx, rbx
0x180122cd0  mov     rcx, rdi
0x180122cd3  call    cs:__imp_sqlite3_open_v2
0x180122cda  nop     dword ptr [rax+rax+00h]
0x180122cdf  mov     r15d, 87AF0000h
0x180122ce5  test    eax, eax
0x180122ce7  jle     short loc_180122CF1
0x180122ce9  movzx   eax, ax
0x180122cec  or      eax, r15d
0x180122cef  test    eax, eax
0x180122cf1  jns     loc_180122E24
0x180122cf7  mov     rcx, [rbx]
0x180122cfa  call    cs:__imp_sqlite3_extended_errcode
0x180122d01  nop     dword ptr [rax+rax+00h]
0x180122d06  mov     esi, eax
0x180122d08  test    eax, eax
0x180122d0a  jle     short loc_180122D12
0x180122d0c  movzx   esi, ax
0x180122d0f  or      esi, r15d
0x180122d12  mov     rcx, [rbx]
0x180122d15  call    cs:__imp_sqlite3_errmsg
0x180122d1c  nop     dword ptr [rax+rax+00h]
0x180122d21  mov     rcx, [rbx]
0x180122d24  mov     edi, 7
0x180122d29  mov     dword ptr [rsp+88h+arg_18], 8007000Eh
0x180122d34  mov     r14, rax
0x180122d37  test    rcx, rcx
0x180122d3a  jz      short loc_180122D58
0x180122d3c  lea     r9, [rsp+88h+arg_18]
0x180122d44  xor     edx, edx
0x180122d46  lea     r8d, [rdi-3]
0x180122d4a  call    cs:__imp_sqlite3_file_control
0x180122d51  nop     dword ptr [rax+rax+00h]
0x180122d56  mov     edi, eax
0x180122d58  mov     ebp, 1
0x180122d5d  mov     ecx, ebp
0x180122d5f  lock xadd cs:dword_180245B88, ecx
0x180122d67  mov     r8d, dword ptr [rsp+88h+arg_18]
0x180122d6f  lea     rdx, aSqlite3OpenLas_0; "[sqlite3_open: lastErrNo:0x%X filecontr"...
0x180122d76  add     ecx, ebp
0x180122d78  mov     [rsp+88h+var_60], r14
0x180122d7d  mov     [rsp+88h+var_68], ecx
0x180122d81  mov     r9d, edi
0x180122d84  mov     ecx, esi
0x180122d86  call    cs:__imp_sqlite3_log
0x180122d8d  nop     dword ptr [rax+rax+00h]
0x180122d92  mov     eax, ebp
0x180122d94  lock xadd cs:dword_180245B88, eax
0x180122d9c  mov     rcx, [rsp+88h]; this
0x180122da4  add     eax, ebp
0x180122da6  mov     [rsp+88h+var_48], r14
0x180122dab  mov     r9d, esi; char *
0x180122dae  mov     [rsp+88h+var_50], eax
0x180122db2  mov     edx, 0BEh; void *
0x180122db7  mov     eax, dword ptr [rsp+88h+arg_18]
0x180122dbe  mov     [rsp+88h+var_58], edi
0x180122dc2  lea     rdi, aOnecoreBaseApp_69; "onecore\\base\\appmodel\\staterepositor"...
0x180122dc9  mov     dword ptr [rsp+88h+var_60], eax; char *
0x180122dcd  mov     r8, rdi; unsigned int
0x180122dd0  lea     rax, aSqlite3OpenLas; "[sqlite3_open: lastErrNo:0x%X filecontr"...
0x180122dd7  mov     qword ptr [rsp+88h+var_68], rax; int
0x180122ddc  call    ?Log_HrMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Log_HrMsg(void *,uint,char const *,long,char const *,...)
0x180122de1  mov     rcx, [rbx]
0x180122de4  call    cs:__imp_sqlite3_close
0x180122deb  nop     dword ptr [rax+rax+00h]
0x180122df0  test    eax, eax
0x180122df2  jle     short loc_180122DFC
0x180122df4  movzx   eax, ax
0x180122df7  or      eax, r15d
0x180122dfa  test    eax, eax
0x180122dfc  jns     short loc_180122E16
0x180122dfe  mov     rcx, [rsp+88h]; this
0x180122e06  mov     r9d, eax; char *
0x180122e09  mov     r8, rdi; unsigned int
0x180122e0c  mov     edx, 0BFh; void *
0x180122e11  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180122e16  mov     qword ptr [rbx], 0
0x180122e1d  mov     eax, esi
0x180122e1f  jmp     loc_180122FE4
0x180122e24  mov     rcx, rbx; this
0x180122e27  call    ?SetConnectionId@Database@StateRepository@@AEAAJXZ; StateRepository::Database::SetConnectionId(void)
0x180122e2c  test    eax, eax
0x180122e2e  jle     short loc_180122E36
0x180122e30  movzx   eax, ax
0x180122e33  or      eax, r15d
0x180122e36  lea     rdi, aOnecoreBaseApp_69; "onecore\\base\\appmodel\\staterepositor"...
0x180122e3d  test    eax, eax
0x180122e3f  jns     short loc_180122E59
0x180122e41  mov     rcx, [rsp+88h]; this
0x180122e49  mov     r9d, eax; char *
0x180122e4c  mov     r8, rdi; unsigned int
0x180122e4f  mov     edx, 0C5h; void *
0x180122e54  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180122e59  mov     rcx, [rbx]
0x180122e5c  mov     edx, 1
0x180122e61  call    cs:__imp_sqlite3_extended_result_codes
0x180122e68  nop     dword ptr [rax+rax+00h]
0x180122e6d  mov     ebp, eax
0x180122e6f  test    eax, eax
0x180122e71  jle     short loc_180122E79
0x180122e73  movzx   ebp, ax
0x180122e76  or      ebp, r15d
0x180122e79  test    ebp, ebp
0x180122e7b  jns     short loc_180122E8A
0x180122e7d  mov     r8, rdi
0x180122e80  mov     edx, 0C9h
0x180122e85  jmp     loc_180122CA9
0x180122e8a  bt      esi, 11h
0x180122e8e  jnb     short loc_180122EAB
0x180122e90  mov     rcx, rbx; this
0x180122e93  call    ?EnableTrace@Database@StateRepository@@QEAAJ_N@Z; StateRepository::Database::EnableTrace(bool)
0x180122e98  mov     ebp, eax
0x180122e9a  test    eax, eax
0x180122e9c  jns     short loc_180122EAB
0x180122e9e  mov     r8, rdi
0x180122ea1  mov     edx, 0CDh
0x180122ea6  jmp     loc_180122CA9
0x180122eab  bt      esi, 13h
0x180122eaf  jnb     short loc_180122ECC
0x180122eb1  mov     rcx, rbx; this
0x180122eb4  call    ?EnableProfile@Database@StateRepository@@QEAAJ_N@Z; StateRepository::Database::EnableProfile(bool)
0x180122eb9  mov     ebp, eax
0x180122ebb  test    eax, eax
0x180122ebd  jns     short loc_180122ECC
0x180122ebf  mov     r8, rdi
0x180122ec2  mov     edx, 0D2h
0x180122ec7  jmp     loc_180122CA9
0x180122ecc  mov     rcx, rbx; this
0x180122ecf  call    ?RegisterFunctions@Database@StateRepository@@QEAAJXZ; StateRepository::Database::RegisterFunctions(void)
0x180122ed4  mov     ebp, eax
0x180122ed6  test    eax, eax
0x180122ed8  jns     short loc_180122EE7
0x180122eda  mov     r8, rdi
0x180122edd  mov     edx, 0D5h
0x180122ee2  jmp     loc_180122CA9
0x180122ee7  mov     eax, esi
0x180122ee9  and     eax, 700000h
0x180122eee  cmp     eax, 100000h
0x180122ef3  jz      short loc_180122F1A
0x180122ef5  mov     ecx, esi
0x180122ef7  call    ?OpenFlagsToWalFilesPersistence@Database@StateRepository@@CA?AW4WalFilesPersistence@12@W4OpenFlags@12@@Z; StateRepository::Database::OpenFlagsToWalFilesPersistence(StateRepository::Database::OpenFlags)
0x180122efc  mov     r8d, eax
0x180122eff  mov     rcx, rbx
0x180122f02  call    ?SetWalFilesPersistence@Database@StateRepository@@QEAAJPEBDW4WalFilesPersistence@12@@Z; StateRepository::Database::SetWalFilesPersistence(char const *,StateRepository::Database::WalFilesPersistence)
0x180122f07  mov     ebp, eax
0x180122f09  test    eax, eax
0x180122f0b  jns     short loc_180122F1A
0x180122f0d  mov     r8, rdi
0x180122f10  mov     edx, 0DDh
0x180122f15  jmp     loc_180122CA9
0x180122f1a  lea     r8, aMemory; "MEMORY"
0x180122f21  mov     rcx, rbx; this
0x180122f24  lea     rdx, aTempStore; "temp_store"
0x180122f2b  call    ?SetPragma@Database@StateRepository@@QEAAJPEBD0@Z; StateRepository::Database::SetPragma(char const *,char const *)
0x180122f30  mov     ebp, eax
0x180122f32  test    eax, eax
0x180122f34  jns     short loc_180122F43
0x180122f36  mov     r8, rdi
0x180122f39  mov     edx, 0E0h
0x180122f3e  jmp     loc_180122CA9
0x180122f43  mov     eax, esi
0x180122f45  and     al, 70h
0x180122f47  cmp     al, 10h
0x180122f49  jz      short loc_180122F6F
0x180122f4b  mov     ecx, esi
0x180122f4d  call    ?OpenFlagsToJournalMode@Database@StateRepository@@CA?AW4JournalMode@12@W4OpenFlags@12@@Z; StateRepository::Database::OpenFlagsToJournalMode(StateRepository::Database::OpenFlags)
0x180122f52  mov     edx, eax
0x180122f54  mov     rcx, rbx
0x180122f57  call    ?SetJournalMode@Database@StateRepository@@QEAAJW4JournalMode@12@@Z; StateRepository::Database::SetJournalMode(StateRepository::Database::JournalMode)
0x180122f5c  mov     ebp, eax
0x180122f5e  test    eax, eax
0x180122f60  jns     short loc_180122F6F
0x180122f62  mov     r8, rdi
0x180122f65  mov     edx, 0E5h
0x180122f6a  jmp     loc_180122CA9
0x180122f6f  mov     eax, esi
0x180122f71  and     eax, 300h
0x180122f76  cmp     eax, 100h
0x180122f7b  jz      short loc_180122FA1
0x180122f7d  mov     ecx, esi
0x180122f7f  call    ?OpenFlagsToLockingMode@Database@StateRepository@@CA?AW4LockingMode@12@W4OpenFlags@12@@Z; StateRepository::Database::OpenFlagsToLockingMode(StateRepository::Database::OpenFlags)
0x180122f84  mov     edx, eax
0x180122f86  mov     rcx, rbx
0x180122f89  call    ?SetLockingMode@Database@StateRepository@@QEAAJW4LockingMode@12@@Z; StateRepository::Database::SetLockingMode(StateRepository::Database::LockingMode)
0x180122f8e  mov     ebp, eax
0x180122f90  test    eax, eax
0x180122f92  jns     short loc_180122FA1
0x180122f94  mov     r8, rdi
0x180122f97  mov     edx, 0EBh
0x180122f9c  jmp     loc_180122CA9
0x180122fa1  mov     eax, esi
0x180122fa3  and     eax, 7000h
0x180122fa8  cmp     eax, 1000h
0x180122fad  jz      short loc_180122FE2
0x180122faf  mov     ecx, esi
0x180122fb1  call    ?OpenFlagsToSynchronous@Database@StateRepository@@CA?AW4Synchronous@12@W4OpenFlags@12@@Z; StateRepository::Database::OpenFlagsToSynchronous(StateRepository::Database::OpenFlags)
0x180122fb6  mov     edx, eax
0x180122fb8  mov     rcx, rbx
0x180122fbb  call    ?SetSynchronous@Database@StateRepository@@QEAAJW4Synchronous@12@@Z; StateRepository::Database::SetSynchronous(StateRepository::Database::Synchronous)
0x180122fc0  mov     ebx, eax
0x180122fc2  test    eax, eax
0x180122fc4  jns     short loc_180122FE2
0x180122fc6  mov     rcx, [rsp+88h]; this
0x180122fce  mov     r9d, eax; char *
0x180122fd1  mov     r8, rdi; unsigned int
0x180122fd4  mov     edx, 0F1h; void *
0x180122fd9  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180122fde  mov     eax, ebx
0x180122fe0  jmp     short loc_180122FE4
0x180122fe2  xor     eax, eax
0x180122fe4  add     rsp, 58h
0x180122fe8  pop     r15
0x180122fea  pop     r14
0x180122fec  pop     rdi
0x180122fed  pop     rsi
0x180122fee  pop     rbp
0x180122fef  pop     rbx
0x180122ff0  retn
```
