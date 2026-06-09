# wil::details::DestroyThreadPoolWork<0>::Destroy(_TP_WORK *)

- ea: `0x18005d504`
- end: `0x18005d532`
- name: `?Destroy@?$DestroyThreadPoolWork@$0A@@details@wil@@SAXPEAU_TP_WORK@@@Z`
- size: `46`
- prototype: ``
- caller_count: `2`
- callee_count: `0`
- tags: ``

## callers

- `0x18005772c`
- `0x180060ce8`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolWorkCallbacks` at `0x18005d512`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolWorkCallbacks` at `0x18005d512`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x18005d526`

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
0x18005d504  push    rbx
0x18005d506  sub     rsp, 20h
0x18005d50a  mov     edx, 1; fCancelPendingCallbacks
0x18005d50f  mov     rbx, rcx
0x18005d512  call    cs:__imp_WaitForThreadpoolWorkCallbacks
0x18005d519  nop     dword ptr [rax+rax+00h]
0x18005d51e  mov     rcx, rbx
0x18005d521  add     rsp, 20h
0x18005d525  pop     rbx
0x18005d526  jmp     cs:__imp_CloseThreadpoolWork
```
