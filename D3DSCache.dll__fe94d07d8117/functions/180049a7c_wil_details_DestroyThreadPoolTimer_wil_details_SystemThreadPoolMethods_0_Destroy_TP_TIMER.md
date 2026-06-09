# wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *)

- ea: `0x180049a7c`
- end: `0x180049ab0`
- name: `?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAXPEAU_TP_TIMER@@@Z`
- size: `52`
- prototype: `void __fastcall(PTP_TIMER pti)`
- caller_count: `2`
- callee_count: `0`
- tags: ``

## callers

- `0x180048d14`
- `0x18004ef9c`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180049aa9`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180049a9b`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180049a9b`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180049a8d`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180049a8d`

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
0x180049a7c  push    rbx
0x180049a7e  sub     rsp, 20h
0x180049a82  xor     r9d, r9d; msWindowLength
0x180049a85  xor     r8d, r8d; msPeriod
0x180049a88  xor     edx, edx; pftDueTime
0x180049a8a  mov     rbx, rcx
0x180049a8d  call    cs:__imp_SetThreadpoolTimer
0x180049a93  mov     edx, 1; fCancelPendingCallbacks
0x180049a98  mov     rcx, rbx; pti
0x180049a9b  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x180049aa1  mov     rcx, rbx
0x180049aa4  add     rsp, 20h
0x180049aa8  pop     rbx
0x180049aa9  jmp     cs:__imp_CloseThreadpoolTimer
```
