# VfsDeleteMappingPrefixTable

- ea: `0x140008a04`
- end: `0x140008aa0`
- name: `VfsDeleteMappingPrefixTable`
- size: `156`
- prototype: `__int64 __fastcall(PVOID Entry)`
- caller_count: `2`
- callee_count: `2`
- tags: `authz_impersonation`

## callers

- `0x140008910`
- `0x1400093f0`

## callees

- `0x140008a04`
- `0x140011998`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x140008a4b`
- `ntoskrnl!ExFreePoolWithTag` at `0x140008a6a`
- `ntoskrnl!ExFreePoolWithTag` at `0x140008a4b`
- `ntoskrnl!ExFreePoolWithTag` at `0x140008a6a`
- `ntoskrnl!ExFreeToPagedLookasideList` at `0x140008a35`
- `ntoskrnl!ExFreeToPagedLookasideList` at `0x140008a88`
- `ntoskrnl!ExFreeToPagedLookasideList` at `0x140008a35`
- `ntoskrnl!ExFreeToPagedLookasideList` at `0x140008a88`

## pseudocode

```c
void __fastcall VfsDeleteMappingPrefixTable(_QWORD *Entry)
{
  void *v1; // rdi
  void *v3; // rcx

  v1 = (void *)Entry[4];
  if ( v1 )
  {
    appv::shared::vfs::prefix_tree<PrefixTreeContext,PrefixTreeAllocator>::~prefix_tree<PrefixTreeContext,PrefixTreeAllocator>(Entry[4]);
    if ( PrefixTreeAllocator::LookasideInited )
      ExFreeToPagedLookasideList(&PrefixTreeAllocator::PrefixTreeLookasideList, v1);
    else
      ExFreePoolWithTag(v1, 0x30704656u);
    Entry[4] = 0;
  }
  v3 = (void *)Entry[3];
  if ( v3 )
  {
    ExFreePoolWithTag(v3, 0);
    Entry[3] = 0;
  }
  ExFreeToPagedLookasideList(&stru_14001FA80, Entry);
}

```

## disassembly

```asm
0x140008a04  mov     [rsp+arg_0], rbx
0x140008a09  push    rdi
0x140008a0a  sub     rsp, 20h
0x140008a0e  mov     rdi, [rcx+20h]
0x140008a12  mov     rbx, rcx
0x140008a15  test    rdi, rdi
0x140008a18  jz      short loc_140008A5F
0x140008a1a  mov     rcx, rdi
0x140008a1d  call    ??1?$prefix_tree@VPrefixTreeContext@@VPrefixTreeAllocator@@@vfs@shared@appv@@QEAA@XZ; appv::shared::vfs::prefix_tree<PrefixTreeContext,PrefixTreeAllocator>::~prefix_tree<PrefixTreeContext,PrefixTreeAllocator>(void)
0x140008a22  cmp     cs:?LookasideInited@PrefixTreeAllocator@@0_NA, 0; bool PrefixTreeAllocator::LookasideInited
0x140008a29  jz      short loc_140008A43
0x140008a2b  mov     rdx, rdi; Entry
0x140008a2e  lea     rcx, ?PrefixTreeLookasideList@PrefixTreeAllocator@@0U_PAGED_LOOKASIDE_LIST@@A; Lookaside
0x140008a35  call    cs:__imp_ExFreeToPagedLookasideList
0x140008a3c  nop     dword ptr [rax+rax+00h]
0x140008a41  jmp     short loc_140008A57
0x140008a43  mov     edx, 30704656h; Tag
0x140008a48  mov     rcx, rdi; P
0x140008a4b  call    cs:__imp_ExFreePoolWithTag
0x140008a52  nop     dword ptr [rax+rax+00h]
0x140008a57  mov     qword ptr [rbx+20h], 0
0x140008a5f  mov     rcx, [rbx+18h]; P
0x140008a63  test    rcx, rcx
0x140008a66  jz      short loc_140008A7E
0x140008a68  xor     edx, edx; Tag
0x140008a6a  call    cs:__imp_ExFreePoolWithTag
0x140008a71  nop     dword ptr [rax+rax+00h]
0x140008a76  mov     qword ptr [rbx+18h], 0
0x140008a7e  mov     rdx, rbx; Entry
0x140008a81  lea     rcx, stru_14001FA80; Lookaside
0x140008a88  call    cs:__imp_ExFreeToPagedLookasideList
0x140008a8f  nop     dword ptr [rax+rax+00h]
0x140008a94  mov     rbx, [rsp+28h+arg_0]
0x140008a99  add     rsp, 20h
0x140008a9d  pop     rdi
0x140008a9e  retn
```
