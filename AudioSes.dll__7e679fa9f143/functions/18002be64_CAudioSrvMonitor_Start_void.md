# CAudioSrvMonitor::Start(void)

- ea: `0x18002be64`
- end: `0x18002bf86`
- name: `?Start@CAudioSrvMonitor@@QEAAJXZ`
- size: `290`
- prototype: `__int64 __fastcall(CAudioSrvMonitor *__hidden this)`
- caller_count: `3`
- callee_count: `2`
- tags: `service_task`

## callers

- `0x18002bcc0`
- `0x18002c200`
- `0x18007e38c`

## callees

- `0x18002be64`
- `0x180087e80`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002bea9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002bf52`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002bf69`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002bea9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002bf52`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002bf69`
- `api-ms-win-service-management-l1-1-0!OpenSCManagerW` at `0x18002be9b`
- `api-ms-win-service-management-l1-1-0!OpenSCManagerW` at `0x18002be9b`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x18002bf30`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x18002bf39`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x18002bf30`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x18002bf39`
- `api-ms-win-service-management-l1-1-0!OpenServiceW` at `0x18002bee1`
- `api-ms-win-service-management-l1-1-0!OpenServiceW` at `0x18002bee1`
- `api-ms-win-service-winsvc-l1-1-0!QueryServiceStatus` at `0x18002bef7`
- `api-ms-win-service-winsvc-l1-1-0!QueryServiceStatus` at `0x18002bef7`
- `api-ms-win-service-private-l1-1-0!SubscribeServiceChangeNotifications` at `0x18002bf23`
- `api-ms-win-service-private-l1-1-0!SubscribeServiceChangeNotifications` at `0x18002bf23`

## string_xrefs

- `0x18002be7f`: `ServicesActive`

## pseudocode

```c
__int64 __fastcall CAudioSrvMonitor::Start(CAudioSrvMonitor *this)
{
  SC_HANDLE v2; // rax
  SC_HANDLE v3; // rsi
  signed int v4; // eax
  unsigned int v5; // ebx
  SC_HANDLE v7; // rax
  SC_HANDLE v8; // rdi
  signed int v9; // eax
  signed int LastError; // eax
  _SERVICE_STATUS ServiceStatus; // [rsp+30h] [rbp-58h] BYREF

  memset(&ServiceStatus, 0, sizeof(ServiceStatus));
  v2 = OpenSCManagerW(0, L"ServicesActive", 1u);
  v3 = v2;
  if ( v2 )
  {
    v7 = OpenServiceW(v2, L"AudioSrv", 4u);
    v8 = v7;
    if ( !v7 )
    {
      LastError = GetLastError();
      v5 = LastError;
      if ( LastError > 0 )
        v5 = (unsigned __int16)LastError | 0x80070000;
      goto LABEL_9;
    }
    if ( QueryServiceStatus(v7, &ServiceStatus) )
    {
      *((_DWORD *)this + 5) = ServiceStatus.dwCurrentState;
      v5 = 0;
      v9 = SubscribeServiceChangeNotifications(
             v8,
             2,
             CAudioSrvMonitor::AudioSrvStatusChangedCallback,
             this,
             (char *)this + 24);
      if ( !v9 )
      {
LABEL_8:
        CloseServiceHandle(v8);
LABEL_9:
        CloseServiceHandle(v3);
        return v5;
      }
      if ( v9 <= 0 )
      {
        v5 = v9;
        goto LABEL_8;
      }
    }
    else
    {
      v9 = GetLastError();
      v5 = v9;
      if ( v9 <= 0 )
        goto LABEL_8;
    }
    v5 = (unsigned __int16)v9 | 0x80070000;
    goto LABEL_8;
  }
  v4 = GetLastError();
  v5 = v4;
  if ( v4 > 0 )
    return (unsigned __int16)v4 | 0x80070000;
  return v5;
}

```

## disassembly

```asm
0x18002be64  push    rbx
0x18002be66  push    rbp
0x18002be67  push    rsi
0x18002be68  push    rdi
0x18002be69  sub     rsp, 68h
0x18002be6d  mov     rax, cs:__security_cookie
0x18002be74  xor     rax, rsp
0x18002be77  mov     [rsp+88h+var_38], rax
0x18002be7c  xorps   xmm0, xmm0
0x18002be7f  lea     rdx, DatabaseName; "ServicesActive"
0x18002be86  mov     rbp, rcx
0x18002be89  mov     r8d, 1; dwDesiredAccess
0x18002be8f  movups  xmmword ptr [rsp+88h+ServiceStatus.dwServiceType], xmm0
0x18002be94  xor     ecx, ecx; lpMachineName
0x18002be96  movups  xmmword ptr [rsp+88h+ServiceStatus.dwWin32ExitCode], xmm0
0x18002be9b  call    cs:__imp_OpenSCManagerW
0x18002bea1  mov     rsi, rax
0x18002bea4  test    rax, rax
0x18002bea7  jnz     short loc_18002BED1
0x18002bea9  call    cs:__imp_GetLastError
0x18002beaf  mov     ebx, eax
0x18002beb1  test    eax, eax
0x18002beb3  jg      loc_18002BF44
0x18002beb9  mov     eax, ebx
0x18002bebb  mov     rcx, [rsp+88h+var_38]
0x18002bec0  xor     rcx, rsp; StackCookie
0x18002bec3  call    __security_check_cookie
0x18002bec8  add     rsp, 68h
0x18002becc  pop     rdi
0x18002becd  pop     rsi
0x18002bece  pop     rbp
0x18002becf  pop     rbx
0x18002bed0  retn
0x18002bed1  mov     r8d, 4; dwDesiredAccess
0x18002bed7  lea     rdx, ServiceName; "AudioSrv"
0x18002bede  mov     rcx, rsi; hSCManager
0x18002bee1  call    cs:__imp_OpenServiceW
0x18002bee7  mov     rdi, rax
0x18002beea  test    rax, rax
0x18002beed  jz      short loc_18002BF52
0x18002beef  lea     rdx, [rsp+88h+ServiceStatus]; lpServiceStatus
0x18002bef4  mov     rcx, rax; hService
0x18002bef7  call    cs:__imp_QueryServiceStatus
0x18002befd  test    eax, eax
0x18002beff  jz      short loc_18002BF69
0x18002bf01  mov     eax, [rsp+88h+ServiceStatus.dwCurrentState]
0x18002bf05  lea     r8, ?AudioSrvStatusChangedCallback@CAudioSrvMonitor@@SAXKPEAX@Z; CAudioSrvMonitor::AudioSrvStatusChangedCallback(ulong,void *)
0x18002bf0c  mov     [rbp+14h], eax
0x18002bf0f  xor     ebx, ebx
0x18002bf11  lea     rax, [rbp+18h]
0x18002bf15  mov     r9, rbp
0x18002bf18  mov     rcx, rdi
0x18002bf1b  mov     [rsp+88h+var_68], rax
0x18002bf20  lea     edx, [rbx+2]
0x18002bf23  call    cs:__imp_SubscribeServiceChangeNotifications
0x18002bf29  test    eax, eax
0x18002bf2b  jnz     short loc_18002BF80
0x18002bf2d  mov     rcx, rdi; hSCObject
0x18002bf30  call    cs:__imp_CloseServiceHandle
0x18002bf36  mov     rcx, rsi; hSCObject
0x18002bf39  call    cs:__imp_CloseServiceHandle
0x18002bf3f  jmp     loc_18002BEB9
0x18002bf44  movzx   ebx, ax
0x18002bf47  or      ebx, 80070000h
0x18002bf4d  jmp     loc_18002BEB9
0x18002bf52  call    cs:__imp_GetLastError
0x18002bf58  mov     ebx, eax
0x18002bf5a  test    eax, eax
0x18002bf5c  jle     short loc_18002BF36
0x18002bf5e  movzx   ebx, ax
0x18002bf61  or      ebx, 80070000h
0x18002bf67  jmp     short loc_18002BF36
0x18002bf69  call    cs:__imp_GetLastError
0x18002bf6f  mov     ebx, eax
0x18002bf71  test    eax, eax
0x18002bf73  jle     short loc_18002BF2D
0x18002bf75  movzx   ebx, ax
0x18002bf78  or      ebx, 80070000h
0x18002bf7e  jmp     short loc_18002BF2D
0x18002bf80  jg      short loc_18002BF75
0x18002bf82  mov     ebx, eax
0x18002bf84  jmp     short loc_18002BF2D
```
