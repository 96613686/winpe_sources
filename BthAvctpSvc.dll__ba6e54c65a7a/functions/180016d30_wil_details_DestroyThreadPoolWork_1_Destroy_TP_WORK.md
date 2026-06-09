# wil::details::DestroyThreadPoolWork<1>::Destroy(_TP_WORK *)

- ea: `0x180016d30`
- end: `0x180016d50`
- name: `?Destroy@?$DestroyThreadPoolWork@$00@details@wil@@SAXPEAU_TP_WORK@@@Z`
- size: `32`
- prototype: ``
- caller_count: `2`
- callee_count: `0`
- tags: ``

## callers

- `0x180015b3c`
- `0x18001a028`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolWorkCallbacks` at `0x180016d3b`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolWorkCallbacks` at `0x180016d3b`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x180016d49`

## pseudocode

```c
void __fastcall wil::details::DestroyThreadPoolWork<1>::Destroy(struct _TP_WORK *a1)
{
  WaitForThreadpoolWorkCallbacks(a1, 0);
  CloseThreadpoolWork(a1);
}

```

## disassembly

```asm
0x180016d30  push    rbx
0x180016d32  sub     rsp, 20h
0x180016d36  xor     edx, edx; fCancelPendingCallbacks
0x180016d38  mov     rbx, rcx
0x180016d3b  call    cs:__imp_WaitForThreadpoolWorkCallbacks
0x180016d41  mov     rcx, rbx
0x180016d44  add     rsp, 20h
0x180016d48  pop     rbx
0x180016d49  jmp     cs:__imp_CloseThreadpoolWork
```
