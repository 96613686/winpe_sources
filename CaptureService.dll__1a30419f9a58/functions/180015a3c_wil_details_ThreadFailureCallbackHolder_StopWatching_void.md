# wil::details::ThreadFailureCallbackHolder::StopWatching(void)

- ea: `0x180015a3c`
- end: `0x180015aa3`
- name: `?StopWatching@ThreadFailureCallbackHolder@details@wil@@QEAAXXZ`
- size: `103`
- prototype: `void __fastcall(wil::details::ThreadFailureCallbackHolder *__hidden this)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x18000e110`
- `0x180011f74`

## callees

- `0x180015a3c`
- `0x180022010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180015a45`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180015a45`

## string_xrefs

- `0x180015a61`: `MEMORY CORRUPTION: Calling code is leaking an activity thread-watcher and releasing it on another thread`

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
0x180015a3c  push    rbx
0x180015a3e  sub     rsp, 20h
0x180015a42  mov     rbx, rcx
0x180015a45  call    cs:__imp_GetCurrentThreadId
0x180015a4b  cmp     [rbx+18h], eax
0x180015a4e  jz      short loc_180015A6D
0x180015a50  mov     rax, cs:?g_pfnReportFatalUsageError@details@wil@@3P6AXPEBDPEBX@_EEA
0x180015a57  test    rax, rax
0x180015a5a  jz      short loc_180015A6D
0x180015a5c  mov     rdx, [rsp+28h]
0x180015a61  lea     rcx, aMemoryCorrupti; "MEMORY CORRUPTION: Calling code is leak"...
0x180015a68  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015a6d  mov     rcx, [rbx]
0x180015a70  mov     dword ptr [rbx+18h], 0
0x180015a77  jmp     short loc_180015A85
0x180015a79  cmp     rax, rbx
0x180015a7c  jz      short loc_180015A8F
0x180015a7e  lea     rcx, [rax+10h]
0x180015a82  mov     [rbx], rcx
0x180015a85  mov     rax, [rcx]
0x180015a88  test    rax, rax
0x180015a8b  jnz     short loc_180015A79
0x180015a8d  jmp     short loc_180015A96
0x180015a8f  mov     rax, [rbx+10h]
0x180015a93  mov     [rcx], rax
0x180015a96  mov     qword ptr [rbx], 0
0x180015a9d  add     rsp, 20h
0x180015aa1  pop     rbx
0x180015aa2  retn
```
