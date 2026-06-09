# wil::details::ThreadFailureCallbackHolder::~ThreadFailureCallbackHolder(void)

- ea: `0x180007a10`
- end: `0x180007a8f`
- name: `??1ThreadFailureCallbackHolder@details@wil@@QEAA@XZ`
- size: `127`
- prototype: `void __fastcall(wil::details::ThreadFailureCallbackHolder *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180007510`

## callees

- `0x180007a10`
- `0x180011010`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x180007a26`
- `KERNEL32!GetCurrentThreadId` at `0x180007a26`

## string_xrefs

- `0x180007a47`: `MEMORY CORRUPTION: Calling code is leaking an activity thread-watcher and releasing it on another thread`

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
0x180007a10  mov     [rsp+arg_0], rbx
0x180007a15  push    rdi
0x180007a16  sub     rsp, 20h
0x180007a1a  mov     rdi, rcx
0x180007a1d  cmp     dword ptr [rcx+18h], 0
0x180007a21  jz      short loc_180007A83
0x180007a23  mov     ebx, [rcx+18h]
0x180007a26  call    cs:__imp_GetCurrentThreadId
0x180007a2d  nop     dword ptr [rax+rax+00h]
0x180007a32  cmp     ebx, eax
0x180007a34  jz      short loc_180007A53
0x180007a36  mov     rax, cs:?g_pfnReportFatalUsageError@details@wil@@3P6AXPEBDPEBX@_EEA
0x180007a3d  test    rax, rax
0x180007a40  jz      short loc_180007A53
0x180007a42  mov     rdx, [rsp+28h]
0x180007a47  lea     rcx, aMemoryCorrupti; "MEMORY CORRUPTION: Calling code is leak"...
0x180007a4e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007a53  mov     dword ptr [rdi+18h], 0
0x180007a5a  mov     rcx, [rdi]
0x180007a5d  jmp     short loc_180007A6B
0x180007a5f  cmp     rax, rdi
0x180007a62  jz      short loc_180007A75
0x180007a64  lea     rcx, [rax+10h]
0x180007a68  mov     [rdi], rcx
0x180007a6b  mov     rax, [rcx]
0x180007a6e  test    rax, rax
0x180007a71  jnz     short loc_180007A5F
0x180007a73  jmp     short loc_180007A7C
0x180007a75  mov     rax, [rdi+10h]
0x180007a79  mov     [rcx], rax
0x180007a7c  mov     qword ptr [rdi], 0
0x180007a83  mov     rbx, [rsp+28h+arg_0]
0x180007a88  add     rsp, 20h
0x180007a8c  pop     rdi
0x180007a8d  retn
```
