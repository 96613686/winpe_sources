# StateRepository::Repository::OpenDatabaseFromCache(StateRepository::Partition,StateRepository::Repository::OpenFlags,StateRepository::Database &)

- ea: `0x1800171c0`
- end: `0x18001791a`
- name: `?OpenDatabaseFromCache@Repository@StateRepository@@SAJW4Partition@2@W4OpenFlags@12@AEAVDatabase@2@@Z`
- size: `1882`
- prototype: `__int64 __fastcall(int, unsigned __int64, __int64)`
- caller_count: `1183`
- callee_count: `17`
- tags: `file_ops, registry_config, broker_com_uri`

## callers

- `0x18000347c`
- `0x1800037e0`
- `0x1800041c0`
- `0x180004650`
- `0x180004a70`
- `0x180004eac`
- `0x180009ba0`
- `0x180009fb8`
- `0x18000a230`
- `0x18000a980`
- `0x18000b030`
- `0x18000b3c0`
- `0x18000b780`
- `0x18000bb70`
- `0x18000e940`
- `0x18000eef0`
- `0x18000f090`
- `0x18000f7b0`
- `0x180011280`
- `0x180012c20`
- `0x180014c30`
- `0x1800160d0`
- `0x18001d710`
- `0x18001ea80`
- `0x180022698`
- `0x18002d220`
- `0x18002d8e0`
- `0x18002e050`
- `0x18002ea40`
- `0x180030234`
- `0x180030f90`
- `0x18003e220`
- `0x18003e940`
- `0x1800400a0`
- `0x180040e40`
- `0x180051ad0`
- `0x18005feb0`
- `0x1800628b0`
- `0x180063c50`
- `0x180066e10`
- `0x180067100`
- `0x180067620`
- `0x1800683a8`
- `0x180068810`
- `0x180068fcc`
- `0x18006d650`
- `0x18006f050`
- `0x180070618`
- `0x180070a70`
- `0x180071c10`

## callees

- `0x1800171c0`
- `0x180017a58`
- `0x180018174`
- `0x1800183a0`
- `0x180018400`
- `0x18001843c`
- `0x18001a9e0`
- `0x18001d4c0`
- `0x180053f98`
- `0x180053ff0`
- `0x1800540dc`
- `0x180078ca0`
- `0x1800ad7dc`
- `0x18018f650`
- `0x18018fb5c`
- `0x180190234`
- `0x18027719c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800174e7`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800174e7`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18001746a`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18001746a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001767b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001783d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001767b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001783d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001720f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180017429`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001720f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180017429`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x1800173e9`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x1800178c5`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x1800173e9`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x1800178c5`

## string_xrefs

- `0x1800174a5`: `onecore\base\appmodel\staterepository\dataaccesslayer\databasecache.cpp`
- `0x18001759b`: `onecore\base\appmodel\staterepository\dataaccesslayer\databasecache.cpp`
- `0x1800175f3`: `onecore\base\appmodel\staterepository\dataaccesslayer\databasecache.cpp`
- `0x1800176ac`: `onecore\base\appmodel\staterepository\dataaccesslayer\databasecache.cpp`
- `0x1800172fc`: `onecore\base\appmodel\staterepository\dataaccesslayer\repository.cpp`
- `0x180017412`: `onecore\base\appmodel\staterepository\dataaccesslayer\repository.cpp`
- `0x180017647`: `onecore\base\appmodel\staterepository\dataaccesslayer\repository.cpp`
- `0x1800176ea`: `onecore\base\appmodel\staterepository\dataaccesslayer\repository.cpp`
- `0x180017736`: `onecore\base\appmodel\staterepository\dataaccesslayer\repository.cpp`
- `0x180017777`: `onecore\base\appmodel\staterepository\dataaccesslayer\repository.cpp`
- `0x1800177b8`: `onecore\base\appmodel\staterepository\dataaccesslayer\repository.cpp`
- `0x1800177da`: `onecore\base\appmodel\staterepository\dataaccesslayer\repository.cpp`
- `0x1800177fe`: `onecore\base\appmodel\staterepository\dataaccesslayer\repository.cpp`
- `0x1800178f5`: `onecore\base\appmodel\staterepository\dataaccesslayer\repository.cpp`
- `0x180017889`: `onecore\base\appmodel\StateRepository\DataAccessLayer\Utf8String.hpp`

## pseudocode

```c
__int64 __fastcall StateRepository::Repository::OpenDatabaseFromCache(int a1, unsigned __int64 a2, __int64 a3)
{
  void *v5; // rbx
  int v6; // ebx
  __int16 *v7; // rdi
  __int64 v8; // rsi
  unsigned __int64 v9; // rsi
  unsigned __int64 v10; // rax
  _WORD *v11; // rax
  _WORD *v12; // rdx
  __int64 v13; // rcx
  __int16 v14; // ax
  _WORD *v15; // rcx
  __int64 v16; // r9
  int v17; // ecx
  int v18; // ecx
  int v19; // ecx
  void *v21; // rcx
  unsigned int v22; // edi
  const WCHAR *v23; // rsi
  char *v24; // rsi
  int v25; // eax
  int v26; // edi
  StateRepository::DatabaseCache *v27; // rcx
  StateRepository::DatabaseCache *v28; // rsi
  StateRepository::Time *v29; // rcx
  unsigned __int64 UnbiasedInterruptTimeAsMSec; // rax
  unsigned int v31; // edx
  unsigned __int64 v32; // rdi
  __int64 v33; // rcx
  void *v34; // rcx
  int v35; // eax
  unsigned int v36; // ebx
  unsigned __int64 v37; // r8
  int v38; // eax
  unsigned __int64 v39; // r15
  unsigned __int64 i; // r14
  _QWORD *v41; // rcx
  int v42; // eax
  __int64 v43; // rdx
  signed int LastError; // eax
  int v45; // eax
  int Settings; // eax
  unsigned int v47; // ebx
  unsigned __int64 v48; // rdx
  int v49; // eax
  unsigned int v50; // ebx
  unsigned __int64 v51; // rdx
  unsigned __int64 v52; // rdx
  unsigned __int64 v53; // rdx
  unsigned __int64 v54; // rdx
  void *v55; // rax
  unsigned __int64 v56; // rdx
  void *v57; // rcx
  unsigned __int64 v58; // rdx
  int lpMultiByteStr; // [rsp+20h] [rbp-E0h]
  int lpMultiByteStra; // [rsp+20h] [rbp-E0h]
  int lpMultiByteStrb; // [rsp+20h] [rbp-E0h]
  int lpMultiByteStrc; // [rsp+20h] [rbp-E0h]
  const char *lpDefaultChar; // [rsp+30h] [rbp-D0h]
  void *v64; // [rsp+40h] [rbp-C0h] BYREF
  int v65; // [rsp+48h] [rbp-B8h] BYREF
  char *v66; // [rsp+50h] [rbp-B0h]
  void *v67; // [rsp+58h] [rbp-A8h]
  CHAR MultiByteStr[272]; // [rsp+60h] [rbp-A0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+1C8h] [rbp+C8h]

  v5 = 0;
  v64 = 0;
  v65 = 0;
  if ( a1 == 1 )
  {
    v6 = dword_1804E01A8;
    if ( v6 == GetCurrentThreadId() )
      goto LABEL_6;
    v64 = *(void **)&qword_1804E01A0;
    if ( (*(_BYTE *)(&qword_1804E01A0 + 1) & 2) != 0 )
    {
      v22 = -2147023781;
    }
    else if ( (BYTE4(v64) & (unsigned __int8)a1) != 0 )
    {
      v22 = -2140733424;
    }
    else
    {
      if ( !(_DWORD)v64 )
      {
LABEL_6:
        v7 = (__int16 *)StateRepository::Globals::PartitionSettings::machine;
        v8 = -1;
        do
          ++v8;
        while ( *(_WORD *)(StateRepository::Globals::PartitionSettings::machine + 2 * v8) );
        v9 = v8 + 1;
        v10 = 2 * v9;
        if ( !is_mul_ok(v9, 2u) )
          v10 = -1;
        v11 = operator new[](v10, (const struct std::nothrow_t *)&std::nothrow);
        v5 = v11;
        if ( v11 )
        {
          if ( v9 )
          {
            if ( v9 > 0x7FFFFFFF )
            {
              v16 = 2147942487LL;
              *v11 = 0;
            }
            else
            {
              v13 = 2147483646;
              v12 = v11;
              do
              {
                if ( !v13 )
                  break;
                v14 = *v7;
                if ( !*v7 )
                  break;
                ++v7;
                *v12++ = v14;
                --v13;
                --v9;
              }
              while ( v9 );
              v15 = v12 - 1;
              if ( v9 )
                v15 = v12;
              *v15 = 0;
              v16 = 2147942522LL;
              if ( v9 )
                v16 = 0;
            }
          }
          else
          {
            v16 = 2147942487LL;
          }
          if ( (int)v16 < 0 )
            wil::details::in1diag3::_FailFast_Hr(
              retaddr,
              (void *)0x6F5,
              (unsigned int)"onecore\\base\\appmodel\\staterepository\\dataaccesslayer\\repository.cpp",
              (const char *)v16,
              lpMultiByteStr);
          v65 = dword_1804E0758;
          operator delete(0, (unsigned __int64)v12);
          goto LABEL_34;
        }
        v22 = -2147024882;
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x6F4,
          (unsigned int)"onecore\\base\\appmodel\\staterepository\\dataaccesslayer\\repository.cpp",
          (const char *)0x8007000ELL,
          lpMultiByteStr);
        operator delete(0, v53);
LABEL_87:
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x28A,
          (unsigned int)"onecore\\base\\appmodel\\staterepository\\dataaccesslayer\\repository.cpp",
          (const char *)v22,
          lpMultiByteStrc);
        operator delete(0, v54);
        return v22;
      }
      v22 = -2140733434;
    }
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x6EC,
      (unsigned int)"onecore\\base\\appmodel\\staterepository\\dataaccesslayer\\repository.cpp",
      (const char *)v22,
      lpMultiByteStr);
    goto LABEL_87;
  }
  v17 = a1 - 2;
  if ( v17 )
  {
    v18 = v17 - 1;
    if ( !v18 )
    {
      v23 = L":memory:";
LABEL_35:
      v67 = 0;
      memset_0(MultiByteStr, 0, 0x104u);
      v66 = MultiByteStr;
      if ( WideCharToMultiByte(0xFDE9u, 0, v23, -1, MultiByteStr, 260, 0, 0) )
      {
LABEL_36:
        v24 = v66;
        v25 = StateRepository::Database::Close((StateRepository::Database *)a3);
        if ( v25 < 0 )
          wil::details::in1diag3::_Log_Hr(
            retaddr,
            (void *)0x2FC,
            (unsigned int)"onecore\\base\\appmodel\\staterepository\\dataaccesslayer\\repository.cpp",
            (const char *)(unsigned int)v25,
            lpMultiByteStra);
        v26 = dword_1804E01A8;
        if ( v26 == GetCurrentThreadId() )
        {
LABEL_42:
          AcquireSRWLockExclusive(&StateRepository::DatabaseCacheSingleton::s_lock);
          StateRepository::DatabaseCache::Get(v27, v24, (struct StateRepository::Database *)a3);
          v28 = StateRepository::DatabaseCacheSingleton::s_cache;
          LODWORD(lpDefaultChar) = 0;
          wil::details::in1diag3::Log_HrIfMsg(
            retaddr,
            (void *)0x83,
            (unsigned int)"onecore\\base\\appmodel\\staterepository\\dataaccesslayer\\databasecache.cpp",
            (const char *)0x8000FFFFLL,
            0,
            (bool)"policy=%d",
            lpDefaultChar);
          UnbiasedInterruptTimeAsMSec = StateRepository::Time::QueryUnbiasedInterruptTimeAsMSec(v29);
          v32 = UnbiasedInterruptTimeAsMSec;
          v33 = *((_QWORD *)v28 + 6);
          if ( !v33
            || (v31 = UnbiasedInterruptTimeAsMSec - v33,
                UnbiasedInterruptTimeAsMSec - v33 >= (unsigned int)dword_1804E0178) )
          {
            while ( 1 )
            {
              v37 = *((_QWORD *)v28 + 2);
              if ( !v37
                || v32 - *(_QWORD *)(**(_QWORD **)v28 + 128LL) <= StateRepository::Globals::PolicySettings::normal )
              {
                break;
              }
              v38 = Common::Array<StateRepository::DatabaseCacheEntry,Common::ContainerOperations<StateRepository::DatabaseCacheEntry,StateRepository::DatabaseCacheEntry>,char,Common::ContainerOperations<char,StateRepository::DatabaseCacheEntry>,Common::ArrayOperations<StateRepository::DatabaseCacheEntry,StateRepository::DatabaseCacheEntry>>::DeleteAt(v28);
              if ( v38 < 0 )
                wil::details::in1diag3::_Log_Hr(
                  retaddr,
                  (void *)0xA4,
                  (unsigned int)"onecore\\base\\appmodel\\staterepository\\dataaccesslayer\\databasecache.cpp",
                  (const char *)(unsigned int)v38,
                  lpMultiByteStrb);
            }
            if ( v37 > *(&StateRepository::Globals::PolicySettings::normal + 1) )
            {
              v45 = Common::Array<StateRepository::DatabaseCacheEntry,Common::ContainerOperations<StateRepository::DatabaseCacheEntry,StateRepository::DatabaseCacheEntry>,char,Common::ContainerOperations<char,StateRepository::DatabaseCacheEntry>,Common::ArrayOperations<StateRepository::DatabaseCacheEntry,StateRepository::DatabaseCacheEntry>>::DeleteRange(
                      (__int64)v28,
                      v31,
                      v37 - *(&StateRepository::Globals::PolicySettings::normal + 2));
              if ( v45 < 0 )
                wil::details::in1diag3::_Log_Hr(
                  retaddr,
                  (void *)0xAD,
                  (unsigned int)"onecore\\base\\appmodel\\staterepository\\dataaccesslayer\\databasecache.cpp",
                  (const char *)(unsigned int)v45,
                  lpMultiByteStrb);
            }
            v39 = *((_QWORD *)v28 + 2);
            for ( i = 0; i < v39; ++i )
            {
              if ( i >= *((_QWORD *)v28 + 2) )
                v41 = 0;
              else
                v41 = *(_QWORD **)(*(_QWORD *)v28 + 8 * i);
              if ( *v41 )
                v42 = StateRepository::StatementCache::GC(
                        (StateRepository::StatementCache *)(v41 + 5),
                        (const struct StateRepository::Globals::PolicySettings *)&StateRepository::Globals::PolicySettings::normal,
                        v32);
              else
                v42 = 0;
              if ( v42 < 0 )
                wil::details::in1diag3::_Log_Hr(
                  retaddr,
                  (void *)0xB7,
                  (unsigned int)"onecore\\base\\appmodel\\staterepository\\dataaccesslayer\\databasecache.cpp",
                  (const char *)(unsigned int)v42,
                  lpMultiByteStrb);
            }
            *((_QWORD *)v28 + 6) = v32;
          }
          ReleaseSRWLockExclusive(&StateRepository::DatabaseCacheSingleton::s_lock);
          if ( *(_QWORD *)a3 )
          {
            *(_DWORD *)(a3 + 16) = a1;
            *(_QWORD *)(a3 + 8) = 0;
            v21 = v67;
            v67 = 0;
            if ( v21 )
              operator delete(v21, v58);
            v22 = 0;
            goto LABEL_31;
          }
          v22 = StateRepository::Repository::OpenDatabaseFromDisk((BlockRequests *)v66, a1, v65 | 0x100u, a3);
          v34 = v67;
          v67 = 0;
          if ( !v34 )
          {
LABEL_31:
            operator delete(v5, v58);
            return v22;
          }
LABEL_46:
          operator delete(v34, v58);
          goto LABEL_31;
        }
        v64 = *(void **)&qword_1804E01A0;
        if ( (*(_BYTE *)(&qword_1804E01A0 + 1) & 2) != 0 )
        {
          v22 = -2147023781;
        }
        else if ( (BYTE4(v64) & 1) != 0 )
        {
          v22 = -2140733424;
        }
        else
        {
          if ( !(_DWORD)v64 )
            goto LABEL_42;
          v22 = -2140733434;
        }
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x2FE,
          (unsigned int)"onecore\\base\\appmodel\\staterepository\\dataaccesslayer\\repository.cpp",
          (const char *)v22,
          lpMultiByteStra);
        v43 = 727;
LABEL_68:
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)v43,
          (unsigned int)"onecore\\base\\appmodel\\staterepository\\dataaccesslayer\\repository.cpp",
          (const char *)v22,
          lpMultiByteStra);
        v34 = v67;
        v67 = 0;
        if ( !v34 )
          goto LABEL_31;
        goto LABEL_46;
      }
      LastError = GetLastError();
      v22 = LastError;
      if ( LastError == 122 )
      {
        v55 = operator new[](0, (const struct std::nothrow_t *)&std::nothrow);
        v57 = v67;
        v67 = v55;
        if ( v57 )
        {
          operator delete(v57, v56);
          v55 = v67;
        }
        if ( !v55 )
        {
          v22 = -2147024882;
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x25,
            (unsigned int)"onecore\\base\\appmodel\\StateRepository\\DataAccessLayer\\Utf8String.hpp",
            (const char *)0x8007000ELL,
            lpMultiByteStra);
          goto LABEL_67;
        }
        v66 = (char *)v55;
        if ( WideCharToMultiByte(0xFDE9u, 0, v23, -1, (LPSTR)v55, 0, 0, 0) )
          goto LABEL_36;
        LastError = GetLastError();
        v22 = LastError;
        if ( LastError > 0 )
          goto LABEL_65;
      }
      else if ( LastError > 0 )
      {
LABEL_65:
        v22 = (unsigned __int16)LastError | 0x80070000;
      }
      if ( (v22 & 0x80000000) == 0 )
        goto LABEL_36;
LABEL_67:
      v43 = 722;
      goto LABEL_68;
    }
    v19 = v18 - 1;
    if ( v19 )
    {
      if ( v19 != 1 )
      {
        operator delete(0, a2);
        return 2147942487LL;
      }
      Settings = StateRepository::Repository::GetSettings(5, &v64, &v65);
      v47 = Settings;
      if ( Settings < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x2A2,
          (unsigned int)"onecore\\base\\appmodel\\staterepository\\dataaccesslayer\\repository.cpp",
          (const char *)(unsigned int)Settings,
          lpMultiByteStr);
        operator delete(v64, v48);
        return v47;
      }
LABEL_48:
      v5 = v64;
LABEL_34:
      v23 = (const WCHAR *)v5;
      goto LABEL_35;
    }
    v49 = StateRepository::Repository::GetSettings(4, &v64, &v65);
    v50 = v49;
    if ( v49 >= 0 )
      goto LABEL_48;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x29C,
      (unsigned int)"onecore\\base\\appmodel\\staterepository\\dataaccesslayer\\repository.cpp",
      (const char *)(unsigned int)v49,
      lpMultiByteStr);
    operator delete(v64, v51);
    return v50;
  }
  else
  {
    v35 = StateRepository::Repository::GetSettings(2, &v64, &v65);
    v36 = v35;
    if ( v35 >= 0 )
      goto LABEL_48;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x290,
      (unsigned int)"onecore\\base\\appmodel\\staterepository\\dataaccesslayer\\repository.cpp",
      (const char *)(unsigned int)v35,
      lpMultiByteStr);
    operator delete(v64, v52);
    return v36;
  }
}

```

## disassembly

```asm
0x1800171c0  push    rbp
0x1800171c2  push    rbx
0x1800171c3  push    rsi
0x1800171c4  push    rdi
0x1800171c5  push    r12
0x1800171c7  push    r13
0x1800171c9  push    r14
0x1800171cb  push    r15
0x1800171cd  lea     rbp, [rsp-88h]
0x1800171d5  sub     rsp, 188h
0x1800171dc  mov     rax, cs:__security_cookie
0x1800171e3  xor     rax, rsp
0x1800171e6  mov     [rbp+0C0h+var_50], rax
0x1800171ea  mov     r13, r8
0x1800171ed  mov     r12d, ecx
0x1800171f0  xor     r15d, r15d
0x1800171f3  mov     ebx, r15d
0x1800171f6  mov     [rsp+1C0h+var_180], rbx
0x1800171fb  mov     [rsp+1C0h+var_178], r15d
0x180017200  cmp     ecx, 1
0x180017203  jnz     loc_18001730E
0x180017209  mov     ebx, cs:dword_1804E01A8
0x18001720f  call    cs:__imp_GetCurrentThreadId
0x180017215  cmp     ebx, eax
0x180017217  jz      short loc_18001724A
0x180017219  mov     rax, cs:qword_1804E01A0
0x180017220  mov     [rsp+1C0h+var_180], rax
0x180017225  mov     eax, dword ptr [rsp+1C0h+var_180+4]
0x180017229  test    al, 2
0x18001722b  jnz     loc_18001779B
0x180017231  mov     eax, dword ptr [rsp+1C0h+var_180+4]
0x180017235  test    r12b, al
0x180017238  jnz     loc_1800177A2
0x18001723e  mov     eax, dword ptr [rsp+1C0h+var_180]
0x180017242  test    eax, eax
0x180017244  jnz     loc_1800177A9
0x18001724a  mov     rdi, cs:?machine@PartitionSettings@Globals@StateRepository@@0U123@A; StateRepository::Globals::PartitionSettings StateRepository::Globals::PartitionSettings::machine
0x180017251  mov     r14, 0FFFFFFFFFFFFFFFFh
0x180017258  mov     rsi, r14
0x18001725b  nop     dword ptr [rax+rax+00h]
0x180017260  inc     rsi
0x180017263  cmp     word ptr [rdi+rsi*2], 0
0x180017268  jnz     short loc_180017260
0x18001726a  inc     rsi
0x18001726d  mov     eax, 2
0x180017272  mul     rsi
0x180017275  cmovb   rax, r14
0x180017279  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180017280  mov     rcx, rax; unsigned __int64
0x180017283  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x180017288  mov     rbx, rax
0x18001728b  test    rax, rax
0x18001728e  jz      loc_1800177CB
0x180017294  test    rsi, rsi
0x180017297  jz      loc_180017825
0x18001729d  cmp     rsi, 7FFFFFFFh
0x1800172a4  ja      loc_18001781D
0x1800172aa  mov     ecx, 7FFFFFFEh
0x1800172af  mov     rdx, rax
0x1800172b2  test    rcx, rcx
0x1800172b5  jz      short loc_1800172D3
0x1800172b7  movzx   eax, word ptr [rdi]
0x1800172ba  test    ax, ax
0x1800172bd  jz      short loc_1800172D3
0x1800172bf  add     rdi, 2
0x1800172c3  mov     [rdx], ax
0x1800172c6  add     rdx, 2; unsigned __int64
0x1800172ca  dec     rcx
0x1800172cd  sub     rsi, 1
0x1800172d1  jnz     short loc_1800172B2
0x1800172d3  lea     rcx, [rdx-2]
0x1800172d7  test    rsi, rsi
0x1800172da  cmovnz  rcx, rdx
0x1800172de  mov     [rcx], r15w
0x1800172e2  mov     r9d, 8007007Ah
0x1800172e8  cmovnz  r9d, r15d; char *
0x1800172ec  mov     rcx, [rbp+0C8h]; this
0x1800172f3  test    r9d, r9d
0x1800172f6  jns     loc_18001738A
0x1800172fc  lea     r8, aOnecoreBaseApp_79; "onecore\\base\\appmodel\\staterepositor"...
0x180017303  mov     edx, 6F5h; void *
0x180017308  call    ?_FailFast_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_FailFast_Hr(void *,uint,char const *,long)
0x18001730e  sub     ecx, 2
0x180017311  jz      loc_180017532
0x180017317  sub     ecx, 1
0x18001731a  jz      loc_18001775A
0x180017320  sub     ecx, 1
0x180017323  jz      loc_18001770E
0x180017329  cmp     ecx, 1
0x18001732c  jz      loc_1800176C2
0x180017332  xor     ecx, ecx; void *
0x180017334  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180017339  nop
0x18001733a  mov     eax, 80070057h
0x18001733f  jmp     short loc_18001736A
0x180017341  mov     [r13+10h], r12d
0x180017345  mov     [r13+8], r15
0x180017349  mov     rcx, [rsp+1C0h+var_168]; void *
0x18001734e  mov     [rsp+1C0h+var_168], r15
0x180017353  test    rcx, rcx
0x180017356  jnz     loc_180017910
0x18001735c  mov     edi, r15d
0x18001735f  mov     rcx, rbx; void *
0x180017362  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180017367  nop
0x180017368  mov     eax, edi
0x18001736a  mov     rcx, [rbp+0C0h+var_50]
0x18001736e  xor     rcx, rsp; StackCookie
0x180017371  call    __security_check_cookie
0x180017376  add     rsp, 188h
0x18001737d  pop     r15
0x18001737f  pop     r14
0x180017381  pop     r13
0x180017383  pop     r12
0x180017385  pop     rdi
0x180017386  pop     rsi
0x180017387  pop     rbx
0x180017388  pop     rbp
0x180017389  retn
0x18001738a  mov     eax, cs:dword_1804E0758
0x180017390  mov     [rsp+1C0h+var_178], eax
0x180017394  xor     ecx, ecx; void *
0x180017396  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18001739b  nop
0x18001739c  mov     rsi, rbx
0x18001739f  mov     [rsp+1C0h+var_168], r15
0x1800173a4  xor     edx, edx; Val
0x1800173a6  mov     r8d, 104h; Size
0x1800173ac  lea     rcx, [rsp+1C0h+MultiByteStr]; void *
0x1800173b1  call    memset_0
0x1800173b6  lea     rax, [rsp+1C0h+MultiByteStr]
0x1800173bb  mov     [rsp+1C0h+var_170], rax
0x1800173c0  mov     [rsp+1C0h+lpUsedDefaultChar], r15; lpUsedDefaultChar
0x1800173c5  mov     [rsp+1C0h+lpDefaultChar], r15; lpDefaultChar
0x1800173ca  mov     [rsp+1C0h+cbMultiByte], 104h; cbMultiByte
0x1800173d2  lea     rax, [rsp+1C0h+MultiByteStr]
0x1800173d7  mov     [rsp+1C0h+lpMultiByteStr], rax; int
0x1800173dc  mov     r9d, r14d; cchWideChar
0x1800173df  mov     r8, rsi; lpWideCharStr
0x1800173e2  xor     edx, edx; dwFlags
0x1800173e4  mov     ecx, 0FDE9h; CodePage
0x1800173e9  call    cs:__imp_WideCharToMultiByte
0x1800173ef  test    eax, eax
0x1800173f1  jz      loc_18001783D
0x1800173f7  mov     rsi, [rsp+1C0h+var_170]
0x1800173fc  mov     rcx, r13; this
0x1800173ff  call    ?Close@Database@StateRepository@@QEAAJXZ; StateRepository::Database::Close(void)
0x180017404  mov     rcx, [rbp+0C8h]; this
0x18001740b  test    eax, eax
0x18001740d  jns     short loc_180017423
0x18001740f  mov     r9d, eax; char *
0x180017412  lea     r8, aOnecoreBaseApp_79; "onecore\\base\\appmodel\\staterepositor"...
0x180017419  mov     edx, 2FCh; void *
0x18001741e  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180017423  mov     edi, cs:dword_1804E01A8
0x180017429  call    cs:__imp_GetCurrentThreadId
0x18001742f  cmp     edi, eax
0x180017431  jz      short loc_180017463
0x180017433  mov     rax, cs:qword_1804E01A0
0x18001743a  mov     [rsp+1C0h+var_180], rax
0x18001743f  mov     eax, dword ptr [rsp+1C0h+var_180+4]
0x180017443  test    al, 2
0x180017445  jnz     loc_1800178D8
0x18001744b  mov     eax, dword ptr [rsp+1C0h+var_180+4]
0x18001744f  test    al, 1
0x180017451  jnz     loc_1800178DF
0x180017457  mov     eax, dword ptr [rsp+1C0h+var_180]
0x18001745b  test    eax, eax
0x18001745d  jnz     loc_1800178E6
0x180017463  lea     rcx, ?s_lock@DatabaseCacheSingleton@StateRepository@@0Vsrwlock@wil@@A; SRWLock
0x18001746a  call    cs:__imp_AcquireSRWLockExclusive
0x180017470  mov     r8, r13; struct StateRepository::Database *
0x180017473  mov     rdx, rsi; char *
0x180017476  call    ?Get@DatabaseCache@StateRepository@@QEAAPEAVDatabase@2@PEBDAEAV32@@Z; StateRepository::DatabaseCache::Get(char const *,StateRepository::Database &)
0x18001747b  mov     rsi, cs:?s_cache@DatabaseCacheSingleton@StateRepository@@0PEAVDatabaseCache@2@EA; StateRepository::DatabaseCache * StateRepository::DatabaseCacheSingleton::s_cache
0x180017482  mov     rcx, [rbp+0C8h]; this
0x180017489  mov     dword ptr [rsp+1C0h+lpDefaultChar], r15d; char *
0x18001748e  lea     rax, aPolicyD; "policy=%d"
0x180017495  mov     qword ptr [rsp+1C0h+cbMultiByte], rax; bool
0x18001749a  mov     byte ptr [rsp+1C0h+lpMultiByteStr], 0; int
0x18001749f  mov     r9d, 8000FFFFh; char *
0x1800174a5  lea     r8, aOnecoreBaseApp_244; "onecore\\base\\appmodel\\staterepositor"...
0x1800174ac  mov     edx, 83h; void *
0x1800174b1  call    ?Log_HrIfMsg@in1diag3@details@wil@@YA_NPEAXIPEBDJ_N1ZZ; wil::details::in1diag3::Log_HrIfMsg(void *,uint,char const *,long,bool,char const *,...)
0x1800174b6  call    ?QueryUnbiasedInterruptTimeAsMSec@Time@StateRepository@@YA_KXZ; StateRepository::Time::QueryUnbiasedInterruptTimeAsMSec(void)
0x1800174bb  mov     rdi, rax
0x1800174be  mov     rcx, [rsi+30h]
0x1800174c2  test    rcx, rcx
0x1800174c5  jz      loc_180017561
0x1800174cb  mov     rdx, rax
0x1800174ce  sub     rdx, rcx
0x1800174d1  mov     ecx, cs:dword_1804E0178
0x1800174d7  cmp     rdx, rcx
0x1800174da  jnb     loc_180017561
0x1800174e0  lea     rcx, ?s_lock@DatabaseCacheSingleton@StateRepository@@0Vsrwlock@wil@@A; SRWLock
0x1800174e7  call    cs:__imp_ReleaseSRWLockExclusive
0x1800174ed  nop
0x1800174ee  cmp     qword ptr [r13+0], 0
0x1800174f3  jnz     loc_180017341
0x1800174f9  mov     r8d, [rsp+1C0h+var_178]
0x1800174fe  bts     r8d, 8
0x180017503  mov     r9, r13
0x180017506  mov     edx, r12d
0x180017509  mov     rcx, [rsp+1C0h+var_170]
0x18001750e  call    ?OpenDatabaseFromDisk@Repository@StateRepository@@CAJPEBDW4Partition@2@W4Options@12@AEAVDatabase@2@@Z; StateRepository::Repository::OpenDatabaseFromDisk(char const *,StateRepository::Partition,StateRepository::Repository::Options,StateRepository::Database &)
0x180017513  mov     edi, eax
0x180017515  mov     rcx, [rsp+1C0h+var_168]; void *
0x18001751a  mov     [rsp+1C0h+var_168], r15
0x18001751f  test    rcx, rcx
0x180017522  jz      loc_18001735F
0x180017528  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18001752d  jmp     loc_18001735F
0x180017532  lea     r8, [rsp+1C0h+var_178]
0x180017537  lea     rdx, [rsp+1C0h+var_180]
0x18001753c  mov     ecx, 2
0x180017541  call    ?GetSettings@Repository@StateRepository@@SAJW4Partition@2@PEAPEAGPEAW4Options@12@@Z; StateRepository::Repository::GetSettings(StateRepository::Partition,ushort * *,StateRepository::Repository::Options *)
0x180017546  mov     ebx, eax
0x180017548  test    eax, eax
0x18001754a  js      loc_18001776D
0x180017550  mov     rbx, [rsp+1C0h+var_180]
0x180017555  mov     r14, 0FFFFFFFFFFFFFFFFh
0x18001755c  jmp     loc_18001739C
0x180017561  mov     r8, [rsi+10h]
0x180017565  test    r8, r8
0x180017568  jz      short loc_1800175AE
0x18001756a  mov     rax, [rsi]
0x18001756d  mov     rax, [rax]
0x180017570  mov     rcx, rdi
0x180017573  sub     rcx, [rax+80h]
0x18001757a  mov     eax, dword ptr cs:?normal@PolicySettings@Globals@StateRepository@@0U123@A; StateRepository::Globals::PolicySettings StateRepository::Globals::PolicySettings::normal
0x180017580  cmp     rcx, rax
0x180017583  jbe     short loc_1800175AE
0x180017585  mov     rcx, rsi
0x180017588  call    ?DeleteAt@?$Array@VDatabaseCacheEntry@StateRepository@@V?$ContainerOperations@VDatabaseCacheEntry@StateRepository@@V12@@Common@@DV?$ContainerOperations@DVDatabaseCacheEntry@StateRepository@@@4@V?$ArrayOperations@VDatabaseCacheEntry@StateRepository@@V12@@4@@Common@@QEAAJ_K@Z; Common::Array<StateRepository::DatabaseCacheEntry,Common::ContainerOperations<StateRepository::DatabaseCacheEntry,StateRepository::DatabaseCacheEntry>,char,Common::ContainerOperations<char,StateRepository::DatabaseCacheEntry>,Common::ArrayOperations<StateRepository::DatabaseCacheEntry,StateRepository::DatabaseCacheEntry>>::DeleteAt(unsigned __int64)
0x18001758d  test    eax, eax
0x18001758f  jns     short loc_180017561
0x180017591  mov     rcx, [rbp+0C8h]; this
0x180017598  mov     r9d, eax; char *
0x18001759b  lea     r8, aOnecoreBaseApp_244; "onecore\\base\\appmodel\\staterepositor"...
0x1800175a2  mov     edx, 0A4h; void *
0x1800175a7  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1800175ac  jmp     short loc_180017561
0x1800175ae  mov     eax, dword ptr cs:?normal@PolicySettings@Globals@StateRepository@@0U123@A+4; StateRepository::Globals::PolicySettings StateRepository::Globals::PolicySettings::normal
0x1800175b4  cmp     r8, rax
0x1800175b7  ja      loc_180017689
0x1800175bd  mov     r15, [rsi+10h]
0x1800175c1  xor     r14d, r14d
0x1800175c4  test    r15, r15
0x1800175c7  jz      short loc_18001760C
0x1800175c9  nop     dword ptr [rax+00000000h]
0x1800175d0  cmp     r14, [rsi+10h]
0x1800175d4  jnb     short loc_18001762D
0x1800175d6  mov     rax, [rsi]
0x1800175d9  mov     rcx, [rax+r14*8]
0x1800175dd  cmp     qword ptr [rcx], 0
0x1800175e1  jnz     short loc_180017618
0x1800175e3  xor     eax, eax
0x1800175e5  mov     rcx, [rbp+0C8h]; this
0x1800175ec  test    eax, eax
0x1800175ee  jns     short loc_180017604
0x1800175f0  mov     r9d, eax; char *
0x1800175f3  lea     r8, aOnecoreBaseApp_244; "onecore\\base\\appmodel\\staterepositor"...
0x1800175fa  mov     edx, 0B7h; void *
0x1800175ff  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180017604  inc     r14
0x180017607  cmp     r14, r15
0x18001760a  jb      short loc_1800175D0
0x18001760c  mov     [rsi+30h], rdi
0x180017610  xor     r15d, r15d
0x180017613  jmp     loc_1800174E0
0x180017618  add     rcx, 28h ; '('; this
0x18001761c  mov     r8, rdi; unsigned __int64
0x18001761f  lea     rdx, ?normal@PolicySettings@Globals@StateRepository@@0U123@A; struct StateRepository::Globals::PolicySettings *
0x180017626  call    ?GC@StatementCache@StateRepository@@QEAAJAEBUPolicySettings@Globals@2@_K@Z; StateRepository::StatementCache::GC(StateRepository::Globals::PolicySettings const &,unsigned __int64)
0x18001762b  jmp     short loc_1800175E5
0x18001762d  xor     ecx, ecx
0x18001762f  jmp     short loc_1800175DD
0x180017631  movzx   edi, ax
0x180017634  or      edi, 80070000h
0x18001763a  test    edi, edi
0x18001763c  jns     loc_1800173F7
0x180017642  mov     edx, 2D2h; void *
0x180017647  lea     r8, aOnecoreBaseApp_79; "onecore\\base\\appmodel\\staterepositor"...
0x18001764e  mov     r9d, edi; char *
0x180017651  mov     rcx, [rbp+0C8h]; this
0x180017658  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001765d  mov     rcx, [rsp+1C0h+var_168]
0x180017662  mov     [rsp+1C0h+var_168], r15
0x180017667  test    rcx, rcx
0x18001766a  jz      loc_18001735F
0x180017670  jmp     loc_180017528
0x180017675  test    eax, eax
0x180017677  jle     short loc_18001763A
0x180017679  jmp     short loc_180017631
0x18001767b  call    cs:__imp_GetLastError
0x180017681  mov     edi, eax
0x180017683  test    eax, eax
0x180017685  jle     short loc_18001763A
0x180017687  jmp     short loc_180017631
0x180017689  mov     eax, dword ptr cs:?normal@PolicySettings@Globals@StateRepository@@0U123@A+8; StateRepository::Globals::PolicySettings StateRepository::Globals::PolicySettings::normal
  ... truncated ...
```
