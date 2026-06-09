# WSManHttpSenderConnection::NotifyClientThread(void)

- ea: `0x1800177cc`
- end: `0x180017e4f`
- name: `?NotifyClientThread@WSManHttpSenderConnection@@AEAAXXZ`
- size: `1667`
- prototype: `void __fastcall(WSManHttpSenderConnection *__hidden this)`
- caller_count: `1`
- callee_count: `13`
- tags: `authz_impersonation, loader_planting, service_task, broker_com_uri`

## callers

- `0x180016080`

## callees

- `0x180005d10`
- `0x1800166a0`
- `0x1800177cc`
- `0x180017e60`
- `0x18002c580`
- `0x1800520d0`
- `0x18006f9a0`
- `0x18007ec20`
- `0x180080980`
- `0x180112380`
- `0x18011349c`
- `0x18011a6d4`
- `0x1801c2010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800178a6`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180017925`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180017ae3`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180017af1`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180017b75`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180017ba5`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180017bd9`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800178a6`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180017925`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180017ae3`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180017af1`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180017b75`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180017ba5`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180017bd9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180017826`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800178b5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180017de4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180017826`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800178b5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180017de4`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180017a4c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180017a4c`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180017808`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180017808`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180017a83`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180017a83`
- `api-ms-win-core-processthreads-l1-1-0!ExitProcess` at `0x180017e2a`
- `api-ms-win-core-processthreads-l1-1-0!ExitProcess` at `0x180017e2a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180017985`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180017985`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x1800179ba`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x180017a18`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x1800179ba`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x180017a18`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18001799b`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18001799b`
- `api-ms-win-core-synch-l1-2-0!WakeAllConditionVariable` at `0x180017a6b`
- `api-ms-win-core-synch-l1-2-0!WakeAllConditionVariable` at `0x180017a6b`
- `ntdll!EtwEventProviderEnabled` at `0x180017899`
- `ntdll!EtwEventProviderEnabled` at `0x180017899`
- `ntdll!EtwEventEnabled` at `0x180017918`
- `ntdll!EtwEventEnabled` at `0x180017918`

## string_xrefs

- `0x180017b92`: `onecore\admin\wmi\wmx\binaries\service\cwsmancriticalsection.cpp`
- `0x180017bc6`: `onecore\admin\wmi\wmx\binaries\service\cwsmancriticalsection.cpp`
- `0x180017ca6`: `@Notify(OperationCompleted3)`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
void __fastcall WSManHttpSenderConnection::NotifyClientThread(WSManHttpSenderConnection *this)
{
  char *v2; // rcx
  DWORD LastError; // esi
  bool v4; // bl
  DWORD v5; // esi
  bool v6; // bl
  PVOID *v7; // rcx
  char *v8; // rbx
  char v9; // r12
  HANDLE CurrentThread; // rax
  unsigned int v11; // r13d
  unsigned int v12; // eax
  char *v13; // [rsp+30h] [rbp-39h] BYREF
  int v14; // [rsp+38h] [rbp-31h]
  void **v15; // [rsp+40h] [rbp-29h] BYREF
  signed __int32 v16; // [rsp+48h] [rbp-21h] BYREF
  int v17; // [rsp+50h] [rbp-19h]
  int v18; // [rsp+54h] [rbp-15h]
  char v19; // [rsp+58h] [rbp-11h]
  const wchar_t *v20; // [rsp+60h] [rbp-9h]
  const wchar_t *v21; // [rsp+68h] [rbp-1h]
  const wchar_t *v22; // [rsp+70h] [rbp+7h]
  const wchar_t *v23; // [rsp+78h] [rbp+Fh]
  void *TokenHandle; // [rsp+D0h] [rbp+67h] BYREF

  v2 = (char *)this + 9184;
  v13 = v2;
  v14 = 0;
  if ( *(_DWORD *)v2 )
  {
    SetLastError(*(_DWORD *)v2);
    WSManError(
      (wchar_t *)L"onecore\\admin\\wmi\\wmx\\binaries\\service\\cwsmancriticalsection.cpp",
      59,
      L"59",
      0x54Fu,
      0);
  }
  else
  {
    EnterCriticalSection((LPCRITICAL_SECTION)(v2 + 8));
  }
  if ( *((_BYTE *)this + 11360) )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400) != 0 )
      WPP_SF_qq(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        314,
        &WPP_1a71944546983a3ae75b6cead512f96f_Traceguids,
        this,
        *((_QWORD *)this + 1141));
    *((_BYTE *)this + 11365) = 0;
    InCritSecWithConditionVar::Release((InCritSecWithConditionVar *)&v13);
    (*(void (__fastcall **)(WSManHttpSenderConnection *, const char *))(*(_QWORD *)this + 112LL))(
      this,
      "@Notify(OperationCompleted3)");
    InCritSecWithConditionVar::~InCritSecWithConditionVar((InCritSecWithConditionVar *)&v13);
  }
  else
  {
    if ( !*((_QWORD *)this + 1) )
      WSManError((wchar_t *)L"onecore\\admin\\wmi\\wmx\\client\\remote\\wsmanhttpsender.cpp", 5880, L"5880", 0x54Fu, 0);
    LastError = GetLastError();
    v16 = 0;
    v15 = &CErrorContext::`vftable';
    v17 = 0;
    v18 = -1;
    v20 = &Class;
    v21 = &Class;
    v22 = &Class;
    v23 = &Class;
    v19 = 1;
    _InterlockedIncrement(&v16);
    if ( !g_eventHandler )
      ILoader<WSMan::EventHandler>::CreateInstance(&g_eventHandler, &v15);
    if ( g_eventHandler )
    {
      if ( *(_QWORD *)g_eventHandler )
      {
        v4 = (unsigned __int8)EtwEventProviderEnabled(*(_QWORD *)g_eventHandler, 0, 0) != 0;
      }
      else
      {
        WSManError((wchar_t *)L"onecore\\admin\\wmi\\wmx\\stdlib\\wsmaneventhandler.cpp", 624, L"624", 0x54Fu, 0);
        v4 = 0;
      }
      SetLastError(LastError);
      if ( v4 )
        WSMan::EventHandler::EnsureActivityIdOnThread();
    }
    else
    {
      SetLastError(LastError);
    }
    v5 = GetLastError();
    v16 = 0;
    v15 = &CErrorContext::`vftable';
    v17 = 0;
    v18 = -1;
    v20 = &Class;
    v21 = &Class;
    v22 = &Class;
    v23 = &Class;
    v19 = 0;
    _InterlockedIncrement(&v16);
    if ( !g_eventHandler )
      ILoader<WSMan::EventHandler>::CreateInstance(&g_eventHandler, &v15);
    if ( g_eventHandler )
    {
      if ( *(_QWORD *)g_eventHandler )
      {
        v6 = (unsigned __int8)EtwEventEnabled(*(_QWORD *)g_eventHandler, &LOG_WSMAN_AN_TRANSFER_EVENT) != 0;
      }
      else
      {
        WSManError((wchar_t *)L"onecore\\admin\\wmi\\wmx\\stdlib\\wsmaneventhandler.cpp", 644, L"644", 0x54Fu, 0);
        v6 = 0;
      }
      SetLastError(v5);
      if ( v6 )
        WSMan::EventHandler::GenerateTransferId(
          &LOG_WSMAN_AN_TRANSFER_EVENT,
          (const struct _GUID *)((char *)this + 11452),
          0);
    }
    else
    {
      SetLastError(v5);
    }
    v7 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400) != 0 )
    {
      WPP_SF_qq(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        315,
        &WPP_1a71944546983a3ae75b6cead512f96f_Traceguids,
        this,
        *((_QWORD *)this + 1));
      v7 = (PVOID *)WPP_GLOBAL_Control;
    }
    v8 = 0;
    TokenHandle = 0;
    v9 = 0;
    if ( *((_QWORD *)this + 1427) )
    {
      if ( v7 != &WPP_GLOBAL_Control && (*((_DWORD *)v7 + 7) & 0x400) != 0 )
        WPP_SF_q(v7[2], 458, &WPP_1a71944546983a3ae75b6cead512f96f_Traceguids, this);
      if ( !*((_QWORD *)this + 1427) )
        WSManError(
          (wchar_t *)L"onecore\\admin\\wmi\\wmx\\client\\remote\\wsmanhttpsender.cpp",
          8700,
          L"8700",
          0x54Fu,
          0);
      TokenHandle = 0;
      CurrentThread = GetCurrentThread();
      if ( !OpenThreadToken(CurrentThread, 4u, 1, &TokenHandle)
        && WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x10000000) != 0 )
      {
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 18, WPP_5b789da118f632ad9796e014c1252c4d_Traceguids);
      }
      v8 = (char *)TokenHandle;
      if ( SetThreadToken(0, *((HANDLE *)this + 1427)) )
      {
        v9 = 1;
      }
      else
      {
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400) != 0 )
          WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 459, &WPP_1a71944546983a3ae75b6cead512f96f_Traceguids);
        *((_DWORD *)this + 2279) = GetLastError();
        *((_DWORD *)this + 2280) = 2;
        v9 = 0;
      }
      v7 = (PVOID *)WPP_GLOBAL_Control;
    }
    if ( !*((_DWORD *)this + 2279) && *((_QWORD *)this + 1) && !*((_QWORD *)this + 1145) )
    {
      v12 = WSManHttpSenderConnection::ProcessFinalResponsePacket(this);
      *((_DWORD *)this + 2279) = v12;
      *((_DWORD *)this + 2280) = v12 != 0 ? 2 : 0;
      v7 = (PVOID *)WPP_GLOBAL_Control;
    }
    v11 = *((_DWORD *)this + 2278);
    if ( v7 != &WPP_GLOBAL_Control && (*((_DWORD *)v7 + 7) & 0x400) != 0 )
      WPP_SF_qq(v7[2], 317, &WPP_1a71944546983a3ae75b6cead512f96f_Traceguids, this, *((_QWORD *)this + 1));
    WSManHttpSenderConnection::OperationCompleted(this, &v13, v11);
    if ( v9 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400) != 0 )
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 460, &WPP_1a71944546983a3ae75b6cead512f96f_Traceguids);
      if ( !SetThreadToken(0, v8) )
      {
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400) != 0 )
          WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 461, &WPP_1a71944546983a3ae75b6cead512f96f_Traceguids);
        ExitProcess(0x1Fu);
      }
    }
    if ( (unsigned __int64)(v8 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x1000000) != 0 )
        WPP_SF_q(*((_QWORD *)WPP_GLOBAL_Control + 2), 12, WPP_4bcfcb6bc4c53d70488bc6bf4d078fb8_Traceguids, v8);
      CloseHandle(v8);
    }
    if ( !v14 )
    {
      if ( *(_DWORD *)v13 )
      {
        SetLastError(*(_DWORD *)v13);
        WSManError(
          (wchar_t *)L"onecore\\admin\\wmi\\wmx\\binaries\\service\\cwsmancriticalsection.cpp",
          102,
          L"102",
          0x54Fu,
          0);
      }
      else
      {
        WakeAllConditionVariable((PCONDITION_VARIABLE)v13 + 6);
      }
      if ( *(_DWORD *)v13 )
        SetLastError(*(_DWORD *)v13);
      else
        LeaveCriticalSection((LPCRITICAL_SECTION)(v13 + 8));
    }
  }
}

```

## disassembly

```asm
0x1800177cc  push    rbp
0x1800177ce  push    rbx
0x1800177cf  push    rsi
0x1800177d0  push    rdi
0x1800177d1  push    r12
0x1800177d3  push    r13
0x1800177d5  push    r14
0x1800177d7  push    r15
0x1800177d9  lea     rbp, [rsp-1Fh]
0x1800177de  sub     rsp, 88h
0x1800177e5  mov     rdi, rcx
0x1800177e8  add     rcx, 23E0h
0x1800177ef  mov     [rbp+57h+var_90], rcx
0x1800177f3  xor     r13d, r13d
0x1800177f6  mov     [rbp+57h+var_88], r13d
0x1800177fa  mov     eax, [rcx]
0x1800177fc  test    eax, eax
0x1800177fe  jnz     loc_180017B73
0x180017804  add     rcx, 8; lpCriticalSection
0x180017808  call    cs:__imp_EnterCriticalSection
0x18001780e  nop
0x18001780f  cmp     [rdi+2C60h], r13b
0x180017816  jnz     loc_180017C7C
0x18001781c  cmp     [rdi+8], r13
0x180017820  jz      loc_180017D56
0x180017826  call    cs:__imp_GetLastError
0x18001782c  mov     esi, eax
0x18001782e  mov     [rbp+57h+var_78], r13d
0x180017832  lea     r15, ??_7CErrorContext@@6B@; const CErrorContext::`vftable'
0x180017839  mov     [rbp+57h+var_80], r15
0x18001783d  mov     [rbp+57h+var_70], r13d
0x180017841  or      r12d, 0FFFFFFFFh
0x180017845  mov     [rbp+57h+var_6C], r12d
0x180017849  lea     r14, Class
0x180017850  mov     [rbp+57h+var_60], r14
0x180017854  mov     [rbp+57h+var_58], r14
0x180017858  mov     [rbp+57h+var_50], r14
0x18001785c  mov     [rbp+57h+var_48], r14
0x180017860  mov     [rbp+57h+var_68], 1
0x180017864  lock inc [rbp+57h+var_78]
0x180017868  mov     rax, cs:?g_eventHandler@@3V?$Loader@VEventHandler@WSMan@@$00@@A; Loader<WSMan::EventHandler,1> g_eventHandler
0x18001786f  test    rax, rax
0x180017872  jz      loc_180017CF3
0x180017878  mov     rax, cs:?g_eventHandler@@3V?$Loader@VEventHandler@WSMan@@$00@@A; Loader<WSMan::EventHandler,1> g_eventHandler
0x18001787f  test    rax, rax
0x180017882  jz      loc_180017AEF
0x180017888  mov     rcx, [rax]
0x18001788b  test    rcx, rcx
0x18001788e  jz      loc_180017CC8
0x180017894  xor     r8d, r8d
0x180017897  xor     edx, edx
0x180017899  call    cs:__imp_EtwEventProviderEnabled
0x18001789f  test    al, al
0x1800178a1  setnz   bl
0x1800178a4  mov     ecx, esi; dwErrCode
0x1800178a6  call    cs:__imp_SetLastError
0x1800178ac  nop
0x1800178ad  test    bl, bl
0x1800178af  jnz     loc_180017C47
0x1800178b5  call    cs:__imp_GetLastError
0x1800178bb  mov     esi, eax
0x1800178bd  mov     [rbp+57h+var_78], r13d
0x1800178c1  mov     [rbp+57h+var_80], r15
0x1800178c5  mov     [rbp+57h+var_70], r13d
0x1800178c9  mov     [rbp+57h+var_6C], r12d
0x1800178cd  mov     [rbp+57h+var_60], r14
0x1800178d1  mov     [rbp+57h+var_58], r14
0x1800178d5  mov     [rbp+57h+var_50], r14
0x1800178d9  mov     [rbp+57h+var_48], r14
0x1800178dd  mov     [rbp+57h+var_68], r13b
0x1800178e1  lock inc [rbp+57h+var_78]
0x1800178e5  mov     rdx, cs:?g_eventHandler@@3V?$Loader@VEventHandler@WSMan@@$00@@A; Loader<WSMan::EventHandler,1> g_eventHandler
0x1800178ec  test    rdx, rdx
0x1800178ef  jz      loc_180017D08
0x1800178f5  mov     rax, cs:?g_eventHandler@@3V?$Loader@VEventHandler@WSMan@@$00@@A; Loader<WSMan::EventHandler,1> g_eventHandler
0x1800178fc  test    rax, rax
0x1800178ff  jz      loc_180017AE1
0x180017905  mov     rcx, [rax]
0x180017908  test    rcx, rcx
0x18001790b  jz      loc_180017C51
0x180017911  lea     rdx, LOG_WSMAN_AN_TRANSFER_EVENT
0x180017918  call    cs:__imp_EtwEventEnabled
0x18001791e  test    al, al
0x180017920  setnz   bl
0x180017923  mov     ecx, esi; dwErrCode
0x180017925  call    cs:__imp_SetLastError
0x18001792b  nop
0x18001792c  test    bl, bl
0x18001792e  jnz     loc_180017D7E
0x180017934  lea     rsi, WPP_GLOBAL_Control
0x18001793b  mov     r14d, 400h
0x180017941  lea     r15, WPP_1a71944546983a3ae75b6cead512f96f_Traceguids
0x180017948  mov     rcx, cs:WPP_GLOBAL_Control
0x18001794f  cmp     rcx, rsi
0x180017952  jnz     loc_180017B20
0x180017958  mov     rbx, r13
0x18001795b  mov     [rbp+57h+TokenHandle], rbx
0x18001795f  mov     r12b, r13b
0x180017962  cmp     [rdi+2C98h], r13
0x180017969  jz      short loc_1800179D2
0x18001796b  cmp     rcx, rsi
0x18001796e  jnz     loc_180017AFD
0x180017974  cmp     [rdi+2C98h], r13
0x18001797b  jz      loc_180017D99
0x180017981  mov     [rbp+57h+TokenHandle], r13
0x180017985  call    cs:__imp_GetCurrentThread
0x18001798b  mov     rcx, rax; ThreadHandle
0x18001798e  lea     r9, [rbp+57h+TokenHandle]; TokenHandle
0x180017992  mov     edx, 4; DesiredAccess
0x180017997  lea     r8d, [rdx-3]; OpenAsSelf
0x18001799b  call    cs:__imp_OpenThreadToken
0x1800179a1  test    eax, eax
0x1800179a3  jz      loc_180017C10
0x1800179a9  mov     rbx, [rbp+57h+TokenHandle]
0x1800179ad  mov     [rbp+57h+TokenHandle], rbx
0x1800179b1  mov     rdx, [rdi+2C98h]; Token
0x1800179b8  xor     ecx, ecx; Thread
0x1800179ba  call    cs:__imp_SetThreadToken
0x1800179c0  test    eax, eax
0x1800179c2  jz      loc_180017DC1
0x1800179c8  mov     r12b, 1
0x1800179cb  mov     rcx, cs:WPP_GLOBAL_Control
0x1800179d2  cmp     [rdi+239Ch], r13d
0x1800179d9  jz      loc_180017A9E
0x1800179df  mov     r13d, [rdi+2398h]
0x1800179e6  cmp     rcx, rsi
0x1800179e9  jnz     loc_180017BE4
0x1800179ef  mov     r8d, r13d
0x1800179f2  lea     rdx, [rbp+57h+var_90]
0x1800179f6  mov     rcx, rdi
0x1800179f9  call    ?OperationCompleted@WSManHttpSenderConnection@@AEAAXPEAVInCritSecWithConditionVar@@W4OperationCompleteCallbackOptions@@@Z; WSManHttpSenderConnection::OperationCompleted(InCritSecWithConditionVar *,OperationCompleteCallbackOptions)
0x1800179fe  test    r12b, r12b
0x180017a01  jz      short loc_180017A26
0x180017a03  mov     rcx, cs:WPP_GLOBAL_Control
0x180017a0a  cmp     rcx, rsi
0x180017a0d  jnz     loc_180017B53
0x180017a13  mov     rdx, rbx; Token
0x180017a16  xor     ecx, ecx; Thread
0x180017a18  call    cs:__imp_SetThreadToken
0x180017a1e  test    eax, eax
0x180017a20  jz      loc_180017E02
0x180017a26  lea     rax, [rbx-1]
0x180017a2a  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x180017a2e  ja      short loc_180017A53
0x180017a30  mov     rcx, cs:WPP_GLOBAL_Control
0x180017a37  cmp     rcx, rsi
0x180017a3a  jz      short loc_180017A49
0x180017a3c  test    dword ptr [rcx+1Ch], 1000000h
0x180017a43  jnz     loc_180017E31
0x180017a49  mov     rcx, rbx; hObject
0x180017a4c  call    cs:__imp_CloseHandle
0x180017a52  nop
0x180017a53  cmp     [rbp+57h+var_88], 0
0x180017a57  jnz     short loc_180017A8A
0x180017a59  mov     rcx, [rbp+57h+var_90]
0x180017a5d  mov     eax, [rcx]
0x180017a5f  test    eax, eax
0x180017a61  jnz     loc_180017BA3
0x180017a67  add     rcx, 30h ; '0'; ConditionVariable
0x180017a6b  call    cs:__imp_WakeAllConditionVariable
0x180017a71  mov     rcx, [rbp+57h+var_90]
0x180017a75  mov     eax, [rcx]
0x180017a77  test    eax, eax
0x180017a79  jnz     loc_180017BD7
0x180017a7f  add     rcx, 8; lpCriticalSection
0x180017a83  call    cs:__imp_LeaveCriticalSection
0x180017a89  nop
0x180017a8a  add     rsp, 88h
0x180017a91  pop     r15
0x180017a93  pop     r14
0x180017a95  pop     r13
0x180017a97  pop     r12
0x180017a99  pop     rdi
0x180017a9a  pop     rsi
0x180017a9b  pop     rbx
0x180017a9c  pop     rbp
0x180017a9d  retn
0x180017a9e  cmp     [rdi+8], r13
0x180017aa2  jz      loc_1800179DF
0x180017aa8  cmp     [rdi+23C8h], r13
0x180017aaf  jnz     loc_1800179DF
0x180017ab5  mov     rcx, rdi; this
0x180017ab8  call    ?ProcessFinalResponsePacket@WSManHttpSenderConnection@@AEAAKXZ; WSManHttpSenderConnection::ProcessFinalResponsePacket(void)
0x180017abd  mov     [rdi+239Ch], eax
0x180017ac3  mov     ecx, r13d
0x180017ac6  sub     ecx, eax
0x180017ac8  neg     ecx
0x180017aca  sbb     eax, eax
0x180017acc  and     eax, 2
0x180017acf  mov     [rdi+23A0h], eax
0x180017ad5  mov     rcx, cs:WPP_GLOBAL_Control
0x180017adc  jmp     loc_1800179DF
0x180017ae1  mov     ecx, esi; dwErrCode
0x180017ae3  call    cs:__imp_SetLastError
0x180017ae9  nop
0x180017aea  jmp     loc_180017934
0x180017aef  mov     ecx, esi; dwErrCode
0x180017af1  call    cs:__imp_SetLastError
0x180017af7  nop
0x180017af8  jmp     loc_1800178B5
0x180017afd  test    [rcx+1Ch], r14d
0x180017b01  jz      loc_180017974
0x180017b07  mov     edx, 1CAh
0x180017b0c  mov     r9, rdi
0x180017b0f  mov     r8, r15
0x180017b12  mov     rcx, [rcx+10h]
0x180017b16  call    WPP_SF_q
0x180017b1b  jmp     loc_180017974
0x180017b20  test    [rcx+1Ch], r14d
0x180017b24  jz      loc_180017958
0x180017b2a  mov     edx, 13Bh
0x180017b2f  mov     rax, [rdi+8]
0x180017b33  mov     [rsp+0C0h+var_A0], rax
0x180017b38  mov     r9, rdi
0x180017b3b  mov     r8, r15
0x180017b3e  mov     rcx, [rcx+10h]
0x180017b42  call    WPP_SF_qq
0x180017b47  mov     rcx, cs:WPP_GLOBAL_Control
0x180017b4e  jmp     loc_180017958
0x180017b53  test    [rcx+1Ch], r14d
0x180017b57  jz      loc_180017A13
0x180017b5d  mov     edx, 1CCh
0x180017b62  mov     r8, r15
0x180017b65  mov     rcx, [rcx+10h]
0x180017b69  call    WPP_SF_
0x180017b6e  jmp     loc_180017A13
0x180017b73  mov     ecx, eax; dwErrCode
0x180017b75  call    cs:__imp_SetLastError
0x180017b7b  mov     [rsp+0C0h+var_A0], r13; struct IRequestContext *
0x180017b80  mov     r9d, 54Fh; unsigned int
0x180017b86  lea     r8, a59; "59"
0x180017b8d  mov     edx, 3Bh ; ';'; unsigned int
0x180017b92  lea     rcx, aOnecoreAdminWm_164; "onecore\\admin\\wmi\\wmx\\binaries\\ser"...
0x180017b99  call    ?WSManError@@YAXPEBGK0KPEAVIRequestContext@@@Z; WSManError(ushort const *,ulong,ushort const *,ulong,IRequestContext *)
0x180017b9e  jmp     loc_18001780F
0x180017ba3  mov     ecx, eax; dwErrCode
0x180017ba5  call    cs:__imp_SetLastError
0x180017bab  mov     [rsp+0C0h+var_A0], 0; struct IRequestContext *
0x180017bb4  mov     r9d, 54Fh; unsigned int
0x180017bba  lea     r8, a102; "102"
0x180017bc1  mov     edx, 66h ; 'f'; unsigned int
0x180017bc6  lea     rcx, aOnecoreAdminWm_164; "onecore\\admin\\wmi\\wmx\\binaries\\ser"...
0x180017bcd  call    ?WSManError@@YAXPEBGK0KPEAVIRequestContext@@@Z; WSManError(ushort const *,ulong,ushort const *,ulong,IRequestContext *)
0x180017bd2  jmp     loc_180017A71
0x180017bd7  mov     ecx, eax; dwErrCode
0x180017bd9  call    cs:__imp_SetLastError
0x180017bdf  jmp     loc_180017A8A
0x180017be4  test    [rcx+1Ch], r14d
0x180017be8  jz      loc_1800179EF
0x180017bee  mov     edx, 13Dh
0x180017bf3  mov     rax, [rdi+8]
0x180017bf7  mov     [rsp+0C0h+var_A0], rax
0x180017bfc  mov     r9, rdi
0x180017bff  mov     r8, r15
0x180017c02  mov     rcx, [rcx+10h]
0x180017c06  call    WPP_SF_qq
0x180017c0b  jmp     loc_1800179EF
0x180017c10  mov     rcx, cs:WPP_GLOBAL_Control
0x180017c17  cmp     rcx, rsi
0x180017c1a  jz      loc_1800179A9
0x180017c20  test    dword ptr [rcx+1Ch], 10000000h
0x180017c27  jz      loc_1800179A9
0x180017c2d  mov     edx, 12h
0x180017c32  lea     r8, WPP_5b789da118f632ad9796e014c1252c4d_Traceguids
0x180017c39  mov     rcx, [rcx+10h]
0x180017c3d  call    WPP_SF_
0x180017c42  jmp     loc_1800179A9
0x180017c47  call    ?EnsureActivityIdOnThread@EventHandler@WSMan@@SAXXZ; WSMan::EventHandler::EnsureActivityIdOnThread(void)
0x180017c4c  jmp     loc_1800178B5
0x180017c51  mov     [rsp+0C0h+var_A0], r13; struct IRequestContext *
0x180017c56  mov     r9d, 54Fh; unsigned int
0x180017c5c  lea     r8, a644; "644"
0x180017c63  mov     edx, 284h; unsigned int
0x180017c68  lea     rcx, aOnecoreAdminWm_109; "onecore\\admin\\wmi\\wmx\\stdlib\\wsman"...
0x180017c6f  call    ?WSManError@@YAXPEBGK0KPEAVIRequestContext@@@Z; WSManError(ushort const *,ulong,ushort const *,ulong,IRequestContext *)
0x180017c74  mov     bl, r13b
0x180017c77  jmp     loc_180017923
0x180017c7c  lea     rsi, WPP_GLOBAL_Control
0x180017c83  mov     rcx, cs:WPP_GLOBAL_Control
0x180017c8a  cmp     rcx, rsi
0x180017c8d  jnz     loc_180017D1D
0x180017c93  mov     [rdi+2C65h], r13b
0x180017c9a  lea     rcx, [rbp+57h+var_90]; this
0x180017c9e  call    ?Release@InCritSecWithConditionVar@@QEAAXXZ; InCritSecWithConditionVar::Release(void)
0x180017ca3  mov     rax, [rdi]
0x180017ca6  lea     rdx, aNotifyOperatio; "@Notify(OperationCompleted3)"
0x180017cad  mov     rcx, rdi
0x180017cb0  mov     rax, [rax+70h]
0x180017cb4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017cb9  nop
0x180017cba  lea     rcx, [rbp+57h+var_90]; this
0x180017cbe  call    ??1InCritSecWithConditionVar@@QEAA@XZ; InCritSecWithConditionVar::~InCritSecWithConditionVar(void)
0x180017cc3  jmp     loc_180017A8A
0x180017cc8  mov     [rsp+0C0h+var_A0], r13; struct IRequestContext *
0x180017ccd  mov     r9d, 54Fh; unsigned int
0x180017cd3  lea     r8, a624; "624"
0x180017cda  mov     edx, 270h; unsigned int
0x180017cdf  lea     rcx, aOnecoreAdminWm_109; "onecore\\admin\\wmi\\wmx\\stdlib\\wsman"...
0x180017ce6  call    ?WSManError@@YAXPEBGK0KPEAVIRequestContext@@@Z; WSManError(ushort const *,ulong,ushort const *,ulong,IRequestContext *)
0x180017ceb  mov     bl, r13b
  ... truncated ...
```
