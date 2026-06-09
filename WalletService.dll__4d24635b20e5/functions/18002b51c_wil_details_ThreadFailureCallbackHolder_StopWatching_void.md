# wil::details::ThreadFailureCallbackHolder::StopWatching(void)

- ea: `0x18002b51c`
- end: `0x18002b583`
- name: `?StopWatching@ThreadFailureCallbackHolder@details@wil@@QEAAXXZ`
- size: `103`
- prototype: `void __fastcall(wil::details::ThreadFailureCallbackHolder *__hidden this)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x180029378`
- `0x18002a340`

## callees

- `0x18002b51c`
- `0x180045010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18002b525`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18002b525`

## string_xrefs

- `0x18002b541`: `MEMORY CORRUPTION: Calling code is leaking an activity thread-watcher and releasing it on another thread`

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
0x18002b51c  push    rbx
0x18002b51e  sub     rsp, 20h
0x18002b522  mov     rbx, rcx
0x18002b525  call    cs:__imp_GetCurrentThreadId
0x18002b52b  cmp     [rbx+18h], eax
0x18002b52e  jz      short loc_18002B54D
0x18002b530  mov     rax, cs:?g_pfnReportFatalUsageError@details@wil@@3P6AXPEBDPEBX@_EEA
0x18002b537  test    rax, rax
0x18002b53a  jz      short loc_18002B54D
0x18002b53c  mov     rdx, [rsp+28h]
0x18002b541  lea     rcx, aMemoryCorrupti; "MEMORY CORRUPTION: Calling code is leak"...
0x18002b548  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002b54d  mov     rcx, [rbx]
0x18002b550  mov     dword ptr [rbx+18h], 0
0x18002b557  jmp     short loc_18002B565
0x18002b559  cmp     rax, rbx
0x18002b55c  jz      short loc_18002B56F
0x18002b55e  lea     rcx, [rax+10h]
0x18002b562  mov     [rbx], rcx
0x18002b565  mov     rax, [rcx]
0x18002b568  test    rax, rax
0x18002b56b  jnz     short loc_18002B559
0x18002b56d  jmp     short loc_18002B576
0x18002b56f  mov     rax, [rbx+10h]
0x18002b573  mov     [rcx], rax
0x18002b576  mov     qword ptr [rbx], 0
0x18002b57d  add     rsp, 20h
0x18002b581  pop     rbx
0x18002b582  retn
```
