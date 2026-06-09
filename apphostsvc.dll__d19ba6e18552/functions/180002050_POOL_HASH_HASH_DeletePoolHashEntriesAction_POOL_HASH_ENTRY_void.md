# POOL_HASH_HASH::DeletePoolHashEntriesAction(POOL_HASH_ENTRY *,void *)

- ea: `0x180002050`
- end: `0x180002078`
- name: `?DeletePoolHashEntriesAction@POOL_HASH_HASH@@SA?AW4LK_ACTION@@PEAVPOOL_HASH_ENTRY@@PEAX@Z`
- size: `40`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x180002050`

## pseudocode

```c
__int64 __fastcall POOL_HASH_HASH::DeletePoolHashEntriesAction(__int64 a1, __int64 *a2)
{
  __int64 v2; // r8

  v2 = *a2;
  if ( *(__int64 **)(*a2 + 8) != a2 )
    __fastfail(3u);
  *(_QWORD *)(a1 + 80) = v2;
  *(_QWORD *)(a1 + 88) = a2;
  *(_QWORD *)(v2 + 8) = a1 + 80;
  *a2 = a1 + 80;
  return 3;
}

```

## disassembly

```asm
0x180002050  mov     r8, [rdx]; public: static enum LK_ACTION HASH_POOL_HASH::DeletePoolHashEntriesAction(class POOL_HASH_ENTRY *, void *)
0x180002053  cmp     [r8+8], rdx
0x180002057  jz      short loc_180002060
0x180002059  mov     ecx, 3
0x18000205e  int     29h; Win8: RtlFailFast(ecx)
0x180002060  lea     rax, [rcx+50h]
0x180002064  mov     [rax], r8
0x180002067  mov     [rax+8], rdx
0x18000206b  mov     [r8+8], rax
0x18000206f  mov     [rdx], rax
0x180002072  mov     eax, 3
0x180002077  retn
```
