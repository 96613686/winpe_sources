# AppReadiness::ServiceHandle::SetStatus(ulong,ulong,ulong,ulong,ulong)

- ea: `0x180011bd0`
- end: `0x180011ca5`
- name: `?SetStatus@ServiceHandle@AppReadiness@@QEAA_NKKKKK@Z`
- size: `213`
- prototype: `bool __fastcall(AppReadiness::ServiceHandle *__hidden this, unsigned int, unsigned int, unsigned int, unsigned int, unsigned int)`
- caller_count: `7`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callers

- `0x1800115b4`
- `0x18001338c`
- `0x1800138e0`
- `0x1800221a4`
- `0x180032f80`
- `0x180038848`
- `0x18003ce60`

## callees

- `0x180011bd0`
- `0x180024610`
- `0x18003e210`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180011c69`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180011c69`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180011c58`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180011c58`
- `api-ms-win-service-core-l1-1-0!SetServiceStatus` at `0x180011c47`
- `api-ms-win-service-core-l1-1-0!SetServiceStatus` at `0x180011c47`

## pseudocode

```c
char __fastcall AppReadiness::ServiceHandle::SetStatus(
        AppReadiness::ServiceHandle *this,
        DWORD a2,
        DWORD a3,
        __int64 a4,
        DWORD a5,
        DWORD a6)
{
  __int64 v8; // rcx
  _SERVICE_STATUS ServiceStatus; // [rsp+20h] [rbp-48h] BYREF

  if ( !*((_QWORD *)this + 1) )
    return 0;
  if ( a2 == 4 )
    v8 = *((unsigned int *)this + 5);
  else
    v8 = 0;
  ServiceStatus.dwServiceType = *((_DWORD *)this + 24);
  ServiceStatus.dwCheckPoint = a5;
  ServiceStatus.dwWaitHint = a6;
  ServiceStatus.dwCurrentState = a2;
  ServiceStatus.dwControlsAccepted = v8;
  ServiceStatus.dwWin32ExitCode = a3;
  ServiceStatus.dwServiceSpecificExitCode = 0;
  if ( (Microsoft_Windows_AppReadinessEnableBits & 8) != 0 )
    McTemplateU0qd_EventWriteTransfer(
      v8,
      "h",
      a2,
      a3,
      *(_QWORD *)&ServiceStatus.dwServiceType,
      *(_QWORD *)&ServiceStatus.dwControlsAccepted,
      *(_QWORD *)&ServiceStatus.dwServiceSpecificExitCode,
      ServiceStatus.dwWaitHint);
  if ( !SetServiceStatus(*((SERVICE_STATUS_HANDLE *)this + 1), &ServiceStatus) )
    return 0;
  AcquireSRWLockExclusive((PSRWLOCK)this + 3);
  *((_DWORD *)this + 4) = a2;
  if ( this != (AppReadiness::ServiceHandle *)-24LL )
    ReleaseSRWLockExclusive((PSRWLOCK)this + 3);
  return 1;
}

```

## disassembly

```asm
0x180011bd0  push    rbx
0x180011bd2  push    rsi
0x180011bd3  push    rdi
0x180011bd4  sub     rsp, 50h
0x180011bd8  mov     rax, cs:__security_cookie
0x180011bdf  xor     rax, rsp
0x180011be2  mov     [rsp+68h+var_28], rax
0x180011be7  cmp     qword ptr [rcx+8], 0
0x180011bec  mov     esi, edx
0x180011bee  mov     rbx, rcx
0x180011bf1  jz      loc_180011C8D
0x180011bf7  cmp     edx, 4
0x180011bfa  jnz     loc_180011C86
0x180011c00  mov     ecx, [rcx+14h]
0x180011c03  test    byte ptr cs:Microsoft_Windows_AppReadinessEnableBits, 8
0x180011c0a  mov     eax, [rbx+60h]
0x180011c0d  mov     [rsp+68h+ServiceStatus.dwServiceType], eax
0x180011c11  mov     eax, [rsp+68h+arg_20]
0x180011c18  mov     [rsp+68h+ServiceStatus.dwCheckPoint], eax
0x180011c1c  mov     eax, [rsp+68h+arg_28]
0x180011c23  mov     [rsp+68h+ServiceStatus.dwWaitHint], eax
0x180011c27  mov     [rsp+68h+ServiceStatus.dwCurrentState], esi
0x180011c2b  mov     [rsp+68h+ServiceStatus.dwControlsAccepted], ecx
0x180011c2f  mov     [rsp+68h+ServiceStatus.dwWin32ExitCode], r8d
0x180011c34  mov     [rsp+68h+ServiceStatus.dwServiceSpecificExitCode], 0
0x180011c3c  jnz     short loc_180011C91
0x180011c3e  mov     rcx, [rbx+8]; hServiceStatus
0x180011c42  lea     rdx, [rsp+68h+ServiceStatus]; lpServiceStatus
0x180011c47  call    cs:__imp_SetServiceStatus
0x180011c4d  test    eax, eax
0x180011c4f  jz      short loc_180011C8D
0x180011c51  lea     rdi, [rbx+18h]
0x180011c55  mov     rcx, rdi; SRWLock
0x180011c58  call    cs:__imp_AcquireSRWLockExclusive
0x180011c5e  mov     [rbx+10h], esi
0x180011c61  test    rdi, rdi
0x180011c64  jz      short loc_180011C6F
0x180011c66  mov     rcx, rdi; SRWLock
0x180011c69  call    cs:__imp_ReleaseSRWLockExclusive
0x180011c6f  mov     al, 1
0x180011c71  mov     rcx, [rsp+68h+var_28]
0x180011c76  xor     rcx, rsp; StackCookie
0x180011c79  call    __security_check_cookie
0x180011c7e  add     rsp, 50h
0x180011c82  pop     rdi
0x180011c83  pop     rsi
0x180011c84  pop     rbx
0x180011c85  retn
0x180011c86  xor     ecx, ecx
0x180011c88  jmp     loc_180011C03
0x180011c8d  xor     al, al
0x180011c8f  jmp     short loc_180011C71
0x180011c91  mov     r9d, r8d
0x180011c94  lea     rdx, Service_SetStatus; "h"
0x180011c9b  mov     r8d, esi
0x180011c9e  call    McTemplateU0qd_EventWriteTransfer
0x180011ca3  jmp     short loc_180011C3E
```
