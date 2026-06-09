# wil::details::ThreadFailureCallbackHolder::~ThreadFailureCallbackHolder(void)

- ea: `0x1800152f4`
- end: `0x180015373`
- name: `??1ThreadFailureCallbackHolder@details@wil@@QEAA@XZ`
- size: `127`
- prototype: `void __fastcall(wil::details::ThreadFailureCallbackHolder *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180014f38`

## callees

- `0x1800152f4`
- `0x18002f010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001530a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001530a`

## string_xrefs

- `0x18001532b`: `MEMORY CORRUPTION: Calling code is leaking an activity thread-watcher and releasing it on another thread`

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
0x1800152f4  mov     [rsp+arg_0], rbx
0x1800152f9  push    rdi
0x1800152fa  sub     rsp, 20h
0x1800152fe  mov     rdi, rcx
0x180015301  cmp     dword ptr [rcx+18h], 0
0x180015305  jz      short loc_180015367
0x180015307  mov     ebx, [rcx+18h]
0x18001530a  call    cs:__imp_GetCurrentThreadId
0x180015311  nop     dword ptr [rax+rax+00h]
0x180015316  cmp     ebx, eax
0x180015318  jz      short loc_180015337
0x18001531a  mov     rax, cs:?g_pfnReportFatalUsageError@details@wil@@3P6AXPEBDPEBX@_EEA
0x180015321  test    rax, rax
0x180015324  jz      short loc_180015337
0x180015326  mov     rdx, [rsp+28h]
0x18001532b  lea     rcx, aMemoryCorrupti; "MEMORY CORRUPTION: Calling code is leak"...
0x180015332  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015337  mov     dword ptr [rdi+18h], 0
0x18001533e  mov     rcx, [rdi]
0x180015341  jmp     short loc_18001534F
0x180015343  cmp     rax, rdi
0x180015346  jz      short loc_180015359
0x180015348  lea     rcx, [rax+10h]
0x18001534c  mov     [rdi], rcx
0x18001534f  mov     rax, [rcx]
0x180015352  test    rax, rax
0x180015355  jnz     short loc_180015343
0x180015357  jmp     short loc_180015360
0x180015359  mov     rax, [rdi+10h]
0x18001535d  mov     [rcx], rax
0x180015360  mov     qword ptr [rdi], 0
0x180015367  mov     rbx, [rsp+28h+arg_0]
0x18001536c  add     rsp, 20h
0x180015370  pop     rdi
0x180015371  retn
```
