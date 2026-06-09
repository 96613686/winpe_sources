# wil::details::ThreadFailureCallbackHolder::StopWatching(void)

- ea: `0x18001b990`
- end: `0x18001b9f7`
- name: `?StopWatching@ThreadFailureCallbackHolder@details@wil@@QEAAXXZ`
- size: `103`
- prototype: `void __fastcall(wil::details::ThreadFailureCallbackHolder *__hidden this)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x18001a75c`
- `0x18001a878`

## callees

- `0x18001b990`
- `0x180032010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001b999`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001b999`

## string_xrefs

- `0x18001b9b5`: `MEMORY CORRUPTION: Calling code is leaking an activity thread-watcher and releasing it on another thread`

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
0x18001b990  push    rbx
0x18001b992  sub     rsp, 20h
0x18001b996  mov     rbx, rcx
0x18001b999  call    cs:__imp_GetCurrentThreadId
0x18001b99f  cmp     [rbx+18h], eax
0x18001b9a2  jz      short loc_18001B9C1
0x18001b9a4  mov     rax, cs:?g_pfnReportFatalUsageError@details@wil@@3P6AXPEBDPEBX@_EEA; __annotation("Debug", "TelemetryAssert", "MEMORY CORRUPTION: Calling code is leaking an activity thread-watcher and releasing it on another thread")
0x18001b9ab  test    rax, rax
0x18001b9ae  jz      short loc_18001B9C1
0x18001b9b0  mov     rdx, [rsp+28h]
0x18001b9b5  lea     rcx, aMemoryCorrupti; "MEMORY CORRUPTION: Calling code is leak"...
0x18001b9bc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001b9c1  mov     rcx, [rbx]
0x18001b9c4  mov     dword ptr [rbx+18h], 0
0x18001b9cb  jmp     short loc_18001B9D9
0x18001b9cd  cmp     rax, rbx
0x18001b9d0  jz      short loc_18001B9E3
0x18001b9d2  lea     rcx, [rax+10h]
0x18001b9d6  mov     [rbx], rcx
0x18001b9d9  mov     rax, [rcx]
0x18001b9dc  test    rax, rax
0x18001b9df  jnz     short loc_18001B9CD
0x18001b9e1  jmp     short loc_18001B9EA
0x18001b9e3  mov     rax, [rbx+10h]
0x18001b9e7  mov     [rcx], rax
0x18001b9ea  mov     qword ptr [rbx], 0
0x18001b9f1  add     rsp, 20h
0x18001b9f5  pop     rbx
0x18001b9f6  retn
```
