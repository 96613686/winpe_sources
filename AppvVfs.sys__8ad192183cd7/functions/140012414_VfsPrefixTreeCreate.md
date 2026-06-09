# VfsPrefixTreeCreate

- ea: `0x140012414`
- end: `0x140012541`
- name: `VfsPrefixTreeCreate`
- size: `301`
- prototype: `__int64 __fastcall(PVOID **)`
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x140008910`

## callees

- `0x140011998`
- `0x140012414`

## import_xrefs

- `ntoskrnl!RtlInitializeGenericTableAvl` at `0x1400124d9`
- `ntoskrnl!RtlInitializeGenericTableAvl` at `0x1400124d9`
- `ntoskrnl!ExFreePoolWithTag` at `0x140012518`
- `ntoskrnl!ExFreePoolWithTag` at `0x140012518`
- `ntoskrnl!ExAllocatePool2` at `0x14001244f`
- `ntoskrnl!ExAllocatePool2` at `0x1400124a4`
- `ntoskrnl!ExAllocatePool2` at `0x14001244f`
- `ntoskrnl!ExAllocatePool2` at `0x1400124a4`
- `ntoskrnl!ExFreeToPagedLookasideList` at `0x140012502`
- `ntoskrnl!ExFreeToPagedLookasideList` at `0x140012502`
- `ntoskrnl!ExAllocateFromPagedLookasideList` at `0x140012431`
- `ntoskrnl!ExAllocateFromPagedLookasideList` at `0x140012486`
- `ntoskrnl!ExAllocateFromPagedLookasideList` at `0x140012431`
- `ntoskrnl!ExAllocateFromPagedLookasideList` at `0x140012486`

## pseudocode

```c
__int64 __fastcall VfsPrefixTreeCreate(PVOID **a1)
{
  PVOID *Pool2; // rax
  PVOID *v3; // rbx
  bool v4; // zf
  struct _RTL_AVL_TABLE *v5; // rax

  if ( PrefixTreeAllocator::LookasideInited )
    Pool2 = (PVOID *)ExAllocateFromPagedLookasideList(&PrefixTreeAllocator::PrefixTreeLookasideList);
  else
    Pool2 = (PVOID *)ExAllocatePool2(256, 16, 812664406);
  v3 = Pool2;
  if ( !Pool2 )
    goto LABEL_13;
  v4 = !PrefixTreeAllocator::LookasideInited;
  Pool2[1] = 0;
  *Pool2 = 0;
  if ( v4 )
    v5 = (struct _RTL_AVL_TABLE *)ExAllocatePool2(256, 104, 812664406);
  else
    v5 = (struct _RTL_AVL_TABLE *)ExAllocateFromPagedLookasideList(&PrefixTreeAllocator::PrefixTableLookasideList);
  *v3 = v5;
  if ( !v5 )
  {
    appv::shared::vfs::prefix_tree<PrefixTreeContext,PrefixTreeAllocator>::~prefix_tree<PrefixTreeContext,PrefixTreeAllocator>(v3);
    if ( PrefixTreeAllocator::LookasideInited )
      ExFreeToPagedLookasideList(&PrefixTreeAllocator::PrefixTreeLookasideList, v3);
    else
      ExFreePoolWithTag(v3, 0x30704656u);
LABEL_13:
    v3 = 0;
    goto LABEL_14;
  }
  RtlInitializeGenericTableAvl(
    v5,
    (PRTL_AVL_COMPARE_ROUTINE)appv::shared::vfs::named_avl_table<appv::shared::vfs::prefix_tree_name_entry<PrefixTreeContext>,PrefixTreeAllocator>::named_avl_compare,
    appv::shared::vfs::named_avl_table<appv::shared::vfs::prefix_tree_name_entry<PrefixTreeContext>,PrefixTreeAllocator>::named_avl_allocate,
    appv::shared::vfs::named_avl_table<appv::shared::vfs::prefix_tree_name_entry<PrefixTreeContext>,PrefixTreeAllocator>::named_avl_free,
    0);
LABEL_14:
  *a1 = v3;
  return v3 == 0 ? 0xC000009A : 0;
}

```

## disassembly

```asm
0x140012414  mov     [rsp+arg_0], rbx
0x140012419  push    rdi
0x14001241a  sub     rsp, 30h
0x14001241e  cmp     cs:?LookasideInited@PrefixTreeAllocator@@0_NA, 0; bool PrefixTreeAllocator::LookasideInited
0x140012425  mov     rdi, rcx
0x140012428  jz      short loc_14001243F
0x14001242a  lea     rcx, ?PrefixTreeLookasideList@PrefixTreeAllocator@@0U_PAGED_LOOKASIDE_LIST@@A; Lookaside
0x140012431  call    cs:__imp_ExAllocateFromPagedLookasideList
0x140012438  nop     dword ptr [rax+rax+00h]
0x14001243d  jmp     short loc_14001245B
0x14001243f  mov     edx, 10h
0x140012444  mov     r8d, 30704656h
0x14001244a  mov     ecx, 100h
0x14001244f  call    cs:__imp_ExAllocatePool2
0x140012456  nop     dword ptr [rax+rax+00h]
0x14001245b  mov     rbx, rax
0x14001245e  test    rax, rax
0x140012461  jz      loc_140012524
0x140012467  cmp     cs:?LookasideInited@PrefixTreeAllocator@@0_NA, 0; bool PrefixTreeAllocator::LookasideInited
0x14001246e  mov     qword ptr [rax+8], 0
0x140012476  mov     qword ptr [rax], 0
0x14001247d  jz      short loc_140012494
0x14001247f  lea     rcx, ?PrefixTableLookasideList@PrefixTreeAllocator@@0U_PAGED_LOOKASIDE_LIST@@A; Lookaside
0x140012486  call    cs:__imp_ExAllocateFromPagedLookasideList
0x14001248d  nop     dword ptr [rax+rax+00h]
0x140012492  jmp     short loc_1400124B0
0x140012494  mov     edx, 68h ; 'h'
0x140012499  mov     r8d, 30704656h
0x14001249f  mov     ecx, 100h
0x1400124a4  call    cs:__imp_ExAllocatePool2
0x1400124ab  nop     dword ptr [rax+rax+00h]
0x1400124b0  mov     [rbx], rax
0x1400124b3  test    rax, rax
0x1400124b6  jz      short loc_1400124E7
0x1400124b8  lea     r9, ?named_avl_free@?$named_avl_table@U?$prefix_tree_name_entry@VPrefixTreeContext@@@vfs@shared@appv@@VPrefixTreeAllocator@@@vfs@shared@appv@@CAXPEAU_RTL_AVL_TABLE@@PEAX@Z; FreeRoutine
0x1400124bf  mov     [rsp+38h+TableContext], 0; TableContext
0x1400124c8  lea     r8, ?named_avl_allocate@?$named_avl_table@U?$prefix_tree_name_entry@VPrefixTreeContext@@@vfs@shared@appv@@VPrefixTreeAllocator@@@vfs@shared@appv@@CAPEAXPEAU_RTL_AVL_TABLE@@K@Z; AllocateRoutine
0x1400124cf  mov     rcx, rax; Table
0x1400124d2  lea     rdx, ?named_avl_compare@?$named_avl_table@U?$prefix_tree_name_entry@VPrefixTreeContext@@@vfs@shared@appv@@VPrefixTreeAllocator@@@vfs@shared@appv@@CA?AW4_RTL_GENERIC_COMPARE_RESULTS@@PEAU_RTL_AVL_TABLE@@PEAX1@Z; CompareRoutine
0x1400124d9  call    cs:__imp_RtlInitializeGenericTableAvl
0x1400124e0  nop     dword ptr [rax+rax+00h]
0x1400124e5  jmp     short loc_140012526
0x1400124e7  mov     rcx, rbx
0x1400124ea  call    ??1?$prefix_tree@VPrefixTreeContext@@VPrefixTreeAllocator@@@vfs@shared@appv@@QEAA@XZ; appv::shared::vfs::prefix_tree<PrefixTreeContext,PrefixTreeAllocator>::~prefix_tree<PrefixTreeContext,PrefixTreeAllocator>(void)
0x1400124ef  cmp     cs:?LookasideInited@PrefixTreeAllocator@@0_NA, 0; bool PrefixTreeAllocator::LookasideInited
0x1400124f6  jz      short loc_140012510
0x1400124f8  mov     rdx, rbx; Entry
0x1400124fb  lea     rcx, ?PrefixTreeLookasideList@PrefixTreeAllocator@@0U_PAGED_LOOKASIDE_LIST@@A; Lookaside
0x140012502  call    cs:__imp_ExFreeToPagedLookasideList
0x140012509  nop     dword ptr [rax+rax+00h]
0x14001250e  jmp     short loc_140012524
0x140012510  mov     edx, 30704656h; Tag
0x140012515  mov     rcx, rbx; P
0x140012518  call    cs:__imp_ExFreePoolWithTag
0x14001251f  nop     dword ptr [rax+rax+00h]
0x140012524  xor     ebx, ebx
0x140012526  mov     [rdi], rbx
0x140012529  neg     rbx
0x14001252c  mov     rbx, [rsp+38h+arg_0]
0x140012531  sbb     eax, eax
0x140012533  not     eax
0x140012535  and     eax, 0C000009Ah
0x14001253a  add     rsp, 30h
0x14001253e  pop     rdi
0x14001253f  retn
```
