# wil::details::ThreadFailureCallbackHolder::StopWatching(void)

- ea: `0x18000907c`
- end: `0x1800090ea`
- name: `?StopWatching@ThreadFailureCallbackHolder@details@wil@@QEAAXXZ`
- size: `110`
- prototype: `void __fastcall(wil::details::ThreadFailureCallbackHolder *__hidden this)`
- caller_count: `19`
- callee_count: `2`
- tags: ``

## callers

- `0x1800059f8`
- `0x18000892c`
- `0x180008b20`
- `0x180008dd0`
- `0x18001cb10`
- `0x18001cdc0`
- `0x18001d070`
- `0x18001d320`
- `0x18001d5d0`
- `0x18001d880`
- `0x18001db30`
- `0x18001dde0`
- `0x18001e090`
- `0x18001e340`
- `0x18001e5f0`
- `0x18001e8a0`
- `0x18001eb50`
- `0x18002239c`
- `0x180022614`

## callees

- `0x18000907c`
- `0x18003c010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180009085`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180009085`

## string_xrefs

- `0x1800090a7`: `MEMORY CORRUPTION: Calling code is leaking an activity thread-watcher and releasing it on another thread`

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
0x18000907c  push    rbx
0x18000907e  sub     rsp, 20h
0x180009082  mov     rbx, rcx
0x180009085  call    cs:__imp_GetCurrentThreadId
0x18000908c  nop     dword ptr [rax+rax+00h]
0x180009091  cmp     [rbx+18h], eax
0x180009094  jz      short loc_1800090B3
0x180009096  mov     rax, cs:?g_pfnReportFatalUsageError@details@wil@@3P6AXPEBDPEBX@_EEA
0x18000909d  test    rax, rax
0x1800090a0  jz      short loc_1800090B3
0x1800090a2  mov     rdx, [rsp+28h]
0x1800090a7  lea     rcx, aMemoryCorrupti; "MEMORY CORRUPTION: Calling code is leak"...
0x1800090ae  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800090b3  mov     rcx, [rbx]
0x1800090b6  mov     dword ptr [rbx+18h], 0
0x1800090bd  jmp     short loc_1800090CB
0x1800090bf  cmp     rax, rbx
0x1800090c2  jz      short loc_1800090D5
0x1800090c4  lea     rcx, [rax+10h]
0x1800090c8  mov     [rbx], rcx
0x1800090cb  mov     rax, [rcx]
0x1800090ce  test    rax, rax
0x1800090d1  jnz     short loc_1800090BF
0x1800090d3  jmp     short loc_1800090DC
0x1800090d5  mov     rax, [rbx+10h]
0x1800090d9  mov     [rcx], rax
0x1800090dc  mov     qword ptr [rbx], 0
0x1800090e3  add     rsp, 20h
0x1800090e7  pop     rbx
0x1800090e8  retn
```
