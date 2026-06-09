# FeedbackManager::~FeedbackManager(void)

- ea: `0x18000f800`
- end: `0x18000fddc`
- name: `??1FeedbackManager@@QEAA@XZ`
- size: `1500`
- prototype: `void __fastcall(FeedbackManager *__hidden this)`
- caller_count: `4`
- callee_count: `9`
- tags: `file_ops, loader_planting`

## callers

- `0x180012684`
- `0x18002cdd4`
- `0x18002d4a4`
- `0x18002da74`

## callees

- `0x180001304`
- `0x180001540`
- `0x180001e28`
- `0x180001f38`
- `0x18000c11c`
- `0x18000d658`
- `0x18000d68c`
- `0x18000f800`
- `0x18000fde4`

## import_xrefs

- `ntdll!NtWaitForSingleObject` at `0x18000f9c8`
- `ntdll!NtWaitForSingleObject` at `0x18000fbc0`
- `ntdll!NtWaitForSingleObject` at `0x18000f9c8`
- `ntdll!NtWaitForSingleObject` at `0x18000fbc0`
- `ntdll!NtAlertThread` at `0x18000f8f6`
- `ntdll!NtAlertThread` at `0x18000f8f6`
- `api-ms-win-core-synch-l1-1-0!TryAcquireSRWLockExclusive` at `0x18000f987`
- `api-ms-win-core-synch-l1-1-0!TryAcquireSRWLockExclusive` at `0x18000f987`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000fb87`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000fb87`
- `api-ms-win-core-processthreads-l1-1-0!GetThreadId` at `0x18000f840`
- `api-ms-win-core-processthreads-l1-1-0!GetThreadId` at `0x18000f840`
- `api-ms-win-core-processthreads-l1-1-0!SuspendThread` at `0x18000faa5`
- `api-ms-win-core-processthreads-l1-1-0!SuspendThread` at `0x18000faa5`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000fc8e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000fc8e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000fc9e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000fda7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000fc9e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000fda7`

## string_xrefs

- `0x18000f899`: `Stopping feedback worker thread`
- `0x18000fc30`: `Feedback worker thread abandoned`
- `0x18000fb33`: `Feedback worker thread leaked`
- `0x18000fa40`: `Unexpected failure waiting for feedback worker thread`

## pseudocode

```c
void __fastcall FeedbackManager::~FeedbackManager(HANDLE *this, __int64 a2, int a3, int a4)
{
  __int64 v5; // r15
  int v6; // r8d
  int v7; // r9d
  DWORD ThreadId; // r14d
  __int64 v9; // rcx
  __int64 v10; // rax
  __int64 v11; // rdx
  __int64 v12; // rcx
  NTSTATUS v13; // r8d
  int v14; // r9d
  unsigned __int64 v15; // rsi
  unsigned __int64 v16; // rdi
  __int64 v17; // rax
  HANDLE v18; // rcx
  NTSTATUS v19; // eax
  int v20; // r9d
  NTSTATUS v21; // r8d
  __int64 v22; // rax
  int v23; // r8d
  int v24; // r9d
  __int64 v25; // rax
  union _LARGE_INTEGER v26; // rax
  HANDLE v27; // rcx
  NTSTATUS v28; // eax
  int v29; // r8d
  int v30; // r9d
  __int64 v31; // rcx
  __int64 v32; // rax
  DWORD v33; // eax
  __int64 v34; // rcx
  volatile signed __int8 *v35; // rbx
  const struct std::nothrow_t *v36; // rdx
  signed int LastError; // eax
  const char *v38; // [rsp+50h] [rbp-9h] BYREF
  const char *v39; // [rsp+58h] [rbp-1h] BYREF
  __int16 v40; // [rsp+60h] [rbp+7h]
  __int64 v41; // [rsp+68h] [rbp+Fh] BYREF
  __int16 v42; // [rsp+70h] [rbp+17h]
  int v43; // [rsp+C0h] [rbp+67h] BYREF
  const char *v44; // [rsp+C8h] [rbp+6Fh] BYREF
  const char *v45; // [rsp+D0h] [rbp+77h] BYREF
  union _LARGE_INTEGER Timeout; // [rsp+D8h] [rbp+7Fh] BYREF

  if ( *this )
  {
    if ( this[1] )
    {
      v5 = GameInputCurrentTime(this, a2);
      ThreadId = GetThreadId(this[1]);
      if ( (unsigned int)dword_180069000 > 4 && (qword_180069010 & 8) != 0 )
      {
        v9 = qword_180069018 & 8;
        if ( v9 == qword_180069018 )
        {
          v10 = (__int64)*this + 172;
          v40 = 32;
          v39 = (const char *)v10;
          v45 = "Stopping feedback worker thread";
          v43 = ThreadId;
          LODWORD(v44) = 28;
          Timeout.QuadPart = (LONGLONG)"onecore\\xbox\\gameinput\\feedback\\FeedbackManager.cpp";
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_GameInputEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperArray<1>>(
            v9,
            (unsigned int)&word_18005D956,
            v6,
            v7,
            (__int64)&Timeout,
            (__int64)&v44,
            (__int64)&v45,
            (__int64)&v43,
            (__int64)&v39);
        }
      }
      _InterlockedOr8((volatile signed __int8 *)*this + 169, 8u);
      v13 = NtAlertThread(this[1]);
      if ( v13 < 0 )
      {
        v12 = (unsigned int)dword_180069000;
        if ( (unsigned int)dword_180069000 > 2 )
        {
          v11 = qword_180069018;
          v12 = qword_180069010;
          if ( (qword_180069010 & 8) != 0 && (qword_180069018 & 8) == qword_180069018 )
          {
            v43 = v13;
            LODWORD(v44) = 32;
            v45 = "onecore\\xbox\\gameinput\\feedback\\FeedbackManager.cpp";
            _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_GameInputEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
              qword_180069010,
              (unsigned int)&byte_18005E00F,
              v13,
              v14,
              (__int64)&v45,
              (__int64)&v44,
              (__int64)&v43);
          }
        }
      }
      while ( 1 )
      {
        v15 = GameInputCurrentTime(v12, v11) - v5;
        v16 = (100000 - v15) & -(__int64)(v15 < 0x186A0);
        if ( TryAcquireSRWLockExclusive((PSRWLOCK)*this) )
          break;
        if ( v15 >= 0x186A0 )
        {
          if ( SuspendThread(this[1]) == -1 )
          {
            LastError = GetLastError();
            if ( LastError > 0 )
              LastError = (unsigned __int16)LastError | 0x80070000;
            GameInputFailFast((unsigned int)LastError, 104);
            __debugbreak();
          }
          if ( ++FeedbackManager::s_leakedWorkerThreadCount > 5u )
          {
            GameInputFailFast(2147942414LL, 105);
            JUMPOUT(0x18000FDDBLL);
          }
          if ( (unsigned int)dword_180069000 > 2
            && (qword_180069010 & 8) != 0
            && (qword_180069018 & 8) == qword_180069018 )
          {
            v25 = (__int64)*this + 172;
            v43 = ThreadId;
            v41 = v25;
            LODWORD(v44) = 110;
            v42 = 32;
            v45 = "Feedback worker thread leaked";
            Timeout.QuadPart = (LONGLONG)"onecore\\xbox\\gameinput\\feedback\\FeedbackManager.cpp";
            _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_GameInputEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperArray<1>>(
              qword_180069018,
              (unsigned int)byte_18005B043,
              v23,
              v24,
              (__int64)&Timeout,
              (__int64)&v44,
              (__int64)&v45,
              (__int64)&v43,
              (__int64)&v41);
          }
          goto LABEL_36;
        }
        v17 = 2000;
        v18 = this[1];
        if ( v16 < 0x7D0 )
          v17 = (100000 - v15) & -(__int64)(v15 < 0x186A0);
        Timeout.QuadPart = -10 * v17;
        v19 = NtWaitForSingleObject(v18, 0, &Timeout);
        v21 = v19;
        if ( !v19 )
          goto LABEL_36;
        if ( v19 != 258 )
        {
          v12 = (unsigned int)dword_180069000;
          if ( (unsigned int)dword_180069000 > 2 )
          {
            v11 = qword_180069018;
            v12 = qword_180069010;
            if ( (qword_180069010 & 8) != 0 && (qword_180069018 & 8) == qword_180069018 )
            {
              v22 = (__int64)*this + 172;
              v43 = v21;
              v41 = v22;
              v42 = 32;
              v38 = "Unexpected failure waiting for feedback worker thread";
              v39 = "onecore\\xbox\\gameinput\\feedback\\FeedbackManager.cpp";
              LODWORD(v44) = ThreadId;
              LODWORD(v45) = 135;
              _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_GameInputEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperArray<1>,_tlgWrapperByVal<4>>(
                qword_180069010,
                (unsigned int)&dword_18005AFE4,
                v21,
                v20,
                (__int64)&v39,
                (__int64)&v45,
                (__int64)&v38,
                (__int64)&v44,
                (__int64)&v41,
                (__int64)&v43);
            }
          }
        }
      }
      *((_QWORD *)*this + 2) = 0;
      ReleaseSRWLockExclusive((PSRWLOCK)*this);
      if ( v16 > 0xCCCCCCCCCCCCCCCLL )
        v26.QuadPart = 0x8000000000000000uLL;
      else
        v26.QuadPart = -10LL * v16;
      v27 = this[1];
      Timeout = v26;
      v28 = NtWaitForSingleObject(v27, 0, &Timeout);
      if ( v28 )
      {
        if ( (unsigned int)dword_180069000 > 3 && (qword_180069010 & 8) != 0 )
        {
          v31 = qword_180069018 & 8;
          if ( v31 == qword_180069018 )
          {
            v43 = v28;
            v32 = (__int64)*this + 172;
            LODWORD(v44) = ThreadId;
            v41 = v32;
            v42 = 32;
            v39 = "Feedback worker thread abandoned";
            LODWORD(v45) = 83;
            v38 = "onecore\\xbox\\gameinput\\feedback\\FeedbackManager.cpp";
            _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_GameInputEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperArray<1>,_tlgWrapperByVal<4>>(
              v31,
              (unsigned int)byte_18005CC4B,
              v29,
              v30,
              (__int64)&v38,
              (__int64)&v45,
              (__int64)&v39,
              (__int64)&v44,
              (__int64)&v41,
              (__int64)&v43);
          }
        }
      }
LABEL_36:
      if ( !CloseHandle(this[1]) )
      {
        v33 = GetLastError();
        if ( (unsigned int)dword_180069000 > 2 && (qword_180069010 & 8) != 0 )
        {
          v34 = qword_180069018 & 8;
          if ( v34 == qword_180069018 )
          {
            v43 = v33;
            LODWORD(v44) = 143;
            v45 = "onecore\\xbox\\gameinput\\feedback\\FeedbackManager.cpp";
            _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_GameInputEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
              v34,
              (unsigned int)byte_18005C7B9,
              a3,
              a4,
              (__int64)&v45,
              (__int64)&v44,
              (__int64)&v43);
          }
        }
      }
    }
    v35 = (volatile signed __int8 *)*this;
    if ( _InterlockedExchangeAdd8(v35 + 204, 0xFFu) == 1 && v35 )
    {
      FeedbackManagerState::~FeedbackManagerState((FeedbackManagerState *)v35);
      operator delete((PVOID)v35, v36);
    }
  }
  if ( (unsigned int)dword_180069000 > 5 && (qword_180069010 & 8) != 0 && (qword_180069018 & 8) == qword_180069018 )
  {
    v43 = 152;
    v44 = "Feedback manager destroyed";
    v45 = "onecore\\xbox\\gameinput\\feedback\\FeedbackManager.cpp";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_GameInputEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
      qword_180069018,
      (unsigned int)&byte_18005BF47,
      a3,
      a4,
      (__int64)&v45,
      (__int64)&v43,
      (__int64)&v44);
  }
}

```

## disassembly

```asm
0x18000f800  push    rbp
0x18000f802  push    rbx
0x18000f803  push    rsi
0x18000f804  push    rdi
0x18000f805  push    r14
0x18000f807  push    r15
0x18000f809  lea     rbp, [rsp-2Fh]
0x18000f80e  sub     rsp, 88h
0x18000f815  cmp     qword ptr [rcx], 0
0x18000f819  lea     rdi, aOnecoreXboxGam_10; "onecore\\xbox\\gameinput\\feedback\\Fee"...
0x18000f820  mov     rbx, rcx
0x18000f823  jz      loc_18000FD31
0x18000f829  cmp     qword ptr [rcx+8], 0
0x18000f82e  jz      loc_18000FD08
0x18000f834  call    GameInputCurrentTime
0x18000f839  mov     rcx, [rbx+8]; Thread
0x18000f83d  mov     r15, rax
0x18000f840  call    cs:__imp_GetThreadId
0x18000f847  nop     dword ptr [rax+rax+00h]
0x18000f84c  mov     ecx, cs:dword_180069000
0x18000f852  mov     esi, 20h ; ' '
0x18000f857  mov     r14d, eax
0x18000f85a  cmp     ecx, 4
0x18000f85d  jbe     loc_18000F8E5
0x18000f863  mov     rdx, cs:qword_180069018
0x18000f86a  mov     rcx, cs:qword_180069010
0x18000f871  test    cl, 8
0x18000f874  jz      short loc_18000F8E5
0x18000f876  mov     rcx, rdx
0x18000f879  and     ecx, 8
0x18000f87c  cmp     rcx, rdx
0x18000f87f  jnz     short loc_18000F8E5
0x18000f881  mov     rax, [rbx]
0x18000f884  lea     rdx, word_18005D956
0x18000f88b  add     rax, 0ACh
0x18000f891  mov     [rbp+57h+var_50], si
0x18000f895  mov     [rbp+57h+var_58], rax
0x18000f899  lea     rax, aStoppingFeedba; "Stopping feedback worker thread"
0x18000f8a0  mov     [rbp+57h+arg_10], rax
0x18000f8a4  lea     rax, [rbp+57h+var_58]
0x18000f8a8  mov     [rsp+0B0h+var_70], rax
0x18000f8ad  lea     rax, [rbp+57h+arg_0]
0x18000f8b1  mov     [rsp+0B0h+var_78], rax
0x18000f8b6  lea     rax, [rbp+57h+arg_10]
0x18000f8ba  mov     [rsp+0B0h+var_80], rax
0x18000f8bf  lea     rax, [rbp+57h+arg_8]
0x18000f8c3  mov     [rsp+0B0h+var_88], rax
0x18000f8c8  lea     rax, [rbp+57h+Timeout]
0x18000f8cc  mov     [rsp+0B0h+var_90], rax
0x18000f8d1  mov     [rbp+57h+arg_0], r14d
0x18000f8d5  mov     dword ptr [rbp+57h+arg_8], 1Ch
0x18000f8dc  mov     qword ptr [rbp+57h+Timeout], rdi
0x18000f8e0  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U2@U?$_tlgWrapperArray@$00@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_GameInputEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@34AEBU?$_tlgWrapperArray@$00@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_GameInputEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperArray<1>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapperArray<1> const &)
0x18000f8e5  mov     rax, [rbx]
0x18000f8e8  nop
0x18000f8e9  lock or byte ptr [rax+0A9h], 8
0x18000f8f1  nop
0x18000f8f2  mov     rcx, [rbx+8]; ThreadHandle
0x18000f8f6  call    cs:__imp_NtAlertThread
0x18000f8fd  nop     dword ptr [rax+rax+00h]
0x18000f902  mov     r8d, eax
0x18000f905  test    eax, eax
0x18000f907  jns     short loc_18000F964
0x18000f909  mov     ecx, cs:dword_180069000
0x18000f90f  cmp     ecx, 2
0x18000f912  jbe     short loc_18000F964
0x18000f914  mov     rdx, cs:qword_180069018
0x18000f91b  mov     rcx, cs:qword_180069010
0x18000f922  test    cl, 8
0x18000f925  jz      short loc_18000F964
0x18000f927  mov     rax, rdx
0x18000f92a  and     eax, 8
0x18000f92d  cmp     rax, rdx
0x18000f930  jnz     short loc_18000F964
0x18000f932  lea     rax, [rbp+57h+arg_0]
0x18000f936  mov     [rbp+57h+arg_0], r8d
0x18000f93a  mov     [rsp+0B0h+var_80], rax
0x18000f93f  lea     rdx, byte_18005E00F
0x18000f946  lea     rax, [rbp+57h+arg_8]
0x18000f94a  mov     dword ptr [rbp+57h+arg_8], esi
0x18000f94d  mov     [rsp+0B0h+var_88], rax
0x18000f952  lea     rax, [rbp+57h+arg_10]
0x18000f956  mov     [rsp+0B0h+var_90], rax
0x18000f95b  mov     [rbp+57h+arg_10], rdi
0x18000f95f  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_GameInputEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_GameInputEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x18000f964  call    GameInputCurrentTime
0x18000f969  mov     rsi, rax
0x18000f96c  mov     ecx, 186A0h
0x18000f971  sub     rsi, r15
0x18000f974  sub     rcx, rsi
0x18000f977  cmp     rsi, 186A0h
0x18000f97e  sbb     rdi, rdi
0x18000f981  and     rdi, rcx
0x18000f984  mov     rcx, [rbx]; SRWLock
0x18000f987  call    cs:__imp_TryAcquireSRWLockExclusive
0x18000f98e  nop     dword ptr [rax+rax+00h]
0x18000f993  test    al, al
0x18000f995  jnz     loc_18000FB79
0x18000f99b  cmp     rsi, 186A0h
0x18000f9a2  jnb     loc_18000FAA1
0x18000f9a8  mov     ecx, 7D0h
0x18000f9ad  lea     r8, [rbp+57h+Timeout]; Timeout
0x18000f9b1  cmp     rdi, rcx
0x18000f9b4  mov     eax, ecx
0x18000f9b6  mov     rcx, [rbx+8]; Handle
0x18000f9ba  cmovb   rax, rdi
0x18000f9be  xor     edx, edx; Alertable
0x18000f9c0  imul    rax, -0Ah
0x18000f9c4  mov     qword ptr [rbp+57h+Timeout], rax
0x18000f9c8  call    cs:__imp_NtWaitForSingleObject
0x18000f9cf  nop     dword ptr [rax+rax+00h]
0x18000f9d4  mov     r8d, eax
0x18000f9d7  test    eax, eax
0x18000f9d9  jz      loc_18000FC83
0x18000f9df  cmp     eax, 102h
0x18000f9e4  jz      loc_18000F964
0x18000f9ea  mov     ecx, cs:dword_180069000
0x18000f9f0  cmp     ecx, 2
0x18000f9f3  jbe     loc_18000F964
0x18000f9f9  mov     rdx, cs:qword_180069018
0x18000fa00  mov     rcx, cs:qword_180069010
0x18000fa07  test    cl, 8
0x18000fa0a  jz      loc_18000F964
0x18000fa10  mov     rax, rdx
0x18000fa13  and     eax, 8
0x18000fa16  cmp     rax, rdx
0x18000fa19  jnz     loc_18000F964
0x18000fa1f  mov     rax, [rbx]
0x18000fa22  lea     rdx, dword_18005AFE4
0x18000fa29  add     rax, 0ACh
0x18000fa2f  mov     [rbp+57h+arg_0], r8d
0x18000fa33  mov     [rbp+57h+var_48], rax
0x18000fa37  mov     eax, 20h ; ' '
0x18000fa3c  mov     [rbp+57h+var_40], ax
0x18000fa40  lea     rax, aUnexpectedFail; "Unexpected failure waiting for feedback"...
0x18000fa47  mov     [rbp+57h+var_60], rax
0x18000fa4b  lea     rax, aOnecoreXboxGam_10; "onecore\\xbox\\gameinput\\feedback\\Fee"...
0x18000fa52  mov     [rbp+57h+var_58], rax
0x18000fa56  lea     rax, [rbp+57h+arg_0]
0x18000fa5a  mov     [rsp+0B0h+var_68], rax
0x18000fa5f  lea     rax, [rbp+57h+var_48]
0x18000fa63  mov     [rsp+0B0h+var_70], rax
0x18000fa68  lea     rax, [rbp+57h+arg_8]
0x18000fa6c  mov     [rsp+0B0h+var_78], rax
0x18000fa71  lea     rax, [rbp+57h+var_60]
0x18000fa75  mov     [rsp+0B0h+var_80], rax
0x18000fa7a  lea     rax, [rbp+57h+arg_10]
0x18000fa7e  mov     [rsp+0B0h+var_88], rax
0x18000fa83  lea     rax, [rbp+57h+var_58]
0x18000fa87  mov     [rsp+0B0h+var_90], rax
0x18000fa8c  mov     dword ptr [rbp+57h+arg_8], r14d
0x18000fa90  mov     dword ptr [rbp+57h+arg_10], 87h
0x18000fa97  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U2@U?$_tlgWrapperArray@$00@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_GameInputEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@34AEBU?$_tlgWrapperArray@$00@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_GameInputEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperArray<1>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapperArray<1> const &,_tlgWrapperByVal<4> const &)
0x18000fa9c  jmp     loc_18000F964
0x18000faa1  mov     rcx, [rbx+8]; hThread
0x18000faa5  call    cs:__imp_SuspendThread
0x18000faac  nop     dword ptr [rax+rax+00h]
0x18000fab1  cmp     eax, 0FFFFFFFFh
0x18000fab4  jz      loc_18000FDA7
0x18000faba  mov     al, cs:?s_leakedWorkerThreadCount@FeedbackManager@@0EA; uchar FeedbackManager::s_leakedWorkerThreadCount
0x18000fac0  inc     al
0x18000fac2  mov     cs:?s_leakedWorkerThreadCount@FeedbackManager@@0EA, al; uchar FeedbackManager::s_leakedWorkerThreadCount
0x18000fac8  cmp     al, 5
0x18000faca  ja      loc_18000FDCC
0x18000fad0  mov     eax, cs:dword_180069000
0x18000fad6  cmp     eax, 2
0x18000fad9  jbe     loc_18000FC83
0x18000fadf  mov     rcx, cs:qword_180069018
0x18000fae6  mov     rax, cs:qword_180069010
0x18000faed  test    al, 8
0x18000faef  jz      loc_18000FC83
0x18000faf5  mov     rax, rcx
0x18000faf8  and     eax, 8
0x18000fafb  cmp     rax, rcx
0x18000fafe  jnz     loc_18000FC83
0x18000fb04  mov     rax, [rbx]
0x18000fb07  lea     rdi, aOnecoreXboxGam_10; "onecore\\xbox\\gameinput\\feedback\\Fee"...
0x18000fb0e  add     rax, 0ACh
0x18000fb14  mov     [rbp+57h+arg_0], r14d
0x18000fb18  mov     [rbp+57h+var_48], rax
0x18000fb1c  lea     rdx, byte_18005B043
0x18000fb23  mov     eax, 20h ; ' '
0x18000fb28  mov     dword ptr [rbp+57h+arg_8], 6Eh ; 'n'
0x18000fb2f  mov     [rbp+57h+var_40], ax
0x18000fb33  lea     rax, aFeedbackWorker_0; "Feedback worker thread leaked"
0x18000fb3a  mov     [rbp+57h+arg_10], rax
0x18000fb3e  lea     rax, [rbp+57h+var_48]
0x18000fb42  mov     [rsp+0B0h+var_70], rax
0x18000fb47  lea     rax, [rbp+57h+arg_0]
0x18000fb4b  mov     [rsp+0B0h+var_78], rax
0x18000fb50  lea     rax, [rbp+57h+arg_10]
0x18000fb54  mov     [rsp+0B0h+var_80], rax
0x18000fb59  lea     rax, [rbp+57h+arg_8]
0x18000fb5d  mov     [rsp+0B0h+var_88], rax
0x18000fb62  lea     rax, [rbp+57h+Timeout]
0x18000fb66  mov     [rsp+0B0h+var_90], rax
0x18000fb6b  mov     qword ptr [rbp+57h+Timeout], rdi
0x18000fb6f  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U2@U?$_tlgWrapperArray@$00@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_GameInputEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@34AEBU?$_tlgWrapperArray@$00@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_GameInputEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperArray<1>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapperArray<1> const &)
0x18000fb74  jmp     loc_18000FC8A
0x18000fb79  mov     rax, [rbx]
0x18000fb7c  mov     qword ptr [rax+10h], 0
0x18000fb84  mov     rcx, [rbx]; SRWLock
0x18000fb87  call    cs:__imp_ReleaseSRWLockExclusive
0x18000fb8e  nop     dword ptr [rax+rax+00h]
0x18000fb93  mov     rax, 0CCCCCCCCCCCCCCCh
0x18000fb9d  cmp     rdi, rax
0x18000fba0  ja      short loc_18000FBA8
0x18000fba2  imul    rax, rdi, -0Ah
0x18000fba6  jmp     short loc_18000FBB2
0x18000fba8  mov     rax, 8000000000000000h
0x18000fbb2  mov     rcx, [rbx+8]; Handle
0x18000fbb6  lea     r8, [rbp+57h+Timeout]; Timeout
0x18000fbba  xor     edx, edx; Alertable
0x18000fbbc  mov     qword ptr [rbp+57h+Timeout], rax
0x18000fbc0  call    cs:__imp_NtWaitForSingleObject
0x18000fbc7  nop     dword ptr [rax+rax+00h]
0x18000fbcc  test    eax, eax
0x18000fbce  jz      loc_18000FC83
0x18000fbd4  mov     ecx, cs:dword_180069000
0x18000fbda  cmp     ecx, 3
0x18000fbdd  jbe     loc_18000FC83
0x18000fbe3  mov     rdx, cs:qword_180069018
0x18000fbea  mov     rcx, cs:qword_180069010
0x18000fbf1  test    cl, 8
0x18000fbf4  jz      loc_18000FC83
0x18000fbfa  mov     rcx, rdx
0x18000fbfd  and     ecx, 8
0x18000fc00  cmp     rcx, rdx
0x18000fc03  jnz     short loc_18000FC83
0x18000fc05  mov     [rbp+57h+arg_0], eax
0x18000fc08  lea     rdi, aOnecoreXboxGam_10; "onecore\\xbox\\gameinput\\feedback\\Fee"...
0x18000fc0f  mov     rax, [rbx]
0x18000fc12  lea     rdx, byte_18005CC4B
0x18000fc19  add     rax, 0ACh
0x18000fc1f  mov     dword ptr [rbp+57h+arg_8], r14d
0x18000fc23  mov     [rbp+57h+var_48], rax
0x18000fc27  mov     eax, 20h ; ' '
0x18000fc2c  mov     [rbp+57h+var_40], ax
0x18000fc30  lea     rax, aFeedbackWorker; "Feedback worker thread abandoned"
0x18000fc37  mov     [rbp+57h+var_58], rax
0x18000fc3b  lea     rax, [rbp+57h+arg_0]
0x18000fc3f  mov     [rsp+0B0h+var_68], rax
0x18000fc44  lea     rax, [rbp+57h+var_48]
0x18000fc48  mov     [rsp+0B0h+var_70], rax
0x18000fc4d  lea     rax, [rbp+57h+arg_8]
0x18000fc51  mov     [rsp+0B0h+var_78], rax
0x18000fc56  lea     rax, [rbp+57h+var_58]
0x18000fc5a  mov     [rsp+0B0h+var_80], rax
0x18000fc5f  lea     rax, [rbp+57h+arg_10]
0x18000fc63  mov     [rsp+0B0h+var_88], rax
0x18000fc68  lea     rax, [rbp+57h+var_60]
0x18000fc6c  mov     [rsp+0B0h+var_90], rax
0x18000fc71  mov     dword ptr [rbp+57h+arg_10], 53h ; 'S'
0x18000fc78  mov     [rbp+57h+var_60], rdi
0x18000fc7c  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U2@U?$_tlgWrapperArray@$00@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_GameInputEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@34AEBU?$_tlgWrapperArray@$00@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_GameInputEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperArray<1>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapperArray<1> const &,_tlgWrapperByVal<4> const &)
0x18000fc81  jmp     short loc_18000FC8A
0x18000fc83  lea     rdi, aOnecoreXboxGam_10; "onecore\\xbox\\gameinput\\feedback\\Fee"...
0x18000fc8a  mov     rcx, [rbx+8]; hObject
0x18000fc8e  call    cs:__imp_CloseHandle
0x18000fc95  nop     dword ptr [rax+rax+00h]
0x18000fc9a  test    eax, eax
0x18000fc9c  jnz     short loc_18000FD08
0x18000fc9e  call    cs:__imp_GetLastError
0x18000fca5  nop     dword ptr [rax+rax+00h]
0x18000fcaa  mov     ecx, cs:dword_180069000
0x18000fcb0  cmp     ecx, 2
0x18000fcb3  jbe     short loc_18000FD08
0x18000fcb5  mov     rdx, cs:qword_180069018
0x18000fcbc  mov     rcx, cs:qword_180069010
0x18000fcc3  test    cl, 8
0x18000fcc6  jz      short loc_18000FD08
0x18000fcc8  mov     rcx, rdx
0x18000fccb  and     ecx, 8
0x18000fcce  cmp     rcx, rdx
0x18000fcd1  jnz     short loc_18000FD08
0x18000fcd3  mov     [rbp+57h+arg_0], eax
0x18000fcd6  lea     rdx, byte_18005C7B9
0x18000fcdd  lea     rax, [rbp+57h+arg_0]
0x18000fce1  mov     dword ptr [rbp+57h+arg_8], 8Fh
0x18000fce8  mov     [rsp+0B0h+var_80], rax
0x18000fced  lea     rax, [rbp+57h+arg_8]
0x18000fcf1  mov     [rsp+0B0h+var_88], rax
0x18000fcf6  lea     rax, [rbp+57h+arg_10]
0x18000fcfa  mov     [rsp+0B0h+var_90], rax
0x18000fcff  mov     [rbp+57h+arg_10], rdi
0x18000fd03  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_GameInputEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_GameInputEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x18000fd08  mov     rbx, [rbx]
0x18000fd0b  or      eax, 0FFFFFFFFh
0x18000fd0e  nop
0x18000fd0f  lock xadd [rbx+0CCh], al
0x18000fd17  nop
0x18000fd18  cmp     al, 1
0x18000fd1a  jnz     short loc_18000FD31
0x18000fd1c  test    rbx, rbx
0x18000fd1f  jz      short loc_18000FD31
0x18000fd21  mov     rcx, rbx; this
0x18000fd24  call    ??1FeedbackManagerState@@AEAA@XZ; FeedbackManagerState::~FeedbackManagerState(void)
0x18000fd29  mov     rcx, rbx; P
0x18000fd2c  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18000fd31  mov     eax, cs:dword_180069000
  ... truncated ...
```
