# Windows::ProcessHelpers::CreateProcessAsUserToken(wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>> const &,std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>>,std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>>)

- ea: `0x140373ec0`
- end: `0x140374214`
- name: `?CreateProcessAsUserToken@ProcessHelpers@Windows@@YA?AV?$unique_struct@U_PROCESS_INFORMATION@@P6AXPEAU1@@Z$1?CloseProcessInformation@details@wil@@YAX0@Z$$T$0A@@wil@@AEBV?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@4@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@1@Z`
- size: `852`
- prototype: `LPHANDLE __fastcall(LPHANDLE lpTargetHandle, HANDLE *, WCHAR *, WCHAR *)`
- caller_count: `6`
- callee_count: `10`
- tags: `authz_impersonation, registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x140243d30`
- `0x1402a2a30`
- `0x1402a31a0`
- `0x1402a3ca0`
- `0x1402a5560`
- `0x1402aa49c`

## callees

- `0x1400289d4`
- `0x14003c578`
- `0x1400413a8`
- `0x140045404`
- `0x140312df0`
- `0x140373ec0`
- `0x140379070`
- `0x1403790d8`
- `0x140380b50`
- `0x140380bd0`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x14037408a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x140374093`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x1403740c9`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x1403740d2`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x14037408a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x140374093`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x1403740c9`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x1403740d2`
- `api-ms-win-core-processthreads-l1-1-0!CreateProcessAsUserW` at `0x140374078`
- `api-ms-win-core-processthreads-l1-1-0!CreateProcessAsUserW` at `0x140374078`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140374112`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140374123`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140374112`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140374123`
- `api-ms-win-core-handle-l1-1-0!DuplicateHandle` at `0x1403740b7`
- `api-ms-win-core-handle-l1-1-0!DuplicateHandle` at `0x1403740f8`
- `api-ms-win-core-handle-l1-1-0!DuplicateHandle` at `0x1403740b7`
- `api-ms-win-core-handle-l1-1-0!DuplicateHandle` at `0x1403740f8`
- `api-ms-win-security-base-l1-1-0!DuplicateTokenEx` at `0x140373f69`
- `api-ms-win-security-base-l1-1-0!DuplicateTokenEx` at `0x140373f69`
- `USERENV!CreateEnvironmentBlock` at `0x140373f97`
- `USERENV!CreateEnvironmentBlock` at `0x140373f97`
- `USERENV!DestroyEnvironmentBlock` at `0x140374133`
- `USERENV!DestroyEnvironmentBlock` at `0x140374133`

## string_xrefs

- `0x1403741a5`: `C:\__w\1\s\src\orchestrator\system\windows\common\ProcessHelpers.cpp`
- `0x1403741b7`: `C:\__w\1\s\src\orchestrator\system\windows\common\ProcessHelpers.cpp`
- `0x1403741c9`: `C:\__w\1\s\src\orchestrator\system\windows\common\ProcessHelpers.cpp`
- `0x1403741de`: `C:\__w\1\s\src\orchestrator\system\windows\common\ProcessHelpers.cpp`
- `0x1403741f0`: `C:\__w\1\s\src\orchestrator\system\windows\common\ProcessHelpers.cpp`
- `0x140374202`: `C:\__w\1\s\src\orchestrator\system\windows\common\ProcessHelpers.cpp`

## pseudocode

```c
LPHANDLE __fastcall Windows::ProcessHelpers::CreateProcessAsUserToken(
        LPHANDLE lpTargetHandle,
        HANDLE *a2,
        WCHAR *a3,
        WCHAR *a4)
{
  char *v8; // rsi
  void **v9; // rdi
  const char *v10; // r9
  void *v11; // rdx
  const char *v12; // r9
  WCHAR *v13; // rdx
  __int64 *v14; // r8
  int v15; // eax
  void *v16; // rcx
  LPWSTR v17; // rbx
  const char *v18; // r9
  HANDLE CurrentProcess; // rdi
  HANDLE v20; // rax
  const char *v21; // r9
  HANDLE v22; // rdi
  HANDLE v23; // rax
  __int64 v24; // rdx
  const char *v25; // r9
  __int64 v26; // rdx
  int TokenType; // [rsp+20h] [rbp-E0h]
  LPCWSTR lpApplicationName; // [rsp+68h] [rbp-98h] BYREF
  LPWSTR lpCommandLine[6]; // [rsp+70h] [rbp-90h] BYREF
  struct _STARTUPINFOW StartupInfo; // [rsp+A0h] [rbp-60h] BYREF
  LPVOID Environment; // [rsp+110h] [rbp+10h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+168h] [rbp+68h]

  lpCommandLine[3] = (LPWSTR)lpTargetHandle;
  lpCommandLine[4] = a3;
  lpCommandLine[5] = a4;
  v8 = (char *)operator new(0x18u);
  lpCommandLine[0] = (LPWSTR)v8;
  *(_OWORD *)v8 = 0;
  *((_DWORD *)v8 + 2) = 1;
  *((_DWORD *)v8 + 3) = 1;
  *(_QWORD *)v8 = &std::_Ref_count_obj2<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>>>::`vftable';
  v9 = (void **)(v8 + 16);
  *((_QWORD *)v8 + 2) = 0;
  lpCommandLine[1] = (LPWSTR)(v8 + 16);
  lpCommandLine[2] = (LPWSTR)v8;
  if ( !DuplicateTokenEx(*a2, 0xBu, 0, SecurityImpersonation, TokenPrimary, (PHANDLE)v8 + 2) )
    wil::details::in1diag3::Throw_GetLastError(
      retaddr,
      (void *)0x16,
      (unsigned int)"C:\\__w\\1\\s\\src\\orchestrator\\system\\windows\\common\\ProcessHelpers.cpp",
      v10);
  Environment = 0;
  if ( v8 == (char *)-16LL )
    v11 = 0;
  else
    v11 = *v9;
  Environment = 0;
  if ( !CreateEnvironmentBlock(&Environment, v11, 0) )
    wil::details::in1diag3::Throw_GetLastError(
      retaddr,
      (void *)0x1C,
      (unsigned int)"C:\\__w\\1\\s\\src\\orchestrator\\system\\windows\\common\\ProcessHelpers.cpp",
      v12);
  lpApplicationName = 0;
  v13 = a3;
  if ( *((_QWORD *)a3 + 3) > 7u )
    v13 = *(WCHAR **)a3;
  wil::ExpandEnvironmentStringsW<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<wchar_t *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>>,256>(
    &lpApplicationName,
    v13);
  memset(&StartupInfo, 0, sizeof(StartupInfo));
  StartupInfo.cb = 104;
  StartupInfo.lpDesktop = L"WinSta0\\Default";
  lpCommandLine[0] = 0;
  v14 = (__int64 *)a4;
  if ( *((_QWORD *)a4 + 3) > 7u )
    v14 = *(__int64 **)a4;
  v15 = wil::str_printf_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<wchar_t *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>>>(
          lpCommandLine,
          L"%ws",
          v14);
  if ( v15 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x25,
      (unsigned int)"C:\\__w\\1\\s\\src\\orchestrator\\system\\windows\\common\\ProcessHelpers.cpp",
      (const char *)(unsigned int)v15,
      TokenType);
  *(_OWORD *)lpTargetHandle = 0;
  lpTargetHandle[2] = 0;
  if ( v8 == (char *)-16LL )
    v16 = 0;
  else
    v16 = *v9;
  v17 = lpCommandLine[0];
  if ( !CreateProcessAsUserW(
          v16,
          lpApplicationName,
          lpCommandLine[0],
          0,
          0,
          0,
          0x400u,
          Environment,
          0,
          &StartupInfo,
          (LPPROCESS_INFORMATION)lpTargetHandle) )
    wil::details::in1diag3::Throw_GetLastError(
      retaddr,
      (void *)0x33,
      (unsigned int)"C:\\__w\\1\\s\\src\\orchestrator\\system\\windows\\common\\ProcessHelpers.cpp",
      v18);
  CurrentProcess = GetCurrentProcess();
  v20 = GetCurrentProcess();
  if ( !DuplicateHandle(v20, *lpTargetHandle, CurrentProcess, lpTargetHandle, 0, 0, 2u) )
    wil::details::in1diag3::Throw_GetLastError(
      retaddr,
      (void *)0x3C,
      (unsigned int)"C:\\__w\\1\\s\\src\\orchestrator\\system\\windows\\common\\ProcessHelpers.cpp",
      v21);
  v22 = GetCurrentProcess();
  v23 = GetCurrentProcess();
  if ( !DuplicateHandle(v23, lpTargetHandle[1], v22, lpTargetHandle + 1, 0, 0, 2u) )
    wil::details::in1diag3::Throw_GetLastError(
      retaddr,
      (void *)0x45,
      (unsigned int)"C:\\__w\\1\\s\\src\\orchestrator\\system\\windows\\common\\ProcessHelpers.cpp",
      v25);
  if ( v17 )
    CoTaskMemFree(v17);
  if ( lpApplicationName )
    CoTaskMemFree((LPVOID)lpApplicationName);
  if ( Environment )
    DestroyEnvironmentBlock(Environment);
  if ( _InterlockedExchangeAdd((volatile signed __int32 *)v8 + 2, 0xFFFFFFFF) == 1 )
  {
    (**(void (__fastcall ***)(void *))v8)(v8);
    if ( _InterlockedExchangeAdd((volatile signed __int32 *)v8 + 3, 0xFFFFFFFF) == 1 )
      (*(void (__fastcall **)(char *))(*(_QWORD *)v8 + 8LL))(v8);
  }
  std::wstring::~wstring(a3, v24);
  std::wstring::~wstring(a4, v26);
  return lpTargetHandle;
}

```

## disassembly

```asm
0x140373ec0  push    rbp
0x140373ec2  push    rbx
0x140373ec3  push    rsi
0x140373ec4  push    rdi
0x140373ec5  push    r12
0x140373ec7  push    r13
0x140373ec9  push    r14
0x140373ecb  push    r15
0x140373ecd  lea     rbp, [rsp-28h]
0x140373ed2  sub     rsp, 128h
0x140373ed9  mov     rax, cs:__security_cookie
0x140373ee0  xor     rax, rsp
0x140373ee3  mov     [rbp+60h+var_48], rax
0x140373ee7  mov     r12, r9
0x140373eea  mov     r15, r8
0x140373eed  mov     rbx, rdx
0x140373ef0  mov     r14, rcx
0x140373ef3  mov     [rbp+60h+var_D8], rcx
0x140373ef7  mov     [rbp+60h+var_D0], r8
0x140373efb  mov     [rbp+60h+var_C8], r9
0x140373eff  xor     r13d, r13d
0x140373f02  mov     [rsp+160h+var_100], r13d
0x140373f07  xorps   xmm0, xmm0
0x140373f0a  movdqu  [rsp+160h+var_E8], xmm0
0x140373f10  lea     ecx, [r13+18h]; Size
0x140373f14  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x140373f19  mov     rsi, rax
0x140373f1c  mov     [rsp+160h+lpCommandLine], rax
0x140373f21  xorps   xmm0, xmm0
0x140373f24  movups  xmmword ptr [rax], xmm0
0x140373f27  lea     ecx, [r13+1]
0x140373f2b  mov     [rax+8], ecx
0x140373f2e  mov     [rax+0Ch], ecx
0x140373f31  lea     rax, ??_7?$_Ref_count_obj2@V?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@@std@@6B@; const std::_Ref_count_obj2<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>>>::`vftable'
0x140373f38  mov     [rsi], rax
0x140373f3b  lea     rdi, [rsi+10h]
0x140373f3f  mov     [rdi], r13
0x140373f42  mov     [rsp+160h+var_100], 4
0x140373f4a  mov     qword ptr [rsp+160h+var_E8], rdi
0x140373f4f  mov     qword ptr [rbp+60h+var_E8+8], rsi
0x140373f53  mov     [rsp+160h+phNewToken], rdi; phNewToken
0x140373f58  mov     [rsp+160h+TokenType], ecx; int
0x140373f5c  lea     r9d, [r13+2]; ImpersonationLevel
0x140373f60  xor     r8d, r8d; lpTokenAttributes
0x140373f63  lea     edx, [rcx+0Ah]; dwDesiredAccess
0x140373f66  mov     rcx, [rbx]; hExistingToken
0x140373f69  call    cs:__imp_DuplicateTokenEx
0x140373f6f  mov     rcx, [rbp+68h]; this
0x140373f73  test    eax, eax
0x140373f75  jz      loc_1403741B7
0x140373f7b  mov     [rbp+60h+Environment], r13
0x140373f7f  test    rdi, rdi
0x140373f82  jz      short loc_140373F89
0x140373f84  mov     rdx, [rdi]
0x140373f87  jmp     short loc_140373F8C
0x140373f89  mov     rdx, r13; hToken
0x140373f8c  mov     [rbp+60h+Environment], r13
0x140373f90  xor     r8d, r8d; bInherit
0x140373f93  lea     rcx, [rbp+60h+Environment]; lpEnvironment
0x140373f97  call    cs:__imp_CreateEnvironmentBlock
0x140373f9d  mov     rcx, [rbp+68h]; this
0x140373fa1  test    eax, eax
0x140373fa3  jz      loc_1403741C9
0x140373fa9  mov     [rsp+160h+lpApplicationName], r13
0x140373fae  mov     rdx, r15
0x140373fb1  cmp     qword ptr [r15+18h], 7
0x140373fb6  jbe     short loc_140373FBB
0x140373fb8  mov     rdx, [r15]
0x140373fbb  lea     rcx, [rsp+160h+lpApplicationName]
0x140373fc0  call    ??$ExpandEnvironmentStringsW@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEA_WP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEA_WPEA_W$0A@$$T@details@wil@@@details@wil@@@wil@@$0BAA@@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEA_WP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEA_WPEA_W$0A@$$T@details@wil@@@details@wil@@@0@PEB_W@Z; wil::ExpandEnvironmentStringsW<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<wchar_t *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>>,256>(wchar_t const *)
0x140373fc5  nop
0x140373fc6  mov     ebx, 68h ; 'h'
0x140373fcb  mov     r8d, ebx; Size
0x140373fce  xor     edx, edx; Val
0x140373fd0  lea     rcx, [rbp+60h+StartupInfo]; void *
0x140373fd4  call    memset
0x140373fd9  mov     [rbp+60h+StartupInfo.cb], ebx
0x140373fdc  lea     rax, aWinsta0Default; "WinSta0\\Default"
0x140373fe3  mov     [rbp+60h+StartupInfo.lpDesktop], rax
0x140373fe7  mov     [rsp+160h+lpCommandLine], r13
0x140373fec  mov     r8, r12
0x140373fef  cmp     qword ptr [r12+18h], 7
0x140373ff5  jbe     short loc_140373FFB
0x140373ff7  mov     r8, [r12]
0x140373ffb  lea     rdx, aWs; "%ws"
0x140374002  lea     rcx, [rsp+160h+lpCommandLine]
0x140374007  call    ??$str_printf_nothrow@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEA_WP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEA_WPEA_W$0A@$$T@details@wil@@@details@wil@@@wil@@@wil@@YAJAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEA_WP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEA_WPEA_W$0A@$$T@details@wil@@@details@wil@@@0@PEB_WZZ; wil::str_printf_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<wchar_t *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>>>(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<wchar_t *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>> &,wchar_t const *,...)
0x14037400c  mov     rcx, [rbp+68h]; this
0x140374010  test    eax, eax
0x140374012  js      loc_1403741DB
0x140374018  xorps   xmm0, xmm0
0x14037401b  xor     eax, eax
0x14037401d  movups  xmmword ptr [r14], xmm0
0x140374021  mov     [r14+10h], rax
0x140374025  mov     [rsp+160h+var_100], 5
0x14037402d  mov     rax, [rbp+60h+Environment]
0x140374031  test    rdi, rdi
0x140374034  jz      short loc_14037403B
0x140374036  mov     rcx, [rdi]
0x140374039  jmp     short loc_14037403E
0x14037403b  mov     rcx, r13; hToken
0x14037403e  mov     [rsp+160h+lpProcessInformation], r14; lpProcessInformation
0x140374043  lea     rdx, [rbp+60h+StartupInfo]
0x140374047  mov     [rsp+160h+lpStartupInfo], rdx; lpStartupInfo
0x14037404c  mov     [rsp+160h+lpCurrentDirectory], r13; lpCurrentDirectory
0x140374051  mov     [rsp+160h+lpEnvironment], rax; lpEnvironment
0x140374056  mov     [rsp+160h+dwCreationFlags], 400h; dwCreationFlags
0x14037405e  mov     dword ptr [rsp+160h+phNewToken], r13d; bInheritHandles
0x140374063  mov     qword ptr [rsp+160h+TokenType], r13; lpThreadAttributes
0x140374068  xor     r9d, r9d; lpProcessAttributes
0x14037406b  mov     rbx, [rsp+160h+lpCommandLine]
0x140374070  mov     r8, rbx; lpCommandLine
0x140374073  mov     rdx, [rsp+160h+lpApplicationName]; lpApplicationName
0x140374078  call    cs:__imp_CreateProcessAsUserW
0x14037407e  mov     rcx, [rbp+68h]; this
0x140374082  test    eax, eax
0x140374084  jz      loc_1403741F0
0x14037408a  call    cs:__imp_GetCurrentProcess
0x140374090  mov     rdi, rax
0x140374093  call    cs:__imp_GetCurrentProcess
0x140374099  mov     [rsp+160h+dwCreationFlags], 2; dwOptions
0x1403740a1  mov     dword ptr [rsp+160h+phNewToken], r13d; bInheritHandle
0x1403740a6  mov     [rsp+160h+TokenType], r13d; dwDesiredAccess
0x1403740ab  mov     r9, r14; lpTargetHandle
0x1403740ae  mov     r8, rdi; hTargetProcessHandle
0x1403740b1  mov     rdx, [r14]; hSourceHandle
0x1403740b4  mov     rcx, rax; hSourceProcessHandle
0x1403740b7  call    cs:__imp_DuplicateHandle
0x1403740bd  mov     rcx, [rbp+68h]; this
0x1403740c1  test    eax, eax
0x1403740c3  jz      loc_140374202
0x1403740c9  call    cs:__imp_GetCurrentProcess
0x1403740cf  mov     rdi, rax
0x1403740d2  call    cs:__imp_GetCurrentProcess
0x1403740d8  mov     [rsp+160h+dwCreationFlags], 2; dwOptions
0x1403740e0  mov     dword ptr [rsp+160h+phNewToken], r13d; bInheritHandle
0x1403740e5  mov     [rsp+160h+TokenType], r13d; dwDesiredAccess
0x1403740ea  lea     r9, [r14+8]; lpTargetHandle
0x1403740ee  mov     r8, rdi; hTargetProcessHandle
0x1403740f1  mov     rdx, [r14+8]; hSourceHandle
0x1403740f5  mov     rcx, rax; hSourceProcessHandle
0x1403740f8  call    cs:__imp_DuplicateHandle
0x1403740fe  mov     rcx, [rbp+68h]; this
0x140374102  test    eax, eax
0x140374104  jz      loc_1403741A5
0x14037410a  test    rbx, rbx
0x14037410d  jz      short loc_140374119
0x14037410f  mov     rcx, rbx; pv
0x140374112  call    cs:__imp_CoTaskMemFree
0x140374118  nop
0x140374119  mov     rcx, [rsp+160h+lpApplicationName]; pv
0x14037411e  test    rcx, rcx
0x140374121  jz      short loc_14037412A
0x140374123  call    cs:__imp_CoTaskMemFree
0x140374129  nop
0x14037412a  mov     rcx, [rbp+60h+Environment]; lpEnvironment
0x14037412e  test    rcx, rcx
0x140374131  jz      short loc_14037413A
0x140374133  call    cs:__imp_DestroyEnvironmentBlock
0x140374139  nop
0x14037413a  or      ebx, 0FFFFFFFFh
0x14037413d  mov     eax, ebx
0x14037413f  lock xadd [rsi+8], eax
0x140374144  add     eax, ebx
0x140374146  jnz     short loc_140374171
0x140374148  mov     rax, [rsi]
0x14037414b  mov     rcx, rsi
0x14037414e  mov     rax, [rax]
0x140374151  call    _guard_dispatch_icall
0x140374156  mov     eax, ebx
0x140374158  lock xadd [rsi+0Ch], eax
0x14037415d  add     eax, ebx
0x14037415f  jnz     short loc_140374171
0x140374161  mov     rdx, [rsi]
0x140374164  mov     rcx, rsi
0x140374167  mov     rax, [rdx+8]
0x14037416b  call    _guard_dispatch_icall
0x140374170  nop
0x140374171  mov     rcx, r15
0x140374174  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x140374179  nop
0x14037417a  mov     rcx, r12
0x14037417d  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x140374182  mov     rax, r14
0x140374185  mov     rcx, [rbp+60h+var_48]
0x140374189  xor     rcx, rsp; StackCookie
0x14037418c  call    __security_check_cookie
0x140374191  add     rsp, 128h
0x140374198  pop     r15
0x14037419a  pop     r14
0x14037419c  pop     r13
0x14037419e  pop     r12
0x1403741a0  pop     rdi
0x1403741a1  pop     rsi
0x1403741a2  pop     rbx
0x1403741a3  pop     rbp
0x1403741a4  retn
0x1403741a5  lea     r8, aCW1SSrcOrchest_94; "C:\\__w\\1\\s\\src\\orchestrator\\syste"...
0x1403741ac  mov     edx, 45h ; 'E'; void *
0x1403741b1  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
0x1403741b7  lea     r8, aCW1SSrcOrchest_94; "C:\\__w\\1\\s\\src\\orchestrator\\syste"...
0x1403741be  mov     edx, 16h; void *
0x1403741c3  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
0x1403741c9  lea     r8, aCW1SSrcOrchest_94; "C:\\__w\\1\\s\\src\\orchestrator\\syste"...
0x1403741d0  mov     edx, 1Ch; void *
0x1403741d5  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
0x1403741db  mov     r9d, eax; char *
0x1403741de  lea     r8, aCW1SSrcOrchest_94; "C:\\__w\\1\\s\\src\\orchestrator\\syste"...
0x1403741e5  mov     edx, 25h ; '%'; void *
0x1403741ea  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1403741f0  lea     r8, aCW1SSrcOrchest_94; "C:\\__w\\1\\s\\src\\orchestrator\\syste"...
0x1403741f7  mov     edx, 33h ; '3'; void *
0x1403741fc  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
0x140374202  lea     r8, aCW1SSrcOrchest_94; "C:\\__w\\1\\s\\src\\orchestrator\\syste"...
0x140374209  mov     edx, 3Ch ; '<'; void *
0x14037420e  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
```
