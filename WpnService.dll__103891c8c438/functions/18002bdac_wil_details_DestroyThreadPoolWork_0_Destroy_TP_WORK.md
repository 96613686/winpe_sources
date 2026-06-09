# wil::details::DestroyThreadPoolWork<0>::Destroy(_TP_WORK *)

- ea: `0x18002bdac`
- end: `0x18002bdcf`
- name: `?Destroy@?$DestroyThreadPoolWork@$0A@@details@wil@@SAXPEAU_TP_WORK@@@Z`
- size: `35`
- prototype: `void __fastcall(struct _TP_WORK *)`
- caller_count: `2`
- callee_count: `0`
- tags: ``

## callers

- `0x1800200f4`
- `0x180025108`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolWorkCallbacks` at `0x18002bdba`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolWorkCallbacks` at `0x18002bdba`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x18002bdc8`

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
0x18002bdac  push    rbx
0x18002bdae  sub     rsp, 20h
0x18002bdb2  mov     edx, 1; fCancelPendingCallbacks
0x18002bdb7  mov     rbx, rcx
0x18002bdba  call    cs:__imp_WaitForThreadpoolWorkCallbacks
0x18002bdc0  mov     rcx, rbx
0x18002bdc3  add     rsp, 20h
0x18002bdc7  pop     rbx
0x18002bdc8  jmp     cs:__imp_CloseThreadpoolWork
```
