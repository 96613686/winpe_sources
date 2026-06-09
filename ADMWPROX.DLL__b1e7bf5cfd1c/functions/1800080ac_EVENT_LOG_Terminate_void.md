# EVENT_LOG::Terminate(void)

- ea: `0x1800080ac`
- end: `0x18000813e`
- name: `?Terminate@EVENT_LOG@@SAXXZ`
- size: `146`
- prototype: `void(void)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180006e00`

## callees

- `0x180007fbc`
- `0x1800080ac`

## import_xrefs

- `KERNEL32!DeleteCriticalSection` at `0x1800080c6`
- `KERNEL32!DeleteCriticalSection` at `0x1800080c6`
- `KERNEL32!GetProcessHeap` at `0x18000810a`
- `KERNEL32!GetProcessHeap` at `0x18000810a`
- `KERNEL32!HeapFree` at `0x180008118`
- `KERNEL32!HeapFree` at `0x180008118`

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
0x1800080ac  mov     [rsp+arg_0], rbx
0x1800080b1  push    rdi
0x1800080b2  sub     rsp, 20h
0x1800080b6  cmp     cs:?sm_fLockInitialized@EVENT_LOG@@0HA, 0; int EVENT_LOG::sm_fLockInitialized
0x1800080bd  jz      short loc_1800080D6
0x1800080bf  lea     rcx, ?sm_csLock@EVENT_LOG@@0U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x1800080c6  call    cs:__imp_DeleteCriticalSection
0x1800080cc  mov     cs:?sm_fLockInitialized@EVENT_LOG@@0HA, 0; int EVENT_LOG::sm_fLockInitialized
0x1800080d6  mov     rbx, cs:?sm_pEventLogSource@EVENT_LOG@@0PEAU_EVENT_LOG_SOURCE@@EA; _EVENT_LOG_SOURCE * EVENT_LOG::sm_pEventLogSource
0x1800080dd  test    rbx, rbx
0x1800080e0  jz      short loc_180008133
0x1800080e2  xor     edi, edi
0x1800080e4  cmp     cs:?sm_cEventLogSource@EVENT_LOG@@0KA, edi; ulong EVENT_LOG::sm_cEventLogSource
0x1800080ea  jbe     short loc_18000810A
0x1800080ec  lea     rcx, [rdi+rdi*2]
0x1800080f0  lea     rcx, [rbx+rcx*8]; struct _EVENT_LOG_SOURCE *
0x1800080f4  call    ?DestroyEventLogSource@EVENT_LOG@@CAXPEAU_EVENT_LOG_SOURCE@@@Z; EVENT_LOG::DestroyEventLogSource(_EVENT_LOG_SOURCE *)
0x1800080f9  mov     rbx, cs:?sm_pEventLogSource@EVENT_LOG@@0PEAU_EVENT_LOG_SOURCE@@EA; _EVENT_LOG_SOURCE * EVENT_LOG::sm_pEventLogSource
0x180008100  inc     edi
0x180008102  cmp     edi, cs:?sm_cEventLogSource@EVENT_LOG@@0KA; ulong EVENT_LOG::sm_cEventLogSource
0x180008108  jb      short loc_1800080EC
0x18000810a  call    cs:__imp_GetProcessHeap
0x180008110  mov     r8, rbx; lpMem
0x180008113  xor     edx, edx; dwFlags
0x180008115  mov     rcx, rax; hHeap
0x180008118  call    cs:__imp_HeapFree
0x18000811e  mov     cs:?sm_pEventLogSource@EVENT_LOG@@0PEAU_EVENT_LOG_SOURCE@@EA, 0; _EVENT_LOG_SOURCE * EVENT_LOG::sm_pEventLogSource
0x180008129  mov     cs:?sm_cEventLogSource@EVENT_LOG@@0KA, 0; ulong EVENT_LOG::sm_cEventLogSource
0x180008133  mov     rbx, [rsp+28h+arg_0]
0x180008138  add     rsp, 20h
0x18000813c  pop     rdi
0x18000813d  retn
```
