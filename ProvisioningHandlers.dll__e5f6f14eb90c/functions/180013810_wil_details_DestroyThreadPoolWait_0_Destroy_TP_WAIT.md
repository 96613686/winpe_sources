# wil::details::DestroyThreadPoolWait<0>::Destroy(_TP_WAIT *)

- ea: `0x180013810`
- end: `0x180013852`
- name: `?Destroy@?$DestroyThreadPoolWait@$0A@@details@wil@@SAXPEAU_TP_WAIT@@@Z`
- size: `66`
- prototype: `__int64 __fastcall(PTP_WAIT pwa)`
- caller_count: `2`
- callee_count: `0`
- tags: ``

## callers

- `0x180010968`
- `0x180020474`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWait` at `0x180013846`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolWaitCallbacks` at `0x180013832`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolWaitCallbacks` at `0x180013832`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWait` at `0x18001381e`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWait` at `0x18001381e`

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
0x180013810  push    rbx
0x180013812  sub     rsp, 20h
0x180013816  xor     r8d, r8d; pftTimeout
0x180013819  xor     edx, edx; h
0x18001381b  mov     rbx, rcx
0x18001381e  call    cs:__imp_SetThreadpoolWait
0x180013825  nop     dword ptr [rax+rax+00h]
0x18001382a  mov     edx, 1; fCancelPendingCallbacks
0x18001382f  mov     rcx, rbx; pwa
0x180013832  call    cs:__imp_WaitForThreadpoolWaitCallbacks
0x180013839  nop     dword ptr [rax+rax+00h]
0x18001383e  mov     rcx, rbx
0x180013841  add     rsp, 20h
0x180013845  pop     rbx
0x180013846  jmp     cs:__imp_CloseThreadpoolWait
```
