# VirtualMachine::TeardownPartition(int)

- ea: `0x140050030`
- end: `0x14005025f`
- name: `?TeardownPartition@VirtualMachine@@AEAAXH@Z`
- size: `559`
- prototype: `void __fastcall(VirtualMachine *__hidden this, int)`
- caller_count: `3`
- callee_count: `10`
- tags: `registry_config`

## callers

- `0x14004fa0c`
- `0x140167340`
- `0x14016add4`

## callees

- `0x140042240`
- `0x140050030`
- `0x140055af0`
- `0x140059880`
- `0x14005b5d8`
- `0x1400d436c`
- `0x140111070`
- `0x140120294`
- `0x14020cb00`
- `0x1402c2010`

## import_xrefs

- `msvcp_win!_Mtx_unlock` at `0x140050075`
- `msvcp_win!_Mtx_unlock` at `0x140050075`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1400500b1`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1400500b1`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1400500e5`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1400500e5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140050170`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140050170`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x140050114`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x140050114`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1400500cc`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1400500cc`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x1400500fd`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x1400500fd`
- `vid!VidChangePartitionLifeState` at `0x140050160`
- `vid!VidChangePartitionLifeState` at `0x140050160`

## pseudocode

```c
void __fastcall VirtualMachine::TeardownPartition(VirtualMachine *this, int a2)
{
  CancellationTokenProvider *v4; // rbx
  void *v5; // rdx
  __int64 v6; // rcx
  __int64 v7; // rax
  signed int LastError; // eax
  unsigned int v9; // ebx
  __int64 v10; // rcx
  __int64 v11; // rax
  __int64 v12; // rbx
  __int64 v13; // rcx
  MemoryManager *v14; // rcx
  __int64 v15; // rcx

  if ( !a2 )
  {
    v4 = (VirtualMachine *)((char *)this + 1280);
    *((_DWORD *)this + 319) = 0;
    std::_Mutex_base::lock((VirtualMachine *)((char *)this + 1280));
    wil::details::ResetEvent(*(wil::details **)(*((_QWORD *)v4 + 12) + 8LL), v5);
    CancellationTokenProvider::EndTimedCancel(v4);
    _Mtx_unlock(v4);
  }
  v6 = *((_QWORD *)this + 133);
  if ( v6 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v6 + 8LL))(v6);
  if ( *((_QWORD *)this + 312) )
  {
    EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 2456));
    SetThreadpoolTimer(*((PTP_TIMER *)this + 312), 0, 0, 0);
    *((_DWORD *)this + 626) = 0;
    LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 2456));
    WaitForThreadpoolTimerCallbacks(*((PTP_TIMER *)this + 312), 1);
    if ( !a2 )
    {
      CloseThreadpoolTimer(*((PTP_TIMER *)this + 312));
      *((_QWORD *)this + 312) = 0;
    }
  }
  if ( *((_BYTE *)this + 2744) )
  {
    if ( *((_DWORD *)this + 317) != 3 )
    {
      v7 = (**(__int64 (__fastcall ***)(__int64))(*((_QWORD *)this + 128) + 24LL))(*((_QWORD *)this + 128) + 24LL);
      if ( !(unsigned int)VidChangePartitionLifeState(v7, 4, 0, 0) )
      {
        LastError = GetLastError();
        v9 = LastError;
        if ( LastError > 0 )
          v9 = (unsigned __int16)LastError | 0x80070000;
        if ( (unsigned int)VmlIsDebugTraceEnabled(16416) )
          VmlDebugTraceWithError(16416, &off_1402D8E90, v9);
      }
    }
    *((_BYTE *)this + 2744) = 0;
  }
  v10 = *((_QWORD *)this + 130);
  if ( v10 )
  {
    if ( (*(unsigned int (__fastcall **)(__int64))(*(_QWORD *)v10 + 160LL))(v10) )
      AsyncTimer::DisableAndWait((VirtualMachine *)((char *)this + 1496));
    (*(void (__fastcall **)(_QWORD))(**((_QWORD **)this + 130) + 272LL))(*((_QWORD *)this + 130));
  }
  v11 = *((_QWORD *)this + 131);
  if ( v11 )
  {
    v12 = v11 + 248;
    v13 = *(_QWORD *)(v11 + 248);
    if ( v13 )
    {
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v13 + 80LL))(v13);
      Vml::VmReferencePtr<WorkerConfiguration,Vml::VmUserReferenceTraits>::Reset(v12, 0);
    }
  }
  v14 = (MemoryManager *)*((_QWORD *)this + 124);
  if ( v14 )
    MemoryManager::TeardownGmoStats(v14);
  v15 = *((_QWORD *)this + 128);
  if ( v15 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v15 + 96LL))(v15);
}

```

## disassembly

```asm
0x140050030  mov     [rsp+arg_8], rbx
0x140050035  mov     [rsp+arg_10], rsi
0x14005003a  push    rdi
0x14005003b  sub     rsp, 20h
0x14005003f  mov     esi, edx
0x140050041  mov     rdi, rcx
0x140050044  test    edx, edx
0x140050046  jnz     short loc_140050081
0x140050048  lea     rbx, [rcx+500h]
0x14005004f  mov     [rcx+4FCh], edx
0x140050055  mov     rcx, rbx; this
0x140050058  call    ?lock@_Mutex_base@std@@QEAAXXZ; std::_Mutex_base::lock(void)
0x14005005d  mov     rcx, [rbx+60h]
0x140050061  mov     rcx, [rcx+8]; this
0x140050065  call    ?ResetEvent@details@wil@@YAXPEAX@Z; wil::details::ResetEvent(void *)
0x14005006a  mov     rcx, rbx; this
0x14005006d  call    ?EndTimedCancel@CancellationTokenProvider@@AEAAXXZ; CancellationTokenProvider::EndTimedCancel(void)
0x140050072  mov     rcx, rbx; _Mtx_t
0x140050075  call    cs:__imp__Mtx_unlock
0x14005007c  nop     dword ptr [rax+rax+00h]
0x140050081  mov     rcx, [rdi+428h]
0x140050088  test    rcx, rcx
0x14005008b  jz      short loc_140050099
0x14005008d  mov     rax, [rcx]
0x140050090  mov     rax, [rax+8]
0x140050094  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140050099  cmp     qword ptr [rdi+9C0h], 0
0x1400500a1  jz      loc_14005012B
0x1400500a7  lea     rbx, [rdi+998h]
0x1400500ae  mov     rcx, rbx; lpCriticalSection
0x1400500b1  call    cs:__imp_EnterCriticalSection
0x1400500b8  nop     dword ptr [rax+rax+00h]
0x1400500bd  mov     rcx, [rdi+9C0h]; pti
0x1400500c4  xor     r9d, r9d; msWindowLength
0x1400500c7  xor     r8d, r8d; msPeriod
0x1400500ca  xor     edx, edx; pftDueTime
0x1400500cc  call    cs:__imp_SetThreadpoolTimer
0x1400500d3  nop     dword ptr [rax+rax+00h]
0x1400500d8  mov     rcx, rbx; lpCriticalSection
0x1400500db  mov     dword ptr [rdi+9C8h], 0
0x1400500e5  call    cs:__imp_LeaveCriticalSection
0x1400500ec  nop     dword ptr [rax+rax+00h]
0x1400500f1  mov     rcx, [rdi+9C0h]; pti
0x1400500f8  mov     edx, 1; fCancelPendingCallbacks
0x1400500fd  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x140050104  nop     dword ptr [rax+rax+00h]
0x140050109  test    esi, esi
0x14005010b  jnz     short loc_14005012B
0x14005010d  mov     rcx, [rdi+9C0h]; pti
0x140050114  call    cs:__imp_CloseThreadpoolTimer
0x14005011b  nop     dword ptr [rax+rax+00h]
0x140050120  mov     qword ptr [rdi+9C0h], 0
0x14005012b  cmp     byte ptr [rdi+0AB8h], 0
0x140050132  jz      short loc_1400501B3
0x140050134  cmp     dword ptr [rdi+4F4h], 3
0x14005013b  jz      short loc_1400501AC
0x14005013d  mov     rcx, [rdi+400h]
0x140050144  add     rcx, 18h
0x140050148  mov     rax, [rcx]
0x14005014b  mov     rax, [rax]
0x14005014e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140050153  xor     r9d, r9d
0x140050156  mov     rcx, rax
0x140050159  xor     r8d, r8d
0x14005015c  lea     edx, [r9+4]
0x140050160  call    cs:__imp_VidChangePartitionLifeState
0x140050167  nop     dword ptr [rax+rax+00h]
0x14005016c  test    eax, eax
0x14005016e  jnz     short loc_1400501AC
0x140050170  call    cs:__imp_GetLastError
0x140050177  nop     dword ptr [rax+rax+00h]
0x14005017c  mov     ebx, eax
0x14005017e  test    eax, eax
0x140050180  jle     short loc_14005018B
0x140050182  movzx   ebx, ax
0x140050185  or      ebx, 80070000h
0x14005018b  mov     esi, 4020h
0x140050190  mov     ecx, esi
0x140050192  call    VmlIsDebugTraceEnabled
0x140050197  test    eax, eax
0x140050199  jz      short loc_1400501AC
0x14005019b  mov     r8d, ebx
0x14005019e  lea     rdx, off_1402D8E90; "Unable to transition partition into sec"...
0x1400501a5  mov     ecx, esi
0x1400501a7  call    VmlDebugTraceWithError
0x1400501ac  mov     byte ptr [rdi+0AB8h], 0
0x1400501b3  mov     rcx, [rdi+410h]
0x1400501ba  test    rcx, rcx
0x1400501bd  jz      short loc_1400501F4
0x1400501bf  mov     rax, [rcx]
0x1400501c2  mov     rax, [rax+0A0h]
0x1400501c9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400501ce  test    eax, eax
0x1400501d0  jz      short loc_1400501DE
0x1400501d2  lea     rcx, [rdi+5D8h]; this
0x1400501d9  call    ?DisableAndWait@AsyncTimer@@QEAAHXZ; AsyncTimer::DisableAndWait(void)
0x1400501de  mov     rcx, [rdi+410h]
0x1400501e5  mov     rax, [rcx]
0x1400501e8  mov     rax, [rax+110h]
0x1400501ef  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400501f4  mov     rax, [rdi+418h]
0x1400501fb  test    rax, rax
0x1400501fe  jz      short loc_140050225
0x140050200  lea     rbx, [rax+0F8h]
0x140050207  mov     rcx, [rbx]
0x14005020a  test    rcx, rcx
0x14005020d  jz      short loc_140050225
0x14005020f  mov     rax, [rcx]
0x140050212  mov     rax, [rax+50h]
0x140050216  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14005021b  xor     edx, edx
0x14005021d  mov     rcx, rbx
0x140050220  call    ?Reset@?$VmReferencePtr@VWorkerConfiguration@@VVmUserReferenceTraits@Vml@@@Vml@@QEAAXPEAVWorkerConfiguration@@@Z; Vml::VmReferencePtr<WorkerConfiguration,Vml::VmUserReferenceTraits>::Reset(WorkerConfiguration *)
0x140050225  mov     rcx, [rdi+3E0h]; this
0x14005022c  test    rcx, rcx
0x14005022f  jz      short loc_140050236
0x140050231  call    ?TeardownGmoStats@MemoryManager@@QEAAXXZ; MemoryManager::TeardownGmoStats(void)
0x140050236  mov     rcx, [rdi+400h]
0x14005023d  test    rcx, rcx
0x140050240  jz      short loc_14005024E
0x140050242  mov     rax, [rcx]
0x140050245  mov     rax, [rax+60h]
0x140050249  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14005024e  mov     rbx, [rsp+28h+arg_8]
0x140050253  mov     rsi, [rsp+28h+arg_10]
0x140050258  add     rsp, 20h
0x14005025c  pop     rdi
0x14005025d  retn
```
