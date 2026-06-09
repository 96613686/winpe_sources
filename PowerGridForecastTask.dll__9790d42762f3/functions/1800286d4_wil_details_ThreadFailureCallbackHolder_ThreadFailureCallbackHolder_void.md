# wil::details::ThreadFailureCallbackHolder::~ThreadFailureCallbackHolder(void)

- ea: `0x1800286d4`
- end: `0x18002874c`
- name: `??1ThreadFailureCallbackHolder@details@wil@@QEAA@XZ`
- size: `120`
- prototype: `void __fastcall(wil::details::ThreadFailureCallbackHolder *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180027cc4`

## callees

- `0x1800286d4`
- `0x180037010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800286ea`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800286ea`

## string_xrefs

- `0x180028705`: `MEMORY CORRUPTION: Calling code is leaking an activity thread-watcher and releasing it on another thread`

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
0x1800286d4  mov     [rsp+arg_0], rbx
0x1800286d9  push    rdi
0x1800286da  sub     rsp, 20h
0x1800286de  mov     rdi, rcx
0x1800286e1  cmp     dword ptr [rcx+18h], 0
0x1800286e5  jz      short loc_180028741
0x1800286e7  mov     ebx, [rcx+18h]
0x1800286ea  call    cs:__imp_GetCurrentThreadId
0x1800286f0  cmp     ebx, eax
0x1800286f2  jz      short loc_180028711
0x1800286f4  mov     rax, cs:?g_pfnReportFatalUsageError@details@wil@@3P6AXPEBDPEBX@_EEA
0x1800286fb  test    rax, rax
0x1800286fe  jz      short loc_180028711
0x180028700  mov     rdx, [rsp+28h]
0x180028705  lea     rcx, aMemoryCorrupti; "MEMORY CORRUPTION: Calling code is leak"...
0x18002870c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180028711  mov     dword ptr [rdi+18h], 0
0x180028718  mov     rcx, [rdi]
0x18002871b  jmp     short loc_180028729
0x18002871d  cmp     rax, rdi
0x180028720  jz      short loc_180028733
0x180028722  lea     rcx, [rax+10h]
0x180028726  mov     [rdi], rcx
0x180028729  mov     rax, [rcx]
0x18002872c  test    rax, rax
0x18002872f  jnz     short loc_18002871D
0x180028731  jmp     short loc_18002873A
0x180028733  mov     rax, [rdi+10h]
0x180028737  mov     [rcx], rax
0x18002873a  mov     qword ptr [rdi], 0
0x180028741  mov     rbx, [rsp+28h+arg_0]
0x180028746  add     rsp, 20h
0x18002874a  pop     rdi
0x18002874b  retn
```
