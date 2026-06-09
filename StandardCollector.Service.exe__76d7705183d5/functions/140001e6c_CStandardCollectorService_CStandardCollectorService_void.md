# CStandardCollectorService::~CStandardCollectorService(void)

- ea: `0x140001e6c`
- end: `0x140001f2a`
- name: `??1CStandardCollectorService@@QEAA@XZ`
- size: `190`
- prototype: `void __fastcall(CStandardCollectorService *__hidden this)`
- caller_count: `2`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callers

- `0x140001388`
- `0x140014d57`

## callees

- `0x140001e6c`
- `0x140002028`
- `0x140014c70`

## import_xrefs

- `KERNEL32!CloseThreadpoolTimer` at `0x140001ec2`
- `KERNEL32!CloseThreadpoolTimer` at `0x140001ec2`
- `KERNEL32!IsThreadpoolTimerSet` at `0x140001e8a`
- `KERNEL32!IsThreadpoolTimerSet` at `0x140001e8a`
- `KERNEL32!SetThreadpoolTimer` at `0x140001ea3`
- `KERNEL32!SetThreadpoolTimer` at `0x140001ea3`
- `KERNEL32!CloseHandle` at `0x140001f1d`
- `KERNEL32!CloseHandle` at `0x140001f1d`
- `KERNEL32!WaitForThreadpoolTimerCallbacks` at `0x140001eb5`
- `KERNEL32!WaitForThreadpoolTimerCallbacks` at `0x140001eb5`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall CStandardCollectorService::~CStandardCollectorService(CStandardCollectorService *this)
{
  struct _TP_TIMER *v2; // rcx
  __int64 v3; // rcx
  __int64 v4; // rcx
  void *v5; // rcx

  if ( *((_BYTE *)this + 200) )
  {
    v2 = (struct _TP_TIMER *)*((_QWORD *)this + 24);
    if ( v2 )
    {
      if ( IsThreadpoolTimerSet(v2) )
      {
        SetThreadpoolTimer(*((PTP_TIMER *)this + 24), 0, 0, 0);
        WaitForThreadpoolTimerCallbacks(*((PTP_TIMER *)this + 24), 1);
      }
      CloseThreadpoolTimer(*((PTP_TIMER *)this + 24));
      *((_QWORD *)this + 24) = 0;
    }
  }
  DiagHubCommon::HubTask<long,0>::~HubTask<long,0>((char *)this + 80);
  v3 = *((_QWORD *)this + 9);
  if ( v3 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v3 + 16LL))(v3);
  v4 = *((_QWORD *)this + 8);
  if ( v4 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v4 + 16LL))(v4);
  v5 = (void *)*((_QWORD *)this + 6);
  if ( v5 != (void *)-1LL )
  {
    *((_QWORD *)this + 6) = -1;
    CloseHandle(v5);
  }
}

```

## disassembly

```asm
0x140001e6c  push    rbx
0x140001e6e  sub     rsp, 20h
0x140001e72  mov     rbx, rcx
0x140001e75  cmp     byte ptr [rcx+0C8h], 0
0x140001e7c  jz      short loc_140001ED3
0x140001e7e  mov     rcx, [rcx+0C0h]; pti
0x140001e85  test    rcx, rcx
0x140001e88  jz      short loc_140001ED3
0x140001e8a  call    cs:__imp_IsThreadpoolTimerSet
0x140001e90  test    eax, eax
0x140001e92  jz      short loc_140001EBB
0x140001e94  xor     r9d, r9d; msWindowLength
0x140001e97  xor     r8d, r8d; msPeriod
0x140001e9a  xor     edx, edx; pftDueTime
0x140001e9c  mov     rcx, [rbx+0C0h]; pti
0x140001ea3  call    cs:__imp_SetThreadpoolTimer
0x140001ea9  mov     edx, 1; fCancelPendingCallbacks
0x140001eae  mov     rcx, [rbx+0C0h]; pti
0x140001eb5  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x140001ebb  mov     rcx, [rbx+0C0h]; pti
0x140001ec2  call    cs:__imp_CloseThreadpoolTimer
0x140001ec8  mov     qword ptr [rbx+0C0h], 0
0x140001ed3  lea     rcx, [rbx+50h]
0x140001ed7  call    ??1?$HubTask@J$0A@@DiagHubCommon@@UEAA@XZ; DiagHubCommon::HubTask<long,0>::~HubTask<long,0>(void)
0x140001edc  nop
0x140001edd  mov     rcx, [rbx+48h]
0x140001ee1  test    rcx, rcx
0x140001ee4  jz      short loc_140001EF4
0x140001ee6  mov     rax, [rcx]
0x140001ee9  mov     rax, [rax+10h]
0x140001eed  call    cs:__guard_dispatch_icall_fptr
0x140001ef3  nop
0x140001ef4  mov     rcx, [rbx+40h]
0x140001ef8  test    rcx, rcx
0x140001efb  jz      short loc_140001F0B
0x140001efd  mov     rax, [rcx]
0x140001f00  mov     rax, [rax+10h]
0x140001f04  call    cs:__guard_dispatch_icall_fptr
0x140001f0a  nop
0x140001f0b  mov     rcx, [rbx+30h]; hObject
0x140001f0f  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x140001f13  jz      short loc_140001F24
0x140001f15  mov     qword ptr [rbx+30h], 0FFFFFFFFFFFFFFFFh
0x140001f1d  call    cs:__imp_CloseHandle
0x140001f23  nop
0x140001f24  add     rsp, 20h
0x140001f28  pop     rbx
0x140001f29  retn
```
