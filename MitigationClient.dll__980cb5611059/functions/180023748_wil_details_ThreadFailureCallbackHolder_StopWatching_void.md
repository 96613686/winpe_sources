# wil::details::ThreadFailureCallbackHolder::StopWatching(void)

- ea: `0x180023748`
- end: `0x1800237af`
- name: `?StopWatching@ThreadFailureCallbackHolder@details@wil@@QEAAXXZ`
- size: `103`
- prototype: `void __fastcall(wil::details::ThreadFailureCallbackHolder *__hidden this)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x18001a36c`
- `0x18001e13c`

## callees

- `0x180023748`
- `0x18005c010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180023751`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180023751`

## string_xrefs

- `0x18002376d`: `MEMORY CORRUPTION: Calling code is leaking an activity thread-watcher and releasing it on another thread`

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
0x180023748  push    rbx
0x18002374a  sub     rsp, 20h
0x18002374e  mov     rbx, rcx
0x180023751  call    cs:__imp_GetCurrentThreadId
0x180023757  cmp     [rbx+18h], eax
0x18002375a  jz      short loc_180023779
0x18002375c  mov     rax, cs:?g_pfnReportFatalUsageError@details@wil@@3P6AXPEBDPEBX@_EEA; __annotation("Debug", "TelemetryAssert", "MEMORY CORRUPTION: Calling code is leaking an activity thread-watcher and releasing it on another thread")
0x180023763  test    rax, rax
0x180023766  jz      short loc_180023779
0x180023768  mov     rdx, [rsp+28h]
0x18002376d  lea     rcx, aMemoryCorrupti; "MEMORY CORRUPTION: Calling code is leak"...
0x180023774  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180023779  mov     rcx, [rbx]
0x18002377c  mov     dword ptr [rbx+18h], 0
0x180023783  jmp     short loc_180023791
0x180023785  cmp     rax, rbx
0x180023788  jz      short loc_18002379B
0x18002378a  lea     rcx, [rax+10h]
0x18002378e  mov     [rbx], rcx
0x180023791  mov     rax, [rcx]
0x180023794  test    rax, rax
0x180023797  jnz     short loc_180023785
0x180023799  jmp     short loc_1800237A2
0x18002379b  mov     rax, [rbx+10h]
0x18002379f  mov     [rcx], rax
0x1800237a2  mov     qword ptr [rbx], 0
0x1800237a9  add     rsp, 20h
0x1800237ad  pop     rbx
0x1800237ae  retn
```
