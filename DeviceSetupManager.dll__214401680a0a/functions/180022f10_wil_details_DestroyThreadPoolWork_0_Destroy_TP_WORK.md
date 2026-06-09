# wil::details::DestroyThreadPoolWork<0>::Destroy(_TP_WORK *)

- ea: `0x180022f10`
- end: `0x180022f33`
- name: `?Destroy@?$DestroyThreadPoolWork@$0A@@details@wil@@SAXPEAU_TP_WORK@@@Z`
- size: `35`
- prototype: `__int64(void)`
- caller_count: `2`
- callee_count: `0`
- tags: ``

## callers

- `0x180022b98`
- `0x18002b92c`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolWorkCallbacks` at `0x180022f1e`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolWorkCallbacks` at `0x180022f1e`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x180022f2c`

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
0x180022f10  push    rbx
0x180022f12  sub     rsp, 20h
0x180022f16  mov     edx, 1; fCancelPendingCallbacks
0x180022f1b  mov     rbx, rcx
0x180022f1e  call    cs:__imp_WaitForThreadpoolWorkCallbacks
0x180022f24  mov     rcx, rbx
0x180022f27  add     rsp, 20h
0x180022f2b  pop     rbx
0x180022f2c  jmp     cs:__imp_CloseThreadpoolWork
```
