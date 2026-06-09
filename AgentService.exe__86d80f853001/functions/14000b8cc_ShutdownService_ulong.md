# ShutdownService(ulong)

- ea: `0x14000b8cc`
- end: `0x14000ba31`
- name: `?ShutdownService@@YAXK@Z`
- size: `357`
- prototype: `void __fastcall(unsigned int)`
- caller_count: `1`
- callee_count: `6`
- tags: `service_task, broker_com_uri`

## callers

- `0x14000b0a0`

## callees

- `0x14000108c`
- `0x140003e50`
- `0x14000b8cc`
- `0x14000bc7c`
- `0x140019f8c`
- `0x14009b010`

## import_xrefs

- `ADVAPI32!SetServiceStatus` at `0x14000ba16`
- `ADVAPI32!SetServiceStatus` at `0x14000ba16`

## pseudocode

```c
void __fastcall ShutdownService(Uev::NotificationListener *a1, __int64 a2, __int64 a3)
{
  DWORD dwServiceSpecificExitCode; // [rsp+30h] [rbp-29h] BYREF
  DWORD dwWin32ExitCode; // [rsp+34h] [rbp-25h] BYREF
  int v5; // [rsp+38h] [rbp-21h] BYREF
  struct _EVENT_DATA_DESCRIPTOR v6; // [rsp+40h] [rbp-19h] BYREF
  int *v7; // [rsp+60h] [rbp+7h]
  __int64 v8; // [rsp+68h] [rbp+Fh]
  DWORD *p_dwWin32ExitCode; // [rsp+70h] [rbp+17h]
  __int64 v10; // [rsp+78h] [rbp+1Fh]
  DWORD *p_dwServiceSpecificExitCode; // [rsp+80h] [rbp+27h]
  __int64 v12; // [rsp+88h] [rbp+2Fh]
  struct _EVENT_DATA_DESCRIPTOR v13; // [rsp+90h] [rbp+37h] BYREF

  if ( pCreateProcNotificationListener )
  {
    Uev::NotificationListener::Stop(a1, a2);
    if ( pCreateProcNotificationListener )
      (**(void (__fastcall ***)(LPVOID, __int64))pCreateProcNotificationListener)(pCreateProcNotificationListener, 1);
    pCreateProcNotificationListener = 0;
  }
  if ( (Microsoft_User_Experience_Virtualization_App_AgentEnableBits & 2) != 0 )
    McGenEventWrite_EventWriteTransfer(
      (REGHANDLE *)UevAppAgentProvider_Context,
      (const EVENT_DESCRIPTOR *)AgentServiceLog_ServiceStopped,
      a3,
      1u,
      &v13);
  *(_QWORD *)&ServiceStatus.dwWin32ExitCode = 0;
  ServiceStatus.dwCurrentState = 1;
  if ( (unsigned int)dword_1400CB248 > 5
    && (qword_1400CB258 & 0x400000000000LL) != 0
    && (qword_1400CB260 & 0x400000000000LL) == qword_1400CB260 )
  {
    dwServiceSpecificExitCode = ServiceStatus.dwServiceSpecificExitCode;
    dwWin32ExitCode = ServiceStatus.dwWin32ExitCode;
    v5 = 1;
    p_dwServiceSpecificExitCode = &dwServiceSpecificExitCode;
    p_dwWin32ExitCode = &dwWin32ExitCode;
    v7 = &v5;
    v12 = 4;
    v10 = 4;
    v8 = 4;
    tlgWriteTransfer_EventWriteTransfer((int)&dword_1400CB248, (int)&byte_1400B76ED, 0, 0, 5u, &v6);
  }
  SetServiceStatus(hStatus, &ServiceStatus);
}

```

## disassembly

```asm
0x14000b8cc  push    rbp
0x14000b8ce  lea     rbp, [rsp-57h]
0x14000b8d3  sub     rsp, 0B0h
0x14000b8da  mov     rax, cs:__security_cookie
0x14000b8e1  xor     rax, rsp
0x14000b8e4  mov     [rbp+57h+var_10], rax
0x14000b8e8  cmp     cs:?pCreateProcNotificationListener@@3PEAVCreateProcNotificationListener@Uev@@EA, 0; Uev::CreateProcNotificationListener * pCreateProcNotificationListener
0x14000b8f0  jz      short loc_14000B91E
0x14000b8f2  call    ?Stop@NotificationListener@Uev@@QEAAXXZ; Uev::NotificationListener::Stop(void)
0x14000b8f7  mov     rcx, cs:?pCreateProcNotificationListener@@3PEAVCreateProcNotificationListener@Uev@@EA; Uev::CreateProcNotificationListener * pCreateProcNotificationListener
0x14000b8fe  test    rcx, rcx
0x14000b901  jz      short loc_14000B913
0x14000b903  mov     rax, [rcx]
0x14000b906  mov     edx, 1
0x14000b90b  mov     rax, [rax]
0x14000b90e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000b913  mov     cs:?pCreateProcNotificationListener@@3PEAVCreateProcNotificationListener@Uev@@EA, 0; Uev::CreateProcNotificationListener * pCreateProcNotificationListener
0x14000b91e  test    cs:Microsoft_User_Experience_Virtualization_App_AgentEnableBits, 2
0x14000b925  jz      short loc_14000B949
0x14000b927  lea     rax, [rbp+57h+var_20]
0x14000b92b  mov     r9d, 1
0x14000b931  lea     rdx, AgentServiceLog_ServiceStopped
0x14000b938  mov     qword ptr [rsp+0B0h+var_90], rax
0x14000b93d  lea     rcx, UevAppAgentProvider_Context
0x14000b944  call    McGenEventWrite_EventWriteTransfer
0x14000b949  mov     eax, cs:dword_1400CB248
0x14000b94f  mov     qword ptr cs:?ServiceStatus@@3U_SERVICE_STATUS@@A.dwWin32ExitCode, 0; _SERVICE_STATUS ServiceStatus ...
0x14000b95a  mov     cs:?ServiceStatus@@3U_SERVICE_STATUS@@A.dwCurrentState, 1; _SERVICE_STATUS ServiceStatus ...
0x14000b964  cmp     eax, 5
0x14000b967  jbe     loc_14000BA08
0x14000b96d  mov     rcx, cs:qword_1400CB260
0x14000b974  mov     rdx, 400000000000h
0x14000b97e  mov     rax, cs:qword_1400CB258
0x14000b985  test    rdx, rax
0x14000b988  jz      short loc_14000BA08
0x14000b98a  mov     rax, rcx
0x14000b98d  and     rax, rdx
0x14000b990  cmp     rax, rcx
0x14000b993  jnz     short loc_14000BA08
0x14000b995  mov     eax, cs:?ServiceStatus@@3U_SERVICE_STATUS@@A.dwServiceSpecificExitCode; _SERVICE_STATUS ServiceStatus ...
0x14000b99b  lea     rdx, byte_1400B76ED; int
0x14000b9a2  mov     [rbp+57h+var_80], eax
0x14000b9a5  lea     rcx, dword_1400CB248; int
0x14000b9ac  mov     eax, cs:?ServiceStatus@@3U_SERVICE_STATUS@@A.dwWin32ExitCode; _SERVICE_STATUS ServiceStatus ...
0x14000b9b2  xor     r9d, r9d; int
0x14000b9b5  mov     [rbp+57h+var_7C], eax
0x14000b9b8  xor     r8d, r8d; int
0x14000b9bb  lea     rax, [rbp+57h+var_80]
0x14000b9bf  mov     [rbp+57h+var_78], 1
0x14000b9c6  mov     [rbp+57h+var_30], rax
0x14000b9ca  lea     rax, [rbp+57h+var_7C]
0x14000b9ce  mov     [rbp+57h+var_40], rax
0x14000b9d2  lea     rax, [rbp+57h+var_78]
0x14000b9d6  mov     [rbp+57h+var_50], rax
0x14000b9da  lea     rax, [rbp+57h+var_70]
0x14000b9de  mov     [rsp+0B0h+var_88], rax; PEVENT_DATA_DESCRIPTOR
0x14000b9e3  mov     [rsp+0B0h+var_90], 5; ULONG
0x14000b9eb  mov     [rbp+57h+var_28], 4
0x14000b9f3  mov     [rbp+57h+var_38], 4
0x14000b9fb  mov     [rbp+57h+var_48], 4
0x14000ba03  call    _tlgWriteTransfer_EventWriteTransfer
0x14000ba08  mov     rcx, cs:?hStatus@@3PEAUSERVICE_STATUS_HANDLE__@@EA; hServiceStatus
0x14000ba0f  lea     rdx, ?ServiceStatus@@3U_SERVICE_STATUS@@A; lpServiceStatus
0x14000ba16  call    cs:__imp_SetServiceStatus
0x14000ba1c  mov     rcx, [rbp+57h+var_10]
0x14000ba20  xor     rcx, rsp; StackCookie
0x14000ba23  call    __security_check_cookie
0x14000ba28  add     rsp, 0B0h
0x14000ba2f  pop     rbp
0x14000ba30  retn
```
