# GetWindowsServiceInformation(ushort const *,ulong *,ulong *)

- ea: `0x140067778`
- end: `0x140067bee`
- name: `?GetWindowsServiceInformation@@YAJPEBGPEAK1@Z`
- size: `1142`
- prototype: `__int64 __fastcall(LPCWSTR lpServiceName, unsigned int *, unsigned int *)`
- caller_count: `1`
- callee_count: `7`
- tags: `file_ops, registry_config, service_task, broker_com_uri`

## callers

- `0x140065368`

## callees

- `0x1400016b8`
- `0x1400016c4`
- `0x14005bc68`
- `0x14005bfec`
- `0x14005c408`
- `0x140067778`
- `0x14007cbd0`

## import_xrefs

- `ADVAPI32!OpenSCManagerW` at `0x1400677cf`
- `ADVAPI32!OpenSCManagerW` at `0x1400677cf`
- `ADVAPI32!OpenServiceW` at `0x14006788c`
- `ADVAPI32!OpenServiceW` at `0x14006788c`
- `ADVAPI32!QueryServiceStatus` at `0x140067a7f`
- `ADVAPI32!QueryServiceStatus` at `0x140067a7f`
- `ADVAPI32!CloseServiceHandle` at `0x140067bb3`
- `ADVAPI32!CloseServiceHandle` at `0x140067bc1`
- `ADVAPI32!CloseServiceHandle` at `0x140067bb3`
- `ADVAPI32!CloseServiceHandle` at `0x140067bc1`
- `ADVAPI32!QueryServiceConfigW` at `0x140067921`
- `ADVAPI32!QueryServiceConfigW` at `0x1400679dc`
- `ADVAPI32!QueryServiceConfigW` at `0x140067921`
- `ADVAPI32!QueryServiceConfigW` at `0x1400679dc`
- `KERNEL32!GetLastError` at `0x1400677e4`
- `KERNEL32!GetLastError` at `0x140067895`
- `KERNEL32!GetLastError` at `0x140067929`
- `KERNEL32!GetLastError` at `0x1400679ea`
- `KERNEL32!GetLastError` at `0x140067a8d`
- `KERNEL32!GetLastError` at `0x1400677e4`
- `KERNEL32!GetLastError` at `0x140067895`
- `KERNEL32!GetLastError` at `0x140067929`
- `KERNEL32!GetLastError` at `0x1400679ea`
- `KERNEL32!GetLastError` at `0x140067a8d`
- `KERNEL32!IsDebuggerPresent` at `0x14006783f`
- `KERNEL32!IsDebuggerPresent` at `0x1400678f2`
- `KERNEL32!IsDebuggerPresent` at `0x14006798f`
- `KERNEL32!IsDebuggerPresent` at `0x140067a41`
- `KERNEL32!IsDebuggerPresent` at `0x140067ae4`
- `KERNEL32!IsDebuggerPresent` at `0x140067b6c`
- `KERNEL32!IsDebuggerPresent` at `0x14006783f`
- `KERNEL32!IsDebuggerPresent` at `0x1400678f2`
- `KERNEL32!IsDebuggerPresent` at `0x14006798f`
- `KERNEL32!IsDebuggerPresent` at `0x140067a41`
- `KERNEL32!IsDebuggerPresent` at `0x140067ae4`
- `KERNEL32!IsDebuggerPresent` at `0x140067b6c`

## string_xrefs

- `0x1400677aa`: `ServicesActive`
- `0x140067814`: `termsrv\wms\src\common\srcutils\srcutils.cpp`
- `0x1400678da`: `termsrv\wms\src\common\srcutils\srcutils.cpp`
- `0x140067968`: `termsrv\wms\src\common\srcutils\srcutils.cpp`
- `0x140067a14`: `termsrv\wms\src\common\srcutils\srcutils.cpp`
- `0x140067ab7`: `termsrv\wms\src\common\srcutils\srcutils.cpp`
- `0x140067b54`: `termsrv\wms\src\common\srcutils\srcutils.cpp`
- `0x140067821`: `hServiceManager != 0`
- `0x140067847`: `hServiceManager != 0`
- `0x140067807`: `GetWindowsServiceInformation`
- `0x1400678cd`: `GetWindowsServiceInformation`
- `0x140067958`: `GetWindowsServiceInformation`
- `0x140067a0d`: `GetWindowsServiceInformation`
- `0x140067ab0`: `GetWindowsServiceInformation`
- `0x140067b47`: `GetWindowsServiceInformation`
- `0x1400678b6`: `hService != 0 || dwError == 1060L`
- `0x1400678fa`: `hService != 0 || dwError == 1060L`
- `0x140067972`: `pQueryServiceConfig`

## pseudocode

```c
__int64 __fastcall GetWindowsServiceInformation(LPCWSTR lpServiceName, unsigned int *a2, unsigned int *a3)
{
  struct _QUERY_SERVICE_CONFIGW *v6; // r13
  SC_HANDLE v7; // rax
  SC_HANDLE v8; // r12
  SC_HANDLE v9; // r14
  signed int LastError; // eax
  signed int v11; // edi
  unsigned int v12; // r15d
  bool v13; // zf
  const unsigned __int16 *v14; // rax
  __int64 v15; // r9
  signed int v16; // eax
  BOOL v17; // ebx
  signed int v18; // eax
  struct _QUERY_SERVICE_CONFIGW *v19; // rax
  signed int v20; // eax
  __int64 v21; // r8
  unsigned int dwStartType; // ebx
  signed int v23; // eax
  DWORD dwCurrentState; // eax
  const unsigned __int16 *v26; // [rsp+28h] [rbp-80h]
  const unsigned __int16 *v27; // [rsp+30h] [rbp-78h]
  signed int v28; // [rsp+30h] [rbp-78h]
  signed int v29; // [rsp+38h] [rbp-70h]
  DWORD pcbBytesNeeded; // [rsp+40h] [rbp-68h] BYREF
  DWORD v31; // [rsp+44h] [rbp-64h] BYREF
  struct _SERVICE_STATUS ServiceStatus; // [rsp+48h] [rbp-60h] BYREF

  v6 = 0;
  memset(&ServiceStatus, 0, sizeof(ServiceStatus));
  pcbBytesNeeded = 0;
  v31 = 0;
  v7 = OpenSCManagerW(0, L"ServicesActive", 0x80000000);
  v8 = v7;
  if ( !v7 )
  {
    v9 = 0;
    LastError = GetLastError();
    v11 = LastError;
    if ( LastError > 0 )
      v11 = (unsigned __int16)LastError | 0x80070000;
    v12 = 2538;
    if ( v11 >= 0 )
      v11 = -2147467259;
    LOGASSERTHR(
      L"termsrv\\wms\\src\\common\\srcutils\\srcutils.cpp",
      0x9EAu,
      L"GetWindowsServiceInformation",
      L"CBRAEx",
      L"hServiceManager != 0",
      v11);
    v13 = !IsDebuggerPresent();
    v14 = L"hServiceManager != 0";
LABEL_7:
    if ( !v13 )
    {
      v29 = v11;
      v15 = v12;
      v27 = v14;
LABEL_9:
      DEBUGMSGLEVEL(
        2u,
        L"%s(%d) - %s - Assertion failed:  %s (%s)  hr = 0x%08X\n",
        L"termsrv\\wms\\src\\common\\srcutils\\srcutils.cpp",
        v15,
        L"GetWindowsServiceInformation",
        L"CBRAEx",
        v27,
        v29);
      goto LABEL_45;
    }
    v28 = v11;
    v21 = v12;
    v26 = v14;
    goto LABEL_44;
  }
  v9 = OpenServiceW(v7, lpServiceName, 0x80000000);
  v16 = GetLastError();
  v11 = v16;
  if ( !v9 )
  {
    if ( v16 == 1060 )
    {
      v11 = -2147023836;
      goto LABEL_45;
    }
    if ( v16 > 0 )
      v11 = (unsigned __int16)v16 | 0x80070000;
    v12 = 2543;
    LOGASSERTHR(
      L"termsrv\\wms\\src\\common\\srcutils\\srcutils.cpp",
      0x9EFu,
      L"GetWindowsServiceInformation",
      L"CBRAEx",
      L"hService != 0 || dwError == 1060L",
      v11);
    v13 = !IsDebuggerPresent();
    v14 = L"hService != 0 || dwError == 1060L";
    goto LABEL_7;
  }
  v17 = QueryServiceConfigW(v9, 0, 0, &pcbBytesNeeded);
  v18 = GetLastError();
  v11 = v18;
  if ( v17 || v18 != 122 )
  {
    if ( v18 > 0 )
      v11 = (unsigned __int16)v18 | 0x80070000;
    v12 = 2549;
    LOGASSERTHR(
      L"termsrv\\wms\\src\\common\\srcutils\\srcutils.cpp",
      0x9F5u,
      L"GetWindowsServiceInformation",
      L"CBRAEx",
      L"fSuccess == 0 && dwError == 122L",
      v11);
    v13 = !IsDebuggerPresent();
    v14 = L"fSuccess == 0 && dwError == 122L";
    goto LABEL_7;
  }
  v19 = (struct _QUERY_SERVICE_CONFIGW *)operator new(pcbBytesNeeded);
  v6 = v19;
  if ( v19 )
  {
    if ( QueryServiceConfigW(v9, v19, pcbBytesNeeded, &v31) )
    {
      dwStartType = v6->dwStartType;
      if ( QueryServiceStatus(v9, &ServiceStatus) )
      {
        dwCurrentState = ServiceStatus.dwCurrentState;
        v11 = 0;
        *a2 = dwStartType;
        *a3 = dwCurrentState;
        goto LABEL_45;
      }
      v23 = GetLastError();
      v11 = v23;
      if ( v23 > 0 )
        v11 = (unsigned __int16)v23 | 0x80070000;
      if ( v11 >= 0 )
        v11 = -2147467259;
      LOGASSERTHR(
        L"termsrv\\wms\\src\\common\\srcutils\\srcutils.cpp",
        0xA00u,
        L"GetWindowsServiceInformation",
        L"CBRAEx",
        L"fSuccess",
        v11);
      if ( IsDebuggerPresent() )
      {
        v29 = v11;
        v15 = 2560;
        v27 = L"fSuccess";
        goto LABEL_9;
      }
      v28 = v11;
      v21 = 2560;
      v26 = L"fSuccess";
    }
    else
    {
      v20 = GetLastError();
      v11 = v20;
      if ( v20 > 0 )
        v11 = (unsigned __int16)v20 | 0x80070000;
      if ( v11 >= 0 )
        v11 = -2147467259;
      LOGASSERTHR(
        L"termsrv\\wms\\src\\common\\srcutils\\srcutils.cpp",
        0x9FBu,
        L"GetWindowsServiceInformation",
        L"CBRAEx",
        L"fSuccess",
        v11);
      if ( IsDebuggerPresent() )
      {
        v29 = v11;
        v15 = 2555;
        v27 = L"fSuccess";
        goto LABEL_9;
      }
      v28 = v11;
      v21 = 2555;
      v26 = L"fSuccess";
    }
LABEL_44:
    DEBUGMSGBOX(
      L"Assertion failed:  %s(%d) - %s - %s (%s)  hr = 0x%08X\n\n",
      L"termsrv\\wms\\src\\common\\srcutils\\srcutils.cpp",
      v21,
      L"GetWindowsServiceInformation",
      L"CBRAEx",
      v26,
      v28);
    goto LABEL_45;
  }
  v11 = -2147024882;
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
  operator delete(v6);
  if ( v9 )
    CloseServiceHandle(v9);
  if ( v8 )
    CloseServiceHandle(v8);
  return (unsigned int)v11;
}

```

## disassembly

```asm
0x140067778  mov     [rsp+arg_18], rbx
0x14006777d  push    rbp
0x14006777e  push    rsi
0x14006777f  push    rdi
0x140067780  push    r12
0x140067782  push    r13
0x140067784  push    r14
0x140067786  push    r15
0x140067788  sub     rsp, 70h
0x14006778c  mov     rax, cs:__security_cookie
0x140067793  xor     rax, rsp
0x140067796  mov     [rsp+0A8h+var_40], rax
0x14006779b  xorps   xmm0, xmm0
0x14006779e  mov     r15, r8
0x1400677a1  mov     rsi, rdx
0x1400677a4  mov     rbx, rcx
0x1400677a7  xor     r13d, r13d
0x1400677aa  lea     rdx, DatabaseName; "ServicesActive"
0x1400677b1  movups  xmmword ptr [rsp+0A8h+ServiceStatus.dwServiceType], xmm0
0x1400677b6  mov     edi, 80000000h
0x1400677bb  mov     [rsp+0A8h+pcbBytesNeeded], r13d
0x1400677c0  mov     r8d, edi; dwDesiredAccess
0x1400677c3  mov     [rsp+0A8h+var_64], r13d
0x1400677c8  xor     ecx, ecx; lpMachineName
0x1400677ca  movups  xmmword ptr [rsp+0A8h+ServiceStatus.dwWin32ExitCode], xmm0
0x1400677cf  call    cs:__imp_OpenSCManagerW
0x1400677d5  mov     r12, rax
0x1400677d8  test    rax, rax
0x1400677db  jnz     loc_140067883
0x1400677e1  xor     r14d, r14d
0x1400677e4  call    cs:__imp_GetLastError
0x1400677ea  mov     edi, eax
0x1400677ec  test    eax, eax
0x1400677ee  jle     short loc_1400677F9
0x1400677f0  movzx   edi, ax
0x1400677f3  or      edi, 80070000h
0x1400677f9  mov     eax, 80004005h
0x1400677fe  lea     rbp, aCbraex; "CBRAEx"
0x140067805  test    edi, edi
0x140067807  lea     rsi, aGetwindowsserv; "GetWindowsServiceInformation"
0x14006780e  mov     r15d, 9EAh
0x140067814  lea     rbx, aTermsrvWmsSrcC_22; "termsrv\\wms\\src\\common\\srcutils\\sr"...
0x14006781b  cmovns  edi, eax
0x14006781e  mov     r9, rbp; unsigned __int16 *
0x140067821  lea     rax, aHservicemanage; "hServiceManager != 0"
0x140067828  mov     [rsp+0A8h+var_80], edi; int
0x14006782c  mov     r8, rsi; unsigned __int16 *
0x14006782f  mov     [rsp+0A8h+var_88], rax; unsigned __int16 *
0x140067834  mov     edx, r15d; unsigned int
0x140067837  mov     rcx, rbx; unsigned __int16 *
0x14006783a  call    ?LOGASSERTHR@@YAXPEBGK000J@Z; LOGASSERTHR(ushort const *,ulong,ushort const *,ushort const *,ushort const *,long)
0x14006783f  call    cs:__imp_IsDebuggerPresent
0x140067845  test    eax, eax
0x140067847  lea     rax, aHservicemanage; "hServiceManager != 0"
0x14006784e  jz      loc_140067B80
0x140067854  mov     [rsp+0A8h+var_70], edi
0x140067858  mov     r9d, r15d
0x14006785b  mov     [rsp+0A8h+var_78], rax
0x140067860  mov     qword ptr [rsp+0A8h+var_80], rbp
0x140067865  mov     r8, rbx
0x140067868  mov     [rsp+0A8h+var_88], rsi
0x14006786d  lea     rdx, aSDSAssertionFa_0; "%s(%d) - %s - Assertion failed:  %s (%s"...
0x140067874  mov     ecx, 2; unsigned __int8
0x140067879  call    ?DEBUGMSGLEVEL@@YAXEPEBGZZ; DEBUGMSGLEVEL(uchar,ushort const *,...)
0x14006787e  jmp     loc_140067BA3
0x140067883  mov     r8d, edi; dwDesiredAccess
0x140067886  mov     rdx, rbx; lpServiceName
0x140067889  mov     rcx, r12; hSCManager
0x14006788c  call    cs:__imp_OpenServiceW
0x140067892  mov     r14, rax
0x140067895  call    cs:__imp_GetLastError
0x14006789b  mov     edi, eax
0x14006789d  test    r14, r14
0x1400678a0  jnz     short loc_140067914
0x1400678a2  cmp     eax, 424h
0x1400678a7  jz      short loc_140067906
0x1400678a9  test    eax, eax
0x1400678ab  jle     short loc_1400678B6
0x1400678ad  movzx   edi, ax
0x1400678b0  or      edi, 80070000h
0x1400678b6  lea     rax, aHservice0Dwerr; "hService != 0 || dwError == 1060L"
0x1400678bd  mov     [rsp+0A8h+var_80], edi; int
0x1400678c1  lea     rbp, aCbraex; "CBRAEx"
0x1400678c8  mov     [rsp+0A8h+var_88], rax; unsigned __int16 *
0x1400678cd  lea     rsi, aGetwindowsserv; "GetWindowsServiceInformation"
0x1400678d4  mov     r15d, 9EFh
0x1400678da  lea     rbx, aTermsrvWmsSrcC_22; "termsrv\\wms\\src\\common\\srcutils\\sr"...
0x1400678e1  mov     r9, rbp; unsigned __int16 *
0x1400678e4  mov     r8, rsi; unsigned __int16 *
0x1400678e7  mov     edx, r15d; unsigned int
0x1400678ea  mov     rcx, rbx; unsigned __int16 *
0x1400678ed  call    ?LOGASSERTHR@@YAXPEBGK000J@Z; LOGASSERTHR(ushort const *,ulong,ushort const *,ushort const *,ushort const *,long)
0x1400678f2  call    cs:__imp_IsDebuggerPresent
0x1400678f8  test    eax, eax
0x1400678fa  lea     rax, aHservice0Dwerr; "hService != 0 || dwError == 1060L"
0x140067901  jmp     loc_14006784E
0x140067906  movzx   edi, ax
0x140067909  or      edi, 80070000h
0x14006790f  jmp     loc_140067BA3
0x140067914  lea     r9, [rsp+0A8h+pcbBytesNeeded]; pcbBytesNeeded
0x140067919  xor     r8d, r8d; cbBufSize
0x14006791c  xor     edx, edx; lpServiceConfig
0x14006791e  mov     rcx, r14; hService
0x140067921  call    cs:__imp_QueryServiceConfigW
0x140067927  mov     ebx, eax
0x140067929  call    cs:__imp_GetLastError
0x14006792f  mov     edi, eax
0x140067931  test    ebx, ebx
0x140067933  jnz     loc_140067B23
0x140067939  cmp     eax, 7Ah ; 'z'
0x14006793c  jnz     loc_140067B23
0x140067942  mov     ecx, [rsp+0A8h+pcbBytesNeeded]; Size
0x140067946  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x14006794b  mov     r13, rax
0x14006794e  test    rax, rax
0x140067951  jnz     short loc_1400679CC
0x140067953  mov     edi, 8007000Eh
0x140067958  lea     rsi, aGetwindowsserv; "GetWindowsServiceInformation"
0x14006795f  mov     ebp, 9F8h
0x140067964  mov     [rsp+0A8h+var_80], edi; int
0x140067968  lea     rbx, aTermsrvWmsSrcC_22; "termsrv\\wms\\src\\common\\srcutils\\sr"...
0x14006796f  mov     r8, rsi; unsigned __int16 *
0x140067972  lea     r15, aPqueryservicec; "pQueryServiceConfig"
0x140067979  mov     edx, ebp; unsigned int
0x14006797b  mov     rcx, rbx; unsigned __int16 *
0x14006797e  mov     [rsp+0A8h+var_88], r15; unsigned __int16 *
0x140067983  lea     r9, aCpr; "CPR"
0x14006798a  call    ?LOGASSERTHR@@YAXPEBGK000J@Z; LOGASSERTHR(ushort const *,ulong,ushort const *,ushort const *,ushort const *,long)
0x14006798f  call    cs:__imp_IsDebuggerPresent
0x140067995  test    eax, eax
0x140067997  lea     rax, aCpr; "CPR"
0x14006799e  jz      short loc_1400679B6
0x1400679a0  mov     [rsp+0A8h+var_70], edi
0x1400679a4  mov     r9d, ebp
0x1400679a7  mov     [rsp+0A8h+var_78], r15
0x1400679ac  mov     qword ptr [rsp+0A8h+var_80], rax
0x1400679b1  jmp     loc_140067865
0x1400679b6  mov     dword ptr [rsp+0A8h+var_78], edi
0x1400679ba  mov     r8d, ebp
0x1400679bd  mov     qword ptr [rsp+0A8h+var_80], r15
0x1400679c2  mov     [rsp+0A8h+var_88], rax
0x1400679c7  jmp     loc_140067B91
0x1400679cc  mov     r8d, [rsp+0A8h+pcbBytesNeeded]; cbBufSize
0x1400679d1  lea     r9, [rsp+0A8h+var_64]; pcbBytesNeeded
0x1400679d6  mov     rdx, r13; lpServiceConfig
0x1400679d9  mov     rcx, r14; hService
0x1400679dc  call    cs:__imp_QueryServiceConfigW
0x1400679e2  test    eax, eax
0x1400679e4  jnz     loc_140067A73
0x1400679ea  call    cs:__imp_GetLastError
0x1400679f0  mov     edi, eax
0x1400679f2  test    eax, eax
0x1400679f4  jle     short loc_1400679FF
0x1400679f6  movzx   edi, ax
0x1400679f9  or      edi, 80070000h
0x1400679ff  mov     eax, 80004005h
0x140067a04  lea     rbp, aCbraex; "CBRAEx"
0x140067a0b  test    edi, edi
0x140067a0d  lea     rsi, aGetwindowsserv; "GetWindowsServiceInformation"
0x140067a14  lea     rbx, aTermsrvWmsSrcC_22; "termsrv\\wms\\src\\common\\srcutils\\sr"...
0x140067a1b  mov     r9, rbp; unsigned __int16 *
0x140067a1e  cmovns  edi, eax
0x140067a21  lea     r15, aFsuccess; "fSuccess"
0x140067a28  mov     [rsp+0A8h+var_80], edi; int
0x140067a2c  mov     r8, rsi; unsigned __int16 *
0x140067a2f  mov     edx, 9FBh; unsigned int
0x140067a34  mov     [rsp+0A8h+var_88], r15; unsigned __int16 *
0x140067a39  mov     rcx, rbx; unsigned __int16 *
0x140067a3c  call    ?LOGASSERTHR@@YAXPEBGK000J@Z; LOGASSERTHR(ushort const *,ulong,ushort const *,ushort const *,ushort const *,long)
0x140067a41  call    cs:__imp_IsDebuggerPresent
0x140067a47  test    eax, eax
0x140067a49  jz      short loc_140067A5F
0x140067a4b  mov     [rsp+0A8h+var_70], edi
0x140067a4f  mov     r9d, 9FBh
0x140067a55  mov     [rsp+0A8h+var_78], r15
0x140067a5a  jmp     loc_140067860
0x140067a5f  mov     dword ptr [rsp+0A8h+var_78], edi
0x140067a63  mov     r8d, 9FBh
0x140067a69  mov     qword ptr [rsp+0A8h+var_80], r15
0x140067a6e  jmp     loc_140067B8C
0x140067a73  mov     ebx, [r13+4]
0x140067a77  lea     rdx, [rsp+0A8h+ServiceStatus]; lpServiceStatus
0x140067a7c  mov     rcx, r14; hService
0x140067a7f  call    cs:__imp_QueryServiceStatus
0x140067a85  test    eax, eax
0x140067a87  jnz     loc_140067B13
0x140067a8d  call    cs:__imp_GetLastError
0x140067a93  mov     edi, eax
0x140067a95  test    eax, eax
0x140067a97  jle     short loc_140067AA2
0x140067a99  movzx   edi, ax
0x140067a9c  or      edi, 80070000h
0x140067aa2  mov     eax, 80004005h
0x140067aa7  lea     rbp, aCbraex; "CBRAEx"
0x140067aae  test    edi, edi
0x140067ab0  lea     rsi, aGetwindowsserv; "GetWindowsServiceInformation"
0x140067ab7  lea     rbx, aTermsrvWmsSrcC_22; "termsrv\\wms\\src\\common\\srcutils\\sr"...
0x140067abe  mov     r9, rbp; unsigned __int16 *
0x140067ac1  cmovns  edi, eax
0x140067ac4  lea     r15, aFsuccess; "fSuccess"
0x140067acb  mov     [rsp+0A8h+var_80], edi; int
0x140067acf  mov     r8, rsi; unsigned __int16 *
0x140067ad2  mov     edx, 0A00h; unsigned int
0x140067ad7  mov     [rsp+0A8h+var_88], r15; unsigned __int16 *
0x140067adc  mov     rcx, rbx; unsigned __int16 *
0x140067adf  call    ?LOGASSERTHR@@YAXPEBGK000J@Z; LOGASSERTHR(ushort const *,ulong,ushort const *,ushort const *,ushort const *,long)
0x140067ae4  call    cs:__imp_IsDebuggerPresent
0x140067aea  test    eax, eax
0x140067aec  jz      short loc_140067B02
0x140067aee  mov     [rsp+0A8h+var_70], edi
0x140067af2  mov     r9d, 0A00h
0x140067af8  mov     [rsp+0A8h+var_78], r15
0x140067afd  jmp     loc_140067860
0x140067b02  mov     dword ptr [rsp+0A8h+var_78], edi
0x140067b06  mov     r8d, 0A00h
0x140067b0c  mov     qword ptr [rsp+0A8h+var_80], r15
0x140067b11  jmp     short loc_140067B8C
0x140067b13  mov     eax, [rsp+0A8h+ServiceStatus.dwCurrentState]
0x140067b17  xor     edi, edi
0x140067b19  mov     [rsi], ebx
0x140067b1b  mov     [r15], eax
0x140067b1e  jmp     loc_140067BA3
0x140067b23  test    eax, eax
0x140067b25  jle     short loc_140067B30
0x140067b27  movzx   edi, ax
0x140067b2a  or      edi, 80070000h
0x140067b30  lea     rax, aFsuccess0Dwerr; "fSuccess == 0 && dwError == 122L"
0x140067b37  mov     [rsp+0A8h+var_80], edi; int
0x140067b3b  lea     rbp, aCbraex; "CBRAEx"
0x140067b42  mov     [rsp+0A8h+var_88], rax; unsigned __int16 *
0x140067b47  lea     rsi, aGetwindowsserv; "GetWindowsServiceInformation"
0x140067b4e  mov     r15d, 9F5h
0x140067b54  lea     rbx, aTermsrvWmsSrcC_22; "termsrv\\wms\\src\\common\\srcutils\\sr"...
0x140067b5b  mov     r9, rbp; unsigned __int16 *
0x140067b5e  mov     r8, rsi; unsigned __int16 *
0x140067b61  mov     edx, r15d; unsigned int
0x140067b64  mov     rcx, rbx; unsigned __int16 *
0x140067b67  call    ?LOGASSERTHR@@YAXPEBGK000J@Z; LOGASSERTHR(ushort const *,ulong,ushort const *,ushort const *,ushort const *,long)
0x140067b6c  call    cs:__imp_IsDebuggerPresent
0x140067b72  test    eax, eax
0x140067b74  lea     rax, aFsuccess0Dwerr; "fSuccess == 0 && dwError == 122L"
0x140067b7b  jmp     loc_14006784E
0x140067b80  mov     dword ptr [rsp+0A8h+var_78], edi
0x140067b84  mov     r8d, r15d
0x140067b87  mov     qword ptr [rsp+0A8h+var_80], rax
0x140067b8c  mov     [rsp+0A8h+var_88], rbp
0x140067b91  mov     r9, rsi
0x140067b94  lea     rcx, aAssertionFaile; "Assertion failed:  %s(%d) - %s - %s (%s"...
0x140067b9b  mov     rdx, rbx
0x140067b9e  call    ?DEBUGMSGBOX@@YAHPEBGZZ; DEBUGMSGBOX(ushort const *,...)
0x140067ba3  mov     rcx, r13; Block
0x140067ba6  call    ??3@YAXPEAX@Z; operator delete(void *)
0x140067bab  test    r14, r14
0x140067bae  jz      short loc_140067BB9
0x140067bb0  mov     rcx, r14; hSCObject
0x140067bb3  call    cs:__imp_CloseServiceHandle
0x140067bb9  test    r12, r12
0x140067bbc  jz      short loc_140067BC7
0x140067bbe  mov     rcx, r12; hSCObject
0x140067bc1  call    cs:__imp_CloseServiceHandle
0x140067bc7  mov     eax, edi
0x140067bc9  mov     rcx, [rsp+0A8h+var_40]
0x140067bce  xor     rcx, rsp; StackCookie
0x140067bd1  call    __security_check_cookie
0x140067bd6  mov     rbx, [rsp+0A8h+arg_18]
0x140067bde  add     rsp, 70h
0x140067be2  pop     r15
0x140067be4  pop     r14
0x140067be6  pop     r13
0x140067be8  pop     r12
0x140067bea  pop     rdi
0x140067beb  pop     rsi
0x140067bec  pop     rbp
0x140067bed  retn
```
