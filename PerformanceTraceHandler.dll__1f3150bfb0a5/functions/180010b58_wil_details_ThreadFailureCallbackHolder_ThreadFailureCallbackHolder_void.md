# wil::details::ThreadFailureCallbackHolder::~ThreadFailureCallbackHolder(void)

- ea: `0x180010b58`
- end: `0x180010bce`
- name: `??1ThreadFailureCallbackHolder@details@wil@@QEAA@XZ`
- size: `118`
- prototype: `void __fastcall(wil::details::ThreadFailureCallbackHolder *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180010ac8`

## callees

- `0x180010b58`
- `0x18001c010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180010b6e`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180010b6e`

## string_xrefs

- `0x180010b89`: `MEMORY CORRUPTION: Calling code is leaking an activity thread-watcher and releasing it on another thread`

## pseudocode

```c
void __fastcall wil::details::ThreadFailureCallbackHolder::~ThreadFailureCallbackHolder(
        wil::details::ThreadFailureCallbackHolder *this)
{
  int v2; // ebx
  wil::details::ThreadFailureCallbackHolder *v3; // rax
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
    while ( 1 )
    {
      v3 = **(wil::details::ThreadFailureCallbackHolder ***)this;
      if ( !v3 )
        break;
      if ( v3 == this )
      {
        **(_QWORD **)this = *((_QWORD *)this + 2);
        break;
      }
      *(_QWORD *)this = (char *)v3 + 16;
    }
    *(_QWORD *)this = 0;
  }
}

```

## disassembly

```asm
0x180010b58  mov     [rsp+arg_0], rbx
0x180010b5d  push    rdi
0x180010b5e  sub     rsp, 20h
0x180010b62  mov     rdi, rcx
0x180010b65  cmp     dword ptr [rcx+18h], 0
0x180010b69  jz      short loc_180010BC3
0x180010b6b  mov     ebx, [rcx+18h]
0x180010b6e  call    cs:__imp_GetCurrentThreadId
0x180010b74  cmp     ebx, eax
0x180010b76  jz      short loc_180010B95
0x180010b78  mov     rax, cs:?g_pfnReportFatalUsageError@details@wil@@3P6AXPEBDPEBX@_EEA
0x180010b7f  test    rax, rax
0x180010b82  jz      short loc_180010B95
0x180010b84  mov     rdx, [rsp+28h]
0x180010b89  lea     rcx, aMemoryCorrupti; "MEMORY CORRUPTION: Calling code is leak"...
0x180010b90  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010b95  mov     dword ptr [rdi+18h], 0
0x180010b9c  mov     rcx, [rdi]
0x180010b9f  mov     rax, [rcx]
0x180010ba2  test    rax, rax
0x180010ba5  jz      short loc_180010BBC
0x180010ba7  cmp     rax, rdi
0x180010baa  jz      short loc_180010BB5
0x180010bac  add     rax, 10h
0x180010bb0  mov     [rdi], rax
0x180010bb3  jmp     short loc_180010B9C
0x180010bb5  mov     rax, [rdi+10h]
0x180010bb9  mov     [rcx], rax
0x180010bbc  mov     qword ptr [rdi], 0
0x180010bc3  mov     rbx, [rsp+28h+arg_0]
0x180010bc8  add     rsp, 20h
0x180010bcc  pop     rdi
0x180010bcd  retn
```
