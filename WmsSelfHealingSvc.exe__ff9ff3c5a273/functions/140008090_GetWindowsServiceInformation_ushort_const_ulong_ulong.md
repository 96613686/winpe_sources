# GetWindowsServiceInformation(ushort const *,ulong *,ulong *)

- ea: `0x140008090`
- end: `0x140008507`
- name: `?GetWindowsServiceInformation@@YAJPEBGPEAK1@Z`
- size: `1143`
- prototype: `__int64 __fastcall(const unsigned __int16 *, unsigned int *, unsigned int *)`
- caller_count: `1`
- callee_count: `7`
- tags: `file_ops, registry_config, service_task, broker_com_uri`

## callers

- `0x1400068bc`

## callees

- `0x1400011d4`
- `0x140001b34`
- `0x1400036d8`
- `0x140003918`
- `0x140003c2c`
- `0x140008090`
- `0x14000ae60`

## import_xrefs

- `ADVAPI32!QueryServiceConfigW` at `0x14000823a`
- `ADVAPI32!QueryServiceConfigW` at `0x1400082f5`
- `ADVAPI32!QueryServiceConfigW` at `0x14000823a`
- `ADVAPI32!QueryServiceConfigW` at `0x1400082f5`
- `ADVAPI32!QueryServiceStatus` at `0x140008398`
- `ADVAPI32!QueryServiceStatus` at `0x140008398`
- `ADVAPI32!OpenServiceW` at `0x1400081a5`
- `ADVAPI32!OpenServiceW` at `0x1400081a5`
- `ADVAPI32!CloseServiceHandle` at `0x1400084cc`
- `ADVAPI32!CloseServiceHandle` at `0x1400084da`
- `ADVAPI32!CloseServiceHandle` at `0x1400084cc`
- `ADVAPI32!CloseServiceHandle` at `0x1400084da`
- `ADVAPI32!OpenSCManagerW` at `0x1400080e4`
- `ADVAPI32!OpenSCManagerW` at `0x1400080e4`
- `KERNEL32!IsDebuggerPresent` at `0x140008154`
- `KERNEL32!IsDebuggerPresent` at `0x14000820b`
- `KERNEL32!IsDebuggerPresent` at `0x1400082a8`
- `KERNEL32!IsDebuggerPresent` at `0x14000835a`
- `KERNEL32!IsDebuggerPresent` at `0x1400083fd`
- `KERNEL32!IsDebuggerPresent` at `0x140008485`
- `KERNEL32!IsDebuggerPresent` at `0x140008154`
- `KERNEL32!IsDebuggerPresent` at `0x14000820b`
- `KERNEL32!IsDebuggerPresent` at `0x1400082a8`
- `KERNEL32!IsDebuggerPresent` at `0x14000835a`
- `KERNEL32!IsDebuggerPresent` at `0x1400083fd`
- `KERNEL32!IsDebuggerPresent` at `0x140008485`
- `KERNEL32!GetLastError` at `0x1400080f9`
- `KERNEL32!GetLastError` at `0x1400081ae`
- `KERNEL32!GetLastError` at `0x140008242`
- `KERNEL32!GetLastError` at `0x140008303`
- `KERNEL32!GetLastError` at `0x1400083a6`
- `KERNEL32!GetLastError` at `0x1400080f9`
- `KERNEL32!GetLastError` at `0x1400081ae`
- `KERNEL32!GetLastError` at `0x140008242`
- `KERNEL32!GetLastError` at `0x140008303`
- `KERNEL32!GetLastError` at `0x1400083a6`

## string_xrefs

- `0x140008129`: `termsrv\wms\src\common\srcutils\srcutils.cpp`
- `0x1400081f3`: `termsrv\wms\src\common\srcutils\srcutils.cpp`
- `0x140008281`: `termsrv\wms\src\common\srcutils\srcutils.cpp`
- `0x14000832d`: `termsrv\wms\src\common\srcutils\srcutils.cpp`
- `0x1400083d0`: `termsrv\wms\src\common\srcutils\srcutils.cpp`
- `0x14000846d`: `termsrv\wms\src\common\srcutils\srcutils.cpp`
- `0x1400080d6`: `ServicesActive`
- `0x140008136`: `hServiceManager != 0`
- `0x14000815c`: `hServiceManager != 0`
- `0x14000811c`: `GetWindowsServiceInformation`
- `0x1400081e6`: `GetWindowsServiceInformation`
- `0x140008271`: `GetWindowsServiceInformation`
- `0x140008326`: `GetWindowsServiceInformation`
- `0x1400083c9`: `GetWindowsServiceInformation`
- `0x140008460`: `GetWindowsServiceInformation`
- `0x1400081cf`: `hService != 0 || dwError == 1060L`
- `0x140008213`: `hService != 0 || dwError == 1060L`
- `0x14000828b`: `pQueryServiceConfig`

## pseudocode

```c
__int64 __fastcall GetWindowsServiceInformation(const unsigned __int16 *a1, unsigned int *a2, unsigned int *a3)
{
  struct _QUERY_SERVICE_CONFIGW *v5; // r13
  SC_HANDLE v6; // rax
  SC_HANDLE v7; // r12
  SC_HANDLE v8; // r14
  signed int LastError; // eax
  signed int v10; // edi
  unsigned int v11; // r15d
  bool v12; // zf
  const unsigned __int16 *v13; // rax
  __int64 v14; // r9
  signed int v15; // eax
  BOOL v16; // ebx
  signed int v17; // eax
  struct _QUERY_SERVICE_CONFIGW *v18; // rax
  signed int v19; // eax
  __int64 v20; // r8
  unsigned int dwStartType; // ebx
  signed int v22; // eax
  DWORD dwCurrentState; // eax
  const unsigned __int16 *v25; // [rsp+28h] [rbp-80h]
  const unsigned __int16 *v26; // [rsp+30h] [rbp-78h]
  signed int v27; // [rsp+30h] [rbp-78h]
  signed int v28; // [rsp+38h] [rbp-70h]
  DWORD pcbBytesNeeded; // [rsp+40h] [rbp-68h] BYREF
  DWORD v30; // [rsp+44h] [rbp-64h] BYREF
  struct _SERVICE_STATUS ServiceStatus; // [rsp+48h] [rbp-60h] BYREF

  v5 = 0;
  memset(&ServiceStatus, 0, sizeof(ServiceStatus));
  pcbBytesNeeded = 0;
  v30 = 0;
  v6 = OpenSCManagerW(0, L"ServicesActive", 0x80000000);
  v7 = v6;
  if ( !v6 )
  {
    v8 = 0;
    LastError = GetLastError();
    v10 = LastError;
    if ( LastError > 0 )
      v10 = (unsigned __int16)LastError | 0x80070000;
    v11 = 2538;
    if ( v10 >= 0 )
      v10 = -2147467259;
    LOGASSERTHR(
      L"termsrv\\wms\\src\\common\\srcutils\\srcutils.cpp",
      0x9EAu,
      L"GetWindowsServiceInformation",
      L"CBRAEx",
      L"hServiceManager != 0",
      v10);
    v12 = !IsDebuggerPresent();
    v13 = L"hServiceManager != 0";
LABEL_7:
    if ( !v12 )
    {
      v28 = v10;
      v14 = v11;
      v26 = v13;
LABEL_9:
      DEBUGMSGLEVEL(
        2u,
        L"%s(%d) - %s - Assertion failed:  %s (%s)  hr = 0x%08X\n",
        L"termsrv\\wms\\src\\common\\srcutils\\srcutils.cpp",
        v14,
        L"GetWindowsServiceInformation",
        L"CBRAEx",
        v26,
        v28);
      goto LABEL_45;
    }
    v27 = v10;
    v20 = v11;
    v25 = v13;
    goto LABEL_44;
  }
  v8 = OpenServiceW(v6, L"Wms", 0x80000000);
  v15 = GetLastError();
  v10 = v15;
  if ( !v8 )
  {
    if ( v15 == 1060 )
    {
      v10 = -2147023836;
      goto LABEL_45;
    }
    if ( v15 > 0 )
      v10 = (unsigned __int16)v15 | 0x80070000;
    v11 = 2543;
    LOGASSERTHR(
      L"termsrv\\wms\\src\\common\\srcutils\\srcutils.cpp",
      0x9EFu,
      L"GetWindowsServiceInformation",
      L"CBRAEx",
      L"hService != 0 || dwError == 1060L",
      v10);
    v12 = !IsDebuggerPresent();
    v13 = L"hService != 0 || dwError == 1060L";
    goto LABEL_7;
  }
  v16 = QueryServiceConfigW(v8, 0, 0, &pcbBytesNeeded);
  v17 = GetLastError();
  v10 = v17;
  if ( v16 || v17 != 122 )
  {
    if ( v17 > 0 )
      v10 = (unsigned __int16)v17 | 0x80070000;
    v11 = 2549;
    LOGASSERTHR(
      L"termsrv\\wms\\src\\common\\srcutils\\srcutils.cpp",
      0x9F5u,
      L"GetWindowsServiceInformation",
      L"CBRAEx",
      L"fSuccess == 0 && dwError == 122L",
      v10);
    v12 = !IsDebuggerPresent();
    v13 = L"fSuccess == 0 && dwError == 122L";
    goto LABEL_7;
  }
  v18 = (struct _QUERY_SERVICE_CONFIGW *)operator new(pcbBytesNeeded);
  v5 = v18;
  if ( v18 )
  {
    if ( QueryServiceConfigW(v8, v18, pcbBytesNeeded, &v30) )
    {
      dwStartType = v5->dwStartType;
      if ( QueryServiceStatus(v8, &ServiceStatus) )
      {
        dwCurrentState = ServiceStatus.dwCurrentState;
        v10 = 0;
        *a2 = dwStartType;
        *a3 = dwCurrentState;
        goto LABEL_45;
      }
      v22 = GetLastError();
      v10 = v22;
      if ( v22 > 0 )
        v10 = (unsigned __int16)v22 | 0x80070000;
      if ( v10 >= 0 )
        v10 = -2147467259;
      LOGASSERTHR(
        L"termsrv\\wms\\src\\common\\srcutils\\srcutils.cpp",
        0xA00u,
        L"GetWindowsServiceInformation",
        L"CBRAEx",
        L"fSuccess",
        v10);
      if ( IsDebuggerPresent() )
      {
        v28 = v10;
        v14 = 2560;
        v26 = L"fSuccess";
        goto LABEL_9;
      }
      v27 = v10;
      v20 = 2560;
      v25 = L"fSuccess";
    }
    else
    {
      v19 = GetLastError();
      v10 = v19;
      if ( v19 > 0 )
        v10 = (unsigned __int16)v19 | 0x80070000;
      if ( v10 >= 0 )
        v10 = -2147467259;
      LOGASSERTHR(
        L"termsrv\\wms\\src\\common\\srcutils\\srcutils.cpp",
        0x9FBu,
        L"GetWindowsServiceInformation",
        L"CBRAEx",
        L"fSuccess",
        v10);
      if ( IsDebuggerPresent() )
      {
        v28 = v10;
        v14 = 2555;
        v26 = L"fSuccess";
        goto LABEL_9;
      }
      v27 = v10;
      v20 = 2555;
      v25 = L"fSuccess";
    }
LABEL_44:
    DEBUGMSGBOX(
      L"Assertion failed:  %s(%d) - %s - %s (%s)  hr = 0x%08X\n\n",
      L"termsrv\\wms\\src\\common\\srcutils\\srcutils.cpp",
      v20,
      L"GetWindowsServiceInformation",
      L"CBRAEx",
      v25,
      v27);
    goto LABEL_45;
  }
  v10 = -2147024882;
  LOGASSERTHR(
    L"termsrv\\wms\\src\\common\\srcutils\\srcutils.cpp",
    0x9F8u,
    L"GetWindowsServiceInformation",
    L"CPR",
    L"pQueryServiceConfig",
    -2147024882);
  if ( IsDebuggerPresent() )
    DEBUGMSGLEVEL(
      2u,
      L"%s(%d) - %s - Assertion failed:  %s (%s)  hr = 0x%08X\n",
      L"termsrv\\wms\\src\\common\\srcutils\\srcutils.cpp",
      2552,
      L"GetWindowsServiceInformation",
      L"CPR",
      L"pQueryServiceConfig",
      -2147024882);
  else
    DEBUGMSGBOX(
      L"Assertion failed:  %s(%d) - %s - %s (%s)  hr = 0x%08X\n\n",
      L"termsrv\\wms\\src\\common\\srcutils\\srcutils.cpp",
      2552,
      L"GetWindowsServiceInformation",
      L"CPR",
      L"pQueryServiceConfig",
      -2147024882);
LABEL_45:
  operator delete(v5);
  if ( v8 )
    CloseServiceHandle(v8);
  if ( v7 )
    CloseServiceHandle(v7);
  return (unsigned int)v10;
}

```

## disassembly

```asm
0x140008090  mov     [rsp+arg_0], rbx
0x140008095  push    rbp
0x140008096  push    rsi
0x140008097  push    rdi
0x140008098  push    r12
0x14000809a  push    r13
0x14000809c  push    r14
0x14000809e  push    r15
0x1400080a0  sub     rsp, 70h
0x1400080a4  mov     rax, cs:__security_cookie
0x1400080ab  xor     rax, rsp
0x1400080ae  mov     [rsp+0A8h+var_40], rax
0x1400080b3  xorps   xmm0, xmm0
0x1400080b6  mov     r15, r8
0x1400080b9  mov     rsi, rdx
0x1400080bc  xor     r13d, r13d
0x1400080bf  movups  xmmword ptr [rsp+0A8h+ServiceStatus.dwServiceType], xmm0
0x1400080c4  mov     ebx, 80000000h
0x1400080c9  mov     [rsp+0A8h+pcbBytesNeeded], r13d
0x1400080ce  mov     r8d, ebx; dwDesiredAccess
0x1400080d1  mov     [rsp+0A8h+var_64], r13d
0x1400080d6  lea     rdx, DatabaseName; "ServicesActive"
0x1400080dd  xor     ecx, ecx; lpMachineName
0x1400080df  movups  xmmword ptr [rsp+0A8h+ServiceStatus.dwWin32ExitCode], xmm0
0x1400080e4  call    cs:__imp_OpenSCManagerW
0x1400080ea  mov     r12, rax
0x1400080ed  test    rax, rax
0x1400080f0  jnz     loc_140008198
0x1400080f6  xor     r14d, r14d
0x1400080f9  call    cs:__imp_GetLastError
0x1400080ff  mov     edi, eax
0x140008101  test    eax, eax
0x140008103  jle     short loc_14000810E
0x140008105  movzx   edi, ax
0x140008108  or      edi, 80070000h
0x14000810e  mov     eax, 80004005h
0x140008113  lea     rbp, aCbraex; "CBRAEx"
0x14000811a  test    edi, edi
0x14000811c  lea     rsi, aGetwindowsserv; "GetWindowsServiceInformation"
0x140008123  mov     r15d, 9EAh
0x140008129  lea     rbx, aTermsrvWmsSrcC_4; "termsrv\\wms\\src\\common\\srcutils\\sr"...
0x140008130  cmovns  edi, eax
0x140008133  mov     r9, rbp; unsigned __int16 *
0x140008136  lea     rax, aHservicemanage; "hServiceManager != 0"
0x14000813d  mov     [rsp+0A8h+var_80], edi; int
0x140008141  mov     r8, rsi; unsigned __int16 *
0x140008144  mov     [rsp+0A8h+var_88], rax; unsigned __int16 *
0x140008149  mov     edx, r15d; unsigned int
0x14000814c  mov     rcx, rbx; unsigned __int16 *
0x14000814f  call    ?LOGASSERTHR@@YAXPEBGK000J@Z; LOGASSERTHR(ushort const *,ulong,ushort const *,ushort const *,ushort const *,long)
0x140008154  call    cs:__imp_IsDebuggerPresent
0x14000815a  test    eax, eax
0x14000815c  lea     rax, aHservicemanage; "hServiceManager != 0"
0x140008163  jz      loc_140008499
0x140008169  mov     [rsp+0A8h+var_70], edi
0x14000816d  mov     r9d, r15d
0x140008170  mov     [rsp+0A8h+var_78], rax
0x140008175  mov     qword ptr [rsp+0A8h+var_80], rbp
0x14000817a  mov     r8, rbx
0x14000817d  mov     [rsp+0A8h+var_88], rsi
0x140008182  lea     rdx, aSDSAssertionFa_0; "%s(%d) - %s - Assertion failed:  %s (%s"...
0x140008189  mov     ecx, 2; unsigned __int8
0x14000818e  call    ?DEBUGMSGLEVEL@@YAXEPEBGZZ; DEBUGMSGLEVEL(uchar,ushort const *,...)
0x140008193  jmp     loc_1400084BC
0x140008198  mov     r8d, ebx; dwDesiredAccess
0x14000819b  lea     rdx, ServiceName; "Wms"
0x1400081a2  mov     rcx, r12; hSCManager
0x1400081a5  call    cs:__imp_OpenServiceW
0x1400081ab  mov     r14, rax
0x1400081ae  call    cs:__imp_GetLastError
0x1400081b4  mov     edi, eax
0x1400081b6  test    r14, r14
0x1400081b9  jnz     short loc_14000822D
0x1400081bb  cmp     eax, 424h
0x1400081c0  jz      short loc_14000821F
0x1400081c2  test    eax, eax
0x1400081c4  jle     short loc_1400081CF
0x1400081c6  movzx   edi, ax
0x1400081c9  or      edi, 80070000h
0x1400081cf  lea     rax, aHservice0Dwerr; "hService != 0 || dwError == 1060L"
0x1400081d6  mov     [rsp+0A8h+var_80], edi; int
0x1400081da  lea     rbp, aCbraex; "CBRAEx"
0x1400081e1  mov     [rsp+0A8h+var_88], rax; unsigned __int16 *
0x1400081e6  lea     rsi, aGetwindowsserv; "GetWindowsServiceInformation"
0x1400081ed  mov     r15d, 9EFh
0x1400081f3  lea     rbx, aTermsrvWmsSrcC_4; "termsrv\\wms\\src\\common\\srcutils\\sr"...
0x1400081fa  mov     r9, rbp; unsigned __int16 *
0x1400081fd  mov     r8, rsi; unsigned __int16 *
0x140008200  mov     edx, r15d; unsigned int
0x140008203  mov     rcx, rbx; unsigned __int16 *
0x140008206  call    ?LOGASSERTHR@@YAXPEBGK000J@Z; LOGASSERTHR(ushort const *,ulong,ushort const *,ushort const *,ushort const *,long)
0x14000820b  call    cs:__imp_IsDebuggerPresent
0x140008211  test    eax, eax
0x140008213  lea     rax, aHservice0Dwerr; "hService != 0 || dwError == 1060L"
0x14000821a  jmp     loc_140008163
0x14000821f  movzx   edi, ax
0x140008222  or      edi, 80070000h
0x140008228  jmp     loc_1400084BC
0x14000822d  lea     r9, [rsp+0A8h+pcbBytesNeeded]; pcbBytesNeeded
0x140008232  xor     r8d, r8d; cbBufSize
0x140008235  xor     edx, edx; lpServiceConfig
0x140008237  mov     rcx, r14; hService
0x14000823a  call    cs:__imp_QueryServiceConfigW
0x140008240  mov     ebx, eax
0x140008242  call    cs:__imp_GetLastError
0x140008248  mov     edi, eax
0x14000824a  test    ebx, ebx
0x14000824c  jnz     loc_14000843C
0x140008252  cmp     eax, 7Ah ; 'z'
0x140008255  jnz     loc_14000843C
0x14000825b  mov     ecx, [rsp+0A8h+pcbBytesNeeded]; Size
0x14000825f  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x140008264  mov     r13, rax
0x140008267  test    rax, rax
0x14000826a  jnz     short loc_1400082E5
0x14000826c  mov     edi, 8007000Eh
0x140008271  lea     rsi, aGetwindowsserv; "GetWindowsServiceInformation"
0x140008278  mov     ebp, 9F8h
0x14000827d  mov     [rsp+0A8h+var_80], edi; int
0x140008281  lea     rbx, aTermsrvWmsSrcC_4; "termsrv\\wms\\src\\common\\srcutils\\sr"...
0x140008288  mov     r8, rsi; unsigned __int16 *
0x14000828b  lea     r15, aPqueryservicec; "pQueryServiceConfig"
0x140008292  mov     edx, ebp; unsigned int
0x140008294  mov     rcx, rbx; unsigned __int16 *
0x140008297  mov     [rsp+0A8h+var_88], r15; unsigned __int16 *
0x14000829c  lea     r9, aCpr; "CPR"
0x1400082a3  call    ?LOGASSERTHR@@YAXPEBGK000J@Z; LOGASSERTHR(ushort const *,ulong,ushort const *,ushort const *,ushort const *,long)
0x1400082a8  call    cs:__imp_IsDebuggerPresent
0x1400082ae  test    eax, eax
0x1400082b0  lea     rax, aCpr; "CPR"
0x1400082b7  jz      short loc_1400082CF
0x1400082b9  mov     [rsp+0A8h+var_70], edi
0x1400082bd  mov     r9d, ebp
0x1400082c0  mov     [rsp+0A8h+var_78], r15
0x1400082c5  mov     qword ptr [rsp+0A8h+var_80], rax
0x1400082ca  jmp     loc_14000817A
0x1400082cf  mov     dword ptr [rsp+0A8h+var_78], edi
0x1400082d3  mov     r8d, ebp
0x1400082d6  mov     qword ptr [rsp+0A8h+var_80], r15
0x1400082db  mov     [rsp+0A8h+var_88], rax
0x1400082e0  jmp     loc_1400084AA
0x1400082e5  mov     r8d, [rsp+0A8h+pcbBytesNeeded]; cbBufSize
0x1400082ea  lea     r9, [rsp+0A8h+var_64]; pcbBytesNeeded
0x1400082ef  mov     rdx, r13; lpServiceConfig
0x1400082f2  mov     rcx, r14; hService
0x1400082f5  call    cs:__imp_QueryServiceConfigW
0x1400082fb  test    eax, eax
0x1400082fd  jnz     loc_14000838C
0x140008303  call    cs:__imp_GetLastError
0x140008309  mov     edi, eax
0x14000830b  test    eax, eax
0x14000830d  jle     short loc_140008318
0x14000830f  movzx   edi, ax
0x140008312  or      edi, 80070000h
0x140008318  mov     eax, 80004005h
0x14000831d  lea     rbp, aCbraex; "CBRAEx"
0x140008324  test    edi, edi
0x140008326  lea     rsi, aGetwindowsserv; "GetWindowsServiceInformation"
0x14000832d  lea     rbx, aTermsrvWmsSrcC_4; "termsrv\\wms\\src\\common\\srcutils\\sr"...
0x140008334  mov     r9, rbp; unsigned __int16 *
0x140008337  cmovns  edi, eax
0x14000833a  lea     r15, aFsuccess; "fSuccess"
0x140008341  mov     [rsp+0A8h+var_80], edi; int
0x140008345  mov     r8, rsi; unsigned __int16 *
0x140008348  mov     edx, 9FBh; unsigned int
0x14000834d  mov     [rsp+0A8h+var_88], r15; unsigned __int16 *
0x140008352  mov     rcx, rbx; unsigned __int16 *
0x140008355  call    ?LOGASSERTHR@@YAXPEBGK000J@Z; LOGASSERTHR(ushort const *,ulong,ushort const *,ushort const *,ushort const *,long)
0x14000835a  call    cs:__imp_IsDebuggerPresent
0x140008360  test    eax, eax
0x140008362  jz      short loc_140008378
0x140008364  mov     [rsp+0A8h+var_70], edi
0x140008368  mov     r9d, 9FBh
0x14000836e  mov     [rsp+0A8h+var_78], r15
0x140008373  jmp     loc_140008175
0x140008378  mov     dword ptr [rsp+0A8h+var_78], edi
0x14000837c  mov     r8d, 9FBh
0x140008382  mov     qword ptr [rsp+0A8h+var_80], r15
0x140008387  jmp     loc_1400084A5
0x14000838c  mov     ebx, [r13+4]
0x140008390  lea     rdx, [rsp+0A8h+ServiceStatus]; lpServiceStatus
0x140008395  mov     rcx, r14; hService
0x140008398  call    cs:__imp_QueryServiceStatus
0x14000839e  test    eax, eax
0x1400083a0  jnz     loc_14000842C
0x1400083a6  call    cs:__imp_GetLastError
0x1400083ac  mov     edi, eax
0x1400083ae  test    eax, eax
0x1400083b0  jle     short loc_1400083BB
0x1400083b2  movzx   edi, ax
0x1400083b5  or      edi, 80070000h
0x1400083bb  mov     eax, 80004005h
0x1400083c0  lea     rbp, aCbraex; "CBRAEx"
0x1400083c7  test    edi, edi
0x1400083c9  lea     rsi, aGetwindowsserv; "GetWindowsServiceInformation"
0x1400083d0  lea     rbx, aTermsrvWmsSrcC_4; "termsrv\\wms\\src\\common\\srcutils\\sr"...
0x1400083d7  mov     r9, rbp; unsigned __int16 *
0x1400083da  cmovns  edi, eax
0x1400083dd  lea     r15, aFsuccess; "fSuccess"
0x1400083e4  mov     [rsp+0A8h+var_80], edi; int
0x1400083e8  mov     r8, rsi; unsigned __int16 *
0x1400083eb  mov     edx, 0A00h; unsigned int
0x1400083f0  mov     [rsp+0A8h+var_88], r15; unsigned __int16 *
0x1400083f5  mov     rcx, rbx; unsigned __int16 *
0x1400083f8  call    ?LOGASSERTHR@@YAXPEBGK000J@Z; LOGASSERTHR(ushort const *,ulong,ushort const *,ushort const *,ushort const *,long)
0x1400083fd  call    cs:__imp_IsDebuggerPresent
0x140008403  test    eax, eax
0x140008405  jz      short loc_14000841B
0x140008407  mov     [rsp+0A8h+var_70], edi
0x14000840b  mov     r9d, 0A00h
0x140008411  mov     [rsp+0A8h+var_78], r15
0x140008416  jmp     loc_140008175
0x14000841b  mov     dword ptr [rsp+0A8h+var_78], edi
0x14000841f  mov     r8d, 0A00h
0x140008425  mov     qword ptr [rsp+0A8h+var_80], r15
0x14000842a  jmp     short loc_1400084A5
0x14000842c  mov     eax, [rsp+0A8h+ServiceStatus.dwCurrentState]
0x140008430  xor     edi, edi
0x140008432  mov     [rsi], ebx
0x140008434  mov     [r15], eax
0x140008437  jmp     loc_1400084BC
0x14000843c  test    eax, eax
0x14000843e  jle     short loc_140008449
0x140008440  movzx   edi, ax
0x140008443  or      edi, 80070000h
0x140008449  lea     rax, aFsuccess0Dwerr; "fSuccess == 0 && dwError == 122L"
0x140008450  mov     [rsp+0A8h+var_80], edi; int
0x140008454  lea     rbp, aCbraex; "CBRAEx"
0x14000845b  mov     [rsp+0A8h+var_88], rax; unsigned __int16 *
0x140008460  lea     rsi, aGetwindowsserv; "GetWindowsServiceInformation"
0x140008467  mov     r15d, 9F5h
0x14000846d  lea     rbx, aTermsrvWmsSrcC_4; "termsrv\\wms\\src\\common\\srcutils\\sr"...
0x140008474  mov     r9, rbp; unsigned __int16 *
0x140008477  mov     r8, rsi; unsigned __int16 *
0x14000847a  mov     edx, r15d; unsigned int
0x14000847d  mov     rcx, rbx; unsigned __int16 *
0x140008480  call    ?LOGASSERTHR@@YAXPEBGK000J@Z; LOGASSERTHR(ushort const *,ulong,ushort const *,ushort const *,ushort const *,long)
0x140008485  call    cs:__imp_IsDebuggerPresent
0x14000848b  test    eax, eax
0x14000848d  lea     rax, aFsuccess0Dwerr; "fSuccess == 0 && dwError == 122L"
0x140008494  jmp     loc_140008163
0x140008499  mov     dword ptr [rsp+0A8h+var_78], edi
0x14000849d  mov     r8d, r15d
0x1400084a0  mov     qword ptr [rsp+0A8h+var_80], rax
0x1400084a5  mov     [rsp+0A8h+var_88], rbp
0x1400084aa  mov     r9, rsi
0x1400084ad  lea     rcx, aAssertionFaile; "Assertion failed:  %s(%d) - %s - %s (%s"...
0x1400084b4  mov     rdx, rbx
0x1400084b7  call    ?DEBUGMSGBOX@@YAHPEBGZZ; DEBUGMSGBOX(ushort const *,...)
0x1400084bc  mov     rcx, r13; Block
0x1400084bf  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1400084c4  test    r14, r14
0x1400084c7  jz      short loc_1400084D2
0x1400084c9  mov     rcx, r14; hSCObject
0x1400084cc  call    cs:__imp_CloseServiceHandle
0x1400084d2  test    r12, r12
0x1400084d5  jz      short loc_1400084E0
0x1400084d7  mov     rcx, r12; hSCObject
0x1400084da  call    cs:__imp_CloseServiceHandle
0x1400084e0  mov     eax, edi
0x1400084e2  mov     rcx, [rsp+0A8h+var_40]
0x1400084e7  xor     rcx, rsp; StackCookie
0x1400084ea  call    __security_check_cookie
0x1400084ef  mov     rbx, [rsp+0A8h+arg_0]
0x1400084f7  add     rsp, 70h
0x1400084fb  pop     r15
0x1400084fd  pop     r14
0x1400084ff  pop     r13
0x140008501  pop     r12
0x140008503  pop     rdi
0x140008504  pop     rsi
0x140008505  pop     rbp
0x140008506  retn
```
