# wil::details::ThreadFailureCallbackHolder::~ThreadFailureCallbackHolder(void)

- ea: `0x1800149fc`
- end: `0x180014a74`
- name: `??1ThreadFailureCallbackHolder@details@wil@@QEAA@XZ`
- size: `120`
- prototype: `void __fastcall(wil::details::ThreadFailureCallbackHolder *__hidden this)`
- caller_count: `15`
- callee_count: `2`
- tags: ``

## callers

- `0x180013ecc`
- `0x180013f1c`
- `0x180014c40`
- `0x180015930`
- `0x18001b234`
- `0x18001c060`
- `0x18001c64c`
- `0x18001d95c`
- `0x18002b6a8`
- `0x1800437ec`
- `0x180046cf0`
- `0x18004c184`
- `0x1800e6bb8`
- `0x1800e75bc`
- `0x1800f4eb4`

## callees

- `0x1800149fc`
- `0x180108010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180014a12`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180014a12`

## string_xrefs

- `0x180014a2d`: `MEMORY CORRUPTION: Calling code is leaking an activity thread-watcher and releasing it on another thread`

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
0x1800149fc  mov     [rsp+arg_0], rbx
0x180014a01  push    rdi
0x180014a02  sub     rsp, 20h
0x180014a06  mov     rdi, rcx
0x180014a09  cmp     dword ptr [rcx+18h], 0
0x180014a0d  jz      short loc_180014A69
0x180014a0f  mov     ebx, [rcx+18h]
0x180014a12  call    cs:__imp_GetCurrentThreadId
0x180014a18  cmp     ebx, eax
0x180014a1a  jz      short loc_180014A39
0x180014a1c  mov     rax, cs:?g_pfnReportFatalUsageError@details@wil@@3P6AXPEBDPEBX@_EEA
0x180014a23  test    rax, rax
0x180014a26  jz      short loc_180014A39
0x180014a28  mov     rdx, [rsp+28h]
0x180014a2d  lea     rcx, aMemoryCorrupti; "MEMORY CORRUPTION: Calling code is leak"...
0x180014a34  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014a39  mov     dword ptr [rdi+18h], 0
0x180014a40  mov     rcx, [rdi]
0x180014a43  jmp     short loc_180014A51
0x180014a45  cmp     rax, rdi
0x180014a48  jz      short loc_180014A5B
0x180014a4a  lea     rcx, [rax+10h]
0x180014a4e  mov     [rdi], rcx
0x180014a51  mov     rax, [rcx]
0x180014a54  test    rax, rax
0x180014a57  jnz     short loc_180014A45
0x180014a59  jmp     short loc_180014A62
0x180014a5b  mov     rax, [rdi+10h]
0x180014a5f  mov     [rcx], rax
0x180014a62  mov     qword ptr [rdi], 0
0x180014a69  mov     rbx, [rsp+28h+arg_0]
0x180014a6e  add     rsp, 20h
0x180014a72  pop     rdi
0x180014a73  retn
```
