# WsShutdownDfs

- ea: `0x18002d3d0`
- end: `0x18002d527`
- name: `WsShutdownDfs`
- size: `343`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config, loader_planting`

## callers

- `0x18002db4c`

## callees

- `0x18002d3d0`

## import_xrefs

- `ntdll!RtlDeregisterWaitEx` at `0x18002d4ac`
- `ntdll!RtlDeregisterWaitEx` at `0x18002d4ac`
- `ntdll!RtlDeleteElementGenericTable` at `0x18002d405`
- `ntdll!RtlDeleteElementGenericTable` at `0x18002d405`
- `ntdll!RtlEnumerateGenericTable` at `0x18002d414`
- `ntdll!RtlEnumerateGenericTable` at `0x18002d414`
- `ntdll!NtClose` at `0x18002d4d0`
- `ntdll!NtClose` at `0x18002d4d0`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18002d487`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18002d487`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002d44d`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002d47e`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002d4df`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002d44d`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002d47e`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002d4df`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18002d497`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18002d497`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18002d3f3`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18002d45a`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18002d3f3`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18002d45a`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18002d4ec`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18002d4f9`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18002d4ec`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18002d4f9`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002d4c3`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002d50b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002d4c3`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002d50b`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18002d435`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18002d435`
- `SspiCli!LsaUnregisterPolicyChangeNotification` at `0x18002d4ba`
- `SspiCli!LsaUnregisterPolicyChangeNotification` at `0x18002d4ba`
- `IPHLPAPI!CancelMibChangeNotify2` at `0x18002d3e6`
- `IPHLPAPI!CancelMibChangeNotify2` at `0x18002d3e6`

## pseudocode

```c
void WsShutdownDfs()
{
  PVOID v0; // rax
  HANDLE v1; // rbx

  if ( WsDfsIpNotify )
    CancelMibChangeNotify2(WsDfsIpNotify);
  EnterCriticalSection(&WsDfsNetLuidTableCriticalSection);
  while ( 1 )
  {
    v0 = RtlEnumerateGenericTable(WsDfsNetLuidTable, 1u);
    if ( !v0 )
      break;
    RtlDeleteElementGenericTable(WsDfsNetLuidTable, v0);
  }
  HeapFree(NtCurrentPeb()->ProcessHeap, 0, WsDfsNetLuidTable);
  WsDfsNetLuidTable = 0;
  LeaveCriticalSection(&WsDfsNetLuidTableCriticalSection);
  EnterCriticalSection(&WsDfsTearDownCriticalSection);
  v1 = g_WsDomainNameChangeEvent;
  if ( g_WsDomainNameChangeEvent == (HANDLE)-1LL )
  {
    LeaveCriticalSection(&WsDfsTearDownCriticalSection);
  }
  else
  {
    g_WsDomainNameChangeEvent = (HANDLE)-1LL;
    LeaveCriticalSection(&WsDfsTearDownCriticalSection);
    SetEvent(v1);
    WaitForSingleObject(WsDfsTearDownDoneEvent, 0xFFFFFFFF);
    if ( g_WsDomainNameChangeWorkItem != (HANDLE)-1LL )
      RtlDeregisterWaitEx(g_WsDomainNameChangeWorkItem, (HANDLE)0xFFFFFFFFFFFFFFFFLL);
    LsaUnregisterPolicyChangeNotification(PolicyNotifyDnsDomainInformation, v1);
    CloseHandle(v1);
    NtClose(WsDfsTearDownDoneEvent);
    WsDfsTearDownDoneEvent = (HANDLE)-1LL;
  }
  DeleteCriticalSection(&WsDfsTearDownCriticalSection);
  DeleteCriticalSection(&WsDfsNetLuidTableCriticalSection);
  if ( hMupEvent )
  {
    CloseHandle(hMupEvent);
    hMupEvent = 0;
  }
}

```

## disassembly

```asm
0x18002d3d0  mov     [rsp+arg_0], rbx
0x18002d3d5  push    rsi
0x18002d3d6  sub     rsp, 20h
0x18002d3da  mov     rcx, cs:WsDfsIpNotify; NotificationHandle
0x18002d3e1  test    rcx, rcx
0x18002d3e4  jz      short loc_18002D3EC
0x18002d3e6  call    cs:__imp_CancelMibChangeNotify2
0x18002d3ec  lea     rcx, WsDfsNetLuidTableCriticalSection; lpCriticalSection
0x18002d3f3  call    cs:__imp_EnterCriticalSection
0x18002d3f9  jmp     short loc_18002D40B
0x18002d3fb  mov     rcx, cs:WsDfsNetLuidTable; Table
0x18002d402  mov     rdx, rax; Buffer
0x18002d405  call    cs:__imp_RtlDeleteElementGenericTable
0x18002d40b  mov     rcx, cs:WsDfsNetLuidTable; Table
0x18002d412  mov     dl, 1; Restart
0x18002d414  call    cs:__imp_RtlEnumerateGenericTable
0x18002d41a  test    rax, rax
0x18002d41d  jnz     short loc_18002D3FB
0x18002d41f  mov     rcx, gs:60h
0x18002d428  xor     edx, edx; dwFlags
0x18002d42a  mov     r8, cs:WsDfsNetLuidTable; lpMem
0x18002d431  mov     rcx, [rcx+30h]; hHeap
0x18002d435  call    cs:__imp_HeapFree
0x18002d43b  lea     rcx, WsDfsNetLuidTableCriticalSection; lpCriticalSection
0x18002d442  mov     cs:WsDfsNetLuidTable, 0
0x18002d44d  call    cs:__imp_LeaveCriticalSection
0x18002d453  lea     rcx, WsDfsTearDownCriticalSection; lpCriticalSection
0x18002d45a  call    cs:__imp_EnterCriticalSection
0x18002d460  mov     rbx, cs:g_WsDomainNameChangeEvent
0x18002d467  lea     rcx, WsDfsTearDownCriticalSection; lpCriticalSection
0x18002d46e  or      rsi, 0FFFFFFFFFFFFFFFFh
0x18002d472  cmp     rbx, rsi
0x18002d475  jz      short loc_18002D4DF
0x18002d477  mov     cs:g_WsDomainNameChangeEvent, rsi
0x18002d47e  call    cs:__imp_LeaveCriticalSection
0x18002d484  mov     rcx, rbx; hEvent
0x18002d487  call    cs:__imp_SetEvent
0x18002d48d  mov     rcx, cs:WsDfsTearDownDoneEvent; hHandle
0x18002d494  or      edx, 0FFFFFFFFh; dwMilliseconds
0x18002d497  call    cs:__imp_WaitForSingleObject
0x18002d49d  mov     rcx, cs:g_WsDomainNameChangeWorkItem; hWaitHandle
0x18002d4a4  cmp     rcx, rsi
0x18002d4a7  jz      short loc_18002D4B2
0x18002d4a9  mov     rdx, rsi; hCompletionEvent
0x18002d4ac  call    cs:__imp_RtlDeregisterWaitEx
0x18002d4b2  mov     rdx, rbx; NotificationEventHandle
0x18002d4b5  mov     ecx, 4; InformationClass
0x18002d4ba  call    cs:__imp_LsaUnregisterPolicyChangeNotification
0x18002d4c0  mov     rcx, rbx; hObject
0x18002d4c3  call    cs:__imp_CloseHandle
0x18002d4c9  mov     rcx, cs:WsDfsTearDownDoneEvent; Handle
0x18002d4d0  call    cs:__imp_NtClose
0x18002d4d6  mov     cs:WsDfsTearDownDoneEvent, rsi
0x18002d4dd  jmp     short loc_18002D4E5
0x18002d4df  call    cs:__imp_LeaveCriticalSection
0x18002d4e5  lea     rcx, WsDfsTearDownCriticalSection; lpCriticalSection
0x18002d4ec  call    cs:__imp_DeleteCriticalSection
0x18002d4f2  lea     rcx, WsDfsNetLuidTableCriticalSection; lpCriticalSection
0x18002d4f9  call    cs:__imp_DeleteCriticalSection
0x18002d4ff  mov     rcx, cs:hMupEvent; hObject
0x18002d506  test    rcx, rcx
0x18002d509  jz      short loc_18002D51C
0x18002d50b  call    cs:__imp_CloseHandle
0x18002d511  mov     cs:hMupEvent, 0
0x18002d51c  mov     rbx, [rsp+28h+arg_0]
0x18002d521  add     rsp, 20h
0x18002d525  pop     rsi
0x18002d526  retn
```
