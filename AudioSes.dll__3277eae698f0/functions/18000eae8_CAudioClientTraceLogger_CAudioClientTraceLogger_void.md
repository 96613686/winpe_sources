# CAudioClientTraceLogger::~CAudioClientTraceLogger(void)

- ea: `0x18000eae8`
- end: `0x18000ebb4`
- name: `??1CAudioClientTraceLogger@@QEAA@XZ`
- size: `204`
- prototype: `void __fastcall(CAudioClientTraceLogger *__hidden this)`
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x18006d65c`

## callees

- `0x18000e904`
- `0x18000eae8`
- `0x18000ebbc`
- `0x180087e80`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000eb9b`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000eb9b`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18000eb52`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18000eb52`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18000eb5f`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18000eb5f`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18000eb40`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18000eb40`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x18000eb26`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x18000eb82`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x18000eb26`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x18000eb82`

## pseudocode

```c
void __fastcall CAudioClientTraceLogger::~CAudioClientTraceLogger(CAudioClientTraceLogger *this)
{
  struct _TP_TIMER *v2; // rcx
  GUID ActivityId; // [rsp+30h] [rbp-28h] BYREF

  ActivityId = (GUID)*((_OWORD *)this + 1);
  EventActivityIdControl(4u, &ActivityId);
  v2 = (struct _TP_TIMER *)*((_QWORD *)this + 30);
  if ( v2 )
  {
    SetThreadpoolTimer(v2, 0, 0, 0);
    WaitForThreadpoolTimerCallbacks(*((PTP_TIMER *)this + 30), 1);
    CloseThreadpoolTimer(*((PTP_TIMER *)this + 30));
    *((_QWORD *)this + 30) = 0;
  }
  CAudioClientTraceLogger::LogVolumeChangeBurst(this);
  EventActivityIdControl(4u, &ActivityId);
  Microsoft::WRL::Details::MakeAllocator<CAudioShellStateTracker>::~MakeAllocator<CAudioShellStateTracker>((char *)this + 176);
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 128));
}

```

## disassembly

```asm
0x18000eae8  push    rbx
0x18000eaea  sub     rsp, 50h
0x18000eaee  mov     rax, cs:__security_cookie
0x18000eaf5  xor     rax, rsp
0x18000eaf8  mov     [rsp+58h+var_18], rax
0x18000eafd  mov     rax, [rcx+10h]
0x18000eb01  lea     rdx, [rsp+58h+ActivityId]; ActivityId
0x18000eb06  movups  xmm0, xmmword ptr [rcx+10h]
0x18000eb0a  mov     qword ptr [rsp+58h+ActivityId.Data1], rax
0x18000eb0f  mov     rbx, rcx
0x18000eb12  mov     rax, [rcx+18h]
0x18000eb16  mov     ecx, 4; ControlCode
0x18000eb1b  mov     qword ptr [rsp+58h+ActivityId.Data4], rax
0x18000eb20  movdqu  [rsp+58h+var_38], xmm0
0x18000eb26  call    cs:__imp_EventActivityIdControl
0x18000eb2c  mov     rcx, [rbx+0F0h]; pti
0x18000eb33  test    rcx, rcx
0x18000eb36  jz      short loc_18000EB70
0x18000eb38  xor     r9d, r9d; msWindowLength
0x18000eb3b  xor     r8d, r8d; msPeriod
0x18000eb3e  xor     edx, edx; pftDueTime
0x18000eb40  call    cs:__imp_SetThreadpoolTimer
0x18000eb46  mov     rcx, [rbx+0F0h]; pti
0x18000eb4d  mov     edx, 1; fCancelPendingCallbacks
0x18000eb52  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x18000eb58  mov     rcx, [rbx+0F0h]; pti
0x18000eb5f  call    cs:__imp_CloseThreadpoolTimer
0x18000eb65  mov     qword ptr [rbx+0F0h], 0
0x18000eb70  mov     rcx, rbx; this
0x18000eb73  call    ?LogVolumeChangeBurst@CAudioClientTraceLogger@@AEAAXXZ; CAudioClientTraceLogger::LogVolumeChangeBurst(void)
0x18000eb78  lea     rdx, [rsp+58h+ActivityId]; ActivityId
0x18000eb7d  mov     ecx, 4; ControlCode
0x18000eb82  call    cs:__imp_EventActivityIdControl
0x18000eb88  lea     rcx, [rbx+0B0h]
0x18000eb8f  call    ??1?$MakeAllocator@VCAudioShellStateTracker@@@Details@WRL@Microsoft@@QEAA@XZ; Microsoft::WRL::Details::MakeAllocator<CAudioShellStateTracker>::~MakeAllocator<CAudioShellStateTracker>(void)
0x18000eb94  lea     rcx, [rbx+80h]; lpCriticalSection
0x18000eb9b  call    cs:__imp_DeleteCriticalSection
0x18000eba1  mov     rcx, [rsp+58h+var_18]
0x18000eba6  xor     rcx, rsp; StackCookie
0x18000eba9  call    __security_check_cookie
0x18000ebae  add     rsp, 50h
0x18000ebb2  pop     rbx
0x18000ebb3  retn
```
