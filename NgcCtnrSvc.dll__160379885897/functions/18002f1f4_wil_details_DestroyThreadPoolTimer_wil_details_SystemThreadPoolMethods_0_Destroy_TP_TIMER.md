# wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *)

- ea: `0x18002f1f4`
- end: `0x18002f239`
- name: `?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAXPEAU_TP_TIMER@@@Z`
- size: `69`
- prototype: `__int64 __fastcall(PTP_TIMER pti)`
- caller_count: `2`
- callee_count: `0`
- tags: ``

## callers

- `0x180025d9c`
- `0x180028e64`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18002f22d`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18002f219`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18002f219`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18002f205`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18002f205`

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
0x18002f1f4  push    rbx
0x18002f1f6  sub     rsp, 20h
0x18002f1fa  xor     r9d, r9d; msWindowLength
0x18002f1fd  xor     r8d, r8d; msPeriod
0x18002f200  xor     edx, edx; pftDueTime
0x18002f202  mov     rbx, rcx
0x18002f205  call    cs:__imp_SetThreadpoolTimer
0x18002f20c  nop     dword ptr [rax+rax+00h]
0x18002f211  mov     edx, 1; fCancelPendingCallbacks
0x18002f216  mov     rcx, rbx; pti
0x18002f219  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x18002f220  nop     dword ptr [rax+rax+00h]
0x18002f225  mov     rcx, rbx
0x18002f228  add     rsp, 20h
0x18002f22c  pop     rbx
0x18002f22d  jmp     cs:__imp_CloseThreadpoolTimer
```
