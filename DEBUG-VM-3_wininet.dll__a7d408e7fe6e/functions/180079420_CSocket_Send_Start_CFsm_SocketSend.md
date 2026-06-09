# CSocket::Send_Start(CFsm_SocketSend *)

- ea: `0x180079420`
- end: `0x18007a126`
- name: `?Send_Start@CSocket@@QEAAKPEAVCFsm_SocketSend@@@Z`
- size: `3334`
- prototype: `unsigned int __fastcall(CSocket *__hidden this, struct CFsm_SocketSend *)`
- caller_count: `1`
- callee_count: `27`
- tags: `file_ops, broker_com_uri`

## callers

- `0x180077b70`

## callees

- `0x180009cf0`
- `0x180019d20`
- `0x18004e0f0`
- `0x18005c7d8`
- `0x18005e7e0`
- `0x1800701d0`
- `0x180079420`
- `0x18007a12c`
- `0x18007ad20`
- `0x180087c14`
- `0x18008a970`
- `0x18008aaf0`
- `0x1800bbbc4`
- `0x1800bdee8`
- `0x1800e2fe8`
- `0x1800fc53c`
- `0x1801420f8`
- `0x18014a3a4`
- `0x18014a7a0`
- `0x1801d005c`
- `0x1801e1790`
- `0x1801e3c78`
- `0x1801e4988`
- `0x1801e67a8`
- `0x1801e75a4`
- `0x1801ecc00`
- `0x1801ee010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180079516`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800795da`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18007974c`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180079892`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180079516`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800795da`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18007974c`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180079892`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800794dd`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18007956d`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180079717`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18007985a`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800794dd`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18007956d`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180079717`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18007985a`
- `api-ms-win-core-synch-l1-1-0!CreateEventA` at `0x180079d3b`
- `api-ms-win-core-synch-l1-1-0!CreateEventA` at `0x180079d3b`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180079f50`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180079f50`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x180079935`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x180079935`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x1800798a8`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x1800798a8`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800797c0`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800797c0`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x180079611`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x180079643`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x1800796c0`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x1800799ca`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x180079611`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x180079643`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x1800796c0`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x1800799ca`
- `api-ms-win-core-threadpool-l1-2-0!CancelThreadpoolIo` at `0x180079919`
- `api-ms-win-core-threadpool-l1-2-0!CancelThreadpoolIo` at `0x180079919`
- `api-ms-win-core-threadpool-l1-2-0!StartThreadpoolIo` at `0x1800798cf`
- `api-ms-win-core-threadpool-l1-2-0!StartThreadpoolIo` at `0x1800798cf`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180079da8`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180079da8`
- `WS2_32!WSASend` at `0x1800798fe`
- `WS2_32!WSASend` at `0x1800798fe`

## pseudocode

```c
__int64 __fastcall CSocket::Send_Start(CSocket *this, struct CFsm_SocketSend *a2, __int64 a3)
{
  CSocket *v4; // rsi
  int v5; // eax
  int v6; // r12d
  int v7; // edi
  __int64 v8; // r13
  __int64 v9; // rbx
  __int64 v10; // r14
  __int64 v11; // r9
  _DWORD *v12; // rdi
  struct _RTL_CRITICAL_SECTION *v13; // rdi
  int v14; // eax
  int v15; // esi
  int v16; // r14d
  int v17; // edi
  __int64 v18; // rdi
  int TimeoutValue; // edi
  int v20; // edi
  __int64 v21; // rax
  int v22; // eax
  DWORD TickCount; // eax
  DWORD v24; // edx
  int v25; // ecx
  ULONG v26; // eax
  HANDLE v27; // rcx
  char *v28; // rax
  char *v29; // r14
  CWxSocket *v30; // rdi
  int v31; // edi
  bool v32; // zf
  DWORD v33; // esi
  unsigned int Error; // edi
  int v35; // eax
  signed int v36; // edi
  unsigned int LastError; // r14d
  INTERNET_HANDLE_OBJECT *v38; // rcx
  const char *v39; // r14
  int v40; // esi
  __int64 v41; // rax
  char v42; // r9
  __int64 v43; // rcx
  __int64 v44; // r8
  __int64 v45; // rcx
  __int64 v46; // rdi
  unsigned __int16 v47; // di
  __int64 v48; // rcx
  const char *v49; // rax
  __int64 v50; // r8
  HANDLE EventA; // rdi
  CSocket *v53; // rax
  void *v54; // rcx
  int v55; // ecx
  unsigned int v56; // eax
  unsigned int v57; // eax
  unsigned __int64 v58; // rax
  __int64 v60; // r14
  int v61; // ebx
  int v62; // eax
  int v63; // ecx
  int v64; // [rsp+50h] [rbp-F8h]
  CSocket *v65; // [rsp+68h] [rbp-E0h] BYREF
  __int64 ThreadInfo; // [rsp+70h] [rbp-D8h] BYREF
  _WSABUF Buffers; // [rsp+78h] [rbp-D0h] BYREF
  int v68; // [rsp+88h] [rbp-C0h] BYREF
  __int128 v69; // [rsp+90h] [rbp-B8h] BYREF
  DWORD NumberOfBytesSent[4]; // [rsp+A0h] [rbp-A8h] BYREF
  char v71[16]; // [rsp+B0h] [rbp-98h] BYREF
  __int64 *p_ThreadInfo; // [rsp+C0h] [rbp-88h]
  __int64 v73; // [rsp+C8h] [rbp-80h]
  CSocket **v74; // [rsp+D0h] [rbp-78h]
  __int64 v75; // [rsp+D8h] [rbp-70h]
  int *v76; // [rsp+E0h] [rbp-68h]
  __int64 v77; // [rsp+E8h] [rbp-60h]
  const char *v78; // [rsp+F0h] [rbp-58h]
  int v79; // [rsp+F8h] [rbp-50h]
  int v80; // [rsp+FCh] [rbp-4Ch]
  __int128 *v81; // [rsp+100h] [rbp-48h]
  __int64 v82; // [rsp+108h] [rbp-40h]

  v65 = this;
  v4 = this;
  if ( (xmmword_180266B60 & 8) != 0 )
  {
    v60 = *((_QWORD *)a2 + 25);
    v61 = (*(unsigned __int16 (__fastcall **)(CSocket *))(*(_QWORD *)this + 176LL))(this);
    v62 = (*(__int64 (__fastcall **)(CSocket *))(*(_QWORD *)this + 32LL))(this);
    v4 = this;
    WPP_SF_qPdqqdD(
      v63,
      70,
      (unsigned int)&WPP_bd14be58d2f038a275675270d4ce3d8e_Traceguids,
      (_DWORD)this,
      v62,
      v61,
      (__int64)a2,
      v60);
  }
  v5 = *((_DWORD *)a2 + 10);
  v6 = *((_DWORD *)a2 + 21);
  v7 = 0;
  v8 = *((_QWORD *)a2 + 9);
  v9 = 0;
  v68 = 0;
  Buffers = 0;
  v64 = v5;
  ThreadInfo = InternetGetThreadInfo(this, a2, a3);
  v10 = ThreadInfo;
  if ( !ThreadInfo )
  {
    LastError = 12004;
    v64 = 12004;
    goto LABEL_96;
  }
  v11 = *((_QWORD *)a2 + 9);
  if ( v11 )
  {
    v12 = (_DWORD *)(v11 + 144);
    if ( (BYTE1(xmmword_180266B60) & 0x20) != 0 )
      WPP_SF_qD(1037, 11, &WPP_32522a7fa2653838cddfc2ba8aa3ec74_Traceguids, v11, *v12);
    if ( *v12 )
    {
      LastError = 12017;
      v7 = 0;
      v64 = 12017;
      goto LABEL_96;
    }
  }
  v13 = (struct _RTL_CRITICAL_SECTION *)((char *)v4 + 224);
  v14 = 0;
  if ( v4 != (CSocket *)-224LL )
  {
    EnterCriticalSection((LPCRITICAL_SECTION)((char *)v4 + 224));
    v14 = 1;
  }
  v9 = *((_QWORD *)v4 + 27);
  if ( v9 )
  {
    _InterlockedIncrement((volatile signed __int32 *)v9);
    v15 = 1;
  }
  else
  {
    v15 = 0;
  }
  if ( v13 && v14 )
    LeaveCriticalSection(v13);
  if ( v15 )
  {
    if ( v64 )
    {
      LastError = v64;
      if ( v64 == 12901 )
      {
        LastError = 12031;
        v64 = 12031;
        RecordInternetError(12901, 12031);
      }
      else
      {
LABEL_154:
        if ( LastError == 997 )
          goto LABEL_131;
      }
      goto LABEL_95;
    }
    if ( v6 )
      goto LABEL_39;
    if ( (xmmword_180266B60 & 8) != 0 )
    {
      v58 = *((_QWORD *)a2 + 25);
      v69 = v58;
      if ( v58 && (LODWORD(v58) = *((_DWORD *)a2 + 52), (unsigned int)v58 > 0xFFFF) )
        WORD4(v69) = -1;
      else
        WORD4(v69) = v58;
      WPP_SF__COUNTEDSTRING_(1027, 71, &WPP_bd14be58d2f038a275675270d4ce3d8e_Traceguids, &v69);
    }
    if ( !v8 )
      goto LABEL_36;
    v16 = 0;
    if ( (BYTE1(xmmword_180266B60) & 1) != 0 )
    {
      (*(void (__fastcall **)(CSocket *))(*(_QWORD *)v65 + 16LL))(v65);
      (*(void (__fastcall **)(CSocket *))(*(_QWORD *)v65 + 32LL))(v65);
      WPP_SF_qqPd(
        v55,
        35,
        (unsigned int)&WPP_a85fccec657a30c16cbc767298893445_Traceguids,
        *(_QWORD *)(v8 + 128),
        (__int64)v65);
    }
    if ( v8 != -200 )
    {
      EnterCriticalSection((LPCRITICAL_SECTION)(v8 + 200));
      v16 = 1;
    }
    if ( !*(_DWORD *)(v8 + 580) )
    {
      v17 = 0;
      if ( (unsigned int)HANDLE_OBJECT::IsInvalidated((HANDLE_OBJECT *)v8) )
      {
LABEL_29:
        if ( (BYTE1(xmmword_180266B60) & 1) != 0 )
          WPP_SF_(1032, 36, &WPP_a85fccec657a30c16cbc767298893445_Traceguids);
        if ( v16 && v8 != -200 )
          LeaveCriticalSection((LPCRITICAL_SECTION)(v8 + 200));
        if ( v17 )
        {
          v10 = ThreadInfo;
          v68 = 1;
LABEL_36:
          if ( (*((_BYTE *)a2 + 212) & 0x20) != 0 )
            InternetIndicateStatus(0x1Eu);
          *((_DWORD *)a2 + 34) = GetTickCount();
          *((_DWORD *)a2 + 35) = 1;
          while ( 1 )
          {
LABEL_39:
            if ( !*((_DWORD *)a2 + 52) )
            {
              LastError = 0;
              goto LABEL_95;
            }
            v18 = *((_QWORD *)a2 + 28);
            if ( v18 )
              *(_DWORD *)(v18 + 408) = GetTickCount();
            if ( *((_DWORD *)v65 + 10) )
            {
              TimeoutValue = -1;
            }
            else
            {
              TimeoutValue = GetTimeoutValue(5);
              if ( v8
                && *(_DWORD *)(v8 + 512) != -1
                && *(_DWORD *)(v8 + 136) == 1902465608
                && (unsigned int)HTTP_REQUEST_HANDLE_OBJECT::CanRetrieveFromCache((HTTP_REQUEST_HANDLE_OBJECT *)v8, 1) )
              {
                v20 = GetTimeoutValue(63);
                v21 = *((_QWORD *)a2 + 29);
                if ( !v21 || (v22 = *(_DWORD *)(v21 + 416)) == 0 )
                  v22 = v20;
                TimeoutValue = v22 + v20;
              }
            }
            TickCount = GetTickCount();
            v24 = TimeoutValue;
            if ( TimeoutValue != -1 )
              v24 = TickCount + TimeoutValue;
            *((_DWORD *)a2 + 32) = v24;
            *((_DWORD *)a2 + 33) = TickCount > v24;
            v25 = 0;
            *(_QWORD *)&v69 = v9 + 8;
            if ( !TimeoutValue )
              TimeoutValue = -1;
            if ( v9 != -32 )
            {
              EnterCriticalSection((LPCRITICAL_SECTION)(v9 + 32));
              v25 = 1;
            }
            *(_DWORD *)(v9 + 184) = TimeoutValue;
            *(_DWORD *)(v9 + 192) = TimeoutValue != -1;
            if ( v9 != -32 && v25 )
              LeaveCriticalSection((LPCRITICAL_SECTION)(v9 + 32));
            LODWORD(v69) = (*(__int64 (__fastcall **)(CSocket *))(*(_QWORD *)v65 + 416LL))(v65);
            if ( !(_DWORD)v69 && !*((_QWORD *)v65 + 34) )
            {
              EventA = CreateEventA(0, 0, 0, 0);
              v53 = v65;
              v54 = (void *)*((_QWORD *)v65 + 34);
              if ( v54 )
              {
                CloseHandle(v54);
                v53 = v65;
              }
              *((_QWORD *)v53 + 34) = EventA;
              if ( !EventA )
              {
                LastError = WxGetLastError(v54);
                v64 = LastError;
                goto LABEL_154;
              }
            }
            Buffers.buf = (CHAR *)*((_QWORD *)a2 + 25);
            if ( !GlobalEnableBufferBreaking
              || (v26 = GlobalBufferBreakingSize, *((_DWORD *)a2 + 52) <= (unsigned int)GlobalBufferBreakingSize) )
            {
              v26 = *((_DWORD *)a2 + 52);
            }
            v27 = g_hWxProcessHeap;
            Buffers.len = v26;
            *(_QWORD *)(v10 + 80) = 0;
            v28 = (char *)HeapAlloc(v27, 0, 0x60u);
            v29 = v28;
            if ( !v28 )
              break;
            *(_QWORD *)v28 = 1;
            *(_QWORD *)(v28 + 44) = 0;
            *((_DWORD *)v28 + 13) = 0;
            *((_DWORD *)v28 + 10) = 0;
            *((_QWORD *)v28 + 7) = 0;
            *((_QWORD *)v28 + 8) = 0;
            *((_QWORD *)v28 + 9) = 0;
            *((_QWORD *)v28 + 10) = 0;
            *((_QWORD *)v28 + 11) = 0;
            *(_OWORD *)(v28 + 8) = 0;
            *(_OWORD *)(v28 + 24) = 0;
            _InterlockedIncrement((volatile signed __int32 *)v9);
            v30 = (CWxSocket *)*((_QWORD *)v28 + 9);
            if ( v30 && _InterlockedExchangeAdd((volatile signed __int32 *)v30, 0xFFFFFFFF) == 1 )
            {
              CWxSocket::~CWxSocket(v30);
              operator delete(v30, 0x270u);
            }
            *((_QWORD *)v29 + 9) = v9;
            *((_QWORD *)v29 + 6) = CWxSocket::SendCompletion;
            *((_QWORD *)v29 + 7) = CSocket::SendCompletion;
            *((_DWORD *)v29 + 10) = 2;
            *((_QWORD *)v29 + 8) = a2;
            v31 = 0;
            if ( v9 != -32 )
            {
              EnterCriticalSection((LPCRITICAL_SECTION)(v9 + 32));
              v31 = 1;
            }
            v32 = (*(_DWORD *)(v9 + 188))++ == -1;
            if ( !v32
              && !*(_DWORD *)(v9 + 196)
              && *(_DWORD *)(v9 + 192)
              && (unsigned int)(*(_DWORD *)(v9 + 184) - 1) <= 0xFFFFFFFD )
            {
              *(_DWORD *)(v9 + 196) = 1;
              _InterlockedIncrement((volatile signed __int32 *)v9);
              CWxTimerWheel::Set(
                (CWxTimerWheel *)1,
                (struct CWxTimer *)(v9 + 200),
                *(_DWORD *)(v9 + 184),
                (void (*)(void *))CWxSocketTimer::Callback,
                (void *)v9);
            }
            if ( v31 && v9 != -32 )
              LeaveCriticalSection((LPCRITICAL_SECTION)(v9 + 32));
            v33 = 0;
            NumberOfBytesSent[0] = 0;
            AcquireSRWLockShared((PSRWLOCK)(v9 + 8));
            if ( *(_QWORD *)(v9 + 16) == -1 )
            {
              Error = 1359;
              if ( *(_DWORD *)(v9 + 300) )
                Error = *(_DWORD *)(v9 + 300);
            }
            else
            {
              _InterlockedIncrement((volatile signed __int32 *)v29);
              Error = 997;
              if ( *(_DWORD *)(v9 + 308) )
                Error = 0;
              StartThreadpoolIo(*(PTP_IO *)(v9 + 24));
              if ( WSASend(*(_QWORD *)(v9 + 16), &Buffers, 1u, NumberOfBytesSent, 0, (LPWSAOVERLAPPED)(v29 + 8), 0) == -1 )
                Error = WxWSAGetLastError();
              if ( Error != 997 )
                CancelThreadpoolIo(*(PTP_IO *)(v9 + 24));
              CWxIoContext::Release((CWxIoContext *)v29);
              if ( !Error )
                v33 = NumberOfBytesSent[0];
            }
            ReleaseSRWLockShared((PSRWLOCK)(v9 + 8));
            if ( Error == 997 )
            {
              v36 = -2147023899;
LABEL_178:
              v33 = 0;
              goto LABEL_91;
            }
            v35 = (*((__int64 (__fastcall **)(_QWORD, char *, _QWORD))v29 + 6))(Error, v29, v33);
            v36 = v35;
            if ( v35 > 0 )
              v36 = (unsigned __int16)v35 | 0x80070000;
            if ( v36 < 0 )
              v33 = 0;
            CWxIoContext::Release((CWxIoContext *)v29);
LABEL_91:
            if ( v36 < 0 )
            {
              v57 = WX_WIN32_FROM_HR((unsigned int)v36);
              v64 = MapInternetError(v57);
              LastError = v64;
              if ( v64 == 997 )
              {
                if ( (_DWORD)v69 )
                  goto LABEL_131;
                WaitForSingleObject(*((HANDLE *)v65 + 34), 0xFFFFFFFF);
                v64 = *((_DWORD *)a2 + 10);
                v33 = *((_DWORD *)a2 + 60);
              }
            }
            v10 = ThreadInfo;
            *(_QWORD *)(ThreadInfo + 80) = a2;
            if ( v64 )
            {
              LastError = v64;
              goto LABEL_154;
            }
            *((_DWORD *)a2 + 54) += v33;
            *((_QWORD *)a2 + 25) += v33;
            *((_DWORD *)a2 + 52) -= v33;
          }
          v36 = -2147024882;
          goto LABEL_178;
        }
        LastError = 12017;
        v64 = 12017;
        goto LABEL_95;
      }
      if ( !*(_DWORD *)(v8 + 192) )
      {
        (**(void (__fastcall ***)(CSocket *))v65)(v65);
        *(_QWORD *)(v8 + 336) = v65;
      }
    }
    ++*(_DWORD *)(v8 + 192);
    v17 = 1;
    goto LABEL_29;
  }
  LastError = 12017;
  v64 = 12017;
LABEL_95:
  v7 = v68;
LABEL_96:
  if ( *((_DWORD *)a2 + 35) )
    *((_QWORD *)a2 + 17) = GetTickCount() - *((_DWORD *)a2 + 34);
  v38 = (INTERNET_HANDLE_OBJECT *)*((_QWORD *)a2 + 9);
  if ( v38 && (v6 || v7) )
    INTERNET_HANDLE_OBJECT::ResetAbortHandle(v38);
  if ( LastError )
  {
    if ( (Microsoft_Windows_WinINetEnableBits & 0x20) != 0 )
      McTemplateU0pq_EventWriteTransfer(v38, &WININET_HTTP_REQUEST_FAILED, *((_QWORD *)a2 + 8), LastError);
  }
  else
  {
    v39 = "???";
    v40 = 0;
    if ( v8 && *(_DWORD *)(v8 + 136) == 1902465608 )
    {
      v41 = *(int *)(v8 + 3064);
      if ( (unsigned int)v41 <= 0x1E )
      {
        _mm_lfence();
        if ( dword_1801F1D50[6 * v41] != -1 )
          v39 = *(const char **)&dword_1801F1D50[6 * v41 + 2];
      }
      v42 = xmmword_180266B60;
      if ( (xmmword_180266B60 & 2) != 0 )
      {
        WPP_SF_sd(1025, 43, (unsigned int)&WPP_764547bcea91352f6757a10208e155bd_Traceguids, (unsigned int)"Cookie", 0);
        v42 = xmmword_180266B60;
      }
      HIDWORD(ThreadInfo) = 0;
      v43 = *(_QWORD *)(v8 + 1992);
      HIDWORD(ThreadInfo) = 0;
      v44 = v43 - 16;
      if ( v43 == v8 + 1992 )
        v44 = 0;
      if ( v44 )
      {
        v45 = 0;
      }
      else
      {
        HIDWORD(ThreadInfo) = 2854;
        v45 = 2147954550LL;
      }
      if ( (int)v45 < 0 )
        HIDWORD(ThreadInfo) = 4850;
      v46 = 0;
      if ( (int)v45 >= 0 )
        v46 = v44 + 40;
      if ( (v42 & 2) != 0 )
      {
        v56 = WX_WIN32_FROM_HR(v45);
        WPP_SF_d(1025, 44, &WPP_764547bcea91352f6757a10208e155bd_Traceguids, v56);
      }
      if ( v46 && *(_DWORD *)(v46 + 24) )
        v40 = 1;
    }
    if ( (Microsoft_Windows_WinINetEnableBits & 0x10) != 0 )
    {
      v47 = 0;
      if ( v39 )
      {
        HIDWORD(ThreadInfo) = 0;
        v48 = 0xFFFF;
        LOWORD(v68) = 0;
        v49 = v39;
        while ( *v49 )
        {
          ++v49;
          if ( !--v48 )
          {
            HIDWORD(ThreadInfo) = 135;
            goto LABEL_126;
          }
        }
        v47 = -1 - v48;
      }
LABEL_126:
      LOWORD(v68) = v47;
      v65 = (CSocket *)(*(__int64 (__fastcall **)(CSocket *))(*(_QWORD *)v65 + 32LL))(v65);
      ThreadInfo = *((_QWORD *)a2 + 8);
      LODWORD(v69) = v40;
      p_ThreadInfo = &ThreadInfo;
      v74 = &v65;
      v76 = &v68;
      v79 = v47;
      v81 = &v69;
      v73 = 8;
      v75 = 8;
      v77 = 2;
      v78 = v39;
      v80 = 0;
      v82 = 4;
      McGenEventWrite_EventWriteTransfer(&WININET_Context, &WININET_HTTP_REQUEST_SENT, v50, 6, v71);
    }
    if ( (*((_BYTE *)a2 + 212) & 0x20) != 0 )
      InternetIndicateStatus(0x1Fu);
    LastError = v64;
  }
  *((_DWORD *)a2 + 10) = LastError;
  *((_DWORD *)a2 + 21) = 2;
LABEL_131:
  if ( (xmmword_180266B60 & 8) != 0 )
    WPP_SF_d(1027, 72, &WPP_bd14be58d2f038a275675270d4ce3d8e_Traceguids, LastError);
  if ( v9 && _InterlockedExchangeAdd((volatile signed __int32 *)v9, 0xFFFFFFFF) == 1 )
  {
    CWxSocket::~CWxSocket((CWxSocket *)v9);
    operator delete((void *)v9, 0x270u);
  }
  return LastError;
}

```

## disassembly

```asm
0x180079420  mov     [rsp+arg_10], rbx
0x180079425  mov     [rsp+arg_18], rsi
0x18007942a  push    rdi
0x18007942b  push    r12
0x18007942d  push    r13
0x18007942f  push    r14
0x180079431  push    r15
0x180079433  sub     rsp, 120h
0x18007943a  mov     rax, cs:__security_cookie
0x180079441  xor     rax, rsp
0x180079444  mov     [rsp+148h+var_38], rax
0x18007944c  mov     r15, rdx
0x18007944f  mov     [rsp+148h+var_E0], rcx
0x180079454  mov     rsi, rcx
0x180079457  test    byte ptr cs:xmmword_180266B60, 8
0x18007945e  jnz     loc_180079FD9
0x180079464  mov     eax, [r15+28h]
0x180079468  xorps   xmm0, xmm0
0x18007946b  mov     r12d, [r15+54h]
0x18007946f  xor     edi, edi
0x180079471  mov     r13, [r15+48h]
0x180079475  xor     ebx, ebx
0x180079477  mov     [rsp+148h+var_C0], edi
0x18007947e  movups  xmmword ptr [rsp+148h+Buffers.len], xmm0
0x180079483  mov     [rsp+148h+var_F8], eax
0x180079487  mov     [rsp+148h+var_E4], r12d
0x18007948c  call    InternetGetThreadInfo
0x180079491  mov     [rsp+148h+var_D8], rax
0x180079496  mov     r14, rax
0x180079499  mov     ecx, 1
0x18007949e  test    rax, rax
0x1800794a1  jz      loc_180079CC8
0x1800794a7  mov     r9, [r15+48h]
0x1800794ab  test    r9, r9
0x1800794ae  jz      short loc_1800794CC
0x1800794b0  test    byte ptr cs:xmmword_180266B60+1, 20h
0x1800794b7  lea     rdi, [r9+90h]
0x1800794be  jnz     loc_180079E2C
0x1800794c4  cmp     [rdi], ebx
0x1800794c6  jnz     loc_180079DFB
0x1800794cc  lea     rdi, [rsi+0E0h]
0x1800794d3  xor     eax, eax
0x1800794d5  test    rdi, rdi
0x1800794d8  jz      short loc_1800794EA
0x1800794da  mov     rcx, rdi; lpCriticalSection
0x1800794dd  call    cs:__imp_EnterCriticalSection
0x1800794e3  mov     ecx, 1
0x1800794e8  mov     eax, ecx
0x1800794ea  mov     rbx, [rsi+0D8h]
0x1800794f1  test    rbx, rbx
0x1800794f4  jz      loc_18007A048
0x1800794fa  lock inc dword ptr [rbx]
0x1800794fd  mov     esi, ecx
0x1800794ff  test    rdi, rdi
0x180079502  jz      short loc_18007950A
0x180079504  test    eax, eax
0x180079506  jz      short loc_18007951C
0x180079508  jmp     short loc_180079513
0x18007950a  test    eax, eax
0x18007950c  jz      short loc_18007951C
0x18007950e  test    rdi, rdi
0x180079511  jz      short loc_18007951C
0x180079513  mov     rcx, rdi; lpCriticalSection
0x180079516  call    cs:__imp_LeaveCriticalSection
0x18007951c  test    esi, esi
0x18007951e  jz      loc_180079D88
0x180079524  cmp     [rsp+148h+var_F8], 0
0x180079529  jnz     loc_18007A04F
0x18007952f  test    r12d, r12d
0x180079532  jnz     loc_180079629
0x180079538  test    byte ptr cs:xmmword_180266B60, 8
0x18007953f  jnz     loc_180079F6A
0x180079545  test    r13, r13
0x180079548  jz      loc_1800795F8
0x18007954e  lea     rsi, [r13+0C8h]
0x180079555  xor     r14d, r14d
0x180079558  test    byte ptr cs:xmmword_180266B60+1, 1
0x18007955f  jnz     loc_180079E97
0x180079565  test    rsi, rsi
0x180079568  jz      short loc_180079579
0x18007956a  mov     rcx, rsi; lpCriticalSection
0x18007956d  call    cs:__imp_EnterCriticalSection
0x180079573  mov     r14d, 1
0x180079579  cmp     dword ptr [r13+244h], 0
0x180079581  jnz     short loc_1800795B4
0x180079583  mov     rcx, r13; this
0x180079586  xor     edi, edi
0x180079588  call    ?IsInvalidated@HANDLE_OBJECT@@QEBAHXZ; HANDLE_OBJECT::IsInvalidated(void)
0x18007958d  test    eax, eax
0x18007958f  jnz     short loc_1800795C0
0x180079591  cmp     [r13+0C0h], edi
0x180079598  jnz     short loc_1800795B4
0x18007959a  mov     rdi, [rsp+148h+var_E0]
0x18007959f  mov     rcx, rdi
0x1800795a2  mov     rax, [rdi]
0x1800795a5  mov     rax, [rax]
0x1800795a8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800795ad  mov     [r13+150h], rdi
0x1800795b4  inc     dword ptr [r13+0C0h]
0x1800795bb  mov     edi, 1
0x1800795c0  test    byte ptr cs:xmmword_180266B60+1, 1
0x1800795c7  jnz     loc_18007A08B
0x1800795cd  test    r14d, r14d
0x1800795d0  jz      short loc_1800795E0
0x1800795d2  test    rsi, rsi
0x1800795d5  jz      short loc_1800795E0
0x1800795d7  mov     rcx, rsi; lpCriticalSection
0x1800795da  call    cs:__imp_LeaveCriticalSection
0x1800795e0  test    edi, edi
0x1800795e2  jz      loc_180079D98
0x1800795e8  mov     r14, [rsp+148h+var_D8]
0x1800795ed  mov     [rsp+148h+var_C0], 1
0x1800795f8  test    byte ptr [r15+0D4h], 20h
0x180079600  jz      short loc_180079611
0x180079602  xor     r8d, r8d
0x180079605  xor     edx, edx
0x180079607  mov     ecx, 1Eh; unsigned int
0x18007960c  call    InternetIndicateStatus
0x180079611  call    cs:__imp_GetTickCount
0x180079617  mov     [r15+88h], eax
0x18007961e  mov     dword ptr [r15+8Ch], 1
0x180079629  cmp     dword ptr [r15+0D0h], 0
0x180079631  jz      loc_1800799AF
0x180079637  mov     rdi, [r15+0E0h]
0x18007963e  test    rdi, rdi
0x180079641  jz      short loc_18007964F
0x180079643  call    cs:__imp_GetTickCount
0x180079649  mov     [rdi+198h], eax
0x18007964f  mov     rax, [rsp+148h+var_E0]
0x180079654  cmp     dword ptr [rax+28h], 0
0x180079658  jnz     short loc_1800796BB
0x18007965a  mov     ecx, 5
0x18007965f  call    GetTimeoutValue
0x180079664  mov     edi, eax
0x180079666  test    r13, r13
0x180079669  jz      short loc_1800796C0
0x18007966b  cmp     dword ptr [r13+200h], 0FFFFFFFFh
0x180079673  jz      short loc_1800796C0
0x180079675  cmp     dword ptr [r13+88h], 71655248h
0x180079680  jnz     short loc_1800796C0
0x180079682  mov     edx, 1; int
0x180079687  mov     rcx, r13; this
0x18007968a  call    ?CanRetrieveFromCache@HTTP_REQUEST_HANDLE_OBJECT@@QEAAHH@Z; HTTP_REQUEST_HANDLE_OBJECT::CanRetrieveFromCache(int)
0x18007968f  test    eax, eax
0x180079691  jz      short loc_1800796C0
0x180079693  mov     ecx, 3Fh ; '?'
0x180079698  call    GetTimeoutValue
0x18007969d  mov     edi, eax
0x18007969f  mov     rax, [r15+0E8h]
0x1800796a6  test    rax, rax
0x1800796a9  jz      short loc_1800796B5
0x1800796ab  mov     eax, [rax+1A0h]
0x1800796b1  test    eax, eax
0x1800796b3  jnz     short loc_1800796B7
0x1800796b5  mov     eax, edi
0x1800796b7  add     edi, eax
0x1800796b9  jmp     short loc_1800796C0
0x1800796bb  mov     edi, 0FFFFFFFFh
0x1800796c0  call    cs:__imp_GetTickCount
0x1800796c6  mov     r8d, 0FFFFFFFFh
0x1800796cc  lea     rsi, [rbx+20h]
0x1800796d0  cmp     edi, r8d
0x1800796d3  lea     r12, [rbx+8]
0x1800796d7  mov     edx, edi
0x1800796d9  lea     ecx, [rax+rdi]
0x1800796dc  cmovnz  edx, ecx
0x1800796df  xor     ecx, ecx
0x1800796e1  cmp     eax, edx
0x1800796e3  mov     [r15+80h], edx
0x1800796ea  setnbe  cl
0x1800796ed  mov     [r15+84h], ecx
0x1800796f4  xor     ecx, ecx
0x1800796f6  test    edi, edi
0x1800796f8  mov     dword ptr [rsp+148h+var_B8+4], 0
0x180079703  mov     qword ptr [rsp+148h+var_B8], r12
0x18007970b  cmovz   edi, r8d
0x18007970f  test    rsi, rsi
0x180079712  jz      short loc_180079728
0x180079714  mov     rcx, rsi; lpCriticalSection
0x180079717  call    cs:__imp_EnterCriticalSection
0x18007971d  mov     ecx, 1
0x180079722  mov     r8d, 0FFFFFFFFh
0x180079728  xor     eax, eax
0x18007972a  mov     [rbx+0B8h], edi
0x180079730  cmp     edi, r8d
0x180079733  setnz   al
0x180079736  mov     [rbx+0C0h], eax
0x18007973c  test    rsi, rsi
0x18007973f  jz      loc_180079E52
0x180079745  test    ecx, ecx
0x180079747  jz      short loc_180079752
0x180079749  mov     rcx, rsi; lpCriticalSection
0x18007974c  call    cs:__imp_LeaveCriticalSection
0x180079752  mov     rdi, [rsp+148h+var_E0]
0x180079757  mov     rcx, rdi
0x18007975a  mov     rax, [rdi]
0x18007975d  mov     rax, [rax+1A0h]
0x180079764  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180079769  mov     dword ptr [rsp+148h+var_B8], eax
0x180079770  test    eax, eax
0x180079772  jz      loc_180079D23
0x180079778  cmp     cs:GlobalEnableBufferBreaking, 0
0x18007977f  mov     rax, [r15+0C8h]
0x180079786  mov     [rsp+148h+Buffers.buf], rax
0x18007978e  jnz     loc_18007A0A6
0x180079794  mov     eax, [r15+0D0h]
0x18007979b  mov     rcx, cs:g_hWxProcessHeap; hHeap
0x1800797a2  xor     edi, edi
0x1800797a4  mov     [rsp+148h+Buffers.len], eax
0x1800797a8  xor     edx, edx; dwFlags
0x1800797aa  mov     [r14+50h], rdi
0x1800797ae  mov     r8d, 60h ; '`'; dwBytes
0x1800797b4  mov     [rsp+148h+var_EC], edi
0x1800797b8  mov     [rsp+148h+var_E8], edi
0x1800797bc  mov     [rsp+148h+var_EC], edi
0x1800797c0  call    cs:__imp_HeapAlloc
0x1800797c6  mov     r14, rax
0x1800797c9  test    rax, rax
0x1800797cc  jz      loc_18007A0EA
0x1800797d2  mov     qword ptr [rax], 1
0x1800797d9  xorps   xmm0, xmm0
0x1800797dc  xor     eax, eax
0x1800797de  mov     ecx, 1
0x1800797e3  mov     [r14+2Ch], rax
0x1800797e7  mov     [r14+34h], eax
0x1800797eb  mov     [r14+28h], edi
0x1800797ef  mov     [r14+38h], rdi
0x1800797f3  mov     [r14+40h], rdi
0x1800797f7  mov     [r14+48h], rdi
0x1800797fb  mov     [r14+50h], rdi
0x1800797ff  mov     [r14+58h], rdi
0x180079803  movups  xmmword ptr [r14+8], xmm0
0x180079808  movups  xmmword ptr [r14+18h], xmm0
0x18007980d  lock inc dword ptr [rbx]
0x180079810  mov     rdi, [r14+48h]
0x180079814  test    rdi, rdi
0x180079817  jz      short loc_18007982A
0x180079819  mov     eax, 0FFFFFFFFh
0x18007981e  lock xadd [rdi], eax
0x180079822  cmp     eax, ecx
0x180079824  jz      loc_180079E0D
0x18007982a  mov     [r14+48h], rbx
0x18007982e  lea     rax, ?SendCompletion@CWxSocket@@CAKKPEAVCWxIoContext@@K@Z; CWxSocket::SendCompletion(ulong,CWxIoContext *,ulong)
0x180079835  mov     [r14+30h], rax
0x180079839  lea     rax, ?SendCompletion@CSocket@@CAXPEAXKK@Z; CSocket::SendCompletion(void *,ulong,ulong)
0x180079840  mov     [r14+38h], rax
0x180079844  mov     dword ptr [r14+28h], 2
0x18007984c  mov     [r14+40h], r15
0x180079850  xor     edi, edi
0x180079852  test    rsi, rsi
0x180079855  jz      short loc_180079867
0x180079857  mov     rcx, rsi; lpCriticalSection
0x18007985a  call    cs:__imp_EnterCriticalSection
0x180079860  mov     ecx, 1; this
0x180079865  mov     edi, ecx
0x180079867  add     dword ptr [rbx+0BCh], 1
0x18007986e  jz      short loc_180079886
0x180079870  cmp     dword ptr [rbx+0C4h], 0
0x180079877  jnz     short loc_180079886
0x180079879  cmp     dword ptr [rbx+0C0h], 0
0x180079880  jnz     loc_180079CE5
0x180079886  test    edi, edi
0x180079888  jz      short loc_180079898
0x18007988a  test    rsi, rsi
0x18007988d  jz      short loc_180079898
0x18007988f  mov     rcx, rsi; lpCriticalSection
0x180079892  call    cs:__imp_LeaveCriticalSection
0x180079898  xor     esi, esi
0x18007989a  mov     rcx, r12; SRWLock
0x18007989d  mov     [rsp+148h+NumberOfBytesSent], esi
0x1800798a4  mov     [rsp+148h+var_F0], esi
0x1800798a8  call    cs:__imp_AcquireSRWLockShared
0x1800798ae  cmp     qword ptr [rbx+10h], 0FFFFFFFFFFFFFFFFh
0x1800798b3  jz      loc_180079CA3
0x1800798b9  lock inc dword ptr [r14]
0x1800798bd  cmp     [rbx+134h], esi
0x1800798c3  mov     edi, 3E5h
0x1800798c8  mov     rcx, [rbx+18h]; pio
0x1800798cc  cmovnz  edi, esi
0x1800798cf  call    cs:__imp_StartThreadpoolIo
0x1800798d5  mov     rcx, [rbx+10h]; s
0x1800798d9  lea     rax, [r14+8]
0x1800798dd  mov     [rsp+148h+lpCompletionRoutine], rsi; lpCompletionRoutine
0x1800798e2  lea     r9, [rsp+148h+NumberOfBytesSent]; lpNumberOfBytesSent
0x1800798ea  mov     [rsp+148h+lpOverlapped], rax; lpOverlapped
0x1800798ef  lea     rdx, [rsp+148h+Buffers]; lpBuffers
0x1800798f4  mov     r8d, 1; dwBufferCount
0x1800798fa  mov     [rsp+148h+dwFlags], esi; dwFlags
0x1800798fe  call    cs:__imp_WSASend
0x180079904  cmp     eax, 0FFFFFFFFh
0x180079907  jz      loc_18007A0BE
0x18007990d  cmp     edi, 3E5h
0x180079913  jz      short loc_18007991F
0x180079915  mov     rcx, [rbx+18h]; pio
0x180079919  call    cs:__imp_CancelThreadpoolIo
0x18007991f  mov     rcx, r14; this
0x180079922  call    ?Release@CWxIoContext@@QEAAKXZ; CWxIoContext::Release(void)
0x180079927  test    edi, edi
0x180079929  jnz     short loc_180079932
0x18007992b  mov     esi, [rsp+148h+NumberOfBytesSent]
  ... truncated ...
```
