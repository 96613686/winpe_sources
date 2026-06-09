# wil::details::ThreadFailureCallbackHolder::StopWatching(void)

- ea: `0x180027580`
- end: `0x1800275e5`
- name: `?StopWatching@ThreadFailureCallbackHolder@details@wil@@QEAAXXZ`
- size: `101`
- prototype: `void __fastcall(wil::details::ThreadFailureCallbackHolder *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x18001a708`

## callees

- `0x180027580`
- `0x180031010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180027589`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180027589`

## string_xrefs

- `0x1800275a5`: `MEMORY CORRUPTION: Calling code is leaking an activity thread-watcher and releasing it on another thread`

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
0x180027580  push    rbx
0x180027582  sub     rsp, 20h
0x180027586  mov     rbx, rcx
0x180027589  call    cs:__imp_GetCurrentThreadId
0x18002758f  cmp     [rbx+18h], eax
0x180027592  jz      short loc_1800275B1
0x180027594  mov     rax, cs:?g_pfnReportFatalUsageError@details@wil@@3P6AXPEBDPEBX@_EEA
0x18002759b  test    rax, rax
0x18002759e  jz      short loc_1800275B1
0x1800275a0  mov     rdx, [rsp+28h]
0x1800275a5  lea     rcx, aMemoryCorrupti; "MEMORY CORRUPTION: Calling code is leak"...
0x1800275ac  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800275b1  mov     dword ptr [rbx+18h], 0
0x1800275b8  mov     rcx, [rbx]
0x1800275bb  mov     rax, [rcx]
0x1800275be  test    rax, rax
0x1800275c1  jz      short loc_1800275D8
0x1800275c3  cmp     rax, rbx
0x1800275c6  jz      short loc_1800275D1
0x1800275c8  add     rax, 10h
0x1800275cc  mov     [rbx], rax
0x1800275cf  jmp     short loc_1800275B8
0x1800275d1  mov     rax, [rbx+10h]
0x1800275d5  mov     [rcx], rax
0x1800275d8  mov     qword ptr [rbx], 0
0x1800275df  add     rsp, 20h
0x1800275e3  pop     rbx
0x1800275e4  retn
```
