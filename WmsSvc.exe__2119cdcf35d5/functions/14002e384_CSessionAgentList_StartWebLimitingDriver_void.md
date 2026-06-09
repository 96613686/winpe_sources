# CSessionAgentList::StartWebLimitingDriver(void)

- ea: `0x14002e384`
- end: `0x14002e712`
- name: `?StartWebLimitingDriver@CSessionAgentList@@AEAAJXZ`
- size: `910`
- prototype: `__int64 __fastcall(CSessionAgentList *__hidden this)`
- caller_count: `1`
- callee_count: `7`
- tags: `service_task`

## callers

- `0x14002d554`

## callees

- `0x14002ce08`
- `0x14002e384`
- `0x14005bc30`
- `0x14005bc68`
- `0x14005bfec`
- `0x14005c408`
- `0x140065368`

## import_xrefs

- `ADVAPI32!OpenSCManagerW` at `0x14002e40e`
- `ADVAPI32!OpenSCManagerW` at `0x14002e40e`
- `ADVAPI32!OpenServiceW` at `0x14002e535`
- `ADVAPI32!OpenServiceW` at `0x14002e535`
- `ADVAPI32!CloseServiceHandle` at `0x14002e5fe`
- `ADVAPI32!CloseServiceHandle` at `0x14002e5fe`
- `ADVAPI32!StartServiceW` at `0x14002e593`
- `ADVAPI32!StartServiceW` at `0x14002e593`
- `KERNEL32!GetLastError` at `0x14002e420`
- `KERNEL32!GetLastError` at `0x14002e544`
- `KERNEL32!GetLastError` at `0x14002e59d`
- `KERNEL32!GetLastError` at `0x14002e613`
- `KERNEL32!GetLastError` at `0x14002e620`
- `KERNEL32!GetLastError` at `0x14002e420`
- `KERNEL32!GetLastError` at `0x14002e544`
- `KERNEL32!GetLastError` at `0x14002e59d`
- `KERNEL32!GetLastError` at `0x14002e613`
- `KERNEL32!GetLastError` at `0x14002e620`
- `KERNEL32!IsDebuggerPresent` at `0x14002e478`
- `KERNEL32!IsDebuggerPresent` at `0x14002e678`
- `KERNEL32!IsDebuggerPresent` at `0x14002e478`
- `KERNEL32!IsDebuggerPresent` at `0x14002e678`
- `KERNEL32!QueryPerformanceCounter` at `0x14002e4fa`
- `KERNEL32!QueryPerformanceCounter` at `0x14002e584`
- `KERNEL32!QueryPerformanceCounter` at `0x14002e4fa`
- `KERNEL32!QueryPerformanceCounter` at `0x14002e584`
- `USER32!GetSystemMetrics` at `0x14002e3a5`
- `USER32!GetSystemMetrics` at `0x14002e3a5`

## string_xrefs

- `0x14002e3ca`: `termsrv\wms\src\devices\wmssvc\sessionagentlist.cpp`
- `0x14002e45a`: `termsrv\wms\src\devices\wmssvc\sessionagentlist.cpp`
- `0x14002e486`: `termsrv\wms\src\devices\wmssvc\sessionagentlist.cpp`
- `0x14002e4b9`: `termsrv\wms\src\devices\wmssvc\sessionagentlist.cpp`
- `0x14002e5ca`: `termsrv\wms\src\devices\wmssvc\sessionagentlist.cpp`
- `0x14002e65a`: `termsrv\wms\src\devices\wmssvc\sessionagentlist.cpp`
- `0x14002e686`: `termsrv\wms\src\devices\wmssvc\sessionagentlist.cpp`
- `0x14002e6b6`: `termsrv\wms\src\devices\wmssvc\sessionagentlist.cpp`
- `0x14002e396`: `CSessionAgentList::StartWebLimitingDriver\n`
- `0x14002e3c3`: `CSessionAgentList::StartWebLimitingDriver`
- `0x14002e447`: `CSessionAgentList::StartWebLimitingDriver`
- `0x14002e5b8`: `CSessionAgentList::StartWebLimitingDriver`
- `0x14002e643`: `CSessionAgentList::StartWebLimitingDriver`
- `0x14002e3f0`: `WmsWlFltr.sys is already started, nothing to do.`
- `0x14002e405`: `ServicesActive`
- `0x14002e4e1`: `CSessionAgentList::StartWebLimitingDriver - ConditionalWaitForServiceStart ("bfe", NULL)`
- `0x14002e56b`: `CSessionAgentList::StartWebLimitingDriver - ::StartService ("WmsWlFltr")`
- `0x14002e6eb`: `CSessionAgentList::StartWebLimitingDriver - WMS Web Limiting driver was already running.\n`
- `0x14002e5ea`: `CSessionAgentList::StartWebLimitingDriver - WMS Web Limiting driver successfully started.\n`
- `0x14002e701`: `CSessionAgentList::StartWebLimitingDriver - WMS Web Limiting driver DID NOT start, hr = 0x%08X!\n`

## pseudocode

```c
__int64 __fastcall CSessionAgentList::StartWebLimitingDriver(CSessionAgentList *this)
{
  SC_HANDLE v2; // rbp
  const wchar_t *v3; // rax
  __int64 v4; // r9
  signed int started; // ebx
  signed int LastError; // eax
  const unsigned __int16 *v7; // r12
  unsigned int v8; // r15d
  SC_HANDLE v9; // rax
  signed int v10; // eax
  signed int v12; // eax
  const wchar_t *v13; // [rsp+40h] [rbp-58h] BYREF
  LARGE_INTEGER PerformanceCount; // [rsp+48h] [rbp-50h] BYREF
  int v15; // [rsp+50h] [rbp-48h]

  v2 = 0;
  DEBUGMSG(L"CSessionAgentList::StartWebLimitingDriver\n");
  if ( GetSystemMetrics(67) )
  {
    v3 = L"Skipping start of web limiting driver due to safe mode";
    v4 = 750;
LABEL_3:
    started = 0;
    DEBUGMSGLEVEL(
      4u,
      L"%s(%d) - %s - Test failed:  %s\n",
      L"termsrv\\wms\\src\\devices\\wmssvc\\sessionagentlist.cpp",
      v4,
      L"CSessionAgentList::StartWebLimitingDriver",
      v3);
LABEL_24:
    DEBUGMSG(L"CSessionAgentList::StartWebLimitingDriver - WMS Web Limiting driver successfully started.\n");
    goto LABEL_25;
  }
  if ( *((_QWORD *)this + 3) )
  {
    v3 = L"WmsWlFltr.sys is already started, nothing to do.";
    v4 = 752;
    goto LABEL_3;
  }
  v2 = OpenSCManagerW(0, L"ServicesActive", 4u);
  if ( !v2 )
  {
    LastError = GetLastError();
    started = LastError;
    if ( LastError > 0 )
      started = (unsigned __int16)LastError | 0x80070000;
    v7 = L"hSCMan";
    v8 = 755;
LABEL_10:
    if ( started >= 0 )
      started = -2147467259;
    LOGASSERTHR(
      L"termsrv\\wms\\src\\devices\\wmssvc\\sessionagentlist.cpp",
      v8,
      L"CSessionAgentList::StartWebLimitingDriver",
      L"CBRAEx",
      v7,
      started);
    if ( IsDebuggerPresent() )
      DEBUGMSGLEVEL(
        2u,
        L"%s(%d) - %s - Assertion failed:  %s (%s)  hr = 0x%08X\n",
        L"termsrv\\wms\\src\\devices\\wmssvc\\sessionagentlist.cpp",
        v8,
        L"CSessionAgentList::StartWebLimitingDriver",
        L"CBRAEx",
        v7,
        started);
    else
      DEBUGMSGBOX(
        L"Assertion failed:  %s(%d) - %s - %s (%s)  hr = 0x%08X\n\n",
        L"termsrv\\wms\\src\\devices\\wmssvc\\sessionagentlist.cpp",
        v8,
        L"CSessionAgentList::StartWebLimitingDriver",
        L"CBRAEx",
        v7,
        started);
    goto LABEL_37;
  }
  v15 = 0;
  v13 = L"CSessionAgentList::StartWebLimitingDriver - ConditionalWaitForServiceStart (\"bfe\", NULL)";
  QueryPerformanceCounter(&PerformanceCount);
  started = ConditionalWaitForServiceStartUsingEventToStop(L"bfe", 0, 0);
  if ( started >= 0 )
  {
    CPerfTrace::~CPerfTrace((CPerfTrace *)&v13);
    v9 = OpenServiceW(v2, L"WmsWlFltr", 0x30u);
    *((_QWORD *)this + 3) = v9;
    if ( !v9 )
    {
      v10 = GetLastError();
      started = v10;
      if ( v10 > 0 )
        started = (unsigned __int16)v10 | 0x80070000;
      v7 = L"m_hWlDriver";
      v8 = 765;
      goto LABEL_10;
    }
    v15 = 0;
    v13 = L"CSessionAgentList::StartWebLimitingDriver - ::StartService (\"WmsWlFltr\")";
    QueryPerformanceCounter(&PerformanceCount);
    if ( StartServiceW(*((SC_HANDLE *)this + 3), 0, 0) )
    {
LABEL_23:
      CPerfTrace::~CPerfTrace((CPerfTrace *)&v13);
      goto LABEL_24;
    }
    if ( GetLastError() == 577 )
    {
      started = 0;
      DEBUGMSGLEVEL(
        4u,
        L"%s(%d) - %s - Test failed:  %s\n",
        L"termsrv\\wms\\src\\devices\\wmssvc\\sessionagentlist.cpp",
        777,
        L"CSessionAgentList::StartWebLimitingDriver",
        L"Web limiting driver is not signed");
      goto LABEL_23;
    }
    if ( GetLastError() == 1056 )
      goto LABEL_23;
    v12 = GetLastError();
    started = v12;
    if ( v12 > 0 )
      started = (unsigned __int16)v12 | 0x80070000;
    if ( started >= 0 )
      started = -2147467259;
    LOGASSERTHR(
      L"termsrv\\wms\\src\\devices\\wmssvc\\sessionagentlist.cpp",
      0x30Au,
      L"CSessionAgentList::StartWebLimitingDriver",
      L"CBRAEx",
      L"fSuccess || ::GetLastError () == 1056L",
      started);
    if ( IsDebuggerPresent() )
      DEBUGMSGLEVEL(
        2u,
        L"%s(%d) - %s - Assertion failed:  %s (%s)  hr = 0x%08X\n",
        L"termsrv\\wms\\src\\devices\\wmssvc\\sessionagentlist.cpp",
        778,
        L"CSessionAgentList::StartWebLimitingDriver",
        L"CBRAEx",
        L"fSuccess || ::GetLastError () == 1056L",
        started);
    else
      DEBUGMSGBOX(
        L"Assertion failed:  %s(%d) - %s - %s (%s)  hr = 0x%08X\n\n",
        L"termsrv\\wms\\src\\devices\\wmssvc\\sessionagentlist.cpp",
        778,
        L"CSessionAgentList::StartWebLimitingDriver",
        L"CBRAEx",
        L"fSuccess || ::GetLastError () == 1056L",
        started);
  }
  CPerfTrace::~CPerfTrace((CPerfTrace *)&v13);
LABEL_37:
  if ( started == -2147023840 )
    DEBUGMSG(L"CSessionAgentList::StartWebLimitingDriver - WMS Web Limiting driver was already running.\n");
  else
    DEBUGMSG(
      L"CSessionAgentList::StartWebLimitingDriver - WMS Web Limiting driver DID NOT start, hr = 0x%08X!\n",
      (unsigned int)started);
LABEL_25:
  if ( v2 )
    CloseServiceHandle(v2);
  return (unsigned int)started;
}

```

## disassembly

```asm
0x14002e384  push    rbx
0x14002e386  push    rbp
0x14002e387  push    rsi
0x14002e388  push    rdi
0x14002e389  push    r12
0x14002e38b  push    r15
0x14002e38d  sub     rsp, 68h
0x14002e391  mov     rdi, rcx
0x14002e394  xor     ebp, ebp
0x14002e396  lea     rcx, aCsessionagentl_8; "CSessionAgentList::StartWebLimitingDriv"...
0x14002e39d  call    ?DEBUGMSG@@YAXPEBGZZ; DEBUGMSG(ushort const *,...)
0x14002e3a2  lea     ecx, [rbp+43h]; nIndex
0x14002e3a5  call    cs:__imp_GetSystemMetrics
0x14002e3ab  test    eax, eax
0x14002e3ad  jz      short loc_14002E3EA
0x14002e3af  lea     rax, aSkippingStartO; "Skipping start of web limiting driver d"...
0x14002e3b6  mov     r9d, 2EEh
0x14002e3bc  xor     ebx, ebx
0x14002e3be  mov     qword ptr [rsp+98h+var_70], rax
0x14002e3c3  lea     rdi, aCsessionagentl_39; "CSessionAgentList::StartWebLimitingDriv"...
0x14002e3ca  lea     r8, aTermsrvWmsSrcD_19; "termsrv\\wms\\src\\devices\\wmssvc\\ses"...
0x14002e3d1  mov     [rsp+98h+var_78], rdi
0x14002e3d6  lea     rdx, aSDSTestFailedS; "%s(%d) - %s - Test failed:  %s\n"
0x14002e3dd  lea     ecx, [rbx+4]; unsigned __int8
0x14002e3e0  call    ?DEBUGMSGLEVEL@@YAXEPEBGZZ; DEBUGMSGLEVEL(uchar,ushort const *,...)
0x14002e3e5  jmp     loc_14002E5EA
0x14002e3ea  cmp     [rdi+18h], rbp
0x14002e3ee  jz      short loc_14002E3FF
0x14002e3f0  lea     rax, aWmswlfltrSysIs; "WmsWlFltr.sys is already started, nothi"...
0x14002e3f7  mov     r9d, 2F0h
0x14002e3fd  jmp     short loc_14002E3BC
0x14002e3ff  mov     r8d, 4; dwDesiredAccess
0x14002e405  lea     rdx, DatabaseName; "ServicesActive"
0x14002e40c  xor     ecx, ecx; lpMachineName
0x14002e40e  call    cs:__imp_OpenSCManagerW
0x14002e414  mov     rbp, rax
0x14002e417  test    rax, rax
0x14002e41a  jnz     loc_14002E4E1
0x14002e420  call    cs:__imp_GetLastError
0x14002e426  mov     ebx, eax
0x14002e428  test    eax, eax
0x14002e42a  jle     short loc_14002E435
0x14002e42c  movzx   ebx, ax
0x14002e42f  or      ebx, 80070000h
0x14002e435  lea     r12, aHscman; "hSCMan"
0x14002e43c  mov     r15d, 2F3h
0x14002e442  mov     eax, 80004005h
0x14002e447  lea     rdi, aCsessionagentl_39; "CSessionAgentList::StartWebLimitingDriv"...
0x14002e44e  test    ebx, ebx
0x14002e450  lea     rsi, aCbraex; "CBRAEx"
0x14002e457  mov     r8, rdi; unsigned __int16 *
0x14002e45a  lea     rcx, aTermsrvWmsSrcD_19; "termsrv\\wms\\src\\devices\\wmssvc\\ses"...
0x14002e461  cmovns  ebx, eax
0x14002e464  mov     r9, rsi; unsigned __int16 *
0x14002e467  mov     [rsp+98h+var_70], ebx; int
0x14002e46b  mov     edx, r15d; unsigned int
0x14002e46e  mov     [rsp+98h+var_78], r12; unsigned __int16 *
0x14002e473  call    ?LOGASSERTHR@@YAXPEBGK000J@Z; LOGASSERTHR(ushort const *,ulong,ushort const *,ushort const *,ushort const *,long)
0x14002e478  call    cs:__imp_IsDebuggerPresent
0x14002e47e  test    eax, eax
0x14002e480  jz      short loc_14002E4B5
0x14002e482  mov     [rsp+98h+var_60], ebx
0x14002e486  lea     r8, aTermsrvWmsSrcD_19; "termsrv\\wms\\src\\devices\\wmssvc\\ses"...
0x14002e48d  mov     [rsp+98h+var_68], r12
0x14002e492  lea     rdx, aSDSAssertionFa_0; "%s(%d) - %s - Assertion failed:  %s (%s"...
0x14002e499  mov     qword ptr [rsp+98h+var_70], rsi
0x14002e49e  mov     r9d, r15d
0x14002e4a1  mov     ecx, 2; unsigned __int8
0x14002e4a6  mov     [rsp+98h+var_78], rdi
0x14002e4ab  call    ?DEBUGMSGLEVEL@@YAXEPEBGZZ; DEBUGMSGLEVEL(uchar,ushort const *,...)
0x14002e4b0  jmp     loc_14002E6E3
0x14002e4b5  mov     dword ptr [rsp+98h+var_68], ebx
0x14002e4b9  lea     rdx, aTermsrvWmsSrcD_19; "termsrv\\wms\\src\\devices\\wmssvc\\ses"...
0x14002e4c0  mov     qword ptr [rsp+98h+var_70], r12
0x14002e4c5  lea     rcx, aAssertionFaile; "Assertion failed:  %s(%d) - %s - %s (%s"...
0x14002e4cc  mov     r9, rdi
0x14002e4cf  mov     [rsp+98h+var_78], rsi
0x14002e4d4  mov     r8d, r15d
0x14002e4d7  call    ?DEBUGMSGBOX@@YAHPEBGZZ; DEBUGMSGBOX(ushort const *,...)
0x14002e4dc  jmp     loc_14002E6E3
0x14002e4e1  lea     rax, aCsessionagentl_26; "CSessionAgentList::StartWebLimitingDriv"...
0x14002e4e8  mov     [rsp+98h+var_48], 0
0x14002e4f0  lea     rcx, [rsp+98h+PerformanceCount]; lpPerformanceCount
0x14002e4f5  mov     [rsp+98h+var_58], rax
0x14002e4fa  call    cs:__imp_QueryPerformanceCounter
0x14002e500  xor     r8d, r8d; int *
0x14002e503  lea     rcx, aBfe; "bfe"
0x14002e50a  xor     edx, edx; void *
0x14002e50c  call    ?ConditionalWaitForServiceStartUsingEventToStop@@YAJPEBGPEAXPEAH@Z; ConditionalWaitForServiceStartUsingEventToStop(ushort const *,void *,int *)
0x14002e511  mov     ebx, eax
0x14002e513  lea     rcx, [rsp+98h+var_58]; this
0x14002e518  test    eax, eax
0x14002e51a  js      loc_14002E6DE
0x14002e520  call    ??1CPerfTrace@@QEAA@XZ; CPerfTrace::~CPerfTrace(void)
0x14002e525  mov     r8d, 30h ; '0'; dwDesiredAccess
0x14002e52b  lea     rdx, aWmswlfltr; "WmsWlFltr"
0x14002e532  mov     rcx, rbp; hSCManager
0x14002e535  call    cs:__imp_OpenServiceW
0x14002e53b  mov     [rdi+18h], rax
0x14002e53f  test    rax, rax
0x14002e542  jnz     short loc_14002E56B
0x14002e544  call    cs:__imp_GetLastError
0x14002e54a  mov     ebx, eax
0x14002e54c  test    eax, eax
0x14002e54e  jle     short loc_14002E559
0x14002e550  movzx   ebx, ax
0x14002e553  or      ebx, 80070000h
0x14002e559  lea     r12, aMHwldriver; "m_hWlDriver"
0x14002e560  mov     r15d, 2FDh
0x14002e566  jmp     loc_14002E442
0x14002e56b  lea     rax, aCsessionagentl_1; "CSessionAgentList::StartWebLimitingDriv"...
0x14002e572  mov     [rsp+98h+var_48], 0
0x14002e57a  lea     rcx, [rsp+98h+PerformanceCount]; lpPerformanceCount
0x14002e57f  mov     [rsp+98h+var_58], rax
0x14002e584  call    cs:__imp_QueryPerformanceCounter
0x14002e58a  mov     rcx, [rdi+18h]; hService
0x14002e58e  xor     r8d, r8d; lpServiceArgVectors
0x14002e591  xor     edx, edx; dwNumServiceArgs
0x14002e593  call    cs:__imp_StartServiceW
0x14002e599  test    eax, eax
0x14002e59b  jnz     short loc_14002E5E0
0x14002e59d  call    cs:__imp_GetLastError
0x14002e5a3  cmp     eax, 241h
0x14002e5a8  jnz     short loc_14002E613
0x14002e5aa  xor     ebx, ebx
0x14002e5ac  lea     rax, aWebLimitingDri; "Web limiting driver is not signed"
0x14002e5b3  mov     qword ptr [rsp+98h+var_70], rax
0x14002e5b8  lea     rdi, aCsessionagentl_39; "CSessionAgentList::StartWebLimitingDriv"...
0x14002e5bf  mov     r9d, 309h
0x14002e5c5  mov     [rsp+98h+var_78], rdi
0x14002e5ca  lea     r8, aTermsrvWmsSrcD_19; "termsrv\\wms\\src\\devices\\wmssvc\\ses"...
0x14002e5d1  lea     ecx, [rbx+4]; unsigned __int8
0x14002e5d4  lea     rdx, aSDSTestFailedS; "%s(%d) - %s - Test failed:  %s\n"
0x14002e5db  call    ?DEBUGMSGLEVEL@@YAXEPEBGZZ; DEBUGMSGLEVEL(uchar,ushort const *,...)
0x14002e5e0  lea     rcx, [rsp+98h+var_58]; this
0x14002e5e5  call    ??1CPerfTrace@@QEAA@XZ; CPerfTrace::~CPerfTrace(void)
0x14002e5ea  lea     rcx, aCsessionagentl_3; "CSessionAgentList::StartWebLimitingDriv"...
0x14002e5f1  call    ?DEBUGMSG@@YAXPEBGZZ; DEBUGMSG(ushort const *,...)
0x14002e5f6  test    rbp, rbp
0x14002e5f9  jz      short loc_14002E604
0x14002e5fb  mov     rcx, rbp; hSCObject
0x14002e5fe  call    cs:__imp_CloseServiceHandle
0x14002e604  mov     eax, ebx
0x14002e606  add     rsp, 68h
0x14002e60a  pop     r15
0x14002e60c  pop     r12
0x14002e60e  pop     rdi
0x14002e60f  pop     rsi
0x14002e610  pop     rbp
0x14002e611  pop     rbx
0x14002e612  retn
0x14002e613  call    cs:__imp_GetLastError
0x14002e619  cmp     eax, 420h
0x14002e61e  jz      short loc_14002E5E0
0x14002e620  call    cs:__imp_GetLastError
0x14002e626  mov     ebx, eax
0x14002e628  test    eax, eax
0x14002e62a  jle     short loc_14002E635
0x14002e62c  movzx   ebx, ax
0x14002e62f  or      ebx, 80070000h
0x14002e635  mov     eax, 80004005h
0x14002e63a  lea     rsi, aCbraex; "CBRAEx"
0x14002e641  test    ebx, ebx
0x14002e643  lea     rdi, aCsessionagentl_39; "CSessionAgentList::StartWebLimitingDriv"...
0x14002e64a  mov     r15d, 30Ah
0x14002e650  lea     r12, aFsuccessGetlas_4; "fSuccess || ::GetLastError () == 1056L"
0x14002e657  cmovns  ebx, eax
0x14002e65a  lea     rcx, aTermsrvWmsSrcD_19; "termsrv\\wms\\src\\devices\\wmssvc\\ses"...
0x14002e661  mov     [rsp+98h+var_70], ebx; int
0x14002e665  mov     r9, rsi; unsigned __int16 *
0x14002e668  mov     r8, rdi; unsigned __int16 *
0x14002e66b  mov     [rsp+98h+var_78], r12; unsigned __int16 *
0x14002e670  mov     edx, r15d; unsigned int
0x14002e673  call    ?LOGASSERTHR@@YAXPEBGK000J@Z; LOGASSERTHR(ushort const *,ulong,ushort const *,ushort const *,ushort const *,long)
0x14002e678  call    cs:__imp_IsDebuggerPresent
0x14002e67e  test    eax, eax
0x14002e680  jz      short loc_14002E6B2
0x14002e682  mov     [rsp+98h+var_60], ebx
0x14002e686  lea     r8, aTermsrvWmsSrcD_19; "termsrv\\wms\\src\\devices\\wmssvc\\ses"...
0x14002e68d  mov     [rsp+98h+var_68], r12
0x14002e692  lea     rdx, aSDSAssertionFa_0; "%s(%d) - %s - Assertion failed:  %s (%s"...
0x14002e699  mov     qword ptr [rsp+98h+var_70], rsi
0x14002e69e  mov     r9d, r15d
0x14002e6a1  mov     ecx, 2; unsigned __int8
0x14002e6a6  mov     [rsp+98h+var_78], rdi
0x14002e6ab  call    ?DEBUGMSGLEVEL@@YAXEPEBGZZ; DEBUGMSGLEVEL(uchar,ushort const *,...)
0x14002e6b0  jmp     short loc_14002E6D9
0x14002e6b2  mov     dword ptr [rsp+98h+var_68], ebx
0x14002e6b6  lea     rdx, aTermsrvWmsSrcD_19; "termsrv\\wms\\src\\devices\\wmssvc\\ses"...
0x14002e6bd  mov     qword ptr [rsp+98h+var_70], r12
0x14002e6c2  lea     rcx, aAssertionFaile; "Assertion failed:  %s(%d) - %s - %s (%s"...
0x14002e6c9  mov     r9, rdi
0x14002e6cc  mov     [rsp+98h+var_78], rsi
0x14002e6d1  mov     r8d, r15d
0x14002e6d4  call    ?DEBUGMSGBOX@@YAHPEBGZZ; DEBUGMSGBOX(ushort const *,...)
0x14002e6d9  lea     rcx, [rsp+98h+var_58]; this
0x14002e6de  call    ??1CPerfTrace@@QEAA@XZ; CPerfTrace::~CPerfTrace(void)
0x14002e6e3  cmp     ebx, 80070420h
0x14002e6e9  jnz     short loc_14002E6F7
0x14002e6eb  lea     rcx, aCsessionagentl_14; "CSessionAgentList::StartWebLimitingDriv"...
0x14002e6f2  jmp     loc_14002E5F1
0x14002e6f7  test    ebx, ebx
0x14002e6f9  jns     loc_14002E5EA
0x14002e6ff  mov     edx, ebx
0x14002e701  lea     rcx, aCsessionagentl_10; "CSessionAgentList::StartWebLimitingDriv"...
0x14002e708  call    ?DEBUGMSG@@YAXPEBGZZ; DEBUGMSG(ushort const *,...)
0x14002e70d  jmp     loc_14002E5F6
```
