# wil::details::ThreadFailureCallbackHolder::~ThreadFailureCallbackHolder(void)

- ea: `0x1800063b4`
- end: `0x18000642c`
- name: `??1ThreadFailureCallbackHolder@details@wil@@QEAA@XZ`
- size: `120`
- prototype: `void __fastcall(wil::details::ThreadFailureCallbackHolder *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180005878`

## callees

- `0x1800063b4`
- `0x180012010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800063ca`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800063ca`

## string_xrefs

- `0x1800063e5`: `MEMORY CORRUPTION: Calling code is leaking an activity thread-watcher and releasing it on another thread`

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
0x1800063b4  mov     [rsp+arg_0], rbx
0x1800063b9  push    rdi
0x1800063ba  sub     rsp, 20h
0x1800063be  mov     rdi, rcx
0x1800063c1  cmp     dword ptr [rcx+18h], 0
0x1800063c5  jz      short loc_180006421
0x1800063c7  mov     ebx, [rcx+18h]
0x1800063ca  call    cs:__imp_GetCurrentThreadId
0x1800063d0  cmp     ebx, eax
0x1800063d2  jz      short loc_1800063F1
0x1800063d4  mov     rax, cs:?g_pfnReportFatalUsageError@details@wil@@3P6AXPEBDPEBX@_EEA
0x1800063db  test    rax, rax
0x1800063de  jz      short loc_1800063F1
0x1800063e0  mov     rdx, [rsp+28h]
0x1800063e5  lea     rcx, aMemoryCorrupti; "MEMORY CORRUPTION: Calling code is leak"...
0x1800063ec  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800063f1  mov     dword ptr [rdi+18h], 0
0x1800063f8  mov     rcx, [rdi]
0x1800063fb  jmp     short loc_180006409
0x1800063fd  cmp     rax, rdi
0x180006400  jz      short loc_180006413
0x180006402  lea     rcx, [rax+10h]
0x180006406  mov     [rdi], rcx
0x180006409  mov     rax, [rcx]
0x18000640c  test    rax, rax
0x18000640f  jnz     short loc_1800063FD
0x180006411  jmp     short loc_18000641A
0x180006413  mov     rax, [rdi+10h]
0x180006417  mov     [rcx], rax
0x18000641a  mov     qword ptr [rdi], 0
0x180006421  mov     rbx, [rsp+28h+arg_0]
0x180006426  add     rsp, 20h
0x18000642a  pop     rdi
0x18000642b  retn
```
