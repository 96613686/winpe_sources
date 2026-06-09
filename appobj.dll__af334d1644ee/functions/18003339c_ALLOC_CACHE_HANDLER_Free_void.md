# ALLOC_CACHE_HANDLER::Free(void *)

- ea: `0x18003339c`
- end: `0x180033422`
- name: `?Free@ALLOC_CACHE_HANDLER@@QEAAHPEAX@Z`
- size: `134`
- prototype: `__int64 __fastcall(ALLOC_CACHE_HANDLER *this, struct _SLIST_ENTRY *)`
- caller_count: `7`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x180002070`
- `0x180030b44`
- `0x180030d80`
- `0x1800311e8`
- `0x1800318d4`
- `0x180031f3c`
- `0x1800321e0`

## callees

- `0x18003339c`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800333b5`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800333b5`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800333ee`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800333ee`
- `api-ms-win-core-interlocked-l1-1-0!InterlockedPushEntrySList` at `0x180033400`
- `api-ms-win-core-interlocked-l1-1-0!InterlockedPushEntrySList` at `0x180033400`
- `api-ms-win-core-interlocked-l1-1-0!QueryDepthSList` at `0x1800333d4`
- `api-ms-win-core-interlocked-l1-1-0!QueryDepthSList` at `0x1800333d4`

## pseudocode

```c
__int64 __fastcall ALLOC_CACHE_HANDLER::Free(ALLOC_CACHE_HANDLER *this, struct _SLIST_ENTRY *a2)
{
  _QWORD *v2; // rbx
  union _SLIST_HEADER *v5; // rbx
  __int64 result; // rax

  v2 = (_QWORD *)*((_QWORD *)this + 3);
  v5 = (union _SLIST_HEADER *)(v2[1] * ((unsigned __int64)GetCurrentThreadId() % v2[2]) + *v2);
  if ( QueryDepthSList(v5) < *((int *)this + 3) )
  {
    InterlockedPushEntrySList(v5, a2);
  }
  else
  {
    HeapFree(ALLOC_CACHE_HANDLER::sm_hHeap, 0, a2);
    _InterlockedDecrement((volatile signed __int32 *)this + 16);
  }
  result = 1;
  _InterlockedAdd((volatile signed __int32 *)this + 48, 1u);
  return result;
}

```

## disassembly

```asm
0x18003339c  mov     [rsp+arg_0], rbx
0x1800333a1  mov     [rsp+arg_8], rsi
0x1800333a6  push    rdi
0x1800333a7  sub     rsp, 20h
0x1800333ab  mov     rbx, [rcx+18h]
0x1800333af  mov     rsi, rdx
0x1800333b2  mov     rdi, rcx
0x1800333b5  call    cs:__imp_GetCurrentThreadId
0x1800333bb  mov     eax, eax
0x1800333bd  xor     edx, edx
0x1800333bf  div     qword ptr [rbx+10h]
0x1800333c3  mov     r8d, edx
0x1800333c6  imul    r8, [rbx+8]
0x1800333cb  mov     rbx, [rbx]
0x1800333ce  add     rbx, r8
0x1800333d1  mov     rcx, rbx; ListHead
0x1800333d4  call    cs:__imp_QueryDepthSList
0x1800333da  movzx   eax, ax
0x1800333dd  cmp     eax, [rdi+0Ch]
0x1800333e0  jl      short loc_1800333FA
0x1800333e2  mov     rcx, cs:?sm_hHeap@ALLOC_CACHE_HANDLER@@0PEAXEA; hHeap
0x1800333e9  mov     r8, rsi; lpMem
0x1800333ec  xor     edx, edx; dwFlags
0x1800333ee  call    cs:__imp_HeapFree
0x1800333f4  lock dec dword ptr [rdi+40h]
0x1800333f8  jmp     short loc_180033406
0x1800333fa  mov     rdx, rsi; ListEntry
0x1800333fd  mov     rcx, rbx; ListHead
0x180033400  call    cs:__imp_InterlockedPushEntrySList
0x180033406  mov     eax, 1
0x18003340b  lock add [rdi+0C0h], eax
0x180033412  mov     rbx, [rsp+28h+arg_0]
0x180033417  mov     rsi, [rsp+28h+arg_8]
0x18003341c  add     rsp, 20h
0x180033420  pop     rdi
0x180033421  retn
```
