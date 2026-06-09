# SetNcbServiceStatus

- ea: `0x180015924`
- end: `0x1800159b0`
- name: `SetNcbServiceStatus`
- size: `140`
- prototype: ``
- caller_count: `4`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callers

- `0x180015690`
- `0x180018300`
- `0x1800230a0`
- `0x1800231f0`

## callees

- `0x180009740`
- `0x18000a0a0`
- `0x180015924`

## import_xrefs

- `api-ms-win-service-core-l1-1-0!SetServiceStatus` at `0x180015976`
- `api-ms-win-service-core-l1-1-0!SetServiceStatus` at `0x180015976`

## string_xrefs

- `0x18001593e`: `SetNcbServiceStatus: Setting state to %d`
- `0x180015989`: `SetNcbServiceStatus: Failed to set NCB service status`

## pseudocode

```c
int __fastcall SetNcbServiceStatus(__int64 a1, __int64 a2)
{
  DWORD v2; // edi
  DWORD v3; // ebx
  int result; // eax
  __int64 v5; // rdx
  __int64 v6; // rcx

  v2 = a2;
  v3 = a1;
  if ( (Microsoft_Windows_Network_Connection_BrokerEnableBits & 1) != 0 )
    McTemplateU0zq_EventWriteTransfer(a1, a2, L"SetNcbServiceStatus: Setting state to %d", (unsigned int)a1);
  g_ServiceStatus.dwCurrentState = v3;
  g_ServiceStatus.dwWin32ExitCode = v2;
  if ( v3 - 2 <= 1 )
    g_ServiceStatus.dwWaitHint = 30000;
  result = SetServiceStatus(hServiceStatus, &g_ServiceStatus);
  if ( !result && (Microsoft_Windows_Network_Connection_BrokerEnableBits & 1) != 0 )
    result = McTemplateU0z_EventWriteTransfer(v6, v5, L"SetNcbServiceStatus: Failed to set NCB service status");
  g_ServiceStatus.dwWaitHint = 0;
  g_ErrorCode = v2;
  return result;
}

```

## disassembly

```asm
0x180015924  mov     [rsp+arg_0], rbx
0x180015929  push    rdi
0x18001592a  sub     rsp, 20h
0x18001592e  test    byte ptr cs:Microsoft_Windows_Network_Connection_BrokerEnableBits, 1
0x180015935  mov     edi, edx
0x180015937  mov     ebx, ecx
0x180015939  jz      short loc_18001594A
0x18001593b  mov     r9d, ecx
0x18001593e  lea     r8, aSetncbservices; "SetNcbServiceStatus: Setting state to %"...
0x180015945  call    McTemplateU0zq_EventWriteTransfer
0x18001594a  lea     eax, [rbx-2]
0x18001594d  mov     cs:g_ServiceStatus.dwCurrentState, ebx
0x180015953  mov     cs:g_ServiceStatus.dwWin32ExitCode, edi
0x180015959  cmp     eax, 1
0x18001595c  ja      short loc_180015968
0x18001595e  mov     cs:g_ServiceStatus.dwWaitHint, 7530h
0x180015968  mov     rcx, cs:hServiceStatus; hServiceStatus
0x18001596f  lea     rdx, g_ServiceStatus; lpServiceStatus
0x180015976  call    cs:__imp_SetServiceStatus
0x18001597c  test    eax, eax
0x18001597e  jnz     short loc_180015995
0x180015980  test    byte ptr cs:Microsoft_Windows_Network_Connection_BrokerEnableBits, 1
0x180015987  jz      short loc_180015995
0x180015989  lea     r8, aSetncbservices_0; "SetNcbServiceStatus: Failed to set NCB "...
0x180015990  call    McTemplateU0z_EventWriteTransfer
0x180015995  mov     rbx, [rsp+28h+arg_0]
0x18001599a  mov     cs:g_ServiceStatus.dwWaitHint, 0
0x1800159a4  mov     cs:g_ErrorCode, edi
0x1800159aa  add     rsp, 20h
0x1800159ae  pop     rdi
0x1800159af  retn
```
