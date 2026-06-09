# wil::details::ThreadFailureCallbackHolder::StopWatching(void)

- ea: `0x180094cb8`
- end: `0x180094d1f`
- name: `?StopWatching@ThreadFailureCallbackHolder@details@wil@@QEAAXXZ`
- size: `103`
- prototype: `void __fastcall(wil::details::ThreadFailureCallbackHolder *__hidden this)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x180082abc`
- `0x1800863a0`

## callees

- `0x180094cb8`
- `0x1800dc010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180094cc1`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180094cc1`

## string_xrefs

- `0x180094cdd`: `MEMORY CORRUPTION: Calling code is leaking an activity thread-watcher and releasing it on another thread`

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
0x180094cb8  push    rbx
0x180094cba  sub     rsp, 20h
0x180094cbe  mov     rbx, rcx
0x180094cc1  call    cs:__imp_GetCurrentThreadId
0x180094cc7  cmp     [rbx+18h], eax
0x180094cca  jz      short loc_180094CE9
0x180094ccc  mov     rax, cs:?g_pfnReportFatalUsageError@details@wil@@3P6AXPEBDPEBX@_EEA
0x180094cd3  test    rax, rax
0x180094cd6  jz      short loc_180094CE9
0x180094cd8  mov     rdx, [rsp+28h]
0x180094cdd  lea     rcx, aMemoryCorrupti; "MEMORY CORRUPTION: Calling code is leak"...
0x180094ce4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180094ce9  mov     rcx, [rbx]
0x180094cec  mov     dword ptr [rbx+18h], 0
0x180094cf3  jmp     short loc_180094D01
0x180094cf5  cmp     rax, rbx
0x180094cf8  jz      short loc_180094D0B
0x180094cfa  lea     rcx, [rax+10h]
0x180094cfe  mov     [rbx], rcx
0x180094d01  mov     rax, [rcx]
0x180094d04  test    rax, rax
0x180094d07  jnz     short loc_180094CF5
0x180094d09  jmp     short loc_180094D12
0x180094d0b  mov     rax, [rbx+10h]
0x180094d0f  mov     [rcx], rax
0x180094d12  mov     qword ptr [rbx], 0
0x180094d19  add     rsp, 20h
0x180094d1d  pop     rbx
0x180094d1e  retn
```
