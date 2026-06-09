# wil::details::DestroyThreadPoolIo<1>::Destroy(_TP_IO *)

- ea: `0x18001c6f8`
- end: `0x18001c718`
- name: `?Destroy@?$DestroyThreadPoolIo@$00@details@wil@@SAXPEAU_TP_IO@@@Z`
- size: `32`
- prototype: ``
- caller_count: `2`
- callee_count: `0`
- tags: ``

## callers

- `0x18001b6d4`
- `0x18001f62c`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolIo` at `0x18001c711`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolIoCallbacks` at `0x18001c703`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolIoCallbacks` at `0x18001c703`

## pseudocode

```c
void __fastcall wil::details::DestroyThreadPoolIo<1>::Destroy(struct _TP_IO *a1)
{
  WaitForThreadpoolIoCallbacks(a1, 0);
  CloseThreadpoolIo(a1);
}

```

## disassembly

```asm
0x18001c6f8  push    rbx
0x18001c6fa  sub     rsp, 20h
0x18001c6fe  xor     edx, edx; fCancelPendingCallbacks
0x18001c700  mov     rbx, rcx
0x18001c703  call    cs:__imp_WaitForThreadpoolIoCallbacks
0x18001c709  mov     rcx, rbx
0x18001c70c  add     rsp, 20h
0x18001c710  pop     rbx
0x18001c711  jmp     cs:__imp_CloseThreadpoolIo
```
