# appv::shared::vfs::prefix_tree<PrefixTreeContext,PrefixTreeAllocator>::~prefix_tree<PrefixTreeContext,PrefixTreeAllocator>(void)

- ea: `0x140011998`
- end: `0x140011a5e`
- name: `??1?$prefix_tree@VPrefixTreeContext@@VPrefixTreeAllocator@@@vfs@shared@appv@@QEAA@XZ`
- size: `198`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `authz_impersonation`

## callers

- `0x140008a04`
- `0x140012414`

## callees

- `0x140011998`
- `0x140012130`

## import_xrefs

- `ntoskrnl!RtlIsGenericTableEmptyAvl` at `0x1400119b5`
- `ntoskrnl!RtlIsGenericTableEmptyAvl` at `0x140011a0b`
- `ntoskrnl!RtlIsGenericTableEmptyAvl` at `0x1400119b5`
- `ntoskrnl!RtlIsGenericTableEmptyAvl` at `0x140011a0b`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400119ef`
- `ntoskrnl!ExFreePoolWithTag` at `0x140011a44`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400119ef`
- `ntoskrnl!ExFreePoolWithTag` at `0x140011a44`
- `ntoskrnl!ExFreeToPagedLookasideList` at `0x1400119dc`
- `ntoskrnl!ExFreeToPagedLookasideList` at `0x140011a31`
- `ntoskrnl!ExFreeToPagedLookasideList` at `0x1400119dc`
- `ntoskrnl!ExFreeToPagedLookasideList` at `0x140011a31`

## pseudocode

```c
void __fastcall appv::shared::vfs::prefix_tree<PrefixTreeContext,PrefixTreeAllocator>::~prefix_tree<PrefixTreeContext,PrefixTreeAllocator>(
        PVOID *a1)
{
  struct _RTL_AVL_TABLE *v2; // rcx

  if ( *a1 )
    appv::shared::vfs::prefix_tree<PrefixTreeContext,PrefixTreeAllocator>::remove_directory(a1);
  v2 = (struct _RTL_AVL_TABLE *)a1[1];
  if ( v2 && RtlIsGenericTableEmptyAvl(v2) )
  {
    if ( PrefixTreeAllocator::LookasideInited )
      ExFreeToPagedLookasideList(&PrefixTreeAllocator::PrefixTableLookasideList, a1[1]);
    else
      ExFreePoolWithTag(a1[1], 0x30704656u);
    a1[1] = 0;
  }
  if ( *a1 && RtlIsGenericTableEmptyAvl((PRTL_AVL_TABLE)*a1) )
  {
    if ( PrefixTreeAllocator::LookasideInited )
      ExFreeToPagedLookasideList(&PrefixTreeAllocator::PrefixTableLookasideList, *a1);
    else
      ExFreePoolWithTag(*a1, 0x30704656u);
    *a1 = 0;
  }
}

```

## disassembly

```asm
0x140011998  push    rbx
0x14001199a  sub     rsp, 20h
0x14001199e  cmp     qword ptr [rcx], 0
0x1400119a2  mov     rbx, rcx
0x1400119a5  jz      short loc_1400119AC
0x1400119a7  call    ?remove_directory@?$prefix_tree@VPrefixTreeContext@@VPrefixTreeAllocator@@@vfs@shared@appv@@CAXAEAUprefix_tree_table@234@@Z; appv::shared::vfs::prefix_tree<PrefixTreeContext,PrefixTreeAllocator>::remove_directory(appv::shared::vfs::prefix_tree_table &)
0x1400119ac  mov     rcx, [rbx+8]; Table
0x1400119b0  test    rcx, rcx
0x1400119b3  jz      short loc_140011A03
0x1400119b5  call    cs:__imp_RtlIsGenericTableEmptyAvl
0x1400119bc  nop     dword ptr [rax+rax+00h]
0x1400119c1  test    al, al
0x1400119c3  jz      short loc_140011A03
0x1400119c5  cmp     cs:?LookasideInited@PrefixTreeAllocator@@0_NA, 0; bool PrefixTreeAllocator::LookasideInited
0x1400119cc  mov     rcx, [rbx+8]; P
0x1400119d0  jz      short loc_1400119EA
0x1400119d2  mov     rdx, rcx; Entry
0x1400119d5  lea     rcx, ?PrefixTableLookasideList@PrefixTreeAllocator@@0U_PAGED_LOOKASIDE_LIST@@A; Lookaside
0x1400119dc  call    cs:__imp_ExFreeToPagedLookasideList
0x1400119e3  nop     dword ptr [rax+rax+00h]
0x1400119e8  jmp     short loc_1400119FB
0x1400119ea  mov     edx, 30704656h; Tag
0x1400119ef  call    cs:__imp_ExFreePoolWithTag
0x1400119f6  nop     dword ptr [rax+rax+00h]
0x1400119fb  mov     qword ptr [rbx+8], 0
0x140011a03  mov     rcx, [rbx]; Table
0x140011a06  test    rcx, rcx
0x140011a09  jz      short loc_140011A57
0x140011a0b  call    cs:__imp_RtlIsGenericTableEmptyAvl
0x140011a12  nop     dword ptr [rax+rax+00h]
0x140011a17  test    al, al
0x140011a19  jz      short loc_140011A57
0x140011a1b  cmp     cs:?LookasideInited@PrefixTreeAllocator@@0_NA, 0; bool PrefixTreeAllocator::LookasideInited
0x140011a22  mov     rcx, [rbx]; P
0x140011a25  jz      short loc_140011A3F
0x140011a27  mov     rdx, rcx; Entry
0x140011a2a  lea     rcx, ?PrefixTableLookasideList@PrefixTreeAllocator@@0U_PAGED_LOOKASIDE_LIST@@A; Lookaside
0x140011a31  call    cs:__imp_ExFreeToPagedLookasideList
0x140011a38  nop     dword ptr [rax+rax+00h]
0x140011a3d  jmp     short loc_140011A50
0x140011a3f  mov     edx, 30704656h; Tag
0x140011a44  call    cs:__imp_ExFreePoolWithTag
0x140011a4b  nop     dword ptr [rax+rax+00h]
0x140011a50  mov     qword ptr [rbx], 0
0x140011a57  add     rsp, 20h
0x140011a5b  pop     rbx
0x140011a5c  retn
```
