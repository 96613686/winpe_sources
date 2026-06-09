# wil::details::ThreadFailureCallbackHolder::StopWatching(void)

- ea: `0x180023840`
- end: `0x1800238a5`
- name: `?StopWatching@ThreadFailureCallbackHolder@details@wil@@QEAAXXZ`
- size: `101`
- prototype: `void __fastcall(wil::details::ThreadFailureCallbackHolder *__hidden this)`
- caller_count: `15`
- callee_count: `2`
- tags: ``

## callers

- `0x180003900`
- `0x180008780`
- `0x180008ba0`
- `0x180009250`
- `0x1800099f0`
- `0x18000b720`
- `0x18000c220`
- `0x18000d36c`
- `0x18000de40`
- `0x18000e010`
- `0x18000fb20`
- `0x180013210`
- `0x180017c30`
- `0x1800245c8`
- `0x18002bb9c`

## callees

- `0x180023840`
- `0x180037010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180023849`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180023849`

## string_xrefs

- `0x180023865`: `MEMORY CORRUPTION: Calling code is leaking an activity thread-watcher and releasing it on another thread`

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
0x180023840  push    rbx
0x180023842  sub     rsp, 20h
0x180023846  mov     rbx, rcx
0x180023849  call    cs:__imp_GetCurrentThreadId
0x18002384f  cmp     [rbx+18h], eax
0x180023852  jz      short loc_180023871
0x180023854  mov     rax, cs:?g_pfnReportFatalUsageError@details@wil@@3P6AXPEBDPEBX@_EEA
0x18002385b  test    rax, rax
0x18002385e  jz      short loc_180023871
0x180023860  mov     rdx, [rsp+28h]
0x180023865  lea     rcx, aMemoryCorrupti; "MEMORY CORRUPTION: Calling code is leak"...
0x18002386c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180023871  mov     dword ptr [rbx+18h], 0
0x180023878  mov     rcx, [rbx]
0x18002387b  mov     rax, [rcx]
0x18002387e  test    rax, rax
0x180023881  jz      short loc_180023898
0x180023883  cmp     rax, rbx
0x180023886  jz      short loc_180023891
0x180023888  add     rax, 10h
0x18002388c  mov     [rbx], rax
0x18002388f  jmp     short loc_180023878
0x180023891  mov     rax, [rbx+10h]
0x180023895  mov     [rcx], rax
0x180023898  mov     qword ptr [rbx], 0
0x18002389f  add     rsp, 20h
0x1800238a3  pop     rbx
0x1800238a4  retn
```
