# wil::details::DestroyThreadPoolWait<0>::Destroy(_TP_WAIT *)

- ea: `0x180006910`
- end: `0x180006941`
- name: `?Destroy@?$DestroyThreadPoolWait@$0A@@details@wil@@SAXPEAU_TP_WAIT@@@Z`
- size: `49`
- prototype: `void __fastcall(PTP_WAIT pwa)`
- caller_count: `3`
- callee_count: `0`
- tags: ``

## callers

- `0x180005e00`
- `0x180006db4`
- `0x18000c2c4`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWait` at `0x18000691e`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWait` at `0x18000691e`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWait` at `0x18000693a`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolWaitCallbacks` at `0x18000692c`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolWaitCallbacks` at `0x18000692c`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall wil::details::DestroyThreadPoolWait<0>::Destroy(PTP_WAIT pwa)
{
  SetThreadpoolWait(pwa, 0, 0);
  WaitForThreadpoolWaitCallbacks(pwa, 1);
  CloseThreadpoolWait(pwa);
}

```

## disassembly

```asm
0x180006910  push    rbx
0x180006912  sub     rsp, 20h
0x180006916  xor     r8d, r8d; pftTimeout
0x180006919  xor     edx, edx; h
0x18000691b  mov     rbx, rcx
0x18000691e  call    cs:__imp_SetThreadpoolWait
0x180006924  mov     edx, 1; fCancelPendingCallbacks
0x180006929  mov     rcx, rbx; pwa
0x18000692c  call    cs:__imp_WaitForThreadpoolWaitCallbacks
0x180006932  mov     rcx, rbx
0x180006935  add     rsp, 20h
0x180006939  pop     rbx
0x18000693a  jmp     cs:__imp_CloseThreadpoolWait
```
