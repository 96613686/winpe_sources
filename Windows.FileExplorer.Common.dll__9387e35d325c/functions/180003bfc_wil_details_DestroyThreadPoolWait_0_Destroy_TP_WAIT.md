# wil::details::DestroyThreadPoolWait<0>::Destroy(_TP_WAIT *)

- ea: `0x180003bfc`
- end: `0x180003c2d`
- name: `?Destroy@?$DestroyThreadPoolWait@$0A@@details@wil@@SAXPEAU_TP_WAIT@@@Z`
- size: `49`
- prototype: `__int64 __fastcall(PTP_WAIT pwa)`
- caller_count: `2`
- callee_count: `0`
- tags: ``

## callers

- `0x180003788`
- `0x180005230`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWait` at `0x180003c26`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWait` at `0x180003c0a`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWait` at `0x180003c0a`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolWaitCallbacks` at `0x180003c18`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolWaitCallbacks` at `0x180003c18`

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
0x180003bfc  push    rbx
0x180003bfe  sub     rsp, 20h
0x180003c02  xor     r8d, r8d; pftTimeout
0x180003c05  xor     edx, edx; h
0x180003c07  mov     rbx, rcx
0x180003c0a  call    cs:__imp_SetThreadpoolWait
0x180003c10  mov     edx, 1; fCancelPendingCallbacks
0x180003c15  mov     rcx, rbx; pwa
0x180003c18  call    cs:__imp_WaitForThreadpoolWaitCallbacks
0x180003c1e  mov     rcx, rbx
0x180003c21  add     rsp, 20h
0x180003c25  pop     rbx
0x180003c26  jmp     cs:__imp_CloseThreadpoolWait
```
