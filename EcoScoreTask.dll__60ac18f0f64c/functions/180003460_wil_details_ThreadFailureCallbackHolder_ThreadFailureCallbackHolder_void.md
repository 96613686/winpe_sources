# wil::details::ThreadFailureCallbackHolder::~ThreadFailureCallbackHolder(void)

- ea: `0x180003460`
- end: `0x1800034d8`
- name: `??1ThreadFailureCallbackHolder@details@wil@@QEAA@XZ`
- size: `120`
- prototype: `void __fastcall(wil::details::ThreadFailureCallbackHolder *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180002fd4`

## callees

- `0x180003460`
- `0x180009010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180003476`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180003476`

## string_xrefs

- `0x180003491`: `MEMORY CORRUPTION: Calling code is leaking an activity thread-watcher and releasing it on another thread`

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
    v3 = *(wil::details::ThreadFailureCallbackHolder ***)this;
    *((_DWORD *)this + 6) = 0;
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
0x180003460  mov     [rsp+arg_0], rbx
0x180003465  push    rdi
0x180003466  sub     rsp, 20h
0x18000346a  cmp     dword ptr [rcx+18h], 0
0x18000346e  mov     rdi, rcx
0x180003471  jz      short loc_1800034CD
0x180003473  mov     ebx, [rcx+18h]
0x180003476  call    cs:__imp_GetCurrentThreadId
0x18000347c  cmp     ebx, eax
0x18000347e  jz      short loc_18000349D
0x180003480  mov     rax, cs:?g_pfnReportFatalUsageError@details@wil@@3P6AXPEBDPEBX@_EEA
0x180003487  test    rax, rax
0x18000348a  jz      short loc_18000349D
0x18000348c  mov     rdx, [rsp+28h]
0x180003491  lea     rcx, aMemoryCorrupti; "MEMORY CORRUPTION: Calling code is leak"...
0x180003498  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000349d  mov     rcx, [rdi]
0x1800034a0  mov     dword ptr [rdi+18h], 0
0x1800034a7  jmp     short loc_1800034B5
0x1800034a9  cmp     rax, rdi
0x1800034ac  jz      short loc_1800034BF
0x1800034ae  lea     rcx, [rax+10h]
0x1800034b2  mov     [rdi], rcx
0x1800034b5  mov     rax, [rcx]
0x1800034b8  test    rax, rax
0x1800034bb  jnz     short loc_1800034A9
0x1800034bd  jmp     short loc_1800034C6
0x1800034bf  mov     rax, [rdi+10h]
0x1800034c3  mov     [rcx], rax
0x1800034c6  mov     qword ptr [rdi], 0
0x1800034cd  mov     rbx, [rsp+28h+arg_0]
0x1800034d2  add     rsp, 20h
0x1800034d6  pop     rdi
0x1800034d7  retn
```
