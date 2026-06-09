# wil::details::ThreadFailureCallbackHolder::~ThreadFailureCallbackHolder(void)

- ea: `0x180014ef8`
- end: `0x180014f70`
- name: `??1ThreadFailureCallbackHolder@details@wil@@QEAA@XZ`
- size: `120`
- prototype: `void __fastcall(wil::details::ThreadFailureCallbackHolder *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180014b4c`

## callees

- `0x180014ef8`
- `0x18002e010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180014f0e`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180014f0e`

## string_xrefs

- `0x180014f29`: `MEMORY CORRUPTION: Calling code is leaking an activity thread-watcher and releasing it on another thread`

## pseudocode

```c
void __fastcall wil::details::ThreadFailureCallbackHolder::~ThreadFailureCallbackHolder(
        wil::details::ThreadFailureCallbackHolder *this)
{
  int v2; // ebx
  wil::details::ThreadFailureCallbackHolder **v3; // rcx
  wil::details::ThreadFailureCallbackHolder *v4; // rax
  void *retaddr; // [rsp+28h] [rbp+0h]

  if ( *((_DWORD *)this + 6) )
  {
    v2 = *((_DWORD *)this + 6);
    if ( v2 != GetCurrentThreadId() )
    {
      if ( wil::details::g_pfnReportFatalUsageError )
        wil::details::g_pfnReportFatalUsageError(
          "MEMORY CORRUPTION: Calling code is leaking an activity thread-watcher and releasing it on another thread",
          retaddr);
    }
    *((_DWORD *)this + 6) = 0;
    v3 = *(wil::details::ThreadFailureCallbackHolder ***)this;
    while ( 1 )
    {
      v4 = *v3;
      if ( !*v3 )
        break;
      if ( v4 == this )
      {
        *v3 = (wil::details::ThreadFailureCallbackHolder *)*((_QWORD *)this + 2);
        break;
      }
      v3 = (wil::details::ThreadFailureCallbackHolder **)((char *)v4 + 16);
      *(_QWORD *)this = (char *)v4 + 16;
    }
    *(_QWORD *)this = 0;
  }
}

```

## disassembly

```asm
0x180014ef8  mov     [rsp+arg_0], rbx
0x180014efd  push    rdi
0x180014efe  sub     rsp, 20h
0x180014f02  mov     rdi, rcx
0x180014f05  cmp     dword ptr [rcx+18h], 0
0x180014f09  jz      short loc_180014F65
0x180014f0b  mov     ebx, [rcx+18h]
0x180014f0e  call    cs:__imp_GetCurrentThreadId
0x180014f14  cmp     ebx, eax
0x180014f16  jz      short loc_180014F35
0x180014f18  mov     rax, cs:?g_pfnReportFatalUsageError@details@wil@@3P6AXPEBDPEBX@_EEA; __annotation("Debug", "TelemetryAssert", "MEMORY CORRUPTION: Calling code is leaking an activity thread-watcher and releasing it on another thread")
0x180014f1f  test    rax, rax
0x180014f22  jz      short loc_180014F35
0x180014f24  mov     rdx, [rsp+28h]
0x180014f29  lea     rcx, aMemoryCorrupti; "MEMORY CORRUPTION: Calling code is leak"...
0x180014f30  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014f35  mov     dword ptr [rdi+18h], 0
0x180014f3c  mov     rcx, [rdi]
0x180014f3f  jmp     short loc_180014F4D
0x180014f41  cmp     rax, rdi
0x180014f44  jz      short loc_180014F57
0x180014f46  lea     rcx, [rax+10h]
0x180014f4a  mov     [rdi], rcx
0x180014f4d  mov     rax, [rcx]
0x180014f50  test    rax, rax
0x180014f53  jnz     short loc_180014F41
0x180014f55  jmp     short loc_180014F5E
0x180014f57  mov     rax, [rdi+10h]
0x180014f5b  mov     [rcx], rax
0x180014f5e  mov     qword ptr [rdi], 0
0x180014f65  mov     rbx, [rsp+28h+arg_0]
0x180014f6a  add     rsp, 20h
0x180014f6e  pop     rdi
0x180014f6f  retn
```
