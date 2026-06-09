# CEventNotificationService::Initialize(void)

- ea: `0x14001e6c8`
- end: `0x14001e901`
- name: `?Initialize@CEventNotificationService@@QEAAJXZ`
- size: `569`
- prototype: `__int64 __fastcall(CEventNotificationService *__hidden this)`
- caller_count: `1`
- callee_count: `7`
- tags: `service_task, broker_com_uri`

## callers

- `0x140027f40`

## callees

- `0x140018154`
- `0x14001e6c8`
- `0x1400267d0`
- `0x140026bbc`
- `0x14005bc68`
- `0x14005bfec`
- `0x14005c408`

## import_xrefs

- `KERNEL32!GetComputerNameExW` at `0x14001e830`
- `KERNEL32!GetComputerNameExW` at `0x14001e830`
- `KERNEL32!CreateEventW` at `0x14001e736`
- `KERNEL32!CreateEventW` at `0x14001e776`
- `KERNEL32!CreateEventW` at `0x14001e7b6`
- `KERNEL32!CreateEventW` at `0x14001e736`
- `KERNEL32!CreateEventW` at `0x14001e776`
- `KERNEL32!CreateEventW` at `0x14001e7b6`
- `KERNEL32!GetLastError` at `0x14001e745`
- `KERNEL32!GetLastError` at `0x14001e785`
- `KERNEL32!GetLastError` at `0x14001e7c5`
- `KERNEL32!GetLastError` at `0x14001e83e`
- `KERNEL32!GetLastError` at `0x14001e745`
- `KERNEL32!GetLastError` at `0x14001e785`
- `KERNEL32!GetLastError` at `0x14001e7c5`
- `KERNEL32!GetLastError` at `0x14001e83e`
- `KERNEL32!IsDebuggerPresent` at `0x14001e899`
- `KERNEL32!IsDebuggerPresent` at `0x14001e899`

## string_xrefs

- `0x14001e6fd`: `CEventNotificationService::Initialize`
- `0x14001e86e`: `CEventNotificationService::Initialize`
- `0x14001e75a`: `m_hStationReadyEvent != 0`
- `0x14001e79a`: `m_hCoreProcessWatcherThreadTerminationEvent != 0`
- `0x14001e7da`: `m_hKillStationThreadEvent`

## pseudocode

```c
__int64 __fastcall CEventNotificationService::Initialize(CEventNotificationService *this)
{
  bool v1; // zf
  signed int v3; // ebx
  HANDLE EventW; // rax
  signed int v5; // eax
  const unsigned __int16 *v6; // r15
  unsigned int v7; // r14d
  HANDLE v8; // rax
  signed int v9; // eax
  HANDLE v10; // rax
  signed int v11; // eax
  CEventNotificationService *v12; // rcx
  signed int LastError; // eax
  signed int v15; // [rsp+30h] [rbp-48h]
  signed int v16; // [rsp+38h] [rbp-40h]
  DWORD nSize; // [rsp+80h] [rbp+8h] BYREF

  v1 = *((_QWORD *)this + 58) == 0;
  nSize = 256;
  if ( v1 )
  {
    v3 = -2147024882;
    DEBUGMSGLEVEL(
      4u,
      L"%s(%d) - %s - Test failed:  %s\n",
      L"termsrv\\wms\\src\\devices\\wmssvc\\eventnotification.cpp",
      147,
      L"CEventNotificationService::Initialize",
      L"Critical section is not initialized.");
    return (unsigned int)v3;
  }
  EventW = CreateEventW(0, 1, 0, 0);
  *((_QWORD *)this + 14) = EventW;
  if ( EventW )
  {
    v8 = CreateEventW(0, 0, 0, 0);
    *((_QWORD *)this + 12) = v8;
    if ( v8 )
    {
      v10 = CreateEventW(0, 0, 0, 0);
      *((_QWORD *)this + 15) = v10;
      if ( v10 )
      {
        v3 = CEventNotificationService::SwitchToMaintenanceMode(this);
        if ( v3 < 0 )
          return (unsigned int)v3;
        v3 = CEventNotificationService::TerminateAllRunningSessionAgents(v12);
        if ( v3 < 0 )
          return (unsigned int)v3;
        v3 = CEventNotificationService::ConnectAllCurrentSessions(this);
        if ( v3 < 0 || GetComputerNameExW(ComputerNameDnsFullyQualified, (LPWSTR)this + 440, &nSize) )
          return (unsigned int)v3;
        LastError = GetLastError();
        v3 = LastError;
        if ( LastError > 0 )
          v3 = (unsigned __int16)LastError | 0x80070000;
        v6 = L"dwRet";
        v7 = 201;
      }
      else
      {
        v11 = GetLastError();
        v3 = v11;
        if ( v11 > 0 )
          v3 = (unsigned __int16)v11 | 0x80070000;
        v6 = L"m_hKillStationThreadEvent";
        v7 = 164;
      }
    }
    else
    {
      v9 = GetLastError();
      v3 = v9;
      if ( v9 > 0 )
        v3 = (unsigned __int16)v9 | 0x80070000;
      v6 = L"m_hCoreProcessWatcherThreadTerminationEvent != 0";
      v7 = 157;
    }
  }
  else
  {
    v5 = GetLastError();
    v3 = v5;
    if ( v5 > 0 )
      v3 = (unsigned __int16)v5 | 0x80070000;
    v6 = L"m_hStationReadyEvent != 0";
    v7 = 152;
  }
  if ( v3 >= 0 )
    v3 = -2147467259;
  LOGASSERTHR(
    L"termsrv\\wms\\src\\devices\\wmssvc\\eventnotification.cpp",
    v7,
    L"CEventNotificationService::Initialize",
    L"CBRAEx",
    v6,
    v3);
  if ( IsDebuggerPresent() )
  {
    v16 = v3;
    DEBUGMSGLEVEL(
      2u,
      L"%s(%d) - %s - Assertion failed:  %s (%s)  hr = 0x%08X\n",
      L"termsrv\\wms\\src\\devices\\wmssvc\\eventnotification.cpp",
      v7,
      L"CEventNotificationService::Initialize",
      L"CBRAEx",
      v6,
      v16);
  }
  else
  {
    v15 = v3;
    DEBUGMSGBOX(
      L"Assertion failed:  %s(%d) - %s - %s (%s)  hr = 0x%08X\n\n",
      L"termsrv\\wms\\src\\devices\\wmssvc\\eventnotification.cpp",
      v7,
      L"CEventNotificationService::Initialize",
      L"CBRAEx",
      v6,
      v15);
  }
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x14001e6c8  mov     r11, rsp
0x14001e6cb  push    rbx
0x14001e6cc  push    rbp
0x14001e6cd  push    rsi
0x14001e6ce  push    rdi
0x14001e6cf  push    r14
0x14001e6d1  push    r15
0x14001e6d3  sub     rsp, 48h
0x14001e6d7  cmp     qword ptr [rcx+1D0h], 0
0x14001e6df  mov     rdi, rcx
0x14001e6e2  mov     dword ptr [r11+8], 100h
0x14001e6ea  jnz     short loc_14001E72A
0x14001e6ec  lea     rax, aCriticalSectio; "Critical section is not initialized."
0x14001e6f3  mov     r9d, 93h
0x14001e6f9  mov     [r11-50h], rax
0x14001e6fd  lea     rsi, aCeventnotifica_41; "CEventNotificationService::Initialize"
0x14001e704  lea     r8, aTermsrvWmsSrcD_32; "termsrv\\wms\\src\\devices\\wmssvc\\eve"...
0x14001e70b  mov     [r11-58h], rsi
0x14001e70f  lea     rdx, aSDSTestFailedS; "%s(%d) - %s - Test failed:  %s\n"
0x14001e716  mov     ecx, 4; unsigned __int8
0x14001e71b  mov     ebx, 8007000Eh
0x14001e720  call    ?DEBUGMSGLEVEL@@YAXEPEBGZZ; DEBUGMSGLEVEL(uchar,ushort const *,...)
0x14001e725  jmp     loc_14001E8F2
0x14001e72a  xor     r9d, r9d; lpName
0x14001e72d  xor     r8d, r8d; bInitialState
0x14001e730  xor     ecx, ecx; lpEventAttributes
0x14001e732  lea     edx, [r9+1]; bManualReset
0x14001e736  call    cs:__imp_CreateEventW
0x14001e73c  mov     [rdi+70h], rax
0x14001e740  test    rax, rax
0x14001e743  jnz     short loc_14001E76C
0x14001e745  call    cs:__imp_GetLastError
0x14001e74b  mov     ebx, eax
0x14001e74d  test    eax, eax
0x14001e74f  jle     short loc_14001E75A
0x14001e751  movzx   ebx, ax
0x14001e754  or      ebx, 80070000h
0x14001e75a  lea     r15, aMHstationready; "m_hStationReadyEvent != 0"
0x14001e761  mov     r14d, 98h
0x14001e767  jmp     loc_14001E860
0x14001e76c  xor     r9d, r9d; lpName
0x14001e76f  xor     r8d, r8d; bInitialState
0x14001e772  xor     edx, edx; bManualReset
0x14001e774  xor     ecx, ecx; lpEventAttributes
0x14001e776  call    cs:__imp_CreateEventW
0x14001e77c  mov     [rdi+60h], rax
0x14001e780  test    rax, rax
0x14001e783  jnz     short loc_14001E7AC
0x14001e785  call    cs:__imp_GetLastError
0x14001e78b  mov     ebx, eax
0x14001e78d  test    eax, eax
0x14001e78f  jle     short loc_14001E79A
0x14001e791  movzx   ebx, ax
0x14001e794  or      ebx, 80070000h
0x14001e79a  lea     r15, aMHcoreprocessw_1; "m_hCoreProcessWatcherThreadTerminationE"...
0x14001e7a1  mov     r14d, 9Dh
0x14001e7a7  jmp     loc_14001E860
0x14001e7ac  xor     r9d, r9d; lpName
0x14001e7af  xor     r8d, r8d; bInitialState
0x14001e7b2  xor     edx, edx; bManualReset
0x14001e7b4  xor     ecx, ecx; lpEventAttributes
0x14001e7b6  call    cs:__imp_CreateEventW
0x14001e7bc  mov     [rdi+78h], rax
0x14001e7c0  test    rax, rax
0x14001e7c3  jnz     short loc_14001E7E9
0x14001e7c5  call    cs:__imp_GetLastError
0x14001e7cb  mov     ebx, eax
0x14001e7cd  test    eax, eax
0x14001e7cf  jle     short loc_14001E7DA
0x14001e7d1  movzx   ebx, ax
0x14001e7d4  or      ebx, 80070000h
0x14001e7da  lea     r15, aMHkillstationt; "m_hKillStationThreadEvent"
0x14001e7e1  mov     r14d, 0A4h
0x14001e7e7  jmp     short loc_14001E860
0x14001e7e9  mov     rcx, rdi; this
0x14001e7ec  call    ?SwitchToMaintenanceMode@CEventNotificationService@@IEAAJXZ; CEventNotificationService::SwitchToMaintenanceMode(void)
0x14001e7f1  mov     ebx, eax
0x14001e7f3  test    eax, eax
0x14001e7f5  js      loc_14001E8F2
0x14001e7fb  call    ?TerminateAllRunningSessionAgents@CEventNotificationService@@IEAAJXZ; CEventNotificationService::TerminateAllRunningSessionAgents(void)
0x14001e800  mov     ebx, eax
0x14001e802  test    eax, eax
0x14001e804  js      loc_14001E8F2
0x14001e80a  mov     rcx, rdi; this
0x14001e80d  call    ?ConnectAllCurrentSessions@CEventNotificationService@@IEAAJXZ; CEventNotificationService::ConnectAllCurrentSessions(void)
0x14001e812  mov     ebx, eax
0x14001e814  test    eax, eax
0x14001e816  js      loc_14001E8F2
0x14001e81c  lea     rdx, [rdi+370h]; lpBuffer
0x14001e823  mov     ecx, 3; NameType
0x14001e828  lea     r8, [rsp+78h+nSize]; nSize
0x14001e830  call    cs:__imp_GetComputerNameExW
0x14001e836  test    eax, eax
0x14001e838  jnz     loc_14001E8F2
0x14001e83e  call    cs:__imp_GetLastError
0x14001e844  mov     ebx, eax
0x14001e846  test    eax, eax
0x14001e848  jle     short loc_14001E853
0x14001e84a  movzx   ebx, ax
0x14001e84d  or      ebx, 80070000h
0x14001e853  lea     r15, aDwret; "dwRet"
0x14001e85a  mov     r14d, 0C9h
0x14001e860  mov     eax, 80004005h
0x14001e865  lea     rbp, aCbraex; "CBRAEx"
0x14001e86c  test    ebx, ebx
0x14001e86e  lea     rsi, aCeventnotifica_41; "CEventNotificationService::Initialize"
0x14001e875  lea     rdi, aTermsrvWmsSrcD_32; "termsrv\\wms\\src\\devices\\wmssvc\\eve"...
0x14001e87c  mov     r9, rbp; unsigned __int16 *
0x14001e87f  cmovns  ebx, eax
0x14001e882  mov     r8, rsi; unsigned __int16 *
0x14001e885  mov     [rsp+78h+var_50], ebx; int
0x14001e889  mov     edx, r14d; unsigned int
0x14001e88c  mov     rcx, rdi; unsigned __int16 *
0x14001e88f  mov     [rsp+78h+var_58], r15; unsigned __int16 *
0x14001e894  call    ?LOGASSERTHR@@YAXPEBGK000J@Z; LOGASSERTHR(ushort const *,ulong,ushort const *,ushort const *,ushort const *,long)
0x14001e899  call    cs:__imp_IsDebuggerPresent
0x14001e89f  test    eax, eax
0x14001e8a1  jz      short loc_14001E8CF
0x14001e8a3  mov     [rsp+78h+var_40], ebx
0x14001e8a7  lea     rdx, aSDSAssertionFa_0; "%s(%d) - %s - Assertion failed:  %s (%s"...
0x14001e8ae  mov     [rsp+78h+var_48], r15
0x14001e8b3  mov     r9d, r14d
0x14001e8b6  mov     qword ptr [rsp+78h+var_50], rbp
0x14001e8bb  mov     r8, rdi
0x14001e8be  mov     ecx, 2; unsigned __int8
0x14001e8c3  mov     [rsp+78h+var_58], rsi
0x14001e8c8  call    ?DEBUGMSGLEVEL@@YAXEPEBGZZ; DEBUGMSGLEVEL(uchar,ushort const *,...)
0x14001e8cd  jmp     short loc_14001E8F2
0x14001e8cf  mov     dword ptr [rsp+78h+var_48], ebx
0x14001e8d3  lea     rcx, aAssertionFaile; "Assertion failed:  %s(%d) - %s - %s (%s"...
0x14001e8da  mov     qword ptr [rsp+78h+var_50], r15
0x14001e8df  mov     r9, rsi
0x14001e8e2  mov     r8d, r14d
0x14001e8e5  mov     [rsp+78h+var_58], rbp
0x14001e8ea  mov     rdx, rdi
0x14001e8ed  call    ?DEBUGMSGBOX@@YAHPEBGZZ; DEBUGMSGBOX(ushort const *,...)
0x14001e8f2  mov     eax, ebx
0x14001e8f4  add     rsp, 48h
0x14001e8f8  pop     r15
0x14001e8fa  pop     r14
0x14001e8fc  pop     rdi
0x14001e8fd  pop     rsi
0x14001e8fe  pop     rbp
0x14001e8ff  pop     rbx
0x14001e900  retn
```
