# wil::details::ThreadFailureCallbackHolder::StopWatching(void)

- ea: `0x1800576a0`
- end: `0x18005770c`
- name: `?StopWatching@ThreadFailureCallbackHolder@details@wil@@QEAAXXZ`
- size: `108`
- prototype: `void __fastcall(wil::details::ThreadFailureCallbackHolder *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x18001e100`

## callees

- `0x1800576a0`
- `0x1800c8010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800576a9`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800576a9`

## string_xrefs

- `0x1800576cb`: `MEMORY CORRUPTION: Calling code is leaking an activity thread-watcher and releasing it on another thread`

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
0x1800576a0  push    rbx
0x1800576a2  sub     rsp, 20h
0x1800576a6  mov     rbx, rcx
0x1800576a9  call    cs:__imp_GetCurrentThreadId
0x1800576b0  nop     dword ptr [rax+rax+00h]
0x1800576b5  cmp     [rbx+18h], eax
0x1800576b8  jz      short loc_1800576D7
0x1800576ba  mov     rax, cs:?g_pfnReportFatalUsageError@details@wil@@3P6AXPEBDPEBX@_EEA
0x1800576c1  test    rax, rax
0x1800576c4  jz      short loc_1800576D7
0x1800576c6  mov     rdx, [rsp+28h]
0x1800576cb  lea     rcx, aMemoryCorrupti; "MEMORY CORRUPTION: Calling code is leak"...
0x1800576d2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800576d7  mov     dword ptr [rbx+18h], 0
0x1800576de  mov     rcx, [rbx]
0x1800576e1  mov     rax, [rcx]
0x1800576e4  test    rax, rax
0x1800576e7  jz      short loc_1800576FE
0x1800576e9  cmp     rax, rbx
0x1800576ec  jz      short loc_1800576F7
0x1800576ee  add     rax, 10h
0x1800576f2  mov     [rbx], rax
0x1800576f5  jmp     short loc_1800576DE
0x1800576f7  mov     rax, [rbx+10h]
0x1800576fb  mov     [rcx], rax
0x1800576fe  mov     qword ptr [rbx], 0
0x180057705  add     rsp, 20h
0x180057709  pop     rbx
0x18005770a  retn
```
