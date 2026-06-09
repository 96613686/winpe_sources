# DiscoveryService::CheckAndStartDependencies(void)

- ea: `0x1400783b8`
- end: `0x1400789d9`
- name: `?CheckAndStartDependencies@DiscoveryService@@CAJXZ`
- size: `1569`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `7`
- tags: `service_task`

## callers

- `0x1400080f0`

## callees

- `0x14005bc30`
- `0x14005bc68`
- `0x14005bfec`
- `0x14005c408`
- `0x1400783b8`
- `0x14007c644`
- `0x14007cbd0`

## import_xrefs

- `ADVAPI32!OpenSCManagerW` at `0x140078409`
- `ADVAPI32!OpenSCManagerW` at `0x140078409`
- `ADVAPI32!OpenServiceW` at `0x1400784e7`
- `ADVAPI32!OpenServiceW` at `0x14007851e`
- `ADVAPI32!OpenServiceW` at `0x1400784e7`
- `ADVAPI32!OpenServiceW` at `0x14007851e`
- `ADVAPI32!QueryServiceStatus` at `0x1400785f3`
- `ADVAPI32!QueryServiceStatus` at `0x1400785f3`
- `ADVAPI32!CloseServiceHandle` at `0x1400789a8`
- `ADVAPI32!CloseServiceHandle` at `0x1400789b1`
- `ADVAPI32!CloseServiceHandle` at `0x1400789a8`
- `ADVAPI32!CloseServiceHandle` at `0x1400789b1`
- `ADVAPI32!StartServiceW` at `0x14007886a`
- `ADVAPI32!StartServiceW` at `0x1400788f7`
- `ADVAPI32!StartServiceW` at `0x14007886a`
- `ADVAPI32!StartServiceW` at `0x1400788f7`
- `ADVAPI32!ControlServiceExW` at `0x140078711`
- `ADVAPI32!ControlServiceExW` at `0x1400787be`
- `ADVAPI32!ControlServiceExW` at `0x140078711`
- `ADVAPI32!ControlServiceExW` at `0x1400787be`
- `KERNEL32!GetLastError` at `0x14007841b`
- `KERNEL32!GetLastError` at `0x1400784f9`
- `KERNEL32!GetLastError` at `0x140078530`
- `KERNEL32!GetLastError` at `0x140078601`
- `KERNEL32!GetLastError` at `0x14007871f`
- `KERNEL32!GetLastError` at `0x1400787cc`
- `KERNEL32!GetLastError` at `0x140078878`
- `KERNEL32!GetLastError` at `0x140078905`
- `KERNEL32!GetLastError` at `0x14007841b`
- `KERNEL32!GetLastError` at `0x1400784f9`
- `KERNEL32!GetLastError` at `0x140078530`
- `KERNEL32!GetLastError` at `0x140078601`
- `KERNEL32!GetLastError` at `0x14007871f`
- `KERNEL32!GetLastError` at `0x1400787cc`
- `KERNEL32!GetLastError` at `0x140078878`
- `KERNEL32!GetLastError` at `0x140078905`
- `KERNEL32!IsDebuggerPresent` at `0x140078476`
- `KERNEL32!IsDebuggerPresent` at `0x14007858b`
- `KERNEL32!IsDebuggerPresent` at `0x140078658`
- `KERNEL32!IsDebuggerPresent` at `0x140078776`
- `KERNEL32!IsDebuggerPresent` at `0x140078823`
- `KERNEL32!IsDebuggerPresent` at `0x1400788cf`
- `KERNEL32!IsDebuggerPresent` at `0x14007895d`
- `KERNEL32!IsDebuggerPresent` at `0x140078476`
- `KERNEL32!IsDebuggerPresent` at `0x14007858b`
- `KERNEL32!IsDebuggerPresent` at `0x140078658`
- `KERNEL32!IsDebuggerPresent` at `0x140078776`
- `KERNEL32!IsDebuggerPresent` at `0x140078823`
- `KERNEL32!IsDebuggerPresent` at `0x1400788cf`
- `KERNEL32!IsDebuggerPresent` at `0x14007895d`

## string_xrefs

- `0x14007856a`: `hService != 0`
- `0x14007844b`: `termsrv\wms\src\middletier\discovery\service\discoveryservice.cpp`
- `0x140078560`: `termsrv\wms\src\middletier\discovery\service\discoveryservice.cpp`
- `0x14007862b`: `termsrv\wms\src\middletier\discovery\service\discoveryservice.cpp`
- `0x140078749`: `termsrv\wms\src\middletier\discovery\service\discoveryservice.cpp`
- `0x1400787f6`: `termsrv\wms\src\middletier\discovery\service\discoveryservice.cpp`
- `0x1400788a2`: `termsrv\wms\src\middletier\discovery\service\discoveryservice.cpp`
- `0x140078945`: `termsrv\wms\src\middletier\discovery\service\discoveryservice.cpp`
- `0x14007843e`: `DiscoveryService::CheckAndStartDependencies`
- `0x140078553`: `DiscoveryService::CheckAndStartDependencies`
- `0x140078624`: `DiscoveryService::CheckAndStartDependencies`
- `0x140078742`: `DiscoveryService::CheckAndStartDependencies`
- `0x1400787ef`: `DiscoveryService::CheckAndStartDependencies`
- `0x14007889b`: `DiscoveryService::CheckAndStartDependencies`
- `0x140078938`: `DiscoveryService::CheckAndStartDependencies`
- `0x140078504`: `DiscoveryService::CheckAndStartDependencies - OpenService failed with ERROR_ACCESS_DENIED for SERVICE_PAUSE_CONTINUE, trying without SERVICE_PAUSE_CONTINUE.\n`

## pseudocode

```c
__int64 DiscoveryService::CheckAndStartDependencies(void)
{
  SC_HANDLE v0; // rax
  SC_HANDLE v1; // r13
  signed int v2; // eax
  signed int v3; // ebx
  SC_HANDLE v4; // r15
  signed int LastError; // eax
  const unsigned __int16 *v6; // rcx
  signed int v7; // eax
  __int64 v8; // r9
  __int64 v9; // r8
  signed int v10; // eax
  signed int v11; // eax
  signed int v12; // eax
  signed int v13; // eax
  __int128 pControlParams; // [rsp+40h] [rbp-49h] BYREF
  __int128 v16; // [rsp+50h] [rbp-39h]
  __int128 v17; // [rsp+60h] [rbp-29h]
  __int64 v18; // [rsp+70h] [rbp-19h]
  struct _SERVICE_STATUS ServiceStatus; // [rsp+78h] [rbp-11h] BYREF

  memset(&ServiceStatus, 0, sizeof(ServiceStatus));
  v18 = 0;
  pControlParams = 0;
  v16 = 0;
  v17 = 0;
  v0 = OpenSCManagerW(0, 0, 0xF003Fu);
  v1 = v0;
  if ( v0 )
  {
    v4 = OpenServiceW(v0, L"WinHttpAutoProxySvc", 0x54u);
    if ( !v4 )
    {
      if ( GetLastError() != 5
        || (DEBUGMSG(
              L"DiscoveryService::CheckAndStartDependencies - OpenService failed with ERROR_ACCESS_DENIED for SERVICE_PAUS"
               "E_CONTINUE, trying without SERVICE_PAUSE_CONTINUE.\n"),
            (v4 = OpenServiceW(v1, L"WinHttpAutoProxySvc", 0x14u)) == 0) )
      {
        LastError = GetLastError();
        v3 = LastError;
        if ( LastError > 0 )
          v3 = (unsigned __int16)LastError | 0x80070000;
        if ( v3 >= 0 )
          v3 = -2147467259;
        LOGASSERTHR(
          L"termsrv\\wms\\src\\middletier\\discovery\\service\\discoveryservice.cpp",
          0x199u,
          L"DiscoveryService::CheckAndStartDependencies",
          L"CBRAEx",
          L"hService != 0",
          v3);
        if ( IsDebuggerPresent() )
          DEBUGMSGLEVEL(
            2u,
            L"%s(%d) - %s - Assertion failed:  %s (%s)  hr = 0x%08X\n",
            L"termsrv\\wms\\src\\middletier\\discovery\\service\\discoveryservice.cpp",
            409,
            L"DiscoveryService::CheckAndStartDependencies",
            L"CBRAEx",
            L"hService != 0",
            v3,
            pControlParams,
            v16,
            v17,
            v18,
            *(_QWORD *)&ServiceStatus.dwServiceType,
            *(_QWORD *)&ServiceStatus.dwControlsAccepted);
        else
          DEBUGMSGBOX(
            L"Assertion failed:  %s(%d) - %s - %s (%s)  hr = 0x%08X\n\n",
            L"termsrv\\wms\\src\\middletier\\discovery\\service\\discoveryservice.cpp",
            409,
            L"DiscoveryService::CheckAndStartDependencies",
            L"CBRAEx",
            L"hService != 0",
            v3);
        goto LABEL_70;
      }
    }
    if ( !QueryServiceStatus(v4, &ServiceStatus) )
    {
      v7 = GetLastError();
      v3 = v7;
      if ( v7 > 0 )
        v3 = (unsigned __int16)v7 | 0x80070000;
      if ( v3 >= 0 )
        v3 = -2147467259;
      LOGASSERTHR(
        L"termsrv\\wms\\src\\middletier\\discovery\\service\\discoveryservice.cpp",
        0x19Cu,
        L"DiscoveryService::CheckAndStartDependencies",
        L"CBRAEx",
        L"fResult",
        v3);
      if ( IsDebuggerPresent() )
      {
        v8 = 412;
LABEL_26:
        DEBUGMSGLEVEL(
          2u,
          L"%s(%d) - %s - Assertion failed:  %s (%s)  hr = 0x%08X\n",
          L"termsrv\\wms\\src\\middletier\\discovery\\service\\discoveryservice.cpp",
          v8,
          L"DiscoveryService::CheckAndStartDependencies",
          L"CBRAEx",
          L"fResult",
          v3,
          pControlParams,
          v16,
          v17,
          v18,
          *(_QWORD *)&ServiceStatus.dwServiceType,
          *(_QWORD *)&ServiceStatus.dwControlsAccepted);
LABEL_69:
        CloseServiceHandle(v4);
LABEL_70:
        CloseServiceHandle(v1);
        return (unsigned int)v3;
      }
      v9 = 412;
      goto LABEL_28;
    }
    v18 = 0;
    pControlParams = 0;
    v16 = 0;
    v17 = 0;
    switch ( ServiceStatus.dwCurrentState )
    {
      case 1u:
        if ( !StartServiceW(v4, 0, 0) )
        {
          v13 = GetLastError();
          v3 = v13;
          if ( v13 != 1056 )
          {
            if ( v13 > 0 )
              v3 = (unsigned __int16)v13 | 0x80070000;
            LOGASSERTHR(
              L"termsrv\\wms\\src\\middletier\\discovery\\service\\discoveryservice.cpp",
              0x1C4u,
              L"DiscoveryService::CheckAndStartDependencies",
              L"CBRAEx",
              L"dwRet == 1056L",
              v3);
            if ( IsDebuggerPresent() )
              DEBUGMSGLEVEL(
                2u,
                L"%s(%d) - %s - Assertion failed:  %s (%s)  hr = 0x%08X\n",
                L"termsrv\\wms\\src\\middletier\\discovery\\service\\discoveryservice.cpp",
                452,
                L"DiscoveryService::CheckAndStartDependencies",
                L"CBRAEx",
                L"dwRet == 1056L",
                v3,
                pControlParams,
                v16,
                v17,
                v18,
                *(_QWORD *)&ServiceStatus.dwServiceType,
                *(_QWORD *)&ServiceStatus.dwControlsAccepted);
            else
              DEBUGMSGBOX(
                L"Assertion failed:  %s(%d) - %s - %s (%s)  hr = 0x%08X\n\n",
                L"termsrv\\wms\\src\\middletier\\discovery\\service\\discoveryservice.cpp",
                452,
                L"DiscoveryService::CheckAndStartDependencies",
                L"CBRAEx",
                L"dwRet == 1056L",
                v3);
            goto LABEL_69;
          }
        }
        break;
      case 3u:
        v3 = WaitForServiceStatus(v6, v4, 1u);
        if ( v3 < 0 )
          goto LABEL_69;
        if ( !StartServiceW(v4, 0, 0) )
        {
          v12 = GetLastError();
          v3 = v12;
          if ( v12 > 0 )
            v3 = (unsigned __int16)v12 | 0x80070000;
          if ( v3 >= 0 )
            v3 = -2147467259;
          LOGASSERTHR(
            L"termsrv\\wms\\src\\middletier\\discovery\\service\\discoveryservice.cpp",
            0x1DBu,
            L"DiscoveryService::CheckAndStartDependencies",
            L"CBRAEx",
            L"fResult",
            v3);
          if ( IsDebuggerPresent() )
          {
            v8 = 475;
            goto LABEL_26;
          }
          v9 = 475;
          goto LABEL_28;
        }
        break;
      case 4u:
        v3 = 0;
        goto LABEL_69;
      case 6u:
        v3 = WaitForServiceStatus(v6, v4, 7u);
        if ( v3 < 0 )
          goto LABEL_69;
        if ( !ControlServiceExW(v4, 3u, 1u, &pControlParams) )
        {
          v11 = GetLastError();
          v3 = v11;
          if ( v11 > 0 )
            v3 = (unsigned __int16)v11 | 0x80070000;
          if ( v3 >= 0 )
            v3 = -2147467259;
          LOGASSERTHR(
            L"termsrv\\wms\\src\\middletier\\discovery\\service\\discoveryservice.cpp",
            0x1D2u,
            L"DiscoveryService::CheckAndStartDependencies",
            L"CBRAEx",
            L"fResult",
            v3);
          if ( IsDebuggerPresent() )
          {
            v8 = 466;
            goto LABEL_26;
          }
          v9 = 466;
          goto LABEL_28;
        }
        break;
      default:
        if ( ServiceStatus.dwCurrentState == 7 && !ControlServiceExW(v4, 3u, 1u, &pControlParams) )
        {
          v10 = GetLastError();
          v3 = v10;
          if ( v10 > 0 )
            v3 = (unsigned __int16)v10 | 0x80070000;
          if ( v3 >= 0 )
            v3 = -2147467259;
          LOGASSERTHR(
            L"termsrv\\wms\\src\\middletier\\discovery\\service\\discoveryservice.cpp",
            0x1BBu,
            L"DiscoveryService::CheckAndStartDependencies",
            L"CBRAEx",
            L"fResult",
            v3);
          if ( IsDebuggerPresent() )
          {
            v8 = 443;
            goto LABEL_26;
          }
          v9 = 443;
LABEL_28:
          DEBUGMSGBOX(
            L"Assertion failed:  %s(%d) - %s - %s (%s)  hr = 0x%08X\n\n",
            L"termsrv\\wms\\src\\middletier\\discovery\\service\\discoveryservice.cpp",
            v9,
            L"DiscoveryService::CheckAndStartDependencies",
            L"CBRAEx",
            L"fResult",
            v3);
          goto LABEL_69;
        }
        break;
    }
    v3 = WaitForServiceStatus(v6, v4, 4u);
    goto LABEL_69;
  }
  v2 = GetLastError();
  v3 = v2;
  if ( v2 > 0 )
    v3 = (unsigned __int16)v2 | 0x80070000;
  if ( v3 >= 0 )
    v3 = -2147467259;
  LOGASSERTHR(
    L"termsrv\\wms\\src\\middletier\\discovery\\service\\discoveryservice.cpp",
    0x18Cu,
    L"DiscoveryService::CheckAndStartDependencies",
    L"CBRAEx",
    L"hSCM != 0",
    v3);
  if ( IsDebuggerPresent() )
    DEBUGMSGLEVEL(
      2u,
      L"%s(%d) - %s - Assertion failed:  %s (%s)  hr = 0x%08X\n",
      L"termsrv\\wms\\src\\middletier\\discovery\\service\\discoveryservice.cpp",
      396,
      L"DiscoveryService::CheckAndStartDependencies",
      L"CBRAEx",
      L"hSCM != 0",
      v3,
      pControlParams,
      v16,
      v17,
      v18,
      *(_QWORD *)&ServiceStatus.dwServiceType,
      *(_QWORD *)&ServiceStatus.dwControlsAccepted);
  else
    DEBUGMSGBOX(
      L"Assertion failed:  %s(%d) - %s - %s (%s)  hr = 0x%08X\n\n",
      L"termsrv\\wms\\src\\middletier\\discovery\\service\\discoveryservice.cpp",
      396,
      L"DiscoveryService::CheckAndStartDependencies",
      L"CBRAEx",
      L"hSCM != 0",
      v3);
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x1400783b8  push    rbp
0x1400783ba  push    rbx
0x1400783bb  push    rsi
0x1400783bc  push    rdi
0x1400783bd  push    r12
0x1400783bf  push    r13
0x1400783c1  push    r14
0x1400783c3  push    r15
0x1400783c5  lea     rbp, [rsp-1Fh]
0x1400783ca  sub     rsp, 0A8h
0x1400783d1  mov     rax, cs:__security_cookie
0x1400783d8  xor     rax, rsp
0x1400783db  mov     [rbp+57h+var_48], rax
0x1400783df  xorps   xmm1, xmm1
0x1400783e2  xorps   xmm0, xmm0
0x1400783e5  xor     eax, eax
0x1400783e7  xor     edx, edx; lpDatabaseName
0x1400783e9  movups  xmmword ptr [rbp+57h+ServiceStatus.dwServiceType], xmm0
0x1400783ed  xor     ecx, ecx; lpMachineName
0x1400783ef  mov     [rbp+57h+var_70], rax
0x1400783f3  mov     r8d, 0F003Fh; dwDesiredAccess
0x1400783f9  movups  xmmword ptr [rbp+57h+ServiceStatus.dwWin32ExitCode], xmm0
0x1400783fd  movups  [rbp+57h+pControlParams], xmm1
0x140078401  movups  [rbp+57h+var_90], xmm1
0x140078405  movups  [rbp+57h+var_80], xmm1
0x140078409  call    cs:__imp_OpenSCManagerW
0x14007840f  mov     r13, rax
0x140078412  test    rax, rax
0x140078415  jnz     loc_1400784D7
0x14007841b  call    cs:__imp_GetLastError
0x140078421  mov     ebx, eax
0x140078423  test    eax, eax
0x140078425  jle     short loc_140078430
0x140078427  movzx   ebx, ax
0x14007842a  or      ebx, 80070000h
0x140078430  mov     eax, 80004005h
0x140078435  lea     r14, aCbraex; "CBRAEx"
0x14007843c  test    ebx, ebx
0x14007843e  lea     rsi, aDiscoveryservi_1; "DiscoveryService::CheckAndStartDependen"...
0x140078445  mov     r15d, 18Ch
0x14007844b  lea     rdi, aTermsrvWmsSrcM_1; "termsrv\\wms\\src\\middletier\\discover"...
0x140078452  cmovns  ebx, eax
0x140078455  lea     r12, aHscm0; "hSCM != 0"
0x14007845c  mov     [rsp+0E0h+var_B8], ebx; int
0x140078460  mov     r9, r14; unsigned __int16 *
0x140078463  mov     r8, rsi; unsigned __int16 *
0x140078466  mov     [rsp+0E0h+var_C0], r12; unsigned __int16 *
0x14007846b  mov     edx, r15d; unsigned int
0x14007846e  mov     rcx, rdi; unsigned __int16 *
0x140078471  call    ?LOGASSERTHR@@YAXPEBGK000J@Z; LOGASSERTHR(ushort const *,ulong,ushort const *,ushort const *,ushort const *,long)
0x140078476  call    cs:__imp_IsDebuggerPresent
0x14007847c  test    eax, eax
0x14007847e  jz      short loc_1400784AF
0x140078480  mov     [rsp+0E0h+var_A8], ebx
0x140078484  lea     rdx, aSDSAssertionFa_0; "%s(%d) - %s - Assertion failed:  %s (%s"...
0x14007848b  mov     [rsp+0E0h+var_B0], r12
0x140078490  mov     r9d, r15d
0x140078493  mov     qword ptr [rsp+0E0h+var_B8], r14
0x140078498  mov     r8, rdi
0x14007849b  mov     ecx, 2; unsigned __int8
0x1400784a0  mov     [rsp+0E0h+var_C0], rsi
0x1400784a5  call    ?DEBUGMSGLEVEL@@YAXEPEBGZZ; DEBUGMSGLEVEL(uchar,ushort const *,...)
0x1400784aa  jmp     loc_1400789B7
0x1400784af  mov     dword ptr [rsp+0E0h+var_B0], ebx
0x1400784b3  lea     rcx, aAssertionFaile; "Assertion failed:  %s(%d) - %s - %s (%s"...
0x1400784ba  mov     qword ptr [rsp+0E0h+var_B8], r12
0x1400784bf  mov     r9, rsi
0x1400784c2  mov     r8d, r15d
0x1400784c5  mov     [rsp+0E0h+var_C0], r14
0x1400784ca  mov     rdx, rdi
0x1400784cd  call    ?DEBUGMSGBOX@@YAHPEBGZZ; DEBUGMSGBOX(ushort const *,...)
0x1400784d2  jmp     loc_1400789B7
0x1400784d7  mov     r8d, 54h ; 'T'; dwDesiredAccess
0x1400784dd  lea     rdx, aWinhttpautopro; "WinHttpAutoProxySvc"
0x1400784e4  mov     rcx, r13; hSCManager
0x1400784e7  call    cs:__imp_OpenServiceW
0x1400784ed  mov     r15, rax
0x1400784f0  test    rax, rax
0x1400784f3  jnz     loc_1400785EC
0x1400784f9  call    cs:__imp_GetLastError
0x1400784ff  cmp     eax, 5
0x140078502  jnz     short loc_140078530
0x140078504  lea     rcx, aDiscoveryservi_0; "DiscoveryService::CheckAndStartDependen"...
0x14007850b  call    ?DEBUGMSG@@YAXPEBGZZ; DEBUGMSG(ushort const *,...)
0x140078510  lea     r8d, [r15+14h]; dwDesiredAccess
0x140078514  mov     rcx, r13; hSCManager
0x140078517  lea     rdx, aWinhttpautopro; "WinHttpAutoProxySvc"
0x14007851e  call    cs:__imp_OpenServiceW
0x140078524  mov     r15, rax
0x140078527  test    rax, rax
0x14007852a  jnz     loc_1400785EC
0x140078530  call    cs:__imp_GetLastError
0x140078536  mov     ebx, eax
0x140078538  test    eax, eax
0x14007853a  jle     short loc_140078545
0x14007853c  movzx   ebx, ax
0x14007853f  or      ebx, 80070000h
0x140078545  mov     eax, 80004005h
0x14007854a  lea     r14, aCbraex; "CBRAEx"
0x140078551  test    ebx, ebx
0x140078553  lea     rsi, aDiscoveryservi_1; "DiscoveryService::CheckAndStartDependen"...
0x14007855a  mov     r15d, 199h
0x140078560  lea     rdi, aTermsrvWmsSrcM_1; "termsrv\\wms\\src\\middletier\\discover"...
0x140078567  cmovns  ebx, eax
0x14007856a  lea     r12, aHservice0; "hService != 0"
0x140078571  mov     [rsp+0E0h+var_B8], ebx; int
0x140078575  mov     r9, r14; unsigned __int16 *
0x140078578  mov     r8, rsi; unsigned __int16 *
0x14007857b  mov     [rsp+0E0h+var_C0], r12; unsigned __int16 *
0x140078580  mov     edx, r15d; unsigned int
0x140078583  mov     rcx, rdi; unsigned __int16 *
0x140078586  call    ?LOGASSERTHR@@YAXPEBGK000J@Z; LOGASSERTHR(ushort const *,ulong,ushort const *,ushort const *,ushort const *,long)
0x14007858b  call    cs:__imp_IsDebuggerPresent
0x140078591  test    eax, eax
0x140078593  jz      short loc_1400785C4
0x140078595  mov     [rsp+0E0h+var_A8], ebx
0x140078599  lea     rdx, aSDSAssertionFa_0; "%s(%d) - %s - Assertion failed:  %s (%s"...
0x1400785a0  mov     [rsp+0E0h+var_B0], r12
0x1400785a5  mov     r9d, r15d
0x1400785a8  mov     qword ptr [rsp+0E0h+var_B8], r14
0x1400785ad  mov     r8, rdi
0x1400785b0  mov     ecx, 2; unsigned __int8
0x1400785b5  mov     [rsp+0E0h+var_C0], rsi
0x1400785ba  call    ?DEBUGMSGLEVEL@@YAXEPEBGZZ; DEBUGMSGLEVEL(uchar,ushort const *,...)
0x1400785bf  jmp     loc_1400789AE
0x1400785c4  mov     dword ptr [rsp+0E0h+var_B0], ebx
0x1400785c8  lea     rcx, aAssertionFaile; "Assertion failed:  %s(%d) - %s - %s (%s"...
0x1400785cf  mov     qword ptr [rsp+0E0h+var_B8], r12
0x1400785d4  mov     r9, rsi
0x1400785d7  mov     r8d, r15d
0x1400785da  mov     [rsp+0E0h+var_C0], r14
0x1400785df  mov     rdx, rdi
0x1400785e2  call    ?DEBUGMSGBOX@@YAHPEBGZZ; DEBUGMSGBOX(ushort const *,...)
0x1400785e7  jmp     loc_1400789AE
0x1400785ec  lea     rdx, [rbp+57h+ServiceStatus]; lpServiceStatus
0x1400785f0  mov     rcx, r15; hService
0x1400785f3  call    cs:__imp_QueryServiceStatus
0x1400785f9  test    eax, eax
0x1400785fb  jnz     loc_1400786BF
0x140078601  call    cs:__imp_GetLastError
0x140078607  mov     ebx, eax
0x140078609  test    eax, eax
0x14007860b  jle     short loc_140078616
0x14007860d  movzx   ebx, ax
0x140078610  or      ebx, 80070000h
0x140078616  mov     eax, 80004005h
0x14007861b  lea     r14, aCbraex; "CBRAEx"
0x140078622  test    ebx, ebx
0x140078624  lea     rsi, aDiscoveryservi_1; "DiscoveryService::CheckAndStartDependen"...
0x14007862b  lea     rdi, aTermsrvWmsSrcM_1; "termsrv\\wms\\src\\middletier\\discover"...
0x140078632  mov     r9, r14; unsigned __int16 *
0x140078635  cmovns  ebx, eax
0x140078638  lea     r12, aFresult; "fResult"
0x14007863f  mov     [rsp+0E0h+var_B8], ebx; int
0x140078643  mov     r8, rsi; unsigned __int16 *
0x140078646  mov     edx, 19Ch; unsigned int
0x14007864b  mov     [rsp+0E0h+var_C0], r12; unsigned __int16 *
0x140078650  mov     rcx, rdi; unsigned __int16 *
0x140078653  call    ?LOGASSERTHR@@YAXPEBGK000J@Z; LOGASSERTHR(ushort const *,ulong,ushort const *,ushort const *,ushort const *,long)
0x140078658  call    cs:__imp_IsDebuggerPresent
0x14007865e  test    eax, eax
0x140078660  jz      short loc_140078694
0x140078662  mov     r9d, 19Ch
0x140078668  mov     [rsp+0E0h+var_A8], ebx
0x14007866c  mov     [rsp+0E0h+var_B0], r12
0x140078671  mov     qword ptr [rsp+0E0h+var_B8], r14
0x140078676  lea     rdx, aSDSAssertionFa_0; "%s(%d) - %s - Assertion failed:  %s (%s"...
0x14007867d  mov     r8, rdi
0x140078680  mov     [rsp+0E0h+var_C0], rsi
0x140078685  mov     ecx, 2; unsigned __int8
0x14007868a  call    ?DEBUGMSGLEVEL@@YAXEPEBGZZ; DEBUGMSGLEVEL(uchar,ushort const *,...)
0x14007868f  jmp     loc_1400789A0
0x140078694  mov     r8d, 19Ch
0x14007869a  mov     dword ptr [rsp+0E0h+var_B0], ebx
0x14007869e  mov     qword ptr [rsp+0E0h+var_B8], r12
0x1400786a3  mov     r9, rsi
0x1400786a6  mov     [rsp+0E0h+var_C0], r14
0x1400786ab  mov     rdx, rdi
0x1400786ae  lea     rcx, aAssertionFaile; "Assertion failed:  %s(%d) - %s - %s (%s"...
0x1400786b5  call    ?DEBUGMSGBOX@@YAHPEBGZZ; DEBUGMSGBOX(ushort const *,...)
0x1400786ba  jmp     loc_1400789A0
0x1400786bf  xor     eax, eax
0x1400786c1  xorps   xmm0, xmm0
0x1400786c4  mov     [rbp+57h+var_70], rax
0x1400786c8  mov     eax, [rbp+57h+ServiceStatus.dwCurrentState]
0x1400786cb  movups  [rbp+57h+pControlParams], xmm0
0x1400786cf  movups  [rbp+57h+var_90], xmm0
0x1400786d3  movups  [rbp+57h+var_80], xmm0
0x1400786d7  sub     eax, 1
0x1400786da  jz      loc_1400788EF
0x1400786e0  sub     eax, 2
0x1400786e3  jz      loc_14007884A
0x1400786e9  sub     eax, 1
0x1400786ec  jz      loc_140078843
0x1400786f2  sub     eax, 2
0x1400786f5  jz      loc_140078796
0x1400786fb  cmp     eax, 1
0x1400786fe  jnz     loc_140078990
0x140078704  lea     r9, [rbp+57h+pControlParams]; pControlParams
0x140078708  mov     r8d, eax; dwInfoLevel
0x14007870b  lea     edx, [rax+2]; dwControl
0x14007870e  mov     rcx, r15; hService
0x140078711  call    cs:__imp_ControlServiceExW
0x140078717  test    eax, eax
0x140078719  jnz     loc_140078990
0x14007871f  call    cs:__imp_GetLastError
0x140078725  mov     ebx, eax
0x140078727  test    eax, eax
0x140078729  jle     short loc_140078734
0x14007872b  movzx   ebx, ax
0x14007872e  or      ebx, 80070000h
0x140078734  mov     eax, 80004005h
0x140078739  lea     r14, aCbraex; "CBRAEx"
0x140078740  test    ebx, ebx
0x140078742  lea     rsi, aDiscoveryservi_1; "DiscoveryService::CheckAndStartDependen"...
0x140078749  lea     rdi, aTermsrvWmsSrcM_1; "termsrv\\wms\\src\\middletier\\discover"...
0x140078750  mov     r9, r14; unsigned __int16 *
0x140078753  cmovns  ebx, eax
0x140078756  lea     r12, aFresult; "fResult"
0x14007875d  mov     [rsp+0E0h+var_B8], ebx; int
0x140078761  mov     r8, rsi; unsigned __int16 *
0x140078764  mov     edx, 1BBh; unsigned int
0x140078769  mov     [rsp+0E0h+var_C0], r12; unsigned __int16 *
0x14007876e  mov     rcx, rdi; unsigned __int16 *
0x140078771  call    ?LOGASSERTHR@@YAXPEBGK000J@Z; LOGASSERTHR(ushort const *,ulong,ushort const *,ushort const *,ushort const *,long)
0x140078776  call    cs:__imp_IsDebuggerPresent
0x14007877c  test    eax, eax
0x14007877e  jz      short loc_14007878B
0x140078780  mov     r9d, 1BBh
0x140078786  jmp     loc_140078668
0x14007878b  mov     r8d, 1BBh
0x140078791  jmp     loc_14007869A
0x140078796  mov     r8d, 7; unsigned int
0x14007879c  mov     rdx, r15; struct SC_HANDLE__ *
0x14007879f  call    ?WaitForServiceStatus@@YAJPEBGPEAUSC_HANDLE__@@K@Z; WaitForServiceStatus(ushort const *,SC_HANDLE__ *,ulong)
0x1400787a4  mov     ebx, eax
0x1400787a6  test    eax, eax
0x1400787a8  js      loc_1400789A0
0x1400787ae  mov     edx, 3; dwControl
0x1400787b3  lea     r9, [rbp+57h+pControlParams]; pControlParams
0x1400787b7  mov     rcx, r15; hService
0x1400787ba  lea     r8d, [rdx-2]; dwInfoLevel
0x1400787be  call    cs:__imp_ControlServiceExW
0x1400787c4  test    eax, eax
0x1400787c6  jnz     loc_140078990
0x1400787cc  call    cs:__imp_GetLastError
0x1400787d2  mov     ebx, eax
0x1400787d4  test    eax, eax
0x1400787d6  jle     short loc_1400787E1
0x1400787d8  movzx   ebx, ax
0x1400787db  or      ebx, 80070000h
0x1400787e1  mov     eax, 80004005h
0x1400787e6  lea     r14, aCbraex; "CBRAEx"
0x1400787ed  test    ebx, ebx
0x1400787ef  lea     rsi, aDiscoveryservi_1; "DiscoveryService::CheckAndStartDependen"...
0x1400787f6  lea     rdi, aTermsrvWmsSrcM_1; "termsrv\\wms\\src\\middletier\\discover"...
0x1400787fd  mov     r9, r14; unsigned __int16 *
0x140078800  cmovns  ebx, eax
0x140078803  lea     r12, aFresult; "fResult"
0x14007880a  mov     [rsp+0E0h+var_B8], ebx; int
0x14007880e  mov     r8, rsi; unsigned __int16 *
0x140078811  mov     edx, 1D2h; unsigned int
0x140078816  mov     [rsp+0E0h+var_C0], r12; unsigned __int16 *
0x14007881b  mov     rcx, rdi; unsigned __int16 *
0x14007881e  call    ?LOGASSERTHR@@YAXPEBGK000J@Z; LOGASSERTHR(ushort const *,ulong,ushort const *,ushort const *,ushort const *,long)
0x140078823  call    cs:__imp_IsDebuggerPresent
0x140078829  test    eax, eax
0x14007882b  jz      short loc_140078838
0x14007882d  mov     r9d, 1D2h
0x140078833  jmp     loc_140078668
0x140078838  mov     r8d, 1D2h
0x14007883e  jmp     loc_14007869A
0x140078843  xor     ebx, ebx
0x140078845  jmp     loc_1400789A0
0x14007884a  mov     r8d, 1; unsigned int
0x140078850  mov     rdx, r15; struct SC_HANDLE__ *
0x140078853  call    ?WaitForServiceStatus@@YAJPEBGPEAUSC_HANDLE__@@K@Z; WaitForServiceStatus(ushort const *,SC_HANDLE__ *,ulong)
0x140078858  mov     ebx, eax
0x14007885a  test    eax, eax
0x14007885c  js      loc_1400789A0
0x140078862  xor     r8d, r8d; lpServiceArgVectors
0x140078865  xor     edx, edx; dwNumServiceArgs
0x140078867  mov     rcx, r15; hService
0x14007886a  call    cs:__imp_StartServiceW
0x140078870  test    eax, eax
0x140078872  jnz     loc_140078990
0x140078878  call    cs:__imp_GetLastError
0x14007887e  mov     ebx, eax
0x140078880  test    eax, eax
0x140078882  jle     short loc_14007888D
0x140078884  movzx   ebx, ax
0x140078887  or      ebx, 80070000h
0x14007888d  mov     eax, 80004005h
0x140078892  lea     r14, aCbraex; "CBRAEx"
0x140078899  test    ebx, ebx
0x14007889b  lea     rsi, aDiscoveryservi_1; "DiscoveryService::CheckAndStartDependen"...
0x1400788a2  lea     rdi, aTermsrvWmsSrcM_1; "termsrv\\wms\\src\\middletier\\discover"...
0x1400788a9  mov     r9, r14; unsigned __int16 *
0x1400788ac  cmovns  ebx, eax
0x1400788af  lea     r12, aFresult; "fResult"
  ... truncated ...
```
