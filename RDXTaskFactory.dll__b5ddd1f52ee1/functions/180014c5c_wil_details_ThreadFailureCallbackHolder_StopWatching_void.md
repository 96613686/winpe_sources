# wil::details::ThreadFailureCallbackHolder::StopWatching(void)

- ea: `0x180014c5c`
- end: `0x180014cc3`
- name: `?StopWatching@ThreadFailureCallbackHolder@details@wil@@QEAAXXZ`
- size: `103`
- prototype: `void __fastcall(wil::details::ThreadFailureCallbackHolder *__hidden this)`
- caller_count: `3`
- callee_count: `2`
- tags: ``

## callers

- `0x180013c00`
- `0x180014128`
- `0x180047978`

## callees

- `0x180014c5c`
- `0x180050010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180014c65`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180014c65`

## string_xrefs

- `0x180014c81`: `MEMORY CORRUPTION: Calling code is leaking an activity thread-watcher and releasing it on another thread`

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
0x180014c5c  push    rbx
0x180014c5e  sub     rsp, 20h
0x180014c62  mov     rbx, rcx
0x180014c65  call    cs:__imp_GetCurrentThreadId
0x180014c6b  cmp     [rbx+18h], eax
0x180014c6e  jz      short loc_180014C8D
0x180014c70  mov     rax, cs:?g_pfnReportFatalUsageError@details@wil@@3P6AXPEBDPEBX@_EEA
0x180014c77  test    rax, rax
0x180014c7a  jz      short loc_180014C8D
0x180014c7c  mov     rdx, [rsp+28h]
0x180014c81  lea     rcx, aMemoryCorrupti; "MEMORY CORRUPTION: Calling code is leak"...
0x180014c88  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014c8d  mov     rcx, [rbx]
0x180014c90  mov     dword ptr [rbx+18h], 0
0x180014c97  jmp     short loc_180014CA5
0x180014c99  cmp     rax, rbx
0x180014c9c  jz      short loc_180014CAF
0x180014c9e  lea     rcx, [rax+10h]
0x180014ca2  mov     [rbx], rcx
0x180014ca5  mov     rax, [rcx]
0x180014ca8  test    rax, rax
0x180014cab  jnz     short loc_180014C99
0x180014cad  jmp     short loc_180014CB6
0x180014caf  mov     rax, [rbx+10h]
0x180014cb3  mov     [rcx], rax
0x180014cb6  mov     qword ptr [rbx], 0
0x180014cbd  add     rsp, 20h
0x180014cc1  pop     rbx
0x180014cc2  retn
```
