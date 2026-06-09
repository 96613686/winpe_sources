# SharedSocket::DeleteKeepAliveTimer(void)

- ea: `0x1800024bc`
- end: `0x180002542`
- name: `?DeleteKeepAliveTimer@SharedSocket@@AEAAXXZ`
- size: `134`
- prototype: `void __fastcall(struct _RTL_CRITICAL_SECTION *this)`
- caller_count: `3`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180001fe0`
- `0x180002430`
- `0x180027ba8`

## callees

- `0x1800024bc`
- `0x18000a0a0`

## import_xrefs

- `ntdll!RtlNtStatusToDosError` at `0x180002522`
- `ntdll!RtlNtStatusToDosError` at `0x180002522`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800024d5`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800024d5`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800024ea`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000250b`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800024ea`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000250b`
- `EventAggregation!EaDeleteAggregatedEvent` at `0x180002516`
- `EventAggregation!EaDeleteAggregatedEvent` at `0x180002516`

## string_xrefs

- `0x180002534`: `DeleteWakeTimer: RtlNtStatusToDosError failed with`

## pseudocode

```c
void __fastcall SharedSocket::DeleteKeepAliveTimer(struct _RTL_CRITICAL_SECTION *this)
{
  struct _RTL_CRITICAL_SECTION *v1; // rbx
  HANDLE LockSemaphore; // rsi
  NTSTATUS v4; // eax
  ULONG v5; // eax
  __int64 v6; // rdx
  __int64 v7; // rcx

  v1 = this + 1;
  EnterCriticalSection(this + 1);
  LockSemaphore = this[5].LockSemaphore;
  if ( LockSemaphore )
  {
    this[5].LockSemaphore = 0;
    LeaveCriticalSection(v1);
    v4 = EaDeleteAggregatedEvent(LockSemaphore, 0);
    if ( v4 < 0 )
    {
      v5 = RtlNtStatusToDosError(v4);
      if ( (Microsoft_Windows_Network_Connection_BrokerEnableBits & 1) != 0 )
        McTemplateU0zq_EventWriteTransfer(v7, v6, L"DeleteWakeTimer: RtlNtStatusToDosError failed with", v5);
    }
  }
  else
  {
    LeaveCriticalSection(v1);
  }
}

```

## disassembly

```asm
0x1800024bc  mov     [rsp+arg_0], rbx
0x1800024c1  mov     [rsp+arg_8], rsi
0x1800024c6  push    rdi
0x1800024c7  sub     rsp, 20h
0x1800024cb  lea     rbx, [rcx+28h]
0x1800024cf  mov     rdi, rcx
0x1800024d2  mov     rcx, rbx; lpCriticalSection
0x1800024d5  call    cs:__imp_EnterCriticalSection
0x1800024db  mov     rsi, [rdi+0E0h]
0x1800024e2  mov     rcx, rbx; lpCriticalSection
0x1800024e5  test    rsi, rsi
0x1800024e8  jnz     short loc_180002500
0x1800024ea  call    cs:__imp_LeaveCriticalSection
0x1800024f0  mov     rbx, [rsp+28h+arg_0]
0x1800024f5  mov     rsi, [rsp+28h+arg_8]
0x1800024fa  add     rsp, 20h
0x1800024fe  pop     rdi
0x1800024ff  retn
0x180002500  mov     qword ptr [rdi+0E0h], 0
0x18000250b  call    cs:__imp_LeaveCriticalSection
0x180002511  xor     edx, edx
0x180002513  mov     rcx, rsi
0x180002516  call    cs:__imp_EaDeleteAggregatedEvent
0x18000251c  test    eax, eax
0x18000251e  jns     short loc_1800024F0
0x180002520  mov     ecx, eax; Status
0x180002522  call    cs:__imp_RtlNtStatusToDosError
0x180002528  test    byte ptr cs:Microsoft_Windows_Network_Connection_BrokerEnableBits, 1
0x18000252f  jz      short loc_1800024F0
0x180002531  mov     r9d, eax
0x180002534  lea     r8, aDeletewaketime; "DeleteWakeTimer: RtlNtStatusToDosError "...
0x18000253b  call    McTemplateU0zq_EventWriteTransfer
0x180002540  jmp     short loc_1800024F0
```
