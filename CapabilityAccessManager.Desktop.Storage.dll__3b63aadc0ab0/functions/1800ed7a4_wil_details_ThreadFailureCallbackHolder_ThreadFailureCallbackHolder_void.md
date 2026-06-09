# wil::details::ThreadFailureCallbackHolder::~ThreadFailureCallbackHolder(void)

- ea: `0x1800ed7a4`
- end: `0x1800ed81c`
- name: `??1ThreadFailureCallbackHolder@details@wil@@QEAA@XZ`
- size: `120`
- prototype: `void __fastcall(wil::details::ThreadFailureCallbackHolder *__hidden this)`
- caller_count: `5`
- callee_count: `2`
- tags: ``

## callers

- `0x1800ed778`
- `0x1800f28f4`
- `0x1800f6a20`
- `0x1800f8448`
- `0x180107ad4`

## callees

- `0x1800ed7a4`
- `0x18010d010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800ed7ba`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800ed7ba`

## string_xrefs

- `0x1800ed7d5`: `MEMORY CORRUPTION: Calling code is leaking an activity thread-watcher and releasing it on another thread`

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
0x1800ed7a4  mov     [rsp+arg_0], rbx
0x1800ed7a9  push    rdi
0x1800ed7aa  sub     rsp, 20h
0x1800ed7ae  mov     rdi, rcx
0x1800ed7b1  cmp     dword ptr [rcx+18h], 0
0x1800ed7b5  jz      short loc_1800ED811
0x1800ed7b7  mov     ebx, [rcx+18h]
0x1800ed7ba  call    cs:__imp_GetCurrentThreadId
0x1800ed7c0  cmp     ebx, eax
0x1800ed7c2  jz      short loc_1800ED7E1
0x1800ed7c4  mov     rax, cs:?g_pfnReportFatalUsageError@details@wil@@3P6AXPEBDPEBX@_EEA
0x1800ed7cb  test    rax, rax
0x1800ed7ce  jz      short loc_1800ED7E1
0x1800ed7d0  mov     rdx, [rsp+28h]
0x1800ed7d5  lea     rcx, aMemoryCorrupti; "MEMORY CORRUPTION: Calling code is leak"...
0x1800ed7dc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ed7e1  mov     dword ptr [rdi+18h], 0
0x1800ed7e8  mov     rcx, [rdi]
0x1800ed7eb  jmp     short loc_1800ED7F9
0x1800ed7ed  cmp     rax, rdi
0x1800ed7f0  jz      short loc_1800ED803
0x1800ed7f2  lea     rcx, [rax+10h]
0x1800ed7f6  mov     [rdi], rcx
0x1800ed7f9  mov     rax, [rcx]
0x1800ed7fc  test    rax, rax
0x1800ed7ff  jnz     short loc_1800ED7ED
0x1800ed801  jmp     short loc_1800ED80A
0x1800ed803  mov     rax, [rdi+10h]
0x1800ed807  mov     [rcx], rax
0x1800ed80a  mov     qword ptr [rdi], 0
0x1800ed811  mov     rbx, [rsp+28h+arg_0]
0x1800ed816  add     rsp, 20h
0x1800ed81a  pop     rdi
0x1800ed81b  retn
```
