# wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *)

- ea: `0x1400042d0`
- end: `0x140004304`
- name: `?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAXPEAU_TP_TIMER@@@Z`
- size: `52`
- prototype: `void __fastcall(PTP_TIMER pti)`
- caller_count: `2`
- callee_count: `0`
- tags: ``

## callers

- `0x140003af8`
- `0x140008038`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1400042e1`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1400042e1`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x1400042fd`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x1400042ef`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x1400042ef`

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
0x1400042d0  push    rbx
0x1400042d2  sub     rsp, 20h
0x1400042d6  xor     r9d, r9d; msWindowLength
0x1400042d9  xor     r8d, r8d; msPeriod
0x1400042dc  xor     edx, edx; pftDueTime
0x1400042de  mov     rbx, rcx
0x1400042e1  call    cs:__imp_SetThreadpoolTimer
0x1400042e7  mov     edx, 1; fCancelPendingCallbacks
0x1400042ec  mov     rcx, rbx; pti
0x1400042ef  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x1400042f5  mov     rcx, rbx
0x1400042f8  add     rsp, 20h
0x1400042fc  pop     rbx
0x1400042fd  jmp     cs:__imp_CloseThreadpoolTimer
```
