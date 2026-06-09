# StateRepository::Database::Open(char const *,StateRepository::Database::OpenFlags,uint const *)

- ea: `0x1800fa944`
- end: `0x1800fae41`
- name: `?Open@Database@StateRepository@@QEAAJPEBDW4OpenFlags@12@PEBI@Z`
- size: `1277`
- prototype: `__int64(StateRepository::Database *, __int64, unsigned int, ...)`
- caller_count: `2`
- callee_count: `21`
- tags: ``

## callers

- `0x1800fae48`
- `0x1801019b8`

## callees

- `0x1800045b0`
- `0x180005db0`
- `0x180005e30`
- `0x180006190`
- `0x180006970`
- `0x180006a00`
- `0x180011c10`
- `0x180016970`
- `0x180022a30`
- `0x1800eabf4`
- `0x1800f7630`
- `0x1800f8f28`
- `0x1800fa588`
- `0x1800fa944`
- `0x1800fafb0`
- `0x1800fb1f4`
- `0x1800fbcb4`
- `0x1800fbd64`
- `0x1800fbe4c`
- `0x1800fbf64`
- `0x1800fc014`

## string_xrefs

- `0x1800fa971`: `onecore\base\appmodel\staterepository\dataaccesslayer\database.cpp`
- `0x1800faa6c`: `onecore\base\appmodel\staterepository\dataaccesslayer\database.cpp`
- `0x1800fab15`: `onecore\base\appmodel\staterepository\dataaccesslayer\database.cpp`
- `0x1800fab3d`: `onecore\base\appmodel\staterepository\dataaccesslayer\database.cpp`
- `0x1800fab9e`: `onecore\base\appmodel\staterepository\dataaccesslayer\database.cpp`
- `0x1800fabef`: `onecore\base\appmodel\staterepository\dataaccesslayer\database.cpp`
- `0x1800faa20`: `[sqlite3_open: lastErrNo:0x%X filecontrolrc:%d] #%u : %s`
- `0x1800faa7a`: `[sqlite3_open: lastErrNo:0x%X filecontrolrc:%d] #%u : %hs`
- `0x1800fac8b`: `temp_store`

## pseudocode

```c
__int64 StateRepository::Database::Open(StateRepository::Database *a1, __int64 a2, unsigned int a3, ...)
{
  int v6; // eax
  unsigned int v7; // esi
  unsigned int v9; // eax
  int v10; // eax
  bool v11; // sf
  int v12; // eax
  unsigned int v13; // ebp
  __int64 v14; // rax
  __int64 v15; // rcx
  const char *v16; // r14
  int v17; // ebx
  signed int v18; // eax
  bool v19; // sf
  signed __int64 v20; // rax
  __int64 v21; // rcx
  int v22; // eax
  __int64 v23; // rdx
  int v24; // edi
  __int64 v25; // rdx
  int v26; // eax
  unsigned int v27; // ebp
  __int64 v28; // rdx
  int v29; // r15d
  __int64 v30; // rdx
  int v31; // eax
  __int64 v32; // rdx
  int v33; // eax
  __int64 v34; // rdx
  int v35; // eax
  int v36; // [rsp+20h] [rbp-68h]
  char *v37; // [rsp+28h] [rbp-60h]
  char *v38; // [rsp+28h] [rbp-60h]
  wil::details::in1diag3 *retaddr; // [rsp+88h] [rbp+0h]
  char *v40; // [rsp+A8h] [rbp+20h] BYREF
  va_list va; // [rsp+A8h] [rbp+20h]
  va_list va1; // [rsp+B0h] [rbp+28h] BYREF

  va_start(va1, a3);
  va_start(va, a3);
  v40 = va_arg(va1, char *);
  v6 = StateRepository::Database::Close(a1);
  v7 = v6;
  if ( v6 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xA4,
      (unsigned int)"onecore\\base\\appmodel\\staterepository\\dataaccesslayer\\database.cpp",
      (const char *)(unsigned int)v6,
      v36);
    return v7;
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
    v16 = (const char *)v14;
    LODWORD(v40) = -2147024882;
    v17 = 7;
    if ( v15 )
      v17 = sqlite3_file_control(v15, 0, 4, (char **)va);
    sqlite3_log(
      v13,
      "[sqlite3_open: lastErrNo:0x%X filecontrolrc:%d] #%u : %s",
      (_DWORD)v40,
      v17,
      _InterlockedIncrement(&dword_180140410),
      v16);
    LODWORD(v38) = (_DWORD)v40;
    wil::details::in1diag3::Log_HrMsg(
      retaddr,
      (void *)0xBE,
      (unsigned int)"onecore\\base\\appmodel\\staterepository\\dataaccesslayer\\database.cpp",
      (const char *)v13,
      (int)"[sqlite3_open: lastErrNo:0x%X filecontrolrc:%d] #%u : %hs",
      v38,
      v17,
      _InterlockedIncrement(&dword_180140410),
      v16);
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
        (int)"onecore\\base\\appmodel\\staterepository\\dataaccesslayer\\database.cpp",
        (const char *)(unsigned int)v18);
    *(_QWORD *)a1 = 0;
    return v13;
  }
  v20 = _InterlockedIncrement64(&qword_1801402A8);
  if ( !v20 )
    v20 = _InterlockedIncrement64(&qword_1801402A8);
  v21 = *(_QWORD *)a1;
  *((_QWORD *)a1 + 15) = v20;
  v22 = sqlite3_extended_result_codes(v21, 1);
  v13 = v22;
  if ( v22 > 0 )
    v13 = (unsigned __int16)v22 | 0x87AF0000;
  if ( (v13 & 0x80000000) != 0 )
  {
    v23 = 201;
LABEL_22:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v23,
      (unsigned int)"onecore\\base\\appmodel\\staterepository\\dataaccesslayer\\database.cpp",
      (const char *)v13,
      v36);
    return v13;
  }
  if ( (a3 & 0x20000) != 0 )
  {
    if ( !*(_QWORD *)a1 )
    {
      v24 = -2147019873;
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x815,
        (unsigned int)"onecore\\base\\appmodel\\staterepository\\dataaccesslayer\\database.cpp",
        (const char *)0x8007139FLL,
        v36);
      v25 = 205;
LABEL_26:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v25,
        (unsigned int)"onecore\\base\\appmodel\\staterepository\\dataaccesslayer\\database.cpp",
        (const char *)(unsigned int)v24,
        v36);
      return (unsigned int)v24;
    }
    sqlite3_trace(*(_QWORD *)a1, StateRepository::Logging::sqliteTraceCallback, 0);
  }
  if ( (a3 & 0x80000) != 0 )
  {
    if ( !*(_QWORD *)a1 )
    {
      v24 = -2147019873;
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x81D,
        (unsigned int)"onecore\\base\\appmodel\\staterepository\\dataaccesslayer\\database.cpp",
        (const char *)0x8007139FLL,
        v36);
      v25 = 210;
      goto LABEL_26;
    }
    sqlite3_profile(*(_QWORD *)a1, StateRepository::Logging::sqliteProfileCallback, 0);
    *((_BYTE *)a1 + 36) = 1;
  }
  v13 = StateRepository::Database::RegisterFunctions(a1);
  if ( (v13 & 0x80000000) != 0 )
  {
    v23 = 213;
    goto LABEL_22;
  }
  v26 = a3 & 0x700000;
  v27 = 3;
  if ( (a3 & 0x700000) == 0x100000 )
    goto LABEL_45;
  switch ( v26 )
  {
    case 0:
      goto LABEL_39;
    case 2097152:
      v28 = 1;
      break;
    case 3145728:
      v28 = 2;
      break;
    default:
      LODWORD(v37) = a3;
      wil::details::in1diag3::Log_HrMsg(
        retaddr,
        (void *)0xC0F,
        (unsigned int)"onecore\\base\\appmodel\\staterepository\\dataaccesslayer\\database.cpp",
        (const char *)0x8000FFFFLL,
        (int)"Unknown mask_walfiles bits, flags=0x%X",
        v37);
LABEL_39:
      v28 = 3;
      break;
  }
  v29 = StateRepository::Database::SetWalFilesPersistence(a1, v28);
  if ( v29 < 0 )
  {
    v30 = 221;
LABEL_42:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v30,
      (unsigned int)"onecore\\base\\appmodel\\staterepository\\dataaccesslayer\\database.cpp",
      (const char *)(unsigned int)v29,
      v36);
    return (unsigned int)v29;
  }
LABEL_45:
  v29 = StateRepository::Database::SetPragma(a1, "temp_store", "MEMORY");
  if ( v29 < 0 )
  {
    v30 = 224;
    goto LABEL_42;
  }
  v31 = a3 & 0x70;
  if ( v31 != 16 )
  {
    if ( (a3 & 0x70) != 0 )
    {
      switch ( v31 )
      {
        case ' ':
          v32 = 1;
          goto LABEL_57;
        case '0':
          v32 = 2;
          goto LABEL_57;
        case '@':
          v32 = 3;
          goto LABEL_57;
        case 'P':
          v32 = 4;
          goto LABEL_57;
      }
      if ( v31 != 96 )
      {
        if ( v31 != 112 )
        {
          LODWORD(v37) = a3;
          wil::details::in1diag3::Log_HrMsg(
            retaddr,
            (void *)0xBB9,
            (unsigned int)"onecore\\base\\appmodel\\staterepository\\dataaccesslayer\\database.cpp",
            (const char *)0x8000FFFFLL,
            (int)"Unknown mask_journalmode bits, flags=0x%X",
            v37);
          goto LABEL_56;
        }
        v32 = 6;
LABEL_57:
        v29 = StateRepository::Database::SetJournalMode(a1, v32);
        if ( v29 < 0 )
        {
          v30 = 229;
          goto LABEL_42;
        }
        goto LABEL_64;
      }
    }
LABEL_56:
    v32 = 5;
    goto LABEL_57;
  }
LABEL_64:
  v33 = a3 & 0x300;
  if ( v33 == 256 )
    goto LABEL_73;
  if ( (a3 & 0x300) == 0 || v33 == 512 )
    goto LABEL_69;
  if ( v33 != 768 )
  {
    LODWORD(v37) = a3;
    wil::details::in1diag3::Log_HrMsg(
      retaddr,
      (void *)0xC22,
      (unsigned int)"onecore\\base\\appmodel\\staterepository\\dataaccesslayer\\database.cpp",
      (const char *)0x8000FFFFLL,
      (int)"Unknown mask_lockingmode bits, flags=0x%X",
      v37);
LABEL_69:
    v34 = 1;
    goto LABEL_70;
  }
  v34 = 2;
LABEL_70:
  v29 = StateRepository::Database::SetLockingMode(a1, v34);
  if ( v29 < 0 )
  {
    v30 = 235;
    goto LABEL_42;
  }
LABEL_73:
  v35 = a3 & 0x7000;
  if ( v35 != 4096 )
  {
    if ( (a3 & 0x7000) != 0 )
    {
      if ( v35 == 0x2000 )
      {
        v27 = 1;
      }
      else if ( v35 == 12288 )
      {
        v27 = 2;
      }
      else if ( v35 != 0x4000 )
      {
        if ( v35 == 20480 )
        {
          v27 = 4;
        }
        else
        {
          LODWORD(v37) = a3;
          wil::details::in1diag3::Log_HrMsg(
            retaddr,
            (void *)0xC64,
            (unsigned int)"onecore\\base\\appmodel\\staterepository\\dataaccesslayer\\database.cpp",
            (const char *)0x8000FFFFLL,
            (int)"Unknown mask_synchronous bits, flags=0x%X",
            v37);
        }
      }
    }
    v24 = StateRepository::Database::SetSynchronous(a1, v27);
    if ( v24 < 0 )
    {
      v25 = 241;
      goto LABEL_26;
    }
  }
  return 0;
}

```

## disassembly

```asm
0x1800fa944  mov     [rsp+arg_18], r9
0x1800fa949  push    rbx
0x1800fa94a  push    rbp
0x1800fa94b  push    rsi
0x1800fa94c  push    rdi
0x1800fa94d  push    r14
0x1800fa94f  push    r15
0x1800fa951  sub     rsp, 58h
0x1800fa955  mov     r14d, r8d
0x1800fa958  mov     rbx, rdx
0x1800fa95b  mov     rdi, rcx
0x1800fa95e  call    ?Close@Database@StateRepository@@QEAAJXZ; StateRepository::Database::Close(void)
0x1800fa963  mov     esi, eax
0x1800fa965  test    eax, eax
0x1800fa967  jns     short loc_1800FA98C
0x1800fa969  mov     rcx, [rsp+88h]; this
0x1800fa971  lea     r8, aOnecoreBaseApp_18; "onecore\\base\\appmodel\\staterepositor"...
0x1800fa978  mov     r9d, eax; char *
0x1800fa97b  mov     edx, 0A4h; void *
0x1800fa980  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800fa985  mov     eax, esi
0x1800fa987  jmp     loc_1800FAE34
0x1800fa98c  mov     ecx, r14d
0x1800fa98f  call    ?OpenFlagsToOpenFlags@Database@StateRepository@@CAHW4OpenFlags@12@@Z; StateRepository::Database::OpenFlagsToOpenFlags(StateRepository::Database::OpenFlags)
0x1800fa994  mov     r8d, eax
0x1800fa997  xor     r9d, r9d
0x1800fa99a  mov     rdx, rdi
0x1800fa99d  mov     rcx, rbx
0x1800fa9a0  call    sqlite3_open_v2
0x1800fa9a5  mov     r15d, 87AF0000h
0x1800fa9ab  test    eax, eax
0x1800fa9ad  jle     short loc_1800FA9B7
0x1800fa9af  movzx   eax, ax
0x1800fa9b2  or      eax, r15d
0x1800fa9b5  test    eax, eax
0x1800fa9b7  jns     loc_1800FAAC7
0x1800fa9bd  mov     rcx, [rdi]
0x1800fa9c0  call    sqlite3_extended_errcode
0x1800fa9c5  mov     ebp, eax
0x1800fa9c7  test    eax, eax
0x1800fa9c9  jle     short loc_1800FA9D1
0x1800fa9cb  movzx   ebp, ax
0x1800fa9ce  or      ebp, r15d
0x1800fa9d1  mov     rcx, [rdi]
0x1800fa9d4  call    sqlite3_errmsg
0x1800fa9d9  mov     rcx, [rdi]
0x1800fa9dc  mov     r14, rax
0x1800fa9df  mov     dword ptr [rsp+88h+arg_18], 8007000Eh
0x1800fa9ea  mov     ebx, 7
0x1800fa9ef  test    rcx, rcx
0x1800fa9f2  jz      short loc_1800FAA09
0x1800fa9f4  lea     r9, [rsp+88h+arg_18]
0x1800fa9fc  xor     edx, edx
0x1800fa9fe  lea     r8d, [rbx-3]
0x1800faa02  call    sqlite3_file_control
0x1800faa07  mov     ebx, eax
0x1800faa09  mov     esi, 1
0x1800faa0e  mov     ecx, esi
0x1800faa10  lock xadd cs:dword_180140410, ecx
0x1800faa18  mov     r8d, dword ptr [rsp+88h+arg_18]
0x1800faa20  lea     rdx, aSqlite3OpenLas_0; "[sqlite3_open: lastErrNo:0x%X filecontr"...
0x1800faa27  add     ecx, esi
0x1800faa29  mov     [rsp+88h+var_60], r14
0x1800faa2e  mov     [rsp+88h+var_68], ecx
0x1800faa32  mov     r9d, ebx
0x1800faa35  mov     ecx, ebp
0x1800faa37  call    sqlite3_log
0x1800faa3c  mov     eax, esi
0x1800faa3e  lock xadd cs:dword_180140410, eax
0x1800faa46  mov     rcx, [rsp+88h]; this
0x1800faa4e  add     eax, esi
0x1800faa50  mov     [rsp+88h+var_48], r14
0x1800faa55  mov     r9d, ebp; char *
0x1800faa58  mov     [rsp+88h+var_50], eax
0x1800faa5c  mov     edx, 0BEh; void *
0x1800faa61  mov     eax, dword ptr [rsp+88h+arg_18]
0x1800faa68  mov     [rsp+88h+var_58], ebx
0x1800faa6c  lea     rbx, aOnecoreBaseApp_18; "onecore\\base\\appmodel\\staterepositor"...
0x1800faa73  mov     dword ptr [rsp+88h+var_60], eax; char *
0x1800faa77  mov     r8, rbx; unsigned int
0x1800faa7a  lea     rax, aSqlite3OpenLas; "[sqlite3_open: lastErrNo:0x%X filecontr"...
0x1800faa81  mov     qword ptr [rsp+88h+var_68], rax; int
0x1800faa86  call    ?Log_HrMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Log_HrMsg(void *,uint,char const *,long,char const *,...)
0x1800faa8b  mov     rcx, [rdi]
0x1800faa8e  call    sqlite3_close
0x1800faa93  test    eax, eax
0x1800faa95  jle     short loc_1800FAA9F
0x1800faa97  movzx   eax, ax
0x1800faa9a  or      eax, r15d
0x1800faa9d  test    eax, eax
0x1800faa9f  jns     short loc_1800FAAB9
0x1800faaa1  mov     rcx, [rsp+88h]; this
0x1800faaa9  mov     r9d, eax; char *
0x1800faaac  mov     r8, rbx; unsigned int
0x1800faaaf  mov     edx, 0BFh; void *
0x1800faab4  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1800faab9  mov     qword ptr [rdi], 0
0x1800faac0  mov     eax, ebp
0x1800faac2  jmp     loc_1800FAE34
0x1800faac7  mov     esi, 1
0x1800faacc  mov     eax, esi
0x1800faace  lock xadd cs:qword_1801402A8, rax
0x1800faad7  add     rax, rsi
0x1800faada  jnz     short loc_1800FAAEA
0x1800faadc  mov     eax, esi
0x1800faade  lock xadd cs:qword_1801402A8, rax
0x1800faae7  add     rax, rsi
0x1800faaea  mov     rcx, [rdi]
0x1800faaed  mov     edx, esi
0x1800faaef  mov     [rdi+78h], rax
0x1800faaf3  call    sqlite3_extended_result_codes
0x1800faaf8  mov     ebp, eax
0x1800faafa  test    eax, eax
0x1800faafc  jle     short loc_1800FAB04
0x1800faafe  movzx   ebp, ax
0x1800fab01  or      ebp, r15d
0x1800fab04  test    ebp, ebp
0x1800fab06  jns     short loc_1800FAB26
0x1800fab08  mov     edx, 0C9h; void *
0x1800fab0d  mov     rcx, [rsp+88h]; this
0x1800fab15  lea     r8, aOnecoreBaseApp_18; "onecore\\base\\appmodel\\staterepositor"...
0x1800fab1c  mov     r9d, ebp; char *
0x1800fab1f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800fab24  jmp     short loc_1800FAAC0
0x1800fab26  bt      r14d, 11h
0x1800fab2b  jnb     short loc_1800FAB87
0x1800fab2d  mov     rcx, [rdi]
0x1800fab30  test    rcx, rcx
0x1800fab33  jnz     short loc_1800FAB78
0x1800fab35  mov     rcx, [rsp+88h]; this
0x1800fab3d  lea     rbx, aOnecoreBaseApp_18; "onecore\\base\\appmodel\\staterepositor"...
0x1800fab44  mov     edi, 8007139Fh
0x1800fab49  mov     r8, rbx; unsigned int
0x1800fab4c  mov     r9d, edi; char *
0x1800fab4f  mov     edx, 815h; void *
0x1800fab54  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800fab59  mov     edx, 0CDh; void *
0x1800fab5e  mov     rcx, [rsp+88h]; this
0x1800fab66  mov     r9d, edi; char *
0x1800fab69  mov     r8, rbx; unsigned int
0x1800fab6c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800fab71  mov     eax, edi
0x1800fab73  jmp     loc_1800FAE34
0x1800fab78  xor     r8d, r8d
0x1800fab7b  lea     rdx, ?sqliteTraceCallback@Logging@StateRepository@@YAXPEAXPEBD@Z; StateRepository::Logging::sqliteTraceCallback(void *,char const *)
0x1800fab82  call    sqlite3_trace
0x1800fab87  bt      r14d, 13h
0x1800fab8c  jnb     short loc_1800FABD4
0x1800fab8e  mov     rcx, [rdi]
0x1800fab91  test    rcx, rcx
0x1800fab94  jnz     short loc_1800FABC1
0x1800fab96  mov     rcx, [rsp+88h]; this
0x1800fab9e  lea     rbx, aOnecoreBaseApp_18; "onecore\\base\\appmodel\\staterepositor"...
0x1800faba5  mov     edi, 8007139Fh
0x1800fabaa  mov     r8, rbx; unsigned int
0x1800fabad  mov     r9d, edi; char *
0x1800fabb0  mov     edx, 81Dh; void *
0x1800fabb5  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800fabba  mov     edx, 0D2h
0x1800fabbf  jmp     short loc_1800FAB5E
0x1800fabc1  xor     r8d, r8d
0x1800fabc4  lea     rdx, ?sqliteProfileCallback@Logging@StateRepository@@YAXPEAXPEBD_K@Z; StateRepository::Logging::sqliteProfileCallback(void *,char const *,unsigned __int64)
0x1800fabcb  call    sqlite3_profile
0x1800fabd0  mov     [rdi+24h], sil
0x1800fabd4  mov     rcx, rdi; this
0x1800fabd7  call    ?RegisterFunctions@Database@StateRepository@@QEAAJXZ; StateRepository::Database::RegisterFunctions(void)
0x1800fabdc  mov     ebp, eax
0x1800fabde  test    eax, eax
0x1800fabe0  jns     short loc_1800FABEC
0x1800fabe2  mov     edx, 0D5h
0x1800fabe7  jmp     loc_1800FAB0D
0x1800fabec  mov     eax, r14d
0x1800fabef  lea     rbx, aOnecoreBaseApp_18; "onecore\\base\\appmodel\\staterepositor"...
0x1800fabf6  and     eax, 700000h
0x1800fabfb  mov     ebp, 3
0x1800fac00  cmp     eax, 100000h
0x1800fac05  jz      short loc_1800FAC81
0x1800fac07  test    eax, eax
0x1800fac09  jz      short loc_1800FAC45
0x1800fac0b  cmp     eax, 200000h
0x1800fac10  jz      short loc_1800FAC7D
0x1800fac12  cmp     eax, 300000h
0x1800fac17  jz      short loc_1800FAC76
0x1800fac19  mov     rcx, [rsp+88h]; this
0x1800fac21  lea     rax, aUnknownMaskWal; "Unknown mask_walfiles bits, flags=0x%X"
0x1800fac28  mov     dword ptr [rsp+88h+var_60], r14d; char *
0x1800fac2d  mov     r9d, 8000FFFFh; char *
0x1800fac33  mov     r8, rbx; unsigned int
0x1800fac36  mov     qword ptr [rsp+88h+var_68], rax; int
0x1800fac3b  mov     edx, 0C0Fh; void *
0x1800fac40  call    ?Log_HrMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Log_HrMsg(void *,uint,char const *,long,char const *,...)
0x1800fac45  mov     edx, ebp
0x1800fac47  mov     rcx, rdi
0x1800fac4a  call    ?SetWalFilesPersistence@Database@StateRepository@@QEAAJW4WalFilesPersistence@12@@Z; StateRepository::Database::SetWalFilesPersistence(StateRepository::Database::WalFilesPersistence)
0x1800fac4f  mov     r15d, eax
0x1800fac52  test    eax, eax
0x1800fac54  jns     short loc_1800FAC81
0x1800fac56  mov     edx, 0DDh; void *
0x1800fac5b  mov     rcx, [rsp+88h]; this
0x1800fac63  mov     r8, rbx; unsigned int
0x1800fac66  mov     r9d, r15d; char *
0x1800fac69  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800fac6e  mov     eax, r15d
0x1800fac71  jmp     loc_1800FAE34
0x1800fac76  mov     edx, 2
0x1800fac7b  jmp     short loc_1800FAC47
0x1800fac7d  mov     edx, esi
0x1800fac7f  jmp     short loc_1800FAC47
0x1800fac81  lea     r8, aMemory_0; "MEMORY"
0x1800fac88  mov     rcx, rdi; this
0x1800fac8b  lea     rdx, aTempStore; "temp_store"
0x1800fac92  call    ?SetPragma@Database@StateRepository@@QEAAJPEBD0@Z; StateRepository::Database::SetPragma(char const *,char const *)
0x1800fac97  mov     r15d, eax
0x1800fac9a  test    eax, eax
0x1800fac9c  jns     short loc_1800FACA5
0x1800fac9e  mov     edx, 0E0h
0x1800faca3  jmp     short loc_1800FAC5B
0x1800faca5  mov     eax, r14d
0x1800faca8  and     eax, 70h
0x1800facab  cmp     eax, 10h
0x1800facae  jz      loc_1800FAD3D
0x1800facb4  test    eax, eax
0x1800facb6  jz      short loc_1800FAD02
0x1800facb8  cmp     eax, 20h ; ' '
0x1800facbb  jz      short loc_1800FAD39
0x1800facbd  cmp     eax, 30h ; '0'
0x1800facc0  jz      short loc_1800FAD32
0x1800facc2  cmp     eax, 40h ; '@'
0x1800facc5  jz      short loc_1800FAD2E
0x1800facc7  cmp     eax, 50h ; 'P'
0x1800facca  jz      short loc_1800FAD27
0x1800faccc  cmp     eax, 60h ; '`'
0x1800faccf  jz      short loc_1800FAD02
0x1800facd1  cmp     eax, 70h ; 'p'
0x1800facd4  jz      short loc_1800FAD20
0x1800facd6  mov     rcx, [rsp+88h]; this
0x1800facde  lea     rax, aUnknownMaskJou; "Unknown mask_journalmode bits, flags=0x"...
0x1800face5  mov     dword ptr [rsp+88h+var_60], r14d; char *
0x1800facea  mov     r9d, 8000FFFFh; char *
0x1800facf0  mov     r8, rbx; unsigned int
0x1800facf3  mov     qword ptr [rsp+88h+var_68], rax; int
0x1800facf8  mov     edx, 0BB9h; void *
0x1800facfd  call    ?Log_HrMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Log_HrMsg(void *,uint,char const *,long,char const *,...)
0x1800fad02  mov     edx, 5
0x1800fad07  mov     rcx, rdi
0x1800fad0a  call    ?SetJournalMode@Database@StateRepository@@QEAAJW4JournalMode@12@@Z; StateRepository::Database::SetJournalMode(StateRepository::Database::JournalMode)
0x1800fad0f  mov     r15d, eax
0x1800fad12  test    eax, eax
0x1800fad14  jns     short loc_1800FAD3D
0x1800fad16  mov     edx, 0E5h
0x1800fad1b  jmp     loc_1800FAC5B
0x1800fad20  mov     edx, 6
0x1800fad25  jmp     short loc_1800FAD07
0x1800fad27  mov     edx, 4
0x1800fad2c  jmp     short loc_1800FAD07
0x1800fad2e  mov     edx, ebp
0x1800fad30  jmp     short loc_1800FAD07
0x1800fad32  mov     edx, 2
0x1800fad37  jmp     short loc_1800FAD07
0x1800fad39  mov     edx, esi
0x1800fad3b  jmp     short loc_1800FAD07
0x1800fad3d  mov     eax, r14d
0x1800fad40  mov     ecx, 300h
0x1800fad45  and     eax, ecx
0x1800fad47  cmp     eax, 100h
0x1800fad4c  jz      short loc_1800FADAB
0x1800fad4e  test    eax, eax
0x1800fad50  jz      short loc_1800FAD89
0x1800fad52  cmp     eax, 200h
0x1800fad57  jz      short loc_1800FAD89
0x1800fad59  cmp     eax, ecx
0x1800fad5b  jz      short loc_1800FADA4
0x1800fad5d  mov     rcx, [rsp+88h]; this
0x1800fad65  lea     rax, aUnknownMaskLoc; "Unknown mask_lockingmode bits, flags=0x"...
0x1800fad6c  mov     dword ptr [rsp+88h+var_60], r14d; char *
0x1800fad71  mov     r9d, 8000FFFFh; char *
0x1800fad77  mov     r8, rbx; unsigned int
0x1800fad7a  mov     qword ptr [rsp+88h+var_68], rax; int
0x1800fad7f  mov     edx, 0C22h; void *
0x1800fad84  call    ?Log_HrMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Log_HrMsg(void *,uint,char const *,long,char const *,...)
0x1800fad89  mov     edx, esi
0x1800fad8b  mov     rcx, rdi
0x1800fad8e  call    ?SetLockingMode@Database@StateRepository@@QEAAJW4LockingMode@12@@Z; StateRepository::Database::SetLockingMode(StateRepository::Database::LockingMode)
0x1800fad93  mov     r15d, eax
0x1800fad96  test    eax, eax
0x1800fad98  jns     short loc_1800FADAB
0x1800fad9a  mov     edx, 0EBh
0x1800fad9f  jmp     loc_1800FAC5B
0x1800fada4  mov     edx, 2
0x1800fada9  jmp     short loc_1800FAD8B
0x1800fadab  mov     eax, r14d
0x1800fadae  and     eax, 7000h
0x1800fadb3  cmp     eax, 1000h
0x1800fadb8  jz      short loc_1800FAE32
0x1800fadba  test    eax, eax
0x1800fadbc  jz      short loc_1800FAE18
0x1800fadbe  cmp     eax, 2000h
0x1800fadc3  jz      short loc_1800FAE16
0x1800fadc5  cmp     eax, 3000h
0x1800fadca  jz      short loc_1800FAE0F
  ... truncated ...
```
