# wil::details::ThreadFailureCallbackHolder::StopWatching(void)

- ea: `0x18000f79c`
- end: `0x18000f803`
- name: `?StopWatching@ThreadFailureCallbackHolder@details@wil@@QEAAXXZ`
- size: `103`
- prototype: `void __fastcall(wil::details::ThreadFailureCallbackHolder *__hidden this)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x18000d560`
- `0x18000df18`

## callees

- `0x18000f79c`
- `0x18002b010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000f7a5`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000f7a5`

## string_xrefs

- `0x18000f7c1`: `MEMORY CORRUPTION: Calling code is leaking an activity thread-watcher and releasing it on another thread`

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
0x18000f79c  push    rbx
0x18000f79e  sub     rsp, 20h
0x18000f7a2  mov     rbx, rcx
0x18000f7a5  call    cs:__imp_GetCurrentThreadId
0x18000f7ab  cmp     [rbx+18h], eax
0x18000f7ae  jz      short loc_18000F7CD
0x18000f7b0  mov     rax, cs:?g_pfnReportFatalUsageError@details@wil@@3P6AXPEBDPEBX@_EEA
0x18000f7b7  test    rax, rax
0x18000f7ba  jz      short loc_18000F7CD
0x18000f7bc  mov     rdx, [rsp+28h]
0x18000f7c1  lea     rcx, aMemoryCorrupti; "MEMORY CORRUPTION: Calling code is leak"...
0x18000f7c8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f7cd  mov     rcx, [rbx]
0x18000f7d0  mov     dword ptr [rbx+18h], 0
0x18000f7d7  jmp     short loc_18000F7E5
0x18000f7d9  cmp     rax, rbx
0x18000f7dc  jz      short loc_18000F7EF
0x18000f7de  lea     rcx, [rax+10h]
0x18000f7e2  mov     [rbx], rcx
0x18000f7e5  mov     rax, [rcx]
0x18000f7e8  test    rax, rax
0x18000f7eb  jnz     short loc_18000F7D9
0x18000f7ed  jmp     short loc_18000F7F6
0x18000f7ef  mov     rax, [rbx+10h]
0x18000f7f3  mov     [rcx], rax
0x18000f7f6  mov     qword ptr [rbx], 0
0x18000f7fd  add     rsp, 20h
0x18000f801  pop     rbx
0x18000f802  retn
```
