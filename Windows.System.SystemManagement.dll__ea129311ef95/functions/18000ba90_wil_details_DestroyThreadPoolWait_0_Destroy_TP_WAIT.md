# wil::details::DestroyThreadPoolWait<0>::Destroy(_TP_WAIT *)

- ea: `0x18000ba90`
- end: `0x18000bac1`
- name: `?Destroy@?$DestroyThreadPoolWait@$0A@@details@wil@@SAXPEAU_TP_WAIT@@@Z`
- size: `49`
- prototype: `__int64 __fastcall(PTP_WAIT pwa)`
- caller_count: `2`
- callee_count: `0`
- tags: ``

## callers

- `0x18000af64`
- `0x18000fa70`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWait` at `0x18000ba9e`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWait` at `0x18000ba9e`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolWaitCallbacks` at `0x18000baac`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolWaitCallbacks` at `0x18000baac`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWait` at `0x18000baba`

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
0x18000ba90  push    rbx
0x18000ba92  sub     rsp, 20h
0x18000ba96  xor     r8d, r8d; pftTimeout
0x18000ba99  xor     edx, edx; h
0x18000ba9b  mov     rbx, rcx
0x18000ba9e  call    cs:__imp_SetThreadpoolWait
0x18000baa4  mov     edx, 1; fCancelPendingCallbacks
0x18000baa9  mov     rcx, rbx; pwa
0x18000baac  call    cs:__imp_WaitForThreadpoolWaitCallbacks
0x18000bab2  mov     rcx, rbx
0x18000bab5  add     rsp, 20h
0x18000bab9  pop     rbx
0x18000baba  jmp     cs:__imp_CloseThreadpoolWait
```
