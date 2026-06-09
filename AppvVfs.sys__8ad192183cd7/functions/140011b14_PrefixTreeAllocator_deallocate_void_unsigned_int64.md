# PrefixTreeAllocator::deallocate(void *,unsigned __int64)

- ea: `0x140011b14`
- end: `0x140011b94`
- name: `?deallocate@PrefixTreeAllocator@@SAXPEAX_K@Z`
- size: `128`
- prototype: `void __fastcall(PVOID Entry, __int64)`
- caller_count: `2`
- callee_count: `1`
- tags: `authz_impersonation`

## callers

- `0x1400120f0`
- `0x140012110`

## callees

- `0x140011b14`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x140011b82`
- `ntoskrnl!ExFreePoolWithTag` at `0x140011b82`
- `ntoskrnl!ExFreeToPagedLookasideList` at `0x140011b6f`
- `ntoskrnl!ExFreeToPagedLookasideList` at `0x140011b6f`

## pseudocode

```c
void __fastcall PrefixTreeAllocator::deallocate(PVOID Entry, __int64 a2)
{
  PVOID v2; // rdx
  struct _PAGED_LOOKASIDE_LIST *v3; // rcx

  if ( PrefixTreeAllocator::LookasideInited && a2 )
  {
    switch ( a2 )
    {
      case 208LL:
        v2 = Entry;
        v3 = &PrefixTreeAllocator::PrefixEntryLookasideList;
        break;
      case 80LL:
        v2 = Entry;
        v3 = &PrefixTreeAllocator::PrefixShortNameEntryLookasideList;
        break;
      case 104LL:
        v2 = Entry;
        v3 = &PrefixTreeAllocator::PrefixTableLookasideList;
        break;
      case 16LL:
        v2 = Entry;
        v3 = &PrefixTreeAllocator::PrefixTreeLookasideList;
        break;
      default:
        return;
    }
    ExFreeToPagedLookasideList(v3, v2);
  }
  else
  {
    ExFreePoolWithTag(Entry, 0x30704656u);
  }
}

```

## disassembly

```asm
0x140011b14  sub     rsp, 28h
0x140011b18  cmp     cs:?LookasideInited@PrefixTreeAllocator@@0_NA, 0; bool PrefixTreeAllocator::LookasideInited
0x140011b1f  jz      short loc_140011B7D
0x140011b21  test    rdx, rdx
0x140011b24  jz      short loc_140011B7D
0x140011b26  cmp     rdx, 0D0h
0x140011b2d  jnz     short loc_140011B3B
0x140011b2f  mov     rdx, rcx
0x140011b32  lea     rcx, ?PrefixEntryLookasideList@PrefixTreeAllocator@@0U_PAGED_LOOKASIDE_LIST@@A; _PAGED_LOOKASIDE_LIST PrefixTreeAllocator::PrefixEntryLookasideList
0x140011b39  jmp     short loc_140011B6F
0x140011b3b  cmp     rdx, 50h ; 'P'
0x140011b3f  jnz     short loc_140011B4D
0x140011b41  mov     rdx, rcx
0x140011b44  lea     rcx, ?PrefixShortNameEntryLookasideList@PrefixTreeAllocator@@0U_PAGED_LOOKASIDE_LIST@@A; _PAGED_LOOKASIDE_LIST PrefixTreeAllocator::PrefixShortNameEntryLookasideList
0x140011b4b  jmp     short loc_140011B6F
0x140011b4d  cmp     rdx, 68h ; 'h'
0x140011b51  jnz     short loc_140011B5F
0x140011b53  mov     rdx, rcx
0x140011b56  lea     rcx, ?PrefixTableLookasideList@PrefixTreeAllocator@@0U_PAGED_LOOKASIDE_LIST@@A; _PAGED_LOOKASIDE_LIST PrefixTreeAllocator::PrefixTableLookasideList
0x140011b5d  jmp     short loc_140011B6F
0x140011b5f  cmp     rdx, 10h
0x140011b63  jnz     short loc_140011B8E
0x140011b65  mov     rdx, rcx; Entry
0x140011b68  lea     rcx, ?PrefixTreeLookasideList@PrefixTreeAllocator@@0U_PAGED_LOOKASIDE_LIST@@A; Lookaside
0x140011b6f  call    cs:__imp_ExFreeToPagedLookasideList
0x140011b76  nop     dword ptr [rax+rax+00h]
0x140011b7b  jmp     short loc_140011B8E
0x140011b7d  mov     edx, 30704656h; Tag
0x140011b82  call    cs:__imp_ExFreePoolWithTag
0x140011b89  nop     dword ptr [rax+rax+00h]
0x140011b8e  add     rsp, 28h
0x140011b92  retn
```
