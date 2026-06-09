# wil::details::ThreadFailureCallbackHolder::StopWatching(void)

- ea: `0x180075f24`
- end: `0x180075f89`
- name: `?StopWatching@ThreadFailureCallbackHolder@details@wil@@QEAAXXZ`
- size: `101`
- prototype: `void __fastcall(wil::details::ThreadFailureCallbackHolder *__hidden this)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x1800551c4`
- `0x180074f28`

## callees

- `0x180075f24`
- `0x1800c0010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180075f2d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180075f2d`

## string_xrefs

- `0x180075f49`: `MEMORY CORRUPTION: Calling code is leaking an activity thread-watcher and releasing it on another thread`

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
0x180075f24  push    rbx
0x180075f26  sub     rsp, 20h
0x180075f2a  mov     rbx, rcx
0x180075f2d  call    cs:__imp_GetCurrentThreadId
0x180075f33  cmp     [rbx+18h], eax
0x180075f36  jz      short loc_180075F55
0x180075f38  mov     rax, cs:?g_pfnReportFatalUsageError@details@wil@@3P6AXPEBDPEBX@_EEA
0x180075f3f  test    rax, rax
0x180075f42  jz      short loc_180075F55
0x180075f44  mov     rdx, [rsp+28h]
0x180075f49  lea     rcx, aMemoryCorrupti; "MEMORY CORRUPTION: Calling code is leak"...
0x180075f50  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180075f55  mov     dword ptr [rbx+18h], 0
0x180075f5c  mov     rcx, [rbx]
0x180075f5f  mov     rax, [rcx]
0x180075f62  test    rax, rax
0x180075f65  jz      short loc_180075F7C
0x180075f67  cmp     rax, rbx
0x180075f6a  jz      short loc_180075F75
0x180075f6c  add     rax, 10h
0x180075f70  mov     [rbx], rax
0x180075f73  jmp     short loc_180075F5C
0x180075f75  mov     rax, [rbx+10h]
0x180075f79  mov     [rcx], rax
0x180075f7c  mov     qword ptr [rbx], 0
0x180075f83  add     rsp, 20h
0x180075f87  pop     rbx
0x180075f88  retn
```
