# CDplUser::RetrieveCredentialsFromAad(ushort *,int *)

- ea: `0x1800baeb0`
- end: `0x1800bb982`
- name: `?RetrieveCredentialsFromAad@CDplUser@@AEAAJPEAGPEAH@Z`
- size: `2770`
- prototype: `__int64 __fastcall(CDplUser *__hidden this, RPC_WSTR StringUuid, int *)`
- caller_count: `4`
- callee_count: `24`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x18008afdc`
- `0x18008d804`
- `0x180095594`
- `0x1800bd9c0`

## callees

- `0x180001a7c`
- `0x180001d84`
- `0x180002474`
- `0x18000254c`
- `0x180063698`
- `0x180063730`
- `0x1800637e8`
- `0x18006fb14`
- `0x1800857a8`
- `0x1800885ac`
- `0x18009487c`
- `0x1800964ac`
- `0x18009652c`
- `0x1800ab00c`
- `0x1800b4668`
- `0x1800b494c`
- `0x1800b9364`
- `0x1800baeb0`
- `0x1800bd9d8`
- `0x1800cf880`
- `0x1800cfe1c`
- `0x1800d0534`
- `0x1800d5af8`
- `0x1800dddf0`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800bb7d3`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800bb804`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800bb829`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800bb7d3`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800bb804`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800bb829`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800bb7e1`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800bb812`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800bb838`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800bb7e1`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800bb812`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800bb838`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800bb0e0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800bb0e0`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800bb847`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800bb847`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x1800bb8a2`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x1800bb8a2`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x1800bb1b8`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x1800bb1b8`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x1800bb771`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x1800bb771`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x1800bb0d6`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x1800bb0d6`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x1800bb432`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x1800bb432`
- `WINHTTP!WinHttpCloseHandle` at `0x1800bb4ab`
- `WINHTTP!WinHttpCloseHandle` at `0x1800bb4be`
- `WINHTTP!WinHttpCloseHandle` at `0x1800bb4d0`
- `WINHTTP!WinHttpCloseHandle` at `0x1800bb74e`
- `WINHTTP!WinHttpCloseHandle` at `0x1800bb75d`
- `WINHTTP!WinHttpCloseHandle` at `0x1800bb76b`
- `WINHTTP!WinHttpCloseHandle` at `0x1800bb4ab`
- `WINHTTP!WinHttpCloseHandle` at `0x1800bb4be`
- `WINHTTP!WinHttpCloseHandle` at `0x1800bb4d0`
- `WINHTTP!WinHttpCloseHandle` at `0x1800bb74e`
- `WINHTTP!WinHttpCloseHandle` at `0x1800bb75d`
- `WINHTTP!WinHttpCloseHandle` at `0x1800bb76b`
- `RPCRT4!UuidFromStringW` at `0x1800bb1d7`
- `RPCRT4!UuidFromStringW` at `0x1800bb1d7`

## string_xrefs

- `0x1800bb901`: `RequestComplete`

## pseudocode

```c
__int64 __fastcall CDplUser::RetrieveCredentialsFromAad(CDplUser *this, RPC_WSTR StringUuid, int *a3)
{
  unsigned int v5; // ebx
  void *v7; // r14
  unsigned __int8 *v8; // r15
  bool IsZero; // al
  GUID *p_ActivityId; // r9
  int v11; // ecx
  unsigned int IsAutoRecoverySupported; // edi
  int v13; // ecx
  int v14; // ecx
  signed int LastError; // eax
  int v16; // eax
  int v17; // ecx
  int v18; // ecx
  RPC_STATUS v19; // ebx
  int v20; // ecx
  int v21; // ecx
  int v22; // ecx
  unsigned int v23; // ebx
  int v24; // eax
  DWORD dwHighDateTime; // ecx
  __int64 v26; // r9
  char *v27; // rax
  int v28; // eax
  unsigned int v29; // esi
  __int64 v30; // r9
  int v31; // ecx
  void *v32; // rsi
  HANDLE ProcessHeap; // rax
  unsigned int i; // esi
  _QWORD *v35; // r15
  void *v36; // r12
  HANDLE v37; // rax
  HANDLE v38; // rax
  __int64 v39; // r9
  unsigned int v41; // [rsp+50h] [rbp-89h] BYREF
  int v42; // [rsp+54h] [rbp-85h] BYREF
  int v43; // [rsp+58h] [rbp-81h] BYREF
  unsigned int v44; // [rsp+5Ch] [rbp-7Dh] BYREF
  HINTERNET v45; // [rsp+60h] [rbp-79h] BYREF
  unsigned int v46; // [rsp+68h] [rbp-71h] BYREF
  HINTERNET hInternet; // [rsp+70h] [rbp-69h] BYREF
  HINTERNET v48; // [rsp+78h] [rbp-61h] BYREF
  LPVOID v49; // [rsp+80h] [rbp-59h] BYREF
  unsigned __int8 *v50; // [rsp+88h] [rbp-51h] BYREF
  HANDLE hToken; // [rsp+90h] [rbp-49h] BYREF
  struct _FILETIME SystemTimeAsFileTime; // [rsp+98h] [rbp-41h] BYREF
  LPVOID lpMem; // [rsp+A0h] [rbp-39h] BYREF
  const char *v54; // [rsp+A8h] [rbp-31h] BYREF
  void *v55; // [rsp+B0h] [rbp-29h] BYREF
  int v56; // [rsp+B8h] [rbp-21h] BYREF
  char v57; // [rsp+BCh] [rbp-1Dh]
  _BYTE v58[16]; // [rsp+C0h] [rbp-19h] BYREF
  GUID ActivityId; // [rsp+D0h] [rbp-9h] BYREF
  UUID Uuid; // [rsp+E0h] [rbp+7h] BYREF

  v55 = 0;
  hToken = 0;
  v43 = 0;
  v5 = 0;
  hInternet = 0;
  v48 = 0;
  v45 = 0;
  v41 = 0;
  v49 = 0;
  Uuid = 0;
  v7 = 0;
  lpMem = 0;
  v8 = 0;
  v50 = 0;
  v44 = 0;
  v46 = 0;
  v42 = 0;
  SystemTimeAsFileTime = 0;
  v56 = 0;
  v57 = 0;
  fnEfsLogTrace1Strings((_DWORD)this, (unsigned int)EFS_TRACE_ENTER_EVENT, (unsigned int)&sourceString, 40, 46);
  _TlgActivityBase<TraceLoggingThreadActivity<&_tlgProvider_t const * const g_hEfsCoreTraceLoggingProvider,70368744177664,5,_TlgReflectorTag_Param0IsHProvider>,70368744177664,5>::zInternalStart(&v56);
  if ( (unsigned int)dword_180114250 > 5 && (unsigned __int8)tlgKeywordOn(&dword_180114250, 0x400000000000LL) )
  {
    if ( !v57 || (IsZero = _tlgGuidIsZero(&ActivityId), p_ActivityId = &ActivityId, IsZero) )
      p_ActivityId = 0;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(
      (__int64)&dword_180114250,
      (__int64)byte_1801035ED,
      (__int64)v58,
      (__int64)p_ActivityId);
  }
  if ( a3 )
    *a3 = 0;
  if ( (unsigned int)CDplServiceImpl::IsCurrentLockOwner(*((CDplServiceImpl **)this + 6)) )
  {
    IsAutoRecoverySupported = -2147418113;
    fnEfsLogTrace1(g_hPublisher, (unsigned int)EFS_TRACE_ERROR, -2147418113, 40, 60);
  }
  else if ( (unsigned int)CDplUser::IsCurrentLockOwner(this) )
  {
    IsAutoRecoverySupported = -2147418113;
    fnEfsLogTrace1(g_hPublisher, (unsigned int)EFS_TRACE_ERROR, -2147418113, 40, 61);
  }
  else
  {
    fnEfsLogTrace1Strings(v11, (unsigned int)EFS_TRACE_START_EVENT, (unsigned int)&sourceString, 40, 67);
    IsAutoRecoverySupported = CDplServiceImpl::RevertToSelf(*((CDplServiceImpl **)this + 6), &v55);
    if ( (int)fnEfsLogTrace1String1Dword(
                g_hPublisher,
                (unsigned int)EFS_TRACE_COMPLETE_EVENT,
                (unsigned int)EFS_TRACE_COMPLETE_EVENT_ERROR,
                (unsigned int)&sourceString,
                IsAutoRecoverySupported,
                40,
                67) >= 0 )
    {
      fnEfsLogTrace1Strings(v13, (unsigned int)EFS_TRACE_START_EVENT, (unsigned int)&sourceString, 40, 73);
      IsAutoRecoverySupported = EdpCredSvcQuerySessionUserTokenBySid(*((const unsigned __int16 **)this + 13), &hToken);
      if ( (int)fnEfsLogTrace1String1Dword(
                  g_hPublisher,
                  (unsigned int)EFS_TRACE_COMPLETE_EVENT,
                  (unsigned int)EFS_TRACE_COMPLETE_EVENT_ERROR,
                  (unsigned int)&sourceString,
                  IsAutoRecoverySupported,
                  40,
                  73) >= 0 )
      {
        if ( hToken )
        {
          if ( ImpersonateLoggedOnUser(hToken) )
          {
            fnEfsLogTrace1Strings(v14, (unsigned int)EFS_TRACE_START_EVENT, (unsigned int)&sourceString, 40, 94);
            IsAutoRecoverySupported = CDplUser::IsAutoRecoverySupported(this, 0, &v43);
            v16 = fnEfsLogTrace1String1Dword(
                    g_hPublisher,
                    (unsigned int)EFS_TRACE_COMPLETE_EVENT,
                    (unsigned int)EFS_TRACE_COMPLETE_EVENT_ERROR,
                    (unsigned int)&sourceString,
                    IsAutoRecoverySupported,
                    40,
                    94);
            v17 = 0;
            if ( v16 >= 0 )
            {
              if ( v43 )
              {
                while ( 1 )
                {
                  v42 = v17 + 1;
                  Sleep(250 * v17);
                  if ( StringUuid && *StringUuid )
                  {
                    v19 = UuidFromStringW(StringUuid, &Uuid);
                    fnEfsLogTrace1Strings(
                      v20,
                      (unsigned int)EFS_TRACE_START_EVENT,
                      (unsigned int)&sourceString,
                      40,
                      142);
                    IsAutoRecoverySupported = 0;
                    if ( v19 )
                      IsAutoRecoverySupported = v19 | 0x80010000;
                    if ( (int)fnEfsLogTrace1String1Dword(
                                g_hPublisher,
                                (unsigned int)EFS_TRACE_COMPLETE_EVENT,
                                (unsigned int)EFS_TRACE_COMPLETE_EVENT_ERROR,
                                (unsigned int)&sourceString,
                                IsAutoRecoverySupported,
                                40,
                                142) < 0 )
                      goto LABEL_62;
                    fnEfsLogTrace1Strings(
                      v21,
                      (unsigned int)EFS_TRACE_START_EVENT,
                      (unsigned int)&sourceString,
                      40,
                      151);
                    IsAutoRecoverySupported = WIPCreateRequestForAAD(
                                                1u,
                                                (__int64)&Uuid,
                                                0,
                                                0,
                                                0,
                                                &hInternet,
                                                &v48,
                                                &v45);
                    if ( (int)fnEfsLogTrace1String1Dword(
                                g_hPublisher,
                                (unsigned int)EFS_TRACE_COMPLETE_EVENT,
                                (unsigned int)EFS_TRACE_COMPLETE_EVENT_ERROR,
                                (unsigned int)&sourceString,
                                IsAutoRecoverySupported,
                                40,
                                151) < 0 )
                      goto LABEL_61;
                    v23 = 1;
                  }
                  else
                  {
                    v23 = 2;
                    fnEfsLogTrace1Strings(
                      v18,
                      (unsigned int)EFS_TRACE_START_EVENT,
                      (unsigned int)&sourceString,
                      40,
                      131);
                    IsAutoRecoverySupported = WIPCreateRequestForAAD(2u, 0, 0, 0, 0, &hInternet, &v48, &v45);
                    if ( (int)fnEfsLogTrace1String1Dword(
                                g_hPublisher,
                                (unsigned int)EFS_TRACE_COMPLETE_EVENT,
                                (unsigned int)EFS_TRACE_COMPLETE_EVENT_ERROR,
                                (unsigned int)&sourceString,
                                IsAutoRecoverySupported,
                                40,
                                131) < 0 )
                      goto LABEL_61;
                  }
                  if ( IsAutoRecoverySupported == 1 )
                  {
LABEL_61:
                    v7 = v45;
                    goto LABEL_62;
                  }
                  fnEfsLogTrace1Strings(v22, (unsigned int)EFS_TRACE_START_EVENT, (unsigned int)&sourceString, 40, 170);
                  v7 = v45;
                  IsAutoRecoverySupported = WIPSendHttpRequest(v23, v45, 0);
                  if ( (int)fnEfsLogTrace1String1Dword(
                              g_hPublisher,
                              (unsigned int)EFS_TRACE_COMPLETE_EVENT,
                              (unsigned int)EFS_TRACE_COMPLETE_EVENT_ERROR,
                              (unsigned int)&sourceString,
                              IsAutoRecoverySupported,
                              40,
                              170) < 0 )
                    goto LABEL_62;
                  v24 = WIPGetAndParseResponse(v23, v7, (unsigned __int16 ***)&v49, &lpMem, &v41);
                  IsAutoRecoverySupported = v24;
                  if ( v24 == -2147024637 )
                  {
                    IsAutoRecoverySupported = 1;
                    fnEfsLogTrace1(g_hPublisher, (unsigned int)EFS_TRACE_STATUS, 1, 40, 184);
LABEL_62:
                    v5 = v41;
                    goto LABEL_63;
                  }
                  if ( v24 >= 0 )
                    break;
                  GetSystemTimeAsFileTime(&SystemTimeAsFileTime);
                  dwHighDateTime = SystemTimeAsFileTime.dwHighDateTime;
                  *((_DWORD *)this + 4) = SystemTimeAsFileTime.dwLowDateTime;
                  *((_DWORD *)this + 5) = dwHighDateTime;
                  fnEfsLogTrace1Strings(
                    dwHighDateTime,
                    (unsigned int)EFS_TRACE_START_EVENT,
                    (unsigned int)&sourceString,
                    40,
                    212);
                  if ( (int)fnEfsLogTrace1String1Dword(
                              g_hPublisher,
                              (unsigned int)EFS_TRACE_COMPLETE_EVENT,
                              (unsigned int)EFS_TRACE_COMPLETE_EVENT_ERROR,
                              (unsigned int)&sourceString,
                              IsAutoRecoverySupported,
                              40,
                              212) < 0 )
                    goto LABEL_62;
                  if ( hInternet )
                  {
                    WinHttpCloseHandle(hInternet);
                    hInternet = 0;
                  }
                  if ( v48 )
                  {
                    WinHttpCloseHandle(v48);
                    v48 = 0;
                  }
                  if ( v7 )
                  {
                    WinHttpCloseHandle(v7);
                    v7 = 0;
                    v45 = 0;
                  }
                  v17 = v42;
                  if ( v42 >= 3 )
                    goto LABEL_44;
                }
                *((_QWORD *)this + 2) = 0;
LABEL_44:
                if ( (unsigned int)dword_180114250 > 5
                  && (unsigned __int8)tlgKeywordOn(&dword_180114250, 0x400000000000LL) )
                {
                  if ( !StringUuid || (v27 = "SpecificKeyRequest", !*StringUuid) )
                    v27 = "NormalKeyRequest";
                  v45 = v27;
                  v54 = "RequestSentParsed";
                  _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>>(
                    (__int64)&dword_180114250,
                    (__int64)&dword_1801035A4,
                    (__int64)v58,
                    v26,
                    (const unsigned __int16 **)&v54,
                    (const unsigned __int16 **)&v45);
                }
                fnEfsLogTrace1Strings(v17, (unsigned int)EFS_TRACE_START_EVENT, (unsigned int)&sourceString, 40, 242);
                v28 = fnEfsLogTrace1String1Dword(
                        g_hPublisher,
                        (unsigned int)EFS_TRACE_COMPLETE_EVENT,
                        (unsigned int)EFS_TRACE_COMPLETE_EVENT_ERROR,
                        (unsigned int)&sourceString,
                        IsAutoRecoverySupported,
                        40,
                        242);
                v5 = v41;
                if ( v28 >= 0 )
                {
                  v29 = 0;
                  if ( v41 )
                  {
                    do
                    {
                      v46 = 4;
                      fnEfsLogTrace1Strings(0, (unsigned int)EFS_TRACE_START_EVENT, (unsigned int)&sourceString, 40, 0);
                      IsAutoRecoverySupported = CDplServiceImpl::Base64Decode(
                                                  (CDplServiceImpl *)&v50,
                                                  *((const WCHAR **)v49 + v29),
                                                  *((_DWORD *)lpMem + v29),
                                                  v30,
                                                  &v50,
                                                  &v44);
                      if ( (int)fnEfsLogTrace1String1Dword(
                                  g_hPublisher,
                                  (unsigned int)EFS_TRACE_COMPLETE_EVENT,
                                  (unsigned int)EFS_TRACE_COMPLETE_EVENT_ERROR,
                                  (unsigned int)&sourceString,
                                  IsAutoRecoverySupported,
                                  40,
                                  0) < 0 )
                      {
                        v8 = v50;
                        goto LABEL_63;
                      }
                      fnEfsLogTrace1Strings(
                        v31,
                        (unsigned int)EFS_TRACE_START_EVENT,
                        (unsigned int)&sourceString,
                        40,
                        5);
                      v8 = v50;
                      IsAutoRecoverySupported = CDplUser::RecoveryIngestionHelper(this, v50, v44, 1, &v46);
                      if ( (int)fnEfsLogTrace1String1Dword(
                                  g_hPublisher,
                                  (unsigned int)EFS_TRACE_COMPLETE_EVENT,
                                  (unsigned int)EFS_TRACE_COMPLETE_EVENT_ERROR,
                                  (unsigned int)&sourceString,
                                  IsAutoRecoverySupported,
                                  40,
                                  5) < 0 )
                        goto LABEL_63;
                      if ( v8 )
                        DplibMemFree(v8);
                      ++v29;
                      v50 = 0;
                      v8 = 0;
                    }
                    while ( v29 < v5 );
                    if ( a3 )
                      *a3 = 1;
                  }
                }
LABEL_63:
                if ( hInternet )
                  WinHttpCloseHandle(hInternet);
                if ( v48 )
                  WinHttpCloseHandle(v48);
                if ( v7 )
                  WinHttpCloseHandle(v7);
              }
              else
              {
                IsAutoRecoverySupported = 1;
                fnEfsLogTrace1(g_hPublisher, (unsigned int)EFS_TRACE_STATUS, 1, 40, 102);
              }
            }
            RevertToSelf();
          }
          else
          {
            LastError = GetLastError();
            IsAutoRecoverySupported = LastError;
            if ( LastError > 0 )
              IsAutoRecoverySupported = (unsigned __int16)LastError | 0x80070000;
            fnEfsLogTrace1(g_hPublisher, (unsigned int)EFS_TRACE_ERROR, IsAutoRecoverySupported, 40, 85);
          }
        }
        else
        {
          IsAutoRecoverySupported = -2147023888;
          fnEfsLogTrace1(g_hPublisher, (unsigned int)EFS_TRACE_ERROR, -2147023888, 40, 79);
        }
      }
    }
  }
  if ( v8 )
    DplibMemFree(v8);
  v32 = lpMem;
  if ( lpMem )
  {
    ProcessHeap = GetProcessHeap();
    HeapFree(ProcessHeap, 0, v32);
  }
  if ( v49 )
  {
    for ( i = 0; i < v5; ++i )
    {
      v35 = v49;
      v36 = (void *)*((_QWORD *)v49 + i);
      if ( v36 )
      {
        v37 = GetProcessHeap();
        HeapFree(v37, 0, v36);
        v35[i] = 0;
      }
    }
    v38 = GetProcessHeap();
    HeapFree(v38, 0, v49);
  }
  if ( hToken )
  {
    CloseHandle(hToken);
    hToken = 0;
  }
  CDplServiceImpl::RestoreImpersonation(*((CDplServiceImpl **)this + 6), &v55);
  fnEfsLogTrace1String1Dword(
    g_hPublisher,
    (unsigned int)EFS_TRACE_LEAVE_HR_EVENT,
    (unsigned int)EFS_TRACE_LEAVE_HR_EVENT_ERROR,
    (unsigned int)&sourceString,
    IsAutoRecoverySupported,
    40,
    59);
  if ( v57 )
    EventActivityIdControl(4u, &ActivityId);
  v56 = 2;
  if ( (unsigned int)dword_180114250 > 5 && (unsigned __int8)tlgKeywordOn(&dword_180114250, 0x400000000000LL) )
  {
    v41 = v46;
    v54 = "RequestComplete";
    v44 = IsAutoRecoverySupported;
    LODWORD(v45) = v5;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
      (__int64)&dword_180114250,
      (__int64)byte_1801037EB,
      (__int64)v58,
      v39,
      (const unsigned __int16 **)&v54,
      (__int64)&v42,
      (__int64)&v43,
      (__int64)&v45,
      (__int64)&v41,
      (__int64)&v44);
  }
  _TlgActivityBase<TraceLoggingThreadActivity<&_tlgProvider_t const * const g_hEfsCoreTraceLoggingProvider,70368744177664,5,_TlgReflectorTag_Param0IsHProvider>,70368744177664,5>::~_TlgActivityBase<TraceLoggingThreadActivity<&_tlgProvider_t const * const g_hEfsCoreTraceLoggingProvider,70368744177664,5,_TlgReflectorTag_Param0IsHProvider>,70368744177664,5>((__int64)&v56);
  return IsAutoRecoverySupported;
}

```

## disassembly

```asm
0x1800baeb0  mov     [rsp-8+arg_18], rbx
0x1800baeb5  push    rbp
0x1800baeb6  push    rsi
0x1800baeb7  push    rdi
0x1800baeb8  push    r12
0x1800baeba  push    r13
0x1800baebc  push    r14
0x1800baebe  push    r15
0x1800baec0  lea     rbp, [rsp-27h]
0x1800baec5  sub     rsp, 100h
0x1800baecc  mov     rax, cs:__security_cookie
0x1800baed3  xor     rax, rsp
0x1800baed6  mov     [rbp+57h+var_40], rax
0x1800baeda  xor     edi, edi
0x1800baedc  mov     dword ptr [rsp+130h+var_110], 2E2Eh
0x1800baee4  mov     r12, r8
0x1800baee7  mov     [rbp+57h+var_80], rdi
0x1800baeeb  mov     rsi, rdx
0x1800baeee  mov     [rbp+57h+hToken], rdi
0x1800baef2  xorps   xmm0, xmm0
0x1800baef5  mov     [rsp+130h+var_D8], edi
0x1800baef9  mov     ebx, edi
0x1800baefb  mov     [rbp+57h+hInternet], rdi
0x1800baeff  lea     r9d, [rdi+28h]
0x1800baf03  mov     [rbp+57h+var_B8], rdi
0x1800baf07  lea     r8, sourceString
0x1800baf0e  mov     [rbp+57h+var_D0], rdi
0x1800baf12  lea     rdx, EFS_TRACE_ENTER_EVENT
0x1800baf19  mov     [rsp+130h+var_E0], ebx
0x1800baf1d  mov     r13, rcx
0x1800baf20  mov     [rbp+57h+var_B0], rdi
0x1800baf24  movups  xmmword ptr [rbp+57h+Uuid.Data1], xmm0
0x1800baf28  mov     r14d, edi
0x1800baf2b  mov     [rbp+57h+lpMem], rdi
0x1800baf2f  mov     r15d, edi
0x1800baf32  mov     [rbp+57h+var_A8], rdi
0x1800baf36  mov     [rbp+57h+var_D4], edi
0x1800baf39  mov     [rbp+57h+var_C8], edi
0x1800baf3c  mov     [rsp+130h+var_DC], edi
0x1800baf40  mov     qword ptr [rbp+57h+SystemTimeAsFileTime.dwLowDateTime], rdi
0x1800baf44  mov     [rbp+57h+var_78], edi
0x1800baf47  mov     [rbp+57h+var_74], dil
0x1800baf4b  call    fnEfsLogTrace1Strings
0x1800baf50  lea     rcx, [rbp+57h+var_78]
0x1800baf54  call    ?zInternalStart@?$_TlgActivityBase@V?$TraceLoggingThreadActivity@$1?g_hEfsCoreTraceLoggingProvider@@3QEBU_tlgProvider_t@@EB$0EAAAAAAAAAAA@$04U_TlgReflectorTag_Param0IsHProvider@@@@$0EAAAAAAAAAAA@$04@@QEAAXXZ; _TlgActivityBase<TraceLoggingThreadActivity<&_tlgProvider_t const * const g_hEfsCoreTraceLoggingProvider,70368744177664,5,_TlgReflectorTag_Param0IsHProvider>,70368744177664,5>::zInternalStart(void)
0x1800baf59  mov     eax, cs:dword_180114250
0x1800baf5f  cmp     eax, 5
0x1800baf62  jbe     short loc_1800BAFAF
0x1800baf64  mov     rdx, 400000000000h
0x1800baf6e  lea     rcx, dword_180114250
0x1800baf75  call    _tlgKeywordOn
0x1800baf7a  test    al, al
0x1800baf7c  jz      short loc_1800BAFAF
0x1800baf7e  cmp     [rbp+57h+var_74], dil
0x1800baf82  jz      short loc_1800BAF95
0x1800baf84  lea     rcx, [rbp+57h+ActivityId]; struct _GUID *
0x1800baf88  call    ?_tlgGuidIsZero@@YA_NAEBU_GUID@@@Z; _tlgGuidIsZero(_GUID const &)
0x1800baf8d  lea     r9, [rbp+57h+ActivityId]
0x1800baf91  test    al, al
0x1800baf93  jz      short loc_1800BAF98
0x1800baf95  mov     r9, rdi
0x1800baf98  lea     r8, [rbp+57h+var_70]
0x1800baf9c  lea     rdx, byte_1801035ED
0x1800bafa3  lea     rcx, dword_180114250
0x1800bafaa  call    ??$Write@$$V@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *)
0x1800bafaf  test    r12, r12
0x1800bafb2  jz      short loc_1800BAFBA
0x1800bafb4  xor     eax, eax
0x1800bafb6  mov     [r12], eax
0x1800bafba  mov     rcx, [r13+30h]; this
0x1800bafbe  call    ?IsCurrentLockOwner@CDplServiceImpl@@AEAAHXZ; CDplServiceImpl::IsCurrentLockOwner(void)
0x1800bafc3  test    eax, eax
0x1800bafc5  jnz     loc_1800BB78E
0x1800bafcb  mov     rcx, r13; this
0x1800bafce  call    ?IsCurrentLockOwner@CDplUser@@AEAAHXZ; CDplUser::IsCurrentLockOwner(void)
0x1800bafd3  mov     r9d, 28h ; '('
0x1800bafd9  test    eax, eax
0x1800bafdb  jnz     loc_1800BB779
0x1800bafe1  lea     r8, sourceString
0x1800bafe8  mov     dword ptr [rsp+130h+var_110], 2E43h
0x1800baff0  lea     rdx, EFS_TRACE_START_EVENT
0x1800baff7  call    fnEfsLogTrace1Strings
0x1800baffc  mov     rcx, [r13+30h]; this
0x1800bb000  lea     rdx, [rbp+57h+var_80]; void **
0x1800bb004  call    ?RevertToSelf@CDplServiceImpl@@AEAAJPEAPEAX@Z; CDplServiceImpl::RevertToSelf(void * *)
0x1800bb009  mov     rcx, cs:g_hPublisher
0x1800bb010  lea     r9, sourceString
0x1800bb017  mov     dword ptr [rsp+130h+var_100], 2E43h
0x1800bb01f  lea     r8, EFS_TRACE_COMPLETE_EVENT_ERROR
0x1800bb026  mov     dword ptr [rsp+130h+var_108], 28h ; '('
0x1800bb02e  lea     rdx, EFS_TRACE_COMPLETE_EVENT
0x1800bb035  mov     dword ptr [rsp+130h+var_110], eax
0x1800bb039  mov     edi, eax
0x1800bb03b  call    fnEfsLogTrace1String1Dword
0x1800bb040  test    eax, eax
0x1800bb042  js      loc_1800BB7BA
0x1800bb048  mov     r9d, 28h ; '('
0x1800bb04e  mov     dword ptr [rsp+130h+var_110], 2E49h
0x1800bb056  lea     r8, sourceString
0x1800bb05d  lea     rdx, EFS_TRACE_START_EVENT
0x1800bb064  call    fnEfsLogTrace1Strings
0x1800bb069  mov     rcx, [r13+68h]; unsigned __int16 *
0x1800bb06d  lea     rdx, [rbp+57h+hToken]; void **
0x1800bb071  call    ?EdpCredSvcQuerySessionUserTokenBySid@@YAJPEBGPEAPEAX@Z; EdpCredSvcQuerySessionUserTokenBySid(ushort const *,void * *)
0x1800bb076  mov     rcx, cs:g_hPublisher
0x1800bb07d  lea     r9, sourceString
0x1800bb084  mov     dword ptr [rsp+130h+var_100], 2E49h
0x1800bb08c  lea     r8, EFS_TRACE_COMPLETE_EVENT_ERROR
0x1800bb093  mov     dword ptr [rsp+130h+var_108], 28h ; '('
0x1800bb09b  lea     rdx, EFS_TRACE_COMPLETE_EVENT
0x1800bb0a2  mov     dword ptr [rsp+130h+var_110], eax
0x1800bb0a6  mov     edi, eax
0x1800bb0a8  call    fnEfsLogTrace1String1Dword
0x1800bb0ad  test    eax, eax
0x1800bb0af  js      loc_1800BB7BA
0x1800bb0b5  mov     rcx, [rbp+57h+hToken]; hToken
0x1800bb0b9  test    rcx, rcx
0x1800bb0bc  jnz     short loc_1800BB0D6
0x1800bb0be  mov     edi, 800703F0h
0x1800bb0c3  mov     dword ptr [rsp+130h+var_110], 2E4Fh
0x1800bb0cb  mov     r8d, 800703F0h
0x1800bb0d1  jmp     loc_1800BB7A1
0x1800bb0d6  call    cs:__imp_ImpersonateLoggedOnUser
0x1800bb0dc  test    eax, eax
0x1800bb0de  jnz     short loc_1800BB105
0x1800bb0e0  call    cs:__imp_GetLastError
0x1800bb0e6  mov     edi, eax
0x1800bb0e8  test    eax, eax
0x1800bb0ea  jle     short loc_1800BB0F5
0x1800bb0ec  movzx   edi, ax
0x1800bb0ef  or      edi, 80070000h
0x1800bb0f5  mov     dword ptr [rsp+130h+var_110], 2E55h
0x1800bb0fd  mov     r8d, edi
0x1800bb100  jmp     loc_1800BB7A1
0x1800bb105  mov     r9d, 28h ; '('
0x1800bb10b  mov     dword ptr [rsp+130h+var_110], 2E5Eh
0x1800bb113  lea     r8, sourceString
0x1800bb11a  lea     rdx, EFS_TRACE_START_EVENT
0x1800bb121  call    fnEfsLogTrace1Strings
0x1800bb126  lea     r8, [rsp+130h+var_D8]; int *
0x1800bb12b  xor     edx, edx; unsigned __int16 *
0x1800bb12d  mov     rcx, r13; this
0x1800bb130  call    ?IsAutoRecoverySupported@CDplUser@@AEAAJPEBGPEAH@Z; CDplUser::IsAutoRecoverySupported(ushort const *,int *)
0x1800bb135  mov     rcx, cs:g_hPublisher
0x1800bb13c  lea     r9, sourceString
0x1800bb143  mov     dword ptr [rsp+130h+var_100], 2E5Eh
0x1800bb14b  lea     r8, EFS_TRACE_COMPLETE_EVENT_ERROR
0x1800bb152  mov     dword ptr [rsp+130h+var_108], 28h ; '('
0x1800bb15a  lea     rdx, EFS_TRACE_COMPLETE_EVENT
0x1800bb161  mov     dword ptr [rsp+130h+var_110], eax
0x1800bb165  mov     edi, eax
0x1800bb167  call    fnEfsLogTrace1String1Dword
0x1800bb16c  xor     ecx, ecx
0x1800bb16e  test    eax, eax
0x1800bb170  js      loc_1800BB771
0x1800bb176  cmp     [rsp+130h+var_D8], ecx
0x1800bb17a  jnz     short loc_1800BB1AA
0x1800bb17c  lea     r12d, [rcx+1]
0x1800bb180  mov     dword ptr [rsp+130h+var_110], 2E66h
0x1800bb188  lea     r9d, [rcx+28h]
0x1800bb18c  mov     r8d, r12d
0x1800bb18f  mov     rcx, cs:g_hPublisher
0x1800bb196  lea     rdx, EFS_TRACE_STATUS
0x1800bb19d  mov     edi, r12d
0x1800bb1a0  call    fnEfsLogTrace1
0x1800bb1a5  jmp     loc_1800BB771
0x1800bb1aa  mov     eax, ecx
0x1800bb1ac  inc     ecx
0x1800bb1ae  mov     [rsp+130h+var_DC], ecx
0x1800bb1b2  imul    ecx, eax, 0FAh; dwMilliseconds
0x1800bb1b8  call    cs:__imp_Sleep
0x1800bb1be  test    rsi, rsi
0x1800bb1c1  jz      loc_1800BB2EA
0x1800bb1c7  cmp     [rsi], bx
0x1800bb1ca  jz      loc_1800BB2EA
0x1800bb1d0  lea     rdx, [rbp+57h+Uuid]; Uuid
0x1800bb1d4  mov     rcx, rsi; StringUuid
0x1800bb1d7  call    cs:__imp_UuidFromStringW
0x1800bb1dd  mov     r9d, 28h ; '('
0x1800bb1e3  mov     dword ptr [rsp+130h+var_110], 2E8Eh
0x1800bb1eb  lea     r8, sourceString
0x1800bb1f2  mov     ebx, eax
0x1800bb1f4  lea     rdx, EFS_TRACE_START_EVENT
0x1800bb1fb  call    fnEfsLogTrace1Strings
0x1800bb200  xor     eax, eax
0x1800bb202  mov     dword ptr [rsp+130h+var_100], 2E8Eh
0x1800bb20a  mov     ecx, ebx
0x1800bb20c  mov     dword ptr [rsp+130h+var_108], 28h ; '('
0x1800bb214  or      ecx, 80010000h
0x1800bb21a  lea     r9, sourceString
0x1800bb221  mov     edi, eax
0x1800bb223  lea     r8, EFS_TRACE_COMPLETE_EVENT_ERROR
0x1800bb22a  test    ebx, ebx
0x1800bb22c  lea     rdx, EFS_TRACE_COMPLETE_EVENT
0x1800bb233  cmovnz  edi, ecx
0x1800bb236  mov     rcx, cs:g_hPublisher
0x1800bb23d  mov     dword ptr [rsp+130h+var_110], edi
0x1800bb241  call    fnEfsLogTrace1String1Dword
0x1800bb246  xor     ebx, ebx
0x1800bb248  test    eax, eax
0x1800bb24a  js      loc_1800BB741
0x1800bb250  mov     r14d, 2E97h
0x1800bb256  lea     r9d, [rbx+28h]
0x1800bb25a  lea     r8, sourceString
0x1800bb261  mov     dword ptr [rsp+130h+var_110], r14d
0x1800bb266  lea     rdx, EFS_TRACE_START_EVENT
0x1800bb26d  call    fnEfsLogTrace1Strings
0x1800bb272  lea     rax, [rbp+57h+var_D0]
0x1800bb276  xor     r9d, r9d
0x1800bb279  mov     [rsp+130h+var_F8], rax
0x1800bb27e  lea     rdx, [rbp+57h+Uuid]
0x1800bb282  lea     rax, [rbp+57h+var_B8]
0x1800bb286  xor     r8d, r8d
0x1800bb289  mov     [rsp+130h+var_100], rax
0x1800bb28e  lea     ecx, [rbx+1]
0x1800bb291  lea     rax, [rbp+57h+hInternet]
0x1800bb295  mov     [rsp+130h+var_108], rax
0x1800bb29a  mov     [rsp+130h+var_110], rbx
0x1800bb29f  call    ?WIPCreateRequestForAAD@@YAJW4_WIP_AAD_REQUEST_TYPE@@QEAU_GUID@@QEBG2PEAPEAGPEAPEAX44@Z; WIPCreateRequestForAAD(_WIP_AAD_REQUEST_TYPE,_GUID * const,ushort const * const,ushort const * const,ushort * *,void * *,void * *,void * *)
0x1800bb2a4  mov     rcx, cs:g_hPublisher
0x1800bb2ab  lea     r9, sourceString
0x1800bb2b2  mov     dword ptr [rsp+130h+var_100], r14d
0x1800bb2b7  lea     r8, EFS_TRACE_COMPLETE_EVENT_ERROR
0x1800bb2be  mov     dword ptr [rsp+130h+var_108], 28h ; '('
0x1800bb2c6  lea     rdx, EFS_TRACE_COMPLETE_EVENT
0x1800bb2cd  mov     dword ptr [rsp+130h+var_110], eax
0x1800bb2d1  mov     edi, eax
0x1800bb2d3  call    fnEfsLogTrace1String1Dword
0x1800bb2d8  test    eax, eax
0x1800bb2da  js      loc_1800BB73D
0x1800bb2e0  mov     ebx, 1
0x1800bb2e5  jmp     loc_1800BB381
0x1800bb2ea  mov     edi, 2
0x1800bb2ef  mov     dword ptr [rsp+130h+var_110], 2E83h
0x1800bb2f7  lea     r8, sourceString
0x1800bb2fe  mov     ebx, edi
0x1800bb300  lea     rdx, EFS_TRACE_START_EVENT
0x1800bb307  lea     r9d, [rdi+26h]
0x1800bb30b  call    fnEfsLogTrace1Strings
0x1800bb310  lea     rax, [rbp+57h+var_D0]
0x1800bb314  xor     r14d, r14d
0x1800bb317  mov     [rsp+130h+var_F8], rax
0x1800bb31c  xor     r9d, r9d
0x1800bb31f  lea     rax, [rbp+57h+var_B8]
0x1800bb323  xor     r8d, r8d
0x1800bb326  mov     [rsp+130h+var_100], rax
0x1800bb32b  xor     edx, edx
0x1800bb32d  lea     rax, [rbp+57h+hInternet]
0x1800bb331  mov     ecx, edi
0x1800bb333  mov     [rsp+130h+var_108], rax
0x1800bb338  mov     [rsp+130h+var_110], r14
0x1800bb33d  call    ?WIPCreateRequestForAAD@@YAJW4_WIP_AAD_REQUEST_TYPE@@QEAU_GUID@@QEBG2PEAPEAGPEAPEAX44@Z; WIPCreateRequestForAAD(_WIP_AAD_REQUEST_TYPE,_GUID * const,ushort const * const,ushort const * const,ushort * *,void * *,void * *,void * *)
0x1800bb342  mov     rcx, cs:g_hPublisher
0x1800bb349  lea     r9, sourceString
0x1800bb350  mov     dword ptr [rsp+130h+var_100], 2E83h
0x1800bb358  lea     r8, EFS_TRACE_COMPLETE_EVENT_ERROR
0x1800bb35f  mov     dword ptr [rsp+130h+var_108], 28h ; '('
0x1800bb367  lea     rdx, EFS_TRACE_COMPLETE_EVENT
0x1800bb36e  mov     dword ptr [rsp+130h+var_110], eax
0x1800bb372  mov     edi, eax
0x1800bb374  call    fnEfsLogTrace1String1Dword
0x1800bb379  test    eax, eax
0x1800bb37b  js      loc_1800BB73D
0x1800bb381  cmp     edi, 1
0x1800bb384  jz      loc_1800BB73D
0x1800bb38a  mov     r9d, 28h ; '('
0x1800bb390  mov     dword ptr [rsp+130h+var_110], 2EAAh
0x1800bb398  lea     r8, sourceString
0x1800bb39f  lea     rdx, EFS_TRACE_START_EVENT
0x1800bb3a6  call    fnEfsLogTrace1Strings
0x1800bb3ab  mov     r14, [rbp+57h+var_D0]
0x1800bb3af  xor     r8d, r8d
0x1800bb3b2  mov     rdx, r14
0x1800bb3b5  mov     ecx, ebx
0x1800bb3b7  call    ?WIPSendHttpRequest@@YAJW4_WIP_AAD_REQUEST_TYPE@@PEAXQEBG@Z; WIPSendHttpRequest(_WIP_AAD_REQUEST_TYPE,void *,ushort const * const)
0x1800bb3bc  mov     rcx, cs:g_hPublisher
0x1800bb3c3  lea     r9, sourceString
0x1800bb3ca  mov     dword ptr [rsp+130h+var_100], 2EAAh
0x1800bb3d2  lea     r8, EFS_TRACE_COMPLETE_EVENT_ERROR
0x1800bb3d9  mov     dword ptr [rsp+130h+var_108], 28h ; '('
0x1800bb3e1  lea     rdx, EFS_TRACE_COMPLETE_EVENT
0x1800bb3e8  mov     dword ptr [rsp+130h+var_110], eax
0x1800bb3ec  mov     edi, eax
0x1800bb3ee  call    fnEfsLogTrace1String1Dword
0x1800bb3f3  test    eax, eax
0x1800bb3f5  js      loc_1800BB741
0x1800bb3fb  lea     rax, [rsp+130h+var_E0]
0x1800bb400  mov     rdx, r14
0x1800bb403  lea     r9, [rbp+57h+lpMem]
0x1800bb407  mov     [rsp+130h+var_110], rax
0x1800bb40c  lea     r8, [rbp+57h+var_B0]
0x1800bb410  mov     ecx, ebx
0x1800bb412  call    ?WIPGetAndParseResponse@@YAJW4_WIP_AAD_REQUEST_TYPE@@PEAXPEAPEAPEAGPEAPEAKPEAK@Z; WIPGetAndParseResponse(_WIP_AAD_REQUEST_TYPE,void *,ushort * * *,ulong * *,ulong *)
0x1800bb417  mov     edi, eax
0x1800bb419  cmp     eax, 80070103h
0x1800bb41e  jz      loc_1800BB712
0x1800bb424  xor     ebx, ebx
0x1800bb426  test    eax, eax
0x1800bb428  jns     loc_1800BB4EC
0x1800bb42e  lea     rcx, [rbp+57h+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
  ... truncated ...
```
