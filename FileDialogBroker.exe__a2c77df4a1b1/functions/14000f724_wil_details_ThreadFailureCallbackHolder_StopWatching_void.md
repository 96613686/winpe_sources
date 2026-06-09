# wil::details::ThreadFailureCallbackHolder::StopWatching(void)

- ea: `0x14000f724`
- end: `0x14000f78b`
- name: `?StopWatching@ThreadFailureCallbackHolder@details@wil@@QEAAXXZ`
- size: `103`
- prototype: `void __fastcall(wil::details::ThreadFailureCallbackHolder *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x14000928c`

## callees

- `0x14000f724`
- `0x140014010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x14000f72d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x14000f72d`

## string_xrefs

- `0x14000f749`: `MEMORY CORRUPTION: Calling code is leaking an activity thread-watcher and releasing it on another thread`

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
0x14000f724  push    rbx
0x14000f726  sub     rsp, 20h
0x14000f72a  mov     rbx, rcx
0x14000f72d  call    cs:__imp_GetCurrentThreadId
0x14000f733  cmp     [rbx+18h], eax
0x14000f736  jz      short loc_14000F755
0x14000f738  mov     rax, cs:?g_pfnReportFatalUsageError@details@wil@@3P6AXPEBDPEBX@_EEA
0x14000f73f  test    rax, rax
0x14000f742  jz      short loc_14000F755
0x14000f744  mov     rdx, [rsp+28h]
0x14000f749  lea     rcx, aMemoryCorrupti; "MEMORY CORRUPTION: Calling code is leak"...
0x14000f750  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000f755  mov     rcx, [rbx]
0x14000f758  mov     dword ptr [rbx+18h], 0
0x14000f75f  jmp     short loc_14000F76D
0x14000f761  cmp     rax, rbx
0x14000f764  jz      short loc_14000F777
0x14000f766  lea     rcx, [rax+10h]
0x14000f76a  mov     [rbx], rcx
0x14000f76d  mov     rax, [rcx]
0x14000f770  test    rax, rax
0x14000f773  jnz     short loc_14000F761
0x14000f775  jmp     short loc_14000F77E
0x14000f777  mov     rax, [rbx+10h]
0x14000f77b  mov     [rcx], rax
0x14000f77e  mov     qword ptr [rbx], 0
0x14000f785  add     rsp, 20h
0x14000f789  pop     rbx
0x14000f78a  retn
```
