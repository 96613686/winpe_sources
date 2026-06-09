# ServiceHandler

- ea: `0x18000c840`
- end: `0x18000c8d4`
- name: `ServiceHandler`
- size: `148`
- prototype: `DWORD __stdcall(DWORD dwControl, DWORD dwEventType, LPVOID lpEventData, LPVOID lpContext)`
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting, service_task, installer_update`

## callees

- `0x18000c840`
- `0x18000cd64`
- `0x180051628`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18000c8c1`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18000c8c1`

## string_xrefs

- `0x18000c84c`: `SmsRouterSvc ServiceHandler OpCode=%d`
- `0x18000c85b`: `ServiceHandler`
- `0x18000c892`: `ServiceHandler`

## pseudocode

```c
__int64 __fastcall ServiceHandler(DWORD dwControl, DWORD dwEventType, LPVOID lpEventData, LPVOID lpContext)
{
  unsigned int v5; // edi
  DWORD v6; // ebx
  DWORD v7; // ebx
  DWORD v8; // ebx

  v5 = 0;
  LogSmsRouterInfo("ServiceHandler", 0x120u, "SmsRouterSvc ServiceHandler OpCode=%d", dwControl);
  v6 = dwControl - 1;
  if ( v6 && (v7 = v6 - 4) != 0 && (v8 = v7 - 10) != 0 )
  {
    if ( v8 == 17 && ServiceStatus.dwCurrentState == 3 )
    {
      LogSmsRouterInfo("ServiceHandler", 0x130u, "SmsRouterSvc Shutdown in progress");
      return 1115;
    }
  }
  else
  {
    UpdateServiceStatus(3u, 0, 0x2710u);
    if ( hObject )
      SetEvent(hObject);
  }
  return v5;
}

```

## disassembly

```asm
0x18000c840  mov     [rsp+arg_0], rbx
0x18000c845  push    rdi
0x18000c846  sub     rsp, 20h
0x18000c84a  mov     ebx, ecx
0x18000c84c  lea     r8, aSmsroutersvcSe; "SmsRouterSvc ServiceHandler OpCode=%d"
0x18000c853  mov     r9d, ecx
0x18000c856  mov     edx, 120h; unsigned int
0x18000c85b  lea     rcx, aServicehandler; "ServiceHandler"
0x18000c862  xor     edi, edi
0x18000c864  call    ?LogSmsRouterInfo@@YAXPEADK0ZZ; LogSmsRouterInfo(char *,ulong,char *,...)
0x18000c869  sub     ebx, 1
0x18000c86c  jz      short loc_18000C8A5
0x18000c86e  sub     ebx, 4
0x18000c871  jz      short loc_18000C8A5
0x18000c873  sub     ebx, 0Ah
0x18000c876  jz      short loc_18000C8A5
0x18000c878  cmp     ebx, 11h
0x18000c87b  jnz     short loc_18000C8C7
0x18000c87d  cmp     cs:ServiceStatus.dwCurrentState, 3
0x18000c884  jnz     short loc_18000C8C7
0x18000c886  lea     r8, aSmsroutersvcSh; "SmsRouterSvc Shutdown in progress"
0x18000c88d  mov     edx, 130h; unsigned int
0x18000c892  lea     rcx, aServicehandler; "ServiceHandler"
0x18000c899  call    ?LogSmsRouterInfo@@YAXPEADK0ZZ; LogSmsRouterInfo(char *,ulong,char *,...)
0x18000c89e  mov     edi, 45Bh
0x18000c8a3  jmp     short loc_18000C8C7
0x18000c8a5  xor     edx, edx; unsigned int
0x18000c8a7  mov     r8d, 2710h; unsigned int
0x18000c8ad  lea     ecx, [rdx+3]; unsigned int
0x18000c8b0  call    ?UpdateServiceStatus@@YAJKKK@Z; UpdateServiceStatus(ulong,ulong,ulong)
0x18000c8b5  mov     rcx, cs:hObject; hEvent
0x18000c8bc  test    rcx, rcx
0x18000c8bf  jz      short loc_18000C8C7
0x18000c8c1  call    cs:__imp_SetEvent
0x18000c8c7  mov     rbx, [rsp+28h+arg_0]
0x18000c8cc  mov     eax, edi
0x18000c8ce  add     rsp, 20h
0x18000c8d2  pop     rdi
0x18000c8d3  retn
```
