# Windows::Compat::Shared::UtcJson::Begin(ushort const *,bool,ushort const * const *,unsigned __int64)

- ea: `0x1801d8c88`
- end: `0x1801d94f7`
- name: `?Begin@UtcJson@Shared@Compat@Windows@@QEAAJPEBG_NPEBQEBG_K@Z`
- size: `2159`
- prototype: `__int64 __fastcall(Windows::Compat::Shared::UtcJson *__hidden this, LPCWSTR pszFile, bool, const unsigned __int16 *const *, unsigned __int64)`
- caller_count: `1`
- callee_count: `12`
- tags: `authz_impersonation, registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x18004c2cc`

## callees

- `0x180008570`
- `0x1800092dc`
- `0x18000a927`
- `0x180011d94`
- `0x180014ac8`
- `0x180014be8`
- `0x1800287d4`
- `0x18002a778`
- `0x1801d8c88`
- `0x1801d9c78`
- `0x1801db028`
- `0x18021f010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_wcscpy_s` at `0x1801d90f0`
- `api-ms-win-crt-private-l1-1-0!_o_wcscpy_s` at `0x1801d90f0`
- `ntdll!WinSqmIsOptedInEx` at `0x1801d8d82`
- `ntdll!WinSqmIsOptedInEx` at `0x1801d8d82`
- `KERNEL32!CreateThread` at `0x1801d9326`
- `KERNEL32!CreateThread` at `0x1801d9326`
- `KERNEL32!CreateEventW` at `0x1801d8eeb`
- `KERNEL32!CreateEventW` at `0x1801d8f57`
- `KERNEL32!CreateEventW` at `0x1801d8eeb`
- `KERNEL32!CreateEventW` at `0x1801d8f57`
- `KERNEL32!WideCharToMultiByte` at `0x1801d8eaa`
- `KERNEL32!WideCharToMultiByte` at `0x1801d8eaa`
- `KERNEL32!GetProcessHeap` at `0x1801d8e5c`
- `KERNEL32!GetProcessHeap` at `0x1801d9027`
- `KERNEL32!GetProcessHeap` at `0x1801d94ab`
- `KERNEL32!GetProcessHeap` at `0x1801d8e5c`
- `KERNEL32!GetProcessHeap` at `0x1801d9027`
- `KERNEL32!GetProcessHeap` at `0x1801d94ab`
- `KERNEL32!HeapAlloc` at `0x1801d8e6a`
- `KERNEL32!HeapAlloc` at `0x1801d903a`
- `KERNEL32!HeapAlloc` at `0x1801d8e6a`
- `KERNEL32!HeapAlloc` at `0x1801d903a`
- `KERNEL32!GetLastError` at `0x1801d8efa`
- `KERNEL32!GetLastError` at `0x1801d8f29`
- `KERNEL32!GetLastError` at `0x1801d8f66`
- `KERNEL32!GetLastError` at `0x1801d8f95`
- `KERNEL32!GetLastError` at `0x1801d920c`
- `KERNEL32!GetLastError` at `0x1801d923b`
- `KERNEL32!GetLastError` at `0x1801d9338`
- `KERNEL32!GetLastError` at `0x1801d9367`
- `KERNEL32!GetLastError` at `0x1801d93d8`
- `KERNEL32!GetLastError` at `0x1801d9403`
- `KERNEL32!GetLastError` at `0x1801d8efa`
- `KERNEL32!GetLastError` at `0x1801d8f29`
- `KERNEL32!GetLastError` at `0x1801d8f66`
- `KERNEL32!GetLastError` at `0x1801d8f95`
- `KERNEL32!GetLastError` at `0x1801d920c`
- `KERNEL32!GetLastError` at `0x1801d923b`
- `KERNEL32!GetLastError` at `0x1801d9338`
- `KERNEL32!GetLastError` at `0x1801d9367`
- `KERNEL32!GetLastError` at `0x1801d93d8`
- `KERNEL32!GetLastError` at `0x1801d9403`
- `KERNEL32!HeapFree` at `0x1801d94b9`
- `KERNEL32!HeapFree` at `0x1801d94b9`
- `ADVAPI32!CloseTrace` at `0x1801d94a0`
- `ADVAPI32!CloseTrace` at `0x1801d94a0`
- `ADVAPI32!OpenTraceW` at `0x1801d91fa`
- `ADVAPI32!OpenTraceW` at `0x1801d91fa`
- `ADVAPI32!EnableTrace` at `0x1801d9270`
- `ADVAPI32!EnableTrace` at `0x1801d92cc`
- `ADVAPI32!EnableTrace` at `0x1801d9270`
- `ADVAPI32!EnableTrace` at `0x1801d92cc`
- `ADVAPI32!StartTraceW` at `0x1801d9191`
- `ADVAPI32!StartTraceW` at `0x1801d9191`
- `ADVAPI32!ControlTraceW` at `0x1801d917c`
- `ADVAPI32!ControlTraceW` at `0x1801d9495`
- `ADVAPI32!ControlTraceW` at `0x1801d917c`
- `ADVAPI32!ControlTraceW` at `0x1801d9495`
- `OLE32!CoCreateGuid` at `0x1801d90ae`
- `OLE32!CoCreateGuid` at `0x1801d90ae`
- `OLE32!StringFromCLSID` at `0x1801d90dc`
- `OLE32!StringFromCLSID` at `0x1801d90dc`
- `OLE32!CoTaskMemFree` at `0x1801d90fb`
- `OLE32!CoTaskMemFree` at `0x1801d90fb`
- `SHLWAPI!SHCreateStreamOnFileEx` at `0x1801d8fbe`
- `SHLWAPI!SHCreateStreamOnFileEx` at `0x1801d8fbe`

## string_xrefs

- `0x1801d8dc4`: `Windows::Compat::Shared::UtcJson::Begin`
- `0x1801d93af`: `Windows::Compat::Shared::UtcJson::Begin`
- `0x1801d9460`: `Windows::Compat::Shared::UtcJson::Begin`
- `0x1801d8db3`: `Device is in security mode. Exiting function...`
- `0x1801d8dd2`: `onecore\base\appcompat\shared\unmanaged\utclogger\lib\utcjson.cpp`
- `0x1801d93bd`: `onecore\base\appcompat\shared\unmanaged\utclogger\lib\utcjson.cpp`
- `0x1801d946b`: `onecore\base\appcompat\shared\unmanaged\utclogger\lib\utcjson.cpp`
- `0x1801d8fda`: `Error opening file for write: [0x%x].`
- `0x1801d924a`: `Error opening trace: [%d].`
- `0x1801d9376`: `Error creating thread: [%d].`

## pseudocode

```c
__int64 __fastcall Windows::Compat::Shared::UtcJson::Begin(
        Windows::Compat::Shared::UtcJson *this,
        LPCWSTR pszFile,
        __int64 a3,
        const unsigned __int16 *const *a4)
{
  CHAR *v6; // r14
  char v7; // al
  int v8; // ebx
  unsigned __int64 v9; // rsi
  __int64 v10; // rbx
  HANDLE ProcessHeap; // rax
  CHAR *lpMultiByteStr; // rax
  HANDLE EventW; // rax
  signed int LastError; // eax
  __int64 (*v15)(__int64, __int64, const char *, const char *, int, const char *, ...); // rsi
  DWORD v16; // eax
  __int64 v17; // rdx
  const char *v18; // rax
  HANDLE v19; // rax
  signed int v20; // eax
  __int64 (*v21)(__int64, __int64, const char *, const char *, int, const char *, ...); // rax
  const char *v22; // rcx
  __int64 v23; // rdx
  HANDLE v24; // rax
  void *v25; // rax
  __int64 v26; // r8
  signed int started; // eax
  TRACEHANDLE v28; // rax
  signed int v29; // eax
  signed int v30; // eax
  signed int v31; // eax
  HANDLE Thread; // rax
  signed int v33; // eax
  signed int v34; // eax
  HANDLE v35; // rax
  LPCCH lpDefaultChar; // [rsp+30h] [rbp-D0h]
  DWORD lpDefaultChara; // [rsp+30h] [rbp-D0h]
  ULONG64 TraceHandle; // [rsp+40h] [rbp-C0h] BYREF
  LPOLESTR lpsz; // [rsp+48h] [rbp-B8h] BYREF
  CHAR *v41; // [rsp+50h] [rbp-B0h] BYREF
  struct _EVENT_TRACE_LOGFILEW Logfile; // [rsp+60h] [rbp-A0h] BYREF
  GUID ControlGuid; // [rsp+220h] [rbp+120h] BYREF
  GUID v44; // [rsp+230h] [rbp+130h] BYREF
  GUID pguid; // [rsp+240h] [rbp+140h] BYREF
  WCHAR WideCharStr[264]; // [rsp+250h] [rbp+150h] BYREF

  ControlGuid.Data1 = 1457276475;
  lpsz = 0;
  *(_DWORD *)&ControlGuid.Data2 = 1264162792;
  *(_DWORD *)ControlGuid.Data4 = 2091595496;
  *(_DWORD *)&ControlGuid.Data4[4] = 23312795;
  v44.Data1 = 1135363387;
  *(_DWORD *)&v44.Data2 = 1263638477;
  *(_DWORD *)v44.Data4 = 2094757443;
  pguid = 0;
  *(_DWORD *)&v44.Data4[4] = -1402750565;
  TraceHandle = -1;
  memset_0(&Logfile, 0, sizeof(Logfile));
  v6 = 0;
  if ( IsWindowsVersionOrGreater(0xAu, 0, 0) )
  {
    if ( `Windows::Compat::Shared::Telemetry::PermissionsHelper::IsOptedIntoCore'::`2'::AlreadyChecked )
    {
      v7 = `Windows::Compat::Shared::Telemetry::PermissionsHelper::IsOptedIntoCore'::`2'::IsOptedIn;
    }
    else
    {
      v7 = IsWindowsVersionOrGreater(0xAu, 0, 0)
         ? Windows::Compat::Shared::Telemetry::PermissionsHelper::IsWin10TelemetryTypeAllowed(1u)
         : (unsigned int)WinSqmIsOptedInEx(4) == 1;
      `Windows::Compat::Shared::Telemetry::PermissionsHelper::IsOptedIntoCore'::`2'::IsOptedIn = v7;
      `Windows::Compat::Shared::Telemetry::PermissionsHelper::IsOptedIntoCore'::`2'::AlreadyChecked = 1;
    }
    if ( !v7 )
    {
      if ( UtcHelperWriteLogCallback )
        UtcHelperWriteLogCallback(
          0,
          129,
          "onecore\\base\\appcompat\\shared\\unmanaged\\utclogger\\lib\\utcjson.cpp",
          "Windows::Compat::Shared::UtcJson::Begin",
          0,
          "Device is in security mode. Exiting function...");
      goto LABEL_11;
    }
  }
  v9 = 0;
  while ( 1 )
  {
    v8 = StringCchPrintfW(
           WideCharStr,
           0x104u,
           L"%ls%ls",
           L"\"name\":\"",
           (&Windows::Compat::Appraiser::Utilities::InterestingProviderNames)[v9]);
    if ( v8 < 0 )
    {
      v21 = (__int64 (*)(__int64, __int64, const char *, const char *, int, const char *, ...))UtcHelperWriteLogCallback;
      if ( !UtcHelperWriteLogCallback )
        goto LABEL_101;
      v22 = "Error printing interesting provider: [0x%x].";
      v23 = 137;
      goto LABEL_100;
    }
    v8 = RtlStringArray::Append((Windows::Compat::Shared::UtcJson *)((char *)this + 80), WideCharStr, 0);
    if ( v8 < 0 )
    {
      v21 = (__int64 (*)(__int64, __int64, const char *, const char *, int, const char *, ...))UtcHelperWriteLogCallback;
      if ( !UtcHelperWriteLogCallback )
        goto LABEL_101;
      v22 = "Error appending interesting provider: [0x%x].";
      v23 = 140;
      goto LABEL_100;
    }
    v10 = -1;
    do
      ++v10;
    while ( WideCharStr[v10] );
    ProcessHeap = GetProcessHeap();
    lpMultiByteStr = (CHAR *)HeapAlloc(ProcessHeap, 0, 2 * v10 + 2);
    v41 = lpMultiByteStr;
    v6 = lpMultiByteStr;
    if ( !lpMultiByteStr )
      goto LABEL_95;
    if ( !WideCharToMultiByte(0xFDE9u, 0, WideCharStr, -1, lpMultiByteStr, 260, 0, 0) )
      break;
    v8 = RtlArray<JsonValue *>::Append((char *)this + 32, &v41);
    if ( v8 < 0 )
    {
      if ( UtcHelperWriteLogCallback )
      {
        LODWORD(lpDefaultChar) = v8;
        UtcHelperWriteLogCallback(
          1,
          162,
          "onecore\\base\\appcompat\\shared\\unmanaged\\utclogger\\lib\\utcjson.cpp",
          "Windows::Compat::Shared::UtcJson::Begin",
          v8,
          "Error appending interesting provider: [0x%x].",
          lpDefaultChar);
      }
      v6 = v41;
      goto LABEL_101;
    }
    ++v9;
    v6 = 0;
    if ( v9 >= 6 )
    {
      EventW = CreateEventW(0, 1, 0, 0);
      *((_QWORD *)this + 1) = EventW;
      if ( !EventW )
      {
        LastError = GetLastError();
        v8 = LastError;
        if ( LastError > 0 )
          v8 = (unsigned __int16)LastError | 0x80070000;
        v15 = (__int64 (*)(__int64, __int64, const char *, const char *, int, const char *, ...))UtcHelperWriteLogCallback;
        if ( v8 >= 0 )
          v8 = -2147467259;
        if ( !UtcHelperWriteLogCallback )
          goto LABEL_101;
        v16 = GetLastError();
        v17 = 178;
        goto LABEL_28;
      }
      v19 = CreateEventW(0, 1, 0, 0);
      *((_QWORD *)this + 2) = v19;
      if ( !v19 )
      {
        v20 = GetLastError();
        v8 = v20;
        if ( v20 > 0 )
          v8 = (unsigned __int16)v20 | 0x80070000;
        v15 = (__int64 (*)(__int64, __int64, const char *, const char *, int, const char *, ...))UtcHelperWriteLogCallback;
        if ( v8 >= 0 )
          v8 = -2147467259;
        if ( !UtcHelperWriteLogCallback )
          goto LABEL_101;
        v16 = GetLastError();
        v17 = 183;
LABEL_28:
        lpDefaultChara = v16;
        v18 = "Error creating event: [%d].";
LABEL_29:
        v15(
          1,
          v17,
          "onecore\\base\\appcompat\\shared\\unmanaged\\utclogger\\lib\\utcjson.cpp",
          "Windows::Compat::Shared::UtcJson::Begin",
          v8,
          v18,
          lpDefaultChara);
        goto LABEL_101;
      }
      *((_BYTE *)this + 25) = 0;
      v8 = SHCreateStreamOnFileEx(pszFile, 0x1001u, 0, 0, 0, (IStream **)this);
      if ( v8 < 0 )
      {
        v21 = (__int64 (*)(__int64, __int64, const char *, const char *, int, const char *, ...))UtcHelperWriteLogCallback;
        if ( !UtcHelperWriteLogCallback )
          goto LABEL_101;
        v22 = "Error opening file for write: [0x%x].";
        v23 = 193;
        goto LABEL_100;
      }
      if ( *((_BYTE *)this + 25) )
      {
        v8 = Windows::Compat::Shared::UtcJson::WriteStringToFile(*(struct IStream **)this, "{\r\n    \"Events\":[");
        if ( v8 < 0 )
        {
          v21 = (__int64 (*)(__int64, __int64, const char *, const char *, int, const char *, ...))UtcHelperWriteLogCallback;
          if ( !UtcHelperWriteLogCallback )
            goto LABEL_101;
          v22 = "Error writing file beginning: [0x%x].";
          v23 = 198;
          goto LABEL_100;
        }
      }
      v24 = GetProcessHeap();
      v25 = HeapAlloc(v24, 0, 0x478u);
      *((_QWORD *)this + 17) = v25;
      if ( !v25 )
      {
LABEL_95:
        v8 = -2147024882;
        goto LABEL_101;
      }
      memset_0(v25, 0, 0x478u);
      v26 = -1;
      do
        ++v26;
      while ( Windows::Compat::Shared::UtcJson::s_TraceSessionName[v26] );
      memcpy_0((void *)(*((_QWORD *)this + 17) + 120LL), Windows::Compat::Shared::UtcJson::s_TraceSessionName, 2 * v26);
      **((_DWORD **)this + 17) = 1144;
      *(GUID *)(*((_QWORD *)this + 17) + 24LL) = ControlGuid;
      if ( !CoCreateGuid(&pguid) )
      {
        *(GUID *)(*((_QWORD *)this + 17) + 24LL) = pguid;
        if ( !StringFromCLSID(&pguid, &lpsz) )
        {
          _o_wcscpy_s(Windows::Compat::Shared::UtcJson::s_TraceSessionName, 256, lpsz);
          CoTaskMemFree(lpsz);
        }
      }
      *(_DWORD *)(*((_QWORD *)this + 17) + 40LL) = 1;
      *(_DWORD *)(*((_QWORD *)this + 17) + 44LL) = 0x20000;
      *(_DWORD *)(*((_QWORD *)this + 17) + 116LL) = 120;
      *(_DWORD *)(*((_QWORD *)this + 17) + 48LL) = *((_DWORD *)this + 41);
      *(_DWORD *)(*((_QWORD *)this + 17) + 52LL) = *((_DWORD *)this + 42);
      *(_DWORD *)(*((_QWORD *)this + 17) + 56LL) = *((_DWORD *)this + 43);
      *(_DWORD *)(*((_QWORD *)this + 17) + 64LL) = 256;
      *(_DWORD *)(*((_QWORD *)this + 17) + 68LL) = 1;
      ControlTraceW(
        0,
        Windows::Compat::Shared::UtcJson::s_TraceSessionName,
        *((PEVENT_TRACE_PROPERTIES *)this + 17),
        1u);
      started = StartTraceW(
                  &TraceHandle,
                  Windows::Compat::Shared::UtcJson::s_TraceSessionName,
                  *((PEVENT_TRACE_PROPERTIES *)this + 17));
      v8 = started;
      if ( started )
      {
        if ( started > 0 )
          v8 = (unsigned __int16)started | 0x80070000;
        if ( v8 >= 0 )
          v8 = -2147467259;
        v21 = (__int64 (*)(__int64, __int64, const char *, const char *, int, const char *, ...))UtcHelperWriteLogCallback;
        if ( !UtcHelperWriteLogCallback )
          goto LABEL_101;
        v22 = "Error starting trace: [0x%x].";
        v23 = 254;
        goto LABEL_100;
      }
      Logfile.LogFileMode = 268435712;
      Logfile.EventCallback = (PEVENT_CALLBACK)Windows::Compat::Shared::UtcJson::ProcessEventRecord;
      Logfile.LoggerName = Windows::Compat::Shared::UtcJson::s_TraceSessionName;
      Logfile.Context = this;
      v28 = OpenTraceW(&Logfile);
      *((_QWORD *)this + 19) = v28;
      if ( v28 == -1 )
      {
        v29 = GetLastError();
        v8 = v29;
        if ( v29 > 0 )
          v8 = (unsigned __int16)v29 | 0x80070000;
        v15 = (__int64 (*)(__int64, __int64, const char *, const char *, int, const char *, ...))UtcHelperWriteLogCallback;
        if ( v8 >= 0 )
          v8 = -2147467259;
        if ( !UtcHelperWriteLogCallback )
          goto LABEL_101;
        lpDefaultChara = GetLastError();
        v17 = 265;
        v18 = "Error opening trace: [%d].";
        goto LABEL_29;
      }
      v30 = EnableTrace(1u, 0, 4u, &ControlGuid, TraceHandle);
      v8 = v30;
      if ( v30 )
      {
        if ( v30 > 0 )
          v8 = (unsigned __int16)v30 | 0x80070000;
        if ( v8 >= 0 )
          v8 = -2147467259;
        v21 = (__int64 (*)(__int64, __int64, const char *, const char *, int, const char *, ...))UtcHelperWriteLogCallback;
        if ( !UtcHelperWriteLogCallback )
          goto LABEL_101;
        v22 = "Error enabling trace: [0x%x].";
        v23 = 271;
        goto LABEL_100;
      }
      v31 = EnableTrace(1u, 0, 5u, &v44, TraceHandle);
      v8 = v31;
      if ( v31 )
      {
        if ( v31 > 0 )
          v8 = (unsigned __int16)v31 | 0x80070000;
        if ( v8 >= 0 )
          v8 = -2147467259;
        v21 = (__int64 (*)(__int64, __int64, const char *, const char *, int, const char *, ...))UtcHelperWriteLogCallback;
        if ( !UtcHelperWriteLogCallback )
          goto LABEL_101;
        v22 = "Error enabling trace: [0x%x].";
        v23 = 277;
LABEL_100:
        v21(
          1,
          v23,
          "onecore\\base\\appcompat\\shared\\unmanaged\\utclogger\\lib\\utcjson.cpp",
          "Windows::Compat::Shared::UtcJson::Begin",
          v8,
          v22,
          v8);
        goto LABEL_101;
      }
      Thread = CreateThread(0, 0, Windows::Compat::Shared::UtcJson::TracerThreadProc, this, 0, 0);
      *((_QWORD *)this + 18) = Thread;
      if ( !Thread )
      {
        v33 = GetLastError();
        v8 = v33;
        if ( v33 > 0 )
          v8 = (unsigned __int16)v33 | 0x80070000;
        v15 = (__int64 (*)(__int64, __int64, const char *, const char *, int, const char *, ...))UtcHelperWriteLogCallback;
        if ( v8 >= 0 )
          v8 = -2147467259;
        if ( !UtcHelperWriteLogCallback )
          goto LABEL_101;
        lpDefaultChara = GetLastError();
        v17 = 287;
        v18 = "Error creating thread: [%d].";
        goto LABEL_29;
      }
      TraceHandle = -1;
      Windows::Compat::Shared::UtcJson::s_TraceStarted = 1;
LABEL_11:
      v8 = 0;
      goto LABEL_101;
    }
  }
  v34 = GetLastError();
  v8 = v34;
  if ( v34 > 0 )
    v8 = (unsigned __int16)v34 | 0x80070000;
  v15 = (__int64 (*)(__int64, __int64, const char *, const char *, int, const char *, ...))UtcHelperWriteLogCallback;
  if ( v8 >= 0 )
    v8 = -2147467259;
  if ( UtcHelperWriteLogCallback )
  {
    lpDefaultChara = GetLastError();
    v17 = 154;
    v18 = "Error writing to multi-byte buffer: [%d].";
    goto LABEL_29;
  }
LABEL_101:
  if ( TraceHandle - 1 <= 0xFFFFFFFFFFFFFFFDuLL )
  {
    ControlTraceW(TraceHandle, 0, *((PEVENT_TRACE_PROPERTIES *)this + 17), 1u);
    CloseTrace(TraceHandle);
  }
  if ( v6 )
  {
    v35 = GetProcessHeap();
    HeapFree(v35, 0, v6);
  }
  if ( v8 < 0 )
    Windows::Compat::Shared::UtcJson::CleanupMembers(this);
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x1801d8c88  mov     [rsp-8+arg_10], rbx
0x1801d8c8d  push    rbp
0x1801d8c8e  push    rsi
0x1801d8c8f  push    rdi
0x1801d8c90  push    r12
0x1801d8c92  push    r13
0x1801d8c94  push    r14
0x1801d8c96  push    r15
0x1801d8c98  lea     rbp, [rsp-370h]
0x1801d8ca0  sub     rsp, 470h
0x1801d8ca7  mov     rax, cs:__security_cookie
0x1801d8cae  xor     rax, rsp
0x1801d8cb1  mov     [rbp+3A0h+var_40], rax
0x1801d8cb8  xor     r12d, r12d
0x1801d8cbb  mov     [rbp+3A0h+ControlGuid.Data1], 56DC463Bh
0x1801d8cc5  mov     r15, rdx
0x1801d8cc8  mov     [rsp+4A0h+lpsz], r12
0x1801d8ccd  mov     rdi, rcx
0x1801d8cd0  mov     dword ptr [rbp+3A0h+ControlGuid.Data2], 4B5997E8h
0x1801d8cda  xorps   xmm0, xmm0
0x1801d8cdd  mov     dword ptr [rbp+3A0h+ControlGuid.Data4], 7CAB36E8h
0x1801d8ce7  xor     edx, edx; Val
0x1801d8ce9  mov     dword ptr [rbp+3A0h+ControlGuid.Data4+4], 163B99Bh
0x1801d8cf3  mov     r8d, 1C0h; Size
0x1801d8cf9  mov     [rbp+3A0h+var_270.Data1], 43AC453Bh
0x1801d8d03  lea     rcx, [rsp+4A0h+Logfile]; void *
0x1801d8d08  mov     dword ptr [rbp+3A0h+var_270.Data2], 4B5197CDh
0x1801d8d12  lea     r13d, [r12+1]
0x1801d8d17  mov     dword ptr [rbp+3A0h+var_270.Data4], 7CDB7643h
0x1801d8d21  movups  xmmword ptr [rbp+3A0h+pguid.Data1], xmm0
0x1801d8d28  mov     dword ptr [rbp+3A0h+var_270.Data4+4], 0AC63B99Bh
0x1801d8d32  mov     [rsp+4A0h+TraceHandle], 0FFFFFFFFFFFFFFFFh
0x1801d8d3b  call    memset_0
0x1801d8d40  xor     edx, edx; unsigned __int16
0x1801d8d42  xor     r8d, r8d; unsigned __int16
0x1801d8d45  mov     r14d, r12d
0x1801d8d48  lea     ebx, [rdx+0Ah]
0x1801d8d4b  mov     ecx, ebx; unsigned __int16
0x1801d8d4d  call    ?IsWindowsVersionOrGreater@@YA_NGGG@Z; IsWindowsVersionOrGreater(ushort,ushort,ushort)
0x1801d8d52  test    al, al
0x1801d8d54  jz      loc_1801D8DE6
0x1801d8d5a  cmp     cs:?AlreadyChecked@?1??IsOptedIntoCore@PermissionsHelper@Telemetry@Shared@Compat@Windows@@SA_N_N@Z@4_NA, r12b; bool `Windows::Compat::Shared::Telemetry::PermissionsHelper::IsOptedIntoCore(bool)'::`2'::AlreadyChecked
0x1801d8d61  jnz     short loc_1801D8D9D
0x1801d8d63  xor     r8d, r8d; unsigned __int16
0x1801d8d66  xor     edx, edx; unsigned __int16
0x1801d8d68  mov     ecx, ebx; unsigned __int16
0x1801d8d6a  call    ?IsWindowsVersionOrGreater@@YA_NGGG@Z; IsWindowsVersionOrGreater(ushort,ushort,ushort)
0x1801d8d6f  test    al, al
0x1801d8d71  jz      short loc_1801D8D7D
0x1801d8d73  mov     ecx, r13d; unsigned int
0x1801d8d76  call    ?IsWin10TelemetryTypeAllowed@PermissionsHelper@Telemetry@Shared@Compat@Windows@@CA_NK@Z; Windows::Compat::Shared::Telemetry::PermissionsHelper::IsWin10TelemetryTypeAllowed(ulong)
0x1801d8d7b  jmp     short loc_1801D8D8E
0x1801d8d7d  mov     ecx, 4
0x1801d8d82  call    cs:__imp_WinSqmIsOptedInEx
0x1801d8d88  cmp     eax, r13d
0x1801d8d8b  setz    al
0x1801d8d8e  mov     cs:?IsOptedIn@?1??IsOptedIntoCore@PermissionsHelper@Telemetry@Shared@Compat@Windows@@SA_N_N@Z@4_NA, al; bool `Windows::Compat::Shared::Telemetry::PermissionsHelper::IsOptedIntoCore(bool)'::`2'::IsOptedIn
0x1801d8d94  mov     cs:?AlreadyChecked@?1??IsOptedIntoCore@PermissionsHelper@Telemetry@Shared@Compat@Windows@@SA_N_N@Z@4_NA, r13b; bool `Windows::Compat::Shared::Telemetry::PermissionsHelper::IsOptedIntoCore(bool)'::`2'::AlreadyChecked
0x1801d8d9b  jmp     short loc_1801D8DA3
0x1801d8d9d  mov     al, cs:?IsOptedIn@?1??IsOptedIntoCore@PermissionsHelper@Telemetry@Shared@Compat@Windows@@SA_N_N@Z@4_NA; bool `Windows::Compat::Shared::Telemetry::PermissionsHelper::IsOptedIntoCore(bool)'::`2'::IsOptedIn
0x1801d8da3  test    al, al
0x1801d8da5  jnz     short loc_1801D8DE6
0x1801d8da7  mov     rax, cs:UtcHelperWriteLogCallback
0x1801d8dae  test    rax, rax
0x1801d8db1  jz      short loc_1801D8DDE
0x1801d8db3  lea     rcx, aDeviceIsInSecu_1; "Device is in security mode. Exiting fun"...
0x1801d8dba  mov     edx, 81h
0x1801d8dbf  mov     qword ptr [rsp+4A0h+cbMultiByte], rcx
0x1801d8dc4  lea     r9, aWindowsCompatS_2; "Windows::Compat::Shared::UtcJson::Begin"
0x1801d8dcb  xor     ecx, ecx
0x1801d8dcd  mov     [rsp+4A0h+lpMultiByteStr], r12
0x1801d8dd2  lea     r8, aOnecoreBaseApp_106; "onecore\\base\\appcompat\\shared\\unman"...
0x1801d8dd9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801d8dde  mov     ebx, r12d
0x1801d8de1  jmp     loc_1801D947A
0x1801d8de6  mov     rsi, r12
0x1801d8de9  lea     rax, ?InterestingProviderNames@Utilities@Appraiser@Compat@Windows@@2QBQEBGB; ushort const * const near * const Windows::Compat::Appraiser::Utilities::InterestingProviderNames
0x1801d8df0  mov     edx, 104h; unsigned __int64
0x1801d8df5  mov     rax, [rax+rsi*8]
0x1801d8df9  lea     r9, aName; "\"name\":\""
0x1801d8e00  lea     r8, aLsLs_3; "%ls%ls"
0x1801d8e07  mov     [rsp+4A0h+lpMultiByteStr], rax
0x1801d8e0c  lea     rcx, [rbp+3A0h+WideCharStr]; unsigned __int16 *
0x1801d8e13  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1801d8e18  mov     ebx, eax
0x1801d8e1a  test    eax, eax
0x1801d8e1c  js      loc_1801D943F
0x1801d8e22  lea     rcx, [rdi+50h]; this
0x1801d8e26  xor     r8d, r8d; unsigned __int64
0x1801d8e29  lea     rdx, [rbp+3A0h+WideCharStr]; unsigned __int16 *
0x1801d8e30  call    ?Append@RtlStringArray@@QEAAJPEBG_K@Z; RtlStringArray::Append(ushort const *,unsigned __int64)
0x1801d8e35  mov     ebx, eax
0x1801d8e37  test    eax, eax
0x1801d8e39  js      loc_1801D9425
0x1801d8e3f  lea     rax, [rbp+3A0h+WideCharStr]
0x1801d8e46  or      rbx, 0FFFFFFFFFFFFFFFFh
0x1801d8e4a  inc     rbx
0x1801d8e4d  cmp     [rax+rbx*2], r12w
0x1801d8e52  jnz     short loc_1801D8E4A
0x1801d8e54  lea     rbx, ds:2[rbx*2]
0x1801d8e5c  call    cs:__imp_GetProcessHeap
0x1801d8e62  mov     r8, rbx; dwBytes
0x1801d8e65  xor     edx, edx; dwFlags
0x1801d8e67  mov     rcx, rax; hHeap
0x1801d8e6a  call    cs:__imp_HeapAlloc
0x1801d8e70  mov     [rsp+4A0h+var_450], rax
0x1801d8e75  mov     r14, rax
0x1801d8e78  test    rax, rax
0x1801d8e7b  jz      loc_1801D941E
0x1801d8e81  mov     [rsp+4A0h+lpUsedDefaultChar], r12; lpUsedDefaultChar
0x1801d8e86  lea     r8, [rbp+3A0h+WideCharStr]; lpWideCharStr
0x1801d8e8d  mov     [rsp+4A0h+lpDefaultChar], r12; lpDefaultChar
0x1801d8e92  or      r9d, 0FFFFFFFFh; cchWideChar
0x1801d8e96  mov     [rsp+4A0h+cbMultiByte], 104h; cbMultiByte
0x1801d8e9e  xor     edx, edx; dwFlags
0x1801d8ea0  mov     ecx, 0FDE9h; CodePage
0x1801d8ea5  mov     [rsp+4A0h+lpMultiByteStr], rax; lpMultiByteStr
0x1801d8eaa  call    cs:__imp_WideCharToMultiByte
0x1801d8eb0  test    eax, eax
0x1801d8eb2  jz      loc_1801D93D8
0x1801d8eb8  lea     rcx, [rdi+20h]
0x1801d8ebc  lea     rdx, [rsp+4A0h+var_450]
0x1801d8ec1  call    ?Append@?$RtlArray@PEAUJsonValue@@@@QEAAJAEBQEAUJsonValue@@@Z; RtlArray<JsonValue *>::Append(JsonValue * const &)
0x1801d8ec6  mov     ebx, eax
0x1801d8ec8  test    eax, eax
0x1801d8eca  js      loc_1801D9393
0x1801d8ed0  add     rsi, r13
0x1801d8ed3  mov     r14, r12
0x1801d8ed6  cmp     rsi, 6
0x1801d8eda  jb      loc_1801D8DE9
0x1801d8ee0  xor     r9d, r9d; lpName
0x1801d8ee3  xor     r8d, r8d; bInitialState
0x1801d8ee6  mov     edx, r13d; bManualReset
0x1801d8ee9  xor     ecx, ecx; lpEventAttributes
0x1801d8eeb  call    cs:__imp_CreateEventW
0x1801d8ef1  mov     [rdi+8], rax
0x1801d8ef5  test    rax, rax
0x1801d8ef8  jnz     short loc_1801D8F4C
0x1801d8efa  call    cs:__imp_GetLastError
0x1801d8f00  mov     ebx, eax
0x1801d8f02  test    eax, eax
0x1801d8f04  jle     short loc_1801D8F0F
0x1801d8f06  movzx   ebx, ax
0x1801d8f09  or      ebx, 80070000h
0x1801d8f0f  mov     rsi, cs:UtcHelperWriteLogCallback
0x1801d8f16  test    ebx, ebx
0x1801d8f18  mov     eax, 80004005h
0x1801d8f1d  cmovns  ebx, eax
0x1801d8f20  test    rsi, rsi
0x1801d8f23  jz      loc_1801D947A
0x1801d8f29  call    cs:__imp_GetLastError
0x1801d8f2f  mov     edx, 0B2h
0x1801d8f34  mov     dword ptr [rsp+4A0h+lpDefaultChar], eax
0x1801d8f38  lea     rax, aErrorCreatingE_1; "Error creating event: [%d]."
0x1801d8f3f  mov     qword ptr [rsp+4A0h+cbMultiByte], rax
0x1801d8f44  mov     rax, rsi
0x1801d8f47  jmp     loc_1801D9460
0x1801d8f4c  xor     r9d, r9d; lpName
0x1801d8f4f  xor     r8d, r8d; bInitialState
0x1801d8f52  mov     edx, r13d; bManualReset
0x1801d8f55  xor     ecx, ecx; lpEventAttributes
0x1801d8f57  call    cs:__imp_CreateEventW
0x1801d8f5d  mov     [rdi+10h], rax
0x1801d8f61  test    rax, rax
0x1801d8f64  jnz     short loc_1801D8FA2
0x1801d8f66  call    cs:__imp_GetLastError
0x1801d8f6c  mov     ebx, eax
0x1801d8f6e  test    eax, eax
0x1801d8f70  jle     short loc_1801D8F7B
0x1801d8f72  movzx   ebx, ax
0x1801d8f75  or      ebx, 80070000h
0x1801d8f7b  mov     rsi, cs:UtcHelperWriteLogCallback
0x1801d8f82  test    ebx, ebx
0x1801d8f84  mov     eax, 80004005h
0x1801d8f89  cmovns  ebx, eax
0x1801d8f8c  test    rsi, rsi
0x1801d8f8f  jz      loc_1801D947A
0x1801d8f95  call    cs:__imp_GetLastError
0x1801d8f9b  mov     edx, 0B7h
0x1801d8fa0  jmp     short loc_1801D8F34
0x1801d8fa2  mov     qword ptr [rsp+4A0h+cbMultiByte], rdi; ppstm
0x1801d8fa7  xor     r9d, r9d; fCreate
0x1801d8faa  xor     r8d, r8d; dwAttributes
0x1801d8fad  mov     [rsp+4A0h+lpMultiByteStr], r12; pstmTemplate
0x1801d8fb2  mov     edx, 1001h; grfMode
0x1801d8fb7  mov     [rdi+19h], r12b
0x1801d8fbb  mov     rcx, r15; pszFile
0x1801d8fbe  call    cs:__imp_SHCreateStreamOnFileEx
0x1801d8fc4  mov     ebx, eax
0x1801d8fc6  test    eax, eax
0x1801d8fc8  jns     short loc_1801D8FEB
0x1801d8fca  mov     rax, cs:UtcHelperWriteLogCallback
0x1801d8fd1  test    rax, rax
0x1801d8fd4  jz      loc_1801D947A
0x1801d8fda  lea     rcx, aErrorOpeningFi_0; "Error opening file for write: [0x%x]."
0x1801d8fe1  mov     edx, 0C1h
0x1801d8fe6  jmp     loc_1801D9457
0x1801d8feb  cmp     [rdi+19h], r12b
0x1801d8fef  jz      short loc_1801D9027
0x1801d8ff1  mov     rcx, [rdi]; struct IStream *
0x1801d8ff4  lea     rdx, aEvents; "{\r\n    \"Events\":["
0x1801d8ffb  call    ?WriteStringToFile@UtcJson@Shared@Compat@Windows@@CAJPEAUIStream@@PEBD@Z; Windows::Compat::Shared::UtcJson::WriteStringToFile(IStream *,char const *)
0x1801d9000  mov     ebx, eax
0x1801d9002  test    eax, eax
0x1801d9004  jns     short loc_1801D9027
0x1801d9006  mov     rax, cs:UtcHelperWriteLogCallback
0x1801d900d  test    rax, rax
0x1801d9010  jz      loc_1801D947A
0x1801d9016  lea     rcx, aErrorWritingFi_0; "Error writing file beginning: [0x%x]."
0x1801d901d  mov     edx, 0C6h
0x1801d9022  jmp     loc_1801D9457
0x1801d9027  call    cs:__imp_GetProcessHeap
0x1801d902d  mov     ebx, 478h
0x1801d9032  xor     edx, edx; dwFlags
0x1801d9034  mov     rcx, rax; hHeap
0x1801d9037  mov     r8d, ebx; dwBytes
0x1801d903a  call    cs:__imp_HeapAlloc
0x1801d9040  mov     [rdi+88h], rax
0x1801d9047  test    rax, rax
0x1801d904a  jz      loc_1801D941E
0x1801d9050  mov     r8d, ebx; Size
0x1801d9053  xor     edx, edx; Val
0x1801d9055  mov     rcx, rax; void *
0x1801d9058  call    memset_0
0x1801d905d  or      r15, 0FFFFFFFFFFFFFFFFh
0x1801d9061  lea     rsi, ?s_TraceSessionName@UtcJson@Shared@Compat@Windows@@0PAGA; "Appraiser DiagTrack Listener"
0x1801d9068  mov     r8, r15
0x1801d906b  inc     r8
0x1801d906e  cmp     [rsi+r8*2], r12w
0x1801d9073  jnz     short loc_1801D906B
0x1801d9075  mov     rcx, [rdi+88h]
0x1801d907c  add     r8, r8; Size
0x1801d907f  add     rcx, 78h ; 'x'; void *
0x1801d9083  mov     rdx, rsi; Src
0x1801d9086  call    memcpy_0
0x1801d908b  mov     rax, [rdi+88h]
0x1801d9092  lea     rcx, [rbp+3A0h+pguid]; pguid
0x1801d9099  mov     [rax], ebx
0x1801d909b  mov     rax, [rdi+88h]
0x1801d90a2  movups  xmm0, xmmword ptr [rbp+3A0h+ControlGuid.Data1]
0x1801d90a9  movdqu  xmmword ptr [rax+18h], xmm0
0x1801d90ae  call    cs:__imp_CoCreateGuid
0x1801d90b4  mov     ebx, 100h
0x1801d90b9  test    eax, eax
0x1801d90bb  jnz     short loc_1801D9101
0x1801d90bd  mov     rax, [rdi+88h]
0x1801d90c4  lea     rdx, [rsp+4A0h+lpsz]; lplpsz
0x1801d90c9  movups  xmm0, xmmword ptr [rbp+3A0h+pguid.Data1]
0x1801d90d0  lea     rcx, [rbp+3A0h+pguid]; rclsid
0x1801d90d7  movdqu  xmmword ptr [rax+18h], xmm0
0x1801d90dc  call    cs:__imp_StringFromCLSID
0x1801d90e2  test    eax, eax
0x1801d90e4  jnz     short loc_1801D9101
0x1801d90e6  mov     r8, [rsp+4A0h+lpsz]
0x1801d90eb  mov     edx, ebx
0x1801d90ed  mov     rcx, rsi
0x1801d90f0  call    cs:__imp__o_wcscpy_s
0x1801d90f6  mov     rcx, [rsp+4A0h+lpsz]; pv
0x1801d90fb  call    cs:__imp_CoTaskMemFree
0x1801d9101  mov     rax, [rdi+88h]
0x1801d9108  mov     r9d, r13d; ControlCode
0x1801d910b  mov     rdx, rsi; InstanceName
0x1801d910e  mov     [rax+28h], r13d
0x1801d9112  mov     rax, [rdi+88h]
0x1801d9119  mov     dword ptr [rax+2Ch], 20000h
0x1801d9120  mov     rax, [rdi+88h]
0x1801d9127  mov     dword ptr [rax+74h], 78h ; 'x'
0x1801d912e  mov     eax, [rdi+0A4h]
0x1801d9134  mov     rcx, [rdi+88h]
0x1801d913b  mov     [rcx+30h], eax
0x1801d913e  mov     eax, [rdi+0A8h]
0x1801d9144  mov     rcx, [rdi+88h]
0x1801d914b  mov     [rcx+34h], eax
0x1801d914e  mov     rcx, [rdi+88h]
0x1801d9155  mov     eax, [rdi+0ACh]
0x1801d915b  mov     [rcx+38h], eax
0x1801d915e  xor     ecx, ecx; TraceHandle
0x1801d9160  mov     rax, [rdi+88h]
0x1801d9167  mov     [rax+40h], ebx
0x1801d916a  mov     rax, [rdi+88h]
0x1801d9171  mov     [rax+44h], r13d
0x1801d9175  mov     r8, [rdi+88h]; Properties
0x1801d917c  call    cs:__imp_ControlTraceW
0x1801d9182  mov     r8, [rdi+88h]; Properties
0x1801d9189  lea     rcx, [rsp+4A0h+TraceHandle]; TraceHandle
0x1801d918e  mov     rdx, rsi; InstanceName
0x1801d9191  call    cs:__imp_StartTraceW
0x1801d9197  mov     ebx, eax
0x1801d9199  test    eax, eax
0x1801d919b  jz      short loc_1801D91D3
0x1801d919d  jle     short loc_1801D91A8
0x1801d919f  movzx   ebx, ax
0x1801d91a2  or      ebx, 80070000h
0x1801d91a8  test    ebx, ebx
0x1801d91aa  mov     eax, 80004005h
0x1801d91af  cmovns  ebx, eax
0x1801d91b2  mov     rax, cs:UtcHelperWriteLogCallback
0x1801d91b9  test    rax, rax
0x1801d91bc  jz      loc_1801D947A
0x1801d91c2  lea     rcx, aErrorStartingT; "Error starting trace: [0x%x]."
  ... truncated ...
```
