# wil::details::ThreadFailureCallbackHolder::StopWatching(void)

- ea: `0x18001bc18`
- end: `0x18001bc7f`
- name: `?StopWatching@ThreadFailureCallbackHolder@details@wil@@QEAAXXZ`
- size: `103`
- prototype: `void __fastcall(wil::details::ThreadFailureCallbackHolder *__hidden this)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x180018e3c`
- `0x18001ab14`

## callees

- `0x18001bc18`
- `0x18004e010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001bc21`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001bc21`

## string_xrefs

- `0x18001bc3d`: `MEMORY CORRUPTION: Calling code is leaking an activity thread-watcher and releasing it on another thread`

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
0x18001bc18  push    rbx
0x18001bc1a  sub     rsp, 20h
0x18001bc1e  mov     rbx, rcx
0x18001bc21  call    cs:__imp_GetCurrentThreadId
0x18001bc27  cmp     [rbx+18h], eax
0x18001bc2a  jz      short loc_18001BC49
0x18001bc2c  mov     rax, cs:?g_pfnReportFatalUsageError@details@wil@@3P6AXPEBDPEBX@_EEA
0x18001bc33  test    rax, rax
0x18001bc36  jz      short loc_18001BC49
0x18001bc38  mov     rdx, [rsp+28h]
0x18001bc3d  lea     rcx, aMemoryCorrupti; "MEMORY CORRUPTION: Calling code is leak"...
0x18001bc44  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001bc49  mov     rcx, [rbx]
0x18001bc4c  mov     dword ptr [rbx+18h], 0
0x18001bc53  jmp     short loc_18001BC61
0x18001bc55  cmp     rax, rbx
0x18001bc58  jz      short loc_18001BC6B
0x18001bc5a  lea     rcx, [rax+10h]
0x18001bc5e  mov     [rbx], rcx
0x18001bc61  mov     rax, [rcx]
0x18001bc64  test    rax, rax
0x18001bc67  jnz     short loc_18001BC55
0x18001bc69  jmp     short loc_18001BC72
0x18001bc6b  mov     rax, [rbx+10h]
0x18001bc6f  mov     [rcx], rax
0x18001bc72  mov     qword ptr [rbx], 0
0x18001bc79  add     rsp, 20h
0x18001bc7d  pop     rbx
0x18001bc7e  retn
```
