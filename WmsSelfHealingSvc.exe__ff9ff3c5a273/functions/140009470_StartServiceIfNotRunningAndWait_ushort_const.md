# StartServiceIfNotRunningAndWait(ushort const *)

- ea: `0x140009470`
- end: `0x1400097cb`
- name: `?StartServiceIfNotRunningAndWait@@YAJPEBG@Z`
- size: `859`
- prototype: `__int64 __fastcall(const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `7`
- tags: `service_task, broker_com_uri`

## callers

- `0x1400029e8`

## callees

- `0x1400036a0`
- `0x1400036d8`
- `0x140003918`
- `0x140003c2c`
- `0x1400068bc`
- `0x140009470`
- `0x14000ae60`

## import_xrefs

- `ADVAPI32!StartServiceW` at `0x140009754`
- `ADVAPI32!StartServiceW` at `0x140009754`
- `ADVAPI32!QueryServiceStatus` at `0x140009673`
- `ADVAPI32!QueryServiceStatus` at `0x140009673`
- `ADVAPI32!OpenServiceW` at `0x14000959d`
- `ADVAPI32!OpenServiceW` at `0x14000959d`
- `ADVAPI32!CloseServiceHandle` at `0x14000979c`
- `ADVAPI32!CloseServiceHandle` at `0x1400097a5`
- `ADVAPI32!CloseServiceHandle` at `0x14000979c`
- `ADVAPI32!CloseServiceHandle` at `0x1400097a5`
- `ADVAPI32!OpenSCManagerW` at `0x1400094bf`
- `ADVAPI32!OpenSCManagerW` at `0x1400094bf`
- `KERNEL32!IsDebuggerPresent` at `0x14000952c`
- `KERNEL32!IsDebuggerPresent` at `0x14000960a`
- `KERNEL32!IsDebuggerPresent` at `0x1400096dc`
- `KERNEL32!IsDebuggerPresent` at `0x14000952c`
- `KERNEL32!IsDebuggerPresent` at `0x14000960a`
- `KERNEL32!IsDebuggerPresent` at `0x1400096dc`
- `KERNEL32!GetLastError` at `0x1400094d1`
- `KERNEL32!GetLastError` at `0x1400095af`
- `KERNEL32!GetLastError` at `0x140009681`
- `KERNEL32!GetLastError` at `0x14000975e`
- `KERNEL32!GetLastError` at `0x14000976b`
- `KERNEL32!GetLastError` at `0x1400094d1`
- `KERNEL32!GetLastError` at `0x1400095af`
- `KERNEL32!GetLastError` at `0x140009681`
- `KERNEL32!GetLastError` at `0x14000975e`
- `KERNEL32!GetLastError` at `0x14000976b`

## string_xrefs

- `0x1400095e9`: `hService != 0`
- `0x140009501`: `termsrv\wms\src\common\srcutils\srcutils.cpp`
- `0x1400095df`: `termsrv\wms\src\common\srcutils\srcutils.cpp`
- `0x1400096b8`: `termsrv\wms\src\common\srcutils\srcutils.cpp`
- `0x1400094b6`: `ServicesActive`
- `0x14000950b`: `hServiceManager != 0`
- `0x14000949f`: `StartServiceIfNotRunningAndWait - %s.\n`
- `0x1400094f4`: `StartServiceIfNotRunningAndWait`
- `0x1400095d2`: `StartServiceIfNotRunningAndWait`
- `0x1400096a8`: `StartServiceIfNotRunningAndWait`

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
  void *v8; // rdx
  const unsigned __int16 *v9; // rcx
  int *v10; // r8
  signed int v11; // eax
  const unsigned __int16 *v12; // r13
  unsigned int v13; // r12d
  signed int v14; // eax
  struct _SERVICE_STATUS ServiceStatus; // [rsp+40h] [rbp-78h] BYREF

  memset(&ServiceStatus, 0, sizeof(ServiceStatus));
  DEBUGMSG(L"StartServiceIfNotRunningAndWait - %s.\n", L"Wms");
  v1 = OpenSCManagerW(0, L"ServicesActive", 0x80000000);
  v2 = v1;
  if ( v1 )
  {
    v5 = OpenServiceW(v1, L"Wms", 0x80000010);
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
      v11 = GetLastError();
      started = v11;
      if ( v11 > 0 )
        started = (unsigned __int16)v11 | 0x80070000;
      v12 = L"fSuccess";
      v13 = 2997;
LABEL_21:
      if ( started >= 0 )
        started = -2147467259;
      LOGASSERTHR(
        L"termsrv\\wms\\src\\common\\srcutils\\srcutils.cpp",
        v13,
        L"StartServiceIfNotRunningAndWait",
        L"CBRAEx",
        v12,
        started);
      if ( IsDebuggerPresent() )
        DEBUGMSGLEVEL(
          2u,
          L"%s(%d) - %s - Assertion failed:  %s (%s)  hr = 0x%08X\n",
          L"termsrv\\wms\\src\\common\\srcutils\\srcutils.cpp",
          v13,
          L"StartServiceIfNotRunningAndWait",
          L"CBRAEx",
          v12,
          started);
      else
        DEBUGMSGBOX(
          L"Assertion failed:  %s(%d) - %s - %s (%s)  hr = 0x%08X\n\n",
          L"termsrv\\wms\\src\\common\\srcutils\\srcutils.cpp",
          v13,
          L"StartServiceIfNotRunningAndWait",
          L"CBRAEx",
          v12,
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
        v14 = GetLastError();
        started = v14;
        if ( v14 > 0 )
          started = (unsigned __int16)v14 | 0x80070000;
        v12 = L"fSuccess || (::GetLastError () == 1056L)";
        v13 = 3003;
        goto LABEL_21;
      }
      started = ConditionalWaitForServiceStartUsingEventToStop(v9, v8, v10);
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
0x140009470  push    rbx
0x140009472  push    rbp
0x140009473  push    rsi
0x140009474  push    rdi
0x140009475  push    r12
0x140009477  push    r13
0x140009479  push    r14
0x14000947b  push    r15
0x14000947d  sub     rsp, 78h
0x140009481  mov     rax, cs:__security_cookie
0x140009488  xor     rax, rsp
0x14000948b  mov     [rsp+0B8h+var_58], rax
0x140009490  xorps   xmm0, xmm0
0x140009493  lea     rdx, ServiceName; "Wms"
0x14000949a  movups  xmmword ptr [rsp+0B8h+ServiceStatus.dwServiceType], xmm0
0x14000949f  lea     rcx, aStartserviceif; "StartServiceIfNotRunningAndWait - %s.\n"
0x1400094a6  movups  xmmword ptr [rsp+0B8h+ServiceStatus.dwWin32ExitCode], xmm0
0x1400094ab  call    ?DEBUGMSG@@YAXPEBGZZ; DEBUGMSG(ushort const *,...)
0x1400094b0  mov     r8d, 80000000h; dwDesiredAccess
0x1400094b6  lea     rdx, DatabaseName; "ServicesActive"
0x1400094bd  xor     ecx, ecx; lpMachineName
0x1400094bf  call    cs:__imp_OpenSCManagerW
0x1400094c5  mov     r15, rax
0x1400094c8  test    rax, rax
0x1400094cb  jnz     loc_14000958D
0x1400094d1  call    cs:__imp_GetLastError
0x1400094d7  mov     ebx, eax
0x1400094d9  test    eax, eax
0x1400094db  jle     short loc_1400094E6
0x1400094dd  movzx   ebx, ax
0x1400094e0  or      ebx, 80070000h
0x1400094e6  mov     eax, 80004005h
0x1400094eb  lea     rbp, aCbraex; "CBRAEx"
0x1400094f2  test    ebx, ebx
0x1400094f4  lea     rsi, aStartserviceif_0; "StartServiceIfNotRunningAndWait"
0x1400094fb  mov     r14d, 0BADh
0x140009501  lea     rdi, aTermsrvWmsSrcC_4; "termsrv\\wms\\src\\common\\srcutils\\sr"...
0x140009508  cmovns  ebx, eax
0x14000950b  lea     r15, aHservicemanage; "hServiceManager != 0"
0x140009512  mov     [rsp+0B8h+var_90], ebx; int
0x140009516  mov     r9, rbp; unsigned __int16 *
0x140009519  mov     r8, rsi; unsigned __int16 *
0x14000951c  mov     [rsp+0B8h+var_98], r15; unsigned __int16 *
0x140009521  mov     edx, r14d; unsigned int
0x140009524  mov     rcx, rdi; unsigned __int16 *
0x140009527  call    ?LOGASSERTHR@@YAXPEBGK000J@Z; LOGASSERTHR(ushort const *,ulong,ushort const *,ushort const *,ushort const *,long)
0x14000952c  call    cs:__imp_IsDebuggerPresent
0x140009532  test    eax, eax
0x140009534  jz      short loc_140009565
0x140009536  mov     [rsp+0B8h+var_80], ebx
0x14000953a  lea     rdx, aSDSAssertionFa_0; "%s(%d) - %s - Assertion failed:  %s (%s"...
0x140009541  mov     [rsp+0B8h+var_88], r15
0x140009546  mov     r9d, r14d
0x140009549  mov     qword ptr [rsp+0B8h+var_90], rbp
0x14000954e  mov     r8, rdi
0x140009551  mov     ecx, 2; unsigned __int8
0x140009556  mov     [rsp+0B8h+var_98], rsi
0x14000955b  call    ?DEBUGMSGLEVEL@@YAXEPEBGZZ; DEBUGMSGLEVEL(uchar,ushort const *,...)
0x140009560  jmp     loc_1400097AB
0x140009565  mov     dword ptr [rsp+0B8h+var_88], ebx
0x140009569  lea     rcx, aAssertionFaile; "Assertion failed:  %s(%d) - %s - %s (%s"...
0x140009570  mov     qword ptr [rsp+0B8h+var_90], r15
0x140009575  mov     r9, rsi
0x140009578  mov     r8d, r14d
0x14000957b  mov     [rsp+0B8h+var_98], rbp
0x140009580  mov     rdx, rdi
0x140009583  call    ?DEBUGMSGBOX@@YAHPEBGZZ; DEBUGMSGBOX(ushort const *,...)
0x140009588  jmp     loc_1400097AB
0x14000958d  mov     r8d, 80000010h; dwDesiredAccess
0x140009593  lea     rdx, ServiceName; "Wms"
0x14000959a  mov     rcx, r15; hSCManager
0x14000959d  call    cs:__imp_OpenServiceW
0x1400095a3  mov     r14, rax
0x1400095a6  test    rax, rax
0x1400095a9  jnz     loc_14000966B
0x1400095af  call    cs:__imp_GetLastError
0x1400095b5  mov     ebx, eax
0x1400095b7  test    eax, eax
0x1400095b9  jle     short loc_1400095C4
0x1400095bb  movzx   ebx, ax
0x1400095be  or      ebx, 80070000h
0x1400095c4  mov     eax, 80004005h
0x1400095c9  lea     rbp, aCbraex; "CBRAEx"
0x1400095d0  test    ebx, ebx
0x1400095d2  lea     rsi, aStartserviceif_0; "StartServiceIfNotRunningAndWait"
0x1400095d9  mov     r14d, 0BB1h
0x1400095df  lea     rdi, aTermsrvWmsSrcC_4; "termsrv\\wms\\src\\common\\srcutils\\sr"...
0x1400095e6  cmovns  ebx, eax
0x1400095e9  lea     r12, aHservice0; "hService != 0"
0x1400095f0  mov     [rsp+0B8h+var_90], ebx; int
0x1400095f4  mov     r9, rbp; unsigned __int16 *
0x1400095f7  mov     r8, rsi; unsigned __int16 *
0x1400095fa  mov     [rsp+0B8h+var_98], r12; unsigned __int16 *
0x1400095ff  mov     edx, r14d; unsigned int
0x140009602  mov     rcx, rdi; unsigned __int16 *
0x140009605  call    ?LOGASSERTHR@@YAXPEBGK000J@Z; LOGASSERTHR(ushort const *,ulong,ushort const *,ushort const *,ushort const *,long)
0x14000960a  call    cs:__imp_IsDebuggerPresent
0x140009610  test    eax, eax
0x140009612  jz      short loc_140009643
0x140009614  mov     [rsp+0B8h+var_80], ebx
0x140009618  lea     rdx, aSDSAssertionFa_0; "%s(%d) - %s - Assertion failed:  %s (%s"...
0x14000961f  mov     [rsp+0B8h+var_88], r12
0x140009624  mov     r9d, r14d
0x140009627  mov     qword ptr [rsp+0B8h+var_90], rbp
0x14000962c  mov     r8, rdi
0x14000962f  mov     ecx, 2; unsigned __int8
0x140009634  mov     [rsp+0B8h+var_98], rsi
0x140009639  call    ?DEBUGMSGLEVEL@@YAXEPEBGZZ; DEBUGMSGLEVEL(uchar,ushort const *,...)
0x14000963e  jmp     loc_1400097A2
0x140009643  mov     dword ptr [rsp+0B8h+var_88], ebx
0x140009647  lea     rcx, aAssertionFaile; "Assertion failed:  %s(%d) - %s - %s (%s"...
0x14000964e  mov     qword ptr [rsp+0B8h+var_90], r12
0x140009653  mov     r9, rsi
0x140009656  mov     r8d, r14d
0x140009659  mov     [rsp+0B8h+var_98], rbp
0x14000965e  mov     rdx, rdi
0x140009661  call    ?DEBUGMSGBOX@@YAHPEBGZZ; DEBUGMSGBOX(ushort const *,...)
0x140009666  jmp     loc_1400097A2
0x14000966b  lea     rdx, [rsp+0B8h+ServiceStatus]; lpServiceStatus
0x140009670  mov     rcx, r14; hService
0x140009673  call    cs:__imp_QueryServiceStatus
0x140009679  test    eax, eax
0x14000967b  jnz     loc_14000973A
0x140009681  call    cs:__imp_GetLastError
0x140009687  mov     ebx, eax
0x140009689  test    eax, eax
0x14000968b  jle     short loc_140009696
0x14000968d  movzx   ebx, ax
0x140009690  or      ebx, 80070000h
0x140009696  lea     r13, aFsuccess; "fSuccess"
0x14000969d  mov     r12d, 0BB5h
0x1400096a3  mov     eax, 80004005h
0x1400096a8  lea     rsi, aStartserviceif_0; "StartServiceIfNotRunningAndWait"
0x1400096af  test    ebx, ebx
0x1400096b1  lea     rbp, aCbraex; "CBRAEx"
0x1400096b8  lea     rdi, aTermsrvWmsSrcC_4; "termsrv\\wms\\src\\common\\srcutils\\sr"...
0x1400096bf  mov     r8, rsi; unsigned __int16 *
0x1400096c2  cmovns  ebx, eax
0x1400096c5  mov     r9, rbp; unsigned __int16 *
0x1400096c8  mov     [rsp+0B8h+var_90], ebx; int
0x1400096cc  mov     edx, r12d; unsigned int
0x1400096cf  mov     rcx, rdi; unsigned __int16 *
0x1400096d2  mov     [rsp+0B8h+var_98], r13; unsigned __int16 *
0x1400096d7  call    ?LOGASSERTHR@@YAXPEBGK000J@Z; LOGASSERTHR(ushort const *,ulong,ushort const *,ushort const *,ushort const *,long)
0x1400096dc  call    cs:__imp_IsDebuggerPresent
0x1400096e2  test    eax, eax
0x1400096e4  jz      short loc_140009715
0x1400096e6  mov     [rsp+0B8h+var_80], ebx
0x1400096ea  lea     rdx, aSDSAssertionFa_0; "%s(%d) - %s - Assertion failed:  %s (%s"...
0x1400096f1  mov     [rsp+0B8h+var_88], r13
0x1400096f6  mov     r9d, r12d
0x1400096f9  mov     qword ptr [rsp+0B8h+var_90], rbp
0x1400096fe  mov     r8, rdi
0x140009701  mov     ecx, 2; unsigned __int8
0x140009706  mov     [rsp+0B8h+var_98], rsi
0x14000970b  call    ?DEBUGMSGLEVEL@@YAXEPEBGZZ; DEBUGMSGLEVEL(uchar,ushort const *,...)
0x140009710  jmp     loc_140009799
0x140009715  mov     dword ptr [rsp+0B8h+var_88], ebx
0x140009719  lea     rcx, aAssertionFaile; "Assertion failed:  %s(%d) - %s - %s (%s"...
0x140009720  mov     qword ptr [rsp+0B8h+var_90], r13
0x140009725  mov     r9, rsi
0x140009728  mov     r8d, r12d
0x14000972b  mov     [rsp+0B8h+var_98], rbp
0x140009730  mov     rdx, rdi
0x140009733  call    ?DEBUGMSGBOX@@YAHPEBGZZ; DEBUGMSGBOX(ushort const *,...)
0x140009738  jmp     short loc_140009799
0x14000973a  cmp     [rsp+0B8h+ServiceStatus.dwCurrentState], 4
0x14000973f  jnz     short loc_140009745
0x140009741  xor     ebx, ebx
0x140009743  jmp     short loc_140009799
0x140009745  cmp     [rsp+0B8h+ServiceStatus.dwCurrentState], 2
0x14000974a  jz      short loc_140009792
0x14000974c  xor     r8d, r8d; lpServiceArgVectors
0x14000974f  xor     edx, edx; dwNumServiceArgs
0x140009751  mov     rcx, r14; hService
0x140009754  call    cs:__imp_StartServiceW
0x14000975a  test    eax, eax
0x14000975c  jnz     short loc_140009792
0x14000975e  call    cs:__imp_GetLastError
0x140009764  cmp     eax, 420h
0x140009769  jz      short loc_140009792
0x14000976b  call    cs:__imp_GetLastError
0x140009771  mov     ebx, eax
0x140009773  test    eax, eax
0x140009775  jle     short loc_140009780
0x140009777  movzx   ebx, ax
0x14000977a  or      ebx, 80070000h
0x140009780  lea     r13, aFsuccessGetlas; "fSuccess || (::GetLastError () == 1056L"...
0x140009787  mov     r12d, 0BBBh
0x14000978d  jmp     loc_1400096A3
0x140009792  call    ?ConditionalWaitForServiceStartUsingEventToStop@@YAJPEBGPEAXPEAH@Z; ConditionalWaitForServiceStartUsingEventToStop(ushort const *,void *,int *)
0x140009797  mov     ebx, eax
0x140009799  mov     rcx, r14; hSCObject
0x14000979c  call    cs:__imp_CloseServiceHandle
0x1400097a2  mov     rcx, r15; hSCObject
0x1400097a5  call    cs:__imp_CloseServiceHandle
0x1400097ab  mov     eax, ebx
0x1400097ad  mov     rcx, [rsp+0B8h+var_58]
0x1400097b2  xor     rcx, rsp; StackCookie
0x1400097b5  call    __security_check_cookie
0x1400097ba  add     rsp, 78h
0x1400097be  pop     r15
0x1400097c0  pop     r14
0x1400097c2  pop     r13
0x1400097c4  pop     r12
0x1400097c6  pop     rdi
0x1400097c7  pop     rsi
0x1400097c8  pop     rbp
0x1400097c9  pop     rbx
0x1400097ca  retn
```
