# MonitorReader

- ea: `0x180001950`
- end: `0x1800022aa`
- name: `MonitorReader`
- size: `2394`
- prototype: `ULONG __stdcall(PVOID Parameter)`
- caller_count: `0`
- callee_count: `28`
- tags: ``

## callees

- `0x1800016c0`
- `0x180001900`
- `0x180001950`
- `0x1800022b0`
- `0x18000366c`
- `0x18000371c`
- `0x1800037b8`
- `0x180003ff0`
- `0x1800044e0`
- `0x18000457c`
- `0x180006700`
- `0x1800067a0`
- `0x18000c870`
- `0x18000cd80`
- `0x18000d7a0`
- `0x18000f1c0`
- `0x18000f770`
- `0x18000f800`
- `0x180014180`
- `0x18001cb74`
- `0x180029b78`
- `0x180029dd4`
- `0x180029e44`
- `0x18002a72c`
- `0x18002ab4c`
- `0x18002e770`
- `0x18003261b`
- `0x180037010`

## import_xrefs

- `SCardBi!?Instance@SmartCardBiManager@@SAPEAV1@XZ` at `0x180001a87`
- `SCardBi!?Instance@SmartCardBiManager@@SAPEAV1@XZ` at `0x180001a87`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180001a17`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180001a17`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180001a06`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180001a3a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180001b29`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180001c20`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180001d1b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180001d63`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180001eb3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180001f94`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180001fdc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000222e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180001a06`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180001a3a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180001b29`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180001c20`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180001d1b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180001d63`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180001eb3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180001f94`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180001fdc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000222e`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadPriority` at `0x1800019fc`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadPriority` at `0x1800019fc`
- `api-ms-win-core-io-l1-1-0!CancelIoEx` at `0x180001c05`
- `api-ms-win-core-io-l1-1-0!CancelIoEx` at `0x180001d48`
- `api-ms-win-core-io-l1-1-0!CancelIoEx` at `0x180001fc1`
- `api-ms-win-core-io-l1-1-0!CancelIoEx` at `0x180001c05`
- `api-ms-win-core-io-l1-1-0!CancelIoEx` at `0x180001d48`
- `api-ms-win-core-io-l1-1-0!CancelIoEx` at `0x180001fc1`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x180001b1b`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x180001ea5`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x180001b1b`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x180001ea5`
- `api-ms-win-core-io-l1-1-0!GetOverlappedResult` at `0x180001d11`
- `api-ms-win-core-io-l1-1-0!GetOverlappedResult` at `0x180001f8a`
- `api-ms-win-core-io-l1-1-0!GetOverlappedResult` at `0x180001d11`
- `api-ms-win-core-io-l1-1-0!GetOverlappedResult` at `0x180001f8a`

## pseudocode

```c
// Hidden C++ exception states: #wind=6 #try_helpers=1
__int64 __fastcall MonitorReader(HANDLE *Parameter)
{
  int v2; // r12d
  HANDLE *v3; // r13
  unsigned int v4; // eax
  char *EventW; // r14
  DWORD LastError; // ebx
  const WCHAR *v7; // rbx
  int v8; // r12d
  HANDLE *v9; // r14
  DWORD v10; // ebx
  int v11; // r14d
  unsigned int v12; // eax
  unsigned int v13; // eax
  unsigned int v14; // eax
  const unsigned __int16 *v15; // rbx
  DWORD v16; // eax
  int *v17; // r12
  int v18; // ebx
  const unsigned __int16 *v19; // rbx
  DWORD v20; // eax
  const unsigned __int8 *v21; // rcx
  int v22; // r12d
  DWORD v23; // ebx
  int v24; // r14d
  unsigned int v25; // eax
  unsigned int v26; // eax
  const unsigned __int16 *v27; // rbx
  DWORD v28; // eax
  bool v29; // zf
  const unsigned __int8 *v30; // rcx
  const unsigned __int8 *v31; // rcx
  const unsigned __int16 *v32; // r9
  __int64 v33; // rdx
  const unsigned __int8 *v34; // r8
  const unsigned __int8 *v35; // r9
  HANDLE *v37; // rbx
  const unsigned __int16 *v38; // r9
  HANDLE *v39; // rbx
  unsigned __int16 *v40; // r8
  HANDLE *v41; // [rsp+40h] [rbp-108h] BYREF
  HANDLE *v42; // [rsp+48h] [rbp-100h]
  int v43; // [rsp+50h] [rbp-F8h]
  char *v44; // [rsp+60h] [rbp-E8h] BYREF
  DWORD v45; // [rsp+68h] [rbp-E0h]
  ulong pExceptionObject; // [rsp+70h] [rbp-D8h] BYREF
  ulong v47; // [rsp+74h] [rbp-D4h] BYREF
  ulong v48; // [rsp+78h] [rbp-D0h] BYREF
  ulong v49; // [rsp+7Ch] [rbp-CCh] BYREF
  ulong v50; // [rsp+80h] [rbp-C8h] BYREF
  ulong v51; // [rsp+84h] [rbp-C4h] BYREF
  struct _OVERLAPPED Overlapped; // [rsp+88h] [rbp-C0h] BYREF
  struct CAccessLock *v53; // [rsp+A8h] [rbp-A0h]
  int *v54; // [rsp+B0h] [rbp-98h]
  int v55; // [rsp+B8h] [rbp-90h] BYREF
  char v56[8]; // [rsp+C0h] [rbp-88h] BYREF
  char v57[8]; // [rsp+C8h] [rbp-80h] BYREF
  struct CAccessLock *v58; // [rsp+D0h] [rbp-78h]
  char v59[8]; // [rsp+D8h] [rbp-70h] BYREF
  CReader *v60[13]; // [rsp+E0h] [rbp-68h] BYREF
  int v61; // [rsp+150h] [rbp+8h] BYREF
  int v62; // [rsp+158h] [rbp+10h]
  DWORD BytesReturned; // [rsp+160h] [rbp+18h] BYREF
  int v64; // [rsp+168h] [rbp+20h]

  set_terminate(CalaisTerminate);
  v2 = 0;
  v61 = 0;
  v43 = 0;
  v62 = 0;
  BytesReturned = 0;
  v64 = 3;
  v42 = Parameter;
  v3 = Parameter;
  memset(&Overlapped, 0, sizeof(Overlapped));
  v44 = 0;
  v45 = 0;
  v4 = CalRpcSetCallerId((void *)_InterlockedIncrement(&dword_18004BF90));
  try
  {
    if ( v4 )
    {
      pExceptionObject = v4;
      throw &pExceptionObject;
    }
    if ( !SetThreadPriority(Parameter[95], 1) )
      GetLastError();
    EventW = (char *)CreateEventW(0, 1, 0, 0);
    Overlapped.hEvent = EventW;
    if ( (unsigned __int64)(EventW - 1) > 0xFFFFFFFFFFFFFFFDuLL )
    {
      LastError = GetLastError();
      v45 = LastError;
    }
    else
    {
      LastError = 0;
      v45 = 0;
    }
    v44 = EventW;
    if ( (unsigned __int64)(EventW - 1) > 0xFFFFFFFFFFFFFFFDuLL )
    {
      CalaisError((const unsigned __int8 *)EventW - 1, 0x261u, LastError, 0, 0, 0);
      v51 = LastError;
      throw &v51;
    }
    v58 = (struct CAccessLock *)(Parameter + 7);
    CLockWrite::CLockWrite((CLockWrite *)&v41, (struct CAccessLock *)(Parameter + 7));
    v54 = (int *)(Parameter + 24);
    if ( *((_DWORD *)Parameter + 48) != 1 )
    {
      SmartCardBiManager::Instance();
      *((_DWORD *)Parameter + 48) = 1;
      Parameter[27] = 0;
      *((_DWORD *)Parameter + 56) = 0;
      CMultiEvent::Signal((CMultiEvent *)(Parameter + 52));
    }
    v53 = (struct CAccessLock *)(Parameter + 7);
    CLockWrite::~CLockWrite((CLockWrite *)&v41);
    CMultiEvent::Signal(g_phReaderChangeEvent);
LABEL_13:
    while ( 1 )
    {
      v7 = &Data;
      if ( v2 )
        break;
      v8 = 3;
      while ( 1 )
      {
        v9 = Parameter + 104;
        v41 = Parameter + 104;
        if ( DeviceIoControl(Parameter[104], 0x310028u, 0, 0, 0, 0, &BytesReturned, &Overlapped) )
          break;
        v10 = GetLastError();
        while ( 1 )
        {
          v11 = 0;
          v62 = 0;
          switch ( v10 )
          {
            case 0u:
              goto LABEL_52;
            case 1u:
              goto LABEL_46;
            case 6u:
              goto LABEL_47;
            case 0x37u:
              goto LABEL_46;
            case 0x3E3u:
              goto LABEL_47;
          }
          if ( v10 != 997 )
            break;
          v12 = WaitForAnyObject(0xFFFFFFFF, g_hCalaisShutdown, Parameter[113], Overlapped.hEvent, Parameter[93], 0) - 1;
          if ( !v12 || (v13 = v12 - 1) == 0 )
          {
            if ( !CancelIoEx(*v41, &Overlapped) )
            {
              v19 = &Data;
              if ( *((_DWORD *)v3 + 7) )
                v19 = (const unsigned __int16 *)v3[2];
              v20 = GetLastError();
              CalaisWarningAlwaysEvent(
                (const unsigned __int8 *)L"IOCTL_SMARTCARD_IS_PRESENT",
                0x26Cu,
                v20,
                v19,
                L"IOCTL_SMARTCARD_IS_PRESENT",
                L"XX XX XX XX");
            }
            WaitForAnObject(Overlapped.hEvent, 0xFFFFFFFF);
            v2 = 1;
            v61 = 1;
            goto LABEL_13;
          }
          v14 = v13 - 1;
          if ( v14 )
          {
            if ( v14 != 1 )
            {
              v47 = -2146435071;
              throw &v47;
            }
            v9 = v41;
            if ( !CancelIoEx(*v41, &Overlapped) )
            {
              v15 = &Data;
              if ( *((_DWORD *)v3 + 7) )
                v15 = (const unsigned __int16 *)v3[2];
              v16 = GetLastError();
              CalaisWarningAlwaysEvent(
                (const unsigned __int8 *)L"IOCTL_SMARTCARD_IS_PRESENT",
                0x26Cu,
                v16,
                v15,
                L"IOCTL_SMARTCARD_IS_PRESENT",
                L"XX XX XX XX");
            }
            WaitForAnObject(Overlapped.hEvent, 0xFFFFFFFF);
            v61 = 0;
            WaitForAnObject(Parameter[94], 0xFFFFFFFF);
            goto LABEL_35;
          }
          CReader::LatchReader((CReader *)Parameter, 0, 0);
          if ( GetOverlappedResult(*v41, &Overlapped, &BytesReturned, 1) )
            v10 = 0;
          else
            v10 = GetLastError();
          CMutex::Share((CMutex *)(Parameter + 41));
        }
        if ( v10 == 1617 )
        {
LABEL_46:
          v43 = 1;
LABEL_47:
          v61 = 1;
          (*((void (__fastcall **)(HANDLE *))*Parameter + 5))(Parameter);
          v10 = 0;
        }
        else
        {
          v11 = 1;
          v62 = 1;
        }
        if ( !v10 )
        {
LABEL_52:
          v9 = v41;
          break;
        }
        if ( v11 )
        {
          if ( !--v8 )
          {
            CReader::SetAvailabilityStatusLocked(Parameter, 10);
            CalaisError(v21, 0x264u, v10, 0, 0, 0);
            v48 = v10;
            throw &v48;
          }
        }
      }
      v2 = v61;
      if ( !v61 )
      {
LABEL_35:
        CLockWrite::CLockWrite((CLockWrite *)v56, v53);
        ++*((_DWORD *)Parameter + 49);
        *((_DWORD *)v3 + 51) = 0;
        v17 = v54;
        v18 = *v54;
        CLockWrite::~CLockWrite((CLockWrite *)v56);
        if ( v18 >= 8 )
        {
          if ( *v17 < 2 )
            CReader::SetAvailabilityStatus(Parameter, 2);
        }
        else
        {
          try
          {
            CLatchReader::CLatchReader((CLatchReader *)v60, (struct CReader *)Parameter, 0);
            CReader::PowerUp((CReader *)Parameter);
            CLatchReader::~CLatchReader(v60);
          }
          catch ( ... )
          {
            Parameter = v42;
            v3 = v42;
            v9 = v41;
          }
        }
        CReader::PowerDownTimeoutStart((CReader *)Parameter);
        v22 = 3;
LABEL_58:
        if ( !DeviceIoControl(*v9, 0x31002Cu, 0, 0, 0, 0, &BytesReturned, &Overlapped) )
        {
          v23 = GetLastError();
          while ( 1 )
          {
            v24 = 0;
            v62 = 0;
            if ( !v23 )
              break;
            switch ( v23 )
            {
              case 1u:
                goto LABEL_81;
              case 6u:
                goto LABEL_82;
              case 0x37u:
                goto LABEL_81;
              case 0x3E3u:
                goto LABEL_82;
            }
            if ( v23 != 997 )
            {
              if ( v23 == 1617 )
              {
LABEL_81:
                v43 = 1;
LABEL_82:
                v23 = 0;
                v61 = 1;
                (*((void (__fastcall **)(HANDLE *))*Parameter + 5))(Parameter);
              }
              else
              {
                v24 = 1;
                v62 = 1;
              }
              if ( !v23 )
                break;
              v29 = v24 == 0;
              v9 = v41;
              if ( !v29 && !--v22 )
              {
                CReader::SetAvailabilityStatusLocked(Parameter, 10);
                CalaisError(v30, 0x267u, v23, 0, 0, 0);
                v50 = v23;
                throw &v50;
              }
              goto LABEL_58;
            }
            v25 = WaitForAnyObject(0xFFFFFFFF, g_hCalaisShutdown, Parameter[113], Overlapped.hEvent, 0) - 1;
            if ( !v25 || (v26 = v25 - 1) == 0 )
            {
              if ( !CancelIoEx(*v41, &Overlapped) )
              {
                v27 = &Data;
                if ( *((_DWORD *)v3 + 7) )
                  v27 = (const unsigned __int16 *)v3[2];
                v28 = GetLastError();
                CalaisWarningAlwaysEvent(
                  (const unsigned __int8 *)L"IOCTL_SMARTCARD_IS_PRESENT",
                  0x26Cu,
                  v28,
                  v27,
                  L"IOCTL_SMARTCARD_IS_PRESENT",
                  L"XX XX XX XX");
              }
              WaitForAnObject(Overlapped.hEvent, 0xFFFFFFFF);
              v2 = 1;
              v61 = 1;
              goto LABEL_88;
            }
            if ( v26 != 1 )
            {
              v49 = -2146435071;
              throw &v49;
            }
            CReader::LatchReader((CReader *)Parameter, 0, 0);
            if ( GetOverlappedResult(*v41, &Overlapped, &BytesReturned, 1) )
              v23 = 0;
            else
              v23 = GetLastError();
            CMutex::Share((CMutex *)(Parameter + 41));
          }
        }
        v2 = v61;
LABEL_88:
        CReader::PowerDownTimeoutStop((CReader *)Parameter);
        if ( !v2 )
        {
          CLockWrite::CLockWrite((CLockWrite *)v57, v53);
          *((_DWORD *)v3 + 46) = 0;
          *((_DWORD *)Parameter + 57) = 0;
          ++*((_DWORD *)v3 + 50);
          CLockWrite::~CLockWrite((CLockWrite *)v57);
          if ( (int)CReader::AvailabilityStatus((__int64)Parameter) < 8 )
          {
            v41 = Parameter;
            CReader::TakeoverReader((CReader *)Parameter);
            CReader::GetReaderState((CReader *)Parameter);
            CReader::SetAvailabilityStatusLocked(Parameter, 1);
            CTakeReader::~CTakeReader((CReader **)&v41);
          }
          v64 = 3;
        }
      }
    }
    CLockWrite::CLockWrite((CLockWrite *)v59, v58);
    if ( *v54 < 9 )
      CReader::SetAvailabilityStatus(Parameter, 11);
    CLockWrite::~CLockWrite((CLockWrite *)v59);
  }
  catch ( ulong v55 )
  {
    v37 = v42;
    v38 = &Data;
    if ( *((_DWORD *)v42 + 7) )
      v38 = (const unsigned __int16 *)v42[2];
    CalaisError(v31, 0x268u, v55, v38, 0, 0);
    CReader::SetAvailabilityStatusLocked(v37, 10);
    Parameter = v42;
    v3 = v42;
    v7 = &Data;
  }
  catch ( ... )
  {
    v39 = v42;
    v40 = (unsigned __int16 *)&Data;
    if ( *((_DWORD *)v42 + 7) )
      v40 = (unsigned __int16 *)v42[2];
    CalaisError(v31, 0x269u, v40, v32);
    CReader::SetAvailabilityStatusLocked(v39, 10);
    Parameter = v42;
    v3 = v42;
    v7 = &Data;
  }
  if ( (unsigned __int64)(v44 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
    CHandleObject::Close((void **)&v44);
  if ( v43 )
  {
    CLockWrite::CLockWrite((CLockWrite *)&v61, (struct CAccessLock *)(Parameter + 7));
    *((_DWORD *)v3 + 46) = 0;
    *((_DWORD *)Parameter + 57) = 0;
    ++*((_DWORD *)v3 + 50);
    *((_DWORD *)Parameter + 192) = GetLastError();
    if ( CHandleObject::IsValid((CHandleObject *)(Parameter + 95)) )
      CHandleObject::Close(Parameter + 95);
    Parameter[95] = 0;
    CLockWrite::~CLockWrite((CLockWrite *)&v61);
    if ( *((_DWORD *)v3 + 7) )
      v7 = (const WCHAR *)v3[2];
    CalaisRemoveReader(v7, v33, v34, v35);
  }
  if ( (unsigned __int64)(v44 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
    CHandleObject::Close((void **)&v44);
  return 0;
}

```

## disassembly

```asm
0x180001950  push    rbx
0x180001952  push    rsi
0x180001953  push    rdi
0x180001954  push    r12
0x180001956  push    r13
0x180001958  push    r14
0x18000195a  push    r15
0x18000195c  sub     rsp, 110h
0x180001963  mov     rsi, rcx
0x180001966  lea     rcx, ?CalaisTerminate@@YAXXZ; void (*)(void)
0x18000196d  call    ?set_terminate@@YAP6AXXZP6AXXZ@Z_0; set_terminate(void (*)(void))
0x180001972  xor     edi, edi
0x180001974  mov     r12d, edi
0x180001977  mov     [rsp+148h+arg_0], edi
0x18000197e  mov     [rsp+148h+var_F8], edi
0x180001982  mov     [rsp+148h+arg_8], edi
0x180001989  mov     [rsp+148h+BytesReturned], edi
0x180001990  mov     [rsp+148h+arg_18], 3
0x18000199b  mov     [rsp+148h+var_100], rsi
0x1800019a0  mov     r13, rsi
0x1800019a3  xorps   xmm0, xmm0
0x1800019a6  movups  xmmword ptr [rsp+148h+Overlapped.Internal], xmm0
0x1800019ae  movups  xmmword ptr [rsp+148h+Overlapped.10h], xmm0
0x1800019b6  mov     [rsp+148h+var_E8], rdi
0x1800019bb  mov     [rsp+148h+var_E0], edi
0x1800019bf  lea     r15d, [rdi+1]
0x1800019c3  mov     eax, r15d
0x1800019c6  lock xadd cs:dword_18004BF90, eax
0x1800019ce  add     eax, r15d
0x1800019d1  movsxd  rcx, eax; lpTlsValue
0x1800019d4  call    ?CalRpcSetCallerId@@YAKPEAX@Z; CalRpcSetCallerId(void *)
0x1800019d9  test    eax, eax
0x1800019db  jz      short loc_1800019F2
0x1800019dd  mov     [rsp+148h+pExceptionObject], eax
0x1800019e1  lea     rdx, _TI1K; pThrowInfo
0x1800019e8  lea     rcx, [rsp+148h+pExceptionObject]; pExceptionObject
0x1800019ed  call    _CxxThrowException_0
0x1800019f2  mov     edx, r15d; nPriority
0x1800019f5  mov     rcx, [rsi+2F8h]; hThread
0x1800019fc  call    cs:__imp_SetThreadPriority
0x180001a02  test    eax, eax
0x180001a04  jnz     short loc_180001A0C
0x180001a06  call    cs:__imp_GetLastError
0x180001a0c  xor     r9d, r9d; lpName
0x180001a0f  xor     r8d, r8d; bInitialState
0x180001a12  mov     edx, r15d; bManualReset
0x180001a15  xor     ecx, ecx; lpEventAttributes
0x180001a17  call    cs:__imp_CreateEventW
0x180001a1d  mov     r14, rax
0x180001a20  mov     [rsp+148h+Overlapped.hEvent], rax
0x180001a28  lea     rcx, [rax-1]
0x180001a2c  cmp     rcx, 0FFFFFFFFFFFFFFFDh
0x180001a30  ja      short loc_180001A3A
0x180001a32  mov     ebx, edi
0x180001a34  mov     [rsp+148h+var_E0], ebx
0x180001a38  jmp     short loc_180001A46
0x180001a3a  call    cs:__imp_GetLastError
0x180001a40  mov     ebx, eax
0x180001a42  mov     [rsp+148h+var_E0], eax
0x180001a46  mov     [rsp+148h+var_E8], r14
0x180001a4b  lea     rcx, [r14-1]; unsigned __int8 *
0x180001a4f  cmp     rcx, 0FFFFFFFFFFFFFFFDh
0x180001a53  ja      loc_18000219C
0x180001a59  lea     rbx, [rsi+38h]
0x180001a5d  mov     [rsp+148h+var_78], rbx
0x180001a65  mov     rdx, rbx; struct CAccessLock *
0x180001a68  lea     rcx, [rsp+148h+var_108]; this
0x180001a6d  call    ??0CLockWrite@@QEAA@PEAVCAccessLock@@@Z; CLockWrite::CLockWrite(CAccessLock *)
0x180001a72  nop
0x180001a73  lea     r14, [rsi+0C0h]
0x180001a7a  mov     [rsp+148h+var_98], r14
0x180001a82  cmp     [r14], r15d
0x180001a85  jz      short loc_180001AAA
0x180001a87  call    cs:__imp_?Instance@SmartCardBiManager@@SAPEAV1@XZ; SmartCardBiManager::Instance(void)
0x180001a8d  mov     [r14], r15d
0x180001a90  mov     [rsi+0D8h], rdi
0x180001a97  mov     [rsi+0E0h], edi
0x180001a9d  lea     rcx, [rsi+1A0h]; this
0x180001aa4  call    ?Signal@CMultiEvent@@QEAAXXZ; CMultiEvent::Signal(void)
0x180001aa9  nop
0x180001aaa  mov     [rsp+148h+var_A0], rbx
0x180001ab2  lea     rcx, [rsp+148h+var_108]; this
0x180001ab7  call    ??1CLockWrite@@QEAA@XZ; CLockWrite::~CLockWrite(void)
0x180001abc  mov     rcx, cs:?g_phReaderChangeEvent@@3PEAVCMultiEvent@@EA; this
0x180001ac3  call    ?Signal@CMultiEvent@@QEAAXXZ; CMultiEvent::Signal(void)
0x180001ac8  lea     rbx, Data
0x180001acf  test    r12d, r12d
0x180001ad2  jnz     loc_180002159
0x180001ad8  mov     r12d, 3
0x180001ade  lea     r14, [rsi+340h]
0x180001ae5  mov     [rsp+148h+var_108], r14
0x180001aea  lea     rax, [rsp+148h+Overlapped]
0x180001af2  mov     [rsp+148h+lpOverlapped], rax; lpOverlapped
0x180001af7  lea     rax, [rsp+148h+BytesReturned]
0x180001aff  mov     [rsp+148h+lpBytesReturned], rax; lpBytesReturned
0x180001b04  mov     [rsp+148h+nOutBufferSize], edi; nOutBufferSize
0x180001b08  mov     [rsp+148h+lpOutBuffer], rdi; lpOutBuffer
0x180001b0d  xor     r9d, r9d; nInBufferSize
0x180001b10  xor     r8d, r8d; lpInBuffer
0x180001b13  mov     edx, 310028h; dwIoControlCode
0x180001b18  mov     rcx, [r14]; hDevice
0x180001b1b  call    cs:__imp_DeviceIoControl
0x180001b21  test    eax, eax
0x180001b23  jnz     loc_180001E27
0x180001b29  call    cs:__imp_GetLastError
0x180001b2f  mov     ebx, eax
0x180001b31  mov     r14d, edi
0x180001b34  mov     [rsp+148h+arg_8], edi
0x180001b3b  mov     ecx, ebx
0x180001b3d  test    ebx, ebx
0x180001b3f  jz      loc_180001E22
0x180001b45  sub     ecx, 1
0x180001b48  jz      loc_180001DB1
0x180001b4e  sub     ecx, 5
0x180001b51  jz      loc_180001DB6
0x180001b57  sub     ecx, 31h ; '1'
0x180001b5a  jz      loc_180001DB1
0x180001b60  sub     ecx, 3ACh
0x180001b66  jz      loc_180001DB6
0x180001b6c  sub     ecx, 2
0x180001b6f  jz      short loc_180001B8D
0x180001b71  cmp     ecx, 26Ch
0x180001b77  jz      loc_180001DB1
0x180001b7d  mov     r14d, r15d
0x180001b80  mov     [rsp+148h+arg_8], r15d
0x180001b88  jmp     loc_180001DCF
0x180001b8d  mov     qword ptr [rsp+148h+nOutBufferSize], rdi
0x180001b92  mov     rax, [rsi+2E8h]
0x180001b99  mov     [rsp+148h+lpOutBuffer], rax
0x180001b9e  mov     r9, [rsp+148h+Overlapped.hEvent]
0x180001ba6  mov     r8, [rsi+388h]
0x180001bad  mov     rdx, cs:?g_hCalaisShutdown@@3PEAXEA; void * g_hCalaisShutdown
0x180001bb4  or      ecx, 0FFFFFFFFh; dwMilliseconds
0x180001bb7  call    ?WaitForAnyObject@@YAKKZZ; WaitForAnyObject(ulong,...)
0x180001bbc  sub     eax, 1
0x180001bbf  jz      loc_180001D38
0x180001bc5  sub     eax, 1
0x180001bc8  jz      loc_180001D38
0x180001bce  sub     eax, 1
0x180001bd1  jz      loc_180001CE9
0x180001bd7  cmp     eax, 1
0x180001bda  jz      short loc_180001BF5
0x180001bdc  mov     [rsp+148h+var_D4], 80100001h
0x180001be4  lea     rdx, _TI1K; pThrowInfo
0x180001beb  lea     rcx, [rsp+148h+var_D4]; pExceptionObject
0x180001bf0  call    _CxxThrowException_0
0x180001bf5  lea     rdx, [rsp+148h+Overlapped]; lpOverlapped
0x180001bfd  mov     r14, [rsp+148h+var_108]
0x180001c02  mov     rcx, [r14]; hFile
0x180001c05  call    cs:__imp_CancelIoEx
0x180001c0b  test    eax, eax
0x180001c0d  jnz     short loc_180001C4E
0x180001c0f  cmp     [r13+1Ch], edi
0x180001c13  lea     rbx, Data
0x180001c1a  jbe     short loc_180001C20
0x180001c1c  mov     rbx, [r13+10h]
0x180001c20  call    cs:__imp_GetLastError
0x180001c26  lea     rcx, aXxXxXxXx; "XX XX XX XX"
0x180001c2d  mov     qword ptr [rsp+148h+nOutBufferSize], rcx; unsigned __int16 *
0x180001c32  lea     rcx, aIoctlSmartcard; "IOCTL_SMARTCARD_IS_PRESENT"
0x180001c39  mov     [rsp+148h+lpOutBuffer], rcx; unsigned __int16 *
0x180001c3e  mov     r9, rbx; unsigned __int16 *
0x180001c41  mov     r8d, eax; unsigned int
0x180001c44  mov     edx, 26Ch; unsigned int
0x180001c49  call    ?CalaisWarningAlwaysEvent@@YAXPEBEKKPEBG11@Z; CalaisWarningAlwaysEvent(uchar const *,ulong,ulong,ushort const *,ushort const *,ushort const *)
0x180001c4e  or      edx, 0FFFFFFFFh; unsigned int
0x180001c51  mov     rcx, [rsp+148h+Overlapped.hEvent]; void *
0x180001c59  call    ?WaitForAnObject@@YAKPEAXK@Z; WaitForAnObject(void *,ulong)
0x180001c5e  mov     [rsp+148h+arg_0], edi
0x180001c65  or      edx, 0FFFFFFFFh; unsigned int
0x180001c68  mov     rcx, [rsi+2F0h]; void *
0x180001c6f  call    ?WaitForAnObject@@YAKPEAXK@Z; WaitForAnObject(void *,ulong)
0x180001c74  mov     rdx, [rsp+148h+var_A0]; struct CAccessLock *
0x180001c7c  lea     rcx, [rsp+148h+var_88]; this
0x180001c84  call    ??0CLockWrite@@QEAA@PEAVCAccessLock@@@Z; CLockWrite::CLockWrite(CAccessLock *)
0x180001c89  add     [rsi+0C4h], r15d
0x180001c90  mov     [r13+0CCh], edi
0x180001c97  mov     r12, [rsp+148h+var_98]
0x180001c9f  mov     ebx, [r12]
0x180001ca3  lea     rcx, [rsp+148h+var_88]; this
0x180001cab  call    ??1CLockWrite@@QEAA@XZ; CLockWrite::~CLockWrite(void)
0x180001cb0  cmp     ebx, 8
0x180001cb3  jge     loc_180001E52
0x180001cb9  xor     r8d, r8d; struct CReader::ActiveState *
0x180001cbc  mov     rdx, rsi; struct CReader *
0x180001cbf  lea     rcx, [rsp+148h+var_68]; this
0x180001cc7  call    ??0CLatchReader@@QEAA@PEAVCReader@@PEBUActiveState@1@@Z; CLatchReader::CLatchReader(CReader *,CReader::ActiveState const *)
0x180001ccc  nop
0x180001ccd  mov     rcx, rsi; this
0x180001cd0  call    ?PowerUp@CReader@@IEAAXXZ; CReader::PowerUp(void)
0x180001cd5  nop
0x180001cd6  lea     rcx, [rsp+148h+var_68]; this
0x180001cde  call    ??1CLatchReader@@QEAA@XZ; CLatchReader::~CLatchReader(void)
0x180001ce3  nop
0x180001ce4  jmp     loc_180001E66
0x180001ce9  xor     r8d, r8d; bool *
0x180001cec  xor     edx, edx; struct CReader::ActiveState *
0x180001cee  mov     rcx, rsi; this
0x180001cf1  call    ?LatchReader@CReader@@QEAAXPEBUActiveState@1@PEA_N@Z; CReader::LatchReader(CReader::ActiveState const *,bool *)
0x180001cf6  mov     r9d, r15d; bWait
0x180001cf9  lea     r8, [rsp+148h+BytesReturned]; lpNumberOfBytesTransferred
0x180001d01  lea     rdx, [rsp+148h+Overlapped]; lpOverlapped
0x180001d09  mov     rax, [rsp+148h+var_108]
0x180001d0e  mov     rcx, [rax]; hFile
0x180001d11  call    cs:__imp_GetOverlappedResult
0x180001d17  test    eax, eax
0x180001d19  jnz     short loc_180001D25
0x180001d1b  call    cs:__imp_GetLastError
0x180001d21  mov     ebx, eax
0x180001d23  jmp     short loc_180001D27
0x180001d25  mov     ebx, edi
0x180001d27  lea     rcx, [rsi+148h]; this
0x180001d2e  call    ?Share@CMutex@@QEAAHXZ; CMutex::Share(void)
0x180001d33  jmp     loc_180001B31
0x180001d38  lea     rdx, [rsp+148h+Overlapped]; lpOverlapped
0x180001d40  mov     rax, [rsp+148h+var_108]
0x180001d45  mov     rcx, [rax]; hFile
0x180001d48  call    cs:__imp_CancelIoEx
0x180001d4e  test    eax, eax
0x180001d50  jnz     short loc_180001D91
0x180001d52  cmp     [r13+1Ch], edi
0x180001d56  lea     rbx, Data
0x180001d5d  jbe     short loc_180001D63
0x180001d5f  mov     rbx, [r13+10h]
0x180001d63  call    cs:__imp_GetLastError
0x180001d69  lea     rcx, aXxXxXxXx; "XX XX XX XX"
0x180001d70  mov     qword ptr [rsp+148h+nOutBufferSize], rcx; unsigned __int16 *
0x180001d75  lea     rcx, aIoctlSmartcard; "IOCTL_SMARTCARD_IS_PRESENT"
0x180001d7c  mov     [rsp+148h+lpOutBuffer], rcx; unsigned __int16 *
0x180001d81  mov     r9, rbx; unsigned __int16 *
0x180001d84  mov     r8d, eax; unsigned int
0x180001d87  mov     edx, 26Ch; unsigned int
0x180001d8c  call    ?CalaisWarningAlwaysEvent@@YAXPEBEKKPEBG11@Z; CalaisWarningAlwaysEvent(uchar const *,ulong,ulong,ushort const *,ushort const *,ushort const *)
0x180001d91  or      edx, 0FFFFFFFFh; unsigned int
0x180001d94  mov     rcx, [rsp+148h+Overlapped.hEvent]; void *
0x180001d9c  call    ?WaitForAnObject@@YAKPEAXK@Z; WaitForAnObject(void *,ulong)
0x180001da1  mov     r12d, r15d
0x180001da4  mov     [rsp+148h+arg_0], r15d
0x180001dac  jmp     loc_180001E38
0x180001db1  mov     [rsp+148h+var_F8], r15d
0x180001db6  mov     [rsp+148h+arg_0], r15d
0x180001dbe  mov     rax, [rsi]
0x180001dc1  mov     rcx, rsi
0x180001dc4  mov     rax, [rax+28h]
0x180001dc8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001dcd  mov     ebx, edi
0x180001dcf  test    ebx, ebx
0x180001dd1  jz      short loc_180001E22
0x180001dd3  test    r14d, r14d
0x180001dd6  jz      loc_180001ADE
0x180001ddc  sub     r12d, 1
0x180001de0  jnz     loc_180001ADE
0x180001de6  lea     edx, [r12+0Ah]
0x180001deb  mov     rcx, rsi
0x180001dee  call    ?SetAvailabilityStatusLocked@CReader@@IEAAXW4AvailableState@1@@Z; CReader::SetAvailabilityStatusLocked(CReader::AvailableState)
0x180001df3  mov     qword ptr [rsp+148h+nOutBufferSize], rdi; unsigned __int16 *
0x180001df8  mov     [rsp+148h+lpOutBuffer], rdi; unsigned __int16 *
0x180001dfd  xor     r9d, r9d; unsigned __int16 *
0x180001e00  mov     r8d, ebx; unsigned int
0x180001e03  mov     edx, 264h; unsigned int
0x180001e08  call    ?CalaisError@@YAXPEBEKKPEBG11@Z; CalaisError(uchar const *,ulong,ulong,ushort const *,ushort const *,ushort const *)
0x180001e0d  mov     [rsp+148h+var_D0], ebx
0x180001e11  lea     rdx, _TI1K; pThrowInfo
0x180001e18  lea     rcx, [rsp+148h+var_D0]; pExceptionObject
0x180001e1d  call    _CxxThrowException_0
0x180001e22  mov     r14, [rsp+148h+var_108]
0x180001e27  mov     r12d, [rsp+148h+arg_0]
0x180001e2f  test    r12d, r12d
0x180001e32  jz      loc_180001C74
0x180001e38  jmp     loc_180001AC8
0x180001e3d  xor     edi, edi
0x180001e3f  lea     r15d, [rdi+1]
0x180001e43  mov     rsi, [rsp+148h+var_100]
0x180001e48  mov     r13, rsi
0x180001e4b  mov     r14, [rsp+148h+var_108]
0x180001e50  jmp     short loc_180001E66
0x180001e52  cmp     dword ptr [r12], 2
0x180001e57  jge     short loc_180001E66
0x180001e59  mov     edx, 2
0x180001e5e  mov     rcx, rsi
0x180001e61  call    ?SetAvailabilityStatus@CReader@@IEAAXW4AvailableState@1@@Z; CReader::SetAvailabilityStatus(CReader::AvailableState)
0x180001e66  mov     rcx, rsi; this
0x180001e69  call    ?PowerDownTimeoutStart@CReader@@IEAAXXZ; CReader::PowerDownTimeoutStart(void)
0x180001e6e  mov     r12d, 3
0x180001e74  lea     rax, [rsp+148h+Overlapped]
0x180001e7c  mov     [rsp+148h+lpOverlapped], rax; lpOverlapped
0x180001e81  lea     rax, [rsp+148h+BytesReturned]
0x180001e89  mov     [rsp+148h+lpBytesReturned], rax; lpBytesReturned
0x180001e8e  mov     [rsp+148h+nOutBufferSize], edi; nOutBufferSize
0x180001e92  mov     [rsp+148h+lpOutBuffer], rdi; lpOutBuffer
0x180001e97  xor     r9d, r9d; nInBufferSize
0x180001e9a  xor     r8d, r8d; lpInBuffer
0x180001e9d  mov     edx, 31002Ch; dwIoControlCode
0x180001ea2  mov     rcx, [r14]; hDevice
0x180001ea5  call    cs:__imp_DeviceIoControl
0x180001eab  test    eax, eax
0x180001ead  jnz     loc_1800020A6
0x180001eb3  call    cs:__imp_GetLastError
0x180001eb9  mov     ebx, eax
0x180001ebb  mov     r14d, edi
  ... truncated ...
```
