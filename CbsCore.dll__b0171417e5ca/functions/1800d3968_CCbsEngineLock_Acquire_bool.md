# CCbsEngineLock::Acquire(bool)

- ea: `0x1800d3968`
- end: `0x1800d3f0e`
- name: `?Acquire@CCbsEngineLock@@QEAAJ_N@Z`
- size: `1446`
- prototype: `__int64 __fastcall(CCbsEngineLock *__hidden this, bool)`
- caller_count: `2`
- callee_count: `18`
- tags: `file_ops, broker_com_uri`

## callers

- `0x180140040`
- `0x1801402f0`

## callees

- `0x1800150c0`
- `0x180028900`
- `0x1800289f0`
- `0x18002a78c`
- `0x18002ac84`
- `0x180065034`
- `0x180095e34`
- `0x180098538`
- `0x180099548`
- `0x18009cf78`
- `0x1800a8678`
- `0x1800d3968`
- `0x1800eb920`
- `0x1800ebd20`
- `0x1800f1eb4`
- `0x18013ffec`
- `0x18014001c`
- `0x180140b08`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x1800d3de1`
- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x1800d3de1`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x1800d3c15`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x1800d3c15`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800d3ad5`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800d3ad5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800d3afb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800d3c29`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800d3df1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800d3afb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800d3c29`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800d3df1`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800d3a0a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800d3a7b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800d3abd`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800d3a0a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800d3a7b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800d3abd`

## string_xrefs

- `0x1800d3b1a`: `CreateEventFailed`
- `0x1800d3dca`: `Engine: Unable to remove requesting thread info from queue`
- `0x1800d3d8f`: `Engine: Thread ready for execution: {}`
- `0x1800d3d48`: `Unexpected, owning thread is not the current thread`
- `0x1800d3ba2`: `Engine: Add thread to the execution waiting queue: {}`

## pseudocode

```c
__int64 __fastcall CCbsEngineLock::Acquire(CCbsEngineLock *this, char a2)
{
  unsigned int v4; // ebx
  __int64 v5; // rdx
  int v6; // ebx
  HANDLE *v7; // rax
  HANDLE *v8; // rsi
  HANDLE EventW; // rax
  unsigned int v10; // edx
  signed int LastError; // ebx
  unsigned int v12; // eax
  unsigned int v13; // edx
  char *v14; // rcx
  int v15; // eax
  __int64 v16; // rdx
  __int64 v17; // rbx
  signed int v18; // ebx
  unsigned int v19; // eax
  __int64 v20; // rcx
  unsigned __int64 i; // rax
  unsigned int v22; // eax
  signed int v23; // eax
  unsigned int v25; // [rsp+20h] [rbp-40h]
  unsigned int v26[2]; // [rsp+30h] [rbp-30h] BYREF
  _BYTE v27[24]; // [rsp+38h] [rbp-28h] BYREF
  int v28; // [rsp+50h] [rbp-10h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+88h] [rbp+28h]

  CritSecLocker::CritSecLocker((CritSecLocker *)v27, this, 1);
  if ( *((_BYTE *)this + 108) )
  {
    v4 = -2146498550;
    v28 = -2146498550;
    if ( LogAdapter::g_Logger )
    {
      LogAdapter::Logger::LogNumObjects<>(
        (__int64)LogAdapter::g_Logger,
        0,
        3,
        (struct Windows::Rtl::IRtlFormattedOutputStream *)"Execution engine queue deactivated or not initialized properly");
      *(_QWORD *)v26 = &v28;
      LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
        (__int64)LogAdapter::g_Logger,
        1,
        3,
        (__int64)": {}",
        (__int64)v26);
    }
    v5 = 83;
LABEL_62:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v5,
      (unsigned int)"onecore\\base\\cbs\\core\\executionengine.cpp",
      (const char *)v4,
      v25);
    goto LABEL_63;
  }
  v6 = *((_DWORD *)this + 26);
  if ( v6 == GetCurrentThreadId() )
  {
    v4 = -2146498560;
    v28 = -2146498560;
    if ( LogAdapter::g_Logger )
    {
      LogAdapter::Logger::LogNumObjects<>(
        (__int64)LogAdapter::g_Logger,
        0,
        3,
        (struct Windows::Rtl::IRtlFormattedOutputStream *)"Unexpected nested engine locking.");
      *(_QWORD *)v26 = &v28;
      LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
        (__int64)LogAdapter::g_Logger,
        1,
        3,
        (__int64)": {}",
        (__int64)v26);
    }
    v5 = 87;
    goto LABEL_62;
  }
  if ( v6 )
  {
    v7 = (HANDLE *)operator new(0x10u, (const struct std::nothrow_t *)&std::nothrow);
    v8 = v7;
    if ( !v7 )
    {
      v4 = -2147024882;
      v28 = -2147024882;
      if ( LogAdapter::g_Logger )
      {
        LogAdapter::Logger::LogNumObjects<>(
          (__int64)LogAdapter::g_Logger,
          0,
          3,
          (struct Windows::Rtl::IRtlFormattedOutputStream *)"Failed to allocate memory");
        *(_QWORD *)v26 = &v28;
        LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
          (__int64)LogAdapter::g_Logger,
          1,
          3,
          (__int64)": {}",
          (__int64)v26);
      }
      v5 = 99;
      goto LABEL_62;
    }
    *v7 = 0;
    v7[1] = 0;
    *(_DWORD *)v7 = GetCurrentThreadId();
    EventW = CreateEventW(0, 0, 0, 0);
    Windows::AutoComPtr<CCbsCancelSessionExecutionObject>::TakeOwnership(v8 + 1, EventW);
    if ( !v8[1] )
    {
      LastError = GetLastError();
      if ( LogAdapter::g_Logger )
      {
        LogAdapter::Logger::LogNumObjects<>(
          (__int64)LogAdapter::g_Logger,
          0,
          3,
          (struct Windows::Rtl::IRtlFormattedOutputStream *)"CreateEventFailed");
        if ( LastError > 0 )
          v12 = (unsigned __int16)LastError | 0x80070000;
        else
          v12 = LastError;
        v28 = v12;
        *(_QWORD *)v26 = &v28;
        LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
          (__int64)LogAdapter::g_Logger,
          1,
          3,
          (__int64)": {0}",
          (__int64)v26);
      }
      if ( !LastError )
      {
        CCbsEngineLock::RequestingThreadInfo::`scalar deleting destructor'(
          (CCbsEngineLock::RequestingThreadInfo *)v8,
          v10);
        goto LABEL_11;
      }
      v4 = wil::details::in1diag3::Return_Win32(
             retaddr,
             (void *)0x6D,
             (unsigned int)"onecore\\base\\cbs\\core\\executionengine.cpp",
             (const char *)(unsigned int)LastError,
             v25);
LABEL_21:
      CCbsEngineLock::RequestingThreadInfo::`scalar deleting destructor'(
        (CCbsEngineLock::RequestingThreadInfo *)v8,
        v13);
      goto LABEL_63;
    }
    LogAdapter::TraceAtLevel<unsigned long>(1, "Engine: Add thread to the execution waiting queue: {}", v8);
    *(_QWORD *)v26 = v8;
    v14 = (char *)this + 40;
    if ( a2 )
    {
      v15 = CCbsArrayBase<AnalyzerStore::ComponentVersion *,CCbsPointerArray<AnalyzerStore::ComponentVersion *>>::InsertAt(
              v14,
              v26,
              0);
      v4 = v15;
      if ( v15 < 0 )
      {
        v16 = 117;
LABEL_26:
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)v16,
          (unsigned int)"onecore\\base\\cbs\\core\\executionengine.cpp",
          (const char *)(unsigned int)v15,
          v25);
        goto LABEL_21;
      }
    }
    else
    {
      v15 = CCbsArrayBase<CCbsEngineLock::RequestingThreadInfo *,CCbsPointerArray<CCbsEngineLock::RequestingThreadInfo *>>::Add(
              v14,
              v26);
      v4 = v15;
      if ( v15 < 0 )
      {
        v16 = 121;
        goto LABEL_26;
      }
    }
    CritSecLocker::Unlock((CritSecLocker *)v27);
    v17 = 0xFFFFFFFFLL;
    if ( WaitForSingleObject(v8[1], 0xFFFFFFFF) )
    {
      v18 = GetLastError();
      if ( LogAdapter::g_Logger )
      {
        LogAdapter::Logger::LogNumObjects<>(
          (__int64)LogAdapter::g_Logger,
          0,
          3,
          (struct Windows::Rtl::IRtlFormattedOutputStream *)"Wait failed");
        if ( v18 > 0 )
          v19 = (unsigned __int16)v18 | 0x80070000;
        else
          v19 = v18;
        v28 = v19;
        *(_QWORD *)v26 = &v28;
        LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
          (__int64)LogAdapter::g_Logger,
          1,
          3,
          (__int64)": {0}",
          (__int64)v26);
      }
      if ( v18 )
      {
        v4 = wil::details::in1diag3::Return_Win32(
               retaddr,
               (void *)0x83,
               (unsigned int)"onecore\\base\\cbs\\core\\executionengine.cpp",
               (const char *)(unsigned int)v18,
               v25);
        goto LABEL_63;
      }
    }
    else
    {
      CritSecLocker::Lock((CritSecLocker *)v27);
      if ( *((_BYTE *)this + 108) )
      {
        v4 = -2146498521;
        v28 = -2146498521;
        if ( LogAdapter::g_Logger )
        {
          LogAdapter::Logger::LogNumObjects<>(
            (__int64)LogAdapter::g_Logger,
            0,
            3,
            (struct Windows::Rtl::IRtlFormattedOutputStream *)"Execution engine queue deactivated");
          *(_QWORD *)v26 = &v28;
          LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
            (__int64)LogAdapter::g_Logger,
            1,
            3,
            (__int64)": {}",
            (__int64)v26);
        }
        v5 = 136;
        goto LABEL_62;
      }
      if ( *((_DWORD *)this + 26) != *(_DWORD *)v8 )
      {
        v4 = -2146498560;
        v28 = -2146498560;
        if ( LogAdapter::g_Logger )
        {
          LogAdapter::Logger::LogNumObjects<>(
            (__int64)LogAdapter::g_Logger,
            0,
            3,
            (struct Windows::Rtl::IRtlFormattedOutputStream *)"Unexpected, owning thread is not the current thread");
          *(_QWORD *)v26 = &v28;
          LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
            (__int64)LogAdapter::g_Logger,
            1,
            3,
            (__int64)": {}",
            (__int64)v26);
        }
        v5 = 140;
        goto LABEL_62;
      }
      LogAdapter::TraceAtLevel<unsigned long>(1, "Engine: Thread ready for execution: {}", v8);
      v20 = *((_QWORD *)this + 10);
      if ( v20 )
      {
        for ( i = 0; i < *((_QWORD *)this + 8); ++i )
        {
          if ( v8 == *(HANDLE **)(v20 + 8 * i) )
          {
            v17 = i;
            break;
          }
        }
      }
      v22 = CCbsPointerArray<CCbsEngineLock::RequestingThreadInfo *>::RemoveAt((char *)this + 40, v17);
      LogAdapter::TraceAtLevelIfFailed<long,>(2, v22, "Engine: Unable to remove requesting thread info from queue");
      if ( !ResetEvent(*((HANDLE *)this + 14)) )
      {
        v23 = GetLastError();
        v4 = v23;
        if ( v23 > 0 )
          v4 = (unsigned __int16)v23 | 0x80070000;
        v28 = v4;
        if ( LogAdapter::g_Logger )
        {
          LogAdapter::Logger::LogNumObjects<>(
            (__int64)LogAdapter::g_Logger,
            0,
            3,
            (struct Windows::Rtl::IRtlFormattedOutputStream *)"Failed to reset idle event");
          *(_QWORD *)v26 = &v28;
          LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
            (__int64)LogAdapter::g_Logger,
            1,
            3,
            (__int64)": {}",
            (__int64)v26);
        }
        if ( (v4 & 0x80000000) == 0 )
          goto LABEL_63;
        v5 = 148;
        goto LABEL_62;
      }
    }
    CritSecLocker::~CritSecLocker((CritSecLocker *)v27);
    return 0;
  }
  *((_DWORD *)this + 26) = GetCurrentThreadId();
LABEL_11:
  v4 = 0;
LABEL_63:
  CritSecLocker::~CritSecLocker((CritSecLocker *)v27);
  return v4;
}

```

## disassembly

```asm
0x1800d3968  mov     [rsp-28h+arg_8], rbx
0x1800d396d  mov     [rsp-28h+arg_10], rsi
0x1800d3972  push    rbp
0x1800d3973  push    rdi
0x1800d3974  push    r12
0x1800d3976  push    r14
0x1800d3978  push    r15
0x1800d397a  mov     rbp, rsp
0x1800d397d  sub     rsp, 60h
0x1800d3981  mov     rax, cs:__security_cookie
0x1800d3988  xor     rax, rsp
0x1800d398b  mov     [rbp+var_8], rax
0x1800d398f  mov     r15b, dl
0x1800d3992  mov     rdi, rcx
0x1800d3995  mov     rdx, rcx; struct AutoCritSec *
0x1800d3998  mov     r8b, 1; bool
0x1800d399b  lea     rcx, [rbp+var_28]; this
0x1800d399f  call    ??0CritSecLocker@@QEAA@AEAVAutoCritSec@@_N@Z; CritSecLocker::CritSecLocker(AutoCritSec &,bool)
0x1800d39a4  cmp     byte ptr [rdi+6Ch], 0
0x1800d39a8  jz      short loc_1800D3A07
0x1800d39aa  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1800d39b1  mov     ebx, 800F080Ah
0x1800d39b6  mov     [rbp+var_10], ebx
0x1800d39b9  test    rcx, rcx
0x1800d39bc  jz      short loc_1800D39FD
0x1800d39be  mov     edi, 3
0x1800d39c3  lea     r9, aExecutionEngin_0; "Execution engine queue deactivated or n"...
0x1800d39ca  mov     r8d, edi
0x1800d39cd  xor     edx, edx
0x1800d39cf  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x1800d39d4  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1800d39db  lea     rax, [rbp+var_10]
0x1800d39df  mov     qword ptr [rbp+var_30], rax
0x1800d39e3  lea     r9, asc_1802EE7AC; ": {}"
0x1800d39ea  lea     rax, [rbp+var_30]
0x1800d39ee  mov     r8d, edi
0x1800d39f1  mov     dl, 1
0x1800d39f3  mov     qword ptr [rsp+60h+var_40], rax
0x1800d39f8  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x1800d39fd  mov     edx, 53h ; 'S'
0x1800d3a02  jmp     loc_1800D3ECA
0x1800d3a07  mov     ebx, [rdi+68h]
0x1800d3a0a  call    cs:__imp_GetCurrentThreadId
0x1800d3a11  nop     dword ptr [rax+rax+00h]
0x1800d3a16  cmp     ebx, eax
0x1800d3a18  jnz     short loc_1800D3A77
0x1800d3a1a  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1800d3a21  mov     ebx, 800F0800h
0x1800d3a26  mov     [rbp+var_10], ebx
0x1800d3a29  test    rcx, rcx
0x1800d3a2c  jz      short loc_1800D3A6D
0x1800d3a2e  mov     edi, 3
0x1800d3a33  lea     r9, aUnexpectedNest; "Unexpected nested engine locking."
0x1800d3a3a  mov     r8d, edi
0x1800d3a3d  xor     edx, edx
0x1800d3a3f  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x1800d3a44  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1800d3a4b  lea     rax, [rbp+var_10]
0x1800d3a4f  mov     qword ptr [rbp+var_30], rax
0x1800d3a53  lea     r9, asc_1802EE7AC; ": {}"
0x1800d3a5a  lea     rax, [rbp+var_30]
0x1800d3a5e  mov     r8d, edi
0x1800d3a61  mov     dl, 1
0x1800d3a63  mov     qword ptr [rsp+60h+var_40], rax
0x1800d3a68  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x1800d3a6d  mov     edx, 57h ; 'W'
0x1800d3a72  jmp     loc_1800D3ECA
0x1800d3a77  test    ebx, ebx
0x1800d3a79  jnz     short loc_1800D3A91
0x1800d3a7b  call    cs:__imp_GetCurrentThreadId
0x1800d3a82  nop     dword ptr [rax+rax+00h]
0x1800d3a87  mov     [rdi+68h], eax
0x1800d3a8a  xor     ebx, ebx
0x1800d3a8c  jmp     loc_1800D3EDD
0x1800d3a91  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x1800d3a98  mov     ecx, 10h; unsigned __int64
0x1800d3a9d  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x1800d3aa2  mov     rsi, rax
0x1800d3aa5  test    rax, rax
0x1800d3aa8  jz      loc_1800D3E72
0x1800d3aae  mov     qword ptr [rax], 0
0x1800d3ab5  mov     qword ptr [rax+8], 0
0x1800d3abd  call    cs:__imp_GetCurrentThreadId
0x1800d3ac4  nop     dword ptr [rax+rax+00h]
0x1800d3ac9  xor     r9d, r9d; lpName
0x1800d3acc  xor     r8d, r8d; bInitialState
0x1800d3acf  xor     edx, edx; bManualReset
0x1800d3ad1  mov     [rsi], eax
0x1800d3ad3  xor     ecx, ecx; lpEventAttributes
0x1800d3ad5  call    cs:__imp_CreateEventW
0x1800d3adc  nop     dword ptr [rax+rax+00h]
0x1800d3ae1  lea     r12, [rsi+8]
0x1800d3ae5  mov     rdx, rax
0x1800d3ae8  mov     rcx, r12
0x1800d3aeb  call    ?TakeOwnership@?$AutoComPtr@VCCbsCancelSessionExecutionObject@@@Windows@@QEAAXPEAVCCbsCancelSessionExecutionObject@@@Z; Windows::AutoComPtr<CCbsCancelSessionExecutionObject>::TakeOwnership(CCbsCancelSessionExecutionObject *)
0x1800d3af0  cmp     qword ptr [r12], 0
0x1800d3af5  jnz     loc_1800D3B9F
0x1800d3afb  call    cs:__imp_GetLastError
0x1800d3b02  nop     dword ptr [rax+rax+00h]
0x1800d3b07  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1800d3b0e  mov     ebx, eax
0x1800d3b10  test    rcx, rcx
0x1800d3b13  jz      short loc_1800D3B67
0x1800d3b15  mov     edi, 3
0x1800d3b1a  lea     r9, aCreateeventfai; "CreateEventFailed"
0x1800d3b21  mov     r8d, edi
0x1800d3b24  xor     edx, edx
0x1800d3b26  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x1800d3b2b  test    ebx, ebx
0x1800d3b2d  jg      short loc_1800D3B33
0x1800d3b2f  mov     eax, ebx
0x1800d3b31  jmp     short loc_1800D3B3B
0x1800d3b33  movzx   eax, bx
0x1800d3b36  or      eax, 80070000h
0x1800d3b3b  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1800d3b42  lea     r9, a0; ": {0}"
0x1800d3b49  mov     [rbp+var_10], eax
0x1800d3b4c  mov     r8d, edi
0x1800d3b4f  lea     rax, [rbp+var_10]
0x1800d3b53  mov     dl, 1
0x1800d3b55  mov     qword ptr [rbp+var_30], rax
0x1800d3b59  lea     rax, [rbp+var_30]
0x1800d3b5d  mov     qword ptr [rsp+60h+var_40], rax; unsigned int
0x1800d3b62  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x1800d3b67  test    ebx, ebx
0x1800d3b69  jz      short loc_1800D3B92
0x1800d3b6b  mov     rcx, [rbp+28h]; this
0x1800d3b6f  lea     r8, aOnecoreBaseCbs_68; "onecore\\base\\cbs\\core\\executionengi"...
0x1800d3b76  mov     r9d, ebx; char *
0x1800d3b79  mov     edx, 6Dh ; 'm'; void *
0x1800d3b7e  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x1800d3b83  mov     ebx, eax
0x1800d3b85  mov     rcx, rsi; this
0x1800d3b88  call    ??_GRequestingThreadInfo@CCbsEngineLock@@QEAAPEAXI@Z; CCbsEngineLock::RequestingThreadInfo::`scalar deleting destructor'(uint)
0x1800d3b8d  jmp     loc_1800D3EDD
0x1800d3b92  mov     rcx, rsi; this
0x1800d3b95  call    ??_GRequestingThreadInfo@CCbsEngineLock@@QEAAPEAXI@Z; CCbsEngineLock::RequestingThreadInfo::`scalar deleting destructor'(uint)
0x1800d3b9a  jmp     loc_1800D3A8A
0x1800d3b9f  mov     r8, rsi
0x1800d3ba2  lea     rdx, aEngineAddThrea; "Engine: Add thread to the execution wai"...
0x1800d3ba9  mov     ecx, 1
0x1800d3bae  call    ??$TraceAtLevel@K@LogAdapter@@YAXW4LogLevel@0@QEBDAEBK@Z; LogAdapter::TraceAtLevel<ulong>(LogAdapter::LogLevel,char const * const,ulong const &)
0x1800d3bb3  mov     qword ptr [rbp+var_30], rsi
0x1800d3bb7  lea     r14, [rdi+28h]
0x1800d3bbb  lea     rdx, [rbp+var_30]
0x1800d3bbf  mov     rcx, r14
0x1800d3bc2  test    r15b, r15b
0x1800d3bc5  jz      short loc_1800D3BEF
0x1800d3bc7  xor     r8d, r8d
0x1800d3bca  call    ?InsertAt@?$CCbsArrayBase@PEAUComponentVersion@AnalyzerStore@@V?$CCbsPointerArray@PEAUComponentVersion@AnalyzerStore@@@@@@QEAAJAEBQEAUComponentVersion@AnalyzerStore@@_K@Z; CCbsArrayBase<AnalyzerStore::ComponentVersion *,CCbsPointerArray<AnalyzerStore::ComponentVersion *>>::InsertAt(AnalyzerStore::ComponentVersion * const &,unsigned __int64)
0x1800d3bcf  mov     ebx, eax
0x1800d3bd1  test    eax, eax
0x1800d3bd3  jns     short loc_1800D3C01
0x1800d3bd5  mov     edx, 75h ; 'u'; void *
0x1800d3bda  mov     rcx, [rbp+28h]; this
0x1800d3bde  lea     r8, aOnecoreBaseCbs_68; "onecore\\base\\cbs\\core\\executionengi"...
0x1800d3be5  mov     r9d, eax; char *
0x1800d3be8  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800d3bed  jmp     short loc_1800D3B85
0x1800d3bef  call    ?Add@?$CCbsArrayBase@PEAURequestingThreadInfo@CCbsEngineLock@@V?$CCbsPointerArray@PEAURequestingThreadInfo@CCbsEngineLock@@@@@@QEAAJAEBQEAURequestingThreadInfo@CCbsEngineLock@@@Z; CCbsArrayBase<CCbsEngineLock::RequestingThreadInfo *,CCbsPointerArray<CCbsEngineLock::RequestingThreadInfo *>>::Add(CCbsEngineLock::RequestingThreadInfo * const &)
0x1800d3bf4  mov     ebx, eax
0x1800d3bf6  test    eax, eax
0x1800d3bf8  jns     short loc_1800D3C01
0x1800d3bfa  mov     edx, 79h ; 'y'
0x1800d3bff  jmp     short loc_1800D3BDA
0x1800d3c01  lea     rcx, [rbp+var_28]; this
0x1800d3c05  call    ?Unlock@CritSecLocker@@UEAAXXZ; CritSecLocker::Unlock(void)
0x1800d3c0a  mov     rcx, [r12]; hHandle
0x1800d3c0e  mov     ebx, 0FFFFFFFFh
0x1800d3c13  mov     edx, ebx; dwMilliseconds
0x1800d3c15  call    cs:__imp_WaitForSingleObject
0x1800d3c1c  nop     dword ptr [rax+rax+00h]
0x1800d3c21  test    eax, eax
0x1800d3c23  jz      loc_1800D3CBC
0x1800d3c29  call    cs:__imp_GetLastError
0x1800d3c30  nop     dword ptr [rax+rax+00h]
0x1800d3c35  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1800d3c3c  mov     ebx, eax
0x1800d3c3e  test    rcx, rcx
0x1800d3c41  jz      short loc_1800D3C95
0x1800d3c43  mov     edi, 3
0x1800d3c48  lea     r9, aWaitFailed; "Wait failed"
0x1800d3c4f  mov     r8d, edi
0x1800d3c52  xor     edx, edx
0x1800d3c54  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x1800d3c59  test    ebx, ebx
0x1800d3c5b  jg      short loc_1800D3C61
0x1800d3c5d  mov     eax, ebx
0x1800d3c5f  jmp     short loc_1800D3C69
0x1800d3c61  movzx   eax, bx
0x1800d3c64  or      eax, 80070000h
0x1800d3c69  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1800d3c70  lea     r9, a0; ": {0}"
0x1800d3c77  mov     [rbp+var_10], eax
0x1800d3c7a  mov     r8d, edi
0x1800d3c7d  lea     rax, [rbp+var_10]
0x1800d3c81  mov     dl, 1
0x1800d3c83  mov     qword ptr [rbp+var_30], rax
0x1800d3c87  lea     rax, [rbp+var_30]
0x1800d3c8b  mov     qword ptr [rsp+60h+var_40], rax; unsigned int
0x1800d3c90  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x1800d3c95  test    ebx, ebx
0x1800d3c97  jz      loc_1800D3E65
0x1800d3c9d  mov     rcx, [rbp+28h]; this
0x1800d3ca1  lea     r8, aOnecoreBaseCbs_68; "onecore\\base\\cbs\\core\\executionengi"...
0x1800d3ca8  mov     r9d, ebx; char *
0x1800d3cab  mov     edx, 83h; void *
0x1800d3cb0  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x1800d3cb5  mov     ebx, eax
0x1800d3cb7  jmp     loc_1800D3EDD
0x1800d3cbc  lea     rcx, [rbp+var_28]; this
0x1800d3cc0  call    ?Lock@CritSecLocker@@UEAAXXZ; CritSecLocker::Lock(void)
0x1800d3cc5  cmp     byte ptr [rdi+6Ch], 0
0x1800d3cc9  jz      short loc_1800D3D28
0x1800d3ccb  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1800d3cd2  mov     ebx, 800F0827h
0x1800d3cd7  mov     [rbp+var_10], ebx
0x1800d3cda  test    rcx, rcx
0x1800d3cdd  jz      short loc_1800D3D1E
0x1800d3cdf  mov     edi, 3
0x1800d3ce4  lea     r9, aExecutionEngin_1; "Execution engine queue deactivated"
0x1800d3ceb  mov     r8d, edi
0x1800d3cee  xor     edx, edx
0x1800d3cf0  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x1800d3cf5  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1800d3cfc  lea     rax, [rbp+var_10]
0x1800d3d00  mov     qword ptr [rbp+var_30], rax
0x1800d3d04  lea     r9, asc_1802EE7AC; ": {}"
0x1800d3d0b  lea     rax, [rbp+var_30]
0x1800d3d0f  mov     r8d, edi
0x1800d3d12  mov     dl, 1
0x1800d3d14  mov     qword ptr [rsp+60h+var_40], rax
0x1800d3d19  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x1800d3d1e  mov     edx, 88h
0x1800d3d23  jmp     loc_1800D3ECA
0x1800d3d28  mov     eax, [rsi]
0x1800d3d2a  cmp     [rdi+68h], eax
0x1800d3d2d  jz      short loc_1800D3D8C
0x1800d3d2f  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1800d3d36  mov     ebx, 800F0800h
0x1800d3d3b  mov     [rbp+var_10], ebx
0x1800d3d3e  test    rcx, rcx
0x1800d3d41  jz      short loc_1800D3D82
0x1800d3d43  mov     edi, 3
0x1800d3d48  lea     r9, aUnexpectedOwni; "Unexpected, owning thread is not the cu"...
0x1800d3d4f  mov     r8d, edi
0x1800d3d52  xor     edx, edx
0x1800d3d54  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x1800d3d59  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1800d3d60  lea     rax, [rbp+var_10]
0x1800d3d64  mov     qword ptr [rbp+var_30], rax
0x1800d3d68  lea     r9, asc_1802EE7AC; ": {}"
0x1800d3d6f  lea     rax, [rbp+var_30]
0x1800d3d73  mov     r8d, edi
0x1800d3d76  mov     dl, 1
0x1800d3d78  mov     qword ptr [rsp+60h+var_40], rax
0x1800d3d7d  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x1800d3d82  mov     edx, 8Ch
0x1800d3d87  jmp     loc_1800D3ECA
0x1800d3d8c  mov     r8, rsi
0x1800d3d8f  lea     rdx, aEngineThreadRe; "Engine: Thread ready for execution: {}"
0x1800d3d96  mov     ecx, 1
0x1800d3d9b  call    ??$TraceAtLevel@K@LogAdapter@@YAXW4LogLevel@0@QEBDAEBK@Z; LogAdapter::TraceAtLevel<ulong>(LogAdapter::LogLevel,char const * const,ulong const &)
0x1800d3da0  mov     rcx, [r14+28h]
0x1800d3da4  test    rcx, rcx
0x1800d3da7  jz      short loc_1800D3DBF
0x1800d3da9  xor     eax, eax
0x1800d3dab  cmp     rax, [r14+18h]
0x1800d3daf  jnb     short loc_1800D3DBF
0x1800d3db1  cmp     rsi, [rcx+rax*8]
0x1800d3db5  jz      short loc_1800D3DBC
0x1800d3db7  inc     rax
0x1800d3dba  jmp     short loc_1800D3DAB
0x1800d3dbc  mov     rbx, rax
0x1800d3dbf  mov     rdx, rbx
0x1800d3dc2  mov     rcx, r14
0x1800d3dc5  call    ?RemoveAt@?$CCbsPointerArray@PEAURequestingThreadInfo@CCbsEngineLock@@@@QEAAJ_K@Z; CCbsPointerArray<CCbsEngineLock::RequestingThreadInfo *>::RemoveAt(unsigned __int64)
0x1800d3dca  lea     r8, aEngineUnableTo; "Engine: Unable to remove requesting thr"...
0x1800d3dd1  mov     edx, eax
0x1800d3dd3  mov     ecx, 2
0x1800d3dd8  call    ??$TraceAtLevelIfFailed@J$$V@LogAdapter@@YAXW4LogLevel@0@JQEBD@Z; LogAdapter::TraceAtLevelIfFailed<long,>(LogAdapter::LogLevel,long,char const * const)
0x1800d3ddd  mov     rcx, [rdi+70h]; hEvent
0x1800d3de1  call    cs:__imp_ResetEvent
0x1800d3de8  nop     dword ptr [rax+rax+00h]
0x1800d3ded  test    eax, eax
0x1800d3def  jnz     short loc_1800D3E65
0x1800d3df1  call    cs:__imp_GetLastError
0x1800d3df8  nop     dword ptr [rax+rax+00h]
0x1800d3dfd  mov     ebx, eax
0x1800d3dff  test    eax, eax
0x1800d3e01  jle     short loc_1800D3E0C
0x1800d3e03  movzx   ebx, ax
0x1800d3e06  or      ebx, 80070000h
0x1800d3e0c  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1800d3e13  mov     [rbp+var_10], ebx
0x1800d3e16  test    rcx, rcx
0x1800d3e19  jz      short loc_1800D3E5A
0x1800d3e1b  mov     edi, 3
0x1800d3e20  lea     r9, aFailedToResetI; "Failed to reset idle event"
0x1800d3e27  mov     r8d, edi
  ... truncated ...
```
