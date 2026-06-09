# ServiceMain

- ea: `0x18000dd00`
- end: `0x18000de4a`
- name: `ServiceMain`
- size: `330`
- prototype: `void()`
- caller_count: `0`
- callee_count: `7`
- tags: `loader_planting, service_task, installer_update`

## callees

- `0x18000dbb0`
- `0x18000dd00`
- `0x1800124bc`
- `0x180012580`
- `0x18001af7c`
- `0x18001b1a0`
- `0x18002c010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000dda5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000dda5`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000de17`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000ddd8`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000de17`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x18000dd74`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x18000dd74`
- `api-ms-win-service-winsvc-l1-1-0!RegisterServiceCtrlHandlerW` at `0x18000dd93`
- `api-ms-win-service-winsvc-l1-1-0!RegisterServiceCtrlHandlerW` at `0x18000dd93`

## string_xrefs

- `0x18000dd29`: `Entering ServiceMain`

## pseudocode

```c
void ServiceMain()
{
  unsigned int LastError; // edi
  const unsigned __int16 *v1; // rcx

  LastError = 0;
  gDebugRequestedMode = 2;
  gDebugEnabled = 1;
  LogTime();
  if ( *(_DWORD *)&gDebugLevel )
    _DebugMsg(0xCu, 0xBB8u, L"Entering ServiceMain");
  ServiceStatus.dwServiceType = 32;
  ServiceStatus.dwCurrentState = 2;
  *(_QWORD *)&ServiceStatus.dwControlsAccepted = 1;
  *(_QWORD *)&ServiceStatus.dwServiceSpecificExitCode = 0;
  ServiceStatus.dwWaitHint = 10000;
  InitializeCriticalSection(&gAppCS);
  hServiceStatus = RegisterServiceCtrlHandlerW(L"APPMGMT", ServiceHandler);
  if ( !hServiceStatus )
    LastError = GetLastError();
  if ( LastError || (LastError = CRPCServiceManager::Initialize(v1)) != 0 )
  {
    ServiceStatus.dwWin32ExitCode = LastError;
    UpdateState(1u);
    DeleteCriticalSection(&gAppCS);
  }
  else
  {
    UpdateState(4u);
    if ( !CRPCServiceManager::WaitForServiceTermination(CRPCServiceManager::_pSingletonManager) )
    {
      ServiceStatus.dwWin32ExitCode = 0;
      UpdateState(1u);
      if ( !ServiceStatus.dwWin32ExitCode )
        DeleteCriticalSection(&gAppCS);
    }
    if ( CRPCServiceManager::_pSingletonManager )
    {
      (**(void (__fastcall ***)(CGPRPCServerBase *, __int64))CRPCServiceManager::_pSingletonManager)(
        CRPCServiceManager::_pSingletonManager,
        1);
      CRPCServiceManager::_pSingletonManager = 0;
    }
  }
}

```

## disassembly

```asm
0x18000dd00  push    rdi
0x18000dd02  sub     rsp, 20h
0x18000dd06  xor     edi, edi
0x18000dd08  mov     cs:?gDebugRequestedMode@@3KA, 2; ulong gDebugRequestedMode
0x18000dd12  mov     cs:?gDebugEnabled@@3KA, 1; ulong gDebugEnabled
0x18000dd1c  call    ?LogTime@@YAXXZ; LogTime(void)
0x18000dd21  cmp     cs:?gDebugLevel@@3KA, edi; ulong gDebugLevel
0x18000dd27  jz      short loc_18000DD3D
0x18000dd29  lea     r8, aEnteringServic; "Entering ServiceMain"
0x18000dd30  mov     edx, 0BB8h; unsigned int
0x18000dd35  lea     ecx, [rdi+0Ch]; unsigned int
0x18000dd38  call    ?_DebugMsg@@YAXKKZZ; _DebugMsg(ulong,ulong,...)
0x18000dd3d  mov     cs:ServiceStatus.dwServiceType, 20h ; ' '
0x18000dd47  mov     cs:ServiceStatus.dwCurrentState, 2
0x18000dd51  mov     qword ptr cs:ServiceStatus.dwControlsAccepted, 1
0x18000dd5c  mov     qword ptr cs:ServiceStatus.dwServiceSpecificExitCode, rdi
0x18000dd63  mov     cs:ServiceStatus.dwWaitHint, 2710h
0x18000dd6d  lea     rcx, ?gAppCS@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x18000dd74  call    cs:__imp_InitializeCriticalSection
0x18000dd7a  jmp     short loc_18000DD81
0x18000dd7c  mov     edi, 0Eh
0x18000dd81  test    edi, edi
0x18000dd83  jnz     short loc_18000DDBC
0x18000dd85  lea     rdx, ServiceHandler; lpHandlerProc
0x18000dd8c  lea     rcx, ServiceName; "APPMGMT"
0x18000dd93  call    cs:__imp_RegisterServiceCtrlHandlerW
0x18000dd99  mov     cs:hServiceStatus, rax
0x18000dda0  test    rax, rax
0x18000dda3  jnz     short loc_18000DDAD
0x18000dda5  call    cs:__imp_GetLastError
0x18000ddab  mov     edi, eax
0x18000ddad  test    edi, edi
0x18000ddaf  jnz     short loc_18000DDBC
0x18000ddb1  call    ?Initialize@CRPCServiceManager@@SAKPEBG@Z; CRPCServiceManager::Initialize(ushort const *)
0x18000ddb6  mov     edi, eax
0x18000ddb8  test    eax, eax
0x18000ddba  jz      short loc_18000DDDF
0x18000ddbc  mov     cs:ServiceStatus.dwWin32ExitCode, edi
0x18000ddc2  mov     ecx, 1; unsigned int
0x18000ddc7  call    ?UpdateState@@YAXK@Z; UpdateState(ulong)
0x18000ddcc  lea     rcx, ?gAppCS@@3U_RTL_CRITICAL_SECTION@@A; _RTL_CRITICAL_SECTION gAppCS
0x18000ddd3  add     rsp, 20h
0x18000ddd7  pop     rdi
0x18000ddd8  jmp     cs:__imp_DeleteCriticalSection
0x18000dddf  mov     ecx, 4; unsigned int
0x18000dde4  call    ?UpdateState@@YAXK@Z; UpdateState(ulong)
0x18000dde9  mov     rcx, cs:?_pSingletonManager@CRPCServiceManager@@0PEAV1@EA; this
0x18000ddf0  call    ?WaitForServiceTermination@CRPCServiceManager@@QEAAKXZ; CRPCServiceManager::WaitForServiceTermination(void)
0x18000ddf5  test    eax, eax
0x18000ddf7  jnz     short loc_18000DE1D
0x18000ddf9  mov     cs:ServiceStatus.dwWin32ExitCode, eax
0x18000ddff  lea     ecx, [rax+1]; unsigned int
0x18000de02  call    ?UpdateState@@YAXK@Z; UpdateState(ulong)
0x18000de07  cmp     cs:ServiceStatus.dwWin32ExitCode, 0
0x18000de0e  jnz     short loc_18000DE1D
0x18000de10  lea     rcx, ?gAppCS@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x18000de17  call    cs:__imp_DeleteCriticalSection
0x18000de1d  mov     rcx, cs:?_pSingletonManager@CRPCServiceManager@@0PEAV1@EA; CRPCServiceManager * CRPCServiceManager::_pSingletonManager
0x18000de24  test    rcx, rcx
0x18000de27  jz      short loc_18000DE44
0x18000de29  mov     rax, [rcx]
0x18000de2c  mov     edx, 1
0x18000de31  mov     rax, [rax]
0x18000de34  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000de39  mov     cs:?_pSingletonManager@CRPCServiceManager@@0PEAV1@EA, 0; CRPCServiceManager * CRPCServiceManager::_pSingletonManager
0x18000de44  add     rsp, 20h
0x18000de48  pop     rdi
0x18000de49  retn
```
