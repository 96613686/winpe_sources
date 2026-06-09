# wil::details::DestroyThreadPoolWork<0>::Destroy(_TP_WORK *)

- ea: `0x18000b63c`
- end: `0x18000b65f`
- name: `?Destroy@?$DestroyThreadPoolWork@$0A@@details@wil@@SAXPEAU_TP_WORK@@@Z`
- size: `35`
- prototype: `void __fastcall(struct _TP_WORK *)`
- caller_count: `2`
- callee_count: `0`
- tags: ``

## callers

- `0x18000b5f0`
- `0x18000bb08`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolWorkCallbacks` at `0x18000b64a`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolWorkCallbacks` at `0x18000b64a`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x18000b658`

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
0x18000b63c  push    rbx
0x18000b63e  sub     rsp, 20h
0x18000b642  mov     edx, 1; fCancelPendingCallbacks
0x18000b647  mov     rbx, rcx
0x18000b64a  call    cs:__imp_WaitForThreadpoolWorkCallbacks
0x18000b650  mov     rcx, rbx
0x18000b653  add     rsp, 20h
0x18000b657  pop     rbx
0x18000b658  jmp     cs:__imp_CloseThreadpoolWork
```
