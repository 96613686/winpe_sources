# wil::details::DestroyThreadPoolWork<0>::Destroy(_TP_WORK *)

- ea: `0x18005b598`
- end: `0x18005b5bb`
- name: `?Destroy@?$DestroyThreadPoolWork@$0A@@details@wil@@SAXPEAU_TP_WORK@@@Z`
- size: `35`
- prototype: ``
- caller_count: `2`
- callee_count: `0`
- tags: ``

## callers

- `0x1800558e8`
- `0x18005eaa8`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolWorkCallbacks` at `0x18005b5a6`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolWorkCallbacks` at `0x18005b5a6`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x18005b5b4`

## pseudocode

```c
void __fastcall wil::details::DestroyThreadPoolWork<0>::Destroy(struct _TP_WORK *a1)
{
  WaitForThreadpoolWorkCallbacks(a1, 1);
  CloseThreadpoolWork(a1);
}

```

## disassembly

```asm
0x18005b598  push    rbx
0x18005b59a  sub     rsp, 20h
0x18005b59e  mov     edx, 1; fCancelPendingCallbacks
0x18005b5a3  mov     rbx, rcx
0x18005b5a6  call    cs:__imp_WaitForThreadpoolWorkCallbacks
0x18005b5ac  mov     rcx, rbx
0x18005b5af  add     rsp, 20h
0x18005b5b3  pop     rbx
0x18005b5b4  jmp     cs:__imp_CloseThreadpoolWork
```
