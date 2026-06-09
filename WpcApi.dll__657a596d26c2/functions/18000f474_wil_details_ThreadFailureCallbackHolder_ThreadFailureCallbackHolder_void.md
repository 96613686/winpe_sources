# wil::details::ThreadFailureCallbackHolder::~ThreadFailureCallbackHolder(void)

- ea: `0x18000f474`
- end: `0x18000f4ec`
- name: `??1ThreadFailureCallbackHolder@details@wil@@QEAA@XZ`
- size: `120`
- prototype: `void __fastcall(wil::details::ThreadFailureCallbackHolder *__hidden this)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x18000ed54`
- `0x18001fd4c`

## callees

- `0x18000f474`
- `0x18002c010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000f48a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000f48a`

## string_xrefs

- `0x18000f4a5`: `MEMORY CORRUPTION: Calling code is leaking an activity thread-watcher and releasing it on another thread`

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
0x18000f474  mov     [rsp+arg_0], rbx
0x18000f479  push    rdi
0x18000f47a  sub     rsp, 20h
0x18000f47e  mov     rdi, rcx
0x18000f481  cmp     dword ptr [rcx+18h], 0
0x18000f485  jz      short loc_18000F4E1
0x18000f487  mov     ebx, [rcx+18h]
0x18000f48a  call    cs:__imp_GetCurrentThreadId
0x18000f490  cmp     ebx, eax
0x18000f492  jz      short loc_18000F4B1
0x18000f494  mov     rax, cs:?g_pfnReportFatalUsageError@details@wil@@3P6AXPEBDPEBX@_EEA
0x18000f49b  test    rax, rax
0x18000f49e  jz      short loc_18000F4B1
0x18000f4a0  mov     rdx, [rsp+28h]
0x18000f4a5  lea     rcx, aMemoryCorrupti; "MEMORY CORRUPTION: Calling code is leak"...
0x18000f4ac  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f4b1  mov     dword ptr [rdi+18h], 0
0x18000f4b8  mov     rcx, [rdi]
0x18000f4bb  jmp     short loc_18000F4C9
0x18000f4bd  cmp     rax, rdi
0x18000f4c0  jz      short loc_18000F4D3
0x18000f4c2  lea     rcx, [rax+10h]
0x18000f4c6  mov     [rdi], rcx
0x18000f4c9  mov     rax, [rcx]
0x18000f4cc  test    rax, rax
0x18000f4cf  jnz     short loc_18000F4BD
0x18000f4d1  jmp     short loc_18000F4DA
0x18000f4d3  mov     rax, [rdi+10h]
0x18000f4d7  mov     [rcx], rax
0x18000f4da  mov     qword ptr [rdi], 0
0x18000f4e1  mov     rbx, [rsp+28h+arg_0]
0x18000f4e6  add     rsp, 20h
0x18000f4ea  pop     rdi
0x18000f4eb  retn
```
