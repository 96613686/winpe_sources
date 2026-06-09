# EVENT_LOG::Terminate(void)

- ea: `0x180034b6c`
- end: `0x180034bfe`
- name: `?Terminate@EVENT_LOG@@SAXXZ`
- size: `146`
- prototype: `void(void)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x18003466c`

## callees

- `0x180034a60`
- `0x180034b6c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180034b86`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180034b86`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180034bd8`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180034bd8`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180034bca`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180034bca`

## pseudocode

```c
void EVENT_LOG::Terminate(void)
{
  char *v0; // rbx
  __int64 i; // rdi
  HANDLE ProcessHeap; // rax

  if ( EVENT_LOG::sm_fLockInitialized )
  {
    DeleteCriticalSection(&EVENT_LOG::sm_csLock);
    EVENT_LOG::sm_fLockInitialized = 0;
  }
  v0 = (char *)EVENT_LOG::sm_pEventLogSource;
  if ( EVENT_LOG::sm_pEventLogSource )
  {
    for ( i = 0; (unsigned int)i < EVENT_LOG::sm_cEventLogSource; i = (unsigned int)(i + 1) )
    {
      EVENT_LOG::DestroyEventLogSource((struct _EVENT_LOG_SOURCE *)&v0[24 * i]);
      v0 = (char *)EVENT_LOG::sm_pEventLogSource;
    }
    ProcessHeap = GetProcessHeap();
    HeapFree(ProcessHeap, 0, v0);
    EVENT_LOG::sm_pEventLogSource = 0;
    EVENT_LOG::sm_cEventLogSource = 0;
  }
}

```

## disassembly

```asm
0x180034b6c  mov     [rsp+arg_0], rbx
0x180034b71  push    rdi
0x180034b72  sub     rsp, 20h
0x180034b76  cmp     cs:?sm_fLockInitialized@EVENT_LOG@@0HA, 0; int EVENT_LOG::sm_fLockInitialized
0x180034b7d  jz      short loc_180034B96
0x180034b7f  lea     rcx, ?sm_csLock@EVENT_LOG@@0U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x180034b86  call    cs:__imp_DeleteCriticalSection
0x180034b8c  mov     cs:?sm_fLockInitialized@EVENT_LOG@@0HA, 0; int EVENT_LOG::sm_fLockInitialized
0x180034b96  mov     rbx, cs:?sm_pEventLogSource@EVENT_LOG@@0PEAU_EVENT_LOG_SOURCE@@EA; _EVENT_LOG_SOURCE * EVENT_LOG::sm_pEventLogSource
0x180034b9d  test    rbx, rbx
0x180034ba0  jz      short loc_180034BF3
0x180034ba2  xor     edi, edi
0x180034ba4  cmp     cs:?sm_cEventLogSource@EVENT_LOG@@0KA, edi; ulong EVENT_LOG::sm_cEventLogSource
0x180034baa  jbe     short loc_180034BCA
0x180034bac  lea     rcx, [rdi+rdi*2]
0x180034bb0  lea     rcx, [rbx+rcx*8]; struct _EVENT_LOG_SOURCE *
0x180034bb4  call    ?DestroyEventLogSource@EVENT_LOG@@CAXPEAU_EVENT_LOG_SOURCE@@@Z; EVENT_LOG::DestroyEventLogSource(_EVENT_LOG_SOURCE *)
0x180034bb9  mov     rbx, cs:?sm_pEventLogSource@EVENT_LOG@@0PEAU_EVENT_LOG_SOURCE@@EA; _EVENT_LOG_SOURCE * EVENT_LOG::sm_pEventLogSource
0x180034bc0  inc     edi
0x180034bc2  cmp     edi, cs:?sm_cEventLogSource@EVENT_LOG@@0KA; ulong EVENT_LOG::sm_cEventLogSource
0x180034bc8  jb      short loc_180034BAC
0x180034bca  call    cs:__imp_GetProcessHeap
0x180034bd0  mov     r8, rbx; lpMem
0x180034bd3  xor     edx, edx; dwFlags
0x180034bd5  mov     rcx, rax; hHeap
0x180034bd8  call    cs:__imp_HeapFree
0x180034bde  mov     cs:?sm_pEventLogSource@EVENT_LOG@@0PEAU_EVENT_LOG_SOURCE@@EA, 0; _EVENT_LOG_SOURCE * EVENT_LOG::sm_pEventLogSource
0x180034be9  mov     cs:?sm_cEventLogSource@EVENT_LOG@@0KA, 0; ulong EVENT_LOG::sm_cEventLogSource
0x180034bf3  mov     rbx, [rsp+28h+arg_0]
0x180034bf8  add     rsp, 20h
0x180034bfc  pop     rdi
0x180034bfd  retn
```
