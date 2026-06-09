# BthUsbAltSetting6_ScoAllocReadTransferCtxImpl(void *,_LIST_ENTRY *)

- ea: `0x1400073e0`
- end: `0x1400073fc`
- name: `?BthUsbAltSetting6_ScoAllocReadTransferCtxImpl@@YAJPEAXPEAU_LIST_ENTRY@@@Z`
- size: `28`
- prototype: `int(void *, struct _LIST_ENTRY *)`
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x140007334`

## pseudocode

```c
__int64 __fastcall BthUsbAltSetting6_ScoAllocReadTransferCtxImpl(struct _DEVICE_EXTENSION *a1, struct _LIST_ENTRY *a2)
{
  return AllocReadTransferCtxImpl(a1, a1->Sco.UsbAltSetting->MAX_PENDING_READS, a2);
}

```

## disassembly

```asm
0x1400073e0  sub     rsp, 28h
0x1400073e4  mov     r8, rdx; struct _LIST_ENTRY *
0x1400073e7  mov     rdx, [rcx+478h]
0x1400073ee  mov     edx, [rdx+4Ch]; unsigned int
0x1400073f1  call    AllocReadTransferCtxImpl
0x1400073f6  add     rsp, 28h
0x1400073fa  retn
```
