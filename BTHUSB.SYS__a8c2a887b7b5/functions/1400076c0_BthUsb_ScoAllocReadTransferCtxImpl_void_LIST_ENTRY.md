# BthUsb_ScoAllocReadTransferCtxImpl(void *,_LIST_ENTRY *)

- ea: `0x1400076c0`
- end: `0x1400076df`
- name: `?BthUsb_ScoAllocReadTransferCtxImpl@@YAJPEAXPEAU_LIST_ENTRY@@@Z`
- size: `31`
- prototype: `int(void *, struct _LIST_ENTRY *)`
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x140007334`

## pseudocode

```c
__int64 __fastcall BthUsb_ScoAllocReadTransferCtxImpl(struct _DEVICE_EXTENSION *a1, struct _LIST_ENTRY *a2)
{
  return AllocReadTransferCtxImpl(a1, a1->Sco.UsbAltSetting->MAX_PENDING_READS + 2, a2);
}

```

## disassembly

```asm
0x1400076c0  sub     rsp, 28h
0x1400076c4  mov     rax, [rcx+478h]
0x1400076cb  mov     r8, rdx; struct _LIST_ENTRY *
0x1400076ce  mov     edx, [rax+4Ch]
0x1400076d1  add     edx, 2; unsigned int
0x1400076d4  call    AllocReadTransferCtxImpl
0x1400076d9  add     rsp, 28h
0x1400076dd  retn
```
