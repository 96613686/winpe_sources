# wil::details::ThreadFailureCallbackHolder::StopWatching(void)

- ea: `0x180068374`
- end: `0x1800683d9`
- name: `?StopWatching@ThreadFailureCallbackHolder@details@wil@@QEAAXXZ`
- size: `101`
- prototype: `void __fastcall(wil::details::ThreadFailureCallbackHolder *__hidden this)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x180064590`
- `0x1800669d0`

## callees

- `0x180068374`
- `0x180091010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18006837d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18006837d`

## string_xrefs

- `0x180068399`: `MEMORY CORRUPTION: Calling code is leaking an activity thread-watcher and releasing it on another thread`

## pseudocode

```c
void __fastcall wil::details::ThreadFailureCallbackHolder::StopWatching(
        wil::details::ThreadFailureCallbackHolder *this)
{
  wil::details::ThreadFailureCallbackHolder *v2; // rax
  void *retaddr; // [rsp+28h] [rbp+0h]

  if ( *((_DWORD *)this + 6) != GetCurrentThreadId() && wil::details::g_pfnReportFatalUsageError )
    wil::details::g_pfnReportFatalUsageError(
      "MEMORY CORRUPTION: Calling code is leaking an activity thread-watcher and releasing it on another thread",
      retaddr);
  *((_DWORD *)this + 6) = 0;
  while ( 1 )
  {
    v2 = **(wil::details::ThreadFailureCallbackHolder ***)this;
    if ( !v2 )
      break;
    if ( v2 == this )
    {
      **(_QWORD **)this = *((_QWORD *)this + 2);
      break;
    }
    *(_QWORD *)this = (char *)v2 + 16;
  }
  *(_QWORD *)this = 0;
}

```

## disassembly

```asm
0x180068374  push    rbx
0x180068376  sub     rsp, 20h
0x18006837a  mov     rbx, rcx
0x18006837d  call    cs:__imp_GetCurrentThreadId
0x180068383  cmp     [rbx+18h], eax
0x180068386  jz      short loc_1800683A5
0x180068388  mov     rax, cs:?g_pfnReportFatalUsageError@details@wil@@3P6AXPEBDPEBX@_EEA
0x18006838f  test    rax, rax
0x180068392  jz      short loc_1800683A5
0x180068394  mov     rdx, [rsp+28h]
0x180068399  lea     rcx, aMemoryCorrupti; "MEMORY CORRUPTION: Calling code is leak"...
0x1800683a0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800683a5  mov     dword ptr [rbx+18h], 0
0x1800683ac  mov     rcx, [rbx]
0x1800683af  mov     rax, [rcx]
0x1800683b2  test    rax, rax
0x1800683b5  jz      short loc_1800683CC
0x1800683b7  cmp     rax, rbx
0x1800683ba  jz      short loc_1800683C5
0x1800683bc  add     rax, 10h
0x1800683c0  mov     [rbx], rax
0x1800683c3  jmp     short loc_1800683AC
0x1800683c5  mov     rax, [rbx+10h]
0x1800683c9  mov     [rcx], rax
0x1800683cc  mov     qword ptr [rbx], 0
0x1800683d3  add     rsp, 20h
0x1800683d7  pop     rbx
0x1800683d8  retn
```
