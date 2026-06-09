# FSSourceWatchdog::ShutdownWatchdog(void)

- ea: `0x1800b4660`
- end: `0x1800b46e8`
- name: `?ShutdownWatchdog@FSSourceWatchdog@@UEAAXXZ`
- size: `136`
- prototype: `void __fastcall(FSSourceWatchdog *__hidden this)`
- caller_count: `0`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callees

- `0x180009494`
- `0x1800b4660`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800b46e1`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800b4671`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800b4671`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x1800b46a1`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x1800b46a1`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x1800b4697`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x1800b4697`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1800b4688`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1800b4688`

## pseudocode

```c
void __fastcall FSSourceWatchdog::ShutdownWatchdog(FSSourceWatchdog *this)
{
  struct _TP_TIMER *v2; // rcx

  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 8));
  v2 = (struct _TP_TIMER *)*((_QWORD *)this + 8);
  if ( v2 )
  {
    SetThreadpoolTimer(v2, 0, 0, 0);
    WaitForThreadpoolTimerCallbacks(*((PTP_TIMER *)this + 8), 1);
    CloseThreadpoolTimer(*((PTP_TIMER *)this + 8));
    *((_QWORD *)this + 8) = 0;
  }
  wil::com_ptr_t<IFSProcessActivities,wil::err_returncode_policy>::reset((char *)this + 768);
  wil::com_ptr_t<IFSProcessActivities,wil::err_returncode_policy>::reset((char *)this + 760);
  wil::com_ptr_t<IFSProcessActivities,wil::err_returncode_policy>::reset((char *)this + 752);
  LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 8));
}

```

## disassembly

```asm
0x1800b4660  mov     [rsp+arg_0], rbx
0x1800b4665  push    rdi
0x1800b4666  sub     rsp, 20h
0x1800b466a  mov     rbx, rcx
0x1800b466d  add     rcx, 8; lpCriticalSection
0x1800b4671  call    cs:__imp_EnterCriticalSection
0x1800b4677  mov     rcx, [rbx+40h]; pti
0x1800b467b  test    rcx, rcx
0x1800b467e  jz      short loc_1800B46AF
0x1800b4680  xor     r9d, r9d; msWindowLength
0x1800b4683  xor     r8d, r8d; msPeriod
0x1800b4686  xor     edx, edx; pftDueTime
0x1800b4688  call    cs:__imp_SetThreadpoolTimer
0x1800b468e  mov     rcx, [rbx+40h]; pti
0x1800b4692  mov     edx, 1; fCancelPendingCallbacks
0x1800b4697  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x1800b469d  mov     rcx, [rbx+40h]; pti
0x1800b46a1  call    cs:__imp_CloseThreadpoolTimer
0x1800b46a7  mov     qword ptr [rbx+40h], 0
0x1800b46af  lea     rcx, [rbx+300h]
0x1800b46b6  call    ?reset@?$com_ptr_t@UIFSProcessActivities@@Uerr_returncode_policy@wil@@@wil@@QEAAXXZ; wil::com_ptr_t<IFSProcessActivities,wil::err_returncode_policy>::reset(void)
0x1800b46bb  lea     rcx, [rbx+2F8h]
0x1800b46c2  call    ?reset@?$com_ptr_t@UIFSProcessActivities@@Uerr_returncode_policy@wil@@@wil@@QEAAXXZ; wil::com_ptr_t<IFSProcessActivities,wil::err_returncode_policy>::reset(void)
0x1800b46c7  lea     rcx, [rbx+2F0h]
0x1800b46ce  call    ?reset@?$com_ptr_t@UIFSProcessActivities@@Uerr_returncode_policy@wil@@@wil@@QEAAXXZ; wil::com_ptr_t<IFSProcessActivities,wil::err_returncode_policy>::reset(void)
0x1800b46d3  lea     rcx, [rbx+8]
0x1800b46d7  mov     rbx, [rsp+28h+arg_0]
0x1800b46dc  add     rsp, 20h
0x1800b46e0  pop     rdi
0x1800b46e1  jmp     cs:__imp_LeaveCriticalSection
```
