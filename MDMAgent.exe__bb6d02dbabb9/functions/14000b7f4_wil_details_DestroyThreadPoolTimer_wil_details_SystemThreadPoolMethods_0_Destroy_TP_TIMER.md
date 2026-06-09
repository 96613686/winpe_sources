# wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *)

- ea: `0x14000b7f4`
- end: `0x14000b839`
- name: `?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAXPEAU_TP_TIMER@@@Z`
- size: `69`
- prototype: `__int64 __fastcall(PTP_TIMER pti)`
- caller_count: `2`
- callee_count: `0`
- tags: ``

## callers

- `0x14000947c`
- `0x140011dd4`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x14000b82d`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x14000b805`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x14000b805`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x14000b819`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x14000b819`

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
0x14000b7f4  push    rbx
0x14000b7f6  sub     rsp, 20h
0x14000b7fa  xor     r9d, r9d; msWindowLength
0x14000b7fd  xor     r8d, r8d; msPeriod
0x14000b800  xor     edx, edx; pftDueTime
0x14000b802  mov     rbx, rcx
0x14000b805  call    cs:__imp_SetThreadpoolTimer
0x14000b80c  nop     dword ptr [rax+rax+00h]
0x14000b811  mov     edx, 1; fCancelPendingCallbacks
0x14000b816  mov     rcx, rbx; pti
0x14000b819  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x14000b820  nop     dword ptr [rax+rax+00h]
0x14000b825  mov     rcx, rbx
0x14000b828  add     rsp, 20h
0x14000b82c  pop     rbx
0x14000b82d  jmp     cs:__imp_CloseThreadpoolTimer
```
