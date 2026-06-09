# PostCreateProcessAppXActivation

- ea: `0x18008d9c0`
- end: `0x18008dd93`
- name: `PostCreateProcessAppXActivation`
- size: `979`
- prototype: `__int64 __fastcall(void *)`
- caller_count: `0`
- callee_count: `18`
- tags: `authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callees

- `0x18000b5c0`
- `0x18000cbc0`
- `0x180011328`
- `0x180027ce8`
- `0x18002c428`
- `0x180037a80`
- `0x180039340`
- `0x180044514`
- `0x180056228`
- `0x18005ae90`
- `0x18005ba40`
- `0x18005ed40`
- `0x18007638c`
- `0x1800763a8`
- `0x18008d218`
- `0x18008d78c`
- `0x18008d9c0`
- `0x180094d14`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!OpenThread` at `0x18008da1d`
- `api-ms-win-core-processthreads-l1-1-0!OpenThread` at `0x18008da1d`
- `ntdll!NtTerminateProcess` at `0x18008dd6f`
- `ntdll!NtTerminateProcess` at `0x18008dd6f`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x18008d9f5`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x18008d9f5`
- `RMCLIENT!HamInitializeActivityAutoRestartProperties` at `0x18008db88`
- `RMCLIENT!HamInitializeActivityAutoRestartProperties` at `0x18008db88`
- `RMCLIENT!HamPopulateActivityProperties` at `0x18008daa4`
- `RMCLIENT!HamPopulateActivityProperties` at `0x18008daa4`
- `RMCLIENT!HamCreateAutoRestartActivity` at `0x18008dbac`
- `RMCLIENT!HamCreateAutoRestartActivity` at `0x18008dbac`
- `ext-ms-win-com-psmregister-l1-1-0!PsmRegisterApplicationProcess` at `0x18008dc14`
- `ext-ms-win-com-psmregister-l1-1-0!PsmRegisterApplicationProcess` at `0x18008dc14`
- `ext-ms-win-desktopappx-l1-2-1!CAMHandlePackagedProcessLaunch` at `0x18008dc31`
- `ext-ms-win-desktopappx-l1-2-1!CAMHandlePackagedProcessLaunch` at `0x18008dc31`

## string_xrefs

- `0x18008dab9`: `onecoreuap\base\appmodel\execmodel\modern\activationmanager\extensionlib\activationextensions.cpp`
- `0x18008dbc1`: `onecoreuap\base\appmodel\execmodel\modern\activationmanager\extensionlib\activationextensions.cpp`
- `0x18008dc48`: `onecoreuap\base\appmodel\execmodel\modern\activationmanager\extensionlib\activationextensions.cpp`
- `0x18008dcf4`: `onecoreuap\base\appmodel\execmodel\modern\activationmanager\extensionlib\activationextensions.cpp`
- `0x18008dd06`: `onecoreuap\base\appmodel\execmodel\modern\activationmanager\extensionlib\activationextensions.cpp`
- `0x18008dd1b`: `onecoreuap\base\appmodel\execmodel\modern\activationmanager\extensionlib\activationextensions.cpp`
- `0x18008dd30`: `onecoreuap\base\appmodel\execmodel\modern\activationmanager\extensionlib\activationextensions.cpp`
- `0x18008dd44`: `onecoreuap\base\appmodel\execmodel\modern\activationmanager\extensionlib\activationextensions.cpp`
- `0x18008dd58`: `onecoreuap\base\appmodel\execmodel\modern\activationmanager\extensionlib\activationextensions.cpp`
- `0x18008dd80`: `onecoreuap\base\appmodel\execmodel\modern\activationmanager\extensionlib\activationextensions.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall PostCreateProcessAppXActivation(void *a1, __int64 a2, struct _PROCESS_INFORMATION *a3)
{
  HANDLE v6; // rax
  const char *v7; // r9
  void *v8; // rdi
  HANDLE v9; // rax
  __int64 v10; // rdx
  const char *v11; // r9
  int ProcessHostInfo; // eax
  int v13; // eax
  unsigned int v14; // ebx
  const char *v15; // r9
  __int64 result; // rax
  void *v17; // rbx
  int Instance; // eax
  int started; // eax
  int v20; // eax
  int restarted; // eax
  unsigned int v22; // ebx
  NTSTATUS v23; // eax
  unsigned int v24; // ebx
  int v25; // eax
  unsigned int v26; // ebx
  int v27; // [rsp+20h] [rbp-418h] BYREF
  HANDLE hHandle; // [rsp+28h] [rbp-410h] BYREF
  HANDLE v29; // [rsp+30h] [rbp-408h] BYREF
  HANDLE v30; // [rsp+38h] [rbp-400h] BYREF
  int v31; // [rsp+40h] [rbp-3F8h] BYREF
  int v32; // [rsp+44h] [rbp-3F4h]
  int v33; // [rsp+48h] [rbp-3F0h]
  _BYTE v34[560]; // [rsp+1D0h] [rbp-268h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+438h] [rbp+0h]

  v6 = OpenProcess(0x100501u, 0, a3->dwProcessId);
  try
  {
    v8 = v6;
    if ( !v6 )
      wil::details::in1diag3::_Throw_GetLastError(
        retaddr,
        (void *)0xE7,
        (unsigned int)"onecoreuap\\base\\appmodel\\execmodel\\modern\\activationmanager\\extensionlib\\activationextensions.cpp",
        v7);
    v30 = v6;
    v9 = OpenThread(2u, 0, a3->dwThreadId);
    if ( !v9 )
      wil::details::in1diag3::_Throw_GetLastError(
        retaddr,
        (void *)0xEA,
        (unsigned int)"onecoreuap\\base\\appmodel\\execmodel\\modern\\activationmanager\\extensionlib\\activationextensions.cpp",
        v11);
    v29 = v9;
    if ( *(_DWORD *)(a2 + 36) )
    {
      LOBYTE(v10) = 0;
      wil::init_once__lambda_46ff534c55db9e22fcff926e35a20093___(retaddr, v10);
      memset_0(v34, 0, 0x228u);
      ProcessHostInfo = CempGetProcessHostInfo(v8, v34);
      if ( ProcessHostInfo < 0 )
        wil::details::in1diag3::_Throw_NtStatus(
          retaddr,
          (void *)0xFE,
          (unsigned int)"onecoreuap\\base\\appmodel\\execmodel\\modern\\activationmanager\\extensionlib\\activationextensions.cpp",
          (const char *)(unsigned int)ProcessHostInfo,
          v27);
      memset_0(&v31, 0, 0x188u);
      v13 = HamPopulateActivityProperties(L"AppExecutionAlias", L"UiModernForeground", &v31);
      if ( v13 < 0 )
      {
        v14 = wil::details::in1diag3::Return_NtStatus(
                retaddr,
                (void *)0x101,
                (unsigned int)"onecoreuap\\base\\appmodel\\execmodel\\modern\\activationmanager\\extensionlib\\activationextensions.cpp",
                (const char *)(unsigned int)v13,
                v27);
        wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&v29);
        wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&v30);
        return v14;
      }
      v31 |= 0x400u;
      v32 |= 4u;
      v33 |= 4u;
      hHandle = 0;
      v17 = s_hamContext;
      Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&hHandle);
      Instance = HamActivityWrapper::CreateInstance((struct HamActivityWrapper **)&hHandle, v17, 0);
      if ( Instance < 0 )
        wil::details::in1diag3::_Throw_NtStatus(
          retaddr,
          (void *)0x107,
          (unsigned int)"onecoreuap\\base\\appmodel\\execmodel\\modern\\activationmanager\\extensionlib\\activationextensions.cpp",
          (const char *)(unsigned int)Instance,
          v27);
      started = HamActivityWrapper::StartAsync(hHandle, v34, &v31, 0);
      if ( started < 0 )
        wil::details::in1diag3::_Throw_NtStatus(
          retaddr,
          (void *)0x109,
          (unsigned int)"onecoreuap\\base\\appmodel\\execmodel\\modern\\activationmanager\\extensionlib\\activationextensions.cpp",
          (const char *)(unsigned int)started,
          v27);
      v20 = HamActivityWrapper::WaitForStarted((HamActivityWrapper *)hHandle, 0x1388u);
      if ( v20 < 0 )
        wil::details::in1diag3::_Throw_NtStatus(
          retaddr,
          (void *)0x10A,
          (unsigned int)"onecoreuap\\base\\appmodel\\execmodel\\modern\\activationmanager\\extensionlib\\activationextensions.cpp",
          (const char *)(unsigned int)v20,
          v27);
      v27 = 0;
      HamInitializeActivityAutoRestartProperties(&v27);
      v27 |= 1u;
      restarted = HamCreateAutoRestartActivity(s_hamContext, v34, &v31, &v27);
      if ( restarted < 0 )
      {
        v22 = wil::details::in1diag3::Return_NtStatus(
                retaddr,
                (void *)0x110,
                (unsigned int)"onecoreuap\\base\\appmodel\\execmodel\\modern\\activationmanager\\extensionlib\\activationextensions.cpp",
                (const char *)(unsigned int)restarted,
                v27);
        Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&hHandle);
        wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&v29);
        wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&v30);
        return v22;
      }
      Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&hHandle);
    }
    v23 = PsmRegisterApplicationProcess(v8, *(_DWORD *)(a2 + 8) != 0 ? 3 : 1);
    v24 = v23;
    if ( v23 < 0 )
    {
      NtTerminateProcess(v8, v23);
      wil::details::in1diag3::_Throw_NtStatus(
        retaddr,
        (void *)0x11C,
        (unsigned int)"onecoreuap\\base\\appmodel\\execmodel\\modern\\activationmanager\\extensionlib\\activationextensions.cpp",
        (const char *)v24,
        v27);
    }
    if ( (unsigned __int8)IsCAMHandlePackagedProcessLaunchPresent()
      && (v25 = CAMHandlePackagedProcessLaunch(a3->dwProcessId), v26 = v25, v25 < 0) )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x126,
        (unsigned int)"onecoreuap\\base\\appmodel\\execmodel\\modern\\activationmanager\\extensionlib\\activationextensions.cpp",
        (const char *)(unsigned int)v25,
        v27);
      wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&v29);
      wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&v30);
      result = v26;
    }
    else
    {
      if ( *(_DWORD *)(a2 + 8) )
      {
        hHandle = 0;
        wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::reset(
          &hHandle,
          0);
        LaunchDebugger(*(const unsigned __int16 **)(a2 + 16), a3, a1, &hHandle);
        WaitForDebuggerWorkAround(hHandle);
        wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&hHandle);
      }
      wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&v29);
      wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&v30);
      result = 0;
    }
  }
  catch ( ... )
  {
    return (unsigned int)wil::details::in1diag3::Return_CaughtException(
                           retaddr,
                           (void *)0x13C,
                           (unsigned int)"onecoreuap\\base\\appmodel\\execmodel\\modern\\activationmanager\\extensionlib\\"
                                         "activationextensions.cpp",
                           v15);
  }
  return result;
}

```

## disassembly

```asm
0x18008d9c0  push    rbx
0x18008d9c2  push    rsi
0x18008d9c3  push    rdi
0x18008d9c4  push    r14
0x18008d9c6  push    r15
0x18008d9c8  sub     rsp, 410h
0x18008d9cf  mov     rax, cs:__security_cookie
0x18008d9d6  xor     rax, rsp
0x18008d9d9  mov     [rsp+438h+var_38], rax
0x18008d9e1  mov     r14, r8
0x18008d9e4  mov     rsi, rdx
0x18008d9e7  mov     r15, rcx
0x18008d9ea  mov     r8d, [r8+10h]; dwProcessId
0x18008d9ee  xor     edx, edx; bInheritHandle
0x18008d9f0  mov     ecx, 100501h; dwDesiredAccess
0x18008d9f5  call    cs:__imp_OpenProcess
0x18008d9fb  mov     rdi, rax
0x18008d9fe  mov     rcx, [rsp+438h]; this
0x18008da06  test    rax, rax
0x18008da09  jz      loc_18008DCF4
0x18008da0f  mov     [rsp+438h+var_400], rdi
0x18008da14  mov     r8d, [r14+14h]; dwThreadId
0x18008da18  xor     edx, edx; bInheritHandle
0x18008da1a  lea     ecx, [rdx+2]; dwDesiredAccess
0x18008da1d  call    cs:__imp_OpenThread
0x18008da23  mov     rcx, [rsp+438h]; this
0x18008da2b  test    rax, rax
0x18008da2e  jz      loc_18008DD06
0x18008da34  mov     [rsp+438h+var_408], rax
0x18008da39  cmp     dword ptr [rsi+24h], 0
0x18008da3d  jz      loc_18008DC05
0x18008da43  xor     dl, dl
0x18008da45  call    wil__init_once__lambda_46ff534c55db9e22fcff926e35a20093___
0x18008da4a  xor     edx, edx; Val
0x18008da4c  mov     r8d, 228h; Size
0x18008da52  lea     rcx, [rsp+438h+var_268]; void *
0x18008da5a  call    memset_0
0x18008da5f  lea     rdx, [rsp+438h+var_268]
0x18008da67  mov     rcx, rdi
0x18008da6a  call    CempGetProcessHostInfo
0x18008da6f  mov     rcx, [rsp+438h]; this
0x18008da77  test    eax, eax
0x18008da79  js      loc_18008DD18
0x18008da7f  xor     edx, edx; Val
0x18008da81  mov     r8d, 188h; Size
0x18008da87  lea     rcx, [rsp+438h+var_3F8]; void *
0x18008da8c  call    memset_0
0x18008da91  lea     r8, [rsp+438h+var_3F8]
0x18008da96  lea     rdx, aUimodernforegr; "UiModernForeground"
0x18008da9d  lea     rcx, aAppexecutional; "AppExecutionAlias"
0x18008daa4  call    cs:__imp_HamPopulateActivityProperties
0x18008daaa  test    eax, eax
0x18008daac  jns     short loc_18008DAE8
0x18008daae  mov     rcx, [rsp+438h]; this
0x18008dab6  mov     r9d, eax; char *
0x18008dab9  lea     r8, aOnecoreuapBase; "onecoreuap\\base\\appmodel\\execmodel\\"...
0x18008dac0  mov     edx, 101h; void *
0x18008dac5  call    ?Return_NtStatus@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Return_NtStatus(void *,uint,char const *,long)
0x18008daca  mov     ebx, eax
0x18008dacc  lea     rcx, [rsp+438h+var_408]
0x18008dad1  call    ??1?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x18008dad6  nop
0x18008dad7  lea     rcx, [rsp+438h+var_400]
0x18008dadc  call    ??1?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x18008dae1  mov     eax, ebx
0x18008dae3  jmp     loc_18008DCD5
0x18008dae8  bts     [rsp+438h+var_3F8], 0Ah
0x18008daee  or      [rsp+438h+var_3F4], 4
0x18008daf3  or      [rsp+438h+var_3F0], 4
0x18008daf8  mov     [rsp+438h+hHandle], 0
0x18008db01  mov     rbx, cs:?s_hamContext@@3V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AJPEAX@Z$1?HamDisconnectFromServer@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@wil@@A; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,long (*)(void *),&HamDisconnectFromServer(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>> s_hamContext
0x18008db08  lea     rcx, [rsp+438h+hHandle]
0x18008db0d  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x18008db12  xor     r8d, r8d; unsigned __int64
0x18008db15  mov     rdx, rbx; void *
0x18008db18  lea     rcx, [rsp+438h+hHandle]; struct HamActivityWrapper **
0x18008db1d  call    ?CreateInstance@HamActivityWrapper@@SAJPEAPEAV1@PEAX_K@Z; HamActivityWrapper::CreateInstance(HamActivityWrapper * *,void *,unsigned __int64)
0x18008db22  mov     rcx, [rsp+438h]; this
0x18008db2a  test    eax, eax
0x18008db2c  js      loc_18008DD2D
0x18008db32  xor     r9d, r9d
0x18008db35  lea     r8, [rsp+438h+var_3F8]
0x18008db3a  lea     rdx, [rsp+438h+var_268]
0x18008db42  mov     rcx, [rsp+438h+hHandle]
0x18008db47  call    ?StartAsync@HamActivityWrapper@@QEAAJPEAU_RM_PSM_HOST_INFO@@PEAU_HAM_ACTIVITY_PROPERTIES@@W4_HAM_ACTIVITY_START_TYPE@@@Z; HamActivityWrapper::StartAsync(_RM_PSM_HOST_INFO *,_HAM_ACTIVITY_PROPERTIES *,_HAM_ACTIVITY_START_TYPE)
0x18008db4c  mov     rcx, [rsp+438h]; this
0x18008db54  test    eax, eax
0x18008db56  js      loc_18008DD41
0x18008db5c  mov     edx, 1388h; unsigned int
0x18008db61  mov     rcx, [rsp+438h+hHandle]; this
0x18008db66  call    ?WaitForStarted@HamActivityWrapper@@QEAAJK@Z; HamActivityWrapper::WaitForStarted(ulong)
0x18008db6b  mov     rcx, [rsp+438h]; this
0x18008db73  test    eax, eax
0x18008db75  js      loc_18008DD55
0x18008db7b  mov     [rsp+438h+var_418], 0; int
0x18008db83  lea     rcx, [rsp+438h+var_418]
0x18008db88  call    cs:__imp_HamInitializeActivityAutoRestartProperties
0x18008db8e  or      [rsp+438h+var_418], 1
0x18008db93  lea     r9, [rsp+438h+var_418]
0x18008db98  lea     r8, [rsp+438h+var_3F8]
0x18008db9d  lea     rdx, [rsp+438h+var_268]
0x18008dba5  mov     rcx, cs:?s_hamContext@@3V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AJPEAX@Z$1?HamDisconnectFromServer@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@wil@@A; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,long (*)(void *),&HamDisconnectFromServer(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>> s_hamContext
0x18008dbac  call    cs:__imp_HamCreateAutoRestartActivity
0x18008dbb2  test    eax, eax
0x18008dbb4  jns     short loc_18008DBFB
0x18008dbb6  mov     rcx, [rsp+438h]; this
0x18008dbbe  mov     r9d, eax; char *
0x18008dbc1  lea     r8, aOnecoreuapBase; "onecoreuap\\base\\appmodel\\execmodel\\"...
0x18008dbc8  mov     edx, 110h; void *
0x18008dbcd  call    ?Return_NtStatus@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Return_NtStatus(void *,uint,char const *,long)
0x18008dbd2  mov     ebx, eax
0x18008dbd4  lea     rcx, [rsp+438h+hHandle]
0x18008dbd9  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x18008dbde  nop
0x18008dbdf  lea     rcx, [rsp+438h+var_408]
0x18008dbe4  call    ??1?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x18008dbe9  nop
0x18008dbea  lea     rcx, [rsp+438h+var_400]
0x18008dbef  call    ??1?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x18008dbf4  mov     eax, ebx
0x18008dbf6  jmp     loc_18008DCD5
0x18008dbfb  lea     rcx, [rsp+438h+hHandle]
0x18008dc00  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x18008dc05  mov     eax, [rsi+8]
0x18008dc08  neg     eax
0x18008dc0a  sbb     edx, edx
0x18008dc0c  and     edx, 2
0x18008dc0f  inc     edx
0x18008dc11  mov     rcx, rdi
0x18008dc14  call    cs:__imp_PsmRegisterApplicationProcess
0x18008dc1a  mov     ebx, eax
0x18008dc1c  test    eax, eax
0x18008dc1e  js      loc_18008DD6A
0x18008dc24  call    IsCAMHandlePackagedProcessLaunchPresent
0x18008dc29  test    al, al
0x18008dc2b  jz      short loc_18008DC73
0x18008dc2d  mov     ecx, [r14+10h]
0x18008dc31  call    cs:__imp_CAMHandlePackagedProcessLaunch
0x18008dc37  mov     ebx, eax
0x18008dc39  test    eax, eax
0x18008dc3b  jns     short loc_18008DC73
0x18008dc3d  mov     rcx, [rsp+438h]; this
0x18008dc45  mov     r9d, eax; char *
0x18008dc48  lea     r8, aOnecoreuapBase; "onecoreuap\\base\\appmodel\\execmodel\\"...
0x18008dc4f  mov     edx, 126h; void *
0x18008dc54  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18008dc59  nop
0x18008dc5a  lea     rcx, [rsp+438h+var_408]
0x18008dc5f  call    ??1?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x18008dc64  nop
0x18008dc65  lea     rcx, [rsp+438h+var_400]
0x18008dc6a  call    ??1?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x18008dc6f  mov     eax, ebx
0x18008dc71  jmp     short loc_18008DCD5
0x18008dc73  cmp     dword ptr [rsi+8], 0
0x18008dc77  jz      short loc_18008DCB8
0x18008dc79  mov     [rsp+438h+hHandle], 0
0x18008dc82  xor     edx, edx
0x18008dc84  lea     rcx, [rsp+438h+hHandle]
0x18008dc89  call    ?reset@?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::reset(void *)
0x18008dc8e  lea     r9, [rsp+438h+hHandle]; void **
0x18008dc93  mov     r8, r15; void *
0x18008dc96  mov     rdx, r14; struct _PROCESS_INFORMATION *
0x18008dc99  mov     rcx, [rsi+10h]; unsigned __int16 *
0x18008dc9d  call    ?LaunchDebugger@@YAXPEBGPEAU_PROCESS_INFORMATION@@PEAXPEAPEAX@Z; LaunchDebugger(ushort const *,_PROCESS_INFORMATION *,void *,void * *)
0x18008dca2  mov     rcx, [rsp+438h+hHandle]; hHandle
0x18008dca7  call    ?WaitForDebuggerWorkAround@@YAXPEAX@Z; WaitForDebuggerWorkAround(void *)
0x18008dcac  nop
0x18008dcad  lea     rcx, [rsp+438h+hHandle]
0x18008dcb2  call    ??1?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x18008dcb7  nop
0x18008dcb8  lea     rcx, [rsp+438h+var_408]
0x18008dcbd  call    ??1?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x18008dcc2  nop
0x18008dcc3  lea     rcx, [rsp+438h+var_400]
0x18008dcc8  call    ??1?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x18008dccd  xor     eax, eax
0x18008dccf  jmp     short loc_18008DCD5
0x18008dcd1  mov     eax, [rsp+438h+var_418]
0x18008dcd5  mov     rcx, [rsp+438h+var_38]
0x18008dcdd  xor     rcx, rsp; StackCookie
0x18008dce0  call    __security_check_cookie
0x18008dce5  add     rsp, 410h
0x18008dcec  pop     r15
0x18008dcee  pop     r14
0x18008dcf0  pop     rdi
0x18008dcf1  pop     rsi
0x18008dcf2  pop     rbx
0x18008dcf3  retn
0x18008dcf4  lea     r8, aOnecoreuapBase; "onecoreuap\\base\\appmodel\\execmodel\\"...
0x18008dcfb  mov     edx, 0E7h; void *
0x18008dd00  call    ?_Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_GetLastError(void *,uint,char const *)
0x18008dd06  lea     r8, aOnecoreuapBase; "onecoreuap\\base\\appmodel\\execmodel\\"...
0x18008dd0d  mov     edx, 0EAh; void *
0x18008dd12  call    ?_Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_GetLastError(void *,uint,char const *)
0x18008dd18  mov     r9d, eax; char *
0x18008dd1b  lea     r8, aOnecoreuapBase; "onecoreuap\\base\\appmodel\\execmodel\\"...
0x18008dd22  mov     edx, 0FEh; void *
0x18008dd27  call    ?_Throw_NtStatus@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_NtStatus(void *,uint,char const *,long)
0x18008dd2d  mov     r9d, eax; char *
0x18008dd30  lea     r8, aOnecoreuapBase; "onecoreuap\\base\\appmodel\\execmodel\\"...
0x18008dd37  mov     edx, 107h; void *
0x18008dd3c  call    ?_Throw_NtStatus@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_NtStatus(void *,uint,char const *,long)
0x18008dd41  mov     r9d, eax; char *
0x18008dd44  lea     r8, aOnecoreuapBase; "onecoreuap\\base\\appmodel\\execmodel\\"...
0x18008dd4b  mov     edx, 109h; void *
0x18008dd50  call    ?_Throw_NtStatus@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_NtStatus(void *,uint,char const *,long)
0x18008dd55  mov     r9d, eax; char *
0x18008dd58  lea     r8, aOnecoreuapBase; "onecoreuap\\base\\appmodel\\execmodel\\"...
0x18008dd5f  mov     edx, 10Ah; void *
0x18008dd64  call    ?_Throw_NtStatus@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_NtStatus(void *,uint,char const *,long)
0x18008dd6a  mov     edx, eax; ExitStatus
0x18008dd6c  mov     rcx, rdi; ProcessHandle
0x18008dd6f  call    cs:__imp_NtTerminateProcess
0x18008dd75  mov     rcx, [rsp+438h]; this
0x18008dd7d  mov     r9d, ebx; char *
0x18008dd80  lea     r8, aOnecoreuapBase; "onecoreuap\\base\\appmodel\\execmodel\\"...
0x18008dd87  mov     edx, 11Ch; void *
0x18008dd8c  call    ?_Throw_NtStatus@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_NtStatus(void *,uint,char const *,long)
```
