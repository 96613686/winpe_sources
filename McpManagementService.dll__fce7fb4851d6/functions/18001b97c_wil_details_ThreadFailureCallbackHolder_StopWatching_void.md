# wil::details::ThreadFailureCallbackHolder::StopWatching(void)

- ea: `0x18001b97c`
- end: `0x18001b9e3`
- name: `?StopWatching@ThreadFailureCallbackHolder@details@wil@@QEAAXXZ`
- size: `103`
- prototype: `void __fastcall(wil::details::ThreadFailureCallbackHolder *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180012a8c`

## callees

- `0x18001b97c`
- `0x18002b010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001b985`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001b985`

## string_xrefs

- `0x18001b9a1`: `MEMORY CORRUPTION: Calling code is leaking an activity thread-watcher and releasing it on another thread`

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
0x18001b97c  push    rbx
0x18001b97e  sub     rsp, 20h
0x18001b982  mov     rbx, rcx
0x18001b985  call    cs:__imp_GetCurrentThreadId
0x18001b98b  cmp     [rbx+18h], eax
0x18001b98e  jz      short loc_18001B9AD
0x18001b990  mov     rax, cs:?g_pfnReportFatalUsageError@details@wil@@3P6AXPEBDPEBX@_EEA
0x18001b997  test    rax, rax
0x18001b99a  jz      short loc_18001B9AD
0x18001b99c  mov     rdx, [rsp+28h]
0x18001b9a1  lea     rcx, aMemoryCorrupti; "MEMORY CORRUPTION: Calling code is leak"...
0x18001b9a8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001b9ad  mov     rcx, [rbx]
0x18001b9b0  mov     dword ptr [rbx+18h], 0
0x18001b9b7  jmp     short loc_18001B9C5
0x18001b9b9  cmp     rax, rbx
0x18001b9bc  jz      short loc_18001B9CF
0x18001b9be  lea     rcx, [rax+10h]
0x18001b9c2  mov     [rbx], rcx
0x18001b9c5  mov     rax, [rcx]
0x18001b9c8  test    rax, rax
0x18001b9cb  jnz     short loc_18001B9B9
0x18001b9cd  jmp     short loc_18001B9D6
0x18001b9cf  mov     rax, [rbx+10h]
0x18001b9d3  mov     [rcx], rax
0x18001b9d6  mov     qword ptr [rbx], 0
0x18001b9dd  add     rsp, 20h
0x18001b9e1  pop     rbx
0x18001b9e2  retn
```
