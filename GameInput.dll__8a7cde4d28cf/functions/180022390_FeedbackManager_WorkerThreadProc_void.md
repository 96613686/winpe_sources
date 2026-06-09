# FeedbackManager::WorkerThreadProc(void *)

- ea: `0x180022390`
- end: `0x180022c19`
- name: `?WorkerThreadProc@FeedbackManager@@CAKPEAX@Z`
- size: `2185`
- prototype: `ULONG __stdcall(PVOID Parameter)`
- caller_count: `0`
- callee_count: `12`
- tags: `file_ops, loader_planting, installer_update, broker_com_uri`

## callees

- `0x180001304`
- `0x180001e28`
- `0x18000c11c`
- `0x18000d658`
- `0x18000ea74`
- `0x18000fde4`
- `0x18001a274`
- `0x18001a730`
- `0x18001ef98`
- `0x180021f3c`
- `0x180022390`
- `0x18004d010`

## import_xrefs

- `ntdll!RtlAllocateHeap` at `0x180022a09`
- `ntdll!RtlAllocateHeap` at `0x180022a09`
- `ntdll!NtDelayExecution` at `0x18002253f`
- `ntdll!NtDelayExecution` at `0x180022b32`
- `ntdll!NtDelayExecution` at `0x18002253f`
- `ntdll!NtDelayExecution` at `0x180022b32`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800227f7`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800227f7`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180022806`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180022806`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadPriority` at `0x18002246a`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadPriority` at `0x18002246a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180022456`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180022456`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800223f8`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18002260e`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800226b5`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180022779`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180022868`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180022996`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180022b80`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800223f8`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18002260e`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800226b5`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180022779`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180022868`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180022996`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180022b80`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002247c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002247c`

## string_xrefs

- `0x180022415`: `Starting feedback manager worker thread`
- `0x18002262b`: `Initial wait for device quiesce completed`
- `0x180022b9d`: `Exiting feedback manager worker thread`

## pseudocode

```c
__int64 __fastcall FeedbackManager::WorkerThreadProc(char *Parameter)
{
  DWORD CurrentThreadId; // eax
  int v3; // ecx
  int v4; // r8d
  int v5; // r9d
  HANDLE CurrentThread; // rax
  unsigned __int64 v7; // rdx
  __int64 v8; // rcx
  DWORD LastError; // eax
  int v10; // r8d
  int v11; // r9d
  unsigned __int64 v12; // rax
  unsigned __int64 v13; // rcx
  unsigned __int64 v14; // rcx
  LARGE_INTEGER v15; // rax
  char v16; // di
  DWORD v17; // eax
  int v18; // ecx
  int v19; // r8d
  int v20; // r9d
  DWORD v21; // eax
  int v22; // ecx
  int v23; // r8d
  int v24; // r9d
  GipQuiesceWatcher *v25; // rcx
  DWORD v26; // eax
  int v27; // ecx
  int v28; // r8d
  int v29; // r9d
  DWORD v30; // eax
  int v31; // ecx
  int v32; // r8d
  int v33; // r9d
  __int64 v34; // rcx
  __int64 v35; // rax
  void *v36; // rcx
  DWORD v37; // eax
  int v38; // ecx
  int v39; // r8d
  int v40; // r9d
  char *Heap; // rdi
  int v42; // r8d
  int v43; // r9d
  struct Windows::Gaming::Input::Custom::IGipGameControllerProvider *v44; // rdx
  __int64 v45; // rax
  unsigned __int64 updated; // rax
  unsigned __int64 v47; // rdi
  unsigned __int64 v48; // rax
  DWORD v49; // eax
  int v50; // ecx
  int v51; // r8d
  int v52; // r9d
  const struct std::nothrow_t *v53; // rdx
  LARGE_INTEGER Interval; // [rsp+50h] [rbp-79h] BYREF
  const char *v56; // [rsp+58h] [rbp-71h] BYREF
  union _LARGE_INTEGER v57[2]; // [rsp+60h] [rbp-69h] BYREF
  __int128 v58; // [rsp+70h] [rbp-59h]
  DWORD v59; // [rsp+80h] [rbp-49h] BYREF
  int v60; // [rsp+84h] [rbp-45h] BYREF
  DWORD v61; // [rsp+88h] [rbp-41h] BYREF
  int v62; // [rsp+8Ch] [rbp-3Dh] BYREF
  DWORD v63; // [rsp+90h] [rbp-39h] BYREF
  int v64; // [rsp+94h] [rbp-35h] BYREF
  char *v65; // [rsp+98h] [rbp-31h] BYREF
  __int16 v66; // [rsp+A0h] [rbp-29h]
  char *v67; // [rsp+A8h] [rbp-21h] BYREF
  __int16 v68; // [rsp+B0h] [rbp-19h]
  char *v69; // [rsp+B8h] [rbp-11h] BYREF
  __int16 v70; // [rsp+C0h] [rbp-9h]
  char *v71; // [rsp+C8h] [rbp-1h] BYREF
  __int16 v72; // [rsp+D0h] [rbp+7h]
  char *v73; // [rsp+D8h] [rbp+Fh] BYREF
  __int16 v74; // [rsp+E0h] [rbp+17h]
  DWORD v75; // [rsp+130h] [rbp+67h] BYREF
  int v76; // [rsp+138h] [rbp+6Fh] BYREF
  const char *v77; // [rsp+140h] [rbp+77h] BYREF
  const char *v78; // [rsp+148h] [rbp+7Fh] BYREF

  if ( (unsigned int)dword_180069000 > 5 && (qword_180069010 & 8) != 0 && (qword_180069018 & 8) == qword_180069018 )
  {
    LOWORD(v57[1].LowPart) = 32;
    v57[0].QuadPart = (LONGLONG)(Parameter + 172);
    CurrentThreadId = GetCurrentThreadId();
    v76 = 586;
    v75 = CurrentThreadId;
    v77 = "Starting feedback manager worker thread";
    v78 = "onecore\\xbox\\gameinput\\feedback\\FeedbackManager.cpp";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_GameInputEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperArray<1>>(
      v3,
      (unsigned int)&byte_18005DBC7,
      v4,
      v5,
      (__int64)&v78,
      (__int64)&v76,
      (__int64)&v77,
      (__int64)&v75,
      (__int64)v57);
  }
  CurrentThread = GetCurrentThread();
  if ( !SetThreadPriority(CurrentThread, 2) )
  {
    LastError = GetLastError();
    v8 = (unsigned int)dword_180069000;
    if ( (unsigned int)dword_180069000 > 2 )
    {
      v7 = qword_180069018;
      v8 = qword_180069010;
      if ( (qword_180069010 & 8) != 0 )
      {
        v8 = qword_180069018 & 8;
        if ( v8 == qword_180069018 )
        {
          v75 = LastError;
          v76 = 591;
          v77 = "onecore\\xbox\\gameinput\\feedback\\FeedbackManager.cpp";
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_GameInputEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
            v8,
            (unsigned int)byte_18005DF55,
            v10,
            v11,
            (__int64)&v77,
            (__int64)&v76,
            (__int64)&v75);
        }
      }
    }
  }
  while ( (Parameter[169] & 8) == 0 )
  {
    if ( *((_QWORD *)Parameter + 20) )
    {
      v12 = GameInputCurrentTime(v8, v7);
      v13 = *((_QWORD *)Parameter + 20);
      if ( v12 >= v13 )
      {
        *((_QWORD *)Parameter + 20) = 0;
        goto LABEL_19;
      }
      v14 = v13 - v12;
      if ( v14 > 0xCCCCCCCCCCCCCCCLL )
        v15.QuadPart = 0x8000000000000000uLL;
      else
        v15.QuadPart = -10LL * v14;
      Interval = v15;
      if ( NtDelayExecution(1u, &Interval) == 258 )
        *((_QWORD *)Parameter + 20) = 0;
    }
    else
    {
LABEL_19:
      if ( (Parameter[169] & 6) != 0 )
      {
        v16 = Parameter[169] & 2;
        Interval.QuadPart = (-(__int64)(v16 != 0) & 0xFFFFFFFFFFD23940uLL) - 2000000;
        if ( (unsigned int)GipQuiesceWatcher::WaitForQuiesce(*((GipQuiesceWatcher **)Parameter + 15), 1u, &Interval) == 258 )
        {
          if ( v16 )
          {
            _InterlockedAnd8(Parameter + 169, 0xFDu);
            if ( (unsigned int)dword_180069000 > 5 )
            {
              v8 = qword_180069018;
              if ( (qword_180069010 & 8) != 0 && (qword_180069018 & 8) == qword_180069018 )
              {
                v68 = 32;
                v67 = Parameter + 172;
                v17 = GetCurrentThreadId();
                v76 = 659;
                v75 = v17;
                v56 = "Initial wait for device quiesce completed";
                v57[0].QuadPart = (LONGLONG)"onecore\\xbox\\gameinput\\feedback\\FeedbackManager.cpp";
                _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_GameInputEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperArray<1>>(
                  v18,
                  (unsigned int)word_18005E0CA,
                  v19,
                  v20,
                  (__int64)v57,
                  (__int64)&v76,
                  (__int64)&v56,
                  (__int64)&v75,
                  (__int64)&v67);
              }
            }
          }
          else
          {
            _InterlockedAnd8(Parameter + 169, 0xFBu);
            if ( (unsigned int)dword_180069000 > 5 )
            {
              v8 = qword_180069018;
              if ( (qword_180069010 & 8) != 0 && (qword_180069018 & 8) == qword_180069018 )
              {
                v70 = 32;
                v69 = Parameter + 172;
                v21 = GetCurrentThreadId();
                LODWORD(v78) = 670;
                LODWORD(v77) = v21;
                v57[0].QuadPart = (LONGLONG)"All device quiesce notifications flushed";
                v56 = "onecore\\xbox\\gameinput\\feedback\\FeedbackManager.cpp";
                _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_GameInputEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperArray<1>>(
                  v22,
                  (unsigned int)qword_18005D330,
                  v23,
                  v24,
                  (__int64)&v56,
                  (__int64)&v78,
                  (__int64)v57,
                  (__int64)&v77,
                  (__int64)&v69);
              }
            }
          }
        }
      }
      else
      {
        v25 = (GipQuiesceWatcher *)*((_QWORD *)Parameter + 15);
        if ( !v25 || (v57[0].QuadPart = 0, (unsigned int)GipQuiesceWatcher::WaitForQuiesce(v25, 0, v57)) )
        {
          if ( (Parameter[169] & 1) != 0 )
          {
            AcquireSRWLockExclusive((PSRWLOCK)Parameter);
            ReleaseSRWLockExclusive((PSRWLOCK)Parameter);
            if ( (Parameter[169] & 0xFE) == 0 )
            {
              if ( (unsigned int)dword_180069000 > 5
                && (qword_180069010 & 8) != 0
                && (qword_180069018 & 8) == qword_180069018 )
              {
                v74 = 32;
                v73 = Parameter + 172;
                v30 = GetCurrentThreadId();
                v62 = 715;
                v61 = v30;
                v57[0].QuadPart = (LONGLONG)"Resetting device feedback state";
                Interval.QuadPart = (LONGLONG)"onecore\\xbox\\gameinput\\feedback\\FeedbackManager.cpp";
                _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_GameInputEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperArray<1>>(
                  v31,
                  (unsigned int)&word_18005B7C6,
                  v32,
                  v33,
                  (__int64)&Interval,
                  (__int64)&v62,
                  (__int64)v57,
                  (__int64)&v61,
                  (__int64)&v73);
              }
              FeedbackManagerState::ResetCache((FeedbackManagerState *)Parameter);
              v34 = *((_QWORD *)Parameter + 14);
              if ( v34 )
                (*(void (__fastcall **)(__int64))(*(_QWORD *)v34 + 24LL))(v34);
              v8 = *((_QWORD *)Parameter + 17);
              if ( v8 && !*((_QWORD *)Parameter + 15) && Parameter[170] )
              {
                v35 = *(_QWORD *)v8;
                *(_OWORD *)&v57[0].LowPart = 0;
                v58 = 0;
                (*(void (__fastcall **)(__int64, union _LARGE_INTEGER *))(v35 + 168))(v8, v57);
              }
              Parameter[170] = 0;
              if ( Parameter[171] )
              {
                if ( !*((_QWORD *)Parameter + 2) )
                  goto LABEL_66;
                if ( (unsigned __int8)Parameter[40] < 4u )
                {
                  v36 = (void *)*((_QWORD *)Parameter + 1);
                  if ( v36 )
                  {
                    GipEquationManager::ReleaseReference(v36);
                    *((_QWORD *)Parameter + 1) = 0;
                  }
                  if ( (unsigned int)dword_180069000 > 5
                    && (qword_180069010 & 8) != 0
                    && (qword_180069018 & 8) == qword_180069018 )
                  {
                    v66 = 32;
                    v65 = Parameter + 172;
                    v37 = GetCurrentThreadId();
                    v64 = 761;
                    v63 = v37;
                    v57[0].QuadPart = (LONGLONG)"Starting new legacy GIP equation manager";
                    Interval.QuadPart = (LONGLONG)"onecore\\xbox\\gameinput\\feedback\\FeedbackManager.cpp";
                    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_GameInputEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperArray<1>>(
                      v38,
                      (unsigned int)word_18005D50A,
                      v39,
                      v40,
                      (__int64)&Interval,
                      (__int64)&v64,
                      (__int64)v57,
                      (__int64)&v63,
                      (__int64)&v65);
                  }
                  Heap = (char *)RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 0, 0x11A0u);
                  if ( Heap )
                  {
                    v44 = (struct Windows::Gaming::Input::Custom::IGipGameControllerProvider *)*((_QWORD *)Parameter + 16);
                    *(_QWORD *)Heap = &GipEquationManager::`vftable';
                    EquationManager::EquationManager((EquationManager *)(Heap + 8), v44);
                    Heap[4504] = 1;
                    *((_QWORD *)Parameter + 1) = Heap;
                  }
                  else
                  {
                    *((_QWORD *)Parameter + 1) = 0;
                    if ( (unsigned int)dword_180069000 > 2 )
                    {
                      v8 = qword_180069018;
                      if ( (qword_180069010 & 8) != 0 && (qword_180069018 & 8) == qword_180069018 )
                      {
                        LODWORD(v56) = -2147024882;
                        Interval.LowPart = 765;
                        v57[0].QuadPart = (LONGLONG)"onecore\\xbox\\gameinput\\feedback\\FeedbackManager.cpp";
                        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_GameInputEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
                          qword_180069018,
                          (unsigned int)&unk_18005D560,
                          v42,
                          v43,
                          (__int64)v57,
                          (__int64)&Interval,
                          (__int64)&v56);
                      }
                    }
                  }
                }
              }
              if ( *((_QWORD *)Parameter + 2) )
              {
                v45 = GameInputCurrentTime(v8, v7);
                goto LABEL_67;
              }
LABEL_66:
              v45 = 0;
LABEL_67:
              *((_QWORD *)Parameter + 3) = v45;
              _InterlockedAnd8(Parameter + 169, 0xFEu);
            }
          }
          else
          {
            updated = FeedbackManager::UpdateDevice((struct FeedbackManagerState *)Parameter);
            LOBYTE(v8) = Parameter[169];
            v47 = updated;
            if ( !(_BYTE)v8 )
            {
              Interval.QuadPart = 0;
              v48 = GameInputCurrentTime(v8, v7);
              v8 = v47 - v48;
              v7 = (v47 - v48) & -(__int64)(v48 < v47);
              if ( v7 > 0xCCCCCCCCCCCCCCCLL )
              {
                Interval.QuadPart = 0x8000000000000000uLL;
                goto LABEL_73;
              }
              Interval.QuadPart = -10LL * v7;
              if ( v7 )
LABEL_73:
                NtDelayExecution(1u, &Interval);
            }
          }
        }
        else
        {
          if ( (unsigned int)dword_180069000 > 5 )
          {
            v8 = qword_180069018;
            if ( (qword_180069010 & 8) != 0 && (qword_180069018 & 8) == qword_180069018 )
            {
              v72 = 32;
              v71 = Parameter + 172;
              v26 = GetCurrentThreadId();
              v60 = 689;
              v59 = v26;
              v57[0].QuadPart = (LONGLONG)"Unexpected quiesce notifications detected";
              Interval.QuadPart = (LONGLONG)"onecore\\xbox\\gameinput\\feedback\\FeedbackManager.cpp";
              _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_GameInputEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperArray<1>>(
                v27,
                (unsigned int)byte_18005A16B,
                v28,
                v29,
                (__int64)&Interval,
                (__int64)&v60,
                (__int64)v57,
                (__int64)&v59,
                (__int64)&v71);
            }
          }
          _InterlockedOr8(Parameter + 169, 5u);
        }
      }
    }
  }
  if ( (unsigned int)dword_180069000 > 5 && (qword_180069010 & 8) != 0 && (qword_180069018 & 8) == qword_180069018 )
  {
    v66 = 32;
    v65 = Parameter + 172;
    v49 = GetCurrentThreadId();
    v76 = 802;
    v75 = v49;
    v77 = "Exiting feedback manager worker thread";
    v78 = "onecore\\xbox\\gameinput\\feedback\\FeedbackManager.cpp";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_GameInputEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperArray<1>>(
      v50,
      (unsigned int)&byte_18005AED7,
      v51,
      v52,
      (__int64)&v78,
      (__int64)&v76,
      (__int64)&v77,
      (__int64)&v75,
      (__int64)&v65);
  }
  if ( _InterlockedExchangeAdd8(Parameter + 204, 0xFFu) == 1 && Parameter )
  {
    FeedbackManagerState::~FeedbackManagerState((FeedbackManagerState *)Parameter);
    operator delete(Parameter, v53);
  }
  return 0;
}

```

## disassembly

```asm
0x180022390  push    rbp
0x180022392  push    rbx
0x180022393  push    rsi
0x180022394  push    rdi
0x180022395  push    r12
0x180022397  push    r13
0x180022399  push    r14
0x18002239b  lea     rbp, [rsp-27h]
0x1800223a0  sub     rsp, 0F0h
0x1800223a7  mov     eax, cs:dword_180069000
0x1800223ad  lea     r12, aOnecoreXboxGam_10; "onecore\\xbox\\gameinput\\feedback\\Fee"...
0x1800223b4  mov     r14d, 8
0x1800223ba  mov     rbx, rcx
0x1800223bd  lea     r13d, [r14+18h]
0x1800223c1  cmp     eax, 5
0x1800223c4  jbe     loc_180022456
0x1800223ca  mov     rcx, cs:qword_180069018
0x1800223d1  mov     rax, cs:qword_180069010
0x1800223d8  test    r14b, al
0x1800223db  jz      short loc_180022456
0x1800223dd  mov     rax, rcx
0x1800223e0  and     rax, r14
0x1800223e3  cmp     rax, rcx
0x1800223e6  jnz     short loc_180022456
0x1800223e8  lea     rax, [rbx+0ACh]
0x1800223ef  mov     word ptr [rbp+57h+var_C0+8], r13w
0x1800223f4  mov     qword ptr [rbp+57h+var_C0], rax
0x1800223f8  call    cs:__imp_GetCurrentThreadId
0x1800223ff  nop     dword ptr [rax+rax+00h]
0x180022404  lea     rdx, byte_18005DBC7
0x18002240b  mov     [rbp+57h+arg_8], 24Ah
0x180022412  mov     [rbp+57h+arg_0], eax
0x180022415  lea     rax, aStartingFeedba; "Starting feedback manager worker thread"
0x18002241c  mov     [rbp+57h+arg_10], rax
0x180022420  lea     rax, [rbp+57h+var_C0]
0x180022424  mov     [rsp+120h+var_E0], rax
0x180022429  lea     rax, [rbp+57h+arg_0]
0x18002242d  mov     [rsp+120h+var_E8], rax
0x180022432  lea     rax, [rbp+57h+arg_10]
0x180022436  mov     [rsp+120h+var_F0], rax
0x18002243b  lea     rax, [rbp+57h+arg_8]
0x18002243f  mov     [rsp+120h+var_F8], rax
0x180022444  lea     rax, [rbp+57h+arg_18]
0x180022448  mov     [rsp+120h+var_100], rax
0x18002244d  mov     [rbp+57h+arg_18], r12
0x180022451  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U2@U?$_tlgWrapperArray@$00@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_GameInputEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@34AEBU?$_tlgWrapperArray@$00@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_GameInputEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperArray<1>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapperArray<1> const &)
0x180022456  call    cs:__imp_GetCurrentThread
0x18002245d  nop     dword ptr [rax+rax+00h]
0x180022462  mov     rcx, rax; hThread
0x180022465  mov     edx, 2; nPriority
0x18002246a  call    cs:__imp_SetThreadPriority
0x180022471  nop     dword ptr [rax+rax+00h]
0x180022476  xor     esi, esi
0x180022478  test    eax, eax
0x18002247a  jnz     short loc_1800224E6
0x18002247c  call    cs:__imp_GetLastError
0x180022483  nop     dword ptr [rax+rax+00h]
0x180022488  mov     ecx, cs:dword_180069000
0x18002248e  cmp     ecx, 2
0x180022491  jbe     short loc_1800224E6
0x180022493  mov     rdx, cs:qword_180069018
0x18002249a  mov     rcx, cs:qword_180069010
0x1800224a1  test    r14b, cl
0x1800224a4  jz      short loc_1800224E6
0x1800224a6  mov     rcx, rdx
0x1800224a9  and     rcx, r14
0x1800224ac  cmp     rcx, rdx
0x1800224af  jnz     short loc_1800224E6
0x1800224b1  mov     [rbp+57h+arg_0], eax
0x1800224b4  lea     rdx, byte_18005DF55
0x1800224bb  lea     rax, [rbp+57h+arg_0]
0x1800224bf  mov     [rbp+57h+arg_8], 24Fh
0x1800224c6  mov     [rsp+120h+var_F0], rax
0x1800224cb  lea     rax, [rbp+57h+arg_8]
0x1800224cf  mov     [rsp+120h+var_F8], rax
0x1800224d4  lea     rax, [rbp+57h+arg_10]
0x1800224d8  mov     [rsp+120h+var_100], rax
0x1800224dd  mov     [rbp+57h+arg_10], r12
0x1800224e1  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_GameInputEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_GameInputEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x1800224e6  mov     rdi, 8000000000000000h
0x1800224f0  mov     al, [rbx+0A9h]
0x1800224f6  nop
0x1800224f7  test    r14b, al
0x1800224fa  jnz     loc_180022B43
0x180022500  cmp     [rbx+0A0h], rsi
0x180022507  jz      short loc_180022562
0x180022509  call    GameInputCurrentTime
0x18002250e  mov     rcx, [rbx+0A0h]
0x180022515  cmp     rax, rcx
0x180022518  jnb     short loc_18002255B
0x18002251a  sub     rcx, rax
0x18002251d  mov     rax, 0CCCCCCCCCCCCCCCh
0x180022527  cmp     rcx, rax
0x18002252a  ja      short loc_180022532
0x18002252c  imul    rax, rcx, -0Ah
0x180022530  jmp     short loc_180022535
0x180022532  mov     rax, rdi
0x180022535  lea     rdx, [rbp+57h+Interval]; Interval
0x180022539  mov     qword ptr [rbp+57h+Interval], rax
0x18002253d  mov     cl, 1; Alertable
0x18002253f  call    cs:__imp_NtDelayExecution
0x180022546  nop     dword ptr [rax+rax+00h]
0x18002254b  cmp     eax, 102h
0x180022550  jnz     short loc_1800224F0
0x180022552  mov     [rbx+0A0h], rsi
0x180022559  jmp     short loc_1800224F0
0x18002255b  mov     [rbx+0A0h], rsi
0x180022562  mov     dil, [rbx+0A9h]
0x180022569  nop
0x18002256a  and     dil, 6
0x18002256e  jz      loc_180022718
0x180022574  and     dil, 2
0x180022578  lea     r8, [rbp+57h+Interval]; union _LARGE_INTEGER *
0x18002257c  mov     al, dil
0x18002257f  mov     dl, 1; unsigned __int8
0x180022581  neg     al
0x180022583  sbb     rcx, rcx
0x180022586  and     rcx, 0FFFFFFFFFFD23940h
0x18002258d  add     rcx, 0FFFFFFFFFFE17B80h
0x180022594  mov     qword ptr [rbp+57h+Interval], rcx
0x180022598  mov     rcx, [rbx+78h]; this
0x18002259c  call    ?WaitForQuiesce@GipQuiesceWatcher@@QEAAJEAEAT_LARGE_INTEGER@@@Z; GipQuiesceWatcher::WaitForQuiesce(uchar,_LARGE_INTEGER &)
0x1800225a1  cmp     eax, 102h
0x1800225a6  jnz     loc_1800224E6
0x1800225ac  test    dil, dil
0x1800225af  nop
0x1800225b0  mov     rdi, 8000000000000000h
0x1800225ba  jz      loc_180022667
0x1800225c0  lock and byte ptr [rbx+0A9h], 0FDh
0x1800225c8  nop
0x1800225c9  mov     eax, cs:dword_180069000
0x1800225cf  cmp     eax, 5
0x1800225d2  jbe     loc_1800224F0
0x1800225d8  mov     rcx, cs:qword_180069018
0x1800225df  mov     rax, cs:qword_180069010
0x1800225e6  test    r14b, al
0x1800225e9  jz      loc_1800224F0
0x1800225ef  mov     rax, rcx
0x1800225f2  and     rax, r14
0x1800225f5  cmp     rax, rcx
0x1800225f8  jnz     loc_1800224F0
0x1800225fe  lea     rax, [rbx+0ACh]
0x180022605  mov     [rbp+57h+var_70], r13w
0x18002260a  mov     [rbp+57h+var_78], rax
0x18002260e  call    cs:__imp_GetCurrentThreadId
0x180022615  nop     dword ptr [rax+rax+00h]
0x18002261a  mov     [rbp+57h+arg_8], 293h
0x180022621  lea     rdx, word_18005E0CA
0x180022628  mov     [rbp+57h+arg_0], eax
0x18002262b  lea     rax, aInitialWaitFor; "Initial wait for device quiesce complet"...
0x180022632  mov     [rbp+57h+var_C8], rax
0x180022636  lea     rax, [rbp+57h+var_78]
0x18002263a  mov     [rsp+120h+var_E0], rax
0x18002263f  lea     rax, [rbp+57h+arg_0]
0x180022643  mov     [rsp+120h+var_E8], rax
0x180022648  lea     rax, [rbp+57h+var_C8]
0x18002264c  mov     [rsp+120h+var_F0], rax
0x180022651  lea     rax, [rbp+57h+arg_8]
0x180022655  mov     [rsp+120h+var_F8], rax
0x18002265a  lea     rax, [rbp+57h+var_C0]
0x18002265e  mov     qword ptr [rbp+57h+var_C0], r12
0x180022662  jmp     loc_180022709
0x180022667  lock and byte ptr [rbx+0A9h], 0FBh
0x18002266f  nop
0x180022670  mov     eax, cs:dword_180069000
0x180022676  cmp     eax, 5
0x180022679  jbe     loc_1800224F0
0x18002267f  mov     rcx, cs:qword_180069018
0x180022686  mov     rax, cs:qword_180069010
0x18002268d  test    r14b, al
0x180022690  jz      loc_1800224F0
0x180022696  mov     rax, rcx
0x180022699  and     rax, r14
0x18002269c  cmp     rax, rcx
0x18002269f  jnz     loc_1800224F0
0x1800226a5  lea     rax, [rbx+0ACh]
0x1800226ac  mov     [rbp+57h+var_60], r13w
0x1800226b1  mov     [rbp+57h+var_68], rax
0x1800226b5  call    cs:__imp_GetCurrentThreadId
0x1800226bc  nop     dword ptr [rax+rax+00h]
0x1800226c1  mov     dword ptr [rbp+57h+arg_18], 29Eh
0x1800226c8  lea     rdx, qword_18005D330
0x1800226cf  mov     dword ptr [rbp+57h+arg_10], eax
0x1800226d2  lea     rax, aAllDeviceQuies; "All device quiesce notifications flushe"...
0x1800226d9  mov     qword ptr [rbp+57h+var_C0], rax
0x1800226dd  lea     rax, [rbp+57h+var_68]
0x1800226e1  mov     [rsp+120h+var_E0], rax
0x1800226e6  lea     rax, [rbp+57h+arg_10]
0x1800226ea  mov     [rsp+120h+var_E8], rax
0x1800226ef  lea     rax, [rbp+57h+var_C0]
0x1800226f3  mov     [rsp+120h+var_F0], rax
0x1800226f8  lea     rax, [rbp+57h+arg_18]
0x1800226fc  mov     [rsp+120h+var_F8], rax
0x180022701  lea     rax, [rbp+57h+var_C8]
0x180022705  mov     [rbp+57h+var_C8], r12
0x180022709  mov     [rsp+120h+var_100], rax
0x18002270e  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U2@U?$_tlgWrapperArray@$00@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_GameInputEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@34AEBU?$_tlgWrapperArray@$00@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_GameInputEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperArray<1>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapperArray<1> const &)
0x180022713  jmp     loc_1800224F0
0x180022718  mov     rcx, [rbx+78h]; this
0x18002271c  test    rcx, rcx
0x18002271f  jz      loc_1800227E5
0x180022725  lea     r8, [rbp+57h+var_C0]; union _LARGE_INTEGER *
0x180022729  mov     qword ptr [rbp+57h+var_C0], rsi
0x18002272d  xor     edx, edx; unsigned __int8
0x18002272f  call    ?WaitForQuiesce@GipQuiesceWatcher@@QEAAJEAEAT_LARGE_INTEGER@@@Z; GipQuiesceWatcher::WaitForQuiesce(uchar,_LARGE_INTEGER &)
0x180022734  test    eax, eax
0x180022736  jnz     loc_1800227E5
0x18002273c  mov     eax, cs:dword_180069000
0x180022742  cmp     eax, 5
0x180022745  jbe     loc_1800227D7
0x18002274b  mov     rcx, cs:qword_180069018
0x180022752  mov     rax, cs:qword_180069010
0x180022759  test    r14b, al
0x18002275c  jz      short loc_1800227D7
0x18002275e  mov     rax, rcx
0x180022761  and     rax, r14
0x180022764  cmp     rax, rcx
0x180022767  jnz     short loc_1800227D7
0x180022769  lea     rax, [rbx+0ACh]
0x180022770  mov     [rbp+57h+var_50], r13w
0x180022775  mov     [rbp+57h+var_58], rax
0x180022779  call    cs:__imp_GetCurrentThreadId
0x180022780  nop     dword ptr [rax+rax+00h]
0x180022785  lea     rdx, byte_18005A16B
0x18002278c  mov     [rbp+57h+var_9C], 2B1h
0x180022793  mov     [rbp+57h+var_A0], eax
0x180022796  lea     rax, aUnexpectedQuie; "Unexpected quiesce notifications detect"...
0x18002279d  mov     qword ptr [rbp+57h+var_C0], rax
0x1800227a1  lea     rax, [rbp+57h+var_58]
0x1800227a5  mov     [rsp+120h+var_E0], rax
0x1800227aa  lea     rax, [rbp+57h+var_A0]
0x1800227ae  mov     [rsp+120h+var_E8], rax
0x1800227b3  lea     rax, [rbp+57h+var_C0]
0x1800227b7  mov     [rsp+120h+var_F0], rax
0x1800227bc  lea     rax, [rbp+57h+var_9C]
0x1800227c0  mov     [rsp+120h+var_F8], rax
0x1800227c5  lea     rax, [rbp+57h+Interval]
0x1800227c9  mov     [rsp+120h+var_100], rax
0x1800227ce  mov     qword ptr [rbp+57h+Interval], r12
0x1800227d2  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U2@U?$_tlgWrapperArray@$00@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_GameInputEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@34AEBU?$_tlgWrapperArray@$00@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_GameInputEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperArray<1>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapperArray<1> const &)
0x1800227d7  nop
0x1800227d8  lock or byte ptr [rbx+0A9h], 5
0x1800227e0  jmp     loc_180022AC7
0x1800227e5  mov     al, [rbx+0A9h]
0x1800227eb  mov     rcx, rbx; this
0x1800227ee  nop
0x1800227ef  test    al, 1
0x1800227f1  jz      loc_180022ACD
0x1800227f7  call    cs:__imp_AcquireSRWLockExclusive
0x1800227fe  nop     dword ptr [rax+rax+00h]
0x180022803  mov     rcx, rbx; SRWLock
0x180022806  call    cs:__imp_ReleaseSRWLockExclusive
0x18002280d  nop     dword ptr [rax+rax+00h]
0x180022812  mov     al, [rbx+0A9h]
0x180022818  mov     rdi, 8000000000000000h
0x180022822  nop
0x180022823  test    al, 0FEh
0x180022825  jnz     loc_1800224F0
0x18002282b  mov     eax, cs:dword_180069000
0x180022831  cmp     eax, 5
0x180022834  jbe     loc_1800228C6
0x18002283a  mov     rcx, cs:qword_180069018
0x180022841  mov     rax, cs:qword_180069010
0x180022848  test    r14b, al
0x18002284b  jz      short loc_1800228C6
0x18002284d  mov     rax, rcx
0x180022850  and     rax, r14
0x180022853  cmp     rax, rcx
0x180022856  jnz     short loc_1800228C6
0x180022858  lea     rax, [rbx+0ACh]
0x18002285f  mov     [rbp+57h+var_40], r13w
0x180022864  mov     [rbp+57h+var_48], rax
0x180022868  call    cs:__imp_GetCurrentThreadId
0x18002286f  nop     dword ptr [rax+rax+00h]
0x180022874  lea     rdx, word_18005B7C6
0x18002287b  mov     [rbp+57h+var_94], 2CBh
0x180022882  mov     [rbp+57h+var_98], eax
0x180022885  lea     rax, aResettingDevic; "Resetting device feedback state"
0x18002288c  mov     qword ptr [rbp+57h+var_C0], rax
0x180022890  lea     rax, [rbp+57h+var_48]
0x180022894  mov     [rsp+120h+var_E0], rax
0x180022899  lea     rax, [rbp+57h+var_98]
0x18002289d  mov     [rsp+120h+var_E8], rax
0x1800228a2  lea     rax, [rbp+57h+var_C0]
0x1800228a6  mov     [rsp+120h+var_F0], rax
0x1800228ab  lea     rax, [rbp+57h+var_94]
0x1800228af  mov     [rsp+120h+var_F8], rax
0x1800228b4  lea     rax, [rbp+57h+Interval]
0x1800228b8  mov     [rsp+120h+var_100], rax
0x1800228bd  mov     qword ptr [rbp+57h+Interval], r12
0x1800228c1  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U2@U?$_tlgWrapperArray@$00@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_GameInputEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@34AEBU?$_tlgWrapperArray@$00@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_GameInputEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperArray<1>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapperArray<1> const &)
0x1800228c6  mov     rcx, rbx; this
0x1800228c9  call    ?ResetCache@FeedbackManagerState@@QEAAXXZ; FeedbackManagerState::ResetCache(void)
0x1800228ce  mov     rcx, [rbx+70h]
0x1800228d2  test    rcx, rcx
0x1800228d5  jz      short loc_1800228E3
0x1800228d7  mov     rax, [rcx]
0x1800228da  mov     rax, [rax+18h]
0x1800228de  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800228e3  mov     rcx, [rbx+88h]
  ... truncated ...
```
