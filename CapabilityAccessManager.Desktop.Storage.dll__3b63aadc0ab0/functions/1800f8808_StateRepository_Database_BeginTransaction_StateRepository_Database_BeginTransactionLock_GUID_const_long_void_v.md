# StateRepository::Database::BeginTransaction(StateRepository::Database::BeginTransactionLock,_GUID const &,long (*)(void *),void *)

- ea: `0x1800f8808`
- end: `0x1800f89ec`
- name: `?BeginTransaction@Database@StateRepository@@QEAAJW4BeginTransactionLock@12@AEBU_GUID@@P6AJPEAX@Z2@Z`
- size: `484`
- prototype: `__int64 __fastcall(StateRepository::Database *, unsigned __int64, const struct _GUID *)`
- caller_count: `2`
- callee_count: `9`
- tags: ``

## callers

- `0x1800f6584`
- `0x1800f73a4`

## callees

- `0x1800017e4`
- `0x180003060`
- `0x18000ed50`
- `0x1800eabf4`
- `0x1800edb2c`
- `0x1800f8808`
- `0x1800f9300`
- `0x1800f94fc`
- `0x1800fc9e8`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800f88e2`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800f88e2`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x1800f88ff`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x1800f88ff`
- `api-ms-win-core-realtime-l1-1-0!QueryUnbiasedInterruptTime` at `0x1800f892a`
- `api-ms-win-core-realtime-l1-1-0!QueryUnbiasedInterruptTime` at `0x1800f892a`

## string_xrefs

- `0x1800f884d`: `onecore\base\appmodel\staterepository\dataaccesslayer\database.cpp`
- `0x1800f88ad`: `onecore\base\appmodel\staterepository\dataaccesslayer\database.cpp`
- `0x1800f89d7`: `onecore\base\appmodel\staterepository\dataaccesslayer\database.cpp`

## pseudocode

```c
__int64 __fastcall StateRepository::Database::BeginTransaction(
        StateRepository::Database *a1,
        unsigned __int64 a2,
        const struct _GUID *a3)
{
  int v6; // eax
  int (*v7)(void *); // r8
  void *v8; // r9
  int v9; // eax
  unsigned int v10; // esi
  DWORD CurrentThreadId; // eax
  __int64 v12; // rcx
  unsigned __int64 v13; // rcx
  __int64 v14; // r8
  __int64 v15; // r9
  _DWORD *v16; // rsi
  __int64 v17; // rcx
  __int64 v18; // rax
  const char *v19; // rax
  int v20; // [rsp+20h] [rbp-61h]
  struct _FILETIME SystemTimeAsFileTime; // [rsp+40h] [rbp-41h] BYREF
  __int64 v22; // [rsp+48h] [rbp-39h] BYREF
  __int64 v23; // [rsp+50h] [rbp-31h] BYREF
  const struct _GUID *v24; // [rsp+58h] [rbp-29h] BYREF
  const char *v25; // [rsp+60h] [rbp-21h] BYREF
  char v26[64]; // [rsp+70h] [rbp-11h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+D8h] [rbp+57h]

  if ( *(_QWORD *)&a3->Data1 == *(_QWORD *)&GUID_00000000_0000_0000_0000_000000000000.Data1
    && *(_QWORD *)a3->Data4 == *(_QWORD *)GUID_00000000_0000_0000_0000_000000000000.Data4 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x206,
      (unsigned int)"onecore\\base\\appmodel\\staterepository\\dataaccesslayer\\database.cpp",
      (const char *)0x80070057LL,
      v20);
    return 2147942487LL;
  }
  else
  {
    v6 = StateRepository::Database::FormatSql(
           v26,
           a2,
           "BEGIN EXCLUSIVE /*%08X-%04X-%04X-%02X%02X-%02X%02X%02X%02X%02X%02X*/;",
           a3);
    if ( v6 < 0 )
      wil::details::in1diag3::_FailFast_Hr(
        retaddr,
        (void *)0x212,
        (unsigned int)"onecore\\base\\appmodel\\staterepository\\dataaccesslayer\\database.cpp",
        (const char *)(unsigned int)v6,
        v20);
    StateRepository::Database::VerifyResourcePriorities(a1, a3, v26);
    v9 = StateRepository::Database::Execute(a1, v26, v7, v8);
    v10 = v9;
    if ( v9 >= 0 )
    {
      xmmword_180140340[*((int *)a1 + 4)] = (__int128)*a3;
      CurrentThreadId = GetCurrentThreadId();
      v12 = *((int *)a1 + 4);
      SystemTimeAsFileTime = 0;
      dword_180140320[v12] = CurrentThreadId;
      GetSystemTimeAsFileTime(&SystemTimeAsFileTime);
      v13 = SystemTimeAsFileTime.dwLowDateTime + ((unsigned __int64)SystemTimeAsFileTime.dwHighDateTime << 32);
      SystemTimeAsFileTime = 0;
      qword_1801402F0[*((int *)a1 + 4)] = v13;
      QueryUnbiasedInterruptTime((PULONGLONG)&SystemTimeAsFileTime);
      v16 = (_DWORD *)qword_1801402E8;
      *((_QWORD *)a1 + 3) = *(unsigned __int64 *)&SystemTimeAsFileTime / 0x2710;
      if ( *v16 > 5u )
      {
        v17 = *(_QWORD *)a1;
        v18 = *((_QWORD *)a1 + 3);
        v22 = 0x1000000;
        v23 = v18;
        v24 = a3;
        if ( v17 )
          v19 = (const char *)sqlite3_db_filename(v17, 0);
        else
          v19 = 0;
        v25 = v19;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByRef<16>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>>(
          (__int64)v16,
          (__int64)&byte_18012A14F,
          v14,
          v15,
          &v25,
          (__int64 *)&v24,
          (__int64)&v23,
          (__int64)&v22);
      }
      return 0;
    }
    else
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x216,
        (unsigned int)"onecore\\base\\appmodel\\staterepository\\dataaccesslayer\\database.cpp",
        (const char *)(unsigned int)v9,
        v20);
      return v10;
    }
  }
}

```

## disassembly

```asm
0x1800f8808  mov     [rsp-8+arg_8], rbx
0x1800f880d  push    rbp
0x1800f880e  push    rsi
0x1800f880f  push    rdi
0x1800f8810  lea     rbp, [rsp-3Fh]
0x1800f8815  sub     rsp, 0C0h
0x1800f881c  mov     rax, cs:__security_cookie
0x1800f8823  xor     rax, rsp
0x1800f8826  mov     [rbp+4Fh+var_20], rax
0x1800f882a  mov     rax, [r8]
0x1800f882d  mov     rbx, r8
0x1800f8830  cmp     rax, qword ptr cs:_GUID_00000000_0000_0000_0000_000000000000.Data1
0x1800f8837  mov     rdi, rcx
0x1800f883a  jnz     short loc_1800F886D
0x1800f883c  mov     rax, [r8+8]
0x1800f8840  cmp     rax, qword ptr cs:_GUID_00000000_0000_0000_0000_000000000000.Data4
0x1800f8847  jnz     short loc_1800F886D
0x1800f8849  mov     rcx, [rbp+57h]; this
0x1800f884d  lea     r8, aOnecoreBaseApp_18; "onecore\\base\\appmodel\\staterepositor"...
0x1800f8854  mov     ebx, 80070057h
0x1800f8859  mov     edx, 206h; void *
0x1800f885e  mov     r9d, ebx; char *
0x1800f8861  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800f8866  mov     eax, ebx
0x1800f8868  jmp     loc_1800F89B4
0x1800f886d  mov     r9, rbx; struct _GUID *
0x1800f8870  lea     r8, aBeginExclusive; "BEGIN EXCLUSIVE /*%08X-%04X-%04X-%02X%0"...
0x1800f8877  lea     rcx, [rbp+4Fh+var_60]; char *
0x1800f887b  call    ?FormatSql@Database@StateRepository@@CAJPEAD_KPEBDAEBU_GUID@@@Z; StateRepository::Database::FormatSql(char *,unsigned __int64,char const *,_GUID const &)
0x1800f8880  test    eax, eax
0x1800f8882  js      loc_1800F89D3
0x1800f8888  lea     r8, [rbp+4Fh+var_60]; char *
0x1800f888c  mov     rdx, rbx; struct _GUID *
0x1800f888f  mov     rcx, rdi; this
0x1800f8892  call    ?VerifyResourcePriorities@Database@StateRepository@@AEAAXAEBU_GUID@@PEBD@Z; StateRepository::Database::VerifyResourcePriorities(_GUID const &,char const *)
0x1800f8897  lea     rdx, [rbp+4Fh+var_60]; char *
0x1800f889b  mov     rcx, rdi; this
0x1800f889e  call    ?Execute@Database@StateRepository@@QEAAJPEBDP6AJPEAX@Z1@Z; StateRepository::Database::Execute(char const *,long (*)(void *),void *)
0x1800f88a3  mov     esi, eax
0x1800f88a5  test    eax, eax
0x1800f88a7  jns     short loc_1800F88C8
0x1800f88a9  mov     rcx, [rbp+57h]; this
0x1800f88ad  lea     r8, aOnecoreBaseApp_18; "onecore\\base\\appmodel\\staterepositor"...
0x1800f88b4  mov     r9d, eax; char *
0x1800f88b7  mov     edx, 216h; void *
0x1800f88bc  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800f88c1  mov     eax, esi
0x1800f88c3  jmp     loc_1800F89B4
0x1800f88c8  movsxd  rax, dword ptr [rdi+10h]
0x1800f88cc  lea     rsi, cs:180000000h
0x1800f88d3  movups  xmm0, xmmword ptr [rbx]
0x1800f88d6  add     rax, rax
0x1800f88d9  movdqu  rva xmmword_180140340[rsi+rax*8], xmm0
0x1800f88e2  call    cs:__imp_GetCurrentThreadId
0x1800f88e8  movsxd  rcx, dword ptr [rdi+10h]
0x1800f88ec  mov     qword ptr [rbp+4Fh+SystemTimeAsFileTime.dwLowDateTime], 0
0x1800f88f4  mov     rva dword_180140320[rsi+rcx*4], eax
0x1800f88fb  lea     rcx, [rbp+4Fh+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x1800f88ff  call    cs:__imp_GetSystemTimeAsFileTime
0x1800f8905  mov     eax, [rbp+4Fh+SystemTimeAsFileTime.dwLowDateTime]
0x1800f8908  mov     ecx, [rbp+4Fh+SystemTimeAsFileTime.dwHighDateTime]
0x1800f890b  shl     rcx, 20h
0x1800f890f  add     rcx, rax
0x1800f8912  mov     qword ptr [rbp+4Fh+SystemTimeAsFileTime.dwLowDateTime], 0
0x1800f891a  movsxd  rax, dword ptr [rdi+10h]
0x1800f891e  mov     rva qword_1801402F0[rsi+rax*8], rcx
0x1800f8926  lea     rcx, [rbp+4Fh+SystemTimeAsFileTime]; UnbiasedTime
0x1800f892a  call    cs:__imp_QueryUnbiasedInterruptTime
0x1800f8930  mov     rsi, cs:qword_1801402E8
0x1800f8937  mov     rax, 346DC5D63886594Bh
0x1800f8941  mul     qword ptr [rbp+4Fh+SystemTimeAsFileTime.dwLowDateTime]
0x1800f8945  shr     rdx, 0Bh
0x1800f8949  mov     [rdi+18h], rdx
0x1800f894d  mov     eax, [rsi]
0x1800f894f  cmp     eax, 5
0x1800f8952  jbe     short loc_1800F89B2
0x1800f8954  mov     rcx, [rdi]
0x1800f8957  mov     rax, [rdi+18h]
0x1800f895b  mov     [rbp+4Fh+var_88], 1000000h
0x1800f8963  mov     [rbp+4Fh+var_80], rax
0x1800f8967  mov     [rbp+4Fh+var_78], rbx
0x1800f896b  test    rcx, rcx
0x1800f896e  jz      short loc_1800F8979
0x1800f8970  xor     edx, edx
0x1800f8972  call    sqlite3_db_filename
0x1800f8977  jmp     short loc_1800F897B
0x1800f8979  xor     eax, eax
0x1800f897b  mov     [rbp+4Fh+var_70], rax
0x1800f897f  lea     rdx, byte_18012A14F
0x1800f8986  lea     rax, [rbp+4Fh+var_88]
0x1800f898a  mov     rcx, rsi
0x1800f898d  mov     [rsp+0D0h+var_98], rax
0x1800f8992  lea     rax, [rbp+4Fh+var_80]
0x1800f8996  mov     [rsp+0D0h+var_A0], rax
0x1800f899b  lea     rax, [rbp+4Fh+var_78]
0x1800f899f  mov     [rsp+0D0h+var_A8], rax
0x1800f89a4  lea     rax, [rbp+4Fh+var_70]
0x1800f89a8  mov     [rsp+0D0h+var_B0], rax
0x1800f89ad  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByRef@$0BA@@@U?$_tlgWrapperByVal@$07@@U3@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByRef@$0BA@@@AEBU?$_tlgWrapperByVal@$07@@5@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByRef<16>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByRef<16> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &)
0x1800f89b2  xor     eax, eax
0x1800f89b4  mov     rcx, [rbp+4Fh+var_20]
0x1800f89b8  xor     rcx, rsp; StackCookie
0x1800f89bb  call    __security_check_cookie
0x1800f89c0  mov     rbx, [rsp+0D0h+arg_8]
0x1800f89c8  add     rsp, 0C0h
0x1800f89cf  pop     rdi
0x1800f89d0  pop     rsi
0x1800f89d1  pop     rbp
0x1800f89d2  retn
0x1800f89d3  mov     rcx, [rbp+57h]; this
0x1800f89d7  lea     r8, aOnecoreBaseApp_18; "onecore\\base\\appmodel\\staterepositor"...
0x1800f89de  mov     r9d, eax; char *
0x1800f89e1  mov     edx, 212h; void *
0x1800f89e6  call    ?_FailFast_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_FailFast_Hr(void *,uint,char const *,long)
```
