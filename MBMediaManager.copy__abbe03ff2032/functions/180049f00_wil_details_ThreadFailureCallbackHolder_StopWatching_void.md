# wil::details::ThreadFailureCallbackHolder::StopWatching(void)

- ea: `0x180049f00`
- end: `0x180049f67`
- name: `?StopWatching@ThreadFailureCallbackHolder@details@wil@@QEAAXXZ`
- size: `103`
- prototype: `void __fastcall(wil::details::ThreadFailureCallbackHolder *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180047ec8`

## callees

- `0x180049f00`
- `0x180059010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180049f09`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180049f09`

## string_xrefs

- `0x180049f25`: `MEMORY CORRUPTION: Calling code is leaking an activity thread-watcher and releasing it on another thread`

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
0x180049f00  push    rbx
0x180049f02  sub     rsp, 20h
0x180049f06  mov     rbx, rcx
0x180049f09  call    cs:__imp_GetCurrentThreadId
0x180049f0f  cmp     [rbx+18h], eax
0x180049f12  jz      short loc_180049F31
0x180049f14  mov     rax, cs:?g_pfnReportFatalUsageError@details@wil@@3P6AXPEBDPEBX@_EEA
0x180049f1b  test    rax, rax
0x180049f1e  jz      short loc_180049F31
0x180049f20  mov     rdx, [rsp+28h]
0x180049f25  lea     rcx, aMemoryCorrupti; "MEMORY CORRUPTION: Calling code is leak"...
0x180049f2c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180049f31  mov     rcx, [rbx]
0x180049f34  mov     dword ptr [rbx+18h], 0
0x180049f3b  jmp     short loc_180049F49
0x180049f3d  cmp     rax, rbx
0x180049f40  jz      short loc_180049F53
0x180049f42  lea     rcx, [rax+10h]
0x180049f46  mov     [rbx], rcx
0x180049f49  mov     rax, [rcx]
0x180049f4c  test    rax, rax
0x180049f4f  jnz     short loc_180049F3D
0x180049f51  jmp     short loc_180049F5A
0x180049f53  mov     rax, [rbx+10h]
0x180049f57  mov     [rcx], rax
0x180049f5a  mov     qword ptr [rbx], 0
0x180049f61  add     rsp, 20h
0x180049f65  pop     rbx
0x180049f66  retn
```
