# wil::details::DestroyThreadPoolWait<0>::Destroy(_TP_WAIT *)

- ea: `0x1800198c8`
- end: `0x1800198f9`
- name: `?Destroy@?$DestroyThreadPoolWait@$0A@@details@wil@@SAXPEAU_TP_WAIT@@@Z`
- size: `49`
- prototype: `__int64 __fastcall(PTP_WAIT pwa)`
- caller_count: `2`
- callee_count: `0`
- tags: ``

## callers

- `0x180019150`
- `0x18001c49c`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolWaitCallbacks` at `0x1800198e4`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolWaitCallbacks` at `0x1800198e4`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWait` at `0x1800198d6`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWait` at `0x1800198d6`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWait` at `0x1800198f2`

## pseudocode

```c
void __fastcall wil::details::DestroyThreadPoolWait<0>::Destroy(PTP_WAIT pwa)
{
  SetThreadpoolWait(pwa, 0, 0);
  WaitForThreadpoolWaitCallbacks(pwa, 1);
  CloseThreadpoolWait(pwa);
}

```

## disassembly

```asm
0x1800198c8  push    rbx
0x1800198ca  sub     rsp, 20h
0x1800198ce  xor     r8d, r8d; pftTimeout
0x1800198d1  xor     edx, edx; h
0x1800198d3  mov     rbx, rcx
0x1800198d6  call    cs:__imp_SetThreadpoolWait
0x1800198dc  mov     edx, 1; fCancelPendingCallbacks
0x1800198e1  mov     rcx, rbx; pwa
0x1800198e4  call    cs:__imp_WaitForThreadpoolWaitCallbacks
0x1800198ea  mov     rcx, rbx
0x1800198ed  add     rsp, 20h
0x1800198f1  pop     rbx
0x1800198f2  jmp     cs:__imp_CloseThreadpoolWait
```
