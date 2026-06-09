# getCache

- ea: `0x1800164bc`
- end: `0x18001655d`
- name: `getCache`
- size: `161`
- prototype: ``
- caller_count: `3`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x18001620c`
- `0x180016318`
- `0x18001641c`

## callees

- `0x180004200`
- `0x180009430`
- `0x1800164bc`
- `0x18001b7a9`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!InitializeSRWLock` at `0x180016526`
- `api-ms-win-core-synch-l1-1-0!InitializeSRWLock` at `0x180016526`

## pseudocode

```c
__int64 getCache()
{
  __int64 v0; // rdi
  void *v1; // rax
  void *v2; // rbx
  RTL_SRWLOCK *v3; // rax
  RTL_SRWLOCK *v4; // rbx

  v0 = 0;
  if ( !g_handleCache )
  {
    v1 = (void *)SafeAllocaAllocateFromHeap(1792);
    v2 = v1;
    if ( !v1 )
      return v0;
    memset_0(v1, 0, 0x700u);
    if ( _InterlockedCompareExchange64(&g_handleCache, (signed __int64)v2, 0) )
      MSCryptFree(v2);
  }
  if ( g_pHandleCacheLock )
    return g_handleCache;
  v3 = (RTL_SRWLOCK *)SafeAllocaAllocateFromHeap(8);
  v4 = v3;
  if ( v3 )
  {
    InitializeSRWLock(v3);
    if ( _InterlockedCompareExchange64((volatile signed __int64 *)&g_pHandleCacheLock, (signed __int64)v4, 0) )
      MSCryptFree(v4);
    return g_handleCache;
  }
  return v0;
}

```

## disassembly

```asm
0x1800164bc  mov     [rsp+arg_0], rbx
0x1800164c1  push    rdi
0x1800164c2  sub     rsp, 20h
0x1800164c6  xor     edi, edi
0x1800164c8  cmp     cs:g_handleCache, rdi
0x1800164cf  jnz     short loc_180016508
0x1800164d1  mov     ecx, 700h
0x1800164d6  call    SafeAllocaAllocateFromHeap
0x1800164db  mov     rbx, rax
0x1800164de  test    rax, rax
0x1800164e1  jz      short loc_18001654E
0x1800164e3  xor     edx, edx; Val
0x1800164e5  mov     r8d, 700h; Size
0x1800164eb  mov     rcx, rax; void *
0x1800164ee  call    memset_0
0x1800164f3  xor     eax, eax
0x1800164f5  lock cmpxchg cs:g_handleCache, rbx
0x1800164fe  jz      short loc_180016508
0x180016500  mov     rcx, rbx
0x180016503  call    MSCryptFree
0x180016508  cmp     cs:g_pHandleCacheLock, rdi
0x18001650f  jnz     short loc_180016547
0x180016511  mov     ecx, 8
0x180016516  call    SafeAllocaAllocateFromHeap
0x18001651b  mov     rbx, rax
0x18001651e  test    rax, rax
0x180016521  jz      short loc_18001654E
0x180016523  mov     rcx, rax; SRWLock
0x180016526  call    cs:__imp_InitializeSRWLock
0x18001652d  nop     dword ptr [rax+rax+00h]
0x180016532  xor     eax, eax
0x180016534  lock cmpxchg cs:g_pHandleCacheLock, rbx
0x18001653d  jz      short loc_180016547
0x18001653f  mov     rcx, rbx
0x180016542  call    MSCryptFree
0x180016547  mov     rdi, cs:g_handleCache
0x18001654e  mov     rbx, [rsp+28h+arg_0]
0x180016553  mov     rax, rdi
0x180016556  add     rsp, 20h
0x18001655a  pop     rdi
0x18001655b  retn
```
