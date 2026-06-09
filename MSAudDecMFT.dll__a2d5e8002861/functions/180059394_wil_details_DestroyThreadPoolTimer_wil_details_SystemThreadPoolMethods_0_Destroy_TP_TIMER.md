# wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *)

- ea: `0x180059394`
- end: `0x1800593d9`
- name: `?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAXPEAU_TP_TIMER@@@Z`
- size: `69`
- prototype: `__int64 __fastcall(PTP_TIMER pti)`
- caller_count: `2`
- callee_count: `0`
- tags: ``

## callers

- `0x18004bc78`
- `0x18004c01c`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x1800593b9`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x1800593b9`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1800593a5`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1800593a5`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x1800593cd`

## pseudocode

```c
void __fastcall wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(PTP_TIMER pti)
{
  SetThreadpoolTimer(pti, 0, 0, 0);
  WaitForThreadpoolTimerCallbacks(pti, 1);
  CloseThreadpoolTimer(pti);
}

```

## disassembly

```asm
0x180059394  push    rbx
0x180059396  sub     rsp, 20h
0x18005939a  xor     r9d, r9d; msWindowLength
0x18005939d  xor     r8d, r8d; msPeriod
0x1800593a0  xor     edx, edx; pftDueTime
0x1800593a2  mov     rbx, rcx
0x1800593a5  call    cs:__imp_SetThreadpoolTimer
0x1800593ac  nop     dword ptr [rax+rax+00h]
0x1800593b1  mov     edx, 1; fCancelPendingCallbacks
0x1800593b6  mov     rcx, rbx; pti
0x1800593b9  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x1800593c0  nop     dword ptr [rax+rax+00h]
0x1800593c5  mov     rcx, rbx
0x1800593c8  add     rsp, 20h
0x1800593cc  pop     rbx
0x1800593cd  jmp     cs:__imp_CloseThreadpoolTimer
```
