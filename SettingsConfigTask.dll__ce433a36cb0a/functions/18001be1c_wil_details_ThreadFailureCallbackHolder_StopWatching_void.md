# wil::details::ThreadFailureCallbackHolder::StopWatching(void)

- ea: `0x18001be1c`
- end: `0x18001be83`
- name: `?StopWatching@ThreadFailureCallbackHolder@details@wil@@QEAAXXZ`
- size: `103`
- prototype: `void __fastcall(wil::details::ThreadFailureCallbackHolder *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180012b38`

## callees

- `0x18001be1c`
- `0x180024010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001be25`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001be25`

## string_xrefs

- `0x18001be41`: `MEMORY CORRUPTION: Calling code is leaking an activity thread-watcher and releasing it on another thread`

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
0x18001be1c  push    rbx
0x18001be1e  sub     rsp, 20h
0x18001be22  mov     rbx, rcx
0x18001be25  call    cs:__imp_GetCurrentThreadId
0x18001be2b  cmp     [rbx+18h], eax
0x18001be2e  jz      short loc_18001BE4D
0x18001be30  mov     rax, cs:?g_pfnReportFatalUsageError@details@wil@@3P6AXPEBDPEBX@_EEA
0x18001be37  test    rax, rax
0x18001be3a  jz      short loc_18001BE4D
0x18001be3c  mov     rdx, [rsp+28h]
0x18001be41  lea     rcx, aMemoryCorrupti; "MEMORY CORRUPTION: Calling code is leak"...
0x18001be48  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001be4d  mov     rcx, [rbx]
0x18001be50  mov     dword ptr [rbx+18h], 0
0x18001be57  jmp     short loc_18001BE65
0x18001be59  cmp     rax, rbx
0x18001be5c  jz      short loc_18001BE6F
0x18001be5e  lea     rcx, [rax+10h]
0x18001be62  mov     [rbx], rcx
0x18001be65  mov     rax, [rcx]
0x18001be68  test    rax, rax
0x18001be6b  jnz     short loc_18001BE59
0x18001be6d  jmp     short loc_18001BE76
0x18001be6f  mov     rax, [rbx+10h]
0x18001be73  mov     [rcx], rax
0x18001be76  mov     qword ptr [rbx], 0
0x18001be7d  add     rsp, 20h
0x18001be81  pop     rbx
0x18001be82  retn
```
