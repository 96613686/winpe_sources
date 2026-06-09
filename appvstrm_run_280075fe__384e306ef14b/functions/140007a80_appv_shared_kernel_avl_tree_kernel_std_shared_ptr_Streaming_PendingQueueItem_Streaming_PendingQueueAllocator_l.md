# appv::shared::kernel::avl_tree<kernel_std::shared_ptr<Streaming::PendingQueueItem>,Streaming::PendingQueueAllocator,less<kernel_std::shared_ptr<Streaming::PendingQueueItem>>>::avl_tree_order(_RTL_AVL_TABLE *,void *,void *)

- ea: `0x140007a80`
- end: `0x140007aa1`
- name: `?avl_tree_order@?$avl_tree@V?$shared_ptr@UPendingQueueItem@Streaming@@@kernel_std@@UPendingQueueAllocator@Streaming@@U?$less@V?$shared_ptr@UPendingQueueItem@Streaming@@@kernel_std@@@@@kernel@shared@appv@@CA?AW4_RTL_GENERIC_COMPARE_RESULTS@@PEAU_RTL_AVL_TABLE@@PEAX1@Z`
- size: `33`
- prototype: `RTL_AVL_COMPARE_ROUTINE`
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x140007a80`

## pseudocode

```c
__int64 __fastcall appv::shared::kernel::avl_tree<kernel_std::shared_ptr<Streaming::PendingQueueItem>,Streaming::PendingQueueAllocator,less<kernel_std::shared_ptr<Streaming::PendingQueueItem>>>::avl_tree_order(
        struct _RTL_AVL_TABLE *Table,
        unsigned __int64 **FirstStruct,
        unsigned __int64 **SecondStruct)
{
  unsigned __int64 v3; // rcx

  v3 = **SecondStruct;
  if ( **FirstStruct == v3 )
    return 2;
  else
    return **FirstStruct >= v3;
}

```

## disassembly

```asm
0x140007a80  mov     rax, [r8]
0x140007a83  mov     rcx, [rax]
0x140007a86  mov     rax, [rdx]
0x140007a89  cmp     [rax], rcx
0x140007a8c  jz      short loc_140007A9B
0x140007a8e  jnb     short loc_140007A94
0x140007a90  xor     eax, eax
0x140007a92  retn
0x140007a94  mov     eax, 1
0x140007a99  retn
0x140007a9b  mov     eax, 2
0x140007aa0  retn
```
