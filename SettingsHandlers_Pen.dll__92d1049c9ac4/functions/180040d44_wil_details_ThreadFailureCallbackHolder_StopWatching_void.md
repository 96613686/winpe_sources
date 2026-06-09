# wil::details::ThreadFailureCallbackHolder::StopWatching(void)

- ea: `0x180040d44`
- end: `0x180040dab`
- name: `?StopWatching@ThreadFailureCallbackHolder@details@wil@@QEAAXXZ`
- size: `103`
- prototype: `void __fastcall(wil::details::ThreadFailureCallbackHolder *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x18003efd4`

## callees

- `0x180040d44`
- `0x18005d010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180040d4d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180040d4d`

## string_xrefs

- `0x180040d69`: `MEMORY CORRUPTION: Calling code is leaking an activity thread-watcher and releasing it on another thread`

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
0x180040d44  push    rbx
0x180040d46  sub     rsp, 20h
0x180040d4a  mov     rbx, rcx
0x180040d4d  call    cs:__imp_GetCurrentThreadId
0x180040d53  cmp     [rbx+18h], eax
0x180040d56  jz      short loc_180040D75
0x180040d58  mov     rax, cs:?g_pfnReportFatalUsageError@details@wil@@3P6AXPEBDPEBX@_EEA
0x180040d5f  test    rax, rax
0x180040d62  jz      short loc_180040D75
0x180040d64  mov     rdx, [rsp+28h]
0x180040d69  lea     rcx, aMemoryCorrupti; "MEMORY CORRUPTION: Calling code is leak"...
0x180040d70  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180040d75  mov     rcx, [rbx]
0x180040d78  mov     dword ptr [rbx+18h], 0
0x180040d7f  jmp     short loc_180040D8D
0x180040d81  cmp     rax, rbx
0x180040d84  jz      short loc_180040D97
0x180040d86  lea     rcx, [rax+10h]
0x180040d8a  mov     [rbx], rcx
0x180040d8d  mov     rax, [rcx]
0x180040d90  test    rax, rax
0x180040d93  jnz     short loc_180040D81
0x180040d95  jmp     short loc_180040D9E
0x180040d97  mov     rax, [rbx+10h]
0x180040d9b  mov     [rcx], rax
0x180040d9e  mov     qword ptr [rbx], 0
0x180040da5  add     rsp, 20h
0x180040da9  pop     rbx
0x180040daa  retn
```
