# dxg::svc::Host::Host(ushort const *)

- ea: `0x180025c68`
- end: `0x180025dd5`
- name: `??0Host@svc@dxg@@QEAA@PEBG@Z`
- size: `365`
- prototype: `LPSERVICE_STATUS __fastcall(LPSERVICE_STATUS lpServiceStatus, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x180011630`

## callees

- `0x180005920`
- `0x180005fc4`
- `0x18000aac8`
- `0x18001c068`
- `0x180025c68`
- `0x1800260d4`
- `0x1800261f4`
- `0x180031010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventExW` at `0x180025cfa`
- `api-ms-win-core-synch-l1-1-0!CreateEventExW` at `0x180025cfa`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180025d0c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180025d0c`
- `api-ms-win-core-kernel32-legacy-l1-1-0!UnregisterWait` at `0x180025d54`
- `api-ms-win-core-kernel32-legacy-l1-1-0!UnregisterWait` at `0x180025d54`
- `api-ms-win-service-core-l1-1-0!RegisterServiceCtrlHandlerExW` at `0x180025c93`
- `api-ms-win-service-core-l1-1-0!RegisterServiceCtrlHandlerExW` at `0x180025c93`
- `api-ms-win-service-core-l1-1-0!SetServiceStatus` at `0x180025ccd`
- `api-ms-win-service-core-l1-1-0!SetServiceStatus` at `0x180025ccd`

## string_xrefs

- `0x180025caa`: `onecoreuap\windows\directx\dxg\common\servicehelpers\host.cpp`
- `0x180025cdc`: `onecoreuap\windows\directx\dxg\common\servicehelpers\host.cpp`
- `0x180025da9`: `onecoreuap\windows\directx\dxg\common\servicehelpers\host.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
LPSERVICE_STATUS __fastcall dxg::svc::Host::Host(LPSERVICE_STATUS lpServiceStatus, const unsigned __int16 *a2)
{
  SERVICE_STATUS_HANDLE v3; // rax
  const char *v4; // r9
  const char *v5; // r9
  void *v6; // rdx
  HANDLE Event; // rdi
  unsigned int v8; // r8d
  const char *v9; // r9
  HANDLE v10; // rdi
  wil::details *v11; // rsi
  __int64 (__fastcall *v12)(HANDLE *, const WCHAR *, wil::details *, void (__fastcall *)(void *, unsigned __int8)); // rbp
  unsigned int v13; // eax
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+0h]
  const unsigned __int16 *v16; // [rsp+78h] [rbp+10h] BYREF

  v16 = a2;
  *(_OWORD *)&lpServiceStatus->dwServiceType = 0;
  *(_OWORD *)&lpServiceStatus->dwWin32ExitCode = 0;
  v3 = RegisterServiceCtrlHandlerExW(L"GraphicsPerfSvc", ServiceHandler, 0);
  g::StatusHandle = v3;
  if ( !v3 )
    wil::details::in1diag3::_Throw_GetLastError(
      retaddr,
      (void *)0x45,
      (unsigned int)"onecoreuap\\windows\\directx\\dxg\\common\\servicehelpers\\host.cpp",
      v4);
  lpServiceStatus->dwServiceType = 16;
  lpServiceStatus->dwCurrentState = 2;
  if ( !SetServiceStatus(v3, lpServiceStatus) )
    wil::details::in1diag3::_Throw_GetLastError(
      retaddr,
      (void *)0x49,
      (unsigned int)"onecoreuap\\windows\\directx\\dxg\\common\\servicehelpers\\host.cpp",
      v5);
  Event = CreateEventExW(0, 0, 1u, 0x1F0003u);
  if ( !Event )
    wil::details::in1diag3::Throw_GetLastError(retaddr, v6, v8, v9);
  GetLastError();
  _reset___unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAAXPEAX_Z(
    &g::ShutdownEvent,
    Event);
  v10 = g::ServiceThreadPoolWaitHandle;
  v11 = g::ShutdownEvent;
  v12 = (__int64 (__fastcall *)(HANDLE *, const WCHAR *, wil::details *, void (__fastcall *)(void *, unsigned __int8)))*((_QWORD *)g::ServiceHostSharedGlobals + 26);
  if ( (char *)g::ServiceThreadPoolWaitHandle - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
  {
    wil::last_error_context::last_error_context((wil::last_error_context *)&v16);
    UnregisterWait(v10);
    wil::last_error_context::~last_error_context((wil::last_error_context *)&v16);
  }
  g::ServiceThreadPoolWaitHandle = 0;
  v13 = v12(&g::ServiceThreadPoolWaitHandle, L"GraphicsPerfSvc", v11, ServiceStopCallback);
  if ( v13 )
    wil::details::in1diag3::_Throw_Win32(
      retaddr,
      (void *)0x56,
      (unsigned int)"onecoreuap\\windows\\directx\\dxg\\common\\servicehelpers\\host.cpp",
      (const char *)v13,
      0);
  return lpServiceStatus;
}

```

## disassembly

```asm
0x180025c68  mov     [rsp+arg_8], rdx
0x180025c6d  push    rbx
0x180025c6e  push    rbp
0x180025c6f  push    rsi
0x180025c70  push    rdi
0x180025c71  sub     rsp, 48h
0x180025c75  xorps   xmm0, xmm0
0x180025c78  lea     rdx, ServiceHandler; lpHandlerProc
0x180025c7f  movups  xmmword ptr [rcx], xmm0
0x180025c82  mov     rbx, rcx
0x180025c85  xor     r8d, r8d; lpContext
0x180025c88  movups  xmmword ptr [rcx+0Ch], xmm0
0x180025c8c  lea     rcx, ServiceName; "GraphicsPerfSvc"
0x180025c93  call    cs:__imp_RegisterServiceCtrlHandlerExW
0x180025c99  mov     cs:?StatusHandle@g@@3PEAUSERVICE_STATUS_HANDLE__@@EA, rax; SERVICE_STATUS_HANDLE__ * g::StatusHandle
0x180025ca0  test    rax, rax
0x180025ca3  jnz     short loc_180025CBA
0x180025ca5  mov     rcx, [rsp+68h]; this
0x180025caa  lea     r8, aOnecoreuapWind_0; "onecoreuap\\windows\\directx\\dxg\\comm"...
0x180025cb1  lea     edx, [rax+45h]; void *
0x180025cb4  call    ?_Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_GetLastError(void *,uint,char const *)
0x180025cba  mov     rdx, rbx; lpServiceStatus
0x180025cbd  mov     dword ptr [rbx], 10h
0x180025cc3  mov     rcx, rax; hServiceStatus
0x180025cc6  mov     dword ptr [rbx+4], 2
0x180025ccd  call    cs:__imp_SetServiceStatus
0x180025cd3  test    eax, eax
0x180025cd5  jnz     short loc_180025CEC
0x180025cd7  mov     rcx, [rsp+68h]; this
0x180025cdc  lea     r8, aOnecoreuapWind_0; "onecoreuap\\windows\\directx\\dxg\\comm"...
0x180025ce3  lea     edx, [rax+49h]; void *
0x180025ce6  call    ?_Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_GetLastError(void *,uint,char const *)
0x180025cec  xor     edx, edx; lpName
0x180025cee  xor     ecx, ecx; lpEventAttributes
0x180025cf0  mov     r9d, 1F0003h; dwDesiredAccess
0x180025cf6  lea     r8d, [rdx+1]; dwFlags
0x180025cfa  call    cs:__imp_CreateEventExW
0x180025d00  mov     rdi, rax
0x180025d03  test    rax, rax
0x180025d06  jz      loc_180025DCA
0x180025d0c  call    cs:__imp_GetLastError
0x180025d12  mov     rdx, rdi
0x180025d15  lea     rcx, ?ShutdownEvent@g@@3V?$unique_any_t@V?$event_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_exception_policy@3@@wil@@@wil@@A
0x180025d1c  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z
0x180025d21  mov     rax, cs:?ServiceHostSharedGlobals@g@@3PEAU_SVCHOST_GLOBAL_DATA_EX_V1@@EA; _SVCHOST_GLOBAL_DATA_EX_V1 * g::ServiceHostSharedGlobals
0x180025d28  mov     rdi, cs:?ServiceThreadPoolWaitHandle@g@@3V?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?UnregisterWait@@YAH0@Z@details@wil@@@details@wil@@@wil@@A; wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&UnregisterWait(void *)>>> g::ServiceThreadPoolWaitHandle
0x180025d2f  mov     rsi, cs:?ShutdownEvent@g@@3V?$unique_any_t@V?$event_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_exception_policy@3@@wil@@@wil@@A
0x180025d36  mov     rbp, [rax+0D0h]
0x180025d3d  lea     rax, [rdi-1]
0x180025d41  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x180025d45  ja      short loc_180025D64
0x180025d47  lea     rcx, [rsp+68h+arg_8]; this
0x180025d4c  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x180025d51  mov     rcx, rdi; WaitHandle
0x180025d54  call    cs:__imp_UnregisterWait
0x180025d5a  lea     rcx, [rsp+68h+arg_8]; this
0x180025d5f  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x180025d64  mov     [rsp+68h+var_40], 18h
0x180025d6c  lea     r9, ?ServiceStopCallback@@YAXPEAXE@Z; ServiceStopCallback(void *,uchar)
0x180025d73  mov     r8, rsi
0x180025d76  mov     qword ptr [rsp+68h+var_48], 0; unsigned int
0x180025d7f  lea     rdx, ServiceName; "GraphicsPerfSvc"
0x180025d86  mov     cs:?ServiceThreadPoolWaitHandle@g@@3V?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?UnregisterWait@@YAH0@Z@details@wil@@@details@wil@@@wil@@A, 0; wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&UnregisterWait(void *)>>> g::ServiceThreadPoolWaitHandle
0x180025d91  lea     rcx, ?ServiceThreadPoolWaitHandle@g@@3V?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?UnregisterWait@@YAH0@Z@details@wil@@@details@wil@@@wil@@A; wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&UnregisterWait(void *)>>> g::ServiceThreadPoolWaitHandle
0x180025d98  mov     rax, rbp
0x180025d9b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180025da0  test    eax, eax
0x180025da2  jz      short loc_180025DBE
0x180025da4  mov     rcx, [rsp+68h]; this
0x180025da9  lea     r8, aOnecoreuapWind_0; "onecoreuap\\windows\\directx\\dxg\\comm"...
0x180025db0  mov     r9d, eax; char *
0x180025db3  mov     edx, 56h ; 'V'; void *
0x180025db8  call    ?_Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::_Throw_Win32(void *,uint,char const *,ulong)
0x180025dbe  mov     rax, rbx
0x180025dc1  add     rsp, 48h
0x180025dc5  pop     rdi
0x180025dc6  pop     rsi
0x180025dc7  pop     rbp
0x180025dc8  pop     rbx
0x180025dc9  retn
0x180025dca  mov     rcx, [rsp+68h]; this
0x180025dcf  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
```
