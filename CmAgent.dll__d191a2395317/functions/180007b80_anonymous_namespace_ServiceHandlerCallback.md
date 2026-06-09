# _anonymous_namespace_::ServiceHandlerCallback

- ea: `0x180007b80`
- end: `0x180007c23`
- name: `_anonymous_namespace_::ServiceHandlerCallback`
- size: `163`
- prototype: `DWORD __stdcall(DWORD dwControl, DWORD dwEventType, LPVOID lpEventData, LPVOID lpContext)`
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting, service_task`

## callees

- `0x180007b80`
- `0x180009518`
- `0x1800095d8`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180007bfe`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180007bfe`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180007be7`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180007be7`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180007b8f`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180007b8f`
- `api-ms-win-service-core-l1-1-0!SetServiceStatus` at `0x180007bc1`
- `api-ms-win-service-core-l1-1-0!SetServiceStatus` at `0x180007bc1`

## pseudocode

```c
__int64 __fastcall anonymous_namespace_::ServiceHandlerCallback(
        DWORD dwControl,
        DWORD dwEventType,
        LPVOID lpEventData,
        LPVOID lpContext)
{
  unsigned int v5; // r8d
  const char *v6; // r9
  __int64 v7; // r8
  const char *v8; // r9
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]

  AcquireSRWLockExclusive(&SRWLock);
  if ( ServiceStatus.dwCurrentState != 1 && dwControl == 1 )
  {
    ServiceStatus.dwCurrentState = 3;
    if ( !SetServiceStatus(hServiceStatus, &ServiceStatus) )
      wil::details::in1diag3::_Log_GetLastError(retaddr, (void *)0xEC, v5, v6);
    if ( !SetEvent(hEvent) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA01, v7, v8);
  }
  ReleaseSRWLockExclusive(&SRWLock);
  return 0;
}

```

## disassembly

```asm
0x180007b80  push    rbx
0x180007b82  sub     rsp, 20h
0x180007b86  mov     ebx, ecx
0x180007b88  lea     rcx, SRWLock; SRWLock
0x180007b8f  call    cs:__imp_AcquireSRWLockExclusive
0x180007b96  nop     dword ptr [rax+rax+00h]
0x180007b9b  cmp     cs:ServiceStatus.dwCurrentState, 1
0x180007ba2  jz      short loc_180007BF7
0x180007ba4  cmp     ebx, 1
0x180007ba7  jnz     short loc_180007BF7
0x180007ba9  mov     rcx, cs:hServiceStatus; hServiceStatus
0x180007bb0  lea     rdx, ServiceStatus; lpServiceStatus
0x180007bb7  mov     cs:ServiceStatus.dwCurrentState, 3
0x180007bc1  call    cs:__imp_SetServiceStatus
0x180007bc8  nop     dword ptr [rax+rax+00h]
0x180007bcd  test    eax, eax
0x180007bcf  jnz     short loc_180007BE0
0x180007bd1  mov     rcx, [rsp+28h]; this
0x180007bd6  mov     edx, 0ECh; void *
0x180007bdb  call    ?_Log_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Log_GetLastError(void *,uint,char const *)
0x180007be0  mov     rcx, cs:hEvent; hEvent
0x180007be7  call    cs:__imp_SetEvent
0x180007bee  nop     dword ptr [rax+rax+00h]
0x180007bf3  test    eax, eax
0x180007bf5  jz      short loc_180007C13
0x180007bf7  lea     rcx, SRWLock; SRWLock
0x180007bfe  call    cs:__imp_ReleaseSRWLockExclusive
0x180007c05  nop     dword ptr [rax+rax+00h]
0x180007c0a  xor     eax, eax
0x180007c0c  add     rsp, 20h
0x180007c10  pop     rbx
0x180007c11  retn
0x180007c13  mov     rcx, [rsp+28h]; this
0x180007c18  mov     edx, 0A01h; void *
0x180007c1d  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
