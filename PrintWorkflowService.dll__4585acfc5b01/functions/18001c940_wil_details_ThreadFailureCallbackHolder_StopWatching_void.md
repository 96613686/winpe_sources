# wil::details::ThreadFailureCallbackHolder::StopWatching(void)

- ea: `0x18001c940`
- end: `0x18001c9a7`
- name: `?StopWatching@ThreadFailureCallbackHolder@details@wil@@QEAAXXZ`
- size: `103`
- prototype: `void __fastcall(wil::details::ThreadFailureCallbackHolder *__hidden this)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x18001ac10`
- `0x18001b0d4`

## callees

- `0x18001c940`
- `0x18005e010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001c949`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001c949`

## string_xrefs

- `0x18001c965`: `MEMORY CORRUPTION: Calling code is leaking an activity thread-watcher and releasing it on another thread`

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
0x18001c940  push    rbx
0x18001c942  sub     rsp, 20h
0x18001c946  mov     rbx, rcx
0x18001c949  call    cs:__imp_GetCurrentThreadId
0x18001c94f  cmp     [rbx+18h], eax
0x18001c952  jz      short loc_18001C971
0x18001c954  mov     rax, cs:?g_pfnReportFatalUsageError@details@wil@@3P6AXPEBDPEBX@_EEA; __annotation("Debug", "TelemetryAssert", "MEMORY CORRUPTION: Calling code is leaking an activity thread-watcher and releasing it on another thread")
0x18001c95b  test    rax, rax
0x18001c95e  jz      short loc_18001C971
0x18001c960  mov     rdx, [rsp+28h]
0x18001c965  lea     rcx, aMemoryCorrupti; "MEMORY CORRUPTION: Calling code is leak"...
0x18001c96c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001c971  mov     rcx, [rbx]
0x18001c974  mov     dword ptr [rbx+18h], 0
0x18001c97b  jmp     short loc_18001C989
0x18001c97d  cmp     rax, rbx
0x18001c980  jz      short loc_18001C993
0x18001c982  lea     rcx, [rax+10h]
0x18001c986  mov     [rbx], rcx
0x18001c989  mov     rax, [rcx]
0x18001c98c  test    rax, rax
0x18001c98f  jnz     short loc_18001C97D
0x18001c991  jmp     short loc_18001C99A
0x18001c993  mov     rax, [rbx+10h]
0x18001c997  mov     [rcx], rax
0x18001c99a  mov     qword ptr [rbx], 0
0x18001c9a1  add     rsp, 20h
0x18001c9a5  pop     rbx
0x18001c9a6  retn
```
