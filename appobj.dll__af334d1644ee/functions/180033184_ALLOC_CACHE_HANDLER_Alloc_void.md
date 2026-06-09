# ALLOC_CACHE_HANDLER::Alloc(void)

- ea: `0x180033184`
- end: `0x180033210`
- name: `?Alloc@ALLOC_CACHE_HANDLER@@QEAAPEAXXZ`
- size: `140`
- prototype: `void *__fastcall(ALLOC_CACHE_HANDLER *__hidden this)`
- caller_count: `4`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180002050`
- `0x18003090c`
- `0x18003093c`
- `0x180030a90`

## callees

- `0x180033184`
- `0x18003374c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180033208`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180033208`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18003319b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18003319b`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800331ce`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800331ce`
- `api-ms-win-core-interlocked-l1-1-0!InterlockedPopEntrySList` at `0x1800331b3`
- `api-ms-win-core-interlocked-l1-1-0!InterlockedPopEntrySList` at `0x1800331b3`

## pseudocode

```c
void *__fastcall ALLOC_CACHE_HANDLER::Alloc(ALLOC_CACHE_HANDLER *this)
{
  _QWORD *v2; // rbx
  DWORD CurrentThreadId; // eax
  void *v4; // rbx

  if ( *((int *)this + 3) <= 0
    || (v2 = (_QWORD *)*((_QWORD *)this + 3),
        CurrentThreadId = GetCurrentThreadId(),
        (v4 = InterlockedPopEntrySList((PSLIST_HEADER)(*v2 + v2[1] * ((unsigned __int64)CurrentThreadId % v2[2])))) == 0) )
  {
    v4 = HeapAlloc(ALLOC_CACHE_HANDLER::sm_hHeap, 0, *((unsigned int *)this + 4));
    if ( v4 )
    {
      _InterlockedIncrement((volatile signed __int32 *)this + 16);
    }
    else
    {
      v4 = ALLOC_CACHE_HANDLER::PopAnyFreeListEntry(this);
      if ( !v4 )
      {
        SetLastError(8u);
        return v4;
      }
    }
  }
  _InterlockedIncrement((volatile signed __int32 *)this + 32);
  return v4;
}

```

## disassembly

```asm
0x180033184  mov     [rsp+arg_0], rbx
0x180033189  push    rdi
0x18003318a  sub     rsp, 20h
0x18003318e  cmp     dword ptr [rcx+0Ch], 0
0x180033192  mov     rdi, rcx
0x180033195  jle     short loc_1800331C1
0x180033197  mov     rbx, [rcx+18h]
0x18003319b  call    cs:__imp_GetCurrentThreadId
0x1800331a1  mov     eax, eax
0x1800331a3  xor     edx, edx
0x1800331a5  div     qword ptr [rbx+10h]
0x1800331a9  mov     ecx, edx
0x1800331ab  imul    rcx, [rbx+8]
0x1800331b0  add     rcx, [rbx]; ListHead
0x1800331b3  call    cs:__imp_InterlockedPopEntrySList
0x1800331b9  mov     rbx, rax
0x1800331bc  test    rax, rax
0x1800331bf  jnz     short loc_1800331E0
0x1800331c1  mov     r8d, [rdi+10h]; dwBytes
0x1800331c5  xor     edx, edx; dwFlags
0x1800331c7  mov     rcx, cs:?sm_hHeap@ALLOC_CACHE_HANDLER@@0PEAXEA; hHeap
0x1800331ce  call    cs:__imp_HeapAlloc
0x1800331d4  mov     rbx, rax
0x1800331d7  test    rax, rax
0x1800331da  jz      short loc_1800331F5
0x1800331dc  lock inc dword ptr [rdi+40h]
0x1800331e0  lock inc dword ptr [rdi+80h]
0x1800331e7  mov     rax, rbx
0x1800331ea  mov     rbx, [rsp+28h+arg_0]
0x1800331ef  add     rsp, 20h
0x1800331f3  pop     rdi
0x1800331f4  retn
0x1800331f5  mov     rcx, rdi; this
0x1800331f8  call    ?PopAnyFreeListEntry@ALLOC_CACHE_HANDLER@@AEAAPEAXXZ; ALLOC_CACHE_HANDLER::PopAnyFreeListEntry(void)
0x1800331fd  mov     rbx, rax
0x180033200  test    rax, rax
0x180033203  jnz     short loc_1800331E0
0x180033205  lea     ecx, [rax+8]; dwErrCode
0x180033208  call    cs:__imp_SetLastError
0x18003320e  jmp     short loc_1800331E7
```
