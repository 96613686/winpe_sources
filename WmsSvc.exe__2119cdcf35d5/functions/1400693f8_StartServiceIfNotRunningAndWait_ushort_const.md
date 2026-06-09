# StartServiceIfNotRunningAndWait(ushort const *)

- ea: `0x1400693f8`
- end: `0x14006975a`
- name: `?StartServiceIfNotRunningAndWait@@YAJPEBG@Z`
- size: `866`
- prototype: `__int64 __fastcall(const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `7`
- tags: `service_task, broker_com_uri`

## callers

- `0x140014210`

## callees

- `0x14005bc30`
- `0x14005bc68`
- `0x14005bfec`
- `0x14005c408`
- `0x140065368`
- `0x1400693f8`
- `0x14007cbd0`

## import_xrefs

- `ADVAPI32!OpenSCManagerW` at `0x14006944a`
- `ADVAPI32!OpenSCManagerW` at `0x14006944a`
- `ADVAPI32!OpenServiceW` at `0x140069524`
- `ADVAPI32!OpenServiceW` at `0x140069524`
- `ADVAPI32!QueryServiceStatus` at `0x1400695fa`
- `ADVAPI32!QueryServiceStatus` at `0x1400695fa`
- `ADVAPI32!CloseServiceHandle` at `0x14006972b`
- `ADVAPI32!CloseServiceHandle` at `0x140069734`
- `ADVAPI32!CloseServiceHandle` at `0x14006972b`
- `ADVAPI32!CloseServiceHandle` at `0x140069734`
- `ADVAPI32!StartServiceW` at `0x1400696db`
- `ADVAPI32!StartServiceW` at `0x1400696db`
- `KERNEL32!GetLastError` at `0x14006945c`
- `KERNEL32!GetLastError` at `0x140069536`
- `KERNEL32!GetLastError` at `0x140069608`
- `KERNEL32!GetLastError` at `0x1400696e5`
- `KERNEL32!GetLastError` at `0x1400696f2`
- `KERNEL32!GetLastError` at `0x14006945c`
- `KERNEL32!GetLastError` at `0x140069536`
- `KERNEL32!GetLastError` at `0x140069608`
- `KERNEL32!GetLastError` at `0x1400696e5`
- `KERNEL32!GetLastError` at `0x1400696f2`
- `KERNEL32!IsDebuggerPresent` at `0x1400694b7`
- `KERNEL32!IsDebuggerPresent` at `0x140069591`
- `KERNEL32!IsDebuggerPresent` at `0x140069663`
- `KERNEL32!IsDebuggerPresent` at `0x1400694b7`
- `KERNEL32!IsDebuggerPresent` at `0x140069591`
- `KERNEL32!IsDebuggerPresent` at `0x140069663`

## string_xrefs

- `0x140069570`: `hService != 0`
- `0x140069441`: `ServicesActive`
- `0x14006948c`: `termsrv\wms\src\common\srcutils\srcutils.cpp`
- `0x140069566`: `termsrv\wms\src\common\srcutils\srcutils.cpp`
- `0x14006963f`: `termsrv\wms\src\common\srcutils\srcutils.cpp`
- `0x140069496`: `hServiceManager != 0`
- `0x14006942a`: `StartServiceIfNotRunningAndWait - %s.\n`
- `0x14006947f`: `StartServiceIfNotRunningAndWait`
- `0x140069559`: `StartServiceIfNotRunningAndWait`
- `0x14006962f`: `StartServiceIfNotRunningAndWait`

## pseudocode

```c
__int64 __fastcall StartServiceIfNotRunningAndWait(const unsigned __int16 *a1)
{
  SC_HANDLE v1; // rax
  SC_HANDLE v2; // r15
  signed int v3; // eax
  signed int started; // ebx
  SC_HANDLE v5; // rax
  SC_HANDLE v6; // r14
  signed int LastError; // eax
  signed int v8; // eax
  const unsigned __int16 *v9; // r13
  unsigned int v10; // r12d
  signed int v11; // eax
  struct _SERVICE_STATUS ServiceStatus; // [rsp+40h] [rbp-78h] BYREF

  memset(&ServiceStatus, 0, sizeof(ServiceStatus));
  DEBUGMSG(L"StartServiceIfNotRunningAndWait - %s.\n", L"LanmanWorkstation");
  v1 = OpenSCManagerW(0, L"ServicesActive", 0x80000000);
  v2 = v1;
  if ( v1 )
  {
    v5 = OpenServiceW(v1, L"LanmanWorkstation", 0x80000010);
    v6 = v5;
    if ( !v5 )
    {
      LastError = GetLastError();
      started = LastError;
      if ( LastError > 0 )
        started = (unsigned __int16)LastError | 0x80070000;
      if ( started >= 0 )
        started = -2147467259;
      LOGASSERTHR(
        L"termsrv\\wms\\src\\common\\srcutils\\srcutils.cpp",
        0xBB1u,
        L"StartServiceIfNotRunningAndWait",
        L"CBRAEx",
        L"hService != 0",
        started);
      if ( IsDebuggerPresent() )
        DEBUGMSGLEVEL(
          2u,
          L"%s(%d) - %s - Assertion failed:  %s (%s)  hr = 0x%08X\n",
          L"termsrv\\wms\\src\\common\\srcutils\\srcutils.cpp",
          2993,
          L"StartServiceIfNotRunningAndWait",
          L"CBRAEx",
          L"hService != 0",
          started);
      else
        DEBUGMSGBOX(
          L"Assertion failed:  %s(%d) - %s - %s (%s)  hr = 0x%08X\n\n",
          L"termsrv\\wms\\src\\common\\srcutils\\srcutils.cpp",
          2993,
          L"StartServiceIfNotRunningAndWait",
          L"CBRAEx",
          L"hService != 0",
          started);
      goto LABEL_36;
    }
    if ( !QueryServiceStatus(v5, &ServiceStatus) )
    {
      v8 = GetLastError();
      started = v8;
      if ( v8 > 0 )
        started = (unsigned __int16)v8 | 0x80070000;
      v9 = L"fSuccess";
      v10 = 2997;
LABEL_21:
      if ( started >= 0 )
        started = -2147467259;
      LOGASSERTHR(
        L"termsrv\\wms\\src\\common\\srcutils\\srcutils.cpp",
        v10,
        L"StartServiceIfNotRunningAndWait",
        L"CBRAEx",
        v9,
        started);
      if ( IsDebuggerPresent() )
        DEBUGMSGLEVEL(
          2u,
          L"%s(%d) - %s - Assertion failed:  %s (%s)  hr = 0x%08X\n",
          L"termsrv\\wms\\src\\common\\srcutils\\srcutils.cpp",
          v10,
          L"StartServiceIfNotRunningAndWait",
          L"CBRAEx",
          v9,
          started);
      else
        DEBUGMSGBOX(
          L"Assertion failed:  %s(%d) - %s - %s (%s)  hr = 0x%08X\n\n",
          L"termsrv\\wms\\src\\common\\srcutils\\srcutils.cpp",
          v10,
          L"StartServiceIfNotRunningAndWait",
          L"CBRAEx",
          v9,
          started);
      goto LABEL_35;
    }
    if ( ServiceStatus.dwCurrentState == 4 )
    {
      started = 0;
    }
    else
    {
      if ( ServiceStatus.dwCurrentState != 2 && !StartServiceW(v6, 0, 0) && GetLastError() != 1056 )
      {
        v11 = GetLastError();
        started = v11;
        if ( v11 > 0 )
          started = (unsigned __int16)v11 | 0x80070000;
        v9 = L"fSuccess || (::GetLastError () == 1056L)";
        v10 = 3003;
        goto LABEL_21;
      }
      started = ConditionalWaitForServiceStartUsingEventToStop(L"LanmanWorkstation", 0, 0);
    }
LABEL_35:
    CloseServiceHandle(v6);
LABEL_36:
    CloseServiceHandle(v2);
    return (unsigned int)started;
  }
  v3 = GetLastError();
  started = v3;
  if ( v3 > 0 )
    started = (unsigned __int16)v3 | 0x80070000;
  if ( started >= 0 )
    started = -2147467259;
  LOGASSERTHR(
    L"termsrv\\wms\\src\\common\\srcutils\\srcutils.cpp",
    0xBADu,
    L"StartServiceIfNotRunningAndWait",
    L"CBRAEx",
    L"hServiceManager != 0",
    started);
  if ( IsDebuggerPresent() )
    DEBUGMSGLEVEL(
      2u,
      L"%s(%d) - %s - Assertion failed:  %s (%s)  hr = 0x%08X\n",
      L"termsrv\\wms\\src\\common\\srcutils\\srcutils.cpp",
      2989,
      L"StartServiceIfNotRunningAndWait",
      L"CBRAEx",
      L"hServiceManager != 0",
      started);
  else
    DEBUGMSGBOX(
      L"Assertion failed:  %s(%d) - %s - %s (%s)  hr = 0x%08X\n\n",
      L"termsrv\\wms\\src\\common\\srcutils\\srcutils.cpp",
      2989,
      L"StartServiceIfNotRunningAndWait",
      L"CBRAEx",
      L"hServiceManager != 0",
      started);
  return (unsigned int)started;
}

```

## disassembly

```asm
0x1400693f8  push    rbx
0x1400693fa  push    rbp
0x1400693fb  push    rsi
0x1400693fc  push    rdi
0x1400693fd  push    r12
0x1400693ff  push    r13
0x140069401  push    r14
0x140069403  push    r15
0x140069405  sub     rsp, 78h
0x140069409  mov     rax, cs:__security_cookie
0x140069410  xor     rax, rsp
0x140069413  mov     [rsp+0B8h+var_58], rax
0x140069418  xorps   xmm0, xmm0
0x14006941b  lea     rbx, aLanmanworkstat; "LanmanWorkstation"
0x140069422  movups  xmmword ptr [rsp+0B8h+ServiceStatus.dwServiceType], xmm0
0x140069427  mov     rdx, rbx
0x14006942a  lea     rcx, aStartserviceif; "StartServiceIfNotRunningAndWait - %s.\n"
0x140069431  movups  xmmword ptr [rsp+0B8h+ServiceStatus.dwWin32ExitCode], xmm0
0x140069436  call    ?DEBUGMSG@@YAXPEBGZZ; DEBUGMSG(ushort const *,...)
0x14006943b  mov     r8d, 80000000h; dwDesiredAccess
0x140069441  lea     rdx, DatabaseName; "ServicesActive"
0x140069448  xor     ecx, ecx; lpMachineName
0x14006944a  call    cs:__imp_OpenSCManagerW
0x140069450  mov     r15, rax
0x140069453  test    rax, rax
0x140069456  jnz     loc_140069518
0x14006945c  call    cs:__imp_GetLastError
0x140069462  mov     ebx, eax
0x140069464  test    eax, eax
0x140069466  jle     short loc_140069471
0x140069468  movzx   ebx, ax
0x14006946b  or      ebx, 80070000h
0x140069471  mov     eax, 80004005h
0x140069476  lea     rbp, aCbraex; "CBRAEx"
0x14006947d  test    ebx, ebx
0x14006947f  lea     rsi, aStartserviceif_0; "StartServiceIfNotRunningAndWait"
0x140069486  mov     r14d, 0BADh
0x14006948c  lea     rdi, aTermsrvWmsSrcC_22; "termsrv\\wms\\src\\common\\srcutils\\sr"...
0x140069493  cmovns  ebx, eax
0x140069496  lea     r15, aHservicemanage; "hServiceManager != 0"
0x14006949d  mov     [rsp+0B8h+var_90], ebx; int
0x1400694a1  mov     r9, rbp; unsigned __int16 *
0x1400694a4  mov     r8, rsi; unsigned __int16 *
0x1400694a7  mov     [rsp+0B8h+var_98], r15; unsigned __int16 *
0x1400694ac  mov     edx, r14d; unsigned int
0x1400694af  mov     rcx, rdi; unsigned __int16 *
0x1400694b2  call    ?LOGASSERTHR@@YAXPEBGK000J@Z; LOGASSERTHR(ushort const *,ulong,ushort const *,ushort const *,ushort const *,long)
0x1400694b7  call    cs:__imp_IsDebuggerPresent
0x1400694bd  test    eax, eax
0x1400694bf  jz      short loc_1400694F0
0x1400694c1  mov     [rsp+0B8h+var_80], ebx
0x1400694c5  lea     rdx, aSDSAssertionFa_0; "%s(%d) - %s - Assertion failed:  %s (%s"...
0x1400694cc  mov     [rsp+0B8h+var_88], r15
0x1400694d1  mov     r9d, r14d
0x1400694d4  mov     qword ptr [rsp+0B8h+var_90], rbp
0x1400694d9  mov     r8, rdi
0x1400694dc  mov     ecx, 2; unsigned __int8
0x1400694e1  mov     [rsp+0B8h+var_98], rsi
0x1400694e6  call    ?DEBUGMSGLEVEL@@YAXEPEBGZZ; DEBUGMSGLEVEL(uchar,ushort const *,...)
0x1400694eb  jmp     loc_14006973A
0x1400694f0  mov     dword ptr [rsp+0B8h+var_88], ebx
0x1400694f4  lea     rcx, aAssertionFaile; "Assertion failed:  %s(%d) - %s - %s (%s"...
0x1400694fb  mov     qword ptr [rsp+0B8h+var_90], r15
0x140069500  mov     r9, rsi
0x140069503  mov     r8d, r14d
0x140069506  mov     [rsp+0B8h+var_98], rbp
0x14006950b  mov     rdx, rdi
0x14006950e  call    ?DEBUGMSGBOX@@YAHPEBGZZ; DEBUGMSGBOX(ushort const *,...)
0x140069513  jmp     loc_14006973A
0x140069518  mov     r8d, 80000010h; dwDesiredAccess
0x14006951e  mov     rdx, rbx; lpServiceName
0x140069521  mov     rcx, r15; hSCManager
0x140069524  call    cs:__imp_OpenServiceW
0x14006952a  mov     r14, rax
0x14006952d  test    rax, rax
0x140069530  jnz     loc_1400695F2
0x140069536  call    cs:__imp_GetLastError
0x14006953c  mov     ebx, eax
0x14006953e  test    eax, eax
0x140069540  jle     short loc_14006954B
0x140069542  movzx   ebx, ax
0x140069545  or      ebx, 80070000h
0x14006954b  mov     eax, 80004005h
0x140069550  lea     rbp, aCbraex; "CBRAEx"
0x140069557  test    ebx, ebx
0x140069559  lea     rsi, aStartserviceif_0; "StartServiceIfNotRunningAndWait"
0x140069560  mov     r14d, 0BB1h
0x140069566  lea     rdi, aTermsrvWmsSrcC_22; "termsrv\\wms\\src\\common\\srcutils\\sr"...
0x14006956d  cmovns  ebx, eax
0x140069570  lea     r12, aHservice0; "hService != 0"
0x140069577  mov     [rsp+0B8h+var_90], ebx; int
0x14006957b  mov     r9, rbp; unsigned __int16 *
0x14006957e  mov     r8, rsi; unsigned __int16 *
0x140069581  mov     [rsp+0B8h+var_98], r12; unsigned __int16 *
0x140069586  mov     edx, r14d; unsigned int
0x140069589  mov     rcx, rdi; unsigned __int16 *
0x14006958c  call    ?LOGASSERTHR@@YAXPEBGK000J@Z; LOGASSERTHR(ushort const *,ulong,ushort const *,ushort const *,ushort const *,long)
0x140069591  call    cs:__imp_IsDebuggerPresent
0x140069597  test    eax, eax
0x140069599  jz      short loc_1400695CA
0x14006959b  mov     [rsp+0B8h+var_80], ebx
0x14006959f  lea     rdx, aSDSAssertionFa_0; "%s(%d) - %s - Assertion failed:  %s (%s"...
0x1400695a6  mov     [rsp+0B8h+var_88], r12
0x1400695ab  mov     r9d, r14d
0x1400695ae  mov     qword ptr [rsp+0B8h+var_90], rbp
0x1400695b3  mov     r8, rdi
0x1400695b6  mov     ecx, 2; unsigned __int8
0x1400695bb  mov     [rsp+0B8h+var_98], rsi
0x1400695c0  call    ?DEBUGMSGLEVEL@@YAXEPEBGZZ; DEBUGMSGLEVEL(uchar,ushort const *,...)
0x1400695c5  jmp     loc_140069731
0x1400695ca  mov     dword ptr [rsp+0B8h+var_88], ebx
0x1400695ce  lea     rcx, aAssertionFaile; "Assertion failed:  %s(%d) - %s - %s (%s"...
0x1400695d5  mov     qword ptr [rsp+0B8h+var_90], r12
0x1400695da  mov     r9, rsi
0x1400695dd  mov     r8d, r14d
0x1400695e0  mov     [rsp+0B8h+var_98], rbp
0x1400695e5  mov     rdx, rdi
0x1400695e8  call    ?DEBUGMSGBOX@@YAHPEBGZZ; DEBUGMSGBOX(ushort const *,...)
0x1400695ed  jmp     loc_140069731
0x1400695f2  lea     rdx, [rsp+0B8h+ServiceStatus]; lpServiceStatus
0x1400695f7  mov     rcx, r14; hService
0x1400695fa  call    cs:__imp_QueryServiceStatus
0x140069600  test    eax, eax
0x140069602  jnz     loc_1400696C1
0x140069608  call    cs:__imp_GetLastError
0x14006960e  mov     ebx, eax
0x140069610  test    eax, eax
0x140069612  jle     short loc_14006961D
0x140069614  movzx   ebx, ax
0x140069617  or      ebx, 80070000h
0x14006961d  lea     r13, aFsuccess; "fSuccess"
0x140069624  mov     r12d, 0BB5h
0x14006962a  mov     eax, 80004005h
0x14006962f  lea     rsi, aStartserviceif_0; "StartServiceIfNotRunningAndWait"
0x140069636  test    ebx, ebx
0x140069638  lea     rbp, aCbraex; "CBRAEx"
0x14006963f  lea     rdi, aTermsrvWmsSrcC_22; "termsrv\\wms\\src\\common\\srcutils\\sr"...
0x140069646  mov     r8, rsi; unsigned __int16 *
0x140069649  cmovns  ebx, eax
0x14006964c  mov     r9, rbp; unsigned __int16 *
0x14006964f  mov     [rsp+0B8h+var_90], ebx; int
0x140069653  mov     edx, r12d; unsigned int
0x140069656  mov     rcx, rdi; unsigned __int16 *
0x140069659  mov     [rsp+0B8h+var_98], r13; unsigned __int16 *
0x14006965e  call    ?LOGASSERTHR@@YAXPEBGK000J@Z; LOGASSERTHR(ushort const *,ulong,ushort const *,ushort const *,ushort const *,long)
0x140069663  call    cs:__imp_IsDebuggerPresent
0x140069669  test    eax, eax
0x14006966b  jz      short loc_14006969C
0x14006966d  mov     [rsp+0B8h+var_80], ebx
0x140069671  lea     rdx, aSDSAssertionFa_0; "%s(%d) - %s - Assertion failed:  %s (%s"...
0x140069678  mov     [rsp+0B8h+var_88], r13
0x14006967d  mov     r9d, r12d
0x140069680  mov     qword ptr [rsp+0B8h+var_90], rbp
0x140069685  mov     r8, rdi
0x140069688  mov     ecx, 2; unsigned __int8
0x14006968d  mov     [rsp+0B8h+var_98], rsi
0x140069692  call    ?DEBUGMSGLEVEL@@YAXEPEBGZZ; DEBUGMSGLEVEL(uchar,ushort const *,...)
0x140069697  jmp     loc_140069728
0x14006969c  mov     dword ptr [rsp+0B8h+var_88], ebx
0x1400696a0  lea     rcx, aAssertionFaile; "Assertion failed:  %s(%d) - %s - %s (%s"...
0x1400696a7  mov     qword ptr [rsp+0B8h+var_90], r13
0x1400696ac  mov     r9, rsi
0x1400696af  mov     r8d, r12d
0x1400696b2  mov     [rsp+0B8h+var_98], rbp
0x1400696b7  mov     rdx, rdi
0x1400696ba  call    ?DEBUGMSGBOX@@YAHPEBGZZ; DEBUGMSGBOX(ushort const *,...)
0x1400696bf  jmp     short loc_140069728
0x1400696c1  cmp     [rsp+0B8h+ServiceStatus.dwCurrentState], 4
0x1400696c6  jnz     short loc_1400696CC
0x1400696c8  xor     ebx, ebx
0x1400696ca  jmp     short loc_140069728
0x1400696cc  cmp     [rsp+0B8h+ServiceStatus.dwCurrentState], 2
0x1400696d1  jz      short loc_140069719
0x1400696d3  xor     r8d, r8d; lpServiceArgVectors
0x1400696d6  xor     edx, edx; dwNumServiceArgs
0x1400696d8  mov     rcx, r14; hService
0x1400696db  call    cs:__imp_StartServiceW
0x1400696e1  test    eax, eax
0x1400696e3  jnz     short loc_140069719
0x1400696e5  call    cs:__imp_GetLastError
0x1400696eb  cmp     eax, 420h
0x1400696f0  jz      short loc_140069719
0x1400696f2  call    cs:__imp_GetLastError
0x1400696f8  mov     ebx, eax
0x1400696fa  test    eax, eax
0x1400696fc  jle     short loc_140069707
0x1400696fe  movzx   ebx, ax
0x140069701  or      ebx, 80070000h
0x140069707  lea     r13, aFsuccessGetlas_3; "fSuccess || (::GetLastError () == 1056L"...
0x14006970e  mov     r12d, 0BBBh
0x140069714  jmp     loc_14006962A
0x140069719  xor     r8d, r8d; int *
0x14006971c  xor     edx, edx; void *
0x14006971e  mov     rcx, rbx; unsigned __int16 *
0x140069721  call    ?ConditionalWaitForServiceStartUsingEventToStop@@YAJPEBGPEAXPEAH@Z; ConditionalWaitForServiceStartUsingEventToStop(ushort const *,void *,int *)
0x140069726  mov     ebx, eax
0x140069728  mov     rcx, r14; hSCObject
0x14006972b  call    cs:__imp_CloseServiceHandle
0x140069731  mov     rcx, r15; hSCObject
0x140069734  call    cs:__imp_CloseServiceHandle
0x14006973a  mov     eax, ebx
0x14006973c  mov     rcx, [rsp+0B8h+var_58]
0x140069741  xor     rcx, rsp; StackCookie
0x140069744  call    __security_check_cookie
0x140069749  add     rsp, 78h
0x14006974d  pop     r15
0x14006974f  pop     r14
0x140069751  pop     r13
0x140069753  pop     r12
0x140069755  pop     rdi
0x140069756  pop     rsi
0x140069757  pop     rbp
0x140069758  pop     rbx
0x140069759  retn
```
