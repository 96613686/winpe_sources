# DqbStatusUpdate(SERVICE_STATUS_HANDLE__ *,ulong,ulong,ulong)

- ea: `0x180002e18`
- end: `0x180002ea3`
- name: `?DqbStatusUpdate@@YAXPEAUSERVICE_STATUS_HANDLE__@@KKK@Z`
- size: `139`
- prototype: `void __fastcall(struct SERVICE_STATUS_HANDLE__ *, DWORD, DWORD, DWORD)`
- caller_count: `3`
- callee_count: `2`
- tags: `service_task, installer_update`

## callers

- `0x180002af0`
- `0x180002c20`
- `0x180002ec0`

## callees

- `0x180002e18`
- `0x18000a1d0`

## import_xrefs

- `api-ms-win-service-core-l1-1-0!SetServiceStatus` at `0x180002e8b`
- `api-ms-win-service-core-l1-1-0!SetServiceStatus` at `0x180002e8b`

## pseudocode

```c
void __fastcall DqbStatusUpdate(struct SERVICE_STATUS_HANDLE__ *a1, DWORD a2, DWORD a3, DWORD a4)
{
  _SERVICE_STATUS ServiceStatus; // [rsp+20h] [rbp-38h] BYREF

  g_dqbCurrentState = a2;
  if ( g_hDqbStatus )
  {
    ServiceStatus.dwServiceType = 48;
    ServiceStatus.dwCurrentState = a2;
    ServiceStatus.dwCheckPoint = a3;
    if ( a2 == 4 )
    {
      ServiceStatus.dwControlsAccepted = 37;
    }
    else
    {
      ServiceStatus.dwControlsAccepted = 0;
      if ( a2 - 2 <= 1 )
      {
        ServiceStatus.dwWaitHint = 500;
        goto LABEL_7;
      }
    }
    ServiceStatus.dwWaitHint = 0;
LABEL_7:
    ServiceStatus.dwWin32ExitCode = a4;
    ServiceStatus.dwServiceSpecificExitCode = 0;
    SetServiceStatus(g_hDqbStatus, &ServiceStatus);
  }
}

```

## disassembly

```asm
0x180002e18  sub     rsp, 58h
0x180002e1c  mov     rax, cs:__security_cookie
0x180002e23  xor     rax, rsp
0x180002e26  mov     [rsp+58h+var_18], rax
0x180002e2b  mov     rcx, cs:?g_hDqbStatus@@3PEAUSERVICE_STATUS_HANDLE__@@EA; hServiceStatus
0x180002e32  xor     r10d, r10d
0x180002e35  mov     cs:?g_dqbCurrentState@@3KA, edx; ulong g_dqbCurrentState
0x180002e3b  test    rcx, rcx
0x180002e3e  jz      short loc_180002E91
0x180002e40  mov     [rsp+58h+ServiceStatus.dwServiceType], 30h ; '0'
0x180002e48  mov     [rsp+58h+ServiceStatus.dwCurrentState], edx
0x180002e4c  mov     [rsp+58h+ServiceStatus.dwCheckPoint], r8d
0x180002e51  cmp     edx, 4
0x180002e54  jnz     short loc_180002E60
0x180002e56  mov     [rsp+58h+ServiceStatus.dwControlsAccepted], 25h ; '%'
0x180002e5e  jmp     short loc_180002E6D
0x180002e60  lea     eax, [rdx-2]
0x180002e63  mov     [rsp+58h+ServiceStatus.dwControlsAccepted], r10d
0x180002e68  cmp     eax, 1
0x180002e6b  jbe     short loc_180002E74
0x180002e6d  mov     [rsp+58h+ServiceStatus.dwWaitHint], r10d
0x180002e72  jmp     short loc_180002E7C
0x180002e74  mov     [rsp+58h+ServiceStatus.dwWaitHint], 1F4h
0x180002e7c  lea     rdx, [rsp+58h+ServiceStatus]; lpServiceStatus
0x180002e81  mov     [rsp+58h+ServiceStatus.dwWin32ExitCode], r9d
0x180002e86  mov     [rsp+58h+ServiceStatus.dwServiceSpecificExitCode], r10d
0x180002e8b  call    cs:__imp_SetServiceStatus
0x180002e91  mov     rcx, [rsp+58h+var_18]
0x180002e96  xor     rcx, rsp; StackCookie
0x180002e99  call    __security_check_cookie
0x180002e9e  add     rsp, 58h
0x180002ea2  retn
```
