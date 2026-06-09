# wil::details::ThreadFailureCallbackHolder::~ThreadFailureCallbackHolder(void)

- ea: `0x180014770`
- end: `0x1800147e8`
- name: `??1ThreadFailureCallbackHolder@details@wil@@QEAA@XZ`
- size: `120`
- prototype: `void __fastcall(wil::details::ThreadFailureCallbackHolder *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180014258`

## callees

- `0x180014770`
- `0x18002f010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180014786`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180014786`

## string_xrefs

- `0x1800147a1`: `MEMORY CORRUPTION: Calling code is leaking an activity thread-watcher and releasing it on another thread`

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
0x180014770  mov     [rsp+arg_0], rbx
0x180014775  push    rdi
0x180014776  sub     rsp, 20h
0x18001477a  mov     rdi, rcx
0x18001477d  cmp     dword ptr [rcx+18h], 0
0x180014781  jz      short loc_1800147DD
0x180014783  mov     ebx, [rcx+18h]
0x180014786  call    cs:__imp_GetCurrentThreadId
0x18001478c  cmp     ebx, eax
0x18001478e  jz      short loc_1800147AD
0x180014790  mov     rax, cs:?g_pfnReportFatalUsageError@details@wil@@3P6AXPEBDPEBX@_EEA
0x180014797  test    rax, rax
0x18001479a  jz      short loc_1800147AD
0x18001479c  mov     rdx, [rsp+28h]
0x1800147a1  lea     rcx, aMemoryCorrupti; "MEMORY CORRUPTION: Calling code is leak"...
0x1800147a8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800147ad  mov     dword ptr [rdi+18h], 0
0x1800147b4  mov     rcx, [rdi]
0x1800147b7  jmp     short loc_1800147C5
0x1800147b9  cmp     rax, rdi
0x1800147bc  jz      short loc_1800147CF
0x1800147be  lea     rcx, [rax+10h]
0x1800147c2  mov     [rdi], rcx
0x1800147c5  mov     rax, [rcx]
0x1800147c8  test    rax, rax
0x1800147cb  jnz     short loc_1800147B9
0x1800147cd  jmp     short loc_1800147D6
0x1800147cf  mov     rax, [rdi+10h]
0x1800147d3  mov     [rcx], rax
0x1800147d6  mov     qword ptr [rdi], 0
0x1800147dd  mov     rbx, [rsp+28h+arg_0]
0x1800147e2  add     rsp, 20h
0x1800147e6  pop     rdi
0x1800147e7  retn
```
