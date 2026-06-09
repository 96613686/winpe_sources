# BthUsbAltSetting6_ScoAllocWriteTransferCtxImpl(void *,_LIST_ENTRY *)

- ea: `0x140008e40`
- end: `0x140008e64`
- name: `?BthUsbAltSetting6_ScoAllocWriteTransferCtxImpl@@YAJPEAXPEAU_LIST_ENTRY@@@Z`
- size: `36`
- prototype: `int(void *, struct _LIST_ENTRY *)`
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x140008d90`

## pseudocode

```c
__int64 __fastcall BthUsbAltSetting6_ScoAllocWriteTransferCtxImpl(struct _DEVICE_EXTENSION *a1, struct _LIST_ENTRY *a2)
{
  return AllocWriteTransferCtxImpl(a1, 3 * a1->Sco.UsbAltSetting->MAX_PENDING_WRITES, a2);
}

```

## disassembly

```asm
0x140008e40  sub     rsp, 28h
0x140008e44  mov     rax, [rcx+478h]
0x140008e4b  mov     r9, rdx
0x140008e4e  mov     r8d, [rax+40h]
0x140008e52  lea     edx, [r8+r8*2]; unsigned int
0x140008e56  mov     r8, r9; struct _LIST_ENTRY *
0x140008e59  call    AllocWriteTransferCtxImpl
0x140008e5e  add     rsp, 28h
0x140008e62  retn
```
