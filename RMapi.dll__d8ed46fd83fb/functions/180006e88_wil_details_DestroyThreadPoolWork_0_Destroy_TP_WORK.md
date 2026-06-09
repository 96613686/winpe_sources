# wil::details::DestroyThreadPoolWork<0>::Destroy(_TP_WORK *)

- ea: `0x180006e88`
- end: `0x180006eab`
- name: `?Destroy@?$DestroyThreadPoolWork@$0A@@details@wil@@SAXPEAU_TP_WORK@@@Z`
- size: `35`
- prototype: ``
- caller_count: `3`
- callee_count: `0`
- tags: ``

## callers

- `0x18000521c`
- `0x180009e14`
- `0x18000a518`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x180006ea4`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolWorkCallbacks` at `0x180006e96`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolWorkCallbacks` at `0x180006e96`

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
0x180006e88  push    rbx
0x180006e8a  sub     rsp, 20h
0x180006e8e  mov     edx, 1; fCancelPendingCallbacks
0x180006e93  mov     rbx, rcx
0x180006e96  call    cs:__imp_WaitForThreadpoolWorkCallbacks
0x180006e9c  mov     rcx, rbx
0x180006e9f  add     rsp, 20h
0x180006ea3  pop     rbx
0x180006ea4  jmp     cs:__imp_CloseThreadpoolWork
```
