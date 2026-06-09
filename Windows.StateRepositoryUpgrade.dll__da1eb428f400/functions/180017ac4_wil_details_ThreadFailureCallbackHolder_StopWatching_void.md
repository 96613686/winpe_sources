# wil::details::ThreadFailureCallbackHolder::StopWatching(void)

- ea: `0x180017ac4`
- end: `0x180017b2b`
- name: `?StopWatching@ThreadFailureCallbackHolder@details@wil@@QEAAXXZ`
- size: `103`
- prototype: `void __fastcall(wil::details::ThreadFailureCallbackHolder *__hidden this)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x1800157c4`
- `0x18002a938`

## callees

- `0x180017ac4`
- `0x18002f010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180017acd`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180017acd`

## string_xrefs

- `0x180017ae9`: `MEMORY CORRUPTION: Calling code is leaking an activity thread-watcher and releasing it on another thread`

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
0x180017ac4  push    rbx
0x180017ac6  sub     rsp, 20h
0x180017aca  mov     rbx, rcx
0x180017acd  call    cs:__imp_GetCurrentThreadId
0x180017ad3  cmp     [rbx+18h], eax
0x180017ad6  jz      short loc_180017AF5
0x180017ad8  mov     rax, cs:?g_pfnReportFatalUsageError@details@wil@@3P6AXPEBDPEBX@_EEA
0x180017adf  test    rax, rax
0x180017ae2  jz      short loc_180017AF5
0x180017ae4  mov     rdx, [rsp+28h]
0x180017ae9  lea     rcx, aMemoryCorrupti; "MEMORY CORRUPTION: Calling code is leak"...
0x180017af0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017af5  mov     rcx, [rbx]
0x180017af8  mov     dword ptr [rbx+18h], 0
0x180017aff  jmp     short loc_180017B0D
0x180017b01  cmp     rax, rbx
0x180017b04  jz      short loc_180017B17
0x180017b06  lea     rcx, [rax+10h]
0x180017b0a  mov     [rbx], rcx
0x180017b0d  mov     rax, [rcx]
0x180017b10  test    rax, rax
0x180017b13  jnz     short loc_180017B01
0x180017b15  jmp     short loc_180017B1E
0x180017b17  mov     rax, [rbx+10h]
0x180017b1b  mov     [rcx], rax
0x180017b1e  mov     qword ptr [rbx], 0
0x180017b25  add     rsp, 20h
0x180017b29  pop     rbx
0x180017b2a  retn
```
