# wil::details::DestroyThreadPoolWork<0>::Destroy(_TP_WORK *)

- ea: `0x180028240`
- end: `0x180028263`
- name: `?Destroy@?$DestroyThreadPoolWork@$0A@@details@wil@@SAXPEAU_TP_WORK@@@Z`
- size: `35`
- prototype: ``
- caller_count: `2`
- callee_count: `0`
- tags: ``

## callers

- `0x1800280ec`
- `0x180028858`

## import_xrefs

- `KERNEL32!CloseThreadpoolWork` at `0x18002825c`
- `KERNEL32!WaitForThreadpoolWorkCallbacks` at `0x18002824e`
- `KERNEL32!WaitForThreadpoolWorkCallbacks` at `0x18002824e`

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
0x180028240  push    rbx
0x180028242  sub     rsp, 20h
0x180028246  mov     edx, 1; fCancelPendingCallbacks
0x18002824b  mov     rbx, rcx
0x18002824e  call    cs:__imp_WaitForThreadpoolWorkCallbacks
0x180028254  mov     rcx, rbx
0x180028257  add     rsp, 20h
0x18002825b  pop     rbx
0x18002825c  jmp     cs:__imp_CloseThreadpoolWork
```
