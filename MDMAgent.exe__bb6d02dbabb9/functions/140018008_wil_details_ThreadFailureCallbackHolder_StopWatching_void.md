# wil::details::ThreadFailureCallbackHolder::StopWatching(void)

- ea: `0x140018008`
- end: `0x140018076`
- name: `?StopWatching@ThreadFailureCallbackHolder@details@wil@@QEAAXXZ`
- size: `110`
- prototype: `void __fastcall(wil::details::ThreadFailureCallbackHolder *__hidden this)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x1400133f0`
- `0x140016a00`

## callees

- `0x140018008`
- `0x14001a010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x140018011`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x140018011`

## string_xrefs

- `0x140018033`: `MEMORY CORRUPTION: Calling code is leaking an activity thread-watcher and releasing it on another thread`

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
0x140018008  push    rbx
0x14001800a  sub     rsp, 20h
0x14001800e  mov     rbx, rcx
0x140018011  call    cs:__imp_GetCurrentThreadId
0x140018018  nop     dword ptr [rax+rax+00h]
0x14001801d  cmp     [rbx+18h], eax
0x140018020  jz      short loc_14001803F
0x140018022  mov     rax, cs:?g_pfnReportFatalUsageError@details@wil@@3P6AXPEBDPEBX@_EEA; __annotation("Debug", "TelemetryAssert", "MEMORY CORRUPTION: Calling code is leaking an activity thread-watcher and releasing it on another thread")
0x140018029  test    rax, rax
0x14001802c  jz      short loc_14001803F
0x14001802e  mov     rdx, [rsp+28h]
0x140018033  lea     rcx, aMemoryCorrupti; "MEMORY CORRUPTION: Calling code is leak"...
0x14001803a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001803f  mov     rcx, [rbx]
0x140018042  mov     dword ptr [rbx+18h], 0
0x140018049  jmp     short loc_140018057
0x14001804b  cmp     rax, rbx
0x14001804e  jz      short loc_140018061
0x140018050  lea     rcx, [rax+10h]
0x140018054  mov     [rbx], rcx
0x140018057  mov     rax, [rcx]
0x14001805a  test    rax, rax
0x14001805d  jnz     short loc_14001804B
0x14001805f  jmp     short loc_140018068
0x140018061  mov     rax, [rbx+10h]
0x140018065  mov     [rcx], rax
0x140018068  mov     qword ptr [rbx], 0
0x14001806f  add     rsp, 20h
0x140018073  pop     rbx
0x140018074  retn
```
