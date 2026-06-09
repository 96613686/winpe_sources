# wil::details::ThreadFailureCallbackHolder::StopWatching(void)

- ea: `0x1800c60dc`
- end: `0x1800c6143`
- name: `?StopWatching@ThreadFailureCallbackHolder@details@wil@@QEAAXXZ`
- size: `103`
- prototype: `void __fastcall(wil::details::ThreadFailureCallbackHolder *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x1800c1fcc`

## callees

- `0x1800c60dc`
- `0x1800ed010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800c60e5`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800c60e5`

## string_xrefs

- `0x1800c6101`: `MEMORY CORRUPTION: Calling code is leaking an activity thread-watcher and releasing it on another thread`

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
0x1800c60dc  push    rbx
0x1800c60de  sub     rsp, 20h
0x1800c60e2  mov     rbx, rcx
0x1800c60e5  call    cs:__imp_GetCurrentThreadId
0x1800c60eb  cmp     [rbx+18h], eax
0x1800c60ee  jz      short loc_1800C610D
0x1800c60f0  mov     rax, cs:?g_pfnReportFatalUsageError@details@wil@@3P6AXPEBDPEBX@_EEA
0x1800c60f7  test    rax, rax
0x1800c60fa  jz      short loc_1800C610D
0x1800c60fc  mov     rdx, [rsp+28h]
0x1800c6101  lea     rcx, aMemoryCorrupti; "MEMORY CORRUPTION: Calling code is leak"...
0x1800c6108  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c610d  mov     rcx, [rbx]
0x1800c6110  mov     dword ptr [rbx+18h], 0
0x1800c6117  jmp     short loc_1800C6125
0x1800c6119  cmp     rax, rbx
0x1800c611c  jz      short loc_1800C612F
0x1800c611e  lea     rcx, [rax+10h]
0x1800c6122  mov     [rbx], rcx
0x1800c6125  mov     rax, [rcx]
0x1800c6128  test    rax, rax
0x1800c612b  jnz     short loc_1800C6119
0x1800c612d  jmp     short loc_1800C6136
0x1800c612f  mov     rax, [rbx+10h]
0x1800c6133  mov     [rcx], rax
0x1800c6136  mov     qword ptr [rbx], 0
0x1800c613d  add     rsp, 20h
0x1800c6141  pop     rbx
0x1800c6142  retn
```
