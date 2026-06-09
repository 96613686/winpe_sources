# wil::details::ThreadFailureCallbackHolder::StopWatching(void)

- ea: `0x18000f190`
- end: `0x18000f1fe`
- name: `?StopWatching@ThreadFailureCallbackHolder@details@wil@@QEAAXXZ`
- size: `110`
- prototype: `void __fastcall(wil::details::ThreadFailureCallbackHolder *__hidden this)`
- caller_count: `7`
- callee_count: `2`
- tags: ``

## callers

- `0x18000f0ac`
- `0x18000f168`
- `0x180013720`
- `0x180014690`
- `0x1800156b0`
- `0x180016610`
- `0x18001a524`

## callees

- `0x18000f190`
- `0x180048010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000f199`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000f199`

## string_xrefs

- `0x18000f1b5`: `MEMORY CORRUPTION: Calling code is leaking an activity thread-watcher and releasing it on another thread`

## pseudocode

```c
void __fastcall wil::details::ThreadFailureCallbackHolder::StopWatching(
        wil::details::ThreadFailureCallbackHolder *this)
{
  wil::details::ThreadFailureCallbackHolder **v2; // rcx
  wil::details::ThreadFailureCallbackHolder *v3; // rax
  void *retaddr; // [rsp+28h] [rbp+0h]

  if ( *((_DWORD *)this + 6) != GetCurrentThreadId() )
  {
    if ( wil::details::g_pfnReportFatalUsageError )
      wil::details::g_pfnReportFatalUsageError(
        "MEMORY CORRUPTION: Calling code is leaking an activity thread-watcher and releasing it on another thread",
        retaddr);
  }
  v2 = *(wil::details::ThreadFailureCallbackHolder ***)this;
  *((_DWORD *)this + 6) = 0;
  v3 = *v2;
  if ( *v2 )
  {
    while ( v3 != this )
    {
      v2 = (wil::details::ThreadFailureCallbackHolder **)((char *)v3 + 16);
      *(_QWORD *)this = (char *)v3 + 16;
      v3 = (wil::details::ThreadFailureCallbackHolder *)*((_QWORD *)v3 + 2);
      if ( !v3 )
      {
        *(_QWORD *)this = 0;
        return;
      }
    }
    *v2 = (wil::details::ThreadFailureCallbackHolder *)*((_QWORD *)this + 2);
  }
  *(_QWORD *)this = 0;
}

```

## disassembly

```asm
0x18000f190  push    rbx
0x18000f192  sub     rsp, 20h
0x18000f196  mov     rbx, rcx
0x18000f199  call    cs:__imp_GetCurrentThreadId
0x18000f19f  cmp     [rbx+18h], eax
0x18000f1a2  jz      short loc_18000F1C1
0x18000f1a4  mov     rax, cs:?g_pfnReportFatalUsageError@details@wil@@3P6AXPEBDPEBX@_EEA
0x18000f1ab  test    rax, rax
0x18000f1ae  jz      short loc_18000F1C1
0x18000f1b0  mov     rdx, [rsp+28h]
0x18000f1b5  lea     rcx, aMemoryCorrupti; "MEMORY CORRUPTION: Calling code is leak"...
0x18000f1bc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f1c1  mov     rcx, [rbx]
0x18000f1c4  xor     edx, edx
0x18000f1c6  mov     [rbx+18h], edx
0x18000f1c9  mov     rax, [rcx]
0x18000f1cc  test    rax, rax
0x18000f1cf  jz      short loc_18000F1F5
0x18000f1d1  cmp     rax, rbx
0x18000f1d4  jz      short loc_18000F1EE
0x18000f1d6  lea     rcx, [rax+10h]
0x18000f1da  mov     [rbx], rcx
0x18000f1dd  mov     rax, [rcx]
0x18000f1e0  test    rax, rax
0x18000f1e3  jnz     short loc_18000F1D1
0x18000f1e5  mov     [rbx], rdx
0x18000f1e8  add     rsp, 20h
0x18000f1ec  pop     rbx
0x18000f1ed  retn
0x18000f1ee  mov     rax, [rbx+10h]
0x18000f1f2  mov     [rcx], rax
0x18000f1f5  mov     [rbx], rdx
0x18000f1f8  add     rsp, 20h
0x18000f1fc  pop     rbx
0x18000f1fd  retn
```
