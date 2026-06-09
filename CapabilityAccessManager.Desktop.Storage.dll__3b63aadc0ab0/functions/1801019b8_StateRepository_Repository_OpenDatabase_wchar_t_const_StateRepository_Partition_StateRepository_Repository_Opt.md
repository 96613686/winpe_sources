# StateRepository::Repository::OpenDatabase(wchar_t const *,StateRepository::Partition,StateRepository::Repository::Options,StateRepository::Database &)

- ea: `0x1801019b8`
- end: `0x180101c9e`
- name: `?OpenDatabase@Repository@StateRepository@@SAJPEB_WW4Partition@2@W4Options@12@AEAVDatabase@2@@Z`
- size: `742`
- prototype: `__int64 __fastcall(const WCHAR *, __int64, unsigned int, __int64)`
- caller_count: `1`
- callee_count: `14`
- tags: `file_ops, service_task`

## callers

- `0x180101ca4`

## callees

- `0x180003060`
- `0x1800038f0`
- `0x180003a40`
- `0x1800e4c28`
- `0x1800eabf4`
- `0x1800f7630`
- `0x1800f8f28`
- `0x1800fa944`
- `0x1801013e8`
- `0x1801019b8`
- `0x180102014`
- `0x180104ca4`
- `0x18010819c`
- `0x1801083c4`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180101b6d`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180101b6d`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180101bb1`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180101bb1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180101a43`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180101ad0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180101a43`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180101ad0`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x180101a35`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x180101ac6`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x180101a35`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x180101ac6`

## string_xrefs

- `0x180101aec`: `onecore\base\appmodel\staterepository\dataaccesslayer\repository.cpp`
- `0x180101afd`: `onecore\base\appmodel\staterepository\dataaccesslayer\repository.cpp`
- `0x180101a8f`: `onecore\base\appmodel\StateRepository\DataAccessLayer\Utf8String.hpp`
- `0x180101b98`: `onecore\base\appmodel\staterepository\dataaccesslayer\databasecachesingleton.cpp`

## pseudocode

```c
__int64 __fastcall StateRepository::Repository::OpenDatabase(const WCHAR *a1, __int64 a2, unsigned int a3, __int64 a4)
{
  StateRepository::Globals *v7; // rcx
  signed int LastError; // eax
  unsigned int v9; // ebx
  void *v10; // rax
  unsigned __int64 v11; // r9
  __int64 v12; // rdx
  int v13; // eax
  StateRepository::Globals *v14; // rcx
  int ServiceControl_FailIfBlocked; // eax
  StateRepository::DatabaseCache *v16; // rcx
  int v17; // eax
  void *v18; // rcx
  char *v20; // r15
  int v21; // eax
  void *v22; // rcx
  int lpMultiByteStr; // [rsp+20h] [rbp-E0h]
  unsigned int v24[4]; // [rsp+40h] [rbp-C0h] BYREF
  char *v25; // [rsp+50h] [rbp-B0h]
  void *Block; // [rsp+58h] [rbp-A8h]
  CHAR MultiByteStr[272]; // [rsp+60h] [rbp-A0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+1B8h] [rbp+B8h]

  Block = 0;
  memset_0(MultiByteStr, 0, 0x104u);
  v25 = MultiByteStr;
  if ( WideCharToMultiByte(0xFDE9u, 0, a1, -1, MultiByteStr, 260, 0, 0) )
    goto LABEL_11;
  LastError = GetLastError();
  v9 = LastError;
  if ( LastError != 122 )
    goto LABEL_7;
  v10 = operator new[](0, (const struct std::nothrow_t *)&std::nothrow);
  Block = v10;
  if ( !v10 )
  {
    v9 = -2147024882;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x25,
      (unsigned int)"onecore\\base\\appmodel\\StateRepository\\DataAccessLayer\\Utf8String.hpp",
      (const char *)0x8007000ELL,
      lpMultiByteStr);
LABEL_10:
    v11 = v9;
    v12 = 722;
    goto LABEL_25;
  }
  v25 = (char *)v10;
  if ( !WideCharToMultiByte(0xFDE9u, 0, a1, -1, (LPSTR)v10, 0, 0, 0) )
  {
    LastError = GetLastError();
    v9 = LastError;
LABEL_7:
    if ( LastError > 0 )
      v9 = (unsigned __int16)LastError | 0x80070000;
    if ( (v9 & 0x80000000) != 0 )
      goto LABEL_10;
  }
LABEL_11:
  if ( (a3 & 0x100) == 0 )
    goto LABEL_22;
  v13 = StateRepository::Database::Close((StateRepository::Database *)a4);
  v14 = retaddr;
  if ( v13 < 0 )
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x2FC,
      (int)"onecore\\base\\appmodel\\staterepository\\dataaccesslayer\\repository.cpp",
      (const char *)(unsigned int)v13);
  ServiceControl_FailIfBlocked = StateRepository::Globals::GetServiceControl_FailIfBlocked(v14);
  v9 = ServiceControl_FailIfBlocked;
  if ( ServiceControl_FailIfBlocked < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x2FE,
      (unsigned int)"onecore\\base\\appmodel\\staterepository\\dataaccesslayer\\repository.cpp",
      (const char *)(unsigned int)ServiceControl_FailIfBlocked,
      lpMultiByteStr);
    v11 = v9;
    v12 = 727;
    goto LABEL_25;
  }
  AcquireSRWLockExclusive(&StateRepository::DatabaseCacheSingleton::s_lock);
  StateRepository::DatabaseCache::Get(v16, v25, (struct StateRepository::Database *)a4);
  v17 = StateRepository::DatabaseCache::GC((void ***)StateRepository::DatabaseCacheSingleton::s_cache);
  if ( v17 < 0 )
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x20,
      (int)"onecore\\base\\appmodel\\staterepository\\dataaccesslayer\\databasecachesingleton.cpp",
      (const char *)(unsigned int)v17);
  ReleaseSRWLockExclusive(&StateRepository::DatabaseCacheSingleton::s_lock);
  if ( !*(_QWORD *)a4 )
  {
LABEL_22:
    v20 = v25;
    v21 = StateRepository::Globals::GetServiceControl_FailIfBlocked(v7);
    v9 = v21;
    if ( v21 >= 0 )
    {
      v24[0] = 0;
      v21 = StateRepository::Repository::AdjustDatabaseOpenFlagsPerOptions(a3, v24);
      v9 = v21;
      if ( v21 >= 0 )
      {
        v21 = StateRepository::Database::Open((StateRepository::Database *)a4, (__int64)v20, v24[0]);
        v9 = v21;
        if ( v21 >= 0 )
        {
          *(_DWORD *)(a4 + 16) = 1;
          v21 = StateRepository::Repository::SetOptions(a4, a3);
          v9 = v21;
          if ( v21 >= 0 )
          {
            v9 = 0;
            goto LABEL_33;
          }
          v12 = 756;
        }
        else
        {
          v12 = 754;
        }
      }
      else
      {
        v12 = 753;
      }
    }
    else
    {
      v12 = 749;
    }
    v11 = (unsigned int)v21;
LABEL_25:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v12,
      (unsigned int)"onecore\\base\\appmodel\\staterepository\\dataaccesslayer\\repository.cpp",
      (const char *)v11,
      lpMultiByteStr);
LABEL_33:
    v22 = Block;
    Block = 0;
    if ( v22 )
      operator delete(v22);
    return v9;
  }
  *(_DWORD *)(a4 + 16) = 1;
  *(_QWORD *)(a4 + 8) = 0;
  v18 = Block;
  Block = 0;
  if ( v18 )
    operator delete(v18);
  return 0;
}

```

## disassembly

```asm
0x1801019b8  push    rbp
0x1801019ba  push    rbx
0x1801019bb  push    rsi
0x1801019bc  push    rdi
0x1801019bd  push    r12
0x1801019bf  push    r14
0x1801019c1  push    r15
0x1801019c3  lea     rbp, [rsp-80h]
0x1801019c8  sub     rsp, 180h
0x1801019cf  mov     rax, cs:__security_cookie
0x1801019d6  xor     rax, rsp
0x1801019d9  mov     [rbp+0B0h+var_40], rax
0x1801019dd  mov     rsi, r9
0x1801019e0  mov     r14d, r8d
0x1801019e3  mov     rdi, rcx
0x1801019e6  xor     r12d, r12d
0x1801019e9  mov     [rsp+1B0h+Block], r12
0x1801019ee  mov     ebx, 104h
0x1801019f3  mov     r8d, ebx; Size
0x1801019f6  xor     edx, edx; Val
0x1801019f8  lea     rcx, [rsp+1B0h+MultiByteStr]; void *
0x1801019fd  call    memset_0
0x180101a02  lea     rax, [rsp+1B0h+MultiByteStr]
0x180101a07  mov     [rsp+1B0h+var_160], rax
0x180101a0c  mov     [rsp+1B0h+lpUsedDefaultChar], r12; lpUsedDefaultChar
0x180101a11  mov     [rsp+1B0h+lpDefaultChar], r12; lpDefaultChar
0x180101a16  mov     [rsp+1B0h+cbMultiByte], ebx; cbMultiByte
0x180101a1a  lea     rax, [rsp+1B0h+MultiByteStr]
0x180101a1f  mov     [rsp+1B0h+lpMultiByteStr], rax; int
0x180101a24  or      r15d, 0FFFFFFFFh
0x180101a28  mov     r9d, r15d; cchWideChar
0x180101a2b  mov     r8, rdi; lpWideCharStr
0x180101a2e  xor     edx, edx; dwFlags
0x180101a30  mov     ecx, 0FDE9h; CodePage
0x180101a35  call    cs:__imp_WideCharToMultiByte
0x180101a3b  test    eax, eax
0x180101a3d  jnz     loc_180101AFD
0x180101a43  call    cs:__imp_GetLastError
0x180101a49  mov     ebx, eax
0x180101a4b  cmp     eax, 7Ah ; 'z'
0x180101a4e  jnz     loc_180101AD8
0x180101a54  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180101a5b  xor     ecx, ecx; unsigned __int64
0x180101a5d  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x180101a62  mov     rcx, [rsp+1B0h+Block]; Block
0x180101a67  mov     [rsp+1B0h+Block], rax
0x180101a6c  test    rcx, rcx
0x180101a6f  jz      short loc_180101A7B
0x180101a71  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180101a76  mov     rax, [rsp+1B0h+Block]
0x180101a7b  test    rax, rax
0x180101a7e  jnz     short loc_180101AA0
0x180101a80  mov     rcx, [rbp+0B8h]; this
0x180101a87  mov     ebx, 8007000Eh
0x180101a8c  mov     r9d, ebx; char *
0x180101a8f  lea     r8, aOnecoreBaseApp_3; "onecore\\base\\appmodel\\StateRepositor"...
0x180101a96  lea     edx, [rax+25h]; void *
0x180101a99  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180101a9e  jmp     short loc_180101AE9
0x180101aa0  mov     [rsp+1B0h+var_160], rax
0x180101aa5  mov     [rsp+1B0h+lpUsedDefaultChar], r12; lpUsedDefaultChar
0x180101aaa  mov     [rsp+1B0h+lpDefaultChar], r12; lpDefaultChar
0x180101aaf  mov     [rsp+1B0h+cbMultiByte], r12d; cbMultiByte
0x180101ab4  mov     [rsp+1B0h+lpMultiByteStr], rax; lpMultiByteStr
0x180101ab9  mov     r9d, r15d; cchWideChar
0x180101abc  mov     r8, rdi; lpWideCharStr
0x180101abf  xor     edx, edx; dwFlags
0x180101ac1  mov     ecx, 0FDE9h; CodePage
0x180101ac6  call    cs:__imp_WideCharToMultiByte
0x180101acc  test    eax, eax
0x180101ace  jnz     short loc_180101AFD
0x180101ad0  call    cs:__imp_GetLastError
0x180101ad6  mov     ebx, eax
0x180101ad8  test    eax, eax
0x180101ada  jle     short loc_180101AE5
0x180101adc  movzx   ebx, ax
0x180101adf  or      ebx, 80070000h
0x180101ae5  test    ebx, ebx
0x180101ae7  jns     short loc_180101AFD
0x180101ae9  mov     r9d, ebx
0x180101aec  lea     r8, aOnecoreBaseApp_4; "onecore\\base\\appmodel\\staterepositor"...
0x180101af3  mov     edx, 2D2h
0x180101af8  jmp     loc_180101BFE
0x180101afd  lea     rdi, aOnecoreBaseApp_4; "onecore\\base\\appmodel\\staterepositor"...
0x180101b04  bt      r14d, 8
0x180101b09  jnb     loc_180101BE3
0x180101b0f  mov     r15, [rsp+1B0h+var_160]
0x180101b14  mov     rcx, rsi; this
0x180101b17  call    ?Close@Database@StateRepository@@QEAAJXZ; StateRepository::Database::Close(void)
0x180101b1c  mov     rcx, [rbp+0B8h]; this
0x180101b23  test    eax, eax
0x180101b25  jns     short loc_180101B37
0x180101b27  mov     r9d, eax; char *
0x180101b2a  mov     r8, rdi; unsigned int
0x180101b2d  mov     edx, 2FCh; void *
0x180101b32  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180101b37  call    ?GetServiceControl_FailIfBlocked@Globals@StateRepository@@YAJ_N@Z; StateRepository::Globals::GetServiceControl_FailIfBlocked(bool)
0x180101b3c  mov     ebx, eax
0x180101b3e  test    eax, eax
0x180101b40  jns     short loc_180101B66
0x180101b42  mov     rcx, [rbp+0B8h]; this
0x180101b49  mov     r9d, eax; char *
0x180101b4c  mov     r8, rdi; unsigned int
0x180101b4f  mov     edx, 2FEh; void *
0x180101b54  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180101b59  mov     r9d, ebx
0x180101b5c  mov     edx, 2D7h
0x180101b61  jmp     loc_180101BFB
0x180101b66  lea     rcx, ?s_lock@DatabaseCacheSingleton@StateRepository@@0Vsrwlock@wil@@A; SRWLock
0x180101b6d  call    cs:__imp_AcquireSRWLockExclusive
0x180101b73  mov     r8, rsi; struct StateRepository::Database *
0x180101b76  mov     rdx, r15; char *
0x180101b79  call    ?Get@DatabaseCache@StateRepository@@QEAAPEAVDatabase@2@PEBDAEAV32@@Z; StateRepository::DatabaseCache::Get(char const *,StateRepository::Database &)
0x180101b7e  mov     rcx, cs:?s_cache@DatabaseCacheSingleton@StateRepository@@0PEAVDatabaseCache@2@EA; StateRepository::DatabaseCache * StateRepository::DatabaseCacheSingleton::s_cache
0x180101b85  call    ?GC@DatabaseCache@StateRepository@@QEAAJW4GCPolicy@Globals@2@W4GCFlags@42@@Z; StateRepository::DatabaseCache::GC(StateRepository::Globals::GCPolicy,StateRepository::Globals::GCFlags)
0x180101b8a  mov     rcx, [rbp+0B8h]; this
0x180101b91  test    eax, eax
0x180101b93  jns     short loc_180101BAA
0x180101b95  mov     r9d, eax; char *
0x180101b98  lea     r8, aOnecoreBaseApp_22; "onecore\\base\\appmodel\\staterepositor"...
0x180101b9f  mov     edx, 20h ; ' '; void *
0x180101ba4  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180101ba9  nop
0x180101baa  lea     rcx, ?s_lock@DatabaseCacheSingleton@StateRepository@@0Vsrwlock@wil@@A; SRWLock
0x180101bb1  call    cs:__imp_ReleaseSRWLockExclusive
0x180101bb7  nop
0x180101bb8  cmp     [rsi], r12
0x180101bbb  jz      short loc_180101BE3
0x180101bbd  mov     dword ptr [rsi+10h], 1
0x180101bc4  mov     [rsi+8], r12
0x180101bc8  mov     rcx, [rsp+1B0h+Block]; Block
0x180101bcd  mov     [rsp+1B0h+Block], r12
0x180101bd2  test    rcx, rcx
0x180101bd5  jz      short loc_180101BDC
0x180101bd7  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180101bdc  xor     eax, eax
0x180101bde  jmp     loc_180101C80
0x180101be3  mov     r15, [rsp+1B0h+var_160]
0x180101be8  call    ?GetServiceControl_FailIfBlocked@Globals@StateRepository@@YAJ_N@Z; StateRepository::Globals::GetServiceControl_FailIfBlocked(bool)
0x180101bed  mov     ebx, eax
0x180101bef  test    eax, eax
0x180101bf1  jns     short loc_180101C0C
0x180101bf3  mov     edx, 2EDh; void *
0x180101bf8  mov     r9d, eax; char *
0x180101bfb  mov     r8, rdi; unsigned int
0x180101bfe  mov     rcx, [rbp+0B8h]; this
0x180101c05  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180101c0a  jmp     short loc_180101C6A
0x180101c0c  mov     [rsp+1B0h+var_170], r12d
0x180101c11  lea     rdx, [rsp+1B0h+var_170]
0x180101c16  mov     ecx, r14d
0x180101c19  call    ?AdjustDatabaseOpenFlagsPerOptions@Repository@StateRepository@@CAJW4Options@12@PEAH@Z; StateRepository::Repository::AdjustDatabaseOpenFlagsPerOptions(StateRepository::Repository::Options,int *)
0x180101c1e  mov     ebx, eax
0x180101c20  test    eax, eax
0x180101c22  jns     short loc_180101C2B
0x180101c24  mov     edx, 2F1h
0x180101c29  jmp     short loc_180101BF8
0x180101c2b  mov     r8d, [rsp+1B0h+var_170]
0x180101c30  mov     rdx, r15
0x180101c33  mov     rcx, rsi
0x180101c36  call    ?Open@Database@StateRepository@@QEAAJPEBDW4OpenFlags@12@PEBI@Z; StateRepository::Database::Open(char const *,StateRepository::Database::OpenFlags,uint const *)
0x180101c3b  mov     ebx, eax
0x180101c3d  test    eax, eax
0x180101c3f  jns     short loc_180101C48
0x180101c41  mov     edx, 2F2h
0x180101c46  jmp     short loc_180101BF8
0x180101c48  mov     dword ptr [rsi+10h], 1
0x180101c4f  mov     edx, r14d
0x180101c52  mov     rcx, rsi
0x180101c55  call    ?SetOptions@Repository@StateRepository@@CAJAEAVDatabase@2@W4Options@12@@Z; StateRepository::Repository::SetOptions(StateRepository::Database &,StateRepository::Repository::Options)
0x180101c5a  mov     ebx, eax
0x180101c5c  test    eax, eax
0x180101c5e  jns     short loc_180101C67
0x180101c60  mov     edx, 2F4h
0x180101c65  jmp     short loc_180101BF8
0x180101c67  mov     ebx, r12d
0x180101c6a  mov     rcx, [rsp+1B0h+Block]; Block
0x180101c6f  mov     [rsp+1B0h+Block], r12
0x180101c74  test    rcx, rcx
0x180101c77  jz      short loc_180101C7E
0x180101c79  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180101c7e  mov     eax, ebx
0x180101c80  mov     rcx, [rbp+0B0h+var_40]
0x180101c84  xor     rcx, rsp; StackCookie
0x180101c87  call    __security_check_cookie
0x180101c8c  add     rsp, 180h
0x180101c93  pop     r15
0x180101c95  pop     r14
0x180101c97  pop     r12
0x180101c99  pop     rdi
0x180101c9a  pop     rsi
0x180101c9b  pop     rbx
0x180101c9c  pop     rbp
0x180101c9d  retn
```
