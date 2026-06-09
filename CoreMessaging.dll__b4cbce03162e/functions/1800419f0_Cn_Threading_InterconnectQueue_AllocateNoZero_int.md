# Cn::Threading::InterconnectQueue::AllocateNoZero(int)

- ea: `0x1800419f0`
- end: `0x180041a4d`
- name: `?AllocateNoZero@InterconnectQueue@Threading@Cn@@CAPEAXH@Z`
- size: `93`
- prototype: `void *__fastcall(int)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation`

## callers

- `0x18004177c`

## callees

- `0x1800419f0`
- `0x18004c408`
- `0x1800c7d64`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__aligned_offset_malloc` at `0x180041a0c`
- `api-ms-win-crt-private-l1-1-0!_o__aligned_offset_malloc` at `0x180041a0c`
- `api-ms-win-core-interlocked-l1-1-0!InterlockedPopEntrySList` at `0x180041a28`
- `api-ms-win-core-interlocked-l1-1-0!InterlockedPopEntrySList` at `0x180041a28`

## pseudocode

```c
struct _SLIST_ENTRY *__fastcall Cn::Threading::InterconnectQueue::AllocateNoZero(int a1)
{
  unsigned __int64 v1; // rbx
  struct _SLIST_ENTRY *result; // rax
  PSLIST_ENTRY NoZero; // rax
  __int64 v4; // rcx
  __int64 v5; // r8

  if ( !a1 )
    return 0;
  if ( a1 <= 48 )
  {
    NoZero = InterlockedPopEntrySList(&Cn::Threading::InterconnectQueue::s_poolLookaside);
    if ( !NoZero )
      NoZero = (PSLIST_ENTRY)Cn::Engine::Heap::AlignedAllocateNoZero(v4, 64, v5, 0);
    return NoZero + 1;
  }
  else
  {
    v1 = a1;
    result = (struct _SLIST_ENTRY *)_aligned_offset_malloc(a1, 0x10u, 0);
    if ( !result )
      CFlat::Abandonment::OutOfMemory(v1);
  }
  return result;
}

```

## disassembly

```asm
0x1800419f0  push    rbx
0x1800419f2  sub     rsp, 20h
0x1800419f6  test    ecx, ecx
0x1800419f8  jz      short loc_180041A1D
0x1800419fa  cmp     ecx, 30h ; '0'
0x1800419fd  jle     short loc_180041A21
0x1800419ff  xor     r8d, r8d; Offset
0x180041a02  movsxd  rbx, ecx
0x180041a05  mov     rcx, rbx; Size
0x180041a08  lea     edx, [r8+10h]; Alignment
0x180041a0c  call    cs:__imp__aligned_offset_malloc
0x180041a12  test    rax, rax
0x180041a15  jz      short loc_180041A44
0x180041a17  add     rsp, 20h
0x180041a1b  pop     rbx
0x180041a1c  retn
0x180041a1d  xor     eax, eax
0x180041a1f  jmp     short loc_180041A17
0x180041a21  lea     rcx, ?s_poolLookaside@InterconnectQueue@Threading@Cn@@0T_SLIST_HEADER@@A; ListHead
0x180041a28  call    cs:__imp_InterlockedPopEntrySList
0x180041a2e  test    rax, rax
0x180041a31  jnz     short loc_180041A3E
0x180041a33  xor     r9d, r9d
0x180041a36  lea     edx, [rax+40h]
0x180041a39  call    ?AlignedAllocateNoZero@Heap@Engine@Cn@@SAPEAXUAllocType@23@_K11@Z; Cn::Engine::Heap::AlignedAllocateNoZero(Cn::Engine::AllocType,unsigned __int64,unsigned __int64,unsigned __int64)
0x180041a3e  add     rax, 10h
0x180041a42  jmp     short loc_180041A17
0x180041a44  mov     rcx, rbx; unsigned __int64
0x180041a47  call    ?OutOfMemory@Abandonment@CFlat@@SAX_K@Z; CFlat::Abandonment::OutOfMemory(unsigned __int64)
```
