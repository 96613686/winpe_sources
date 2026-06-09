# wil::details::ThreadFailureCallbackHolder::StopWatching(void)

- ea: `0x18001b4f8`
- end: `0x18001b55f`
- name: `?StopWatching@ThreadFailureCallbackHolder@details@wil@@QEAAXXZ`
- size: `103`
- prototype: `void __fastcall(wil::details::ThreadFailureCallbackHolder *this)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x180017310`
- `0x180018f40`

## callees

- `0x18001b4f8`
- `0x180021010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001b501`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001b501`

## string_xrefs

- `0x18001b51d`: `MEMORY CORRUPTION: Calling code is leaking an activity thread-watcher and releasing it on another thread`

## pseudocode

```c
void __fastcall wil::details::ThreadFailureCallbackHolder::StopWatching(
        wil::details::ThreadFailureCallbackHolder *this)
{
  wil::details::ThreadFailureCallbackHolder **m_ppThreadList; // rcx
  wil::details::ThreadFailureCallbackHolder *v3; // rax
  const void *retaddr; // [rsp+28h] [rbp+0h]

  if ( this->m_threadId != GetCurrentThreadId() && wil::details::g_pfnReportFatalUsageError )
    wil::details::g_pfnReportFatalUsageError(
      "MEMORY CORRUPTION: Calling code is leaking an activity thread-watcher and releasing it on another thread",
      retaddr);
  m_ppThreadList = this->m_ppThreadList;
  this->m_threadId = 0;
  while ( 1 )
  {
    v3 = *m_ppThreadList;
    if ( !*m_ppThreadList )
      break;
    if ( v3 == this )
    {
      *m_ppThreadList = this->m_pNext;
      break;
    }
    m_ppThreadList = &v3->m_pNext;
    this->m_ppThreadList = &v3->m_pNext;
  }
  this->m_ppThreadList = 0;
}

```

## disassembly

```asm
0x18001b4f8  push    rbx
0x18001b4fa  sub     rsp, 20h
0x18001b4fe  mov     rbx, this
0x18001b501  call    cs:__imp_GetCurrentThreadId
0x18001b507  cmp     [rbx+18h], eax
0x18001b50a  jz      short loc_18001B529
0x18001b50c  mov     rax, cs:?g_pfnReportFatalUsageError@details@wil@@3P6AXPEBDPEBX@_EEA; __annotation("Debug", "TelemetryAssert", "MEMORY CORRUPTION: Calling code is leaking an activity thread-watcher and releasing it on another thread")
0x18001b513  test    rax, rax
0x18001b516  jz      short loc_18001B529
0x18001b518  mov     rdx, [rsp+28h]
0x18001b51d  lea     this, aMemoryCorrupti; "MEMORY CORRUPTION: Calling code is leak"...
0x18001b524  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001b529  mov     this, [rbx]
0x18001b52c  mov     dword ptr [rbx+18h], 0
0x18001b533  jmp     short loc_18001B541
0x18001b535  cmp     rax, rbx
0x18001b538  jz      short loc_18001B54B
0x18001b53a  lea     this, [rax+10h]
0x18001b53e  mov     [rbx], this
0x18001b541  mov     rax, [this]
0x18001b544  test    rax, rax
0x18001b547  jnz     short loc_18001B535
0x18001b549  jmp     short loc_18001B552
0x18001b54b  mov     rax, [rbx+10h]
0x18001b54f  mov     [this], rax
0x18001b552  mov     qword ptr [rbx], 0
0x18001b559  add     rsp, 20h
0x18001b55d  pop     rbx
0x18001b55e  retn
```
