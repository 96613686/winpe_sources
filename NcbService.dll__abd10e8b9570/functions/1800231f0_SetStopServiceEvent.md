# SetStopServiceEvent

- ea: `0x1800231f0`
- end: `0x180023266`
- name: `SetStopServiceEvent`
- size: `118`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callers

- `0x18000aa90`

## callees

- `0x180009740`
- `0x180015924`
- `0x1800231f0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180023225`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180023225`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18002325a`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18002325a`

## string_xrefs

- `0x18002320f`: `SetStopServiceEvent: Synchronizing with startup.`
- `0x180023233`: `SetStopServiceEvent: Done synchronizing with startup.`

## pseudocode

```c
signed __int32 __fastcall SetStopServiceEvent(__int64 a1, __int64 a2)
{
  signed __int32 result; // eax
  __int64 v3; // rdx
  __int64 v4; // rcx

  result = _InterlockedCompareExchange(&g_StopServiceEventSet, 1, 0);
  if ( !result )
  {
    if ( (Microsoft_Windows_Network_Connection_BrokerEnableBits & 1) != 0 )
      McTemplateU0z_EventWriteTransfer(a1, a2, L"SetStopServiceEvent: Synchronizing with startup.");
    WaitForSingleObject(hHandle, 0xFFFFFFFF);
    if ( (Microsoft_Windows_Network_Connection_BrokerEnableBits & 1) != 0 )
      McTemplateU0z_EventWriteTransfer(v4, v3, L"SetStopServiceEvent: Done synchronizing with startup.");
    g_ServiceStatus.dwControlsAccepted = 1024;
    SetNcbServiceStatus(3, 0);
    return SetEvent(g_StopHandles);
  }
  return result;
}

```

## disassembly

```asm
0x1800231f0  push    rbx
0x1800231f2  sub     rsp, 20h
0x1800231f6  mov     ebx, 1
0x1800231fb  xor     eax, eax
0x1800231fd  lock cmpxchg cs:g_StopServiceEventSet, ebx
0x180023205  jnz     short loc_180023260
0x180023207  test    byte ptr cs:Microsoft_Windows_Network_Connection_BrokerEnableBits, bl
0x18002320d  jz      short loc_18002321B
0x18002320f  lea     r8, aSetstopservice; "SetStopServiceEvent: Synchronizing with"...
0x180023216  call    McTemplateU0z_EventWriteTransfer
0x18002321b  mov     rcx, cs:hHandle; hHandle
0x180023222  or      edx, 0FFFFFFFFh; dwMilliseconds
0x180023225  call    cs:__imp_WaitForSingleObject
0x18002322b  test    byte ptr cs:Microsoft_Windows_Network_Connection_BrokerEnableBits, bl
0x180023231  jz      short loc_18002323F
0x180023233  lea     r8, aSetstopservice_0; "SetStopServiceEvent: Done synchronizing"...
0x18002323a  call    McTemplateU0z_EventWriteTransfer
0x18002323f  xor     edx, edx
0x180023241  mov     cs:g_ServiceStatus.dwControlsAccepted, 400h
0x18002324b  lea     ecx, [rdx+3]
0x18002324e  call    SetNcbServiceStatus
0x180023253  mov     rcx, cs:g_StopHandles; hEvent
0x18002325a  call    cs:__imp_SetEvent
0x180023260  add     rsp, 20h
0x180023264  pop     rbx
0x180023265  retn
```
