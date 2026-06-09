# wil::details::ThreadFailureCallbackHolder::StopWatching(void)

- ea: `0x1800153d8`
- end: `0x18001543f`
- name: `?StopWatching@ThreadFailureCallbackHolder@details@wil@@QEAAXXZ`
- size: `103`
- prototype: `void __fastcall(wil::details::ThreadFailureCallbackHolder *__hidden this)`
- caller_count: `3`
- callee_count: `2`
- tags: ``

## callers

- `0x1800105f8`
- `0x18001155c`
- `0x1800137d4`

## callees

- `0x1800153d8`
- `0x18002c010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800153e1`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800153e1`

## string_xrefs

- `0x1800153fd`: `MEMORY CORRUPTION: Calling code is leaking an activity thread-watcher and releasing it on another thread`

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
0x1800153d8  push    rbx
0x1800153da  sub     rsp, 20h
0x1800153de  mov     rbx, rcx
0x1800153e1  call    cs:__imp_GetCurrentThreadId
0x1800153e7  cmp     [rbx+18h], eax
0x1800153ea  jz      short loc_180015409
0x1800153ec  mov     rax, cs:?g_pfnReportFatalUsageError@details@wil@@3P6AXPEBDPEBX@_EEA
0x1800153f3  test    rax, rax
0x1800153f6  jz      short loc_180015409
0x1800153f8  mov     rdx, [rsp+28h]
0x1800153fd  lea     rcx, aMemoryCorrupti; "MEMORY CORRUPTION: Calling code is leak"...
0x180015404  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015409  mov     rcx, [rbx]
0x18001540c  mov     dword ptr [rbx+18h], 0
0x180015413  jmp     short loc_180015421
0x180015415  cmp     rax, rbx
0x180015418  jz      short loc_18001542B
0x18001541a  lea     rcx, [rax+10h]
0x18001541e  mov     [rbx], rcx
0x180015421  mov     rax, [rcx]
0x180015424  test    rax, rax
0x180015427  jnz     short loc_180015415
0x180015429  jmp     short loc_180015432
0x18001542b  mov     rax, [rbx+10h]
0x18001542f  mov     [rcx], rax
0x180015432  mov     qword ptr [rbx], 0
0x180015439  add     rsp, 20h
0x18001543d  pop     rbx
0x18001543e  retn
```
