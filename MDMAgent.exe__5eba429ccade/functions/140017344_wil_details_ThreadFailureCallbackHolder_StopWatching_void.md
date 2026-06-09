# wil::details::ThreadFailureCallbackHolder::StopWatching(void)

- ea: `0x140017344`
- end: `0x1400173ab`
- name: `?StopWatching@ThreadFailureCallbackHolder@details@wil@@QEAAXXZ`
- size: `103`
- prototype: `void __fastcall(wil::details::ThreadFailureCallbackHolder *__hidden this)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x140012ab8`
- `0x140015d70`

## callees

- `0x140017344`
- `0x140019010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x14001734d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x14001734d`

## string_xrefs

- `0x140017369`: `MEMORY CORRUPTION: Calling code is leaking an activity thread-watcher and releasing it on another thread`

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
0x140017344  push    rbx
0x140017346  sub     rsp, 20h
0x14001734a  mov     rbx, rcx
0x14001734d  call    cs:__imp_GetCurrentThreadId
0x140017353  cmp     [rbx+18h], eax
0x140017356  jz      short loc_140017375
0x140017358  mov     rax, cs:?g_pfnReportFatalUsageError@details@wil@@3P6AXPEBDPEBX@_EEA; __annotation("Debug", "TelemetryAssert", "MEMORY CORRUPTION: Calling code is leaking an activity thread-watcher and releasing it on another thread")
0x14001735f  test    rax, rax
0x140017362  jz      short loc_140017375
0x140017364  mov     rdx, [rsp+28h]
0x140017369  lea     rcx, aMemoryCorrupti; "MEMORY CORRUPTION: Calling code is leak"...
0x140017370  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140017375  mov     rcx, [rbx]
0x140017378  mov     dword ptr [rbx+18h], 0
0x14001737f  jmp     short loc_14001738D
0x140017381  cmp     rax, rbx
0x140017384  jz      short loc_140017397
0x140017386  lea     rcx, [rax+10h]
0x14001738a  mov     [rbx], rcx
0x14001738d  mov     rax, [rcx]
0x140017390  test    rax, rax
0x140017393  jnz     short loc_140017381
0x140017395  jmp     short loc_14001739E
0x140017397  mov     rax, [rbx+10h]
0x14001739b  mov     [rcx], rax
0x14001739e  mov     qword ptr [rbx], 0
0x1400173a5  add     rsp, 20h
0x1400173a9  pop     rbx
0x1400173aa  retn
```
