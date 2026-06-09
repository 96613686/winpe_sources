# Common::Deployment::CreateShellRefreshProcess(void)

- ea: `0x180029e04`
- end: `0x18002a2c7`
- name: `?CreateShellRefreshProcess@Deployment@Common@@YAJXZ`
- size: `1219`
- prototype: `__int64 __fastcall(Common::Deployment *__hidden this)`
- caller_count: `6`
- callee_count: `21`
- tags: `file_ops, authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x180029dd0`
- `0x18002a920`
- `0x180059750`
- `0x180090080`
- `0x1800e23c0`
- `0x1800e2620`

## callees

- `0x180006564`
- `0x18000669c`
- `0x180012fc8`
- `0x18001adb4`
- `0x18001f678`
- `0x180029e04`
- `0x18003d9b0`
- `0x18004ce78`
- `0x18004e244`
- `0x18004e96c`
- `0x18005174c`
- `0x1800529ec`
- `0x180074000`
- `0x18007b024`
- `0x18007b1e8`
- `0x1800aed10`
- `0x1800af1bc`
- `0x1800af918`
- `0x1800affe4`
- `0x1800d7ad0`
- `0x18017e174`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002a176`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002a176`
- `api-ms-win-core-processthreads-l1-1-0!CreateProcessAsUserW` at `0x18002a168`
- `api-ms-win-core-processthreads-l1-1-0!CreateProcessAsUserW` at `0x18002a168`
- `api-ms-win-core-registry-l1-1-0!RegDeleteKeyExW` at `0x18002a21d`
- `api-ms-win-core-registry-l1-1-0!RegDeleteKeyExW` at `0x18002a21d`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemDirectoryW` at `0x18002a018`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemDirectoryW` at `0x18002a018`
- `ADVAPI32!DuplicateTokenEx` at `0x180029f63`
- `ADVAPI32!DuplicateTokenEx` at `0x180029f63`

## string_xrefs

- `0x180029e4b`: `onecore\admin\appmodel\common\shellrefresh.cpp`
- `0x180029eac`: `onecore\admin\appmodel\common\shellrefresh.cpp`
- `0x180029f09`: `onecore\admin\appmodel\common\shellrefresh.cpp`
- `0x180029f7a`: `onecore\admin\appmodel\common\shellrefresh.cpp`
- `0x180029fd4`: `onecore\admin\appmodel\common\shellrefresh.cpp`
- `0x18002a02f`: `onecore\admin\appmodel\common\shellrefresh.cpp`
- `0x18002a058`: `onecore\admin\appmodel\common\shellrefresh.cpp`
- `0x18002a0ac`: `onecore\admin\appmodel\common\shellrefresh.cpp`
- `0x18002a1c0`: `onecore\admin\appmodel\common\shellrefresh.cpp`
- `0x18002a237`: `onecore\admin\appmodel\common\shellrefresh.cpp`
- `0x18002a0da`: `\rundll32.exe `
- `0x18002a111`: `\AppXDeploymentExtensions.OneCore.dll,ShellRefresh`

## pseudocode

```c
// Hidden C++ exception states: #wind=7
__int64 __fastcall Common::Deployment::CreateShellRefreshProcess(Common::Deployment *this)
{
  unsigned int LastError; // ebx
  struct Common::StringBuffer *v2; // r8
  int ShellRefreshRegistryLocation; // eax
  struct _PROCESS_INFORMATION *v4; // rdx
  WCHAR *v5; // rcx
  int v6; // eax
  const char *v7; // r9
  unsigned int *v8; // r8
  int ShellRefreshRegistryMarker; // eax
  UINT SystemDirectoryW; // eax
  const char *v11; // r9
  int appended; // eax
  __int64 v13; // rdx
  const struct std::nothrow_t *v14; // rdx
  BOOL v15; // edi
  signed int v16; // eax
  const struct std::nothrow_t *v17; // rdx
  __int64 v18; // rdx
  wil::details::in1diag3 *v19; // rcx
  int v20; // eax
  LPCWSTR v21; // rdi
  const struct std::nothrow_t *v22; // rdx
  int TokenType; // [rsp+20h] [rbp-E0h]
  int TokenTypea; // [rsp+20h] [rbp-E0h]
  int TokenTypeb; // [rsp+20h] [rbp-E0h]
  HANDLE hExistingToken; // [rsp+60h] [rbp-A0h] BYREF
  HANDLE hToken; // [rsp+68h] [rbp-98h] BYREF
  _BYTE v29[8]; // [rsp+70h] [rbp-90h] BYREF
  int v30; // [rsp+78h] [rbp-88h] BYREF
  LPCWSTR lpSubKey[2]; // [rsp+80h] [rbp-80h] BYREF
  int v32; // [rsp+90h] [rbp-70h]
  struct _PROCESS_INFORMATION ProcessInformation; // [rsp+98h] [rbp-68h] BYREF
  HKEY hKey; // [rsp+B0h] [rbp-50h] BYREF
  LPWSTR lpCommandLine[2]; // [rsp+B8h] [rbp-48h] BYREF
  __int64 v36; // [rsp+C8h] [rbp-38h]
  _QWORD v37[4]; // [rsp+D0h] [rbp-30h] BYREF
  struct _STARTUPINFOW StartupInfo; // [rsp+F0h] [rbp-10h] BYREF
  WCHAR Buffer[264]; // [rsp+160h] [rbp+60h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+3A8h] [rbp+2A8h]

  v30 = 0;
  hKey = 0;
  if ( !(unsigned __int8)IsSHChangeNotifyPresent(this) )
  {
    LastError = -2147467263;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x68,
      (unsigned int)"onecore\\admin\\appmodel\\common\\shellrefresh.cpp",
      (const char *)0x80004001LL,
      TokenType);
    goto LABEL_53;
  }
  memset(&ProcessInformation, 0, sizeof(ProcessInformation));
  memset_0(&StartupInfo.cb + 1, 0, 0x64u);
  StartupInfo.cb = 104;
  *(_OWORD *)lpSubKey = 0;
  v32 = 0;
  ShellRefreshRegistryLocation = Common::Deployment::GetShellRefreshRegistryLocation(
                                   (Common::Deployment *)1,
                                   (int)lpSubKey,
                                   v2);
  LastError = ShellRefreshRegistryLocation;
  if ( ShellRefreshRegistryLocation < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x74,
      (unsigned int)"onecore\\admin\\appmodel\\common\\shellrefresh.cpp",
      (const char *)(unsigned int)ShellRefreshRegistryLocation,
      TokenType);
    goto LABEL_5;
  }
  hExistingToken = 0;
  wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::reset(
    &hExistingToken,
    0);
  v6 = wil::open_current_access_token_nothrow(&hExistingToken, 131083);
  LastError = v6;
  if ( v6 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x79,
      (unsigned int)"onecore\\admin\\appmodel\\common\\shellrefresh.cpp",
      (const char *)(unsigned int)v6,
      TokenType);
LABEL_10:
    wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&hExistingToken);
LABEL_5:
    v5 = (WCHAR *)lpSubKey[1];
    if ( !lpSubKey[1] )
    {
LABEL_7:
      wil::details::CloseProcessInformation((wil::details *)&ProcessInformation, v4);
      goto LABEL_53;
    }
LABEL_6:
    operator delete(v5, (const struct std::nothrow_t *)v4);
    goto LABEL_7;
  }
  hToken = 0;
  wil::run_as_self_failfast(v29);
  wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::reset(
    &hToken,
    0);
  if ( !DuplicateTokenEx(hExistingToken, 0xF01FFu, 0, SecurityImpersonation, TokenPrimary, &hToken) )
  {
    LastError = wil::details::in1diag3::Return_GetLastError(
                  retaddr,
                  (void *)0x7F,
                  (unsigned int)"onecore\\admin\\appmodel\\common\\shellrefresh.cpp",
                  v7);
LABEL_13:
    wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void wil::details::RevertImpersonateToken(void *),wistd::integral_constant<unsigned __int64,2>,void *,__int64,-1,void *>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void wil::details::RevertImpersonateToken(void *),wistd::integral_constant<unsigned __int64,2>,void *,__int64,-1,void *>>(v29);
LABEL_14:
    wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&hToken);
    goto LABEL_10;
  }
  wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void wil::details::RevertImpersonateToken(void *),wistd::integral_constant<unsigned __int64,2>,void *,__int64,-1,void *>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void wil::details::RevertImpersonateToken(void *),wistd::integral_constant<unsigned __int64,2>,void *,__int64,-1,void *>>(v29);
  do
  {
    ShellRefreshRegistryMarker = Common::Deployment::CreateShellRefreshRegistryMarker(
                                   (Common::Deployment *)lpSubKey,
                                   (struct Common::StringBuffer *)&v30,
                                   v8);
    LastError = ShellRefreshRegistryMarker;
  }
  while ( ShellRefreshRegistryMarker == -2147023878 );
  if ( ShellRefreshRegistryMarker < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x8F,
      (unsigned int)"onecore\\admin\\appmodel\\common\\shellrefresh.cpp",
      (const char *)(unsigned int)ShellRefreshRegistryMarker,
      TokenTypea);
    goto LABEL_14;
  }
  if ( v30 == 1 )
  {
    wil::run_as_self_failfast(v29);
    memset_0(Buffer, 0, 0x208u);
    SystemDirectoryW = GetSystemDirectoryW(Buffer, 0x104u);
    if ( !SystemDirectoryW )
    {
      LastError = wil::details::in1diag3::Return_GetLastError(
                    retaddr,
                    (void *)0x9E,
                    (unsigned int)"onecore\\admin\\appmodel\\common\\shellrefresh.cpp",
                    v11);
      goto LABEL_13;
    }
    if ( SystemDirectoryW >= 0x104 )
    {
      LastError = -2147024774;
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x9F,
        (unsigned int)"onecore\\admin\\appmodel\\common\\shellrefresh.cpp",
        (const char *)0x8007007ALL,
        TokenTypea);
      goto LABEL_13;
    }
    *(_OWORD *)lpCommandLine = 0;
    v36 = 0;
    v37[1] = lpCommandLine;
    v37[0] = &Common::StringBufferBuilder::`vftable';
    v37[2] = lpCommandLine;
    appended = Common::StringBuilder::AppendString((Common::StringBuilder *)v37, Buffer);
    LastError = appended;
    if ( appended < 0 )
    {
      v13 = 163;
      goto LABEL_27;
    }
    appended = Common::StringBuilder::AppendString((Common::StringBuilder *)v37, L"\\rundll32.exe ");
    LastError = appended;
    if ( appended < 0 )
    {
      v13 = 164;
      goto LABEL_27;
    }
    appended = Common::StringBuilder::AppendString((Common::StringBuilder *)v37, Buffer);
    LastError = appended;
    if ( appended < 0 )
    {
      v13 = 165;
      goto LABEL_27;
    }
    appended = Common::StringBuilder::AppendString(
                 (Common::StringBuilder *)v37,
                 L"\\AppXDeploymentExtensions.OneCore.dll,ShellRefresh");
    LastError = appended;
    if ( appended < 0 )
    {
      v13 = 166;
LABEL_27:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v13,
        (unsigned int)"onecore\\admin\\appmodel\\common\\shellrefresh.cpp",
        (const char *)(unsigned int)appended,
        TokenTypea);
      if ( lpCommandLine[1] )
        operator delete(lpCommandLine[1], v14);
      goto LABEL_13;
    }
    v15 = CreateProcessAsUserW(hToken, 0, lpCommandLine[1], 0, 0, 0, 0, 0, 0, &StartupInfo, &ProcessInformation);
    v16 = GetLastError();
    LastError = v16;
    if ( v16 > 0 )
      LastError = (unsigned __int16)v16 | 0x80070000;
    if ( lpCommandLine[1] )
      operator delete(lpCommandLine[1], v17);
    wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void wil::details::RevertImpersonateToken(void *),wistd::integral_constant<unsigned __int64,2>,void *,__int64,-1,void *>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void wil::details::RevertImpersonateToken(void *),wistd::integral_constant<unsigned __int64,2>,void *,__int64,-1,void *>>(v29);
    if ( !v15 )
    {
      v19 = retaddr;
      if ( (LastError & 0x80000000) != 0 )
        wil::details::in1diag3::_Log_Hr(
          retaddr,
          (void *)0xAF,
          (unsigned int)"onecore\\admin\\appmodel\\common\\shellrefresh.cpp",
          (const char *)LastError,
          TokenTypeb);
      if ( (Microsoft_Windows_AppXDeployment_ServerEnableBits & 4) != 0 )
        McTemplateU0d_EventWriteTransfer(v19, &ShellRefreshProcessLaunchError, LastError);
      details::appxLog<long>(LastError, v18, &ShellRefreshProcessLaunchError, LastError);
      v20 = Common::RegistryKey::OpenCurrentUser(&hKey, 0xF003Fu);
      v21 = lpSubKey[1];
      if ( v20 >= 0 )
        RegDeleteKeyExW(hKey, lpSubKey[1], 0, 0);
      if ( (LastError & 0x80000000) != 0 )
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0xB9,
          (unsigned int)"onecore\\admin\\appmodel\\common\\shellrefresh.cpp",
          (const char *)LastError,
          TokenTypeb);
      wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&hToken);
      wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&hExistingToken);
      if ( !v21 )
        goto LABEL_7;
      v5 = (WCHAR *)v21;
      goto LABEL_6;
    }
  }
  wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&hToken);
  wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&hExistingToken);
  if ( lpSubKey[1] )
    operator delete((void *)lpSubKey[1], v22);
  wil::details::CloseProcessInformation((wil::details *)&ProcessInformation, (struct _PROCESS_INFORMATION *)v22);
  LastError = 0;
LABEL_53:
  Common::RegistryKey::~RegistryKey((Common::RegistryKey *)&hKey);
  return LastError;
}

```

## disassembly

```asm
0x180029e04  push    rbp
0x180029e06  push    rbx
0x180029e07  push    rsi
0x180029e08  push    rdi
0x180029e09  lea     rbp, [rsp-288h]
0x180029e11  sub     rsp, 388h
0x180029e18  mov     rax, cs:__security_cookie
0x180029e1f  xor     rax, rsp
0x180029e22  mov     [rbp+2A0h+var_30], rax
0x180029e29  xor     esi, esi
0x180029e2b  mov     [rsp+3A0h+var_328], esi
0x180029e2f  mov     [rbp+2A0h+hKey], rsi
0x180029e33  call    IsSHChangeNotifyPresent
0x180029e38  test    al, al
0x180029e3a  jnz     short loc_180029E5F
0x180029e3c  mov     rcx, [rbp+2A8h]; this
0x180029e43  mov     ebx, 80004001h
0x180029e48  mov     r9d, ebx; char *
0x180029e4b  lea     r8, aOnecoreAdminAp_83; "onecore\\admin\\appmodel\\common\\shell"...
0x180029e52  lea     edx, [rsi+68h]; void *
0x180029e55  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180029e5a  jmp     loc_18002A2A0
0x180029e5f  xorps   xmm0, xmm0
0x180029e62  xor     eax, eax
0x180029e64  movups  xmmword ptr [rbp+2A0h+ProcessInformation.hProcess], xmm0
0x180029e68  mov     qword ptr [rbp+2A0h+ProcessInformation.dwProcessId], rax
0x180029e6c  xor     edx, edx; Val
0x180029e6e  lea     r8d, [rax+64h]; Size
0x180029e72  lea     rcx, [rbp+2A0h+StartupInfo+4]; void *
0x180029e76  call    memset_0
0x180029e7b  mov     [rbp+2A0h+StartupInfo.cb], 68h ; 'h'
0x180029e82  xorps   xmm0, xmm0
0x180029e85  movups  xmmword ptr [rbp+2A0h+lpSubKey], xmm0
0x180029e89  mov     [rbp+2A0h+var_310], esi
0x180029e8c  lea     rdx, [rbp+2A0h+lpSubKey]; int
0x180029e90  mov     edi, 1
0x180029e95  mov     ecx, edi; this
0x180029e97  call    ?GetShellRefreshRegistryLocation@Deployment@Common@@YAJHPEAVStringBuffer@2@@Z; Common::Deployment::GetShellRefreshRegistryLocation(int,Common::StringBuffer *)
0x180029e9c  mov     ebx, eax
0x180029e9e  test    eax, eax
0x180029ea0  jns     short loc_180029ED9
0x180029ea2  mov     rcx, [rbp+2A8h]; this
0x180029ea9  mov     r9d, eax; char *
0x180029eac  lea     r8, aOnecoreAdminAp_83; "onecore\\admin\\appmodel\\common\\shell"...
0x180029eb3  lea     edx, [rdi+73h]; void *
0x180029eb6  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180029ebb  nop
0x180029ebc  mov     rcx, [rbp+2A0h+lpSubKey+8]; void *
0x180029ec0  test    rcx, rcx
0x180029ec3  jz      short loc_180029ECB
0x180029ec5  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180029eca  nop
0x180029ecb  lea     rcx, [rbp+2A0h+ProcessInformation]; this
0x180029ecf  call    ?CloseProcessInformation@details@wil@@YAXPEAU_PROCESS_INFORMATION@@@Z; wil::details::CloseProcessInformation(_PROCESS_INFORMATION *)
0x180029ed4  jmp     loc_18002A2A0
0x180029ed9  mov     [rsp+3A0h+hExistingToken], rsi
0x180029ede  xor     edx, edx
0x180029ee0  lea     rcx, [rsp+3A0h+hExistingToken]
0x180029ee5  call    ?reset@?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::reset(void *)
0x180029eea  mov     edx, 2000Bh
0x180029eef  lea     rcx, [rsp+3A0h+hExistingToken]
0x180029ef4  call    ?open_current_access_token_nothrow@wil@@YAJPEAPEAXKW4OpenThreadTokenAs@1@@Z; wil::open_current_access_token_nothrow(void * *,ulong,wil::OpenThreadTokenAs)
0x180029ef9  mov     ebx, eax
0x180029efb  test    eax, eax
0x180029efd  jns     short loc_180029F27
0x180029eff  mov     rcx, [rbp+2A8h]; this
0x180029f06  mov     r9d, eax; char *
0x180029f09  lea     r8, aOnecoreAdminAp_83; "onecore\\admin\\appmodel\\common\\shell"...
0x180029f10  mov     edx, 79h ; 'y'; void *
0x180029f15  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180029f1a  nop
0x180029f1b  lea     rcx, [rsp+3A0h+hExistingToken]
0x180029f20  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x180029f25  jmp     short loc_180029EBC
0x180029f27  mov     [rsp+3A0h+hToken], rsi
0x180029f2c  lea     rcx, [rsp+3A0h+var_330]
0x180029f31  call    ?run_as_self_failfast@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?RevertImpersonateToken@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAX_J$0?0PEAX@details@wil@@@details@wil@@@1@XZ; wil::run_as_self_failfast(void)
0x180029f36  xor     edx, edx
0x180029f38  lea     rcx, [rsp+3A0h+hToken]
0x180029f3d  call    ?reset@?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::reset(void *)
0x180029f42  lea     rax, [rsp+3A0h+hToken]
0x180029f47  mov     [rsp+3A0h+phNewToken], rax; phNewToken
0x180029f4c  mov     [rsp+3A0h+TokenType], edi; int
0x180029f50  mov     r9d, 2; ImpersonationLevel
0x180029f56  xor     r8d, r8d; lpTokenAttributes
0x180029f59  mov     edx, 0F01FFh; dwDesiredAccess
0x180029f5e  mov     rcx, [rsp+3A0h+hExistingToken]; hExistingToken
0x180029f63  call    cs:__imp_DuplicateTokenEx
0x180029f6a  nop     dword ptr [rax+rax+00h]
0x180029f6f  test    eax, eax
0x180029f71  jnz     short loc_180029FA5
0x180029f73  mov     rcx, [rbp+2A8h]; this
0x180029f7a  lea     r8, aOnecoreAdminAp_83; "onecore\\admin\\appmodel\\common\\shell"...
0x180029f81  lea     edx, [rax+7Fh]; void *
0x180029f84  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180029f89  mov     ebx, eax
0x180029f8b  lea     rcx, [rsp+3A0h+var_330]
0x180029f90  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?RevertImpersonateToken@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAX_J$0?0PEAX@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&wil::details::RevertImpersonateToken(void *),wistd::integral_constant<unsigned __int64,2>,void *,__int64,-1,void *>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&wil::details::RevertImpersonateToken(void *),wistd::integral_constant<unsigned __int64,2>,void *,__int64,-1,void *>>(void)
0x180029f95  nop
0x180029f96  lea     rcx, [rsp+3A0h+hToken]
0x180029f9b  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x180029fa0  jmp     loc_180029F1B
0x180029fa5  lea     rcx, [rsp+3A0h+var_330]
0x180029faa  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?RevertImpersonateToken@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAX_J$0?0PEAX@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&wil::details::RevertImpersonateToken(void *),wistd::integral_constant<unsigned __int64,2>,void *,__int64,-1,void *>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&wil::details::RevertImpersonateToken(void *),wistd::integral_constant<unsigned __int64,2>,void *,__int64,-1,void *>>(void)
0x180029faf  lea     rdx, [rsp+3A0h+var_328]; struct Common::StringBuffer *
0x180029fb4  lea     rcx, [rbp+2A0h+lpSubKey]; this
0x180029fb8  call    ?CreateShellRefreshRegistryMarker@Deployment@Common@@YAJPEAVStringBuffer@2@PEAK@Z; Common::Deployment::CreateShellRefreshRegistryMarker(Common::StringBuffer *,ulong *)
0x180029fbd  mov     ebx, eax
0x180029fbf  cmp     eax, 800703FAh
0x180029fc4  jz      short loc_180029FAF
0x180029fc6  test    eax, eax
0x180029fc8  jns     short loc_180029FE7
0x180029fca  mov     rcx, [rbp+2A8h]; this
0x180029fd1  mov     r9d, eax; char *
0x180029fd4  lea     r8, aOnecoreAdminAp_83; "onecore\\admin\\appmodel\\common\\shell"...
0x180029fdb  mov     edx, 8Fh; void *
0x180029fe0  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180029fe5  jmp     short loc_180029F96
0x180029fe7  cmp     [rsp+3A0h+var_328], edi
0x180029feb  jnz     loc_18002A270
0x180029ff1  lea     rcx, [rsp+3A0h+var_330]
0x180029ff6  call    ?run_as_self_failfast@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?RevertImpersonateToken@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAX_J$0?0PEAX@details@wil@@@details@wil@@@1@XZ; wil::run_as_self_failfast(void)
0x180029ffb  nop
0x180029ffc  xor     edx, edx; Val
0x180029ffe  mov     r8d, 208h; Size
0x18002a004  lea     rcx, [rbp+2A0h+Buffer]; void *
0x18002a008  call    memset_0
0x18002a00d  mov     ebx, 104h
0x18002a012  mov     edx, ebx; uSize
0x18002a014  lea     rcx, [rbp+2A0h+Buffer]; lpBuffer
0x18002a018  call    cs:__imp_GetSystemDirectoryW
0x18002a01f  nop     dword ptr [rax+rax+00h]
0x18002a024  test    eax, eax
0x18002a026  jnz     short loc_18002A045
0x18002a028  mov     rcx, [rbp+2A8h]; this
0x18002a02f  lea     r8, aOnecoreAdminAp_83; "onecore\\admin\\appmodel\\common\\shell"...
0x18002a036  lea     edx, [rbx-66h]; void *
0x18002a039  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18002a03e  mov     ebx, eax
0x18002a040  jmp     loc_180029F8B
0x18002a045  cmp     eax, ebx
0x18002a047  jb      short loc_18002A06B
0x18002a049  mov     rcx, [rbp+2A8h]; this
0x18002a050  mov     ebx, 8007007Ah
0x18002a055  mov     r9d, ebx; char *
0x18002a058  lea     r8, aOnecoreAdminAp_83; "onecore\\admin\\appmodel\\common\\shell"...
0x18002a05f  mov     edx, 9Fh; void *
0x18002a064  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002a069  jmp     short loc_18002A040
0x18002a06b  mov     [rbp+2A0h+var_2D8], rsi
0x18002a06f  xorps   xmm0, xmm0
0x18002a072  movups  xmmword ptr [rbp+2A0h+lpCommandLine], xmm0
0x18002a076  mov     dword ptr [rbp+2A0h+var_2D8], esi
0x18002a079  lea     rax, [rbp+2A0h+lpCommandLine]
0x18002a07d  mov     [rbp+2A0h+var_2C8], rax
0x18002a081  lea     rax, ??_7StringBufferBuilder@Common@@6B@; const Common::StringBufferBuilder::`vftable'
0x18002a088  mov     [rbp+2A0h+var_2D0], rax
0x18002a08c  lea     rax, [rbp+2A0h+lpCommandLine]
0x18002a090  mov     [rbp+2A0h+var_2C0], rax
0x18002a094  lea     rdx, [rbp+2A0h+Buffer]; unsigned __int16 *
0x18002a098  lea     rcx, [rbp+2A0h+var_2D0]; this
0x18002a09c  call    ?AppendString@StringBuilder@Common@@QEAAJPEBG@Z; Common::StringBuilder::AppendString(ushort const *)
0x18002a0a1  mov     ebx, eax
0x18002a0a3  test    eax, eax
0x18002a0a5  jns     short loc_18002A0DA
0x18002a0a7  mov     edx, 0A3h; void *
0x18002a0ac  lea     r8, aOnecoreAdminAp_83; "onecore\\admin\\appmodel\\common\\shell"...
0x18002a0b3  mov     r9d, eax; char *
0x18002a0b6  mov     rcx, [rbp+2A8h]; this
0x18002a0bd  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002a0c2  nop
0x18002a0c3  mov     rcx, [rbp+2A0h+lpCommandLine+8]; void *
0x18002a0c7  test    rcx, rcx
0x18002a0ca  jz      loc_18002A040
0x18002a0d0  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18002a0d5  jmp     loc_18002A040
0x18002a0da  lea     rdx, aRundll32Exe; "\\rundll32.exe "
0x18002a0e1  lea     rcx, [rbp+2A0h+var_2D0]; this
0x18002a0e5  call    ?AppendString@StringBuilder@Common@@QEAAJPEBG@Z; Common::StringBuilder::AppendString(ushort const *)
0x18002a0ea  mov     ebx, eax
0x18002a0ec  test    eax, eax
0x18002a0ee  jns     short loc_18002A0F7
0x18002a0f0  mov     edx, 0A4h
0x18002a0f5  jmp     short loc_18002A0AC
0x18002a0f7  lea     rdx, [rbp+2A0h+Buffer]; unsigned __int16 *
0x18002a0fb  lea     rcx, [rbp+2A0h+var_2D0]; this
0x18002a0ff  call    ?AppendString@StringBuilder@Common@@QEAAJPEBG@Z; Common::StringBuilder::AppendString(ushort const *)
0x18002a104  mov     ebx, eax
0x18002a106  test    eax, eax
0x18002a108  jns     short loc_18002A111
0x18002a10a  mov     edx, 0A5h
0x18002a10f  jmp     short loc_18002A0AC
0x18002a111  lea     rdx, aAppxdeployment_2; "\\AppXDeploymentExtensions.OneCore.dll,"...
0x18002a118  lea     rcx, [rbp+2A0h+var_2D0]; this
0x18002a11c  call    ?AppendString@StringBuilder@Common@@QEAAJPEBG@Z; Common::StringBuilder::AppendString(ushort const *)
0x18002a121  mov     ebx, eax
0x18002a123  test    eax, eax
0x18002a125  jns     short loc_18002A131
0x18002a127  mov     edx, 0A6h
0x18002a12c  jmp     loc_18002A0AC
0x18002a131  lea     rax, [rbp+2A0h+ProcessInformation]
0x18002a135  mov     [rsp+3A0h+lpProcessInformation], rax; lpProcessInformation
0x18002a13a  lea     rax, [rbp+2A0h+StartupInfo]
0x18002a13e  mov     [rsp+3A0h+lpStartupInfo], rax; lpStartupInfo
0x18002a143  mov     [rsp+3A0h+lpCurrentDirectory], rsi; lpCurrentDirectory
0x18002a148  mov     [rsp+3A0h+lpEnvironment], rsi; lpEnvironment
0x18002a14d  mov     [rsp+3A0h+dwCreationFlags], esi; dwCreationFlags
0x18002a151  mov     dword ptr [rsp+3A0h+phNewToken], esi; bInheritHandles
0x18002a155  mov     qword ptr [rsp+3A0h+TokenType], rsi; int
0x18002a15a  xor     r9d, r9d; lpProcessAttributes
0x18002a15d  mov     r8, [rbp+2A0h+lpCommandLine+8]; lpCommandLine
0x18002a161  xor     edx, edx; lpApplicationName
0x18002a163  mov     rcx, [rsp+3A0h+hToken]; hToken
0x18002a168  call    cs:__imp_CreateProcessAsUserW
0x18002a16f  nop     dword ptr [rax+rax+00h]
0x18002a174  mov     edi, eax
0x18002a176  call    cs:__imp_GetLastError
0x18002a17d  nop     dword ptr [rax+rax+00h]
0x18002a182  mov     ebx, eax
0x18002a184  test    eax, eax
0x18002a186  jle     short loc_18002A191
0x18002a188  movzx   ebx, ax
0x18002a18b  or      ebx, 80070000h
0x18002a191  mov     rcx, [rbp+2A0h+lpCommandLine+8]; void *
0x18002a195  test    rcx, rcx
0x18002a198  jz      short loc_18002A1A0
0x18002a19a  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18002a19f  nop
0x18002a1a0  lea     rcx, [rsp+3A0h+var_330]
0x18002a1a5  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?RevertImpersonateToken@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAX_J$0?0PEAX@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&wil::details::RevertImpersonateToken(void *),wistd::integral_constant<unsigned __int64,2>,void *,__int64,-1,void *>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&wil::details::RevertImpersonateToken(void *),wistd::integral_constant<unsigned __int64,2>,void *,__int64,-1,void *>>(void)
0x18002a1aa  test    edi, edi
0x18002a1ac  jnz     loc_18002A270
0x18002a1b2  mov     rcx, [rbp+2A8h]; this
0x18002a1b9  test    ebx, ebx
0x18002a1bb  jns     short loc_18002A1D1
0x18002a1bd  mov     r9d, ebx; char *
0x18002a1c0  lea     r8, aOnecoreAdminAp_83; "onecore\\admin\\appmodel\\common\\shell"...
0x18002a1c7  mov     edx, 0AFh; void *
0x18002a1cc  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18002a1d1  test    cs:Microsoft_Windows_AppXDeployment_ServerEnableBits, 4
0x18002a1d8  jz      short loc_18002A1E9
0x18002a1da  mov     r8d, ebx
0x18002a1dd  lea     rdx, ShellRefreshProcessLaunchError
0x18002a1e4  call    McTemplateU0d_EventWriteTransfer
0x18002a1e9  mov     r9d, ebx
0x18002a1ec  lea     r8, ShellRefreshProcessLaunchError
0x18002a1f3  mov     ecx, ebx
0x18002a1f5  call    ??$appxLog@J@details@@YAXJAEBU_GUID@@AEBU_EVENT_DESCRIPTOR@@J@Z; details::appxLog<long>(long,_GUID const &,_EVENT_DESCRIPTOR const &,long)
0x18002a1fa  mov     edx, 0F003Fh; samDesired
0x18002a1ff  lea     rcx, [rbp+2A0h+hKey]; phkResult
0x18002a203  call    ?OpenCurrentUser@RegistryKey@Common@@QEAAJK@Z; Common::RegistryKey::OpenCurrentUser(ulong)
0x18002a208  mov     rdi, [rbp+2A0h+lpSubKey+8]
0x18002a20c  test    eax, eax
0x18002a20e  js      short loc_18002A229
0x18002a210  xor     r9d, r9d; Reserved
0x18002a213  xor     r8d, r8d; samDesired
0x18002a216  mov     rdx, rdi; lpSubKey
0x18002a219  mov     rcx, [rbp+2A0h+hKey]; hKey
0x18002a21d  call    cs:__imp_RegDeleteKeyExW
0x18002a224  nop     dword ptr [rax+rax+00h]
0x18002a229  test    ebx, ebx
0x18002a22b  jns     short loc_18002A249
0x18002a22d  mov     rcx, [rbp+2A8h]; this
0x18002a234  mov     r9d, ebx; char *
0x18002a237  lea     r8, aOnecoreAdminAp_83; "onecore\\admin\\appmodel\\common\\shell"...
0x18002a23e  mov     edx, 0B9h; void *
0x18002a243  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002a248  nop
0x18002a249  lea     rcx, [rsp+3A0h+hToken]
0x18002a24e  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x18002a253  nop
0x18002a254  lea     rcx, [rsp+3A0h+hExistingToken]
0x18002a259  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x18002a25e  nop
0x18002a25f  test    rdi, rdi
0x18002a262  jz      loc_180029ECB
0x18002a268  mov     rcx, rdi
0x18002a26b  jmp     loc_180029EC5
0x18002a270  lea     rcx, [rsp+3A0h+hToken]
0x18002a275  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x18002a27a  nop
0x18002a27b  lea     rcx, [rsp+3A0h+hExistingToken]
0x18002a280  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x18002a285  nop
0x18002a286  mov     rcx, [rbp+2A0h+lpSubKey+8]; void *
0x18002a28a  test    rcx, rcx
0x18002a28d  jz      short loc_18002A295
0x18002a28f  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18002a294  nop
0x18002a295  lea     rcx, [rbp+2A0h+ProcessInformation]; this
0x18002a299  call    ?CloseProcessInformation@details@wil@@YAXPEAU_PROCESS_INFORMATION@@@Z; wil::details::CloseProcessInformation(_PROCESS_INFORMATION *)
0x18002a29e  mov     ebx, esi
0x18002a2a0  lea     rcx, [rbp+2A0h+hKey]; this
0x18002a2a4  call    ??1RegistryKey@Common@@QEAA@XZ; Common::RegistryKey::~RegistryKey(void)
0x18002a2a9  mov     eax, ebx
0x18002a2ab  mov     rcx, [rbp+2A0h+var_30]
0x18002a2b2  xor     rcx, rsp; StackCookie
0x18002a2b5  call    __security_check_cookie
0x18002a2ba  add     rsp, 388h
0x18002a2c1  pop     rdi
  ... truncated ...
```
