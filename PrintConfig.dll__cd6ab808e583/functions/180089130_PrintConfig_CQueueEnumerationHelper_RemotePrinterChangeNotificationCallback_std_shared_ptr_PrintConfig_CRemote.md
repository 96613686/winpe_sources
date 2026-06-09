# PrintConfig::CQueueEnumerationHelper::RemotePrinterChangeNotificationCallback(std::shared_ptr<PrintConfig::CRemotePrinterNotificationContext>)

- ea: `0x180089130`
- end: `0x180089530`
- name: `?RemotePrinterChangeNotificationCallback@CQueueEnumerationHelper@PrintConfig@@CAXV?$shared_ptr@VCRemotePrinterNotificationContext@PrintConfig@@@std@@@Z`
- size: `1024`
- prototype: ``
- caller_count: `0`
- callee_count: `11`
- tags: `registry_config, loader_planting, installer_update, broker_com_uri`

## callees

- `0x1800032e0`
- `0x180004424`
- `0x18000da28`
- `0x18000f380`
- `0x18000f590`
- `0x1800183f8`
- `0x180036514`
- `0x180036714`
- `0x18003744c`
- `0x180089130`
- `0x1801c3010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1800891b2`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1800891b2`
- `KERNEL32!CloseHandle` at `0x1800892b6`
- `KERNEL32!CloseHandle` at `0x1800892e3`
- `KERNEL32!CloseHandle` at `0x18008939c`
- `KERNEL32!CloseHandle` at `0x1800893c9`
- `KERNEL32!CloseHandle` at `0x1800892b6`
- `KERNEL32!CloseHandle` at `0x1800892e3`
- `KERNEL32!CloseHandle` at `0x18008939c`
- `KERNEL32!CloseHandle` at `0x1800893c9`
- `KERNEL32!GetLastError` at `0x18008918b`
- `KERNEL32!GetLastError` at `0x18008928d`
- `KERNEL32!GetLastError` at `0x180089370`
- `KERNEL32!GetLastError` at `0x18008918b`
- `KERNEL32!GetLastError` at `0x18008928d`
- `KERNEL32!GetLastError` at `0x180089370`
- `KERNEL32!SetEvent` at `0x180089425`
- `KERNEL32!SetEvent` at `0x180089425`
- `KERNEL32!CreateEventW` at `0x180089172`
- `KERNEL32!CreateEventW` at `0x180089172`
- `KERNEL32!CreateWaitableTimerW` at `0x18008923a`
- `KERNEL32!CreateWaitableTimerW` at `0x18008923a`
- `KERNEL32!WaitForMultipleObjects` at `0x180089275`
- `KERNEL32!WaitForMultipleObjects` at `0x180089354`
- `KERNEL32!WaitForMultipleObjects` at `0x180089275`
- `KERNEL32!WaitForMultipleObjects` at `0x180089354`
- `ADVAPI32!RegCloseKey` at `0x1800892c7`
- `ADVAPI32!RegCloseKey` at `0x1800893ad`
- `ADVAPI32!RegCloseKey` at `0x1800892c7`
- `ADVAPI32!RegCloseKey` at `0x1800893ad`

## string_xrefs

- `0x1800891bc`: `Registry location for v4 connection cache appears to have changed. Enumerating remote printers may not function properly.`
- `0x1800891c3`: `PrintConfig::CQueueEnumerationHelper::RemotePrinterChangeNotificationCallback`
- `0x18008943c`: `PrintConfig::CQueueEnumerationHelper::RemotePrinterChangeNotificationCallback`
- `0x180089435`: `Listening to updates for printer connections in registry failed: 0x%x`

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
  bool v8; // r8
  char *WaitableTimerW; // rdi
  HANDLE *v10; // rcx
  DWORD v11; // eax
  signed int v12; // eax
  bool v13; // sf
  signed __int32 result; // eax
  volatile signed __int32 *v15; // rdi
  DWORD v16; // eax
  struct RegistryHandleRAII *v17; // rdx
  bool v18; // r8
  signed int v19; // eax
  bool v20; // sf
  volatile signed __int32 *v21; // rdi
  void *v22; // [rsp+20h] [rbp-F8h]
  void *v23; // [rsp+20h] [rbp-F8h]
  bool v24; // [rsp+28h] [rbp-F0h]
  bool v25; // [rsp+28h] [rbp-F0h]
  HKEY hKey[2]; // [rsp+30h] [rbp-E8h] BYREF
  HANDLE Handles[2]; // [rsp+40h] [rbp-D8h] BYREF
  HANDLE v28[7]; // [rsp+50h] [rbp-C8h] BYREF
  _BYTE pExceptionObject[32]; // [rsp+88h] [rbp-90h] BYREF
  _BYTE v30[32]; // [rsp+A8h] [rbp-70h] BYREF
  _BYTE v31[32]; // [rsp+C8h] [rbp-50h] BYREF
  _OWORD v32[2]; // [rsp+E8h] [rbp-30h] BYREF

  v28[2] = (HANDLE)-2LL;
  hKey[1] = a1;
  EventW = (char *)CreateEventW(0, 1, 0, 0);
  v28[3] = EventW;
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
  memset(v32, 0, sizeof(v32));
  std::wstring::_Construct<1,unsigned short const *>(
    (char **)v32,
    L"SOFTWARE\\Microsoft\\Windows NT\\CurrentVersion\\Print\\V4 Connections",
    0x41u);
  Win32Adapters::Registry::RegOpenKeyW(v5, v32, v6, hKey);
  std::wstring::~wstring(v32);
  Win32Adapters::Registry::RegNotifyChangeKeyValue(
    (Win32Adapters::Registry *)hKey,
    v7,
    v8,
    (unsigned int)EventW,
    v22,
    v24);
  WaitableTimerW = (char *)CreateWaitableTimerW(0, 0, 0);
  v28[4] = WaitableTimerW;
  Handles[0] = EventW;
  v10 = *(HANDLE **)a1;
  Handles[1] = **(HANDLE **)a1;
  v28[0] = WaitableTimerW;
  v28[1] = *v10;
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
            hr_error::hr_error((hr_error *)v30, v12);
            throw (hr_error *)v30;
          }
        }
      }
      Win32Adapters::Synchronization::SetWaitableTimerEx(
        (Win32Adapters::Synchronization *)WaitableTimerW,
        (void *const)0x1F40,
        0x320u,
        0,
        (unsigned int)v23);
      v16 = WaitForMultipleObjects(2u, v28, 0, 0xFFFFFFFF);
      if ( v16 )
        break;
      Win32Adapters::Registry::RegNotifyChangeKeyValue(
        (Win32Adapters::Registry *)hKey,
        v17,
        v18,
        (unsigned int)EventW,
        v23,
        v25);
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
        hr_error::hr_error((hr_error *)v31, v19);
        throw (hr_error *)v31;
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
0x180089130  mov     rax, rsp
0x180089133  push    rdi
0x180089134  sub     rsp, 110h
0x18008913b  mov     [rsp+118h+var_B8], 0FFFFFFFFFFFFFFFEh
0x180089144  mov     [rax+10h], rbx
0x180089148  mov     [rax+18h], rsi
0x18008914c  mov     rax, cs:__security_cookie
0x180089153  xor     rax, rsp
0x180089156  mov     [rsp+118h+var_10], rax
0x18008915e  mov     rsi, rcx
0x180089161  mov     [rsp+118h+var_E0], rcx
0x180089166  xor     r9d, r9d; lpName
0x180089169  xor     r8d, r8d; bInitialState
0x18008916c  lea     edx, [r9+1]; bManualReset
0x180089170  xor     ecx, ecx; lpEventAttributes
0x180089172  call    cs:__imp_CreateEventW
0x180089178  mov     rbx, rax
0x18008917b  mov     [rsp+118h+var_B0], rax
0x180089180  inc     rax
0x180089183  test    rax, 0FFFFFFFFFFFFFFFEh
0x180089189  jnz     short loc_1800891A5
0x18008918b  call    cs:__imp_GetLastError
0x180089191  test    eax, eax
0x180089193  jle     short loc_18008919F
0x180089195  movzx   eax, ax
0x180089198  or      eax, 80070000h
0x18008919d  test    eax, eax
0x18008919f  js      loc_1800894C4
0x1800891a5  lea     rdi, aSoftwareMicros; "SOFTWARE\\Microsoft\\Windows NT\\Curren"...
0x1800891ac  mov     rdx, rdi
0x1800891af  mov     rcx, rdi
0x1800891b2  call    cs:__imp__o__wcsicmp
0x1800891b8  test    eax, eax
0x1800891ba  jz      short loc_1800891CF
0x1800891bc  lea     rdx, aRegistryLocati; "Registry location for v4 connection cac"...
0x1800891c3  lea     rcx, aPrintconfigCqu; "PrintConfig::CQueueEnumerationHelper::R"...
0x1800891ca  call    ?WriteDbgTraceWarning@PrintConfigTelemetry@Telemetry@Driver@Print@@SAXPEADPEAGZZ; Print::Driver::Telemetry::PrintConfigTelemetry::WriteDbgTraceWarning(char *,ushort *,...)
0x1800891cf  mov     [rsp+118h+hKey], 0
0x1800891d8  xorps   xmm0, xmm0
0x1800891db  movups  [rsp+118h+var_30], xmm0
0x1800891e3  xorps   xmm1, xmm1
0x1800891e6  movdqu  [rsp+118h+var_20], xmm1
0x1800891ef  mov     r8d, 41h ; 'A'
0x1800891f5  mov     rdx, rdi
0x1800891f8  lea     rcx, [rsp+118h+var_30]
0x180089200  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x180089205  nop
0x180089206  lea     r9, [rsp+118h+hKey]
0x18008920b  lea     rdx, [rsp+118h+var_30]
0x180089213  call    ?RegOpenKeyW@Registry@Win32Adapters@@YAXPEAUHKEY__@@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@_NAEAVRegistryHandleRAII@@@Z; Win32Adapters::Registry::RegOpenKeyW(HKEY__ *,std::wstring const &,bool,RegistryHandleRAII &)
0x180089218  nop
0x180089219  lea     rcx, [rsp+118h+var_30]
0x180089221  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180089226  mov     r9, rbx; unsigned int
0x180089229  lea     rcx, [rsp+118h+hKey]; this
0x18008922e  call    ?RegNotifyChangeKeyValue@Registry@Win32Adapters@@YAXAEAVRegistryHandleRAII@@_NKPEAX1@Z; Win32Adapters::Registry::RegNotifyChangeKeyValue(RegistryHandleRAII &,bool,ulong,void *,bool)
0x180089233  xor     r8d, r8d; lpTimerName
0x180089236  xor     edx, edx; bManualReset
0x180089238  xor     ecx, ecx; lpTimerAttributes
0x18008923a  call    cs:__imp_CreateWaitableTimerW
0x180089240  mov     rdi, rax
0x180089243  mov     [rsp+118h+var_A8], rax
0x180089248  mov     [rsp+118h+Handles], rbx
0x18008924d  mov     rcx, [rsi]
0x180089250  mov     rax, [rcx]
0x180089253  mov     [rsp+118h+var_D0], rax
0x180089258  mov     [rsp+118h+var_C8], rdi
0x18008925d  mov     rax, [rcx]
0x180089260  mov     [rsp+118h+var_C0], rax
0x180089265  or      r9d, 0FFFFFFFFh; dwMilliseconds
0x180089269  xor     r8d, r8d; bWaitAll
0x18008926c  lea     rdx, [rsp+118h+Handles]; lpHandles
0x180089271  lea     ecx, [r8+2]; nCount
0x180089275  call    cs:__imp_WaitForMultipleObjects
0x18008927b  test    eax, eax
0x18008927d  jz      loc_18008932E
0x180089283  cmp     eax, 1
0x180089286  jz      short loc_1800892A9
0x180089288  cmp     eax, 0FFFFFFFFh
0x18008928b  jnz     short loc_180089265
0x18008928d  call    cs:__imp_GetLastError
0x180089293  test    eax, eax
0x180089295  jle     short loc_1800892A1
0x180089297  movzx   eax, ax
0x18008929a  or      eax, 80070000h
0x18008929f  test    eax, eax
0x1800892a1  js      loc_1800894E8
0x1800892a7  jmp     short loc_180089265
0x1800892a9  lea     rax, [rdi-1]
0x1800892ad  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x1800892b1  ja      short loc_1800892BD
0x1800892b3  mov     rcx, rdi; hObject
0x1800892b6  call    cs:__imp_CloseHandle
0x1800892bc  nop
0x1800892bd  mov     rcx, [rsp+118h+hKey]; hKey
0x1800892c2  test    rcx, rcx
0x1800892c5  jz      short loc_1800892D6
0x1800892c7  call    cs:__imp_RegCloseKey
0x1800892cd  mov     [rsp+118h+hKey], 0
0x1800892d6  lea     rax, [rbx-1]
0x1800892da  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x1800892de  ja      short loc_1800892EA
0x1800892e0  mov     rcx, rbx; hObject
0x1800892e3  call    cs:__imp_CloseHandle
0x1800892e9  nop
0x1800892ea  mov     rdi, [rsi+8]
0x1800892ee  test    rdi, rdi
0x1800892f1  jz      short loc_180089329
0x1800892f3  or      ebx, 0FFFFFFFFh
0x1800892f6  mov     eax, ebx
0x1800892f8  lock xadd [rdi+8], eax
0x1800892fd  add     eax, ebx
0x1800892ff  jnz     short loc_180089329
0x180089301  mov     rax, [rdi]
0x180089304  mov     rcx, rdi
0x180089307  mov     rax, [rax]
0x18008930a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008930f  mov     eax, ebx
0x180089311  lock xadd [rdi+0Ch], eax
0x180089316  add     eax, ebx
0x180089318  jnz     short loc_180089329
0x18008931a  mov     rax, [rdi]
0x18008931d  mov     rcx, rdi
0x180089320  mov     rax, [rax+8]
0x180089324  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180089329  jmp     loc_18008948E
0x18008932e  xor     r9d, r9d; unsigned int
0x180089331  mov     edx, 1F40h; void *
0x180089336  mov     r8d, 320h; unsigned int
0x18008933c  mov     rcx, rdi; this
0x18008933f  call    ?SetWaitableTimerEx@Synchronization@Win32Adapters@@YAXQEAXKKK@Z; Win32Adapters::Synchronization::SetWaitableTimerEx(void * const,ulong,ulong,ulong)
0x180089344  or      r9d, 0FFFFFFFFh; dwMilliseconds
0x180089348  xor     r8d, r8d; bWaitAll
0x18008934b  lea     rdx, [rsp+118h+var_C8]; lpHandles
0x180089350  lea     ecx, [r8+2]; nCount
0x180089354  call    cs:__imp_WaitForMultipleObjects
0x18008935a  test    eax, eax
0x18008935c  jz      loc_180089411
0x180089362  cmp     eax, 1
0x180089365  jz      short loc_18008938F
0x180089367  cmp     eax, 0FFFFFFFFh
0x18008936a  jnz     loc_180089265
0x180089370  call    cs:__imp_GetLastError
0x180089376  test    eax, eax
0x180089378  jle     short loc_180089384
0x18008937a  movzx   eax, ax
0x18008937d  or      eax, 80070000h
0x180089382  test    eax, eax
0x180089384  js      loc_18008950B
0x18008938a  jmp     loc_180089265
0x18008938f  lea     rax, [rdi-1]
0x180089393  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x180089397  ja      short loc_1800893A3
0x180089399  mov     rcx, rdi; hObject
0x18008939c  call    cs:__imp_CloseHandle
0x1800893a2  nop
0x1800893a3  mov     rcx, [rsp+118h+hKey]; hKey
0x1800893a8  test    rcx, rcx
0x1800893ab  jz      short loc_1800893BC
0x1800893ad  call    cs:__imp_RegCloseKey
0x1800893b3  mov     [rsp+118h+hKey], 0
0x1800893bc  lea     rax, [rbx-1]
0x1800893c0  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x1800893c4  ja      short loc_1800893D0
0x1800893c6  mov     rcx, rbx; hObject
0x1800893c9  call    cs:__imp_CloseHandle
0x1800893cf  nop
0x1800893d0  mov     rdi, [rsi+8]
0x1800893d4  test    rdi, rdi
0x1800893d7  jz      short loc_18008940F
0x1800893d9  or      ebx, 0FFFFFFFFh
0x1800893dc  mov     eax, ebx
0x1800893de  lock xadd [rdi+8], eax
0x1800893e3  add     eax, ebx
0x1800893e5  jnz     short loc_18008940F
0x1800893e7  mov     rax, [rdi]
0x1800893ea  mov     rcx, rdi
0x1800893ed  mov     rax, [rax]
0x1800893f0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800893f5  mov     eax, ebx
0x1800893f7  lock xadd [rdi+0Ch], eax
0x1800893fc  add     eax, ebx
0x1800893fe  jnz     short loc_18008940F
0x180089400  mov     rax, [rdi]
0x180089403  mov     rcx, rdi
0x180089406  mov     rax, [rax+8]
0x18008940a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008940f  jmp     short loc_18008948E
0x180089411  mov     r9, rbx; unsigned int
0x180089414  lea     rcx, [rsp+118h+hKey]; this
0x180089419  call    ?RegNotifyChangeKeyValue@Registry@Win32Adapters@@YAXAEAVRegistryHandleRAII@@_NKPEAX1@Z; Win32Adapters::Registry::RegNotifyChangeKeyValue(RegistryHandleRAII &,bool,ulong,void *,bool)
0x18008941e  mov     rcx, [rsi]
0x180089421  mov     rcx, [rcx+8]; hEvent
0x180089425  call    cs:__imp_SetEvent
0x18008942b  jmp     loc_180089265
0x180089430  mov     r8d, dword ptr [rsp+118h+hKey]
0x180089435  lea     rdx, aListeningToUpd; "Listening to updates for printer connec"...
0x18008943c  lea     rcx, aPrintconfigCqu; "PrintConfig::CQueueEnumerationHelper::R"...
0x180089443  call    ?WriteDbgTraceWarning@PrintConfigTelemetry@Telemetry@Driver@Print@@SAXPEADPEAGZZ; Print::Driver::Telemetry::PrintConfigTelemetry::WriteDbgTraceWarning(char *,ushort *,...)
0x180089448  nop
0x180089449  mov     rax, [rsp+118h+var_E0]
0x18008944e  mov     rdi, [rax+8]
0x180089452  test    rdi, rdi
0x180089455  jz      short loc_18008948E
0x180089457  or      ebx, 0FFFFFFFFh
0x18008945a  mov     eax, ebx
0x18008945c  lock xadd [rdi+8], eax
0x180089461  add     eax, ebx
0x180089463  jnz     short loc_18008948E
0x180089465  mov     rax, [rdi]
0x180089468  mov     rcx, rdi
0x18008946b  mov     rax, [rax]
0x18008946e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180089473  mov     eax, ebx
0x180089475  lock xadd [rdi+0Ch], eax
0x18008947a  add     eax, ebx
0x18008947c  jnz     short loc_18008948E
0x18008947e  mov     rax, [rdi]
0x180089481  mov     rcx, rdi
0x180089484  mov     rax, [rax+8]
0x180089488  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008948d  nop
0x18008948e  mov     rcx, [rsp+118h+var_10]
0x180089496  xor     rcx, rsp; StackCookie
0x180089499  call    __security_check_cookie
0x18008949e  lea     r11, [rsp+118h+var_8]
0x1800894a6  mov     rbx, [r11+18h]
0x1800894aa  mov     rsi, [r11+20h]
0x1800894ae  mov     rsp, r11
0x1800894b1  pop     rdi
0x1800894b2  retn
0x1800894b3  cmp     dword ptr [rsp+118h+hKey], 0
0x1800894b8  jge     short loc_180089449
0x1800894ba  jmp     loc_180089430
0x1800894bf  jmp     loc_180089430
0x1800894c4  mov     edx, eax; int
0x1800894c6  lea     rcx, [rsp+118h+pExceptionObject]; this
0x1800894ce  call    ??0hr_error@@QEAA@J@Z; hr_error::hr_error(long)
0x1800894d3  lea     rdx, _TI2?AUhr_error@@; pThrowInfo
0x1800894da  lea     rcx, [rsp+118h+pExceptionObject]; pExceptionObject
0x1800894e2  call    _CxxThrowException_0
0x1800894e8  mov     edx, eax; int
0x1800894ea  lea     rcx, [rsp+118h+var_70]; this
0x1800894f2  call    ??0hr_error@@QEAA@J@Z; hr_error::hr_error(long)
0x1800894f7  lea     rdx, _TI2?AUhr_error@@; pThrowInfo
0x1800894fe  lea     rcx, [rsp+118h+var_70]; pExceptionObject
0x180089506  call    _CxxThrowException_0
0x18008950b  mov     edx, eax; int
0x18008950d  lea     rcx, [rsp+118h+var_50]; this
0x180089515  call    ??0hr_error@@QEAA@J@Z; hr_error::hr_error(long)
0x18008951a  lea     rdx, _TI2?AUhr_error@@; pThrowInfo
0x180089521  lea     rcx, [rsp+118h+var_50]; pExceptionObject
0x180089529  call    _CxxThrowException_0
```
