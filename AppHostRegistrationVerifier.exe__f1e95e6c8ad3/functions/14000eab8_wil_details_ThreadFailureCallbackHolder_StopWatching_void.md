# wil::details::ThreadFailureCallbackHolder::StopWatching(void)

- ea: `0x14000eab8`
- end: `0x14000eb1f`
- name: `?StopWatching@ThreadFailureCallbackHolder@details@wil@@QEAAXXZ`
- size: `103`
- prototype: `void __fastcall(wil::details::ThreadFailureCallbackHolder *__hidden this)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x14000a3ac`
- `0x14000d438`

## callees

- `0x14000eab8`
- `0x140012010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x14000eac1`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x14000eac1`

## string_xrefs

- `0x14000eadd`: `MEMORY CORRUPTION: Calling code is leaking an activity thread-watcher and releasing it on another thread`

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
0x14000eab8  push    rbx
0x14000eaba  sub     rsp, 20h
0x14000eabe  mov     rbx, rcx
0x14000eac1  call    cs:__imp_GetCurrentThreadId
0x14000eac7  cmp     [rbx+18h], eax
0x14000eaca  jz      short loc_14000EAE9
0x14000eacc  mov     rax, cs:?g_pfnReportFatalUsageError@details@wil@@3P6AXPEBDPEBX@_EEA
0x14000ead3  test    rax, rax
0x14000ead6  jz      short loc_14000EAE9
0x14000ead8  mov     rdx, [rsp+28h]
0x14000eadd  lea     rcx, aMemoryCorrupti; "MEMORY CORRUPTION: Calling code is leak"...
0x14000eae4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000eae9  mov     rcx, [rbx]
0x14000eaec  mov     dword ptr [rbx+18h], 0
0x14000eaf3  jmp     short loc_14000EB01
0x14000eaf5  cmp     rax, rbx
0x14000eaf8  jz      short loc_14000EB0B
0x14000eafa  lea     rcx, [rax+10h]
0x14000eafe  mov     [rbx], rcx
0x14000eb01  mov     rax, [rcx]
0x14000eb04  test    rax, rax
0x14000eb07  jnz     short loc_14000EAF5
0x14000eb09  jmp     short loc_14000EB12
0x14000eb0b  mov     rax, [rbx+10h]
0x14000eb0f  mov     [rcx], rax
0x14000eb12  mov     qword ptr [rbx], 0
0x14000eb19  add     rsp, 20h
0x14000eb1d  pop     rbx
0x14000eb1e  retn
```
