# Container::Manager::Agent::Service::CmAgentService::Stop(long)

- ea: `0x180008a78`
- end: `0x180008b10`
- name: `?Stop@CmAgentService@Service@Agent@Manager@Container@@QEAAXJ@Z`
- size: `152`
- prototype: `void __fastcall(Container::Manager::Agent::Service::CmAgentService *this, DWORD)`
- caller_count: `2`
- callee_count: `5`
- tags: `service_task`

## callers

- `0x180007c30`
- `0x180009a60`

## callees

- `0x180007a4c`
- `0x180008a78`
- `0x1800095d8`
- `0x18000ef48`
- `0x180016860`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180008b04`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180008a87`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180008a87`
- `api-ms-win-service-core-l1-1-0!SetServiceStatus` at `0x180008ad4`
- `api-ms-win-service-core-l1-1-0!SetServiceStatus` at `0x180008ad4`

## pseudocode

```c
void __fastcall Container::Manager::Agent::Service::CmAgentService::Stop(
        Container::Manager::Agent::Service::CmAgentService *this,
        DWORD a2)
{
  Container::Manager::Agent::Core *v3; // rcx
  Container::Manager::Agent::Service::CmAgentService *v4; // rcx
  unsigned int v5; // r8d
  const char *v6; // r9
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]

  AcquireSRWLockExclusive(&SRWLock);
  if ( byte_18004B1D0 )
    Container::Manager::Rpc::Server::Shutdown((Container::Manager::Rpc::Server *)&IfSpec);
  if ( byte_18004B1B8 )
    Container::Manager::Agent::Core::Destroy(v3);
  ServiceStatus.dwCurrentState = 1;
  ServiceStatus.dwWin32ExitCode = a2;
  if ( !SetServiceStatus(hServiceStatus, &ServiceStatus) )
    wil::details::in1diag3::_Log_GetLastError(retaddr, (void *)0xCF, v5, v6);
  Container::Manager::Agent::Service::CmAgentService::Reset(v4);
  ReleaseSRWLockExclusive(&SRWLock);
}

```

## disassembly

```asm
0x180008a78  push    rbx
0x180008a7a  sub     rsp, 20h
0x180008a7e  lea     rcx, SRWLock; SRWLock
0x180008a85  mov     ebx, edx
0x180008a87  call    cs:__imp_AcquireSRWLockExclusive
0x180008a8e  nop     dword ptr [rax+rax+00h]
0x180008a93  cmp     cs:byte_18004B1D0, 0
0x180008a9a  jz      short loc_180008AA8
0x180008a9c  lea     rcx, IfSpec; this
0x180008aa3  call    ?Shutdown@Server@Rpc@Manager@Container@@QEAAXXZ; Container::Manager::Rpc::Server::Shutdown(void)
0x180008aa8  cmp     cs:byte_18004B1B8, 0
0x180008aaf  jz      short loc_180008AB6
0x180008ab1  call    ?Destroy@Core@Agent@Manager@Container@@YAXXZ; Container::Manager::Agent::Core::Destroy(void)
0x180008ab6  mov     rcx, cs:hServiceStatus; hServiceStatus
0x180008abd  lea     rdx, ServiceStatus; lpServiceStatus
0x180008ac4  mov     cs:ServiceStatus.dwCurrentState, 1
0x180008ace  mov     cs:ServiceStatus.dwWin32ExitCode, ebx
0x180008ad4  call    cs:__imp_SetServiceStatus
0x180008adb  nop     dword ptr [rax+rax+00h]
0x180008ae0  test    eax, eax
0x180008ae2  jnz     short loc_180008AF3
0x180008ae4  mov     rcx, [rsp+28h]; this
0x180008ae9  mov     edx, 0CFh; void *
0x180008aee  call    ?_Log_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Log_GetLastError(void *,uint,char const *)
0x180008af3  call    ?Reset@CmAgentService@Service@Agent@Manager@Container@@AEAAXXZ; Container::Manager::Agent::Service::CmAgentService::Reset(void)
0x180008af8  lea     rcx, SRWLock
0x180008aff  add     rsp, 20h
0x180008b03  pop     rbx
0x180008b04  jmp     cs:__imp_ReleaseSRWLockExclusive
```
