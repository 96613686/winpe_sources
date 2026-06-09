# wil::details::ThreadFailureCallbackHolder::StopWatching(void)

- ea: `0x180003000`
- end: `0x180003067`
- name: `?StopWatching@ThreadFailureCallbackHolder@details@wil@@QEAAXXZ`
- size: `103`
- prototype: `void __fastcall(wil::details::ThreadFailureCallbackHolder *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180003574`

## callees

- `0x180003000`
- `0x18000c010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180003009`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180003009`

## string_xrefs

- `0x180003025`: `MEMORY CORRUPTION: Calling code is leaking an activity thread-watcher and releasing it on another thread`

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
0x180003000  push    rbx
0x180003002  sub     rsp, 20h
0x180003006  mov     rbx, rcx
0x180003009  call    cs:__imp_GetCurrentThreadId
0x18000300f  cmp     [rbx+18h], eax
0x180003012  jz      short loc_180003031
0x180003014  mov     rax, cs:?g_pfnReportFatalUsageError@details@wil@@3P6AXPEBDPEBX@_EEA
0x18000301b  test    rax, rax
0x18000301e  jz      short loc_180003031
0x180003020  mov     rdx, [rsp+28h]
0x180003025  lea     rcx, aMemoryCorrupti; "MEMORY CORRUPTION: Calling code is leak"...
0x18000302c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003031  mov     rcx, [rbx]
0x180003034  mov     dword ptr [rbx+18h], 0
0x18000303b  jmp     short loc_180003049
0x18000303d  cmp     rax, rbx
0x180003040  jz      short loc_180003053
0x180003042  lea     rcx, [rax+10h]
0x180003046  mov     [rbx], rcx
0x180003049  mov     rax, [rcx]
0x18000304c  test    rax, rax
0x18000304f  jnz     short loc_18000303D
0x180003051  jmp     short loc_18000305A
0x180003053  mov     rax, [rbx+10h]
0x180003057  mov     [rcx], rax
0x18000305a  mov     qword ptr [rbx], 0
0x180003061  add     rsp, 20h
0x180003065  pop     rbx
0x180003066  retn
```
