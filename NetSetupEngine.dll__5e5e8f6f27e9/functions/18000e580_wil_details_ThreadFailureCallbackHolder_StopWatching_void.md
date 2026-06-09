# wil::details::ThreadFailureCallbackHolder::StopWatching(void)

- ea: `0x18000e580`
- end: `0x18000e5ee`
- name: `?StopWatching@ThreadFailureCallbackHolder@details@wil@@QEAAXXZ`
- size: `110`
- prototype: `void __fastcall(wil::details::ThreadFailureCallbackHolder *__hidden this)`
- caller_count: `11`
- callee_count: `2`
- tags: ``

## callers

- `0x18000d574`
- `0x18000d860`
- `0x18000e1a0`
- `0x18000e54c`
- `0x18000ebc8`
- `0x18000ee0c`
- `0x18000ee54`
- `0x180010778`
- `0x180013994`
- `0x180019d08`
- `0x180048de0`

## callees

- `0x18000e580`
- `0x18008b010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000e589`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000e589`

## string_xrefs

- `0x18000e5a5`: `MEMORY CORRUPTION: Calling code is leaking an activity thread-watcher and releasing it on another thread`

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
0x18000e580  push    rbx
0x18000e582  sub     rsp, 20h
0x18000e586  mov     rbx, rcx
0x18000e589  call    cs:__imp_GetCurrentThreadId
0x18000e58f  cmp     [rbx+18h], eax
0x18000e592  jz      short loc_18000E5B1
0x18000e594  mov     rax, cs:?g_pfnReportFatalUsageError@details@wil@@3P6AXPEBDPEBX@_EEA
0x18000e59b  test    rax, rax
0x18000e59e  jz      short loc_18000E5B1
0x18000e5a0  mov     rdx, [rsp+28h]
0x18000e5a5  lea     rcx, aMemoryCorrupti; "MEMORY CORRUPTION: Calling code is leak"...
0x18000e5ac  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e5b1  mov     rcx, [rbx]
0x18000e5b4  xor     edx, edx
0x18000e5b6  mov     [rbx+18h], edx
0x18000e5b9  mov     rax, [rcx]
0x18000e5bc  test    rax, rax
0x18000e5bf  jz      short loc_18000E5E5
0x18000e5c1  cmp     rax, rbx
0x18000e5c4  jz      short loc_18000E5DE
0x18000e5c6  lea     rcx, [rax+10h]
0x18000e5ca  mov     [rbx], rcx
0x18000e5cd  mov     rax, [rcx]
0x18000e5d0  test    rax, rax
0x18000e5d3  jnz     short loc_18000E5C1
0x18000e5d5  mov     [rbx], rdx
0x18000e5d8  add     rsp, 20h
0x18000e5dc  pop     rbx
0x18000e5dd  retn
0x18000e5de  mov     rax, [rbx+10h]
0x18000e5e2  mov     [rcx], rax
0x18000e5e5  mov     [rbx], rdx
0x18000e5e8  add     rsp, 20h
0x18000e5ec  pop     rbx
0x18000e5ed  retn
```
