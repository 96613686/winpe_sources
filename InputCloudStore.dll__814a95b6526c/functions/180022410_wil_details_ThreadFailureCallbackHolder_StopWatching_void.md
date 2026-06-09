# wil::details::ThreadFailureCallbackHolder::StopWatching(void)

- ea: `0x180022410`
- end: `0x180022477`
- name: `?StopWatching@ThreadFailureCallbackHolder@details@wil@@QEAAXXZ`
- size: `103`
- prototype: `void __fastcall(wil::details::ThreadFailureCallbackHolder *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x18001b768`

## callees

- `0x180022410`
- `0x180031010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180022419`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180022419`

## string_xrefs

- `0x180022435`: `MEMORY CORRUPTION: Calling code is leaking an activity thread-watcher and releasing it on another thread`

## pseudocode

```c
void __fastcall wil::details::ThreadFailureCallbackHolder::StopWatching(
        wil::details::ThreadFailureCallbackHolder *this)
{
  wil::details::ThreadFailureCallbackHolder **v2; // rcx
  wil::details::ThreadFailureCallbackHolder *v3; // rax
  void *retaddr; // [rsp+28h] [rbp+0h]

  if ( *((_DWORD *)this + 6) != GetCurrentThreadId() && wil::details::g_pfnReportFatalUsageError )
    wil::details::g_pfnReportFatalUsageError(
      "MEMORY CORRUPTION: Calling code is leaking an activity thread-watcher and releasing it on another thread",
      retaddr);
  v2 = *(wil::details::ThreadFailureCallbackHolder ***)this;
  *((_DWORD *)this + 6) = 0;
  while ( 1 )
  {
    v3 = *v2;
    if ( !*v2 )
      break;
    if ( v3 == this )
    {
      *v2 = (wil::details::ThreadFailureCallbackHolder *)*((_QWORD *)this + 2);
      break;
    }
    v2 = (wil::details::ThreadFailureCallbackHolder **)((char *)v3 + 16);
    *(_QWORD *)this = (char *)v3 + 16;
  }
  *(_QWORD *)this = 0;
}

```

## disassembly

```asm
0x180022410  push    rbx
0x180022412  sub     rsp, 20h
0x180022416  mov     rbx, rcx
0x180022419  call    cs:__imp_GetCurrentThreadId
0x18002241f  cmp     [rbx+18h], eax
0x180022422  jz      short loc_180022441
0x180022424  mov     rax, cs:?g_pfnReportFatalUsageError@details@wil@@3P6AXPEBDPEBX@_EEA
0x18002242b  test    rax, rax
0x18002242e  jz      short loc_180022441
0x180022430  mov     rdx, [rsp+28h]
0x180022435  lea     rcx, aMemoryCorrupti; "MEMORY CORRUPTION: Calling code is leak"...
0x18002243c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180022441  mov     rcx, [rbx]
0x180022444  mov     dword ptr [rbx+18h], 0
0x18002244b  jmp     short loc_180022459
0x18002244d  cmp     rax, rbx
0x180022450  jz      short loc_180022463
0x180022452  lea     rcx, [rax+10h]
0x180022456  mov     [rbx], rcx
0x180022459  mov     rax, [rcx]
0x18002245c  test    rax, rax
0x18002245f  jnz     short loc_18002244D
0x180022461  jmp     short loc_18002246A
0x180022463  mov     rax, [rbx+10h]
0x180022467  mov     [rcx], rax
0x18002246a  mov     qword ptr [rbx], 0
0x180022471  add     rsp, 20h
0x180022475  pop     rbx
0x180022476  retn
```
