# VfsCleanupPrefixTreeLibrary

- ea: `0x1400086e8`
- end: `0x140008745`
- name: `VfsCleanupPrefixTreeLibrary`
- size: `93`
- prototype: ``
- caller_count: `1`
- callee_count: `0`
- tags: `authz_impersonation`

## callers

- `0x140024008`

## import_xrefs

- `ntoskrnl!ExDeletePagedLookasideList` at `0x1400086f3`
- `ntoskrnl!ExDeletePagedLookasideList` at `0x140008706`
- `ntoskrnl!ExDeletePagedLookasideList` at `0x140008719`
- `ntoskrnl!ExDeletePagedLookasideList` at `0x14000872c`
- `ntoskrnl!ExDeletePagedLookasideList` at `0x1400086f3`
- `ntoskrnl!ExDeletePagedLookasideList` at `0x140008706`
- `ntoskrnl!ExDeletePagedLookasideList` at `0x140008719`
- `ntoskrnl!ExDeletePagedLookasideList` at `0x14000872c`

## pseudocode

```c
void VfsCleanupPrefixTreeLibrary()
{
  ExDeletePagedLookasideList(&PrefixTreeAllocator::PrefixShortNameEntryLookasideList);
  ExDeletePagedLookasideList(&PrefixTreeAllocator::PrefixEntryLookasideList);
  ExDeletePagedLookasideList(&PrefixTreeAllocator::PrefixTableLookasideList);
  ExDeletePagedLookasideList(&PrefixTreeAllocator::PrefixTreeLookasideList);
  PrefixTreeAllocator::LookasideInited = 0;
}

```

## disassembly

```asm
0x1400086e8  sub     rsp, 28h
0x1400086ec  lea     rcx, ?PrefixShortNameEntryLookasideList@PrefixTreeAllocator@@0U_PAGED_LOOKASIDE_LIST@@A; Lookaside
0x1400086f3  call    cs:__imp_ExDeletePagedLookasideList
0x1400086fa  nop     dword ptr [rax+rax+00h]
0x1400086ff  lea     rcx, ?PrefixEntryLookasideList@PrefixTreeAllocator@@0U_PAGED_LOOKASIDE_LIST@@A; Lookaside
0x140008706  call    cs:__imp_ExDeletePagedLookasideList
0x14000870d  nop     dword ptr [rax+rax+00h]
0x140008712  lea     rcx, ?PrefixTableLookasideList@PrefixTreeAllocator@@0U_PAGED_LOOKASIDE_LIST@@A; Lookaside
0x140008719  call    cs:__imp_ExDeletePagedLookasideList
0x140008720  nop     dword ptr [rax+rax+00h]
0x140008725  lea     rcx, ?PrefixTreeLookasideList@PrefixTreeAllocator@@0U_PAGED_LOOKASIDE_LIST@@A; Lookaside
0x14000872c  call    cs:__imp_ExDeletePagedLookasideList
0x140008733  nop     dword ptr [rax+rax+00h]
0x140008738  mov     cs:?LookasideInited@PrefixTreeAllocator@@0_NA, 0; bool PrefixTreeAllocator::LookasideInited
0x14000873f  add     rsp, 28h
0x140008743  retn
```
