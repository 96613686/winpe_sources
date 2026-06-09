# PrintConfig::CQueueEnumerationHelper::RemotePrinterChangeNotificationCallback(std::shared_ptr<PrintConfig::CRemotePrinterNotificationContext>)

- ea: `0x18008c520`
- end: `0x18008c97e`
- name: `?RemotePrinterChangeNotificationCallback@CQueueEnumerationHelper@PrintConfig@@CAXV?$shared_ptr@VCRemotePrinterNotificationContext@PrintConfig@@@std@@@Z`
- size: `1118`
- prototype: `signed __int32 __fastcall(HKEY)`
- caller_count: `0`
- callee_count: `11`
- tags: `registry_config, loader_planting, installer_update, broker_com_uri`

## callees

- `0x180003400`
- `0x180004564`
- `0x18000de1c`
- `0x18000f830`
- `0x18000fa4c`
- `0x180018f58`
- `0x1800378fc`
- `0x180037b14`
- `0x1800388f4`
- `0x18008c520`
- `0x1801cb010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18008c5ae`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18008c5ae`
- `KERNEL32!CloseHandle` at `0x18008c6ca`
- `KERNEL32!CloseHandle` at `0x18008c703`
- `KERNEL32!CloseHandle` at `0x18008c7ce`
- `KERNEL32!CloseHandle` at `0x18008c807`
- `KERNEL32!CloseHandle` at `0x18008c6ca`
- `KERNEL32!CloseHandle` at `0x18008c703`
- `KERNEL32!CloseHandle` at `0x18008c7ce`
- `KERNEL32!CloseHandle` at `0x18008c807`
- `KERNEL32!GetLastError` at `0x18008c581`
- `KERNEL32!GetLastError` at `0x18008c69b`
- `KERNEL32!GetLastError` at `0x18008c79c`
- `KERNEL32!GetLastError` at `0x18008c581`
- `KERNEL32!GetLastError` at `0x18008c69b`
- `KERNEL32!GetLastError` at `0x18008c79c`
- `KERNEL32!SetEvent` at `0x18008c86c`
- `KERNEL32!SetEvent` at `0x18008c86c`
- `KERNEL32!CreateEventW` at `0x18008c562`
- `KERNEL32!CreateEventW` at `0x18008c562`
- `KERNEL32!CreateWaitableTimerW` at `0x18008c63c`
- `KERNEL32!CreateWaitableTimerW` at `0x18008c63c`
- `KERNEL32!WaitForMultipleObjects` at `0x18008c67d`
- `KERNEL32!WaitForMultipleObjects` at `0x18008c77a`
- `KERNEL32!WaitForMultipleObjects` at `0x18008c67d`
- `KERNEL32!WaitForMultipleObjects` at `0x18008c77a`
- `ADVAPI32!RegCloseKey` at `0x18008c6e1`
- `ADVAPI32!RegCloseKey` at `0x18008c7e5`
- `ADVAPI32!RegCloseKey` at `0x18008c6e1`
- `ADVAPI32!RegCloseKey` at `0x18008c7e5`

## string_xrefs

- `0x18008c5be`: `Registry location for v4 connection cache appears to have changed. Enumerating remote printers may not function properly.`
- `0x18008c5c5`: `PrintConfig::CQueueEnumerationHelper::RemotePrinterChangeNotificationCallback`
- `0x18008c889`: `PrintConfig::CQueueEnumerationHelper::RemotePrinterChangeNotificationCallback`
- `0x18008c882`: `Listening to updates for printer connections in registry failed: 0x%x`

## pseudocode

```c
// Hidden C++ exception states: #wind=5 #try_helpers=1
signed __int32 __fastcall PrintConfig::CQueueEnumerationHelper::RemotePrinterChangeNotificationCallback(HKEY a1)
{
  char *EventW; // rbx
  signed int LastError; // eax
  bool v4; // sf
  __int64 v5; // rcx
  __int64 v6; // r8
  struct RegistryHandleRAII *v7; // rdx
  __int64 v8; // r8
  char *WaitableTimerW; // rdi
  HANDLE *v10; // rcx
  DWORD v11; // eax
  signed int v12; // eax
  bool v13; // sf
  signed __int32 result; // eax
  volatile signed __int32 *v15; // rdi
  DWORD v16; // eax
  struct RegistryHandleRAII *v17; // rdx
  __int64 v18; // r8
  signed int v19; // eax
  bool v20; // sf
  volatile signed __int32 *v21; // rdi
  HKEY hKey[2]; // [rsp+30h] [rbp-E8h] BYREF
  HANDLE Handles[2]; // [rsp+40h] [rbp-D8h] BYREF
  HANDLE v24[7]; // [rsp+50h] [rbp-C8h] BYREF
  _BYTE pExceptionObject[32]; // [rsp+88h] [rbp-90h] BYREF
  _BYTE v26[32]; // [rsp+A8h] [rbp-70h] BYREF
  _BYTE v27[32]; // [rsp+C8h] [rbp-50h] BYREF
  _OWORD v28[2]; // [rsp+E8h] [rbp-30h] BYREF

  v24[2] = (HANDLE)-2LL;
  hKey[1] = a1;
  EventW = (char *)CreateEventW(0, 1, 0, 0);
  v24[3] = EventW;
  if ( ((unsigned __int64)(EventW + 1) & 0xFFFFFFFFFFFFFFFEuLL) == 0 )
  {
    LastError = GetLastError();
    v4 = LastError < 0;
    if ( LastError > 0 )
    {
      LastError = (unsigned __int16)LastError | 0x80070000;
      v4 = LastError < 0;
    }
    if ( v4 )
    {
      hr_error::hr_error((hr_error *)pExceptionObject, LastError);
      throw (hr_error *)pExceptionObject;
    }
  }
  if ( (unsigned int)_o__wcsicmp(
                       L"SOFTWARE\\Microsoft\\Windows NT\\CurrentVersion\\Print\\V4 Connections",
                       L"SOFTWARE\\Microsoft\\Windows NT\\CurrentVersion\\Print\\V4 Connections") )
    Print::Driver::Telemetry::PrintConfigTelemetry::WriteDbgTraceWarning(
      "PrintConfig::CQueueEnumerationHelper::RemotePrinterChangeNotificationCallback",
      L"Registry location for v4 connection cache appears to have changed. Enumerating remote printers may not function properly.");
  hKey[0] = 0;
  memset(v28, 0, sizeof(v28));
  std::wstring::_Construct<1,unsigned short const *>(
    v28,
    L"SOFTWARE\\Microsoft\\Windows NT\\CurrentVersion\\Print\\V4 Connections",
    0x41u);
  Win32Adapters::Registry::RegOpenKeyW(v5, (const WCHAR *)v28, v6, hKey);
  std::wstring::~wstring((char **)v28);
  Win32Adapters::Registry::RegNotifyChangeKeyValue(hKey, v7, v8, EventW);
  WaitableTimerW = (char *)CreateWaitableTimerW(0, 0, 0);
  v24[4] = WaitableTimerW;
  Handles[0] = EventW;
  v10 = *(HANDLE **)a1;
  Handles[1] = **(HANDLE **)a1;
  v24[0] = WaitableTimerW;
  v24[1] = *v10;
  while ( 1 )
  {
    while ( 1 )
    {
      while ( 1 )
      {
        v11 = WaitForMultipleObjects(2u, Handles, 0, 0xFFFFFFFF);
        if ( !v11 )
          break;
        if ( v11 == 1 )
        {
          if ( (unsigned __int64)(WaitableTimerW - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
            CloseHandle(WaitableTimerW);
          if ( hKey[0] )
          {
            RegCloseKey(hKey[0]);
            hKey[0] = 0;
          }
          result = (_DWORD)EventW - 1;
          if ( (unsigned __int64)(EventW - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
            result = CloseHandle(EventW);
          v15 = (volatile signed __int32 *)*((_QWORD *)a1 + 1);
          if ( v15 )
          {
            result = _InterlockedDecrement(v15 + 2);
            if ( !result )
            {
              (**(void (__fastcall ***)(volatile signed __int32 *))v15)(v15);
              result = _InterlockedDecrement(v15 + 3);
              if ( !result )
                return (*(__int64 (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v15 + 8LL))(v15);
            }
          }
          return result;
        }
        if ( v11 == -1 )
        {
          v12 = GetLastError();
          v13 = v12 < 0;
          if ( v12 > 0 )
          {
            v12 = (unsigned __int16)v12 | 0x80070000;
            v13 = v12 < 0;
          }
          if ( v13 )
          {
            hr_error::hr_error((hr_error *)v26, v12);
            throw (hr_error *)v26;
          }
        }
      }
      Win32Adapters::Synchronization::SetWaitableTimerEx(
        (Win32Adapters::Synchronization *)WaitableTimerW,
        (void *const)0x1F40,
        800,
        0);
      v16 = WaitForMultipleObjects(2u, v24, 0, 0xFFFFFFFF);
      if ( v16 )
        break;
      Win32Adapters::Registry::RegNotifyChangeKeyValue(hKey, v17, v18, EventW);
      SetEvent(*(HANDLE *)(*(_QWORD *)a1 + 8LL));
    }
    if ( v16 == 1 )
      break;
    if ( v16 == -1 )
    {
      v19 = GetLastError();
      v20 = v19 < 0;
      if ( v19 > 0 )
      {
        v19 = (unsigned __int16)v19 | 0x80070000;
        v20 = v19 < 0;
      }
      if ( v20 )
      {
        hr_error::hr_error((hr_error *)v27, v19);
        throw (hr_error *)v27;
      }
    }
  }
  if ( (unsigned __int64)(WaitableTimerW - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
    CloseHandle(WaitableTimerW);
  if ( hKey[0] )
  {
    RegCloseKey(hKey[0]);
    hKey[0] = 0;
  }
  result = (_DWORD)EventW - 1;
  if ( (unsigned __int64)(EventW - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
    result = CloseHandle(EventW);
  v21 = (volatile signed __int32 *)*((_QWORD *)a1 + 1);
  if ( v21 )
  {
    result = _InterlockedDecrement(v21 + 2);
    if ( !result )
    {
      (**(void (__fastcall ***)(volatile signed __int32 *))v21)(v21);
      result = _InterlockedDecrement(v21 + 3);
      if ( !result )
        return (*(__int64 (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v21 + 8LL))(v21);
    }
  }
  return result;
}

```

## disassembly

```asm
0x18008c520  mov     rax, rsp
0x18008c523  push    rdi
0x18008c524  sub     rsp, 110h
0x18008c52b  mov     [rsp+118h+var_B8], 0FFFFFFFFFFFFFFFEh
0x18008c534  mov     [rax+10h], rbx
0x18008c538  mov     [rax+18h], rsi
0x18008c53c  mov     rax, cs:__security_cookie
0x18008c543  xor     rax, rsp
0x18008c546  mov     [rsp+118h+var_10], rax
0x18008c54e  mov     rsi, rcx
0x18008c551  mov     [rsp+118h+var_E0], rcx
0x18008c556  xor     r9d, r9d; lpName
0x18008c559  xor     r8d, r8d; bInitialState
0x18008c55c  lea     edx, [r9+1]; bManualReset
0x18008c560  xor     ecx, ecx; lpEventAttributes
0x18008c562  call    cs:__imp_CreateEventW
0x18008c569  nop     dword ptr [rax+rax+00h]
0x18008c56e  mov     rbx, rax
0x18008c571  mov     [rsp+118h+var_B0], rax
0x18008c576  inc     rax
0x18008c579  test    rax, 0FFFFFFFFFFFFFFFEh
0x18008c57f  jnz     short loc_18008C5A1
0x18008c581  call    cs:__imp_GetLastError
0x18008c588  nop     dword ptr [rax+rax+00h]
0x18008c58d  test    eax, eax
0x18008c58f  jle     short loc_18008C59B
0x18008c591  movzx   eax, ax
0x18008c594  or      eax, 80070000h
0x18008c599  test    eax, eax
0x18008c59b  js      loc_18008C912
0x18008c5a1  lea     rdi, aSoftwareMicros; "SOFTWARE\\Microsoft\\Windows NT\\Curren"...
0x18008c5a8  mov     rdx, rdi
0x18008c5ab  mov     rcx, rdi
0x18008c5ae  call    cs:__imp__o__wcsicmp
0x18008c5b5  nop     dword ptr [rax+rax+00h]
0x18008c5ba  test    eax, eax
0x18008c5bc  jz      short loc_18008C5D1
0x18008c5be  lea     rdx, aRegistryLocati; "Registry location for v4 connection cac"...
0x18008c5c5  lea     rcx, aPrintconfigCqu; "PrintConfig::CQueueEnumerationHelper::R"...
0x18008c5cc  call    ?WriteDbgTraceWarning@PrintConfigTelemetry@Telemetry@Driver@Print@@SAXPEADPEAGZZ; Print::Driver::Telemetry::PrintConfigTelemetry::WriteDbgTraceWarning(char *,ushort *,...)
0x18008c5d1  mov     [rsp+118h+hKey], 0
0x18008c5da  xorps   xmm0, xmm0
0x18008c5dd  movups  [rsp+118h+var_30], xmm0
0x18008c5e5  xorps   xmm1, xmm1
0x18008c5e8  movdqu  [rsp+118h+var_20], xmm1
0x18008c5f1  mov     r8d, 41h ; 'A'
0x18008c5f7  mov     rdx, rdi
0x18008c5fa  lea     rcx, [rsp+118h+var_30]
0x18008c602  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x18008c607  nop
0x18008c608  lea     r9, [rsp+118h+hKey]
0x18008c60d  lea     rdx, [rsp+118h+var_30]
0x18008c615  call    ?RegOpenKeyW@Registry@Win32Adapters@@YAXPEAUHKEY__@@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@_NAEAVRegistryHandleRAII@@@Z; Win32Adapters::Registry::RegOpenKeyW(HKEY__ *,std::wstring const &,bool,RegistryHandleRAII &)
0x18008c61a  nop
0x18008c61b  lea     rcx, [rsp+118h+var_30]
0x18008c623  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18008c628  mov     r9, rbx; unsigned int
0x18008c62b  lea     rcx, [rsp+118h+hKey]; this
0x18008c630  call    ?RegNotifyChangeKeyValue@Registry@Win32Adapters@@YAXAEAVRegistryHandleRAII@@_NKPEAX1@Z; Win32Adapters::Registry::RegNotifyChangeKeyValue(RegistryHandleRAII &,bool,ulong,void *,bool)
0x18008c635  xor     r8d, r8d; lpTimerName
0x18008c638  xor     edx, edx; bManualReset
0x18008c63a  xor     ecx, ecx; lpTimerAttributes
0x18008c63c  call    cs:__imp_CreateWaitableTimerW
0x18008c643  nop     dword ptr [rax+rax+00h]
0x18008c648  mov     rdi, rax
0x18008c64b  mov     [rsp+118h+var_A8], rax
0x18008c650  mov     [rsp+118h+Handles], rbx
0x18008c655  mov     rcx, [rsi]
0x18008c658  mov     rax, [rcx]
0x18008c65b  mov     [rsp+118h+var_D0], rax
0x18008c660  mov     [rsp+118h+var_C8], rdi
0x18008c665  mov     rax, [rcx]
0x18008c668  mov     [rsp+118h+var_C0], rax
0x18008c66d  or      r9d, 0FFFFFFFFh; dwMilliseconds
0x18008c671  xor     r8d, r8d; bWaitAll
0x18008c674  lea     rdx, [rsp+118h+Handles]; lpHandles
0x18008c679  lea     ecx, [r8+2]; nCount
0x18008c67d  call    cs:__imp_WaitForMultipleObjects
0x18008c684  nop     dword ptr [rax+rax+00h]
0x18008c689  test    eax, eax
0x18008c68b  jz      loc_18008C754
0x18008c691  cmp     eax, 1
0x18008c694  jz      short loc_18008C6BD
0x18008c696  cmp     eax, 0FFFFFFFFh
0x18008c699  jnz     short loc_18008C66D
0x18008c69b  call    cs:__imp_GetLastError
0x18008c6a2  nop     dword ptr [rax+rax+00h]
0x18008c6a7  test    eax, eax
0x18008c6a9  jle     short loc_18008C6B5
0x18008c6ab  movzx   eax, ax
0x18008c6ae  or      eax, 80070000h
0x18008c6b3  test    eax, eax
0x18008c6b5  js      loc_18008C936
0x18008c6bb  jmp     short loc_18008C66D
0x18008c6bd  lea     rax, [rdi-1]
0x18008c6c1  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18008c6c5  ja      short loc_18008C6D7
0x18008c6c7  mov     rcx, rdi; hObject
0x18008c6ca  call    cs:__imp_CloseHandle
0x18008c6d1  nop     dword ptr [rax+rax+00h]
0x18008c6d6  nop
0x18008c6d7  mov     rcx, [rsp+118h+hKey]; hKey
0x18008c6dc  test    rcx, rcx
0x18008c6df  jz      short loc_18008C6F6
0x18008c6e1  call    cs:__imp_RegCloseKey
0x18008c6e8  nop     dword ptr [rax+rax+00h]
0x18008c6ed  mov     [rsp+118h+hKey], 0
0x18008c6f6  lea     rax, [rbx-1]
0x18008c6fa  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18008c6fe  ja      short loc_18008C710
0x18008c700  mov     rcx, rbx; hObject
0x18008c703  call    cs:__imp_CloseHandle
0x18008c70a  nop     dword ptr [rax+rax+00h]
0x18008c70f  nop
0x18008c710  mov     rdi, [rsi+8]
0x18008c714  test    rdi, rdi
0x18008c717  jz      short loc_18008C74F
0x18008c719  or      ebx, 0FFFFFFFFh
0x18008c71c  mov     eax, ebx
0x18008c71e  lock xadd [rdi+8], eax
0x18008c723  add     eax, ebx
0x18008c725  jnz     short loc_18008C74F
0x18008c727  mov     rax, [rdi]
0x18008c72a  mov     rcx, rdi
0x18008c72d  mov     rax, [rax]
0x18008c730  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008c735  mov     eax, ebx
0x18008c737  lock xadd [rdi+0Ch], eax
0x18008c73c  add     eax, ebx
0x18008c73e  jnz     short loc_18008C74F
0x18008c740  mov     rax, [rdi]
0x18008c743  mov     rcx, rdi
0x18008c746  mov     rax, [rax+8]
0x18008c74a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008c74f  jmp     loc_18008C8DB
0x18008c754  xor     r9d, r9d; unsigned int
0x18008c757  mov     edx, 1F40h; void *
0x18008c75c  mov     r8d, 320h; unsigned int
0x18008c762  mov     rcx, rdi; this
0x18008c765  call    ?SetWaitableTimerEx@Synchronization@Win32Adapters@@YAXQEAXKKK@Z; Win32Adapters::Synchronization::SetWaitableTimerEx(void * const,ulong,ulong,ulong)
0x18008c76a  or      r9d, 0FFFFFFFFh; dwMilliseconds
0x18008c76e  xor     r8d, r8d; bWaitAll
0x18008c771  lea     rdx, [rsp+118h+var_C8]; lpHandles
0x18008c776  lea     ecx, [r8+2]; nCount
0x18008c77a  call    cs:__imp_WaitForMultipleObjects
0x18008c781  nop     dword ptr [rax+rax+00h]
0x18008c786  test    eax, eax
0x18008c788  jz      loc_18008C858
0x18008c78e  cmp     eax, 1
0x18008c791  jz      short loc_18008C7C1
0x18008c793  cmp     eax, 0FFFFFFFFh
0x18008c796  jnz     loc_18008C66D
0x18008c79c  call    cs:__imp_GetLastError
0x18008c7a3  nop     dword ptr [rax+rax+00h]
0x18008c7a8  test    eax, eax
0x18008c7aa  jle     short loc_18008C7B6
0x18008c7ac  movzx   eax, ax
0x18008c7af  or      eax, 80070000h
0x18008c7b4  test    eax, eax
0x18008c7b6  js      loc_18008C959
0x18008c7bc  jmp     loc_18008C66D
0x18008c7c1  lea     rax, [rdi-1]
0x18008c7c5  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18008c7c9  ja      short loc_18008C7DB
0x18008c7cb  mov     rcx, rdi; hObject
0x18008c7ce  call    cs:__imp_CloseHandle
0x18008c7d5  nop     dword ptr [rax+rax+00h]
0x18008c7da  nop
0x18008c7db  mov     rcx, [rsp+118h+hKey]; hKey
0x18008c7e0  test    rcx, rcx
0x18008c7e3  jz      short loc_18008C7FA
0x18008c7e5  call    cs:__imp_RegCloseKey
0x18008c7ec  nop     dword ptr [rax+rax+00h]
0x18008c7f1  mov     [rsp+118h+hKey], 0
0x18008c7fa  lea     rax, [rbx-1]
0x18008c7fe  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18008c802  ja      short loc_18008C814
0x18008c804  mov     rcx, rbx; hObject
0x18008c807  call    cs:__imp_CloseHandle
0x18008c80e  nop     dword ptr [rax+rax+00h]
0x18008c813  nop
0x18008c814  mov     rdi, [rsi+8]
0x18008c818  test    rdi, rdi
0x18008c81b  jz      short loc_18008C853
0x18008c81d  or      ebx, 0FFFFFFFFh
0x18008c820  mov     eax, ebx
0x18008c822  lock xadd [rdi+8], eax
0x18008c827  add     eax, ebx
0x18008c829  jnz     short loc_18008C853
0x18008c82b  mov     rax, [rdi]
0x18008c82e  mov     rcx, rdi
0x18008c831  mov     rax, [rax]
0x18008c834  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008c839  mov     eax, ebx
0x18008c83b  lock xadd [rdi+0Ch], eax
0x18008c840  add     eax, ebx
0x18008c842  jnz     short loc_18008C853
0x18008c844  mov     rax, [rdi]
0x18008c847  mov     rcx, rdi
0x18008c84a  mov     rax, [rax+8]
0x18008c84e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008c853  jmp     loc_18008C8DB
0x18008c858  mov     r9, rbx; unsigned int
0x18008c85b  lea     rcx, [rsp+118h+hKey]; this
0x18008c860  call    ?RegNotifyChangeKeyValue@Registry@Win32Adapters@@YAXAEAVRegistryHandleRAII@@_NKPEAX1@Z; Win32Adapters::Registry::RegNotifyChangeKeyValue(RegistryHandleRAII &,bool,ulong,void *,bool)
0x18008c865  mov     rcx, [rsi]
0x18008c868  mov     rcx, [rcx+8]; hEvent
0x18008c86c  call    cs:__imp_SetEvent
0x18008c873  nop     dword ptr [rax+rax+00h]
0x18008c878  jmp     loc_18008C66D
0x18008c87d  mov     r8d, dword ptr [rsp+118h+hKey]
0x18008c882  lea     rdx, aListeningToUpd; "Listening to updates for printer connec"...
0x18008c889  lea     rcx, aPrintconfigCqu; "PrintConfig::CQueueEnumerationHelper::R"...
0x18008c890  call    ?WriteDbgTraceWarning@PrintConfigTelemetry@Telemetry@Driver@Print@@SAXPEADPEAGZZ; Print::Driver::Telemetry::PrintConfigTelemetry::WriteDbgTraceWarning(char *,ushort *,...)
0x18008c895  nop
0x18008c896  mov     rax, [rsp+118h+var_E0]
0x18008c89b  mov     rdi, [rax+8]
0x18008c89f  test    rdi, rdi
0x18008c8a2  jz      short loc_18008C8DB
0x18008c8a4  or      ebx, 0FFFFFFFFh
0x18008c8a7  mov     eax, ebx
0x18008c8a9  lock xadd [rdi+8], eax
0x18008c8ae  add     eax, ebx
0x18008c8b0  jnz     short loc_18008C8DB
0x18008c8b2  mov     rax, [rdi]
0x18008c8b5  mov     rcx, rdi
0x18008c8b8  mov     rax, [rax]
0x18008c8bb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008c8c0  mov     eax, ebx
0x18008c8c2  lock xadd [rdi+0Ch], eax
0x18008c8c7  add     eax, ebx
0x18008c8c9  jnz     short loc_18008C8DB
0x18008c8cb  mov     rax, [rdi]
0x18008c8ce  mov     rcx, rdi
0x18008c8d1  mov     rax, [rax+8]
0x18008c8d5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008c8da  nop
0x18008c8db  mov     rcx, [rsp+118h+var_10]
0x18008c8e3  xor     rcx, rsp; StackCookie
0x18008c8e6  call    __security_check_cookie
0x18008c8eb  lea     r11, [rsp+118h+var_8]
0x18008c8f3  mov     rbx, [r11+18h]
0x18008c8f7  mov     rsi, [r11+20h]
0x18008c8fb  mov     rsp, r11
0x18008c8fe  pop     rdi
0x18008c8ff  retn
0x18008c901  cmp     dword ptr [rsp+118h+hKey], 0
0x18008c906  jge     short loc_18008C896
0x18008c908  jmp     loc_18008C87D
0x18008c90d  jmp     loc_18008C87D
0x18008c912  mov     edx, eax; int
0x18008c914  lea     rcx, [rsp+118h+pExceptionObject]; this
0x18008c91c  call    ??0hr_error@@QEAA@J@Z; hr_error::hr_error(long)
0x18008c921  lea     rdx, _TI2?AUhr_error@@; pThrowInfo
0x18008c928  lea     rcx, [rsp+118h+pExceptionObject]; pExceptionObject
0x18008c930  call    _CxxThrowException_0
0x18008c936  mov     edx, eax; int
0x18008c938  lea     rcx, [rsp+118h+var_70]; this
0x18008c940  call    ??0hr_error@@QEAA@J@Z; hr_error::hr_error(long)
0x18008c945  lea     rdx, _TI2?AUhr_error@@; pThrowInfo
0x18008c94c  lea     rcx, [rsp+118h+var_70]; pExceptionObject
0x18008c954  call    _CxxThrowException_0
0x18008c959  mov     edx, eax; int
0x18008c95b  lea     rcx, [rsp+118h+var_50]; this
0x18008c963  call    ??0hr_error@@QEAA@J@Z; hr_error::hr_error(long)
0x18008c968  lea     rdx, _TI2?AUhr_error@@; pThrowInfo
0x18008c96f  lea     rcx, [rsp+118h+var_50]; pExceptionObject
0x18008c977  call    _CxxThrowException_0
```
