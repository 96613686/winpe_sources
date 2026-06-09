# CNTService::Uninstall(void)

- ea: `0x140005bc0`
- end: `0x140006269`
- name: `?Uninstall@CNTService@@UEAAHXZ`
- size: `1705`
- prototype: `__int64 __fastcall(const WCHAR *this)`
- caller_count: `0`
- callee_count: `6`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callees

- `0x1400036d8`
- `0x140003918`
- `0x140003c2c`
- `0x140005a98`
- `0x140005bc0`
- `0x14000ae60`

## import_xrefs

- `ADVAPI32!RegDeleteKeyW` at `0x140005fca`
- `ADVAPI32!RegDeleteKeyW` at `0x1400060f3`
- `ADVAPI32!RegDeleteKeyW` at `0x140006213`
- `ADVAPI32!RegDeleteKeyW` at `0x140005fca`
- `ADVAPI32!RegDeleteKeyW` at `0x1400060f3`
- `ADVAPI32!RegDeleteKeyW` at `0x140006213`
- `ADVAPI32!DeleteService` at `0x140005d62`
- `ADVAPI32!DeleteService` at `0x140005d62`
- `ADVAPI32!QueryServiceStatus` at `0x140005d55`
- `ADVAPI32!QueryServiceStatus` at `0x140005d55`
- `ADVAPI32!ControlService` at `0x140005d1a`
- `ADVAPI32!ControlService` at `0x140005d1a`
- `ADVAPI32!OpenServiceW` at `0x140005cf2`
- `ADVAPI32!OpenServiceW` at `0x140005cf2`
- `ADVAPI32!CloseServiceHandle` at `0x140005e3e`
- `ADVAPI32!CloseServiceHandle` at `0x140006226`
- `ADVAPI32!CloseServiceHandle` at `0x14000622f`
- `ADVAPI32!CloseServiceHandle` at `0x140005e3e`
- `ADVAPI32!CloseServiceHandle` at `0x140006226`
- `ADVAPI32!CloseServiceHandle` at `0x14000622f`
- `ADVAPI32!OpenSCManagerW` at `0x140005c07`
- `ADVAPI32!OpenSCManagerW` at `0x140005c07`
- `KERNEL32!IsDebuggerPresent` at `0x140005c7c`
- `KERNEL32!IsDebuggerPresent` at `0x140005dcb`
- `KERNEL32!IsDebuggerPresent` at `0x140005eee`
- `KERNEL32!IsDebuggerPresent` at `0x140005f9f`
- `KERNEL32!IsDebuggerPresent` at `0x14000605e`
- `KERNEL32!IsDebuggerPresent` at `0x1400060c8`
- `KERNEL32!IsDebuggerPresent` at `0x14000617e`
- `KERNEL32!IsDebuggerPresent` at `0x1400061e8`
- `KERNEL32!IsDebuggerPresent` at `0x140005c7c`
- `KERNEL32!IsDebuggerPresent` at `0x140005dcb`
- `KERNEL32!IsDebuggerPresent` at `0x140005eee`
- `KERNEL32!IsDebuggerPresent` at `0x140005f9f`
- `KERNEL32!IsDebuggerPresent` at `0x14000605e`
- `KERNEL32!IsDebuggerPresent` at `0x1400060c8`
- `KERNEL32!IsDebuggerPresent` at `0x14000617e`
- `KERNEL32!IsDebuggerPresent` at `0x1400061e8`
- `KERNEL32!GetLastError` at `0x140005c21`
- `KERNEL32!GetLastError` at `0x140005d74`
- `KERNEL32!GetLastError` at `0x140005c21`
- `KERNEL32!GetLastError` at `0x140005d74`
- `KERNEL32!Sleep` at `0x140005d2b`
- `KERNEL32!Sleep` at `0x140005d44`
- `KERNEL32!Sleep` at `0x140005d2b`
- `KERNEL32!Sleep` at `0x140005d44`

## string_xrefs

- `0x140005c51`: `termsrv\wms\src\common\ntservice\ntservice.cpp`
- `0x140005d9e`: `termsrv\wms\src\common\ntservice\ntservice.cpp`
- `0x140005ecb`: `termsrv\wms\src\common\ntservice\ntservice.cpp`
- `0x140005f7c`: `termsrv\wms\src\common\ntservice\ntservice.cpp`
- `0x14000603b`: `termsrv\wms\src\common\ntservice\ntservice.cpp`
- `0x1400060a5`: `termsrv\wms\src\common\ntservice\ntservice.cpp`
- `0x14000615b`: `termsrv\wms\src\common\ntservice\ntservice.cpp`
- `0x1400061c5`: `termsrv\wms\src\common\ntservice\ntservice.cpp`
- `0x140005c44`: `CNTService::Uninstall`
- `0x140005d97`: `CNTService::Uninstall`
- `0x140005ec1`: `CNTService::Uninstall`
- `0x140005f72`: `CNTService::Uninstall`
- `0x140006031`: `CNTService::Uninstall`
- `0x14000609b`: `CNTService::Uninstall`
- `0x140006151`: `CNTService::Uninstall`
- `0x1400061bb`: `CNTService::Uninstall`
- `0x140005e53`: `SYSTEM\CurrentControlSet\Services\EventLog\Application\`

## pseudocode

```c
__int64 __fastcall CNTService::Uninstall(const WCHAR *this)
{
  SC_HANDLE v2; // rax
  SC_HANDLE v3; // r15
  signed int LastError; // eax
  signed int v5; // ebx
  const unsigned __int16 *v6; // r14
  SC_HANDLE v7; // rax
  SC_HANDLE v8; // rbx
  unsigned int v9; // r12d
  int i; // edi
  signed int v11; // eax
  signed int v12; // ebx
  SC_HANDLE v13; // rcx
  __int64 v14; // rsi
  const wchar_t *v15; // rcx
  __int64 v16; // rdi
  WCHAR *v17; // r8
  __int64 v18; // rax
  unsigned __int64 v19; // rdx
  WCHAR *v20; // rcx
  __int64 v21; // r9
  __int64 v22; // r8
  int v23; // eax
  __int64 v24; // rax
  const wchar_t *v25; // rcx
  unsigned __int64 v26; // rdx
  WCHAR *v27; // r8
  WCHAR *v28; // rcx
  int v29; // eax
  const wchar_t *v30; // rax
  WCHAR *v31; // rdx
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
      goto LABEL_73;
    }
    CloseServiceHandle(v8);
    v36 = 1;
    hSCObject = 0;
  }
  v14 = 2147483646;
  v15 = L"SYSTEM\\CurrentControlSet\\Services\\EventLog\\Application\\";
  v16 = 512;
  v17 = SubKey;
  v18 = 2147483646;
  v19 = 512;
  do
  {
    if ( !v18 )
      break;
    if ( !*v15 )
      break;
    *v17++ = *v15++;
    --v18;
    --v19;
  }
  while ( v19 );
  v20 = v17 - 1;
  v12 = v19 == 0 ? 0x8007007A : 0;
  if ( v19 )
    v20 = v17;
  *v20 = 0;
  if ( !v19 )
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
      v21 = 786;
LABEL_35:
      DEBUGMSGLEVEL(
        2u,
        L"%s(%d) - %s - Assertion failed:  %s (%s)  hr = 0x%08X\n",
        L"termsrv\\wms\\src\\common\\ntservice\\ntservice.cpp",
        v21,
        L"CNTService::Uninstall",
        L"CHRA",
        L"hr",
        v12);
LABEL_38:
      v3 = v35;
      goto LABEL_72;
    }
    v22 = 786;
    goto LABEL_37;
  }
  v23 = StringCchCatW(SubKey, v19, v6);
  v12 = v23;
  if ( v23 < 0 )
  {
    LOGASSERTHR(
      L"termsrv\\wms\\src\\common\\ntservice\\ntservice.cpp",
      0x314u,
      L"CNTService::Uninstall",
      L"CHRA",
      L"hr",
      v23);
    if ( IsDebuggerPresent() )
    {
      v21 = 788;
      goto LABEL_35;
    }
    v22 = 788;
LABEL_37:
    DEBUGMSGBOX(
      L"Assertion failed:  %s(%d) - %s - %s (%s)  hr = 0x%08X\n\n",
      L"termsrv\\wms\\src\\common\\ntservice\\ntservice.cpp",
      v22,
      L"CNTService::Uninstall",
      L"CHRA",
      L"hr",
      v12);
    goto LABEL_38;
  }
  RegDeleteKeyW(HKEY_LOCAL_MACHINE, SubKey);
  v24 = 2147483646;
  v25 = L"SYSTEM\\CurrentControlSet\\Control\\Safeboot\\Network\\";
  v26 = 512;
  v27 = SubKey;
  do
  {
    if ( !v24 )
      break;
    if ( !*v25 )
      break;
    *v27++ = *v25++;
    --v24;
    --v26;
  }
  while ( v26 );
  v28 = v27 - 1;
  v12 = v26 == 0 ? 0x8007007A : 0;
  if ( v26 )
    v28 = v27;
  *v28 = 0;
  if ( !v26 )
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
      v21 = 799;
      goto LABEL_35;
    }
    v22 = 799;
    goto LABEL_37;
  }
  v29 = StringCchCatW(SubKey, v26, v6);
  v12 = v29;
  if ( v29 < 0 )
  {
    LOGASSERTHR(
      L"termsrv\\wms\\src\\common\\ntservice\\ntservice.cpp",
      0x321u,
      L"CNTService::Uninstall",
      L"CHRA",
      L"hr",
      v29);
    if ( IsDebuggerPresent() )
    {
      v21 = 801;
      goto LABEL_35;
    }
    v22 = 801;
    goto LABEL_37;
  }
  RegDeleteKeyW(HKEY_LOCAL_MACHINE, SubKey);
  v30 = L"SYSTEM\\CurrentControlSet\\Control\\Safeboot\\Minimal\\";
  v31 = SubKey;
  do
  {
    if ( !v14 )
      break;
    if ( !*v30 )
      break;
    *v31++ = *v30++;
    --v14;
    --v16;
  }
  while ( v16 );
  v32 = v31 - 1;
  v12 = v16 == 0 ? 0x8007007A : 0;
  if ( v16 )
    v32 = v31;
  *v32 = 0;
  if ( !v16 )
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
      v21 = 808;
      goto LABEL_35;
    }
    v22 = 808;
    goto LABEL_37;
  }
  v33 = StringCchCatW(SubKey, (unsigned __int64)v31, v6);
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
      v21 = 810;
      goto LABEL_35;
    }
    v22 = 810;
    goto LABEL_37;
  }
  RegDeleteKeyW(HKEY_LOCAL_MACHINE, SubKey);
LABEL_72:
  v13 = hSCObject;
  if ( hSCObject )
LABEL_73:
    CloseServiceHandle(v13);
  CloseServiceHandle(v3);
  if ( !v36 || v12 < 0 )
    return 0;
  return v9;
}

```

## disassembly

```asm
0x140005bc0  push    rbp
0x140005bc2  push    rbx
0x140005bc3  push    rsi
0x140005bc4  push    rdi
0x140005bc5  push    r12
0x140005bc7  push    r13
0x140005bc9  push    r14
0x140005bcb  push    r15
0x140005bcd  lea     rbp, [rsp-398h]
0x140005bd5  sub     rsp, 498h
0x140005bdc  mov     rax, cs:__security_cookie
0x140005be3  xor     rax, rsp
0x140005be6  mov     [rbp+3D0h+var_50], rax
0x140005bed  xorps   xmm0, xmm0
0x140005bf0  mov     rbx, rcx
0x140005bf3  movups  xmmword ptr [rsp+4D0h+ServiceStatus.dwServiceType], xmm0
0x140005bf8  xor     edx, edx; lpDatabaseName
0x140005bfa  xor     ecx, ecx; lpMachineName
0x140005bfc  mov     r8d, 0F003Fh; dwDesiredAccess
0x140005c02  movups  xmmword ptr [rsp+4D0h+ServiceStatus.dwWin32ExitCode], xmm0
0x140005c07  call    cs:__imp_OpenSCManagerW
0x140005c0d  xor     r13d, r13d
0x140005c10  mov     [rsp+4D0h+var_490], rax
0x140005c15  mov     r15, rax
0x140005c18  test    rax, rax
0x140005c1b  jnz     loc_140005CDD
0x140005c21  call    cs:__imp_GetLastError
0x140005c27  mov     ebx, eax
0x140005c29  test    eax, eax
0x140005c2b  jle     short loc_140005C36
0x140005c2d  movzx   ebx, ax
0x140005c30  or      ebx, 80070000h
0x140005c36  mov     eax, 80004005h
0x140005c3b  lea     r14, aCbraex; "CBRAEx"
0x140005c42  test    ebx, ebx
0x140005c44  lea     rsi, aCntserviceUnin; "CNTService::Uninstall"
0x140005c4b  mov     r15d, 2ECh
0x140005c51  lea     rdi, aTermsrvWmsSrcC_5; "termsrv\\wms\\src\\common\\ntservice\\n"...
0x140005c58  cmovns  ebx, eax
0x140005c5b  lea     r12, aHscm0; "hSCM != 0"
0x140005c62  mov     [rsp+4D0h+var_4A8], ebx; int
0x140005c66  mov     r9, r14; unsigned __int16 *
0x140005c69  mov     r8, rsi; unsigned __int16 *
0x140005c6c  mov     [rsp+4D0h+var_4B0], r12; unsigned __int16 *
0x140005c71  mov     edx, r15d; unsigned int
0x140005c74  mov     rcx, rdi; unsigned __int16 *
0x140005c77  call    ?LOGASSERTHR@@YAXPEBGK000J@Z; LOGASSERTHR(ushort const *,ulong,ushort const *,ushort const *,ushort const *,long)
0x140005c7c  call    cs:__imp_IsDebuggerPresent
0x140005c82  test    eax, eax
0x140005c84  jz      short loc_140005CB5
0x140005c86  mov     [rsp+4D0h+var_498], ebx
0x140005c8a  lea     rdx, aSDSAssertionFa_0; "%s(%d) - %s - Assertion failed:  %s (%s"...
0x140005c91  mov     [rsp+4D0h+var_4A0], r12
0x140005c96  mov     r9d, r15d
0x140005c99  mov     qword ptr [rsp+4D0h+var_4A8], r14
0x140005c9e  mov     r8, rdi
0x140005ca1  mov     ecx, 2; unsigned __int8
0x140005ca6  mov     [rsp+4D0h+var_4B0], rsi
0x140005cab  call    ?DEBUGMSGLEVEL@@YAXEPEBGZZ; DEBUGMSGLEVEL(uchar,ushort const *,...)
0x140005cb0  jmp     loc_140006240
0x140005cb5  mov     dword ptr [rsp+4D0h+var_4A0], ebx
0x140005cb9  lea     rcx, aAssertionFaile; "Assertion failed:  %s(%d) - %s - %s (%s"...
0x140005cc0  mov     qword ptr [rsp+4D0h+var_4A8], r12
0x140005cc5  mov     r9, rsi
0x140005cc8  mov     r8d, r15d
0x140005ccb  mov     [rsp+4D0h+var_4B0], r14
0x140005cd0  mov     rdx, rdi
0x140005cd3  call    ?DEBUGMSGBOX@@YAHPEBGZZ; DEBUGMSGBOX(ushort const *,...)
0x140005cd8  jmp     loc_140006240
0x140005cdd  lea     r14, [rbx+8]
0x140005ce1  mov     [rsp+4D0h+var_488], r13d
0x140005ce6  mov     rdx, r14; lpServiceName
0x140005ce9  mov     r8d, 10020h; dwDesiredAccess
0x140005cef  mov     rcx, rax; hSCManager
0x140005cf2  call    cs:__imp_OpenServiceW
0x140005cf8  mov     [rsp+4D0h+hSCObject], rax
0x140005cfd  mov     rbx, rax
0x140005d00  mov     r12d, 1
0x140005d06  test    rax, rax
0x140005d09  jz      loc_140005E4E
0x140005d0f  lea     r8, [rsp+4D0h+ServiceStatus]; lpServiceStatus
0x140005d14  mov     edx, r12d; dwControl
0x140005d17  mov     rcx, rax; hService
0x140005d1a  call    cs:__imp_ControlService
0x140005d20  test    eax, eax
0x140005d22  jz      short loc_140005D5F
0x140005d24  mov     esi, 3E8h
0x140005d29  mov     ecx, esi; dwMilliseconds
0x140005d2b  call    cs:__imp_Sleep
0x140005d31  mov     edi, r13d
0x140005d34  jmp     short loc_140005D4D
0x140005d36  cmp     edi, 5
0x140005d39  jge     short loc_140005D5F
0x140005d3b  cmp     [rsp+4D0h+ServiceStatus.dwCurrentState], r12d
0x140005d40  jz      short loc_140005D5F
0x140005d42  mov     ecx, esi; dwMilliseconds
0x140005d44  call    cs:__imp_Sleep
0x140005d4a  add     edi, r12d
0x140005d4d  lea     rdx, [rsp+4D0h+ServiceStatus]; lpServiceStatus
0x140005d52  mov     rcx, rbx; hService
0x140005d55  call    cs:__imp_QueryServiceStatus
0x140005d5b  test    eax, eax
0x140005d5d  jnz     short loc_140005D36
0x140005d5f  mov     rcx, rbx; hService
0x140005d62  call    cs:__imp_DeleteService
0x140005d68  mov     [rsp+4D0h+var_488], eax
0x140005d6c  test    eax, eax
0x140005d6e  jnz     loc_140005E3B
0x140005d74  call    cs:__imp_GetLastError
0x140005d7a  mov     ebx, eax
0x140005d7c  test    eax, eax
0x140005d7e  jle     short loc_140005D89
0x140005d80  movzx   ebx, ax
0x140005d83  or      ebx, 80070000h
0x140005d89  mov     eax, 80004005h
0x140005d8e  lea     r14, aCbraex; "CBRAEx"
0x140005d95  test    ebx, ebx
0x140005d97  lea     rsi, aCntserviceUnin; "CNTService::Uninstall"
0x140005d9e  lea     rdi, aTermsrvWmsSrcC_5; "termsrv\\wms\\src\\common\\ntservice\\n"...
0x140005da5  mov     r9, r14; unsigned __int16 *
0x140005da8  cmovns  ebx, eax
0x140005dab  mov     r8, rsi; unsigned __int16 *
0x140005dae  lea     rax, aFresult; "fResult"
0x140005db5  mov     [rsp+4D0h+var_4A8], ebx; int
0x140005db9  mov     edx, 307h; unsigned int
0x140005dbe  mov     [rsp+4D0h+var_4B0], rax; unsigned __int16 *
0x140005dc3  mov     rcx, rdi; unsigned __int16 *
0x140005dc6  call    ?LOGASSERTHR@@YAXPEBGK000J@Z; LOGASSERTHR(ushort const *,ulong,ushort const *,ushort const *,ushort const *,long)
0x140005dcb  call    cs:__imp_IsDebuggerPresent
0x140005dd1  test    eax, eax
0x140005dd3  lea     rax, aFresult; "fResult"
0x140005dda  jz      short loc_140005E0B
0x140005ddc  mov     [rsp+4D0h+var_498], ebx
0x140005de0  lea     rdx, aSDSAssertionFa_0; "%s(%d) - %s - Assertion failed:  %s (%s"...
0x140005de7  mov     [rsp+4D0h+var_4A0], rax
0x140005dec  mov     r9d, 307h
0x140005df2  mov     qword ptr [rsp+4D0h+var_4A8], r14
0x140005df7  mov     r8, rdi
0x140005dfa  mov     ecx, 2; unsigned __int8
0x140005dff  mov     [rsp+4D0h+var_4B0], rsi
0x140005e04  call    ?DEBUGMSGLEVEL@@YAXEPEBGZZ; DEBUGMSGLEVEL(uchar,ushort const *,...)
0x140005e09  jmp     short loc_140005E31
0x140005e0b  mov     dword ptr [rsp+4D0h+var_4A0], ebx
0x140005e0f  lea     rcx, aAssertionFaile; "Assertion failed:  %s(%d) - %s - %s (%s"...
0x140005e16  mov     qword ptr [rsp+4D0h+var_4A8], rax
0x140005e1b  mov     r9, rsi
0x140005e1e  mov     r8d, 307h
0x140005e24  mov     [rsp+4D0h+var_4B0], r14
0x140005e29  mov     rdx, rdi
0x140005e2c  call    ?DEBUGMSGBOX@@YAHPEBGZZ; DEBUGMSGBOX(ushort const *,...)
0x140005e31  mov     rcx, [rsp+4D0h+hSCObject]
0x140005e36  jmp     loc_140006226
0x140005e3b  mov     rcx, rbx; hSCObject
0x140005e3e  call    cs:__imp_CloseServiceHandle
0x140005e44  mov     [rsp+4D0h+var_488], r12d
0x140005e49  mov     [rsp+4D0h+hSCObject], r13
0x140005e4e  mov     esi, 7FFFFFFEh
0x140005e53  lea     rcx, aSystemCurrentc_3; "SYSTEM\\CurrentControlSet\\Services\\Ev"...
0x140005e5a  mov     edi, 200h
0x140005e5f  lea     r8, [rbp+3D0h+SubKey]
0x140005e63  mov     eax, esi
0x140005e65  mov     edx, edi
0x140005e67  mov     r13d, 2
0x140005e6d  xor     r10d, r10d
0x140005e70  test    rax, rax
0x140005e73  jz      short loc_140005E91
0x140005e75  movzx   r9d, word ptr [rcx]
0x140005e79  test    r9w, r9w
0x140005e7d  jz      short loc_140005E91
0x140005e7f  mov     [r8], r9w
0x140005e83  add     rcx, r13
0x140005e86  add     r8, r13
0x140005e89  sub     rax, r12
0x140005e8c  sub     rdx, r12; unsigned __int64
0x140005e8f  jnz     short loc_140005E70
0x140005e91  mov     rax, rdx
0x140005e94  lea     rcx, [r8-2]
0x140005e98  neg     rax
0x140005e9b  sbb     ebx, ebx
0x140005e9d  not     ebx
0x140005e9f  and     ebx, 8007007Ah
0x140005ea5  test    rdx, rdx
0x140005ea8  cmovnz  rcx, r8
0x140005eac  mov     [rcx], r10w
0x140005eb0  jnz     loc_140005F55
0x140005eb6  lea     r15, aChra; "CHRA"
0x140005ebd  mov     [rsp+4D0h+var_4A8], ebx; int
0x140005ec1  lea     rsi, aCntserviceUnin; "CNTService::Uninstall"
0x140005ec8  mov     r9, r15; unsigned __int16 *
0x140005ecb  lea     rdi, aTermsrvWmsSrcC_5; "termsrv\\wms\\src\\common\\ntservice\\n"...
0x140005ed2  mov     r8, rsi; unsigned __int16 *
0x140005ed5  lea     r14, aHr; "hr"
0x140005edc  mov     rcx, rdi; unsigned __int16 *
0x140005edf  mov     edx, 312h; unsigned int
0x140005ee4  mov     [rsp+4D0h+var_4B0], r14; unsigned __int16 *
0x140005ee9  call    ?LOGASSERTHR@@YAXPEBGK000J@Z; LOGASSERTHR(ushort const *,ulong,ushort const *,ushort const *,ushort const *,long)
0x140005eee  call    cs:__imp_IsDebuggerPresent
0x140005ef4  test    eax, eax
0x140005ef6  jz      short loc_140005F25
0x140005ef8  mov     r9d, 312h
0x140005efe  mov     [rsp+4D0h+var_498], ebx
0x140005f02  lea     rdx, aSDSAssertionFa_0; "%s(%d) - %s - Assertion failed:  %s (%s"...
0x140005f09  mov     [rsp+4D0h+var_4A0], r14
0x140005f0e  mov     r8, rdi
0x140005f11  mov     qword ptr [rsp+4D0h+var_4A8], r15
0x140005f16  mov     ecx, r13d; unsigned __int8
0x140005f19  mov     [rsp+4D0h+var_4B0], rsi
0x140005f1e  call    ?DEBUGMSGLEVEL@@YAXEPEBGZZ; DEBUGMSGLEVEL(uchar,ushort const *,...)
0x140005f23  jmp     short loc_140005F4B
0x140005f25  mov     r8d, 312h
0x140005f2b  mov     dword ptr [rsp+4D0h+var_4A0], ebx
0x140005f2f  lea     rcx, aAssertionFaile; "Assertion failed:  %s(%d) - %s - %s (%s"...
0x140005f36  mov     qword ptr [rsp+4D0h+var_4A8], r14
0x140005f3b  mov     r9, rsi
0x140005f3e  mov     rdx, rdi
0x140005f41  mov     [rsp+4D0h+var_4B0], r15
0x140005f46  call    ?DEBUGMSGBOX@@YAHPEBGZZ; DEBUGMSGBOX(ushort const *,...)
0x140005f4b  mov     r15, [rsp+4D0h+var_490]
0x140005f50  jmp     loc_140006219
0x140005f55  mov     r8, r14; unsigned __int16 *
0x140005f58  lea     rcx, [rbp+3D0h+SubKey]; unsigned __int16 *
0x140005f5c  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x140005f61  mov     ebx, eax
0x140005f63  test    eax, eax
0x140005f65  jns     short loc_140005FBF
0x140005f67  mov     [rsp+4D0h+var_4A8], eax; int
0x140005f6b  lea     r15, aChra; "CHRA"
0x140005f72  lea     rsi, aCntserviceUnin; "CNTService::Uninstall"
0x140005f79  mov     r9, r15; unsigned __int16 *
0x140005f7c  lea     rdi, aTermsrvWmsSrcC_5; "termsrv\\wms\\src\\common\\ntservice\\n"...
0x140005f83  mov     r8, rsi; unsigned __int16 *
0x140005f86  lea     r14, aHr; "hr"
0x140005f8d  mov     rcx, rdi; unsigned __int16 *
0x140005f90  mov     edx, 314h; unsigned int
0x140005f95  mov     [rsp+4D0h+var_4B0], r14; unsigned __int16 *
0x140005f9a  call    ?LOGASSERTHR@@YAXPEBGK000J@Z; LOGASSERTHR(ushort const *,ulong,ushort const *,ushort const *,ushort const *,long)
0x140005f9f  call    cs:__imp_IsDebuggerPresent
0x140005fa5  test    eax, eax
0x140005fa7  jz      short loc_140005FB4
0x140005fa9  mov     r9d, 314h
0x140005faf  jmp     loc_140005EFE
0x140005fb4  mov     r8d, 314h
0x140005fba  jmp     loc_140005F2B
0x140005fbf  lea     rdx, [rbp+3D0h+SubKey]; lpSubKey
0x140005fc3  mov     rcx, 0FFFFFFFF80000002h; hKey
0x140005fca  call    cs:__imp_RegDeleteKeyW
0x140005fd0  mov     rax, rsi
0x140005fd3  lea     rcx, aSystemCurrentc; "SYSTEM\\CurrentControlSet\\Control\\Saf"...
0x140005fda  mov     rdx, rdi
0x140005fdd  lea     r8, [rbp+3D0h+SubKey]
0x140005fe1  xor     r10d, r10d
0x140005fe4  test    rax, rax
0x140005fe7  jz      short loc_140006005
0x140005fe9  movzx   r9d, word ptr [rcx]
0x140005fed  test    r9w, r9w
0x140005ff1  jz      short loc_140006005
0x140005ff3  mov     [r8], r9w
0x140005ff7  add     rcx, r13
0x140005ffa  add     r8, r13
0x140005ffd  sub     rax, r12
0x140006000  sub     rdx, r12; unsigned __int64
0x140006003  jnz     short loc_140005FE4
0x140006005  mov     rax, rdx
0x140006008  lea     rcx, [r8-2]
0x14000600c  neg     rax
0x14000600f  sbb     ebx, ebx
0x140006011  not     ebx
0x140006013  and     ebx, 8007007Ah
0x140006019  test    rdx, rdx
0x14000601c  cmovnz  rcx, r8
0x140006020  mov     [rcx], r10w
0x140006024  jnz     short loc_14000607E
0x140006026  lea     r15, aChra; "CHRA"
0x14000602d  mov     [rsp+4D0h+var_4A8], ebx; int
0x140006031  lea     rsi, aCntserviceUnin; "CNTService::Uninstall"
0x140006038  mov     r9, r15; unsigned __int16 *
0x14000603b  lea     rdi, aTermsrvWmsSrcC_5; "termsrv\\wms\\src\\common\\ntservice\\n"...
0x140006042  mov     r8, rsi; unsigned __int16 *
0x140006045  lea     r14, aHr; "hr"
0x14000604c  mov     rcx, rdi; unsigned __int16 *
0x14000604f  mov     edx, 31Fh; unsigned int
0x140006054  mov     [rsp+4D0h+var_4B0], r14; unsigned __int16 *
0x140006059  call    ?LOGASSERTHR@@YAXPEBGK000J@Z; LOGASSERTHR(ushort const *,ulong,ushort const *,ushort const *,ushort const *,long)
0x14000605e  call    cs:__imp_IsDebuggerPresent
0x140006064  test    eax, eax
0x140006066  jz      short loc_140006073
0x140006068  mov     r9d, 31Fh
0x14000606e  jmp     loc_140005EFE
0x140006073  mov     r8d, 31Fh
0x140006079  jmp     loc_140005F2B
0x14000607e  mov     r8, r14; unsigned __int16 *
0x140006081  lea     rcx, [rbp+3D0h+SubKey]; unsigned __int16 *
0x140006085  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x14000608a  mov     ebx, eax
0x14000608c  test    eax, eax
0x14000608e  jns     short loc_1400060E8
0x140006090  mov     [rsp+4D0h+var_4A8], eax; int
0x140006094  lea     r15, aChra; "CHRA"
0x14000609b  lea     rsi, aCntserviceUnin; "CNTService::Uninstall"
0x1400060a2  mov     r9, r15; unsigned __int16 *
  ... truncated ...
```
