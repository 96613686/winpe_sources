# PrefixTreeAllocator::allocate(unsigned __int64,bool)

- ea: `0x140011a90`
- end: `0x140011b0c`
- name: `?allocate@PrefixTreeAllocator@@SAPEAX_K_N@Z`
- size: `124`
- prototype: `void *__fastcall(unsigned __int64, bool)`
- caller_count: `2`
- callee_count: `1`
- tags: `authz_impersonation`

## callers

- `0x140012070`
- `0x140012090`

## callees

- `0x140011a90`

## import_xrefs

- `ntoskrnl!ExAllocatePool2` at `0x140011afa`
- `ntoskrnl!ExAllocatePool2` at `0x140011afa`
- `ntoskrnl!ExAllocateFromPagedLookasideList` at `0x140011ab1`
- `ntoskrnl!ExAllocateFromPagedLookasideList` at `0x140011ab1`

## pseudocode

```c
PVOID __fastcall PrefixTreeAllocator::allocate(__int64 a1, char a2)
{
  struct _PAGED_LOOKASIDE_LIST *v2; // rcx

  if ( PrefixTreeAllocator::LookasideInited && a2 )
  {
    switch ( a1 )
    {
      case 208LL:
        v2 = &PrefixTreeAllocator::PrefixEntryLookasideList;
        return ExAllocateFromPagedLookasideList(v2);
      case 80LL:
        v2 = &PrefixTreeAllocator::PrefixShortNameEntryLookasideList;
        return ExAllocateFromPagedLookasideList(v2);
      case 104LL:
        v2 = &PrefixTreeAllocator::PrefixTableLookasideList;
        return ExAllocateFromPagedLookasideList(v2);
      case 16LL:
        v2 = &PrefixTreeAllocator::PrefixTreeLookasideList;
        return ExAllocateFromPagedLookasideList(v2);
    }
  }
  return (PVOID)ExAllocatePool2(256, a1, 812664406);
}

```

## disassembly

```asm
0x140011a90  sub     rsp, 28h
0x140011a94  cmp     cs:?LookasideInited@PrefixTreeAllocator@@0_NA, 0; bool PrefixTreeAllocator::LookasideInited
0x140011a9b  jz      short loc_140011AEC
0x140011a9d  test    dl, dl
0x140011a9f  jz      short loc_140011AEC
0x140011aa1  cmp     rcx, 0D0h
0x140011aa8  jnz     short loc_140011ABF
0x140011aaa  lea     rcx, ?PrefixEntryLookasideList@PrefixTreeAllocator@@0U_PAGED_LOOKASIDE_LIST@@A; Lookaside
0x140011ab1  call    cs:__imp_ExAllocateFromPagedLookasideList
0x140011ab8  nop     dword ptr [rax+rax+00h]
0x140011abd  jmp     short loc_140011B06
0x140011abf  cmp     rcx, 50h ; 'P'
0x140011ac3  jnz     short loc_140011ACE
0x140011ac5  lea     rcx, ?PrefixShortNameEntryLookasideList@PrefixTreeAllocator@@0U_PAGED_LOOKASIDE_LIST@@A; _PAGED_LOOKASIDE_LIST PrefixTreeAllocator::PrefixShortNameEntryLookasideList
0x140011acc  jmp     short loc_140011AB1
0x140011ace  cmp     rcx, 68h ; 'h'
0x140011ad2  jnz     short loc_140011ADD
0x140011ad4  lea     rcx, ?PrefixTableLookasideList@PrefixTreeAllocator@@0U_PAGED_LOOKASIDE_LIST@@A; _PAGED_LOOKASIDE_LIST PrefixTreeAllocator::PrefixTableLookasideList
0x140011adb  jmp     short loc_140011AB1
0x140011add  cmp     rcx, 10h
0x140011ae1  jnz     short loc_140011AEC
0x140011ae3  lea     rcx, ?PrefixTreeLookasideList@PrefixTreeAllocator@@0U_PAGED_LOOKASIDE_LIST@@A; _PAGED_LOOKASIDE_LIST PrefixTreeAllocator::PrefixTreeLookasideList
0x140011aea  jmp     short loc_140011AB1
0x140011aec  mov     rdx, rcx
0x140011aef  mov     r8d, 30704656h
0x140011af5  mov     ecx, 100h
0x140011afa  call    cs:__imp_ExAllocatePool2
0x140011b01  nop     dword ptr [rax+rax+00h]
0x140011b06  add     rsp, 28h
0x140011b0a  retn
```
