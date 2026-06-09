# StateWebServer::SetServiceStatus(ulong,ulong,ulong)

- ea: `0x140001d04`
- end: `0x140001d63`
- name: `?SetServiceStatus@StateWebServer@@AEAAXKKK@Z`
- size: `95`
- prototype: `void __fastcall(StateWebServer *this, DWORD, DWORD, DWORD)`
- caller_count: `1`
- callee_count: `1`
- tags: `service_task`

## callers

- `0x140001a20`

## callees

- `0x140005b20`

## import_xrefs

- `ADVAPI32!SetServiceStatus` at `0x140001d4b`
- `ADVAPI32!SetServiceStatus` at `0x140001d4b`

## pseudocode

```c
void __fastcall StateWebServer::SetServiceStatus(StateWebServer *this, DWORD a2, DWORD a3, DWORD a4)
{
  SERVICE_STATUS_HANDLE v4; // rcx
  _SERVICE_STATUS ServiceStatus; // [rsp+20h] [rbp-38h] BYREF

  ServiceStatus.dwServiceSpecificExitCode = 0;
  ServiceStatus.dwCheckPoint = 0;
  *((_DWORD *)this + 22) = a2;
  v4 = (SERVICE_STATUS_HANDLE)*((_QWORD *)this + 10);
  ServiceStatus.dwCurrentState = a2;
  ServiceStatus.dwServiceType = 272;
  ServiceStatus.dwControlsAccepted = 7;
  ServiceStatus.dwWin32ExitCode = a3;
  ServiceStatus.dwWaitHint = a4;
  SetServiceStatus(v4, &ServiceStatus);
}

```

## disassembly

```asm
0x140001d04  sub     rsp, 58h
0x140001d08  mov     rax, cs:__security_cookie
0x140001d0f  xor     rax, rsp
0x140001d12  mov     [rsp+58h+var_18], rax
0x140001d17  and     [rsp+58h+ServiceStatus.dwServiceSpecificExitCode], 0
0x140001d1c  and     [rsp+58h+ServiceStatus.dwCheckPoint], 0
0x140001d21  mov     [rcx+58h], edx
0x140001d24  mov     rcx, [rcx+50h]; hServiceStatus
0x140001d28  mov     [rsp+58h+ServiceStatus.dwCurrentState], edx
0x140001d2c  lea     rdx, [rsp+58h+ServiceStatus]; lpServiceStatus
0x140001d31  mov     [rsp+58h+ServiceStatus.dwServiceType], 110h
0x140001d39  mov     [rsp+58h+ServiceStatus.dwControlsAccepted], 7
0x140001d41  mov     [rsp+58h+ServiceStatus.dwWin32ExitCode], r8d
0x140001d46  mov     [rsp+58h+ServiceStatus.dwWaitHint], r9d
0x140001d4b  call    cs:__imp_SetServiceStatus
0x140001d51  mov     rcx, [rsp+58h+var_18]
0x140001d56  xor     rcx, rsp; StackCookie
0x140001d59  call    __security_check_cookie
0x140001d5e  add     rsp, 58h
0x140001d62  retn
```
