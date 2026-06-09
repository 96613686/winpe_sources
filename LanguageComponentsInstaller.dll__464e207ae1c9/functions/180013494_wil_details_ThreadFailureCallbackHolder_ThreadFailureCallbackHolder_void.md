# wil::details::ThreadFailureCallbackHolder::~ThreadFailureCallbackHolder(void)

- ea: `0x180013494`
- end: `0x18001350c`
- name: `??1ThreadFailureCallbackHolder@details@wil@@QEAA@XZ`
- size: `120`
- prototype: `void __fastcall(wil::details::ThreadFailureCallbackHolder *__hidden this)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x180012160`
- `0x1800248c0`

## callees

- `0x180013494`
- `0x18002a010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800134aa`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800134aa`

## string_xrefs

- `0x1800134c5`: `MEMORY CORRUPTION: Calling code is leaking an activity thread-watcher and releasing it on another thread`

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
0x180013494  mov     [rsp+arg_0], rbx
0x180013499  push    rdi
0x18001349a  sub     rsp, 20h
0x18001349e  mov     rdi, rcx
0x1800134a1  cmp     dword ptr [rcx+18h], 0
0x1800134a5  jz      short loc_180013501
0x1800134a7  mov     ebx, [rcx+18h]
0x1800134aa  call    cs:__imp_GetCurrentThreadId
0x1800134b0  cmp     ebx, eax
0x1800134b2  jz      short loc_1800134D1
0x1800134b4  mov     rax, cs:?g_pfnReportFatalUsageError@details@wil@@3P6AXPEBDPEBX@_EEA
0x1800134bb  test    rax, rax
0x1800134be  jz      short loc_1800134D1
0x1800134c0  mov     rdx, [rsp+28h]
0x1800134c5  lea     rcx, aMemoryCorrupti; "MEMORY CORRUPTION: Calling code is leak"...
0x1800134cc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800134d1  mov     dword ptr [rdi+18h], 0
0x1800134d8  mov     rcx, [rdi]
0x1800134db  jmp     short loc_1800134E9
0x1800134dd  cmp     rax, rdi
0x1800134e0  jz      short loc_1800134F3
0x1800134e2  lea     rcx, [rax+10h]
0x1800134e6  mov     [rdi], rcx
0x1800134e9  mov     rax, [rcx]
0x1800134ec  test    rax, rax
0x1800134ef  jnz     short loc_1800134DD
0x1800134f1  jmp     short loc_1800134FA
0x1800134f3  mov     rax, [rdi+10h]
0x1800134f7  mov     [rcx], rax
0x1800134fa  mov     qword ptr [rdi], 0
0x180013501  mov     rbx, [rsp+28h+arg_0]
0x180013506  add     rsp, 20h
0x18001350a  pop     rdi
0x18001350b  retn
```
