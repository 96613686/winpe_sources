# InitiateStopNcbService

- ea: `0x1800230a0`
- end: `0x1800231b9`
- name: `InitiateStopNcbService`
- size: `281`
- prototype: ``
- caller_count: `0`
- callee_count: `6`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callees

- `0x180009740`
- `0x180015924`
- `0x18001fce0`
- `0x1800230a0`
- `0x1800231c0`
- `0x180026a08`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002311a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002314c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002311a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002314c`
- `api-ms-win-core-threadpool-legacy-l1-1-0!UnregisterWaitEx` at `0x1800230e8`
- `api-ms-win-core-threadpool-legacy-l1-1-0!UnregisterWaitEx` at `0x1800230e8`
- `WS2_32!__imp_WSACleanup` at `0x18002317d`
- `WS2_32!__imp_WSACleanup` at `0x18002317d`
- `ext-ms-win-networking-radiomonitor-l1-1-0!RadioDeviceStop` at `0x180023177`
- `ext-ms-win-networking-radiomonitor-l1-1-0!RadioDeviceStop` at `0x180023177`

## string_xrefs

- `0x1800230c4`: `The serivce has already tried to stop once.`
- `0x180023102`: `StopServiceWaitObject uninitialized`
- `0x180023134`: `StopServiceEvent uninitialized`
- `0x180023166`: `StartServiceCompleteEvent uninitialized`
- `0x18002318c`: `NcbService will stop immediately following this log.`

## pseudocode

```c
__int64 __fastcall InitiateStopNcbService(__int64 a1, __int64 a2)
{
  __int64 result; // rax
  __int64 v3; // rdx
  __int64 v4; // rcx
  __int64 v5; // rdx
  __int64 v6; // rcx
  __int64 v7; // rdx
  __int64 v8; // rcx
  __int64 v9; // rdx
  __int64 v10; // rcx

  result = (unsigned int)_InterlockedCompareExchange(&g_Stopping, 1, 0);
  if ( (_DWORD)result )
  {
    if ( (Microsoft_Windows_Network_Connection_BrokerEnableBits & 1) != 0 )
      return McTemplateU0z_EventWriteTransfer(a1, a2, L"The serivce has already tried to stop once.");
  }
  else
  {
    KamUninitialize();
    if ( WaitHandle )
    {
      UnregisterWaitEx(WaitHandle, 0);
      WaitHandle = 0;
      if ( (Microsoft_Windows_Network_Connection_BrokerEnableBits & 1) != 0 )
        McTemplateU0z_EventWriteTransfer(v4, v3, L"StopServiceWaitObject uninitialized");
    }
    if ( g_StopHandles )
    {
      CloseHandle(g_StopHandles);
      g_StopHandles = 0;
      if ( (Microsoft_Windows_Network_Connection_BrokerEnableBits & 1) != 0 )
        McTemplateU0z_EventWriteTransfer(v6, v5, L"StopServiceEvent uninitialized");
    }
    if ( hHandle )
    {
      CloseHandle(hHandle);
      hHandle = 0;
      if ( (Microsoft_Windows_Network_Connection_BrokerEnableBits & 1) != 0 )
        McTemplateU0z_EventWriteTransfer(v8, v7, L"StartServiceCompleteEvent uninitialized");
    }
    CleanupSocketBroker();
    RadioDeviceStop();
    WSACleanup();
    if ( (Microsoft_Windows_Network_Connection_BrokerEnableBits & 1) != 0 )
      McTemplateU0z_EventWriteTransfer(v10, v9, L"NcbService will stop immediately following this log.");
    if ( g_TracingEnabled )
      McGenEventUnregister_EventUnregister();
    return SetNcbServiceStatus(1);
  }
  return result;
}

```

## disassembly

```asm
0x1800230a0  push    rdi
0x1800230a2  sub     rsp, 20h
0x1800230a6  mov     edi, 1
0x1800230ab  xor     eax, eax
0x1800230ad  lock cmpxchg cs:g_Stopping, edi
0x1800230b5  jz      short loc_1800230D5
0x1800230b7  test    byte ptr cs:Microsoft_Windows_Network_Connection_BrokerEnableBits, dil
0x1800230be  jz      loc_1800231B3
0x1800230c4  lea     r8, aTheSerivceHasA; "The serivce has already tried to stop o"...
0x1800230cb  add     rsp, 20h
0x1800230cf  pop     rdi
0x1800230d0  jmp     McTemplateU0z_EventWriteTransfer
0x1800230d5  call    KamUninitialize
0x1800230da  mov     rcx, cs:WaitHandle; WaitHandle
0x1800230e1  test    rcx, rcx
0x1800230e4  jz      short loc_18002310E
0x1800230e6  xor     edx, edx; CompletionEvent
0x1800230e8  call    cs:__imp_UnregisterWaitEx
0x1800230ee  test    byte ptr cs:Microsoft_Windows_Network_Connection_BrokerEnableBits, dil
0x1800230f5  mov     cs:WaitHandle, 0
0x180023100  jz      short loc_18002310E
0x180023102  lea     r8, aStopservicewai; "StopServiceWaitObject uninitialized"
0x180023109  call    McTemplateU0z_EventWriteTransfer
0x18002310e  mov     rcx, cs:g_StopHandles; hObject
0x180023115  test    rcx, rcx
0x180023118  jz      short loc_180023140
0x18002311a  call    cs:__imp_CloseHandle
0x180023120  test    byte ptr cs:Microsoft_Windows_Network_Connection_BrokerEnableBits, dil
0x180023127  mov     cs:g_StopHandles, 0
0x180023132  jz      short loc_180023140
0x180023134  lea     r8, aStopserviceeve; "StopServiceEvent uninitialized"
0x18002313b  call    McTemplateU0z_EventWriteTransfer
0x180023140  mov     rcx, cs:hHandle; hObject
0x180023147  test    rcx, rcx
0x18002314a  jz      short loc_180023172
0x18002314c  call    cs:__imp_CloseHandle
0x180023152  test    byte ptr cs:Microsoft_Windows_Network_Connection_BrokerEnableBits, dil
0x180023159  mov     cs:hHandle, 0
0x180023164  jz      short loc_180023172
0x180023166  lea     r8, aStartserviceco; "StartServiceCompleteEvent uninitialized"
0x18002316d  call    McTemplateU0z_EventWriteTransfer
0x180023172  call    CleanupSocketBroker
0x180023177  call    cs:__imp_RadioDeviceStop
0x18002317d  call    cs:__imp_WSACleanup
0x180023183  test    byte ptr cs:Microsoft_Windows_Network_Connection_BrokerEnableBits, dil
0x18002318a  jz      short loc_180023198
0x18002318c  lea     r8, aNcbserviceWill; "NcbService will stop immediately follow"...
0x180023193  call    McTemplateU0z_EventWriteTransfer
0x180023198  cmp     cs:g_TracingEnabled, 0
0x18002319f  jz      short loc_1800231A6
0x1800231a1  call    McGenEventUnregister_EventUnregister
0x1800231a6  mov     edx, cs:g_ErrorCode
0x1800231ac  mov     ecx, edi
0x1800231ae  call    SetNcbServiceStatus
0x1800231b3  add     rsp, 20h
0x1800231b7  pop     rdi
0x1800231b8  retn
```
