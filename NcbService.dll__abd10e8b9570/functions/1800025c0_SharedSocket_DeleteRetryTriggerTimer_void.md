# SharedSocket::DeleteRetryTriggerTimer(void)

- ea: `0x1800025c0`
- end: `0x180002646`
- name: `?DeleteRetryTriggerTimer@SharedSocket@@AEAAXXZ`
- size: `134`
- prototype: `void __fastcall(struct _RTL_CRITICAL_SECTION *this)`
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1800022e4`
- `0x180027c50`

## callees

- `0x1800025c0`
- `0x18000a0a0`

## import_xrefs

- `ntdll!RtlNtStatusToDosError` at `0x180002610`
- `ntdll!RtlNtStatusToDosError` at `0x180002610`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800025d9`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800025d9`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800025f9`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180002630`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800025f9`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180002630`
- `EventAggregation!EaDeleteAggregatedEvent` at `0x180002604`
- `EventAggregation!EaDeleteAggregatedEvent` at `0x180002604`

## string_xrefs

- `0x180002622`: `DeleteWakeTimer: RtlNtStatusToDosError failed with`

## pseudocode

```c
void __fastcall SharedSocket::DeleteRetryTriggerTimer(struct _RTL_CRITICAL_SECTION *this)
{
  struct _RTL_CRITICAL_SECTION *v1; // rbx
  ULONG_PTR SpinCount; // rsi
  NTSTATUS v4; // eax
  ULONG v5; // eax
  __int64 v6; // rdx
  __int64 v7; // rcx

  v1 = this + 1;
  EnterCriticalSection(this + 1);
  SpinCount = this[5].SpinCount;
  if ( SpinCount )
  {
    this[5].SpinCount = 0;
    LeaveCriticalSection(v1);
    v4 = EaDeleteAggregatedEvent(SpinCount, 0);
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
0x1800025c0  mov     [rsp+arg_0], rbx
0x1800025c5  mov     [rsp+arg_8], rsi
0x1800025ca  push    rdi
0x1800025cb  sub     rsp, 20h
0x1800025cf  lea     rbx, [rcx+28h]
0x1800025d3  mov     rdi, rcx
0x1800025d6  mov     rcx, rbx; lpCriticalSection
0x1800025d9  call    cs:__imp_EnterCriticalSection
0x1800025df  mov     rsi, [rdi+0E8h]
0x1800025e6  mov     rcx, rbx; lpCriticalSection
0x1800025e9  test    rsi, rsi
0x1800025ec  jz      short loc_180002630
0x1800025ee  mov     qword ptr [rdi+0E8h], 0
0x1800025f9  call    cs:__imp_LeaveCriticalSection
0x1800025ff  xor     edx, edx
0x180002601  mov     rcx, rsi
0x180002604  call    cs:__imp_EaDeleteAggregatedEvent
0x18000260a  test    eax, eax
0x18000260c  jns     short loc_180002636
0x18000260e  mov     ecx, eax; Status
0x180002610  call    cs:__imp_RtlNtStatusToDosError
0x180002616  test    byte ptr cs:Microsoft_Windows_Network_Connection_BrokerEnableBits, 1
0x18000261d  jz      short loc_180002636
0x18000261f  mov     r9d, eax
0x180002622  lea     r8, aDeletewaketime; "DeleteWakeTimer: RtlNtStatusToDosError "...
0x180002629  call    McTemplateU0zq_EventWriteTransfer
0x18000262e  jmp     short loc_180002636
0x180002630  call    cs:__imp_LeaveCriticalSection
0x180002636  mov     rbx, [rsp+28h+arg_0]
0x18000263b  mov     rsi, [rsp+28h+arg_8]
0x180002640  add     rsp, 20h
0x180002644  pop     rdi
0x180002645  retn
```
