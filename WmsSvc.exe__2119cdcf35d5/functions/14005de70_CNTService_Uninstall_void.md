# CNTService::Uninstall(void)

- ea: `0x14005de70`
- end: `0x14005e53a`
- name: `?Uninstall@CNTService@@UEAAHXZ`
- size: `1738`
- prototype: `__int64 __fastcall(CNTService *__hidden this)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x140045fa0`

## callees

- `0x14002e718`
- `0x14005bc68`
- `0x14005bfec`
- `0x14005c408`
- `0x14005de70`
- `0x14007cbd0`

## import_xrefs

- `ADVAPI32!OpenSCManagerW` at `0x14005debc`
- `ADVAPI32!OpenSCManagerW` at `0x14005debc`
- `ADVAPI32!OpenServiceW` at `0x14005dfa7`
- `ADVAPI32!OpenServiceW` at `0x14005dfa7`
- `ADVAPI32!QueryServiceStatus` at `0x14005e00b`
- `ADVAPI32!QueryServiceStatus` at `0x14005e00b`
- `ADVAPI32!CloseServiceHandle` at `0x14005e0f7`
- `ADVAPI32!CloseServiceHandle` at `0x14005e4ef`
- `ADVAPI32!CloseServiceHandle` at `0x14005e4f8`
- `ADVAPI32!CloseServiceHandle` at `0x14005e0f7`
- `ADVAPI32!CloseServiceHandle` at `0x14005e4ef`
- `ADVAPI32!CloseServiceHandle` at `0x14005e4f8`
- `ADVAPI32!RegDeleteKeyW` at `0x14005e284`
- `ADVAPI32!RegDeleteKeyW` at `0x14005e3b3`
- `ADVAPI32!RegDeleteKeyW` at `0x14005e4df`
- `ADVAPI32!RegDeleteKeyW` at `0x14005e284`
- `ADVAPI32!RegDeleteKeyW` at `0x14005e3b3`
- `ADVAPI32!RegDeleteKeyW` at `0x14005e4df`
- `ADVAPI32!ControlService` at `0x14005dfcf`
- `ADVAPI32!ControlService` at `0x14005dfcf`
- `ADVAPI32!DeleteService` at `0x14005e018`
- `ADVAPI32!DeleteService` at `0x14005e018`
- `KERNEL32!Sleep` at `0x14005dfde`
- `KERNEL32!Sleep` at `0x14005dffa`
- `KERNEL32!Sleep` at `0x14005dfde`
- `KERNEL32!Sleep` at `0x14005dffa`
- `KERNEL32!GetLastError` at `0x14005ded6`
- `KERNEL32!GetLastError` at `0x14005e02a`
- `KERNEL32!GetLastError` at `0x14005ded6`
- `KERNEL32!GetLastError` at `0x14005e02a`
- `KERNEL32!IsDebuggerPresent` at `0x14005df31`
- `KERNEL32!IsDebuggerPresent` at `0x14005e081`
- `KERNEL32!IsDebuggerPresent` at `0x14005e19e`
- `KERNEL32!IsDebuggerPresent` at `0x14005e259`
- `KERNEL32!IsDebuggerPresent` at `0x14005e319`
- `KERNEL32!IsDebuggerPresent` at `0x14005e388`
- `KERNEL32!IsDebuggerPresent` at `0x14005e447`
- `KERNEL32!IsDebuggerPresent` at `0x14005e4b4`
- `KERNEL32!IsDebuggerPresent` at `0x14005df31`
- `KERNEL32!IsDebuggerPresent` at `0x14005e081`
- `KERNEL32!IsDebuggerPresent` at `0x14005e19e`
- `KERNEL32!IsDebuggerPresent` at `0x14005e259`
- `KERNEL32!IsDebuggerPresent` at `0x14005e319`
- `KERNEL32!IsDebuggerPresent` at `0x14005e388`
- `KERNEL32!IsDebuggerPresent` at `0x14005e447`
- `KERNEL32!IsDebuggerPresent` at `0x14005e4b4`

## string_xrefs

- `0x14005df06`: `termsrv\wms\src\common\ntservice\ntservice.cpp`
- `0x14005e054`: `termsrv\wms\src\common\ntservice\ntservice.cpp`
- `0x14005e17b`: `termsrv\wms\src\common\ntservice\ntservice.cpp`
- `0x14005e236`: `termsrv\wms\src\common\ntservice\ntservice.cpp`
- `0x14005e2f6`: `termsrv\wms\src\common\ntservice\ntservice.cpp`
- `0x14005e365`: `termsrv\wms\src\common\ntservice\ntservice.cpp`
- `0x14005e424`: `termsrv\wms\src\common\ntservice\ntservice.cpp`
- `0x14005e491`: `termsrv\wms\src\common\ntservice\ntservice.cpp`
- `0x14005def9`: `CNTService::Uninstall`
- `0x14005e04d`: `CNTService::Uninstall`
- `0x14005e171`: `CNTService::Uninstall`
- `0x14005e22c`: `CNTService::Uninstall`
- `0x14005e2ec`: `CNTService::Uninstall`
- `0x14005e35b`: `CNTService::Uninstall`
- `0x14005e41a`: `CNTService::Uninstall`
- `0x14005e487`: `CNTService::Uninstall`
- `0x14005e10c`: `SYSTEM\CurrentControlSet\Services\EventLog\Application\`

## pseudocode

```c
__int64 __fastcall CNTService::Uninstall(const WCHAR *this)
{
  SC_HANDLE v2; // rax
  SC_HANDLE v3; // r15
  signed int LastError; // eax
  signed int v5; // ebx
  const unsigned __int16 *v6; // rsi
  SC_HANDLE v7; // rax
  SC_HANDLE v8; // rbx
  unsigned int v9; // r12d
  int i; // edi
  signed int v11; // eax
  signed int v12; // ebx
  SC_HANDLE v13; // rcx
  __int64 v14; // rdi
  const wchar_t *v15; // rcx
  __int64 v16; // rax
  WCHAR *v17; // r8
  __int64 v18; // rdx
  WCHAR *v19; // rcx
  __int64 v20; // r9
  __int64 v21; // r8
  int v22; // eax
  __int64 v23; // rax
  const wchar_t *v24; // rcx
  __int64 v25; // rdx
  WCHAR *v26; // r8
  WCHAR *v27; // rcx
  int v28; // eax
  const wchar_t *v29; // rax
  __int64 v30; // rdx
  WCHAR *v31; // r8
  WCHAR *v32; // rcx
  int v33; // eax
  SC_HANDLE v35; // [rsp+40h] [rbp-C0h]
  BOOL v36; // [rsp+48h] [rbp-B8h]
  SC_HANDLE hSCObject; // [rsp+50h] [rbp-B0h]
  struct _SERVICE_STATUS ServiceStatus; // [rsp+58h] [rbp-A8h] BYREF
  WCHAR SubKey[512]; // [rsp+80h] [rbp-80h] BYREF

  memset(&ServiceStatus, 0, sizeof(ServiceStatus));
  v2 = OpenSCManagerW(0, 0, 0xF003Fu);
  v35 = v2;
  v3 = v2;
  if ( !v2 )
  {
    LastError = GetLastError();
    v5 = LastError;
    if ( LastError > 0 )
      v5 = (unsigned __int16)LastError | 0x80070000;
    if ( v5 >= 0 )
      v5 = -2147467259;
    LOGASSERTHR(
      L"termsrv\\wms\\src\\common\\ntservice\\ntservice.cpp",
      0x2ECu,
      L"CNTService::Uninstall",
      L"CBRAEx",
      L"hSCM != 0",
      v5);
    if ( IsDebuggerPresent() )
      DEBUGMSGLEVEL(
        2u,
        L"%s(%d) - %s - Assertion failed:  %s (%s)  hr = 0x%08X\n",
        L"termsrv\\wms\\src\\common\\ntservice\\ntservice.cpp",
        748,
        L"CNTService::Uninstall",
        L"CBRAEx",
        L"hSCM != 0",
        v5);
    else
      DEBUGMSGBOX(
        L"Assertion failed:  %s(%d) - %s - %s (%s)  hr = 0x%08X\n\n",
        L"termsrv\\wms\\src\\common\\ntservice\\ntservice.cpp",
        748,
        L"CNTService::Uninstall",
        L"CBRAEx",
        L"hSCM != 0",
        v5);
    return 0;
  }
  v6 = this + 4;
  v36 = 0;
  v7 = OpenServiceW(v2, this + 4, 0x10020u);
  hSCObject = v7;
  v8 = v7;
  v9 = 1;
  if ( v7 )
  {
    if ( ControlService(v7, 1u, &ServiceStatus) )
    {
      Sleep(0x3E8u);
      for ( i = 0; QueryServiceStatus(v8, &ServiceStatus) && i < 5 && ServiceStatus.dwCurrentState != 1; ++i )
        Sleep(0x3E8u);
    }
    v36 = DeleteService(v8);
    if ( !v36 )
    {
      v11 = GetLastError();
      v12 = v11;
      if ( v11 > 0 )
        v12 = (unsigned __int16)v11 | 0x80070000;
      if ( v12 >= 0 )
        v12 = -2147467259;
      LOGASSERTHR(
        L"termsrv\\wms\\src\\common\\ntservice\\ntservice.cpp",
        0x307u,
        L"CNTService::Uninstall",
        L"CBRAEx",
        L"fResult",
        v12);
      if ( IsDebuggerPresent() )
        DEBUGMSGLEVEL(
          2u,
          L"%s(%d) - %s - Assertion failed:  %s (%s)  hr = 0x%08X\n",
          L"termsrv\\wms\\src\\common\\ntservice\\ntservice.cpp",
          775,
          L"CNTService::Uninstall",
          L"CBRAEx",
          L"fResult",
          v12);
      else
        DEBUGMSGBOX(
          L"Assertion failed:  %s(%d) - %s - %s (%s)  hr = 0x%08X\n\n",
          L"termsrv\\wms\\src\\common\\ntservice\\ntservice.cpp",
          775,
          L"CNTService::Uninstall",
          L"CBRAEx",
          L"fResult",
          v12);
      v13 = hSCObject;
      goto LABEL_74;
    }
    CloseServiceHandle(v8);
    v36 = 1;
    hSCObject = 0;
  }
  v14 = 2147483646;
  v15 = L"SYSTEM\\CurrentControlSet\\Services\\EventLog\\Application\\";
  v16 = 2147483646;
  v17 = SubKey;
  v18 = 512;
  do
  {
    if ( !v16 )
      break;
    if ( !*v15 )
      break;
    *v17++ = *v15++;
    --v16;
    --v18;
  }
  while ( v18 );
  v19 = v17 - 1;
  v12 = v18 == 0 ? 0x8007007A : 0;
  if ( v18 )
    v19 = v17;
  *v19 = 0;
  if ( !v18 )
  {
    LOGASSERTHR(
      L"termsrv\\wms\\src\\common\\ntservice\\ntservice.cpp",
      0x312u,
      L"CNTService::Uninstall",
      L"CHRA",
      L"hr",
      -2147024774);
    if ( IsDebuggerPresent() )
    {
      v20 = 786;
LABEL_36:
      DEBUGMSGLEVEL(
        2u,
        L"%s(%d) - %s - Assertion failed:  %s (%s)  hr = 0x%08X\n",
        L"termsrv\\wms\\src\\common\\ntservice\\ntservice.cpp",
        v20,
        L"CNTService::Uninstall",
        L"CHRA",
        L"hr",
        v12);
LABEL_39:
      v3 = v35;
      goto LABEL_73;
    }
    v21 = 786;
    goto LABEL_38;
  }
  v22 = StringCchCatW(SubKey, 0x200u, v6);
  v12 = v22;
  if ( v22 < 0 )
  {
    LOGASSERTHR(
      L"termsrv\\wms\\src\\common\\ntservice\\ntservice.cpp",
      0x314u,
      L"CNTService::Uninstall",
      L"CHRA",
      L"hr",
      v22);
    if ( IsDebuggerPresent() )
    {
      v20 = 788;
      goto LABEL_36;
    }
    v21 = 788;
LABEL_38:
    DEBUGMSGBOX(
      L"Assertion failed:  %s(%d) - %s - %s (%s)  hr = 0x%08X\n\n",
      L"termsrv\\wms\\src\\common\\ntservice\\ntservice.cpp",
      v21,
      L"CNTService::Uninstall",
      L"CHRA",
      L"hr",
      v12);
    goto LABEL_39;
  }
  RegDeleteKeyW(HKEY_LOCAL_MACHINE, SubKey);
  v23 = 2147483646;
  v24 = L"SYSTEM\\CurrentControlSet\\Control\\Safeboot\\Network\\";
  v25 = 512;
  v26 = SubKey;
  do
  {
    if ( !v23 )
      break;
    if ( !*v24 )
      break;
    *v26++ = *v24++;
    --v23;
    --v25;
  }
  while ( v25 );
  v27 = v26 - 1;
  v12 = v25 == 0 ? 0x8007007A : 0;
  if ( v25 )
    v27 = v26;
  *v27 = 0;
  if ( !v25 )
  {
    LOGASSERTHR(
      L"termsrv\\wms\\src\\common\\ntservice\\ntservice.cpp",
      0x31Fu,
      L"CNTService::Uninstall",
      L"CHRA",
      L"hr",
      -2147024774);
    if ( IsDebuggerPresent() )
    {
      v20 = 799;
      goto LABEL_36;
    }
    v21 = 799;
    goto LABEL_38;
  }
  v28 = StringCchCatW(SubKey, 0x200u, v6);
  v12 = v28;
  if ( v28 < 0 )
  {
    LOGASSERTHR(
      L"termsrv\\wms\\src\\common\\ntservice\\ntservice.cpp",
      0x321u,
      L"CNTService::Uninstall",
      L"CHRA",
      L"hr",
      v28);
    if ( IsDebuggerPresent() )
    {
      v20 = 801;
      goto LABEL_36;
    }
    v21 = 801;
    goto LABEL_38;
  }
  RegDeleteKeyW(HKEY_LOCAL_MACHINE, SubKey);
  v29 = L"SYSTEM\\CurrentControlSet\\Control\\Safeboot\\Minimal\\";
  v30 = 512;
  v31 = SubKey;
  do
  {
    if ( !v14 )
      break;
    if ( !*v29 )
      break;
    *v31++ = *v29++;
    --v14;
    --v30;
  }
  while ( v30 );
  v32 = v31 - 1;
  v12 = v30 == 0 ? 0x8007007A : 0;
  if ( v30 )
    v32 = v31;
  *v32 = 0;
  if ( !v30 )
  {
    LOGASSERTHR(
      L"termsrv\\wms\\src\\common\\ntservice\\ntservice.cpp",
      0x328u,
      L"CNTService::Uninstall",
      L"CHRA",
      L"hr",
      -2147024774);
    if ( IsDebuggerPresent() )
    {
      v20 = 808;
      goto LABEL_36;
    }
    v21 = 808;
    goto LABEL_38;
  }
  v33 = StringCchCatW(SubKey, 0x200u, v6);
  v12 = v33;
  if ( v33 < 0 )
  {
    LOGASSERTHR(
      L"termsrv\\wms\\src\\common\\ntservice\\ntservice.cpp",
      0x32Au,
      L"CNTService::Uninstall",
      L"CHRA",
      L"hr",
      v33);
    if ( IsDebuggerPresent() )
    {
      v20 = 810;
      goto LABEL_36;
    }
    v21 = 810;
    goto LABEL_38;
  }
  RegDeleteKeyW(HKEY_LOCAL_MACHINE, SubKey);
LABEL_73:
  v13 = hSCObject;
  if ( hSCObject )
LABEL_74:
    CloseServiceHandle(v13);
  CloseServiceHandle(v3);
  if ( !v36 || v12 < 0 )
    return 0;
  return v9;
}

```

## disassembly

```asm
0x14005de70  mov     [rsp-8+arg_8], rbx
0x14005de75  mov     [rsp-8+arg_10], rsi
0x14005de7a  push    rbp
0x14005de7b  push    rdi
0x14005de7c  push    r12
0x14005de7e  push    r14
0x14005de80  push    r15
0x14005de82  lea     rbp, [rsp-390h]
0x14005de8a  sub     rsp, 490h
0x14005de91  mov     rax, cs:__security_cookie
0x14005de98  xor     rax, rsp
0x14005de9b  mov     [rbp+3B0h+var_30], rax
0x14005dea2  xorps   xmm0, xmm0
0x14005dea5  mov     rbx, rcx
0x14005dea8  movups  xmmword ptr [rsp+4B0h+ServiceStatus.dwServiceType], xmm0
0x14005dead  xor     edx, edx; lpDatabaseName
0x14005deaf  xor     ecx, ecx; lpMachineName
0x14005deb1  mov     r8d, 0F003Fh; dwDesiredAccess
0x14005deb7  movups  xmmword ptr [rsp+4B0h+ServiceStatus.dwWin32ExitCode], xmm0
0x14005debc  call    cs:__imp_OpenSCManagerW
0x14005dec2  xor     r14d, r14d
0x14005dec5  mov     [rsp+4B0h+var_470], rax
0x14005deca  mov     r15, rax
0x14005decd  test    rax, rax
0x14005ded0  jnz     loc_14005DF92
0x14005ded6  call    cs:__imp_GetLastError
0x14005dedc  mov     ebx, eax
0x14005dede  test    eax, eax
0x14005dee0  jle     short loc_14005DEEB
0x14005dee2  movzx   ebx, ax
0x14005dee5  or      ebx, 80070000h
0x14005deeb  mov     eax, 80004005h
0x14005def0  lea     r14, aCbraex; "CBRAEx"
0x14005def7  test    ebx, ebx
0x14005def9  lea     rsi, aCntserviceUnin; "CNTService::Uninstall"
0x14005df00  mov     r15d, 2ECh
0x14005df06  lea     rdi, aTermsrvWmsSrcC_23; "termsrv\\wms\\src\\common\\ntservice\\n"...
0x14005df0d  cmovns  ebx, eax
0x14005df10  lea     r12, aHscm0; "hSCM != 0"
0x14005df17  mov     [rsp+4B0h+var_488], ebx; int
0x14005df1b  mov     r9, r14; unsigned __int16 *
0x14005df1e  mov     r8, rsi; unsigned __int16 *
0x14005df21  mov     [rsp+4B0h+var_490], r12; unsigned __int16 *
0x14005df26  mov     edx, r15d; unsigned int
0x14005df29  mov     rcx, rdi; unsigned __int16 *
0x14005df2c  call    ?LOGASSERTHR@@YAXPEBGK000J@Z; LOGASSERTHR(ushort const *,ulong,ushort const *,ushort const *,ushort const *,long)
0x14005df31  call    cs:__imp_IsDebuggerPresent
0x14005df37  test    eax, eax
0x14005df39  jz      short loc_14005DF6D
0x14005df3b  mov     [rsp+4B0h+var_478], ebx
0x14005df3f  lea     rdx, aSDSAssertionFa_0; "%s(%d) - %s - Assertion failed:  %s (%s"...
0x14005df46  mov     [rsp+4B0h+var_480], r12
0x14005df4b  mov     r9d, r15d
0x14005df4e  mov     qword ptr [rsp+4B0h+var_488], r14
0x14005df53  mov     r8, rdi
0x14005df56  mov     ecx, 2; unsigned __int8
0x14005df5b  mov     [rsp+4B0h+var_490], rsi
0x14005df60  call    ?DEBUGMSGLEVEL@@YAXEPEBGZZ; DEBUGMSGLEVEL(uchar,ushort const *,...)
0x14005df65  xor     r14d, r14d
0x14005df68  jmp     loc_14005E509
0x14005df6d  mov     dword ptr [rsp+4B0h+var_480], ebx
0x14005df71  lea     rcx, aAssertionFaile; "Assertion failed:  %s(%d) - %s - %s (%s"...
0x14005df78  mov     qword ptr [rsp+4B0h+var_488], r12
0x14005df7d  mov     r9, rsi
0x14005df80  mov     r8d, r15d
0x14005df83  mov     [rsp+4B0h+var_490], r14
0x14005df88  mov     rdx, rdi
0x14005df8b  call    ?DEBUGMSGBOX@@YAHPEBGZZ; DEBUGMSGBOX(ushort const *,...)
0x14005df90  jmp     short loc_14005DF65
0x14005df92  lea     rsi, [rbx+8]
0x14005df96  mov     [rsp+4B0h+var_468], r14d
0x14005df9b  mov     rdx, rsi; lpServiceName
0x14005df9e  mov     r8d, 10020h; dwDesiredAccess
0x14005dfa4  mov     rcx, rax; hSCManager
0x14005dfa7  call    cs:__imp_OpenServiceW
0x14005dfad  mov     [rsp+4B0h+hSCObject], rax
0x14005dfb2  mov     rbx, rax
0x14005dfb5  mov     r12d, 1
0x14005dfbb  test    rax, rax
0x14005dfbe  jz      loc_14005E107
0x14005dfc4  lea     r8, [rsp+4B0h+ServiceStatus]; lpServiceStatus
0x14005dfc9  mov     edx, r12d; dwControl
0x14005dfcc  mov     rcx, rax; hService
0x14005dfcf  call    cs:__imp_ControlService
0x14005dfd5  test    eax, eax
0x14005dfd7  jz      short loc_14005E015
0x14005dfd9  mov     ecx, 3E8h; dwMilliseconds
0x14005dfde  call    cs:__imp_Sleep
0x14005dfe4  mov     edi, r14d
0x14005dfe7  jmp     short loc_14005E003
0x14005dfe9  cmp     edi, 5
0x14005dfec  jge     short loc_14005E015
0x14005dfee  cmp     [rsp+4B0h+ServiceStatus.dwCurrentState], r12d
0x14005dff3  jz      short loc_14005E015
0x14005dff5  mov     ecx, 3E8h; dwMilliseconds
0x14005dffa  call    cs:__imp_Sleep
0x14005e000  add     edi, r12d
0x14005e003  lea     rdx, [rsp+4B0h+ServiceStatus]; lpServiceStatus
0x14005e008  mov     rcx, rbx; hService
0x14005e00b  call    cs:__imp_QueryServiceStatus
0x14005e011  test    eax, eax
0x14005e013  jnz     short loc_14005DFE9
0x14005e015  mov     rcx, rbx; hService
0x14005e018  call    cs:__imp_DeleteService
0x14005e01e  mov     [rsp+4B0h+var_468], eax
0x14005e022  test    eax, eax
0x14005e024  jnz     loc_14005E0F4
0x14005e02a  call    cs:__imp_GetLastError
0x14005e030  mov     ebx, eax
0x14005e032  test    eax, eax
0x14005e034  jle     short loc_14005E03F
0x14005e036  movzx   ebx, ax
0x14005e039  or      ebx, 80070000h
0x14005e03f  mov     eax, 80004005h
0x14005e044  lea     r14, aCbraex; "CBRAEx"
0x14005e04b  test    ebx, ebx
0x14005e04d  lea     rsi, aCntserviceUnin; "CNTService::Uninstall"
0x14005e054  lea     rdi, aTermsrvWmsSrcC_23; "termsrv\\wms\\src\\common\\ntservice\\n"...
0x14005e05b  mov     r9, r14; unsigned __int16 *
0x14005e05e  cmovns  ebx, eax
0x14005e061  mov     r8, rsi; unsigned __int16 *
0x14005e064  lea     rax, aFresult; "fResult"
0x14005e06b  mov     [rsp+4B0h+var_488], ebx; int
0x14005e06f  mov     edx, 307h; unsigned int
0x14005e074  mov     [rsp+4B0h+var_490], rax; unsigned __int16 *
0x14005e079  mov     rcx, rdi; unsigned __int16 *
0x14005e07c  call    ?LOGASSERTHR@@YAXPEBGK000J@Z; LOGASSERTHR(ushort const *,ulong,ushort const *,ushort const *,ushort const *,long)
0x14005e081  call    cs:__imp_IsDebuggerPresent
0x14005e087  test    eax, eax
0x14005e089  lea     rax, aFresult; "fResult"
0x14005e090  jz      short loc_14005E0C1
0x14005e092  mov     [rsp+4B0h+var_478], ebx
0x14005e096  lea     rdx, aSDSAssertionFa_0; "%s(%d) - %s - Assertion failed:  %s (%s"...
0x14005e09d  mov     [rsp+4B0h+var_480], rax
0x14005e0a2  mov     r9d, 307h
0x14005e0a8  mov     qword ptr [rsp+4B0h+var_488], r14
0x14005e0ad  mov     r8, rdi
0x14005e0b0  mov     ecx, 2; unsigned __int8
0x14005e0b5  mov     [rsp+4B0h+var_490], rsi
0x14005e0ba  call    ?DEBUGMSGLEVEL@@YAXEPEBGZZ; DEBUGMSGLEVEL(uchar,ushort const *,...)
0x14005e0bf  jmp     short loc_14005E0E7
0x14005e0c1  mov     dword ptr [rsp+4B0h+var_480], ebx
0x14005e0c5  lea     rcx, aAssertionFaile; "Assertion failed:  %s(%d) - %s - %s (%s"...
0x14005e0cc  mov     qword ptr [rsp+4B0h+var_488], rax
0x14005e0d1  mov     r9, rsi
0x14005e0d4  mov     r8d, 307h
0x14005e0da  mov     [rsp+4B0h+var_490], r14
0x14005e0df  mov     rdx, rdi
0x14005e0e2  call    ?DEBUGMSGBOX@@YAHPEBGZZ; DEBUGMSGBOX(ushort const *,...)
0x14005e0e7  mov     rcx, [rsp+4B0h+hSCObject]
0x14005e0ec  xor     r14d, r14d
0x14005e0ef  jmp     loc_14005E4EF
0x14005e0f4  mov     rcx, rbx; hSCObject
0x14005e0f7  call    cs:__imp_CloseServiceHandle
0x14005e0fd  mov     [rsp+4B0h+var_468], r12d
0x14005e102  mov     [rsp+4B0h+hSCObject], r14
0x14005e107  mov     edi, 7FFFFFFEh
0x14005e10c  lea     rcx, aSystemCurrentc_7; "SYSTEM\\CurrentControlSet\\Services\\Ev"...
0x14005e113  mov     eax, edi
0x14005e115  lea     r8, [rbp+3B0h+SubKey]
0x14005e119  mov     edx, 200h
0x14005e11e  test    rax, rax
0x14005e121  jz      short loc_14005E141
0x14005e123  movzx   r9d, word ptr [rcx]
0x14005e127  test    r9w, r9w
0x14005e12b  jz      short loc_14005E141
0x14005e12d  mov     [r8], r9w
0x14005e131  add     rcx, 2
0x14005e135  add     r8, 2
0x14005e139  sub     rax, r12
0x14005e13c  sub     rdx, r12
0x14005e13f  jnz     short loc_14005E11E
0x14005e141  mov     rax, rdx
0x14005e144  lea     rcx, [r8-2]
0x14005e148  neg     rax
0x14005e14b  sbb     ebx, ebx
0x14005e14d  not     ebx
0x14005e14f  and     ebx, 8007007Ah
0x14005e155  test    rdx, rdx
0x14005e158  cmovnz  rcx, r8
0x14005e15c  mov     [rcx], r14w
0x14005e160  jnz     loc_14005E20A
0x14005e166  lea     r15, aChra; "CHRA"
0x14005e16d  mov     [rsp+4B0h+var_488], ebx; int
0x14005e171  lea     rsi, aCntserviceUnin; "CNTService::Uninstall"
0x14005e178  mov     r9, r15; unsigned __int16 *
0x14005e17b  lea     rdi, aTermsrvWmsSrcC_23; "termsrv\\wms\\src\\common\\ntservice\\n"...
0x14005e182  mov     r8, rsi; unsigned __int16 *
0x14005e185  lea     r14, aHr; "hr"
0x14005e18c  mov     rcx, rdi; unsigned __int16 *
0x14005e18f  mov     edx, 312h; unsigned int
0x14005e194  mov     [rsp+4B0h+var_490], r14; unsigned __int16 *
0x14005e199  call    ?LOGASSERTHR@@YAXPEBGK000J@Z; LOGASSERTHR(ushort const *,ulong,ushort const *,ushort const *,ushort const *,long)
0x14005e19e  call    cs:__imp_IsDebuggerPresent
0x14005e1a4  test    eax, eax
0x14005e1a6  jz      short loc_14005E1D7
0x14005e1a8  mov     r9d, 312h
0x14005e1ae  mov     [rsp+4B0h+var_478], ebx
0x14005e1b2  lea     rdx, aSDSAssertionFa_0; "%s(%d) - %s - Assertion failed:  %s (%s"...
0x14005e1b9  mov     [rsp+4B0h+var_480], r14
0x14005e1be  mov     r8, rdi
0x14005e1c1  mov     qword ptr [rsp+4B0h+var_488], r15
0x14005e1c6  mov     ecx, 2; unsigned __int8
0x14005e1cb  mov     [rsp+4B0h+var_490], rsi
0x14005e1d0  call    ?DEBUGMSGLEVEL@@YAXEPEBGZZ; DEBUGMSGLEVEL(uchar,ushort const *,...)
0x14005e1d5  jmp     short loc_14005E1FD
0x14005e1d7  mov     r8d, 312h
0x14005e1dd  mov     dword ptr [rsp+4B0h+var_480], ebx
0x14005e1e1  lea     rcx, aAssertionFaile; "Assertion failed:  %s(%d) - %s - %s (%s"...
0x14005e1e8  mov     qword ptr [rsp+4B0h+var_488], r14
0x14005e1ed  mov     r9, rsi
0x14005e1f0  mov     rdx, rdi
0x14005e1f3  mov     [rsp+4B0h+var_490], r15
0x14005e1f8  call    ?DEBUGMSGBOX@@YAHPEBGZZ; DEBUGMSGBOX(ushort const *,...)
0x14005e1fd  mov     r15, [rsp+4B0h+var_470]
0x14005e202  xor     r14d, r14d
0x14005e205  jmp     loc_14005E4E5
0x14005e20a  mov     r8, rsi; unsigned __int16 *
0x14005e20d  lea     rcx, [rbp+3B0h+SubKey]; unsigned __int16 *
0x14005e211  mov     edx, 200h; unsigned __int64
0x14005e216  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x14005e21b  mov     ebx, eax
0x14005e21d  test    eax, eax
0x14005e21f  jns     short loc_14005E279
0x14005e221  mov     [rsp+4B0h+var_488], eax; int
0x14005e225  lea     r15, aChra; "CHRA"
0x14005e22c  lea     rsi, aCntserviceUnin; "CNTService::Uninstall"
0x14005e233  mov     r9, r15; unsigned __int16 *
0x14005e236  lea     rdi, aTermsrvWmsSrcC_23; "termsrv\\wms\\src\\common\\ntservice\\n"...
0x14005e23d  mov     r8, rsi; unsigned __int16 *
0x14005e240  lea     r14, aHr; "hr"
0x14005e247  mov     rcx, rdi; unsigned __int16 *
0x14005e24a  mov     edx, 314h; unsigned int
0x14005e24f  mov     [rsp+4B0h+var_490], r14; unsigned __int16 *
0x14005e254  call    ?LOGASSERTHR@@YAXPEBGK000J@Z; LOGASSERTHR(ushort const *,ulong,ushort const *,ushort const *,ushort const *,long)
0x14005e259  call    cs:__imp_IsDebuggerPresent
0x14005e25f  test    eax, eax
0x14005e261  jz      short loc_14005E26E
0x14005e263  mov     r9d, 314h
0x14005e269  jmp     loc_14005E1AE
0x14005e26e  mov     r8d, 314h
0x14005e274  jmp     loc_14005E1DD
0x14005e279  lea     rdx, [rbp+3B0h+SubKey]; lpSubKey
0x14005e27d  mov     rcx, 0FFFFFFFF80000002h; hKey
0x14005e284  call    cs:__imp_RegDeleteKeyW
0x14005e28a  mov     rax, rdi
0x14005e28d  lea     rcx, aSystemCurrentc_1; "SYSTEM\\CurrentControlSet\\Control\\Saf"...
0x14005e294  mov     edx, 200h
0x14005e299  lea     r8, [rbp+3B0h+SubKey]
0x14005e29d  test    rax, rax
0x14005e2a0  jz      short loc_14005E2C0
0x14005e2a2  movzx   r9d, word ptr [rcx]
0x14005e2a6  test    r9w, r9w
0x14005e2aa  jz      short loc_14005E2C0
0x14005e2ac  mov     [r8], r9w
0x14005e2b0  add     rcx, 2
0x14005e2b4  add     r8, 2
0x14005e2b8  sub     rax, r12
0x14005e2bb  sub     rdx, r12
0x14005e2be  jnz     short loc_14005E29D
0x14005e2c0  mov     rax, rdx
0x14005e2c3  lea     rcx, [r8-2]
0x14005e2c7  neg     rax
0x14005e2ca  sbb     ebx, ebx
0x14005e2cc  not     ebx
0x14005e2ce  and     ebx, 8007007Ah
0x14005e2d4  test    rdx, rdx
0x14005e2d7  cmovnz  rcx, r8
0x14005e2db  mov     [rcx], r14w
0x14005e2df  jnz     short loc_14005E339
0x14005e2e1  lea     r15, aChra; "CHRA"
0x14005e2e8  mov     [rsp+4B0h+var_488], ebx; int
0x14005e2ec  lea     rsi, aCntserviceUnin; "CNTService::Uninstall"
0x14005e2f3  mov     r9, r15; unsigned __int16 *
0x14005e2f6  lea     rdi, aTermsrvWmsSrcC_23; "termsrv\\wms\\src\\common\\ntservice\\n"...
0x14005e2fd  mov     r8, rsi; unsigned __int16 *
0x14005e300  lea     r14, aHr; "hr"
0x14005e307  mov     rcx, rdi; unsigned __int16 *
0x14005e30a  mov     edx, 31Fh; unsigned int
0x14005e30f  mov     [rsp+4B0h+var_490], r14; unsigned __int16 *
0x14005e314  call    ?LOGASSERTHR@@YAXPEBGK000J@Z; LOGASSERTHR(ushort const *,ulong,ushort const *,ushort const *,ushort const *,long)
0x14005e319  call    cs:__imp_IsDebuggerPresent
0x14005e31f  test    eax, eax
0x14005e321  jz      short loc_14005E32E
0x14005e323  mov     r9d, 31Fh
0x14005e329  jmp     loc_14005E1AE
0x14005e32e  mov     r8d, 31Fh
0x14005e334  jmp     loc_14005E1DD
0x14005e339  mov     r8, rsi; unsigned __int16 *
0x14005e33c  lea     rcx, [rbp+3B0h+SubKey]; unsigned __int16 *
0x14005e340  mov     edx, 200h; unsigned __int64
0x14005e345  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x14005e34a  mov     ebx, eax
0x14005e34c  test    eax, eax
0x14005e34e  jns     short loc_14005E3A8
0x14005e350  mov     [rsp+4B0h+var_488], eax; int
0x14005e354  lea     r15, aChra; "CHRA"
0x14005e35b  lea     rsi, aCntserviceUnin; "CNTService::Uninstall"
0x14005e362  mov     r9, r15; unsigned __int16 *
0x14005e365  lea     rdi, aTermsrvWmsSrcC_23; "termsrv\\wms\\src\\common\\ntservice\\n"...
  ... truncated ...
```
