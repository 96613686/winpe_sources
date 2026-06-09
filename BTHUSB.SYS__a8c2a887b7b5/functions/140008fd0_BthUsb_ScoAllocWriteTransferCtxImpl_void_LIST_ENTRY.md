# BthUsb_ScoAllocWriteTransferCtxImpl(void *,_LIST_ENTRY *)

- ea: `0x140008fd0`
- end: `0x140008ff7`
- name: `?BthUsb_ScoAllocWriteTransferCtxImpl@@YAJPEAXPEAU_LIST_ENTRY@@@Z`
- size: `39`
- prototype: `int(void *, struct _LIST_ENTRY *)`
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x140008d90`

## pseudocode

```c
__int64 __fastcall BthUsb_ScoAllocWriteTransferCtxImpl(struct _DEVICE_EXTENSION *a1, struct _LIST_ENTRY *a2)
{
  return AllocWriteTransferCtxImpl(a1, 3 * (a1->Sco.UsbAltSetting->MAX_PENDING_WRITES + 1), a2);
}

```

## disassembly

```asm
0x140008fd0  sub     rsp, 28h
0x140008fd4  mov     rax, [rcx+478h]
0x140008fdb  mov     r9, rdx
0x140008fde  mov     r8d, [rax+40h]
0x140008fe2  inc     r8d
0x140008fe5  lea     edx, [r8+r8*2]; unsigned int
0x140008fe9  mov     r8, r9; struct _LIST_ENTRY *
0x140008fec  call    AllocWriteTransferCtxImpl
0x140008ff1  add     rsp, 28h
0x140008ff5  retn
```
