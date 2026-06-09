# BthUsb_ScoAllocTransferContextsImpl(_DEVICE_EXTENSION *,ulong,ulong,ulong,_RESOURCE_QUEUE *,_LIST_ENTRY *)

- ea: `0x1400045e4`
- end: `0x140004654`
- name: `?BthUsb_ScoAllocTransferContextsImpl@@YAJPEAU_DEVICE_EXTENSION@@KKKPEAU_RESOURCE_QUEUE@@PEAU_LIST_ENTRY@@@Z`
- size: `112`
- prototype: `__int64 __usercall@<rax>(struct _DEVICE_EXTENSION *@<rcx>, unsigned int@<edx>, unsigned int@<r8d>, unsigned int@<r9d>, struct _RESOURCE_QUEUE *, struct _LIST_ENTRY *)`
- caller_count: `2`
- callee_count: `4`
- tags: `loader_planting`

## callers

- `0x140007334`
- `0x140008d90`

## callees

- `0x140004088`
- `0x1400045e4`
- `0x1400049f0`
- `0x140004de0`

## pseudocode

```c
__int64 __fastcall BthUsb_ScoAllocTransferContextsImpl(
        struct _DEVICE_EXTENSION *a1,
        unsigned int a2,
        unsigned int a3,
        unsigned int a4,
        struct _RESOURCE_QUEUE *a5,
        struct _LIST_ENTRY *a6)
{
  unsigned int v6; // ebx
  int v7; // esi
  struct _SCO_USB_TRANSFER_CTX *v12; // rax

  v6 = 0;
  v7 = 0;
  if ( a2 )
  {
    while ( 1 )
    {
      v12 = BthUsb_ScoAllocTransferContextImpl(a1, a3, a4, a5);
      if ( !v12 )
        break;
      BthUsb_ScoFreeTransferContextImpl(a1, a6, v12);
      if ( ++v7 >= a2 )
        return v6;
    }
    v6 = -1073741670;
    BthUsb_ScoDestroyTransferContextsImpl(a1, a6);
  }
  return v6;
}

```

## disassembly

```asm
0x1400045e4  push    rbx
0x1400045e6  push    rbp
0x1400045e7  push    rsi
0x1400045e8  push    rdi
0x1400045e9  push    r14
0x1400045eb  push    r15
0x1400045ed  sub     rsp, 28h
0x1400045f1  xor     ebx, ebx
0x1400045f3  xor     esi, esi
0x1400045f5  mov     r14d, r9d
0x1400045f8  mov     r15d, r8d
0x1400045fb  mov     ebp, edx
0x1400045fd  mov     rdi, rcx
0x140004600  test    edx, edx
0x140004602  jz      short loc_140004644
0x140004604  mov     r9, [rsp+58h+arg_20]; struct _RESOURCE_QUEUE *
0x14000460c  mov     r8d, r14d; unsigned int
0x14000460f  mov     edx, r15d; unsigned int
0x140004612  mov     rcx, rdi; struct _DEVICE_EXTENSION *
0x140004615  call    ?BthUsb_ScoAllocTransferContextImpl@@YAPEAU_SCO_USB_TRANSFER_CTX@@PEAU_DEVICE_EXTENSION@@KKPEAU_RESOURCE_QUEUE@@@Z; BthUsb_ScoAllocTransferContextImpl(_DEVICE_EXTENSION *,ulong,ulong,_RESOURCE_QUEUE *)
0x14000461a  mov     rdx, [rsp+58h+arg_28]; struct _LIST_ENTRY *
0x140004622  mov     rcx, rdi; void *
0x140004625  test    rax, rax
0x140004628  jz      short loc_14000463A
0x14000462a  mov     r8, rax; void *
0x14000462d  call    ?BthUsb_ScoFreeTransferContextImpl@@YAXPEAXPEAU_LIST_ENTRY@@0@Z; BthUsb_ScoFreeTransferContextImpl(void *,_LIST_ENTRY *,void *)
0x140004632  inc     esi
0x140004634  cmp     esi, ebp
0x140004636  jb      short loc_140004604
0x140004638  jmp     short loc_140004644
0x14000463a  mov     ebx, 0C000009Ah
0x14000463f  call    ?BthUsb_ScoDestroyTransferContextsImpl@@YAXPEAXPEAU_LIST_ENTRY@@@Z; BthUsb_ScoDestroyTransferContextsImpl(void *,_LIST_ENTRY *)
0x140004644  mov     eax, ebx
0x140004646  add     rsp, 28h
0x14000464a  pop     r15
0x14000464c  pop     r14
0x14000464e  pop     rdi
0x14000464f  pop     rsi
0x140004650  pop     rbp
0x140004651  pop     rbx
0x140004652  retn
```
