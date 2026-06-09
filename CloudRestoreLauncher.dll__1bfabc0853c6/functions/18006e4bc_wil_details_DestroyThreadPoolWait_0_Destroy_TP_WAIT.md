# wil::details::DestroyThreadPoolWait<0>::Destroy(_TP_WAIT *)

- ea: `0x18006e4bc`
- end: `0x18006e4ed`
- name: `?Destroy@?$DestroyThreadPoolWait@$0A@@details@wil@@SAXPEAU_TP_WAIT@@@Z`
- size: `49`
- prototype: `__int64 __fastcall(PTP_WAIT pwa)`
- caller_count: `2`
- callee_count: `0`
- tags: ``

## callers

- `0x18006d5a4`
- `0x1800825bc`

## import_xrefs

- `KERNEL32!SetThreadpoolWait` at `0x18006e4ca`
- `KERNEL32!SetThreadpoolWait` at `0x18006e4ca`
- `KERNEL32!WaitForThreadpoolWaitCallbacks` at `0x18006e4d8`
- `KERNEL32!WaitForThreadpoolWaitCallbacks` at `0x18006e4d8`
- `KERNEL32!CloseThreadpoolWait` at `0x18006e4e6`

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
0x18006e4bc  push    rbx
0x18006e4be  sub     rsp, 20h
0x18006e4c2  xor     r8d, r8d; pftTimeout
0x18006e4c5  xor     edx, edx; h
0x18006e4c7  mov     rbx, rcx
0x18006e4ca  call    cs:__imp_SetThreadpoolWait
0x18006e4d0  mov     edx, 1; fCancelPendingCallbacks
0x18006e4d5  mov     rcx, rbx; pwa
0x18006e4d8  call    cs:__imp_WaitForThreadpoolWaitCallbacks
0x18006e4de  mov     rcx, rbx
0x18006e4e1  add     rsp, 20h
0x18006e4e5  pop     rbx
0x18006e4e6  jmp     cs:__imp_CloseThreadpoolWait
```
