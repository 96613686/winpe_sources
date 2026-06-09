# CEventNotificationService::s_IsWmsShellSession(ulong,int *)

- ea: `0x1400282a8`
- end: `0x1400287ba`
- name: `?s_IsWmsShellSession@CEventNotificationService@@SAJKPEAH@Z`
- size: `1298`
- prototype: `__int64 __fastcall(DWORD SessionId, int *)`
- caller_count: `3`
- callee_count: `7`
- tags: `authz_impersonation, service_task`

## callers

- `0x1400192b0`
- `0x140020100`
- `0x14002d554`

## callees

- `0x1400282a8`
- `0x14005bc30`
- `0x14005bc68`
- `0x14005bfec`
- `0x14005c408`
- `0x14007cb9e`
- `0x14007cbd0`

## import_xrefs

- `KERNEL32!CloseHandle` at `0x140028590`
- `KERNEL32!CloseHandle` at `0x140028787`
- `KERNEL32!CloseHandle` at `0x140028590`
- `KERNEL32!CloseHandle` at `0x140028787`
- `KERNEL32!QueryFullProcessImageNameW` at `0x14002857d`
- `KERNEL32!QueryFullProcessImageNameW` at `0x14002857d`
- `KERNEL32!OpenProcess` at `0x14002855a`
- `KERNEL32!OpenProcess` at `0x14002855a`
- `KERNEL32!ExpandEnvironmentStringsW` at `0x1400284ff`
- `KERNEL32!ExpandEnvironmentStringsW` at `0x1400284ff`
- `KERNEL32!lstrcmpiW` at `0x140028423`
- `KERNEL32!lstrcmpiW` at `0x14002853f`
- `KERNEL32!lstrcmpiW` at `0x1400285a5`
- `KERNEL32!lstrcmpiW` at `0x140028423`
- `KERNEL32!lstrcmpiW` at `0x14002853f`
- `KERNEL32!lstrcmpiW` at `0x1400285a5`
- `KERNEL32!GetLastError` at `0x140028359`
- `KERNEL32!GetLastError` at `0x14002846d`
- `KERNEL32!GetLastError` at `0x1400285ce`
- `KERNEL32!GetLastError` at `0x14002864e`
- `KERNEL32!GetLastError` at `0x1400286ba`
- `KERNEL32!GetLastError` at `0x140028359`
- `KERNEL32!GetLastError` at `0x14002846d`
- `KERNEL32!GetLastError` at `0x1400285ce`
- `KERNEL32!GetLastError` at `0x14002864e`
- `KERNEL32!GetLastError` at `0x1400286ba`
- `KERNEL32!IsDebuggerPresent` at `0x1400283b0`
- `KERNEL32!IsDebuggerPresent` at `0x1400284c4`
- `KERNEL32!IsDebuggerPresent` at `0x140028625`
- `KERNEL32!IsDebuggerPresent` at `0x1400286a9`
- `KERNEL32!IsDebuggerPresent` at `0x140028715`
- `KERNEL32!IsDebuggerPresent` at `0x1400283b0`
- `KERNEL32!IsDebuggerPresent` at `0x1400284c4`
- `KERNEL32!IsDebuggerPresent` at `0x140028625`
- `KERNEL32!IsDebuggerPresent` at `0x1400286a9`
- `KERNEL32!IsDebuggerPresent` at `0x140028715`
- `WTSAPI32!WTSFreeMemory` at `0x140028764`
- `WTSAPI32!WTSFreeMemory` at `0x140028774`
- `WTSAPI32!WTSFreeMemory` at `0x140028764`
- `WTSAPI32!WTSFreeMemory` at `0x140028774`
- `WTSAPI32!WTSEnumerateProcessesW` at `0x14002845f`
- `WTSAPI32!WTSEnumerateProcessesW` at `0x14002845f`
- `WTSAPI32!WTSQuerySessionInformationW` at `0x14002834b`
- `WTSAPI32!WTSQuerySessionInformationW` at `0x14002834b`

## string_xrefs

- `0x14002837c`: `CEventNotificationService::s_IsWmsShellSession`
- `0x140028490`: `CEventNotificationService::s_IsWmsShellSession`
- `0x1400285f1`: `CEventNotificationService::s_IsWmsShellSession`
- `0x140028671`: `CEventNotificationService::s_IsWmsShellSession`
- `0x1400286dd`: `CEventNotificationService::s_IsWmsShellSession`
- `0x14002842d`: `CEventNotificationService::s_IsWmsShellSession - Detected WMS server WmsShell user in session %lu\n`
- `0x1400286f7`: `cchWmsShellExeFullPath != 0 && cchWmsShellExeFullPath <= (sizeof(*RtlpNumberOf(szWmsShellExeFullPath)))`
- `0x14002871d`: `cchWmsShellExeFullPath != 0 && cchWmsShellExeFullPath <= (sizeof(*RtlpNumberOf(szWmsShellExeFullPath)))`
- `0x1400285c2`: `CEventNotificationService::s_IsWmsShellSession - Detected WMS server WmsShell process in session %lu\n`

## pseudocode

```c
__int64 __fastcall CEventNotificationService::s_IsWmsShellSession(DWORD SessionId, int *a2)
{
  char *v4; // r13
  signed int LastError; // eax
  signed int v6; // ebx
  __int64 v7; // r9
  signed int v8; // eax
  DWORD v9; // ecx
  __int64 v10; // rdi
  char *v11; // rax
  signed int v12; // eax
  signed int v13; // eax
  unsigned int v14; // r15d
  bool v15; // zf
  const unsigned __int16 *v16; // rax
  signed int v17; // eax
  DWORD pCount; // [rsp+40h] [rbp-C0h] BYREF
  DWORD pBytesReturned; // [rsp+44h] [rbp-BCh] BYREF
  LPWSTR ppBuffer; // [rsp+48h] [rbp-B8h] BYREF
  PWTS_PROCESS_INFOW ppProcessInfo; // [rsp+50h] [rbp-B0h] BYREF
  DWORD dwSize; // [rsp+58h] [rbp-A8h] BYREF
  WCHAR Dst[264]; // [rsp+60h] [rbp-A0h] BYREF
  WCHAR ExeName[264]; // [rsp+270h] [rbp+170h] BYREF

  ppBuffer = 0;
  pBytesReturned = 0;
  ppProcessInfo = 0;
  pCount = 0;
  v4 = 0;
  memset_0(ExeName, 0, 0x208u);
  dwSize = 260;
  memset_0(Dst, 0, 0x208u);
  if ( !WTSQuerySessionInformationW(0, SessionId, WTSUserName, &ppBuffer, &pBytesReturned) )
  {
    LastError = GetLastError();
    v6 = LastError;
    if ( LastError > 0 )
      v6 = (unsigned __int16)LastError | 0x80070000;
    if ( v6 >= 0 )
      v6 = -2147467259;
    LOGASSERTHR(
      L"termsrv\\wms\\src\\devices\\wmssvc\\eventnotification.cpp",
      0xC8Du,
      L"CEventNotificationService::s_IsWmsShellSession",
      L"CBRAEx",
      L"fSuccess",
      v6);
    if ( !IsDebuggerPresent() )
    {
      DEBUGMSGBOX(
        L"Assertion failed:  %s(%d) - %s - %s (%s)  hr = 0x%08X\n\n",
        L"termsrv\\wms\\src\\devices\\wmssvc\\eventnotification.cpp",
        3213,
        L"CEventNotificationService::s_IsWmsShellSession",
        L"CBRAEx",
        L"fSuccess",
        v6);
      goto LABEL_55;
    }
    v7 = 3213;
LABEL_8:
    DEBUGMSGLEVEL(
      2u,
      L"%s(%d) - %s - Assertion failed:  %s (%s)  hr = 0x%08X\n",
      L"termsrv\\wms\\src\\devices\\wmssvc\\eventnotification.cpp",
      v7,
      L"CEventNotificationService::s_IsWmsShellSession",
      L"CBRAEx",
      L"fSuccess",
      v6);
    goto LABEL_55;
  }
  v6 = 0;
  ppBuffer[((unsigned __int64)pBytesReturned >> 1) - 1] = 0;
  if ( !lstrcmpiW(ppBuffer, L"WmsShell") )
  {
    DEBUGMSG(
      L"CEventNotificationService::s_IsWmsShellSession - Detected WMS server WmsShell user in session %lu\n",
      SessionId);
LABEL_13:
    *a2 = 1;
    goto LABEL_55;
  }
  if ( !WTSEnumerateProcessesW(0, 0, 1u, &ppProcessInfo, &pCount) )
  {
    v8 = GetLastError();
    v6 = v8;
    if ( v8 > 0 )
      v6 = (unsigned __int16)v8 | 0x80070000;
    if ( v6 >= 0 )
      v6 = -2147467259;
    LOGASSERTHR(
      L"termsrv\\wms\\src\\devices\\wmssvc\\eventnotification.cpp",
      0xC9Fu,
      L"CEventNotificationService::s_IsWmsShellSession",
      L"CBRAEx",
      L"fSuccess",
      v6);
    if ( !IsDebuggerPresent() )
    {
      DEBUGMSGBOX(
        L"Assertion failed:  %s(%d) - %s - %s (%s)  hr = 0x%08X\n\n",
        L"termsrv\\wms\\src\\devices\\wmssvc\\eventnotification.cpp",
        3231,
        L"CEventNotificationService::s_IsWmsShellSession",
        L"CBRAEx",
        L"fSuccess",
        v6);
      goto LABEL_55;
    }
    v7 = 3231;
    goto LABEL_8;
  }
  *a2 = 0;
  if ( ExpandEnvironmentStringsW(L"%ProgramFiles%\\Windows MultiPoint Server\\WmsShell.exe", Dst, 0x104u) - 1 <= 0x103 )
  {
    v9 = pCount;
    v10 = 0;
    if ( !pCount )
      goto LABEL_55;
    while ( 1 )
    {
      if ( ppProcessInfo[v10].SessionId == SessionId )
      {
        if ( !lstrcmpiW(ppProcessInfo[v10].pProcessName, L"WmsShell.exe") )
        {
          v11 = (char *)OpenProcess(0x400u, 0, ppProcessInfo[v10].ProcessId);
          v4 = v11;
          if ( !v11 )
          {
            v13 = GetLastError();
            v6 = v13;
            if ( v13 > 0 )
              v6 = (unsigned __int16)v13 | 0x80070000;
            v14 = 3245;
            if ( v6 >= 0 )
              v6 = -2147467259;
            LOGASSERTHR(
              L"termsrv\\wms\\src\\devices\\wmssvc\\eventnotification.cpp",
              0xCADu,
              L"CEventNotificationService::s_IsWmsShellSession",
              L"CBRAEx",
              L"hWmsShell",
              v6);
            v15 = !IsDebuggerPresent();
            v16 = L"hWmsShell";
            goto LABEL_52;
          }
          if ( !QueryFullProcessImageNameW(v11, 0, ExeName, &dwSize) )
          {
            v12 = GetLastError();
            v6 = v12;
            if ( v12 > 0 )
              v6 = (unsigned __int16)v12 | 0x80070000;
            if ( v6 >= 0 )
              v6 = -2147467259;
            LOGASSERTHR(
              L"termsrv\\wms\\src\\devices\\wmssvc\\eventnotification.cpp",
              0xCB0u,
              L"CEventNotificationService::s_IsWmsShellSession",
              L"CBRAEx",
              L"fSuccess",
              v6);
            if ( IsDebuggerPresent() )
            {
              v7 = 3248;
              goto LABEL_8;
            }
            DEBUGMSGBOX(
              L"Assertion failed:  %s(%d) - %s - %s (%s)  hr = 0x%08X\n\n",
              L"termsrv\\wms\\src\\devices\\wmssvc\\eventnotification.cpp",
              3248,
              L"CEventNotificationService::s_IsWmsShellSession",
              L"CBRAEx",
              L"fSuccess",
              v6);
            goto LABEL_55;
          }
          if ( v4 != (char *)-1LL )
          {
            CloseHandle(v4);
            v4 = 0;
          }
          if ( !lstrcmpiW(ExeName, Dst) )
          {
            DEBUGMSG(
              L"CEventNotificationService::s_IsWmsShellSession - Detected WMS server WmsShell process in session %lu\n",
              SessionId);
            goto LABEL_13;
          }
        }
        v9 = pCount;
      }
      v10 = (unsigned int)(v10 + 1);
      if ( (unsigned int)v10 >= v9 )
        goto LABEL_55;
    }
  }
  v17 = GetLastError();
  v6 = v17;
  if ( v17 > 0 )
    v6 = (unsigned __int16)v17 | 0x80070000;
  v14 = 3237;
  if ( v6 >= 0 )
    v6 = -2147467259;
  LOGASSERTHR(
    L"termsrv\\wms\\src\\devices\\wmssvc\\eventnotification.cpp",
    0xCA5u,
    L"CEventNotificationService::s_IsWmsShellSession",
    L"CBRAEx",
    L"cchWmsShellExeFullPath != 0 && cchWmsShellExeFullPath <= (sizeof(*RtlpNumberOf(szWmsShellExeFullPath)))",
    v6);
  v15 = !IsDebuggerPresent();
  v16 = L"cchWmsShellExeFullPath != 0 && cchWmsShellExeFullPath <= (sizeof(*RtlpNumberOf(szWmsShellExeFullPath)))";
LABEL_52:
  if ( v15 )
    DEBUGMSGBOX(
      L"Assertion failed:  %s(%d) - %s - %s (%s)  hr = 0x%08X\n\n",
      L"termsrv\\wms\\src\\devices\\wmssvc\\eventnotification.cpp",
      v14,
      L"CEventNotificationService::s_IsWmsShellSession",
      L"CBRAEx",
      v16,
      v6);
  else
    DEBUGMSGLEVEL(
      2u,
      L"%s(%d) - %s - Assertion failed:  %s (%s)  hr = 0x%08X\n",
      L"termsrv\\wms\\src\\devices\\wmssvc\\eventnotification.cpp",
      v14,
      L"CEventNotificationService::s_IsWmsShellSession",
      L"CBRAEx",
      v16,
      v6);
LABEL_55:
  if ( ppBuffer )
    WTSFreeMemory(ppBuffer);
  if ( ppProcessInfo )
    WTSFreeMemory(ppProcessInfo);
  if ( (unsigned __int64)(v4 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
    CloseHandle(v4);
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x1400282a8  mov     [rsp-8+arg_10], rbx
0x1400282ad  mov     [rsp-8+arg_18], rsi
0x1400282b2  push    rbp
0x1400282b3  push    rdi
0x1400282b4  push    r13
0x1400282b6  push    r14
0x1400282b8  push    r15
0x1400282ba  lea     rbp, [rsp-390h]
0x1400282c2  sub     rsp, 490h
0x1400282c9  mov     rax, cs:__security_cookie
0x1400282d0  xor     rax, rsp
0x1400282d3  mov     [rbp+3B0h+var_30], rax
0x1400282da  mov     r15, rdx
0x1400282dd  mov     [rsp+4B0h+ppBuffer], 0
0x1400282e6  mov     r14d, ecx
0x1400282e9  mov     [rsp+4B0h+var_46C], 0
0x1400282f1  mov     ebx, 208h
0x1400282f6  mov     [rsp+4B0h+ppProcessInfo], 0
0x1400282ff  mov     r8d, ebx; Size
0x140028302  mov     [rsp+4B0h+pCount], 0
0x14002830a  xor     edx, edx; Val
0x14002830c  lea     rcx, [rbp+3B0h+ExeName]; void *
0x140028313  xor     r13d, r13d
0x140028316  call    memset_0
0x14002831b  mov     edi, 104h
0x140028320  lea     rcx, [rsp+4B0h+Dst]; void *
0x140028325  mov     r8d, ebx; Size
0x140028328  mov     [rsp+4B0h+dwSize], edi
0x14002832c  xor     edx, edx; Val
0x14002832e  call    memset_0
0x140028333  lea     rax, [rsp+4B0h+var_46C]
0x140028338  mov     edx, r14d; SessionId
0x14002833b  lea     r9, [rsp+4B0h+ppBuffer]; ppBuffer
0x140028340  mov     [rsp+4B0h+pBytesReturned], rax; pBytesReturned
0x140028345  lea     r8d, [r13+5]; WTSInfoClass
0x140028349  xor     ecx, ecx; hServer
0x14002834b  call    cs:__imp_WTSQuerySessionInformationW
0x140028351  test    eax, eax
0x140028353  jnz     loc_140028400
0x140028359  call    cs:__imp_GetLastError
0x14002835f  mov     ebx, eax
0x140028361  test    eax, eax
0x140028363  jle     short loc_14002836E
0x140028365  movzx   ebx, ax
0x140028368  or      ebx, 80070000h
0x14002836e  mov     eax, 80004005h
0x140028373  lea     r14, aCbraex; "CBRAEx"
0x14002837a  test    ebx, ebx
0x14002837c  lea     rsi, aCeventnotifica_101; "CEventNotificationService::s_IsWmsShell"...
0x140028383  lea     rdi, aTermsrvWmsSrcD_32; "termsrv\\wms\\src\\devices\\wmssvc\\eve"...
0x14002838a  mov     r9, r14; unsigned __int16 *
0x14002838d  cmovns  ebx, eax
0x140028390  lea     r15, aFsuccess; "fSuccess"
0x140028397  mov     [rsp+4B0h+var_488], ebx; int
0x14002839b  mov     r8, rsi; unsigned __int16 *
0x14002839e  mov     edx, 0C8Dh; unsigned int
0x1400283a3  mov     [rsp+4B0h+pBytesReturned], r15; unsigned __int16 *
0x1400283a8  mov     rcx, rdi; unsigned __int16 *
0x1400283ab  call    ?LOGASSERTHR@@YAXPEBGK000J@Z; LOGASSERTHR(ushort const *,ulong,ushort const *,ushort const *,ushort const *,long)
0x1400283b0  call    cs:__imp_IsDebuggerPresent
0x1400283b6  test    eax, eax
0x1400283b8  jz      short loc_1400283EC
0x1400283ba  mov     r9d, 0C8Dh
0x1400283c0  mov     [rsp+4B0h+var_478], ebx
0x1400283c4  mov     [rsp+4B0h+var_480], r15
0x1400283c9  mov     qword ptr [rsp+4B0h+var_488], r14
0x1400283ce  lea     rdx, aSDSAssertionFa_0; "%s(%d) - %s - Assertion failed:  %s (%s"...
0x1400283d5  mov     r8, rdi
0x1400283d8  mov     [rsp+4B0h+pBytesReturned], rsi
0x1400283dd  mov     ecx, 2; unsigned __int8
0x1400283e2  call    ?DEBUGMSGLEVEL@@YAXEPEBGZZ; DEBUGMSGLEVEL(uchar,ushort const *,...)
0x1400283e7  jmp     loc_14002875A
0x1400283ec  mov     dword ptr [rsp+4B0h+var_480], ebx
0x1400283f0  mov     r8d, 0C8Dh
0x1400283f6  mov     qword ptr [rsp+4B0h+var_488], r15
0x1400283fb  jmp     loc_140028743
0x140028400  mov     r8d, [rsp+4B0h+var_46C]
0x140028405  lea     rdx, String2; "WmsShell"
0x14002840c  mov     rax, [rsp+4B0h+ppBuffer]
0x140028411  xor     ecx, ecx
0x140028413  shr     r8, 1
0x140028416  xor     ebx, ebx
0x140028418  mov     [rax+r8*2-2], cx
0x14002841e  mov     rcx, [rsp+4B0h+ppBuffer]; lpString1
0x140028423  call    cs:__imp_lstrcmpiW
0x140028429  test    eax, eax
0x14002842b  jnz     short loc_140028448
0x14002842d  lea     rcx, aCeventnotifica_70; "CEventNotificationService::s_IsWmsShell"...
0x140028434  mov     edx, r14d
0x140028437  call    ?DEBUGMSG@@YAXPEBGZZ; DEBUGMSG(ushort const *,...)
0x14002843c  mov     dword ptr [r15], 1
0x140028443  jmp     loc_14002875A
0x140028448  xor     edx, edx; Reserved
0x14002844a  lea     rax, [rsp+4B0h+pCount]
0x14002844f  lea     r9, [rsp+4B0h+ppProcessInfo]; ppProcessInfo
0x140028454  mov     [rsp+4B0h+pBytesReturned], rax; pCount
0x140028459  xor     ecx, ecx; hServer
0x14002845b  lea     r8d, [rdx+1]; Version
0x14002845f  call    cs:__imp_WTSEnumerateProcessesW
0x140028465  test    eax, eax
0x140028467  jnz     loc_1400284ED
0x14002846d  call    cs:__imp_GetLastError
0x140028473  mov     ebx, eax
0x140028475  test    eax, eax
0x140028477  jle     short loc_140028482
0x140028479  movzx   ebx, ax
0x14002847c  or      ebx, 80070000h
0x140028482  mov     eax, 80004005h
0x140028487  lea     r14, aCbraex; "CBRAEx"
0x14002848e  test    ebx, ebx
0x140028490  lea     rsi, aCeventnotifica_101; "CEventNotificationService::s_IsWmsShell"...
0x140028497  lea     rdi, aTermsrvWmsSrcD_32; "termsrv\\wms\\src\\devices\\wmssvc\\eve"...
0x14002849e  mov     r9, r14; unsigned __int16 *
0x1400284a1  cmovns  ebx, eax
0x1400284a4  lea     r15, aFsuccess; "fSuccess"
0x1400284ab  mov     [rsp+4B0h+var_488], ebx; int
0x1400284af  mov     r8, rsi; unsigned __int16 *
0x1400284b2  mov     edx, 0C9Fh; unsigned int
0x1400284b7  mov     [rsp+4B0h+pBytesReturned], r15; unsigned __int16 *
0x1400284bc  mov     rcx, rdi; unsigned __int16 *
0x1400284bf  call    ?LOGASSERTHR@@YAXPEBGK000J@Z; LOGASSERTHR(ushort const *,ulong,ushort const *,ushort const *,ushort const *,long)
0x1400284c4  call    cs:__imp_IsDebuggerPresent
0x1400284ca  test    eax, eax
0x1400284cc  jz      short loc_1400284D9
0x1400284ce  mov     r9d, 0C9Fh
0x1400284d4  jmp     loc_1400283C0
0x1400284d9  mov     dword ptr [rsp+4B0h+var_480], ebx
0x1400284dd  mov     r8d, 0C9Fh
0x1400284e3  mov     qword ptr [rsp+4B0h+var_488], r15
0x1400284e8  jmp     loc_140028743
0x1400284ed  mov     r8d, edi; nSize
0x1400284f0  mov     [r15], ebx
0x1400284f3  lea     rdx, [rsp+4B0h+Dst]; lpDst
0x1400284f8  lea     rcx, Src; "%ProgramFiles%\\Windows MultiPoint Serv"...
0x1400284ff  call    cs:__imp_ExpandEnvironmentStringsW
0x140028505  dec     eax
0x140028507  cmp     eax, 103h
0x14002850c  ja      loc_1400286BA
0x140028512  mov     ecx, [rsp+4B0h+pCount]
0x140028516  xor     edi, edi
0x140028518  test    ecx, ecx
0x14002851a  jz      loc_14002875A
0x140028520  mov     rax, [rsp+4B0h+ppProcessInfo]
0x140028525  lea     rsi, [rdi+rdi*2]
0x140028529  cmp     [rax+rsi*8], r14d
0x14002852d  jnz     loc_1400285B3
0x140028533  mov     rcx, [rax+rsi*8+8]; lpString1
0x140028538  lea     rdx, aWmsshellExe; "WmsShell.exe"
0x14002853f  call    cs:__imp_lstrcmpiW
0x140028545  test    eax, eax
0x140028547  jnz     short loc_1400285AF
0x140028549  mov     r8, [rsp+4B0h+ppProcessInfo]
0x14002854e  xor     edx, edx; bInheritHandle
0x140028550  mov     ecx, 400h; dwDesiredAccess
0x140028555  mov     r8d, [r8+rsi*8+4]; dwProcessId
0x14002855a  call    cs:__imp_OpenProcess
0x140028560  mov     r13, rax
0x140028563  test    rax, rax
0x140028566  jz      loc_14002864E
0x14002856c  lea     r9, [rsp+4B0h+dwSize]; lpdwSize
0x140028571  xor     edx, edx; dwFlags
0x140028573  lea     r8, [rbp+3B0h+ExeName]; lpExeName
0x14002857a  mov     rcx, rax; hProcess
0x14002857d  call    cs:__imp_QueryFullProcessImageNameW
0x140028583  test    eax, eax
0x140028585  jz      short loc_1400285CE
0x140028587  cmp     r13, 0FFFFFFFFFFFFFFFFh
0x14002858b  jz      short loc_140028599
0x14002858d  mov     rcx, r13; hObject
0x140028590  call    cs:__imp_CloseHandle
0x140028596  xor     r13d, r13d
0x140028599  lea     rdx, [rsp+4B0h+Dst]; lpString2
0x14002859e  lea     rcx, [rbp+3B0h+ExeName]; lpString1
0x1400285a5  call    cs:__imp_lstrcmpiW
0x1400285ab  test    eax, eax
0x1400285ad  jz      short loc_1400285C2
0x1400285af  mov     ecx, [rsp+4B0h+pCount]
0x1400285b3  inc     edi
0x1400285b5  cmp     edi, ecx
0x1400285b7  jb      loc_140028520
0x1400285bd  jmp     loc_14002875A
0x1400285c2  lea     rcx, aCeventnotifica_28; "CEventNotificationService::s_IsWmsShell"...
0x1400285c9  jmp     loc_140028434
0x1400285ce  call    cs:__imp_GetLastError
0x1400285d4  mov     ebx, eax
0x1400285d6  test    eax, eax
0x1400285d8  jle     short loc_1400285E3
0x1400285da  movzx   ebx, ax
0x1400285dd  or      ebx, 80070000h
0x1400285e3  mov     eax, 80004005h
0x1400285e8  lea     r14, aCbraex; "CBRAEx"
0x1400285ef  test    ebx, ebx
0x1400285f1  lea     rsi, aCeventnotifica_101; "CEventNotificationService::s_IsWmsShell"...
0x1400285f8  lea     rdi, aTermsrvWmsSrcD_32; "termsrv\\wms\\src\\devices\\wmssvc\\eve"...
0x1400285ff  mov     r9, r14; unsigned __int16 *
0x140028602  cmovns  ebx, eax
0x140028605  lea     r15, aFsuccess; "fSuccess"
0x14002860c  mov     [rsp+4B0h+var_488], ebx; int
0x140028610  mov     r8, rsi; unsigned __int16 *
0x140028613  mov     edx, 0CB0h; unsigned int
0x140028618  mov     [rsp+4B0h+pBytesReturned], r15; unsigned __int16 *
0x14002861d  mov     rcx, rdi; unsigned __int16 *
0x140028620  call    ?LOGASSERTHR@@YAXPEBGK000J@Z; LOGASSERTHR(ushort const *,ulong,ushort const *,ushort const *,ushort const *,long)
0x140028625  call    cs:__imp_IsDebuggerPresent
0x14002862b  test    eax, eax
0x14002862d  jz      short loc_14002863A
0x14002862f  mov     r9d, 0CB0h
0x140028635  jmp     loc_1400283C0
0x14002863a  mov     dword ptr [rsp+4B0h+var_480], ebx
0x14002863e  mov     r8d, 0CB0h
0x140028644  mov     qword ptr [rsp+4B0h+var_488], r15
0x140028649  jmp     loc_140028743
0x14002864e  call    cs:__imp_GetLastError
0x140028654  mov     ebx, eax
0x140028656  test    eax, eax
0x140028658  jle     short loc_140028663
0x14002865a  movzx   ebx, ax
0x14002865d  or      ebx, 80070000h
0x140028663  mov     eax, 80004005h
0x140028668  lea     r14, aCbraex; "CBRAEx"
0x14002866f  test    ebx, ebx
0x140028671  lea     rsi, aCeventnotifica_101; "CEventNotificationService::s_IsWmsShell"...
0x140028678  mov     r15d, 0CADh
0x14002867e  lea     rdi, aTermsrvWmsSrcD_32; "termsrv\\wms\\src\\devices\\wmssvc\\eve"...
0x140028685  cmovns  ebx, eax
0x140028688  mov     r9, r14; unsigned __int16 *
0x14002868b  lea     rax, aHwmsshell; "hWmsShell"
0x140028692  mov     [rsp+4B0h+var_488], ebx; int
0x140028696  mov     r8, rsi; unsigned __int16 *
0x140028699  mov     [rsp+4B0h+pBytesReturned], rax; unsigned __int16 *
0x14002869e  mov     edx, r15d; unsigned int
0x1400286a1  mov     rcx, rdi; unsigned __int16 *
0x1400286a4  call    ?LOGASSERTHR@@YAXPEBGK000J@Z; LOGASSERTHR(ushort const *,ulong,ushort const *,ushort const *,ushort const *,long)
0x1400286a9  call    cs:__imp_IsDebuggerPresent
0x1400286af  test    eax, eax
0x1400286b1  lea     rax, aHwmsshell; "hWmsShell"
0x1400286b8  jmp     short loc_140028724
0x1400286ba  call    cs:__imp_GetLastError
0x1400286c0  mov     ebx, eax
0x1400286c2  test    eax, eax
0x1400286c4  jle     short loc_1400286CF
0x1400286c6  movzx   ebx, ax
0x1400286c9  or      ebx, 80070000h
0x1400286cf  mov     eax, 80004005h
0x1400286d4  lea     r14, aCbraex; "CBRAEx"
0x1400286db  test    ebx, ebx
0x1400286dd  lea     rsi, aCeventnotifica_101; "CEventNotificationService::s_IsWmsShell"...
0x1400286e4  mov     r15d, 0CA5h
0x1400286ea  lea     rdi, aTermsrvWmsSrcD_32; "termsrv\\wms\\src\\devices\\wmssvc\\eve"...
0x1400286f1  cmovns  ebx, eax
0x1400286f4  mov     r9, r14; unsigned __int16 *
0x1400286f7  lea     rax, aCchwmsshellexe; "cchWmsShellExeFullPath != 0 && cchWmsSh"...
0x1400286fe  mov     [rsp+4B0h+var_488], ebx; int
0x140028702  mov     r8, rsi; unsigned __int16 *
0x140028705  mov     [rsp+4B0h+pBytesReturned], rax; unsigned __int16 *
0x14002870a  mov     edx, r15d; unsigned int
0x14002870d  mov     rcx, rdi; unsigned __int16 *
0x140028710  call    ?LOGASSERTHR@@YAXPEBGK000J@Z; LOGASSERTHR(ushort const *,ulong,ushort const *,ushort const *,ushort const *,long)
0x140028715  call    cs:__imp_IsDebuggerPresent
0x14002871b  test    eax, eax
0x14002871d  lea     rax, aCchwmsshellexe; "cchWmsShellExeFullPath != 0 && cchWmsSh"...
0x140028724  jz      short loc_140028737
0x140028726  mov     [rsp+4B0h+var_478], ebx
0x14002872a  mov     r9d, r15d
0x14002872d  mov     [rsp+4B0h+var_480], rax
0x140028732  jmp     loc_1400283C9
0x140028737  mov     dword ptr [rsp+4B0h+var_480], ebx
0x14002873b  mov     r8d, r15d
0x14002873e  mov     qword ptr [rsp+4B0h+var_488], rax
0x140028743  mov     r9, rsi
0x140028746  mov     [rsp+4B0h+pBytesReturned], r14
0x14002874b  mov     rdx, rdi
0x14002874e  lea     rcx, aAssertionFaile; "Assertion failed:  %s(%d) - %s - %s (%s"...
0x140028755  call    ?DEBUGMSGBOX@@YAHPEBGZZ; DEBUGMSGBOX(ushort const *,...)
0x14002875a  mov     rcx, [rsp+4B0h+ppBuffer]; pMemory
0x14002875f  test    rcx, rcx
0x140028762  jz      short loc_14002876A
0x140028764  call    cs:__imp_WTSFreeMemory
0x14002876a  mov     rcx, [rsp+4B0h+ppProcessInfo]; pMemory
0x14002876f  test    rcx, rcx
0x140028772  jz      short loc_14002877A
0x140028774  call    cs:__imp_WTSFreeMemory
0x14002877a  lea     rcx, [r13-1]
0x14002877e  cmp     rcx, 0FFFFFFFFFFFFFFFDh
0x140028782  ja      short loc_14002878D
0x140028784  mov     rcx, r13; hObject
0x140028787  call    cs:__imp_CloseHandle
0x14002878d  mov     eax, ebx
0x14002878f  mov     rcx, [rbp+3B0h+var_30]
0x140028796  xor     rcx, rsp; StackCookie
0x140028799  call    __security_check_cookie
0x14002879e  lea     r11, [rsp+4B0h+var_20]
0x1400287a6  mov     rbx, [r11+40h]
0x1400287aa  mov     rsi, [r11+48h]
0x1400287ae  mov     rsp, r11
0x1400287b1  pop     r15
0x1400287b3  pop     r14
0x1400287b5  pop     r13
0x1400287b7  pop     rdi
0x1400287b8  pop     rbp
  ... truncated ...
```
